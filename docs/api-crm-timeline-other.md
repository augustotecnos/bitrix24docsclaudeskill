---
description: 'CRM Timeline: Comments, notes, bindings, layout blocks, actions'
methods:
- crm.activity.layout.blocks.
- crm.activity.layout.blocks.delete
- crm.activity.layout.blocks.get
- crm.activity.layout.blocks.set
- crm.activity.list
- crm.item.add
- crm.item.list
- crm.timeline.bindings.
- crm.timeline.bindings.bind
- crm.timeline.bindings.fields
- crm.timeline.bindings.list
- crm.timeline.bindings.unbind
- crm.timeline.comment.
- crm.timeline.comment.add
- crm.timeline.comment.delete
- crm.timeline.comment.fields
- crm.timeline.comment.get
- crm.timeline.comment.list
- crm.timeline.comment.update
- crm.timeline.historyitem.list
- crm.timeline.icon.
- crm.timeline.item.pin
- crm.timeline.item.unpin
- crm.timeline.layout.blocks.
- crm.timeline.layout.blocks.delete
- crm.timeline.layout.blocks.get
- crm.timeline.layout.blocks.set
- crm.timeline.logmessage.
- crm.timeline.logmessage.add
- crm.timeline.logmessage.delete
pages: 29
title: 'CRM Timeline: Comments, notes, bindings, layout blocks, actions'
---
# CRM Timeline: Comments, notes, bindings, layout blocks, actions
> CRM Timeline: Comments, notes, bindings, layout blocks, actions
> **29 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Timeline and Activities in CRM: Overview of Methods](#timeline-and-activities-in-crm-overview-of-methods)
- [Overview of Methods](#overview-of-methods)
- [Get Information About the Note crm.timeline.note.get](#get-information-about-the-note-crmtimelinenoteget)
- [Save Note crm.timeline.note.save](#save-note-crmtimelinenotesave)
- [Delete Note crm.timeline.note.delete](#delete-note-crmtimelinenotedelete)
- [Overview of Methods](#overview-of-methods)
- [Add Timeline Record Binding to CRM Entity crm.timeline.bindings.bind](#add-timeline-record-binding-to-crm-entity-crmtimel)
- [Get the list of bindings for a record in the timeline crm.timeline.bindings.list](#get-the-list-of-bindings-for-a-record-in-the-timel)
- [Unbind Timeline Record from CRM Entity crm.timeline.bindings.unbind](#unbind-timeline-record-from-crm-entity-crmtimeline)
- [Get CRM entity bindings fields and timeline record in crm.timeline.bindings.fields](#get-crm-entity-bindings-fields-and-timeline-record)
- [Overview of Methods](#overview-of-methods)
- [Add Comment crm.timeline.comment.add](#add-comment-crmtimelinecommentadd)
- [Update Comment crm.timeline.comment.update](#update-comment-crmtimelinecommentupdate)
- [Get Information About the Comment crm.timeline.comment.get](#get-information-about-the-comment-crmtimelinecomme)
- [Get a List of Comments crm.timeline.comment.list](#get-a-list-of-comments-crmtimelinecommentlist)
- [Delete Comment crm.timeline.comment.delete](#delete-comment-crmtimelinecommentdelete)
- [Get CRM Timeline Comment Fields](#get-crm-timeline-comment-fields)
- [Overview of Events](#overview-of-events)
- [Event for Creating a New Deal Type "Comment" onCrmTimelineCommentAdd](#event-for-creating-a-new-deal-type-comment-oncrmti)
- [Event on deal update of type "Comment" onCrmTimelineCommentUpdate](#event-on-deal-update-of-type-comment-oncrmtimeline)
- [Event for Deleting a "Comment" Activity onCrmTimelineCommentDelete](#event-for-deleting-a-comment-activity-oncrmtimelin)
- [Additional Content Blocks](#additional-content-blocks)
- [Set a set of additional content blocks in the timeline record crm.timeline.layout.blocks.set](#set-a-set-of-additional-content-blocks-in-the-time)
- [Get a set of additional content blocks for the timeline record crm.timeline.layout.blocks.get](#get-a-set-of-additional-content-blocks-for-the-tim)
- [Delete a set of additional content blocks for the timeline record crm.timeline.layout.blocks.delete](#delete-a-set-of-additional-content-blocks-for-the-)
- [Example Application with Additional Content Blocks](#example-application-with-additional-content-blocks)
- [Actions with Records in the Timeline: Overview of Methods](#actions-with-records-in-the-timeline-overview-of-m)
- [Pinning an Item in the Timeline crm.timeline.item.pin](#pinning-an-item-in-the-timeline-crmtimelineitempin)
- [Unpin Timeline Item in crm.timeline.item.unpin](#unpin-timeline-item-in-crmtimelineitemunpin)

---

## Timeline and Activities in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/index

Timeline and Activities in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Timeline and Activities in CRM: Overview of Methods
Timeline and Activities in CRM: Overview of Methods
Activities
Timeline
Widgets
Additional Features
Overview of Methods and Events
Timeline Comments
Notes for Timeline Entries
Managing Timeline Entry Relationships
Additional Content Blocks
Application Log Entry Journal
Actions with Timeline Entries
The timeline is the primary workspace in the CRM entity detail form. It records:
system information about working with the entity: stage changes, payments, creating entities based on the current one
user information: CRM activities (tasks, e-mails, calls) and timeline entries (comments, documents generated from templates, application log entries)
Quick navigation:
all methods and events
User documentation:
timeline in Bitrix24
,
universal activity in Bitrix24
Activities
Activities
Activities in CRM are divided into incoming and scheduled:
Incoming — activities received from the client, such as an e-mail or a call. For these activities, it is important to correctly specify the parameter
DIRECTION
=
1
so that the incoming CRM activities counter works
Scheduled — activities created by employees, such as tasks or universal activities
More details about activities and methods for managing them can be found in the article
Activities in CRM: Overview of Methods
.
Timeline
Timeline
Timeline entries are divided into two types:
Comments. You can add, delete, modify, and retrieve comments through the group of methods
crm.timeline.comment.*
Log entries. You can add, delete, modify, and retrieve log entries through the group of methods
crm.timeline.logmessage.*
You can manage the relationships of timeline entries with CRM entities using the methods from the group
crm.timeline.bindings.*
Widgets
Widgets
You can embed an application into activities and timeline entries. Thanks to the embedding, you can use the application without leaving the CRM entity detail form. For embedding, there are special places in the timeline:
Button above the timeline of the entity detail form
CRM_XXX_DETAIL_ACTIVITY
,
CRM_DYNAMIC_XXX_DETAIL_ACTIVITY
Context menu item of the activity in the entity detail form
CRM_XXX_ACTIVITY_TIMELINE_MENU
Typical use-cases and scenarios
Widget embedding mechanism
Create activities from applications
Additional Features
Additional Features
Text notes
can be added to activities and timeline comments and deleted. Use the group of methods
crm.timeline.note.*
.
Content blocks
can be added to timeline comments and deleted. Use the group of methods
crm.timeline.layout.blocks.*
.
Available content blocks
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can perform methods: depending on the method
Timeline Comments
Timeline Comments
Methods
Events
Method
Description
crm.timeline.comment.add
Adds a new comment to the timeline
crm.timeline.comment.update
Updates a comment
crm.timeline.comment.get
Retrieves information about a comment
crm.timeline.comment.list
Retrieves a list of all comments for the CRM entity
crm.timeline.comment.delete
Deletes a comment
crm.timeline.comment.fields
Retrieves a list of timeline comment fields
Event
Triggered
onCrmTimelineCommentAdd
When a new comment is created in the timeline
onCrmTimelineCommentUpdate
When a comment is updated in the timeline
onCrmTimelineCommentDelete
When a comment is deleted in the timeline
Notes for Timeline Entries
Notes for Timeline Entries
Method
Description
crm.timeline.note.get
Retrieves information about a note
crm.timeline.note.save
Saves a note
crm.timeline.note.delete
Deletes a note
Managing Timeline Entry Relationships
Managing Timeline Entry Relationships
Method
Description
crm.timeline.bindings.bind
Adds a relationship between a timeline entry and a CRM entity
crm.timeline.bindings.list
Retrieves a list of relationships for a timeline entry
crm.timeline.bindings.unbind
Removes the relationship between a timeline entry and a CRM entity
crm.timeline.bindings.fields
Retrieves the fields of the relationship between CRM entities and timeline entries
Additional Content Blocks
Additional Content Blocks
Method
Description
crm.timeline.layout.blocks.set
Sets a set of additional content blocks in the timeline entry
crm.timeline.layout.blocks.get
Retrieves the set of additional content blocks installed by the application for the timeline entry
crm.timeline.layout.blocks.delete
Deletes the set of additional content blocks installed by the application for the timeline entry
Application Log Entry Journal
Application Log Entry Journal
Method
Description
crm.timeline.logmessage.add
Adds a new log entry to the timeline
crm.timeline.logmessage.get
Retrieves information about a log entry
crm.timeline.logmessage.list
Retrieves a list of all log entries for a specific entity
crm.timeline.logmessage.delete
Deletes a log entry
crm.timeline.icon.*
Manages entry icons
crm.timeline.logo.*
Manages entry logos
Actions with Timeline Entries
Actions with Timeline Entries
Method
Description
crm.timeline.item.pin
Pins an entry in the timeline
crm.timeline.item.unpin
Unpins an entry in the timeline
Copied
Was the article helpful?
Yes
No
Previous
When Deleting Bank Details
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/note/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Additional Information
Overview of Methods
Scope:
crm
Who can execute the method: any user
Method
Description
crm.timeline.note.get
Retrieves information about a note
crm.timeline.note.save
Saves a note
crm.timeline.note.delete
Deletes a note
Additional Information
Additional Information
CRM Entity Type
Copied
Was the article helpful?
Yes
No
Previous
How to Create an Activity from an Application
Next
Get Note Information

---

## Get Information About the Note crm.timeline.note.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/note/crm-timeline-note-get

Get Information About the Note crm.timeline.note.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Information About the Note crm.timeline.note.get
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
The method returns information about a note related to a timeline record.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ownerTypeId
*
integer
Identifier of the element type
to which the record belongs
ownerId
*
integer
Identifier of the element to which the record belongs
itemType
*
integer
Type of the record to which the note should be applied:
1
— history record
2
— activity
itemId
*
integer
Identifier of the record to which the note should be applied. If
itemType=1
, this is the identifier of the timeline history record. If
itemType=2
, this is the identifier of the activity
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
'{"ownerTypeId":1,"ownerId":1,"itemType":1,"itemId":2}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.note.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ownerTypeId":1,"ownerId":1,"itemType":1,"itemId":2,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.note.get
try
{
const
response =
await
$b24.
callMethod
(
"crm.timeline.note.get"
,
{
ownerTypeId
:
1
,
ownerId
:
1
,
itemType
:
1
,
itemId
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
'crm.timeline.note.get'
,
[
'ownerTypeId'
=>
1
,
'ownerId'
=>
1
,
'itemType'
=>
1
,
'itemId'
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
'Error getting timeline note: '
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
"crm.timeline.note.get"
,
{
ownerTypeId
:
1
,
ownerId
:
1
,
itemType
:
1
,
itemId
:
2
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
'crm.timeline.note.get'
,
[
'ownerTypeId'
=>
1
,
'ownerId'
=>
1
,
'itemType'
=>
1
,
'itemId'
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
HTTP Status:
200
{
"result"
:
{
"text"
:
"Test note"
,
"createdById"
:
1
,
"createdTime"
:
"2024-03-17T15:55:10+02:00"
,
"updatedById"
:
1
,
"updatedTime"
:
"2024-03-17T15:55:10+02:00"
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
Information about the found note:
text
— text of the note
createdById
— identifier of the user who created the note
createdTime
— date and time of note creation
updatedById
— identifier of the user who modified the note
updatedTime
— date and time of note modification
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
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Element not found
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Delete Note crm.timeline.note.delete
Save Note crm.timeline.note.save
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Save Note

---

## Save Note crm.timeline.note.save

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/note/crm-timeline-note-save

Save Note crm.timeline.note.save | Bitrix24 REST API and Marketplace Applications
Method Parameters
Save Note crm.timeline.note.save
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
This method allows you to save a note.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ownerTypeId
*
integer
Identifier of the entity type
to which the record belongs
ownerId
*
integer
Identifier of the entity to which the record belongs
itemType
*
integer
Type of the record to which the note should be applied:
1
— history record
2
— activity
itemId
*
integer
Identifier of the record to which the note should be applied. If
itemType=1
, this is the identifier of the timeline history record. If
itemType=2
, this is the identifier of the activity
text
*
string
Note text
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
'{"ownerTypeId":1,"ownerId":1,"itemType":1,"itemId":2,"text":"Test note"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.note.save
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ownerTypeId":1,"ownerId":1,"itemType":1,"itemId":2,"text":"Test note","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.note.save
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.note.save'
,
{
ownerTypeId
:
1
,
ownerId
:
1
,
itemType
:
1
,
itemId
:
2
,
text
:
'Test note'
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
'crm.timeline.note.save'
,
[
'ownerTypeId'
=>
1
,
'ownerId'
=>
1
,
'itemType'
=>
1
,
'itemId'
=>
2
,
'text'
=>
'Test note'
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
'Error saving note: '
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
"crm.timeline.note.save"
,
{
ownerTypeId
:
1
,
ownerId
:
1
,
itemType
:
1
,
itemId
:
2
,
text
:
'Test note'
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
'crm.timeline.note.save'
,
[
'ownerTypeId'
=>
1
,
'ownerId'
=>
1
,
'itemType'
=>
1
,
'itemId'
=>
2
,
'text'
=>
'Test note'
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
Operation result
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
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Element not found
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Delete Note crm.timeline.note.delete
Get Information About the Note crm.timeline.note.get
Copied
Was the article helpful?
Yes
No
Previous
Get Note Information
Next
Delete Note

---

## Delete Note crm.timeline.note.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/note/crm-timeline-note-delete

Delete Note crm.timeline.note.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Note crm.timeline.note.delete
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
This method deletes a timeline note.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ownerTypeId
*
integer
Identifier of the element type
to which the record belongs
ownerId
*
integer
Identifier of the element to which the record belongs
itemType
*
integer
Type of the record to which the note should be applied:
1
— history record
2
— deal
itemId
*
integer
Identifier of the record to which the note should be applied. If
itemType=1
, this is the identifier of the timeline history record. If
itemType=2
, this is the identifier of the deal
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
'{"ownerTypeId":1,"ownerId":1,"itemType":1,"itemId":2}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.note.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ownerTypeId":1,"ownerId":1,"itemType":1,"itemId":2,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.note.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.note.delete'
,
{
ownerTypeId
:
1
,
ownerId
:
1
,
itemType
:
1
,
itemId
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
'crm.timeline.note.delete'
,
[
'ownerTypeId'
=>
1
,
'ownerId'
=>
1
,
'itemType'
=>
1
,
'itemId'
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
'Error deleting timeline note: '
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
"crm.timeline.note.delete"
,
{
ownerTypeId
:
1
,
ownerId
:
1
,
itemType
:
1
,
itemId
:
2
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
'crm.timeline.note.delete'
,
[
'ownerTypeId'
=>
1
,
'ownerId'
=>
1
,
'itemType'
=>
1
,
'itemId'
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
Result of the operation
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
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Element not found
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Get Information About the Note crm.timeline.note.get
Save Note crm.timeline.note.save
Copied
Was the article helpful?
Yes
No
Previous
Save Note
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/bindings/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: any user
Method
Description
crm.timeline.bindings.bind
Adds a link between a timeline record and a CRM entity
crm.timeline.bindings.list
Retrieves a list of links for a timeline record
crm.timeline.bindings.unbind
Removes a link between a timeline record and a CRM entity
crm.timeline.bindings.fields
Retrieves the fields of the link between CRM entities and the timeline record
Copied
Was the article helpful?
Yes
No
Previous
Delete Note
Next
Add Timeline Record Relationship with CRM Entity

---

## Add Timeline Record Binding to CRM Entity crm.timeline.bindings.bind

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/bindings/crm-timeline-bindings-bind

Add Timeline Record Binding to CRM Entity crm.timeline.bindings.bind | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Timeline Record Binding to CRM Entity crm.timeline.bindings.bind
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
This method adds a binding of a timeline record to a CRM entity.
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
) for adding a binding of a timeline record to a CRM entity in the form of a structure:
fields
: {
"OWNER_ID"
:
"value"
,
"ENTITY_ID"
:
"value"
,
"ENTITY_TYPE"
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
OWNER_ID
*
integer
Identifier of the timeline record
ENTITY_ID
*
integer
Identifier
ID
of the CRM entity to which the comment is linked
ENTITY_TYPE
*
string
Type of the entity to which the comment is linked. Possible values:
lead
— lead
deal
— deal
contact
— contact
company
— company
order
— order
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
'{"fields":{"OWNER_ID":1110,"ENTITY_ID":10,"ENTITY_TYPE":"deal"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.bindings.bind
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"OWNER_ID":1110,"ENTITY_ID":10,"ENTITY_TYPE":"deal"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.bindings.bind
try
{
const
response =
await
$b24.
callMethod
(
"crm.timeline.bindings.bind"
,
{
fields
: {
"OWNER_ID"
:
1110
,
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
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
'crm.timeline.bindings.bind'
,
[
'fields'
=> [
'OWNER_ID'
=>
1110
,
'ENTITY_ID'
=>
10
,
'ENTITY_TYPE'
=>
'deal'
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
'Error binding timeline: '
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
"crm.timeline.bindings.bind"
,
{
fields
: {
"OWNER_ID"
:
1110
,
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
,
},
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
'crm.timeline.bindings.bind'
,
[
'fields'
=> [
'OWNER_ID'
=>
1110
,
'ENTITY_ID'
=>
10
,
'ENTITY_TYPE'
=>
'deal'
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
if the binding was successfully created, otherwise —
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
"OWNER_ID is not defined or invalid."
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
Error Message
Description
Empty string
OWNER_ID is not defined or invalid
The required parameter
OWNER_ID
was not provided or the provided
OWNER_ID
is invalid
Empty string
ENTITY_ID is not defined or invalid.
The required parameter
ENTITY_ID
was not provided or the provided
ENTITY_ID
is invalid
Empty string
ENTITY_TYPE is not defined or invalid.
The required parameter
ENTITY_TYPE
was not provided or the provided
ENTITY_TYPE
is invalid
Empty string
Access denied.
No permission to edit the entity in CRM
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
Get the list of bindings for a record in the timeline crm.timeline.bindings.list
Unbind Timeline Record from CRM Entity crm.timeline.bindings.unbind
Get CRM entity bindings fields and timeline record in crm.timeline.bindings.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Retrieve List of Timeline Record Relationships

---

## Get the list of bindings for a record in the timeline crm.timeline.bindings.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/bindings/crm-timeline-bindings-list

Get the list of bindings for a record in the timeline crm.timeline.bindings.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of bindings for a record in the timeline crm.timeline.bindings.list
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
The method retrieves a list of bindings for a record in the timeline.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
filter
*
object
Object for filtering selected records.
The
OWNER_ID
field is required; other fields are not necessary.
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
'{"filter":{"OWNER_ID":999}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.bindings.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":{"OWNER_ID":999},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.bindings.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.timeline.bindings.list'
,
{
filter
: {
"OWNER_ID"
:
999
,
},
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in chunks and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.timeline.bindings.list'
, {
filter
: {
"OWNER_ID"
:
999
,
},
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
'crm.timeline.bindings.list'
, {
filter
: {
"OWNER_ID"
:
999
,
},
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
'crm.timeline.bindings.list'
,
[
'filter'
=> [
'OWNER_ID'
=>
999
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
}
else
{
print_r
(
$result
->
data
());
if
(
$result
->
more
()) {
$result
->
next
();
}
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
'Error fetching timeline bindings: '
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
"crm.timeline.bindings.list"
,
{
filter
: {
"OWNER_ID"
:
999
,
},
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
if
(result.
more
())
{
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
'crm.timeline.bindings.list'
,
[
'filter'
=> [
'OWNER_ID'
=>
999
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
"OWNER_ID"
:
"999"
,
"ENTITY_ID"
:
"39"
,
"ENTITY_TYPE"
:
"deal"
}
,
{
"OWNER_ID"
:
"999"
,
"ENTITY_ID"
:
"92"
,
"ENTITY_TYPE"
:
"company"
}
,
{
"OWNER_ID"
:
"999"
,
"ENTITY_ID"
:
"205"
,
"ENTITY_TYPE"
:
"lead"
}
]
,
"total"
:
3
,
"time"
:
{
"start"
:
1715091541.642592
,
"finish"
:
1715091541.730599
,
"duration"
:
0.08800697326660156
,
"date_start"
:
"2024-05-03T17:19:01+02:00"
,
"date_finish"
:
"2024-05-03T17:19:01+02:00"
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
Root element of the response containing an array of objects with
information
about the found bindings
total
integer
Total number of records found
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
"OWNER_ID is not defined or invalid."
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
Error Message
Description
Empty string
OWNER_ID is not defined or invalid
The required parameter
OWNER_ID
was not provided or the provided
OWNER_ID
is invalid.
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
Add Timeline Record Binding to CRM Entity crm.timeline.bindings.bind
Unbind Timeline Record from CRM Entity crm.timeline.bindings.unbind
Get CRM entity bindings fields and timeline record in crm.timeline.bindings.fields
Copied
Was the article helpful?
Yes
No
Previous
Add Timeline Record Relationship with CRM Entity
Next
Remove Timeline Record Relationship with CRM Entity

---

## Unbind Timeline Record from CRM Entity crm.timeline.bindings.unbind

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/bindings/crm-timeline-bindings-unbind

Unbind Timeline Record from CRM Entity crm.timeline.bindings.unbind | Bitrix24 REST API and Marketplace Applications
Method Parameters
Unbind Timeline Record from CRM Entity crm.timeline.bindings.unbind
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
This method removes the binding of a timeline record from a CRM entity.
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
) for unbinding the timeline record from the CRM entity in the form of a structure:
fields
: {
"OWNER_ID"
:
"value"
,
"ENTITY_ID"
:
"value"
,
"ENTITY_TYPE"
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
OWNER_ID
*
integer
Identifier of the timeline record
ENTITY_ID
*
integer
Identifier
ID
of the CRM entity to which the comment is linked
ENTITY_TYPE
*
string
Type of the entity to which the comment is linked. Possible values:
lead
— lead
deal
— deal
contact
— contact
company
— company
order
— order
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
'{"fields":{"OWNER_ID":1110,"ENTITY_ID":10,"ENTITY_TYPE":"deal"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.bindings.unbind
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"OWNER_ID":1110,"ENTITY_ID":10,"ENTITY_TYPE":"deal"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.bindings.unbind
try
{
const
response =
await
$b24.
callMethod
(
"crm.timeline.bindings.unbind"
,
{
fields
: {
"OWNER_ID"
:
1110
,
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
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
'crm.timeline.bindings.unbind'
,
[
'fields'
=> [
'OWNER_ID'
=>
1110
,
'ENTITY_ID'
=>
10
,
'ENTITY_TYPE'
=>
'deal'
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
'Error unbinding timeline: '
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
"crm.timeline.bindings.unbind"
,
{
fields
: {
"OWNER_ID"
:
1110
,
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
,
},
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
'crm.timeline.bindings.unbind'
,
[
'fields'
=> [
'OWNER_ID'
=>
1110
,
'ENTITY_ID'
=>
10
,
'ENTITY_TYPE'
=>
'deal'
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
if the binding was successfully removed, otherwise —
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
"OWNER_ID is not defined or invalid."
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
Error Message
Description
Empty string
OWNER_ID is not defined or invalid
The required parameter
OWNER_ID
was not provided or the provided
OWNER_ID
is invalid
Empty string
ENTITY_ID is not defined or invalid.
The required parameter
ENTITY_ID
was not provided or the provided
ENTITY_ID
is invalid
Empty string
ENTITY_TYPE is not defined or invalid.
The required parameter
ENTITY_TYPE
was not provided or the provided
ENTITY_TYPE
is invalid
Empty string
Not found.
The record of the timeline binding with the CRM entity was not found
Empty string
Access denied.
No permission to edit the entity in CRM
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
Add Timeline Record Binding to CRM Entity crm.timeline.bindings.bind
Get the list of bindings for a record in the timeline crm.timeline.bindings.list
Get CRM entity bindings fields and timeline record in crm.timeline.bindings.fields
Copied
Was the article helpful?
Yes
No
Previous
Retrieve List of Timeline Record Relationships
Next
Get Fields of Timeline Record Relationships and CRM Entities

---

## Get CRM entity bindings fields and timeline record in crm.timeline.bindings.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/bindings/crm-timeline-bindings-fields

Get CRM entity bindings fields and timeline record in crm.timeline.bindings.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get CRM entity bindings fields and timeline record in crm.timeline.bindings.fields
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
This method retrieves a list of available fields for linking CRM entities and timeline records.
No parameters.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.bindings.fields
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
https://**put_your_bitrix24_address**/rest/crm.timeline.bindings.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.timeline.bindings.fields"
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
'crm.timeline.bindings.fields'
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
'Error fetching timeline bindings fields: '
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
"crm.timeline.bindings.fields"
,
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
'crm.timeline.bindings.fields'
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
"OWNER_ID"
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
"Timeline record ID"
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
"Entity ID"
}
,
"ENTITY_TYPE"
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
"Entity type"
}
}
,
"time"
:
{
"start"
:
1715091541.642592
,
"finish"
:
1715091541.730599
,
"duration"
:
0.08800697326660156
,
"date_start"
:
"2024-05-03T17:19:01+02:00"
,
"date_finish"
:
"2024-05-03T17:19:01+02:00"
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
Root element of the response. Contains
fields
linking timeline records to CRM entities
time
time
Information about the request execution time
List of Fields
List of Fields
Required parameters are marked with *
Name
type
Description
OWNER_ID
*
integer
Identifier of the timeline record. Read-only
ENTITY_ID
*
integer
ID
of the CRM entity to which the comment is linked. Immutable
ENTITY_TYPE
*
string
Type of the entity to which the comment is linked. Immutable. Possible values:
lead
— lead
deal
— deal
contact
— contact
company
— company
order
— order
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
"error"
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
0
Other errors (e.g., fatal errors)
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
Add Timeline Record Binding to CRM Entity crm.timeline.bindings.bind
Get the list of bindings for a record in the timeline crm.timeline.bindings.list
Unbind Timeline Record from CRM Entity crm.timeline.bindings.unbind
Copied
Was the article helpful?
Yes
No
Previous
Remove Timeline Record Relationship with CRM Entity
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method:
any user
Methods for working with a "Comment" type deal in the
timeline
Method
Description
crm.timeline.comment.add
Adds a new comment to the timeline
crm.timeline.comment.update
Updates a comment
crm.timeline.comment.get
Retrieves information about a comment
crm.timeline.comment.list
Retrieves a list of all comments for a CRM entity
crm.timeline.comment.delete
Deletes a comment
crm.timeline.comment.fields
Retrieves a list of timeline comment fields
Additional Information
Additional Information
Timeline in CRM entity
CRM Entity Type
Copied
Was the article helpful?
Yes
No
Previous
Get Fields of Timeline Record Relationships and CRM Entities
Next
Add Comment

---

## Add Comment crm.timeline.comment.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/crm-timeline-comment-add

Add Comment crm.timeline.comment.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Comment crm.timeline.comment.add
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
This method adds a new activity of type "Comment" to the timeline.
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
) for adding a new activity of type "Comment" in the form of a structure:
fields
:
{
"ENTITY_ID"
:
'value'
,
"ENTITY_TYPE"
:
'value'
,
"COMMENT"
:
'value'
,
"AUTHOR_ID"
:
'value'
,
"FILES"
:
[
[
"file name"
,
"file content"
]
,
[
"file name"
,
"file content"
]
,
]
}
The file content is transmitted as a
base64 string
Warning
Starting from version crm 23.100.0, the method only accepts parameters with the key
fields
in lowercase. Other undocumented variants (Fields, FIELDS, arFields) are not accepted.
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
ENTITY_ID
*
integer
ID
of the element to which the comment is attached.
The value can be obtained using the
crm.item.list
method or when creating an element with the help of
crm.item.add
ENTITY_TYPE
*
string
Identifier of the
system
or
user-defined type
of the CRM object to which the comment is attached. For example:
lead
,
deal
,
contact
,
company
,
order
,
dynamic_1046
AUTHOR_ID
user
Identifier of the user adding the comment
COMMENT
*
string
Text of the comment
FILES
attached_diskfile
List of files. An array of values described by the
rules
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
'{"fields":{"ENTITY_ID":10,"ENTITY_TYPE":"deal","COMMENT":"New comment was added","AUTHOR_ID":5,"FILES":[["1.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="],["2.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="]]}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.comment.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"ENTITY_ID":10,"ENTITY_TYPE":"deal","COMMENT":"New comment was added","AUTHOR_ID":5,"FILES":[["1.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="],["2.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="]]},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.comment.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.timeline.comment.add"
,
{
fields
:
{
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
,
"COMMENT"
:
"New comment was added"
,
"AUTHOR_ID"
:
5
,
"FILES"
: [
[
"1.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
[
"2.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
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
'crm.timeline.comment.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
10
,
'ENTITY_TYPE'
=>
'deal'
,
'COMMENT'
=>
'New comment was added'
,
'AUTHOR_ID'
=>
5
,
'FILES'
=> [
[
'1.gif'
,
'R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=='
],
[
'2.gif'
,
'R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=='
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
'Error adding timeline comment: '
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
"crm.timeline.comment.add"
,
{
fields
:
{
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
,
"COMMENT"
:
"New comment was added"
,
"AUTHOR_ID"
:
5
,
"FILES"
: [
[
"1.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
[
"2.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
]
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
'crm.timeline.comment.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
10
,
'ENTITY_TYPE'
=>
'deal'
,
'COMMENT'
=>
'New comment was added'
,
'AUTHOR_ID'
=>
5
,
'FILES'
=> [
[
"1.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
[
"2.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
]
]
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
999
,
"time"
:
{
"start"
:
1715091541.642592
,
"finish"
:
1715091541.730599
,
"duration"
:
0.08800697326660156
,
"date_start"
:
"2024-05-03T17:19:01+02:00"
,
"date_finish"
:
"2024-05-03T17:19:01+02:00"
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
integer
Returns the integer identifier of the added comment
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
OWNER_NOT_FOUND
Owner of the element not found
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Element not found
INVALID_ARG_VALUE
Empty comment
100
Required fields not provided
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
Update Comment crm.timeline.comment.update
Get Information About the Comment crm.timeline.comment.get
Get a List of Comments crm.timeline.comment.list
Delete Comment crm.timeline.comment.delete
Get CRM Timeline Comment Fields
How to Add a Comment to the Timeline of a Smart Process
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Comment

---

## Update Comment crm.timeline.comment.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/crm-timeline-comment-update

Update Comment crm.timeline.comment.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Comment crm.timeline.comment.update
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
This method updates a "Comment" type activity in the timeline.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Integer identifier of the "Comment" type activity (for example,
1
). Identifiers can be obtained using the
crm.timeline.comment.list
method
fields
*
object
Values of the fields (detailed description provided
below
) for updating the "Comment" type activity in the structure:
fields
:
{
"COMMENT"
:
"value"
,
"FILES"
: [
[
"file name"
,
"file"
],
[
"file name"
,
"file"
],
]
}
Warning
Starting from version crm 23.100.0, only parameters with the key
fields
in lowercase are accepted. Other undocumented variants (Fields, FIELDS, arFields) are not accepted.
ownerTypeId
integer
Integer identifier of the CRM entity type
to which the comment is attached (for example,
2
for a deal)
ownerId
integer
Integer identifier of the CRM entity to which the comment is attached (for example,
1
). A list of identifiers can be obtained using the
crm.timeline.bindings.list
method (field
ENTITY_ID
)
Parameter fields
Parameter fields
Name
type
Description
COMMENT
string
Text of the comment
FILES
attached_diskfile
List of files. An array of values described by
rules
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
'{"id":999,"fields":{"COMMENT":"Comment was changed","FILES":[["1.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="],["2.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="]]}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.comment.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"fields":{"COMMENT":"Comment was changed","FILES":[["1.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="],["2.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="]]},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.comment.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.comment.update'
,
{
id
:
999
,
fields
:
{
"COMMENT"
:
"Comment was changed"
,
"FILES"
: [
[
"1.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
[
"2.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
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
'crm.timeline.comment.update'
,
[
'id'
=>
999
,
'fields'
=> [
'COMMENT'
=>
'Comment was changed'
,
'FILES'
=> [
[
'1.gif'
,
'R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=='
],
[
'2.gif'
,
'R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=='
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
'Error updating timeline comment: '
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
"crm.timeline.comment.update"
,
{
id
:
999
,
fields
:
{
"COMMENT"
:
"Comment was changed"
,
"FILES"
: [
[
"1.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
[
"2.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
]
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
'crm.timeline.comment.update'
,
[
'id'
=>
999
,
'fields'
=> [
'COMMENT'
=>
'Comment was changed'
,
'FILES'
=> [
[
"1.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
[
"2.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
]
]
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
999
,
"time"
:
{
"start"
:
1715091541.642592
,
"finish"
:
1715091541.730599
,
"duration"
:
0.08800697326660156
,
"date_start"
:
"2024-05-03T17:19:01+02:00"
,
"date_finish"
:
"2024-05-03T17:19:01+02:00"
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
integer
Returns the integer identifier of the updated comment
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
OWNER_NOT_FOUND
Owner of the item not found
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Item not found
INVALID_ARG_VALUE
Empty comment
100
Required fields not provided
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
Add Comment crm.timeline.comment.add
Get Information About the Comment crm.timeline.comment.get
Get a List of Comments crm.timeline.comment.list
Delete Comment crm.timeline.comment.delete
Get CRM Timeline Comment Fields
Copied
Was the article helpful?
Yes
No
Previous
Add Comment
Next
Get Comment Information

---

## Get Information About the Comment crm.timeline.comment.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/crm-timeline-comment-get

Get Information About the Comment crm.timeline.comment.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Information About the Comment crm.timeline.comment.get
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
This method retrieves information about a comment type activity.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Integer identifier of the comment type activity (for example,
1
). Identifiers can be obtained using the
crm.timeline.comment.list
method
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
'{"id":999}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.comment.get
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
https://**put_your_bitrix24_address**/rest/crm.timeline.comment.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.comment.get'
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
'crm.timeline.comment.get'
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
'Error getting timeline comment: '
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
"crm.timeline.comment.get"
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
'crm.timeline.comment.get'
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
{
"ID"
:
"999"
,
"ENTITY_ID"
:
"2"
,
"ENTITY_TYPE"
:
"deal"
,
"CREATED"
:
"2020-03-02T12:00:00+02:00"
,
"COMMENT"
:
"New comment was added"
,
"AUTHOR_ID"
:
"1"
,
"FILES"
:
{
"1"
:
{
"id"
:
1
,
"date"
:
"2020-03-02T12:00:00+02:00"
,
"type"
:
"image"
,
"name"
:
"1.gif"
,
"size"
:
43
,
"image"
:
{
"width"
:
1
,
"height"
:
1
}
,
"authorId"
:
1
,
"authorName"
:
"John Dou"
,
"urlPreview"
:
"https://my.bitrix24.com/disk/showFile/930/?&ncc=1&width=640&height=640&signature=292f450929833cd881070155e05a2c41b5bb265ea8c8c1bc2108dbcbb56f667f&ts=1718366521&filename=1.gif"
,
"urlShow"
:
"https://my.bitrix24.com/disk/showFile/930/?&ncc=1&ts=1718366521&filename=1.gif"
,
"urlDownload"
:
"https://my.bitrix24.com/disk/downloadFile/930/?&ncc=1&filename=1.gif"
}
,
"2"
:
{
"id"
:
2
,
"date"
:
"2020-03-02T12:00:00+02:00"
,
"type"
:
"image"
,
"name"
:
"2.gif"
,
"size"
:
43
,
"image"
:
{
"width"
:
1
,
"height"
:
1
}
,
"authorId"
:
1
,
"authorName"
:
"John Dou"
,
"urlPreview"
:
"https://my.bitrix24.com/disk/showFile/931/?&ncc=1&width=640&height=640&signature=118de010a40eff06fb9d691ee9235e2ef809a17780e46927bf8b12f8dc3224db&ts=1718366521&filename=2.gif"
,
"urlShow"
:
"https://my.bitrix24.com/disk/showFile/931/?&ncc=1&ts=1718366521&filename=2.gif"
,
"urlDownload"
:
"https://my.bitrix24.com/disk/downloadFile/931/?&ncc=1&filename=2.gif"
}
}
}
,
"time"
:
{
"start"
:
1715091541.642592
,
"finish"
:
1715091541.730599
,
"duration"
:
0.08800697326660156
,
"date_start"
:
"2024-05-03T17:19:01+02:00"
,
"date_finish"
:
"2024-05-03T17:19:01+02:00"
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
The root element of the response. The values for the
result
field correspond to the fields of the
result
object.
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
Error Message
Description
Empty string
Not found.
The element with the specified parameters was not found
Empty string
Access denied.
No permission to edit the entity in CRM
Empty string
ID is not defined or invalid.
Required fields were not provided
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
Add Comment crm.timeline.comment.add
Update Comment crm.timeline.comment.update
Get a List of Comments crm.timeline.comment.list
Delete Comment crm.timeline.comment.delete
Get CRM Timeline Comment Fields
Copied
Was the article helpful?
Yes
No
Previous
Update Comment
Next
Get List of Comments

---

## Get a List of Comments crm.timeline.comment.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/crm-timeline-comment-list

Get a List of Comments crm.timeline.comment.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a List of Comments crm.timeline.comment.list
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
The method retrieves a list of all comments of the specified CRM entity type.
Method Parameters
Method Parameters
Name
type
Description
select
array
An array containing the list of fields to be selected (see the fields of the
result
object). If not provided or an empty array is passed, the result will return an empty array
filter
object
An object for filtering the selected comments in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
correspond to the fields of the
result
object.
Required fields:
ENTITY_ID
,
ENTITY_TYPE
.
An additional prefix can be assigned to the key to specify the filter behavior. Possible prefix values:
>=
— greater than or equal to
>
— greater than
<=
— less than or equal to
<
— less than
@
— IN (an array is passed as the value)
!@
— NOT IN (an array is passed as the value)
%
— LIKE, substring search. The
%
symbol in the filter value does not need to be passed. The search looks for the substring in any position of the string
=%
— LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
"mol%"
— looking for values starting with "mol"
"%mol"
— looking for values ending with "mol"
"%mol%"
— looking for values where "mol" can be in any position
%=
— LIKE (see description above)
!%
— NOT LIKE, substring search. The
%
symbol in the filter value does not need to be passed. The search goes from both sides.
!=%
— NOT LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
"mol%"
— looking for values not starting with "mol"
"%mol"
— looking for values not ending with "mol"
"%mol%"
— looking for values where the substring "mol" is not present in any position
!%=
— NOT LIKE (see description above)
=
— equal, exact match (used by default)
!=
— not equal
!
— not equal
order
object
An object for sorting the selected comments in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
correspond to the fields of the
result
object.
Possible values for
order
:
ASC
— in ascending order
DESC
— in descending order
start
integer
This parameter is used for managing pagination.
The page size of results is always static: 50 records.
To select the second page of results, you need to pass the value
50
. To select the third page of results, the value is
100
, and so on.
The formula for calculating the
start
parameter value:
start = (N-1) * 50
, where
N
— the number of the desired page
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
'{"filter":{"ENTITY_ID":10,"ENTITY_TYPE":"deal"},"select":["ID","CREATED","ENTITY_ID","ENTITY_TYPE","AUTHOR_ID","COMMENT","FILES"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.comment.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":{"ENTITY_ID":10,"ENTITY_TYPE":"deal"},"select":["ID","CREATED","ENTITY_ID","ENTITY_TYPE","AUTHOR_ID","COMMENT","FILES"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.comment.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.timeline.comment.list'
,
{
filter
: {
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
,
},
select
: [
"ID"
,
"CREATED"
,
"ENTITY_ID"
,
"ENTITY_TYPE"
,
"AUTHOR_ID"
,
"COMMENT"
,
"FILES"
,
],
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
);
const
items = response.
getData
() || [];
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
, entity); }
}
catch
(error) {
console
.
error
(
'Request failed'
, error);
}
// fetchListMethod is preferred when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.timeline.comment.list'
, {
filter
: {
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
,
},
select
: [
"ID"
,
"CREATED"
,
"ENTITY_ID"
,
"ENTITY_TYPE"
,
"AUTHOR_ID"
,
"COMMENT"
,
"FILES"
,
],
},
'ID'
);
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
, entity); }
}
}
catch
(error) {
console
.
error
(
'Request failed'
, error);
}
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.comment.list'
, {
filter
: {
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
,
},
select
: [
"ID"
,
"CREATED"
,
"ENTITY_ID"
,
"ENTITY_TYPE"
,
"AUTHOR_ID"
,
"COMMENT"
,
"FILES"
,
],
},
0
);
const
result = response.
getData
().
result
|| [];
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
, entity); }
}
catch
(error) {
console
.
error
(
'Request failed'
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
'crm.timeline.comment.list'
,
[
'filter'
=> [
'ENTITY_ID'
=>
10
,
'ENTITY_TYPE'
=>
'deal'
,
],
'select'
=> [
'ID'
,
'CREATED'
,
'ENTITY_ID'
,
'ENTITY_TYPE'
,
'AUTHOR_ID'
,
'COMMENT'
,
'FILES'
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
'Error fetching timeline comments: '
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
"crm.timeline.comment.list"
,
{
filter
: {
"ENTITY_ID"
:
10
,
"ENTITY_TYPE"
:
"deal"
,
},
select
: [
"ID"
,
"CREATED"
,
"ENTITY_ID"
,
"ENTITY_TYPE"
,
"AUTHOR_ID"
,
"COMMENT"
,
"FILES"
,
],
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
'crm.timeline.comment.list'
,
[
'filter'
=> [
'ENTITY_ID'
=>
10
,
'ENTITY_TYPE'
=>
'deal'
,
],
'select'
=> [
'ID'
,
'CREATED'
,
'ENTITY_ID'
,
'ENTITY_TYPE'
,
'AUTHOR_ID'
,
'COMMENT'
,
'FILES'
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
"ID"
:
"999"
,
"ENTITY_ID"
:
"2"
,
"ENTITY_TYPE"
:
"deal"
,
"CREATED"
:
"2020-03-02T12:00:00+02:00"
,
"COMMENT"
:
"New comment was added"
,
"AUTHOR_ID"
:
"1"
,
"FILES"
:
{
"1"
:
{
"id"
:
1
,
"date"
:
"2020-03-02T12:00:00+02:00"
,
"type"
:
"image"
,
"name"
:
"1.gif"
,
"size"
:
43
,
"image"
:
{
"width"
:
1
,
"height"
:
1
}
,
"authorId"
:
1
,
"authorName"
:
"John Dou"
,
"urlPreview"
:
"https://my.bitrix24.com/disk/showFile/930/?&ncc=1&width=640&height=640&signature=292f450929833cd881070155e05a2c41b5bb265ea8c8c1bc2108dbcbb56f667f&ts=1718366521&filename=1.gif"
,
"urlShow"
:
"https://my.bitrix24.com/disk/showFile/930/?&ncc=1&ts=1718366521&filename=1.gif"
,
"urlDownload"
:
"https://my.bitrix24.com/disk/downloadFile/930/?&ncc=1&filename=1.gif"
}
,
"2"
:
{
"id"
:
2
,
"date"
:
"2020-03-02T12:00:00+02:00"
,
"type"
:
"image"
,
"name"
:
"2.gif"
,
"size"
:
43
,
"image"
:
{
"width"
:
1
,
"height"
:
1
}
,
"authorId"
:
1
,
"authorName"
:
"John Dou"
,
"urlPreview"
:
"https://my.bitrix24.com/disk/showFile/931/?&ncc=1&width=640&height=640&signature=118de010a40eff06fb9d691ee9235e2ef809a17780e46927bf8b12f8dc3224db&ts=1718366521&filename=2.gif"
,
"urlShow"
:
"https://my.bitrix24.com/disk/showFile/931/?&ncc=1&ts=1718366521&filename=2.gif"
,
"urlDownload"
:
"https://my.bitrix24.com/disk/downloadFile/931/?&ncc=1&filename=2.gif"
}
}
,
}
,
{
"ID"
:
"1000"
,
"ENTITY_ID"
:
"2"
,
"ENTITY_TYPE"
:
"deal"
,
"CREATED"
:
"2020-03-02T12:00:00+02:00"
,
"COMMENT"
:
"Test comment"
,
"AUTHOR_ID"
:
"1"
,
"FILES"
:
{
}
,
}
]
,
"total"
:
2
,
"time"
:
{
"start"
:
1715091541.642592
,
"finish"
:
1715091541.730599
,
"duration"
:
0.08800697326660156
,
"date_start"
:
"2024-05-03T17:19:01+02:00"
,
"date_finish"
:
"2024-05-03T17:19:01+02:00"
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
The root element of the response, containing an array of objects with information about the selected comments
total
integer
The total number of records found
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
Error Message
Description
Empty string
Access denied.
No rights to edit the entity in CRM
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
Add Comment crm.timeline.comment.add
Update Comment crm.timeline.comment.update
Get Information About the Comment crm.timeline.comment.get
Delete Comment crm.timeline.comment.delete
Get CRM Timeline Comment Fields
Copied
Was the article helpful?
Yes
No
Previous
Get Comment Information
Next
Delete Comment

---

## Delete Comment crm.timeline.comment.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/crm-timeline-comment-delete

Delete Comment crm.timeline.comment.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Comment crm.timeline.comment.delete
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
This method deletes a "Comment" type activity.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Integer identifier of the "Comment" type activity (for example,
1
). Identifiers can be obtained using the
crm.timeline.comment.list
method
ownerTypeId
integer
Integer identifier of the CRM entity type
to which the comment is attached (for example,
2
for a deal)
ownerId
integer
Integer identifier of the CRM entity to which the comment is attached (for example,
1
). A list of identifiers can be obtained using the
crm.timeline.bindings.list
method (field
ENTITY_ID
)
Warning
When specifying
ownerTypeId
and
ownerId
, if the comment is linked to multiple entities, the comment will be deleted from the entity whose identifiers were provided. You can get a list of all bindings for the comment using the
crm.timeline.bindings.list
method.
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
'{"id":999,"ownerTypeId":2,"ownerId":10}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.comment.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"ownerTypeId":2,"ownerId":10,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.comment.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.comment.delete'
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
10
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
'crm.timeline.comment.delete'
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
10
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
'Error deleting timeline comment: '
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
"crm.timeline.comment.delete"
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
10
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
'crm.timeline.comment.delete'
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
10
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
1715091541.642592
,
"finish"
:
1715091541.730599
,
"duration"
:
0.08800697326660156
,
"date_start"
:
"2024-05-03T17:19:01+02:00"
,
"date_finish"
:
"2024-05-03T17:19:01+02:00"
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
The operation always returns
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
Insufficient permissions
NOT_FOUND
Element not found
MULTIPLE_BINDINGS
Element has bindings to multiple entities
OWNER_NOT_FOUND
Owner of the element not found
100
Required fields not provided
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
Add Comment crm.timeline.comment.add
Update Comment crm.timeline.comment.update
Get Information About the Comment crm.timeline.comment.get
Get a List of Comments crm.timeline.comment.list
Get CRM Timeline Comment Fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of Comments
Next
Get Comment Fields

---

## Get CRM Timeline Comment Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/crm-timeline-comment-fields

Get CRM Timeline Comment Fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get CRM Timeline Comment Fields
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
This method retrieves fields of the "Comment" type deal.
No parameters.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.comment.fields
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
https://**put_your_bitrix24_address**/rest/crm.timeline.comment.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.comment.fields'
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
'crm.timeline.comment.fields'
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
'Error fetching timeline comment fields: '
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
"crm.timeline.comment.fields"
,
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
'crm.timeline.comment.fields'
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
"Date Added"
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
"ID of the entity to which the comment is linked"
}
,
"ENTITY_TYPE"
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
"Type of the entity to which the comment is linked"
}
,
"AUTHOR_ID"
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
"Author"
}
,
"COMMENT"
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
"Comment Text"
}
,
"FILES"
:
{
"type"
:
"attached_diskfile"
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
"List of Files"
}
}
,
"time"
:
{
"start"
:
1715091541.642592
,
"finish"
:
1715091541.730599
,
"duration"
:
0.08800697326660156
,
"date_start"
:
"2024-05-03T17:19:01+02:00"
,
"date_finish"
:
"2024-05-03T17:19:01+02:00"
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
Root element of the response, containing all
comment fields
time
time
Information about the request execution time
List of Fields
List of Fields
Required parameters are marked with *
Name
type
Description
ID
integer
Identifier. Read-only
CREATED
datetime
Date added. Read-only
ENTITY_ID
integer
ID
of the entity to which the comment is linked. Immutable
ENTITY_TYPE
string
Type of the entity to which the comment is linked. Immutable.
Values:
lead
— lead
deal
— deal
contact
— contact
company
— company
order
— order
AUTHOR_ID
integer
Author. Immutable
COMMENT
string
Comment text
FILES
attached_diskfile
List of files. An array of values described by
rules
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
"error"
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
0
Other errors (e.g., fatal errors)
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
Add Comment crm.timeline.comment.add
Update Comment crm.timeline.comment.update
Get Information About the Comment crm.timeline.comment.get
Get a List of Comments crm.timeline.comment.list
Delete Comment crm.timeline.comment.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete Comment
Next
Overview of Events

---

## Overview of Events

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/events/index

Overview of Events | Bitrix24 REST API and Marketplace Applications
Overview of Events
Overview of Events
Scope:
crm
Who can subscribe:
any user
List of events when working with timeline comments.
Event
Triggered by
onCrmTimelineCommentAdd
When a new comment is created in the timeline
onCrmTimelineCommentUpdate
When a comment is updated in the timeline
onCrmTimelineCommentDelete
When a comment is deleted from the timeline
Copied
Was the article helpful?
Yes
No
Previous
Get Comment Fields
Next
On Creating a New CRM Activity of Type "Comment"

---

## Event for Creating a New Deal Type "Comment" onCrmTimelineCommentAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/events/on-Crm-Timeline-Comment-Add

Event for Creating a New Deal Type "Comment" onCrmTimelineCommentAdd | Bitrix24 REST API and Marketplace Applications
Event for Creating a New Deal Type "Comment" onCrmTimelineCommentAdd
Event for Creating a New Deal Type "Comment" onCrmTimelineCommentAdd
What the Handler Receives
Parameter data[]
Parameter auth[]
Continue Your Exploration
Scope:
crm
Who can subscribe:
any user
The event triggers when a new deal of type "Comment" is added to the CRM timeline.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
array
(
'event'
=>
'onCrmTimelineCommentAdd'
,
'data'
=>
array
(
'ID'
=>
999
,
),
'ts'
=>
'1466439714'
,
'auth'
=>
array
(
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
),
)
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic code of the event. In our case, it is
onCrmTimelineCommentAdd
data
*
array
Array with data of the added element
ts
*
timestamp
Date and time of the event sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
ID
with the value of the added comment's identifier
Parameter auth[]
Parameter auth[]
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
Continue Your Exploration
Continue Your Exploration
Overview of Events
Event on deal update of type "Comment" onCrmTimelineCommentUpdate
Event for Deleting a "Comment" Activity onCrmTimelineCommentDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
On Updating a CRM Activity of Type "Comment"

---

## Event on deal update of type "Comment" onCrmTimelineCommentUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/events/on-Crm-Timeline-Comment-Update

Event on deal update of type "Comment" onCrmTimelineCommentUpdate | Bitrix24 REST API and Marketplace Applications
Event on deal update of type "Comment" onCrmTimelineCommentUpdate
Event on deal update of type "Comment" onCrmTimelineCommentUpdate
What the handler receives
Parameter data[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event triggers on the update of a deal of type "Comment" in the CRM timeline.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
array
(
'event'
=>
'onCrmTimelineCommentUpdate'
,
'data'
=>
array
(
'ID'
=>
999
,
),
'ts'
=>
'1466439714'
,
'auth'
=>
array
(
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
),
)
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic code of the event. In our case, it is
onCrmTimelineCommentUpdate
data
*
array
Array with data of the updated element
ts
*
timestamp
Date and time of the event sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
ID
with the value of the updated comment identifier
Parameter auth[]
Parameter auth[]
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
Overview of Events
Event for Creating a New Deal Type "Comment" onCrmTimelineCommentAdd
Event for Deleting a "Comment" Activity onCrmTimelineCommentDelete
Copied
Was the article helpful?
Yes
No
Previous
On Creating a New CRM Activity of Type "Comment"
Next
On Deleting a CRM Activity of Type "Comment"

---

## Event for Deleting a "Comment" Activity onCrmTimelineCommentDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/comments/events/on-Crm-Timeline-Comment-Delete

Event for Deleting a "Comment" Activity onCrmTimelineCommentDelete | Bitrix24 REST API and Marketplace Applications
Event for Deleting a "Comment" Activity onCrmTimelineCommentDelete
Event for Deleting a "Comment" Activity onCrmTimelineCommentDelete
What the Handler Receives
Parameter data[]
Parameter auth[]
Continue Exploring
Scope:
crm
Who can subscribe:
any user
This event triggers when a "Comment" activity is deleted from the CRM timeline.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the Handler Receives
What the Handler Receives
Data is sent as a POST request
array
(
'event'
=>
'onCrmTimelineCommentDelete'
,
'data'
=>
array
(
'ID'
=>
999
,
),
'ts'
=>
'1466439714'
,
'auth'
=>
array
(
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
),
)
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic code of the event. In our case, it is
onCrmTimelineCommentDelete
data
*
array
Array with data of the deleted element
ts
*
timestamp
Date and time the event was sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
ID
with the value of the deleted comment's identifier
Parameter auth[]
Parameter auth[]
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
Overview of Events
Event for Creating a New Deal Type "Comment" onCrmTimelineCommentAdd
Event on deal update of type "Comment" onCrmTimelineCommentUpdate
Copied
Was the article helpful?
Yes
No
Previous
On Updating a CRM Activity of Type "Comment"
Next
Log Record Journal

---

## Additional Content Blocks

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/layout-blocks/index

Additional Content Blocks | Bitrix24 REST API and Marketplace Applications
Additional Content Blocks
Additional Content Blocks
Deleting Timeline Entries
Deleting the Application
See Also
Methods for working with additional content blocks in the timeline:
Method
Description
crm.timeline.layout.blocks.set
Sets a collection of additional content blocks in the timeline entry
crm.timeline.layout.blocks.get
Retrieves the set of additional content blocks established by the application for the timeline entry
crm.timeline.layout.blocks.delete
Deletes the set of additional content blocks established by the application for the timeline entry
Deleting Timeline Entries
Deleting Timeline Entries
When a timeline entry is deleted, the sets of additional content blocks added by applications will also be permanently removed.
Deleting the Application
Deleting the Application
When an application is deleted, all sets of additional content blocks added to timeline entries by it will be permanently removed.
See Also
See Also
Example Test Application
Methods for Working with Sets of Additional Content Blocks for Deals
Was the article helpful?
Yes
No
Previous
Delete Logo
Next
Install a Set of Additional Content Blocks

---

## Set a set of additional content blocks in the timeline record crm.timeline.layout.blocks.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/layout-blocks/crm-timeline-layout-blocks-set

Set a set of additional content blocks in the timeline record crm.timeline.layout.blocks.set | Bitrix24 REST API and Marketplace Applications
Set a set of additional content blocks in the timeline record crm.timeline.layout.blocks.set
Set a set of additional content blocks in the timeline record crm.timeline.layout.blocks.set
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
crm.timeline.layout.blocks.set
sets a set of additional content blocks for a timeline record.
Setting a new set of additional content blocks in a timeline record will erase the previously added set within the same application.
Setting a set of additional content blocks cannot be applied to timeline records related to:
activities, for activities use the methods
crm.activity.layout.blocks.*
,
timeline log records
,
deprecated timeline records.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the CRM object to which the timeline record is linked
entityId
*
integer
Identifier of the CRM object to which the timeline record is linked
timelineId
*
integer
Identifier of the timeline record
layout
*
RestAppLayoutDto
Object describing the set of additional content blocks
Code Examples
Code Examples
In the timeline record with
id = 8
, linked to the deal with
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
'{"entityTypeId":2,"entityId":4,"timelineId":8,"layout":{"blocks":{"block_1":{"type":"text","properties":{"value":"Hello!\nWe are starting.","multiline":true,"bold":true,"color":"base_90"}},"block_2":{"type":"largeText","properties":{"value":"Hello!\nWe are starting.\nWe are continuing.\nWe are still working on this.\nWe are continuing.\nWe are close to the result.\nGoodbye."}},"block_3":{"type":"link","properties":{"text":"Open deal","bold":true,"action":{"type":"redirect","uri":"/crm/deal/details/123/"}}},"block_4":{"type":"withTitle","properties":{"title":"Title","block":{"type":"text","properties":{"value":"Some value"}}}}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.layout.blocks.set
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"entityId":4,"timelineId":8,"layout":{"blocks":{"block_1":{"type":"text","properties":{"value":"Hello!\nWe are starting.","multiline":true,"bold":true,"color":"base_90"}},"block_2":{"type":"largeText","properties":{"value":"Hello!\nWe are starting.\nWe are continuing.\nWe are still working on this.\nWe are continuing.\nWe are close to the result.\nGoodbye."}},"block_3":{"type":"link","properties":{"text":"Open deal","bold":true,"action":{"type":"redirect","uri":"/crm/deal/details/123/"}}},"block_4":{"type":"withTitle","properties":{"title":"Title","block":{"type":"text","properties":{"value":"Some value"}}}}}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.layout.blocks.set
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.layout.blocks.set'
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
timelineId
:
8
,
// ID of the timeline record linked to this deal
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
'crm.timeline.layout.blocks.set'
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
'timelineId'
=>
8
, // ID of the timeline record linked to this deal
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
'Error setting timeline layout blocks: '
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
'crm.timeline.layout.blocks.set'
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
timelineId
:
8
,
// ID of the timeline record linked to this deal
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
'crm.timeline.layout.blocks.set'
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
'timelineId'
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
If the timeline record contains more than one set of additional content blocks, they will be displayed in the order they were added.
In the HTML layout, it is explicitly highlighted with data attributes which application added the set of additional content blocks:
data-app-name
: application name,
data-rest-client-id
: application identifier.
Response Handling
Response Handling
HTTP status:
200
Returns
{ success: true }
in case of successful recording of the set of additional content blocks, otherwise
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
"Method call is only possible in the context of a REST application"
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
Method call is only possible in the context of a REST application
OWNER_NOT_FOUND
The element to which the timeline record is linked was not found
NOT_FOUND
Timeline record not found
ACCESS_DENIED
Access denied
UNSUITABLE_TIMELINE_ITEM
The type of timeline record is not suitable for adding a set of additional content blocks
FIELD_IS_REQUIRED
The
blocks
field in
RestAppLayoutDto
must be filled.
The method also returns errors related to incorrect structure of the content block set. Details can be found in the error message.
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
Get a set of additional content blocks for the timeline record crm.timeline.layout.blocks.get
Delete a set of additional content blocks for the timeline record crm.timeline.layout.blocks.delete
Example Application with Additional Content Blocks
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Retrieve a Set of Additional Content Blocks

---

## Get a set of additional content blocks for the timeline record crm.timeline.layout.blocks.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/layout-blocks/crm-timeline-layout-blocks-get

Get a set of additional content blocks for the timeline record crm.timeline.layout.blocks.get | Bitrix24 REST API and Marketplace Applications
Get a set of additional content blocks for the timeline record crm.timeline.layout.blocks.get
Get a set of additional content blocks for the timeline record crm.timeline.layout.blocks.get
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
crm.timeline.layout.blocks.get
retrieves a set of additional content blocks for a timeline record.
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
Identifier of the CRM object type to which the timeline record is linked
entityId
*
integer
Identifier of the CRM object to which the timeline record is linked
timelineId
*
integer
Identifier of the timeline record
Code Examples
Code Examples
Retrieve a set of additional content blocks for the timeline record with
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
'{"entityTypeId":2,"entityId":4,"timelineId":8}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.layout.blocks.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"entityId":4,"timelineId":8,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.layout.blocks.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.layout.blocks.get'
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
timelineId
:
8
,
// ID of the timeline record linked to this deal
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
'crm.timeline.layout.blocks.get'
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
'timelineId'
=>
8
, // ID of the timeline record linked to this deal
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
'Error getting timeline layout blocks: '
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
'crm.timeline.layout.blocks.get'
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
timelineId
:
8
,
// ID of the timeline record linked to this deal
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
'crm.timeline.layout.blocks.get'
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
'timelineId'
=>
8
,
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
The element to which the timeline record is linked was not found
NOT_FOUND
The timeline record was not found
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
Set a set of additional content blocks in the timeline record crm.timeline.layout.blocks.set
Delete a set of additional content blocks for the timeline record crm.timeline.layout.blocks.delete
Example Application with Additional Content Blocks
Copied
Was the article helpful?
Yes
No
Previous
Install a Set of Additional Content Blocks
Next
Delete a Set of Additional Content Blocks

---

## Delete a set of additional content blocks for the timeline record crm.timeline.layout.blocks.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/layout-blocks/crm-timeline-layout-blocks-delete

Delete a set of additional content blocks for the timeline record crm.timeline.layout.blocks.delete | Bitrix24 REST API and Marketplace Applications
Delete a set of additional content blocks for the timeline record crm.timeline.layout.blocks.delete
Delete a set of additional content blocks for the timeline record crm.timeline.layout.blocks.delete
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
crm.timeline.layout.blocks.delete
removes a set of additional content blocks for a timeline record.
Within the application, you can only delete the set of additional content blocks that was installed through this application.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the entity type to which the timeline record is linked
entityId
*
integer
Identifier of the entity to which the timeline record is linked
timelineId
*
integer
Identifier of the timeline record
Code Examples
Code Examples
Delete a set of additional content blocks for the timeline record with
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
'{"entityTypeId":2,"entityId":4,"timelineId":8}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.layout.blocks.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"entityId":4,"timelineId":8,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.layout.blocks.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.layout.blocks.delete'
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
timelineId
:
8
,
// ID of the timeline record linked to this deal
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
'crm.timeline.layout.blocks.delete'
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
'timelineId'
=>
8
, // ID of the timeline record linked to this deal
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
'Error deleting timeline layout block: '
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
'crm.timeline.layout.blocks.delete'
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
timelineId
:
8
,
// ID of the timeline record linked to this deal
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
'crm.timeline.layout.blocks.delete'
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
'timelineId'
=>
8
,
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
if the set of additional content blocks was successfully deleted, otherwise
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
The element to which the timeline record is linked was not found
NOT_FOUND
The timeline record or the set of additional content blocks was not found
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
Set a set of additional content blocks in the timeline record crm.timeline.layout.blocks.set
Get a set of additional content blocks for the timeline record crm.timeline.layout.blocks.get
Example Application with Additional Content Blocks
Copied
Was the article helpful?
Yes
No
Previous
Retrieve a Set of Additional Content Blocks
Next
Example Application with Additional Content Blocks

---

## Example Application with Additional Content Blocks

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/layout-blocks/content-blocks-test-app

Example Application with Additional Content Blocks | Bitrix24 REST API and Marketplace Applications
Example Application with Additional Content Blocks
Example Application with Additional Content Blocks
<?php
header
(
'Content-Type: text/html; charset=UTF-8'
);
$placementOptions
=
json_decode
(
$_REQUEST
[
'PLACEMENT_OPTIONS'
] ??
''
,
true
);
$forceMode
= (
$placementOptions
[
'force_mode'
] ??
null
) ===
'Y'
;
?>
<!DOCTYPE html>
<html>
<head>
<meta charset=
"utf-8"
/>
<link href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css"
rel=
"stylesheet"
>
<script src=
"https://cdn.jsdelivr.net/npm/jsoneditor@9.9.2/dist/jsoneditor.min.js"
></script>
<link href=
"https://cdn.jsdelivr.net/npm/jsoneditor@9.9.2/dist/jsoneditor.min.css"
rel=
"stylesheet"
>
<script src=
"//api.bitrix24.com/api/v1/"
></script>
</head>
<body>
<div
class
="
container
-
fluid
">
<
form
id
="
form
"
class
="
mt
-3
md
-3">
<
div
class
="
row
">
<
div
class
="
col
-8">
<
div
class
="
mb
-3">
<
div
class
="
d
-
flex
flex
-
row
gap
-3">
<
label
class
="
form
-
label
h3
">
Layout
JSON
</
label
>
<
div
id
="
content_block_presets
"
class
="
d
-
flex
flex
-
row
gap
-2"></
div
>
</
div
>
<
div
id
="
json_editor
"
style
="
height
: 510
px
"></
div
>
<
input
type
="
hidden
"
id
="
layout
"
value
="
{}
">
</div>
</div>
<div class="
col-
4
" id="
parameters
">
<label class="
form-label h3
">Parameters</label>
<hr class="
mt-
0
">
<div class="
vstack gap-
3
">
<div class="
form-group
">
<label for="
entity_type_id
">Parent Entity</label>
<select id="
entity_type_id
" name="
entityTypeId
" class="
form-select
">
<option value="
2
" selected>[2] Deal</option>
<option value="
1
">[1] Lead</option>
<option value="
3
">[3] Contact</option>
<option value="
4
">[4] Company</option>
<option value="
7
">[7] Estimate</option>
<option value="
31
">[31] Invoice </option>
</select>
</div>
<div class="
form-group
">
<label for="
entity_id
">Parent Entity ID</label>
<input id="
entity_id
" name="
entityId
" type="
text
" class="
form-control
">
</div>
<div class="
form-group
">
<label for="
item_type_id
" class="
text-truncate
">Adding configurable blocks to:</label>
<select name="
itemTypeId
" id="
item_type_id
" class="
form-select
" required>
<option value="
1
" selected>CRM Activity</option>
<option value="
2
">Timeline Record</option>
</select>
</div>
<?php if (!
$forceMode
): ?>
<button id="
get_items_button
" type="
button
" class="
btn btn-outline-dark btn-sm
">Find</button>
<?php endif; ?>
<div class="
form-group
">
<label for="
item_id
">CRM Activity:</label>
<?php if (
$forceMode
): ?>
<input id="
item_id
" name="
itemId
" type="
text
" class="
form-control
">
<?php else: ?>
<select name="
itemId
" id="
item_id
" class="
form-select
"></select>
<?php endif; ?>
</div>
<button id="
get_button
" type="
button
" class="
btn btn-outline-dark btn-sm
">Get</button>
<button id="
set_button
" type="
button
" class="
btn btn-outline-dark btn-sm
">Set</button>
<button id="
delete_button
" type="
button
" class="
btn btn-outline-danger btn-sm
">Delete</button>
</div>
</div>
</div>
</form>
</div>
<div class="
container-fluid
" id="
alert_container
"></div>
</body>
</html>
<script>
const ITEM_ACTIVITY = 1;
const ITEM_TIMELINE = 2;
const ALLOWED_ITEM_TYPES = [
ITEM_ACTIVITY,
ITEM_TIMELINE,
];
const METHODS_MAP = {
[ITEM_ACTIVITY]: {
get: 'crm.activity.layout.blocks.get',
set: 'crm.activity.layout.blocks.set',
delete: 'crm.activity.layout.blocks.delete',
itemField: 'activityId',
},
[ITEM_TIMELINE]: {
get: 'crm.timeline.layout.blocks.get',
set: 'crm.timeline.layout.blocks.set',
delete: 'crm.timeline.layout.blocks.delete',
itemField: 'timelineId',
},
};
class ConfigurableTimelineBlocks {
#jsonEditor;
#statusContainer;
#contentBlockPresets;
#isForceMode = false;
// fields
#entityTypeIdNode;
#entityIdNode;
#itemTypeIdNode;
#itemIdNode;
// buttons
#getButton;
#setButton;
#deleteButton;
#getItemsButton
constructor(
jsonEditor,
statusContainer,
contentBlockPresets,
) {
this.#jsonEditor = jsonEditor;
this.#statusContainer = statusContainer;
this.#contentBlockPresets = contentBlockPresets;
this.renderJSONLayoutActions();
this.fetchProperties();
this.bindEvents();
this.loadDynamicTypes();
}
fetchProperties() {
this.#entityTypeIdNode = document.getElementById('entity_type_id');
this.#entityIdNode = document.getElementById('entity_id');
this.#itemTypeIdNode = document.getElementById('item_type_id');
this.#itemIdNode = document.getElementById('item_id');
this.#getButton = document.getElementById('get_button');
this.#setButton = document.getElementById('set_button');
this.#deleteButton = document.getElementById('delete_button');
this.#getItemsButton = !this.#isForceMode ? document.getElementById('get_items_button') : null;
}
bindEvents() {
this.#getButton.onclick = this.getAction.bind(this);
this.#setButton.onclick = this.setAction.bind(this);
this.#deleteButton.onclick = this.deleteAction.bind(this);
if (this.#getItemsButton)
{
this.#getItemsButton.onclick = this.getItemsAction.bind(this);
this.#itemTypeIdNode.onchange = () => {
this.#itemIdNode.innerHTML = '';
const label = document.querySelector(`[for="
item_id
"]`);
label.textContent = this.getItemTypeId() === ITEM_ACTIVITY ? 'CRM Activity' : 'Timeline Record';
};
}
}
renderJSONLayoutActions() {
const contentBlockPresetsContainer = document.getElementById('content_block_presets');
if (!contentBlockPresetsContainer) {
return;
}
contentBlockPresetsContainer.innerHTML = '';
this.#contentBlockPresets.forEach((contentBlockPreset) => {
const button = document.createElement('button');
button.classList = 'btn btn-link btn-sm text-secondary';
button.innerText = contentBlockPreset.getTitle();
button.type = 'button';
button.onclick = () => {
let json = this.#jsonEditor.get();
if (!json.blocks) {
json.blocks = {};
}
const length = Object.keys(json?.blocks).length;
json.blocks[`${length + 1}`] = contentBlockPreset.getValue();
this.#jsonEditor.set(json);
return false;
};
contentBlockPresetsContainer.append(button);
});
const clearButton = document.createElement('button');
clearButton.innerText = 'Clear';
clearButton.classList = 'btn btn-link btn-sm text-danger';
clearButton.type = 'button';
clearButton.onclick = () => {
this.#jsonEditor.set({});
};
contentBlockPresetsContainer.append(clearButton);
}
loadDynamicTypes()
{
BX24.callMethod('crm.type.list', {}, (result) => {
const types = result?.answer?.result?.types || [];
types.forEach((item) => {
const option = document.createElement("
option
");
option.value = item.entityTypeId;
option.innerText = `[${item.id}] ${item.title}`;
this.#entityTypeIdNode.append(option);
})
});
}
loading()
{
this.#entityTypeIdNode.disabled = true;
this.#entityIdNode.disabled = true;
this.#itemTypeIdNode.disabled = true;
this.#itemIdNode.disabled = true;
this.#getButton.disabled = true;
this.#setButton.disabled = true;
this.#deleteButton.disabled = true;
}
stopLoading()
{
this.#entityTypeIdNode.disabled = false;
this.#entityIdNode.disabled = false;
this.#itemTypeIdNode.disabled = false;
this.#itemIdNode.disabled = false;
this.#getButton.disabled = false;
this.#setButton.disabled = false;
this.#deleteButton.disabled = false;
}
getItemsAction()
{
if (this.#isForceMode)
{
return;
}
if (!this.validateEntityTypeIdAndEntityId())
{
return;
}
if (this.getItemTypeId() === ITEM_ACTIVITY)
{
const data = {
select: ['*'],
filter: {
'OWNER_TYPE_ID': this.getEntityTypeId(),
'OWNER_ID': this.getEntityId(),
},
};
const callback = (result) => {
if (result.error())
{
this.renderDangerAlert(result.error());
return;
}
const activities = result.data();
this.#itemIdNode.innerHTML = '';
activities.forEach((activity) => {
const option = document.createElement('option');
option.innerText = `[${activity.ID}] ${activity.SUBJECT} | ${activity.PROVIDER_ID}`;
option.value = activity.ID;
this.#itemIdNode.append(option);
});
};
BX24.callMethod('crm.activity.list', data, callback);
return;
}
const data = {
select: ['*'],
filter: {
'bindings': {
'entityTypeId': this.getEntityTypeId(),
'entityId': this.getEntityId(),
},
},
};
const callback = (result) => {
if (result.error())
{
this.renderDangerAlert(result.error());
return;
}
const items = result.data().items;
items.forEach((item) => {
let option = document.createElement('option');
const title = item?.layout?.header?.title ?? 'Undefined';
const id = item.id;
option.value = id;
option.innerText = `[${id}] ${title}`;
this.#itemIdNode.append(option);
});
};
BX24.callMethod('crm.timeline.historyitem.list', data, callback);
}
getAction()
{
const isValid = this.validateFieldsWithAlerts();
if (!isValid)
{
return;
}
const method = this.getMethod('get');
const data = this.getData();
const callback = (result) => {
this.stopLoading();
if (result.error())
{
this.renderDangerAlert(result.error());
return;
}
this.#jsonEditor.set(result.data().layout ?? {});
this.renderSuccessAlert("
Done, the result is just above ;)
");
};
this.loading();
BX24.callMethod(method, data, callback);
}
setAction()
{
const isValid = this.validateFieldsWithAlerts();
if (!isValid)
{
return;
}
const method = this.getMethod('set');
const data = {
...this.getData(),
layout: this.#jsonEditor.get(),
};
const callback = (result) => {
this.stopLoading();
if (result.error())
{
this.renderDangerAlert(result.error());
return;
}
this.renderSuccessAlert("
Additional content blocks have been successfully set ;)
");
};
this.loading();
BX24.callMethod(method, data, callback);
}
deleteAction()
{
const isValid = this.validateFieldsWithAlerts();
if (!isValid)
{
return;
}
const method = this.getMethod('delete');
const data = this.getData();
const callback = (result) => {
this.stopLoading();
if (result.error())
{
this.renderDangerAlert(result.error());
return;
}
this.renderSuccessAlert("
Additional content blocks have been successfully deleted ;)
");
this.#jsonEditor.set({});
};
this.loading();
BX24.callMethod(method, data, callback);
}
validateFieldsWithAlerts()
{
if (!this.validateEntityTypeIdAndEntityId())
{
return false;
}
const itemId = this.getItemId();
if (!itemId)
{
alert('Enter the ID of the CRM Activity/Timeline Record');
this.#itemIdNode.focus();
return false;
}
return true;
}
validateEntityTypeIdAndEntityId()
{
const entityId = this.getEntityId();
if (!entityId)
{
alert('Enter the ID of the Parent Entity');
this.#entityIdNode.focus();
return false;
}
if (!ALLOWED_ITEM_TYPES.includes(this.getItemTypeId()))
{
alert('Select a valid value for the entity type to which the configurable blocks will be added');
this.#itemTypeIdNode.focus();
return false;
}
return true;
}
getData()
{
return {
entityTypeId: this.getEntityTypeId(),
entityId: this.getEntityId(),
[this.getItemFieldName()]: this.getItemId(),
};
}
getMethod(method)
{
return METHODS_MAP[this.getItemTypeId()][method];
}
getEntityTypeId()
{
return Number.parseInt(this.#entityTypeIdNode.value, 10);
}
getEntityId()
{
return Number.parseInt(this.#entityIdNode.value, 10);
}
getItemTypeId()
{
return Number.parseInt(this.#itemTypeIdNode.value, 10);
}
getItemId()
{
return Number.parseInt(this.#itemIdNode.value, 10);
}
getItemFieldName()
{
return METHODS_MAP[this.getItemTypeId()].itemField;
}
renderAlert(message, classList)
{
const alert = document.createElement('div');
alert.className = classList;
alert.setAttribute('role', 'alert');
const time = (new Date()).toLocaleTimeString();
alert.innerText = `[${time}] ${message}`;
this.#statusContainer.innerHTML = '';
this.#statusContainer.append(alert);
}
renderDangerAlert(message)
{
this.renderAlert(message, 'alert alert-danger');
}
renderSuccessAlert(message)
{
this.renderAlert(message, 'alert alert-success')
}
}
class ContentBlockPreset
{
#title;
#value;
constructor(title, value) {
this.#title = title;
this.#value = value;
}
getTitle(){ return this.#title; }
getValue(){ return this.#value; }
}
const presets = [
new ContentBlockPreset('Text', {
type: "
text
",
properties: {
value: "
Hello!\nWe are starting.
",
multiline: true,
bold: true,
color: "
base_90
"
}
}),
new ContentBlockPreset('Large text', {
type: "
largeText
",
properties: {
value: "
Hello!\nWe are starting.\nWe are continuing.\nWe are still working on this.\nWe are continuing.\nWe are close to the result.\nGoodbye.
"
}
}),
new ContentBlockPreset('Link', {
type: "
link
",
properties: {
text: "
Open Deal
",
action: {
type: "
redirect
",
uri: "
/crm/deal/details/
123
/
"
},
bold: true
}
}),
new ContentBlockPreset('With title', {
type: "
withTitle
",
properties: {
title: "
Title
",
block: {
type: "
text
",
properties: {
value: "
Some value
"
}
}
}
}),
new ContentBlockPreset('With title (inline)', {
type: "
withTitle
",
properties: {
title: "
Title
2
",
block: {
type: "
link
",
properties: {
text: "
Open Deal
",
action: {
type: "
redirect
",
uri: "
/crm/deal/details/
123
/
"
}
}
},
inline: true
}
}),
new ContentBlockPreset('Line of blocks', {
type: "
lineOfBlocks
",
properties: {
blocks: {
text: {
type: "
text
",
properties: {
value: "
Some text
"
}
},
link: {
type: "
link
",
properties: {
text: "
link
",
action: {
type: "
redirect
",
uri: "
/crm/deal/details/
123
/
"
}
}
},
boldText: {
type: "
text
",
properties: {
value: "
bold text
",
bold: true
}
}
}
}
}),
new ContentBlockPreset('Deadline', {
type: "
deadline
",
properties: {
readonly: false
}
}),
];
document.addEventListener("
DOMContentLoaded
", () => {
const alertContainer = document.getElementById('alert_container');
const jsonEditor = new JSONEditor(document.getElementById('json_editor'), {
mode: 'code',
});
new ConfigurableTimelineBlocks(
jsonEditor,
alertContainer,
presets,
);
});
</script>
Was the article helpful?
Yes
No
Previous
Delete a Set of Additional Content Blocks
Next
Overview of Methods

---

## Actions with Records in the Timeline: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/actions/index

Actions with Records in the Timeline: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Connection with CRM Entities
Actions with Records in the Timeline: Overview of Methods
Connection with CRM Entities
Overview of Methods
In the timeline of a CRM entity, you can pin 7 records. Pinned records will be displayed simultaneously under the form for creating a new activity and in their chronological place in the timeline.
Connection with CRM Entities
Connection with CRM Entities
Comments.
Use the method
crm.timeline.comment.add
or
crm.timeline.comment.list
to obtain the ID of the timeline record.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: any user
Method
Description
crm.timeline.item.pin
Pins a record in the timeline
crm.timeline.item.unpin
Unpins a record in the timeline
Copied
Was the article helpful?
Yes
No
Previous
Example Application with Additional Content Blocks
Next
Pin a Record in the Timeline

---

## Pinning an Item in the Timeline crm.timeline.item.pin

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/actions/crm-timeline-item-pin

Pinning an Item in the Timeline crm.timeline.item.pin | Bitrix24 REST API and Marketplace Applications
Method Parameters
Pinning an Item in the Timeline crm.timeline.item.pin
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
crm.timeline.item.pin
pins an item in the timeline.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the timeline item, for example
999
. You can obtain the id using the method
crm.timeline.comment.list
ownerTypeId
*
integer
Identifier of the CRM object type
to which the item is linked, for example
2
for a deal
ownerId
*
integer
Identifier of the CRM element to which the item is linked, for example
10
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
'{"id": 999, "ownerTypeId": 2, "ownerId": 10}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.item.pin
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"ownerTypeId":2,"ownerId":10,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.item.pin
try
{
const
response =
await
$b24.
callMethod
(
"crm.timeline.item.pin"
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
10
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
'crm.timeline.item.pin'
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
10
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
'Error pinning timeline item: '
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
"crm.timeline.item.pin"
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
10
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
'crm.timeline.item.pin'
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
10
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
null
Result of the operation. Always returns
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
0
Only three events can be added to favorites
100
Required fields are missing
ACCESS_DENIED
Insufficient permissions to perform the operation
NOT_FOUND
Item not found
OWNER_NOT_FOUND
Owner of the item not found
CAN_NOT_CHANGE_PINNED
Unable to perform the operation
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
Unpin Timeline Item in crm.timeline.item.unpin
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Unpin Timeline Record

---

## Unpin Timeline Item in crm.timeline.item.unpin

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/actions/crm-timeline-item-unpin

Unpin Timeline Item in crm.timeline.item.unpin | Bitrix24 REST API and Marketplace Applications
Method Parameters
Unpin Timeline Item in crm.timeline.item.unpin
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
crm.timeline.item.unpin
unpins a timeline item.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the timeline item, for example
999
. You can obtain the id using the method
crm.timeline.comment.list
ownerTypeId
*
integer
Identifier of the CRM object type
to which the item is linked, for example
2
for a deal
ownerId
*
integer
Identifier of the CRM entity to which the item is linked, for example
10
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
'{"id": 999, "ownerTypeId": 2, "ownerId": 10}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.item.unpin
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":999,"ownerTypeId":2,"ownerId":10,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.item.unpin
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.item.unpin'
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
10
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
'crm.timeline.item.unpin'
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
10
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
'Error unpinning timeline item: '
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
"crm.timeline.item.unpin"
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
10
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
'crm.timeline.item.unpin'
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
10
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
null
Result of the operation. Always returns
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
100
Required fields are missing
ACCESS_DENIED
Insufficient permissions to perform the operation
NOT_FOUND
Item not found
OWNER_NOT_FOUND
Owner of the item not found
CAN_NOT_CHANGE_PINNED
Unable to perform the operation
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
Pinning an Item in the Timeline crm.timeline.item.pin
Copied
Was the article helpful?
Yes
No
Previous
Pin a Record in the Timeline
Next
Overview of Methods

---

