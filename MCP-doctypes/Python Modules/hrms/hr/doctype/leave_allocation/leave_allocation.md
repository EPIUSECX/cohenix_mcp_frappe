# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_allocation/leave_allocation.py`

## Classes

### `OverlapError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `BackDatedAllocationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OverAllocationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `LessAllocationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ValueMultiplierError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `LeaveAllocation`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_leave_days_and_dates` | `self` | `` |  |
| `validate_leave_allocation_days` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `get_existing_leave_count` | `self` | `` |  |
| `validate_earned_leave_update` | `self` | `` |  |
| `validate_against_leave_applications` | `self` | `` |  |
| `update_leave_policy_assignments_when_no_allocations_left` | `self` | `` |  |
| `validate_period` | `self` | `` |  |
| `validate_lwp` | `self` | `` |  |
| `validate_allocation_overlap` | `self` | `` |  |
| `validate_back_dated_allocation` | `self` | `` |  |
| `set_total_leaves_allocated` | `self` | `` |  |
| `limit_carry_forward_based_on_max_allowed_leaves` | `self` | `` |  |
| `set_carry_forwarded_leaves_in_previous_allocation` | `self, on_cancel` | `` | Set carry forwarded leaves in previous allocation |
| `validate_total_leaves_allocated` | `self` | `` |  |
| `create_leave_ledger_entry` | `self, submit` | `` |  |
| `allocate_leaves_manually` | `self, new_leaves, from_date` | `` |  |
| `get_monthly_earned_leave` | `self` | `` |  |





## Functions

### `get_previous_allocation`
**Arguments:** `from_date, leave_type, employee`
**Decorators:** ``

**Docstring:**
```
Returns document properties of previous allocation
```
### `get_leave_allocation_for_period`
**Arguments:** `employee, leave_type, from_date, to_date, exclude_allocation`
**Decorators:** ``

**Docstring:**
```

```
### `get_carry_forwarded_leaves`
**Arguments:** `employee, leave_type, date, carry_forward`
**Decorators:** ``

**Docstring:**
```
Returns carry forwarded leaves for the given employee
```
### `get_unused_leaves`
**Arguments:** `employee, leave_type, from_date, to_date`
**Decorators:** ``

**Docstring:**
```
Returns unused leaves between the given period while skipping leave allocation expiry
```
### `validate_carry_forward`
**Arguments:** `leave_type`
**Decorators:** ``

**Docstring:**
```

```
### `show_expire_leave_dialog`
**Arguments:** `expired_leaves, leave_type`
**Decorators:** ``

**Docstring:**
```

```
### `expire_carried_forward_allocation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

