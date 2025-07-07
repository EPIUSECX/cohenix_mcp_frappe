# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/database/sqlite/database.py`

## Classes

### `SQLiteExceptionUtil`


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
| `is_nested_transaction_error` | `e` | `staticmethod` |  |


### `SQLiteDatabase`
**Inherits:** `SQLiteExceptionUtil, Database`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_connection` | `self, read_only` | `` |  |
| `create_connection` | `self, read_only` | `` |  |
| `get_db_path` | `self` | `` |  |
| `set_execution_timeout` | `self, seconds` | `` |  |
| `setup_type_map` | `self` | `` |  |
| `get_database_size` | `self` | `` | Return database size in MB. |
| `_clean_up` | `self` | `` |  |
| `escape` | `s, percent` | `staticmethod` | Escape quotes and percent in given string. |
| `is_type_number` | `code` | `staticmethod` |  |
| `is_type_datetime` | `code` | `staticmethod` |  |
| `rename_table` | `self, old_name, new_name` | `` |  |
| `describe` | `self, doctype` | `` |  |
| `change_column_type` | `self, doctype, column, type, nullable` | `` | Change column type by recreating the table |
| `rename_column` | `self, doctype, old_column_name, new_column_name` | `` | Rename column by recreating the table |
| `create_auth_table` | `self` | `` |  |
| `create_global_search_table` | `self` | `` |  |
| `create_user_settings_table` | `self` | `` |  |
| `get_on_duplicate_update` | `` | `staticmethod` |  |
| `get_table_columns_description` | `self, table_name` | `` | Return list of columns with descriptions. |
| `get_column_type` | `self, doctype, column` | `` | Return column type from database. |
| `has_index` | `self, table_name, index_name` | `` |  |
| `get_column_index` | `self, table_name, fieldname, unique` | `` | Check if column exists for a specific fields in specified order. |
| `add_index` | `self, doctype, fields, index_name` | `` | Creates an index with given fields if not already created. |
| `add_unique` | `self, doctype, fields, constraint_name` | `` | Creates unique constraint on fields. |
| `updatedb` | `self, doctype, meta` | `` | Syncs a `DocType` to the table. |
| `get_database_list` | `self` | `` |  |
| `get_tables` | `self, cached` | `` | Return list of tables. |
| `get_row_size` | `self, doctype` | `` | Get estimated max row size of any table in bytes. |
| `execute_query` | `self, query, values` | `` |  |
| `sql` | `self` | `` |  |
| `sql_ddl` | `self, query` | `` | Execute DDL query. |
| `begin` | `self` | `` |  |
| `commit` | `self` | `` | Commit current transaction. Calls SQL `COMMIT`. |
| `rollback` | `self` | `` | `ROLLBACK` current transaction. Optionally rollback to a known save_point. |
| `get_db_table_columns` | `self, table` | `` | Return list of column names from given table. |
| `estimate_count` | `self, doctype` | `` | Get estimated count of total rows in a table. |
| `truncate` | `self, doctype` | `` | Truncate a table. |
| `check_implicit_commit` | `self, query, query_type` | `` |  |





## Functions

### `modify_query`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```
Modifies query according to the requirements of SQLite
```
### `replace_locate_with_instr`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```

```
### `regexp`
**Arguments:** `expr, item`
**Decorators:** ``

**Docstring:**
```
Define regexp implementation for SQLite manually

Although it works in the CLI - doesn't work through python
```

