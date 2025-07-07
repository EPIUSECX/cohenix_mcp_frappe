# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source/sources/base_database.py`

## Classes

### `DatabaseConnectionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DatabaseCredentialsError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DatabaseParallelConnectionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Database`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_connection` | `self` | `` |  |
| `connect` | `self` | `` |  |
| `build_query` | `self, query` | `` |  |
| `run_query` | `self, query` | `` |  |
| `execute_query` | `self` | `` |  |
| `sync_tables` | `self` | `` |  |
| `get_table_columns` | `self` | `` |  |
| `get_column_options` | `self` | `` |  |
| `get_table_preview` | `self` | `` |  |
| `table_exists` | `self, table` | `` | While importing a csv file, check if the table exists in the database |
| `import_table` | `self, import_doc` | `` | Imports the table into the database |


### `BaseDatabase`
**Inherits:** `Database`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `test_connection` | `self, log_errors` | `` |  |
| `connect` | `self` | `` |  |
| `handle_db_connection_error` | `self, e` | `` |  |
| `build_query` | `self, query` | `` | Used to update the sql in insights query |
| `run_query` | `self, query` | `` |  |
| `execute_query` | `self, sql, pluck, return_columns, cached, query_name, log_errors` | `` |  |
| `compile_query` | `self, query` | `` |  |
| `process_subquery` | `self, sql` | `` |  |
| `escape_special_characters` | `self, sql` | `` |  |
| `replace_template_tags` | `self, sql` | `` |  |
| `set_row_limit` | `self, sql` | `` |  |
| `validate_native_sql` | `self, query` | `` |  |





## Functions

No top-level functions found in this file.
