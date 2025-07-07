# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/report/stock_analytics/test_stock_analytics.py`

## Classes

### `TestStockAnalyticsReport`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `assert_single_item_report` | `self, movement, expected_buckets` | `` |  |
| `generate_stock` | `self, movement` | `` |  |
| `compare_analytics_row` | `self, report_row, columns, expected_buckets` | `` |  |
| `test_get_period_date_ranges` | `self` | `` |  |
| `test_get_period_date_ranges_yearly` | `self` | `` |  |
| `test_basic_report_functionality` | `self` | `` | Stock analytics report generates balance "as of" periods based on
user defined ranges. Check that this behaviour is correct. |
| `test_empty_month_in_between` | `self` | `` |  |
| `test_multi_month_missings` | `self` | `` |  |





## Functions

### `stock_analytics`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```

