# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/api/__init__.py`

## Classes

### `ApiVersion`
**Inherits:** `str, Enum`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `handle`
**Arguments:** `request`
**Decorators:** ``

**Docstring:**
```
Entry point for `/api` methods.

APIs are versioned using second part of path.
v1 -> `/api/v1/*`
v2 -> `/api/v2/*`

Different versions have different specification but broadly following things are supported:

- `/api/method/{methodname}` will call a whitelisted method
- `/api/resource/{doctype}` will query a table
        examples:
        - `?fields=["name", "owner"]`
        - `?filters=[["Task", "name", "like", "%005"]]`
        - `?limit_start=0`
        - `?limit_page_length=20`
- `/api/resource/{doctype}/{name}` will point to a resource
        `GET` will return document
        `POST` will insert
        `PUT` will update
        `DELETE` will delete
```
### `get_api_version`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

