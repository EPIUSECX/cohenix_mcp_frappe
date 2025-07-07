# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/database/utils.py`

## Classes

### `LazyString`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `_setup` | `self` | `` |  |
| `value` | `self` | `cached_property` |  |
| `__str__` | `self` | `` |  |
| `__repr__` | `self` | `` |  |


### `LazyDecode`
**Inherits:** `LazyString`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, value` | `` |  |
| `_setup` | `self` | `` |  |


### `LazyMogrify`
**Inherits:** `LazyString`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, query, values` | `` |  |
| `_setup` | `self` | `` |  |





## Functions

### `convert_to_value`
**Arguments:** `o`
**Decorators:** ``

**Docstring:**
```

```
### `get_query_type`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```

```
### `is_query_type`
**Arguments:** `query, query_type`
**Decorators:** ``

**Docstring:**
```

```
### `is_pypika_function_object`
**Arguments:** `field`
**Decorators:** ``

**Docstring:**
```

```
### `get_doctype_name`
**Arguments:** `table_name`
**Decorators:** ``

**Docstring:**
```

```
### `dangerously_reconnect_on_connection_abort`
**Arguments:** `func`
**Decorators:** ``

**Docstring:**
```
Reconnect on connection failure.

As the name suggest, it's dangerous to use this function as it will NOT restore DB transaction
so make sure you're using it right.

Ideal use case: Some kinda logging or final steps in a background jobs. Anything more than that
will risk bugs from DB transactions.
```

