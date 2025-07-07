# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_structure_assignment/salary_structure_assignment.py`

## Classes

### `DuplicateAssignment`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SalaryStructureAssignment`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `validate_company` | `self` | `` |  |
| `validate_income_tax_slab` | `self` | `` |  |
| `set_payroll_payable_account` | `self` | `` |  |
| `set_payroll_cost_centers` | `self` | `` |  |
| `get_payroll_cost_center` | `self` | `` |  |
| `validate_cost_centers` | `self` | `` |  |
| `warn_about_missing_opening_entries` | `self` | `` |  |
| `are_opening_entries_required` | `self` | `` |  |





## Functions

### `get_assigned_salary_structure`
**Arguments:** `employee, on_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_employee_currency`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `get_tax_component`
**Arguments:** `salary_structure`
**Decorators:** ``

**Docstring:**
```

```

