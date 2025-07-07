# Model Context Profile: `assets`

## 1. Module Overview

The `assets` module in ERPNext provides a comprehensive system for managing the complete lifecycle of fixed assets. This includes acquisition, depreciation, value adjustments, maintenance, and disposal (through sale or scrap). The module is tightly integrated with the `accounts` module to ensure that all asset-related activities are accurately reflected in the company's financial statements.

The core of the module is the `Asset` DocType, which represents a single fixed asset. The system supports multiple depreciation methods and allows for parallel depreciation schedules for different accounting purposes (e.g., company books vs. tax books) through the use of Finance Books.

## 2. File Structure and Key Components

The `assets` module is primarily driven by its DocTypes, which define the data structures and business logic for asset management.

```
erpnext/assets/
├── doctype/
│   ├── asset/
│   │   ├── asset.py              # Main controller for the Asset master.
│   │   └── depreciation.py       # Contains the logic for posting periodic depreciation.
│   ├── asset_category/
│   │   └── asset_category.py     # Defines asset classes, including default accounts and depreciation rules.
│   ├── asset_depreciation_schedule/
│   │   └── asset_depreciation_schedule.py # Manages the pre-calculated depreciation schedule for an asset.
│   ├── asset_value_adjustment/
│   │   └── asset_value_adjustment.py # Handles manual appreciation or depreciation of an asset.
│   ├── asset_maintenance/
│   │   └── asset_maintenance.py    # Manages scheduled maintenance for assets.
│   └── asset_movement/
│       └── asset_movement.py       # Tracks the physical movement of assets between locations and custodians.
└── report/                         # Contains standard reports like Fixed Asset Register.
```

## 3. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development.

### 3.1. Server-Side (Python)

#### `erpnext.assets.doctype.asset.depreciation`

-   **`post_depreciation_entries(date=None)`**: This is the main entry point for the periodic depreciation scheduler. It identifies all assets due for depreciation up to the given date and calls `make_depreciation_entry` for each one. This can be called manually to trigger depreciation for all assets.
-   **`make_depreciation_entry(...)`**: A whitelisted function that creates a "Depreciation Entry" `Journal Entry` for a given asset based on its depreciation schedule. This is the core function for posting depreciation.
-   **`scrap_asset(asset_name, scrap_date=None)`**: A whitelisted function that handles the entire asset scrapping process. It first calls `depreciate_asset` to book any pending depreciation up to the scrap date, and then creates a `Journal Entry` to write off the asset's remaining value.
-   **`restore_asset(asset_name)`**: A whitelisted function that reverses the scrapping of an asset by cancelling the scrap journal entry and recalculating the depreciation schedule.

#### `erpnext.assets.doctype.asset.asset.Asset` (Class Methods & Module Functions)

-   **`on_submit()`**: The instance method that orchestrates the capitalization of an asset. It creates the necessary `GL Entries` to move the asset's value to the fixed asset account and activates its depreciation schedules.
-   **`make_sales_invoice(asset, ...)`**: A whitelisted function that generates a new `Sales Invoice` document pre-filled with the details of the asset to be sold.
-   **`transfer_asset(args)`**: A whitelisted function that creates and submits an `Asset Movement` document to transfer an asset to a new location or custodian.
-   **`split_asset(asset_name, split_qty)`**: A whitelisted function that splits a multi-quantity asset into two separate asset records, prorating the costs and depreciation schedules accordingly.

### 3.2. Client-Side (JavaScript)

#### `erpnext.asset` (Namespace)

-   **`erpnext.asset.scrap_asset(frm)`**: This function, defined in `asset.js`, opens a dialog to get the scrap date from the user and then calls the server-side `scrap_asset` method. It provides a reusable UI pattern for this action.
-   **`erpnext.asset.restore_asset(frm)`**: This function shows a confirmation dialog and then calls the server-side `restore_asset` method.
-   **`erpnext.asset.transfer_asset(frm)`**: This function initiates the asset transfer process by calling the `make_asset_movement` server-side method and routing the user to the new `Asset Movement` form.

#### Form Event Handlers (`frappe.ui.form.on("Asset", ...)` in `asset.js`)

-   **`refresh(frm)`**: This is the main client-side controller. It dynamically adds custom buttons to the form based on the asset's status (e.g., "Transfer Asset", "Scrap Asset", "Sell Asset"). It also triggers the rendering of the depreciation chart and schedule view.
-   **`make_sales_invoice(frm)`**: This event handler calls the server-side `make_sales_invoice` function and routes the user to the newly created document.
-   **`setup_chart_and_depr_schedule_view(frm)`**: This asynchronous function fetches the depreciation schedule data and uses it to render both the graphical chart of asset value over time and the detailed schedule table in the form's dashboard.

## 4. Dependencies and Interactions

- **Accounts Module**: The `assets` module is fundamentally linked to the `accounts` module.
    -   **`Purchase Invoice` / `Purchase Receipt`**: These documents are the primary source for creating new `Asset` documents upon acquisition.
    -   **`Journal Entry`**: All financial transactions related to assets (capitalization, depreciation, disposal) are recorded as `Journal Entry` documents, which in turn create `GL Entry` records.
    -   **`Chart of Accounts`**: The `Asset Category` doctype links to various accounts (Fixed Asset Account, Accumulated Depreciation Account, Depreciation Expense Account) to automate the GL postings.
- **Stock Module**: While assets are typically non-stock items, the acquisition process is often linked to `Purchase Receipt` if the asset is received physically before being capitalized.
- **Scheduler**: The periodic depreciation process relies on the Frappe scheduler to call `post_depreciation_entries` at regular intervals (e.g., daily, monthly).