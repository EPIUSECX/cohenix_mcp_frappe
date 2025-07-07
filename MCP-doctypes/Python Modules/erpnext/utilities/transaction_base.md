# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/utilities/transaction_base.py`

## Classes

### `UOMMustBeIntegerError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `TransactionBase`
**Inherits:** `StatusUpdater`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate_posting_time` | `self` | `` |  |
| `validate_uom_is_integer` | `self, uom_field, qty_fields, child_dt` | `` |  |
| `validate_with_previous_doc` | `self, ref` | `` |  |
| `compare_values` | `self, ref_doc, fields, doc` | `` |  |
| `get_prev_doc_reference_details` | `self, reference_names, reference_doctype, fields` | `` |  |
| `validate_rate_with_reference_doc` | `self, ref_details` | `` |  |
| `get_reference_details` | `self, reference_names, reference_doctype` | `` |  |
| `get_link_filters` | `self, for_doctype` | `` |  |
| `reset_default_field_value` | `self, default_field, child_table, child_table_field` | `` | Reset "Set default X" fields on forms to avoid confusion.

example:
        doc = {
                "set_from_warehouse": "Warehouse A",
                "items": [{"from_warehouse": "warehouse B"}, {"from_warehouse": "warehouse A"}],
        }
        Since this has dissimilar values in child table, the default field will be erased.

        doc.reset_default_field_value("set_from_warehouse", "items", "from_warehouse") |
| `validate_currency_for_receivable_payable_and_advance_account` | `self` | `` |  |
| `fetch_item_details` | `self, item` | `` |  |
| `process_item_selection` | `self, item_idx` | `` |  |
| `set_fetched_values` | `self, item_obj, item_details` | `` |  |
| `handle_internal_parties` | `self, item_obj, item_details` | `` |  |
| `add_taxes_from_item_template` | `self, item_obj, item_details` | `` |  |
| `set_rate_based_on_price_list` | `self, item_obj, item_details` | `` |  |
| `copy_from_first_row` | `self, row, fields` | `` |  |
| `add_free_item` | `self, item_obj, item_details` | `` |  |
| `conversion_factor` | `self, item_obj, item_details` | `` |  |
| `calculate_stock_uom_rate` | `self, item_obj` | `` |  |
| `set_item_rate_and_discounts` | `self, item_obj, item_details` | `` |  |
| `calculate_net_weight` | `self` | `` |  |
| `_apply_price_list` | `self, item_obj, reset_plc_conversion` | `` |  |





## Functions

### `delete_events`
**Arguments:** `ref_type, ref_name`
**Decorators:** ``

**Docstring:**
```

```
### `validate_uom_is_integer`
**Arguments:** `doc, uom_field, qty_fields, child_dt`
**Decorators:** ``

**Docstring:**
```

```

