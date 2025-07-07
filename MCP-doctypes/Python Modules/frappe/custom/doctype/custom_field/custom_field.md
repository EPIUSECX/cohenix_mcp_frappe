# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/custom/doctype/custom_field/custom_field.py`

## Classes

### `CustomField`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `set_fieldname` | `self` | `` |  |
| `before_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate_insert_after` | `self, meta` | `` |  |
| `get_permission_log_options` | `self, event` | `` |  |





## Functions

### `get_fields_label`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `create_custom_field_if_values_exist`
**Arguments:** `doctype, df`
**Decorators:** ``

**Docstring:**
```

```
### `create_custom_field`
**Arguments:** `doctype, df, ignore_validate, is_system_generated`
**Decorators:** ``

**Docstring:**
```

```
### `create_custom_fields`
**Arguments:** `custom_fields, ignore_validate, update`
**Decorators:** ``

**Docstring:**
```
Add / update multiple custom fields

:param custom_fields: example `{'Sales Invoice': [dict(fieldname='test')]}`
```
### `get_existing_custom_fields`
**Arguments:** `custom_fields`
**Decorators:** ``

**Docstring:**
```

```
### `rename_fieldname`
**Arguments:** `custom_field, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `_update_fieldname_references`
**Arguments:** `field, old_fieldname, new_fieldname`
**Decorators:** ``

**Docstring:**
```

```

