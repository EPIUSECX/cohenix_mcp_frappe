# Master Control Plan: `DocType Layout`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Custom`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `document_type` | Document Type | Link | DocType | ✅ |  |  | None | None |
| `route` | Route | Data | None | ✅ |  |  | None | None |
| `fields` | Fields | Table | DocType Layout Field | ✅ |  |  | None | None |
| `client_script` | Client Script | Code | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/custom/doctype/doctype_layout/doctype_layout.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("DocType Layout", {
	onload_post_render(frm) {
		// disallow users from manually adding/deleting rows; this doctype should only
		// be used for managing layout, and docfields and custom fields should be used
		// to manage other field metadata (hidden, etc.)
		frm.set_df_property("fields", "cannot_add_rows", true);
		frm.set_df_property("fields", "cannot_delete_rows", true);

		$(frm.wrapper).on("grid-move-row", (e, frm) => {
			// refresh the layout after moving a row
			frm.dirty();
		});
	},

	refresh(frm) {
		frm.events.add_buttons(frm);
	},

	async document_type(frm) {
		if (frm.doc.document_type) {
			// refreshing the doctype fields resets the new name input field;
			// once the fields are set, reset the name to the original input
			if (frm.is_new()) {
				const document_name = frm.doc.__newname || frm.doc.name;
			}

			frm.set_value("fields", []);
			await frm.events.sync_fields(frm, false);

			if (frm.is_new()) {
				frm.doc.__newname = document_name; // eslint-disable-line
				frm.refresh_field("__newname");
			}
		}
	},

	add_buttons(frm) {
		if (!frm.is_new()) {
			frm.add_custom_button(__("Go to {0} List", [frm.doc.name]), () => {
				window.open(`/app/${frappe.router.slug(frm.doc.name)}`);
			});

			frm.add_custom_button(__("Sync {0} Fields", [frm.doc.name]), async () => {
				await frm.events.sync_fields(frm, true);
			});
		}
	},

	async sync_fields(frm, notify) {
		frappe.dom.freeze("Fetching fields...");
		const response = await frm.call({ doc: frm.doc, method: "sync_fields" });
		frm.refresh_field("fields");
		frappe.dom.unfreeze();

		if (!response.message) {
			frappe.msgprint(__("No changes to sync"));
			return;
		}

		frm.dirty();
		if (notify) {
			const addedFields = response.message.added;
			const removedFields = response.message.removed;

			const getChangedMessage = (fields) => {
				let changes = "";
				for (const field of fields) {
					if (field.label) {
						changes += `<li>Row #${field.idx}: ${field.fieldname.bold()} (${
							field.label
						})</li>`;
					} else {
						changes += `<li>Row #${field.idx}: ${field.fieldname.bold()}</li>`;
					}
				}
				return changes;
			};

			let message = "";

			if (addedFields.length) {
				message += `The following fields have been added:<br><br><ul>${getChangedMessage(
					addedFields
				)}</ul>`;
			}

			if (removedFields.length) {
				message += `The following fields have been removed:<br><br><ul>${getChangedMessage(
					removedFields
				)}</ul>`;
			}

			if (message) {
				frappe.msgprint({
					message: __(message),
					indicator: "green",
					title: __("Synced Fields"),
				});
			}
		}
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
