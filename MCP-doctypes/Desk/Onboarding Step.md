# Master Control Plan: `Onboarding Step`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `is_complete` | Is Complete | Check | None |  |  |  | 0 | None |
| `is_skipped` | Is Skipped | Check | None |  |  |  | 0 | None |
| `description_section` | Description | Section Break | None |  |  |  | None | Description to inform the user about any action that is going to be performed |
| `description` | Description | Markdown Editor | None |  |  |  | None | None |
| `intro_video_url` | Intro Video URL | Data | None |  |  |  | None | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `action` | Action | Select | Create Entry
Update Settings
Show Form Tour
View Report
Go to Page
Watch Video | ✅ |  |  | None | None |
| `action_label` | Action Label | Data | None |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `reference_document` | Reference Document | Link | DocType |  |  |  | None | None |
| `show_full_form` | Show Full Form? | Check | None |  |  |  | 0 | Show full form instead of a quick entry modal |
| `show_form_tour` | Show Form Tour | Check | None |  |  |  | 0 | None |
| `form_tour` | Form Tour | Link | Form Tour |  |  |  | None | None |
| `is_single` | Is Single | Check | None |  |  |  | 0 | None |
| `reference_report` | Reference Report | Link | Report |  |  |  | None | None |
| `report_reference_doctype` | Report Reference Doctype | Data | None |  |  | ✅ | None | None |
| `report_type` | Report Type | Data | None |  |  | ✅ | None | None |
| `report_description` | Report Description | Data | None |  |  |  | None | This will be shown to the user in a dialog after routing to the report |
| `path` | Path | Data | None |  |  |  | None | Example: #Tree/Account |
| `callback_title` | Callback Title | Data | None |  |  |  | None | None |
| `callback_message` | Callback Message | Small Text | None |  |  |  | None | This will be shown in a modal after routing |
| `validate_action` | Validate Field | Check | None |  |  |  | 1 | None |
| `field` | Field | Select | None |  |  |  | None | None |
| `value_to_validate` | Value to Validate | Data | None |  |  |  | None | Use % for any non empty value. |
| `video_url` | Video URL | Data | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/onboarding_step/onboarding_step.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Onboarding Step", {
	setup: function (frm) {
		frm.set_query("form_tour", function () {
			return {
				filters: {
					reference_doctype: frm.doc.reference_document,
				},
			};
		});
	},

	refresh: function (frm) {
		frappe.boot.developer_mode &&
			frm.set_intro(
				__(
					"To export this step as JSON, link it in a Onboarding document and save the document."
				),
				true
			);
		if (frm.doc.reference_document && frm.doc.action == "Update Settings") {
			setup_fields(frm);
		}

		if (!frappe.boot.developer_mode) {
			frm.trigger("disable_form");
		}
	},

	reference_document: function (frm) {
		if (frm.doc.reference_document && frm.doc.action == "Update Settings") {
			setup_fields(frm);
		}
	},

	action: function (frm) {
		if (frm.doc.action == "Show Form Tour") {
			frm.fields_dict.reference_document
				.set_description(`You need to add the steps in the contoller JS file. For example: <code>note.js</code>
<pre class="small text-muted"><code>
frappe.tour['Note'] = [
	{
		fieldname: "title",
		title: "Title of the Note",
		description: "...",
	}
];
</code></pre>
				`);
		} else {
			frm.fields_dict.reference_document.set_description(null);
		}
	},

	disable_form: function (frm) {
		frm.set_read_only();
		frm.fields
			.filter((field) => field.has_input)
			.forEach((field) => {
				frm.set_df_property(field.df.fieldname, "read_only", "1");
			});
		frm.disable_save();
	},
});

function setup_fields(frm) {
	if (frm.doc.reference_document && frm.doc.action == "Update Settings") {
		frappe.model.with_doctype(frm.doc.reference_document, () => {
			let fields = frappe
				.get_meta(frm.doc.reference_document)
				.fields.filter((df) => {
					return ["Data", "Check", "Int", "Link", "Select"].includes(df.fieldtype);
				})
				.map((df) => {
					return {
						label: `${__(df.label, null, df.parent)} (${df.fieldname})`,
						value: df.fieldname,
					};
				});

			frm.set_df_property("field", "options", fields);
		});
	}
}

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
