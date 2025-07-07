# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_search.py`

## Classes

### `TestSearch`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_search_field_sanitizer` | `self` | `` |  |
| `test_only_enabled_in_mention` | `self` | `` |  |
| `test_link_field_order` | `self` | `` |  |
| `test_link_search_in_foreign_language` | `self` | `` |  |
| `test_doctype_search_in_foreign_language` | `self` | `` |  |
| `test_validate_and_sanitize_search_inputs` | `self` | `` |  |
| `test_reference_doctype` | `self` | `` | search query methods should get reference_doctype if they want |
| `test_search_relevance` | `self` | `` |  |
| `test_search_with_paren` | `self` | `` |  |





## Functions

### `get_data`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `query_with_reference_doctype`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters, reference_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `setup_test_link_field_order`
**Arguments:** `TestCase`
**Decorators:** ``

**Docstring:**
```

```
### `teardown_test_link_field_order`
**Arguments:** `TestCase`
**Decorators:** ``

**Docstring:**
```

```

