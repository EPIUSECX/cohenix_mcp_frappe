# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/regional/india/utils.py`

## Classes

No classes found in this file.


## Functions

### `calculate_annual_eligible_hra_exemption`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `has_hra_component`
**Arguments:** `salary_structure, hra_component`
**Decorators:** ``

**Docstring:**
```

```
### `get_end_date_for_assignment`
**Arguments:** `assignment_dates, idx, payroll_period`
**Decorators:** ``

**Docstring:**
```

```
### `get_component_amt_from_salary_slip`
**Arguments:** `employee, salary_structure, basic_component, hra_component, from_date`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_hra_exemption`
**Arguments:** `salary_structure, annual_basic, annual_hra, monthly_house_rent, rented_in_metro_city`
**Decorators:** ``

**Docstring:**
```

```
### `get_component_pay`
**Arguments:** `frequency, amount, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `validate_house_rent_dates`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_hra_exemption_for_period`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_tax_with_marginal_relief`
**Arguments:** `tax_slab, tax_amount, annual_taxable_earning`
**Decorators:** ``

**Docstring:**
```
Returns the tax payable after applying marginal relief (if applicable).
    If taxable income is between tax relief limit and marginal relief limit, and tax payable on income is more than income excess over tax relief, then tax payable is reduced to just the excess income.
```

