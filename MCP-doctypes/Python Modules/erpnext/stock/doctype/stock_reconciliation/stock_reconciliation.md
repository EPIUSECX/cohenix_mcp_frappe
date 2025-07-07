# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_reconciliation/stock_reconciliation.py`

## Classes

### `OpeningEntryAccountError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `EmptyStockReconciliationItemsError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `StockReconciliation`
**Inherits:** `StockController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `validate_inventory_dimension` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `make_bundle_for_current_qty` | `self` | `` |  |
| `set_current_serial_and_batch_bundle` | `self, voucher_detail_no, save` | `` | Set Serial and Batch Bundle for each item |
| `get_bundle_for_specific_serial_batch` | `self, row` | `` |  |
| `has_change_in_serial_batch` | `self, row` | `` |  |
| `set_new_serial_and_batch_bundle` | `self` | `` |  |
| `update_existing_serial_and_batch_bundle` | `self, item` | `` |  |
| `remove_items_with_no_change` | `self` | `` |  |
| `calculate_difference_amount` | `self, item, item_dict` | `` |  |
| `validate_data` | `self` | `` |  |
| `validate_item` | `self, item_code, row` | `` |  |
| `validate_reserved_stock` | `self` | `` | Raises an exception if there is any reserved stock for the items in the Stock Reconciliation. |
| `update_stock_ledger` | `self, allow_negative_stock` | `` | find difference between current and expected entries
and create stock ledger entries based on the difference |
| `make_adjustment_entry` | `self, row, sl_entries` | `` |  |
| `get_sle_for_serialized_items` | `self, row, sl_entries` | `` |  |
| `update_valuation_rate_for_serial_no` | `self` | `` |  |
| `update_valuation_rate_for_serial_nos` | `self, row, serial_nos` | `` |  |
| `get_sle_for_items` | `self, row, serial_nos, current_bundle` | `` | Insert Stock Ledger Entries |
| `make_sle_on_cancel` | `self` | `` |  |
| `merge_similar_item_serial_nos` | `self, sl_entries` | `` |  |
| `get_gl_entries` | `self, warehouse_account` | `` |  |
| `validate_expense_account` | `self` | `` |  |
| `set_zero_value_for_customer_provided_items` | `self` | `` |  |
| `set_total_qty_and_amount` | `self` | `` |  |
| `get_items_for` | `self, warehouse` | `` |  |
| `submit` | `self` | `` |  |
| `cancel` | `self` | `` |  |
| `recalculate_current_qty` | `self, voucher_detail_no, sle_creation, add_new_sle` | `` |  |
| `add_missing_stock_ledger_entry` | `self, row, voucher_detail_no, sle_creation` | `` |  |
| `has_negative_stock_allowed` | `self` | `` |  |
| `get_current_qty_for_serial_or_batch` | `self, row` | `` |  |
| `get_current_qty_for_serial_nos` | `self, doc` | `` |  |
| `get_current_qty_for_batch_nos` | `self, doc` | `` |  |





## Functions

### `get_batch_qty_for_stock_reco`
**Arguments:** `item_code, warehouse, batch_no, posting_date, posting_time, voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_items`
**Arguments:** `warehouse, posting_date, posting_time, company, item_code, ignore_empty_stock`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_and_warehouses`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_items_for_stock_reco`
**Arguments:** `warehouse, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_data`
**Arguments:** `row, qty, valuation_rate, serial_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_itemwise_batch`
**Arguments:** `warehouse, posting_date, company, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_balance_for`
**Arguments:** `item_code, warehouse, posting_date, posting_time, batch_no, with_valuation_rate, inventory_dimensions_dict, row, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_difference_account`
**Arguments:** `purpose, company`
**Decorators:** ``

**Docstring:**
```

```

