# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_request/payment_request.py`

## Classes

### `PaymentRequest`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_reference_document` | `self` | `` |  |
| `validate_payment_request_amount` | `self` | `` |  |
| `validate_currency` | `self` | `` |  |
| `validate_subscription_details` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `request_phone_payment` | `self` | `` |  |
| `get_request_amount` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `make_invoice` | `self` | `` |  |
| `payment_gateway_validation` | `self` | `` |  |
| `set_payment_request_url` | `self` | `` |  |
| `get_payment_url` | `self` | `` |  |
| `set_as_paid` | `self` | `` |  |
| `create_payment_entry` | `self, submit` | `` | create entry |
| `send_email` | `self` | `` | send email with payment link |
| `get_message` | `self` | `` | return message with payment gateway link |
| `set_failed` | `self` | `` |  |
| `set_as_cancelled` | `self` | `` |  |
| `check_if_payment_entry_exists` | `self` | `` |  |
| `make_communication_entry` | `self` | `` | Make communication entry |
| `create_subscription` | `self, payment_provider, gateway_controller, data` | `` |  |
| `update_reference_advance_payment_status` | `self` | `` |  |
| `_allocate_payment_request_to_pe_references` | `self, references` | `` | Allocate the Payment Request to the Payment Entry references based on

    - Allocated Amount.
    - Outstanding Amount of Payment Request.

Payment Request is doc itself and references are the rows of Payment Entry. |





## Functions

### `_get_payment_gateway_controller`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_payment_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Make payment request
```
### `get_amount`
**Arguments:** `ref_doc, payment_account`
**Decorators:** ``

**Docstring:**
```
get amount based on doctype
```
### `get_irequest_status`
**Arguments:** `payment_requests`
**Decorators:** ``

**Docstring:**
```

```
### `cancel_old_payment_requests`
**Arguments:** `ref_dt, ref_dn`
**Decorators:** ``

**Docstring:**
```

```
### `get_existing_payment_request_amount`
**Arguments:** `ref_doc, statuses`
**Decorators:** ``

**Docstring:**
```
Return the total amount of Payment Requests against a reference document.
```
### `get_gateway_details`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```
Return gateway and payment account of default payment gateway
```
### `get_payment_gateway_account`
**Arguments:** `filter`
**Decorators:** ``

**Docstring:**
```

```
### `get_print_format_list`
**Arguments:** `ref_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `resend_payment_email`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```

```
### `make_payment_entry`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```

```
### `update_payment_requests_as_per_pe_references`
**Arguments:** `references, cancel`
**Decorators:** ``

**Docstring:**
```
Update Payment Request's `Status` and `Outstanding Amount` based on Payment Entry Reference's `Allocated Amount`.
```
### `get_dummy_message`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_subscription_details`
**Arguments:** `reference_doctype, reference_name`
**Decorators:** ``

**Docstring:**
```

```
### `make_payment_order`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `validate_payment`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```

```
### `get_open_payment_requests_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_irequests_of_payment_request`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```

