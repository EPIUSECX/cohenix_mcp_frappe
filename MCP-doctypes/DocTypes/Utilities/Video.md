# Master Control Plan: `Video`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Utilities`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:title`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| All | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `provider` | Provider | Select | YouTube
Vimeo | ✅ |  |  | None | None |
| `url` | URL | Data | None | ✅ |  |  | None | None |
| `youtube_video_id` | Youtube ID | Data | None |  | ✅ | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `publish_date` | Publish Date | Date | None |  |  |  | None | None |
| `duration` | Duration | Duration | None |  |  |  | None | None |
| `youtube_tracking_section` | Youtube Statistics | Section Break | None |  |  |  | None | None |
| `like_count` | Likes | Float | None |  |  | ✅ | None | None |
| `view_count` | Views | Float | None |  |  | ✅ | None | None |
| `col_break` | None | Column Break | None |  |  |  | None | None |
| `dislike_count` | Dislikes | Float | None |  |  | ✅ | None | None |
| `comment_count` | Comments | Float | None |  |  | ✅ | None | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None | ✅ |  |  | None | None |
| `image` | Image | Attach Image | None |  | ✅ |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/utilities/doctype/video/video.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Video", {
	refresh: function (frm) {
		frm.events.toggle_youtube_statistics_section(frm);
		frm.add_custom_button(__("Watch Video"), () => frappe.help.show_video(frm.doc.url, frm.doc.title));
	},

	toggle_youtube_statistics_section: (frm) => {
		if (frm.doc.provider === "YouTube") {
			frappe.db.get_single_value("Video Settings", "enable_youtube_tracking").then((val) => {
				frm.toggle_display("youtube_tracking_section", val);
			});
		}
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `YouTube Interactions` | Script Report | Utilities |



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
