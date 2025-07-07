# Master Control Plan: `Form Tour`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:title`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `view_name` | View | Select | Workspaces
List
Form
Tree
Page |  |  |  | None | None |
| `workspace_name` | Select Workspace | Link | Workspace |  |  |  | None | None |
| `list_name` | Select List View | Select | List
Report
Dashboard
Kanban
Gantt
Calendar
File
Image
Inbox
Map |  |  |  | List | None |
| `report_name` | Select Report | Link | Report |  |  |  | None | None |
| `dashboard_name` | Select Dashboard | Link | Dashboard |  |  |  | None | None |
| `new_document_form` | New Document Form | Check | None |  |  |  | 0 | None |
| `page_name` | Select Page | Link | Page |  |  |  | None | None |
| `reference_doctype` | Reference Document | Link | DocType |  |  |  | None | None |
| `module` | Module | Link | Module Def |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `ui_tour` | UI Tour | Check | None |  |  |  | 0 | None |
| `track_steps` | Track Steps | Check | None |  |  |  | 0 | The next tour will start from where the user left off. |
| `is_standard` | Is Standard | Check | None |  |  |  | 0 | None |
| `save_on_complete` | Save on Completion | Check | None |  |  |  | 0 | None |
| `first_document` | Show First Document Tour | Check | None |  |  |  | 0 | None |
| `include_name_field` | Include Name Field | Check | None |  |  |  | 0 | None |
| `page_route` | Page Route | Small Text | None |  | ✅ |  | None | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `steps` | Steps | Table | Form Tour Step | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/form_tour/form_tour.js`
```javascript
// Copyright (c) 2021, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Form Tour", {
	refresh(frm) {
		if (frm.doc.is_standard && !frappe.boot.developer_mode) {
			frm.trigger("disable_form");
		}
		frm.set_query("reference_doctype", () => {
			return { filters: { istable: 0 } };
		});
		frm.trigger("reference_doctype");
		frm.set_query("report_name", () => {
			if (frm.doc.reference_doctype) {
				return {
					filters: {
						ref_doctype: frm.doc.reference_doctype,
					},
				};
			}
			return {};
		});
		!frm.is_new() && add_custom_button(frm);
	},
	async report_name(frm) {
		if (!frm.doc.ui_tour || !frm.doc.report_name) return;
		let { message } = await frappe.db.get_value("Report", frm.doc.report_name, "ref_doctype");
		frm.set_value("reference_doctype", message?.ref_doctype || "");
	},
	async before_save(frm) {
		if (
			frm.doc.select_view == "List" &&
			frm.doc.list_name == "Dashboard" &&
			frm.doc.dashboard_name &&
			frm.doc.reference_doctype
		) {
			frappe.throw(
				__("Referance Doctype and Dashboard Name both can't be used at the same time.")
			);
		}
		frm.doc.ui_tour && (frm.doc.page_route = JSON.stringify(await get_path(frm)));
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

	reference_doctype(frm) {
		if (!frm.doc.reference_doctype) return;

		frm.set_fields_as_options("fieldname", frm.doc.reference_doctype, (df) => !df.hidden).then(
			(options) => {
				frm.fields_dict.steps.grid.update_docfield_property(
					"fieldname",
					"options",
					[""].concat(options)
				);
			}
		);

		frm.set_fields_as_options(
			"parent_fieldname",
			frm.doc.reference_doctype,
			(df) => df.fieldtype == "Table" && !df.hidden
		).then((options) => {
			frm.fields_dict.steps.grid.update_docfield_property(
				"parent_fieldname",
				"options",
				[""].concat(options)
			);
		});
		if (!frm.doc.ui_tour) {
			// remove report name if reference doctype is changed and report name is not valid.
			frappe.db
				.get_list(
					"Report",
					{
						filters: {
							ref_doctype: frm.doc.reference_doctype,
						},
					},
					{ fields: ["name"] }
				)
				.then((reports) => {
					if (reports.findIndex((r) => r.name == frm.doc.report_name) == -1) {
						frm.set_value("report_name", "");
						frm.refresh_field("report_name");
					}
				});
		}
	},
});

let add_custom_button = (frm) => {
	if (frm.doc.ui_tour) {
		frm.add_custom_button(__("Reset"), function () {
			frappe.confirm(
				__("This will reset this tour and show it to all users. Are you sure?"),
				function () {
					frappe.call({
						method: "frappe.desk.doctype.form_tour.form_tour.reset_tour",
						args: {
							tour_name: frm.doc.name,
						},
					});
					delete frappe.boot.user.onboarding_status[frm.doc.name];
				}
			);
		});
	} else {
		frm.add_custom_button(__("Show Tour"), async () => {
			const issingle = await check_if_single(frm.doc.reference_doctype);
			let route_changed = null;

			if (issingle) {
				route_changed = frappe.set_route("Form", frm.doc.reference_doctype);
			} else if (frm.doc.first_document) {
				const name = await get_first_document(frm.doc.reference_doctype);
				route_changed = frappe.set_route("Form", frm.doc.reference_doctype, name);
			} else {
				route_changed = frappe.set_route("Form", frm.doc.reference_doctype, "new");
			}
			route_changed.then(() => {
				const tour_name = frm.doc.name;
				cur_frm.tour.init({ tour_name }).then(() => cur_frm.tour.start());
			});
		});
	}
};

frappe.ui.form.on("Form Tour Step", {
	form_render(frm, cdt, cdn) {
		if (locals[cdt][cdn].is_table_field) {
			frm.trigger("parent_fieldname", cdt, cdn);
		}
	},
	parent_fieldname(frm, cdt, cdn) {
		const child_row = locals[cdt][cdn];

		const parent_fieldname_df = frappe
			.get_meta(frm.doc.reference_doctype)
			.fields.find((df) => df.fieldname == child_row.parent_fieldname);

		frm.set_fields_as_options(
			"fieldname",
			parent_fieldname_df.options,
			(df) => !df.hidden
		).then((options) => {
			frm.fields_dict.steps.grid.update_docfield_property(
				"fieldname",
				"options",
				[""].concat(options)
			);
			if (child_row.fieldname) {
				frappe.model.set_value(cdt, cdn, "fieldname", child_row.fieldname);
			}
		});
	},
});

async function check_if_single(doctype) {
	const { message } = await frappe.db.get_value("DocType", doctype, "issingle");
	return message.issingle || 0;
}
async function check_if_private_workspace(name) {
	const { message } = await frappe.db.get_value("Workspace", name, "public");
	return !message.public || 0;
}

async function get_first_document(doctype) {
	let docname;

	await frappe.db.get_list(doctype, { order_by: "creation" }).then((res) => {
		if (Array.isArray(res) && res.length) docname = res[0].name;
	});

	return docname || "new";
}

async function get_path(frm) {
	let route = [frm.doc.view_name];
	switch (route[0]) {
		case "Workspaces":
			frm.doc.list_name = "";
			frm.doc.new_document_form = 0;
			frm.doc.report_name = "";
			frm.doc.page_name = "";
			frm.doc.dashboard_name = "";
			frm.doc.reference_doctype = "";
			if (!frm.doc.workspace_name) {
				route.push("*");
				return route;
			}
			if (await check_if_private_workspace(frm.doc.workspace_name)) {
				route.push("private");
			}
			route.push(frm.doc.workspace_name);
			return route;
		case "List":
			frm.doc.workspace_name = "";
			frm.doc.new_document_form = 0;
			frm.doc.list_name != "Report" && (frm.doc.report_name = "");
			frm.doc.list_name != "Dashboard" && (frm.doc.dashboard_name = "");
			frm.doc.page_name = "";
			if (frm.doc.list_name == "File") return ["List", "File"];
			if (!frm.doc.reference_doctype) {
				if (frm.doc.list_name == "Dashboard")
					return ["dashboard-view", frm.doc.dashboard_name || "*"];
				route.push("*");
			} else {
				route.push(frm.doc.reference_doctype);
			}
			route.push(frm.doc.list_name);
			return route;
		case "Form":
			frm.doc.workspace_name = "";
			frm.doc.list_name = "";
			frm.doc.report_name = "";
			frm.doc.page_name = "";
			frm.doc.dashboard_name = "";
			if (!frm.doc.reference_doctype) {
				route.push("*");
				frm.doc.new_document_form && route.push("new-*");
				return route;
			}
			route.push(frm.doc.reference_doctype);
			if (await check_if_single(frm.doc.reference_doctype)) {
				route.push(frm.doc.reference_doctype);
			} else if (frm.doc.new_document_form) {
				route.push("new-" + frappe.router.slug(frm.doc.reference_doctype));
			}
			return route;
		case "Tree":
			frm.doc.workspace_name = "";
			frm.doc.list_name = "";
			frm.doc.new_document_form = 0;
			frm.doc.report_name = "";
			frm.doc.page_name = "";
			frm.doc.dashboard_name = "";
			return route;
		case "Page":
			frm.doc.workspace_name = "";
			frm.doc.list_name = "";
			frm.doc.new_document_form = 0;
			frm.doc.report_name = "";
			frm.doc.dashboard_name = "";
			frm.doc.reference_doctype = "";
			return [frm.doc.page_name];
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
