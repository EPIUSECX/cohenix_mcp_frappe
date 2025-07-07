# Master Control Plan: `Job Offer`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-OFF-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `job_applicant` | Job Applicant | Link | Job Applicant | ✅ |  |  | None | None |
| `applicant_name` | Applicant Name | Data | None | ✅ |  | ✅ | None | None |
| `applicant_email` | Applicant Email Address | Data | Email |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | Awaiting Response
Accepted
Rejected |  |  |  | None | None |
| `offer_date` | Offer Date | Date | None | ✅ |  |  | None | None |
| `designation` | Designation | Link | Designation | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `job_offer_term_template` | Job Offer Term Template | Link | Job Offer Term Template |  |  |  | None | None |
| `offer_terms` | Job Offer Terms | Table | Job Offer Term |  |  |  | None | None |
| `section_break_14` | None | Section Break | None |  |  |  | None | None |
| `select_terms` | Select Terms and Conditions | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions | Text Editor | None |  |  |  | None | None |
| `printing_details` | Printing Details | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `amended_from` | Amended From | Link | Job Offer |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/job_offer/job_offer.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.job_offer");

frappe.ui.form.on("Job Offer", {
	onload: function (frm) {
		frm.set_query("select_terms", function () {
			return { filters: { hr: 1 } };
		});
	},

	setup: function (frm) {
		frm.email_field = "applicant_email";
	},

	select_terms: function (frm) {
		erpnext.utils.get_terms(frm.doc.select_terms, frm.doc, function (r) {
			if (!r.exc) {
				frm.set_value("terms", r.message);
			}
		});
	},
	job_offer_term_template: function (frm) {
		if (!frm.doc.job_offer_term_template) return;

		frappe.db
			.get_doc("Job Offer Term Template", frm.doc.job_offer_term_template)
			.then((doc) => {
				frm.clear_table("offer_terms");
				doc.offer_terms.forEach((term) => {
					frm.add_child("offer_terms", term);
				});
				refresh_field("offer_terms");
			});
	},

	refresh: function (frm) {
		if (
			!frm.doc.__islocal &&
			frm.doc.status == "Accepted" &&
			frm.doc.docstatus === 1 &&
			(!frm.doc.__onload || !frm.doc.__onload.employee)
		) {
			frm.add_custom_button(__("Create Employee"), function () {
				erpnext.job_offer.make_employee(frm);
			});
		}

		if (frm.doc.__onload && frm.doc.__onload.employee) {
			frm.add_custom_button(__("Show Employee"), function () {
				frappe.set_route("Form", "Employee", frm.doc.__onload.employee);
			});
		}
	},
});

erpnext.job_offer.make_employee = function (frm) {
	frappe.model.open_mapped_doc({
		method: "hrms.hr.doctype.job_offer.job_offer.make_employee",
		frm: frm,
	});
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
No linked reports found.


### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Job Offer Status` | Job Offer Status | Group By | HR |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Job Offers (This Month)` | Job Offers (This Month) | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
