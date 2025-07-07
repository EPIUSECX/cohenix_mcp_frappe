# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/delivery_note/delivery_note.py`

## Classes

### `DeliveryNote`
**Inherits:** `SellingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `before_print` | `self, settings` | `` |  |
| `set_actual_qty` | `self` | `` |  |
| `so_required` | `self` | `` | check in manage account if sales order required or not |
| `validate` | `self` | `` |  |
| `validate_with_previous_doc` | `self` | `` |  |
| `set_serial_and_batch_bundle_from_pick_list` | `self` | `` |  |
| `validate_references` | `self` | `` |  |
| `validate_sales_order_references` | `self` | `` |  |
| `validate_sales_invoice_references` | `self` | `` |  |
| `_validate_dependent_item_fields` | `self, field_a, field_b, error_title` | `` |  |
| `validate_proj_cust` | `self` | `` | check for does customer belong to same project as entered.. |
| `validate_warehouse` | `self` | `` |  |
| `update_current_stock` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate_against_stock_reservation_entries` | `self` | `` | Validates if Stock Reservation Entries are available for the Sales Order Item reference. |
| `check_credit_limit` | `self` | `` |  |
| `validate_packed_qty` | `self` | `` | Validate that if packed qty exists, it should be equal to qty |
| `update_pick_list_status` | `self` | `` |  |
| `check_next_docstatus` | `self` | `` |  |
| `cancel_packing_slips` | `self` | `` | Cancel submitted packing slips related to this delivery note |
| `update_status` | `self, status` | `` |  |
| `update_billing_status` | `self, update_modified` | `` |  |
| `make_return_invoice` | `self` | `` |  |
| `has_unpacked_items` | `self` | `` |  |
| `get_product_bundle_list` | `self` | `` |  |





## Functions

### `update_billed_amount_based_on_so`
**Arguments:** `so_detail, update_modified`
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
### `get_invoiced_qty_map`
**Arguments:** `delivery_note`
**Decorators:** ``

**Docstring:**
```
returns a map: {dn_detail: invoiced_qty}
```
### `get_returned_qty_map`
**Arguments:** `delivery_note`
**Decorators:** ``

**Docstring:**
```
returns a map: {so_detail: returned_qty}
```
### `make_sales_invoice`
**Arguments:** `source_name, target_doc, args`
**Decorators:** ``

**Docstring:**
```

```
### `make_delivery_trip`
**Arguments:** `source_name, target_doc, kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `make_installation_note`
**Arguments:** `source_name, target_doc, kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `make_packing_slip`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_shipment`
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
### `update_delivery_note_status`
**Arguments:** `docname, status`
**Decorators:** ``

**Docstring:**
```

```
### `make_inter_company_purchase_receipt`
**Arguments:** `source_name, target_doc`
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

