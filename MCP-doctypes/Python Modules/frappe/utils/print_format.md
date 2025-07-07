# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/print_format.py`

## Classes

No classes found in this file.


## Functions

### `download_multi_pdf`
**Arguments:** `doctype, name, format, no_letterhead, letterhead, options`
**Decorators:** ``

**Docstring:**
```
Calls _download_multi_pdf with the given parameters and returns the response
```
### `download_multi_pdf_async`
**Arguments:** `doctype, name, format, no_letterhead, letterhead, options`
**Decorators:** ``

**Docstring:**
```
Calls _download_multi_pdf with the given parameters in a background job, returns task ID
```
### `_download_multi_pdf`
**Arguments:** `doctype, name, format, no_letterhead, letterhead, options, task_id`
**Decorators:** ``

**Docstring:**
```
Return a PDF compiled by concatenating multiple documents.

The documents can be from a single DocType or multiple DocTypes.

Note: The design may seem a little weird, but it  exists to ensure backward compatibility.
          The correct way to use this function is to pass a dict to doctype as described below

NEW FUNCTIONALITY
=================
Parameters:
doctype (dict):
        key (string): DocType name
        value (list): of strings of doc names which need to be concatenated and printed
name (string):
        name of the pdf which is generated
format:
        Print Format to be used

OLD FUNCTIONALITY - soon to be deprecated
=========================================
Parameters:
doctype (string):
        name of the DocType to which the docs belong which need to be printed
name (string or list):
        If string the name of the doc which needs to be printed
        If list the list of strings of doc names which needs to be printed
format:
        Print Format to be used

Returns:
Publishes a link to the PDF to the given task ID
```
### `download_pdf`
**Arguments:** `doctype, name, format, doc, no_letterhead, language, letterhead, pdf_generator`
**Decorators:** ``

**Docstring:**
```

```
### `report_to_pdf`
**Arguments:** `html, orientation`
**Decorators:** ``

**Docstring:**
```

```
### `print_by_server`
**Arguments:** `doctype, name, printer_setting, print_format, doc, no_letterhead, file_path`
**Decorators:** ``

**Docstring:**
```

```

