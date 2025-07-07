# Master Control Plan: `Email Campaign`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:MAIL-CAMP-{YYYY}-{#####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `campaign_name` | Campaign | Link | Campaign | ✅ |  |  | None | None |
| `email_campaign_for` | Email Campaign For  | Select | 
Lead
Contact
Email Group | ✅ |  |  | Lead | None |
| `recipient` | Recipient | Dynamic Link | email_campaign_for | ✅ |  |  | None | None |
| `sender` | Sender | Link | User |  |  |  | __user | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | None | None |
| `end_date` | End Date | Date | None |  |  | ✅ | None | None |
| `status` | Status | Select | 
Scheduled
In Progress
Completed
Unsubscribed |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/email_campaign/email_campaign.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Email Campaign", {
	email_campaign_for: function (frm) {
		frm.set_value("recipient", "");
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
