# Hospital Employee Roster — MVP Database Schema

## PostgreSQL Enum Types

The following enum types should be defined in PostgreSQL to keep the schema
readable and consistent.

### account_role

Allowed values:

- manager
- physician

### shift_type

Allowed values:

- morning
- evening
- night

### availability_request_type

Allowed values:

- vacation
- busy_period

### request_status

Allowed values:

- pending
- approved
- rejected

### schedule_status

Allowed values:

- draft
- generated
- finalized

### assignment_source_type

Allowed values:

- generated
- manual_override

## Departments

Stores hospital departments, such as the Pediatric Department.

- department_id
  - Primary Key
  - Auto-increment

- department_name
  - Required
  - Example: "Pediatric Department"

- is_active
  - Boolean
  - Default: true

## Department Settings

Stores simple scheduling rules for each department.

- department_id
  - Primary Key
  - Foreign Key → Departments.department_id

- morning_required_physicians
  - Integer
  - Required
  - Minimum: 1

- evening_required_physicians
  - Integer
  - Required
  - Minimum: 1

- night_required_physicians
  - Integer
  - Required
  - Minimum: 1

- min_shifts_per_physician
  - Integer
  - Required
  - Minimum: 0

- max_shifts_per_physician
  - Integer
  - Required
  - Minimum: 1

## Accounts

Stores login and profile information for managers and physicians.

- account_id
  - Primary Key
  - Auto-increment

- full_name
  - Required

- display_name
  - Optional

- email
  - Required
  - Unique
  - Used for login

- password_hash
  - Required
  - Stores hashed password only

- role
  - Required
  - Type: account_role
  - Allowed values:
    - manager
    - physician

- department_id
  - Foreign Key → Departments.department_id
  - Required

- is_active
  - Boolean
  - Default: true

## Shift Preferences

Stores each physician’s general shift preferences.

- physician_id
  - Primary Key
  - Foreign Key → Accounts.account_id

- morning_preference
  - Integer
  - Required
  - Range: 0 to 5

- evening_preference
  - Integer
  - Required
  - Range: 0 to 5

- night_preference
  - Integer
  - Required
  - Range: 0 to 5

## Availability Requests

Stores vacation requests and busy-period declarations.

- request_id
  - Primary Key
  - Auto-increment

- physician_id
  - Foreign Key → Accounts.account_id
  - Required

- start_date
  - Required

- end_date
  - Required

- request_type
  - Required
  - Type: availability_request_type
  - Allowed values:
    - vacation
    - busy_period

- status
  - Required
  - Type: request_status
  - Allowed values:
    - pending
    - approved
    - rejected
  - Default: pending

- reviewed_by_account_id
  - Foreign Key → Accounts.account_id
  - Optional
  - Usually a manager account

- reviewed_at
  - Timestamp
  - Optional

- notes
  - Optional

### Availability Request Constraints

- end_date >= start_date

## Schedules

Represents a generated monthly roster for a department.

- schedule_id
  - Primary Key
  - Auto-increment

- department_id
  - Foreign Key → Departments.department_id
  - Required

- schedule_month
  - Integer
  - Required
  - Range: 1 to 12

- schedule_year
  - Integer
  - Required

- status
  - Required
  - Type: schedule_status
  - Allowed values:
    - draft
    - generated
    - finalized
  - Default: draft

- generated_by_account_id
  - Foreign Key → Accounts.account_id
  - Optional
  - Usually a manager account

- generated_at
  - Timestamp
  - Optional

- finalized_at
  - Timestamp
  - Optional

## Schedule Entries

Stores individual physician shift assignments.

Each row represents one physician assigned to one shift on one date.

This design allows multiple physicians to be assigned to the same date and
shift when busier shifts require extra coverage.

- schedule_entry_id
  - Primary Key
  - Auto-increment

- schedule_id
  - Foreign Key → Schedules.schedule_id
  - Required

- work_date
  - Required

- shift
  - Required
  - Type: shift_type
  - Allowed values:
    - morning
    - evening
    - night

- physician_id
  - Foreign Key → Accounts.account_id
  - Required

- assignment_source
  - Required
  - Type: assignment_source_type
  - Allowed values:
    - generated
    - manual_override
  - Default: generated

### Schedule Entry Constraints

Unique:

- schedule_id
- work_date
- shift
- physician_id
