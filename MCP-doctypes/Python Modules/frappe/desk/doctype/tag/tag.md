# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/tag/tag.py`

## Classes

### `Tag`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DocTags`


**Docstring:**
```
Tags for a particular doctype
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, dt` | `` |  |
| `get_tag_fields` | `self` | `` | Return `tag_fields` property. |
| `get_tags` | `self, dn` | `` | Return tag for a particular item. |
| `add` | `self, dn, tag` | `` | Add a new user tag. |
| `remove` | `self, dn, tag` | `` | Remove a user tag. |
| `remove_all` | `self, dn` | `` | Remove all user tags (call before delete). |
| `update` | `self, dn, tl` | `` | Update the `_user_tag` column in the table. |
| `setup` | `self` | `` | Add the `_user_tags` column if not exists. |





## Functions

### `check_user_tags`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```
if the user does not have a tags column, then it creates one
```
### `add_tag`
**Arguments:** `tag, dt, dn, color`
**Decorators:** ``

**Docstring:**
```
adds a new tag to a record, and creates the Tag master
```
### `add_tags`
**Arguments:** `tags, dt, docs, color`
**Decorators:** ``

**Docstring:**
```
adds a new tag to a record, and creates the Tag master
```
### `remove_tag`
**Arguments:** `tag, dt, dn`
**Decorators:** ``

**Docstring:**
```
removes tag from the record
```
### `get_tagged_docs`
**Arguments:** `doctype, tag`
**Decorators:** ``

**Docstring:**
```

```
### `get_tags`
**Arguments:** `doctype, txt`
**Decorators:** ``

**Docstring:**
```

```
### `delete_tags_for_document`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Delete the Tag Link entry of a document that has been deleted.

:param doc: Deleted document
```
### `update_tags`
**Arguments:** `doc, tags`
**Decorators:** ``

**Docstring:**
```
Add tags for documents.

:param doc: Document to be added to global tags
```
### `get_documents_for_tag`
**Arguments:** `tag`
**Decorators:** ``

**Docstring:**
```
Search for given text in Tag Link.

:param tag: tag to be searched
```
### `get_tags_list_for_awesomebar`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

