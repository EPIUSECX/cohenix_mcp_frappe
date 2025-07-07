# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source/sources/query_store.py`

## Classes

### `StoredQueryTableFactory`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `sync_tables` | `self, connection, tables, force` | `` |  |
| `make_table` | `self, query` | `` |  |
| `get_stored_queries` | `self` | `` |  |
| `make_columns` | `self, columns` | `` |  |


### `QueryStore`
**Inherits:** `SQLiteDB`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `sync_tables` | `self, tables, force` | `` |  |
| `get_table_columns` | `self, table` | `` |  |
| `store_query` | `self, query, results` | `` |  |





## Functions

### `sync_query_store`
**Arguments:** `tables, force`
**Decorators:** ``

**Docstring:**
```

```
### `store_query`
**Arguments:** `query, results`
**Decorators:** ``

**Docstring:**
```

```
### `remove_stored_query`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```

```

