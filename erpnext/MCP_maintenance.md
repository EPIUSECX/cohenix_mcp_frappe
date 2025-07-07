# Model Context Profile: Maintenance

## 1. Module Overview

The Maintenance module in ERPNext is designed to manage the lifecycle of machinery and other assets. It facilitates scheduling preventive maintenance, recording ad-hoc maintenance visits, and tracking the associated costs and activities to ensure asset uptime and longevity.

## 2. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development. The module follows a "planner-executor" pattern, where the `Maintenance Schedule` plans the work and the `Maintenance Visit` records its execution.

### 2.1. Server-Side (Python)

#### `erpnext.maintenance.doctype.maintenance_schedule.maintenance_schedule.MaintenanceSchedule`

-   **`generate_schedule()`**: This is the core function for planning preventive maintenance. It programmatically populates the `schedules` child table with a series of `Maintenance Schedule Detail` entries based on the start date, end date, and number of visits defined for each item.

-   **`on_submit()`**: This controller method orchestrates several key actions upon submission of a schedule:
    -   It creates an `Event` in the calendar for each scheduled visit, assigning it to the relevant service person (`Sales Person`).
    -   It validates the `Serial No` of the assets to be maintained.
    -   It updates the `amc_expiry_date` on the `Serial No` master.

-   **`make_maintenance_visit(source_name, ...)`**: A `@frappe.whitelist()` function that serves as the primary integration point between planning and execution. It uses the `frappe.model.mapper.get_mapped_doc` utility to create a new `Maintenance Visit` document directly from a `Maintenance Schedule`, pre-filling all the relevant details.

#### `erpnext.maintenance.doctype.maintenance_visit.maintenance_visit.MaintenanceVisit`

-   **`on_submit()`**: This method provides the feedback loop to the planning document. When a `Maintenance Visit` is submitted, it updates the `completion_status` of the corresponding `Maintenance Schedule Detail` to "Fully Completed" or "Partially Completed". It also updates the status of any linked `Warranty Claim`.

-   **`on_cancel()`**: This method reverts the changes made on submission. It resets the `completion_status` of the linked `Maintenance Schedule Detail` back to "Pending".

### 2.2. Client-Side (JavaScript)

#### `erpnext.maintenance.MaintenanceSchedule` in `maintenance_schedule.js`

-   **`refresh(frm)`**: The UI controller for the `Maintenance Schedule` form. It provides a custom button to create a `Maintenance Visit` directly from the schedule, which triggers the `make_maintenance_visit` server-side function. It also allows users to pull maintenance items directly from a `Sales Order`.

#### `erpnext.maintenance.MaintenanceVisit` in `maintenance_visit.js`

-   **`refresh(frm)`**: The UI controller for the `Maintenance Visit` form. It demonstrates the module's flexibility by providing custom buttons to create a visit from multiple sources:
    -   `Maintenance Schedule`
    -   `Warranty Claim`
    -   `Sales Order`
    This allows users to initiate maintenance activities from various points in the customer lifecycle.