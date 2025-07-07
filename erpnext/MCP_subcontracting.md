# Model Context Profile: Subcontracting

## 1. Module Overview

The Subcontracting module in ERPNext manages the process of outsourcing manufacturing or service tasks to a third-party vendor. It handles the transfer of raw materials to the subcontractor, the receipt of the finished goods, and the associated accounting and stock movements.

## 2. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development. The module's architecture is centered around the `Subcontracting Order` (the initiator) and the `Subcontracting Receipt` (the completer), with both inheriting from a shared `SubcontractingController`.

### 2.1. Server-Side (Python)

#### `erpnext.controllers.subcontracting_controller.SubcontractingController`

This base class contains the core logic shared between the Order and Receipt documents.

-   **`create_raw_materials_supplied(set_missing_values=True)`**: A crucial method that populates the "Supplied Items" table based on the BOM of the finished good. It calculates the required quantity of each raw material needed for the subcontracting process.

-   **`make_rm_stock_entry(subcontract_order, order_doctype)`**: A `@frappe.whitelist()` function that creates a `Stock Entry` of type "Material Transfer for Subcontract" to move the raw materials from the company's warehouse to the supplier's virtual warehouse.

#### `erpnext.subcontracting.doctype.subcontracting_order.subcontracting_order.SubcontractingOrder`

-   **`on_submit()`**: This method updates the status of the linked `Material Request` and the subcontracted quantity on the original `Purchase Order`.

-   **`make_subcontracting_receipt(source_name, target_doc=None)`**: A `@frappe.whitelist()` function that uses `get_mapped_doc` to create a `Subcontracting Receipt` from the `Subcontracting Order`, transferring all relevant data.

#### `erpnext.subcontracting.doctype.subcontracting_receipt.subcontracting_receipt.SubcontractingReceipt`

-   **`on_submit()`**: This is the transactional core of the module. It orchestrates several critical actions:
    -   Updates the stock ledger for the received finished goods (increasing stock) and the consumed raw materials (decreasing stock).
    -   Creates the corresponding `GL Entries` to debit the stock asset account and credit the stock expense account.
    -   Updates the status of the original `Subcontracting Order`.
    -   Triggers the `auto_create_purchase_receipt` function.

-   **`make_purchase_receipt(source_name, ...)`**: A `@frappe.whitelist()` function that automatically creates a `Purchase Receipt` for the service items associated with the subcontracting work. This is a key automation that closes the financial loop by allowing the creation of a `Purchase Invoice` to pay the subcontractor.

### 2.2. Client-Side (JavaScript)

#### `erpnext.buying.SubcontractingOrderController` in `subcontracting_order.js`

-   **`refresh(doc)`**: The UI controller for the `Subcontracting Order` form. It provides two key custom buttons:
    -   **"Material to Supplier"**: Triggers the `make_rm_stock_entry` server-side function to create the stock transfer.
    -   **"Subcontracting Receipt"**: Triggers the `make_subcontracting_receipt` server-side function to create the receipt document.

#### `frappe.ui.form.on("Subcontracting Receipt", ...)` in `subcontracting_receipt.js`

-   **`refresh(frm)`**: The UI controller for the `Subcontracting Receipt` form. It provides a button to create a `Purchase Receipt` manually if the automatic creation is disabled. It also provides a button to create a `Subcontract Return` for handling rejected items.