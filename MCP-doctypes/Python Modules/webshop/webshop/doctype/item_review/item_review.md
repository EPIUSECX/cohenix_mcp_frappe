# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/doctype/item_review/item_review.py`

## Classes

### `UnverifiedReviewer`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ItemReview`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `after_insert` | `self` | `` |  |
| `after_delete` | `self` | `` |  |





## Functions

### `get_item_reviews`
**Arguments:** `web_item, start, end, data`
**Decorators:** ``

**Docstring:**
```
Get Website Item Review Data.
```
### `get_queried_reviews`
**Arguments:** `web_item, start, end, data`
**Decorators:** ``

**Docstring:**
```
Query Website Item wise reviews and cache if needed.
Cache stores only first page of reviews i.e. 10 reviews maximum.
Returns:
        dict: Containing reviews, average ratings, % of reviews per rating and total reviews.
```
### `set_reviews_in_cache`
**Arguments:** `web_item, reviews_dict`
**Decorators:** ``

**Docstring:**
```

```
### `add_item_review`
**Arguments:** `web_item, title, rating, comment`
**Decorators:** ``

**Docstring:**
```
Add an Item Review by a user if non-existent.
```
### `get_customer`
**Arguments:** `silent`
**Decorators:** ``

**Docstring:**
```
silent: Return customer if exists else return nothing. Dont throw error.
```

