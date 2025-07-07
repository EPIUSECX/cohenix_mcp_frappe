# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/auto_email_report/auto_email_report.py`

## Classes

### `AutoEmailReport`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `sender_email` | `self` | `property` |  |
| `validate_emails` | `self` | `` | Cleanup list of emails |
| `validate_report_count` | `self` | `` |  |
| `validate_report_format` | `self` | `` | check if user has select correct report format |
| `validate_mandatory_fields` | `self` | `` |  |
| `get_report_content` | `self` | `` | Return file for the report in given format. |
| `get_html_table` | `self, columns, data` | `` |  |
| `get_file_name` | `self` | `` |  |
| `prepare_dynamic_filters` | `self` | `` |  |
| `set_date_filters` | `self, from_date, to_date` | `` |  |
| `send` | `self` | `` |  |
| `dynamic_date_filters_set` | `self` | `` |  |





## Functions

### `download`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
Download report locally
```
### `send_now`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
Send Auto Email report now
```
### `send_daily`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Check reports to be sent daily
```
### `process_auto_email_report`
**Arguments:** `report`
**Decorators:** ``

**Docstring:**
```
Process and send the Auto Email Report based on frequency
```
### `send_monthly`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Check reports to be sent monthly
```
### `make_links`
**Arguments:** `columns, data`
**Decorators:** ``

**Docstring:**
```

```
### `update_field_types`
**Arguments:** `columns`
**Decorators:** ``

**Docstring:**
```

```
### `get_half_year_start`
**Arguments:** `as_str`
**Decorators:** ``

**Docstring:**
```
Returns the first day of the current half-year based on the current date.
```

