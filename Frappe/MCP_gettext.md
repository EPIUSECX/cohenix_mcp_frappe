# Model Context Profile: `gettext`

## 1. Module Overview

The `gettext` module is central to Frappe's internationalization and translation capabilities. It likely contains the tools and logic for extracting translatable strings from source code, compiling them into message catalogs (`.po` and `.mo` files), and loading them for use at runtime. This module enables the entire framework and the applications built on it to be presented in multiple languages.

Key functionalities are expected to include:
-   Extraction of translatable strings (e.g., `_("...")`) from Python and JavaScript files.
-   Management of `.po` files, which contain the source strings and their translations.
-   Compilation of `.po` files into binary `.mo` files for efficient loading.
-   Loading and caching of translations for use by the `frappe._` translation function.

## 2. File Index

-   **`translate.py`**: The main file containing the core logic for managing the translation lifecycle (POT generation, PO file updates, MO file compilation).
-   **`extractors/`**: A directory containing custom extractor functions for Babel. Each file corresponds to a specific type of source file or data structure from which translatable strings are extracted.
    -   `python.py`: Extracts strings from Python files.
    -   `javascript.py`: Extracts strings from JavaScript files.
    -   `html_template.py`: Extracts strings from Jinja/HTML templates.
    -   `doctype.py`: Extracts translatable strings from DocType JSON definitions (labels, descriptions, options, etc.).
    -   `workspace.py`, `report.py`, etc.: Extractors for other specific Frappe metadata types.

## 3. Public API / Callable Functions

The functions in this module are primarily intended to be called from the `bench` command-line interface, not directly from application code.

-   **`bench get-untranslated {lang} {app}`**: A command that uses the logic in this module to find missing translations.
-   **`bench update-translations {lang} {app}`**: A command that updates existing `.po` files with new strings from the source code.
-   **`bench build`**: This command, while part of the `utils` commands, calls `compile_translations` from this module to generate the binary `.mo` files.

## 4. Detailed Walkthrough

The `gettext` module provides a complete toolchain for managing translations, built on top of the standard Python `babel` library. The process can be broken down into three main stages: Extraction, Updating, and Compilation.

### 1. Extraction (`generate_pot`)

-   **`translate.generate_pot(target_app)`**: This function is the starting point for all translations. It scans the source code of an app to find all translatable strings.
-   It uses `babel.messages.extract.extract_from_dir`, a powerful function that iterates through a directory and applies different extraction methods based on file patterns.
-   The configuration for which extractor to use for which file type is defined in `babel_extractors.csv` files within each app. This allows apps to define their own custom extractors.
-   **`extractors/`**: This directory contains the custom logic for extraction.
    -   **`python.py`**: This is a wrapper around Babel's standard Python extractor. It adds special handling for Frappe's `pgettext` equivalent, `_("message", context=...)`.
    -   **`doctype.py`**: This extractor is crucial for translating the UI. It doesn't parse code, but instead parses the `.json` file of a DocType. It intelligently extracts strings from `label`, `description`, `options` (for Select fields), and other properties of DocFields, as well as the names and descriptions of the DocType itself.
-   The result of the extraction is a **`.pot` (Portable Object Template)** file. This is a text file that contains all the unique translatable strings found in the app, but no translations.

### 2. Updating (`update_po`)

-   **`translate.update_po(target_app, locale)`**: This function is used to update the language-specific translation files (`.po` files) with new strings found during the extraction phase.
-   It reads the master `.pot` file and the language-specific `.po` file (e.g., `de.po` for German).
-   It then uses `catalog.update()` from Babel to merge the new strings from the `.pot` file into the `.po` file. Existing translations are preserved, and new strings are added as untranslated entries.

### 3. Compilation (`compile_translations`)

-   **`translate.compile_translations(target_app, locale)`**: This is the final step that makes the translations available to the running application.
-   It reads a `.po` file, which is a human-readable text file.
-   It compiles it into a **`.mo` (Machine Object)** file using `babel.messages.mofile.write_mo`. The `.mo` file is a binary, hash-table-based format that is highly optimized for fast lookups at runtime.
-   These `.mo` files are placed in a central `sites/assets/locale` directory, from where the framework's `gettext` machinery can load them into memory for the `frappe._()` translation function to use.
-   This function uses a `multiprocessing.Pool` to compile translations for multiple apps and languages in parallel, significantly speeding up the build process.