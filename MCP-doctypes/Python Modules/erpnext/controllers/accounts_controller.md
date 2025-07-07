# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/accounts_controller.py`

## Classes

### `AccountMissingError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidQtyError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `AccountsController`
**Inherits:** `TransactionBase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_print_settings` | `self` | `` |  |
| `company_currency` | `self` | `property` |  |
| `onload` | `self` | `` |  |
| `remove_bundle_for_non_stock_invoices` | `self` | `` |  |
| `ensure_supplier_is_not_blocked` | `self` | `` |  |
| `validate_against_voucher_outstanding` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `set_default_letter_head` | `self` | `` |  |
| `init_internal_values` | `self` | `` |  |
| `before_cancel` | `self` | `` |  |
| `_remove_references_in_unreconcile` | `self` | `` |  |
| `_remove_references_in_repost_doctypes` | `self` | `` |  |
| `_remove_advance_payment_ledger_entries` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `remove_serial_and_batch_bundle` | `self` | `` |  |
| `validate_company_in_accounting_dimension` | `self` | `` |  |
| `validate_company` | `self, dimension_list, child` | `` |  |
| `validate_party_address_and_contact` | `self` | `` |  |
| `validate_party_address` | `self, party, party_type, billing_address, shipping_address` | `` |  |
| `validate_party_contact` | `self, party, party_type` | `` |  |
| `validate_return_against_account` | `self` | `` |  |
| `validate_deferred_income_expense_account` | `self` | `` |  |
| `validate_auto_repeat_subscription_dates` | `self` | `` |  |
| `validate_deferred_start_and_end_date` | `self` | `` |  |
| `validate_invoice_documents_schedule` | `self` | `` |  |
| `validate_non_invoice_documents_schedule` | `self` | `` |  |
| `validate_all_documents_schedule` | `self` | `` |  |
| `before_print` | `self, settings` | `` |  |
| `calculate_paid_amount` | `self` | `` |  |
| `set_missing_values` | `self, for_validate` | `` |  |
| `calculate_taxes_and_totals` | `self` | `` |  |
| `validate_date_with_fiscal_year` | `self` | `` |  |
| `validate_party_accounts` | `self` | `` |  |
| `validate_inter_company_reference` | `self` | `` |  |
| `validate_internal_transaction` | `self` | `` |  |
| `validate_internal_transaction_based_on_voucher_type` | `self` | `` |  |
| `validate_line_items` | `self, ref_dt, ref_dn_field, ref_link_field` | `` |  |
| `disable_pricing_rule_on_internal_transfer` | `self` | `` |  |
| `disable_tax_included_prices_for_internal_transfer` | `self` | `` |  |
| `validate_due_date` | `self` | `` |  |
| `set_price_list_currency` | `self, buying_or_selling` | `` |  |
| `set_missing_item_details` | `self, for_validate` | `` | set missing item values |
| `apply_pricing_rule_on_items` | `self, item, pricing_rule_args` | `` |  |
| `set_pricing_rule_details` | `self, item_row, args` | `` |  |
| `set_taxes` | `self` | `` |  |
| `is_pos_profile_changed` | `self` | `` |  |
| `set_taxes_and_charges` | `self` | `` |  |
| `append_taxes_from_master` | `self, tax_master_doctype` | `` |  |
| `append_taxes_from_item_tax_template` | `self` | `` |  |
| `get_tax_row` | `self, account_head` | `` |  |
| `set_other_charges` | `self` | `` |  |
| `validate_enabled_taxes_and_charges` | `self` | `` |  |
| `validate_tax_account_company` | `self` | `` |  |
| `get_gl_dict` | `self, args, account_currency, item` | `` | this method populates the common properties of a gl entry record |
| `get_voucher_subtype` | `self` | `` |  |
| `get_value_in_transaction_currency` | `self, account_currency, gl_dict, field` | `` |  |
| `validate_zero_qty_for_return_invoices_with_stock` | `self` | `` |  |
| `validate_qty_is_not_zero` | `self` | `` |  |
| `validate_account_currency` | `self, account, account_currency` | `` |  |
| `clear_unallocated_advances` | `self, childtype, parentfield` | `` |  |
| `apply_shipping_rule` | `self` | `` |  |
| `get_shipping_address` | `self` | `` | Returns Address object from shipping address fields if present |
| `set_advances` | `self` | `` | Returns list of advances against Account, Party, Reference |
| `get_advance_entries` | `self, include_unallocated` | `` |  |
| `is_inclusive_tax` | `self` | `` |  |
| `should_show_taxes_as_table_in_print` | `self` | `` |  |
| `validate_advance_entries` | `self` | `` |  |
| `set_advance_gain_or_loss` | `self` | `` |  |
| `make_precision_loss_gl_entry` | `self, gl_entries` | `` |  |
| `gain_loss_journal_already_booked` | `self, gain_loss_account, exc_gain_loss, ref2_dt, ref2_dn, ref2_detail_no` | `` | Check if gain/loss is booked |
| `make_exchange_gain_loss_journal` | `self, args, dimensions_dict` | `` | Make Exchange Gain/Loss journal for Invoices and Payments |
| `is_payable_account` | `self, reference_doctype, account` | `` |  |
| `update_against_document_in_jv` | `self` | `` | Links invoice and advance voucher:
        1. cancel advance voucher
        2. split into multiple rows if partially adjusted, assign against voucher
        3. submit advance voucher |
| `cancel_system_generated_credit_debit_notes` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `unlink_ref_doc_from_po` | `self` | `` |  |
| `get_tax_map` | `self` | `` |  |
| `get_amount_and_base_amount` | `self, item, enable_discount_accounting` | `` |  |
| `get_tax_amounts` | `self, tax, enable_discount_accounting` | `` |  |
| `make_discount_gl_entries` | `self, gl_entries` | `` |  |
| `validate_multiple_billing` | `self, ref_dt, item_ref_dn, based_on` | `` |  |
| `get_billing_reference_details` | `self, reference_names, reference_doctype, based_on` | `` |  |
| `get_reference_wise_billed_amt` | `self, ref_dt, item_ref_dn, based_on` | `` | Returns Sum of Amount of
Sales/Purchase Invoice Items
that are linked to `item_ref_dn` (`dn_detail` / `pr_detail`)
that are submitted OR not submitted but are under current invoice |
| `get_already_billed_amount` | `self, reference_names, item_ref_dn, based_on` | `` |  |
| `throw_overbill_exception` | `self, overbilled_items, precision` | `` |  |
| `get_company_default` | `self, fieldname, ignore_validation` | `` |  |
| `get_stock_items` | `self` | `` |  |
| `calculate_total_advance_from_ledger` | `self` | `` |  |
| `set_total_advance_paid` | `self` | `` |  |
| `set_advance_payment_status` | `self` | `` |  |
| `company_abbr` | `self` | `property` |  |
| `raise_missing_debit_credit_account_error` | `self, party_type, party` | `` | Raise an error if debit to/credit to account does not exist. |
| `validate_party` | `self` | `` |  |
| `get_party` | `self` | `` |  |
| `validate_currency` | `self` | `` |  |
| `validate_party_account_currency` | `self` | `` |  |
| `delink_advance_entries` | `self, linked_doc_name` | `` |  |
| `group_similar_items` | `self` | `` |  |
| `set_payment_schedule` | `self` | `` |  |
| `get_order_details` | `self` | `` |  |
| `linked_order_has_payment_terms` | `self, po_or_so, fieldname, doctype` | `` |  |
| `all_items_have_same_po_or_so` | `self, po_or_so, fieldname` | `` |  |
| `linked_order_has_payment_terms_template` | `self, po_or_so, doctype` | `` |  |
| `linked_order_has_payment_schedule` | `self, po_or_so` | `` |  |
| `fetch_payment_terms_from_order` | `self, po_or_so, po_or_so_doctype, grand_total, base_grand_total, automatically_fetch_payment_terms` | `` | Fetch Payment Terms from Purchase/Sales Order on creating a new Purchase/Sales Invoice. |
| `set_due_date` | `self` | `` |  |
| `validate_payment_schedule_dates` | `self` | `` |  |
| `validate_payment_schedule_amount` | `self` | `` |  |
| `is_rounded_total_disabled` | `self` | `` |  |
| `set_inter_company_account` | `self` | `` | Set intercompany account for inter warehouse transactions
This account will be used in case billing company and internal customer's
representation company is same |
| `is_internal_transfer` | `self` | `` | It will an internal transfer if its an internal customer and representation
company is same as billing company |
| `process_common_party_accounting` | `self` | `` |  |
| `get_common_party_link` | `self` | `` |  |
| `create_advance_and_reconcile` | `self, party_link` | `` |  |
| `check_conversion_rate` | `self` | `` |  |
| `check_finance_books` | `self, item, asset` | `` |  |
| `check_if_fields_updated` | `self, fields_to_check, child_tables` | `` |  |
| `repost_accounting_entries` | `self` | `` |  |
| `get_advance_payment_doctypes` | `self` | `` |  |
| `make_advance_payment_ledger_for_journal` | `self` | `` |  |
| `make_advance_payment_ledger_for_payment` | `self` | `` |  |
| `make_advance_payment_ledger_entries` | `self` | `` |  |
| `set_transaction_currency_and_rate_in_gl_map` | `self, gl_entries` | `` |  |





## Functions

### `get_tax_rate`
**Arguments:** `account_head`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_taxes_and_charges`
**Arguments:** `master_doctype, tax_template, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_taxes_and_charges`
**Arguments:** `master_doctype, master_name`
**Decorators:** ``

**Docstring:**
```

```
### `validate_conversion_rate`
**Arguments:** `currency, conversion_rate, conversion_rate_label, company`
**Decorators:** ``

**Docstring:**
```
common validation for currency and price list currency
```
### `validate_taxes_and_charges`
**Arguments:** `tax`
**Decorators:** ``

**Docstring:**
```

```
### `validate_account_head`
**Arguments:** `idx, account, company, context`
**Decorators:** ``

**Docstring:**
```
Throw a ValidationError if the account belongs to a different company or is a group account.
```
### `validate_cost_center`
**Arguments:** `tax, doc`
**Decorators:** ``

**Docstring:**
```

```
### `validate_inclusive_tax`
**Arguments:** `tax, doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_balance_in_account_currency`
**Arguments:** `gl_dict, account_currency, conversion_rate, company_currency`
**Decorators:** ``

**Docstring:**
```

```
### `get_advance_journal_entries`
**Arguments:** `party_type, party, party_account, amount_field, order_doctype, order_list, include_unallocated`
**Decorators:** ``

**Docstring:**
```

```
### `get_advance_payment_entries_for_regional`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_advance_payment_entries`
**Arguments:** `party_type, party, party_account, order_doctype, order_list, default_advance_account, include_unallocated, against_all_orders, limit, condition`
**Decorators:** ``

**Docstring:**
```

```
### `get_common_query`
**Arguments:** `party_type, party, party_account, default_advance_account, limit, condition`
**Decorators:** ``

**Docstring:**
```

```
### `update_invoice_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Updates status as Overdue for applicable invoices. Runs daily.
```
### `get_payment_terms`
**Arguments:** `terms_template, posting_date, grand_total, base_grand_total, bill_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_term_details`
**Arguments:** `term, posting_date, grand_total, base_grand_total, bill_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_due_date`
**Arguments:** `term, posting_date, bill_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_discount_date`
**Arguments:** `term, posting_date, bill_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_supplier_block_status`
**Arguments:** `party_name`
**Decorators:** ``

**Docstring:**
```
Returns a dict containing the values of `on_hold`, `release_date` and `hold_type` of
a `Supplier`
```
### `set_child_tax_template_and_map`
**Arguments:** `item, child_item, parent_doc`
**Decorators:** ``

**Docstring:**
```

```
### `add_taxes_from_tax_template`
**Arguments:** `child_item, parent_doc, db_insert`
**Decorators:** ``

**Docstring:**
```

```
### `set_order_defaults`
**Arguments:** `parent_doctype, parent_doctype_name, child_doctype, child_docname, trans_item`
**Decorators:** ``

**Docstring:**
```
Returns a Sales/Purchase Order Item child item containing the default values
```
### `validate_child_on_delete`
**Arguments:** `row, parent`
**Decorators:** ``

**Docstring:**
```
Check if partially transacted item (row) is being deleted.
```
### `update_bin_on_delete`
**Arguments:** `row, doctype`
**Decorators:** ``

**Docstring:**
```
Update bin for deleted item (row).
```
### `validate_and_delete_children`
**Arguments:** `parent, data`
**Decorators:** ``

**Docstring:**
```

```
### `update_child_qty_rate`
**Arguments:** `parent_doctype, trans_items, parent_doctype_name, child_docname`
**Decorators:** ``

**Docstring:**
```

```
### `check_if_child_table_updated`
**Arguments:** `child_table_before_update, child_table_after_update, fields_to_check`
**Decorators:** ``

**Docstring:**
```

```
### `merge_taxes`
**Arguments:** `source_taxes, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `validate_regional`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `validate_einvoice_fields`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_gl_dict_with_regional_fields`
**Arguments:** `doc, gl_dict`
**Decorators:** ``

**Docstring:**
```

```
### `update_gl_dict_with_app_based_fields`
**Arguments:** `doc, gl_dict`
**Decorators:** ``

**Docstring:**
```

```

