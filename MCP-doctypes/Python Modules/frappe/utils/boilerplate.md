# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/boilerplate.py`

## Classes

### `PatchCreator`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `fetch_user_inputs` | `self` | `` |  |
| `_ask_app_name` | `self` | `` |  |
| `_ask_doctype_name` | `self` | `` |  |
| `_ask_patch_meta_info` | `self` | `` |  |
| `create_patch_file` | `self` | `` |  |
| `_create_parent_folder_if_not_exists` | `self` | `` |  |





## Functions

### `make_boilerplate`
**Arguments:** `dest, app_name, no_git`
**Decorators:** ``

**Docstring:**
```

```
### `_get_user_inputs`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```
Prompt user for various inputs related to new app and return config.
```
### `is_valid_email`
**Arguments:** `email`
**Decorators:** ``

**Docstring:**
```

```
### `is_valid_title`
**Arguments:** `title`
**Decorators:** ``

**Docstring:**
```

```
### `get_license_options`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_license_text`
**Arguments:** `license_name`
**Decorators:** ``

**Docstring:**
```

```
### `copy_from_frappe`
**Arguments:** `rel_path, new_app_path`
**Decorators:** ``

**Docstring:**
```
Copy files from frappe app to new app.
```
### `_create_app_boilerplate`
**Arguments:** `dest, hooks, no_git`
**Decorators:** ``

**Docstring:**
```

```
### `_create_github_workflow_files`
**Arguments:** `dest, hooks`
**Decorators:** ``

**Docstring:**
```

```

