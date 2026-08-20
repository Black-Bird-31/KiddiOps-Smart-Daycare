# KiddieOps

**Smart Daycare Management and AI Guardian Platform**

KiddieOps is a web-based, mobile-responsive daycare management platform built for daycare centers and childcare facilities in Bangladesh. It gives administrators and caregivers simple tools to run daily operations, and gives parents real-time, meaningful insight into their child's day through a conversational **AI Guardian Assistant** — instead of forcing them to scroll through raw timelines of meals, naps, and diaper changes.

> Course project — Web Programming and Mobile Application Development.
> Status: **Week 1 — Initiation & SRS**

---

## Why this project

Daycare centers in Bangladesh largely rely on paper logs or informal messaging groups to communicate a child's day to parents, which is easy to lose, hard to search, and gives no real sense of trends over time. Parents are left piecing together their child's routine, health, and development from scattered updates instead of getting a clear, synthesized picture.

KiddieOps is scoped around that gap: a simple, role-based daycare operations system, paired with an AI Guardian Assistant that can answer a parent's actual question — *"did she sleep less than usual today?"* — by reading across attendance, activity logs, and medical records for that specific child, rather than requiring the parent to dig through raw entries themselves.

## Core features

- **Role-based platform** — Administrator, Caregiver, and Parent/Guardian each get a dashboard scoped to what they're allowed to see and do
- **Attendance management** — daily check-in/check-out tracking per classroom/group, with history for parents
- **Daily activity logging** — meals, naps, diaper changes, play/learning activity, and mood, logged per child by caregivers
- **Medical records** — allergies, conditions, medications, immunizations, and incident reports, with strict read/write permissions and a full audit log
- **Notice board** — announcements from admins/caregivers to parents (closures, fee reminders, events, policy updates)
- **AI Guardian Assistant** — a chat-based assistant (powered by the Claude API) that answers parents' natural-language questions by synthesizing that child's own logs, trends, and milestones — supports Bangla and English, follow-up questions, and time-period comparisons
- **Data isolation by design** — every parent's session and AI Guardian queries are strictly scoped to their own child's data

See [`docs/KiddieOps_SRS.docx`](docs/KiddieOps_SRS.docx) for the full Software Requirements Specification, including requirement IDs (REQ01–REQ37, NFR01–NFR12, EI01–EI02), MoSCoW priorities, and a full traceability matrix.

## Tech stack

| Layer            | Technology                                                         |
| ---------------- | ------------------------------------------------------------------ |
| Frontend         | React, mobile-first responsive design                              |
| Backend          | Node.js, Express                                                   |
| Database         | MySQL                                                         |
| Auth             | JWT, bcrypt (password hashing)                                     |
| AI Guardian      | Claude API (Anthropic)                                             |
| Hosting (target) | TBD — see [`docs/architecture.md`](docs/architecture.md)           |

## Project structure

```
kiddieops/
├── backend/           # Express API, auth, business logic, DB access
├── frontend/          # React app (Admin, Caregiver, Parent views)
├── docs/
│   ├── KiddieOps_SRS.docx   # Software Requirements Specification
│   ├── architecture.md      # System architecture & data model
│   └── tasks.md             # Sprint backlog / task list
├── CONTRIBUTING.md
└── README.md
```

## Getting started

> Setup instructions below are the target flow once the codebase is scaffolded (Week 3–4). Update this section as soon as `backend/` and `frontend/` exist.

```bash
# Backend
cd backend
npm install
npm run dev          # starts API on localhost:5000 (adjust as needed)

# Frontend
cd frontend
npm install
npm start             # starts React dev server on localhost:3000
```

Environment variables (backend `.env`, not committed):

```
DATABASE_URL=postgresql://user:password@localhost:5432/kiddieops
JWT_SECRET=change-me
ANTHROPIC_API_KEY=your-claude-api-key
```

## User roles

| Role                | Can do |
| -------------------- | ------ |
| **Administrator**    | Manage users, children, caregivers, classrooms/groups; publish notices; oversee medical records |
| **Caregiver**        | Take attendance, log daily activities, record medical notes (if authorized), view assigned classroom/children |
| **Parent/Guardian**  | View their own child's profile, attendance, activity logs, medical records (read-only), notices, and use the AI Guardian Assistant |

## Team

| Member                 |
| ---------------------- |
| Md. Habibur Rahman     |
| Radhika Chowdhury      |

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for branch naming, commit conventions, and PR review rules.

## Roadmap

- [x] **Week 1 — Initiation & SRS**: scope/objectives/roles, SRS v2.0 with prioritized requirement IDs, repo + contribution guidelines, README + initial task list
- [ ] **Week 2 — Design & Planning**: UI wireframes, architecture documentation (ER diagram, data flow), task board
- [ ] **Week 3–4 — Development Sprint 1**: core modules (auth, navigation, child/caregiver/classroom CRUD), unit tests, PR-based peer review
- [ ] **Week 5–6 — Development Sprint 2**: attendance, daily activity logging, medical records, notices, dashboards
- [ ] **Week 7–8 — Development Sprint 3**: AI Guardian Assistant integration (Claude API), Bangla/English support
- [ ] **Week 9+ — Hardening & Demo Prep**: security review, responsive polish, final testing, presentation

## License

TBD (course project — a license needed before any public/production use).
