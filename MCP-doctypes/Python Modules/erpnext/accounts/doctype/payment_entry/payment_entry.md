# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_entry/payment_entry.py`

## Classes

### `InvalidPaymentEntry`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `PaymentEntry`
**Inherits:** `AccountsController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `setup_party_account_field` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `validate_for_repost` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `set_liability_account` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `update_payment_requests` | `self, cancel` | `` |  |
| `update_outstanding_amounts` | `self` | `` |  |
| `validate_duplicate_entry` | `self` | `` |  |
| `set_bank_account_data` | `self` | `` |  |
| `validate_payment_type_with_outstanding` | `self` | `` |  |
| `validate_allocated_amount` | `self` | `` |  |
| `validate_allocated_amount_as_per_payment_request` | `self` | `` | Allocated amount should not be greater than the outstanding amount of the Payment Request. |
| `term_based_allocation_enabled_for_reference` | `self, reference_doctype, reference_name` | `` |  |
| `validate_allocated_amount_with_latest_data` | `self` | `` |  |
| `delink_advance_entry_references` | `self` | `` |  |
| `set_missing_values` | `self` | `` |  |
| `set_missing_ref_details` | `self, force, update_ref_details_only_for, reference_exchange_details` | `` |  |
| `validate_payment_type` | `self` | `` |  |
| `validate_party_details` | `self` | `` |  |
| `set_exchange_rate` | `self, ref_doc` | `` |  |
| `set_source_exchange_rate` | `self, ref_doc` | `` |  |
| `set_target_exchange_rate` | `self, ref_doc` | `` |  |
| `validate_mandatory` | `self` | `` |  |
| `validate_reference_documents` | `self` | `` |  |
| `get_valid_reference_doctypes` | `self` | `` |  |
| `validate_paid_invoices` | `self` | `` |  |
| `validate_journal_entry` | `self` | `` |  |
| `update_payment_schedule` | `self, cancel` | `` |  |
| `get_allocated_amount_in_transaction_currency` | `self, allocated_amount, reference_doctype, reference_docname` | `` | Payment Entry could be in base currency while reference's payment schedule
is always in transaction currency.
E.g.
* SI with base=INR and currency=USD
* SI with payment schedule in USD
* PE in INR (accounting done in base currency) |
| `set_status` | `self` | `` |  |
| `set_total_in_words` | `self` | `` |  |
| `set_tax_withholding` | `self` | `` |  |
| `calculate_tax_withholding_net_total` | `self` | `` |  |
| `get_order_wise_tax_withholding_net_total` | `self` | `` |  |
| `apply_taxes` | `self` | `` |  |
| `set_amounts` | `self` | `` |  |
| `validate_amounts` | `self` | `` |  |
| `validate_received_amount` | `self` | `` |  |
| `set_received_amount` | `self` | `` |  |
| `set_amounts_after_tax` | `self` | `` |  |
| `set_amounts_in_company_currency` | `self` | `` |  |
| `calculate_base_allocated_amount_for_reference` | `self, d` | `` |  |
| `set_total_allocated_amount` | `self` | `` |  |
| `set_unallocated_amount` | `self` | `` |  |
| `set_exchange_gain_loss` | `self` | `` |  |
| `set_difference_amount` | `self` | `` |  |
| `get_included_taxes` | `self` | `` |  |
| `clear_unallocated_reference_document_rows` | `self` | `` |  |
| `set_title` | `self` | `` |  |
| `validate_transaction_reference` | `self` | `` |  |
| `set_remarks` | `self` | `` |  |
| `set_transaction_currency_and_rate` | `self` | `` |  |
| `build_gl_map` | `self` | `` |  |
| `make_gl_entries` | `self, cancel, adv_adj` | `` |  |
| `add_party_gl_entries` | `self, gl_entries` | `` |  |
| `make_advance_gl_entries` | `self, entry, cancel, update_outstanding` | `` |  |
| `add_advance_gl_entries` | `self, gl_entries, entry` | `` | If 'entry' is passed, GL entries only for that reference is added. |
| `get_dr_and_account_for_advances` | `self, reference` | `` |  |
| `add_advance_gl_for_reference` | `self, gl_entries, invoice` | `` |  |
| `add_bank_gl_entries` | `self, gl_entries` | `` |  |
| `add_tax_gl_entries` | `self, gl_entries` | `` |  |
| `add_deductions_gl_entries` | `self, gl_entries` | `` |  |
| `get_party_account_for_taxes` | `self` | `` |  |
| `get_value_in_transaction_currency` | `self, account_currency, gl_dict, field` | `` |  |
| `update_advance_paid` | `self` | `` |  |
| `on_recurring` | `self, reference_doc, auto_repeat_doc` | `` |  |
| `calculate_deductions` | `self, tax_details` | `` |  |
| `set_gain_or_loss` | `self, account_details` | `` |  |
| `get_exchange_rate` | `self` | `` |  |
| `initialize_taxes` | `self` | `` |  |
| `determine_exclusive_rate` | `self` | `` |  |
| `calculate_taxes` | `self` | `` |  |
| `get_current_tax_amount` | `self, tax` | `` |  |
| `get_current_tax_fraction` | `self, tax` | `` |  |
| `set_matched_unset_payment_requests_to_response` | `self` | `` | Find matched Payment Requests for those references which have no Payment Request set.

And set to `frappe.response` to show in the frontend for allocation. |
| `allocate_amount_to_references` | `self, paid_amount, paid_amount_change, allocate_payment_amount` | `` | Allocate `Allocated Amount` and `Payment Request` against `Reference` based on `Paid Amount` and `Outstanding Amount`.

:param paid_amount: Paid Amount / Received Amount.
:param paid_amount_change: Flag to check if `Paid Amount` is changed or not.
:param allocate_payment_amount: Flag to allocate amount or not. (Payment Request is also dependent on this flag) |
| `set_matched_payment_requests` | `self, matched_payment_requests` | `` | Set `Payment Request` against `Reference` based on `matched_payment_requests`.

:param matched_payment_requests: List of tuple of matched Payment Requests.

---
Example: [(reference_doctype, reference_name, allocated_amount, payment_request), ...] |





## Functions

### `get_matched_payment_request_of_references`
**Arguments:** `references`
**Decorators:** ``

**Docstring:**
```
Get those `Payment Requests` which are matched with `References`.

        - Amount must be same.
        - Only single `Payment Request` available for this amount.

Example: [(reference_doctype, reference_name, allocated_amount, payment_request), ...]
```
### `get_references_outstanding_amount`
**Arguments:** `references`
**Decorators:** ``

**Docstring:**
```
Fetch accurate outstanding amount of `References`.

    - If `Payment Term` is set, then fetch outstanding amount from `Payment Schedule`.
    - If `Payment Term` is not set, then fetch outstanding amount from `References` it self.

Example: {(reference_doctype, reference_name, payment_term): outstanding_amount, ...}
```
### `get_outstanding_of_references_with_payment_term`
**Arguments:** `references`
**Decorators:** ``

**Docstring:**
```
Fetch outstanding amount of `References` which have `Payment Term` set.

Example: {(reference_doctype, reference_name, payment_term): outstanding_amount, ...}
```
### `get_outstanding_of_references_with_no_payment_term`
**Arguments:** `references`
**Decorators:** ``

**Docstring:**
```
Fetch outstanding amount of `References` which have no `Payment Term` set.

        - Fetch outstanding amount from `References` it self.

Note: `None` is used for allocation of `Payment Request`
Example: {(reference_doctype, reference_name, None): outstanding_amount, ...}
```
### `get_payment_request_outstanding_set_in_references`
**Arguments:** `references`
**Decorators:** ``

**Docstring:**
```
Fetch outstanding amount of `Payment Request` which are set in `References`.

Example: {payment_request: outstanding_amount, ...}
```
### `validate_inclusive_tax`
**Arguments:** `tax, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_outstanding_reference_documents`
**Arguments:** `args, validate`
**Decorators:** ``

**Docstring:**
```

```
### `split_invoices_based_on_payment_terms`
**Arguments:** `outstanding_invoices, company`
**Decorators:** ``

**Docstring:**
```
Split a list of invoices based on their payment terms.
```
### `get_currency_data`
**Arguments:** `outstanding_invoices, company`
**Decorators:** ``

**Docstring:**
```
Get currency and conversion data for a list of invoices.
```
### `get_split_invoice_rows`
**Arguments:** `invoice, payment_term_template, exc_rates`
**Decorators:** ``

**Docstring:**
```
Split invoice based on its payment schedule table.
```
### `get_orders_to_be_billed`
**Arguments:** `posting_date, party_type, party, company, party_account_currency, company_currency, cost_center, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_negative_outstanding_invoices`
**Arguments:** `party_type, party, party_account, party_account_currency, company_currency, cost_center, condition`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_details`
**Arguments:** `company, party_type, party, date, cost_center`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_details`
**Arguments:** `account, date, cost_center`
**Decorators:** ``

**Docstring:**
```

```
### `get_company_defaults`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_outstanding_on_journal_entry`
**Arguments:** `voucher_no, party_type, party`
**Decorators:** ``

**Docstring:**
```

```
### `get_reference_details`
**Arguments:** `reference_doctype, reference_name, party_account_currency, party_type, party`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_entry`
**Arguments:** `dt, dn, party_amount, bank_account, bank_amount, party_type, payment_type, reference_date, created_from_payment_request`
**Decorators:** ``

**Docstring:**
```

```
### `get_open_payment_requests_for_references`
**Arguments:** `references`
**Decorators:** ``

**Docstring:**
```
Fetch all unpaid Payment Requests for the references. 

        - Each reference can have multiple Payment Requests. 


Example: {("Sales Invoice", "SINV-00001"): {"PREQ-00001": 1000, "PREQ-00002": 2000}}
```
### `allocate_open_payment_requests_to_references`
**Arguments:** `references, precision`
**Decorators:** ``

**Docstring:**
```
Allocate unpaid Payment Requests to the references. 

---
- Allocation based on below factors
    - Reference Allocated Amount
    - Reference Outstanding Amount (With Payment Terms or without Payment Terms)
    - Reference Payment Request's outstanding amount
---
- Allocation based on below scenarios
    - Reference's Allocated Amount == Payment Request's Outstanding Amount
        - Allocate the Payment Request to the reference
        - This PR will not be allocated further
    - Reference's Allocated Amount < Payment Request's Outstanding Amount
        - Allocate the Payment Request to the reference
        - Reduce the PR's outstanding amount by the allocated amount
        - This PR can be allocated further
    - Reference's Allocated Amount > Payment Request's Outstanding Amount
        - Allocate the Payment Request to the reference
        - Reduce Allocated Amount of the reference by the PR's outstanding amount
        - Create a new row for the remaining amount until the Allocated Amount is 0
            - Allocate PR if available
---
- Note:
    - Priority is given to the first Payment Request of respective references.
    - Single Reference can have multiple rows.
        - With Payment Terms or without Payment Terms
        - With Payment Request or without Payment Request
```
### `update_accounting_dimensions`
**Arguments:** `pe, doc`
**Decorators:** ``

**Docstring:**
```
Updates accounting dimensions in Payment Entry based on the accounting dimensions in the reference document
```
### `get_bank_cash_account`
**Arguments:** `doc, bank_account`
**Decorators:** ``

**Docstring:**
```

```
### `set_party_type`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```

```
### `set_party_account`
**Arguments:** `dt, dn, doc, party_type`
**Decorators:** ``

**Docstring:**
```

```
### `set_party_account_currency`
**Arguments:** `dt, party_account, doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_payment_type`
**Arguments:** `dt, doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_grand_total_and_outstanding_amount`
**Arguments:** `party_amount, dt, party_account_currency, doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_paid_amount_and_received_amount`
**Arguments:** `dt, party_account_currency, bank, outstanding_amount, payment_type, bank_amount, doc`
**Decorators:** ``

**Docstring:**
```

```
### `apply_early_payment_discount`
**Arguments:** `paid_amount, received_amount, doc, party_account_currency, reference_date`
**Decorators:** ``

**Docstring:**
```

```
### `set_pending_discount_loss`
**Arguments:** `pe, doc, discount_amount, base_total_discount_loss, party_account_currency`
**Decorators:** ``

**Docstring:**
```

```
### `split_early_payment_discount_loss`
**Arguments:** `pe, doc, valid_discounts`
**Decorators:** ``

**Docstring:**
```
Split early payment discount into Income Loss & Tax Loss.
```
### `get_total_discount_percent`
**Arguments:** `doc, valid_discounts`
**Decorators:** ``

**Docstring:**
```
Get total percentage and amount discount applied as a percentage.
```
### `add_income_discount_loss`
**Arguments:** `pe, doc, total_discount_percent`
**Decorators:** ``

**Docstring:**
```
Add loss on income discount in base currency.
```
### `add_tax_discount_loss`
**Arguments:** `pe, doc, total_discount_percentage`
**Decorators:** ``

**Docstring:**
```
Add loss on tax discount in base currency.
```
### `get_reference_as_per_payment_terms`
**Arguments:** `payment_schedule, dt, dn, doc, grand_total, outstanding_amount, party_account_currency`
**Decorators:** ``

**Docstring:**
```

```
### `get_paid_amount`
**Arguments:** `dt, dn, party_type, party, account, due_date`
**Decorators:** ``

**Docstring:**
```

```
### `make_payment_order`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `add_regional_gl_entries`
**Arguments:** `gl_entries, doc`
**Decorators:** ``

**Docstring:**
```

```

