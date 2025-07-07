# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/user_type/user_type.py`

## Classes

### `UserType`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `clear_cache` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `set_modules` | `self` | `` |  |
| `validate_document_type_limit` | `self` | `` |  |
| `validate_role` | `self` | `` |  |
| `update_users` | `self` | `` |  |
| `update_roles_in_user` | `self, user` | `` |  |
| `update_modules_in_user` | `self, user` | `` |  |
| `add_role_permissions_for_user_doctypes` | `self` | `` |  |
| `add_select_perm_doctypes` | `self` | `` |  |
| `prepare_select_perm_doctypes` | `self, doc, user_doctypes, select_doctypes` | `` |  |
| `add_role_permissions_for_select_doctypes` | `self` | `` |  |
| `add_role_permissions_for_file` | `self` | `` |  |
| `remove_permission_for_deleted_doctypes` | `self` | `` |  |





## Functions

### `add_role_permissions`
**Arguments:** `doctype, role`
**Decorators:** ``

**Docstring:**
```

```
### `get_non_standard_user_types`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_user_linked_doctypes`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_id`
**Arguments:** `parent`
**Decorators:** ``

**Docstring:**
```

```
### `user_linked_with_permission_on_doctype`
**Arguments:** `doc, user`
**Decorators:** ``

**Docstring:**
```

```
### `apply_permissions_for_non_standard_user_type`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Create user permission for the non standard user type
```

