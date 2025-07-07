# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_withholding/salary_withholding.py`

## Classes

### `SalaryWithholding`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_duplicate_record` | `self` | `` |  |
| `set_status` | `self, update` | `` |  |
| `set_withholding_cycles_and_to_date` | `self` | `` |  |
| `get_to_date` | `self` | `` |  |
| `get_frequency_kwargs` | `self, withholding_cycles` | `` |  |





## Functions

### `get_payroll_frequency`
**Arguments:** `employee, posting_date`
**Decorators:** ``

**Docstring:**
```

```
### `link_bank_entry_in_salary_withholdings`
**Arguments:** `salary_slips, bank_entry`
**Decorators:** ``

**Docstring:**
```

```
### `update_salary_withholding_payment_status`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
update withholding status on bank entry submission/cancellation. Called from hooks
```
### `_update_payment_status_in_payroll`
**Arguments:** `withholdings, cancel`
**Decorators:** ``

**Docstring:**
```

```
### `_update_salary_withholdings`
**Arguments:** `withholdings, cancel`
**Decorators:** ``

**Docstring:**
```

```

