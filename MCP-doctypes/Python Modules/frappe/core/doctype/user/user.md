# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/user/user.py`

## Classes

### `User`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__setup__` | `self` | `` |  |
| `autoname` | `self` | `` | set name as Email Address |
| `onload` | `self` | `` |  |
| `before_insert` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `disable_email_fields_if_user_disabled` | `self` | `` |  |
| `populate_role_profile_roles` | `self` | `` |  |
| `move_role_profile_name_to_role_profiles` | `self` | `` | This handles old role_profile_name field if programatically set.

This behaviour will be remoed in future versions. |
| `validate_allowed_modules` | `self` | `` |  |
| `validate_user_image` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `has_website_permission` | `self, ptype, user, verbose` | `` | Return True if current user is the session user. |
| `clean_name` | `self` | `` |  |
| `set_full_name` | `self` | `` |  |
| `check_enable_disable` | `self` | `` |  |
| `email_new_password` | `self, new_password` | `` |  |
| `set_system_user` | `self` | `` | For the standard users like admin and guest, the user type is fixed. |
| `set_roles_and_modules_based_on_user_type` | `self` | `` |  |
| `has_desk_access` | `self` | `` | Return true if any of the set roles has desk access |
| `share_with_self` | `self` | `` |  |
| `validate_share` | `self, docshare` | `` |  |
| `send_password_notification` | `self, new_password` | `` |  |
| `validate_reset_password` | `self` | `` |  |
| `reset_password` | `self, send_email, password_expired` | `` |  |
| `get_fullname` | `self` | `` | get first_name space last_name |
| `password_reset_mail` | `self, link` | `` |  |
| `send_welcome_mail_to_user` | `self` | `` |  |
| `send_login_mail` | `self, subject, template, add_args, now, custom_template` | `` | send mail with login details |
| `on_trash` | `self` | `` |  |
| `before_rename` | `self, old_name, new_name, merge` | `` |  |
| `validate_rename` | `self, old_name, new_name` | `` |  |
| `validate_email_type` | `self, email` | `` |  |
| `after_rename` | `self, old_name, new_name, merge` | `` |  |
| `append_roles` | `self` | `` | Add roles to user |
| `add_roles` | `self` | `` | Add roles to user and save |
| `remove_roles` | `self` | `` |  |
| `remove_all_roles_for_guest` | `self` | `` |  |
| `remove_disabled_roles` | `self` | `` |  |
| `ensure_unique_roles` | `self` | `` |  |
| `ensure_unique_role_profiles` | `self` | `` |  |
| `validate_username` | `self` | `` |  |
| `password_strength_test` | `self` | `` | test password strength |
| `suggest_username` | `self` | `` |  |
| `username_exists` | `self, username` | `` |  |
| `get_blocked_modules` | `self` | `` | Return list of modules blocked for that user. |
| `validate_user_email_inbox` | `self` | `` | check if same email account added in User Emails twice |
| `get_social_login_userid` | `self, provider` | `` |  |
| `set_social_login_userid` | `self, provider, userid, username` | `` |  |
| `get_restricted_ip_list` | `self` | `` |  |
| `find_by_credentials` | `cls, user_name, password, validate_password` | `classmethod` | Find the user by credentials.

This is a login utility that needs to check login related system settings while finding the user.
1. Find user by email ID by default
2. If allow_login_using_mobile_number is set, you can use mobile number while finding the user.
3. If allow_login_using_user_name is set, you can use username while finding the user. |
| `set_time_zone` | `self` | `` |  |
| `get_permission_log_options` | `self, event` | `` |  |
| `check_roles_added` | `self` | `` |  |
| `validate_ip_addr` | `self` | `` |  |





## Functions

### `get_timezones`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_all_roles`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
return all roles
```
### `get_roles`
**Arguments:** `arg`
**Decorators:** ``

**Docstring:**
```
get roles for a user
```
### `get_perm_info`
**Arguments:** `role`
**Decorators:** ``

**Docstring:**
```
get permission info
```
### `update_password`
**Arguments:** `new_password, logout_all_sessions, key, old_password`
**Decorators:** ``

**Docstring:**
```
Update password for the current user.

Args:
    new_password (str): New password.
    logout_all_sessions (int, optional): If set to 1, all other sessions will be logged out. Defaults to 0.
    key (str, optional): Password reset key. Defaults to None.
    old_password (str, optional): Old password. Defaults to None.
```
### `test_password_strength`
**Arguments:** `new_password, key, old_password, user_data`
**Decorators:** ``

**Docstring:**
```

```
### `has_email_account`
**Arguments:** `email`
**Decorators:** ``

**Docstring:**
```

```
### `get_email_awaiting`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `ask_pass_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_get_user_for_update_password`
**Arguments:** `key, old_password`
**Decorators:** ``

**Docstring:**
```

```
### `reset_user_data`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `verify_password`
**Arguments:** `password`
**Decorators:** ``

**Docstring:**
```

```
### `sign_up`
**Arguments:** `email, full_name, redirect_to`
**Decorators:** ``

**Docstring:**
```

```
### `reset_password`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `user_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_total_users`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return total number of system users.
```
### `get_system_users`
**Arguments:** `exclude_users, limit`
**Decorators:** ``

**Docstring:**
```

```
### `get_active_users`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return number of system users who logged in, in the last 3 days.
```
### `get_website_users`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return total number of website users.
```
### `get_active_website_users`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return number of website users who logged in, in the last 3 days.
```
### `get_permission_query_conditions`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `has_permission`
**Arguments:** `doc, user`
**Decorators:** ``

**Docstring:**
```

```
### `notify_admin_access_to_system_manager`
**Arguments:** `login_manager`
**Decorators:** ``

**Docstring:**
```

```
### `handle_password_test_fail`
**Arguments:** `feedback`
**Decorators:** ``

**Docstring:**
```

```
### `update_gravatar`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `throttle_user_creation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_module_profile`
**Arguments:** `module_profile`
**Decorators:** ``

**Docstring:**
```

```
### `create_contact`
**Arguments:** `user, ignore_links, ignore_mandatory`
**Decorators:** ``

**Docstring:**
```

```
### `get_restricted_ip_list`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `generate_keys`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
generate api key and api secret

:param user: str
```
### `switch_theme`
**Arguments:** `theme`
**Decorators:** ``

**Docstring:**
```

```
### `get_enabled_users`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `impersonate`
**Arguments:** `user, reason`
**Decorators:** ``

**Docstring:**
```

```

