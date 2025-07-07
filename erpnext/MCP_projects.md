# Model Context Profile: Projects

## 1. Module Overview

The `projects` module is a comprehensive project management system integrated within ERPNext. It provides a full suite of tools for planning, executing, and monitoring projects, from initial setup to final billing. The module is designed to manage the entire project lifecycle, including task management, time tracking, resource allocation, costing, and reporting.

The core of the module revolves around three main DocTypes: `Project`, `Task`, and `Timesheet`. These are supported by numerous other DocTypes for configuration (e.g., `Project Type`, `Activity Type`), data tracking (e.g., `Activity Cost`), and reporting.

## 2. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development.

### 2.1. Server-Side (Python)

#### `erpnext.projects.doctype.project.project.Project` (Class Methods)

-   **`update_costing()`**: This is a critical instance method that recalculates all project costs and revenues. It aggregates data from linked `Timesheet`, `Purchase Invoice`, and `Sales Order` documents to provide a real-time financial overview of the project, including gross margin.
-   **`update_percent_complete()`**: This method automatically updates the project's completion percentage based on the selected method (e.g., 'Task Completion', 'Task Progress'). It is the core logic for tracking project progress.
-   **`copy_from_template()`**: This method is called when a `project_template` is set. It creates a new set of tasks for the project based on the template, including their dependencies and hierarchy.
-   **`create_duplicate_project(prev_doc, project_name)`**: A whitelisted function that creates a deep copy of an existing project, including all its tasks. This is useful for starting new projects based on previous ones.

#### `erpnext.projects.doctype.task.task.Task` (Class Methods)

-   **`on_update()`**: This is the central method for the `Task` DocType. It is responsible for updating the Nested Set model (`lft`, `rgt`), checking for circular dependencies, rescheduling dependent tasks if dates change, and triggering an update on the parent `Project`.
-   **`reschedule_dependent_tasks()`**: This method is called when a task's end date changes. It automatically pushes the start date of any tasks that depend on it, ensuring the project schedule remains consistent.
-   **`make_timesheet(source_name, ...)`**: A whitelisted function that creates a `Timesheet` from a `Task`, pre-filling it with the relevant project and task details.

### 2.2. Client-Side (JavaScript)

#### `frappe.ui.form.on("Project", ...)` in `project.js`

-   **`refresh(frm)`**: This is the main UI controller for the Project form. It dynamically adds custom buttons based on the document's state, such as "Gantt Chart", "Kanban Board", and "Duplicate Project". It also triggers the rendering of the project dashboard.
-   **`create_duplicate(frm)`**: This function prompts the user for a new project name and then calls the server-side `create_duplicate_project` method to perform the duplication.
-   **`set_status(frm, status)`**: This function shows a confirmation dialog and then calls the server-side `set_project_status` method to update the status of the project and all its associated tasks.

#### `frappe.ui.form.on("Task", ...)` in `task.js`

-   **`onload(frm)`**: This function sets up dynamic queries for the `parent_task` and `depends_on` fields. This ensures that users can only select valid tasks within the same project and prevents circular dependencies from being created through the UI.
-   **`is_group(frm)`**: This event handler includes a validation check. It calls the server-side `check_if_child_exists` method to prevent a user from converting a task with sub-tasks into a non-group task, thus protecting the integrity of the task hierarchy.

## 3. Data Flow and Integrations

1.  A **`Project`** is created, optionally from a **`Project Template`**, which generates a set of **`Tasks`**.
2.  An **`Employee`** logs work against a **`Task`** by creating a **`Timesheet`**.
3.  The **`Timesheet`** calculates billing and costing amounts based on **`Activity Cost`** and **`Activity Type`**.
4.  On submission, the **`Timesheet`** updates the `actual_time` and costing fields on the linked **`Task`**.
5.  The **`Task`** update triggers a recalculation of progress and costs on the parent **`Project`**.
6.  A **`Sales Invoice`** can be created from the **`Timesheet`** to bill the **`Customer`**.
7.  **`Purchase Invoices`** and **`Stock Entries`** linked to the **`Project`** also contribute to its total cost.

## 4. Architectural Significance

The `projects` module is a cornerstone of ERPNext's service-oriented functionality. Its tight integration with accounting, sales, purchasing, and stock modules provides a 360-degree view of project profitability and performance. The hierarchical task structure, dependency management, and automated time tracking make it a powerful tool for managing complex projects within the ERP ecosystem.