# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/full_and_final_statement/full_and_final_statement.py`

## Classes

### `FullandFinalStatement`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate_relieving_date` | `self` | `` |  |
| `validate_settlement` | `self, component_type` | `` |  |
| `validate_assets` | `self` | `` |  |
| `get_outstanding_statements` | `self` | `` |  |
| `get_assets_statements` | `self` | `` |  |
| `set_total_asset_recovery_cost` | `self` | `` |  |
| `set_totals` | `self` | `` |  |
| `add_withheld_salary_slips` | `self` | `` |  |
| `create_component_row` | `self, components, component_type` | `` |  |
| `get_payable_component` | `self` | `` |  |
| `get_receivable_component` | `self` | `` |  |
| `get_assets_movement` | `self` | `` |  |
| `create_journal_entry` | `self` | `` |  |
| `update_reference_document_payment_status` | `self, payable` | `` |  |
| `update_linked_payable_documents` | `self` | `` | update payment status in linked payable documents |





## Functions

### `get_account_and_amount`
**Arguments:** `ref_doctype, ref_document, company`
**Decorators:** ``

**Docstring:**
```

```
### `update_full_and_final_statement_status`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Updates FnF status on Journal Entry Submission/Cancellation
```

