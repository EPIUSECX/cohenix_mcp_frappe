# Master Control Plan: `Serial No`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:serial_no`
- **Description:** Distinct unit of an Item

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Item Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `details` | None | Section Break | None |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Data | None | ✅ |  |  | None | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  | ✅ | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  | ✅ | None | None |
| `purchase_rate` | Incoming Rate | Float | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Active
Inactive
Consumed
Delivered
Expired |  |  | ✅ | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `description` | Description | Text | None |  |  | ✅ | None | None |
| `item_group` | Item Group | Link | Item Group |  |  | ✅ | None | None |
| `brand` | Brand | Link | Brand |  |  | ✅ | None | None |
| `asset_details` | Asset Details | Section Break | None |  |  |  | None | None |
| `asset` | Asset | Link | Asset |  |  | ✅ | None | None |
| `asset_status` | Asset Status | Select | 
Issue
Receipt
Transfer |  |  | ✅ | None | None |
| `column_break_24` | None | Column Break | None |  |  |  | None | None |
| `location` | Location | Link | Location |  |  | ✅ | None | None |
| `employee` | Employee | Link | Employee |  |  | ✅ | None | None |
| `warranty_amc_details` | Warranty / AMC Details | Section Break | None |  |  |  | None | None |
| `column_break6` | None | Column Break | None |  |  |  | None | None |
| `warranty_expiry_date` | Warranty Expiry Date | Date | None |  |  |  | None | None |
| `amc_expiry_date` | AMC Expiry Date | Date | None |  |  |  | None | None |
| `column_break7` | None | Column Break | None |  |  |  | None | None |
| `maintenance_status` | Maintenance Status | Select | 
Under Warranty
Out of Warranty
Under AMC
Out of AMC |  |  | ✅ | None | None |
| `warranty_period` | Warranty Period (Days) | Int | None |  |  | ✅ | None | None |
| `more_info` | More Information | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `column_break_2cmm` | None | Column Break | None |  |  |  | None | None |
| `work_order` | Work Order | Link | Work Order |  |  |  | None | None |
| `purchase_document_no` | Creation Document No | Data | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 10
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/serial_no/serial_no.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

cur_frm.add_fetch("customer", "customer_name", "customer_name");
cur_frm.add_fetch("supplier", "supplier_name", "supplier_name");

cur_frm.add_fetch("item_code", "item_name", "item_name");
cur_frm.add_fetch("item_code", "description", "description");
cur_frm.add_fetch("item_code", "item_group", "item_group");
cur_frm.add_fetch("item_code", "brand", "brand");

cur_frm.cscript.onload = function () {
	cur_frm.set_query("item_code", function () {
		return erpnext.queries.item({ is_stock_item: 1, has_serial_no: 1 });
	});
};

frappe.ui.form.on("Serial No", "refresh", function (frm) {
	frm.toggle_enable("item_code", frm.doc.__islocal);
});

frappe.ui.form.on("Serial No", {
	refresh(frm) {
		frm.trigger("view_ledgers");
	},

	view_ledgers(frm) {
		frm.add_custom_button(__("View Ledgers"), () => {
			frappe.route_options = {
				item_code: frm.doc.item_code,
				serial_no: frm.doc.name,
				posting_date: frappe.datetime.now_date(),
				posting_time: frappe.datetime.now_time(),
			};
			frappe.set_route("query-report", "Serial No Ledger");
		}).addClass("btn-primary");
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Serial No Status` | Report Builder | Stock |
| `Serial No Warranty Expiry` | Report Builder | Stock |
| `Serial No Service Contract Expiry` | Report Builder | Stock |



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
