# Master Control Plan: `Loyalty Point Entry`

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
| Auditor | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `loyalty_program` | Loyalty Program | Link | Loyalty Program | ✅ |  |  | None | None |
| `loyalty_program_tier` | Loyalty Program Tier | Data | None |  |  |  | None | None |
| `customer` | Customer | Link | Customer | ✅ |  |  | None | None |
| `invoice_type` | Invoice Type | Link | DocType | ✅ |  |  | None | None |
| `invoice` | Invoice | Dynamic Link | invoice_type |  |  |  | None | None |
| `redeem_against` | Redeem Against | Link | Loyalty Point Entry |  |  |  | None | None |
| `loyalty_points` | Loyalty Points | Int | None | ✅ |  |  | None | None |
| `purchase_amount` | Purchase Amount | Currency | None |  |  |  | None | None |
| `expiry_date` | Expiry Date | Date | None | ✅ |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `discretionary_reason` | Discretionary Reason | Data | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/loyalty_point_entry/loyalty_point_entry.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Loyalty Point Entry", {
	refresh: function (frm) {},
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
