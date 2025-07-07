# Model Context Profile: Quality Management

## 1. Module Overview

The `quality_management` module in ERPNext provides a comprehensive framework for implementing a Quality Management System (QMS). It is designed to help organizations document, monitor, and improve their processes in line with quality standards like ISO 9001. The module provides tools for defining quality procedures, setting goals, managing non-conformances, conducting reviews, and gathering feedback.

The module is structured around a few key concepts: defining the "right way" to do things (`Quality Procedure`), measuring performance against that standard (`Quality Goal`, `Quality Feedback`), and correcting deviations (`Non Conformance`, `Quality Action`).

## 2. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development.

### 2.1. Server-Side (Python)

#### `erpnext.quality_management.doctype.quality_procedure.quality_procedure.QualityProcedure` (Class Methods)

-   **`on_update()`**: This is the core method for managing the hierarchical structure of quality procedures. It leverages the `NestedSet` model to maintain the integrity of the tree, automatically updating parent-child relationships when a procedure is moved or its sub-procedures are changed.
-   **`set_parent()`**: This internal method is called on update. It iterates through the child procedures listed in the `processes` table and sets their `parent_quality_procedure` field, ensuring the relationship is correctly established in the database.
-   **`get_children(doctype, parent, ...)`**: A whitelisted function that is used by the client-side tree view to fetch the direct children of a given `Quality Procedure`. This is essential for rendering the procedure hierarchy in the UI.

#### `erpnext.quality_management.doctype.quality_action.quality_action.QualityAction` (Class Methods)

-   **`validate()`**: This method contains the core business logic for the `Quality Action` DocType. It automatically sets the overall `status` of the action to 'Open' or 'Completed' based on the status of the individual steps listed in the `resolutions` child table. This provides a simple, aggregated view of the action's progress.

### 2.2. Client-Side (JavaScript)

#### `frappe.ui.form.on("Quality Procedure", ...)` in `quality_procedure.js`

-   **`refresh(frm)`**: This function sets up dynamic queries for the `parent_quality_procedure` and the `procedure` fields in the child table. These queries are crucial for the user experience, as they filter the selection lists to prevent invalid data entry (e.g., setting a procedure as its own parent or child).

## 3. Data Flow and Integrations

1.  **Foundation**: The **`Quality Procedure`** documents define the standard processes.
2.  **Goal Setting**: **`Quality Goals`** are set against these procedures to drive improvement.
3.  **Monitoring**: **`Quality Feedback`** is collected using **`Quality Feedback Templates`** to measure user satisfaction or process adherence.
4.  **Deviation**: If a process deviates from the standard, a **`Non Conformance`** is raised against the relevant **`Quality Procedure`**.
5.  **Correction**: To address the non-conformance or a finding from a **`Quality Review`**, a **`Quality Action`** is created. This action outlines the corrective/preventive steps.
6.  **Review Cycle**: **`Quality Meetings`** are held to conduct **`Quality Reviews`**, which may lead to new goals or actions, thus completing the continuous improvement cycle (Plan-Do-Check-Act).

## 4. Architectural Significance

The `quality_management` module provides a structured, document-driven approach to quality assurance. It is designed to be flexible enough to adapt to various quality standards and organizational needs. By integrating QMS activities directly into the ERP, it allows quality to be managed as an integral part of the organization's operations, rather than as a separate, siloed function. The use of linked documents creates a clear audit trail, which is essential for certification and regulatory compliance.