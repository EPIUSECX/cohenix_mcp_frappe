# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source_v3/data_warehouse.py`

## Classes

### `Warehouse`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `db` | `self` | `property` |  |
| `get_table` | `self, data_source, table_name` | `` |  |


### `WarehouseTable`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data_source, table_name` | `` |  |
| `validate` | `self` | `` |  |
| `get_ibis_table` | `self, import_if_not_exists` | `` |  |
| `get_remote_table` | `self` | `` |  |
| `enqueue_import` | `self` | `` |  |


### `WarehouseTableImporter`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, table` | `` |  |
| `import_in_progress` | `self` | `` |  |
| `enqueue_import` | `self` | `` |  |
| `start_import` | `self` | `` |  |
| `prepare_log` | `self` | `` |  |
| `prepare_settings` | `self` | `` |  |
| `prepare_remote_table` | `self` | `` |  |
| `start_batch_import` | `self` | `` |  |
| `calculate_batch_size` | `self` | `` |  |
| `process_batches` | `self, batch_size` | `` |  |
| `create_parquet_file` | `self, batch, batch_number` | `` |  |
| `get_batch_metadata` | `self, path` | `` |  |
| `merge_batches` | `self` | `` |  |
| `update_log` | `self` | `` |  |
| `update_insights_table` | `self` | `` |  |
| `_cleanup` | `self` | `` |  |





## Functions

### `_start_table_import`
**Arguments:** `data_source, table_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_warehouse_folder_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_warehouse_table_name`
**Arguments:** `data_source, table_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_parquet_filepath`
**Arguments:** `data_source, table_name`
**Decorators:** ``

**Docstring:**
```

```

