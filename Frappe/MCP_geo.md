# Model Context Profile: `geo`

## 1. Module Overview

The `geo` module likely contains functionality related to geographical data and operations. This could include DocTypes for storing geographical information like countries, currencies, and timezones, as well as utility functions for handling location-based data.

Key functionalities are expected to include:
-   DocTypes for `Country`, `Currency`, and `Timezone`.
-   Utility functions for fetching and managing geographical data.
-   Potential integration points for mapping services or location-based features.

## 2. File Index

-   **`country_info.json`**: A large JSON file containing a dictionary of all countries, with details like country code, currency, timezones, and number formats.
-   **`country_info.py`**: A Python module that provides functions to access and process the data from `country_info.json`.
-   **`languages.csv`**: A CSV file listing languages.
-   **`doctype/`**
    -   **`country/`**: Contains the `Country` DocType definition and controller (`country.py`).
    -   **`currency/`**: Contains the `Currency` DocType definition and controller (`currency.py`).

## 3. Public API / Callable Functions

-   **`frappe.geo.country_info.get_country_info(country)`**: Returns a dictionary of information for a specific country from `country_info.json`.
-   **`frappe.geo.country_info.get_all()`**: Returns the entire dictionary of country information from the JSON file.
-   **`frappe.geo.doctype.country.import_country_and_currency()`**: A utility function called during installation (`after_migrate` hook) to populate the `Country` and `Currency` DocTypes from the `country_info.json` data.

## 4. Detailed Walkthrough

### `country_info.json`

This is the master data file for the `geo` module. It is a large JSON object where keys are country names (e.g., "India", "United States") and values are dictionaries containing various metadata for that country, including:
-   `code`: The two-letter ISO 3166-1 alpha-2 country code.
-   `currency`: The three-letter ISO 4217 currency code.
-   `currency_symbol`: The symbol for the currency (e.g., $, €, ₹).
-   `timezones`: A list of timezones applicable to the country.
-   `number_format`: The default number format string.
-   `date_format`: The default date format string.

### `country_info.py`

This file acts as a simple Python API to access the data stored in `country_info.json`.

-   **`get_all()`**: This function simply opens and reads `country_info.json` and returns its contents as a Python dictionary.
-   **`get_country_info(country)`**: This function retrieves the data for a specific country from the dictionary returned by `get_all()`. It provides a convenient way to access the information for a single country.
-   **`get_country_timezone_info()`**: A whitelisted and cached function that returns a dictionary containing both the country info and a list of all timezones, making it available for client-side use.

### `doctype/country/country.py`

This file contains the controller for the `Country` DocType.

-   **`validate()`**: This method uses the `pycountry` library to validate that the `code` field contains a valid ISO 3166-1 alpha-2 country code.
-   **`import_country_and_currency()`**: This is the most important function in the file. It is called during the installation process. It reads the data from `country_info.json`, iterates through it, and creates `Country` and `Currency` documents for each entry. It uses `frappe.model.document.bulk_insert` to efficiently insert all the records at once.

### `doctype/currency/currency.py`

This file contains the controller for the `Currency` DocType.

-   **`validate()`**: This method simply calls `frappe.clear_cache()` to ensure that any changes to a currency's properties (like its symbol or number format) are immediately reflected throughout the system.
-   **`enable_default_currencies()`**: A helper function called during installation that enables a predefined list of common world currencies (`INR`, `USD`, `GBP`, `EUR`, etc.) by setting their `enabled` flag to 1. This ensures that these currencies are immediately available for use in transactions after a new site is set up.