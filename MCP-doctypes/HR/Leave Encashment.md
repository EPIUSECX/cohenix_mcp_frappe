# Master Control Plan: `Leave Encashment`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-ENC-.YYYY.-.#####`
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
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `leave_period` | Leave Period | Link | Leave Period | ✅ |  |  | None | None |
| `leave_type` | Leave Type | Link | Leave Type | ✅ |  |  | None | None |
| `leave_allocation` | Leave Allocation | Link | Leave Allocation |  |  | ✅ | None | None |
| `leave_balance` | Leave Balance | Float | None |  |  | ✅ | None | None |
| `column_break_cevy` | None | Column Break | None |  |  |  | None | None |
| `actual_encashable_days` | Actual Encashable Days | Float | None |  |  | ✅ | None | Number of leaves eligible for encashment based on leave type settings |
| `encashment_days` | Encashment Days | Float | None |  |  |  | None | None |
| `encashment_amount` | Encashment Amount | Currency | currency |  |  | ✅ | None | None |
| `accounting_section` | Accounting | Section Break | None |  |  |  | None | None |
| `pay_via_payment_entry` | Pay Via Payment Entry | Check | None |  |  |  | 0 | Process leave encashment via a separate Payment Entry instead of Salary Slip |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `payable_account` | Payable Account | Link | Account |  |  |  | None | None |
| `column_break_vdnb` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None |  |  |  | Today | None |
| `currency` | Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `paid_amount` | Paid Amount | Currency | None |  |  | ✅ | 0.0 | Amount paid against this encashment |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `payroll` | Payroll | Section Break | None |  |  |  | None | None |
| `encashment_date` | Encashment Date | Date | None |  |  |  | Today | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `additional_salary` | Additional Salary | Link | Additional Salary |  |  | ✅ | None | None |
| `section_break_svbb` | More Info | Section Break | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Leave Encashment |  |  | ✅ | None | None |
| `status` | Status | Select | Draft
Unpaid
Paid
Submitted
Cancelled |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 12
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_encashment/leave_encashment.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.accounts.dimensions");

frappe.ui.form.on("Leave Encashment", {
	onload: function (frm) {
		// Ignore cancellation of doctype on cancel all.
		frm.ignore_doctypes_on_cancel_all = ["Leave Ledger Entry"];
		erpnext.accounts.dimensions.setup_dimension_filters(frm, frm.doctype);
	},
	setup: function (frm) {
		frm.set_query("leave_type", function () {
			return {
				filters: {
					allow_encashment: 1,
				},
			};
		});
		frm.set_query("leave_period", function () {
			return {
				filters: {
					is_active: 1,
				},
			};
		});

		frm.set_query("payable_account", function () {
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
					company: frm.doc.company,
					account_currency: ["in", currencies],
				},
			};
		});
	},
	refresh: function (frm) {
		cur_frm.set_intro("");
		if (frm.doc.__islocal && !frappe.user_roles.includes("Employee")) {
			frm.set_intro(__("Fill the form and save it"));
		}

		if (
			frm.doc.docstatus === 1 &&
			frm.doc.pay_via_payment_entry == 1 &&
			frm.doc.status !== "Paid"
		) {
			frm.add_custom_button(
				__("Payment"),
				function () {
					frm.events.make_payment_entry(frm);
				},
				__("Create"),
			);
		}

		hrms.leave_utils.add_view_ledger_button(frm);
	},
	employee: function (frm) {
		if (frm.doc.employee) {
			frappe.run_serially([
				() => frm.trigger("get_employee_currency"),
				() => frm.trigger("get_leave_details_for_encashment"),
			]);
		}
	},
	company: function (frm) {
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
	},
	leave_type: function (frm) {
		frm.trigger("get_leave_details_for_encashment");
	},
	encashment_date: function (frm) {
		frm.trigger("get_leave_details_for_encashment");
	},
	get_leave_details_for_encashment: function (frm) {
		frm.set_value("actual_encashable_days", 0);
		frm.set_value("encashment_days", 0);

		if (frm.doc.docstatus === 0 && frm.doc.employee && frm.doc.leave_type) {
			return frappe.call({
				method: "get_leave_details_for_encashment",
				doc: frm.doc,
				callback: function (r) {
					frm.refresh_fields();
				},
			});
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
	make_payment_entry: function (frm) {
		return frappe.call({
			method: "hrms.overrides.employee_payment_entry.get_payment_entry_for_employee",
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
