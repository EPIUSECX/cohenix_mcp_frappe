# Master Control Plan: `Workspace Link`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
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
| `type` | Type | Select | Link
Card Break | ✅ |  |  | Link | None |
| `label` | Label | Data | None | ✅ |  |  | None | None |
| `icon` | Icon | Data | None |  |  |  | None | None |
| `description` | Description | HTML Editor | None |  |  |  | None | None |
| `hidden` | Hidden | Check | None |  |  |  | 0 | None |
| `link_details_section` | Link Details | Section Break | None |  |  |  | None | None |
| `link_type` | Link Type | Select | DocType
Page
Report |  |  |  | None | None |
| `link_to` | Link To | Dynamic Link | link_type |  |  |  | None | None |
| `report_ref_doctype` | Report Ref DocType | Link | DocType |  |  | ✅ | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `dependencies` | Dependencies | Data | None |  |  |  | None | None |
| `only_for` | Only for | Link | Country |  |  |  | None | None |
| `onboard` | Onboard | Check | None |  |  |  | 0 | None |
| `is_query_report` | Is Query Report | Check | None |  |  |  | 0 | None |
| `link_count` | Link Count | Int | None |  | ✅ |  | None | None |


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
