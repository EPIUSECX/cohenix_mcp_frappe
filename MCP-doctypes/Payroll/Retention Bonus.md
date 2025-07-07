# Master Control Plan: `Retention Bonus`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-RTB-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee_section` | Employee | Section Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `date_of_joining` | Date of Joining | Data | None |  |  | ✅ | None | None |
| `bonus_section` | Bonus | Section Break | None |  |  |  | None | None |
| `salary_component` | Salary Component | Link | Salary Component | ✅ |  |  | None | None |
| `bonus_amount` | Bonus Amount | Currency | currency | ✅ |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `bonus_payment_date` | Bonus Payment Date | Date | None | ✅ |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Retention Bonus |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/retention_bonus/retention_bonus.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Retention Bonus", {
	setup: function (frm) {
		frm.set_query("employee", function () {
			if (!frm.doc.company) {
				frappe.msgprint(__("Please Select Company First"));
			}
			return {
				filters: {
					status: "Active",
					company: frm.doc.company,
				},
			};
		});

		frm.set_query("salary_component", function () {
			return {
				filters: {
					type: "Earning",
				},
			};
		});
	},

	employee: function (frm) {
		if (frm.doc.employee) {
			frappe.call({
				method: "hrms.payroll.doctype.salary_structure_assignment.salary_structure_assignment.get_employee_currency",
				args: {
					employee: frm.doc.employee,
				},
				callback: function (r) {
					if (r.message) {
						frm.set_value("currency", r.message);
						frm.refresh_fields();
					}
				},
			});
		}
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
| Name | Event | Channel | Subject |
|---|---|---|---|
| `Retention Bonus` | Days Before | Email | Retention Bonus alert for {{ doc.employee }} |



### Webhooks
No enabled webhooks found.
