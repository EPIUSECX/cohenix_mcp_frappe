# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/shift_assignment_tool/shift_assignment_tool.py`

## Classes

### `ShiftAssignmentTool`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_employees` | `self, advanced_filters` | `` |  |
| `get_employees_for_assigning_shift` | `self, filters` | `` |  |
| `get_shift_requests` | `self, filters` | `` |  |
| `get_query_for_employees_with_shifts` | `self` | `` |  |
| `get_query_for_employees_with_same_shift_schedule` | `self` | `` |  |
| `get_query_checking_overlapping_shift_timings` | `self, query, doctype, shift_type` | `` |  |
| `bulk_assign` | `self, employees` | `` |  |
| `_bulk_assign` | `self, employees` | `` |  |
| `bulk_process_shift_requests` | `self, shift_requests, status` | `` |  |
| `_bulk_process_shift_requests` | `self, shift_requests, status` | `` |  |
| `create_shift_schedule_assignment` | `self, employee` | `` |  |





## Functions

### `create_shift_assignment`
**Arguments:** `employee, company, shift_type, start_date, end_date, status, shift_location, shift_schedule_assignment`
**Decorators:** ``

**Docstring:**
```

```

