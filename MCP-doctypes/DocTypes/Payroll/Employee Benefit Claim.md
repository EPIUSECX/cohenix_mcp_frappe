# Master Control Plan: `Employee Benefit Claim`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-BEN-CLM-.YY.-.MM.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `claim_date` | Claim Date | Date | None | ✅ |  |  | Today | None |
| `currency` | Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Employee Benefit Claim |  |  | ✅ | None | None |
| `benefit_type_and_amount` | Benefits | Section Break | None |  |  |  | None | None |
| `earning_component` | Claim Benefit For | Link | Salary Component | ✅ |  |  | None | None |
| `max_amount_eligible` | Max Amount Eligible | Currency | currency |  |  | ✅ | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `pay_against_benefit_claim` | Pay Against Benefit Claim | Check | None |  | ✅ | ✅ | 0 | None |
| `claimed_amount` | Claimed Amount | Currency | currency | ✅ |  |  | None | None |
| `salary_slip` | Salary Slip | Link | Salary Slip |  |  | ✅ | None | None |
| `section_break_9` | Expense Proof | Section Break | None |  |  |  | None | None |
| `attachments` | Attachments | Attach | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/employee_benefit_claim/employee_benefit_claim.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Benefit Claim", {
	setup: function (frm) {
		frm.set_query("earning_component", function () {
			return {
				query: "hrms.payroll.doctype.employee_benefit_application.employee_benefit_application.get_earning_components",
				filters: { date: frm.doc.claim_date, employee: frm.doc.employee },
			};
		});
	},
	employee: function (frm) {
		frm.set_value("earning_component", null);
		if (frm.doc.employee) {
			frappe.call({
				method: "hrms.payroll.doctype.salary_structure_assignment.salary_structure_assignment.get_employee_currency",
				args: {
					employee: frm.doc.employee,
				},
				callback: function (r) {
					if (r.message) {
						frm.set_value("currency", r.message);
					}
				},
			});
		}
		if (!frm.doc.earning_component) {
			frm.doc.max_amount_eligible = null;
			frm.doc.claimed_amount = null;
		}
		frm.refresh_fields();
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
