# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/purchase_invoice/purchase_invoice.py`

## Classes

### `WarehouseMissingError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `PurchaseInvoice`
**Inherits:** `BuyingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `invoice_is_blocked` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `set_percentage_received` | `self` | `` |  |
| `validate_release_date` | `self` | `` |  |
| `validate_cash` | `self` | `` |  |
| `create_remarks` | `self` | `` |  |
| `set_missing_values` | `self, for_validate` | `` |  |
| `validate_credit_to_acc` | `self` | `` |  |
| `check_on_hold_or_closed_status` | `self` | `` |  |
| `validate_with_previous_doc` | `self` | `` |  |
| `validate_warehouse` | `self, for_validate` | `` |  |
| `validate_item_code` | `self` | `` |  |
| `set_expense_account` | `self, for_validate` | `` |  |
| `validate_expense_account` | `self` | `` |  |
| `set_against_expense_account` | `self, force` | `` |  |
| `force_set_against_expense_account` | `self` | `` |  |
| `po_required` | `self` | `` |  |
| `pr_required` | `self` | `` |  |
| `validate_write_off_account` | `self` | `` |  |
| `check_prev_docstatus` | `self` | `` |  |
| `update_status_updater_args` | `self` | `` |  |
| `validate_purchase_receipt_if_update_stock` | `self` | `` |  |
| `validate_for_repost` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `make_gl_entries` | `self, gl_entries, from_repost` | `` |  |
| `cancel_provisional_entries` | `self` | `` |  |
| `update_supplier_outstanding` | `self, update_outstanding` | `` |  |
| `get_gl_entries` | `self, warehouse_account` | `` |  |
| `check_asset_cwip_enabled` | `self` | `` |  |
| `make_supplier_gl_entry` | `self, gl_entries` | `` |  |
| `add_supplier_gl_entry` | `self, gl_entries, base_grand_total, grand_total, against_account, remarks, skip_merge` | `` |  |
| `make_item_gl_entries` | `self, gl_entries` | `` |  |
| `get_provisional_accounts` | `self` | `` |  |
| `make_provisional_gl_entry` | `self, gl_entries, item` | `` |  |
| `update_gross_purchase_amount_for_linked_assets` | `self, item` | `` |  |
| `make_stock_adjustment_entry` | `self, gl_entries, item, voucher_wise_stock_value, account_currency` | `` |  |
| `make_tax_gl_entries` | `self, gl_entries` | `` |  |
| `make_internal_transfer_gl_entries` | `self, gl_entries` | `` |  |
| `make_gl_entries_for_tax_withholding` | `self, gl_entries` | `` | Tax withholding amount is not part of supplier invoice.
Separate supplier GL Entry for correct reporting. |
| `make_payment_gl_entries` | `self, gl_entries` | `` |  |
| `make_write_off_gl_entry` | `self, gl_entries` | `` |  |
| `make_gle_for_rounding_adjustment` | `self, gl_entries` | `` |  |
| `on_cancel` | `self` | `` |  |
| `update_project` | `self` | `` |  |
| `validate_supplier_invoice` | `self` | `` |  |
| `update_billing_status_in_pr` | `self, update_modified` | `` |  |
| `get_pr_details_billed_amt` | `self` | `` |  |
| `on_recurring` | `self, reference_doc, auto_repeat_doc` | `` |  |
| `block_invoice` | `self, hold_comment, release_date` | `` |  |
| `unblock_invoice` | `self` | `` |  |
| `set_tax_withholding` | `self` | `` |  |
| `allocate_advance_tds` | `self, tax_withholding_details, advance_taxes` | `` |  |
| `update_advance_tax_references` | `self, cancel` | `` |  |
| `set_status` | `self, update, status, update_modified` | `` |  |





## Functions

### `get_purchase_document_details`
**Arguments:** `doc`
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
### `make_regional_gl_entries`
**Arguments:** `gl_entries, doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_debit_note`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_stock_entry`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `change_release_date`
**Arguments:** `name, release_date`
**Decorators:** ``

**Docstring:**
```

```
### `unblock_invoice`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `block_invoice`
**Arguments:** `name, release_date, hold_comment`
**Decorators:** ``

**Docstring:**
```

```
### `make_inter_company_sales_invoice`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_receipt`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```

