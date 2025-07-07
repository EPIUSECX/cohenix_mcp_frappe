# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/comment/comment.py`

## Classes

### `Comment`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `after_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `notify_change` | `self, action` | `` |  |
| `remove_comment_from_cache` | `self` | `` |  |





## Functions

### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_comment_in_doc`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Updates `_comments` (JSON) property in parent Document.
Creates a column `_comments` if property does not exist.

Only user created Communication or Comment of type Comment are saved.

`_comments` format

        {
                "comment": [String],
                "by": [user],
                "name": [Comment Document name]
        }
```
### `get_comments_from_parent`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
get the list of comments cached in the document record in the column
`_comments`
```
### `update_comments_in_parent`
**Arguments:** `reference_doctype, reference_name, _comments`
**Decorators:** ``

**Docstring:**
```
Updates `_comments` property in parent Document with given dict.

:param _comments: Dict of comments.
```

