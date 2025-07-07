# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/data_import/data_import.py`

## Classes

### `DataImport`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `set_delimiters_flag` | `self` | `` |  |
| `validate_doctype` | `self` | `` |  |
| `validate_import_file` | `self` | `` |  |
| `validate_google_sheets_url` | `self` | `` |  |
| `set_payload_count` | `self` | `` |  |
| `get_preview_from_template` | `self, import_file, google_sheets_url` | `` |  |
| `start_import` | `self` | `` |  |
| `export_errored_rows` | `self` | `` |  |
| `download_import_log` | `self` | `` |  |
| `get_importer` | `self` | `` |  |
| `on_trash` | `self` | `` |  |





## Functions

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
### `start_import`
**Arguments:** `data_import`
**Decorators:** ``

**Docstring:**
```
This method runs in background job
```
### `download_template`
**Arguments:** `doctype, export_fields, export_records, export_filters, file_type`
**Decorators:** ``

**Docstring:**
```
Download template from Exporter
        :param doctype: Document Type
        :param export_fields=None: Fields to export as dict {'Sales Invoice': ['name', 'customer'], 'Sales Invoice Item': ['item_code']}
        :param export_records=None: One of 'all', 'by_filter', 'blank_template'
        :param export_filters: Filter dict
        :param file_type: File type to export into
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
### `get_import_status`
**Arguments:** `data_import_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_import_logs`
**Arguments:** `data_import`
**Decorators:** ``

**Docstring:**
```

```
### `import_file`
**Arguments:** `doctype, file_path, import_type, submit_after_import, console`
**Decorators:** ``

**Docstring:**
```
Import documents in from CSV or XLSX using data import.

:param doctype: DocType to import
:param file_path: Path to .csv, .xls, or .xlsx file to import
:param import_type: One of "Insert" or "Update"
:param submit_after_import: Whether to submit documents after import
:param console: Set to true if this is to be used from command line. Will print errors or progress to stdout.
```
### `import_doc`
**Arguments:** `path, pre_process, sort`
**Decorators:** ``

**Docstring:**
```

```
### `export_json`
**Arguments:** `doctype, path, filters, or_filters, name, order_by`
**Decorators:** ``

**Docstring:**
```

```
### `export_csv`
**Arguments:** `doctype, path`
**Decorators:** ``

**Docstring:**
```

```

