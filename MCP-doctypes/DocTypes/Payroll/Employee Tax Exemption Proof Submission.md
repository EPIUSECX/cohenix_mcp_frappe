# Master Control Plan: `Employee Tax Exemption Proof Submission`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-TAX-PRF-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee_details_tab` | Employee | Tab Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Employee Tax Exemption Proof Submission |  |  | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `submission_date` | Submission Date | Date | None | ✅ |  |  | Today | None |
| `payroll_period` | Payroll Period | Link | Payroll Period | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  | ✅ | None | None |
| `exemption_proofs_details_tab` | Exemption Proofs | Tab Break | None |  |  |  | None | None |
| `tax_exemption_proofs` | Tax Exemption Proofs | Table | Employee Tax Exemption Proof Submission Detail |  |  |  | None | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `total_actual_amount` | Total Actual Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `exemption_amount` | Total Exemption Amount | Currency | currency |  |  | ✅ | None | None |
| `attachment_section` | None | Section Break | None |  |  |  | None | None |
| `attachments` | Attachments | Attach | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/employee_tax_exemption_proof_submission/employee_tax_exemption_proof_submission.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Tax Exemption Proof Submission", {
	setup: function (frm) {
		frm.set_query("employee", function () {
			return {
				filters: {
					status: "Active",
				},
			};
		});

		frm.set_query("payroll_period", function () {
			if (frm.doc.employee && frm.doc.company) {
				return {
					filters: {
						company: frm.doc.company,
					},
				};
			} else {
				frappe.msgprint(__("Please select Employee"));
			}
		});

		frm.set_query("exemption_sub_category", "tax_exemption_proofs", function () {
			return {
				filters: {
					is_active: 1,
				},
			};
		});
	},

	refresh: function (frm) {
		// hide attachments section in new forms in favor of the Attach Proof button against each proof
		frm.toggle_display("attachments", frm.doc.attachments ? 1 : 0);

		if (frm.doc.docstatus === 0) {
			let filters = {
				docstatus: 1,
				company: frm.doc.company,
			};
			if (frm.doc.employee) filters["employee"] = frm.doc.employee;
			if (frm.doc.payroll_period) filters["payroll_period"] = frm.doc.payroll_period;

			frm.add_custom_button(__("Get Details From Declaration"), function () {
				erpnext.utils.map_current_doc({
					method: "hrms.payroll.doctype.employee_tax_exemption_declaration.employee_tax_exemption_declaration.make_proof_submission",
					source_doctype: "Employee Tax Exemption Declaration",
					target: frm,
					date_field: "creation",
					setters: {
						employee: frm.doc.employee || undefined,
					},
					get_query_filters: filters,
				});
			});
		}
	},

	currency: function (frm) {
		frm.refresh_fields();
	},

	employee: function (frm) {
		if (frm.doc.employee) {
			frm.trigger("get_employee_currency");
		}
	},

	get_employee_currency: function (frm) {
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
