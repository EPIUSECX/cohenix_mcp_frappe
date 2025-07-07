# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_query/utils.py`

## Classes

### `QueryStatus`
**Inherits:** `Enum`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Column`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `__repr__` | `self` | `` |  |
| `is_valid` | `self` | `` |  |
| `from_dicts` | `dicts` | `staticmethod` |  |
| `is_aggregate` | `self` | `` |  |
| `is_expression` | `self` | `` |  |
| `is_formatted` | `self` | `` |  |
| `has_granularity` | `self` | `` |  |
| `is_date_type` | `self` | `` |  |
| `is_numeric_type` | `self` | `` |  |
| `is_string_type` | `self` | `` |  |
| `is_measure` | `self` | `` |  |
| `is_dimension` | `self` | `` |  |


### `LabelValue`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `is_valid` | `self` | `` |  |


### `Table`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `is_valid` | `self` | `` |  |


### `JoinColumn`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `is_valid` | `self` | `` |  |


### `Join`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `is_valid` | `self` | `` |  |
| `from_dicts` | `dicts` | `staticmethod` |  |


### `Filter`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `is_valid` | `self` | `` |  |
| `from_dicts` | `cls, dicts` | `classmethod` |  |


### `Query`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `is_valid` | `self` | `` |  |
| `add_filter` | `self, column, operator, value` | `` |  |
| `get_tables` | `self` | `` |  |
| `get_columns` | `self` | `` |  |
| `_extract_columns` | `self` | `` | Extract columns from columns, measures, dimensions
A column has the following format: { table, column, type, label, alias, format } |


### `BaseNestedQueryImporter`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, data, doc, imported_queries` | `` |  |
| `import_query` | `self` | `` |  |
| `_import_subqueries` | `self` | `` |  |
| `_update_subquery_references` | `self` | `` |  |
| `_update_doc` | `self` | `` |  |





## Functions

### `update_sql`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```

```
### `format_query`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```

```
### `apply_pivot_transform`
**Arguments:** `results, options`
**Decorators:** ``

**Docstring:**
```

```
### `apply_unpivot_transform`
**Arguments:** `results, options`
**Decorators:** ``

**Docstring:**
```

```
### `apply_transpose_transform`
**Arguments:** `results, options`
**Decorators:** ``

**Docstring:**
```

```
### `apply_cumulative_sum`
**Arguments:** `columns, results`
**Decorators:** ``

**Docstring:**
```

```
### `infer_type`
**Arguments:** `value`
**Decorators:** ``

**Docstring:**
```

```
### `infer_type_from_list`
**Arguments:** `values`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns_with_inferred_types`
**Arguments:** `results`
**Decorators:** ``

**Docstring:**
```

```
### `export_query`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `import_query`
**Arguments:** `data_source, query`
**Decorators:** ``

**Docstring:**
```

```

