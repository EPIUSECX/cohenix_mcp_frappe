# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/data_import/importer.py`

## Classes

### `Importer`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, data_import, file_path, import_type, console, use_sniffer` | `` |  |
| `get_data_for_import_preview` | `self` | `` |  |
| `before_import` | `self` | `` |  |
| `import_data` | `self` | `` |  |
| `after_import` | `self` | `` |  |
| `process_doc` | `self, doc` | `` |  |
| `insert_record` | `self, doc` | `` |  |
| `update_record` | `self, doc` | `` |  |
| `get_eta` | `self, current, total, processing_time` | `` |  |
| `export_errored_rows` | `self` | `` |  |
| `export_import_log` | `self` | `` |  |
| `print_import_log` | `self, import_log` | `` |  |
| `print_grouped_warnings` | `self, warnings` | `` |  |


### `ImportFile`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, file, template_options, import_type` | `` |  |
| `get_data_from_template_file` | `self` | `` |  |
| `parse_data_from_template` | `self` | `` |  |
| `get_data_for_import_preview` | `self` | `` | Adds a serial number column as the first column |
| `get_payloads_for_import` | `self` | `` |  |
| `parse_next_row_for_import` | `self, data` | `` | Parse rows that make up a doc. A doc maybe built from a single row or multiple rows.
Return the doc, rows, and data without the rows. |
| `get_warnings` | `self` | `` |  |
| `read_file` | `self, file_path` | `` |  |
| `read_content` | `self, content, extension` | `` |  |


### `Row`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, index, row, doctype, header, import_type` | `` |  |
| `parse_doc` | `self, doctype, parent_doc, table_df` | `` |  |
| `_parse_doc` | `self, doctype, columns, values, parent_doc, table_df` | `` |  |
| `validate_value` | `self, value, col` | `` |  |
| `link_exists` | `self, value, df` | `` |  |
| `parse_value` | `self, value, col` | `` |  |
| `get_date` | `self, value, column` | `` |  |
| `get_datetime` | `self, value, column` | `` |  |
| `get_values` | `self, indexes` | `` |  |
| `get` | `self, index` | `` |  |
| `as_list` | `self` | `` |  |


### `Header`
**Inherits:** `Row`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, index, row, doctype, raw_data, column_to_field_map` | `` |  |
| `get_column_indexes` | `self, doctype, tablefield` | `` |  |
| `get_columns` | `self, indexes` | `` |  |


### `Column`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, index, header, doctype, column_values, map_to_field, seen` | `` |  |
| `parse` | `self` | `` |  |
| `guess_date_format_for_column` | `self` | `` | Guesses date format for a column by parsing all the values in the column,
getting the date format and then returning the one which has the maximum frequency |
| `validate_values` | `self` | `` |  |
| `as_dict` | `self` | `` |  |





## Functions

### `build_fields_dict_for_column_matching`
**Arguments:** `parent_doctype`
**Decorators:** ``

**Docstring:**
```
Build a dict with various keys to match with column headers and value as docfield
The keys can be label or fieldname
{
        'Customer': df1,
        'customer': df1,
        'Due Date': df2,
        'due_date': df2,
        'Item Code (Sales Invoice Item)': df3,
        'Sales Invoice Item:item_code': df3,
}
```
### `get_df_for_column_header`
**Arguments:** `doctype, header`
**Decorators:** ``

**Docstring:**
```

```
### `get_id_field`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_autoname_field`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_at_index`
**Arguments:** `_list, i, default`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_format`
**Arguments:** `date_format`
**Decorators:** ``

**Docstring:**
```

```
### `df_as_json`
**Arguments:** `df`
**Decorators:** ``

**Docstring:**
```

```
### `get_select_options`
**Arguments:** `df`
**Decorators:** ``

**Docstring:**
```

```
### `create_import_log`
**Arguments:** `data_import, log_index, log_details`
**Decorators:** ``

**Docstring:**
```

```

