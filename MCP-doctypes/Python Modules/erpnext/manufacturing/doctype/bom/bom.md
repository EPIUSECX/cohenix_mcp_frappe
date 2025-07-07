# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/bom/bom.py`

## Classes

### `BOMRecursionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `BOMTree`


**Docstring:**
```
Full tree representation of a BOM
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, name, is_bom, exploded_qty, qty` | `` |  |
| `__create_tree` | `self` | `` |  |
| `level_order_traversal` | `self` | `` | Get level order traversal of tree.
E.g. for following tree the traversal will return list of nodes in order from top to bottom.
BOM:
        - SubAssy1
                - item1
                - item2
        - SubAssy2
                - item3
        - item4

returns = [SubAssy1, item1, item2, SubAssy2, item3, item4] |
| `__str__` | `self` | `` |  |
| `__repr__` | `self, level` | `` |  |


### `BOM`
**Inherits:** `WebsiteGenerator`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `get_index_for_bom` | `self, existing_boms` | `` |  |
| `onload` | `self` | `` |  |
| `set_onload_for_muulti_level_bom` | `self` | `` |  |
| `get_next_version_index` | `existing_boms` | `staticmethod` |  |
| `validate` | `self` | `` |  |
| `set_default_uom` | `self` | `` |  |
| `get_context` | `self, context` | `` |  |
| `on_update` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `update_bom_creator_status` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `get_item_det` | `self, item_code` | `` |  |
| `get_routing` | `self` | `` |  |
| `set_bom_material_details` | `self` | `` |  |
| `set_bom_scrap_items_detail` | `self` | `` |  |
| `get_bom_material_detail` | `self, args` | `` | Get raw material details like uom, desc and rate |
| `validate_bom_currency` | `self, item` | `` |  |
| `get_rm_rate` | `self, arg` | `` | Get raw material rate as per selected method, if bom exists takes bom cost |
| `update_cost` | `self, update_parent, from_child_bom, update_hour_rate, save` | `` |  |
| `update_parent_cost` | `self` | `` |  |
| `get_bom_unitcost` | `self, bom_no` | `` |  |
| `manage_default_bom` | `self` | `` | Uncheck others if current one is selected as default or
check the current one as default if it the only bom for the selected item,
update default bom in item master |
| `clear_operations` | `self` | `` |  |
| `clear_inspection` | `self` | `` |  |
| `validate_main_item` | `self` | `` | Validate main FG item |
| `validate_currency` | `self` | `` |  |
| `update_stock_qty` | `self` | `` |  |
| `validate_uom_is_interger` | `self` | `` |  |
| `set_conversion_rate` | `self` | `` |  |
| `set_plc_conversion_rate` | `self` | `` |  |
| `validate_materials` | `self` | `` | Validate raw material entries |
| `check_recursion` | `self, bom_list` | `` | Check whether recursion occurs in any bom |
| `set_materials_based_on_operation_bom` | `self` | `` |  |
| `add_raw_materials` | `self, operation_row_id, items` | `` |  |
| `add_materials_from_bom` | `self, finished_good, bom_no, operation_row_id, qty` | `` |  |
| `traverse_tree` | `self, bom_list` | `` |  |
| `calculate_cost` | `self, save_updates, update_hour_rate` | `` | Calculate bom totals |
| `calculate_op_cost` | `self, update_hour_rate` | `` | Update workstation rate and calculates totals |
| `update_rate_and_time` | `self, row, update_hour_rate` | `` |  |
| `calculate_rm_cost` | `self, save` | `` | Fetch RM rate as per today's valuation rate and calculate totals |
| `calculate_sm_cost` | `self, save` | `` | Fetch RM rate as per today's valuation rate and calculate totals |
| `calculate_exploded_cost` | `self` | `` | Set exploded row cost from it's parent BOM. |
| `get_rm_rate_map` | `self` | `` | Create Raw Material-Rate map for Exploded Items. Fetch rate from Items table or Subassembly BOM. |
| `update_exploded_items` | `self, save` | `` | Update Flat BOM, following will be correct data |
| `get_exploded_items` | `self` | `` | Get all raw materials including items from child bom |
| `company_currency` | `self` | `` |  |
| `add_to_cur_exploded_items` | `self, args` | `` |  |
| `get_child_exploded_items` | `self, bom_no, stock_qty, operation` | `` | Add all items from Flat BOM of child BOM |
| `add_exploded_items` | `self, save` | `` | Add items to Flat BOM table |
| `validate_bom_links` | `self` | `` |  |
| `validate_transfer_against` | `self` | `` |  |
| `set_routing_operations` | `self` | `` |  |
| `validate_operations` | `self` | `` |  |
| `get_tree_representation` | `self` | `` | Get a complete tree representation preserving order of child items. |
| `set_process_loss_qty` | `self` | `` |  |
| `validate_scrap_items` | `self` | `` |  |





## Functions

### `get_bom_item_rate`
**Arguments:** `args, bom_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_valuation_rate`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```
1) Get average valuation rate from all warehouses
2) If no value, get last valuation rate from SLE
3) If no value, get valuation rate from Item
```
### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `get_bom_items_as_dict`
**Arguments:** `bom, company, qty, fetch_exploded, fetch_scrap_items, include_non_stock_items, fetch_qty_in_stock_uom`
**Decorators:** ``

**Docstring:**
```

```
### `get_bom_items`
**Arguments:** `bom, company, qty, fetch_exploded`
**Decorators:** ``

**Docstring:**
```

```
### `validate_bom_no`
**Arguments:** `item, bom_no`
**Decorators:** ``

**Docstring:**
```
Validate BOM No of sub-contracted items
```
### `get_children`
**Arguments:** `parent, is_root`
**Decorators:** ``

**Docstring:**
```

```
### `add_additional_cost`
**Arguments:** `stock_entry, work_order`
**Decorators:** ``

**Docstring:**
```

```
### `add_non_stock_items_cost`
**Arguments:** `stock_entry, work_order, expense_account`
**Decorators:** ``

**Docstring:**
```

```
### `add_operations_cost`
**Arguments:** `stock_entry, work_order, expense_account`
**Decorators:** ``

**Docstring:**
```

```
### `get_bom_diff`
**Arguments:** `bom1, bom2`
**Decorators:** ``

**Docstring:**
```

```
### `item_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `make_variant_bom`
**Arguments:** `source_name, bom_no, item, variant_items, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_op_cost_from_sub_assemblies`
**Arguments:** `bom_no, op_cost`
**Decorators:** ``

**Docstring:**
```

```
### `get_scrap_items_from_sub_assemblies`
**Arguments:** `bom_no, company, qty, scrap_items`
**Decorators:** ``

**Docstring:**
```

```

