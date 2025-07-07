# Master Control Plan: `Transaction Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `row_index` | Row Index | Data | None |  |  | ✅ | None | None |
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `reference_doctype` | Reference Document Type | Data | None |  |  | ✅ | None | None |
| `document_name` | Document Name | Data | None |  |  | ✅ | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `timestamp` | Timestamp | Datetime | None |  |  | ✅ | None | None |
| `checksum_version` | Checksum Version | Data | None |  |  | ✅ | None | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `previous_hash` | Previous Hash | Small Text | None |  | ✅ | ✅ | None | None |
| `transaction_hash` | Transaction Hash | Small Text | None |  |  | ✅ | None | None |
| `chaining_hash` | Chaining Hash | Small Text | None |  | ✅ | ✅ | None | None |
| `data` | Data | Long Text | None |  | ✅ | ✅ | None | None |
| `amended_from` | Amended From | Link | Transaction Log |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/transaction_log/transaction_log.js`
```javascript
// Copyright (c) 2018, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Transaction Log", {});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Transaction Log Report` | Script Report | Core |



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
