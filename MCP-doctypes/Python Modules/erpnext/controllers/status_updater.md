# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/status_updater.py`

## Classes

### `OverAllowanceError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `StatusUpdater`
**Inherits:** `Document`


**Docstring:**
```
Updates the status of the calling records
Delivery Note: Update Delivered Qty, Update Percent and Validate over delivery
Sales Invoice: Update Billed Amt, Update Percent and Validate over billing
Installation Note: Update Installed Qty, Update Percent Qty and Validate over installation
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `update_prevdoc_status` | `self` | `` |  |
| `set_status` | `self, update, status, update_modified` | `` |  |
| `get_status` | `self` | `` | Get the status of the document.

Returns:
dict: A dictionary containing the status. This allows callers to receive
a dictionary for efficient bulk updates, for example when `per_billed`
and other status fields also need to be updated.

Note:
Can be overriden on a doctype to implement more localized status updater logic.

Example:
{
"status": "Draft",
"per_billed": 50,
"billing_status": "Partly Billed"
} |
| `validate_qty` | `self` | `` | Validates qty at row level |
| `check_overflow_with_allowance` | `self, item, args` | `` | Checks if there is overflow condering a relaxation allowance |
| `limits_crossed_error` | `self, args, item, qty_or_amount` | `` | Raise exception for limits crossed |
| `warn_about_bypassing_with_role` | `self, item, qty_or_amount, role` | `` |  |
| `update_qty` | `self, update_modified` | `` | Updates qty or amount at row level

:param update_modified: If true, updates `modified` and `modified_by` for target parent doc |
| `_update_children` | `self, args, update_modified` | `` | Update quantities or amount in child table |
| `_calculate_target_parent_percentage` | `name, target_parent_dt, target_dt, target_ref_field, target_field` | `staticmethod` |  |
| `_determine_status` | `percentage, keyword` | `staticmethod` |  |
| `_update_percent_field_in_targets` | `self, args, update_modified` | `` | Update percent field in parent transaction |
| `_update_percent_field` | `self, args, update_modified` | `` | Update percent field in parent transaction |
| `_update_modified` | `self, args, update_modified` | `` |  |
| `update_billing_status_for_zero_amount_refdoc` | `self, ref_dt` | `` |  |
| `update_billing_status` | `self, zero_amount_refdoc, ref_dt, ref_fieldname` | `` |  |





## Functions

### `validate_status`
**Arguments:** `status, options`
**Decorators:** ``

**Docstring:**
```

```
### `get_allowance_for`
**Arguments:** `item_code, item_allowance, global_qty_allowance, global_amount_allowance, qty_or_amount`
**Decorators:** ``

**Docstring:**
```
Returns the allowance for the item, if not set, returns global allowance
```

