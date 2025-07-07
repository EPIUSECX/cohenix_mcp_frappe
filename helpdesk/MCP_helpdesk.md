---

### **Module: `Helpdesk`**

**1. High-Level Summary:**

*   **Purpose:** The Helpdesk module is a comprehensive ticketing system designed to manage customer support and internal service requests. It provides a structured way to track issues, assign them to agents, enforce service level agreements (SLAs), and manage communication with customers.
*   **Key Features:**
    *   Ticket Management (Create, Update, Close)
    *   Agent and Team Management
    *   Service Level Agreements (SLAs)
    *   Ticket Escalation Rules
    *   Customer and Contact Management
    *   Knowledge Base (Articles)
    *   Email-to-Ticket Conversion

**2. Core Components (DocTypes):**

*   **DocType: `HD Ticket`**
    *   **Type:** Document
    *   **Purpose:** This is the central document of the Helpdesk module, representing a single support request or issue. It tracks the entire lifecycle of a ticket, from its creation and assignment to its resolution and feedback.
    *   **Key Fields:**
| Field Name | Type | Description |
| :--- | :--- | :--- |
| `subject` | Data | The main subject or title of the ticket. |
| `status` | Select | The current status of the ticket (e.g., Open, Replied, Resolved, Closed). |
| `priority` | Link | The priority level of the ticket (e.g., Low, Medium, High). |
| `agent_group` | Link | The team of agents responsible for handling the ticket. |
| `customer` | Link | The customer who raised the ticket. |
| `contact` | Link | The specific contact person for the ticket. |
| `sla` | Link | The Service Level Agreement applied to the ticket. |

    *   **Backend Logic (`hd_ticket.py`):**
        *   **Controller Class Methods:**
            *   `before_validate`: Sets default values for ticket type and priority, identifies the contact and customer from the `raised_by` email, and applies any matching SLA.
            *   `on_update`: Publishes real-time updates for the ticket, updates the search index, and handles agent assignment changes.
            *   `on_communication_update`: A special hook called from the `Communication` DocType. It automatically re-opens a ticket if a customer replies and sets the status to "Replied" when an agent sends a message.
            *   `assign_agent`: A whitelisted method to assign a ticket to a specific agent.
            *   `reply_via_agent`: A whitelisted method that handles sending email replies to customers, creating `Communication` records, and managing email threading.
        *   **Standard Hooks:**
            *   The DocType has extensive logic in `before_validate` and `on_update` to automate various aspects of the ticket management process.
        *   **Whitelisted API Methods (`@frappe.whitelist()`):**
            *   `assign_agent`: Allows for programmatic assignment of agents to tickets.
            *   `reply_via_agent`: Provides an API for sending replies to tickets.
            *   `new_comment`: Allows agents to add internal comments to a ticket.
    *   **Frontend Logic (`hd_ticket.js`):**
        *   The `hd_ticket.js` file is currently empty. All frontend interactions are handled by the standard Frappe Desk form and list views.
    *   **Workflow:** The ticket's lifecycle is primarily managed by the `status` field. The system also supports automated escalations through the `HD Escalation Rule` DocType, which can change the ticket's team, priority, or assigned agent based on predefined conditions.

---
*   **DocType: `HD Service Level Agreement`**
    *   **Type:** Document
    *   **Purpose:** This DocType is used to define and enforce service level agreements for tickets. It allows for setting response and resolution time targets based on ticket priority, and can be configured to apply only to tickets that meet certain conditions.
    *   **Key Fields:**
| Field Name | Type | Description |
| :--- | :--- | :--- |
| `service_level` | Data | The name of the SLA. |
| `enabled` | Check | Determines if the SLA is active. |
| `default_sla` | Check | If checked, this SLA will be applied to all tickets that do not match any other SLA. |
| `condition` | Code | A Python expression that determines if the SLA should be applied to a ticket. |
| `priorities` | Table | A child table that defines the response and resolution times for each ticket priority. |
| `support_and_resolution` | Table | A child table that defines the working hours and days for the support team. |

    *   **Backend Logic (`hd_service_level_agreement.py`):**
        *   **Controller Class Methods:**
            *   `validate`: Performs extensive validation to ensure that the SLA is configured correctly. It checks for unique priorities, valid working hours, and that there is only one default SLA.
            *   `apply`: This is the core method that applies the SLA to a ticket. It calculates the `response_by` and `resolution_by` dates based on the ticket's creation time, priority, and the working hours defined in the SLA.
            *   `calc_time`: A utility method that calculates the target date and time for a response or resolution, taking into account working hours and holidays.
            *   `calc_elapsed_time`: Calculates the actual time elapsed between two dates, excluding non-working hours and holidays.
        *   **Standard Hooks:**
            *   The `before_save` hook is used to set the default priority for the SLA.
    *   **Frontend Logic (`hd_service_level_agreement.js`):**
        *   **Client Scripts (`frm.cscript`):**
            *   `refresh`: Toggles the visibility of the resolution time fields in the priorities table based on the `apply_sla_for_resolution` checkbox.
            *   `apply_sla_for_resolution`: An `onchange` handler that dynamically updates the grid view for the priorities table.
    *   **Workflow:** There is no explicit workflow, but the `enabled` field controls whether the SLA is active. The system automatically applies the first matching SLA to a ticket based on the conditions defined.

---
**3. Reports & Pages:**

*   **Component: `Ticket Analytics`**
    *   **Type:** Report
    *   **Purpose:** This report provides a time-series analysis of ticket data, allowing users to see trends in ticket creation over various periods (weekly, monthly, quarterly). It can be grouped by different criteria like Contact, Ticket Type, Priority, or Assigned Agent, making it a powerful tool for understanding support workload and identifying patterns.
    *   **Data Source:** This is a Script Report that fetches data from the `HD Ticket` DocType.
    *   **Backend Logic (`ticket_analytics.py`):**
        *   The `execute` function is the main entry point. It first determines the date ranges for the report based on the selected period (weekly, monthly, etc.).
        *   It then fetches all `HD Ticket` records that fall within the specified date range and match the other filter criteria.
        *   The script processes this data, grouping the tickets by the selected "Based On" criteria and by the calculated time periods.
        *   It dynamically generates the report columns based on the time periods.
        *   Finally, it constructs the data for the line chart, which visualizes the ticket trends over time.
    *   **Frontend Logic (`ticket_analytics.js`):**
        *   This file defines the filters for the report, including "Based On", "From Date", "To Date", "Range", "Status", "Priority", "Contact", and "Assigned To".
        *   It includes a `get_datatable_options` function that adds a checkbox column to the report and an `onCheckRow` event. This allows users to selectively show or hide different data series on the line chart, providing an interactive way to analyze the data.

---
**4. Module-Level Logic & APIs:**

*   **Public API (`api.py` or whitelisted methods):** The `helpdesk` module does not have a dedicated top-level `api.py` file. Public methods are exposed as whitelisted functions within the DocType controllers (e.g., `assign_agent` in `HD Ticket`).
*   **Scheduled Jobs (`hooks.py`):**
    *   **`daily`**: `helpdesk.helpdesk.doctype.hd_ticket.hd_ticket.close_tickets_after_n_days` - This job automatically closes tickets that have been in a "Replied" state for a configurable number of days.
*   **Other Hooks (`hooks.py`):**
    *   **`doc_events`**: The module hooks into the `before_insert` event of the `Contact` DocType to perform custom actions. It also hooks into the `on_trash` event of `Assignment Rule`.
    *   **`has_permission`**: A custom permission query function (`helpdesk.helpdesk.doctype.hd_ticket.hd_ticket.has_permission`) is defined for the `HD Ticket` DocType. This allows for more granular access control than the standard permission system, enabling customers to see their own tickets.
    *   **`override_doctype_class`**: The module overrides the standard `Contact` DocType with a custom class (`CustomContact`) to inject specialized helpdesk logic.

**5. Inter-Module Dependencies & Extensibility:**

*   **Consumes (Dependencies):**
    *   **Frappe Core:** The Helpdesk application is built on the Frappe framework and relies on its core features, such as the DocType system, permission management, and scheduled jobs.
    *   **Email Module:** The system is tightly integrated with the Email module for creating tickets from incoming emails and sending replies.
*   **Exposes (API Surface for Extension):**
    *   The primary way to interact with the `helpdesk` module is through its DocTypes. Creating an `HD Ticket` is the main entry point for the system.
    *   The whitelisted methods within the `HD Ticket` controller (e.g., `assign_agent`, `reply_via_agent`) provide a direct API for building custom integrations.
    *   The `doc_events` for `Contact` and `Assignment Rule` provide extension points for custom apps to hook into.

**6. File Manifest:**

*   `helpdesk-develop/helpdesk/helpdesk/doctype/hd_ticket/hd_ticket.json`
*   `helpdesk-develop/helpdesk/helpdesk/doctype/hd_ticket/hd_ticket.py`
*   `helpdesk-develop/helpdesk/helpdesk/doctype/hd_ticket/hd_ticket.js`
*   `helpdesk-develop/helpdesk/helpdesk/doctype/hd_service_level_agreement/hd_service_level_agreement.json`
*   `helpdesk-develop/helpdesk/helpdesk/doctype/hd_service_level_agreement/hd_service_level_agreement.py`
*   `helpdesk-develop/helpdesk/helpdesk/doctype/hd_service_level_agreement/hd_service_level_agreement.js`
*   `helpdesk-develop/helpdesk/helpdesk/report/ticket_analytics/ticket_analytics.json`
*   `helpdesk-develop/helpdesk/helpdesk/report/ticket_analytics/ticket_analytics.py`
*   `helpdesk-develop/helpdesk/helpdesk/report/ticket_analytics/ticket_analytics.js`
*   `helpdesk-develop/helpdesk/hooks.py`

---