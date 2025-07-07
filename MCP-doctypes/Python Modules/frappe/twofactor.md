# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/twofactor.py`

## Classes

### `ExpiredLoginException`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `get_default`
**Arguments:** `key`
**Decorators:** ``

**Docstring:**
```

```
### `set_default`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```

```
### `clear_default`
**Arguments:** `key`
**Decorators:** ``

**Docstring:**
```

```
### `toggle_two_factor_auth`
**Arguments:** `state, roles`
**Decorators:** ``

**Docstring:**
```
Enable or disable 2FA in site_config and roles
```
### `two_factor_is_enabled`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Return True if 2FA is enabled.
```
### `should_run_2fa`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Check if 2fa should run.
```
### `get_cached_user_pass`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get user and password if set.
```
### `authenticate_for_2factor`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Authenticate two factor for enabled user before login.
```
### `cache_2fa_data`
**Arguments:** `user, token, otp_secret, tmp_id`
**Decorators:** ``

**Docstring:**
```
Cache and set expiry for data.
```
### `two_factor_is_enabled_for_`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Check if 2factor is enabled for user.
```
### `get_otpsecret_for_`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Set OTP Secret for user even if not set.
```
### `get_verification_method`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `confirm_otp_token`
**Arguments:** `login_manager, otp, tmp_id`
**Decorators:** ``

**Docstring:**
```
Confirm otp matches.
```
### `get_verification_obj`
**Arguments:** `user, token, otp_secret`
**Decorators:** ``

**Docstring:**
```

```
### `process_2fa_for_sms`
**Arguments:** `user, token, otp_secret`
**Decorators:** ``

**Docstring:**
```
Process sms method for 2fa.
```
### `process_2fa_for_otp_app`
**Arguments:** `user, otp_secret, otp_issuer`
**Decorators:** ``

**Docstring:**
```
Process OTP App method for 2fa.
```
### `process_2fa_for_email`
**Arguments:** `user, token, otp_secret, otp_issuer, method`
**Decorators:** ``

**Docstring:**
```
Process Email method for 2fa.
```
### `get_email_subject_for_2fa`
**Arguments:** `kwargs_dict`
**Decorators:** ``

**Docstring:**
```
Get email subject for 2fa.
```
### `get_email_body_for_2fa`
**Arguments:** `kwargs_dict`
**Decorators:** ``

**Docstring:**
```
Get email body for 2fa.
```
### `get_email_subject_for_qr_code`
**Arguments:** `kwargs_dict`
**Decorators:** ``

**Docstring:**
```
Get QRCode email subject.
```
### `get_email_body_for_qr_code`
**Arguments:** `kwargs_dict`
**Decorators:** ``

**Docstring:**
```
Get QRCode email body.
```
### `get_link_for_qrcode`
**Arguments:** `user, totp_uri`
**Decorators:** ``

**Docstring:**
```
Get link to temporary page showing QRCode.
```
### `send_token_via_sms`
**Arguments:** `otpsecret, token, phone_no`
**Decorators:** ``

**Docstring:**
```
Send token as sms to user.
```
### `send_token_via_email`
**Arguments:** `user, token, otp_secret, otp_issuer, subject, message`
**Decorators:** ``

**Docstring:**
```
Send token to user as email.
```
### `get_qr_svg_code`
**Arguments:** `totp_uri`
**Decorators:** ``

**Docstring:**
```
Get SVG code to display Qrcode for OTP.
```
### `create_barcode_folder`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get Barcodes folder.
```
### `delete_qrimage`
**Arguments:** `user, check_expiry`
**Decorators:** ``

**Docstring:**
```
Delete Qrimage when user logs in.
```
### `delete_all_barcodes_for_users`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Task to delete all barcodes for user.
```
### `should_remove_barcode_image`
**Arguments:** `barcode`
**Decorators:** ``

**Docstring:**
```
Check if it's time to delete barcode image from server.
```
### `disable`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `reset_otp_secret`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```

