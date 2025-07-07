# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/subscription/subscription.py`

## Classes

### `InvoiceCancelled`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvoiceNotCancelled`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Subscription`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_insert` | `self` | `` |  |
| `update_subscription_period` | `self, date` | `` | Subscription period is the period to be billed. This method updates the
beginning of the billing period and end of the billing period.
The beginning of the billing period is represented in the doctype as
`current_invoice_start` and the end of the billing period is represented
as `current_invoice_end`. |
| `_get_subscription_period` | `self, date` | `` |  |
| `get_current_invoice_start` | `self, date` | `` | This returns the date of the beginning of the current billing period.
If the `date` parameter is not given , it will be automatically set as today's
date. |
| `get_current_invoice_end` | `self, date` | `` | This returns the date of the end of the current billing period.
If the subscription is in trial period, it will be set as the end of the
trial period.
If is not in a trial period, it will be `x` days from the beginning of the
current billing period where `x` is the billing interval from the
`Subscription Plan` in the `Subscription`. |
| `validate_plans_billing_cycle` | `billing_cycle_data` | `staticmethod` | Makes sure that all `Subscription Plan` in the `Subscription` have the
same billing interval |
| `get_billing_cycle_and_interval` | `self` | `` | Returns a dict representing the billing interval and cycle for this `Subscription`.
You shouldn't need to call this directly. Use `get_billing_cycle` instead. |
| `get_billing_cycle_data` | `self` | `` | Returns dict contain the billing cycle data.
You shouldn't need to call this directly. Use `get_billing_cycle` instead. |
| `set_subscription_status` | `self, posting_date` | `` | Sets the status of the `Subscription` |
| `is_trialling` | `self` | `` | Returns `True` if the `Subscription` is in trial period. |
| `period_has_passed` | `end_date, posting_date` | `staticmethod` | Returns true if the given `end_date` has passed |
| `get_status_for_past_grace_period` | `self` | `` |  |
| `is_past_grace_period` | `self, posting_date` | `` | Returns `True` if the grace period for the `Subscription` has passed |
| `current_invoice_is_past_due` | `self, posting_date` | `` | Returns `True` if the current generated invoice is overdue |
| `invoice_document_type` | `self` | `property` |  |
| `validate` | `self` | `` |  |
| `validate_party_billing_currency` | `self` | `` | Subscription should be of the same currency as the Party's default billing currency or company default. |
| `validate_trial_period` | `self` | `` | Runs sanity checks on trial period dates for the `Subscription` |
| `validate_end_date` | `self` | `` |  |
| `validate_to_follow_calendar_months` | `self` | `` |  |
| `generate_invoice` | `self, from_date, to_date, posting_date` | `` | Creates a `Invoice` for the `Subscription`, updates `self.invoices` and
saves the `Subscription`.
Backwards compatibility |
| `create_invoice` | `self, from_date, to_date, posting_date` | `` | Creates a `Invoice`, submits it and returns it |
| `get_items_from_plans` | `self, plans, prorate` | `` | Returns the `Item`s linked to `Subscription Plan` |
| `process` | `self, posting_date` | `` | To be called by task periodically. It checks the subscription and takes appropriate action
as need be. It calls either of these methods depending the `Subscription` status:
1. `process_for_active`
2. `process_for_past_due` |
| `can_generate_new_invoice` | `self, posting_date` | `` |  |
| `is_current_invoice_generated` | `self, _current_start_date, _current_end_date` | `` |  |
| `current_invoice` | `self` | `property` | Adds property for accessing the current_invoice |
| `get_current_invoice` | `self` | `` | Returns the most recent generated invoice. |
| `cancel_subscription_at_period_end` | `self` | `` | Called when `Subscription.cancel_at_period_end` is truthy |
| `invoices` | `self` | `property` |  |
| `is_paid` | `invoice` | `staticmethod` | Return `True` if the given invoice is paid |
| `has_outstanding_invoice` | `self` | `` | Returns `True` if the most recent invoice for the `Subscription` is not paid |
| `cancel_subscription` | `self` | `` | This sets the subscription as cancelled. It will stop invoices from being generated
but it will not affect already created invoices. |
| `restart_subscription` | `self, posting_date` | `` | This sets the subscription as active. The subscription will be made to be like a new
subscription and the `Subscription` will lose all the history of generated invoices
it has. |
| `force_fetch_subscription_updates` | `self` | `` | Process Subscription and create Invoices even if current date doesn't lie between current_invoice_start and currenct_invoice_end
It makes use of 'Proces Subscription' to force processing in a specific 'posting_date' |





## Functions

### `is_prorate`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_prorata_factor`
**Arguments:** `period_end, period_start, is_prepaid`
**Decorators:** ``

**Docstring:**
```

```
### `process_all`
**Arguments:** `subscription, posting_date`
**Decorators:** ``

**Docstring:**
```
Task to updates the status of all `Subscription` apart from those that are cancelled
```

