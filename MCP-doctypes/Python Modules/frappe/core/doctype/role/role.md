# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/role/role.py`

## Classes

### `Role`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_rename` | `self, old, new, merge` | `` |  |
| `after_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `disable_role` | `self` | `` |  |
| `validate_homepage` | `self` | `` |  |
| `set_desk_properties` | `self` | `` |  |
| `remove_roles` | `self` | `` |  |
| `on_update` | `self` | `` | update system user desk access if this has changed in this update |
| `update_user_type_on_change` | `self` | `` | When desk access changes, all the users that have this role need to be re-evaluated |





## Functions

### `get_info_based_on_role`
**Arguments:** `role, field, ignore_permissions`
**Decorators:** ``

**Docstring:**
```
Get information of all users that have been assigned this role
```
### `get_user_info`
**Arguments:** `users, field`
**Decorators:** ``

**Docstring:**
```
Fetch details about users for the specified field
```
### `get_users`
**Arguments:** `role`
**Decorators:** ``

**Docstring:**
```

```
### `role_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```

