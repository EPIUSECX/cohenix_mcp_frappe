# Python Module Analysis: `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/paytm_settings/paytm_settings.py`

## Classes

### `PaytmSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_transaction_currency` | `self, currency` | `` |  |
| `get_payment_url` | `self` | `` | Return payment url with several params |





## Functions

### `get_paytm_config`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Returns paytm config
```
### `get_paytm_params`
**Arguments:** `payment_details, order_id, paytm_config`
**Decorators:** ``

**Docstring:**
```

```
### `verify_transaction`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Verify checksum for received data in the callback and then verify the transaction
```
### `verify_transaction_status`
**Arguments:** `paytm_config, order_id`
**Decorators:** ``

**Docstring:**
```
Verify transaction completion after checksum has been verified
```
### `finalize_request`
**Arguments:** `order_id, transaction_response`
**Decorators:** ``

**Docstring:**
```

```
### `get_gateway_controller`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```

