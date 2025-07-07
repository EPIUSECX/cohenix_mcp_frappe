# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_reconciliation_tool/bank_reconciliation_tool.py`

## Classes

### `BankReconciliationTool`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `get_bank_transactions`
**Arguments:** `bank_account, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_balance`
**Arguments:** `bank_account, till_date, company`
**Decorators:** ``

**Docstring:**
```

```
### `update_bank_transaction`
**Arguments:** `bank_transaction_name, reference_number, party_type, party`
**Decorators:** ``

**Docstring:**
```

```
### `create_journal_entry_bts`
**Arguments:** `bank_transaction_name, reference_number, reference_date, posting_date, entry_type, second_account, mode_of_payment, party_type, party, allow_edit`
**Decorators:** ``

**Docstring:**
```

```
### `create_payment_entry_bts`
**Arguments:** `bank_transaction_name, reference_number, reference_date, party_type, party, posting_date, mode_of_payment, project, cost_center, allow_edit`
**Decorators:** ``

**Docstring:**
```

```
### `auto_reconcile_vouchers`
**Arguments:** `bank_account, from_date, to_date, filter_by_reference_date, from_reference_date, to_reference_date`
**Decorators:** ``

**Docstring:**
```

```
### `start_auto_reconcile`
**Arguments:** `bank_transactions, from_date, to_date, filter_by_reference_date, from_reference_date, to_reference_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_auto_reconcile_message`
**Arguments:** `partially_reconciled, reconciled`
**Decorators:** ``

**Docstring:**
```
Returns alert message and indicator for auto reconciliation depending on result state.
```
### `reconcile_vouchers`
**Arguments:** `bank_transaction_name, vouchers`
**Decorators:** ``

**Docstring:**
```

```
### `get_linked_payments`
**Arguments:** `bank_transaction_name, document_types, from_date, to_date, filter_by_reference_date, from_reference_date, to_reference_date`
**Decorators:** ``

**Docstring:**
```

```
### `subtract_allocations`
**Arguments:** `gl_account, vouchers`
**Decorators:** ``

**Docstring:**
```
Look up & subtract any existing Bank Transaction allocations
```
### `get_allocated_amount`
**Arguments:** `voucher_allocated_amounts, voucher, gl_account`
**Decorators:** ``

**Docstring:**
```

```
### `check_matching`
**Arguments:** `bank_account, company, transaction, document_types, from_date, to_date, filter_by_reference_date, from_reference_date, to_reference_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_queries`
**Arguments:** `bank_account, company, transaction, document_types, from_date, to_date, filter_by_reference_date, from_reference_date, to_reference_date, exact_match, common_filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_matching_queries`
**Arguments:** `bank_account, company, transaction, document_types, exact_match, account_from_to, from_date, to_date, filter_by_reference_date, from_reference_date, to_reference_date, common_filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_bt_matching_query`
**Arguments:** `exact_match, transaction`
**Decorators:** ``

**Docstring:**
```

```
### `get_pe_matching_query`
**Arguments:** `exact_match, account_from_to, transaction, from_date, to_date, filter_by_reference_date, from_reference_date, to_reference_date, common_filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_je_matching_query`
**Arguments:** `exact_match, transaction, from_date, to_date, filter_by_reference_date, from_reference_date, to_reference_date, common_filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_si_matching_query`
**Arguments:** `exact_match, currency, common_filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_pi_matching_query`
**Arguments:** `exact_match, currency, common_filters`
**Decorators:** ``

**Docstring:**
```

```

