# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/desktop.py`

## Classes

### `Workspace`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, page, minimal` | `` |  |
| `is_permitted` | `self` | `` | Return true if `Has Role` is not set or the user is allowed. |
| `get_cached` | `self, cache_key, fallback_fn` | `` |  |
| `get_can_read_items` | `self` | `` |  |
| `get_allowed_modules` | `self` | `` |  |
| `get_onboarding_doc` | `self, onboarding` | `` |  |
| `is_item_allowed` | `self, name, item_type` | `` |  |
| `build_workspace` | `self` | `` |  |
| `_doctype_contains_a_record` | `self, name` | `` |  |
| `_prepare_item` | `self, item` | `` |  |
| `is_custom_block_permitted` | `self, custom_block_name` | `` |  |
| `get_links` | `self` | `handle_not_exist` |  |
| `get_charts` | `self` | `handle_not_exist` |  |
| `get_shortcuts` | `self` | `handle_not_exist` |  |
| `get_quick_lists` | `self` | `handle_not_exist` |  |
| `get_onboardings` | `self` | `handle_not_exist` |  |
| `get_onboarding_steps` | `self, onboarding_doc` | `handle_not_exist` |  |
| `get_number_cards` | `self` | `handle_not_exist` |  |
| `get_custom_blocks` | `self` | `handle_not_exist` |  |





## Functions

### `handle_not_exist`
**Arguments:** `fn`
**Decorators:** ``

**Docstring:**
```

```
### `get_desktop_page`
**Arguments:** `page`
**Decorators:** ``

**Docstring:**
```
Apply permissions, customizations and return the configuration for a page on desk.

Args:
        page (json): page data

Return:
        dict: dictionary of cards, charts and shortcuts to be displayed on website
```
### `get_workspace_sidebar_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get list of sidebar items for desk
```
### `get_table_with_counts`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_custom_reports_and_doctypes`
**Arguments:** `module`
**Decorators:** ``

**Docstring:**
```

```
### `get_custom_doctype_list`
**Arguments:** `module`
**Decorators:** ``

**Docstring:**
```

```
### `get_custom_report_list`
**Arguments:** `module`
**Decorators:** ``

**Docstring:**
```
Return list on new style reports for modules.
```
### `save_new_widget`
**Arguments:** `doc, page, blocks, new_widgets`
**Decorators:** ``

**Docstring:**
```

```
### `clean_up`
**Arguments:** `original_page, blocks`
**Decorators:** ``

**Docstring:**
```

```
### `new_widget`
**Arguments:** `config, doctype, parentfield`
**Decorators:** ``

**Docstring:**
```

```
### `prepare_widget`
**Arguments:** `config, doctype, parentfield`
**Decorators:** ``

**Docstring:**
```
Create widget child table entries with parent details.

Args:
        config (dict): Dictionary containing widget config
        doctype (string): Doctype name of the child table
        parentfield (string): Parent field for the child table

Return:
        TYPE: List of Document objects
```
### `update_onboarding_step`
**Arguments:** `name, field, value`
**Decorators:** ``

**Docstring:**
```
Update status of onboaridng step

Args:
        name (string): Name of the doc
        field (string): field to be updated
        value: Value to be updated
```

