# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/auth.py`

## Classes

### `HTTPRequest`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `domain` | `self` | `property` |  |
| `set_request_ip` | `self` | `` |  |
| `set_cookies` | `self` | `` |  |
| `set_session` | `self` | `` |  |
| `validate_csrf_token` | `self` | `` |  |
| `set_lang` | `self` | `` |  |
| `is_allowed_referrer` | `self` | `` |  |


### `LoginManager`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `login` | `self` | `` |  |
| `post_login` | `self, session_end, audit_user` | `` |  |
| `get_user_info` | `self` | `` |  |
| `setup_boot_cache` | `self` | `` |  |
| `set_user_info` | `self, resume` | `` |  |
| `clear_preferred_language` | `self` | `` |  |
| `make_session` | `self, resume, session_end, audit_user` | `` |  |
| `clear_active_sessions` | `self` | `` | Clear other sessions of the current user if `deny_multiple_sessions` is not set |
| `authenticate` | `self, user, pwd` | `` |  |
| `force_user_to_reset_password` | `self` | `` |  |
| `check_password` | `self, user, pwd` | `` | check password |
| `fail` | `self, message, user` | `` |  |
| `run_trigger` | `self, event` | `` |  |
| `validate_hour` | `self` | `` | check if user is logging in during restricted hours |
| `login_as_guest` | `self` | `` | login as guest |
| `login_as` | `self, user, session_end, audit_user` | `` |  |
| `impersonate` | `self, user` | `` |  |
| `logout` | `self, arg, user` | `` |  |
| `clear_cookies` | `self` | `` |  |


### `CookieManager`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `init_cookies` | `self` | `` |  |
| `set_cookie` | `self, key, value, expires, secure, httponly, samesite, max_age, deduplicate` | `` |  |
| `delete_cookie` | `self, to_delete` | `` |  |
| `flush_cookies` | `self, response` | `` |  |


### `LoginAttemptTracker`


**Docstring:**
```
Track login attemts of a user.

Lock the account for s number of seconds if there have been n consecutive unsuccessful attempts to log in.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, key, max_consecutive_login_attempts, lock_interval` | `` | Initialize the tracker.

:param user_name: Name of the loggedin user
:param max_consecutive_login_attempts: Maximum allowed consecutive failed login attempts
:param lock_interval: Locking interval incase of maximum failed attempts |
| `login_failed_count` | `self` | `property` |  |
| `login_failed_count` | `self, count` | `` |  |
| `login_failed_count` | `self` | `` |  |
| `login_failed_time` | `self` | `property` | First failed login attempt time within lock interval.

For every user we track only First failed login attempt time within lock interval of time. |
| `login_failed_time` | `self, timestamp` | `` |  |
| `login_failed_time` | `self` | `` |  |
| `add_failure_attempt` | `self` | `` | Log user failure attempts into the system.

Increase the failure count if new failure is with in current lock interval time period, if not reset the login failure count. |
| `add_success_attempt` | `self` | `` | Reset login failures. |
| `is_user_allowed` | `self` | `` | Is user allowed to login

User is not allowed to login if login failures are greater than threshold within in lock interval from first login failure. |





## Functions

### `get_logged_user`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `clear_cookies`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `validate_ip_address`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Method to check if the user has IP restrictions enabled, and if so is the IP address they are
connecting from allowlisted.

Certain methods called from our socketio backend need direct access, and so the IP is not
checked for those
```
### `get_login_attempt_tracker`
**Arguments:** `key, raise_locked_exception`
**Decorators:** ``

**Docstring:**
```
Get login attempt tracker instance.

:param user_name: Name of the loggedin user
:param raise_locked_exception: If set, raises an exception incase of user not allowed to login
```
### `validate_auth`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Authenticate and sets user for the request.
```
### `validate_oauth`
**Arguments:** `authorization_header`
**Decorators:** ``

**Docstring:**
```
Authenticate request using OAuth and set session user

Args:
        authorization_header (list of str): The 'Authorization' header containing the prefix and token
```
### `validate_auth_via_api_keys`
**Arguments:** `authorization_header`
**Decorators:** ``

**Docstring:**
```
Authenticate request using API keys and set session user

Args:
        authorization_header (list of str): The 'Authorization' header containing the prefix and token
```
### `validate_api_key_secret`
**Arguments:** `api_key, api_secret, frappe_authorization_source`
**Decorators:** ``

**Docstring:**
```
frappe_authorization_source to provide api key and secret for a doctype apart from User
```
### `validate_auth_via_hooks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `check_request_ip`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

