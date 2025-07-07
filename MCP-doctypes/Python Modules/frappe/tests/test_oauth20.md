# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_oauth20.py`

## Classes

### `FrappeRequestTestCase`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `sid` | `self` | `property` |  |
| `get` | `self, path, params` | `` |  |
| `post` | `self, path, data` | `` |  |
| `put` | `self, path, data` | `` |  |
| `delete` | `self, path` | `` |  |


### `TestOAuth20`
**Inherits:** `FrappeRequestTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_invalid_login` | `self` | `` |  |
| `test_login_using_authorization_code` | `self` | `` |  |
| `test_login_using_authorization_code_with_pkce` | `self` | `` |  |
| `test_revoke_token` | `self` | `` |  |
| `test_resource_owner_password_credentials_grant` | `self` | `` |  |
| `test_login_using_implicit_token` | `self` | `` |  |
| `test_openid_code_id_token` | `self` | `` |  |
| `decode_id_token` | `self, id_token` | `` |  |





## Functions

### `check_valid_openid_response`
**Arguments:** `access_token, client`
**Decorators:** ``

**Docstring:**
```
Return True for valid response.
```
### `login`
**Arguments:** `session`
**Decorators:** ``

**Docstring:**
```

```
### `get_full_url`
**Arguments:** `endpoint`
**Decorators:** ``

**Docstring:**
```
Turn '/endpoint' into 'http://127.0.0.1:8000/endpoint'.
```
### `update_client_for_auth_code_grant`
**Arguments:** `client_id`
**Decorators:** ``

**Docstring:**
```

```

