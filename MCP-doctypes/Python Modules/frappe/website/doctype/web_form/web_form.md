# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/web_form/web_form.py`

## Classes

### `WebForm`
**Inherits:** `WebsiteGenerator`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_fields` | `self` | `` | Validate all fields are present |
| `reset_field_parent` | `self` | `` | Convert link fields to select with names as options. |
| `on_update` | `self` | `` | Writes the .txt for this page and if write_content is checked,
it will write out a .html file |
| `get_context` | `self, context` | `` | Build context to render the `web_form.html` template |
| `add_metatags` | `self, context` | `` |  |
| `load_translations` | `self, context` | `` |  |
| `load_list_data` | `self, context` | `` |  |
| `load_form_data` | `self, context` | `` | Load document `doc` and `layout` properties for template |
| `add_custom_context_and_script` | `self, context` | `` | Update context from module if standard and append script |
| `get_parents` | `self, context` | `` |  |
| `validate_mandatory` | `self, doc` | `` | Validate mandatory web form fields |
| `allow_website_search_indexing` | `self` | `` |  |
| `has_web_form_permission` | `self, doctype, name, ptype` | `` |  |
| `get_webform_attachments` | `self, context` | `` | Returns permitted attachments for the webform.
NOTE: At this point, `self.login_required` is True. |





## Functions

### `get_web_form_module`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `accept`
**Arguments:** `web_form, data`
**Decorators:** ``

**Docstring:**
```
Save the web form
```
### `delete`
**Arguments:** `web_form_name, docname`
**Decorators:** ``

**Docstring:**
```

```
### `delete_multiple`
**Arguments:** `web_form_name, docnames`
**Decorators:** ``

**Docstring:**
```

```
### `check_webform_perm`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_web_form_filters`
**Arguments:** `web_form_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_form_data`
**Arguments:** `doctype, docname, web_form_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_in_list_view_fields`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_link_options`
**Arguments:** `web_form_name, doctype, allow_read_on_all_link_options`
**Decorators:** ``

**Docstring:**
```

```
### `get_published_web_forms`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

