# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/log_settings/log_settings.py`

## Classes

### `LogType`
**Inherits:** `Protocol`


**Docstring:**
```
Interface requirement for doctypes that can be cleared using log settings.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `clear_old_logs` | `days` | `staticmethod` |  |


### `LogSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `remove_unsupported_doctypes` | `self` | `` |  |
| `_deduplicate_entries` | `self` | `` |  |
| `add_default_logtypes` | `self` | `` |  |
| `clear_logs` | `self` | `` | Log settings can clear any log type that's registered to it and provides a method to delete old logs.

Check `LogDoctype` above for interface that doctypes need to implement. |
| `register_doctype` | `self, doctype, days` | `` |  |





## Functions

### `_supports_log_clearing`
**Arguments:** `doctype`
**Decorators:** `site_cache`

**Docstring:**
```

```
### `run_log_clean_up`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `has_unseen_error_log`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_log_doctypes`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `clear_log_table`
**Arguments:** `doctype, days`
**Decorators:** ``

**Docstring:**
```
If any logtype table grows too large then clearing it with DELETE query
is not feasible in reasonable time. This command copies recent data to new
table and replaces current table with new smaller table.

ref: https://mariadb.com/kb/en/big-deletes/#deleting-more-than-half-a-table
```

