# Master Control Plan: `Vehicle Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Fleet Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `vehicle_section` | None | Section Break | fa fa-user |  |  |  | None | None |
| `naming_series` | Series | Select | HR-VLOG-.YYYY.- | ✅ |  |  | None | None |
| `license_plate` | License Plate | Link | Vehicle | ✅ |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `model` | Model | Read Only | None |  |  |  | None | None |
| `make` | Make | Read Only | None |  |  |  | None | None |
| `odometer_reading` | Odometer Reading | Section Break | None |  |  |  | None | None |
| `date` | Date | Date | None | ✅ |  |  | None | None |
| `odometer` | Current Odometer value  | Int | None | ✅ |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `last_odometer` | Last Odometer Value  | Int | None | ✅ |  | ✅ | None | None |
| `refuelling_details` | Refuelling Details | Section Break | None |  |  |  | None | None |
| `fuel_qty` | Fuel Qty | Float | None |  |  |  | None | None |
| `price` | Fuel Price | Currency | None |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `invoice` | Invoice Ref | Data | None |  |  |  | None | None |
| `service_details` | Service Details | Section Break | None |  |  |  | None | None |
| `service_detail` | None | Table | Vehicle Service |  |  |  | None | None |
| `amended_from` | Amended From | Link | Vehicle Log |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/vehicle_log/vehicle_log.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Vehicle Log", {
	setup: function (frm) {
		frm.set_query("employee", function () {
			return {
				filters: {
					status: "Active",
				},
			};
		});
	},
	refresh: function (frm) {
		if (frm.doc.docstatus == 1) {
			frm.add_custom_button(
				__("Expense Claim"),
				function () {
					frm.events.expense_claim(frm);
				},
				__("Create"),
			);
			frm.page.set_inner_btn_group_as_primary(__("Create"));
		}
	},

	expense_claim: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.vehicle_log.vehicle_log.make_expense_claim",
			args: {
				docname: frm.doc.name,
			},
			callback: function (r) {
				var doc = frappe.model.sync(r.message);
				frappe.set_route("Form", "Expense Claim", r.message.name);
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
