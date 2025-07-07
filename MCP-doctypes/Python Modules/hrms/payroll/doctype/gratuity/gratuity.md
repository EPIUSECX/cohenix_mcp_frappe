# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/gratuity/gratuity.py`

## Classes

### `Gratuity`
**Inherits:** `AccountsController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `gratuity_settings` | `self` | `property` |  |
| `set_status` | `self, update` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `create_gl_entries` | `self, cancel` | `` |  |
| `get_gl_entries` | `self` | `` |  |
| `create_additional_salary` | `self` | `` |  |
| `set_total_advance_paid` | `self` | `` |  |
| `calculate_work_experience_and_amount` | `self` | `` |  |
| `get_work_experience` | `self` | `` |  |
| `get_total_working_days` | `self` | `` |  |
| `get_non_working_days` | `self, relieving_date, status` | `` |  |
| `get_gratuity_amount` | `self, experience` | `` |  |
| `get_total_component_amount` | `self` | `` |  |
| `get_applicable_components` | `self` | `` |  |
| `get_gratuity_rule_slabs` | `self` | `` |  |
| `_is_experience_within_slab` | `self, slab, experience` | `` |  |
| `_is_experience_beyond_slab` | `self, slab, experience` | `` |  |





## Functions

### `get_last_salary_slip`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```

