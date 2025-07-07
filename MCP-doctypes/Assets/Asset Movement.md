# Master Control Plan: `Asset Movement`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `format:ACC-ASM-{YYYY}-{#####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `purpose` | Purpose | Select | 
Issue
Receipt
Transfer
Transfer and Issue | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `transaction_date` | Transaction Date | Datetime | None | ✅ |  |  | Now | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `assets` | Assets | Table | Asset Movement Item | ✅ |  |  | None | None |
| `reference` | Reference | Section Break | None |  |  |  | None | None |
| `reference_doctype` | Reference Document Type | Link | DocType |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `reference_name` | Reference Document Name | Dynamic Link | reference_doctype |  |  |  | None | None |
| `amended_from` | Amended From | Link | Asset Movement |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 1
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_movement/asset_movement.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Asset Movement", {
	setup: (frm) => {
		frm.set_query("to_employee", "assets", (doc) => {
			return {
				filters: {
					company: doc.company,
				},
			};
		});
		frm.set_query("from_employee", "assets", (doc) => {
			return {
				filters: {
					company: doc.company,
				},
			};
		});
		frm.set_query("reference_name", (doc) => {
			return {
				filters: {
					company: doc.company,
					docstatus: 1,
				},
			};
		});
		frm.set_query("reference_doctype", () => {
			return {
				filters: {
					name: ["in", ["Purchase Receipt", "Purchase Invoice"]],
				},
			};
		}),
			frm.set_query("asset", "assets", () => {
				return {
					filters: {
						status: ["not in", ["Draft"]],
					},
				};
			});
	},

	onload: (frm) => {
		frm.trigger("set_required_fields");
	},

	purpose: (frm) => {
		frm.trigger("set_required_fields");
	},

	set_required_fields: (frm, cdt, cdn) => {
		let fieldnames_to_be_altered;
		if (frm.doc.purpose === "Transfer") {
			fieldnames_to_be_altered = {
				target_location: { read_only: 0, reqd: 1 },
				source_location: { read_only: 1, reqd: 1 },
				from_employee: { read_only: 1, reqd: 0 },
				to_employee: { read_only: 1, reqd: 0 },
			};
		} else if (frm.doc.purpose === "Receipt") {
			fieldnames_to_be_altered = {
				target_location: { read_only: 0, reqd: 1 },
				source_location: { read_only: 1, reqd: 0 },
				from_employee: { read_only: 1, reqd: 0 },
				to_employee: { read_only: 0, reqd: 0 },
			};
		} else if (frm.doc.purpose === "Issue") {
			fieldnames_to_be_altered = {
				target_location: { read_only: 1, reqd: 0 },
				source_location: { read_only: 1, reqd: 0 },
				from_employee: { read_only: 1, reqd: 0 },
				to_employee: { read_only: 0, reqd: 1 },
			};
		} else if (frm.doc.purpose === "Transfer and Issue") {
			fieldnames_to_be_altered = {
				target_location: { read_only: 0, reqd: 1 },
				source_location: { read_only: 0, reqd: 1 },
				from_employee: { read_only: 0, reqd: 1 },
				to_employee: { read_only: 0, reqd: 1 },
			};
		}
		if (fieldnames_to_be_altered) {
			Object.keys(fieldnames_to_be_altered).forEach((fieldname) => {
				let property_to_be_altered = fieldnames_to_be_altered[fieldname];
				Object.keys(property_to_be_altered).forEach((property) => {
					let value = property_to_be_altered[property];
					frm.fields_dict["assets"].grid.update_docfield_property(fieldname, property, value);
				});
			});
			frm.refresh_field("assets");
		}
	},
});

frappe.ui.form.on("Asset Movement Item", {
	asset: function (frm, cdt, cdn) {
		// on manual entry of an asset auto sets their source location / employee
		const asset_name = locals[cdt][cdn].asset;
		if (asset_name) {
			frappe.db
				.get_doc("Asset", asset_name)
				.then((asset_doc) => {
					if (asset_doc.location)
						frappe.model.set_value(cdt, cdn, "source_location", asset_doc.location);
					if (asset_doc.custodian)
						frappe.model.set_value(cdt, cdn, "from_employee", asset_doc.custodian);
				})
				.catch((err) => {
					console.log(err); // eslint-disable-line
				});
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
