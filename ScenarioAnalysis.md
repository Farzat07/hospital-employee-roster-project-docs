# SCENARIO ANALYSIS WORKSHEET

<!-- markdownlint-configure-file
{
    "MD013": { "tables": false }
}
-->

## 1. Scenario Summary

The business / organization is a University Hospital’s emergency department.
The problem is manual assignment of shifts by doctors, and automating that
schedule would help keep things on track.

## 2. Stakeholders

| **Stakeholder**  | **Why they matter**                                    | **What they need**                                                  |
|:----------------:|:------------------------------------------------------:|:-------------------------------------------------------------------:|
| Hospital manager | Head of department, responsible for smooth functioning | All shifts to be filled to have at least one doctor on at all times |
| Doctor           | The one following the schedule                         | Proper rest: a maximum of one shift per 24 hour window              |

## 3. Pain Points (Current Problems)

1. Manual shift assigning.
2. Not giving doctors the proper rest.
3. Keeping track of vacation and covering for shifts.

## 4. Key Goals of the Solution

1. Automated shift assigning.
2. Ensuring proper rest for doctors.
3. Factoring in vacation time and PTO in an automated system.

## 5. Functional Requirements (What the system should *do*)

1. The system must… Assign a maximum of one shift to a doctor in each 24 hour period.
2. The system must… Assign one free weekend at least each month.
3. The system must… Factor in vacation time and PTO.
4. The system must… Assign more doctors to busier times/shifts.
5. The system must… Print a clean schedule as a table each month.

## 6. Non-Functional Requirements (Qualities of the system)

1. The system should… be easy to use.
2. The system should… have secure logins.
3. The system should… function smoothly (fast processing).
4. The system should… be easy to access.
5. The system should… check the schedule for missing requirements before output.

## 7. Constraints and Assumption

### Constraints

- Sick days
- Technical skills
- Maximum work hours
- Unclear operating environment (in-house? cloud?)

### Assumptions

- Accurate availability
- Sufficient availability of doctors
- Acceptance of shifts

## 8. Early System Ideas (Brainstorm Section)

### Screens/Pages

- A preferences settings page for doctors.
- A configuration page for management.

### Stored Data

- Names of doctors.
- Doctor vacations.
- Doctor preferences.
- Department-wide configurations.
- Past schedules.

### Reports/Dashboards

- A shifts page for each doctor.
- A final schedule.
- Aggregate number of shifts and vacation days for each employee (optional).

### Build order

1. Start with the basic algorithm.
2. As more data is needed for extra features, evolve the database structure accordingly.
3. Design the UI and reports generation.
4. Add printable PDF generation functionality.

## 9. Risks You Already See

1. Team responsiveness.
2. Lack of UI/UX expertise.
3. Unfamiliar algorithms.
4. More steps than previously acknowledged.

## 10. Preliminary Scope Statement

This project aims to automate the shift schedules of doctors, reducing the
manual work and potentially adding more flexibility to individual doctors'
needs. This will make things quicker and easier for the doctors, and improve
control and visibility for the hospital manager.
