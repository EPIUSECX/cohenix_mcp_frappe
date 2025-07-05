# Model Context Profile: `workflow`

## 1. Module Overview

The `workflow` module provides a powerful state machine for any DocType in the Frappe Framework. It allows administrators to define custom document lifecycles with specific states (e.g., Draft, Pending Approval, Approved, Rejected) and transitions between them. Each transition can be restricted to certain roles and can trigger actions.

The core components are:
-   **Workflow DocType**: A document used to define the entire workflow, including its states and transitions, and link it to a specific document type.
-   **Workflow Engine**: The logic embedded within the generic `frappe.model.document.Document` class that applies the defined workflow rules to documents during their lifecycle (on save, submit, cancel).
-   **Workflow Builder**: A client-side, single-page application that provides a visual interface for creating and managing workflow definitions.

## 2. File Structure and Key Components

```
frappe/workflow/
├── doctype/
│   ├── workflow/
│   │   ├── workflow.js
│   │   └── workflow.py       # Controller for the Workflow DocType itself.
│   ├── workflow_state/       # Child DocType for defining states.
│   └── workflow_transition/  # Child DocType for defining transitions.
└── page/
    └── workflow_builder/
        ├── workflow_builder.js # Loads the JS bundle for the builder UI.
        └── workflow_builder.py # Server-side helpers for the builder.
```

-   **`doctype/workflow/workflow.py`**: Contains the server-side logic for the `Workflow` doctype. Its primary role is to validate the workflow definition itself (e.g., ensuring logical transitions) and to create a necessary custom field on the target doctype to store the current state.
-   **`page/workflow_builder/workflow_builder.js`**: A simple page script that loads the main `workflow_builder.bundle.js`, which contains the Vue.js or similar front-end application for the visual workflow editor.
-   **`frappe/model/document.py`**: This is where the core workflow engine logic resides. It is not part of the `workflow` module directly but is invoked by all documents. The key methods are `validate_workflow` and `set_workflow_state_on_action`.
-   **`frappe/model/workflow.py`**: Contains helper functions used by `document.py` to apply workflow logic.

## 3. Key Classes and Functions

### `frappe.model.document.Document` (Workflow-related methods)

-   **`validate_workflow()`**: This method is called during the `_validate` phase of a document's lifecycle. It retrieves the active workflow for the document's type (if any) and validates the current state and any proposed action against the defined transitions.
-   **`set_workflow_state_on_action(workflow, action)`**: Called after a successful validation, this method determines the `next_state` based on the current state and the action being performed (e.g., 'Submit', 'Approve', 'Reject'). It then updates the document's `workflow_state_field` to the new state.

### `frappe.workflow.doctype.workflow.workflow.Workflow`

-   **`validate()`**: Ensures that the defined states and transitions are logical. For example, it prevents creating a transition from a "Cancelled" state or from a "Submitted" state back to a "Draft" state.
-   **`on_update()`**: Automatically creates a custom "Link" field on the target `document_type` if it doesn't already exist. This field is used to store the document's current workflow state.

## 4. Dependencies and Interactions

-   **`frappe.model.document.Document`**: The workflow engine is tightly coupled with the `Document` class. The workflow logic is a generic feature available to any DocType, and it's triggered from within the `save` and `submit` methods of the `Document` class.
-   **Custom Fields**: The workflow system relies on a custom field being present on the target DocType to track the current state. This field is created automatically when the workflow is saved.
-   **Permissions System**: Transitions between states are role-based. The workflow engine checks if the current user has the role specified in the `Workflow Transition` document before allowing the state change.

## 5. Public API / Callable Functions

The workflow functionality is primarily invoked implicitly through the document lifecycle (`doc.save()`, `doc.submit()`). There isn't a large public Python API for direct interaction, as the state changes are managed by the framework based on user actions.

The main point of interaction for users and administrators is the **Workflow Builder** UI, which provides a user-friendly way to define the state machine without writing code.