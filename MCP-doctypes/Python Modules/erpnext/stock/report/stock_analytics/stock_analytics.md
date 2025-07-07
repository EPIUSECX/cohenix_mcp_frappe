# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/report/stock_analytics/stock_analytics.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_period_date_ranges`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `round_down_to_nearest_frequency`
**Arguments:** `date, frequency`
**Decorators:** ``

**Docstring:**
```
Rounds down the date to nearest frequency unit.
example:

>>> round_down_to_nearest_frequency("2021-02-21", "Monthly")
datetime.datetime(2021, 2, 1)

>>> round_down_to_nearest_frequency("2021-08-21", "Yearly")
datetime.datetime(2021, 1, 1)
```
### `get_period`
**Arguments:** `posting_date, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_periodic_data`
**Arguments:** `entry, filters`
**Decorators:** ``

**Docstring:**
```
Structured as:
Item 1
        - Balance (updated and carried forward):
                        - Warehouse A : bal_qty/value
                        - Warehouse B : bal_qty/value
        - Jun 2021 (sum of warehouse quantities used in report)
                        - Warehouse A : bal_qty/value
                        - Warehouse B : bal_qty/value
        - Jul 2021 (sum of warehouse quantities used in report)
                        - Warehouse A : bal_qty/value
                        - Warehouse B : bal_qty/value
Item 2
        - Balance (updated and carried forward):
                        - Warehouse A : bal_qty/value
                        - Warehouse B : bal_qty/value
        - Jun 2021 (sum of warehouse quantities used in report)
                        - Warehouse A : bal_qty/value
                        - Warehouse B : bal_qty/value
        - Jul 2021 (sum of warehouse quantities used in report)
                        - Warehouse A : bal_qty/value
                        - Warehouse B : bal_qty/value
```
### `fill_intermediate_periods`
**Arguments:** `periodic_data, item_code, current_period, all_periods`
**Decorators:** ``

**Docstring:**
```
There might be intermediate periods where no stock ledger entry exists, copy previous previous data.

Previous data is ONLY copied if period falls in report range and before period being processed currently.

args:
        current_period: process till this period (exclusive)
        all_periods: all periods expected in report via filters
        periodic_data: report's periodic data
        item_code: item_code being processed
```
### `get_data`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_chart_data`
**Arguments:** `columns`
**Decorators:** ``

**Docstring:**
```

```
### `get_items`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Get items based on item code, item group or brand.
```
### `get_stock_ledger_entries`
**Arguments:** `filters, items`
**Decorators:** ``

**Docstring:**
```

```
### `apply_conditions`
**Arguments:** `query, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_details`
**Arguments:** `items, sle`
**Decorators:** ``

**Docstring:**
```

```

