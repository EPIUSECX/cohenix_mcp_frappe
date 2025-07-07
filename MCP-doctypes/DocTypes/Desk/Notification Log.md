# Master Control Plan: `Notification Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `subject` | Subject | Text | None |  |  |  | None | None |
| `for_user` | For User | Link | User |  | ✅ |  | None | None |
| `type` | Type | Select | 
Mention
Energy Point
Assignment
Share
Alert |  | ✅ |  | None | None |
| `email_content` | Message | Text Editor | None |  |  |  | None | None |
| `document_type` | Document Type | Link | DocType |  | ✅ |  | None | None |
| `read` | Read | Check | None |  | ✅ |  | 0 | None |
| `document_name` | Document Link | Data | None |  | ✅ |  | None | None |
| `attached_file` | Attached File | Code | JSON |  | ✅ |  | None | None |
| `attachment_link` | Attachment Link | HTML | None |  |  |  | None | None |
| `open_reference_document` | Open Reference Document | Button | None |  |  |  | None | None |
| `from_user` | From User | Link | User |  | ✅ |  | None | None |
| `link` | Link | Small Text | None |  | ✅ |  | None | None |
| `email_header` | Email Header | Data | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/notification_log/notification_log.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Notification Log", {
	refresh: function (frm) {
		if (frm.doc.attached_file) {
			frm.trigger("set_attachment");
		} else {
			frm.get_field("attachment_link").$wrapper.empty();
		}
	},

	open_reference_document: function (frm) {
		if (frm.doc?.link) {
			frappe.set_route(frm.doc.link);
			return;
		}
		const dt = frm.doc.document_type;
		const dn = frm.doc.document_name;
		frappe.set_route("Form", dt, dn);
	},

	set_attachment: function (frm) {
		const attachment = JSON.parse(frm.doc.attached_file);

		const $wrapper = frm.get_field("attachment_link").$wrapper;
		$wrapper.html(`
			<div class="attached-file text-medium">
				<div class="ellipsis">
					<i class="fa fa-paperclip"></i>
					<a class="attached-file-link">${attachment.name}.pdf</a>
				</div>
			</div>
		`);

		$wrapper.find(".attached-file-link").click(() => {
			const w = window.open(
				frappe.urllib.get_full_url(`/api/method/frappe.utils.print_format.download_pdf?
					doctype=${encodeURIComponent(attachment.doctype)}
					&name=${encodeURIComponent(attachment.name)}
					&format=${encodeURIComponent(attachment.print_format)}
					&lang=${encodeURIComponent(attachment.lang)}`)
			);
			if (!w) {
				frappe.msgprint(__("Please enable pop-ups"));
			}
		});
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
