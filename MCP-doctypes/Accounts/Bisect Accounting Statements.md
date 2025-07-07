# Master Control Plan: `Bisect Accounting Statements`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_cvfg` | None | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `column_break_hcam` | None | Column Break | None |  |  |  | None | None |
| `from_date` | From Date | Datetime | None |  |  |  | None | None |
| `column_break_qxbi` | None | Column Break | None |  |  |  | None | None |
| `to_date` | To Date | Datetime | None |  |  |  | None | None |
| `column_break_iwny` | None | Column Break | None |  |  |  | None | None |
| `algorithm` | Algorithm | Select | BFS
DFS |  |  |  | BFS | None |
| `section_break_8ph9` | None | Section Break | None |  | ✅ |  | None | None |
| `current_node` | Current Node | Link | Bisect Nodes |  |  |  | None | None |
| `section_break_ngid` | None | Section Break | None |  |  |  | None | None |
| `bisect_heatmap` | Heatmap | HTML | None |  |  |  | None | None |
| `section_break_hmsy` | None | Section Break | None |  |  |  | None | None |
| `bisecting_from` | Bisecting From | Heading | None |  |  |  | None | None |
| `current_from_date` | None | Datetime | None |  |  | ✅ | None | None |
| `column_break_uqyd` | None | Column Break | None |  |  |  | None | None |
| `bisecting_to` | Bisecting To | Heading | None |  |  |  | None | None |
| `current_to_date` | None | Datetime | None |  |  | ✅ | None | None |
| `section_break_hbyo` | None | Section Break | None |  |  |  | None | None |
| `heading_cppb` | Profit and Loss Summary | Heading | None |  |  |  | None | None |
| `p_l_summary` | None | Float | None |  |  | ✅ | None | None |
| `column_break_aivo` | None | Column Break | None |  |  |  | None | None |
| `balance_sheet_summary` | Balance Sheet Summary | Heading | None |  |  |  | None | None |
| `b_s_summary` | None | Float | None |  |  | ✅ | None | None |
| `column_break_gvwx` | None | Column Break | None |  |  |  | None | None |
| `difference_heading` | Difference | Heading | None |  |  |  | None | None |
| `difference` | None | Float | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bisect_accounting_statements/bisect_accounting_statements.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Bisect Accounting Statements", {
	onload(frm) {
		frm.trigger("render_heatmap");
	},
	refresh(frm) {
		frm.add_custom_button(__("Bisect Left"), () => {
			frm.trigger("bisect_left");
		});

		frm.add_custom_button(__("Bisect Right"), () => {
			frm.trigger("bisect_right");
		});

		frm.add_custom_button(__("Up"), () => {
			frm.trigger("move_up");
		});
		frm.add_custom_button(__("Build Tree"), () => {
			frm.trigger("build_tree");
		});
	},
	render_heatmap(frm) {
		let bisect_heatmap = frm.get_field("bisect_heatmap").$wrapper;
		bisect_heatmap.addClass("bisect_heatmap_location");

		// milliseconds in a day
		let msiad = 24 * 60 * 60 * 1000;
		let datapoints = {};
		let fr_dt = new Date(frm.doc.from_date).getTime();
		let to_dt = new Date(frm.doc.to_date).getTime();
		let bisect_start = new Date(frm.doc.current_from_date).getTime();
		let bisect_end = new Date(frm.doc.current_to_date).getTime();

		for (let x = fr_dt; x <= to_dt; x += msiad) {
			let epoch_in_seconds = x / 1000;
			if (bisect_start <= x && x <= bisect_end) {
				datapoints[epoch_in_seconds] = 1.0;
			} else {
				datapoints[epoch_in_seconds] = 0.0;
			}
		}

		new frappe.Chart(".bisect_heatmap_location", {
			type: "heatmap",
			data: {
				dataPoints: datapoints,
				start: new Date(frm.doc.from_date),
				end: new Date(frm.doc.to_date),
			},
			countLabel: "Bisecting",
			discreteDomains: 1,
		});
	},
	bisect_left(frm) {
		frm.call({
			doc: frm.doc,
			method: "bisect_left",
			freeze: true,
			freeze_message: __("Bisecting Left ..."),
			callback: (r) => {
				frm.trigger("render_heatmap");
			},
		});
	},
	bisect_right(frm) {
		frm.call({
			doc: frm.doc,
			freeze: true,
			freeze_message: __("Bisecting Right ..."),
			method: "bisect_right",
			callback: (r) => {
				frm.trigger("render_heatmap");
			},
		});
	},
	move_up(frm) {
		frm.call({
			doc: frm.doc,
			freeze: true,
			freeze_message: __("Moving up in tree ..."),
			method: "move_up",
			callback: (r) => {
				frm.trigger("render_heatmap");
			},
		});
	},
	build_tree(frm) {
		frm.call({
			doc: frm.doc,
			freeze: true,
			freeze_message: __("Rebuilding BTree for period ..."),
			method: "build_tree",
			callback: (r) => {
				frm.trigger("render_heatmap");
			},
		});
	},
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
