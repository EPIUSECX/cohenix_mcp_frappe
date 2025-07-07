# Master Control Plan: `Webhook`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Integrations`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `sb_doc_events` | Doc Events | Section Break | None |  |  |  | None | None |
| `webhook_doctype` | DocType | Link | DocType | ✅ |  |  | None | None |
| `cb_doc_events` | None | Column Break | None |  |  |  | None | None |
| `webhook_docevent` | Doc Event | Select | after_insert
on_update
on_submit
on_cancel
on_trash
on_update_after_submit
on_change |  |  |  | None | None |
| `enabled` | Enabled | Check | None |  |  |  | 1 | None |
| `sb_condition` | Webhook Trigger | Section Break | None |  |  |  | None | None |
| `condition` | Condition | Small Text | None |  |  |  | None | The webhook will be triggered if this expression is true |
| `cb_condition` | None | Column Break | None |  |  |  | None | None |
| `html_condition` | None | HTML | <p><strong>Condition Examples:</strong></p>
<pre>doc.status=="Open"<br>doc.due_date==nowdate()<br>doc.total &gt; 40000
</pre> |  |  |  | None | None |
| `sb_webhook` | Webhook Request | Section Break | None |  |  |  | None | None |
| `request_url` | Request URL | Small Text | None | ✅ |  |  | None | None |
| `is_dynamic_url` | Is Dynamic URL? | Check | None |  |  |  | 0 | On checking this option, URL will be treated like a jinja template string |
| `timeout` | Request Timeout | Int | None |  |  |  | 5 | The number of seconds until the request expires |
| `background_jobs_queue` | Background Jobs Queue | Autocomplete | None |  |  |  | None | None |
| `cb_webhook` | None | Column Break | None |  |  |  | None | None |
| `request_method` | Request Method | Select | POST
PUT
DELETE | ✅ |  |  | POST | None |
| `request_structure` | Request Structure | Select | 
Form URL-Encoded
JSON |  |  |  | None | None |
| `sb_security` | Webhook Security | Section Break | None |  |  |  | None | None |
| `enable_security` | Enable Security | Check | None |  |  |  | 0 | None |
| `webhook_secret` | Webhook Secret | Password | None |  |  |  | None | None |
| `sb_webhook_headers` | Webhook Headers | Section Break | None |  |  |  | None | None |
| `webhook_headers` | Headers | Table | Webhook Header |  |  |  | None | None |
| `sb_webhook_data` | Webhook Data | Section Break | None |  |  |  | None | None |
| `webhook_data` | Data | Table | Webhook Data |  |  |  | None | None |
| `webhook_json` | JSON Request Body | Code | Jinja |  |  |  | None | To add dynamic values from the document, use jinja tags like

<div>
<pre><code>{ "id": "{{ doc.name }}" }</code>
</pre>
</div> |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/webhook/webhook.js`
```javascript
// Copyright (c) 2017, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.webhook = {
	set_fieldname_select: (frm) => {
		if (frm.doc.webhook_doctype) {
			frappe.model.with_doctype(frm.doc.webhook_doctype, () => {
				// get doctype fields
				let fields = $.map(
					frappe.get_doc("DocType", frm.doc.webhook_doctype).fields,
					(d) => {
						if (
							frappe.model.no_value_type.includes(d.fieldtype) &&
							!frappe.model.table_fields.includes(d.fieldtype)
						) {
							return null;
						} else {
							return {
								label: `${__(d.label, null, d.parent)} (${__(d.fieldtype)})`,
								value: d.fieldname,
							};
						}
					}
				);

				// add meta fields
				for (let field of frappe.model.std_fields) {
					if (field.fieldname == "name") {
						fields.unshift({ label: __("Name (Doc Name)"), value: "name" });
					} else {
						fields.push({
							label: `${__(field.label, null, field.parent)} (${__(
								field.fieldtype
							)})`,
							value: field.fieldname,
						});
					}
				}

				frm.fields_dict.webhook_data.grid.update_docfield_property(
					"fieldname",
					"options",
					[""].concat(fields)
				);
			});
		}
	},

	set_request_headers: (frm) => {
		if (frm.doc.request_structure) {
			let header_value;
			if (frm.doc.request_structure == "Form URL-Encoded") {
				header_value = "application/x-www-form-urlencoded";
			} else if (frm.doc.request_structure == "JSON") {
				header_value = "application/json";
			}

			if (header_value) {
				let header_row = (frm.doc.webhook_headers || []).find(
					(row) => row.key === "Content-Type"
				);
				if (header_row) {
					frappe.model.set_value(
						header_row.doctype,
						header_row.name,
						"value",
						header_value
					);
				} else {
					frm.add_child("webhook_headers", {
						key: "Content-Type",
						value: header_value,
					});
				}
				frm.refresh();
			}
		}
	},
};

frappe.ui.form.on("Webhook", {
	refresh: (frm) => {
		frappe.webhook.set_fieldname_select(frm);
		frm.set_query(
			"background_jobs_queue",
			"frappe.integrations.doctype.webhook.webhook.get_all_queues"
		);

		if (frm.doc.webhook_doctype) {
			frm.add_custom_button(__("Preview"), () => {
				const args = {
					doc: frm.doc,
					doctype: frm.doc.webhook_doctype,
					preview_fields: [
						{
							label: __("Meets Condition?"),
							fieldtype: "Data",
							method: "preview_meets_condition",
						},
						{
							label: __("Request Body"),
							fieldtype: "Code",
							method: "preview_request_body",
						},
					],
				};
				let dialog = new frappe.views.RenderPreviewer(args);
				return dialog;
			});
		}
	},

	request_structure: (frm) => {
		frappe.webhook.set_request_headers(frm);
	},

	webhook_doctype: (frm) => {
		frappe.webhook.set_fieldname_select(frm);
	},

	enable_security: (frm) => {
		frm.toggle_reqd("webhook_secret", frm.doc.enable_security);
	},
});

frappe.ui.form.on("Webhook Data", {
	fieldname: (frm, cdt, cdn) => {
		let row = locals[cdt][cdn];
		let df = frappe
			.get_meta(frm.doc.webhook_doctype)
			.fields.filter((field) => field.fieldname == row.fieldname);

		if (!df.length) {
			// check if field is a meta field
			df = frappe.model.std_fields.filter((field) => field.fieldname == row.fieldname);
		}

		row.key = df.length ? df[0].fieldname : "name";
		frm.refresh_field("webhook_data");
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
