# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/path_resolver.py`

## Classes

### `PathResolver`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, path, http_status_code` | `` |  |
| `resolve` | `self` | `` | Return endpoint and a renderer instance that can render the endpoint. |
| `is_valid_path` | `self` | `` |  |
| `get_custom_page_renderers` | `` | `staticmethod` |  |





## Functions

### `resolve_redirect`
**Arguments:** `path, query_string`
**Decorators:** ``

**Docstring:**
```
Resolve redirects from hooks

Example:

                website_redirect = [
                                # absolute location
                                {"source": "/from", "target": "https://mysite/from"},

                                # relative location
                                {"source": "/from", "target": "/main"},

                                # use regex
                                {"source": r"/from/(.*)", "target": r"/main/"}
                                # use r as a string prefix if you use regex groups or want to escape any string literal
                ]
```
### `resolve_path`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```
### `resolve_from_map`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
transform dynamic route to a static one from hooks and route defined in doctype
```
### `get_website_rules`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get website route rules from hooks and DocType route
```
### `validate_path`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```

