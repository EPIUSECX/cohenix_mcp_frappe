# Master Control Plan: `Sales Person`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:sales_person_name`
- **Description:** All Sales Transactions can be tagged against multiple Sales Persons so that you can set and monitor targets.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `name_and_employee_id` | Name and Employee ID | Section Break | icon-user |  |  |  | None | None |
| `sales_person_name` | Sales Person Name | Data | None | ✅ |  |  | None | None |
| `parent_sales_person` | Parent Sales Person | Link | Sales Person |  |  |  | None | Select company name first. |
| `commission_rate` | Commission Rate | Data | None |  |  |  | None | None |
| `is_group` | Is Group | Check | None | ✅ |  |  | 0 | None |
| `enabled` | Enabled | Check | None |  |  |  | 1 | None |
| `cb0` | None | Column Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee |  |  |  | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `lft` | lft | Int | None |  | ✅ |  | None | None |
| `rgt` | rgt | Int | None |  | ✅ |  | None | None |
| `old_parent` | old_parent | Data | None |  | ✅ |  | None | None |
| `target_details_section_break` | Sales Person Targets | Section Break | icon-bullseye |  |  |  | None | Set targets Item Group-wise for this Sales Person. |
| `targets` | Targets | Table | Target Detail |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/sales_person/sales_person.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Sales Person", {
	refresh: function (frm) {
		if (frm.doc.__onload && frm.doc.__onload.dashboard_info) {
			let info = frm.doc.__onload.dashboard_info;
			frm.dashboard.add_indicator(
				__("Total Contribution Amount Against Orders: {0}", [
					format_currency(info.allocated_amount_against_order, info.currency),
				]),
				"blue"
			);

			frm.dashboard.add_indicator(
				__("Total Contribution Amount Against Invoices: {0}", [
					format_currency(info.allocated_amount_against_invoice, info.currency),
				]),
				"blue"
			);
		}
		frm.trigger("set_root_readonly");
	},

	setup: function (frm) {
		frm.fields_dict["targets"].grid.get_field("distribution_id").get_query = function (doc, cdt, cdn) {
			var row = locals[cdt][cdn];
			return {
				filters: {
					fiscal_year: row.fiscal_year,
				},
			};
		};

		frm.make_methods = {
			"Sales Order": () =>
				frappe
					.new_doc("Sales Order")
					.then(() => frm.add_child("sales_team", { sales_person: frm.doc.name })),
		};
	},
	set_root_readonly: function (frm) {
		// read-only for root
		if (!frm.doc.parent_sales_person && !frm.doc.__islocal) {
			frm.set_read_only();
			frm.set_intro(__("This is a root sales person and cannot be edited."));
		} else {
			frm.set_intro(null);
		}
	},
});

//get query select sales person
cur_frm.fields_dict["parent_sales_person"].get_query = function (doc, cdt, cdn) {
	return {
		filters: [
			["Sales Person", "is_group", "=", 1],
			["Sales Person", "name", "!=", doc.sales_person_name],
		],
	};
};

cur_frm.fields_dict.employee.get_query = function (doc, cdt, cdn) {
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
