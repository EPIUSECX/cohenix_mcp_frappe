# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/purchase_receipt/test_purchase_receipt.py`

## Classes

### `TestPurchaseReceipt`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_purchase_receipt_qty` | `self` | `` |  |
| `test_purchase_receipt_received_qty` | `self` | `` | 1. Test if received qty is validated against accepted + rejected
2. Test if received qty is auto set on save |
| `test_reverse_purchase_receipt_sle` | `self` | `` |  |
| `test_make_purchase_invoice` | `self` | `` |  |
| `test_purchase_receipt_no_gl_entry` | `self` | `` |  |
| `test_batched_serial_no_purchase` | `self` | `` |  |
| `test_duplicate_serial_nos` | `self` | `` |  |
| `test_purchase_receipt_gl_entry` | `self` | `` |  |
| `test_serial_no_warehouse` | `self` | `` |  |
| `test_rejected_warehouse_filter` | `self` | `` |  |
| `test_rejected_serial_no` | `self` | `` |  |
| `test_purchase_return_partial` | `self` | `` |  |
| `test_purchase_return_full` | `self` | `` |  |
| `test_purchase_return_for_rejected_qty` | `self` | `` |  |
| `test_purchase_receipt_for_rejected_gle_without_accepted_warehouse` | `self` | `` |  |
| `test_purchase_return_for_serialized_items` | `self` | `` |  |
| `test_purchase_return_for_multi_uom` | `self` | `` |  |
| `test_closed_purchase_receipt` | `self` | `` |  |
| `test_pr_billing_status` | `self` | `` | Flow:
1. PO -> PR1 -> PI
2. PO -> PI
3. PO -> PR2. |
| `test_serial_no_against_purchase_receipt` | `self` | `` |  |
| `test_auto_asset_creation` | `self` | `` |  |
| `test_purchase_return_with_submitted_asset` | `self` | `` |  |
| `test_purchase_receipt_cost_center` | `self` | `` |  |
| `test_purchase_receipt_cost_center_with_balance_sheet_account` | `self` | `` |  |
| `test_make_purchase_invoice_from_pr_for_returned_qty` | `self` | `` |  |
| `test_make_purchase_invoice_from_pr_with_returned_qty_duplicate_items` | `self` | `` |  |
| `test_stock_transfer_from_purchase_receipt` | `self` | `` |  |
| `test_stock_transfer_from_purchase_receipt_with_valuation` | `self` | `` |  |
| `test_po_to_pi_and_po_to_pr_worflow_full` | `self` | `` | Test following behaviour:
- Create PO
- Create PI from PO and submit
- Create PR from PO and submit |
| `test_po_to_pi_and_po_to_pr_worflow_partial` | `self` | `` | Test following behaviour:
- Create PO
- Create partial PI from PO and submit
- Create PR from PO and submit |
| `test_purchase_receipt_with_exchange_rate_difference` | `self` | `` |  |
| `test_payment_terms_are_fetched_when_creating_purchase_invoice` | `self` | `` |  |
| `test_neg_to_positive` | `self` | `` |  |
| `test_backdated_transaction_for_internal_transfer` | `self` | `` |  |
| `test_backdated_transaction_for_internal_transfer_in_trasit_warehouse_for_purchase_receipt` | `self` | `` |  |
| `test_backdated_transaction_for_internal_transfer_in_trasit_warehouse_for_purchase_invoice` | `self` | `` |  |
| `test_batch_expiry_for_purchase_receipt` | `self` | `` |  |
| `test_disable_last_purchase_rate` | `self` | `` |  |
| `test_validate_received_qty_for_internal_pr` | `self` | `` |  |
| `test_internal_pr_gl_entries` | `self` | `` |  |
| `test_internal_pr_reference` | `self` | `` |  |
| `test_purchase_return_valuation_with_rejected_qty` | `self` | `` |  |
| `test_return_from_rejected_warehouse` | `self` | `` |  |
| `test_purchase_receipt_with_backdated_landed_cost_voucher` | `self` | `` |  |
| `test_purchase_receipt_provisional_accounting` | `self` | `` |  |
| `test_purchase_return_status_with_debit_note` | `self` | `` |  |
| `test_purchase_return_with_zero_rate` | `self` | `` |  |
| `non_internal_transfer_purchase_receipt` | `self` | `` |  |
| `test_use_serial_batch_fields_for_serial_nos` | `self` | `` |  |
| `test_sle_qty_after_transaction` | `self` | `` |  |
| `test_auto_set_batch_based_on_bundle` | `self` | `` |  |
| `test_pr_billed_amount_against_return_entry` | `self` | `` |  |
| `test_valuation_taxes_lcv_repost_after_billing` | `self` | `` |  |
| `test_purchase_receipt_with_use_serial_batch_field_for_rejected_qty` | `self` | `` |  |
| `test_internal_transfer_with_serial_batch_items_and_their_valuation` | `self` | `` |  |
| `test_internal_transfer_with_serial_batch_items_without_use_serial_batch_fields` | `self` | `` |  |
| `test_purchase_receipt_bill_for_rejected_quantity_in_purchase_invoice` | `self` | `` |  |
| `test_zero_valuation_rate_for_batched_item` | `self` | `` |  |
| `test_purchase_return_from_accepted_and_rejected_warehouse` | `self` | `` |  |
| `test_manufacturing_and_expiry_date_for_batch` | `self` | `` |  |
| `test_purchase_return_from_rejected_warehouse` | `self` | `` |  |
| `test_tax_account_heads_on_lcv_and_item_repost` | `self` | `` | PO -> PR -> PI
PR -> LCV
Backdated `Repost Item valuation` should not merge tax account heads into stock_rbnb |
| `create_lcv` | `self, receipt_document_type, receipt_document, company, expense_account, charges` | `` |  |
| `test_tax_account_heads_on_item_repost_without_lcv` | `self` | `` | PO -> PR -> PI
Backdated `Repost Item valuation` should not merge tax account heads into stock_rbnb if Purchase Receipt was created first
This scenario is without LCV |
| `test_do_not_use_batchwise_valuation_rate` | `self` | `` |  |
| `test_status_mapping` | `self` | `` |  |
| `test_internal_transfer_for_batch_items_with_cancel` | `self` | `` |  |
| `test_internal_transfer_for_batch_items_with_cancel_use_serial_batch_fields` | `self` | `` |  |
| `test_sles_with_same_posting_datetime_and_creation` | `self` | `` |  |
| `test_same_stock_and_transaction_uom_conversion_factor` | `self` | `` |  |
| `test_purchase_receipt_return_valuation_without_use_serial_batch_field` | `self` | `` |  |
| `test_purchase_receipt_return_valuation_with_use_serial_batch_field` | `self` | `` |  |
| `test_purchase_return_partial_debit_note` | `self` | `` |  |
| `test_do_not_allow_to_inward_same_serial_no_multiple_times` | `self` | `` |  |
| `test_seral_no_return_validation` | `self` | `` |  |
| `test_batch_no_return_validation` | `self` | `` |  |
| `test_pr_status_based_on_invoices_with_update_stock` | `self` | `` |  |
| `test_recreate_stock_ledgers` | `self` | `` |  |
| `test_internal_pr_qty_change_only_single_batch` | `self` | `` |  |
| `test_valuation_rate_for_rejected_materials` | `self` | `` |  |
| `test_no_valuation_rate_for_rejected_materials` | `self` | `` |  |





## Functions

### `prepare_data_for_internal_transfer`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_sl_entries`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_gl_entries`
**Arguments:** `voucher_type, voucher_no, skip_cancelled, as_dict`
**Decorators:** ``

**Docstring:**
```

```
### `get_taxes`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_receipt`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

