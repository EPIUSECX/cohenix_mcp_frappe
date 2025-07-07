# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_query/insights_legacy_query.py`

## Classes

### `InsightsLegacyQueryClient`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `add_table` | `self, table` | `` |  |
| `update_table` | `self, table` | `` |  |
| `remove_table` | `self, table` | `` |  |
| `add_column` | `self, column` | `` |  |
| `move_column` | `self, from_index, to_index` | `` |  |
| `update_column` | `self, column` | `` |  |
| `remove_column` | `self, column` | `` |  |
| `update_filters` | `self, filters` | `` |  |
| `sanitize_conditions` | `self, conditions` | `` |  |
| `fetch_tables` | `self` | `` |  |
| `fetch_columns` | `self` | `` |  |
| `fetch_column_values` | `self, column, search_text` | `` |  |
| `fetch_join_options` | `self, left_table, right_table` | `` |  |


### `InsightsLegacyQueryValidation`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_tables` | `self` | `` |  |
| `validate_limit` | `self` | `` |  |
| `validate_filters` | `self` | `` |  |
| `validate_columns` | `self` | `` |  |


### `InsightsLegacyQueryController`
**Inherits:** `InsightsLegacyQueryValidation`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doc` | `` |  |
| `before_save` | `self` | `` |  |
| `after_reset` | `self` | `` |  |
| `get_columns_from_results` | `self, results` | `` |  |
| `get_tables_columns` | `self` | `` |  |
| `get_selected_tables` | `self` | `` |  |
| `before_fetch` | `self` | `` |  |
| `after_fetch` | `self, results` | `` |  |
| `has_cumulative_columns` | `self` | `` |  |
| `fetch_results` | `self, additional_filters` | `` |  |
| `apply_additional_filters` | `self, additional_filters` | `` |  |
| `export_query` | `self` | `` |  |
| `import_query` | `self, exported_query` | `` |  |


### `LegacyQueryImporter`
**Inherits:** `BaseNestedQueryImporter`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `_update_doc` | `self` | `` |  |
| `_update_subquery_references` | `self` | `` |  |
| `_rename_subquery_in_table` | `self, old_name, new_name` | `` |  |
| `_rename_subquery_in_joins` | `self, old_name, new_name` | `` |  |
| `_rename_subquery_in_columns` | `self, old_name, new_name` | `` |  |
| `_rename_subquery_in_filters` | `self, old_name, new_name` | `` |  |





## Functions

No top-level functions found in this file.
