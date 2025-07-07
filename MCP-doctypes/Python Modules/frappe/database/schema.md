# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/database/schema.py`

## Classes

### `InvalidColumnName`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DBTable`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, meta` | `` |  |
| `sync` | `self` | `` |  |
| `create` | `self` | `` |  |
| `get_column_definitions` | `self` | `` |  |
| `get_index_definitions` | `self` | `` |  |
| `get_columns_from_docfields` | `self` | `` | get columns from docfields and custom fields |
| `validate` | `self` | `` | Check if change in varchar length isn't truncating the columns |
| `is_new` | `self` | `` |  |
| `setup_table_columns` | `self` | `` |  |
| `alter` | `self` | `` |  |


### `DbColumn`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `get_definition` | `self, for_modification` | `` |  |
| `build_for_alter_table` | `self, current_def` | `` |  |
| `default_changed` | `self, current_def` | `` |  |
| `default_changed_for_decimal` | `self, current_def` | `` |  |
| `default_changed_for_time` | `self, cur_default, new_default` | `` |  |





## Functions

### `validate_column_name`
**Arguments:** `n`
**Decorators:** ``

**Docstring:**
```

```
### `validate_column_length`
**Arguments:** `fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `get_definition`
**Arguments:** `fieldtype, precision, length`
**Decorators:** ``

**Docstring:**
```

```
### `add_column`
**Arguments:** `doctype, column_name, fieldtype, precision, length, default, not_null`
**Decorators:** ``

**Docstring:**
```

```

