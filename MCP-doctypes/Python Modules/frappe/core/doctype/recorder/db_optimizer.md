# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/recorder/db_optimizer.py`

## Classes

### `DBColumn`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `from_frappe_ouput` | `cls, data` | `classmethod` | Parse DBColumn from output of describe-database-table command in Frappe |


### `DBIndex`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__eq__` | `self, other` | `` |  |
| `__repr__` | `self` | `` |  |
| `from_frappe_ouput` | `cls, data, table` | `classmethod` | Parse DBIndex from output of describe-database-table command in Frappe |


### `ColumnStat`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__post_init__` | `self` | `` |  |
| `from_frappe_ouput` | `cls, data` | `classmethod` |  |


### `DBTable`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__post_init__` | `self` | `` |  |
| `update_cardinality` | `self, column_stats` | `` | Estimate cardinality using mysql.column_stat |
| `from_frappe_ouput` | `cls, data` | `classmethod` | Parse DBTable from output of describe-database-table command in Frappe |
| `has_column` | `self, column` | `` |  |


### `DBOptimizer`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__post_init__` | `self` | `` |  |
| `tables_examined` | `self` | `` |  |
| `update_table_data` | `self, table` | `` |  |
| `_convert_to_db_index` | `self, column` | `` |  |
| `_remove_existing_indexes` | `self, potential_indexes` | `` | Given list of potential index candidates remove the ones that already exist.

This also removes multi-column indexes for parts that are applicable to query.
Example: If multi-col index A+B+C exists and query utilizes A+B then
A+B are removed from potential indexes. |
| `potential_indexes` | `self` | `` | Get all columns that can potentially be indexed to speed up this query. |
| `suggest_index` | `self` | `` | Suggest best possible column to index given query and table stats. |
| `index_score` | `self, index` | `` | Score an index from 0 to 1 based on usefulness.

A score of 0.5 indicates on average this index will read 50% of the table. (e.g. checkboxes) |





## Functions

No top-level functions found in this file.
