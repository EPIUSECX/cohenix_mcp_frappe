# Master Control Plan: `Repost Item Valuation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `based_on` | Based On | Select | Transaction
Item and Warehouse | ✅ |  |  | Transaction | None |
| `voucher_type` | Voucher Type | Link | DocType |  |  |  | None | None |
| `voucher_no` | Voucher No | Dynamic Link | voucher_type |  |  |  | None | None |
| `item_code` | Item Code | Link | Item |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | None | None |
| `posting_time` | Posting Time | Time | None |  |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | Queued
In Progress
Completed
Skipped
Failed |  |  | ✅ | Queued | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `allow_negative_stock` | Allow Negative Stock | Check | None |  |  |  | 1 | None |
| `via_landed_cost_voucher` | Via Landed Cost Voucher | Check | None |  |  |  | 0 | None |
| `allow_zero_rate` | Allow Zero Rate | Check | None |  |  |  | 0 | None |
| `recreate_stock_ledgers` | Recreate Stock Ledgers | Check | None |  |  |  | 0 | None |
| `amended_from` | Amended From | Link | Repost Item Valuation |  |  | ✅ | None | None |
| `error_section` | Error | Section Break | None |  |  |  | None | None |
| `error_log` | Error Log | Long Text | None |  |  | ✅ | None | None |
| `reposting_info_section` | Reposting Info | Section Break | None |  |  |  | None | None |
| `reposting_data_file` | Reposting Data File | Attach | None |  |  | ✅ | None | None |
| `items_to_be_repost` | Items to Be Repost | Code | None |  | ✅ | ✅ | None | None |
| `distinct_item_and_warehouse` | Distinct Item and Warehouse | Code | None |  | ✅ | ✅ | None | None |
| `column_break_o1sj` | None | Column Break | None |  |  |  | None | None |
| `total_reposting_count` | Total Reposting Count | Int | None |  |  | ✅ | None | None |
| `current_index` | Current Index | Int | None |  | ✅ | ✅ | None | None |
| `gl_reposting_index` | GL reposting index | Int | None |  | ✅ | ✅ | 0 | None |
| `affected_transactions` | Affected Transactions | Code | None |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/repost_item_valuation/repost_item_valuation.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Repost Item Valuation", {
	setup: function (frm) {
		frm.set_query("warehouse", () => {
			let filters = {
				is_group: 0,
			};
			if (frm.doc.company) filters["company"] = frm.doc.company;
			return { filters: filters };
		});

		frm.set_query("voucher_type", () => {
			return {
				filters: {
					name: [
						"in",
						[
							"Purchase Receipt",
							"Purchase Invoice",
							"Delivery Note",
							"Sales Invoice",
							"Stock Entry",
							"Stock Reconciliation",
							"Subcontracting Receipt",
						],
					],
				},
			};
		});

		if (frm.doc.company) {
			frm.set_query("voucher_no", () => {
				return {
					filters: {
						company: frm.doc.company,
						docstatus: 1,
					},
				};
			});
		}

		frm.trigger("setup_realtime_progress");
	},

	based_on: function (frm) {
		var fields_to_reset = [];

		if (frm.doc.based_on == "Transaction") {
			fields_to_reset = ["item_code", "warehouse"];
		} else if (frm.doc.based_on == "Item and Warehouse") {
			fields_to_reset = ["voucher_type", "voucher_no"];
		}

		if (fields_to_reset) {
			fields_to_reset.forEach((field) => {
				frm.set_value(field, undefined);
			});
		}
	},

	setup_realtime_progress: function (frm) {
		frappe.realtime.on("item_reposting_progress", (data) => {
			if (frm.doc.name !== data.name) {
				return;
			}

			if (frm.doc.status == "In Progress") {
				frm.doc.current_index = data.current_index;
				frm.doc.items_to_be_repost = data.items_to_be_repost;
				frm.doc.total_reposting_count = data.total_reposting_count;

				frm.dashboard.reset();
				frm.trigger("show_reposting_progress");
			}
		});
	},

	refresh: function (frm) {
		if (frm.doc.status == "Failed" && frm.doc.docstatus == 1) {
			frm.add_custom_button(__("Restart"), function () {
				frm.trigger("restart_reposting");
			}).addClass("btn-primary");
		}

		frm.trigger("show_reposting_progress");

		if (frm.doc.status === "Queued" && frm.doc.docstatus === 1) {
			frm.trigger("execute_reposting");
		}
	},

	execute_reposting(frm) {
		frm.add_custom_button(__("Start Reposting"), () => {
			frappe.call({
				method: "erpnext.stock.doctype.repost_item_valuation.repost_item_valuation.execute_repost_item_valuation",
				callback: function () {
					frappe.msgprint(__("Reposting has been started in the background."));
				},
			});
		});
	},

	show_reposting_progress: function (frm) {
		var bars = [];

		let total_count = frm.doc.items_to_be_repost ? JSON.parse(frm.doc.items_to_be_repost).length : 0;

		if (frm.doc?.total_reposting_count) {
			total_count = frm.doc.total_reposting_count;
		}

		let progress = flt((cint(frm.doc.current_index) / total_count) * 100, 2) || 0.5;
		var title = __("Reposting Completed {0}%", [progress]);

		bars.push({
			title: title,
			width: progress + "%",
			progress_class: "progress-bar-success",
		});

		frm.dashboard.add_progress(__("Reposting Progress"), bars);
	},

	restart_reposting: function (frm) {
		frappe.call({
			method: "restart_reposting",
			doc: frm.doc,
			callback: function (r) {
				frm.reload_doc();
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
