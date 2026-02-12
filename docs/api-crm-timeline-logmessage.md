---
description: 'CRM Timeline: Log messages API'
methods:
- crm.timeline.comment.add
- crm.timeline.icon.
- crm.timeline.icon.add
- crm.timeline.icon.delete
- crm.timeline.icon.get
- crm.timeline.icon.list
- crm.timeline.logmessage.add
- crm.timeline.logmessage.delete
- crm.timeline.logmessage.get
- crm.timeline.logmessage.list
- crm.timeline.logo.
- crm.timeline.logo.add
- crm.timeline.logo.delete
- crm.timeline.logo.get
- crm.timeline.logo.list
pages: 15
title: 'CRM Timeline: Log messages API'
---
# CRM Timeline: Log messages API
> CRM Timeline: Log messages API
> **15 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Log Message Journal](#log-message-journal)
- [Add Log Entry crm.timeline.logmessage.add](#add-log-entry-crmtimelinelogmessageadd)
- [Get Information About the Log Entry crm.timeline.logmessage.get](#get-information-about-the-log-entry-crmtimelinelog)
- [Get the list of log entries crm.timeline.logmessage.list](#get-the-list-of-log-entries-crmtimelinelogmessagel)
- [Delete log entry crm.timeline.logmessage.delete](#delete-log-entry-crmtimelinelogmessagedelete)
- [Overview of Methods](#overview-of-methods)
- [Add Icon to crm.timeline.icon.add](#add-icon-to-crmtimelineiconadd)
- [Get Information About the crm.timeline.icon.get](#get-information-about-the-crmtimelineiconget)
- [Get a List of Available Icons crm.timeline.icon.list](#get-a-list-of-available-icons-crmtimelineiconlist)
- [Delete Icon crm.timeline.icon.delete](#delete-icon-crmtimelineicondelete)
- [Overview of Methods](#overview-of-methods)
- [Add Logo crm.timeline.logo.add](#add-logo-crmtimelinelogoadd)
- [Get Information About the Logo crm.timeline.logo.get](#get-information-about-the-logo-crmtimelinelogoget)
- [Get a list of available logos crm.timeline.logo.list](#get-a-list-of-available-logos-crmtimelinelogolist)
- [Delete logo crm.timeline.logo.delete](#delete-logo-crmtimelinelogodelete)

---

## Log Message Journal

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/index

Log Message Journal | Bitrix24 REST API and Marketplace Applications
Log Message Journal
Log Message Journal
The log message journal is a special type of timeline record. It contains less important data than other timeline entries and is distinguished by a muted gray background, drawing less attention.
Scope:
crm
Who can execute the method:
depends on the method
List of methods for managing the log message journal.
Important: The methods
crm.timeline.logmessage.get
and
crm.timeline.logmessage.list
only return records that were previously created using
crm.timeline.logmessage.add
. System records cannot be retrieved using these methods.
Method
Description
crm.timeline.logmessage.add
Adds a new log message to the timeline
crm.timeline.logmessage.get
Retrieves information about a log message
crm.timeline.logmessage.list
Retrieves a list of all log messages for a specific entity
crm.timeline.logmessage.delete
Deletes a log message
crm.timeline.icon.*
Methods for working with record icons
crm.timeline.logo.*
Methods for working with record logos
Copied
Was the article helpful?
Yes
No
Previous
On Deleting a CRM Activity of Type "Comment"
Next
Add Log Entry

---

## Add Log Entry crm.timeline.logmessage.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/crm-timeline-logmessage-add

Add Log Entry crm.timeline.logmessage.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Log Entry crm.timeline.logmessage.add
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
user with permission to modify the CRM entity to which the entry will be added
This method adds a new log entry to the timeline.
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
) for adding a new log entry in the form of a structure:
fields
:
{
entityTypeId
:
"value"
,
entityId
:
"value"
,
title
:
"value"
,
text
:
"value"
,
iconCode
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
entityTypeId
*
integer
Identifier of the entity type
in which the entry will be created
entityId
*
integer
Identifier of the entity item in which the entry will be created
title
*
string
Title of the entry
text
*
string
Text of the entry
iconCode
*
string
Icon code.
A list of available codes can be obtained using the method
crm.timeline.icon.list
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
'{"fields":{"entityTypeId":1,"entityId":1,"title":"Test title","text":"Test text message","iconCode":"info"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.logmessage.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"entityTypeId":1,"entityId":1,"title":"Test title","text":"Test text message","iconCode":"info"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.logmessage.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.logmessage.add'
,
{
fields
: {
entityTypeId
:
1
,
entityId
:
1
,
title
:
'Test title'
,
text
:
'Test text message'
,
iconCode
:
'info'
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
'crm.timeline.logmessage.add'
,
[
'fields'
=> [
'entityTypeId'
=>
1
,
'entityId'
=>
1
,
'title'
=>
'Test title'
,
'text'
=>
'Test text message'
,
'iconCode'
=>
'info'
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
'Error adding log message: '
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
"crm.timeline.logmessage.add"
,
{
fields
: {
entityTypeId
:
1
,
entityId
:
1
,
title
:
"Test title"
,
text
:
"Test text message"
,
iconCode
:
"info"
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
'crm.timeline.logmessage.add'
,
[
'fields'
=> [
'entityTypeId'
=>
1
,
'entityId'
=>
1
,
'title'
=>
'Test title'
,
'text'
=>
'Test text message'
,
'iconCode'
=>
'info'
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
"logMessage"
:
{
"id"
:
1
,
"created"
:
"2024-04-03T10:26:32+02:00"
,
"authorId"
:
1
,
"title"
:
"Test title"
,
"text"
:
"Test note"
,
"iconCode"
:
"info"
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
Root element of the response.
The
result
field contains the
logMessage
object
time
time
Information about the request execution time
logMessage Object
logMessage Object
Name
type
Description
id
integer
Identifier of the timeline entry
created
datetime
Date and time of creation
authorId
integer
User who created the entry
title
string
Title of the entry
text
string
Content of the entry
iconCode
string
Icon code
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
Code
Description
ACCESS_DENIED
Access denied
OWNER_NOT_FOUND
The CRM entity with the specified
entityTypeId
and
entityId
does not exist
100
Required fields not provided
0
Other errors (e.g., fatal)
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
Get Information About the Log Entry crm.timeline.logmessage.get
Get the list of log entries crm.timeline.logmessage.list
Delete log entry crm.timeline.logmessage.delete
Copied
Was the article helpful?
Yes
No
Previous
Log Record Journal
Next
Get Log Entry Information

---

## Get Information About the Log Entry crm.timeline.logmessage.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/crm-timeline-logmessage-get

Get Information About the Log Entry crm.timeline.logmessage.get | Bitrix24 REST API and Marketplace Applications
Get Information About the Log Entry crm.timeline.logmessage.get
Get Information About the Log Entry crm.timeline.logmessage.get
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
user with read access permission to the CRM entity containing the entry
This method retrieves information about a timeline log entry.
It is important to note that the method can only retrieve data about entries that were previously added using
crm.timeline.logmessage.add
. System entries cannot be retrieved using
crm.timeline.logmessage.get
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
Integer identifier of the timeline entry (for example,
1
).
Identifiers can be obtained using the method
crm.timeline.logmessage.list
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
'{"id":1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.logmessage.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":1,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.logmessage.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.logmessage.get'
,
{
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
'crm.timeline.logmessage.get'
,
[
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
'Error getting log message: '
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
"crm.timeline.logmessage.get"
,
{
id
:
1
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
'crm.timeline.logmessage.get'
,
[
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
HTTP Status:
200
{
"result"
:
{
"logMessage"
:
{
"id"
:
1
,
"created"
:
"2024-04-03T10:26:32+02:00"
,
"authorId"
:
1
,
"title"
:
"Test title"
,
"text"
:
"Test note"
,
"iconCode"
:
"info"
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
Root element of the response.
The
result
field contains the
logMessage
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
"Timeline logmessage not found for id 1"
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
NOT_FOUND
The timeline entry with the specified
id
does not exist
100
Required fields were not provided
0
Other errors (e.g., fatal)
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
Add Log Entry crm.timeline.logmessage.add
Get the list of log entries crm.timeline.logmessage.list
Delete log entry crm.timeline.logmessage.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Log Entry
Next
Get List of Timeline Log Entries

---

## Get the list of log entries crm.timeline.logmessage.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/crm-timeline-logmessage-list

Get the list of log entries crm.timeline.logmessage.list | Bitrix24 REST API and Marketplace Applications
Get the list of log entries crm.timeline.logmessage.list
Get the list of log entries crm.timeline.logmessage.list
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
Who can execute the method:
user with read access permission for the CRM entity containing the record
This method retrieves a list of timeline log entries.
It is important to note that the method can only retrieve data about records that were previously added using
crm.timeline.logmessage.add
. System records cannot be retrieved using
crm.timeline.logmessage.list
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
Identifier of the entity type
for which to retrieve the list of log entries (e.g.,
1
— lead)
entityId
*
integer
Identifier of the entity item for which to retrieve the list of log entries (e.g.,
1
)
order
object
List for sorting, where the key is the field and the value is
asc
or
desc
.
By default,
desc
is used.
Sorting is supported only by the
id
and
created
fields
start
integer
This parameter is used to manage pagination.
The page size of results is always static: 10 entries.
To select the second page of results, you need to pass the value
10
. To select the third page of results — the value
20
, and so on.
The formula for calculating the
start
parameter value:
start = (N - 1) * 10
, where
N
is the desired page number
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
'{"entityTypeId":1,"entityId":1,"order":{"created":"desc"},"start":1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.logmessage.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1,"entityId":1,"order":{"created":"desc"},"start":1,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.logmessage.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.timeline.logmessage.list'
,
{
entityTypeId
:
1
,
entityId
:
1
,
order
: {
created
:
"desc"
},
start
:
1
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.timeline.logmessage.list'
, {
entityTypeId
:
1
,
entityId
:
1
,
order
: {
created
:
"desc"
},
start
:
1
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
'crm.timeline.logmessage.list'
, {
entityTypeId
:
1
,
entityId
:
1
,
order
: {
created
:
"desc"
},
start
:
1
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
'crm.timeline.logmessage.list'
,
[
'entityTypeId'
=>
1
,
'entityId'
=>
1
,
'order'
=> [
'created'
=>
'desc'
],
'start'
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
'Error listing log messages: '
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
"crm.timeline.logmessage.list"
,
{
entityTypeId
:
1
,
entityId
:
1
,
order
: {
created
:
"desc"
},
start
:
1
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
'crm.timeline.logmessage.list'
,
[
'entityTypeId'
=>
1
,
'entityId'
=>
1
,
'order'
=> [
'created'
=>
'desc'
],
'start'
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
HTTP Status:
200
{
"result"
:
[
{
"id"
:
42074
,
"created"
:
"2024-04-03T10:26:32+02:00"
,
"authorId"
:
1
,
"title"
:
"Test title new"
,
"text"
:
"Test note new"
,
"iconCode"
:
"info"
}
,
{
"id"
:
42073
,
"created"
:
"2024-04-03T10:26:32+02:00"
,
"authorId"
:
1
,
"title"
:
"Test title"
,
"text"
:
"Test note"
,
"iconCode"
:
"info"
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
The root element of the response.
The
result
field contains an array, each entry of which contains an associative array of log entry fields
logMessage
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
"100"
,
"error_description"
:
"Could not find value for parameter {entityTypeId}"
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
0
Other errors (e.g., fatal)
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
Add Log Entry crm.timeline.logmessage.add
Get Information About the Log Entry crm.timeline.logmessage.get
Delete log entry crm.timeline.logmessage.delete
Copied
Was the article helpful?
Yes
No
Previous
Get Log Entry Information
Next
Delete Entry

---

## Delete log entry crm.timeline.logmessage.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/crm-timeline-logmessage-delete

Delete log entry crm.timeline.logmessage.delete | Bitrix24 REST API and Marketplace Applications
Delete log entry crm.timeline.logmessage.delete
Delete log entry crm.timeline.logmessage.delete
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
user with permission to modify the CRM entity where the entry is located
This method deletes a timeline log entry.
Warning
You can only delete a log entry in the context of the
application
that created it.
This means that only the application that added the entry can delete it. This ensures data security and control.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Integer identifier of the timeline entry (for example,
1
).
You can obtain identifiers using the
crm.timeline.logmessage.list
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
'{"id":1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.logmessage.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":1,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.logmessage.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.logmessage.delete'
,
{
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
'crm.timeline.logmessage.delete'
,
[
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
'Error deleting log message: '
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
"crm.timeline.logmessage.delete"
,
{
id
:
1
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
'crm.timeline.logmessage.delete'
,
[
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
Result of the operation. Returns:
true
— on successful deletion
null
— on error
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
"Timeline logmessage not found for id 1"
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
Access denied
NOT_FOUND
Timeline entry with the specified
id
does not exist
REMOVING_DISABLED
Timeline entry with the specified
id
was created in the context of another REST application
100
Required fields not provided
0
Other errors (e.g., fatal)
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
Add Log Entry crm.timeline.logmessage.add
Get Information About the Log Entry crm.timeline.logmessage.get
Get the list of log entries crm.timeline.logmessage.list
Copied
Was the article helpful?
Yes
No
Previous
Get List of Timeline Log Entries
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/icons/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method:
depends on the method
A list of methods for managing log record icons.
Method
Description
crm.timeline.icon.add
Adds a new icon
crm.timeline.icon.get
Retrieves information about an icon
crm.timeline.icon.list
Retrieves a list of all available icons
crm.timeline.icon.delete
Deletes an icon
Continue Exploring
Continue Exploring
Log Message Journal
Copied
Was the article helpful?
Yes
No
Previous
Delete Entry
Next
Add Icon

---

## Add Icon to crm.timeline.icon.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/icons/crm-timeline-icon-add

Add Icon to crm.timeline.icon.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Icon to crm.timeline.icon.add
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
administrator
This method adds a new icon.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
code
*
string
Icon code (for example,
info
)
fileContent
*
string
Base64 encoded content of the icon file.
File requirements:
Type — png
Size — 24x24 pixels
Background — transparent
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
'{"code":"info","fileContent":"iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAIAAABvFaqvAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TRdGqgx1UHDLUgmBBVMRRq1CECqFWaNXB5NIvaNKQpLg4Cq4FBz8Wqw4uzro6uAqC4AeIo5OToouU"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.icon.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"code":"info","fileContent":"iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAIAAABvFaqvAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TRdGqgx1UHDLUgmBBVMRRq1CECqFWaNXB5NIvaNKQpLg4Cq4FBz8Wqw4uzro6uAqC4AeIo5OToouU","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.icon.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.icon.add'
,
{
code
:
'info'
,
fileContent
:
'iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAIAAABvFaqvAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TRdGqgx1UHDLUgmBBVMRRq1CECqFWaNXB5NIvaNKQpLg4Cq4FBz8Wqw4uzro6uAqC4AeIo5OToouU'
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
'crm.timeline.icon.add'
,
[
'code'
=>
'info'
,
'fileContent'
=>
'iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAIAAABvFaqvAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TRdGqgx1UHDLUgmBBVMRRq1CECqFWaNXB5NIvaNKQpLg4Cq4FBz8Wqw4uzro6uAqC4AeIo5OToouU'
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
'Error adding timeline icon: '
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
"crm.timeline.icon.add"
,
{
code
:
"info"
,
fileContent
:
"iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAIAAABvFaqvAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TRdGqgx1UHDLUgmBBVMRRq1CECqFWaNXB5NIvaNKQpLg4Cq4FBz8Wqw4uzro6uAqC4AeIo5OToouU"
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
'crm.timeline.icon.add'
,
[
'code'
=>
'info'
,
'fileContent'
=>
'iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAIAAABvFaqvAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TRdGqgx1UHDLUgmBBVMRRq1CECqFWaNXB5NIvaNKQpLg4Cq4FBz8Wqw4uzro6uAqC4AeIo5OToouU'
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
"icon"
:
{
"code"
:
"info"
,
"isSystem"
:
false
,
"fileUri"
:
"/upload/crm/13f/huhnvzds7ckoy6mk5mdze9pb7jqscpxi/e66fm2cbau9f8u32oe9jzx2qflqhj2vv"
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
Root element of the response.
The
result
field contains the
icon
object
time
time
Information about the request execution time
Icon Object
Icon Object
Field
type
Description
code
Icon code
isSystem
Flag field.
Can have the value:
true
— if the icon is standard (provided in the product)
false
— if the icon was added by the user
fileUri
Path to the file.
If the icon was added by the user, the field contains the path to the icon image file
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
Code
Description
ACCESS_DENIED
Access denied
INVALID_ARG_VALUE
Invalid
fileContent
parameter specified
FILE_SAVE_ERROR
Unable to save the provided icon file
100
Required fields not provided
0
Other errors (e.g., fatal)
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
Get Information About the crm.timeline.icon.get
Get a List of Available Icons crm.timeline.icon.list
Delete Icon crm.timeline.icon.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get Icon Information

---

## Get Information About the crm.timeline.icon.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/icons/crm-timeline-icon-get

Get Information About the crm.timeline.icon.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Information About the crm.timeline.icon.get
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
This method retrieves information about the timeline log entry icon.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
code
*
string
Icon code (for example,
info
).
You can get a list of all available codes using the method
crm.timeline.icon.list
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
'{"code":"info"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.icon.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"code":"info","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.icon.get
try
{
const
response =
await
$b24.
callMethod
(
"crm.timeline.icon.get"
,
{
code
:
"info"
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
'crm.timeline.icon.get'
,
[
'code'
=>
'info'
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
'Error getting timeline icon: '
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
"crm.timeline.icon.get"
,
{
code
:
"info"
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
'crm.timeline.icon.get'
,
[
'code'
=>
'info'
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
"icon"
:
{
"code"
:
"info"
,
"isSystem"
:
false
,
"fileUri"
:
"/upload/crm/13f/huhnvzds7ckoy6mk5mdze9pb7jqscpxi/e66fm2cbau9f8u32oe9jzx2qflqhj2vv"
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
Root element of the response.
The
result
field contains the
icon
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
"Icon not found for code `test`"
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
NOT_FOUND
No icon exists with the specified
code
100
Required fields were not provided
0
Other errors (e.g., fatal)
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
Add Icon to crm.timeline.icon.add
Get a List of Available Icons crm.timeline.icon.list
Delete Icon crm.timeline.icon.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Icon
Next
Get List of Available Icons

---

## Get a List of Available Icons crm.timeline.icon.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/icons/crm-timeline-icon-list

Get a List of Available Icons crm.timeline.icon.list | Bitrix24 REST API and Marketplace Applications
Code Examples
Get a List of Available Icons crm.timeline.icon.list
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Exploring
Scope:
crm
Who can execute the method:
any user
This method retrieves a list of available icons for timeline log entries.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.icon.list
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
https://**put_your_bitrix24_address**/rest/crm.timeline.icon.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). This method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.timeline.icon.list'
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
// fetchListMethod is preferable when working with large datasets. This method implements iterative fetching using a generator, allowing data to be processed in chunks and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.timeline.icon.list'
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.icon.list'
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
'crm.timeline.icon.list'
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
'Error fetching timeline icons: '
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
"crm.timeline.icon.list"
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
'crm.timeline.icon.list'
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
HTTP Status:
200
{
"result"
:
{
"icons"
:
[
{
"code"
:
"call"
,
"isSystem"
:
true
,
"fileUri"
:
""
}
,
{
"code"
:
"arrow-down"
,
"isSystem"
:
true
,
"fileUri"
:
""
}
,
{
"code"
:
"info"
,
"isSystem"
:
false
,
"fileUri"
:
"/upload/crm/13f/huhnvzds7ckoy6mk5mdze9pb7jqscpxi/e66fm2cbau9f8u32oe9jzx2qflqhj2vv"
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
Root element of the response.
The
result
field contains an array of
icons
, each entry includes an associative array of icon fields
icon
total
integer
Total number of records found
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
"0"
,
"error_description"
:
"Could not find value"
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
Other errors (e.g., fatal)
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
Add Icon to crm.timeline.icon.add
Get Information About the crm.timeline.icon.get
Delete Icon crm.timeline.icon.delete
Copied
Was the article helpful?
Yes
No
Previous
Get Icon Information
Next
Delete Icon

---

## Delete Icon crm.timeline.icon.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/icons/crm-timeline-icon-delete

Delete Icon crm.timeline.icon.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Icon crm.timeline.icon.delete
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
administrator
This method deletes an icon.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
code
*
string
Icon code (for example,
info
).
You can get a list of all available codes using the method
crm.timeline.icon.list
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
'{"code":"info"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.icon.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"code":"info","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.icon.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.icon.delete'
,
{
code
:
'info'
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
'crm.timeline.icon.delete'
,
[
'code'
=>
'info'
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
'Error deleting timeline icon: '
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
'Error deleting timeline icon: '
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
"crm.timeline.icon.delete"
,
{
code
:
"info"
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
'crm.timeline.icon.delete'
,
[
'code'
=>
'info'
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
Operation result Returns:
true
— on successful deletion
null
— on error
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
"Icon not found for code `info`"
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
Access denied
NOT_FOUND
Icon with the specified
code
does not exist
100
Required fields not provided
0
Other errors (e.g., fatal)
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
Add Icon to crm.timeline.icon.add
Get Information About the crm.timeline.icon.get
Get a List of Available Icons crm.timeline.icon.list
Copied
Was the article helpful?
Yes
No
Previous
Get List of Available Icons
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/logo/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method:
depends on the method
A list of methods for managing the logos of log entries in the journal.
Method
Description
crm.timeline.logo.add
Adds a new logo
crm.timeline.logo.get
Retrieves information about the logo
crm.timeline.logo.list
Gets a list of all available logos
crm.timeline.logo.delete
Deletes a logo
Continue Exploring
Continue Exploring
Log Message Journal
Copied
Was the article helpful?
Yes
No
Previous
Delete Icon
Next
Add Logo

---

## Add Logo crm.timeline.logo.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/logo/crm-timeline-logo-add

Add Logo crm.timeline.logo.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Logo crm.timeline.logo.add
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
administrator
This method adds a new logo.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
code
*
string
Logo code (for example,
info
)
fileContent
*
string
Base64 encoded content of the logo file.
File requirements:
Type — png
Size — 60x60 pixels
Background — transparent
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
'crm.timeline.logo.add'
,
{
code
:
'info'
,
fileContent
:
'iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAIAAABvFaqvAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TRdGqgx1UHDLUgmBBVMRRq1CECqFWaNXB5NIvaNKQpLg4Cq4FBz8Wqw4uzro6uAqC4AeIo5OToouU'
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
'crm.timeline.logo.add'
,
[
'code'
=>
'info'
,
'fileContent'
=>
'iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAIAAABvFaqvAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TRdGqgx1UHDLUgmBBVMRRq1CECqFWaNXB5NIvaNKQpLg4Cq4FBz8Wqw4uzro6uAqC4AeIo5OToouU'
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
'Error adding timeline logo: '
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
"crm.timeline.logo.add"
,
{
code
:
"info"
,
fileContent
:
"iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAIAAABvFaqvAAABhWlDQ1BJQ0MgcHJvZmlsZQAAKJF9kT1Iw0AcxV9TRdGqgx1UHDLUgmBBVMRRq1CECqFWaNXB5NIvaNKQpLg4Cq4FBz8Wqw4uzro6uAqC4AeIo5OToouU"
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
{
"logo"
:
{
"code"
:
"info"
,
"isSystem"
:
false
,
"fileUri"
:
"/upload/crm/286/a1k092hygdrzpiz6a01enuymqoo5qzym/ou0akdwnbxalzk9hgfme39nbvtozblew"
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
Root element of the response.
The
result
field contains the
logo
object
time
time
Information about the request execution time
Logo Object
Logo Object
Field
type
Description
code
Logo code
isSystem
Flag field. Can have the value:
true
— if the logo is standard (provided with the product)
false
— if the logo was added by the user
fileUri
Path to the file.
If the logo was added by the user, the field contains the path to the logo image file
Error Handling
Error Handling
HTTP Status:
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
Code
Description
ACCESS_DENIED
Access denied
INVALID_ARG_VALUE
Invalid
fileContent
parameter specified
FILE_SAVE_ERROR
Unable to save the provided logo file
100
Required fields not provided
0
Other errors (e.g., fatal)
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
Get Information About the Logo crm.timeline.logo.get
Get a list of available logos crm.timeline.logo.list
Delete logo crm.timeline.logo.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get Logo Information

---

## Get Information About the Logo crm.timeline.logo.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/logo/crm-timeline-logo-get

Get Information About the Logo crm.timeline.logo.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Information About the Logo crm.timeline.logo.get
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
Who can execute the method:
any user
This method retrieves information about the logo of the timeline log entry.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
code
*
string
Logo code (for example,
info
).
You can get a list of all available codes using the method
crm.timeline.logo.list
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
'{"code":"info"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.logo.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"code":"info","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.logo.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.logo.get'
,
{
code
:
'info'
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
'crm.timeline.logo.get'
,
[
'code'
=>
'info'
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
'Error getting timeline logo: '
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
"crm.timeline.logo.get"
,
{
code
:
"info"
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
'crm.timeline.logo.get'
,
[
'code'
=>
'info'
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
"logo"
:
{
"code"
:
"info"
,
"isSystem"
:
false
,
"fileUri"
:
"/upload/crm/286/a1k092hygdrzpiz6a01enuymqoo5qzym/ou0akdwnbxalzk9hgfme39nbvtozblew"
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
Root element of the response.
The
result
field contains the
logo
object
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
"Logo not found for code `test`"
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
NOT_FOUND
No logo exists with the specified
code
100
Required fields not provided
0
Other errors (e.g., fatal)
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
Add Logo crm.timeline.logo.add
Get a list of available logos crm.timeline.logo.list
Delete logo crm.timeline.logo.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Logo
Next
Get List of Available Logos

---

## Get a list of available logos crm.timeline.logo.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/logo/crm-timeline-logo-list

Get a list of available logos crm.timeline.logo.list | Bitrix24 REST API and Marketplace Applications
Code Examples
Get a list of available logos crm.timeline.logo.list
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Exploring
Scope:
crm
Who can execute the method:
any user
This method retrieves a list of available logos for timeline log entries.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.logo.list
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
https://**put_your_bitrix24_address**/rest/crm.timeline.logo.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.timeline.logo.list'
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
'crm.timeline.logo.list'
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
'crm.timeline.logo.list'
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
'crm.timeline.logo.list'
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
'Error fetching timeline logos: '
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
"crm.timeline.logo.list"
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
'crm.timeline.logo.list'
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
"logos"
:
[
{
"code"
:
"call"
,
"isSystem"
:
true
,
"fileUri"
:
""
}
,
{
"code"
:
"arrow-down"
,
"isSystem"
:
true
,
"fileUri"
:
""
}
,
{
"code"
:
"info"
,
"isSystem"
:
false
,
"fileUri"
:
"/upload/crm/286/a1k092hygdrzpiz6a01enuymqoo5qzym/ou0akdwnbxalzk9hgfme39nbvtozblew"
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
Root element of the response.
The
result
field contains an array of
logos
, each entry of which includes an associative array of logo fields
logo
total
integer
Total number of records found
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
"0"
,
"error_description"
:
"Could not find value"
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
Other errors (e.g., fatal)
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
Add Logo crm.timeline.logo.add
Get Information About the Logo crm.timeline.logo.get
Delete logo crm.timeline.logo.delete
Copied
Was the article helpful?
Yes
No
Previous
Get Logo Information
Next
Delete Logo

---

## Delete logo crm.timeline.logo.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/timeline/logmessage/logo/crm-timeline-logo-delete

Delete logo crm.timeline.logo.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete logo crm.timeline.logo.delete
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
administrator
This method deletes the logo.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
code
*
string
Logo code (for example,
info
).
You can get a list of all available codes using the method
crm.timeline.logo.list
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
'{"code":"info"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.timeline.logo.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"code":"info","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.timeline.logo.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.timeline.logo.delete'
,
{
code
:
'info'
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
'crm.timeline.logo.delete'
,
[
'code'
=>
'info'
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
'Error deleting timeline logo: '
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
"crm.timeline.logo.delete"
,
{
code
:
"info"
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
'crm.timeline.logo.delete'
,
[
'code'
=>
'info'
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
Operation result. Returns:
true
— on successful deletion
null
— on error
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
"Logo not found for code `info`"
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
Access denied
NOT_FOUND
Logo with the specified
code
does not exist
100
Required fields not provided
0
Other errors (e.g., fatal)
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
Add Logo crm.timeline.logo.add
Get Information About the Logo crm.timeline.logo.get
Get a list of available logos crm.timeline.logo.list
Copied
Was the article helpful?
Yes
No
Previous
Get List of Available Logos
Next
Overview of Methods

---

