# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/compensatory_leave_request/test_compensatory_leave_request.py`

## Classes

### `TestCompensatoryLeaveRequest`
**Inherits:** `HRMSTestSuite`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `test_leave_balance_on_submit` | `self` | `` | check creation of leave allocation on submission of compensatory leave request |
| `test_allocation_update_on_submit` | `self` | `` |  |
| `test_allocation_update_on_submit_on_multiple_allocations` | `self` | `` | Tests whether the correct allocation is updated when there are multiple allocations in the same leave period |
| `test_creation_of_leave_ledger_entry_on_submit` | `self` | `` | check creation of leave ledger entry on submission of leave request |
| `test_half_day_compensatory_leave` | `self` | `` |  |
| `test_request_on_leave_period_boundary` | `self` | `` |  |





## Functions

### `get_compensatory_leave_request`
**Arguments:** `employee, leave_date`
**Decorators:** ``

**Docstring:**
```

```
### `mark_attendance`
**Arguments:** `employee, date, status`
**Decorators:** ``

**Docstring:**
```

```
### `create_holiday_list`
**Arguments:** `from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```

