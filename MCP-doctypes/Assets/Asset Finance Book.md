# Master Control Plan: `Asset Finance Book`

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
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `depreciation_method` | Depreciation Method | Select | 
Straight Line
Double Declining Balance
Written Down Value
Manual | ✅ |  |  | None | None |
| `frequency_of_depreciation` | Frequency of Depreciation (Months) | Int | None | ✅ |  |  | None | None |
| `total_number_of_depreciations` | Total Number of Depreciations | Int | None | ✅ |  |  | None | None |
| `increase_in_asset_life` | Increase In Asset Life (Months) | Int | None |  |  | ✅ | None | via Asset Repair |
| `depreciation_start_date` | Depreciation Posting Date | Date | None |  |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `salvage_value_percentage` | Salvage Value Percentage | Percent | None |  |  |  | None | None |
| `expected_value_after_useful_life` | Salvage Value | Currency | Company:company:default_currency |  |  |  | 0 | Expected Value After Useful Life |
| `rate_of_depreciation` | Rate of Depreciation (%) | Percent | None |  |  |  | None | None |
| `daily_prorata_based` | Depreciate based on daily pro-rata | Check | None |  |  |  | 0 | None |
| `shift_based` | Depreciate based on shifts | Check | None |  |  |  | 0 | None |
| `section_break_jkdf` | None | Section Break | None |  |  |  | None | None |
| `value_after_depreciation` | Value After Depreciation | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_sigk` | None | Column Break | None |  |  |  | None | None |
| `total_number_of_booked_depreciations` | Total Number of Booked Depreciations  | Int | None |  |  | ✅ | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
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
