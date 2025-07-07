# Model Context Profile: Support

## 1. Module Overview

The **Support** module in ERPNext provides a comprehensive system for managing customer service interactions, service level agreements (SLAs), and product warranty claims. It is designed to function as a complete helpdesk solution, enabling businesses to track and resolve customer issues efficiently while monitoring service quality.

The module is architecturally divided into two primary workflows:
1.  **Issue Management:** A flexible, SLA-driven system for handling general support tickets, questions, and problems raised by customers.
2.  **Warranty and Maintenance:** A structured process for managing claims against product warranties and Annual Maintenance Contracts (AMCs).

## 2. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development.

### 2.1. Server-Side (Python)

#### `erpnext.support.doctype.issue.issue.Issue`

-   **`split_issue(subject, communication_id)`**: A whitelisted function that creates a new `Issue` from an existing one. It moves the specified communication and all subsequent communications to the new issue, which is useful for splitting a long conversation into separate, manageable tickets.
-   **`make_task(source_name, ...)`**: A whitelisted function that creates a `Task` from an `Issue`, linking the two documents. This allows for escalating a support issue into a trackable task for another department.
-   **`make_issue_from_communication(communication, ...)`**: A whitelisted function that creates a new `Issue` directly from a `Communication` document (typically an email), automatically linking the communication and populating the issue with the email's subject and sender.
-   **`set_first_response_time(communication, method)`**: This is a hook method called from the `Communication` DocType. It calculates the actual time taken for the first response to an issue based on the defined SLA working hours and holidays, and updates the `first_response_time` field on the `Issue`.

#### `erpnext.support.doctype.warranty_claim.warranty_claim`

-   **`make_maintenance_visit(source_name, ...)`**: A whitelisted function that creates a `Maintenance Visit` from a `Warranty Claim`. This is the primary function for converting a claim into a scheduled service appointment.

### 2.2. Client-Side (JavaScript)

#### `frappe.ui.form.on("Issue", ...)` in `issue.js`

-   **`refresh(frm)`**: This is the main UI controller for the Issue form. It dynamically adds buttons like "Close"/"Reopen" and "Create Task" based on the issue's status.
-   **`timeline_refresh(frm)`**: This event handler dynamically injects a "Split Issue" button into the communication timeline view. This provides a context-sensitive UI for users to split a conversation into a new issue directly from a specific email reply.
-   **`reset_service_level_agreement(frm)`**: This function displays a dialog to capture a reason and then calls the server-side method to reset the SLA timers for the current issue.

#### `frappe.ui.form.on("Warranty Claim", ...)` in `warranty_claim.js`

-   **`refresh(frm)`**: This method controls the UI for the Warranty Claim form. It adds the "Maintenance Visit" button if the claim is open, providing the primary call to action for the user.

## 3. Business Logic and Workflows

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