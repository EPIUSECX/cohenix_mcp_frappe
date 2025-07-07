# Master Control Plan: `Warehouse`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** A logical Warehouse against which stock entries are made.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Item Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `warehouse_detail` | Warehouse Detail | Section Break | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  | ✅ |  | 0 | None |
| `warehouse_name` | Warehouse Name | Data | None | ✅ |  |  | None | None |
| `column_break_3` | None | Section Break | None |  |  |  | None | None |
| `is_group` | Is Group Warehouse | Check | None |  |  |  | 0 | None |
| `parent_warehouse` | Parent Warehouse | Link | Warehouse |  |  |  | None | None |
| `is_rejected_warehouse` | Is Rejected Warehouse | Check | None |  |  |  | 0 | If yes, then this warehouse will be used to store rejected materials |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `account` | Account | Link | Account |  |  |  | None | If blank, parent Warehouse Account or company default will be considered in transactions |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `address_and_contact` | Address and Contact | Section Break | None |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  |  | None | None |
| `warehouse_contact_info` | Warehouse Contact Info | Section Break | None |  |  |  | None | None |
| `email_id` | Email Address | Data | None |  | ✅ |  | None | None |
| `phone_no` | Phone No | Data | Phone |  |  |  | None | None |
| `mobile_no` | Mobile No | Data | Phone |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `address_line_1` | Address Line 1 | Data | None |  |  |  | None | None |
| `address_line_2` | Address Line 2 | Data | None |  |  |  | None | None |
| `city` | City | Data | None |  |  |  | None | None |
| `state` | State/Province | Data | None |  |  |  | None | None |
| `pin` | PIN | Data | None |  |  |  | None | None |
| `transit_section` | Transit | Section Break | None |  |  |  | None | None |
| `warehouse_type` | Warehouse Type | Link | Warehouse Type |  |  |  | None | None |
| `column_break_qajx` | None | Column Break | None |  |  |  | None | None |
| `default_in_transit_warehouse` | Default In-Transit Warehouse | Link | Warehouse |  |  |  | None | None |
| `tree_details` | Tree Details | Section Break | None |  |  |  | None | None |
| `lft` | lft | Int | None |  | ✅ | ✅ | None | None |
| `rgt` | rgt | Int | None |  | ✅ | ✅ | None | None |
| `old_parent` | Old Parent | Link | Warehouse |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/warehouse/warehouse.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Warehouse", {
	setup: function (frm) {
		frm.set_query("default_in_transit_warehouse", function (doc) {
			return {
				filters: {
					warehouse_type: "Transit",
					is_group: 0,
					company: doc.company,
				},
			};
		});

		frm.set_query("parent_warehouse", function (doc) {
			return {
				filters: {
					is_group: 1,
					company: doc.company,
				},
			};
		});

		frm.set_query("account", function (doc) {
			return {
				filters: {
					is_group: 0,
					account_type: "Stock",
					company: doc.company,
				},
			};
		});
	},

	refresh: function (frm) {
		frm.toggle_display("warehouse_name", frm.doc.__islocal);
		frm.toggle_display(["address_html", "contact_html"], !frm.doc.__islocal);

		if (!frm.is_new()) {
			frappe.contacts.render_address_and_contact(frm);

			if (frm.has_perm("write")) {
				let enable_toggle = frm.doc.disabled ? "Enable" : "Disable";
				frm.add_custom_button(__(enable_toggle), () => {
					frm.set_value("disabled", 1 - frm.doc.disabled);
					frm.save();
				});

				frm.add_custom_button(
					frm.doc.is_group
						? __("Convert to Ledger", null, "Warehouse")
						: __("Convert to Group", null, "Warehouse"),
					function () {
						convert_to_group_or_ledger(frm);
					}
				);
			}

			if ("Stock Balance" in frappe.boot.user.all_reports) {
				frm.add_custom_button(__("Stock Balance"), function () {
					frappe.set_route("query-report", "Stock Balance", {
						warehouse: frm.doc.name,
						company: frm.doc.company,
					});
				});
			}
		} else {
			frappe.contacts.clear_address_and_contact(frm);
		}

		if (
			!frm.doc.is_group &&
			frm.doc.__onload?.account &&
			"General Ledger" in frappe.boot.user.all_reports
		) {
			frm.add_custom_button(__("General Ledger", null, "Warehouse"), function () {
				frappe.route_options = {
					account: frm.doc.__onload.account,
					company: frm.doc.company,
				};
				frappe.set_route("query-report", "General Ledger");
			});
		}

		frm.toggle_enable(["is_group", "company"], false);
	},
});

function convert_to_group_or_ledger(frm) {
	frappe.call({
		method: "erpnext.stock.doctype.warehouse.warehouse.convert_to_group_or_ledger",
		args: {
			docname: frm.doc.name,
			is_group: frm.doc.is_group,
		},
		callback: function () {
			frm.refresh();
		},
	});
}

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
No linked reports found.


### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Total Warehouses` | Total Warehouses | Count | Stock |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
