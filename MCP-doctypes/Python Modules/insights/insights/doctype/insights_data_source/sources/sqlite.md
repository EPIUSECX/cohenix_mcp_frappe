# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source/sources/sqlite.py`

## Classes

### `SQLiteTableFactory`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data_source` | `` |  |
| `sync_tables` | `self, connection, tables, force` | `` |  |
| `get_tables` | `self, table_names` | `` |  |
| `get_db_tables` | `self, table_names` | `` |  |
| `get_table` | `self, table_name` | `` |  |
| `get_table_columns` | `self, table_name` | `` |  |
| `get_column_type` | `self, column_type` | `` |  |


### `SQLiteDB`
**Inherits:** `BaseDatabase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data_source, database_name` | `` |  |
| `sync_tables` | `self, tables, force` | `` |  |
| `get_table_preview` | `self, table, limit` | `` |  |
| `get_table_columns` | `self, table` | `` |  |
| `get_column_options` | `self, table, column, search_text, limit` | `` |  |
| `table_exists` | `self, table` | `` |  |
| `import_table` | `self, import_doc` | `` |  |





## Functions

No top-level functions found in this file.
