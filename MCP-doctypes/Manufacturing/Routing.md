# Master Control Plan: `Routing`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:routing_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Manufacturing User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `routing_name` | Routing Name | Data | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `operations` | BOM Operation | Table | BOM Operation |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/routing/routing.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Routing", {
	refresh: function (frm) {
		frm.trigger("display_sequence_id_column");
	},

	onload: function (frm) {
		frm.trigger("display_sequence_id_column");
	},

	display_sequence_id_column: function (frm) {
		frm.fields_dict.operations.grid.update_docfield_property("sequence_id", "in_list_view", 1);
	},

	calculate_operating_cost: function (frm, child) {
		const operating_cost = flt(
			(flt(child.hour_rate) * flt(child.time_in_mins)) / 60,
			precision("operating_cost", child)
		);
		frappe.model.set_value(child.doctype, child.name, "operating_cost", operating_cost);
	},
});

frappe.ui.form.on("BOM Operation", {
	operation: function (frm, cdt, cdn) {
		const d = locals[cdt][cdn];

		if (!d.operation) return;

		frappe.call({
			method: "frappe.client.get",
			args: {
				doctype: "Operation",
				name: d.operation,
			},
			callback: function (data) {
				if (data.message.description) {
					frappe.model.set_value(d.doctype, d.name, "description", data.message.description);
				}

				if (data.message.workstation) {
					frappe.model.set_value(d.doctype, d.name, "workstation", data.message.workstation);
				}

				frm.events.calculate_operating_cost(frm, d);
			},
		});
	},

	workstation: function (frm, cdt, cdn) {
		const d = locals[cdt][cdn];
		if (!d.workstation) return;
		frappe.call({
			method: "frappe.client.get",
			args: {
				doctype: "Workstation",
				name: d.workstation,
			},
			callback: function (data) {
				frappe.model.set_value(d.doctype, d.name, "hour_rate", data.message.hour_rate);
				frm.events.calculate_operating_cost(frm, d);
			},
		});
	},

	time_in_mins: function (frm, cdt, cdn) {
		const d = locals[cdt][cdn];
		frm.events.calculate_operating_cost(frm, d);
	},
});

frappe.tour["Routing"] = [
	{
		fieldname: "routing_name",
		title: "Routing Name",
		description: __("Enter a name for Routing."),
	},
	{
		fieldname: "operations",
		title: "BOM Operations",
		description: __(
			"Enter the Operation, the table will fetch the Operation details like Hourly Rate, Workstation automatically.\n\n After that, set the Operation Time in minutes and the table will calculate the Operation Costs based on the Hourly Rate and Operation Time."
		),
	},
];

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
