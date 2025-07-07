# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/sales_invoice/test_sales_invoice.py`

## Classes

### `TestSalesInvoice`
**Inherits:** `ERPNextTestSuite`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_invalid_rate_without_override` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `make` | `self` | `` |  |
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `self` | `classmethod` |  |
| `test_sales_invoice_qty` | `self` | `` |  |
| `test_timestamp_change` | `self` | `` |  |
| `test_sales_invoice_change_naming_series` | `self` | `` |  |
| `test_add_terms_after_save` | `self` | `` |  |
| `test_sales_invoice_calculation_base_currency` | `self` | `` |  |
| `test_payment_entry_unlink_against_invoice` | `self` | `` |  |
| `test_payment_entry_unlink_against_standalone_credit_note` | `self` | `` |  |
| `test_sales_invoice_calculation_export_currency` | `self` | `` |  |
| `test_sales_invoice_with_discount_and_inclusive_tax` | `self` | `` |  |
| `test_sales_invoice_discount_amount` | `self` | `` |  |
| `test_discount_amount_gl_entry` | `self` | `` |  |
| `test_tax_calculation_with_multiple_items` | `self` | `` |  |
| `test_tax_calculation_with_item_tax_template` | `self` | `` |  |
| `test_tax_calculation_with_multiple_items_and_discount` | `self` | `` |  |
| `test_inclusive_rate_validations` | `self` | `` |  |
| `test_sales_invoice_calculation_base_currency_with_tax_inclusive_price` | `self` | `` |  |
| `test_sales_invoice_calculation_export_currency_with_tax_inclusive_price` | `self` | `` |  |
| `test_outstanding` | `self` | `` |  |
| `test_rounded_total_with_cash_discount` | `self` | `` |  |
| `test_payment` | `self` | `` |  |
| `test_outstanding_on_cost_center_allocation` | `self` | `` |  |
| `test_sales_invoice_gl_entry_without_perpetual_inventory` | `self` | `` |  |
| `test_pos_gl_entry_with_perpetual_inventory` | `self` | `` |  |
| `test_pos_returns_with_repayment` | `self` | `` |  |
| `test_pos_change_amount` | `self` | `` |  |
| `test_auto_write_off_amount` | `self` | `` |  |
| `test_ledger_entries_of_return_pos_invoice` | `self` | `` |  |
| `test_pos_with_no_gl_entry_for_change_amount` | `self` | `` |  |
| `validate_pos_gl_entry` | `self, si, pos, cash_amount, validate_without_change_gle` | `` |  |
| `test_bin_details_of_packed_item` | `self` | `` |  |
| `test_pos_si_without_payment` | `self` | `` |  |
| `test_sales_invoice_gl_entry_with_perpetual_inventory_no_item_code` | `self` | `` |  |
| `test_sales_invoice_gl_entry_with_perpetual_inventory_non_stock_item` | `self` | `` |  |
| `_insert_purchase_receipt` | `self` | `` |  |
| `_insert_delivery_note` | `self` | `` |  |
| `test_sales_invoice_with_advance` | `self` | `` |  |
| `test_serialized` | `self` | `` |  |
| `test_serialized_cancel` | `self` | `` |  |
| `test_serial_numbers_against_delivery_note` | `self` | `` | check if the sales invoice item serial numbers and the delivery note items
serial numbers are same |
| `test_return_sales_invoice` | `self` | `` |  |
| `test_zero_qty_return_invoice_with_stock_effect` | `self` | `` |  |
| `test_return_invoice_with_account_mismatch` | `self` | `` |  |
| `test_gle_made_when_asset_is_returned` | `self` | `` |  |
| `test_incoming_rate_for_stand_alone_credit_note` | `self` | `` |  |
| `test_discount_on_net_total` | `self` | `` |  |
| `test_multi_currency_gle` | `self` | `` |  |
| `test_gle_in_transaction_currency` | `self` | `` |  |
| `test_invalid_currency` | `self` | `` |  |
| `test_create_so_with_margin` | `self` | `` |  |
| `test_outstanding_amount_after_advance_jv_cancellation` | `self` | `` |  |
| `test_outstanding_amount_after_advance_payment_entry_cancellation` | `self` | `` | Test impact of advance PE submission/cancellation on SI and SO. |
| `test_multiple_uom_in_selling` | `self` | `` |  |
| `test_item_wise_tax_breakup` | `self` | `` |  |
| `create_si_to_test_tax_breakup` | `self` | `` |  |
| `test_company_monthly_sales` | `self` | `` |  |
| `test_rounding_adjustment` | `self` | `` |  |
| `test_rounding_adjustment_2` | `self` | `` |  |
| `test_rounding_adjustment_3` | `self` | `` |  |
| `test_sales_invoice_with_shipping_rule` | `self` | `` |  |
| `test_create_invoice_without_terms` | `self` | `` |  |
| `test_duplicate_due_date_in_terms` | `self` | `` |  |
| `test_credit_note` | `self` | `` |  |
| `test_sales_invoice_with_cost_center` | `self` | `` |  |
| `test_sales_invoice_with_project_link` | `self` | `` |  |
| `test_sales_invoice_without_cost_center` | `self` | `` |  |
| `test_deferred_revenue` | `self` | `` |  |
| `test_deferred_revenue_missing_account` | `self` | `` |  |
| `test_fixed_deferred_revenue` | `self` | `` |  |
| `test_validate_inter_company_transaction_address_links` | `self` | `` |  |
| `test_inter_company_transaction` | `self` | `` |  |
| `test_inter_company_transaction_without_default_warehouse` | `self` | `` | Check mapping (expense account) of inter company SI to PI in absence of default warehouse. |
| `test_sle_for_target_warehouse` | `self` | `` |  |
| `test_internal_transfer_gl_entry` | `self` | `` |  |
| `test_internal_transfer_gl_precision_issues` | `self` | `` |  |
| `test_item_tax_net_range` | `self` | `` |  |
| `test_sales_invoice_with_discount_accounting_enabled` | `self` | `` |  |
| `test_additional_discount_for_sales_invoice_with_discount_accounting_enabled` | `self` | `` |  |
| `test_asset_depreciation_on_sale_with_pro_rata` | `self` | `` | Tests if an Asset set to depreciate yearly on June 30, that gets sold on Sept 30, creates an additional depreciation entry on its date of sale. |
| `test_asset_depreciation_on_sale_without_pro_rata` | `self` | `` | Tests if an Asset set to depreciate yearly on Dec 31, that gets sold on Dec 31 after two years, created an additional depreciation entry on its date of sale. |
| `test_sales_invoice_against_supplier` | `self` | `` |  |
| `test_sales_invoice_against_supplier_usd_with_dimensions` | `self` | `` |  |
| `test_sales_invoice_cancel_with_common_party_advance_jv` | `self` | `` |  |
| `test_payment_statuses` | `self` | `` |  |
| `test_update_invoice_status` | `self` | `` |  |
| `test_sales_commission` | `self` | `` |  |
| `test_sales_invoice_submission_post_account_freezing_date` | `self` | `` |  |
| `test_over_billing_case_against_delivery_note` | `self` | `` | Test a case where duplicating the item with qty = 1 in the invoice
allows overbilling even if it is disabled |
| `test_multi_currency_deferred_revenue_via_journal_entry` | `self` | `` |  |
| `test_standalone_serial_no_return` | `self` | `` |  |
| `test_sales_invoice_with_disabled_account` | `self` | `` |  |
| `test_gain_loss_with_advance_entry` | `self` | `` |  |
| `test_batch_expiry_for_sales_invoice_return` | `self` | `` |  |
| `test_sales_invoice_with_payable_tax_account` | `self` | `` |  |
| `test_advance_entries_as_liability` | `self` | `` |  |
| `test_sales_invoice_without_customer_group_and_territory` | `self` | `` |  |
| `test_sales_return_negative_rate` | `self` | `` |  |
| `test_partial_allocation_on_advance_as_liability` | `self` | `` |  |
| `test_loyalty_points_redemption_with_shopping_cart` | `self` | `` |  |
| `test_pulling_advance_based_on_debit_to` | `self` | `` |  |
| `test_taxes_merging_from_delivery_note` | `self` | `` |  |
| `test_pos_returns_without_update_outstanding_for_self` | `self` | `` |  |
| `test_validation_on_opening_invoice_with_rounding` | `self` | `` |  |
| `_create_opening_roundoff_account` | `self, company_name` | `` |  |
| `test_opening_invoice_with_rounding_adjustment` | `self` | `` |  |
| `_create_opening_invoice_with_inclusive_tax` | `self` | `` |  |
| `test_rounding_validation_for_opening_with_inclusive_tax` | `self` | `` |  |
| `test_ledger_entries_on_opening_invoice_with_rounding_loss_by_inclusive_tax` | `self` | `` |  |
| `test_common_party_with_foreign_currency_jv` | `self` | `` |  |
| `test_common_party_with_different_currency_in_debtor_and_creditor` | `self` | `` |  |
| `test_invoice_remarks` | `self` | `` |  |
| `test_gl_voucher_subtype` | `self` | `` |  |
| `test_total_billed_amount` | `self` | `` |  |
| `test_total_billed_amount_with_different_projects` | `self` | `` |  |
| `test_pos_returns_with_party_account_currency` | `self` | `` |  |
| `test_create_return_invoice_for_self_update` | `self` | `` |  |
| `test_prevents_fully_returned_invoice_with_zero_quantity` | `self` | `` |  |
| `test_pos_sales_invoice_creation_during_pos_invoice_mode` | `self` | `` |  |
| `test_stand_alone_credit_note_valuation` | `self` | `` |  |
| `test_stand_alone_credit_note_zero_valuation` | `self` | `` |  |





## Functions

### `make_item_for_si`
**Arguments:** `item_code, properties`
**Decorators:** ``

**Docstring:**
```

```
### `set_advance_flag`
**Arguments:** `company, flag, default_account`
**Decorators:** ``

**Docstring:**
```

```
### `check_gl_entries`
**Arguments:** `doc, voucher_no, expected_gle, posting_date, voucher_type`
**Decorators:** ``

**Docstring:**
```

```
### `create_sales_invoice`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_sales_invoice_against_cost_center`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_outstanding_amount`
**Arguments:** `against_voucher_type, against_voucher, account, party, party_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_taxes_and_charges`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_internal_parties`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_internal_supplier`
**Arguments:** `supplier_name, represents_company, allowed_to_interact_with`
**Decorators:** ``

**Docstring:**
```

```
### `setup_accounts`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `add_taxes`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```

