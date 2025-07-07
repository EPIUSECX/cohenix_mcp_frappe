# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_translate.py`

## Classes

### `TestTranslate`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_clear_cache` | `self` | `` |  |
| `test_extract_message_from_file` | `self` | `` |  |
| `test_read_language_variant` | `self` | `` |  |
| `test_translation_with_context` | `self` | `` |  |
| `test_lazy_translations` | `self` | `` |  |
| `test_request_language_resolution_with_form_dict` | `self` | `` | Test for frappe.translate.get_language

Case 1: frappe.form_dict._lang is set |
| `test_request_language_resolution_with_cookie` | `self` | `` | Test for frappe.translate.get_language

Case 2: frappe.form_dict._lang is not set, but preferred_language cookie is |
| `test_guest_request_language_resolution_with_cookie` | `self` | `` | Test for frappe.translate.get_language

Case 3: frappe.form_dict._lang is not set, but preferred_language cookie is [Guest User] |
| `test_global_translations` | `self` | `` |  |
| `test_guest_request_language_resolution_with_request_header` | `self` | `` | Test for frappe.translate.get_language

Case 4: frappe.form_dict._lang & preferred_language cookie is not set, but Accept-Language header is [Guest User] |
| `test_request_language_resolution_with_request_header` | `self` | `` | Test for frappe.translate.get_language

Case 5: frappe.form_dict._lang & preferred_language cookie is not set, but Accept-Language header is |
| `test_load_all_translate_files` | `self` | `` | Load all CSV files to ensure they have correct format |
| `test_python_extractor` | `self` | `` |  |
| `test_js_extractor` | `self` | `` |  |
| `test_js_parser_arg_capturing` | `self` | `` | Get non-flattened args in correct order so 3rd arg if present is always context. |





## Functions

### `verify_translation_files`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Function to verify translation file syntax in app.
```

