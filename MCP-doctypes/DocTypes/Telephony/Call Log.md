# Master Control Plan: `Call Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Telephony`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:id`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `call_details_section` | Call Details | Section Break | None |  |  |  | None | None |
| `id` | ID | Data | None |  |  | ✅ | None | None |
| `from` | From | Data | None |  |  | ✅ | None | None |
| `to` | To | Data | None |  |  | ✅ | None | None |
| `call_received_by` | Call Received By | Link | Employee |  |  | ✅ | None | None |
| `employee_user_id` | Employee User Id | Link | User |  | ✅ |  | None | None |
| `medium` | Medium | Data | None |  |  | ✅ | None | None |
| `start_time` | Start Time | Datetime | None |  |  | ✅ | None | None |
| `end_time` | End Time | Datetime | None |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `type` | Type | Select | Incoming
Outgoing |  |  | ✅ | None | None |
| `customer` | Customer | Link | Customer |  |  | ✅ | None | None |
| `status` | Status | Select | Ringing
In Progress
Completed
Failed
Busy
No Answer
Queued
Canceled |  |  | ✅ | None | None |
| `duration` | Duration | Duration | None |  |  | ✅ | None | Call Duration in seconds |
| `recording_url` | Recording URL | Data | None |  | ✅ |  | None | None |
| `recording_html` | Recording HTML | HTML | None |  |  |  | None | None |
| `section_break_11` | Call Summary | Section Break | None |  |  |  | None | None |
| `type_of_call` | Type Of Call | Link | Telephony Call Type |  |  |  | None | None |
| `summary` | Summary | Small Text | None |  |  |  | None | None |
| `section_break_19` | Reference | Section Break | None |  |  |  | None | None |
| `links` | Links | Table | Dynamic Link |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/telephony/doctype/call_log/call_log.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Call Log", {
	refresh: function (frm) {
		frm.events.setup_recording_audio_control(frm);
		const incoming_call = frm.doc.type == "Incoming";
		frm.add_custom_button(incoming_call ? __("Callback") : __("Call Again"), () => {
			const number = incoming_call ? frm.doc.from : frm.doc.to;
			frappe.phone_call.handler(number, frm);
		});
	},
	setup_recording_audio_control(frm) {
		const recording_wrapper = frm.get_field("recording_html").$wrapper;
		if (!frm.doc.recording_url || frm.doc.recording_url == "null") {
			recording_wrapper.empty();
		} else {
			recording_wrapper.addClass("input-max-width");
			recording_wrapper.html(`
				<audio
					controls
					src="${frm.doc.recording_url}">
				</audio>
			`);
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
