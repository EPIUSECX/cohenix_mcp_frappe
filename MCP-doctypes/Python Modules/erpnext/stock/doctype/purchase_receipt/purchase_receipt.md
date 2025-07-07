# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/purchase_receipt/purchase_receipt.py`

## Classes

### `PurchaseReceipt`
**Inherits:** `BuyingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_uom_is_integer` | `self` | `` |  |
| `validate_cwip_accounts` | `self` | `` |  |
| `validate_provisional_expense_account` | `self` | `` |  |
| `validate_with_previous_doc` | `self` | `` |  |
| `po_required` | `self` | `` |  |
| `validate_items_quality_inspection` | `self` | `` |  |
| `get_already_received_qty` | `self, po, po_detail` | `` |  |
| `get_po_qty_and_warehouse` | `self, po_detail` | `` |  |
| `check_on_hold_or_closed_status` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `update_received_qty_if_from_pp` | `self` | `` |  |
| `check_next_docstatus` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `before_cancel` | `self` | `` |  |
| `remove_amount_difference_with_purchase_invoice` | `self` | `` |  |
| `get_gl_entries` | `self, warehouse_account, via_landed_cost_voucher` | `` |  |
| `make_item_gl_entries` | `self, gl_entries, warehouse_account` | `` |  |
| `add_provisional_gl_entry` | `self, item, gl_entries, posting_date, provisional_account, reverse, item_amount` | `` |  |
| `is_landed_cost_booked_for_any_item` | `self` | `` |  |
| `make_tax_gl_entries` | `self, gl_entries, via_landed_cost_voucher` | `` |  |
| `update_assets` | `self, item, valuation_rate` | `` |  |
| `update_status` | `self, status` | `` |  |
| `update_billing_status` | `self, update_modified` | `` |  |
| `reserve_stock` | `self` | `` |  |
| `reserve_stock_for_sales_order` | `self` | `` |  |
| `reserve_stock_for_production_plan` | `self` | `` |  |
| `get_production_plan_references` | `self` | `` |  |
| `enable_recalculate_rate_in_sles` | `self` | `` |  |





## Functions

### `get_stock_value_difference`
**Arguments:** `voucher_no, voucher_detail_no, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `update_billed_amount_based_on_po`
**Arguments:** `po_details, update_modified, pr_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_purchase_receipts_against_po_details`
**Arguments:** `po_details`
**Decorators:** ``

**Docstring:**
```

```
### `get_billed_amount_against_pr`
**Arguments:** `pr_items`
**Decorators:** ``

**Docstring:**
```

```
### `get_billed_amount_against_po`
**Arguments:** `po_items`
**Decorators:** ``

**Docstring:**
```

```
### `update_billing_percentage`
**Arguments:** `pr_doc, update_modified, adjust_incoming_rate`
**Decorators:** ``

**Docstring:**
```

```
### `get_billed_qty_against_purchase_receipt`
**Arguments:** `pr_doc`
**Decorators:** ``

**Docstring:**
```

```
### `adjust_incoming_rate_for_pr`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_wise_returned_qty`
**Arguments:** `pr_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_invoice`
**Arguments:** `source_name, target_doc, args`
**Decorators:** ``

**Docstring:**
```

```
### `get_invoiced_qty_map`
**Arguments:** `purchase_receipt`
**Decorators:** ``

**Docstring:**
```
returns a map: {pr_detail: invoiced_qty}
```
### `get_returned_qty_map`
**Arguments:** `purchase_receipt`
**Decorators:** ``

**Docstring:**
```
returns a map: {so_detail: returned_qty}
```
### `make_purchase_return_against_rejected_warehouse`
**Arguments:** `source_name`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_return`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_purchase_receipt_status`
**Arguments:** `docname, status`
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
### `make_inter_company_delivery_note`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_regional_gl_entries`
**Arguments:** `gl_list, doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_lcv`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```

