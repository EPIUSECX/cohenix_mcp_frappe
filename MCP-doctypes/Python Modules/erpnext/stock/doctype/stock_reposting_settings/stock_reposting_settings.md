# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_reposting_settings/stock_reposting_settings.py`

## Classes

### `StockRepostingSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `set_minimum_reposting_time_slot` | `self` | `` | Ensure that timeslot for reposting is at least 12 hours. |
| `convert_to_item_wh_reposting` | `self` | `` | Convert Transaction reposting to Item Warehouse based reposting if Item Based Reposting has enabled. |





## Functions

### `get_reposting_entries`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_ledgers`
**Arguments:** `vouchers`
**Decorators:** ``

**Docstring:**
```

```
### `create_repost_item_valuation`
**Arguments:** `item_code, warehouse, posting_date`
**Decorators:** ``

**Docstring:**
```

```

