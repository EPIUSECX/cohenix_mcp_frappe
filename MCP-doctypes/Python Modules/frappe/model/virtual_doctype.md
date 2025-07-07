# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/virtual_doctype.py`

## Classes

### `VirtualDoctype`
**Inherits:** `Protocol`


**Docstring:**
```
This class documents requirements that must be met by a doctype controller to function as virtual doctype


Additional requirements:
- DocType controller has to inherit from `frappe.model.document.Document` class

Note:
- "Backend" here means any storage service, it can be a database, flat file or network call to API.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_list` | `` | `staticmethod` | Similar to reportview.get_list |
| `get_count` | `` | `staticmethod` | Similar to reportview.get_count, return total count of documents on listview. |
| `get_stats` | `` | `staticmethod` | Similar to reportview.get_stats, return sidebar stats. |
| `db_insert` | `self` | `` | Serialize the `Document` object and insert it in backend. |
| `load_from_db` | `self` | `` | Using self.name initialize current document from backend data.

This is responsible for updatinng __dict__ of class with all the fields on doctype. |
| `db_update` | `self` | `` | Serialize the `Document` object and update existing document in backend. |
| `delete` | `self` | `` | Delete the current document from backend |





## Functions

### `validate_controller`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```

