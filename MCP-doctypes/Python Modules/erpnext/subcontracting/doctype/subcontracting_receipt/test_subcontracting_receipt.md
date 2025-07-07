# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/subcontracting/doctype/subcontracting_receipt/test_subcontracting_receipt.py`

## Classes

### `TestSubcontractingReceipt`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_subcontracting` | `self` | `` |  |
| `test_available_qty_for_consumption` | `self` | `` |  |
| `test_subcontracting_gle_fg_item_rate_zero` | `self` | `` |  |
| `test_subcontracting_over_receipt` | `self` | `` | Behaviour: Raise multiple SCRs against one SCO that in total
        receive more than the required qty in the SCO.
Expected Result: Error Raised for Over Receipt against SCO. |
| `test_subcontracting_receipt_partial_return` | `self` | `` |  |
| `test_subcontracting_receipt_over_return` | `self` | `` |  |
| `test_subcontracting_receipt_no_gl_entry` | `self` | `` |  |
| `test_subcontracting_receipt_gl_entry` | `self` | `` |  |
| `test_subcontracting_receipt_gl_entry_with_different_rm_expense_accounts` | `self` | `` |  |
| `test_subcontracting_receipt_with_zero_service_cost` | `self` | `` |  |
| `test_supplied_items_consumed_qty` | `self` | `` |  |
| `test_supplied_items_cost_after_reposting` | `self` | `` |  |
| `test_subcontracting_receipt_for_batch_raw_materials_without_material_transfer` | `self` | `` |  |
| `test_subcontracting_receipt_valuation_with_auto_created_serial_batch_bundle` | `self` | `` |  |
| `test_subcontracting_receipt_valuation_for_fg_with_auto_created_serial_batch_bundle` | `self` | `` |  |
| `test_subcontracting_receipt_raw_material_rate` | `self` | `` |  |
| `test_quality_inspection_for_subcontracting_receipt` | `self` | `` |  |
| `test_scrap_items_for_subcontracting_receipt` | `self` | `` |  |
| `test_subcontracting_receipt_cancel_with_batch` | `self` | `` |  |
| `test_auto_create_purchase_receipt` | `self` | `` |  |
| `test_auto_create_purchase_receipt_with_no_reference_of_po_item` | `self` | `` |  |
| `test_use_serial_batch_fields_for_subcontracting_receipt` | `self` | `` |  |
| `test_use_serial_batch_fields_for_subcontracting_receipt_with_rejected_qty` | `self` | `` |  |
| `test_subcontracting_receipt_for_batch_materials_without_use_serial_batch_fields` | `self` | `` |  |
| `test_change_batch_for_raw_materials` | `self` | `` |  |





## Functions

### `make_return_subcontracting_receipt`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

