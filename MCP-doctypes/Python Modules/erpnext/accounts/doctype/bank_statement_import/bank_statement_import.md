# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_statement_import/bank_statement_import.py`

## Classes

### `BankStatementImport`
**Inherits:** `DataImport`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `start_import` | `self` | `` |  |





## Functions

### `convert_mt940_to_csv`
**Arguments:** `data_import, mt940_file_path`
**Decorators:** ``

**Docstring:**
```

```
### `get_preview_from_template`
**Arguments:** `data_import, import_file, google_sheets_url`
**Decorators:** ``

**Docstring:**
```

```
### `form_start_import`
**Arguments:** `data_import`
**Decorators:** ``

**Docstring:**
```

```
### `download_errored_template`
**Arguments:** `data_import_name`
**Decorators:** ``

**Docstring:**
```

```
### `download_import_log`
**Arguments:** `data_import_name`
**Decorators:** ``

**Docstring:**
```

```
### `is_mt940_format`
**Arguments:** `content`
**Decorators:** ``

**Docstring:**
```
Check if the content has key MT940 tags
```
### `parse_data_from_template`
**Arguments:** `raw_data`
**Decorators:** ``

**Docstring:**
```

```
### `start_import`
**Arguments:** `data_import, bank_account, import_file_path, google_sheets_url, bank, template_options`
**Decorators:** ``

**Docstring:**
```
This method runs in background job
```
### `update_mapping_db`
**Arguments:** `bank, template_options`
**Decorators:** ``

**Docstring:**
```

```
### `add_bank_account`
**Arguments:** `data, bank_account`
**Decorators:** ``

**Docstring:**
```

```
### `write_files`
**Arguments:** `import_file, data`
**Decorators:** ``

**Docstring:**
```

```
### `write_xlsx`
**Arguments:** `data, sheet_name, wb, column_widths, file_path`
**Decorators:** ``

**Docstring:**
```

```
### `get_import_status`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```

```
### `get_import_logs`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```

```
### `upload_bank_statement`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

