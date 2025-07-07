# Master Control Plan: `Appointment`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:APMT-{customer_name}-{####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `scheduled_time` | Scheduled Time | Datetime | None | ✅ |  |  | None | None |
| `status` | Status | Select | Open
Unverified
Closed | ✅ |  |  | None | None |
| `customer_details_section` | Customer Details | Section Break | None |  |  |  | None | None |
| `customer_name` | Name | Data | None | ✅ |  |  | None | None |
| `customer_phone_number` | Phone Number | Data | None |  |  |  | None | None |
| `customer_skype` | Skype ID | Data | None |  |  |  | None | None |
| `customer_email` | Email | Data | None | ✅ |  |  | None | None |
| `col_br_2` | None | Column Break | None |  |  |  | None | None |
| `customer_details` | Details | Long Text | None |  |  |  | None | None |
| `linked_docs_section` | Linked Documents | Section Break | None |  |  |  | None | None |
| `appointment_with` | Appointment With | Link | DocType |  |  |  | None | None |
| `party` | Party | Dynamic Link | appointment_with |  |  |  | None | None |
| `col_br_3` | None | Column Break | None |  |  |  | None | None |
| `calendar_event` | Calendar Event | Link | Event |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/appointment/appointment.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Appointment", {
	refresh: function (frm) {
		if (frm.doc.lead) {
			frm.add_custom_button(frm.doc.lead, () => {
				frappe.set_route("Form", "Lead", frm.doc.lead);
			});
		}
		if (frm.doc.calendar_event) {
			frm.add_custom_button(__(frm.doc.calendar_event), () => {
				frappe.set_route("Form", "Event", frm.doc.calendar_event);
			});
		}
	},
	onload: function (frm) {
		frm.set_query("appointment_with", function () {
			return {
				filters: {
					name: ["in", ["Customer", "Lead"]],
				},
			};
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
