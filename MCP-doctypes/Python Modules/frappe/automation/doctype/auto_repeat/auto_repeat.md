# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/automation/doctype/auto_repeat/auto_repeat.py`

## Classes

### `AutoRepeat`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `before_insert` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `set_dates` | `self` | `` |  |
| `unlink_if_applicable` | `self` | `` |  |
| `validate_reference_doctype` | `self` | `` |  |
| `validate_submit_on_creation` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `validate_email_id` | `self` | `` |  |
| `validate_auto_repeat_days` | `self` | `` |  |
| `update_auto_repeat_id` | `self` | `` |  |
| `update_status` | `self` | `` |  |
| `is_completed` | `self` | `` |  |
| `get_auto_repeat_schedule` | `self` | `` |  |
| `create_documents` | `self` | `` |  |
| `make_new_document` | `self` | `` |  |
| `update_doc` | `self, new_doc, reference_doc` | `` |  |
| `set_auto_repeat_period` | `self, new_doc` | `` |  |
| `get_next_schedule_date` | `self, schedule_date, for_full_schedule` | `` | Return the next schedule date for auto repeat after a recurring document has been created.
Add required offset to the schedule_date param and return the next schedule date.

:param schedule_date: The date when the last recurring document was created.
:param for_full_schedule: If True, return the immediate next schedule date, else the full schedule. |
| `get_days` | `self, schedule_date` | `` |  |
| `get_offset_for_weekly_frequency` | `self, schedule_date` | `` |  |
| `get_auto_repeat_days` | `self` | `` |  |
| `send_notification` | `self, new_doc` | `` | Notify concerned people about recurring document generation |
| `fetch_linked_contacts` | `self` | `` |  |
| `disable_auto_repeat` | `self` | `` |  |
| `notify_error_to_user` | `self, error_log` | `` |  |





## Functions

### `get_next_date`
**Arguments:** `dt, mcount, day`
**Decorators:** ``

**Docstring:**
```

```
### `get_next_weekday`
**Arguments:** `current_schedule_day, weekdays`
**Decorators:** ``

**Docstring:**
```

```
### `make_auto_repeat_entry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_repeated_entries`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `get_auto_repeat_entries`
**Arguments:** `date`
**Decorators:** ``

**Docstring:**
```

```
### `make_auto_repeat`
**Arguments:** `doctype, docname, frequency, start_date, end_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_auto_repeat_doctypes`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `update_reference`
**Arguments:** `docname, reference`
**Decorators:** ``

**Docstring:**
```

```
### `generate_message_preview`
**Arguments:** `reference_dt, reference_doc, message, subject`
**Decorators:** ``

**Docstring:**
```

```

