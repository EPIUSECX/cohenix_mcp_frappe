# Master Control Plan: `Holiday List`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:holiday_list_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `holiday_list_name` | Holiday List Name | Data | None | ✅ |  |  | None | None |
| `from_date` | From Date | Date | None | ✅ |  |  | None | None |
| `to_date` | To Date | Date | None | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `total_holidays` | Total Holidays | Int | None |  |  | ✅ | None | None |
| `add_weekly_holidays` | Add Weekly Holidays | Section Break | None |  |  |  | None | None |
| `weekly_off` | Weekly Off | Select | 
Sunday
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday |  |  |  | None | None |
| `get_weekly_off_dates` | Add to Holidays | Button | get_weekly_off_dates |  |  |  | None | None |
| `add_local_holidays` | Add Local Holidays | Section Break | None |  |  |  | None | None |
| `country` | Country | Autocomplete | None |  |  |  | None | None |
| `subdivision` | Subdivision | Autocomplete | None |  |  |  | None | None |
| `get_local_holidays` | Add to Holidays | Button | get_local_holidays |  |  |  | None | None |
| `holidays_section` | Holidays | Section Break | None |  |  |  | None | None |
| `holidays` | Holidays | Table | Holiday |  |  |  | None | None |
| `clear_table` | Clear Table | Button | clear_table |  |  |  | None | None |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `color` | Color | Color | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/holiday_list/holiday_list.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Holiday List", {
	refresh: function (frm) {
		if (frm.doc.holidays) {
			frm.set_value("total_holidays", frm.doc.holidays.length);
		}

		frm.call("get_supported_countries").then((r) => {
			frm.subdivisions_by_country = r.message.subdivisions_by_country;
			frm.fields_dict.country.set_data(
				r.message.countries.sort((a, b) => a.label.localeCompare(b.label))
			);

			if (frm.doc.country) {
				frm.trigger("set_subdivisions");
			}
		});
	},
	from_date: function (frm) {
		if (frm.doc.from_date && !frm.doc.to_date) {
			var a_year_from_start = frappe.datetime.add_months(frm.doc.from_date, 12);
			frm.set_value("to_date", frappe.datetime.add_days(a_year_from_start, -1));
		}
	},
	country: function (frm) {
		frm.set_value("subdivision", "");

		if (frm.doc.country) {
			frm.trigger("set_subdivisions");
		}
	},
	set_subdivisions: function (frm) {
		const subdivisions = [...frm.subdivisions_by_country[frm.doc.country]];
		if (subdivisions && subdivisions.length > 0) {
			frm.fields_dict.subdivision.set_data(subdivisions);
			frm.set_df_property("subdivision", "hidden", 0);
		} else {
			frm.fields_dict.subdivision.set_data([]);
			frm.set_df_property("subdivision", "hidden", 1);
		}
	},
});

frappe.tour["Holiday List"] = [
	{
		fieldname: "holiday_list_name",
		title: "Holiday List Name",
		description: __("Enter a name for this Holiday List."),
	},
	{
		fieldname: "from_date",
		title: "From Date",
		description: __("Based on your HR Policy, select your leave allocation period's start date"),
	},
	{
		fieldname: "to_date",
		title: "To Date",
		description: __("Based on your HR Policy, select your leave allocation period's end date"),
	},
	{
		fieldname: "weekly_off",
		title: "Weekly Off",
		description: __("Select your weekly off day"),
	},
	{
		fieldname: "get_weekly_off_dates",
		title: "Add Holidays",
		description: __(
			"Click on Add to Holidays. This will populate the holidays table with all the dates that fall on the selected weekly off. Repeat the process for populating the dates for all your weekly holidays"
		),
	},
	{
		fieldname: "holidays",
		title: "Holidays",
		description: __(
			"Here, your weekly offs are pre-populated based on the previous selections. You can add more rows to also add public and national holidays individually."
		),
	},
];

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
