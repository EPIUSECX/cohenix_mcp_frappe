# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/daily_work_summary/daily_work_summary.py`

## Classes

### `DailyWorkSummary`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `send_mails` | `self, dws_group, emails` | `` | Send emails to get daily work summary to all users                      in selected daily work summary group |
| `send_summary` | `self` | `` | Send summary of all replies. Called at midnight |
| `get_message_details` | `self` | `` | Return args for template |





## Functions

### `get_user_emails_from_group`
**Arguments:** `group`
**Decorators:** ``

**Docstring:**
```
Returns list of email of enabled users from the given group

:param group: Daily Work Summary Group `name`
```
### `get_users_email`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```

