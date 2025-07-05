# Model Context Profile: Domains

## 1. Module Overview

The **Domains** module in ERPNext serves as a configuration hub that tailors the user experience based on the selected business domain (e.g., Manufacturing, Retail, Services). It does not contain any functional DocTypes or business logic in the traditional sense. Instead, it holds a set of predefined configurations that are applied during the initial setup of an ERPNext instance.

The primary purpose of this module is to simplify the onboarding process by providing sensible defaults and a curated set of tools for specific industries, making the system more accessible and relevant to the user's business needs from the outset.

## 2. Core Concepts

### a. Domain-Specific Presets

The core concept is the use of domain-specific presets. When a user selects a domain like "Manufacturing" or "Retail" in the setup wizard, the system reads the corresponding Python file from this module and applies the configurations defined within it.

Each configuration file contains a `data` dictionary with several keys that control different aspects of the system:

-   **`desktop_icons`**: A list of DocTypes and modules that will be shown as icons on the Desk. This provides a focused workspace with the most relevant tools for that domain.
-   **`set_value`**: A list of tuples that directly set default values in various Settings DocTypes. For example, it can enable or disable the barcode field in `Stock Settings`.
-   **`properties`**: A list of dictionaries that modify the properties of a DocField in a specific DocType. For instance, it can make a field collapsible based on another field's value.
-   **`default_portal_role`**: Sets the default role for new portal users, typically "Customer".

### b. User Experience Customization

By applying these presets, the `domains` module fundamentally alters the user experience to match the operational focus of the selected industry. A user in the "Services" domain will see a Desk centered around projects and timesheets, while a "Retail" user will see a POS-centric layout.

## 3. Data Model and Structure

The data model for this module is the Python `data` dictionary within each domain file. There are no database tables or DocTypes associated with the `domains` module itself. It is purely a mechanism for applying initial configurations.

-   **Root Directory**: `erpnext/domains/`
-   **Configuration Files**: Python files named after the domain they configure. Each file must contain a `data` dictionary.

## 4. Key Files

### a. `distribution.py`

-   **File Path**: [`erpnext/domains/distribution.py`](erpnext-develop/erpnext/domains/distribution.py)
-   **Focus**: Emphasizes core trading operations.
-   **Desktop Icons**: `Item`, `Customer`, `Supplier`, `Sales Order`, `Purchase Order`.

### b. `manufacturing.py`

-   **File Path**: [`erpnext/domains/manufacturing.py`](erpnext-develop/erpnext/domains/manufacturing.py)
-   **Focus**: Tailored for production-centric businesses.
-   **Desktop Icons**: `Item`, `BOM`, `Work Order`, `Sales Order`.
-   **Properties**: Makes the "Manufacturing" section in the `Item` form collapsible, simplifying the view for non-manufacturing items.

### c. `retail.py`

-   **File Path**: [`erpnext/domains/retail.py`](erpnext-develop/erpnext/domains/retail.py)
-   **Focus**: Optimized for point-of-sale and retail operations.
-   **Desktop Icons**: `POS`, `Item`, `Customer`, `Sales Invoice`.

### d. `services.py`

-   **File Path**: [`erpnext/domains/services.py`](erpnext-develop/erpnext/domains/services.py)
-   **Focus**: Designed for project-based and service-oriented businesses.
-   **Desktop Icons**: `Project`, `Timesheet`, `Sales Invoice`, `Expense Claim`.
-   **Set Value**: Notably, it disables the `show_barcode_field` in `Stock Settings`, as barcodes are less relevant in a pure services context.

## 5. Integrations and Business Logic

The `domains` module does not contain business logic. Its integration is with the ERPNext setup wizard and the core Frappe framework that reads these configurations. It acts as a one-time configuration provider during the initial setup, influencing the default state of the system but not participating in its ongoing transactional logic.

## 6. Callable Functions (`@frappe.whitelist()`)

This module has **no whitelisted functions**. It is a data and configuration module and does not expose any callable API methods.