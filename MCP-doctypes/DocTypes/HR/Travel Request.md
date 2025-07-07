# Master Control Plan: `Travel Request`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-TRQ-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `travel_type` | Travel Type | Select | 
Domestic
International | ✅ |  |  | None | None |
| `travel_funding` | Travel Funding | Select | 
Require Full Funding
Fully Sponsored
Partially Sponsored, Require Partial Funding |  |  |  | None | None |
| `travel_proof` | Copy of Invitation/Announcement | Attach | None |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `purpose_of_travel` | Purpose of Travel | Link | Purpose of Travel | ✅ |  |  | None | None |
| `details_of_sponsor` | Details of Sponsor (Name, Location) | Data | None |  |  |  | None | None |
| `employee_details` | Employee Details | Section Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `cell_number` | Contact Number | Data | None |  |  |  | None | None |
| `prefered_email` | Contact Email | Data | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `date_of_birth` | Date of Birth | Date | None |  |  | ✅ | None | None |
| `personal_id_type` | Identification Document Type | Link | Identification Document Type |  |  |  | None | None |
| `personal_id_number` | Identification Document Number | Data | None |  |  |  | None | None |
| `passport_number` | Passport Number | Data | None |  |  |  | None | None |
| `section_break_4` | Description | Section Break | None |  |  |  | None | None |
| `description` | Any other details | Small Text | None |  |  |  | None | None |
| `travel_itinerary` | Travel Itinerary | Section Break | None |  |  |  | None | None |
| `itinerary` | None | Table | Travel Itinerary |  |  |  | None | None |
| `costing_details` | Costing Details | Section Break | None |  |  |  | None | None |
| `costings` | Costing | Table | Travel Request Costing |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `event_details` | Event Details | Section Break | None |  |  |  | None | None |
| `name_of_organizer` | Name of Organizer | Data | None |  |  |  | None | None |
| `address_of_organizer` | Address of Organizer | Data | None |  |  |  | None | None |
| `other_details` | Other Details | Text | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Travel Request |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/travel_request/travel_request.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Travel Request", {
	refresh: function (frm) {},
});

```




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
