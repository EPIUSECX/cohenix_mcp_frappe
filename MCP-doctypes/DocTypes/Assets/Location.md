# Master Control Plan: `Location`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:location_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `location_name` | Location Name | Data | None | ✅ |  |  | None | None |
| `parent_location` | Parent Location | Link | Location |  |  |  | None | None |
| `cb_details` | None | Column Break | None |  |  |  | None | None |
| `is_container` | Is Container | Check | None |  |  |  | 0 | Check if it is a hydroponic unit |
| `is_group` | Is Group | Check | None |  |  |  | 0 | None |
| `sb_location_details` | Location Details | Section Break | None |  |  |  | None | None |
| `latitude` | Latitude | Float | None |  |  |  | None | None |
| `longitude` | Longitude | Float | None |  |  |  | None | None |
| `cb_latlong` | None | Column Break | None |  |  |  | None | None |
| `area` | Area | Float | None |  |  | ✅ | None | None |
| `area_uom` | Area UOM | Link | UOM |  |  |  | None | None |
| `sb_geolocation` | None | Section Break | None |  |  |  | None | None |
| `location` | Location | Geolocation | None |  |  |  | None | None |
| `tree_details` | Tree Details | Section Break | None |  | ✅ |  | None | None |
| `lft` | lft | Int | None |  | ✅ | ✅ | None | None |
| `rgt` | rgt | Int | None |  | ✅ | ✅ | None | None |
| `old_parent` | Old Parent | Data | None |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/location/location.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Location", {
	setup: function (frm) {
		frm.set_query("parent_location", function () {
			return {
				filters: {
					is_group: 1,
				},
			};
		});
	},

	onload_post_render(frm) {
		if (!frm.doc.location && frm.doc.latitude && frm.doc.longitude) {
			frm.fields_dict.location.map.setView([frm.doc.latitude, frm.doc.longitude], 13);
		} else {
			frm.doc.latitude = frm.fields_dict.location.map.getCenter()["lat"];
			frm.doc.longitude = frm.fields_dict.location.map.getCenter()["lng"];
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
