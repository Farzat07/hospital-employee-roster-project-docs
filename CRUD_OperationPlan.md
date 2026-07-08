# CRUD Operation Plan

## 1. Departments

| Operation | Example                                                    |
| --------- | ---------------------------------------------------------- |
| Create    | Manager creates a new department: "Pediatric Department".  |
| Read      | Manager views all departments.                             |
| Update    | Manager renames a department or changes its active status. |
| Delete    | Manager deactivates or removes an unused department.       |

## 2. Department Settings

| Operation | Example                                                        |
| --------- | -------------------------------------------------------------- |
| Create    | Manager defines staffing requirements for a department.        |
| Read      | Manager views current scheduling rules.                        |
| Update    | Manager changes required night-shift coverage to 2 physicians. |
| Delete    | Usually not allowed; settings are updated instead.             |

## 3. Accounts (FR-01: Profile Management)

| Operation | Example                                                       |
| --------- | ------------------------------------------------------------- |
| Create    | Manager creates a physician account.                          |
| Read      | Manager views physician details. Physician views own profile. |
| Update    | Manager updates physician status. Physician updates password. |
| Delete    | Manager deactivates a physician account.                      |

## 4. Shift Preferences

| Operation | Example                                           |
| --------- | ------------------------------------------------- |
| Create    | Physician submits preferences for the first time. |
| Read      | Physician or Manager views preferences.           |
| Update    | Physician changes night-shift preference.         |
| Delete    | Reset preferences to defaults.                    |

## 5. Availability Requests

| Operation | Example                                |
| --------- | -------------------------------------- |
| Create    | Physician requests vacation.           |
| Read      | Manager reviews requests.              |
| Update    | Manager approves or rejects request.   |
| Delete    | Physician withdraws a pending request. |

## 6. Schedules

| Operation | Example                                                  |
| --------- | -------------------------------------------------------- |
| Create    | Manager generates August 2026 roster.                    |
| Read      | Users view monthly schedule.                             |
| Update    | Manager changes schedule status from Draft to Finalized. |
| Delete    | Manager removes an incorrect draft schedule.             |

## 7. Schedule Entries

| Operation | Example                                         |
| --------- | ----------------------------------------------- |
| Create    | Scheduling engine assigns physician to a shift. |
| Read      | Users view shift assignments.                   |
| Update    | Manager manually reassigns a physician.         |
| Delete    | Manager removes an incorrect assignment.        |

## Role-Based CRUD Matrix

| Entity                | Manager     | Physician |
| --------------------- | ----------- | --------- |
| Departments           | CRUD        | Read      |
| Department Settings   | CRUD        | Read      |
| Accounts              | CRUD        | Read Own  |
| Shift Preferences     | Read        | CRUD Own  |
| Availability Requests | Read/Update | CRUD Own  |
| Schedules             | CRUD        | Read      |
| Schedule Entries      | CRUD        | Read      |
