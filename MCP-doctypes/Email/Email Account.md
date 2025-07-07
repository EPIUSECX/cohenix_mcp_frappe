# Master Control Plan: `Email Account`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Email`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:email_account_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Inbox User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `account_section` | Account | Section Break | None |  |  |  | None | None |
| `email_id` | Email Address | Data | Email | ✅ |  |  | None | None |
| `email_account_name` | Email Account Name | Data | None |  |  |  | None | e.g. "Support", "Sales", "Jerry Yang" |
| `enable_incoming` | Enable Incoming | Check | None |  |  |  | 0 | None |
| `enable_outgoing` | Enable Outgoing | Check | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `service` | Service | Select | 
Frappe Mail
GMail
Sendgrid
SparkPost
Yahoo Mail
Outlook.com
Yandex.Mail |  |  |  | None | None |
| `domain` | Domain | Link | Email Domain |  |  |  | None | None |
| `frappe_mail_site` | Frappe Mail Site | Data | None |  |  |  | https://frappemail.com | None |
| `authentication_column` | Authentication | Section Break | None |  |  |  | None | None |
| `auth_method` | Method | Select | Basic
OAuth |  |  |  | Basic | None |
| `backend_app_flow` | Authenticate as Service Principal | Check | None |  |  |  | 0 | None |
| `authorize_api_access` | Authorize API Access | Button | None |  |  |  | None | None |
| `validate_frappe_mail_settings` | Validate Frappe Mail Settings | Button | None |  |  |  | None | None |
| `password` | Password | Password | None |  |  |  | None | None |
| `awaiting_password` | Awaiting password | Check | None |  |  |  | 0 | None |
| `ascii_encode_password` | Use ASCII encoding for password | Check | None |  |  |  | 0 | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `api_key` | API Key | Data | None |  |  |  | None | None |
| `api_secret` | API Secret | Password | None |  |  |  | None | None |
| `connected_app` | Connected App | Link | Connected App |  |  |  | None | None |
| `connected_user` | Connected User | Link | User |  |  |  | None | None |
| `login_id_is_different` | Use different Email ID | Check | None |  |  |  | 0 | None |
| `login_id` | Alternative Email ID | Data | None |  |  |  | None | None |
| `incoming_popimap_tab` | Incoming | Tab Break | None |  |  |  | None | None |
| `section_break_uc6h` | None | Section Break | None |  |  |  | None | None |
| `default_incoming` | Default Incoming | Check | None |  |  |  | 0 | e.g. replies@yourcomany.com. All replies will come to this inbox. |
| `column_break_uynb` | None | Column Break | None |  |  |  | None | None |
| `attachment_limit` | Attachment Limit (MB) | Int | None |  |  |  | None | Ignore attachments over this size |
| `last_synced_at` | Last Synced At | Datetime | None |  |  |  | None | None |
| `mailbox_settings` | Incoming (POP/IMAP) Settings | Section Break | None |  |  |  | None | None |
| `use_imap` | Use IMAP | Check | None |  |  |  | 0 | None |
| `use_ssl` | Use SSL | Check | None |  |  |  | 0 | None |
| `validate_ssl_certificate` | Validate SSL Certificate | Check | None |  |  |  | 1 | None |
| `use_starttls` | Use STARTTLS | Check | None |  |  |  | 0 | None |
| `email_server` | Incoming Server | Data | None |  |  |  | None | e.g. pop.gmail.com / imap.gmail.com |
| `incoming_port` | Port | Data | None |  |  |  | None | If non-standard port (e.g. POP3: 995/110, IMAP: 993/143) |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `email_sync_option` | Email Sync Option | Select | ALL
UNSEEN |  |  |  | UNSEEN | None |
| `initial_sync_count` | Initial Sync Count | Select | 100
250
500 |  |  |  | 250 | Total number of emails to sync in initial sync process  |
| `section_break_25` | IMAP Details | Section Break | None |  |  |  | None | None |
| `imap_folder` | IMAP Folder | Table | IMAP Folder |  |  |  | None | None |
| `section_break_12` | Document Linking | Section Break | None |  |  |  | None | None |
| `append_emails_to_sent_folder` | Append Emails to Sent Folder | Check | None |  |  |  | 0 | None |
| `sent_folder_name` | Sent Folder Name | Data | None |  |  |  | None | None |
| `append_to` | Append To | Link | DocType |  |  |  | None | Append as communication against this DocType (must have fields: "Sender" and "Subject"). These fields can be defined in the email settings section of the appended doctype. |
| `create_contact` | Create Contacts from Incoming Emails | Check | None |  |  |  | 1 | None |
| `enable_automatic_linking` | Enable Automatic Linking in Documents | Check | None |  |  |  | 0 | For more information, <a class="text-muted" href="https://erpnext.com/docs/user/manual/en/setting-up/email/linking-emails-to-document">click here</a>. |
| `section_break_13` | None | Column Break | None |  |  |  | None | None |
| `notify_if_unreplied` | Notify if unreplied | Check | None |  |  |  | 0 | None |
| `unreplied_for_mins` | Notify if unreplied for (in mins) | Int | None |  |  |  | 30 | None |
| `send_notification_to` | Send Notification to | Small Text | None |  |  |  | None | List of email addresses, separated by comma or new line. |
| `outgoing_tab` | Outgoing | Tab Break | None |  |  |  | None | None |
| `default_outgoing` | Default Outgoing | Check | None |  |  |  | 0 | Notifications and bulk mails will be sent from this outgoing server. |
| `column_break_h5pd` | None | Column Break | None |  |  |  | None | None |
| `always_use_account_email_id_as_sender` | Always use this email address as sender address | Check | None |  |  |  | 0 | None |
| `always_use_account_name_as_sender_name` | Always use this name as sender name | Check | None |  |  |  | 0 | None |
| `send_unsubscribe_message` | Send unsubscribe message in email | Check | None |  |  |  | 1 | None |
| `track_email_status` | Track Email Status | Check | None |  |  |  | 1 | Track if your email has been opened by the recipient.
<br>
Note: If you're sending to multiple recipients, even if 1 recipient reads the email, it'll be considered "Opened" |
| `outgoing_mail_settings` | Outgoing (SMTP) Settings | Section Break | None |  |  |  | None | None |
| `use_tls` | Use TLS | Check | None |  |  |  | 0 | None |
| `use_ssl_for_outgoing` | Use SSL | Check | None |  |  |  | 0 | None |
| `smtp_server` | Outgoing Server | Data | None |  |  |  | None | e.g. smtp.gmail.com |
| `smtp_port` | Port | Data | None |  |  |  | None | If non standard port (e.g. 587). If on Google Cloud, try port 2525. |
| `column_break_38` | None | Column Break | None |  |  |  | None | None |
| `no_smtp_authentication` | Disable SMTP server authentication | Check | None |  |  |  | 0 | None |
| `always_bcc` | Always BCC Address | Data | Email |  |  |  | None | Use this, for example, if all sent emails should also be send to an archive. |
| `signature_section` | Signature | Section Break | None |  |  |  | None | None |
| `add_signature` | Add Signature | Check | None |  |  |  | 0 | None |
| `signature` | Signature | Text Editor | None |  |  |  | None | None |
| `auto_reply` | Auto Reply | Section Break | None |  |  |  | None | None |
| `enable_auto_reply` | Enable Auto Reply | Check | None |  |  |  | 0 | None |
| `auto_reply_message` | Auto Reply Message | Text Editor | None |  |  |  | None | ProTip: Add <code>Reference: {{ reference_doctype }} {{ reference_name }}</code> to send document reference |
| `set_footer` | Footer | Section Break | None |  |  |  | None | None |
| `footer` | Footer Content | Text Editor | None |  |  |  | None | None |
| `brand_logo` | Brand Logo | Attach Image | None |  |  |  | None | None |
| `uidvalidity` | UIDVALIDITY | Data | None |  | ✅ |  | None | None |
| `uidnext` | UIDNEXT | Int | None |  | ✅ |  | None | None |
| `no_failed` | no failed attempts | Int | None |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/email_account/email_account.js`
```javascript
frappe.email_defaults = {
	"Frappe Mail": {
		domain: null,
		password: null,
		awaiting_password: 0,
		ascii_encode_password: 0,
		login_id_is_different: 0,
		login_id: null,
		use_imap: 0,
		use_ssl: 0,
		validate_ssl_certificate: 0,
		use_starttls: 0,
		email_server: null,
		incoming_port: 0,
		always_use_account_email_id_as_sender: 1,
		use_tls: 0,
		use_ssl_for_outgoing: 0,
		smtp_server: null,
		smtp_port: null,
		no_smtp_authentication: 0,
	},
	GMail: {
		email_server: "imap.gmail.com",
		incoming_port: 993,
		use_ssl: 1,
		enable_outgoing: 1,
		smtp_server: "smtp.gmail.com",
		smtp_port: 587,
		use_tls: 1,
		use_imap: 1,
	},
	"Outlook.com": {
		email_server: "imap-mail.outlook.com",
		use_ssl: 1,
		enable_outgoing: 1,
		smtp_server: "smtp-mail.outlook.com",
		smtp_port: 587,
		use_tls: 1,
		use_imap: 1,
	},
	Sendgrid: {
		enable_outgoing: 1,
		smtp_server: "smtp.sendgrid.net",
		smtp_port: 587,
		use_tls: 1,
	},
	SparkPost: {
		enable_incoming: 0,
		enable_outgoing: 1,
		smtp_server: "smtp.sparkpostmail.com",
		smtp_port: 587,
		use_tls: 1,
	},
	"Yahoo Mail": {
		email_server: "imap.mail.yahoo.com",
		use_ssl: 1,
		enable_outgoing: 1,
		smtp_server: "smtp.mail.yahoo.com",
		smtp_port: 587,
		use_tls: 1,
		use_imap: 1,
	},
	"Yandex.Mail": {
		email_server: "imap.yandex.com",
		use_ssl: 1,
		enable_outgoing: 1,
		smtp_server: "smtp.yandex.com",
		smtp_port: 587,
		use_tls: 1,
		use_imap: 1,
	},
};

frappe.email_defaults_pop = {
	GMail: {
		email_server: "pop.gmail.com",
	},
	"Outlook.com": {
		email_server: "pop3-mail.outlook.com",
	},
	"Yahoo Mail": {
		email_server: "pop.mail.yahoo.com",
	},
	"Yandex.Mail": {
		email_server: "pop.yandex.com",
	},
};

function oauth_access(frm) {
	frappe.model.with_doc("Connected App", frm.doc.connected_app, () => {
		const connected_app = frappe.get_doc("Connected App", frm.doc.connected_app);
		return frappe.call({
			doc: connected_app,
			method: "initiate_web_application_flow",
			args: {
				success_uri: window.location.pathname,
				user: frm.doc.connected_user,
			},
			callback: function (r) {
				window.open(r.message, "_self");
			},
		});
	});
}

function set_default_max_attachment_size(frm) {
	if (frm.doc.__islocal && !frm.doc["attachment_limit"]) {
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
function add_helpful_links(frm) {
	// For better UX
	if (frm.doc.service === "GMail") {
		frm.set_df_property(
			"password",
			"description",
			__("To generate password click {0}", [
				"<a href='https://knowledge.workspace.google.com/kb/how-to-create-app-passwords-000009237' target='_blank'>" +
					__("here") +
					"</a>",
			])
		);
	} else {
		frm.set_df_property("password", "description", "");
	}

	if (frm.doc.service === "Frappe Mail") {
		frm.set_df_property(
			"api_secret",
			"description",
			__("To know more click {0}", [
				"<a href='https://github.com/frappe/mail' target='_blank'>" + __("here") + "</a>",
			])
		);
	} else {
		frm.set_df_property("api_secret", "description", "");
	}
}

frappe.ui.form.on("Email Account", {
	service: function (frm) {
		$.each(frappe.email_defaults[frm.doc.service], function (key, value) {
			frm.set_value(key, value);
		});
		if (!frm.doc.use_imap) {
			$.each(frappe.email_defaults_pop[frm.doc.service], function (key, value) {
				frm.set_value(key, value);
			});
		}
		add_helpful_links(frm);
	},

	use_imap: function (frm) {
		if (!frm.doc.use_imap) {
			$.each(frappe.email_defaults_pop[frm.doc.service], function (key, value) {
				frm.set_value(key, value);
			});
		} else {
			$.each(frappe.email_defaults[frm.doc.service], function (key, value) {
				frm.set_value(key, value);
			});
		}
	},

	enable_incoming: function (frm) {
		frm.trigger("warn_autoreply_on_incoming");
	},

	enable_auto_reply: function (frm) {
		frm.trigger("warn_autoreply_on_incoming");
	},

	onload: function (frm) {
		frm.set_df_property("append_to", "only_select", true);
		frm.set_query(
			"append_to",
			"frappe.email.doctype.email_account.email_account.get_append_to"
		);
		frm.set_query("append_to", "imap_folder", function () {
			return {
				query: "frappe.email.doctype.email_account.email_account.get_append_to",
			};
		});
		if (frm.doc.__islocal) {
			frm.add_child("imap_folder", { folder_name: "INBOX" });
			frm.refresh_field("imap_folder");
		}
		set_default_max_attachment_size(frm);
	},

	refresh: function (frm) {
		frm.events.enable_incoming(frm);
		frm.events.show_oauth_authorization_message(frm);

		if (frappe.route_flags.delete_user_from_locals && frappe.route_flags.linked_user) {
			delete frappe.route_flags.delete_user_from_locals;
			delete locals["User"][frappe.route_flags.linked_user];
		}

		if (!frm.is_dirty() && frm.doc.enable_incoming) {
			frm.add_custom_button(__("Pull Emails"), () => {
				frappe.dom.freeze(__("Pulling emails..."));
				frm.call({
					method: "pull_emails",
					args: { email_account: frm.doc.name },
				}).then((r) => {
					frappe.dom.unfreeze();
					if (!(r._server_messages && r._server_messages.length)) {
						frappe.show_alert({ message: __("Emails Pulled"), indicator: "green" });
					}
				});
			});
		}
	},

	authorize_api_access: function (frm) {
		oauth_access(frm);
	},

	validate_frappe_mail_settings: function (frm) {
		if (frm.doc.service == "Frappe Mail") {
			frappe.call({
				doc: frm.doc,
				method: "validate_frappe_mail_settings",
			});
		}
	},

	show_oauth_authorization_message(frm) {
		if (
			frm.doc.auth_method === "OAuth" &&
			frm.doc.connected_app &&
			!frm.doc.backend_app_flow
		) {
			frappe.call({
				method: "frappe.integrations.doctype.connected_app.connected_app.has_token",
				args: {
					connected_app: frm.doc.connected_app,
					connected_user: frm.doc.connected_user,
				},
				callback: (r) => {
					if (!r.message) {
						let msg = __(
							'OAuth has been enabled but not authorised. Please use "Authorise API Access" button to do the same.'
						);
						frm.dashboard.clear_headline();
						frm.dashboard.set_headline_alert(msg, "yellow");
					}
				},
			});
		}
	},

	domain: frappe.utils.debounce((frm) => {
		if (frm.doc.domain) {
			frappe.call({
				method: "get_domain_values",
				doc: frm.doc,
				args: {
					domain: frm.doc.domain,
				},
				callback: function (r) {
					if (!r.exc) {
						for (let field in r.message) {
							frm.set_value(field, r.message[field]);
						}
					}
				},
			});
		}
	}),

	email_sync_option: function (frm) {
		// confirm if the ALL sync option is selected

		if (frm.doc.email_sync_option == "ALL") {
			var msg = __(
				"You are selecting Sync Option as ALL, It will resync all read as well as unread message from server. This may also cause the duplication of Communication (emails)."
			);
			frappe.confirm(msg, null, function () {
				frm.set_value("email_sync_option", "UNSEEN");
			});
		}
	},

	warn_autoreply_on_incoming: function (frm) {
		if (frm.doc.enable_incoming && frm.doc.enable_auto_reply && frm.doc.__islocal) {
			var msg = __(
				"Enabling auto reply on an incoming email account will send automated replies to all the synchronized emails. Do you wish to continue?"
			);
			frappe.confirm(msg, null, function () {
				frm.set_value("enable_auto_reply", 0);
				frappe.show_alert({ message: __("Disabled Auto Reply"), indicator: "blue" });
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
