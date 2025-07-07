# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/modules/utils.py`

## Classes

No classes found in this file.


## Functions

### `export_module_json`
**Arguments:** `doc, is_standard, module`
**Decorators:** ``

**Docstring:**
```
Make a folder for the given doc and add its json file (make it a standard object that will be synced).

Return the absolute file_path without the extension.
Eg: For exporting a Print Format "_Test Print Format 1", the return value will be
`/home/gavin/frappe-bench/apps/frappe/frappe/core/print_format/_test_print_format_1/_test_print_format_1`
```
### `get_doc_module`
**Arguments:** `module, doctype, name`
**Decorators:** ``

**Docstring:**
```
Get custom module for given document
```
### `export_customizations`
**Arguments:** `module, doctype, sync_on_migrate, with_permissions`
**Decorators:** ``

**Docstring:**
```
Export Custom Field and Property Setter for the current document to the app folder.
This will be synced with bench migrate
```
### `sync_customizations`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Sync custom fields and property setters from custom folder in each app module
```
### `sync_customizations_for_doctype`
**Arguments:** `data, folder, filename`
**Decorators:** ``

**Docstring:**
```
Sync doctype customzations for a particular data set
```
### `scrub_dt_dn`
**Arguments:** `dt, dn`
**Decorators:** ``

**Docstring:**
```
Return in lowercase and code friendly names of doctype and name for certain types.
```
### `get_doc_path`
**Arguments:** `module, doctype, name`
**Decorators:** ``

**Docstring:**
```
Return path of a doc in a module.
```
### `reload_doc`
**Arguments:** `module, dt, dn, force, reset_permissions`
**Decorators:** ``

**Docstring:**
```
Reload Document from model (`[module]/<doctype>/[name]/[name].json`) files
```
### `export_doc`
**Arguments:** `doctype, name, module`
**Decorators:** ``

**Docstring:**
```
Write a doc to standard path.
```
### `get_doctype_module`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Return **Module Def** name of given doctype.
```
### `load_doctype_module`
**Arguments:** `doctype, module, prefix, suffix`
**Decorators:** ``

**Docstring:**
```
Return the module object for given doctype.

Note: This will return the standard defined module object for the doctype irrespective
of the `override_doctype_class` hook.
```
### `get_module_name`
**Arguments:** `doctype, module, prefix, suffix, app`
**Decorators:** ``

**Docstring:**
```

```
### `get_module_app`
**Arguments:** `module`
**Decorators:** ``

**Docstring:**
```

```
### `get_app_publisher`
**Arguments:** `module`
**Decorators:** ``

**Docstring:**
```

```
### `make_boilerplate`
**Arguments:** `template, doc, opts`
**Decorators:** ``

**Docstring:**
```

```

