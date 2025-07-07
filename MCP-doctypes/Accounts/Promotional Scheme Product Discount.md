# Master Control Plan: `Promotional Scheme Product Discount`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
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
| `disable` | Disable | Check | None |  |  |  | 0 | None |
| `apply_multiple_pricing_rules` | Apply Multiple Pricing Rules | Check | None |  |  |  | 0 | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `rule_description` | Rule Description | Small Text | None | ✅ |  |  | None | None |
| `section_break_1` | None | Section Break | None |  |  |  | None | None |
| `min_qty` | Min Qty | Float | None |  |  |  | 0 | None |
| `max_qty` | Max Qty | Float | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `min_amount` | Min Amount | Currency | None |  |  |  | 0 | None |
| `max_amount` | Max Amount | Currency | None |  |  |  | 0 | None |
| `section_break_6` | Free Item | Section Break | None |  |  |  | None | None |
| `same_item` | Same Item | Check | None |  |  |  | 0 | None |
| `free_item` | Item Code | Link | Item |  |  |  | None | None |
| `free_qty` | Qty | Float | None |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `free_item_uom` | UOM | Link | UOM |  |  |  | None | None |
| `free_item_rate` | Rate | Currency | None |  |  |  | None | None |
| `round_free_qty` | Round Free Qty | Check | None |  |  |  | 0 | None |
| `section_break_12` | None | Section Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  |  | None | None |
| `threshold_percentage` | Threshold for Suggestion | Percent | None |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `priority` | Priority | Select | 
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20 |  |  |  | None | None |
| `is_recursive` | Is Recursive | Check | None |  |  |  | 0 | Discounts to be applied in sequential ranges like buy 1 get 1, buy 2 get 2, buy 3 get 3 and so on |
| `recurse_for` | Recurse Every (As Per Transaction UOM) | Float | None |  |  |  | 0 | Give free item for every N quantity |
| `apply_recursion_over` | Apply Recursion Over (As Per Transaction UOM) | Float | None |  |  |  | 0 | Qty for which recursion isn't applicable. |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
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
