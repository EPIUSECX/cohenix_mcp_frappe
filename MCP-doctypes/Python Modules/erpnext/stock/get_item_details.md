# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/get_item_details.py`

## Classes

No classes found in this file.


## Functions

### `_preprocess_ctx`
**Arguments:** `ctx`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_details`
**Arguments:** `ctx, doc, for_validate, overwrite_warehouse`
**Decorators:** ``

**Docstring:**
```
ctx = {
        "item_code": "",
        "warehouse": None,
        "customer": "",
        "conversion_rate": 1.0,
        "selling_price_list": None,
        "price_list_currency": None,
        "plc_conversion_rate": 1.0,
        "doctype": "",
        "name": "",
        "supplier": None,
        "transaction_date": None,
        "conversion_rate": 1.0,
        "buying_price_list": None,
        "is_subcontracted": 0/1,
        "ignore_pricing_rule": 0/1
        "project": ""
        "set_warehouse": ""
}
```
### `remove_standard_fields`
**Arguments:** `out`
**Decorators:** ``

**Docstring:**
```

```
### `set_valuation_rate`
**Arguments:** `out, ctx`
**Decorators:** ``

**Docstring:**
```

```
### `update_stock`
**Arguments:** `ctx, out, doc`
**Decorators:** ``

**Docstring:**
```

```
### `has_incorrect_serial_nos`
**Arguments:** `ctx, out`
**Decorators:** ``

**Docstring:**
```

```
### `filter_batches`
**Arguments:** `batches, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_filtered_serial_nos`
**Arguments:** `serial_nos, doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_bin_details`
**Arguments:** `ctx, out, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_code`
**Arguments:** `barcode, serial_no`
**Decorators:** ``

**Docstring:**
```

```
### `validate_item_details`
**Arguments:** `ctx, item`
**Decorators:** ``

**Docstring:**
```

```
### `get_basic_details`
**Arguments:** `ctx, item, overwrite_warehouse`
**Decorators:** ``

**Docstring:**
```
:param ctx: {
                "item_code": "",
                "warehouse": None,
                "customer": "",
                "conversion_rate": 1.0,
                "selling_price_list": None,
                "price_list_currency": None,
                "price_list_uom_dependant": None,
                "plc_conversion_rate": 1.0,
                "doctype": "",
                "name": "",
                "supplier": None,
                "transaction_date": None,
                "conversion_rate": 1.0,
                "buying_price_list": None,
                "is_subcontracted": 0/1,
                "ignore_pricing_rule": 0/1
                "project": "",
                barcode: "",
                serial_no: "",
                currency: "",
                update_stock: "",
                price_list: "",
                company: "",
                order_type: "",
                is_pos: "",
                project: "",
                qty: "",
                stock_qty: "",
                conversion_factor: "",
                against_blanket_order: 0/1
        }
:param item: `item_code` of Item object
:return: frappe._dict
```
### `get_item_warehouse_`
**Arguments:** `ctx, item, overwrite_warehouse, defaults`
**Decorators:** ``

**Docstring:**
```

```
### `update_barcode_value`
**Arguments:** `out`
**Decorators:** ``

**Docstring:**
```

```
### `get_barcode_data`
**Arguments:** `items_list, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_tax_info`
**Arguments:** `doc, tax_category, item_codes, item_rates, item_tax_templates`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_tax_template`
**Arguments:** `ctx, item, out`
**Decorators:** ``

**Docstring:**
```
Determines item_tax template from item or parent item groups.

Accesses:
        ctx = {
        "child_doctype": str
        }
Passes:
        ctx = {
                "company": str
                "bill_date": str
                "transaction_date": str
        "tax_category": None
        "item_tax_template": None
        "base_net_rate": float
        }
```
### `_get_item_tax_template`
**Arguments:** `ctx, taxes, out, for_validate`
**Decorators:** ``

**Docstring:**
```
Accesses:
        ctx = {
                "company": str
                "bill_date": str
                "transaction_date": str
        "tax_category": None
        "item_tax_template": None
        }
Passes:
        ctx = {
        "base_net_rate": float
        }
```
### `is_within_valid_range`
**Arguments:** `ctx, tax`
**Decorators:** ``

**Docstring:**
```
Accesses:
        ctx = {
        "base_net_rate": float
        }
```
### `get_item_tax_map`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `calculate_service_end_date`
**Arguments:** `ctx, item`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_income_account`
**Arguments:** `ctx, item, item_group, brand`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_expense_account`
**Arguments:** `ctx, item, item_group, brand`
**Decorators:** ``

**Docstring:**
```

```
### `get_provisional_account`
**Arguments:** `ctx, item, item_group, brand`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_discount_account`
**Arguments:** `ctx, item, item_group, brand`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_deferred_account`
**Arguments:** `ctx, item, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_cost_center`
**Arguments:** `ctx, item, item_group, brand, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_supplier`
**Arguments:** `_ctx, item, item_group, brand`
**Decorators:** ``

**Docstring:**
```

```
### `get_price_list_rate`
**Arguments:** `ctx, item_doc, out`
**Decorators:** ``

**Docstring:**
```

```
### `insert_item_price`
**Arguments:** `ctx`
**Decorators:** ``

**Docstring:**
```
Insert Item Price if Price List and Price List Rate are specified and currency is the same
```
### `_get_stock_uom_rate`
**Arguments:** `rate, ctx`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_price`
**Arguments:** `pctx, item_code, ignore_party, force_batch_no`
**Decorators:** ``

**Docstring:**
```
Get name, price_list_rate from Item Price based on conditions
        Check if the desired qty is within the increment of the packing list.
:param pctx: dict (or frappe._dict) with mandatory fields price_list, uom
        optional fields transaction_date, customer, supplier
:param item_code: str, Item Doctype field item_code
```
### `get_batch_based_item_price`
**Arguments:** `pctx, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_price_list_rate_for`
**Arguments:** `ctx, item_code`
**Decorators:** ``

**Docstring:**
```
:param customer: link to Customer DocType
:param supplier: link to Supplier DocType
:param price_list: str (Standard Buying or Standard Selling)
:param item_code: str, Item Doctype field item_code
:param qty: Desired Qty
:param transaction_date: Date of the price
```
### `check_packing_list`
**Arguments:** `price_list_rate_name, desired_qty, item_code`
**Decorators:** ``

**Docstring:**
```
Check if the desired qty is within the increment of the packing list.
:param price_list_rate_name: Name of Item Price
:param desired_qty: Desired Qt
:param item_code: str, Item Doctype field item_code
:param qty: Desired Qt
```
### `validate_conversion_rate`
**Arguments:** `ctx, meta`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_item_code`
**Arguments:** `ctx, item_doc, out`
**Decorators:** ``

**Docstring:**
```

```
### `get_pos_profile_item_details_`
**Arguments:** `ctx, company, pos_profile, update_data`
**Decorators:** ``

**Docstring:**
```

```
### `get_pos_profile`
**Arguments:** `company, pos_profile, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_conversion_factor`
**Arguments:** `item_code, uom`
**Decorators:** ``

**Docstring:**
```

```
### `get_projected_qty`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_bin_details`
**Arguments:** `item_code, warehouse, company, include_child_warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `get_company_total_stock`
**Arguments:** `item_code, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_batch_qty`
**Arguments:** `batch_no, warehouse, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `apply_price_list`
**Arguments:** `ctx, as_doc, doc`
**Decorators:** ``

**Docstring:**
```
Apply pricelist on a document-like dict object and return as
{'parent': dict, 'children': list}

:param ctx: See below
:param as_doc: Updates value in the passed dict

        ctx = {
                "doctype": "",
                "name": "",
                "items": [{"doctype": "", "name": "", "item_code": "", "brand": "", "item_group": ""}, ...],
                "conversion_rate": 1.0,
                "selling_price_list": None,
                "price_list_currency": None,
                "price_list_uom_dependant": None,
                "plc_conversion_rate": 1.0,
                "doctype": "",
                "name": "",
                "supplier": None,
                "transaction_date": None,
                "conversion_rate": 1.0,
                "buying_price_list": None,
                "ignore_pricing_rule": 0/1
        }
```
### `apply_price_list_on_item`
**Arguments:** `ctx, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_price_list_currency_and_exchange_rate`
**Arguments:** `ctx`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_bom`
**Arguments:** `item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_valuation_rate`
**Arguments:** `item_code, company, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_gross_profit`
**Arguments:** `out`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_no`
**Arguments:** `_args, serial_nos, sales_order`
**Decorators:** ``

**Docstring:**
```

```
### `update_party_blanket_order`
**Arguments:** `ctx, out`
**Decorators:** ``

**Docstring:**
```

```
### `get_blanket_order_details`
**Arguments:** `ctx`
**Decorators:** ``

**Docstring:**
```

```

