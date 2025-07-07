# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/recorder/recorder.py`

## Classes

### `Recorder`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `load_from_db` | `self` | `` |  |
| `get_list` | `filters, start, page_length, order_by` | `staticmethod` |  |
| `get_count` | `filters` | `staticmethod` |  |
| `get_filtered_requests` | `filters` | `staticmethod` |  |
| `get_stats` | `args` | `staticmethod` |  |
| `delete` | `self` | `staticmethod` |  |
| `db_insert` | `self` | `` |  |
| `db_update` | `self` | `` |  |





## Functions

### `serialize_request`
**Arguments:** `request`
**Decorators:** ``

**Docstring:**
```

```
### `add_indexes`
**Arguments:** `indexes`
**Decorators:** ``

**Docstring:**
```

```
### `_add_index`
**Arguments:** `table, column`
**Decorators:** ``

**Docstring:**
```

```
### `optimize`
**Arguments:** `recorder_id`
**Decorators:** ``

**Docstring:**
```

```
### `_optimize`
**Arguments:** `recorder_id`
**Decorators:** ``

**Docstring:**
```

```
### `_optimize_query`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```

```
### `_fetch_table_stats`
**Arguments:** `doctype, columns`
**Decorators:** ``

**Docstring:**
```

```
### `_get_column_cardinality`
**Arguments:** `table, column`
**Decorators:** `redis_cache`

**Docstring:**
```

```
### `get_doctype_name`
**Arguments:** `table_name`
**Decorators:** ``

**Docstring:**
```

```

