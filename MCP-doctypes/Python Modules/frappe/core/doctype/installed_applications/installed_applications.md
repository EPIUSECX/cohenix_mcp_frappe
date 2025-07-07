# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/installed_applications/installed_applications.py`

## Classes

### `InvalidAppOrder`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InstalledApplications`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `update_versions` | `self` | `` |  |
| `get_app_wise_setup_details` | `self` | `` | Get app wise setup details from the Installed Application doctype |
| `reload_doc_if_required` | `self` | `` |  |





## Functions

### `update_installed_apps_order`
**Arguments:** `new_order`
**Decorators:** ``

**Docstring:**
```
Change the ordering of `installed_apps` global

This list is used to resolve hooks and by default it's order of installation on site.

Sometimes it might not be the ordering you want, so thie function is provided to override it.
```
### `_create_version_log_for_change`
**Arguments:** `old, new`
**Decorators:** ``

**Docstring:**
```

```
### `get_installed_app_order`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_setup_wizard_completed_apps`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get list of apps that have completed setup wizard
```
### `get_setup_wizard_not_required_apps`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get list of apps that do not require setup wizard
```
### `get_apps_with_incomplete_dependencies`
**Arguments:** `current_app`
**Decorators:** ``

**Docstring:**
```
Get apps with incomplete dependencies.
```
### `get_setup_wizard_pending_apps`
**Arguments:** `apps`
**Decorators:** ``

**Docstring:**
```
Get list of apps that have completed setup wizard
```

