# Model Context Profile: Setup

## 1. Module Overview

The `setup` module is a foundational module in ERPNext that contains the core master data and configuration documents required to set up and operate an ERPNext instance. It is not a functional module in the sense of managing transactions, but rather a repository for the essential building blocks of the system, such as organizational structure, master data classifications, and system-wide settings.

This module is the starting point for any new ERPNext implementation, as it is where companies, departments, item groups, customer groups, and other fundamental entities are defined.

## 2. Core Components

The `setup` module is extensive, but its core components can be grouped into several key areas.

### 2.1. Organizational Structure

These DocTypes define the legal and organizational hierarchy of the business.

-   **`Company`**:
    -   The central entity representing a legal business entity. It is a tree-structured DocType, allowing for the creation of parent and subsidiary companies.
    -   It holds critical default information, including the `default_currency`, `country`, `chart_of_accounts`, and default accounts for various transactions (e.g., `default_receivable_account`, `default_inventory_account`).
    -   The `Company` document is the primary link for almost all transactional data in the system.

-   **`Department`**:
    -   A tree-structured DocType used to model the internal organizational structure of a company (e.g., Sales, Marketing, Accounts).
    -   It is linked to employees and can be used for reporting and approval workflows.

-   **`Branch`**:
    -   Represents a physical branch or location of a company.

### 2.2. Master Data Classification

These DocTypes are used to categorize and group other master data, such as customers, suppliers, and items. They are all tree-structured, allowing for hierarchical classification.

-   **`Customer Group`**:
    -   Used to classify customers into groups (e.g., by region, industry, or size).
    -   Can hold default settings for `Price List`, `Payment Terms`, and receivable accounts that are applied to customers within that group.

-   **`Supplier Group`**:
    -   Similar to `Customer Group`, but for classifying suppliers.
    -   Can hold default payable accounts.

-   **`Item Group`**:
    -   Used to classify items into a hierarchy (e.g., Raw Materials, Finished Goods, Services).
    -   Can hold default accounts for inventory, cost of goods sold, and income, as well as default tax templates.

-   **`Territory`**:
    -   Used to classify customers, suppliers, and sales partners by geographical or business territory.
    -   Essential for sales management and reporting.

### 2.3. Configuration and Settings

This group of DocTypes is used to configure system-wide rules and behaviors.

-   **`Authorization Control` and `Authorization Rule`**:
    -   A powerful feature for setting up approval workflows based on the value of transactions.
    -   Allows for defining rules such as "Sales Invoices over $10,000 must be approved by an Accounts Manager."

-   **`Email Digest`**:
    -   A tool for creating and scheduling periodic summary emails of key business metrics (e.g., daily sales, weekly support tickets).

-   **`Terms and Conditions`**:
    -   A master for storing standard terms and conditions that can be fetched into transactional documents like quotations and invoices.

-   **`Holiday List`**:
    -   Defines a list of public holidays for a specific region, which is used in calculating working days for payroll, project management, and manufacturing.

## 3. Data Flow and Architecture

The `setup` module is at the top of the data hierarchy. The data created here is foundational and is used to provide default values and classifications for almost all other transactions in the system.

1.  A **`Company`** is created, which establishes the legal entity and its chart of accounts.
2.  **`Department`**, **`Customer Group`**, **`Item Group`**, etc., are created to define the organizational and data structure.
3.  When a new master document is created (e.g., a `Customer` or an `Item`), it is assigned to a group (e.g., `Customer Group`, `Item Group`).
4.  The group provides default values (e.g., default accounts, price lists) to the master document.
5.  When a transactional document is created (e.g., a `Sales Order`), it is linked to a `Company`. The master data selected (e.g., `Customer`, `Item`) then provides its default values to the transaction, which may have been inherited from its group in the `setup` module.

## 4. Architectural Significance

The `setup` module is the bedrock of ERPNext's multi-company and configurable nature. By centralizing the core master data and organizational structure, it provides a single source of truth for the entire system. The use of tree-structured DocTypes for classification allows for a high degree of flexibility and granularity in reporting and analysis.

The architecture of the `setup` module is designed to ensure that once the foundational data is correctly configured, the day-to-day transactional processes can run smoothly and consistently, with the correct defaults and classifications applied automatically. This reduces data entry errors and ensures data integrity across the system.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.setup.doctype.company.company`
- `check_if_transactions_exist`: Checks if any transactions are linked to the company before allowing certain changes.
- `create_default_tax_template`: Creates default tax templates for the company.
- `get_children`: Fetches child companies for the company tree view.
- `add_node`: Adds a new company to the tree.
- `get_default_company_address`: Fetches the default billing or shipping address for the company.
- `get_billing_shipping_address`: Fetches both billing and shipping addresses.
- `create_transaction_deletion_request`: Creates a request to delete all transactions for the company.

### `erpnext.setup.doctype.employee.employee`
- `deactivate_sales_person`: Deactivates the linked Sales Person record when an employee is deactivated.
- `create_user`: Creates a system user for the employee.
- `get_children`: Fetches child employees for the employee tree view.

### `erpnext.setup.doctype.department.department`
- `get_children`: Fetches child departments for the department tree view.
- `add_node`: Adds a new department to the tree.

### `erpnext.setup.doctype.holiday_list.holiday_list`
- `get_weekly_off_dates`: Gets the dates of weekly holidays for a given year.
- `get_supported_countries`: Gets a list of countries with pre-defined holiday lists.
- `get_local_holidays`: Fetches holidays for a specific country from an external source.
- `clear_table`: Clears the holidays table in the Holiday List document.
- `get_events`: Fetches holidays to be displayed on the calendar.

### `erpnext.setup.doctype.email_digest.email_digest`
- `get_users`: Fetches a list of users for the email digest.
- `send`: Manually sends the email digest.
- `get_digest_msg`: Gets the content of the digest email.

### `erpnext.setup.doctype.transaction_deletion_record.transaction_deletion_record`
- `start_deletion_tasks`: Starts the background jobs for deleting transactions.
- `get_doctypes_to_be_ignored`: Gets a list of DocTypes to be ignored during deletion.
- `is_deletion_doc_running`: Checks if a deletion process is currently running for a company.

### Other
- `erpnext.setup.demo.clear_demo_data`: Clears all demo data from the system.
- `erpnext.setup.doctype.global_defaults.global_defaults.get_defaults`: Gets the global default values.
- `erpnext.setup.doctype.terms_and_conditions.terms_and_conditions.get_terms_and_conditions`: Fetches and renders a Terms and Conditions template.
- `erpnext.setup.utils.get_exchange_rate`: Gets the exchange rate between two currencies.