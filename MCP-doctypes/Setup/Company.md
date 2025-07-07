# Master Control Plan: `Company`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:company_name`
- **Description:** Legal Entity / Subsidiary with a separate Chart of Accounts belonging to the Organization.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Auditor | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Projects User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Employee Self Service | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `details` | None | Section Break | None |  |  |  | None | None |
| `company_name` | Company | Data | None | ✅ |  |  | None | None |
| `abbr` | Abbr | Data | None | ✅ |  |  | None | None |
| `default_currency` | Default Currency | Link | Currency | ✅ |  |  | None | None |
| `country` | Country | Link | Country | ✅ |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  |  | 0 | None |
| `default_holiday_list` | Default Holiday List | Link | Holiday List |  |  |  | None | None |
| `cb0` | None | Column Break | None |  |  |  | None | None |
| `default_letter_head` | Default Letter Head | Link | Letter Head |  |  |  | None | None |
| `tax_id` | Tax ID | Data | None |  |  |  | None | None |
| `domain` | Domain | Data | None |  |  |  | None | None |
| `date_of_establishment` | Date of Establishment | Date | None |  |  |  | None | None |
| `parent_company` | Parent Company | Link | Company |  |  |  | None | None |
| `company_info` | Address & Contact | Section Break | None |  |  |  | None | None |
| `company_logo` | Company Logo | Attach Image | None |  | ✅ |  | None | None |
| `date_of_incorporation` | Date of Incorporation | Date | None |  |  |  | None | None |
| `phone_no` | Phone No | Data | Phone |  |  |  | None | None |
| `email` | Email | Data | Email |  |  |  | None | None |
| `company_description` | Company Description | Text Editor | None |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `date_of_commencement` | Date of Commencement | Date | None |  |  |  | None | None |
| `fax` | Fax | Data | Phone |  |  |  | None | None |
| `website` | Website | Data | None |  |  |  | None | None |
| `address_html` | None | HTML | None |  |  |  | None | None |
| `registration_info` | None | Section Break | None |  |  |  | None | None |
| `registration_details` | Registration Details | Code | None |  |  |  | None | Company registration numbers for your reference. Tax numbers etc. |
| `lft` | Lft | Int | None |  | ✅ | ✅ | None | None |
| `rgt` | Rgt | Int | None |  | ✅ | ✅ | None | None |
| `old_parent` | old_parent | Data | None |  | ✅ | ✅ | None | None |
| `accounts_tab` | Accounts | Tab Break | None |  |  |  | None | None |
| `section_break_28` | Chart of Accounts | Section Break | None |  |  |  | None | None |
| `create_chart_of_accounts_based_on` | Create Chart Of Accounts Based On | Select | 
Standard Template
Existing Company |  |  |  | None | None |
| `existing_company` | Existing Company  | Link | Company |  |  |  | None | None |
| `column_break_26` | None | Column Break | None |  |  |  | None | None |
| `chart_of_accounts` | Chart Of Accounts Template | Select | None |  |  |  | None | None |
| `default_settings` | Default Accounts | Section Break | None |  |  |  | None | None |
| `default_bank_account` | Default Bank Account | Link | Account |  |  |  | None | None |
| `default_cash_account` | Default Cash Account | Link | Account |  |  |  | None | None |
| `default_receivable_account` | Default Receivable Account | Link | Account |  |  |  | None | None |
| `default_payable_account` | Default Payable Account | Link | Account |  |  |  | None | None |
| `write_off_account` | Write Off Account | Link | Account |  |  |  | None | None |
| `unrealized_profit_loss_account` | Unrealized Profit / Loss Account | Link | Account |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `allow_account_creation_against_child_company` | Allow Account Creation Against Child Company | Check | None |  |  |  | 0 | None |
| `default_expense_account` | Default Cost of Goods Sold Account | Link | Account |  |  |  | None | None |
| `default_income_account` | Default Income Account | Link | Account |  |  |  | None | None |
| `default_discount_account` | Default Payment Discount Account | Link | Account |  |  |  | None | None |
| `payment_terms` | Default Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `cost_center` | Default Cost Center | Link | Cost Center |  |  |  | None | None |
| `default_finance_book` | Default Finance Book | Link | Finance Book |  |  |  | None | None |
| `exchange_gain__loss_section` | Exchange Gain / Loss | Section Break | None |  |  |  | None | None |
| `exchange_gain_loss_account` | Exchange Gain / Loss Account | Link | Account |  |  |  | None | None |
| `column_break_sttp` | None | Column Break | None |  |  |  | None | None |
| `unrealized_exchange_gain_loss_account` | Unrealized Exchange Gain/Loss Account | Link | Account |  |  |  | None | None |
| `round_off_section` | Round Off | Section Break | None |  |  |  | None | None |
| `round_off_account` | Round Off Account | Link | Account |  |  |  | None | None |
| `round_off_cost_center` | Round Off Cost Center | Link | Cost Center |  |  |  | None | None |
| `column_break_jqfo` | None | Column Break | None |  |  |  | None | None |
| `round_off_for_opening` | Round Off for Opening | Link | Account |  |  |  | None | None |
| `deferred_accounting_section` | Deferred Accounting | Section Break | None |  |  |  | None | None |
| `default_deferred_revenue_account` | Default Deferred Revenue Account | Link | Account |  |  |  | None | None |
| `column_break_dcdl` | None | Column Break | None |  |  |  | None | None |
| `default_deferred_expense_account` | Default Deferred Expense Account | Link | Account |  |  |  | None | None |
| `advance_payments_section` | Advance Payments | Section Break | None |  |  |  | None | None |
| `book_advance_payments_in_separate_party_account` | Book Advance Payments in Separate Party Account | Check | None |  |  |  | 0 | Enabling this option will allow you to record - <br><br> 1. Advances Received in a <b>Liability Account</b> instead of the <b>Asset Account</b><br><br>2. Advances Paid in an <b>Asset Account</b> instead of the <b> Liability Account</b> |
| `reconcile_on_advance_payment_date` | Reconcile on Advance Payment Date | Check | None |  | ✅ |  | 0 | If <b>Enabled</b> - Reconciliation happens on the <b>Advance Payment posting date</b><br>
If <b>Disabled</b> - Reconciliation happens on oldest of 2 Dates: <b>Invoice Date</b> or the <b>Advance Payment posting date</b><br>
 |
| `reconciliation_takes_effect_on` | Reconciliation Takes Effect On | Select | Advance Payment Date
Oldest Of Invoice Or Advance
Reconciliation Date |  |  |  | Oldest Of Invoice Or Advance | None |
| `column_break_fwcf` | None | Column Break | None |  |  |  | None | None |
| `default_advance_received_account` | Default Advance Received Account | Link | Account |  |  |  | None | Only 'Payment Entries' made against this advance account are supported. |
| `default_advance_paid_account` | Default Advance Paid Account | Link | Account |  |  |  | None | Only 'Payment Entries' made against this advance account are supported. |
| `exchange_rate_revaluation_settings_section` | Exchange Rate Revaluation Settings | Section Break | None |  |  |  | None | None |
| `auto_exchange_rate_revaluation` | Auto Create Exchange Rate Revaluation | Check | None |  |  |  | 0 | None |
| `auto_err_frequency` | Frequency | Select | Daily
Weekly
Monthly |  |  |  | None | None |
| `submit_err_jv` | Submit ERR Journals? | Check | None |  |  |  | 0 | None |
| `budget_detail` | Budget Detail | Section Break | None |  |  |  | None | None |
| `exception_budget_approver_role` | Exception Budget Approver Role | Link | Role |  |  |  | None | None |
| `fixed_asset_defaults` | Fixed Asset Defaults | Section Break | None |  |  |  | None | None |
| `accumulated_depreciation_account` | Accumulated Depreciation Account | Link | Account |  |  |  | None | None |
| `depreciation_expense_account` | Depreciation Expense Account | Link | Account |  |  |  | None | None |
| `series_for_depreciation_entry` | Series for Asset Depreciation Entry (Journal Entry) | Data | None |  |  |  | None | None |
| `column_break_40` | None | Column Break | None |  |  |  | None | None |
| `disposal_account` | Gain/Loss Account on Asset Disposal | Link | Account |  |  |  | None | None |
| `depreciation_cost_center` | Asset Depreciation Cost Center | Link | Cost Center |  |  |  | None | None |
| `capital_work_in_progress_account` | Capital Work In Progress Account | Link | Account |  |  |  | None | None |
| `asset_received_but_not_billed` | Asset Received But Not Billed | Link | Account |  |  |  | None | None |
| `buying_and_selling_tab` | Buying and Selling | Tab Break | None |  |  |  | None | None |
| `sales_settings` | Buying & Selling Settings | Section Break | None |  |  |  | None | None |
| `default_buying_terms` | Default Buying Terms | Link | Terms and Conditions |  |  |  | None | None |
| `sales_monthly_history` | Sales Monthly History | Small Text | None |  | ✅ | ✅ | None | None |
| `monthly_sales_target` | Monthly Sales Target | Currency | default_currency |  |  |  | None | None |
| `total_monthly_sales` | Total Monthly Sales | Currency | default_currency |  |  | ✅ | None | None |
| `column_break_goals` | None | Column Break | None |  |  |  | None | None |
| `default_selling_terms` | Default Selling Terms | Link | Terms and Conditions |  |  |  | None | None |
| `default_warehouse_for_sales_return` | Default Warehouse for Sales Return | Link | Warehouse |  |  |  | None | None |
| `credit_limit` | Credit Limit | Currency | default_currency |  |  |  | None | None |
| `hr_and_payroll_tab` | HR & Payroll | Tab Break | None |  |  |  | None | None |
| `hr_settings_section` | HR & Payroll Settings | Section Break | None |  |  |  | None | None |
| `default_expense_claim_payable_account` | Default Expense Claim Payable Account | Link | Account |  |  |  | None | None |
| `default_employee_advance_account` | Default Employee Advance Account | Link | Account |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `default_payroll_payable_account` | Default Payroll Payable Account | Link | Account |  |  |  | None | None |
| `transactions_annual_history` | Transactions Annual History | Code | None |  | ✅ | ✅ | None | None |
| `stock_tab` | Stock and Manufacturing | Tab Break | None |  |  |  | None | None |
| `auto_accounting_for_stock_settings` | Stock Settings | Section Break | None |  |  |  | None | None |
| `enable_perpetual_inventory` | Enable Perpetual Inventory | Check | None |  |  |  | 1 | None |
| `enable_provisional_accounting_for_non_stock_items` | Enable Provisional Accounting For Non Stock Items | Check | None |  |  |  | 0 | None |
| `default_inventory_account` | Default Inventory Account | Link | Account |  |  |  | None | None |
| `stock_adjustment_account` | Stock Adjustment Account | Link | Account |  |  |  | None | None |
| `column_break_32` | None | Column Break | None |  |  |  | None | None |
| `stock_received_but_not_billed` | Stock Received But Not Billed | Link | Account |  |  |  | None | None |
| `default_provisional_account` | Default Provisional Account | Link | Account |  |  |  | None | None |
| `default_in_transit_warehouse` | Default In-Transit Warehouse | Link | Warehouse |  |  |  | None | None |
| `manufacturing_section` | Manufacturing | Section Break | None |  |  |  | None | None |
| `default_operating_cost_account` | Default Operating Cost Account | Link | Account |  |  |  | None | None |
| `dashboard_tab` | Dashboard | Tab Break | None |  |  |  | None | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `default_payroll_payable_account` | Default Payroll Payable Account | Link | Account |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `default_employee_advance_account` | Default Employee Advance Account | Link | Account |  |  |  | None | None |
| `default_expense_claim_payable_account` | Default Expense Claim Payable Account | Link | Account |  |  |  | None | None |
| `hr_settings_section` | HR & Payroll Settings | Section Break | None |  |  |  | None | None |
| `hr_and_payroll_tab` | HR & Payroll | Tab Break | None |  |  |  | None | None |



### Links & Relationships
- **Link Fields:** 49
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/company/company.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.company");

frappe.ui.form.on("Company", {
	onload: function (frm) {
		if (frm.doc.__islocal && frm.doc.parent_company) {
			frappe.db.get_value("Company", frm.doc.parent_company, "is_group", (r) => {
				if (!r.is_group) {
					frm.set_value("parent_company", "");
				}
			});
		}
		if (!frm.doc.__islocal) {
			frm.call("check_if_transactions_exist").then((r) => {
				frm.toggle_enable("default_currency", !r.message);
			});
		}
	},
	setup: function (frm) {
		frm.__rename_queue = "long";

		frm.set_query("parent_company", function () {
			return {
				filters: { is_group: 1 },
			};
		});

		frm.set_query("default_operating_cost_account", function (doc) {
			return {
				filters: { company: doc.name, root_type: "Expense" },
			};
		});

		frm.set_query("default_selling_terms", function () {
			return { filters: { selling: 1 } };
		});

		frm.set_query("default_buying_terms", function () {
			return { filters: { buying: 1 } };
		});

		frm.set_query("default_in_transit_warehouse", function () {
			return {
				filters: {
					warehouse_type: "Transit",
					is_group: 0,
					company: frm.doc.company_name,
				},
			};
		});
	},

	company_name: function (frm) {
		if (frm.doc.__islocal) {
			// add missing " " arg in split method
			let parts = frm.doc.company_name.split(" ");
			let abbr = $.map(parts, function (p) {
				return p ? p.substr(0, 1) : null;
			}).join("");
			frm.set_value("abbr", abbr);
		}
	},

	parent_company: function (frm) {
		var bool = frm.doc.parent_company ? true : false;
		frm.set_value("create_chart_of_accounts_based_on", bool ? "Existing Company" : "");
		frm.set_value("existing_company", bool ? frm.doc.parent_company : "");
		disbale_coa_fields(frm, bool);
	},

	date_of_commencement: function (frm) {
		if (frm.doc.date_of_commencement < frm.doc.date_of_incorporation) {
			frappe.throw(__("Date of Commencement should be greater than Date of Incorporation"));
		}
		if (!frm.doc.date_of_commencement) {
			frm.doc.date_of_incorporation = "";
		}
	},

	refresh: function (frm) {
		erpnext.company.setup_queries(frm);

		frm.toggle_display("address_html", !frm.is_new());

		if (!frm.is_new()) {
			frm.doc.abbr && frm.set_df_property("abbr", "read_only", 1);
			disbale_coa_fields(frm);
			frappe.contacts.render_address_and_contact(frm);

			if (frappe.perm.has_perm("Cost Center", 0, "read")) {
				frm.add_custom_button(
					__("Cost Centers"),
					function () {
						frappe.set_route("Tree", "Cost Center", { company: frm.doc.name });
					},
					__("View")
				);
			}

			if (frappe.perm.has_perm("Account", 0, "read")) {
				frm.add_custom_button(
					__("Chart of Accounts"),
					function () {
						frappe.set_route("Tree", "Account", { company: frm.doc.name });
					},
					__("View")
				);
			}

			if (frappe.perm.has_perm("Sales Taxes and Charges Template", 0, "read")) {
				frm.add_custom_button(
					__("Sales Tax Template"),
					function () {
						frappe.set_route("List", "Sales Taxes and Charges Template", {
							company: frm.doc.name,
						});
					},
					__("View")
				);
			}

			if (frappe.perm.has_perm("Purchase Taxes and Charges Template", 0, "read")) {
				frm.add_custom_button(
					__("Purchase Tax Template"),
					function () {
						frappe.set_route("List", "Purchase Taxes and Charges Template", {
							company: frm.doc.name,
						});
					},
					__("View")
				);
			}

			if (frm.has_perm("write")) {
				frm.add_custom_button(
					__("Create Tax Template"),
					function () {
						frm.trigger("make_default_tax_template");
					},
					__("Manage")
				);
			}

			if (frappe.user.has_role("System Manager")) {
				if (frm.has_perm("write")) {
					frm.add_custom_button(
						__("Delete Transactions"),
						function () {
							frm.trigger("delete_company_transactions");
						},
						__("Manage")
					);
				}
			}
		}

		erpnext.company.set_chart_of_accounts_options(frm.doc);
	},

	make_default_tax_template: function (frm) {
		frm.call({
			method: "create_default_tax_template",
			doc: frm.doc,
			freeze: true,
			callback: function () {
				frappe.msgprint(__("Default tax templates for sales, purchase and items are created."));
			},
		});
	},

	country: function (frm) {
		erpnext.company.set_chart_of_accounts_options(frm.doc);
	},

	delete_company_transactions: function (frm) {
		frappe.call({
			method: "erpnext.setup.doctype.transaction_deletion_record.transaction_deletion_record.is_deletion_doc_running",
			args: {
				company: frm.doc.name,
			},
			freeze: true,
			callback: function (r) {
				if (!r.exc) {
					frappe.verify_password(function () {
						var d = frappe.prompt(
							{
								fieldtype: "Data",
								fieldname: "company_name",
								label: __("Please enter the company name to confirm"),
								reqd: 1,
								description: __(
									"Please make sure you really want to delete all the transactions for this company. Your master data will remain as it is. This action cannot be undone."
								),
							},
							function (data) {
								if (data.company_name !== frm.doc.name) {
									frappe.msgprint(__("Company name not same"));
									return;
								}
								frappe.call({
									method: "erpnext.setup.doctype.company.company.create_transaction_deletion_request",
									args: {
										company: data.company_name,
									},
									freeze: true,
									callback: function (r, rt) {},
									onerror: function () {
										frappe.msgprint(__("Wrong Password"));
									},
								});
							},
							__("Delete all the Transactions for this Company"),
							__("Delete")
						);
						d.get_primary_btn().addClass("btn-danger");
					});
				}
			},
		});
	},
});

erpnext.company.set_chart_of_accounts_options = function (doc) {
	var selected_value = doc.chart_of_accounts;
	if (doc.country) {
		return frappe.call({
			method: "erpnext.accounts.doctype.account.chart_of_accounts.chart_of_accounts.get_charts_for_country",
			args: {
				country: doc.country,
				with_standard: true,
			},
			callback: function (r) {
				if (!r.exc) {
					set_field_options("chart_of_accounts", [""].concat(r.message).join("\n"));
					if (in_list(r.message, selected_value))
						cur_frm.set_value("chart_of_accounts", selected_value);
				}
			},
		});
	}
};

erpnext.company.setup_queries = function (frm) {
	$.each(
		[
			["default_bank_account", { account_type: "Bank" }],
			["default_cash_account", { account_type: "Cash" }],
			["default_receivable_account", { root_type: "Asset", account_type: "Receivable" }],
			["default_payable_account", { root_type: "Liability", account_type: "Payable" }],
			["default_expense_account", { root_type: "Expense" }],
			["default_income_account", { root_type: "Income" }],
			["round_off_account", { root_type: "Expense" }],
			["round_off_for_opening", { root_type: "Liability", account_type: "Round Off for Opening" }],
			["write_off_account", { root_type: "Expense" }],
			["default_deferred_expense_account", {}],
			["default_deferred_revenue_account", {}],
			["default_discount_account", {}],
			["discount_allowed_account", { root_type: "Expense" }],
			["discount_received_account", { root_type: "Income" }],
			["exchange_gain_loss_account", { root_type: ["in", ["Expense", "Income"]] }],
			[
				"unrealized_exchange_gain_loss_account",
				{ root_type: ["in", ["Expense", "Income", "Equity", "Liability"]] },
			],
			[
				"accumulated_depreciation_account",
				{ root_type: "Asset", account_type: "Accumulated Depreciation" },
			],
			["depreciation_expense_account", { root_type: "Expense", account_type: "Depreciation" }],
			["disposal_account", { report_type: "Profit and Loss" }],
			["default_inventory_account", { account_type: "Stock" }],
			["cost_center", {}],
			["round_off_cost_center", {}],
			["depreciation_cost_center", {}],
			["capital_work_in_progress_account", { account_type: "Capital Work in Progress" }],
			["asset_received_but_not_billed", { account_type: "Asset Received But Not Billed" }],
			["unrealized_profit_loss_account", { root_type: ["in", ["Liability", "Asset"]] }],
			["default_provisional_account", { root_type: ["in", ["Liability", "Asset"]] }],
			["default_advance_received_account", { root_type: "Liability", account_type: "Receivable" }],
			["default_advance_paid_account", { root_type: "Asset", account_type: "Payable" }],
		],
		function (i, v) {
			erpnext.company.set_custom_query(frm, v);
		}
	);

	if (frm.doc.enable_perpetual_inventory) {
		$.each(
			[
				["stock_adjustment_account", { root_type: "Expense", account_type: "Stock Adjustment" }],
				[
					"stock_received_but_not_billed",
					{ root_type: "Liability", account_type: "Stock Received But Not Billed" },
				],
				[
					"service_received_but_not_billed",
					{ root_type: "Liability", account_type: "Service Received But Not Billed" },
				],
			],
			function (i, v) {
				erpnext.company.set_custom_query(frm, v);
			}
		);
	}
};

erpnext.company.set_custom_query = function (frm, v) {
	var filters = {
		company: frm.doc.name,
		is_group: 0,
	};

	for (var key in v[1]) {
		filters[key] = v[1][key];
	}

	frm.set_query(v[0], function () {
		return {
			filters: filters,
		};
	});
};

var disbale_coa_fields = function (frm, bool = true) {
	frm.set_df_property("create_chart_of_accounts_based_on", "read_only", bool);
	frm.set_df_property("chart_of_accounts", "read_only", bool);
	frm.set_df_property("existing_company", "read_only", bool);
};

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
