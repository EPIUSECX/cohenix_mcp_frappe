# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/subcontracting/doctype/subcontracting_receipt/subcontracting_receipt.py`

## Classes

### `SubcontractingReceipt`
**Inherits:** `SubcontractingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `reset_raw_materials` | `self` | `` |  |
| `validate_closed_subcontracting_order` | `self` | `` |  |
| `update_job_card` | `self` | `` |  |
| `get_manufactured_qty` | `self, job_card` | `` |  |
| `validate_items_qty` | `self` | `` |  |
| `set_items_bom` | `self` | `` |  |
| `set_items_cost_center` | `self` | `` |  |
| `set_supplied_items_cost_center` | `self` | `` |  |
| `set_items_expense_account` | `self` | `` |  |
| `set_supplied_items_expense_account` | `self` | `` |  |
| `reset_supplied_items` | `self` | `` |  |
| `get_scrap_items` | `self, recalculate_rate` | `` |  |
| `remove_scrap_items` | `self, recalculate_rate` | `` |  |
| `set_missing_values` | `self` | `` |  |
| `set_available_qty_for_consumption` | `self` | `` |  |
| `calculate_items_qty_and_amount` | `self` | `` |  |
| `validate_scrap_items` | `self` | `` |  |
| `validate_accepted_warehouse` | `self` | `` |  |
| `validate_available_qty_for_consumption` | `self` | `` |  |
| `update_status_updater_args` | `self` | `` |  |
| `update_status` | `self, status, update_modified` | `` |  |
| `get_gl_entries` | `self, warehouse_account` | `` |  |
| `make_item_gl_entries` | `self, gl_entries, warehouse_account` | `` |  |
| `make_item_gl_entries_for_lcv` | `self, gl_entries, warehouse_account` | `` |  |
| `auto_create_purchase_receipt` | `self` | `` |  |





## Functions

### `make_subcontract_return`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_purchase_receipt`
**Arguments:** `source_name, target_doc, save, submit, notify`
**Decorators:** ``

**Docstring:**
```

```
### `add_po_items_to_pr`
**Arguments:** `scr_doc, target_doc`
**Decorators:** ``

**Docstring:**
```

```

