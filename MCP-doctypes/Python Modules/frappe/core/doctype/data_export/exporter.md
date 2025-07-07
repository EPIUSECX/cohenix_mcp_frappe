# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/data_export/exporter.py`

## Classes

### `DataExporter`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, parent_doctype, all_doctypes, with_data, select_columns, file_type, template, filters, export_without_column_meta` | `` |  |
| `prepare_args` | `self` | `` |  |
| `build_response` | `self` | `` |  |
| `add_main_header` | `self` | `` |  |
| `build_field_columns` | `self, dt, parentfield` | `` |  |
| `append_field_column` | `self, docfield, for_mandatory` | `` |  |
| `append_empty_field_column` | `self` | `` |  |
| `getinforow` | `docfield` | `staticmethod` | make info comment for options, links etc. |
| `add_field_headings` | `self` | `` |  |
| `add_data` | `self` | `` |  |
| `add_data_row` | `self, rows, dt, parentfield, doc, rowidx` | `` |  |
| `build_response_as_excel` | `self` | `` |  |
| `_append_name_column` | `self, dt` | `` |  |





## Functions

### `get_data_keys`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `export_data`
**Arguments:** `doctype, parent_doctype, all_doctypes, with_data, select_columns, file_type, template, filters, export_without_column_meta`
**Decorators:** ``

**Docstring:**
```

```

