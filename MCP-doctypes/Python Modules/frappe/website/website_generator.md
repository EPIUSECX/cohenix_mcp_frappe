# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/website_generator.py`

## Classes

### `WebsiteGenerator`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `get_website_properties` | `self, key, default` | `` |  |
| `autoname` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `set_route` | `self` | `` |  |
| `make_route` | `self` | `` | Return the default route. If `route` is specified in DocType it will be route/title. |
| `scrubbed_title` | `self` | `` |  |
| `get_title_field` | `self` | `` | return title field from website properties or meta.title_field |
| `clear_cache` | `self` | `` |  |
| `scrub` | `self, text` | `` |  |
| `get_parents` | `self, context` | `` | Return breadcrumbs |
| `on_update` | `self` | `` |  |
| `on_change` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `is_website_published` | `self` | `` | Return true if published in website |
| `get_condition_field` | `self` | `` |  |
| `get_page_info` | `self` | `` |  |
| `send_indexing_request` | `self, operation_type` | `` | Send indexing request on update/trash operation. |
| `allow_website_search_indexing` | `self` | `` |  |
| `remove_old_route_from_index` | `self` | `` | Remove page from the website index if the route has changed. |
| `update_website_search_index` | `self` | `` | Update the full test index executed on document change event.
- remove document from index if document is unpublished
- update index otherwise |





## Functions

No top-level functions found in this file.
