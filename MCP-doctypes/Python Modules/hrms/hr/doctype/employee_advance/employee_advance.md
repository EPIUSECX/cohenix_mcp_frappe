# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_advance/employee_advance.py`

## Classes

### `EmployeeAdvanceOverPayment`


**Docstring:**
```

```

**Methods:**
No methods found.

### `EmployeeAdvance`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `after_delete` | `self` | `` |  |
| `publish_update` | `self` | `` |  |
| `validate_exchange_rate` | `self` | `` |  |
| `set_status` | `self, update` | `` |  |
| `set_total_advance_paid` | `self` | `` |  |
| `update_claimed_amount` | `self` | `` |  |
| `set_pending_amount` | `self` | `` |  |
| `check_linked_payment_entry` | `self` | `` |  |





## Functions

### `make_bank_entry`
**Arguments:** `dt, dn`
**Decorators:** ``

**Docstring:**
```

```
### `get_advance_amount_advance_exchange_rate`
**Arguments:** `advance_account_currency, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_paying_amount_paying_exchange_rate`
**Arguments:** `payment_account, doc`
**Decorators:** ``

**Docstring:**
```

```
### `create_return_through_additional_salary`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_return_entry`
**Arguments:** `employee, company, employee_advance_name, return_amount, advance_account, currency, exchange_rate, mode_of_payment`
**Decorators:** ``

**Docstring:**
```

```
### `get_voucher_type`
**Arguments:** `mode_of_payment`
**Decorators:** ``

**Docstring:**
```

```

