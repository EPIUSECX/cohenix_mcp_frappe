# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/repost_item_valuation/repost_item_valuation.py`

## Classes

### `RepostItemValuation`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `clear_old_logs` | `days` | `staticmethod` |  |
| `validate` | `self` | `` |  |
| `validate_period_closing_voucher` | `self` | `` |  |
| `reset_recreate_stock_ledgers` | `self` | `` |  |
| `get_closing_stock_balance` | `self` | `` |  |
| `get_max_period_closing_date` | `company` | `staticmethod` |  |
| `validate_accounts_freeze` | `self` | `` |  |
| `reset_field_values` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `set_company` | `self` | `` |  |
| `set_status` | `self, status, write` | `` |  |
| `clear_attachment` | `self` | `` |  |
| `on_submit` | `self` | `` | During tests reposts are executed immediately.

Exceptions:
        1. "Repost Item Valuation" document has self.flags.dont_run_in_test
        2. global flag frappe.flags.dont_execute_stock_reposts is set

        These flags are useful for asserting real time behaviour like quantity updates. |
| `before_cancel` | `self` | `` |  |
| `check_pending_repost_against_cancelled_transaction` | `self` | `` |  |
| `restart_reposting` | `self` | `` |  |
| `deduplicate_similar_repost` | `self` | `` | Deduplicate similar reposts based on item-warehouse-posting combination. |
| `recreate_stock_ledger_entries` | `self` | `` | Recreate Stock Ledger Entries for the transaction. |





## Functions

### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `repost`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `remove_attached_file`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```

```
### `repost_sl_entries`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `repost_gl_entries`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `_get_directly_dependent_vouchers`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Get stock vouchers that are directly affected by reposting
i.e. any one item-warehouse is present in the stock transaction
```
### `notify_error_to_stock_managers`
**Arguments:** `doc, traceback`
**Decorators:** ``

**Docstring:**
```

```
### `get_recipients`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `repost_entries`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Reposts 'Repost Item Valuation' entries in queue.
Called hourly via hooks.py.
```
### `get_repost_item_valuation_entries`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `in_configured_timeslot`
**Arguments:** `repost_settings, current_time`
**Decorators:** ``

**Docstring:**
```
Check if current time is in configured timeslot for reposting.
```
### `execute_repost_item_valuation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Execute repost item valuation via scheduler.
```

