## Database Schema

### TimesheetTable

| Field      | Description                                    | Data Type    | Nullable | PK/FK |
| ---------- | ---------------------------------------------- | ------------ | -------- | ----- |
| ID         | Unique identifier for the timesheet            | int          | no       | PK    |
| StartDate  | The date of the first available entry          | datetime     | no       | N/A   |
| EndDate    | The date of the last available entry           | datetime     | no       | N/A   |
| RegHours   | The number of regular hours for the timesheet  | float        | no       | N/A   |
| OTHours    | The number of overtime hours for the timesheet | float        | no       | N/A   |
| TotalHours | The total number of hours for the timesheet    | float        | no       | N/A   |
| CreatedBy  | The user that created the timesheet            | nvarchar(50) | no       | N/A   |
| CreatedOn  | The date the timesheet was created             | datetime     | no       | N/A   |
| UpdatedBy  | The user that updated the timesheet            | nvarchar(50) | yes      | N/A   |
| UpdatedOn  | The date the timesheet was updated             | datetime     | yes      | N/A   |
| rowversion | The rowversion of the row                      | int          | no       | N/A   |

### TimesheetEntryTable

| Field | Description                                           | Data Type | Nullable | PK/FK |
| ----- | ----------------------------------------------------- | --------- | -------- | ----- |
| ID    | Unique identifier for the timesheet entry             | int       | no       | PK    |
| Date  | The date of the entry                                 | datetime  | no       | N/A   |
| JobID | The ID of the job associated with the timesheet entry | int       | yes      | FK    |
| Hours | The number of hours worked for this timesheet entry   | float     | yes      | N/A   |

### JobTable

| Field | Description                   | Data Type     | Nullable | PK/FK |
| ----- | ----------------------------- | ------------- | -------- | ----- |
| ID    | Unique identifier for the job | int           | no       | PK    |
| Name  | The name of the job           | nvarchar(256) | no       | N/A   |
