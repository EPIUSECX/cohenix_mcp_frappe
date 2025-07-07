# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/custom/doctype/property_setter/property_setter.py`

## Classes

### `PropertySetter`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate_fieldtype_change` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `get_permission_log_options` | `self, event` | `` |  |





## Functions

### `make_property_setter`
**Arguments:** `doctype, fieldname, property, value, property_type, for_doctype, validate_fields_for_doctype, is_system_generated`
**Decorators:** ``

**Docstring:**
```

```
### `delete_property_setter`
**Arguments:** `doc_type, property, field_name, row_name`
**Decorators:** ``

**Docstring:**
```
delete other property setters on this, if this is new
```

