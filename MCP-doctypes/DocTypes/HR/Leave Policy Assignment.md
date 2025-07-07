# Master Control Plan: `Leave Policy Assignment`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-LPOL-ASSGN-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee name | Data | None |  |  | ✅ | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `leave_policy` | Leave Policy | Link | Leave Policy | ✅ |  |  | None | None |
| `carry_forward` | Add unused leaves from previous allocations | Check | None |  |  |  | 0 | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `assignment_based_on` | Assignment based on | Select | 
Leave Period
Joining Date |  |  |  | None | None |
| `leave_period` | Leave Period | Link | Leave Period |  |  |  | None | None |
| `effective_from` | Effective From | Date | None | ✅ |  |  | None | None |
| `effective_to` | Effective To | Date | None | ✅ |  |  | None | None |
| `leaves_allocated` | Leaves Allocated | Check | None |  | ✅ |  | 0 | None |
| `amended_from` | Amended From | Link | Leave Policy Assignment |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_policy_assignment/leave_policy_assignment.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Leave Policy Assignment", {
	onload: function (frm) {
		frm.ignore_doctypes_on_cancel_all = ["Leave Ledger Entry"];

		frm.set_query("leave_policy", function () {
			return {
				filters: {
					docstatus: 1,
				},
			};
		});
		frm.set_query("leave_period", function () {
			return {
				filters: {
					is_active: 1,
					company: frm.doc.company,
				},
			};
		});
	},

	assignment_based_on: function (frm) {
		if (frm.doc.assignment_based_on) {
			frm.events.set_effective_date(frm);
		} else {
			frm.set_value("effective_from", "");
			frm.set_value("effective_to", "");
		}
	},

	leave_period: function (frm) {
		if (frm.doc.leave_period) {
			frm.events.set_effective_date(frm);
		}
	},

	set_effective_date: function (frm) {
		if (frm.doc.assignment_based_on == "Leave Period" && frm.doc.leave_period) {
			frappe.model.with_doc("Leave Period", frm.doc.leave_period, function () {
				let from_date = frappe.model.get_value(
					"Leave Period",
					frm.doc.leave_period,
					"from_date",
				);
				let to_date = frappe.model.get_value(
					"Leave Period",
					frm.doc.leave_period,
					"to_date",
				);
				frm.set_value("effective_from", from_date);
				frm.set_value("effective_to", to_date);
			});
		} else if (frm.doc.assignment_based_on == "Joining Date" && frm.doc.employee) {
			frappe.model.with_doc("Employee", frm.doc.employee, function () {
				let from_date = frappe.model.get_value(
					"Employee",
					frm.doc.employee,
					"date_of_joining",
				);
				frm.set_value("effective_from", from_date);
				frm.set_value(
					"effective_to",
					frappe.datetime.add_months(frm.doc.effective_from, 12),
				);
			});
		}
		frm.refresh();
	},
});

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
