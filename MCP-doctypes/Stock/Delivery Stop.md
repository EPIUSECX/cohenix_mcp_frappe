# Master Control Plan: `Delivery Stop`

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
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `address` | Address Name | Link | Address | ✅ |  |  | None | None |
| `locked` | Locked | Check | None |  |  |  | 0 | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `customer_address` | Customer Address | Small Text | None |  |  | ✅ | None | None |
| `visited` | Visited | Check | None |  |  |  | 0 | None |
| `order_information_section` | Order Information | Section Break | None |  |  |  | None | None |
| `delivery_note` | Delivery Note | Link | Delivery Note |  |  | ✅ | None | None |
| `cb_order` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | None |  |  | ✅ | None | None |
| `section_break_7` | Contact Information | Section Break | None |  |  |  | None | None |
| `contact` | Contact Name | Link | Contact |  |  |  | None | None |
| `email_sent_to` | Email sent to | Data | None |  |  | ✅ | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `customer_contact` | Customer Contact | Small Text | None |  |  | ✅ | None | None |
| `section_break_9` | Dispatch Information | Section Break | None |  |  |  | None | None |
| `distance` | Distance | Float | None |  |  | ✅ | None | None |
| `estimated_arrival` | Estimated Arrival | Datetime | None |  |  |  | None | None |
| `lat` | Latitude | Float | None |  | ✅ |  | None | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM |  |  | ✅ | None | None |
| `lng` | Longitude | Float | None |  | ✅ |  | None | None |
| `more_information_section` | More Information | Section Break | None |  |  |  | None | None |
| `details` | Details | Text Editor | None |  |  |  | None | None |


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
