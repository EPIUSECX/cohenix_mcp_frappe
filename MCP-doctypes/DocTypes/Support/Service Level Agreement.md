# Master Control Plan: `Service Level Agreement`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Support`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:SLA-{document_type}-{service_level}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `document_type` | Apply On | Link | DocType | ✅ |  |  | None | None |
| `default_priority` | Default Priority | Link | Issue Priority |  |  | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `service_level` | Service Level Name | Data | None | ✅ |  |  | None | None |
| `enabled` | Enabled | Check | None |  |  |  | 1 | None |
| `filters_section` | Assignment Conditions | Section Break | None |  |  |  | None | None |
| `default_service_level_agreement` | Default Service Level Agreement | Check | None |  |  |  | 0 | None |
| `entity_type` | Entity Type | Select | 
Customer
Customer Group
Territory |  |  |  | None | None |
| `entity` | Entity | Dynamic Link | entity_type |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `condition` | Condition | Code | PythonExpression |  |  |  | None | Simple Python Expression, Example: doc.status == 'Open' and doc.issue_type == 'Bug' |
| `agreement_details_section` | Valid From | Section Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `end_date` | End Date | Date | None |  |  |  | None | None |
| `response_and_resolution_time_section` | Response and Resolution | Section Break | None |  |  |  | None | None |
| `apply_sla_for_resolution` | Apply SLA for Resolution Time | Check | None |  |  |  | 1 | None |
| `priorities` | Priorities | Table | Service Level Priority | ✅ |  |  | None | None |
| `status_details` | Status Details | Section Break | None |  |  |  | None | None |
| `sla_fulfilled_on` | SLA Fulfilled On | Table | SLA Fulfilled On Status | ✅ |  |  | None | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `pause_sla_on` | SLA Paused On | Table | Pause SLA On Status |  |  |  | None | None |
| `support_and_resolution_section_break` | Working Hours | Section Break | None |  |  |  | None | None |
| `holiday_list` | Holiday List | Link | Holiday List | ✅ |  |  | None | None |
| `support_and_resolution` | Working Hours | Table | Service Day | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 1
- **Table Fields:** 4

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/support/doctype/service_level_agreement/service_level_agreement.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Service Level Agreement", {
	setup: function (frm) {
		if (cint(frm.doc.apply_sla_for_resolution) === 1) {
			frm.get_field("priorities").grid.editable_fields = [
				{ fieldname: "default_priority", columns: 1 },
				{ fieldname: "priority", columns: 2 },
				{ fieldname: "response_time", columns: 2 },
				{ fieldname: "resolution_time", columns: 2 },
			];
		} else {
			frm.get_field("priorities").grid.editable_fields = [
				{ fieldname: "default_priority", columns: 1 },
				{ fieldname: "priority", columns: 2 },
				{ fieldname: "response_time", columns: 3 },
			];
		}
	},

	refresh: function (frm) {
		frm.trigger("fetch_status_fields");
		frm.trigger("toggle_resolution_fields");
		frm.trigger("default_service_level_agreement");
		frm.trigger("entity");
	},

	default_service_level_agreement: function (frm) {
		const field = frm.get_field("default_service_level_agreement");
		if (frm.doc.default_service_level_agreement) {
			field.set_description(__("SLA will be applied on every {0}", [frm.doc.document_type]));
		} else {
			field.set_description(__("Enable to apply SLA on every {0}", [frm.doc.document_type]));
		}
	},

	document_type: function (frm) {
		frm.trigger("fetch_status_fields");
		frm.trigger("default_service_level_agreement");
	},

	entity_type: function (frm) {
		frm.set_value("entity", undefined);
	},

	entity: function (frm) {
		const field = frm.get_field("entity");
		if (frm.doc.entity) {
			const and_descendants = frm.doc.entity_type != "Customer" ? " " + __("or its descendants") : "";
			field.set_description(
				__("SLA will be applied if {1} is set as {2}{3}", [
					frm.doc.document_type,
					frm.doc.entity_type,
					frm.doc.entity,
					and_descendants,
				])
			);
		} else {
			field.set_description("");
		}
	},

	fetch_status_fields: function (frm) {
		let allow_statuses = [];
		let exclude_statuses = [];

		if (frm.doc.document_type) {
			frappe.model.with_doctype(frm.doc.document_type, () => {
				let statuses = frappe.meta.get_docfield(
					frm.doc.document_type,
					"status",
					frm.doc.name
				).options;
				statuses = statuses.split("\n");

				exclude_statuses = ["Open", "Closed"];
				allow_statuses = statuses.filter((status) => !exclude_statuses.includes(status));

				frm.fields_dict.pause_sla_on.grid.update_docfield_property(
					"status",
					"options",
					[""].concat(allow_statuses)
				);

				exclude_statuses = ["Open"];
				allow_statuses = statuses.filter((status) => !exclude_statuses.includes(status));
				frm.fields_dict.sla_fulfilled_on.grid.update_docfield_property(
					"status",
					"options",
					[""].concat(allow_statuses)
				);
			});
		}

		frm.refresh_field("pause_sla_on");
	},

	apply_sla_for_resolution: function (frm) {
		frm.trigger("toggle_resolution_fields");
	},

	toggle_resolution_fields: function (frm) {
		if (cint(frm.doc.apply_sla_for_resolution) === 1) {
			frm.fields_dict.priorities.grid.update_docfield_property("resolution_time", "hidden", 0);
			frm.fields_dict.priorities.grid.update_docfield_property("resolution_time", "reqd", 1);
		} else {
			frm.fields_dict.priorities.grid.update_docfield_property("resolution_time", "hidden", 1);
			frm.fields_dict.priorities.grid.update_docfield_property("resolution_time", "reqd", 0);
		}

		frm.refresh_field("priorities");
	},

	onload: function (frm) {
		frm.set_query("document_type", function () {
			let invalid_doctypes = frappe.model.core_doctypes_list;
			invalid_doctypes.push(frm.doc.doctype, "Cost Center", "Company");

			return {
				filters: [
					["DocType", "issingle", "=", 0],
					["DocType", "istable", "=", 0],
					["DocType", "is_submittable", "=", 0],
					["DocType", "name", "not in", invalid_doctypes],
					[
						"DocType",
						"module",
						"not in",
						[
							"Email",
							"Core",
							"Custom",
							"Event Streaming",
							"Social",
							"Data Migration",
							"Geo",
							"Desk",
						],
					],
				],
			};
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
