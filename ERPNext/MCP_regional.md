# Model Context Profile: Regional

## 1. Module Overview

The `regional` module in ERPNext is a specialized module responsible for providing country-specific localizations and ensuring compliance with regional regulations, particularly concerning taxation and reporting. Unlike other modules that provide core functionalities, the `regional` module is a collection of features, reports, and configurations tailored to specific countries.

Its primary purpose is to adapt the standard ERPNext functionalities to meet the legal and business requirements of different geographic regions. This includes custom tax calculations, region-specific print formats for invoices, and statutory reports.

## 2. Core Components

The `regional` module is organized by feature type and by country.

### 2.1. Country-Specific Settings DocTypes

A key feature of the module is the use of dedicated DocTypes to manage settings for a particular country's regulations. These are typically singleton DocTypes linked to a `Company`.

-   **`UAE VAT Settings`**:
    -   Allows companies in the UAE to configure their VAT accounts.
    -   Contains a child table, `UAE VAT Account`, to link specific GL accounts to the VAT reporting structure. This is crucial for the `UAE VAT 201` report to correctly categorize and aggregate tax data.

-   **`South Africa VAT Settings`**:
    -   Similar to the UAE settings, this DocType allows South African companies to map their VAT accounts for reporting purposes.

-   **Other Regional DocTypes**:
    -   `Lower Deduction Certificate`: For Indian TDS (Tax Deducted at Source) compliance.
    -   `Import Supplier Invoice`: A tool to facilitate the import of supplier invoices, often used in regions with specific e-invoicing requirements.

### 2.2. Statutory Reports

The module includes a number of script reports that are designed to generate financial statements in the format required by a specific country's tax authorities.

-   **`UAE VAT 201`**:
    -   A script report that generates the data required for the UAE's VAT return (Form 201).
    -   It pulls data from `Sales Invoice` and `Purchase Invoice` documents, categorizing them into standard-rated supplies, zero-rated supplies, exempt supplies, and reverse charge transactions.
    -   The report's logic (`uae_vat_201.py`) contains specific functions to calculate totals for each category based on the configurations in `UAE VAT Settings`.

-   **`IRS 1099`**:
    -   A report for US compliance, used to generate the IRS Form 1099 for non-employee compensation.

-   **`Electronic Invoice Register`**:
    -   A report often required in countries with e-invoicing mandates, providing a register of all electronic invoices issued.

### 2.3. Print Formats

The module provides print formats that comply with the legal requirements of specific countries.

-   **`Tax Invoice` / `Simplified Tax Invoice`**: Standard invoice formats that include the necessary tax information, often used in VAT/GST regimes.
-   **`Detailed Tax Invoice`**: A more detailed version of the tax invoice, sometimes required for specific industries or transaction types.
-   **`IRS 1099 Form`**: A print format for the US IRS Form 1099.

### 2.4. Address Templates

The `address_template` directory contains HTML templates for formatting addresses according to the conventions of different countries (e.g., Germany, Switzerland, USA). This ensures that addresses on printed documents are displayed correctly for the target region.

### 2.5. Country-Specific Sub-packages

The module contains subdirectories for specific countries (e.g., `italy`, `australia`, `united_states`). These packages can contain:
-   A `setup.py` file, which can be used to install country-specific fixtures or run custom setup scripts.
-   Custom utility functions (`utils.py`) that contain logic specific to that country's regulations.
-   XML or other data files required for integration with government portals (e.g., `italy/e-invoice.xml`).

## 3. Data Flow and Architecture

1.  A user configures the **regional settings** for their company (e.g., `UAE VAT Settings`). This involves mapping their chart of accounts to the required reporting categories.
2.  When creating transactions (e.g., `Sales Invoice`, `Purchase Invoice`), users enter data as usual. Country-specific fields (e.g., `vat_emirate` on the Sales Invoice for the UAE) may be visible.
3.  When a **regional report** (e.g., `UAE VAT 201`) is run, its Python script fetches the transactional data.
4.  The script uses the **regional settings** to filter and categorize the data correctly. For example, it uses the account mappings in `UAE VAT Settings` to determine which GL entries correspond to standard-rated sales, reverse charges, etc.
5.  The report then presents the aggregated data in the legally required format.
6.  Similarly, when printing a document, the system can use a **regional print format** to ensure compliance.

## 4. Architectural Significance

The `regional` module is a prime example of how a generic ERP system can be adapted for global use. By isolating country-specific logic and configurations into a dedicated module, ERPNext can maintain a clean core application while still providing deep localization capabilities. This modular approach makes it easier to add support for new countries without altering the core business logic of the application. It also allows businesses to operate in multiple countries from a single instance, with each company configured for its specific regional requirements.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.regional.report.irs_1099.irs_1099`
- `irs_1099_print`: Generates a printable format for the IRS 1099 report.

### `erpnext.regional.doctype.import_supplier_invoice.import_supplier_invoice`
- `process_file_data`: Processes an uploaded file of supplier invoices for import.

### `erpnext.regional.italy.utils`
- `export_invoices`: Exports invoices in the Italian e-invoicing format.
- `generate_single_invoice`: Generates a single e-invoice for a specific document.