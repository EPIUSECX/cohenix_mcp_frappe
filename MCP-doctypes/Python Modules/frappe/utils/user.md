# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/user.py`

## Classes

### `UserPermissions`


**Docstring:**
```
A user permission object can be accessed as `frappe.get_user()`
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, name` | `` |  |
| `setup_user` | `self` | `` |  |
| `get_roles` | `self` | `` | get list of roles |
| `build_doctype_map` | `self` | `` | build map of special doctype properties |
| `build_perm_map` | `self` | `` | build map of permissions at level 0 |
| `build_permissions` | `self` | `` | build lists of what the user can read / write / create
quirks:
        read_only => Not in Search
        in_create => Not in create |
| `get_defaults` | `self` | `` |  |
| `_get` | `self, key` | `` |  |
| `get_can_read` | `self` | `` | return list of doctypes that the user can read |
| `load_user` | `self` | `` |  |
| `get_all_reports` | `self` | `` |  |





## Functions

### `get_user_fullname`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_fullname_and_avatar`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_system_managers`
**Arguments:** `only_name`
**Decorators:** ``

**Docstring:**
```
Return all system manager's user details.
```
### `add_role`
**Arguments:** `user, role`
**Decorators:** ``

**Docstring:**
```

```
### `add_system_manager`
**Arguments:** `email, first_name, last_name, send_welcome_email, password`
**Decorators:** ``

**Docstring:**
```

```
### `get_enabled_system_users`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_website_user`
**Arguments:** `username`
**Decorators:** ``

**Docstring:**
```

```
### `is_system_user`
**Arguments:** `username`
**Decorators:** ``

**Docstring:**
```

```
### `get_users`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_users_with_role`
**Arguments:** `role`
**Decorators:** ``

**Docstring:**
```

```

