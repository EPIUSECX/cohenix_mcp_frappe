# Master Control Plan: `Vehicle`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:license_plate`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Fleet Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Delivery User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| Delivery Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `license_plate` | License Plate | Data | None | ✅ |  |  | None | None |
| `make` | Make | Data | None | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `model` | Model | Data | None | ✅ |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `vehicle_details` | Details | Section Break | None |  |  |  | None | None |
| `last_odometer` | Odometer Value (Last) | Int | None | ✅ |  |  | None | None |
| `acquisition_date` | Acquisition Date | Date | None |  |  |  | None | None |
| `location` | Location | Data | None |  |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `chassis_no` | Chassis No | Data | None |  |  |  | None | None |
| `vehicle_value` | Vehicle Value | Currency | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee |  |  |  | None | None |
| `insurance_details` | Insurance Details | Section Break | None |  |  |  | None | None |
| `insurance_company` | Insurance Company | Data | None |  |  |  | None | None |
| `policy_no` | Policy No | Data | None |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None |  |  |  | None | None |
| `end_date` | End Date | Date | None |  |  |  | None | None |
| `additional_details` | Additional Details | Section Break | None |  |  |  | None | None |
| `fuel_type` | Fuel Type | Select | Petrol
Diesel
Natural Gas
Electric | ✅ |  |  | None | None |
| `uom` | Fuel UOM | Link | UOM | ✅ |  |  | None | None |
| `carbon_check_date` | Last Carbon Check | Date | None |  |  |  | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `color` | Color | Data | None |  |  |  | None | None |
| `wheels` | Wheels | Int | None |  |  |  | None | None |
| `doors` | Doors | Int | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Vehicle |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/vehicle/vehicle.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Vehicle", {
	refresh: function (frm) {},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Vehicle Expenses` | Script Report | HR |



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
