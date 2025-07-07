# Master Control Plan: `SMS Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `SYS-SMS-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `sender_name` | Sender Name | Data | None |  |  | ✅ | None | None |
| `sent_on` | Sent On | Date | None |  |  | ✅ | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `message` | Message | Small Text | None |  |  | ✅ | None | None |
| `sec_break1` | None | Section Break | Simple |  |  |  | None | None |
| `no_of_requested_sms` | No of Requested SMS | Int | None |  |  | ✅ | None | None |
| `requested_numbers` | Requested Numbers | Code | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `no_of_sent_sms` | No of Sent SMS | Int | None |  |  | ✅ | None | None |
| `sent_to` | Sent To | Code | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/sms_log/sms_log.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("SMS Log", {
	refresh: function (frm) {},
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
