# Master Control Plan: `Quality Inspection Reading`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `specification` | Parameter | Link | Quality Inspection Parameter | ✅ |  |  | None | None |
| `parameter_group` | Parameter Group | Link | Quality Inspection Parameter Group |  |  | ✅ | None | None |
| `status` | Status | Select | 
Accepted
Rejected |  |  |  | Accepted | None |
| `value` | Acceptance Criteria Value | Data | None |  |  |  | None | None |
| `numeric` | Numeric | Check | None |  |  |  | 1 | None |
| `manual_inspection` | Manual Inspection | Check | None |  |  |  | 0 | Set the status manually. |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `min_value` | Minimum Value | Float | None |  |  |  | None | Applied on each reading. |
| `max_value` | Maximum Value | Float | None |  |  |  | None | Applied on each reading. |
| `formula_based_criteria` | Formula Based Criteria | Check | None |  |  |  | 0 | None |
| `acceptance_formula` | Acceptance Criteria Formula | Code | None |  |  |  | None | Simple Python formula applied on Reading fields.<br> Numeric eg. 1: <b>reading_1 &gt; 0.2 and reading_1 &lt; 0.5</b><br>
Numeric eg. 2: <b>mean &gt; 3.5</b> (mean of populated fields)<br>
Value based eg.:  <b>reading_value in ("A", "B", "C")</b> |
| `section_break_3` | Value Based Inspection | Section Break | None |  |  |  | None | None |
| `reading_value` | Reading Value | Data | None |  |  |  | None | None |
| `section_break_14` | Numeric Inspection | Section Break | None |  |  |  | None | None |
| `reading_1` | Reading 1 | Data | None |  |  |  | None | None |
| `reading_2` | Reading 2 | Data | None |  |  |  | None | None |
| `reading_3` | Reading 3 | Data | None |  |  |  | None | None |
| `reading_4` | Reading 4 | Data | None |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `reading_5` | Reading 5 | Data | None |  |  |  | None | None |
| `reading_6` | Reading 6 | Data | None |  |  |  | None | None |
| `reading_7` | Reading 7 | Data | None |  |  |  | None | None |
| `reading_8` | Reading 8 | Data | None |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `reading_9` | Reading 9 | Data | None |  |  |  | None | None |
| `reading_10` | Reading 10 | Data | None |  |  |  | None | None |


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
