# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/classes/unit_test_case.py`

## Classes

### `BaseTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `registerAs` | `cls, _as` | `classmethod` |  |


### `UnitTestCase`
**Inherits:** `BaseTestCase`


**Docstring:**
```
Unit test class for Frappe tests.

This class extends unittest.TestCase and provides additional utilities
specific to Frappe framework. It's designed for testing individual
components or functions in isolation.

Key features:
- Custom assertions for Frappe-specific comparisons
- Utilities for HTML and SQL normalization
- Context managers for user switching and time freezing

Note: If you override `setUpClass`, make sure to call `super().setUpClass()`
to maintain the functionality of this base class.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `assertQueryEqual` | `self, first, second` | `` |  |
| `assertSequenceSubset` | `self, larger, smaller, msg` | `` | Assert that `expected` is a subset of `actual`. |
| `assertDocumentEqual` | `self, expected, actual` | `` | Compare a (partial) expected document with actual Document. |
| `_compare_field` | `self, expected, actual, doc, field` | `` |  |
| `normalize_html` | `code` | `staticmethod` | Formats HTML consistently so simple string comparisons can work on them. |
| `normalize_sql` | `query` | `staticmethod` | Formats SQL consistently so simple string comparisons can work on them. |





## Functions

### `_get_doctype_from_module`
**Arguments:** `cls`
**Decorators:** ``

**Docstring:**
```

```

