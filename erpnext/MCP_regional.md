# Model Context Profile: Regional

## 1. Module Overview

The Regional module in ERPNext provides region-specific features and compliance for various countries. This includes customizations for chart of accounts, tax regulations, print formats, and other local requirements.

## 2. Key Reusable Functions

### 2.1. Server-Side (Python)

The primary logic in the regional module is controlled by the company's specified country. The core functions below are defined in `erpnext.regional.__init__` and are conditionally executed based on the output of the `erpnext.get_region()` function.

#### Generic Regional Functions

-   **`check_deletion_permission(doc, method)`**: This function is hooked into the `on_trash` event for all DocTypes. It checks the company's region and, if it is "Nepal", prevents the deletion of any submitted document (`docstatus=1`). This is a crucial compliance feature.

-   **`create_transaction_log(doc, method)`**: Hooked into the `on_submit` event for `Sales Invoice` and `Payment Entry`. If the company's region is "Germany", this function creates a `Transaction Log` entry, which serves as a legal, auditable record of the transaction.

#### Country-Specific Logic: South Africa

The logic for South Africa is not contained in traditional DocType controllers but is executed via a `setup.py` script (`erpnext.regional.south_africa.setup`). This script programmatically modifies core DocTypes and permissions to enable regional features.

-   **`setup(company=None, patch=True)`**: The main function that orchestrates the setup process. It is typically run once during installation or on a bench update.

-   **`make_custom_fields(update=True)`**: This function is a key part of the setup. It creates a custom checkbox field named `is_zero_rated` and adds it to the following DocTypes:
    -   `Item`
    -   `Sales Invoice Item`
    -   `Purchase Invoice Item`
    This field is essential for applying the correct Value Added Tax (VAT) rules.

-   **`add_permissions()`**: This function configures permissions for South Africa-specific DocTypes and Reports. It grants `read`, `write`, and `create` permissions to roles like `Accounts Manager` and `Accounts User` for the `South Africa VAT Settings` and `South Africa VAT Account` DocTypes. It also ensures that relevant roles have access to the `VAT Audit Report`.

#### Country-Specific Logic: United Arab Emirates

The UAE implementation is more extensive, combining a `setup.py` script for schema modifications with a `utils.py` file for runtime business logic.

##### Setup Script (`erpnext.regional.united_arab_emirates.setup`)

-   **`make_custom_fields()`**: This is the most critical setup function. It programmatically adds a large number of custom fields to core sales and purchase documents (`Sales Invoice`, `Purchase Invoice`, `Sales Order`, etc.) to support UAE VAT requirements. Key fields include:
    -   `is_zero_rated` and `is_exempt` for items.
    -   `permit_no`, `vat_emirate`, and Arabic names for customers and suppliers.
    -   Fields for handling reverse charge (`reverse_charge`, `recoverable_reverse_charge`).

-   **`add_print_formats()`**: Installs and enables three UAE-specific print formats: `Detailed Tax Invoice`, `Simplified Tax Invoice`, and `Tax Invoice`.

-   **`add_custom_roles_for_reports()`**: Creates a custom role to control access to the `UAE VAT 201` report.

##### Utility Functions (`erpnext.regional.united_arab_emirates.utils`)

This file contains the core runtime logic for UAE VAT calculations and is hooked into various DocType events.

-   **`update_itemised_tax_data(doc)`**: A utility function to calculate and set the `tax_rate` and `tax_amount` for each item in a transaction based on the applied tax templates.

-   **`update_grand_total_for_rcm(doc, method)`**: Hooked into sales and purchase documents. If the `reverse_charge` field is set to "Y", this function recalculates the `grand_total` to exclude the VAT amount, as it's handled through the reverse charge mechanism.

-   **`make_regional_gl_entries(gl_entries, doc)`**: Hooked into the `make_gl_entries` method of `Purchase Invoice`. It appends the necessary GL entries for reverse charge VAT, ensuring correct accounting treatment.

-   **`get_tax_accounts(company)`**: A helper function that retrieves the list of VAT-related accounts from the `UAE VAT Settings` for a given company.

-   **`validate_returns(doc, method)`**: A validation function that prevents users from setting "Recoverable Standard Rated Expenses" when the "Reverse Charge Applicable" flag is set, enforcing correct data entry.