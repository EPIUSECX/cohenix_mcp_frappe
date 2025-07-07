# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/quality_management/doctype/quality_procedure/quality_procedure.py`

## Classes

### `QualityProcedure`
**Inherits:** `NestedSet`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_save` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `check_for_incorrect_child` | `self` | `` |  |
| `set_parent` | `self` | `` | Set `Parent Procedure` in `Child Procedures` |
| `remove_parent_from_old_child` | `self` | `` | Remove `Parent Procedure` from `Old Child Procedures` |
| `add_child_to_parent` | `self` | `` | Add `Child Procedure` to `Parent Procedure` |
| `remove_child_from_old_parent` | `self` | `` | Remove `Child Procedure` from `Old Parent Procedure` |





## Functions

### `get_children`
**Arguments:** `doctype, parent, parent_quality_procedure, is_root`
**Decorators:** ``

**Docstring:**
```

```
### `add_node`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

