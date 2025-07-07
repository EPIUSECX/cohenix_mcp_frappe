# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/notification_log/notification_log.py`

## Classes

### `NotificationLog`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `after_insert` | `self` | `` |  |
| `clear_old_logs` | `days` | `staticmethod` |  |





## Functions

### `get_permission_query_conditions`
**Arguments:** `for_user`
**Decorators:** ``

**Docstring:**
```

```
### `get_title`
**Arguments:** `doctype, docname, title_field`
**Decorators:** ``

**Docstring:**
```

```
### `get_title_html`
**Arguments:** `title`
**Decorators:** ``

**Docstring:**
```

```
### `enqueue_create_notification`
**Arguments:** `users, doc`
**Decorators:** ``

**Docstring:**
```
Send notification to users.

users: list of user emails or string of users with comma separated emails
doc: contents of `Notification` doc
```
### `make_notification_logs`
**Arguments:** `doc, users`
**Decorators:** ``

**Docstring:**
```

```
### `_get_user_ids`
**Arguments:** `user_emails`
**Decorators:** ``

**Docstring:**
```

```
### `send_notification_email`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_email_header`
**Arguments:** `doc, language`
**Decorators:** ``

**Docstring:**
```

```
### `format_email_header`
**Arguments:** `header_map, language, docname`
**Decorators:** ``

**Docstring:**
```

```
### `get_notification_logs`
**Arguments:** `limit`
**Decorators:** ``

**Docstring:**
```

```
### `mark_all_as_read`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `mark_as_read`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```

```
### `trigger_indicator_hide`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `set_notifications_as_unseen`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```

