# KiddieOps — Task List / Sprint Backlog

Tracks work by sprint. Each task references its REQ/NFR ID from `KiddieOps_SRS.docx` where applicable, so progress traces back to the SRS. Move items between status columns as you work; keep this file as the single source of truth for "what's next."

Status legend: `☐` To do · `🔄` In progress · `✅` Done

---

## Week 1 — Initiation & SRS

- ✅ Define scope, objectives, and user roles
- ✅ Rename project from DaycareOS to KiddieOps
- ✅ Restructure SRS with sequential REQ IDs (REQ01–REQ37, NFR01–NFR12, EI01–EI02) and MoSCoW priority
- ✅ Build requirement traceability matrix
- ✅ Create repo documentation: README.md, CONTRIBUTING.md, docs/architecture.md, docs/tasks.md

## Week 2 — Design & Planning

- ☐ Finalize database schema / ER diagram from `docs/architecture.md` §4
- ☐ Choose ORM (Prisma / Sequelize / raw `pg`)
- ☐ Wireframe: Login screen (REQ01)
- ☐ Wireframe: Admin Dashboard (REQ29)
- ☐ Wireframe: Caregiver Dashboard (REQ28)
- ☐ Wireframe: Parent Dashboard (REQ27)
- ☐ Wireframe: AI Guardian chat UI (EI02)
- ☐ Set up GitHub repo structure (`backend/`, `frontend/`, `docs/`) per README
- ☐ Set up task board (GitHub Projects or equivalent) mirroring this file
- ☐ Decide hosting target (see architecture.md open questions)

## Week 3–4 — Development Sprint 1: Core Modules

**Goal: authentication, navigation, and core CRUD (children, caregivers, classrooms).**

- ☐ Backend: project scaffold (Express, PostgreSQL connection, env config)
- ☐ Backend: `users` table + auth endpoints (REQ01, REQ02)
- ☐ Backend: JWT auth middleware + role-based access middleware (REQ03, NFR04, NFR05)
- ☐ Backend: password hashing with bcrypt (NFR06)
- ☐ Backend: user management endpoints — add/update/deactivate/assign role (REQ04–REQ07)
- ☐ Backend: child management endpoints (REQ08–REQ10)
- ☐ Backend: caregiver management endpoints (REQ11, REQ12)
- ☐ Backend: classroom/group management endpoints (REQ13, REQ14)
- ☐ Frontend: scaffold (React, routing, auth context)
- ☐ Frontend: Login page (REQ01)
- ☐ Frontend: role-based route guarding (REQ03)
- ☐ Frontend: Admin — user/child/caregiver/classroom management screens (REQ04–REQ14)
- ☐ Input validation on all new endpoints (NFR08)
- ☐ Unit tests for auth + core CRUD
- ☐ PR review pass on all Sprint 1 branches

## Week 5–6 — Development Sprint 2: Daily Operations

**Goal: attendance, activity logging, medical records, notices, dashboards.**

- ☐ Backend: attendance endpoints — check-in/check-out, status (REQ15–REQ17)
- ☐ Backend: daily activity log endpoints (REQ18–REQ20)
- ☐ Backend: medical records endpoints + read/write permission checks (REQ21, REQ22)
- ☐ Backend: medical record audit logging (REQ23)
- ☐ Backend: medical alert flag logic (REQ24)
- ☐ Backend: notice endpoints (REQ25, REQ26)
- ☐ Frontend: Caregiver — attendance screen (REQ15)
- ☐ Frontend: Caregiver — daily activity logging form (REQ18)
- ☐ Frontend: Medical records screen — write view (staff) and read-only view (parent) (REQ21, REQ22)
- ☐ Frontend: Notice board — publish (staff) and view (parent) (REQ25, REQ26)
- ☐ Frontend: Parent Dashboard — pull together child profile, attendance status, recent logs, medical alerts, notices (REQ27)
- ☐ Frontend: Caregiver Dashboard — assigned classroom, child list, quick links (REQ28)
- ☐ Frontend: Admin Dashboard — management shortcuts + basic reports (REQ29)
- ☐ Encrypt medical data at rest (NFR07)
- ☐ Unit/integration tests for attendance, logging, medical records permission boundaries
- ☐ PR review pass on all Sprint 2 branches

## Week 7–8 — Development Sprint 3: AI Guardian Assistant

**Goal: AI Guardian chat feature end-to-end.**

- ☐ Backend: `ai_guardian_sessions` table + endpoint
- ☐ Backend: data-gathering layer — pull scoped attendance/logs/milestones/medical data for a child (REQ31)
- ☐ Backend: Claude API integration — send question + scoped context, return synthesized answer (REQ30, REQ31)
- ☐ Backend: session/follow-up context handling (REQ32)
- ☐ Backend: enforce per-guardian child data isolation on every AI Guardian call (REQ36)
- ☐ Backend: encrypt AI Guardian data in transit/at rest + log queries & responses (REQ37)
- ☐ Backend: comparative query support — time-period comparisons (REQ33)
- ☐ Backend (stretch): predictive scheduling suggestions (REQ34, Could-Have)
- ☐ Backend: Bangla/English response handling (REQ35)
- ☐ Frontend: AI Guardian chat UI — child selector, message area, input, send, quick-query buttons (EI02)
- ☐ Frontend: multi-child selector for guardians with more than one child
- ☐ Manual QA: verify a parent cannot retrieve another child's data via the AI Guardian under any phrasing
- ☐ PR review pass on all Sprint 3 branches

## Week 9+ — Hardening & Demo Prep

- ☐ Cross-browser check: Chrome, Edge, Firefox (NFR10)
- ☐ Responsive/mobile pass across all screens, prioritizing parent-facing views (NFR11)
- ☐ Security review: RBAC boundaries, medical record access, AI Guardian isolation (NFR04, NFR05, REQ36)
- ☐ Performance check on core flows — login, attendance view, log view (NFR02)
- ☐ Seed demo data (sample children, caregivers, a few days of logs) for presentation
- ☐ Final walkthrough against Section 10 (Acceptance Criteria) of the SRS
- ☐ Prepare demo script / presentation

---

## Future / Backlog (beyond v1.0)

Ideas raised during development that are out of scope for the course deadline — capture here instead of building now (see CONTRIBUTING.md §"Working with the SRS").

- ☐ Native mobile app (v1.0 is responsive web only — see SRS Constraint #5)
- ☐ SMS/push notifications for notices
- ☐ Photo/video sharing in daily activity logs
- ☐ Multi-branch daycare center support
