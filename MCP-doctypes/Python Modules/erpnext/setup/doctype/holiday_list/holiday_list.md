# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/holiday_list/holiday_list.py`

## Classes

### `OverlapError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `HolidayList`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `get_weekly_off_dates` | `self` | `` |  |
| `get_supported_countries` | `self` | `` |  |
| `get_local_holidays` | `self` | `` |  |
| `sort_holidays` | `self` | `` |  |
| `get_holidays` | `self` | `` |  |
| `validate_days` | `self` | `` |  |
| `get_weekly_off_date_list` | `self, start_date, end_date` | `` |  |
| `clear_table` | `self` | `` |  |
| `validate_duplicate_date` | `self` | `` |  |





## Functions

### `get_events`
**Arguments:** `start, end, filters`
**Decorators:** ``

**Docstring:**
```
Returns events for Gantt / Calendar view rendering.

:param start: Start date-time.
:param end: End date-time.
:param filters: Filters (JSON).
```
### `is_holiday`
**Arguments:** `holiday_list, date`
**Decorators:** ``

**Docstring:**
```
Returns true if the given date is a holiday in the given holiday list
```
### `local_country_name`
**Arguments:** `country_code`
**Decorators:** ``

**Docstring:**
```
Return the localized country name for the given country code.
```

