# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/file_lock.py`

## Classes

### `LockTimeoutError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `create_lock`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
Creates a file in the /locks folder by the given name.

Note: This is a "weak lock" and is prone to race conditions. Do not use this lock for small
sections of code that execute immediately.

This is primarily use for locking documents for background submission.
```
### `lock_exists`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
Return True if lock of the given name exists.
```
### `lock_age`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
Return time in seconds since lock was created.
```
### `check_lock`
**Arguments:** `path, timeout`
**Decorators:** ``

**Docstring:**
```

```
### `delete_lock`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `get_lock_path`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `release_document_locks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Unlocks all documents that were locked by the current context.
```

