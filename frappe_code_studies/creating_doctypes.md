# How to Create Frappe DocTypes

This document provides a comprehensive guide to creating DocTypes in Frappe, based on real-world examples from the ERPNext and HRMS codebases. It covers Standard DocTypes, Child Tables, Single DocTypes, and Tree Structures.

---

## 1. Core Concepts & Files

Every DocType in Frappe is defined by a directory containing at least a `.json` file. Optional `.py` and `.js` files can be added to implement custom logic.

- **`[doctype_name].json`**: The schema definition file. It contains all fields, properties, permissions, and settings for the DocType. This is the only mandatory file.
- **`[doctype_name].py`**: The server-side controller. It contains a Python class that inherits from `frappe.model.document.Document` (or a more specialized controller) and is used to implement business logic, validation, and lifecycle hooks.
- **`[doctype_name].js`**: The client-side script. It contains JavaScript code for handling form events, custom UI interactions, and client-side validation.

---

## 2. Standard DocType

A Standard DocType is the most common type of document in Frappe. It represents a transactional or master record, such as a Sales Invoice, Customer, or Item.

**Example**: `Sales Invoice` (`erpnext-develop/erpnext/accounts/doctype/sales_invoice/`)

### Key Properties (`sales_invoice.json`)

The `.json` file defines the core behavior of the DocType.

```json
{
    "doctype": "DocType",
    "name": "Sales Invoice",
    "owner": "Administrator",
    "module": "Accounts",
    "autoname": "naming_series:",
    "is_submittable": 1,
    "track_changes": 1,
    "permissions": [
        {
            "role": "Accounts Manager",
            "read": 1,
            "write": 1,
            "create": 1,
            "delete": 1,
            "submit": 1,
            "cancel": 1,
            "amend": 1
        }
    ],
    "fields": [
        {
            "fieldname": "customer",
            "fieldtype": "Link",
            "label": "Customer",
            "options": "Customer",
            "reqd": 1
        },
        {
            "fieldname": "posting_date",
            "fieldtype": "Date",
            "label": "Date",
            "reqd": 1
        },
        {
            "fieldname": "items",
            "fieldtype": "Table",
            "label": "Items",
            "options": "Sales Invoice Item",
            "reqd": 1
        }
    ]
}
```

- **`"autoname": "naming_series:"`**: Specifies that the document's name (ID) will be generated from a Naming Series.
- **`"is_submittable": 1`**: Allows the document to have a lifecycle of Draft -> Submitted -> Cancelled. Submitted documents are typically immutable.
- **`"permissions"`**: An array defining Role-based permissions for the DocType.
- **`"fields"`**: An array defining the schema of the document, including field names, types, labels, and properties.

### Server-Side Logic (`sales_invoice.py`)

The Python controller handles backend logic.

```python
# erpnext-develop/erpnext/accounts/doctype/sales_invoice/sales_invoice.py:59
from erpnext.controllers.selling_controller import SellingController

class SalesInvoice(SellingController):
    def validate(self):
        # Custom validation logic before saving
        self.validate_pos_return()
        self.validate_with_previous_doc()
        self.set_status()

    def on_submit(self):
        # Logic to execute upon submission
        self.update_stock_ledger()
        self.make_gl_entries()
        self.update_project()

    def on_cancel(self):
        # Logic to execute upon cancellation
        self.update_prevdoc_status()
        self.make_gl_entries_on_cancel()
```

- **Inheritance**: `SalesInvoice` inherits from `SellingController`, which provides common methods for sales transactions.
- **Hooks**: Methods like `validate`, `on_submit`, and `on_cancel` are automatically called at different points in the document's lifecycle.

### Client-Side Script (`sales_invoice.js`)

The JavaScript file controls frontend behavior.

```javascript
// erpnext-develop/erpnext/accounts/doctype/sales_invoice/sales_invoice.js:600
frappe.ui.form.on("Sales Invoice", {
    refresh: function(frm) {
        // Add a custom button to the form
        if (frm.doc.docstatus == 1 && frm.doc.outstanding_amount != 0) {
            frm.add_custom_button(__("Payment"), () => frm.cscript.make_payment_entry(), __("Create"));
        }
    },

    customer: function(frm) {
        // Fetch party details when the customer is changed
        erpnext.utils.get_party_details(frm, "erpnext.accounts.party.get_party_details", {
            party: frm.doc.customer,
            party_type: "Customer",
        });
    }
});
```

- **`frappe.ui.form.on`**: The primary function for attaching event handlers to a form.
- **`refresh` event**: Triggered when the form is loaded or refreshed. Used here to add a custom "Payment" button.
- **Field events (`customer`)**: Triggered when a field's value changes. Used here to fetch and set related customer data.

---

## 3. Child Table (DocType)

A Child Table is a DocType that is embedded within another DocType, typically to handle line items in a transaction.

**Example**: `Sales Invoice Item` (`erpnext-develop/erpnext/accounts/doctype/sales_invoice_item/`)

### Key Properties (`sales_invoice_item.json`)

The key difference is the `istable` property.

```json
{
    "doctype": "DocType",
    "name": "Sales Invoice Item",
    "module": "Accounts",
    "istable": 1,
    "fields": [
        {
            "fieldname": "item_code",
            "fieldtype": "Link",
            "label": "Item",
            "options": "Item",
            "reqd": 1,
            "in_list_view": 1
        },
        {
            "fieldname": "qty",
            "fieldtype": "Float",
            "label": "Quantity",
            "reqd": 1,
            "in_list_view": 1
        },
        {
            "fieldname": "rate",
            "fieldtype": "Currency",
            "label": "Rate",
            "reqd": 1,
            "in_list_view": 1
        }
    ]
}
```

- **`"istable": 1`**: This property designates the DocType as a Child Table. It cannot be used as a standalone document.
- **`"in_list_view": 1`**: This property makes the field visible in the grid view of the parent's form.

A Child Table does not have its own `permissions` section; its permissions are inherited from the parent document.

---

## 4. Single DocType

A Single DocType is used for settings or configurations that have only one instance in the system.

**Example**: `Accounts Settings` (`erpnext-develop/erpnext/accounts/doctype/accounts_settings/`)

### Key Properties (`accounts_settings.json`)

The key property is `issingle`.

```json
{
    "doctype": "DocType",
    "name": "Accounts Settings",
    "module": "Accounts",
    "issingle": 1,
    "permissions": [
        {
            "role": "Accounts Manager",
            "read": 1,
            "write": 1
        }
    ],
    "fields": [
        {
            "fieldname": "acc_frozen_upto",
            "fieldtype": "Date",
            "label": "Accounts Frozen Till Date"
        },
        {
            "fieldname": "credit_controller",
            "fieldtype": "Link",
            "label": "Role allowed to bypass Credit Limit",
            "options": "Role"
        }
    ]
}
```

- **`"issingle": 1`**: This property marks the DocType as a Single DocType. There will be only one document record for `Accounts Settings`.

### Accessing Single DocTypes

Single DocTypes are accessed via `frappe.get_single()` on the server-side or `frappe.get_doc("Accounts Settings", "Accounts Settings")` on the client-side.

---

## 5. Tree DocType

A Tree DocType is used to represent hierarchical data, such as a Chart of Accounts, Territory, or Item Group.

**Example**: `Account` (`erpnext-develop/erpnext/accounts/doctype/account/`)

### Key Properties (`account.json`)

The key property is `is_tree`.

```json
{
    "doctype": "DocType",
    "name": "Account",
    "module": "Accounts",
    "is_tree": 1,
    "nsm_parent_field": "parent_account",
    "fields": [
        {
            "fieldname": "account_name",
            "fieldtype": "Data",
            "label": "Account Name",
            "reqd": 1
        },
        {
            "fieldname": "parent_account",
            "fieldtype": "Link",
            "label": "Parent Account",
            "options": "Account",
            "reqd": 1
        },
        {
            "fieldname": "is_group",
            "fieldtype": "Check",
            "label": "Is Group"
        },
        {
            "fieldname": "lft",
            "fieldtype": "Int",
            "hidden": 1,
            "read_only": 1
        },
        {
            "fieldname": "rgt",
            "fieldtype": "Int",
            "hidden": 1,
            "read_only": 1
        }
    ]
}
```

- **`"is_tree": 1`**: Marks the DocType as a tree structure.
- **`"nsm_parent_field": "parent_account"`**: Specifies the field used to link to the parent node in the tree.
- **`"is_group"`**: A checkbox to indicate whether a node is a group (can have children) or a leaf (cannot have children).
- **`"lft"` and `"rgt"`**: Hidden fields automatically managed by Frappe's Nested Set Model to efficiently query the tree structure.

### Server-Side Logic (`account.py`)

The controller for a Tree DocType must inherit from `NestedSet`.

```python
# erpnext-develop/erpnext/accounts/doctype/account/account.py:25
from frappe.utils.nestedset import NestedSet

class Account(NestedSet):
    nsm_parent_field = "parent_account"

    def validate(self):
        self.validate_parent()
        self.validate_group_or_ledger()

    def validate_parent(self):
        if self.parent_account:
            parent_is_group = frappe.db.get_value("Account", self.parent_account, "is_group")
            if not parent_is_group:
                frappe.throw(_("Parent account must be a group account."))
```

- **`NestedSet` Inheritance**: Provides all the necessary methods for managing the tree structure, such as rebuilding the tree when nodes are moved.
- **Validation**: Custom validation ensures the integrity of the tree (e.g., a ledger cannot be a parent).