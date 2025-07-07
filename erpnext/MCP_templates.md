# Model Context Profile: Templates

## 1. Module Overview

The **Templates** module is a non-functional, toolchain module within ERPNext. It does not contain any DocTypes, reports, or direct business logic. Instead, its sole purpose is to house the Jinja2 templates and related front-end assets (CSS, JS) that define the presentation layer for various parts of the application.

This module is a central repository for UI components, ensuring a consistent and reusable approach to building user interfaces, web pages, email notifications, and print formats across the entire ERPNext platform.

## 2. Core Concepts

### Jinja2 Templating

The entire module is built around the Jinja2 templating engine. It makes extensive use of template inheritance, includes, and macros to create a modular and maintainable front-end architecture.

-   **Includes:** Small, reusable snippets of HTML (e.g., `address_row.html`, `itemised_tax_breakup.html`) are stored in the `includes/` directory and can be inserted into any other template.
-   **Macros:** The `includes/macros.html` file likely contains reusable Jinja2 macros for rendering common UI patterns, such as forms, tables, or buttons, with different data.
-   **Pages:** The `pages/` directory contains full-page templates that often have a corresponding Python file (e.g., `projects.py` for `projects.html`) to fetch and pass context data to the template.

### Separation of Concerns

The structure of this module enforces a clear separation between business logic (handled in the respective functional modules' Python files) and presentation (handled by these templates). A DocType's `.py` file will prepare the data, and a template from this module will be responsible for rendering it.

## 3. Key Directories and Their Purpose

The module is organized into several directories, each serving a distinct purpose:

-   **`pages/`:** Contains the primary templates for user-facing web pages within the application's portal. Examples include:
    -   `projects.html`: The main dashboard for viewing and managing projects.
    -   `order.html`: A page for viewing order details.
    -   `rfq.html`: The page for "Request for Quotation" interactions.

-   **`emails/`:** Holds the HTML templates for transactional emails sent by the system. Examples include:
    -   `daily_project_summary.html`: Template for the daily digest email for project updates.
    -   `confirm_appointment.html`: The email sent to confirm a scheduled appointment.
    -   `reorder_item.html`: Notification email for items that need to be reordered.

-   **`print_formats/`:** Contains reusable HTML partials used to construct the print views of various transactional documents. This ensures consistency across different print formats. Key includes are:
    -   `items.html`: A standard table for rendering line items.
    -   `taxes_and_charges.html`: A template for the taxes and charges table.
    -   `serial_and_batch_bundle.html`: A partial for displaying serial and batch number information.

-   **`form_grid/`:** Provides templates for rendering complex grid layouts within forms, offering more control over the presentation than the standard grid view. Examples:
    -   `bank_reconciliation_grid.html`
    -   `material_request_grid.html`

-   **`includes/`:** A general-purpose directory for a wide variety of reusable template components and partials that are shared across different pages and forms.

## 4. How It Works

When a user navigates to a web page or triggers an action that generates a print view or an email, the corresponding controller function in the source module is called. This function gathers the necessary data from the database and then calls Frappe's rendering engine, passing the path to the appropriate template from this `templates` module and the context data.

For example, when viewing a Sales Order, the system might use `print_formats/includes/items.html` to render the item table and `print_formats/includes/taxes.html` to render the tax details, combining them into a single, cohesive print document.

This modular approach allows for high reusability and makes it easier to maintain and customize the look and feel of the application without altering the core business logic of the functional modules.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`). These functions are typically used by the corresponding page's JavaScript to dynamically load data.

### `erpnext.templates.pages.projects`
- `get_task_html`: Fetches and renders the HTML for a list of tasks for a project.
- `get_timesheet_html`: Fetches and renders the HTML for a list of timesheets for a project.