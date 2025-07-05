# Model Context Profile: Patches

## 1. Module Overview

The **Patches** module in ERPNext is a crucial component of the framework's upgrade and migration system. It does not contain any runtime application logic, DocTypes, or controllers. Instead, it is a repository for small, single-use Python scripts, known as "patches," that are executed during the `bench migrate` process.

The primary purpose of this module is to manage data and schema migrations between different versions of ERPNext. These scripts handle changes that are too complex for the standard schema synchronization mechanism, ensuring data integrity and a smooth transition when the application is updated.

## 2. Core Concepts

### a. Data and Schema Migration

When a new version of ERPNext is released, it may include changes to the database schema that go beyond simple additions of fields or DocTypes. These can include:
-   **Renaming DocTypes or fields**: For example, `v11_0/rename_supplier_type_to_supplier_group.py` changes a field name while preserving the data.
-   **Data Transformation**: Moving data from one field or DocType to another, like in `v12_0/move_credit_limit_to_customer_credit_limit.py`.
-   **Complex Data Updates**: Performing calculations or updates on existing data that cannot be done with a simple SQL `UPDATE` statement.
-   **Deprecation and Cleanup**: Removing obsolete DocTypes, fields, or configuration data, as seen in `v13_0/delete_old_sales_reports.py`.

### b. Patch Execution

Patches are executed automatically by the `bench migrate` command. The framework keeps track of which patches have already been run for a given site in the `tabPatch Log` table in the database. This ensures that each patch is executed only once.

The patches are organized into version-specific directories (e.g., `v13_0`, `v14_0`), and they are executed in a specific order to ensure that dependencies between migrations are handled correctly.

## 3. Data Model and Structure

The data model for this module is the file system itself, specifically the directory structure that organizes the patch files.

-   **Root Directory**: `erpnext/patches/`
-   **Version Directories**: Subdirectories named according to the ERPNext version they apply to (e.g., `v13_0/`).
-   **Patch Files**: Python files within each version directory. Each file must contain an `execute()` function, which is the entry point for the patch logic.

## 4. Key Files

The key files are the individual patch scripts themselves. The naming convention of these files is highly descriptive, making it easy to understand their purpose. For example:

-   [`v10_0/rename_price_to_rate_in_pricing_rule.py`](erpnext-develop/erpnext/patches/v10_0/rename_price_to_rate_in_pricing_rule.py): A patch from version 10 that renames a field in the `Pricing Rule` DocType.
-   [`v13_0/add_missing_fg_item_for_stock_entry.py`](erpnext-develop/erpnext/patches/v13_0/add_missing_fg_item_for_stock_entry.py): A patch from version 13 that fixes data integrity by adding a missing value to `Stock Entry` documents.
-   [`v15_0/delete_ecommerce_doctypes.py`](erpnext-develop/erpnext/patches/v15_0/delete_ecommerce_doctypes.py): A patch from version 15 that removes deprecated DocTypes related to the old e-commerce module.

## 5. Integrations

The `patches` module is tightly integrated with the Frappe Framework's command-line interface (CLI) and the `bench` utility.
-   **`bench migrate`**: This is the primary command that discovers and executes the patches in this module.
-   **Database**: The patches directly interact with the database to perform data manipulation and schema changes.

This module has no direct runtime integrations with other ERPNext modules but is essential for the long-term maintenance and evolution of the entire application.

## 6. Callable Functions (`@frappe.whitelist()`)

This module has **no whitelisted functions**. It is a toolchain module for the `bench migrate` command and does not expose any callable API methods.