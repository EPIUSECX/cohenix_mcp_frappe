# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/language/language.py`

## Classes

### `Language`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `before_rename` | `self, old, new, merge` | `` |  |
| `on_update` | `self` | `` |  |
| `update_user_defaults` | `self` | `` | Update user defaults for date, time, number format and first day of the week.

When we change any settings of a language, the defaults for all users with that language
should be updated. |





## Functions

### `validate_with_regex`
**Arguments:** `name, label`
**Decorators:** ``

**Docstring:**
```

```
### `sync_languages`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Create Language records from frappe/geo/languages.csv
```

