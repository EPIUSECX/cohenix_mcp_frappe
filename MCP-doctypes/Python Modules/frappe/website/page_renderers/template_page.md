# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/page_renderers/template_page.py`

## Classes

### `TemplatePage`
**Inherits:** `BaseTemplatePage`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, path, http_status_code` | `` |  |
| `set_template_path` | `self` | `` | Searches for file matching the path in the /www
and /templates/pages folders and sets path if match is found |
| `can_render` | `self` | `` |  |
| `get_index_path_options` | `search_path` | `staticmethod` |  |
| `render` | `self` | `` |  |
| `get_html` | `self` | `cache_html` |  |
| `post_process_context` | `self` | `` |  |
| `add_sidebar_and_breadcrumbs` | `self` | `` |  |
| `set_pymodule` | `self` | `` | A template may have a python module with a `get_context` method along with it in the
same folder. Also the hyphens will be coverted to underscore for python module names.
This method sets the pymodule_name if it exists. |
| `setup_template_source` | `self` | `` | Setup template source, frontmatter and markdown conversion |
| `update_context` | `self` | `` |  |
| `set_pymodule_properties` | `self` | `` |  |
| `set_page_properties` | `self` | `` |  |
| `set_properties_from_source` | `self` | `` |  |
| `set_properties_via_comments` | `self` | `` |  |
| `run_pymodule_method` | `self, method_name` | `` |  |
| `render_template` | `self` | `` |  |
| `extends_template` | `self` | `` |  |
| `get_raw_template` | `self` | `` |  |
| `load_colocated_files` | `self` | `` | load co-located css/js files with the same name |
| `get_colocated_file` | `self, path` | `` |  |
| `extract_frontmatter` | `self` | `` |  |
| `convert_from_markdown` | `self` | `` |  |
| `update_toc` | `self, html` | `` |  |
| `set_standard_path` | `self, path` | `` |  |
| `set_missing_values` | `self` | `` |  |
| `set_user_info` | `self` | `` |  |





## Functions

### `get_start_folders`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

