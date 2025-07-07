# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/utils.py`

## Classes

### `ResultColumn`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `from_args` | `label, type, options` | `staticmethod` |  |
| `from_dict` | `cls, data` | `classmethod` |  |
| `from_dicts` | `cls, data` | `classmethod` |  |


### `DoctypeBase`
**Inherits:** `BaseDocument`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_name` | `cls` | `classmethod` |  |
| `exists` | `cls` | `classmethod` |  |
| `get_doc` | `cls` | `classmethod` |  |
| `get_cached_doc` | `cls` | `classmethod` |  |
| `new_doc` | `cls` | `classmethod` |  |
| `get_or_create_doc` | `cls` | `classmethod` |  |
| `get_value` | `cls` | `classmethod` |  |
| `delete_doc` | `cls, name` | `classmethod` |  |


### `InsightsChart`
**Inherits:** `DoctypeBase`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InsightsTable`
**Inherits:** `DoctypeBase`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InsightsQuery`
**Inherits:** `DoctypeBase`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InsightsDataSource`
**Inherits:** `DoctypeBase`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InsightsQueryResult`
**Inherits:** `DoctypeBase`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InsightsDataSourcev3`
**Inherits:** `DoctypeBase`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InsightsTablev3`
**Inherits:** `DoctypeBase`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DocShare`
**Inherits:** `DoctypeBase`


**Docstring:**
```

```

**Methods:**
No methods found.

### `File`
**Inherits:** `DoctypeBase`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InsightsSettings`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get` | `cls, key` | `classmethod` |  |


### `InsightsPageRenderer`
**Inherits:** `TemplatePage`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `can_render` | `self` | `` |  |
| `render` | `self` | `` |  |
| `set_headers` | `self` | `` |  |





## Functions

### `deep_convert_dict_to_dict`
**Arguments:** `d`
**Decorators:** ``

**Docstring:**
```

```
### `create_execution_log`
**Arguments:** `sql, time_taken, query_name`
**Decorators:** ``

**Docstring:**
```

```
### `detect_encoding`
**Arguments:** `file_path`
**Decorators:** ``

**Docstring:**
```

```
### `anonymize_data`
**Arguments:** `df, columns_to_anonymize, prefix_by_column`
**Decorators:** ``

**Docstring:**
```
Anonymizes the data in the specified columns of a DataFrame.

Args:
    df (pandas.DataFrame): The DataFrame containing the data to be anonymized.
    columns_to_anonymize (list): A list of column names to be anonymized.
    prefix_by_column (dict, optional): A dictionary mapping column names to prefixes.
        If provided, the anonymized values will be prefixed with the corresponding value.
        Defaults to None.

Returns:
    pandas.DataFrame: The DataFrame with the anonymized data.
```
### `xls_to_df`
**Arguments:** `file_path`
**Decorators:** ``

**Docstring:**
```

```

