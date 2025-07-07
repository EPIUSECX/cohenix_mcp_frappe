# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/query_builder/functions.py`

## Classes

### `Concat_ws`
**Inherits:** `Function`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |


### `Locate`
**Inherits:** `Function`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |


### `Ifnull`
**Inherits:** `IfNull`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, condition, term` | `` |  |


### `Timestamp`
**Inherits:** `Function`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, term, time, alias` | `` |  |


### `Round`
**Inherits:** `Function`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, term, decimal` | `` |  |


### `Truncate`
**Inherits:** `Function`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, term, decimal` | `` |  |


### `_PostgresTimestamp`
**Inherits:** `ArithmeticExpression`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, datepart, timepart, alias` | `` | Postgres would need both datepart and timepart to be a string for concatenation |


### `_PostgresUnixTimestamp`
**Inherits:** `Extract`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, field, alias` | `` |  |


### `Cast_`
**Inherits:** `Function`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, value, as_type, alias` | `` |  |
| `get_special_params_sql` | `self` | `` |  |


### `SqlFunctions`
**Inherits:** `Enum`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `_aggregate`
**Arguments:** `function, dt, fieldname, filters`
**Decorators:** ``

**Docstring:**
```

```
### `_max`
**Arguments:** `dt, fieldname, filters`
**Decorators:** ``

**Docstring:**
```

```
### `_min`
**Arguments:** `dt, fieldname, filters`
**Decorators:** ``

**Docstring:**
```

```
### `_avg`
**Arguments:** `dt, fieldname, filters`
**Decorators:** ``

**Docstring:**
```

```
### `_sum`
**Arguments:** `dt, fieldname, filters`
**Decorators:** ``

**Docstring:**
```

```

