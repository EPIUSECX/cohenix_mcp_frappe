# Master Control Plan: `Payment Reconciliation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `party_type` | Party Type | Link | DocType | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `party` | Party | Dynamic Link | party_type | ✅ |  |  | None | None |
| `receivable_payable_account` | Receivable / Payable Account | Link | Account | ✅ |  |  | None | None |
| `default_advance_account` | Default Advance Account | Link | Account |  |  |  | None | Only 'Payment Entries' made against this advance account are supported. |
| `col_break1` | Filters | Section Break | None |  |  |  | None | None |
| `from_invoice_date` | From Invoice Date | Date | None |  |  |  | None | None |
| `from_payment_date` | From Payment Date | Date | None |  |  |  | None | None |
| `minimum_invoice_amount` | Minimum Invoice Amount | Currency | None |  |  |  | None | None |
| `minimum_payment_amount` | Minimum Payment Amount | Currency | None |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `to_invoice_date` | To Invoice Date | Date | None |  |  |  | None | None |
| `to_payment_date` | To Payment Date | Date | None |  |  |  | None | None |
| `maximum_invoice_amount` | Maximum Invoice Amount | Currency | None |  |  |  | None | None |
| `maximum_payment_amount` | Maximum Payment Amount | Currency | None |  |  |  | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `invoice_limit` | Invoice Limit | Int | None |  |  |  | 50 | System will fetch all the entries if limit value is zero. |
| `payment_limit` | Payment Limit | Int | None |  |  |  | 50 | System will fetch all the entries if limit value is zero. |
| `bank_cash_account` | Bank / Cash Account | Link | Account |  |  |  | None | This filter will be applied to Journal Entry. |
| `accounting_dimensions_section` | Accounting Dimensions Filter | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `sec_break1` | Unreconciled Entries | Section Break | None |  |  |  | None | If you need to reconcile particular transactions against each other, then please select accordingly. If not, all the transactions will be allocated in FIFO order. |
| `invoice_name` | Filter on Invoice | Data | None |  |  |  | None | None |
| `invoices` | Invoices | Table | Payment Reconciliation Invoice |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `payment_name` | Filter on Payment | Data | None |  |  |  | None | None |
| `payments` | Payments | Table | Payment Reconciliation Payment |  |  |  | None | None |
| `sec_break2` | Allocated Entries | Section Break | None |  |  |  | None | None |
| `allocation` | Allocation | Table | Payment Reconciliation Allocation |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 1
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_reconciliation/payment_reconciliation.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// For license information, please see license.txt

frappe.provide("erpnext.accounts");
erpnext.accounts.PaymentReconciliationController = class PaymentReconciliationController extends (
	frappe.ui.form.Controller
) {
	onload() {
		const default_company = frappe.defaults.get_default("company");
		this.frm.set_value("company", default_company);

		this.frm.set_value("party_type", "");
		this.frm.set_value("party", "");
		this.frm.set_value("receivable_payable_account", "");

		this.frm.set_query("party_type", () => {
			return {
				filters: {
					name: ["in", Object.keys(frappe.boot.party_account_types)],
				},
			};
		});

		this.frm.set_query("receivable_payable_account", () => {
			return {
				filters: {
					company: this.frm.doc.company,
					is_group: 0,
					account_type: frappe.boot.party_account_types[this.frm.doc.party_type],
					root_type: this.frm.doc.party_type == "Customer" ? "Asset" : "Liability",
				},
			};
		});

		this.frm.set_query("default_advance_account", () => {
			return {
				filters: {
					company: this.frm.doc.company,
					is_group: 0,
					account_type: this.frm.doc.party_type == "Customer" ? "Receivable" : "Payable",
					root_type: this.frm.doc.party_type == "Customer" ? "Liability" : "Asset",
				},
			};
		});

		this.frm.set_query("bank_cash_account", () => {
			return {
				filters: [
					["Account", "company", "=", this.frm.doc.company],
					["Account", "is_group", "=", 0],
					["Account", "account_type", "in", ["Bank", "Cash"]],
				],
			};
		});

		this.frm.set_query("cost_center", () => {
			return {
				filters: {
					company: this.frm.doc.company,
					is_group: 0,
				},
			};
		});
	}

	refresh() {
		this.frm.disable_save();

		this.frm.set_df_property("invoices", "cannot_delete_rows", true);
		this.frm.set_df_property("payments", "cannot_delete_rows", true);
		this.frm.set_df_property("allocation", "cannot_delete_rows", true);

		this.frm.set_df_property("invoices", "cannot_add_rows", true);
		this.frm.set_df_property("payments", "cannot_add_rows", true);
		this.frm.set_df_property("allocation", "cannot_add_rows", true);

		if (this.frm.doc.receivable_payable_account) {
			this.frm.add_custom_button(__("Get Unreconciled Entries"), () =>
				this.frm.trigger("get_unreconciled_entries")
			);
			this.frm.change_custom_button_type(__("Get Unreconciled Entries"), null, "primary");
		}
		if (this.frm.doc.invoices.length && this.frm.doc.payments.length) {
			this.frm.add_custom_button(__("Allocate"), () => this.frm.trigger("allocate"));
			this.frm.change_custom_button_type(__("Allocate"), null, "primary");
			this.frm.change_custom_button_type(__("Get Unreconciled Entries"), null, "default");
		}
		if (this.frm.doc.allocation.length) {
			this.frm.add_custom_button(__("Reconcile"), () => this.frm.trigger("reconcile"));
			this.frm.change_custom_button_type(__("Reconcile"), null, "primary");
			this.frm.change_custom_button_type(__("Get Unreconciled Entries"), null, "default");
			this.frm.change_custom_button_type(__("Allocate"), null, "default");
		}

		this.frm.trigger("set_query_for_dimension_filters");

		// check for any running reconciliation jobs
		if (this.frm.doc.receivable_payable_account) {
			this.frm.call({
				doc: this.frm.doc,
				method: "is_auto_process_enabled",
				callback: (r) => {
					if (r.message) {
						this.frm
							.call({
								method: "erpnext.accounts.doctype.process_payment_reconciliation.process_payment_reconciliation.is_any_doc_running",
								args: {
									for_filter: {
										company: this.frm.doc.company,
										party_type: this.frm.doc.party_type,
										party: this.frm.doc.party,
										receivable_payable_account: this.frm.doc.receivable_payable_account,
									},
								},
							})
							.then((r) => {
								if (r.message) {
									let doc_link = frappe.utils.get_form_link(
										"Process Payment Reconciliation",
										r.message,
										true
									);
									let msg = __(
										"Payment Reconciliation Job: {0} is running for this party. Can't reconcile now.",
										[doc_link]
									);
									this.frm.dashboard.add_comment(msg, "yellow");
								}
							});
					}
				},
			});
		}
	}
	set_query_for_dimension_filters() {
		frappe.call({
			method: "erpnext.accounts.doctype.payment_reconciliation.payment_reconciliation.get_queries_for_dimension_filters",
			args: {
				company: this.frm.doc.company,
			},
			callback: (r) => {
				if (!r.exc && r.message) {
					r.message.forEach((x) => {
						this.frm.set_query(x.fieldname, () => {
							return {
								filters: x.filters,
							};
						});
					});
				}
			},
		});
	}

	company() {
		this.frm.set_value("party", "");
		this.frm.set_value("receivable_payable_account", "");
	}

	party_type() {
		this.frm.set_value("party", "");
	}

	party() {
		this.frm.set_value("receivable_payable_account", "");
		this.frm.trigger("clear_child_tables");

		if (!this.frm.doc.receivable_payable_account && this.frm.doc.party_type && this.frm.doc.party) {
			frappe.call({
				method: "erpnext.accounts.party.get_party_account",
				args: {
					company: this.frm.doc.company,
					party_type: this.frm.doc.party_type,
					party: this.frm.doc.party,
					include_advance: 1,
				},
				callback: (r) => {
					if (!r.exc && r.message) {
						if (typeof r.message === "string") {
							this.frm.set_value("receivable_payable_account", r.message);
						} else if (Array.isArray(r.message)) {
							this.frm.set_value("receivable_payable_account", r.message[0]);
							this.frm.set_value("default_advance_account", r.message[1]);
						}
					}
					this.frm.refresh();
				},
			});
		}
	}

	receivable_payable_account() {
		this.frm.trigger("clear_child_tables");
		this.frm.refresh();
	}

	invoice_name() {
		this.frm.trigger("get_unreconciled_entries");
	}

	payment_name() {
		this.frm.trigger("get_unreconciled_entries");
	}

	clear_child_tables() {
		this.frm.clear_table("invoices");
		this.frm.clear_table("payments");
		this.frm.clear_table("allocation");
		this.frm.refresh_fields();
	}

	get_unreconciled_entries() {
		this.frm.clear_table("allocation");
		return this.frm.call({
			doc: this.frm.doc,
			method: "get_unreconciled_entries",
			callback: () => {
				if (!(this.frm.doc.payments.length || this.frm.doc.invoices.length)) {
					frappe.throw({
						message: __("No Unreconciled Invoices and Payments found for this party and account"),
					});
				} else if (!this.frm.doc.invoices.length) {
					frappe.throw({ message: __("No Outstanding Invoices found for this party") });
				} else if (!this.frm.doc.payments.length) {
					frappe.throw({ message: __("No Unreconciled Payments found for this party") });
				}
				this.frm.refresh();
			},
		});
	}

	allocate() {
		let payments = this.frm.fields_dict.payments.grid.get_selected_children();
		if (!payments.length) {
			payments = this.frm.doc.payments;
		}
		let invoices = this.frm.fields_dict.invoices.grid.get_selected_children();
		if (!invoices.length) {
			invoices = this.frm.doc.invoices;
		}
		return this.frm.call({
			doc: this.frm.doc,
			method: "allocate_entries",
			args: {
				payments: payments,
				invoices: invoices,
			},
			callback: () => {
				this.frm.refresh();
			},
		});
	}

	reconcile() {
		var show_dialog = this.frm.doc.allocation.filter((d) => d.difference_amount);

		if (show_dialog && show_dialog.length) {
			this.data = [];
			const dialog = new frappe.ui.Dialog({
				title: __("Select Difference Account"),
				size: "extra-large",
				fields: [
					{
						fieldname: "allocation",
						fieldtype: "Table",
						label: __("Allocation"),
						data: this.data,
						in_place_edit: true,
						cannot_add_rows: true,
						get_data: () => {
							return this.data;
						},
						fields: [
							{
								fieldtype: "Data",
								fieldname: "docname",
								in_list_view: 1,
								hidden: 1,
							},
							{
								fieldtype: "Data",
								fieldname: "reference_name",
								label: __("Voucher No"),
								in_list_view: 1,
								read_only: 1,
							},
							{
								fieldtype: "Date",
								fieldname: "gain_loss_posting_date",
								label: __("Posting Date"),
								in_list_view: 1,
								reqd: 1,
							},
							{
								fieldtype: "Link",
								options: "Account",
								in_list_view: 1,
								label: __("Difference Account"),
								fieldname: "difference_account",
								reqd: 1,
								get_query: () => {
									return {
										filters: {
											company: this.frm.doc.company,
											is_group: 0,
										},
									};
								},
							},
							{
								fieldtype: "Currency",
								in_list_view: 1,
								label: __("Difference Amount"),
								fieldname: "difference_amount",
								read_only: 1,
							},
						],
					},
					{
						fieldtype: "HTML",
						options: "<b> New Journal Entry will be posted for the difference amount </b>",
					},
				],
				primary_action: () => {
					const args = dialog.get_values()["allocation"];

					args.forEach((d) => {
						frappe.model.set_value(
							"Payment Reconciliation Allocation",
							d.docname,
							"difference_account",
							d.difference_account
						);
						frappe.model.set_value(
							"Payment Reconciliation Allocation",
							d.docname,
							"gain_loss_posting_date",
							d.gain_loss_posting_date
						);
					});

					this.reconcile_payment_entries();
					dialog.hide();
				},
				primary_action_label: __("Reconcile Entries"),
			});

			this.frm.doc.allocation.forEach((d) => {
				if (d.difference_amount) {
					dialog.fields_dict.allocation.df.data.push({
						docname: d.name,
						reference_name: d.reference_name,
						difference_amount: d.difference_amount,
						difference_account: d.difference_account,
						gain_loss_posting_date: d.gain_loss_posting_date,
					});
				}
			});

			this.data = dialog.fields_dict.allocation.df.data;
			dialog.fields_dict.allocation.grid.refresh();
			dialog.show();
		} else {
			this.reconcile_payment_entries();
		}
	}

	reconcile_payment_entries() {
		return this.frm.call({
			doc: this.frm.doc,
			method: "reconcile",
			callback: () => {
				this.frm.clear_table("allocation");
				this.frm.refresh();
			},
		});
	}
};

frappe.ui.form.on("Payment Reconciliation Allocation", {
	allocated_amount: function (frm, cdt, cdn) {
		let row = locals[cdt][cdn];
		// filter invoice
		let invoice = frm.doc.invoices.filter((x) => x.invoice_number == row.invoice_number);
		// filter payment
		let payment = frm.doc.payments.filter((x) => x.reference_name == row.reference_name);

		frm.call({
			doc: frm.doc,
			method: "calculate_difference_on_allocation_change",
			args: {
				payment_entry: payment,
				invoice: invoice,
				allocated_amount: row.allocated_amount,
			},
			callback: (r) => {
				if (r.message) {
					row.difference_amount = r.message;
					frm.refresh();
				}
			},
		});
	},
});

extend_cscript(cur_frm.cscript, new erpnext.accounts.PaymentReconciliationController({ frm: cur_frm }));

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
