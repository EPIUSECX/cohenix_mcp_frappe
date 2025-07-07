# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/job_card/job_card.py`

## Classes

### `OverlapError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OperationMismatchError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OperationSequenceError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `JobCardCancelError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `JobCardOverTransferError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `JobCard`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `has_stock_entry` | `self` | `` |  |
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `validate_on_hold` | `self` | `` |  |
| `set_manufactured_qty` | `self` | `` |  |
| `validate_job_card_qty` | `self` | `` |  |
| `set_sub_operations` | `self` | `` |  |
| `validate_time_logs` | `self, save` | `` |  |
| `get_overlap_for` | `self, args, open_job_cards` | `` |  |
| `has_overlap` | `self, production_capacity, time_logs` | `` |  |
| `get_time_logs` | `self, args, doctype, open_job_cards` | `` |  |
| `get_open_job_cards` | `self, employee, workstation` | `` |  |
| `get_workstation_based_on_available_slot` | `self, existing_time_logs` | `` |  |
| `time_slot_wise_busy_workstations` | `existing_time_logs` | `staticmethod` |  |
| `schedule_time_logs` | `self, row` | `` |  |
| `validate_overlap_for_workstation` | `self, args, row` | `` |  |
| `check_workstation_time` | `self, row` | `` |  |
| `add_time_log` | `self, args` | `` |  |
| `add_start_time_log` | `self, args` | `` |  |
| `set_employees` | `self, employees` | `` |  |
| `update_sub_operation_status` | `self` | `` |  |
| `update_time_logs` | `self, row` | `` |  |
| `get_required_items` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate_transfer_qty` | `self` | `` |  |
| `validate_job_card` | `self` | `` |  |
| `set_expected_and_actual_time` | `self` | `` |  |
| `set_process_loss` | `self` | `` |  |
| `update_work_order` | `self` | `` |  |
| `update_semi_finished_good_details` | `self` | `` |  |
| `update_corrective_in_work_order` | `self, wo` | `` |  |
| `validate_produced_quantity` | `self, for_quantity, process_loss_qty, wo` | `` |  |
| `update_work_order_data` | `self, for_quantity, process_loss_qty, time_in_mins, wo` | `` |  |
| `get_current_operation_data` | `self` | `` |  |
| `set_transferred_qty_in_job_card_item` | `self, ste_doc` | `` |  |
| `set_transferred_qty` | `self, update_status` | `` |  |
| `set_transferred_qty_in_work_order` | `self` | `` |  |
| `set_status` | `self, update_status` | `` |  |
| `set_wip_warehouse` | `self` | `` |  |
| `validate_operation_id` | `self` | `` |  |
| `pause_job` | `self` | `` |  |
| `resume_job` | `self` | `` |  |
| `validate_sequence_id` | `self` | `` |  |
| `validate_work_order` | `self` | `` |  |
| `is_work_order_closed` | `self` | `` |  |
| `update_status_in_workstation` | `self, status` | `` |  |
| `add_time_logs` | `self` | `` |  |
| `update_workstation_status` | `self` | `` |  |
| `start_timer` | `self` | `` |  |
| `complete_job_card` | `self` | `` |  |
| `make_stock_entry_for_semi_fg_item` | `self, auto_submit` | `` |  |





## Functions

### `make_subcontracting_po`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_time_log`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_operation_details`
**Arguments:** `work_order, operation`
**Decorators:** ``

**Docstring:**
```

```
### `get_operations`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `make_material_request`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_stock_entry`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `time_diff_in_minutes`
**Arguments:** `string_ed_date, string_st_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_job_details`
**Arguments:** `start, end, filters`
**Decorators:** ``

**Docstring:**
```

```
### `make_corrective_job_card`
**Arguments:** `source_name, operation, for_operation, target_doc`
**Decorators:** ``

**Docstring:**
```

```

