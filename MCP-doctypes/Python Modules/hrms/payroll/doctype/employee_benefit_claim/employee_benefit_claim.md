# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/employee_benefit_claim/employee_benefit_claim.py`

## Classes

### `EmployeeBenefitClaim`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_benefit_claim_amount` | `self, max_benefits, payroll_period` | `` |  |
| `validate_max_benefit_for_sal_struct` | `self, max_benefits` | `` |  |
| `validate_max_benefit_for_component` | `self, payroll_period` | `` |  |
| `validate_non_pro_rata_benefit_claim` | `self, max_benefits, payroll_period` | `` |  |
| `get_pro_rata_amount_in_application` | `self, payroll_period` | `` |  |





## Functions

### `get_benefit_pro_rata_ratio_amount`
**Arguments:** `employee, on_date, sal_struct`
**Decorators:** ``

**Docstring:**
```

```
### `get_benefit_claim_amount`
**Arguments:** `employee, start_date, end_date, salary_component`
**Decorators:** ``

**Docstring:**
```

```
### `get_total_benefit_dispensed`
**Arguments:** `employee, sal_struct, sal_slip_start_date, payroll_period`
**Decorators:** ``

**Docstring:**
```

```
### `get_last_payroll_period_benefits`
**Arguments:** `employee, sal_slip_start_date, sal_slip_end_date, payroll_period, sal_struct`
**Decorators:** ``

**Docstring:**
```

```

