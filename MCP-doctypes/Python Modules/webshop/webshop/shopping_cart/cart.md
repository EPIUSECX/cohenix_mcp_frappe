# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/shopping_cart/cart.py`

## Classes

### `WebsitePriceListMissingError`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `set_cart_count`
**Arguments:** `quotation`
**Decorators:** ``

**Docstring:**
```

```
### `get_cart_quotation`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_shipping_addresses`
**Arguments:** `party`
**Decorators:** ``

**Docstring:**
```

```
### `get_billing_addresses`
**Arguments:** `party`
**Decorators:** ``

**Docstring:**
```

```
### `place_order`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `request_for_quotation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_cart`
**Arguments:** `item_code, qty, additional_notes, with_items`
**Decorators:** ``

**Docstring:**
```

```
### `get_shopping_cart_menu`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `add_new_address`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `create_lead_for_item_inquiry`
**Arguments:** `lead, subject, message`
**Decorators:** ``

**Docstring:**
```

```
### `get_terms_and_conditions`
**Arguments:** `terms_name`
**Decorators:** ``

**Docstring:**
```

```
### `update_cart_address`
**Arguments:** `address_type, address_name`
**Decorators:** ``

**Docstring:**
```

```
### `guess_territory`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `decorate_quotation_doc`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `_get_cart_quotation`
**Arguments:** `party`
**Decorators:** ``

**Docstring:**
```
Return the open Quotation of type "Shopping Cart" or make a new one
```
### `update_party`
**Arguments:** `fullname, company_name, mobile_no, phone`
**Decorators:** ``

**Docstring:**
```

```
### `apply_cart_settings`
**Arguments:** `party, quotation`
**Decorators:** ``

**Docstring:**
```

```
### `set_price_list_and_rate`
**Arguments:** `quotation, cart_settings`
**Decorators:** ``

**Docstring:**
```
set price list based on billing territory
```
### `_set_price_list`
**Arguments:** `cart_settings, quotation`
**Decorators:** ``

**Docstring:**
```
Set price list based on customer or shopping cart default
```
### `set_taxes`
**Arguments:** `quotation, cart_settings`
**Decorators:** ``

**Docstring:**
```
set taxes based on billing territory
```
### `get_party`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_debtors_account`
**Arguments:** `cart_settings`
**Decorators:** ``

**Docstring:**
```

```
### `get_address_docs`
**Arguments:** `doctype, txt, filters, limit_start, limit_page_length, party`
**Decorators:** ``

**Docstring:**
```

```
### `apply_shipping_rule`
**Arguments:** `shipping_rule`
**Decorators:** ``

**Docstring:**
```

```
### `_apply_shipping_rule`
**Arguments:** `party, quotation, cart_settings`
**Decorators:** ``

**Docstring:**
```

```
### `get_applicable_shipping_rules`
**Arguments:** `party, quotation`
**Decorators:** ``

**Docstring:**
```

```
### `get_shipping_rules`
**Arguments:** `quotation, cart_settings`
**Decorators:** ``

**Docstring:**
```

```
### `get_address_territory`
**Arguments:** `address_name`
**Decorators:** ``

**Docstring:**
```
Tries to match city, state and country of address to existing territory
```
### `show_terms`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `apply_coupon_code`
**Arguments:** `applied_code, applied_referral_sales_partner`
**Decorators:** ``

**Docstring:**
```

```
### `remove_coupon_code`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

