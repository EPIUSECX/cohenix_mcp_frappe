# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/timesheet_detail/timesheet_detail.py`

## Classes

### `TimesheetDetail`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `set_to_time` | `self` | `` | Set to_time based on from_time and hours. |
| `set_project` | `self` | `` | Set project based on task. |
| `calculate_hours` | `self` | `` | Calculate hours based on from_time and to_time. |
| `update_billing_hours` | `self` | `` | Update billing hours based on hours. |
| `update_cost` | `self, employee` | `` | Update costing and billing rates based on activity type. |
| `validate_dates` | `self` | `` | Validate that to_time is not before from_time. |
| `validate_parent_project` | `self, parent_project` | `` | Validate that project is same as Timesheet's parent project. |
| `validate_task_project` | `self` | `` | Validate that the the task belongs to the project specified in the timesheet detail. |
| `validate_billing_hours` | `self` | `` | Warn if billing hours are more than actual hours. |





## Functions

No top-level functions found in this file.
