# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_ledger_entry/stock_ledger_entry.py`

## Classes

### `StockFreezeError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `BackDatedStockTransaction`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InventoryDimensionNegativeStockError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `StockLedgerEntry`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` | Temporarily name doc for fast insertion
name will be changed using autoname options (in a scheduled job) |
| `validate` | `self` | `` |  |
| `set_posting_datetime` | `self` | `` |  |
| `validate_inventory_dimension_negative_stock` | `self` | `` |  |
| `get_available_qty_after_prev_transaction` | `self, dimension, dimension_value` | `` |  |
| `throw_validation_error` | `self, diff, dimension, dimension_value` | `` |  |
| `_get_inventory_dimensions` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `validate_mandatory` | `self` | `` |  |
| `validate_serial_batch_no_bundle` | `self` | `` |  |
| `throw_error_message` | `self, message, exception` | `` |  |
| `check_stock_frozen_date` | `self` | `` |  |
| `scrub_posting_time` | `self` | `` |  |
| `validate_batch` | `self` | `` |  |
| `validate_and_set_fiscal_year` | `self` | `` |  |
| `block_transactions_against_group_warehouse` | `self` | `` |  |
| `validate_with_last_transaction_posting_time` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |





## Functions

### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

