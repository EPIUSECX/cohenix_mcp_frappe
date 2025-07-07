# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/like.py`

## Classes

No classes found in this file.


## Functions

### `toggle_like`
**Arguments:** `doctype, name, add`
**Decorators:** ``

**Docstring:**
```
Adds / removes the current user in the `__liked_by` property of the given document.
If column does not exist, will add it in the database.

The `_liked_by` property is always set from this function and is ignored if set via
Document API

:param doctype: DocType of the document to like
:param name: Name of the document to like
:param add: `Yes` if like is to be added. If not `Yes` the like will be removed.
```
### `_toggle_like`
**Arguments:** `doctype, name, add, user`
**Decorators:** ``

**Docstring:**
```
Same as toggle_like but hides param `user` from API
```
### `remove_like`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Remove previous Like
```
### `add_comment`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```

