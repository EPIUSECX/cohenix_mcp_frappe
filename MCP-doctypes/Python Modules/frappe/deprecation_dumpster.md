# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/deprecation_dumpster.py`

## Classes

### `Color`


**Docstring:**
```

```

**Methods:**
No methods found.

### `FrappeDeprecationError`
**Inherits:** `Warning`


**Docstring:**
```
Deprecated feature in current version.

Raises an error by default but can be configured via PYTHONWARNINGS in an emergency.
```

**Methods:**
No methods found.

### `FrappeDeprecationWarning`
**Inherits:** `Warning`


**Docstring:**
```
Deprecated feature in next version
```

**Methods:**
No methods found.

### `PendingFrappeDeprecationWarning`
**Inherits:** `FrappeDeprecationWarning`


**Docstring:**
```
Deprecated feature in develop beyond next version.

Warning ignored by default.

The deprecation decision may still be reverted or deferred at this stage.
Regardless, using the new variant is encouraged and stable.
```

**Methods:**
No methods found.

### `V15FrappeDeprecationWarning`
**Inherits:** `FrappeDeprecationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `V16FrappeDeprecationWarning`
**Inherits:** `FrappeDeprecationWarning`


**Docstring:**
```

```

**Methods:**
No methods found.

### `V17FrappeDeprecationWarning`
**Inherits:** `PendingFrappeDeprecationWarning`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `colorize`
**Arguments:** `text, color_code`
**Decorators:** ``

**Docstring:**
```

```
### `__get_deprecation_class`
**Arguments:** `graduation, class_name`
**Decorators:** ``

**Docstring:**
```

```
### `deprecated`
**Arguments:** `original, marked, graduation, msg, stacklevel`
**Decorators:** ``

**Docstring:**
```
Decorator to wrap a function/method as deprecated.

Arguments:
        - original: frappe.utils.make_esc  (fully qualified)
        - marked: 2024-09-13  (the date it has been marked)
        - graduation: v17  (generally: current version + 2)
```
### `deprecation_warning`
**Arguments:** `marked, graduation, msg`
**Decorators:** ``

**Docstring:**
```
Warn in-place from a deprecated code path, for objects use `@deprecated` decorator from the deprectation_dumpster"

Arguments:
        - marked: 2024-09-13  (the date it has been marked)
        - graduation: v17  (generally: current version + 2)
```
### `_old_deprecated`
**Arguments:** `func`
**Decorators:** ``

**Docstring:**
```

```
### `_old_deprecation_warning`
**Arguments:** `msg`
**Decorators:** ``

**Docstring:**
```

```
### `make_esc`
**Arguments:** `esc_chars`
**Decorators:** ``

**Docstring:**
```
Function generator for Escaping special characters
```
### `is_column_missing`
**Arguments:** `e`
**Decorators:** ``

**Docstring:**
```

```
### `show_progress`
**Arguments:** `docnames, message, i, description`
**Decorators:** ``

**Docstring:**
```

```
### `get_js`
**Arguments:** `items`
**Decorators:** ``

**Docstring:**
```
Load JS code files.  Will also append translations
and extend `frappe._messages`

:param items: JSON list of paths of the js files to be loaded.
```
### `read_multi_pdf`
**Arguments:** `output`
**Decorators:** ``

**Docstring:**
```

```
### `gzip_compress`
**Arguments:** `data, compresslevel`
**Decorators:** ``

**Docstring:**
```
Compress data in one shot and return the compressed string.
Optional argument is the compression level, in range of 0-9.
```
### `gzip_decompress`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```
Decompress a gzip compressed string in one shot.
Return the decompressed string.
```
### `send_mail`
**Arguments:** `email_queue_name, smtp_server_instance`
**Decorators:** ``

**Docstring:**
```
This is equivalent to EmailQueue.send.

This provides a way to make sending mail as a background job.
```
### `get_translated_dict`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `validate_roles`
**Arguments:** `self`
**Decorators:** ``

**Docstring:**
```

```
### `test_runner_get_modules`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `test_runner_make_test_records`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `test_runner_make_test_objects`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `test_runner_make_test_records_for_doctype`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `test_runner_print_mandatory_fields`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `test_runner_get_test_record_log`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `test_runner_add_to_test_record_log`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `test_runner_main`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `test_xmlrunner_wrapper`
**Arguments:** `output`
**Decorators:** ``

**Docstring:**
```
Convenience wrapper to keep method signature unchanged for XMLTestRunner and TextTestRunner
```
### `tests_update_system_settings`
**Arguments:** `args, commit`
**Decorators:** ``

**Docstring:**
```

```
### `tests_get_system_setting`
**Arguments:** `key`
**Decorators:** ``

**Docstring:**
```

```
### `tests_change_settings`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `tests_patch_hooks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `tests_debug_on`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `tests_timeout`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_tests_CompatFrappeTestCase`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Unfortunately, due to circular imports, we just have to copy the entire old implementation here, even though IntegrationTestCase is overwhelmingly api-compatible.
```
### `get_compat_frappe_test_case_preparation`
**Arguments:** `cfg`
**Decorators:** ``

**Docstring:**
```

```
### `model_trace_traced_field_context`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `tests_utils_get_dependencies`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Get the dependencies for the specified doctype
```
### `test_runner_get_dependencies`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `frappe_get_test_records`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `compat_preload_test_records_upfront`
**Arguments:** `candidates`
**Decorators:** ``

**Docstring:**
```

```
### `get_number_format_info`
**Arguments:** `format`
**Decorators:** ``

**Docstring:**
```
DEPRECATED: use `NumberFormat.from_string()` from `frappe.utils.number_format` instead.

Return the decimal separator, thousands separator and precision for the given number `format` string.

e.g. get_number_format_info('#,##,###.##') -> ('.', ',', 2)

Will return ('.', ',', 2) for format strings which can't be guessed.
```
### `boilerplate_modules_txt`
**Arguments:** `dest, app_name, app_title`
**Decorators:** ``

**Docstring:**
```

```

