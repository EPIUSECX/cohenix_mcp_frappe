# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/submission_queue/submission_queue.py`

## Classes

### `SubmissionQueue`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `created_at` | `self` | `property` |  |
| `enqueued_by` | `self` | `property` |  |
| `queued_doc` | `self` | `property` |  |
| `clear_old_logs` | `days` | `staticmethod` |  |
| `insert` | `self, to_be_queued_doc, action` | `` |  |
| `lock` | `self` | `` |  |
| `unlock` | `self` | `` |  |
| `update_job_id` | `self, job_id` | `` |  |
| `after_insert` | `self` | `` |  |
| `background_submission` | `self, to_be_queued_doc, action_for_queuing` | `` |  |
| `notify` | `self, submission_status, action` | `` |  |
| `unlock_doc` | `self` | `` |  |





## Functions

### `queue_submission`
**Arguments:** `doc, action, alert`
**Decorators:** ``

**Docstring:**
```

```
### `get_latest_submissions`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `format_tb`
**Arguments:** `traceback`
**Decorators:** ``

**Docstring:**
```

```

