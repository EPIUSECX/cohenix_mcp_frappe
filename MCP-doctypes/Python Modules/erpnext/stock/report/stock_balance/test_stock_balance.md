# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/report/stock_balance/test_stock_balance.py`

## Classes

### `TestStockBalance`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `assertPartialDictEq` | `self, expected, actual` | `` |  |
| `generate_stock_ledger` | `self, item_code, movements` | `` |  |
| `assertInvariants` | `self, rows` | `` |  |
| `test_basic_stock_balance` | `self` | `` | Check very basic functionality and item info |
| `test_opening_balance` | `self` | `` |  |
| `test_uom_converted_info` | `self` | `` |  |
| `test_item_group` | `self` | `` |  |
| `test_child_warehouse_balances` | `self` | `` |  |
| `test_show_item_attr` | `self` | `` |  |





## Functions

### `stock_balance`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Get rows from stock balance report
```

