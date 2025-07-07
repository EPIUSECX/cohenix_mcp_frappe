# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_settings/stock_settings.py`

## Classes

### `StockSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_warehouses` | `self` | `` |  |
| `cant_change_valuation_method` | `self` | `` |  |
| `validate_clean_description_html` | `self` | `` |  |
| `validate_pending_reposts` | `self` | `` |  |
| `validate_stock_reservation` | `self` | `` | Raises an exception if the user tries to enable/disable `Stock Reservation` with `Negative Stock` or `Open Stock Reservation Entries`. |
| `on_update` | `self` | `` |  |
| `change_precision_for_for_sales` | `self` | `` |  |
| `change_precision_for_purchase` | `self` | `` |  |
| `make_property_setter_for_precision` | `doctypes` | `staticmethod` |  |
| `toggle_warehouse_field_for_inter_warehouse_transfer` | `self` | `` |  |





## Functions

### `clean_all_descriptions`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_enable_stock_uom_editing`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

