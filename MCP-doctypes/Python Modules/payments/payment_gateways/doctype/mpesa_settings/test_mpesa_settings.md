# Python Module Analysis: `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/mpesa_settings/test_mpesa_settings.py`

## Classes

### `TestMpesaSettings`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_creation_of_payment_gateway` | `self` | `` |  |
| `test_processing_of_account_balance` | `self` | `` |  |
| `test_processing_of_callback_payload` | `self` | `` |  |
| `test_processing_of_multiple_callback_payload` | `self` | `` |  |
| `test_processing_of_only_one_succes_callback_payload` | `self` | `` |  |





## Functions

### `create_mpesa_settings`
**Arguments:** `payment_gateway_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_test_account_balance_response`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Response received after calling the account balance API.
```
### `get_payment_request_response_payload`
**Arguments:** `Amount`
**Decorators:** ``

**Docstring:**
```
Response received after successfully calling the stk push process request API.
```
### `get_payment_callback_payload`
**Arguments:** `Amount, CheckoutRequestID, MpesaReceiptNumber`
**Decorators:** ``

**Docstring:**
```
Response received from the server as callback after calling the stkpush process request API.
```
### `get_account_balance_callback_payload`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Response received from the server as callback after calling the account balance API.
```

