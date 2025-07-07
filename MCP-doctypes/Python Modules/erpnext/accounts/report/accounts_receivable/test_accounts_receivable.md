# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/report/accounts_receivable/test_accounts_receivable.py`

## Classes

### `TestAccountsReceivable`
**Inherits:** `AccountsTestMixin, IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `create_sales_invoice` | `self, no_payment_schedule, do_not_submit` | `` |  |
| `create_payment_entry` | `self, docname, do_not_submit` | `` |  |
| `create_credit_note` | `self, docname, do_not_submit` | `` |  |
| `test_pos_receivable` | `self` | `` |  |
| `test_accounts_receivable_with_payment` | `self` | `` |  |
| `test_accounts_receivable_without_payment` | `self` | `` |  |
| `test_accounts_receivable_with_partial_payment` | `self` | `` |  |
| `test_cr_note_flag_to_update_self` | `self` | `` |  |
| `test_payment_againt_po_in_receivable_report` | `self` | `` | Payments made against Purchase Order will show up as outstanding amount |
| `test_exchange_revaluation_for_party` | `self` | `` | Exchange Revaluation for party on Receivable/Payable should be included |
| `test_payment_against_credit_note` | `self` | `` | Payment against credit/debit note should be considered against the parent invoice |
| `test_group_by_party` | `self` | `` |  |
| `test_future_payments` | `self` | `` |  |
| `test_sales_person` | `self` | `` |  |
| `test_cost_center_filter` | `self` | `` |  |
| `test_customer_group_filter` | `self` | `` |  |
| `test_multi_customer_group_filter` | `self` | `` |  |
| `test_party_account_filter` | `self` | `` |  |
| `test_usd_customer_filter` | `self` | `` |  |
| `test_multi_select_party_filter` | `self` | `` |  |
| `test_report_output_if_party_is_missing` | `self` | `` |  |
| `test_future_payments_on_foreign_currency` | `self` | `` |  |
| `test_accounts_receivable_output_for_minor_outstanding` | `self` | `` | AR/AP should report miniscule outstanding of 0.01. Or else there will be slight difference with General Ledger/Trial Balance |
| `test_cost_center_on_report_output` | `self` | `` |  |





## Functions

No top-level functions found in this file.
