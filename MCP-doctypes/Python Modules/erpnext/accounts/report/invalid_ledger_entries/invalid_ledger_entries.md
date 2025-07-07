# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/report/invalid_ledger_entries/invalid_ledger_entries.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Return columns and data for the report.

This is the main entry point for the report. It accepts the filters as a
dictionary and should return columns and data. It is called by the framework
every time the report is refreshed or a filter is updated.
```
### `get_columns`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return columns for the report.

One field definition per column, just like a DocType field definition.
```
### `get_data`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Return data for the report.

The report data is a list of rows, with each row being a list of cell values.
```
### `identify_cancelled_vouchers`
**Arguments:** `active_vouchers`
**Decorators:** ``

**Docstring:**
```

```
### `validate_filters`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `build_query_filters`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_active_vouchers_for_period`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```

