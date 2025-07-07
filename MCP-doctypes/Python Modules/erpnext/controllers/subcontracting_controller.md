# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/subcontracting_controller.py`

## Classes

### `SubcontractingController`
**Inherits:** `StockController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_rejected_warehouse` | `self` | `` |  |
| `remove_empty_rows` | `self` | `` |  |
| `set_items_conversion_factor` | `self` | `` |  |
| `validate_items` | `self` | `` |  |
| `__get_data_before_save` | `self` | `` |  |
| `__identify_change_in_item_table` | `self` | `` |  |
| `__get_backflush_based_on` | `self` | `` |  |
| `initialized_fields` | `self` | `` |  |
| `__get_subcontract_orders` | `self` | `` |  |
| `__get_pending_qty_to_receive` | `self` | `` | Get qty to be received against the subcontract order. |
| `__get_transferred_items` | `self` | `` |  |
| `__set_alternative_item_details` | `self, row` | `` |  |
| `__get_received_items` | `self, doctype` | `` |  |
| `__get_consumed_items` | `self, doctype, receipt_items` | `` |  |
| `__update_consumed_materials` | `self, doctype, return_consumed_items` | `` | Deduct the consumed materials from the available materials. |
| `get_available_materials` | `self` | `` | Get the available raw materials which has been transferred to the supplier.
available_materials = {
        (item_code, subcontracted_item, subcontract_order): {
                'qty': 1, 'serial_no': [ABC], 'batch_no': {'batch1': 1}, 'data': item_details
        }
} |
| `__remove_changed_rows` | `self` | `` |  |
| `__remove_serial_and_batch_bundle` | `self, item` | `` |  |
| `__get_materials_from_bom` | `self, item_code, bom_no, exploded_item` | `` |  |
| `__update_reserve_warehouse` | `self, row, item` | `` |  |
| `__set_alternative_item` | `self, bom_item` | `` |  |
| `__set_serial_and_batch_bundle` | `self, item_row, rm_obj, qty` | `` |  |
| `__get_batch_nos_for_bundle` | `self, qty, key` | `` |  |
| `__get_serial_nos_for_bundle` | `self, qty, key` | `` |  |
| `__add_supplied_item` | `self, item_row, bom_item, qty` | `` |  |
| `update_rate_for_supplied_items` | `self` | `` |  |
| `get_item_row` | `self, reference_name` | `` |  |
| `set_rate_for_supplied_items` | `self, rm_obj, item_row` | `` |  |
| `__set_batch_nos` | `self, bom_item, item_row, rm_obj, qty` | `` |  |
| `__set_consumed_qty` | `self, rm_obj, consumed_qty, required_qty` | `` |  |
| `__set_serial_nos` | `self, item_row, rm_obj` | `` |  |
| `__set_batch_no_as_per_qty` | `self, item_row, rm_obj, batch_no, qty` | `` |  |
| `__get_qty_based_on_material_transfer` | `self, item_row, transfer_item` | `` |  |
| `__set_supplied_items` | `self` | `` |  |
| `__set_rate_for_serial_and_batch_bundle` | `self` | `` |  |
| `__modify_serial_and_batch_bundle` | `self` | `` |  |
| `__get_bundle_to_modify` | `self, name` | `` |  |
| `__prepare_supplied_items` | `self` | `` |  |
| `__validate_batch_no` | `self, row, key` | `` |  |
| `__validate_serial_no` | `self, row, key` | `` |  |
| `__validate_supplied_items` | `self` | `` |  |
| `set_materials_for_subcontracted_items` | `self, raw_material_table` | `` |  |
| `create_raw_materials_supplied` | `self, raw_material_table` | `` |  |
| `__update_consumed_qty_in_subcontract_order` | `self, itemwise_consumed_qty` | `` |  |
| `set_consumed_qty_in_subcontract_order` | `self` | `` |  |
| `update_ordered_and_reserved_qty` | `self` | `` |  |
| `make_sl_entries_for_supplier_warehouse` | `self, sl_entries` | `` |  |
| `update_stock_ledger` | `self, allow_negative_stock, via_landed_cost_voucher` | `` |  |
| `get_supplied_items_cost` | `self, item_row_id, reset_outgoing_rate` | `` |  |
| `set_subcontracting_order_status` | `self` | `` |  |
| `calculate_additional_costs` | `self` | `` |  |
| `get_current_stock` | `self` | `` |  |
| `sub_contracted_items` | `self` | `property` |  |
| `update_requested_qty` | `self` | `` |  |





## Functions

### `get_item_details`
**Arguments:** `items`
**Decorators:** ``

**Docstring:**
```

```
### `get_pending_subcontracted_quantity`
**Arguments:** `po_name`
**Decorators:** ``

**Docstring:**
```

```
### `make_rm_stock_entry`
**Arguments:** `subcontract_order, rm_items, order_doctype, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `add_items_in_ste`
**Arguments:** `ste_doc, row, qty, rm_details, rm_detail_field, batch_no`
**Decorators:** ``

**Docstring:**
```

```
### `make_return_stock_entry_for_subcontract`
**Arguments:** `available_materials, order_doc, rm_details, order_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_materials_from_supplier`
**Arguments:** `subcontract_order, rm_details, order_doctype`
**Decorators:** ``

**Docstring:**
```

```

