# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_checkin/employee_checkin.py`

## Classes

### `CheckinRadiusExceededError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `EmployeeCheckin`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_duplicate_log` | `self` | `` |  |
| `validate_time_change` | `self` | `` |  |
| `set_geolocation` | `self` | `` |  |
| `fetch_shift` | `self` | `` |  |
| `validate_distance_from_shift_location` | `self` | `` |  |





## Functions

### `add_log_based_on_employee_field`
**Arguments:** `employee_field_value, timestamp, device_id, log_type, skip_auto_attendance, employee_fieldname, latitude, longitude`
**Decorators:** ``

**Docstring:**
```
Finds the relevant Employee using the employee field value and creates a Employee Checkin.

:param employee_field_value: The value to look for in employee field.
:param timestamp: The timestamp of the Log. Currently expected in the following format as string: '2019-05-08 10:48:08.000000'
:param device_id: (optional)Location / Device ID. A short string is expected.
:param log_type: (optional)Direction of the Punch if available (IN/OUT).
:param skip_auto_attendance: (optional)Skip auto attendance field will be set for this log(0/1).
:param employee_fieldname: (Default: attendance_device_id)Name of the field in Employee DocType based on which employee lookup will happen.
:latitude: (optional) Latitude of the shift location.
:longitude: (optional) Longitude of the shift location.
```
### `bulk_fetch_shift`
**Arguments:** `checkins`
**Decorators:** ``

**Docstring:**
```

```
### `mark_attendance_and_link_log`
**Arguments:** `logs, attendance_status, attendance_date, working_hours, late_entry, early_exit, in_time, out_time, shift`
**Decorators:** ``

**Docstring:**
```
Creates an attendance and links the attendance to the Employee Checkin.
Note: If attendance is already present for the given date, the logs are marked as skipped and no exception is thrown.

:param logs: The List of 'Employee Checkin'.
:param attendance_status: Attendance status to be marked. One of: (Present, Absent, Half Day, Skip). Note: 'On Leave' is not supported by this function.
:param attendance_date: Date of the attendance to be created.
:param working_hours: (optional)Number of working hours for the given date.
```
### `get_existing_half_day_attendance`
**Arguments:** `employee, attendance_date`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_working_hours`
**Arguments:** `logs, check_in_out_type, working_hours_calc_type`
**Decorators:** ``

**Docstring:**
```
Given a set of logs in chronological order calculates the total working hours based on the parameters.
Zero is returned for all invalid cases.

:param logs: The List of 'Employee Checkin'.
:param check_in_out_type: One of: 'Alternating entries as IN and OUT during the same shift', 'Strictly based on Log Type in Employee Checkin'
:param working_hours_calc_type: One of: 'First Check-in and Last Check-out', 'Every Valid Check-in and Check-out'
```
### `time_diff_in_hours`
**Arguments:** `start, end`
**Decorators:** ``

**Docstring:**
```

```
### `find_index_in_dict`
**Arguments:** `dict_list, key, value`
**Decorators:** ``

**Docstring:**
```

```
### `handle_attendance_exception`
**Arguments:** `log_names, error_message`
**Decorators:** ``

**Docstring:**
```

```
### `add_comment_in_checkins`
**Arguments:** `log_names, error_message`
**Decorators:** ``

**Docstring:**
```

```
### `skip_attendance_in_checkins`
**Arguments:** `log_names`
**Decorators:** ``

**Docstring:**
```

```
### `update_attendance_in_checkins`
**Arguments:** `log_names, attendance_id`
**Decorators:** ``

**Docstring:**
```

```

