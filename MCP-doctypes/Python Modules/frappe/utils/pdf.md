# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/pdf.py`

## Classes

No classes found in this file.


## Functions

### `pdf_header_html`
**Arguments:** `soup, head, content, styles, html_id, css, path`
**Decorators:** ``

**Docstring:**
```

```
### `pdf_body_html`
**Arguments:** `template, args`
**Decorators:** ``

**Docstring:**
```

```
### `_guess_template_error_line_number`
**Arguments:** `template`
**Decorators:** ``

**Docstring:**
```
Guess line on which exception occurred from current traceback.
```
### `pdf_footer_html`
**Arguments:** `soup, head, content, styles, html_id, css, path`
**Decorators:** ``

**Docstring:**
```

```
### `get_pdf`
**Arguments:** `html, options, output`
**Decorators:** ``

**Docstring:**
```

```
### `get_file_data_from_writer`
**Arguments:** `writer_obj`
**Decorators:** ``

**Docstring:**
```

```
### `prepare_options`
**Arguments:** `html, options`
**Decorators:** ``

**Docstring:**
```

```
### `get_cookie_options`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `read_options_from_html`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```

```
### `get_print_format_styles`
**Arguments:** `soup`
**Decorators:** ``

**Docstring:**
```
Get styles purely on class 'print-format'.
Valid:
1) .print-format { ... }
2) .print-format, p { ... } | p, .print-format { ... }

Invalid (applied on child elements):
1) .print-format p { ... } | .print-format > p { ... }
2) .print-format #abc { ... }

Returns:
[cssutils.css.Property(name='margin-top', value='50mm', priority=''), ...]
```
### `inline_private_images`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```

```
### `_get_base64_image`
**Arguments:** `src`
**Decorators:** ``

**Docstring:**
```
Return base64 version of image if user has permission to view it
```
### `prepare_header_footer`
**Arguments:** `soup`
**Decorators:** ``

**Docstring:**
```

```
### `cleanup`
**Arguments:** `options`
**Decorators:** ``

**Docstring:**
```

```
### `toggle_visible_pdf`
**Arguments:** `soup`
**Decorators:** ``

**Docstring:**
```

```
### `is_wkhtmltopdf_valid`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_wkhtmltopdf_version`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

