# Model Context Profile: Maintenance

## 1. Module Overview

The **Maintenance** module in ERPNext is designed to manage and track the maintenance of assets and serialized items. It provides a structured workflow for scheduling preventive maintenance and recording maintenance activities, whether they are planned or unscheduled.

The core purpose of this module is to ensure that equipment and other assets are properly maintained, which helps to minimize downtime, extend asset life, and track maintenance costs. It is closely integrated with the `Stock` and `Asset` modules.

## 2. Core Concepts

### a. Scheduled Maintenance

The module's primary feature is the ability to create a `Maintenance Schedule`. This allows users to define a proactive maintenance plan for specific items or assets.
-   **Periodicity**: Schedules can be defined with various periodicities, such as "Weekly", "Monthly", "Quarterly", or "Random".
-   **Schedule Generation**: Based on the start date, end date, and number of visits, the system can automatically generate a list of scheduled maintenance dates.
-   **Holiday List Integration**: The schedule generation process takes into account the company's or employee's holiday list, ensuring that maintenance is not scheduled on non-working days.

### b. Maintenance Visits

The `Maintenance Visit` is the transactional document that records the execution of a maintenance task.
-   **Types of Maintenance**: A visit can be "Scheduled" (generated from a `Maintenance Schedule`), "Unscheduled" (planned but not part of a recurring schedule), or "Breakdown" (in response to an equipment failure).
-   **Tracking**: The visit records the date and time of maintenance, the service person responsible, the work done, and the completion status.
-   **Integration with Warranty Claims**: A maintenance visit can be linked to a `Warranty Claim`, and the status of the claim can be updated based on the outcome of the visit.

### c. Asset and Serial Number Integration

The maintenance workflow is tightly coupled with serialized items and assets.
-   A `Maintenance Schedule` can be created for specific `Serial No`s.
-   When a schedule is submitted, the `amc_expiry_date` on the linked `Serial No` documents is updated, providing a clear record of the maintenance contract period.
-   This ensures that maintenance is tracked at the individual asset level, which is crucial for accurate record-keeping and asset lifecycle management.

## 3. Key DocTypes and Data Models

### a. `Maintenance Schedule`

-   **File Path**: [`erpnext/maintenance/doctype/maintenance_schedule/maintenance_schedule.py`](erpnext-develop/erpnext/maintenance/doctype/maintenance_schedule/maintenance_schedule.py)
-   **Inherits**: `TransactionBase`
-   **Purpose**: To create and manage a schedule of planned maintenance visits.
-   **Key Fields**: `customer`, `transaction_date`.
-   **Child Tables**:
    -   `Maintenance Schedule Item`: Defines the items/assets to be maintained, the period of the schedule (`start_date`, `end_date`), the `periodicity`, and the number of visits.
    -   `Maintenance Schedule Detail`: This table is automatically populated by the `generate_schedule` method and lists all the individual maintenance dates.
-   **Logic**:
    -   The `generate_schedule` method calculates the dates for each visit based on the defined periodicity and date range.
    -   On submit, it creates `Event` documents in the calendar for each scheduled visit, assigned to the relevant sales/service person.

### b. `Maintenance Visit`

-   **File Path**: [`erpnext/maintenance/doctype/maintenance_visit/maintenance_visit.py`](erpnext-develop/erpnext/maintenance/doctype/maintenance_visit/maintenance_visit.py)
-   **Inherits**: `TransactionBase`
-   **Purpose**: To record the details of a single maintenance activity.
-   **Key Fields**: `customer`, `maintenance_type`, `mntc_date`, `completion_status`.
-   **Child Tables**: `Maintenance Visit Purpose`: Details the specific items serviced during the visit, the work done, and the service person.
-   **Logic**:
    -   Can be created from a `Maintenance Schedule`.
    -   On submit, it updates the `completion_status` and `actual_date` of the corresponding entry in the `Maintenance Schedule Detail` table.
    -   If linked to a `Warranty Claim`, it updates the status of the claim.

## 4. Integrations

-   **Stock**: The module is integrated with the `Stock` module through the `Serial No` DocType. Maintenance schedules and visits are linked to specific serial numbers, allowing for detailed tracking of an asset's maintenance history.
-   **Asset**: While not explicitly shown in the analyzed code, the maintenance module is conceptually linked to the `Asset` module, as assets are often the subject of maintenance.
-   **Support**: The integration with `Warranty Claim` connects the maintenance process with the customer support and issue resolution workflow.
-   **Calendar**: The system automatically creates `Event` entries for scheduled maintenance, ensuring that service personnel are aware of their upcoming tasks.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.maintenance.doctype.maintenance_schedule.maintenance_schedule`
- `generate_schedule`: Populates the `Maintenance Schedule Detail` table with calculated visit dates based on the schedule's periodicity.
- `validate_end_date_visits`: Validates the end date and number of visits for a schedule.
- `get_pending_data`: Fetches pending maintenance data for a specific item or schedule.
- `get_serial_nos_from_schedule`: Gets the serial numbers associated with a maintenance schedule.
- `make_maintenance_visit`: Creates a `Maintenance Visit` document from a `Maintenance Schedule`.