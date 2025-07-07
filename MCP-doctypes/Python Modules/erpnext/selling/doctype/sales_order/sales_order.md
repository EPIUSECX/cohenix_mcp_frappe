# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/sales_order/sales_order.py`

## Classes

### `WarehouseRequired`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SalesOrder`
**Inherits:** `SellingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `enable_auto_reserve_stock` | `self` | `` |  |
| `set_has_unit_price_items` | `self` | `` | If permitted in settings and any item has 0 qty, the SO has unit price items. |
| `validate_po` | `self` | `` |  |
| `validate_for_items` | `self` | `` |  |
| `product_bundle_has_stock_item` | `self, product_bundle` | `` | Returns true if product bundle has stock item |
| `validate_sales_mntc_quotation` | `self` | `` |  |
| `validate_delivery_date` | `self` | `` |  |
| `validate_proj_cust` | `self` | `` |  |
| `validate_warehouse` | `self` | `` |  |
| `validate_with_previous_doc` | `self` | `` |  |
| `update_enquiry_status` | `self, prevdoc, flag` | `` |  |
| `update_prevdoc_status` | `self, flag` | `` |  |
| `validate_drop_ship` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `update_project` | `self` | `` |  |
| `check_credit_limit` | `self` | `` |  |
| `check_nextdoc_docstatus` | `self` | `` |  |
| `check_modified_date` | `self` | `` |  |
| `update_status` | `self, status` | `` |  |
| `update_reserved_qty` | `self, so_item_rows` | `` | update requested qty (before ordered_qty is updated) |
| `on_update` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `before_update_after_submit` | `self` | `` |  |
| `validate_supplier_after_submit` | `self` | `` | Check that supplier is the same after submit if PO is already made |
| `update_delivery_status` | `self` | `` | Update delivery status from Purchase Order for drop shipping |
| `update_picking_status` | `self` | `` |  |
| `set_indicator` | `self` | `` | Set indicator for portal |
| `on_recurring` | `self, reference_doc, auto_repeat_doc` | `` |  |
| `validate_serial_no_based_delivery` | `self` | `` |  |
| `validate_reserved_stock` | `self` | `` | Clean reserved stock flag for non-stock Item |
| `has_unreserved_stock` | `self` | `` | Returns True if there is any unreserved item in the Sales Order. |
| `create_stock_reservation_entries` | `self, items_details, from_voucher_type, notify` | `` | Creates Stock Reservation Entries for Sales Order Items. |
| `cancel_stock_reservation_entries` | `self, sre_list, notify` | `` | Cancel Stock Reservation Entries for Sales Order Items. |
| `set_missing_values` | `self, for_validate` | `` |  |





## Functions

### `get_unreserved_qty`
**Arguments:** `item, reserved_qty_details`
**Decorators:** ``

**Docstring:**
```
Returns the unreserved quantity for the Sales Order Item.
```
### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `is_enable_cutoff_date_on_bulk_delivery_note_creation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `close_or_unclose_sales_orders`
**Arguments:** `names, status`
**Decorators:** ``

**Docstring:**
```

```
### `get_requested_item_qty`
**Arguments:** `sales_order`
**Decorators:** ``

**Docstring:**
```

```
### `make_material_request`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_project`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_delivery_note`
**Arguments:** `source_name, target_doc, kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `make_sales_invoice`
**Arguments:** `source_name, target_doc, ignore_permissions`
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
### `make_maintenance_visit`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_events`
**Arguments:** `start, end, filters`
**Decorators:** ``

**Docstring:**
```
Returns events for Gantt / Calendar view rendering.

:param start: Start date-time.
:param end: End date-time.
:param filters: Filters (JSON).
```
### `make_purchase_order_for_default_supplier`
**Arguments:** `source_name, selected_items, target_doc`
**Decorators:** ``

**Docstring:**
```
Creates Purchase Order for each Supplier. Returns a list of doc objects.
```
### `make_purchase_order`
**Arguments:** `source_name, selected_items, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_delivery_date`
**Arguments:** `items, sales_order`
**Decorators:** ``

**Docstring:**
```

```
### `is_product_bundle`
**Arguments:** `item_code`
**Decorators:** ``

**Docstring:**
```

```
### `make_work_orders`
**Arguments:** `items, sales_order, company, project`
**Decorators:** ``

**Docstring:**
```
Make Work Orders against the given Sales Order for the given `items`
```
### `update_status`
**Arguments:** `status, name`
**Decorators:** ``

**Docstring:**
```

```
### `make_raw_material_request`
**Arguments:** `items, company, sales_order, project`
**Decorators:** ``

**Docstring:**
```

```
### `make_inter_company_purchase_order`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `create_pick_list`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_produced_qty_in_so_item`
**Arguments:** `sales_order, sales_order_item`
**Decorators:** ``

**Docstring:**
```

```
### `get_work_order_items`
**Arguments:** `sales_order, for_raw_material_request`
**Decorators:** ``

**Docstring:**
```
Returns items with BOM that already do not have a linked work order
```
### `get_stock_reservation_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

