# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/edi/doctype/code_list/code_list.py`

## Classes

### `CodeList`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `on_trash` | `self` | `` |  |
| `__delete_linked_docs` | `self` | `` |  |
| `get_codes_for` | `self, doctype, name` | `` | Get the applicable codes for a doctype and name |
| `get_docnames_for` | `self, doctype, code` | `` | Get the mapped docnames for a doctype and code |
| `get_default_code` | `self` | `` | Get the default common code for this code list |
| `from_genericode` | `self, root` | `` | Extract Code List details from genericode XML |





## Functions

### `get_codes_for`
**Arguments:** `code_list, doctype, name`
**Decorators:** ``

**Docstring:**
```
Return the common code for a given record
```
### `get_docnames_for`
**Arguments:** `code_list, doctype, code`
**Decorators:** ``

**Docstring:**
```
Return the record name for a given common code
```
### `get_default_code`
**Arguments:** `code_list`
**Decorators:** ``

**Docstring:**
```
Return the default common code for a given code list
```

