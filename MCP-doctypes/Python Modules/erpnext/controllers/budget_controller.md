# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/budget_controller.py`

## Classes

### `BudgetValidation`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doc, gl_map` | `` |  |
| `validate` | `self` | `` |  |
| `build_validation_map` | `self` | `` |  |
| `initialize_dict` | `self, key` | `` |  |
| `overlap` | `self` | `property` |  |
| `build_to_validate_map` | `self` | `` |  |
| `validate_for_overbooking` | `self` | `` |  |
| `get_child_nodes` | `self, budget_against, dimension` | `` |  |
| `budget_keys` | `self` | `property` |  |
| `build_budget_keys` | `self` | `` | key structure - (dimension_type, dimension, GL account) |
| `item_keys` | `self` | `property` |  |
| `build_item_keys` | `self` | `` | key structure - (dimension_type, dimension, GL account) |
| `get_dimensions` | `self` | `` |  |
| `get_budget_records` | `self` | `` |  |
| `get_ordered_amount` | `self, key` | `` |  |
| `get_requested_amount` | `self, key` | `` |  |
| `get_actual_expense` | `self, key` | `` |  |
| `stop` | `self, msg` | `` |  |
| `warn` | `self, msg` | `` |  |
| `execute_action` | `self, action, msg` | `` |  |
| `handle_individual_doctype_action` | `self, key, config, budget, budget_amt, existing_amt, current_amt, acc_monthly_budget` | `` |  |
| `handle_purchase_order_overlimit` | `self, key, v_map` | `` |  |
| `handle_material_request_overlimit` | `self, key, v_map` | `` |  |
| `handle_actual_expense_overlimit` | `self, key, v_map` | `` |  |
| `handle_actions` | `self, key, v_map` | `` |  |
| `handle_cumulative_overlimit` | `self, key, v_map` | `` |  |
| `budget_applicable_for` | `self, v_map, current_amt` | `` |  |
| `handle_cumulative_overlimit_for_monthly` | `self, key, v_map` | `` |  |
| `handle_cumulative_overlimit_for_annual` | `self, key, v_map` | `` |  |





## Functions

No top-level functions found in this file.
