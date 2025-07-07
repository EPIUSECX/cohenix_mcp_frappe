# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/dashboard_chart/dashboard_chart.py`

## Classes

### `DashboardChart`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `on_update` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `check_required_field` | `self` | `` |  |
| `check_document_type` | `self` | `` |  |
| `validate_custom_options` | `self` | `` |  |





## Functions

### `get_permission_query_conditions`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `has_permission`
**Arguments:** `doc, ptype, user`
**Decorators:** ``

**Docstring:**
```

```
### `get`
**Arguments:** `chart_name, chart, no_cache, filters, from_date, to_date, timespan, time_interval, heatmap_year, refresh`
**Decorators:** `cache_source`

**Docstring:**
```

```
### `create_dashboard_chart`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `create_report_chart`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `add_chart_to_dashboard`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `get_chart_config`
**Arguments:** `chart, filters, timespan, timegrain, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_heatmap_chart_config`
**Arguments:** `chart, filters, heatmap_year`
**Decorators:** ``

**Docstring:**
```

```
### `get_group_by_chart_config`
**Arguments:** `chart, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_aggregate_function`
**Arguments:** `chart_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_result`
**Arguments:** `data, timegrain, from_date, to_date, chart_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_charts_for_user`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_parent_doctypes`
**Arguments:** `child_type`
**Decorators:** ``

**Docstring:**
```
Get all parent doctypes that have the child doctype.
```

