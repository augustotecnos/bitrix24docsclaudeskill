---
description: 'CRM Universal Config: Categories, user fields, SPA types, detail config'
methods:
- app.info
- crm.activity.
- crm.automatedsolution.
- crm.category.
- crm.category.add
- crm.category.delete
- crm.category.fields
- crm.category.get
- crm.category.list
- crm.category.update
- crm.company.userfield.add
- crm.contact.userfield.add
- crm.deal.userfield.add
- crm.documentgenerator.
- crm.enum.addresstype
- crm.enum.ownertype
- crm.item.
- crm.item.add
- crm.item.delete
- crm.item.details.configuration.
- crm.item.details.configuration.forceCommonScopeForAll
- crm.item.details.configuration.get
- crm.item.details.configuration.reset
- crm.item.details.configuration.set
- crm.item.fields
- crm.item.get
- crm.item.list
- crm.item.productrow.
- crm.item.productrow.add
- crm.item.productrow.delete
pages: 35
title: 'CRM Universal Config: Categories, user fields, SPA types, detail config'
---
# CRM Universal Config: Categories, user fields, SPA types, detail config
> CRM Universal Config: Categories, user fields, SPA types, detail config
> **35 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Smart Processes: Overview of Methods](#smart-processes-overview-of-methods)
- [Create a new custom type crm.type.add](#create-a-new-custom-type-crmtypeadd)
- [Update User Type crm.type.update](#update-user-type-crmtypeupdate)
- [Get the user type by id crm.type.get](#get-the-user-type-by-id-crmtypeget)
- [Get the user type by entityTypeId crm.type.getByEntityTypeId](#get-the-user-type-by-entitytypeid-crmtypegetbyenti)
- [Get a list of custom types crm.type.list](#get-a-list-of-custom-types-crmtypelist)
- [Delete user type crm.type.delete](#delete-user-type-crmtypedelete)
- [Get Custom Type Fields crm.type.fields](#get-custom-type-fields-crmtypefields)
- [Custom Fields in CRM](#custom-fields-in-crm)
- [Custom Field Types in CRM](#custom-field-types-in-crm)
- [Get Description for Custom Fields crm.userfield.fields](#get-description-for-custom-fields-crmuserfieldfiel)
- [Get a list of user field types crm.userfield.types](#get-a-list-of-user-field-types-crmuserfieldtypes)
- [Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields](#get-field-descriptions-for-custom-field-type-enume)
- [Get the field settings description for the custom field type crm.userfield.settings.fields](#get-the-field-settings-description-for-the-custom-)
- [Custom Fields](#custom-fields)
- [EntityId Identifiers](#entityid-identifiers)
- [Custom Fields](#custom-fields)
- [Add a New Custom Field userfieldconfig.add](#add-a-new-custom-field-userfieldconfigadd)
- [Delete User Field Settings userfieldconfig.delete](#delete-user-field-settings-userfieldconfigdelete)
- [Get Data on User Field Settings userfieldconfig.get](#get-data-on-user-field-settings-userfieldconfigget)
- [Get a set of available custom field types for the module moduleId userfieldconfig.getTypes](#get-a-set-of-available-custom-field-types-for-the-)
- [Get a List of User Field Settings userfieldconfig.list](#get-a-list-of-user-field-settings-userfieldconfigl)
- [Change the value of the user field userfieldconfig.update](#change-the-value-of-the-user-field-userfieldconfig)
- [Overview of Methods](#overview-of-methods)
- [Add a New Sales Funnel crm.category.add](#add-a-new-sales-funnel-crmcategoryadd)
- [Update Sales Funnel crm.category.update](#update-sales-funnel-crmcategoryupdate)
- [Get the funnel by Id crm.category.get](#get-the-funnel-by-id-crmcategoryget)
- [Get the list of Sales Funnels crm.category.list](#get-the-list-of-sales-funnels-crmcategorylist)
- [Delete Sales Funnel crm.category.delete](#delete-sales-funnel-crmcategorydelete)
- [Get Fields of the Sales Funnel crm.category.fields](#get-fields-of-the-sales-funnel-crmcategoryfields)
- [Configuring Sections in the Detail Form of CRM Entities](#configuring-sections-in-the-detail-form-of-crm-ent)
- [Get Parameters of CRM Item Detail Configuration](#get-parameters-of-crm-item-detail-configuration)
- [Set Parameters for CRM Item Card crm.item.details.configuration.set](#set-parameters-for-crm-item-card-crmitemdetailscon)
- [Reset Item Card Parameters crm.item.details.configuration.reset](#reset-item-card-parameters-crmitemdetailsconfigura)
- [Set Common Detail for All Users crm.item.details.configuration.forceCommonScopeForAll](#set-common-detail-for-all-users-crmitemdetailsconf)

---

## Smart Processes: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-object-types/index

Smart Processes: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Working with a Smart Process
Smart Processes: Overview of Methods
Working with a Smart Process
Connections with Other Objects
Smart Process Item Detail Form
Widgets
Smart Process Embedding Locations
Smart Process Identifiers
Overview of Methods and Events
Smart Processes
Items
Funnels
Custom Fields
Managing Detail Form Settings
Product Items
A smart process is a versatile CRM object that can be customized to meet the needs of a company. For each smart process, Bitrix24 creates a separate section in the CRM. In this section, you can configure funnels and stages, Automation rules, fields, and connections with other Bitrix24 objects.
Quick navigation:
all methods and events
User documentation:
Smart Processes in CRM
Working with a Smart Process
Working with a Smart Process
Create and configure the smart process — methods
crm.type.*
.
Set up funnels and stages —
crm.category.*
for funnels and
crm.status.*
for stages.
Add custom fields —
userfieldconfig.*
.
Configure the item detail form —
crm.item.details.configuration.*
.
Create the first items within the smart process —
crm.item.*
.
The smart process can be transferred from the CRM section to the Automation section via
digital workplaces
.
Connections with Other Objects
Connections with Other Objects
CRM Objects.
A smart process can be
linked
to leads, deals, and other CRM objects. The linked object will be accessible through the field
parentId{ID}
, where
{ID}
is the numeric identifier of the CRM object.
Client.
A field in the smart process detail form that consists of the associated company and contacts. There is one company in the field; change the linked company through the
companyId
field. There can be multiple contacts in the "Client" field. Interaction with contacts is conducted through the
contactIds
field — pass an array of contact IDs into the field. Enable the field with the option
isClientEnabled
in the method
crm.type.add
or
crm.type.update
.
Your Company Details.
Specify your company ID in the
mycompanyId
field so that its details are automatically used in documents. You can obtain your company ID using the method
crm.item.list
for the company object with a filter on the
isMyCompany
field. Enable the field with the option
isMycompanyEnabled
in the method
crm.type.add
or
crm.type.update
.
Products.
To add, modify, or delete product items in the smart process, use the methods
crm.item.productrow.*
. Enable the products tab and the "Amount and Currency" field with the option
isLinkWithProductsEnabled
in the method
crm.type.add
or
crm.type.update
.
Users.
The smart process is linked to users by numeric identifiers in the fields:
createdBy
— who created it,
updatedBy
— who updated it,
movedBy
— who changed the stage,
assignedById
— responsible for the item,
observers
— observers. Enable the field with the option
isObserversEnabled
in the method
crm.type.add
or
crm.type.update
.
You can obtain the identifier and data of a user using the method
user.get
.
Documents.
To create a document from a template, upload a new template for the smart process, or configure the numbering for documents, use the methods
crm.documentgenerator.*
. Enable document handling in the smart process with the option
isDocumentsEnabled
in the method
crm.type.add
or
crm.type.update
.
Tasks.
Smart process items can be linked to tasks. To work with tasks, use the methods
tasks.task.*
. To make the linking option available, enable and configure the option
isUseInUserfieldEnabled
in the method
crm.type.add
or
crm.type.update
.
Calendar Events.
Smart process items can be linked to calendar events. To work with the calendar, use the methods
calendar.event.*
. To make the linking option available, enable and configure the option
isUseInUserfieldEnabled
in the method
crm.type.add
or
crm.type.update
.
User Documentation
How to attach a task to a smart process
How to create a custom field in a smart process
How to add a comment to the smart process timeline
How to create a new funnel with stages in a smart process
Smart Process Item Detail Form
Smart Process Item Detail Form
The main workspace in the smart process is the "General" tab of the detail form. It consists of two parts:
the left part, which contains fields with information. If the system fields are insufficient, you can create your own custom fields. Fields allow you to store information in various data formats: string, number, link, address, and others. To create, modify, retrieve, or delete custom fields in the smart process, use the group of methods
userfieldconfig.*
.
the right part, which contains the smart process timeline. In it, you can create, edit, filter, and delete CRM activities — a group of methods
crm.activity.*
, and timeline records — a group of methods
crm.timeline.*
.
You can manage the parameters of the smart process detail form through the group of methods
crm.item.details.configuration.*
.
User Documentation
CRM Detail Form: Features and Settings
System Fields in CRM
Custom Fields in CRM
Timeline in CRM Item
Widgets
Widgets
You can embed an application into the smart process detail form. Thanks to embedding, you can use the application without leaving the item detail form.
There are two embedding scenarios:
use special
embedding locations
. For example, by creating your own tab.
create a
custom field
, where the interface of your application will be loaded.
Smart Process Embedding Locations
Smart Process Embedding Locations
Replace
XXX
with the numeric identifier of a specific smart process, for example
CRM_DYNAMIC_183_DOCUMENTGENERATOR_BUTTON
.
CRM_DYNAMIC_XXX_DETAIL_TAB
— tab in the detailed CRM item form
CRM_DYNAMIC_XXX_DETAIL_ACTIVITY
— button above the item detail timeline
CRM_DYNAMIC_XXX_DETAIL_TOOLBAR
— dropdown menu item in the upper button of the detail form
CRM_DYNAMIC_XXX_DOCUMENTGENERATOR_BUTTON
— dropdown menu item for the document generator
CRM_DYNAMIC_XXX_LIST_MENU
— context menu item in the list of items
CRM_DYNAMIC_XXX_LIST_TOOLBAR
— dropdown menu item above the list of items
CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU
— context menu item for an activity in the item detail form
CRM_DYNAMIC_XXX_ROBOT_DESIGNER_TOOLBAR
— dropdown menu item in the upper button of the robot designer
Typical use-cases and scenarios
Widget Embedding Mechanism
Embed a widget in the CRM detail form
Smart Process Identifiers
Smart Process Identifiers
Each smart process has four types of identifiers. Use the identifiers to apply a method to a specific smart process.
Numeric identifier of type
130
. Obtain it using the method
crm.enum.ownertype
ID
or
crm.type.list
entityTypeId
.
Symbolic code of type
DYNAMIC_130
—
crm.enum.ownertype
SYMBOL_CODE
.
Short symbolic code of type
T82
—
crm.enum.ownertype
SYMBOL_CODE_SHORT
.
Custom field object type
CRM_13
—
crm.type.list
. Substitute the
id
from the method result into the formula
CRM_ + {ID}
.
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can execute the method: depending on the method
Smart Processes
Smart Processes
Methods
Events
Method
Description
crm.type.add
Creates a new smart process
crm.type.update
Updates the smart process
crm.type.get
Returns the smart process by id
crm.type.getByEntityTypeId
Returns the smart process by entityTypeId
crm.type.list
Returns a list of smart processes
crm.type.delete
Deletes the smart process
crm.type.fields
Returns the fields of the smart process
Event
Triggered
onCrmTypeAdd
When a smart process is created
onCrmTypeUpdate
When a smart process is updated
onCrmTypeDelete
When a smart process is deleted
Items
Items
The CRM object identifier
entityTypeId
—
numeric identifier type
, for example
128
.
Methods
Events
Method
Description
crm.item.add
Creates a new item
crm.item.update
Updates the item
crm.item.get
Returns the item by Id
crm.item.list
Returns a list of items by filter
crm.item.delete
Deletes the item
crm.item.fields
Returns the fields of the item
Event
Triggered
onCrmDynamicItemAdd
When a smart process item is created
onCrmDynamicItemDelete
When a smart process item is deleted
onCrmDynamicItemUpdate
When a smart process item is modified
Funnels
Funnels
The CRM object identifier
entityTypeId
—
numeric identifier type
, for example
128
.
Method
Description
crm.category.add
Creates a new funnel
crm.category.update
Updates the funnel
crm.category.get
Returns the funnel by Id
crm.category.list
Returns a list of funnels
crm.category.delete
Deletes the funnel
crm.category.fields
Returns the fields of the funnel
Custom Fields
Custom Fields
The CRM object identifier
entityId
—
custom field object type
, for example
CRM_1
.
Method
Description
userfieldconfig.add
Creates a custom field
userfieldconfig.update
Modifies field settings
userfieldconfig.get
Returns custom field settings by identifier
userfieldconfig.getTypes
Returns the set of available custom field types for the module
userfieldconfig.list
Returns a list of custom field settings
userfieldconfig.delete
Deletes a custom field
Managing Detail Form Settings
Managing Detail Form Settings
The CRM object identifier
entityTypeId
—
numeric identifier type
, for example
128
.
Method
Description
crm.item.details.configuration.forceCommonScopeForAll
Sets a common detail form for all users
crm.item.details.configuration.get
Retrieves the parameters of item detail forms
crm.item.details.configuration.reset
Resets the parameters of item detail forms
crm.item.details.configuration.set
Sets the parameters of item detail forms
Product Items
Product Items
The CRM object identifier
ownerType
—
short symbolic code type
, for example
T80
.
Method
Description
crm.item.productrow.add
Adds a product item
crm.item.productrow.update
Updates a product item
crm.item.productrow.get
Retrieves information about a product item by id
crm.item.productrow.set
Links a product item to a CRM object
crm.item.productrow.list
Retrieves a list of product items
crm.item.productrow.getAvailableForPayment
Retrieves a list of unpaid products
crm.item.productrow.delete
Deletes a product item
crm.item.productrow.fields
Retrieves a list of product item fields
Copied
Was the article helpful?
Yes
No
Previous
Universal Methods for Invoices
Next
Create a new custom type

---

## Create a new custom type crm.type.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-object-types/crm-type-add

Create a new custom type crm.type.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create a new custom type crm.type.add
Method Parameters
Parameter fields
Relations relations
Binding to user fields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with administrative access to the CRM section
This method creates a new SPA.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
Field values (detailed description provided
below
) for adding a new SPA
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
Default
title
*
string
Title of the SPA
entityTypeId
integer
Identifier of the created SPA. If this field is not provided, it will be generated automatically.
It should be noted that:
This parameter is unique. It is not possible to create two SPAs with the same
entityTypeId
The value of
entityTypeId
must be within one of two ranges:
an even integer that is greater than or equal to 1030
in the range from 128 to 192
relations
object
An object containing links to other CRM entities. The structure is described
below
isUseInUserfieldEnabled
boolean
Is the use of the SPA in the user field enabled
N
linkedUserFields
object
A set of user fields in which this SPA should be displayed. The structure is described
below
{}
isAutomationEnabled
boolean
Are Automation rules and triggers enabled
N
isBeginCloseDatesEnabled
boolean
Are the
Start Date
and
End Date
fields enabled
N
isBizProcEnabled
boolean
Is the business process designer enabled
N
isCategoriesEnabled
boolean
Are custom sales funnels and tunnels enabled
N
isClientEnabled
boolean
Is the
Client
field enabled. When this option is enabled, the SPA has a preset binding to
Contacts
and
Companies
N
isDocumentsEnabled
boolean
Is document printing enabled
N
isLinkWithProductsEnabled
boolean
Is the binding of catalog products enabled
N
isMycompanyEnabled
boolean
Is the
Your Company Details
field enabled
N
isObserversEnabled
boolean
Is the
Observers
field enabled
N
isRecyclebinEnabled
boolean
Is the use of the recycle bin enabled
N
isSetOpenPermissions
boolean
Should new funnels be available to everyone
Y
isSourceEnabled
boolean
Are the
Source
and
Additional Information about Source
fields enabled
N
isStagesEnabled
boolean
Is the use of custom stages and kanban enabled
N
isExternal
boolean
Is the SPA external to the CRM (linked to a digital workplace)
This parameter is deprecated. For working with digital workplaces, use the methods
crm.automatedsolution.*
-
customSectionId
integer
Identifier of the digital workplace
This parameter is deprecated. For working with digital workplaces, use the methods
crm.automatedsolution.*
-
customSections
array
Array of digital workplaces
This parameter is deprecated. For working with digital workplaces, use the methods
crm.automatedsolution.*
-
Relations relations
Relations relations
Name
type
Description
parent
relation[]
CRM elements that will be linked to this SPA
child
relation[]
CRM elements to which this SPA will be linked
One relation relation
One relation relation
Required parameters are marked with *
Name
type
Description
Default
entityTypeId
*
integer
Identifier of the
system
or
custom type
of the CRM entity
-
isChildrenListEnabled
boolean
Should the linked element be added to the card.
Values
Y
and
N
do not work. You must pass
"true"
or
"false"
"false"
Binding to user fields
Binding to user fields
linkedUserFields
— a set of fields in which this SPA should be displayed.
This setting will only be considered if
isUseInUserfieldEnabled = 'Y'
is passed.
Name
type
Description
Default Value
CALENDAR_EVENT
|
UF_CRM_CAL_EVENT
boolean
Calendar event
"false"
TASKS_TASK
|
UF_CRM_TASK
boolean
Tasks
"false"
TASKS_TASK_TEMPLATE
|
UF_CRM_TASK
boolean
Task templates
"false"
These parameters do not support passing values
Y
and
N
. Use
"true"
or
"false"
.
Code Examples
Code Examples
How to Use Examples in Documentation
Let's create an SPA with the following conditions:
The most complete set of enabled settings
Link
Leads
,
Deals
,
Invoices
to the created SPA. Each link is added to the card of the elements of this SPA
Link the created SPA to
Contacts
and
Companies
. The link to
Contacts
is added to the card
The SPA should be displayed in the following fields:
Calendar Event
,
Tasks
cURL (Webhook)
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
'{"fields":{"title":"SPA","entityTypeId":2024,"isAutomationEnabled":"Y","isBeginCloseDatesEnabled":"Y","isBizProcEnabled":"Y","isCategoriesEnabled":"Y","isClientEnabled":"Y","isDocumentsEnabled":"Y","isLinkWithProductsEnabled":"Y","isMycompanyEnabled":"Y","isObserversEnabled":"Y","isRecyclebinEnabled":"Y","isSetOpenPermissions":"Y","isSourceEnabled":"Y","isStagesEnabled":"Y","isUseInUserfieldEnabled":"Y","linkedUserFields":{"CALENDAR_EVENT|UF_CRM_CAL_EVENT":"true","TASKS_TASK|UF_CRM_TASK":"true"},"relations":{"parent":[{"entityTypeId":1,"isChildrenListEnabled":"true"},{"entityTypeId":2,"isChildrenListEnabled":"true"},{"entityTypeId":31,"isChildrenListEnabled":"true"}],"child":[{"entityTypeId":3,"isChildrenListEnabled":"true"},{"entityTypeId":4}]}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.type.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"title":"SPA","entityTypeId":2024,"isAutomationEnabled":"Y","isBeginCloseDatesEnabled":"Y","isBizProcEnabled":"Y","isCategoriesEnabled":"Y","isClientEnabled":"Y","isDocumentsEnabled":"Y","isLinkWithProductsEnabled":"Y","isMycompanyEnabled":"Y","isObserversEnabled":"Y","isRecyclebinEnabled":"Y","isSetOpenPermissions":"Y","isSourceEnabled":"Y","isStagesEnabled":"Y","isUseInUserfieldEnabled":"Y","linkedUserFields":{"CALENDAR_EVENT|UF_CRM_CAL_EVENT":"true","TASKS_TASK|UF_CRM_TASK":"true"},"relations":{"parent":[{"entityTypeId":1,"isChildrenListEnabled":"true"},{"entityTypeId":2,"isChildrenListEnabled":"true"},{"entityTypeId":31,"isChildrenListEnabled":"true"}],"child":[{"entityTypeId":3,"isChildrenListEnabled":"true"},{"entityTypeId":4}]}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.type.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.type.add'
,
{
fields
: {
title
:
"SPA"
,
entityTypeId
:
2024
,
isAutomationEnabled
:
"Y"
,
isBeginCloseDatesEnabled
:
"Y"
,
isBizProcEnabled
:
"Y"
,
isCategoriesEnabled
:
"Y"
,
isClientEnabled
:
"Y"
,
isDocumentsEnabled
:
"Y"
,
isLinkWithProductsEnabled
:
"Y"
,
isMycompanyEnabled
:
"Y"
,
isObserversEnabled
:
"Y"
,
isRecyclebinEnabled
:
"Y"
,
isSetOpenPermissions
:
"Y"
,
isSourceEnabled
:
"Y"
,
isStagesEnabled
:
"Y"
,
isUseInUserfieldEnabled
:
"Y"
,
linkedUserFields
: {
"CALENDAR_EVENT|UF_CRM_CAL_EVENT"
:
"true"
,
"TASKS_TASK|UF_CRM_TASK"
:
"true"
,
},
relations
: {
parent
: [
{
entityTypeId
:
1
,
isChildrenListEnabled
:
"true"
,
},
{
entityTypeId
:
2
,
isChildrenListEnabled
:
"true"
,
},
{
entityTypeId
:
31
,
isChildrenListEnabled
:
"true"
,
},
],
child
: [
{
entityTypeId
:
3
,
isChildrenListEnabled
:
"true"
,
},
{
entityTypeId
:
4
,
},
],
},
},
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
info
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
'crm.type.add'
,
[
'fields'
=> [
'title'
=>
"SPA"
,
'entityTypeId'
=>
2024
,
'isAutomationEnabled'
=>
"Y"
,
'isBeginCloseDatesEnabled'
=>
"Y"
,
'isBizProcEnabled'
=>
"Y"
,
'isCategoriesEnabled'
=>
"Y"
,
'isClientEnabled'
=>
"Y"
,
'isDocumentsEnabled'
=>
"Y"
,
'isLinkWithProductsEnabled'
=>
"Y"
,
'isMycompanyEnabled'
=>
"Y"
,
'isObserversEnabled'
=>
"Y"
,
'isRecyclebinEnabled'
=>
"Y"
,
'isSetOpenPermissions'
=>
"Y"
,
'isSourceEnabled'
=>
"Y"
,
'isStagesEnabled'
=>
"Y"
,
'isUseInUserfieldEnabled'
=>
"Y"
,
'linkedUserFields'
=> [
"CALENDAR_EVENT|UF_CRM_CAL_EVENT"
=>
"true"
,
"TASKS_TASK|UF_CRM_TASK"
=>
"true"
,
],
'relations'
=> [
'parent'
=> [
[
'entityTypeId'
=>
1
,
'isChildrenListEnabled'
=>
"true"
,
],
[
'entityTypeId'
=>
2
,
'isChildrenListEnabled'
=>
"true"
,
],
[
'entityTypeId'
=>
31
,
'isChildrenListEnabled'
=>
"true"
,
],
],
'child'
=> [
[
'entityTypeId'
=>
3
,
'isChildrenListEnabled'
=>
"true"
,
],
[
'entityTypeId'
=>
4
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
'Error adding CRM type: '
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
'crm.type.add'
,
{
fields
: {
title
:
"SPA"
,
entityTypeId
:
2024
,
isAutomationEnabled
:
"Y"
,
isBeginCloseDatesEnabled
:
"Y"
,
isBizProcEnabled
:
"Y"
,
isCategoriesEnabled
:
"Y"
,
isClientEnabled
:
"Y"
,
isDocumentsEnabled
:
"Y"
,
isLinkWithProductsEnabled
:
"Y"
,
isMycompanyEnabled
:
"Y"
,
isObserversEnabled
:
"Y"
,
isRecyclebinEnabled
:
"Y"
,
isSetOpenPermissions
:
"Y"
,
isSourceEnabled
:
"Y"
,
isStagesEnabled
:
"Y"
,
isUseInUserfieldEnabled
:
"Y"
,
linkedUserFields
: {
"CALENDAR_EVENT|UF_CRM_CAL_EVENT"
:
"true"
,
"TASKS_TASK|UF_CRM_TASK"
:
"true"
,
},
relations
: {
parent
: [
{
entityTypeId
:
1
,
isChildrenListEnabled
:
"true"
,
},
{
entityTypeId
:
2
,
isChildrenListEnabled
:
"true"
,
},
{
entityTypeId
:
31
,
isChildrenListEnabled
:
"true"
,
},
],
child
: [
{
entityTypeId
:
3
,
isChildrenListEnabled
:
"true"
,
},
{
entityTypeId
:
4
,
},
],
},
},
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.type.add'
,
[
'fields'
=> [
'title'
=>
"SPA"
,
'entityTypeId'
=>
2024
,
'isAutomationEnabled'
=>
"Y"
,
'isBeginCloseDatesEnabled'
=>
"Y"
,
'isBizProcEnabled'
=>
"Y"
,
'isCategoriesEnabled'
=>
"Y"
,
'isClientEnabled'
=>
"Y"
,
'isDocumentsEnabled'
=>
"Y"
,
'isLinkWithProductsEnabled'
=>
"Y"
,
'isMycompanyEnabled'
=>
"Y"
,
'isObserversEnabled'
=>
"Y"
,
'isRecyclebinEnabled'
=>
"Y"
,
'isSetOpenPermissions'
=>
"Y"
,
'isSourceEnabled'
=>
"Y"
,
'isStagesEnabled'
=>
"Y"
,
'isUseInUserfieldEnabled'
=>
"Y"
,
'linkedUserFields'
=> [
"CALENDAR_EVENT|UF_CRM_CAL_EVENT"
=>
"true"
,
"TASKS_TASK|UF_CRM_TASK"
=>
"true"
,
],
'relations'
=> [
'parent'
=> [
[
'entityTypeId'
=>
1
,
'isChildrenListEnabled'
=>
"true"
,
],
[
'entityTypeId'
=>
2
,
'isChildrenListEnabled'
=>
"true"
,
],
[
'entityTypeId'
=>
31
,
'isChildrenListEnabled'
=>
"true"
,
],
],
'child'
=> [
[
'entityTypeId'
=>
3
,
'isChildrenListEnabled'
=>
"true"
,
],
[
'entityTypeId'
=>
4
,
],
],
],
],
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
"type"
:
{
"id"
:
16
,
"createdBy"
:
1
,
"entityTypeId"
:
2024
,
"isCategoriesEnabled"
:
"Y"
,
"isStagesEnabled"
:
"Y"
,
"isBeginCloseDatesEnabled"
:
"Y"
,
"isClientEnabled"
:
"Y"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"Y"
,
"isMycompanyEnabled"
:
"Y"
,
"isDocumentsEnabled"
:
"Y"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"Y"
,
"isRecyclebinEnabled"
:
"Y"
,
"isAutomationEnabled"
:
"Y"
,
"isBizProcEnabled"
:
"Y"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2024-07-05T19:47:33+02:00"
,
"updatedTime"
:
"2024-07-05T19:47:33+02:00"
,
"updatedBy"
:
1
,
"title"
:
"SPA"
,
"relations"
:
{
"parent"
:
[
{
"entityTypeId"
:
3
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"Y"
}
,
{
"entityTypeId"
:
4
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"Y"
}
,
{
"entityTypeId"
:
1
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
2
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
31
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
]
,
"child"
:
[
{
"entityTypeId"
:
3
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
4
,
"isChildrenListEnabled"
:
"N"
,
"isPredefined"
:
"N"
}
]
}
,
"linkedUserFields"
:
{
"CALENDAR_EVENT|UF_CRM_CAL_EVENT"
:
"Y"
,
"TASKS_TASK|UF_CRM_TASK"
:
"Y"
,
"TASKS_TASK_TEMPLATE|UF_CRM_TASK"
:
"N"
}
,
"customSections"
:
[
]
,
"customSectionId"
:
null
}
}
,
"time"
:
{
"start"
:
1720201651.707909
,
"finish"
:
1720201654.748627
,
"duration"
:
3.040717840194702
,
"processing"
:
2.71589994430542
,
"date_start"
:
"2024-07-05T19:47:31+02:00"
,
"date_finish"
:
"2024-07-05T19:47:34+02:00"
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
Root element of the response. Contains a single key
type
type
type
Information about the created SPA
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
400
,
403
{
"error"
:
"INVALID_ARG_VALUE"
,
"error_description"
:
"entityTypeId is out of allowed range"
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
Status
Code
Description
Value
400
INVALID_ARG_VALUE
entityTypeId is out of allowed range
Occurs when an invalid
entityTypeId
is passed
400
ACCESS_DENIED
Access denied
Occurs if the user does not have administrative rights in CRM
403
allowed_only_intranet_user
Action allowed only for intranet users
Occurs if the user is not an intranet user
400
100
Could not find value for parameter
Occurs if the required parameter
fields
is not passed
400
0
Select a workplace where the SPA will be located
Occurs when
isExternal = 'true'
, but
customSectionId
is empty
400
CREATE_DYNAMIC_TYPE_RESTRICTED
Maximum number of SPAs exceeded
Creating an SPA is restricted due to the plan
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
Smart Processes: Overview of Methods
Update User Type crm.type.update
Get the user type by id crm.type.get
Get the user type by entityTypeId crm.type.getByEntityTypeId
Get a list of custom types crm.type.list
Delete user type crm.type.delete
Get Custom Type Fields crm.type.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Update custom type

---

## Update User Type crm.type.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-object-types/crm-type-update

Update User Type crm.type.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update User Type crm.type.update
Method Parameters
Parameter fields
Relations
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with administrative access to the CRM section
This method updates an existing SPA by its identifier
id
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
Identifier of the SPA. Can be obtained using the methods:
crm.type.list
,
crm.type.add
fields
object
Field values (detailed description provided
below
) for updating the SPA
Parameter fields
Parameter fields
Name
type
Description
title
string
Title of the SPA
relations
object
An object containing links to other CRM entities. The structure is described by the object
type.relations
isUseInUserfieldEnabled
boolean
Is the use of the SPA in the user field enabled
linkedUserFields
object
A set of user fields in which this SPA should be displayed. The structure is described by the object
type.linkedUserFields
isAutomationEnabled
boolean
Are automation rules and triggers enabled
isBeginCloseDatesEnabled
boolean
Are the
Start Date
and
End Date
fields enabled
isBizProcEnabled
boolean
Is the use of the business process designer enabled
isCategoriesEnabled
boolean
Are custom Sales Funnels and sales tunnels enabled
isClientEnabled
boolean
Is the
Client
field enabled. When this option is enabled, the SPA has a preset link to
Contacts
and
Companies
isDocumentsEnabled
boolean
Is document printing enabled
isLinkWithProductsEnabled
boolean
Is the link to catalog products enabled
isMycompanyEnabled
boolean
Is the
Your Company Details
field enabled
isObserversEnabled
boolean
Is the
Observers
field enabled
isRecyclebinEnabled
boolean
Is the use of the recycle bin enabled
isSetOpenPermissions
boolean
Should new funnels be made available to everyone
isSourceEnabled
boolean
Are the
Source
and
Additional Information about Source
fields enabled
isStagesEnabled
boolean
Is the use of custom stages and Kanban enabled
isExternal
boolean
Is the SPA external to the CRM (linked to a digital workplace)
This parameter is deprecated. For working with digital workplaces, use the methods
crm.automatedsolution.*
customSectionId
integer
Identifier of the digital workplace
This parameter is deprecated. For working with digital workplaces, use the methods
crm.automatedsolution.*
customSections
array
Array of digital workplaces
This parameter is deprecated. For working with digital workplaces, use the methods
crm.automatedsolution.*
Note
Changes to the SPA settings fields occur only when the modifiable field values are passed.
For example, if you need to disable document printing functionality for the SPA with
id = 128
, you would pass the following parameters:
{
"id"
:
128
,
"fields"
:
{
"isDocumentsEnabled"
:
"N"
}
}
Relations
Relations
Settings must be passed in full; they are completely overwritten.
You cannot change the settings of predefined links (
iPredefined: true
). These settings can be omitted in the request.
If an error occurs while trying to save the passed link settings, it will not be displayed. The settings will simply not be saved.
Code Examples
Code Examples
For the SPA with
id = 20
:
Disable the following settings:
Automation rules and triggers
Start Date
and
End Date
fields
Client
field
Observers
field
Enable the following settings:
Source
and
Additional Information about Source
fields
Use of custom stages and Kanban
Enable display of the SPA in the
Tasks
field
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":20,"fields":{"isAutomationEnabled":"N","isBeginCloseDatesEnabled":"N","isClientEnabled":"N","isObserversEnabled":"N","isSourceEnabled":"Y","isStagesEnabled":"Y","isUseInUserfieldEnabled":"Y","linkedUserFields":{"TASKS_TASK|UF_CRM_TASK":"true"}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.type.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":20,"fields":{"isAutomationEnabled":"N","isBeginCloseDatesEnabled":"N","isClientEnabled":"N","isObserversEnabled":"N","isSourceEnabled":"Y","isStagesEnabled":"Y","isUseInUserfieldEnabled":"Y","linkedUserFields":{"TASKS_TASK|UF_CRM_TASK":"true"}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.type.update
BX24
.
callMethod
(
'crm.type.update'
,
{
id
:
20
,
fields
: {
isAutomationEnabled
:
"N"
,
isBeginCloseDatesEnabled
:
"N"
,
isClientEnabled
:
"N"
,
isObserversEnabled
:
"N"
,
isSourceEnabled
:
"Y"
,
isStagesEnabled
:
"Y"
,
isUseInUserfieldEnabled
:
"Y"
,
linkedUserFields
: {
"TASKS_TASK|UF_CRM_TASK"
:
"true"
,
},
},
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.type.update'
,
[
'id'
=>
20
,
'fields'
=> [
'isAutomationEnabled'
=>
"N"
,
'isBeginCloseDatesEnabled'
=>
"N"
,
'isClientEnabled'
=>
"N"
,
'isObserversEnabled'
=>
"N"
,
'isSourceEnabled'
=>
"Y"
,
'isStagesEnabled'
=>
"Y"
,
'isUseInUserfieldEnabled'
=>
"Y"
,
'linkedUserFields'
=> [
"TASKS_TASK|UF_CRM_TASK"
=>
"true"
,
],
]
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
Suppose for the SPA with
id = 20
you need to:
Remove all entities linked to the SPA (
relations.parent
)
Enable "show in detail form" for
Leads
linked to the SPA
Initial
relations
in the SPA:
{
"relations"
:
{
"parent"
:
[
{
"entityTypeId"
:
31
,
"isChildrenListEnabled"
:
"N"
,
"isPredefined"
:
"N"
}
]
,
"child"
:
[
{
"entityTypeId"
:
1
,
"isChildrenListEnabled"
:
"N"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
2
,
"isChildrenListEnabled"
:
"N"
,
"isPredefined"
:
"N"
}
]
}
}
Final request:
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":20,"fields":{"relations":{"parent":[],"child":[{"entityTypeId":1,"isChildrenListEnabled":"true"},{"entityTypeId":2,"isChildrenListEnabled":"false"}]}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.type.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":20,"fields":{"relations":{"parent":[],"child":[{"entityTypeId":1,"isChildrenListEnabled":"true"},{"entityTypeId":2,"isChildrenListEnabled":"false"}]}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.type.update
BX24
.
callMethod
(
'crm.type.update'
,
{
id
:
20
,
fields
: {
relations
: {
parent
: [],
child
: [
{
"entityTypeId"
:
1
,
"isChildrenListEnabled"
:
"true"
,
},
{
"entityTypeId"
:
2
,
"isChildrenListEnabled"
:
"false"
,
}
],
},
},
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.type.update'
,
[
'id'
=>
20
,
'fields'
=> [
'relations'
=> [
'parent'
=> [],
'child'
=> [
[
"entityTypeId"
=>
1
,
"isChildrenListEnabled"
=>
"true"
,
],
[
"entityTypeId"
=>
2
,
"isChildrenListEnabled"
=>
"false"
,
]
],
],
]
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
"type"
:
{
"id"
:
20
,
"title"
:
"SPA #3"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
1222
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"Y"
,
"isStagesEnabled"
:
"Y"
,
"isBeginCloseDatesEnabled"
:
"N"
,
"isClientEnabled"
:
"N"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"N"
,
"isMycompanyEnabled"
:
"Y"
,
"isDocumentsEnabled"
:
"N"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"N"
,
"isRecyclebinEnabled"
:
"N"
,
"isAutomationEnabled"
:
"N"
,
"isBizProcEnabled"
:
"N"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2024-07-08T17:24:47+02:00"
,
"updatedTime"
:
"2024-07-09T20:55:37+02:00"
,
"updatedBy"
:
1
,
"relations"
:
{
"parent"
:
[
]
,
"child"
:
[
{
"entityTypeId"
:
1
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
2
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
]
}
,
"linkedUserFields"
:
{
"CALENDAR_EVENT|UF_CRM_CAL_EVENT"
:
"N"
,
"TASKS_TASK|UF_CRM_TASK"
:
"Y"
,
"TASKS_TASK_TEMPLATE|UF_CRM_TASK"
:
"N"
}
,
"customSections"
:
[
]
}
}
,
"time"
:
{
"start"
:
1720551426.116454
,
"finish"
:
1720551426.816224
,
"duration"
:
0.6997702121734619
,
"processing"
:
0.20451998710632324
,
"date_start"
:
"2024-07-09T20:57:06+02:00"
,
"date_finish"
:
"2024-07-09T20:57:06+02:00"
,
"operating"
:
0.2044668197631836
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response. Contains a single key
type
type
type
Information about the updated SPA
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
0
,
"error_description"
:
"SPA not found"
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
Status
Code
Description
Value
400
ACCESS_DENIED
Access denied
Occurs if the user does not have administrative rights in CRM
403
allowed_only_intranet_user
Action allowed only for intranet users
Occurs if the user is not an intranet user
400
UPDATE_DYNAMIC_TYPE_RESTRICTED
You cannot change the SPA settings due to your plan's restrictions
SPAs are not available on your plan
400
0
Select a workplace where the SPA will be located
When passing
isExternal = 'true'
, but with an empty
customSectionId
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
Smart Processes: Overview of Methods
Create a new custom type crm.type.add
Get the user type by id crm.type.get
Get a list of custom types crm.type.list
Delete user type crm.type.delete
Get Custom Type Fields crm.type.fields
Copied
Was the article helpful?
Yes
No
Previous
Create a new custom type
Next
Get custom type by id

---

## Get the user type by id crm.type.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-object-types/crm-type-get

Get the user type by id crm.type.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the user type by id crm.type.get
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
Who can execute the method: any user with administrative access to the SPA, or a user with read access to the SPA
The method retrieves information about the SPA with the identifier
id
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
Identifier of the SPA. Can be obtained using the methods:
crm.type.list
,
crm.type.add
Code Examples
Code Examples
Get information about the SPA with
id = 16
.
How to Use Examples in Documentation
cURL (Webhook)
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
'{"id":16}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.type.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":16,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.type.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.type.get'
,
{
id
:
16
,
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
info
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
'crm.type.get'
,
[
'id'
=>
16
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
return
;
}
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
'Error getting CRM type: '
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
'crm.type.get'
,
{
id
:
16
,
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.type.get'
,
[
'id'
=>
16
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
"type"
:
{
"id"
:
16
,
"title"
:
"SPA"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
2024
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"Y"
,
"isStagesEnabled"
:
"Y"
,
"isBeginCloseDatesEnabled"
:
"Y"
,
"isClientEnabled"
:
"Y"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"Y"
,
"isMycompanyEnabled"
:
"Y"
,
"isDocumentsEnabled"
:
"Y"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"Y"
,
"isRecyclebinEnabled"
:
"Y"
,
"isAutomationEnabled"
:
"Y"
,
"isBizProcEnabled"
:
"Y"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2024-07-08T14:46:54+02:00"
,
"updatedTime"
:
"2024-07-08T14:46:54+02:00"
,
"updatedBy"
:
1
,
"relations"
:
{
"parent"
:
[
{
"entityTypeId"
:
3
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"Y"
}
,
{
"entityTypeId"
:
4
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"Y"
}
,
{
"entityTypeId"
:
1
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
2
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
31
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
]
,
"child"
:
[
{
"entityTypeId"
:
3
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
4
,
"isChildrenListEnabled"
:
"N"
,
"isPredefined"
:
"N"
}
]
}
,
"linkedUserFields"
:
{
"CALENDAR_EVENT|UF_CRM_CAL_EVENT"
:
"Y"
,
"TASKS_TASK|UF_CRM_TASK"
:
"Y"
,
"TASKS_TASK_TEMPLATE|UF_CRM_TASK"
:
"N"
}
,
"customSections"
:
[
]
}
}
,
"time"
:
{
"start"
:
1720442829.865672
,
"finish"
:
1720442830.334845
,
"duration"
:
0.46917295455932617
,
"processing"
:
0.13246917724609375
,
"date_start"
:
"2024-07-08T14:47:09+02:00"
,
"date_finish"
:
"2024-07-08T14:47:10+02:00"
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
Root element of the response containing the object
type
with information about the SPA
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
0
,
"error_description"
:
"SPA not found"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action allowed only for intranet users
Occurs if the user is not an intranet user
400
ACCESS_DENIED
Access denied
Occurs if the user does not have administrative rights in CRM or does not have read access to the SPA
400
0
SPA not found
SPA with the provided
id
not found
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
Smart Processes: Overview of Methods
Create a new custom type crm.type.add
Update User Type crm.type.update
Get the user type by entityTypeId crm.type.getByEntityTypeId
Get a list of custom types crm.type.list
Delete user type crm.type.delete
Get Custom Type Fields crm.type.fields
Copied
Was the article helpful?
Yes
No
Previous
Update custom type
Next
Get custom type by entityTypeId

---

## Get the user type by entityTypeId crm.type.getByEntityTypeId

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-object-types/crm-type-get-by-entity-type-id

Get the user type by entityTypeId crm.type.getByEntityTypeId | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the user type by entityTypeId crm.type.getByEntityTypeId
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
Who can execute the method: any user with administrative access to the SPA, or a user with read access to the SPA
The method retrieves information about the SPA with the smart process type identifier
entityTypeId
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the smart process type.
Code Examples
Code Examples
Retrieve information about the smart process with
entityTypeId = 2024
.
How to Use Examples in Documentation
cURL (Webhook)
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
'{"entityTypeId":2024}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.type.getByEntityTypeId
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2024,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.type.getByEntityTypeId
try
{
const
response =
await
$b24.
callMethod
(
'crm.type.getByEntityTypeId'
,
{
entityTypeId
:
2024
,
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
info
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
'crm.type.getByEntityTypeId'
,
[
'entityTypeId'
=>
2024
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
return
;
}
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
'Error getting entity types: '
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
'crm.type.getByEntityTypeId'
,
{
entityTypeId
:
2024
,
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.type.getByEntityTypeId'
,
[
'entityTypeId'
=>
2024
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
"type"
:
{
"id"
:
16
,
"title"
:
"Smart Process"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
2024
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"Y"
,
"isStagesEnabled"
:
"Y"
,
"isBeginCloseDatesEnabled"
:
"Y"
,
"isClientEnabled"
:
"Y"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"Y"
,
"isMycompanyEnabled"
:
"Y"
,
"isDocumentsEnabled"
:
"Y"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"Y"
,
"isRecyclebinEnabled"
:
"Y"
,
"isAutomationEnabled"
:
"Y"
,
"isBizProcEnabled"
:
"Y"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2024-07-08T14:46:54+02:00"
,
"updatedTime"
:
"2024-07-08T14:46:54+02:00"
,
"updatedBy"
:
1
,
"relations"
:
{
"parent"
:
[
{
"entityTypeId"
:
3
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"Y"
}
,
{
"entityTypeId"
:
4
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"Y"
}
,
{
"entityTypeId"
:
1
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
2
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
31
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
]
,
"child"
:
[
{
"entityTypeId"
:
3
,
"isChildrenListEnabled"
:
"Y"
,
"isPredefined"
:
"N"
}
,
{
"entityTypeId"
:
4
,
"isChildrenListEnabled"
:
"N"
,
"isPredefined"
:
"N"
}
]
}
,
"linkedUserFields"
:
{
"CALENDAR_EVENT|UF_CRM_CAL_EVENT"
:
"Y"
,
"TASKS_TASK|UF_CRM_TASK"
:
"Y"
,
"TASKS_TASK_TEMPLATE|UF_CRM_TASK"
:
"N"
}
,
"customSections"
:
[
]
}
}
,
"time"
:
{
"start"
:
1720442829.865672
,
"finish"
:
1720442830.334845
,
"duration"
:
0.46917295455932617
,
"processing"
:
0.13246917724609375
,
"date_start"
:
"2024-07-08T14:47:09+02:00"
,
"date_finish"
:
"2024-07-08T14:47:10+02:00"
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
Root element of the response containing the
type
object with information about the smart process
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
0
,
"error_description"
:
"Smart process not found"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action allowed only for intranet users
Occurs if the user is not an intranet user
400
ACCESS_DENIED
Access denied
Occurs if the user does not have administrative rights in CRM or does not have read access to the SPA
400
0
Smart process not found
Smart process with the provided
entityTypeId
not found
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
Smart Processes: Overview of Methods
Create a new custom type crm.type.add
Update User Type crm.type.update
Get the user type by id crm.type.get
Get a list of custom types crm.type.list
Delete user type crm.type.delete
Get Custom Type Fields crm.type.fields
Copied
Was the article helpful?
Yes
No
Previous
Get custom type by id
Next
Get list of custom types

---

## Get a list of custom types crm.type.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-object-types/crm-type-list

Get a list of custom types crm.type.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of custom types crm.type.list
Method Parameters
Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with administrative access to the CRM section
This method retrieves a list of smart process settings.
Method Parameters
Method Parameters
Name
type
Description
order
object
Object format:
{ field_1: value_1, field_2: value_2, ..., field_n: value_n }
, where
field_n
: the name of the field by which the smart processes will be sorted
value_n
: a
string
value, equal to:
ASC
— ascending order
DESC
— descending order
Possible values for
field
correspond to the fields of the
type
object
filter
object
Object format:
{ field_1: value_1, field_2: value_2, ..., field_n: value_n }
, where
field_n
: the name of the field by which the smart processes will be filtered
value_n
: the filter value
Possible values for
field
correspond to the fields of the
type
object
The filter can have unlimited nesting and number of conditions.
By default, all conditions are combined with each other as
AND
. If you need to use
OR
, you can pass a special key
logic
with the value
OR
.
You can add a prefix to the
field_n
keys to clarify the filter's operation.
Possible prefix values:
>=
— greater than or equal to
>
— greater than
<=
— less than or equal to
<
— less than
@
— IN, an array is passed as the value
!@
— NOT IN, an array is passed as the value
%
— LIKE, substring search. The
%
symbol in the filter value does not need to be passed. The search looks for the substring in any position of the string
=%
— LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
"mol%"
— searches for values starting with "mol"
"%mol"
— searches for values ending with "mol"
"%mol%"
— searches for values where "mol" can be in any position
%=
— LIKE (similar to
=%
)
!%
— NOT LIKE, substring search. The
%
symbol in the filter value does not need to be passed. The search goes from both sides
!=%
— NOT LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
"mol%"
— searches for values not starting with "mol"
"%mol"
— searches for values not ending with "mol"
"%mol%"
— searches for values where the substring "mol" is not present in any position
!%=
— NOT LIKE (similar to
!=%
)
=
— equal, exact match (used by default)
!=
— not equal
!
— not equal
start
integer
This parameter is used for pagination control.
The page size of results is always static — 50 records.
To select the second page of results, pass the value
50
. To select the third page of results — the value
100
, and so on.
The formula for calculating the
start
parameter value:
start = (N-1) * 50
, where
N
— the number of the desired page
Required parameters are marked with *
Examples
Examples
How to Use Examples in Documentation
Get a list of all smart processes where
title
contains either
5
or
0
. Sort the resulting list in descending order by
id
.
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":[{"logic":"OR",{"%title":"5"},{"%title":"0"}]},"order":{"id":"DESC"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.type.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":[{"logic":"OR",{"%title":"5"},{"%title":"0"}]},"order":{"id":"DESC"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.type.list
BX24
.
callMethod
(
'crm.type.list'
,
{
filter
: {
"0"
: {
logic
:
'OR'
,
"0"
: {
"%title"
:
"5"
,
},
"1"
: {
"%title"
:
"0"
,
},
},
},
order
: {
id
:
'DESC'
,
},
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.type.list'
,
[
'filter'
=> [
[
'logic'
=>
'OR'
,
[
'%title'
=>
'5'
,
],
[
'%title'
=>
'0'
,
],
],
],
'order'
=> [
'id'
=>
'DESC'
,
],
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
Get a list of smart processes where:
Automation rules and triggers are enabled (
isAutomationEnabled
)
Business process designer is enabled (
isBizProcEnabled
)
Custom sales funnels and tunnels are enabled (
isCategoriesEnabled
)
Custom stages and Kanban are enabled (
isClientEnabled
)
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":{"isAutomationEnabled":"Y","isBizProcEnabled":"Y","isCategoriesEnabled":"Y","isClientEnabled":"Y"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.type.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":{"isAutomationEnabled":"Y","isBizProcEnabled":"Y","isCategoriesEnabled":"Y","isClientEnabled":"Y"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.type.list
BX24
.
callMethod
(
'crm.type.list'
,
{
filter
: {
isAutomationEnabled
:
'Y'
,
isBizProcEnabled
:
"Y"
,
isCategoriesEnabled
:
"Y"
,
isClientEnabled
:
"Y"
,
},
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.type.list'
,
[
'filter'
=> [
'isAutomationEnabled'
=>
'Y'
,
'isBizProcEnabled'
=>
'Y'
,
'isCategoriesEnabled'
=>
'Y'
,
'isClientEnabled'
=>
'Y'
,
]
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
"types"
:
[
{
"id"
:
37
,
"title"
:
"Smart Process #20"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
1256
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"Y"
,
"isStagesEnabled"
:
"N"
,
"isBeginCloseDatesEnabled"
:
"Y"
,
"isClientEnabled"
:
"Y"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"N"
,
"isMycompanyEnabled"
:
"Y"
,
"isDocumentsEnabled"
:
"Y"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"Y"
,
"isRecyclebinEnabled"
:
"Y"
,
"isAutomationEnabled"
:
"Y"
,
"isBizProcEnabled"
:
"N"
,
"isSetOpenPermissions"
:
"N"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2024-07-08T17:24:55+02:00"
,
"updatedTime"
:
"2024-07-08T17:24:55+02:00"
,
"updatedBy"
:
1
}
,
{
"id"
:
32
,
"title"
:
"Smart Process #15"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
1246
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"N"
,
"isStagesEnabled"
:
"Y"
,
"isBeginCloseDatesEnabled"
:
"N"
,
"isClientEnabled"
:
"Y"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"Y"
,
"isMycompanyEnabled"
:
"N"
,
"isDocumentsEnabled"
:
"N"
,
"isSourceEnabled"
:
"N"
,
"isObserversEnabled"
:
"N"
,
"isRecyclebinEnabled"
:
"N"
,
"isAutomationEnabled"
:
"N"
,
"isBizProcEnabled"
:
"Y"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2024-07-08T17:24:52+02:00"
,
"updatedTime"
:
"2024-07-08T17:24:52+02:00"
,
"updatedBy"
:
1
}
,
{
"id"
:
27
,
"title"
:
"Smart Process #10"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
1236
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"N"
,
"isStagesEnabled"
:
"Y"
,
"isBeginCloseDatesEnabled"
:
"Y"
,
"isClientEnabled"
:
"Y"
,
"isUseInUserfieldEnabled"
:
"N"
,
"isLinkWithProductsEnabled"
:
"N"
,
"isMycompanyEnabled"
:
"Y"
,
"isDocumentsEnabled"
:
"N"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"N"
,
"isRecyclebinEnabled"
:
"N"
,
"isAutomationEnabled"
:
"Y"
,
"isBizProcEnabled"
:
"Y"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2024-07-08T17:24:50+02:00"
,
"updatedTime"
:
"2024-07-08T17:24:50+02:00"
,
"updatedBy"
:
1
}
,
{
"id"
:
22
,
"title"
:
"Smart Process #5"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
1226
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"Y"
,
"isStagesEnabled"
:
"N"
,
"isBeginCloseDatesEnabled"
:
"N"
,
"isClientEnabled"
:
"N"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"Y"
,
"isMycompanyEnabled"
:
"N"
,
"isDocumentsEnabled"
:
"N"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"Y"
,
"isRecyclebinEnabled"
:
"Y"
,
"isAutomationEnabled"
:
"N"
,
"isBizProcEnabled"
:
"Y"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2024-07-08T17:24:48+02:00"
,
"updatedTime"
:
"2024-07-08T17:24:48+02:00"
,
"updatedBy"
:
1
}
]
}
,
"time"
:
{
"start"
:
1720516793.835427
,
"finish"
:
1720516794.697913
,
"duration"
:
0.8624858856201172
,
"processing"
:
0.07323503494262695
,
"date_start"
:
"2024-07-09T11:19:53+02:00"
,
"date_finish"
:
"2024-07-09T11:19:54+02:00"
,
"operating"
:
0
}
,
"total"
:
4
}
Returned Data
Returned Data
Name
type
Description
result
object
The root element of the response. Contains a single key
types
types
type[]
A list of smart processes, each corresponding to the structure of the
type
object
time
time
Information about the request execution time
total
integer
The total number of records found
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
"ACCESS_DENIED"
,
"error_description"
:
"Access denied"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action allowed only for intranet users
Occurs if the user is not an intranet user
400
ACCESS_DENIED
Access denied
Occurs if the user does not have administrative rights in CRM
400
INVALID_ARG_VALUE
Invalid filter: field
'field_n'
is not allowed in filter
Occurs when passing a field
field_n
not present in the smart process to the
filter
parameter
400
INVALID_ARG_VALUE
Invalid filter: field
'field_n'
has invalid value
Occurs when passing an incorrect
value_n
for the field
field_n
in the
filter
parameter
400
INVALID_ARG_VALUE
Invalid order: field
'field_n'
is not allowed in order
Occurs when passing a field
field_n
not present in the smart process to the
order
parameter
400
INVALID_ARG_VALUE
Invalid order: allowed sort directions are
ASC, DESC
. But got
'invalid_value'
for field
'field_n'
Occurs when passing an incorrect
value_n
for the field
field_n
in the
order
parameter
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
Smart Processes: Overview of Methods
Create a new custom type crm.type.add
Update User Type crm.type.update
Get the user type by id crm.type.get
Get the user type by entityTypeId crm.type.getByEntityTypeId
Delete user type crm.type.delete
Get Custom Type Fields crm.type.fields
How to Create a Custom Field in a SPA
How to Create a New Sales Funnel with Stages in a Smart Process
Copied
Was the article helpful?
Yes
No
Previous
Get custom type by entityTypeId
Next
Delete custom type

---

## Delete user type crm.type.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-object-types/crm-type-delete

Delete user type crm.type.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete user type crm.type.delete
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
Who can execute the method: any user with administrative access to the CRM section
This method deletes an existing smart process by the identifier
id
.
You can only delete a smart process if there are no associated elements. If such elements exist, they must be deleted first before deleting the smart process.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the smart process. It can be obtained using the methods:
crm.type.list
,
crm.type.add
Code Examples
Code Examples
Delete the smart process with
id = 16
How to Use Examples in Documentation
cURL (Webhook)
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
'{"id":16}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.type.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":16,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.type.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.type.delete'
,
{
id
:
16
,
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
info
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
'crm.type.delete'
,
[
'id'
=>
16
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
return
;
}
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
'Error deleting CRM type: '
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
'crm.type.delete'
,
{
id
:
16
,
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.type.delete'
,
[
'id'
=>
16
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
[
]
,
"time"
:
{
"start"
:
1720441523.621191
,
"finish"
:
1720441528.162992
,
"duration"
:
4.5418009757995605
,
"processing"
:
4.141964912414551
,
"date_start"
:
"2024-07-08T14:25:23+02:00"
,
"date_finish"
:
"2024-07-08T14:25:28+02:00"
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
Root element of the response. In case of success,
result = []
.
If
result
returns
null
, it is likely that the required parameter
id
was not provided. In this case, the object will not be deleted
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
"BX_ERROR"
,
"error_description"
:
"You cannot delete an entity type that has elements"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action allowed only for intranet users
Occurs if the user is not an intranet user
400
ACCESS_DENIED
Access denied
Occurs if the user does not have administrative rights in CRM
400
BX_ERROR
You cannot delete an entity type that has elements
Occurs when trying to delete a smart process with associated elements
400
0
Smart process not found
Smart process with the provided
id
not found
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
Smart Processes: Overview of Methods
Create a new custom type crm.type.add
Update User Type crm.type.update
Get the user type by id crm.type.get
Get the user type by entityTypeId crm.type.getByEntityTypeId
Get a list of custom types crm.type.list
Get Custom Type Fields crm.type.fields
Copied
Was the article helpful?
Yes
No
Previous
Get list of custom types
Next
Get fields of custom type

---

## Get Custom Type Fields crm.type.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-object-types/crm-type-fields

Get Custom Type Fields crm.type.fields | Bitrix24 REST API and Marketplace Applications
Examples
Get Custom Type Fields crm.type.fields
Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with administrative access to the CRM section
This method retrieves information about the custom fields of the smart process settings.
No parameters.
Examples
Examples
How to Use Examples in Documentation
Get information about the smart process fields
cURL (Webhook)
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
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.type.fields
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{}'
\
https://**put_your_bitrix24_address**/rest/crm.type.fields?auth=**put_access_token_here**
try
{
const
response =
await
$b24.
callMethod
(
'crm.type.fields'
,
{}
);
const
result = response.
getData
().
result
;
console
.
info
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
'crm.type.fields'
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
return
;
}
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
'Error fetching CRM type fields: '
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
'crm.type.fields'
,
{},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.type.fields'
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
"fields"
:
{
"id"
:
{
"type"
:
"integer"
,
"isRequired"
:
false
,
"isReadOnly"
:
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"ID"
,
"upperName"
:
"ID"
}
,
"title"
:
{
"type"
:
"string"
,
"isRequired"
:
true
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Title"
,
"upperName"
:
"TITLE"
}
,
"code"
:
{
"type"
:
"string"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Symbolic Code"
,
"upperName"
:
"CODE"
}
,
"createdBy"
:
{
"type"
:
"user"
,
"isRequired"
:
false
,
"isReadOnly"
:
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Created By"
,
"upperName"
:
"CREATED_BY"
}
,
"entityTypeId"
:
{
"type"
:
"integer"
,
"isRequired"
:
true
,
"isReadOnly"
:
false
,
"isImmutable"
:
true
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Type Identifier"
,
"upperName"
:
"ENTITY_TYPE_ID"
}
,
"customSectionId"
:
{
"type"
:
"integer"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
true
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Digital Workspace"
,
"upperName"
:
"CUSTOM_SECTION_ID"
}
,
"isCategoriesEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Use custom funnels and sales tunnels in the smart process"
,
"upperName"
:
"IS_CATEGORIES_ENABLED"
}
,
"isStagesEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Use custom stages and Kanban in the smart process"
,
"upperName"
:
"IS_STAGES_ENABLED"
}
,
"isBeginCloseDatesEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Fields 'Start Date' and 'End Date'"
,
"upperName"
:
"IS_BEGIN_CLOSE_DATES_ENABLED"
}
,
"isClientEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Field 'Client'"
,
"upperName"
:
"IS_CLIENT_ENABLED"
}
,
"isUseInUserfieldEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Use in user field"
,
"upperName"
:
"IS_USE_IN_USERFIELD_ENABLED"
}
,
"isLinkWithProductsEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Link with catalog products"
,
"upperName"
:
"IS_LINK_WITH_PRODUCTS_ENABLED"
}
,
"isMycompanyEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Field 'Your Company Details'"
,
"upperName"
:
"IS_MYCOMPANY_ENABLED"
}
,
"isDocumentsEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Document Printing"
,
"upperName"
:
"IS_DOCUMENTS_ENABLED"
}
,
"isSourceEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Fields 'Source' and 'Additional Information about Source'"
,
"upperName"
:
"IS_SOURCE_ENABLED"
}
,
"isObserversEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Field 'Observers'"
,
"upperName"
:
"IS_OBSERVERS_ENABLED"
}
,
"isRecyclebinEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Use Recycle Bin"
,
"upperName"
:
"IS_RECYCLEBIN_ENABLED"
}
,
"isAutomationEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Use Automation rules and triggers in the smart process"
,
"upperName"
:
"IS_AUTOMATION_ENABLED"
}
,
"isBizProcEnabled"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Use business process designer in the smart process"
,
"upperName"
:
"IS_BIZ_PROC_ENABLED"
}
,
"isSetOpenPermissions"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Make new funnels available to everyone"
,
"upperName"
:
"IS_SET_OPEN_PERMISSIONS"
}
,
"createdTime"
:
{
"type"
:
"datetime"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Creation Date"
,
"upperName"
:
"CREATED_TIME"
}
,
"updatedTime"
:
{
"type"
:
"datetime"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Modification Date"
,
"upperName"
:
"UPDATED_TIME"
}
,
"updatedBy"
:
{
"type"
:
"user"
,
"isRequired"
:
false
,
"isReadOnly"
:
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Modified By"
,
"upperName"
:
"UPDATED_BY"
}
}
}
,
"time"
:
{
"start"
:
1720436891.554676
,
"finish"
:
1720436894.393655
,
"duration"
:
2.8389790058135986
,
"processing"
:
0.20139384269714355
,
"date_start"
:
"2024-07-08T13:08:11+02:00"
,
"date_finish"
:
"2024-07-08T13:08:14+02:00"
,
"operating"
:
0
}
}
Returned Data
Returned Data
Title
type
Description
result
object
Root element of the response. Contains an object with a single key
fields
fields
object
Object in the format:
{ field_1: value_1, field_2: value_2, ... , field_n: value_n }
, where
field_n
— fields of the smart process settings, and
value_n
— object of type
crm_rest_field_description
time
time
Object containing information about the request execution time
Error Handling
Error Handling
HTTP status:
400
,
403
{
"error"
:
"ACCESS_DENIED"
,
"error_description"
:
"Access Denied"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action allowed only for intranet users
Occurs if the user is not an intranet user
400
ACCESS_DENIED
Access Denied
Occurs if the user does not have administrative rights in CRM
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
Smart Processes: Overview of Methods
Create a new custom type crm.type.add
Update User Type crm.type.update
Get the user type by id crm.type.get
Get the user type by entityTypeId crm.type.getByEntityTypeId
Get a list of custom types crm.type.list
Delete user type crm.type.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete custom type
Next
Create New CRM Entity

---

## Custom Fields in CRM

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-fields/index

Custom Fields in CRM | Bitrix24 REST API and Marketplace Applications
Custom Fields in CRM
Custom Fields in CRM
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
crm
Who can execute the method: any user
Methods for working with custom fields:
Method
Description
crm.userfield.fields
This method returns the description of fields for custom fields.
crm.userfield.types
This method returns a list of custom field types.
crm.userfield.enumeration.fields
This method returns the description of fields for a custom field of type "enumeration" (list).
crm.userfield.settings.fields
This method returns the description of settings fields for the custom field type.
Additional
Additional
Custom Field Settings
How to Create a Custom Field in a SPA
Copied
Was the article helpful?
Yes
No
Previous
Get List of Product Item Fields
Next
Custom Field Types in CRM

---

## Custom Field Types in CRM

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-fields/userfield-type

Custom Field Types in CRM | Bitrix24 REST API and Marketplace Applications
Custom Field Types in CRM
Custom Field Types in CRM
Connection with CRM Objects
Errors When Working with Custom Field Types
Error 400 When Creating a Field
Error 50x When Loading a Field
General Recommendations
Overview of Methods
In CRM, you can create fields of two types:
standard: number, string, date, address, link, file, and so on,
custom: application integrations within the CRM detail form.
With custom field types, you can:
display data in the CRM detail form that does not fit standard field types. Essentially, the data will be stored in the application database in the required format, and the integration will show it within the field.
create interface elements in CRM detail forms. For example, display buttons within a field to control the application.
integrate external services into the CRM detail form. For instance, display dynamic information in a field. Each time the detail form is opened, the field will make a request to the application handler and automatically load fresh data.
Quick navigation:
all methods
User documentation:
Working with custom fields
Connection with CRM Objects
Connection with CRM Objects
Custom field types can be added to:
deals
— use the methods
crm.deal.userfield.add
or
userfieldconfig.add
,
leads
—
crm.lead.userfield.add
or
userfieldconfig.add
,
contacts
—
crm.contact.userfield.add
or
userfieldconfig.add
,
companies
—
crm.company.userfield.add
or
userfieldconfig.add
,
new invoices
—
userfieldconfig.add
,
estimates
—
crm.quote.userfield.add
or
userfieldconfig.add
,
SPAs
—
userfieldconfig.add
.
In the
USER_TYPE_ID
field, pass the value in the form
rest_#ID_application#_#USER_TYPE_ID#
. For example, for an application with
ID: 123
and
USER_TYPE_ID: userfield1
, the value will be
rest_123_test_userfield1
.
To get the application
ID
, use the method
app.info
.
Errors When Working with Custom Field Types
Errors When Working with Custom Field Types
Error 400 When Creating a Field
Error 400 When Creating a Field
When creating a field with a custom type, you may encounter the error
Error! 400: ERROR_CORE: Invalid user type specified. (400)
.
Execute the method
userfieldtype.list
.
If the method returned the field type
USER_TYPE_ID
, proceed to step 2.
If the required field type is not found, register a new type using the method
userfieldtype.add
.
Execute the method
app.info
. This method will check the correctness of the application installation.
If the method returned
INSTALLED = true
, the application is installed correctly.
If the method returned
INSTALLED = false
, execute the method
BX24.installFinish
on the application page. This method will complete the installation of the application with the interface.
BX24
.
init
(
function
(
){
BX24
.
installFinish
();
});
Error 50x When Loading a Field
Error 50x When Loading a Field
If the field was created without errors, but the content is not loading:
Check the URL of the handler
HANDLER
specified during field registration using the method
userfieldtype.list
. To change the
HANDLER
, use the method
userfieldtype.update
.
Ensure that the handler is accessible from the internet:
do not use local addresses: localhost, 192.168.* and other addresses accessible only from the local network,
check the handler's accessibility using public "site availability" services.
Check:
the correctness of the SSL certificate if HTTPS is used,
the absence of blocks in .htaccess or firewall on the handler server,
the returned HTTP codes, which should be 200 OK.
General Recommendations
General Recommendations
Use the HTTPS protocol for handlers; otherwise, browsers may block the loading of application content.
Give clear names to field types: consider the purpose of the field and its connection with the application. The field type cannot be renamed after creation — it can only be deleted and registered again.
Typical use-cases and scenarios
Embed a widget in a lead as a custom property
Widget embedding mechanism
Overview of Methods
Overview of Methods
Scope:
placement, crm
Who can execute the method: administrator
Method
Description
userfieldtype.add
Registers a new type of custom field
userfieldtype.update
Modifies the parameters of an existing field type
userfieldtype.list
Returns a list of registered field types
userfieldtype.delete
Deletes a registered field type
Copied
Was the article helpful?
Yes
No
Previous
Custom Fields in CRM
Next
Get Description for Custom Fields

---

## Get Description for Custom Fields crm.userfield.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-fields/crm-userfield-fields

Get Description for Custom Fields crm.userfield.fields | Bitrix24 REST API and Marketplace Applications
Example
Get Description for Custom Fields crm.userfield.fields
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.userfield.fields
returns the description of fields for custom fields.
Example
Example
CURL (webhook)
CURL (oauth)
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
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.userfield.fields
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{}'
\
https://**put_your_bitrix24_address**/rest/crm.userfield.fields?auth=**put_access_token_here**
try
{
const
response =
await
$b24.
callMethod
(
"crm.userfield.fields"
,
{}
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
(error)
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
'crm.userfield.fields'
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
'Error fetching user fields: '
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
"crm.userfield.fields"
,
{},
function
(
result
)
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
require_once('crest.php');
$result = CRest::call(
'crm.userfield.fields',
[]
);
echo '<PRE>';
print_r($result);
echo '</PRE>';
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Custom Field Types in CRM
Next
Get List of Custom Field Types

---

## Get a list of user field types crm.userfield.types

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-fields/crm-userfield-types

Get a list of user field types crm.userfield.types | Bitrix24 REST API and Marketplace Applications
Get a list of user field types crm.userfield.types
Get a list of user field types crm.userfield.types
Example
Continue exploring
We are still updating this page
Some data may be missing — we will complete it soon.
Scope:
crm
Who can execute the method: any user
The method
crm.userfield.types
returns a description of fields for user-defined fields.
List of user field types. Contains descriptions of types:
string
integer
double
boolean
datetime
enumeration
iblock_section
iblock_element
employee
crm_status
crm
address
money
url
Also, the
types
of user-defined fields registered by the current application will be returned.
Example
Example
CURL (webhook)
CURL (oauth)
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
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.userfield.types
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{}'
\
https://**put_your_bitrix24_address**/rest/crm.userfield.types?auth=**put_access_token_here**
try
{
const
response =
await
$b24.
callMethod
(
"crm.userfield.types"
,
{}
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
(error)
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
$userfieldService
=
$serviceBuilder
->
getCRMScope
()->
userfield
();
$userfieldTypesResult
=
$userfieldService
->
types
();
foreach
(
$userfieldTypesResult
->
getTypes
()
as
$item
) {
print
(
"ID: "
.
$item
->ID .
"\n"
);
print
(
"Title: "
.
$item
->title .
"\n"
);
}
}
catch
(
Throwable
$e
) {
print
(
"Error: "
.
$e
->
getMessage
() .
"\n"
);
}
BX24
.
callMethod
(
"crm.userfield.types"
,
{},
function
(
result
)
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
'crm.userfield.types'
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
How to Use Examples in Documentation
Continue exploring
Continue exploring
How to Set Up Rounding for a Custom Field of Type "Number"
Copied
Was the article helpful?
Yes
No
Previous
Get Description for Custom Fields
Next
Get Description of Fields for List

---

## Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-fields/crm-userfield-enumeration-fields

Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields | Bitrix24 REST API and Marketplace Applications
Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields
Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
crm
Who can execute the method: any user
The method
crm.userfield.enumeration.fields
returns the field descriptions for a custom field of type "enumeration" (list).
Example
Example
JS
PHP
CURL (oauth)
CURL (webhook)
BX24.callMethod(
"crm.userfield.enumeration.fields",
{},
function(result)
{
if(result.error())
console.error(result.error());
else
console.dir(result.data());
}
);
require_once('crest.php');
$result = CRest::call(
'crm.userfield.enumeration.fields',
[]
);
echo '<PRE>';
print_r($result);
echo '</PRE>';
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/crm.userfield.enumeration.fields?auth=**put_access_token_here**
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.userfield.enumeration.fields
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get List of Custom Field Types
Next
Get Description of Settings Fields

---

## Get the field settings description for the custom field type crm.userfield.settings.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/user-defined-fields/crm-userfield-settings-fields

Get the field settings description for the custom field type crm.userfield.settings.fields | Bitrix24 REST API and Marketplace Applications
Get the field settings description for the custom field type crm.userfield.settings.fields
Get the field settings description for the custom field type crm.userfield.settings.fields
Parameters
Example
Continue exploring
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.userfield.settings.fields
returns the field settings description for the custom field type.
Parameters
Parameters
Parameter
Description
type
The type of the custom field. Value from the list returned by the method
crm.userfield.types
.
Required parameters are marked with *
Example
Example
CURL (webhook)
CURL (oauth)
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
'{"type":"string"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.userfield.settings.fields
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"type":"string"}'
\
https://**put_your_bitrix24_address**/rest/crm.userfield.settings.fields?auth=**put_access_token_here**
try
{
const
id =
prompt
(
"Enter ID"
);
const
response =
await
$b24.
callMethod
(
"crm.userfield.settings.fields"
,
{
type
:
"string"
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
(error)
{
console
.
error
(error);
}
$id
=
$_POST
[
'id'
];
try
{
$response
=
$b24Service
->core
->
call
(
'crm.userfield.settings.fields'
,
[
'type'
=>
'string'
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
// Your required data processing logic
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
'Error: '
.
$e
->
getMessage
();
}
var
id =
prompt
(
"Enter ID"
);
BX24
.
callMethod
(
"crm.userfield.settings.fields"
,
{
type
:
"string"
},
function
(
result
)
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
$type
=
'string'
;
// Replace with the required type
$result
=
CRest
::
call
(
'crm.userfield.settings.fields'
,
[
'type'
=>
$type
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
How to Use Examples in Documentation
Continue exploring
Continue exploring
How to Set Up Rounding for a Custom Field of Type "Number"
Copied
Was the article helpful?
Yes
No
Previous
Get Description of Fields for List
Next
Custom Field Settings

---

## Custom Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/userfieldconfig/index

Custom Fields | Bitrix24 REST API and Marketplace Applications
Custom Fields
Custom Fields
Physically, the controller is located in the
main
module. However, it has been extracted as a separate
scope
for REST (it can be accessed via AJAX as
main.userfieldconfig.
).
For the methods to work, the application must have access not only to the
userfieldconfig
scope but also to the scope for which the field settings are being modified. For example, to change the field settings in the Business Automation module, the application must have access to both
userfieldconfig
and
rpa
.
When calling any of the methods, it is necessary to pass the module identifier
moduleId
, which determines the user's access to the fields.
Copied
Was the article helpful?
Yes
No
Previous
Get Description of Settings Fields
Next
Entity Identifiers (entityId)

---

## EntityId Identifiers

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/userfieldconfig/entity-id

EntityId Identifiers | Bitrix24 REST API and Marketplace Applications
CRM
EntityId Identifiers
CRM
RPA
The association of a field with a specific entity is determined by the value of the
entityId
field. Below are the identifiers for different entities:
CRM
CRM
Lead –
CRM_LEAD
Contact –
CRM_CONTACT
Company –
CRM_COMPANY
Deal –
CRM_DEAL
Estimate –
CRM_QUOTE
Invoice –
CRM_INVOICE
SPA –
CRM_ + {ID}
, where ID is the identifier of the SPA (not the type identifier)
New invoices –
CRM_SMART_INVOICE
RPA
RPA
In the RPA module, the field is constructed using the rule
RPA_ + {ID}
, where ID is the identifier of the process.
Copied
Was the article helpful?
Yes
No
Previous
Custom Field Settings
Next
Working with Custom Fields

---

## Custom Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/userfieldconfig/userfieldconfig/index

Custom Fields | Bitrix24 REST API and Marketplace Applications
Custom Fields
Custom Fields
Scope
:
catalog
|
Who can execute the method
:
any user
Methods for working with custom fields:
Method
Description
userfieldconfig.add
This method adds a custom field.
userfieldconfig.delete
This method deletes a custom field.
userfieldconfig.get
This method retrieves data about the settings of the custom field with the identifier id.
userfieldconfig.getTypes
This method returns a set of available types of custom fields for the module moduleId.
userfieldconfig.list
This method retrieves a list of custom field settings.
userfieldconfig.update
This method modifies the value of a field.
Continue Learning
Continue Learning
How to Create a Custom Field in a SPA
Copied
Was the article helpful?
Yes
No
Previous
Entity Identifiers (entityId)
Next
Add Custom Field

---

## Add a New Custom Field userfieldconfig.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/userfieldconfig/userfieldconfig/userfieldconfig-add

Add a New Custom Field userfieldconfig.add | Bitrix24 REST API and Marketplace Applications
Description
Add a New Custom Field userfieldconfig.add
Description
Parameters
Return Value and Example
Return Value
Examples
Continue Learning
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
userfieldconfig, module scope
Who can execute the method: any user
Description
Description
userfieldconfig.add({moduleId: string, field: {}})
This method will add a new custom field.
Parameters
Parameters
Parameter
Description
moduleId
*
String identifier of the module.
field
List of settings for the new field:
entityId
*
- string identifier of the entity.
fieldName
*
- field code. Must be formed according to the template
UF_ + {entity identifier} + _ + {arbitrary string in UPPER_CASE}
. The field code cannot exceed 50 characters.
userTypeId
*
- string identifier of the
field type
.
xmlId - external identifier.
sort - sorting index.
multiple - multiplicity flag (N or Y), default is N. This flag can only be specified when creating the field.
mandatory - required flag (N or Y), default is N.
showFilter - flag to show the field in the filter (N or Y), default is N.
showInList - flag to show the field in the list (N or Y), default is Y.
editInList - flag to allow editing the field in the list (N or Y), default is Y.
isSearchable - flag for the presence of the field value
in the full-text index
(N or Y), default is N.
settings - list of additional settings for the field.
editFormLabel - list of language-dependent names for the field, where the key is the language identifier and the value is the phrase.
enum - array of value options for properties of type "list":
value
*
- value of the option
def - default value flag (N or Y), default is N. Only one can be the default option
sort - sorting index. If not specified, it is generated automatically based on the order of value options
xmlId - external identifier of the option
Required parameters are marked with *
Return Value and Example
Return Value and Example
Return Value
Return Value
The method will return the same data as the
userfieldconfig.get
method on the newly created field.
Examples
Examples
Example of a simple request. This request is sufficient to create a field of type "string".
{
"moduleId"
:
"rpa"
,
"field"
:
{
"entityId"
:
"RPA_1"
,
"fieldName"
:
"UF_RPA_1_NEW_REST_STRING"
,
"userTypeId"
:
"string"
}
}
Creating a field of type "list"
{
"moduleId"
:
"rpa"
,
"field"
:
{
"entityId"
:
"RPA_1"
,
"fieldName"
:
"UF_RPA_1_NEW_REST_STRING"
,
"userTypeId"
:
"enumeration"
}
}
How to Use Examples in Documentation
Continue Learning
Continue Learning
How to Create a Custom Field in a SPA
How to Set Up Rounding for a Custom Field of Type "Number"
Only add necessary fields to the search. Building the index takes time when changing each field value, which can significantly slow down operations with a large number of such fields.
Copied
Was the article helpful?
Yes
No
Previous
Working with Custom Fields
Next
Delete Custom Field Settings

---

## Delete User Field Settings userfieldconfig.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/userfieldconfig/userfieldconfig/userfieldconfig-delete

Delete User Field Settings userfieldconfig.delete | Bitrix24 REST API and Marketplace Applications
Description
Delete User Field Settings userfieldconfig.delete
Description
Parameters
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
userfieldconfig, module scope
Who can execute the method: any user
Description
Description
userfieldconfig.delete({moduleId: string, id: number})
This method will delete the field settings with the identifier id.
Parameters
Parameters
Parameter
Description
moduleId
*
String identifier of the module.
id
*
Identifier of the field settings.
Required parameters are marked with *
Copied
Was the article helpful?
Yes
No
Previous
Add Custom Field
Next
Retrieve Custom Field Settings Data

---

## Get Data on User Field Settings userfieldconfig.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/userfieldconfig/userfieldconfig/userfieldconfig-get

Get Data on User Field Settings userfieldconfig.get | Bitrix24 REST API and Marketplace Applications
Description
Get Data on User Field Settings userfieldconfig.get
Description
Parameters
Examples
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
userfieldconfig, module scope
Who can execute the method: any user
Description
Description
userfieldconfig.get({id: number, moduleId: string})
The method will return data on the settings of the user field with the identifier
id
.
Parameters
Parameters
Parameter
Description
id
*
Identifier of the field settings.
moduleId
*
String identifier of the module.
Required parameters are marked with *
Examples
Examples
Example response:
{
"field"
:
{
"id"
:
"165"
,
"entityId"
:
"RPA_1"
,
"fieldName"
:
"UF_RPA_1_1585069397"
,
"userTypeId"
:
"file"
,
"xmlId"
:
null
,
"sort"
:
"100"
,
"multiple"
:
"Y"
,
"mandatory"
:
"N"
,
"showFilter"
:
"E"
,
"showInList"
:
"Y"
,
"editInList"
:
"Y"
,
"isSearchable"
:
"Y"
,
"settings"
:
{
"SIZE"
:
20
,
"LIST_WIDTH"
:
0
,
"LIST_HEIGHT"
:
0
,
"MAX_SHOW_SIZE"
:
0
,
"MAX_ALLOWED_SIZE"
:
0
,
"EXTENSIONS"
:
[
]
}
,
"languageId"
:
{
"en"
:
"en"
,
"de"
:
"de"
}
,
"editFormLabel"
:
{
"en"
:
""
,
"de"
:
"Multiple file"
}
,
"listColumnLabel"
:
{
"en"
:
null
,
"de"
:
null
}
,
"listFilterLabel"
:
{
"en"
:
null
,
"de"
:
null
}
,
"errorMessage"
:
{
"en"
:
null
,
"de"
:
null
}
,
"helpMessage"
:
{
"en"
:
null
,
"de"
:
null
}
}
}
Where:
id
- identifier
entityId
- string identifier of the object
fieldName
- field code
userTypeId
- string identifier of the field type
xmlId
- external identifier
sort
- sort index
multiple
- multiplicity flag
mandatory
- mandatory flag
showFilter
- flag for showing the field in the filter. For some objects, such as RPA, it returns the value Enabled
E
instead of
Y
showInList
- flag for showing the field in the list
editInList
- flag for allowing editing the field in the list
isSearchable
- flag for the presence of the field value in the full-text index
settings
- list of additional field settings, depending on its type
languageId
- list of language identifiers for which phrases are available
editFormLabel
- list with language-dependent field names, where the key is the language identifier and the value is the phrase
listColumnLabel
,
listFilterLabel
,
errorMessage
,
helpMessage
- similar lists of phrases for various purposes (not used)
enum
- array with value options for properties of type "list" (enumeration), including option identifier, value, default flag, sort index, and external identifier of the option.
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Delete Custom Field Settings
Next
Get Available Custom Field Types

---

## Get a set of available custom field types for the module moduleId userfieldconfig.getTypes

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/userfieldconfig/userfieldconfig/userfieldconfig-get-types

Get a set of available custom field types for the module moduleId userfieldconfig.getTypes | Bitrix24 REST API and Marketplace Applications
Get a set of available custom field types for the module moduleId userfieldconfig.getTypes
Get a set of available custom field types for the module moduleId userfieldconfig.getTypes
Description
Parameters
Examples
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
userfieldconfig, module scope
Who can execute the method: any user
Description
Description
userfieldconfig.
getTypes
({
moduleId
: string})
The method will return a set of available custom field types for the module moduleId.
Parameters
Parameters
Parameter
Description
Available since
moduleId
*
Module identifier.
Required parameters are marked with *
Examples
Examples
Example response
{
"types"
:
{
"employee"
:
{
"userTypeId"
:
"employee"
,
"description"
:
"Link to employee"
}
,
"money"
:
{
"userTypeId"
:
"money"
,
"description"
:
"Money"
}
,
"string"
:
{
"userTypeId"
:
"string"
,
"description"
:
"String"
}
,
"integer"
:
{
"userTypeId"
:
"integer"
,
"description"
:
"Integer"
}
}
}
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Custom Field Settings Data
Next
Get List of Custom Field Settings

---

## Get a List of User Field Settings userfieldconfig.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/userfieldconfig/userfieldconfig/userfieldconfig-list

Get a List of User Field Settings userfieldconfig.list | Bitrix24 REST API and Marketplace Applications
Get a List of User Field Settings userfieldconfig.list
Get a List of User Field Settings userfieldconfig.list
Parameters
Examples
We are still updating this page
Some data may be missing here — we will add it soon.
Scope:
userfieldconfig, module scope
Who can execute the method: any user
userfieldconfig.list({moduleId: string, select: ?{}, order: ?{}, filter: ?{}, start: number = 0})
The method will return a list of user field settings.
Parameters
Parameters
Parameter
Description
moduleId
*
String identifier of the module.
select
Array of fields to display. By default, all fields are shown except for list options and language phrases. To get phrases in the list, you need to pass the language identifier with the key
language
.
order
List to determine the display order, where the key is the field name and the value is ASC or DESC.
filter
List for filtering.
Required parameters are marked with *
Examples
Examples
Example Request
Find all multiple user field settings from the
rpa
module, sorted in descending order by
id
, with all fields and language phrases for the
en
language.
{
"moduleId"
:
"rpa"
,
"select"
:
{
"0"
:
"*"
,
"language"
:
"en"
}
,
"order"
:
{
"id"
:
"DESC"
}
,
"filter"
:
{
"multiple"
:
"Y"
}
}
The response format for language phrases is slightly different, as it contains phrases for only one language.
{
"fields"
:
[
{
"id"
:
"165"
,
"entityId"
:
"RPA_1"
,
"fieldName"
:
"UF_RPA_1_1585069397"
,
"userTypeId"
:
"file"
,
"xmlId"
:
null
,
"sort"
:
"100"
,
"multiple"
:
"Y"
,
"mandatory"
:
"N"
,
"showFilter"
:
"E"
,
"showInList"
:
"Y"
,
"editInList"
:
"Y"
,
"isSearchable"
:
"Y"
,
"settings"
:
{
"SIZE"
:
20
,
"LIST_WIDTH"
:
0
,
"LIST_HEIGHT"
:
0
,
"MAX_SHOW_SIZE"
:
0
,
"MAX_ALLOWED_SIZE"
:
0
,
"EXTENSIONS"
:
[
]
}
,
"languageId"
:
{
"en"
:
"en"
}
,
"editFormLabel"
:
{
"en"
:
"Multiple File"
}
,
"listColumnLabel"
:
null
,
"listFilterLabel"
:
null
,
"errorMessage"
:
null
,
"helpMessage"
:
null
}
,
{
...
}
]
}
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get Available Custom Field Types
Next
Change Custom Field Values

---

## Change the value of the user field userfieldconfig.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/userfieldconfig/userfieldconfig/userfieldconfig-update

Change the value of the user field userfieldconfig.update | Bitrix24 REST API and Marketplace Applications
Change the value of the user field userfieldconfig.update
Change the value of the user field userfieldconfig.update
Parameters
Return value and example
Examples
Continue exploring
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
userfieldconfig, module scope
Who can execute the method: any user
userfieldconfig.update({moduleId: string, id: number, field: {}})
The method changes the value of the field.
Parameters
Parameters
Parameter
Description
moduleId
*
String identifier of the module.
id
*
Identifier of the field settings.
field
List of settings for the new field. Similar to the userfieldconfig.add method, but:
fieldName
- cannot be changed
userTypeId
- cannot be changed
entityId
- cannot be changed
editInList
- cannot be changed
multiple
- cannot be changed
isSearchable
- changing this flag will not trigger automatic rebuilding of the search index. Rebuilding occurs when entities to which the fields are linked are changed
enum
- complete list of all value options for the "list" type property. For this field to be considered,
userTypeId
must be present in fields
id - identifier of the option. Must be present if the option needs to be updated
Required parameters are marked with *
Be careful when working with value options for lists.
Return value and example
Return value and example
The method will return the same data as the userfieldconfig.get method on the modified field.
Examples
Examples
Updating flags and language phrases, without changing value options
{
"moduleId"
:
"rpa"
,
"id"
:
170
,
"field"
:
{
"mandatory"
:
"Y"
,
"editFormLabel"
:
{
"de"
:
"New field name"
}
}
}
Example of removing all value options.
{
"moduleId"
:
"rpa"
,
"id"
:
170
,
"field"
:
{
"userTypeId"
:
"enumeration"
,
"enum"
:
[
[
""
]
]
}
}
Example of partially updating value options.
{
"moduleId"
:
"rpa"
,
"id"
:
170
,
"field"
:
{
"userTypeId"
:
"enumeration"
,
"enum"
:
[
{
"id"
:
29
,
"value"
:
"Old value"
}
,
{
"id"
:
30
,
"value"
:
"Updated value"
}
,
{
"value"
:
"New value"
}
]
}
}
In this example:
The value option with id=29 will remain unchanged
The value of the option with id=30 will change
A new option "New value" will be added
All other options will be removed. If only the id of the option is passed in the request without the value, the option will be deleted.
How to Use Examples in Documentation
Continue exploring
Continue exploring
How to Set Up Rounding for a Custom Field of Type "Number"
Copied
Was the article helpful?
Yes
No
Previous
Get List of Custom Field Settings
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/category/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Sales Funnels (directions in deals) are a set of stages in a kanban for managing deals or elements of SPAs.
You can find more information about funnels (directions) at
helpdesk.bitrix24.com
.
REST methods for working with CRM funnels:
Add a New Sales Funnel crm.category.add
Update Sales Funnel crm.category.update
Get the funnel by Id crm.category.get
Get the list of Sales Funnels crm.category.list
Delete Sales Funnel crm.category.delete
Get Fields of the Sales Funnel crm.category.fields
Was the article helpful?
Yes
No
Previous
Change Custom Field Values
Next
Add a New Funnel

---

## Add a New Sales Funnel crm.category.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/category/crm-category-add

Add a New Sales Funnel crm.category.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add a New Sales Funnel crm.category.add
Method Parameters
Parameter fields
Code Examples
Response Handling
Returned Values
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with administrative access to the CRM section
This method creates a new sales funnel (direction) for the CRM object type with the identifier
entityTypeId
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of the CRM entity for which the new funnel will be created
fields
*
object
Field values (detailed description provided
below
) for adding a new funnel in the form of a structure:
fields
: {
name
:
"value"
,
sort
:
"value"
,
isDefault
:
"value"
,
},
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
name
*
string
Name of the funnel. The name can be:
length cannot exceed
255
characters
cannot be empty
cannot consist solely of spaces, tabs, etc.
Defaults to
-
sort
integer
Sort index.
Cannot be negative. If a value less than zero is passed to
sort
, it will be ignored and set to
sort = 0
Defaults to
500
isDefault
boolean
Indicates whether the funnel is the default funnel. Can have values:
Y
— yes, it is
N
— no
Defaults to
N
.
In deals, the
isDefault
field is not available for modification.
Restrictions on changing the
isDefault
field in SPAs:
the default direction cannot be deleted,
when creating a new direction and passing it the flag
isDefault: "Y"
, the old default direction will cease to be the default direction,
when changing the default direction, it cannot be made a non-default direction,
when changing a non-default direction and passing it the flag
isDefault: "Y"
, the old default direction will cease to be the default direction.
If the display of directions in the interface is disabled for an existing SPA, working with directions via REST is still possible.
Code Examples
Code Examples
Create a new default funnel in the SPA with
entityTypeId = 1152
.
How to Use Examples in Documentation
cURL (Webhook)
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
'{"entityTypeId": 1152, "fields": {"name": "New Default Funnel", "sort": 50, "isDefault": "Y"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.category.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId": 1152, "fields": {"name": "New Default Funnel", "sort": 50, "isDefault": "Y"}, "auth": "**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.category.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.category.add'
,
{
entityTypeId
:
1152
,
fields
: {
name
:
'New Default Funnel'
,
sort
:
50
,
isDefault
:
'Y'
,
},
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
info
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
'crm.category.add'
,
[
'entityTypeId'
=>
1152
,
'fields'
=> [
'name'
=>
'New Default Funnel'
,
'sort'
=>
50
,
'isDefault'
=>
'Y'
,
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
'Error adding category: '
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
"crm.category.add"
,
{
entityTypeId
:
1152
,
fields
: {
name
:
"New Default Funnel"
,
sort
:
50
,
isDefault
:
'Y'
,
},
},
(
result
) =>
{
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
info
(result.
data
());
}
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
'crm.category.add'
,
[
'entityTypeId'
=>
1152
,
'fields'
=> [
'name'
=>
"New Default Funnel"
,
'sort'
=>
50
,
'isDefault'
=>
'Y'
,
]
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
"category"
:
{
"id"
:
5
,
"name"
:
"New Default Funnel"
,
"sort"
:
50
,
"entityTypeId"
:
1152
,
"isDefault"
:
"Y"
}
}
,
"time"
:
{
"start"
:
1718116794.208887
,
"finish"
:
1718116794.666272
,
"duration"
:
0.4573848247528076
,
"processing"
:
0.1496260166168213
,
"date_start"
:
"2024-06-11T16:39:54+02:00"
,
"date_finish"
:
"2024-06-11T16:39:54+02:00"
,
"operating"
:
0
}
}
Returned Values
Returned Values
Name
type
Description
result
object
Root element of the response. Contains the
category
object with information about the funnel
time
object
Object containing information about the execution time of the request
Object category
Object category
Name
type
Description
id
integer
Identifier of the funnel (direction)
name
string
Name of the funnel
sort
integer
Sort index
entityTypeId
integer
Identifier of the
system
or
user-defined type
to which the funnel belongs
isDefault
boolean
Indicates whether the funnel is the default funnel
originId
string
Identifier of the data source.
Exists only in deals
originatorId
string
Identifier of the element in the data source.
Exists only in deals
isSystem
boolean
Indicates whether the funnel is a system funnel.
Exists only in SPAs
code
string
Alias for system funnels.
Exists only in SPAs
Error Handling
Error Handling
HTTP Status:
160
,
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"SPA not found"
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
Value
NOT_FOUND
SPA not found
Occurs with incorrect values for
entityTypeId
ENTITY_TYPE_NOT_SUPPORTED
Entity type
{entityTypeName}
is not supported
Occurs if the CRM object does not support funnels
ADDING_DISABLED
Adding a system category is prohibited
Occurs when attempting to create a system funnel in SPAs
ACCESS_DENIED
Access denied
Occurs if the user does not have sufficient rights to add a funnel
0
Field 'NAME' is required
Occurs if the required field
name
is not provided
0
Default client category does not support updating default state
Occurs when attempting to create a default funnel for
contacts
or
companies
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
Update Sales Funnel crm.category.update
Get the funnel by Id crm.category.get
Get the list of Sales Funnels crm.category.list
Delete Sales Funnel crm.category.delete
Get Fields of the Sales Funnel crm.category.fields
How to Create a New Sales Funnel with Stages in a Smart Process
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Funnel

---

## Update Sales Funnel crm.category.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/category/crm-category-update

Update Sales Funnel crm.category.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Sales Funnel crm.category.update
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
Who can execute the method: any user with administrative access to the CRM section
This method updates the funnel (direction) with the identifier
id
, setting new values for the fields from
fields
. If any field is missing in
fields
, its value will remain unchanged.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of CRM entities for which the funnel will be updated
id
*
integer
Identifier of the funnel. It can be obtained using the
crm.category.list
method or when creating a funnel with the
crm.category.add
method
fields
*
object
Field values (detailed description provided
below
) for updating the funnel fields in the form of a structure:
fields
: {
name
:
"value"
,
sort
:
"value"
,
isDefault
:
"value"
,
},
Parameter fields
Parameter fields
Name
type
Description
name
string
Name of the funnel. The name can be:
length cannot exceed
255
characters
cannot be empty
cannot consist solely of spaces, tabs, etc.
Defaults to
-
sort
integer
Sort index.
Cannot be negative. If a value less than zero is passed to
sort
, it will be ignored and
sort = 0
will be set.
Defaults to
500
isDefault
boolean
Indicates whether the funnel is the default funnel. Can have values:
Y
— yes, it is
N
— no
Defaults to
N
In deals, the
isDefault
field is not available for modification.
You can find out if the field is immutable using the
crm.category.fields
method. Immutable fields have the property
isReadonly = true
Code Examples
Code Examples
How to update a funnel with
id = 4
in an SPA with
entityTypeId = 1152
How to Use Examples in Documentation
cURL (Webhook)
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
'{"entityTypeId":1152,"id":4,"fields":{"name":"New Funnel Name","sort":1000,"isDefault":"Y"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.category.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1152,"id":4,"fields":{"name":"New Funnel Name","sort":1000,"isDefault":"Y"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.category.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.category.update"
,
{
entityTypeId
:
1152
,
id
:
4
,
fields
: {
name
:
"New Funnel Name"
,
sort
:
1000
,
isDefault
:
"Y"
,
},
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
info
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
'crm.category.update'
,
[
'entityTypeId'
=>
1152
,
'id'
=>
4
,
'fields'
=> [
'name'
=>
'New Funnel Name'
,
'sort'
=>
1000
,
'isDefault'
=>
'Y'
,
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
// Your data processing logic
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
'Error updating category: '
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
"crm.category.update"
,
{
entityTypeId
:
1152
,
id
:
4
,
fields
: {
name
:
"New Funnel Name"
,
sort
:
1000
,
isDefault
:
"Y"
,
},
},
(
result
) =>
{
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
info
(result.
data
());
}
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
'crm.category.update'
,
[
'entityTypeId'
=>
1152
,
'id'
=>
4
,
'fields'
=> [
'name'
=>
"New Funnel Name"
,
'sort'
=>
1000
,
'isDefault'
=>
"Y"
]
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
"category"
:
{
"id"
:
4
,
"name"
:
"New Funnel Name"
,
"sort"
:
1000
,
"entityTypeId"
:
1152
,
"isDefault"
:
"Y"
}
}
,
"time"
:
{
"start"
:
1718359296.368324
,
"finish"
:
1718359296.65352
,
"duration"
:
0.28519606590270996
,
"processing"
:
0.03645014762878418
,
"date_start"
:
"2024-06-14T12:01:36+02:00"
,
"date_finish"
:
"2024-06-14T12:01:36+02:00"
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
Root element of the response. Contains the
category
object
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
"Smart process not found"
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
Value
NOT_FOUND
Smart process not found
Occurs with incorrect values for
entityTypeId
ENTITY_TYPE_NOT_SUPPORTED
Entity type
{entityTypeName}
is not supported
Occurs if the CRM object does not support funnels
NOT_FOUND
Element not found
Occurs if the funnel being updated does not exist
ACCESS_DENIED
Access denied
Occurs if the user updating the funnel does not have sufficient rights
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
Add a New Sales Funnel crm.category.add
Get the funnel by Id crm.category.get
Get the list of Sales Funnels crm.category.list
Delete Sales Funnel crm.category.delete
Get Fields of the Sales Funnel crm.category.fields
Copied
Was the article helpful?
Yes
No
Previous
Add a New Funnel
Next
Get Funnel by Id

---

## Get the funnel by Id crm.category.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/category/crm-category-get

Get the funnel by Id crm.category.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the funnel by Id crm.category.get
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
Who can execute the method: any user with "Read" access permission to the funnel
This method retrieves information about the funnel (direction) with the identifier
id
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of the CRM object for which we want to get the funnel
id
*
integer
Funnel identifier. Can be obtained using the
crm.category.list
method or when creating a funnel using the
crm.category.add
method
Code Examples
Code Examples
How to get information about the funnel with
id
=
1
, located in deals.
How to Use Examples in Documentation
cURL (Webhook)
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
'{"entityTypeId":2,"id":1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.category.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"id":1,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.category.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.category.get'
,
{
entityTypeId
:
2
,
id
:
1
,
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
info
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
'crm.category.get'
,
[
'entityTypeId'
=>
2
,
'id'
=>
1
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
'Info: '
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
'Error getting category: '
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
"crm.category.get"
,
{
entityTypeId
:
2
,
id
:
1
,
},
(
result
) =>
{
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
info
(result.
data
());
}
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
'crm.category.get'
,
[
'entityTypeId'
=>
2
,
'id'
=>
1
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
"category"
:
{
"id"
:
1
,
"name"
:
"New funnel #1"
,
"sort"
:
200
,
"entityTypeId"
:
2
,
"isDefault"
:
"N"
,
"originId"
:
""
,
"originatorId"
:
""
}
}
,
"time"
:
{
"start"
:
1718291429.253404
,
"finish"
:
1718291429.654617
,
"duration"
:
0.4012131690979004
,
"processing"
:
0.025265216827392578
,
"date_start"
:
"2024-06-13T17:10:29+02:00"
,
"date_finish"
:
"2024-06-13T17:10:29+02:00"
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
Root element of the response. Contains the
category
object
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
"Element not found"
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
Value
NOT_FOUND
SPA not found
Occurs with incorrect values for
entityTypeId
ENTITY_TYPE_NOT_SUPPORTED
Entity type
{entityTypeName}
is not supported
Occurs if the CRM object does not support funnels
NOT_FOUND
Element not found
Occurs if no funnels exist with such parameters
ACCESS_DENIED
Access denied
Occurs if the user does not have permission to view elements of this funnel
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
Add a New Sales Funnel crm.category.add
Update Sales Funnel crm.category.update
Get the list of Sales Funnels crm.category.list
Delete Sales Funnel crm.category.delete
Get Fields of the Sales Funnel crm.category.fields
Copied
Was the article helpful?
Yes
No
Previous
Update Funnel
Next
Get List of Funnels

---

## Get the list of Sales Funnels crm.category.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/category/crm-category-list

Get the list of Sales Funnels crm.category.list | Bitrix24 REST API and Marketplace Applications
Get the list of Sales Funnels crm.category.list
Get the list of Sales Funnels crm.category.list
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
The method retrieves a list of sales funnels (directions) that belong to the CRM object type with the identifier
entityTypeId
.
Which funnels will be included in the list
The list of returned funnels is filtered by access permissions. This means that if a user does not have permission to read a specific funnel, it will not be included in the response.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of CRM entities for which to retrieve the list of funnels
Code Examples
Code Examples
Get the list of funnels for deals.
How to Use Examples in Documentation
cURL (Webhook)
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
'{"entityTypeId":2}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.category.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.category.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.category.list'
,
{
entityTypeId
:
2
,
},
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
'crm.category.list'
, {
entityTypeId
:
2
},
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.category.list'
, {
entityTypeId
:
2
},
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
'crm.category.list'
,
[
'entityTypeId'
=>
2
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
echo
'Error: '
.
$result
->
error
();
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
'Error fetching category list: '
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
"crm.category.list"
,
{
entityTypeId
:
2
,
},
(
result
) =>
{
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
info
(result.
data
());
}
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
'crm.category.list'
,
[
'entityTypeId'
=>
2
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
"categories"
:
[
{
"id"
:
9
,
"name"
:
"Funnel with Original Name"
,
"sort"
:
200
,
"entityTypeId"
:
2
,
"isDefault"
:
"N"
,
"originId"
:
""
,
"originatorId"
:
""
}
,
{
"id"
:
10
,
"name"
:
"Lead Route"
,
"sort"
:
200
,
"entityTypeId"
:
2
,
"isDefault"
:
"N"
,
"originId"
:
""
,
"originatorId"
:
""
}
,
{
"id"
:
11
,
"name"
:
"Path to Success"
,
"sort"
:
200
,
"entityTypeId"
:
2
,
"isDefault"
:
"N"
,
"originId"
:
""
,
"originatorId"
:
""
}
,
{
"id"
:
0
,
"name"
:
"General"
,
"sort"
:
300
,
"entityTypeId"
:
2
,
"isDefault"
:
"Y"
}
]
}
,
"total"
:
4
,
"time"
:
{
"start"
:
1718293410.373042
,
"finish"
:
1718293425.947633
,
"duration"
:
15.574590921401978
,
"processing"
:
15.16909408569336
,
"date_start"
:
"2024-06-13T17:43:30+02:00"
,
"date_finish"
:
"2024-06-13T17:43:45+02:00"
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
The root element of the response. Contains a single element with the key
categories
, which represents an array of funnels. The structure of an individual funnel corresponds to the
category
object
total
integer
The total number of funnels belonging to a specific
entityTypeId
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
"Smart process not found"
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
Value
NOT_FOUND
Smart process not found
Occurs when invalid values for
entityTypeId
are provided
ENTITY_TYPE_NOT_SUPPORTED
Entity type
{entityTypeName}
is not supported
Occurs if the CRM object does not support funnels
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
Add a New Sales Funnel crm.category.add
Update Sales Funnel crm.category.update
Get the funnel by Id crm.category.get
Delete Sales Funnel crm.category.delete
Get Fields of the Sales Funnel crm.category.fields
How to Filter Items by Stage Name
How to Create a Vendor in CRM
How to Get a List of Vendors
Copied
Was the article helpful?
Yes
No
Previous
Get Funnel by Id
Next
Delete Funnel

---

## Delete Sales Funnel crm.category.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/category/crm-category-delete

Delete Sales Funnel crm.category.delete | Bitrix24 REST API and Marketplace Applications
Delete Sales Funnel crm.category.delete
Delete Sales Funnel crm.category.delete
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
Who can execute the method: any user with administrative access to the CRM section
This method deletes a funnel (direction) with the identifier
id
.
Cannot delete:
Default funnels
Funnels that have at least one element
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of the CRM entity from which the funnel will be deleted
id
*
integer
Identifier of the funnel to be deleted. Can be obtained using the
crm.category.list
method or when creating a funnel with the
crm.category.add
method
Code Examples
Code Examples
Delete the funnel with
id = 5
, located in deals.
How to Use Examples in Documentation
cURL (Webhook)
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
'{"entityTypeId":2,"id":5}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.category.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"id":5,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.category.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.category.delete'
,
{
entityTypeId
:
2
,
id
:
5
,
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
info
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
'crm.category.delete'
,
[
'entityTypeId'
=>
2
,
'id'
=>
5
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
'Error deleting category: '
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
"crm.category.delete"
,
{
entityTypeId
:
2
,
id
:
5
,
},
(
result
) =>
{
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
info
(result.
data
());
}
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
'crm.category.delete'
,
[
'entityTypeId'
=>
2
,
'id'
=>
5
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
null
,
"time"
:
{
"start"
:
1718288046.047386
,
"finish"
:
1718288046.892514
,
"duration"
:
0.845128059387207
,
"processing"
:
0.4207921028137207
,
"date_start"
:
"2024-06-13T16:14:06+02:00"
,
"date_finish"
:
"2024-06-13T16:14:06+02:00"
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
null
Root element of the response, equal to
null
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
160
,
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Element not found"
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
Value
NOT_FOUND
SPA not found
Occurs with incorrect values for
entityTypeId
ENTITY_TYPE_NOT_SUPPORTED
Entity type
{entityTypeName}
is not supported
Occurs if the CRM object does not support funnels
NOT_FOUND
Element not found
Occurs if the funnel to be deleted does not exist
REMOVING_DISABLED
Deletion of system category is prohibited
Occurs when attempting to delete a system funnel
ACCESS_DENIED
Access denied
Occurs if the user deleting the funnel does not have sufficient rights
0
Deals related to the funnel
{categoryName}
found
Occurs if the funnel to be deleted has at least one element. Relevant only for
deals
0
Default deal category cannot be deleted
Occurs when attempting to delete a default funnel. Relevant only for
deals
BX_ERROR
Elements related to the funnel found
Occurs if the funnel to be deleted has at least one element. Relevant for
SPAs
BX_ERROR
This funnel is the default funnel
Occurs when attempting to delete a default funnel. Relevant for
SPAs
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
Add a New Sales Funnel crm.category.add
Update Sales Funnel crm.category.update
Get the funnel by Id crm.category.get
Get the list of Sales Funnels crm.category.list
Get Fields of the Sales Funnel crm.category.fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of Funnels
Next
Get Funnel Fields

---

## Get Fields of the Sales Funnel crm.category.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/category/crm-category-fields

Get Fields of the Sales Funnel crm.category.fields | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Fields of the Sales Funnel crm.category.fields
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
The method retrieves information about the fields of the sales funnels (directions) of the CRM object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of CRM objects for which to retrieve information about the funnel fields
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (Webhook)
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
'{"entityTypeId":2}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.category.fields
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.category.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.category.fields"
,
{
entityTypeId
:
2
,
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
info
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
'crm.category.fields'
,
[
'entityTypeId'
=>
2
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
echo
'Error: '
.
$result
->
error
();
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
'Error calling crm.category.fields: '
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
"crm.category.fields"
,
{
entityTypeId
:
2
,
},
(
result
) =>
{
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
info
(result.
data
());
}
},
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
'crm.category.fields'
,
[
'entityTypeId'
=>
2
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
"fields"
:
{
"id"
:
{
"type"
:
"integer"
,
"isRequired"
:
false
,
"isReadOnly"
:
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"ID"
,
"upperName"
:
"ID"
}
,
"name"
:
{
"type"
:
"string"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"NAME"
,
"upperName"
:
"NAME"
}
,
"sort"
:
{
"type"
:
"integer"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"SORT"
,
"upperName"
:
"SORT"
}
,
"entityTypeId"
:
{
"type"
:
"integer"
,
"isRequired"
:
true
,
"isReadOnly"
:
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"ENTITY_TYPE_ID"
,
"upperName"
:
"ENTITY_TYPE_ID"
}
,
"isDefault"
:
{
"type"
:
"boolean"
,
"isRequired"
:
false
,
"isReadOnly"
:
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"IS_DEFAULT"
,
"upperName"
:
"IS_DEFAULT"
}
,
"originId"
:
{
"type"
:
"string"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"ORIGIN_ID"
,
"upperName"
:
"ORIGIN_ID"
}
,
"originatorId"
:
{
"type"
:
"string"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"ORIGINATOR_ID"
,
"upperName"
:
"ORIGINATOR_ID"
}
}
}
,
"time"
:
{
"start"
:
1718098629.350263
,
"finish"
:
1718098629.800741
,
"duration"
:
0.45047783851623535
,
"processing"
:
0.02919292449951172
,
"date_start"
:
"2024-06-11T11:37:09+02:00"
,
"date_finish"
:
"2024-06-11T11:37:09+02:00"
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
Object containing a list of available fields in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field_N
is the identifier of the
object field
, and
value
is an object of type
crm_rest_field_description
time
time
Information about the execution time of the request
Field Descriptions
Field Descriptions
Name
type
Description
id
integer
Identifier of the funnel (direction)
name
string
Name of the funnel
sort
integer
Sort index
entityTypeId
integer
Identifier of the
system
or
user-defined type
to which the funnel belongs
isDefault
boolean
Indicates whether the funnel is the default funnel
originId
string
Identifier of the data source.
Exists only in deals
originatorId
string
Identifier of the item in the data source.
Exists only in deals
isSystem
boolean
Indicates whether the funnel is a system funnel.
Exists only in SPAs
code
string
Alias for system funnels.
Exists only in SPAs
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
"SPA not found"
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
Value
NOT_FOUND
SPA not found
Occurs with incorrect values for
entityTypeId
ENTITY_TYPE_NOT_SUPPORTED
Entity type
{entityTypeName}
is not supported
Occurs if the CRM entity does not support funnels
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
Add a New Sales Funnel crm.category.add
Update Sales Funnel crm.category.update
Get the funnel by Id crm.category.get
Get the list of Sales Funnels crm.category.list
Delete Sales Funnel crm.category.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete Funnel
Next
Import

---

## Configuring Sections in the Detail Form of CRM Entities

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/item-details-configuration/index

Configuring Sections in the Detail Form of CRM Entities | Bitrix24 REST API and Marketplace Applications
Configuring Sections in the Detail Form of CRM Entities
Configuring Sections in the Detail Form of CRM Entities
These methods allow you to configure sections within the detail form of CRM entities.
REST Methods
REST Methods
Get Parameters of CRM Item Detail Configuration
Set Parameters for CRM Item Card crm.item.details.configuration.set
Reset Item Card Parameters crm.item.details.configuration.reset
Set Common Detail for All Users crm.item.details.configuration.forceCommonScopeForAll
Was the article helpful?
Yes
No
Previous
Get List of Deliveries
Next
Get CRM Entity Detail Form Parameters

---

## Get Parameters of CRM Item Detail Configuration

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/item-details-configuration/crm-item-details-configuration-get

Get Parameters of CRM Item Detail Configuration | Bitrix24 REST API and Marketplace Applications
Get Parameters of CRM Item Detail Configuration
Get Parameters of CRM Item Detail Configuration
Method Parameters
extras
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: access rights during method execution depend on the provided data:
Any user has the right to access their own and shared settings
A user can access another user's settings only if they are an administrator
The method returns the settings of the detail form for a specific CRM entity. It can work with both personal settings of the specified user and shared settings defined for all users.
Note
The settings for repeat lead detail forms may differ from those of simple lead detail forms. The parameter
extras.leadCustomerType
is used to switch between lead detail form settings.
The settings for the CRM entity detail form may vary depending on their Sales Funnel. The parameters used for switching are:
extras.categoryId
— for SPAs
extras.dealCategoryId
— for deals
Copied
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of CRM entities
userId
user
Identifier of the user whose configuration you want to retrieve.
If this parameter is not provided, the
userId
of the user calling this method will be used.
Required only when requesting personal settings
scope
string
Scope of the settings. Allowed values:
'P'
— personal settings
'C'
— shared settings
By default, the value is
'P'
extras
object
Additional parameters. Possible values and their structure are described
below
extras
extras
The
extras
parameter depends on the CRM entity.
CRM Entity
Name
Description
SPA
categoryId
Identifier of the SPA funnel. Can be obtained using
crm.category.list
.
If not specified, the default funnel identifier for this SPA will be used
Deal
dealCategoryId
Identifier of the deal funnel. Can be obtained using
crm.category.list
.
If not specified, the default funnel identifier for deals will be used
Lead
leadCustomerType
Type of leads.
Possible values:
1
— simple leads
2
— repeat leads
Code Examples
Code Examples
How to Use Examples in Documentation
Get the shared configuration of item details for deals in the funnel with
id = 9
, for the user with
id = 1
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"userId":1,"scope":"C","extras":{"dealCategoryId":9}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.details.configuration.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"userId":1,"scope":"C","extras":{"dealCategoryId":9},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.details.configuration.get
BX24
.
callMethod
(
'crm.item.details.configuration.get'
,
{
entityTypeId
:
2
,
userId
:
1
,
scope
:
"C"
,
extras
: {
dealCategoryId
:
9
,
},
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.item.details.configuration.get'
,
[
'entityTypeId'
=>
2
,
'userId'
=>
1
,
'scope'
=>
"C"
,
'extras'
=> [
'dealCategoryId'
=>
9
,
]
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
Get the personal configuration of item details for the SPA with
entityTypeId = 1032
in the funnel with
id = 5
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1032,"extras":{"categoryId":5}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.details.configuration.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1032,"extras":{"categoryId":5},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.details.configuration.get
BX24
.
callMethod
(
'crm.item.details.configuration.get'
,
{
entityTypeId
:
1032
,
extras
: {
categoryId
:
5
,
},
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.item.details.configuration.get'
,
[
'entityTypeId'
=>
1032
,
'extras'
=> [
'categoryId'
=>
5
,
]
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
[
{
"name"
:
"main"
,
"title"
:
"About the Deal"
,
"type"
:
"section"
,
"elements"
:
[
{
"name"
:
"TITLE"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"STAGE_ID"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"OPPORTUNITY_WITH_CURRENCY"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"CLOSEDATE"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"CLIENT"
,
"optionFlags"
:
"1"
,
"options"
:
{
"defaultCountry"
:
"US"
}
}
,
{
"name"
:
"UF_CRM_1686898039656"
,
"optionFlags"
:
"1"
}
]
}
,
{
"name"
:
"additional"
,
"title"
:
"Additional"
,
"type"
:
"section"
,
"elements"
:
[
{
"name"
:
"TYPE_ID"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"SOURCE_ID"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"SOURCE_DESCRIPTION"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"BEGINDATE"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"OPENED"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"ASSIGNED_BY_ID"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"OBSERVER"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"COMMENTS"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"UTM"
,
"optionFlags"
:
"0"
}
]
}
,
{
"name"
:
"products"
,
"title"
:
"Products"
,
"type"
:
"section"
,
"elements"
:
[
{
"name"
:
"PRODUCT_ROW_SUMMARY"
,
"optionFlags"
:
"0"
}
]
}
,
{
"name"
:
"recurring"
,
"title"
:
"Recurring Deal"
,
"type"
:
"section"
,
"elements"
:
[
{
"name"
:
"RECURRING"
,
"optionFlags"
:
"0"
}
]
}
]
,
"time"
:
{
"start"
:
1720624891.017344
,
"finish"
:
1720624891.405621
,
"duration"
:
0.3882770538330078
,
"processing"
:
0.02097320556640625
,
"date_start"
:
"2024-07-10T17:21:31+02:00"
,
"date_finish"
:
"2024-07-10T17:21:31+02:00"
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
section[]
|
null
Root element of the response. Contains the configuration of the sections of the detail form. Returns
null
if there is no configuration
time
time
Information about the execution time of the request
section
section
Describes an individual section with fields within the item detail form
Name
type
Description
name
string
Unique name of the section used for identification
title
string
Title of the section
type
string
Type of the section
elements
section_element[]
List of fields displayed in the entity detail form with additional settings
section_element
section_element
Configuration of an individual field within a section
Name
type
Description
name
string
Identifier of the field
optionFlags
string
Values:
"1"
— always show
"0"
— not always show
options
object
Additional options for the field
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
""
,
"error_description"
:
"Parameter 'entityTypeId' is not defined"
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
Value
Empty value
Parameter 'entityTypeId' is not defined
Required parameter
entityTypeId
is not provided
Empty value
The entity type '
entityTypeName
' is not supported in the current context.
The method does not support this entity type
Empty value
Access denied.
The user does not have administrative rights
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
Configuring Sections in the Detail Form of CRM Entities
Set Parameters for CRM Item Card crm.item.details.configuration.set
Reset Item Card Parameters crm.item.details.configuration.reset
Set Common Detail for All Users crm.item.details.configuration.forceCommonScopeForAll
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Set CRM Entity Detail Form Parameters

---

## Set Parameters for CRM Item Card crm.item.details.configuration.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/item-details-configuration/crm-item-details-configuration-set

Set Parameters for CRM Item Card crm.item.details.configuration.set | Bitrix24 REST API and Marketplace Applications
Set Parameters for CRM Item Card crm.item.details.configuration.set
Set Parameters for CRM Item Card crm.item.details.configuration.set
Method Parameters
section
extras
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Method name:
crm.item.details.configuration.set
Scope:
crm
Who can execute the method: access permission checks depend on the provided data:
Any user can set their personal settings
A user can set common and others' settings only if they are an administrator
The method sets the settings for the card of a specific CRM object. It records personal settings for the specified user or common settings for all users.
Note
The settings for repeat lead detail forms may differ from those of simple lead detail forms. The parameter
extras.leadCustomerType
is used to switch between lead detail form settings.
The settings for the CRM entity detail form may vary depending on their Sales Funnel. The parameters used for switching are:
extras.categoryId
— for SPAs
extras.dealCategoryId
— for deals
Copied
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of CRM objects
data
*
section[]
List of
section
describing the configuration of field sections in the item card. The structure of
section
is described below
userId
user
Identifier of the user for whom you want to set the configuration.
If the parameter is not provided, the
userId
of the user calling this method will be used.
Required only when requesting personal settings
scope
string
Scope of the settings. Allowed values:
'P'
— personal settings
'C'
— common settings
By default, the value is
'P'
extras
object
Additional parameters. Possible values and their structure are described
below
section
section
Describes a specific section with fields within the item card.
Required parameters are marked with *
Name
type
Description
name
*
string
Unique name of the section
title
*
string
Title of the section. Displayed in the item card
type
*
string
Type of the section.
Currently, only the value
'section'
is available
elements
section_element[]
Array of
section_element
, describing the configuration of fields in the section
section_element
section_element
Configuration of a specific field within the section.
Required parameters are marked with *
Name
type
Description
name
*
string
Field identifier. The list of available fields can be found using
crm.item.fields
optionFlags
integer
Should the field always be shown:
1
— yes
0
— no
By default, the value is
0
options
object
Additional
options list
for the field
section_element.options
section_element.options
Name
type
Fields where the option is available
Description
Default
defaultAddressType
integer
ADDRESS
Identifier of the default address type. To find possible address types, use
crm.enum.addresstype
Computed
defaultCountry
string
PHONE
CLIENT
COMPANY
CONTACT
MYCOMPANY_ID
Country code for the default phone number format — a string of two Latin letters. For example,
"GB"
Computed
isPayButtonVisible
boolean
OPPORTUNITY_WITH_CURRENCY
Is the payment acceptance button shown.
Possible values:
'true'
— shown
'false'
— hidden
'true'
isPaymentDocumentsVisible
boolean
OPPORTUNITY_WITH_CURRENCY
Is the "Payment and Delivery" block shown.
Possible values:
'true'
— shown
'false'
— hidden
'true'
extras
extras
The
extras
parameter depends on the CRM object.
CRM Object
Name
Description
SPA
categoryId
Identifier of the SPA funnel. Can be obtained using
crm.category.list
.
If not specified, the default funnel identifier for this SPA will be used
Deal
dealCategoryId
Identifier of the deal funnel. Can be obtained using
crm.category.list
.
If not specified, the default funnel identifier for deals will be used
Lead
leadCustomerType
Type of leads.
Possible values:
1
— simple leads
2
— repeat leads
Code Examples
Code Examples
How to Use Examples in Documentation
For the user with
id = 1
, set the following configuration for the item card
Section 1 -
Personal Data
First Name
Show always
Last Name
Show always
Middle Name
Date of Birth
Phone
Show always
Default country:
United Kingdom(+44)
Address
Show always
Default address type:
Registration Address
(see
crm.enum.addresstype
)
Section 2 -
Basic Information
Contact Type
Source
Position
Section 3 -
Additional Information
Photo
Comment
Custom Field #1
cURL (Webhook)
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
'{"entityTypeId":3,"userId":1,"data":[{"name":"section_1","title":"Personal Data","type":"section","elements":[{"name":"NAME","optionFlags":1},{"name":"LAST_NAME","optionFlags":1},{"name":"SECOND_NAME"},{"name":"BIRTHDATE"},{"name":"PHONE","optionFlags":1,"options":{"defaultCountry":"GB"}},{"name":"ADDRESS","optionFlags":1,"options":{"defaultAddressType":4}}]},{"name":"section_2","title":"Basic Information","type":"section","elements":[{"name":"TYPE_ID"},{"name":"SOURCE_ID"},{"name":"POST"}]},{"name":"section_3","title":"Additional Information","type":"section","elements":[{"name":"PHOTO"},{"name":"COMMENTS"},{"name":"UF_CRM_1720697698689"}]}]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.details.configuration.set
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":3,"userId":1,"data":[{"name":"section_1","title":"Personal Data","type":"section","elements":[{"name":"NAME","optionFlags":1},{"name":"LAST_NAME","optionFlags":1},{"name":"SECOND_NAME"},{"name":"BIRTHDATE"},{"name":"PHONE","optionFlags":1,"options":{"defaultCountry":"GB"}},{"name":"ADDRESS","optionFlags":1,"options":{"defaultAddressType":4}}]},{"name":"section_2","title":"Basic Information","type":"section","elements":[{"name":"TYPE_ID"},{"name":"SOURCE_ID"},{"name":"POST"}]},{"name":"section_3","title":"Additional Information","type":"section","elements":[{"name":"PHOTO"},{"name":"COMMENTS"},{"name":"UF_CRM_1720697698689"}]}],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.details.configuration.set
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.details.configuration.set'
,
{
entityTypeId
:
3
,
userId
:
1
,
data
: [
{
name
:
"section_1"
,
title
:
"Personal Data"
,
type
:
"section"
,
elements
: [
{
name
:
"NAME"
,
optionFlags
:
1
,
},
{
name
:
"LAST_NAME"
,
optionFlags
:
1
,
},
{
name
:
"SECOND_NAME"
,
},
{
name
:
"BIRTHDATE"
,
},
{
name
:
"PHONE"
,
optionFlags
:
1
,
options
: {
defaultCountry
:
"GB"
,
},
},
{
name
:
"ADDRESS"
,
optionFlags
:
1
,
options
: {
defaultAddressType
:
4
,
},
},
],
},
{
name
:
"section_2"
,
title
:
"Basic Information"
,
type
:
"section"
,
elements
: [
{
name
:
"TYPE_ID"
},
{
name
:
"SOURCE_ID"
},
{
name
:
"POST"
},
],
},
{
name
:
"section_3"
,
title
:
"Additional Information"
,
type
:
"section"
,
elements
: [
{
name
:
"PHOTO"
},
{
name
:
"COMMENTS"
},
{
name
:
"UF_CRM_1720697698689"
},
],
},
],
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
info
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
'crm.item.details.configuration.set'
,
[
'entityTypeId'
=>
3
,
'userId'
=>
1
,
'data'
=> [
[
'name'
=>
"section_1"
,
'title'
=>
"Personal Data"
,
'type'
=>
"section"
,
'elements'
=> [
[
'name'
=>
"NAME"
,
'optionFlags'
=>
1
,
],
[
'name'
=>
"LAST_NAME"
,
'optionFlags'
=>
1
,
],
[
'name'
=>
"SECOND_NAME"
,
],
[
'name'
=>
"BIRTHDATE"
,
],
[
'name'
=>
"PHONE"
,
'optionFlags'
=>
1
,
'options'
=> [
'defaultCountry'
=>
"GB"
,
],
],
[
'name'
=>
"ADDRESS"
,
'optionFlags'
=>
1
,
'options'
=> [
'defaultAddressType'
=>
4
,
],
],
],
],
[
'name'
=>
"section_2"
,
'title'
=>
"Basic Information"
,
'type'
=>
"section"
,
'elements'
=> [
[
'name'
=>
"TYPE_ID"
],
[
'name'
=>
"SOURCE_ID"
],
[
'name'
=>
"POST"
],
],
],
[
'name'
=>
"section_3"
,
'title'
=>
"Additional Information"
,
'type'
=>
"section"
,
'elements'
=> [
[
'name'
=>
"PHOTO"
],
[
'name'
=>
"COMMENTS"
],
[
'name'
=>
"UF_CRM_1720697698689"
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
'Error setting details configuration: '
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
'crm.item.details.configuration.set'
,
{
entityTypeId
:
3
,
userId
:
1
,
data
: [
{
name
:
"section_1"
,
title
:
"Personal Data"
,
type
:
"section"
,
elements
: [
{
name
:
"NAME"
,
optionFlags
:
1
,
},
{
name
:
"LAST_NAME"
,
optionFlags
:
1
,
},
{
name
:
"SECOND_NAME"
,
},
{
name
:
"BIRTHDATE"
,
},
{
name
:
"PHONE"
,
optionFlags
:
1
,
options
: {
defaultCountry
:
"GB"
,
},
},
{
name
:
"ADDRESS"
,
optionFlags
:
1
,
options
: {
defaultAddressType
:
4
,
},
},
],
},
{
name
:
"section_2"
,
title
:
"Basic Information"
,
type
:
"section"
,
elements
: [
{
name
:
"TYPE_ID"
},
{
name
:
"SOURCE_ID"
},
{
name
:
"POST"
},
],
},
{
name
:
"section_3"
,
title
:
"Additional Information"
,
type
:
"section"
,
elements
: [
{
name
:
"PHOTO"
},
{
name
:
"COMMENTS"
},
{
name
:
"UF_CRM_1720697698689"
},
],
},
],
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.item.details.configuration.set'
,
[
'entityTypeId'
=>
3
,
'userId'
=>
1
,
'data'
=> [
[
'name'
=>
"section_1"
,
'title'
=>
"Personal Data"
,
'type'
=>
"section"
,
'elements'
=> [
[
'name'
=>
"NAME"
,
'optionFlags'
=>
1
,
],
[
'name'
=>
"LAST_NAME"
,
'optionFlags'
=>
1
,
],
[
'name'
=>
"SECOND_NAME"
,
],
[
'name'
=>
"BIRTHDATE"
,
],
[
'name'
=>
"PHONE"
,
'optionFlags'
=>
1
,
'options'
=> [
'defaultCountry'
=>
"GB"
,
],
],
[
'name'
=>
"ADDRESS"
,
'optionFlags'
=>
1
,
'options'
=> [
'defaultAddressType'
=>
4
,
],
],
],
],
[
'name'
=>
"section_2"
,
'title'
=>
"Basic Information"
,
'type'
=>
"section"
,
'elements'
=> [
[
'name'
=>
"TYPE_ID"
],
[
'name'
=>
"SOURCE_ID"
],
[
'name'
=>
"POST"
],
],
],
[
'name'
=>
"section_3"
,
'title'
=>
"Additional Information"
,
'type'
=>
"section"
,
'elements'
=> [
[
'name'
=>
"PHOTO"
],
[
'name'
=>
"COMMENTS"
],
[
'name'
=>
"UF_CRM_1720697698689"
],
],
],
],
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
1720699969.76157
,
"finish"
:
1720699970.153406
,
"duration"
:
0.39183592796325684
,
"processing"
:
0.02178215980529785
,
"date_start"
:
"2024-07-11T14:12:49+02:00"
,
"date_finish"
:
"2024-07-11T14:12:50+02:00"
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
Root element of the response. Returns
true
on success
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
""
,
"error_description"
:
"Element at index 0 in section at index 1 does not have name."
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
Value
Empty value
Parameter 'entityTypeId' is not defined
Required parameter
entityTypeId
not provided
Empty value
The entity type '
entityTypeName
' is not supported in the current context.
The method does not support this entity type
Empty value
Access denied.
The user does not have administrative rights
Empty value
Parameter 'data' must be an array.
A non-array was provided in
data
Empty value
The data must be an indexed array.
A non-indexed array was provided in
data
Empty value
There are no data to write.
An empty array was provided in
data
Empty value
Section at index
i
has type
data[i].type
. The expected type is 'section'.
The value in
data[i].type
is different from
'section'
Empty value
Section at index
i
does not have a name.
An empty value was provided in
data[i].name
Empty value
Section at index
i
does not have a title.
An empty value was provided in
data[i].title
Empty value
Element at index
j
in section at index
i
does not have a name.
An empty value was provided in
data[i].elements[j].name
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
Configuring Sections in the Detail Form of CRM Entities
Get Parameters of CRM Item Detail Configuration
Reset Item Card Parameters crm.item.details.configuration.reset
Set Common Detail for All Users crm.item.details.configuration.forceCommonScopeForAll
Copied
Was the article helpful?
Yes
No
Previous
Get CRM Entity Detail Form Parameters
Next
Reset CRM Entity Detail Form Parameters

---

## Reset Item Card Parameters crm.item.details.configuration.reset

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/item-details-configuration/crm-item-details-configuration-reset

Reset Item Card Parameters crm.item.details.configuration.reset | Bitrix24 REST API and Marketplace Applications
Reset Item Card Parameters crm.item.details.configuration.reset
Reset Item Card Parameters crm.item.details.configuration.reset
Method Parameters
extras
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Method name:
crm.item.details.configuration.reset
Scope:
crm
Who can execute the method: permission checks during method execution depend on the provided data:
Any user has the right to reset their personal settings
A user can reset shared and others' settings only if they are an administrator
The method resets the item card settings to their default values. It removes the personal settings of the specified user or the shared settings defined for all users.
Note
The settings for repeat lead detail forms may differ from those of simple lead detail forms. The parameter
extras.leadCustomerType
is used to switch between lead detail form settings.
The settings for the CRM entity detail form may vary depending on their Sales Funnel. The parameters used for switching are:
extras.categoryId
— for SPAs
extras.dealCategoryId
— for deals
Copied
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of CRM objects
userId
user
Identifier of the user whose configuration you want to reset.
If the parameter is not provided, the
userId
of the user calling this method will be used.
Required only when requesting personal settings
scope
string
Scope of the settings. Allowed values:
'P'
— personal settings
'C'
— shared settings
By default, the value is
'P'
extras
object
Additional parameters. Possible values and their structure are described
below
extras
extras
The
extras
parameter depends on the CRM object.
CRM Object
Name
Description
SPA
categoryId
Identifier of the SPA funnel. Can be obtained using
crm.category.list
.
If not specified, the default funnel identifier for this SPA will be used
Deal
dealCategoryId
Identifier of the deal funnel. Can be obtained using
crm.category.list
.
If not specified, the default funnel identifier for deals will be used
Lead
leadCustomerType
Type of leads.
Possible values:
1
— simple leads
2
— repeat leads
Code Examples
Code Examples
How to Use Examples in Documentation
Reset the shared configuration for deal cards in the funnel with
id = 9
for the user with
id = 1
cURL (Webhook)
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
'{"entityTypeId":2,"userId":1,"scope":"C","extras":{"dealCategoryId":9}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.details.configuration.reset
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"userId":1,"scope":"C","extras":{"dealCategoryId":9},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.details.configuration.reset
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.details.configuration.reset'
,
{
entityTypeId
:
2
,
userId
:
1
,
scope
:
"C"
,
extras
: {
dealCategoryId
:
9
,
},
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
info
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
'crm.item.details.configuration.reset'
,
[
'entityTypeId'
=>
2
,
'userId'
=>
1
,
'scope'
=>
"C"
,
'extras'
=> [
'dealCategoryId'
=>
9
,
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
return
;
}
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
'Error resetting details configuration: '
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
'crm.item.details.configuration.reset'
,
{
entityTypeId
:
2
,
userId
:
1
,
scope
:
"C"
,
extras
: {
dealCategoryId
:
9
,
},
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.item.details.configuration.reset'
,
[
'entityTypeId'
=>
2
,
'userId'
=>
1
,
'scope'
=>
'C'
,
'extras'
=> [
'dealCategoryId'
=>
9
,
]
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
1720687072.190654
,
"finish"
:
1720687072.586945
,
"duration"
:
0.39629101753234863
,
"processing"
:
0.057084083557128906
,
"date_start"
:
"2024-07-11T10:37:52+02:00"
,
"date_finish"
:
"2024-07-11T10:37:52+02:00"
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
Root element of the response. Returns
true
in case of successful settings reset
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
""
,
"error_description"
:
"Parameter 'entityTypeId' is not defined"
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
Value
Empty value
Parameter 'entityTypeId' is not defined
Required parameter
entityTypeId
not provided
Empty value
The entity type '
entityTypeName
' is not supported in current context.
The method does not support this entity type
Empty value
Access denied.
The user does not have administrative rights
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
Configuring Sections in the Detail Form of CRM Entities
Get Parameters of CRM Item Detail Configuration
Set Parameters for CRM Item Card crm.item.details.configuration.set
Set Common Detail for All Users crm.item.details.configuration.forceCommonScopeForAll
Copied
Was the article helpful?
Yes
No
Previous
Set CRM Entity Detail Form Parameters
Next
Set Common Detail Form for All Users

---

## Set Common Detail for All Users crm.item.details.configuration.forceCommonScopeForAll

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/item-details-configuration/crm-item-details-configuration-forceCommonScopeForAll

Set Common Detail for All Users crm.item.details.configuration.forceCommonScopeForAll | Bitrix24 REST API and Marketplace Applications
Set Common Detail for All Users crm.item.details.configuration.forceCommonScopeForAll
Set Common Detail for All Users crm.item.details.configuration.forceCommonScopeForAll
Method Parameters
extras
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: Administrator
This method forcibly sets a common detail for all users, removing their personal detail configuration.
Note
The settings for repeat lead detail forms may differ from those of simple lead detail forms. The parameter
extras.leadCustomerType
is used to switch between lead detail form settings.
The settings for the CRM entity detail form may vary depending on their Sales Funnel. The parameters used for switching are:
extras.categoryId
— for SPAs
extras.dealCategoryId
— for deals
Copied
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
of CRM objects
extras
object
Additional parameters. Possible values and their structure are described
below
extras
extras
The
extras
parameter depends on the CRM object.
CRM Object
Name
Description
SPA
categoryId
Identifier of the SPA funnel. Can be obtained using
crm.category.list
.
If not specified, the default funnel identifier for this SPA is used
Deal
dealCategoryId
Identifier of the deal funnel. Can be obtained using
crm.category.list
.
If not specified, the default funnel identifier for deals is used
Lead
leadCustomerType
Type of leads.
Possible values:
1
— simple leads
2
— repeat leads
Code Examples
Code Examples
How to Use Examples in Documentation
Set a common detail for deals in the funnel with
id = 9
cURL (Webhook)
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
'{"entityTypeId":2,"extras":{"dealCategoryId":9}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.details.configuration.forceCommonScopeForAll
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"extras":{"dealCategoryId":9},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.details.configuration.forceCommonScopeForAll
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.details.configuration.forceCommonScopeForAll'
,
{
entityTypeId
:
2
,
extras
: {
dealCategoryId
:
9
,
},
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
info
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
'crm.item.details.configuration.forceCommonScopeForAll'
,
[
'entityTypeId'
=>
2
,
'extras'
=> [
'dealCategoryId'
=>
9
,
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
return
;
}
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
'Error: '
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
'crm.item.details.configuration.forceCommonScopeForAll'
,
{
entityTypeId
:
2
,
extras
: {
dealCategoryId
:
9
,
},
},
(
result
) =>
{
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
return
;
}
console
.
info
(result.
data
());
},
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
'crm.item.details.configuration.forceCommonScopeForAll'
,
[
'entityTypeId'
=>
2
,
'extras'
=> [
'dealCategoryId'
=>
9
,
]
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
true
,
"time"
:
{
"start"
:
1720687903.685834
,
"finish"
:
1720687904.076471
,
"duration"
:
0.3906371593475342
,
"processing"
:
0.02508091926574707
,
"date_start"
:
"2024-07-11T10:51:43+02:00"
,
"date_finish"
:
"2024-07-11T10:51:44+02:00"
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
Root element of the response. Returns
true
on success
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
""
,
"error_description"
:
"Parameter 'entityTypeId' is not defined"
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
Value
Empty value
Parameter 'entityTypeId' is not defined
Required parameter
entityTypeId
not provided
Empty value
The entity type '
entityTypeName
' is not supported in current context.
The method does not support this entity type
Empty value
Access denied.
The user does not have administrative rights
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
Configuring Sections in the Detail Form of CRM Entities
Get Parameters of CRM Item Detail Configuration
Set Parameters for CRM Item Card crm.item.details.configuration.set
Reset Item Card Parameters crm.item.details.configuration.reset
Copied
Was the article helpful?
Yes
No
Previous
Reset CRM Entity Detail Form Parameters
Next
Widgets

---

