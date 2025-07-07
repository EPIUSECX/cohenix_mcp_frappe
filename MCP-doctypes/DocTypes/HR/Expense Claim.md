# Master Control Plan: `Expense Claim`

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
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Expense Approver | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Expense Approver | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `expenses_and_advances_tab` | Expenses & Advances | Tab Break | None |  |  |  | None | None |
| `naming_series` | Series | Select | HR-EXP-.YYYY.- | ✅ |  |  | None | None |
| `employee` | From Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `expense_approver` | Expense Approver | Link | User |  |  |  | None | None |
| `approval_status` | Approval Status | Select | Draft
Approved
Rejected |  |  |  | Draft | None |
| `expense_details` | None | Section Break | None |  |  |  | None | None |
| `expenses` | Expenses | Table | Expense Claim Detail | ✅ |  |  | None | None |
| `taxes_and_charges_sb` | Taxes & Charges | Section Break | Simple |  |  |  | None | None |
| `taxes` | Expense Taxes and Charges | Table | Expense Taxes and Charges |  |  |  | None | None |
| `advance_payments_sb` | Advance Payments | Section Break | None |  |  |  | None | None |
| `advances` | Advances | Table | Expense Claim Advance |  |  |  | None | None |
| `transactions_section` | Totals | Section Break | None |  |  |  | None | None |
| `total_sanctioned_amount` | Total Sanctioned Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `total_advance_amount` | Total Advance Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `total_claimed_amount` | Total Claimed Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `total_amount_reimbursed` | Total Amount Reimbursed | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `accounting_details_tab` | Accounting | Tab Break | None |  |  |  | None | None |
| `accounting_details` | Accounting Details | Section Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `is_paid` | Is Paid | Check | None |  |  |  | 0 | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  |  | None | None |
| `payable_account` | Payable Account | Link | Account |  |  |  | None | None |
| `column_break_24` | None | Column Break | None |  |  |  | None | None |
| `clearance_date` | Clearance Date | Date | None |  |  |  | None | None |
| `remark` | Remark | Small Text | None |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `more_info_tab` | More Info | Tab Break | None |  |  |  | None | None |
| `more_details` | None | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Paid
Unpaid
Rejected
Submitted
Cancelled |  |  | ✅ | Draft | None |
| `task` | Task | Link | Task |  |  |  | None | None |
| `amended_from` | Amended From | Link | Expense Claim |  |  | ✅ | None | None |
| `column_break_xdzn` | None | Column Break | None |  |  |  | None | None |
| `delivery_trip` | Delivery Trip | Link | Delivery Trip |  |  |  | None | None |
| `vehicle_log` | Vehicle Log | Link | Vehicle Log |  |  | ✅ | None | None |
| `dashboard_tab` | Dashboard | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 12
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/expense_claim/expense_claim.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("hrms.hr");
frappe.provide("erpnext.accounts.dimensions");

frappe.ui.form.on("Expense Claim", {
	setup: function (frm) {
		frm.set_query("employee_advance", "advances", function () {
			return {
				filters: [
					["docstatus", "=", 1],
					["employee", "=", frm.doc.employee],
					["paid_amount", ">", 0],
					["status", "not in", ["Claimed", "Returned", "Partly Claimed and Returned"]],
				],
			};
		});

		frm.set_query("expense_approver", function () {
			return {
				query: "hrms.hr.doctype.department_approver.department_approver.get_approvers",
				filters: {
					employee: frm.doc.employee,
					doctype: frm.doc.doctype,
				},
			};
		});

		frm.set_query("account_head", "taxes", function () {
			return {
				filters: [
					["company", "=", frm.doc.company],
					[
						"account_type",
						"in",
						["Tax", "Chargeable", "Income Account", "Expenses Included In Valuation"],
					],
				],
			};
		});

		frm.set_query("payable_account", function () {
			return {
				filters: {
					report_type: "Balance Sheet",
					account_type: "Payable",
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("task", function () {
			return {
				filters: {
					project: frm.doc.project,
				},
			};
		});

		frm.set_query("employee", function () {
			return {
				query: "erpnext.controllers.queries.employee_query",
			};
		});

		frm.set_query("department", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
	},

	onload: function (frm) {
		erpnext.accounts.dimensions.setup_dimension_filters(frm, frm.doctype);

		if (frm.doc.docstatus == 0) {
			return frappe.call({
				method: "hrms.hr.doctype.leave_application.leave_application.get_mandatory_approval",
				args: {
					doctype: frm.doc.doctype,
				},
				callback: function (r) {
					if (!r.exc && r.message) {
						frm.toggle_reqd("expense_approver", true);
					}
				},
			});
		}
	},

	refresh: function (frm) {
		frm.trigger("toggle_fields");
		frm.trigger("add_ledger_buttons");

		if (
			frm.doc.docstatus === 1 &&
			frm.doc.status !== "Paid" &&
			frappe.model.can_create("Payment Entry")
		) {
			frm.add_custom_button(
				__("Payment"),
				function () {
					frm.events.make_payment_entry(frm);
				},
				__("Create"),
			);
		}
	},

	validate: function (frm) {
		frm.trigger("calculate_total");
	},

	add_ledger_buttons: function (frm) {
		if (frm.doc.docstatus > 0 && frm.doc.approval_status !== "Rejected") {
			frm.add_custom_button(
				__("Accounting Ledger"),
				function () {
					frappe.route_options = {
						voucher_no: frm.doc.name,
						company: frm.doc.company,
						from_date: frm.doc.posting_date,
						to_date: moment(frm.doc.modified).format("YYYY-MM-DD"),
						group_by: "",
						show_cancelled_entries: frm.doc.docstatus === 2,
					};
					frappe.set_route("query-report", "General Ledger");
				},
				__("View"),
			);
		}

		if (!frm.doc.__islocal && frm.doc.docstatus === 1) {
			let entry_doctype, entry_reference_doctype, entry_reference_name;
			if (frm.doc.__onload.make_payment_via_journal_entry) {
				entry_doctype = "Journal Entry";
				entry_reference_doctype = "Journal Entry Account.reference_type";
				entry_reference_name = "Journal Entry.reference_name";
			} else {
				entry_doctype = "Payment Entry";
				entry_reference_doctype = "Payment Entry Reference.reference_doctype";
				entry_reference_name = "Payment Entry Reference.reference_name";
			}

			if (
				cint(frm.doc.total_amount_reimbursed) > 0 &&
				frappe.model.can_read(entry_doctype)
			) {
				// nosemgrep: frappe-semgrep-rules.rules.frappe-cur-frm-usage
				frm.add_custom_button(
					__("Bank Entries"),
					function () {
						frappe.route_options = {
							party_type: "Employee",
							party: frm.doc.employee,
							company: frm.doc.company,
						};
						frappe.set_route("List", entry_doctype);
					},
					__("View"),
				);
			}
		}
	},

	calculate_total: function (frm) {
		let total_claimed_amount = 0;
		let total_sanctioned_amount = 0;

		frm.doc.expenses.forEach((row) => {
			total_claimed_amount += row.amount;
			total_sanctioned_amount += row.sanctioned_amount;
		});

		frm.set_value(
			"total_claimed_amount",
			flt(total_claimed_amount, precision("total_claimed_amount")),
		);
		frm.set_value(
			"total_sanctioned_amount",
			flt(total_sanctioned_amount, precision("total_sanctioned_amount")),
		);
	},

	calculate_grand_total: function (frm) {
		var grand_total =
			flt(frm.doc.total_sanctioned_amount) +
			flt(frm.doc.total_taxes_and_charges) -
			flt(frm.doc.total_advance_amount);
		frm.set_value("grand_total", grand_total);
		frm.refresh_fields();
	},

	grand_total: function (frm) {
		frm.trigger("update_employee_advance_claimed_amount");
	},

	update_employee_advance_claimed_amount: function (frm) {
		let amount_to_be_allocated = frm.doc.grand_total;
		$.each(frm.doc.advances || [], function (i, advance) {
			if (amount_to_be_allocated >= advance.unclaimed_amount - advance.return_amount) {
				advance.allocated_amount =
					frm.doc.advances[i].unclaimed_amount - frm.doc.advances[i].return_amount;
				amount_to_be_allocated -= advance.allocated_amount;
			} else {
				advance.allocated_amount = amount_to_be_allocated;
				amount_to_be_allocated = 0;
			}
			frm.refresh_field("advances");
		});
	},
	make_payment_entry: function (frm) {
		let method = "hrms.overrides.employee_payment_entry.get_payment_entry_for_employee";
		if (frm.doc.__onload && frm.doc.__onload.make_payment_via_journal_entry) {
			method = "hrms.hr.doctype.expense_claim.expense_claim.make_bank_entry";
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

	company: function (frm) {
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
		var expenses = frm.doc.expenses;
		for (var i = 0; i < expenses.length; i++) {
			var expense = expenses[i];
			if (!expense.expense_type) {
				continue;
			}
			frappe.call({
				method: "hrms.hr.doctype.expense_claim.expense_claim.get_expense_claim_account_and_cost_center",
				args: {
					expense_claim_type: expense.expense_type,
					company: frm.doc.company,
				},
				callback: function (r) {
					if (r.message) {
						expense.default_account = r.message.account;
						expense.cost_center = r.message.cost_center;
					}
				},
			});
		}
	},

	is_paid: function (frm) {
		frm.trigger("toggle_fields");
	},

	toggle_fields: function (frm) {
		frm.toggle_reqd("mode_of_payment", frm.doc.is_paid);
	},

	employee: function (frm) {
		frm.events.get_advances(frm);
	},

	cost_center: function (frm) {
		frm.events.set_child_cost_center(frm);
	},

	validate: function (frm) {
		frm.events.set_child_cost_center(frm);
	},

	set_child_cost_center: function (frm) {
		(frm.doc.expenses || []).forEach(function (d) {
			if (!d.cost_center) {
				d.cost_center = frm.doc.cost_center;
			}
		});
	},

	get_taxes: function (frm) {
		if (!frm.doc.taxes.length) return;

		frappe.call({
			method: "calculate_taxes",
			doc: frm.doc,
			callback: () => {
				refresh_field("taxes");
				frm.trigger("update_employee_advance_claimed_amount");
			},
		});
	},

	get_advances: function (frm) {
		frappe.model.clear_table(frm.doc, "advances");
		if (frm.doc.employee) {
			return frappe.call({
				method: "hrms.hr.doctype.expense_claim.expense_claim.get_advances",
				args: {
					employee: frm.doc.employee,
				},
				callback: function (r, rt) {
					if (r.message) {
						$.each(r.message, function (i, d) {
							var row = frappe.model.add_child(
								frm.doc,
								"Expense Claim Advance",
								"advances",
							);
							row.employee_advance = d.name;
							row.posting_date = d.posting_date;
							row.advance_account = d.advance_account;
							row.advance_paid = d.paid_amount;
							row.unclaimed_amount = flt(d.paid_amount) - flt(d.claimed_amount);
							row.return_amount = flt(d.return_amount);
							row.allocated_amount = get_allocation_amount(
								flt(d.paid_amount),
								flt(d.claimed_amount),
								flt(d.return_amount),
							);
						});
						refresh_field("advances");
					}
				},
			});
		}
	},
});

frappe.ui.form.on("Expense Claim Detail", {
	expense_type: function (frm, cdt, cdn) {
		var d = locals[cdt][cdn];
		if (!frm.doc.company) {
			d.expense_type = "";
			frappe.msgprint(__("Please set the Company"));
			this.frm.refresh_fields();
			return;
		}

		if (!d.expense_type) {
			return;
		}
		return frappe.call({
			method: "hrms.hr.doctype.expense_claim.expense_claim.get_expense_claim_account_and_cost_center",
			args: {
				expense_claim_type: d.expense_type,
				company: frm.doc.company,
			},
			callback: function (r) {
				if (r.message) {
					d.default_account = r.message.account;
					d.cost_center = r.message.cost_center;
				}
			},
		});
	},

	amount: function (frm, cdt, cdn) {
		var child = locals[cdt][cdn];
		frappe.model.set_value(cdt, cdn, "sanctioned_amount", child.amount);
	},

	sanctioned_amount: function (frm, cdt, cdn) {
		frm.trigger("calculate_total");
		frm.trigger("get_taxes");
		frm.trigger("calculate_grand_total");
	},

	cost_center: function (frm, cdt, cdn) {
		erpnext.utils.copy_value_in_all_rows(frm.doc, cdt, cdn, "expenses", "cost_center");
	},
});

frappe.ui.form.on("Expense Claim Advance", {
	employee_advance: function (frm, cdt, cdn) {
		var child = locals[cdt][cdn];
		if (!frm.doc.employee) {
			frappe.msgprint(__("Select an employee to get the employee advance."));
			frm.doc.advances = [];
			refresh_field("advances");
		} else {
			return frappe.call({
				method: "hrms.hr.doctype.expense_claim.expense_claim.get_advances",
				args: {
					employee: frm.doc.employee,
					advance_id: child.employee_advance,
				},
				callback: function (r, rt) {
					if (r.message) {
						child.employee_advance = r.message[0].name;
						child.posting_date = r.message[0].posting_date;
						child.advance_account = r.message[0].advance_account;
						child.advance_paid = r.message[0].paid_amount;
						child.unclaimed_amount =
							flt(r.message[0].paid_amount) - flt(r.message[0].claimed_amount);
						child.return_amount = flt(r.message[0].return_amount);
						child.allocated_amount = get_allocation_amount(
							flt(r.message[0].paid_amount),
							flt(r.message[0].claimed_amount),
							flt(r.message[0].return_amount),
						);
						frm.trigger("calculate_grand_total");
						refresh_field("advances");
					}
				},
			});
		}
	},
});

frappe.ui.form.on("Expense Taxes and Charges", {
	account_head: function (frm, cdt, cdn) {
		var child = locals[cdt][cdn];
		if (child.account_head && !child.description) {
			// set description from account head
			child.description = child.account_head.split(" - ").slice(0, -1).join(" - ");
			refresh_field("taxes");
		}
	},

	calculate_total_tax: function (frm, cdt, cdn) {
		var child = locals[cdt][cdn];
		child.total = flt(frm.doc.total_sanctioned_amount) + flt(child.tax_amount);
		frm.trigger("calculate_tax_amount", cdt, cdn);
	},

	calculate_tax_amount: function (frm) {
		frm.doc.total_taxes_and_charges = 0;
		(frm.doc.taxes || []).forEach(function (d) {
			frm.doc.total_taxes_and_charges += d.tax_amount;
		});
		frm.trigger("calculate_grand_total");
	},

	rate: function (frm, cdt, cdn) {
		var child = locals[cdt][cdn];
		if (!child.amount) {
			child.tax_amount = flt(frm.doc.total_sanctioned_amount) * (flt(child.rate) / 100);
		}
		frm.trigger("calculate_total_tax", cdt, cdn);
	},

	tax_amount: function (frm, cdt, cdn) {
		frm.trigger("calculate_total_tax", cdt, cdn);
	},
});

function get_allocation_amount(paid_amount, claimed_amount, return_amount) {
	return paid_amount - (claimed_amount + return_amount);
}

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Unpaid Expense Claim` | Script Report | HR |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Department wise Expense Claims` | Department wise Expense Claims | Group By | HR |
| `Expense Claims` | Expense Claims | Sum | HR |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Rejected Claims (This Month)` | Rejected Claims (This Month) | Count | HR |
| `Approved Claims (This Month)` | Approved Claims (This Month) | Count | HR |
| `Expense Claims (This Month)` | Expense Claims (This Month) | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
