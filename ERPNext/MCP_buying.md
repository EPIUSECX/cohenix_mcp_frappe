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

## 3. Key DocTypes and Data Models

### a. `Supplier`

-   **File Path**: [`erpnext/buying/doctype/supplier/supplier.py`](erpnext-develop/erpnext/buying/doctype/supplier/supplier.py)
-   **Inherits**: `TransactionBase`
-   **Purpose**: Master for vendor data.
-   **Key Fields**: `supplier_name`, `supplier_group`, `on_hold`, `is_internal_supplier`, `payment_terms`.
-   **Child Tables**: `PartyAccount` (for company-specific accounting), `PortalUser`.

### b. `Request for Quotation`

-   **File Path**: [`erpnext/buying/doctype/request_for_quotation/request_for_quotation.py`](erpnext-develop/erpnext/buying/doctype/request_for_quotation/request_for_quotation.py)
-   **Inherits**: `BuyingController`
-   **Purpose**: Solicit quotes from multiple suppliers.
-   **Key Fields**: `transaction_date`, `status` ('Draft', 'Submitted', 'Cancelled').
-   **Child Tables**:
    -   `Request for Quotation Item`: The list of items for which quotes are requested.
    -   `Request for Quotation Supplier`: The list of suppliers to whom the RFQ is sent. Each row tracks the `quote_status` ('Pending', 'Received').
-   **Logic**:
    -   Can be created from `Material Request`.
    -   Handles sending emails to suppliers via `supplier_rfq_mail`.
    -   Creates `Website User` and `Contact` if they don't exist for a supplier's email.
    -   Can be used to generate a `Supplier Quotation`.

### c. `Supplier Quotation`

-   **File Path**: [`erpnext/buying/doctype/supplier_quotation/supplier_quotation.py`](erpnext-develop/erpnext/buying/doctype/supplier_quotation/supplier_quotation.py)
-   **Inherits**: `BuyingController`
-   **Purpose**: Record a supplier's quotation.
-   **Key Fields**: `supplier`, `valid_till`, `status` ('Draft', 'Submitted', 'Expired', 'Cancelled').
-   **Child Tables**: `Supplier Quotation Item`.
-   **Logic**:
    -   Can be created from `Request for Quotation`.
    -   Updates the `quote_status` on the parent `Request for Quotation Supplier` table.
    -   The `set_expired_status` method is called via a scheduler to automatically expire quotations past their `valid_till` date.
    -   Can be used to create a `Purchase Order`.

### d. `Purchase Order`

-   **File Path**: [`erpnext/buying/doctype/purchase_order/purchase_order.py`](erpnext-develop/erpnext/buying/doctype/purchase_order/purchase_order.py)
-   **Inherits**: `BuyingController`
-   **Purpose**: A formal order placed with a supplier.
-   **Key Fields**: `supplier`, `transaction_date`, `schedule_date`, `is_subcontracted`, `status`.
-   **Status Lifecycle**: The status ('Draft', 'To Receive and Bill', 'To Bill', 'To Receive', 'Completed', 'Cancelled', 'Closed') is a key field that drives procurement reporting and actions. It is updated based on the quantities received (`Purchase Receipt`) and billed (`Purchase Invoice`).
-   **Child Tables**: `Purchase Order Item`.
-   **Logic**:
    -   Can be created from `Supplier Quotation` or `Material Request`.
    -   Updates `ordered_qty` in `Bin` and `Material Request`.
    -   Handles subcontracting logic, including reserving raw materials.
    -   Can be linked to `Blanket Order` for release management.
    -   Can be used to create `Purchase Receipt` and `Purchase Invoice`.

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

## 6. Business Logic and Automation

-   **Status Updates**: The status of a `Purchase Order` is automatically updated based on the creation and submission of linked `Purchase Receipts` and `Purchase Invoices`.
-   **Email Automation**: `Request for Quotation` automates the process of sending emails to suppliers and creating portal users.
-   **Pricing and Validation**: The module uses `Price List` for default rates and validates against `Supplier Scorecard` standings to enforce procurement policies.
-   **Last Purchase Rate**: The system automatically tracks the last purchase rate of an item, providing valuable data for future purchasing decisions.

## 7. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.buying.doctype.purchase_order.purchase_order`
- `get_last_purchase_rate`: Fetches the last purchase rate for the items in the PO.
- `close_or_unclose_purchase_orders`: A bulk action to close or reopen multiple POs.
- `make_purchase_receipt`: Creates a Purchase Receipt from a Purchase Order.
- `make_purchase_invoice`: Creates a Purchase Invoice from a Purchase Order.
- `make_purchase_invoice_from_portal`: Allows creation of a Purchase Invoice from the supplier portal.
- `update_status`: Updates the status of a Purchase Order.
- `make_inter_company_sales_order`: Creates a Sales Order in a target company for inter-company transfers.
- `make_subcontracting_order`: Creates a Subcontracting Order from a Purchase Order.

### `erpnext.buying.doctype.request_for_quotation.request_for_quotation`
- `get_supplier_email_preview`: Gets a preview of the email to be sent to a supplier.
- `send_supplier_emails`: Sends the RFQ to all listed suppliers.
- `make_supplier_quotation_from_rfq`: Creates a Supplier Quotation from an RFQ for a specific supplier.
- `create_supplier_quotation`: Allows a supplier to create a Supplier Quotation from the portal.
- `get_pdf`: Generates a PDF of the RFQ.
- `get_item_from_material_requests_based_on_supplier`: Fetches items from Material Requests, filtered by a supplier.
- `get_supplier_tag`: Gets the HTML tag for a supplier.

### `erpnext.buying.doctype.supplier.supplier`
- `get_supplier_group_details`: Fetches details from the parent Supplier Group.

### `erpnext.buying.doctype.supplier_quotation.supplier_quotation`
- `make_purchase_order`: Creates a Purchase Order from a Supplier Quotation.
- `make_purchase_invoice`: Creates a Purchase Invoice from a Supplier Quotation.
- `make_quotation`: Creates a (Sales) Quotation from a Supplier Quotation.

### `erpnext.buying.doctype.supplier_scorecard.supplier_scorecard`
- `get_timeline_data`: Fetches data for the scorecard timeline.
- `make_all_scorecards`: A utility to generate scorecards for all suppliers.

### `erpnext.buying.doctype.supplier_scorecard_criteria.supplier_scorecard_criteria`
- `get_criteria_list`: Gets the list of all available scorecard criteria.

### `erpnext.buying.doctype.supplier_scorecard_standing.supplier_scorecard_standing`
- `get_scoring_standing`: Gets the details of a specific scoring standing.
- `get_standings_list`: Gets the list of all available scorecard standings.

### `erpnext.buying.report.supplier_quotation_comparison.supplier_quotation_comparison`
- `set_default_supplier`: Sets the default supplier for an item.

### `erpnext.buying.utils`
- `get_linked_material_requests`: Fetches Material Requests linked to the items in a transaction.