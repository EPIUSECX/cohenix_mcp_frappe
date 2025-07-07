# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/api/queries.py`

## Classes

No classes found in this file.


## Functions

### `get_queries`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_query`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_chart`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `pivot`
**Arguments:** `data, indexes, columns, values`
**Decorators:** ``

**Docstring:**
```

```
### `flatten_column_keys`
**Arguments:** `pivoted_records`
**Decorators:** ``

**Docstring:**
```
- Move the values to the bottom level
- Flatten the column names

Input:
df = [{ ("Date", "", ""): "2018-01-01", ("Region", "", ""): "A", ("Price", "OK", "No"): 100, ...}]

Output:
df = [{ "Date": "2018-01-01", "Region": "A", "OK___No__Price": 100, ...}]
```

