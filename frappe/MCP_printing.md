# MCP: Printing Module

## Module Overview

The **Printing** module in Frappe is responsible for generating printable documents, such as invoices, sales orders, and reports. It provides a flexible system for creating and customizing print formats using HTML, Jinja templating, and a drag-and-drop print format builder.

This module allows users to define multiple print formats for a single DocType, create custom letterheads, and configure global print settings like page size and fonts.

## File Index

*   `frappe/printing/__init__.py`
*   `frappe/printing/doctype/print_format/print_format.py`
*   `frappe/printing/doctype/letter_head/letter_head.py`
*   `frappe/printing/doctype/print_settings/print_settings.py`
*   `frappe/printing/page/print_format_builder/print_format_builder.py`
*   ... and so on for all files in the `printing` module.

## Public API / Callable Functions

### `frappe.printing.doctype.print_format.make_default(name)`
- **Description:** Sets a print format as the default for its DocType.
- **Arguments:**
    - `name` (string): The name of the `Print Format`.
- **Returns:** None.

### `frappe.printing.page.print_format_builder.create_custom_format(doctype, name, based_on="Standard", beta=False)`
- **Description:** Creates a new custom print format.
- **Arguments:**
    - `doctype` (string): The DocType for which the print format is being created.
    - `name` (string): The name of the new print format.
    - `based_on` (string, optional): The print format to use as a base. Defaults to "Standard".
    - `beta` (bool, optional): Whether to use the beta print format builder. Defaults to False.
- **Returns:** The newly created `Print Format` document.

## Detailed Walkthrough

### `frappe/printing/doctype/print_format/print_format.py`

This file defines the `PrintFormat` DocType, which is the core model for creating print formats.

#### Class: `PrintFormat(Document)`

This class represents a print format. It stores the HTML, CSS, and other settings for a print format. Print formats can be created using Jinja templates, a drag-and-drop builder, or raw printing commands.

**Key Methods:**

*   **`get_html(docname, letterhead=None)`**: Renders the print format as HTML for a given document.
*   **`download_pdf(docname, letterhead=None)`**: Renders the print format as a PDF and initiates a download.
*   **`validate()`**: Validates the print format, including checking for valid Jinja syntax in the HTML.

**Key Properties (Fields):**

*   **`doc_type`**: The DocType for which this print format is designed.
*   **`html`**: The HTML content of the print format, which can include Jinja templating tags.
*   **`css`**: Custom CSS for the print format.
*   **`print_format_type`**: The type of print format ("Jinja" or "JS").
*   **`custom_format`**: If checked, the print format is a custom format.
*   **`standard`**: If "Yes", the print format is a standard, system-generated format.
*   **`module`**: The module to which the print format belongs.

### `frappe/printing/doctype/letter_head/letter_head.py`

This file defines the `LetterHead` DocType, which is used to create letterheads for printed documents.

#### Class: `LetterHead(Document)`

This class represents a letterhead. It allows you to define a header and footer for your documents, which can include your company logo, address, and other information.

**Key Methods:**

*   **`validate()`**: Sets the header and footer HTML from the attached images, if any.
*   **`on_update()`**: Sets the letterhead as the default if `is_default` is checked.

**Key Properties (Fields):**

*   **`letter_head_name`**: The name of the letterhead.
*   **`is_default`**: If checked, this letterhead will be used as the default for all printed documents.
*   **`source`**, **`footer_source`**: The source for the header and footer ("Image" or "HTML").
*   **`image`**, **`footer_image`**: The images to be used in the header and footer.
*   **`content`**, **`footer`**: The HTML content of the header and footer.

### `frappe/printing/doctype/print_settings/print_settings.py`

This file defines the `PrintSettings` DocType, a Singleton for configuring global printing options.

#### Class: `PrintSettings(Document)`

This class holds the system-wide settings for printing, such as the default page size, fonts, and whether to attach a PDF to emails.

**Key Methods:**

*   **`on_update()`**: Clears the cache after the settings are updated.

**Key Functions (outside the class):**

*   **`is_print_server_enabled()`**: Returns whether the print server is enabled.

**Key Properties (Fields):**

*   **`pdf_page_size`**: The default page size for PDFs ("A4", "Letter", etc.).
*   **`font`**, **`font_size`**: The default font and font size for printed documents.
*   **`with_letterhead`**: If checked, the default letterhead will be applied to all printed documents.
*   **`send_print_as_pdf`**: If checked, prints will be sent as PDFs in emails by default.

### `frappe/printing/page/print_format_builder/print_format_builder.py`

This file contains the server-side logic for the Print Format Builder, a UI for creating and customizing print formats.

**Key Functions:**

*   **`create_custom_format(doctype, name, based_on="Standard", beta=False)`**: Creates a new custom print format, optionally based on an existing one. This is called from the Print Format Builder UI.