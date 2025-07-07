# Model Context Profile: Telephony

## 1. Module Overview

The Telephony module in ERPNext integrates with telephony systems to enable features like click-to-call, call logging, and pop-ups for incoming calls, connecting communication channels directly with CRM and support workflows.

## 2. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development.

### 2.1. Server-Side (Python)

The core of the Telephony module is the `Call Log` DocType, which manages call records and real-time events.

#### `erpnext.telephony.doctype.call_log.call_log.CallLog`

-   **`before_insert()`**: This controller method is triggered before a new `Call Log` is created. It automatically searches for existing `Contacts` and `Leads` with a matching phone number and links them to the call record.

-   **`trigger_call_popup()`**: This is a crucial function for incoming calls. It identifies which employees are scheduled to receive call notifications (based on `Incoming Call Handling Schedule`) and uses `frappe.publish_realtime("show_call_popup", ...)` to push a real-time notification to the relevant users' browsers, triggering a pop-up.

-   **`on_update()`**: This method manages the lifecycle of a call. It detects when a call is missed or ended and publishes real-time events (`call_{self.id}_missed`, `call_{self.id}_ended`) that the client-side can subscribe to for UI updates.

-   **`add_call_summary_and_call_type(call_log, summary, call_type)`**: A `@frappe.whitelist()` function that allows a client-side script (like a call pop-up) to send back a call summary and a disposition (`Telephony Call Type`) to be saved against the `Call Log`.

-   **`link_existing_conversations(doc, state)`**: A powerful hook that is called when a new `Contact` is created. It scours all existing `Call Logs` and links any that match the new contact's phone number, ensuring a complete communication history.

-   **`get_linked_call_logs(doctype, docname)`**: This function is used to populate the timeline of documents like `Lead` and `Contact`, showing a complete history of all linked calls.

### 2.2. Client-Side (JavaScript)

#### `frappe.ui.form.on("Call Log", ...)` in `call_log.js`

-   **`refresh(frm)`**: The main UI controller for the `Call Log` form. It dynamically adds a "Callback" or "Call Again" button that, when clicked, invokes the global `frappe.phone_call.handler` to initiate an outbound call.

-   **`setup_recording_audio_control(frm)`**: This function checks if a `recording_url` exists for the call and, if so, renders an HTML `<audio>` control to allow the user to play back the call recording directly within the form.