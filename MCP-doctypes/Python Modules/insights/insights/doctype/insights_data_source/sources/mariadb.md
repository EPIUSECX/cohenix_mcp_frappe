# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source/sources/mariadb.py`

## Classes

### `MariaDBTableFactory`


**Docstring:**
```
Fetchs tables and columns from database and links from doctype
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data_source` | `` |  |
| `sync_tables` | `self, connection, tablenames, force` | `` |  |
| `get_table` | `self, table_name` | `` |  |
| `get_columns_by_tables` | `self, tablenames` | `` |  |
| `get_column` | `self, column_name, column_type` | `` |  |


### `MariaDB`
**Inherits:** `BaseDatabase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data_source, host, port, username, password, database_name, use_ssl` | `` |  |
| `connect` | `self` | `` |  |
| `handle_db_connection_error` | `self, e` | `` |  |
| `sync_tables` | `self, tables, force` | `` |  |
| `get_table_preview` | `self, table, limit` | `` |  |
| `get_table_columns` | `self, table` | `` |  |
| `get_column_options` | `self, table, column, search_text, limit` | `` |  |





## Functions

No top-level functions found in this file.
