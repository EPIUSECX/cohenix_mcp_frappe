# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/query_report.py`

## Classes

No classes found in this file.


## Functions

### `get_report_doc`
**Arguments:** `report_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_report_result`
**Arguments:** `report, filters`
**Decorators:** ``

**Docstring:**
```

```
### `generate_report_result`
**Arguments:** `report, filters, user, custom_columns, is_tree, parent_field`
**Decorators:** ``

**Docstring:**
```

```
### `normalize_result`
**Arguments:** `result, columns`
**Decorators:** ``

**Docstring:**
```

```
### `get_script`
**Arguments:** `report_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_reference_report`
**Arguments:** `report`
**Decorators:** ``

**Docstring:**
```

```
### `run`
**Arguments:** `report_name, filters, user, ignore_prepared_report, custom_columns, is_tree, parent_field, are_default_filters`
**Decorators:** ``

**Docstring:**
```

```
### `add_custom_column_data`
**Arguments:** `custom_columns, result`
**Decorators:** ``

**Docstring:**
```

```
### `get_prepared_report_result`
**Arguments:** `report, filters, dn, user`
**Decorators:** ``

**Docstring:**
```

```
### `export_query`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
export from query reports
```
### `valid_report_name`
**Arguments:** `report_name, suffix`
**Decorators:** ``

**Docstring:**
```

```
### `format_fields`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `build_xlsx_data`
**Arguments:** `data, visible_idx, include_indentation, include_filters, ignore_visible_idx`
**Decorators:** ``

**Docstring:**
```

```
### `add_total_row`
**Arguments:** `result, columns, meta, is_tree, parent_field`
**Decorators:** ``

**Docstring:**
```

```
### `get_data_for_custom_field`
**Arguments:** `doctype, field, names`
**Decorators:** ``

**Docstring:**
```

```
### `get_data_for_custom_report`
**Arguments:** `columns, result`
**Decorators:** ``

**Docstring:**
```

```
### `save_report`
**Arguments:** `reference_report, report_name, columns, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_filtered_data`
**Arguments:** `ref_doctype, columns, data, user`
**Decorators:** ``

**Docstring:**
```

```
### `has_match`
**Arguments:** `row, linked_doctypes, doctype_match_filters, ref_doctype, if_owner, columns_dict, user`
**Decorators:** ``

**Docstring:**
```
Return True if after evaluating permissions for each linked doctype:
        - There is an owner match for the ref_doctype
        - `and` There is a user permission match for all linked doctypes

Return True if the row is empty.

Note:
Each doctype could have multiple conflicting user permission doctypes.
Hence even if one of the sets allows a match, it is true.
This behavior is equivalent to the trickling of user permissions of linked doctypes to the ref doctype.
```
### `has_unrestricted_read_access`
**Arguments:** `doctype, user`
**Decorators:** `request_cache`

**Docstring:**
```

```
### `get_linked_doctypes`
**Arguments:** `columns, data`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns_dict`
**Arguments:** `columns`
**Decorators:** ``

**Docstring:**
```
Return a dict with column docfield values as dict.

The keys for the dict are both idx and fieldname,
so either index or fieldname can be used to search for a column's docfield properties.
```
### `get_column_as_dict`
**Arguments:** `col`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_match_filters`
**Arguments:** `doctypes, user`
**Decorators:** ``

**Docstring:**
```

```
### `validate_filters_permissions`
**Arguments:** `report_name, filters, user`
**Decorators:** ``

**Docstring:**
```

```
### `translate_report_data`
**Arguments:** `data, total_row`
**Decorators:** ``

**Docstring:**
```

```

