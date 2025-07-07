# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/types/exporter.py`

## Classes

### `TypeExporter`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doc` | `` |  |
| `export_types` | `self` | `` |  |
| `_replace_or_add_code` | `self, new_code` | `` |  |
| `_generate_code` | `self` | `` |  |
| `_create_fields_code_block` | `self` | `` |  |
| `_create_imports_block` | `self` | `` |  |
| `_get_doctype_imports` | `self, doctype` | `` |  |
| `_map_fieldtype` | `self, field` | `` |  |
| `_is_nullable` | `self, field` | `` | If value can be `None` |
| `_generic_parameters` | `self, field` | `` | If field is container type then return element type. |
| `_validate_code` | `code` | `staticmethod` | Make sure whatever code Frappe adds dynamically is valid python. |
| `_guess_indentation` | `self` | `` |  |





## Functions

No top-level functions found in this file.
