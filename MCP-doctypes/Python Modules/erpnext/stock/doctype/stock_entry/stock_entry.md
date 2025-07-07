# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_entry/stock_entry.py`

## Classes

### `FinishedGoodError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `IncorrectValuationRateError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DuplicateEntryForWorkOrderError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OperationsNotCompleteError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `MaxSampleAlreadyRetainedError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `StockEntry`
**Inherits:** `StockController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `set_job_card_data` | `self` | `` |  |
| `validate_job_card_fg_item` | `self` | `` |  |
| `validate_job_card_item` | `self` | `` |  |
| `validate_work_order_status` | `self` | `` |  |
| `validate_purpose` | `self` | `` |  |
| `delete_linked_stock_entry` | `self` | `` |  |
| `delink_asset_repair_sabb` | `self` | `` |  |
| `set_transfer_qty` | `self` | `` |  |
| `update_cost_in_project` | `self` | `` |  |
| `validate_item` | `self` | `` |  |
| `validate_fg_completed_qty` | `self` | `` |  |
| `validate_difference_account` | `self` | `` |  |
| `validate_warehouse` | `self` | `` | perform various (sometimes conditional) validations on warehouse |
| `validate_work_order` | `self` | `` |  |
| `check_if_operations_completed` | `self` | `` | Check if Time Sheets are completed against before manufacturing to capture operating costs. |
| `check_duplicate_entry_for_work_order` | `self` | `` |  |
| `set_actual_qty` | `self` | `` |  |
| `validate_component_and_quantities` | `self` | `` |  |
| `get_matched_items` | `self, item_code` | `` |  |
| `get_stock_and_rate` | `self` | `` | Updates rate and availability of all the items.
Called from Update Rate and Availability button. |
| `calculate_rate_and_amount` | `self, reset_outgoing_rate, raise_error_if_no_rate` | `` |  |
| `set_basic_rate` | `self, reset_outgoing_rate, raise_error_if_no_rate` | `` | Set rate for outgoing, scrapped and finished items |
| `set_rate_for_outgoing_items` | `self, reset_outgoing_rate, raise_error_if_no_rate` | `` |  |
| `get_args_for_incoming_rate` | `self, item` | `` |  |
| `get_basic_rate_for_repacked_items` | `self, finished_item_qty, outgoing_items_cost` | `` |  |
| `get_basic_rate_for_manufactured_item` | `self, finished_item_qty, outgoing_items_cost` | `` |  |
| `distribute_additional_costs` | `self` | `` |  |
| `update_valuation_rate` | `self, reset_outgoing_rate` | `` |  |
| `set_total_incoming_outgoing_value` | `self` | `` |  |
| `set_total_amount` | `self` | `` |  |
| `set_stock_entry_type` | `self` | `` |  |
| `set_purpose_for_stock_entry` | `self` | `` |  |
| `make_serial_and_batch_bundle_for_outward` | `self` | `` |  |
| `validate_subcontract_order` | `self` | `` | Throw exception if more raw material is transferred against Subcontract Order than in
the raw materials supplied table |
| `validate_bom` | `self` | `` |  |
| `validate_purchase_order` | `self` | `` |  |
| `validate_closed_subcontracting_order` | `self` | `` |  |
| `mark_finished_and_scrap_items` | `self` | `` |  |
| `get_finished_item` | `self` | `` |  |
| `validate_finished_goods` | `self` | `` | 1. Check if FG exists (mfg, repack)
2. Check if Multiple FG Items are present (mfg)
3. Check FG Item and Qty against WO if present (mfg) |
| `update_stock_ledger` | `self, allow_negative_stock, via_landed_cost_voucher` | `` |  |
| `get_finished_item_row` | `self` | `` |  |
| `validate_serial_batch_bundle_type` | `self, serial_and_batch_bundle` | `` |  |
| `get_sle_for_source_warehouse` | `self, sl_entries, finished_item_row` | `` |  |
| `make_serial_and_batch_bundle_for_transfer` | `self` | `` |  |
| `get_sle_for_target_warehouse` | `self, sl_entries, finished_item_row` | `` |  |
| `get_gl_entries` | `self, warehouse_account` | `` |  |
| `set_gl_entries_for_landed_cost_voucher` | `self, gl_entries, warehouse_account` | `` |  |
| `update_work_order` | `self` | `` |  |
| `update_disassembled_order` | `self, is_cancel` | `` |  |
| `make_stock_reserve_for_wip_and_fg` | `self` | `` |  |
| `cancel_stock_reserve_for_wip_and_fg` | `self` | `` |  |
| `is_stock_reserve_for_work_order` | `self` | `` |  |
| `get_item_details` | `self, args, for_update` | `` |  |
| `set_items_for_stock_in` | `self` | `` |  |
| `get_items_for_disassembly` | `self, disassemble_qty, production_item` | `` | Get items for Disassembly Order |
| `get_items_from_manufacture_entry` | `self` | `` |  |
| `get_items` | `self, qty, production_item` | `` |  |
| `set_serial_batch_from_reserved_entry` | `self` | `` |  |
| `get_available_reserved_materials` | `self` | `` |  |
| `get_reserved_materials` | `self` | `` |  |
| `set_scrap_items` | `self` | `` |  |
| `set_process_loss_qty` | `self` | `` |  |
| `set_work_order_details` | `self` | `` |  |
| `load_items_from_bom` | `self` | `` |  |
| `set_batchwise_finished_goods` | `self, args, item` | `` |  |
| `add_batchwise_finished_good` | `self, batches, args, item` | `` |  |
| `add_finished_goods` | `self, args, item` | `` |  |
| `get_bom_raw_materials` | `self, qty` | `` |  |
| `get_bom_scrap_material` | `self, qty` | `` |  |
| `get_scrap_items_from_job_card` | `self` | `` |  |
| `get_completed_job_card_qty` | `self` | `` |  |
| `get_used_scrap_items` | `self` | `` |  |
| `get_unconsumed_raw_materials` | `self` | `` |  |
| `add_transfered_raw_materials_in_items` | `self` | `` |  |
| `update_batches_to_be_consume` | `self, batches, row, qty` | `` |  |
| `update_item_in_stock_entry_detail` | `self, row, item, qty` | `` |  |
| `get_serial_nos_based_on_transferred_batch` | `batch_no, serial_nos` | `staticmethod` |  |
| `get_pending_raw_materials` | `self, backflush_based_on` | `` | issue (item quantity) that is pending to issue or desire to transfer,
whichever is less |
| `get_pro_order_required_items` | `self, backflush_based_on` | `` | Gets Work Order Required Items only if Stock Entry purpose is **Material Transferred for Manufacture**. |
| `get_job_card_item_codes` | `self, job_card` | `` |  |
| `add_to_stock_entry_detail` | `self, item_dict, bom_no` | `` |  |
| `validate_with_material_request` | `self` | `` |  |
| `validate_batch` | `self` | `` |  |
| `update_subcontract_order_supplied_items` | `self` | `` |  |
| `update_transferred_qty` | `self` | `` |  |
| `update_quality_inspection` | `self` | `` |  |
| `set_material_request_transfer_status` | `self, status` | `` |  |
| `set_serial_no_batch_for_finished_good` | `self` | `` |  |
| `get_available_serial_nos` | `self` | `` |  |
| `update_subcontracting_order_status` | `self` | `` |  |
| `update_pick_list_status` | `self` | `` |  |
| `set_missing_values` | `self` | `` | Updates rate and availability of all the items of mapped doc. |





## Functions

### `move_sample_to_retention_warehouse`
**Arguments:** `company, items`
**Decorators:** ``

**Docstring:**
```

```
### `make_stock_in_entry`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_work_order_details`
**Arguments:** `work_order, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_operating_cost_per_unit`
**Arguments:** `work_order, bom_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_used_alternative_items`
**Arguments:** `subcontract_order, subcontract_order_field, work_order`
**Decorators:** ``

**Docstring:**
```

```
### `get_valuation_rate_for_finished_good_entry`
**Arguments:** `work_order`
**Decorators:** ``

**Docstring:**
```

```
### `get_uom_details`
**Arguments:** `item_code, uom, qty`
**Decorators:** ``

**Docstring:**
```
Returns dict `{"conversion_factor": [value], "transfer_qty": qty * [value]}`
:param args: dict with `item_code`, `uom` and `qty`
```
### `get_expired_batch_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_expired_batches`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_warehouse_details`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `validate_sample_quantity`
**Arguments:** `item_code, sample_quantity, qty, batch_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_supplied_items`
**Arguments:** `subcontract_order, rm_detail_field, subcontract_order_field`
**Decorators:** ``

**Docstring:**
```

```
### `get_items_from_subcontract_order`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_materials`
**Arguments:** `work_order`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_entry_data`
**Arguments:** `work_order`
**Decorators:** ``

**Docstring:**
```

```
### `create_serial_and_batch_bundle`
**Arguments:** `parent_doc, row, child, type_of_transaction`
**Decorators:** ``

**Docstring:**
```

```
### `get_batchwise_serial_nos`
**Arguments:** `item_code, row`
**Decorators:** ``

**Docstring:**
```

```

