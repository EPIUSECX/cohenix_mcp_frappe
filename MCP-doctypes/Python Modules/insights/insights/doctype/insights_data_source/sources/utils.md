# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source/sources/utils.py`

## Classes

### `Timer`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `__enter__` | `self` | `` |  |
| `__exit__` | `self` | `` |  |





## Functions

### `get_sqlalchemy_engine`
**Arguments:** `connect_args`
**Decorators:** ``

**Docstring:**
```

```
### `create_insights_table`
**Arguments:** `table, force`
**Decorators:** ``

**Docstring:**
```

```
### `parse_sql_tables`
**Arguments:** `sql`
**Decorators:** ``

**Docstring:**
```

```
### `get_stored_query_sql`
**Arguments:** `sql, data_source, dialect`
**Decorators:** ``

**Docstring:**
```
Takes a native sql query and returns a map of table name to the query along with the subqueries

For example, if the query is
SELECT * FROM `QRY-001`
LEFT JOIN `QRY-002` ON `QRY-001`.`name` = `QRY-002`.`name`
LEFT JOIN `QRY-003` ON `QRY-001`.`name` = `QRY-003`.`name`

and QRY-001 = SELECT name FROM `QRY-004`
and QRY-002 = SELECT name FROM `Customer`
and QRY-003 = SELECT name FROM `Supplier`
and QRY-004 = SELECT name FROM `Item`

Then the returned map will be
{
    'QRY-001': 'WITH `QRY-004` AS (SELECT name FROM `Item`) SELECT name FROM `QRY-004`',
    'QRY-002': 'SELECT name FROM `Customer`',
    'QRY-003': 'SELECT name FROM `Supplier)'
}

If any one of the table belongs to any other data source
then stop and return None
```
### `make_wrap_table_fn`
**Arguments:** `dialect, data_source`
**Decorators:** ``

**Docstring:**
```

```
### `process_cte`
**Arguments:** `main_query, data_source, dialect`
**Decorators:** ``

**Docstring:**
```
Replaces stored queries in the main query with the actual query using CTE
```
### `strip_quotes`
**Arguments:** `table`
**Decorators:** ``

**Docstring:**
```

```
### `add_limit_to_sql`
**Arguments:** `sql, limit`
**Decorators:** ``

**Docstring:**
```

```
### `replace_query_tables_with_cte`
**Arguments:** `sql, data_source, dialect`
**Decorators:** ``

**Docstring:**
```

```
### `compile_query`
**Arguments:** `query, dialect`
**Decorators:** ``

**Docstring:**
```

```
### `execute_and_log`
**Arguments:** `conn, sql, data_source, query_name`
**Decorators:** ``

**Docstring:**
```

```
### `handle_query_execution_error`
**Arguments:** `e`
**Decorators:** ``

**Docstring:**
```

```
### `cache_results`
**Arguments:** `sql, data_source, results`
**Decorators:** ``

**Docstring:**
```

```
### `get_cached_results`
**Arguments:** `sql, data_source`
**Decorators:** ``

**Docstring:**
```

```
### `create_execution_log`
**Arguments:** `sql, data_source, time_taken, query_name`
**Decorators:** ``

**Docstring:**
```

```

