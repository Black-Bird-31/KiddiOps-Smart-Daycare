# KiddiOps

### Smart Daycare Management and AI Guardian Platform

KiddiOps is a web-based, mobile-responsive daycare management platform designed for daycare centers and childcare facilities in Bangladesh.

The platform provides essential daycare management features for administrators, caregivers, and parents/guardians, while its main intelligent feature — the **AI Guardian Assistant** — allows parents to ask natural-language questions about their child's routine, health, and development.

> **Course Project — Web Programming and Mobile Application Development, Department of CSE**
> **Status:** Week 1 — Initiation & SRS

---

## Why KiddiOps?

Daycare staff often need to manage attendance, daily activities, meals, naps, medical information, and notices, while parents want meaningful information about their child's day without manually going through multiple records.

KiddiOps brings these activities into one platform.

The system combines conventional daycare management with an AI-powered Guardian Assistant that synthesizes a child's authorized records and provides contextual answers instead of simply displaying raw activity logs.

The project is intentionally scoped around a practical set of features that can be implemented within the available development period.

---

## Core Features

* **Role-based authentication** — Separate access for administrators, caregivers, and parents/guardians.
* **Child management** — Manage child profiles, guardians, classrooms, emergency contacts, and allergy information.
* **Caregiver management** — Manage caregivers and their classroom/group assignments.
* **Classroom/group management** — Create groups and assign children and caregivers.
* **Attendance management** — Record check-in, check-out, and attendance status.
* **Daily activity logging** — Record meals, naps, diaper changes, learning/play activities, mood, and notes.
* **Medical records** — Securely manage allergies, conditions, medications, immunizations, incidents, and special care information.
* **Notice management** — Publish daycare announcements, events, reminders, and policy updates.
* **Parent dashboard** — Provide parents with a consolidated view of their child's information.
* **Caregiver dashboard** — Provide quick access to assigned children and daily care tasks.
* **Administrator dashboard** — Provide management and operational oversight.
* **AI Guardian Assistant** — Answer contextual questions about a parent's authorized child.
* **Bangla & English AI interaction** — Support the AI Guardian experience in both languages.

---

## AI Guardian Assistant

The AI Guardian Assistant is the primary intelligent feature of KiddiOps.

Instead of requiring parents to browse through raw records of meals, naps, attendance, and other activities, the assistant uses the child's authorized data to generate contextual responses.

### Example Questions

**Routine Synthesis**

> "How long did she sleep today compared to her average this week?"

**Health & Nutrition Correlation**

> "He seems cranky; did he eat less solid food or skip a nap today?"

**Milestone Progress**

> "What words did the teacher notice him saying during playtime this month?"

**Routine-Based Planning**

> "Based on her nap times this week, what is the best window for a grocery run tonight?"

The assistant should use the individual child's historical information when making comparisons rather than relying only on general averages.

---

## AI Guardian Conversation

KiddiOps supports contextual follow-up questions within an active AI Guardian session.

Example:

```text
Parent:
Did he nap well today?

AI Guardian:
He napped for 1 hour 40 minutes today, slightly less than
his weekly average of 2 hours.

Parent:
Give me his meal details for today too.

AI Guardian:
...
```

The assistant should understand that the parent is still referring to the same child and relevant time context.

---

## User Roles

### Administrator

Administrators manage the daycare's overall information.

Responsibilities include:

* User management
* Child management
* Caregiver management
* Classroom/group management
* Medical record oversight
* Notice publishing
* Basic operational reports and summaries

### Caregiver / Teacher

Caregivers manage the daily care of children.

They can:

* View assigned classrooms/groups
* View assigned children
* Take attendance
* Log daily activities
* Record medical notes/incidents when authorized
* View relevant notices

### Parent / Guardian

Parents can:

* View their child's profile
* View attendance history
* View daily activity logs
* View medical records
* View notices
* Use the AI Guardian Assistant

---

## Main System Modules

```text
KiddiOps
│
├── Authentication & Authorization
├── User Management
├── Child Management
├── Caregiver Management
├── Classroom / Group Management
├── Attendance Management
├── Daily Activity Logging
├── Medical Records
├── Notice Management
├── Administrator Dashboard
├── Caregiver Dashboard
├── Parent Dashboard
└── AI Guardian Assistant
```

---

## Security & Privacy

KiddiOps handles sensitive information related to children, including medical records.

The system is designed around:

* Authentication
* Role-based access control
* Protected passwords
* Restricted child information
* Secure medical records
* Input validation
* Encryption of sensitive data
* Medical record access/modification logging
* AI Guardian query/response auditing
* Strict isolation of each parent's AI session
* Prevention of cross-child information exposure

The AI Guardian must only work with information that the authenticated parent is authorized to access.

---

## AI Data Isolation

The intended AI data flow is:

```text
Parent
   │
   ▼
Authentication
   │
   ▼
Identify Authorized Child
   │
   ▼
Retrieve Relevant Child Data
   │
   ├── Attendance
   ├── Daily Activities
   ├── Milestone / Development Notes
   └── Medical Information
   │
   ▼
AI Guardian
   │
   ▼
Contextual Response
```

The AI system must never have unrestricted access to the entire daycare database.

---

## Technology Stack

> Technologies will be finalized during the design and planning phase.

| Layer          | Technology |
| -------------- | ---------- |
| Frontend       | TBD        |
| Backend        | TBD        |
| Database       | TBD        |
| Authentication | TBD        |
| AI Service/API | TBD        |
| Deployment     | TBD        |

---

## Project Structure

```text
kiddiops/
├── backend/              # Backend API and server-side logic
├── frontend/             # Responsive web application
├── docs/                 # SRS and technical documentation
│   ├── KiddiOps_SRS_v1.0.docx
│   ├── architecture.md
│   ├── api-contract.md
│   ├── database-schema.md
│   └── tasks.md
├── tests/                # Test cases and automated tests
├── .gitignore
├── CONTRIBUTING.md
├── README.md
└── LICENSE
```

---

## Getting Started

> Setup instructions will be finalized after the technology stack is selected.

Clone the repository:

```bash
git clone <repository-url>
cd kiddiops
```

Install dependencies and configure environment variables according to the frontend and backend setup.

Do **not** commit API keys, passwords, database credentials, or `.env` files.

---

## Development Roadmap

### Week 1 — Initiation & SRS

* Define project scope
* Define objectives and user roles
* Finalize SRS
* Set up GitHub repository
* Define contribution rules
* Prepare initial task backlog

### Week 2 — Design & Planning

* UI wireframes
* System architecture
* Database/ER design
* API planning
* GitHub Project board
* AI Guardian architecture planning

### Development Sprint 1

* Authentication
* Role-based navigation
* Basic dashboards
* Core UI components
* Database foundation

### Development Sprint 2

* Child management
* Caregiver management
* Classroom/group management
* CRUD operations
* Attendance
* Daily activity logging

### Development Sprint 3

* Medical records
* Notices
* Parent dashboard
* Caregiver dashboard
* Administrator dashboard

### Development Sprint 4

* AI Guardian Assistant
* Contextual data retrieval
* Follow-up conversation
* Bangla/English support
* Security and data isolation

### Final Phase

* Integration testing
* Security testing
* UI refinement
* Documentation
* Final demonstration

---

## Project Scope

### In Scope

* Authentication
* Role-based access
* User management
* Child management
* Caregiver management
* Classroom/group management
* Attendance
* Daily activity logging
* Medical records
* Notice management
* Parent dashboard
* Caregiver dashboard
* Administrator dashboard
* AI Guardian Assistant
* Basic Bangla and English AI support

### Out of Scope for Version 1

Advanced daycare management and advanced AI functionality are intentionally excluded from the initial release to keep the project achievable within the available development period.

---

## Project Constraints

* Approximately three months of development time
* Responsive web application as the initial platform
* AI Guardian may depend on an external AI service/API
* Sensitive child and medical information requires appropriate protection
* Initial AI Guardian functionality will support a limited set of query types

---

## Documentation

The complete functional requirements are maintained in the Software Requirements Specification:

```text
docs/KiddiOps_SRS_v1.0.docx
```

Additional technical documentation will be added during development:

* `architecture.md`
* `api-contract.md`
* `database-schema.md`
* `tasks.md`

---

## Team

| Member                  | Responsibility |
| ----------------------  | -------------- |
| Md. Habibur Rahman      | TBD            |
| Radhika Chowdhury       | TBD            |

---

## Contributing

Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) before creating branches, commits, or pull requests.

---

## Project Status

🚧 **In Development**

KiddiOps is being developed as an academic Web Programming and Mobile Application Development project.

---

## License

TBD — This is currently an academic course project.
