# Master Control Plan: `Promotional Scheme Price Discount`

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
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `min_qty` | Min Qty | Float | None |  |  |  | 0 | None |
| `max_qty` | Max Qty | Float | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `min_amount` | Min Amount | Currency | None |  |  |  | 0 | None |
| `max_amount` | Max Amount | Currency | None |  |  |  | 0 | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `rate_or_discount` | Discount Type | Select | 
Rate
Discount Percentage
Discount Amount |  |  |  | Discount Percentage | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | None |  |  |  | None | None |
| `discount_amount` | Discount Amount | Currency | None |  |  |  | None | None |
| `discount_percentage` | Discount Percentage | Float | None |  |  |  | None | None |
| `for_price_list` | For Price List | Link | Price List |  |  |  | None | None |
| `section_break_11` | None | Section Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  |  | None | None |
| `threshold_percentage` | Threshold for Suggestion | Percent | None |  |  |  | None | None |
| `validate_applied_rule` | Validate Applied Rule | Check | None |  |  |  | 0 | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
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
| `apply_discount_on_rate` | Apply Discount on Rate | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
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
