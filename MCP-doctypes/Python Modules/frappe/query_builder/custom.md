# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/query_builder/custom.py`

## Classes

### `GROUP_CONCAT`
**Inherits:** `DistinctOptionFunction`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, column, alias` | `` | [ Implements the group concat function read more about it at https://www.geeksforgeeks.org/mysql-group_concat-function ]
Args:
        column (str): [ name of the column you want to concat]
        alias (Optional[str], optional): [ is this an alias? ]. Defaults to None. |


### `STRING_AGG`
**Inherits:** `DistinctOptionFunction`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, column, separator, alias` | `` | [ Implements the group concat function read more about it at https://docs.microsoft.com/en-us/sql/t-sql/functions/string-agg-transact-sql?view=sql-server-ver15 ]

Args:
        column (str): [ name of the column you want to concat ]
        separator (str, optional): [separator to be used]. Defaults to ",".
        alias (Optional[str], optional): [description]. Defaults to None. |


### `MATCH`
**Inherits:** `DistinctOptionFunction`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, column` | `` | [ Implementation of Match Against read more about it https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html#function_match ]

Args:
        column (str):[ column to search in ] |
| `get_function_sql` | `self` | `` |  |
| `Against` | `self, text` | `builder` | [ Text that has to be searched against ]

Args:
        text (str): [ the text string that we match it against ] |


### `TO_TSVECTOR`
**Inherits:** `DistinctOptionFunction`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, column` | `` | [ Implementation of TO_TSVECTOR read more about it https://www.postgresql.org/docs/9.1/textsearch-controls.html]

Args:
        column (str): [ column to search in ] |
| `get_function_sql` | `self` | `` |  |
| `Against` | `self, text` | `builder` | [ Text that has to be searched against ]

Args:
        text (str): [ the text string that we match it against ] |


### `ConstantColumn`
**Inherits:** `Term`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, value` | `` | Return a pseudo column with the given constant `value` in all the rows. |
| `get_sql` | `self, quote_char` | `` |  |





## Functions

No top-level functions found in this file.
