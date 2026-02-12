---
description: 'CRM Automation: Triggers, automated solutions, call lists'
methods:
- crm.activity.delete
- crm.activity.list
- crm.automatedsolution.add
- crm.automatedsolution.delete
- crm.automatedsolution.fields
- crm.automatedsolution.get
- crm.automatedsolution.list
- crm.automatedsolution.update
- crm.automation.trigger
- crm.automation.trigger.
- crm.automation.trigger.add
- crm.automation.trigger.delete
- crm.automation.trigger.execute
- crm.automation.trigger.list
- crm.calllist.add
- crm.calllist.get
- crm.calllist.items.get
- crm.calllist.list
- crm.calllist.statuslist
- crm.calllist.update
- crm.deal.delete
- crm.deal.list
- crm.enum.ownertype
- crm.item.list
- crm.status.
- crm.type.get
- user.get
pages: 21
title: 'CRM Automation: Triggers, automated solutions, call lists'
---
# CRM Automation: Triggers, automated solutions, call lists
> CRM Automation: Triggers, automated solutions, call lists
> **21 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Call List: Overview of Methods](#call-list-overview-of-methods)
- [Create a New Call List crm.calllist.add](#create-a-new-call-list-crmcalllistadd)
- [Get Information About the Call List crm.calllist.get](#get-information-about-the-call-list-crmcalllistget)
- [Get the list of call participants crm.calllist.items.get](#get-the-list-of-call-participants-crmcalllistitems)
- [Get the list of call lists crm.calllist.list](#get-the-list-of-call-lists-crmcalllistlist)
- [Get the list of call statuses crm.calllist.statuslist](#get-the-list-of-call-statuses-crmcallliststatuslis)
- [Update Call List Composition crm.calllist.update](#update-call-list-composition-crmcalllistupdate)
- [Digital Workspaces](#digital-workspaces)
- [Create Digital Workspace crm.automatedsolution.add](#create-digital-workspace-crmautomatedsolutionadd)
- [Update Digital Workplace crm.automatedsolution.update](#update-digital-workplace-crmautomatedsolutionupdat)
- [Get data about the digital workplace by id crm.automatedsolution.get](#get-data-about-the-digital-workplace-by-id-crmauto)
- [Get a list of digital workspaces crm.automatedsolution.list](#get-a-list-of-digital-workspaces-crmautomatedsolut)
- [Delete Digital Workplace crm.automatedsolution.delete](#delete-digital-workplace-crmautomatedsolutiondelet)
- [Get fields of the digital workplace crm.automatedsolution.fields](#get-fields-of-the-digital-workplace-crmautomatedso)
- [Automation and Triggers](#automation-and-triggers)
- [Activate the crm.automation.trigger](#activate-the-crmautomationtrigger)
- [Overview of Methods](#overview-of-methods)
- [Add Trigger crm.automation.trigger.add](#add-trigger-crmautomationtriggeradd)
- [Execute the Trigger crm.automation.trigger.execute](#execute-the-trigger-crmautomationtriggerexecute)
- [Get the list of triggers crm.automation.trigger.list](#get-the-list-of-triggers-crmautomationtriggerlist)
- [Delete Trigger ctrigger.delete](#delete-trigger-ctriggerdelete)

---

## Call List: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/call-list/index

Call List: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Connection with Other Objects
Call List: Overview of Methods
Connection with Other Objects
How to Delete a Call List
Overview of Methods
A call list is a CRM activity from which multiple clients can be called consecutively. An employee works with a single activity that contains selected contacts or companies. The results of the calls will be automatically saved in the client cards:
in the attached call activity and its comments,
in the filled CRM form and fields of the card,
in the deal or invoice created from the call list.
Quick navigation:
all methods
User documentation:
Calling in Bitrix24
Connection with Other Objects
Connection with Other Objects
Contact
. To call multiple contacts, specify an array of
ID
contacts in the
creation
or
update
method of the call list. You can obtain the
ID
of contacts using the
crm.item.list
method with the parameter
entityTypeId = 3
.
Company
. To call multiple companies, specify an array of
ID
companies in the
creation
or
update
method of the call list. You can obtain the
ID
of companies using the
crm.item.list
method with the parameter
entityTypeId = 4
.
CRM Form
. During the call, the employee can fill in information about the client in the CRM form attached to the call list. After the call is completed, the form will be available in the client card, and the information from the form will be saved in the fields of the card. To attach a form to the call list, specify its
ID
in the
creation
or
update
method of the call list. The
ID
of the form can be found in the list of forms in Bitrix24 at
https://your-domain.com/crm/webform/
.
Directory
. The status of the call in the call list card is an element of the
directory
. To change the statuses of the call list, use the directory methods
crm.status.*
with the parameter
ENTITY_ID = CALL_LIST
.
User
. The call list is linked to a user by a numeric identifier in the
createdBy
field — who created it. You can obtain user data by identifier using the
user.get
method.
How to Delete a Call List
How to Delete a Call List
There is no method for deleting a call list among the call list methods. You can delete a call list by deleting the activity using the
crm.activity.delete
method.
Use the
crm.activity.list
method with a filter by the activity name
SUBJECT
. In the field value, specify
Call #ID
. Replace
ID
with the
ID
of the call list obtained from the
crm.calllist.add
or
crm.calllist.list
methods.
Pass the
ID
of the activity from the result to the deletion method
crm.activity.delete
.
How to Use Examples in Documentation
JS
PHP
BX24.js
PHP CRest
// callListMethod is recommended when you need to get the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.activity.list'
,
{
filter
: {
"SUBJECT"
:
"Call #13"
,
},
select
: [
"ID"
]
}
)
const
deals = response.
getData
() || []
if
(deals.
length
===
0
) {
console
.
log
(
"No activities found with the name 'Call #13'."
);
return
;
}
let
dealId = deals[
0
].
ID
;
await
$b24.
callMethod
(
'crm.activity.delete'
,
{
id
: dealId,
}
)
console
.
log
(
"Activity ID "
+ dealId +
" successfully deleted."
);
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.activity.list'
, {
filter
: {
"SUBJECT"
:
"Call #13"
,
},
select
: [
"ID"
]
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
if
(page.
length
===
0
) {
console
.
log
(
"No activities found with the name 'Call #13'."
);
return
;
}
let
dealId = page[
0
].
ID
;
await
$b24.
callMethod
(
'crm.activity.delete'
,
{
id
: dealId,
}
)
console
.
log
(
"Activity ID "
+ dealId +
" successfully deleted."
);
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
'crm.activity.list'
, {
filter
: {
"SUBJECT"
:
"Call #13"
,
},
select
: [
"ID"
]
},
0
)
const
deals = response.
getData
().
result
|| []
if
(deals.
length
===
0
) {
console
.
log
(
"No activities found with the name 'Call #13'."
);
return
;
}
let
dealId = deals[
0
].
ID
;
await
$b24.
callMethod
(
'crm.activity.delete'
,
{
id
: dealId,
}
)
console
.
log
(
"Activity ID "
+ dealId +
" successfully deleted."
);
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
'crm.activity.list'
,
[
'filter'
=> [
'SUBJECT'
=>
'Call #13'
,
],
'select'
=> [
'ID'
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
$deals
=
$result
->
data
();
// If there are no activities, exit
if
(
count
(
$deals
) ===
0
) {
echo
"No activities found with the name 'Call #13'."
;
return
;
}
// Get the ID of the first activity
$dealId
=
$deals
[
0
][
'ID'
];
// Call the delete method
$deleteResponse
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
$dealId
,
]
);
$deleteResult
=
$deleteResponse
->
getResponseData
()
->
getResult
();
if
(
$deleteResult
->
error
()) {
error_log
(
"Error deleting activity ID "
.
$dealId
.
": "
.
$deleteResult
->
error
());
}
else
{
echo
"Activity ID "
.
$dealId
.
" successfully deleted."
;
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
"crm.activity.list"
,
{
filter
: {
"SUBJECT"
:
"Call #13"
,
},
select
: [
"ID"
]
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
(result.
error
());
return
;
}
let
deals = result.
data
();
// If there are no activities, exit
if
(deals.
length
===
0
) {
console
.
log
(
"No activities found with the name 'Call #13'."
);
return
;
}
// Get the ID of the first activity
let
dealId = deals[
0
].
ID
;
// Call the delete method
BX24
.
callMethod
(
'crm.activity.delete'
,
{
id
: dealId,
},
function
(
deleteResult
) {
if
(deleteResult.
error
()) {
console
.
error
(
"Error deleting activity ID "
+ dealId +
": "
+ deleteResult.
error
());
}
else
{
console
.
log
(
"Activity ID "
+ dealId +
" successfully deleted."
);
}
}
);
}
);
<?php
require_once
(
'crest.php'
);
// 1. Get the list of activities by name
$result
=
CRest
::
call
(
'crm.deal.list'
,
[
'filter'
=> [
'TITLE'
=>
'Call #13'
],
'select'
=> [
'ID'
]
]
);
if
(
$result
[
'error'
]) {
echo
'Error: '
.
$result
[
'error_description'
];
exit
;
}
$deals
=
$result
[
'result'
];
// If there are no activities, exit
if
(
empty
(
$deals
)) {
echo
"No activities found with the name 'Call #13'.\n"
;
exit
;
}
// Get the ID of the first activity
$dealId
=
$deals
[
0
][
'ID'
];
// 2. Delete the activity by ID
$result
=
CRest
::
call
(
'crm.deal.delete'
,
[
'id'
=>
$dealId
]
);
if
(
$result
[
'error'
]) {
echo
"Error deleting activity ID
$dealId
: "
.
$result
[
'error_description'
] .
"\n"
;
}
else
{
echo
"Activity ID
$dealId
successfully deleted.\n"
;
}
Overview of Methods
Overview of Methods
Scope:
crm
Who can perform methods: user with permissions to read CRM elements
Method
Description
crm.calllist.add
Creates a new call list
crm.calllist.get
Returns information about the call list
crm.calllist.items.get
Returns participants of the call list
crm.calllist.list
Returns a list of all call lists
crm.calllist.statuslist
Returns a list of call statuses
crm.calllist.update
Updates the composition of the call list
Copied
Was the article helpful?
Yes
No
Previous
Unpin Timeline Record
Next
Create a New Call List

---

## Create a New Call List crm.calllist.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/call-list/crm-calllist-add

Create a New Call List crm.calllist.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create a New Call List crm.calllist.add
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
Who can execute the method: user with access permission to read CRM entities
The method
crm.calllist.add
creates a new call list.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ENTITY_TYPE
*
string
Type of the object:
CONTACT
— contact,
COMPANY
— company
ENTITIES
*
array
Array of
ID
of contacts or companies, which can be obtained using the
crm.item.list
method
WEBFORM_ID
integer
ID
of the CRM form that will be displayed in the call list form.
The
ID
can be found in the list of forms in Bitrix24 https://your-domain.com/crm/webform/
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
-d
'{"ENTITY_TYPE":"CONTACT","ENTITIES":[1,2,3],"WEBFORM_ID":5}'
\
https://**your_bitrix24**/rest/**user_id**/**webhook**/crm.calllist.add
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{"ENTITY_TYPE":"CONTACT","ENTITIES":[1,2,3],"WEBFORM_ID":5,"auth":"**put_access_token_here**"}'
\
https://**your_bitrix24**/rest/crm.calllist.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.calllist.add'
,
{
ENTITY_TYPE
:
'CONTACT'
,
ENTITIES
: [
9
,
17
,
19
],
WEBFORM_ID
:
1
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
'crm.calllist.add'
,
[
'ENTITY_TYPE'
=>
'CONTACT'
,
'ENTITIES'
=> [
9
,
17
,
19
],
'WEBFORM_ID'
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
'Error adding call list: '
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
"crm.calllist.add"
,
{
ENTITY_TYPE
:
"CONTACT"
,
ENTITIES
: [
9
,
17
,
19
],
WEBFORM_ID
:
1
},
function
(
result
) {
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
'crm.calllist.add'
,
[
'ENTITY_TYPE'
=>
'CONTACT'
,
'ENTITIES'
=> [
1
,
2
,
3
],
'WEBFORM_ID'
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
11
,
"time"
:
{
"start"
:
1752471668.062547
,
"finish"
:
1752471668.531711
,
"duration"
:
0.4691641330718994
,
"processing"
:
0.4174520969390869
,
"date_start"
:
"2025-07-14T08:41:08+02:00"
,
"date_finish"
:
"2025-07-14T08:41:08+02:00"
,
"operating_reset_at"
:
1752472268
,
"operating"
:
0.41742897033691406
}
}
Returned Data
Returned Data
Name
type
Description
result
integer
ID of the created call list
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
"Invalid parameters."
,
"error_description"
:
"Invalid parameters were provided."
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
400
Access denied
No permission to perform the operation
400
Invalid parameters
Invalid parameters were provided
400
Incorrect entity type
An unsupported object type was specified
400
Entities is not array
The
ENTITIES
parameter is not an array
400
Incorrect entities id
Invalid
ID
of elements were provided
403
You don't have access to these entities
No access to the specified elements
400
Incorrect webform id
Invalid
ID
of the CRM form
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
Get Information About the Call List crm.calllist.get
Get the list of call participants crm.calllist.items.get
Get the list of call lists crm.calllist.list
Get the list of call statuses crm.calllist.statuslist
Update Call List Composition crm.calllist.update
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get Information About the Call List

---

## Get Information About the Call List crm.calllist.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/call-list/crm-calllist-get

Get Information About the Call List crm.calllist.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Information About the Call List crm.calllist.get
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
crm.calllist.get
returns information about the call list by its identifier, without the list of participants.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ID
*
integer
Identifier of the call list
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
-d
'{"ID":123}'
\
https://**your_bitrix24**/rest/**user_id**/**webhook**/crm.calllist.get
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{"ID":123,"auth":"**put_access_token_here**"}'
\
https://**your_bitrix24**/rest/crm.calllist.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.calllist.get'
,
{
ID
:
123
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
'crm.calllist.get'
,
[
'ID'
=>
123
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
'Error getting call list: '
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
"crm.calllist.get"
,
{
ID
:
123
},
function
(
result
) {
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
'crm.calllist.get'
,
[
'ID'
=>
123
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
"ID"
:
"13"
,
"DATE_CREATE"
:
"2025-07-14 08:47:19"
,
"CREATED_BY_ID"
:
"29"
,
"WEBFORM_ID"
:
"1"
,
"ENTITY_TYPE_ID"
:
"3"
,
"ENTITY_TYPE"
:
"CONTACT"
}
,
"time"
:
{
"start"
:
1752472572.278248
,
"finish"
:
1752472572.332555
,
"duration"
:
0.054306983947753906
,
"processing"
:
0.004546165466308594
,
"date_start"
:
"2025-07-14T08:56:12+02:00"
,
"date_finish"
:
"2025-07-14T08:56:12+02:00"
,
"operating_reset_at"
:
1752473172
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
ID
integer
Identifier of the call list
DATE_CREATE
datetime
Date and time of call list creation
CREATED_BY_ID
integer
Identifier of the user who created the call list
WEBFORM_ID
integer
Identifier of the associated CRM form
ENTITY_TYPE_ID
integer
Identifier of the object type
ENTITY_TYPE
string
Type of the object
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
"Incorrect list id"
,
"error_description"
:
"An incorrect list identifier was provided."
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
400
Incorrect list id
Incorrect list identifier or the user does not have read access permission
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
Create a New Call List crm.calllist.add
Get the list of call participants crm.calllist.items.get
Get the list of call lists crm.calllist.list
Get the list of call statuses crm.calllist.statuslist
Update Call List Composition crm.calllist.update
Copied
Was the article helpful?
Yes
No
Previous
Create a New Call List
Next
Get Participants of the Call List

---

## Get the list of call participants crm.calllist.items.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/call-list/crm-calllist-items-get

Get the list of call participants crm.calllist.items.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of call participants crm.calllist.items.get
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
Who can execute the method: a user with read access permission to CRM entities
The method
crm.calllist.items.get
returns a list of participants, contacts, or companies, along with the call status.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
LIST_ID
*
integer
Identifier of the call list, which can be obtained using the methods
crm.calllist.add
and
crm.calllist.list
FILTER
object
Filter by the call status of the item:
{ STATUS: "status_code" }
.
You can get the status code values using the method
crm.calllist.statuslist
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
-d
'{"LIST_ID":13,"FILTER":{"STATUS":"IN_WORK"}}'
\
https://**your_bitrix24**/rest/**user_id**/**webhook**/crm.calllist.items.get
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{"LIST_ID":13,"FILTER":{"STATUS":"IN_WORK"},"auth":"**put_access_token_here**"}'
\
https://**your_bitrix24**/rest/crm.calllist.items.get
try
{
const
response =
await
$b24.
callMethod
(
"crm.calllist.items.get"
,
{
LIST_ID
:
13
,
FILTER
: {
STATUS
:
"IN_WORK"
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
'crm.calllist.items.get'
,
[
'LIST_ID'
=>
13
,
'FILTER'
=> [
'STATUS'
=>
'IN_WORK'
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
'Error getting call list items: '
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
"crm.calllist.items.get"
,
{
LIST_ID
:
13
,
FILTER
: {
STATUS
:
"IN_WORK"
}
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
'crm.calllist.items.get'
,
[
'LIST_ID'
=>
13
,
'FILTER'
=> [
'STATUS'
=>
'IN_WORK'
] ]
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
"ID"
:
9
,
"STATUS"
:
"IN_WORK"
,
"ENTITY_TYPE"
:
3
}
,
{
"ID"
:
17
,
"STATUS"
:
"IN_WORK"
,
"ENTITY_TYPE"
:
3
}
,
{
"ID"
:
19
,
"STATUS"
:
"IN_WORK"
,
"ENTITY_TYPE"
:
3
}
]
,
"time"
:
{
"start"
:
1752475017.529502
,
"finish"
:
1752475017.588903
,
"duration"
:
0.05940103530883789
,
"processing"
:
0.010075092315673828
,
"date_start"
:
"2025-07-14T09:36:57+02:00"
,
"date_finish"
:
"2025-07-14T09:36:57+02:00"
,
"operating_reset_at"
:
1752475617
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
Array of items with call statuses and object types
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
"Incorrect list id"
,
"error_description"
:
"An incorrect list identifier was provided."
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
400
Incorrect list id
Incorrect call list identifier
400
Incorrect status
Incorrect call status
403
Access denied
No access to list items
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
Create a New Call List crm.calllist.add
Get Information About the Call List crm.calllist.get
Get the list of call lists crm.calllist.list
Get the list of call statuses crm.calllist.statuslist
Update Call List Composition crm.calllist.update
Copied
Was the article helpful?
Yes
No
Previous
Get Information About the Call List
Next
Get a List of All Call Lists

---

## Get the list of call lists crm.calllist.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/call-list/crm-calllist-list

Get the list of call lists crm.calllist.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of call lists crm.calllist.list
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
Who can execute the method: user with read access permission for CRM elements
The method
crm.calllist.list
returns a list of call list activities.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
SELECT
array
Array of fields to retrieve. By default, all fields are returned.
List of fields to retrieve:
ID
,
DATE_CREATE
,
CREATED_BY_ID
,
WEBFORM_ID
,
ENTITY_TYPE_ID
FILTER
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
field_n
— name of the field by which the call list will be filtered
value_n
— filter value
List of fields for filtering:
ID
,
CREATED_BY_ID
,
WEBFORM_ID
,
ENTITY_TYPE_ID
.
An additional prefix can be assigned to the field to specify the filter behavior. Possible prefix values:
>=
— greater than or equal to,
>
— greater than,
<=
— less than or equal to,
<
— less than,
@
— IN, an array is passed as the value,
!@
— NOT IN, an array is passed as the value,
=
— equal, exact match, used by default,
!=
- not equal,
!
— not equal
ORDER
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
field_n
— name of the field by which the call list will be sorted
value_n
— value of type
string
, equal to:
ASC
— ascending sort
DESC
— descending sort
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST -H
"Content-Type: application/json"
-H
"Accept: application/json"
-d
'{"SELECT":["ID","CREATED_BY_ID"],"FILTER":{"ENTITY_TYPE_ID":3},"ORDER":{"ID":"DESC"}}'
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.calllist.list
curl -X POST -H
"Content-Type: application/json"
-H
"Accept: application/json"
-d
'{"SELECT":["ID","CREATED_BY_ID"],"FILTER":{"ENTITY_TYPE_ID":3},"ORDER":{"ID":"DESC"},"auth":"**put_access_token_here**"}'
https://**put_your_bitrix24_address**/rest/crm.calllist.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.calllist.list'
,
{
SELECT
: [
"ID"
,
"CREATED_BY_ID"
],
FILTER
: {
"ENTITY_TYPE_ID"
:
3
},
ORDER
: {
"ID"
:
"DESC"
}
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative retrieval using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.calllist.list'
, {
SELECT
: [
"ID"
,
"CREATED_BY_ID"
],
FILTER
: {
"ENTITY_TYPE_ID"
:
3
},
ORDER
: {
"ID"
:
"DESC"
} },
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. Suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.calllist.list'
, {
SELECT
: [
"ID"
,
"CREATED_BY_ID"
],
FILTER
: {
"ENTITY_TYPE_ID"
:
3
},
ORDER
: {
"ID"
:
"DESC"
} },
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
'crm.calllist.list'
,
[
'SELECT'
=> [
'ID'
,
'CREATED_BY_ID'
],
'FILTER'
=> [
'ENTITY_TYPE_ID'
=>
3
],
'ORDER'
=> [
'ID'
=>
'DESC'
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
'Error fetching call list: '
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
"crm.calllist.list"
,
{
SELECT
: [
"ID"
,
"CREATED_BY_ID"
],
FILTER
: {
"ENTITY_TYPE_ID"
:
3
},
ORDER
: {
"ID"
:
"DESC"
}
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
'crm.calllist.list'
,
[
'SELECT'
=> [
'ID'
,
'CREATED_BY_ID'
],
'FILTER'
=> [
'ENTITY_TYPE_ID'
=>
3
],
'ORDER'
=> [
'ID'
=>
'DESC'
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
[
{
"ID"
:
"13"
,
"CREATED_BY_ID"
:
"29"
}
,
{
"ID"
:
"9"
,
"CREATED_BY_ID"
:
"1"
}
,
{
"ID"
:
"3"
,
"CREATED_BY_ID"
:
"131"
}
,
{
"ID"
:
"1"
,
"CREATED_BY_ID"
:
"131"
}
]
,
"time"
:
{
"start"
:
1752475786.965766
,
"finish"
:
1752475787.035008
,
"duration"
:
0.06924200057983398
,
"processing"
:
0.016666889190673828
,
"date_start"
:
"2025-07-14T09:49:46+02:00"
,
"date_finish"
:
"2025-07-14T09:49:47+02:00"
,
"operating_reset_at"
:
1752476387
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
Root element of the response. Contains an array of objects with information about call lists.
The structure of fields depends on the
select
parameter
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
"Invalid parameters."
,
"error_description"
:
"Invalid parameters were provided."
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
400
Invalid parameters
Invalid parameters were provided
100
Unknown field definition "TITLE"
Unknown parameter "Field name"
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
Create a New Call List crm.calllist.add
Get Information About the Call List crm.calllist.get
Get the list of call participants crm.calllist.items.get
Get the list of call statuses crm.calllist.statuslist
Update Call List Composition crm.calllist.update
Copied
Was the article helpful?
Yes
No
Previous
Get Participants of the Call List
Next
Get a List of Call List Statuses

---

## Get the list of call statuses crm.calllist.statuslist

**Source:** https://apidocs.bitrix24.com/api-reference/crm/call-list/crm-calllist-statuslist

Get the list of call statuses crm.calllist.statuslist | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of call statuses crm.calllist.statuslist
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method
crm.calllist.statuslist
returns a list of call statuses.
To create a new status, modify, or delete an existing one, use the methods
crm.status.*
.
Method Parameters
Method Parameters
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
-d
'{}'
\
https://**your_bitrix24**/rest/**user_id**/**webhook**/crm.calllist.statuslist
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{"auth":"**put_access_token_here**"}'
\
https://**your_bitrix24**/rest/crm.calllist.statuslist
try
{
const
response =
await
$b24.
callMethod
(
"crm.calllist.statuslist"
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
'crm.calllist.statuslist'
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
'Error fetching call list status: '
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
"crm.calllist.statuslist"
,
{},
function
(
result
) {
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
'crm.calllist.statuslist'
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
"ID"
:
61
,
"NAME"
:
"In Progress"
,
"SORT"
:
10
,
"STATUS_ID"
:
"IN_WORK"
}
,
{
"ID"
:
63
,
"NAME"
:
"Successful"
,
"SORT"
:
20
,
"STATUS_ID"
:
"SUCCESS"
}
,
{
"ID"
:
65
,
"NAME"
:
"Wrong Number"
,
"SORT"
:
30
,
"STATUS_ID"
:
"WRONG_NUMBER"
}
,
{
"ID"
:
67
,
"NAME"
:
"Do Not Call Again"
,
"SORT"
:
40
,
"STATUS_ID"
:
"STOP_CALLING"
}
]
,
"time"
:
{
"start"
:
1752560909.614115
,
"finish"
:
1752560909.68214
,
"duration"
:
0.06802511215209961
,
"processing"
:
0.007961034774780273
,
"date_start"
:
"2025-07-15T09:28:29+02:00"
,
"date_finish"
:
"2025-07-15T09:28:29+02:00"
,
"operating_reset_at"
:
1752561509
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
Array of call statuses
(detailed description)
time
time
Information about the request execution time
Field Descriptions for result
Field Descriptions for result
Name
type
Description
ID
integer
Status identifier
NAME
string
Name
SORT
integer
Sort order
STATUS_ID
string
Status code, use in the method
crm.calllist.items.get
Error Handling
Error Handling
The method does not return errors.
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
Create a New Call List crm.calllist.add
Get Information About the Call List crm.calllist.get
Get the list of call participants crm.calllist.items.get
Get the list of call lists crm.calllist.list
Update Call List Composition crm.calllist.update
Copied
Was the article helpful?
Yes
No
Previous
Get a List of All Call Lists
Next
Update the Composition of the Call List

---

## Update Call List Composition crm.calllist.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/call-list/crm-calllist-update

Update Call List Composition crm.calllist.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Call List Composition crm.calllist.update
Method Parameters
Method Operation Features
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
The
crm.calllist.update
method allows you to add or remove participants from an existing call list and update the associated CRM form.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
LIST_ID
*
integer
Identifier of the call list
ENTITY_TYPE
*
string
Type of entity:
CONTACT
— contact,
COMPANY
— company
ENTITIES
*
array
Array of
ID
s of contacts or companies, which can be obtained using the
crm.item.list
method
WEBFORM_ID
integer
ID
of the CRM form that will be displayed in the call form.
The
ID
can be found in the list of forms in Bitrix24 https://your-domain.com/crm/webform/
Method Operation Features
Method Operation Features
The method overwrites the
ENTITIES
array. To add an element, include both current and new
ID
s in the request:
Current IDs: [1,2,3].
New IDs: [4].
Send: [1,2,3,4].
To remove an element, send only those
ID
s that should remain in the list:
Current IDs: [1,2,3].
Remove: [2].
Send: [1,3].
The method overwrites the
WEBFORM_ID
field. If the
WEBFORM_ID
field is not provided when calling the method, it will be cleared.
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
-d
'{"LIST_ID":123,"ENTITY_TYPE":"CONTACT","ENTITIES":[1,2,3],"WEBFORM_ID":5}'
\
https://**your_bitrix24**/rest/**user_id**/**webhook**/crm.calllist.update
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{"LIST_ID":123,"ENTITY_TYPE":"CONTACT","ENTITIES":[1,2,3],"WEBFORM_ID":5,"auth":"**put_access_token_here**"}'
\
https://**your_bitrix24**/rest/crm.calllist.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.calllist.update'
,
{
LIST_ID
:
123
,
ENTITY_TYPE
:
'CONTACT'
,
ENTITIES
: [
1
,
2
,
3
],
WEBFORM_ID
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
'crm.calllist.update'
,
[
'LIST_ID'
=>
123
,
'ENTITY_TYPE'
=>
'CONTACT'
,
'ENTITIES'
=> [
1
,
2
,
3
],
'WEBFORM_ID'
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
'Error updating call list: '
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
"crm.calllist.update"
,
{
LIST_ID
:
123
,
ENTITY_TYPE
:
"CONTACT"
,
ENTITIES
: [
1
,
2
,
3
],
WEBFORM_ID
:
5
},
function
(
result
) {
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
'crm.calllist.update'
,
[
'LIST_ID'
=>
123
,
'ENTITY_TYPE'
=>
'CONTACT'
,
'ENTITIES'
=> [
1
,
2
,
3
],
'WEBFORM_ID'
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
1752562914.533195
,
"finish"
:
1752562914.606445
,
"duration"
:
0.07325005531311035
,
"processing"
:
0.044027090072631836
,
"date_start"
:
"2025-07-15T10:01:54+02:00"
,
"date_finish"
:
"2025-07-15T10:01:54+02:00"
,
"operating_reset_at"
:
1752563514
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
Root element of the response, contains
true
in case of success
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
"Invalid parameters."
,
"error_description"
:
"Invalid parameters were provided."
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
400
Invalid parameters
Invalid parameters were provided
400
Incorrect entity type
Unsupported entity type specified
400
Entities is not array
The ENTITIES parameter is not an array
400
Incorrect entities id
Invalid IDs of elements were provided
400
Incorrect list id or access denied
Invalid list identifier or no access
400
Discrepancy between the type of call participants and incoming type
Mismatch between participant type and provided type
400
Incorrect webform id
Invalid ID of the CRM form
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
Create a New Call List crm.calllist.add
Get Information About the Call List crm.calllist.get
Get the list of call participants crm.calllist.items.get
Get the list of call lists crm.calllist.list
Get the list of call statuses crm.calllist.statuslist
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Call List Statuses
Next
Overview of Methods

---

## Digital Workspaces

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automated-solution/index

Digital Workspaces | Bitrix24 REST API and Marketplace Applications
Digital Workspaces
Digital Workspaces
Digital workspaces are a separate section for smart processes that are not tied to CRM. A workspace can consist of one or more processes. Each has its own cards, funnels, kanban stages, Automation rules, and other features.
On the account, you can find them in the section
Automation > Digital Workspaces > List of Digital Workspaces
.
You can learn more about digital workspaces at
helpdesk.bitrix24.com
.
Methods for managing digital workspaces:
Create Digital Workspace crm.automatedsolution.add
Update Digital Workplace crm.automatedsolution.update
Get data about the digital workplace by id crm.automatedsolution.get
Get a list of digital workspaces crm.automatedsolution.list
Delete Digital Workplace crm.automatedsolution.delete
Get fields of the digital workplace crm.automatedsolution.fields
The on-premise version of Bitrix24 is available starting from CRM version
24.300.0
.
Was the article helpful?
Yes
No
Previous
Delete a numberer
Next
Create a Digital Workspace

---

## Create Digital Workspace crm.automatedsolution.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automated-solution/crm-automated-solution-add

Create Digital Workspace crm.automatedsolution.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create Digital Workspace crm.automatedsolution.add
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
Who can execute the method: users with administrative access to the CRM section
This method will create a new digital workspace.
In the cloud, the maximum number of digital workspaces depends on the plan. In on-premise, the maximum number depends on technical limitations.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
Field values (detailed description provided below) for creating a digital workspace in the form of a structure:
"fields"
: {
"title"
:
"value"
,
"typeIds"
: []
}
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
title
*
string
The name of the digital workspace. The link to the corresponding section on the account will be built based on the title of the digital workspace.
typeIds
crm_dynamic_type.id[]
An array of identifiers of SPAs that need to be linked to this workspace.
If the SPA was previously linked to another workspace or to the CRM, it will disappear from there after being linked to the new workspace.
A digital workspace without SPAs will not be displayed in the left menu. However, it can be found in the list of digital workspaces.
Code Examples
Code Examples
How to Use Examples in Documentation
Create a digital workspace and immediately link SPAs to it
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
'{"fields":{"title":"HR","typeIds":[1,2,3]}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"title":"HR","typeIds":[1,2,3]},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.add
BX24
.
callMethod
(
'crm.automatedsolution.add'
,
{
"fields"
: {
"title"
:
"HR"
,
"typeIds"
: [
1
,
2
,
3
]
}
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
'crm.automatedsolution.add'
,
[
'fields'
=>
[
'title'
=>
'HR'
,
'typeIds'
=> [
1
,
2
,
3
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
Create a digital workspace without SPAs
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
'{"fields":{"title":"HR"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"title":"HR"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.add
BX24
.
callMethod
(
'crm.automatedsolution.add'
,
{
"fields"
: {
"title"
:
"HR"
}
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
'crm.automatedsolution.add'
,
[
'fields'
=>
[
'title'
=>
'HR'
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
"automatedSolution"
:
{
"id"
:
1
,
"title"
:
"HR"
,
"typeIds"
:
[
1
,
2
,
3
]
}
}
,
"time"
:
{
"start"
:
1715849396.642359
,
"finish"
:
1715849396.954623
,
"duration"
:
0.31226396560668945
,
"processing"
:
0.0068209171295166016
,
"date_start"
:
"2024-05-16T11:49:56+03:00"
,
"date_finish"
:
"2024-05-16T11:49:56+03:00"
,
"operating_reset_at"
:
1715849996
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
Root element of the response
automatedSolution
object
Object containing information about the added digital workspace
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
"BX_EMPTY_REQUIRED"
,
"error_description"
:
"The required field 'Title' is not filled"
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
LIMIT_EXCEEDED
The number of available digital workspaces has been exceeded
BX_EMPTY_REQUIRED
A required field is not filled
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
Digital Workspaces
Update Digital Workplace crm.automatedsolution.update
Get data about the digital workplace by id crm.automatedsolution.get
Get a list of digital workspaces crm.automatedsolution.list
Delete Digital Workplace crm.automatedsolution.delete
Get fields of the digital workplace crm.automatedsolution.fields
Copied
Was the article helpful?
Yes
No
Previous
Digital Workspaces
Next
Modify a Digital Workspace

---

## Update Digital Workplace crm.automatedsolution.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automated-solution/crm-automated-solution-update

Update Digital Workplace crm.automatedsolution.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Digital Workplace crm.automatedsolution.update
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
Who can execute the method: users with administrative access to the crm section
This method updates the existing settings of the digital workplace with the identifier
id
. If any of the fields are not provided, their values will remain unchanged.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the digital workplace. It can be obtained from the response of the method
crm.automatedsolution.add
(result.automatedSolution.id), which was called when adding the digital workplace, or
crm.automatedsolution.list
. You can also use the "Digital Workplaces" section in the Bitrix24 account — the
ID
column in the list of digital workplaces
fields
*
object
Field values (detailed description provided below) for creating a digital workplace in the following structure:
"fields"
: {
"title"
:
"value"
,
"typeIds"
: []
}
Parameter fields
Parameter fields
Name
type
Description
title
string
Title of the digital workplace.
Be careful when changing the
title
field. Since the link to the digital workplace is built based on the title, changing it will also change the link to the digital workplace
typeIds
crm_dynamic_type.id[]
Array of identifiers of SPAs that need to be linked to this workplace.
To change the list of linked SPAs, you need to pass the
typeIds
field with the desired set of SPAs.
Warning
Settings are completely overwritten. When changing the list of linked SPAs, you must pass the
typeIds
set in its entirety, or omit the
typeIds
key altogether
Code Examples
Code Examples
How to Use Examples in Documentation
Change the title of the digital workplace
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
'{"id":238,"fields":{"title":"HR & Customer Success"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":238,"fields":{"title":"HR & Customer Success"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.update
BX24
.
callMethod
(
'crm.automatedsolution.update'
,
{
"id"
:
238
,
"fields"
: {
"title"
:
"HR & Customer Success"
}
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
'crm.automatedsolution.update'
,
[
'id'
=>
238
,
'fields'
=>
[
'title'
=>
'HR & Customer Success'
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
Change the list of linked SPAs
Suppose the digital workplace with
id
=
267
had two SPAs linked — one with
id
=
14
, and the other with
id
=
158
. If we want the digital workplace to retain only one SPA, we pass the
typeIds
field containing only the desired SPAs:
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
'{"id":238,"fields":{"typeIds":[14]}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":238,"fields":{"typeIds":[14]},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.update
BX24
.
callMethod
(
'crm.automatedsolution.update'
,
{
"id"
:
238
,
"fields"
: {
"typeIds"
: [
14
]
}
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
'crm.automatedsolution.update'
,
[
'id'
=>
238
,
'fields'
=>
[
'typeIds'
=> [
14
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
Unlink all SPAs
To unlink all SPAs from the digital workplace, you need to pass an empty array as
typeIds
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
'{"id":238,"fields":{"typeIds":[]}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":238,"fields":{"typeIds":[]},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.update
BX24
.
callMethod
(
'crm.automatedsolution.update'
,
{
"id"
:
238
,
"fields"
: {
"typeIds"
: []
}
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
'crm.automatedsolution.update'
,
[
'id'
=>
238
,
'fields'
=>
[
'typeIds'
=> []
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
"automatedSolution"
:
{
"id"
:
1
,
"title"
:
"HR"
,
"typeIds"
:
[
1
,
2
,
3
]
}
}
,
"time"
:
{
"start"
:
1715849396.642359
,
"finish"
:
1715849396.954623
,
"duration"
:
0.31226396560668945
,
"processing"
:
0.0068209171295166016
,
"date_start"
:
"2024-05-16T11:49:56+03:00"
,
"date_finish"
:
"2024-05-16T11:49:56+03:00"
,
"operating_reset_at"
:
1715849996
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
Root element of the response
automatedSolution
object
Object containing information about the updated digital workplace
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
"BX_EMPTY_REQUIRED"
,
"error_description"
:
"Required field is not filled"
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
BX_EMPTY_REQUIRED
Required field is not filled
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
Digital Workspaces
Create Digital Workspace crm.automatedsolution.add
Get data about the digital workplace by id crm.automatedsolution.get
Get a list of digital workspaces crm.automatedsolution.list
Delete Digital Workplace crm.automatedsolution.delete
Get fields of the digital workplace crm.automatedsolution.fields
Copied
Was the article helpful?
Yes
No
Previous
Create a Digital Workspace
Next
Retrieve Digital Workspace Data by ID

---

## Get data about the digital workplace by id crm.automatedsolution.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automated-solution/crm-automated-solution-get

Get data about the digital workplace by id crm.automatedsolution.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get data about the digital workplace by id crm.automatedsolution.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Exploring
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
The method returns information about the digital workplace with the identifier
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
Identifier of the digital workplace
Code Examples
Code Examples
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
'{"id":393}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":393,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.automatedsolution.get'
,
{
'id'
:
393
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
'crm.automatedsolution.get'
,
[
'id'
=>
393
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
'Error getting automated solution: '
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
"crm.automatedsolution.get"
,
{
"id"
:
393
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
'crm.automatedsolution.get'
,
[
'id'
=>
393
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
"automatedSolution"
:
{
"id"
:
393
,
"title"
:
"HR"
,
"typeIds"
:
[
4
,
9
,
77
,
157
,
225
]
}
}
,
"time"
:
{
"start"
:
1715849396.642359
,
"finish"
:
1715849396.954623
,
"duration"
:
0.31226396560668945
,
"processing"
:
0.0068209171295166016
,
"date_start"
:
"2024-05-16T11:49:56+02:00"
,
"date_finish"
:
"2024-05-16T11:49:56+02:00"
,
"operating_reset_at"
:
1715849996
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
Root element of the response
automatedSolution
object
Information about the digital workplace
time
time
Information about the request execution time
Object
automatedSolution
:
Name
type
Description
id
integer
Unique identifier of the digital workplace
title
string
Name of the digital workplace
typeIds
array
Identifiers of the smart processes linked to the workplace
Warning
Id
of the digital workplace and
id
of the
customSection
structures from the method
crm.type.get
do not match due to different storage organization
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
"Digital workplace with such id not found"
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
Digital workplace with such
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
Continue Exploring
Continue Exploring
Digital Workspaces
Create Digital Workspace crm.automatedsolution.add
Update Digital Workplace crm.automatedsolution.update
Get a list of digital workspaces crm.automatedsolution.list
Delete Digital Workplace crm.automatedsolution.delete
Get fields of the digital workplace crm.automatedsolution.fields
Copied
Was the article helpful?
Yes
No
Previous
Modify a Digital Workspace
Next
Get a List of Digital Workspaces

---

## Get a list of digital workspaces crm.automatedsolution.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automated-solution/crm-automated-solution-list

Get a list of digital workspaces crm.automatedsolution.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of digital workspaces crm.automatedsolution.list
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
Who can execute the method: users with administrative access to the CRM section
The method will return an array of digital workspace settings. Each element of the array is a structure similar to the response from the request
crm.automatedsolution.get
.
Method Parameters
Method Parameters
Name
type
Description
order
object
List for sorting in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where the key is the field and the value is
ASC
or
DESC
. Available fields for sorting:
id
title
filter
object
Object for filtering selected digital workspaces in the format
{"field_1": "value_1", ... "field_N": "value_N"}
. Available fields for filtering:
id
title
The filter can have unlimited nesting and number of conditions. By default, all conditions are combined using
AND
. If you need to use
OR
, you can pass a special key
logic
with the value
OR
.
An additional prefix can be assigned to the key to specify the filter's behavior. Possible prefix values:
>=
— greater than or equal to
>
— greater than
<=
— less than or equal to
<
— less than
%
— LIKE, substring search. The
%
symbol in the filter value does not need to be passed. The search looks for the substring in any position of the string.
=%
— LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
"mol%"
— searching for values starting with "mol"
"%mol"
— searching for values ending with "mol"
"%mol%"
— searching for values where "mol" can be in any position.
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
— searching for values not starting with "mol"
"%mol"
— searching for values not ending with "mol"
"%mol%"
— searching for values where the substring "mol" is not present in any position.
!%=
— NOT LIKE (see description above)
=
— equals, exact match (used by default)
!=
- not equal
start
integer
This parameter is used for pagination control.
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
is the desired page number
Code Examples
Code Examples
Get all digital workspaces sorted by descending
id
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
'{"order":{"id":"DESC"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"id":"DESC"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.list
BX24
.
callMethod
(
"crm.automatedsolution.list"
,
{
"order"
: {
"id"
:
"DESC"
,
}
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
'crm.automatedsolution.list'
,
[
'order'
=> [
'id'
=>
'DESC'
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
Get all digital workspaces whose titles start with "HR"
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
'{"filter":{"%=title":"HR%"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":{"%=title":"HR%"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.list
BX24
.
callMethod
(
"crm.automatedsolution.list"
,
{
"filter"
: {
"%=title"
:
"HR%"
}
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
'crm.automatedsolution.list'
,
[
'filter'
=> [
'%=title'
=>
'HR%'
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
Get all digital workspaces whose titles start with "HR" or "Customer" and
id
greater than
100
, sorted by title
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
'{"order":{"title":"ASC"},"filter":{">id":100,"0":{"logic":"OR","0":{"%=title":"HR%"},"1":{"%=title":"Customer%"}}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"title":"ASC"},"filter":{">id":100,"0":{"logic":"OR","0":{"%=title":"HR%"},"1":{"%=title":"Customer%"}}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.list
BX24
.
callMethod
(
"crm.automatedsolution.list"
,
{
"order"
: {
"title"
:
"ASC"
},
"filter"
: {
">id"
:
100
,
"0"
: {
"logic"
:
"OR"
,
"0"
: {
"%=title"
:
"HR%"
},
"1"
: {
"%=title"
:
"Customer%"
}
}
}
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
'crm.automatedsolution.list'
,
[
'order'
=> [
'title'
=>
'ASC'
],
'filter'
=> [
'>id'
=>
100
,
'0'
=> [
'logic'
=>
'OR'
,
'0'
=> [
'%=title'
=>
'HR%'
],
'1'
=> [
'%=title'
=>
'Customer%'
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
HTTP status:
200
{
"result"
:
{
"automatedSolutions"
:
[
{
"id"
:
238
,
"title"
:
"HR"
,
"typeIds"
:
[
129
]
}
,
{
"id"
:
240
,
"title"
:
"Customer Success"
,
"typeIds"
:
[
]
}
,
{
"id"
:
267
,
"title"
:
"R&D"
,
"typeIds"
:
[
14
,
158
]
}
]
}
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
1715849396.642359
,
"finish"
:
1715849396.954623
,
"duration"
:
0.31226396560668945
,
"processing"
:
0.0068209171295166016
,
"date_start"
:
"2024-05-16T11:49:56+03:00"
,
"date_finish"
:
"2024-05-16T11:49:56+03:00"
,
"operating_reset_at"
:
1715849996
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
Root element of the response
automatedSolutions
object
Array of objects with information about selected payments
total
integer
Total number of records found
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
"ACCESS_DENIED"
,
"error_description"
:
"Insufficient permissions"
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
INVALID_ARG_VALUE
Invalid input argument value. Details can be found in the error message
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
Digital Workspaces
Create Digital Workspace crm.automatedsolution.add
Update Digital Workplace crm.automatedsolution.update
Get data about the digital workplace by id crm.automatedsolution.get
Delete Digital Workplace crm.automatedsolution.delete
Get fields of the digital workplace crm.automatedsolution.fields
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Digital Workspace Data by ID
Next
Delete a Digital Workspace

---

## Delete Digital Workplace crm.automatedsolution.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automated-solution/crm-automated-solution-delete

Delete Digital Workplace crm.automatedsolution.delete | Bitrix24 REST API and Marketplace Applications
Delete Digital Workplace crm.automatedsolution.delete
Delete Digital Workplace crm.automatedsolution.delete
Method Parameters
Code Examples
Response Handling
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
This method deletes an existing digital workplace with the identifier
id
.
Deletion of the digital workplace is only possible if there are no bound SPAs associated with it.
If there are SPAs, they must first be unbound or reassigned to another workplace before deleting this digital workplace.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the digital workplace. It can be obtained from the response of the method
crm.automatedsolution.add
(
result.automatedSolution.id
), which was called when adding the digital workplace, or
crm.automatedsolution.list
. You can also use the "Digital Workplaces" section on the Bitrix24 account — the
ID
column in the list of digital workplaces
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
'{"id":5}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":5,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.automatedsolution.delete'
,
{
"id"
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
'crm.automatedsolution.delete'
,
[
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
'Error deleting automated solution: '
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
"crm.automatedsolution.delete"
,
{
"id"
:
5
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
'crm.automatedsolution.delete'
,
[
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
HTTP Status:
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
1715852365.744733
,
"finish"
:
1715852366.078274
,
"duration"
:
0.3335409164428711
,
"processing"
:
0.01611018180847168
,
"date_start"
:
"2024-05-16T12:39:25+02:00"
,
"date_finish"
:
"2024-05-16T12:39:26+02:00"
,
"operating_reset_at"
:
1715852966
,
"operating"
:
0
}
}
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
"HAS_BOUND_TYPES"
,
"error_description"
:
"Cannot delete the workplace that has SPAs. Move them to another workplace"
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
HAS_BOUND_TYPES
The digital workplace has bound SPAs. You must unbind the SPAs before deletion
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
Digital Workspaces
Create Digital Workspace crm.automatedsolution.add
Update Digital Workplace crm.automatedsolution.update
Get data about the digital workplace by id crm.automatedsolution.get
Get a list of digital workspaces crm.automatedsolution.list
Get fields of the digital workplace crm.automatedsolution.fields
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Digital Workspaces
Next
Retrieve Digital Workspace Fields

---

## Get fields of the digital workplace crm.automatedsolution.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automated-solution/crm-automated-solution-fields

Get fields of the digital workplace crm.automatedsolution.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get fields of the digital workplace crm.automatedsolution.fields
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
The method returns information about the fields of the digital workplace settings.
No parameters.
Code Examples
Code Examples
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.fields
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
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.fields?auth=**put_access_token_here**
try
{
const
response =
await
$b24.
callMethod
(
"crm.automatedsolution.fields"
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
'crm.automatedsolution.fields'
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
'Error calling automated solution fields: '
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
"crm.automatedsolution.fields"
,
{},
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
'crm.automatedsolution.fields'
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
"TITLE"
,
"upperName"
:
"TITLE"
}
,
"typeIds"
:
{
"type"
:
"crm_dynamic_type"
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
"TYPE_IDS"
,
"upperName"
:
"TYPE_IDS"
}
}
,
"time"
:
{
"start"
:
1715848631.568101
,
"finish"
:
1715848631.898371
,
"duration"
:
0.33027005195617676
,
"processing"
:
0.0055119991302490234
,
"date_start"
:
"2024-05-16T11:37:11+02:00"
,
"date_finish"
:
"2024-05-16T11:37:11+02:00"
,
"operating_reset_at"
:
1715849231
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
An object in the format
{"field_1": "value_1", ... "field_N": "value_N"}
. Where
field
— fields of the digital workplace, and
value
— an object of type
rest_field_description
.
time
time
Information about the execution time of the request
Error Handling
Error Handling
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
Digital Workspaces
Create Digital Workspace crm.automatedsolution.add
Update Digital Workplace crm.automatedsolution.update
Get data about the digital workplace by id crm.automatedsolution.get
Get a list of digital workspaces crm.automatedsolution.list
Delete Digital Workplace crm.automatedsolution.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete a Digital Workspace
Next
About Automation

---

## Automation and Triggers

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automation/index

Automation and Triggers | Bitrix24 REST API and Marketplace Applications
Automation and Triggers
Automation and Triggers
Scope:
crm
Who can execute the method: a user with access permission to modify the target object
target
Triggers are a tool for CRM automation. Unlike Automation rules, triggers do not perform operations. Instead, they can monitor client actions and certain changes within the CRM. Triggers in CRM are available for leads, deals, estimates, invoices, and SPAs. For more details, refer to the article
Triggers in CRM
.
Methods for working with triggers:
Method
Description
crm.automation.trigger
Activates the Webhook trigger configured in CRM automation
crm.automation.trigger.*
Methods for working with application triggers
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Digital Workspace Fields
Next
Activate Trigger

---

## Activate the crm.automation.trigger

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automation/crm-automation-trigger

Activate the crm.automation.trigger | Bitrix24 REST API and Marketplace Applications
Activate the crm.automation.trigger
Activate the crm.automation.trigger
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
Who can execute the method: a user with access permission to modify the target object
target
Bitrix24 allows users to create a special custom trigger "Track Incoming Webhook." The user is provided with a ready-made URL of the form
https://mydomain.bitrix24.com/rest/1/{{PASSWORD}}/crm.automation.trigger/?target=DEAL_{{ID}}&code=nwly5
A call to this URL from an external source will trigger the automation and transition the CRM entity to another stage in the Sales Funnel.
As you can see from the format of this URL, a
local incoming webhook
is effectively created within Bitrix24, which calls the
crm.automation.trigger
method, specifying a specific CRM object and the unique symbolic code of the trigger that was created by Bitrix24 itself (in the example above, this is
nwly5
).
You can use the method not only via the incoming webhook but also in the context of
local
and
mass-market
applications. However, to invoke your own triggers created by your application, you need to use the method
crm.automation.trigger.execute
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
target
*
string
Target object for automation, specified in the form of
TYPENAME_ID
(for example,
LEAD_25
)
code
string
Unique symbolic code of the trigger configured in Automation for a specific status/stage of the document. The
code
parameter can be obtained from the trigger settings
Note
In rare cases, multiple triggers may be detected for the specified
target
object. This happens if:
code
is not passed in the request and there are old triggers on the account that do not have a
code
a
code
is passed that turns out to be the same for multiple triggers
In this case, the first trigger that sets an earlier status for the CRM object will be activated.
It is also worth noting that triggers have "Conditions" and the option "Allow transitioning to the previous status," which affect whether the trigger will work or not.
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
'{"target":"DEAL_57","code":"c5u4m"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automation.trigger
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"target":"DEAL_57","code":"c5u4m","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automation.trigger
try
{
const
response =
await
$b24.
callMethod
(
"crm.automation.trigger"
,
{
target
:
'DEAL_57'
,
code
:
'c5u4m'
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
(error)
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
'crm.automation.trigger'
,
[
'target'
=>
'DEAL_57'
,
'code'
=>
'c5u4m'
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
'Error triggering automation: '
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
"crm.automation.trigger"
,
{
target
:
'DEAL_57'
,
code
:
'c5u4m'
,
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
$result
=
CRest
::
call
(
'crm.automation.trigger'
,
[
'target'
=>
'DEAL_57'
,
'code'
=>
'c5u4m'
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
1718809827.810153
,
"finish"
:
1718809828.541046
,
"duration"
:
0.7308928966522217
,
"processing"
:
0.09834408760070801
,
"date_start"
:
"2024-06-19T15:10:27+00:00"
,
"date_finish"
:
"2024-06-19T15:10:28+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of trigger activation
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
""
,
"error_description"
:
"Target is not set."
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
Target is not set.
The required parameter
target
was not provided
Empty string
Incorrect target format.
The
target
parameter was not provided in the required format (Required format
TYPENAME_ID
)
Empty string
Target is not found.
An incorrect
TYPENAME
was provided in the
target
parameter
ACCESS_DENIED
Access denied! There are no permissions to update the entity.
The user did not pass the permission check to trigger the automation.
Empty string
Access denied.
The user did not pass the preliminary permission check for CRM access
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
Automation and Triggers
Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
About Automation
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automation/triggers/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: administrator with access to CRM in the context of the application
All methods for working with application triggers are executed only in the context of the application.
Method
Description
crm.automation.trigger.add
Adds a trigger
crm.automation.trigger.execute
Executes the trigger
crm.automation.trigger.list
Retrieves the list of applications and triggers
crm.automation.trigger.delete
Deletes a trigger
Copied
Was the article helpful?
Yes
No
Previous
Activate Trigger
Next
Add Trigger

---

## Add Trigger crm.automation.trigger.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automation/triggers/crm-automation-trigger-add

Add Trigger crm.automation.trigger.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Trigger crm.automation.trigger.add
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
Who can execute the method: administrator with access to CRM in the application context
This method adds a trigger.
The method can only be executed in the application context, as the added triggers are tied to this application.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
CODE
*
string
Internal unique (within the application) identifier of the trigger. Must match the pattern
[a-z0-9\.\-_]
.
If an existing trigger identifier
CODE
is provided, the trigger name
NAME
will be updated.
NAME
*
string
Name of the trigger
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
'{"CODE":"c5u4m","NAME":"trigger name"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automation.trigger.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"CODE":"c5u4m","NAME":"trigger name","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automation.trigger.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.automation.trigger.add'
,
{
"CODE"
:
'c5u4m'
,
"NAME"
:
'trigger name'
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
'crm.automation.trigger.add'
,
[
'CODE'
=>
'c5u4m'
,
'NAME'
=>
'trigger name'
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
'Error adding automation trigger: '
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
'crm.automation.trigger.add'
,
{
"CODE"
:
'c5u4m'
,
"NAME"
:
'trigger name'
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
$result
=
CRest
::
call
(
'crm.automation.trigger.add'
,
[
'CODE'
=>
'c5u4m'
,
'NAME'
=>
'trigger name'
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
1718884406.366687
,
"finish"
:
1718884406.80718
,
"duration"
:
0.4404928684234619
,
"processing"
:
0.03356289863586426
,
"date_start"
:
"2024-06-20T11:53:26+00:00"
,
"date_finish"
:
"2024-06-20T11:53:26+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Returns
true
if the trigger was successfully added
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
"ACCESS_DENIED"
,
"error_description"
:
"Access denied! Application context required"
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
User did not pass the preliminary access rights check for CRM
ACCESS_DENIED
Access denied! Admin permissions required
Admin rights check failed
ACCESS_DENIED
Access denied! Application context required
Method called outside of application context
Empty string
Empty trigger code!
Empty parameter
CODE
Empty string
Wrong trigger code!
Parameter
CODE
does not match the pattern
[a-z0-9\.\-_]
Empty string
Empty trigger name!
Empty parameter
NAME
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
Execute the Trigger crm.automation.trigger.execute
Get the list of triggers crm.automation.trigger.list
Delete Trigger ctrigger.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Execute Trigger

---

## Execute the Trigger crm.automation.trigger.execute

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automation/triggers/crm-automation-trigger-execute

Execute the Trigger crm.automation.trigger.execute | Bitrix24 REST API and Marketplace Applications
Method Parameters
Execute the Trigger crm.automation.trigger.execute
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
Who can execute the method: administrator with access to CRM in the application context
This method initiates the execution of a trigger.
The method can only be called in the application context.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
CODE
*
string
Internal unique (within the application) identifier of the trigger. Must match the pattern
[a-z0-9\.\-_]
OWNER_TYPE_ID
*
integer
Type of the CRM object according to the
crm.enum.ownertype
reference (For example,
1
— lead)
Triggers exist in leads, deals, estimates, invoices, and SPAs
OWNER_ID
*
integer
Identifier of the entity
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
'{"CODE":"c5u4m","OWNER_TYPE_ID":2,"OWNER_ID":6}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automation.trigger.execute
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"CODE":"c5u4m","OWNER_TYPE_ID":2,"OWNER_ID":6,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automation.trigger.execute
try
{
const
response =
await
$b24.
callMethod
(
'crm.automation.trigger.execute'
,
{
CODE
:
'c5u4m'
,
OWNER_TYPE_ID
:
2
,
OWNER_ID
:
6
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
'crm.automation.trigger.execute'
,
[
'CODE'
=>
'c5u4m'
,
'OWNER_TYPE_ID'
=>
2
,
'OWNER_ID'
=>
6
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
'Error executing automation trigger: '
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
'crm.automation.trigger.execute'
,
{
CODE
:
'c5u4m'
,
OWNER_TYPE_ID
:
2
,
OWNER_ID
:
6
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
$result
=
CRest
::
call
(
'crm.automation.trigger.execute'
,
[
'CODE'
=>
'c5u4m'
,
'OWNER_TYPE_ID'
=>
2
,
'OWNER_ID'
=>
6
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
1718891973.429101
,
"finish"
:
1718891986.721889
,
"duration"
:
13.292788028717041
,
"processing"
:
13.012810945510864
,
"date_start"
:
"2024-06-20T13:59:33+00:00"
,
"date_finish"
:
"2024-06-20T13:59:46+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Returns true if the trigger was successfully initiated
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
"Incorrect parameter OWNER_TYPE_ID."
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
User did not pass the preliminary access rights check for CRM
ACCESS_DENIED
Access denied! Admin permissions required
Admin rights check failed
ACCESS_DENIED
Access denied! Application context required
Method called outside of application context
Empty string
Empty trigger code!
Empty
CODE
parameter
Empty string
Wrong trigger code!
CODE
parameter does not match the pattern
[a-z0-9\.\-_]
Empty string
Trigger with code {$code} is not registered.
Application trigger not found
Empty string
Incorrect parameter OWNER_TYPE_ID.
Provided
owner_type_id
is not defined in CRM
Empty string
Incorrect parameter OWNER_ID.
Provided
owner_id
parameter value is incorrect (value is not positive)
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
Add Trigger crm.automation.trigger.add
Get the list of triggers crm.automation.trigger.list
Delete Trigger ctrigger.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Trigger
Next
Get List of Triggers

---

## Get the list of triggers crm.automation.trigger.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automation/triggers/crm-automation-trigger-list

Get the list of triggers crm.automation.trigger.list | Bitrix24 REST API and Marketplace Applications
Code Examples
Get the list of triggers crm.automation.trigger.list
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: administrator with access to CRM in the application context
This method retrieves a list of applications and triggers.
The method can only be executed in the application context.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automation.trigger.list
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
https://**put_your_bitrix24_address**/rest/crm.automation.trigger.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.automation.trigger.list'
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in chunks and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.automation.trigger.list'
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
'crm.automation.trigger.list'
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
'crm.automation.trigger.list'
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
'Error fetching automation triggers: '
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
'crm.automation.trigger.list'
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
'crm.automation.trigger.list'
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
"NAME"
:
"Trigger 1"
,
"CODE"
:
"trigger1"
}
,
{
"NAME"
:
"Trigger 2"
,
"CODE"
:
"trigger2"
}
]
,
"time"
:
{
"start"
:
1718952595.479501
,
"finish"
:
1718952595.594397
,
"duration"
:
0.11489605903625488
,
"processing"
:
0.007472038269042969
,
"date_start"
:
"2024-06-21T06:49:55+00:00"
,
"date_finish"
:
"2024-06-21T06:49:55+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Returns an array of triggers added by the application with fields
NAME
and
CODE
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
"ACCESS_DENIED"
,
"error_description"
:
"Access denied! Admin permissions required"
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
User did not pass the preliminary access rights check for CRM
ACCESS_DENIED
Access denied! Admin permissions required
Admin rights check failed
ACCESS_DENIED
Access denied! Application context required
Method called outside of application context
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
Add Trigger crm.automation.trigger.add
Execute the Trigger crm.automation.trigger.execute
Delete Trigger ctrigger.delete
Copied
Was the article helpful?
Yes
No
Previous
Execute Trigger
Next
Delete Trigger

---

## Delete Trigger ctrigger.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/automation/triggers/crm-automation-trigger-delete

Delete Trigger ctrigger.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Trigger ctrigger.delete
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
Who can execute the method: administrator with access to CRM in the application context
This method deletes a trigger.
The method can only be executed in the application context.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
CODE
*
string
Internal unique (within the application) identifier of the trigger. Must match the pattern
[a-z0-9\.\-_]
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
'{"CODE":"c5u4m"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automation.trigger.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"CODE":"c5u4m","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automation.trigger.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.automation.trigger.delete'
,
{
"CODE"
:
'c5u4m'
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
'crm.automation.trigger.delete'
,
[
'CODE'
=>
'c5u4m'
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
'Error deleting automation trigger: '
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
'crm.automation.trigger.delete'
,
{
"CODE"
:
'c5u4m'
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
$result
=
CRest
::
call
(
'crm.automation.trigger.delete'
,
[
'CODE'
=>
'c5u4m'
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
1718891973.429101
,
"finish"
:
1718891986.721889
,
"duration"
:
13.292788028717041
,
"processing"
:
13.012810945510864
,
"date_start"
:
"2024-06-20T13:59:33+00:00"
,
"date_finish"
:
"2024-06-20T13:59:46+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Returns
true
if deleted successfully
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
"Trigger not found"
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
User did not pass the preliminary access rights check for CRM
ACCESS_DENIED
Access denied! Admin permissions required
Admin rights check failed
ACCESS_DENIED
Access denied! Application context required
Method called outside of application context
Empty string
Empty trigger code!
Empty
CODE
parameter
Empty string
Wrong trigger code!
CODE
parameter does not match the pattern
[a-z0-9\.\-_]
Empty string
Trigger not found
Trigger not found
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
Add Trigger crm.automation.trigger.add
Execute the Trigger crm.automation.trigger.execute
Get the list of triggers crm.automation.trigger.list
Copied
Was the article helpful?
Yes
No
Previous
Get List of Triggers
Next
Overview of Methods

---

