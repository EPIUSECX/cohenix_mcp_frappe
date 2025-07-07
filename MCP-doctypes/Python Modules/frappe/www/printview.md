# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/www/printview.py`

## Classes

### `PrintContext`
**Inherits:** `TypedDict`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `get_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```
Build context for print
```
### `get_print_format_doc`
**Arguments:** `print_format_name, meta`
**Decorators:** ``

**Docstring:**
```
Return print format document.
```
### `get_rendered_template`
**Arguments:** `doc, print_format, meta, no_letterhead, letterhead, trigger_print, settings`
**Decorators:** ``

**Docstring:**
```

```
### `set_link_titles`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_title_values_for_link_and_dynamic_link_fields`
**Arguments:** `meta, doc, parent_doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_title_values_for_table_and_multiselect_fields`
**Arguments:** `meta, doc`
**Decorators:** ``

**Docstring:**
```

```
### `convert_markdown`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Convert text field values to markdown if necessary.
```
### `get_html_and_style`
**Arguments:** `doc, name, print_format, no_letterhead, letterhead, trigger_print, style, settings`
**Decorators:** ``

**Docstring:**
```
Return `html` and `style` of print format, used in PDF etc.
```
### `get_rendered_raw_commands`
**Arguments:** `doc, name, print_format`
**Decorators:** ``

**Docstring:**
```
Return Rendered Raw Commands of print format, used to send directly to printer.
```
### `validate_print_permission`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `validate_key`
**Arguments:** `key, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_letter_head`
**Arguments:** `doc, no_letterhead, letterhead`
**Decorators:** ``

**Docstring:**
```

```
### `get_print_format`
**Arguments:** `doctype, print_format`
**Decorators:** ``

**Docstring:**
```

```
### `make_layout`
**Arguments:** `doc, meta, format_data`
**Decorators:** ``

**Docstring:**
```
Builds a hierarchical layout object from the fields list to be rendered
by `standard.html`

:param doc: Document to be rendered.
:param meta: Document meta object (doctype).
:param format_data: Fields sequence and properties defined by Print Format Builder.
```
### `is_visible`
**Arguments:** `df, doc`
**Decorators:** ``

**Docstring:**
```
Return True if docfield is visible in print layout and does not have print_hide set.
```
### `has_value`
**Arguments:** `df, doc`
**Decorators:** ``

**Docstring:**
```
Return True if given docfield (`df`) has some value in the given document (`doc`).
```
### `get_print_style`
**Arguments:** `style, print_format, for_legacy`
**Decorators:** ``

**Docstring:**
```

```
### `get_font`
**Arguments:** `print_settings, print_format, for_legacy`
**Decorators:** ``

**Docstring:**
```

```
### `get_visible_columns`
**Arguments:** `data, table_meta, df`
**Decorators:** ``

**Docstring:**
```
Return list of visible columns based on print_hide and if all columns have value.
```
### `column_has_value`
**Arguments:** `data, fieldname, col_df`
**Decorators:** ``

**Docstring:**
```
Check if at least one cell in column has non-zero and non-blank value
```

