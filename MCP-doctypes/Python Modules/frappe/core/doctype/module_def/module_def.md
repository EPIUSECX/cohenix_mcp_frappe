# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/module_def/module_def.py`

## Classes

### `ModuleDef`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` | If in `developer_mode`, create folder for module and
add in `modules.txt` of app if missing. |
| `create_modules_folder` | `self` | `` | Creates a folder `[app]/[module]` and adds `__init__.py` |
| `add_to_modules_txt` | `self` | `` | Adds to `[app]/modules.txt` |
| `on_trash` | `self` | `` | Delete module name from modules.txt |
| `delete_module_from_file` | `self` | `` |  |





## Functions

### `get_installed_apps`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

