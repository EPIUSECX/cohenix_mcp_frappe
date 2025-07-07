# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_closing_entry/stock_closing_entry.py`

## Classes

### `StockClosingEntry`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_save` | `self` | `` |  |
| `set_status` | `self, save` | `` |  |
| `validate` | `self` | `` |  |
| `validate_duplicate` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `remove_stock_closing` | `self` | `` |  |
| `enqueue_job` | `self` | `` |  |
| `regenerate_closing_balance` | `self` | `` |  |
| `create_stock_closing_balance_entries` | `self` | `` |  |
| `get_prepared_data` | `self` | `` |  |


### `StockClosing`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, company, from_date, to_date` | `` |  |
| `get_stock_closing_entries` | `self` | `` |  |
| `update_fifo_queue` | `self, fifo_queue, actual_qty, posting_date` | `` |  |
| `get_initialized_entry` | `self, row, dimension_fields` | `` |  |
| `get_sle_entries` | `self` | `` |  |
| `get_entries` | `self, doctype, fields, filters` | `` | Get Stock Ledger Entries for the given filters. |
| `get_last_stock_closing_entry` | `self` | `` |  |
| `get_keys` | `self, row` | `` |  |
| `get_stock_closing_balance` | `self, kwargs, for_batch` | `` |  |





## Functions

### `prepare_closing_stock_balance`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```

