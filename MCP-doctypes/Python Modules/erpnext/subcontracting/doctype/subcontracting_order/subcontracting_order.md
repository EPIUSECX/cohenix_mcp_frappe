# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/subcontracting/doctype/subcontracting_order/subcontracting_order.py`

## Classes

### `SubcontractingOrder`
**Inherits:** `SubcontractingController`


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
| `validate_purchase_order_for_subcontracting` | `self` | `` |  |
| `validate_service_items` | `self` | `` |  |
| `validate_supplied_items` | `self` | `` |  |
| `set_missing_values` | `self` | `` |  |
| `calculate_service_costs` | `self` | `` |  |
| `calculate_supplied_items_qty_and_amount` | `self` | `` |  |
| `calculate_items_qty_and_amount` | `self` | `` |  |
| `update_ordered_qty_for_subcontracting` | `self, sco_item_rows` | `` |  |
| `get_ordered_qty` | `item_code, warehouse` | `staticmethod` |  |
| `update_reserved_qty_for_subcontracting` | `self` | `` |  |
| `populate_items_table` | `self` | `` |  |
| `update_status` | `self, status, update_modified` | `` |  |
| `update_subcontracted_quantity_in_po` | `self, cancel` | `` |  |





## Functions

### `make_subcontracting_receipt`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_mapped_subcontracting_receipt`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_subcontracting_order_status`
**Arguments:** `sco, status`
**Decorators:** ``

**Docstring:**
```

```

