# Master Control Plan: `Prepared Report`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Prepared Report User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `status` | Status | Select | Error
Queued
Completed
Started |  | ✅ | ✅ | Queued | None |
| `report_name` | Report Name | Data | None | ✅ |  | ✅ | None | None |
| `queued_by` | Queued By | Data | None |  |  | ✅ | None | None |
| `job_id` | Job ID | Data | None |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `queued_at` | Queued At | Datetime | None |  |  | ✅ | None | None |
| `report_end_time` | Finished At | Datetime | None |  |  | ✅ | None | None |
| `peak_memory_usage` | Peak Memory Usage | Int | None |  |  | ✅ | None | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `error_message` | Error Message | Text | None |  |  | ✅ | None | None |
| `filters_sb` | Filters | Section Break | None |  |  |  | None | None |
| `filters` | Filters | Small Text | None |  | ✅ | ✅ | None | None |
| `filter_values` | Filter Values | HTML | None |  | ✅ |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/prepared_report/prepared_report.js`
```javascript
// Copyright (c) 2018, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Prepared Report", {
	render_filter_values: function (frm, filters) {
		var wrapper = $(frm.fields_dict["filter_values"].wrapper).empty();

		let filter_table = $(`<table class="table table-bordered">
			<thead>
				<tr>
					<td>${__("Filter")}</td>
					<td>${__("Value")}</td>
				</tr>
			</thead>
			<tbody></tbody>
		</table>`);

		Object.keys(filters).forEach((key) => {
			const filter_row = $(`<tr>
				<td>${frappe.model.unscrub(key)}</td>
				<td>${filters[key]}</td>
			</tr>`);
			filter_table.find("tbody").append(filter_row);
		});

		wrapper.append(filter_table);
	},

	refresh: function (frm) {
		frm.disable_save();

		const filters = JSON.parse(frm.doc.filters);
		if (!$.isEmptyObject(filters)) {
			frm.toggle_display(["filter_values"], 1);
			frm.events.render_filter_values(frm, filters);
		}

		// always keep report_name hidden - we do this as we can't set mandatory and hidden
		// property on a docfield at the same time
		frm.toggle_display(["report_name"], 0);

		if (frm.doc.status == "Completed") {
			frm.page.set_primary_action(__("Show Report"), () => {
				frappe.route_options = { prepared_report_name: frm.doc.name };
				frappe.set_route("query-report", frm.doc.report_name);
			});
			let csv_attached = (frm.get_files() || []).some((f) => f.file_url.endsWith(".csv"));
			if (!csv_attached) {
				frm.add_custom_button(__("Download as CSV"), function () {
					frappe.call({
						method: "frappe.core.doctype.prepared_report.prepared_report.enqueue_json_to_csv_conversion",
						args: {
							prepared_report_name: frm.doc.name,
						},
						callback: function () {
							frappe.msgprint(
								__(
									"Your CSV file is being generated and will appear in the Attachments section once ready. Additionally, you will get notified when the file is available for download."
								)
							);
						},
					});
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
| Name | Type | Module |
|---|---|---|
| `Prepared Report Analytics` | Script Report | Core |



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
