# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/global_search.py`

## Classes

No classes found in this file.


## Functions

### `setup_global_search_table`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Creates __global_search table
:return:
```
### `reset`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Deletes all data in __global_search
:return:
```
### `get_doctypes_with_global_search`
**Arguments:** `with_child_tables`
**Decorators:** ``

**Docstring:**
```
Return doctypes with global search fields
:param with_child_tables:
:return:
```
### `rebuild_for_doctype`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Rebuild entries of doctype's documents in __global_search on change of
searchable fields
:param doctype: Doctype
```
### `delete_global_search_records_for_doctype`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_selected_fields`
**Arguments:** `meta, global_search_fields`
**Decorators:** ``

**Docstring:**
```

```
### `get_children_data`
**Arguments:** `doctype, meta`
**Decorators:** ``

**Docstring:**
```
Get all records from all the child tables of a doctype

all_children = {
        "parent1": {
                "child_doctype1": [
                        {
                                "field1": val1,
                                "field2": val2
                        }
                ]
        }
}
```
### `insert_values_for_multiple_docs`
**Arguments:** `all_contents`
**Decorators:** ``

**Docstring:**
```

```
### `update_global_search`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Add values marked with `in_global_search` to
`global_search_queue` from given doc
:param doc: Document to be added to global search
```
### `update_global_search_for_all_web_pages`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_routes_to_index`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `add_route_to_global_search`
**Arguments:** `route`
**Decorators:** ``

**Docstring:**
```

```
### `get_formatted_value`
**Arguments:** `value, field`
**Decorators:** ``

**Docstring:**
```
Prepare field from raw data
:param value:
:param field:
:return:
```
### `sync_global_search`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Inserts / updates values from `global_search_queue` to __global_search.
This is called via job scheduler
:param flags:
:return:
```
### `_get_deduped_search_item_values`
**Arguments:** `items`
**Decorators:** ``

**Docstring:**
```

```
### `sync_values`
**Arguments:** `values`
**Decorators:** ``

**Docstring:**
```

```
### `sync_value_in_queue`
**Arguments:** `value`
**Decorators:** ``

**Docstring:**
```

```
### `sync_value`
**Arguments:** `value`
**Decorators:** ``

**Docstring:**
```
Sync a given document to global search
:param value: dict of { doctype, name, content, published, title, route }
```
### `delete_for_document`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Delete the __global_search entry of a document that has
been deleted
:param doc: Deleted document
```
### `search`
**Arguments:** `text, start, limit, doctype`
**Decorators:** ``

**Docstring:**
```
Search for given text in __global_search
:param text: phrase to be searched
:param start: start results at, default 0
:param limit: number of results to return, default 20
:return: Array of result objects
```
### `web_search`
**Arguments:** `text, scope, start, limit`
**Decorators:** ``

**Docstring:**
```
Search for given text in __global_search where published = 1
:param text: phrase to be searched
:param scope: search only in this route, for e.g /docs
:param start: start results at, default 0
:param limit: number of results to return, default 20
:return: Array of result objects
```
### `get_distinct_words`
**Arguments:** `text`
**Decorators:** ``

**Docstring:**
```

```

