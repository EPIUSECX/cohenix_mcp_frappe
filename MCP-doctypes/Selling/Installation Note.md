# Master Control Plan: `Installation Note`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `installation_note` | Installation Note | Section Break | None |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `naming_series` | Series | Select | MAT-INS-.YYYY.- | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer | ✅ |  |  | None | None |
| `customer_address` | Customer Address | Link | Address |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `customer_name` | Name | Data | None |  |  | ✅ | None | None |
| `address_display` | Address | Text Editor | None |  | ✅ | ✅ | None | None |
| `contact_display` | Contact | Small Text | None |  | ✅ | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  |  | ✅ | None | None |
| `territory` | Territory | Link | Territory | ✅ |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `inst_date` | Installation Date | Date | None | ✅ |  |  | None | None |
| `inst_time` | Installation Time | Time | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Submitted
Cancelled | ✅ |  | ✅ | Draft | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `amended_from` | Amended From | Link | Installation Note |  |  | ✅ | None | None |
| `remarks` | Remarks | Small Text | None |  |  |  | None | None |
| `item_details` | None | Section Break | Simple |  |  |  | None | None |
| `items` | Items | Table | Installation Note Item | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/installation_note/installation_note.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Installation Note", {
	setup: function (frm) {
		frappe.dynamic_link = { doc: frm.doc, fieldname: "customer", doctype: "Customer" };
		frm.set_query("customer_address", erpnext.queries.address_query);
		frm.set_query("contact_person", erpnext.queries.contact_query);
		frm.set_query("customer", erpnext.queries.customer);
		frm.set_query("serial_and_batch_bundle", "items", (doc, cdt, cdn) => {
			let row = locals[cdt][cdn];
			return {
				filters: {
					item_code: row.item_code,
					voucher_type: doc.doctype,
					voucher_no: ["in", [doc.name, ""]],
					is_cancelled: 0,
				},
			};
		});
	},
	onload: function (frm) {
		if (!frm.doc.status) {
			frm.set_value({ status: "Draft" });
		}
		if (frm.doc.__islocal) {
			frm.set_value({ inst_date: frappe.datetime.get_today() });
		}

		let sbb_field = frm.get_docfield("items", "serial_and_batch_bundle");
		if (sbb_field) {
			sbb_field.get_route_options_for_new_doc = (row) => {
				return {
					item_code: row.doc.item_code,
					voucher_type: frm.doc.doctype,
				};
			};
		}
	},
	customer: function (frm) {
		erpnext.utils.get_party_details(frm);
	},
	customer_address: function (frm) {
		erpnext.utils.get_address_display(frm);
	},
	contact_person: function (frm) {
		erpnext.utils.get_contact_details(frm);
	},
});

frappe.provide("erpnext.selling");

// TODO commonify this code
erpnext.selling.InstallationNote = class InstallationNote extends frappe.ui.form.Controller {
	refresh() {
		var me = this;
		if (this.frm.doc.docstatus === 0) {
			this.frm.add_custom_button(
				__("From Delivery Note"),
				function () {
					erpnext.utils.map_current_doc({
						method: "erpnext.stock.doctype.delivery_note.delivery_note.make_installation_note",
						source_doctype: "Delivery Note",
						target: me.frm,
						date_field: "posting_date",
						setters: {
							customer: me.frm.doc.customer || undefined,
						},
						get_query_filters: {
							docstatus: 1,
							status: ["not in", ["Stopped", "Closed"]],
							per_installed: ["<", 99.99],
							company: me.frm.doc.company,
						},
					});
				},
				"fa fa-download",
				"btn-default"
			);
		}
	}
};

extend_cscript(cur_frm.cscript, new erpnext.selling.InstallationNote({ frm: cur_frm }));

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
