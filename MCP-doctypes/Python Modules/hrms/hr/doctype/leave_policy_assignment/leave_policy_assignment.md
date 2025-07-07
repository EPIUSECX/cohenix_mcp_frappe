# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_policy_assignment/leave_policy_assignment.py`

## Classes

### `LeavePolicyAssignment`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `set_dates` | `self` | `` |  |
| `validate_policy_assignment_overlap` | `self` | `` |  |
| `warn_about_carry_forwarding` | `self` | `` |  |
| `grant_leave_alloc_for_employee` | `self` | `` |  |
| `create_leave_allocation` | `self, annual_allocation, leave_details, date_of_joining` | `` |  |
| `get_new_leaves` | `self, annual_allocation, leave_details, date_of_joining` | `` |  |
| `get_leaves_for_passed_months` | `self, annual_allocation, leave_details, date_of_joining` | `` |  |





## Functions

### `calculate_pro_rated_leaves`
**Arguments:** `leaves, date_of_joining, period_start_date, period_end_date, is_earned_leave`
**Decorators:** ``

**Docstring:**
```

```
### `is_earned_leave_applicable_for_current_month`
**Arguments:** `date_of_joining, allocate_on_day`
**Decorators:** ``

**Docstring:**
```

```
### `create_assignment_for_multiple_employees`
**Arguments:** `employees, data`
**Decorators:** ``

**Docstring:**
```

```
### `create_assignment`
**Arguments:** `employee, data`
**Decorators:** ``

**Docstring:**
```

```
### `show_assignment_submission_status`
**Arguments:** `failed`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_type_details`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

