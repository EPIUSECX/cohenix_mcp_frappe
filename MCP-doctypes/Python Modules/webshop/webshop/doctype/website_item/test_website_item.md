# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/doctype/website_item/test_website_item.py`

## Classes

### `TestWebsiteItem`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `test_index_creation` | `self` | `` | Check if index is getting created in db. |
| `test_website_item_desk_item_sync` | `self` | `` | Check creation/updation/deletion of Website Item and its impact on Item master. |
| `test_publish_variant_and_template` | `self` | `` | Check if template is published on publishing variant. |
| `test_impact_on_merging_items` | `self` | `` | Check if merging items is blocked if old and new items both have website items |
| `test_website_item_breadcrumbs` | `self` | `` | Check if breadcrumbs include homepage, product listing navigation page, parent item group(s) and item group. |
| `test_website_item_price_for_logged_in_user` | `self` | `` | Check if price details are fetched correctly while logged in. |
| `test_website_item_price_for_guest_user` | `self` | `` | Check if price details are fetched correctly for guest user. |
| `test_website_item_stock_when_out_of_stock` | `self` | `` | Check if stock details are fetched correctly for empty inventory when:
1) Showing stock availability enabled:
        - Warehouse unset
        - Warehouse set
2) Showing stock availability disabled |
| `test_website_item_stock_when_in_stock` | `self` | `` | Check if stock details are fetched correctly for available inventory when:
1) Showing stock availability enabled:
        - Warehouse set
        - Warehouse unset
2) Showing stock availability disabled |
| `test_recommended_item` | `self` | `` | Check if added recommended items are fetched correctly. |
| `test_recommended_item_for_guest_user` | `self` | `` | Check if added recommended items are fetched correctly for guest user. |





## Functions

### `create_regular_web_item`
**Arguments:** `item_code, item_args, web_args`
**Decorators:** ``

**Docstring:**
```
Create Regular Item and Website Item.
```
### `make_web_item_price`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_web_pricing_rule`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_user_and_customer_if_not_exists`
**Arguments:** `email, first_name`
**Decorators:** ``

**Docstring:**
```

```

