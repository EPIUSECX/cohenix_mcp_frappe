# Master Control Plan: `Upload Attendance`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `download_template` | Download Template | Section Break | None |  |  |  | None | None |
| `att_fr_date` | Attendance From Date | Date | None | ✅ |  |  | None | None |
| `att_to_date` | Attendance To Date | Date | None | ✅ |  |  | None | None |
| `get_template` | Get Template | Button | None |  |  |  | None | None |
| `upload_attendance_data` | Import Attendance | Section Break | None |  |  |  | None | None |
| `upload_html` | Upload HTML | HTML | None |  |  |  | None | None |
| `import_log` | Import Log | HTML | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/upload_attendance/upload_attendance.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("hrms.hr");

hrms.hr.AttendanceControlPanel = class AttendanceControlPanel extends frappe.ui.form.Controller {
	onload() {
		this.frm.set_value("att_fr_date", frappe.datetime.get_today());
		this.frm.set_value("att_to_date", frappe.datetime.get_today());
	}

	refresh() {
		this.frm.disable_save();
		this.show_upload();
		this.setup_import_progress();
	}

	get_template() {
		if (!this.frm.doc.att_fr_date || !this.frm.doc.att_to_date) {
			frappe.msgprint(__("Attendance From Date and Attendance To Date is mandatory"));
			return;
		}
		window.location.href = repl(
			frappe.request.url + "?cmd=%(cmd)s&from_date=%(from_date)s&to_date=%(to_date)s",
			{
				cmd: "hrms.hr.doctype.upload_attendance.upload_attendance.get_template",
				from_date: this.frm.doc.att_fr_date,
				to_date: this.frm.doc.att_to_date,
			},
		);
	}

	show_upload() {
		let $wrapper = $(this.frm.fields_dict.upload_html.wrapper).empty();
		new frappe.ui.FileUploader({
			wrapper: $wrapper,
			method: "hrms.hr.doctype.upload_attendance.upload_attendance.upload",
		});
		$wrapper.addClass("pb-5");
	}

	setup_import_progress() {
		var $log_wrapper = $(this.frm.fields_dict.import_log.wrapper).empty();

		frappe.realtime.on("import_attendance", (data) => {
			if (data.progress) {
				this.frm.dashboard.show_progress(
					"Import Attendance",
					(data.progress / data.total) * 100,
					__("Importing {0} of {1}", [data.progress, data.total]),
				);
				if (data.progress === data.total) {
					this.frm.dashboard.hide_progress("Import Attendance");
				}
			} else if (data.error) {
				this.frm.dashboard.hide();
				let messages = [`<th>${__("Error in some rows")}</th>`]
					.concat(
						data.messages
							.filter((message) => message.includes("Error"))
							.map((message) => `<tr><td>${message}</td></tr>`),
					)
					.join("");
				$log_wrapper.append('<table class="table table-bordered">' + messages);
			} else if (data.messages) {
				this.frm.dashboard.hide();
				let messages = [`<th>${__("Import Successful")}</th>`]
					.concat(data.messages.map((message) => `<tr><td>${message}</td></tr>`))
					.join("");
				$log_wrapper.append('<table class="table table-bordered">' + messages);
			}
		});
	}
};

// nosemgrep: frappe-semgrep-rules.rules.frappe-cur-frm-usage
cur_frm.cscript = new hrms.hr.AttendanceControlPanel({ frm: cur_frm });

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
