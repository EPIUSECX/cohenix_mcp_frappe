# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/defaults.py`

## Classes

No classes found in this file.


## Functions

### `set_user_default`
**Arguments:** `key, value, user, parenttype`
**Decorators:** ``

**Docstring:**
```

```
### `add_user_default`
**Arguments:** `key, value, user, parenttype`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_default`
**Arguments:** `key, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_permission_default`
**Arguments:** `key, defaults`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_default_as_list`
**Arguments:** `key, user`
**Decorators:** ``

**Docstring:**
```

```
### `is_a_user_permission_key`
**Arguments:** `key`
**Decorators:** ``

**Docstring:**
```

```
### `not_in_user_permission`
**Arguments:** `key, value, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_permissions`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_defaults`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `clear_user_default`
**Arguments:** `key, user`
**Decorators:** ``

**Docstring:**
```

```
### `set_global_default`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```

```
### `add_global_default`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```

```
### `get_global_default`
**Arguments:** `key`
**Decorators:** ``

**Docstring:**
```

```
### `set_default`
**Arguments:** `key, value, parent, parenttype`
**Decorators:** ``

**Docstring:**
```
Override or add a default value.
Adds default value in table `tabDefaultValue`.

:param key: Default key.
:param value: Default value.
:param parent: Usually, **User** to whom the default belongs.
:param parenttype: [optional] default is `__default`.
```
### `add_default`
**Arguments:** `key, value, parent, parenttype`
**Decorators:** ``

**Docstring:**
```

```
### `clear_default`
**Arguments:** `key, value, parent, name, parenttype`
**Decorators:** ``

**Docstring:**
```
Clear a default value by any of the given parameters and delete caches.

:param key: Default key.
:param value: Default value.
:param parent: User name, or `__global`, `__default`.
:param name: Default ID.
:param parenttype: Clear defaults table for a particular type e.g. **User**.
```
### `get_defaults_for`
**Arguments:** `parent`
**Decorators:** ``

**Docstring:**
```
get all defaults
```
### `_clear_cache`
**Arguments:** `parent`
**Decorators:** ``

**Docstring:**
```

```

