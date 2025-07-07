# Python Module Analysis: `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/mpesa_settings/mpesa_settings.py`

## Classes

### `MpesaSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate_transaction_currency` | `self, currency` | `` |  |
| `on_update` | `self` | `` |  |
| `request_for_payment` | `self` | `` |  |
| `split_request_amount_according_to_transaction_limit` | `self, args` | `` |  |
| `get_account_balance_info` | `self` | `` |  |
| `handle_api_response` | `self, global_id, request_dict, response` | `` | Response received from API calls returns a global identifier for each transaction, this code is returned during the callback. |





## Functions

### `generate_stk_push`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Generate stk push by making a API call to the stk push API.
```
### `sanitize_mobile_number`
**Arguments:** `number`
**Decorators:** ``

**Docstring:**
```
Add country code and strip leading zeroes from the phone number.
```
### `verify_transaction`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Verify the transaction result received via callback from stk.
```
### `get_completed_integration_requests_info`
**Arguments:** `reference_doctype, reference_docname, checkout_id`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_balance`
**Arguments:** `request_payload`
**Decorators:** ``

**Docstring:**
```
Call account balance API to send the request to the Mpesa Servers.
```
### `process_balance_info`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Process and store account balance information received via callback from the account balance API call.
```
### `format_string_to_json`
**Arguments:** `balance_info`
**Decorators:** ``

**Docstring:**
```
Format string to json.

e.g: '''Working Account|KES|481000.00|481000.00|0.00|0.00'''
=> {'Working Account': {'current_balance': '481000.00',
        'available_balance': '481000.00',
        'reserved_balance': '0.00',
        'uncleared_balance': '0.00'}}
```
### `fetch_param_value`
**Arguments:** `response, key, key_field`
**Decorators:** ``

**Docstring:**
```
Fetch the specified key from list of dictionary. Key is identified via the key field.
```
### `create_mode_of_payment`
**Arguments:** `gateway, payment_type`
**Decorators:** ``

**Docstring:**
```

```

