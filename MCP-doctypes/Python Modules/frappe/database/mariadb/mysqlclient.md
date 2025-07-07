# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/database/mariadb/mysqlclient.py`

## Classes

### `MariaDBExceptionUtil`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `is_deadlocked` | `e` | `staticmethod` |  |
| `is_timedout` | `e` | `staticmethod` |  |
| `is_read_only_mode_error` | `e` | `staticmethod` |  |
| `is_table_missing` | `e` | `staticmethod` |  |
| `is_missing_table` | `e` | `staticmethod` |  |
| `is_missing_column` | `e` | `staticmethod` |  |
| `is_duplicate_fieldname` | `e` | `staticmethod` |  |
| `is_duplicate_entry` | `e` | `staticmethod` |  |
| `is_access_denied` | `e` | `staticmethod` |  |
| `cant_drop_field_or_key` | `e` | `staticmethod` |  |
| `is_syntax_error` | `e` | `staticmethod` |  |
| `is_statement_timeout` | `e` | `staticmethod` |  |
| `is_data_too_long` | `e` | `staticmethod` |  |
| `is_db_table_size_limit` | `e` | `staticmethod` |  |
| `is_primary_key_violation` | `e` | `staticmethod` |  |
| `is_unique_key_violation` | `e` | `staticmethod` |  |
| `is_interface_error` | `e` | `staticmethod` |  |


### `MariaDBConnectionUtil`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_connection` | `self` | `` |  |
| `_get_connection` | `self` | `` |  |
| `create_connection` | `self` | `` |  |
| `set_execution_timeout` | `self, seconds` | `` |  |
| `get_connection_settings` | `self` | `` |  |


### `MariaDBDatabase`
**Inherits:** `MariaDBConnectionUtil, MariaDBExceptionUtil, Database`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setup_type_map` | `self` | `` |  |
| `get_database_size` | `self` | `` | Return database size in MB. |
| `log_query` | `self, query, query_type, values, debug` | `` |  |
| `_clean_up` | `self` | `` |  |
| `escape` | `s, percent` | `staticmethod` | Escape quotes and percent in given string. |
| `is_type_number` | `code` | `staticmethod` |  |
| `is_type_datetime` | `code` | `staticmethod` |  |
| `rename_table` | `self, old_name, new_name` | `` |  |
| `describe` | `self, doctype` | `` |  |
| `change_column_type` | `self, doctype, column, type, nullable` | `` |  |
| `rename_column` | `self, doctype, old_column_name, new_column_name` | `` |  |
| `create_auth_table` | `self` | `` |  |
| `create_global_search_table` | `self` | `` |  |
| `create_user_settings_table` | `self` | `` |  |
| `get_on_duplicate_update` | `` | `staticmethod` |  |
| `get_table_columns_description` | `self, table_name` | `` | Return list of columns with descriptions. |
| `get_column_type` | `self, doctype, column` | `` | Return column type from database. |
| `has_index` | `self, table_name, index_name` | `` |  |
| `get_column_index` | `self, table_name, fieldname, unique` | `` | Check if column exists for a specific fields in specified order.

This differs from db.has_index because it doesn't rely on index name but columns inside an
index. |
| `add_index` | `self, doctype, fields, index_name` | `` | Creates an index with given fields if not already created.
Index name will be `fieldname1_fieldname2_index` |
| `add_unique` | `self, doctype, fields, constraint_name` | `` |  |
| `updatedb` | `self, doctype, meta` | `` | Syncs a `DocType` to the table
* creates if required
* updates columns
* updates indices |
| `get_database_list` | `self` | `` |  |
| `get_tables` | `self, cached` | `` | Return list of tables. |
| `get_row_size` | `self, doctype` | `` | Get estimated max row size of any table in bytes. |
| `unbuffered_cursor` | `self` | `contextmanager` |  |
| `estimate_count` | `self, doctype` | `` | Get estimated count of total rows in a table. |





## Functions

### `escape_frozenset`
**Arguments:** `obj, mapping`
**Decorators:** ``

**Docstring:**
```

```
### `escape_timedelta`
**Arguments:** `obj, mapping`
**Decorators:** ``

**Docstring:**
```

```
### `escape_dict`
**Arguments:** `obj, mapping`
**Decorators:** ``

**Docstring:**
```

```

