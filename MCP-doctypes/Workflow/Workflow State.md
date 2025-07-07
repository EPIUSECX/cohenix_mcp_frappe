# Master Control Plan: `Workflow State`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Workflow`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:workflow_state_name`
- **Description:** Workflow state represents the current state of a document.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `workflow_state_name` | State | Data | None | ✅ |  |  | None | None |
| `icon` | Icon | Select | 
glass
music
search
envelope
heart
star
star-empty
user
film
th-large
th
th-list
ok
remove
zoom-in
zoom-out
off
signal
cog
trash
home
file
time
road
download-alt
download
upload
inbox
play-circle
repeat
refresh
list-alt
lock
flag
headphones
volume-off
volume-down
volume-up
qrcode
barcode
tag
tags
book
bookmark
print
camera
font
bold
italic
text-height
text-width
align-left
align-center
align-right
align-justify
list
indent-left
indent-right
facetime-video
picture
pencil
map-marker
adjust
tint
edit
share
check
move
step-backward
fast-backward
backward
play
pause
stop
forward
fast-forward
step-forward
eject
chevron-left
chevron-right
plus-sign
minus-sign
remove-sign
ok-sign
question-sign
info-sign
screenshot
remove-circle
ok-circle
ban-circle
arrow-left
arrow-right
arrow-up
arrow-down
share-alt
resize-full
resize-small
plus
minus
asterisk
exclamation-sign
gift
leaf
fire
eye-open
eye-close
warning-sign
plane
calendar
random
comment
magnet
chevron-up
chevron-down
retweet
shopping-cart
folder-close
folder-open
resize-vertical
resize-horizontal
hdd
bullhorn
bell
certificate
thumbs-up
thumbs-down
hand-right
hand-left
hand-up
hand-down
circle-arrow-right
circle-arrow-left
circle-arrow-up
circle-arrow-down
globe
wrench
tasks
filter
briefcase
fullscreen |  | ✅ |  | None | Icon will appear on the button |
| `style` | Style | Select | 
Primary
Info
Success
Warning
Danger
Inverse |  |  |  | None | Style represents the button color: Success - Green, Danger - Red, Inverse - Black, Primary - Dark Blue, Info - Light Blue, Warning - Orange |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/workflow/doctype/workflow_state/workflow_state.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Workflow State", {
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
