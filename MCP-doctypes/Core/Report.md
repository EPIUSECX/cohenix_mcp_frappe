# Master Control Plan: `Report`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:report_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Report Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `report_name` | Report Name | Data | None | ✅ |  |  | None | None |
| `ref_doctype` | Ref DocType | Link | DocType | ✅ |  |  | None | None |
| `reference_report` | Reference Report | Data | None |  |  |  | None | None |
| `is_standard` | Is Standard | Select | No
Yes | ✅ |  |  | None | None |
| `module` | Module | Link | Module Def |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `report_type` | Report Type | Select | Report Builder
Query Report
Script Report
Custom Report | ✅ |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `add_total_row` | Add Total Row | Check | None |  |  |  | 0 | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `prepared_report` | Prepared Report | Check | None |  |  |  | 0 | None |
| `add_translate_data` | Add Translate Data | Check | None |  |  |  | 0 | None |
| `timeout` | Timeout (In Seconds) | Int | None |  |  |  | None | Specify a custom timeout, default timeout is 1500 seconds |
| `filters_section` | Filters | Section Break | None |  |  |  | None | None |
| `filters` | Filters | Table | Report Filter |  |  |  | None | None |
| `columns_section` | Columns | Section Break | None |  |  |  | None | None |
| `columns` | Columns | Table | Report Column |  |  |  | None | None |
| `section_break_6` | Query / Script | Section Break | None |  |  |  | None | None |
| `query` | Query | Code | SQL |  |  |  | None | None |
| `report_script` | Script | Code | Python |  |  |  | None | Filters will be accessible via <code>filters</code>. <br><br>Send output as <code>result = [result]</code>, or for old style <code>data = [columns], [result]</code> |
| `client_code_section` | Client Code | Section Break | None |  |  |  | None | None |
| `javascript` | Javascript | Code | Javascript |  |  |  | None | JavaScript Format: frappe.query_reports['REPORTNAME'] = {} |
| `json` | JSON | Code | None |  |  | ✅ | None | None |
| `permission_rules` | None | Section Break | None |  |  |  | None | None |
| `roles` | Roles | Table | Has Role |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/report/report.js`
```javascript
// Copyright (c) 2022, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Report", {
	refresh: function (frm) {
		if (frm.doc.is_standard === "Yes" && !frappe.boot.developer_mode) {
			// make the document read-only
			frm.disable_form();
		} else {
			frm.enable_save();
		}

		let doc = frm.doc;
		if (!doc.__islocal) {
			frm.add_custom_button(
				__("Show Report"),
				function () {
					switch (doc.report_type) {
						case "Report Builder":
							frappe.set_route("List", doc.ref_doctype, "Report", doc.name);
							break;
						case "Query Report":
							frappe.set_route("query-report", doc.name);
							break;
						case "Script Report":
							frappe.set_route("query-report", doc.name);
							break;
						case "Custom Report":
							frappe.set_route("query-report", doc.name);
							break;
					}
				},
				"fa fa-table"
			);
		}

		if (doc.is_standard === "Yes" && frm.perm[0].write) {
			frm.add_custom_button(
				doc.disabled ? __("Enable Report") : __("Disable Report"),
				function () {
					frm.call("toggle_disable", {
						disable: doc.disabled ? 0 : 1,
					}).then(() => {
						frm.reload_doc();
					});
				},
				doc.disabled ? "fa fa-check" : "fa fa-off"
			);
		}

		frm.set_query("ref_doctype", () => {
			return {
				filters: {
					istable: 0,
				},
			};
		});
	},

	ref_doctype: function (frm) {
		if (frm.doc.ref_doctype) {
			frm.trigger("set_doctype_roles");
		}
	},

	set_doctype_roles: function (frm) {
		return frm.call("set_doctype_roles").then(() => {
			frm.refresh_field("roles");
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
