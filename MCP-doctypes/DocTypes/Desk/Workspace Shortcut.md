# Master Control Plan: `Workspace Shortcut`

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
| `type` | Type | Select | DocType
Report
Page
Dashboard
URL | ✅ |  |  | None | None |
| `link_to` | Link To | Dynamic Link | type |  |  |  | None | None |
| `url` | URL | Data | None |  |  |  | None | None |
| `doc_view` | DocType View | Select | 
List
Report Builder
Dashboard
Tree
New
Calendar
Kanban
Image |  |  |  | None | Which view of the associated DocType should this shortcut take you to? |
| `kanban_board` | Kanban Board | Link | Kanban Board |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `label` | Label | Data | None | ✅ |  |  | None | None |
| `icon` | Icon | Data | None |  |  |  | None | None |
| `restrict_to_domain` | Restrict to Domain | Link | Domain |  |  |  | None | None |
| `report_ref_doctype` | Report Ref DocType | Link | DocType |  |  | ✅ | None | None |
| `section_break_5` | Count Filter | Section Break | None |  |  |  | None | None |
| `stats_filter` | Count Filter | Code | JSON |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `color` | Color | Color | None |  |  |  | None | None |
| `format` | Format | Data | None |  |  |  | None | For example: {} Open |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
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
