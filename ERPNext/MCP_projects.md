# Model Context Profile: Projects

## 1. Module Overview

The `projects` module is a comprehensive project management system integrated within ERPNext. It provides a full suite of tools for planning, executing, and monitoring projects, from initial setup to final billing. The module is designed to manage the entire project lifecycle, including task management, time tracking, resource allocation, costing, and reporting.

The core of the module revolves around three main DocTypes: `Project`, `Task`, and `Timesheet`. These are supported by numerous other DocTypes for configuration (e.g., `Project Type`, `Activity Type`), data tracking (e.g., `Activity Cost`), and reporting.

## 2. Core Components

### 2.1. `Project` DocType

The `Project` is the central entity in the module. It acts as a container for all project-related information and activities.

-   **Key Features**:
    -   **Project Definition**: Defines the project's name, status (`Open`, `Completed`, `Cancelled`), type, and priority.
    -   **Scheduling**: Captures expected and actual start/end dates.
    -   **Costing and Billing**: Tracks estimated costs, total sales, billable amounts, and billed amounts from linked documents like `Sales Order`, `Purchase Invoice`, and `Timesheet`. It calculates gross margin and percentage margin.
    -   **Progress Tracking**: Progress can be tracked manually or automatically based on task completion, progress, or weight.
    -   **User Management**: Assigns users to the project via the `Project User` child table.
    -   **Templates**: Projects can be created from a `Project Template`, which automatically generates a predefined set of tasks.
    -   **Automated Reminders**: Can be configured to send periodic email reminders to users to update their progress.

-   **Business Logic (`project.py`)**:
    -   `update_costing()`: Recalculates all project costs and revenues by aggregating data from linked `Timesheet`, `Purchase Invoice`, and `Sales Order` documents.
    -   `update_percent_complete()`: Automatically updates the project's completion percentage based on the selected method.
    -   `copy_from_template()`: Creates a set of tasks for the project based on a selected `Project Template`.
    -   `send_welcome_email()`: Sends an invitation email to newly added project users.
    -   `project_status_update_reminder()`: A scheduler hook that triggers daily, weekly, or hourly reminders for progress updates.

### 2.2. `Task` DocType

The `Task` represents an individual unit of work within a project. Tasks can be organized hierarchically and have dependencies.

-   **Key Features**:
    -   **Hierarchy**: Tasks can be structured in a tree using the `parent_task` field, allowing for sub-tasks. The `is_group` property designates a task as a container for other tasks.
    -   **Dependencies**: A task can be made dependent on other tasks using the `depends_on` child table. A task cannot be completed until its dependencies are met.
    -   **Scheduling**: Includes expected and actual start/end dates, and expected time (in hours).
    -   **Progress and Weight**: Each task has a `progress` field and a `task_weight`, which are used for calculating the overall project completion.
    -   **Costing**: Aggregates `total_costing_amount` and `total_billing_amount` from linked `Timesheet` entries.
    -   **Templates**: Tasks can be marked as `is_template` to be included in `Project Template` documents.

-   **Business Logic (`task.py`)**:
    -   **Nested Set Model**: Implements `NestedSet` for efficient management of the task hierarchy (`lft`, `rgt` fields).
    -   `check_recursion()`: Prevents circular dependencies between tasks.
    -   `reschedule_dependent_tasks()`: Automatically pushes the start date of a dependent task if the end date of its prerequisite is delayed.
    -   `update_project()`: Triggers an update on the parent `Project` document whenever a task is updated, ensuring project-level metrics are current.

### 2.3. `Timesheet` DocType

The `Timesheet` is used to log time spent by employees on specific tasks and projects. It is the primary source of data for project costing and billing.

-   **Key Features**:
    -   **Time Logs**: Contains a child table (`Timesheet Detail`) where users log `from_time`, `to_time`, `activity_type`, `project`, and `task`.
    -   **Billing and Costing**: For each time log, the system calculates `billing_amount` and `costing_amount` based on the `Activity Cost` and `Activity Type` master data.
    -   **Billable Hours**: Time logs can be marked as `is_billable`, which determines whether they contribute to the project's billable amount.
    -   **Integration with Invoicing**: Timesheets can be pulled into a `Sales Invoice` to bill customers for project work.
    -   **Status Tracking**: A timesheet moves through a lifecycle (`Draft`, `Submitted`, `Billed`, `Completed`, `Cancelled`).

-   **Business Logic (`timesheet.py`)**:
    -   `validate_overlap()`: Prevents users or employees from logging overlapping time entries.
    -   `update_task_and_project()`: On submit or cancel, it updates the actual time and costing information on the linked `Task` and `Project` documents.
    -   `make_sales_invoice()`: A controller method to create a `Sales Invoice` directly from a `Timesheet`.

## 3. Supporting Components

-   **Configuration DocTypes**:
    -   `Project Template`: Defines a reusable set of tasks for creating new projects.
    -   `Activity Type`: Defines standard types of work (e.g., "Development", "Testing", "Design") and their default billing/costing rates.
    -   `Activity Cost`: Allows setting specific billing/costing rates for an employee and activity type combination, overriding the defaults in `Activity Type`.
    -   `Projects Settings`: A singleton DocType for global settings, such as whether to allow overlapping time entries.
-   **Reports**: The module includes several standard reports, such as `Daily Timesheet Summary`, `Project Summary`, and `Project Wise Stock Tracking`.
-   **Dashboards**: Provides dashboards for `Project` and `Task` to give a quick overview of progress and key metrics.

## 4. Data Flow and Integrations

1.  A **`Project`** is created, optionally from a **`Project Template`**, which generates a set of **`Tasks`**.
2.  An **`Employee`** logs work against a **`Task`** by creating a **`Timesheet`**.
3.  The **`Timesheet`** calculates billing and costing amounts based on **`Activity Cost`** and **`Activity Type`**.
4.  On submission, the **`Timesheet`** updates the `actual_time` and costing fields on the linked **`Task`**.
5.  The **`Task`** update triggers a recalculation of progress and costs on the parent **`Project`**.
6.  A **`Sales Invoice`** can be created from the **`Timesheet`** to bill the **`Customer`**.
7.  **`Purchase Invoices`** and **`Stock Entries`** linked to the **`Project`** also contribute to its total cost.

## 5. Architectural Significance

The `projects` module is a cornerstone of ERPNext's service-oriented functionality. Its tight integration with accounting, sales, purchasing, and stock modules provides a 360-degree view of project profitability and performance. The hierarchical task structure, dependency management, and automated time tracking make it a powerful tool for managing complex projects within the ERP ecosystem.

## 6. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.projects.doctype.project.project`
- `get_cost_center_name`: Fetches the cost center associated with a project.
- `create_duplicate_project`: Creates a copy of an existing project.
- `create_kanban_board_if_not_exists`: Creates a Kanban board for the project's tasks.
- `set_project_status`: Updates the status of a project.
- `recalculate_project_total_purchase_cost`: Recalculates the project's purchase costs.

### `erpnext.projects.doctype.task.task`
- `check_if_child_exists`: Checks if a task has any sub-tasks.
- `set_multiple_status`: A bulk action to update the status of multiple tasks.
- `make_timesheet`: Creates a Timesheet from a Task.
- `get_children`: Fetches child tasks for the task tree view.
- `add_node`: Adds a new task to the tree.
- `add_multiple_tasks`: A bulk action to add multiple tasks under a parent.

### `erpnext.projects.doctype.timesheet.timesheet`
- `get_projectwise_timesheet_data`: Fetches timesheet data for a specific project.
- `get_timesheet_detail_rate`: Gets the billing/costing rate for a specific time log entry.
- `get_timesheet_data`: Fetches data for a specific timesheet.
- `make_sales_invoice`: Creates a Sales Invoice from a Timesheet.
- `get_activity_cost`: Gets the cost for a specific employee and activity type.
- `get_events`: Fetches timesheet data to be displayed on the calendar.

### `erpnext.projects.doctype.project_update.project_update`
- `daily_reminder`: A scheduler function to send daily reminders for project updates.

### `erpnext.projects.utils`
- This file contains query functions for powering search fields (link fields) within the projects module.