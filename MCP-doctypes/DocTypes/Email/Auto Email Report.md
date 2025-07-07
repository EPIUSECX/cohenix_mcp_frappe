# Master Control Plan: `Auto Email Report`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Email`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Report Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `report` | Report | Link | Report | ✅ |  |  | None | None |
| `user` | Based on Permissions For User | Link | User | ✅ |  |  | User | None |
| `enabled` | Enabled | Check | None |  |  |  | 1 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `report_type` | Report Type | Read Only | None |  |  |  | None | None |
| `reference_report` | Reference Report | Data | None |  | ✅ | ✅ | None | None |
| `filter_data` | Filter Data | Section Break | None |  |  |  | None | None |
| `send_if_data` | Send only if there is any data | Check | None |  |  |  | 1 | None |
| `data_modified_till` | Only Send Records Updated in Last X Hours | Int | None |  |  |  | None | Zero means send records updated at anytime |
| `no_of_rows` | No of Rows (Max 500) | Int | None |  |  |  | 100 | None |
| `report_filters` | Report Filters | Section Break | None |  |  |  | None | None |
| `filters_display` | Filters Display | HTML | None |  |  |  | None | None |
| `filters` | Filters | Text | None |  | ✅ |  | None | None |
| `filter_meta` | Filter Meta | Text | None |  | ✅ | ✅ | None | None |
| `dynamic_report_filters_section` | Dynamic Report Filters | Section Break | None |  |  |  | None | None |
| `from_date_field` | From Date Field | Select | None |  |  |  | None | None |
| `to_date_field` | To Date Field | Select | None |  |  |  | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `dynamic_date_period` | Period | Select | 
Daily
Weekly
Monthly
Quarterly
Half Yearly
Yearly |  |  |  | None | None |
| `use_first_day_of_period` | Use First Day of Period | Check | None |  |  |  | 0 | To begin the date range at the start of the chosen period. For example, if 'Year' is selected as the period, the report will start from January 1st of the current year. |
| `email_settings` | Email Settings | Section Break | None |  |  |  | None | None |
| `email_to` | Email To | Small Text | None | ✅ |  |  | None | For multiple addresses, enter the address on different line. e.g. test@test.com ⏎ test1@test.com |
| `day_of_week` | Day of Week | Select | Monday
Tuesday
Wednesday
Thursday
Friday
Saturday
Sunday |  |  |  | Monday | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `sender` | Sender | Link | Email Account |  |  |  | None | None |
| `frequency` | Frequency | Select | Daily
Weekdays
Weekly
Monthly | ✅ |  |  | None | None |
| `format` | Format | Select | HTML
XLSX
CSV | ✅ |  |  | None | None |
| `section_break_15` | Message | Section Break | None |  |  |  | None | None |
| `description` | Message | Text Editor | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/auto_email_report/auto_email_report.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Auto Email Report", {
	refresh: function (frm) {
		frm.trigger("fetch_report_filters");
		if (!frm.is_new()) {
			frm.add_custom_button(__("Download"), function () {
				var w = window.open(
					frappe.urllib.get_full_url(
						"/api/method/frappe.email.doctype.auto_email_report.auto_email_report.download?" +
							"name=" +
							encodeURIComponent(frm.doc.name)
					)
				);
				if (!w) {
					frappe.msgprint(__("Please enable pop-ups"));
					return;
				}
			});
			frm.add_custom_button(__("Send Now"), function () {
				frappe.call({
					method: "frappe.email.doctype.auto_email_report.auto_email_report.send_now",
					args: { name: frm.doc.name },
					callback: function () {
						frappe.msgprint(__("Scheduled to send"));
					},
				});
			});
		} else {
			if (!frm.doc.user) {
				frm.set_value("user", frappe.session.user);
			}
			if (!frm.doc.email_to) {
				frm.set_value("email_to", frappe.session.user);
			}
		}

		frm.set_query("sender", function () {
			return {
				filters: {
					enable_outgoing: 1,
					awaiting_password: 0,
				},
			};
		});
	},
	report: function (frm) {
		frm.set_value("filters", "");
		frm.trigger("fetch_report_filters");
	},
	fetch_report_filters(frm) {
		if (
			frm.doc.report &&
			frm.doc.report_type !== "Report Builder" &&
			frm.script_setup_for !== frm.doc.report
		) {
			frappe.call({
				method: "frappe.desk.query_report.get_script",
				args: {
					report_name: frm.doc.report,
				},
				callback: function (r) {
					frappe.dom.eval(r.message.script || "");
					frm.script_setup_for = frm.doc.report;
					frm.trigger("show_filters");
				},
			});
		} else {
			frm.trigger("show_filters");
		}
	},
	show_filters: async function (frm) {
		if (!frm.doc.report) {
			return;
		}
		var wrapper = $(frm.get_field("filters_display").wrapper);
		wrapper.empty();
		let reference_report = frappe.query_reports[frm.doc.report];
		if (!reference_report || !reference_report.filters) {
			reference_report = await frappe.model.with_doc("Report", frm.doc.report);
		}
		if (
			frm.doc.report_type === "Custom Report" ||
			(frm.doc.report_type !== "Report Builder" &&
				reference_report &&
				reference_report.filters)
		) {
			// make a table to show filters
			var table = $(
				'<table class="table table-bordered" style="cursor:pointer; margin:0px;"><thead>\
				<tr><th style="width: 50%">' +
					__("Filter") +
					"</th><th>" +
					__("Value") +
					"</th></tr>\
				</thead><tbody></tbody></table>"
			).appendTo(wrapper);
			$('<p class="text-muted small">' + __("Click table to edit") + "</p>").appendTo(
				wrapper
			);

			var filters = {};
			var dialog;
			let report_filters;

			if (
				frm.doc.report_type === "Custom Report" &&
				reference_report &&
				reference_report.filters
			) {
				if (frm.doc.filters) {
					filters = JSON.parse(frm.doc.filters);
				} else {
					frappe.db.get_value("Report", frm.doc.report, "json", (r) => {
						if (r && r.json) {
							filters = JSON.parse(r.json).filters || {};
						}
					});
				}

				report_filters = frappe.query_reports[frm.doc.reference_report].filters;
			} else {
				filters = JSON.parse(frm.doc.filters || "{}");
				report_filters = reference_report.filters;
			}

			if (report_filters && report_filters.length > 0) {
				frm.set_value("filter_meta", JSON.stringify(report_filters));
				if (frm.is_dirty()) {
					frm.save();
				}
			}

			var report_filters_list = [];
			$.each(report_filters, function (key, val) {
				// Remove break fieldtype from the filters
				if (val.fieldtype != "Break") {
					if (val.fieldtype === "MultiSelectList") {
						val.get_data = (txt) => {
							if (!dialog || !val.options) return [];

							if (Array.isArray(val.options)) return val.options;

							const doctype_link =
								frappe.scrub(val.options) === val.options
									? dialog.get_value(val.options)
									: val.options;

							return doctype_link
								? frappe.db.get_link_options(doctype_link, txt)
								: [];
						};
					}
					report_filters_list.push(val);
				}
			});
			report_filters = report_filters_list;

			const mandatory_css = {
				"background-color": "var(--error-bg)",
				"font-weight": "bold",
			};

			report_filters.forEach((f) => {
				const css = f.reqd ? mandatory_css : {};
				const row = $("<tr></tr>").appendTo(table.find("tbody"));
				$("<td>" + f.label + "</td>").appendTo(row);
				$("<td>" + frappe.format(filters[f.fieldname], f) + "</td>")
					.css(css)
					.appendTo(row);
			});

			table.on("click", function () {
				dialog = new frappe.ui.Dialog({
					fields: report_filters,
					primary_action: function () {
						var values = this.get_values();
						if (values) {
							this.hide();
							frm.set_value("filters", JSON.stringify(values));
							frm.trigger("show_filters");
						}
					},
				});
				dialog.show();
				dialog.set_values(filters);
			});

			// populate dynamic date field selection
			let date_fields = report_filters
				.filter((df) => df.fieldtype === "Date")
				.map((df) => ({ label: df.label, value: df.fieldname }));
			frm.set_df_property("from_date_field", "options", date_fields);
			frm.set_df_property("to_date_field", "options", date_fields);
			frm.toggle_display("dynamic_report_filters_section", date_fields.length > 0);
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
