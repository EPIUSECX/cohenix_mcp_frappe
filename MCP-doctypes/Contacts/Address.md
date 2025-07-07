# Master Control Plan: `Address`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Contacts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Maintenance User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| All | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `address_details` | None | Section Break | fa fa-map-marker |  |  |  | None | None |
| `address_title` | Address Title | Data | None |  |  |  | None | None |
| `address_type` | Address Type | Select | Billing
Shipping
Office
Personal
Plant
Postal
Shop
Subsidiary
Warehouse
Current
Permanent
Other | ✅ |  |  | None | None |
| `address_line1` | Address Line 1 | Data | None | ✅ |  |  | None | None |
| `address_line2` | Address Line 2 | Data | None |  |  |  | None | None |
| `city` | City/Town | Data | None | ✅ |  |  | None | None |
| `county` | County | Data | None |  |  |  | None | None |
| `state` | State/Province | Data | None |  |  |  | None | None |
| `country` | Country | Link | Country | ✅ |  |  | None | None |
| `pincode` | Postal Code | Data | None |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `email_id` | Email Address | Data | Email |  |  |  | None | None |
| `phone` | Phone | Data | None |  |  |  | None | None |
| `fax` | Fax | Data | None |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `is_primary_address` | Preferred Billing Address | Check | None |  |  |  | 0 | None |
| `is_shipping_address` | Preferred Shipping Address | Check | None |  |  |  | 0 | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `linked_with` | Reference | Section Break | fa fa-pushpin |  |  |  | None | None |
| `is_your_company_address` | Is Your Company Address | Check | None |  |  |  | 0 | None |
| `links` | Links | Table | Dynamic Link |  |  |  | None | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `is_your_company_address` | Is Your Company Address | Check | None |  |  |  | 0 | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |



### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/contacts/doctype/address/address.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Address", {
	refresh: function (frm) {
		if (frm.doc.__islocal) {
			const last_doc = frappe.contacts.get_last_doc(frm);
			if (
				frappe.dynamic_link &&
				frappe.dynamic_link.doc &&
				frappe.dynamic_link.doc.name == last_doc.docname
			) {
				frm.set_value("links", "");
				frm.add_child("links", {
					link_doctype: frappe.dynamic_link.doctype,
					link_name: frappe.dynamic_link.doc[frappe.dynamic_link.fieldname],
				});
			}
		}
		frm.set_query("link_doctype", "links", function () {
			return {
				query: "frappe.contacts.address_and_contact.filter_dynamic_link_doctypes",
				filters: {
					fieldtype: "HTML",
					fieldname: "address_html",
				},
			};
		});
		frm.refresh_field("links");

		if (frm.doc.links) {
			for (let i in frm.doc.links) {
				let link = frm.doc.links[i];
				frm.add_custom_button(
					__("{0}: {1}", [__(link.link_doctype), __(link.link_name)]),
					function () {
						frappe.set_route("Form", link.link_doctype, link.link_name);
					},
					__("Links")
				);
			}
		}
	},
	validate: function (frm) {
		// clear linked customer / supplier / sales partner on saving...
		if (frm.doc.links) {
			frm.doc.links.forEach(function (d) {
				frappe.model.remove_from_locals(d.link_doctype, d.link_name);
			});
		}
	},
	after_save: function (frm) {
		frappe.run_serially([
			() => frappe.timeout(1),
			() => {
				const last_doc = frappe.contacts.get_last_doc(frm);
				if (
					frappe.dynamic_link &&
					frappe.dynamic_link.doc &&
					frappe.dynamic_link.doc.name == last_doc.docname
				) {
					for (let i in frm.doc.links) {
						let link = frm.doc.links[i];
						if (
							last_doc.doctype == link.link_doctype &&
							last_doc.docname == link.link_name
						) {
							frappe.set_route("Form", last_doc.doctype, last_doc.docname);
						}
					}
				}
			},
		]);
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Address And Contacts` | Script Report | Selling |
| `Addresses And Contacts` | Script Report | Contacts |



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
