# Master Control Plan: `Lower Deduction Certificate`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Regional`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:certificate_no`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `certificate_details_section` | Certificate Details | Section Break | None |  |  |  | None | None |
| `tax_withholding_category` | Tax Withholding Category | Link | Tax Withholding Category | ✅ |  |  | None | None |
| `fiscal_year` | Fiscal Year | Link | Fiscal Year | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `certificate_no` | Certificate No | Data | None | ✅ |  |  | None | None |
| `section_break_3` | Deductee Details | Section Break | None |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier | ✅ |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `pan_no` | PAN No | Data | None | ✅ |  |  | None | None |
| `validity_details_section` | Validity Details | Section Break | None |  |  |  | None | None |
| `valid_from` | Valid From | Date | None | ✅ |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `valid_upto` | Valid Up To | Date | None | ✅ |  |  | None | None |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate Of TDS As Per Certificate | Percent | None | ✅ |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `certificate_limit` | Certificate Limit | Currency | None | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/regional/doctype/lower_deduction_certificate/lower_deduction_certificate.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Lower Deduction Certificate", {
	// refresh: function(frm) {
	// }
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
