# Master Control Plan: `Blog Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Settings to control blog categories and interactions like comments and likes

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Website Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Blogger | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `blog_title` | Blog Title | Data | None |  |  |  | None | None |
| `blog_introduction` | Blog Introduction | Small Text | None |  |  |  | None | None |
| `preview_image` | Preview Image | Attach Image | None |  |  |  | None | None |
| `column_break` | None | Column Break | None |  |  |  | None | None |
| `enable_social_sharing` | Enable Social Sharing | Check | None |  |  |  | 0 | None |
| `allow_guest_to_comment` | Allow Guest to comment | Check | None |  |  |  | 1 | None |
| `browse_by_category` | Browse by category | Check | None |  |  |  | 0 | None |
| `show_cta_in_blog` | Show "Call to Action" in Blog | Check | None |  |  |  | 0 | None |
| `cta_section` | Call to Action | Section Break | None |  |  |  | None | None |
| `title` | Title | Data | None |  |  |  | None | None |
| `subtitle` | Subtitle | Data | None |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `cta_label` | CTA Label | Data | None |  |  |  | None | None |
| `cta_url` | CTA URL | Data | None |  |  |  | None | None |
| `section_break_12` | Rate Limits | Section Break | None |  |  |  | None | None |
| `like_limit` | Like limit | Int | None |  |  |  | 5 | Like limit per hour |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `comment_limit` | Comment limit | Int | None |  |  |  | 5 | Comment limit per hour |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/blog_settings/blog_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Blog Settings", {
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
