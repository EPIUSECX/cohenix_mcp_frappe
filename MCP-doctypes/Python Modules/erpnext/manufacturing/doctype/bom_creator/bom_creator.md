# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/bom_creator/bom_creator.py`

## Classes

### `BOMCreator`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_save` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_items` | `self` | `` |  |
| `set_status` | `self, save` | `` |  |
| `set_status_completed` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `set_conversion_factor` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `set_reference_id` | `self` | `` |  |
| `add_boms` | `self` | `` |  |
| `set_rate_for_items` | `self` | `` |  |
| `get_raw_material_cost` | `self, fg_item, amount` | `` |  |
| `set_is_expandable` | `self` | `` |  |
| `validate_fields` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `enqueue_create_boms` | `self` | `` |  |
| `create_boms` | `self` | `` | Sample data structure of production_item_wise_rm
production_item_wise_rm = {
        (fg_item_code, name): {
                "items": [],
                "bom_no": "",
                "fg_item_data": {}
        }
} |
| `create_bom` | `self, row, production_item_wise_rm` | `` |  |
| `has_operations` | `self` | `` |  |
| `get_default_bom` | `self, item_code` | `` |  |





## Functions

### `get_children`
**Arguments:** `doctype, parent`
**Decorators:** ``

**Docstring:**
```

```
### `add_item`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `add_sub_assembly`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_item_details`
**Arguments:** `item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_parent_row_no`
**Arguments:** `doc, name`
**Decorators:** ``

**Docstring:**
```

```
### `delete_node`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `edit_bom_creator`
**Arguments:** `doctype, docname, data, parent`
**Decorators:** ``

**Docstring:**
```

```

