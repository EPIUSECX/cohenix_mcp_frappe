# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/material_request/material_request.py`

## Classes

### `MaterialRequest`
**Inherits:** `BuyingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `check_if_already_pulled` | `self` | `` |  |
| `validate_qty_against_so` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_pp_qty` | `self` | `` |  |
| `before_update_after_submit` | `self` | `` |  |
| `validate_material_request_type` | `self` | `` | Validate fields in accordance with selected type |
| `set_title` | `self` | `` | Set title as comma separated list of items |
| `on_submit` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `before_cancel` | `self` | `` |  |
| `check_modified_date` | `self` | `` |  |
| `update_status` | `self, status` | `` |  |
| `status_can_change` | `self, status` | `` | validates that `status` is acceptable for the present controller status
and throws an Exception if otherwise. |
| `on_cancel` | `self` | `` |  |
| `get_mr_items_ordered_qty` | `self, mr_items` | `` |  |
| `update_completed_qty` | `self, mr_items, update_modified` | `` |  |
| `update_requested_qty` | `self, mr_item_rows` | `` | update requested qty (before ordered_qty is updated) |
| `update_requested_qty_in_production_plan` | `self, cancel` | `` |  |





## Functions

### `update_completed_and_requested_qty`
**Arguments:** `stock_entry, method`
**Decorators:** ``

**Docstring:**
```

```
### `set_missing_values`
**Arguments:** `source, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_item`
**Arguments:** `obj, target, source_parent`
**Decorators:** ``

**Docstring:**
```

```
### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `update_status`
**Arguments:** `name, status`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_order`
**Arguments:** `source_name, target_doc, args`
**Decorators:** ``

**Docstring:**
```

```
### `make_request_for_quotation`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_order_based_on_supplier`
**Arguments:** `source_name, target_doc, args`
**Decorators:** ``

**Docstring:**
```

```
### `get_items_based_on_default_supplier`
**Arguments:** `supplier`
**Decorators:** ``

**Docstring:**
```

```
### `get_material_requests_based_on_supplier`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_supplier_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `make_supplier_quotation`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_stock_entry`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `raise_work_orders`
**Arguments:** `material_request`
**Decorators:** ``

**Docstring:**
```

```
### `create_pick_list`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_in_transit_stock_entry`
**Arguments:** `source_name, in_transit_warehouse`
**Decorators:** ``

**Docstring:**
```

```

