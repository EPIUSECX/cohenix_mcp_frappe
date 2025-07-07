# Master Control Plan: `Plaid Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `ERPNext Integrations`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enabled` | Enabled | Check | None |  |  |  | 0 | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `automatic_sync` | Synchronize all accounts every hour | Check | None |  |  |  | 0 | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `plaid_client_id` | Plaid Client ID | Data | None |  |  |  | None | None |
| `plaid_secret` | Plaid Secret | Password | None |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `plaid_env` | Plaid Environment | Select | sandbox
development
production |  |  |  | None | None |
| `enable_european_access` | Enable European Access | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/erpnext_integrations/doctype/plaid_settings/plaid_settings.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.integrations");

frappe.ui.form.on("Plaid Settings", {
	enabled: function (frm) {
		frm.toggle_reqd("plaid_client_id", frm.doc.enabled);
		frm.toggle_reqd("plaid_secret", frm.doc.enabled);
		frm.toggle_reqd("plaid_env", frm.doc.enabled);
	},

	refresh: function (frm) {
		if (frm.doc.enabled) {
			frm.add_custom_button(__("Link a new bank account"), () => {
				new erpnext.integrations.plaidLink(frm);
			});

			frm.add_custom_button(__("Reset Plaid Link"), () => {
				new erpnext.integrations.plaidLink(frm);
			});

			frm.add_custom_button(__("Sync Now"), () => {
				frappe.call({
					method: "erpnext.erpnext_integrations.doctype.plaid_settings.plaid_settings.enqueue_synchronization",
					freeze: true,
					callback: () => {
						let bank_transaction_link = frappe.utils.get_form_link(
							"Bank Transaction",
							"",
							true,
							__("Bank Transaction")
						);

						frappe.msgprint({
							title: __("Sync Started"),
							message: __(
								"The sync has started in the background, please check the {0} list for new records.",
								[bank_transaction_link]
							),
							alert: 1,
						});
					},
				});
			}).addClass("btn-primary");
		}
	},
});

erpnext.integrations.plaidLink = class plaidLink {
	constructor(parent) {
		this.frm = parent;
		this.plaidUrl = "https://cdn.plaid.com/link/v2/stable/link-initialize.js";
		this.init_config();
	}

	async init_config() {
		this.product = ["transactions"];
		this.plaid_env = this.frm.doc.plaid_env;
		this.client_name = frappe.boot.sitename;
		this.token = await this.get_link_token();
		this.init_plaid();
	}

	async get_link_token() {
		const token = await this.frm.call("get_link_token").then((resp) => resp.message);
		if (!token) {
			frappe.throw(__("Cannot retrieve link token. Check Error Log for more information"));
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
			if (document.querySelector('script[src="' + src + '"]')) {
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
			clientName: me.client_name,
			product: me.product,
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
		const me = this;

		frappe.prompt(
			{
				fieldtype: "Link",
				options: "Company",
				label: __("Company"),
				fieldname: "company",
				reqd: 1,
			},
			(data) => {
				me.company = data.company;
				frappe
					.xcall(
						"erpnext.erpnext_integrations.doctype.plaid_settings.plaid_settings.add_institution",
						{
							token: token,
							response: response,
						}
					)
					.then((result) => {
						frappe.xcall(
							"erpnext.erpnext_integrations.doctype.plaid_settings.plaid_settings.add_bank_accounts",
							{
								response: response,
								bank: result,
								company: me.company,
							}
						);
					})
					.then(() => {
						frappe.show_alert({ message: __("Bank accounts added"), indicator: "green" });
					});
			},
			__("Select a company"),
			__("Continue")
		);
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
