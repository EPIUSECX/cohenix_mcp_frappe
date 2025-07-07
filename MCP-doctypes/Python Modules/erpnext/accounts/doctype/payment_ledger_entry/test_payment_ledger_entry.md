# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_ledger_entry/test_payment_ledger_entry.py`

## Classes

### `TestPaymentLedgerEntry`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `create_company` | `self` | `` |  |
| `create_item` | `self` | `` |  |
| `create_customer` | `self` | `` |  |
| `create_sales_invoice` | `self, qty, rate, posting_date, do_not_save, do_not_submit` | `` | Helper function to populate default values in sales invoice |
| `create_payment_entry` | `self, amount, posting_date` | `` | Helper function to populate default values in payment entry |
| `create_sales_order` | `self, qty, rate, posting_date, do_not_save, do_not_submit` | `` |  |
| `clear_old_entries` | `self` | `` |  |
| `create_journal_entry` | `self, acc1, acc2, amount, posting_date, cost_center` | `` |  |
| `test_payment_against_invoice` | `self` | `` |  |
| `test_partial_payment_against_invoice` | `self` | `` |  |
| `test_cr_note_against_invoice` | `self` | `` |  |
| `test_je_against_inv_and_note` | `self` | `` |  |
| `test_multi_payment_unlink_on_invoice_cancellation` | `self` | `` |  |
| `test_multi_je_unlink_on_invoice_cancellation` | `self` | `` |  |
| `test_advance_payment_unlink_on_order_cancellation` | `self` | `` |  |





## Functions

No top-level functions found in this file.
