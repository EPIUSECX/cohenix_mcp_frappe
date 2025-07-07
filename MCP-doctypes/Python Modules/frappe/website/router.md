# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/router.py`

## Classes

No classes found in this file.


## Functions

### `get_page_info_from_web_page_with_dynamic_routes`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Query Web Page with dynamic_route = 1 and evaluate if any of the routes match
```
### `get_page_info_from_web_form`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Query published web forms and evaluate if the route matches
```
### `evaluate_dynamic_routes`
**Arguments:** `rules, path`
**Decorators:** ``

**Docstring:**
```
Use Werkzeug routing to evaluate dynamic routes like /project/<name>
https://werkzeug.palletsprojects.com/en/1.0.x/routing/
```
### `get_pages`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Get all pages. Called for docs / sitemap
```
### `get_pages_from_path`
**Arguments:** `start, app, app_path`
**Decorators:** ``

**Docstring:**
```

```
### `get_page_info`
**Arguments:** `path, app, start, basepath, app_path, fname`
**Decorators:** ``

**Docstring:**
```
Load page info
```
### `setup_source`
**Arguments:** `page_info`
**Decorators:** ``

**Docstring:**
```
Get the HTML source of the template
```
### `get_base_template`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Return the `base_template` for given `path`.

The default `base_template` for any web route is `templates/web.html` defined in `hooks.py`.
This can be overridden for certain routes in `custom_app/hooks.py` based on regex pattern.
```
### `setup_index`
**Arguments:** `page_info`
**Decorators:** ``

**Docstring:**
```
Build page sequence from index.txt
```
### `load_properties_from_controller`
**Arguments:** `page_info`
**Decorators:** ``

**Docstring:**
```

```
### `get_doctypes_with_web_view`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return doctypes with Has Web View or set via hooks
```
### `get_start_folders`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `clear_routing_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

