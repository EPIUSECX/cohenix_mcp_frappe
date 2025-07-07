# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_twofactor.py`

## Classes

### `TestTwoFactor`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_should_run_2fa` | `self` | `` | Should return true if enabled. |
| `test_get_cached_user_pass` | `self` | `` | Cached data should not contain user and pass before 2fa. |
| `test_authenticate_for_2factor` | `self` | `` | Verification obj and tmp_id should be set in frappe.local. |
| `test_two_factor_is_enabled` | `self` | `` | 1. Should return true, if enabled and not bypass_2fa_for_retricted_ip_users
2. Should return false, if not enabled
3. Should return true, if enabled and not bypass_2fa_for_retricted_ip_users and ip in restrict_ip
4. Should return true, if enabled and bypass_2fa_for_retricted_ip_users and not restrict_ip
5. Should return false, if enabled and bypass_2fa_for_retricted_ip_users and ip in restrict_ip |
| `test_two_factor_is_enabled_for_user` | `self` | `` | Should return true if enabled for user. |
| `test_get_otpsecret_for_user` | `self` | `` | OTP secret should be set for user. |
| `test_confirm_otp_token` | `self` | `` | Ensure otp is confirmed |
| `test_get_verification_obj` | `self` | `` | Confirm verification object is returned. |
| `test_render_string_template` | `self` | `` | String template renders as expected with variables. |
| `test_bypass_restict_ip` | `self` | `` | 1. Raise error if user not login from one of the restrict_ip, Bypass restrict ip check disabled by default
2. Bypass restrict ip check enabled in System Settings
3. Bypass restrict ip check enabled for User |
| `test_otp_attempt_tracker` | `self` | `` | Check that OTP login attempts are tracked. |





## Functions

### `create_http_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get http request object.
```
### `enable_2fa`
**Arguments:** `bypass_two_factor_auth, bypass_restrict_ip_check`
**Decorators:** ``

**Docstring:**
```
Enable Two factor in system settings.
```
### `disable_2fa`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `toggle_2fa_all_role`
**Arguments:** `state`
**Decorators:** ``

**Docstring:**
```
Enable or disable 2fa for 'all' role on the system.
```
### `get_otp`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```

