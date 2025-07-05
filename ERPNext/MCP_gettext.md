# Model Context Profile: Gettext

## 1. Module Overview

The **Gettext** module in ERPNext is a specialized toolchain module that enhances the internationalization (i18n) and translation capabilities of the Frappe Framework. It does not contain any runtime application logic, DocTypes, or controllers. Instead, its purpose is to provide custom "extractors" for the `bench get-untranslated` command.

This command is a core part of the Frappe development process, responsible for scanning the codebase to find translatable strings and updating the `.csv` files used for translation. The extractors in this module allow this process to parse non-standard data files, ensuring that content stored in formats like CSV and JSON can also be translated.

## 2. Core Concepts

### a. Babel Extraction for Internationalization

Frappe uses the [Babel](https://babel.pocoo.org/) library and the `gettext` utility to manage translations. The process involves:
1.  **Marking Strings**: Developers mark translatable strings in the code, typically using `_("My String")`.
2.  **Extraction**: The `bench get-untranslated` command runs an extractor that scans source files (`.py`, `.js`, `.html`) to find these marked strings.
3.  **Translation Files**: The extracted strings are compiled into `.csv` or `.po` files, which can then be translated into different languages.

### b. Custom Extractors

While Babel has built-in extractors for common file types, it can be extended with custom functions to handle other formats. The `gettext` module in ERPNext contains such custom extractors. These are simple Python functions that take a file object as input and `yield` a tuple for each translatable string found. The tuple contains the line number, the function used for translation (typically `_`), the string itself, and any comments.

This mechanism allows ERPNext to manage translatable content that is defined as data (e.g., in a CSV or JSON file) rather than being hardcoded in the application logic.

## 3. Key Files and Extractors

### a. `extractors/incoterms.py`

-   **File Path**: [`erpnext/gettext/extractors/incoterms.py`](erpnext-develop/erpnext/gettext/extractors/incoterms.py)
-   **Purpose**: To extract the `title` of each Incoterm from the `incoterm.csv` data file.
-   **Logic**: It uses Python's built-in `csv.DictReader` to parse the CSV file and yields the value from the "title" column for each row.

### b. `extractors/uom_data.py`

-   **File Path**: [`erpnext/gettext/extractors/uom_data.py`](erpnext-develop/erpnext/gettext/extractors/uom_data.py)
-   **Purpose**: To extract the `uom_name` from the `uom.json` data file, which contains the standard Units of Measure.
-   **Logic**: It loads the JSON file, iterates through the list of UOM objects, and yields the value of the `uom_name` key for each.

### c. `extractors/lines_from_txt_file.py`

-   **File Path**: [`erpnext/gettext/extractors/lines_from_txt_file.py`](erpnext-develop/erpnext/gettext/extractors/lines_from_txt_file.py)
-   **Purpose**: A generic extractor that treats each line in a text file as a separate translatable string.
-   **Logic**: It reads the file line by line and yields each line as a translation unit.

## 4. Integrations

The `gettext` module integrates directly with the Frappe Framework's build and translation toolchain. Its functionality is invoked during development when a developer runs `bench get-untranslated`. It has no direct impact on the runtime behavior of the ERPNext application itself but is critical for ensuring that all user-facing content, including data-driven lists and descriptions, can be fully localized.

## 5. Callable Functions (`@frappe.whitelist()`)

This module has **no whitelisted functions**. It is a toolchain module for the build process and does not expose any callable API methods.