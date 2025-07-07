# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/report/accounts_receivable/accounts_receivable.py`

## Classes

### `ReceivablePayableReport`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, filters` | `` |  |
| `run` | `self, args` | `` |  |
| `set_defaults` | `self` | `` |  |
| `get_data` | `self` | `` |  |
| `fetch_ple_in_buffered_cursor` | `self` | `` |  |
| `fetch_ple_in_unbuffered_cursor` | `self` | `` |  |
| `build_voucher_dict` | `self, ple` | `` |  |
| `init_voucher_balance` | `self, ple` | `` |  |
| `get_invoices` | `self, ple` | `` |  |
| `init_subtotal_row` | `self, party` | `` |  |
| `get_currency_fields` | `self` | `` |  |
| `get_voucher_balance` | `self, ple` | `` |  |
| `update_voucher_balance` | `self, ple` | `` |  |
| `update_sub_total_row` | `self, row, party` | `` |  |
| `append_subtotal_row` | `self, party` | `` |  |
| `build_data` | `self` | `` |  |
| `append_row` | `self, row` | `` |  |
| `set_invoice_details` | `self, row` | `` |  |
| `set_delivery_notes` | `self, row` | `` |  |
| `build_delivery_note_map` | `self` | `` |  |
| `get_invoice_details` | `self` | `` |  |
| `set_party_details` | `self, row` | `` |  |
| `allocate_outstanding_based_on_payment_terms` | `self, row` | `` |  |
| `get_payment_terms` | `self, row` | `` |  |
| `append_payment_term` | `self, row, d, term, company_currency` | `` |  |
| `allocate_closing_to_term` | `self, row, term, key` | `` |  |
| `allocate_extra_payments_or_credits` | `self, row` | `` |  |
| `get_future_payments` | `self` | `` |  |
| `get_future_payments_from_payment_entry` | `self` | `` |  |
| `get_future_payments_from_journal_entry` | `self` | `` |  |
| `allocate_future_payments` | `self, row` | `` |  |
| `get_return_entries` | `self` | `` |  |
| `set_ageing` | `self, row` | `` |  |
| `get_ageing_data` | `self, entry_date, row` | `` |  |
| `prepare_ple_query` | `self` | `` |  |
| `get_sales_invoices_or_customers_based_on_sales_person` | `self` | `` |  |
| `prepare_conditions` | `self` | `` |  |
| `get_cost_center_conditions` | `self` | `` |  |
| `add_common_filters` | `self` | `` |  |
| `add_customer_filters` | `self` | `` |  |
| `add_supplier_filters` | `self` | `` |  |
| `get_hierarchical_filters` | `self, doctype, key` | `` |  |
| `add_accounting_dimensions_filters` | `self` | `` |  |
| `is_invoice` | `self, ple` | `` |  |
| `get_party_details` | `self, party` | `` |  |
| `get_columns` | `self` | `` |  |
| `add_column` | `self, label, fieldname, fieldtype, options, width` | `` |  |
| `setup_ageing_columns` | `self` | `` |  |
| `get_chart_data` | `self` | `` |  |
| `get_exchange_rate_revaluations` | `self` | `` |  |





## Functions

### `execute`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_customer_group_with_children`
**Arguments:** `customer_groups`
**Decorators:** ``

**Docstring:**
```

```

