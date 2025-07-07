# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/timesheet/timesheet.py`

## Classes

### `OverlapError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OverWorkLoggedError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Timesheet`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `calculate_hours` | `self` | `` |  |
| `calculate_total_amounts` | `self` | `` |  |
| `calculate_percentage_billed` | `self` | `` |  |
| `update_billing_hours` | `self, args` | `deprecated` |  |
| `set_status` | `self` | `` |  |
| `set_dates` | `self` | `` |  |
| `before_cancel` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `validate_mandatory_fields` | `self` | `` |  |
| `update_task_and_project` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `validate_time_logs` | `self` | `` |  |
| `validate_overlap` | `self, data` | `` |  |
| `set_project` | `self, data` | `deprecated` |  |
| `validate_project` | `self, data` | `deprecated` |  |
| `validate_overlap_for` | `self, fieldname, args, value, ignore_validation` | `` |  |
| `get_overlap_for` | `self, fieldname, args, value` | `` |  |
| `check_internal_overlap` | `self, fieldname, args` | `` |  |
| `update_cost` | `self` | `` |  |
| `update_time_rates` | `self, ts_detail` | `` |  |
| `unlink_sales_invoice` | `self, sales_invoice` | `` | Remove link to Sales Invoice from all time logs. |





## Functions

### `get_projectwise_timesheet_data`
**Arguments:** `project, parent, from_time, to_time`
**Decorators:** ``

**Docstring:**
```

```
### `get_timesheet_detail_rate`
**Arguments:** `timelog, currency`
**Decorators:** ``

**Docstring:**
```

```
### `get_timesheet`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_timesheet_data`
**Arguments:** `name, project`
**Decorators:** ``

**Docstring:**
```

```
### `make_sales_invoice`
**Arguments:** `source_name, item_code, customer, currency`
**Decorators:** ``

**Docstring:**
```

```
### `get_activity_cost`
**Arguments:** `employee, activity_type, currency`
**Decorators:** ``

**Docstring:**
```

```
### `get_events`
**Arguments:** `start, end, filters`
**Decorators:** ``

**Docstring:**
```
Returns events for Gantt / Calendar view rendering.
:param start: Start date-time.
:param end: End date-time.
:param filters: Filters (JSON).
```
### `get_timesheets_list`
**Arguments:** `doctype, txt, filters, limit_start, limit_page_length, order_by`
**Decorators:** ``

**Docstring:**
```

```
### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```

