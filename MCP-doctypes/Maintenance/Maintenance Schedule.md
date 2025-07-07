# Master Control Plan: `Maintenance Schedule`

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
| Maintenance Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `customer_details` | None | Section Break | fa fa-user |  |  |  | None | None |
| `naming_series` | Series | Select | MAT-MSH-.YYYY.- | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Submitted
Cancelled | ✅ |  | ✅ | Draft | None |
| `transaction_date` | Transaction Date | Date | None | ✅ |  |  | None | None |
| `items_section` | None | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `items` | Items | Table | Maintenance Schedule Item | ✅ |  |  | None | None |
| `schedule` | Schedule | Section Break | fa fa-time |  |  |  | None | None |
| `generate_schedule` | Generate Schedule | Button | None |  |  |  | None | None |
| `schedules` | Schedules | Table | Maintenance Schedule Detail |  |  |  | None | None |
| `contact_info` | Contact Info | Section Break | None |  |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  |  | ✅ | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_mobile` | Mobile No | Data | Phone |  | ✅ | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  | ✅ | ✅ | None | None |
| `contact_display` | Contact | Small Text | None |  | ✅ | ✅ | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `customer_address` | Customer Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  | ✅ | ✅ | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Maintenance Schedule |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/maintenance/doctype/maintenance_schedule/maintenance_schedule.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.maintenance");
frappe.ui.form.on("Maintenance Schedule", {
	setup: function (frm) {
		frm.set_query("contact_person", erpnext.queries.contact_query);
		frm.set_query("customer_address", erpnext.queries.address_query);
		frm.set_query("customer", erpnext.queries.customer);

		frm.set_query("serial_and_batch_bundle", "items", (doc, cdt, cdn) => {
			let item = locals[cdt][cdn];

			return {
				filters: {
					item_code: item.item_code,
					voucher_type: "Maintenance Schedule",
					type_of_transaction: "Maintenance",
					company: doc.company,
				},
			};
		});
	},
	onload: function (frm) {
		if (!frm.doc.status) {
			frm.set_value({ status: "Draft" });
		}
		if (frm.doc.__islocal) {
			frm.set_value({ transaction_date: frappe.datetime.get_today() });
		}
	},
	refresh: function (frm) {
		setTimeout(() => {
			frm.toggle_display("generate_schedule", !(frm.is_new() || frm.doc.docstatus));
			frm.toggle_display("schedule", !frm.is_new());
		}, 10);
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
	generate_schedule: function (frm) {
		if (frm.is_new()) {
			frappe.msgprint(__("Please save first"));
		} else {
			frm.call("generate_schedule");
		}
	},
});

// TODO commonify this code
erpnext.maintenance.MaintenanceSchedule = class MaintenanceSchedule extends frappe.ui.form.Controller {
	refresh() {
		frappe.dynamic_link = { doc: this.frm.doc, fieldname: "customer", doctype: "Customer" };

		var me = this;

		if (this.frm.doc.docstatus === 0) {
			this.frm.add_custom_button(
				__("Sales Order"),
				function () {
					erpnext.utils.map_current_doc({
						method: "erpnext.selling.doctype.sales_order.sales_order.make_maintenance_schedule",
						source_doctype: "Sales Order",
						target: me.frm,
						setters: {
							customer: me.frm.doc.customer || undefined,
						},
						get_query_filters: {
							docstatus: 1,
							company: me.frm.doc.company,
						},
					});
				},
				__("Get Items From")
			);
		} else if (this.frm.doc.docstatus === 1) {
			let schedules = me.frm.doc.schedules;
			let flag = schedules.some((schedule) => schedule.completion_status === "Pending");
			if (flag) {
				this.frm.add_custom_button(
					__("Maintenance Visit"),
					function () {
						let options = "";

						me.frm.call("get_pending_data", { data_type: "items" }).then((r) => {
							options = r.message;

							let schedule_id = "";
							let d = new frappe.ui.Dialog({
								title: __("Enter Visit Details"),
								fields: [
									{
										fieldtype: "Select",
										fieldname: "item_name",
										label: __("Item Name"),
										options: options,
										reqd: 1,
										onchange: function () {
											let field = d.get_field("scheduled_date");
											me.frm
												.call("get_pending_data", {
													item_name: this.value,
													data_type: "date",
												})
												.then((r) => {
													field.df.options = r.message;
													field.refresh();
												});
										},
									},
									{
										label: __("Scheduled Date"),
										fieldname: "scheduled_date",
										fieldtype: "Select",
										options: "",
										reqd: 1,
										onchange: function () {
											let field = d.get_field("item_name");
											me.frm
												.call("get_pending_data", {
													item_name: field.value,
													s_date: this.value,
													data_type: "id",
												})
												.then((r) => {
													schedule_id = r.message;
												});
										},
									},
								],
								primary_action_label: "Create Visit",
								primary_action(values) {
									frappe.call({
										method: "erpnext.maintenance.doctype.maintenance_schedule.maintenance_schedule.make_maintenance_visit",
										args: {
											item_name: values.item_name,
											s_id: schedule_id,
											source_name: me.frm.doc.name,
										},
										callback: function (r) {
											if (!r.exc) {
												frappe.model.sync(r.message);
												frappe.set_route("Form", r.message.doctype, r.message.name);
											}
										},
									});
									d.hide();
								},
							});
							d.show();
						});
					},
					__("Create")
				);
			}
		}
	}
};

extend_cscript(cur_frm.cscript, new erpnext.maintenance.MaintenanceSchedule({ frm: cur_frm }));

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Maintenance Schedules` | Query Report | Support |



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
