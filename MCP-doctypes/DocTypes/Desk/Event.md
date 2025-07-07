# Master Control Plan: `Event`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `EV.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Desk User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `details` | Details | Section Break | None |  |  |  | None | None |
| `subject` | Subject | Small Text | None | ✅ |  |  | None | None |
| `event_category` | Event Category | Select | Event
Meeting
Call
Sent/Received Email
Other |  |  |  | None | None |
| `event_type` | Event Type | Select | Private
Public | ✅ |  |  | None | None |
| `color` | Color | Color | None |  |  |  | None | None |
| `send_reminder` | Send an email reminder in the morning | Check | None |  |  |  | 1 | None |
| `repeat_this_event` | Repeat this Event | Check | None |  |  |  | 0 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `starts_on` | Starts on | Datetime | None | ✅ |  |  | None | None |
| `ends_on` | Ends on | Datetime | None |  |  |  | None | None |
| `status` | Status | Select | Open
Completed
Closed
Cancelled |  |  |  | Open | None |
| `sender` | Sender | Data | Email |  |  | ✅ | None | None |
| `all_day` | All Day | Check | None |  |  |  | 0 | None |
| `sync_with_google_calendar` | Sync with Google Calendar | Check | None |  |  |  | 0 | None |
| `add_video_conferencing` | Add Video Conferencing | Check | None |  |  |  | 0 | via Google Meet |
| `sb_00` | Google Calendar | Section Break | None |  |  |  | None | None |
| `google_calendar` | Google Calendar | Link | Google Calendar |  |  |  | None | None |
| `google_calendar_id` | Google Calendar ID | Data | None |  |  | ✅ | None | None |
| `cb_00` | None | Column Break | None |  |  |  | None | None |
| `google_calendar_event_id` | Google Calendar Event ID | Data | None |  |  | ✅ | None | None |
| `google_meet_link` | Google Meet Link | Small Text | None |  |  | ✅ | None | None |
| `pulled_from_google_calendar` | Pulled from Google Calendar | Check | None |  |  | ✅ | 0 | None |
| `section_break_13` | None | Section Break | None |  |  |  | None | None |
| `repeat_on` | Repeat On | Select | 
Daily
Weekly
Monthly
Quarterly
Half Yearly
Yearly |  |  |  | None | None |
| `repeat_till` | Repeat Till | Date | None |  |  |  | None | Leave blank to repeat always |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `monday` | Monday | Check | None |  |  |  | 0 | None |
| `tuesday` | Tuesday | Check | None |  |  |  | 0 | None |
| `wednesday` | Wednesday | Check | None |  |  |  | 0 | None |
| `thursday` | Thursday | Check | None |  |  |  | 0 | None |
| `friday` | Friday | Check | None |  |  |  | 0 | None |
| `saturday` | Saturday | Check | None |  |  |  | 0 | None |
| `sunday` | Sunday | Check | None |  |  |  | 0 | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `participants` | Participants | Section Break | None |  |  |  | None | None |
| `event_participants` | Event Participants | Table | Event Participants |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/event/event.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// MIT License. See license.txt
frappe.provide("frappe.desk");

frappe.ui.form.on("Event", {
	onload: function (frm) {
		frm.set_query("reference_doctype", "event_participants", function () {
			return {
				filters: {
					issingle: 0,
				},
			};
		});
		frm.set_query("google_calendar", function () {
			return {
				filters: {
					owner: frappe.session.user,
				},
			};
		});
	},
	refresh: function (frm) {
		if (frm.doc.event_participants) {
			frm.doc.event_participants.forEach((value) => {
				frm.add_custom_button(
					__(value.reference_docname),
					function () {
						frappe.set_route("Form", value.reference_doctype, value.reference_docname);
					},
					__("Participants")
				);
			});
		}

		frm.page.set_inner_btn_group_as_primary(__("Add Participants"));

		frm.add_custom_button(
			__("Add Contacts"),
			function () {
				new frappe.desk.eventParticipants(frm, "Contact");
			},
			__("Add Participants")
		);

		const [ends_on_date] = frm.doc.ends_on
			? frm.doc.ends_on.split(" ")
			: frm.doc.starts_on?.split(" ") || [];

		if (
			ends_on_date &&
			frm.doc.google_meet_link &&
			frappe.datetime.now_date() <= ends_on_date
		) {
			frm.dashboard.set_headline(
				__("Join video conference with {0}", [
					`<a target='_blank' href='${frm.doc.google_meet_link}'>Google Meet</a>`,
				])
			);
		}
	},
	repeat_on: function (frm) {
		if (frm.doc.repeat_on === "Every Day") {
			["monday", "tuesday", "wednesday", "thursday", "friday", "saturday", "sunday"].map(
				function (v) {
					frm.set_value(v, 1);
				}
			);
		}
	},
});

frappe.ui.form.on("Event Participants", {
	event_participants_remove: function (frm, cdt, cdn) {
		if (cdt && !cdn.includes("new-event-participants")) {
			frappe.call({
				type: "POST",
				method: "frappe.desk.doctype.event.event.delete_communication",
				args: {
					event: frm.doc,
					reference_doctype: cdt,
					reference_docname: cdn,
				},
				freeze: true,
				callback: function (r) {
					if (r.exc) {
						frappe.show_alert({
							message: __("{0}", [r.exc]),
							indicator: "orange",
						});
					}
				},
			});
		}
	},
});

frappe.desk.eventParticipants = class eventParticipants {
	constructor(frm, doctype) {
		this.frm = frm;
		this.doctype = doctype;
		this.make();
	}

	make() {
		let me = this;

		let table = me.frm.get_field("event_participants").grid;
		new frappe.ui.form.LinkSelector({
			doctype: me.doctype,
			dynamic_link_field: "reference_doctype",
			dynamic_link_reference: me.doctype,
			fieldname: "reference_docname",
			target: table,
			txt: "",
		});
	}
};

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
