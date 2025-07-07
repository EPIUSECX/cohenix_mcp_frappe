# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/cache_manager.py`

## Classes

No classes found in this file.


## Functions

### `get_doctype_map_key`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `clear_user_cache`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `clear_domain_cache`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `clear_global_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `clear_defaults_cache`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `clear_doctype_cache`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `_clear_doctype_cache_from_redis`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `clear_controller_cache`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_doctype_map`
**Arguments:** `doctype, name, filters, order_by`
**Decorators:** ``

**Docstring:**
```

```
### `clear_doctype_map`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `build_table_count_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `build_domain_restricted_doctype_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `build_domain_restricted_page_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `clear_cache`
**Arguments:** `user, doctype`
**Decorators:** ``

**Docstring:**
```
Clear **User**, **DocType** or global cache.

:param user: If user is given, only user cache is cleared.
:param doctype: If doctype is given, only DocType cache is cleared.
```
### `reset_metadata_version`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Reset `metadata_version` (Client (Javascript) build ID) hash.
```

