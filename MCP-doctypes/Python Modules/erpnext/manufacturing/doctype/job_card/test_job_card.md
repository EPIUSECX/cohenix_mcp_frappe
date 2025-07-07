# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/job_card/test_job_card.py`

## Classes

### `TestJobCard`
**Inherits:** `ERPNextTestSuite`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `make_bom_for_jc_tests` | `self` | `` |  |
| `work_order` | `self` | `property` | Work Order lazily created for tests. |
| `generate_required_stock` | `self, work_order` | `` | Create twice the stock for all required items in work order. |
| `tearDown` | `self` | `` |  |
| `test_job_card_operations` | `self` | `` |  |
| `test_job_card_with_different_work_station` | `self` | `` |  |
| `test_job_card_overlap` | `self` | `` |  |
| `test_job_card_overlap_with_capacity` | `self` | `` |  |
| `test_job_card_multiple_materials_transfer` | `self` | `` | Test transferring RMs separately against Job Card with multiple RMs. |
| `test_job_card_excess_material_transfer` | `self` | `` | Test transferring more than required RM against Job Card. |
| `test_job_card_excess_material_transfer_block` | `self` | `` |  |
| `test_job_card_excess_material_transfer_with_no_reference` | `self` | `` |  |
| `test_job_card_partial_material_transfer` | `self` | `` | Test partial material transfer against Job Card |
| `test_job_card_material_transfer_correctness` | `self` | `` | 1. Test if only current Job Card Items are pulled in a Stock Entry against a Job Card
2. Test impact of changing 'For Qty' in such a Stock Entry |
| `test_corrective_costing` | `self` | `` |  |
| `test_if_corrective_jc_ops_cost_is_added_to_manufacture_stock_entry` | `self` | `` |  |
| `test_job_card_statuses` | `self` | `` |  |
| `test_job_card_material_request_and_bom_details` | `self` | `` |  |
| `test_job_card_proccess_qty_and_completed_qty` | `self` | `` |  |





## Functions

### `create_bom_with_multiple_operations`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Create a BOM with multiple operations and Material Transfer against Job Card
```
### `make_wo_with_transfer_against_jc`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Create a WO with multiple operations and Material Transfer against Job Card
```

