# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/additional_salary/additional_salary.py`

## Classes

### `AdditionalSalary`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_validate` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_salary_structure` | `self` | `` |  |
| `validate_recurring_additional_salary_overlap` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `validate_employee_referral` | `self` | `` |  |
| `validate_duplicate_additional_salary` | `self` | `` |  |
| `validate_tax_component_overwrite` | `self` | `` |  |
| `update_return_amount_in_employee_advance` | `self` | `` |  |
| `update_employee_referral` | `self, cancel` | `` |  |
| `get_amount` | `self, sal_start_date, sal_end_date` | `` |  |
| `validate_update_after_submit` | `self` | `` |  |





## Functions

### `get_additional_salaries`
**Arguments:** `employee, start_date, end_date, component_type`
**Decorators:** ``

**Docstring:**
```

```

