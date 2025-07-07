# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/process_statement_of_accounts/process_statement_of_accounts.py`

## Classes

### `ProcessStatementOfAccounts`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |





## Functions

### `get_report_pdf`
**Arguments:** `doc, consolidated`
**Decorators:** ``

**Docstring:**
```

```
### `get_statement_dict`
**Arguments:** `doc, get_statement_dict`
**Decorators:** ``

**Docstring:**
```

```
### `set_ageing`
**Arguments:** `doc, entry`
**Decorators:** ``

**Docstring:**
```

```
### `get_common_filters`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_gl_filters`
**Arguments:** `doc, entry, tax_id, presentation_currency`
**Decorators:** ``

**Docstring:**
```

```
### `get_ar_filters`
**Arguments:** `doc, entry`
**Decorators:** ``

**Docstring:**
```

```
### `get_html`
**Arguments:** `doc, filters, entry, col, res, ageing`
**Decorators:** ``

**Docstring:**
```

```
### `get_customers_based_on_territory_or_customer_group`
**Arguments:** `customer_collection, collection_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_customers_based_on_sales_person`
**Arguments:** `sales_person`
**Decorators:** ``

**Docstring:**
```

```
### `get_recipients_and_cc`
**Arguments:** `customer, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_context`
**Arguments:** `customer, doc`
**Decorators:** ``

**Docstring:**
```

```
### `fetch_customers`
**Arguments:** `customer_collection, collection_name, primary_mandatory`
**Decorators:** ``

**Docstring:**
```

```
### `get_customer_emails`
**Arguments:** `customer_name, primary_mandatory, billing_and_primary`
**Decorators:** ``

**Docstring:**
```
Returns first email from Contact Email table as a Billing email
when Is Billing Contact checked
and Primary email- email with Is Primary checked
```
### `download_statements`
**Arguments:** `document_name`
**Decorators:** ``

**Docstring:**
```

```
### `send_emails`
**Arguments:** `document_name, from_scheduler, posting_date`
**Decorators:** ``

**Docstring:**
```

```
### `send_auto_email`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

