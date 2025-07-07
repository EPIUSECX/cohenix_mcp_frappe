# Master Control Plan: `Employee Tax Exemption Declaration`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-TAX-DEC-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `payroll_period` | Payroll Period | Link | Payroll Period | ✅ |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Employee Tax Exemption Declaration |  |  | ✅ | None | None |
| `section_break_8` | Tax Exemption Declaration | Tab Break | None |  |  |  | None | None |
| `declarations` | Declarations | Table | Employee Tax Exemption Declaration Category |  |  |  | None | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `total_declared_amount` | Total Declared Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `total_exemption_amount` | Total Exemption Amount | Currency | currency |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/employee_tax_exemption_declaration/employee_tax_exemption_declaration.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Tax Exemption Declaration", {
	setup: function (frm) {
		frm.set_query("employee", function () {
			return {
				filters: {
					status: "Active",
				},
			};
		});

		frm.set_query("payroll_period", function () {
			const fields = { employee: "Employee", company: "Company" };

			for (let [field, label] of Object.entries(fields)) {
				if (!frm.doc[field]) {
					frappe.msgprint(__("Please select {0}", [label]));
				}
			}

			if (frm.doc.employee && frm.doc.company) {
				return {
					filters: {
						company: frm.doc.company,
					},
				};
			}
		});

		frm.set_query("exemption_sub_category", "declarations", function () {
			return {
				filters: {
					is_active: 1,
				},
			};
		});
	},

	refresh: function (frm) {
		if (frm.doc.docstatus == 1) {
			frm.add_custom_button(__("Submit Proof"), function () {
				frappe.model.open_mapped_doc({
					method: "hrms.payroll.doctype.employee_tax_exemption_declaration.employee_tax_exemption_declaration.make_proof_submission",
					frm: frm,
				});
			}).addClass("btn-primary");
		}
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
| Name | Label | Function | Module |
|---|---|---|---|
| `Total Declaration Submitted` | Total Declaration Submitted | Count | Payroll |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
