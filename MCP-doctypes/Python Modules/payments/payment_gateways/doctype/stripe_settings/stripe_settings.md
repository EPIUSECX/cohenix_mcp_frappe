# Python Module Analysis: `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/stripe_settings/stripe_settings.py`

## Classes

### `StripeSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `on_update` | `self` | `` |  |
| `validate_stripe_credentails` | `self` | `` |  |
| `validate_transaction_currency` | `self, currency` | `` |  |
| `validate_minimum_transaction_amount` | `self, currency, amount` | `` |  |
| `get_payment_url` | `self` | `` |  |
| `create_request` | `self, data` | `` |  |
| `create_charge_on_stripe` | `self` | `` |  |
| `finalize_request` | `self` | `` |  |





## Functions

### `get_gateway_controller`
**Arguments:** `doctype, docname, payment_gateway`
**Decorators:** ``

**Docstring:**
```

```

