# Master Control Plan: `Quick Stock Balance`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| Stock User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `warehouse` | Warehouse | Link | Warehouse | ✅ |  |  | None | None |
| `date` | Date | Date | None | ✅ |  |  | Today | None |
| `item_barcode` | Item Barcode | Data | None |  |  |  | None | None |
| `item` | Item Code | Link | Item | ✅ |  |  | None | None |
| `col_break` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `item_description` | Item Description | Small Text | None |  |  | ✅ |    | None |
| `image` | Image View | Image | image |  |  |  | None | None |
| `sec_break` | None | Section Break | None |  |  |  | None | None |
| `qty` | Available Quantity | Float | None |  |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `value` | Stock Value | Currency | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/quick_stock_balance/quick_stock_balance.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Quick Stock Balance", {
	setup: (frm) => {
		frm.set_query("item", () => {
			if (!(frm.doc.warehouse && frm.doc.date)) {
				frm.trigger("check_warehouse_and_date");
			}
		});
	},

	make_custom_stock_report_button: (frm) => {
		if (frm.doc.item) {
			frm.add_custom_button(__("Stock Balance Report"), () => {
				frappe.set_route("query-report", "Stock Balance", {
					item_code: frm.doc.item,
					warehouse: frm.doc.warehouse,
				});
			});
		}
	},

	refresh: (frm) => {
		frm.disable_save();
		frm.trigger("make_custom_stock_report_button");
	},

	check_warehouse_and_date: (frm) => {
		frappe.msgprint(__("Please enter Warehouse and Date"));
		frm.doc.item = "";
		frm.refresh();
	},

	warehouse: (frm) => {
		if (frm.doc.item || frm.doc.item_barcode) {
			frm.trigger("get_stock_and_item_details");
		}
	},

	date: (frm) => {
		if (frm.doc.item || frm.doc.item_barcode) {
			frm.trigger("get_stock_and_item_details");
		}
	},

	item: (frm) => {
		frappe.flags.last_updated_element = "item";
		frm.trigger("get_stock_and_item_details");
		frm.trigger("make_custom_stock_report_button");
	},

	item_barcode: (frm) => {
		frappe.flags.last_updated_element = "item_barcode";
		frm.trigger("get_stock_and_item_details");
		frm.trigger("make_custom_stock_report_button");
	},

	get_stock_and_item_details: (frm) => {
		if (!(frm.doc.warehouse && frm.doc.date)) {
			frm.trigger("check_warehouse_and_date");
		} else if (frm.doc.item || frm.doc.item_barcode) {
			let filters = {
				warehouse: frm.doc.warehouse,
				date: frm.doc.date,
			};
			if (frappe.flags.last_updated_element === "item") {
				filters = { ...filters, ...{ item: frm.doc.item } };
			} else {
				filters = { ...filters, ...{ barcode: frm.doc.item_barcode } };
			}
			frappe.call({
				method: "erpnext.stock.doctype.quick_stock_balance.quick_stock_balance.get_stock_item_details",
				args: filters,
				callback: (r) => {
					if (r.message) {
						let fields = ["item", "qty", "value", "image"];
						if (!r.message["barcodes"].includes(frm.doc.item_barcode)) {
							frm.doc.item_barcode = "";
							frm.refresh();
						}
						fields.forEach(function (field) {
							frm.set_value(field, r.message[field]);
						});
					}
				},
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
