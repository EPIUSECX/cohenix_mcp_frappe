# Master Control Plan: `Help Article`

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
| Knowledge Base Editor | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Knowledge Base Contributor | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `category` | Category | Link | Help Category | ✅ |  |  | None | None |
| `published` | Published | Check | None |  |  |  | 0 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `author` | Author | Data | None |  |  |  | user_fullname | None |
| `level` | Level | Select | Beginner
Intermediate
Expert |  |  |  | None | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `content` | Content | Text Editor | None | ✅ |  |  | None | None |
| `likes` | Likes | Int | None |  |  | ✅ | None | None |
| `route` | Route | Data | None |  |  |  | None | None |
| `section_break_cww5` | None | Section Break | None |  |  |  | None | None |
| `helpful` | Helpful | Int | None |  |  | ✅ | 0 | None |
| `cb_00` | None | Column Break | None |  |  |  | None | None |
| `not_helpful` | Not Helpful | Int | None |  |  | ✅ | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/help_article/help_article.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Help Article", {
	refresh: function (frm) {
		frm.dashboard.clear_headline();

		frm.dashboard.set_headline_alert(`
			<div class="row">
				<div class="col-md-6 col-xs-12">
					<span class="indicator whitespace-nowrap green">
						<span>Helpful: ${frm.doc.helpful || 0}</span>
					</span>
				</div>
				<div class="col-md-6 col-xs-12">
					<span class="indicator whitespace-nowrap red">
						<span>Not Helpful: ${frm.doc.not_helpful || 0}</span>
					</span>
				</div>
			</div>
		`);
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
