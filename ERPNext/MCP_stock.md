# Model Context Profile: Stock

## 1. Module Overview

The `stock` module is the heart of inventory management in ERPNext. It provides a comprehensive suite of tools for tracking the quantity and value of items across multiple warehouses. The module is responsible for managing all inventory-related master data, processing all stock movements, and maintaining an accurate, perpetual inventory ledger.

Its functionality is deeply integrated with the Sales, Buying, and Manufacturing modules, as nearly every transaction in these modules has a stock impact.

## 2. Core Components

### 2.1. `Item` DocType

The `Item` is the master document for any product, material, or service that is bought, sold, stored, or consumed. It is one of the most complex and central DocTypes in ERPNext.

-   **Key Features**:
    -   **Stock Control**: The `is_stock_item` checkbox determines whether the system will maintain a stock ledger for the item.
    -   **Units of Measure (UOM)**: Defines the `stock_uom` and allows for multiple other UOMs with conversion factors.
    -   **Valuation**: Sets the `valuation_method` (FIFO or Moving Average) and stores the `valuation_rate`.
    -   **Serialization and Batching**: Can be configured to have `has_serial_no` or `has_batch_no`, which enforces the tracking of individual units or batches.
    -   **Warehousing**: Defines default warehouses and reorder levels per warehouse.
    -   **Variants**: An item can be a template (`has_variants` = 1), and variants can be generated from it based on `Item Attributes`.

### 2.2. `Warehouse` DocType

The `Warehouse` DocType is used to create and manage all physical or logical locations where stock is stored.

-   **Key Features**:
    -   **Hierarchy**: It is a tree-structured DocType, allowing for the creation of a hierarchy of warehouses (e.g., a main warehouse with several sub-locations).
    -   **Company Link**: Each warehouse is linked to a specific `Company`.
    -   **Accounting**: Can be linked to a specific `Account` in the Chart of Accounts to track the stock value for that warehouse separately.

### 2.3. `Stock Entry` DocType

The `Stock Entry` is the primary transactional document for recording internal stock movements. It is a versatile document used for various purposes.

-   **Key Features**:
    -   **Purpose-Driven**: The `purpose` field (e.g., `Material Transfer`, `Material Issue`, `Manufacture`, `Repack`) dictates the behavior of the document, including which warehouses are required (source or target) and how accounting entries are made.
    -   **Item Movement**: The `items` child table details the items being moved, their quantities, source and target warehouses, and valuation rates.
    -   **Manufacturing**: For `Manufacture` and `Repack` purposes, it consumes raw materials (outgoing stock) and creates finished goods (incoming stock), often based on a `BOM`.
    -   **Subcontracting**: Used to `Send to Subcontractor` and receive finished goods.

### 2.4. `Stock Ledger Entry` (SLE)

The `Stock Ledger Entry` is the immutable, append-only ledger that provides the foundation for perpetual inventory. It is the source of truth for all stock quantity and value calculations.

-   **Key Features**:
    -   **Immutable Record**: An SLE is created for every stock transaction (e.g., `Stock Entry`, `Delivery Note`, `Purchase Receipt`) and cannot be modified directly. To correct an entry, the source document must be cancelled and amended.
    -   **Detailed Tracking**: Each entry records the `item_code`, `warehouse`, `posting_date`, `posting_time`, `actual_qty` (the change in quantity), and `valuation_rate`.
    -   **Balance Calculation**: It stores the `qty_after_transaction` and `stock_value`, providing a running balance of stock levels and value at any point in time.
    -   **FIFO/LIFO Queue**: For FIFO/LIFO valuation, it maintains a `stock_queue` to track the cost of different batches of incoming stock.

### 2.5. `Stock Settings` DocType

This singleton DocType provides global configuration for the stock module.

-   **Key Features**:
    -   **Valuation Method**: Sets the default `valuation_method` for new items.
    -   **Negative Stock**: The `allow_negative_stock` setting determines whether the system will block transactions that would result in a negative stock balance.
    -   **Serialization and Batching**: Contains settings for how serial numbers and batches are created and managed.
    -   **Stock Freezing**: Allows for freezing stock transactions up to a certain date to prevent back-dated entries.

## 3. Data Flow and Architecture

1.  **Master Data**: **`Item`** and **`Warehouse`** masters are created in the `setup` and `stock` modules.
2.  **Transactions**: When a stock-related transaction occurs (e.g., a `Delivery Note` is submitted, a `Purchase Receipt` is received, or a `Stock Entry` is made), the system creates one or more **`Stock Ledger Entry`** records.
3.  **Ledger Posting**: For each item and warehouse in the transaction, an SLE is created.
    -   For an outgoing transaction, `actual_qty` is negative. The `valuation_rate` is determined by the chosen valuation method (FIFO or Moving Average).
    -   For an incoming transaction, `actual_qty` is positive. The `valuation_rate` is based on the purchase price or manufacturing cost.
4.  **Bin Update**: The system updates the `Bin` record (a cache of the current stock level) for the item and warehouse, reflecting the new `qty_after_transaction` from the SLE.
5.  **Reporting**: All stock reports, such as the `Stock Balance` and `Stock Ledger`, are generated by querying the `Stock Ledger Entry` table.

## 4. Architectural Significance

The `stock` module's architecture is centered around the principle of a perpetual, immutable ledger (`Stock Ledger Entry`). This design ensures a high degree of data integrity and provides a complete audit trail for every stock movement. It is a classic example of event sourcing, where the current state (the stock balance in a `Bin`) is derived from a sequence of historical events (the `Stock Ledger Entries`).

This robust and auditable foundation allows ERPNext to provide accurate, real-time inventory valuation and quantity tracking, which is essential for the effective management of a business's supply chain and finances. The clear separation between transactional documents (`Stock Entry`, `Delivery Note`) and the ledger (`Stock Ledger Entry`) is a key architectural pattern that ensures consistency and reliability.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.stock.doctype.stock_entry.stock_entry`
- `get_stock_and_rate`: Fetches stock levels and valuation rates for items.
- `get_item_details`: A comprehensive function to get all details for an item in the context of a stock entry.
- `set_items_for_stock_in`: Populates items for a stock-in entry.
- `get_items`: Fetches items for various purposes (e.g., from a BOM).
- `move_sample_to_retention_warehouse`: Creates a stock entry to move quality inspection samples.
- `make_stock_in_entry`: Creates a stock-in entry from another document.
- `get_work_order_details`: Fetches details from a Work Order.
- `get_uom_details`: Gets UOM conversion details.
- `get_expired_batch_items`: Fetches items with expired batches.
- `get_warehouse_details`: Fetches details for a warehouse.
- `validate_sample_quantity`: Validates the sample quantity for a quality inspection.
- `get_items_from_subcontract_order`: Fetches items from a Subcontracting Order.

### `erpnext.stock.doctype.delivery_note.delivery_note`
- `make_sales_invoice`: Creates a Sales Invoice from a Delivery Note.
- `make_delivery_trip`: Creates a Delivery Trip from a Delivery Note.
- `make_installation_note`: Creates an Installation Note.
- `make_packing_slip`: Creates a Packing Slip.
- `make_shipment`: Creates a Shipment record.
- `make_sales_return`: Creates a Sales Return (credit note) from a Delivery Note.
- `update_delivery_note_status`: Updates the status of a Delivery Note.
- `make_inter_company_purchase_receipt`: Creates an inter-company Purchase Receipt.

### `erpnext.stock.doctype.purchase_receipt.purchase_receipt`
- `make_purchase_invoice`: Creates a Purchase Invoice from a Purchase Receipt.
- `make_purchase_return_against_rejected_warehouse`: Creates a return for rejected items.
- `make_purchase_return`: Creates a Purchase Return (debit note).
- `update_purchase_receipt_status`: Updates the status of a Purchase Receipt.
- `make_stock_entry`: Creates a Stock Entry from a Purchase Receipt.
- `make_lcv`: Creates a Landed Cost Voucher.

### `erpnext.stock.doctype.material_request.material_request`
- `update_status`: Updates the status of a Material Request.
- `make_purchase_order`: Creates a Purchase Order.
- `make_request_for_quotation`: Creates a Request for Quotation.
- `make_supplier_quotation`: Creates a Supplier Quotation.
- `make_stock_entry`: Creates a Stock Entry for material transfer.
- `raise_work_orders`: Creates Work Orders for requested items.
- `create_pick_list`: Creates a Pick List.
- `make_in_transit_stock_entry`: Creates a stock entry for in-transit inventory.

### `erpnext.stock.doctype.pick_list.pick_list`
- `create_stock_reservation_entries`: Creates stock reservation entries for the items in the pick list.
- `cancel_stock_reservation_entries`: Cancels stock reservation entries.
- `set_item_locations`: Assigns warehouse locations for picking.
- `create_delivery_note`: Creates a Delivery Note from a Pick List.
- `create_stock_entry`: Creates a Stock Entry from a Pick List.
- `get_item_details`: Fetches details for an item.

### `erpnext.stock.doctype.serial_and_batch_bundle.serial_and_batch_bundle`
- `set_warehouse`: Sets the warehouse for the bundle.
- `add_serial_batch`: Adds serial/batch numbers to the bundle.
- `download_blank_csv_template`: Downloads a CSV template for uploading serial/batch numbers.
- `upload_csv_file`: Uploads serial/batch numbers from a CSV file.
- `create_serial_nos`: Creates Serial No documents.
- `get_serial_batch_ledgers`: Fetches ledger entries for a serial/batch number.
- `add_serial_batch_ledgers`: Adds ledger entries for a serial/batch number.
- `update_serial_or_batch`: Updates the details of a serial/batch number.
- `get_auto_data`: Fetches data for auto-creating serial/batch numbers.

### Other Key Functions
- `erpnext.stock.get_item_details.get_item_details`: A central function to get all details for an item.
- `erpnext.stock.utils.scan_barcode`: Scans a barcode and returns the corresponding item/serial/batch details.
- `erpnext.stock.doctype.putaway_rule.putaway_rule.apply_putaway_rule`: Applies putaway rules to determine the target warehouse for incoming stock.
- `erpnext.stock.doctype.repost_item_valuation.repost_item_valuation.execute_repost_item_valuation`: The main function to execute the reposting of item valuations.