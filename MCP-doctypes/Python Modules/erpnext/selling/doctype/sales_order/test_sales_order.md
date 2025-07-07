# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/sales_order/test_sales_order.py`

## Classes

### `TestSalesOrder`
**Inherits:** `AccountsTestMixin, IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_sales_order_with_negative_rate` | `self` | `` | Test if negative rate is allowed in Sales Order via doc submission and update items |
| `test_sales_order_qty` | `self` | `` |  |
| `test_sales_order_zero_qty` | `self` | `` |  |
| `test_make_material_request` | `self` | `` |  |
| `test_make_delivery_note` | `self` | `` |  |
| `test_make_sales_invoice` | `self` | `` |  |
| `test_so_billed_amount_against_return_entry` | `self` | `` |  |
| `test_make_sales_invoice_with_terms` | `self` | `` |  |
| `test_update_qty` | `self` | `` |  |
| `test_return_against_sales_order` | `self` | `` |  |
| `test_reserved_qty_for_partial_delivery` | `self` | `` |  |
| `test_reserved_qty_for_over_delivery` | `self` | `` |  |
| `test_reserved_qty_for_over_delivery_via_sales_invoice` | `self` | `` |  |
| `test_reserved_qty_for_partial_delivery_with_packing_list` | `self` | `` |  |
| `test_sales_order_on_hold` | `self` | `` |  |
| `test_reserved_qty_for_over_delivery_with_packing_list` | `self` | `` |  |
| `test_update_child_adding_new_item` | `self` | `` |  |
| `test_update_child_removing_item` | `self` | `` |  |
| `test_update_child` | `self` | `` |  |
| `test_update_child_with_precision` | `self` | `` |  |
| `test_update_child_perm` | `self` | `` |  |
| `test_update_child_qty_rate_with_workflow` | `self` | `` |  |
| `test_material_request_for_product_bundle` | `self` | `` |  |
| `test_bin_details_of_packed_item` | `self` | `` |  |
| `test_update_child_product_bundle` | `self` | `` |  |
| `test_update_child_with_tax_template` | `self` | `` | Test Action: Create a SO with one item having its tax account head already in the SO.
Add the same item + new item with tax template via Update Items.
Expected result: First Item's tax row is updated. New tax row is added for second Item. |
| `test_warehouse_user` | `self` | `` |  |
| `test_block_delivery_note_against_cancelled_sales_order` | `self` | `` |  |
| `test_service_type_product_bundle` | `self` | `` |  |
| `test_mix_type_product_bundle` | `self` | `` |  |
| `test_auto_insert_price` | `self` | `` |  |
| `test_update_existing_item_price` | `self` | `` |  |
| `test_drop_shipping` | `self` | `` |  |
| `test_drop_shipping_partial_order` | `self` | `` |  |
| `test_drop_shipping_full_for_default_suppliers` | `self` | `` | Test if multiple POs are generated in one go against different default suppliers. |
| `test_product_bundles_in_so_are_replaced_with_bundle_items_in_po` | `self` | `` | Tests if the the Product Bundles in the Items table of Sales Orders are replaced with
their child items(from the Packed Items table) on creating a Purchase Order from it. |
| `test_purchase_order_updates_packed_item_ordered_qty` | `self` | `` | Tests if the packed item's `ordered_qty` is updated with the quantity of the Purchase Order |
| `test_reserved_qty_for_closing_so` | `self` | `` |  |
| `test_create_so_with_margin` | `self` | `` |  |
| `test_terms_auto_added` | `self` | `` |  |
| `test_terms_not_copied` | `self` | `` |  |
| `test_terms_copied` | `self` | `` |  |
| `test_make_work_order` | `self` | `` |  |
| `test_advance_payment_entry_unlink_against_sales_order` | `self` | `` |  |
| `test_advance_paid_upon_payment_cancellation` | `self` | `` |  |
| `test_cancel_sales_order_after_cancel_payment_entry` | `self` | `` |  |
| `test_work_order_pop_up_from_sales_order` | `self` | `` | Test `get_work_order_items` in Sales Order picks the right BOM for items to manufacture. |
| `test_request_for_raw_materials` | `self` | `` |  |
| `test_so_optional_blanket_order` | `self` | `` | Expected result: Blanket order Ordered Quantity should only be affected on Sales Order with against_blanket_order = 1.
Second Sales Order should not add on to Blanket Orders Ordered Quantity. |
| `test_so_cancellation_when_si_drafted` | `self` | `` | Test to check if Sales Order gets cancelled if Sales Invoice is in Draft state
Expected result: sales order should not get cancelled |
| `test_so_cancellation_after_si_submission` | `self` | `` | Test to check if Sales Order gets cancelled when linked Sales Invoice has been Submitted
Expected result: Sales Order should not get cancelled |
| `test_so_cancellation_after_dn_submission` | `self` | `` | Test to check if Sales Order gets cancelled when linked Delivery Note has been Submitted
Expected result: Sales Order should not get cancelled |
| `test_so_cancellation_after_maintenance_schedule_submission` | `self` | `` | Expected result: Sales Order should not get cancelled |
| `test_so_cancellation_after_maintenance_visit_submission` | `self` | `` | Expected result: Sales Order should not get cancelled |
| `test_so_cancellation_after_work_order_submission` | `self` | `` | Expected result: Sales Order should not get cancelled |
| `test_payment_terms_are_fetched_when_creating_sales_invoice` | `self` | `` |  |
| `test_zero_amount_sales_order_billing_status` | `self` | `` |  |
| `test_so_billing_status_with_crnote_against_sales_return` | `self` | `` | | Step | Document creation                    |                               |
|------+--------------------------------------+-------------------------------|
|    1 | SO -> DN -> SI                       | SO Fully Billed and Completed |
|    2 | DN -> Sales Return(Partial)          | SO 50% Delivered, 100% billed |
|    3 | Sales Return(Partial) -> Credit Note | SO 50% Delivered, 50% billed  | |
| `test_so_back_updated_from_wo_via_mr` | `self` | `` | SO -> MR (Manufacture) -> WO. Test if WO Qty is updated in SO. |
| `test_sales_order_with_shipping_rule` | `self` | `` |  |
| `test_sales_order_partial_advance_payment` | `self` | `` |  |
| `test_delivered_item_material_request` | `self` | `` | SO -> MR (Manufacture) -> WO. Test if WO Qty is updated in SO. |
| `test_packed_items_for_partial_sales_order` | `self` | `` |  |
| `test_expired_rate_for_packed_item` | `self` | `` |  |
| `test_sales_order_advance_payment_status` | `self, mocked_get_payment_url` | `` |  |
| `test_pick_list_without_rejected_materials` | `self` | `` |  |
| `test_pick_list_for_batch` | `self` | `` |  |
| `test_auto_update_price_list` | `self` | `` |  |
| `test_delivery_note_rate_on_change_of_warehouse` | `self` | `` |  |
| `test_credit_limit_on_so_reopning` | `self` | `` |  |
| `test_warehouse_mapping_based_on_stock_reservation` | `self` | `` |  |
| `test_deliver_zero_qty_purchase_order` | `self` | `` | Test the flow of a Unit Price SO and DN creation against it until completion.
Flow:
SO Qty 0 -> Deliver +5 -> Update SO Qty +10 -> Deliver +5 -> SO is 100% delivered |
| `test_bill_zero_qty_sales_order` | `self` | `` |  |
| `test_item_tax_transfer_from_sales_to_purchase` | `self` | `` |  |





## Functions

### `automatically_fetch_payment_terms`
**Arguments:** `enable`
**Decorators:** ``

**Docstring:**
```

```
### `compare_payment_schedules`
**Arguments:** `doc, doc1, doc2`
**Decorators:** ``

**Docstring:**
```

```
### `make_sales_order`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_dn_against_so`
**Arguments:** `so, delivered_qty, do_not_submit`
**Decorators:** ``

**Docstring:**
```

```
### `get_reserved_qty`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `make_sales_order_workflow`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

