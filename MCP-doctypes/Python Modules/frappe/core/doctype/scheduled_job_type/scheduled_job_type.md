# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/scheduled_job_type/scheduled_job_type.py`

## Classes

### `ScheduledJobType`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `enqueue` | `self, force` | `` |  |
| `is_event_due` | `self, current_time` | `` | Return true if event is due based on time lapsed since last execution |
| `is_job_in_queue` | `self` | `` |  |
| `rq_job_id` | `self` | `property` | Unique ID created to deduplicate jobs with single RQ call. |
| `next_execution` | `self` | `property` |  |
| `get_next_execution` | `self` | `` |  |
| `execute` | `self` | `` |  |
| `log_status` | `self, status` | `` |  |
| `update_scheduler_log` | `self, status` | `` |  |
| `get_queue_name` | `self` | `` |  |
| `on_trash` | `self` | `` |  |





## Functions

### `execute_event`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `skip_next_execution`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `run_scheduled_job`
**Arguments:** `scheduled_job_type, job_type`
**Decorators:** ``

**Docstring:**
```
This is a wrapper function that runs a hooks.scheduler_events method
```
### `sync_jobs`
**Arguments:** `hooks`
**Decorators:** ``

**Docstring:**
```

```
### `insert_events`
**Arguments:** `scheduler_events`
**Decorators:** ``

**Docstring:**
```

```
### `insert_cron_jobs`
**Arguments:** `events`
**Decorators:** ``

**Docstring:**
```

```
### `insert_event_jobs`
**Arguments:** `events, event_type`
**Decorators:** ``

**Docstring:**
```

```
### `insert_single_event`
**Arguments:** `frequency, event, cron_format`
**Decorators:** ``

**Docstring:**
```

```
### `clear_events`
**Arguments:** `scheduler_events`
**Decorators:** ``

**Docstring:**
```

```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

