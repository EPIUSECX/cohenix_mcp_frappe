# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_application/leave_application.py`

## Classes

### `LeaveDayBlockedError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OverlapError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `AttendanceAlreadyMarkedError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NotAnOptionalHoliday`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InsufficientLeaveBalanceError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `LeaveAcrossAllocationsError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `LeaveApplication`
**Inherits:** `Document, PWANotificationsMixin`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_feed` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `before_cancel` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `after_delete` | `self` | `` |  |
| `publish_update` | `self` | `` |  |
| `validate_applicable_after` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `validate_dates_across_allocation` | `self` | `` |  |
| `get_allocation_based_on_application_dates` | `self` | `` | Returns allocation name, from and to dates for application dates |
| `validate_back_dated_application` | `self` | `` |  |
| `update_attendance` | `self` | `` |  |
| `create_or_update_attendance` | `self, attendance_name, date` | `` |  |
| `cancel_attendance` | `self` | `` |  |
| `validate_salary_processed_days` | `self` | `` |  |
| `show_block_day_warning` | `self` | `` |  |
| `validate_block_days` | `self` | `` |  |
| `validate_balance_leaves` | `self` | `` |  |
| `show_insufficient_balance_message` | `self, leave_balance_for_consumption` | `` |  |
| `validate_leave_overlap` | `self` | `` |  |
| `throw_overlap_error` | `self, d` | `` |  |
| `get_total_leaves_on_half_day` | `self` | `` |  |
| `validate_max_days` | `self` | `` |  |
| `get_consecutive_leave_details` | `self` | `` |  |
| `validate_attendance` | `self` | `` |  |
| `validate_optional_leave` | `self` | `` |  |
| `set_half_day_date` | `self` | `` |  |
| `notify_employee` | `self` | `` |  |
| `notify_leave_approver` | `self` | `` |  |
| `notify` | `self, args` | `` |  |
| `create_leave_ledger_entry` | `self, submit` | `` |  |
| `is_separate_ledger_entry_required` | `self, alloc_on_from_date, alloc_on_to_date` | `` | Checks if application dates fall in separate allocations |
| `create_separate_ledger_entries` | `self, alloc_on_from_date, alloc_on_to_date, submit, lwp` | `` | Creates separate ledger entries for application period falling into separate allocations |
| `create_ledger_entry_for_intermediate_allocation_expiry` | `self, expiry_date, submit, lwp` | `` | Splits leave application into two ledger entries to consider expiry of allocation |
| `validate_for_self_approval` | `self` | `` |  |
| `onload` | `self` | `` |  |





## Functions

### `get_allocation_expiry_for_cf_leaves`
**Arguments:** `employee, leave_type, to_date, from_date`
**Decorators:** ``

**Docstring:**
```
Returns expiry of carry forward allocation in leave ledger entry
```
### `get_number_of_leave_days`
**Arguments:** `employee, leave_type, from_date, to_date, half_day, half_day_date, holiday_list`
**Decorators:** ``

**Docstring:**
```
Returns number of leave days between 2 dates after considering half day and holidays
(Based on the include_holiday setting in Leave Type)
```
### `get_leave_details`
**Arguments:** `employee, date, for_salary_slip`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_balance_on`
**Arguments:** `employee, leave_type, date, to_date, consider_all_leaves_in_the_allocation_period, for_consumption`
**Decorators:** ``

**Docstring:**
```
Returns leave balance till date
:param employee: employee name
:param leave_type: leave type
:param date: date to check balance on
:param to_date: future date to check for allocation expiry
:param consider_all_leaves_in_the_allocation_period: consider all leaves taken till the allocation end date
:param for_consumption: flag to check if leave balance is required for consumption or display
        eg: employee has leave balance = 10 but allocation is expiring in 1 day so employee can only consume 1 leave
        in this case leave_balance = 10 but leave_balance_for_consumption = 1
        if True, returns a dict eg: {'leave_balance': 10, 'leave_balance_for_consumption': 1}
        else, returns leave_balance (in this case 10)
```
### `get_leave_allocation_records`
**Arguments:** `employee, date, leave_type`
**Decorators:** ``

**Docstring:**
```
Returns the total allocated leaves and carry forwarded leaves based on ledger entries
```
### `get_leaves_pending_approval_for_period`
**Arguments:** `employee, leave_type, from_date, to_date`
**Decorators:** ``

**Docstring:**
```
Returns leaves that are pending for approval
```
### `get_remaining_leaves`
**Arguments:** `allocation, leaves_taken, date, cf_expiry`
**Decorators:** ``

**Docstring:**
```
Returns a dict of leave_balance and leave_balance_for_consumption
leave_balance returns the available leave balance
leave_balance_for_consumption returns the minimum leaves remaining after comparing with remaining days for allocation expiry
```
### `get_new_and_cf_leaves_taken`
**Arguments:** `allocation, cf_expiry`
**Decorators:** ``

**Docstring:**
```
returns new leaves taken and carry forwarded leaves taken within an allocation period based on cf leave expiry
```
### `get_leaves_for_period`
**Arguments:** `employee, leave_type, from_date, to_date, skip_expired_leaves`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_entries`
**Arguments:** `employee, leave_type, from_date, to_date`
**Decorators:** ``

**Docstring:**
```
Returns leave entries between from_date and to_date.
```
### `get_holidays`
**Arguments:** `employee, from_date, to_date, holiday_list`
**Decorators:** ``

**Docstring:**
```
get holidays between two dates for the given employee
```
### `is_lwp`
**Arguments:** `leave_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_events`
**Arguments:** `start, end, filters`
**Decorators:** ``

**Docstring:**
```

```
### `add_department_leaves`
**Arguments:** `events, start, end, employee, company`
**Decorators:** ``

**Docstring:**
```

```
### `add_leaves`
**Arguments:** `events, start, end, filters`
**Decorators:** ``

**Docstring:**
```

```
### `add_block_dates`
**Arguments:** `events, start, end, employee, company`
**Decorators:** ``

**Docstring:**
```

```
### `add_holidays`
**Arguments:** `events, start, end, employee, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_mandatory_approval`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_approved_leaves_for_period`
**Arguments:** `employee, leave_type, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_approver`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

