# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/dynamic_links.py`

## Classes

No classes found in this file.


## Functions

### `get_dynamic_link_map`
**Arguments:** `for_delete`
**Decorators:** ``

**Docstring:**
```
Build a map of all dynamically linked tables. For example,
        if Note is dynamically linked to ToDo, the function will return
        `{"Note": ["ToDo"], "Sales Invoice": ["Journal Entry Detail"]}`

Note: Will not map single doctypes
```
### `get_dynamic_links`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return list of dynamic link fields as DocField.
Uses cache if possible
```
### `_dynamic_link_map_key`
**Arguments:** `doctype, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `fetch_distinct_link_doctypes`
**Arguments:** `doctype, fieldname`
**Decorators:** ``

**Docstring:**
```
Return all unique doctypes a dynamic link is linking against.
Note:
- results are cached and can *possibly be outdated*
- cache gets updated when a document with different document link is discovered
- raw queries adding dynamic link won't update this cache
- cache miss can often be VERY expensive on large table.
```
### `invalidate_distinct_link_doctypes`
**Arguments:** `doctype, fieldname, linked_doctype`
**Decorators:** ``

**Docstring:**
```
If new linked doctype is discovered for a dynamic link then cache is evicted.
```

