# Master Control Plan: `Web Page View`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `path` | Path | Data | None |  |  |  | None | None |
| `referrer` | Referrer | Data | None |  |  |  | None | None |
| `browser` | Browser | Data | None |  |  |  | None | None |
| `browser_version` | Browser Version | Data | None |  |  |  | None | None |
| `is_unique` | Is Unique | Data | None |  |  |  | None | None |
| `time_zone` | Time Zone | Data | None |  |  |  | None | None |
| `user_agent` | User Agent | Data | None |  |  |  | None | None |
| `source` | Source | Data | None |  |  | ✅ | None | None |
| `campaign` | Campaign | Data | None |  |  | ✅ | None | None |
| `medium` | Medium | Data | None |  |  | ✅ | None | None |
| `visitor_id` | Visitor ID | Data | None |  |  | ✅ | None | None |
| `content` | Content | Data | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/web_page_view/web_page_view.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Web Page View", {
	// refresh: function(frm) {
	// }
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Website Analytics` | Script Report | Website |



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
