# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/customer/customer.py`

## Classes

### `Customer`
**Inherits:** `TransactionBase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` | Load address and contacts in `__onload` |
| `load_dashboard_info` | `self` | `` |  |
| `autoname` | `self` | `` |  |
| `get_customer_name` | `self` | `` |  |
| `after_insert` | `self` | `` | If customer created from Lead, update customer id in quotations, opportunities |
| `validate` | `self` | `` |  |
| `get_customer_group_details` | `self` | `` |  |
| `check_customer_group_change` | `self` | `` |  |
| `validate_default_bank_account` | `self` | `` |  |
| `validate_internal_customer` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `add_role_for_user` | `self` | `` |  |
| `update_customer_groups` | `self` | `` |  |
| `create_primary_contact` | `self` | `` |  |
| `create_primary_address` | `self` | `` |  |
| `update_lead_status` | `self` | `` | If Customer created from Lead, update lead status to "Converted"
update Customer link in Quotation, Opportunity |
| `link_lead_address_and_contact` | `self` | `` |  |
| `copy_communication` | `self` | `` |  |
| `validate_name_with_customer_group` | `self` | `` |  |
| `validate_credit_limit_on_change` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `after_rename` | `self, olddn, newdn, merge` | `` |  |
| `set_loyalty_program` | `self` | `` |  |





## Functions

### `make_quotation`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_opportunity`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_payment_entry`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `_set_missing_values`
**Arguments:** `source, target`
**Decorators:** ``

**Docstring:**
```

```
### `get_loyalty_programs`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
returns applicable loyalty programs for a customer
```
### `get_nested_links`
**Arguments:** `link_doctype, link_name, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `check_credit_limit`
**Arguments:** `customer, company, ignore_outstanding_sales_order, extra_amount`
**Decorators:** ``

**Docstring:**
```

```
### `send_emails`
**Arguments:** `customer, customer_outstanding, credit_limit, credit_controller_users_list`
**Decorators:** ``

**Docstring:**
```

```
### `get_customer_outstanding`
**Arguments:** `customer, company, ignore_outstanding_sales_order, cost_center`
**Decorators:** ``

**Docstring:**
```

```
### `get_credit_limit`
**Arguments:** `customer, company`
**Decorators:** ``

**Docstring:**
```

```
### `make_contact`
**Arguments:** `args, is_primary_contact`
**Decorators:** ``

**Docstring:**
```

```
### `make_address`
**Arguments:** `args, is_primary_address, is_shipping_address`
**Decorators:** ``

**Docstring:**
```

```
### `get_customer_primary_contact`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `parse_full_name`
**Arguments:** `full_name`
**Decorators:** ``

**Docstring:**
```
Parse full name into first name, middle name and last name
```

