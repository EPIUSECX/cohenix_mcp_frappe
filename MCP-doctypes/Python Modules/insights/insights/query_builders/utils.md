# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/query_builders/utils.py`

## Classes

### `AndOrReplacer`


**Docstring:**
```
AST Node Transformer to replace 'and' and 'or' with 'and_(...)' and 'or_(...)' respectively.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `visit_BoolOp` | `self, node` | `` |  |
| `_create_new_node` | `self, node` | `` | Create a new node with 'and_' or 'or_' function call. |
| `_create_call_node` | `self, fn_name, left, right` | `` | Helper method to create an ast.Call node. |





## Functions

### `replace_and_or_expressions`
**Arguments:** `source_code`
**Decorators:** ``

**Docstring:**
```
Replace 'and' with 'and_' and 'or' with 'or_' in the given source code.
```
### `replace_equals_with_double_equals`
**Arguments:** `code`
**Decorators:** ``

**Docstring:**
```

```
### `replace_column_names`
**Arguments:** `raw_expression`
**Decorators:** ``

**Docstring:**
```

```
### `process_raw_expression`
**Arguments:** `raw_expression`
**Decorators:** ``

**Docstring:**
```

```

