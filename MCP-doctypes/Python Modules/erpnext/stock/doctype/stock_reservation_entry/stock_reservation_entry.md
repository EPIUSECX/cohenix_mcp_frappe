# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_reservation_entry/stock_reservation_entry.py`

## Classes

### `StockReservationEntry`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `update_unreserved_qty_in_sre` | `self` | `` |  |
| `get_serial_batch_entries` | `self` | `` |  |
| `get_from_voucher_reservation_entries` | `self` | `` |  |
| `validate_amended_doc` | `self` | `` | Raises an exception if document is amended. |
| `validate_mandatory` | `self` | `` | Raises an exception if mandatory fields are not set. |
| `validate_group_warehouse` | `self` | `` | Raises an exception if `Warehouse` is a Group Warehouse. |
| `validate_uom_is_integer` | `self` | `` | Validates `Reserved Qty` with Stock UOM. |
| `set_reservation_based_on` | `self` | `` | Sets `Reservation Based On` based on `Has Serial No` and `Has Batch No`. |
| `validate_reservation_based_on_qty` | `self` | `` | Validates `Reserved Qty` when `Reservation Based On` is `Qty`. |
| `auto_reserve_serial_and_batch` | `self, based_on` | `` | Auto pick Serial and Batch Nos to reserve when `Reservation Based On` is `Serial and Batch`. |
| `validate_reservation_based_on_serial_and_batch` | `self` | `` | Validates `Reserved Qty`, `Serial and Batch Nos` when `Reservation Based On` is `Serial and Batch`. |
| `update_reserved_qty_in_voucher` | `self, reserved_qty_field, update_modified` | `` | Updates total reserved qty in the voucher. |
| `update_reserved_qty_in_pick_list` | `self, reserved_qty_field, update_modified` | `` | Updates total reserved qty in the Pick List. |
| `update_reserved_stock_in_bin` | `self` | `` | Updates `Reserved Stock` in Bin. |
| `update_status` | `self, status, update_modified` | `` | Updates status based on Voucher Qty, Reserved Qty and Delivered Qty. |
| `can_be_updated` | `self` | `` | Raises an exception if `Stock Reservation Entry` is not allowed to be updated. |
| `validate_with_allowed_qty` | `self, qty_to_be_reserved` | `` | Validates `Reserved Qty` with `Max Reserved Qty`. |
| `consume_serial_batch_for_material_transfer` | `self, row_wise_serial_batch` | `` |  |


### `StockReservation`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doc, items, kwargs, notify` | `` |  |
| `initialize_fields` | `self` | `` |  |
| `cancel_stock_reservation_entries` | `self, names` | `` | Cancels Stock Reservation Entries for the Voucher. |
| `make_stock_reservation_entries` | `self` | `` |  |
| `set_serial_batch` | `self, sre, serial_batch_bundles` | `` |  |
| `throw_stock_not_exists_error` | `self, idx, item_code, warehouse` | `` |  |
| `get_available_qty_to_reserve` | `self, item_code, warehouse, ignore_sre` | `` |  |
| `transfer_reservation_entries_to` | `self, docnames, from_doctype, to_doctype` | `` |  |
| `update_delivered_qty` | `self, data` | `` |  |
| `make_stock_reservation_entry` | `self, row` | `` |  |
| `get_reserved_entries` | `self, doctype, docnames` | `` |  |
| `get_items_to_reserve` | `self, docnames, from_doctype, to_doctype` | `` |  |





## Functions

### `validate_stock_reservation_settings`
**Arguments:** `voucher`
**Decorators:** ``

**Docstring:**
```
Raises an exception if `Stock Reservation` is not enabled or `Voucher Type` is not allowed.
```
### `get_available_qty_to_reserve`
**Arguments:** `item_code, warehouse, batch_no, ignore_sre`
**Decorators:** ``

**Docstring:**
```
Returns `Available Qty to Reserve (Actual Qty - Reserved Qty)` for Item, Warehouse and Batch combination.
```
### `get_available_serial_nos_to_reserve`
**Arguments:** `item_code, warehouse, has_batch_no, ignore_sre`
**Decorators:** ``

**Docstring:**
```
Returns Available Serial Nos to Reserve (Available Serial Nos - Reserved Serial Nos)` for Item, Warehouse and Batch combination.
```
### `get_sre_reserved_qty_for_item_and_warehouse`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```
Returns current `Reserved Qty` for Item and Warehouse combination.
```
### `get_sre_reserved_qty_for_items_and_warehouses`
**Arguments:** `item_code_list, warehouse_list`
**Decorators:** ``

**Docstring:**
```
Returns a dict like {("item_code", "warehouse"): "reserved_qty", ... }.
```
### `get_sre_reserved_qty_details_for_voucher`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```
Returns a dict like {"voucher_detail_no": "reserved_qty", ... }.
```
### `get_sre_reserved_warehouses_for_voucher`
**Arguments:** `voucher_type, voucher_no, voucher_detail_no`
**Decorators:** ``

**Docstring:**
```
Returns a list of warehouses where the stock is reserved for the provided voucher.
```
### `get_sre_reserved_qty_for_voucher_detail_no`
**Arguments:** `item_code, voucher_type, voucher_no, voucher_detail_no, ignore_sre, warehouse, from_voucher_detail_no`
**Decorators:** ``

**Docstring:**
```
Returns `Reserved Qty` against the Voucher.
```
### `get_sre_reserved_serial_nos_details`
**Arguments:** `item_code, warehouse, serial_nos`
**Decorators:** ``

**Docstring:**
```
Returns a dict of `Serial No` reserved in Stock Reservation Entry. The dict is like {serial_no: sre_name, ...}
```
### `get_sre_reserved_batch_nos_details`
**Arguments:** `item_code, warehouse, batch_nos`
**Decorators:** ``

**Docstring:**
```
Returns a dict of `Batch Qty` reserved in Stock Reservation Entry. The dict is like {batch_no: qty, ...}
```
### `get_sre_details_for_voucher`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```
Returns a list of SREs for the provided voucher.
```
### `get_serial_batch_entries_for_voucher`
**Arguments:** `sre_name`
**Decorators:** ``

**Docstring:**
```
Returns a list of `Serial and Batch Entries` for the provided voucher.
```
### `get_ssb_bundle_for_voucher`
**Arguments:** `sre`
**Decorators:** ``

**Docstring:**
```
Returns a new `Serial and Batch Bundle` against the provided SRE.
```
### `has_reserved_stock`
**Arguments:** `voucher_type, voucher_no, voucher_detail_no`
**Decorators:** ``

**Docstring:**
```
Returns True if there is any Stock Reservation Entry for the given voucher.
```
### `create_stock_reservation_entries_for_so_items`
**Arguments:** `sales_order, items_details, from_voucher_type, notify`
**Decorators:** ``

**Docstring:**
```
Creates Stock Reservation Entries for Sales Order Items.
```
### `cancel_stock_reservation_entries`
**Arguments:** `voucher_type, voucher_no, voucher_detail_no, from_voucher_type, from_voucher_no, from_voucher_detail_no, sre_list, notify`
**Decorators:** ``

**Docstring:**
```
Cancel Stock Reservation Entries.
```
### `get_stock_reservation_entries_for_voucher`
**Arguments:** `voucher_type, voucher_no, voucher_detail_no, fields, ignore_status`
**Decorators:** ``

**Docstring:**
```
Returns list of Stock Reservation Entries against a Voucher.
```
### `update_serial_batch_delivered_qty`
**Arguments:** `row, name, is_cancelled`
**Decorators:** ``

**Docstring:**
```

```

