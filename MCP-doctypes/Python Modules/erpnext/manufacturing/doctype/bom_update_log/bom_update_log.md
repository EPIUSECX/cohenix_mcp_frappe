# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/bom_update_log/bom_update_log.py`

## Classes

### `BOMMissingError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `BOMUpdateLog`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `clear_old_logs` | `days` | `staticmethod` |  |
| `validate` | `self` | `` |  |
| `validate_boms_are_specified` | `self` | `` |  |
| `validate_same_bom` | `self` | `` |  |
| `validate_bom_items` | `self` | `` |  |
| `validate_bom_cost_update_in_progress` | `self` | `` | If another Cost Updation Log is still in progress, dont make new ones. |
| `on_submit` | `self` | `` |  |





## Functions

### `run_replace_bom_job`
**Arguments:** `doc, boms`
**Decorators:** ``

**Docstring:**
```

```
### `process_boms_cost_level_wise`
**Arguments:** `update_doc, parent_boms`
**Decorators:** ``

**Docstring:**
```
Queue jobs at the start of new BOM Level in 'Update Cost' Jobs.
```
### `queue_bom_cost_jobs`
**Arguments:** `current_boms_list, update_doc, current_level`
**Decorators:** ``

**Docstring:**
```
Queue batches of 20k BOMs of the same level to process parallelly
```
### `resume_bom_cost_update_jobs`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
1. Checks for In Progress BOM Update Log.
2. Checks if this job has completed the _current level_.
3. If current level is complete, get parent BOMs and start next level.
4. If no parents, mark as Complete.
5. If current level is WIP, skip the Log.

Called every 5 minutes via Cron job.
```
### `get_processed_current_boms`
**Arguments:** `log, bom_batches`
**Decorators:** ``

**Docstring:**
```
Aggregate all BOMs from BOM Update Batch rows into 'processed_boms' field
and into current boms list.
```

