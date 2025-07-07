# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/tax_withholding_category/test_tax_withholding_category.py`

## Classes

### `TestTaxWithholdingCategory`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDown` | `self` | `` |  |
| `test_cumulative_threshold_tds` | `self` | `` |  |
| `test_tds_with_account_changed` | `self` | `` |  |
| `test_single_threshold_tds` | `self` | `` |  |
| `test_tax_withholding_category_checks` | `self` | `` |  |
| `test_cumulative_threshold_with_party_ledger_amount_on_net_total` | `self` | `` |  |
| `test_cumulative_threshold_with_tax_on_excess_amount` | `self` | `` |  |
| `test_cumulative_threshold_tcs` | `self` | `` |  |
| `test_tcs_on_unallocated_advance_payments` | `self` | `` |  |
| `test_tcs_on_allocated_advance_payments` | `self` | `` |  |
| `test_tds_calculation_on_net_total` | `self` | `` |  |
| `test_tds_calculation_on_net_total_partial_tds` | `self` | `` |  |
| `test_tds_deduction_for_po_via_payment_entry` | `self` | `` |  |
| `test_multi_category_single_supplier` | `self` | `` |  |
| `test_tax_withholding_category_voucher_display` | `self` | `` |  |
| `test_tax_withholding_via_payment_entry_for_advances` | `self` | `` |  |
| `test_lower_deduction_certificate_application` | `self` | `` |  |
| `test_ldc_at_0_rate` | `self` | `` |  |
| `set_previous_fy_and_tax_category` | `self` | `` |  |
| `test_tds_across_fiscal_year` | `self` | `` | Advance TDS on previous fiscal year should be properly allocated on Invoices in upcoming fiscal year
--||-----FY 2023-----||-----FY 2024-----||--
--||-----Advance-----||---Inv1---Inv2---||-- |





## Functions

### `cancel_invoices`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_purchase_invoice`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_purchase_order`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_sales_invoice`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_payment_entry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_records`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_tax_withholding_category_records`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_tax_withholding_category`
**Arguments:** `category_name, rate, from_date, to_date, account, single_threshold, cumulative_threshold, round_off_tax_amount, consider_party_ledger_amount, tax_on_excess_amount`
**Decorators:** ``

**Docstring:**
```

```
### `create_lower_deduction_certificate`
**Arguments:** `supplier, tax_withholding_category, tax_rate, certificate_no, limit, valid_from, valid_upto`
**Decorators:** ``

**Docstring:**
```

```
### `make_pan_no_field`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

