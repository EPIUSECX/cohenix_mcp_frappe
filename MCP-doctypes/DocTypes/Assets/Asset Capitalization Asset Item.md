# Master Control Plan: `Asset Capitalization Asset Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `asset` | Asset | Link | Asset | ✅ |  |  | None | None |
| `asset_name` | Asset Name | Data | None |  |  | ✅ | None | None |
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `item_code` | Item Code | Link | Item | ✅ |  | ✅ | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `section_break_6` | Value | Section Break | None |  |  |  | None | None |
| `current_asset_value` | Current Asset Value | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `asset_value` | Asset Value | Currency | Company:company:default_currency |  |  | ✅ | 0 | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `fixed_asset_account` | Fixed Asset Account | Link | Account |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)




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
