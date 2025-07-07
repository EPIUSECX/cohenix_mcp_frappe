# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_structure/salary_structure.py`

## Classes

### `SalaryStructure`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_validate` | `self` | `` |  |
| `before_update_after_submit` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `validate_formula_setup` | `self` | `` |  |
| `set_missing_values` | `self` | `` |  |
| `validate_component_based_on_tax_slab` | `self` | `` |  |
| `validate_amount` | `self` | `` |  |
| `validate_payment_days_based_dependent_component` | `self` | `` |  |
| `get_component_abbreviations` | `self` | `` |  |
| `validate_timesheet_component` | `self` | `` |  |
| `sanitize_condition_and_formula_fields` | `self` | `` |  |
| `reset_condition_and_formula_fields` | `self` | `` |  |
| `validate_max_benefits_with_flexi` | `self` | `` |  |
| `get_employees` | `self` | `` |  |
| `assign_salary_structure` | `self, branch, grade, department, designation, employee, payroll_payable_account, from_date, base, variable, income_tax_slab` | `` |  |





## Functions

### `assign_salary_structure_for_employees`
**Arguments:** `employees, salary_structure, payroll_payable_account, from_date, base, variable, income_tax_slab`
**Decorators:** ``

**Docstring:**
```

```
### `create_salary_structure_assignment`
**Arguments:** `employee, salary_structure, company, currency, from_date, payroll_payable_account, base, variable, income_tax_slab`
**Decorators:** ``

**Docstring:**
```

```
### `get_existing_assignments`
**Arguments:** `employees, salary_structure, from_date`
**Decorators:** ``

**Docstring:**
```

```
### `make_salary_slip`
**Arguments:** `source_name, target_doc, employee, posting_date, as_print, print_format, for_preview, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `get_employees`
**Arguments:** `salary_structure`
**Decorators:** ``

**Docstring:**
```

```
### `get_salary_component`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```

