KiddieOps: Smart Daycare Management and AI Guardian Platform
Version: 1.0
Project Type: Web Application (mobile-responsive)
Target Context: Daycare centers and childcare facilities in Bangladesh

1. Introduction
1.1 Purpose
This Software Requirements Specification (SRS) defines the requirements of DaycareOS, a web-based Smart Daycare Management and AI Guardian Platform.
DaycareOS is designed to provide basic daycare management features for administrators, caregivers, and parents/guardians. The system will also provide an AI Guardian Assistant that answers parents' specific questions about their child by synthesizing daily logs, historical trends, developmental milestones, and medical records — instead of requiring guardians to scroll through raw timelines of meals, naps, and diaper changes.
The purpose of this document is to clearly describe what the system will provide and what users will be able to do.
2. Project Overview
2.1 Project Name
DaycareOS
Full Name: Smart Daycare Management and AI Guardian Platform
2.2 Project Vision
DaycareOS aims to make day-to-day daycare operations easier for staff while giving parents real-time, meaningful insight into their child's day through a conversational AI Guardian Assistant, instead of forcing them to piece together information from raw activity timelines.
The system will focus on a simple, easy-to-use web interface and a limited set of important features that can realistically be developed within the project timeline.
3. Objectives
The main objectives of DaycareOS are:
1.	To provide a simple platform for basic daycare management.
2.	To allow caregivers to log daily activities such as meals, naps, and diaper changes.
3.	To allow authorized staff to record and maintain each child's medical information.
4.	To allow parents to monitor their child's routine, health, and development in real time.
5.	To provide an AI Guardian Assistant that answers parents' questions through natural conversation.
6.	To support contextual queries that synthesize logs, trends, and milestones rather than raw timelines.
7.	To support Bangla and English for the AI Guardian experience.
8.	To develop a practical, secure system suitable for daycare centers in Bangladesh.
4. Scope of the System
DaycareOS will be developed as a web application with three main user roles:
•	Administrator
•	Caregiver (Teacher)
•	Parent/Guardian
The system will mainly include:
•	Login and authentication
•	User management
•	Child management
•	Classroom/group management
•	Attendance (check-in/check-out) management
•	Daily activity logging
•	Medical records management
•	Notice management
•	Parent dashboard
•	AI Guardian Assistant
The first version will focus only on these core features.
5. Users of the System
5.1 Administrator
The administrator manages the basic information of the daycare center.
The administrator can:
•	Manage children
•	Manage caregivers
•	Manage classrooms/groups
•	Manage users
•	Publish notices
•	Oversee medical records
5.2 Caregiver (Teacher)
Caregivers manage the daily care activities of children.
Caregivers can:
•	View assigned classrooms/groups
•	View children
•	Take attendance (check-in/check-out)
•	Log daily activities (meals, naps, diaper changes)
•	Record medical notes and incidents (if authorized)
•	View relevant notices
5.3 Parent/Guardian
Parents/guardians can:
•	View their child's profile
•	View attendance and check-in/check-out history
•	View daily activity logs
•	View their child's medical records
•	View notices
•	Use the AI Guardian Assistant
6. Functional Requirements
6.1 Authentication
The system shall provide a login system for registered users.
The system shall identify the user's role after login.
Users shall only be able to access features permitted for their role.
6.2 User Management
The administrator shall be able to:
•	Add users
•	Update user information
•	Remove/deactivate users
•	Assign user roles
6.3 Child Management
The administrator shall be able to manage basic child information.
Child information may include:
•	Child ID
•	Name
•	Date of birth
•	Classroom/group
•	Guardian information
•	Contact information
•	Known allergies (summary flag)
•	Emergency contact
Parents shall be able to view their own child's profile.
6.4 Caregiver Management
The administrator shall be able to manage caregiver information.
Caregiver information may include:
•	Caregiver ID
•	Name
•	Contact information
•	Assigned classroom/group
•	Assigned children
6.5 Classroom/Group Management
The administrator shall be able to:
•	Create classrooms/groups
•	Update classrooms/groups
•	Assign children to a classroom/group
•	Assign caregivers to a classroom/group
7. Attendance Management
Caregivers shall be able to take child attendance through check-in and check-out.
The caregiver shall:
1.	Select a classroom/group.
2.	Select a date.
3.	View the child list.
4.	Record check-in time, check-out time, and present/absent status.
5.	Save the attendance.
Parents shall be able to view their child's attendance and check-in/check-out history.
The system may display a monthly attendance summary.
8. Daily Activity Logging
Caregivers shall be able to log daily activities for each child.
A daily log entry shall contain:
•	Child
•	Date/time
•	Activity type (meal, nap, diaper change, learning/play activity, mood)
•	Details/notes
•	Caregiver who logged the entry
Parents shall be able to view daily activity logs for their child.
The system may calculate daily summaries such as total nap time and meals recorded.
9. Medical Records Management
9.1 Overview
The system shall allow authorized caregivers and administrators to record and maintain each child's medical information securely.
9.2 Medical Record Contents
A child's medical record may include:
•	Allergies
•	Chronic conditions
•	Current medications and dosage instructions
•	Immunization records
•	Emergency medical contact/physician information
•	Incident reports (injuries or illness episodes at the daycare)
•	Special care instructions
9.3 Access and Permissions
Only administrators and authorized caregivers shall be able to add or update medical records.
Parents shall be able to view — but not edit — their own child's medical records.
The system shall log every access to and modification of medical records for accountability.
9.4 Medical Alerts
The system may flag critical medical information, such as a severe allergy, to caregivers when a child's profile is viewed.
10. Notice Management
Administrators and authorized caregivers shall be able to publish notices.
A notice shall contain:
•	Title
•	Description
•	Date
•	Author
Parents shall be able to view relevant notices.
Examples include:
•	Holiday and closure announcements
•	Fee reminders
•	Daycare events
•	Policy updates
11. Parent Dashboard
After login, parents shall have access to a simple dashboard.
The dashboard may display:
•	Child profile
•	Today's attendance/check-in status
•	Recent activity logs
•	Medical alerts/records summary
•	Recent notices
•	AI Guardian Assistant
12. Caregiver Dashboard
The caregiver dashboard shall provide access to:
•	Assigned classroom/group
•	Child list
•	Attendance
•	Daily activity logging
•	Medical records (view/add, per permission)
•	Notices
The dashboard should allow caregivers to access common tasks easily.
13. Administrator Dashboard
The administrator dashboard shall display basic operational information.
It may include:
•	User management
•	Child and caregiver management
•	Classroom/group management
•	Medical records oversight
•	Notices
•	Basic reports and summaries
14. AI Guardian Assistant
14.1 Overview
The AI Guardian Assistant is the main personalized-insight feature of DaycareOS.
It functions as a secure, real-time data synthesis engine that answers parents' specific questions by analyzing a child's daily logs, historical trends, and developmental milestones. Instead of forcing a guardian to scroll through endless timelines of diaper changes, naps, and meals, the AI provides instant, contextual insights through a conversational interface.
14.2 Contextual Query Categories
The AI Guardian Assistant shall support at least the following categories of contextual queries:
Routine Synthesis: "How long did she sleep today compared to her average this week?"
Health & Nutrition Correlation: "He seems cranky; did he eat less solid food or skip a nap today?"
Milestone Progress: "What words did the teacher notice him saying during playtime this month?"
Predictive Planning: "Based on her nap times this week, what is the best window for a grocery run tonight?"
14.3 AI Guardian Features
Parents shall be able to:
•	Ask free-form questions about their child in natural language
•	Receive answers synthesized from attendance, daily logs, milestone notes, and medical records
•	Ask follow-up questions within the same conversation
•	Request comparisons across time periods (today vs. this week, this week vs. last month)
•	Receive predictive scheduling suggestions based on the child's routine patterns
•	Ask questions in Bangla or English
14.4 Example Interaction
Parent: How long did she sleep today compared to her average this week?
AI Guardian Assistant: She napped for 1 hour 20 minutes today, about 30 minutes less than her weekly average of 1 hour 50 minutes.
The parent can then ask a follow-up without repeating context:
Parent: Could that be why she seems cranky this evening?
AI Guardian Assistant: It's possible — shorter naps this week have coincided with lower afternoon mood ratings in her daily logs.
14.5 Personalization
The AI Guardian Assistant should consider the individual child's own historical data — not general averages — when generating comparisons, so that insights reflect that specific child's routine and developmental stage.
14.6 Data Privacy and Security for the AI Guardian
Because the AI Guardian Assistant synthesizes sensitive information, including medical records, the system shall:
•	Restrict each parent's AI Guardian session strictly to their own child's data
•	Encrypt data in transit and at rest
•	Log AI Guardian queries and responses for audit purposes
•	Never expose one child's information to another guardian
15. AI Guardian Session
The system may maintain the current AI Guardian conversation during a session, allowing parents to ask follow-up questions without repeating the topic.
For example:
Parent: Did he nap well today?
AI Guardian Assistant: He napped for 1 hour 40 minutes today, slightly less than his weekly average of 2 hours.
Parent: Give me his meal details for today too.
The AI should understand that the parent is still asking about "today" for the same child, and return the relevant meal log without requiring the date or child to be re-specified.
16. Non-Functional Requirements
16.1 Usability
The system should be simple and easy to use.
Users should be able to access common features with minimal navigation.
16.2 Performance
Normal system operations such as login, viewing attendance, and viewing daily logs should respond within a reasonable time under normal usage.
AI Guardian response time may depend on the AI service.
16.3 Security
The system shall:
•	Require authentication.
•	Use role-based access.
•	Protect user passwords.
•	Encrypt medical and other sensitive child data at rest.
•	Prevent unauthorized access to child, attendance, and medical information.
•	Validate user input.
16.4 Reliability
The system should reliably store important information such as:
•	Child data
•	Attendance records
•	Daily activity logs
•	Medical records
•	User accounts
16.5 Compatibility
The web application should work on modern browsers such as:
•	Google Chrome
•	Microsoft Edge
•	Mozilla Firefox
The interface should be responsive for desktop and mobile screens, with priority given to mobile usability for parents.
17. External Interface Requirements
17.1 User Interface
The system should contain simple interfaces for:
•	Login
•	Dashboards
•	Child management
•	Caregiver management
•	Attendance
•	Daily activity logs
•	Medical records
•	Notices
•	AI Guardian Assistant
17.2 AI Guardian Interface
The AI Guardian Assistant shall use a simple chat-based interface.
It should contain:
•	Child selector (for guardians with more than one child)
•	Chat/message area
•	Text input
•	Send button
•	Suggested quick-query buttons (e.g., "How did today go?")
18. Basic Data Requirements
The system will store the following basic information.
User
User ID
Name
Email/username
Password
Role

Child
Child ID
Name
Date of birth
Classroom/group
Guardian(s)
Allergy flag
Emergency contact

Caregiver
Caregiver ID
Name
Contact information
Assigned classroom/group

Classroom/Group
Group ID
Group name
Age range

Attendance
Child
Date
Check-in time
Check-out time
Status

Daily Activity Log
Child
Date/time
Activity type
Details
Logged by

Medical Record
Child
Allergies
Conditions
Medications
Immunizations
Physician contact
Incident reports
Last updated by

Notice
Notice ID
Title
Description
Date

AI Guardian Session
Guardian
Child
Query
AI response
Timestamp

19. Basic Use Cases
UC-01: User Login
Actor: Administrator, Caregiver, Parent/Guardian
Flow:
1.	User opens the login page.
2.	User enters login credentials.
3.	System validates the credentials.
4.	System identifies the user's role.
5.	System opens the appropriate dashboard.
UC-02: Caregiver Takes Attendance
Actor: Caregiver
Flow:
1.	Caregiver logs in.
2.	Caregiver selects Attendance.
3.	Caregiver selects a classroom/group and date.
4.	System displays the child list.
5.	Caregiver records check-in/check-out and status for each child.
6.	Caregiver saves the attendance.
UC-03: Caregiver Logs a Daily Activity
Actor: Caregiver
Flow:
1.	Caregiver logs in.
2.	Caregiver selects a child.
3.	Caregiver selects an activity type (meal, nap, diaper change, activity).
4.	Caregiver enters details/notes.
5.	Caregiver saves the log entry.
UC-04: Authorized Staff Records Medical Information
Actor: Administrator, Authorized Caregiver
Flow:
1.	Staff member logs in.
2.	Staff member selects a child's medical record.
3.	Staff member adds or updates medical information (allergies, medications, immunizations, incidents).
4.	System records the change along with the staff member's identity and timestamp.
5.	System saves the updated medical record.
UC-05: Parent Uses the AI Guardian Assistant
Actor: Parent/Guardian
Flow:
1.	Parent logs in.
2.	Parent opens the AI Guardian Assistant.
3.	Parent selects their child (if more than one is linked to their account).
4.	Parent asks a question in natural language.
5.	System gathers relevant attendance, log, milestone, and medical data for that child.
6.	AI generates a synthesized, contextual response.
7.	Parent receives the response and may ask follow-up questions.
20. Assumptions
1.	Users have valid accounts.
2.	Users have internet access.
3.	Daycare information is entered correctly by authorized staff.
4.	Caregivers are responsible for entering accurate attendance and daily logs.
5.	Medical information is provided accurately by parents/guardians and kept current by authorized staff.
6.	The AI service is available when parents use the AI Guardian Assistant.
7.	The initial AI Guardian Assistant will support a limited set of query types.
21. Constraints
1.	The project has a limited development period of approximately three months.
2.	The first version will focus on essential daycare management features.
3.	The AI Guardian Assistant may depend on an external AI service/API.
4.	Medical record handling must follow applicable data protection practices for children's data.
5.	The system will initially be developed as a responsive web application.


22. Acceptance Criteria
The project will be considered successful if:
1.	Users can log in according to their roles.
2.	Administrators can manage users, children, caregivers, and classrooms/groups.
3.	Caregivers can take attendance and log daily activities.
4.	Authorized staff can record and update medical records, and parents can view them (read-only).
5.	Parents/guardians can view relevant information about their child.
6.	Users can view daycare notices.
7.	Parents can ask contextual questions to the AI Guardian Assistant and receive understandable, data-grounded answers.
8.	The system provides basic Bangla and English support for the AI Guardian feature.
9.	Unauthorized users cannot access restricted information, especially medical records.
10.	Each guardian's AI Guardian session is strictly isolated to their own child's data.
