# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/variant_selector/test_variant_selector.py`

## Classes

### `TestVariantSelector`
**Inherits:** `FrappeTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `test_item_attributes` | `self` | `` | Test if the right attributes are fetched in the popup.
(Attributes must only come from active items)

Attribute selection must not be linked to Website Items. |
| `test_next_item_variant_values` | `self` | `` | Test if on selecting an attribute value, the next possible values
are filtered accordingly.
Values that dont apply should not be fetched.
E.g.
There is a ** Small-Red ** Tshirt. No other colour in this size.
On selecting ** Small **, only ** Red ** should be selectable next. |
| `test_exact_match_with_price` | `self` | `` | Test price fetching and matching of variant without Website Item |





## Functions

No top-level functions found in this file.
