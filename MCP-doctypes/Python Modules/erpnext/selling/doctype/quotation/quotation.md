# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/quotation/quotation.py`

## Classes

### `Quotation`
**Inherits:** `SellingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `set_indicator` | `self` | `` |  |
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `validate_valid_till` | `self` | `` |  |
| `set_has_alternative_item` | `self` | `` | Mark 'Has Alternative Item' for rows. |
| `set_has_unit_price_items` | `self` | `` | If permitted in settings and any item has 0 qty, the SO has unit price items. |
| `get_ordered_status` | `self` | `` |  |
| `get_valid_items` | `self` | `` | Filters out items in an alternatives set that were not ordered. |
| `is_fully_ordered` | `self` | `` |  |
| `is_partially_ordered` | `self` | `` |  |
| `update_lead` | `self` | `` |  |
| `set_customer_name` | `self` | `` |  |
| `update_opportunity` | `self, status` | `` |  |
| `update_opportunity_status` | `self, status, opportunity` | `` |  |
| `declare_enquiry_lost` | `self, lost_reasons_list, competitors, detailed_reason` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `print_other_charges` | `self, docname` | `` |  |
| `on_recurring` | `self, reference_doc, auto_repeat_doc` | `` |  |
| `get_rows_with_alternatives` | `self` | `` |  |





## Functions

### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `make_sales_order`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `_make_sales_order`
**Arguments:** `source_name, target_doc, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `set_expired_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_sales_invoice`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `_make_sales_invoice`
**Arguments:** `source_name, target_doc, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `_make_customer`
**Arguments:** `source_name, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `create_customer_from_lead`
**Arguments:** `lead_name, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `create_customer_from_prospect`
**Arguments:** `prospect_name, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `handle_mandatory_error`
**Arguments:** `e, customer, lead_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_ordered_items`
**Arguments:** `quotation`
**Decorators:** ``

**Docstring:**
```
Returns a dict of ordered items with their total qty based on quotation row name.

In `Sales Order Item`, `quotation_item` is the row name of `Quotation Item`.

Example:
```
{
    "refsdjhd2": 10,
    "ygdhdshrt": 5,
}
```
```

