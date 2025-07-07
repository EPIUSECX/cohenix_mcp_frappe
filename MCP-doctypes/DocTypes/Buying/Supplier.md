# Master Control Plan: `Supplier`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Buying`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** Supplier of Goods or Services.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | SUP-.YYYY.- |  | ✅ |  | None | None |
| `supplier_name` | Supplier Name | Data | None | ✅ |  |  | None | None |
| `country` | Country | Link | Country |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `supplier_group` | Supplier Group | Link | Supplier Group |  |  |  | None | None |
| `supplier_type` | Supplier Type | Select | Company
Individual
Partnership | ✅ |  |  | Company | None |
| `is_transporter` | Is Transporter | Check | None |  |  |  | 0 | None |
| `image` | Image | Attach Image | None |  | ✅ |  | None | None |
| `defaults_section` | Defaults | Section Break | None |  |  |  | None | None |
| `default_currency` | Billing Currency | Link | Currency |  |  |  | None | None |
| `default_bank_account` | Default Company Bank Account | Link | Bank Account |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `default_price_list` | Price List | Link | Price List |  |  |  | None | None |
| `internal_supplier_section` | Internal Supplier | Section Break | None |  |  |  | None | None |
| `is_internal_supplier` | Is Internal Supplier | Check | None |  |  |  | 0 | None |
| `represents_company` | Represents Company | Link | Company |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `companies` | Allowed To Transact With | Table | Allowed To Transact With |  |  |  | None | None |
| `column_break2` | More Information | Section Break | None |  |  |  | None | None |
| `supplier_details` | Supplier Details | Text | None |  |  |  | None | Statutory info and other general information about your Supplier |
| `column_break_30` | None | Column Break | None |  |  |  | None | None |
| `website` | Website | Data | None |  |  |  | None | None |
| `language` | Print Language | Link | Language |  |  |  | None | None |
| `customer_numbers` | Customer Numbers | Table | Customer Number At Supplier |  |  |  | None | None |
| `dashboard_tab` | Dashboard | Tab Break | None |  |  |  | None | None |
| `tax_tab` | Tax | Tab Break | None |  |  |  | None | None |
| `tax_id` | Tax ID | Data | None |  |  |  | None | None |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `tax_withholding_category` | Tax Withholding Category | Link | Tax Withholding Category |  |  |  | None | None |
| `contact_and_address_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `address_contacts` | Address and Contacts | Section Break | fa fa-map-marker |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  | ✅ | None | None |
| `primary_address_and_contact_detail_section` | Primary Address and Contact | Section Break | None |  |  |  | None | None |
| `column_break_44` | None | Column Break | None |  |  |  | None | None |
| `supplier_primary_address` | Supplier Primary Address | Link | Address |  |  |  | None | Reselect, if the chosen address is edited after save |
| `primary_address` | Primary Address | Text | None |  |  | ✅ | None | None |
| `column_break_mglr` | None | Column Break | None |  |  |  | None | None |
| `supplier_primary_contact` | Supplier Primary Contact | Link | Contact |  |  |  | None | Reselect, if the chosen contact is edited after save |
| `mobile_no` | Mobile No | Read Only | None |  |  |  | None | None |
| `email_id` | Email Id | Read Only | None |  |  |  | None | None |
| `accounting_tab` | Accounting | Tab Break | None |  |  |  | None | None |
| `payment_terms` | Default Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `default_accounts_section` | Default Accounts | Section Break | None |  |  |  | None | None |
| `accounts` | Accounts | Table | Party Account |  |  |  | None | Mention if non-standard payable account |
| `settings_tab` | Settings | Tab Break | None |  |  |  | None | None |
| `allow_purchase_invoice_creation_without_purchase_order` | Allow Purchase Invoice Creation Without Purchase Order | Check | None |  |  |  | 0 | None |
| `allow_purchase_invoice_creation_without_purchase_receipt` | Allow Purchase Invoice Creation Without Purchase Receipt | Check | None |  |  |  | 0 | None |
| `column_break_54` | None | Column Break | None |  |  |  | None | None |
| `is_frozen` | Is Frozen | Check | None |  |  |  | 0 | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `warn_rfqs` | Warn RFQs | Check | None |  | ✅ | ✅ | 0 | None |
| `warn_pos` | Warn POs | Check | None |  | ✅ | ✅ | 0 | None |
| `prevent_rfqs` | Prevent RFQs | Check | None |  | ✅ | ✅ | 0 | None |
| `prevent_pos` | Prevent POs | Check | None |  | ✅ | ✅ | 0 | None |
| `block_supplier_section` | Block Supplier | Section Break | None |  |  |  | None | None |
| `on_hold` | Block Supplier | Check | None |  |  |  | 0 | None |
| `hold_type` | Hold Type | Select | 
All
Invoices
Payments |  |  |  | None | None |
| `column_break_59` | None | Column Break | None |  |  |  | None | None |
| `release_date` | Release Date | Date | None |  |  |  | None | Leave blank if the Supplier is blocked indefinitely |
| `portal_users_tab` | Portal Users | Tab Break | None |  |  |  | None | None |
| `portal_users` | Supplier Portal Users | Table | Portal User |  |  |  | None | None |
| `column_break_1mqv` | None | Column Break | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/supplier/supplier.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Supplier", {
	setup: function (frm) {
		frm.set_query("default_price_list", { buying: 1 });
		if (frm.doc.__islocal == 1) {
			frm.set_value("represents_company", "");
		}
		frm.set_query("account", "accounts", function (doc, cdt, cdn) {
			let d = locals[cdt][cdn];
			return {
				filters: {
					account_type: "Payable",
					root_type: "Liability",
					company: d.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("advance_account", "accounts", function (doc, cdt, cdn) {
			let d = locals[cdt][cdn];
			return {
				filters: {
					account_type: "Payable",
					root_type: "Asset",
					company: d.company,
					is_group: 0,
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

		frm.set_query("supplier_primary_contact", function (doc) {
			return {
				query: "erpnext.buying.doctype.supplier.supplier.get_supplier_primary_contact",
				filters: {
					supplier: doc.name,
				},
			};
		});

		frm.set_query("supplier_primary_address", function (doc) {
			return {
				filters: {
					link_doctype: "Supplier",
					link_name: doc.name,
				},
			};
		});

		frm.set_query("user", "portal_users", function (doc) {
			return {
				filters: {
					ignore_user_type: true,
				},
			};
		});
	},

	refresh: function (frm) {
		if (frappe.defaults.get_default("supp_master_name") != "Naming Series") {
			frm.toggle_display("naming_series", false);
		} else {
			erpnext.toggle_naming_series();
		}

		if (frm.doc.__islocal) {
			hide_field(["address_html", "contact_html"]);
			frappe.contacts.clear_address_and_contact(frm);
		} else {
			unhide_field(["address_html", "contact_html"]);
			frappe.contacts.render_address_and_contact(frm);

			// custom buttons
			frm.add_custom_button(
				__("Accounting Ledger"),
				function () {
					frappe.set_route("query-report", "General Ledger", {
						party_type: "Supplier",
						party: frm.doc.name,
						party_name: frm.doc.supplier_name,
					});
				},
				__("View")
			);

			frm.add_custom_button(
				__("Accounts Payable"),
				function () {
					frappe.set_route("query-report", "Accounts Payable", {
						party_type: "Supplier",
						party: frm.doc.name,
					});
				},
				__("View")
			);

			frm.add_custom_button(
				__("Bank Account"),
				function () {
					erpnext.utils.make_bank_account(frm.doc.doctype, frm.doc.name);
				},
				__("Create")
			);

			frm.add_custom_button(
				__("Pricing Rule"),
				function () {
					erpnext.utils.make_pricing_rule(frm.doc.doctype, frm.doc.name);
				},
				__("Create")
			);

			frm.add_custom_button(
				__("Get Supplier Group Details"),
				function () {
					frm.trigger("get_supplier_group_details");
				},
				__("Actions")
			);

			if (cint(frappe.defaults.get_default("enable_common_party_accounting"))) {
				frm.add_custom_button(
					__("Link with Customer"),
					function () {
						frm.trigger("show_party_link_dialog");
					},
					__("Actions")
				);
			}

			// indicators
			erpnext.utils.set_party_dashboard_indicators(frm);
		}
	},
	get_supplier_group_details: function (frm) {
		frappe.call({
			method: "get_supplier_group_details",
			doc: frm.doc,
			callback: function () {
				frm.refresh();
			},
		});
	},

	supplier_primary_address: function (frm) {
		if (frm.doc.supplier_primary_address) {
			frappe.call({
				method: "frappe.contacts.doctype.address.address.get_address_display",
				args: {
					address_dict: frm.doc.supplier_primary_address,
				},
				callback: function (r) {
					frm.set_value("primary_address", frappe.utils.html2text(r.message));
				},
			});
		}
		if (!frm.doc.supplier_primary_address) {
			frm.set_value("primary_address", "");
		}
	},

	supplier_primary_contact: function (frm) {
		if (!frm.doc.supplier_primary_contact) {
			frm.set_value("mobile_no", "");
			frm.set_value("email_id", "");
		}
	},

	is_internal_supplier: function (frm) {
		if (frm.doc.is_internal_supplier == 1) {
			frm.toggle_reqd("represents_company", true);
		} else {
			frm.toggle_reqd("represents_company", false);
		}
	},
	show_party_link_dialog: function (frm) {
		const dialog = new frappe.ui.Dialog({
			title: __("Select a Customer"),
			fields: [
				{
					fieldtype: "Link",
					label: __("Customer"),
					options: "Customer",
					fieldname: "customer",
					reqd: 1,
				},
			],
			primary_action: function ({ customer }) {
				frappe.call({
					method: "erpnext.accounts.doctype.party_link.party_link.create_party_link",
					args: {
						primary_role: "Supplier",
						primary_party: frm.doc.name,
						secondary_party: customer,
					},
					freeze: true,
					callback: function () {
						dialog.hide();
						frappe.msgprint({
							message: __("Successfully linked to Customer"),
							alert: true,
						});
					},
					error: function () {
						dialog.hide();
						frappe.msgprint({
							message: __("Linking to Customer Failed. Please try again."),
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
| `IRS 1099` | Script Report | Regional |



### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Active Suppliers` | Active Suppliers | Count | Buying |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
