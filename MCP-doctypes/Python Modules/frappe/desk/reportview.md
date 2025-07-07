# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/reportview.py`

## Classes

No classes found in this file.


## Functions

### `get`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_list`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_count`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `execute`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_form_params`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
parse GET request parameters.
```
### `validate_args`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `validate_fields`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `validate_filters`
**Arguments:** `data, filters`
**Decorators:** ``

**Docstring:**
```

```
### `setup_group_by`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```
Add columns for aggregated values e.g. count(name)
```
### `raise_invalid_field`
**Arguments:** `fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `is_standard`
**Arguments:** `fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `extract_fieldnames`
**Arguments:** `field`
**Decorators:** ``

**Docstring:**
```

```
### `get_meta_and_docfield`
**Arguments:** `fieldname, data`
**Decorators:** ``

**Docstring:**
```

```
### `update_wildcard_field_param`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `clean_params`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `parse_json`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `get_parenttype_and_fieldname`
**Arguments:** `field, data`
**Decorators:** ``

**Docstring:**
```

```
### `compress`
**Arguments:** `data, args`
**Decorators:** ``

**Docstring:**
```
separate keys and values
```
### `save_report`
**Arguments:** `name, doctype, report_settings`
**Decorators:** ``

**Docstring:**
```
Save reports of type Report Builder from Report View
```
### `delete_report`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
Delete reports of type Report Builder from Report View
```
### `export_query`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
export from report builder
```
### `append_totals_row`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `get_field_info`
**Arguments:** `fields, doctype`
**Decorators:** ``

**Docstring:**
```
Get column names, labels, field types, and translatable properties based on column names.
```
### `handle_duration_fieldtype_values`
**Arguments:** `doctype, data, fields`
**Decorators:** ``

**Docstring:**
```

```
### `parse_field`
**Arguments:** `field`
**Decorators:** ``

**Docstring:**
```
Parse a field into parenttype and fieldname.
```
### `delete_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
delete selected items
```
### `delete_bulk`
**Arguments:** `doctype, items`
**Decorators:** ``

**Docstring:**
```

```
### `get_sidebar_stats`
**Arguments:** `stats, doctype, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_stats`
**Arguments:** `stats, doctype, filters`
**Decorators:** ``

**Docstring:**
```
get tag info
```
### `get_filter_dashboard_data`
**Arguments:** `stats, doctype, filters`
**Decorators:** ``

**Docstring:**
```
get tags info
```
### `scrub_user_tags`
**Arguments:** `tagcount`
**Decorators:** ``

**Docstring:**
```
rebuild tag list for tags
```
### `get_match_cond`
**Arguments:** `doctype, as_condition`
**Decorators:** ``

**Docstring:**
```

```
### `build_match_conditions`
**Arguments:** `doctype, user, as_condition`
**Decorators:** ``

**Docstring:**
```

```
### `get_filters_cond`
**Arguments:** `doctype, filters, conditions, ignore_permissions, with_match_conditions`
**Decorators:** ``

**Docstring:**
```

```

