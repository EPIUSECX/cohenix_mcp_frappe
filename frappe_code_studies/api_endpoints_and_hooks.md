# How to Create Frappe API Endpoints and Hooks

This document explains how to create custom API endpoints and register hooks in Frappe, allowing for extensive customization and integration.

---

## 1. Custom API Endpoints

You can create custom server-side functions and expose them as API endpoints that can be called from client scripts or external applications. This is achieved using the `@frappe.whitelist()` decorator.

### Creating a Whitelisted Method

Any Python function decorated with `@frappe.whitelist()` becomes an API endpoint. These functions can be defined in any `.py` file within your app.

**Example**: A function to get party details.

```python
# erpnext-develop/erpnext/accounts/party.py:58
import frappe

@frappe.whitelist()
def get_party_details(party_type, party, company):
    # ... logic to fetch party details ...
    party_details = {
        "customer_name": "Test Customer",
        "credit_limit": 5000
    }
    return party_details
```

- **`@frappe.whitelist()`**: This decorator makes the `get_party_details` function accessible via the Frappe API.
- **Arguments**: The function can accept arguments, which will be passed in the API call.
- **Return Value**: The function's return value will be serialized as a JSON response.

### Calling the API Endpoint

You can call this endpoint from a client script using `frappe.call`:

```javascript
frappe.call({
    method: "erpnext.accounts.party.get_party_details",
    args: {
        party_type: "Customer",
        party: "Test Customer",
        company: "Frappe Inc"
    },
    callback: function(r) {
        if (r.message) {
            console.log(r.message);
            // Outputs: { "customer_name": "Test Customer", "credit_limit": 5000 }
        }
    }
});
```

- **`method`**: The full path to the whitelisted function, in the format `[app_name].[path_to_module].[function_name]`.

You can also call this endpoint via a standard HTTP request:

`GET /api/method/erpnext.accounts.party.get_party_details?party_type=Customer&party=Test%20Customer&company=Frappe%20Inc`

---

## 2. Hooks

Hooks are a powerful mechanism in Frappe that allows you to extend or override the framework's core behavior without modifying the source code. Hooks are registered in the `hooks.py` file located in your app's root directory.

**Example**: `erpnext-develop/erpnext/hooks.py`

### Document Events (`doc_events`)

This hook allows you to trigger a function on a specific DocType event (e.g., `on_submit`, `on_cancel`, `validate`).

```python
# erpnext-develop/erpnext/hooks.py:358
doc_events = {
    "Sales Invoice": {
        "on_submit": "erpnext.regional.create_transaction_log"
    },
    "User": {
        "validate": "erpnext.setup.doctype.employee.employee.validate_employee_role"
    }
}
```

- The keys of the outer dictionary are DocType names.
- The keys of the inner dictionary are the event names.
- The value is the full path to the function to be executed.

### Scheduler Events (`scheduler_events`)

This hook allows you to schedule functions to run at regular intervals.

```python
# erpnext-develop/erpnext/hooks.py:427
scheduler_events = {
    "hourly": [
        "erpnext.projects.doctype.project.project.hourly_reminder"
    ],
    "daily_maintenance": [
        "erpnext.support.doctype.issue.issue.auto_close_tickets"
    ]
}
```

- **Keys**: The frequency of the event ("all", "hourly", "daily", "weekly", "monthly").
- **Value**: A list of function paths to be executed at that frequency.

### Website Generators (`website_generators`)

This hook specifies which DocTypes should have a web page generated for them.

```python
# erpnext-develop/erpnext/hooks.py:113
website_generators = ["BOM", "Sales Partner"]
```

- When a DocType is listed here, Frappe will look for a corresponding template to render its web view.

### Other Common Hooks

- **`override_doctype_class`**: Allows you to replace a core DocType's controller class with your own custom class.
- **`doctype_js`**: Injects a custom JavaScript file into a DocType's form view.
- **`app_include_js` / `app_include_css`**: Includes custom JS and CSS files across the entire desk application.

By using hooks, you can deeply integrate your app's functionality with the Frappe framework in a clean and maintainable way.