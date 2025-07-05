# MCP: Automation Module

## Module Overview

The **Automation** module in Frappe provides tools and features to automate various business processes and workflows. This includes automatically assigning documents to users, creating documents on a recurring schedule, tracking progress against milestones, and setting up reminders.

This module helps in reducing manual intervention and ensuring that tasks are handled in a timely and efficient manner.

## File Index

*   `frappe/automation/__init__.py`
*   `frappe/automation/doctype/assignment_rule/assignment_rule.py`
*   `frappe/automation/doctype/auto_repeat/auto_repeat.py`
*   `frappe/automation/doctype/milestone_tracker/milestone_tracker.py`
*   `frappe/automation/doctype/reminder/reminder.py`
*   ... and so on for all files in the `automation` module.

## Public API / Callable Functions

### `frappe.automation.doctype.assignment_rule.assignment_rule.apply(doc, method=None)`
- **Description:** Applies all matching assignment rules to a document. This is the main entry point for the assignment rule logic and is typically called from a DocType's `on_update` hook.
- **Arguments:**
    - `doc` (Document): The document to which the assignment rules should be applied.
    - `method` (string, optional): The event that triggered the assignment (e.g., "on_update").
- **Returns:** None.

### `frappe.automation.doctype.auto_repeat.auto_repeat.make_auto_repeat(doctype, docname, frequency, start_date, end_date)`
- **Description:** Creates an `Auto Repeat` document for a given document.
- **Arguments:**
    - `doctype` (string): The DocType of the document to be repeated.
    - `docname` (string): The name of the document to be repeated.
    - `frequency` (string): The frequency of repetition ("Daily", "Weekly", "Monthly", etc.).
    - `start_date` (string): The start date for the auto-repeat schedule.
    - `end_date` (string, optional): The end date for the auto-repeat schedule.
- **Returns:** The newly created `Auto Repeat` document.

### `frappe.automation.doctype.reminder.create_new_reminder(remind_at, description, reminder_doctype, reminder_docname)`
- **Description:** Creates a new reminder for the current user.
- **Arguments:**
    - `remind_at` (string): The date and time for the reminder.
    - `description` (string): The description of the reminder.
    - `reminder_doctype` (string, optional): The DocType to which the reminder is linked.
    - `reminder_docname` (string, optional): The name of the document to which the reminder is linked.
- **Returns:** The newly created `Reminder` document.

## Detailed Walkthrough

### `frappe/automation/doctype/assignment_rule/assignment_rule.py`

This file defines the `AssignmentRule` DocType, which is used to automatically assign documents to users based on certain conditions.

#### Class: `AssignmentRule(Document)`

This class represents an assignment rule. It allows you to define conditions under which a document should be assigned to a user or a group of users.

**Key Methods:**

*   **`apply_assign(doc)`**: Checks if the `assign_condition` is met and, if so, calls `do_assignment`.
*   **`do_assignment(doc)`**: Assigns the document to a user based on the assignment rule ("Round Robin", "Load Balancing", or "Based on Field").
*   **`apply_unassign(doc, assignments)`**: Checks if the `unassign_condition` is met and, if so, clears the assignment.
*   **`get_user(doc)`**: Returns the user to whom the document should be assigned.

**Key Properties (Fields):**

*   **`document_type`**: The DocType to which this assignment rule applies.
*   **`assign_condition`**: A Python expression that determines when the document should be assigned.
*   **`unassign_condition`**: A Python expression that determines when the document should be unassigned.
*   **`rule`**: The assignment rule to use ("Round Robin", "Load Balancing", "Based on Field").
*   **`users`**: A child table of users to whom the document can be assigned.

### `frappe/automation/doctype/auto_repeat/auto_repeat.py`

This file defines the `AutoRepeat` DocType, which is used to create documents on a recurring schedule.

#### Class: `AutoRepeat(Document)`

This class represents an auto-repeat schedule. It allows you to specify a reference document, a frequency, and a start and end date for the schedule.

**Key Methods:**

*   **`create_documents()`**: Creates a new document based on the reference document and the schedule.
*   **`make_new_document()`**: Creates a copy of the reference document and updates it with the new schedule information.
*   **`get_next_schedule_date(schedule_date, ...)`**: Calculates the next date on which a document should be created.

**Key Properties (Fields):**

*   **`reference_doctype`**: The DocType of the document to be repeated.
*   **`reference_document`**: A link to the document to be repeated.
*   **`frequency`**: The frequency of repetition ("Daily", "Weekly", "Monthly", etc.).
*   **`start_date`**, **`end_date`**: The start and end dates for the auto-repeat schedule.
*   **`submit_on_creation`**: If checked, the new document will be submitted automatically upon creation.

### `frappe/automation/doctype/milestone_tracker/milestone_tracker.py`

This file defines the `MilestoneTracker` DocType, which is used to track changes to a specific field in a document.

#### Class: `MilestoneTracker(Document)`

This class represents a milestone tracker. Each time the tracked field is changed, a new `Milestone` document is created to record the change.

**Key Methods:**

*   **`apply(doc)`**: This method is called when a document of the tracked DocType is updated. It checks if the tracked field has changed and, if so, creates a new `Milestone` document.

**Key Functions (outside the class):**

*   **`evaluate_milestone(doc, event)`**: This function is called from a DocType's `on_update` hook. It gets all the milestone trackers for the document's DocType and calls their `apply` method.

**Key Properties (Fields):**

*   **`document_type`**: The DocType to be tracked.
*   **`track_field`**: The field to be tracked for changes.

### `frappe/automation/doctype/reminder/reminder.py`

This file defines the `Reminder` DocType, which allows users to set reminders for themselves.

#### Class: `Reminder(Document)`

This class represents a reminder. It includes a description, a date and time for the reminder, and an optional link to a document.

**Key Methods:**

*   **`send_reminder()`**: This method is called by the scheduler when the reminder is due. It creates a system notification for the user.

**Key Functions (outside the class):**

*   **`send_reminders()`**: This function is called by the scheduler to send all pending reminders.

**Key Properties (Fields):**

*   **`user`**: The user for whom the reminder is set.
*   **`remind_at`**: The date and time for the reminder.
*   **`description`**: The description of the reminder.
*   **`reminder_doctype`**, **`reminder_docname`**: An optional link to a document.