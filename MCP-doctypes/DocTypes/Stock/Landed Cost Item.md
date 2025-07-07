# Master Control Plan: `Landed Cost Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
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
| `item_code` | Item Code | Link | Item | ✅ |  | ✅ | None | None |
| `description` | Description | Text Editor | None | ✅ |  | ✅ | None | None |
| `receipt_document_type` | Receipt Document Type | Select | Purchase Invoice
Purchase Receipt
Stock Entry
Subcontracting Receipt |  |  | ✅ | None | None |
| `receipt_document` | Receipt Document | Dynamic Link | receipt_document_type |  |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `qty` | Qty | Float | None |  |  | ✅ | None | None |
| `rate` | Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `amount` | Amount | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `is_fixed_asset` | Is Fixed Asset | Check | None |  | ✅ | ✅ | 0 | None |
| `applicable_charges` | Applicable Charges | Currency | Company:company:default_currency |  |  |  | None | None |
| `purchase_receipt_item` | Purchase Receipt Item | Data | None |  | ✅ | ✅ | None | None |
| `stock_entry_item` | Stock Entry Item | Data | None |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 1
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
