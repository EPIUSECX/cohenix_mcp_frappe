# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/party.py`

## Classes

### `DuplicatePartyAccountError`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `get_party_details`
**Arguments:** `party, account, party_type, company, posting_date, bill_date, price_list, currency, doctype, ignore_permissions, fetch_payment_terms_template, party_address, company_address, shipping_address, dispatch_address, pos_profile`
**Decorators:** ``

**Docstring:**
```

```
### `_get_party_details`
**Arguments:** `party, account, party_type, company, posting_date, bill_date, price_list, currency, doctype, ignore_permissions, fetch_payment_terms_template, party_address, company_address, shipping_address, dispatch_address, pos_profile`
**Decorators:** ``

**Docstring:**
```

```
### `set_address_details`
**Arguments:** `party_details, party, party_type, doctype, company, party_address, company_address, shipping_address, dispatch_address`
**Decorators:** ``

**Docstring:**
```

```
### `get_regional_address_details`
**Arguments:** `party_details, doctype, company`
**Decorators:** ``

**Docstring:**
```

```
### `complete_contact_details`
**Arguments:** `party_details`
**Decorators:** ``

**Docstring:**
```

```
### `set_contact_details`
**Arguments:** `party_details, party, party_type`
**Decorators:** ``

**Docstring:**
```

```
### `set_other_values`
**Arguments:** `party_details, party, party_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_price_list`
**Arguments:** `party`
**Decorators:** ``

**Docstring:**
```
Return default price list for party (Document object)
```
### `set_price_list`
**Arguments:** `party_details, party, party_type, given_price_list, pos`
**Decorators:** ``

**Docstring:**
```

```
### `set_account_and_due_date`
**Arguments:** `party, account, party_type, company, posting_date, bill_date, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_account`
**Arguments:** `party_type, party, company, include_advance`
**Decorators:** ``

**Docstring:**
```
Returns the account for the given `party`.
Will first search in party (Customer / Supplier) record, if not found,
will search in group (Customer Group / Supplier Group),
finally will return default.
```
### `get_party_advance_account`
**Arguments:** `party_type, party, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_bank_account`
**Arguments:** `party_type, party`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_account_currency`
**Arguments:** `party_type, party, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_gle_currency`
**Arguments:** `party_type, party, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_gle_account`
**Arguments:** `party_type, party, company`
**Decorators:** ``

**Docstring:**
```

```
### `validate_party_gle_currency`
**Arguments:** `party_type, party, company, party_account_currency`
**Decorators:** ``

**Docstring:**
```
Validate party account currency with existing GL Entry's currency
```
### `validate_party_accounts`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_due_date`
**Arguments:** `posting_date, party_type, party, company, bill_date, template_name`
**Decorators:** ``

**Docstring:**
```
Get due date from `Payment Terms Template`
```
### `get_due_date_from_template`
**Arguments:** `template_name, posting_date, bill_date`
**Decorators:** ``

**Docstring:**
```
Inspects all `Payment Term`s from the a `Payment Terms Template` and returns the due
date after considering all the `Payment Term`s requirements.
:param template_name: Name of the `Payment Terms Template`
:return: String representing the calculated due date
```
### `validate_due_date`
**Arguments:** `posting_date, due_date, bill_date, template_name, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `validate_due_date_with_template`
**Arguments:** `posting_date, due_date, bill_date, template_name, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_address_tax_category`
**Arguments:** `tax_category, billing_address, shipping_address`
**Decorators:** ``

**Docstring:**
```

```
### `set_taxes`
**Arguments:** `party, party_type, posting_date, company, customer_group, supplier_group, tax_category, billing_address, shipping_address, use_for_shopping_cart`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_terms_template`
**Arguments:** `party_name, party_type, company`
**Decorators:** ``

**Docstring:**
```

```
### `validate_party_frozen_disabled`
**Arguments:** `party_type, party_name`
**Decorators:** ``

**Docstring:**
```

```
### `validate_account_party_type`
**Arguments:** `self`
**Decorators:** ``

**Docstring:**
```

```
### `get_dashboard_info`
**Arguments:** `party_type, party, loyalty_program`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_shipping_address`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Returns an Address name (best guess) for the given doctype and name for which `address_type == 'Shipping'` is true.
and/or `is_shipping_address = 1`.

It returns an empty string if there is no matching record.

:param doctype: Party Doctype
:param name: Party name
:return: String
```
### `get_partywise_advanced_payment_amount`
**Arguments:** `party_type, posting_date, future_payment, company, party`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_contact`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Returns contact name only if there is a primary contact for given doctype and name.

Else returns None

:param doctype: Party Doctype
:param name: Party name
:return: String
```
### `add_party_account`
**Arguments:** `party_type, party, company, account`
**Decorators:** ``

**Docstring:**
```

```
### `render_address`
**Arguments:** `address, check_permissions`
**Decorators:** ``

**Docstring:**
```

```

