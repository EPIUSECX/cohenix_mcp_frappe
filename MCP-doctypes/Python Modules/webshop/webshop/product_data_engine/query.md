# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/product_data_engine/query.py`

## Classes

### `ProductQuery`


**Docstring:**
```
Query engine for product listing

Attributes:
        fields (list): Fields to fetch in query
        conditions (string): Conditions for query building
        or_conditions (string): Search conditions
        page_length (Int): Length of page for the query
        settings (Document): Webshop Settings DocType
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `query` | `self, attributes, fields, search_term, start, item_group` | `` | Args:
        attributes (dict, optional): Item Attribute filters
        fields (dict, optional): Field level filters
        search_term (str, optional): Search term to lookup
        start (int, optional): Page start

Returns:
        dict: Dict containing items, item count & discount range |
| `query_items` | `self, start` | `` | Build a query to fetch Website Items based on field filters. |
| `query_items_with_attributes` | `self, attributes, start` | `` | Build a query to fetch Website Items based on field & attribute filters. |
| `build_fields_filters` | `self, filters` | `` | Build filters for field values

Args:
        filters (dict): Filters |
| `build_item_group_filters` | `self, item_group` | `` | Add filters for Item group page and include Website Item Groups. |
| `build_search_filters` | `self, search_term` | `` | Query search term in specified fields

Args:
        search_term (str): Search candidate |
| `add_display_details` | `self, result, discount_list, cart_items` | `` | Add price and availability details in result. |
| `get_price_discount_info` | `self, item, price_object, discount_list` | `` | Modify item object and add price details. |
| `get_stock_availability` | `self, item` | `` | Modify item object and add stock details. |
| `get_cart_items` | `self` | `` |  |
| `filter_results_by_discount` | `self, fields, result` | `` |  |





## Functions

No top-level functions found in this file.
