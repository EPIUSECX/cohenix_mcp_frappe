# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/supplier_scorecard_variable/supplier_scorecard_variable.py`

## Classes

### `VariablePathNotFound`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SupplierScorecardVariable`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_path_exists` | `self` | `` |  |





## Functions

### `get_total_workdays`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the number of days in this period
```
### `get_item_workdays`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the number of days in this period
```
### `get_total_cost_of_shipments`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total cost of all shipments in the period (based on Purchase Orders)
```
### `get_cost_of_delayed_shipments`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total cost of all delayed shipments in the period (based on Purchase Receipts - POs)
```
### `get_cost_of_on_time_shipments`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total cost of all on_time shipments in the period (based on Purchase Receipts)
```
### `get_total_days_late`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the number of item days late in the period (based on Purchase Receipts vs POs)
```
### `get_on_time_shipments`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the number of late shipments (counting each item) in the period (based on Purchase Receipts vs POs)
```
### `get_late_shipments`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the number of late shipments (counting each item) in the period (based on Purchase Receipts vs POs)
```
### `get_total_received`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of received shipments in the period (based on Purchase Receipts)
```
### `get_total_received_amount`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total amount (in company currency) received in the period (based on Purchase Receipts)
```
### `get_total_received_items`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of received shipments in the period (based on Purchase Receipts)
```
### `get_total_rejected_amount`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total amount (in company currency) rejected in the period (based on Purchase Receipts)
```
### `get_total_rejected_items`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of rejected items in the period (based on Purchase Receipts)
```
### `get_total_accepted_amount`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total amount (in company currency) accepted in the period (based on Purchase Receipts)
```
### `get_total_accepted_items`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of rejected items in the period (based on Purchase Receipts)
```
### `get_total_shipments`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of ordered shipments to arrive in the period (based on Purchase Receipts)
```
### `get_ordered_qty`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Returns the total number of ordered quantity (based on Purchase Orders)
```
### `get_invoiced_qty`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Returns the total number of invoiced quantity (based on Purchase Invoice)
```
### `get_rfq_total_number`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of RFQs sent to supplier
```
### `get_rfq_total_items`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of RFQ items sent to supplier
```
### `get_sq_total_number`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of RFQ items sent to supplier
```
### `get_sq_total_items`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of RFQ items sent to supplier
```
### `get_rfq_response_days`
**Arguments:** `scorecard`
**Decorators:** ``

**Docstring:**
```
Gets the total number of days it has taken a supplier to respond to rfqs in the period
```

