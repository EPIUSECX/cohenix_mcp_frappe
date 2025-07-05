# Model Context Profile: Manufacturing

## 1. Module Overview

The **Manufacturing** module in ERPNext is a comprehensive system for managing the entire production process, from product design and planning to shop floor execution and costing. It is designed to support discrete manufacturing environments and is tightly integrated with the `Stock`, `Buying`, and `Accounts` modules to ensure a seamless flow of data and materials.

The core purpose of this module is to provide tools for defining product structures, planning production based on demand, managing shop floor operations, and accurately tracking the costs associated with manufacturing.

## 2. Core Concepts

### a. Bill of Materials (BOM)

The `BOM` is the foundational document in the manufacturing module. It serves as the "recipe" for a product, detailing:
-   **Raw Materials**: The list of items required to produce the finished good.
-   **Operations**: The sequence of manufacturing tasks (e.g., cutting, assembly, painting) that need to be performed.
-   **Workstations**: The specific machines or locations where each operation is carried out.
-   **Costs**: The BOM is used to calculate the standard cost of a product, including raw material costs and operating costs.

BOMs can be multi-level, allowing a sub-assembly (an item with its own BOM) to be used as a raw material in a higher-level BOM.

### b. Production Planning and Execution

The manufacturing workflow follows a structured path from planning to execution:

1.  **`Production Plan`**: A high-level document used to aggregate demand from `Sales Orders` or `Material Requests`. It helps in planning what to produce and in what quantities over a specific period.
2.  **`Work Order`**: The primary execution document. It is a specific instruction to produce a certain quantity of an item. It inherits the required materials and operations from the item's default `BOM`.
3.  **`Job Card`**: A detailed, granular task derived from a `Work Order` operation. It is assigned to a specific `Workstation` and tracks the time spent and quantity completed for that single operation.

### c. Shop Floor Management

-   **`Workstation`**: Represents a physical machine or area on the shop floor. It defines the operating costs (labor, electricity, etc.) and working hours, which are crucial for capacity planning and costing.
-   **Material Transfer**: The system manages the movement of raw materials from a source warehouse to a `Work-in-Progress (WIP)` warehouse for consumption in a `Work Order`. Finished goods are then moved from the WIP warehouse to a finished goods store.

## 3. Key DocTypes and Data Models

### a. `BOM` (Bill of Materials)

-   **File Path**: [`erpnext/manufacturing/doctype/bom/bom.py`](erpnext-develop/erpnext/manufacturing/doctype/bom/bom.py)
-   **Inherits**: `WebsiteGenerator`
-   **Purpose**: To define the components and processes required to manufacture an item.
-   **Key Fields**: `item`, `quantity`, `with_operations`.
-   **Child Tables**: `BOM Item` (raw materials), `BOM Operation`.
-   **Logic**:
    -   Calculates the total cost of the BOM, including material and operating costs.
    -   Includes a robust `check_recursion` method to prevent circular dependencies (e.g., a BOM cannot contain itself as a raw material).
    -   Provides a method to get an "exploded" view of all raw materials, including those from sub-assembly BOMs.

### b. `Workstation`

-   **File Path**: [`erpnext/manufacturing/doctype/workstation/workstation.py`](erpnext-develop/erpnext/manufacturing/doctype/workstation/workstation.py)
-   **Purpose**: To define a manufacturing resource (machine, assembly line, etc.).
-   **Key Fields**: `workstation_name`, `hour_rate`, `production_capacity`.
-   **Child Tables**: `Workstation Working Hour`.
-   **Logic**:
    -   Calculates the total operating cost per hour.
    -   Validates operating schedules to prevent overlapping time entries.
    -   Integrates with a `Holiday List` to account for non-working days.

### c. `Production Plan`

-   **File Path**: [`erpnext/manufacturing/doctype/production_plan/production_plan.py`](erpnext-develop/erpnext/manufacturing/doctype/production_plan/production_plan.py)
-   **Purpose**: To plan production based on aggregated demand.
-   **Key Fields**: `get_items_from` (Sales Order or Material Request), `company`.
-   **Child Tables**: `Production Plan Item` (items to be produced), `Production Plan Sales Order` (source SOs).
-   **Logic**:
    -   Provides methods to pull open `Sales Orders` or `Material Requests` and consolidate the required production items.
    -   Can generate `Work Orders` for the planned items.
    -   Can generate `Material Requests` for the required raw materials.

### d. `Work Order`

-   **File Path**: [`erpnext/manufacturing/doctype/work_order/work_order.py`](erpnext-develop/erpnext/manufacturing/doctype/work_order/work_order.py)
-   **Purpose**: The core transactional document for managing a specific production run.
-   **Key Fields**: `production_item`, `qty`, `bom_no`, `wip_warehouse`, `fg_warehouse`, `status`.
-   **Child Tables**: `Work Order Item` (required materials), `Work Order Operation`.
-   **Logic**:
    -   Pulls materials and operations from the specified `BOM`.
    -   Tracks the quantity produced against the quantity to manufacture.
    -   Manages the creation of `Job Cards` for each operation.
    -   The `status` field (`Draft`, `Not Started`, `In Process`, `Completed`, `Stopped`, `Closed`) drives the production workflow and reporting.

## 4. Integrations

-   **Stock**: Deeply integrated. `Work Orders` reserve raw materials from `Bin`. `Stock Entries` are used to transfer materials to the WIP warehouse and to receive finished goods into the FG warehouse.
-   **Accounts**: The costs calculated in the `BOM` and `Work Order` are used to value the finished goods and to book expenses in the general ledger.
-   **Selling**: `Sales Orders` are a primary source of demand for `Production Plans`.
-   **Buying**: `Material Requests` generated from a `Production Plan` can be used to create `Purchase Orders` for raw materials.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.manufacturing.doctype.bom.bom`
- `get_routing`: Fetches the operations from a Routing template.
- `get_bom_material_detail`: Fetches raw material details for a BOM.
- `update_cost`: Recalculates and updates the cost of a BOM.
- `add_raw_materials`: Adds raw materials to a specific operation in a BOM.
- `add_materials_from_bom`: Imports materials from another BOM.
- `get_bom_items`: Gets the list of items required for a BOM.
- `get_children`: Fetches child BOMs for the BOM tree view.
- `get_bom_diff`: Compares two BOMs and shows the differences.
- `make_variant_bom`: Creates a new BOM for an item variant.

### `erpnext.manufacturing.doctype.work_order.work_order`
- `get_items_and_operations_from_bom`: Fetches items and operations from the selected BOM.
- `make_bom`: Creates a new BOM from the Work Order.
- `make_stock_reservation_entries`: Creates stock reservation entries for raw materials.
- `cancel_stock_reservation_entries`: Cancels stock reservation entries.
- `get_item_details`: Fetches details for the production item.
- `make_work_order`: Creates a new Work Order (often from a Production Plan).
- `check_if_scrap_warehouse_mandatory`: Checks if a scrap warehouse is required.
- `set_work_order_ops`: Sets the operations for a Work Order.
- `make_stock_entry`: Creates a Stock Entry for material transfer or finished goods receipt.
- `get_default_warehouse`: Gets the default manufacturing warehouses.
- `stop_unstop`: Stops or re-opens a Work Order.
- `make_job_card`: Creates Job Cards for the Work Order's operations.
- `close_work_order`: Closes a Work Order.
- `create_pick_list`: Creates a Pick List for the required raw materials.
- `make_stock_return_entry`: Creates a return entry for unused materials.

### `erpnext.manufacturing.doctype.production_plan.production_plan`
- `validate_sales_orders`: Validates the selected Sales Orders.
- `get_open_sales_orders`: Fetches open Sales Orders to pull into the plan.
- `get_pending_material_requests`: Fetches pending Material Requests to pull into the plan.
- `combine_so_items`: Combines items from multiple Sales Orders.
- `get_items`: Fetches items to be produced.
- `set_status`: Sets the status of the Production Plan.
- `make_work_order`: Creates Work Orders from the Production Plan.
- `make_material_request`: Creates Material Requests from the Production Plan.
- `get_sub_assembly_items`: Gets the sub-assembly items required for the plan.
- `download_raw_materials`: Downloads a report of all required raw materials.
- `get_bin_details`: Gets stock details for an item from a warehouse.
- `get_so_details`: Fetches details for a Sales Order.
- `get_items_for_material_requests`: Gets the items required for a Material Request.
- `get_item_data`: Fetches data for an item.

### `erpnext.manufacturing.doctype.job_card.job_card`
- `get_required_items`: Fetches the raw materials required for the job.
- `pause_job`: Pauses the job and records the time.
- `resume_job`: Resumes a paused job.
- `start_timer`: Starts the timer for a job.
- `complete_job_card`: Marks the job card as complete.
- `make_stock_entry_for_semi_fg_item`: Creates a stock entry for a semi-finished good.
- `make_subcontracting_po`: Creates a Subcontracting Purchase Order.
- `make_time_log`: Creates a Time Log entry for the job.
- `get_operation_details`: Fetches details for the operation.
- `make_material_request`: Creates a Material Request from the Job Card.
- `make_stock_entry`: Creates a Stock Entry from the Job Card.
- `get_job_details`: Fetches details for multiple job cards.
- `make_corrective_job_card`: Creates a new job card to correct a previous one.

### `erpnext.manufacturing.doctype.workstation.workstation`
- `set_data_based_on_workstation_type`: Sets default data based on the workstation type.
- `start_job`: Starts a job on the workstation.
- `complete_job`: Completes a job on the workstation.
- `get_job_cards`: Fetches job cards for the workstation.
- `get_raw_materials`: Fetches raw materials for a job card.
- `get_default_holiday_list`: Gets the default holiday list.
- `get_workstations`: Gets a list of all workstations.
- `update_job_card`: Updates a job card's status.
- `validate_job_card`: Validates a job card.

### Other
- `erpnext.manufacturing.doctype.bom_update_tool.bom_update_tool.enqueue_replace_bom`: Enqueues a job to replace a BOM in other BOMs.
- `erpnext.manufacturing.doctype.bom_update_tool.bom_update_tool.enqueue_update_cost`: Enqueues a job to update the cost of multiple BOMs.
- `erpnext.manufacturing.doctype.blanket_order.blanket_order.make_order`: Creates a Sales/Purchase Order from a Blanket Order.