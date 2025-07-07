# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/report/monthly_attendance_sheet/monthly_attendance_sheet.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_message`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_columns`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns_for_leave_types`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_columns_for_days`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_total_days_in_month`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_data`
**Arguments:** `filters, attendance_map`
**Decorators:** ``

**Docstring:**
```

```
### `get_attendance_map`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns a dictionary of employee wise attendance map as per shifts for all the days of the month like
{
    'employee1': {
            'Morning Shift': {1: 'Present', 2: 'Absent', ...}
            'Evening Shift': {1: 'Absent', 2: 'Present', ...}
    },
    'employee2': {
            'Afternoon Shift': {1: 'Present', 2: 'Absent', ...}
            'Night Shift': {1: 'Absent', 2: 'Absent', ...}
    },
    'employee3': {
            None: {1: 'On Leave'}
    }
}
```
### `get_attendance_records`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_employee_related_details`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns
1. nested dict for employee details
2. list of values for the group by filter
```
### `get_holiday_map`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns a dict of holidays falling in the filter month and year
with list name as key and list of holidays as values like
{
        'Holiday List 1': [
                {'day_of_month': '0' , 'weekly_off': 1},
                {'day_of_month': '1', 'weekly_off': 0}
        ],
        'Holiday List 2': [
                {'day_of_month': '0' , 'weekly_off': 1},
                {'day_of_month': '1', 'weekly_off': 0}
        ]
}
```
### `get_rows`
**Arguments:** `employee_details, filters, holiday_map, attendance_map`
**Decorators:** ``

**Docstring:**
```

```
### `set_defaults_for_summarized_view`
**Arguments:** `filters, row`
**Decorators:** ``

**Docstring:**
```

```
### `get_attendance_status_for_summarized_view`
**Arguments:** `employee, filters, holidays`
**Decorators:** ``

**Docstring:**
```
Returns dict of attendance status for employee like
{'total_present': 1.5, 'total_leaves': 0.5, 'total_absent': 13.5, 'total_holidays': 8, 'unmarked_days': 5}
```
### `get_attendance_summary_and_days`
**Arguments:** `employee, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_attendance_status_for_detailed_view`
**Arguments:** `employee, filters, employee_attendance, holidays`
**Decorators:** ``

**Docstring:**
```
Returns list of shift-wise attendance status for employee
[
        {'shift': 'Morning Shift', 1: 'A', 2: 'P', 3: 'A'....},
        {'shift': 'Evening Shift', 1: 'P', 2: 'A', 3: 'P'....}
]
```
### `get_holiday_status`
**Arguments:** `day, holidays`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_summary`
**Arguments:** `employee, filters`
**Decorators:** ``

**Docstring:**
```
Returns a dict of leave type and corresponding leaves taken by employee like:
{'leave_without_pay': 1.0, 'sick_leave': 2.0}
```
### `get_entry_exits_summary`
**Arguments:** `employee, filters`
**Decorators:** ``

**Docstring:**
```
Returns total late entries and total early exits for employee like:
{'total_late_entries': 5, 'total_early_exits': 2}
```
### `get_attendance_years`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Returns all the years for which attendance records exist
```
### `get_chart_data`
**Arguments:** `attendance_map, filters`
**Decorators:** ``

**Docstring:**
```

```

