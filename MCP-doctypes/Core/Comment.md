# Master Control Plan: `Comment`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `comment_type` | Comment Type | Select | Comment
Like
Info
Label
Workflow
Created
Submitted
Cancelled
Updated
Deleted
Assigned
Assignment Completed
Attachment
Attachment Removed
Shared
Unshared
Bot
Relinked
Edit | ✅ |  |  | Comment | None |
| `comment_email` | Comment Email | Data | None |  |  |  | None | None |
| `subject` | Subject | Text | None |  |  |  | None | None |
| `comment_by` | Comment By | Data | None |  |  |  | None | None |
| `published` | Published | Check | None |  |  |  | 0 | None |
| `seen` | Seen | Check | None |  |  |  | 0 | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `reference_doctype` | Reference Document Type | Link | DocType |  |  |  | None | None |
| `reference_name` | Reference Name | Dynamic Link | reference_doctype |  |  |  | None | None |
| `reference_owner` | Reference Owner | Data | None |  |  | ✅ | None | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `content` | Content | HTML Editor | None |  |  |  | None | None |
| `ip_address` | IP Address | Data | None |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/comment/comment.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Comment", {
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
