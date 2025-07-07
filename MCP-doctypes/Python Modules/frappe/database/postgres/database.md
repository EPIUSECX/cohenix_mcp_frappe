# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/database/postgres/database.py`

## Classes

### `PostgresExceptionUtil`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `is_deadlocked` | `e` | `staticmethod` |  |
| `is_timedout` | `e` | `staticmethod` |  |
| `is_read_only_mode_error` | `e` | `staticmethod` |  |
| `is_syntax_error` | `e` | `staticmethod` |  |
| `is_table_missing` | `e` | `staticmethod` |  |
| `is_missing_table` | `e` | `staticmethod` |  |
| `is_missing_column` | `e` | `staticmethod` |  |
| `is_access_denied` | `e` | `staticmethod` |  |
| `cant_drop_field_or_key` | `e` | `staticmethod` |  |
| `is_duplicate_entry` | `e` | `staticmethod` |  |
| `is_primary_key_violation` | `e` | `staticmethod` |  |
| `is_unique_key_violation` | `e` | `staticmethod` |  |
| `is_duplicate_fieldname` | `e` | `staticmethod` |  |
| `is_statement_timeout` | `e` | `staticmethod` |  |
| `is_data_too_long` | `e` | `staticmethod` |  |
| `is_db_table_size_limit` | `e` | `staticmethod` |  |
| `is_interface_error` | `e` | `staticmethod` |  |


### `PostgresDatabase`
**Inherits:** `PostgresExceptionUtil, Database`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setup_type_map` | `self` | `` |  |
| `last_query` | `self` | `property` |  |
| `db_schema` | `self` | `property` |  |
| `connect` | `self` | `` |  |
| `get_connection` | `self` | `` |  |
| `set_execution_timeout` | `self, seconds` | `` |  |
| `escape` | `self, s, percent` | `` | Escape quotes and percent in given string. |
| `get_database_size` | `self` | `` | Return database size in MB |
| `_transform_result` | `self, result` | `` |  |
| `sql` | `self, query, values` | `` |  |
| `lazy_mogrify` | `self` | `` |  |
| `get_tables` | `self, cached` | `` |  |
| `get_db_table_columns` | `self, table` | `` | Returns list of column names from given table. |
| `format_date` | `self, date` | `` |  |
| `is_type_number` | `code` | `staticmethod` |  |
| `is_type_datetime` | `code` | `staticmethod` |  |
| `rename_table` | `self, old_name, new_name` | `` |  |
| `describe` | `self, doctype` | `` |  |
| `change_column_type` | `self, doctype, column, type, nullable, use_cast` | `` |  |
| `rename_column` | `self, doctype, old_column_name, new_column_name` | `` |  |
| `create_auth_table` | `self` | `` |  |
| `create_global_search_table` | `self` | `` |  |
| `create_user_settings_table` | `self` | `` |  |
| `updatedb` | `self, doctype, meta` | `` | Syncs a `DocType` to the table
* creates if required
* updates columns
* updates indices |
| `get_on_duplicate_update` | `key` | `staticmethod` |  |
| `check_implicit_commit` | `self, query, query_type` | `` |  |
| `has_index` | `self, table_name, index_name` | `` |  |
| `add_index` | `self, doctype, fields, index_name` | `` | Creates an index with given fields if not already created.
Index name will be `fieldname1_fieldname2_index` |
| `add_unique` | `self, doctype, fields, constraint_name` | `` |  |
| `get_table_columns_description` | `self, table_name` | `` | Return list of columns with description. |
| `get_column_type` | `self, doctype, column` | `` | Return column type from database. |
| `get_database_list` | `self` | `` |  |
| `estimate_count` | `self, doctype` | `` | Get estimated count of total rows in a table. |





## Functions

### `modify_query`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```
"Modifies query according to the requirements of postgres
```
### `modify_values`
**Arguments:** `values`
**Decorators:** ``

**Docstring:**
```

```
### `replace_locate_with_strpos`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```

```

