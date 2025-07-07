# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/patches/v14_0/migrate_gl_to_payment_ledger.py`

## Classes

No classes found in this file.


## Functions

### `create_accounting_dimension_fields`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `generate_name_and_calculate_amount`
**Arguments:** `gl_entries, start, receivable_accounts`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `build_insert_query`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `insert_chunk_into_payment_ledger`
**Arguments:** `insert_query, gl_entries`
**Decorators:** ``

**Docstring:**
```

```
### `execute`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Description:
Migrate records from `tabGL Entry` to `tabPayment Ledger Entry`.
Patch is non-resumable. if patch failed or is terminatted abnormally, clear 'tabPayment Ledger Entry' table manually before re-running. Re-running is safe only during V13->V14 update.

Note: Post successful migration to V14, re-running is NOT-SAFE and SHOULD NOT be attempted.
```

