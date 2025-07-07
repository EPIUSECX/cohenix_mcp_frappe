# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source/sources/frappe_db.py`

## Classes

### `FrappeTableFactory`


**Docstring:**
```
Fetchs tables and columns from database and links from doctype
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data_source` | `` |  |
| `sync_tables` | `self, connection, tablenames, force` | `` |  |
| `get_columns_by_tables` | `self, tablenames` | `` |  |
| `get_table` | `self, table_name` | `` |  |
| `get_column` | `self, column_name, column_type` | `` |  |
| `get_table_links` | `self, doctype` | `` |  |
| `get_all_links` | `self` | `` |  |
| `get_dynamic_link_map` | `self` | `` |  |


### `FrappeDB`
**Inherits:** `MariaDB`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data_source, host, port, username, password, database_name, use_ssl` | `` |  |
| `test_connection` | `self, log_errors` | `` |  |
| `handle_db_connection_error` | `self, e` | `` |  |
| `sync_tables` | `self, tables, force` | `` |  |
| `get_table_preview` | `self, table, limit` | `` |  |
| `get_table_columns` | `self, table` | `` |  |
| `get_column_options` | `self, table, column, search_text, limit` | `` |  |


### `SiteDB`
**Inherits:** `FrappeDB`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data_source` | `` |  |





## Functions

### `is_frappe_db`
**Arguments:** `db_params`
**Decorators:** ``

**Docstring:**
```

```

