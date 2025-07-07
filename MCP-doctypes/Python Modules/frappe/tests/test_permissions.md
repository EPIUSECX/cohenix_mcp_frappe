# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_permissions.py`

## Classes

### `TestPermissions`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `set_strict_user_permissions` | `ignore` | `staticmethod` |  |
| `test_basic_permission` | `self` | `` |  |
| `test_select_permission` | `self` | `` |  |
| `test_user_permissions_in_doc` | `self` | `` |  |
| `test_user_permissions_in_report` | `self` | `` |  |
| `test_default_values` | `self` | `` |  |
| `test_user_link_match_doc` | `self` | `` |  |
| `test_user_link_match_report` | `self` | `` |  |
| `test_set_user_permissions` | `self` | `` |  |
| `test_not_allowed_to_set_user_permissions` | `self` | `` |  |
| `test_read_if_explicit_user_permissions_are_set` | `self` | `` |  |
| `test_not_allowed_to_remove_user_permissions` | `self` | `` |  |
| `test_user_permissions_if_applied_on_doc_being_evaluated` | `self` | `` |  |
| `test_set_standard_fields_manually` | `self` | `` |  |
| `test_dont_change_standard_constants` | `self` | `` |  |
| `test_set_only_once` | `self` | `` |  |
| `test_set_only_once_child_table_rows` | `self` | `` |  |
| `test_set_only_once_child_table_row_value` | `self` | `` |  |
| `test_set_only_once_child_table_okay` | `self` | `` |  |
| `test_user_permission_doctypes` | `self` | `` |  |
| `if_owner_setup` | `self` | `` |  |
| `test_insert_if_owner_with_user_permissions` | `self` | `` | If `If Owner` is checked for a Role, check if that document
is allowed to be read, updated, submitted, etc. except be created,
even if the document is restricted based on User Permissions. |
| `test_ignore_user_permissions_if_missing` | `self` | `` | If there are no user permissions, then allow as per role |
| `test_strict_user_permissions` | `self` | `` | If `Strict User Permissions` is checked in System Settings,
show records even if User Permissions are missing for a linked
doctype |
| `test_user_permission_is_not_applied_if_user_roles_does_not_have_permission` | `self` | `` |  |
| `test_contextual_user_permission` | `self` | `` |  |
| `test_if_owner_permission_overrides_properly` | `self` | `` |  |
| `test_if_owner_permission_on_getdoc` | `self` | `` |  |
| `test_if_owner_permission_on_get_list` | `self` | `` |  |
| `test_if_owner_permission_on_delete` | `self` | `` |  |
| `test_clear_user_permissions` | `self` | `` |  |
| `test_child_permissions` | `self` | `` |  |
| `test_select_user` | `self` | `` | If test3@example.com is restricted by a User Permission to see only
users linked to a certain doctype (in this case: Gender "Female"), he
should not be able to query other users (Gender "Male"). |
| `test_automatic_permissions` | `self` | `` |  |
| `test_get_doctypes_with_read` | `self` | `` |  |
| `test_overrides_work_as_expected` | `self` | `` | custom docperms should completely override standard ones |





## Functions

No top-level functions found in this file.
