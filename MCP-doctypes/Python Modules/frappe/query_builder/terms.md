# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/query_builder/terms.py`

## Classes

### `NamedParameterWrapper`


**Docstring:**
```
Utility class to hold parameter values and keys
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `get_sql` | `self, param_value` | `` | Return SQL for a parameter, while adding the real value in a dict.

Args:
        param_value (Any): Value of the parameter

Return:
        str: parameter used in the SQL query |
| `get_parameters` | `self` | `` | Get dict with parameters and values. |


### `ParameterizedValueWrapper`
**Inherits:** `ValueWrapper`


**Docstring:**
```
Class to monkey patch ValueWrapper

Adds functionality to parameterize queries when a `param wrapper` is passed in get_sql()
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_sql` | `self, quote_char, secondary_quote_char, param_wrapper` | `` |  |


### `SQLiteParameterizedValueWrapper`
**Inherits:** `ParameterizedValueWrapper, SQLLiteValueWrapper`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ParameterizedFunction`
**Inherits:** `Function`


**Docstring:**
```
Class to monkey patch pypika.terms.Functions

Only to pass `param_wrapper` in `get_function_sql`.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_sql` | `self` | `` |  |


### `SubQuery`
**Inherits:** `Criterion`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, subq, alias` | `` |  |
| `get_sql` | `self` | `` |  |





## Functions

No top-level functions found in this file.
