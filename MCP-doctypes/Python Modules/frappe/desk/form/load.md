# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/form/load.py`

## Classes

No classes found in this file.


## Functions

### `getdoc`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Loads a doclist for a given document. This method is called directly from the client.
Requries "doctype", "name" as form variables.
Will also call the "onload" method on the document.
```
### `getdoctype`
**Arguments:** `doctype, with_parent`
**Decorators:** ``

**Docstring:**
```
load doctype
```
### `get_meta_bundle`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_docinfo`
**Arguments:** `doc, doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `add_comments`
**Arguments:** `doc, docinfo`
**Decorators:** ``

**Docstring:**
```

```
### `get_milestones`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_attachments`
**Arguments:** `dt, dn`
**Decorators:** ``

**Docstring:**
```

```
### `get_versions`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_communications`
**Arguments:** `doctype, name, start, limit`
**Decorators:** ``

**Docstring:**
```

```
### `get_comments`
**Arguments:** `doctype, name, comment_type`
**Decorators:** ``

**Docstring:**
```

```
### `_get_communications`
**Arguments:** `doctype, name, start, limit`
**Decorators:** ``

**Docstring:**
```

```
### `get_communication_data`
**Arguments:** `doctype, name, start, limit, after, fields, group_by, as_dict`
**Decorators:** ``

**Docstring:**
```
Return list of communications for a given document.
```
### `get_assignments`
**Arguments:** `dt, dn`
**Decorators:** ``

**Docstring:**
```

```
### `run_onload`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_view_logs`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
get and return the latest view logs if available
```
### `get_tags`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_document_email`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_additional_timeline_content`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `set_link_titles`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_title_values_for_link_and_dynamic_link_fields`
**Arguments:** `doc, link_fields`
**Decorators:** ``

**Docstring:**
```

```
### `get_title_values_for_table_and_multiselect_fields`
**Arguments:** `doc, table_fields`
**Decorators:** ``

**Docstring:**
```

```
### `send_link_titles`
**Arguments:** `link_titles`
**Decorators:** ``

**Docstring:**
```
Append link titles dict in `frappe.local.response`.
```
### `update_user_info`
**Arguments:** `docinfo`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_info_for_viewers`
**Arguments:** `users`
**Decorators:** ``

**Docstring:**
```

```

