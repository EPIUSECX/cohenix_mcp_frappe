# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/item/test_item.py`

## Classes

### `TestItem`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `get_item` | `self, idx` | `` |  |
| `test_get_item_details` | `self` | `` |  |
| `test_get_asset_item_details` | `self` | `` |  |
| `test_item_tax_template` | `self` | `` |  |
| `test_item_defaults` | `self` | `` |  |
| `test_item_default_validations` | `self` | `` |  |
| `test_item_attribute_change_after_variant` | `self` | `` |  |
| `test_make_item_variant` | `self` | `` |  |
| `test_copy_fields_from_template_to_variants` | `self` | `` |  |
| `test_make_item_variant_with_numeric_values` | `self` | `` |  |
| `test_item_merging` | `self` | `` |  |
| `test_item_merging_with_product_bundle` | `self` | `` |  |
| `test_uom_conversion_factor` | `self` | `` |  |
| `test_uom_conv_intermediate` | `self` | `` |  |
| `test_uom_conv_base_case` | `self` | `` |  |
| `test_item_variant_by_manufacturer` | `self` | `` |  |
| `test_stock_exists_against_template_item` | `self` | `` |  |
| `test_add_item_barcode` | `self` | `` |  |
| `test_heatmap_data` | `self` | `` |  |
| `test_index_creation` | `self` | `` | check if index is getting created in db |
| `test_attribute_completions` | `self` | `` |  |
| `test_check_stock_uom_with_bin` | `self` | `` |  |
| `test_check_stock_uom_with_bin_no_sle` | `self` | `` |  |
| `test_erasure_of_old_conversions` | `self` | `` |  |
| `test_validate_stock_item` | `self` | `` |  |
| `test_autoname_series` | `self` | `` |  |
| `test_item_wise_negative_stock` | `self` | `` | When global settings are disabled check that item that allows
negative stock can still consume material in all known stock
transactions that consume inventory. |
| `test_backdated_negative_stock` | `self` | `` | same as test above but backdated entries |
| `test_retain_sample` | `self` | `` |  |
| `consume_item_code_with_differet_stock_transactions` | `self, item_code, warehouse` | `` |  |
| `test_item_dashboard` | `self` | `` |  |
| `test_empty_description` | `self` | `` |  |
| `test_item_type_field_change` | `self` | `` | Check if critical fields like `is_stock_item`, `has_batch_no` are not changed if transactions exist. |
| `test_customer_codes_length` | `self` | `` | Check if item code with special characters are allowed. |
| `test_update_is_stock_item` | `self` | `` |  |
| `test_serach_fields_for_item` | `self` | `` |  |
| `test_group_warehouse_for_reorder_item` | `self` | `` |  |
| `test_variant_uom_mismatch_throws_error` | `self` | `` |  |





## Functions

### `make_item`
**Arguments:** `item_code, properties, uoms, barcode`
**Decorators:** ``

**Docstring:**
```

```
### `set_item_variant_settings`
**Arguments:** `fields`
**Decorators:** ``

**Docstring:**
```

```
### `make_item_variant`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_item`
**Arguments:** `item_code, is_stock_item, valuation_rate, stock_uom, warehouse, is_customer_provided_item, customer, is_purchase_item, opening_stock, is_fixed_asset, asset_category, buying_cost_center, selling_cost_center, company`
**Decorators:** ``

**Docstring:**
```

```

