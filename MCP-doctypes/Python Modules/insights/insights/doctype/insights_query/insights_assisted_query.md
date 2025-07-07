# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_query/insights_assisted_query.py`

## Classes

### `InsightsAssistedQueryController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doc` | `` |  |
| `validate` | `self` | `` |  |
| `validate_if_all_column_tables_are_selected` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `query_json` | `self` | `property` |  |
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


### `AssistedQueryImporter`
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
| `_rename_subquery_in_calculations` | `self, old_name, new_name` | `` |  |
| `_rename_subquery_in_measures` | `self, old_name, new_name` | `` |  |
| `_rename_subquery_in_dimensions` | `self, old_name, new_name` | `` |  |
| `_rename_subquery_in_orders` | `self, old_name, new_name` | `` |  |





## Functions

No top-level functions found in this file.
