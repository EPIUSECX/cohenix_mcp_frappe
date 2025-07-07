# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/nestedset.py`

## Classes

### `NestedSetRecursionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NestedSetMultipleRootsError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NestedSetChildExistsError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NestedSetInvalidMergeError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NestedSet`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__setup__` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self, allow_root_deletion` | `` | Runs on deletion of a document/node

:param allow_root_deletion: used for allowing root document deletion (DEPRECATED) |
| `validate_if_child_exists` | `self` | `` |  |
| `before_rename` | `self, olddn, newdn, merge, group_fname` | `` |  |
| `after_rename` | `self, olddn, newdn, merge` | `` |  |
| `validate_one_root` | `self` | `` |  |
| `get_root_node_count` | `self` | `` |  |
| `validate_ledger` | `self, group_identifier` | `` |  |
| `get_ancestors` | `self` | `` |  |
| `get_parent` | `self` | `` | Return the parent Document. |
| `get_children` | `self` | `` | Return a generator that yields child Documents. |





## Functions

### `update_nsm`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_add_node`
**Arguments:** `doc, parent, parent_field`
**Decorators:** ``

**Docstring:**
```
insert a new node
```
### `update_move_node`
**Arguments:** `doc, parent_field`
**Decorators:** ``

**Docstring:**
```

```
### `rebuild_tree`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Call rebuild_node for all root nodes.
```
### `rebuild_node`
**Arguments:** `doctype, parent, left, parent_field`
**Decorators:** ``

**Docstring:**
```
reset lft, rgt and recursive call for all children
```
### `validate_loop`
**Arguments:** `doctype, name, lft, rgt`
**Decorators:** ``

**Docstring:**
```
check if item not an ancestor (loop)
```
### `remove_subtree`
**Arguments:** `doctype, name, throw`
**Decorators:** ``

**Docstring:**
```
Remove doc and all its children.

WARN: This does not run any controller hooks for deletion and deletes them with raw SQL query.
```
### `get_root_of`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Get root element of a DocType with a tree structure
```
### `get_ancestors_of`
**Arguments:** `doctype, name, order_by, limit`
**Decorators:** ``

**Docstring:**
```
Get ancestor elements of a DocType with a tree structure
```
### `get_descendants_of`
**Arguments:** `doctype, name, order_by, limit, ignore_permissions`
**Decorators:** ``

**Docstring:**
```
Return descendants of the current record
```

