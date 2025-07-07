# Model Context Profile: Selling

## 1. Module Overview

The `selling` module is one of the most critical modules in ERPNext, encapsulating the entire sales lifecycle of a business. It provides a comprehensive set of tools to manage the customer relationship from the initial quotation to the final sales order, and includes functionalities for managing customers, pricing, sales teams, and various sales-related transactions.

The module is designed to be highly integrated with other modules like Accounts, Stock, and CRM, ensuring a seamless flow of information from sales activities to finance and inventory management.

## 2. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development.

### 2.1. Server-Side (Python)

#### `erpnext.selling.doctype.sales_order.sales_order`

-   **`make_delivery_note(source_name, ...)`**: A whitelisted function that creates a `Delivery Note` from a `Sales Order`. It intelligently maps items that are pending delivery.
-   **`make_sales_invoice(source_name, ...)`**: A whitelisted function that creates a `Sales Invoice` from a `Sales Order`, mapping items that are pending billing.
-   **`on_submit()`**: This instance method is the core logic for submitting a sales order. It performs critical validations like checking the customer's credit limit and updates the reserved quantity for stock items.
-   **`update_status(status, name)`**: A whitelisted function that updates the fulfillment status of the order (e.g., 'To Deliver', 'To Bill', 'Completed', 'Closed'). This is the central method for progressing the order through its lifecycle.

#### `erpnext.selling.doctype.quotation.quotation`

-   **`make_sales_order(source_name, ...)`**: A whitelisted function that converts a `Quotation` into a `Sales Order`. This is the primary function for advancing a deal from the quotation stage to a confirmed order.
-   **`declare_enquiry_lost(...)`**: A whitelisted function that allows a user to mark a quotation as 'Lost', capturing the reasons for analysis. This is crucial for sales performance tracking.
-   **`on_submit()`**: This instance method updates the status of any linked `Opportunity`, ensuring the sales funnel is kept up-to-date.
-   **`set_expired_status()`**: A scheduler function that automatically sets the status of quotations to 'Expired' if their `valid_till` date has passed, helping to maintain a clean pipeline.

### 2.2. Client-Side (JavaScript)

#### `erpnext.selling.SalesOrderController`

-   **`refresh()`**: This is the main UI controller for the Sales Order form. It dynamically adds the "Create" buttons (e.g., "Delivery Note", "Sales Invoice", "Work Order", "Pick List") based on the order's status and permissions, guiding the user through the fulfillment process.
-   **`make_delivery_note_based_on_delivery_date()`**: This client-side function provides a dialog for users to select items based on their delivery dates before creating a `Delivery Note`, which is useful for managing partial shipments.
-   **`make_sales_invoice()`**: This function calls the server-side `make_sales_invoice` method via `frappe.model.open_mapped_doc`, which handles the creation and routing to the new invoice document.
-   **`create_stock_reservation_entries(frm)`**: This function opens a dialog that allows users to selectively reserve stock for items in the sales order, providing granular control over inventory allocation.

#### `erpnext.selling.QuotationController`

-   **`refresh()`**: This method controls the UI for the Quotation form. It adds the "Sales Order" button if the quotation is submitted and not expired, providing the primary call to action.
-   **`make_sales_order()`**: This function calls the server-side `make_sales_order` method. It also includes logic to handle quotations with alternative items by first showing a selection dialog.
-   **`show_alternative_items_dialog()`**: This function creates and shows a dialog for the user to select which items to include in the `Sales Order` when the quotation contains alternatives.

## 3. Data Flow and Integrations

1.  A **`Lead`** or **`Opportunity`** from the CRM module can be converted into a **`Quotation`**.
2.  A **`Quotation`** is sent to a **`Customer`**. If accepted, it is converted into a **`Sales Order`**.
3.  The **`Sales Order`** confirms the sale and reserves stock. It becomes the reference for:
    -   **`Delivery Note`**: To manage the shipment of goods from the warehouse (Stock module).
    -   **`Sales Invoice`**: To bill the customer (Accounts module).
    -   **`Work Order`**: If the item needs to be manufactured (Manufacturing module).
    -   **`Purchase Order`**: If the item is to be drop-shipped (Buying module).
4.  The status of the **`Sales Order`** is automatically updated as goods are delivered and invoices are paid, providing a real-time view of the order fulfillment process.

## 4. Architectural Significance

The `selling` module is the engine of the sales process in ERPNext. Its robust data model and tightly integrated workflows ensure data consistency from the initial customer interaction to the final financial accounting. The use of a central `Sales Order` document as the source of truth for fulfillment and billing is a key architectural pattern that provides control and visibility over the entire order-to-cash cycle. The `Selling Settings` DocType allows for significant customization of the module's behavior to fit different business processes.