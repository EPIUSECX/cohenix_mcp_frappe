# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source_v3/ibis_utils.py`

## Classes

### `IbisQueryBuilder`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doc, active_operation_idx` | `` |  |
| `set_operations` | `self` | `` |  |
| `build` | `self` | `` |  |
| `perform_operation` | `self, operation` | `` |  |
| `get_table_or_query` | `self, table_args` | `` |  |
| `get_column` | `self, column_name, throw` | `` |  |
| `apply_source` | `self, source_args` | `` |  |
| `apply_join` | `self, join_args` | `` |  |
| `get_right_table` | `self, join_args` | `` |  |
| `get_columns_from_expression` | `self, expression, table` | `` |  |
| `translate_join_condition` | `self, join_args, right_table` | `` |  |
| `rename_duplicate_columns` | `self, right_table` | `` |  |
| `apply_union` | `self, union_args` | `` |  |
| `apply_filter` | `self, filter_args` | `` |  |
| `make_filter_condition` | `self, filter_args` | `` |  |
| `get_operator` | `self, operator` | `` |  |
| `apply_filter_group` | `self, filter_group_args` | `` |  |
| `apply_select` | `self, select_args` | `` |  |
| `apply_rename` | `self, rename_args` | `` |  |
| `apply_remove` | `self, remove_args` | `` |  |
| `apply_cast` | `self, cast_args` | `` |  |
| `get_ibis_dtype` | `self, data_type` | `` |  |
| `apply_mutate` | `self, mutate_args` | `` |  |
| `apply_summary` | `self, summarize_args` | `` |  |
| `apply_order_by` | `self, order_by_args` | `` |  |
| `apply_limit` | `self, limit_args` | `` |  |
| `apply_pivot` | `self, pivot_args, pivot_type` | `` |  |
| `apply_custom_operation` | `self, operation` | `` |  |
| `apply_sql` | `self, sql_args` | `` |  |
| `apply_code` | `self, code_args` | `` |  |
| `translate_measure` | `self, measure` | `` |  |
| `translate_dimension` | `self, dimension` | `` |  |
| `is_date_type` | `self, data_type` | `` |  |
| `apply_aggregate` | `self, column, aggregate_function` | `` |  |
| `apply_granularity` | `self, column, granularity` | `` |  |
| `evaluate_expression` | `self, expression, additonal_context` | `` |  |
| `get_current_columns` | `self` | `` |  |


### `SafePandasDataFrame`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `to_csv` | `self` | `` |  |
| `to_json` | `self` | `` |  |





## Functions

### `execute_ibis_query`
**Arguments:** `query, limit, force, cache, cache_expiry, reference_doctype, reference_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns_from_schema`
**Arguments:** `schema`
**Decorators:** ``

**Docstring:**
```

```
### `to_insights_type`
**Arguments:** `dtype`
**Decorators:** ``

**Docstring:**
```

```
### `cache_results`
**Arguments:** `cache_key, result, cache_expiry`
**Decorators:** ``

**Docstring:**
```

```
### `get_cached_results`
**Arguments:** `cache_key`
**Decorators:** ``

**Docstring:**
```

```
### `has_cached_results`
**Arguments:** `cache_key`
**Decorators:** ``

**Docstring:**
```

```
### `exec_with_return`
**Arguments:** `script, _globals, _locals`
**Decorators:** ``

**Docstring:**
```

```
### `get_ibis_table_name`
**Arguments:** `table`
**Decorators:** ``

**Docstring:**
```

```
### `sanitize_name`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `get_code_results`
**Arguments:** `code`
**Decorators:** ``

**Docstring:**
```

```

