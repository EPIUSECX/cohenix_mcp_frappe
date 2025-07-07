# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/inventory_dimension/inventory_dimension.py`

## Classes

### `DoNotChangeError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CanNotBeChildDoc`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CanNotBeDefaultDimension`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InventoryDimension`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `has_stock_ledger` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `set_type_of_transaction` | `self` | `` |  |
| `set_fetch_value_from` | `self` | `` |  |
| `do_not_update_document` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `delete_custom_fields` | `self` | `` |  |
| `reset_value` | `self` | `` |  |
| `validate_reference_document` | `self` | `` |  |
| `set_source_and_target_fieldname` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `get_insert_after_fieldname` | `doctype` | `staticmethod` |  |
| `get_dimension_fields` | `self, doctype` | `` |  |
| `add_custom_fields` | `self` | `` |  |
| `add_transfer_field` | `self, doctype, dimension_fields` | `` |  |





## Functions

### `field_exists`
**Arguments:** `doctype, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `get_inventory_documents`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_evaluated_inventory_dimension`
**Arguments:** `doc, sl_dict, parent_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_document_wise_inventory_dimensions`
**Arguments:** `doctype`
**Decorators:** `request_cache`

**Docstring:**
```

```
### `get_inventory_dimensions`
**Arguments:** ``
**Decorators:** `request_cache`

**Docstring:**
```

```
### `delete_dimension`
**Arguments:** `dimension`
**Decorators:** ``

**Docstring:**
```

```
### `get_parent_fields`
**Arguments:** `child_doctype, dimension_name`
**Decorators:** ``

**Docstring:**
```

```

