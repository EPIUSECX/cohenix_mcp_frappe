# Master Control Plan: `Leave Allocation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | HR-LAL-.YYYY.- | ✅ |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `company` | Company | Link | Company | ✅ |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `leave_type` | Leave Type | Link | Leave Type | ✅ |  |  | None | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `to_date` | To Date | Date | None | ✅ |  |  | None | None |
| `section_break_6` | Allocation | Section Break | None |  |  |  | None | None |
| `new_leaves_allocated` | New Leaves Allocated | Float | None |  |  |  | None | None |
| `carry_forward` | Add unused leaves from previous allocations | Check | None |  |  |  | 0 | None |
| `unused_leaves` | Unused leaves | Float | None |  |  | ✅ | None | None |
| `total_leaves_allocated` | Total Leaves Allocated | Float | None | ✅ |  | ✅ | None | None |
| `total_leaves_encashed` | Total Leaves Encashed | Float | None |  |  | ✅ | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `compensatory_request` | Compensatory Leave Request | Link | Compensatory Leave Request |  |  | ✅ | None | None |
| `leave_period` | Leave Period | Link | Leave Period |  |  | ✅ | None | None |
| `leave_policy` | Leave Policy | Link | Leave Policy |  | ✅ | ✅ | None | None |
| `leave_policy_assignment` | Leave Policy Assignment | Link | Leave Policy Assignment |  |  | ✅ | None | None |
| `carry_forwarded_leaves_count` | Carry Forwarded Leaves | Float | None |  |  | ✅ | None | None |
| `expired` | Expired | Check | None |  | ✅ | ✅ | 0 | None |
| `amended_from` | Amended From | Link | Leave Allocation |  |  | ✅ | None | None |
| `notes` | Notes | Section Break | None |  |  |  | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 9
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_allocation/leave_allocation.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

// nosemgrep: frappe-semgrep-rules.rules.frappe-cur-frm-usage
cur_frm.add_fetch("employee", "employee_name", "employee_name");

frappe.ui.form.on("Leave Allocation", {
	onload: function (frm) {
		// Ignore cancellation of doctype on cancel all.
		frm.ignore_doctypes_on_cancel_all = ["Leave Ledger Entry"];

		if (!frm.doc.from_date) frm.set_value("from_date", frappe.datetime.get_today());

		frm.set_query("employee", function () {
			return {
				query: "erpnext.controllers.queries.employee_query",
			};
		});
		frm.set_query("leave_type", function () {
			return {
				filters: {
					is_lwp: 0,
				},
			};
		});
	},

	refresh: function (frm) {
		hrms.leave_utils.add_view_ledger_button(frm);

		if (frm.doc.docstatus === 1 && !frm.doc.expired) {
			var valid_expiry = moment(frappe.datetime.get_today()).isBetween(
				frm.doc.from_date,
				frm.doc.to_date,
			);
			if (valid_expiry) {
				// expire current allocation
				frm.add_custom_button(
					__("Expire Allocation"),
					function () {
						frappe.confirm("Are you sure you want to expire this allocation?", () => {
							frm.trigger("expire_allocation");
						});
					},
					__("Actions"),
				);
			}
		}

		if (!frm.doc.__islocal && frm.doc.leave_policy_assignment) {
			frappe.db.get_value("Leave Type", frm.doc.leave_type, "is_earned_leave", (r) => {
				if (!r?.is_earned_leave) return;
				frm.set_df_property("new_leaves_allocated", "read_only", 1);
				frm.trigger("add_allocate_leaves_button");
			});
		}
	},

	add_allocate_leaves_button: async function (frm) {
		const { message: monthly_earned_leave } = await frappe.call({
			method: "get_monthly_earned_leave",
			doc: frm.doc,
		});

		frm.add_custom_button(
			__("Allocate Leaves"),
			function () {
				const dialog = new frappe.ui.Dialog({
					title: "Manual Leave Allocation",
					fields: [
						{
							label: "New Leaves to be Allocated",
							fieldname: "new_leaves",
							fieldtype: "Float",
							reqd: 1,
						},
						{
							label: "From Date",
							fieldname: "from_date",
							fieldtype: "Date",
							default: frappe.datetime.get_today(),
						},
						{
							label: "To Date",
							fieldname: "to_date",
							fieldtype: "Date",
							read_only: 1,
							default: frm.doc.to_date,
						},
					],
					primary_action_label: "Allocate",
					primary_action({ new_leaves, from_date }) {
						frappe.call({
							method: "allocate_leaves_manually",
							doc: frm.doc,
							args: { new_leaves, from_date },
							callback: function (r) {
								if (!r.exc) {
									dialog.hide();
									frm.reload_doc();
								}
							},
						});
					},
				});
				dialog.fields_dict.new_leaves.set_value(monthly_earned_leave);
				dialog.fields_dict.from_date.datepicker?.update({
					minDate: frappe.datetime.str_to_obj(frm.doc.from_date),
					maxDate: frappe.datetime.str_to_obj(frm.doc.to_date),
				});

				dialog.show();
			},
			__("Actions"),
		);
	},

	expire_allocation: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.leave_ledger_entry.leave_ledger_entry.expire_allocation",
			args: {
				allocation: frm.doc,
				expiry_date: frappe.datetime.get_today(),
			},
			freeze: true,
			callback: function (r) {
				if (!r.exc) {
					frappe.msgprint(__("Allocation Expired!"));
				}
				frm.refresh();
			},
		});
	},

	employee: function (frm) {
		frm.trigger("calculate_total_leaves_allocated");
	},

	leave_type: function (frm) {
		frm.trigger("leave_policy");
		frm.trigger("calculate_total_leaves_allocated");
	},

	carry_forward: function (frm) {
		frm.trigger("calculate_total_leaves_allocated");
	},

	unused_leaves: function (frm) {
		frm.set_value(
			"total_leaves_allocated",
			flt(frm.doc.unused_leaves) + flt(frm.doc.new_leaves_allocated),
		);
	},

	new_leaves_allocated: function (frm) {
		frm.set_value(
			"total_leaves_allocated",
			flt(frm.doc.unused_leaves) + flt(frm.doc.new_leaves_allocated),
		);
	},

	leave_policy: function (frm) {
		if (frm.doc.leave_policy && frm.doc.leave_type) {
			frappe.db.get_value(
				"Leave Policy Detail",
				{
					parent: frm.doc.leave_policy,
					leave_type: frm.doc.leave_type,
				},
				"annual_allocation",
				(r) => {
					if (r && !r.exc)
						frm.set_value("new_leaves_allocated", flt(r.annual_allocation));
				},
				"Leave Policy",
			);
		}
	},

	calculate_total_leaves_allocated: function (frm) {
		if (cint(frm.doc.carry_forward) == 1 && frm.doc.leave_type && frm.doc.employee) {
			return frappe.call({
				method: "set_total_leaves_allocated",
				doc: frm.doc,
				callback: function () {
					frm.refresh_fields();
				},
			});
		} else if (cint(frm.doc.carry_forward) == 0) {
			frm.set_value("unused_leaves", 0);
			frm.set_value("total_leaves_allocated", flt(frm.doc.new_leaves_allocated));
		}
	},
});

frappe.tour["Leave Allocation"] = [
	{
		fieldname: "employee",
		title: "Employee",
		description: __("Select the Employee for which you want to allocate leaves."),
	},
	{
		fieldname: "leave_type",
		title: "Leave Type",
		description: __(
			"Select the Leave Type like Sick leave, Privilege Leave, Casual Leave, etc.",
		),
	},
	{
		fieldname: "from_date",
		title: "From Date",
		description: __("Select the date from which this Leave Allocation will be valid."),
	},
	{
		fieldname: "to_date",
		title: "To Date",
		description: __("Select the date after which this Leave Allocation will expire."),
	},
	{
		fieldname: "new_leaves_allocated",
		title: "New Leaves Allocated",
		description: __("Enter the number of leaves you want to allocate for the period."),
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
