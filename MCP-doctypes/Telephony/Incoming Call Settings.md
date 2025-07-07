# Master Control Plan: `Incoming Call Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Telephony`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `call_routing` | Call Routing | Select | Sequential
Simultaneous |  |  |  | Sequential | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `greeting_message` | Greeting Message | Data | None |  |  |  | None | None |
| `agent_busy_message` | Agent Busy Message | Data | None |  |  |  | None | None |
| `agent_unavailable_message` | Agent Unavailable Message | Data | None |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `call_handling_schedule` | Call Handling Schedule | Table | Incoming Call Handling Schedule | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/telephony/doctype/incoming_call_settings/incoming_call_settings.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

function time_to_seconds(time_str) {
	// Convert time string of format HH:MM:SS into seconds.
	let seq = time_str.split(":");
	seq = seq.map((n) => parseInt(n));
	return seq[0] * 60 * 60 + seq[1] * 60 + seq[2];
}

function number_sort(array, ascending = true) {
	let array_copy = [...array];
	if (ascending) {
		array_copy.sort((a, b) => a - b); // ascending order
	} else {
		array_copy.sort((a, b) => b - a); // descending order
	}
	return array_copy;
}

function groupby(items, key) {
	// Group the list of items using the given key.
	const obj = {};
	items.forEach((item) => {
		if (item[key] in obj) {
			obj[item[key]].push(item);
		} else {
			obj[item[key]] = [item];
		}
	});
	return obj;
}

function check_timeslot_overlap(ts1, ts2) {
	/// Timeslot is a an array of length 2 ex: [from_time, to_time]
	/// time in timeslot is an integer represents number of seconds.
	if ((ts1[0] < ts2[0] && ts1[1] <= ts2[0]) || (ts1[0] >= ts2[1] && ts1[1] > ts2[1])) {
		return false;
	}
	return true;
}

function validate_call_schedule(schedule) {
	validate_call_schedule_timeslot(schedule);
	validate_call_schedule_overlaps(schedule);
}

function validate_call_schedule_timeslot(schedule) {
	// Make sure that to time slot is ahead of from time slot.
	let errors = [];

	for (let row in schedule) {
		let record = schedule[row];
		let from_time_in_secs = time_to_seconds(record.from_time);
		let to_time_in_secs = time_to_seconds(record.to_time);
		if (from_time_in_secs >= to_time_in_secs) {
			errors.push(
				__("Call Schedule Row {0}: To time slot should always be ahead of From time slot.", [row])
			);
		}
	}

	if (errors.length > 0) {
		frappe.throw(errors.join("<br/>"));
	}
}

function is_call_schedule_overlapped(day_schedule) {
	// Check if any time slots are overlapped in a day schedule.
	let timeslots = [];
	day_schedule.forEach((record) => {
		timeslots.push([time_to_seconds(record.from_time), time_to_seconds(record.to_time)]);
	});

	if (timeslots.length < 2) {
		return false;
	}

	timeslots = number_sort(timeslots);

	// Sorted timeslots will be in ascending order if not overlapped.
	for (let i = 1; i < timeslots.length; i++) {
		if (check_timeslot_overlap(timeslots[i - 1], timeslots[i])) {
			return true;
		}
	}
	return false;
}

function validate_call_schedule_overlaps(schedule) {
	let group_by_day = groupby(schedule, "day_of_week");
	for (const [day, day_schedule] of Object.entries(group_by_day)) {
		if (is_call_schedule_overlapped(day_schedule)) {
			frappe.throw(__("Please fix overlapping time slots for {0}", [day]));
		}
	}
}

frappe.ui.form.on("Incoming Call Settings", {
	validate(frm) {
		validate_call_schedule(frm.doc.call_handling_schedule);
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
