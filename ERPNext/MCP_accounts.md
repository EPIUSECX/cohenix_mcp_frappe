# Model Context Profile: `accounts`

## 1. Module Overview

The `accounts` module is the financial backbone of ERPNext. It implements a complete double-entry accounting system, handling everything from the chart of accounts and general ledger to accounts receivable, accounts payable, and financial reporting.

The module's architecture is centered around a few key transactional documents (`Sales Invoice`, `Purchase Invoice`, `Journal Entry`, `Payment Entry`) that, upon submission, generate immutable `GL Entry` records. This ensures the integrity and auditability of the financial records. The module also includes a rich set of utilities for managing fiscal years, currencies, and party balances, as well as a comprehensive reporting engine.

## 2. File Structure and Key Components

The `accounts` module is extensive. The most critical components are the core DocTypes that drive the accounting processes.

```
erpnext/accounts/
├── doctype/
│   ├── gl_entry/
│   │   └── gl_entry.py             # Controller for the General Ledger Entry document.
│   ├── journal_entry/
│   │   └── journal_entry.py        # Controller for manual journal entries.
│   ├── sales_invoice/
│   │   └── sales_invoice.py        # Controller for Accounts Receivable.
│   ├── purchase_invoice/
│   │   └── purchase_invoice.py     # Controller for Accounts Payable.
│   ├── payment_entry/
│   │   └── payment_entry.py        # Controller for recording payments.
│   ├── account/
│   │   └── account.py              # Controller for the Account master (Chart of Accounts).
│   └── accounts_settings/
│       └── accounts_settings.py    # Singleton DocType for module-wide settings.
├── report/                         # Contains all standard financial reports.
└── utils.py                        # Core helper functions for accounting operations.
```

## 3. Key Classes and Functions

### `erpnext.accounts.doctype.gl_entry.gl_entry.GLEntry`
- This class represents a single, immutable entry in the general ledger. It is the lowest-level accounting record.
- **`validate()`**: Ensures that P&L accounts have a cost center and that the account is active and belongs to the correct company. It does not contain complex business logic, as `GL Entry` documents are almost always created by other, higher-level documents.

### `erpnext.accounts.doctype.journal_entry.journal_entry.JournalEntry`
- The primary document for creating manual GL entries.
- **`on_submit()`**: Triggers the creation of `GL Entry` records for each row in the `accounts` child table.
- **`validate()`**: Contains extensive validation logic to ensure that debits equal credits, that multi-currency transactions have valid exchange rates, and that references to other documents (like invoices) are valid.

### `erpnext.accounts.doctype.sales_invoice.sales_invoice.SalesInvoice`
- The core document for accounts receivable.
- **`on_submit()`**: A complex method that orchestrates several actions:
    1.  Updates the status of linked `Sales Order` or `Delivery Note` documents.
    2.  Updates the stock ledger if `update_stock` is checked (for sales returns or direct sales).
    3.  Calls `make_gl_entries()` to post the accounting entries to the general ledger.
    4.  Creates loyalty point entries if applicable.
- **`get_gl_entries()`**: Builds the list of `GL Entry` dictionaries to be created. This includes entries for the customer's accounts receivable, income accounts for each item, and tax accounts.

### `erpnext.accounts.doctype.purchase_invoice.purchase_invoice.PurchaseInvoice`
- The core document for accounts payable.
- **`on_submit()`**: Similar to `Sales Invoice`, this method updates linked `Purchase Order` or `Purchase Receipt` documents, updates the stock ledger, and calls `make_gl_entries()`.
- **`get_gl_entries()`**: Builds the list of `GL Entry` dictionaries, including entries for the supplier's accounts payable, expense or asset accounts for each item, and tax accounts.

### `erpnext.accounts.utils`
- **`get_fiscal_year(date, company)`**: A crucial utility that returns the active fiscal year for a given date and company. This is used throughout the system to ensure transactions are booked in the correct period.
- **`get_balance_on(account, date, ...)`**: Calculates and returns the balance for a given account as of a specific date by summing up all `GL Entry` records.
- **`reconcile_against_document(...)`**: A key function used by the payment reconciliation tool to link payments (`Payment Entry`, `Journal Entry`) to invoices.

## 4. Dependencies and Interactions

- **Frappe Framework**: The entire module is built on the Frappe ORM and controller lifecycle (`validate`, `on_submit`, etc.).
- **Stock Module**: Tightly integrated with the `stock` module. When `update_stock` is checked on an invoice, it creates `Stock Ledger Entry` records in addition to `GL Entry` records.
- **Buying & Selling Modules**: `Purchase Invoice` and `Sales Invoice` are central to the `buying` and `selling` modules, respectively, and are linked to orders, receipts, and deliveries.
- **Projects Module**: Invoices and journal entries can be linked to `Project` documents, allowing for project-based accounting.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.accounts.party`
- `get_party_details`: Fetches default details for a customer or supplier.
- `get_party_account`: Retrieves the default receivable or payable account for a party.
- `get_party_bank_account`: Gets the primary bank account for a party.
- `get_due_date`: Calculates the payment due date based on the party's payment terms.
- `get_address_tax_category`: Determines the tax category based on billing or shipping address.
- `set_taxes`: A generic function to calculate and set taxes on a transaction.
- `get_payment_terms_template`: Fetches the default payment terms for a party.

### `erpnext.accounts.report.utils`
- `get_invoiced_item_gross_margin`: Calculates the gross margin for a specific item on an invoice.

### `erpnext.accounts.doctype.journal_entry_template.journal_entry_template`
- `get_naming_series`: Gets the naming series for Journal Entry Templates.

### `erpnext.accounts.doctype.bank_statement_import.bank_statement_import`
- `convert_mt940_to_csv`: Converts an MT940 bank statement file to CSV format.
- `get_preview_from_template`: Shows a preview of data to be imported.
- `form_start_import`: Initiates the data import process from the form.
- `download_errored_template`: Downloads a CSV of rows that failed to import.
- `download_import_log`: Downloads the log of the import process.
- `get_import_status`: Checks the status of a background import job.
- `get_import_logs`: Retrieves the logs for a specific import.
- `upload_bank_statement`: Handles the file upload for bank statements.

### `erpnext.accounts.doctype.pos_closing_entry.pos_closing_entry`
- `retry`: Retries a failed POS closing entry.
- `get_invoices`: Fetches invoices for a given POS profile and period.

### `erpnext.accounts.doctype.bank_clearance.bank_clearance`
- `get_payment_entries`: Fetches payment entries to be cleared.
- `update_clearance_date`: Updates the clearance date for selected payment entries.

### `erpnext.accounts.doctype.journal_entry.journal_entry`
- `get_balance_for_periodic_accounting`: Gets account balances for periodic accounting.
- `get_balance`: Calculates the balance for a specific account.
- `get_outstanding_invoices`: Fetches outstanding invoices for a party.
- `get_default_bank_cash_account`: Gets the default bank or cash account for a company.
- `get_payment_entry_against_order`: Fetches payment entries linked to a sales/purchase order.
- `get_payment_entry_against_invoice`: Fetches payment entries linked to an invoice.
- `get_outstanding`: A generic function to get outstanding amounts.
- `get_party_account_and_currency`: Gets the account and currency for a party.
- `get_account_details_and_party_type`: Fetches details for an account.
- `get_exchange_rate`: Gets the exchange rate for a currency on a given date.
- `get_average_exchange_rate`: Gets the average exchange rate for an account.
- `make_inter_company_journal_entry`: Creates a journal entry for inter-company transactions.
- `make_reverse_journal_entry`: Creates a reversing journal entry.

### `erpnext.accounts.doctype.sales_invoice.sales_invoice`
- `set_missing_values`: Populates default values in the Sales Invoice form.
- `reset_mode_of_payments`: Clears the mode of payment table.
- `set_account_for_mode_of_payment`: Sets the default account for a mode of payment.
- `is_auto_fetch_timesheet_enabled`: Checks if timesheet auto-fetching is enabled.
- `add_timesheet_data`: Fetches and adds timesheet data to the invoice.
- `get_bank_cash_account`: Gets the bank/cash account for a mode of payment.
- `make_maintenance_schedule`: Creates a maintenance schedule from an invoice.
- `make_delivery_note`: Creates a delivery note from a sales invoice.
- `make_sales_return`: Creates a credit note (return) from a sales invoice.
- `make_inter_company_purchase_invoice`: Creates a purchase invoice in a target company.
- `get_loyalty_programs`: Fetches available loyalty programs for a customer.
- `create_invoice_discounting`: Creates an invoice discounting record.
- `create_dunning`: Creates a dunning record for an overdue invoice.

### `erpnext.accounts.doctype.purchase_invoice.purchase_invoice`
- `make_debit_note`: Creates a debit note (return) from a purchase invoice.
- `make_stock_entry`: Creates a stock entry from a purchase invoice.
- `change_release_date`: Changes the release date for a blocked invoice.
- `unblock_invoice`: Unblocks a held purchase invoice.
- `block_invoice`: Puts a hold on a purchase invoice.
- `make_inter_company_sales_invoice`: Creates a sales invoice in a target company.
- `make_purchase_receipt`: Creates a purchase receipt from a purchase invoice.

### `erpnext.accounts.utils`
- `get_fiscal_year`: Gets the fiscal year for a given date.
- `get_fiscal_year_filter_field`: Gets the appropriate fiscal year filter field.
- `get_balance_on`: Gets the balance of an account on a specific date.
- `add_ac`: A utility to add an account.
- `add_cc`: A utility to add a cost center.
- `get_company_default`: Gets a default value from the Company DocType.
- `get_companies`: Gets a list of all companies.
- `get_children`: Gets child records for a tree-structured DocType.
- `get_account_balances`: Gets the balances for multiple accounts.
- `update_cost_center`: Updates a cost center's details.
- `get_coa`: Gets the chart of accounts for a company.