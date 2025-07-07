# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/report/gross_profit/gross_profit.py`

## Classes

### `GrossProfitGenerator`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, filters` | `` |  |
| `process` | `self` | `` |  |
| `update_return_invoices` | `self, row` | `` |  |
| `get_average_rate_based_on_group_by` | `self` | `` |  |
| `set_average_based_on_payment_term_portion` | `self, new_row, row, invoice_portion, aggr` | `` |  |
| `is_not_invoice_row` | `self, row` | `` |  |
| `set_average_rate` | `self, new_row` | `` |  |
| `set_average_gross_profit` | `self, new_row` | `` |  |
| `get_returned_invoice_items` | `self` | `` |  |
| `skip_row` | `self, row` | `` |  |
| `get_buying_amount_from_product_bundle` | `self, row, product_bundle` | `` |  |
| `calculate_buying_amount_from_sle` | `self, row, my_sle, parenttype, parent, item_row, item_code` | `` |  |
| `get_buying_amount` | `self, row, item_code` | `` |  |
| `get_buying_amount_from_so_dn` | `self, sales_order, so_detail, item_code` | `` |  |
| `get_average_buying_rate` | `self, row, item_code` | `` |  |
| `get_last_purchase_rate` | `self, item_code, row` | `` |  |
| `load_invoice_items` | `self` | `` |  |
| `get_delivery_notes` | `self` | `` |  |
| `group_items_by_invoice` | `self` | `` | Turns list of Sales Invoice Items to a tree of Sales Invoices with their Items as children. |
| `get_invoice_row` | `self, row` | `` |  |
| `get_bundle_item_row` | `self, row, item` | `` |  |
| `get_stock_ledger_entries` | `self, item_code, warehouse` | `` |  |
| `load_product_bundle` | `self` | `` |  |
| `load_non_stock_items` | `self` | `` |  |





## Functions

### `execute`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_data_when_grouped_by_invoice`
**Arguments:** `columns, gross_profit_data, filters, group_wise_columns, data`
**Decorators:** ``

**Docstring:**
```

```
### `get_data_when_not_grouped_by_invoice`
**Arguments:** `gross_profit_data, filters, group_wise_columns, data`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns`
**Arguments:** `group_wise_columns, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_column_names`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

