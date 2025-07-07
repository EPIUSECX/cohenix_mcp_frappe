# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/user_permission/user_permission.py`

## Classes

### `UserPermission`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate_user_permission` | `self` | `` | checks for duplicate user permission records |
| `validate_default_permission` | `self` | `` | validate user permission overlap for default value of a particular doctype |
| `get_permission_log_options` | `self, event` | `` |  |





## Functions

### `send_user_permissions`
**Arguments:** `bootinfo`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_permissions`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Get all users permissions for the user as a dict of doctype
```
### `user_permission_exists`
**Arguments:** `user, allow, for_value, applicable_for`
**Decorators:** ``

**Docstring:**
```
Checks if similar user permission already exists
```
### `get_applicable_for_doctype_list`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_permitted_documents`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Return permitted documents from the given doctype for the session user.
```
### `check_applicable_doc_perm`
**Arguments:** `user, doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `clear_user_permissions`
**Arguments:** `user, for_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `add_user_permissions`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```
Add and update the user permissions
```
### `insert_user_perm`
**Arguments:** `user, doctype, docname, is_default, hide_descendants, apply_to_all, applicable`
**Decorators:** ``

**Docstring:**
```

```
### `remove_applicable`
**Arguments:** `perm_applied_docs, user, doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `remove_apply_to_all`
**Arguments:** `user, doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `update_applicable`
**Arguments:** `already_applied, to_apply, user, doctype, docname`
**Decorators:** ``

**Docstring:**
```

```

