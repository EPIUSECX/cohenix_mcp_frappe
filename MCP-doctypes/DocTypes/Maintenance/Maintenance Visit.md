# Master Control Plan: `Maintenance Visit`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Maintenance`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Maintenance User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `customer_details` | None | Section Break | fa fa-user |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `naming_series` | Series | Select | MAT-MVS-.YYYY.- | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer | ✅ |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  | ✅ | ✅ | None | None |
| `address_display` | Address | Text Editor | None |  | ✅ | ✅ | None | None |
| `contact_display` | Contact | Small Text | None |  | ✅ | ✅ | None | None |
| `contact_mobile` | Mobile No | Data | Phone |  | ✅ | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  | ✅ | ✅ | None | None |
| `maintenance_schedule` | Maintenance Schedule | Link | Maintenance Schedule |  |  | ✅ | None | None |
| `maintenance_schedule_detail` | Maintenance Schedule Detail | Link | Maintenance Schedule Detail |  | ✅ |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `mntc_date` | Maintenance Date | Date | None | ✅ |  |  | Today | None |
| `mntc_time` | Maintenance Time | Time | None |  |  |  | None | None |
| `maintenance_details` | None | Section Break | fa fa-wrench |  |  |  | None | None |
| `completion_status` | Completion Status | Select | 
Partially Completed
Fully Completed | ✅ |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `maintenance_type` | Maintenance Type | Select | 
Scheduled
Unscheduled
Breakdown | ✅ |  |  | Unscheduled | None |
| `section_break0` | None | Section Break | fa fa-wrench |  |  |  | None | None |
| `purposes` | Purposes | Table | Maintenance Visit Purpose |  |  |  | None | None |
| `more_info` | More Information | Section Break | fa fa-file-text |  |  |  | None | None |
| `customer_feedback` | Customer Feedback | Small Text | None |  |  |  | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Cancelled
Submitted | ✅ |  | ✅ | Draft | None |
| `amended_from` | Amended From | Link | Maintenance Visit |  |  | ✅ | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `contact_info_section` | Contact Info | Section Break | fa fa-bullhorn |  |  |  | None | None |
| `customer_address` | Customer Address | Link | Address |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 9
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/maintenance/doctype/maintenance_visit/maintenance_visit.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.maintenance");
frappe.ui.form.on("Maintenance Visit", {
	setup: function (frm) {
		frm.set_query("contact_person", erpnext.queries.contact_query);
		frm.set_query("customer_address", erpnext.queries.address_query);
		frm.set_query("customer", erpnext.queries.customer);
	},
	onload: function (frm) {
		// filters for serial no based on item code
		if (frm.doc.maintenance_type === "Scheduled") {
			let item_code = frm.doc.purposes[0].item_code;
			if (!item_code) {
				return;
			}
			frappe
				.call({
					method: "erpnext.maintenance.doctype.maintenance_schedule.maintenance_schedule.get_serial_nos_from_schedule",
					args: {
						schedule: frm.doc.maintenance_schedule,
						item_code: item_code,
					},
				})
				.then((r) => {
					let serial_nos = r.message;
					frm.set_query("serial_no", "purposes", () => {
						if (serial_nos.length > 0) {
							return {
								filters: {
									item_code: item_code,
									name: ["in", serial_nos],
								},
							};
						}
						return {
							filters: {
								item_code: item_code,
							},
						};
					});
				});
		} else {
			frm.set_query("serial_no", "purposes", (frm, cdt, cdn) => {
				let row = locals[cdt][cdn];
				return {
					filters: {
						item_code: row.item_code,
					},
				};
			});
		}
		if (!frm.doc.status) {
			frm.set_value({ status: "Draft" });
		}
		if (frm.doc.__islocal) {
			frm.set_value({ mntc_date: frappe.datetime.get_today() });
		}
	},
	customer: function (frm) {
		erpnext.utils.get_party_details(frm);
	},
	customer_address: function (frm) {
		erpnext.utils.get_address_display(frm, "customer_address", "address_display");
	},
	contact_person: function (frm) {
		erpnext.utils.get_contact_details(frm);
	},
});

// TODO commonify this code
erpnext.maintenance.MaintenanceVisit = class MaintenanceVisit extends frappe.ui.form.Controller {
	refresh() {
		frappe.dynamic_link = { doc: this.frm.doc, fieldname: "customer", doctype: "Customer" };

		var me = this;

		if (this.frm.doc.docstatus === 0) {
			this.frm.add_custom_button(
				__("Maintenance Schedule"),
				function () {
					if (!me.frm.doc.customer) {
						frappe.msgprint(__("Please select Customer first"));
						return;
					}
					erpnext.utils.map_current_doc({
						method: "erpnext.maintenance.doctype.maintenance_schedule.maintenance_schedule.make_maintenance_visit",
						source_doctype: "Maintenance Schedule",
						target: me.frm,
						setters: {
							customer: me.frm.doc.customer,
						},
						get_query_filters: {
							docstatus: 1,
							company: me.frm.doc.company,
						},
					});
				},
				__("Get Items From")
			);
			this.frm.add_custom_button(
				__("Warranty Claim"),
				function () {
					erpnext.utils.map_current_doc({
						method: "erpnext.support.doctype.warranty_claim.warranty_claim.make_maintenance_visit",
						source_doctype: "Warranty Claim",
						target: me.frm,
						date_field: "complaint_date",
						setters: {
							customer: me.frm.doc.customer || undefined,
						},
						get_query_filters: {
							status: ["in", "Open, Work in Progress"],
							company: me.frm.doc.company,
						},
					});
				},
				__("Get Items From")
			);
			this.frm.add_custom_button(
				__("Sales Order"),
				function () {
					if (!me.frm.doc.customer) {
						frappe.msgprint(__("Please select Customer first"));
						return;
					}
					erpnext.utils.map_current_doc({
						method: "erpnext.selling.doctype.sales_order.sales_order.make_maintenance_visit",
						source_doctype: "Sales Order",
						target: me.frm,
						setters: {
							customer: me.frm.doc.customer,
						},
						get_query_filters: {
							docstatus: 1,
							company: me.frm.doc.company,
							order_type: me.frm.doc.order_type,
						},
					});
				},
				__("Get Items From")
			);
		}
	}
};

extend_cscript(cur_frm.cscript, new erpnext.maintenance.MaintenanceVisit({ frm: cur_frm }));

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
