# Master Control Plan: `Salary Structure`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `is_active` | Is Active | Select | 
Yes
No | ✅ |  |  | Yes | None |
| `is_default` | Is Default | Select | Yes
No |  | ✅ | ✅ | No | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Salary Structure |  |  | ✅ | None | None |
| `time_sheet_earning_detail` | None | Section Break | None |  |  |  | None | None |
| `leave_encashment_amount_per_day` | Leave Encashment Amount Per Day | Currency | currency |  |  |  | None | None |
| `max_benefits` | Max Benefits (Amount) | Currency | currency |  |  |  | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `salary_slip_based_on_timesheet` | Salary Slip Based on Timesheet | Check | None |  |  |  | 0 | None |
| `payroll_frequency` | Payroll Frequency | Select | 
Monthly
Fortnightly
Bimonthly
Weekly
Daily |  |  |  | Monthly | None |
| `salary_component` | Salary Component | Link | Salary Component |  |  |  | None | Salary Component for timesheet based payroll. |
| `hour_rate` | Hour Rate | Currency | currency |  |  |  | None | None |
| `earning_deduction` | Earnings & Deductions | Tab Break | None |  |  |  | None | Salary breakup based on Earning and Deduction. |
| `earnings` | Earnings | Table | Salary Detail |  |  |  | None | None |
| `deductions` | Deductions | Table | Salary Detail |  |  |  | None | None |
| `conditions_and_formula_variable_and_example` | Conditions and Formula variable and example | HTML | None |  |  |  | None | None |
| `net_pay_detail` | None | Section Break | Simple |  |  |  | None | None |
| `total_earning` | Total Earning | Currency | currency |  | ✅ | ✅ | None | None |
| `total_deduction` | Total Deduction | Currency | currency |  | ✅ | ✅ | None | None |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `net_pay` | Net Pay | Currency | currency |  | ✅ | ✅ | None | None |
| `account` | Account | Tab Break | None |  |  |  | None | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  |  | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `payment_account` | Payment Account | Link | Account |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_structure/salary_structure.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Salary Structure", {
	onload: function (frm) {
		frm.alerted_rows = [];

		let help_button = $(`<a class = 'control-label'>
			${__("Condition and Formula Help")}
		</a>`).click(() => {
			let d = new frappe.ui.Dialog({
				title: __("Condition and Formula Help"),
				fields: [
					{
						fieldname: "msg_wrapper",
						fieldtype: "HTML",
					},
				],
			});

			let message_html = frappe.render_template("condition_and_formula_help");

			d.fields_dict.msg_wrapper.$wrapper.append(message_html);

			d.show();
		});
		let help_button_wrapper = frm.get_field(
			"conditions_and_formula_variable_and_example",
		).$wrapper;
		help_button_wrapper.empty();
		help_button_wrapper.append(frm.doc.filters_html).append(help_button);

		frm.toggle_reqd(["payroll_frequency"], !frm.doc.salary_slip_based_on_timesheet);

		frm.set_query("payment_account", function () {
			var account_types = ["Bank", "Cash"];
			return {
				filters: {
					account_type: ["in", account_types],
					is_group: 0,
					company: frm.doc.company,
				},
			};
		});
		frm.trigger("set_earning_deduction_component");
	},

	mode_of_payment: function (frm) {
		erpnext.accounts.pos.get_payment_mode_account(
			frm,
			frm.doc.mode_of_payment,
			function (account) {
				frm.set_value("payment_account", account);
			},
		);
	},

	set_earning_deduction_component: function (frm) {
		if (!frm.doc.company) return;
		frm.set_query("salary_component", "earnings", function () {
			return {
				filters: { component_type: "earning", company: frm.doc.company },
				query: "hrms.payroll.doctype.salary_structure.salary_structure.get_salary_component",
			};
		});
		frm.set_query("salary_component", "deductions", function () {
			return {
				filters: { component_type: "deduction", company: frm.doc.company },
				query: "hrms.payroll.doctype.salary_structure.salary_structure.get_salary_component",
			};
		});
	},

	company: function (frm) {
		frm.trigger("set_earning_deduction_component");
	},

	currency: function (frm) {
		calculate_totals(frm.doc);
		frm.trigger("set_dynamic_labels");
		frm.refresh();
	},

	set_dynamic_labels: function (frm) {
		frm.set_currency_labels(
			[
				"net_pay",
				"hour_rate",
				"leave_encashment_amount_per_day",
				"max_benefits",
				"total_earning",
				"total_deduction",
			],
			frm.doc.currency,
		);

		frm.set_currency_labels(
			["amount", "additional_amount", "tax_on_flexible_benefit", "tax_on_additional_salary"],
			frm.doc.currency,
			"earnings",
		);

		frm.set_currency_labels(
			["amount", "additional_amount", "tax_on_flexible_benefit", "tax_on_additional_salary"],
			frm.doc.currency,
			"deductions",
		);

		frm.refresh_fields();
	},

	refresh: function (frm) {
		frm.trigger("set_dynamic_labels");
		frm.trigger("toggle_fields");
		frm.fields_dict["earnings"].grid.set_column_disp("default_amount", false);
		frm.fields_dict["deductions"].grid.set_column_disp("default_amount", false);

		if (frm.doc.docstatus === 1) {
			frm.add_custom_button(
				__("Single Assignment"),
				function () {
					const doc = frappe.model.get_new_doc("Salary Structure Assignment");
					doc.salary_structure = frm.doc.name;
					doc.company = frm.doc.company;
					frappe.set_route("Form", "Salary Structure Assignment", doc.name);
				},
				__("Create"),
			);

			frm.add_custom_button(
				__("Bulk Assignments"),
				() => {
					const doc = frappe.model.get_new_doc("Bulk Salary Structure Assignment");
					doc.salary_structure = frm.doc.name;
					doc.company = frm.doc.company;
					frappe.set_route("Form", "Bulk Salary Structure Assignment", doc.name);
				},
				__("Create"),
			);

			frm.add_custom_button(
				__("Income Tax Slab"),
				() => {
					frappe.model.with_doctype("Income Tax Slab", () => {
						const doc = frappe.model.get_new_doc("Income Tax Slab");
						frappe.set_route("Form", "Income Tax Slab", doc.name);
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
		}

		// set columns read-only
		let fields_read_only = [
			"is_tax_applicable",
			"is_flexible_benefit",
			"variable_based_on_taxable_salary",
		];
		fields_read_only.forEach(function (field) {
			frm.fields_dict.earnings.grid.update_docfield_property(field, "read_only", 1);
			frm.fields_dict.deductions.grid.update_docfield_property(field, "read_only", 1);
		});
		frm.trigger("set_earning_deduction_component");
	},

	salary_slip_based_on_timesheet: function (frm) {
		frm.trigger("toggle_fields");
	},

	preview_salary_slip: function (frm) {
		frappe.call({
			method: "hrms.payroll.doctype.salary_structure.salary_structure.get_employees",
			args: {
				salary_structure: frm.doc.name,
			},
			callback: function (r) {
				var employees = r.message;
				if (!employees) return;
				if (employees.length == 1) {
					frm.events.open_salary_slip(frm, employees[0]);
				} else {
					var d = new frappe.ui.Dialog({
						title: __("Preview Salary Slip"),
						fields: [
							{
								label: __("Employee"),
								fieldname: "employee",
								fieldtype: "Autocomplete",
								reqd: true,
								options: employees,
							},
							{
								fieldname: "fetch",
								label: __("Show Salary Slip"),
								fieldtype: "Button",
							},
						],
					});
					d.get_input("fetch").on("click", function () {
						var values = d.get_values();
						if (!values) return;
						frm.events.open_salary_slip(frm, values.employee);
					});
					d.show();
				}
			},
		});
	},

	open_salary_slip: function (frm, employee) {
		var print_format = frm.doc.salary_slip_based_on_timesheet
			? "Salary Slip based on Timesheet"
			: "Salary Slip Standard";
		frappe.call({
			method: "hrms.payroll.doctype.salary_structure.salary_structure.make_salary_slip",
			args: {
				source_name: frm.doc.name,
				employee: employee,
				as_print: 1,
				print_format: print_format,
				for_preview: 1,
			},
			callback: function (r) {
				var new_window = window.open();
				new_window.document.write(r.message);
			},
		});
	},

	toggle_fields: function (frm) {
		frm.toggle_display(
			["salary_component", "hour_rate"],
			frm.doc.salary_slip_based_on_timesheet,
		);
		frm.toggle_reqd(["salary_component", "hour_rate"], frm.doc.salary_slip_based_on_timesheet);
		frm.toggle_reqd(["payroll_frequency"], !frm.doc.salary_slip_based_on_timesheet);
	},
});

var validate_date = function (frm, cdt, cdn) {
	var doc = locals[cdt][cdn];
	if (doc.to_date && doc.from_date) {
		var from_date = frappe.datetime.str_to_obj(doc.from_date);
		var to_date = frappe.datetime.str_to_obj(doc.to_date);

		if (to_date < from_date) {
			frappe.model.set_value(cdt, cdn, "to_date", "");
			frappe.throw(__("From Date cannot be greater than To Date"));
		}
	}
};

// nosemgrep: frappe-semgrep-rules.rules.frappe-cur-frm-usage
cur_frm.cscript.amount = function (doc, cdt, cdn) {
	calculate_totals(doc, cdt, cdn);
};

var calculate_totals = function (doc) {
	var tbl1 = doc.earnings || [];
	var tbl2 = doc.deductions || [];

	var total_earn = 0;
	var total_ded = 0;
	for (var i = 0; i < tbl1.length; i++) {
		total_earn += flt(tbl1[i].amount);
	}
	for (var j = 0; j < tbl2.length; j++) {
		total_ded += flt(tbl2[j].amount);
	}
	doc.total_earning = total_earn;
	doc.total_deduction = total_ded;
	doc.net_pay = 0.0;
	if (doc.salary_slip_based_on_timesheet == 0) {
		doc.net_pay = flt(total_earn) - flt(total_ded);
	}

	refresh_many(["total_earning", "total_deduction", "net_pay"]);
};

// nosemgrep: frappe-semgrep-rules.rules.frappe-cur-frm-usage
cur_frm.cscript.validate = function (doc, cdt, cdn) {
	calculate_totals(doc);
};

frappe.ui.form.on("Salary Detail", {
	form_render: function (frm, cdt, cdn) {
		const row = locals[cdt][cdn];
		hrms.payroll_utils.set_autocompletions_for_condition_and_formula(frm, row);
	},

	amount: function (frm) {
		calculate_totals(frm.doc);
	},

	earnings_remove: function (frm) {
		calculate_totals(frm.doc);
	},

	deductions_remove: function (frm) {
		calculate_totals(frm.doc);
	},

	formula: function (frm, cdt, cdn) {
		const row = locals[cdt][cdn];
		if (row.formula && !row?.amount_based_on_formula && !frm.alerted_rows.includes(cdn)) {
			frappe.msgprint({
				message: __(
					"{0} Row #{1}: {2} needs to be enabled for the formula to be considered.",
					[toTitle(row.parentfield), row.idx, __("Amount based on formula").bold()],
				),
				title: __("Warning"),
				indicator: "orange",
			});
			frm.alerted_rows.push(cdn);
		}
	},

	salary_component: function (frm, cdt, cdn) {
		var child = locals[cdt][cdn];
		if (child.salary_component) {
			frappe.call({
				method: "frappe.client.get",
				args: {
					doctype: "Salary Component",
					name: child.salary_component,
				},
				callback: function (data) {
					if (data.message) {
						var result = data.message;
						frappe.model.set_value(cdt, cdn, "condition", result.condition);
						frappe.model.set_value(
							cdt,
							cdn,
							"amount_based_on_formula",
							result.amount_based_on_formula,
						);
						if (result.amount_based_on_formula == 1) {
							frappe.model.set_value(cdt, cdn, "formula", result.formula);
						} else {
							frappe.model.set_value(cdt, cdn, "amount", result.amount);
						}
						frappe.model.set_value(
							cdt,
							cdn,
							"statistical_component",
							result.statistical_component,
						);
						frappe.model.set_value(
							cdt,
							cdn,
							"depends_on_payment_days",
							result.depends_on_payment_days,
						);
						frappe.model.set_value(
							cdt,
							cdn,
							"do_not_include_in_total",
							result.do_not_include_in_total,
						);
						frappe.model.set_value(
							cdt,
							cdn,
							"variable_based_on_taxable_salary",
							result.variable_based_on_taxable_salary,
						);
						frappe.model.set_value(
							cdt,
							cdn,
							"is_tax_applicable",
							result.is_tax_applicable,
						);
						frappe.model.set_value(
							cdt,
							cdn,
							"is_flexible_benefit",
							result.is_flexible_benefit,
						);
						refresh_field("earnings");
						refresh_field("deductions");
					}
				},
			});
		}
	},

	amount_based_on_formula: function (frm, cdt, cdn) {
		var child = locals[cdt][cdn];
		if (child.amount_based_on_formula == 1) {
			frappe.model.set_value(cdt, cdn, "amount", null);
			const index = frm.alerted_rows.indexOf(cdn);
			if (index > -1) frm.alerted_rows.splice(index, 1);
		} else {
			frappe.model.set_value(cdt, cdn, "formula", null);
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
| Name | Label | Function | Module |
|---|---|---|---|
| `Total Salary Structure` | Total Salary Structure | Count | Payroll |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
