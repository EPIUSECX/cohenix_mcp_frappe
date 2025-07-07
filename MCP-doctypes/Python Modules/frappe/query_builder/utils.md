# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/query_builder/utils.py`

## Classes

### `PseudoColumnMapper`
**Inherits:** `PseudoColumn`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, name` | `` |  |
| `get_sql` | `self` | `` |  |


### `db_type_is`
**Inherits:** `Enum`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ImportMapper`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, func_map` | `` |  |
| `__call__` | `self` | `` |  |


### `BuilderIdentificationFailed`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |





## Functions

### `get_query_builder`
**Arguments:** `type_of_db`
**Decorators:** ``

**Docstring:**
```
Return the query builder object.

Args:
        type_of_db: string value of the db used
```
### `get_query`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_attr`
**Arguments:** `method_string`
**Decorators:** ``

**Docstring:**
```

```
### `DocType`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `Table`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `execute_query`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```

```
### `execute_child_queries`
**Arguments:** `queries, result`
**Decorators:** ``

**Docstring:**
```

```
### `prepare_query`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```

```
### `patch_query_execute`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Patch the Query Builder with helper execute method
This excludes the use of `frappe.db.sql` method while
executing the query object
```
### `patch_query_aggregation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Patch aggregation functions to frappe.qb
```
### `patch_get_query`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `patch_all`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

