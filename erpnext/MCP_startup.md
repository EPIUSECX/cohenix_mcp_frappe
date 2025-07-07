# Model Context Profile: Startup

## 1. Module Overview

The `startup` module in ERPNext is a non-functional, toolchain-level module responsible for initializing the user's session and loading essential system data when the application boots up. It does not contain any user-facing DocTypes but consists of a collection of Python scripts that are executed by the Frappe framework during the boot process.

The primary purpose of this module is to populate the `bootinfo` object, which is a critical JavaScript object that contains all the necessary metadata, defaults, and user-specific information required to render the Desk UI and power the client-side application.

## 2. Core Components

The module's functionality is distributed across several Python scripts.

### 2.1. `boot.py`

This is the central script of the module. The `boot_session` function in this file is hooked into the Frappe framework's boot process and is responsible for the following:

-   **Loading System Defaults**: It fetches various system-wide settings from singleton DocTypes like `Selling Settings` and `Accounts Settings` and adds them to `bootinfo.sysdefaults`. This includes settings like the default territory, customer group, and over-billing allowance.
-   **Company Information**: It loads essential data for all `Company` records, such as the default currency, cost center, and country, and makes it available on the client-side.
-   **Fiscal Year**: It determines the current fiscal year for the user's default company and adds it to `bootinfo`.
-   **Page Info**: It populates `bootinfo.page_info` with the routes for various tree views (e.g., Chart of Accounts, Item Group Tree), enabling the Desk to render these pages correctly.
-   **User Information**: It links the logged-in user to their corresponding `Employee` record.

### 2.2. `notifications.py`

This script defines the configuration for the notification indicators that appear in the Desk's module icons.

-   **`get_notification_config()`**: This function returns a dictionary that specifies which documents should be counted for notifications. For each DocType, it defines a set of filters to identify "open" or "pending" documents. For example, it configures notifications for open `Issues`, overdue `Tasks`, and submitted `Sales Orders` that are not yet completed.

### 2.3. `leaderboard.py`

This script defines the data sources and configurations for the leaderboards displayed on the Desk.

-   **`get_leaderboards()`**: This function returns a dictionary that defines several leaderboards, such as "Top Customers", "Top Selling Items", and "Top Sales Partners".
-   For each leaderboard, it specifies:
    -   The fields to be displayed (e.g., `total_sales_amount`, `outstanding_amount`).
    -   The method used to fetch the data (e.g., `erpnext.startup.leaderboard.get_all_customers`).
    -   The icon to be displayed.
-   The script also contains the corresponding data-fetching functions that query the database to get the leaderboard data.

### 2.4. `filters.py`

This script defines custom filters that can be used in reports and list views.

-   **`get_filters_config()`**: This function returns a dictionary that defines custom filters. For example, it defines the "Fiscal Year" filter, which allows users to filter date fields in reports based on a selected fiscal year.

### 2.5. `__init__.py`

The `__init__.py` file in this module defines the `user_defaults`, which maps fields like `Company` and `Territory` to their corresponding user default settings.

## 3. Data Flow and Architecture

The `startup` module operates at the beginning of the user session lifecycle.

1.  When a user logs in, the Frappe framework initiates the boot process.
2.  The `boot_session` function in `erpnext.startup.boot` is called.
3.  This function queries the database for various system settings and master data.
4.  It populates the `bootinfo` object with this data.
5.  The `bootinfo` object is then sent to the client-side as a JSON object.
6.  The client-side application (built with Vue.js) uses the data in `bootinfo` to:
    -   Render the Desk UI.
    -   Set default values in forms.
    -   Configure notifications and leaderboards.
    -   Apply user-specific permissions and settings.

## 4. Architectural Significance

The `startup` module is a critical component of the ERPNext architecture that bridges the gap between the server-side database and the client-side application. By pre-loading a significant amount of essential data into the `bootinfo` object, it improves the performance and responsiveness of the user interface, as the client does not need to make numerous individual API calls to fetch this data.

This module exemplifies the "single page application" (SPA) architecture of the Frappe Desk. It demonstrates how a large amount of server-side state can be efficiently transferred to the client to create a rich and interactive user experience. The use of hooks allows ERPNext to extend the core Frappe boot process with its own application-specific data, showcasing the modularity and extensibility of the framework.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`). These functions are primarily used to fetch data for the leaderboards on the Desk.

### `erpnext.startup.leaderboard`
- `get_all_customers`: Fetches a list of top customers based on sales or outstanding amount.
- `get_all_items`: Fetches a list of top-selling items based on quantity or amount.
- `get_all_suppliers`: Fetches a list of top suppliers based on purchase amount or outstanding amount.
- `get_all_sales_partner`: Fetches a list of top sales partners based on commission or sales amount.
- `get_all_sales_person`: Fetches a list of top sales people based on sales amount.