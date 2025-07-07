# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/tax_withholding_category/tax_withholding_category.py`

## Classes

### `TaxWithholdingCategory`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `validate_companies_and_accounts` | `self` | `` |  |
| `validate_thresholds` | `self` | `` |  |





## Functions

### `get_party_details`
**Arguments:** `inv`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_tax_withholding_details`
**Arguments:** `inv, tax_withholding_category`
**Decorators:** ``

**Docstring:**
```

```
### `get_cost_center`
**Arguments:** `inv`
**Decorators:** ``

**Docstring:**
```

```
### `get_tax_withholding_details`
**Arguments:** `tax_withholding_category, posting_date, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_tax_withholding_rates`
**Arguments:** `tax_withholding, posting_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_tax_row_for_tcs`
**Arguments:** `inv, tax_details, tax_amount, tax_deducted`
**Decorators:** ``

**Docstring:**
```

```
### `get_tax_row_for_tds`
**Arguments:** `tax_details, tax_amount`
**Decorators:** ``

**Docstring:**
```

```
### `get_lower_deduction_certificate`
**Arguments:** `company, posting_date, tax_details, pan_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_tax_amount`
**Arguments:** `party_type, parties, inv, tax_details, posting_date, pan_no`
**Decorators:** ``

**Docstring:**
```

```
### `is_tax_deducted_on_the_basis_of_inv`
**Arguments:** `vouchers`
**Decorators:** ``

**Docstring:**
```

```
### `get_invoice_vouchers`
**Arguments:** `parties, tax_details, company, party_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_entry_vouchers`
**Arguments:** `parties, tax_details, company, party_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_advance_vouchers`
**Arguments:** `parties, company, from_date, to_date, party_type`
**Decorators:** ``

**Docstring:**
```
Use Payment Ledger to fetch unallocated Advance Payments
```
### `get_taxes_deducted_on_advances_allocated`
**Arguments:** `inv, tax_details`
**Decorators:** ``

**Docstring:**
```

```
### `get_deducted_tax`
**Arguments:** `taxable_vouchers, tax_details`
**Decorators:** ``

**Docstring:**
```

```
### `get_advance_tax_across_fiscal_year`
**Arguments:** `tax_deducted_on_advances, tax_details`
**Decorators:** ``

**Docstring:**
```
Only applies for Taxes deducted on Advance Payments
```
### `get_tds_amount`
**Arguments:** `ldc, parties, inv, tax_details, voucher_wise_amount`
**Decorators:** ``

**Docstring:**
```

```
### `get_tcs_amount`
**Arguments:** `parties, inv, tax_details, vouchers, adv_vouchers`
**Decorators:** ``

**Docstring:**
```

```
### `get_advance_adjusted_in_invoice`
**Arguments:** `inv`
**Decorators:** ``

**Docstring:**
```

```
### `get_invoice_total_without_tcs`
**Arguments:** `inv, tax_details`
**Decorators:** ``

**Docstring:**
```

```
### `get_limit_consumed`
**Arguments:** `ldc, parties`
**Decorators:** ``

**Docstring:**
```

```
### `get_lower_deduction_amount`
**Arguments:** `current_amount, limit_consumed, certificate_limit, rate, tax_details`
**Decorators:** ``

**Docstring:**
```

```
### `is_valid_certificate`
**Arguments:** `ldc, posting_date, limit_consumed`
**Decorators:** ``

**Docstring:**
```

```
### `normal_round`
**Arguments:** `number`
**Decorators:** ``

**Docstring:**
```
Rounds a number to the nearest integer.
:param number: The number to round.
```

