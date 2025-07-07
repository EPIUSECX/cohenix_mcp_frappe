# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/packed_item/packed_item.py`

## Classes

### `PackedItem`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `set_actual_and_projected_qty` | `self` | `` | Set actual and projected qty based on warehouse and item_code |





## Functions

### `make_packing_list`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Make/Update packing list for Product Bundle Item.
```
### `is_product_bundle`
**Arguments:** `item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_indexed_packed_items_table`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Create dict from stale packed items table like:
{(Parent Item 1, Bundle Item 1, ae4b5678): {...}, (key): {value}}

Use: to quickly retrieve/check if row existed in table instead of looping n times
```
### `reset_packing_list`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Conditionally reset the table and return if it was reset or not.
```
### `get_product_bundle_items`
**Arguments:** `item_code`
**Decorators:** ``

**Docstring:**
```

```
### `add_packed_item_row`
**Arguments:** `doc, packing_item, main_item_row, packed_items_table, reset`
**Decorators:** ``

**Docstring:**
```
Add and return packed item row.
doc: Transaction document
packing_item (dict): Packed Item details
main_item_row (dict): Items table row corresponding to packed item
packed_items_table (dict): Packed Items table before save (indexed)
reset (bool): State if table is reset or preserved as is
```
### `get_packed_item_details`
**Arguments:** `item_code, company`
**Decorators:** ``

**Docstring:**
```

```
### `update_packed_item_basic_data`
**Arguments:** `main_item_row, pi_row, packing_item, item_data`
**Decorators:** ``

**Docstring:**
```

```
### `update_packed_item_stock_data`
**Arguments:** `main_item_row, pi_row, packing_item, item_data, doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_packed_item_with_pick_list_info`
**Arguments:** `main_item_row, pi_row`
**Decorators:** ``

**Docstring:**
```

```
### `update_packed_item_price_data`
**Arguments:** `pi_row, item_data, doc`
**Decorators:** ``

**Docstring:**
```
Set price as per price list or from the Item master.
```
### `update_packed_item_from_cancelled_doc`
**Arguments:** `main_item_row, packing_item, pi_row, doc`
**Decorators:** ``

**Docstring:**
```
Update packed item row details from cancelled doc into amended doc.
```
### `get_packed_item_bin_qty`
**Arguments:** `item, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_cancelled_doc_packed_item_details`
**Arguments:** `old_packed_items`
**Decorators:** ``

**Docstring:**
```

```
### `update_product_bundle_rate`
**Arguments:** `parent_items_price, pi_row, item_row`
**Decorators:** ``

**Docstring:**
```
Update the price dict of Product Bundles based on the rates of the Items in the bundle.

Stucture:
{(Bundle Item 1, ae56fgji): 150.0, (Bundle Item 2, bc78fkjo): 200.0}
```
### `set_product_bundle_rate_amount`
**Arguments:** `doc, parent_items_price`
**Decorators:** ``

**Docstring:**
```
Set cumulative rate and amount in bundle item.
```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_items_from_product_bundle`
**Arguments:** `row`
**Decorators:** ``

**Docstring:**
```

```

