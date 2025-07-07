# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/bom_update_log/bom_updation_utils.py`

## Classes

No classes found in this file.


## Functions

### `replace_bom`
**Arguments:** `boms, log_name`
**Decorators:** ``

**Docstring:**
```
Replace current BOM with new BOM in parent BOMs.
```
### `update_cost_in_level`
**Arguments:** `doc, bom_list, batch_name`
**Decorators:** ``

**Docstring:**
```
Updates Cost for BOMs within a given level. Runs via background jobs.
```
### `get_ancestor_boms`
**Arguments:** `new_bom, bom_list`
**Decorators:** ``

**Docstring:**
```
Recursively get all ancestors of BOM.
```
### `update_new_bom_in_bom_items`
**Arguments:** `unit_cost, current_bom, new_bom`
**Decorators:** ``

**Docstring:**
```

```
### `get_bom_unit_cost`
**Arguments:** `bom_name`
**Decorators:** ``

**Docstring:**
```

```
### `update_cost_in_boms`
**Arguments:** `bom_list`
**Decorators:** ``

**Docstring:**
```
Updates cost in given BOMs. Returns current and total updated BOMs.
```
### `get_next_higher_level_boms`
**Arguments:** `child_boms, processed_boms`
**Decorators:** ``

**Docstring:**
```
Generate immediate higher level dependants with no unresolved dependencies (children).
```
### `get_leaf_boms`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get BOMs that have no dependencies.
```
### `_generate_dependence_map`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Generate maps such as: { BOM-1: [Dependant-BOM-1, Dependant-BOM-2, ..] }.
Here BOM-1 is the leaf/lower level node/dependency.
The list contains one level higher nodes/dependants that depend on BOM-1.

Generate and return the reverse as well.
```
### `set_values_in_log`
**Arguments:** `log_name, values, commit`
**Decorators:** ``

**Docstring:**
```
Update BOM Update Log record.
```
### `handle_exception`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Rolls back and fails BOM Update Log.
```

