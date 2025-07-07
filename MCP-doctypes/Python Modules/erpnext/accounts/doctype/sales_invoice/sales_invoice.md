# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/sales_invoice/sales_invoice.py`

## Classes

### `PartialPaymentValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SalesInvoice`
**Inherits:** `SellingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `set_indicator` | `self` | `` | Set indicator for portal |
| `validate` | `self` | `` |  |
| `validate_accounts` | `self` | `` |  |
| `validate_for_repost` | `self` | `` |  |
| `validate_fixed_asset` | `self` | `` |  |
| `validate_item_cost_centers` | `self` | `` |  |
| `validate_income_account` | `self` | `` |  |
| `set_tax_withholding` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `validate_pos_return` | `self` | `` |  |
| `validate_pos_paid_amount` | `self` | `` |  |
| `check_if_consolidated_invoice` | `self` | `` |  |
| `check_if_created_using_pos_and_pos_closing_entry_generated` | `self` | `` |  |
| `before_cancel` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `update_status_updater_args` | `self` | `` |  |
| `check_credit_limit` | `self` | `` |  |
| `unlink_sales_invoice_from_timesheets` | `self` | `` |  |
| `cancel_pos_invoice_credit_note_generated_during_sales_invoice_mode` | `self` | `` |  |
| `set_missing_values` | `self, for_validate` | `` |  |
| `reset_mode_of_payments` | `self` | `` |  |
| `update_time_sheet` | `self, sales_invoice` | `` |  |
| `update_time_sheet_detail` | `self, timesheet, args, sales_invoice` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `set_paid_amount` | `self` | `` |  |
| `set_account_for_mode_of_payment` | `self` | `` |  |
| `validate_time_sheets_are_submitted` | `self` | `` |  |
| `set_pos_fields` | `self, for_validate` | `` | Set retail related fields from POS Profiles |
| `get_company_abbr` | `self` | `` |  |
| `validate_debit_to_acc` | `self` | `` |  |
| `clear_unallocated_mode_of_payments` | `self` | `` |  |
| `validate_with_previous_doc` | `self` | `` |  |
| `set_against_income_account` | `self` | `` | Set against account for debit to account |
| `force_set_against_income_account` | `self` | `` |  |
| `add_remarks` | `self` | `` |  |
| `validate_auto_set_posting_time` | `self` | `` |  |
| `so_dn_required` | `self` | `` | check in manage account if sales order / delivery note required or not. |
| `validate_proj_cust` | `self` | `` | check for does customer belong to same project as entered.. |
| `validate_pos` | `self` | `` |  |
| `validate_created_using_pos` | `self` | `` |  |
| `validate_full_payment` | `self` | `` |  |
| `validate_pos_opening_entry` | `self` | `` |  |
| `validate_warehouse` | `self` | `` |  |
| `validate_delivery_note` | `self` | `` | If items are linked with a delivery note, stock cannot be updated again. |
| `allow_write_off_only_on_pos` | `self` | `` |  |
| `validate_write_off_account` | `self` | `` |  |
| `validate_account_for_change_amount` | `self` | `` |  |
| `validate_dropship_item` | `self` | `` | If items are drop shipped, stock cannot be updated. |
| `update_current_stock` | `self` | `` |  |
| `update_packing_list` | `self` | `` |  |
| `set_billing_hours_and_amount` | `self` | `` |  |
| `update_timesheet_billing_for_project` | `self` | `` |  |
| `is_auto_fetch_timesheet_enabled` | `self` | `` |  |
| `add_timesheet_data` | `self` | `` |  |
| `calculate_billing_amount_for_timesheet` | `self` | `` |  |
| `get_warehouse` | `self` | `` |  |
| `set_income_account_for_fixed_assets` | `self` | `` |  |
| `check_prev_docstatus` | `self` | `` |  |
| `process_asset_depreciation` | `self` | `` |  |
| `depreciate_asset_on_sale` | `self` | `` | Depreciate asset on sale or cancellation of return sales invoice |
| `get_note_for_asset_sale` | `self, asset` | `` |  |
| `restore_asset` | `self` | `` | Restore asset on return or cancellation of original sales invoice |
| `get_note_for_asset_return` | `self, asset` | `` |  |
| `update_asset` | `self` | `` | Update asset status, disposal date and asset activity on sale or return sales invoice |
| `get_disposal_date` | `self` | `` |  |
| `make_gl_entries` | `self, gl_entries, from_repost` | `` |  |
| `get_gl_entries` | `self, warehouse_account` | `` |  |
| `make_customer_gl_entry` | `self, gl_entries` | `` |  |
| `make_tax_gl_entries` | `self, gl_entries` | `` |  |
| `make_internal_transfer_gl_entries` | `self, gl_entries` | `` |  |
| `make_item_gl_entries` | `self, gl_entries` | `` |  |
| `get_gl_entries_for_fixed_asset` | `self, item, gl_entries` | `` |  |
| `enable_discount_accounting` | `self` | `property` |  |
| `make_loyalty_point_redemption_gle` | `self, gl_entries` | `` |  |
| `make_pos_gl_entries` | `self, gl_entries` | `` |  |
| `get_gle_for_change_amount` | `self` | `` |  |
| `make_write_off_gl_entry` | `self, gl_entries` | `` |  |
| `make_gle_for_rounding_adjustment` | `self, gl_entries` | `` |  |
| `update_billing_status_in_dn` | `self, update_modified` | `` |  |
| `on_recurring` | `self, reference_doc, auto_repeat_doc` | `` |  |
| `update_project` | `self` | `` |  |
| `verify_payment_amount_is_positive` | `self` | `` |  |
| `verify_payment_amount_is_negative` | `self` | `` |  |
| `make_loyalty_point_entry` | `self` | `` |  |
| `delete_loyalty_point_entry` | `self` | `` |  |
| `set_loyalty_program_tier` | `self` | `` |  |
| `get_returned_amount` | `self` | `` |  |
| `apply_loyalty_points` | `self` | `` |  |
| `set_status` | `self, update, status, update_modified` | `` |  |





## Functions

### `get_total_in_party_account_currency`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `is_overdue`
**Arguments:** `doc, total`
**Decorators:** ``

**Docstring:**
```

```
### `get_discounting_status`
**Arguments:** `sales_invoice`
**Decorators:** ``

**Docstring:**
```

```
### `validate_inter_company_party`
**Arguments:** `doctype, party, company, inter_company_reference`
**Decorators:** ``

**Docstring:**
```

```
### `update_linked_doc`
**Arguments:** `doctype, name, inter_company_reference`
**Decorators:** ``

**Docstring:**
```

```
### `unlink_inter_company_doc`
**Arguments:** `doctype, name, inter_company_reference`
**Decorators:** ``

**Docstring:**
```

```
### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `get_bank_cash_account`
**Arguments:** `mode_of_payment, company`
**Decorators:** ``

**Docstring:**
```

```
### `make_maintenance_schedule`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_delivery_note`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_sales_return`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_inter_company_details`
**Arguments:** `doc, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_internal_party`
**Arguments:** `parties, link_doctype, doc`
**Decorators:** ``

**Docstring:**
```

```
### `validate_inter_company_transaction`
**Arguments:** `doc, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `make_inter_company_purchase_invoice`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_regional_gl_entries`
**Arguments:** `gl_entries, doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_inter_company_transaction`
**Arguments:** `doctype, source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_received_items`
**Arguments:** `reference_name, doctype, reference_fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `set_purchase_references`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_pi_items`
**Arguments:** `doc, detail_field, parent_field, sales_item_map, purchase_item_map, parent_child_map, warehouse_map`
**Decorators:** ``

**Docstring:**
```

```
### `update_pr_items`
**Arguments:** `doc, sales_item_map, purchase_item_map, parent_child_map, warehouse_map`
**Decorators:** ``

**Docstring:**
```

```
### `get_delivery_note_details`
**Arguments:** `internal_reference`
**Decorators:** ``

**Docstring:**
```

```
### `get_sales_invoice_details`
**Arguments:** `internal_reference`
**Decorators:** ``

**Docstring:**
```

```
### `get_pd_details`
**Arguments:** `doctype, sd_detail_map, sd_detail_field`
**Decorators:** ``

**Docstring:**
```

```
### `update_taxes`
**Arguments:** `doc, party, party_type, company, doctype, party_address, company_address, shipping_address_name, master_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `update_address`
**Arguments:** `doc, address_field, address_display_field, address_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_loyalty_programs`
**Arguments:** `customer`
**Decorators:** ``

**Docstring:**
```
sets applicable loyalty program to the customer or returns a list of applicable programs
```
### `create_invoice_discounting`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_multi_mode_option`
**Arguments:** `doc, pos_profile`
**Decorators:** ``

**Docstring:**
```

```
### `get_all_mode_of_payments`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_mode_of_payments_info`
**Arguments:** `mode_of_payments, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_mode_of_payment_info`
**Arguments:** `mode_of_payment, company`
**Decorators:** ``

**Docstring:**
```

```
### `create_dunning`
**Arguments:** `source_name, target_doc, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `check_if_return_invoice_linked_with_payment_entry`
**Arguments:** `self`
**Decorators:** ``

**Docstring:**
```

```

