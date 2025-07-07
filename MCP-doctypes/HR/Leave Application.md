# Master Control Plan: `Leave Application`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** Apply / Approve Leaves

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Leave Approver | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Leave Approver | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| HR User | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | HR-LAP-.YYYY.- | ✅ |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `leave_type` | Leave Type | Link | Leave Type | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `section_break_5` | Dates & Reason | Section Break | None |  |  |  | None | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `to_date` | To Date | Date | None | ✅ |  |  | None | None |
| `half_day` | Half Day | Check | None |  |  |  | 0 | None |
| `half_day_date` | Half Day Date | Date | None |  |  |  | None | None |
| `total_leave_days` | Total Leave Days | Float | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `description` | Reason | Small Text | None |  |  |  | None | None |
| `leave_balance` | Leave Balance Before Application | Float | None |  |  | ✅ | None | None |
| `section_break_7` | Approval | Section Break | None |  |  |  | None | None |
| `leave_approver` | Leave Approver | Link | User |  |  |  | None | None |
| `leave_approver_name` | Leave Approver Name | Data | None |  |  | ✅ | None | None |
| `follow_via_email` | Follow via Email | Check | None |  |  |  | 1 | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `status` | Status | Select | Open
Approved
Rejected
Cancelled | ✅ |  |  | Open | None |
| `sb_other_details` | Other Details | Section Break | None |  |  |  | None | None |
| `salary_slip` | Salary Slip | Link | Salary Slip |  |  |  | None | None |
| `color` | Color | Color | None |  |  |  | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `amended_from` | Amended From | Link | Leave Application |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_application/leave_application.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Leave Application", {
	setup: function (frm) {
		frm.set_query("leave_approver", function () {
			return {
				query: "hrms.hr.doctype.department_approver.department_approver.get_approvers",
				filters: {
					employee: frm.doc.employee,
					doctype: frm.doc.doctype,
				},
			};
		});
		frm.set_query("employee", erpnext.queries.employee);
	},

	onload: function (frm) {
		// Ignore cancellation of doctype on cancel all.
		frm.ignore_doctypes_on_cancel_all = ["Leave Ledger Entry"];

		if (!frm.doc.posting_date) {
			frm.set_value("posting_date", frappe.datetime.get_today());
		}
		if (frm.doc.docstatus == 0) {
			return frappe.call({
				method: "hrms.hr.doctype.leave_application.leave_application.get_mandatory_approval",
				args: {
					doctype: frm.doc.doctype,
				},
				callback: function (r) {
					if (!r.exc && r.message) {
						frm.toggle_reqd("leave_approver", true);
					}
				},
			});
		}
	},

	validate: function (frm) {
		if (frm.doc.from_date === frm.doc.to_date && cint(frm.doc.half_day)) {
			frm.doc.half_day_date = frm.doc.from_date;
		} else if (frm.doc.half_day === 0) {
			frm.doc.half_day_date = "";
		}
		frm.toggle_reqd("half_day_date", cint(frm.doc.half_day));
	},

	make_dashboard: function (frm) {
		let leave_details;
		let lwps;

		if (frm.doc.employee) {
			frappe.call({
				method: "hrms.hr.doctype.leave_application.leave_application.get_leave_details",
				async: false,
				args: {
					employee: frm.doc.employee,
					date: frm.doc.from_date || frm.doc.posting_date,
				},
				callback: function (r) {
					if (!r.exc && r.message["leave_allocation"]) {
						leave_details = r.message["leave_allocation"];
					}
					lwps = r.message["lwps"];
				},
			});

			$("div").remove(".form-dashboard-section.custom");

			frm.dashboard.add_section(
				frappe.render_template("leave_application_dashboard", {
					data: leave_details,
				}),
				__("Allocated Leaves"),
			);
			frm.dashboard.show();

			let allowed_leave_types = Object.keys(leave_details);
			// lwps should be allowed for selection as they don't have any allocation
			allowed_leave_types = allowed_leave_types.concat(lwps);

			frm.set_query("leave_type", function () {
				return {
					filters: [["leave_type_name", "in", allowed_leave_types]],
				};
			});
		}
	},

	refresh: function (frm) {
		hrms.leave_utils.add_view_ledger_button(frm);
		if (frm.is_new()) {
			frm.trigger("calculate_total_days");
		}

		frm.set_intro("");
		if (frm.doc.__islocal && !in_list(frappe.user_roles, "Employee")) {
			frm.set_intro(__("Fill the form and save it"));
		} else if (
			frm.perm[0] &&
			frm.perm[0].submit &&
			!frm.is_dirty() &&
			!frm.is_new() &&
			!frappe.model.has_workflow(frm.doctype) &&
			frm.doc.docstatus === 0
		) {
			frm.set_intro(__("Submit this Leave Application to confirm."));
		}

		frm.trigger("set_employee");
		if (frm.doc.docstatus === 0) {
			frm.trigger("make_dashboard");
		}
		frm.trigger("set_form_buttons");
	},

	async set_employee(frm) {
		if (frm.doc.employee) return;

		const employee = await hrms.get_current_employee(frm);
		if (employee) {
			frm.set_value("employee", employee);
		}
	},

	employee: function (frm) {
		frm.trigger("make_dashboard");
		frm.trigger("get_leave_balance");
		frm.trigger("set_leave_approver");
	},

	leave_approver: function (frm) {
		if (frm.doc.leave_approver) {
			frm.set_value("leave_approver_name", frappe.user.full_name(frm.doc.leave_approver));
		}
	},

	leave_type: function (frm) {
		frm.trigger("get_leave_balance");
	},

	half_day: function (frm) {
		if (frm.doc.half_day) {
			if (frm.doc.from_date == frm.doc.to_date) {
				frm.set_value("half_day_date", frm.doc.from_date);
			} else {
				frm.trigger("half_day_datepicker");
			}
		} else {
			frm.set_value("half_day_date", "");
		}
		frm.trigger("calculate_total_days");
	},

	from_date: function (frm) {
		frm.events.validate_from_to_date(frm, "from_date");
		frm.trigger("make_dashboard");
		frm.trigger("half_day_datepicker");
		frm.trigger("calculate_total_days");
	},

	to_date: function (frm) {
		frm.events.validate_from_to_date(frm, "to_date");
		frm.trigger("make_dashboard");
		frm.trigger("half_day_datepicker");
		frm.trigger("calculate_total_days");
	},

	half_day_date(frm) {
		frm.trigger("calculate_total_days");
	},

	validate_from_to_date: function (frm, updated_field) {
		if (!frm.doc.from_date || !frm.doc.to_date) return;

		const from_date = Date.parse(frm.doc.from_date);
		const to_date = Date.parse(frm.doc.to_date);

		if (to_date < from_date) {
			const other_field = updated_field === "from_date" ? "to_date" : "from_date";

			frm.set_value(other_field, frm.doc[updated_field]);
			frappe.show_alert({
				message: __("Changing '{0}' to {1}.", [
					__(frm.fields_dict[other_field].df.label),
					frappe.datetime.str_to_user(frm.doc[updated_field]),
				]),
				indicator: "blue",
			});
		}
	},

	half_day_datepicker: function (frm) {
		frm.set_value("half_day_date", "");
		if (!(frm.doc.half_day && frm.doc.from_date && frm.doc.to_date)) return;

		const half_day_datepicker = frm.fields_dict.half_day_date.datepicker;
		half_day_datepicker.update({
			minDate: frappe.datetime.str_to_obj(frm.doc.from_date),
			maxDate: frappe.datetime.str_to_obj(frm.doc.to_date),
		});
	},

	get_leave_balance: function (frm) {
		if (
			frm.doc.docstatus === 0 &&
			frm.doc.employee &&
			frm.doc.leave_type &&
			frm.doc.from_date &&
			frm.doc.to_date
		) {
			return frappe.call({
				method: "hrms.hr.doctype.leave_application.leave_application.get_leave_balance_on",
				args: {
					employee: frm.doc.employee,
					date: frm.doc.from_date,
					to_date: frm.doc.to_date,
					leave_type: frm.doc.leave_type,
					consider_all_leaves_in_the_allocation_period: 1,
				},
				callback: function (r) {
					if (!r.exc && r.message) {
						frm.set_value("leave_balance", r.message);
					} else {
						frm.set_value("leave_balance", "0");
					}
				},
			});
		}
	},

	calculate_total_days: function (frm) {
		if (frm.doc.from_date && frm.doc.to_date && frm.doc.employee && frm.doc.leave_type) {
			// server call is done to include holidays in leave days calculations
			return frappe.call({
				method: "hrms.hr.doctype.leave_application.leave_application.get_number_of_leave_days",
				args: {
					employee: frm.doc.employee,
					leave_type: frm.doc.leave_type,
					from_date: frm.doc.from_date,
					to_date: frm.doc.to_date,
					half_day: frm.doc.half_day,
					half_day_date: frm.doc.half_day_date,
				},
				callback: function (r) {
					if (r && r.message) {
						frm.set_value("total_leave_days", r.message);
						frm.trigger("get_leave_balance");
					}
				},
			});
		}
	},

	set_leave_approver: function (frm) {
		if (frm.doc.employee) {
			return frappe.call({
				method: "hrms.hr.doctype.leave_application.leave_application.get_leave_approver",
				args: {
					employee: frm.doc.employee,
				},
				callback: function (r) {
					if (r && r.message) {
						frm.set_value("leave_approver", r.message);
					}
				},
			});
		}
	},

	set_form_buttons: async function (frm) {
		let self_approval_not_allowed = frm.doc.__onload
			? frm.doc.__onload.self_leave_approval_not_allowed
			: 0;
		let current_employee = await hrms.get_current_employee();
		if (
			frm.doc.docstatus === 0 &&
			!frm.is_dirty() &&
			!frappe.model.has_workflow(frm.doctype)
		) {
			if (self_approval_not_allowed && current_employee == frm.doc.employee) {
				frm.set_df_property("status", "read_only", 1);
				frm.trigger("show_save_button");
			}
		}
	},
	show_save_button: function (frm) {
		frm.page.set_primary_action("Save", () => {
			frm.save();
		});
		$(".form-message").prop("hidden", true);
	},
});

frappe.tour["Leave Application"] = [
	{
		fieldname: "employee",
		title: "Employee",
		description: __("Select the Employee."),
	},
	{
		fieldname: "leave_type",
		title: "Leave Type",
		description: __(
			"Select type of leave the employee wants to apply for, like Sick Leave, Privilege Leave, Casual Leave, etc.",
		),
	},
	{
		fieldname: "from_date",
		title: "From Date",
		description: __("Select the start date for your Leave Application."),
	},
	{
		fieldname: "to_date",
		title: "To Date",
		description: __("Select the end date for your Leave Application."),
	},
	{
		fieldname: "half_day",
		title: "Half Day",
		description: __("To apply for a Half Day check 'Half Day' and select the Half Day Date"),
	},
	{
		fieldname: "leave_approver",
		title: "Leave Approver",
		description: __(
			"Select your Leave Approver i.e. the person who approves or rejects your leaves.",
		),
	},
];

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
