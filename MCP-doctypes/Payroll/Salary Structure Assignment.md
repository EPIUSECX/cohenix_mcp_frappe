# Master Control Plan: `Salary Structure Assignment`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-SSA-.YY.-.MM.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `designation` | Designation | Link | Designation |  |  | ✅ | None | None |
| `grade` | Grade | Link | Employee Grade |  |  | ✅ | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `salary_structure` | Salary Structure | Link | Salary Structure | ✅ |  |  | None | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `income_tax_slab` | Income Tax Slab | Link | Income Tax Slab |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `payroll_payable_account` | Payroll Payable Account | Link | Account |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `section_break_7` | Base & Variable | Section Break | None |  |  |  | None | None |
| `base` | Base | Currency | currency |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `variable` | Variable | Currency | currency |  |  |  | None | None |
| `amended_from` | Amended From | Link | Salary Structure Assignment |  |  | ✅ | None | None |
| `opening_balances_section` | Opening Balances | Section Break | None |  | ✅ |  | None | Set opening balances for earnings and taxes from the previous employer |
| `taxable_earnings_till_date` | Taxable Earnings Till Date | Currency | currency |  |  |  | None | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `tax_deducted_till_date` | Tax Deducted Till Date | Currency | currency |  |  |  | None | None |
| `section_break_17` | Payroll Cost Centers | Section Break | None |  |  |  | None | None |
| `payroll_cost_centers` | Cost Centers | Table | Employee Cost Center |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 10
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_structure_assignment/salary_structure_assignment.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Salary Structure Assignment", {
	setup: function (frm) {
		frm.set_query("employee", function () {
			return {
				query: "erpnext.controllers.queries.employee_query",
				filters: { company: frm.doc.company },
			};
		});
		frm.set_query("salary_structure", function () {
			return {
				filters: {
					company: frm.doc.company,
					docstatus: 1,
					is_active: "Yes",
				},
			};
		});

		frm.set_query("income_tax_slab", function () {
			return {
				filters: {
					company: frm.doc.company,
					docstatus: 1,
					disabled: 0,
					currency: frm.doc.currency,
				},
			};
		});

		frm.set_query("payroll_payable_account", function () {
			var company_currency = erpnext.get_currency(frm.doc.company);
			return {
				filters: {
					company: frm.doc.company,
					root_type: "Liability",
					is_group: 0,
					account_currency: ["in", [frm.doc.currency, company_currency]],
				},
			};
		});

		frm.set_query("cost_center", "payroll_cost_centers", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});
	},

	refresh: function (frm) {
		frm.trigger("toggle_opening_balances_section");

		if (frm.doc.docstatus != 1) return;

		frm.add_custom_button(
			__("Payroll Entry"),
			() => {
				frappe.model.with_doctype("Payroll Entry", () => {
					const doc = frappe.model.get_new_doc("Payroll Entry");
					frappe.set_route("Form", "Payroll Entry", doc.name);
				});
			},
			__("Create"),
		);
		frm.page.set_inner_btn_group_as_primary(__("Create"));

		frm.add_custom_button(
			__("Preview Salary Slip"),
			function () {
				frm.trigger("preview_salary_slip");
			},
			__("Actions"),
		);
	},

	employee: function (frm) {
		if (frm.doc.employee) {
			frm.trigger("set_payroll_cost_centers");
			frm.trigger("toggle_opening_balances_section");
		} else {
			frm.set_value("payroll_cost_centers", []);
		}
	},

	company: function (frm) {
		if (frm.doc.company) {
			frappe.db.get_value(
				"Company",
				frm.doc.company,
				"default_payroll_payable_account",
				(r) => {
					frm.set_value("payroll_payable_account", r.default_payroll_payable_account);
				},
			);
		}
	},

	preview_salary_slip: function (frm) {
		frappe.db.get_value(
			"Salary Structure",
			frm.doc.salary_structure,
			"salary_slip_based_on_timesheet",
			(r) => {
				const print_format = r.salary_slip_based_on_timesheet
					? "Salary Slip based on Timesheet"
					: "Salary Slip Standard";
				frappe.call({
					method: "hrms.payroll.doctype.salary_structure.salary_structure.make_salary_slip",
					args: {
						source_name: frm.doc.salary_structure,
						employee: frm.doc.employee,
						posting_date: frm.doc.from_date,
						as_print: 1,
						print_format: print_format,
						for_preview: 1,
					},
					callback: function (r) {
						const new_window = window.open();
						new_window.document.write(r.message);
					},
				});
			},
		);
	},

	set_payroll_cost_centers: function (frm) {
		if (frm.doc.payroll_cost_centers && frm.doc.payroll_cost_centers.length < 1) {
			frappe.call({
				method: "set_payroll_cost_centers",
				doc: frm.doc,
				callback: function (data) {
					refresh_field("payroll_cost_centers");
				},
			});
		}
	},

	toggle_opening_balances_section: function (frm) {
		if (!frm.doc.from_date || !frm.doc.employee) return;

		frm.call("are_opening_entries_required").then((data) => {
			if (data.message) {
				frm.set_df_property("opening_balances_section", "hidden", 0);
			} else {
				frm.set_df_property("opening_balances_section", "hidden", 1);
			}
		});
	},

	from_date: function (frm) {
		if (frm.doc.from_date) {
			frm.trigger("toggle_opening_balances_section");
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
