# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/integrations/google_oauth.py`

## Classes

### `GoogleAuthenticationError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `GoogleOAuth`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, domain, validate, config` | `` |  |
| `validate_google_settings` | `self` | `` |  |
| `authorize` | `self, oauth_code` | `` | Return a dict with access and refresh token.

:param oauth_code: code got back from google upon successful auhtorization |
| `refresh_access_token` | `self, refresh_token` | `` | Refreshes google access token using refresh token |
| `get_authentication_url` | `self, state` | `` | Return Google authentication url.

:param state: dict of values which you need on callback (for calling methods, redirection back to the form, doc name, etc) |
| `get_google_service_object` | `self, access_token, refresh_token` | `` | Return Google service object. |





## Functions

### `handle_response`
**Arguments:** `response, error_title, error_message, raise_err`
**Decorators:** ``

**Docstring:**
```

```
### `is_valid_access_token`
**Arguments:** `access_token`
**Decorators:** ``

**Docstring:**
```

```
### `callback`
**Arguments:** `state, code, error`
**Decorators:** ``

**Docstring:**
```
Common callback for google integrations.
Invokes functions using `frappe.get_attr` and also adds required (keyworded) arguments
along with committing and redirecting us back to frappe site.
```

