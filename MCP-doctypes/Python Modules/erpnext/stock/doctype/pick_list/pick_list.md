# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/pick_list/pick_list.py`

## Classes

### `PickList`
**Inherits:** `TransactionBase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `validate_stock_qty` | `self` | `` |  |
| `check_serial_no_status` | `self` | `` |  |
| `validate_with_previous_doc` | `self` | `` |  |
| `validate_sales_order_percentage` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `validate_sales_order` | `self` | `` | Raises an exception if the `Sales Order` has reserved stock. |
| `validate_picked_items` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `validate_expired_batches` | `self` | `` |  |
| `make_bundle_using_old_serial_batch_fields` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `delink_serial_and_batch_bundle` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `linked_serial_and_batch_bundle` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `remove_serial_and_batch_bundle` | `self` | `` |  |
| `validate_serial_and_batch_bundle` | `self` | `` |  |
| `update_status` | `self, status, update_modified` | `` |  |
| `stock_entry_exists` | `self` | `` |  |
| `update_reference_qty` | `self` | `` |  |
| `update_packed_items_qty` | `self, packed_items` | `` |  |
| `update_sales_order_item_qty` | `self, so_items` | `` |  |
| `update_sales_order_picking_status` | `self` | `` |  |
| `create_stock_reservation_entries` | `self, notify` | `` | Creates Stock Reservation Entries for Sales Order Items against Pick List. |
| `cancel_stock_reservation_entries` | `self, notify` | `` | Cancel Stock Reservation Entries for Sales Order Items created against Pick List. |
| `validate_picked_qty` | `self, data` | `` |  |
| `set_item_locations` | `self, save` | `` |  |
| `aggregate_item_qty` | `self` | `` |  |
| `validate_for_qty` | `self` | `` |  |
| `before_print` | `self, settings` | `` |  |
| `group_similar_items` | `self` | `` |  |
| `update_bundle_picked_qty` | `self` | `` |  |
| `get_picked_items_details` | `self, items` | `` |  |
| `update_picked_item_from_current_pick_list` | `self, picked_items` | `` |  |
| `_get_pick_list_items` | `self, items` | `` |  |
| `_get_product_bundles` | `self` | `` |  |
| `_get_product_bundle_qty_map` | `self, bundles` | `` |  |
| `_compute_picked_qty_for_bundle` | `self, bundle_row, bundle_items` | `` | Compute how many full bundles can be created from picked items. |
| `has_unreserved_stock` | `self` | `` |  |
| `has_reserved_stock` | `self` | `` |  |





## Functions

### `update_pick_list_status`
**Arguments:** `pick_list`
**Decorators:** ``

**Docstring:**
```

```
### `get_picked_items_qty`
**Arguments:** `items, contains_packed_items`
**Decorators:** ``

**Docstring:**
```

```
### `validate_item_locations`
**Arguments:** `pick_list`
**Decorators:** ``

**Docstring:**
```

```
### `get_items_with_location_and_quantity`
**Arguments:** `item_doc, item_location_map, docstatus`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_item_locations`
**Arguments:** `item_code, from_warehouses, required_qty, company, ignore_validation, picked_item_details, consider_rejected_warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `get_locations_based_on_required_qty`
**Arguments:** `locations, required_qty`
**Decorators:** ``

**Docstring:**
```

```
### `validate_picked_materials`
**Arguments:** `item_code, required_qty, locations, picked_item_details`
**Decorators:** ``

**Docstring:**
```

```
### `filter_locations_by_picked_materials`
**Arguments:** `locations, picked_item_details`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_item_locations_for_serial_and_batched_item`
**Arguments:** `item_code, from_warehouses, required_qty, company, consider_rejected_warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_item_locations_for_serialized_item`
**Arguments:** `item_code, from_warehouses, company, consider_rejected_warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_item_locations_for_batched_item`
**Arguments:** `item_code, from_warehouses, consider_rejected_warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_item_locations_for_other_item`
**Arguments:** `item_code, from_warehouses, company, consider_rejected_warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `create_delivery_note`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `create_dn_wo_so`
**Arguments:** `pick_list, delivery_note`
**Decorators:** ``

**Docstring:**
```

```
### `create_dn_for_pick_lists`
**Arguments:** `source_name, target_doc, kwargs`
**Decorators:** ``

**Docstring:**
```
Get Items from Multiple Pick Lists and create a Delivery Note for filtered customer
```
### `create_dn_with_so`
**Arguments:** `sales_dict, pick_list`
**Decorators:** ``

**Docstring:**
```
Create Delivery Note for each customer (based on SO) in a Pick List.
```
### `create_dn_from_so`
**Arguments:** `pick_list, sales_order_list, delivery_note`
**Decorators:** ``

**Docstring:**
```

```
### `map_pl_locations`
**Arguments:** `pick_list, item_mapper, delivery_note, sales_order`
**Decorators:** ``

**Docstring:**
```

```
### `add_product_bundles_to_delivery_note`
**Arguments:** `pick_list, delivery_note, item_mapper, sales_order`
**Decorators:** ``

**Docstring:**
```
Add product bundles found in pick list to delivery note.

When mapping pick list items, the bundle item itself isn't part of the
locations. Dynamically fetch and add parent bundle item into DN.
```
### `create_stock_entry`
**Arguments:** `pick_list`
**Decorators:** ``

**Docstring:**
```

```
### `get_pending_work_orders`
**Arguments:** `doctype, txt, searchfield, start, page_length, filters, as_dict`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_details`
**Arguments:** `item_code, uom`
**Decorators:** ``

**Docstring:**
```

```
### `update_delivery_note_item`
**Arguments:** `source, target, delivery_note`
**Decorators:** ``

**Docstring:**
```

```
### `get_cost_center`
**Arguments:** `for_item, from_doctype, company`
**Decorators:** ``

**Docstring:**
```
Returns Cost Center for Item or Item Group
```
### `set_delivery_note_missing_values`
**Arguments:** `target`
**Decorators:** ``

**Docstring:**
```

```
### `stock_entry_exists`
**Arguments:** `pick_list_name`
**Decorators:** ``

**Docstring:**
```

```
### `update_stock_entry_based_on_work_order`
**Arguments:** `pick_list, stock_entry`
**Decorators:** ``

**Docstring:**
```

```
### `update_stock_entry_based_on_material_request`
**Arguments:** `pick_list, stock_entry`
**Decorators:** ``

**Docstring:**
```

```
### `update_stock_entry_items_with_no_reference`
**Arguments:** `pick_list, stock_entry`
**Decorators:** ``

**Docstring:**
```

```
### `update_common_item_properties`
**Arguments:** `item, location`
**Decorators:** ``

**Docstring:**
```

```
### `get_rejected_warehouses`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_pick_list_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```

