# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/sessions.py`

## Classes

### `Session`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, user, resume, full_name, user_type, session_end, audit_user` | `` |  |
| `validate_user` | `self` | `` |  |
| `start` | `self, session_end, audit_user` | `` | start a new session |
| `insert_session_record` | `self` | `` |  |
| `resume` | `self` | `` | non-login request: load a session |
| `get_session_record` | `self` | `` | get session record, or return the standard Guest Record |
| `get_session_data` | `self` | `` |  |
| `get_session_data_from_cache` | `self` | `` |  |
| `get_session_data_from_db` | `self` | `` |  |
| `_delete_session` | `self` | `` |  |
| `start_as_guest` | `self` | `` | all guests share the same 'Guest' session |
| `update` | `self, force` | `` | extend session expiry |
| `set_impersonated` | `self, original_user` | `` |  |





## Functions

### `clear`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `clear_sessions`
**Arguments:** `user, keep_current, force`
**Decorators:** ``

**Docstring:**
```
Clear other sessions of the current user. Called at login / logout

:param user: user name (default: current user)
:param keep_current: keep current session (default: false)
:param force: triggered by the user (default false)
```
### `get_sessions_to_clear`
**Arguments:** `user, keep_current, force`
**Decorators:** ``

**Docstring:**
```
Return sessions of the current user. Called at login / logout.

:param user: user name (default: current user)
:param keep_current: keep current session (default: false)
:param force: ignore simultaneous sessions count, log the user out of all except current (default: false)
```
### `delete_session`
**Arguments:** `sid, user, reason`
**Decorators:** ``

**Docstring:**
```

```
### `clear_all_sessions`
**Arguments:** `reason`
**Decorators:** ``

**Docstring:**
```
This effectively logs out all users
```
### `get_expired_sessions`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return list of expired sessions.
```
### `clear_expired_sessions`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
This function is meant to be called from scheduler
```
### `get`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
get session boot info
```
### `get_boot_assets_json`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_csrf_token`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `generate_csrf_token`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_expiry_period_for_query`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_expiry_in_seconds`
**Arguments:** `expiry`
**Decorators:** ``

**Docstring:**
```

```
### `get_expired_threshold`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get cutoff time before which all sessions are considered expired.
```
### `get_expiry_period`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

