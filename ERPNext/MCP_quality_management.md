# Model Context Profile: Quality Management

## 1. Module Overview

The `quality_management` module in ERPNext provides a comprehensive framework for implementing a Quality Management System (QMS). It is designed to help organizations document, monitor, and improve their processes in line with quality standards like ISO 9001. The module provides tools for defining quality procedures, setting goals, managing non-conformances, conducting reviews, and gathering feedback.

The module is structured around a few key concepts: defining the "right way" to do things (`Quality Procedure`), measuring performance against that standard (`Quality Goal`, `Quality Feedback`), and correcting deviations (`Non Conformance`, `Quality Action`).

## 2. Core Components

### 2.1. `Quality Procedure`

This is the foundation of the QMS module. It allows for the detailed documentation of all organizational processes.

-   **Key Features**:
    -   **Hierarchical Structure**: It is a tree-structured DocType (`NestedSet`), allowing procedures to be broken down into sub-procedures. A `is_group` field designates a procedure as a container for others.
    -   **Process Definition**: Each procedure can have a list of detailed steps or sub-processes in the `processes` child table.
    -   **Process Ownership**: Each procedure has a designated `process_owner` (a `User`).
    -   **Linkages**: It is linked to all other major QMS documents, providing a central point of reference.

-   **Business Logic (`quality_procedure.py`)**:
    -   The controller logic primarily manages the tree structure, ensuring that parent-child relationships are correctly maintained when procedures are created, moved, or deleted.

### 2.2. `Non Conformance`

This DocType is used to formally record any deviation from a specified `Quality Procedure`.

-   **Key Features**:
    -   **Link to Procedure**: Each non-conformance must be linked to the `Quality Procedure` that was violated.
    -   **Details and Actions**: It includes fields to describe the `details` of the non-conformance and to outline the proposed `corrective_action` and `preventive_action`.
    -   **Status**: Tracks the status of the non-conformance (`Open`, `Resolved`, `Cancelled`).

### 2.3. `Quality Action`

This DocType is used to manage the implementation of corrective or preventive actions to address quality issues.

-   **Key Features**:
    -   **Action Type**: Can be designated as either `Corrective` or `Preventive`.
    -   **Source**: Can be linked to a `Quality Review`, `Quality Feedback`, or a `Quality Goal`.
    -   **Resolution**: Contains a child table (`resolutions`) to list the specific steps taken to resolve the quality issue. Each resolution has its own status.
    -   **Overall Status**: The status of the `Quality Action` (`Open`, `Completed`) is automatically determined by the status of its resolutions.

### 2.4. `Quality Feedback` and `Quality Feedback Template`

These DocTypes provide a system for collecting structured feedback from users.

-   **`Quality Feedback Template`**:
    -   Allows the creation of reusable feedback forms with a defined set of questions or `parameters`.
    -   Each parameter has a `parameter` name and a `description`.

-   **`Quality Feedback`**:
    -   An instance of feedback collection, created using a `Quality Feedback Template`.
    -   The `parameters` table is populated from the template, and users can provide a `rating` and `comment` for each parameter.

### 2.5. `Quality Goal`

This DocType is used to set and monitor specific, measurable quality objectives.

-   **Key Features**:
    -   **Link to Procedure**: Each goal is linked to a `Quality Procedure`.
    -   **Objectives**: Contains a child table (`objectives`) where specific, measurable targets can be defined (e.g., "Reduce customer complaints by 10%").
    -   **Monitoring**: Each objective has a field for the `target` and the `achieved` value, allowing for performance tracking.

### 2.6. `Quality Meeting` and `Quality Review`

These DocTypes facilitate the formal review of the QMS.

-   **`Quality Meeting`**:
    -   Manages the logistics of quality review meetings, including scheduling and attendees.
    -   Contains a child table for the meeting `agenda` and another for the `minutes`.

-   **`Quality Review`**:
    -   A formal record of a review of a specific `Quality Procedure`.
    -   It documents the `objectives` of the review and the `review_summary`.

## 3. Data Flow and Integrations

1.  **Foundation**: The **`Quality Procedure`** documents define the standard processes.
2.  **Goal Setting**: **`Quality Goals`** are set against these procedures to drive improvement.
3.  **Monitoring**: **`Quality Feedback`** is collected using **`Quality Feedback Templates`** to measure user satisfaction or process adherence.
4.  **Deviation**: If a process deviates from the standard, a **`Non Conformance`** is raised against the relevant **`Quality Procedure`**.
5.  **Correction**: To address the non-conformance or a finding from a **`Quality Review`**, a **`Quality Action`** is created. This action outlines the corrective/preventive steps.
6.  **Review Cycle**: **`Quality Meetings`** are held to conduct **`Quality Reviews`**, which may lead to new goals or actions, thus completing the continuous improvement cycle (Plan-Do-Check-Act).

## 4. Architectural Significance

The `quality_management` module provides a structured, document-driven approach to quality assurance. It is designed to be flexible enough to adapt to various quality standards and organizational needs. By integrating QMS activities directly into the ERP, it allows quality to be managed as an integral part of the organization's operations, rather than as a separate, siloed function. The use of linked documents creates a clear audit trail, which is essential for certification and regulatory compliance.

## 5. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.quality_management.doctype.quality_procedure.quality_procedure`
- `get_children`: Fetches child procedures for the Quality Procedure tree view.
- `add_node`: Adds a new procedure to the tree.

### `erpnext.quality_management.doctype.quality_feedback.quality_feedback`
- `set_parameters`: Populates the `parameters` table in a Quality Feedback document from the selected template.