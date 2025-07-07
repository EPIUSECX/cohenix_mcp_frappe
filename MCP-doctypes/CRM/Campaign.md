# Master Control Plan: `Campaign`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** Keep Track of Sales Campaigns. Keep track of Leads, Quotations, Sales Order etc from Campaigns to gauge Return on Investment. 

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `campaign` | Campaign | Section Break | None |  |  |  | None | None |
| `campaign_name` | Campaign Name | Data | None | ✅ |  |  | None | None |
| `naming_series` | Naming Series | Select | SAL-CAM-.YYYY.- |  |  |  | None | None |
| `campaign_schedules_section` | Campaign Schedules | Section Break | None |  |  |  | None | None |
| `campaign_schedules` | Campaign Schedules | Table | Campaign Email Schedule |  |  |  | None | None |
| `description_section` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/campaign/campaign.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Campaign", {
	refresh: function (frm) {
		erpnext.toggle_naming_series();

		if (frm.is_new()) {
			frm.toggle_display(
				"naming_series",
				frappe.boot.sysdefaults.campaign_naming_by == "Naming Series"
			);
		} else {
			frm.add_custom_button(
				__("View Leads"),
				function () {
					frappe.route_options = { utm_source: "Campaign", utm_campaign: frm.doc.name };
					frappe.set_route("List", "Lead");
				},
				"fa fa-list",
				true
			);
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
