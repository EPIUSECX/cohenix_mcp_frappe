# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/rq_job/rq_job.py`

## Classes

### `RQJob`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `load_from_db` | `self` | `` |  |
| `job` | `self` | `property` |  |
| `get_list` | `filters, start, page_length, order_by` | `staticmethod` |  |
| `get_matching_job_ids` | `filters` | `staticmethod` |  |
| `delete` | `self` | `check_permissions` |  |
| `stop_job` | `self` | `check_permissions` |  |
| `cancel` | `self` | `check_permissions` |  |
| `get_count` | `filters` | `staticmethod` |  |
| `get_stats` | `` | `staticmethod` |  |
| `db_insert` | `self` | `` |  |
| `db_update` | `self` | `` |  |





## Functions

### `check_permissions`
**Arguments:** `method`
**Decorators:** ``

**Docstring:**
```

```
### `serialize_job`
**Arguments:** `job`
**Decorators:** ``

**Docstring:**
```

```
### `for_current_site`
**Arguments:** `job`
**Decorators:** ``

**Docstring:**
```

```
### `filter_current_site_jobs`
**Arguments:** `job_ids`
**Decorators:** ``

**Docstring:**
```

```
### `_eval_filters`
**Arguments:** `filter, values`
**Decorators:** ``

**Docstring:**
```

```
### `fetch_job_ids`
**Arguments:** `queue, status`
**Decorators:** ``

**Docstring:**
```

```
### `remove_failed_jobs`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_all_queued_jobs`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `stop_job`
**Arguments:** `job_id`
**Decorators:** ``

**Docstring:**
```

```

