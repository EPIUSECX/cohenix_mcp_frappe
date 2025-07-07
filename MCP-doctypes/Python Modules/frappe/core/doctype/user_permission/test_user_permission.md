# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/user_permission/test_user_permission.py`

## Classes

### `TestUserPermission`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_default_user_permission_validation` | `self` | `` |  |
| `test_default_user_permission_corectness` | `self` | `` |  |
| `test_default_user_permission` | `self` | `` |  |
| `test_apply_to_all` | `self` | `` | Create User permission for User having access to all applicable Doctypes |
| `test_for_apply_to_all_on_update_from_apply_all` | `self` | `` |  |
| `test_for_applicable_on_update_from_apply_to_all` | `self` | `` | Update User Permission from all to some applicable Doctypes |
| `test_for_apply_to_all_on_update_from_applicable` | `self` | `` | Update User Permission from some to all applicable Doctypes |
| `test_user_perm_for_nested_doctype` | `self` | `` | Test if descendants' visibility is controlled for a nested DocType. |
| `test_user_perm_on_new_doc_with_field_default` | `self` | `` | Test User Perm impact on frappe.new_doc. with *field* default value |
| `test_user_perm_on_new_doc_with_user_default` | `self` | `` | Test User Perm impact on frappe.new_doc. with *user* default value |





## Functions

### `create_user`
**Arguments:** `email`
**Decorators:** ``

**Docstring:**
```
create user with role system manager
```
### `get_params`
**Arguments:** `user, doctype, docname, is_default, hide_descendants, applicable`
**Decorators:** ``

**Docstring:**
```
Return param to insert
```
### `get_exists_param`
**Arguments:** `user, applicable`
**Decorators:** ``

**Docstring:**
```
param to check existing Document
```

