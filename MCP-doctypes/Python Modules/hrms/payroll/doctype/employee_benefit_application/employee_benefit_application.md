# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/employee_benefit_application/employee_benefit_application.py`

## Classes

### `EmployeeBenefitApplication`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_prev_benefit_claim` | `self` | `` |  |
| `validate_remaining_benefit_amount` | `self` | `` |  |
| `validate_max_benefit_for_component` | `self` | `` |  |
| `validate_max_benefit` | `self, earning_component_name` | `` |  |
| `validate_duplicate_on_payroll_period` | `self` | `` |  |





## Functions

### `get_max_benefits`
**Arguments:** `employee, on_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_max_benefits_remaining`
**Arguments:** `employee, on_date, payroll_period`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_lwp`
**Arguments:** `employee, start_date, holidays, working_days`
**Decorators:** ``

**Docstring:**
```

```
### `get_benefit_component_amount`
**Arguments:** `employee, start_date, end_date, salary_component, sal_struct, payroll_frequency, payroll_period`
**Decorators:** ``

**Docstring:**
```

```
### `get_benefit_amount_based_on_pro_rata`
**Arguments:** `sal_struct, component_max_benefit`
**Decorators:** ``

**Docstring:**
```

```
### `get_earning_components`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_earning_components_max_benefits`
**Arguments:** `employee, date, earning_component`
**Decorators:** ``

**Docstring:**
```

```

