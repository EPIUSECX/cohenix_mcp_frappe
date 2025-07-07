# Master Control Plan: `Salary Slip`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee_and_payroll_tab` | Details | Tab Break | None |  |  |  | None | None |
| `section_break_6` | Employee Info | Section Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Read Only | None | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `designation` | Designation | Link | Designation |  |  | ✅ | None | None |
| `branch` | Branch | Link | Branch |  |  | ✅ | None | None |
| `column_break_obdl` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Submitted
Cancelled
Withheld |  |  | ✅ | None | None |
| `salary_withholding` | Salary Withholding | Link | Salary Withholding |  |  | ✅ | None | None |
| `salary_withholding_cycle` | Salary Withholding Cycle | Data | None |  | ✅ | ✅ | None | None |
| `currency` | Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `exchange_rate` | Exchange Rate | Float | None | ✅ | ✅ |  | 1.0 | None |
| `section_break_gsts` | Payroll Info | Section Break | None |  |  |  | None | None |
| `payroll_frequency` | Payroll Frequency | Select | 
Monthly
Fortnightly
Bimonthly
Weekly
Daily |  |  |  | None | None |
| `start_date` | Start Date | Date | None |  |  |  | None | None |
| `end_date` | End Date | Date | None |  |  |  | None | None |
| `column_break_ptcc` | None | Column Break | None |  |  |  | None | None |
| `salary_structure` | Salary Structure | Link | Salary Structure | ✅ |  | ✅ | None | None |
| `payroll_entry` | Payroll Entry | Link | Payroll Entry |  |  | ✅ | None | None |
| `mode_of_payment` | Mode Of Payment | Select | None |  |  | ✅ | None | None |
| `column_break_wyhp` | None | Column Break | None |  |  |  | None | None |
| `salary_slip_based_on_timesheet` | Salary Slip Based on Timesheet | Check | None |  |  | ✅ | 0 | None |
| `section_break_gerh` | None | Section Break | None |  |  |  | None | None |
| `deduct_tax_for_unclaimed_employee_benefits` | Deduct Tax For Unclaimed Employee Benefits | Check | None |  |  |  | 0 | None |
| `deduct_tax_for_unsubmitted_tax_exemption_proof` | Deduct Tax For Unsubmitted Tax Exemption Proof | Check | None |  |  |  | 0 | None |
| `payment_days_tab` | Payment Days | Tab Break | None |  |  |  | None | None |
| `total_working_days` | Working Days | Float | None | ✅ |  | ✅ | None | None |
| `unmarked_days` | Unmarked days | Float | None |  | ✅ |  | None | None |
| `leave_without_pay` | Leave Without Pay | Float | None |  |  |  | None | None |
| `column_break_geio` | None | Column Break | None |  |  |  | None | None |
| `absent_days` | Absent Days | Float | None |  |  | ✅ | None | None |
| `payment_days` | Payment Days | Float | None | ✅ |  | ✅ | None | None |
| `help_section` | None | Section Break | None |  |  |  | None | None |
| `payment_days_calculation_help` | Payment Days Calculation Help | HTML | None |  |  |  | None | None |
| `earnings_and_deductions_tab` | Earnings & Deductions | Tab Break | None |  |  |  | None | None |
| `timesheets_section` | Timesheet Details | Section Break | None |  |  |  | None | None |
| `timesheets` | Salary Slip Timesheet | Table | Salary Slip Timesheet |  |  |  | None | None |
| `column_break_ghjr` | None | Column Break | None |  |  |  | None | None |
| `total_working_hours` | Total Working Hours | Float | None |  |  |  | None | None |
| `hour_rate` | Hour Rate | Currency | currency |  |  |  | None | None |
| `base_hour_rate` | Hour Rate (Company Currency) | Currency | Company:company:default_currency |  |  |  | None | None |
| `earning_deduction_sb` | None | Section Break | None |  |  |  | None | None |
| `earnings` | Earnings | Table | Salary Detail |  |  |  | None | None |
| `column_break_k1jz` | None | Column Break | None |  |  |  | None | None |
| `deductions` | Deductions | Table | Salary Detail |  |  |  | None | None |
| `totals` | Totals | Section Break | None |  |  |  | None | None |
| `gross_pay` | Gross Pay | Currency | currency |  |  | ✅ | None | None |
| `base_gross_pay` | Gross Pay (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `gross_year_to_date` | Gross Year To Date | Currency | currency |  |  | ✅ | None | None |
| `base_gross_year_to_date` | Gross Year To Date(Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_25` | None | Column Break | None |  |  |  | None | None |
| `total_deduction` | Total Deduction | Currency | currency |  |  | ✅ | None | None |
| `base_total_deduction` | Total Deduction (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `net_pay_info` | Net Pay Info | Tab Break | None |  |  |  | None | None |
| `net_pay` | Net Pay | Currency | currency |  |  | ✅ | None | None |
| `base_net_pay` | Net Pay (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_dqnd` | None | Column Break | None |  |  |  | None | None |
| `year_to_date` | Year To Date | Currency | currency |  |  | ✅ | None | Total salary booked for this employee from the beginning of the year (payroll period or fiscal year) up to the current salary slip's end date. |
| `base_year_to_date` | Year To Date(Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `month_to_date` | Month To Date | Currency | currency |  |  | ✅ | None | Total salary booked for this employee from the beginning of the month up to the current salary slip's end date. |
| `base_month_to_date` | Month To Date(Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break_55` | None | Section Break | None |  |  |  | None | None |
| `total_in_words` | Total in words | Data | None |  |  | ✅ | None | None |
| `column_break_69` | None | Column Break | None |  |  |  | None | None |
| `base_total_in_words` | Total in words (Company Currency) | Data | None |  |  | ✅ | None | None |
| `income_tax_calculation_breakup_section` | Income Tax Breakup | Tab Break | None |  |  |  | None | None |
| `ctc` | CTC | Currency | currency |  |  | ✅ | None | None |
| `income_from_other_sources` | Income from Other Sources | Currency | currency |  |  | ✅ | None | None |
| `total_earnings` | Total Earnings | Currency | currency |  |  | ✅ | None | None |
| `column_break_0rsw` | None | Column Break | None |  |  |  | None | None |
| `non_taxable_earnings` | Non Taxable Earnings | Currency | currency |  |  | ✅ | None | None |
| `standard_tax_exemption_amount` | Standard Tax Exemption Amount | Currency | currency |  |  | ✅ | None | None |
| `tax_exemption_declaration` | Tax Exemption Declaration | Currency | currency |  |  | ✅ | None | None |
| `deductions_before_tax_calculation` | Deductions before tax calculation | Currency | currency |  |  | ✅ | None | None |
| `annual_taxable_amount` | Annual Taxable Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_35wb` | None | Column Break | None |  |  |  | None | None |
| `income_tax_deducted_till_date` | Income Tax Deducted Till Date | Currency | currency |  |  | ✅ | None | None |
| `current_month_income_tax` | Current Month Income Tax | Currency | currency |  |  | ✅ | None | None |
| `future_income_tax_deductions` | Future Income Tax | Currency | currency |  |  | ✅ | None | None |
| `total_income_tax` | Total Income Tax | Currency | currency |  |  | ✅ | None | None |
| `section_break_75` | Bank Details | Tab Break | None |  |  |  | None | None |
| `journal_entry` | Journal Entry | Link | Journal Entry |  |  |  | None | None |
| `amended_from` | Amended From | Link | Salary Slip |  |  | ✅ | None | None |
| `column_break_ieob` | None | Column Break | None |  |  |  | None | None |
| `bank_name` | Bank Name | Data | None |  |  |  | None | None |
| `bank_account_no` | Bank Account No | Data | None |  |  |  | None | None |
| `leave_details_section` | Leaves | Tab Break | None |  |  |  | None | None |
| `leave_details` | Leave Details | Table | Salary Slip Leave |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 12
- **Dynamic Link Fields:** 0
- **Table Fields:** 4

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_slip/salary_slip.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Salary Slip", {
	setup: function (frm) {
		$.each(["earnings", "deductions"], function (i, table_fieldname) {
			frm.get_field(table_fieldname).grid.editable_fields = [
				{ fieldname: "salary_component", columns: 6 },
				{ fieldname: "amount", columns: 4 },
			];
		});

		frm.fields_dict["timesheets"].grid.get_field("time_sheet").get_query = function () {
			return {
				filters: {
					employee: frm.doc.employee,
				},
			};
		};

		frm.set_query("salary_component", "earnings", function () {
			return {
				filters: {
					type: "earning",
				},
			};
		});

		frm.set_query("salary_component", "deductions", function () {
			return {
				filters: {
					type: "deduction",
				},
			};
		});

		frm.set_query("employee", function () {
			return {
				query: "erpnext.controllers.queries.employee_query",
			};
		});

		frm.trigger("set_payment_days_description");
	},

	validate: function (frm) {
		frm.trigger("set_payment_days_description");
	},

	start_date: function (frm) {
		if (frm.doc.start_date) {
			frm.trigger("set_end_date");
		}
	},

	end_date: function (frm) {
		frm.events.get_emp_and_working_day_details(frm);
	},

	set_end_date: function (frm) {
		frappe.call({
			method: "hrms.payroll.doctype.payroll_entry.payroll_entry.get_end_date",
			args: {
				frequency: frm.doc.payroll_frequency,
				start_date: frm.doc.start_date,
			},
			callback: function (r) {
				if (r.message) {
					frm.set_value("end_date", r.message.end_date);
				}
			},
		});
	},

	company: function (frm) {
		var company = locals[":Company"][frm.doc.company];
		if (!frm.doc.letter_head && company.default_letter_head) {
			frm.set_value("letter_head", company.default_letter_head);
		}
	},

	currency: function (frm) {
		frm.trigger("update_currency_changes");
	},

	update_currency_changes: function (frm) {
		frm.trigger("set_exchange_rate");
		frm.trigger("set_dynamic_labels");
	},

	set_dynamic_labels: function (frm) {
		if (frm.doc.employee && frm.doc.currency) {
			frappe.run_serially([
				() => frm.events.change_form_labels(frm),
				() => frm.events.change_grid_labels(frm),
				() => frm.refresh_fields(),
			]);
		}
	},

	set_exchange_rate: function (frm) {
		const company_currency = erpnext.get_currency(frm.doc.company);

		if (frm.doc.docstatus === 0) {
			if (frm.doc.currency) {
				var from_currency = frm.doc.currency;
				if (from_currency != company_currency) {
					frm.events.hide_loan_section(frm);
					frappe.call({
						method: "erpnext.setup.utils.get_exchange_rate",
						args: {
							from_currency: from_currency,
							to_currency: company_currency,
						},
						callback: function (r) {
							if (r.message) {
								frm.set_value("exchange_rate", flt(r.message));
								frm.set_df_property("exchange_rate", "hidden", 0);
								frm.set_df_property(
									"exchange_rate",
									"description",
									"1 " + frm.doc.currency + " = [?] " + company_currency,
								);
							}
						},
					});
				} else {
					frm.set_value("exchange_rate", 1.0);
					frm.set_df_property("exchange_rate", "hidden", 1);
					frm.set_df_property("exchange_rate", "description", "");
				}
			}
		}
	},

	exchange_rate: function (frm) {
		set_totals(frm);
	},

	hide_loan_section: function (frm) {
		frm.set_df_property("section_break_43", "hidden", 1);
	},

	change_form_labels: function (frm) {
		const company_currency = erpnext.get_currency(frm.doc.company);

		frm.set_currency_labels(
			[
				"base_hour_rate",
				"base_gross_pay",
				"base_total_deduction",
				"base_net_pay",
				"base_rounded_total",
				"base_total_in_words",
				"base_year_to_date",
				"base_month_to_date",
				"base_gross_year_to_date",
			],
			company_currency,
		);

		frm.set_currency_labels(
			[
				"hour_rate",
				"gross_pay",
				"total_deduction",
				"net_pay",
				"rounded_total",
				"total_in_words",
				"year_to_date",
				"month_to_date",
				"gross_year_to_date",
			],
			frm.doc.currency,
		);

		// toggle fields
		frm.toggle_display(
			[
				"exchange_rate",
				"base_hour_rate",
				"base_gross_pay",
				"base_total_deduction",
				"base_net_pay",
				"base_rounded_total",
				"base_total_in_words",
				"base_year_to_date",
				"base_month_to_date",
				"base_gross_year_to_date",
			],
			frm.doc.currency != company_currency,
		);
	},

	change_grid_labels: function (frm) {
		let fields = [
			"amount",
			"year_to_date",
			"default_amount",
			"additional_amount",
			"tax_on_flexible_benefit",
			"tax_on_additional_salary",
		];

		frm.set_currency_labels(fields, frm.doc.currency, "earnings");
		frm.set_currency_labels(fields, frm.doc.currency, "deductions");
	},

	refresh: function (frm) {
		frm.trigger("toggle_fields");

		var salary_detail_fields = [
			"formula",
			"abbr",
			"statistical_component",
			"variable_based_on_taxable_salary",
		];
		frm.fields_dict["earnings"].grid.set_column_disp(salary_detail_fields, false);
		frm.fields_dict["deductions"].grid.set_column_disp(salary_detail_fields, false);
		frm.trigger("set_dynamic_labels");
	},

	salary_slip_based_on_timesheet: function (frm) {
		frm.trigger("toggle_fields");
		frm.events.get_emp_and_working_day_details(frm);
	},

	payroll_frequency: function (frm) {
		frm.trigger("toggle_fields");
		frm.set_value("end_date", "");
	},

	employee: function (frm) {
		frm.events.get_emp_and_working_day_details(frm);
	},

	leave_without_pay: function (frm) {
		if (frm.doc.employee && frm.doc.start_date && frm.doc.end_date) {
			return frappe.call({
				method: "process_salary_based_on_working_days",
				doc: frm.doc,
				callback: function () {
					frm.refresh();
				},
			});
		}
	},

	toggle_fields: function (frm) {
		frm.toggle_display(
			["hourly_wages", "timesheets"],
			cint(frm.doc.salary_slip_based_on_timesheet) === 1,
		);
	},

	get_emp_and_working_day_details: function (frm) {
		if (frm.doc.employee) {
			return frappe.call({
				method: "get_emp_and_working_day_details",
				doc: frm.doc,
				callback: function (r) {
					frm.refresh();
					// triggering events explicitly because structure is set on the server-side
					// and currency is fetched from the structure
					frm.trigger("update_currency_changes");
				},
			});
		}
	},

	set_payment_days_description: function (frm) {
		if (frm.doc.docstatus !== 0) return;

		frappe.call("hrms.payroll.utils.get_payroll_settings_for_payment_days").then((r) => {
			const {
				payroll_based_on,
				consider_unmarked_attendance_as,
				include_holidays_in_total_working_days,
				consider_marked_attendance_on_holidays,
			} = r.message;

			const message = `
				<div class="small text-muted pb-3">
					${__("Note").bold()}: ${__("Payment Days calculations are based on these Payroll Settings")}:
					<br><br>${__("Payroll Based On")}: ${__(payroll_based_on).bold()}
					<br>${__("Consider Unmarked Attendance As")}: ${__(consider_unmarked_attendance_as).bold()}
					<br>${__("Consider Marked Attendance on Holidays")}:
					${
						cint(include_holidays_in_total_working_days) &&
						cint(consider_marked_attendance_on_holidays)
							? __("Enabled").bold()
							: __("Disabled").bold()
					}
					<br><br>
					${__("Click {0} to change the configuration and then resave salary slip", [
						frappe.utils.get_form_link(
							"Payroll Settings",
							"Payroll Settings",
							true,
							"<u>" + __("here") + "</u>",
						),
					])}
				</div>
			`;

			set_field_options("payment_days_calculation_help", message);
		});
	},
});

frappe.ui.form.on("Salary Slip Timesheet", {
	time_sheet: function (frm) {
		set_totals(frm);
	},
	timesheets_remove: function (frm) {
		set_totals(frm);
	},
});

var set_totals = function (frm) {
	if (frm.doc.docstatus === 0 && frm.doc.doctype === "Salary Slip") {
		if (frm.doc.earnings || frm.doc.deductions) {
			frappe.call({
				method: "set_totals",
				doc: frm.doc,
				callback: function () {
					frm.refresh_fields();
				},
			});
		}
	}
};

frappe.ui.form.on("Salary Detail", {
	amount: function (frm) {
		set_totals(frm);
	},

	earnings_remove: function (frm) {
		set_totals(frm);
	},

	deductions_remove: function (frm) {
		set_totals(frm);
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
						if (result.amount_based_on_formula === 1) {
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
		if (child.amount_based_on_formula === 1) {
			frappe.model.set_value(cdt, cdn, "amount", null);
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
| Name | Type | Module |
|---|---|---|
| `Income Tax Computation` | Script Report | Payroll |
| `Salary Payments Based On Payment Mode` | Script Report | Payroll |
| `Salary Payments via ECS` | Script Report | Payroll |
| `Professional Tax Deductions` | Script Report | Payroll |
| `Provident Fund Deductions` | Script Report | Payroll |
| `Income Tax Deductions` | Script Report | Payroll |
| `Salary Register` | Script Report | Payroll |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Designation Wise Salary(Last Month)` | Designation Wise Salary(Last Month) | Group By | Payroll |
| `Department Wise Salary(Last Month)` | Department Wise Salary(Last Month) | Group By | Payroll |
| `Outgoing Salary` | Outgoing Salary | Sum | Payroll |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Total Outgoing Salary(Last month)` | Total Outgoing Salary(Last month) | Sum | Payroll |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
