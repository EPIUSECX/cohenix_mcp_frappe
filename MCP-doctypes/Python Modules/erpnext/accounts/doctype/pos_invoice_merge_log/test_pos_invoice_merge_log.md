# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pos_invoice_merge_log/test_pos_invoice_merge_log.py`

## Classes

### `TestPOSInvoiceMergeLog`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_consolidated_invoice_creation` | `self` | `` |  |
| `test_consolidated_credit_note_creation` | `self` | `` |  |
| `test_consolidated_invoice_item_taxes` | `self` | `` |  |
| `test_consolidation_round_off_error_1` | `self` | `` | Test round off error in consolidated invoice creation if POS Invoice has inclusive tax |
| `test_consolidation_round_off_error_2` | `self` | `` | Test the same case as above but with an Unpaid POS Invoice |
| `test_consolidation_round_off_error_3` | `self` | `` |  |
| `test_consolidation_rounding_adjustment` | `self` | `` | Test if the rounding adjustment is calculated correctly |
| `test_serial_no_case_1` | `self` | `` | Create a POS Invoice with serial no
Create a Return Invoice with serial no
Create a POS Invoice with serial no again
Consolidate the invoices

The first POS Invoice should be consolidated with a separate single Merge Log
The second and third POS Invoice should be consolidated with a single Merge Log |
| `test_separate_consolidated_invoice_for_different_accounting_dimensions` | `self` | `` | Creating 3 POS Invoices where first POS Invoice has different Cost Center than the other two.
Consolidate the Invoices.
Check whether the first POS Invoice is consolidated with a separate Sales Invoice than the other two.
Check whether the second and third POS Invoice are consolidated with the same Sales Invoice. |





## Functions

No top-level functions found in this file.
