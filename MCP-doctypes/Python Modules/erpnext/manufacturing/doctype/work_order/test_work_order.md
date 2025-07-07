# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/work_order/test_work_order.py`

## Classes

### `TestWorkOrder`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `check_planned_qty` | `self` | `` |  |
| `test_over_production` | `self` | `` |  |
| `test_planned_operating_cost` | `self` | `` |  |
| `test_reserved_qty_for_partial_completion` | `self` | `` |  |
| `test_production_item` | `self` | `` |  |
| `test_reserved_qty_for_production_submit` | `self` | `` |  |
| `test_reserved_qty_for_production_cancel` | `self` | `` |  |
| `test_reserved_qty_for_production_on_stock_entry` | `self` | `` |  |
| `test_reserved_qty_for_production_closed` | `self` | `` |  |
| `test_backflush_qty_for_overpduction_manufacture` | `self` | `` |  |
| `test_reserved_qty_for_stopped_production` | `self` | `` |  |
| `test_scrap_material_qty` | `self` | `` |  |
| `test_allow_overproduction` | `self` | `` |  |
| `test_over_production_for_sales_order` | `self` | `` |  |
| `test_work_order_with_non_stock_item` | `self` | `` |  |
| `test_job_card` | `self` | `` |  |
| `test_work_order_material_transferred_qty_with_process_loss` | `self` | `` |  |
| `test_capcity_planning` | `self` | `` |  |
| `test_work_order_with_non_transfer_item` | `self` | `` |  |
| `test_cost_center_for_manufacture` | `self` | `` |  |
| `test_operation_time_with_batch_size` | `self` | `` |  |
| `test_batch_size_for_fg_item` | `self` | `` |  |
| `test_partial_material_consumption` | `self` | `` |  |
| `test_extra_material_transfer` | `self` | `` |  |
| `test_make_stock_entry_for_customer_provided_item` | `self` | `` |  |
| `test_valuation_rate_missing_on_make_stock_entry` | `self` | `` |  |
| `test_wo_completion_with_pl_bom` | `self` | `` |  |
| `test_job_card_scrap_item` | `self` | `` |  |
| `test_close_work_order` | `self` | `` |  |
| `test_fix_time_operations` | `self` | `` |  |
| `test_partial_manufacture_entries` | `self` | `` |  |
| `test_auto_batch_creation` | `self` | `` |  |
| `test_auto_serial_no_creation` | `self` | `` |  |
| `test_auto_serial_no_batch_creation` | `self` | `` |  |
| `get_serial_nos_for_fg` | `self, work_order` | `` |  |
| `test_manufacture_entry_mapped_idx_with_exploded_bom` | `self` | `` | Test if WO containing BOM with partial exploded items and scrap items, maps idx correctly. |
| `test_work_order_multiple_material_transfer` | `self` | `` | Test transferring multiple RMs in separate Stock Entries. |
| `test_backflushed_batch_raw_materials_based_on_transferred` | `self` | `` |  |
| `test_backflushed_serial_no_raw_materials_based_on_transferred` | `self` | `` |  |
| `test_backflushed_serial_no_batch_raw_materials_based_on_transferred` | `self` | `` |  |
| `test_backflushed_batch_raw_materials_based_on_transferred_autosabb` | `self` | `` |  |
| `test_backflushed_serial_no_raw_materials_based_on_transferred_autosabb` | `self` | `` |  |
| `test_backflushed_serial_no_batch_raw_materials_based_on_transferred_autosabb` | `self` | `` |  |
| `test_non_consumed_material_return_against_work_order` | `self` | `` |  |
| `test_workstation_type_for_work_order` | `self` | `` |  |
| `test_job_card_extra_qty` | `self` | `` |  |
| `test_operating_cost_account` | `self` | `` |  |
| `test_op_cost_and_scrap_based_on_sub_assemblies` | `self` | `` |  |
| `test_get_rm_cost_from_consumption_entry` | `self` | `` |  |
| `test_capcity_planning_for_workstation` | `self` | `` |  |
| `test_partial_material_consumption_with_batch` | `self` | `` |  |
| `test_disassemby_order` | `self` | `` |  |
| `test_disassembly_order_with_qty_behavior` | `self` | `` |  |
| `test_components_alternate_item_for_bom_based_manufacture_entry` | `self` | `` |  |
| `test_components_qty_for_bom_based_manufacture_entry` | `self` | `` |  |
| `test_components_as_per_bom_for_manufacture_entry` | `self` | `` |  |
| `test_wip_skip` | `self` | `` |  |
| `test_serial_no_status_for_stock_entry` | `self` | `` |  |
| `test_stock_reservation_for_serialized_raw_material` | `self` | `` |  |
| `test_stock_reservation_for_batched_raw_material` | `self` | `` |  |
| `test_auto_stock_reservation_for_batched_raw_material` | `self` | `` |  |
| `test_work_order_valuation_auto_pick` | `self` | `` |  |
| `test_operations_time_planning_calculation` | `self` | `` |  |





## Functions

### `make_stock_in_entries_and_get_batches`
**Arguments:** `rm_item, source_warehouse, wip_warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `make_operation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_workstation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `prepare_boms_for_sub_assembly_test`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `prepare_data_for_workstation_type_check`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `prepare_data_for_backflush_based_on_materials_transferred`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_job_card`
**Arguments:** `job_card, jc_qty, days`
**Decorators:** ``

**Docstring:**
```

```
### `get_scrap_item_details`
**Arguments:** `bom_no`
**Decorators:** ``

**Docstring:**
```

```
### `allow_overproduction`
**Arguments:** `fieldname, percentage`
**Decorators:** ``

**Docstring:**
```

```
### `make_wo_order_test_record`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

