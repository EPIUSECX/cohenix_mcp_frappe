# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/permissions.py`

## Classes

No classes found in this file.


## Functions

### `print_has_permission_check_logs`
**Arguments:** `func`
**Decorators:** ``

**Docstring:**
```

```
### `_debug_log`
**Arguments:** `log`
**Decorators:** ``

**Docstring:**
```

```
### `_pop_debug_log`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `has_permission`
**Arguments:** `doctype, ptype, doc, user`
**Decorators:** `print_has_permission_check_logs`

**Docstring:**
```
Return True if user has permission `ptype` for given `doctype`.
If `doc` is passed, also check user, share and owner permissions.

:param doctype: DocType to check permission for
:param ptype: Permission Type to check
:param doc: Check User Permissions for specified document.
:param user: User to check permission for. Defaults to current user.
:param print_logs: If True, will display a message using frappe.msgprint
                which explains why the permission check failed.
:param parent_doctype:
        Required when checking permission for a child DocType (unless doc is specified)
```
### `get_doc_permissions`
**Arguments:** `doc, user, ptype, debug`
**Decorators:** ``

**Docstring:**
```
Return a dict of evaluated permissions for given `doc` like `{"read":1, "write":1}`
```
### `get_role_permissions`
**Arguments:** `doctype_meta, user, is_owner, debug`
**Decorators:** ``

**Docstring:**
```
Return dict of evaluated role permissions like:
        {
                "read": 1,
                "write": 0,
                // if "if_owner" is enabled
                "if_owner":
                        {
                                "read": 1,
                                "write": 0
                        }
        }
```
### `get_user_permissions`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `has_user_permission`
**Arguments:** `doc, user, debug`
**Decorators:** ``

**Docstring:**
```
Return True if User is allowed to view considering User Permissions.
```
### `has_controller_permissions`
**Arguments:** `doc, ptype, user, debug`
**Decorators:** ``

**Docstring:**
```
Return controller permissions if denied, True if not defined.

Controllers can only deny permission, they can not explicitly grant any permission that wasn't
already present.
```
### `get_doctypes_with_read`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_valid_perms`
**Arguments:** `doctype, user`
**Decorators:** ``

**Docstring:**
```
Get valid permissions for the current user from DocPerm and Custom DocPerm
```
### `get_all_perms`
**Arguments:** `role`
**Decorators:** ``

**Docstring:**
```
Return valid permissions for a given role.
```
### `get_roles`
**Arguments:** `user, with_standard`
**Decorators:** ``

**Docstring:**
```
get roles of current user
```
### `get_doctype_roles`
**Arguments:** `doctype, access_type`
**Decorators:** ``

**Docstring:**
```
Return a list of roles that are allowed to access the given `doctype`.
```
### `get_perms_for`
**Arguments:** `roles, perm_doctype`
**Decorators:** ``

**Docstring:**
```
Get perms for given roles
```
### `get_doctypes_with_custom_docperms`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return all the doctypes with Custom Docperms.
```
### `add_user_permission`
**Arguments:** `doctype, name, user, ignore_permissions, applicable_for, is_default, hide_descendants`
**Decorators:** ``

**Docstring:**
```
Add user permission
```
### `remove_user_permission`
**Arguments:** `doctype, name, user`
**Decorators:** ``

**Docstring:**
```

```
### `clear_user_permissions_for_doctype`
**Arguments:** `doctype, user`
**Decorators:** ``

**Docstring:**
```

```
### `can_import`
**Arguments:** `doctype, raise_exception`
**Decorators:** ``

**Docstring:**
```

```
### `can_export`
**Arguments:** `doctype, raise_exception, is_owner`
**Decorators:** ``

**Docstring:**
```

```
### `update_permission_property`
**Arguments:** `doctype, role, permlevel, ptype, value, validate, if_owner`
**Decorators:** ``

**Docstring:**
```
Update a property in Custom Perm
```
### `setup_custom_perms`
**Arguments:** `parent`
**Decorators:** ``

**Docstring:**
```
if custom permssions are not setup for the current doctype, set them up
```
### `add_permission`
**Arguments:** `doctype, role, permlevel, ptype`
**Decorators:** ``

**Docstring:**
```
Add a new permission rule to the given doctype
for the given Role and Permission Level
```
### `copy_perms`
**Arguments:** `parent`
**Decorators:** ``

**Docstring:**
```
Copy all DocPerm in to Custom DocPerm for the given document
```
### `reset_perms`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Reset permissions for given doctype.
```
### `get_linked_doctypes`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```

```
### `get_doc_name`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `allow_everything`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return a dict with access to everything, eg. {"read": 1, "write": 1, ...}.
```
### `get_allowed_docs_for_doctype`
**Arguments:** `user_permissions, doctype`
**Decorators:** ``

**Docstring:**
```
Return all the docs from the passed `user_permissions` that are allowed under provided doctype.
```
### `filter_allowed_docs_for_doctype`
**Arguments:** `user_permissions, doctype, with_default_doc`
**Decorators:** ``

**Docstring:**
```
Return all the docs from the passed `user_permissions` that are
allowed under provided doctype along with default doc value if `with_default_doc` is set.
```
### `push_perm_check_log`
**Arguments:** `log, debug`
**Decorators:** ``

**Docstring:**
```

```
### `has_child_permission`
**Arguments:** `child_doctype, ptype, child_doc, user, parent_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `is_system_user`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `check_doctype_permission`
**Arguments:** `doctype, ptype`
**Decorators:** ``

**Docstring:**
```
Designed specfically to override DoesNotExistError in some scenarios.
Ignores share permissions.
```
### `handle_does_not_exist_error`
**Arguments:** `fn`
**Decorators:** ``

**Docstring:**
```
Decorator to override DoesNotExistError when handling exceptions.
Requires the first argument to be an Exception.
```
### `_get_parent_and_ancestors`
**Arguments:** `doctype, parent`
**Decorators:** ``

**Docstring:**
```

```

