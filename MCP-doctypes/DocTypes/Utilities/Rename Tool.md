# Master Control Plan: `Rename Tool`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Utilities`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `select_doctype` | Select DocType | Select | None |  |  |  | None | Type of document to rename. |
| `file_to_rename` | File to Rename | Attach | None |  |  |  | None | Attach .csv file with two columns, one for the old name and one for the new name |
| `rename_log` | Rename Log | HTML | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/utilities/doctype/rename_tool/rename_tool.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Rename Tool", {
	onload: function (frm) {
		return frappe.call({
			method: "erpnext.utilities.doctype.rename_tool.rename_tool.get_doctypes",
			callback: function (r) {
				frm.set_df_property("select_doctype", "options", r.message);
			},
		});
	},
	refresh: function (frm) {
		frm.disable_save();

		frm.get_field("file_to_rename").df.options = {
			restrictions: {
				allowed_file_types: [".csv"],
			},
		};

		frm.trigger("render_overview");

		frm.page.set_primary_action(__("Rename"), function () {
			frappe.call({
				method: "erpnext.utilities.doctype.rename_tool.rename_tool.upload",
				args: {
					select_doctype: frm.doc.select_doctype,
				},
				freeze: true,
				freeze_message: __("Scheduling..."),
				callback: function () {
					frappe.msgprint({
						message: __("Rename jobs for doctype {0} have been enqueued.", [
							frm.doc.select_doctype,
						]),
						alert: true,
						indicator: "green",
					});
					frm.set_value("select_doctype", "");
					frm.set_value("file_to_rename", "");

					frm.trigger("render_overview");
				},
				error: function (r) {
					frappe.msgprint({
						message: __("Rename jobs for doctype {0} have not been enqueued.", [
							frm.doc.select_doctype,
						]),
						alert: true,
						indicator: "red",
					});

					frm.trigger("render_overview");
				},
			});
		});
	},
	render_overview: function (frm) {
		frappe.db
			.get_list("RQ Job", { filters: { status: ["in", ["started", "queued", "finished", "failed"]] } })
			.then((jobs) => {
				let counts = {
					started: 0,
					queued: 0,
					finished: 0,
					failed: 0,
				};

				for (const job of jobs) {
					if (job.job_name !== "frappe.model.rename_doc.bulk_rename") {
						continue;
					}

					counts[job.status]++;
				}

				frm.get_field("rename_log").$wrapper.html(`
					<p><strong>${__("Bulk Rename Jobs")}</a></strong></p>
					<p><a href="/app/rq-job?queue=long&status=queued">${__("Queued")}: ${counts.queued}</a></p>
					<p><a href="/app/rq-job?queue=long&status=started">${__("Started")}: ${counts.started}</a></p>
					<p><a href="/app/rq-job?queue=long&status=finished">${__("Finished")}: ${counts.finished}</a></p>
					<p><a href="/app/rq-job?queue=long&status=failed">${__("Failed")}: ${counts.failed}</a></p>
				`);
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
