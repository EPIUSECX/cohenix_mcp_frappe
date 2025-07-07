# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/doctype/webshop_settings/webshop_settings.py`

## Classes

### `ShoppingCartSetupError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `WebshopSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `after_save` | `self` | `` |  |
| `create_redisearch_indexes` | `self` | `` |  |
| `validate_field_filters` | `filter_fields, enable_field_filters` | `staticmethod` |  |
| `validate_attribute_filters` | `self` | `` |  |
| `validate_checkout` | `self` | `` |  |
| `validate_search_index_fields` | `self` | `` |  |
| `validate_price_list_exchange_rate` | `self` | `` | Check if exchange rate exists for Price List currency (to Company's currency). |
| `validate_tax_rule` | `self` | `` |  |
| `get_tax_master` | `self, billing_territory` | `` |  |
| `get_shipping_rules` | `self, shipping_territory` | `` |  |
| `on_change` | `self` | `` |  |





## Functions

### `validate_cart_settings`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```

```
### `get_shopping_cart_settings`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_cart_enabled`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `show_quantity_in_website`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `check_shopping_cart_enabled`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `show_attachments`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

