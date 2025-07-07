# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/quotation/test_quotation.py`

## Classes

### `TestQuotation`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_quotation_qty` | `self` | `` |  |
| `test_quotation_zero_qty` | `self` | `` | Test if Quote with zero qty (Unit Price Item) is conditionally allowed. |
| `test_make_quotation_without_terms` | `self` | `` |  |
| `test_make_sales_order_terms_copied` | `self` | `` |  |
| `test_do_not_add_ordered_items_in_new_sales_order` | `self` | `` |  |
| `test_gross_profit` | `self` | `` |  |
| `test_maintain_rate_in_sales_cycle_is_enforced` | `self` | `` |  |
| `test_make_sales_order_with_different_currency` | `self` | `` |  |
| `test_make_sales_order` | `self` | `` |  |
| `test_make_sales_order_with_terms` | `self` | `` |  |
| `test_valid_till_before_transaction_date` | `self` | `` |  |
| `test_so_from_expired_quotation` | `self` | `` |  |
| `test_create_quotation_with_margin` | `self` | `` |  |
| `test_create_two_quotations` | `self` | `` |  |
| `test_quotation_expiry` | `self` | `` |  |
| `test_product_bundle_mapping_on_creating_so` | `self` | `` |  |
| `test_product_bundle_price_calculation_when_calculate_bundle_price_is_unchecked` | `self` | `` |  |
| `test_product_bundle_price_calculation_when_calculate_bundle_price_is_checked` | `self` | `` |  |
| `test_product_bundle_price_calculation_for_multiple_product_bundles_when_calculate_bundle_price_is_checked` | `self` | `` |  |
| `test_packed_items_indices_are_reset_when_product_bundle_is_deleted_from_items_table` | `self` | `` |  |
| `test_alternative_items_with_stock_items` | `self` | `` | Check if taxes & totals considers only non-alternative items with:
- One set of non-alternative & alternative items [first 3 rows]
- One simple stock item |
| `test_alternative_items_with_service_items` | `self` | `` | Check if taxes & totals considers only non-alternative items with:
- One set of non-alternative & alternative service items [first 3 rows]
- One simple non-alternative service item
All having the same item code and unique item name/description due to
dynamic services |
| `test_amount_calculation_for_alternative_items` | `self` | `` | Make sure that the amount is calculated correctly for alternative items when the qty is changed. |
| `test_alternative_items_sales_order_mapping_with_stock_items` | `self` | `` |  |
| `test_uom_validation` | `self` | `` |  |
| `test_item_tax_template_for_quotation` | `self` | `` |  |
| `test_grand_total_and_rounded_total_values` | `self` | `` |  |
| `test_so_from_zero_qty_quotation` | `self` | `` |  |
| `test_duplicate_items_in_quotation` | `self` | `` |  |
| `test_make_quotation_qar_to_inr` | `self` | `` |  |





## Functions

### `enable_calculate_bundle_price`
**Arguments:** `enable`
**Decorators:** ``

**Docstring:**
```

```
### `get_quotation_dict`
**Arguments:** `party_name, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `make_quotation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

