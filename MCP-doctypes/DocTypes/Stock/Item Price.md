# Master Control Plan: `Item Price`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** Log the selling and buying rate of an Item

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Purchase Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `packing_unit` | Packing Unit | Int | None |  |  |  | 0 | Quantity  that must be bought or sold per UOM |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `brand` | Brand | Link | Brand |  |  | ✅ | None | None |
| `item_description` | Item Description | Text | None |  |  | ✅ | None | None |
| `price_list_details` | Price List | Section Break | fa fa-tags |  |  |  | None | None |
| `price_list` | Price List | Link | Price List | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `buying` | Buying | Check | None |  |  | ✅ | 0 | None |
| `selling` | Selling | Check | None |  |  | ✅ | 0 | None |
| `item_details` | None | Section Break | fa fa-tag |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  | ✅ | None | None |
| `col_br_1` | None | Column Break | None |  |  |  | None | None |
| `price_list_rate` | Rate | Currency | currency | ✅ |  |  | None | None |
| `section_break_15` | None | Section Break | None |  |  |  | None | None |
| `valid_from` | Valid From | Date | None |  |  |  | Today | None |
| `lead_time_days` | Lead Time in days | Int | None |  |  |  | 0 | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `valid_upto` | Valid Up To | Date | None |  |  |  | None | None |
| `section_break_24` | None | Section Break | None |  |  |  | None | None |
| `note` | Note | Text | None |  |  |  | None | None |
| `reference` | Reference | Data | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/item_price/item_price.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Item Price", {
	setup(frm) {
		frm.set_query("item_code", function () {
			return {
				filters: {
					has_variants: 0,
				},
			};
		});
	},

	onload(frm) {
		// Fetch price list details
		frm.add_fetch("price_list", "buying", "buying");
		frm.add_fetch("price_list", "selling", "selling");
		frm.add_fetch("price_list", "currency", "currency");

		// Fetch item details
		frm.add_fetch("item_code", "item_name", "item_name");
		frm.add_fetch("item_code", "description", "item_description");
		frm.add_fetch("item_code", "stock_uom", "uom");

		frm.set_df_property(
			"bulk_import_help",
			"options",
			'<a href="/app/data-import-tool/Item Price">' + __("Import in Bulk") + "</a>"
		);

		frm.set_query("batch_no", function () {
			return {
				filters: {
					item: frm.doc.item_code,
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
| Name | Type | Module |
|---|---|---|
| `Item-wise Price List Rate` | Report Builder | Stock |



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
