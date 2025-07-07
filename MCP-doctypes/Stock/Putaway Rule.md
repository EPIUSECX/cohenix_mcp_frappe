# Master Control Plan: `Putaway Rule`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `PUT-.####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| Stock Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `disable` | Disable | Check | None |  |  |  | 0 | None |
| `item_code` | Item | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `warehouse` | Warehouse | Link | Warehouse | ✅ |  |  | None | None |
| `priority` | Priority | Int | None |  |  |  | 1 | None |
| `col_break_capacity` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `capacity` | Capacity | Float | None | ✅ |  |  | 0 | None |
| `uom` | UOM | Link | UOM |  |  |  | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  |  | ✅ | 1 | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `stock_capacity` | Capacity in Stock UOM | Float | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/putaway_rule/putaway_rule.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Putaway Rule", {
	setup: function (frm) {
		frm.set_query("warehouse", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});
	},

	uom: function (frm) {
		if (frm.doc.item_code && frm.doc.uom) {
			return frm.call({
				method: "erpnext.stock.get_item_details.get_conversion_factor",
				args: {
					item_code: frm.doc.item_code,
					uom: frm.doc.uom,
				},
				callback: function (r) {
					if (!r.exc) {
						let stock_capacity = flt(frm.doc.capacity) * flt(r.message.conversion_factor);
						frm.set_value("conversion_factor", r.message.conversion_factor);
						frm.set_value("stock_capacity", stock_capacity);
					}
				},
			});
		}
	},

	capacity: function (frm) {
		let stock_capacity = flt(frm.doc.capacity) * flt(frm.doc.conversion_factor);
		frm.set_value("stock_capacity", stock_capacity);
	},

	// refresh: function(frm) {

	// }
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
