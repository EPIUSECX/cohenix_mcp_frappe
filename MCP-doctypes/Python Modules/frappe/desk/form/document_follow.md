# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/form/document_follow.py`

## Classes

No classes found in this file.


## Functions

### `update_follow`
**Arguments:** `doctype, doc_name, following`
**Decorators:** ``

**Docstring:**
```

```
### `follow_document`
**Arguments:** `doctype, doc_name, user`
**Decorators:** ``

**Docstring:**
```
param:
Doctype name
doc name
user email

condition:
avoided for some doctype
follow only if track changes are set to 1
```
### `unfollow_document`
**Arguments:** `doctype, doc_name, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_message`
**Arguments:** `doc_name, doctype, frequency, user`
**Decorators:** ``

**Docstring:**
```

```
### `send_email_alert`
**Arguments:** `receiver, docinfo, timeline`
**Decorators:** ``

**Docstring:**
```

```
### `send_document_follow_mails`
**Arguments:** `frequency`
**Decorators:** ``

**Docstring:**
```
param:
frequency for sanding mails

task:
set receiver according to frequency
group document list according to user
get changes, activity, comments on doctype
call method to send mail
```
### `get_user_list`
**Arguments:** `frequency`
**Decorators:** ``

**Docstring:**
```

```
### `get_message_for_user`
**Arguments:** `frequency, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_document_followed_by_user`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_version`
**Arguments:** `doctype, doc_name, frequency, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_comments`
**Arguments:** `doctype, doc_name, frequency, user`
**Decorators:** ``

**Docstring:**
```

```
### `is_document_followed`
**Arguments:** `doctype, doc_name, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_follow_users`
**Arguments:** `doctype, doc_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_row_changed`
**Arguments:** `row_changed, time, doctype, doc_name, v`
**Decorators:** ``

**Docstring:**
```

```
### `get_added_row`
**Arguments:** `added, time, doctype, doc_name, v`
**Decorators:** ``

**Docstring:**
```

```
### `get_field_changed`
**Arguments:** `changed, time, doctype, doc_name, v`
**Decorators:** ``

**Docstring:**
```

```
### `send_hourly_updates`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `send_daily_updates`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `send_weekly_updates`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_get_filters`
**Arguments:** `frequency, user`
**Decorators:** ``

**Docstring:**
```

```

