# Master Control Plan: `Shift Location`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:location_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `location_name` | Location Name | Data | None | ✅ |  |  | None | None |
| `checkin_radius` | Checkin Radius | Int | None |  |  |  | None | Radius within which check-in is allowed (in meters) |
| `column_break_dlgd` | None | Column Break | None |  |  |  | None | None |
| `latitude` | Latitude | Float | None |  |  |  | None | None |
| `longitude` | Longitude | Float | None |  |  |  | None | None |
| `section_break_xxli` | None | Section Break | None |  |  |  | None | None |
| `fetch_geolocation` | Fetch Geolocation | Button | None |  |  |  | None | None |
| `geolocation` | Geolocation | Geolocation | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/shift_location/shift_location.js`
```javascript
// Copyright (c) 2024, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Shift Location", {
	refresh: async (frm) => {
		const allow_geolocation_tracking = await frappe.db.get_single_value(
			"HR Settings",
			"allow_geolocation_tracking",
		);

		if (!allow_geolocation_tracking)
			hide_field([
				"checkin_radius",
				"fetch_geolocation",
				"latitude",
				"longitude",
				"geolocation",
			]);

		if (!frm.doc.__islocal)
			hrms.add_shift_tools_button_to_form(frm, {
				action: "Assign Shift",
				shift_location: frm.doc.name,
			});
	},

	fetch_geolocation: (frm) => {
		hrms.fetch_geolocation(frm);
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
