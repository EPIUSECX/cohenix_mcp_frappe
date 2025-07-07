# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/deprecation_dumpster.py`

## Classes

### `ERPNextDeprecationError`
**Inherits:** `Warning`


**Docstring:**
```
Deprecated feature in current version.

Raises an error by default but can be configured via PYTHONWARNINGS in an emergency.
```

**Methods:**
No methods found.

### `ERPNextDeprecationWarning`
**Inherits:** `Warning`


**Docstring:**
```
Deprecated feature in next version
```

**Methods:**
No methods found.

### `PendingERPNextDeprecationWarning`
**Inherits:** `ERPNextDeprecationWarning`


**Docstring:**
```
Deprecated feature in develop beyond next version.

Warning ignored by default.

The deprecation decision may still be reverted or deferred at this stage.
Regardless, using the new variant is encouraged and stable.
```

**Methods:**
No methods found.

### `V15ERPNextDeprecationWarning`
**Inherits:** `ERPNextDeprecationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `V16ERPNextDeprecationWarning`
**Inherits:** `ERPNextDeprecationWarning`


**Docstring:**
```

```

**Methods:**
No methods found.

### `V17ERPNextDeprecationWarning`
**Inherits:** `PendingERPNextDeprecationWarning`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `__get_deprecation_class`
**Arguments:** `graduation, class_name`
**Decorators:** ``

**Docstring:**
```

```
### `deprecated`
**Arguments:** `original, marked, graduation, msg, stacklevel`
**Decorators:** ``

**Docstring:**
```
Decorator to wrap a function/method as deprecated.

Arguments:
        - original: frappe.utils.make_esc  (fully qualified)
        - marked: 2024-09-13  (the date it has been marked)
        - graduation: v17  (generally: current version + 2)
        - msg: additional instructions
```
### `deprecation_warning`
**Arguments:** `marked, graduation, msg`
**Decorators:** ``

**Docstring:**
```
Warn in-place from a deprecated code path, for objects use `@deprecated` decorator from the deprectation_dumpster"

Arguments:
        - marked: 2024-09-13  (the date it has been marked)
        - graduation: v17  (generally: current version + 2)
        - msg: additional instructions
```
### `taxes_and_totals_get_itemised_taxable_amount`
**Arguments:** `items`
**Decorators:** ``

**Docstring:**
```

```
### `get_pos_profile_item_details`
**Arguments:** `company, ctx, pos_profile, update_data`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_warehouse`
**Arguments:** `item, ctx, overwrite_warehouse, defaults`
**Decorators:** ``

**Docstring:**
```

```

