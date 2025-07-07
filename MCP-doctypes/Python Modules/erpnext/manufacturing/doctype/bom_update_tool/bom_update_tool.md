# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/bom_update_tool/bom_update_tool.py`

## Classes

### `BOMUpdateTool`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `enqueue_replace_bom`
**Arguments:** `boms, args`
**Decorators:** ``

**Docstring:**
```
Returns a BOM Update Log (that queues a job) for BOM Replacement.
```
### `enqueue_update_cost`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Returns a BOM Update Log (that queues a job) for BOM Cost Updation.
```
### `auto_update_latest_price_in_all_boms`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Called via hooks.py.
```
### `is_older_log`
**Arguments:** `log`
**Decorators:** ``

**Docstring:**
```

```
### `create_bom_update_log`
**Arguments:** `boms, update_type`
**Decorators:** ``

**Docstring:**
```
Creates a BOM Update Log that handles the background job.
```

