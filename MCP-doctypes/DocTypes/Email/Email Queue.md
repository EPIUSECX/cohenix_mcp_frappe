# Master Control Plan: `Email Queue`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Email`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** Email Queue records.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `sender` | Sender | Data | Email |  |  |  | None | None |
| `recipients` | Recipient | Table | Email Queue Recipient |  |  |  | None | None |
| `show_as_cc` | Show as cc | Small Text | None |  |  |  | None | None |
| `message` | Message | Code | None |  |  |  | None | None |
| `status` | Status | Select | Not Sent
Sending
Sent
Partially Sent
Error |  | ✅ |  | Not Sent | None |
| `error` | Error | Code | None |  |  |  | None | None |
| `message_id` | Message ID | Small Text | None |  |  | ✅ | None | None |
| `reference_doctype` | Reference Document Type | Link | DocType |  |  | ✅ | None | None |
| `reference_name` | Reference DocName | Data | None |  |  | ✅ | None | None |
| `communication` | Communication | Link | Communication |  |  |  | None | None |
| `send_after` | Send After | Datetime | None |  |  | ✅ | None | None |
| `priority` | Priority | Int | None |  |  | ✅ | 1 | None |
| `add_unsubscribe_link` | Add Unsubscribe Link | Check | None |  |  |  | 1 | None |
| `unsubscribe_params` | Unsubscribe Params | Code | None |  |  | ✅ | None | None |
| `unsubscribe_method` | Unsubscribe Method | Data | None |  |  |  | None | None |
| `expose_recipients` | Expose Recipients | Data | None |  |  |  | None | None |
| `attachments` | Attachments | Code | None |  |  | ✅ | None | None |
| `retry` | Retry | Int | None |  |  | ✅ | 0 | None |
| `email_account` | Email Account | Link | Email Account |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/email_queue/email_queue.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Email Queue", {
	refresh: function (frm) {
		if (["Not Sent", "Partially Sent"].includes(frm.doc.status)) {
			let button = frm.add_custom_button("Send Now", function () {
				frappe.call({
					method: "frappe.email.doctype.email_queue.email_queue.send_now",
					args: {
						name: frm.doc.name,
						force_send: true,
					},
					btn: button,
					callback: function () {
						frm.reload_doc();
						if (cint(frappe.sys_defaults.suspend_email_queue)) {
							frappe.show_alert(
								__(
									"Email queue is currently suspended. Resume to automatically send other emails."
								)
							);
						}
					},
				});
			});
		} else if (frm.doc.status == "Error") {
			frm.add_custom_button("Retry Sending", function () {
				frm.call({
					method: "frappe.email.doctype.email_queue.email_queue.retry_sending",
					args: {
						queues: [frm.doc.name],
					},
					callback: function () {
						frm.reload_doc();
						frappe.show_alert({
							message: __(
								"Status Updated. The email will be picked up in the next scheduled run."
							),
							indicator: "green",
						});
					},
				});
			});
		}
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
