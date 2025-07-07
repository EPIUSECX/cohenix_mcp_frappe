# Master Control Plan: `BOM Update Tool`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Replace a particular BOM in all other BOMs where it is used. It will replace the old BOM link, update cost and regenerate "BOM Explosion Item" table as per new BOM.
It also updates latest price in all the BOMs.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `replace_bom_section` | Replace BOM | Section Break | None |  |  |  | None | None |
| `current_bom` | Current BOM | Link | BOM | ✅ |  |  | None | The BOM which will be replaced |
| `new_bom` | New BOM | Link | BOM | ✅ |  |  | None | The new BOM after replacement |
| `replace` | Replace | Button | None |  |  |  | None | None |
| `update_cost_section` | Update Cost | Section Break | None |  |  |  | None | None |
| `update_latest_price_in_all_boms` | Update latest price in all BOMs | Button | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/bom_update_tool/bom_update_tool.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("BOM Update Tool", {
	setup: function (frm) {
		frm.set_query("current_bom", function () {
			return {
				query: "erpnext.controllers.queries.bom",
				filters: { name: "!" + frm.doc.new_bom },
			};
		});

		frm.set_query("new_bom", function () {
			return {
				query: "erpnext.controllers.queries.bom",
				filters: { name: "!" + frm.doc.current_bom },
			};
		});
	},

	refresh: function (frm) {
		frm.disable_save();
		frm.events.disable_button(frm, "replace");

		frm.add_custom_button(__("View BOM Update Log"), () => {
			frappe.set_route("List", "BOM Update Log");
		});
	},

	disable_button: (frm, field, disable = true) => {
		frm.get_field(field).input.disabled = disable;
	},

	current_bom: (frm) => {
		if (frm.doc.current_bom && frm.doc.new_bom) {
			frm.events.disable_button(frm, "replace", false);
		}
	},

	new_bom: (frm) => {
		if (frm.doc.current_bom && frm.doc.new_bom) {
			frm.events.disable_button(frm, "replace", false);
		}
	},

	replace: (frm) => {
		if (frm.doc.current_bom && frm.doc.new_bom) {
			frappe.call({
				method: "erpnext.manufacturing.doctype.bom_update_tool.bom_update_tool.enqueue_replace_bom",
				freeze: true,
				args: {
					boms: {
						current_bom: frm.doc.current_bom,
						new_bom: frm.doc.new_bom,
					},
				},
				callback: (result) => {
					if (result && result.message && !result.exc) {
						frm.events.confirm_job_start(frm, result.message);
					}
				},
			});
		}
	},

	update_latest_price_in_all_boms: (frm) => {
		frappe.call({
			method: "erpnext.manufacturing.doctype.bom_update_tool.bom_update_tool.enqueue_update_cost",
			freeze: true,
			callback: (result) => {
				if (result && result.message && !result.exc) {
					frm.events.confirm_job_start(frm, result.message);
				}
			},
		});
	},

	confirm_job_start: (frm, log_data) => {
		let log_link = frappe.utils.get_form_link("BOM Update Log", log_data.name, true);
		frappe.msgprint({
			message: __("BOM Updation is queued and may take a few minutes. Check {0} for progress.", [
				log_link,
			]),
			title: __("BOM Update Initiated"),
			indicator: "blue",
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
