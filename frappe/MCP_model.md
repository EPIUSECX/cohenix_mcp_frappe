# MCP: Model Module

## Module Overview

The **Model** module is the heart of the Frappe Framework's data management system. It provides the core components for defining, creating, reading, updating, and deleting documents (DocTypes). This module includes the `Document` class, which is the base class for all DocTypes, as well as the `Meta` class for accessing DocType metadata, and the `DatabaseQuery` class for building and executing database queries.

This module is fundamental to how data is structured and manipulated in Frappe, and it provides the foundation for the entire ORM (Object-Relational Mapping) system.

## File Index

*   `frappe/model/__init__.py`
*   `frappe/model/document.py`
*   `frappe/model/meta.py`
*   `frappe/model/db_query.py`
*   `frappe/model/delete_doc.py`
*   `frappe/model/rename_doc.py`
*   ... and so on for all files in the `model` module.

## Public API / Callable Functions

### `frappe.get_doc(...)`
- **Description:** This is the primary function for creating and retrieving `Document` objects. It can be called in several ways:
    - `frappe.get_doc(doctype, name)`: Fetches a document from the database.
    - `frappe.get_doc(doctype)`: Fetches a single DocType.
    - `frappe.get_doc({...})`: Creates a new document from a dictionary.
- **Returns:** A `Document` object.

### `frappe.get_meta(doctype)`
- **Description:** Returns a `Meta` object for a given DocType, which contains all the metadata for that DocType, including its fields, permissions, and other properties.
- **Arguments:**
    - `doctype` (string): The name of the DocType.
- **Returns:** A `Meta` object.

### `frappe.delete_doc(doctype, name, ...)`
- **Description:** Deletes a document.
- **Arguments:**
    - `doctype` (string): The DocType of the document to be deleted.
    - `name` (string): The name of the document to be deleted.
- **Returns:** None.

### `frappe.rename_doc(doctype, old, new, ...)`
- **Description:** Renames a document and updates all references to it in the database.
- **Arguments:**
    - `doctype` (string): The DocType of the document to be renamed.
    - `old` (string): The current name of the document.
    - `new` (string): The new name for the document.
- **Returns:** The new name of the document.

## Detailed Walkthrough

### `frappe/model/document.py`

This file defines the `Document` class, which is the base class for all DocTypes in Frappe. It provides the core ORM functionality, including methods for creating, reading, updating, and deleting documents.

#### Class: `Document(BaseDocument)`

This class provides the main interface for interacting with documents. It includes methods for saving, submitting, canceling, and deleting documents, as well as for handling permissions, workflows, and other document-related operations.

**Key Methods:**

*   **`insert()`**: Inserts a new document into the database.
*   **`save()`**: Saves an existing document to the database.
*   **`submit()`**: Submits a document, setting its `docstatus` to 1.
*   **`cancel()`**: Cancels a submitted document, setting its `docstatus` to 2.
*   **`delete()`**: Deletes a document.
*   **`check_permission(permtype)`**: Checks if the current user has the specified permission for the document.
*   **`run_method(method, *args, **kwargs)`**: Executes a method on the document, including any hooked methods from other apps.

### `frappe/model/meta.py`

This file defines the `Meta` class, which is used to get metadata about a DocType.

#### Class: `Meta(Document)`

This class provides a convenient way to access the properties of a DocType, such as its fields, permissions, and other settings. It also includes methods for getting various types of fields (e.g., link fields, table fields).

**Key Methods:**

*   **`get_field(fieldname)`**: Returns the `DocField` object for a given fieldname.
*   **`get_link_fields()`**: Returns a list of all link fields in the DocType.
*   **`get_table_fields()`**: Returns a list of all table fields in the DocType.
*   **`get_valid_columns()`**: Returns a list of all valid database columns for the DocType.

### `frappe/model/db_query.py`

This file defines the `DatabaseQuery` class, which is used to build and execute database queries for list and report views.

#### Class: `DatabaseQuery`

This class provides a high-level interface for building complex database queries. It handles permissions, filters, sorting, and pagination automatically.

**Key Methods:**

*   **`execute(fields, filters, ...)`**: Executes the query and returns the results.
*   **`build_conditions()`**: Builds the `WHERE` clause of the query based on the provided filters and user permissions.
*   **`prepare_args()`**: Prepares the arguments for the query, including the fields, tables, and conditions.

### `frappe/model/delete_doc.py`

This file contains the logic for deleting documents.

**Key Functions:**

*   **`delete_doc(...)`**: The main function for deleting a document. It checks for linked documents, runs the `on_trash` method, and deletes the document from the database.
*   **`check_if_doc_is_linked(doc)`**: Checks if a document is linked in any other documents and raises an exception if it is.
*   **`check_if_doc_is_dynamically_linked(doc)`**: Checks if a document is dynamically linked in any other documents.

### `frappe/model/rename_doc.py`

This file contains the logic for renaming documents.

**Key Functions:**

*   **`rename_doc(...)`**: The main function for renaming a document. It updates the `name` of the document and all references to it in other documents.
*   **`update_link_field_values(link_fields, old, new, doctype)`**: Updates the value of all link fields that point to the renamed document.
*   **`rename_dynamic_links(doctype, old, new)`**: Updates the value of all dynamic link fields that point to the renamed document.
### Detailed Walkthrough (Continued)

#### `frappe.model.workflow`

This module provides the backend logic for the Workflow feature in Frappe, allowing for the creation of state-based approval processes for any DocType.

-   **`get_workflow_name(doctype)`**: A cached function that retrieves the name of the active `Workflow` document for a given DocType.
-   **`get_transitions(doc)`**: This is a core function that determines the possible next states for a given document. It checks the document's current state (defined in the `workflow_state_field`), finds all transitions from that state in the workflow definition, and filters them based on the current user's roles. It also evaluates any conditions defined on the transitions.
-   **`apply_workflow(doc, action)`**: This function is called when a user clicks a workflow action button. It finds the corresponding transition, verifies the user has permission, and then updates the document's state. It also handles changes to the `docstatus` (e.g., submitting or cancelling the document) as defined in the target workflow state.
-   **`validate_workflow(doc)`**: This function is called during the `doc.save()` process. It ensures that if the workflow state has been changed, the transition is a valid one according to the defined workflow and user permissions.

#### `frappe.model.naming`

This module is critical for the framework as it handles the generation and validation of the primary key for all documents (`name` field).

-   **`set_new_name(doc)`**: This is the main entry point for naming a new document. It orchestrates the naming process by checking various sources for a naming rule:
    1.  **Document Naming Rule**: Checks for rules defined in the "Document Naming Rule" DocType first.
    2.  **`autoname` method**: Calls the `autoname` method on the document's controller if it exists.
    3.  **`autoname` property**: If no `autoname` method is found, it interprets the `autoname` property from the DocType's metadata. This property can specify various schemes:
        -   `field:{fieldname}`: Uses the value of another field as the name.
        -   `naming_series:`: Uses the `naming_series` field on the document to generate a name (e.g., `INV-2023-00001`).
        -   `prompt`: Requires the user to enter the name manually.
        -   `format:{pattern}`: Creates a name from a format string with placeholders (e.g., `PO-{supplier_abbr}-{MM}-{#####}`).
        -   `hash`: Generates a random-like hash.
-   **`NamingSeries` Class**: A powerful class that parses a naming series string (like `SINV-.YY.-.MM.-.#####`), substitutes dynamic parts (like year and month), and gets the next sequential number from the `tabSeries` database table.
-   **`revert_series_if_last(key, name)`**: An important function for transactional integrity. If a document was the last one to use a series and it gets deleted before another is created, this function decrements the counter in `tabSeries` to prevent gaps in the sequence.
-   **`validate_name(doctype, name)`**: Performs crucial checks on the final name to ensure it doesn't contain illegal characters (`<`, `>`) and doesn't conflict with the DocType name itself.

#### `frappe.model.create_new`

This module is responsible for the initial creation of a document object when a user clicks "New". Its primary purpose is to populate the new document with default values.

-   **`get_new_doc(doctype, ...)`**: The main function that returns a new document object. It uses a cached template of the new document for performance, as this function is called very frequently.
-   **Default Value Precedence**: The module sets default values in a specific order:
    1.  **User Permissions**: If a user has a `User Permission` record for a Link field that applies to a single document (e.g., only allowed to see one specific Customer), that Customer is set as the default.
    2.  **User Defaults**: Values set by the user in their "User Defaults" list.
    3.  **Static Defaults**: The "Default" value set in the DocField definition in the DocType. Special values like `__user` (current user) and `Today` are handled here.
    4.  **Dynamic Defaults**: Defaults that depend on other values, specified with a `:` prefix (e.g., `:user`).

#### `frappe.model.base_document`

This is the foundational class for the entire ORM. All DocType controller classes inherit from `BaseDocument`. It provides the dictionary-like interface and the core database interaction methods.

-   **`__init__(self, d)`**: The constructor accepts a dictionary `d` and populates the document's attributes.
-   **`get`, `set`, `append`, `remove`**: These methods provide the primary interface for interacting with document fields and child tables. `append` is particularly important as it correctly initializes a child document, setting its `parent`, `parenttype`, and `parentfield` attributes.
-   **`db_insert()` & `db_update()`**: These methods construct and execute the raw `INSERT` and `UPDATE` SQL queries. They use `get_valid_dict()` to get a dictionary of columns that actually exist in the database schema for that DocType.
-   **Validation Methods**: A suite of `_validate_*` methods are called before saving:
    -   `_get_missing_mandatory_fields()`: Checks for required fields.
    -   `get_invalid_links()`: The most complex validation, it checks if all `Link` and `Dynamic Link` fields point to valid, existing documents. It also checks that linked submittable documents are not cancelled. As a side-effect, it also triggers "Fetch From" functionality.
    -   `_validate_selects()`: Ensures the value of a `Select` field is one of the defined options.
    -   `_validate_constants()`: Prevents changes to fields marked as "Set Only Once".
    -   `_validate_update_after_submit()`: Prevents changes to fields that are not marked as "Allow on Submit" after a document has been submitted.
-   **`_sanitize_content()`**: An important security feature that strips potentially malicious code from HTML and Text Editor fields to prevent XSS attacks.
-   **`get_controller(doctype)`**: A static method-like function within the module that is responsible for importing the correct Python class for a given DocType, including handling custom scripts and overrides.

#### `frappe.model.dynamic_links`

This module provides helper functions to manage `Dynamic Link` fields across the system. These fields are powerful but create a challenge because the database doesn't inherently know which DocTypes are being linked to.

-   **`get_dynamic_link_map()`**: This is the most important function. It builds a map of which DocTypes are referenced by other DocTypes via Dynamic Links. For example, it might produce `{'Customer': [{'parent': 'Communication', 'fieldname': 'reference_name', 'options': 'reference_doctype'}], ...}`. This map is crucial for the `delete_doc` logic, which needs to check for references in other documents before allowing a deletion.
-   **`fetch_distinct_link_doctypes(doctype, fieldname)`**: This function queries a table to find all the unique DocType names that have been used in a specific Dynamic Link field. For example, it would query `tabCommunication` and look at the `reference_doctype` column to find all the types of documents that have been communicated about (e.g., 'Customer', 'Supplier', 'Sales Order'). This is an expensive query and its results are heavily cached.
-   **`invalidate_distinct_link_doctypes(...)`**: This function is called when a new link is made. It checks if the newly linked DocType is already in the cache for that dynamic link. If not, it invalidates the cache so it can be rebuilt with the new information.