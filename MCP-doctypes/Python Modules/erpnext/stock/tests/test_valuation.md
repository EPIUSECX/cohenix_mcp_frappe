# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/tests/test_valuation.py`

## Classes

### `TestFIFOValuation`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `assertTotalQty` | `self, qty` | `` |  |
| `assertTotalValue` | `self, value` | `` |  |
| `test_simple_addition` | `self` | `` |  |
| `test_simple_removal` | `self` | `` |  |
| `test_merge_new_stock` | `self` | `` |  |
| `test_adding_negative_stock_keeps_rate` | `self` | `` |  |
| `test_adding_negative_stock_updates_rate` | `self` | `` |  |
| `test_negative_stock` | `self` | `` |  |
| `test_removing_specified_rate` | `self` | `` |  |
| `test_remove_multiple_bins` | `self` | `` |  |
| `test_remove_multiple_bins_with_rate` | `self` | `` |  |
| `test_queue_with_unknown_rate` | `self` | `` |  |
| `test_rounding_off` | `self` | `` |  |
| `test_rounding_off_near_zero` | `self` | `` |  |
| `test_totals` | `self` | `` |  |
| `test_fifo_qty_hypothesis` | `self, stock_queue` | `` |  |
| `test_fifo_qty_value_nonneg_hypothesis` | `self, stock_queue` | `` |  |
| `test_fifo_qty_value_nonneg_hypothesis_with_outgoing_rate` | `self, stock_queue, outgoing_rate` | `` |  |


### `TestLIFOValuation`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `assertTotalQty` | `self, qty` | `` |  |
| `assertTotalValue` | `self, value` | `` |  |
| `test_simple_addition` | `self` | `` |  |
| `test_merge_new_stock` | `self` | `` |  |
| `test_simple_removal` | `self` | `` |  |
| `test_adding_negative_stock_keeps_rate` | `self` | `` |  |
| `test_adding_negative_stock_updates_rate` | `self` | `` |  |
| `test_rounding_off` | `self` | `` |  |
| `test_lifo_consumption` | `self` | `` |  |
| `test_lifo_consumption_going_negative` | `self` | `` |  |
| `test_lifo_consumption_multiple` | `self` | `` |  |
| `test_lifo_qty_hypothesis` | `self, stock_stack` | `` |  |
| `test_lifo_qty_value_nonneg_hypothesis` | `self, stock_stack` | `` |  |


### `TestLIFOValuationSLE`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `_make_stock_entry` | `self, qty, rate` | `` |  |
| `assertStockQueue` | `self, se, expected_queue` | `` |  |
| `test_lifo_values` | `self` | `` |  |





## Functions

No top-level functions found in this file.
