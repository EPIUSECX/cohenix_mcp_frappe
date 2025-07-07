# Master Control Plan: `Leave Type`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:leave_type_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `leave_type_name` | Leave Type Name | Data | None | ✅ |  |  | None | None |
| `max_leaves_allowed` | Maximum Leave Allocation Allowed per Leave Period | Float | None |  |  |  | None | None |
| `applicable_after` | Allow Leave Application After (Working Days) | Int | None |  |  |  | None | Minimum working days required since Date of Joining to apply for this leave |
| `max_continuous_days_allowed` | Maximum Consecutive Leaves Allowed | Int | None |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `is_carry_forward` | Is Carry Forward | Check | None |  |  |  | 0 | None |
| `is_lwp` | Is Leave Without Pay | Check | None |  |  |  | 0 | None |
| `is_ppl` | Is Partially Paid Leave | Check | None |  |  |  | 0 | None |
| `fraction_of_daily_salary_per_leave` | Fraction of Daily Salary per Leave | Float | None |  |  |  | None | For a day of leave taken, if you still pay (say) 50% of the daily salary, then enter 0.50 in this field. |
| `is_optional_leave` | Is Optional Leave | Check | None |  |  |  | 0 | These leaves are holidays permitted by the company however, availing it is optional for an Employee. |
| `allow_negative` | Allow Negative Balance | Check | None |  |  |  | 0 | None |
| `allow_over_allocation` | Allow Over Allocation | Check | None |  |  |  | 0 | Allows allocating more leaves than the number of days in the allocation period. |
| `include_holiday` | Include holidays within leaves as leaves | Check | None |  |  |  | 0 | None |
| `is_compensatory` | Is Compensatory | Check | None |  |  |  | 0 | None |
| `carry_forward_section` | Carry Forward | Section Break | None |  |  |  | None | None |
| `maximum_carry_forwarded_leaves` | Maximum Carry Forwarded Leaves | Float | None |  |  |  | None | None |
| `expire_carry_forwarded_leaves_after_days` | Expire Carry Forwarded Leaves (Days) | Int | None |  |  |  | None | Calculated in days |
| `encashment` | Encashment | Section Break | None |  |  |  | None | None |
| `allow_encashment` | Allow Encashment | Check | None |  |  |  | 0 | None |
| `max_encashable_leaves` | Maximum Encashable Leaves | Int | None |  |  |  | None | None |
| `non_encashable_leaves` | Non-Encashable Leaves | Int | None |  |  |  | None | Indicates the number of leaves that cannot be encashed from the leave balance. E.g. with a leave balance of 10 and 4 Non-Encashable Leaves, you can encash 6, while the remaining 4 can be carried forward or expired |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `earning_component` | Earning Component | Link | Salary Component |  |  |  | None | None |
| `earned_leave` | Earned Leave | Section Break | None |  |  |  | None | None |
| `is_earned_leave` | Is Earned Leave | Check | None |  |  |  | 0 | None |
| `earned_leave_frequency` | Earned Leave Frequency | Select | Monthly
Quarterly
Half-Yearly
Yearly |  |  |  | None | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `allocate_on_day` | Allocate on Day | Select | First Day
Last Day
Date of Joining |  |  |  | Last Day | The day of the month when leaves should be allocated |
| `rounding` | Rounding | Select | 
0.25
0.5
1.0 |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_type/leave_type.js`
```javascript
frappe.ui.form.on("Leave Type", {
	refresh: function (frm) {},
});

frappe.tour["Leave Type"] = [
	{
		fieldname: "max_leaves_allowed",
		title: "Maximum Leave Allocation Allowed",
		description: __(
			"This field allows you to set the maximum number of leaves that can be allocated annually for this Leave Type while creating the Leave Policy",
		),
	},
	{
		fieldname: "max_continuous_days_allowed",
		title: "Maximum Consecutive Leaves Allowed",
		description: __(
			"This field allows you to set the maximum number of consecutive leaves an Employee can apply for.",
		),
	},
	{
		fieldname: "is_optional_leave",
		title: "Is Optional Leave",
		description: __(
			"Optional Leaves are holidays that Employees can choose to avail from a list of holidays published by the company.",
		),
	},
	{
		fieldname: "is_compensatory",
		title: "Is Compensatory Leave",
		description: __(
			"Leaves you can avail against a holiday you worked on. You can claim Compensatory Off Leave using Compensatory Leave Request. Click {0} to know more",
			[
				`<a href='https://docs.frappe.io/hr/compensatory-leave-request' target='_blank'>${__(
					"here",
				)}</a>`,
			],
		),
	},
	{
		fieldname: "allow_encashment",
		title: "Allow Encashment",
		description: __("From here, you can enable encashment for the balance leaves."),
	},
	{
		fieldname: "is_earned_leave",
		title: "Is Earned Leaves",
		description: __(
			"Earned Leaves are leaves earned by an Employee after working with the company for a certain amount of time. Enabling this will allocate leaves on pro-rata basis by automatically updating Leave Allocation for leaves of this type at intervals set by 'Earned Leave Frequency.",
		),
	},
];

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
