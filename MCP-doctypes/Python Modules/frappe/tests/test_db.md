# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_db.py`

## Classes

### `TestDB`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_datetime_format` | `self` | `` |  |
| `test_get_column_type` | `self` | `` |  |
| `test_get_database_size` | `self` | `` |  |
| `test_db_statement_execution_timeout` | `self` | `` |  |
| `test_db_timeout_computation` | `self` | `` |  |
| `test_get_value` | `self` | `` |  |
| `test_escape` | `self` | `` |  |
| `test_get_single_value` | `self` | `` |  |
| `test_get_single_value_destructuring` | `self` | `` |  |
| `test_singles_get_values_variant` | `self` | `` |  |
| `test_log_touched_tables` | `self` | `` |  |
| `test_db_keywords_as_fields` | `self` | `` | Tests if DB keywords work as docfield names. If they're wrapped with grave accents. |
| `test_savepoints` | `self` | `` |  |
| `test_savepoints_wrapper` | `self` | `` |  |
| `test_transaction_writes_error` | `self` | `` |  |
| `test_transaction_write_counting` | `self` | `` |  |
| `test_transactions_disabled_during_writes` | `self` | `` |  |
| `test_pk_collision_ignoring` | `self` | `` |  |
| `test_read_only_errors` | `self` | `` |  |
| `test_exists` | `self` | `` |  |
| `test_estimated_count` | `self` | `` |  |
| `test_datetime_serialization` | `self` | `` |  |
| `test_bulk_insert` | `self` | `` |  |
| `test_bulk_update` | `self` | `` |  |
| `test_count` | `self` | `` |  |
| `test_get_list_return_value_data_type` | `self` | `` |  |
| `test_modify_query` | `self` | `` |  |
| `test_modify_values` | `self` | `` |  |
| `test_callbacks` | `self` | `` |  |
| `test_db_explain` | `self` | `` |  |


### `TestDDLCommandsMaria`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_rename` | `self` | `` |  |
| `test_describe` | `self` | `` |  |
| `test_change_type` | `self` | `` |  |
| `test_add_index` | `self` | `` |  |


### `TestDBSetValue`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `test_update_single_doctype_field` | `self` | `` |  |
| `test_none_no_set_value` | `self` | `` |  |
| `test_update_single_row_single_column` | `self` | `` |  |
| `test_set_single_value_with_set_value` | `self, single_set` | `` |  |
| `test_update_single_row_multiple_columns` | `self` | `` |  |
| `test_update_multiple_rows_single_column` | `self` | `` |  |
| `test_update_multiple_rows_multiple_columns` | `self` | `` |  |
| `test_update_modified_options` | `self` | `` |  |
| `test_set_value` | `self` | `` |  |
| `test_cleared_cache` | `self` | `` |  |
| `tearDownClass` | `cls` | `classmethod` |  |


### `TestDDLCommandsPost`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_rename` | `self` | `` |  |
| `test_describe` | `self` | `` |  |
| `test_change_type` | `self` | `` |  |
| `test_add_index` | `self` | `` |  |
| `test_sequence_table_creation` | `self` | `` |  |
| `test_is` | `self` | `` |  |


### `TestTransactionManagement`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_create_proper_transactions` | `self` | `` |  |


### `TestReplicaConnections`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_switching_to_replica` | `self` | `` |  |


### `TestConcurrency`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_skip_locking` | `self` | `` |  |
| `test_no_wait` | `self` | `` |  |
| `test_delete_race_condition` | `self` | `` |  |


### `TestSqlIterator`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_db_sql_iterator` | `self` | `` |  |
| `test_unbuffered_cursor` | `self` | `` |  |


### `ExtIntegrationTestCase`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `assertSqlException` | `self` | `` |  |


### `TestPostgresSchemaQueryIndependence`
**Inherits:** `ExtIntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self, rollback` | `` |  |
| `tearDown` | `self` | `` |  |
| `cleanup` | `self` | `` |  |
| `test_get_tables` | `self` | `` |  |
| `test_db_table_columns` | `self` | `` |  |
| `test_describe` | `self` | `` |  |
| `test_has_index` | `self` | `` |  |
| `test_add_index` | `self` | `` |  |
| `test_add_unique` | `self` | `` |  |
| `test_get_table_columns_description` | `self` | `` |  |
| `test_get_column_type` | `self` | `` |  |
| `test_search_path` | `self` | `` |  |


### `TestDbConnectWithEnvCredentials`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `tearDown` | `self` | `` |  |
| `test_connect_fails_with_wrong_credentials_by_env` | `self` | `` |  |





## Functions

### `bad_hook`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `bad_nested_hook`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```

