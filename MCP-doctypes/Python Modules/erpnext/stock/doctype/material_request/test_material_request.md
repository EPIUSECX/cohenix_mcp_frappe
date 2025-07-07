# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/material_request/test_material_request.py`

## Classes

### `TestMaterialRequest`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_material_request_qty` | `self` | `` |  |
| `test_make_purchase_order` | `self` | `` |  |
| `test_make_subcontracted_purchase_order` | `self` | `` |  |
| `test_make_supplier_quotation` | `self` | `` |  |
| `test_make_stock_entry` | `self` | `` |  |
| `test_partial_make_stock_entry` | `self` | `` |  |
| `test_in_transit_make_stock_entry` | `self` | `` |  |
| `_insert_stock_entry` | `self, qty1, qty2, warehouse` | `` |  |
| `test_cannot_stop_cancelled_material_request` | `self` | `` |  |
| `test_mr_changes_from_stopped_to_pending_after_reopen` | `self` | `` |  |
| `test_cannot_submit_cancelled_mr` | `self` | `` |  |
| `test_mr_changes_from_pending_to_cancelled_after_cancel` | `self` | `` |  |
| `test_cannot_change_cancelled_mr` | `self` | `` |  |
| `test_cannot_submit_deleted_material_request` | `self` | `` |  |
| `test_cannot_delete_submitted_mr` | `self` | `` |  |
| `test_stopped_mr_changes_to_pending_after_reopen` | `self` | `` |  |
| `test_pending_mr_changes_to_stopped_after_stop` | `self` | `` |  |
| `test_cannot_stop_unsubmitted_mr` | `self` | `` |  |
| `test_completed_qty_for_purchase` | `self` | `` |  |
| `test_completed_qty_for_transfer` | `self` | `` |  |
| `test_over_transfer_qty_allowance` | `self` | `` |  |
| `test_completed_qty_for_over_transfer` | `self` | `` |  |
| `test_incorrect_mapping_of_stock_entry` | `self` | `` |  |
| `test_warehouse_company_validation` | `self` | `` |  |
| `_get_requested_qty` | `self, item_code, warehouse` | `` |  |
| `test_make_stock_entry_for_material_issue` | `self` | `` |  |
| `test_completed_qty_for_issue` | `self` | `` |  |
| `test_material_request_type_manufacture` | `self` | `` |  |
| `test_requested_qty_multi_uom` | `self` | `` |  |
| `test_multi_uom_for_purchase` | `self` | `` |  |
| `test_customer_provided_parts_mr` | `self` | `` |  |
| `test_auto_email_users_with_company_user_permissions` | `self` | `` |  |





## Functions

### `get_in_transit_warehouse`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `make_material_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

