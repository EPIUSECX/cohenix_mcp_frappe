# Master Control Plan: `Appointment Booking Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enable_scheduling` | Enable Appointment Scheduling | Check | None | ✅ |  |  | 0 | None |
| `agent_detail_section` | Agent Details | Section Break | None |  |  |  | None | None |
| `availability_of_slots` | Availability Of Slots | Table | Appointment Booking Slots | ✅ |  |  | None | None |
| `number_of_agents` | Number of Concurrent Appointments | Int | None | ✅ | ✅ | ✅ | 1 | None |
| `agent_list` | Agents | Table MultiSelect | Assignment Rule User | ✅ |  |  | None | None |
| `holiday_list` | Holiday List | Link | Holiday List | ✅ |  |  | None | None |
| `appointment_details_section` | Appointment Details | Section Break | None |  |  |  | None | None |
| `appointment_duration` | Appointment Duration (In Minutes) | Int | None | ✅ |  |  | 60 | None |
| `email_reminders` | Notify Via Email | Check | None |  |  |  | 0 | Notify customer and agent via email on the day of the appointment. |
| `advance_booking_days` | Number of days appointments can be booked in advance | Int | None | ✅ |  |  | 7 | None |
| `success_details` | Success Settings | Section Break | None |  |  |  | None | None |
| `success_redirect_url` | Success Redirect URL | Data | None |  |  |  | None | Leave blank for home.
This is relative to site URL, for example "about" will redirect to "https://yoursitename.com/about" |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/appointment_booking_settings/appointment_booking_settings.js`
```javascript
frappe.ui.form.on("Appointment Booking Settings", "validate", check_times);
function check_times(frm) {
	$.each(frm.doc.availability_of_slots || [], function (i, d) {
		let from_time = Date.parse("01/01/2019 " + d.from_time);
		let to_time = Date.parse("01/01/2019 " + d.to_time);
		if (from_time > to_time) {
			frappe.throw(
				__('In row {0} of Appointment Booking Slots: "To Time" must be later than "From Time".', [
					i + 1,
				])
			);
		}
	});
}

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
