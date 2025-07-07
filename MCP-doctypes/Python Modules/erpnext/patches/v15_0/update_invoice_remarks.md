# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/patches/v15_0/update_invoice_remarks.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_sales_invoice_remarks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Update remarks in Sales Invoice.
Some sites may have very large volume of sales invoices.
In such cases, updating documents one by one won't be successful, especially during site migration step.
Refer to the bug report: https://github.com/frappe/erpnext/issues/43634
In this case, a bulk update must be done.

        Step 1: Update remarks in GL Entries
        Step 2: Update remarks in Payment Ledger Entries
        Step 3: Update remarks in Sales Invoice - Should be last step
```
### `update_purchase_invoice_remarks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Update remarks in Purchase Invoice.
Some sites may have very large volume of purchase invoices.
In such cases, updating documents one by one wont be successful, especially during site migration step.
Refer to the bug report: https://github.com/frappe/erpnext/issues/43634
In this case, a bulk update must be done.

        Step 1: Update remarks in GL Entries
        Step 2: Update remarks in Payment Ledger Entries
        Step 3: Update remarks in Purchase Invoice - Should be last step
```
### `update_sales_invoice_gle_remarks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_sales_invoice_ple_remarks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_purchase_invoice_gle_remarks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_purchase_invoice_ple_remarks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

