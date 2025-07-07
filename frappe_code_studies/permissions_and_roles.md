# How to Manage Frappe Permissions and Roles

This document explains how to define and apply Roles and Permissions in Frappe to control user access to DocTypes and features. Frappe's permission system is role-based, making it flexible and easy to manage.

---

## 1. Core Concepts

- **Role**: A Role is a collection of permissions that can be assigned to a user. Examples include "Accounts Manager", "Sales User", and "HR User". Roles are managed via the "Role" DocType.

- **Permission**: A Permission grants a Role specific access rights to a DocType, such as the ability to read, write, create, or delete documents.

- **Role Profile**: A Role Profile is a collection of Roles that can be assigned to a user. This simplifies user management by allowing you to assign a single profile instead of multiple individual roles. For example, a "Sales Manager" Role Profile might include the "Sales User", "Sales Manager", and "Stock User" roles.

---

## 2. Defining Permissions in a DocType

Permissions are defined within the `permissions` array in a DocType's `.json` file. Each object in the array represents a permission rule for a specific role.

**Example**: `Sales Invoice` Permissions (`erpnext-develop/erpnext/accounts/doctype/sales_invoice/sales_invoice.json`)

```json
"permissions": [
    {
        "role": "Accounts Manager",
        "read": 1,
        "write": 1,
        "create": 1,
        "delete": 1,
        "submit": 1,
        "cancel": 1,
        "amend": 1,
        "share": 1,
        "report": 1
    },
    {
        "role": "Accounts User",
        "read": 1,
        "write": 1,
        "create": 1,
        "submit": 1,
        "amend": 1,
        "share": 1,
        "report": 1
    },
    {
        "role": "All",
        "read": 1,
        "permlevel": 1
    }
]
```

### Permission Properties

- **`"role"`**: The name of the Role to which the permission applies.
- **`"read"`**: Allows users with this role to view documents.
- **`"write"`**: Allows users to edit existing documents.
- **`"create"`**: Allows users to create new documents.
- **`"delete"`**: Allows users to delete documents.
- **`"submit"`**: Allows users to submit submittable documents.
- **`"cancel"`**: Allows users to cancel submitted documents.
- **`"amend"`**: Allows users to amend submitted documents.
- **`"share"`**: Allows users to share documents with other users.
- **`"report"`**: Allows users to view the DocType in reports.
- **`"permlevel"`**: The permission level (0-9) for the rule. This is used for creating field-level permissions. Fields with a `permlevel` greater than 0 will only be visible to roles with a matching or higher `permlevel`.

---

## 3. Creating Roles and Role Profiles

- **Roles**: You can create new Roles by navigating to the "Role" list in the Frappe desk and clicking "New". Simply give the role a name and save it.

- **Role Profiles**: You can create new Role Profiles by navigating to the "Role Profile" list. Give the profile a name and then add the desired roles to the "Roles" table.

### Assigning Roles to Users

Once you have defined your Roles and Role Profiles, you can assign them to users in the "User" list. Each user has a "Roles" section where you can add individual roles or Role Profiles.

---

## 4. Conditional Permissions

For more granular control, you can use server-side logic to apply conditional permissions. This is typically done by implementing a `has_permission` method in your DocType's Python controller.

**Conceptual Example:**
```python
class MyDocType(Document):
    def has_permission(self, ptype, user):
        if ptype == "read" and self.status == "Confidential":
            # Only allow users with the "Manager" role to read confidential documents
            return "Manager" in frappe.get_roles(user)
        return True
```

This method allows you to implement complex permission rules based on the document's state or any other custom logic.