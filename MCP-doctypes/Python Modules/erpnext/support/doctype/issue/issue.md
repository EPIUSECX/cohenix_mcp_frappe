# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/support/doctype/issue/issue.py`

## Classes

### `Issue`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `set_lead_contact` | `self, email_id` | `` |  |
| `create_communication` | `self` | `` |  |
| `split_issue` | `self, subject, communication_id` | `` |  |
| `reset_issue_metrics` | `self` | `` |  |





## Functions

### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `get_issue_list`
**Arguments:** `doctype, txt, filters, limit_start, limit_page_length, order_by`
**Decorators:** ``

**Docstring:**
```

```
### `set_multiple_status`
**Arguments:** `names, status`
**Decorators:** ``

**Docstring:**
```

```
### `set_status`
**Arguments:** `name, status`
**Decorators:** ``

**Docstring:**
```

```
### `auto_close_tickets`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Auto-close replied support tickets after 7 days
```
### `has_website_permission`
**Arguments:** `doc, ptype, user, verbose`
**Decorators:** ``

**Docstring:**
```

```
### `update_issue`
**Arguments:** `contact, method`
**Decorators:** ``

**Docstring:**
```
Called when Contact is deleted
```
### `make_task`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_issue_from_communication`
**Arguments:** `communication, ignore_communication_links`
**Decorators:** ``

**Docstring:**
```
raise a issue from email
```
### `get_time_in_timedelta`
**Arguments:** `time`
**Decorators:** ``

**Docstring:**
```
Converts datetime.time(10, 36, 55, 961454) to datetime.timedelta(seconds=38215)
```
### `set_first_response_time`
**Arguments:** `communication, method`
**Decorators:** ``

**Docstring:**
```

```
### `is_first_response`
**Arguments:** `issue`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_first_response_time`
**Arguments:** `issue, first_responded_on`
**Decorators:** ``

**Docstring:**
```

```
### `get_time_in_seconds`
**Arguments:** `date`
**Decorators:** ``

**Docstring:**
```

```
### `get_working_hours`
**Arguments:** `date, support_hours`
**Decorators:** ``

**Docstring:**
```

```
### `is_work_day`
**Arguments:** `date, support_hours`
**Decorators:** ``

**Docstring:**
```

```
### `is_during_working_hours`
**Arguments:** `date, support_hours`
**Decorators:** ``

**Docstring:**
```

```
### `get_elapsed_time`
**Arguments:** `start_time, end_time`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_initial_frt`
**Arguments:** `issue_creation_date, days_in_between, support_hours`
**Decorators:** ``

**Docstring:**
```

```
### `is_before_working_hours`
**Arguments:** `date, support_hours`
**Decorators:** ``

**Docstring:**
```

```
### `get_holidays`
**Arguments:** `holiday_list_name`
**Decorators:** ``

**Docstring:**
```

```

