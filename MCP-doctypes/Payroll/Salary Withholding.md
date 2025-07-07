# Master Control Plan: `Salary Withholding`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `format:SAL-WTH-{#####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_fwuv` | None | Section Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `column_break_hbju` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `payroll_frequency` | Payroll Frequency | Select | 
Monthly
Fortnightly
Bimonthly
Weekly
Daily |  |  | ✅ | None | None |
| `number_of_withholding_cycles` | Number of Withholding Cycles | Int | None | ✅ |  |  | None | None |
| `column_break_rhlv` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Withheld
Released
Cancelled |  |  | ✅ | Draft | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `to_date` | To Date | Date | None | ✅ |  | ✅ | None | None |
| `exit_details_section` | Exit Details | Section Break | None |  |  |  | None | None |
| `date_of_joining` | Date of Joining | Date | None |  |  | ✅ | None | None |
| `column_break_qlwx` | None | Column Break | None |  |  |  | None | None |
| `relieving_date` | Relieving Date | Date | None |  |  | ✅ | None | None |
| `reason_section` | Reason | Section Break | None |  |  |  | None | None |
| `reason_for_withholding_salary` | Reason for Withholding Salary | Small Text | None |  |  |  | None | None |
| `section_break_xeyl` | None | Section Break | None |  |  |  | None | None |
| `cycles` | Cycles | Table | Salary Withholding Cycle |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Salary Withholding |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_withholding/salary_withholding.js`
```javascript
// Copyright (c) 2024, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Salary Withholding", {
	employee(frm) {
		if (!frm.doc.employee) return;

		frappe
			.call({
				method: "hrms.payroll.doctype.salary_withholding.salary_withholding.get_payroll_frequency",
				args: {
					employee: frm.doc.employee,
					posting_date: frm.doc.posting_date,
				},
			})
			.then((r) => {
				if (r.message) {
					frm.set_value("payroll_frequency", r.message);
				}
			});
	},

	from_date(frm) {
		if (!frm.doc.from_date || !frm.doc.payroll_frequency)
			frappe.msgprint(__("Please select From Date and Payroll Frequency first"));

		frm.call({
			method: "set_withholding_cycles_and_to_date",
			doc: frm.doc,
		}).then((r) => {
			frm.refresh_field("to_date");
			frm.refresh_field("cycles");
		});
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
