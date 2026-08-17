# KiddieOps

### Smart Daycare Management and AI Guardian Platform

KiddieOps is a web-based, mobile-responsive daycare management platform
designed for daycare centers and childcare facilities in Bangladesh. It
combines essential daycare management features with an **AI Guardian
Assistant** that helps parents understand their child's daily routine,
health, and development through natural-language questions.

> **Project Type:** Web Application (Mobile-Responsive)\
> **Version:** 1.0\
> **Target Context:** Daycare centers and childcare facilities in
> Bangladesh

------------------------------------------------------------------------

## Table of Contents

-   [Overview](#overview)
-   [Project Vision](#project-vision)
-   [Objectives](#objectives)
-   [Core Features](#core-features)
-   [User Roles](#user-roles)
-   [AI Guardian Assistant](#ai-guardian-assistant)
-   [System Modules](#system-modules)
-   [Functional Requirements](#functional-requirements)
-   [Dashboards](#dashboards)
-   [Data Model](#data-model)
-   [Security and Privacy](#security-and-privacy)
-   [Non-Functional Requirements](#non-functional-requirements)
-   [Technology Stack](#technology-stack)
-   [Project Structure](#project-structure)
-   [Installation and Setup](#installation-and-setup)
-   [Typical Workflows](#typical-workflows)
-   [Project Scope and Constraints](#project-scope-and-constraints)
-   [Acceptance Criteria](#acceptance-criteria)
-   [Future Improvements](#future-improvements)
-   [Contributors](#contributors)
-   [License](#license)

------------------------------------------------------------------------

## Overview

KiddieOps provides a centralized platform for administrators,
caregivers, and parents/guardians.

The system allows authorized staff to manage children, caregivers,
classrooms, attendance, daily activities, medical information, and
notices. Parents can monitor their child's information through a
dedicated dashboard.

The main innovative component is the **AI Guardian Assistant**. Instead
of requiring parents to manually browse raw records such as meals, naps,
attendance, and activity logs, the assistant synthesizes relevant
information and provides contextual answers.

------------------------------------------------------------------------

## Project Vision

KiddieOps aims to make day-to-day daycare operations easier for staff
while giving parents meaningful, real-time insight into their child's
day.

The first version focuses on a limited set of practical features that
can realistically be developed within the project timeline.

The AI Guardian experience will support both **English and Bangla**.

------------------------------------------------------------------------

## Objectives

The main objectives of KiddieOps are:

1.  Provide a simple platform for basic daycare management.
2.  Allow caregivers to record daily activities such as meals, naps, and
    diaper changes.
3.  Allow authorized staff to maintain children's medical information.
4.  Allow parents to monitor their child's routine, health, and
    development.
5.  Provide an AI Guardian Assistant for natural-language questions.
6.  Support contextual queries that synthesize logs, trends, and
    milestones.
7.  Support Bangla and English for the AI Guardian experience.
8.  Develop a practical and secure system suitable for daycare centers
    in Bangladesh.

------------------------------------------------------------------------

## Core Features

### Authentication and Role-Based Access

-   User login and authentication
-   Automatic role identification
-   Role-based access control
-   Protected child and medical information

### User Management

Administrators can:

-   Add users
-   Update user information
-   Remove/deactivate users
-   Assign user roles

### Child Management

The system stores and manages:

-   Child ID
-   Name
-   Date of birth
-   Classroom/group
-   Guardian information
-   Contact information
-   Allergy flag
-   Emergency contact

### Caregiver Management

Administrators can manage:

-   Caregiver ID
-   Name
-   Contact information
-   Assigned classroom/group
-   Assigned children

### Classroom/Group Management

Administrators can:

-   Create classrooms/groups
-   Update classrooms/groups
-   Assign children
-   Assign caregivers

### Attendance Management

Caregivers can:

-   Select a classroom/group
-   Select a date
-   View the child list
-   Record check-in/check-out
-   Mark present/absent status
-   Save attendance records

Parents can view their child's attendance and check-in/check-out
history.

### Daily Activity Logging

Caregivers can record:

-   Meals
-   Nap/sleep
-   Diaper changes
-   Learning/play activities
-   Mood
-   Additional notes

Each activity record contains:

-   Child
-   Date/time
-   Activity type
-   Details/notes
-   Caregiver who logged the entry

### Medical Records

Authorized administrators and caregivers can manage:

-   Allergies
-   Chronic conditions
-   Current medications and dosage instructions
-   Immunization records
-   Emergency medical contact/physician information
-   Incident reports
-   Special care instructions

Parents can view their child's medical records but cannot edit them.

### Notice Management

Authorized staff can publish notices containing:

-   Title
-   Description
-   Date
-   Author

Examples include:

-   Holiday/closure announcements
-   Fee reminders
-   Daycare events
-   Policy updates

### Parent Dashboard

The parent dashboard may display:

-   Child profile
-   Today's attendance/check-in status
-   Recent activity logs
-   Medical alerts/record summary
-   Recent notices
-   AI Guardian Assistant

------------------------------------------------------------------------

# AI Guardian Assistant

The **AI Guardian Assistant** is the primary AI-powered feature of
KiddieOps.

It provides a conversational interface through which parents can ask
questions about their own child. The assistant uses relevant daycare
data to generate contextual responses instead of simply displaying raw
records.

## Supported Query Categories

### 1. Routine Synthesis

Example:

> "How long did she sleep today compared to her average this week?"

The assistant can compare today's nap duration with the child's
historical average.

### 2. Health and Nutrition Correlation

Example:

> "He seems cranky; did he eat less solid food or skip a nap today?"

The assistant can correlate relevant meal, nap, and mood records.

### 3. Milestone Progress

Example:

> "What words did the teacher notice him saying during playtime this
> month?"

The assistant can summarize relevant developmental or activity notes.

### 4. Predictive Planning

Example:

> "Based on her nap times this week, what is the best window for a
> grocery run tonight?"

The assistant can provide a scheduling suggestion based on the child's
recorded routine.

------------------------------------------------------------------------

## AI Guardian Capabilities

Parents can:

-   Ask free-form questions in natural language
-   Receive answers synthesized from their child's data
-   Ask follow-up questions
-   Compare different time periods
-   Receive routine-based scheduling suggestions
-   Ask questions in Bangla or English

The assistant should use the child's **own historical data** when
generating comparisons rather than relying only on general averages.

### Example Conversation

**Parent:**\
How long did she sleep today compared to her average this week?

**AI Guardian Assistant:**\
She napped for 1 hour 20 minutes today, about 30 minutes less than her
weekly average of 1 hour 50 minutes.

**Parent:**\
Could that be why she seems cranky this evening?

**AI Guardian Assistant:**\
It's possible --- shorter naps this week have coincided with lower
afternoon mood ratings in her daily logs.

------------------------------------------------------------------------

## AI Session Context

The system may maintain the current AI Guardian conversation during a
session.

For example:

**Parent:**\
Did he nap well today?

**AI:**\
He napped for 1 hour 40 minutes today, slightly less than his weekly
average of 2 hours.

**Parent:**\
Give me his meal details for today too.

The assistant should understand that the parent is still asking about
the same child and the same day without requiring the parent to repeat
the context.

------------------------------------------------------------------------

# System Modules

``` text
KiddieOps
│
├── Authentication
├── User Management
├── Child Management
├── Caregiver Management
├── Classroom/Group Management
├── Attendance Management
├── Daily Activity Logging
├── Medical Records
├── Notice Management
├── Parent Dashboard
├── Caregiver Dashboard
├── Administrator Dashboard
└── AI Guardian Assistant
```

------------------------------------------------------------------------

# User Roles

## Administrator

Administrators manage the overall daycare information.

They can:

-   Manage children
-   Manage caregivers
-   Manage classrooms/groups
-   Manage users
-   Publish notices
-   Oversee medical records
-   View basic operational reports and summaries

## Caregiver / Teacher

Caregivers manage daily childcare activities.

They can:

-   View assigned classrooms/groups
-   View assigned children
-   Take attendance
-   Log daily activities
-   Record medical notes/incidents when authorized
-   View relevant notices

## Parent / Guardian

Parents can:

-   View their child's profile
-   View attendance history
-   View daily activity logs
-   View medical records
-   View notices
-   Use the AI Guardian Assistant

------------------------------------------------------------------------

# Functional Requirements

## Authentication

-   Registered users must be able to log in.
-   The system identifies the user's role after login.
-   Users can only access features permitted for their role.

## User Management

Administrators can add, update, deactivate/remove users and assign
roles.

## Child Management

Administrators can create and manage child records.

Parents can view their own child's profile.

## Caregiver Management

Administrators can manage caregiver information and assignments.

## Classroom/Group Management

Administrators can create and update groups and assign children and
caregivers.

## Attendance

Caregivers can record check-in, check-out, and attendance status.

Parents can view their child's attendance history.

## Daily Activities

Caregivers can create activity logs for individual children.

Parents can view their child's activity history.

## Medical Records

Authorized administrators/caregivers can create and update medical
records.

Parents have read-only access to their child's medical records.

Medical record modifications should record the responsible staff member
and timestamp.

## Notices

Authorized staff can publish notices.

Parents can view relevant notices.

## AI Guardian

Parents can ask contextual questions about their own child and receive
data-grounded responses.

Each AI Guardian session must remain isolated to the parent's authorized
child data.

------------------------------------------------------------------------

# Dashboards

## Administrator Dashboard

The administrator dashboard provides access to:

-   User management
-   Child management
-   Caregiver management
-   Classroom/group management
-   Medical record oversight
-   Notices
-   Basic reports and summaries

## Caregiver Dashboard

The caregiver dashboard provides:

-   Assigned classroom/group
-   Child list
-   Attendance
-   Daily activity logging
-   Medical records according to permission
-   Notices

## Parent Dashboard

The parent dashboard provides:

-   Child information
-   Today's attendance
-   Recent activities
-   Medical information/alerts
-   Notices
-   AI Guardian Assistant

------------------------------------------------------------------------

# Data Model

The main entities are:

### User

-   User ID
-   Name
-   Email/username
-   Password
-   Role

### Child

-   Child ID
-   Name
-   Date of birth
-   Classroom/group
-   Guardian(s)
-   Allergy flag
-   Emergency contact

### Caregiver

-   Caregiver ID
-   Name
-   Contact information
-   Assigned classroom/group

### Classroom / Group

-   Group ID
-   Group name
-   Age range

### Attendance

-   Child
-   Date
-   Check-in time
-   Check-out time
-   Status

### Daily Activity Log

-   Child
-   Date/time
-   Activity type
-   Details
-   Logged by

### Medical Record

-   Child
-   Allergies
-   Conditions
-   Medications
-   Immunizations
-   Physician contact
-   Incident reports
-   Last updated by

### Notice

-   Notice ID
-   Title
-   Description
-   Date
-   Author

### AI Guardian Session

-   Guardian
-   Child
-   Query
-   AI response
-   Timestamp

------------------------------------------------------------------------

# Security and Privacy

KiddieOps handles sensitive information, particularly children's medical
records. Security and privacy are therefore core requirements.

The system should:

-   Require authentication
-   Implement role-based access control
-   Protect user passwords
-   Prevent unauthorized access to child information
-   Protect medical records
-   Encrypt sensitive data at rest
-   Encrypt data in transit
-   Validate user input
-   Log medical record access and modifications
-   Log AI Guardian queries and responses for auditing
-   Restrict every parent's AI session to their authorized child data
-   Never expose one child's information to another guardian

------------------------------------------------------------------------

# AI Data Isolation

The AI Guardian must never receive unrestricted access to the entire
daycare database.

The intended flow is:

``` text
Parent
  │
  ▼
Authentication
  │
  ▼
Identify Authorized Child
  │
  ▼
Retrieve Only Relevant Child Data
  │
  ├── Attendance
  ├── Daily Activities
  ├── Milestones / Notes
  └── Medical Information (as permitted)
  │
  ▼
AI Guardian
  │
  ▼
Contextual Response
```

This keeps the AI feature aligned with the project's privacy
requirements.

------------------------------------------------------------------------

# Non-Functional Requirements

## Usability

-   Simple and easy-to-use interface
-   Minimal navigation for common tasks
-   Mobile-friendly parent experience

## Performance

Normal operations such as login, attendance viewing, and activity-log
viewing should respond within a reasonable time under normal usage.

AI response time may depend on the external AI service.

## Reliability

The system should reliably store:

-   Child data
-   Attendance records
-   Daily activity logs
-   Medical records
-   User accounts

## Compatibility

The application should support modern browsers including:

-   Google Chrome
-   Microsoft Edge
-   Mozilla Firefox

The interface should be responsive for desktop and mobile screens.

------------------------------------------------------------------------

# AI Guardian Interface

The AI interface should contain:

-   Child selector (when applicable)
-   Chat/message area
-   Text input
-   Send button
-   Suggested quick-query buttons

Example quick queries:

-   "How did today go?"
-   "How long did my child sleep today?"
-   "What did my child eat today?"
-   "How was my child's attendance this week?"

------------------------------------------------------------------------

# Technology Stack

The SRS defines KiddieOps as a responsive web application but does not
prescribe a specific programming language, framework, database, or AI
provider.

The final implementation stack can therefore be selected according to
the team's development requirements.

### Planned Stack

> Update this section when the development team finalizes the
> technologies.

**Frontend:** `TBD`\
**Backend:** `TBD`\
**Database:** `TBD`\
**AI Service/API:** `TBD`\
**Authentication:** `TBD`\
**Deployment:** `TBD`

------------------------------------------------------------------------

# Project Structure

A suggested repository structure:

``` text
KiddieOps/
│
├── frontend/
│
├── backend/
│
├── docs/
│   └── KiddieOps_SRS.docx
│
├── database/
│
├── tests/
│
├── .gitignore
├── README.md
└── LICENSE
```

The actual structure may change according to the selected technology
stack.

------------------------------------------------------------------------

# Installation and Setup

> **Note:** Installation instructions will be updated after the
> technology stack is finalized.

General setup:

``` bash
# Clone the repository
git clone <repository-url>

# Enter the project directory
cd KiddieOps
```

Then configure the frontend, backend, database, environment variables,
and AI service according to the project's implementation.

------------------------------------------------------------------------

# Typical Workflows

## User Login

``` text
Open Login
    ↓
Enter Credentials
    ↓
Validate Credentials
    ↓
Identify User Role
    ↓
Open Appropriate Dashboard
```

## Caregiver Attendance

``` text
Caregiver Login
    ↓
Select Attendance
    ↓
Select Classroom and Date
    ↓
View Children
    ↓
Record Attendance
    ↓
Save
```

## Daily Activity Logging

``` text
Caregiver Login
    ↓
Select Child
    ↓
Select Activity Type
    ↓
Enter Details
    ↓
Save Activity
```

## Medical Record Update

``` text
Authorized Staff Login
    ↓
Open Child Medical Record
    ↓
Add / Update Information
    ↓
Record Staff Identity + Timestamp
    ↓
Save
```

## Parent Uses AI Guardian

``` text
Parent Login
    ↓
Open AI Guardian
    ↓
Select Child
    ↓
Ask Question
    ↓
Retrieve Authorized Child Data
    ↓
Generate Contextual Response
    ↓
Parent Can Ask Follow-up
```

------------------------------------------------------------------------

# Project Scope and Constraints

The initial version is intentionally limited to essential daycare
management and AI functionality.

### In Scope

-   Authentication
-   Role-based access
-   User management
-   Child management
-   Caregiver management
-   Classroom/group management
-   Attendance
-   Daily activity logs
-   Medical records
-   Notices
-   Parent dashboard
-   Caregiver dashboard
-   Administrator dashboard
-   AI Guardian Assistant
-   Basic Bangla and English AI support

### Constraints

1.  The project has an approximately three-month development period.
2.  The first version focuses on essential daycare management features.
3.  The AI Guardian may depend on an external AI service/API.
4.  Medical record handling must follow applicable data-protection
    practices for children's data.
5.  The initial version is a responsive web application.
6.  The AI Guardian will initially support a limited set of query types.

------------------------------------------------------------------------

# Assumptions

The project assumes that:

-   Users have valid accounts.
-   Users have internet access.
-   Daycare information is entered correctly by authorized staff.
-   Caregivers enter accurate attendance and daily activity information.
-   Medical information is provided accurately and kept current.
-   The AI service is available when the AI Guardian is used.
-   The initial AI Guardian supports a limited set of query types.

------------------------------------------------------------------------

# Acceptance Criteria

KiddieOps will be considered successful when:

-   [ ] Users can log in according to their roles.
-   [ ] Administrators can manage users, children, caregivers, and
    classrooms/groups.
-   [ ] Caregivers can take attendance.
-   [ ] Caregivers can log daily activities.
-   [ ] Authorized staff can record and update medical records.
-   [ ] Parents can view their child's medical records in read-only
    mode.
-   [ ] Parents can view relevant information about their child.
-   [ ] Users can view daycare notices.
-   [ ] Parents can ask contextual questions through the AI Guardian
    Assistant.
-   [ ] AI responses are understandable and grounded in the child's
    available data.
-   [ ] The AI Guardian supports basic Bangla and English interaction.
-   [ ] Unauthorized users cannot access restricted information.
-   [ ] Each guardian's AI session is isolated to their authorized
    child's data.

------------------------------------------------------------------------

# Future Improvements

Advanced features are intentionally outside the first version. Possible
future extensions include:

-   Native Android/iOS applications
-   Advanced analytics
-   More sophisticated predictive features
-   Automated notifications
-   Expanded AI capabilities
-   Additional daycare operational modules
-   More extensive multilingual support

These are **future possibilities**, not requirements for the initial
version.

------------------------------------------------------------------------

# Development Philosophy

KiddieOps is designed around three principles:

### Simple

The system should remain easy to use for administrators, caregivers, and
parents.

### Secure

Children's personal and medical information must be protected through
authentication, authorization, and data isolation.

### Practical

The first release should prioritize features that can realistically be
implemented and demonstrated within the project's development period.

------------------------------------------------------------------------

# Contributors

  Name   Role
  ------ -----------
  TBD    Developer
  TBD    Developer
  TBD    Developer

Update this section with the project team's names and responsibilities.

------------------------------------------------------------------------

# License

License information will be added by the development team.

------------------------------------------------------------------------

## Project Status

**Status:** 🚧 In Development

KiddieOps is currently under active development as an academic
Web/Mobile App Development project.
