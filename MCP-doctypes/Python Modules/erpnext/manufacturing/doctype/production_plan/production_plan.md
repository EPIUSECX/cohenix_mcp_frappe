# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/production_plan/production_plan.py`

## Classes

### `ProductionPlan`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `enable_auto_reserve_stock` | `self` | `` |  |
| `validate_material_request_type` | `self` | `` |  |
| `validate_sales_orders` | `self, sales_order` | `` |  |
| `set_pending_qty_in_row_without_reference` | `self` | `` | Set Pending Qty in independent rows (not from SO or MR). |
| `calculate_total_planned_qty` | `self` | `` |  |
| `validate_data` | `self` | `` |  |
| `_rename_temporary_references` | `self` | `` | po_items and sub_assembly_items items are both constructed client side without saving.

Attempt to fix linkages by using temporary names to map final row names. |
| `get_open_sales_orders` | `self` | `` | Pull sales orders  which are pending to deliver based on criteria selected |
| `add_so_in_table` | `self, open_so` | `` | Add sales orders in the table |
| `get_pending_material_requests` | `self` | `` | Pull Material Requests that are pending based on criteria selected |
| `add_mr_in_table` | `self, pending_mr` | `` | Add Material Requests in the table |
| `combine_so_items` | `self` | `` |  |
| `get_items` | `self` | `` |  |
| `get_so_mr_list` | `self, field, table` | `` | Returns a list of Sales Orders or Material Requests from the respective tables |
| `get_bom_item_condition` | `self` | `` | Check if Item or if its Template has a BOM. |
| `get_so_items` | `self` | `` |  |
| `get_mr_items` | `self` | `` |  |
| `add_items` | `self, items` | `` |  |
| `add_pp_ref` | `self, refs` | `` |  |
| `calculate_total_produced_qty` | `self` | `` |  |
| `update_produced_pending_qty` | `self, produced_qty, production_plan_item` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `update_stock_reservation` | `self` | `` |  |
| `update_sales_order` | `self` | `` |  |
| `get_so_wise_planned_qty` | `sales_orders` | `staticmethod` |  |
| `update_bin_qty` | `self` | `` |  |
| `delete_draft_work_order` | `self` | `` |  |
| `set_status` | `self, close, update_bin` | `` |  |
| `update_ordered_status` | `self` | `` |  |
| `update_requested_status` | `self` | `` |  |
| `get_production_items` | `self` | `` |  |
| `make_work_order` | `self` | `` |  |
| `make_work_order_for_finished_goods` | `self, wo_list, default_warehouses` | `` |  |
| `make_work_order_for_subassembly_items` | `self, wo_list, subcontracted_po, default_warehouses` | `` |  |
| `prepare_data_for_sub_assembly_items` | `self, row, wo_data` | `` |  |
| `make_subcontracted_purchase_order` | `self, subcontracted_po, purchase_orders` | `` |  |
| `show_list_created_message` | `self, doctype, doc_list` | `` |  |
| `create_work_order` | `self, item` | `` |  |
| `validate_mr_subcontracted` | `self` | `` |  |
| `make_material_request` | `self` | `` |  |
| `get_sub_assembly_items` | `self, manufacturing_type` | `` | Fetch sub assembly items and optionally combine them. |
| `set_sub_assembly_items_based_on_level` | `self, row, bom_data, manufacturing_type` | `` | Modify bom_data, set additional details. |
| `set_default_supplier_for_subcontracting_order` | `self` | `` |  |
| `combine_subassembly_items` | `self, sub_assembly_items_store` | `` | Aggregate if same: Item, Warehouse, Inhouse/Outhouse Manu.g, BOM No. |
| `all_items_completed` | `self` | `` |  |





## Functions

### `download_raw_materials`
**Arguments:** `doc, warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `get_exploded_items`
**Arguments:** `item_details, company, bom_no, include_non_stock_items, planned_qty, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_uom_conversion_factor`
**Arguments:** `item_code, uom`
**Decorators:** ``

**Docstring:**
```

```
### `get_subitems`
**Arguments:** `doc, data, item_details, bom_no, company, include_non_stock_items, include_subcontracted_items, parent_qty, planned_qty`
**Decorators:** ``

**Docstring:**
```

```
### `get_material_request_items`
**Arguments:** `doc, row, sales_order, company, ignore_existing_ordered_qty, include_safety_stock, warehouse, bin_dict`
**Decorators:** ``

**Docstring:**
```

```
### `get_sales_orders`
**Arguments:** `self`
**Decorators:** ``

**Docstring:**
```

```
### `get_bin_details`
**Arguments:** `row, company, for_warehouse, all_warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_so_details`
**Arguments:** `sales_order`
**Decorators:** ``

**Docstring:**
```

```
### `get_warehouse_list`
**Arguments:** `warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `get_items_for_material_requests`
**Arguments:** `doc, warehouses, get_parent_warehouse_data`
**Decorators:** ``

**Docstring:**
```

```
### `get_materials_from_other_locations`
**Arguments:** `item, warehouses, new_mr_items, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_data`
**Arguments:** `item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_sub_assembly_items`
**Arguments:** `sub_assembly_items, bin_details, bom_no, bom_data, to_produce_qty, company, warehouse, indent, skip_available_sub_assembly_item`
**Decorators:** ``

**Docstring:**
```

```
### `set_default_warehouses`
**Arguments:** `row, default_warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `get_reserved_qty_for_production_plan`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_non_completed_production_plans`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_raw_materials_of_sub_assembly_items`
**Arguments:** `existing_sub_assembly_items, item_details, company, bom_no, include_non_stock_items, sub_assembly_items, planned_qty`
**Decorators:** ``

**Docstring:**
```

```
### `sales_order_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_reserved_qty_for_sub_assembly`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `make_stock_reservation_entries`
**Arguments:** `doc, items, table_name, notify`
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

