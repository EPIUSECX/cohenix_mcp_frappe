# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_entry/test_payment_entry.py`

## Classes

### `TestPaymentEntry`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `tearDown` | `self` | `` |  |
| `get_journals_for` | `self, voucher_type, voucher_no` | `` |  |
| `test_payment_entry_against_order` | `self` | `` |  |
| `test_payment_against_sales_order_usd_to_inr` | `self` | `` |  |
| `test_payment_entry_for_blocked_supplier_invoice` | `self` | `` |  |
| `test_payment_entry_for_blocked_supplier_payments` | `self` | `` |  |
| `test_payment_entry_for_blocked_supplier_payments_today_date` | `self` | `` |  |
| `test_payment_entry_for_blocked_supplier_payments_past_date` | `self` | `` |  |
| `test_payment_entry_against_si_usd_to_usd` | `self` | `` |  |
| `test_payment_entry_against_pi` | `self` | `` |  |
| `test_payment_against_sales_invoice_to_check_status` | `self` | `` |  |
| `test_payment_entry_against_payment_terms` | `self` | `` |  |
| `test_payment_entry_against_payment_terms_with_discount_on_pi` | `self` | `` |  |
| `test_payment_entry_against_payment_terms_with_discount` | `self` | `` |  |
| `test_payment_entry_against_payment_terms_with_discount_amount` | `self` | `` |  |
| `test_payment_entry_multicurrency_si_with_base_currency_accounting_early_payment_discount` | `self` | `` | 1. Multi-currency SI with single currency accounting (company currency)
2. PE with early payment discount
3. Test if Paid Amount is calculated in company currency
4. Test if deductions are calculated in company currency

SI is in USD to document agreed amounts that are in USD, but the accounting is in base currency. |
| `test_payment_entry_multicurrency_accounting_si_with_early_payment_discount` | `self` | `` | 1. Multi-currency SI with multi-currency accounting
2. PE with early payment discount and also exchange loss
3. Test if Paid Amount is calculated in transaction currency
4. Test if deductions are calculated in base/company currency
5. Test if exchange loss is reflected in difference |
| `test_payment_against_purchase_invoice_to_check_status` | `self` | `` |  |
| `test_payment_entry_against_si_usd_to_inr` | `self` | `` |  |
| `test_payment_entry_against_si_usd_to_usd_with_deduction_in_base_currency` | `self` | `` |  |
| `test_payment_entry_retrieves_last_exchange_rate` | `self` | `` |  |
| `test_internal_transfer_usd_to_inr` | `self` | `` |  |
| `test_payment_against_negative_sales_invoice` | `self` | `` |  |
| `validate_gl_entries` | `self, voucher_no, expected_gle` | `` |  |
| `get_gle` | `self, voucher_no` | `` |  |
| `test_payment_entry_write_off_difference` | `self` | `` |  |
| `test_payment_entry_exchange_gain_loss` | `self` | `` |  |
| `test_payment_entry_against_sales_invoice_with_cost_centre` | `self` | `` |  |
| `test_payment_entry_against_purchase_invoice_with_cost_center` | `self` | `` |  |
| `test_payment_entry_account_and_party_balance_with_cost_center` | `self` | `` |  |
| `test_gl_of_multi_currency_payment_transaction` | `self` | `` |  |
| `test_multi_currency_payment_entry_with_taxes` | `self` | `` |  |
| `test_gl_of_multi_currency_payment_with_taxes` | `self` | `` |  |
| `test_payment_entry_against_onhold_purchase_invoice` | `self` | `` |  |
| `test_payment_entry_for_employee` | `self` | `` |  |
| `test_duplicate_payment_entry_allocate_amount` | `self` | `` |  |
| `test_duplicate_payment_entry_partial_allocate_amount` | `self` | `` |  |
| `test_details_update_on_reference_table` | `self` | `` |  |
| `test_overallocation_validation_on_payment_terms` | `self` | `` | Validate Allocation on Payment Entry based on Payment Schedule. Upon overallocation, validation error must be thrown. |
| `test_overallocation_validation_shouldnt_misfire` | `self` | `` | Overallocation validation shouldn't fire for Template without "Allocate Payment based on Payment Terms" enabled |
| `test_allocation_validation_for_sales_order` | `self` | `` |  |
| `test_outstanding_invoices_api` | `self` | `` | Test if `get_outstanding_reference_documents` fetches invoices in the right order. |
| `test_receive_payment_from_payable_party_type` | `self` | `` | Checks GL entries generated while receiving payments from a Payable Party Type. |
| `test_payment_against_partial_return_invoice` | `self` | `` | Checks GL entries generated for partial return invoice payments. |
| `test_ledger_entries_for_advance_as_liability` | `self` | `` |  |
| `test_advance_as_liability_against_order` | `self` | `` |  |
| `check_pl_entries` | `self` | `` |  |
| `check_gl_entries` | `self` | `` |  |
| `test_reverse_payment_reconciliation` | `self` | `` |  |
| `test_advance_reverse_payment_reconciliation` | `self` | `` |  |
| `test_opening_flag_for_advance_as_liability` | `self` | `` |  |
| `test_delete_linked_exchange_gain_loss_journal` | `self` | `` |  |





## Functions

### `create_payment_entry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_payment_terms_template`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_payment_terms_template_with_discount`
**Arguments:** `name, discount_type, discount, template_name`
**Decorators:** ``

**Docstring:**
```
Create a Payment Terms Template with %  or amount discount.
```
### `create_payment_term`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `create_customer`
**Arguments:** `name, currency`
**Decorators:** ``

**Docstring:**
```

```

