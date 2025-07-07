# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source/insights_data_source.py`

## Classes

### `InsightsDataSourceDocument`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_insert` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_sqlite_fields` | `self` | `` |  |
| `validate_remote_db_fields` | `self` | `` |  |


### `InsightsDataSourceClient`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_tables` | `self` | `` |  |
| `get_queries` | `self` | `` |  |
| `get_schema` | `self` | `` |  |
| `enqueue_sync_tables` | `self` | `` |  |
| `update_table_link` | `self, data` | `` |  |
| `delete_table_link` | `self, data` | `` |  |


### `InsightsDataSource`
**Inherits:** `InsightsDataSourceDocument, InsightsDataSourceClient, Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `_db` | `self` | `cached_property` |  |
| `test_connection` | `self, raise_exception` | `` |  |
| `sync_tables` | `self, tables, force` | `` |  |
| `build_query` | `self, query` | `` |  |
| `run_query` | `self, query` | `` |  |
| `execute_query` | `self, query` | `` |  |
| `get_table_columns` | `self, table` | `` |  |
| `get_column_options` | `self, table, column, search_text, limit` | `` |  |
| `get_table_preview` | `self, table, limit` | `` |  |





## Functions

### `get_data_source_schema`
**Arguments:** `data_source`
**Decorators:** ``

**Docstring:**
```

```

