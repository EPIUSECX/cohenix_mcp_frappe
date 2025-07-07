# Master Control Plan: `Form Tour Step`

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
| `ui_tour` | UI Tour | Check | None |  |  |  | 0 | None |
| `is_table_field` | Is Table Field | Check | None |  |  |  | 0 | None |
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `parent_fieldname` | Parent Field | Select | None |  |  |  | None | None |
| `fieldname` | Fieldname | Select | None |  |  |  | None | None |
| `element_selector` | Element Selector | Data | None |  |  |  | None | CSS selector for the element you want to highlight. |
| `parent_element_selector` | Parent Element Selector | Data | None |  |  |  | None | Mozilla doesn't support :has() so you can pass parent selector here as workaround |
| `description` | Description | HTML Editor | None | ✅ |  |  | None | None |
| `ondemand_description` | Popover or Modal Description | HTML Editor | None |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `position` | Position | Select | Left
Left Center
Left Bottom
Top
Top Center
Top Right
Right
Right Center
Right Bottom
Bottom
Bottom Center
Bottom Right
Mid Center |  |  |  | Bottom | None |
| `hide_buttons` | Hide Buttons | Check | None |  |  |  | 0 | Hide Previous, Next and Close button on highlight dialog. |
| `popover_element` | Popover Element | Check | None |  |  |  | 0 | when clicked on element it will focus popover if present. |
| `modal_trigger` | Modal Trigger | Check | None |  |  |  | 0 | Enable if on click
opens modal. |
| `offset_x` | Offset X | Int | None |  |  |  | 0 | None |
| `offset_y` | Offset Y | Int | None |  |  |  | 0 | None |
| `next_on_click` | Next on Click | Check | None |  |  |  | 0 | Move to next step when clicked inside highlighted area. |
| `label` | Label | Data | None |  |  | ✅ | None | None |
| `fieldtype` | Fieldtype | Data | None |  |  | ✅ | 0 | None |
| `has_next_condition` | Has Next Condition | Check | None |  |  |  | 0 | None |
| `next_step_condition` | Next Step Condition | Code | JS |  |  |  | None | None |
| `next_form_tour` | Next Form Tour | Link | Form Tour |  |  |  | None | None |
| `section_break_13` | Hidden Fields | Section Break | None |  | ✅ |  | None | None |
| `child_doctype` | Child Doctype | Data | None |  | ✅ | ✅ | None | None |


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
