# Model Context Profile: Telephony

## 1. Module Overview

The **Telephony** module in ERPNext integrates with third-party voice-over-IP (VoIP) providers (e.g., Twilio, Exotel) to enable and manage voice calls directly within the ERP system. It provides a framework for logging all incoming and outgoing calls, routing them to the appropriate agents based on predefined schedules, and displaying real-time call notifications to users.

The module's architecture is designed to provide immediate context for customer interactions by automatically linking calls to existing `Contact` and `Lead` records.

## 2. Core Concepts

### External Integration

The module acts as a backend for an external telephony service. It does not handle the voice data itself but rather receives API calls from the provider to log call metadata. The `Call Log` DocType is created and updated by these external API calls, using the provider's unique call ID as the primary key.

### Time-Based Routing

The core of the incoming call logic is a weekly schedule that determines which group of employees should receive calls at any given time. This allows businesses to manage support shifts and after-hours call handling effectively.

-   **Agent Groups:** Calls are routed to an `Employee Group`, not individual users. This provides flexibility in managing support teams.
-   **Routing Methods:** The system supports two standard call distribution strategies:
    -   **`Sequential`:** Rings agents one after another.
    -   **`Simultaneous`:** Rings all agents in the group at once.

### Real-Time User Experience

The module leverages Frappe's real-time messaging system (`frappe.publish_realtime`) to create a dynamic user experience. When a new incoming call is logged, a `show_call_popup` event is published to all scheduled users for that time slot. This triggers an on-screen notification, allowing agents to see who is calling and answer the call without leaving the ERPNext interface.

## 3. Key DocTypes

### Configuration DocTypes

-   **`Incoming Call Settings`:** The central document for defining the incoming call workflow. It contains the weekly schedule that maps days and times to specific `Employee Group`s and sets the overall `call_routing` method.
-   **`Incoming Call Handling Schedule` (Child Table):** A child table within `Incoming Call Settings` that defines the specific time slots (`from_time`, `to_time`) and the assigned `agent_group` for each `day_of_week`.
-   **`Voice Call Settings`:** A user-specific document that allows each agent to configure their personal telephony preferences, such as their `call_receiving_device` (`Computer` or `Phone`) and custom audio messages for greetings or when they are busy.
-   **`Telephony Call Type`:** A simple master for categorizing calls (e.g., "Sales Inquiry," "Support Request").

### Transactional DocType

-   **`Call Log`:** The core transactional document that records every voice call. It captures essential metadata, including the `from` and `to` numbers, `start_time`, `end_time`, `duration`, `status` (Ringing, Completed, etc.), and a link to the call `recording_url`.

## 4. Business Logic and Workflows

### Incoming Call Workflow

1.  **External Trigger:** A customer places a call to a number managed by the integrated telephony provider.
2.  **API Call to ERPNext:** The provider makes an API call to the ERPNext instance, creating a new `Call Log` document with the initial status "Ringing".
3.  **Contact/Lead Linking:** The `Call Log`'s `before_insert` method immediately searches for a `Contact` or `Lead` with a matching phone number. If found, a dynamic link is added to the log, providing instant context.
4.  **Routing and Pop-up:**
    a. The system consults the `Incoming Call Settings` to find the active `Employee Group` for the current time.
    b. The `trigger_call_popup` function is called, which publishes a real-time event to all users in that group.
    c. The telephony provider, guided by the `call_routing` setting, begins ringing the agents' devices.
5.  **Call Lifecycle:** As the call progresses, the provider sends further API updates to change the `Call Log` status (e.g., to "In Progress," "Completed," "No Answer").
6.  **Agent Interaction:** The agent who answers the call can add a `summary` and `type_of_call` to the `Call Log` after the conversation.

### Outgoing Call Workflow

1.  **User Trigger:** A user initiates a call from within ERPNext (e.g., by clicking a phone number on a `Contact` form).
2.  **API Call to Provider:** The system makes an API call to the telephony provider to initiate the outbound call.
3.  **Logging:** A `Call Log` is created with the type "Outgoing" to track the call.

## 5. User Interface (UI) and User Experience (UX)

-   **Call Pop-ups:** The most significant UI feature is the real-time call notification that appears for scheduled agents, providing immediate information about the caller.
-   **Embedded Audio Player:** The `Call Log` form includes an embedded HTML5 audio player that allows users to listen to call recordings directly from the `recording_url`.
-   **Timeline Integration:** The `get_linked_call_logs` function ensures that all calls associated with a `Contact` or `Lead` appear in their respective document timelines, providing a complete history of voice interactions.
-   **Callback Buttons:** The `Call Log` form includes a "Callback" or "Call Again" button, making it easy for users to re-initiate a call with a single click.

## 6. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.telephony.doctype.call_log.call_log`
- `add_call_summary_and_call_type`: Allows a user to add a summary and classify a call after it has been completed.