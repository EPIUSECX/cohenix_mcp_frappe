# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/bom/test_bom.py`

## Classes

### `TestBOM`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_get_items` | `self` | `timeout` |  |
| `test_get_items_exploded` | `self` | `timeout` |  |
| `test_get_items_list` | `self` | `timeout` |  |
| `test_default_bom` | `self` | `timeout` |  |
| `test_update_bom_cost_in_all_boms` | `self` | `timeout` |  |
| `test_bom_cost` | `self` | `timeout` |  |
| `test_bom_cost_with_batch_size` | `self` | `timeout` |  |
| `test_bom_cost_multi_uom_multi_currency_based_on_price_list` | `self` | `timeout` |  |
| `test_bom_cost_multi_uom_based_on_valuation_rate` | `self` | `timeout` |  |
| `test_bom_cost_with_fg_based_operating_cost` | `self` | `timeout` |  |
| `test_subcontractor_sourced_item` | `self` | `timeout` |  |
| `test_bom_tree_representation` | `self` | `timeout` |  |
| `test_generated_variant_bom` | `self` | `timeout` |  |
| `test_bom_recursion_1st_level` | `self` | `timeout` | BOM should not allow BOM item again in child |
| `test_bom_recursion_transitive` | `self` | `timeout` |  |
| `test_bom_with_process_loss_item` | `self` | `timeout` |  |
| `test_bom_item_query` | `self` | `timeout` |  |
| `test_exclude_exploded_items_from_bom` | `self` | `timeout` |  |
| `test_valid_transfer_defaults` | `self` | `timeout` |  |
| `test_bom_name_length` | `self` | `timeout` | test >140 char names |
| `test_version_index` | `self` | `timeout` |  |
| `test_bom_versioning` | `self` | `timeout` |  |
| `test_clear_inpection_quality` | `self` | `timeout` |  |
| `test_bom_pricing_based_on_lpp` | `self` | `timeout` |  |
| `test_set_default_bom_for_item_having_single_bom` | `self` | `timeout` |  |
| `test_exploded_items_rate` | `self` | `timeout` |  |
| `test_bom_cost_update_flag` | `self` | `timeout` |  |
| `test_bom_with_service_item_cost` | `self` | `` |  |
| `test_do_not_include_manufacturing_and_fixed_items` | `self` | `` |  |
| `test_bom_raw_materials_stock_uom` | `self` | `` |  |





## Functions

### `get_default_bom`
**Arguments:** `item_code`
**Decorators:** ``

**Docstring:**
```

```
### `level_order_traversal`
**Arguments:** `node`
**Decorators:** ``

**Docstring:**
```

```
### `create_nested_bom`
**Arguments:** `tree, prefix, submit`
**Decorators:** ``

**Docstring:**
```
Helper function to create a simple nested bom from tree describing item names. (along with required items)
```
### `reset_item_valuation_rate`
**Arguments:** `item_code, warehouse_list, qty, rate`
**Decorators:** ``

**Docstring:**
```

```
### `create_bom_with_process_loss_item`
**Arguments:** `fg_item, bom_item, scrap_qty, scrap_rate, fg_qty, process_loss_percentage`
**Decorators:** ``

**Docstring:**
```

```
### `create_process_loss_bom_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_process_loss_bom_item`
**Arguments:** `item_tuple`
**Decorators:** ``

**Docstring:**
```

```

