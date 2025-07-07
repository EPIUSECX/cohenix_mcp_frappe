# Master Control Plan: `Quality Action`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Quality Management`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:QA-ACT-{#####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `corrective_preventive` | Corrective/Preventive | Select | Corrective
Preventive | ✅ |  |  | Corrective | None |
| `review` | Review | Link | Quality Review |  |  |  | None | None |
| `feedback` | Feedback | Link | Quality Feedback |  |  |  | None | None |
| `status` | Status | Select | Open
Completed |  |  | ✅ | Open | None |
| `cb_00` | None | Column Break | None |  |  |  | None | None |
| `date` | Date | Date | None |  |  | ✅ | Today | None |
| `goal` | Goal | Link | Quality Goal |  |  |  | None | None |
| `procedure` | Procedure | Link | Quality Procedure |  |  |  | None | None |
| `sb_00` | Resolution | Section Break | None |  |  |  | None | None |
| `resolutions` | Resolutions | Table | Quality Action Resolution |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/quality_management/doctype/quality_action/quality_action.js`
```javascript
// Copyright (c) 2018, Frappe and contributors
// For license information, please see license.txt

frappe.ui.form.on("Quality Action", {});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Review` | Query Report | Quality Management |



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
