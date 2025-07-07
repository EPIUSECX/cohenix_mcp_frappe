# Master Control Plan: `Notification`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Email`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enabled` | Enabled | Check | None |  |  |  | 1 | None |
| `is_standard` | Is Standard | Check | None |  |  |  | 0 | None |
| `module` | Module | Link | Module Def |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `channel` | Channel | Select | Email
Slack
System Notification
SMS | ✅ |  |  | Email | None |
| `slack_webhook_url` | Slack Channel | Link | Slack Webhook URL |  |  |  | None | To use Slack Channel, add a <a href="#List/Slack%20Webhook%20URL/List">Slack Webhook URL</a>. |
| `filters` | Filters | Section Break | None |  |  |  | None | None |
| `subject` | Subject | Data | None |  |  |  | None | To add dynamic subject, use jinja tags like

<div><pre><code>{{ doc.name }} Delivered</code></pre></div> |
| `event` | Send Alert On | Select | 
New
Save
Submit
Cancel
Days After
Days Before
Minutes After
Minutes Before
Value Change
Method
Custom | ✅ |  |  | None | None |
| `document_type` | Document Type | Link | DocType | ✅ |  |  | None | None |
| `col_break_1` | None | Column Break | None |  |  |  | None | None |
| `method` | Trigger Method | Data | None |  |  |  | None | Trigger on valid methods like "before_insert", "after_update", etc (will depend on the DocType selected) |
| `date_changed` | Reference Date | Select | None |  |  |  | None | Send alert if date matches this field's value |
| `datetime_changed` | Reference Datetime | Select | None |  |  |  | None | Send alert if datetime matches this field's value |
| `days_in_advance` | Days Before or After | Int | None |  |  |  | 0 | Send days before or after the reference date |
| `minutes_offset` | Minutes Offset | Int | None |  |  |  | 0 | Send <b>at the earliest</b> this number of minutes before or after the reference datetime. The actual sending may be delayed by up to 5 minutes due to the scheduler's trigger cadence. |
| `datetime_last_run` | Last Run | Datetime | None |  |  | ✅ | None | None |
| `value_changed` | Value Changed | Select | None |  |  |  | None | Send alert if this field's value changes |
| `sender` | Sender | Link | Email Account |  |  |  | None | None |
| `send_system_notification` | Send System Notification | Check | None |  |  |  | 0 | If enabled, the notification will show up in the notifications dropdown on the top right corner of the navigation bar. |
| `sender_email` | Sender Email | Data | Email |  |  | ✅ | None | None |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `condition` | Condition | Code | None |  |  |  | None | Optional: The alert will be sent if this expression is true |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `html_7` | None | HTML | <p><strong>Condition Examples:</strong></p>
<pre>doc.status=="Open"<br>doc.due_date==nowdate()<br>doc.total &gt; 40000
</pre>
 |  |  |  | None | None |
| `property_section` | Set Property After Alert | Section Break | None |  |  |  | None | None |
| `set_property_after_alert` | Set Property After Alert | Select | None |  |  |  | None | None |
| `property_value` | Value To Be Set | Data | None |  |  |  | None | None |
| `column_break_5` | Recipients | Section Break | None |  |  |  | None | None |
| `send_to_all_assignees` | Send To All Assignees | Check | None |  |  |  | 0 | None |
| `recipients` | Recipients | Table | Notification Recipient |  |  |  | None | None |
| `message_sb` | Message | Section Break | None |  |  |  | None | None |
| `message_type` | Message Type | Select | Markdown
HTML
Plain Text |  |  |  | Markdown | None |
| `message` | Message | Code | Jinja |  |  |  | Add your message here | None |
| `message_examples` | Message Examples | HTML | <h5>Message Example</h5>

<pre>&lt;h3&gt;Order Overdue&lt;/h3&gt;

&lt;p&gt;Transaction {{ doc.name }} has exceeded Due Date. Please take necessary action.&lt;/p&gt;

&lt;!-- show last comment --&gt;
{% if comments %}
Last comment: {{ comments[-1].comment }} by {{ comments[-1].by }}
{% endif %}

&lt;h4&gt;Details&lt;/h4&gt;

&lt;ul&gt;
&lt;li&gt;Customer: {{ doc.customer }}
&lt;li&gt;Amount: {{ doc.grand_total }}
&lt;/ul&gt;
</pre> |  |  |  | None | None |
| `view_properties` | View Properties (via Customize Form) | Button | None |  |  |  | None | None |
| `column_break_25` | Print Settings | Section Break | None |  |  |  | None | None |
| `attach_print` | Attach Print | Check | None |  |  |  | 0 | None |
| `print_format` | Print Format | Link | Print Format |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/notification/notification.js`
```javascript
// Copyright (c) 2018, Frappe Technologies and contributors
// For license information, please see license.txt

const DATE_BASED_EVENTS = ["Days Before", "Days After"];

frappe.notification = {
	setup_fieldname_select: function (frm) {
		// get the doctype to update fields
		if (!frm.doc.document_type) {
			return;
		}

		frappe.model.with_doctype(frm.doc.document_type, function () {
			let get_select_options = function (df, parent_field) {
				// Append parent_field name along with fieldname for child table fields
				let select_value = parent_field ? df.fieldname + "," + parent_field : df.fieldname;
				let path = parent_field ? parent_field + " > " + df.fieldname : df.fieldname;

				return {
					value: select_value,
					label: path + " (" + __(df.label, null, df.parent) + ")",
				};
			};

			let get_date_change_options = function (fieldtypes) {
				let date_options = $.map(fields, function (d) {
					return fieldtypes.includes(d.fieldtype) ? get_select_options(d) : null;
				});
				// append creation and modified date to Date Change field
				return date_options.concat([
					{ value: "creation", label: `creation (${__("Created On")})` },
					{ value: "modified", label: `modified (${__("Last Modified Date")})` },
				]);
			};
			let get_receiver_fields = function (
				fields,
				is_extra_receiver_field = (_) => {
					return false;
				}
			) {
				// finds receiver fields from the fields or any child table
				// by default finds any link to the User doctype
				// however an additional optional predicate can be passed as argument
				// to find additional fields
				let is_receiver_field = function (df) {
					return (
						is_extra_receiver_field(df) ||
						(df.options == "User" && df.fieldtype == "Link") ||
						(df.options == "Customer" && df.fieldtype == "Link")
					);
				};
				let extract_receiver_field = function (df) {
					// Add recipients from child doctypes into select dropdown
					if (frappe.model.table_fields.includes(df.fieldtype)) {
						let child_fields = frappe.get_doc("DocType", df.options).fields;
						return $.map(child_fields, function (cdf) {
							return is_receiver_field(cdf)
								? get_select_options(cdf, df.fieldname)
								: null;
						});
					} else {
						return is_receiver_field(df) ? get_select_options(df) : null;
					}
				};
				return $.map(fields, extract_receiver_field);
			};

			let fields = frappe.get_doc("DocType", frm.doc.document_type).fields;
			let options = $.map(fields, function (d) {
				return frappe.model.no_value_type.includes(d.fieldtype)
					? null
					: get_select_options(d);
			});

			// set value changed options
			frm.set_df_property("value_changed", "options", [""].concat(options));
			frm.set_df_property("set_property_after_alert", "options", [""].concat(options));

			// set date changed options
			frm.set_df_property(
				"date_changed",
				"options",
				get_date_change_options(["Date", "Datetime"])
			);
			frm.set_df_property(
				"datetime_changed",
				"options",
				get_date_change_options(["Datetime"])
			);

			let receiver_fields = [];
			if (frm.doc.channel === "Email") {
				receiver_fields = get_receiver_fields(fields, function (df) {
					return df.options == "Email";
				});
			} else if (["WhatsApp", "SMS"].includes(frm.doc.channel)) {
				receiver_fields = get_receiver_fields(fields, function (df) {
					return df.options == "Phone" || df.options == "Mobile";
				});
			}

			// set email recipient options
			frm.fields_dict.recipients.grid.update_docfield_property(
				"receiver_by_document_field",
				"options",
				[""].concat(["owner"]).concat(receiver_fields)
			);
		});
	},
	setup_example_message: function (frm) {
		let template = "";
		if (frm.doc.channel === "Email") {
			template = `<h5>Message Example</h5>

<pre>&lt;h3&gt;Order Overdue&lt;/h3&gt;

&lt;p&gt;Transaction {{ doc.name }} has exceeded Due Date. Please take necessary action.&lt;/p&gt;

&lt;!-- show last comment --&gt;
{% if comments %}
Last comment: {{ comments[-1].comment }} by {{ comments[-1].by }}
{% endif %}

&lt;h4&gt;Details&lt;/h4&gt;

&lt;ul&gt;
&lt;li&gt;Customer: {{ doc.customer }}&lt;/li&gt;
&lt;li&gt;Amount: {{ doc.grand_total }}&lt;/li&gt;
&lt;/ul&gt;
</pre>
			`;
		} else if (["Slack", "System Notification", "SMS"].includes(frm.doc.channel)) {
			template = `<h5>Message Example</h5>

<pre>*Order Overdue*

Transaction {{ doc.name }} has exceeded Due Date. Please take necessary action.

<!-- show last comment -->
{% if comments %}
Last comment: {{ comments[-1].comment }} by {{ comments[-1].by }}
{% endif %}

*Details*

• Customer: {{ doc.customer }}
• Amount: {{ doc.grand_total }}
</pre>`;
		}
		if (template) {
			frm.set_df_property("message_examples", "options", template);
		}
	},
};

frappe.ui.form.on("Notification", {
	onload: function (frm) {
		frm.set_query("document_type", function () {
			if (DATE_BASED_EVENTS.includes(frm.doc.event)) return;

			return {
				filters: {
					istable: 0,
				},
			};
		});
		frm.set_query("print_format", function () {
			return {
				filters: {
					doc_type: frm.doc.document_type,
				},
			};
		});
	},
	refresh: function (frm) {
		frappe.notification.setup_fieldname_select(frm);
		frappe.notification.setup_example_message(frm);

		frm.add_fetch("sender", "email_id", "sender_email");
		frm.set_query("sender", () => {
			return {
				filters: {
					enable_outgoing: 1,
				},
			};
		});
		frm.get_field("is_standard").toggle(frappe.boot.developer_mode);
		frm.trigger("event");
		if (frm.doc.document_type) {
			frm.add_custom_button(__("Preview"), () => {
				const args = {
					doc: frm.doc,
					doctype: frm.doc.document_type,
					preview_fields: [
						{
							label: __("Meets Condition?"),
							fieldtype: "Data",
							method: "preview_meets_condition",
						},
						{ label: __("Subject"), fieldtype: "Data", method: "preview_subject" },
						{ label: __("Message"), fieldtype: "Code", method: "preview_message" },
					],
				};
				let dialog = new frappe.views.RenderPreviewer(args);
				return dialog;
			});
		}
	},
	document_type: function (frm) {
		frappe.notification.setup_fieldname_select(frm);
	},
	view_properties: function (frm) {
		frappe.route_options = { doc_type: frm.doc.document_type };
		frappe.set_route("Form", "Customize Form");
	},
	event: function (frm) {
		if (!DATE_BASED_EVENTS.includes(frm.doc.event) || frm.is_new()) return;

		frm.add_custom_button(__("Get Alerts for Today"), function () {
			frappe.call({
				method: "frappe.email.doctype.notification.notification.get_documents_for_today",
				args: {
					notification: frm.doc.name,
				},
				callback: function (r) {
					if (r.message && r.message.length > 0) {
						frappe.msgprint(r.message.toString());
					} else {
						frappe.msgprint(__("No alerts for today"));
					}
				},
			});
		});
	},
	channel: function (frm) {
		frm.toggle_reqd("recipients", frm.doc.channel == "Email");
		frappe.notification.setup_fieldname_select(frm);
		frappe.notification.setup_example_message(frm);
		if (frm.doc.channel === "SMS" && frm.doc.__islocal) {
			frm.set_df_property(
				"channel",
				"description",
				`To use SMS Channel, initialize <a href="/app/sms-settings">SMS Settings</a>.`
			);
		} else {
			frm.set_df_property("channel", "description", ` `);
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
