# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source/sources/postgresql.py`

## Classes

### `PostgresTableFactory`


**Docstring:**
```
Fetchs tables and columns from database and links from doctype
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data_source` | `` |  |
| `sync_tables` | `self, connection, tables, force` | `` |  |
| `get_tables` | `self, table_names` | `` |  |
| `get_db_tables` | `self, table_names` | `` |  |
| `should_ignore` | `self, table_name` | `` |  |
| `get_table` | `self, table_name` | `` |  |
| `get_all_columns` | `self` | `` |  |
| `get_table_columns` | `self, table` | `` |  |
| `get_column` | `self, column_name, column_type` | `` |  |


### `PostgresDatabase`
**Inherits:** `BaseDatabase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `sync_tables` | `self, tables, force` | `` |  |
| `get_table_preview` | `self, table, limit` | `` |  |
| `get_table_columns` | `self, table` | `` |  |
| `get_column_options` | `self, table, column, search_text, limit` | `` |  |





## Functions

No top-level functions found in this file.
