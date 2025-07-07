# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_repair/asset_repair.py`

## Classes

### `AssetRepair`
**Inherits:** `AccountsController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_asset` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `validate_purchase_invoices` | `self` | `` |  |
| `get_invoice_items` | `self, pi` | `` |  |
| `validate_service_purchase_invoice` | `self, purchase_invoice, invoice_items` | `` |  |
| `validate_expense_account` | `self, row, invoice_items` | `` |  |
| `validate_purchase_invoice_repair_cost` | `self, row, invoice_items` | `` |  |
| `update_status` | `self` | `` |  |
| `calculate_consumed_items_cost` | `self` | `` |  |
| `calculate_repair_cost` | `self` | `` |  |
| `calculate_total_repair_cost` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `cancel_sabb` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `after_delete` | `self` | `` |  |
| `check_repair_status` | `self` | `` |  |
| `update_asset_value` | `self` | `` |  |
| `get_total_value_of_stock_consumed` | `self` | `` |  |
| `decrease_stock_quantity` | `self` | `` |  |
| `validate_serial_no` | `self, stock_item` | `` |  |
| `make_gl_entries` | `self, cancel` | `` |  |
| `get_gl_entries` | `self` | `` |  |
| `get_gl_entries_for_repair_cost` | `self, gl_entries, fixed_asset_account` | `` |  |
| `get_gl_entries_for_consumed_items` | `self, gl_entries, fixed_asset_account` | `` |  |
| `set_increase_in_asset_life` | `self` | `` |  |
| `get_depreciation_note` | `self` | `` |  |
| `add_asset_activity` | `self, subject` | `` |  |





## Functions

### `get_downtime`
**Arguments:** `failure_date, completion_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_purchase_invoice`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_expense_accounts`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```

