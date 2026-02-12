---
description: 'CRM Timeline: Configurable activities structure and setup'
methods:
- crm.activity.badge.add
- crm.activity.badge.delete
- crm.activity.badge.get
- crm.activity.badge.list
- crm.activity.configurable.add
- crm.activity.configurable.get
- crm.activity.configurable.update
- crm.activity.delete
- crm.activity.list
- crm.activity.type.add
- crm.timeline.icon.list
- crm.timeline.logo.list
pages: 20
title: 'CRM Timeline: Configurable activities structure and setup'
---
# CRM Timeline: Configurable activities structure and setup
> CRM Timeline: Configurable activities structure and setup
> **20 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Overview of Methods](#overview-of-methods)
- [Structure of Configurable Activity](#structure-of-configurable-activity)
- [Icon](#icon)
- [Record Header](#record-header)
- [Main Content Area of Configurable Activity](#main-content-area-of-configurable-activity)
- [Content Block of Configurable Deal](#content-block-of-configurable-deal)
- [Bottom Part of the Record](#bottom-part-of-the-record)
- [Bottom Dropdown Menu](#bottom-dropdown-menu)
- [Click Reaction](#click-reaction)
- [Field Types](#field-types)
- [Bitrix24 REST API and Marketplace Applications](#bitrix24-rest-api-and-marketplace-applications)
- [Examples of Activity Configurations](#examples-of-activity-configurations)
- [About Configurable Activity Badges](#about-configurable-activity-badges)
- [Add Badge crm.activity.badge.add](#add-badge-crmactivitybadgeadd)
- [Get the list of badges crm.activity.badge.list](#get-the-list-of-badges-crmactivitybadgelist)
- [Get Badge Information by Code crm.activity.badge.get](#get-badge-information-by-code-crmactivitybadgeget)
- [Delete Badge by Code crm.activity.badge.delete](#delete-badge-by-code-crmactivitybadgedelete)
- [Add Configurable CRM Activity <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-hjgc7icy">crm.activity.configurable.add</code>](#add-configurable-crm-activity-code-classyfm-clipbo)
- [Update Configurable Activity crm.activity.configurable.update](#update-configurable-activity-crmactivityconfigurab)
- [Get Configurable Activity by ID crm.activity.configurable.get](#get-configurable-activity-by-id-crmactivityconfigu)

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: any user
Configurable activities are a type of activity that can only be created from the application. For this type, you can customize the appearance of the activity detail form and its functionality. Methods for working with custom activity types in the
timeline
Method
Description
crm.activity.configurable.add
Adds a new configurable activity to the timeline
crm.activity.configurable.update
Updates a configurable activity
crm.activity.configurable.get
Retrieves information about the activity
crm.activity.delete
Deletes a configurable activity by its identifier
crm.activity.list
Retrieves a list of all configurable activities for a CRM entity filtered by
PROVIDER_ID
=
CONFIGURABLE_REST_APP
Warning
The methods
crm.activity.configurable.add
,
crm.activity.configurable.update
,
crm.activity.configurable.get
can only be called in the context of an
application
.
Additional
Additional
Structure of Configurable Activity
About Configurable Activity Badges
Copied
Was the article helpful?
Yes
No
Previous
Get Communication Description
Next
Structure of a Configurable Activity

---

## Structure of Configurable Activity

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/layout

Structure of Configurable Activity | Bitrix24 REST API and Marketplace Applications
Parameters of the LayoutDto Object
Structure of Configurable Activity
Parameters of the LayoutDto Object
Example Object
Continue Learning
The object that describes the appearance of the
timeline entry
is a hierarchical structure of nested objects of various types.
Each of the nested objects has its own set of fields and is described below in the form of DTO (Data Transfer Object).
The top-level object of the timeline entry is
LayoutDto
.
Parameters of the  Object
Parameters of the
LayoutDto
Object
Required parameters are marked with *
Field
Description
icon
*
IconDto
Icon to the left of the entry
header
*
HeaderDto
Title of the entry
body
*
BodyDto
Main content area of the entry
footer
FooterDto
Bottom part of the entry with action block
Example Object
Example Object
{
"icon"
:
{
"code"
:
"call-completed"
}
,
"header"
:
{
"title"
:
"Incoming Call"
,
"tags"
:
{
"status2"
:
{
"type"
:
"warning"
,
"title"
:
"not deciphered"
}
}
}
,
"body"
:
{
"logo"
:
{
"code"
:
"call-incoming"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
}
,
"blocks"
:
{
"client"
:
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Client"
,
"inline"
:
true
,
"block"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Ltd. Horns and Hooves"
}
}
}
}
,
"responsible"
:
{
"type"
:
"lineOfBlocks"
,
"properties"
:
{
"blocks"
:
{
"client"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Sergey Vostrikov"
,
"bold"
:
true
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/lead/details/789/"
}
}
}
,
"phone"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"+1 999 888 7777"
}
}
}
}
}
}
}
,
"footer"
:
{
"buttons"
:
{
"startCall"
:
{
"title"
:
"About the Client"
,
"action"
:
{
"type"
:
"openRestApp"
,
"actionParams"
:
{
"clientId"
:
456
}
}
,
"type"
:
"primary"
}
}
,
"menu"
:
{
"showPostponeItem"
:
"false"
,
"items"
:
{
"confirm"
:
{
"title"
:
"Confirm Request"
,
"action"
:
{
"type"
:
"restEvent"
,
"id"
:
"confirm"
,
"animationType"
:
"loader"
}
}
,
"decline"
:
{
"title"
:
"Decline Request"
,
"action"
:
{
"type"
:
"restEvent"
,
"id"
:
"decline"
,
"animationType"
:
"loader"
}
}
}
}
}
}
Continue Learning
Continue Learning
Icon
Record Header
Main Content Area of Configurable Activity
Content Block of Configurable Deal
Bottom Part of the Record
Bottom Dropdown Menu
Click Reaction
Field Types
Set of Additional Content Blocks
Examples of Activity Configurations
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Icon

---

## Icon

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/icon

Icon | Bitrix24 REST API and Marketplace Applications
Parameters of the IconDto Object
Icon
Parameters of the IconDto Object
Example of the Object
Continue Exploring
Icon of the
timeline entry
IconDto
.
Parameters of the  Object
Parameters of the
IconDto
Object
Required parameters are marked with *
Field
Description
Additional
code
*
string
Icon code
A list of available codes can be obtained using the
crm.timeline.icon.list
method
Example of the Object
Example of the Object
{
"icon"
:
{
"code"
:
"call-completed"
}
}
Continue Exploring
Continue Exploring
Structure of Configurable Activity
Record Header
Main Content Area of Configurable Activity
Content Block of Configurable Deal
Bottom Part of the Record
Bottom Dropdown Menu
Click Reaction
Field Types
Set of Additional Content Blocks
Examples of Activity Configurations
Copied
Was the article helpful?
Yes
No
Previous
Structure of a Configurable Activity
Next
Record Title

---

## Record Header

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/header

Record Header | Bitrix24 REST API and Marketplace Applications
Parameters of the HeaderDto Object
Record Header
Parameters of the HeaderDto Object
TagDto Object
Parameters of the TagDto Object
Example Object
Continue Learning
Header of the
timeline record
HeaderDto
.
Parameters of the  Object
Parameters of the
HeaderDto
Object
Required parameters are marked with *
Field
Description
title
*
textWithTranslation
Record header
titleAction
ActionDto
Action upon clicking the record header
tags
TagDto[]
Associative array of objects describing tags
Object
TagDto
Object
Tag in the timeline record header.
Warning
No more than two tags are allowed.
Parameters of the  Object
Parameters of the
TagDto
Object
Required parameters are marked with *
Field
Description
title
*
textWithTranslation
Tag text
type
*
string
Tag type, for example
warning
. Defines its appearance
action
ActionDto
Action upon clicking the tag
scope
string
Scope
, for example
web
hideIfReadonly
boolean
Flag. Hides the tag if the user does not have edit access (default is
false
)
Possible values for the
type
field:
warning
- Yellow background
success
- Green background
failure
- Red background
primary
- Blue background
secondary
- Gray background
lavender
- Light purple
Example Object
Example Object
"header"
:
{
"title"
:
"Incoming Call"
,
"titleAction"
:
{
"type"
:
"redirect"
,
"uri"
:
"some.url"
}
,
"tags"
:
{
"status2"
:
{
"type"
:
"warning"
,
"title"
:
"not deciphered"
}
}
}
,
Continue Learning
Continue Learning
Structure of Configurable Activity
Icon
Main Content Area of Configurable Activity
Content Block of Configurable Deal
Bottom Part of the Record
Bottom Dropdown Menu
Click Reaction
Field Types
Set of Additional Content Blocks
Examples of Activity Configurations
Copied
Was the article helpful?
Yes
No
Previous
Icon
Next
Main Content Area

---

## Main Content Area of Configurable Activity

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/body

Main Content Area of Configurable Activity | Bitrix24 REST API and Marketplace Applications
Parameters of the BodyDto Object
Main Content Area of Configurable Activity
Parameters of the BodyDto Object
LogoDto Object
Parameters of the LogoDto Object
Example Object (without content blocks)
Continue Exploring
BodyDto
is the main content area of the
timeline entry
.
Parameters of the  Object
Parameters of the
BodyDto
Object
Required parameters are marked with *
Field
Description
logo
*
LogoDto
An object describing the logo of the timeline entry
blocks
ContentBlockDto
An associative array of objects describing content blocks
Warning
The array must contain at least one element and no more than 20 elements.
Object
LogoDto
Object
Logo of the timeline entry.
Parameters of the  Object
Parameters of the
LogoDto
Object
Required parameters are marked with *
Field
Description
code
*
string
Logo code, for example
call
. A list of available codes can be obtained using the
crm.timeline.logo.list
method
action
ActionDto
Action to be taken when the logo is clicked
Example Object (without content blocks)
Example Object (without content blocks)
{
"body"
:
{
"logo"
:
{
"code"
:
"call-incoming"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
}
,
"blocks"
:
{
}
}
,
}
Continue Exploring
Continue Exploring
Structure of Configurable Activity
Record Header
Icon
Content Block of Configurable Deal
Bottom Part of the Record
Bottom Dropdown Menu
Click Reaction
Field Types
Set of Additional Content Blocks
Examples of Activity Configurations
Copied
Was the article helpful?
Yes
No
Previous
Record Title
Next
Content Block of the Configurable Activity

---

## Content Block of Configurable Deal

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/content-block

Content Block of Configurable Deal | Bitrix24 REST API and Marketplace Applications
General Structure of the Block:
Content Block of Configurable Deal
General Structure of the Block:
Types of Content Blocks:
Text
Long Multiline Text
Link
Block with Title
Multiple Content Blocks in One Line
Deadline Selection
Continue Learning
Content blocks
ContentBlockDto
are the foundation of the content area of the timeline record. By combining these blocks, various interfaces can be flexibly assembled.
This structure is used when creating
configurable deals
and when enriching timeline records with
content blocks
.
General Structure of the Block:
General Structure of the Block:
{
"type"
:
"Block type"
,
"properties"
:
{
... some properties
,
varying for each specific block
}
}
Types of Content Blocks:
Types of Content Blocks:
Text
Text
The simplest block
type = text
, which displays some formatted text.
Parameters
Parameters
Required parameters are marked with *
Field
Description
value
*
textWithTranslation
Text to be displayed
multiline
boolean
Line break handling. If true,
\n
characters will be replaced with
<br>
. Default is
false
title
textWithTranslation
Title attribute
bold
boolean
Bold text. Default is
false
size
string
Text size. Can take values
xs
,
sm
,
md
(default is
md
)
color
string
Text color. Can take values
base_50
,
base_60
,
base_70
,
base_90
scope
string
Visibility scope
, for example
web
Example
Example
{
"icon"
:
{
"code"
:
"info"
}
,
"header"
:
{
"title"
:
"Information Message"
}
,
"body"
:
{
"logo"
:
{
"code"
:
"notification"
}
,
"blocks"
:
{
"text"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
}
}
}
}
}
Long Multiline Text
Long Multiline Text
The block
type = largeText
allows displaying long multiline texts that will automatically collapse to a preview.
Parameters
Parameters
Required parameters are marked with *
Field
Description
value
*
textWithTranslation
Text to be displayed
scope
string
Visibility scope
, for example
web
Example
Example
Long text collapsed under "Show more".
{
"icon"
:
{
"code"
:
"info"
}
,
"header"
:
{
"title"
:
"Information Message"
}
,
"body"
:
{
"logo"
:
{
"code"
:
"notification"
}
,
"blocks"
:
{
"text"
:
{
"type"
:
"largeText"
,
"properties"
:
{
"value"
:
"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."
}
}
}
}
}
Link
Link
The block
type = link
displays a link.
Parameters
Parameters
Required parameters are marked with *
Field
Description
text
*
textWithTranslation
Text to be displayed. HTML tags are not supported
action
*
ActionDto
Action upon clicking the link
bold
boolean
Bold text. Default is
false
scope
string
Visibility scope
, for example
web
Example
Example
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Open Deal"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
,
"bold"
:
true
}
}
Block with Title
Block with Title
The block
type = withTitle
displays a title-value pair. Another content block can be used as the value.
Parameters
Parameters
Required parameters are marked with *
Field
Description
title
*
textWithTranslation
Title text
block
*
ContentBlockDto
Content block that serves as the value. Blocks of types
text
,
link
,
deadline
are supported
inline
boolean
Display title and value in one line. Default is
false
scope
string
Visibility scope
, for example
web
Examples
Examples
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Title"
,
"block"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Some value"
}
}
}
}
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Title 2"
,
"block"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Open Deal"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
}
}
,
"inline"
:
true
}
}
Multiple Content Blocks in One Line
Multiple Content Blocks in One Line
The block
type = lineOfBlocks
displays several content blocks of type text or link in one line. This allows displaying text with different formatting mixed with links in a single line.
Parameters
Parameters
Required parameters are marked with *
Field
Description
blocks
*
ContentBlockDto[]
Associative array of content blocks. Blocks of types
text
,
link
,
deadline
are supported
scope
string
Visibility scope
, for example
web
Examples
Examples
{
"type"
:
"lineOfBlocks"
,
"properties"
:
{
"blocks"
:
{
"text"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Some text"
}
}
,
"link"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"link"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
}
}
,
"boldText"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"bold text"
,
"bold"
:
true
}
}
}
}
}
Deadline Selection
Deadline Selection
The block
type = deadline
displays the current deadline value with the ability to quickly change it. The block will not be shown if added to an incoming deal or a deal without a deadline.
Parameters
Parameters
Required parameters are marked with *
Field
Description
readonly
boolean
Permission to change the deadline. Default is
false
. If the user does not have access to modify the entity to which the deal relates, or if the deal is completed, then
readonly = true
regardless of the settings provided
scope
string
Visibility scope
, for example
web
Examples
Examples
{
"type"
:
"deadline"
,
"properties"
:
{
"readonly"
:
false
}
}
Continue Learning
Continue Learning
Additional Content Blocks
Additional Content Blocks
Structure of Configurable Activity
Icon
Record Header
Main Content Area of Configurable Activity
Bottom Part of the Record
Bottom Dropdown Menu
Click Reaction
Field Types
Set of Additional Content Blocks
Examples of Activity Configurations
Copied
Was the article helpful?
Yes
No
Previous
Main Content Area
Next
Bottom Part of the Record

---

## Bottom Part of the Record

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/footer

Bottom Part of the Record | Bitrix24 REST API and Marketplace Applications
Parameters of the FooterDto Object
Bottom Part of the Record
Parameters of the FooterDto Object
FooterButtonDto
Parameters of the FooterButtonDto Object
Example
FooterMenuDto
Parameters of the FooterMenuDto Object
Example
Continue Learning
The bottom part of the
timeline record
with the
FooterDto
action block.
Parameters of the  Object
Parameters of the
FooterDto
Object
Required parameters are marked with *
Field
Description
buttons
FooterButtonDto
An array of objects describing action buttons. No more than two buttons are allowed
menu
FooterMenuDto
Bottom menu
FooterButtonDto
FooterButtonDto
A button in the bottom part of the timeline record.
Parameters of the  Object
Parameters of the
FooterButtonDto
Object
Required parameters are marked with *
Field
Description
title
*
textWithTranslation
Button text
type
*
string
Button type. Defines its appearance, e.g.,
primary
action
*
ActionDto
Action to be performed when the button is clicked
scope
string
Scope
, e.g.,
web
hideIfReadonly
boolean
Flag. Hides the tag if the user does not have edit access (default is
false
)
Possible values for the
type
field:
primary
- Blue button background
secondary
- White button background
Example
Example
{
"title"
:
"Open deal"
,
"type"
:
"primary"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
,
"scope"
:
"web"
,
"hideIfReadonly"
:
true
}
FooterMenuDto
FooterMenuDto
Dropdown menu in the bottom part of the timeline record.
Parameters of the  Object
Parameters of the
FooterMenuDto
Object
Field
Description
showPinItem
boolean
Show the "Pin" menu item. The menu item will not be shown if added to an incomplete activity. Default is
true
showPostponeItem
boolean
Show the "Postpone" menu item. The menu item will not be shown if added to an incoming activity, an activity without a deadline, or a completed activity. Default is
true
.
showDeleteItem
boolean
Show the "Delete" menu item. Default is
true
items
MenuItemDto
Associative array of objects describing dropdown menu items
Example
Example
{
"showPostponeItem"
:
"false"
,
"showDeleteItem"
:
"false"
,
"items"
:
{
"confirm"
:
{
"title"
:
"Confirm request"
,
"action"
:
{
"type"
:
"restEvent"
,
"id"
:
"confirm"
,
"animationType"
:
"loader"
}
}
,
"decline"
:
{
"title"
:
"Decline request"
,
"action"
:
{
"type"
:
"restEvent"
,
"id"
:
"decline"
,
"animationType"
:
"loader"
}
}
}
}
Continue Learning
Continue Learning
Structure of Configurable Activity
Icon
Main Content Area of Configurable Activity
Content Block of Configurable Deal
Record Header
Bottom Dropdown Menu
Click Reaction
Field Types
Set of Additional Content Blocks
Examples of Activity Configurations
Copied
Was the article helpful?
Yes
No
Previous
Content Block of the Configurable Activity
Next
Dropdown Menu of the Bottom Part

---

## Bottom Dropdown Menu

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/menu-item

Bottom Dropdown Menu | Bitrix24 REST API and Marketplace Applications
Parameters of the MenuItemDto Object
Bottom Dropdown Menu
Parameters of the MenuItemDto Object
Example
Continue Exploring
Items in the bottom dropdown menu of the
timeline entry
MenuItemDto
.
Parameters of the  Object
Parameters of the
MenuItemDto
Object
Required parameters are marked with *
Field
Description
title
*
textWithTranslation
Button text
action
*
ActionDto
Action to be performed when the button is pressed
scope
string
Scope
, for example
web
hideIfReadonly
boolean
Flag. Hides the tag if the user does not have edit access, default is
false
Example
Example
{
"title"
:
"Confirm Process"
,
"action"
:
{
"type"
:
"restEvent"
,
"id"
:
"confirmProcess"
,
"animationType"
:
"loader"
}
,
"scope"
:
"web"
,
"hideIfReadonly"
:
true
}
Continue Exploring
Continue Exploring
Structure of Configurable Activity
Icon
Main Content Area of Configurable Activity
Content Block of Configurable Deal
Record Header
Bottom Part of the Record
Click Reaction
Field Types
Set of Additional Content Blocks
Examples of Activity Configurations
Copied
Was the article helpful?
Yes
No
Previous
Bottom Part of the Record
Next
Click Reaction

---

## Click Reaction

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/action

Click Reaction | Bitrix24 REST API and Marketplace Applications
Link Navigation
Click Reaction
Link Navigation
Parameters
Example
Event
Parameters
Example
Opening the Application Slider
Parameters
Example
ActionSliderParamsDto
Continue Exploring
ActionDto
— the action defines the reaction to a click on a specific timeline record element. There are several different types of actions, each with its own format.
Link Navigation
Link Navigation
If a relative link to standard Bitrix24 objects that support opening in a slider is used, the slider will be displayed. Otherwise, it will be a regular link navigation.
Parameters
Parameters
Required parameters are marked with *
Field
Description
type
*
const
Value
redirect
uri
string
Valid URI link, for example
https://example.com
or
/crm/deal/details/1/
Example
Example
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/1/"
}
Event
Event
Calling the action will generate the event
onCrmTimelineItemAction
. When the event occurs, handlers will be triggered only for the application that created this timeline record. The context will always be passed to the handler:
id
- event identifier,
entityTypeId
- identifier of the object type to which the deal is linked,
entityId
- identifier of the element of this object,
activityId
- identifier of the deal,
userId
- identifier of the user who triggered the action.
Parameters
Parameters
Required parameters are marked with *
Field
Description
type
*
const
Value
restEvent
id
*
string
Event identifier. Any value can be specified, for example
resetButtonClick
actionParams
array
Array of arbitrary format, the data from which will be passed to the event handler
animationType
string
Animation that will be shown during event processing, for example
disable
In some cases, sending the event implies that the handler of this event should change the appearance of the record in the timeline. For example, adding new blocks or changing the set of buttons.
To ensure the user sees the update, the
animationType
parameter can be used. If
animationType
is set to
loader
— the timeline record will be blocked and a loader will appear on top of it. The blocking will last until the record is updated via
crm.activity.configurable.update
.
If the action is triggered by clicking a button at the bottom of the timeline and
animationType
is set to
disable
— this button will be blocked until the record is updated via
crm.activity.configurable.update
.
Example
Example
{
"type"
:
"restEvent"
,
"id"
:
"resetButtonClick"
,
"actionParams"
:
{
"myId"
:
123
,
"someImportant"
:
"qwerty"
}
,
"animationType"
:
"disable"
}
The action is assigned to a button. Clicking it will trigger the event handler
onCrmTimelineItemAction
, registered by the application that created the timeline record.
The standard parameters
id=resetButtonClick
,
entityTypeId
,
entityId
,
activityId
,
userId
and the parameters defined by the developer —
myId=123
and
someImportant=qwerty
will be passed to the handler. The button will be blocked from the moment it is clicked until the timeline record is updated via
crm.activity.configurable.update
.
Opening the Application Slider
Opening the Application Slider
Warning
The action is not supported in the mobile application.
Calling the action will open the slider of the application that created the timeline record. The context will be passed to the slider:
entityTypeId
- identifier of the object type to which the deal is linked,
entityId
- identifier of the element of this object,
activityId
- identifier of the deal.
Parameters
Parameters
Required parameters are marked with *
Field
Description
type
*
const
Value
openRestApp
actionParams
array
Array of arbitrary format, the data from which will be passed to the event handler
sliderParams
ActionSliderParamsDto
Options with which the slider is opened
Example
Example
{
"type"
:
"openRestApp"
,
"actionParams"
:
{
"myId"
:
123
,
"someImportant"
:
"qwerty"
}
,
"sliderParams"
:
{
"title"
:
"This is the application slider title"
,
"width"
:
700
}
}
ActionSliderParamsDto
ActionSliderParamsDto
Parameters for Opening the Application Slider
Parameters for Opening the Application Slider
Field
Description
Additional
width
int
Width of the slider,
px
Cannot be used simultaneously with
leftBoundary
leftBoundary
int
Slider spans the full width of the browser window with a left margin,
px
Cannot be used simultaneously with
width
title
string
Text of the browser window title when opening the slider
Continue Exploring
Continue Exploring
Structure of Configurable Activity
Icon
Record Header
Main Content Area of Configurable Activity
Content Block of Configurable Deal
Bottom Part of the Record
Bottom Dropdown Menu
Field Types
Set of Additional Content Blocks
Examples of Activity Configurations
Copied
Was the article helpful?
Yes
No
Previous
Dropdown Menu of the Bottom Part
Next
Field Types

---

## Field Types

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/field-types

Field Types | Bitrix24 REST API and Marketplace Applications
textWithTranslation
Field Types
textWithTranslation
Scope
Available field types for configuring
your types of activities
.
textWithTranslation
textWithTranslation
Text with translation support.
Fields of type
textWithTranslation
support multilingualism. In its simplest form, you just need to pass a string into it. This string will be used as the value.
If support for different interface languages is required, a non-empty array can be passed as the field value, where the keys are the language codes and the values are the text in that language, for example:
{
"de"
:
"Speichern"
,
"en"
:
"Save"
}
If a translation for the current language is not found, English will be used. If the translation in English is also not found, the first element of the array will be used.
Scope
Scope
Visibility. Where to display the block.
Some timeline entry blocks have a
scope
parameter. If it is filled, the visibility of the corresponding block will be limited to a specific type of device.
Possible values:
Not filled
- the block will be shown everywhere
web
- the block will be shown only in the browser
mobile
- the block will be shown only in the mobile application
Copied
Was the article helpful?
Yes
No
Previous
Click Reaction
Next
Set of Additional Content Blocks

---

## Bitrix24 REST API and Marketplace Applications

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure-app-layout-dto

Bitrix24 REST API and Marketplace Applications
The information below may help:
Find the REST API method
​
Create your local application
​
Publish your application at the Bitrix24 Market
​

---

## Examples of Activity Configurations

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/structure/examples

Examples of Activity Configurations | Bitrix24 REST API and Marketplace Applications
Text
Examples of Activity Configurations
Text
Long Text
Fields
Action Types
Multilingual Support
Code examples for
custom activity types
and how they will look.
Text
Text
{
"icon"
:
{
"code"
:
"info"
}
,
"header"
:
{
"title"
:
"Information Message"
}
,
"body"
:
{
"logo"
:
{
"code"
:
"notification"
}
,
"blocks"
:
{
"text"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
}
}
}
}
}
Long Text
Long Text
Long text hidden under "Show more".
{
"icon"
:
{
"code"
:
"info"
}
,
"header"
:
{
"title"
:
"Information Message"
}
,
"body"
:
{
"logo"
:
{
"code"
:
"notification"
}
,
"blocks"
:
{
"text"
:
{
"type"
:
"largeText"
,
"properties"
:
{
"value"
:
"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."
}
}
}
}
}
Fields
Fields
Fields with name-value pairs, changing the deadline.
{
"icon"
:
{
"code"
:
"info"
}
,
"header"
:
{
"title"
:
"Information Message"
}
,
"body"
:
{
"logo"
:
{
"code"
:
"document"
}
,
"blocks"
:
{
"deadline"
:
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Deadline"
,
"inline"
:
true
,
"block"
:
{
"type"
:
"deadline"
}
}
}
,
"client"
:
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Client"
,
"inline"
:
true
,
"block"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Ltd. Horns and Hooves"
}
}
}
}
,
"manager"
:
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Manager"
,
"inline"
:
true
,
"block"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Sergey Vostrikov"
,
"bold"
:
true
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/company/personal/user/1/"
}
}
}
}
}
,
"description"
:
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Additional Information in Large Volume"
,
"inline"
:
false
,
"block"
:
{
"type"
:
"text"
,
"properties"
:
{
"multiline"
:
true
,
"value"
:
"Arrive no earlier than noon. Entrance from the yard, gate password 555. Go up to the 5th floor, ask for Ivan Nikolaevich. Payment in cash, change from $5000."
}
}
}
}
}
}
}
Action Types
Action Types
Various types of actions.
{
"icon"
:
{
"code"
:
"document"
}
,
"header"
:
{
"title"
:
"Example of Different Action Types"
,
"tags"
:
{
"tag1"
:
{
"type"
:
"warning"
,
"title"
:
"Open Application"
,
"action"
:
{
"type"
:
"openRestApp"
,
"actionParams"
:
{
"myId"
:
123
}
}
}
,
"tag2"
:
{
"type"
:
"primary"
,
"title"
:
"Open Application"
,
"action"
:
{
"type"
:
"openRestApp"
,
"actionParams"
:
{
"someImportant"
:
"qwerty"
}
}
}
}
}
,
"body"
:
{
"logo"
:
{
"code"
:
"document"
}
,
"blocks"
:
{
"link1"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Open Internal Link"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/1/"
}
}
}
,
"link2"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Open External Link"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"https://bitrix24.com"
}
}
}
}
}
,
"footer"
:
{
"buttons"
:
{
"button1"
:
{
"title"
:
"REST Event"
,
"action"
:
{
"type"
:
"restEvent"
,
"id"
:
"confirm"
,
"animationType"
:
"loader"
,
"actionParams"
:
{
"blockId"
:
"time"
}
}
,
"type"
:
"primary"
}
,
"button2"
:
{
"title"
:
"REST Event"
,
"action"
:
{
"type"
:
"restEvent"
,
"id"
:
"confirm"
,
"animationType"
:
"disable"
,
"actionParams"
:
{
"blockId"
:
"time"
}
}
,
"type"
:
"primary"
}
}
}
}
Multilingual Support
Multilingual Support
Support for multilingualism.
{
"icon"
:
{
"code"
:
"info"
}
,
"header"
:
{
"title"
:
{
"de"
:
"Information"
,
"en"
:
"Information"
}
,
"tags"
:
{
"tag"
:
{
"type"
:
"warning"
,
"title"
:
{
"de"
:
"Achtung"
,
"en"
:
"Warning"
}
}
}
}
,
"body"
:
{
"logo"
:
{
"code"
:
"notification"
}
,
"blocks"
:
{
"text"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
{
"de"
:
"Dieser Text wird in verschiedenen Sprachen unterschiedlich angezeigt"
,
"en"
:
"A text"
}
}
}
}
}
,
"footer"
:
{
"buttons"
:
{
"button1"
:
{
"title"
:
{
"de"
:
"Drück mich"
,
"en"
:
"Push me"
}
,
"type"
:
"primary"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"https://bitrix24.com"
}
}
}
}
}
Result in English:
Was the article helpful?
Yes
No
Previous
Set of Additional Content Blocks
Next
About Badges

---

## About Configurable Activity Badges

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/badges/index

About Configurable Activity Badges | Bitrix24 REST API and Marketplace Applications
About Configurable Activity Badges
About Configurable Activity Badges
Badge Record Fields
Badge Type
Additional
Quick navigation:
all methods
A
badge
is an icon on the card of a CRM entity in the kanban. The badge helps highlight entities that require attention. If multiple badges are added to an entity, only the most recently added badge will be displayed.
Badges can be added for a
configurable activity
in the
badgeCode
field. The badge will be displayed on the kanban of the object to which the activity is linked until the activity is closed.
Badge Record Fields
Badge Record Fields
Field
Description
code
string
Badge code, for example
missedCall
title
string
|
array
Title of the badge. Can be a string or an array of strings for different languages
value
string
|
array
Value of the badge. Can be a string or an array of strings for different languages
type
string
Badge type
If
title
or
value
contains an array, the keys should be language codes, and the values should be text in those languages, for example:
{
"de"
:
"Achtung"
,
"en"
:
"Alarm"
}
If a translation for the current language is not found, the English version will be used. If the English translation is also not found, the first element of the array will be used.
Badge Type
Badge Type
In Bitrix24, there are several standard badges for different scenarios. The badge type can take the following values:
success
— Green background
failure
— Red background
warning
— Yellow background
primary
— Blue background
secondary
— Gray background
Overview of Methods
Scope:
crm
Who can execute the method: any user
Method
Description
crm.activity.badge.add
Adds a new badge
crm.activity.badge.get
Retrieves information about a badge
crm.activity.badge.list
Retrieves a list of badges
crm.activity.badge.delete
Deletes a badge by code
Additional
Additional
Add Configurable CRM Activity `crm.activity.configurable.add`
Update Configurable Activity crm.activity.configurable.update
Get Configurable Activity by ID crm.activity.configurable.get
Copied
Was the article helpful?
Yes
No
Previous
Examples of Activity Configurations
Next
Add Badge

---

## Add Badge crm.activity.badge.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/badges/crm-activity-badge-add

Add Badge crm.activity.badge.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Badge crm.activity.badge.add
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: users with administrative access to the crm section
The method
crm.activity.badge.add
adds a new badge for a configurable activity.
Method Parameters
Method Parameters
Required parameters are marked with *
Field
Description
code
*
string
Badge code, for example
missedCall
title
*
string
|
array
Badge title. Can be a string or an array of strings for different languages
value
*
string
|
array
Badge value. Can be a string or an array of strings for different languages
type
*
string
Badge type
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"code":"missedCall","title":"Call Status","value":"Missed","type":"failure","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.badge.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.badge.add'
,
{
code
:
'missedCall'
,
title
:
'Call Status'
,
value
:
'Missed'
,
type
:
'failure'
}
);
const
result = response.
getData
().
result
;
if
(result.
error
())
console
.
error
(result.
error
());
else
console
.
dir
(result);
}
catch
( error )
{
console
.
error
(
'Error:'
, error);
}
try
{
$response
=
$b24Service
->core
->
call
(
'crm.activity.badge.add'
,
[
'code'
=>
'missedCall'
,
'title'
=>
'Call Status'
,
'value'
=>
'Missed'
,
'type'
=>
'failure'
]
);
$result
=
$response
->
getResponseData
()
->
getResult
();
if
(
$result
->
error
()) {
error_log
(
$result
->
error
());
}
else
{
echo
'Success: '
.
print_r
(
$result
->
data
(),
true
);
}
}
catch
(
Throwable
$e
) {
error_log
(
$e
->
getMessage
());
echo
'Error adding activity badge: '
.
$e
->
getMessage
();
}
BX24
.
callMethod
(
"crm.activity.badge.add"
,
{
code
:
'missedCall'
,
title
:
'Call Status'
,
value
:
'Missed'
,
type
:
'failure'
},
result
=>
{
if
(result.
error
())
console
.
error
(result.
error
());
else
console
.
dir
(result.
data
());
}
);
require_once
(
'crest.php'
);
$result
=
CRest
::
call
(
'crm.activity.badge.add'
,
[
'code'
=>
'missedCall'
,
'title'
=>
'Call Status'
,
'value'
=>
'Missed'
,
'type'
=>
'failure'
]
);
echo
'<PRE>'
;
print_r
(
$result
);
echo
'</PRE>'
;
Response Handling
Response Handling
HTTP Status:
200
{
"result"
:
{
"badge"
:
{
"code"
:
"missedCall"
,
"title"
:
"Call Status"
,
"value"
:
"Missed"
,
"type"
:
"failure"
}
}
,
"time"
:
{
"start"
:
1724068028.331234
,
"finish"
:
1724068028.726591
,
"duration"
:
0.3953571319580078
,
"processing"
:
0.13033390045166016
,
"date_start"
:
"2025-01-21T13:47:08+02:00"
,
"date_finish"
:
"2025-01-21T13:47:08+02:00"
,
"operating"
:
0
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response containing information about the added badge in case of success. In case of failure, it will return
null
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Not found."
}
Name
type
Description
error
string
String error code. It may consist of digits, Latin letters, and underscores
error_description
error_description
Textual description of the error. The description is not intended to be shown to the end user in its raw form
Copied
Possible Error Codes
Possible Error Codes
Code
Description
ACCESS_DENIED
Insufficient permissions to perform the operation
REQUIRED_ARG_MISSING
Required fields are not filled
Statuses and System Error Codes
Statuses and System Error Codes
HTTP Status:
20x
,
40x
,
50x
The errors described below may occur when calling any method.
Status
Code
Error Message
Description
500
INTERNAL_SERVER_ERROR
Internal server error
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
500
ERROR_UNEXPECTED_ANSWER
Server returned an unexpected response
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
503
QUERY_LIMIT_EXCEEDED
Too many requests
The
request intensity limit
has been exceeded
405
ERROR_BATCH_METHOD_NOT_ALLOWED
Method is not allowed for batch usage
The current method is not allowed to be called using
batch
400
ERROR_BATCH_LENGTH_EXCEEDED
Max batch length exceeded
The maximum length of parameters passed to the
batch
method has been exceeded
401
NO_AUTH_FOUND
Wrong authorization data
Invalid
access token
or
webhook code
400
INVALID_REQUEST
Https required
The methods must be called using the HTTPS protocol
503
OVERLOAD_LIMIT
REST API is blocked due to overload
The REST API is blocked due to overload. This is a manual individual block, to remove it you need to contact
Bitrix24 technical support
403
ACCESS_DENIED
REST API is available only on commercial plans
The REST API is available only on commercial plans
403
INVALID_CREDENTIALS
Invalid request credentials
The user whose
access token
or
webhook
was used to call the method lacks permissions
404
ERROR_MANIFEST_IS_NOT_AVAILABLE
Manifest is not available
The manifest is not available
403
insufficient_scope
The request requires higher privileges than provided by the webhook token
The request requires higher privileges than those provided by the
webhook
token
401
expired_token
The access token provided has expired
The provided
access token
has expired
403
user_access_error
The user does not have access to the application
The user does not have access to the application. This means that the application is installed, but the account administrator has allowed access to this application only for specific users
500
PORTAL_DELETED
Portal was deleted
The public part of the site is closed. To open the public part of the site on an on-premise installation, disable the option "Temporary closure of the public part of the site". Path to the setting:
Desktop > Settings > Product Settings > Module Settings > Main Module > Temporary closure of the public part of the site
Copied
Continue Learning
Continue Learning
Get Badge Information by Code crm.activity.badge.get
Get the list of badges crm.activity.badge.list
Delete Badge by Code crm.activity.badge.delete
Copied
Was the article helpful?
Yes
No
Previous
About Badges
Next
Get Badge List

---

## Get the list of badges crm.activity.badge.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/badges/crm-activity-badge-list

Get the list of badges crm.activity.badge.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of badges crm.activity.badge.list
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method
crm.activity.badge.list
retrieves a list of available badges. It will return an array containing a list of all registered badges. Each element of the array contains
badge fields
.
Method Parameters
Method Parameters
No parameters.
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.badge.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.activity.badge.list'
,
{},
(
progress
) =>
{
console
.
log
(
'Progress:'
, progress) }
)
const
items = response.
getData
() || []
for
(
const
entity
of
items) {
console
.
log
(
'Entity:'
, entity) }
}
catch
(error) {
console
.
error
(
'Request failed'
, error)
}
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.activity.badge.list'
, {},
'ID'
)
for
await
(
const
page
of
generator) {
for
(
const
entity
of
page) {
console
.
log
(
'Entity:'
, entity) }
}
}
catch
(error) {
console
.
error
(
'Request failed'
, error)
}
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.badge.list'
, {},
0
)
const
result = response.
getData
().
result
|| []
for
(
const
entity
of
result) {
console
.
log
(
'Entity:'
, entity) }
}
catch
(error) {
console
.
error
(
'Request failed'
, error)
}
try
{
$response
=
$b24Service
->core
->
call
(
'crm.activity.badge.list'
,
[]
);
$result
=
$response
->
getResponseData
()
->
getResult
();
if
(
$result
->
error
()) {
error_log
(
$result
->
error
());
}
else
{
echo
'Success: '
.
print_r
(
$result
->
data
(),
true
);
}
}
catch
(
Throwable
$e
) {
error_log
(
$e
->
getMessage
());
echo
'Error fetching activity badges: '
.
$e
->
getMessage
();
}
BX24
.
callMethod
(
"crm.activity.badge.list"
,
{
},
result
=>
{
if
(result.
error
())
console
.
error
(result.
error
());
else
console
.
dir
(result.
data
());
}
);
require_once
(
'crest.php'
);
$result
=
CRest
::
call
(
'crm.activity.badge.list'
,
[]
);
echo
'<PRE>'
;
print_r
(
$result
);
echo
'</PRE>'
;
Response Handling
Response Handling
HTTP status:
200
{
"result"
:
{
"badges"
:
[
{
"code"
:
"missedCall"
,
"title"
:
"Call Status"
,
"value"
:
"Missed"
,
"type"
:
"failure"
}
]
}
,
"time"
:
{
"start"
:
1724068028.331234
,
"finish"
:
1724068028.726591
,
"duration"
:
0.3953571319580078
,
"processing"
:
0.13033390045166016
,
"date_start"
:
"2025-01-21T13:47:08+02:00"
,
"date_finish"
:
"2025-01-21T13:47:08+02:00"
,
"operating"
:
0
}
}
Returned Data
Returned Data
Name
type
Description
result
array
The root element of the response containing an array, each element of which carries information about the badge
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Not found."
}
Name
type
Description
error
string
String error code. It may consist of digits, Latin letters, and underscores
error_description
error_description
Textual description of the error. The description is not intended to be shown to the end user in its raw form
Copied
Possible Error Codes
Possible Error Codes
Code
Description
ACCESS_DENIED
Insufficient permissions to perform the operation
Statuses and System Error Codes
Statuses and System Error Codes
HTTP Status:
20x
,
40x
,
50x
The errors described below may occur when calling any method.
Status
Code
Error Message
Description
500
INTERNAL_SERVER_ERROR
Internal server error
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
500
ERROR_UNEXPECTED_ANSWER
Server returned an unexpected response
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
503
QUERY_LIMIT_EXCEEDED
Too many requests
The
request intensity limit
has been exceeded
405
ERROR_BATCH_METHOD_NOT_ALLOWED
Method is not allowed for batch usage
The current method is not allowed to be called using
batch
400
ERROR_BATCH_LENGTH_EXCEEDED
Max batch length exceeded
The maximum length of parameters passed to the
batch
method has been exceeded
401
NO_AUTH_FOUND
Wrong authorization data
Invalid
access token
or
webhook code
400
INVALID_REQUEST
Https required
The methods must be called using the HTTPS protocol
503
OVERLOAD_LIMIT
REST API is blocked due to overload
The REST API is blocked due to overload. This is a manual individual block, to remove it you need to contact
Bitrix24 technical support
403
ACCESS_DENIED
REST API is available only on commercial plans
The REST API is available only on commercial plans
403
INVALID_CREDENTIALS
Invalid request credentials
The user whose
access token
or
webhook
was used to call the method lacks permissions
404
ERROR_MANIFEST_IS_NOT_AVAILABLE
Manifest is not available
The manifest is not available
403
insufficient_scope
The request requires higher privileges than provided by the webhook token
The request requires higher privileges than those provided by the
webhook
token
401
expired_token
The access token provided has expired
The provided
access token
has expired
403
user_access_error
The user does not have access to the application
The user does not have access to the application. This means that the application is installed, but the account administrator has allowed access to this application only for specific users
500
PORTAL_DELETED
Portal was deleted
The public part of the site is closed. To open the public part of the site on an on-premise installation, disable the option "Temporary closure of the public part of the site". Path to the setting:
Desktop > Settings > Product Settings > Module Settings > Main Module > Temporary closure of the public part of the site
Copied
Continue Learning
Continue Learning
Add Badge crm.activity.badge.add
Get Badge Information by Code crm.activity.badge.get
Delete Badge by Code crm.activity.badge.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Badge
Next
Get Badge Information by Code

---

## Get Badge Information by Code crm.activity.badge.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/badges/crm-activity-badge-get

Get Badge Information by Code crm.activity.badge.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Badge Information by Code crm.activity.badge.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method
crm.activity.badge.get
will return an array containing
badge fields
.
Method Parameters
Method Parameters
Required parameters are marked with *
Field
Description
code
*
string
Badge code, for example
missedCall
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"code":"missedCall","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.badge.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.badge.get'
,
{
code
:
'missedCall'
,
}
);
const
result = response.
getData
().
result
;
if
(result.
error
())
{
console
.
error
(result.
error
());
}
else
{
console
.
dir
(result);
}
}
catch
( error )
{
console
.
error
(
'Error:'
, error);
}
try
{
$response
=
$b24Service
->core
->
call
(
'crm.activity.badge.get'
,
[
'code'
=>
'missedCall'
,
]
);
$result
=
$response
->
getResponseData
()
->
getResult
();
if
(
$result
->
error
()) {
error_log
(
$result
->
error
());
}
else
{
echo
'Success: '
.
print_r
(
$result
->
data
(),
true
);
}
}
catch
(
Throwable
$e
) {
error_log
(
$e
->
getMessage
());
echo
'Error getting activity badge: '
.
$e
->
getMessage
();
}
BX24
.
callMethod
(
"crm.activity.badge.get"
,
{
code
:
'missedCall'
,
},
result
=>
{
if
(result.
error
())
console
.
error
(result.
error
());
else
console
.
dir
(result.
data
());
}
);
require_once
(
'crest.php'
);
$result
=
CRest
::
call
(
'crm.activity.badge.get'
,
[
'code'
=>
'missedCall'
]
);
echo
'<PRE>'
;
print_r
(
$result
);
echo
'</PRE>'
;
Response Handling
Response Handling
HTTP status:
200
{
"result"
:
{
"badge"
:
{
"code"
:
"missedCall"
,
"title"
:
"Call Status"
,
"value"
:
"Missed"
,
"type"
:
"failure"
}
}
,
"time"
:
{
"start"
:
1724068028.331234
,
"finish"
:
1724068028.726591
,
"duration"
:
0.3953571319580078
,
"processing"
:
0.13033390045166016
,
"date_start"
:
"2025-01-21T13:47:08+02:00"
,
"date_finish"
:
"2025-01-21T13:47:08+02:00"
,
"operating"
:
0
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response containing badge information in case of success. In case of failure, it will return
null
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Not found."
}
Name
type
Description
error
string
String error code. It may consist of digits, Latin letters, and underscores
error_description
error_description
Textual description of the error. The description is not intended to be shown to the end user in its raw form
Copied
Possible Error Codes
Possible Error Codes
Code
Description
ACCESS_DENIED
Insufficient permissions to perform the operation
NOT_FOUND
Badge with the specified code not found
Statuses and System Error Codes
Statuses and System Error Codes
HTTP Status:
20x
,
40x
,
50x
The errors described below may occur when calling any method.
Status
Code
Error Message
Description
500
INTERNAL_SERVER_ERROR
Internal server error
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
500
ERROR_UNEXPECTED_ANSWER
Server returned an unexpected response
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
503
QUERY_LIMIT_EXCEEDED
Too many requests
The
request intensity limit
has been exceeded
405
ERROR_BATCH_METHOD_NOT_ALLOWED
Method is not allowed for batch usage
The current method is not allowed to be called using
batch
400
ERROR_BATCH_LENGTH_EXCEEDED
Max batch length exceeded
The maximum length of parameters passed to the
batch
method has been exceeded
401
NO_AUTH_FOUND
Wrong authorization data
Invalid
access token
or
webhook code
400
INVALID_REQUEST
Https required
The methods must be called using the HTTPS protocol
503
OVERLOAD_LIMIT
REST API is blocked due to overload
The REST API is blocked due to overload. This is a manual individual block, to remove it you need to contact
Bitrix24 technical support
403
ACCESS_DENIED
REST API is available only on commercial plans
The REST API is available only on commercial plans
403
INVALID_CREDENTIALS
Invalid request credentials
The user whose
access token
or
webhook
was used to call the method lacks permissions
404
ERROR_MANIFEST_IS_NOT_AVAILABLE
Manifest is not available
The manifest is not available
403
insufficient_scope
The request requires higher privileges than provided by the webhook token
The request requires higher privileges than those provided by the
webhook
token
401
expired_token
The access token provided has expired
The provided
access token
has expired
403
user_access_error
The user does not have access to the application
The user does not have access to the application. This means that the application is installed, but the account administrator has allowed access to this application only for specific users
500
PORTAL_DELETED
Portal was deleted
The public part of the site is closed. To open the public part of the site on an on-premise installation, disable the option "Temporary closure of the public part of the site". Path to the setting:
Desktop > Settings > Product Settings > Module Settings > Main Module > Temporary closure of the public part of the site
Copied
Continue Learning
Continue Learning
Add Badge crm.activity.badge.add
Get the list of badges crm.activity.badge.list
Delete Badge by Code crm.activity.badge.delete
Copied
Was the article helpful?
Yes
No
Previous
Get Badge List
Next
Delete Badge

---

## Delete Badge by Code crm.activity.badge.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/badges/crm-activity-badge-delete

Delete Badge by Code crm.activity.badge.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Badge by Code crm.activity.badge.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: users with administrative access to the crm section
The method
crm.activity.badge.delete
removes a badge.
Method Parameters
Method Parameters
Required parameters are marked with *
Field
Description
code
*
string
Badge code, for example
missedCall
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"code":"missedCall","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.badge.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.activity.badge.delete"
,
{
code
:
'missedCall'
,
}
);
const
result = response.
getData
().
result
;
if
(result.
error
())
console
.
error
(result.
error
());
else
console
.
dir
(result);
}
catch
( error )
{
console
.
error
(
'Error:'
, error);
}
try
{
$response
=
$b24Service
->core
->
call
(
'crm.activity.badge.delete'
,
[
'code'
=>
'missedCall'
,
]
);
$result
=
$response
->
getResponseData
()
->
getResult
();
if
(
$result
->
error
()) {
error_log
(
$result
->
error
());
}
else
{
echo
'Success: '
.
print_r
(
$result
->
data
(),
true
);
}
}
catch
(
Throwable
$e
) {
error_log
(
$e
->
getMessage
());
echo
'Error deleting activity badge: '
.
$e
->
getMessage
();
}
BX24
.
callMethod
(
"crm.activity.badge.delete"
,
{
code
:
'missedCall'
,
},
result
=>
{
if
(result.
error
())
console
.
error
(result.
error
());
else
console
.
dir
(result.
data
());
}
);
require_once
(
'crest.php'
);
$result
=
CRest
::
call
(
'crm.activity.badge.delete'
,
[
'code'
=>
'missedCall'
]
);
echo
'<PRE>'
;
print_r
(
$result
);
echo
'</PRE>'
;
Response Handling
Response Handling
HTTP status:
200
{
"result"
:
true
,
"time"
:
{
"start"
:
1724068028.331234
,
"finish"
:
1724068028.726591
,
"duration"
:
0.3953571319580078
,
"processing"
:
0.13033390045166016
,
"date_start"
:
"2025-01-21T13:47:08+02:00"
,
"date_finish"
:
"2025-01-21T13:47:08+02:00"
,
"operating"
:
0
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Root element of the response. Contains:
true
— on success
null
— on failure (an error occurred)
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Not found."
}
Name
type
Description
error
string
String error code. It may consist of digits, Latin letters, and underscores
error_description
error_description
Textual description of the error. The description is not intended to be shown to the end user in its raw form
Copied
Possible Error Codes
Possible Error Codes
Code
Description
ACCESS_DENIED
Insufficient permissions to perform the operation
NOT_FOUND
Badge with the specified code not found
Statuses and System Error Codes
Statuses and System Error Codes
HTTP Status:
20x
,
40x
,
50x
The errors described below may occur when calling any method.
Status
Code
Error Message
Description
500
INTERNAL_SERVER_ERROR
Internal server error
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
500
ERROR_UNEXPECTED_ANSWER
Server returned an unexpected response
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
503
QUERY_LIMIT_EXCEEDED
Too many requests
The
request intensity limit
has been exceeded
405
ERROR_BATCH_METHOD_NOT_ALLOWED
Method is not allowed for batch usage
The current method is not allowed to be called using
batch
400
ERROR_BATCH_LENGTH_EXCEEDED
Max batch length exceeded
The maximum length of parameters passed to the
batch
method has been exceeded
401
NO_AUTH_FOUND
Wrong authorization data
Invalid
access token
or
webhook code
400
INVALID_REQUEST
Https required
The methods must be called using the HTTPS protocol
503
OVERLOAD_LIMIT
REST API is blocked due to overload
The REST API is blocked due to overload. This is a manual individual block, to remove it you need to contact
Bitrix24 technical support
403
ACCESS_DENIED
REST API is available only on commercial plans
The REST API is available only on commercial plans
403
INVALID_CREDENTIALS
Invalid request credentials
The user whose
access token
or
webhook
was used to call the method lacks permissions
404
ERROR_MANIFEST_IS_NOT_AVAILABLE
Manifest is not available
The manifest is not available
403
insufficient_scope
The request requires higher privileges than provided by the webhook token
The request requires higher privileges than those provided by the
webhook
token
401
expired_token
The access token provided has expired
The provided
access token
has expired
403
user_access_error
The user does not have access to the application
The user does not have access to the application. This means that the application is installed, but the account administrator has allowed access to this application only for specific users
500
PORTAL_DELETED
Portal was deleted
The public part of the site is closed. To open the public part of the site on an on-premise installation, disable the option "Temporary closure of the public part of the site". Path to the setting:
Desktop > Settings > Product Settings > Module Settings > Main Module > Temporary closure of the public part of the site
Copied
Continue Learning
Continue Learning
Add Badge crm.activity.badge.add
Get the list of badges crm.activity.badge.list
Get Badge Information by Code crm.activity.badge.get
Copied
Was the article helpful?
Yes
No
Previous
Get Badge Information by Code
Next
Add Configurable Activity

---

## Add Configurable CRM Activity <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-hjgc7icy">crm.activity.configurable.add</code>

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/crm-activity-configurable-add

Add Configurable CRM Activity <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-hjgc7icy">crm.activity.configurable.add</code> | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Configurable CRM Activity
crm.activity.configurable.add
Method Parameters
Parameter fields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method
crm.activity.configurable.add
adds a configurable activity to the timeline.
Warning
The method can only be called in the context of an
application
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ownerTypeId
*
integer
Integer identifier of the
CRM entity type
in which the activity is created, for example
2
for a deal
ownerId
*
integer
Integer identifier of the CRM element in which the activity is created, for example
1
fields
*
array
Associative array of values for the
activity fields
in the following structure:
fields
:
{
"typeId"
:
'value'
,
"completed"
:
'value'
,
"deadline"
:
'value'
,
"pingOffsets"
:
'value'
,
"isIncomingChannel"
:
'value'
,
"responsibleId"
:
'value'
,
"badgeCode"
:
'value'
,
"originatorId"
:
'value'
,
"originId"
:
'value'
,
}
layout
*
LayoutDto
Associative array of a special structure
describing the appearance of the activity in the timeline
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
typeId
string
Type of the configurable activity. If not specified, it defaults to
CONFIGURABLE
. If specified, the value must correspond to one of the types created by the method
crm.activity.type.add
with the field
IS_CONFIGURABLE_TYPE
equal to
Y
in the context of the same application
completed
boolean
Flag indicating whether the activity is closed. You can use
Y/N
,
1/0
,
true/false
to set the value
deadline
datetime
Deadline for the activity
pingOffsets
array
Array of offsets in minutes relative to the deadline, determining when to create ping records for this activity
isIncomingChannel
boolean
Flag indicating whether the activity was created from an incoming channel. You can use
Y/N
,
1/0
,
true/false
to set the value
responsibleId
integer
Responsible person for the activity
badgeCode
string
Code of the
badge on the kanban
corresponding to the activity
originatorId
string
Identifier of the data source
originId
string
Identifier of the element in the data source
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ownerTypeId":1,"ownerId":999,"fields":{"typeId":"CONFIGURABLE","completed":true,"deadline":"**put_current_date_time_here**","pingOffsets":[60,300],"isIncomingChannel":"N","responsibleId":1,"badgeCode":"CUSTOM"},"layout":{"icon":{"code":"call-completed"},"header":{"title":"Incoming Call"},"body":{"logo":{"code":"call-incoming"},"blocks":{"responsible":{"type":"lineOfBlocks","properties":{"blocks":{"client":{"type":"link","properties":{"text":"John Doe","bold":true,"action":{"type":"redirect","uri":"/crm/lead/details/789/"}}},"phone":{"type":"text","properties":{"value":"+1 999 888 7777"}}}}}}},"footer":{"buttons":{"startCall":{"title":"About Client","action":{"type":"openRestApp","actionParams":{"clientId":456}},"type":"primary"}}}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.configurable.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.activity.configurable.add"
,
{
ownerTypeId
:
1
,
ownerId
:
999
,
fields
:
{
typeId
:
'CONFIGURABLE'
,
completed
:
true
,
deadline
:
new
Date
(),
pingOffsets
: [
60
,
300
],
isIncomingChannel
:
'N'
,
responsibleId
:
1
,
badgeCode
:
'CUSTOM'
,
},
layout
:
{
"icon"
: {
"code"
:
"call-completed"
},
"header"
: {
"title"
:
"Incoming Call"
},
"body"
: {
"logo"
: {
"code"
:
"call-incoming"
},
"blocks"
: {
"responsible"
: {
"type"
:
"lineOfBlocks"
,
"properties"
: {
"blocks"
: {
"client"
: {
"type"
:
"link"
,
"properties"
: {
"text"
:
"John Doe"
,
"bold"
:
true
,
"action"
: {
"type"
:
"redirect"
,
"uri"
:
"/crm/lead/details/789/"
}
}
},
"phone"
: {
"type"
:
"text"
,
"properties"
: {
"value"
:
"+1 999 888 7777"
}
}
}
}
}
}
},
"footer"
: {
"buttons"
: {
"startCall"
: {
"title"
:
"About Client"
,
"action"
: {
"type"
:
"openRestApp"
,
"actionParams"
: {
"clientId"
:
456
}
},
"type"
:
"primary"
}
}
}
}
}
);
const
result = response.
getData
().
result
;
console
.
dir
(result);
}
catch
( error )
{
console
.
error
(error);
}
try
{
$response
=
$b24Service
->core
->
call
(
'crm.activity.configurable.add'
,
[
'ownerTypeId'
=>
1
,
'ownerId'
=>
999
,
'fields'
=> [
'typeId'
=>
'CONFIGURABLE'
,
'completed'
=>
true
,
'deadline'
=>
new
DateTime
(),
'pingOffsets'
=> [
60
,
300
],
'isIncomingChannel'
=>
'N'
,
'responsibleId'
=>
1
,
'badgeCode'
=>
'CUSTOM'
,
],
'layout'
=> [
'icon'
=> [
'code'
=>
'call-completed'
,
],
'header'
=> [
'title'
=>
'Incoming Call'
,
],
'body'
=> [
'logo'
=> [
'code'
=>
'call-incoming'
,
],
'blocks'
=> [
'responsible'
=> [
'type'
=>
'lineOfBlocks'
,
'properties'
=> [
'blocks'
=> [
'client'
=> [
'type'
=>
'link'
,
'properties'
=> [
'text'
=>
'John Doe'
,
'bold'
=>
true
,
'action'
=> [
'type'
=>
'redirect'
,
'uri'
=>
'/crm/lead/details/789/'
,
],
],
],
'phone'
=> [
'type'
=>
'text'
,
'properties'
=> [
'value'
=>
'+1 999 888 7777'
,
],
],
],
],
],
],
],
'footer'
=> [
'buttons'
=> [
'startCall'
=> [
'title'
=>
'About Client'
,
'action'
=> [
'type'
=>
'openRestApp'
,
'actionParams'
=> [
'clientId'
=>
456
,
],
],
'type'
=>
'primary'
,
],
],
],
],
]
);
$result
=
$response
->
getResponseData
()
->
getResult
();
echo
'Success: '
.
print_r
(
$result
,
true
);
// Your logic for processing data
processData
(
$result
);
}
catch
(
Throwable
$e
) {
error_log
(
$e
->
getMessage
());
echo
'Error adding configurable activity: '
.
$e
->
getMessage
();
}
BX24
.
callMethod
(
"crm.activity.configurable.add"
,
{
ownerTypeId
:
1
,
ownerId
:
999
,
fields
:
{
typeId
:
'CONFIGURABLE'
,
completed
:
true
,
deadline
:
new
Date
(),
pingOffsets
: [
60
,
300
],
isIncomingChannel
:
'N'
,
responsibleId
:
1
,
badgeCode
:
'CUSTOM'
,
},
layout
:
{
"icon"
: {
"code"
:
"call-completed"
},
"header"
: {
"title"
:
"Incoming Call"
},
"body"
: {
"logo"
: {
"code"
:
"call-incoming"
},
"blocks"
: {
"responsible"
: {
"type"
:
"lineOfBlocks"
,
"properties"
: {
"blocks"
: {
"client"
: {
"type"
:
"link"
,
"properties"
: {
"text"
:
"John Doe"
,
"bold"
:
true
,
"action"
: {
"type"
:
"redirect"
,
"uri"
:
"/crm/lead/details/789/"
}
}
},
"phone"
: {
"type"
:
"text"
,
"properties"
: {
"value"
:
"+1 999 888 7777"
}
}
}
}
}
}
},
"footer"
: {
"buttons"
: {
"startCall"
: {
"title"
:
"About Client"
,
"action"
: {
"type"
:
"openRestApp"
,
"actionParams"
: {
"clientId"
:
456
}
},
"type"
:
"primary"
}
}
}
}
},
result
=>
{
if
(result.
error
())
console
.
error
(result.
error
());
else
console
.
dir
(result.
data
());
}
);
require_once
(
'crest.php'
);
$result
=
CRest
::
call
(
'crm.activity.configurable.add'
,
[
'ownerTypeId'
=>
1
,
'ownerId'
=>
999
,
'fields'
=> [
'typeId'
=>
'CONFIGURABLE'
,
'completed'
=>
true
,
'deadline'
=>
date
(
'c'
), // Use current date
and
time in ISO
8601
format
'pingOffsets'
=> [
60
,
300
],
'isIncomingChannel'
=>
'N'
,
'responsibleId'
=>
1
,
'badgeCode'
=>
'CUSTOM'
,
],
'layout'
=> [
'icon'
=> [
'code'
=>
'call-completed'
],
'header'
=> [
'title'
=>
'Incoming Call'
],
'body'
=> [
'logo'
=> [
'code'
=>
'call-incoming'
],
'blocks'
=> [
'responsible'
=> [
'type'
=>
'lineOfBlocks'
,
'properties'
=> [
'blocks'
=> [
'client'
=> [
'type'
=>
'link'
,
'properties'
=> [
'text'
=>
'John Doe'
,
'bold'
=>
true
,
'action'
=> [
'type'
=>
'redirect'
,
'uri'
=>
'/crm/lead/details/789/'
]
]
],
'phone'
=> [
'type'
=>
'text'
,
'properties'
=> [
'value'
=>
'+1 999 888 7777'
]
]
]
]
]
]
],
'footer'
=> [
'buttons'
=> [
'startCall'
=> [
'title'
=>
'About Client'
,
'action'
=> [
'type'
=>
'openRestApp'
,
'actionParams'
=> [
'clientId'
=>
456
]
},
'type'
=>
'primary'
]
]
]
]
]
);
if
(
isset
(
$result
[
'error'
])) {
echo
'Error: '
.
$result
[
'error_description'
];
}
else
{
echo
'<PRE>'
;
print_r
(
$result
[
'result'
]);
echo
'</PRE>'
;
}
Response Handling
Response Handling
HTTP Status:
200
{
"result"
:
{
"activity"
:
{
"id"
:
999
,
}
,
"time"
:
{
"start"
:
1724068028.331234
,
"finish"
:
1724068028.726591
,
"duration"
:
0.3953571319580078
,
"processing"
:
0.13033390045166016
,
"date_start"
:
"2025-01-21T13:47:08+02:00"
,
"date_finish"
:
"2025-01-21T13:47:08+02:00"
,
"operating"
:
0
}
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response containing information about the added activity identifier
id
in case of success. In case of failure, it will return
null
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Not found."
}
Name
type
Description
error
string
String error code. It may consist of digits, Latin letters, and underscores
error_description
error_description
Textual description of the error. The description is not intended to be shown to the end user in its raw form
Copied
Possible Error Codes
Possible Error Codes
Code
Description
ACCESS_DENIED
Insufficient permissions to perform the operation
100
Required fields are not filled
ERROR_WRONG_CONTEXT
Method call is only possible in the context of an application
ERROR_WRONG_APPLICATION
The activity can only be updated by the application that created it
WRONG_FIELD_VALUE
Incorrect field value
INCOMING_ACTIVITY_CAN_NOT_BE_WITH_DEADLINE
Incoming activity cannot have a deadline
ERROR_EMPTY_LAYOUT
The layout field must be filled
Statuses and System Error Codes
Statuses and System Error Codes
HTTP Status:
20x
,
40x
,
50x
The errors described below may occur when calling any method.
Status
Code
Error Message
Description
500
INTERNAL_SERVER_ERROR
Internal server error
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
500
ERROR_UNEXPECTED_ANSWER
Server returned an unexpected response
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
503
QUERY_LIMIT_EXCEEDED
Too many requests
The
request intensity limit
has been exceeded
405
ERROR_BATCH_METHOD_NOT_ALLOWED
Method is not allowed for batch usage
The current method is not allowed to be called using
batch
400
ERROR_BATCH_LENGTH_EXCEEDED
Max batch length exceeded
The maximum length of parameters passed to the
batch
method has been exceeded
401
NO_AUTH_FOUND
Wrong authorization data
Invalid
access token
or
webhook code
400
INVALID_REQUEST
Https required
The methods must be called using the HTTPS protocol
503
OVERLOAD_LIMIT
REST API is blocked due to overload
The REST API is blocked due to overload. This is a manual individual block, to remove it you need to contact
Bitrix24 technical support
403
ACCESS_DENIED
REST API is available only on commercial plans
The REST API is available only on commercial plans
403
INVALID_CREDENTIALS
Invalid request credentials
The user whose
access token
or
webhook
was used to call the method lacks permissions
404
ERROR_MANIFEST_IS_NOT_AVAILABLE
Manifest is not available
The manifest is not available
403
insufficient_scope
The request requires higher privileges than provided by the webhook token
The request requires higher privileges than those provided by the
webhook
token
401
expired_token
The access token provided has expired
The provided
access token
has expired
403
user_access_error
The user does not have access to the application
The user does not have access to the application. This means that the application is installed, but the account administrator has allowed access to this application only for specific users
500
PORTAL_DELETED
Portal was deleted
The public part of the site is closed. To open the public part of the site on an on-premise installation, disable the option "Temporary closure of the public part of the site". Path to the setting:
Desktop > Settings > Product Settings > Module Settings > Main Module > Temporary closure of the public part of the site
Copied
Continue Learning
Continue Learning
Update Configurable Activity crm.activity.configurable.update
Get Configurable Activity by ID crm.activity.configurable.get
Copied
Was the article helpful?
Yes
No
Previous
Delete Badge
Next
Update Configurable Activity

---

## Update Configurable Activity crm.activity.configurable.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/crm-activity-configurable-update

Update Configurable Activity crm.activity.configurable.update | Bitrix24 REST API and Marketplace Applications
Update Configurable Activity crm.activity.configurable.update
Update Configurable Activity crm.activity.configurable.update
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method
crm.activity.configurable.update
makes changes to a configurable activity.
Warning
The method can only be called in the context of the
application
that created it.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Integer identifier of the activity, for example
999
fields
*
array
Associative array of values for
activity fields
in the following structure:
fields
:
{
"typeId"
:
'value'
,
"completed"
:
'value'
,
"deadline"
:
'value'
,
"pingOffsets"
:
'value'
,
"isIncomingChannel"
:
'value'
,
"responsibleId"
:
'value'
,
"badgeCode"
:
'value'
,
"originatorId"
:
'value'
,
"originId"
:
'value'
,
}
layout
*
LayoutDto
Associative array of special structure
, describing the appearance of the activity in the timeline
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"fields":{"typeId":"CONFIGURABLE","completed":false,"deadline":"**put_current_date_time_here**","pingOffsets":[300],"isIncomingChannel":"Y","responsibleId":5,"badgeCode":"CUSTOM"},"layout":{"icon":{"code":"call-completed"},"header":{"title":"Incoming Call"},"body":{"logo":{"code":"call-incoming"},"blocks":{"responsible":{"type":"lineOfBlocks","properties":{"blocks":{"client":{"type":"link","properties":{"text":"John Smith","bold":true,"action":{"type":"redirect","uri":"/crm/lead/details/789/"}}},"phone":{"type":"text","properties":{"value":"+1 999 888 7777"}}}}}}},"footer":{"buttons":{"startCall":{"title":"About Client","action":{"type":"openRestApp","actionParams":{"clientId":456}},"type":"primary"}}}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.configurable.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.activity.configurable.update"
,
{
id
:
999
,
fields
:
{
typeId
:
'CONFIGURABLE'
,
completed
:
false
,
deadline
:
new
Date
(),
pingOffsets
: [
300
],
isIncomingChannel
:
'Y'
,
responsibleId
:
5
,
badgeCode
:
'CUSTOM'
,
},
layout
:
{
"icon"
: {
"code"
:
"call-completed"
},
"header"
: {
"title"
:
"Incoming Call"
},
"body"
: {
"logo"
: {
"code"
:
"call-incoming"
},
"blocks"
: {
"responsible"
: {
"type"
:
"lineOfBlocks"
,
"properties"
: {
"blocks"
: {
"client"
: {
"type"
:
"link"
,
"properties"
: {
"text"
:
"John Smith"
,
"bold"
:
true
,
"action"
: {
"type"
:
"redirect"
,
"uri"
:
"/crm/lead/details/789/"
}
}
},
"phone"
: {
"type"
:
"text"
,
"properties"
: {
"value"
:
"+1 999 888 7777"
}
}
}
}
}
}
},
"footer"
: {
"buttons"
: {
"startCall"
: {
"title"
:
"About Client"
,
"action"
: {
"type"
:
"openRestApp"
,
"actionParams"
: {
"clientId"
:
456
}
},
"type"
:
"primary"
}
}
}
}
}
);
const
result = response.
getData
().
result
;
console
.
dir
(result);
}
catch
( error )
{
console
.
error
(error);
}
try
{
$response
=
$b24Service
->core
->
call
(
'crm.activity.configurable.update'
,
[
'id'
=>
999
,
'fields'
=> [
'typeId'
=>
'CONFIGURABLE'
,
'completed'
=>
false
,
'deadline'
=>
new
DateTime
(),
'pingOffsets'
=> [
300
],
'isIncomingChannel'
=>
'Y'
,
'responsibleId'
=>
5
,
'badgeCode'
=>
'CUSTOM'
,
],
'layout'
=> [
'icon'
=> [
'code'
=>
'call-completed'
,
],
'header'
=> [
'title'
=>
'Incoming Call'
,
],
'body'
=> [
'logo'
=> [
'code'
=>
'call-incoming'
,
],
'blocks'
=> [
'responsible'
=> [
'type'
=>
'lineOfBlocks'
,
'properties'
=> [
'blocks'
=> [
'client'
=> [
'type'
=>
'link'
,
'properties'
=> [
'text'
=>
'John Smith'
,
'bold'
=>
true
,
'action'
=> [
'type'
=>
'redirect'
,
'uri'
=>
'/crm/lead/details/789/'
,
],
],
],
'phone'
=> [
'type'
=>
'text'
,
'properties'
=> [
'value'
=>
'+1 999 888 7777'
,
],
],
],
],
],
],
],
'footer'
=> [
'buttons'
=> [
'startCall'
=> [
'title'
=>
'About Client'
,
'action'
=> [
'type'
=>
'openRestApp'
,
'actionParams'
=> [
'clientId'
=>
456
,
],
],
'type'
=>
'primary'
,
],
],
],
],
]
);
$result
=
$response
->
getResponseData
()
->
getResult
();
echo
'Success: '
.
print_r
(
$result
,
true
);
// Your logic for processing data
processData
(
$result
);
}
catch
(
Throwable
$e
) {
error_log
(
$e
->
getMessage
());
echo
'Error updating configurable activity: '
.
$e
->
getMessage
();
}
BX24
.
callMethod
(
"crm.activity.configurable.update"
,
{
id
:
999
,
fields
:
{
typeId
:
'CONFIGURABLE'
,
completed
:
false
,
deadline
:
new
Date
(),
pingOffsets
: [
300
],
isIncomingChannel
:
'Y'
,
responsibleId
:
5
,
badgeCode
:
'CUSTOM'
,
},
layout
:
{
"icon"
: {
"code"
:
"call-completed"
},
"header"
: {
"title"
:
"Incoming Call"
},
"body"
: {
"logo"
: {
"code"
:
"call-incoming"
},
"blocks"
: {
"responsible"
: {
"type"
:
"lineOfBlocks"
,
"properties"
: {
"blocks"
: {
"client"
: {
"type"
:
"link"
,
"properties"
: {
"text"
:
"John Smith"
,
"bold"
:
true
,
"action"
: {
"type"
:
"redirect"
,
"uri"
:
"/crm/lead/details/789/"
}
}
},
"phone"
: {
"type"
:
"text"
,
"properties"
: {
"value"
:
"+1 999 888 7777"
}
}
}
}
}
}
},
"footer"
: {
"buttons"
: {
"startCall"
: {
"title"
:
"About Client"
,
"action"
: {
"type"
:
"openRestApp"
,
"actionParams"
: {
"clientId"
:
456
}
},
"type"
:
"primary"
}
}
}
}
},
result
=>
{
if
(result.
error
())
console
.
error
(result.
error
());
else
console
.
dir
(result.
data
());
}
);
require_once
(
'crest.php'
);
$result
=
CRest
::
call
(
'crm.activity.configurable.update'
,
[
'id'
=>
999
,
'fields'
=> [
'typeId'
=>
'CONFIGURABLE'
,
'completed'
=>
false
,
'deadline'
=>
date
(
'c'
), // Using the current date
and
time in ISO
8601
format
'pingOffsets'
=> [
300
],
'isIncomingChannel'
=>
'Y'
,
'responsibleId'
=>
5
,
'badgeCode'
=>
'CUSTOM'
,
],
'layout'
=> [
'icon'
=> [
'code'
=>
'call-completed'
],
'header'
=> [
'title'
=>
'Incoming Call'
],
'body'
=> [
'logo'
=> [
'code'
=>
'call-incoming'
],
'blocks'
=> [
'responsible'
=> [
'type'
=>
'lineOfBlocks'
,
'properties'
=> [
'blocks'
=> [
'client'
=> [
'type'
=>
'link'
,
'properties'
=> [
'text'
=>
'John Smith'
,
'bold'
=>
true
,
'action'
=> [
'type'
=>
'redirect'
,
'uri'
=>
'/crm/lead/details/789/'
]
]
],
'phone'
=> [
'type'
=>
'text'
,
'properties'
=> [
'value'
=>
'+1 999 888 7777'
]
]
]
]
]
]
],
'footer'
=> [
'buttons'
=> [
'startCall'
=> [
'title'
=>
'About Client'
,
'action'
=> [
'type'
=>
'openRestApp'
,
'actionParams'
=> [
'clientId'
=>
456
]
],
'type'
=>
'primary'
]
]
]
]
]
);
if
(
isset
(
$result
[
'error'
])) {
echo
'Error: '
.
$result
[
'error_description'
];
}
else
{
echo
'<PRE>'
;
print_r
(
$result
[
'result'
]);
echo
'</PRE>'
;
}
Response Handling
Response Handling
HTTP Status:
200
{
"result"
:
{
"activity"
:
{
"id"
:
999
,
}
,
"time"
:
{
"start"
:
1724068028.331234
,
"finish"
:
1724068028.726591
,
"duration"
:
0.3953571319580078
,
"processing"
:
0.13033390045166016
,
"date_start"
:
"2025-01-21T13:47:08+02:00"
,
"date_finish"
:
"2025-01-21T13:47:08+02:00"
,
"operating"
:
0
}
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response containing information about the added activity identifier
id
in case of success. In case of failure, it will return
null
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Not found."
}
Name
type
Description
error
string
String error code. It may consist of digits, Latin letters, and underscores
error_description
error_description
Textual description of the error. The description is not intended to be shown to the end user in its raw form
Copied
Possible Error Codes
Possible Error Codes
Code
Description
ACCESS_DENIED
Insufficient permissions to perform the operation
NOT_FOUND
Element not found
100
Required fields are not filled
ERROR_WRONG_CONTEXT
Method call is only possible in the context of the application
ERROR_WRONG_APPLICATION
The activity can only be updated by the application that created it
WRONG_FIELD_VALUE
Incorrect field value
INCOMING_ACTIVITY_CAN_NOT_BE_WITH_DEADLINE
Incoming activity cannot have a deadline
ERROR_EMPTY_LAYOUT
The layout field must be filled
Statuses and System Error Codes
Statuses and System Error Codes
HTTP Status:
20x
,
40x
,
50x
The errors described below may occur when calling any method.
Status
Code
Error Message
Description
500
INTERNAL_SERVER_ERROR
Internal server error
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
500
ERROR_UNEXPECTED_ANSWER
Server returned an unexpected response
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
503
QUERY_LIMIT_EXCEEDED
Too many requests
The
request intensity limit
has been exceeded
405
ERROR_BATCH_METHOD_NOT_ALLOWED
Method is not allowed for batch usage
The current method is not allowed to be called using
batch
400
ERROR_BATCH_LENGTH_EXCEEDED
Max batch length exceeded
The maximum length of parameters passed to the
batch
method has been exceeded
401
NO_AUTH_FOUND
Wrong authorization data
Invalid
access token
or
webhook code
400
INVALID_REQUEST
Https required
The methods must be called using the HTTPS protocol
503
OVERLOAD_LIMIT
REST API is blocked due to overload
The REST API is blocked due to overload. This is a manual individual block, to remove it you need to contact
Bitrix24 technical support
403
ACCESS_DENIED
REST API is available only on commercial plans
The REST API is available only on commercial plans
403
INVALID_CREDENTIALS
Invalid request credentials
The user whose
access token
or
webhook
was used to call the method lacks permissions
404
ERROR_MANIFEST_IS_NOT_AVAILABLE
Manifest is not available
The manifest is not available
403
insufficient_scope
The request requires higher privileges than provided by the webhook token
The request requires higher privileges than those provided by the
webhook
token
401
expired_token
The access token provided has expired
The provided
access token
has expired
403
user_access_error
The user does not have access to the application
The user does not have access to the application. This means that the application is installed, but the account administrator has allowed access to this application only for specific users
500
PORTAL_DELETED
Portal was deleted
The public part of the site is closed. To open the public part of the site on an on-premise installation, disable the option "Temporary closure of the public part of the site". Path to the setting:
Desktop > Settings > Product Settings > Module Settings > Main Module > Temporary closure of the public part of the site
Copied
Continue Learning
Continue Learning
Add Configurable CRM Activity `crm.activity.configurable.add`
Get Configurable Activity by ID crm.activity.configurable.get
Copied
Was the article helpful?
Yes
No
Previous
Add Configurable Activity
Next
Get Information about Configurable Activity

---

## Get Configurable Activity by ID crm.activity.configurable.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/configurable/crm-activity-configurable-get

Get Configurable Activity by ID crm.activity.configurable.get | Bitrix24 REST API and Marketplace Applications
Get Configurable Activity by ID crm.activity.configurable.get
Get Configurable Activity by ID crm.activity.configurable.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method
crm.activity.configurable.get
returns information about a configurable activity.
Warning
The method can only be called in the context of an
application
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Integer identifier of the activity, for example
999
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.configurable.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.configurable.get'
,
{
id
:
999
,
}
);
const
result = response.
getData
().
result
;
if
(result.
error
())
{
console
.
error
(result.
error
());
}
else
{
console
.
dir
(result);
}
}
catch
( error )
{
console
.
error
(
'Error:'
, error);
}
try
{
$response
=
$b24Service
->core
->
call
(
'crm.activity.configurable.get'
,
[
'id'
=>
999
,
]
);
$result
=
$response
->
getResponseData
()
->
getResult
();
if
(
$result
->
error
()) {
error_log
(
$result
->
error
());
}
else
{
echo
'Data: '
.
print_r
(
$result
->
data
(),
true
);
}
}
catch
(
Throwable
$e
) {
error_log
(
$e
->
getMessage
());
echo
'Error getting configurable activity: '
.
$e
->
getMessage
();
}
BX24
.
callMethod
(
"crm.activity.configurable.get"
,
{
id
:
999
,
},
result
=>
{
if
(result.
error
())
console
.
error
(result.
error
());
else
console
.
dir
(result.
data
());
}
);
require_once
(
'crest.php'
);
$result
=
CRest
::
call
(
'crm.activity.configurable.get'
,
[
'id'
=>
999
]
);
echo
'<PRE>'
;
print_r
(
$result
);
echo
'</PRE>'
;
Response Handling
Response Handling
HTTP Status:
200
{
"result"
:
{
"activity"
:
{
"id"
:
8903
,
"ownerTypeId"
:
1
,
"ownerId"
:
2975
,
"fields"
:
{
"typeId"
:
"CONFIGURABLE"
,
"completed"
:
false
,
"deadline"
:
"2025-02-01T01:00:00+03:00"
,
"pingOffsets"
:
[
]
,
"isIncomingChannel"
:
false
,
"responsibleId"
:
1
,
"badgeCode"
:
""
,
"originatorId"
:
null
,
"originId"
:
null
}
,
"layout"
:
{
"icon"
:
{
"code"
:
"call-completed"
}
,
"header"
:
{
"title"
:
"Incoming Call"
,
"tags"
:
{
"status2"
:
{
"title"
:
"not transcribed"
,
"type"
:
"warning"
}
}
}
,
"body"
:
{
"logo"
:
{
"code"
:
"call-incoming"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
}
,
"blocks"
:
{
"client"
:
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Client"
,
"inline"
:
true
,
"block"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Ltd. Hoofs and Horns"
}
}
}
}
,
"responsible"
:
{
"type"
:
"lineOfBlocks"
,
"properties"
:
{
"blocks"
:
{
"client"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Sergey Vostrikov"
,
"bold"
:
true
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/lead/details/789/"
}
}
}
,
"phone"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"+1 999 888 7777"
}
}
}
}
}
}
}
,
"footer"
:
{
"buttons"
:
{
"startCall"
:
{
"title"
:
"About Client"
,
"type"
:
"primary"
,
"action"
:
{
"type"
:
"openRestApp"
,
"actionParams"
:
{
"clientId"
:
"456"
}
}
}
}
,
"menu"
:
{
"showPostponeItem"
:
false
,
"items"
:
{
"confirm"
:
{
"title"
:
"Confirm Request"
,
"action"
:
{
"type"
:
"restEvent"
,
"id"
:
"confirm"
,
"animationType"
:
"loader"
}
}
,
"decline"
:
{
"title"
:
"Decline Request"
,
"action"
:
{
"type"
:
"restEvent"
,
"id"
:
"decline"
,
"animationType"
:
"loader"
}
}
}
}
}
}
}
}
,
"time"
:
{
"start"
:
1724068028.331234
,
"finish"
:
1724068028.726591
,
"duration"
:
0.3953571319580078
,
"processing"
:
0.13033390045166016
,
"date_start"
:
"2025-01-21T13:47:08+02:00"
,
"date_finish"
:
"2025-01-21T13:47:08+02:00"
,
"operating"
:
0
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response - an associative array with the key
activity
, which will contain
fields
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Not found."
}
Name
type
Description
error
string
String error code. It may consist of digits, Latin letters, and underscores
error_description
error_description
Textual description of the error. The description is not intended to be shown to the end user in its raw form
Copied
Possible Error Codes
Possible Error Codes
Code
Description
ACCESS_DENIED
Insufficient permissions to perform the operation
NOT_FOUND
Element not found
ERROR_WRONG_CONTEXT
Method call is only possible in the context of an application
Statuses and System Error Codes
Statuses and System Error Codes
HTTP Status:
20x
,
40x
,
50x
The errors described below may occur when calling any method.
Status
Code
Error Message
Description
500
INTERNAL_SERVER_ERROR
Internal server error
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
500
ERROR_UNEXPECTED_ANSWER
Server returned an unexpected response
An internal server error has occurred, please contact the server administrator or
Bitrix24 technical support
503
QUERY_LIMIT_EXCEEDED
Too many requests
The
request intensity limit
has been exceeded
405
ERROR_BATCH_METHOD_NOT_ALLOWED
Method is not allowed for batch usage
The current method is not allowed to be called using
batch
400
ERROR_BATCH_LENGTH_EXCEEDED
Max batch length exceeded
The maximum length of parameters passed to the
batch
method has been exceeded
401
NO_AUTH_FOUND
Wrong authorization data
Invalid
access token
or
webhook code
400
INVALID_REQUEST
Https required
The methods must be called using the HTTPS protocol
503
OVERLOAD_LIMIT
REST API is blocked due to overload
The REST API is blocked due to overload. This is a manual individual block, to remove it you need to contact
Bitrix24 technical support
403
ACCESS_DENIED
REST API is available only on commercial plans
The REST API is available only on commercial plans
403
INVALID_CREDENTIALS
Invalid request credentials
The user whose
access token
or
webhook
was used to call the method lacks permissions
404
ERROR_MANIFEST_IS_NOT_AVAILABLE
Manifest is not available
The manifest is not available
403
insufficient_scope
The request requires higher privileges than provided by the webhook token
The request requires higher privileges than those provided by the
webhook
token
401
expired_token
The access token provided has expired
The provided
access token
has expired
403
user_access_error
The user does not have access to the application
The user does not have access to the application. This means that the application is installed, but the account administrator has allowed access to this application only for specific users
500
PORTAL_DELETED
Portal was deleted
The public part of the site is closed. To open the public part of the site on an on-premise installation, disable the option "Temporary closure of the public part of the site". Path to the setting:
Desktop > Settings > Product Settings > Module Settings > Main Module > Temporary closure of the public part of the site
Copied
Continue Learning
Continue Learning
Update Configurable Activity crm.activity.configurable.update
Add Configurable CRM Activity `crm.activity.configurable.add`
Copied
Was the article helpful?
Yes
No
Previous
Update Configurable Activity
Next
Overview of Methods

---

