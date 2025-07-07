# Master Control Plan: `Issue`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Support`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Support Team | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `subject_section` | None | Section Break | fa fa-flag |  |  |  | None | None |
| `naming_series` | Series | Select | ISS-.YYYY.- |  |  |  | None | None |
| `subject` | Subject | Data | None | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `raised_by` | Raised By (Email) | Data | Email |  |  |  | None | None |
| `cb00` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | Open
Replied
On Hold
Resolved
Closed |  |  |  | Open | None |
| `priority` | Priority | Link | Issue Priority |  |  |  | None | None |
| `issue_type` | Issue Type | Link | Issue Type |  |  |  | None | None |
| `issue_split_from` | Issue Split From | Link | Issue |  |  | ✅ | None | None |
| `sb_details` | Details | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `service_level_section` | Service Level Agreement Details | Section Break | None |  |  |  | None | None |
| `service_level_agreement` | Service Level Agreement | Link | Service Level Agreement |  |  |  | None | None |
| `response_by` | Response By | Datetime | None |  |  | ✅ | None | None |
| `reset_service_level_agreement` | Reset Service Level Agreement | Button | None |  |  |  | None | None |
| `cb` | None | Column Break | fa fa-pushpin |  |  | ✅ | None | None |
| `agreement_status` | Service Level Agreement Status | Select | First Response Due
Resolution Due
Fulfilled
Failed |  |  | ✅ | First Response Due | None |
| `sla_resolution_by` | Resolution By | Datetime | None |  |  | ✅ | None | None |
| `service_level_agreement_creation` | Service Level Agreement Creation | Datetime | None |  | ✅ | ✅ | None | None |
| `on_hold_since` | On Hold Since | Datetime | None |  | ✅ | ✅ | None | None |
| `total_hold_time` | Total Hold Time | Duration | None |  |  | ✅ | None | None |
| `response` | Response Details | Section Break | None |  |  |  | None | None |
| `first_response_time` | First Response Time | Duration | None |  |  | ✅ | None | None |
| `first_responded_on` | First Responded On | Datetime | None |  |  |  | None | None |
| `column_break_26` | None | Column Break | None |  |  |  | None | None |
| `avg_response_time` | Average Response Time | Duration | None |  |  | ✅ | None | None |
| `section_break_19` | Resolution Details | Section Break | None |  |  |  | None | None |
| `resolution_details` | Resolution Details | Text Editor | None |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  | ✅ | None | None |
| `opening_date` | Opening Date | Date | None |  |  | ✅ | Today | None |
| `opening_time` | Opening Time | Time | None |  |  | ✅ | None | None |
| `sla_resolution_date` | Resolution Date | Datetime | None |  |  | ✅ | None | None |
| `resolution_time` | Resolution Time | Duration | None |  |  | ✅ | None | None |
| `user_resolution_time` | User Resolution Time | Duration | None |  |  | ✅ | None | None |
| `additional_info` | Reference | Section Break | fa fa-pushpin |  |  | ✅ | None | None |
| `lead` | Lead | Link | Lead |  |  |  | None | None |
| `contact` | Contact | Link | Contact |  |  |  | None | None |
| `email_account` | Email Account | Link | Email Account |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  |  | ✅ | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `via_customer_portal` | Via Customer Portal | Check | None |  |  |  | 0 | None |
| `attachment` | Attachment | Attach | None |  | ✅ |  | None | None |
| `content_type` | Content Type | Data | None |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 10
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/support/doctype/issue/issue.js`
```javascript
frappe.ui.form.on("Issue", {
	onload: function (frm) {
		frm.email_field = "raised_by";

		frappe.db.get_value(
			"Support Settings",
			{ name: "Support Settings" },
			["allow_resetting_service_level_agreement", "track_service_level_agreement"],
			(r) => {
				if (r && r.track_service_level_agreement == "0") {
					frm.set_df_property("service_level_section", "hidden", 1);
				}
				if (r && r.allow_resetting_service_level_agreement == "0") {
					frm.set_df_property("reset_service_level_agreement", "hidden", 1);
				}
			}
		);
	},

	refresh: function (frm) {
		// buttons
		if (frm.doc.status !== "Closed") {
			frm.add_custom_button(__("Close"), function () {
				frm.set_value("status", "Closed");
				frm.save();
			});

			frm.add_custom_button(
				__("Task"),
				function () {
					frappe.model.open_mapped_doc({
						method: "erpnext.support.doctype.issue.issue.make_task",
						frm: frm,
					});
				},
				__("Create")
			);
		} else {
			frm.add_custom_button(__("Reopen"), function () {
				frm.set_value("status", "Open");
				frm.save();
			});
		}
	},

	reset_service_level_agreement: function (frm) {
		let reset_sla = new frappe.ui.Dialog({
			title: __("Reset Service Level Agreement"),
			fields: [
				{
					fieldtype: "Data",
					fieldname: "reason",
					label: __("Reason"),
					reqd: 1,
				},
			],
			primary_action_label: __("Reset"),
			primary_action: (values) => {
				reset_sla.disable_primary_action();
				reset_sla.hide();
				reset_sla.clear();

				frappe.show_alert({
					indicator: "green",
					message: __("Resetting Service Level Agreement."),
				});

				frappe.call(
					"erpnext.support.doctype.service_level_agreement.service_level_agreement.reset_service_level_agreement",
					{
						reason: values.reason,
						user: frappe.session.user_email,
						doctype: frm.doc.doctype,
						docname: frm.doc.name,
					},
					() => {
						reset_sla.enable_primary_action();
						frm.refresh();
						frappe.msgprint(__("Service Level Agreement was reset."));
					}
				);
			},
		});

		reset_sla.show();
	},

	timeline_refresh: function (frm) {
		if (!frm.timeline.wrapper.find(".btn-split-issue").length) {
			let split_issue_btn = $(`
				<a class="action-btn btn-split-issue" title="${__("Split Issue")}">
					${frappe.utils.icon("branch", "sm")}
				</a>
			`);

			let communication_box = frm.timeline.wrapper.find('.timeline-item[data-doctype="Communication"]');
			communication_box.find(".actions").prepend(split_issue_btn);

			if (!frm.timeline.wrapper.data("split-issue-event-attached")) {
				frm.timeline.wrapper.on("click", ".btn-split-issue", (e) => {
					var dialog = new frappe.ui.Dialog({
						title: __("Split Issue"),
						fields: [
							{
								fieldname: "subject",
								fieldtype: "Data",
								reqd: 1,
								label: __("Subject"),
								description: __(
									"All communications including and above this shall be moved into the new Issue"
								),
							},
						],
						primary_action_label: __("Split"),
						primary_action: () => {
							frm.call(
								"split_issue",
								{
									subject: dialog.fields_dict.subject.value,
									communication_id: e.currentTarget
										.closest(".timeline-item")
										.getAttribute("data-name"),
								},
								(r) => {
									frappe.msgprint(
										`New issue created: <a href="/app/issue/${r.message}">${r.message}</a>`
									);
									frm.reload_doc();
									dialog.hide();
								}
							);
						},
					});
					dialog.show();
				});
				frm.timeline.wrapper.data("split-issue-event-attached", true);
			}
		}

		// create button for "Help Article"
		// if (frappe.model.can_create("Help Article")) {
		// 	// Removing Help Article button if exists to avoid multiple occurrence
		// 	frm.timeline.wrapper.find('.action-btn .btn-add-to-kb').remove();

		// 	let help_article = $(`
		// 		<a class="action-btn btn-add-to-kb" title="${__('Help Article')}">
		// 			${frappe.utils.icon('solid-info', 'sm')}
		// 		</a>
		// 	`);

		// 	let communication_box = frm.timeline.wrapper.find('.timeline-item[data-doctype="Communication"]');
		// 	communication_box.find('.actions').prepend(help_article);
		// 	if (!frm.timeline.wrapper.data("help-article-event-attached")) {
		// 		frm.timeline.wrapper.on('click', '.btn-add-to-kb', function () {
		// 			const content = $(this).parents('.timeline-item[data-doctype="Communication"]:first').find(".content").html();
		// 			const doc = frappe.model.get_new_doc("Help Article");
		// 			doc.title = frm.doc.subject;
		// 			doc.content = content;
		// 			frappe.set_route("Form", "Help Article", doc.name);
		// 		});
		// 	}
		// 	frm.timeline.wrapper.data("help-article-event-attached", true);
		// }
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Issue Summary` | Script Report | Support |
| `Issue Analytics` | Script Report | Support |
| `First Response Time for Issues` | Script Report | Support |
| `Support Hour Distribution` | Script Report | Support |



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
