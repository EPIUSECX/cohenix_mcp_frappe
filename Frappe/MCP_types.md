# Model Context Profile: `types`

## 1. Module Overview

The `types` module is expected to contain Python type hints and stubs (`.pyi` files). This is a modern development practice that does not affect runtime behavior but provides crucial information for static analysis tools (like MyPy) and IDEs. This improves code quality, readability, and developer productivity by enabling better autocompletion and type checking.

Key functionalities are expected to include:
-   Type aliases for common Frappe data structures.
-   Typed signatures for core framework functions and classes.
-   Stub files for modules that are dynamically generated or difficult for static analysis to parse.

## 2. File Index

-   **`__init__.py`**: Exports the main types for easy access.
-   **`DF.py`**: Defines type aliases for all standard Frappe `DocField` types (e.g., `Data`, `Link`, `Int`).
-   **`exporter.py`**: Contains the `TypeExporter` class, which is responsible for automatically generating type hints within DocType controller files.
-   **`filter.py`**: Defines types for the filter syntax used in `frappe.get_all` and `frappe.get_list` (e.g., `{"field": "value"}`, `["field", "=", "value"]`).
-   **`frappedict.py`**: Defines the `_dict` class, a subclass of the standard Python `dict` that allows attribute-style access to keys (e.g., `my_dict.key` instead of `my_dict['key']`).

## 3. Public API / Callable Functions

This module does not have a runtime API. Its "API" is the set of types and stubs that developers can import and use in their own code for static analysis.

-   **`from frappe.types import DF`**: This is the most common usage, allowing developers to annotate their document classes.
-   **`from frappe.types import _dict`**: Used for creating `_dict` objects.

## 4. Detailed Walkthrough

### `DF.py`

This file is the cornerstone of the `types` module. It provides a set of type aliases that directly correspond to the `fieldtype` options available in a `DocField`.

-   **Type Aliases**: It defines simple aliases like `Data = str`, `Int = int`, `Check = bool | int`, and `Table = list`.
-   **Purpose**: When a developer is writing a DocType controller, they can use these types to annotate the fields of their class. For example:
    ```python
    from frappe.types import DF

    class MyDoc(Document):
        my_field: DF.Data
        my_number: DF.Int
        my_child_table: DF.Table
    ```
-   This provides no runtime benefit but allows static type checkers like MyPy to validate the code and enables IDEs to provide accurate autocompletion and type information, significantly improving the developer experience.

### `exporter.py`

This module contains the logic that automates the creation of the type hints in DocType controller files.

-   **`TypeExporter` Class**: This class is instantiated when a `DocType` is saved.
-   **`export_types()`**: This is the main method. It reads the controller file for the DocType, generates a block of type-hinted code based on the DocType's `fields` table, and then injects this block into the controller file.
-   **Code Generation**: The exporter iterates through the `fields` of the `DocType` and uses the mapping in `DF.py` to generate the appropriate type hint for each field. It handles nullable fields, table fields (by importing the child DocType's class), and select options.
-   **Code Injection**: It cleverly finds the `class ...:` definition in the Python file and inserts the generated type block directly after it, wrapped in `# begin: auto-generated types` and `# end: auto-generated types` comments. This ensures that the type hints are always up-to-date with the DocType definition.

### `filter.py`

This file provides type definitions for the flexible filter syntax used throughout the Frappe API.

-   **`FilterTuple`**: A `NamedTuple` that represents a single filter condition, normalized to the format `(doctype, fieldname, operator, value)`.
-   **`Filters`**: A custom `list` subclass that can be initialized with various filter formats (dictionaries, lists of lists, etc.) and converts them all into a standardized list of `FilterTuple` objects. This provides a single, predictable structure for a feature that has multiple convenient input formats.

### `frappedict.py`

-   **`_dict` Class**: This is a simple but widely used class that inherits from `dict`. It overrides `__getattr__` and `__setattr__` to allow accessing dictionary keys as if they were object attributes. This is purely for developer convenience and is used extensively throughout the Frappe codebase for objects that are essentially dictionaries, like the `frappe.local` object.