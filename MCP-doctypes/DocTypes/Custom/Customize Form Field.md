# Master Control Plan: `Customize Form Field`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Custom`
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
| `is_system_generated` | Is System Generated | Check | None |  | ✅ | ✅ | 0 | None |
| `label_and_type` | Label and Type | Section Break | None |  |  |  | None | None |
| `label` | Label | Data | None |  |  |  | None | None |
| `fieldtype` | Type | Select | Autocomplete
Attach
Attach Image
Barcode
Button
Check
Code
Color
Column Break
Currency
Data
Date
Datetime
Duration
Dynamic Link
Float
Fold
Geolocation
Heading
HTML
HTML Editor
Icon
Image
Int
JSON
Link
Long Text
Markdown Editor
Password
Percent
Phone
Rating
Read Only
Section Break
Select
Signature
Small Text
Tab Break
Table
Table MultiSelect
Text
Text Editor
Time | ✅ |  |  | Data | None |
| `fieldname` | Name | Data | None |  |  | ✅ | None | None |
| `non_negative` | Non Negative | Check | None |  |  |  | 0 | None |
| `reqd` | Mandatory | Check | None |  |  |  | 0 | None |
| `unique` | Unique | Check | None |  |  |  | 0 | None |
| `is_virtual` | Is Virtual | Check | None |  |  |  | 0 | None |
| `in_list_view` | In List View | Check | None |  |  |  | 0 | None |
| `in_standard_filter` | In Standard Filter | Check | None |  |  |  | 0 | None |
| `in_global_search` | In Global Search | Check | None |  |  |  | 0 | None |
| `in_preview` | In Preview | Check | None |  |  |  | 0 | None |
| `bold` | Bold | Check | None |  |  |  | 0 | None |
| `no_copy` | No Copy | Check | None |  |  |  | 0 | None |
| `allow_in_quick_entry` | Allow in Quick Entry | Check | None |  |  |  | 0 | None |
| `translatable` | Translatable | Check | None |  |  |  | 1 | None |
| `link_filters` | Link Filters | JSON | None |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `default` | Default | Small Text | None |  |  |  | None | None |
| `precision` | Precision | Select | 
0
1
2
3
4
5
6
7
8
9 |  |  |  | None | Set non-standard precision for a Float or Currency field |
| `length` | Length | Int | None |  |  |  | None | None |
| `options` | Options | Small Text | None |  |  |  | None | For Links, enter the DocType as range.
For Select, enter list of Options, each on a new line. |
| `sort_options` | Sort Options | Check | None |  |  |  | 0 | None |
| `fetch_from` | Fetch From | Small Text | None |  |  |  | None | None |
| `fetch_if_empty` | Fetch on Save if Empty | Check | None |  |  |  | 0 | If unchecked, the value will always be re-fetched on save. |
| `show_dashboard` | Show Dashboard | Check | None |  |  |  | 0 | None |
| `permissions` | Permissions | Section Break | None |  |  |  | None | None |
| `depends_on` | Depends On | Code | JS |  |  |  | None | This field will appear only if the fieldname defined here has value OR the rules are true (examples):
myfield
eval:doc.myfield=='My Value'
eval:doc.age&gt;18 |
| `permlevel` | Perm Level | Int | None |  |  |  | 0 | None |
| `hidden` | Hidden | Check | None |  |  |  | 0 | None |
| `read_only` | Read Only | Check | None |  |  |  | 0 | None |
| `collapsible` | Collapsible | Check | None |  |  |  | 0 | None |
| `allow_bulk_edit` | Allow Bulk Edit | Check | None |  |  |  | 0 | None |
| `collapsible_depends_on` | Collapsible Depends On | Code | JS |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `ignore_user_permissions` | Ignore User Permissions | Check | None |  |  |  | 0 | None |
| `allow_on_submit` | Allow on Submit | Check | None |  |  |  | 0 | None |
| `report_hide` | Report Hide | Check | None |  |  |  | 0 | None |
| `remember_last_selected_value` | Remember Last Selected Value | Check | None |  |  |  | 0 | None |
| `hide_border` | Hide Border | Check | None |  |  |  | 0 | None |
| `ignore_xss_filter` | Ignore XSS Filter | Check | None |  |  |  | 0 | Don't encode HTML tags like &lt;script&gt; or just characters like &lt; or &gt;, as they could be intentionally used in this field |
| `property_depends_on_section` | Property Depends On | Section Break | None |  |  |  | None | None |
| `mandatory_depends_on` | Mandatory Depends On | Code | JS |  |  |  | None | None |
| `column_break_33` | None | Column Break | None |  |  |  | None | None |
| `read_only_depends_on` | Read Only Depends On | Code | JS |  |  |  | None | None |
| `display` | Display | Section Break | None |  |  |  | None | None |
| `in_filter` | In Filter | Check | None |  |  |  | 0 | None |
| `hide_seconds` | Hide Seconds | Check | None |  |  |  | 0 | None |
| `hide_days` | Hide Days | Check | None |  |  |  | 0 | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `description` | Description | Text | None |  |  |  | None | None |
| `placeholder` | Placeholder | Data | None |  |  |  | None | None |
| `print_hide` | Print Hide | Check | None |  |  |  | 0 | None |
| `print_hide_if_no_value` | Print Hide If No Value | Check | None |  |  |  | 0 | None |
| `print_width` | Print Width | Data | None |  |  |  | None | Print Width of the field, if the field is a column in a table |
| `columns` | Columns | Int | None |  |  |  | None | Number of columns for a field in a Grid (Total Columns in a grid should be less than 11) |
| `width` | Width | Data | None |  |  |  | None | None |
| `is_custom_field` | Is Custom Field | Check | None |  | ✅ | ✅ | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
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
