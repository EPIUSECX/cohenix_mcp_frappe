# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/tests/utils.py`

## Classes

### `ERPNextTestSuite`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `make_monthly_distribution` | `cls` | `classmethod` |  |
| `make_projects` | `cls` | `classmethod` |  |
| `make_employees` | `cls` | `classmethod` |  |
| `make_sales_person` | `cls` | `classmethod` |  |
| `make_leads` | `cls` | `classmethod` |  |





## Functions

### `create_test_contact_and_address`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `execute_script_report`
**Arguments:** `report_name, module, filters, default_filters, optional_filters`
**Decorators:** ``

**Docstring:**
```
Util for testing execution of a report with specified filters.

Tests the execution of report with default_filters + filters.
Tests the execution using optional_filters one at a time.

Args:
        report_name: Human readable name of report (unscrubbed)
        module: module to which report belongs to
        filters: specific values for filters
        default_filters: default values for filters such as company name.
        optional_filters: filters which should be tested one at a time in addition to default filters.
```
### `if_lending_app_installed`
**Arguments:** `function`
**Decorators:** ``

**Docstring:**
```
Decorator to check if lending app is installed
```
### `if_lending_app_not_installed`
**Arguments:** `function`
**Decorators:** ``

**Docstring:**
```
Decorator to check if lending app is not installed
```

