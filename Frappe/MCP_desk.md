# MCP: Desk Module

## Module Overview

The **Desk** module is the primary user interface for the Frappe Framework. It provides the workspace, forms, lists, reports, and other UI elements that users interact with to manage data and perform tasks. The Desk is a single-page application (SPA) that is highly configurable and extensible.

This module is responsible for:
*   Rendering the main desk page with its configurable workspaces.
*   Loading and saving documents through the form view.
*   Displaying lists of documents with filtering, sorting, and searching capabilities.
*   Rendering reports and charts.
*   Handling user notifications and events.

## File Index

*   `frappe/desk/__init__.py`
*   `frappe/desk/calendar.py`
*   `frappe/desk/desk_page.py`
*   `frappe/desk/desktop.py`
*   `frappe/desk/doctype/bulk_update/bulk_update.js`
*   ... and so on for all files in the `desk` module.

## Public API / Callable Functions

### `frappe.desk.desktop.get_desktop_page(page)`
- **Description:** Applies permissions and customizations and returns the configuration for a page on the desk.
- **Arguments:**
    - `page` (JSON string): Page data.
- **Returns:** `dict` containing cards, charts, shortcuts, etc. to be displayed on the workspace.

### `frappe.desk.form.load.getdoc(doctype, name)`
- **Description:** Loads a doclist for a given document. This is called directly from the client-side form view.
- **Arguments:**
    - `doctype` (string): The DocType of the document to load.
    - `name` (string): The name (ID) of the document to load.
- **Returns:** A list containing the document's data.

### `frappe.desk.form.save.savedocs(doc, action)`
- **Description:** Saves, submits, or updates a document.
- **Arguments:**
    - `doc` (JSON string): The document data.
    - `action` (string): The action to perform ("Save", "Submit", "Update", "Cancel").
- **Returns:** None. The updated document is sent back in the response.

### `frappe.desk.listview.get_list_settings(doctype)`
- **Description:** Gets the user's list view settings for a given DocType.
- **Returns:** A `List View Settings` document.

### `frappe.desk.reportview.get()`
- **Description:** The main endpoint for fetching data for list and report views. It parses the request arguments and calls the appropriate execution method.
- **Returns:** A dictionary containing the keys and values of the report data.

## Detailed Walkthrough

### `frappe/desk/desktop.py`

This file is responsible for building the main Desk page, which is composed of workspaces. It fetches the configuration for a given workspace and builds the cards, charts, shortcuts, and other widgets based on the user's permissions.

#### Class: `Workspace`
This class represents a single workspace page. It's responsible for fetching all the components of a workspace and checking the user's permissions for each item.

**Key Methods:**
*   **`is_permitted()`**: Checks if the current user has permission to view the workspace.
*   **`build_workspace()`**: Fetches and prepares all the components of the workspace (links, charts, shortcuts, etc.).
*   **`get_links()`**: Fetches the link cards for the workspace, filtering out any links the user is not permitted to see.
*   **`get_charts()`**: Fetches the chart widgets.
*   **`get_shortcuts()`**: Fetches the shortcut widgets.

### `frappe/desk/form/load.py`

This file handles the loading of documents into the form view.

**Key Functions:**
*   **`getdoc(doctype, name)`**: The main function for loading a document. It gets the document from the database, checks permissions, runs the `onload` method, and gathers additional information like comments, attachments, and versions.
*   **`get_docinfo(doc=None, doctype=None, name=None)`**: Gathers all the auxiliary information for a document, such as comments, attachments, shares, versions, and assignments.
*   **`set_link_titles(doc)`**: Fetches the `title` field for all `Link` fields in the document to display in the UI.

### `frappe/desk/form/save.py`

This file handles the saving, submitting, and canceling of documents from the form view.

**Key Functions:**
*   **`savedocs(doc, action)`**: The main entry point for saving a document. It sets the `docstatus` based on the action and calls the appropriate document method (`save()`, `submit()`, or `cancel()`).
*   **`cancel(doctype=None, name=None, ...)`**: Cancels a submitted document.
*   **`discard(doctype, name)`**: Discards a draft document.

### `frappe/desk/listview.py`

This file provides backend functionality for the list view, such as getting list settings and fetching data for the "group by" feature.

**Key Functions:**
*   **`get_list_settings(doctype)`**: Retrieves the saved list view settings for a user and DocType.
*   **`set_list_settings(doctype, values)`**: Saves the user's list view settings.
*   **`get_group_by_count(doctype, current_filters, field)`**: Fetches the count of documents grouped by a specific field, used for the sidebar in the list view.

### `frappe/desk/reportview.py`

This file is the backend for the list and report views. It's responsible for building and executing the database queries to fetch the data displayed in these views.

**Key Functions:**
*   **`get()`**: The main endpoint that is called from the client-side to fetch data. It parses the request parameters, validates them, and then executes the query.
*   **`execute(doctype, *args, **kwargs)`**: A wrapper for `frappe.model.db_query.DatabaseQuery`, which is the main class for building and executing list/report queries.
*   **`validate_args(data)`**: Validates the query parameters, ensuring that the user has permission to access the requested fields and that the filters are valid.
*   **`compress(data, args=None)`**: Compresses the query results into a format that is more efficient to send to the client (separating keys and values).
### `frappe/desk/doctype/workspace/workspace.py`

This file defines the `Workspace` DocType, which is the data model for the configurable workspaces on the Desk.

#### Class: `Workspace(Document)`

This class represents a Workspace document. Each workspace is a container for various UI elements like link cards, charts, shortcuts, and custom blocks.

**Key Methods:**

*   **`validate()`**: Ensures that the workspace `title` does not conflict with existing routes and that the `content` field contains a valid JSON list.
*   **`on_update()`**: If the workspace is public and in developer mode, it exports the workspace definition to a `.json` file in its module's directory.
*   **`get_link_groups()`**: Processes the `links` child table to group links into cards.
*   **`build_links_table_from_card(config)`**: Reconstructs the `links` child table from a configuration of cards, which is used when customizing workspaces from the UI.

**Key Properties (Fields):**

*   **`title`**: The display title of the workspace.
*   **`public`**: If checked, the workspace is public and can be seen by users who have the required roles. If unchecked, it's a private workspace for a specific user.
*   **`for_user`**: If the workspace is private, this field specifies the user it belongs to.
*   **`content`**: A JSON field that stores the layout of the workspace, including the arrangement of widgets.
*   **`links`**: A child table (`Workspace Link`) that defines the links within the workspace's cards.
*   **`charts`**: A child table (`Workspace Chart`) for dashboard charts.
*   **`shortcuts`**: A child table (`Workspace Shortcut`) for shortcut icons.
*   **`custom_blocks`**: A child table (`Workspace Custom Block`) for custom HTML blocks.

### `frappe/desk/doctype/dashboard_chart/dashboard_chart.py`

This file defines the `DashboardChart` DocType, which is used to create charts that can be displayed on dashboards and workspaces.

#### Class: `DashboardChart(Document)`

This class represents a chart. It can be of various types (Count, Sum, Average, Group By) and can be based on a DocType or a Report.

**Key Functions (outside the class):**

*   **`get(chart_name, ...)`**: The main function for fetching the data for a chart. It takes the chart name and various filters as arguments and returns the chart configuration (labels and datasets).
*   **`create_dashboard_chart(args)`**: A whitelisted method to create a new `Dashboard Chart` document.
*   **`get_chart_config(...)`**: Generates the chart data for time-series charts.
*   **`get_group_by_chart_config(...)`**: Generates the chart data for "Group By" charts.

**Key Properties (Fields):**

*   **`chart_name`**: The name of the chart.
*   **`chart_type`**: The type of chart (e.g., "Count", "Sum", "Group By").
*   **`document_type`**: The DocType on which the chart is based.
*   **`based_on`**: For time-series charts, the date field to use for the x-axis.
*   **`value_based_on`**: For "Sum" and "Average" charts, the numeric field to aggregate.
*   **`group_by_based_on`**: For "Group By" charts, the field to group the data by.
*   **`filters_json`**: A JSON field to store static filters for the chart.
*   **`type`**: The visual type of the chart (e.g., "Line", "Bar", "Pie").

### `frappe/desk/doctype/note/note.py`

This file defines the `Note` DocType, a simple tool for users to create and share notes.

#### Class: `Note(Document)`

This class represents a note. Notes can be public or private and can be configured to appear as notifications upon login.

**Key Methods:**

*   **`mark_seen_by(user)`**: Adds a user to the `seen_by` child table to record that they have seen the note.

**Key Functions (outside the class):**

*   **`get_unseen_notes()`**: Fetches all notes that are marked as "Notify on Login" and have not yet been seen by the current user.
*   **`mark_as_seen(note)`**: A whitelisted method that calls `mark_seen_by` to mark a note as seen by the current user.

**Key Properties (Fields):**

*   **`title`**: The title of the note.
*   **`content`**: The content of the note, stored as HTML.
*   **`public`**: If checked, the note is visible to all users.
*   **`notify_on_login`**: If checked, the note will appear as a notification for users until they mark it as seen.
*   **`seen_by`**: A child table that records which users have seen the note.

### `frappe/desk/doctype/event/event.py`

This file defines the `Event` DocType, which is the backend for the calendar feature in Frappe.

#### Class: `Event(Document)`

This class represents an event, which can be a meeting, a call, or any other type of scheduled activity. Events can be recurring and can be synced with Google Calendar.

**Key Methods:**

*   **`sync_communication()`**: Creates or updates a `Communication` document for each participant in the event. This is how events are linked to other documents and appear in their timelines.
*   **`add_participants(participants)`**: A helper method to add multiple participants to an event.

**Key Functions (outside theclass):**

*   **`get_events(start, end, user, ...)`**: The main function for fetching events for the calendar view. It takes a start and end date and returns all events within that range that are visible to the user. It also handles the expansion of recurring events.
*   **`send_event_digest()`**: A scheduled job that sends an email to users with a summary of their events for the day.

**Key Properties (Fields):**

*   **`subject`**: The subject or title of the event.
*   **`starts_on`**, **`ends_on`**: The start and end date/time of the event.
*   **`all_day`**: If checked, the event is an all-day event.
*   **`repeat_this_event`**: If checked, the event is a recurring event.
*   **`repeat_on`**, **`repeat_till`**: The frequency and end date for recurring events.
*   **`event_participants`**: A child table that lists the participants of the event. Participants can be linked to any DocType in the system.