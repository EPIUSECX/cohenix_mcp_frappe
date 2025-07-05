# Model Context Profile: `modules`

## 1. Module Overview

The `modules` module is a meta-module responsible for the discovery, loading, and management of other modules (apps) and their constituent parts (DocTypes, Reports, Pages, etc.) within the Frappe Framework. It provides the core utilities that allow the framework to be extensible.

Key functionalities are expected to include:
-   Loading DocType controllers and other module-level code.
-   Handling the export of DocTypes and other metadata to JSON files.
-   Providing utilities to get lists of modules, DocTypes, and other entities.
-   Managing patch execution and module installation/uninstallation hooks.

## 2. File Index

-   **`__init__.py`**: Exports all functions from `utils.py` to the `frappe.modules` namespace.
-   **`export_file.py`**: Contains the logic for exporting a document's metadata to a `.json` file within its module directory.
-   **`import_file.py`**: Contains the logic for importing a document from a `.json` file, creating or updating the record in the database.
-   **`patch_handler.py`**: Manages the execution of patches, which are small Python scripts used to apply data or schema changes during a `bench migrate`.
-   **`utils.py`**: Provides various utility functions for working with modules, including loading module controllers, exporting customizations, and creating boilerplate code.

## 3. Public API / Callable Functions

-   **`frappe.modules.export_to_files(...)`**: Exports a list of documents to their respective module folders as JSON files.
-   **`frappe.modules.import_files(...)`**: Imports documents from JSON files within a module's folder structure.
-   **`frappe.modules.reload_doc(module, doctype, docname)`**: A key function used during development to reload a document's definition from its JSON file into the database.
-   **`frappe.modules.patch_handler.run_all()`**: The main function called during `bench migrate` to find and execute all pending patches.
-   **`frappe.modules.utils.load_doctype_module(doctype)`**: A crucial function that dynamically imports the Python controller file for a given DocType.

## 4. Detailed Walkthrough

### `export_file.py`

This module is responsible for serializing a document's data into a structured format on the filesystem. This is a cornerstone of Frappe's "metadata in files" philosophy, which allows for version control of DocTypes and other metadata.

-   **`export_to_files(...)` / `write_document_file(...)`**: These functions orchestrate the export process. When a "standard" DocType (one that is part of an app, not a custom one) is saved, these functions are called.
-   **Folder Structure**: A standard folder structure is created for each exported document: `[app]/[module]/[doctype]/[docname]/`.
-   **JSON Serialization**: The document's data is converted to a dictionary using `doc.as_dict()`, stripped of default fields to keep the file clean, and then written to a `.json` file (e.g., `[docname].json`) inside its folder.
-   **Code Files**: If the document has associated code (e.g., a DocType's Python controller or a Report's script), the `write_code_files` function extracts the content from the document's fields (e.g., `controller`, `script`) and saves it into separate files with the appropriate extension (e.g., `[docname].py`, `[docname].js`). The code is then removed from the JSON data to avoid duplication.

### `import_file.py`

This module handles the reverse process: reading the `.json` files and synchronizing their contents with the database. This is what happens during a `bench migrate` or when a developer uses `bench --site {site} reload-doc`.

-   **`import_file_by_path(...)`**: This is the core import function. It has intelligent logic to decide whether an import is necessary:
    1.  It first checks the `migration_hash` (an MD5 hash of the file's content) stored on the `DocType` record in the database. If the hash of the file on disk matches the stored hash, it skips the import, which makes migrations very fast.
    2.  If the hash doesn't match (or doesn't exist), it compares the `modified` timestamp in the JSON file with the `modified` timestamp in the database. If the file is newer, it proceeds with the import.
-   **`import_doc(...)`**: This function takes the dictionary read from the JSON file, creates a `Document` object, and inserts it into the database. It runs with special flags (`ignore_validate`, `ignore_permissions`) to ensure that the data from the file can be inserted directly without running all the usual business logic and validation, which is essential for a clean data sync. It also handles loading the code from separate files back into the document's fields before saving.

### `patch_handler.py`

This module manages the execution of patches during a migration. Patches are small, single-use Python scripts that perform data transformations or schema changes that can't be handled by the standard schema synchronization.

-   **`run_all(...)`**: This is the main entry point called by `bench migrate`. It discovers all patches from all installed apps and runs the ones that have not been executed yet.
-   **`Patch Log`**: Frappe keeps a record of all executed patches in the `Patch Log` DocType. The `run_all` function checks this log to determine which patches are pending.
-   **`patches.txt`**: Each app can have a `patches.txt` file. This file lists the dotted path to the Python functions that need to be executed as patches (e.g., `frappe.patches.v13_0.my_patch`).
-   **Pre/Post Model Sync**: The `patches.txt` file can be structured like an INI file with `[pre_model_sync]` and `[post_model_sync]` sections. This allows developers to specify whether a patch should run *before* or *after* the standard DocType schema migration (`updatedb`), which is critical for patches that need to alter the schema before new fields are added.

### `utils.py`

This file provides various helper functions for interacting with the module system.

-   **`load_doctype_module(doctype)`**: This is a fundamental function used throughout the framework. It takes a DocType name, determines which app and module it belongs to, constructs the Python module path (e.g., `frappe.core.doctype.user.user`), and imports it. This is how the framework dynamically loads the correct controller class for any given DocType.
-   **`export_customizations(...)`**: A developer tool that allows exporting `Custom Field` and `Property Setter` records related to a DocType into a JSON file in the app's `custom` folder. This allows customizations to be version-controlled and synced across different sites.
-   **`sync_customizations(...)`**: The corresponding function that reads the JSON files created by `export_customizations` and applies the customizations to the database.