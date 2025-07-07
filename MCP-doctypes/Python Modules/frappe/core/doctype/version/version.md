# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/version/version.py`

## Classes

### `Version`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `update_version_info` | `self, old, new` | `` | Update changed info and return true if change contains useful data. |
| `set_impersonator` | `data` | `staticmethod` |  |
| `set_diff` | `self, old, new` | `` | Set the data property with the diff of the docs if present |
| `for_insert` | `self, doc` | `` |  |
| `get_data` | `self` | `` |  |





## Functions

### `get_diff`
**Arguments:** `old, new, for_child, compare_cancelled`
**Decorators:** ``

**Docstring:**
```
Get diff between 2 document objects

If there is a change, then returns a dict like:

        {
                "changed"    : [[fieldname1, old, new], [fieldname2, old, new]],
                "added"      : [[table_fieldname1, {dict}], ],
                "removed"    : [[table_fieldname1, {dict}], ],
                "row_changed": [[table_fieldname1, row_name1, row_index,
                        [[child_fieldname1, old, new],
                        [child_fieldname2, old, new]], ]
                ],

        }
```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

