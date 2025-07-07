# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_query_builder.py`

## Classes

### `TestCustomFunctionsMariaDB`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_concat` | `self` | `` |  |
| `test_match` | `self` | `` |  |
| `test_constant_column` | `self` | `` |  |
| `test_timestamp` | `self` | `` |  |
| `test_unix_ts_mariadb` | `self` | `` |  |
| `test_time` | `self` | `` |  |
| `test_cast` | `self` | `` |  |
| `test_round` | `self` | `` |  |
| `test_truncate` | `self` | `` |  |


### `TestCustomFunctionsPostgres`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_concat` | `self` | `` |  |
| `test_match` | `self` | `` |  |
| `test_constant_column` | `self` | `` |  |
| `test_timestamp` | `self` | `` |  |
| `test_unix_ts_postgres` | `self` | `` |  |
| `test_time` | `self` | `` |  |
| `test_cast` | `self` | `` |  |
| `test_round` | `self` | `` |  |
| `test_truncate` | `self` | `` |  |


### `TestBuilderBase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_adding_tabs` | `self` | `` |  |
| `test_run_patcher` | `self` | `` |  |
| `test_agg_funcs` | `self` | `` |  |


### `TestParameterization`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_where_conditions` | `self` | `` |  |
| `test_set_conditions` | `self` | `` |  |
| `test_where_conditions_functions` | `self` | `` |  |
| `test_case` | `self` | `` |  |
| `test_case_in_update` | `self` | `` |  |
| `test_named_parameter_wrapper` | `self` | `` |  |


### `TestBuilderMaria`
**Inherits:** `IntegrationTestCase, TestBuilderBase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_adding_tabs_in_from` | `self` | `` |  |
| `test_get_qb_type` | `self` | `` |  |


### `TestBuilderPostgres`
**Inherits:** `IntegrationTestCase, TestBuilderBase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_adding_tabs_in_from` | `self` | `` |  |
| `test_replace_tables` | `self` | `` |  |
| `test_replace_fields_post` | `self` | `` |  |
| `test_get_qb_type` | `self` | `` |  |


### `TestMisc`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_custom_func` | `self` | `` |  |
| `test_function_with_schema` | `self` | `` |  |
| `test_util_table` | `self` | `` |  |
| `test_union` | `self` | `` |  |





## Functions

### `run_only_if`
**Arguments:** `dbtype`
**Decorators:** ``

**Docstring:**
```

```

