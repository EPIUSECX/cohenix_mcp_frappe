# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/tests/test_subcontracting_controller.py`

## Classes

### `TestSubcontractingController`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_remove_empty_rows` | `self` | `` |  |
| `test_calculate_additional_costs` | `self` | `` |  |
| `test_create_raw_materials_supplied` | `self` | `` |  |
| `test_sco_with_bom` | `self` | `` | - Set backflush based on BOM.
- Create SCO for the item Subcontracted Item SA1 and add same item two times.
- Transfer the components from Stores to Supplier warehouse with batch no and serial nos.
- Create SCR against the SCO and check serial nos and batch no. |
| `test_sco_with_material_transfer` | `self` | `` | - Set backflush based on Material Transfer.
- Create SCO for the item Subcontracted Item SA1 and Subcontracted Item SA5.
- Transfer the components from Stores to Supplier warehouse with batch no and serial nos.
- Transfer extra item Subcontracted SRM Item 4 for the subcontract item Subcontracted Item SA5.
- Create partial SCR against the SCO and check serial nos and batch no. |
| `test_subcontracting_with_same_components_different_fg` | `self` | `` | - Set backflush based on Material Transfer.
- Create SCO for the item Subcontracted Item SA2 and Subcontracted Item SA3.
- Transfer the components from Stores to Supplier warehouse with serial nos.
- Transfer extra qty of components for the item Subcontracted Item SA2.
- Create partial SCR against the SCO and check serial nos. |
| `test_return_non_consumed_batch_materials` | `self` | `` | - Set backflush based on Material Transfer.
- Create SCO for item Subcontracted Item SA2.
- Transfer the batched components from Stores to Supplier warehouse with serial nos.
- Transfer extra qty of component for the subcontracted item Subcontracted Item SA2.
- Create SCR for full qty against the SCO and change the qty of raw material.
- After that return the non consumed material back to the store from supplier's warehouse. |
| `test_return_non_consumed_materials` | `self` | `` | - Set backflush based on Material Transfer.
- Create SCO for item Subcontracted Item SA2.
- Transfer the components from Stores to Supplier warehouse with serial nos.
- Transfer extra qty of component for the subcontracted item Subcontracted Item SA2.
- Create SCR for full qty against the SCO and change the qty of raw material.
- After that return the non consumed material back to the store from supplier's warehouse. |
| `test_item_with_batch_based_on_bom` | `self` | `` | - Set backflush based on BOM.
- Create SCO for item Subcontracted Item SA4 (has batch no).
- Transfer the components from Stores to Supplier warehouse with batch no and serial nos.
- Transfer the components in multiple batches.
- Create the 3 SCR against the SCO and split Subcontracted Items into two batches.
- Keep the qty as 2 for Subcontracted Item in the SCR. |
| `test_item_with_batch_based_on_material_transfer` | `self` | `` | - Set backflush based on Material Transferred for Subcontract.
- Create SCO for item Subcontracted Item SA4 (has batch no).
- Transfer the components from Stores to Supplier warehouse with batch no and serial nos.
- Transfer the components in multiple batches with extra 2 qty for the batched item.
- Create the 3 SCR against the SCO and split Subcontracted Items into two batches.
- Keep the qty as 2 for Subcontracted Item in the SCR.
- In the first SCR the batched raw materials will be consumed 2 extra qty. |
| `test_partial_transfer_serial_no_components_based_on_material_transfer` | `self` | `` | - Set backflush based on Material Transferred for Subcontract.
- Create SCO for the item Subcontracted Item SA2.
- Transfer the partial components from Stores to Supplier warehouse with serial nos.
- Create partial SCR against the SCO and change the qty manually.
- Transfer the remaining components from Stores to Supplier warehouse with serial nos.
- Create SCR for remaining qty against the SCO and change the qty manually. |
| `test_incorrect_serial_no_components_based_on_material_transfer` | `self` | `` | - Set backflush based on Material Transferred for Subcontract.
- Create SCO for the item Subcontracted Item SA2.
- Transfer the serialized componenets to the supplier.
- Create SCR and change the serial no which is not transferred.
- System should throw the error and not allowed to save the SCR. |
| `delete_bundle_from_scr` | `scr` | `staticmethod` |  |
| `test_partial_transfer_batch_based_on_material_transfer` | `self` | `` | - Set backflush based on Material Transferred for Subcontract.
- Create SCO for the item Subcontracted Item SA6.
- Transfer the partial components from Stores to Supplier warehouse with batch.
- Create partial SCR against the SCO and change the qty manually.
- Transfer the remaining components from Stores to Supplier warehouse with batch.
- Create SCR for remaining qty against the SCO and change the qty manually. |
| `test_sco_supplied_qty` | `self` | `` | Check if 'Supplied Qty' in SCO's Supplied Items table is reset on submit/cancel. |
| `test_sco_with_material_transfer_with_use_serial_batch_fields` | `self` | `` | - Set backflush based on Material Transfer.
- Create SCO for the item Subcontracted Item SA1 and Subcontracted Item SA5.
- Transfer the components from Stores to Supplier warehouse with batch no and serial nos.
- Transfer extra item Subcontracted SRM Item 4 for the subcontract item Subcontracted Item SA5.
- Create partial SCR against the SCO and check serial nos and batch no. |
| `test_subcontracting_with_same_components_different_fg_with_serial_batch_fields` | `self` | `` | - Set backflush based on Material Transfer.
- Create SCO for the item Subcontracted Item SA2 and Subcontracted Item SA3.
- Transfer the components from Stores to Supplier warehouse with serial nos.
- Transfer extra qty of components for the item Subcontracted Item SA2.
- Create partial SCR against the SCO and check serial nos. |
| `test_return_non_consumed_materials_with_serial_batch_fields` | `self` | `` | - Set backflush based on Material Transfer.
- Create SCO for item Subcontracted Item SA2.
- Transfer the components from Stores to Supplier warehouse with serial nos.
- Transfer extra qty of component for the subcontracted item Subcontracted Item SA2.
- Create SCR for full qty against the SCO and change the qty of raw material.
- After that return the non consumed material back to the store from supplier's warehouse. |





## Functions

### `add_second_row_in_scr`
**Arguments:** `scr`
**Decorators:** ``

**Docstring:**
```

```
### `get_supplied_items`
**Arguments:** `scr_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_stock_in_entry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_item_details`
**Arguments:** `child_row, details`
**Decorators:** ``

**Docstring:**
```

```
### `make_stock_transfer_entry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_subcontracted_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_raw_materials`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_service_item`
**Arguments:** `item, properties`
**Decorators:** ``

**Docstring:**
```

```
### `make_service_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_bom_for_subcontracted_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `set_backflush_based_on`
**Arguments:** `based_on`
**Decorators:** ``

**Docstring:**
```

```
### `get_subcontracting_order`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_rm_items`
**Arguments:** `supplied_items`
**Decorators:** ``

**Docstring:**
```

```
### `make_subcontracted_item`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

