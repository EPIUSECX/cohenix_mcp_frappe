# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/purchase_invoice/test_purchase_invoice.py`

## Classes

### `TestPurchaseInvoice`
**Inherits:** `IntegrationTestCase, StockTestMixin`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `tearDown` | `self` | `` |  |
| `test_purchase_invoice_qty` | `self` | `` |  |
| `test_purchase_invoice_received_qty` | `self` | `` | 1. Test if received qty is validated against accepted + rejected
2. Test if received qty is auto set on save |
| `test_update_received_qty_in_material_request` | `self` | `` |  |
| `test_gl_entries_without_perpetual_inventory` | `self` | `` |  |
| `test_gl_entries_with_perpetual_inventory` | `self` | `` |  |
| `test_terms_added_after_save` | `self` | `` |  |
| `test_payment_entry_unlink_against_purchase_invoice` | `self` | `` |  |
| `test_purchase_invoice_for_blocked_supplier` | `self` | `` |  |
| `test_purchase_invoice_for_blocked_supplier_invoice` | `self` | `` |  |
| `test_purchase_invoice_for_blocked_supplier_payment` | `self` | `` |  |
| `test_purchase_invoice_for_blocked_supplier_payment_today_date` | `self` | `` |  |
| `test_purchase_invoice_for_blocked_supplier_payment_past_date` | `self` | `` |  |
| `test_purchase_invoice_blocked_invoice_must_be_in_future` | `self` | `` |  |
| `test_purchase_invoice_temporary_blocked` | `self` | `` |  |
| `test_purchase_invoice_explicit_block` | `self` | `` |  |
| `test_gl_entries_with_perpetual_inventory_against_pr` | `self` | `` |  |
| `check_gle_for_pi` | `self, pi` | `` |  |
| `test_purchase_invoice_with_exchange_rate_difference` | `self` | `` |  |
| `test_purchase_invoice_with_exchange_rate_difference_for_non_stock_item` | `self` | `` |  |
| `test_purchase_invoice_change_naming_series` | `self` | `` |  |
| `test_gl_entries_for_non_stock_items_with_perpetual_inventory` | `self` | `` |  |
| `test_purchase_invoice_calculation` | `self` | `` |  |
| `test_purchase_invoice_with_advance` | `self` | `` |  |
| `test_invoice_with_advance_and_multi_payment_terms` | `self` | `` |  |
| `test_total_purchase_cost_for_project` | `self` | `` |  |
| `test_return_purchase_invoice_with_perpetual_inventory` | `self` | `` |  |
| `test_standalone_return_using_pi` | `self` | `` |  |
| `test_return_with_lcv` | `self` | `` |  |
| `test_multi_currency_gle` | `self` | `` |  |
| `test_purchase_invoice_update_stock_gl_entry_with_perpetual_inventory` | `self` | `` |  |
| `test_purchase_invoice_for_is_paid_and_update_stock_gl_entry_with_perpetual_inventory` | `self` | `` |  |
| `test_auto_batch` | `self` | `` |  |
| `test_update_stock_and_purchase_return` | `self` | `` |  |
| `test_rejected_serial_no` | `self` | `` |  |
| `test_outstanding_amount_after_advance_jv_cancelation` | `self` | `` |  |
| `test_outstanding_amount_after_advance_payment_entry_cancelation` | `self` | `` |  |
| `test_purchase_invoice_with_shipping_rule` | `self` | `` |  |
| `test_make_pi_without_terms` | `self` | `` |  |
| `test_duplicate_due_date_in_terms` | `self` | `` |  |
| `test_debit_note` | `self` | `` |  |
| `test_purchase_invoice_with_cost_center` | `self` | `` |  |
| `test_purchase_invoice_without_cost_center` | `self` | `` |  |
| `test_purchase_invoice_with_project_link` | `self` | `` |  |
| `test_deferred_expense_via_journal_entry` | `self` | `` |  |
| `test_gain_loss_with_advance_entry` | `self` | `` |  |
| `test_purchase_invoice_advance_taxes` | `self` | `` |  |
| `test_purchase_gl_with_tax_withholding_tax` | `self` | `` |  |
| `test_provisional_accounting_entry` | `self` | `` |  |
| `test_provisional_accounting_entry_for_over_billing` | `self` | `` |  |
| `test_provisional_accounting_entry_for_partial_billing` | `self` | `` |  |
| `test_provisional_accounting_entry_multi_currency` | `self` | `` |  |
| `test_adjust_incoming_rate` | `self` | `` |  |
| `test_adjust_incoming_rate_for_rejected_item` | `self` | `` |  |
| `test_item_less_defaults` | `self` | `` |  |
| `test_batch_expiry_for_purchase_invoice` | `self` | `` |  |
| `test_advance_entries_as_asset` | `self` | `` |  |
| `test_gl_entries_for_standalone_debit_note` | `self` | `` |  |
| `test_payment_allocation_for_payment_terms` | `self` | `` |  |
| `test_offsetting_entries_for_accounting_dimensions` | `self` | `` |  |
| `test_repost_accounting_entries` | `self` | `` |  |
| `test_create_purchase_invoice_without_mandatory` | `self` | `` |  |
| `test_purchase_invoice_without_supplier_group` | `self` | `` |  |
| `test_default_cost_center_for_purchase` | `self` | `` |  |
| `test_debit_note_with_account_mismatch` | `self` | `` |  |
| `test_debit_note_without_item` | `self` | `` |  |
| `test_purchase_invoice_with_use_serial_batch_field_for_rejected_qty` | `self` | `` |  |
| `test_make_pr_and_pi_from_po` | `self` | `` |  |
| `test_adjust_incoming_rate_from_pi_with_multi_currency` | `self` | `` |  |
| `test_adjust_incoming_rate_from_pi_with_multi_currency_and_partial_billing` | `self` | `` |  |
| `test_opening_invoice_rounding_adjustment_validation` | `self` | `` |  |
| `_create_opening_roundoff_account` | `self, company_name` | `` |  |
| `test_ledger_entries_of_opening_invoice_with_rounding_adjustment` | `self` | `` |  |
| `test_last_purchase_rate` | `self` | `` |  |
| `test_invoice_against_returned_pr` | `self` | `` |  |
| `test_trx_currency_debit_credit_for_high_precision` | `self` | `` |  |
| `test_prevents_fully_returned_invoice_with_zero_quantity` | `self` | `` |  |
| `test_apply_discount_on_grand_total` | `self` | `` | To test if after applying discount on grand total,
the grand total is calculated correctly without any rounding errors |
| `test_apply_discount_on_grand_total_with_previous_row_total_tax` | `self` | `` | To test if after applying discount on grand total,
where the tax is calculated on previous row total, the grand total is calculated correctly |
| `test_pr_pi_over_billing` | `self` | `` |  |
| `test_discount_percentage_not_set_when_amount_is_manually_set` | `self` | `` |  |





## Functions

### `set_advance_flag`
**Arguments:** `company, flag, default_account`
**Decorators:** ``

**Docstring:**
```

```
### `check_gl_entries`
**Arguments:** `doc, voucher_no, expected_gle, posting_date, voucher_type, additional_columns`
**Decorators:** ``

**Docstring:**
```

```
### `create_tax_witholding_category`
**Arguments:** `category_name, company, account`
**Decorators:** ``

**Docstring:**
```

```
### `unlink_payment_on_cancel_of_invoice`
**Arguments:** `enable`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_invoice`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_invoice_against_cost_center`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `setup_provisional_accounting`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `toggle_provisional_accounting_setting`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

