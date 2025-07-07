# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/report/stock_balance/stock_balance.py`

## Classes

### `StockBalanceFilter`
**Inherits:** `TypedDict`


**Docstring:**
```

```

**Methods:**
No methods found.

### `StockBalanceReport`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, filters` | `` |  |
| `set_company_currency` | `self` | `` |  |
| `run` | `self` | `` |  |
| `prepare_opening_stock` | `self` | `` |  |
| `get_entries_from_stock_closing_balance` | `self` | `` |  |
| `filter_fields` | `self` | `` |  |
| `prepare_sle_query` | `self` | `` |  |
| `prepare_item_warehouse_map_for_current_period` | `self` | `` |  |
| `prepare_new_data` | `self` | `` |  |
| `get_sre_reserved_qty_details` | `self` | `` |  |
| `prepare_item_warehouse_map` | `self, entry, group_by_key` | `` |  |
| `initialize_data` | `self, group_by_key, entry` | `` |  |
| `get_group_by_key` | `self, row` | `` |  |
| `apply_inventory_dimensions_filters` | `self, query, sle` | `` |  |
| `apply_warehouse_filters` | `self, query, sle` | `` |  |
| `apply_items_filters` | `self, query, item_table` | `` |  |
| `apply_date_filters` | `self, query, sle` | `` |  |
| `get_columns` | `self` | `` |  |
| `add_additional_uom_columns` | `self` | `` |  |
| `get_itemwise_conversion_factor` | `self` | `` |  |
| `get_variant_values_for` | `self` | `` | Returns variant values for items. |
| `get_opening_vouchers` | `self` | `` |  |
| `get_inventory_dimension_fields` | `` | `staticmethod` |  |
| `get_opening_fifo_queue` | `report_data` | `staticmethod` |  |





## Functions

### `execute`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `filter_items_with_no_transactions`
**Arguments:** `iwb_map, float_precision, inventory_dimensions`
**Decorators:** ``

**Docstring:**
```

```
### `get_variants_attributes`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return all item variant attributes.
```

