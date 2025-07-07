# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/utils/product.py`

## Classes

No classes found in this file.


## Functions

### `get_web_item_qty_in_stock`
**Arguments:** `item_code, item_warehouse_field, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `adjust_qty_for_expired_items`
**Arguments:** `item_code, stock_qty, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_expired_batches`
**Arguments:** `batches`
**Decorators:** ``

**Docstring:**
```
:param batches: A list of dict in the form [{'expiry_date': datetime.date(20XX, 1, 1), 'name': 'batch_id'}, ...]
```
### `qty_from_all_warehouses`
**Arguments:** `batch_info`
**Decorators:** ``

**Docstring:**
```
:param batch_info: A list of dict in the form [{u'warehouse': u'Stores - I', u'qty': 0.8}, ...]
```
### `get_non_stock_item_status`
**Arguments:** `item_code, item_warehouse_field`
**Decorators:** ``

**Docstring:**
```

```

