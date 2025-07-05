# Model Context Profile: EDI

## 1. Module Overview

The **Electronic Data Interchange (EDI)** module in ERPNext provides a framework for managing and mapping standardized codes used in automated data exchange between different business systems. It is not a transactional module but a foundational one that enables other modules to comply with external coding systems required for EDI formats like EDIFACT, ANSI X12, or UBL.

The core purpose of this module is to create a bridge between ERPNext's internal data representations (e.g., a Customer's name) and the standardized codes used by trading partners (e.g., a GLN - Global Location Number).

## 2. Core Concepts

### a. Code Lists and Common Codes

The module is built around two primary DocTypes:

-   **`Code List`**: This acts as a container or a namespace for a specific set of standardized codes. For example, a `Code List` could represent "ISO 3166-1 Alpha-2" for country codes or "ISO 4217" for currency codes.
-   **`Common Code`**: This represents an individual code within a `Code List`. For example, within the "ISO 3166-1" `Code List`, a `Common Code` would be "US" with the description "United States".

### b. Dynamic Linking for Data Mapping

The key architectural feature is the use of a **Dynamic Link** table within the `Common Code` DocType. This allows a single `Common Code` to be linked to any other document in ERPNext. This many-to-one mapping is what enables the system to translate between internal data and external standards.

For example, the `Common Code` "US" can be linked to the `Country` DocType's record for "United States". When an EDI message needs to be generated, the system can look up the `Country` "United States" and find its corresponding `Common Code` ("US") for the specified `Code List`.

### c. Genericode Import

The module includes a utility to import code lists from `genericode` XML files, which is a standard format for distributing and managing code lists. The `import_genericode` function parses these files and automatically creates the corresponding `Common Code` documents, simplifying the process of populating the system with large, standardized datasets.

## 3. Key DocTypes and Data Models

### a. `Code List`

-   **File Path**: [`erpnext/edi/doctype/code_list/code_list.py`](erpnext-develop/erpnext/edi/doctype/code_list/code_list.py)
-   **Purpose**: To define a collection of standardized codes.
-   **Key Fields**: `title`, `version`, `publisher`, `canonical_uri`.
-   **Logic**:
    -   Provides helper methods like `get_codes_for()` to find all codes linked to a specific ERPNext document and `get_docnames_for()` to do the reverse lookup.
    -   Includes the `from_genericode()` method to populate its fields from a genericode XML file.

### b. `Common Code`

-   **File Path**: [`erpnext/edi/doctype/common_code/common_code.py`](erpnext-develop/erpnext/edi/doctype/common_code/common_code.py)
-   **Purpose**: To represent a single standardized code and its mapping to internal documents.
-   **Key Fields**: `code_list` (Link to `Code List`), `common_code` (the actual code value, e.g., "US"), `title`.
-   **Child Tables**: `Dynamic Link` (named `applies_to`), which stores the mappings to other ERPNext documents.
-   **Logic**:
    -   Includes validation to ensure that a document is not linked to more than one `Common Code` from the same `Code List`.
    -   The `from_genericode()` method populates the document from a row in a genericode XML file.

## 4. Utility Functions

-   **`get_codes_for(code_list, doctype, name)`**: A crucial utility function that takes an internal document (e.g., `Country`, "United States") and returns the corresponding standardized code(s) from a specified `Code List`.
-   **`get_docnames_for(code_list, doctype, code)`**: The inverse of the above, this function takes a standardized code and returns the internal ERPNext document(s) it is linked to.

## 5. Integrations

The `edi` module is designed to be a service module, providing data and functionality to other modules that need to generate or parse EDI-compliant messages. For example, a future `UBL` or `EDIFACT` integration module would use the `edi` module to:

-   Look up the correct standardized codes when generating an outgoing invoice.
-   Identify the correct internal customer or item when parsing an incoming purchase order.

It acts as a translation layer between the internal ERPNext ecosystem and the world of standardized electronic data interchange.

## 6. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.edi.doctype.code_list.code_list_import`
- `import_genericode`: Initiates the import process for a genericode file.
- `process_genericode_import`: The background job that processes the rows of a genericode file and creates `Code List` and `Common Code` documents.