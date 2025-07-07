# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/prepared_report/prepared_report.py`

## Classes

### `PreparedReport`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `queued_by` | `self` | `property` |  |
| `queued_at` | `self` | `property` |  |
| `clear_old_logs` | `days` | `staticmethod` |  |
| `before_insert` | `self` | `` |  |
| `on_trash` | `self` | `` | Remove pending job from queue, if already running then kill the job. |
| `after_insert` | `self` | `` |  |
| `get_prepared_data` | `self, with_file_name` | `` |  |





## Functions

### `generate_report`
**Arguments:** `prepared_report`
**Decorators:** ``

**Docstring:**
```

```
### `_save_error`
**Arguments:** `instance, error`
**Decorators:** `dangerously_reconnect_on_connection_abort`

**Docstring:**
```

```
### `update_job_id`
**Arguments:** `prepared_report`
**Decorators:** ``

**Docstring:**
```

```
### `make_prepared_report`
**Arguments:** `report_name, filters`
**Decorators:** ``

**Docstring:**
```
run reports in background
```
### `process_filters_for_prepared_report`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_reports_in_queued_state`
**Arguments:** `report_name, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_completed_prepared_report`
**Arguments:** `filters, user, report_name`
**Decorators:** ``

**Docstring:**
```

```
### `expire_stalled_report`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `delete_prepared_reports`
**Arguments:** `reports`
**Decorators:** ``

**Docstring:**
```

```
### `create_json_gz_file`
**Arguments:** `data, dt, dn, report_name`
**Decorators:** ``

**Docstring:**
```

```
### `download_attachment`
**Arguments:** `dn`
**Decorators:** ``

**Docstring:**
```

```
### `get_permission_query_condition`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `has_permission`
**Arguments:** `doc, user`
**Decorators:** ``

**Docstring:**
```

```
### `enqueue_json_to_csv_conversion`
**Arguments:** `prepared_report_name`
**Decorators:** ``

**Docstring:**
```
Call this to enqueue the conversion in background.
```
### `convert_json_to_csv`
**Arguments:** `prepared_report_name`
**Decorators:** ``

**Docstring:**
```
Background job: Fetch JSON file, convert to CSV, attach CSV to Prepared Report.
```

