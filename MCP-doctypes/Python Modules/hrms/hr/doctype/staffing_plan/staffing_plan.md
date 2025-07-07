# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/staffing_plan/staffing_plan.py`

## Classes

### `SubsidiaryCompanyError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ParentCompanyError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `StaffingPlan`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_period` | `self` | `` |  |
| `validate_details` | `self` | `` |  |
| `set_total_estimated_budget` | `self` | `` |  |
| `set_number_of_positions` | `self, detail` | `` |  |
| `validate_overlap` | `self, staffing_plan_detail` | `` |  |
| `validate_with_parent_plan` | `self, staffing_plan_detail` | `` |  |
| `validate_with_subsidiary_plans` | `self, staffing_plan_detail` | `` |  |
| `set_job_requisitions` | `self, job_reqs` | `` |  |





## Functions

### `get_designation_counts`
**Arguments:** `designation, company, job_opening`
**Decorators:** ``

**Docstring:**
```

```
### `get_active_staffing_plan_details`
**Arguments:** `company, designation, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```

