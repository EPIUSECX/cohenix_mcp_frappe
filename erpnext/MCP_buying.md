# Model Context Profile: Buying

## 1. Module Overview

The **Buying** module in ERPNext manages the entire procure-to-pay lifecycle. It provides a comprehensive set of tools to handle procurement planning, supplier management, purchase requests, quotation management, purchase orders, and subcontracting. The module is tightly integrated with `Accounts`, `Stock`, and `Manufacturing` to ensure a seamless flow of information and materials.

The core purpose of this module is to streamline procurement activities, maintain optimal inventory levels, manage supplier relationships, and ensure cost-effective purchasing.

## 2. Core Concepts

### a. Procurement Workflow

The module follows a standard procurement workflow:

1.  **Supplier Management**: Onboarding and managing vendor data in the `Supplier` DocType.
2.  **Request for Quotation (RFQ)**: Creating and sending an [`RFQ`](erpnext-develop/erpnext/buying/doctype/request_for_quotation/request_for_quotation.py) to multiple suppliers to solicit pricing for items, often generated from a `Material Request`.
3.  **Supplier Quotation**: Recording the prices and terms received from vendors in the [`Supplier Quotation`](erpnext-develop/erpnext/buying/doctype/supplier_quotation/supplier_quotation.py) DocType. This allows for comparison between different suppliers.
4.  **Purchase Order (PO)**: Issuing a formal [`Purchase Order`](erpnext-develop/erpnext/buying/doctype/purchase_order/purchase_order.py) to the selected supplier, which becomes a binding contract.
5.  **Goods Receipt**: Recording the receipt of items against a PO using the `Purchase Receipt` document (from the `Stock` module).
6.  **Invoice Booking**: Recording the supplier's invoice using the `Purchase Invoice` document (from the `Accounts` module).

### b. Supplier Lifecycle Management

The [`Supplier`](erpnext-develop/erpnext/buying/doctype/supplier/supplier.py) DocType is the master record for all vendors. It stores critical information, including:
-   **Supplier Details**: Name, type (Company, Individual), and group.
-   **Contact & Address**: Manages primary contacts and addresses.
-   **Accounting**: Default payment terms, currency, and accounts.
-   **Portal Access**: Manages supplier portal users, allowing them to view RFQs and submit quotations online.
-   **Status Control**: Suppliers can be put `On Hold` to prevent the creation of new RFQs or Purchase Orders.

### c. Subcontracting

The Buying module facilitates subcontracting workflows where raw materials are sent to a supplier for processing.
-   A [`Purchase Order`](erpnext-develop/erpnext/buying/doctype/purchase_order/purchase_order.py) can be marked as `is_subcontracted`.
-   The system tracks the transfer of raw materials to the supplier and the receipt of finished goods.
-   It integrates with the `BOM` (Bill of Materials) to determine the required raw materials for the subcontracted service.

### d. Drop Shipping

The module supports drop shipping, where a supplier delivers goods directly to a customer. This is managed by linking a `Sales Order` to a `Purchase Order` item and marking it as `delivered_by_supplier`.

## 3. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development.

### 3.1. Server-Side (Python)

#### `erpnext.buying.doctype.purchase_order.purchase_order`

-   **`make_purchase_receipt(source_name, target_doc=None)`**: A whitelisted function that creates a `Purchase Receipt` document from a given `Purchase Order`. It maps the relevant fields and calculates the pending quantity to be received.
-   **`make_purchase_invoice(source_name, target_doc=None)`**: A whitelisted function that creates a `Purchase Invoice` from a `Purchase Order`. It handles the mapping of items, taxes, and other details, calculating the pending quantity to be billed.
-   **`make_subcontracting_order(source_name, ...)`**: A whitelisted function that creates a `Subcontracting Order` from a subcontracting `Purchase Order`. This is a key function in the subcontracting workflow.
-   **`update_status(status, name)`**: A whitelisted function called by the client-side to change the PO's status (e.g., 'On Hold', 'Closed'). It triggers a cascade of updates, including recalculating ordered quantities and updating linked documents.
-   **`on_submit()`**: This instance method is the core logic for submitting a PO. It updates the `ordered_qty` in `Bin` for stock items, updates the status of linked `Material Requests`, and validates the budget.

#### `erpnext.buying.doctype.supplier_quotation.supplier_quotation`

-   **`make_purchase_order(source_name, target_doc=None)`**: A whitelisted function that creates a `Purchase Order` from a `Supplier Quotation`. This is the standard way to convert a quote into an order.
-   **`on_submit()`**: This instance method updates the status of the linked `Request for Quotation`, marking the supplier's quote as 'Received'.
-   **`set_expired_status()`**: This function is designed to be called by the scheduler. It iterates through all submitted `Supplier Quotations` and sets their status to 'Expired' if their `valid_till` date has passed.

### 3.2. Client-Side (JavaScript)

#### `erpnext.buying.PurchaseOrderController`

-   **`refresh()`**: This method is the main UI controller for the Purchase Order form. It dynamically adds buttons like "Purchase Receipt", "Purchase Invoice", "Hold", and "Close" based on the document's status (`docstatus`, `per_received`, `per_billed`).
-   **`make_purchase_receipt()`**: This client-side function calls the server-side `make_purchase_receipt` method using `frappe.model.open_mapped_doc`, which handles the creation and routing to the new document.
-   **`make_purchase_invoice()`**: Similar to the receipt function, this calls the server-side `make_purchase_invoice` method.
-   **`add_from_mappers()`**: This method adds the "Get Items From" button, which allows users to pull items from open `Material Requests` or `Supplier Quotations`, providing a powerful way to create POs from upstream documents.

#### `erpnext.buying.SupplierQuotationController`

-   **`refresh()`**: This method controls the UI for the Supplier Quotation form. It adds the "Purchase Order" button if the quotation is submitted, allowing for direct conversion to a PO.
-   **`make_purchase_order()`**: This function calls the server-side `make_purchase_order` method to generate a PO from the quotation.

## 4. Utility Functions

-   **File Path**: [`erpnext/buying/utils.py`](erpnext-develop/erpnext/buying/utils.py)
-   **Key Functions**:
    -   `update_last_purchase_rate(doc, is_submit)`: Updates the `last_purchase_rate` on the `Item` master. This is a critical function for valuation and pricing. It is called from `Purchase Receipt` and `Purchase Invoice` on submit and cancel.
    -   `validate_for_items(doc)`: A common validation function used across buying documents to check for valid items, warehouses for stock items, and end-of-life status.
    -   `check_on_hold_or_closed_status(doctype, docname)`: Prevents transactions against documents that are `On Hold` or `Closed`.

## 5. Integrations

-   **Accounts**: The Buying module is deeply integrated with Accounts. `Purchase Order` and `Supplier` link to `Payment Terms Template`, `Tax Category`, and party accounts. `Purchase Invoice` is the final accounting document in the cycle.
-   **Stock**: `Purchase Order` updates the `ordered_qty` in `Bin`. `Purchase Receipt` is the primary stock transaction document linked to a `Purchase Order`. Warehouses are mandatory for stock items in all buying transactions.
-   **Manufacturing**: The subcontracting feature directly links the procurement process with manufacturing operations, using `BOM`s to manage raw material requirements.
-   **Selling**: The drop-shipping feature links a `Purchase Order` directly to a `Sales Order`.