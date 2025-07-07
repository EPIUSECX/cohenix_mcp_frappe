# Master Control Plan: `Dunning Type`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `dunning_type` | Dunning Type | Data | None | ✅ |  |  | None | None |
| `is_default` | Is Default | Check | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `dunning_fee` | Dunning Fee | Currency | None |  |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `rate_of_interest` | Rate of Interest (%) Yearly | Float | None |  |  |  | None | None |
| `text_block_section` | Dunning Letter | Section Break | None |  |  |  | None | This section allows the user to set the Body and Closing text of the Dunning Letter for the Dunning Type based on language, which can be used in Print. |
| `dunning_letter_text` | None | Table | Dunning Letter Text |  |  |  | None | None |
| `section_break_9` | Accounting Details | Section Break | None |  |  |  | None | None |
| `income_account` | Income Account | Link | Account |  |  |  | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/dunning_type/dunning_type.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Dunning Type", {
	setup: function (frm) {
		frm.set_query("income_account", () => {
			return {
				filters: {
					root_type: "Income",
					is_group: 0,
					company: frm.doc.company,
				},
			};
		});
		frm.set_query("cost_center", () => {
			return {
				filters: {
					is_group: 0,
					company: frm.doc.company,
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
