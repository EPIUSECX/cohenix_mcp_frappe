# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/web_page/web_page.py`

## Classes

### `WebPage`
**Inherits:** `WebsiteGenerator`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `get_context` | `self, context` | `` |  |
| `render_dynamic` | `self, context` | `` |  |
| `set_breadcrumbs` | `self, context` | `` | Build breadcrumbs template |
| `set_title_and_header` | `self, context` | `` | Extract and set title and header from content or context. |
| `set_page_blocks` | `self, context` | `` |  |
| `add_hero` | `self, context` | `` | Add a hero element if specified in content or hooks.
Hero elements get full page width. |
| `check_for_redirect` | `self, context` | `` |  |
| `set_metatags` | `self, context` | `` |  |
| `validate_dates` | `self` | `` |  |





## Functions

### `check_publish_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_web_blocks_html`
**Arguments:** `blocks`
**Decorators:** ``

**Docstring:**
```
Convert a list of blocks into Raw HTML and extract out their scripts for deduplication.
```
### `extract_script_and_style_tags`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```

```
### `get_dynamic_web_pages`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

