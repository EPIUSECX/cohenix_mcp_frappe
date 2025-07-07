# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/search/website_search.py`

## Classes

### `WebsiteSearch`
**Inherits:** `FullTextSearch`


**Docstring:**
```
Wrapper for WebsiteSearch
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_schema` | `self` | `` |  |
| `get_fields_to_search` | `self` | `` |  |
| `get_id` | `self` | `` |  |
| `get_items_to_index` | `self` | `` | Get all routes to be indexed, this includes the static pages in www/ and routes from published documents.

Return:
        self (object): FullTextSearch Instance |
| `get_document_to_index` | `self, route` | `` | Render a page and parse it using `BeautifulSoup`.

Args:
        path: route of the page to be parsed

Return a dictionary with title, path and content. |
| `parse_result` | `self, result` | `` |  |





## Functions

### `slugs_with_web_view`
**Arguments:** `_items_to_index`
**Decorators:** ``

**Docstring:**
```

```
### `get_static_pages_from_all_apps`
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

