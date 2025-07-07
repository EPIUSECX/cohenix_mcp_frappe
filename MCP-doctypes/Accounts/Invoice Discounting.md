# Master Control Plan: `Invoice Discounting`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `ACC-INV-DISC-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `loan_start_date` | Loan Start Date | Date | None |  |  |  | None | None |
| `loan_period` | Loan Period (Days) | Int | None |  |  |  | None | None |
| `loan_end_date` | Loan End Date | Date | None |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Sanctioned
Disbursed
Settled
Cancelled |  |  | ✅ | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `invoices` | Invoices | Table | Discounted Invoice | ✅ |  |  | None | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `total_amount` | Total Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `bank_charges` | Bank Charges | Currency | Company:company:default_currency |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `short_term_loan` | Short Term Loan Account | Link | Account | ✅ |  |  | None | None |
| `bank_account` | Bank Account | Link | Account | ✅ |  |  | None | None |
| `bank_charges_account` | Bank Charges Account | Link | Account | ✅ |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `accounts_receivable_credit` | Accounts Receivable Credit Account | Link | Account | ✅ |  |  | None | None |
| `accounts_receivable_discounted` | Accounts Receivable Discounted Account | Link | Account | ✅ |  |  | None | None |
| `accounts_receivable_unpaid` | Accounts Receivable Unpaid Account | Link | Account | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Invoice Discounting |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/invoice_discounting/invoice_discounting.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Invoice Discounting", {
	setup: (frm) => {
		frm.set_query("sales_invoice", "invoices", (doc) => {
			return {
				filters: {
					docstatus: 1,
					company: doc.company,
					outstanding_amount: [">", 0],
				},
			};
		});

		frm.events.filter_accounts("bank_account", frm, [["account_type", "=", "Bank"]]);
		frm.events.filter_accounts("bank_charges_account", frm, [["root_type", "=", "Expense"]]);
		frm.events.filter_accounts("short_term_loan", frm, [["root_type", "=", "Liability"]]);
		frm.events.filter_accounts("accounts_receivable_discounted", frm, [
			["account_type", "=", "Receivable"],
		]);
		frm.events.filter_accounts("accounts_receivable_credit", frm, [["account_type", "=", "Receivable"]]);
		frm.events.filter_accounts("accounts_receivable_unpaid", frm, [["account_type", "=", "Receivable"]]);
	},

	filter_accounts: (fieldname, frm, addl_filters) => {
		let filters = [
			["company", "=", frm.doc.company],
			["is_group", "=", 0],
		];
		if (addl_filters) {
			filters = $.merge(filters, addl_filters);
		}

		frm.set_query(fieldname, () => {
			return { filters: filters };
		});
	},

	refresh_filters: (frm) => {
		let invoice_accounts = Object.keys(frm.doc.invoices).map(function (key) {
			return frm.doc.invoices[key].debit_to;
		});
		let filters = [
			["account_type", "=", "Receivable"],
			["name", "not in", invoice_accounts],
		];
		frm.events.filter_accounts("accounts_receivable_credit", frm, filters);
		frm.events.filter_accounts("accounts_receivable_discounted", frm, filters);
		frm.events.filter_accounts("accounts_receivable_unpaid", frm, filters);
	},

	refresh: (frm) => {
		frm.events.show_general_ledger(frm);

		if (frm.doc.docstatus === 0) {
			frm.add_custom_button(__("Get Invoices"), function () {
				frm.events.get_invoices(frm);
			});
		}

		if (frm.doc.docstatus === 1 && frm.doc.status !== "Settled") {
			if (frm.doc.status == "Sanctioned") {
				frm.add_custom_button(__("Disburse Loan"), function () {
					frm.events.create_disbursement_entry(frm);
				}).addClass("btn-primary");
			}
			if (frm.doc.status == "Disbursed") {
				frm.add_custom_button(__("Close Loan"), function () {
					frm.events.close_loan(frm);
				}).addClass("btn-primary");
			}
		}
	},

	loan_start_date: (frm) => {
		frm.events.set_end_date(frm);
	},

	loan_period: (frm) => {
		frm.events.set_end_date(frm);
	},

	set_end_date: (frm) => {
		if (frm.doc.loan_start_date && frm.doc.loan_period) {
			let end_date = frappe.datetime.add_days(frm.doc.loan_start_date, frm.doc.loan_period);
			frm.set_value("loan_end_date", end_date);
		}
	},

	validate: (frm) => {
		frm.events.calculate_total_amount(frm);
	},

	calculate_total_amount: (frm) => {
		let total_amount = 0.0;
		for (let row of frm.doc.invoices || []) {
			total_amount += flt(row.outstanding_amount);
		}
		frm.set_value("total_amount", total_amount);
	},
	get_invoices: (frm) => {
		var d = new frappe.ui.Dialog({
			title: __("Get Invoices based on Filters"),
			fields: [
				{
					label: "Customer",
					fieldname: "customer",
					fieldtype: "Link",
					options: "Customer",
				},
				{
					label: "From Date",
					fieldname: "from_date",
					fieldtype: "Date",
				},
				{
					label: "To Date",
					fieldname: "to_date",
					fieldtype: "Date",
				},
				{
					fieldname: "col_break",
					fieldtype: "Column Break",
				},
				{
					label: "Min Amount",
					fieldname: "min_amount",
					fieldtype: "Currency",
				},
				{
					label: "Max Amount",
					fieldname: "max_amount",
					fieldtype: "Currency",
				},
			],
			primary_action: function () {
				var data = d.get_values();

				frappe.call({
					method: "erpnext.accounts.doctype.invoice_discounting.invoice_discounting.get_invoices",
					args: {
						filters: data,
					},
					callback: function (r) {
						if (!r.exc) {
							d.hide();
							$.each(r.message, function (i, v) {
								frm.doc.invoices = frm.doc.invoices.filter((row) => row.sales_invoice);
								let row = frm.add_child("invoices");
								$.extend(row, v);
								frm.events.refresh_filters(frm);
							});
							refresh_field("invoices");
						}
					},
				});
			},
			primary_action_label: __("Get Invoices"),
		});
		d.show();
	},

	create_disbursement_entry: (frm) => {
		frappe.call({
			method: "create_disbursement_entry",
			doc: frm.doc,
			callback: function (r) {
				if (!r.exc) {
					var doclist = frappe.model.sync(r.message);
					frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
				}
			},
		});
	},

	close_loan: (frm) => {
		frappe.call({
			method: "close_loan",
			doc: frm.doc,
			callback: function (r) {
				if (!r.exc) {
					var doclist = frappe.model.sync(r.message);
					frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
				}
			},
		});
	},

	show_general_ledger: (frm) => {
		if (frm.doc.docstatus > 0) {
			frm.add_custom_button(
				__("Accounting Ledger"),
				function () {
					frappe.route_options = {
						voucher_no: frm.doc.name,
						from_date: frm.doc.posting_date,
						to_date: moment(frm.doc.modified).format("YYYY-MM-DD"),
						company: frm.doc.company,
						categorize_by: "Categorize by Voucher (Consolidated)",
						show_cancelled_entries: frm.doc.docstatus === 2,
					};
					frappe.set_route("query-report", "General Ledger");
				},
				__("View")
			);
		}
	},
});

frappe.ui.form.on("Discounted Invoice", {
	sales_invoice: (frm) => {
		frm.events.calculate_total_amount(frm);
		frm.events.refresh_filters(frm);
	},
	invoices_remove: (frm) => {
		frm.events.calculate_total_amount(frm);
		frm.events.refresh_filters(frm);
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
