# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/legacy_search.py`

## Classes

### `ProductSearch`
**Inherits:** `FullTextSearch`


**Docstring:**
```
Wrapper for WebsiteSearch
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_schema` | `self` | `` |  |
| `get_id` | `self` | `` |  |
| `get_items_to_index` | `self` | `` | Get all routes to be indexed, this includes the static pages
in www/ and routes from published documents

Returns:
        self (object): FullTextSearch Instance |
| `get_document_to_index` | `self, item` | `` |  |
| `search` | `self, text, scope, limit` | `` | Search from the current index

Args:
        text (str): String to search for
        scope (str, optional): Scope to limit the search. Defaults to None.
        limit (int, optional): Limit number of search results. Defaults to 20.

Returns:
        [List(_dict)]: Search results |
| `parse_result` | `self, result` | `` |  |





## Functions

### `get_all_published_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_index_for_path`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```
### `remove_document_from_index`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```
### `build_index_for_all_routes`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

