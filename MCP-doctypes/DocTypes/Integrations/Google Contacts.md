# Master Control Plan: `Google Contacts`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Integrations`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:GC-{email_id}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enable` | Enable | Check | None |  |  |  | 0 | None |
| `sb_00` | Google Contacts | Section Break | None |  |  |  | None | None |
| `email_id` | Email Address | Data | Email | ✅ |  |  | None | Email Address whose Google Contacts are to be synced. |
| `authorize_google_contacts_access` | Authorize Google Contacts Access | Button | None |  |  |  | None | None |
| `cb_00` | None | Column Break | None |  |  |  | None | None |
| `last_sync_on` | Last Sync On | Datetime | None |  |  | ✅ | None | None |
| `authorization_code` | Authorization Code | Password | None |  | ✅ |  | None | None |
| `refresh_token` | Refresh Token | Password | None |  | ✅ |  | None | None |
| `next_sync_token` | Next Sync Token | Password | None |  | ✅ |  | None | None |
| `sync` | Sync | Section Break | None |  |  |  | None | None |
| `pull_from_google_contacts` | Pull from Google Contacts | Check | None |  |  |  | 0 | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `push_to_google_contacts` | Push to Google Contacts | Check | None |  |  |  | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/google_contacts/google_contacts.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Google Contacts", {
	refresh: function (frm) {
		if (!frm.doc.enable) {
			frm.dashboard.set_headline(
				__("To use Google Contacts, enable {0}.", [
					`<a href='/app/google-settings'>${__("Google Settings")}</a>`,
				])
			);
		}

		frappe.realtime.on("import_google_contacts", (data) => {
			if (data.progress) {
				frm.dashboard.show_progress(
					"Import Google Contacts",
					(data.progress / data.total) * 100,
					__("Importing {0} of {1}", [data.progress, data.total])
				);
				if (data.progress === data.total) {
					frm.dashboard.hide_progress("Import Google Contacts");
				}
			}
		});

		if (frm.doc.refresh_token) {
			let sync_button = frm.add_custom_button(__("Sync Contacts"), function () {
				frappe.show_alert({
					indicator: "green",
					message: __("Syncing"),
				});
				frappe
					.call({
						method: "frappe.integrations.doctype.google_contacts.google_contacts.sync",
						args: {
							g_contact: frm.doc.name,
						},
						btn: sync_button,
					})
					.then((r) => {
						frappe.hide_progress();
						frappe.msgprint(r.message);
					});
			});
		}
	},
	authorize_google_contacts_access: function (frm) {
		frappe.call({
			method: "frappe.integrations.doctype.google_contacts.google_contacts.authorize_access",
			args: {
				g_contact: frm.doc.name,
				reauthorize: frm.doc.authorization_code ? 1 : 0,
			},
			callback: function (r) {
				if (!r.exc) {
					frm.save();
					window.open(r.message.url);
				}
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
