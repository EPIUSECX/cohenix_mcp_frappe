# Master Control Plan: `Accounting Dimension`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:label`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `document_type` | Reference Document Type | Link | DocType | ✅ |  |  | None | None |
| `label` | Dimension Name | Data | None |  |  |  | None | None |
| `fieldname` | Fieldname | Data | None |  | ✅ |  | None | None |
| `dimension_defaults` | Dimension Defaults | Table | Accounting Dimension Detail |  |  |  | None | None |
| `disabled` | Disable | Check | None |  | ✅ | ✅ | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/accounting_dimension/accounting_dimension.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Accounting Dimension", {
	refresh: function (frm) {
		frm.set_query("document_type", () => {
			let invalid_doctypes = frappe.model.core_doctypes_list;
			invalid_doctypes.push(
				"Accounting Dimension",
				"Project",
				"Cost Center",
				"Accounting Dimension Detail",
				"Company"
			);

			return {
				filters: {
					name: ["not in", invalid_doctypes],
				},
			};
		});

		frm.set_query("offsetting_account", "dimension_defaults", function (doc, cdt, cdn) {
			let d = locals[cdt][cdn];
			return {
				filters: {
					company: d.company,
					root_type: ["in", ["Asset", "Liability"]],
					is_group: 0,
				},
			};
		});

		if (!frm.is_new()) {
			frm.add_custom_button(__("Show {0}", [frm.doc.document_type]), function () {
				frappe.set_route("List", frm.doc.document_type);
			});

			let button = frm.doc.disabled ? "Enable" : "Disable";

			frm.add_custom_button(__(button), function () {
				frm.set_value("disabled", 1 - frm.doc.disabled);

				frappe.call({
					method: "erpnext.accounts.doctype.accounting_dimension.accounting_dimension.disable_dimension",
					args: {
						doc: frm.doc,
					},
					freeze: true,
					callback: function (r) {
						let message = frm.doc.disabled ? "Dimension Disabled" : "Dimension Enabled";
						frm.save();
						frappe.show_alert({ message: __(message), indicator: "green" });
					},
				});
			});
		}
	},

	label: function (frm) {
		frm.set_value("fieldname", frm.doc.label.replace(/ /g, "_").replace(/-/g, "_").toLowerCase());
	},

	document_type: function (frm) {
		frm.set_value("label", frm.doc.document_type);

		frappe.db.get_value(
			"Accounting Dimension",
			{ document_type: frm.doc.document_type },
			"document_type",
			(r) => {
				if (r && r.document_type) {
					frm.set_df_property(
						"document_type",
						"description",
						"Document type is already set as dimension"
					);
				}
			}
		);
	},
});

frappe.ui.form.on("Accounting Dimension Detail", {
	dimension_defaults_add: function (frm, cdt, cdn) {
		let row = locals[cdt][cdn];
		row.reference_document = frm.doc.document_type;
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
