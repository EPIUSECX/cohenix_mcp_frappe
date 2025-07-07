# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/password.py`

## Classes

No classes found in this file.


## Functions

### `get_decrypted_password`
**Arguments:** `doctype, name, fieldname, raise_exception`
**Decorators:** ``

**Docstring:**
```

```
### `set_encrypted_password`
**Arguments:** `doctype, name, pwd, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `remove_encrypted_password`
**Arguments:** `doctype, name, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `check_password`
**Arguments:** `user, pwd, doctype, fieldname, delete_tracker_cache`
**Decorators:** ``

**Docstring:**
```
Checks if user and password are correct, else raises frappe.AuthenticationError
```
### `delete_login_failed_cache`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `update_password`
**Arguments:** `user, pwd, doctype, fieldname, logout_all_sessions`
**Decorators:** ``

**Docstring:**
```
Update the password for the User

:param user: username
:param pwd: new password
:param doctype: doctype name (for encryption)
:param fieldname: fieldname (in given doctype) (for encryption)
:param logout_all_session: delete all other session
```
### `delete_all_passwords_for`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `rename_password`
**Arguments:** `doctype, old_name, new_name`
**Decorators:** ``

**Docstring:**
```

```
### `rename_password_field`
**Arguments:** `doctype, old_fieldname, new_fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `create_auth_table`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `encrypt`
**Arguments:** `txt, encryption_key`
**Decorators:** ``

**Docstring:**
```

```
### `decrypt`
**Arguments:** `txt, encryption_key, key`
**Decorators:** ``

**Docstring:**
```

```
### `get_encryption_key`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_password_reset_limit`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

