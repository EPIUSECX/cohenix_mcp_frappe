# Master Control Plan: `Additional Salary`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | HR-ADS-.YY.-.MM.- | ✅ |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `is_recurring` | Is Recurring | Check | None |  |  |  | 0 | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `from_date` | From Date | Date | None |  |  |  | None | None |
| `to_date` | To Date | Date | None |  |  |  | None | None |
| `payroll_date` | Payroll Date | Date | None |  |  |  | None | The date on which Salary Component with Amount will contribute for Earnings/Deduction in Salary Slip.  |
| `amended_from` | Amended From | Link | Additional Salary |  |  | ✅ | None | None |
| `salary_details_section` | Salary | Section Break | None |  |  |  | None | None |
| `salary_component` | Salary Component | Link | Salary Component | ✅ |  |  | None | None |
| `type` | Salary Component Type | Data | None |  |  | ✅ | None | None |
| `currency` | Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `amount` | Amount | Currency | currency | ✅ |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `deduct_full_tax_on_selected_payroll_date` | Deduct Full Tax on Selected Payroll Date | Check | None |  |  |  | 0 | None |
| `overwrite_salary_structure_amount` | Overwrite Salary Structure Amount | Check | None |  |  |  | 1 | None |
| `properties_and_references_section` | References | Section Break | None |  |  |  | None | None |
| `ref_doctype` | Reference Document Type | Link | DocType |  |  | ✅ | None | None |
| `ref_docname` | Reference Document | Dynamic Link | ref_doctype |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/additional_salary/additional_salary.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Additional Salary", {
	setup: function (frm) {
		frm.add_fetch(
			"salary_component",
			"deduct_full_tax_on_selected_payroll_date",
			"deduct_full_tax_on_selected_payroll_date",
		);

		frm.set_query("employee", function () {
			return {
				filters: {
					company: frm.doc.company,
					status: ["!=", "Inactive"],
				},
			};
		});
	},

	onload: function (frm) {
		if (frm.doc.type) {
			frm.trigger("set_component_query");
		}
	},

	employee: function (frm) {
		if (frm.doc.employee) {
			frappe.run_serially([
				() => frm.trigger("get_employee_currency"),
				() => frm.trigger("set_company"),
			]);
		} else {
			frm.set_value("company", null);
		}
	},

	set_company: function (frm) {
		frappe.call({
			method: "frappe.client.get_value",
			args: {
				doctype: "Employee",
				fieldname: "company",
				filters: {
					name: frm.doc.employee,
				},
			},
			callback: function (data) {
				if (data.message) {
					frm.set_value("company", data.message.company);
				}
			},
		});
	},

	company: function (frm) {
		frm.set_value("type", "");
		frm.trigger("set_component_query");
	},

	set_component_query: function (frm) {
		if (!frm.doc.company) return;
		let filters = { company: frm.doc.company };
		if (frm.doc.type) {
			filters.type = frm.doc.type;
		}
		frm.set_query("salary_component", function () {
			return {
				filters: filters,
			};
		});
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

	salary_component: function (frm) {
		if (!frm.doc.ref_doctype) {
			frm.trigger("get_salary_component_amount");
		}
	},

	get_salary_component_amount: function (frm) {
		frappe.call({
			method: "frappe.client.get_value",
			args: {
				doctype: "Salary Component",
				fieldname: "amount",
				filters: {
					name: frm.doc.salary_component,
				},
			},
			callback: function (data) {
				if (data.message) {
					frm.set_value("amount", data.message.amount);
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
