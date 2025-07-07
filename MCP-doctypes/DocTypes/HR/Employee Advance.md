# Master Control Plan: `Employee Advance`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Employee | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Expense Approver | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | HR-EAD-.YYYY.- |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Read Only | None |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `company` | Company | Link | Company | ✅ |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `currency_section` | Currency  | Section Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `column_break_crso` | None | Column Break | None |  |  |  | None | None |
| `exchange_rate` | Exchange Rate | Float | None | ✅ |  |  | None | None |
| `section_break_8` | Purpose & Amount | Section Break | None |  |  |  | None | None |
| `purpose` | Purpose | Small Text | None | ✅ |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `advance_amount` | Advance Amount | Currency | currency | ✅ |  |  | None | Amount of expense |
| `paid_amount` | Paid Amount | Currency | currency |  |  | ✅ | None | Amount that has been paid against this advance |
| `pending_amount` | Pending Amount | Currency | currency |  |  | ✅ | None | Pending (unpaid) amount from previous advances |
| `claimed_amount` | Claimed Amount | Currency | currency |  |  | ✅ | None | Amount claimed via Expense Claim |
| `return_amount` | Returned Amount | Currency | currency |  |  | ✅ | None | Amount scheduled for deduction via salary |
| `section_break_7` | Accounting | Section Break | None |  |  |  | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `advance_account` | Advance Account | Link | Account |  |  |  | None | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  |  | None | None |
| `column_break_nhlv` | None | Column Break | None |  |  |  | None | None |
| `repay_unclaimed_amount_from_salary` | Repay Unclaimed Amount from Salary | Check | None |  |  |  | 0 | None |
| `more_info_section` | More Info | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Paid
Unpaid
Claimed
Returned
Partly Claimed and Returned
Cancelled |  |  | ✅ | None | None |
| `column_break_kimx` | None | Column Break | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Employee Advance |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_advance/employee_advance.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Advance", {
	setup: function (frm) {
		frm.set_query("employee", function () {
			return {
				filters: {
					status: "Active",
				},
			};
		});

		frm.set_query("advance_account", function () {
			if (!frm.doc.employee) {
				frappe.msgprint(__("Please select employee first"));
			}
			let company_currency = erpnext.get_currency(frm.doc.company);
			let currencies = [company_currency];
			if (frm.doc.currency && frm.doc.currency != company_currency) {
				currencies.push(frm.doc.currency);
			}

			return {
				filters: {
					root_type: "Asset",
					is_group: 0,
					company: frm.doc.company,
					account_currency: ["in", currencies],
				},
			};
		});

		frm.set_query("salary_component", function () {
			return {
				filters: {
					type: "Deduction",
				},
			};
		});
	},

	refresh: function (frm) {
		if (
			frm.doc.docstatus === 1 &&
			flt(frm.doc.paid_amount) < flt(frm.doc.advance_amount) &&
			frappe.model.can_create("Payment Entry")
		) {
			frm.add_custom_button(
				__("Payment"),
				function () {
					frm.events.make_payment_entry(frm);
				},
				__("Create"),
			);
		} else if (
			frm.doc.docstatus === 1 &&
			flt(frm.doc.claimed_amount) < flt(frm.doc.paid_amount) - flt(frm.doc.return_amount) &&
			frappe.model.can_create("Expense Claim")
		) {
			frm.add_custom_button(
				__("Expense Claim"),
				function () {
					frm.events.make_expense_claim(frm);
				},
				__("Create"),
			);
		}

		if (
			frm.doc.docstatus === 1 &&
			flt(frm.doc.claimed_amount) < flt(frm.doc.paid_amount) - flt(frm.doc.return_amount)
		) {
			if (
				frm.doc.repay_unclaimed_amount_from_salary == 0 &&
				frappe.model.can_create("Journal Entry")
			) {
				frm.add_custom_button(
					__("Return"),
					function () {
						frm.trigger("make_return_entry");
					},
					__("Create"),
				);
			} else if (
				frm.doc.repay_unclaimed_amount_from_salary == 1 &&
				frappe.model.can_create("Additional Salary")
			) {
				frm.add_custom_button(
					__("Deduction from Salary"),
					function () {
						frm.events.make_deduction_via_additional_salary(frm);
					},
					__("Create"),
				);
			}
		}
	},

	make_deduction_via_additional_salary: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.employee_advance.employee_advance.create_return_through_additional_salary",
			args: {
				doc: frm.doc,
			},
			callback: function (r) {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	},

	make_payment_entry: function (frm) {
		let method = "hrms.overrides.employee_payment_entry.get_payment_entry_for_employee";
		if (frm.doc.__onload && frm.doc.__onload.make_payment_via_journal_entry) {
			method = "hrms.hr.doctype.employee_advance.employee_advance.make_bank_entry";
		}
		return frappe.call({
			method: method,
			args: {
				dt: frm.doc.doctype,
				dn: frm.doc.name,
			},
			callback: function (r) {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	},

	make_expense_claim: function (frm) {
		return frappe.call({
			method: "hrms.hr.doctype.expense_claim.expense_claim.get_expense_claim",
			args: {
				employee_name: frm.doc.employee,
				company: frm.doc.company,
				employee_advance_name: frm.doc.name,
				posting_date: frm.doc.posting_date,
				paid_amount: frm.doc.paid_amount,
				claimed_amount: frm.doc.claimed_amount,
				return_amount: frm.doc.return_amount,
			},
			callback: function (r) {
				const doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	},

	make_return_entry: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.employee_advance.employee_advance.make_return_entry",
			args: {
				employee: frm.doc.employee,
				company: frm.doc.company,
				employee_advance_name: frm.doc.name,
				return_amount: flt(frm.doc.paid_amount - frm.doc.claimed_amount),
				advance_account: frm.doc.advance_account,
				mode_of_payment: frm.doc.mode_of_payment,
				currency: frm.doc.currency,
				exchange_rate: frm.doc.exchange_rate,
			},
			callback: function (r) {
				const doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	},

	employee: function (frm) {
		if (frm.doc.employee) frm.trigger("get_employee_currency");
	},

	get_employee_currency: function (frm) {
		frappe.db.get_value(
			"Salary Structure Assignment",
			{ employee: frm.doc.employee, docstatus: 1 },
			"currency",
			(r) => {
				if (r.currency) frm.set_value("currency", r.currency);
				else frm.set_value("currency", erpnext.get_currency(frm.doc.company));
				frm.refresh_fields();
			},
		);
	},

	currency: function (frm) {
		if (frm.doc.currency) {
			var from_currency = frm.doc.currency;
			var company_currency;
			if (!frm.doc.company) {
				company_currency = erpnext.get_currency(frappe.defaults.get_default("Company"));
			} else {
				company_currency = erpnext.get_currency(frm.doc.company);
			}
			if (from_currency != company_currency) {
				frm.events.set_exchange_rate(frm, from_currency, company_currency);
			} else {
				frm.set_value("exchange_rate", 1.0);
				frm.set_df_property("exchange_rate", "hidden", 1);
				frm.set_df_property("exchange_rate", "description", "");
			}
			frm.refresh_fields();
		}
	},

	set_exchange_rate: function (frm, from_currency, company_currency) {
		frappe.call({
			method: "erpnext.setup.utils.get_exchange_rate",
			args: {
				from_currency: from_currency,
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
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Employee Advance Summary` | Script Report | HR |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Employee Advance Status` | Employee Advance Status | Group By | HR |



### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
