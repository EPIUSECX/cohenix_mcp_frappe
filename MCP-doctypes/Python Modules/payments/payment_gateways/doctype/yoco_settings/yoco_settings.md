# Python Module Analysis: `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/yoco_settings/yoco_settings.py`

## Classes

### `YocoSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `on_update` | `self` | `` |  |
| `test_connection` | `self` | `` | Test the connection to the Yoco API. |
| `validate_transaction_currency` | `self, currency` | `` |  |
| `validate_minimum_transaction_amount` | `self, currency, amount` | `` |  |
| `get_payment_url` | `self` | `` |  |
| `create_request` | `self, data` | `` | For Yoco, the payment is processed entirely on the frontend with the Yoco SDK.
The webhook handles the completion and ERPNext integration.
This method just creates the Integration Request for tracking. |
| `finalize_request` | `self` | `` |  |





## Functions

No top-level functions found in this file.
