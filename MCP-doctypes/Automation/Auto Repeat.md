# Master Control Plan: `Auto Repeat`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Automation`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:AUT-AR-{#####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `reference_doctype` | Reference Document Type | Link | DocType | ✅ |  |  | None | None |
| `reference_document` | Reference Document | Dynamic Link | reference_doctype | ✅ |  |  | None | None |
| `submit_on_creation` | Submit on Creation | Check | None |  |  |  | 0 | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | Today | None |
| `end_date` | End Date | Date | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `section_break_10` | Schedule | Tab Break | None |  |  |  | None | None |
| `frequency` | Frequency | Select | 
Daily
Weekly
Monthly
Quarterly
Half-yearly
Yearly | ✅ |  |  | None | None |
| `repeat_on_day` | Repeat on Day | Int | None |  |  |  | None | None |
| `repeat_on_last_day` | Repeat on Last Day of the Month | Check | None |  |  |  | 0 | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `next_schedule_date` | Next Schedule Date | Date | None |  |  | ✅ | None | None |
| `section_break_16` | None | Section Break | None |  |  |  | None | None |
| `repeat_on_days` | Repeat on Days | Table | Auto Repeat Day |  |  |  | None | None |
| `notification` | Notification | Tab Break | None |  |  |  | None | None |
| `notify_by_email` | Notify by Email | Check | None |  |  |  | 0 | None |
| `recipients` | Recipients | Small Text | None |  |  |  | None | None |
| `get_contacts` | Get Contacts | Button | None |  |  |  | None | None |
| `template` | Template | Link | Email Template |  |  |  | None | None |
| `subject` | Subject | Data | None |  |  |  | None | To add dynamic subject, use jinja tags like

<div><pre><code>New {{ doc.doctype }} #{{ doc.name }}</code></pre></div> |
| `message` | Message | Text | None |  |  |  | Please find attached {{ doc.doctype }} #{{ doc.name }} | None |
| `preview_message` | Preview Message | Button | None |  |  |  | None | None |
| `print_format` | Print Format | Link | Print Format |  |  |  | None | None |
| `status` | Status | Select | 
Active
Disabled
Completed |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 1
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/automation/doctype/auto_repeat/auto_repeat.js`
```javascript
// Copyright (c) 2018, Frappe Technologies and contributors
// For license information, please see license.txt
frappe.provide("frappe.auto_repeat");

frappe.ui.form.on("Auto Repeat", {
	setup: function (frm) {
		frm.fields_dict["reference_doctype"].get_query = function () {
			return {
				query: "frappe.automation.doctype.auto_repeat.auto_repeat.get_auto_repeat_doctypes",
			};
		};

		frm.fields_dict["reference_document"].get_query = function () {
			return {
				filters: {
					auto_repeat: "",
				},
			};
		};

		frm.fields_dict["print_format"].get_query = function () {
			return {
				filters: {
					doc_type: frm.doc.reference_doctype,
				},
			};
		};
	},

	refresh: function (frm) {
		// auto repeat message
		if (frm.is_new()) {
			let customize_form_link = `<a href="/app/customize-form">${__("Customize Form")}</a>`;
			frm.dashboard.set_headline(
				__('To configure Auto Repeat, enable "Allow Auto Repeat" from {0}.', [
					customize_form_link,
				])
			);
		}

		// view document button
		if (!frm.is_dirty()) {
			let label = __("View {0}", [__(frm.doc.reference_doctype)]);
			frm.add_custom_button(label, () =>
				frappe.set_route("List", frm.doc.reference_doctype, { auto_repeat: frm.doc.name })
			);
		}

		// auto repeat schedule
		frappe.auto_repeat.render_schedule(frm);

		frm.trigger("toggle_submit_on_creation");
	},

	reference_doctype: function (frm) {
		frm.trigger("toggle_submit_on_creation");
	},

	toggle_submit_on_creation: function (frm) {
		// submit on creation checkbox
		if (frm.doc.reference_doctype) {
			frappe.model.with_doctype(frm.doc.reference_doctype, () => {
				let meta = frappe.get_meta(frm.doc.reference_doctype);
				frm.toggle_display("submit_on_creation", meta.is_submittable);
			});
		}
	},

	template: function (frm) {
		if (frm.doc.template) {
			frappe.model.with_doc("Email Template", frm.doc.template, () => {
				let email_template = frappe.get_doc("Email Template", frm.doc.template);
				frm.set_value("subject", email_template.subject);
				let message_value = email_template.response;
				if (email_template.use_html) message_value = email_template.response_html;
				frm.set_value("message", message_value);
				frm.refresh_field("subject");
				frm.refresh_field("message");
			});
		}
	},

	get_contacts: function (frm) {
		frm.call("fetch_linked_contacts");
	},

	preview_message: function (frm) {
		if (frm.doc.message) {
			frappe.call({
				method: "frappe.automation.doctype.auto_repeat.auto_repeat.generate_message_preview",
				args: {
					reference_dt: frm.doc.reference_doctype,
					reference_doc: frm.doc.reference_document,
					subject: frm.doc.subject,
					message: frm.doc.message,
				},
				callback: function (r) {
					if (r.message) {
						frappe.msgprint(r.message.message, r.message.subject);
					}
				},
			});
		} else {
			frappe.msgprint(__("Please setup a message first"), __("Message not setup"));
		}
	},
});

frappe.auto_repeat.render_schedule = function (frm) {
	if (!frm.is_dirty() && frm.doc.status !== "Disabled") {
		frm.call("get_auto_repeat_schedule").then((r) => {
			frm.dashboard.reset();
			frm.dashboard.add_section(
				frappe.render_template("auto_repeat_schedule", {
					schedule_details: r.message || [],
				}),
				__("Auto Repeat Schedule")
			);
			frm.dashboard.show();
		});
	} else {
		frm.dashboard.hide();
	}
};

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
