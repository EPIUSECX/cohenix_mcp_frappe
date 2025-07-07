# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/notifications.py`

## Classes

No classes found in this file.


## Functions

### `get_notifications`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_notifications_for_doctypes`
**Arguments:** `config, notification_count`
**Decorators:** ``

**Docstring:**
```
Notifications for DocTypes
```
### `get_notifications_for_targets`
**Arguments:** `config, notification_percent`
**Decorators:** ``

**Docstring:**
```
Notifications for doc targets
```
### `clear_notifications`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `clear_notification_config`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `delete_notification_count_for`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `clear_doctype_notifications`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```

```
### `get_notification_info`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_notification_config`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_filters_for`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
get open filters for doctype
```
### `get_open_count`
**Arguments:** `doctype, name, items`
**Decorators:** ``

**Docstring:**
```
Get count for internal and external links for given transactions

:param doctype: Reference DocType
:param name: Reference Name
:param items: Optional list of transactions (json/dict)
```
### `_get_linked_document_counts`
**Arguments:** `doctype, name, items`
**Decorators:** ``

**Docstring:**
```

```
### `get_internal_links`
**Arguments:** `doc, link, link_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_external_links`
**Arguments:** `doctype, name, links`
**Decorators:** ``

**Docstring:**
```

```
### `get_doc_count`
**Arguments:** `doctype, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_dynamic_link_filters`
**Arguments:** `doctype, links, fieldname`
**Decorators:** ``

**Docstring:**
```
- Updating filters based on dynamic_links specified in the dashboard data.
- Eg: "dynamic_links": {"fieldname": ["dynamic_fieldvalue", "dynamic_fieldname"]},
```
### `notify_mentions`
**Arguments:** `ref_doctype, ref_name, content`
**Decorators:** ``

**Docstring:**
```

```
### `extract_mentions`
**Arguments:** `txt`
**Decorators:** ``

**Docstring:**
```
Find all instances of @mentions in the html.
```

