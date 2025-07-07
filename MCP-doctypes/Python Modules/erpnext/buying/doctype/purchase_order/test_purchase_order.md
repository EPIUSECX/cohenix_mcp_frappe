# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/purchase_order/test_purchase_order.py`

## Classes

### `TestPurchaseOrder`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_purchase_order_qty` | `self` | `` |  |
| `test_purchase_order_zero_qty` | `self` | `` |  |
| `test_make_purchase_receipt` | `self` | `` |  |
| `test_ordered_qty` | `self` | `` |  |
| `test_ordered_qty_against_pi_with_update_stock` | `self` | `` |  |
| `test_update_remove_child_linked_to_mr` | `self` | `` | Test impact on linked PO and MR on deleting/updating row. |
| `test_update_child` | `self` | `` |  |
| `test_update_child_adding_new_item` | `self` | `` |  |
| `test_update_child_removing_item` | `self` | `` |  |
| `test_update_child_perm` | `self` | `` |  |
| `test_update_child_with_tax_template` | `self` | `` | Test Action: Create a PO with one item having its tax account head already in the PO.
Add the same item + new item with tax template via Update Items.
Expected result: First Item's tax row is updated. New tax row is added for second Item. |
| `test_update_qty` | `self` | `` |  |
| `test_return_against_purchase_order` | `self` | `` |  |
| `test_purchase_order_invoice_receipt_workflow` | `self` | `` |  |
| `test_make_purchase_invoice` | `self` | `` |  |
| `test_purchase_order_on_hold` | `self` | `` |  |
| `test_make_purchase_invoice_with_terms` | `self` | `` |  |
| `test_warehouse_company_validation` | `self` | `` |  |
| `test_uom_integer_validation` | `self` | `` |  |
| `test_ordered_qty_for_closing_po` | `self` | `` |  |
| `test_group_same_items` | `self` | `` |  |
| `test_make_po_without_terms` | `self` | `` |  |
| `test_po_for_blocked_supplier_all` | `self` | `` |  |
| `test_po_for_blocked_supplier_invoices` | `self` | `` |  |
| `test_po_for_blocked_supplier_payments` | `self` | `` |  |
| `test_po_for_blocked_supplier_payments_with_today_date` | `self` | `` |  |
| `test_po_for_blocked_supplier_payments_past_date` | `self` | `` |  |
| `test_default_payment_terms` | `self` | `` |  |
| `test_terms_are_not_copied_if_automatically_fetch_payment_terms_is_unchecked` | `self` | `` |  |
| `test_terms_copied` | `self` | `` |  |
| `test_advance_payment_entry_unlink_against_purchase_order` | `self` | `` |  |
| `create_account` | `self, account_name, company, currency, parent` | `` |  |
| `test_advance_payment_with_separate_party_account_enabled` | `self` | `` | Test "Advance Paid" on Purchase Order, when "Book Advance Payments in Separate Party Account" is enabled and
the payment entry linked to the Order is allocated to Purchase Invoice. |
| `test_advance_paid_upon_payment_entry_cancellation` | `self` | `` |  |
| `test_schedule_date` | `self` | `` |  |
| `test_po_optional_blanket_order` | `self` | `` | Expected result: Blanket order Ordered Quantity should only be affected on Purchase Order with against_blanket_order = 1.
Second Purchase Order should not add on to Blanket Orders Ordered Quantity. |
| `test_blanket_order_on_po_close_and_open` | `self` | `` |  |
| `test_payment_terms_are_fetched_when_creating_purchase_invoice` | `self` | `` |  |
| `test_internal_transfer_flow` | `self` | `` |  |
| `test_variant_item_po` | `self` | `` |  |
| `test_update_items_for_subcontracting_purchase_order` | `self` | `` |  |
| `test_new_sc_flow` | `self` | `` |  |
| `test_auto_create_subcontracting_order` | `self` | `` |  |
| `test_purchase_order_advance_payment_status` | `self` | `` |  |
| `test_po_billed_amount_against_return_entry` | `self` | `` |  |
| `test_receive_zero_qty_purchase_order` | `self` | `` | Test the flow of a Unit Price PO and PR creation against it until completion.
Flow:
PO Qty 0 -> Receive +5 -> Receive +5 -> Update PO Qty +10 -> PO is 100% received |
| `test_bill_zero_qty_purchase_order` | `self` | `` |  |





## Functions

### `create_po_for_sc_testing`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `prepare_data_for_internal_transfer`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_pr_against_po`
**Arguments:** `po, received_qty`
**Decorators:** ``

**Docstring:**
```

```
### `get_same_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_purchase_order`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_pr_against_po`
**Arguments:** `po, received_qty`
**Decorators:** ``

**Docstring:**
```

```
### `get_ordered_qty`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_requested_qty`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```

