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

## 3. Key Classes and Functions

### `erpnext.assets.doctype.asset.asset.Asset`
- This is the central class representing a fixed asset.
- **`validate()`**: Validates asset details, including its category, purchase information, and finance book configurations.
- **`create_asset_depreciation_schedule()`**: Called on document update, this method generates or updates the `Asset Depreciation Schedule` based on the asset's value and the methods defined in its finance books.
- **`on_submit()`**: A critical method that capitalizes the asset. It triggers the creation of `GL Entries` to move the asset's value from a temporary account (like 'Asset Received But Not Billed' or 'Capital Work in Progress') to the final fixed asset account. It also activates the depreciation schedules.
- **`on_cancel()`**: Reverses all transactions related to the asset, including GL entries and depreciation schedules.
- **`scrap_asset()` / `restore_asset()`**: Manages the disposal of an asset by first posting any pending depreciation and then creating a `Journal Entry` to write off the asset's value from the books.

### `erpnext.assets.doctype.asset.depreciation`
- This file contains the logic for the periodic depreciation process, which is typically run as a scheduled background job.
- **`post_depreciation_entries(date)`**: The main entry point for the scheduler. It fetches all assets due for depreciation and calls `make_depreciation_entry` for each one.
- **`make_depreciation_entry(...)`**: Creates a "Depreciation Entry" `Journal Entry`. It debits the depreciation expense account and credits the accumulated depreciation account for the amount specified in the asset's depreciation schedule for that period.
- **`depreciate_asset(asset_doc, date, notes)`**: A utility function called during asset sale or scrap to ensure depreciation is booked up to the date of disposal before the final disposal entry is made.

## 4. Dependencies and Interactions

- **Accounts Module**: The `assets` module is fundamentally linked to the `accounts` module.
    -   **`Purchase Invoice` / `Purchase Receipt`**: These documents are the primary source for creating new `Asset` documents upon acquisition.
    -   **`Journal Entry`**: All financial transactions related to assets (capitalization, depreciation, disposal) are recorded as `Journal Entry` documents, which in turn create `GL Entry` records.
    -   **`Chart of Accounts`**: The `Asset Category` doctype links to various accounts (Fixed Asset Account, Accumulated Depreciation Account, Depreciation Expense Account) to automate the GL postings.
- **Stock Module**: While assets are typically non-stock items, the acquisition process is often linked to `Purchase Receipt` if the asset is received physically before being capitalized.
- **Scheduler**: The periodic depreciation process relies on the Frappe scheduler to call `post_depreciation_entries` at regular intervals (e.g., daily, monthly).

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.assets.doctype.asset.asset`
- `get_manual_depreciation_entries`: Fetches manually entered depreciation records for an asset.
- `get_depreciation_rate`: Calculates the depreciation rate based on the asset's details.
- `make_sales_invoice`: Creates a Sales Invoice for selling an asset.
- `create_asset_maintenance`: Creates a new Asset Maintenance schedule.
- `create_asset_repair`: Creates an Asset Repair log.
- `create_asset_capitalization`: Creates an Asset Capitalization document for a composite asset.
- `create_asset_value_adjustment`: Creates an Asset Value Adjustment document.
- `transfer_asset`: A wrapper function to create an Asset Movement document.
- `get_item_details`: Fetches details from the linked Item master.
- `make_journal_entry`: A utility to create a Journal Entry related to the asset.
- `make_asset_movement`: Creates an Asset Movement document for one or more assets.
- `get_asset_value_after_depreciation`: Calculates the asset's value on a future date.
- `has_active_capitalization`: Checks if there is an active capitalization process for the asset.
- `get_values_from_purchase_doc`: Pulls details from a Purchase Invoice or Receipt.
- `split_asset`: Splits a single asset with multiple quantities into individual assets.

### `erpnext.assets.doctype.asset.depreciation`
- `make_depreciation_entry`: Creates a Journal Entry for depreciation.
- `scrap_asset`: Scraps an asset and creates the necessary accounting entries.
- `restore_asset`: Reverses the scrapping of an asset.
- `get_disposal_account_and_cost_center`: Fetches the default accounts for asset disposal.
- `get_value_after_depreciation_on_disposal_date`: Calculates the asset's value on the date of disposal.

### `erpnext.assets.doctype.asset_maintenance.asset_maintenance`
- `calculate_next_due_date`: Calculates the next due date for a maintenance task.
- `get_maintenance_log`: Fetches the maintenance logs for a specific asset.

### `erpnext.assets.doctype.asset_capitalization.asset_capitalization`
- `set_warehouse_details`: Sets warehouse details for the capitalization process.
- `set_asset_values`: Sets the values of the assets being capitalized.
- `get_target_item_details`: Fetches details of the target composite item.
- `get_target_asset_details`: Fetches details of the target composite asset.
- `get_warehouse_details`: Fetches warehouse details.
- `get_items_tagged_to_wip_composite_asset`: Gets items linked to a "Work in Progress" composite asset.

### `erpnext.assets.doctype.asset_value_adjustment.asset_value_adjustment`
- `get_value_of_accounting_dimensions`: Fetches the cost center and other dimensions for an asset.

### `erpnext.assets.doctype.asset_depreciation_schedule.asset_depreciation_schedule`
- `get_depr_schedule`: Fetches the depreciation schedule for an asset.
- `get_asset_depr_schedule_doc`: Gets the full `Asset Depreciation Schedule` document.

### `erpnext.assets.doctype.asset_repair.asset_repair`
- `get_downtime`: Calculates the total downtime between failure and completion dates.
- `get_purchase_invoice`: Searches for Purchase Invoices to link as repair costs.
- `get_expense_accounts`: Searches for expense accounts to book repair costs.

### `erpnext.assets.doctype.location.location`
- `get_children`: Fetches child locations for the location tree.
- `add_node`: Adds a new location to the tree.