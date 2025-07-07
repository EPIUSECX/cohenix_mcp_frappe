# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/supplier_quotation/supplier_quotation.py`

## Classes

### `SupplierQuotation`
**Inherits:** `BuyingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `set_has_unit_price_items` | `self` | `` | If permitted in settings and any item has 0 qty, the SQ has unit price items. |
| `validate_with_previous_doc` | `self` | `` |  |
| `validate_valid_till` | `self` | `` |  |
| `update_rfq_supplier_status` | `self, include_me` | `` |  |





## Functions

### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_order`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_invoice`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_quotation`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_expired_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

