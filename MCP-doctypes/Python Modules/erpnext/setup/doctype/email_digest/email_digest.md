# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/email_digest/email_digest.py`

## Classes

### `EmailDigest`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `get_users` | `self` | `` | get list of users |
| `send` | `self` | `` |  |
| `get_msg_html` | `self` | `` | Build email digest content |
| `set_title` | `self, context` | `` | Set digest title |
| `set_style` | `self, context` | `` | Set standard digest style |
| `get_notifications` | `self` | `` | Get notifications for user |
| `get_calendar_events` | `self` | `` | Get calendar events for given user |
| `get_todo_list` | `self, user_id` | `` | Get to-do list |
| `get_todo_count` | `self, user_id` | `` | Get count of Todo |
| `get_issue_list` | `self, user_id` | `` | Get issue list |
| `get_issue_count` | `self` | `` | Get count of Issue |
| `get_project_list` | `self, user_id` | `` | Get project list |
| `get_project_count` | `self` | `` | Get count of Project |
| `set_accounting_cards` | `self, context` | `` | Create accounting cards if checked |
| `get_income` | `self` | `` | Get income for given period |
| `get_income_year_to_date` | `self` | `` | Get income to date |
| `get_expense_year_to_date` | `self` | `` | Get income to date |
| `get_year_to_date_balance` | `self, root_type, fieldname` | `` | Get income to date |
| `get_bank_balance` | `self` | `` |  |
| `get_credit_balance` | `self` | `` |  |
| `get_payables` | `self` | `` |  |
| `get_invoiced_amount` | `self` | `` |  |
| `get_expenses_booked` | `self` | `` |  |
| `get_period_amounts` | `self, accounts, fieldname` | `` | Get amounts for current and past periods |
| `get_sales_orders_to_bill` | `self` | `` | Get value not billed |
| `get_sales_orders_to_deliver` | `self` | `` | Get value not delivered |
| `get_purchase_orders_to_receive` | `self` | `` | Get value not received |
| `get_purchase_orders_to_bill` | `self` | `` | Get purchase not billed |
| `get_type_balance` | `self, fieldname, account_type, root_type` | `` |  |
| `get_roots` | `self, root_type` | `` |  |
| `get_root_type_accounts` | `self, root_type` | `` |  |
| `get_purchase_order` | `self` | `` |  |
| `get_sales_order` | `self` | `` |  |
| `get_pending_purchase_orders` | `self` | `` |  |
| `get_pending_sales_orders` | `self` | `` |  |
| `get_sales_invoice` | `self` | `` |  |
| `get_purchase_invoice` | `self` | `` |  |
| `get_new_quotations` | `self` | `` |  |
| `get_pending_quotations` | `self` | `` |  |
| `get_summary_of_pending` | `self, doc_type, fieldname, getfield` | `` |  |
| `get_summary_of_pending_quotations` | `self, fieldname` | `` |  |
| `get_summary_of_doc` | `self, doc_type, fieldname` | `` |  |
| `get_total_on` | `self, doc_type, from_date, to_date` | `` |  |
| `get_from_to_date` | `self` | `` |  |
| `set_dates` | `self` | `` |  |
| `get_next_sending` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `fmt_money` | `self, value, absol` | `` |  |
| `get_purchase_orders_items_overdue_list` | `self` | `` |  |





## Functions

### `send`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_digest_msg`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `get_incomes_expenses_for_period`
**Arguments:** `account, from_date, to_date`
**Decorators:** ``

**Docstring:**
```
Get amounts for current and past periods
```
### `get_count_for_period`
**Arguments:** `account, fieldname, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_future_date_for_calendaer_event`
**Arguments:** `frequency`
**Decorators:** ``

**Docstring:**
```

```

