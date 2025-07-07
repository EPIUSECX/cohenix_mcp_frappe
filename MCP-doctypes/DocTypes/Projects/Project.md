# Master Control Plan: `Project`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Projects`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Employee | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Projects Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Projects User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | PROJ-.#### | ✅ |  |  | None | None |
| `project_name` | Project Name | Data | None | ✅ |  |  | None | None |
| `status` | Status | Select | Open
Completed
Cancelled |  |  |  | Open | None |
| `project_type` | Project Type | Link | Project Type |  |  |  | None | None |
| `is_active` | Is Active | Select | Yes
No |  |  |  | None | None |
| `percent_complete_method` | % Complete Method | Select | Manual
Task Completion
Task Progress
Task Weight |  |  |  | Task Completion | None |
| `percent_complete` | % Completed | Percent | None |  |  | ✅ | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `project_template` | From Template | Link | Project Template |  |  |  | None | None |
| `expected_start_date` | Expected Start Date | Date | None |  |  |  | None | None |
| `expected_end_date` | Expected End Date | Date | None |  |  |  | None | None |
| `priority` | Priority | Select | Medium
Low
High |  |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `customer_details` | Customer Details | Section Break | fa fa-user |  |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  |  | None | None |
| `users_section` | Users | Section Break | None |  |  |  | None | None |
| `users` | Users | Table | Project User |  |  |  | None | Project will be accessible on the website to these users |
| `copied_from` | Copied From | Data | None |  | ✅ | ✅ | None | None |
| `section_break0` | Notes | Section Break | fa fa-list |  |  |  | None | None |
| `notes` | Notes | Text Editor | None |  |  |  | None | None |
| `section_break_18` | Start and End Dates | Section Break | None |  |  |  | None | None |
| `actual_start_date` | Actual Start Date (via Timesheet) | Date | None |  |  | ✅ | None | None |
| `actual_time` | Actual Time in Hours (via Timesheet) | Float | None |  |  | ✅ | None | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `actual_end_date` | Actual End Date (via Timesheet) | Date | None |  |  | ✅ | None | None |
| `project_details` | Costing and Billing | Section Break | fa fa-money |  |  |  | None | None |
| `estimated_costing` | Estimated Cost | Currency | Company:company:default_currency |  |  |  | None | None |
| `total_costing_amount` | Total Costing Amount (via Timesheet) | Currency | None |  |  | ✅ | None | None |
| `total_expense_claim` | Total Expense Claim (via Expense Claims) | Currency | None |  |  | ✅ | None | None |
| `total_purchase_cost` | Total Purchase Cost (via Purchase Invoice) | Currency | None |  |  | ✅ | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `total_sales_amount` | Total Sales Amount (via Sales Order) | Currency | None |  |  | ✅ | None | None |
| `total_billable_amount` | Total Billable Amount (via Timesheet) | Currency | None |  |  | ✅ | None | None |
| `total_billed_amount` | Total Billed Amount (via Sales Invoice) | Currency | None |  |  | ✅ | None | None |
| `total_consumed_material_cost` | Total Consumed Material Cost (via Stock Entry) | Currency | None |  |  | ✅ | None | None |
| `cost_center` | Default Cost Center | Link | Cost Center |  |  |  | None | None |
| `margin` | Margin | Section Break | None |  |  |  | None | None |
| `gross_margin` | Gross Margin | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_37` | None | Column Break | None |  |  |  | None | None |
| `per_gross_margin` | Gross Margin % | Percent | None |  |  | ✅ | None | None |
| `monitor_progress` | Monitor Progress | Section Break | None |  |  |  | None | None |
| `collect_progress` | Collect Progress | Check | None |  |  |  | 0 | None |
| `holiday_list` | Holiday List | Link | Holiday List |  |  |  | None | None |
| `frequency` | Frequency To Collect Progress | Select | Hourly
Twice Daily
Daily
Weekly |  |  |  | None | None |
| `from_time` | From Time | Time | None |  |  |  | None | None |
| `to_time` | To Time | Time | None |  |  |  | None | None |
| `first_email` | First Email | Time | None |  |  |  | None | None |
| `second_email` | Second Email | Time | None |  |  |  | None | None |
| `daily_time_to_send` | Daily Time to send | Time | None |  |  |  | None | None |
| `day_to_send` | Day to Send | Select | Monday
Tuesday
Wednesday
Thursday
Friday
Saturday
Sunday |  |  |  | None | None |
| `weekly_time_to_send` | Weekly Time to send | Time | None |  |  |  | None | None |
| `column_break_45` | None | Column Break | None |  |  |  | None | None |
| `message` | Message | Text | None |  |  |  | None | Message will be sent to the users to get their status on the Project |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `total_expense_claim` | Total Expense Claim (via Expense Claims) | Currency | None |  |  | ✅ | None | None |



### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/project/project.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt
frappe.ui.form.on("Project", {
	setup(frm) {
		frm.make_methods = {
			Timesheet: () => {
				open_form(frm, "Timesheet", "Timesheet Detail", "time_logs");
			},
			"Purchase Order": () => {
				open_form(frm, "Purchase Order", "Purchase Order Item", "items");
			},
			"Purchase Receipt": () => {
				open_form(frm, "Purchase Receipt", "Purchase Receipt Item", "items");
			},
			"Purchase Invoice": () => {
				open_form(frm, "Purchase Invoice", "Purchase Invoice Item", "items");
			},
		};
	},
	onload: function (frm) {
		const so = frm.get_docfield("sales_order");
		so.get_route_options_for_new_doc = () => {
			if (frm.is_new()) return {};
			return {
				customer: frm.doc.customer,
				project_name: frm.doc.name,
			};
		};

		frm.set_query("user", "users", function () {
			return {
				query: "erpnext.projects.doctype.project.project.get_users_for_project",
			};
		});

		frm.set_query("department", function (doc) {
			return {
				filters: {
					company: doc.company,
				},
			};
		});

		// sales order
		frm.set_query("sales_order", function () {
			var filters = {
				project: ["in", frm.doc.__islocal ? [""] : [frm.doc.name, ""]],
				company: frm.doc.company,
			};

			if (frm.doc.customer) {
				filters["customer"] = frm.doc.customer;
			}

			return {
				filters: filters,
			};
		});

		frm.set_query("cost_center", () => {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
	},

	refresh: function (frm) {
		if (frm.doc.__islocal) {
			frm.web_link && frm.web_link.remove();
		} else {
			frm.add_web_link("/projects?project=" + encodeURIComponent(frm.doc.name));

			frm.trigger("show_dashboard");
		}
		frm.trigger("set_custom_buttons");
	},

	set_custom_buttons: function (frm) {
		if (!frm.is_new()) {
			frm.add_custom_button(
				__("Duplicate Project with Tasks"),
				() => {
					frm.events.create_duplicate(frm);
				},
				__("Actions")
			);

			frm.add_custom_button(
				__("Update Total Purchase Cost"),
				() => {
					frm.events.update_total_purchase_cost(frm);
				},
				__("Actions")
			);

			frm.trigger("set_project_status_button");

			if (frappe.model.can_read("Task")) {
				frm.add_custom_button(
					__("Gantt Chart"),
					function () {
						frappe.route_options = {
							project: frm.doc.name,
						};
						frappe.set_route("List", "Task", "Gantt");
					},
					__("View")
				);

				frm.add_custom_button(
					__("Kanban Board"),
					() => {
						frappe
							.call(
								"erpnext.projects.doctype.project.project.create_kanban_board_if_not_exists",
								{
									project: frm.doc.name,
								}
							)
							.then(() => {
								frappe.set_route("List", "Task", "Kanban", frm.doc.project_name);
							});
					},
					__("View")
				);
			}
		}
	},

	update_total_purchase_cost: function (frm) {
		frappe.call({
			method: "erpnext.projects.doctype.project.project.recalculate_project_total_purchase_cost",
			args: { project: frm.doc.name },
			freeze: true,
			freeze_message: __("Recalculating Purchase Cost against this Project..."),
			callback: function (r) {
				if (r && !r.exc) {
					frappe.msgprint(__("Total Purchase Cost has been updated"));
					frm.refresh();
				}
			},
		});
	},

	set_project_status_button: function (frm) {
		frm.add_custom_button(
			__("Set Project Status"),
			() => frm.events.get_project_status_dialog(frm).show(),
			__("Actions")
		);
	},

	get_project_status_dialog: function (frm) {
		const dialog = new frappe.ui.Dialog({
			title: __("Set Project Status"),
			fields: [
				{
					fieldname: "status",
					fieldtype: "Select",
					label: "Status",
					reqd: 1,
					options: "Completed\nCancelled",
				},
			],
			primary_action: function () {
				frm.events.set_status(frm, dialog.get_values().status);
				dialog.hide();
			},
			primary_action_label: __("Set Project Status"),
		});
		return dialog;
	},

	create_duplicate: function (frm) {
		return new Promise((resolve) => {
			frappe.prompt("Project Name", (data) => {
				frappe
					.xcall("erpnext.projects.doctype.project.project.create_duplicate_project", {
						prev_doc: frm.doc,
						project_name: data.value,
					})
					.then(() => {
						frappe.set_route("Form", "Project", data.value);
						frappe.show_alert(__("Duplicate project has been created"));
					});
				resolve();
			});
		});
	},

	set_status: function (frm, status) {
		frappe.confirm(__("Set Project and all Tasks to status {0}?", [__(status).bold()]), () => {
			frappe
				.xcall("erpnext.projects.doctype.project.project.set_project_status", {
					project: frm.doc.name,
					status: status,
				})
				.then(() => {
					frm.reload_doc();
				});
		});
	},
});

function open_form(frm, doctype, child_doctype, parentfield) {
	frappe.model.with_doctype(doctype, () => {
		let new_doc = frappe.model.get_new_doc(doctype);

		// add a new row and set the project
		let new_child_doc = frappe.model.get_new_doc(child_doctype);
		new_child_doc.project = frm.doc.name;
		new_child_doc.parent = new_doc.name;
		new_child_doc.parentfield = parentfield;
		new_child_doc.parenttype = doctype;
		new_doc[parentfield] = [new_child_doc];
		new_doc.project = frm.doc.name;

		frappe.ui.form.make_quick_entry(doctype, null, null, new_doc);
	});
}

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Project Summary` | Script Report | Projects |
| `Project wise Stock Tracking` | Script Report | Projects |



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
