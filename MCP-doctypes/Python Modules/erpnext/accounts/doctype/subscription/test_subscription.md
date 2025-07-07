# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/subscription/test_subscription.py`

## Classes

### `TestSubscription`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_create_subscription_with_trial_with_correct_period` | `self` | `` |  |
| `test_create_subscription_without_trial_with_correct_period` | `self` | `` |  |
| `test_create_subscription_trial_with_wrong_dates` | `self` | `` |  |
| `test_invoice_is_generated_at_end_of_billing_period` | `self` | `` |  |
| `test_status_goes_back_to_active_after_invoice_is_paid` | `self` | `` |  |
| `test_subscription_cancel_after_grace_period` | `self` | `` |  |
| `test_subscription_unpaid_after_grace_period` | `self` | `` |  |
| `test_subscription_invoice_days_until_due` | `self` | `` |  |
| `test_subscription_is_past_due_doesnt_change_within_grace_period` | `self` | `` |  |
| `test_subscription_remains_active_during_invoice_period` | `self` | `` |  |
| `test_subscription_cancellation` | `self` | `` |  |
| `test_subscription_cancellation_invoices` | `self` | `` |  |
| `test_subscription_cancellation_invoices_with_prorata_false` | `self` | `` |  |
| `test_subscription_cancellation_invoices_with_prorata_true` | `self` | `` |  |
| `test_subscription_cancellation_and_process` | `self` | `` |  |
| `test_subscription_restart_and_process` | `self` | `` |  |
| `test_subscription_unpaid_back_to_active` | `self` | `` |  |
| `test_restart_active_subscription` | `self` | `` |  |
| `test_subscription_invoice_discount_percentage` | `self` | `` |  |
| `test_subscription_invoice_discount_amount` | `self` | `` |  |
| `test_prepaid_subscriptions` | `self` | `` |  |
| `test_prepaid_subscriptions_with_prorate_true` | `self` | `` |  |
| `test_subscription_with_follow_calendar_months` | `self` | `` |  |
| `test_subscription_generate_invoice_past_due` | `self` | `` |  |
| `test_subscription_without_generate_invoice_past_due` | `self` | `` |  |
| `test_multi_currency_subscription` | `self` | `` |  |
| `test_multi_currency_subscription_with_default_company_currency` | `self` | `` |  |
| `test_subscription_recovery` | `self` | `` | Test if Subscription recovers when start/end date run out of sync with created invoices. |
| `test_subscription_invoice_generation_before_days` | `self` | `` |  |
| `test_future_subscription` | `self` | `` | Force-Fetch should not process future subscriptions |





## Functions

### `make_plans`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_plan`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_parties`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `reset_settings`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_subscription`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

