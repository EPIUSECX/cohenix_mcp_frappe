# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_table_v3/patches/force_sync_tables.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
`name` of Insights Table v3 is changed from `autoincrement` to `varchar(140)`
 This patch will delete all the tables and recreate them with the new name
 The new name will be a reproducible hash of the data_source and table name
```

