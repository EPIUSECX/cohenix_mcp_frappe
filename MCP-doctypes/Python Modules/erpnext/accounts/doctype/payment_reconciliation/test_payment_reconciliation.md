# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_reconciliation/test_payment_reconciliation.py`

## Classes

### `TestPaymentReconciliation`
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
| `create_account` | `self` | `` |  |
| `create_sales_invoice` | `self, qty, rate, posting_date, do_not_save, do_not_submit` | `` | Helper function to populate default values in sales invoice |
| `create_payment_entry` | `self, amount, posting_date, customer` | `` | Helper function to populate default values in payment entry |
| `create_purchase_invoice` | `self, qty, rate, posting_date, do_not_save, do_not_submit` | `` | Helper function to populate default values in sales invoice |
| `create_purchase_order` | `self, qty, rate, posting_date, do_not_save, do_not_submit` | `` | Helper function to populate default values in sales invoice |
| `clear_old_entries` | `self` | `` |  |
| `create_payment_reconciliation` | `self, party_is_customer` | `` |  |
| `create_journal_entry` | `self, acc1, acc2, amount, posting_date, cost_center` | `` |  |
| `create_cost_center` | `self` | `` |  |
| `test_filter_min_max` | `self` | `` |  |
| `test_filter_posting_date` | `self` | `` |  |
| `test_filter_posting_date_case2` | `self` | `` | Posting date should not affect outstanding amount calculation |
| `test_filter_invoice_limit` | `self` | `` |  |
| `test_payment_against_invoice` | `self` | `` |  |
| `test_payment_against_journal` | `self` | `` |  |
| `test_payment_against_foreign_currency_journal` | `self` | `` |  |
| `test_journal_against_invoice` | `self` | `` |  |
| `test_negative_debit_or_credit_journal_against_invoice` | `self` | `` |  |
| `test_journal_against_journal` | `self` | `` |  |
| `test_cr_note_against_invoice` | `self` | `` |  |
| `test_invoice_status_after_cr_note_cancellation` | `self` | `` |  |
| `test_cr_note_partial_against_invoice` | `self` | `` |  |
| `test_pr_output_foreign_currency_and_amount` | `self` | `` |  |
| `test_difference_amount_via_journal_entry` | `self` | `` |  |
| `test_difference_amount_via_negative_debit_or_credit_journal_entry` | `self` | `` |  |
| `test_difference_amount_via_payment_entry` | `self` | `` |  |
| `test_differing_cost_center_on_invoice_and_payment` | `self` | `` | Cost Center filter should not affect outstanding amount calculation |
| `test_cost_center_filter_on_vouchers` | `self` | `` | Test Cost Center filter is applied on Invoices, Payment Entries and Journals |
| `test_no_difference_amount_for_base_currency_accounts` | `self` | `` |  |
| `test_reconciliation_purchase_invoice_against_return` | `self` | `` |  |
| `test_reconciliation_from_purchase_order_to_multiple_invoices` | `self` | `` | Reconciling advance payment from PO/SO to multiple invoices should not cause overallocation |
| `test_rounding_of_unallocated_amount` | `self` | `` |  |
| `test_reverse_payment_against_payment_for_supplier` | `self` | `` | Reconcile a payment against a reverse payment, for a supplier. |
| `test_advance_reverse_payment_against_payment_for_supplier` | `self` | `` | Reconcile an Advance payment against reverse payment, for a supplier. |
| `test_advance_payment_reconciliation_date` | `self` | `` |  |
| `test_advance_payment_reconciliation_against_journal_for_customer` | `self` | `` |  |
| `test_advance_payment_reconciliation_against_journal_for_supplier` | `self` | `` |  |
| `test_cr_note_payment_limit_filter` | `self` | `` |  |
| `test_reconciliation_on_closed_period_payment` | `self` | `` |  |
| `test_advance_reconciliation_effect_on_same_date` | `self` | `` |  |





## Functions

### `make_customer`
**Arguments:** `customer_name, currency`
**Decorators:** ``

**Docstring:**
```

```
### `make_supplier`
**Arguments:** `supplier_name, currency`
**Decorators:** ``

**Docstring:**
```

```
### `create_fiscal_year`
**Arguments:** `company, year_start_date, year_end_date`
**Decorators:** ``

**Docstring:**
```

```
### `make_period_closing_voucher`
**Arguments:** `company, cost_center, posting_date, submit`
**Decorators:** ``

**Docstring:**
```

```

