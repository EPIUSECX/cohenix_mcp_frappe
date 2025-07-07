# Master Control Plan: `Activity Cost`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Projects`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `PROJ-ACC-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Projects User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `activity_type` | Activity Type | Link | Activity Type | ✅ |  |  | None | None |
| `employee` | Employee | Link | Employee |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `billing_rate` | Billing Rate | Currency | None |  |  |  | 0 | per hour |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `costing_rate` | Costing Rate | Currency | None |  |  |  | 0 | per hour |
| `title` | title | Data | None |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/activity_cost/activity_cost.js`
```javascript
cur_frm.add_fetch("employee", "employee_name", "employee_name");

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
