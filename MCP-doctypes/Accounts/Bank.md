# Master Control Plan: `Bank`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:bank_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `bank_details_section` | Bank Details | Section Break | None |  |  |  | None | None |
| `bank_name` | Bank Name | Data | None | ✅ |  |  | None | None |
| `swift_number` | SWIFT number | Data | None |  |  |  | None | None |
| `column_break_1` | None | Column Break | None |  |  |  | None | None |
| `website` | Website | Data | None |  |  |  | None | None |
| `address_and_contact` | Address and Contact | Section Break | fa fa-map-marker |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  |  | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  |  | None | None |
| `data_import_configuration_section` | Data Import Configuration | Section Break | None |  |  |  | None | None |
| `bank_transaction_mapping` | Bank Transaction Mapping | Table | Bank Transaction Mapping |  |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `plaid_access_token` | Plaid Access Token | Data | None |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank/bank.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt
frappe.provide("erpnext.integrations");

frappe.ui.form.on("Bank", {
	onload: function (frm) {
		add_fields_to_mapping_table(frm);
	},
	refresh: function (frm) {
		add_fields_to_mapping_table(frm);
		frm.toggle_display(["address_html", "contact_html"], !frm.doc.__islocal);

		if (frm.doc.__islocal) {
			frm.set_df_property("address_and_contact", "hidden", 1);
			frappe.contacts.clear_address_and_contact(frm);
		} else {
			frm.set_df_property("address_and_contact", "hidden", 0);
			frappe.contacts.render_address_and_contact(frm);
		}
		if (frm.doc.plaid_access_token) {
			frm.add_custom_button(__("Refresh Plaid Link"), () => {
				new erpnext.integrations.refreshPlaidLink(frm.doc.plaid_access_token);
			});
		}
	},
});

let add_fields_to_mapping_table = function (frm) {
	let options = [];

	frappe.model.with_doctype("Bank Transaction", function () {
		let meta = frappe.get_meta("Bank Transaction");
		meta.fields.forEach((value) => {
			if (!["Section Break", "Column Break"].includes(value.fieldtype)) {
				options.push(value.fieldname);
			}
		});
	});

	frm.fields_dict.bank_transaction_mapping.grid.update_docfield_property(
		"bank_transaction_field",
		"options",
		options
	);
};

erpnext.integrations.refreshPlaidLink = class refreshPlaidLink {
	constructor(access_token) {
		this.access_token = access_token;
		this.plaidUrl = "https://cdn.plaid.com/link/v2/stable/link-initialize.js";
		this.init_config();
	}

	async init_config() {
		this.plaid_env = await frappe.db.get_single_value("Plaid Settings", "plaid_env");
		this.token = await this.get_link_token_for_update();
		this.init_plaid();
	}

	async get_link_token_for_update() {
		const token = frappe.xcall(
			"erpnext.erpnext_integrations.doctype.plaid_settings.plaid_settings.get_link_token_for_update",
			{ access_token: this.access_token }
		);
		if (!token) {
			frappe.throw(__("Cannot retrieve link token for update. Check Error Log for more information"));
		}
		return token;
	}

	init_plaid() {
		const me = this;
		me.loadScript(me.plaidUrl)
			.then(() => {
				me.onScriptLoaded(me);
			})
			.then(() => {
				if (me.linkHandler) {
					me.linkHandler.open();
				}
			})
			.catch((error) => {
				me.onScriptError(error);
			});
	}

	loadScript(src) {
		return new Promise(function (resolve, reject) {
			if (document.querySelector("script[src='" + src + "']")) {
				resolve();
				return;
			}
			const el = document.createElement("script");
			el.type = "text/javascript";
			el.async = true;
			el.src = src;
			el.addEventListener("load", resolve);
			el.addEventListener("error", reject);
			el.addEventListener("abort", reject);
			document.head.appendChild(el);
		});
	}

	onScriptLoaded(me) {
		me.linkHandler = Plaid.create({
			// eslint-disable-line no-undef
			env: me.plaid_env,
			token: me.token,
			onSuccess: me.plaid_success,
		});
	}

	onScriptError(error) {
		frappe.msgprint(
			__(
				"There was an issue connecting to Plaid's authentication server. Check browser console for more information"
			)
		);
		console.log(error);
	}

	plaid_success(token, response) {
		frappe
			.xcall(
				"erpnext.erpnext_integrations.doctype.plaid_settings.plaid_settings.update_bank_account_ids",
				{
					response: response,
				}
			)
			.then(() => {
				frappe.show_alert({ message: __("Plaid Link Updated"), indicator: "green" });
			});
	}
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
