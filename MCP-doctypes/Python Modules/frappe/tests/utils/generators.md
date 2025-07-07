# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/utils/generators.py`

## Classes

### `TestRecordManager`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `get` | `self` | `` |  |
| `get_records` | `self, index_doctype` | `` |  |
| `add` | `self, index_doctype, records` | `` |  |
| `remove` | `self, index_doctype` | `` | Remove all records for the specified doctype from the log. |
| `_append_to_log` | `self, index_doctype, records` | `` |  |
| `_read_log` | `self` | `` |  |
| `_remove_from_log` | `self, index_doctype` | `` |  |





## Functions

### `get_modules`
**Arguments:** `doctype`
**Decorators:** `cache`

**Docstring:**
```
Get the modules for the specified doctype
```
### `get_missing_records_doctypes`
**Arguments:** `doctype, visited`
**Decorators:** ``

**Docstring:**
```
Get the dependencies for the specified doctype in a depth-first manner
```
### `get_missing_records_module_overrides`
**Arguments:** `module`
**Decorators:** ``

**Docstring:**
```

```
### `load_test_records_for`
**Arguments:** `index_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `_generate_all_records_towards`
**Arguments:** `index_doctype, reset, commit`
**Decorators:** ``

**Docstring:**
```
Generate test records for the given doctype and its dependencies.
```
### `_generate_records_for`
**Arguments:** `index_doctype, reset, commit, initial_doctype`
**Decorators:** ``

**Docstring:**
```
Create and yield test records for a specific doctype.
```
### `_sync_records`
**Arguments:** `index_doctype, test_records, reset, commit`
**Decorators:** ``

**Docstring:**
```
Generate test objects for a register doctype from provided records, with caching and persistence.
```
### `_try_create`
**Arguments:** `record, reset, commit`
**Decorators:** ``

**Docstring:**
```
Create a single test document from the given record data.
```
### `print_mandatory_fields`
**Arguments:** `doctype, initial_doctype`
**Decorators:** ``

**Docstring:**
```
Print mandatory fields for the specified doctype
```
### `_clear_test_log`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_test_records`
**Arguments:** `doctype, force, commit`
**Decorators:** ``

**Docstring:**
```
Generate test records for the given doctype and its dependencies.
```
### `make_test_records_for_doctype`
**Arguments:** `doctype, force, commit`
**Decorators:** ``

**Docstring:**
```
Create test records for a specific doctype.
```
### `make_test_objects`
**Arguments:** `doctype, test_records, reset, commit`
**Decorators:** ``

**Docstring:**
```
Generate test objects from provided records, with caching and persistence.
```
### `_transform_legacy_json_records`
**Arguments:** `test_records, doctype`
**Decorators:** ``

**Docstring:**
```

```

