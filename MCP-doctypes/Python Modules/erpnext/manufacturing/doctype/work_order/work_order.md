# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/work_order/work_order.py`

## Classes

### `OverProductionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CapacityError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `StockOverProductionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OperationTooLongError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ItemHasVariantError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SerialNoQtyError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `WorkOrder`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `show_create_job_card_button` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `validate_fg_warehouse_for_reservation` | `self` | `` |  |
| `set_reserve_stock` | `self` | `` |  |
| `enable_auto_reserve_stock` | `self` | `` |  |
| `set_warehouses` | `self` | `` |  |
| `reset_use_multi_level_bom` | `self` | `` |  |
| `validate_workstation_type` | `self` | `` |  |
| `validate_sales_order` | `self` | `` |  |
| `check_sales_order_on_hold_or_close` | `self` | `` |  |
| `set_default_warehouse` | `self` | `` |  |
| `check_wip_warehouse_skip` | `self` | `` |  |
| `validate_warehouse_belongs_to_company` | `self` | `` |  |
| `calculate_operating_cost` | `self` | `` |  |
| `validate_work_order_against_so` | `self` | `` |  |
| `update_status` | `self, status` | `` | Update status of work order if unknown |
| `get_status` | `self, status` | `` | Return the status based on stock entries against this work order |
| `update_work_order_qty` | `self` | `` | Update **Manufactured Qty** and **Material Transferred for Qty** in Work Order
based on Stock Entry |
| `update_disassembled_qty` | `self, qty, is_cancel` | `` |  |
| `get_transferred_or_manufactured_qty` | `self, purpose` | `` |  |
| `set_process_loss_qty` | `self` | `` |  |
| `update_production_plan_status` | `self` | `` |  |
| `validate_warehouse` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `update_stock_reservation` | `self` | `` |  |
| `create_serial_no_batch_no` | `self` | `` |  |
| `create_batch_for_finished_good` | `self` | `` |  |
| `delete_auto_created_batch_and_serial_no` | `self` | `` |  |
| `make_serial_nos` | `self, args` | `` |  |
| `create_job_card` | `self` | `` |  |
| `prepare_data_for_job_card` | `self, row, idx, plan_days, enable_capacity_planning` | `` |  |
| `set_operation_start_end_time` | `self, row, idx` | `` | Set start and end time for given operation. If first operation, set start as
`planned_start_date`, else add time diff to end time of earlier operation. |
| `validate_cancel` | `self` | `` |  |
| `update_planned_qty` | `self` | `` |  |
| `set_produced_qty_for_sub_assembly_item` | `self` | `` |  |
| `update_ordered_qty` | `self` | `` |  |
| `update_work_order_qty_in_so` | `self` | `` |  |
| `update_work_order_qty_in_combined_so` | `self` | `` |  |
| `update_completed_qty_in_material_request` | `self` | `` |  |
| `set_work_order_operations` | `self` | `` | Fetch operations from BOM and set in 'Work Order' |
| `calculate_time` | `self` | `` |  |
| `get_holidays` | `self, workstation` | `` |  |
| `update_operation_status` | `self` | `` |  |
| `set_actual_dates` | `self` | `` |  |
| `set_lead_time` | `self` | `` |  |
| `delete_job_card` | `self` | `` |  |
| `validate_production_item` | `self` | `` |  |
| `validate_qty` | `self` | `` |  |
| `validate_transfer_against` | `self` | `` |  |
| `validate_operation_time` | `self` | `` |  |
| `update_required_items` | `self` | `` | update bin reserved_qty_for_production
called from Stock Entry for production, after submit, cancel |
| `update_reserved_qty_for_production` | `self, items` | `` | update reserved_qty_for_production in bins |
| `get_items_and_operations_from_bom` | `self` | `` |  |
| `set_available_qty` | `self` | `` |  |
| `set_required_items` | `self, reset_only_qty, reset_source_warehouse` | `` | set required_items for production to keep track of reserved qty |
| `update_transferred_qty_for_required_items` | `self` | `` |  |
| `update_qty_in_stock_reservation` | `self, row, transferred_qty, row_wise_serial_batch` | `` |  |
| `update_returned_qty` | `self` | `` |  |
| `update_consumed_qty_for_required_items` | `self` | `` | Update consumed qty from submitted stock entries
against a work order for each stock item |
| `update_consumed_qty_in_stock_reservation` | `self, item, consumed_qty, wip_warehouse` | `` |  |
| `validate_reserved_qty` | `self` | `` |  |
| `make_bom` | `self` | `` |  |
| `set_reserved_qty_for_wip_and_fg` | `self, stock_entry` | `` |  |
| `get_list_of_materials_for_reservation` | `self, stock_entry` | `` |  |
| `get_finished_goods_for_reservation` | `self, stock_entry` | `` |  |
| `get_wo_details` | `self` | `` |  |
| `get_so_details` | `self` | `` |  |
| `get_voucher_details` | `self, stock_entry` | `` |  |
| `cancel_reserved_qty_for_wip_and_fg` | `self, ste_doc` | `` |  |
| `remove_additional_items` | `self, stock_entry` | `` |  |
| `add_additional_items` | `self, stock_entry` | `` |  |





## Functions

### `make_stock_reservation_entries`
**Arguments:** `doc, items, table_name, is_transfer, notify`
**Decorators:** ``

**Docstring:**
```

```
### `cancel_stock_reservation_entries`
**Arguments:** `doc, sre_list`
**Decorators:** ``

**Docstring:**
```

```
### `get_sre_details`
**Arguments:** `work_order`
**Decorators:** ``

**Docstring:**
```

```
### `get_consumed_qty`
**Arguments:** `work_order, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_bom_operations`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_details`
**Arguments:** `item, project, skip_bom_info, throw`
**Decorators:** ``

**Docstring:**
```

```
### `make_work_order`
**Arguments:** `bom_no, item, qty, project, variant_items, use_multi_level_bom`
**Decorators:** ``

**Docstring:**
```

```
### `add_variant_item`
**Arguments:** `variant_items, wo_doc, bom_no, table_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_template_rm_item`
**Arguments:** `wo_doc, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `check_if_scrap_warehouse_mandatory`
**Arguments:** `bom_no`
**Decorators:** ``

**Docstring:**
```

```
### `set_work_order_ops`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `make_stock_entry`
**Arguments:** `work_order_id, purpose, qty, target_warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_warehouse`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `stop_unstop`
**Arguments:** `work_order, status`
**Decorators:** ``

**Docstring:**
```
Called from client side on Stop/Unstop event
```
### `query_sales_order`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `make_job_card`
**Arguments:** `work_order, operations`
**Decorators:** ``

**Docstring:**
```

```
### `get_operation_details`
**Arguments:** `name, work_order`
**Decorators:** ``

**Docstring:**
```

```
### `close_work_order`
**Arguments:** `work_order, status`
**Decorators:** ``

**Docstring:**
```

```
### `split_qty_based_on_batch_size`
**Arguments:** `wo_doc, row, qty`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_nos_for_job_card`
**Arguments:** `row, wo_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_nos_for_work_order`
**Arguments:** `work_order, production_item`
**Decorators:** ``

**Docstring:**
```

```
### `validate_operation_data`
**Arguments:** `row`
**Decorators:** ``

**Docstring:**
```

```
### `create_job_card`
**Arguments:** `work_order, row, enable_capacity_planning, auto_create`
**Decorators:** ``

**Docstring:**
```

```
### `get_work_order_operation_data`
**Arguments:** `work_order, operation, workstation`
**Decorators:** ``

**Docstring:**
```

```
### `create_pick_list`
**Arguments:** `source_name, target_doc, for_qty`
**Decorators:** ``

**Docstring:**
```

```
### `get_reserved_qty_for_production`
**Arguments:** `item_code, warehouse, non_completed_production_plans, check_production_plan`
**Decorators:** ``

**Docstring:**
```
Get total reserved quantity for any item in specified warehouse
```
### `make_stock_return_entry`
**Arguments:** `work_order`
**Decorators:** ``

**Docstring:**
```

```
### `get_row_wise_serial_batch`
**Arguments:** `work_order, purpose`
**Decorators:** ``

**Docstring:**
```

```

