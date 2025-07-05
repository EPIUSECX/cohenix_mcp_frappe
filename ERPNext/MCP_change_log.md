# Model Context Profile: Change Log

## 1. Module Overview

The **Change Log** module serves as a documentation repository that chronicles the version history of the ERPNext framework. Unlike other modules, it does not contain any functional DocTypes, controllers, or business logic. Its sole purpose is to provide a structured and version-controlled record of updates, new features, bug fixes, and breaking changes.

This module is essential for developers and system administrators to track the evolution of the ERPNext platform, understand the implications of upgrading to a new version, and review the history of changes made over time.

## 2. Core Concepts

### a. Version-Based Documentation

The module's structure is organized by major and minor version numbers. Each version has its own subdirectory (e.g., `v12/`, `v13/`), containing individual Markdown files for specific patch releases (e.g., `v13_1_0.md`, `v13_2_0.md`).

This approach provides a clear, chronological, and granular history of the framework's development.

### b. Content of Changelogs

While the specific content varies, each Markdown file typically details:
-   **New Features**: Descriptions of new functionalities added in a specific version.
-   **Bug Fixes**: A list of issues that have been resolved.
-   **Improvements**: Enhancements to existing features.
-   **Breaking Changes**: Important information about changes that might affect existing implementations or require manual intervention during an upgrade.

## 3. Data Model and Structure

The data model for this module is the file system itself. There are no database tables or DocTypes associated with it.

-   **Root Directory**: `erpnext/change_log/`
-   **Version Directories**: Subdirectories named according to the major version number (e.g., `v5/`, `v6/`, ... `v15/`).
-   **Changelog Files**: Markdown files within each version directory, named with the specific version number they document (e.g., `v13_0_0.md`).
-   **Current Version**: A `current/` directory likely points to or summarizes the latest changes.

## 4. Key Files

-   [`current/readme.md`](erpnext-develop/erpnext/change_log/current/readme.md): Likely contains information about the most recent release.
-   [`vX/vX_Y_Z.md`](erpnext-develop/erpnext/change_log/): The individual changelog files that form the core content of this module.

## 5. Integrations and Business Logic

This module has no direct integrations with other ERPNext modules in a functional sense. It does not execute any business logic, process transactions, or manage user data. Its value is purely informational, providing critical context for anyone working with or maintaining an ERPNext instance.

## 6. Callable Functions (`@frappe.whitelist()`)

This module has **no whitelisted functions**. It is a documentation-only module and does not expose any callable API methods.