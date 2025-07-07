# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/share.py`

## Classes

No classes found in this file.


## Functions

### `add`
**Arguments:** `doctype, name, user, read, write, submit, share, everyone, notify`
**Decorators:** ``

**Docstring:**
```
Expose function without flags to the client-side
```
### `add_docshare`
**Arguments:** `doctype, name, user, read, write, submit, share, everyone, flags, notify`
**Decorators:** ``

**Docstring:**
```
Share the given document with a user.
```
### `remove`
**Arguments:** `doctype, name, user, flags`
**Decorators:** ``

**Docstring:**
```

```
### `set_permission`
**Arguments:** `doctype, name, user, permission_to, value, everyone`
**Decorators:** ``

**Docstring:**
```
Expose function without flags to the client-side
```
### `set_docshare_permission`
**Arguments:** `doctype, name, user, permission_to, value, everyone, flags`
**Decorators:** ``

**Docstring:**
```
Set share permission.
```
### `get_users`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Get list of users with which this document is shared
```
### `_get_users`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_shared`
**Arguments:** `doctype, user, rights`
**Decorators:** ``

**Docstring:**
```
Get list of shared document names for given user and DocType.

:param doctype: DocType of which shared names are queried.
:param user: User for which shared names are queried.
:param rights: List of rights for which the document is shared. List of `read`, `write`, `share`
```
### `get_shared_doctypes`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Return list of doctypes in which documents are shared for the given user.
```
### `get_share_name`
**Arguments:** `doctype, name, user, everyone`
**Decorators:** ``

**Docstring:**
```

```
### `check_share_permission`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Check if the user can share with other users
```
### `notify_assignment`
**Arguments:** `shared_by, doctype, doc_name, everyone, notify`
**Decorators:** ``

**Docstring:**
```

```

