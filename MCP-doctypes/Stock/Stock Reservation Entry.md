# Master Control Plan: `Stock Reservation Entry`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `MAT-SRE-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_xt4m` | Transaction Information | Section Break | None |  |  |  | None | None |
| `voucher_type` | Voucher Type | Select | 
Sales Order
Work Order
Production Plan |  |  | ✅ | None | None |
| `voucher_no` | Voucher No | Dynamic Link | voucher_type |  |  | ✅ | None | None |
| `voucher_detail_no` | Voucher Detail No | Data | None |  |  | ✅ | None | None |
| `column_break_grdt` | None | Column Break | None |  |  |  | None | None |
| `voucher_qty` | Voucher Qty | Float | None |  |  | ✅ | 0 | None |
| `available_qty` | Available Qty to Reserve | Float | None |  |  | ✅ | 0 | None |
| `column_break_o6ex` | None | Column Break | None |  |  |  | None | None |
| `reserved_qty` | Reserved Qty | Float | None |  |  |  | None | None |
| `delivered_qty` | Delivered Qty | Float | None |  |  | ✅ | 0 | None |
| `item_information_section` | Item Information | Section Break | None |  |  |  | None | None |
| `item_code` | Item Code | Link | Item |  |  | ✅ | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  | ✅ | None | None |
| `column_break_elik` | None | Column Break | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `has_serial_no` | Has Serial No | Check | None |  |  | ✅ | 0 | None |
| `has_batch_no` | Has Batch No | Check | None |  |  | ✅ | 0 | None |
| `column_break_7dxj` | None | Column Break | None |  |  |  | None | None |
| `from_voucher_type` | From Voucher Type | Select | 
Pick List
Purchase Receipt
Stock Entry
Work Order
Production Plan |  |  | ✅ | None | None |
| `from_voucher_no` | From Voucher No | Dynamic Link | from_voucher_type |  |  | ✅ | None | None |
| `from_voucher_detail_no` | From Voucher Detail No | Data | None |  |  | ✅ | None | None |
| `production_section` | Production | Section Break | None |  |  |  | None | None |
| `transferred_qty` | Qty in WIP Warehouse | Float | None |  |  |  | None | None |
| `column_break_qdwj` | None | Column Break | None |  |  |  | None | None |
| `consumed_qty` | Consumed Qty | Float | None |  |  |  | None | None |
| `serial_and_batch_reservation_section` | Serial and Batch Reservation | Tab Break | None |  |  |  | None | None |
| `reservation_based_on` | Reservation Based On | Select | Qty
Serial and Batch |  |  |  | Qty | None |
| `sb_entries` | None | Table | Serial and Batch Entry |  |  |  | None | None |
| `section_break_3vb3` | More Information | Tab Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `column_break_jbyr` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  | ✅ | None | None |
| `status` | Status | Select | Draft
Partially Reserved
Reserved
Partially Delivered
Delivered
Cancelled
Closed |  |  | ✅ | Draft | None |
| `amended_from` | Amended From | Link | Stock Reservation Entry |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 2
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_reservation_entry/stock_reservation_entry.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Stock Reservation Entry", {
	refresh(frm) {
		frm.trigger("set_queries");
		frm.trigger("toggle_read_only_fields");
		frm.trigger("hide_rate_related_fields");
		frm.trigger("hide_primary_action_button");
		frm.trigger("make_sb_entries_warehouse_read_only");
	},

	has_serial_no(frm) {
		frm.trigger("toggle_read_only_fields");
	},

	has_batch_no(frm) {
		frm.trigger("toggle_read_only_fields");
	},

	warehouse(frm) {
		if (frm.doc.warehouse) {
			frm.doc.sb_entries.forEach((row) => {
				frappe.model.set_value(row.doctype, row.name, "warehouse", frm.doc.warehouse);
			});
		}
	},

	set_queries(frm) {
		frm.set_query("warehouse", () => {
			return {
				filters: {
					is_group: 0,
					company: frm.doc.company,
				},
			};
		});

		frm.set_query("serial_no", "sb_entries", function (doc, cdt, cdn) {
			var selected_serial_nos = doc.sb_entries.map((row) => {
				return row.serial_no;
			});
			var row = locals[cdt][cdn];
			return {
				filters: {
					item_code: doc.item_code,
					warehouse: row.warehouse,
					status: "Active",
					name: ["not in", selected_serial_nos],
				},
			};
		});

		frm.set_query("batch_no", "sb_entries", function (doc, cdt, cdn) {
			let filters = {
				item: doc.item_code,
				batch_qty: [">", 0],
				disabled: 0,
			};

			if (!doc.has_serial_no) {
				var selected_batch_nos = doc.sb_entries.map((row) => {
					return row.batch_no;
				});

				filters.name = ["not in", selected_batch_nos];
			}

			return { filters: filters };
		});
	},

	toggle_read_only_fields(frm) {
		if (frm.doc.has_serial_no) {
			frm.doc.sb_entries.forEach((row) => {
				if (row.qty !== 1) {
					frappe.model.set_value(row.doctype, row.name, "qty", 1);
				}
			});
		}

		frm.fields_dict.sb_entries.grid.update_docfield_property(
			"serial_no",
			"read_only",
			!frm.doc.has_serial_no
		);

		frm.fields_dict.sb_entries.grid.update_docfield_property(
			"batch_no",
			"read_only",
			!frm.doc.has_batch_no
		);

		// Qty will always be 1 for Serial No.
		frm.fields_dict.sb_entries.grid.update_docfield_property("qty", "read_only", frm.doc.has_serial_no);

		frm.set_df_property(
			"sb_entries",
			"allow_on_submit",
			frm.doc.from_voucher_type == "Pick List" ? 0 : 1
		);
	},

	hide_rate_related_fields(frm) {
		["incoming_rate", "outgoing_rate", "stock_value_difference", "is_outward", "stock_queue"].forEach(
			(field) => {
				frm.fields_dict.sb_entries.grid.update_docfield_property(field, "hidden", 1);
			}
		);
	},

	hide_primary_action_button(frm) {
		// Hide 'Amend' button on cancelled document
		if (frm.doc.docstatus == 2) {
			frm.page.btn_primary.hide();
		}
	},

	make_sb_entries_warehouse_read_only(frm) {
		frm.fields_dict.sb_entries.grid.update_docfield_property("warehouse", "read_only", 1);
	},
});

frappe.ui.form.on("Serial and Batch Entry", {
	sb_entries_add(frm, cdt, cdn) {
		if (frm.doc.warehouse) {
			frappe.model.set_value(cdt, cdn, "warehouse", frm.doc.warehouse);
		}
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Reserved Stock` | Script Report | Stock |



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
