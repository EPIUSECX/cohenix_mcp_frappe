# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/report/gross_profit/test_gross_profit.py`

## Classes

### `TestGrossProfit`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `create_company` | `self` | `` |  |
| `create_item` | `self` | `` |  |
| `create_bundle` | `self` | `` |  |
| `create_customer` | `self` | `` |  |
| `create_sales_invoice` | `self, qty, rate, posting_date, do_not_save, do_not_submit` | `` | Helper function to populate default values in sales invoice |
| `create_delivery_note` | `self, item, qty, rate, posting_date, do_not_save, do_not_submit` | `` | Helper function to populate default values in Delivery Note |
| `clear_old_entries` | `self` | `` |  |
| `test_invoice_without_only_delivery_note` | `self` | `` | Test buying amount for Invoice without `update_stock` flag set but has Delivery Note |
| `test_bundled_delivery_note_with_different_warehouses` | `self` | `` | Test Delivery Note with bundled item. Packed Item from the bundle having different warehouses |
| `test_order_connected_dn_and_inv` | `self` | `` |  |
| `test_crnote_against_invoice_with_multiple_instances_of_same_item` | `self` | `` | Item Qty for Sales Invoices with multiple instances of same item go in the -ve. Ideally, the credit noteshould cancel out the invoice items. |
| `test_standalone_cr_notes` | `self` | `` | Standalone cr notes will be reported as usual |
| `test_different_rates_in_si_and_dn` | `self` | `` |  |
| `test_valuation_rate_without_previous_sle` | `self` | `` | Test Valuation rate calculation when stock ledger is empty and invoices are against different warehouses |
| `test_gross_profit_groupby_invoices` | `self` | `` |  |





## Functions

No top-level functions found in this file.
