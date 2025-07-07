# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/goal/goal.py`

## Classes

### `Goal`
**Inherits:** `NestedSet`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `after_delete` | `self` | `` |  |
| `validate_parent_fields` | `self` | `` |  |
| `validate_progress` | `self` | `` |  |
| `set_status` | `self, status` | `` |  |
| `update_kra_in_child_goals` | `self, doc_before_save` | `` | Aligns children's KRA to parent goal's KRA if parent goal's KRA is changed |
| `update_parent_progress` | `self, old_parent` | `` |  |
| `update_goal_progress_in_appraisal` | `self` | `` |  |





## Functions

### `get_children`
**Arguments:** `doctype, parent, is_root`
**Decorators:** ``

**Docstring:**
```

```
### `_update_goal_completion_status`
**Arguments:** `goals`
**Decorators:** ``

**Docstring:**
```

```
### `update_progress`
**Arguments:** `progress, goal`
**Decorators:** ``

**Docstring:**
```

```
### `update_status`
**Arguments:** `status, goals`
**Decorators:** ``

**Docstring:**
```

```
### `add_tree_node`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

