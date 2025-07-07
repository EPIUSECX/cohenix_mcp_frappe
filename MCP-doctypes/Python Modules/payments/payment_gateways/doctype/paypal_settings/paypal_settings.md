# Python Module Analysis: `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/paypal_settings/paypal_settings.py`

## Classes

### `PayPalSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__setup__` | `self` | `` |  |
| `setup_sandbox_env` | `self, token` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `validate_transaction_currency` | `self, currency` | `` |  |
| `get_paypal_params_and_url` | `self` | `` |  |
| `validate_paypal_credentails` | `self` | `` |  |
| `get_payment_url` | `self` | `` |  |
| `execute_set_express_checkout` | `self` | `` |  |
| `configure_recurring_payments` | `self, params, kwargs` | `` |  |





## Functions

### `get_paypal_and_transaction_details`
**Arguments:** `token`
**Decorators:** ``

**Docstring:**
```

```
### `setup_redirect`
**Arguments:** `data, redirect_url, custom_redirect_to, redirect`
**Decorators:** ``

**Docstring:**
```

```
### `get_express_checkout_details`
**Arguments:** `token`
**Decorators:** ``

**Docstring:**
```

```
### `confirm_payment`
**Arguments:** `token`
**Decorators:** ``

**Docstring:**
```

```
### `create_recurring_profile`
**Arguments:** `token, payerid`
**Decorators:** ``

**Docstring:**
```

```
### `update_integration_request_status`
**Arguments:** `token, data, status, error, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_redirect_uri`
**Arguments:** `doc, token, payerid`
**Decorators:** ``

**Docstring:**
```

```
### `manage_recurring_payment_profile_status`
**Arguments:** `profile_id, action, args, url`
**Decorators:** ``

**Docstring:**
```

```
### `ipn_handler`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `validate_ipn_request`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `handle_subscription_notification`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```

