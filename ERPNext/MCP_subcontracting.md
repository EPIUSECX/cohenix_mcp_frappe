# Model Context Profile: Subcontracting

## 1. Module Overview

The `subcontracting` module in ERPNext provides a specialized workflow for managing the process of outsourcing manufacturing or assembly tasks to a third-party vendor (the subcontractor or "job worker"). This module is designed to track the entire subcontracting lifecycle, from ordering the subcontracted service to supplying the raw materials and receiving the finished goods.

It is tightly integrated with the `Buying` and `Stock` modules, leveraging documents like `Purchase Order` and `Stock Entry` to manage the financial and inventory aspects of the process.

## 2. Core Components

### 2.1. `Subcontracting Order`

This is the primary document used to initiate and manage a subcontracting process. It acts as a central hub linking the purchase of the subcontracting service to the transfer of raw materials.

-   **Key Features**:
    -   **Link to Purchase Order**: A `Subcontracting Order` is always linked to a `Purchase Order` that has been marked as `is_subcontracted`. This PO contains the service items being purchased from the subcontractor.
    -   **Supplier and Warehouse**: It specifies the `Supplier` (the subcontractor) and their `supplier_warehouse`, which represents the location where the raw materials will be sent.
    -   **Finished Goods**: The `items` child table lists the finished goods that are expected to be received from the subcontractor.
    -   **Raw Materials Supplied**: The `supplied_items` child table lists the raw materials that the company will provide to the subcontractor. This list is typically populated from the `BOM` of the finished good.
    -   **Status Tracking**: The order progresses through various statuses, such as `Open`, `Partial Material Transferred`, `Material Transferred`, `Partially Received`, and `Completed`.

-   **Business Logic (`subcontracting_order.py`)**:
    -   `validate_purchase_order_for_subcontracting()`: Ensures that the linked `Purchase Order` is a valid, submitted subcontracting PO.
    -   `update_status()`: Automatically updates the order's status based on the quantity of materials transferred and received.
    -   `make_subcontracting_receipt()`: A controller method to create a `Subcontracting Receipt` from the order.

### 2.2. `Subcontracting Receipt`

This document is used to record the receipt of finished goods from the subcontractor. It also serves to record the consumption of the raw materials that were supplied to them.

-   **Key Features**:
    -   **Link to Order**: It is typically created from a `Subcontracting Order`.
    -   **Received Items**: The `items` child table lists the finished goods received from the subcontractor, including accepted and rejected quantities.
    -   **Consumed Items**: The `supplied_items` child table lists the raw materials that were consumed by the subcontractor to produce the finished goods. This data is crucial for accurate stock valuation.
    -   **Stock Impact**: On submission, it creates `Stock Ledger Entries` to:
        -   Increase the stock of finished goods in the company's warehouse.
        -   Decrease the stock of raw materials from the subcontractor's virtual warehouse.
    -   **Return**: A `Subcontracting Receipt` can be marked as a `is_return` to handle the return of defective goods to the subcontractor.

-   **Business Logic (`subcontracting_receipt.py`)**:
    -   `on_submit()`: Triggers the creation of `Stock Ledger Entries` and updates the status of the linked `Subcontracting Order`.
    -   `get_scrap_items()`: Can fetch scrap items from the BOM and add them to the receipt, allowing for the accounting of manufacturing scrap.
    -   `auto_create_purchase_receipt()`: Can be configured to automatically create a `Purchase Receipt` for the subcontracting service, linking the stock movement to the financial transaction.

## 3. Data Flow and Architecture

1.  A **`Purchase Order`** is created for a subcontracting service item, and the `is_subcontracted` checkbox is ticked.
2.  A **`Subcontracting Order`** is created from this `Purchase Order`. The system populates the `supplied_items` table based on the `BOM` of the finished good being subcontracted.
3.  A **`Stock Entry`** with the purpose `Send to Subcontractor` is created to transfer the raw materials from the company's warehouse to the subcontractor's virtual warehouse. This updates the `total_supplied_qty` on the `Subcontracting Order`.
4.  When the finished goods are received from the subcontractor, a **`Subcontracting Receipt`** is created.
5.  The `Subcontracting Receipt` records the quantity of finished goods received and the quantity of raw materials consumed.
6.  On submission, the `Subcontracting Receipt` updates the stock levels of both the finished goods and the raw materials. It also updates the `received_qty` on the `Subcontracting Order`, which in turn updates the `per_received` status.
7.  Finally, a `Purchase Invoice` is created against the original `Purchase Order` to pay the subcontractor for their service.

## 4. Architectural Significance

The `subcontracting` module provides a robust and auditable workflow for a common manufacturing scenario. By creating dedicated documents (`Subcontracting Order`, `Subcontracting Receipt`), it separates the subcontracting process from standard purchasing and manufacturing, providing greater clarity and control.

The architecture ensures that the inventory of raw materials at the subcontractor's location is accurately tracked. The link between the `Subcontracting Order` and the `Purchase Order` ensures that the financial and inventory aspects of the process are tightly integrated. This allows for accurate costing of the finished goods, including the cost of the raw materials and the subcontracting service.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.subcontracting.doctype.subcontracting_order.subcontracting_order`
- `make_subcontracting_receipt`: Creates a Subcontracting Receipt from a Subcontracting Order.
- `update_subcontracting_order_status`: Updates the status of a Subcontracting Order.

### `erpnext.subcontracting.doctype.subcontracting_receipt.subcontracting_receipt`
- `reset_raw_materials`: Resets the raw materials table in the receipt.
- `get_scrap_items`: Fetches scrap items from the BOM.
- `set_missing_values`: Sets default values in the receipt form.
- `make_subcontract_return`: Creates a return Subcontracting Receipt.
- `make_purchase_receipt`: Creates a Purchase Receipt for the subcontracting service.

### `erpnext.subcontracting.doctype.subcontracting_bom.subcontracting_bom`
- `get_subcontracting_boms_for_finished_goods`: Fetches Subcontracting BOMs for a given finished good.
- `get_subcontracting_boms_for_service_item`: Fetches Subcontracting BOMs for a given service item.