# Model Context Profile: WWW

## 1. Module Overview

The **www** module is a non-functional, toolchain module that contains the files for the public-facing website and portal of the ERPNext application. It follows the standard Frappe Framework convention for creating web pages, where each subdirectory corresponds to a URL endpoint.

This module does not contain any DocTypes. Instead, it provides the presentation layer (HTML, CSS, JS) and server-side controllers (`.py` files) that interact with the functional DocTypes from other modules (e.g., `Issue` from Support, `Item` from Stock). Its purpose is to create a user-friendly interface for external users like customers, suppliers, or students.

## 2. Core Concepts

### Frappe Web Pages

The module is built entirely on the Frappe Framework's web page functionality. The key principles are:
-   **Directory-based Routing:** Each folder within the `www` directory automatically becomes a URL route. For example, the files in `/www/support/` are accessible at the `/support` URL.
-   **Standard File Structure:** Each page typically consists of:
    -   `index.html`: A Jinja2 template that defines the structure and content of the page.
    -   `index.py`: A Python script that acts as the server-side controller. It contains a `get_context` method that fetches data from the database and passes it to the `index.html` template for rendering.
    -   `index.js`: An optional JavaScript file for client-side interactivity.
    -   `index.css`: An optional CSS file for page-specific styling.

### Separation of Concerns

This module provides a clear separation between the application's core business logic (defined in functional modules like Accounts, Stock, etc.) and the public-facing presentation layer. The Python controllers in this module are responsible for querying the necessary data from other DocTypes and preparing it for display, but they do not contain the primary business logic themselves.

## 3. Key Directories and Their Purpose

The subdirectories within the `www` module represent the different pages available on the ERPNext web portal:

-   **`support/`:** Provides the customer-facing support portal. The `index.py` likely fetches a list of `Issues` submitted by the logged-in user, and the `index.html` template renders them.
-   **`book_appointment/`:** A web page for users to schedule appointments. This page's controller would interact with the `Patient Appointment` DocType from the Healthcare module to check for available time slots and create new appointment documents.
-   **`lms/`:** A portal for the Learning Management System. This would render content from DocTypes like `Course` and `Program`.
-   **`all-products/` & `shop-by-category/`:** These pages are part of the e-commerce functionality. They query `Item` and `Item Group` DocTypes to display product listings for the online store.
-   **`payment_setup_certification.html`:** A specific page likely used for a certification process related to payment gateway integrations.

## 4. How It Works

1.  **Request:** A user navigates to a URL, for example, `https://your-erpnext-site.com/support`.
2.  **Routing:** The Frappe Framework identifies that this URL corresponds to the `erpnext/www/support/` directory.
3.  **Controller Execution:** The `get_context` method in `erpnext/www/support/index.py` is executed. This method fetches the relevant data for the logged-in user (e.g., their support tickets).
4.  **Rendering:** The data returned by `get_context` is passed as a context dictionary to the `erpnext/www/support/index.html` Jinja2 template.
5.  **Response:** The rendered HTML page is sent back to the user's browser.

This architecture allows for the creation of rich, data-driven web pages that are seamlessly integrated with the core ERP data, providing a powerful portal for external stakeholders.

## 5. Callable Functions (`@frappe.whitelist()`)

This module has **no whitelisted functions**. The Python files in this module are used as server-side controllers to provide context to web page templates and do not expose a direct, callable API to the client.