# Master Control Plan: `Sales Partner`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:partner_name`
- **Description:** A third party distributor / dealer / commission agent / affiliate / reseller who sells the companies products for a commission.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales Master Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `partner_name` | Sales Partner Name | Data | None | ✅ |  |  | None | None |
| `partner_type` | Partner Type | Link | Sales Partner Type |  |  |  | None | None |
| `territory` | Territory | Link | Territory | ✅ |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `commission_rate` | Commission Rate | Float | None | ✅ |  |  | None | None |
| `address_contacts` | Address & Contacts | Section Break | None |  |  |  | None | None |
| `address_desc` | Address Desc | HTML | None |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `contact_desc` | Contact Desc | HTML | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  | ✅ | None | None |
| `partner_target_details_section_break` | Sales Partner Target | Section Break | None |  |  |  | None | None |
| `targets` | Targets | Table | Target Detail |  |  |  | None | None |
| `website` | Website | Section Break | None |  |  |  | None | None |
| `show_in_website` | Show In Website | Check | None |  |  |  | 0 | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `referral_code` | Referral Code | Data | None |  |  |  | None | To Track inbound purchase |
| `section_break_17` | None | Section Break | None |  |  |  | None | None |
| `route` | Route | Data | None |  |  |  | None | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `logo` | Logo | Attach | None |  |  |  | None | None |
| `partner_website` | Partner website | Data | None |  |  |  | None | None |
| `section_break_22` | None | Section Break | None |  |  |  | None | None |
| `introduction` | Introduction | Text | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/sales_partner/sales_partner.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Sales Partner", {
	refresh: function (frm) {
		if (frm.doc.__islocal) {
			hide_field(["address_html", "contact_html", "address_contacts"]);
			frappe.contacts.clear_address_and_contact(frm);
		} else {
			unhide_field(["address_html", "contact_html", "address_contacts"]);
			frappe.contacts.render_address_and_contact(frm);
		}
	},

	setup: function (frm) {
		frm.fields_dict["targets"].grid.get_field("distribution_id").get_query = function (doc, cdt, cdn) {
			var row = locals[cdt][cdn];
			return {
				filters: {
					fiscal_year: row.fiscal_year,
				},
			};
		};
	},
	referral_code: function (frm) {
		if (frm.doc.referral_code) {
			frm.doc.referral_code = frm.doc.referral_code.toUpperCase();
			frm.refresh_field("referral_code");
		}
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
