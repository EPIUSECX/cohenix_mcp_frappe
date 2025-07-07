# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/bin/bin.py`

## Classes

### `Bin`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `recalculate_qty` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `set_projected_qty` | `self` | `` |  |
| `update_reserved_qty_for_production_plan` | `self, skip_project_qty_update, update_qty` | `` | Update qty reserved for production from Production Plan tables
in open production plan |
| `update_reserved_qty_for_for_sub_assembly` | `self` | `` |  |
| `update_reserved_qty_for_production` | `self` | `` | Update qty reserved for production from Production Item tables
in open work orders |
| `update_reserved_qty_for_sub_contracting` | `self, subcontract_doctype, update_qty` | `` |  |
| `update_reserved_stock` | `self` | `` | Update `Reserved Stock` on change in Reserved Qty of Stock Reservation Entry |





## Functions

### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_bin_details`
**Arguments:** `bin_name`
**Decorators:** ``

**Docstring:**
```

```
### `update_qty`
**Arguments:** `bin_name, args`
**Decorators:** ``

**Docstring:**
```

```
### `get_actual_qty`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```

