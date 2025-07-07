# Master Control Plan: `Blanket Order`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | MFG-BLR-.YYYY.- | ✅ |  |  | None | None |
| `blanket_order_type` | Order Type | Select | 
Selling
Purchasing | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  |  | ✅ | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `supplier_name` | Supplier Name | Data | None |  |  | ✅ | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `order_no` | Order No | Data | None |  |  |  | None | None |
| `order_date` | Order Date | Date | None |  |  |  | None | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `to_date` | To Date | Date | None | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `section_break_12` | None | Section Break | None |  |  |  | None | None |
| `items` | Item | Table | Blanket Order Item | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Blanket Order |  |  | ✅ | None | None |
| `terms_and_conditions_section` | Terms and Conditions | Section Break | None |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions Details | Text Editor | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/blanket_order/blanket_order.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Blanket Order", {
	onload: function (frm) {
		frm.trigger("set_tc_name_filter");
	},

	setup: function (frm) {
		frm.custom_make_buttons = {
			"Purchase Order": "Purchase Order",
			"Sales Order": "Sales Order",
			Quotation: "Quotation",
		};

		frm.add_fetch("customer", "customer_name", "customer_name");
		frm.add_fetch("supplier", "supplier_name", "supplier_name");
	},

	refresh: function (frm) {
		erpnext.hide_company(frm);
		if (frm.doc.customer && frm.doc.docstatus === 1 && frm.doc.to_date > frappe.datetime.get_today()) {
			frm.add_custom_button(
				__("Sales Order"),
				function () {
					frappe.model.open_mapped_doc({
						method: "erpnext.manufacturing.doctype.blanket_order.blanket_order.make_order",
						frm: frm,
						args: {
							doctype: "Sales Order",
						},
					});
				},
				__("Create")
			);

			frm.add_custom_button(
				__("Quotation"),
				function () {
					frappe.model.open_mapped_doc({
						method: "erpnext.manufacturing.doctype.blanket_order.blanket_order.make_order",
						frm: frm,
						args: {
							doctype: "Quotation",
						},
					});
				},
				__("Create")
			);
		}

		if (frm.doc.supplier && frm.doc.docstatus === 1) {
			frm.add_custom_button(
				__("Purchase Order"),
				function () {
					frappe.model.open_mapped_doc({
						method: "erpnext.manufacturing.doctype.blanket_order.blanket_order.make_order",
						frm: frm,
						args: {
							doctype: "Purchase Order",
						},
					});
				},
				__("Create")
			);
		}
	},

	onload_post_render: function (frm) {
		frm.get_field("items").grid.set_multiple_add("item_code", "qty");
	},

	tc_name: function (frm) {
		erpnext.utils.get_terms(frm.doc.tc_name, frm.doc, function (r) {
			if (!r.exc) {
				frm.set_value("terms", r.message);
			}
		});
	},

	set_tc_name_filter: function (frm) {
		if (frm.doc.blanket_order_type === "Selling") {
			frm.set_df_property("customer", "reqd", 1);
			frm.set_df_property("supplier", "reqd", 0);
			frm.set_value("supplier", "");

			frm.set_query("tc_name", function () {
				return { filters: { selling: 1 } };
			});
		}
		if (frm.doc.blanket_order_type === "Purchasing") {
			frm.set_df_property("supplier", "reqd", 1);
			frm.set_df_property("customer", "reqd", 0);
			frm.set_value("customer", "");

			frm.set_query("tc_name", function () {
				return { filters: { buying: 1 } };
			});
		}
	},

	blanket_order_type: function (frm) {
		frm.trigger("set_tc_name_filter");
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
