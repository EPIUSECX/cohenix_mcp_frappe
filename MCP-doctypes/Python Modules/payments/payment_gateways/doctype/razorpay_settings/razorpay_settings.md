# Python Module Analysis: `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/razorpay_settings/razorpay_settings.py`

## Classes

### `RazorpaySettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `init_client` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_razorpay_credentails` | `self` | `` |  |
| `validate_transaction_currency` | `self, currency` | `` |  |
| `setup_addon` | `self, settings` | `` | Addon template:
{
        "item": {
                "name": row.upgrade_type,
                "amount": row.amount,
                "currency": currency,
                "description": "add-on description"
        },
        "quantity": 1 (The total amount is calculated as item.amount * quantity)
} |
| `setup_subscription` | `self, settings` | `` |  |
| `prepare_subscription_details` | `self, settings` | `` |  |
| `get_payment_url` | `self` | `` |  |
| `create_order` | `self` | `` |  |
| `create_request` | `self, data` | `` |  |
| `authorize_payment` | `self` | `` | An authorization is performed when user's payment details are successfully authenticated by the bank.
The money is deducted from the customer's account, but will not be transferred to the merchant's account
until it is explicitly captured by merchant. |
| `get_settings` | `self, data` | `` |  |
| `cancel_subscription` | `self, subscription_id` | `` |  |
| `verify_signature` | `self, body, signature, key` | `` |  |
| `clear` | `self` | `` |  |





## Functions

### `capture_payment`
**Arguments:** `is_sandbox, sanbox_response`
**Decorators:** ``

**Docstring:**
```
Verifies the purchase as complete by the merchant.
After capture, the amount is transferred to the merchant within T+3 days
where T is the day on which payment is captured.

Note: Attempting to capture a payment whose status is not authorized will produce an error.
```
### `get_api_key`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_order`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `order_payment_success`
**Arguments:** `integration_request, params`
**Decorators:** ``

**Docstring:**
```
Called by razorpay.js on order payment success, the params
contains razorpay_payment_id, razorpay_order_id, razorpay_signature
that is updated in the data field of integration request

Args:
        integration_request (string): Name for integration request doc
        params (string): Params to be updated for integration request.
```
### `order_payment_failure`
**Arguments:** `integration_request, params`
**Decorators:** ``

**Docstring:**
```
Called by razorpay.js on failure

Args:
        integration_request (TYPE): Description
        params (TYPE): error data to be updated
```
### `convert_rupee_to_paisa`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `razorpay_subscription_callback`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `validate_payment_callback`
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

