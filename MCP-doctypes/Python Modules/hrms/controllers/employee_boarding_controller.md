# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/controllers/employee_boarding_controller.py`

## Classes

### `EmployeeBoardingController`
**Inherits:** `Document`


**Docstring:**
```
Create the project and the task for the boarding process
Assign to the concerned person and roles as per the onboarding/separation template
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `create_task_and_notify_user` | `self` | `` |  |
| `get_holiday_list` | `self` | `` |  |
| `get_task_dates` | `self, activity, holiday_list` | `` |  |
| `update_if_holiday` | `self, date, holiday_list` | `` |  |
| `assign_task_to_users` | `self, task, users` | `` |  |
| `on_cancel` | `self` | `` |  |





## Functions

### `get_onboarding_details`
**Arguments:** `parent, parenttype`
**Decorators:** ``

**Docstring:**
```

```
### `update_employee_boarding_status`
**Arguments:** `project, event`
**Decorators:** ``

**Docstring:**
```

```
### `update_task`
**Arguments:** `task, event`
**Decorators:** ``

**Docstring:**
```

```

