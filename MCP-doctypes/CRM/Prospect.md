# Master Control Plan: `Prospect`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:company_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `overview_tab` | Overview | Tab Break | None |  |  |  | None | None |
| `company_name` | Company Name | Data | None |  |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |
| `no_of_employees` | No. of Employees | Select | 1-10
11-50
51-200
201-500
501-1000
1000+ |  |  |  | None | None |
| `annual_revenue` | Annual Revenue | Currency | currency |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `market_segment` | Market Segment | Link | Market Segment |  |  |  | None | None |
| `industry` | Industry | Link | Industry Type |  |  |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `prospect_owner` | Prospect Owner | Link | User |  |  |  | None | None |
| `website` | Website | Data | None |  |  |  | None | None |
| `fax` | Fax | Data | Phone |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `address_and_contact_section` | Address | Section Break | None |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `contacts_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `address_html` | Address HTML | HTML | None |  |  |  | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `contact_html` | Contact HTML | HTML | None |  |  |  | None | None |
| `leads_section` | Leads | Tab Break | None |  |  |  | None | None |
| `leads` | None | Table | Prospect Lead |  |  |  | None | None |
| `opportunities_tab` | Opportunities | Tab Break | None |  |  |  | None | None |
| `opportunities` | Opportunities | Table | Prospect Opportunity |  |  |  | None | None |
| `activities_tab` | Activities | Tab Break | None |  |  |  | None | None |
| `open_activities_html` | Open Activities HTML | HTML | None |  |  |  | None | None |
| `all_activities_section` | All Activities | Section Break | None |  |  |  | None | None |
| `all_activities_html` | All Activities HTML | HTML | None |  |  |  | None | None |
| `notes_section` | Comments | Tab Break | None |  |  |  | None | None |
| `notes_html` | Notes HTML | HTML | None |  |  |  | None | None |
| `notes` | Notes | Table | CRM Note |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/prospect/prospect.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Prospect", {
	refresh(frm) {
		if (!frm.is_new() && frappe.boot.user.can_create.includes("Customer")) {
			frm.add_custom_button(
				__("Customer"),
				function () {
					frappe.model.open_mapped_doc({
						method: "erpnext.crm.doctype.prospect.prospect.make_customer",
						frm: frm,
					});
				},
				__("Create")
			);
		}
		if (!frm.is_new() && frappe.boot.user.can_create.includes("Opportunity")) {
			frm.add_custom_button(
				__("Opportunity"),
				function () {
					frappe.model.open_mapped_doc({
						method: "erpnext.crm.doctype.prospect.prospect.make_opportunity",
						frm: frm,
					});
				},
				__("Create")
			);
		}

		if (!frm.is_new()) {
			frappe.contacts.render_address_and_contact(frm);
		} else {
			frappe.contacts.clear_address_and_contact(frm);
		}
		frm.trigger("show_notes");
		frm.trigger("show_activities");
	},

	show_notes(frm) {
		const crm_notes = new erpnext.utils.CRMNotes({
			frm: frm,
			notes_wrapper: $(frm.fields_dict.notes_html.wrapper),
		});
		crm_notes.refresh();
	},

	show_activities(frm) {
		const crm_activities = new erpnext.utils.CRMActivities({
			frm: frm,
			open_activities_wrapper: $(frm.fields_dict.open_activities_html.wrapper),
			all_activities_wrapper: $(frm.fields_dict.all_activities_html.wrapper),
			form_wrapper: $(frm.wrapper),
		});
		crm_activities.refresh();
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
