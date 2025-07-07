# Master Control Plan: `Warranty Claim`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Support`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Maintenance User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | SER-WRN-.YYYY.- | ✅ |  |  | None | None |
| `status` | Status | Select | 
Open
Closed
Work In Progress
Cancelled | ✅ |  |  | Open | None |
| `complaint_date` | Issue Date | Date | None | ✅ |  |  | Today | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `customer` | Customer | Link | Customer | ✅ |  |  | None | None |
| `serial_no` | Serial No | Link | Serial No |  |  |  | None | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `complaint` | Issue | Text Editor | None | ✅ |  |  | None | None |
| `issue_details` | Item and Warranty Details | Section Break | fa fa-ticket |  |  |  | None | None |
| `item_code` | Item Code | Link | Item |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `description` | Description | Small Text | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `warranty_amc_status` | Warranty / AMC Status | Select | 
Under Warranty
Out of Warranty
Under AMC
Out of AMC |  |  |  | None | None |
| `warranty_expiry_date` | Warranty Expiry Date | Date | None |  |  |  | None | None |
| `amc_expiry_date` | AMC Expiry Date | Date | None |  |  |  | None | None |
| `resolution_section` | Resolution | Section Break | fa fa-thumbs-up |  |  |  | None | None |
| `resolution_date` | Resolution Date | Datetime | None |  |  |  | None | None |
| `resolved_by` | Resolved By | Link | User |  |  |  | None | None |
| `resolution_details` | Resolution Details | Text | None |  |  |  | None | None |
| `contact_info` | Customer Details | Section Break | fa fa-bullhorn |  |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  |  | ✅ | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Data | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  |  | ✅ | None | None |
| `territory` | Territory | Link | Territory |  |  | ✅ | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  | ✅ | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `customer_address` | Customer Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `service_address` | Service Address | Small Text | None |  |  |  | None | If different than customer address |
| `more_info` | More Information | Section Break | fa fa-file-text |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `col_break6` | None | Column Break | None |  |  |  | None | None |
| `complaint_raised_by` | Raised By | Data | None |  |  |  | None | None |
| `from_company` | From Company | Data | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Warranty Claim |  | ✅ |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/support/doctype/warranty_claim/warranty_claim.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.support");

frappe.ui.form.on("Warranty Claim", {
	setup: (frm) => {
		frm.set_query("contact_person", erpnext.queries.contact_query);
		frm.set_query("customer_address", erpnext.queries.address_query);
		frm.set_query("customer", erpnext.queries.customer);

		frm.set_query("serial_no", () => {
			let filters = {
				company: frm.doc.company,
			};

			if (frm.doc.item_code) {
				filters["item_code"] = frm.doc.item_code;
			}

			return { filters: filters };
		});

		frm.set_query("item_code", () => {
			return {
				filters: {
					disabled: 0,
				},
			};
		});
	},

	onload: (frm) => {
		if (!frm.doc.status) {
			frm.set_value("status", "Open");
		}
	},

	refresh: (frm) => {
		frappe.dynamic_link = {
			doc: frm.doc,
			fieldname: "customer",
			doctype: "Customer",
		};

		if (!frm.doc.__islocal && ["Open", "Work In Progress"].includes(frm.doc.status)) {
			frm.add_custom_button(__("Maintenance Visit"), () => {
				frappe.model.open_mapped_doc({
					method: "erpnext.support.doctype.warranty_claim.warranty_claim.make_maintenance_visit",
					frm: frm,
				});
			});
		}
	},

	customer: (frm) => {
		erpnext.utils.get_party_details(frm);
	},

	customer_address: (frm) => {
		erpnext.utils.get_address_display(frm);
	},

	contact_person: (frm) => {
		erpnext.utils.get_contact_details(frm);
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
