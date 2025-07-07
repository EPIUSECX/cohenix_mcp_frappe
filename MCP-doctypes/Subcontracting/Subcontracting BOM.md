# Master Control Plan: `Subcontracting BOM`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Subcontracting`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:SB-{####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `is_active` | Is Active | Check | None |  |  |  | 1 | None |
| `section_break_dsjm` | None | Section Break | None |  |  |  | None | None |
| `finished_good` | Finished Good | Link | Item | ✅ |  |  | None | None |
| `finished_good_qty` | Finished Good Qty | Float | None | ✅ |  |  | 1 | None |
| `column_break_quoy` | None | Column Break | None |  |  |  | None | None |
| `finished_good_uom` | Finished Good UOM | Link | UOM |  |  | ✅ | None | None |
| `finished_good_bom` | Finished Good BOM | Link | BOM | ✅ |  |  | None | None |
| `section_break_qdw9` | None | Section Break | None |  |  |  | None | None |
| `service_item` | Service Item | Link | Item | ✅ |  |  | None | None |
| `service_item_qty` | Service Item Qty | Float | None | ✅ |  |  | 1 | None |
| `column_break_uzmw` | None | Column Break | None |  |  |  | None | None |
| `service_item_uom` | Service Item UOM | Link | UOM | ✅ |  |  | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  |  | ✅ | None | Service Item Qty / Finished Good Qty |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/subcontracting/doctype/subcontracting_bom/subcontracting_bom.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Subcontracting BOM", {
	setup: (frm) => {
		frm.trigger("set_queries");
	},

	set_queries: (frm) => {
		frm.set_query("finished_good", () => {
			return {
				filters: {
					disabled: 0,
					is_stock_item: 1,
					default_bom: ["!=", ""],
					is_sub_contracted_item: 1,
				},
			};
		});

		frm.set_query("finished_good_bom", () => {
			return {
				filters: {
					docstatus: 1,
					is_active: 1,
					item: frm.doc.finished_good,
				},
			};
		});

		frm.set_query("service_item", () => {
			return {
				filters: {
					disabled: 0,
					is_stock_item: 0,
				},
			};
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
