# KiddieOps — System Architecture

This document describes the planned technical architecture for KiddieOps v1.0. It should be read alongside `KiddieOps_SRS.docx` for full requirement context — REQ/NFR IDs are referenced throughout so implementation choices trace back to a specific requirement.

---

## 1. High-level architecture

```
                        ┌─────────────────────────┐
                        │        Browser           │
                        │   React SPA (mobile-     │
                        │   responsive frontend)   │
                        └────────────┬─────────────┘
                                     │ HTTPS / JSON (REST)
                                     ▼
                          ┌────────────────────────────┐
                         │     Express API server       │
                         │  ─ Auth (JWT)                │
                         │  ─ Role-based middleware     │
                         │  ─ Domain routes/controllers │
                          └────────┬───────────┬───────┘
                                 │           │
                     ┌───────────┘           └───────────┐
                     ▼                                    ▼
         ┌─────────────────────┐                    ┌───────────────────────┐
        │   MySQL               │                 │   Claude API (Anthropic)│
        │   (children, users,   │                 │   AI Guardian query     │
        │   attendance, logs,   │◄──────────────  ┤   synthesis (reads      │
        │   medical records,    │   scoped read   │   scoped child data,    │
        │   notices, sessions)  │   query results │   returns answer)       │
         └─────────────────────┘                    └───────────────────────┘
```

The system is a standard three-tier web app: a React frontend, an Express API, and a PostgreSQL database — plus an external call to the Claude API specifically for AI Guardian queries (REQ30–REQ37).

## 2. Components

### 2.1 Frontend (React)

- Single-page application, mobile-first responsive layout (NFR11).
- Three role-scoped view sets: Administrator, Caregiver, Parent/Guardian — the UI only renders and requests data appropriate to the logged-in role (REQ02, REQ03).
- Key views: Login, Admin Dashboard, Caregiver Dashboard, Parent Dashboard, Child Profile, Attendance, Daily Activity Log, Medical Records, Notices, AI Guardian chat (REQ27–REQ29, EI01, EI02).
- State/session: JWT stored client-side (httpOnly cookie preferred over localStorage where feasible) and attached to API requests.

### 2.2 Backend (Node.js / Express)

- REST API, organized by domain resource: `/auth`, `/users`, `/children`, `/caregivers`, `/classrooms`, `/attendance`, `/activity-logs`, `/medical-records`, `/notices`, `/ai-guardian`.
- **Auth middleware** validates the JWT and attaches the authenticated user + role to the request.
- **Authorization middleware** enforces role-based access control per route (NFR04, NFR05) — e.g., only Administrators/authorized Caregivers can write to `/medical-records`; Parents get read-only access scoped to their own child (REQ22).
- **Audit logging**: medical record reads/writes and AI Guardian queries are logged with actor identity and timestamp (REQ23, REQ37).
- Input validation on all write endpoints (NFR08).

### 2.3 Database (PostgreSQL)

Relational schema matching the entities in SRS Section 6 (Data Requirements): `users`, `children`, `caregivers`, `classrooms`, `attendance`, `activity_logs`, `medical_records`, `notices`, `ai_guardian_sessions`. See Section 4 below for the initial entity-relationship sketch.

PostgreSQL was chosen over a document store because daycare data is inherently relational (a child belongs to a classroom, has one or more guardians, has many attendance and activity-log rows) and benefits from foreign-key integrity, especially for medical records and audit trails.

### 2.4 AI Guardian Assistant (Claude API)

- The backend, not the frontend, calls the Claude API — the frontend only talks to the KiddieOps backend, so the AI provider key is never exposed client-side.
- Flow for a query (REQ30–REQ31):
  1. Parent submits a natural-language question via the chat UI (EI02).
  2. Backend authenticates the request and confirms the requesting parent is linked to the target child (REQ36).
  3. Backend gathers that child's relevant attendance, activity log, milestone, and medical data for the query window.
  4. Backend sends the question + the gathered, scoped data as context to the Claude API.
  5. Claude API returns a synthesized natural-language answer.
  6. Backend logs the query and response (REQ37), then returns the answer to the frontend.
- Session/follow-up handling (REQ32): recent conversation turns for the active session are included in the context sent to Claude so follow-up questions ("give me his meal details for today too") resolve correctly without the parent repeating the child or date.
- Bangla/English support (REQ35): the prompt to Claude specifies to respond in the language the parent used; no separate translation layer planned for v1.0.
- Data isolation (REQ36): every Claude API call is constructed with only the single target child's data — never another child's — enforced at the backend query layer, not just the AI prompt.

## 3. Security notes (traces to NFR04–NFR08)

- Passwords hashed with bcrypt; never logged or returned in API responses.
- JWT with reasonable expiry; role embedded in the token but re-validated against the DB on sensitive operations.
- Medical record and AI Guardian endpoints require an explicit ownership/authorization check on every request — role alone is not sufficient (a Caregiver must be assigned to that child's classroom; a Parent must be linked to that specific child).
- All traffic served over HTTPS; sensitive fields (medical data) encrypted at rest.
- Parameterized queries / an ORM (e.g., Prisma or Sequelize) to prevent SQL injection.

## 4. Data model sketch

```
users (id, name, email, password_hash, role)
children (id, name, dob, classroom_id, allergy_flag, emergency_contact)
child_guardians (child_id, user_id)          -- many-to-many: child <-> parent(s)
caregivers (id, user_id, classroom_id)
classrooms (id, name, age_range)
attendance (id, child_id, date, check_in, check_out, status)
activity_logs (id, child_id, timestamp, type, details, logged_by_user_id)
medical_records (id, child_id, allergies, conditions, medications,
                  immunizations, physician_contact, incident_reports,
                  last_updated_by, updated_at)
medical_record_audit (id, medical_record_id, actor_user_id, action, timestamp)
notices (id, title, description, date, author_user_id)
ai_guardian_sessions (id, guardian_user_id, child_id, query, response, timestamp)
```

This is a starting point for Week 2 schema design, not a final migration — refine alongside the actual ORM/migration tooling chosen.

## 5. Open questions / decisions for Week 2

- [ ] Final ORM choice (Prisma vs. Sequelize vs. raw `pg`).
- [ ] Hosting target for backend + PostgreSQL + frontend (e.g., Render/Railway + Vercel, or a single VPS).
- [ ] Whether classroom assignment for caregivers is one classroom per caregiver or many-to-many.
- [ ] Exact conversation-history window sent to the Claude API for follow-up context (last N turns vs. full session).
