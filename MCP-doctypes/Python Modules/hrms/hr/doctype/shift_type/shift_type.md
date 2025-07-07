# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/shift_type/shift_type.py`

## Classes

### `ShiftType`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_same_start_and_end` | `self, start_time, end_time` | `` |  |
| `validate_circular_shift` | `self, start_time, end_time` | `` |  |
| `get_shift_start_and_shift_end` | `self, start_time, end_time` | `` |  |
| `get_total_shift_duration_in_minutes` | `self, shift_start, shift_end` | `` |  |
| `get_max_shift_buffer_label` | `self` | `` |  |
| `validate_unlinked_logs` | `self` | `` |  |
| `is_field_modified` | `self, fieldname` | `` |  |
| `unlinked_checkins_exist` | `self` | `` |  |
| `process_auto_attendance` | `self` | `` |  |
| `get_employee_checkins` | `self` | `` |  |
| `get_attendance` | `self, logs` | `` | Return attendance_status, working_hours, late_entry, early_exit, in_time, out_time
for a set of logs belonging to a single shift.
Assumptions:
1. These logs belongs to a single shift, single employee and it's not in a holiday date.
2. Logs are in chronological order |
| `mark_absent_for_dates_with_no_attendance` | `self, employee` | `` | Marks Absents for the given employee on working days in this shift that have no attendance marked.
The Absent status is marked starting from 'process_attendance_after' or employee creation date. |
| `get_dates_for_attendance` | `self, employee` | `` |  |
| `get_start_and_end_dates` | `self, employee` | `` | Returns start and end dates for checking attendance and marking absent
return: start date = max of `process_attendance_after` and DOJ
return: end date = min of shift before `last_sync_of_checkin` and Relieving Date |
| `get_marked_attendance_dates_between` | `self, employee, start_date, end_date` | `` |  |
| `get_assigned_employees` | `self, from_date, consider_default_shift` | `` | Get all such employees who either have this shift assigned that hasn't ended or have this shift as default shift.
This may fetch some redundant employees who have another shift assigned that may have started or ended before or after the
attendance processing date. But this is done to avoid missing any employee who may have this shift as active shift. |
| `get_holiday_list` | `self, employee` | `` |  |
| `should_mark_attendance` | `self, employee, attendance_date` | `` | Determines whether attendance should be marked on holidays or not |
| `mark_absent_for_half_day_dates` | `self, employee` | `` |  |





## Functions

### `update_last_sync_of_checkin`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Called from hooks
```
### `get_actual_shift_end`
**Arguments:** `shift, current_datetime`
**Decorators:** ``

**Docstring:**
```

```
### `process_auto_attendance_for_all_shifts`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Called from hooks
```

