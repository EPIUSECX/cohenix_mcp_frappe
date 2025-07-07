# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_transaction/test_bank_transaction.py`

## Classes

### `TestBankTransaction`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_linked_payments` | `self` | `` |  |
| `test_reconcile` | `self` | `` |  |
| `test_cancel_voucher` | `self` | `` |  |
| `test_debit_credit_output` | `self` | `` |  |
| `test_already_reconciled` | `self` | `` |  |
| `test_clear_sales_invoice` | `self` | `` |  |
| `test_matching_loan_repayment` | `self` | `if_lending_app_installed` |  |





## Functions

### `create_bank_account`
**Arguments:** `bank_name, gl_account, bank_account_name`
**Decorators:** ``

**Docstring:**
```

```
### `create_gl_account`
**Arguments:** `gl_account_name`
**Decorators:** ``

**Docstring:**
```

```
### `add_transactions`
**Arguments:** `bank_account`
**Decorators:** ``

**Docstring:**
```

```
### `add_vouchers`
**Arguments:** `gl_account`
**Decorators:** ``

**Docstring:**
```

```
### `create_loan_and_repayment`
**Arguments:** ``
**Decorators:** `if_lending_app_installed`

**Docstring:**
```

```

