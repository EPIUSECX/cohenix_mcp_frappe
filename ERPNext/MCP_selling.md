# Model Context Profile: Selling

## 1. Module Overview

The `selling` module is one of the most critical modules in ERPNext, encapsulating the entire sales lifecycle of a business. It provides a comprehensive set of tools to manage the customer relationship from the initial quotation to the final sales order, and includes functionalities for managing customers, pricing, sales teams, and various sales-related transactions.

The module is designed to be highly integrated with other modules like Accounts, Stock, and CRM, ensuring a seamless flow of information from sales activities to finance and inventory management.

## 2. Core Components

### 2.1. `Customer` DocType

The `Customer` is the master record for any individual or company that purchases goods or services. It serves as the central repository for all customer-related information.

-   **Key Features**:
    -   **Master Data**: Stores fundamental customer information, including name, type (Company/Individual), group, and territory.
    -   **Defaults**: Defines default settings for transactions with the customer, such as `Billing Currency`, `Default Price List`, and `Payment Terms`.
    -   **Credit Management**: Manages customer credit through the `Customer Credit Limit` child table, allowing for company-specific credit limits.
    -   **Sales Team**: Assigns a default sales team to the customer for commission and reporting purposes.
    -   **Address and Contact**: Manages multiple addresses and contacts linked to the customer.
    -   **Loyalty Program**: Can be linked to a `Loyalty Program` for tracking and redeeming loyalty points.

-   **Business Logic (`customer.py`)**:
    -   `check_credit_limit()`: A crucial function called from sales transactions to validate if a new order is within the customer's credit limit.
    -   `autoname()`: Handles customer naming based on the `Selling Settings` (either by customer name or naming series).
    -   `on_update()`: Triggers the creation of primary contact and address records if they don't exist.

### 2.2. `Quotation` DocType

The `Quotation` is the document used to send a proposal or price offer to a potential customer. It is the starting point for most sales cycles.

-   **Key Features**:
    -   **Party Linking**: Can be linked to a `Customer`, `Lead`, or `Prospect`.
    -   **Item and Pricing**: Contains a list of items with quantities, rates, and discounts. It uses the `Selling Price List` and `Pricing Rules` to determine item prices.
    -   **Validity**: Has a `valid_till` date, after which the quotation may expire.
    -   **Status Tracking**: The status of a quotation progresses from `Draft` to `Open`, `Replied`, `Ordered`, `Lost`, or `Cancelled`.
    -   **Lost Reasons**: If a quotation is lost, the reasons can be captured for analysis.

-   **Business Logic (`quotation.py`)**:
    -   `make_sales_order()`: A controller method to create a `Sales Order` directly from a submitted quotation.
    -   `set_status()`: Automatically updates the status based on whether a `Sales Order` has been created against it.
    -   `update_opportunity()`: Updates the status of a linked `Opportunity` when the quotation is submitted or cancelled.

### 2.3. `Sales Order` DocType

The `Sales Order` is a binding document that confirms a sale to a customer. It is the central transaction in the selling module, linking to downstream documents like `Delivery Note` and `Sales Invoice`.

-   **Key Features**:
    -   **Order Confirmation**: Captures all details of a confirmed order, including items, quantities, rates, delivery dates, and payment terms.
    -   **Stock Management**: Can `reserve_stock` for the ordered items, impacting the projected quantity in the warehouse.
    -   **Drop Shipping**: Supports drop shipping by allowing items to be marked as `delivered_by_supplier`.
    -   **Status Tracking**: Tracks the fulfillment status of the order through `delivery_status` (`Not Delivered`, `Partly Delivered`, `Fully Delivered`) and `billing_status` (`Not Billed`, `Partly Billed`, `Fully Billed`).
    -   **Integration**: Can be created from a `Quotation` and is the source document for creating `Delivery Notes`, `Sales Invoices`, and `Work Orders`.

-   **Business Logic (`sales_order.py`)**:
    -   `on_submit()`: Triggers credit limit checks, updates reserved quantity, and updates the status of the linked `Quotation`.
    -   `on_cancel()`: Reverses the stock reservations and updates the status of linked documents.
    -   `update_status()`: A key method that recalculates the `per_delivered` and `per_billed` percentages and sets the overall status of the order (e.g., `To Deliver`, `To Bill`, `Completed`, `Closed`).
    -   `make_delivery_note()`, `make_sales_invoice()`, `make_work_orders()`: Controller methods to create downstream documents.

### 2.4. `Selling Settings` DocType

This is a singleton DocType that provides global configuration for the entire selling module.

-   **Key Features**:
    -   **Customer Defaults**: Sets the default `Customer Group` and `Territory`.
    -   **Transaction Rules**: Defines rules such as whether a `Sales Order` is required to create a `Sales Invoice` or `Delivery Note`.
    -   **Pricing**: Controls whether to maintain the same rate throughout the sales cycle and whether users can edit price list rates.
    -   **Naming**: Determines how customers are named (`Customer Name` or `Naming Series`).

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

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.selling.doctype.customer.customer`
- `get_customer_group_details`: Fetches details from the parent Customer Group.
- `make_quotation`: Creates a Quotation from a Customer.
- `make_opportunity`: Creates an Opportunity from a Customer.
- `make_payment_entry`: Creates a Payment Entry for a Customer.
- `get_loyalty_programs`: Fetches loyalty programs applicable to a Customer.
- `send_emails`: Sends emails to customers regarding their outstanding balance.

### `erpnext.selling.doctype.quotation.quotation`
- `declare_enquiry_lost`: Sets the quotation status to 'Lost' and records the reasons.
- `make_sales_order`: Creates a Sales Order from a Quotation.
- `make_sales_invoice`: Creates a Sales Invoice from a Quotation.

### `erpnext.selling.doctype.sales_order.sales_order`
- `create_stock_reservation_entries`: Creates stock reservation entries for the items in the SO.
- `cancel_stock_reservation_entries`: Cancels stock reservation entries for the SO.
- `is_enable_cutoff_date_on_bulk_delivery_note_creation`: Checks a system setting.
- `close_or_unclose_sales_orders`: A bulk action to close or reopen multiple SOs.
- `make_material_request`: Creates a Material Request from a Sales Order.
- `make_project`: Creates a Project from a Sales Order.
- `make_delivery_note`: Creates a Delivery Note from a Sales Order.
- `make_sales_invoice`: Creates a Sales Invoice from a Sales Order.
- `make_maintenance_schedule`: Creates a Maintenance Schedule from a Sales Order.
- `make_maintenance_visit`: Creates a Maintenance Visit from a Sales Order.
- `get_events`: Fetches sales order data to be displayed on the calendar.
- `make_purchase_order_for_default_supplier`: Creates a Purchase Order for drop-shipping.
- `make_purchase_order`: Creates a Purchase Order from a Sales Order.
- `make_work_orders`: Creates Work Orders from a Sales Order.
- `update_status`: Updates the status of a Sales Order.
- `make_raw_material_request`: Creates a Material Request for raw materials.
- `make_inter_company_purchase_order`: Creates an inter-company Purchase Order.
- `create_pick_list`: Creates a Pick List from a Sales Order.
- `get_work_order_items`: Gets items from a Work Order linked to the Sales Order.
- `get_stock_reservation_status`: Gets the stock reservation status for the SO.

### `erpnext.selling.page.point_of_sale.point_of_sale`
- `get_parent_item_group`: Gets the root Item Group for the POS view.
- `get_items`: Fetches items for the POS grid.
- `search_for_serial_or_batch_or_barcode_number`: Searches for an item by its serial/batch/barcode.
- `check_opening_entry`: Checks if a POS Opening Entry exists for the user.
- `create_opening_voucher`: Creates a POS Opening Entry.
- `get_past_order_list`: Fetches a list of past POS orders.
- `set_customer_info`: Sets customer information for a POS transaction.
- `get_pos_profile_data`: Fetches data for the selected POS Profile.
- `get_customer_recent_transactions`: Fetches recent transactions for a customer.

### `erpnext.selling.doctype.sms_center.sms_center`
- `create_receiver_list`: Creates a list of SMS recipients.
- `send_sms`: Sends SMS messages to the receiver list.