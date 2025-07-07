# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/tests/test_utils.py`

## Classes

### `StockTestMixin`


**Docstring:**
```
Mixin to simplfy stock ledger tests, useful for all stock transactions.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `make_item` | `self, item_code, properties` | `` |  |
| `assertSLEs` | `self, doc, expected_sles, sle_filters` | `` | Compare sorted SLEs, useful for vouchers that create multiple SLEs for same line |
| `assertGLEs` | `self, doc, expected_gles, gle_filters, order_by` | `` |  |


### `TestStockUtilities`
**Inherits:** `IntegrationTestCase, StockTestMixin`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_barcode_scanning` | `self` | `` |  |





## Functions

No top-level functions found in this file.
