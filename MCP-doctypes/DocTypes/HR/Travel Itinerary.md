# Master Control Plan: `Travel Itinerary`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
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
| `travel_from` | Travel From | Data | None |  |  |  | None | None |
| `travel_to` | Travel To | Data | None |  |  |  | None | None |
| `mode_of_travel` | Mode of Travel | Select | 
Flight
Train
Taxi
Rented Car |  |  |  | None | None |
| `meal_preference` | Meal Preference | Select | 
Vegetarian
Non-Vegetarian
Gluten Free
Non Diary |  |  |  | None | None |
| `travel_advance_required` | Travel Advance Required | Check | None |  |  |  | 0 | None |
| `advance_amount` | Advance Amount | Data | None |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `departure_date` | Departure Datetime | Datetime | None |  |  |  | None | None |
| `arrival_date` | Arrival Datetime | Datetime | None |  |  |  | None | None |
| `lodging_required` | Lodging Required | Check | None |  |  |  | 0 | None |
| `preferred_area_for_lodging` | Preferred Area for Lodging | Data | None |  |  |  | None | None |
| `check_in_date` | Check-in Date | Date | None |  |  |  | None | None |
| `check_out_date` | Check-out Date | Date | None |  |  |  | None | None |
| `section_break_14` | None | Section Break | None |  |  |  | None | None |
| `other_details` | Other Details | Small Text | None |  |  |  | None | None |


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
