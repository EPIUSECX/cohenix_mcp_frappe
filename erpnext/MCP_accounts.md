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

## 3. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development.

### 3.1. Server-Side (Python)

#### `erpnext.accounts.party`

-   **`get_party_details(party, party_type, company, ...)`**: A crucial whitelisted function that acts as a single point of entry for fetching a comprehensive set of details for a `Customer` or `Supplier`. It aggregates information like default accounts, addresses, contacts, price lists, and tax details. This is the primary function to call when you need to load party-specific information into a custom transaction.
-   **`get_party_account(party_type, party, company)`**: A whitelisted utility to get the default receivable or payable account for a given party and company. It intelligently searches the `Party Account` child table, then the party's group, and finally the company defaults.
-   **`get_due_date(posting_date, party_type, party, company, ...)`**: A whitelisted function that calculates the payment due date for a transaction by applying the party's default `Payment Terms Template`.

#### `erpnext.accounts.utils`

-   **`get_fiscal_year(date, company)`**: A fundamental, whitelisted utility that returns the active fiscal year document for a given date and company. This is essential for ensuring transactions are booked in the correct financial period.
-   **`get_balance_on(account, date, ...)`**: A whitelisted function that calculates and returns the balance for any given account as of a specific date by summing up all `GL Entry` records. It can handle group accounts and various filters.
-   **`reconcile_against_document(args)`**: The core server-side logic for linking payments to invoices. It handles the complex process of cancelling and resubmitting `Journal Entry` or `Payment Entry` documents to update their references.
-   **`get_outstanding_invoices(party_type, party, account, ...)`**: A utility function that queries the `Payment Ledger Entry` to get a list of all outstanding invoices for a specific party and account.

#### `erpnext.accounts.doctype.sales_invoice.sales_invoice.SalesInvoice` (Class Methods)

-   **`get_gl_entries()`**: This is a non-whitelisted, but critical, instance method. It constructs the list of all general ledger entries (debits and credits) for a sales invoice transaction. This is a key reference for understanding how financial postings are generated for sales.
-   **`on_submit()`**: The main controller method that orchestrates all actions upon invoice submission, including updating linked documents, creating `GL Entry` records, and updating stock ledgers. Reviewing this provides a complete map of the submission workflow.
-   **`make_sales_return(source_name, target_doc=None)`**: A whitelisted controller method to create a credit note (return) from a submitted sales invoice.

### 3.2. Client-Side (JavaScript)

#### `erpnext.accounts.SalesInvoiceController` (Class)

-   **`customer()`**: This client-side method triggers a call to the server-side `get_party_details` function and populates the form with the returned data. It's a prime example of how to dynamically fetch and set party-related information on a custom form.
-   **`make_payment_entry()`**: This method, attached to a custom button, demonstrates how to initiate the creation of a `Payment Entry` directly from a `Sales Invoice`, passing the necessary context.
-   **`make_sales_return()`**: This method shows how to use `frappe.model.open_mapped_doc` to create a return invoice, mapping the fields from the original document to the new one.

#### `erpnext.utils` (Client-Side)

-   **`map_current_doc(...)`**: While part of the core `erpnext.utils` library, it is heavily used in the `sales_invoice.js` script. It provides a standardized dialog for selecting a source document (like a Sales Order) and mapping its data onto the current form (`Sales Invoice`). This is a highly reusable pattern for creating documents from others.
-   **`get_party_details(...)`**: This client-side utility function is the counterpart to the server-side method. It handles the `frappe.call` and the subsequent setting of values on the form, providing a reusable client-side wrapper for fetching party data.

## 4. Dependencies and Interactions

- **Frappe Framework**: The entire module is built on the Frappe ORM and controller lifecycle (`validate`, `on_submit`, etc.).
- **Stock Module**: Tightly integrated with the `stock` module. When `update_stock` is checked on an invoice, it creates `Stock Ledger Entry` records in addition to `GL Entry` records.
- **Buying & Selling Modules**: `Purchase Invoice` and `Sales Invoice` are central to the `buying` and `selling` modules, respectively, and are linked to orders, receipts, and deliveries.
- **Projects Module**: Invoices and journal entries can be linked to `Project` documents, allowing for project-based accounting.