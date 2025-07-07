# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/attendance/attendance.py`

## Classes

### `DuplicateAttendanceError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OverlappingShiftAttendanceError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Attendance`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate_attendance_date` | `self` | `` |  |
| `validate_duplicate_record` | `self` | `` |  |
| `get_duplicate_attendance_record` | `self` | `` |  |
| `validate_overlapping_shift_attendance` | `self` | `` |  |
| `get_overlapping_shift_attendance` | `self` | `` |  |
| `validate_employee_status` | `self` | `` |  |
| `check_leave_record` | `self` | `` |  |
| `validate_employee` | `self` | `` |  |
| `unlink_attendance_from_checkins` | `self` | `` |  |





## Functions

### `get_events`
**Arguments:** `start, end, filters`
**Decorators:** ``

**Docstring:**
```

```
### `add_attendance`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `add_holidays`
**Arguments:** `events, start, end, employee`
**Decorators:** ``

**Docstring:**
```

```
### `mark_attendance`
**Arguments:** `employee, attendance_date, status, shift, leave_type, late_entry, early_exit, half_day_status`
**Decorators:** ``

**Docstring:**
```

```
### `mark_bulk_attendance`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `get_unmarked_days`
**Arguments:** `employee, from_date, to_date, exclude_holidays`
**Decorators:** ``

**Docstring:**
```

```

