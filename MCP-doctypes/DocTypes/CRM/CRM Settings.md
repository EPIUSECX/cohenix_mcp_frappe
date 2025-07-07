# Master Control Plan: `CRM Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Settings for Selling Module

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_5` | Lead | Section Break | None |  |  |  | None | None |
| `campaign_naming_by` | Campaign Naming By | Select | Campaign Name
Naming Series |  |  |  | None | None |
| `allow_lead_duplication_based_on_emails` | Allow Lead Duplication based on Emails | Check | None |  |  |  | 0 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `auto_creation_of_contact` | Auto Creation of Contact | Check | None |  |  |  | 1 | None |
| `opportunity_section` | Opportunity | Section Break | None |  |  |  | None | None |
| `close_opportunity_after_days` | Close Replied Opportunity After Days | Int | None |  |  |  | 15 | Auto close Opportunity Replied after the no. of days mentioned above |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `quotation_section` | Quotation | Section Break | None |  |  |  | None | None |
| `default_valid_till` | Default Quotation Validity Days | Data | None |  |  |  | None | None |
| `section_break_13` | Activity | Section Break | None |  |  |  | None | None |
| `carry_forward_communication_and_comments` | Carry Forward Communication and Comments | Check | None |  |  |  | 0 | All the Comments and Emails will be copied from one document to another newly created document(Lead -> Opportunity -> Quotation) throughout the CRM documents. |
| `column_break_junk` | None | Column Break | None |  |  |  | None | None |
| `update_timestamp_on_new_communication` | Update timestamp on new communication | Check | None |  |  |  | 0 | Update the modified timestamp on new communications received in Lead & Opportunity. |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/crm_settings/crm_settings.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("CRM Settings", {
	// refresh: function(frm) {
	// }
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
