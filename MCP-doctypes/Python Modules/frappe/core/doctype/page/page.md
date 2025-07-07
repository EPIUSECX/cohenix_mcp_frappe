# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/page/page.py`

## Classes

### `Page`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` | Creates a url friendly name for this page.
Will restrict the name to 30 characters, if there exists a similar name,
it will add name-1, name-2 etc. |
| `validate` | `self` | `` |  |
| `get_permission_log_options` | `self, event` | `` |  |
| `on_update` | `self` | `` | Writes the .json for this page and if write_content is checked,
it will write out a .html file |
| `as_dict` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `delete_folder_with_contents` | `self` | `` |  |
| `is_permitted` | `self` | `` | Return True if `Has Role` is not set or the user is allowed. |
| `load_assets` | `self` | `` |  |





## Functions

### `delete_custom_role`
**Arguments:** `field, docname`
**Decorators:** ``

**Docstring:**
```

```

