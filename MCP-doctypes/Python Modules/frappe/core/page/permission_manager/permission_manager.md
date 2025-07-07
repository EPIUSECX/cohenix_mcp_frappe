# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/page/permission_manager/permission_manager.py`

## Classes

No classes found in this file.


## Functions

### `get_roles_and_doctypes`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_permissions`
**Arguments:** `doctype, role`
**Decorators:** ``

**Docstring:**
```

```
### `add`
**Arguments:** `parent, role, permlevel`
**Decorators:** ``

**Docstring:**
```

```
### `update`
**Arguments:** `doctype, role, permlevel, ptype, value, if_owner`
**Decorators:** ``

**Docstring:**
```
Update role permission params.

Args:
        doctype (str): Name of the DocType to update params for
        role (str): Role to be updated for, eg "Website Manager".
        permlevel (int): perm level the provided rule applies to
        ptype (str): permission type, example "read", "delete", etc.
        value (None, optional): value for ptype, None indicates False

Return:
        str: Refresh flag if permission is updated successfully
```
### `remove`
**Arguments:** `doctype, role, permlevel, if_owner`
**Decorators:** ``

**Docstring:**
```

```
### `reset`
**Arguments:** `doctype`
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
### `get_standard_permissions`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```

