# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/form/assign_to.py`

## Classes

### `DuplicateToDoError`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `get`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```
get assigned to
```
### `add`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```
add in someone's to do list
args = {
        "assign_to": [],
        "doctype": ,
        "name": ,
        "description": ,
        "assignment_rule":
}
```
### `add_multiple`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `close_all_assignments`
**Arguments:** `doctype, name, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `remove`
**Arguments:** `doctype, name, assign_to, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `remove_multiple`
**Arguments:** `doctype, names, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `close`
**Arguments:** `doctype, name, assign_to, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `set_status`
**Arguments:** `doctype, name, todo, assign_to, status, ignore_permissions`
**Decorators:** ``

**Docstring:**
```
remove from todo
```
### `clear`
**Arguments:** `doctype, name, ignore_permissions`
**Decorators:** ``

**Docstring:**
```
Clears assignments, return False if not assigned.
```
### `notify_assignment`
**Arguments:** `assigned_by, allocated_to, doc_type, doc_name, action, description`
**Decorators:** ``

**Docstring:**
```
Notify assignee that there is a change in assignment
```
### `format_message_for_assign_to`
**Arguments:** `users`
**Decorators:** ``

**Docstring:**
```

```

