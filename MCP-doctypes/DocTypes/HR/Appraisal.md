# Master Control Plan: `Appraisal`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Employee | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee_details_tab` | Overview | Tab Break | None |  |  |  | None | None |
| `naming_series` | Series | Select | HR-APR-.YYYY.- | ✅ |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `designation` | Designation | Link | Designation |  |  | ✅ | None | None |
| `employee_image` | Employee Image | Attach Image | None |  | ✅ |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `appraisal_cycle` | Appraisal Cycle | Link | Appraisal Cycle | ✅ |  |  | None | None |
| `start_date` | Start Date | Date | None |  |  | ✅ | None | None |
| `end_date` | End Date | Date | None |  |  | ✅ | None | None |
| `section_break_aeb0` | None | Section Break | None |  |  |  | None | None |
| `final_score` | Final Score | Float | None |  |  | ✅ | None | Average of Goal Score, Feedback Score, and Self Appraisal Score (out of 5) |
| `kra_tab` | KRAs | Tab Break | None |  |  |  | None | None |
| `appraisal_template` | Appraisal Template | Link | Appraisal Template |  |  |  | None | None |
| `rate_goals_manually` | Rate Goals Manually | Check | None |  |  | ✅ | 0 | None |
| `section_break_kras` | None | Section Break | None |  |  |  | None | None |
| `appraisal_kra` | KRA vs Goals | Table | Appraisal KRA |  |  |  | None | None |
| `goal_score_percentage` | Goal Score (%) | Float | None |  |  | ✅ | None | None |
| `section_break_goals` | None | Section Break | None |  |  |  | None | None |
| `goals` | Goals | Table | Appraisal Goal |  |  |  | None | None |
| `remarks` | Remarks | Text | None |  |  |  | None | Any other remarks, noteworthy effort that should go in the records |
| `total_section` | None | Section Break | None |  |  |  | None | None |
| `total_score` | Total Goal Score | Float | None |  |  | ✅ | None | Out of 5 |
| `feedback_tab` | Feedback | Tab Break | None |  |  |  | None | None |
| `feedback_html` | Feedback HTML | HTML | None |  |  |  | None | None |
| `section_break_20` | None | Section Break | None |  |  |  | None | None |
| `avg_feedback_score` | Average Feedback Score | Float | None |  | ✅ | ✅ | None | None |
| `self_appraisal_tab` | Self Appraisal | Tab Break | None |  |  |  | None | None |
| `section_break_23` | Ratings | Section Break | None |  |  |  | None | None |
| `self_ratings` | None | Table | Employee Feedback Rating |  |  |  | None | None |
| `self_score` | Total Self Score | Float | None |  |  | ✅ | None | None |
| `reflections_section` | Reflections | Section Break | None |  |  |  | None | None |
| `reflections` | None | Text Editor | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Appraisal |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/appraisal/appraisal.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Appraisal", {
	refresh(frm) {
		if (!frm.doc.__islocal) {
			frm.trigger("add_custom_buttons");
			frm.trigger("show_feedback_history");
			frm.trigger("setup_chart");
		}

		// don't allow removing image (fetched from employee)
		frm.sidebar.image_wrapper.find(".sidebar-image-actions").addClass("hide");
	},

	appraisal_template(frm) {
		if (frm.doc.appraisal_template) {
			frm.call("set_kras_and_rating_criteria", () => {
				frm.refresh_field("appraisal_kra");
				frm.refresh_field("feedback_ratings");
			});
		}
	},

	appraisal_cycle(frm) {
		if (frm.doc.appraisal_cycle) {
			frappe.run_serially([
				() => {
					if (frm.doc.__islocal && frm.doc.appraisal_cycle) {
						frappe.db.get_value(
							"Appraisal Cycle",
							frm.doc.appraisal_cycle,
							"kra_evaluation_method",
							(r) => {
								if (r.kra_evaluation_method) {
									frm.set_value(
										"rate_goals_manually",
										cint(r.kra_evaluation_method === "Manual Rating"),
									);
								}
							},
						);
					}
				},
				() => {
					frm.call({
						method: "set_appraisal_template",
						doc: frm.doc,
					});
				},
			]);
		}
	},

	add_custom_buttons(frm) {
		frm.add_custom_button(__("View Goals"), function () {
			frappe.route_options = {
				company: frm.doc.company,
				employee: frm.doc.employee,
				appraisal_cycle: frm.doc.appraisal_cycle,
			};
			frappe.set_route("Tree", "Goal");
		});
	},

	show_feedback_history(frm) {
		frappe.require("performance.bundle.js", () => {
			const feedback_history = new hrms.PerformanceFeedback({
				frm: frm,
				wrapper: $(frm.fields_dict.feedback_html.wrapper),
			});
			feedback_history.refresh();
		});
	},

	setup_chart(frm) {
		const labels = [];
		const maximum_scores = [];
		const scores = [];

		frm.doc.appraisal_kra.forEach((d) => {
			labels.push(d.kra);
			maximum_scores.push(d.per_weightage || 0);
			scores.push(d.goal_score || 0);
		});

		if (labels.length && maximum_scores.length && scores.length) {
			frm.dashboard.render_graph({
				data: {
					labels: labels,
					datasets: [
						{
							name: "Maximum Score",
							chartType: "bar",
							values: maximum_scores,
						},
						{
							name: "Score Obtained",
							chartType: "bar",
							values: scores,
						},
					],
				},
				title: __("Scores"),
				height: 250,
				type: "bar",
				barOptions: {
					spaceRatio: 0.7,
				},
				colors: ["blue", "green"],
			});
		}
	},

	calculate_total(frm) {
		let total = 0;

		frm.doc.goals.forEach((d) => {
			total += flt(d.score_earned);
		});

		frm.set_value("total_score", total);
	},
});

frappe.ui.form.on("Appraisal Goal", {
	score(frm, cdt, cdn) {
		let d = frappe.get_doc(cdt, cdn);

		if (flt(d.score) > 5) {
			frappe.msgprint(__("Score must be less than or equal to 5"));
			d.score = 0;
			refresh_field("score", d.name, "goals");
		} else {
			frm.trigger("set_score_earned", cdt, cdn);
		}
	},

	per_weightage(frm, cdt, cdn) {
		frm.trigger("set_score_earned", cdt, cdn);
	},

	goals_remove(frm, cdt, cdn) {
		frm.trigger("set_score_earned", cdt, cdn);
	},

	set_score_earned(frm, cdt, cdn) {
		let d = frappe.get_doc(cdt, cdn);

		let score_earned = (flt(d.score) * flt(d.per_weightage)) / 100;
		frappe.model.set_value(cdt, cdn, "score_earned", score_earned);

		frm.trigger("calculate_total");
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Appraisal Overview` | Script Report | HR |



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
