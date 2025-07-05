# Model Context Profile: `patches`

## 1. Module Overview

The `patches` module is not a functional module containing business logic. It is a repository for the actual patch scripts that are executed by the `frappe.modules.patch_handler` during a migration.

The module is organized into directories named after the Frappe version they belong to (e.g., `v13_0`, `v14_0`). Each of these directories contains Python files, where each file represents a single patch.

The execution of these patches is controlled by the `patches.txt` file in the root of the `frappe` app, which lists the dotted path to the patch functions to be executed.

## 2. File Index

-   **`__init__.py`**: An empty file that marks the directory as a Python module.
-   **`v*` directories**: Contain the individual Python patch files, organized by the major version in which they were introduced.

## 3. Public API / Callable Functions

This module does not contain any callable functions or a public API. The functions within the patch files are intended for single, idempotent execution by the patch handler.

## 4. Detailed Walkthrough

As this is a content-only module, there are no central code files to analyze. The key concept is that this directory serves as the storage location for all historical and current database migration scripts for the Frappe framework. Each patch file typically contains an `execute()` function that performs a specific data or schema modification.