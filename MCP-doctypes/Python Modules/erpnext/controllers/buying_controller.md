# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/buying_controller.py`

## Classes

### `QtyMismatchError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `BuyingController`
**Inherits:** `SubcontractingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__setup__` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `validate_posting_date_with_po` | `self` | `` |  |
| `create_package_for_transfer` | `self` | `` | Create serial and batch package for Sourece Warehouse in case of inter transfer. |
| `set_rate_for_standalone_debit_note` | `self` | `` |  |
| `set_missing_values` | `self, for_validate` | `` |  |
| `set_supplier_from_item_default` | `self` | `` |  |
| `validate_stock_or_nonstock_items` | `self` | `` |  |
| `update_tax_category` | `self, msg` | `` |  |
| `validate_asset_return` | `self` | `` |  |
| `get_asset_items` | `self` | `` |  |
| `validate_from_warehouse` | `self` | `` |  |
| `set_supplier_address` | `self` | `` |  |
| `set_total_in_words` | `self` | `` |  |
| `update_valuation_rate` | `self, reset_outgoing_rate` | `` | item_tax_amount is the total tax amount applied on that item
stored for valuation

TODO: rename item_tax_amount to valuation_tax_amount |
| `get_tax_details` | `self` | `` |  |
| `get_item_tax_amount` | `self, item, tax_accounts` | `` |  |
| `get_item_actual_tax_amount` | `self, item, actual_tax_amount, stock_and_asset_items_amount, stock_and_asset_items_qty` | `` |  |
| `set_incoming_rate` | `self` | `` | Override item rate with incoming rate for internal stock transfer |
| `set_sales_incoming_rate_for_internal_transfer` | `self` | `` | Set incoming rate from the sales transaction against which the
purchase is made (internal transfer) |
| `validate_for_subcontracting` | `self` | `` |  |
| `set_qty_as_per_stock_uom` | `self` | `` |  |
| `validate_purchase_return` | `self` | `` |  |
| `validate_accepted_rejected_qty` | `self` | `` |  |
| `validate_negative_quantity` | `self, item_row, field_list` | `` |  |
| `check_for_on_hold_or_closed_status` | `self, ref_doctype, ref_fieldname` | `` |  |
| `update_stock_ledger` | `self, allow_negative_stock, via_landed_cost_voucher` | `` |  |
| `get_package_for_target_warehouse` | `self, item, warehouse, type_of_transaction` | `` |  |
| `update_ordered_and_reserved_qty` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate_budget` | `self` | `` |  |
| `process_fixed_asset` | `self` | `` |  |
| `auto_make_assets` | `self, asset_items` | `` |  |
| `make_asset` | `self, row, accounting_dimensions, is_grouped_asset` | `` |  |
| `update_fixed_asset` | `self, field, delete_asset` | `` |  |
| `delete_linked_asset` | `self` | `` |  |
| `validate_schedule_date` | `self` | `` |  |
| `validate_items` | `self` | `` |  |





## Functions

### `get_asset_item_details`
**Arguments:** `asset_items`
**Decorators:** ``

**Docstring:**
```

```
### `validate_item_type`
**Arguments:** `doc, fieldname, message`
**Decorators:** ``

**Docstring:**
```

```
### `update_regional_item_valuation_rate`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```

