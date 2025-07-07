# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/patches/v13_0/delete_orphaned_tables.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `has_deleted_company_transactions`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_child_doctypes_whose_parent_doctypes_were_affected`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_affected_doctypes`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_not_child_table`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `remove_duplicate_items`
**Arguments:** `affected_doctypes`
**Decorators:** ``

**Docstring:**
```

```
### `check_for_new_doc_with_same_name_as_deleted_parent`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Compares creation times of parent and child docs.
Since Transaction Deletion Record resets the naming series after deletion,
it allows the creation of new docs with the same names as the deleted ones.
```

