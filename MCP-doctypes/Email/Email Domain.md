# Master Control Plan: `Email Domain`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Email`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:domain_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `email_settings` | None | Section Break | None |  |  |  | None | None |
| `domain_name` | Domain Name | Data | None | ✅ |  |  | None | None |
| `mailbox_settings` | Incoming Settings | Section Break | None |  |  |  | None | None |
| `email_server` | Incoming Server | Data | None | ✅ |  |  | None | e.g. pop.gmail.com / imap.gmail.com |
| `use_imap` | Use IMAP | Check | None |  |  |  | 0 | None |
| `use_ssl` | Use SSL | Check | None |  |  |  | 0 | None |
| `validate_ssl_certificate` | Validate SSL Certificate | Check | None |  |  |  | 1 | None |
| `use_starttls` | Use STARTTLS | Check | None |  |  |  | 0 | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `incoming_port` | Port | Data | None |  |  |  | None | If non-standard port (e.g. POP3: 995/110, IMAP: 993/143) |
| `attachment_limit` | Attachment Limit (MB) | Int | None |  |  |  | None | Ignore attachments over this size |
| `outgoing_mail_settings` | Outgoing Settings | Section Break | None |  |  |  | None | None |
| `smtp_server` | Outgoing Server | Data | None | ✅ |  |  | None | e.g. smtp.gmail.com |
| `use_tls` | Use TLS | Check | None |  |  |  | 0 | None |
| `use_ssl_for_outgoing` | Use SSL | Check | None |  |  |  | 0 | None |
| `validate_ssl_certificate_for_outgoing` | Validate SSL Certificate | Check | None |  |  |  | 1 | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `smtp_port` | Port | Data | None |  |  |  | None | If non standard port (e.g. 587) |
| `append_emails_to_sent_folder` | Append Emails to Sent Folder | Check | None |  |  |  | 0 | None |
| `sent_folder_name` | Sent Folder Name | Data | None |  |  |  | Sent | Some mailboxes require a different Sent Folder Name e.g. "INBOX.Sent" |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/email_domain/email_domain.js`
```javascript
frappe.ui.form.on("Email Domain", {
	onload: function (frm) {
		if (!frm.doc.__islocal) {
			frm.dashboard.clear_headline();
			let msg = __(
				"Changing any setting will reflect on all the email accounts associated with this domain."
			);
			frm.dashboard.set_headline_alert(msg);
		} else {
			if (!frm.doc.attachment_limit) {
				frappe.call({
					method: "frappe.core.api.file.get_max_file_size",
					callback: function (r) {
						if (!r.exc) {
							frm.set_value("attachment_limit", Number(r.message) / (1024 * 1024));
						}
					},
				});
			}
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
