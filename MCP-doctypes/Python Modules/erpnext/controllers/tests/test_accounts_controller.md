# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/tests/test_accounts_controller.py`

## Classes

### `TestAccountsController`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```
Test Exchange Gain/Loss booking on various scenarios.
Test Cases are numbered for better organization

10 series - Sales Invoice against Payment Entries
20 series - Sales Invoice against Journals
30 series - Sales Invoice against Credit Notes
40 series - Company default Cost center is unset
50 series - Journals against Journals
60 series - Journals against Payment Entries
70 series - Advances in Separate party account. Both Party and Advance account are in Foreign currency.
90 series - Dimension inheritence
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `create_company` | `self` | `` |  |
| `create_item` | `self` | `` |  |
| `create_parties` | `self` | `` |  |
| `create_customer` | `self` | `` |  |
| `create_supplier` | `self` | `` |  |
| `create_account` | `self` | `` |  |
| `setup_advance_accounts_in_party_master` | `self` | `` |  |
| `remove_advance_accounts_from_party_master` | `self` | `` |  |
| `create_sales_invoice` | `self, qty, rate, conversion_rate, posting_date, do_not_save, do_not_submit` | `` | Helper function to populate default values in sales invoice |
| `create_payment_entry` | `self, amount, source_exc_rate, posting_date, customer, submit` | `` | Helper function to populate default values in payment entry |
| `create_purchase_invoice` | `self, qty, rate, conversion_rate, posting_date, do_not_save, do_not_submit` | `` | Helper function to populate default values in purchase invoice |
| `clear_old_entries` | `self` | `` |  |
| `create_payment_reconciliation` | `self` | `` |  |
| `create_journal_entry` | `self, acc1, acc1_exc_rate, acc2_exc_rate, acc2, acc1_amount, acc2_amount, posting_date, cost_center` | `` |  |
| `get_journals_for` | `self, voucher_type, voucher_no` | `` |  |
| `assert_ledger_outstanding` | `self, voucher_type, voucher_no, outstanding, outstanding_in_account_currency` | `` | Assert outstanding amount based on ledger on both company/base currency and account currency |
| `test_10_payment_against_sales_invoice` | `self` | `` |  |
| `test_11_advance_against_sales_invoice` | `self` | `` |  |
| `test_12_partial_advance_and_payment_for_sales_invoice` | `self` | `` | Sales invoice with partial advance payment, and a normal payment reconciled |
| `test_13_partial_advance_and_payment_for_invoice_with_cancellation` | `self` | `` | Invoice with partial advance payment, and a normal payment. Then cancel advance and payment. |
| `test_14_same_payment_split_against_invoice` | `self` | `` |  |
| `test_15_gain_loss_on_different_posting_date` | `self` | `` |  |
| `test_16_internal_transfer_at_arms_length_price` | `self` | `` |  |
| `test_17_gain_loss_posting_date_for_normal_payment` | `self` | `` |  |
| `test_18_fetch_taxes_based_on_taxes_and_charges_template` | `self` | `` |  |
| `test_19_fetch_taxes_based_on_item_tax_template_template` | `self` | `` |  |
| `test_20_journal_against_sales_invoice` | `self` | `` |  |
| `test_21_advance_journal_against_sales_invoice` | `self` | `` |  |
| `test_22_partial_advance_and_payment_for_invoice_with_cancellation` | `self` | `` | Invoice with partial advance payment as Journal, and a normal payment. Then cancel advance and payment. |
| `test_23_same_journal_split_against_single_invoice` | `self` | `` |  |
| `test_24_journal_against_multiple_invoices` | `self` | `` |  |
| `test_30_cr_note_against_sales_invoice` | `self` | `` | Reconciling Cr Note against Sales Invoice, both having different exchange rates |
| `test_40_cost_center_from_payment_entry` | `self` | `` | Gain/Loss JE should inherit cost center from payment if company default is unset |
| `test_41_cost_center_from_journal_entry` | `self` | `` | Gain/Loss JE should inherit cost center from payment if company default is unset |
| `test_42_cost_center_from_cr_note` | `self` | `` | Gain/Loss JE should inherit cost center from payment if company default is unset |
| `setup_dimensions` | `self` | `` |  |
| `test_90_dimensions_filter` | `self` | `` | Test workings of dimension filters |
| `test_91_cr_note_should_inherit_dimension` | `self` | `` |  |
| `test_92_dimension_inhertiance_exc_gain_loss` | `self` | `` |  |
| `test_93_dimension_inheritance_on_advance` | `self` | `` |  |
| `test_50_journal_against_journal` | `self` | `` |  |
| `test_60_payment_entry_against_journal` | `self` | `` |  |
| `test_61_payment_entry_against_journal_for_payable_accounts` | `self` | `` |  |
| `test_70_advance_payment_against_sales_invoice_in_foreign_currency` | `self` | `` | Customer advance booked under Liability |
| `test_71_advance_payment_against_purchase_invoice_in_foreign_currency` | `self` | `` | Supplier advance booked under Asset |
| `test_difference_posting_date_in_pi_and_si` | `self` | `` |  |
| `test_company_validation_in_dimension` | `self` | `` |  |
| `test_party_billing_and_shipping_address` | `self` | `` |  |
| `test_party_contact` | `self` | `` |  |





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

