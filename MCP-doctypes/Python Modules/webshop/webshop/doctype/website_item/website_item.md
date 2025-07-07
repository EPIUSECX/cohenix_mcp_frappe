# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/doctype/website_item/website_item.py`

## Classes

### `WebsiteItem`
**Inherits:** `WebsiteGenerator`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate_duplicate_website_item` | `self` | `` |  |
| `publish_unpublish_desk_item` | `self, publish` | `` |  |
| `make_route` | `self` | `` | Called from set_route in WebsiteGenerator. |
| `update_template_item` | `self` | `` | Publish Template Item if Variant is published. |
| `validate_website_image` | `self` | `` |  |
| `make_thumbnail` | `self` | `` | Make a thumbnail of `website_image` |
| `get_context` | `self, context` | `` |  |
| `set_selected_attributes` | `self, variants, context, attribute_values_available` | `` |  |
| `set_attribute_values` | `self, attributes, context, attribute_values_available` | `` |  |
| `set_metatags` | `self, context` | `` |  |
| `set_shopping_cart_data` | `self, context` | `` |  |
| `copy_specification_from_item_group` | `self` | `` |  |
| `get_product_details_section` | `self, context` | `` | Get section with tabs or website specifications. |
| `get_tabs` | `self` | `` |  |
| `get_recommended_items` | `self, settings` | `` |  |





## Functions

### `invalidate_item_variants_cache_for_website`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Rebuild ItemVariantsCacheManager via Item or Website Item

Args:
        doc (Item): item of which cache should be cleared
```
### `invalidate_cache_for_web_item`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Invalidate Website Item Group cache and rebuild ItemVariantsCacheManager
Args:
        doc (Item): document against which cache should be cleared
```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `check_if_user_is_customer`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `make_website_item`
**Arguments:** `doc, save`
**Decorators:** ``

**Docstring:**
```
Make Website Item from Item. Used via Form UI or patch.
```
### `has_website_permission_for_website_item`
**Arguments:** `doc, ptype, user, verbose`
**Decorators:** ``

**Docstring:**
```

```
### `has_website_permission_for_item_group`
**Arguments:** `doc, ptype, user, verbose`
**Decorators:** ``

**Docstring:**
```

```

