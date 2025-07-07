# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/packed_item/test_packed_item.py`

## Classes

### `TestPackedItem`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```
Test impact on Packed Items table in various scenarios.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `test_adding_bundle_item` | `self` | `` | Test impact on packed items if bundle item row is added. |
| `test_updating_bundle_item` | `self` | `` | Test impact on packed items if bundle item row is updated. |
| `test_recurring_bundle_item` | `self` | `` | Test impact on packed items if same bundle item is added and removed. |
| `test_bundle_item_cumulative_price` | `self` | `` | Test if Bundle Item rate is cumulative from packed items. |
| `test_newly_mapped_doc_packed_items` | `self` | `` | Test impact on packed items in newly mapped DN from SO. |
| `test_reposting_packed_items` | `self` | `` |  |
| `assertReturns` | `self, original, returned` | `` |  |
| `test_returning_full_bundles` | `self` | `` |  |
| `test_returning_partial_bundles` | `self` | `` |  |
| `test_returning_partial_bundle_qty` | `self` | `` |  |





## Functions

### `create_product_bundle`
**Arguments:** `quantities, warehouse`
**Decorators:** ``

**Docstring:**
```
Get a new product_bundle for use in tests.

Create 10x required stock if warehouse is specified.
```

