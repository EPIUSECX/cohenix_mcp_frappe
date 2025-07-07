# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/sync.py`

## Classes

No classes found in this file.


## Functions

### `sync_all`
**Arguments:** `force, reset_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `sync_for`
**Arguments:** `app_name, force, reset_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `get_doc_files`
**Arguments:** `files, start_path`
**Decorators:** ``

**Docstring:**
```
walk and sync all doctypes and pages
```
### `remove_orphan_doctypes`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Find and remove any orphaned doctypes.

These are doctypes for which code and schema file is
deleted but entry is present in DocType table.

Note: Deleting the entry doesn't delete any data.
So this is supposed to be non-destrictive operation.
```

