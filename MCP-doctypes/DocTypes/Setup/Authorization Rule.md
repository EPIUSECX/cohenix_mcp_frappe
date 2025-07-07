# Master Control Plan: `Authorization Rule`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `HR-ARU-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `transaction` | Transaction | Select | 
Sales Order
Purchase Order
Quotation
Delivery Note
Sales Invoice
Purchase Invoice
Purchase Receipt | ✅ |  |  | None | None |
| `based_on` | Based On | Select | 
Grand Total
Average Discount
Customerwise Discount
Itemwise Discount
Item Group wise Discount
Not Applicable | ✅ |  |  | None | None |
| `customer_or_item` | Customer or Item | Select | Customer
Item
Item Group |  | ✅ | ✅ | None | None |
| `master_name` | Customer / Item / Item Group | Dynamic Link | customer_or_item |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `section_break_17` | None | Section Break | None |  |  |  | None | None |
| `value` | Authorized Value | Float | None |  |  |  | None | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `system_role` | Applicable To (Role) | Link | Role |  |  |  | None | None |
| `to_emp` | Applicable To (Employee) | Link | Employee |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `system_user` | Applicable To (User) | Link | User |  |  |  | None | None |
| `to_designation` | Applicable To (Designation) | Link | Designation |  |  |  | None | None |
| `section_break_13` | None | Section Break | None |  |  |  | None | None |
| `approving_role` | Approving Role (above authorized value) | Link | Role |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `approving_user` | Approving User  (above authorized value) | Link | User |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/authorization_rule/authorization_rule.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Authorization Rule", {
	refresh: function (frm) {
		frm.events.set_master_type(frm);
	},
	set_master_type: function (frm) {
		if (frm.doc.based_on === "Customerwise Discount") {
			unhide_field("master_name");
			frm.set_value("customer_or_item", "Customer");
		} else if (frm.doc.based_on === "Itemwise Discount") {
			unhide_field("master_name");
			frm.set_value("customer_or_item", "Item");
		} else if (frm.doc.based_on === "Item Group wise Discount") {
			unhide_field("master_name");
			frm.set_value("customer_or_item", "Item Group");
		} else {
			frm.set_value("customer_or_item", "");
			frm.set_value("master_name", "");
			hide_field("master_name");
		}
	},
	based_on: function (frm) {
		frm.events.set_master_type(frm);
		if (frm.doc.based_on === "Not Applicable") {
			frm.set_value("value", 0);
			hide_field("value");
		} else {
			unhide_field("value");
		}
	},
	transaction: function (frm) {
		unhide_field(["system_role", "system_user", "value", "based_on"]);
		hide_field(["to_emp", "to_designation"]);
	},
});

// Settings Module
cur_frm.cscript.refresh = function (doc, cdt, cdn) {
	if (doc.based_on == "Not Applicable") hide_field("value");
	else unhide_field("value");

	unhide_field(["system_role", "system_user", "value"]);
	hide_field(["to_emp", "to_designation"]);
};

cur_frm.fields_dict.system_user.get_query = function (doc, cdt, cdn) {
	return { query: "frappe.core.doctype.user.user.user_query" };
};

cur_frm.fields_dict.approving_user.get_query = function (doc, cdt, cdn) {
	return { query: "frappe.core.doctype.user.user.user_query" };
};

cur_frm.fields_dict["approving_role"].get_query = cur_frm.fields_dict["system_role"].get_query;

// System Role Trigger
// -----------------------
cur_frm.fields_dict["system_role"].get_query = function (doc) {
	return {
		filters: [["Role", "name", "not in", "Administrator, Guest, All"]],
	};
};

// Master Name Trigger
// --------------------
cur_frm.fields_dict["master_name"].get_query = function (doc) {
	if (doc.based_on == "Customerwise Discount")
		return {
			doctype: "Customer",
			filters: [["Customer", "docstatus", "!=", 2]],
		};
	else if (doc.based_on == "Itemwise Discount")
		return {
			doctype: "Item",
			query: "erpnext.controllers.queries.item_query",
		};
	else if (doc.based_on === "Item Group wise Discount")
		return {
			doctype: "Item Group",
			filters: {
				is_group: 0,
			},
		};
	else
		return {
			filters: [["Item", "name", "=", "cheating done to avoid null"]],
		};
};

cur_frm.fields_dict.to_emp.get_query = function (doc, cdt, cdn) {
	return { query: "erpnext.controllers.queries.employee_query" };
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
No linked reports found.


### Dashboard Charts
No dashboard charts found.


### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
