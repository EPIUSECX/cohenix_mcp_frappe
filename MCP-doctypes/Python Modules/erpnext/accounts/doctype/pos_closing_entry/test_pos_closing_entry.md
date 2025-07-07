# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pos_closing_entry/test_pos_closing_entry.py`

## Classes

### `TestPOSClosingEntry`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_pos_closing_entry` | `self` | `` |  |
| `test_pos_closing_without_item_code` | `self` | `` | Test if POS Closing Entry is created without item code |
| `test_pos_qty_for_item` | `self` | `` | Test if quantity is calculated correctly for an item in POS Closing Entry |
| `test_cancelling_of_pos_closing_entry` | `self` | `` |  |
| `test_pos_closing_for_required_accounting_dimension_in_pos_profile` | `self` | `` | test case to check whether we can create POS Closing Entry without mandatory accounting dimension |
| `test_merging_into_sales_invoice_for_batched_item` | `self` | `` |  |
| `test_closing_entries_with_sales_invoice` | `self` | `` |  |
| `test_sales_invoice_in_pos_invoice_mode` | `self` | `` | Test Sales Invoice and Return Sales Invoice creation during POS Invoice mode. |
| `test_pos_invoice_in_sales_invoice_mode` | `self` | `` | Test POS Invoice and Return POS Invoice creation during Sales Invoice mode. |





## Functions

### `init_user_and_profile`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_test_item_qty`
**Arguments:** `pos_profile`
**Decorators:** ``

**Docstring:**
```

```
### `create_multiple_sales_invoices`
**Arguments:** `pos_profile`
**Decorators:** ``

**Docstring:**
```

```
### `create_multiple_pos_invoices`
**Arguments:** `pos_profile`
**Decorators:** ``

**Docstring:**
```

```

