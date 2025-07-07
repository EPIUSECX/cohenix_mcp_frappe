# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/system_health_report/system_health_report.py`

## Classes

### `SystemHealthReport`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `db_insert` | `self` | `` |  |
| `load_from_db` | `self` | `` |  |
| `fetch_background_jobs` | `self` | `` |  |
| `fetch_scheduler` | `self` | `` |  |
| `fetch_email_stats` | `self` | `` |  |
| `fetch_errors` | `self` | `` |  |
| `fetch_database_details` | `self` | `` |  |
| `fetch_cache_details` | `self` | `` |  |
| `fetch_storage_details` | `self` | `` |  |
| `fetch_user_stats` | `self` | `` |  |
| `db_update` | `self` | `` |  |
| `delete` | `self` | `` |  |
| `get_list` | `filters, page_length` | `staticmethod` |  |
| `get_count` | `filters` | `staticmethod` |  |
| `get_stats` | `` | `staticmethod` |  |





## Functions

### `no_wait`
**Arguments:** `func`
**Decorators:** `contextmanager`

**Docstring:**
```
Disable tenacity waiting on some function
```
### `health_check`
**Arguments:** `step`
**Decorators:** ``

**Docstring:**
```

```
### `get_job_status`
**Arguments:** `job_id`
**Decorators:** ``

**Docstring:**
```

```
### `get_directory_size`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_get_directory_size`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

