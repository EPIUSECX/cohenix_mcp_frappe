# Master Control Plan: `Payroll Entry`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-PRUN-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `select_payroll_period` | Overview | Tab Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `exchange_rate` | Exchange Rate | Float | None | ✅ |  |  | None | None |
| `payroll_payable_account` | Payroll Payable Account | Link | Account | ✅ |  |  | None | None |
| `status` | Status | Select | Draft
Submitted
Cancelled
Queued
Failed |  |  | ✅ | None | None |
| `section_break_cypo` | None | Section Break | None |  |  |  | None | None |
| `salary_slip_based_on_timesheet` | Salary Slip Based on Timesheet | Check | None |  |  |  | 0 | None |
| `payroll_frequency` | Payroll Frequency | Select | 
Monthly
Fortnightly
Bimonthly
Weekly
Daily |  |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | None | None |
| `end_date` | End Date | Date | None | ✅ |  |  | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `deduct_tax_for_unclaimed_employee_benefits` | Deduct Tax For Unclaimed Employee Benefits | Check | None |  |  |  | 0 | None |
| `deduct_tax_for_unsubmitted_tax_exemption_proof` | Deduct Tax For Unsubmitted Tax Exemption Proof | Check | None |  |  |  | 0 | None |
| `employees_tab` | Employees | Tab Break | None |  |  |  | None | None |
| `section_break_17` | Filter Employees | Section Break | None |  |  |  | None | None |
| `branch` | Branch | Link | Branch |  |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `designation` | Designation | Link | Designation |  |  |  | None | None |
| `grade` | Grade | Link | Employee Grade |  |  |  | None | None |
| `number_of_employees` | Number Of Employees | Int | None |  |  | ✅ | None | None |
| `section_break_24` | Employee Details | Section Break | None |  |  |  | None | None |
| `employees` | None | Table | Payroll Employee Detail |  |  |  | None | None |
| `section_break_26` | None | Section Break | None |  |  |  | None | None |
| `validate_attendance` | Validate Attendance | Check | None |  |  |  | 0 | None |
| `attendance_detail_html` | None | HTML | None |  |  |  | None | None |
| `accounting_dimensions_tab` | Accounting & Payment | Tab Break | None |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center | ✅ |  |  | :Company | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `account` | Payment Entry | Section Break | None |  |  |  | None | None |
| `payment_account` | Payment Account | Link | Account |  |  |  | None | Select Payment Account to make Bank Entry |
| `column_break_35` | None | Column Break | None |  |  |  | None | None |
| `bank_account` | Bank Account | Link | Bank Account |  |  |  | None | None |
| `salary_slips_created` | Salary Slips Created | Check | None |  | ✅ | ✅ | 0 | None |
| `salary_slips_submitted` | Salary Slips Submitted | Check | None |  | ✅ | ✅ | 0 | None |
| `failure_details_section` | Failure Details | Tab Break | None |  |  |  | None | None |
| `error_message` | Error Message | Small Text | None |  |  | ✅ | None | None |
| `section_break_41` | None | Section Break | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Payroll Entry |  |  | ✅ | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 12
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/payroll_entry/payroll_entry.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

var in_progress = false;

frappe.provide("erpnext.accounts.dimensions");

frappe.ui.form.on("Payroll Entry", {
	onload: function (frm) {
		frm.ignore_doctypes_on_cancel_all = ["Salary Slip", "Journal Entry"];

		if (!frm.doc.posting_date) {
			frm.doc.posting_date = frappe.datetime.nowdate();
		}
		frm.toggle_reqd(["payroll_frequency"], !frm.doc.salary_slip_based_on_timesheet);

		erpnext.accounts.dimensions.setup_dimension_filters(frm, frm.doctype);
		frm.events.department_filters(frm);
		frm.events.payroll_payable_account_filters(frm);

		frappe.realtime.off("completed_salary_slip_creation");
		frappe.realtime.on("completed_salary_slip_creation", function () {
			frm.reload_doc();
		});

		frappe.realtime.off("completed_salary_slip_submission");
		frappe.realtime.on("completed_salary_slip_submission", function () {
			frm.reload_doc();
		});
	},

	department_filters: function (frm) {
		frm.set_query("department", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
	},

	payroll_payable_account_filters: function (frm) {
		frm.set_query("payroll_payable_account", function () {
			return {
				filters: {
					company: frm.doc.company,
					root_type: "Liability",
					is_group: 0,
				},
			};
		});
	},

	refresh: function (frm) {
		if (frm.doc.status === "Queued") frm.page.btn_secondary.hide();

		if (frm.doc.docstatus === 0 && !frm.is_new()) {
			frm.page.clear_primary_action();
			frm.add_custom_button(__("Get Employees"), function () {
				frm.events.get_employee_details(frm);
			}).toggleClass("btn-primary", !(frm.doc.employees || []).length);
		}

		if (
			(frm.doc.employees || []).length &&
			!frappe.model.has_workflow(frm.doctype) &&
			!cint(frm.doc.salary_slips_created) &&
			frm.doc.docstatus != 2
		) {
			if (frm.doc.docstatus == 0 && !frm.is_new()) {
				frm.page.clear_primary_action();
				frm.page.set_primary_action(__("Create Salary Slips"), () => {
					frm.save("Submit").then(() => {
						frm.page.clear_primary_action();
						frm.refresh();
					});
				});
			} else if (frm.doc.docstatus == 1 && frm.doc.status == "Failed") {
				frm.add_custom_button(__("Create Salary Slips"), function () {
					frm.call("create_salary_slips");
				}).addClass("btn-primary");
			}
		}

		if (frm.doc.docstatus == 1) {
			if (frm.custom_buttons) frm.clear_custom_buttons();
			frm.events.add_context_buttons(frm);
		}

		if (frm.doc.status == "Failed" && frm.doc.error_message) {
			const issue = `<a id="jump_to_error" style="text-decoration: underline;">issue</a>`;
			let process = cint(frm.doc.salary_slips_created) ? "submission" : "creation";

			frm.dashboard.set_headline(
				__("Salary Slip {0} failed. You can resolve the {1} and retry {0}.", [
					process,
					issue,
				]),
			);

			$("#jump_to_error").on("click", (e) => {
				e.preventDefault();
				frm.scroll_to_field("error_message");
			});
		}
	},

	get_employee_details: function (frm) {
		return frappe
			.call({
				doc: frm.doc,
				method: "fill_employee_details",
				freeze: true,
				freeze_message: __("Fetching Employees"),
			})
			.then((r) => {
				if (r.docs?.[0]?.employees) {
					frm.dirty();
					frm.save();
				}

				frm.refresh();

				if (r.docs?.[0]?.validate_attendance) {
					render_employee_attendance(frm, r.message);
				}
				frm.scroll_to_field("employees");
			});
	},

	create_salary_slips: function (frm) {
		frm.call({
			doc: frm.doc,
			method: "run_doc_method",
			args: {
				method: "create_salary_slips",
				dt: "Payroll Entry",
				dn: frm.doc.name,
			},
		});
	},

	add_context_buttons: function (frm) {
		if (
			frm.doc.salary_slips_submitted ||
			(frm.doc.__onload && frm.doc.__onload.submitted_ss)
		) {
			frm.events.add_bank_entry_button(frm);
		} else if (frm.doc.salary_slips_created && frm.doc.status !== "Queued") {
			frm.add_custom_button(__("Submit Salary Slip"), function () {
				submit_salary_slip(frm);
			}).addClass("btn-primary");
		} else if (!frm.doc.salary_slips_created && frm.doc.status === "Failed") {
			frm.add_custom_button(__("Create Salary Slips"), function () {
				frm.trigger("create_salary_slips");
			}).addClass("btn-primary");
		}
	},

	add_bank_entry_button: function (frm) {
		frm.call("has_bank_entries").then((r) => {
			if (!r.message.has_bank_entries) {
				frm.add_custom_button(__("Make Bank Entry"), function () {
					make_bank_entry(frm);
				}).addClass("btn-primary");
			} else if (!r.message.has_bank_entries_for_withheld_salaries) {
				frm.add_custom_button(__("Release Withheld Salaries"), function () {
					make_bank_entry(frm, (for_withheld_salaries = 1));
				}).addClass("btn-primary");
			}
		});
	},

	setup: function (frm) {
		frm.add_fetch("company", "cost_center", "cost_center");

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

		frm.set_query("employee", "employees", () => {
			let error_fields = [];
			let mandatory_fields = ["company", "payroll_frequency", "start_date", "end_date"];

			let message = __("Mandatory fields required in {0}", [__(frm.doc.doctype)]);

			mandatory_fields.forEach((field) => {
				if (!frm.doc[field]) {
					error_fields.push(frappe.unscrub(field));
				}
			});

			if (error_fields && error_fields.length) {
				message = message + "<br><br><ul><li>" + error_fields.join("</li><li>") + "</ul>";
				frappe.throw({
					message: message,
					indicator: "red",
					title: __("Missing Fields"),
				});
			}

			return {
				query: "hrms.payroll.doctype.payroll_entry.payroll_entry.employee_query",
				filters: frm.events.get_employee_filters(frm),
			};
		});
	},

	get_employee_filters: function (frm) {
		let filters = {};

		let fields = [
			"company",
			"start_date",
			"end_date",
			"payroll_frequency",
			"payroll_payable_account",
			"currency",
			"department",
			"branch",
			"designation",
			"salary_slip_based_on_timesheet",
			"grade",
		];

		fields.forEach((field) => {
			if (frm.doc[field] || frm.doc[field] === 0) {
				filters[field] = frm.doc[field];
			}
		});

		if (frm.doc.employees) {
			let employees = frm.doc.employees.filter((d) => d.employee).map((d) => d.employee);
			if (employees && employees.length) {
				filters["employees"] = employees;
			}
		}
		return filters;
	},

	payroll_frequency: function (frm) {
		frm.trigger("set_start_end_dates").then(() => {
			frm.events.clear_employee_table(frm);
		});
	},

	company: function (frm) {
		frm.events.clear_employee_table(frm);
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
		frm.trigger("set_payable_account_and_currency");
	},

	set_payable_account_and_currency: function (frm) {
		frappe.db.get_value("Company", { name: frm.doc.company }, "default_currency", (r) => {
			frm.set_value("currency", r.default_currency);
		});
		frappe.db.get_value(
			"Company",
			{ name: frm.doc.company },
			"default_payroll_payable_account",
			(r) => {
				frm.set_value("payroll_payable_account", r.default_payroll_payable_account);
			},
		);
	},

	currency: function (frm) {
		var company_currency;
		if (!frm.doc.company) {
			company_currency = erpnext.get_currency(frappe.defaults.get_default("Company"));
		} else {
			company_currency = erpnext.get_currency(frm.doc.company);
		}
		if (frm.doc.currency) {
			if (company_currency != frm.doc.currency) {
				frappe.call({
					method: "erpnext.setup.utils.get_exchange_rate",
					args: {
						from_currency: frm.doc.currency,
						to_currency: company_currency,
					},
					callback: function (r) {
						frm.set_value("exchange_rate", flt(r.message));
						frm.set_df_property("exchange_rate", "hidden", 0);
						frm.set_df_property(
							"exchange_rate",
							"description",
							"1 " + frm.doc.currency + " = [?] " + company_currency,
						);
					},
				});
			} else {
				frm.set_value("exchange_rate", 1.0);
				frm.set_df_property("exchange_rate", "hidden", 1);
				frm.set_df_property("exchange_rate", "description", "");
			}
		}
	},

	department: function (frm) {
		frm.events.clear_employee_table(frm);
	},
	grade: function (frm) {
		frm.events.clear_employee_table(frm);
	},
	designation: function (frm) {
		frm.events.clear_employee_table(frm);
	},

	branch: function (frm) {
		frm.events.clear_employee_table(frm);
	},

	start_date: function (frm) {
		if (!in_progress && frm.doc.start_date) {
			frm.trigger("set_end_date");
		} else {
			// reset flag
			in_progress = false;
		}
		frm.events.clear_employee_table(frm);
	},

	project: function (frm) {
		frm.events.clear_employee_table(frm);
	},

	salary_slip_based_on_timesheet: function (frm) {
		frm.toggle_reqd(["payroll_frequency"], !frm.doc.salary_slip_based_on_timesheet);
	},

	set_start_end_dates: function (frm) {
		if (frm.doc.payroll_frequency) {
			frappe.call({
				method: "hrms.payroll.doctype.payroll_entry.payroll_entry.get_start_end_dates",
				args: {
					payroll_frequency: frm.doc.payroll_frequency,
					start_date: frm.doc.posting_date,
				},
				callback: function (r) {
					if (r.message) {
						in_progress = true;
						frm.set_value("start_date", r.message.start_date);
						frm.set_value("end_date", r.message.end_date);
					}
				},
			});
		}
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

	validate_attendance: function (frm) {
		if (frm.doc.validate_attendance && frm.doc.employees?.length > 0) {
			frappe.call({
				method: "get_employees_with_unmarked_attendance",
				args: {},
				callback: function (r) {
					render_employee_attendance(frm, r.message);
				},
				doc: frm.doc,
				freeze: true,
				freeze_message: __("Validating Employee Attendance..."),
			});
		} else {
			frm.fields_dict.attendance_detail_html.html("");
		}
	},

	clear_employee_table: function (frm) {
		frm.clear_table("employees");
		frm.refresh();
	},
});

// Submit salary slips

const submit_salary_slip = function (frm) {
	frappe.confirm(
		__(
			"This will submit Salary Slips and create accrual Journal Entry. Do you want to proceed?",
		),
		function () {
			frappe.call({
				method: "submit_salary_slips",
				args: {},
				doc: frm.doc,
				freeze: true,
				freeze_message: __("Submitting Salary Slips and creating Journal Entry..."),
			});
		},
		function () {
			if (frappe.dom.freeze_count) {
				frappe.dom.unfreeze();
			}
		},
	);
};

let make_bank_entry = function (frm, for_withheld_salaries = 0) {
	const doc = frm.doc;
	if (doc.payment_account) {
		return frappe.call({
			method: "run_doc_method",
			args: {
				method: "make_bank_entry",
				dt: "Payroll Entry",
				dn: frm.doc.name,
				args: { for_withheld_salaries: for_withheld_salaries },
			},
			callback: function () {
				frappe.set_route("List", "Journal Entry", {
					"Journal Entry Account.reference_name": frm.doc.name,
				});
			},
			freeze: true,
			freeze_message: __("Creating Payment Entries......"),
		});
	} else {
		frappe.msgprint(__("Payment Account is mandatory"));
		frm.scroll_to_field("payment_account");
	}
};

let render_employee_attendance = function (frm, data) {
	frm.fields_dict.attendance_detail_html.html(
		frappe.render_template("employees_with_unmarked_attendance", {
			data: data,
		}),
	);
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Bank Remittance` | Script Report | Payroll |



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
