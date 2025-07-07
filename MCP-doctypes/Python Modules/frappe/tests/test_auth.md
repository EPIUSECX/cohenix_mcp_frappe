# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_auth.py`

## Classes

### `TestAuth`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `set_system_settings` | `self, k, v` | `` |  |
| `test_allow_login_using_mobile` | `self` | `` |  |
| `test_allow_login_using_only_email` | `self` | `` |  |
| `test_allow_login_using_username` | `self` | `` |  |
| `test_allow_login_using_username_and_mobile` | `self` | `` |  |
| `test_deny_multiple_login` | `self` | `` |  |
| `test_disable_user_pass_login` | `self` | `` |  |
| `test_login_with_email_link` | `self` | `` |  |
| `test_correct_cookie_expiry_set` | `self` | `` |  |


### `TestAllowedReferrer`
**Inherits:** `UnitTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_is_allowed_referrer` | `self` | `` |  |


### `TestLoginAttemptTracker`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_account_lock` | `self` | `` | Make sure that account locks after `n consecutive failures |
| `test_account_unlock` | `self` | `` | Make sure that locked account gets unlocked after lock_interval of time. |


### `TestSessionExpirty`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_session_expires` | `self` | `` |  |





## Functions

### `add_user`
**Arguments:** `email, password, username, mobile_no`
**Decorators:** ``

**Docstring:**
```

```

