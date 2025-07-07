# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/query_builder/builder.py`

## Classes

### `Base`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `functions` | `name` | `staticmethod` |  |
| `DocType` | `table_name` | `staticmethod` |  |
| `into` | `cls, table` | `classmethod` |  |
| `update` | `cls, table` | `classmethod` |  |


### `MariaDB`
**Inherits:** `Base, MySQLQuery`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `_builder` | `cls` | `classmethod` |  |
| `from_` | `cls, table` | `classmethod` |  |


### `Postgres`
**Inherits:** `Base, PostgreSQLQuery`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `_builder` | `cls` | `classmethod` |  |
| `Field` | `cls, field_name` | `classmethod` |  |
| `from_` | `cls, table` | `classmethod` |  |


### `SQLite`
**Inherits:** `Base, SQLLiteQuery`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `_builder` | `cls` | `classmethod` |  |
| `from_` | `cls, table` | `classmethod` |  |





## Functions

No top-level functions found in this file.
