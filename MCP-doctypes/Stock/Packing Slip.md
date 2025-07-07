# Master Control Plan: `Packing Slip`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `MAT-PAC-.YYYY.-.#####`
- **Description:** Generate packing slips for packages to be delivered. Used to notify package number, package contents and its weight.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Stock User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Item Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `packing_slip_details` | None | Section Break | None |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `delivery_note` | Delivery Note | Link | Delivery Note | ✅ |  |  | None | Indicates that the package is a part of this delivery (Only Draft) |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `naming_series` | Series | Select | MAT-PAC-.YYYY.- | ✅ |  |  | None | None |
| `section_break0` | None | Section Break | None |  |  |  | None | None |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `from_case_no` | From Package No. | Int | None | ✅ |  |  | None | Identification of the package for the delivery (for print) |
| `column_break3` | None | Column Break | None |  |  |  | None | None |
| `to_case_no` | To Package No. | Int | None |  |  |  | None | If more than one package of the same type (for print) |
| `package_item_details` | None | Section Break | None |  |  |  | None | None |
| `items` | Items | Table | Packing Slip Item | ✅ |  |  | None | None |
| `package_weight_details` | Package Weight Details | Section Break | None |  |  |  | None | None |
| `net_weight_pkg` | Net Weight | Float | None |  |  | ✅ | None | The net weight of this package. (calculated automatically as sum of net weight of items) |
| `net_weight_uom` | Net Weight UOM | Link | UOM |  |  | ✅ | None | None |
| `column_break4` | None | Column Break | None |  |  |  | None | None |
| `gross_weight_pkg` | Gross Weight | Float | None |  |  |  | None | The gross weight of the package. Usually net weight + packaging material weight. (for print) |
| `gross_weight_uom` | Gross Weight UOM | Link | UOM |  |  |  | None | None |
| `letter_head_details` | Letter Head | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `misc_details` | None | Section Break | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Packing Slip |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/packing_slip/packing_slip.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Packing Slip", {
	setup: (frm) => {
		frm.set_query("delivery_note", () => {
			return {
				filters: {
					docstatus: 0,
				},
			};
		});

		frm.set_query("item_code", "items", (doc, cdt, cdn) => {
			if (!doc.delivery_note) {
				frappe.throw(__("Please select a Delivery Note"));
			} else {
				let d = locals[cdt][cdn];
				return {
					query: "erpnext.stock.doctype.packing_slip.packing_slip.item_details",
					filters: {
						delivery_note: doc.delivery_note,
					},
				};
			}
		});
	},

	refresh: (frm) => {
		frm.toggle_display("misc_details", frm.doc.amended_from);
	},

	delivery_note: (frm) => {
		frm.set_value("items", null);

		if (frm.doc.delivery_note) {
			erpnext.utils.map_current_doc({
				method: "erpnext.stock.doctype.delivery_note.delivery_note.make_packing_slip",
				source_name: frm.doc.delivery_note,
				target_doc: frm,
				freeze: true,
				freeze_message: __("Creating Packing Slip ..."),
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
