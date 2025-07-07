# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/utils.py`

## Classes

No classes found in this file.


## Functions

### `delete_page_cache`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```
### `find_first_image`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```

```
### `can_cache`
**Arguments:** `no_cache`
**Decorators:** ``

**Docstring:**
```

```
### `get_comment_list`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_home_page`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_home_page_via_hooks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_boot_data`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_signup_disabled`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `cleanup_page_name`
**Arguments:** `title`
**Decorators:** ``

**Docstring:**
```
make page name from title
```
### `abs_url`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Deconstructs and Reconstructs a URL into an absolute URL or a URL relative from root '/'
```
### `get_toc`
**Arguments:** `route, url_prefix, app`
**Decorators:** ``

**Docstring:**
```
Insert full index (table of contents) for {index} tag
```
### `get_next_link`
**Arguments:** `route, url_prefix, app`
**Decorators:** ``

**Docstring:**
```

```
### `get_full_index`
**Arguments:** `route, app`
**Decorators:** ``

**Docstring:**
```
Return full index of the website for www upto the n-th level.
```
### `extract_title`
**Arguments:** `source, path`
**Decorators:** ``

**Docstring:**
```
Return title from `&lt;!-- title --&gt;` or &lt;h1&gt; or path.
```
### `extract_comment_tag`
**Arguments:** `source, tag`
**Decorators:** ``

**Docstring:**
```
Extract custom tags in comments from source.

:param source: raw template source in HTML
:param title: tag to search, example "title"
```
### `get_html_content_based_on_type`
**Arguments:** `doc, fieldname, content_type`
**Decorators:** ``

**Docstring:**
```
Set content based on content_type
```
### `clear_cache`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Clear website caches
:param path: (optional) for the given path
```
### `clear_website_cache`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```
### `get_frontmatter`
**Arguments:** `string`
**Decorators:** ``

**Docstring:**
```
Reference: https://github.com/jonbeebe/frontmatter
```
### `get_sidebar_items`
**Arguments:** `parent_sidebar, basepath`
**Decorators:** ``

**Docstring:**
```

```
### `get_portal_sidebar_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_sidebar_items_from_sidebar_file`
**Arguments:** `basepath, look_for_sidebar_json`
**Decorators:** ``

**Docstring:**
```

```
### `get_sidebar_json_path`
**Arguments:** `path, look_for`
**Decorators:** ``

**Docstring:**
```
Get _sidebar.json path from directory path
:param path: path of the current diretory
:param look_for: if True, look for _sidebar.json going upwards from given path
:return: _sidebar.json path
```
### `cache_html`
**Arguments:** `func`
**Decorators:** ``

**Docstring:**
```

```
### `build_response`
**Arguments:** `path, data, http_status_code, headers`
**Decorators:** ``

**Docstring:**
```

```
### `set_content_type`
**Arguments:** `response, data, path`
**Decorators:** ``

**Docstring:**
```

```
### `add_preload_for_bundled_assets`
**Arguments:** `response`
**Decorators:** ``

**Docstring:**
```

```
### `is_binary_file`
**Arguments:** `path`
**Decorators:** `lru_cache`

**Docstring:**
```

```

