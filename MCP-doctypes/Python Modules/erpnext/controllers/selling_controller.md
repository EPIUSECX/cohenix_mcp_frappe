# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/selling_controller.py`

## Classes

### `SellingController`
**Inherits:** `StockController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__setup__` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `set_missing_values` | `self, for_validate` | `` |  |
| `set_missing_lead_customer_details` | `self, for_validate` | `` |  |
| `set_price_list_and_item_details` | `self, for_validate` | `` |  |
| `remove_shipping_charge` | `self` | `` |  |
| `set_total_in_words` | `self` | `` |  |
| `calculate_commission` | `self` | `` |  |
| `calculate_contribution` | `self` | `` |  |
| `validate_sales_team` | `self, sales_team` | `` |  |
| `validate_max_discount` | `self` | `` |  |
| `set_qty_as_per_stock_uom` | `self` | `` |  |
| `validate_selling_price` | `self` | `` |  |
| `get_item_list` | `self` | `` |  |
| `has_product_bundle` | `self, item_code` | `` |  |
| `_fetch_product_bundle_items` | `self, item_code` | `` |  |
| `get_already_delivered_qty` | `self, current_docname, so, so_detail` | `` |  |
| `get_so_qty_and_warehouse` | `self, so_detail` | `` |  |
| `check_sales_order_on_hold_or_close` | `self, ref_fieldname` | `` |  |
| `update_reserved_qty` | `self` | `` |  |
| `set_incoming_rate` | `self` | `` |  |
| `update_stock_ledger` | `self, allow_negative_stock` | `` |  |
| `get_sle_for_source_warehouse` | `self, item_row` | `` |  |
| `get_sle_for_target_warehouse` | `self, item_row` | `` |  |
| `set_po_nos` | `self, for_validate` | `` |  |
| `set_pos_for_sales_invoice` | `self` | `` |  |
| `set_pos_for_delivery_note` | `self` | `` |  |
| `get_po_nos` | `self, ref_doctype, ref_fieldname, po_nos` | `` |  |
| `set_gross_profit` | `self` | `` |  |
| `set_customer_address` | `self` | `` |  |
| `validate_for_duplicate_items` | `self` | `` |  |
| `validate_target_warehouse` | `self` | `` |  |
| `validate_items` | `self` | `` |  |
| `update_stock_reservation_entries` | `self` | `` | Updates Delivered Qty in Stock Reservation Entries. |





## Functions

### `set_default_income_account_for_item`
**Arguments:** `obj`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_and_batch_bundle`
**Arguments:** `child, parent, delivery_note_child`
**Decorators:** ``

**Docstring:**
```

```

