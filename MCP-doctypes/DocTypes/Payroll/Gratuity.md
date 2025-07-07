# Master Control Plan: `Gratuity`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-GRA-PAY-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `details_tab` | Gratuity | Tab Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `designation` | Designation | Data | None |  |  | ✅ | None | None |
| `current_work_experience` | Current Work Experience | Float | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting date | Date | None | ✅ |  |  | None | None |
| `gratuity_rule` | Gratuity Rule | Link | Gratuity Rule | ✅ |  |  | None | None |
| `status` | Status | Select | Draft
Unpaid
Paid
Submitted
Cancelled |  |  | ✅ | Draft | None |
| `company` | Company | Link | Company | ✅ |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Gratuity |  |  | ✅ | None | None |
| `section_break_5` | Payment and Accounting | Tab Break | None |  |  |  | None | None |
| `pay_via_salary_slip` | Pay via Salary Slip | Check | None |  |  |  | 1 | None |
| `amount` | Total Amount | Currency | None | ✅ |  | ✅ | 0 | None |
| `paid_amount` | Paid Amount | Currency | None |  |  | ✅ | 0 | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `payroll_date` | Payroll Date | Date | None |  |  |  | None | None |
| `salary_component` | Salary Component | Link | Salary Component |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `payable_account` | Payable Account | Link | Account |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 10
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/gratuity/gratuity.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Gratuity", {
	setup: function (frm) {
		frm.set_query("salary_component", function () {
			return {
				filters: {
					type: "Earning",
				},
			};
		});

		frm.set_query("expense_account", function () {
			return {
				filters: {
					root_type: "Expense",
					is_group: 0,
					company: frm.doc.company,
				},
			};
		});

		frm.set_query("payable_account", function () {
			return {
				filters: {
					root_type: "Liability",
					is_group: 0,
					company: frm.doc.company,
				},
			};
		});
	},
	refresh: function (frm) {
		if (frm.doc.docstatus == 1 && !frm.doc.pay_via_salary_slip && frm.doc.status == "Unpaid") {
			frm.add_custom_button(__("Create Payment Entry"), function () {
				return frappe.call({
					method: "hrms.overrides.employee_payment_entry.get_payment_entry_for_employee",
					args: {
						dt: frm.doc.doctype,
						dn: frm.doc.name,
					},
					callback: function (r) {
						var doclist = frappe.model.sync(r.message);
						frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
					},
				});
			});
		}
	},

	employee: function (frm) {
		frm.events.calculate_work_experience_and_amount(frm);
	},

	gratuity_rule: function (frm) {
		frm.events.calculate_work_experience_and_amount(frm);
	},

	calculate_work_experience_and_amount: function (frm) {
		if (frm.doc.employee && frm.doc.gratuity_rule) {
			frm.call("calculate_work_experience_and_amount").then((r) => {
				frm.set_value("current_work_experience", r.message["current_work_experience"]);
				frm.set_value("amount", r.message["amount"]);
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
No enabled notifications found.


### Webhooks
No enabled webhooks found.
