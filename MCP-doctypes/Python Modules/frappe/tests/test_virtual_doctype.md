# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_virtual_doctype.py`

## Classes

### `VirtualDoctypeTest`
**Inherits:** `Document`


**Docstring:**
```
This is a virtual doctype controller for test/demo purposes.

- It uses a JSON file on disk as "backend".
- Key is docname and value is the document itself.

Example:
{
        "doc1": {"name": "doc1", ...}
        "doc2": {"name": "doc2", ...}
}
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_current_data` | `` | `staticmethod` | Read data from disk |
| `update_data` | `data` | `staticmethod` | Flush updated data to disk |
| `db_insert` | `self` | `` |  |
| `load_from_db` | `self` | `` |  |
| `db_update` | `self` | `` |  |
| `delete` | `self` | `` |  |
| `get_list` | `` | `staticmethod` |  |
| `get_count` | `` | `staticmethod` |  |
| `get_stats` | `` | `staticmethod` |  |


### `TestVirtualDoctypes`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDown` | `self` | `` |  |
| `test_insert_update_and_load_from_desk` | `self` | `` | Insert, update, reload and assert changes |
| `test_multiple_doc_insert_and_get_list` | `self` | `` |  |
| `test_get_count` | `self` | `` |  |
| `test_delete_doc` | `self` | `` |  |
| `test_controller_validity` | `self` | `` |  |





## Functions

No top-level functions found in this file.
