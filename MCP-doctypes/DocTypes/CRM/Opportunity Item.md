# Master Control Plan: `Opportunity Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
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
| `item_code` | Item Code | Link | Item |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM |  |  |  | None | None |
| `qty` | Qty | Float | None |  |  |  | 1 | None |
| `section_break_6` | Description | Section Break | None |  |  |  | None | None |
| `brand` | Brand | Link | Brand |  | ✅ |  | None | None |
| `item_group` | Item Group | Link | Item Group |  | ✅ |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_and_rate_section` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `base_rate` | Rate (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency | ✅ |  |  | None | None |
| `amount` | Amount | Currency | currency | ✅ |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
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
