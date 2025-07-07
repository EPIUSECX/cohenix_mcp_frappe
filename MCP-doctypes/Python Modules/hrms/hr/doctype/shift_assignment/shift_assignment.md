# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/shift_assignment/shift_assignment.py`

## Classes

### `OverlappingShiftError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `MultipleShiftError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ShiftAssignment`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate_employee_checkin` | `self` | `` |  |
| `validate_attendance` | `self` | `` |  |
| `validate_overlapping_shifts` | `self` | `` |  |
| `validate_same_date_multiple_shifts` | `self, overlapping_dates` | `` |  |
| `get_overlapping_dates` | `self` | `` |  |
| `throw_overlap_error` | `self, shift_details` | `` |  |





## Functions

### `has_overlapping_timings`
**Arguments:** `shift_1, shift_2`
**Decorators:** ``

**Docstring:**
```
Accepts two shift types and checks whether their timings are overlapping
```
### `get_events`
**Arguments:** `start, end, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_shift_assignments`
**Arguments:** `start, end, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_shift_events`
**Arguments:** `assignments`
**Decorators:** ``

**Docstring:**
```

```
### `get_shift_type_timing`
**Arguments:** `shift_types`
**Decorators:** ``

**Docstring:**
```

```
### `get_shift_for_time`
**Arguments:** `shifts, for_timestamp`
**Decorators:** ``

**Docstring:**
```
Returns shift with details for given timestamp
```
### `_is_shift_outside_assignment_period`
**Arguments:** `shift_details, assignment`
**Decorators:** ``

**Docstring:**
```
Compares shift's actual start and end dates with assignment dates
and returns True is shift is outside assignment period
```
### `_is_shift_start_before_assignment`
**Arguments:** `shift_details, assignment, is_midnight_shift`
**Decorators:** ``

**Docstring:**
```

```
### `_is_shift_end_after_assignment`
**Arguments:** `shift_details, assignment, is_midnight_shift`
**Decorators:** ``

**Docstring:**
```

```
### `_is_timestamp_within_shift`
**Arguments:** `shift_details, for_timestamp`
**Decorators:** ``

**Docstring:**
```
Checks whether the timestamp is within shift's actual start and end datetime
```
### `_adjust_overlapping_shifts`
**Arguments:** `shifts`
**Decorators:** ``

**Docstring:**
```
Compares 2 consecutive shifts and adjusts start and end times
if they are overlapping within grace period
```
### `get_shifts_for_date`
**Arguments:** `employee, for_timestamp`
**Decorators:** ``

**Docstring:**
```
Returns list of shifts with details for given date
```
### `get_shift_for_timestamp`
**Arguments:** `employee, for_timestamp`
**Decorators:** ``

**Docstring:**
```

```
### `get_employee_shift`
**Arguments:** `employee, for_timestamp, consider_default_shift, next_shift_direction`
**Decorators:** ``

**Docstring:**
```
Returns a Shift Type for the given employee on the given date

:param employee: Employee for which shift is required.
:param for_timestamp: DateTime on which shift is required
:param consider_default_shift: If set to true, default shift is taken when no shift assignment is found.
:param next_shift_direction: One of: None, 'forward', 'reverse'. Direction to look for next shift if shift not found on given date.
```
### `get_prev_or_next_shift`
**Arguments:** `employee, for_timestamp, consider_default_shift, default_shift, next_shift_direction`
**Decorators:** ``

**Docstring:**
```
Returns a dict of shift details for the next or prev shift based on the next_shift_direction
```
### `get_employee_shift_timings`
**Arguments:** `employee, for_timestamp, consider_default_shift`
**Decorators:** ``

**Docstring:**
```
Returns previous shift, current/upcoming shift, next_shift for the given timestamp and employee
```
### `get_actual_start_end_datetime_of_shift`
**Arguments:** `employee, for_timestamp, consider_default_shift`
**Decorators:** ``

**Docstring:**
```
Returns a Dict containing shift details with actual_start and actual_end datetime values
Here 'actual' means taking into account the "begin_check_in_before_shift_start_time" and "allow_check_out_after_shift_end_time".
Empty Dict is returned if the timestamp is outside any actual shift timings.

:param employee (str): Employee name
:param for_timestamp (datetime, optional): Datetime value of checkin, if not provided considers current datetime
:param consider_default_shift (bool, optional): Flag (defaults to False) to specify whether to consider
default shift in employee master if no shift assignment is found
```
### `get_exact_shift`
**Arguments:** `shifts, for_timestamp`
**Decorators:** ``

**Docstring:**
```
Returns the shift details (dict) for the exact shift in which the 'for_timestamp' value falls among multiple shifts
```
### `get_shift_details`
**Arguments:** `shift_type_name, for_timestamp`
**Decorators:** ``

**Docstring:**
```
Returns a Dict containing shift details with the following data:
'shift_type' - Object of DocType Shift Type,
'start_datetime' - datetime of shift start on given timestamp,
'end_datetime' - datetime of shift end on given timestamp,
'actual_start' - datetime of shift start after adding 'begin_check_in_before_shift_start_time',
'actual_end' - datetime of shift end after adding 'allow_check_out_after_shift_end_time' (None is returned if this is zero)

:param shift_type_name (str): shift type name for which shift_details are required.
:param for_timestamp (datetime, optional): Datetime value of checkin, if not provided considers current datetime
```
### `get_shift_type`
**Arguments:** `shift_type_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_shift_timings`
**Arguments:** `shift_type, for_timestamp`
**Decorators:** ``

**Docstring:**
```

```

