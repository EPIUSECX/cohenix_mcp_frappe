# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/overrides/employee_payment_entry.py`

## Classes

### `EmployeePaymentEntry`
**Inherits:** `PaymentEntry`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_valid_reference_doctypes` | `self` | `` |  |
| `set_missing_ref_details` | `self, force, update_ref_details_only_for, reference_exchange_details` | `` |  |





## Functions

### `get_payment_entry_for_employee`
**Arguments:** `dt, dn, party_amount, bank_account, bank_amount`
**Decorators:** ``

**Docstring:**
```
Function to make Payment Entry for Employee Advance, Gratuity, Expense Claim, Leave Encashment
```
### `get_party_account`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_grand_total_and_outstanding_amount`
**Arguments:** `doc, party_amount, party_account_currency`
**Decorators:** ``

**Docstring:**
```

```
### `get_paid_amount_and_received_amount`
**Arguments:** `doc, party_account_currency, bank, outstanding_amount, payment_type, bank_amount`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_reference_details`
**Arguments:** `reference_doctype, reference_name, party_account_currency, party_type, party`
**Decorators:** ``

**Docstring:**
```

```
### `get_reference_details_for_employee`
**Arguments:** `reference_doctype, reference_name, party_account_currency`
**Decorators:** ``

**Docstring:**
```
Returns payment reference details for employee related doctypes:
Employee Advance, Expense Claim, Gratuity, Leave Encashment
```
### `get_total_amount_and_exchange_rate`
**Arguments:** `ref_doc, party_account_currency, company_currency`
**Decorators:** ``

**Docstring:**
```

```

