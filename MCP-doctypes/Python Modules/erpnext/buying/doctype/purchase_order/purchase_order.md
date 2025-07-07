# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/purchase_order/purchase_order.py`

## Classes

### `PurchaseOrder`
**Inherits:** `BuyingController`


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
| `set_has_unit_price_items` | `self` | `` | If permitted in settings and any item has 0 qty, the PO has unit price items. |
| `validate_with_previous_doc` | `self` | `` |  |
| `set_tax_withholding` | `self` | `` |  |
| `validate_supplier` | `self` | `` |  |
| `validate_minimum_order_qty` | `self` | `` |  |
| `validate_bom_for_subcontracting_items` | `self` | `` |  |
| `validate_fg_item_for_subcontracting` | `self` | `` |  |
| `get_schedule_dates` | `self` | `` |  |
| `get_last_purchase_rate` | `self` | `` | get last purchase rates for all items |
| `check_on_hold_or_closed_status` | `self` | `` |  |
| `update_ordered_qty` | `self, po_item_rows` | `` | update requested qty (before ordered_qty is updated) |
| `check_modified_date` | `self` | `` |  |
| `update_status` | `self, status` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `update_status_updater` | `self` | `` |  |
| `update_status_updater_if_from_pp` | `self` | `` |  |
| `update_delivered_qty_in_sales_order` | `self` | `` | Update delivered qty in Sales Order for drop ship |
| `has_drop_ship_item` | `self` | `` |  |
| `is_against_so` | `self` | `` |  |
| `is_against_pp` | `self` | `` |  |
| `set_received_qty_for_drop_ship_items` | `self` | `` |  |
| `update_reserved_qty_for_subcontract` | `self` | `` |  |
| `update_receiving_percentage` | `self` | `` |  |
| `set_service_items_for_finished_goods` | `self` | `` |  |
| `can_update_items` | `self` | `` |  |
| `update_ordered_qty_in_so_for_removed_items` | `self, removed_items` | `` | Updates ordered_qty in linked SO when item rows are removed using Update Items |
| `auto_create_subcontracting_order` | `self` | `` |  |
| `update_subcontracting_order_status` | `self` | `` |  |
| `set_missing_values` | `self, for_validate` | `` |  |





## Functions

### `item_last_purchase_rate`
**Arguments:** `name, conversion_rate, item_code, conversion_factor`
**Decorators:** ``

**Docstring:**
```
get last purchase rate for an item
```
### `close_or_unclose_purchase_orders`
**Arguments:** `names, status`
**Decorators:** ``

**Docstring:**
```

```
### `set_missing_values`
**Arguments:** `source, target`
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
### `make_purchase_invoice`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_invoice_from_portal`
**Arguments:** `purchase_order_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_mapped_purchase_invoice`
**Arguments:** `source_name, target_doc, ignore_permissions`
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
### `update_status`
**Arguments:** `status, name`
**Decorators:** ``

**Docstring:**
```

```
### `make_inter_company_sales_order`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_subcontracting_order`
**Arguments:** `source_name, target_doc, save, submit, notify`
**Decorators:** ``

**Docstring:**
```

```
### `is_po_fully_subcontracted`
**Arguments:** `po_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_mapped_subcontracting_order`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```

