# Model Context Profile: Support

## 1. Module Overview

The **Support** module in ERPNext provides a comprehensive system for managing customer service interactions, service level agreements (SLAs), and product warranty claims. It is designed to function as a complete helpdesk solution, enabling businesses to track and resolve customer issues efficiently while monitoring service quality.

The module is architecturally divided into two primary workflows:
1.  **Issue Management:** A flexible, SLA-driven system for handling general support tickets, questions, and problems raised by customers.
2.  **Warranty and Maintenance:** A structured process for managing claims against product warranties and Annual Maintenance Contracts (AMCs).

## 2. Core Concepts

### Service Level Agreements (SLAs)

The SLA system is a generic, rules-based engine that can be applied to any DocType with a `status` field, though it is most prominently used with the `Issue` DocType. It allows for the definition of time-based targets for both first response and final resolution.

-   **Business-Aware Clock:** SLA calculations are not based on a simple 24/7 clock. The system intelligently factors in defined **working hours**, company **holiday lists**, and **pause conditions** (e.g., when an issue is "On Hold" awaiting a customer reply).
-   **Hierarchical Matching:** The correct SLA is applied to a document based on a clear hierarchy: a specific `Customer`, `Customer Group`, `Territory`, or a custom Python expression, with a final fallback to a default SLA for the DocType.
-   **Automated Field Injection:** When an SLA is created for a DocType for the first time, the framework automatically adds the necessary tracking fields (e.g., `response_by`, `sla_resolution_by`, `agreement_status`) to that DocType, making the engine highly extensible.

### Issue vs. Warranty Claim

-   **Issue:** Represents a single, trackable unit of work corresponding to a customer query or problem. It is the central document for the helpdesk functionality and is tightly integrated with the SLA engine. Issues are often created automatically from incoming emails.
-   **Warranty Claim:** Represents a customer's request for service under a product's warranty or AMC. It is linked to a specific `Serial No` and `Item` and follows a simpler, non-SLA-driven workflow that may result in a `Maintenance Visit`.

## 3. Key DocTypes

### Configuration DocTypes

-   **`Support Settings` (Single):** A global configuration document that contains a master switch (`track_service_level_agreement`) to enable or disable the entire SLA functionality. It also holds settings for the support portal and email integration.
-   **`Service Level Agreement`:** Defines the core SLA rules. It specifies the target DocType, working hours, holiday list, and a table of priorities with their corresponding response and resolution times. It also defines which statuses will pause the SLA clock and which will mark the SLA as fulfilled.
-   **`Issue Priority` & `Issue Type`:** Simple master data for categorizing and prioritizing issues.

### Transactional DocTypes

-   **`Issue`:** The central document for tracking a support ticket. It captures the customer, subject, description, status, and all SLA-related metrics. Its timeline view aggregates all communications, providing a complete history of the interaction.
-   **`Warranty Claim`:** The document for managing a warranty or AMC request. It links a `Customer` to a `Serial No` and captures the details of the complaint and its resolution.
-   **`Maintenance Visit`:** Represents a scheduled visit by a technician to a customer's location to perform maintenance or resolve a warranty claim.

## 4. Business Logic and Workflows

### Issue Management Workflow

1.  **Creation:** An `Issue` is created either manually by a support agent or automatically from an incoming email.
2.  **SLA Application:** On creation, the system runs the `get_active_service_level_agreement_for` function to find and apply the appropriate SLA. This calculates and sets the `response_by` and `sla_resolution_by` deadlines.
3.  **Interaction:** Support agents and customers communicate, with interactions logged in the `Issue` timeline. When a support agent sends the first reply, `first_responded_on` is logged, and the "First Response" part of the SLA is met.
4.  **Status Changes:** The `Issue` moves through statuses like `Open`, `Replied`, and `On Hold`. When the status is set to one of the defined "pause" states, the `total_hold_time` is updated, and the resolution deadline is pushed out accordingly.
5.  **Resolution:** When the `Issue` is `Resolved` or `Closed`, the `sla_resolution_date` is recorded, and the system determines if the SLA was "Fulfilled" or "Failed".

### Warranty Claim Workflow

1.  **Creation:** A `Warranty Claim` is created, linking a `Customer` to a `Serial No`. The system automatically fetches the warranty and AMC status and expiry dates from the `Serial No` record.
2.  **Processing:** The claim is reviewed, and its status is updated (e.g., to `Work In Progress`).
3.  **Service:** If required, a `Maintenance Visit` can be created directly from the `Warranty Claim` to schedule on-site service.
4.  **Closure:** Once the service is complete, the claim is marked as `Closed`, and the resolution details are recorded.

## 5. User Interface (UI) and User Experience (UX)

-   **Workspace:** The "Support" workspace provides a centralized dashboard for support agents to view key metrics and access lists of Issues, Warranty Claims, and SLAs.
-   **Timeline View:** The timeline in the `Issue` form is critical, providing a chronological history of all emails, comments, and status changes related to the ticket.
-   **Client-Side Logic:** JavaScript in `issue.js` and `service_level_agreement.js` provides a dynamic user experience, such as hiding or showing fields based on configuration and adding custom buttons for common actions like "Close Issue" or "Create Task".
-   **Web Forms:** A standard "Issues" web form allows customers to submit tickets directly through the customer portal.

## 6. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.support.doctype.issue.issue`
- `split_issue`: Splits an issue into a new one, moving subsequent communications to the new issue.
- `set_multiple_status`: A bulk action to update the status of multiple issues.
- `set_status`: Updates the status of a single issue.
- `make_task`: Creates a Task from an Issue.
- `make_issue_from_communication`: Creates an Issue from a Communication (email).

### `erpnext.support.doctype.service_level_agreement.service_level_agreement`
- `get_service_level_agreement_filters`: Gets the available SLA filters for a document type.
- `reset_service_level_agreement`: Resets the SLA timers for a document.
- `get_user_time`: Gets the current time in the user's timezone.
- `get_sla_doctypes`: Gets a list of all DocTypes that have active SLAs.

### `erpnext.support.doctype.warranty_claim.warranty_claim`
- `make_maintenance_visit`: Creates a Maintenance Visit from a Warranty Claim.