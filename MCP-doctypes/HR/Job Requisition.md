# Master Control Plan: `Job Requisition`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Naming Series | Select | HR-HIREQ- |  |  |  | None | None |
| `designation` | Designation | Link | Designation | ✅ |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `column_break_qkna` | None | Column Break | None |  |  |  | None | None |
| `no_of_positions` | No of. Positions | Int | None | ✅ |  |  | None | None |
| `expected_compensation` | Expected Compensation | Currency | Company:company:default_currency | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `status` | Status | Select | Pending
Open & Approved
Rejected
Filled
On Hold
Cancelled | ✅ |  |  | None | None |
| `section_break_7` | Requested By | Section Break | None |  |  |  | None | None |
| `requested_by` | Requested By | Link | Employee | ✅ |  |  | None | None |
| `requested_by_name` | Requested By (Name) | Data | None |  |  | ✅ | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `requested_by_dept` | Department | Link | Department |  |  | ✅ | None | None |
| `requested_by_designation` | Designation | Link | Designation |  |  | ✅ | None | None |
| `timelines_tab` | Timelines | Section Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `completed_on` | Completed On | Date | None |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `expected_by` | Expected By | Date | None |  |  |  | None | None |
| `time_to_fill` | Time to Fill | Duration | None |  |  | ✅ | None | Time taken to fill the open positions |
| `job_description_tab` | Job Description | Tab Break | None |  |  |  | None | None |
| `description` | Job Description | Text Editor | None | ✅ |  |  | None | None |
| `reason_for_requesting` | Reason for Requesting | Text | None |  |  |  | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/job_requisition/job_requisition.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Job Requisition", {
	refresh: function (frm) {
		if (!frm.doc.__islocal && !["Filled", "On Hold", "Cancelled"].includes(frm.doc.status)) {
			frappe.db
				.get_list("Employee Referral", {
					filters: { for_designation: frm.doc.designation, status: "Pending" },
				})
				.then((data) => {
					if (data && data.length) {
						const link =
							data.length > 1
								? `<a id="referral_links" style="text-decoration: underline;">${__(
										"Employee Referrals",
								  )}</a>`
								: `<a id="referral_links" style="text-decoration: underline;">${__(
										"Employee Referral",
								  )}</a>`;

						const headline = __("{} {} open for this position.", [data.length, link]);
						frm.dashboard.clear_headline();
						frm.dashboard.set_headline(headline, "yellow");

						$("#referral_links").on("click", (e) => {
							e.preventDefault();
							frappe.set_route("List", "Employee Referral", {
								for_designation: frm.doc.designation,
								status: "Pending",
							});
						});
					}
				});
		}

		if (frm.doc.status === "Open & Approved") {
			frm.add_custom_button(
				__("Create Job Opening"),
				() => {
					frappe.model.open_mapped_doc({
						method: "hrms.hr.doctype.job_requisition.job_requisition.make_job_opening",
						frm: frm,
					});
				},
				__("Actions"),
			);

			frm.add_custom_button(
				__("Associate Job Opening"),
				() => {
					frappe.prompt(
						{
							label: __("Job Opening"),
							fieldname: "job_opening",
							fieldtype: "Link",
							options: "Job Opening",
							reqd: 1,
							get_query: () => {
								const filters = {
									company: frm.doc.company,
									status: "Open",
									designation: frm.doc.designation,
								};

								if (frm.doc.department) filters.department = frm.doc.department;

								return { filters: filters };
							},
						},
						(values) => {
							frm.call("associate_job_opening", { job_opening: values.job_opening });
						},
						__("Associate Job Opening"),
						__("Submit"),
					);
				},
				__("Actions"),
			);

			frm.page.set_inner_btn_group_as_primary(__("Actions"));
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
