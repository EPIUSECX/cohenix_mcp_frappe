# Model Context Profile: Controllers

## 1. Module Overview

The **Controllers** module in ERPNext is a central hub for shared business logic that governs the behavior of transactional documents. Unlike modules that define specific user-facing features, the `controllers` module provides a set of Python classes that encapsulate reusable logic for domains such as accounting, stock management, buying, and selling.

DocTypes across the ERPNext application inherit from these controller classes to ensure consistent validation, calculation, and processing. This architectural pattern is fundamental to the framework's design, promoting code reuse and maintainability.

## 2. Core Concepts

### a. Inheritance-Based Logic Sharing

The primary concept is the use of a class inheritance hierarchy to share and extend functionality. A typical transactional DocType in ERPNext (e.g., `Sales Invoice`) will have a controller class that inherits from one of the base controllers in this module. This allows it to access a rich set of pre-built methods for common tasks.

The typical inheritance chain is:
`TransactionBase` -> `AccountsController` -> `StockController` -> `SellingController` / `BuyingController`

-   **`TransactionBase`**: Provides the most fundamental methods, likely from the core Frappe framework.
-   **`AccountsController`**: Adds logic for accounting entries, currency, taxes, and payment schedules.
-   **`StockController`**: Extends the `AccountsController` with logic for inventory management, including stock ledger entries, warehouse validation, and serial/batch number handling.
-   **`BuyingController` / `SellingController`**: Provide the final layer of specific logic for procurement and sales workflows, respectively.

### b. Centralized Business Rules

By centralizing logic in these controllers, ERPNext ensures that critical business rules are applied consistently. For example, the logic for calculating taxes, validating against a budget, or updating stock levels is defined once in a controller and then used by all relevant documents.

### c. Separation of Concerns

The module demonstrates a clear separation of concerns. For instance, the complex logic for tax calculation is encapsulated within its own file, [`taxes_and_totals.py`](erpnext-develop/erpnext/controllers/taxes_and_totals.py), and is invoked by the other controllers. This makes the codebase more modular and easier to understand.

## 3. Key Controller Classes

### a. `AccountsController`

-   **File Path**: [`erpnext/controllers/accounts_controller.py`](erpnext-develop/erpnext/controllers/accounts_controller.py)
-   **Purpose**: The foundational controller for all documents with a financial impact.
-   **Key Responsibilities**:
    -   Managing currency conversion (`conversion_rate`).
    -   Validating fiscal years and party accounts.
    -   Calculating taxes and totals by invoking the `calculate_taxes_and_totals` class.
    -   Handling payment schedules and due dates.
    -   Managing advance payments and reconciliations.

### b. `StockController`

-   **File Path**: [`erpnext/controllers/stock_controller.py`](erpnext-develop/erpnext/controllers/stock_controller.py)
-   **Inherits From**: `AccountsController`
-   **Purpose**: Manages all inventory-related operations.
-   **Key Responsibilities**:
    -   Creating and managing Stock Ledger Entries (`make_sl_entries`).
    -   Validating warehouses and serialized/batched items.
    -   Handling quality inspections.
    -   Managing logic for internal stock transfers.
    -   Orchestrating the reposting of future stock entries to maintain correct valuations.

### c. `SellingController`

-   **File Path**: [`erpnext/controllers/selling_controller.py`](erpnext-develop/erpnext/controllers/selling_controller.py)
-   **Inherits From**: `StockController`
-   **Purpose**: Provides logic specific to sales documents (`Quotation`, `Sales Order`, `Delivery Note`, `Sales Invoice`).
-   **Key Responsibilities**:
    -   Validating selling prices and maximum discounts.
    -   Calculating sales commissions and contributions.
    -   Managing customer and lead details.
    -   Updating reserved quantity in `Sales Order`.
    -   Handling product bundles and packing lists.

### d. `BuyingController`

-   **File Path**: [`erpnext/controllers/buying_controller.py`](erpnext-develop/erpnext/controllers/buying_controller.py)
-   **Inherits From**: `SubcontractingController` (which likely inherits from `StockController`)
-   **Purpose**: Provides logic specific to purchasing documents (`Supplier Quotation`, `Purchase Order`, `Purchase Receipt`, `Purchase Invoice`).
-   **Key Responsibilities**:
    -   Validating supplier status (e.g., on hold).
    -   Updating the `last_purchase_rate` for items.
    -   Managing fixed asset creation from purchase documents.
    -   Handling purchase returns and debit notes.
    -   Orchestrating subcontracting workflows.

### e. `taxes_and_totals.py`

-   **File Path**: [`erpnext/controllers/taxes_and_totals.py`](erpnext-develop/erpnext/controllers/taxes_and_totals.py)
-   **Purpose**: A dedicated utility for all tax and total calculations.
-   **Key Responsibilities**:
    -   Calculating item-wise taxes based on templates and rules.
    -   Handling inclusive and exclusive tax calculations.
    -   Applying discounts to net total or grand total.
    -   Calculating rounding adjustments.
    -   Generating the itemised tax breakup for print formats.

## 4. Integrations

The `controllers` module is the primary integration point between different domains. For example, the `StockController` integrates with the `AccountsController` to ensure that stock movements result in the correct accounting entries. The `SellingController` and `BuyingController` integrate with the `StockController` to manage inventory levels based on sales and purchases. This layered approach ensures a cohesive and interconnected system.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.controllers.accounts_controller`
- `apply_shipping_rule`: Applies a shipping rule to a transaction.
- `set_advances`: Fetches and sets advance payments to be adjusted.
- `repost_accounting_entries`: A utility to repost GL entries for a document.
- `get_tax_rate`: Gets the rate for a specific tax account head.
- `get_default_taxes_and_charges`: Fetches the default tax template for a company or master.
- `get_taxes_and_charges`: Fetches the applied taxes for a specific transaction.
- `get_payment_terms`: Gets the payment terms for a party.
- `get_payment_term_details`: Gets the details of a specific payment term template.
- `update_child_qty_rate`: Updates quantities and rates in a child table.

### `erpnext.controllers.stock_controller`
- `show_accounting_ledger_preview`: Shows a preview of the accounting ledger entries for a stock transaction.
- `show_stock_ledger_preview`: Shows a preview of the stock ledger entries.
- `check_item_quality_inspection`: Checks if a quality inspection is required for an item.
- `make_quality_inspections`: Creates Quality Inspection documents for a transaction.

### `erpnext.controllers.subcontracting_controller`
- `get_current_stock`: Gets the current stock of an item at a supplier's warehouse.
- `make_rm_stock_entry`: Creates a stock entry for raw materials in a subcontracting workflow.
- `get_materials_from_supplier`: Fetches raw materials available with a subcontractor.

### `erpnext.controllers.item_variant`
- `get_variant`: Gets an existing item variant based on attributes.
- `create_variant`: Creates a new item variant.
- `enqueue_multiple_variant_creation`: Creates multiple variants in a background job.
- `create_variant_doc_for_quick_entry`: Creates a variant from the quick entry form.

### `erpnext.controllers.queries`
- This file contains a large number of whitelisted functions that are used to power search fields (link fields) throughout the application. Each function provides a filtered list of documents for a specific context (e.g., `get_employees_for_department`, `get_leads_for_opportunity`, `get_items_for_quotation`).

### `erpnext.controllers.sales_and_purchase_return`
- `get_payment_data`: Fetches payment data related to an invoice for processing returns.
- `get_invoice_item_returned_qty`: Gets the already returned quantity for an invoice item.
- `is_invoice_returnable`: Checks if an invoice is eligible for return.

### `erpnext.controllers.taxes_and_totals`
- `get_round_off_applicable_accounts`: Gets accounts where rounding can be applied.
- `get_rounding_tax_settings`: Gets the system settings for rounding taxes.