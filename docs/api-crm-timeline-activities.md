---
description: 'CRM Timeline Activities: Base, todo, binding, types, events, layout'
methods:
- crm.activity.
- crm.activity.add
- crm.activity.badge.add
- crm.activity.badge.delete
- crm.activity.badge.get
- crm.activity.badge.list
- crm.activity.binding.
- crm.activity.binding.add
- crm.activity.binding.delete
- crm.activity.binding.list
- crm.activity.binding.move
- crm.activity.communication.fields
- crm.activity.configurable.
- crm.activity.configurable.add
- crm.activity.configurable.get
- crm.activity.configurable.update
- crm.activity.delete
- crm.activity.fields
- crm.activity.get
- crm.activity.layout.blocks.
- crm.activity.layout.blocks.delete
- crm.activity.layout.blocks.get
- crm.activity.layout.blocks.set
- crm.activity.list
- crm.activity.todo.add
- crm.activity.todo.update
- crm.activity.todo.updateColor
- crm.activity.todo.updateDeadline
- crm.activity.todo.updateDescription
- crm.activity.todo.updateResponsibleUser
pages: 35
title: 'CRM Timeline Activities: Base, todo, binding, types, events, layout'
---
# CRM Timeline Activities: Base, todo, binding, types, events, layout
> CRM Timeline Activities: Base, todo, binding, types, events, layout
> **35 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Activities in CRM: Overview of Methods](#activities-in-crm-overview-of-methods)
- [Overview of Methods](#overview-of-methods)
- [Add System Activity crm.activity.add](#add-system-activity-crmactivityadd)
- [Update System Activity crm.activity.update](#update-system-activity-crmactivityupdate)
- [Get information about the activity by ID crm.activity.get](#get-information-about-the-activity-by-id-crmactivi)
- [Get the list of activities crm.activity.list](#get-the-list-of-activities-crmactivitylist)
- [Delete activity crm.activity.delete](#delete-activity-crmactivitydelete)
- [Get a list of fields for crm.activity.fields](#get-a-list-of-fields-for-crmactivityfields)
- [Get Description of Communication crm.activity.communication.fields](#get-description-of-communication-crmactivitycommun)
- [Overview of Methods](#overview-of-methods)
- [Add Universal Activity crm.activity.todo.add](#add-universal-activity-crmactivitytodoadd)
- [Update universal deal crm.activity.todo.update](#update-universal-deal-crmactivitytodoupdate)
- [Update the color of the universal deal crm.activity.todo.updateColor](#update-the-color-of-the-universal-deal-crmactivity)
- [Update Deadline for Universal Activity crm.activity.todo.updateDeadline](#update-deadline-for-universal-activity-crmactivity)
- [Update the description of the universal activity crm.activity.todo.updateDescription](#update-the-description-of-the-universal-activity-c)
- [Update the responsible user for the universal activity crm.activity.todo.updateResponsibleUser](#update-the-responsible-user-for-the-universal-acti)
- [Managing Activity Relationships in the Timeline](#managing-activity-relationships-in-the-timeline)
- [Add a deal binding to a CRM entity crm.activity.binding.add](#add-a-deal-binding-to-a-crm-entity-crmactivitybind)
- [Update the deal's connection with the CRM entity crm.activity.binding.move](#update-the-deals-connection-with-the-crm-entity-cr)
- [Get a list of all bindings for the deal crm.activity.binding.list](#get-a-list-of-all-bindings-for-the-deal-crmactivit)
- [Delete the connection of the activity with the CRM entity crm.activity.binding.delete](#delete-the-connection-of-the-activity-with-the-crm)
- [Overview of Methods](#overview-of-methods)
- [Add Custom Activity Type crm.activity.type.add](#add-custom-activity-type-crmactivitytypeadd)
- [Get a list of custom activity types crm.activity.type.list](#get-a-list-of-custom-activity-types-crmactivitytyp)
- [Delete Custom Activity Type crm.activity.type.delete](#delete-custom-activity-type-crmactivitytypedelete)
- [Additional Content Blocks](#additional-content-blocks)
- [Set a set of additional content blocks in the activity crm.activity.layout.blocks.set](#set-a-set-of-additional-content-blocks-in-the-acti)
- [Get a Set of Additional Content Blocks in the activity crm.activity.layout.blocks.get](#get-a-set-of-additional-content-blocks-in-the-acti)
- [Delete a set of additional content blocks in the CRM activity crm.activity.layout.blocks.delete](#delete-a-set-of-additional-content-blocks-in-the-c)
- [Overview of Events](#overview-of-events)
- [Event for Creating a New Deal onCrmActivityAdd](#event-for-creating-a-new-deal-oncrmactivityadd)
- [Event onCrmActivityUpdate](#event-oncrmactivityupdate)
- [Event onCrmActivityDelete](#event-oncrmactivitydelete)
- [Embedding Applications](#embedding-applications)
- [How to create an activity from an application](#how-to-create-an-activity-from-an-application)

---

## Activities in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/index

Activities in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Activities in CRM: Overview of Methods
Activities in CRM: Overview of Methods
Links of Activities with Other CRM Entities
System Activities
Custom Activity Types
Universal Activities
Configurable Activities
Widgets
Additional Features
Overview of Methods and Events
General Methods and Events
Managing Activity Links
Custom Activity Types
Universal Activity
Configurable Activity
Badges of Configurable Activity
Additional Content Blocks
In CRM, activities are used for any tasks related to clients: calls, meetings, document approvals.
Activities are divided into incoming and scheduled:
Incoming — activities that come from the client, such as an email, call, or chat. For these activities, it is important to correctly specify the parameter
DIRECTION
=
1
so that the incoming activities counter in CRM works.
Scheduled — activities created by employees, such as tasks or universal activities. They can have a deadline, add links to CRM entities, integrate with the calendar, invite colleagues, and attach files.
Quick navigation:
all methods and events
User documentation:
activities in CRM
,
Activity Direction
Links of Activities with Other CRM Entities
Links of Activities with Other CRM Entities
Activities linked to CRM entities are stored in the timeline of the entity's card. If an activity is linked to multiple entities — for example, an email can be linked to both a deal and a contact — it will be stored in the timelines of all related entities.
Links between activities and CRM entities can be added and removed using the methods from the
crm.activity.binding.*
group.
System Activities
System Activities
System activities in CRM are created automatically:
A call activity is created by the connected telephony in Bitrix. To finish a call, use the method
telephony.externalcall.finish
. This method ends the call, creates an activity in the entity's card, and returns the ID of the created activity in the parameter
CRM_ACTIVITY_ID
.
An email activity is created by the email system. When an email from a client arrives at the connected Bitrix24 address, CRM checks if there is a client in the database with the email from the message. Based on the results of the check, an activity will be created in the card of the found entity or a new client, where the activity will appear.
To create, modify, or delete a system activity, use the methods from the
crm.activity.*
group. When creating a system activity, specify
TYPE_ID
, for example, for an email activity
TYPE_ID
=
2
. To get values for other types of activities, use the method
crm.enum.activitytype
.
Custom Activity Types
Custom Activity Types
Applications can register custom activity types: upload a custom icon and specify the type name. For example, you can create your own activity type with an icon and name of your application.
To register an activity type — use the methods from the
crm.activity.type.*
group. When creating a type, you need to specify its code designation in the parameter
TYPE_ID
.
To create an activity with the application type — use the group of system activity methods
crm.activity.add
. When creating an activity, specify the code designation of the custom type
TYPE_ID
, registered for the activity type, in the parameter
PROVIDER_TYPE_ID
.
The methods
crm.activity.delete
(deletes an activity) and
crm.activity.list
(retrieves a list of activities) are common for all types of CRM activities.
Universal Activities
Universal Activities
Universal activities are a type of activity with extended settings. In the card of a universal activity, you can synchronize the activity with the calendar, choose a meeting location with the client, add colleagues, select a client from a CRM entity, categorize activities by color, and choose a meeting room. Extended settings are available to employees on the Bitrix24 side.
To create a universal activity, use the method
crm.activity.todo.add
. To change the deadline of the activity — use the method
crm.activity.todo.updateDeadline
, and to change the description of the activity —
crm.activity.todo.updateDescription
.
User Documentation
Universal Activity in Bitrix24
Configurable Activities
Configurable Activities
Configurable activities are a type of activity that can only be created from an application. For this type, you can customize the appearance of the activity card and its functionality:
Structure of Configurable Activity
Badges of Configurable Activity
To create or modify a configurable activity, use the methods from the
crm.activity.configurable.*
group.
Widgets
Widgets
Applications can be embedded into activities. For embedding, special places are used, and there is one available in activities —
Context Menu Item of the Activity in the Entity Card
CRM_XXX_ACTIVITY_TIMELINE_MENU
.
Thanks to the embedding, you can use the application without leaving the entity card. The application will open on the page you specify during the registration of the embedding.
Typical use-cases and scenarios
Widget Embedding Mechanism
Create Activities from Applications
Additional Features
Additional Features
Text notes
can be added to activities and deleted. Use the methods from the
crm.timeline.note.*
group.
Content blocks
can be added to activities and deleted. Use the methods from the
crm.activity.layout.blocks.*
.
Available Content Blocks
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can perform methods: any user
General Methods and Events
General Methods and Events
Methods
Events
Method
Description
crm.activity.add
Creates a new activity
crm.activity.update
Updates an activity
crm.activity.get
Returns an activity by ID
crm.activity.list
Returns a list of activities of all types by filter
crm.activity.delete
Deletes any type of activity
crm.activity.fields
Returns the description of activity fields
crm.activity.communication.fields
Returns the description of communication fields
Event
Triggered
onCrmActivityAdd
When an activity is created
onCrmActivityUpdate
When an activity is updated
onCrmActivityDelete
When an activity is deleted
Managing Activity Links
Managing Activity Links
Method
Description
crm.activity.binding.add
Adds a link
crm.activity.binding.list
Returns a list of links
crm.activity.binding.delete
Deletes a link
Custom Activity Types
Custom Activity Types
Method
Description
crm.activity.type.add
Registers a custom activity type with a name and icon
crm.activity.type.list
Retrieves a list of activities
crm.activity.type.delete
Deletes a custom type
Universal Activity
Universal Activity
Method
Description
crm.activity.todo.add
Creates a universal activity
crm.activity.todo.updateDeadline
Changes the deadline
crm.activity.todo.updateDescription
Changes the description
Configurable Activity
Configurable Activity
Method
Description
crm.activity.configurable.add
Adds a new configurable activity to the timeline
crm.activity.configurable.update
Updates a configurable activity
crm.activity.configurable.get
Retrieves information about an activity by ID
Badges of Configurable Activity
Badges of Configurable Activity
Method
Description
crm.activity.badge.add
Creates a badge
crm.activity.badge.get
Returns information about a badge
crm.activity.badge.list
Returns a list of all registered badges
crm.activity.badge.delete
Deletes a badge
Additional Content Blocks
Additional Content Blocks
Method
Description
crm.activity.layout.blocks.set
Sets a set of additional content blocks in the activity
crm.activity.layout.blocks.get
Retrieves the set of additional content blocks in the activity set by the application
crm.activity.layout.blocks.delete
Deletes the set of additional content blocks for the activity set by the application
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/activity-base/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: any user
Methods for working with system activities in the
timeline
Method
Description
crm.activity.add
Adds a new activity to the timeline
crm.activity.update
Updates an activity
crm.activity.get
Retrieves information about an activity by its ID
crm.activity.list
Retrieves a list of all activities for a CRM entity by filter
crm.activity.delete
Deletes any type of activities
crm.activity.fields
Retrieves the description of fields for an activity
crm.activity.communication.fields
Retrieves the description for communication fields in an activity
Additional Information
Additional Information
CRM Entity Type
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Add System Activity

---

## Add System Activity crm.activity.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/activity-base/crm-activity-add

Add System Activity crm.activity.add | Bitrix24 REST API and Marketplace Applications
Add System Activity crm.activity.add
Add System Activity crm.activity.add
Method Parameters
Parameter fields
Value Usage Examples for Fields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: user with permission to add an activity
Method development has been halted
The method
crm.activity.add
continues to function, but there is a more relevant alternative
crm.activity.todo.add
.
The method
crm.activity.add
creates a new system activity.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
array
Array of values for
activity fields
in the following structure:
fields
:
{
"OWNER_TYPE_ID"
:
2
,
"OWNER_ID"
:
102
,
"TYPE_ID"
:
2
,
"SUBJECT"
:
"New call"
,
}
There is an additional field
DISABLE_SENDING_MESSAGE_COPY
. It is intended to forcibly disable sending a copy of the message to the recipient from MESSAGE_FROM. If the parameter is not filled or any value other than
Y
is specified, a copy will be sent. Example:
[
'fields'
=>
array
(
'SETTINGS'
=>
array
(
'DISABLE_SENDING_MESSAGE_COPY'
=>
'Y'
)
)
]
Parameter fields
Parameter fields
Required parameters are marked with *
Field
type
Description
OWNER_ID
*
integer
Identifier of the CRM entity
OWNER_TYPE_ID
*
integer
Identifier of the CRM object type
TYPE_ID
*
crm_enum_activitytype
Type of the deal. To access the available deal types, use the method
crm.enum.activitytype
.
To create a deal with the type "task," use the method
creation
or
modification
of the task and specify the CRM entity in the field
UF_CRM_TASK
ASSOCIATED_ENTITY_ID
integer
Identifier of the entity associated with the activity
COMMUNICATIONS
*
crm_activity_communication
Description of communication
DEADLINE
datetime
Date and time of the activity deadline. The field is not set directly; the value is taken from START_TIME for calls and meetings and from END_TIME for tasks
DESCRIPTION
string
Text description of the activity
DESCRIPTION_TYPE
crm.enum.contenttype
Type of description
DIRECTION
crm.enum.activitydirection
Direction of the activity: incoming/outgoing. Relevant for calls and emails, not used for meetings
END_TIME
datetime
End time of the activity
FILES
diskfile
Files added to the activity
LOCATION
string
Location
NOTIFY_TYPE
crm.enum.activitynotifytype
Type of notification
ORIGINATOR_ID
string
Identifier of the data source, used only for binding to an external source
ORIGIN_ID
string
Identifier of the entity in the data source, used only for binding to an external source
ORIGIN_VERSION
string
Original version, used to protect data from accidental overwriting by an external system. If the data was imported and not changed in the external system, such data can be edited in CRM without fear that the next export will lead to data overwriting
PRIORITY
crm.enum.activitypriority
Priority
PROVIDER_DATA
string
Additional provider data
PROVIDER_GROUP_ID
string
Identifier of the provider group
PROVIDER_ID
string
Identifier of the provider
PROVIDER_TYPE_ID
string
Identifier of the provider type, status from the directory
PROVIDER_PARAMS
object
Additional provider parameters
RESPONSIBLE_ID
*
user
Identifier of the user responsible for the activity
SETTINGS
object
Additional settings
START_TIME
datetime
Start time of the activity
STATUS
crm_enum_activitystatus
Status of the activity
SUBJECT
string
Additional description of the activity
WEBDAV_ELEMENTS
diskfile
Added files. Deprecated, kept for compatibility
IS_INCOMING_CHANNEL
char
Flag indicating whether the activity was created from an incoming channel (
Y
/
N
)
Value Usage Examples for Fields
Value Usage Examples for Fields
For activities of type
e-mail
:
if the email should not be sent, set parameters
DIRECTION=2
and
COMPLETED='N'
;
if it is necessary to mark emails as completed, update the activities by setting the completion flag.
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
'{"fields":{"OWNER_TYPE_ID":2,"OWNER_ID":102,"TYPE_ID":2,"COMMUNICATIONS":[{"VALUE":"+18005551234","ENTITY_ID":134,"ENTITY_TYPE_ID":3}],"SUBJECT":"New call","START_TIME":"2023-12-31T12:00:00+00:00","END_TIME":"2023-12-31T12:30:00+00:00","COMPLETED":"N","PRIORITY":3,"RESPONSIBLE_ID":1,"DESCRIPTION":"Important call","DESCRIPTION_TYPE":3,"DIRECTION":2,"FILES":[{"fileData":["example.jpg","base64_encoded_content_here"]}]} }'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"OWNER_TYPE_ID":2,"OWNER_ID":102,"TYPE_ID":2,"COMMUNICATIONS":[{"VALUE":"+18005551234","ENTITY_ID":134,"ENTITY_TYPE_ID":3}],"SUBJECT":"New call","START_TIME":"2023-12-31T12:00:00+00:00","END_TIME":"2023-12-31T12:30:00+00:00","COMPLETED":"N","PRIORITY":3,"RESPONSIBLE_ID":1,"DESCRIPTION":"Important call","DESCRIPTION_TYPE":3,"DIRECTION":2,"FILES":[{"fileData":["example.jpg","base64_encoded_content_here"]}]},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.activity.add"
,
{
fields
: {
"OWNER_TYPE_ID"
:
2
,
"OWNER_ID"
:
102
,
"TYPE_ID"
:
2
,
"COMMUNICATIONS"
: [
{
VALUE
:
"+18005551234"
,
ENTITY_ID
:
134
,
ENTITY_TYPE_ID
:
3
}
],
"SUBJECT"
:
"New call"
,
"START_TIME"
:
"2023-12-31T12:00:00+00:00"
,
// Example date and time
"END_TIME"
:
"2023-12-31T12:30:00+00:00"
,
// Example date and time
"COMPLETED"
:
"N"
,
"PRIORITY"
:
3
,
"RESPONSIBLE_ID"
:
1
,
"DESCRIPTION"
:
"Important call"
,
"DESCRIPTION_TYPE"
:
3
,
"DIRECTION"
:
2
,
"FILES"
: [
{
fileData
: [
"example.jpg"
,
// File name
"base64_encoded_content_here"
// File content in base64 format
]
}
]
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
'crm.activity.add'
,
[
'fields'
=> [
'OWNER_TYPE_ID'
=>
2
,
'OWNER_ID'
=>
102
,
'TYPE_ID'
=>
2
,
'COMMUNICATIONS'
=> [
[
'VALUE'
=>
'+18005551234'
,
'ENTITY_ID'
=>
134
,
'ENTITY_TYPE_ID'
=>
3
]
],
'SUBJECT'
=>
'New call'
,
'START_TIME'
=>
'2023-12-31T12:00:00+00:00'
,
'END_TIME'
=>
'2023-12-31T12:30:00+00:00'
,
'COMPLETED'
=>
'N'
,
'PRIORITY'
=>
3
,
'RESPONSIBLE_ID'
=>
1
,
'DESCRIPTION'
=>
'Important call'
,
'DESCRIPTION_TYPE'
=>
3
,
'DIRECTION'
=>
2
,
'FILES'
=> [
[
'fileData'
=> [
'example.jpg'
,
'base64_encoded_content_here'
]
]
]
]
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
'Error adding activity: '
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
"crm.activity.add"
,
{
fields
: {
"OWNER_TYPE_ID"
:
2
,
"OWNER_ID"
:
102
,
"TYPE_ID"
:
2
,
"COMMUNICATIONS"
: [
{
VALUE
:
"+18005551234"
,
ENTITY_ID
:
134
,
ENTITY_TYPE_ID
:
3
}
],
"SUBJECT"
:
"New call"
,
"START_TIME"
:
"2023-12-31T12:00:00+00:00"
,
// Example date and time
"END_TIME"
:
"2023-12-31T12:30:00+00:00"
,
// Example date and time
"COMPLETED"
:
"N"
,
"PRIORITY"
:
3
,
"RESPONSIBLE_ID"
:
1
,
"DESCRIPTION"
:
"Important call"
,
"DESCRIPTION_TYPE"
:
3
,
"DIRECTION"
:
2
,
"FILES"
: [
{
fileData
: [
"example.jpg"
,
// File name
"base64_encoded_content_here"
// File content in base64 format
]
}
]
}
},
result
=>
{
if
(result.
error
()) {
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
'crm.activity.add'
,
[
'fields'
=> [
'OWNER_TYPE_ID'
=>
2
,
'OWNER_ID'
=>
102
,
'TYPE_ID'
=>
2
,
'COMMUNICATIONS'
=> [
[
'VALUE'
=>
'+18005551234'
,
'ENTITY_ID'
=>
134
,
'ENTITY_TYPE_ID'
=>
3
]
],
'SUBJECT'
=>
'New call'
,
'START_TIME'
=>
'2023-12-31T12:00:00+00:00'
, // Example date
and
time
'END_TIME'
=>
'2023-12-31T12:30:00+00:00'
, // Example date
and
time
'COMPLETED'
=>
'N'
,
'PRIORITY'
=>
3
,
'RESPONSIBLE_ID'
=>
1
,
'DESCRIPTION'
=>
'Important call'
,
'DESCRIPTION_TYPE'
=>
3
,
'DIRECTION'
=>
2
,
'FILES'
=> [
[
'fileData'
=> [
'example.jpg'
, // File name
'base64_encoded_content_here'
// File content in base64 format
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
HTTP status:
200
{
"result"
:
999
,
"time"
:
{
"start"
:
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation. Returns the identifier of the activity in the timeline in case of success, otherwise —
false
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
"Access denied."
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
The field SUBJECT is not defined or empty
The
SUBJECT
field is not set
The field RESPONSIBLE_ID is not defined or invalid
The
RESPONSIBLE_ID
field is not set
The field TYPE_ID is not defined or invalid
The
TYPE_ID
field is not set
The field COMMUNICATIONS is not defined or invalid
The
COMMUNICATIONS
field is not set
The only one communication is allowed for activity of specified type
More than one contact is specified
Could not build binding. Please ensure that owner info and communications are defined correctly
Connections for the activity are not specified
Email send error. Failed to load module "subscribe"
Email send error. Invalid data
Email send error. Invalid email is specified
Email send error. "From" is not found
Email send error. "To" is not found
Email send error. Failed to add posting. Please see details below
Email send error. Failed to save posting file. Please see details below
Email send error. Failed to update activity
Email send error. General error
Errors related to "email" activities
The custom activity without provider is not supported in current context
Activity type is not supported in the specified context
Use crm.activity.configurable.add for this activity provider
Incorrect method call for configurable activity
Access denied
No permission to add an entity in CRM
Application context required
Incorrect
PROVIDER_ID
parameter for the activity created in the application context
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
Update System Activity crm.activity.update
Delete activity crm.activity.delete
Get information about the activity by ID crm.activity.get
Get the list of activities crm.activity.list
Get Description of Communication crm.activity.communication.fields
Get a list of fields for crm.activity.fields
Add Calendar Event for Client Interaction
How to Send an Email to a Client on Behalf of an Employee
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update System Activity

---

## Update System Activity crm.activity.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/activity-base/crm-activity-update

Update System Activity crm.activity.update | Bitrix24 REST API and Marketplace Applications
Update System Activity crm.activity.update
Update System Activity crm.activity.update
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
Who can execute the method: any user with permission to update the activity
Method development has been halted
The method
crm.activity.update
continues to function, but there is a more current equivalent
crm.activity.todo.update
.
The method
crm.activity.update
updates an existing activity.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Integer identifier of the activity in the timeline, for example
999
fields
*
array
Array of values for
activity fields
in the following structure:
fields
:
{
"OWNER_TYPE_ID"
:
2
,
"OWNER_ID"
:
102
,
"TYPE_ID"
:
2
,
"SUBJECT"
:
"New call"
,
}
Parameter fields
Parameter fields
Required parameters are marked with *
Field
type
Description
OWNER_ID
*
integer
Identifier of the CRM entity
OWNER_TYPE_ID
*
integer
Identifier of the CRM object type
TYPE_ID
*
crm_enum_activitytype
Type of activity
ASSOCIATED_ENTITY_ID
integer
Identifier of the entity associated with the activity
COMMUNICATIONS
*
crm_activity_communication
Description of the communication
DEADLINE
datetime
Date and time of the activity deadline. This field is not set directly; the value is taken from START_TIME for calls and meetings and from END_TIME for tasks
DESCRIPTION
string
Text description of the activity
DESCRIPTION_TYPE
crm.enum.contenttype
Type of description
DIRECTION
crm.enum.activitydirection
Direction of the activity: incoming/outgoing. Relevant for calls and emails, not used for meetings
END_TIME
datetime
End time of the activity
FILES
diskfile
Files added to the activity
LOCATION
string
Location
NOTIFY_TYPE
crm.enum.activitynotifytype
Type of notification
ORIGINATOR_ID
string
Identifier of the data source, used only for linking to an external source
ORIGIN_ID
string
Identifier of the item in the data source, used only for linking to an external source
ORIGIN_VERSION
string
Original version, used to protect data from accidental overwriting by an external system. If the data was imported and not changed in the external system, it can be edited in CRM without fear that the next export will overwrite the data
PRIORITY
crm.enum.activitypriority
Priority
PROVIDER_DATA
string
Additional provider data
PROVIDER_GROUP_ID
string
Identifier of the provider group
PROVIDER_ID
string
Identifier of the provider
PROVIDER_TYPE_ID
string
Identifier of the provider type, status from the directory
PROVIDER_PARAMS
object
Additional provider parameters
RESPONSIBLE_ID
*
user
Identifier of the user responsible for the activity
SETTINGS
object
Additional settings
START_TIME
datetime
Start time of the activity
STATUS
crm_enum_activitystatus
Status of the activity
SUBJECT
string
Additional description of the activity
WEBDAV_ELEMENTS
diskfile
Added files. Deprecated, kept for compatibility
IS_INCOMING_CHANNEL
char
Flag indicating whether the activity was created from an incoming channel (
Y
/
N
)
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
'{"id":999,"fields":{"RESPONSIBLE_ID":1,"DESCRIPTION":"New activity description"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"fields":{"RESPONSIBLE_ID":1,"DESCRIPTION":"New activity description"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.update'
,
{
id
:
999
,
fields
: {
"RESPONSIBLE_ID"
:
1
,
"DESCRIPTION"
:
"New activity description"
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
'crm.activity.update'
,
[
'id'
=>
999
,
'fields'
=> [
"RESPONSIBLE_ID"
=>
1
,
"DESCRIPTION"
=>
"New activity description"
]
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
'Error updating activity: '
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
'crm.activity.update'
,
{
id
:
999
,
fields
: {
"RESPONSIBLE_ID"
:
1
,
"DESCRIPTION"
:
"New activity description"
}
},
result
=>
{
if
(result.
error
()) {
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
'crm.activity.update'
,
[
'id'
=>
999
,
'fields'
=> [
'RESPONSIBLE_ID'
=>
1
,
'DESCRIPTION'
=>
'New activity description'
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
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation. Returns
true
if the activity was successfully updated, otherwise
false
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
"Access denied."
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
Activity is not found
The activity with the specified identifier was not found for the entity in CRM
The field SUBJECT is not defined or empty
The
SUBJECT
field is not set
The field RESPONSIBLE_ID is not defined or invalid
The
RESPONSIBLE_ID
field is not set
The field TYPE_ID is not defined or invalid
The
TYPE_ID
field is not set
The field COMMUNICATIONS is not defined or invalid
The
COMMUNICATIONS
field is not set
The only one communication is allowed for activity of specified type
More than one contact is allowed
Could not build binding. Please ensure that owner info and communications are defined correctly
Connections for the activity are not specified
The custom activity without provider is not supported in current context
The activity type is not supported in the given context
Use crm.activity.configurable.update for this activity provider
Incorrect method call for configurable activity
Access denied
No permission to update the entity in CRM
Application context required
Incorrect
PROVIDER_ID
parameter for the activity created in the application context
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
Add System Activity crm.activity.add
Delete activity crm.activity.delete
Get information about the activity by ID crm.activity.get
Get the list of activities crm.activity.list
Get Description of Communication crm.activity.communication.fields
Get a list of fields for crm.activity.fields
Copied
Was the article helpful?
Yes
No
Previous
Add System Activity
Next
Get Activity by ID

---

## Get information about the activity by ID crm.activity.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/activity-base/crm-activity-get

Get information about the activity by ID crm.activity.get | Bitrix24 REST API and Marketplace Applications
Method parameters
Get information about the activity by ID crm.activity.get
Method parameters
Code examples
Response handling
Returned data
Error handling
Possible error codes
Statuses and System Error Codes
Continue exploring
Scope:
crm
Who can execute the method: any user
The method
crm.activity.get
returns information about the activity by its ID.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
The ID of the activity in the timeline, for example
999
Code examples
Code examples
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
'{ "id":999 }'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.get
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
https://**put_your_bitrix24_address**/rest/crm.activity.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.get'
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
'crm.activity.get'
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
'Error getting activity: '
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
'crm.activity.get'
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
'crm.activity.get'
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
Response handling
Response handling
HTTP status:
200
{
"result"
:
{
"ID"
:
"999"
,
"OWNER_ID"
:
"15"
,
"OWNER_TYPE_ID"
:
"3"
,
"TYPE_ID"
:
"2"
,
"PROVIDER_ID"
:
"VOXIMPLANT_CALL"
,
"PROVIDER_TYPE_ID"
:
"CALL"
,
"PROVIDER_GROUP_ID"
:
null
,
"ASSOCIATED_ENTITY_ID"
:
"0"
,
"SUBJECT"
:
"Outgoing call Andrew Johnson"
,
"CREATED"
:
"2020-09-27T13:26:55+02:00"
,
"LAST_UPDATED"
:
"2021-03-21T20:28:24+02:00"
,
"START_TIME"
:
"2020-09-27T13:25:00+02:00"
,
"END_TIME"
:
"2020-09-27T19:25:00+02:00"
,
"DEADLINE"
:
"2020-09-27T13:25:00+02:00"
,
"COMPLETED"
:
"Y"
,
"STATUS"
:
"2"
,
"RESPONSIBLE_ID"
:
"505"
,
"PRIORITY"
:
"2"
,
"NOTIFY_TYPE"
:
"1"
,
"NOTIFY_VALUE"
:
"15"
,
"DESCRIPTION"
:
""
,
"DESCRIPTION_TYPE"
:
"1"
,
"DIRECTION"
:
"2"
,
"LOCATION"
:
""
,
"SETTINGS"
:
[
]
,
"ORIGINATOR_ID"
:
null
,
"ORIGIN_ID"
:
null
,
"AUTHOR_ID"
:
"505"
,
"EDITOR_ID"
:
"505"
,
"PROVIDER_PARAMS"
:
[
]
,
"PROVIDER_DATA"
:
null
,
"RESULT_MARK"
:
"0"
,
"RESULT_VALUE"
:
null
,
"RESULT_SUM"
:
null
,
"RESULT_CURRENCY_ID"
:
null
,
"RESULT_STATUS"
:
"0"
,
"RESULT_STREAM"
:
"0"
,
"RESULT_SOURCE_ID"
:
null
,
"AUTOCOMPLETE_RULE"
:
"0"
}
,
"time"
:
{
"start"
:
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned data
Returned data
Name
type
Description
result
object
Root element of the response. Values for the
result
field correspond to
fields of the object
time
time
Information about the request execution time
Error handling
Error handling
HTTP status:
400
{
"error"
:
""
,
"error_description"
:
"Access denied."
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
Possible error codes
Possible error codes
Code
Description
Activity is not found
The activity with the specified ID was not found for the entity in CRM
Access denied
No rights to edit the entity in CRM
Application context required
Invalid
PROVIDER_ID
parameter for the activity created in the context of the application
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
Continue exploring
Continue exploring
Add System Activity crm.activity.add
Update System Activity crm.activity.update
Delete activity crm.activity.delete
Get the list of activities crm.activity.list
Get Description of Communication crm.activity.communication.fields
Get a list of fields for crm.activity.fields
Copied
Was the article helpful?
Yes
No
Previous
Update System Activity
Next
Get List of Activities

---

## Get the list of activities crm.activity.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/activity-base/crm-activity-list

Get the list of activities crm.activity.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of activities crm.activity.list
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Private Examples
Using BINDINGS
Retrieving COMMUNICATIONS
Retrieving Attachments
Continue Learning
Scope:
crm
Who can execute the method: any user
The method
crm.activity.list
returns a list of activities based on the filter, considering the access permissions of the current user.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
select
array
An array of fields of the activity
crm.activity.fields
that need to be selected. To get the fields
COMMUNICATIONS
and
FILES
, specify them in select.
filter
object
An object for filtering the selected items in key-value format.
Possible values for
field
correspond to the fields of the activity
crm.activity.fields
.
An additional prefix can be assigned to the key to clarify the filter's behavior. Possible prefix values:
>=
— greater than or equal to
>
— greater than
<=
— less than or equal to
<
— less than
@
— IN (an array is passed as a value)
!@
— NOT IN (an array is passed as a value)
%
— LIKE, substring search. The
%
symbol in the filter value does not need to be passed. The search looks for a substring in any position of the string.
=%
— LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
"mol%" — searching for values starting with "mol"
"%mol" — searching for values ending with "mol"
"%mol%" — searching for values where "mol" can be in any position
%=
— LIKE (see description above)
!%
— NOT LIKE, substring search. The
%
symbol in the filter value does not need to be passed. The search goes from both sides.
=%
— NOT LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
"mol%" — searching for values not starting with "mol"
"%mol" — searching for values not ending with "mol"
"%mol%" — searching for values where the substring "mol" is not present in any position
!%=
— NOT LIKE (see description above)
=
— equal, exact match (used by default)
!=
- not equal
!
— not equal
order
object
A set of key-value pairs for sorting the output results. The keys can use the fields of the activity
crm.activity.fields
.
Possible values for
order
:
asc
— in ascending order
desc
— in descending order
By default, it is sorted by increasing the Start Date field (
START_TIME
)
start
integer
This parameter is used to control pagination.
The page size of results is always static: 50 records.
To select the second page of results, you need to pass the value
50
. To select the third page of results — the value
100
, and so on.
The formula for calculating the value of the
start
parameter:
start = (N-1) * 50
, where
N
— the number of the desired page
See the description of
list methods
.
Pay attention to the peculiarity of the parameter
filter[BINDINGS]
.
Activity can be linked to multiple CRM entities. For example, a call can be linked to both a lead and an activity, so to retrieve these entities, there is a special filter key in the parameters of the method
crm.activity.list
-
BINDINGS
.
You need to specify an array of
system
or
custom
types of CRM objects for which you need to find the binding.
Each object can consist of the keys
OWNER_TYPE_ID
(entity type identifier) and
OWNER_ID
(entity identifier), either one or a combination of both. For example:
"BINDINGS"
:
[
{
"OWNER_TYPE_ID"
:
2
}
,
{
"OWNER_TYPE_ID"
:
3
}
]
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"order":{"ID":"DESC"},"filter":{"OWNER_TYPE_ID":3,"OWNER_ID":102},"select":["*","COMMUNICATIONS"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"ID":"DESC"},"filter":{"OWNER_TYPE_ID":3,"OWNER_ID":102},"select":["*","COMMUNICATIONS"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.list
In this example, we retrieve the list of activities for the contact with
ID
= 102.
BX24
.
callMethod
(
"crm.activity.list"
,
{
order
: {
"ID"
:
"DESC"
},
filter
:
{
"OWNER_TYPE_ID"
:
3
,
"OWNER_ID"
:
102
},
select
: [
"*"
,
"COMMUNICATIONS"
]
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
{
console
.
dir
(result.
data
());
if
(result.
more
())
result.
next
();
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
'crm.activity.list'
,
[
'order'
=> [
'ID'
=>
'DESC'
],
'filter'
=> [
'OWNER_TYPE_ID'
=>
3
,
'OWNER_ID'
=>
102
],
'select'
=> [
'*'
,
'COMMUNICATIONS'
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
Typical use-cases and scenarios
Using BINDINGS
Retrieving COMMUNICATIONS
Retrieving Attachments
Response Handling
Response Handling
HTTP status:
200
{
"result"
:
[
{
"ID"
:
"20"
,
"OWNER_ID"
:
"15"
,
"OWNER_TYPE_ID"
:
"3"
,
"TYPE_ID"
:
"2"
,
"PROVIDER_ID"
:
"VOXIMPLANT_CALL"
,
"PROVIDER_TYPE_ID"
:
"CALL"
,
"PROVIDER_GROUP_ID"
:
null
,
"ASSOCIATED_ENTITY_ID"
:
"0"
,
"SUBJECT"
:
"Outgoing call Andrew Nikolaev"
,
"CREATED"
:
"2020-09-27T13:26:55+03:00"
,
"LAST_UPDATED"
:
"2021-03-21T20:28:24+03:00"
,
"START_TIME"
:
"2020-09-27T13:25:00+03:00"
,
"END_TIME"
:
"2020-09-27T19:25:00+03:00"
,
"DEADLINE"
:
"2020-09-27T13:25:00+03:00"
,
"COMPLETED"
:
"Y"
,
"STATUS"
:
"2"
,
"RESPONSIBLE_ID"
:
"505"
,
"PRIORITY"
:
"2"
,
"NOTIFY_TYPE"
:
"1"
,
"NOTIFY_VALUE"
:
"15"
,
"DESCRIPTION"
:
""
,
"DESCRIPTION_TYPE"
:
"1"
,
"DIRECTION"
:
"2"
,
"LOCATION"
:
""
,
"SETTINGS"
:
[
]
,
"ORIGINATOR_ID"
:
null
,
"ORIGIN_ID"
:
null
,
"AUTHOR_ID"
:
"505"
,
"EDITOR_ID"
:
"505"
,
"PROVIDER_PARAMS"
:
[
]
,
"PROVIDER_DATA"
:
null
,
"RESULT_MARK"
:
"0"
,
"RESULT_VALUE"
:
null
,
"RESULT_SUM"
:
null
,
"RESULT_CURRENCY_ID"
:
null
,
"RESULT_STATUS"
:
"0"
,
"RESULT_STREAM"
:
"0"
,
"RESULT_SOURCE_ID"
:
null
,
"AUTOCOMPLETE_RULE"
:
"0"
}
,
// .. 49 more items
]
,
"next"
:
50
,
"total"
:
123456
,
"time"
:
{
"start"
:
1724677896.295857
,
"finish"
:
1724677897.197243
,
"duration"
:
0.901386022567749
,
"processing"
:
0.8762130737304688
,
"date_start"
:
"2024-08-26T16:11:36+03:00"
,
"date_finish"
:
"2024-08-26T16:11:37+03:00"
,
"operating_reset_at"
:
"2024-08-26T16:11:37+03:00"
,
"operating"
:
0.0162130737304688
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
The result of the operation. An array of activitys. For information about the structure of an activity, see the method
crm.activity.fields
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
"INVALID_REQUEST"
,
"error_description"
:
"Https required"
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
Private Examples
Private Examples
How to Use Examples in Documentation
Using BINDINGS
Using BINDINGS
Retrieve fields: Identifier, Name, Owner Type (Entity Type Identifier), Owner (Entity Identifier)
Selection condition: the activity is linked to both a deal and a contact
Note
When using multiple pairs in
BINDINGS
, duplication may occur in the results. For example, in the result of executing the code example below, the activity linked to both entities will be output twice.
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
'{"order":{"ID":"DESC"},"filter":{"BINDINGS":[{"OWNER_TYPE_ID":2},{"OWNER_TYPE_ID":3}]},"select":["*","COMMUNICATIONS"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"ID":"DESC"},"filter":{"BINDINGS":[{"OWNER_TYPE_ID":2},{"OWNER_TYPE_ID":3}]},"select":["*","COMMUNICATIONS"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.list
BX24
.
callMethod
(
"crm.activity.list"
,
{
order
: {
"ID"
:
"DESC"
},
filter
:
{
"BINDINGS"
: [
{
"OWNER_TYPE_ID"
:
2
},
{
"OWNER_TYPE_ID"
:
3
}
]
},
select
: [
"*"
,
"COMMUNICATIONS"
]
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
{
console
.
dir
(result.
data
());
if
(result.
more
())
result.
next
();
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
'crm.activity.list'
,
[
'order'
=> [
'ID'
=>
'DESC'
],
'filter'
=> [
'BINDINGS'
=> [
[
'OWNER_TYPE_ID'
=>
2
],
[
'OWNER_TYPE_ID'
=>
3
]
]
],
'select'
=> [
'*'
,
'COMMUNICATIONS'
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
Retrieving COMMUNICATIONS
Retrieving COMMUNICATIONS
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
'{"filter":{"ID":"20"},"select":["*","COMMUNICATIONS"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":{"ID":"20"},"select":["*","COMMUNICATIONS"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.list
BX24
.
callMethod
(
"crm.activity.list"
,
{
filter
:
{
"ID"
:
'20'
},
select
: [
"*"
,
"COMMUNICATIONS"
]
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
{
console
.
dir
(result.
data
());
if
(result.
more
())
result.
next
();
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
'crm.activity.list'
,
[
'filter'
=> [
'ID'
=>
'20'
],
'select'
=> [
'*'
,
'COMMUNICATIONS'
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
Example of Returned Data
Example of Returned Data
HTTP status:
200
{
"result"
:
[
{
"ID"
:
"20"
,
"COMMUNICATIONS"
:
[
{
"ID"
:
"23"
,
"TYPE"
:
"PHONE"
,
"VALUE"
:
"19152222222"
,
"ENTITY_ID"
:
"15"
,
"ENTITY_TYPE_ID"
:
"3"
,
"ENTITY_SETTINGS"
:
{
"HONORIFIC"
:
"1"
,
"NAME"
:
"Andrew "
,
"SECOND_NAME"
:
"Nikolaev"
,
"LAST_NAME"
:
""
,
"COMPANY_TITLE"
:
"Ltd. Fusion"
,
"COMPANY_ID"
:
"21"
}
}
]
}
]
,
"total"
:
1
,
"time"
:
{
"start"
:
1724659407.69855
,
"finish"
:
1724659407.723506
,
"duration"
:
0.02495598793029785
,
"processing"
:
0.003489971160888672
,
"date_start"
:
"2024-08-26T11:03:27+03:00"
,
"date_finish"
:
"2024-08-26T11:03:27+03:00"
}
}
Retrieving Attachments
Retrieving Attachments
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
'{"filter":{"ID":"101121"},"select":["*","STORAGE_ELEMENT_IDS"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":{"ID":"101121"},"select":["*","STORAGE_ELEMENT_IDS"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.list
BX24
.
callMethod
(
"crm.activity.list"
,
{
filter
:
{
"ID"
:
'101121'
},
select
: [
"*"
,
"STORAGE_ELEMENT_IDS"
]
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
{
console
.
dir
(result.
data
());
if
(result.
more
())
result.
next
();
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
'crm.activity.list'
,
[
'filter'
=> [
'ID'
=>
'101121'
],
'select'
=> [
'*'
,
'STORAGE_ELEMENT_IDS'
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
Example of Returned Data
Example of Returned Data
HTTP status:
200
{
"result"
:
[
{
"ID"
:
"101121"
,
"FILES"
:
[
{
"id"
:
3101820
,
"url"
:
"http://xxx.bitrix24.com/bitrix/tools/crm_show_file.php?fileId=3101820&ownerTypeId=6&ownerId=101121&auth="
}
]
}
]
,
"total"
:
1
,
"time"
:
{
"start"
:
1724659652.591025
,
"finish"
:
1724659652.623784
,
"duration"
:
0.03275895118713379
,
"processing"
:
0.00624394416809082
,
"date_start"
:
"2024-08-26T11:07:32+03:00"
,
"date_finish"
:
"2024-08-26T11:07:32+03:00"
}
}
Continue Learning
Continue Learning
How to Transfer an Activity from One Object Type to Another
How to Transfer an Activity Between Entities of the Same Type
How to Get a List of Activities from Deals
Copied
Was the article helpful?
Yes
No
Previous
Get Activity by ID
Next
Delete Activity

---

## Delete activity crm.activity.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/activity-base/crm-activity-delete

Delete activity crm.activity.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete activity crm.activity.delete
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
Who can execute the method: any user with permission to delete an activity
The method
crm.activity.delete
removes an activity of any type.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the activity in the timeline, for example
999
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
'{ "id":999 }'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.delete
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
https://**put_your_bitrix24_address**/rest/crm.activity.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.delete'
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
'crm.activity.delete'
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
'Error deleting activity: '
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
'crm.activity.delete'
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
'crm.activity.delete'
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
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation. Returns
true
if the activity was successfully deleted, otherwise —
false
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
"Access denied."
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
Activity is not found
The activity with the specified identifier was not found for the entity in CRM
Access denied
No permission to edit the entity in CRM
Application context required
Invalid parameter
PROVIDER_ID
for the activity created in the context of the application
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
Add System Activity crm.activity.add
Update System Activity crm.activity.update
Get information about the activity by ID crm.activity.get
Get the list of activities crm.activity.list
Get Description of Communication crm.activity.communication.fields
Get a list of fields for crm.activity.fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of Activities
Next
Get List of Activity Fields

---

## Get a list of fields for crm.activity.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/activity-base/crm-activity-fields

Get a list of fields for crm.activity.fields | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of fields for crm.activity.fields
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
crm.activity.fields
returns the description of the fields of the system activity.
Method Parameters
Method Parameters
No parameters
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
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.fields
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
https://**put_your_bitrix24_address**/rest/crm.activity.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.fields'
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
'crm.activity.fields'
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
'Error fetching CRM activity fields: '
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
'crm.activity.fields'
,
{},
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
'crm.activity.fields'
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
"ID"
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
}
,
"OWNER_ID"
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
"Owner ID"
}
,
"OWNER_TYPE_ID"
:
{
"type"
:
"crm_enum_ownertype"
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
"Owner Type"
}
,
"TYPE_ID"
:
{
"type"
:
"crm_enum_activitytype"
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
"Type"
}
,
"PROVIDER_ID"
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
"Provider ID"
}
,
"PROVIDER_TYPE_ID"
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
"Provider Type"
}
,
"PROVIDER_GROUP_ID"
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
"Connector Type"
}
,
"ASSOCIATED_ENTITY_ID"
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
"Associated Entity ID"
}
,
"SUBJECT"
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
"Subject"
}
,
"START_TIME"
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
"Start"
}
,
"END_TIME"
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
"Deadline"
}
,
"DEADLINE"
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
"Execution Deadline"
}
,
"COMPLETED"
:
{
"type"
:
"char"
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
"Completed"
}
,
"STATUS"
:
{
"type"
:
"crm_enum_activitystatus"
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
"Status"
}
,
"RESPONSIBLE_ID"
:
{
"type"
:
"user"
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
"Responsible"
}
,
"PRIORITY"
:
{
"type"
:
"crm_enum_activitypriority"
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
"Priority"
}
,
"NOTIFY_TYPE"
:
{
"type"
:
"crm_enum_activitynotifytype"
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
"Notification Type"
}
,
"NOTIFY_VALUE"
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
"Notification Parameter"
}
,
"DESCRIPTION"
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
"Description"
}
,
"DESCRIPTION_TYPE"
:
{
"type"
:
"crm_enum_contenttype"
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
"Description Type"
}
,
"DIRECTION"
:
{
"type"
:
"crm_enum_activitydirection"
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
"Direction"
}
,
"LOCATION"
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
"Location"
}
,
"CREATED"
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
"Creation Date"
}
,
"AUTHOR_ID"
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
}
,
"LAST_UPDATED"
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
"Last Updated Date"
}
,
"EDITOR_ID"
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
"Edited By"
}
,
"SETTINGS"
:
{
"type"
:
"object"
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
"Settings"
}
,
"ORIGIN_ID"
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
"External Code"
}
,
"ORIGINATOR_ID"
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
"External Source"
}
,
"RESULT_STATUS"
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
"RESULT_STATUS"
}
,
"RESULT_STREAM"
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
"RESULT_STREAM"
}
,
"RESULT_SOURCE_ID"
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
"RESULT_SOURCE_ID"
}
,
"PROVIDER_PARAMS"
:
{
"type"
:
"object"
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
"Provider Parameters"
}
,
"PROVIDER_DATA"
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
"Provider Data"
}
,
"RESULT_MARK"
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
"RESULT_MARK"
}
,
"RESULT_VALUE"
:
{
"type"
:
"double"
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
"RESULT_VALUE"
}
,
"RESULT_SUM"
:
{
"type"
:
"double"
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
"RESULT_SUM"
}
,
"RESULT_CURRENCY_ID"
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
"RESULT_CURRENCY_ID"
}
,
"AUTOCOMPLETE_RULE"
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
"Autocomplete"
}
,
"BINDINGS"
:
{
"type"
:
"crm_activity_binding"
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
true
,
"isDynamic"
:
false
,
"title"
:
"Bindings"
}
,
"COMMUNICATIONS"
:
{
"type"
:
"crm_activity_communication"
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
true
,
"isDynamic"
:
false
,
"title"
:
"Communication Channel"
}
,
"FILES"
:
{
"type"
:
"diskfile"
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
true
,
"isDynamic"
:
false
,
"title"
:
"Files"
}
,
"WEBDAV_ELEMENTS"
:
{
"type"
:
"diskfile"
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
true
,
"isDynamic"
:
false
,
"isDeprecated"
:
true
,
"title"
:
"Added Files"
}
,
"IS_INCOMING_CHANNEL"
:
{
"type"
:
"char"
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
"IS_INCOMING_CHANNEL"
}
}
,
"time"
:
{
"start"
:
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response. Values for the
result
field correspond to
fields of the object
.
time
time
Information about the execution time of the request
Overview of System Activity Fields
Overview of System Activity Fields
Required parameters are marked with *
Field
type
Description
Note
ID
*
integer
Activity ID
Read-only
OWNER_ID
*
integer
CRM entity ID
Can be changed using the
crm.activity.binding.move
method
OWNER_TYPE_ID
*
integer
CRM object type ID
Immutable
TYPE_ID
*
crm_enum_activitytype
Activity type
Required, immutable
ASSOCIATED_ENTITY_ID
integer
Integer ID of the associated entity
Read-only
AUTHOR_ID
*
integer
Integer ID of the user who created the activity
AUTOCOMPLETE_RULE
integer
Integer ID of the rule that triggered the autocomplete
BINDINGS
crm_activity_binding
Bindings to CRM entities
Multiple, read-only
COMMUNICATIONS
*
crm_activity_communication
Description of communication
Multiple, required
COMPLETED
*
char
Flag indicating whether the activity is completed (
Y
N
)
CREATED
*
datetime
Date and time the activity was created
DEADLINE
datetime
Date and time of the activity's execution deadline
This field is not set directly; the value is taken from START_TIME for calls and meetings and from END_TIME for tasks
DESCRIPTION
string
Text description of the activity
DESCRIPTION_TYPE
crm.enum.contenttype
Description type
DIRECTION
crm.enum.activitydirection
Direction of the activity: incoming/outgoing.
Relevant for calls and emails, not used for meetings
EDITOR_ID
user
Integer ID of the user who edited the activity
Read-only
END_TIME
datetime
Time the activity ended
FILES
diskfile
Files added to the activity
Multiple
LAST_UPDATED
datetime
Date of the last update
Read-only
LOCATION
string
Location
NOTIFY_TYPE
crm.enum.activitynotifytype
Notification type
NOTIFY_VALUE
integer
Notification value
Read-only
ORIGINATOR_ID
string
Data source ID
Used only for binding to an external source
ORIGIN_ID
string
ID of the element in the data source
Used only for binding to an external source
ORIGIN_VERSION
string
Original version
Used to protect data from accidental overwriting by an external system. If the data was imported and not changed in the external system, such data can be edited in CRM without fear that the next export will lead to data overwriting
PRIORITY
crm.enum.activitypriority
Priority
PROVIDER_DATA
string
Additional provider data
PROVIDER_GROUP_ID
string
Provider group ID
PROVIDER_ID
string
Provider ID
Read-only
PROVIDER_TYPE_ID
string
Provider type ID
Status from the directory
PROVIDER_PARAMS
object
Additional provider parameters
RESPONSIBLE_ID
*
user
Integer ID of the user responsible for the activity
Required
RESULT_CURRENCY_ID
string
RESULT_MARK
integer
RESULT_SOURCE_ID
string
RESULT_STATUS
integer
RESULT_STREAM
integer
Report statistics
RESULT_SUM
double
RESULT_VALUE
double
SETTINGS
object
Additional settings
START_TIME
datetime
Time the activity starts
STATUS
crm_enum_activitystatus
Activity status
SUBJECT
string
Additional description of the activity
Required
WEBDAV_ELEMENTS
diskfile
Added files
Multiple. Deprecated, kept for compatibility
IS_INCOMING_CHANNEL
char
Flag indicating whether the activity was created from an incoming channel (
Y
/
N
)
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
"Access denied."
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
Add System Activity crm.activity.add
Update System Activity crm.activity.update
Delete activity crm.activity.delete
Get the list of activities crm.activity.list
Get Description of Communication crm.activity.communication.fields
Get information about the activity by ID crm.activity.get
Copied
Was the article helpful?
Yes
No
Previous
Delete Activity
Next
Get Communication Description

---

## Get Description of Communication crm.activity.communication.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/activity-base/crm-activity-communication-fields

Get Description of Communication crm.activity.communication.fields | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Description of Communication crm.activity.communication.fields
Method Parameters
Code Examples
Response Handling
Returned Data
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method
crm.activity.communication.fields
returns the description of communication for an activity. Communications store phone numbers in calls, email addresses in e-mails, and names in meetings.
Method Parameters
Method Parameters
No parameters
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
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.communication.fields
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
https://**put_your_bitrix24_address**/rest/crm.activity.communication.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.communication.fields'
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
'crm.activity.communication.fields'
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
'Error fetching communication fields: '
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
'crm.activity.communication.fields'
,
{},
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
'crm.activity.communication.fields'
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
"ID"
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
}
,
"ACTIVITY_ID"
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
"Activity"
}
,
"ENTITY_ID"
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
"Entity ID"
}
,
"ENTITY_TYPE_ID"
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
"Entity Type"
}
,
"TYPE"
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
"Type"
}
,
"VALUE"
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
"Value"
}
}
,
"time"
:
{
"start"
:
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response. Values for the
result
field correspond to
fields of the object
.
time
time
Information about the execution time of the request
Overview of Activity Communication Fields
Overview of Activity Communication Fields
Required parameters are marked with *
Field
type
Description
ID
*
integer
Identifier of the communication
ACTIVITY_ID
*
integer
Identifier of the activity
ENTITY_ID
*
integer
Identifier of the CRM entity
ENTITY_TYPE_ID
*
integer
Identifier of the CRM object type
TYPE_ID
*
integer
Type of communication
VALUE
*
integer
Value of the communication
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
"Access denied."
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
Add System Activity crm.activity.add
Update System Activity crm.activity.update
Delete activity crm.activity.delete
Get the list of activities crm.activity.list
Get a list of fields for crm.activity.fields
Get information about the activity by ID crm.activity.get
Copied
Was the article helpful?
Yes
No
Previous
Get List of Activity Fields
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/todo/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Overview of Methods
Additional
Quick navigation:
all methods
User documentation:
Universal activity in CRM
Universal activities are a type of activity with extended settings. In the universal activity card, you can synchronize the activity with the calendar, choose a meeting location with the client, add colleagues, select a client from the CRM entity, categorize activity by color, and choose a meeting room. Some extended settings are available to the employee on the Bitrix24 side.
Scope:
crm
Who can execute the method: any user with the appropriate access permissions
Overview of Methods
Overview of Methods
Method
Description
crm.activity.todo.add
Adds a new universal activity to the timeline
crm.activity.todo.update
Updates the universal activity
crm.activity.todo.updateColor
Updates the color of the universal activity
crm.activity.todo.updateDeadline
Updates the deadline of the universal activity
crm.activity.todo.updateDescription
Updates the description of the universal activity
crm.activity.todo.updateResponsibleUser
Updates the responsible user for the universal activity
crm.activity.get
Retrieves information about the universal activity by its ID
crm.activity.list
Retrieves a list of all universal activity for the CRM entity with the filter
PROVIDER_ID
=
"CRM_TODO"
crm.activity.delete
Deletes the universal activity by its ID
Additional
Additional
CRM Object Type
Copied
Was the article helpful?
Yes
No
Previous
Get Information about Configurable Activity
Next
Add Universal Activity

---

## Add Universal Activity crm.activity.todo.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/todo/crm-activity-todo-add

Add Universal Activity crm.activity.todo.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Universal Activity crm.activity.todo.add
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
Who can execute the method: a user with permission to edit the CRM entity to which the activity is being added.
The method
crm.activity.todo.add
adds a universal activity to the timeline.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ownerTypeId
*
integer
Identifier of the CRM object type
to which the activity is linked, for example
2
for a deal
ownerId
*
integer
Identifier of the CRM entity to which the activity is linked, for example,
1
deadline
*
datetime
Deadline for the activity, for example
2025-02-03T15:00:00
title
string
Title of the activity, default is an empty string
description
string
Description of the activity, default is an empty string
responsibleId
integer
Identifier of the user responsible for the activity, for example
1
parentActivityId
integer
Identifier of the activity in the timeline with which the created activity can be linked, for example
888
pingOffsets
array
An array containing integer values in minutes that allow you to set reminder times for the activity. For example,
[0, 15]
means that 2 reminders will be created, one 15 minutes before the deadline and one at the moment the deadline occurs. Default is an empty array, with no reminders
colorId
string
Identifier of the activity color in the timeline, for example
1
. There are 8 colors available, values from 1 to 7 and a default color if none is specified:
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
'{"ownerTypeId":2,"ownerId":1,"deadline":"'
"
$(date -Iseconds)
"
'","title":"Activity Title","description":"Activity Description","responsibleId":5,"pingOffsets":[0,15],"colorId":"2"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.todo.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ownerTypeId":2,"ownerId":1,"deadline":"'
"
$(date -Iseconds)
"
'","title":"Activity Title","description":"Activity Description","responsibleId":5,"pingOffsets":[0,15],"colorId":"2","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.todo.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.todo.add'
,
{
ownerTypeId
:
2
,
ownerId
:
1
,
deadline
: (
new
Date
()),
title
:
'Activity Title'
,
description
:
'Activity Description'
,
responsibleId
:
5
,
pingOffsets
: [
0
,
15
],
colorId
:
'2'
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
'crm.activity.todo.add'
,
[
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'deadline'
=> (
new
DateTime
()),
'title'
=>
'Activity Title'
,
'description'
=>
'Activity Description'
,
'responsibleId'
=>
5
,
'pingOffsets'
=> [
0
,
15
],
'colorId'
=>
'2'
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
'Error adding todo activity: '
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
"crm.activity.todo.add"
,
{
ownerTypeId
:
2
,
ownerId
:
1
,
deadline
: (
new
Date
()),
title
:
'Activity Title'
,
description
:
'Activity Description'
,
responsibleId
:
5
,
pingOffsets
: [
0
,
15
],
colorId
:
'2'
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
'crm.activity.todo.add'
,
[
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'deadline'
=>
date
(
'c'
), // Current date
and
time in ISO
8601
format
'title'
=>
'Activity Title'
,
'description'
=>
'Activity Description'
,
'responsibleId'
=>
5
,
'pingOffsets'
=> [
0
,
15
],
'colorId'
=>
'2'
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
"id"
:
999
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
On success, returns an object containing the identifier of the added activity
id
, on error =
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
100
Required fields are missing
NOT_FOUND
CRM entity not found
ACCESS_DENIED
Insufficient permissions to perform the operation
OWNER_NOT_FOUND
Owner of the entity not found
WRONG_DATETIME_FORMAT
Incorrect date format
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
Update universal deal crm.activity.todo.update
Update Deadline for Universal Activity crm.activity.todo.updateDeadline
Update the description of the universal activity crm.activity.todo.updateDescription
Update the color of the universal deal crm.activity.todo.updateColor
Update the responsible user for the universal activity crm.activity.todo.updateResponsibleUser
Add an activity to a new lead or deal depending on the CRM mode
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Universal Activity

---

## Update universal deal crm.activity.todo.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/todo/crm-activity-todo-update

Update universal deal crm.activity.todo.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update universal deal crm.activity.todo.update
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
Who can execute the method: a user with permission to edit the CRM entity for which the activity is being updated
The method
crm.activity.todo.update
updates a universal deal.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the deal being updated, for example
999
ownerTypeId
*
integer
Identifier of the CRM object type
to which the deal is linked, for example
2
for a deal
ownerId
*
integer
Identifier of the CRM entity to which the deal is linked, for example
1
deadline
*
datetime
Deadline of the deal, for example
2025-02-03T15:00:00
title
string
Title of the deal
description
string
Description of the deal
responsibleId
integer
Identifier of the user responsible for the deal, for example
1
parentActivityId
integer
Identifier of the deal in the timeline that can be linked to the updated deal, for example
888
pingOffsets
array
An array containing integer values in minutes that allow you to set reminder times for the deal. For example,
[0, 15]
means that 2 reminders will be created, which will come 15 minutes before the deadline and at the moment when the deadline occurs. By default, an empty array, with no reminders
colorId
string
Identifier of the deal's color in the timeline, for example
1
. There are 8 colors available, values from 1 to 7 and a default color if none is specified:
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
'{"id":999,"ownerTypeId":2,"ownerId":1,"deadline":"**put_current_date_here**","title":"New deal title","description":"New deal description","responsibleId":1,"pingOffsets":[15,30],"colorId":"7"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.todo.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"ownerTypeId":2,"ownerId":1,"deadline":"**put_current_date_here**","title":"New deal title","description":"New deal description","responsibleId":1,"pingOffsets":[15,30],"colorId":"7","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.todo.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.todo.update'
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
deadline
: (
new
Date
()),
title
:
'New deal title'
,
description
:
'New deal description'
,
responsibleId
:
1
,
pingOffsets
: [
15
,
30
],
colorId
:
'7'
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
'crm.activity.todo.update'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'deadline'
=> (
new
DateTime
()),
'title'
=>
'New deal title'
,
'description'
=>
'New deal description'
,
'responsibleId'
=>
1
,
'pingOffsets'
=> [
15
,
30
],
'colorId'
=>
'7'
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
// Your logic for processing data
processData
(
$result
->
data
());
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
'Error updating todo activity: '
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
"crm.activity.todo.update"
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
deadline
: (
new
Date
()),
title
:
'New deal title'
,
description
:
'New deal description'
,
responsibleId
:
1
,
pingOffsets
: [
15
,
30
],
colorId
:
'7'
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
'crm.activity.todo.update'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'deadline'
=>
date
(
'c'
), // Assuming you want the current date in ISO
8601
format
'title'
=>
'New deal title'
,
'description'
=>
'New deal description'
,
'responsibleId'
=>
1
,
'pingOffsets'
=> [
15
,
30
],
'colorId'
=>
'7'
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
"id"
:
999
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
On success, returns an object containing the integer identifier of the updated deal
id
, on error =
null
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
100
Required fields are missing
NOT_FOUND
CRM entity not found
ACCESS_DENIED
Insufficient permissions to perform the operation
OWNER_NOT_FOUND
Owner of the entity not found
WRONG_DATETIME_FORMAT
Incorrect date format
CAN_NOT_UPDATE_COMPLETED_TODO
Completed deal cannot be modified
ERROR_PARENT_ACTIVITY_RESTRICT
Cannot schedule a deal for a closed deal
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
Add Universal Activity crm.activity.todo.add
Update Deadline for Universal Activity crm.activity.todo.updateDeadline
Update the description of the universal activity crm.activity.todo.updateDescription
Update the color of the universal deal crm.activity.todo.updateColor
Update the responsible user for the universal activity crm.activity.todo.updateResponsibleUser
Copied
Was the article helpful?
Yes
No
Previous
Add Universal Activity
Next
Update Universal Activity Color

---

## Update the color of the universal deal crm.activity.todo.updateColor

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/todo/crm-activity-todo-update-color

Update the color of the universal deal crm.activity.todo.updateColor | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update the color of the universal deal crm.activity.todo.updateColor
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
Who can execute the method: a user with edit access permission for the CRM entity to which the activity is linked
The method
crm.activity.todo.updateColor
updates the color of the universal deal.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the deal being updated, for example
999
ownerTypeId
*
integer
Identifier of the CRM object type
to which the deal is linked, for example
2
for a deal
ownerId
*
integer
Identifier of the CRM entity to which the deal is linked, for example,
1
colorId
*
string
Identifier of the deal's color in the timeline, for example
1
. There are 8 available colors, values from 1 to 7 and the default color if none is specified:
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
'{"id":999,"ownerTypeId":2,"ownerId":1,"colorId":"3"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.todo.updateColor
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"ownerTypeId":2,"ownerId":1,"colorId":"3","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.todo.updateColor
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.todo.updateColor'
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
colorId
:
'3'
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
'crm.activity.todo.updateColor'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'colorId'
=>
'3'
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
'Error updating todo color: '
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
"crm.activity.todo.updateColor"
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
colorId
:
'3'
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
'crm.activity.todo.updateColor'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'colorId'
=>
'3'
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
"id"
:
999
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
On success, returns an object containing the identifier of the updated deal
id
, on error =
null
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
100
Required fields are missing
NOT_FOUND
CRM entity not found
ACCESS_DENIED
Insufficient permissions to perform the operation
OWNER_NOT_FOUND
Owner of the entity not found
CAN_NOT_UPDATE_COLOR_COMPLETED_TODO
Cannot change color in a closed deal
CAN_NOT_UPDATE_WRONG_COLOR_TODO
Invalid color value
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
Add Universal Activity crm.activity.todo.add
Update universal deal crm.activity.todo.update
Update Deadline for Universal Activity crm.activity.todo.updateDeadline
Update the description of the universal activity crm.activity.todo.updateDescription
Update the responsible user for the universal activity crm.activity.todo.updateResponsibleUser
Copied
Was the article helpful?
Yes
No
Previous
Update Universal Activity
Next
Update Universal Activity Deadline

---

## Update Deadline for Universal Activity crm.activity.todo.updateDeadline

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/todo/crm-activity-todo-update-deadline

Update Deadline for Universal Activity crm.activity.todo.updateDeadline | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Deadline for Universal Activity crm.activity.todo.updateDeadline
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
Who can execute the method: a user with edit access permission for the CRM entity associated with the activity being updated.
The method
crm.activity.todo.updateDeadline
changes the deadline of a universal activity.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the activity being updated, for example
999
ownerTypeId
*
integer
Identifier of the CRM object type
to which the activity is linked, for example
2
for a deal
ownerId
*
integer
Identifier of the CRM entity to which the activity is linked, for example,
1
value
*
datetime
New deadline for the activity
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
'{"id":999,"ownerTypeId":2,"ownerId":1,"value":"'
"
$(date -Iseconds)
"
'"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.todo.updateDeadline
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"ownerTypeId":2,"ownerId":1,"value":"**put_current_date_here**","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.todo.updateDeadline
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.todo.updateDeadline'
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
value
:
new
Date
()
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
'crm.activity.todo.updateDeadline'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'value'
=>
date
(
'Y-m-d H:i:s'
),
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
'Error updating todo deadline: '
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
"crm.activity.todo.updateDeadline"
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
value
:
new
Date
()
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
'crm.activity.todo.updateDeadline'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'value'
=>
date
(
'c'
) // Current date
and
time in ISO
8601
format
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
"id"
:
999
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
On success, returns an object containing the identifier of the updated activity
id
, on error =
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
100
Required fields not provided
NOT_FOUND
CRM entity not found
ACCESS_DENIED
Insufficient permissions to perform the operation
OWNER_NOT_FOUND
Owner of the entity not found
WRONG_DATETIME_FORMAT
Incorrect date format
CAN_NOT_UPDATE_COMPLETED_TODO
Completed activity cannot be modified
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
Add Universal Activity crm.activity.todo.add
Update universal deal crm.activity.todo.update
Update the description of the universal activity crm.activity.todo.updateDescription
Update the color of the universal deal crm.activity.todo.updateColor
Update the responsible user for the universal activity crm.activity.todo.updateResponsibleUser
Copied
Was the article helpful?
Yes
No
Previous
Update Universal Activity Color
Next
Update Universal Activity Description

---

## Update the description of the universal activity crm.activity.todo.updateDescription

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/todo/crm-activity-todo-update-description

Update the description of the universal activity crm.activity.todo.updateDescription | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update the description of the universal activity crm.activity.todo.updateDescription
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
Who can execute the method: a user with permission to edit the CRM entity for which the activity is being updated
The method
crm.activity.todo.updateDescription
changes the description in the universal activity.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the activity being updated, for example
999
ownerTypeId
*
integer
Identifier of the CRM object type
to which the activity is linked, for example
2
for a deal
ownerId
*
integer
Identifier of the CRM entity to which the activity is linked, for example
1
value
*
string
New description of the activity
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
'{"id":999,"ownerTypeId":2,"ownerId":1,"value":"New activity description"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.todo.updateDescription
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"ownerTypeId":2,"ownerId":1,"value":"New activity description","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.todo.updateDescription
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.todo.updateDescription'
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
value
:
'New activity description'
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
'crm.activity.todo.updateDescription'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'value'
=>
'New activity description'
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
'Error updating todo description: '
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
"crm.activity.todo.updateDescription"
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
value
:
'New activity description'
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
'crm.activity.todo.updateDescription'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'value'
=>
'New activity description'
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
"id"
:
999
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
On success, returns an object containing the identifier of the updated activity
id
, on error =
null
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
100
Required fields are missing
NOT_FOUND
CRM entity not found
ACCESS_DENIED
Insufficient permissions to perform the operation
OWNER_NOT_FOUND
Owner of the entity not found
CAN_NOT_UPDATE_COMPLETED_TODO
Closed activity cannot be modified
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
Add Universal Activity crm.activity.todo.add
Update universal deal crm.activity.todo.update
Update Deadline for Universal Activity crm.activity.todo.updateDeadline
Update the color of the universal deal crm.activity.todo.updateColor
Update the responsible user for the universal activity crm.activity.todo.updateResponsibleUser
Copied
Was the article helpful?
Yes
No
Previous
Update Universal Activity Deadline
Next
Update Responsible User for Universal Activity

---

## Update the responsible user for the universal activity crm.activity.todo.updateResponsibleUser

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/todo/crm-activity-todo-update-responsible-user

Update the responsible user for the universal activity crm.activity.todo.updateResponsibleUser | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update the responsible user for the universal activity crm.activity.todo.updateResponsibleUser
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
Who can execute the method: a user with permission to edit the CRM entity for which the activity is being updated.
The method
crm.activity.todo.updateResponsibleUser
updates the responsible user for the universal activity.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the activity being updated, for example
999
ownerTypeId
*
integer
Identifier of the CRM object type
to which the activity is linked, for example
2
for a deal
ownerId
*
integer
Identifier of the CRM entity to which the activity is linked, for example
1
responsibleId
*
integer
Identifier of the user who will become responsible for the activity, for example
1
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
'{"id":999,"ownerTypeId":2,"ownerId":1,"responsibleId":5}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.todo.updateResponsibleUser
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"ownerTypeId":2,"ownerId":1,"responsibleId":5,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.todo.updateResponsibleUser
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.todo.updateResponsibleUser'
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
responsibleId
:
5
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
'crm.activity.todo.updateResponsibleUser'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'responsibleId'
=>
5
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
'Error updating responsible user: '
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
"crm.activity.todo.updateResponsibleUser"
,
{
id
:
999
,
ownerTypeId
:
2
,
ownerId
:
1
,
responsibleId
:
5
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
'crm.activity.todo.updateResponsibleUser'
,
[
'id'
=>
999
,
'ownerTypeId'
=>
2
,
'ownerId'
=>
1
,
'responsibleId'
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
{
"id"
:
999
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
On success, returns an object containing the identifier of the updated activity
id
, on error =
null
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
100
Required fields are missing
NOT_FOUND
CRM entity not found
ACCESS_DENIED
Insufficient permissions to perform the operation
OWNER_NOT_FOUND
Owner of the entity not found
CAN_NOT_UPDATE_RESPONSIBLE_USER_COMPLETED_TODO
Cannot change the responsible user in a closed activity
INVALID_ARG_VALUE
Parameter "responsibleId" must be greater than 0
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
Add Universal Activity crm.activity.todo.add
Update universal deal crm.activity.todo.update
Update Deadline for Universal Activity crm.activity.todo.updateDeadline
Update the description of the universal activity crm.activity.todo.updateDescription
Update the color of the universal deal crm.activity.todo.updateColor
Copied
Was the article helpful?
Yes
No
Previous
Update Universal Activity Description
Next
Overview of Methods

---

## Managing Activity Relationships in the Timeline

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/binding/index

Managing Activity Relationships in the Timeline | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Managing Activity Relationships in the Timeline
Scope:
crm
Who can execute the method: any user
Methods for managing the bindings of activities to CRM entities.
Overview of Methods
Overview of Methods
Method
Description
crm.activity.binding.add
Adds a binding of an activity to a CRM entity
crm.activity.binding.move
Updates the binding of an activity to a CRM entity
crm.activity.binding.list
Retrieves a list of all activity bindings
crm.activity.binding.delete
Deletes the binding of an activity to a CRM entity
Copied
Was the article helpful?
Yes
No
Previous
Update Responsible User for Universal Activity
Next
Add CRM Activity Relationship with CRM Entity

---

## Add a deal binding to a CRM entity crm.activity.binding.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/binding/crm-activity-binding-add

Add a deal binding to a CRM entity crm.activity.binding.add | Bitrix24 REST API and Marketplace Applications
Add a deal binding to a CRM entity crm.activity.binding.add
Add a deal binding to a CRM entity crm.activity.binding.add
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
Who can execute the method: user with editing access permission for CRM entities
The method
crm.activity.binding.add
adds a binding of a deal to a CRM entity.
Limit
The maximum number of bindings for a single deal is 100 CRM entities.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
activityId
*
integer
Integer identifier of the deal in the timeline, for example
999
entityTypeId
*
integer
Integer identifier of the CRM object type
to which the deal should be bound, for example
2
for a deal
entityId
*
integer
Integer identifier of the CRM entity to which the deal should be bound, for example
1
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
'{"activityId":999, "entityTypeId":2, "entityId": 1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.binding.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"activityId":999, "entityTypeId":2, "entityId": 1, "auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.binding.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.binding.add'
,
{
activityId
:
999
,
// Deal ID
entityTypeId
:
2
,
// CRM object type ID
entityId
:
1
// CRM entity ID
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
log
(
'Result:'
, result);
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
'crm.activity.binding.add'
,
[
'activityId'
=>
999
, // Deal ID
'entityTypeId'
=>
2
, // CRM
object
type ID
'entityId'
=>
1
// CRM entity ID
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
'Error adding activity binding: '
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
'crm.activity.binding.add'
,
{
activityId
:
999
,
// Deal ID
entityTypeId
:
2
,
// CRM object type ID
entityId
:
1
// CRM entity ID
},
function
(
result
) {
if
(result.
error
()) {
console
.
error
(
'Error:'
, result.
error
());
}
else
{
console
.
log
(
'Result:'
, result.
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
'crm.activity.binding.add'
,
[
'activityId'
=>
999
, // Deal ID
'entityTypeId'
=>
2
, // CRM
object
type ID
'entityId'
=>
1
// CRM entity ID
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
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation. Returns
true
if the binding was successfully created, otherwise
false
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
"Entity not found"
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
100
Required fields not provided
NOT_FOUND
Entity not found
OWNER_NOT_FOUND
Owner of the entity not found
ACCESS_DENIED
Insufficient rights to perform the operation
ACTIVITY_IS_ALREADY_BOUND
The deal is already bound to this entity
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
Get a list of all bindings for the deal crm.activity.binding.list
Delete the connection of the activity with the CRM entity crm.activity.binding.delete
Update the deal's connection with the CRM entity crm.activity.binding.move
How to Transfer an Activity from One Object Type to Another
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update CRM Activity Relationship with CRM Entity

---

## Update the deal's connection with the CRM entity crm.activity.binding.move

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/binding/crm-activity-binding-move

Update the deal's connection with the CRM entity crm.activity.binding.move | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update the deal's connection with the CRM entity crm.activity.binding.move
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
Who can execute the method: user with editing access permission for CRM entities
The method
crm.activity.binding.move
updates the connection of a deal with a CRM entity.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
activityId
*
integer
Identifier of the deal in the timeline, for example
999
sourceEntityTypeId
*
integer
Identifier of the CRM object type
to which the deal is linked, for example
2
for a deal
sourceEntityId
*
integer
Identifier of the CRM entity to which the deal is linked, for example
1
targetEntityTypeId
*
integer
Identifier of the CRM object type
to which the deal needs to be linked, for example
2
for a deal
targetEntityId
*
integer
Identifier of the CRM entity to which the deal needs to be linked, for example
100
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
'{"activityId":999, "sourceEntityTypeId":2, "sourceEntityId": 1, "targetEntityTypeId":2, "targetEntityId": 100}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.binding.move
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"activityId":999,"sourceEntityTypeId":2,"sourceEntityId":1,"targetEntityTypeId":2,"targetEntityId":100,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.binding.move
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.binding.move'
,
{
activityId
:
999
,
// ID of the deal
sourceEntityTypeId
:
2
,
// Type of the object to which the deal is linked
sourceEntityId
:
1
,
// ID of the entity to which the deal is linked
targetEntityTypeId
:
2
,
// Type of the object to which the deal will be linked
targetEntityId
:
100
// ID of the entity to which the deal will be linked
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
log
(
'Result:'
, result);
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
'crm.activity.binding.move'
,
[
'activityId'
=>
999
,
'sourceEntityTypeId'
=>
2
,
'sourceEntityId'
=>
1
,
'targetEntityTypeId'
=>
2
,
'targetEntityId'
=>
100
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
'Error moving activity binding: '
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
'crm.activity.binding.move'
,
{
activityId
:
999
,
// ID of the deal
sourceEntityTypeId
:
2
,
// Type of the object to which the deal is linked
sourceEntityId
:
1
,
// ID of the entity to which the deal is linked
targetEntityTypeId
:
2
,
// Type of the object to which the deal will be linked
targetEntityId
:
100
// ID of the entity to which the deal will be linked
},
function
(
result
) {
if
(result.
error
()) {
console
.
error
(
'Error:'
, result.
error
());
}
else
{
console
.
log
(
'Result:'
, result.
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
'crm.activity.binding.move'
,
[
'activityId'
=>
999
, // ID of the deal
'sourceEntityTypeId'
=>
2
, // Type of the
object
to which the deal is linked
'sourceEntityId'
=>
1
, // ID of the entity to which the deal is linked
'targetEntityTypeId'
=>
2
, // Type of the
object
to which the deal will be linked
'targetEntityId'
=>
100
// ID of the entity to which the deal will be linked
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
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation. Returns
true
if the connection was successfully changed, otherwise returns
false
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
100
Required fields not provided
NOT_FOUND
Element not found
OWNER_NOT_FOUND
Owner of the element not found
SOURCE_AND_TARGET_ENTITY_TYPES_ARE_NOT_EQUAL
Cannot move the deal from one CRM object type to another
SOURCE_AND_TARGET_ENTITY_ID_ARE_EQUAL_ERROR
Cannot move the deal to the same deal
ACCESS_DENIED
Insufficient rights to perform the operation
ACTIVITY_IS_ALREADY_BOUND
The deal is already linked to this entity
BINDING_NOT_FOUND
The deal is not linked to the specified entity
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
Get a list of all bindings for the deal crm.activity.binding.list
Delete the connection of the activity with the CRM entity crm.activity.binding.delete
Add a deal binding to a CRM entity crm.activity.binding.add
How to Transfer an Activity Between Entities of the Same Type
How to Transfer an Activity from One Object Type to Another
Copied
Was the article helpful?
Yes
No
Previous
Add CRM Activity Relationship with CRM Entity
Next
Retrieve List of CRM Activity Relationships

---

## Get a list of all bindings for the deal crm.activity.binding.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/binding/crm-activity-binding-list

Get a list of all bindings for the deal crm.activity.binding.list | Bitrix24 REST API and Marketplace Applications
Get a list of all bindings for the deal crm.activity.binding.list
Get a list of all bindings for the deal crm.activity.binding.list
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
Who can execute the method: user with read access permission for CRM entities
The method
crm.activity.binding.list
retrieves a list of all bindings for the deal.
The method will return an array, where each element will be an array containing:
entityTypeId
— integer identifier of the
CRM object type
entityId
— integer identifier of the CRM entity
The result will only include entities that the current user has read access to.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
activityId
*
integer
Integer identifier of the deal in the timeline, for example
999
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
'{"activityId":999}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.binding.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"activityId":999,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.binding.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.activity.binding.list'
,
{
activityId
:
999
// Deal ID
}
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in chunks and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.activity.binding.list'
, {
activityId
:
999
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.binding.list'
, {
activityId
:
999
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
'crm.activity.binding.list'
,
[
'activityId'
=>
999
, // Deal ID
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
'Result: '
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
'crm.activity.binding.list'
,
{
activityId
:
999
// Deal ID
},
function
(
result
) {
if
(result.
error
()) {
console
.
error
(
'Error:'
, result.
error
());
}
else
{
console
.
log
(
'Result:'
, result.
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
'crm.activity.binding.list'
,
[
'activityId'
=>
999
// Deal ID
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
{
"entityTypeId"
:
1
,
"entityId"
:
123
}
,
{
"entityTypeId"
:
2
,
"entityId"
:
456
}
,
{
"entityTypeId"
:
3
,
"entityId"
:
789
}
]
,
"time"
:
{
"start"
:
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
array
Result of the operation. Returns an array, where each element will be an array containing:
entityTypeId
— integer identifier of the
CRM object type
entityId
— integer identifier of the CRM entity
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
100
Required fields not provided
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
Add a deal binding to a CRM entity crm.activity.binding.add
Delete the connection of the activity with the CRM entity crm.activity.binding.delete
Update the deal's connection with the CRM entity crm.activity.binding.move
Copied
Was the article helpful?
Yes
No
Previous
Update CRM Activity Relationship with CRM Entity
Next
Delete CRM Activity Relationship with CRM Entity

---

## Delete the connection of the activity with the CRM entity crm.activity.binding.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/binding/crm-activity-binding-delete

Delete the connection of the activity with the CRM entity crm.activity.binding.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete the connection of the activity with the CRM entity crm.activity.binding.delete
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
Who can execute the method: user with permission to edit CRM entities
The method
crm.activity.binding.delete
removes the connection of the activity with the CRM entity. If the activity is linked to only one entity, this connection cannot be deleted.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
activityId
*
integer
Integer identifier of the activity in the timeline, for example
999
entityTypeId
*
integer
Integer identifier of the CRM entity type
to which the activity is being unlinked, for example
2
for a deal
entityId
*
integer
Integer identifier of the CRM entity to which the activity is being unlinked, for example
1
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
'{"activityId":999, "entityTypeId":2, "entityId": 1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.binding.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"activityId":999, "entityTypeId":2, "entityId": 1, "auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.binding.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.binding.delete'
,
{
activityId
:
999
,
// Activity ID
entityTypeId
:
2
,
// CRM entity type ID
entityId
:
1
// CRM entity ID
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
log
(
'Result:'
, result);
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
'crm.activity.binding.delete'
,
[
'activityId'
=>
999
, // Activity ID
'entityTypeId'
=>
2
, // CRM entity type ID
'entityId'
=>
1
// CRM entity ID
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
'Result: '
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
'crm.activity.binding.delete'
,
{
activityId
:
999
,
// Activity ID
entityTypeId
:
2
,
// CRM entity type ID
entityId
:
1
// CRM entity ID
},
function
(
result
) {
if
(result.
error
()) {
console
.
error
(
'Error:'
, result.
error
());
}
else
{
console
.
log
(
'Result:'
, result.
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
'crm.activity.binding.delete'
,
[
'activityId'
=>
999
, // Activity ID
'entityTypeId'
=>
2
, // CRM entity type ID
'entityId'
=>
1
// CRM entity ID
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
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation. Returns
true
if the connection was successfully deleted, otherwise
false
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
"Entity not found"
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
100
Required fields not provided
NOT_FOUND
Entity not found
OWNER_NOT_FOUND
Owner of the entity not found
ACCESS_DENIED
Insufficient permissions to perform the operation
BINDING_NOT_FOUND
Activity not linked to this entity
LAST_BINDING_CANNOT_BE_DELETED
Cannot delete the only binding of the activity to the entity
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
Get a list of all bindings for the deal crm.activity.binding.list
Add a deal binding to a CRM entity crm.activity.binding.add
Update the deal's connection with the CRM entity crm.activity.binding.move
How to Transfer an Activity from One Object Type to Another
Copied
Was the article helpful?
Yes
No
Previous
Retrieve List of CRM Activity Relationships
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/types/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Quick navigation:
all methods
User documentation:
Timeline in CRM entity
Applications can register custom activity types: upload a custom icon and specify the type name. For example, you can create your own activity type with an icon and name of your application.
Scope:
crm
Who can execute the method: any user
Overview of Methods
Overview of Methods
Method
Description
crm.activity.type.add
Registers a custom activity type with a specified name and icon
crm.activity.type.list
Retrieves a list of activities
crm.activity.type.delete
Deletes a custom type
Copied
Was the article helpful?
Yes
No
Previous
Delete CRM Activity Relationship with CRM Entity
Next
Add Custom Type

---

## Add Custom Activity Type crm.activity.type.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/types/crm-activity-type-add

Add Custom Activity Type crm.activity.type.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Custom Activity Type crm.activity.type.add
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
Who can execute the method:
any user
The method
crm.activity.type.add
registers a custom activity type by specifying a name and an icon.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
Field values for adding a new custom activity type in the form of a structure:
fields
:
{
"TYPE_ID"
:
'value'
,
"NAME"
:
'value'
,
"ICON_FILE"
:
'value'
,
"IS_CONFIGURABLE_TYPE"
:
'value'
,
}
A detailed description is provided
below
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
TYPE_ID
*
string
String value of the activity type, for example
QuickBooks and other similar platforms
. When creating an activity, this field is
PROVIDER_TYPE_ID
NAME
string
Name of the activity type, for example
Activity for QuickBooks
for a deal. Default is an empty string
ICON_FILE
attached_diskfile
Icon file for the activity type, described according to
rules
IS_CONFIGURABLE_TYPE
string
Default value is
N
. Value
Y
indicates that the type will be used for
configurable activities
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
'{"fields":{"TYPE_ID":"QuickBooks and other similar platforms","NAME":"Activity for QuickBooks","ICON_FILE":"@type-icon","IS_CONFIGURABLE_TYPE":"N"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.type.add
After this, it is sufficient to specify your type when creating an activity, and the icon and name will be loaded automatically.
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"OWNER_TYPE_ID":1,"OWNER_ID":selectedEntityId,"PROVIDER_ID":"REST_APP","PROVIDER_TYPE_ID":"QuickBooks and other similar platforms","SUBJECT":"New Activity","COMPLETED":"N","RESPONSIBLE_ID":1,"DESCRIPTION":"Description of the new activity"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.activity.type.add"
,
{
fields
:
{
"TYPE_ID"
:
'QuickBooks and other similar platforms'
,
"NAME"
:
"Activity for QuickBooks"
,
'ICON_FILE'
:
document
.
getElementById
(
'type-icon'
),
// file input node
"IS_CONFIGURABLE_TYPE"
:
"N"
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
'crm.activity.type.add'
,
[
'fields'
=> [
'TYPE_ID'
=>
'QuickBooks and other similar platforms'
,
'NAME'
=>
'Activity for QuickBooks'
,
'ICON_FILE'
=>
$_FILES
[
'type-icon'
], // file input node
'IS_CONFIGURABLE_TYPE'
=>
'N'
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
'Error adding activity type: '
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
"crm.activity.type.add"
,
{
fields
:
{
"TYPE_ID"
:
'QuickBooks and other similar platforms'
,
"NAME"
:
"Activity for QuickBooks"
,
'ICON_FILE'
:
document
.
getElementById
(
'type-icon'
),
// file input node
"IS_CONFIGURABLE_TYPE"
:
"N"
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
After this, it is sufficient to specify your type when creating an activity, and the icon and name will be loaded automatically.
BX24
.
callMethod
(
'crm.activity.add'
,
{
fields
:
{
"OWNER_TYPE_ID"
:
1
,
"OWNER_ID"
: selectedEntityId,
"PROVIDER_ID"
:
'REST_APP'
,
"PROVIDER_TYPE_ID"
:
'QuickBooks and other similar platforms'
,
"SUBJECT"
:
"New Activity"
,
"COMPLETED"
:
"N"
,
"RESPONSIBLE_ID"
:
1
,
"DESCRIPTION"
:
"Description of the new activity"
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
'crm.activity.type.add'
,
[
'fields'
=> [
'TYPE_ID'
=>
'QuickBooks and other similar platforms'
,
'NAME'
=>
'Activity for QuickBooks'
,
'ICON_FILE'
=>
$_FILES
[
'type-icon'
], // Assuming file input is handled
'IS_CONFIGURABLE_TYPE'
=>
'N'
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
After this, it is sufficient to specify your type when creating an activity, and the icon and name will be loaded automatically.
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
'crm.activity.add'
,
[
'fields'
=> [
'OWNER_TYPE_ID'
=>
1
,
'OWNER_ID'
=>
$selectedEntityId
, // Assuming this variable is defined
'PROVIDER_ID'
=>
'REST_APP'
,
'PROVIDER_TYPE_ID'
=>
'QuickBooks and other similar platforms'
,
'SUBJECT'
=>
'New Activity'
,
'COMPLETED'
=>
'N'
,
'RESPONSIBLE_ID'
=>
1
,
'DESCRIPTION'
=>
'Description of the new activity'
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
— in case of success
false
— in case of failure (an error occurred)
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
Access denied! Application context required
The method works only in the context of applications
INVALID_ARG_VALUE
The required field
TYPE_ID
is not filled
INVALID_ARG_VALUE
A custom activity type with the specified
TYPE_ID
already exists
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
Get a list of custom activity types crm.activity.type.list
Delete Custom Activity Type crm.activity.type.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get List of Custom Types

---

## Get a list of custom activity types crm.activity.type.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/types/crm-activity-type-list

Get a list of custom activity types crm.activity.type.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of custom activity types crm.activity.type.list
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
Who can execute the method:
any user
The method
crm.activity.type.list
retrieves a list of custom activity types registered by the application.
Method Parameters
Method Parameters
No parameters
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
https://**put_your_bitrix24_address**/rest/crm.activity.type.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.activity.type.list'
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in chunks and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.activity.type.list'
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.type.list'
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
'crm.activity.type.list'
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
'Error fetching activity types: '
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
"crm.activity.type.list"
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
'crm.activity.type.list'
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
[
{
"TYPE_ID"
:
"QuickBooks and other similar platforms"
,
"NAME"
:
"Activity QuickBooks"
,
"IS_CONFIGURABLE_TYPE"
:
"Y"
,
"ICON_ID"
:
"0"
}
]
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
The root element of the response containing an array of objects with information about custom activity types registered by the application
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
Access denied! Application context required
The method works only in the context of applications
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
Add Custom Activity Type crm.activity.type.add
Delete Custom Activity Type crm.activity.type.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Custom Type
Next
Delete Custom Type

---

## Delete Custom Activity Type crm.activity.type.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/types/crm-activity-type-delete

Delete Custom Activity Type crm.activity.type.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Custom Activity Type crm.activity.type.delete
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
Who can execute the method:
any user
The method
crm.activity.type.delete
removes a custom activity type.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
TYPE_ID
*
string
String value of the activity type, for example
QuickBooks and other similar platforms
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
'{"TYPE_ID":"QuickBooks and other similar platforms","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.type.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.type.delete'
,
{
'TYPE_ID'
:
'QuickBooks and other similar platforms'
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
'crm.activity.type.delete'
,
[
'TYPE_ID'
=>
'QuickBooks and other similar platforms'
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
'Error deleting activity type: '
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
"crm.activity.type.delete"
,
{
"TYPE_ID"
:
'QuickBooks and other similar platforms'
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
'crm.activity.type.delete'
,
[
'TYPE_ID'
=>
'QuickBooks and other similar platforms'
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
false
— on failure
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
Access denied! Application context required
Method works only in the context of applications
INVALID_ARG_VALUE
Custom activity type with the specified
TYPE_ID
does not exist
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
Get a list of custom activity types crm.activity.type.list
Add Custom Activity Type crm.activity.type.add
Copied
Was the article helpful?
Yes
No
Previous
Get List of Custom Types
Next
Overview of Methods

---

## Additional Content Blocks

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/layout-blocks/index

Additional Content Blocks | Bitrix24 REST API and Marketplace Applications
Additional Content Blocks
Additional Content Blocks
Activity Linked to Multiple Entities
Restoring Activities from Trash
Deleting the Application
See Also
Methods for working with additional content blocks in an activity:
Method
Description
crm.activity.layout.blocks.set
Sets a collection of additional content blocks in an activity
crm.activity.layout.blocks.get
Retrieves the set of additional content blocks established by the application in the activity
crm.activity.layout.blocks.delete
Deletes the set of additional content blocks established by the application for the activity
Activity Linked to Multiple Entities
Activity Linked to Multiple Entities
Adding sets of additional content blocks to an activity linked to multiple entities will result in the sets of additional content blocks being rendered in each of the activities within the timeline.
Restoring Activities from Trash
Restoring Activities from Trash
When restoring activities from the trash, the sets of additional content blocks added by applications will also be restored.
Deleting the Application
Deleting the Application
When the application is deleted, all sets of additional content blocks added to activities by it will be permanently removed.
See Also
See Also
Example Test Application
Methods for Working with Sets of Additional Content Blocks in the Timeline
Was the article helpful?
Yes
No
Previous
Delete Custom Type
Next
Install a Set of Additional Content Blocks

---

## Set a set of additional content blocks in the activity crm.activity.layout.blocks.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/layout-blocks/crm-activity-layout-blocks-set

Set a set of additional content blocks in the activity crm.activity.layout.blocks.set | Bitrix24 REST API and Marketplace Applications
Set a set of additional content blocks in the activity crm.activity.layout.blocks.set
Set a set of additional content blocks in the activity crm.activity.layout.blocks.set
Method Parameters
Code Examples
Appearance
Response Handling
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: administrator
The method
crm.activity.layout.blocks.set
sets a set of additional content blocks for the activity.
Setting a new set of additional content blocks in the activity will overwrite the previously added set within the same application.
Setting a set of additional content blocks cannot be applied to:
configurable activity
,
a activity whose type is deprecated.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the CRM object type to which the activity is linked
entityId
*
integer
Identifier of the CRM object to which the activity is linked
activityId
*
integer
Identifier of the activity
layout
*
RestAppLayoutDto
Object describing the set of additional content blocks
Code Examples
Code Examples
For the activity with
id = 8
, linked to the activity with
id = 4
, we will set the following set of additional content blocks:
Text
Long multiline text
Link
Block with a title
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
'{"entityTypeId":2,"entityId":4,"activityId":8,"layout":{"blocks":{"block_1":{"type":"text","properties":{"value":"Hello!\nWe are starting.","multiline":true,"bold":true,"color":"base_90"}},"block_2":{"type":"largeText","properties":{"value":"Hello!\nWe are starting.\nWe are continuing.\nWe are still working on this.\nWe are continuing.\nWe are close to the result.\nGoodbye."}},"block_3":{"type":"link","properties":{"text":"Open deal","bold":true,"action":{"type":"redirect","uri":"/crm/deal/details/123/"}}},"block_4":{"type":"withTitle","properties":{"title":"Title","block":{"type":"text","properties":{"value":"Some value"}}}}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.layout.blocks.set
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"entityId":4,"activityId":8,"layout":{"blocks":{"block_1":{"type":"text","properties":{"value":"Hello!\nWe are starting.","multiline":true,"bold":true,"color":"base_90"}},"block_2":{"type":"largeText","properties":{"value":"Hello!\nWe are starting.\nWe are continuing.\nWe are still working on this.\nWe are continuing.\nWe are close to the result.\nGoodbye."}},"block_3":{"type":"link","properties":{"text":"Open deal","bold":true,"action":{"type":"redirect","uri":"/crm/deal/details/123/"}}},"block_4":{"type":"withTitle","properties":{"title":"Title","block":{"type":"text","properties":{"value":"Some value"}}}}}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.layout.blocks.set
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.layout.blocks.set'
,
{
entityTypeId
:
2
,
// Deal
entityId
:
4
,
// Deal ID
activityId
:
8
,
// ID of the deal linked to this deal
layout
: layout,
// Object describing the set of additional content blocks
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
'crm.activity.layout.blocks.set'
,
[
'entityTypeId'
=>
2
, // Deal
'entityId'
=>
4
, // Deal ID
'activityId'
=>
8
, // ID of the deal linked to this deal
'layout'
=> [
'blocks'
=> [
'block_1'
=> [
'type'
=>
"text"
,
'properties'
=> [
'value'
=>
"Hello!\nWe are starting."
,
'multiline'
=>
true
,
'bold'
=>
true
,
'color'
=>
"base_90"
,
],
],
'block_2'
=> [
'type'
=>
"largeText"
,
'properties'
=> [
'value'
=>
"Hello!\nWe are starting.\nWe are continuing.\nWe are still working on this.\nWe are continuing.\nWe are close to the result.\nGoodbye."
,
],
],
'block_3'
=> [
'type'
=>
"link"
,
'properties'
=> [
'text'
=>
"Open deal"
,
'bold'
=>
true
,
'action'
=> [
'type'
=>
"redirect"
,
'uri'
=>
"/crm/deal/details/123/"
,
],
],
],
'block_4'
=> [
'type'
=>
"withTitle"
,
'properties'
=> [
'title'
=>
"Title"
,
'block'
=> [
'type'
=>
"text"
,
'properties'
=> [
'value'
=>
"Some value"
,
],
],
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
'Error setting activity layout blocks: '
.
$e
->
getMessage
();
}
const
layout = {
blocks
: {
'block_1'
: {
type
:
"text"
,
properties
: {
value
:
"Hello!\nWe are starting."
,
multiline
:
true
,
bold
:
true
,
color
:
"base_90"
}
},
'block_2'
: {
type
:
"largeText"
,
properties
: {
value
:
"Hello!\nWe are starting.\nWe are continuing.\nWe are still working on this.\nWe are continuing.\nWe are close to the result.\nGoodbye."
}
},
'block_3'
: {
type
:
"link"
,
properties
: {
text
:
"Open deal"
,
bold
:
true
,
action
: {
type
:
"redirect"
,
uri
:
"/crm/deal/details/123/"
}
}
},
'block_4'
: {
type
:
"withTitle"
,
properties
: {
title
:
"Title"
,
block
: {
type
:
"text"
,
properties
: {
value
:
"Some value"
}
}
}
}
}
};
BX24
.
callMethod
(
'crm.activity.layout.blocks.set'
,
{
entityTypeId
:
2
,
// Deal
entityId
:
4
,
// Deal ID
activityId
:
8
,
// ID of the activity linked to this deal
layout
: layout,
// Object describing the set of additional content blocks
},
(
result
) =>
{
if
(result.
error
()) {
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
'crm.activity.layout.blocks.set'
,
[
'entityTypeId'
=>
2
,
'entityId'
=>
4
,
'activityId'
=>
8
,
'layout'
=> [
'blocks'
=> [
'block_1'
=> [
'type'
=>
"text"
,
'properties'
=> [
'value'
=>
"Hello!\nWe are starting."
,
'multiline'
=>
true
,
'bold'
=>
true
,
'color'
=>
"base_90"
]
],
'block_2'
=> [
'type'
=>
"largeText"
,
'properties'
=> [
'value'
=>
"Hello!\nWe are starting.\nWe are continuing.\nWe are still working on this.\nWe are continuing.\nWe are close to the result.\nGoodbye."
]
],
'block_3'
=> [
'type'
=>
"link"
,
'properties'
=> [
'text'
=>
"Open deal"
,
'bold'
=>
true
,
'action'
=> [
'type'
=>
"redirect"
,
'uri'
=>
"/crm/deal/details/123/"
]
]
],
'block_4'
=> [
'type'
=>
"withTitle"
,
'properties'
=> [
'title'
=>
"Title"
,
'block'
=> [
'type'
=>
"text"
,
'properties'
=> [
'value'
=>
"Some value"
]
]
]
]
]
]
]
);
echo
''
;
print_r
(
$result
);
echo
''
;
Appearance
Appearance
If the activity contains more than one set of additional content blocks, they will be displayed in the order they were added.
In the HTML layout, it is explicitly highlighted with data attributes which application added the set of additional content blocks:
data-app-name
: name of the application,
data-rest-client-id
: identifier of the application.
Response Handling
Response Handling
HTTP status:
200
Returns
{ success: true }
in case of successful writing of the set of additional content blocks, otherwise
null
.
{
"success"
:
true
}
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
"ERROR_WRONG_CONTEXT"
,
"error_description"
:
"The method call is only possible in the context of a REST application"
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
ERROR_WRONG_CONTEXT
The method can only be called in the context of a REST application
OWNER_NOT_FOUND
The element to which the activity is linked was not found
NOT_FOUND
The activity was not found
ACCESS_DENIED
Access denied
UNSUITABLE_ACTIVITY_TYPE_ERROR
The type of this activity is not suitable for adding a set of additional content blocks
FIELD_IS_REQUIRED
The
blocks
field in
RestAppLayoutDto
must be filled.
The method also returns errors related to the incorrect structure of the set of content blocks. Details can be found in the error message.
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
Additional Content Blocks
Get a Set of Additional Content Blocks in the activity crm.activity.layout.blocks.get
Delete a set of additional content blocks in the CRM activity crm.activity.layout.blocks.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Retrieve a Set of Additional Content Blocks

---

## Get a Set of Additional Content Blocks in the activity crm.activity.layout.blocks.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/layout-blocks/crm-activity-layout-blocks-get

Get a Set of Additional Content Blocks in the activity crm.activity.layout.blocks.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a Set of Additional Content Blocks in the activity crm.activity.layout.blocks.get
Method Parameters
Code Examples
Response Handling
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: administrator
The method
crm.activity.layout.blocks.get
retrieves a set of additional content blocks for a activity.
Within the application, you can only obtain the set of additional content blocks that has been installed through this application.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the CRM object type to which the activity is linked
entityId
*
integer
Identifier of the CRM object to which the activity is linked
activityId
*
integer
Identifier of the activity
Code Examples
Code Examples
Get a set of additional content blocks in the activity with
id = 8
, linked to the deal with
id = 4
:
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
'{"entityTypeId":2,"entityId":4,"activityId":8}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.layout.blocks.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"entityId":4,"activityId":8,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.layout.blocks.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.layout.blocks.get'
,
{
entityTypeId
:
2
,
entityId
:
4
,
activityId
:
8
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
'crm.activity.layout.blocks.get'
,
[
'entityTypeId'
=>
2
,
'entityId'
=>
4
,
'activityId'
=>
8
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
'Error getting activity layout blocks: '
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
'crm.activity.layout.blocks.get'
,
{
entityTypeId
:
2
,
entityId
:
4
,
activityId
:
8
,
},
(
result
) =>
{
if
(result.
error
()) {
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
'crm.activity.layout.blocks.get'
,
[
'entityTypeId'
=>
2
,
'entityId'
=>
4
,
'activityId'
=>
8
]
);
echo
''
;
print_r
(
$result
);
echo
''
;
Response Handling
Response Handling
HTTP status:
200
Returns an
object
with the key
layout
, containing
RestAppLayoutDto
.
{
"layout"
:
{
"blocks"
:
{
"block_1"
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
"Hello!\nWe are starting."
,
"multiline"
:
true
,
"bold"
:
true
,
"color"
:
"base_90"
}
}
,
"block_2"
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
"Hello!\nWe are starting.\nWe are continuing.\nWe are still working on this.\nWe are continuing.\nWe are close to the result.\nGoodbye."
}
}
,
"block_3"
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
"Open deal"
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
"/crm/deal/details/123/"
}
}
}
,
"block_4"
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
}
}
}
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
"ERROR_WRONG_CONTEXT"
,
"error_description"
:
"The method can only be called in the context of a rest application"
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
ERROR_WRONG_CONTEXT
The method can only be called in the context of a rest application
OWNER_NOT_FOUND
The element to which the activity is linked was not found
NOT_FOUND
The activity was not found
ACCESS_DENIED
Access denied
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
Additional Content Blocks
Set a set of additional content blocks in the activity crm.activity.layout.blocks.set
Delete a set of additional content blocks in the CRM activity crm.activity.layout.blocks.delete
Copied
Was the article helpful?
Yes
No
Previous
Install a Set of Additional Content Blocks
Next
Delete a Set of Additional Content Blocks

---

## Delete a set of additional content blocks in the CRM activity crm.activity.layout.blocks.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/layout-blocks/crm-activity-layout-blocks-delete

Delete a set of additional content blocks in the CRM activity crm.activity.layout.blocks.delete | Bitrix24 REST API and Marketplace Applications
Delete a set of additional content blocks in the CRM activity crm.activity.layout.blocks.delete
Delete a set of additional content blocks in the CRM activity crm.activity.layout.blocks.delete
Method Parameters
Code Examples
Response Handling
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: administrator
The method
crm.activity.layout.blocks.delete
removes a set of additional content blocks for a activity.
Within the application, only the set of additional content blocks that was installed through this application can be deleted.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the CRM object type to which the activity is linked
entityId
*
integer
Identifier of the CRM object to which the activity is linked
activityId
*
integer
Identifier of the activity
Code Examples
Code Examples
Delete a set of additional content blocks in the activity with
id = 8
, linked to the deal with
id = 4
:
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
'{"entityTypeId":2,"entityId":4,"activityId":8}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.activity.layout.blocks.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"entityId":4,"activityId":8,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.activity.layout.blocks.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.activity.layout.blocks.delete'
,
{
entityTypeId
:
2
,
// Deal
entityId
:
4
,
// Deal ID
activityId
:
8
,
// ID of the deal linked to this deal
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
'crm.activity.layout.blocks.delete'
,
[
'entityTypeId'
=>
2
, // Deal
'entityId'
=>
4
, // Deal ID
'activityId'
=>
8
, // ID of the deal linked to this deal
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
'Error deleting activity layout block: '
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
'crm.activity.layout.blocks.delete'
,
{
entityTypeId
:
2
,
// Deal
entityId
:
4
,
// Deal ID
activityId
:
8
,
// ID of the activity linked to this deal
},
(
result
) =>
{
if
(result.
error
()) {
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
'crm.activity.layout.blocks.delete'
,
[
'entityTypeId'
=>
2
,
'entityId'
=>
4
,
'activityId'
=>
8
]
);
echo
''
;
print_r
(
$result
);
echo
''
;
Response Handling
Response Handling
HTTP status:
200
Returns
{ success: true }
if the set of additional content blocks is successfully deleted, otherwise
null
.
{
"success"
:
true
}
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
"ERROR_WRONG_CONTEXT"
,
"error_description"
:
"The method can only be called in the context of a REST application"
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
ERROR_WRONG_CONTEXT
The method can only be called in the context of a REST application
OWNER_NOT_FOUND
The element to which the activity is linked was not found
NOT_FOUND
The activity was not found
ACCESS_DENIED
Access denied
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
Additional Content Blocks
Set a set of additional content blocks in the activity crm.activity.layout.blocks.set
Get a Set of Additional Content Blocks in the activity crm.activity.layout.blocks.get
Copied
Was the article helpful?
Yes
No
Previous
Retrieve a Set of Additional Content Blocks
Next
Overview of Events

---

## Overview of Events

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/events/index

Overview of Events | Bitrix24 REST API and Marketplace Applications
Overview of Events
Overview of Events
Scope:
crm
Who can subscribe:
any user
A list of events when working with an activity in the timeline.
Event
Triggered by
onCrmActivityAdd
When a new activity is created
onCrmActivityUpdate
When a activity is updated
onCrmActivityDelete
When a activity is deleted
Copied
Was the article helpful?
Yes
No
Previous
Delete a Set of Additional Content Blocks
Next
When Creating a New Activity

---

## Event for Creating a New Deal onCrmActivityAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/events/on-crm-activity-add

Event for Creating a New Deal onCrmActivityAdd | Bitrix24 REST API and Marketplace Applications
Event for Creating a New Deal onCrmActivityAdd
Event for Creating a New Deal onCrmActivityAdd
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Exploring
Scope:
crm
Who can subscribe:
any user
The
onCrmActivityAdd
event is triggered when a new deal is added to the CRM timeline.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
{
"event"
:
"onCrmActivityAdd"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"999"
}
}
,
"ts"
:
"1466439714"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"L"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic code of the event. In our case, it is
onCrmActivityAdd
data
array
An object containing information about the created deal.
Contains a single key
FIELDS
ts
timestamp
Date and time of the event sent from the
event queue
auth
array
Authorization parameters and information about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
integer
ID
with the value of the added deal's identifier
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
domain
*
string
Address of Bitrix24 where the event occurred
server_endpoint
*
string
Address of the Bitrix24 authorization server needed to refresh OAuth 2.0 tokens
status
*
string
Status of the application that subscribed to this event:
L
—
local
application
F
—
free mass-market
application
client_endpoint
*
string
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue Exploring
Continue Exploring
Event Handler
Register a new event handler event.bind
Event onCrmActivityUpdate
Event onCrmActivityDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Updating an Activity

---

## Event onCrmActivityUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/events/on-crm-activity-update

Event onCrmActivityUpdate | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmActivityUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe:
any user
The
onCrmActivityUpdate
event is triggered when an activity is updated in the CRM timeline.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"onCrmActivityUpdate"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"999"
}
}
,
"ts"
:
"1466439714"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"L"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic code of the event. In our case, it is
onCrmActivityUpdate
data
array
An object containing information about the updated activity.
Contains a single key
FIELDS
ts
timestamp
Date and time the event was sent from the
event queue
auth
array
Authorization parameters and information about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
integer
ID
with the value of the updated activity identifier
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
domain
*
string
Address of Bitrix24 where the event occurred
server_endpoint
*
string
Address of the Bitrix24 authorization server needed to refresh OAuth 2.0 tokens
status
*
string
Status of the application that subscribed to this event:
L
—
local
application
F
—
free mass-market
application
client_endpoint
*
string
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event for Creating a New Deal onCrmActivityAdd
Event onCrmActivityDelete
Copied
Was the article helpful?
Yes
No
Previous
When Creating a New Activity
Next
When Deleting an Activity

---

## Event onCrmActivityDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/events/on-crm-activity-delete

Event onCrmActivityDelete | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmActivityDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe:
any user
The
onCrmActivityDelete
event is triggered when a deal is deleted in the CRM timeline.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"onCrmActivityDelete"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"999"
}
}
,
"ts"
:
"1466439714"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"L"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic code of the event. In our case, it is
onCrmActivityDelete
data
array
An object containing information about the deleted deal.
Contains a single key
FIELDS
ts
timestamp
Date and time the event was sent from the
event queue
auth
array
Authorization parameters and information about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
integer
ID
with the value of the deleted deal's identifier
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
domain
*
string
Address of Bitrix24 where the event occurred
server_endpoint
*
string
Address of the Bitrix24 authorization server needed to refresh OAuth 2.0 tokens
status
*
string
Status of the application that subscribed to this event:
L
—
local
application
F
—
free mass-market
application
client_endpoint
*
string
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event for Creating a New Deal onCrmActivityAdd
Event onCrmActivityUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Updating an Activity
Next
Embedding Applications

---

## Embedding Applications

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/app-embedding/index

Embedding Applications | Bitrix24 REST API and Marketplace Applications
Embedding Locations
Embedding Applications
Embedding Locations
See Also
External applications can add their elements to the activity interface.
See also the section
Embedding Applications
.
Embedding Locations
Embedding Locations
Code
Description
CRM_ACTIVITY_LIST_MENU
Context menu item for activities
See Also
See Also
Context menu item in the list of entities
Example of creating an activity from applications
Was the article helpful?
Yes
No
Previous
When Deleting an Activity
Next
How to Create an Activity from an Application

---

## How to create an activity from an application

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/activities/app-embedding/activity-app

How to create an activity from an application | Bitrix24 REST API and Marketplace Applications
How to create an activity from an application
How to create an activity from an application
Parameters
Example application
Applications can create activities with a special type provider. Such an activity will have a corresponding
icon
in the timeline. Clicking on the activity will open the application in a slider with options in
PLACEMENT_OPTIONS
Warning
Activities with a special type provider can only be modified/deleted in the context of the application that created the activity. When updating such an activity using the
crm.activity.update
method via webhook, an error will occur:
Access denied! Application context required
.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
PROVIDER_ID
*
string
Provider identifier. For special type, the value must be
REST_APP
PROVIDER_TYPE_ID
*
string
Activity type identifier. When using the
REST_APP
provider, the developer can specify arbitrary type identifiers depending on their tasks
Example application
Example application
How to Use Examples in Documentation
PHP
<?php
header
(
'Content-Type: text/html; charset=UTF-8'
);
?>
<!DOCTYPE html>
<html>
<head>
<meta charset=
"UTF-8"
>
<title></title>
<style type=
"text/css"
>
</style>
</head>
<body style=
"display: none"
>
<script src=
"//api.bitrix24.com/api/v1/"
></script>
<?
if
(
isset
(
$_POST
[
'PLACEMENT'
]) && !
empty
(
$_POST
[
'PLACEMENT_OPTIONS'
])):
$opt
=
json_decode
(
$_POST
[
'PLACEMENT_OPTIONS'
],
true
);
?>
<p>Activity ID:
<?=
(
int
)
$opt
[
'activity_id'
]
?>
</p>
<button onclick=
"updateActivity(<?= (int)
$opt
['activity_id']?>);"
>Update
activity
(set
new
description + completed)</button>
<p><button onclick=
"deleteActivity(<?= (int)
$opt
['activity_id']?>);"
>Delete activity</button>
<?
else
:
?>
<button onclick=
"selectCRMEntity();"
>Select LEAD</button>
<span id=
"selected-entity"
></span>
<p>
<button onclick=
"addActivity();"
>Add activity</button>
<?
endif
;
?>
<script type=
"text/javascript"
>
BX24.
init
(function()
{
document.body.style.display =
''
;
});
var
selectedEntityId =
null
;
function
addActivity
(
)
{
if
(!selectedEntityId)
{
alert
(
'Lead not selected'
);
return
;
}
BX24.
callMethod
(
'crm.activity.add'
,
{
fields
:
{
"OWNER_TYPE_ID"
:
1
,
"OWNER_ID"
: selectedEntityId,
"PROVIDER_ID"
:
'REST_APP'
,
"PROVIDER_TYPE_ID"
:
'LINK'
,
"SUBJECT"
:
"New activity"
,
"COMPLETED"
:
"N"
,
"RESPONSIBLE_ID"
:
1
,
"DESCRIPTION"
:
"Description of the new activity"
}
},
function(result)
{
if
(result.
error
())
alert
(
"Error: "
+ result.
error
());
else
{
alert
(
"Success: "
+ result.
data
());
}
}
);
}
function
updateActivity
(
id
)
{
BX24.
callMethod
(
'crm.activity.update'
,
{
id
: id,
fields
:
{
COMPLETED
:
'Y'
,
SUBJECT
:
"Activity completed!"
,
DESCRIPTION
:
"Description of the new activity (completed)"
}
},
function(result)
{
if
(result.
error
())
alert
(
"Error: "
+ result.
error
());
else
{
alert
(
"Success: "
+ result.
data
());
}
}
);
}
function
deleteActivity
(
id
)
{
BX24.
callMethod
(
'crm.activity.delete'
,
{
id
: id
},
function(result)
{
if
(result.
error
())
alert
(
"Error: "
+ result.
error
());
else
{
alert
(
"Success: "
+ result.
data
());
}
}
);
}
function
selectCRMEntity
(
)
{
document.
getElementById
(
'selected-entity'
).textContent =
''
;
BX24.
selectCRM
({
entityType
: [
'lead'
]
}, function(selected)
{
if
(selected[
'lead'
] && selected[
'lead'
][
0
])
{
document.
getElementById
(
'selected-entity'
).textContent = selected[
'lead'
][
0
][
'title'
];
var
id = selected[
'lead'
][
0
][
'id'
];
selectedEntityId = id.
substring
(
2
);
console.
log
(selectedEntityId);
}
})
}
</script>
</body>
</html>
Copied
Was the article helpful?
Yes
No
Previous
Embedding Applications
Next
Overview of Methods

---

