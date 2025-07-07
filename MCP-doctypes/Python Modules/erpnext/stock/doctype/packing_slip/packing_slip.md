# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/packing_slip/packing_slip.py`

## Classes

### `PackingSlip`
**Inherits:** `StatusUpdater`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate_delivery_note` | `self` | `` | Raises an exception if the `Delivery Note` status is not Draft |
| `validate_case_nos` | `self` | `` | Validate if case nos overlap. If they do, recommend next case no. |
| `validate_items` | `self` | `` |  |
| `set_missing_values` | `self` | `` |  |
| `get_recommended_case_no` | `self` | `` | Returns the next case no. for a new packing slip for a delivery note |
| `calculate_net_total_pkg` | `self` | `` |  |





## Functions

### `item_details`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```

