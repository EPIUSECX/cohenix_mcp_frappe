# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/doctype/override_doctype/item.py`

## Classes

### `DataValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `WebshopItem`
**Inherits:** `Item`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `on_update` | `self` | `` |  |
| `before_rename` | `self, old_name, new_name, merge` | `` |  |
| `validate_duplicate_website_item_before_merge` | `self, old_name, new_name` | `` | Block merge if both old and new items have website items against them.
This is to avoid duplicate website items after merging. |
| `after_rename` | `self, old_name, new_name, merge` | `` |  |





## Functions

### `invalidate_cache_for_item`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Invalidate Item Group cache and rebuild ItemVariantsCacheManager.
```

