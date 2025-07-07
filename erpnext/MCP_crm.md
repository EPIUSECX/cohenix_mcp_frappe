# Model Context Profile: CRM

## 1. Module Overview

The **Customer Relationship Management (CRM)** module in ERPNext provides a comprehensive suite of tools to manage the entire customer lifecycle, from initial lead generation to long-term contract management. It is designed to streamline sales processes, track marketing effectiveness, and maintain strong customer relationships.

The module is tightly integrated with other core ERPNext modules, particularly `Selling` and `Accounts`, to ensure a seamless transition from a sales opportunity to a financial transaction.

## 2. Core Concepts

### a. Sales Funnel Management

The CRM module is built around a standard sales funnel, represented by a series of interconnected DocTypes:

1.  **`Lead`**: The entry point for any potential sales prospect. A lead can be created manually, from an email, or through a web form. It captures basic contact and company information.
2.  **`Opportunity`**: A qualified lead that has been identified as a potential sales deal. An opportunity tracks the sales stage, probability of winning, and the potential value of the deal. It can be created directly from a `Lead`.
3.  **`Quotation`**: A formal offer sent to a customer for goods or services. It can be generated from an `Opportunity` and contains detailed item pricing.
4.  **`Sales Order`**: A confirmed order from a customer, which can be created from a `Quotation`. This marks the conversion of an opportunity into an actual sale.

### b. Marketing and Campaign Management

The `Campaign` DocType allows for the creation and management of marketing campaigns. It integrates with the `UTM Campaign` DocType to track the source of leads and opportunities, providing insights into the effectiveness of different marketing channels.

### c. Contract Management

The `Contract` DocType is used to manage long-term agreements with customers or suppliers. It defines the terms, duration, and fulfilment obligations of a contract. It has its own status lifecycle (`Unsigned`, `Active`, `Inactive`) and can include a checklist to ensure all contractual terms are met.

### d. Communication and Interaction Tracking

The CRM module enhances the core `Communication` DocType by allowing incoming emails to be directly converted into `Leads` or `Opportunities`. This ensures that all customer interactions are captured and linked to the relevant sales documents, providing a complete history of the relationship.

## 3. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development.

### 3.1. Server-Side (Python)

#### `erpnext.crm.doctype.lead.lead`

-   **`make_customer(source_name, ...)`**: A whitelisted function that converts a `Lead` into a `Customer`. It maps fields like name, company, and contact details, and also links the default address and contact.
-   **`make_opportunity(source_name, ...)`**: A whitelisted function that converts a `Lead` into an `Opportunity`. It carries over relevant details and also links open tasks, events, and communications if configured in CRM Settings.
-   **`make_quotation(source_name, ...)`**: A whitelisted function that creates a `Quotation` directly from a `Lead`, setting the `quotation_to` field to 'Lead'.
-   **`create_contact()`**: An internal method that creates a `Contact` document from the lead's details. This is called automatically on lead creation if enabled in CRM Settings.

#### `erpnext.crm.doctype.opportunity.opportunity`

-   **`make_quotation(source_name, ...)`**: A whitelisted function that creates a `Quotation` from an `Opportunity`. It maps the items from the opportunity to the quotation.
-   **`make_customer(source_name, ...)`**: A whitelisted function that creates a `Customer` from an `Opportunity`, linking back to the original opportunity and lead.
-   **`declare_enquiry_lost(...)`**: A whitelisted function that sets the opportunity's status to 'Lost' and records the reasons and competing competitors. This is typically called from the UI.
-   **`after_insert()`**: This instance method is triggered when an opportunity is created from a lead. It automatically updates the lead's status and links related open documents like tasks and events, ensuring a continuous history.

### 3.2. Client-Side (JavaScript)

#### `erpnext.LeadController`

-   **`refresh()`**: This is the main UI controller for the Lead form. It dynamically adds the "Create" buttons ("Customer", "Opportunity", "Quotation") if the lead has not yet been converted.
-   **`make_customer()` / `make_opportunity()` / `make_quotation()`**: These methods are wrappers around `frappe.model.open_mapped_doc`. They call the corresponding server-side `make_*` functions and handle the routing to the newly created document, providing a seamless user experience for converting a lead.
-   **`make_prospect()`**: This client-side function allows a user to create a `Prospect` directly from a lead, pre-filling the prospect's details from the lead document.

#### `erpnext.crm.Opportunity` (Controller)

-   **`refresh()`**: This method controls the UI for the Opportunity form. It adds the "Create" buttons ("Quotation", "Customer") and also a "Set as Lost" button, which triggers the `set_as_lost_dialog`.
-   **`create_quotation()`**: This function calls the server-side `make_quotation` method via `frappe.model.open_mapped_doc` to generate a quotation from the opportunity.
-   **`status()`**: This event handler listens for changes to the `status` field. If the status is changed to "Lost", it automatically triggers the `set_as_lost_dialog` to capture the reasons.

## 4. Utility Functions

-   **File Path**: [`erpnext/crm/doctype/utils.py`](erpnext-develop/erpnext/crm/doctype/utils.py)
-   **Key Functions**:
    -   `get_last_interaction(contact, lead)`: Retrieves the last communication or issue related to a contact or lead, providing quick context for sales and support teams.
    -   `copy_comments`, `link_communications`, `link_open_events`: A set of functions to carry over historical data when a `Lead` is converted to an `Opportunity` or `Customer`, ensuring a continuous record of interactions.

## 5. Integrations

-   **Selling**: The CRM module is the starting point for the sales process. `Opportunity` and `Lead` are directly linked to `Quotation` and `Sales Order`.
-   **Communication**: The module leverages the core `Communication` DocType to link emails and other interactions to CRM documents.
-   **Support**: `Issues` can be linked to `Leads`, providing a complete view of a prospect's interactions with the company.