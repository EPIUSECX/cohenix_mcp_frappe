# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source_v3/insights_data_source_v3.py`

## Classes

### `DataSourceConnectionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InsightsDataSourceDocument`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `before_insert` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `has_credentials_changed` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_database_name` | `self` | `` |  |
| `validate_remote_db_fields` | `self` | `` |  |
| `validate_bigquery_fields` | `self` | `` |  |


### `InsightsDataSourcev3`
**Inherits:** `InsightsDataSourceDocument, Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `_get_ibis_backend` | `self` | `` |  |
| `_get_db_connection` | `self` | `` |  |
| `get_table_list` | `self` | `` |  |
| `test_connection` | `self, raise_exception` | `` |  |
| `update_table_list` | `self, force` | `` |  |
| `update_table_links` | `self, force` | `` |  |
| `get_ibis_table` | `self, table_name` | `` |  |





## Functions

### `before_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `after_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `db_connections`
**Arguments:** ``
**Decorators:** `contextmanager`

**Docstring:**
```

```

