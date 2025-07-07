# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/report/report.py`

## Classes

### `Report`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` | only administrator can save standard report |
| `before_insert` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `before_export` | `self, doc` | `` |  |
| `on_trash` | `self` | `` |  |
| `get_permission_log_options` | `self, event` | `` |  |
| `get_columns` | `self` | `` |  |
| `set_doctype_roles` | `self` | `` |  |
| `is_permitted` | `self` | `` | Return True if `Has Role` is not set or the user is allowed. |
| `update_report_json` | `self` | `` |  |
| `export_doc` | `self` | `` |  |
| `create_report_py` | `self` | `` |  |
| `execute_query_report` | `self, filters` | `` |  |
| `execute_script_report` | `self, filters` | `` |  |
| `execute_module` | `self, filters` | `` |  |
| `execute_script` | `self, filters` | `` |  |
| `get_data` | `self, filters, limit, user, as_dict, ignore_prepared_report, are_default_filters` | `` |  |
| `run_query_report` | `self, filters, user, ignore_prepared_report, are_default_filters` | `` |  |
| `run_standard_report` | `self, filters, limit, user` | `` |  |
| `_format` | `parts` | `staticmethod` |  |
| `get_standard_report_columns` | `self, params` | `` |  |
| `get_standard_report_filters` | `self, params, filters` | `` |  |
| `get_standard_report_order_by` | `self, params` | `` |  |
| `build_standard_report_columns` | `self, columns, group_by_args` | `` |  |
| `build_data_dict` | `self, result, columns` | `` |  |
| `toggle_disable` | `self, disable` | `` |  |





## Functions

### `is_prepared_report_enabled`
**Arguments:** `report`
**Decorators:** ``

**Docstring:**
```

```
### `get_report_module_dotted_path`
**Arguments:** `module, report_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_group_by_field`
**Arguments:** `args, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_group_by_column_label`
**Arguments:** `args, meta`
**Decorators:** ``

**Docstring:**
```

```
### `enable_prepared_report`
**Arguments:** `report, site`
**Decorators:** ``

**Docstring:**
```

```

