# Python Module Analysis: `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/yoco_webhook.py`

## Classes

No classes found in this file.


## Functions

### `handle_webhook`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Handle webhook notifications from Yoco.
This is the single entry point for all Yoco webhooks.
```
### `handle_charge_succeeded`
**Arguments:** `data, log_path`
**Decorators:** ``

**Docstring:**
```
Handle successful charge webhook from Yoco.
```
### `handle_charge_failed`
**Arguments:** `data, log_path`
**Decorators:** ``

**Docstring:**
```
Handle failed charge webhook from Yoco.
```
### `verify_signature`
**Arguments:** `request_body, signature, secret`
**Decorators:** ``

**Docstring:**
```
Verify the signature of the incoming webhook.
```

