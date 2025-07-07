# How to Create Frappe Client and Server Scripts

This document explains how to write Client and Server Scripts in Frappe to add custom logic and behavior to DocTypes. These scripts are essential for creating dynamic and interactive forms.

---

## 1. Client Scripts (`[doctype_name].js`)

Client Scripts are written in JavaScript and run in the user's browser. They are used to handle form events, manipulate the UI, and communicate with the server.

**Example**: `Sales Invoice` Client Script (`erpnext-develop/erpnext/accounts/doctype/sales_invoice/sales_invoice.js`)

### The `frappe.ui.form.on` Event Handler

The primary way to attach event handlers to a form is by using `frappe.ui.form.on`.

```javascript
// erpnext-develop/erpnext/accounts/doctype/sales_invoice/sales_invoice.js:600
frappe.ui.form.on("Sales Invoice", {
    // Form-level events
    refresh: function(frm) {
        // Code to run when the form is refreshed
    },
    validate: function(frm) {
        // Code to run before the form is saved
    },

    // Field-level events
    customer: function(frm) {
        // Code to run when the 'customer' field value changes
    }
});
```

### Common Form Events

- **`refresh`**: Triggered when the form is loaded or refreshed. This is a good place to add custom buttons, set field properties, or perform initial calculations.
- **`validate`**: Triggered when the user clicks "Save". This is used for client-side validation before the document is sent to the server.
- **Field-level events** (e.g., `customer`): Triggered when the value of a specific field changes. The event name matches the `fieldname` of the field.

### Calling Server-Side Methods with `frappe.call`

Client scripts can call server-side methods using `frappe.call`. This is the standard way to fetch data or execute business logic on the server without a full page reload.

```javascript
// erpnext-develop/erpnext/accounts/doctype/sales_invoice/sales_invoice.js:496
return this.frm.call({
    doc: me.frm.doc,
    method: "set_missing_values",
    args: {
        for_validate: for_validate
    },
    callback: function(r) {
        if (!r.exc) {
            // ... handle the response from the server
        }
    }
});
```

- **`method`**: The name of the Python method to call. This method must be decorated with `@frappe.whitelist()`.
- **`doc`**: The current document can be passed to the server-side method.
- **`args`**: A dictionary of additional arguments to pass to the method.
- **`callback`**: A function that is executed when the server responds. The response object `r` contains the return value in `r.message`.

---

## 2. Server Scripts (`[doctype_name].py`)

Server Scripts are written in Python and run on the server. They are used for data validation, business logic, and interacting with the database.

**Example**: `Sales Invoice` Server Script (`erpnext-develop/erpnext/accounts/doctype/sales_invoice/sales_invoice.py`)

### Standard Lifecycle Hooks

The DocType controller class has several standard methods (hooks) that are automatically called at different points in the document's lifecycle.

```python
# erpnext-develop/erpnext/accounts/doctype/sales_invoice/sales_invoice.py:59
class SalesInvoice(SellingController):
    def validate(self):
        # Called before the document is saved
        # Use for data validation that requires database access
        self.validate_proj_cust()

    def on_submit(self):
        # Called when the document is submitted
        # Use for actions that should only happen once, like posting to the ledger
        self.make_gl_entries()

    def on_cancel(self):
        # Called when the document is cancelled
        # Use to reverse actions taken in on_submit
        self.make_gl_entries_on_cancel()
```

- **`validate`**: Called before `on_submit` and `on_update`. Ideal for complex validation rules.
- **`on_submit`**: Called when a submittable document is submitted.
- **`on_cancel`**: Called when a submittable document is cancelled.
- **`before_save`**: Called before the document is saved to the database.
- **`after_save`**: Called after the document is saved to the database.

### Whitelisted Methods

To expose a server-side method to be called from a client script, you must decorate it with `@frappe.whitelist()`.

```python
# erpnext-develop/erpnext/accounts/doctype/sales_invoice/sales_invoice.py:733
@frappe.whitelist()
def set_missing_values(self, for_validate=False):
    # ... logic to set default values ...
    pos = self.set_pos_fields(for_validate)
    return {
        "print_format": pos.get("print_format") if pos else None
    }
```

- **`@frappe.whitelist()`**: This decorator makes the method accessible via `frappe.call` from the client-side.
- **Security**: Be cautious about what you whitelist. Only expose methods that are safe to be called by any user with access to the form. Frappe automatically handles permission checks for the document itself.

By combining client and server scripts, you can create rich, responsive, and secure applications in Frappe.