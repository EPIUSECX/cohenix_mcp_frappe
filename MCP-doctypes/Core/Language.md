# Master Control Plan: `Language`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:language_code`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enabled` | Enabled | Check | None |  |  |  | 1 | None |
| `language_code` | Language Code | Data | None | ✅ |  |  | None | None |
| `language_name` | Language Name | Data | None | ✅ |  |  | None | None |
| `flag` | Flag | Data | None |  |  |  | None | None |
| `based_on` | Based On | Link | Language |  |  |  | None | None |
| `section_break_rtth` | None | Section Break | None |  |  |  | None | None |
| `date_format` | Date Format | Select | 
yyyy-mm-dd
dd-mm-yyyy
dd/mm/yyyy
dd.mm.yyyy
mm/dd/yyyy
mm-dd-yyyy |  |  |  | None | None |
| `time_format` | Time Format | Select | 
HH:mm:ss
HH:mm |  |  |  | None | None |
| `number_format` | Number Format | Select | 
#,###.##
#.###,##
# ###.##
# ###,##
#'###.##
#, ###.##
#,##,###.##
#,###.###
#.###
#,### |  |  |  | None | None |
| `first_day_of_the_week` | First Day of the Week | Select | 
Sunday
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/language/language.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Language", {
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
