# Project Requirements Document

<!-- markdownlint-configure-file
{
    "MD013": { "tables": false }
}
-->

## 1. Project Title

Hospital Employee Roster (Healthcare Scheduling Automation)

## 2. Team Members

- **Abdurrahman Farzat**
  - Role: Developer
- **Ayden Fritz**
  - Role: Project Manager
- **Paul Daley**
  - Role: Tester
- **Rio Dye**
  - Role: Business Analyst
- **Sam Buckland**
  - Role: UX/UI Designer

## 3. Project Summary

The Hospital Employee Roster system is an automated web application that
streamlines monthly shift scheduling for hospital emergency departments. By
evaluating physician profile constraints, custom shift preferences, and
validated vacation logs against strict department coverage requirements, the
backend logic instantly builds conflict-free rosters. The primary value of this
system is to replace time-consuming manual calendar workflows with an efficient
process that eliminates scheduling overlaps, reduces administrative labor
hours, ensures fair weekend distribution, and guarantees consistent 24/7
patient care staffing coverage.

## 4. User Personas

### Persona 1: The Administrative Scheduler

- **Name:** Andrew Mooney
- **Role / Context:** Hospital Emergency Department Manager
- **Goals:** Generate error-free, complete monthly shift schedules in under
  five minutes; eliminate manual spreadsheet conflict-checking.
- **Frustrations:** Balancing overlapping doctor vacation requests; accidental
  scheduling gaps or assigning staff to back-to-back shifts.
- **Technology Comfort Level:** Moderate. Comfortable with core office
  spreadsheets but struggles with overly complex database setups.

### Persona 2: The Emergency Room Physician

- **Name:** Dr. Sarah Jenkins
- **Role / Context:** Full-Time Attending ER Physician
- **Goals:** Securely log into a web dashboard to check shifts; submit vacation
  blocks and preference settings with immediate tracking feedback.
- **Frustrations:** Receiving monthly schedules late; getting stuck with
  consecutive night-then-morning shift rotations; verbal time-off requests
  being overlooked.
- **Technology Comfort Level:** Moderate to High. Navigates mobile applications
  and medical records systems daily.

### Persona 3: IT Administrator

- **Name:** Jacob Kim
- **Role / Context:** The Hospital's IT Administrator
- **Goals:** Keep the IT systems up-to-date and secure from hacking; keep
  systems well integrated and auditable; keep doctors' and patients'
  information private; keep systems up and running.
- **Frustrations:** Unreliable apps that are difficult to deploy and keep
  crashing; dependencies that are difficult to audit and maintain; accounts
  scattered all over the place (no SSO).
- **Technology Comfort Level:** Very High. Can manage Windows and Linux servers
  and host containarized apps.

## 5. User Stories

| **ID** | **User Story** | **Priority** |
| :--: | :--- | :--: |
| **US-01** | As an ED Manager, I want to create and update doctor profiles so that active employee status and contact data stay accurate. | High |
| **US-02** | As an ER Doctor, I want to log in securely so that I can access my private scheduling dashboard safely. | High |
| **US-03** | As an ER Doctor, I want to submit my preferred work shifts (Day, Evening, Night) so that the engine tracks my preferences. | Medium |
| **US-04** | As an ER Doctor, I want to log digital vacation requests so that the automated scheduler excludes me from rotations on those dates. | High |
| **US-05** | As an ED Manager, I want to trigger the automated roster generator so that a complete monthly calendar is built with no manual overlaps. | High |
| **US-06** | As an ER Doctor, I want to view my personalized schedule in a calendar display so that I can check my upcoming shift times easily. | High |
| **US-07** | As an ER Doctor, I want to print out the monthly shift roster view so that I can keep an offline paper record of my schedule. | Low |
| **US-08** | As an ED Manager, I want the system to flag any conflict that schedules a doctor for multiple shifts in a 24-hour window to protect staff from burnout. | High |
| **US-09** | As an ED Manager, I want the scheduling engine to ensure every doctor gets at least one full weekend off monthly for fair shift distribution. | Medium |

## 6. Functional Requirements (What the system must do)**

| **Req ID** | **Requirement** | **Priority** | **Description** |
| :--------: | :-------------: | :----------: | :-------------- |
| **FR-01** | Profile Management | High | The system shall provide an admin management console to create, read, update, and delete (CRUD) doctor accounts containing ID, name, email, and tier. |
| **FR-02** | Secure Access Authentication | High | The system shall validate logins via password encryption, separating access into authorized Manager and Doctor layouts. |
| **FR-03** | Vacation Log Submission | High | The system shall capture date constraints for vacation requests and store them directly in the relational database. |
| **FR-04** | Shift Preference Setting | Medium | The system shall allow Doctor users to select and save preferred operational shift tiers (Day, Evening, or Night). |
| **FR-05** | Automated Roster Generation | High | The system shall execute an automated scheduling algorithm that automatically populates all empty month slots across the roster table. |
| **FR-06** | 24/7 Coverage Filter | High | The system shall validate that exactly three distinct 8-hour shift blocks are entirely filled for every 24-hour calendar cycle. |
| **FR-07** | Repeat Shift Check Rule | High | The system shall programmatically prevent the generation logic from assigning an identical Doctor profile to multiple shifts inside a single 24-hour window. |
| **FR-08** | Weekend Allocation Balance | Medium | The system shall verify during schedule compilation that every active doctor account receives a minimum of one full weekend off (Saturday and Sunday) per month. |
| **FR-09** | Personalized Dashboard Grid | High | The system shall display finalized calendar rosters to authenticated users using a month-view interface custom-filtered by role. |
| **FR-10** | Document Export Interface | Low | The system shall provide an action control button to convert the current active calendar web layout into a standard printable PDF. |

## 7. Non-Functional Requirements

| **NFR ID** | **Requirement** | **Description** |
| :--------: | :-------------: | :-------------- |
| **NFR-01** | Usability (Interface Efficiency) | The user interface shall allow an ED Manager to trigger automated monthly schedule generation in 3 clicks or fewer from the home command screen |
| **NFR-02** | Performance (Speed Constraint) | The background schedule generation algorithm shall finish processing, complete constraint verification, and render a final 1-month roster in less than 15.0 seconds |
| **NFR-03** | Security (Data Isolation) | All stored password strings must be hashed and salted; doctor profiles must be blocked from accessing profile administration pages or triggering the schedule generation algorithm |
| **NFR-04** | Reliability (Availability) | The application architecture shall maintain a minimum platform operational uptime baseline of 99.5% across any standard calendar month |
| **NFR-05** | Technical Constraint (Environment Bounds) | The user interface must operate entirely inside standard web browsers, omitting any external native mobile application packages or third-party email notification servers |

## 8. Success Criteria

1. Physician information can be added and deleted by the administrator.
1. The automated generation engine maps 100% of all required 24/7 active
   emergency department shift windows across a 1-month frame with zero
   unstaffed gaps.
1. The schedule verification backend successfully isolates and excludes 100% of
   validated doctor vacation requests, preventing roster placement errors.
1. 90% of test participants can navigate the system without assistance.

## 9. Risks & Constraints

### Technical Constraints

- Limited prior algorithmic experience within the developer role.
- The application must operate on standard local database structures and web
  environments.
- No integration to live hospital electronic medical record (EMR)
  architectures (outside scope).

### Time & Scope Constraints

- Production is locked to a strict 10-week academic timeline.
- communication is limited exclusively to virtual workspace tools.

### Project Risks & Mitigations

| **Risk** | **Description** | **Mitigation** |
| :------: | :-------------- | :------------- |
| Risk of Algorithmic Deadlock | If too many doctors log identical vacation windows, the system loop may fail to cover the 24/7 staffing matrix | Program the backend logic to flag scheduling failures to the Manager, allowing a manual priority override layer |
| Loss of Group Engagement | Virtual scheduling conflicts among team members | Maintain strict accountability with clear role handoffs during weekly syncs |

## 10. Requirements Traceability Matrix (initial version)

| **Requirement** | **Related User Story** | **Prototype Screen/Feature** |
| :-------------: | :--------------------: | :--------------------------: |
| **FR-01 (Profile CRUD)** | US-01 | Administrative Staff Configuration Dashboard Screen |
| **FR-02 (Authentication)** | US-02 | Main User Login Portal Landing Screen |
| **FR-03 (Vacation Capture)** | US-04 | Doctor Time-Off Request Calendar Entry Panel |
| **FR-04 (Preferences)** | US-03 | Doctor Shift Preference Selection Interface Form |
| **FR-05 (Roster Generation)** | US-05 | Manager Portal Run Schedule Interface Action Controller |
| **FR-06 (24/7 Coverage)** | US-05 | Backend Schedule Compilation Algorithm Code Base |
| **FR-07 (Repeat Shift rule)** | US-08 | Backend Schedule Verification Validation Script |
| **FR-08 (Weekend Policy)** | US-09 | Backend Algorithmic Calendar Logic Controller |
| **FR-09 (Calendar Display)** | US-06 | Master Roster Month-Grid Interface Screen View |
| **FR-10 (PDF Export)** | US-07 | Roster Page Print/Download Link Controller Interface |
