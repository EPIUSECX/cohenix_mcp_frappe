# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/item/item.py`

## Classes

### `DuplicateReorderRows`


**Docstring:**
```

```

**Methods:**
No methods found.

### `StockExistsForTemplate`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidBarcode`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DataValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Item`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `autoname` | `self` | `` |  |
| `after_insert` | `self` | `` | set opening stock and item price |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `validate_description` | `self` | `` | Clean HTML description if set |
| `validate_customer_provided_part` | `self` | `` |  |
| `add_price` | `self, price_list` | `` | Add a new price |
| `set_opening_stock` | `self` | `` | set opening stock |
| `validate_fixed_asset` | `self` | `` |  |
| `validate_retain_sample` | `self` | `` |  |
| `clear_retain_sample` | `self` | `` |  |
| `add_default_uom_in_conversion_factor_table` | `self` | `` |  |
| `validate_item_tax_net_rate_range` | `self` | `` |  |
| `update_template_tables` | `self` | `` |  |
| `validate_conversion_factor` | `self` | `` |  |
| `validate_item_type` | `self` | `` |  |
| `validate_naming_series` | `self` | `` |  |
| `check_for_active_boms` | `self` | `` |  |
| `fill_customer_code` | `self` | `` | Append all the customer codes and insert into "customer_code" field of item table.
Used to search Item by customer code. |
| `check_item_tax` | `self` | `` | Check whether Tax Rate is not entered twice for same Tax Type |
| `validate_barcode` | `self` | `` |  |
| `validate_warehouse_for_reorder` | `self` | `` | Validate Reorder level table for duplicate and conditional mandatory |
| `stock_ledger_created` | `self` | `` |  |
| `update_item_price` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `before_rename` | `self, old_name, new_name, merge` | `` |  |
| `after_rename` | `self, old_name, new_name, merge` | `` |  |
| `delete_old_bins` | `self, old_name` | `` |  |
| `validate_duplicate_item_in_stock_reconciliation` | `self, old_name, new_name` | `` |  |
| `validate_properties_before_merge` | `self, new_name` | `` |  |
| `validate_duplicate_product_bundles_before_merge` | `self, old_name, new_name` | `` | Block merge if both old and new items have product bundles. |
| `set_last_purchase_rate` | `self, new_name` | `` |  |
| `recalculate_bin_qty` | `self, new_name` | `` |  |
| `update_bom_item_desc` | `self` | `` |  |
| `validate_item_defaults` | `self` | `` |  |
| `update_defaults_from_item_group` | `self` | `` | Get defaults from Item Group |
| `update_variants` | `self` | `` |  |
| `validate_has_variants` | `self` | `` |  |
| `validate_attributes_in_variants` | `self` | `` |  |
| `validate_stock_exists_for_template_item` | `self` | `` |  |
| `validate_variant_based_on_change` | `self` | `` |  |
| `validate_uom` | `self` | `` |  |
| `validate_uom_conversion_factor` | `self` | `` |  |
| `validate_attributes` | `self` | `` |  |
| `validate_variant_attributes` | `self` | `` |  |
| `cant_change` | `self` | `` |  |
| `_get_linked_submitted_documents` | `self, changed_fields` | `` |  |
| `validate_auto_reorder_enabled_in_stock_settings` | `self` | `` |  |





## Functions

### `convert_erpnext_to_barcodenumber`
**Arguments:** `erpnext_number, barcode`
**Decorators:** ``

**Docstring:**
```

```
### `make_item_price`
**Arguments:** `item, price_list_name, item_price`
**Decorators:** ``

**Docstring:**
```

```
### `get_timeline_data`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
get timeline data based on Stock Ledger Entry. This is displayed as heatmap on the item page.
```
### `validate_end_of_life`
**Arguments:** `item_code, end_of_life, disabled`
**Decorators:** ``

**Docstring:**
```

```
### `validate_is_stock_item`
**Arguments:** `item_code, is_stock_item`
**Decorators:** ``

**Docstring:**
```

```
### `validate_cancelled_item`
**Arguments:** `item_code, docstatus`
**Decorators:** ``

**Docstring:**
```

```
### `get_last_purchase_details`
**Arguments:** `item_code, doc_name, conversion_rate`
**Decorators:** ``

**Docstring:**
```
returns last purchase details in stock uom
```
### `get_purchase_voucher_details`
**Arguments:** `doctype, item_code, document_name`
**Decorators:** ``

**Docstring:**
```

```
### `check_stock_uom_with_bin`
**Arguments:** `item, stock_uom`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_defaults`
**Arguments:** `item_code, company`
**Decorators:** ``

**Docstring:**
```

```
### `set_item_default`
**Arguments:** `item_code, company, fieldname, value`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_details`
**Arguments:** `item_code, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_uom_conv_factor`
**Arguments:** `uom, stock_uom`
**Decorators:** ``

**Docstring:**
```
Get UOM conversion factor from uom to stock_uom
e.g. uom = "Kg", stock_uom = "Gram" then returns 1000.0
```
### `get_item_attribute`
**Arguments:** `parent, attribute_value`
**Decorators:** ``

**Docstring:**
```
Used for providing auto-completions in child table.
```
### `update_variants`
**Arguments:** `variants, template, publish_progress`
**Decorators:** ``

**Docstring:**
```

```
### `validate_item_default_company_links`
**Arguments:** `item_defaults`
**Decorators:** ``

**Docstring:**
```

```
### `get_asset_naming_series`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_child_warehouses`
**Arguments:** `warehouse`
**Decorators:** ``

**Docstring:**
```

```

