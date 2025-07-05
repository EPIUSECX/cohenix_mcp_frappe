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

## 3. Key DocTypes and Data Models

### a. `Lead`

-   **File Path**: [`erpnext/crm/doctype/lead/lead.py`](erpnext-develop/erpnext/crm/doctype/lead/lead.py)
-   **Inherits**: `SellingController`, `CRMNote`
-   **Purpose**: To capture and manage initial sales prospects.
-   **Key Fields**: `lead_name`, `email_id`, `company_name`, `status`, `lead_owner`.
-   **Logic**:
    -   Can be automatically created from incoming emails.
    -   Validates for unique email addresses to prevent duplicate leads.
    -   Can be converted into an `Opportunity` or a `Customer`.
    -   Automatically creates a `Contact` if the setting is enabled.

### b. `Opportunity`

-   **File Path**: [`erpnext/crm/doctype/opportunity/opportunity.py`](erpnext-develop/erpnext/crm/doctype/opportunity/opportunity.py)
-   **Inherits**: `TransactionBase`, `CRMNote`
-   **Purpose**: To track a qualified sales deal through the sales pipeline.
-   **Key Fields**: `opportunity_from` (Lead or Customer), `party_name`, `sales_stage`, `probability`, `opportunity_amount`.
-   **Child Tables**: `OpportunityItem`, `CompetitorDetail`.
-   **Logic**:
    -   Can be created from a `Lead`.
    -   Calculates the total opportunity value based on the items in the `items` table.
    -   Can be used to generate `Quotations`.
    -   The `status` is updated based on the progress of linked quotations (e.g., "Converted" if a quotation is ordered, "Lost" if a quotation is lost).

### c. `Campaign`

-   **File Path**: [`erpnext/crm/doctype/campaign/campaign.py`](erpnext-develop/erpnext/crm/doctype/campaign/campaign.py)
-   **Purpose**: To manage and track marketing campaigns.
-   **Key Fields**: `campaign_name`, `description`.
-   **Child Tables**: `CampaignEmailSchedule`.
-   **Logic**:
    -   On save, it creates or updates a corresponding `UTM Campaign` record. This is used to link leads and opportunities back to the marketing campaign that generated them.

### d. `Contract`

-   **File Path**: [`erpnext/crm/doctype/contract/contract.py`](erpnext-develop/erpnext/crm/doctype/contract/contract.py)
-   **Purpose**: To manage formal agreements with customers or suppliers.
-   **Key Fields**: `party_type`, `party_name`, `start_date`, `end_date`, `status`.
-   **Child Tables**: `ContractFulfilmentChecklist`.
-   **Logic**:
    -   The `status` (`Unsigned`, `Active`, `Inactive`) is automatically updated based on the current date relative to the contract's start and end dates.
    -   The `fulfilment_status` is updated based on the completion of items in the `fulfilment_terms` checklist.

## 4. Utility Functions

-   **File Path**: [`erpnext/crm/doctype/utils.py`](erpnext-develop/erpnext/crm/doctype/utils.py)
-   **Key Functions**:
    -   `get_last_interaction(contact, lead)`: Retrieves the last communication or issue related to a contact or lead, providing quick context for sales and support teams.
    -   `copy_comments`, `link_communications`, `link_open_events`: A set of functions to carry over historical data when a `Lead` is converted to an `Opportunity` or `Customer`, ensuring a continuous record of interactions.

## 5. Integrations

-   **Selling**: The CRM module is the starting point for the sales process. `Opportunity` and `Lead` are directly linked to `Quotation` and `Sales Order`.
-   **Communication**: The module leverages the core `Communication` DocType to link emails and other interactions to CRM documents.
-   **Support**: `Issues` can be linked to `Leads`, providing a complete view of a prospect's interactions with the company.

## 6. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.crm.doctype.lead.lead`
- `make_customer`: Converts a Lead into a Customer.
- `make_opportunity`: Converts a Lead into an Opportunity.
- `make_quotation`: Creates a Quotation from a Lead.
- `get_lead_details`: Fetches details for a specific Lead.
- `make_lead_from_communication`: Creates a Lead from a Communication (email).
- `add_lead_to_prospect`: Links a Lead to a Prospect.
- `create_prospect_and_contact`: Creates a Prospect and Contact from a Lead.

### `erpnext.crm.doctype.opportunity.opportunity`
- `declare_enquiry_lost`: Sets the opportunity status to 'Lost' and records the reasons.
- `get_item_details`: Fetches details for an item.
- `make_quotation`: Creates a Quotation from an Opportunity.
- `make_request_for_quotation`: Creates an RFQ from an Opportunity.
- `make_customer`: Converts an Opportunity into a Customer.
- `make_supplier_quotation`: Creates a Supplier Quotation from an Opportunity.
- `set_multiple_status`: A bulk action to update the status of multiple opportunities.
- `make_opportunity_from_communication`: Creates an Opportunity from a Communication (email).

### `erpnext.crm.doctype.prospect.prospect`
- `make_customer`: Converts a Prospect into a Customer.
- `make_opportunity`: Creates an Opportunity from a Prospect.
- `get_opportunities`: Fetches all opportunities linked to a Prospect.

### `erpnext.crm.doctype.contract_template.contract_template`
- `get_contract_template`: Fetches and renders a contract template with document data.

### `erpnext.crm.doctype.utils`
- `get_last_interaction`: Gets the last communication or issue for a contact or lead.

### `erpnext.crm.utils.CRMNote`
- `add_note`: Adds a note to a CRM document.
- `edit_note`: Edits an existing note.
- `delete_note`: Deletes a note.

### `erpnext.crm.frappe_crm_api`
- `create_custom_fields_for_frappe_crm`: Utility for Frappe CRM integration.
- `create_prospect_against_crm_deal`: Utility for Frappe CRM integration.
- `create_customer`: Utility for Frappe CRM integration.