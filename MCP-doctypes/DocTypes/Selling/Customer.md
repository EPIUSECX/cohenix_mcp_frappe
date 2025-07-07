# Master Control Plan: `Customer`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** Buyer of Goods and Services.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales Master Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Stock Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `basic_info` | None | Section Break | fa fa-user |  |  |  | None | None |
| `naming_series` | Series | Select | CUST-.YYYY.- |  | ✅ |  | None | None |
| `salutation` | Salutation | Link | Salutation |  |  |  | None | None |
| `customer_name` | Customer Name | Data | None | ✅ |  |  | None | None |
| `customer_type` | Customer Type | Select | Company
Individual
Partnership | ✅ |  |  | Company | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `gender` | Gender | Link | Gender |  |  |  | None | None |
| `lead_name` | From Lead | Link | Lead |  |  |  | None | None |
| `opportunity_name` | From Opportunity | Link | Opportunity |  |  |  | None | None |
| `prospect_name` | From Prospect | Link | Prospect |  |  |  | None | None |
| `account_manager` | Account Manager | Link | User |  |  |  | None | None |
| `image` | Image | Attach Image | None |  | ✅ |  | None | None |
| `defaults_tab` | Defaults | Section Break | None |  |  |  | None | None |
| `default_currency` | Billing Currency | Link | Currency |  |  |  | None | None |
| `default_bank_account` | Default Company Bank Account | Link | Bank Account |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `default_price_list` | Default Price List | Link | Price List |  |  |  | None | None |
| `internal_customer_section` | Internal Customer | Section Break | None |  |  |  | None | None |
| `is_internal_customer` | Is Internal Customer | Check | None |  |  |  | 0 | None |
| `represents_company` | Represents Company | Link | Company |  |  |  | None | None |
| `column_break_70` | None | Column Break | None |  |  |  | None | None |
| `companies` | Allowed To Transact With | Table | Allowed To Transact With |  |  |  | None | None |
| `more_info` | More Information | Section Break | fa fa-file-text |  |  |  | None | None |
| `market_segment` | Market Segment | Link | Market Segment |  |  |  | None | None |
| `industry` | Industry | Link | Industry Type |  |  |  | None | None |
| `customer_pos_id` | Customer POS id | Data | None |  |  | ✅ | None | None |
| `website` | Website | Data | None |  |  |  | None | None |
| `language` | Print Language | Link | Language |  |  |  | None | None |
| `column_break_45` | None | Column Break | None |  |  |  | None | None |
| `customer_details` | Customer Details | Text | None |  |  |  | None | Additional information regarding the customer. |
| `supplier_numbers` | Supplier Numbers | Table | Supplier Number At Customer |  |  |  | None | Supplier numbers assigned by the customer |
| `dashboard_tab` | Dashboard | Tab Break | None |  |  |  | None | None |
| `contact_and_address_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `address_contacts` | Address and Contact | Section Break | fa fa-map-marker |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  | ✅ | None | None |
| `primary_address_and_contact_detail` | Primary Address and Contact | Section Break | None |  |  |  | None | Select, to make the customer searchable with these fields |
| `column_break_26` | None | Column Break | None |  |  |  | None | None |
| `customer_primary_address` | Customer Primary Address | Link | Address |  |  |  | None | Reselect, if the chosen address is edited after save |
| `primary_address` | Primary Address | Text | None |  |  | ✅ | None | None |
| `column_break_nwor` | None | Column Break | None |  |  |  | None | None |
| `customer_primary_contact` | Customer Primary Contact | Link | Contact |  |  |  | None | Reselect, if the chosen contact is edited after save |
| `mobile_no` | Mobile No | Read Only | Mobile |  |  |  | None | None |
| `email_id` | Email Id | Read Only | Email |  |  |  | None | None |
| `first_name` | First Name | Read Only | None |  | ✅ |  | None | None |
| `last_name` | Last Name | Read Only | None |  | ✅ |  | None | None |
| `tax_tab` | Tax | Tab Break | None |  |  |  | None | None |
| `taxation_section` | None | Section Break | None |  |  |  | None | None |
| `tax_id` | Tax ID | Data | None |  |  |  | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `tax_withholding_category` | Tax Withholding Category | Link | Tax Withholding Category |  |  |  | None | None |
| `accounting_tab` | Accounting | Tab Break | None |  |  |  | None | None |
| `credit_limit_section` | Credit Limit and Payment Terms | Section Break | None |  |  |  | None | None |
| `payment_terms` | Default Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `credit_limits` | Credit Limit | Table | Customer Credit Limit |  |  |  | None | None |
| `default_receivable_accounts` | Default Accounts | Section Break | None |  |  |  | None | None |
| `accounts` | Accounts | Table | Party Account |  |  |  | None | Mention if non-standard Receivable account |
| `loyalty_points_tab` | Loyalty Points | Section Break | None |  |  |  | None | None |
| `loyalty_program` | Loyalty Program | Link | Loyalty Program |  |  |  | None | None |
| `column_break_54` | None | Column Break | None |  |  |  | None | None |
| `loyalty_program_tier` | Loyalty Program Tier | Data | None |  |  | ✅ | None | None |
| `sales_team_tab` | Sales Team | Tab Break | fa fa-group |  |  |  | None | None |
| `sales_team` | Sales Team | Table | Sales Team |  |  |  | None | None |
| `sales_team_section` | None | Section Break | None |  |  |  | None | None |
| `default_sales_partner` | Sales Partner | Link | Sales Partner |  |  |  | None | None |
| `column_break_66` | None | Column Break | None |  |  |  | None | None |
| `default_commission_rate` | Commission Rate | Float | None |  |  |  | None | None |
| `settings_tab` | Settings | Tab Break | None |  |  |  | None | None |
| `so_required` | Allow Sales Invoice Creation Without Sales Order | Check | None |  |  |  | 0 | None |
| `dn_required` | Allow Sales Invoice Creation Without Delivery Note | Check | None |  |  |  | 0 | None |
| `column_break_53` | None | Column Break | None |  |  |  | None | None |
| `is_frozen` | Is Frozen | Check | None |  |  |  | 0 | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `portal_users_tab` | Portal Users | Tab Break | None |  |  |  | None | None |
| `portal_users` | Customer Portal Users | Table | Portal User |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 22
- **Dynamic Link Fields:** 0
- **Table Fields:** 6

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/customer/customer.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Customer", {
	setup: function (frm) {
		frm.custom_make_buttons = {
			Opportunity: "Opportunity",
			Quotation: "Quotation",
			"Sales Order": "Sales Order",
			"Pricing Rule": "Pricing Rule",
			"Payment Entry": "Payment Entry",
		};
		frm.make_methods = {
			Quotation: () =>
				frappe.model.open_mapped_doc({
					method: "erpnext.selling.doctype.customer.customer.make_quotation",
					frm: frm,
				}),
			"Sales Order": () =>
				frappe.model.with_doctype("Sales Order", function () {
					var so = frappe.model.get_new_doc("Sales Order");
					so.customer = frm.doc.name; // Set the current customer as the SO customer
					frappe.set_route("Form", "Sales Order", so.name);
				}),
			Opportunity: () =>
				frappe.model.open_mapped_doc({
					method: "erpnext.selling.doctype.customer.customer.make_opportunity",
					frm: frm,
				}),
			"Payment Entry": () =>
				frappe.model.open_mapped_doc({
					method: "erpnext.selling.doctype.customer.customer.make_payment_entry",
					frm: frm,
				}),
			"Pricing Rule": () => erpnext.utils.make_pricing_rule(frm.doc.doctype, frm.doc.name),
		};

		frm.add_fetch("lead_name", "company_name", "customer_name");
		frm.add_fetch("default_sales_partner", "commission_rate", "default_commission_rate");
		frm.set_query("default_price_list", { selling: 1 });
		frm.set_query("account", "accounts", function (doc, cdt, cdn) {
			let d = locals[cdt][cdn];
			let filters = {
				account_type: "Receivable",
				root_type: "Asset",
				company: d.company,
				is_group: 0,
			};

			if (doc.party_account_currency) {
				$.extend(filters, { account_currency: doc.party_account_currency });
			}
			return {
				filters: filters,
			};
		});

		frm.set_query("advance_account", "accounts", function (doc, cdt, cdn) {
			let d = locals[cdt][cdn];
			return {
				filters: {
					account_type: "Receivable",
					root_type: "Liability",
					company: d.company,
					is_group: 0,
				},
			};
		});

		if (frm.doc.__islocal == 1) {
			frm.set_value("represents_company", "");
		}

		frm.set_query("customer_primary_contact", function (doc) {
			return {
				query: "erpnext.selling.doctype.customer.customer.get_customer_primary_contact",
				filters: {
					customer: doc.name,
				},
			};
		});
		frm.set_query("customer_primary_address", function (doc) {
			return {
				filters: {
					link_doctype: "Customer",
					link_name: doc.name,
				},
			};
		});

		frm.set_query("default_bank_account", function () {
			return {
				filters: {
					is_company_account: 1,
				},
			};
		});

		frm.set_query("user", "portal_users", function () {
			return {
				filters: {
					ignore_user_type: true,
				},
			};
		});
	},
	customer_primary_address: function (frm) {
		if (frm.doc.customer_primary_address) {
			frappe.call({
				method: "frappe.contacts.doctype.address.address.get_address_display",
				args: {
					address_dict: frm.doc.customer_primary_address,
				},
				callback: function (r) {
					frm.set_value("primary_address", r.message);
				},
			});
		}
		if (!frm.doc.customer_primary_address) {
			frm.set_value("primary_address", "");
		}
	},

	is_internal_customer: function (frm) {
		if (frm.doc.is_internal_customer == 1) {
			frm.toggle_reqd("represents_company", true);
		} else {
			frm.toggle_reqd("represents_company", false);
		}
	},

	customer_primary_contact: function (frm) {
		if (!frm.doc.customer_primary_contact) {
			frm.set_value("mobile_no", "");
			frm.set_value("email_id", "");
		}
	},

	loyalty_program: function (frm) {
		if (frm.doc.loyalty_program) {
			frm.set_value("loyalty_program_tier", null);
		}
	},

	refresh: function (frm) {
		if (frappe.defaults.get_default("cust_master_name") != "Naming Series") {
			frm.toggle_display("naming_series", false);
		} else {
			erpnext.toggle_naming_series();
		}

		if (!frm.doc.__islocal) {
			frappe.contacts.render_address_and_contact(frm);

			// custom buttons

			frm.add_custom_button(
				__("Accounts Receivable"),
				function () {
					frappe.set_route("query-report", "Accounts Receivable", {
						party_type: "Customer",
						party: frm.doc.name,
					});
				},
				__("View")
			);

			frm.add_custom_button(
				__("Accounting Ledger"),
				function () {
					frappe.set_route("query-report", "General Ledger", {
						party_type: "Customer",
						party: frm.doc.name,
						party_name: frm.doc.customer_name,
					});
				},
				__("View")
			);

			for (const doctype in frm.make_methods) {
				frm.add_custom_button(__(doctype), frm.make_methods[doctype], __("Create"));
			}

			frm.add_custom_button(
				__("Get Customer Group Details"),
				function () {
					frm.trigger("get_customer_group_details");
				},
				__("Actions")
			);

			if (cint(frappe.defaults.get_default("enable_common_party_accounting"))) {
				frm.add_custom_button(
					__("Link with Supplier"),
					function () {
						frm.trigger("show_party_link_dialog");
					},
					__("Actions")
				);
			}

			// indicator
			erpnext.utils.set_party_dashboard_indicators(frm);
		} else {
			frappe.contacts.clear_address_and_contact(frm);
		}

		var grid = cur_frm.get_field("sales_team").grid;
		grid.set_column_disp("allocated_amount", false);
		grid.set_column_disp("incentives", false);
	},
	validate: function (frm) {
		if (frm.doc.lead_name) frappe.model.clear_doc("Lead", frm.doc.lead_name);
	},
	get_customer_group_details: function (frm) {
		frappe.call({
			method: "get_customer_group_details",
			doc: frm.doc,
			callback: function () {
				frm.refresh();
			},
		});
	},
	show_party_link_dialog: function (frm) {
		const dialog = new frappe.ui.Dialog({
			title: __("Select a Supplier"),
			fields: [
				{
					fieldtype: "Link",
					label: __("Supplier"),
					options: "Supplier",
					fieldname: "supplier",
					reqd: 1,
				},
			],
			primary_action: function ({ supplier }) {
				frappe.call({
					method: "erpnext.accounts.doctype.party_link.party_link.create_party_link",
					args: {
						primary_role: "Customer",
						primary_party: frm.doc.name,
						secondary_party: supplier,
					},
					freeze: true,
					callback: function () {
						dialog.hide();
						frappe.msgprint({
							message: __("Successfully linked to Supplier"),
							alert: true,
						});
					},
					error: function () {
						dialog.hide();
						frappe.msgprint({
							message: __("Linking to Supplier Failed. Please try again."),
							title: __("Linking Failed"),
							indicator: "red",
						});
					},
				});
			},
			primary_action_label: __("Create Link"),
		});
		dialog.show();
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Customer-wise Item Price` | Script Report | Selling |
| `Customer Credit Balance` | Script Report | Selling |
| `Customer Acquisition and Loyalty` | Script Report | Selling |



### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Active Customers` | Active Customers | Count | Selling |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
