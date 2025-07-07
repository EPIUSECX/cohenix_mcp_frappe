# How to Create Frappe Workspaces

This document explains how to create and structure Workspaces in Frappe. Workspaces are configurable pages that provide users with quick access to important DocTypes, reports, and pages.

In recent versions of Frappe, Workspaces are managed as a standard DocType. This means each workspace is a document record of the "Workspace" DocType.

---

## 1. Core Concepts

A Workspace is defined by a single `.json` file, which is a record of the "Workspace" DocType. This file contains all the information needed to render the workspace, including its name, icon, shortcuts, and the cards that organize its links.

**Example**: `Selling` Workspace (`erpnext-develop/erpnext/selling/workspace/selling/selling.json`)

---

## 2. Workspace Structure (`.json` file)

The `.json` file for a workspace defines its properties and content. Let's break down the structure using the "Selling" workspace as an example.

```json
{
    "doctype": "Workspace",
    "label": "Selling",
    "icon": "sell",
    "public": 1,
    "charts": [
        {
            "chart_name": "Sales Order Trends",
            "label": "Sales Order Trends"
        }
    ],
    "shortcuts": [
        {
            "label": "Item",
            "link_to": "Item",
            "type": "DocType"
        },
        {
            "label": "Sales Order",
            "link_to": "Sales Order",
            "type": "DocType"
        }
    ],
    "links": [
        {
            "label": "Selling",
            "type": "Card Break"
        },
        {
            "label": "Customer",
            "link_to": "Customer",
            "link_type": "DocType",
            "type": "Link"
        },
        {
            "label": "Quotation",
            "link_to": "Quotation",
            "link_type": "DocType",
            "type": "Link"
        }
    ]
}
```

### Key Properties

- **`"doctype": "Workspace"`**: Identifies the document as a Workspace record.
- **`"label"`**: The display name of the workspace (e.g., "Selling").
- **`"icon"`**: The icon to be displayed in the sidebar.
- **`"public": 1`**: Makes the workspace visible to all users by default. You can use the `"roles"` property to restrict access.

### Charts

The `"charts"` array defines the dashboard charts that appear at the top of the workspace.

- **`"chart_name"`**: The name of the "Dashboard Chart" DocType to display.

### Shortcuts

The `"shortcuts"` array defines the large icon shortcuts for quick access.

- **`"label"`**: The text displayed below the shortcut icon.
- **`"link_to"`**: The name of the DocType, Report, or Page to link to.
- **`"type"`**: The type of link ("DocType", "Report", "Page", or "URL").

### Links and Cards

The `"links"` array is used to define the cards and the links within them.

- **`"type": "Card Break"`**: This entry creates a new card. The `"label"` of this entry is used as the card's title.
- **`"type": "Link"`**: This entry creates a link within the current card.
    - **`"link_type"`**: The type of document to link to ("DocType", "Report", or "Page").
    - **`"link_to"`**: The name of the DocType, Report, or Page.
    - **`"onboard": 1`**: An optional flag to highlight the link as an onboarding step for new users.

---

## 3. How to Create a Custom Workspace

To create a custom workspace in your own app:

1.  **Create the Directory**: In your custom app, create a directory for your workspace. The standard path is:
    `[your_app]/[your_module]/workspace/[workspace_name]/`

2.  **Create the `.json` File**: Inside this directory, create a `[workspace_name].json` file.

3.  **Define the Workspace**: Populate the `.json` file with the structure described above. Define your label, icon, shortcuts, and links.

4.  **Add to `modules.txt`**: Ensure the module containing your workspace is listed in your app's `[your_app]/config/modules.txt` file. This makes the module visible to Frappe.

5.  **Add to Desktop Icons**: To make your workspace appear in the main desktop view, you may need to add it to the `[your_app]/config/desktop.py` file.

**Example `desktop.py`:**
```python
from frappe import _

def get_data():
    return [
        {
            "module_name": "Your Module Name",
            "color": "#ffc107",
            "icon": "octicon octicon-briefcase",
            "type": "module",
            "label": _("Your Module Name")
        }
    ]
```

By following these steps, you can create custom workspaces that provide a tailored user experience for your app's functionality.