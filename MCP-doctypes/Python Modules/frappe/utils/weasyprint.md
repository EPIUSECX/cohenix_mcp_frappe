# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/weasyprint.py`

## Classes

### `PrintFormatGenerator`


**Docstring:**
```
Generate a PDF of a Document, with repeatable header and footer if letterhead is provided.

This generator draws its inspiration and, also a bit of its implementation, from this
discussion in the library github issues: https://github.com/Kozea/WeasyPrint/issues/92
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, print_format, doc, letterhead` | `` | Parameters
----------
print_format: str
        Name of the Print Format
doc: str
        Document to print
letterhead: str
        Letter Head to apply (optional) |
| `build_context` | `self` | `` |  |
| `get_html_preview` | `self` | `` |  |
| `get_main_html` | `self` | `` |  |
| `get_header_footer_html` | `self` | `` |  |
| `render_pdf` | `self` | `` | Return a bytes sequence of the rendered PDF. |
| `_compute_overlay_element` | `self, element` | `` | Parameters
----------
element: str
        Either 'header' or 'footer'

Returns
-------
element_body: BlockBox
        A Weasyprint pre-rendered representation of an html element
element_height: float
        The height of this element, which will be then translated in a html height |
| `_apply_overlay_on_main` | `self, main_doc, header_body, footer_body` | `` | Insert the header and the footer in the main document.

Parameters
----------
main_doc: Document
        The top level representation for a PDF page in Weasyprint.
header_body: BlockBox
        A representation for an html element in Weasyprint.
footer_body: BlockBox
        A representation for an html element in Weasyprint. |
| `_make_header_footer` | `self` | `` |  |
| `get_layout` | `self, print_format` | `` |  |
| `set_field_renderers` | `self, layout` | `` |  |
| `process_margin_texts` | `self, layout` | `` |  |
| `get_element` | `boxes, element` | `staticmethod` | Given a set of boxes representing the elements of a PDF page in a DOM-like way, find the
box which is named `element`.

Look at the notes of the class for more details on Weasyprint insides. |





## Functions

### `download_pdf`
**Arguments:** `doctype, name, print_format, letterhead`
**Decorators:** ``

**Docstring:**
```

```
### `get_html`
**Arguments:** `doctype, name, print_format, letterhead`
**Decorators:** ``

**Docstring:**
```

```
### `import_weasyprint`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

