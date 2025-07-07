# Master Control Plan: `Fiscal Year`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:year`
- **Description:** Represents a Financial Year. All accounting entries and other major transactions are tracked against the Fiscal Year.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Stock Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Auditor | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `year` | Year Name | Data | None | ✅ |  |  | None | For e.g. 2012, 2012-13 |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `is_short_year` | Is Short/Long Year | Check | None |  |  |  | 0 | More/Less than 12 months. |
| `year_start_date` | Year Start Date | Date | None | ✅ |  |  | None | None |
| `year_end_date` | Year End Date | Date | None | ✅ |  |  | None | None |
| `companies` | Companies | Table | Fiscal Year Company |  |  |  | None | None |
| `auto_created` | Auto Created | Check | None |  | ✅ | ✅ | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/fiscal_year/fiscal_year.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Fiscal Year", {
	onload: function (frm) {
		if (frm.doc.__islocal) {
			frm.set_value("year_start_date", frappe.datetime.year_start());
		}
	},
	year_start_date: function (frm) {
		if (!frm.doc.is_short_year) {
			let year_end_date = frappe.datetime.add_days(
				frappe.datetime.add_months(frm.doc.year_start_date, 12),
				-1
			);
			frm.set_value("year_end_date", year_end_date);
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
| Name | Event | Channel | Subject |
|---|---|---|---|
| `Notification for new fiscal year` | New | Email | Notification for new fiscal year {{ doc.name }} |



### Webhooks
No enabled webhooks found.
