# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/web_template/web_template.py`

## Classes

### `WebTemplate`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `on_update` | `self` | `` | Clear cache for all Web Pages in which this template is used |
| `on_trash` | `self` | `` |  |
| `export_to_files` | `self` | `` | Export Web Template to a new folder.

Doc is exported as JSON. The content of the `template` field gets
written into a separate HTML file. The template should not be contained
in the JSON. |
| `import_from_files` | `self` | `` |  |
| `create_template_file` | `self, html` | `` | Touch a HTML file for the Web Template and add existing content, if any. |
| `get_template_folder` | `self` | `` | Return the absolute path to the template's folder. |
| `get_template_path` | `self` | `` | Return the absolute path to the template's HTML file. |
| `get_template` | `self, standard` | `` | Get the jinja template string.

Params:
standard - if True, look on the disk instead of in the database. |
| `render` | `self, values` | `` |  |





## Functions

No top-level functions found in this file.
