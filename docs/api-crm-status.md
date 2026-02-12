---
description: 'CRM Statuses/Stages API: Deal stages, lead statuses, history'
methods:
- crm.deal.update
- crm.deal.userfield.add
- crm.enum.settings.mode
- crm.settings.mode.get
- crm.stagehistory.list
- crm.status.
- crm.status.add
- crm.status.delete
- crm.status.entity.items
- crm.status.entity.types
- crm.status.fields
- crm.status.get
- crm.status.list
- crm.status.update
- crm.xx.userfield.
pages: 11
title: 'CRM Statuses/Stages API: Deal stages, lead statuses, history'
---
# CRM Statuses/Stages API: Deal stages, lead statuses, history
> CRM Statuses/Stages API: Deal stages, lead statuses, history
> **11 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Determine the Current CRM Operating Mode crm.settings.mode.get](#determine-the-current-crm-operating-mode-crmsettin)
- [Statuses and dropdowns in CRM: Overview of Methods](#statuses-and-dropdowns-in-crm-overview-of-methods)
- [Create CRM Status Element crm.status.add](#create-crm-status-element-crmstatusadd)
- [Update CRM Status Element <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-z0tjywqn">crm.status.update</code>](#update-crm-status-element-code-classyfm-clipboard-)
- [Get CRM Status Entity Types](#get-crm-status-entity-types)
- [Get directory items by type crm.status.entity.items](#get-directory-items-by-type-crmstatusentityitems)
- [Get a directory item by ID crm.status.get](#get-a-directory-item-by-id-crmstatusget)
- [Get a List of Directory Items by Filter crm.status.list](#get-a-list-of-directory-items-by-filter-crmstatusl)
- [Delete CRM Status Element <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-yx192bjj">crm.status.delete</code>](#delete-crm-status-element-code-classyfm-clipboard-)
- [Get Description of CRM Status Fields](#get-description-of-crm-status-fields)
- [Get Stage History with crm.stagehistory.list](#get-stage-history-with-crmstagehistorylist)

---

## Determine the Current CRM Operating Mode crm.settings.mode.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/crm-settings-mode-get

Determine the Current CRM Operating Mode crm.settings.mode.get | Bitrix24 REST API and Marketplace Applications
Determine the Current CRM Operating Mode crm.settings.mode.get
Determine the Current CRM Operating Mode crm.settings.mode.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Method name:
crm.settings.mode.get
Scope:
crm
Who can execute the method:
any user
The method returns the current settings of the CRM operating mode:
classic CRM mode
(with leads) or
simple CRM mode
(without leads).
This mode affects a number of CRM operation scenarios, and for better understanding, we recommend reading the
relevant article
in the user documentation.
Method Parameters
Method Parameters
The method is called without parameters.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.settings.mode.get
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
https://**put_your_bitrix24_address**/rest/crm.settings.mode.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.settings.mode.get'
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
'crm.settings.mode.get'
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
'Error getting CRM settings mode: '
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
"crm.settings.mode.get"
, {},
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
});
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
'crm.settings.mode.get'
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
1
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
Returns the value defined in
crm.enum.settings.mode
time
time
Information about the request execution time
Error Handling
Error Handling
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
Copied
Was the article helpful?
Yes
No
Previous
Typical Use-Cases and Tutorials
Next
Universal Methods for Core Elements

---

## Statuses and dropdowns in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/status/index

Statuses and dropdowns in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Statuses and dropdowns in CRM: Overview of Methods
Statuses and dropdowns in CRM: Overview of Methods
List of Statuses and dropdowns
How to Use Reference Book Values
Overview of Methods and Events
In the detail forms of CRM entities, there are two types of "list" fields:
Custom fields — these can be created, modified, and deleted using the methods crm.xx.userfield.*. For example, to create a custom list field in deals, use
crm.deal.userfield.add
System fields — these are pre-installed and cannot be created or deleted. In system list fields, only the values of the list can be modified. The list of values for system fields of type "list" is called a reference book in CRM.
Quick navigation:
all methods and events
User documentation:
Statuses and dropdowns in Bitrix24
List of Statuses and dropdowns
List of Statuses and dropdowns
To modify a reference book, specify the
ENTITY_ID
parameter in the methods of the group crm.status.*. If the value is incorrect, another reference book will be modified.
Stages.
A reference book with stages of working with clients, which are displayed in the CRM kanban. Each CRM object has its own code for the stages reference book:
Deals
—
DEAL_STAGE
for the main direction of deals and
DEAL_STAGE_xx
for additional, where xx is the ID of the direction
Leads
—
STATUS
Invoices
—
SMART_INVOICE_STAGE_xx
, where xx is the ID value of the invoice direction
Estimates
—
QUOTE_STATUS
Documents
—
SMART_DOCUMENT_STAGE_xx
, where xx is the ID value of the document direction
SPAs
—
DYNAMIC_xx_STAGE_xx
, where the first xx is the ID of the SPA, and the second xx is the ID of the direction
To get the ID of the direction for a specific Bitrix24, use the method
crm.status.entity.types
.
Sources.
A reference book with values for the system field Source —
SOURCE
.
Contact and Company Types.
Reference books with values for the system fields Contact Type —
CONTACT_TYPE
, Company Type —
COMPANY_TYPE
.
Number of Employees.
A reference book with values for the system field Number of Employees in the company detail form —
EMPLOYEES
.
Client Industry.
A reference book with values for the system field Industry in the company detail form —
INDUSTRY
.
Deal Type.
A reference book with values for the system field Deal Type in the deal detail form —
DEAL_TYPE
.
Honorifics.
A reference book with values for the system field Honorific in the lead and contact detail forms —
HONORIFIC
.
Call Statuses.
A reference book with values for the Call Status in the call list detail form —
CALL_LIST
.
How to Use Reference Book Values
How to Use Reference Book Values
Each list value in the reference books has:
name
NAME
— displayed in the CRM entity detail form
status
STATUS_ID
— used in methods for creating and modifying entities
Using the method
crm.deal.update
, you can change the values of the fields
Deal Stage
—
STAGE_ID
and
Source
—
SOURCE_ID
. Both fields are system list fields.
To display the name of the stage or source in the CRM detail form, it is important to pass not the
NAME
of the value, but its
STATUS_ID
in the method. For the stage "New Request," this may be
C1:NEW
, and for the source "Call" —
CALL
.
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can execute the method: any user
Method
Description
crm.status.add
Creates a new element in the specified reference book
crm.status.delete
Deletes an element from the reference book
crm.status.entity.items
Returns elements of the reference book by its symbolic identifier
crm.status.entity.types
Returns descriptions of reference book types
crm.status.fields
Returns descriptions of reference book fields
crm.status.get
Returns an element of the reference book by its identifier
crm.status.list
Returns a list of elements of the reference book by filter
crm.status.update
Updates an existing element of the reference book
Copied
Was the article helpful?
Yes
No
Previous
Remove a Field from Duplicate Search
Next
Create a new item in the directory

---

## Create CRM Status Element crm.status.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/status/crm-status-add

Create CRM Status Element crm.status.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create CRM Status Element crm.status.add
Method Parameters
Parameter fields
Field Features
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: user with CRM administrator rights
The method
crm.status.add
creates a new element in the specified CRM directory: deal stage, source, company type, and others.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
Object with fields of the new directory element. The list of available fields is described
below
Parameter fields
Parameter fields
Name
type
Description
ENTITY_ID
*
string
Type of directory, for example
DEAL_STAGE
,
SOURCE
. You can get the list of types using the method
crm.status.entity.types
STATUS_ID
*
string
Status value code. The code must be unique within the directory. Length and character restrictions depend on the type of directory
NAME
*
string
Name
SORT
integer
Sorting. Default is 10
COLOR
string
Hex color code, for example
#39A8EF
. Use for status stages
SEMANTICS
string
Group of stages:
"S"
— "Success",
"F"
— "Failure",
""
— "In Progress".
Use for status stages. Default is "In Progress" group
Field Features
Field Features
Restrictions for
STATUS_ID
Follow the length and character restrictions for different types of directories:
STATUS
lead stages. Max length: 21, can contain only Latin letters, numbers, hyphens, and underscores.
QUOTE_STATUS
estimate stages. Max length: 22, can contain only Latin letters, numbers, hyphens, and underscores.
DEAL_STAGE
deal stages. Max length: 22, can contain only Latin letters, numbers, hyphens, and underscores.
DEAL_STAGE_xx
deal stages in non-default funnels. xx — funnel identifier. Max length depends on the funnel identifier. Can contain only Latin letters, numbers, hyphens, and underscores.
For other
ENTITY_ID
, the maximum length of
STATUS_ID
is 50 characters and can contain any characters.
If a stage is added for a custom deal funnel, the status identifier will automatically have the funnel prefix added. This is necessary to identify the funnel by the stage identifier.
For example, the value
DECISION
for a deal funnel with identifier
1
will be saved as
C1:DECISION
. The system will automatically add the prefix
C1:
corresponding to the deal funnel identifier.
If a value is passed to the field with the prefix
C1:DECISION
, it will be saved as
C1:DECISION
, and no additional prefix will be added.
For SPAs with funnels, a similar logic for forming
STATUS_ID
from the value and prefix applies. The funnel prefix can be obtained using the method
crm.status.entity.types
.
Restrictions for
SORT
For the correct operation of status stages, the sorting must follow this order:
Stages of the "In Progress" group
Stage of the "Success" group
Stages of the "Failure" group
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
'{"fields":{"ENTITY_ID":"DEAL_STAGE_1","STATUS_ID":"DECISION","NAME":"Decision Making","SORT":70,"COLOR":"#FFA900"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.status.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"ENTITY_ID":"DEAL_STAGE_1","STATUS_ID":"DECISION","NAME":"Decision Making","SORT":70,"COLOR":"#FFA900"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.status.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.status.add'
,
{
fields
: {
ENTITY_ID
:
'DEAL_STAGE_1'
,
STATUS_ID
:
'DECISION'
,
NAME
:
'Decision Making'
,
SORT
:
70
,
COLOR
:
'#FFA900'
}
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
'crm.status.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
'DEAL_STAGE_1'
,
'STATUS_ID'
=>
'DECISION'
,
'NAME'
=>
'Decision Making'
,
'SORT'
=>
70
,
'COLOR'
=>
'#FFA900'
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
'Error adding status: '
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
"crm.status.add"
,
{
fields
: {
ENTITY_ID
:
"DEAL_STAGE_1"
,
STATUS_ID
:
"DECISION"
,
NAME
:
"Decision Making"
,
SORT
:
70
,
COLOR
:
"#FFA900"
}
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
'crm.status.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
'DEAL_STAGE_1'
,
'STATUS_ID'
=>
'DECISION'
,
'NAME'
=>
'Decision Making'
,
'SORT'
=>
70
,
'COLOR'
=>
'#FFA900'
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
773
,
"time"
:
{
"start"
:
1752215174.862923
,
"finish"
:
1752215174.916697
,
"duration"
:
0.053774118423461914
,
"processing"
:
0.014070987701416016
,
"date_start"
:
"2025-07-11T09:26:14+02:00"
,
"date_finish"
:
"2025-07-11T09:26:14+02:00"
,
"operating_reset_at"
:
1752215774
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
Identifier of the created directory element
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
Access denied.
No rights to perform the operation
400
Invalid parameters.
Invalid parameters were provided
400
Specified entity type is not supported.
An unsupported directory type was specified
400
The field ENTITY_ID is required.
ENTITY_ID
is not specified
400
The field STATUS_ID is required.
STATUS_ID
is not specified
400
Duplicate STATUS_ID.
Such
STATUS_ID
already exists
400
Error on creating status.
Error creating the element
400
Cannot create an intermediate stage after success
400
The required field "Title" is not filled
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
Get a List of Directory Items by Filter crm.status.list
Get a directory item by ID crm.status.get
Update CRM Status Element `crm.status.update`
Delete CRM Status Element `crm.status.delete`
Get Description of CRM Status Fields
Get CRM Status Entity Types
How to Create a New Sales Funnel with Stages in a Smart Process
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Update a directory item

---

## Update CRM Status Element <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-z0tjywqn">crm.status.update</code>

**Source:** https://apidocs.bitrix24.com/api-reference/crm/status/crm-status-update

Update CRM Status Element <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-z0tjywqn">crm.status.update</code> | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update CRM Status Element
crm.status.update
Method Parameters
Fields Parameter
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: user with CRM administrator rights
The method
crm.status.update
updates the parameters of an existing CRM status element.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the status element to be updated. You can get the list using the method
crm.status.list
fields
*
object
Array of fields to update. The list of available fields is described
below
Fields Parameter
Fields Parameter
Name
type
Description
NAME
string
Name
SORT
integer
Sorting
COLOR
string
Hex color code, for example
#39A8EF
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
'{"id":123,"fields":{"NAME":"New Name","COLOR":"#00A9F4"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.status.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":123,"fields":{"NAME":"New Name","COLOR":"#00A9F4"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.status.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.status.update'
,
{
id
:
123
,
fields
: {
NAME
:
'New Name'
,
COLOR
:
'#00A9F4'
}
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
'crm.status.update'
,
[
'id'
=>
123
,
'fields'
=> [
'NAME'
=>
'New Name'
,
'COLOR'
=>
'#00A9F4'
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
echo
'Error updating status: '
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
'Error updating status: '
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
"crm.status.update"
,
{
id
:
123
,
fields
: {
NAME
:
"New Name"
,
COLOR
:
"#00A9F4"
}
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
'crm.status.update'
,
[
'id'
=>
123
,
'fields'
=> [
'NAME'
=>
'New Name'
,
'COLOR'
=>
'#00A9F4'
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
1752149050.805837
,
"finish"
:
1752149050.842422
,
"duration"
:
0.036585092544555664
,
"processing"
:
0.009345054626464844
,
"date_start"
:
"2025-07-10T15:04:10+02:00"
,
"date_finish"
:
"2025-07-10T15:04:10+02:00"
,
"operating_reset_at"
:
1752149650
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
"Invalid identifier."
,
"error_description"
:
"An invalid identifier was provided."
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
Access denied.
No rights to perform the operation
400
Invalid identifier.
An invalid identifier was provided
400
Status is not found.
Element not found
400
Error on updating status.
Error while updating the element
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
Get Description of CRM Status Fields
Get a List of Directory Items by Filter crm.status.list
Get a directory item by ID crm.status.get
Create CRM Status Element crm.status.add
Delete CRM Status Element `crm.status.delete`
How to Create a New Sales Funnel with Stages in a Smart Process
Copied
Was the article helpful?
Yes
No
Previous
Create a new item in the directory
Next
Get directory types

---

## Get CRM Status Entity Types

**Source:** https://apidocs.bitrix24.com/api-reference/crm/status/crm-status-entity-types

Get CRM Status Entity Types | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get CRM Status Entity Types
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
crm.status.entity.types
returns a list of all supported types of directories,
ENTITY_ID
objects.
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
-H
"Accept: application/json"
\
-d
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.status.entity.types
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
https://**put_your_bitrix24_address**/rest/crm.status.entity.types
try
{
const
response =
await
$b24.
callMethod
(
'crm.status.entity.types'
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
'crm.status.entity.types'
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
'Error calling crm.status.entity.types: '
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
"crm.status.entity.types"
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
'crm.status.entity.types'
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
"STATUS"
,
"NAME"
:
"Lead Stages"
,
"SEMANTIC_INFO"
:
{
"START_FIELD"
:
"NEW"
,
"FINAL_SUCCESS_FIELD"
:
"CONVERTED"
,
"FINAL_UNSUCCESS_FIELD"
:
"JUNK"
,
"FINAL_SORT"
:
0
}
,
"ENTITY_TYPE_ID"
:
1
}
,
{
"ID"
:
"SOURCE"
,
"NAME"
:
"Sources"
}
,
{
"ID"
:
"CONTACT_TYPE"
,
"NAME"
:
"Contact Type"
}
,
{
"ID"
:
"COMPANY_TYPE"
,
"NAME"
:
"Company Type"
}
,
{
"ID"
:
"EMPLOYEES"
,
"NAME"
:
"Number of Employees"
}
,
{
"ID"
:
"INDUSTRY"
,
"NAME"
:
"Industry"
}
,
{
"ID"
:
"DEAL_TYPE"
,
"NAME"
:
"Deal Type"
}
,
{
"ID"
:
"SMART_INVOICE_STAGE_5"
,
"NAME"
:
"Invoice Stages"
,
"SEMANTIC_INFO"
:
[
]
,
"PREFIX"
:
"DT31_5"
,
"FIELD_ATTRIBUTE_SCOPE"
:
"category_5"
,
"ENTITY_TYPE_ID"
:
31
,
"IS_ENABLED"
:
true
,
"CATEGORY_ID"
:
5
}
,
{
"ID"
:
"DEAL_STAGE_1"
,
"NAME"
:
"Newest Deal Stages"
,
"PARENT_ID"
:
"DEAL_STAGE"
,
"SEMANTIC_INFO"
:
{
"START_FIELD"
:
"C1:NEW"
,
"FINAL_SUCCESS_FIELD"
:
"C1:WON"
,
"FINAL_UNSUCCESS_FIELD"
:
"C1:LOSE"
,
"FINAL_SORT"
:
0
}
,
"PREFIX"
:
"C1"
,
"FIELD_ATTRIBUTE_SCOPE"
:
"category_1"
,
"ENTITY_TYPE_ID"
:
2
,
"CATEGORY_ID"
:
"1"
}
,
{
"ID"
:
"DEAL_STAGE"
,
"NAME"
:
"General Deal Stages"
,
"SEMANTIC_INFO"
:
{
"START_FIELD"
:
"NEW"
,
"FINAL_SUCCESS_FIELD"
:
"WON"
,
"FINAL_UNSUCCESS_FIELD"
:
"LOSE"
,
"FINAL_SORT"
:
0
}
,
"FIELD_ATTRIBUTE_SCOPE"
:
""
,
"ENTITY_TYPE_ID"
:
2
,
"CATEGORY_ID"
:
0
}
,
{
"ID"
:
"QUOTE_STATUS"
,
"NAME"
:
"Estimate Stages"
,
"SEMANTIC_INFO"
:
{
"START_FIELD"
:
"DRAFT"
,
"FINAL_SUCCESS_FIELD"
:
"APPROVED"
,
"FINAL_UNSUCCESS_FIELD"
:
"DECLINED"
,
"FINAL_SORT"
:
0
}
,
"ENTITY_TYPE_ID"
:
7
}
,
{
"ID"
:
"HONORIFIC"
,
"NAME"
:
"Honorifics"
}
,
{
"ID"
:
"CALL_LIST"
,
"NAME"
:
"Call Statuses"
}
,
{
"ID"
:
"SMART_DOCUMENT_STAGE_13"
,
"NAME"
:
"Document Stages"
,
"SEMANTIC_INFO"
:
[
]
,
"PREFIX"
:
"DT36_13"
,
"FIELD_ATTRIBUTE_SCOPE"
:
"category_13"
,
"ENTITY_TYPE_ID"
:
36
,
"IS_ENABLED"
:
true
,
"CATEGORY_ID"
:
13
}
,
{
"ID"
:
"DYNAMIC_177_STAGE_7"
,
"NAME"
:
"Equipment Purchase (General)"
,
"SEMANTIC_INFO"
:
[
]
,
"PREFIX"
:
"DT177_7"
,
"FIELD_ATTRIBUTE_SCOPE"
:
"category_7"
,
"ENTITY_TYPE_ID"
:
177
,
"IS_ENABLED"
:
true
,
"CATEGORY_ID"
:
7
,
"CATEGORY_NAME"
:
"General"
,
"CATEGORY_SORT"
:
500
,
"IS_DEFAULT_CATEGORY"
:
true
}
,
{
"ID"
:
"DYNAMIC_177_STAGE_9"
,
"NAME"
:
"Equipment Purchase (Second Funnel)"
,
"SEMANTIC_INFO"
:
[
]
,
"PREFIX"
:
"DT177_9"
,
"FIELD_ATTRIBUTE_SCOPE"
:
"category_9"
,
"ENTITY_TYPE_ID"
:
177
,
"IS_ENABLED"
:
true
,
"CATEGORY_ID"
:
9
,
"CATEGORY_NAME"
:
"Second Funnel"
,
"CATEGORY_SORT"
:
500
,
"IS_DEFAULT_CATEGORY"
:
false
}
]
,
"time"
:
{
"start"
:
1752142616.128453
,
"finish"
:
1752142616.215683
,
"duration"
:
0.08722996711730957
,
"processing"
:
0.018637895584106445
,
"date_start"
:
"2025-07-10T13:16:56+02:00"
,
"date_finish"
:
"2025-07-10T13:16:56+02:00"
,
"operating_reset_at"
:
1752143216
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
Array of objects describing the types of directories
(detailed field description)
time
time
Information about the request execution time
Fields of the result object
Fields of the result object
Name
type
Description
ID
string
Object identifier, use the value in the
ENTITY_ID
field of the
crm.status.*
methods
NAME
string
Name
ENTITY_TYPE_ID
integer
CRM object type
to which the status belongs
SEMANTIC_INFO
object
Information about the semantics of status stages
PREFIX
string
Prefix for the stage code in the funnel
FIELD_ATTRIBUTE_SCOPE
string
Field application area, funnel
IS_ENABLED
boolean
Activity
CATEGORY_ID
integer
Funnel identifier
PARENT_ID
string
ID of the parent element
CATEGORY_NAME
string
Funnel name
CATEGORY_SORT
integer
Funnel sorting
IS_DEFAULT_CATEGORY
boolean
Default funnel
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
Get Description of CRM Status Fields
Get a List of Directory Items by Filter crm.status.list
Create CRM Status Element crm.status.add
Update CRM Status Element `crm.status.update`
Delete CRM Status Element `crm.status.delete`
Copied
Was the article helpful?
Yes
No
Previous
Update a directory item
Next
Get directory items by type

---

## Get directory items by type crm.status.entity.items

**Source:** https://apidocs.bitrix24.com/api-reference/crm/status/crm-status-entity-items

Get directory items by type crm.status.entity.items | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get directory items by type crm.status.entity.items
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
crm.status.entity.items
returns all directory items by the identifier
ENTITY_ID
, sorted by the
SORT
field. This method is similar to
crm.status.list
, except that the latter allows you to define sorting rules.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityId
*
string
Type of the directory, for example
DEAL_STAGE
,
SOURCE
. You can get a list of types using the method
crm.status.entity.types
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
'{"entityId":"DEAL_STAGE"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.status.entity.items
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityId":"DEAL_STAGE","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.status.entity.items
try
{
const
response =
await
$b24.
callMethod
(
"crm.status.entity.items"
,
{
entityId
:
"DEAL_STAGE"
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
'crm.status.entity.items'
,
[
'entityId'
=>
'DEAL_STAGE'
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
'Error fetching status entity items: '
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
"crm.status.entity.items"
,
{
entityId
:
"DEAL_STAGE"
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
'crm.status.entity.items'
,
[
'entityId'
=>
'DEAL_STAGE'
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
"NAME"
:
"New"
,
"SORT"
:
10
,
"STATUS_ID"
:
"NEW"
}
,
{
"NAME"
:
"Document Preparation"
,
"SORT"
:
20
,
"STATUS_ID"
:
"PREPARATION"
}
,
{
"NAME"
:
"Prepayment Invoice"
,
"SORT"
:
30
,
"STATUS_ID"
:
"PREPAYMENT_INVOICE"
}
,
{
"NAME"
:
"In Progress"
,
"SORT"
:
40
,
"STATUS_ID"
:
"EXECUTING"
}
,
{
"NAME"
:
"Final Invoice"
,
"SORT"
:
50
,
"STATUS_ID"
:
"FINAL_INVOICE"
}
,
{
"NAME"
:
"Deal Won"
,
"SORT"
:
60
,
"STATUS_ID"
:
"WON"
}
,
{
"NAME"
:
"Deal Lost"
,
"SORT"
:
70
,
"STATUS_ID"
:
"LOSE"
}
,
{
"NAME"
:
"Analyzing Cause of Loss"
,
"SORT"
:
80
,
"STATUS_ID"
:
"APOLOGY"
}
]
,
"time"
:
{
"start"
:
1752144806.703358
,
"finish"
:
1752144806.76889
,
"duration"
:
0.06553196907043457
,
"processing"
:
0.010729789733886719
,
"date_start"
:
"2025-07-10T13:53:26+02:00"
,
"date_finish"
:
"2025-07-10T13:53:26+02:00"
,
"operating_reset_at"
:
1752145406
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
Array of directory items
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
"The parameter entityId is not defined or invalid."
,
"error_description"
:
"The identifier of the directory is not specified or is incorrect."
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
Access denied.
No permission to perform the operation
400
The parameter entityId is not defined or invalid.
The identifier of the directory is not specified or is incorrect
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
Get Description of CRM Status Fields
Get a List of Directory Items by Filter crm.status.list
Create CRM Status Element crm.status.add
Update CRM Status Element `crm.status.update`
Delete CRM Status Element `crm.status.delete`
Copied
Was the article helpful?
Yes
No
Previous
Get directory types
Next
Get a directory item by ID

---

## Get a directory item by ID crm.status.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/status/crm-status-get

Get a directory item by ID crm.status.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a directory item by ID crm.status.get
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
crm.status.get
returns the parameters of a directory item by its ID.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the directory item. You can get a list of items with identifiers using the method
crm.status.list
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
'{"id":123}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.status.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":123,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.status.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.status.get'
,
{
id
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
'crm.status.get'
,
[
'id'
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
'Error getting CRM status: '
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
"crm.status.get"
,
{
id
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
'crm.status.get'
,
[
'id'
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
HTTP status:
200
{
"result"
:
{
"ID"
:
"733"
,
"ENTITY_ID"
:
"DYNAMIC_1038_STAGE_37"
,
"STATUS_ID"
:
"DT1038_37:SUCCESS"
,
"NAME"
:
"Success"
,
"NAME_INIT"
:
"Success"
,
"SORT"
:
"40"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
"37"
,
"COLOR"
:
"#00ff00"
,
"SEMANTICS"
:
"S"
}
,
"time"
:
{
"start"
:
1752133970.651926
,
"finish"
:
1752133970.690207
,
"duration"
:
0.03828096389770508
,
"processing"
:
0.0060749053955078125
,
"date_start"
:
"2025-07-10T10:52:50+02:00"
,
"date_finish"
:
"2025-07-10T10:52:50+02:00"
,
"operating_reset_at"
:
1752134570
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
Identifier of the directory item
ENTITY_ID
string
Identifier of the object to which the directory relates
STATUS_ID
string
Status value code
NAME
string
Name
NAME_INIT
string
Initial name
SORT
integer
Sorting
SYSTEM
string
Indicator of system value
CATEGORY_ID
integer
Identifier of the funnel to which the status relates
COLOR
string
Status color for kanban
SEMANTICS
string
Group of stages
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
"Status is not found."
,
"error_description"
:
"Directory item not found."
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
Access denied.
No permission to perform the operation
400
Status is not found.
Directory item not found
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
Get Description of CRM Status Fields
Get a List of Directory Items by Filter crm.status.list
Create CRM Status Element crm.status.add
Update CRM Status Element `crm.status.update`
Delete CRM Status Element `crm.status.delete`
Copied
Was the article helpful?
Yes
No
Previous
Get directory items by type
Next
Get a list of items by filter

---

## Get a List of Directory Items by Filter crm.status.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/status/crm-status-list

Get a List of Directory Items by Filter crm.status.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a List of Directory Items by Filter crm.status.list
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
crm.status.list
returns a list of directory items based on the filter.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
order
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
field_n
— the name of the field by which the directory items will be sorted
value_n
— a
string
value equal to:
ASC
— ascending sort
DESC
— descending sort
The list of fields for sorting can be found using the method
crm.status.fields
filter
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
field_n
— the name of the field by which the selection of items will be filtered
value_n
— the filter value
The list of fields for filtering can be found using the method
crm.status.fields
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
'{"order":{"SORT":"ASC"},"filter":{"ENTITY_ID":"DEAL_STAGE"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.status.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"SORT":"ASC"},"filter":{"ENTITY_ID":"DEAL_STAGE"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.status.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.status.list'
,
{
order
: {
SORT
:
"ASC"
},
filter
: {
ENTITY_ID
:
"DEAL_STAGE"
}
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.status.list'
, {
order
: {
SORT
:
"ASC"
},
filter
: {
ENTITY_ID
:
"DEAL_STAGE"
}
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. Suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.status.list'
, {
order
: {
SORT
:
"ASC"
},
filter
: {
ENTITY_ID
:
"DEAL_STAGE"
}
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
'crm.status.list'
,
[
'order'
=> [
'SORT'
=>
'ASC'
],
'filter'
=> [
'ENTITY_ID'
=>
'DEAL_STAGE'
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
'Error fetching status list: '
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
"crm.status.list"
,
{
order
: {
SORT
:
"ASC"
},
filter
: {
ENTITY_ID
:
"DEAL_STAGE"
}
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
'crm.status.list'
,
[
'order'
=> [
'SORT'
=>
'ASC'
],
'filter'
=> [
'ENTITY_ID'
=>
'DEAL_STAGE'
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
"101"
,
"ENTITY_ID"
:
"DEAL_STAGE"
,
"STATUS_ID"
:
"NEW"
,
"NAME"
:
"New"
,
"NAME_INIT"
:
"New"
,
"SORT"
:
"10"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#39A8EF"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#39A8EF"
}
}
,
{
"ID"
:
"103"
,
"ENTITY_ID"
:
"DEAL_STAGE"
,
"STATUS_ID"
:
"PREPARATION"
,
"NAME"
:
"Document Preparation"
,
"NAME_INIT"
:
""
,
"SORT"
:
"20"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#2FC6F6"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#2FC6F6"
}
}
,
{
"ID"
:
"105"
,
"ENTITY_ID"
:
"DEAL_STAGE"
,
"STATUS_ID"
:
"PREPAYMENT_INVOICE"
,
"NAME"
:
"Prepayment Invoice"
,
"NAME_INIT"
:
""
,
"SORT"
:
"30"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#55D0E0"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#55D0E0"
}
}
,
{
"ID"
:
"107"
,
"ENTITY_ID"
:
"DEAL_STAGE"
,
"STATUS_ID"
:
"EXECUTING"
,
"NAME"
:
"In Progress"
,
"NAME_INIT"
:
""
,
"SORT"
:
"40"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#47E4C2"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#47E4C2"
}
}
,
{
"ID"
:
"109"
,
"ENTITY_ID"
:
"DEAL_STAGE"
,
"STATUS_ID"
:
"FINAL_INVOICE"
,
"NAME"
:
"Final Invoice"
,
"NAME_INIT"
:
""
,
"SORT"
:
"50"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#FFA900"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#FFA900"
}
}
,
{
"ID"
:
"111"
,
"ENTITY_ID"
:
"DEAL_STAGE"
,
"STATUS_ID"
:
"WON"
,
"NAME"
:
"Deal Successful"
,
"NAME_INIT"
:
"Deal Successful"
,
"SORT"
:
"60"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#7BD500"
,
"SEMANTICS"
:
"S"
,
"EXTRA"
:
{
"SEMANTICS"
:
"success"
,
"COLOR"
:
"#7BD500"
}
}
,
{
"ID"
:
"113"
,
"ENTITY_ID"
:
"DEAL_STAGE"
,
"STATUS_ID"
:
"LOSE"
,
"NAME"
:
"Deal Failed"
,
"NAME_INIT"
:
"Deal Failed"
,
"SORT"
:
"70"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#FF5752"
,
"SEMANTICS"
:
"F"
,
"EXTRA"
:
{
"SEMANTICS"
:
"failure"
,
"COLOR"
:
"#FF5752"
}
}
,
{
"ID"
:
"115"
,
"ENTITY_ID"
:
"DEAL_STAGE"
,
"STATUS_ID"
:
"APOLOGY"
,
"NAME"
:
"Reason for Failure Analysis"
,
"NAME_INIT"
:
""
,
"SORT"
:
"80"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#FF5752"
,
"SEMANTICS"
:
"F"
,
"EXTRA"
:
{
"SEMANTICS"
:
"apology"
,
"COLOR"
:
"#FF5752"
}
}
]
,
"total"
:
8
,
"time"
:
{
"start"
:
1752146147.312812
,
"finish"
:
1752146147.354549
,
"duration"
:
0.04173684120178223
,
"processing"
:
0.00507807731628418
,
"date_start"
:
"2025-07-10T14:15:47+02:00"
,
"date_finish"
:
"2025-07-10T14:15:47+02:00"
,
"operating_reset_at"
:
1752146747
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
An array of objects with information about directory items
total
integer
The total number of found items
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
Access denied.
No permission to perform the operation
400
Invalid parameters.
Invalid parameters were provided
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
Get Description of CRM Status Fields
Get a directory item by ID crm.status.get
Create CRM Status Element crm.status.add
Update CRM Status Element `crm.status.update`
Delete CRM Status Element `crm.status.delete`
How to Filter Items by Stage Name
How to Get a List of Stages with Semantics for CRM Objects
How to Create a New Sales Funnel with Stages in a Smart Process
Copied
Was the article helpful?
Yes
No
Previous
Get a directory item by ID
Next
Delete a directory item

---

## Delete CRM Status Element <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-yx192bjj">crm.status.delete</code>

**Source:** https://apidocs.bitrix24.com/api-reference/crm/status/crm-status-delete

Delete CRM Status Element <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-yx192bjj">crm.status.delete</code> | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete CRM Status Element
crm.status.delete
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
Who can execute the method: user with CRM administrator rights
The method
crm.status.delete
removes a status element by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the status element to be deleted. You can obtain a list of identifiers using the method
crm.status.list
params
string
Available flags:
FORCED
— flag for forcibly deleting system elements. Default is
N
.
Pass
Y
to delete the element even if it is a system element
Code Examples
Code Examples
How to Use Examples in Documentation
Deleting a regular element.
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
'{"id":123}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.status.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":123,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.status.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.status.delete"
,
{
id
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
'crm.status.delete'
,
[
'id'
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
'Error deleting status: '
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
"crm.status.delete"
,
{
id
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
'crm.status.delete'
,
[
'id'
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
Deleting a system element.
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
'{"id":123,"params":{"FORCED":"Y"}}'
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.status.delete
curl -X POST -H
"Content-Type: application/json"
-H
"Accept: application/json"
-d
'{"id":123,"params":{"FORCED":"Y"},"auth":"**put_access_token_here**"}'
https://**put_your_bitrix24_address**/rest/crm.status.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.status.delete"
,
{
id
:
123
,
params
: {
FORCED
:
"Y"
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
'crm.status.delete'
,
[
'id'
=>
123
,
'params'
=> [
'FORCED'
=>
'Y'
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
'Error deleting CRM status: '
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
"crm.status.delete"
,
{
id
:
123
,
params
: {
FORCED
:
"Y"
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
'crm.status.delete'
,
[
'id'
=>
123
,
'params'
=> [
'FORCED'
=>
'Y'
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
1752145688.808395
,
"finish"
:
1752145688.842539
,
"duration"
:
0.03414416313171387
,
"processing"
:
0.010373115539550781
,
"date_start"
:
"2025-07-10T14:08:08+02:00"
,
"date_finish"
:
"2025-07-10T14:08:08+02:00"
,
"operating_reset_at"
:
1752146288
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
on success
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
"Invalid identifier."
,
"error_description"
:
"An invalid identifier was provided."
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
Access denied.
No permission to perform the operation
400
Invalid identifier.
An invalid identifier was provided
400
Status is not found.
Element not found
400
CRM System Status can be deleted only if parameter FORCED is specified and equal to "Y".
A system element can only be deleted with the
FORCED = "Y"
parameter
400
There are active items in this status.
There are related items, deletion is not possible
400
Error on deleting status.
Error while deleting the element
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
Get Description of CRM Status Fields
Get a List of Directory Items by Filter crm.status.list
Get a directory item by ID crm.status.get
Create CRM Status Element crm.status.add
Update CRM Status Element `crm.status.update`
Copied
Was the article helpful?
Yes
No
Previous
Get a list of items by filter
Next
Get directory fields

---

## Get Description of CRM Status Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/status/crm-status-fields

Get Description of CRM Status Fields | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Description of CRM Status Fields
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
crm.status.fields
returns the description of CRM reference fields.
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
-H
"Accept: application/json"
\
-d
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.status.fields
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
https://**put_your_bitrix24_address**/rest/crm.status.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.status.fields"
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
'crm.status.fields'
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
'Error fetching CRM status fields: '
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
"crm.status.fields"
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
'crm.status.fields'
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
"ENTITY_ID"
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
"Entity ID"
}
,
"STATUS_ID"
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
"Status"
}
,
"SORT"
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
"Sorting"
}
,
"NAME"
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
"Name"
}
,
"NAME_INIT"
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
"Default Name"
}
,
"SYSTEM"
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
"System"
}
,
"CATEGORY_ID"
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
"CATEGORY_ID"
}
,
"COLOR"
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
"COLOR"
}
,
"SEMANTICS"
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
"SEMANTICS"
}
,
"EXTRA"
:
{
"type"
:
"crm_status_extra"
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
"Additional Fields"
}
}
,
"time"
:
{
"start"
:
1752132864.335154
,
"finish"
:
1752132864.366912
,
"duration"
:
0.03175783157348633
,
"processing"
:
0.002053976058959961
,
"date_start"
:
"2025-07-10T10:34:24+02:00"
,
"date_finish"
:
"2025-07-10T10:34:24+02:00"
,
"operating_reset_at"
:
1752133464
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
Object with field descriptions
(detailed description)
time
time
Information about the request execution time
Fields of the result object
Fields of the result object
Name
type
Description
ID
integer
Status identifier, used in methods
crm.status.*
ENTITY_ID
string
Status type identifier
STATUS_ID
string
Status value code, used in CRM object methods
SORT
integer
Sorting order
NAME
string
Name
NAME_INIT
string
Default name
SYSTEM
char
Flag indicating whether the status is system
CATEGORY_ID
integer
Identifier of the funnel to which the status stage belongs
COLOR
string
Color of the status stage for Kanban
SEMANTICS
char
Group of stages:
"S"
— success,
"F"
— failure,
""
— in progress
EXTRA
object
Additional fields
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
Get a List of Directory Items by Filter crm.status.list
Get a directory item by ID crm.status.get
Create CRM Status Element crm.status.add
Update CRM Status Element `crm.status.update`
Delete CRM Status Element `crm.status.delete`
Copied
Was the article helpful?
Yes
No
Previous
Delete a directory item
Next
Overview of Methods

---

## Get Stage History with crm.stagehistory.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/crm-stage-history-list

Get Stage History with crm.stagehistory.list | Bitrix24 REST API and Marketplace Applications
Get Stage History with crm.stagehistory.list
Get Stage History with crm.stagehistory.list
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
crm.stagehistory.list
returns records of stage movement history for the following elements:
leads
,
deals
,
old invoices
,
new invoices
,
SPAs
.
Method Parameters
Method Parameters
Name
type
Description
entityTypeId
integer
Identifier of the object type. Can take the following values:
1
— lead,
2
— deal,
5
— invoice (old),
31
- invoice (new),
numeric identifier of a
custom type
, for example
130
order
object
Sorting list, where the key is the field and the value is
ASC
or
DESC
filter
object
Filtering list. The filter supports the use of exact values, arrays of values, and modifiers:
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
— equals, exact match (used by default)
!=
— not equal
!
— not equal
select
object
List of fields to retrieve
start
integer
Offset for pagination. The pagination logic is standard for
list methods
Code Examples
Code Examples
How to Use Examples in Documentation
Get stage movement history for the deal with
ID=1
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
'{"entityTypeId":2,"order":{"ID":"ASC"},"filter":{"OWNER_ID":1},"select":["ID","STAGE_ID","CREATED_TIME"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.stagehistory.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"order":{"ID":"ASC"},"filter":{"OWNER_ID":1},"select":["ID","STAGE_ID","CREATED_TIME"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.stagehistory.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
const
parameters = {
entityTypeId
:
2
,
order
: {
"ID"
:
"ASC"
},
filter
: {
"OWNER_ID"
:
1
},
select
: [
"ID"
,
"STAGE_ID"
,
"CREATED_TIME"
]
};
try
{
const
response =
await
$b24.
callListMethod
(
'crm.stagehistory.list'
,
parameters,
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.stagehistory.list'
, parameters,
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.stagehistory.list'
, parameters,
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
'crm.stagehistory.list'
,
[
'entityTypeId'
=>
2
,
'order'
=> [
'ID'
=>
'ASC'
],
'filter'
=> [
'OWNER_ID'
=>
1
],
'select'
=> [
'ID'
,
'STAGE_ID'
,
'CREATED_TIME'
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
'Error listing stage history: '
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
"crm.stagehistory.list"
,
{
entityTypeId
:
2
,
order
: {
"ID"
:
"ASC"
},
filter
: {
"OWNER_ID"
:
1
},
select
: [
"ID"
,
"STAGE_ID"
,
"CREATED_TIME"
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
'crm.stagehistory.list'
,
[
'entityTypeId'
=>
2
,
'order'
=> [
'ID'
=>
'ASC'
],
'filter'
=> [
'OWNER_ID'
=>
1
],
'select'
=> [
'ID'
,
'STAGE_ID'
,
'CREATED_TIME'
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
Get stage movement history for the SPA with
entityTypeId=130
and element
OWNER_ID=29
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
'{"entityTypeId":130,"order":{"ID":"ASC"},"filter":{"OWNER_ID":29},"select":["ID","STAGE_ID","CREATED_TIME"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.stagehistory.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":130,"order":{"ID":"ASC"},"filter":{"OWNER_ID":29},"select":["ID","STAGE_ID","CREATED_TIME"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.stagehistory.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
const
parameters = {
entityTypeId
:
130
,
order
: {
"ID"
:
"ASC"
},
filter
: {
"OWNER_ID"
:
29
},
select
: [
"ID"
,
"STAGE_ID"
,
"CREATED_TIME"
]
};
try
{
const
response =
await
$b24.
callListMethod
(
'crm.stagehistory.list'
,
parameters,
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.stagehistory.list'
, parameters,
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.stagehistory.list'
, parameters,
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
'crm.stagehistory.list'
,
[
'entityTypeId'
=>
130
,
'order'
=> [
'ID'
=>
'ASC'
],
'filter'
=> [
'OWNER_ID'
=>
29
],
'select'
=> [
'ID'
,
'STAGE_ID'
,
'CREATED_TIME'
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
'Error listing stage history: '
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
"crm.stagehistory.list"
,
{
entityTypeId
:
130
,
order
: {
"ID"
:
"ASC"
},
filter
: {
"OWNER_ID"
:
29
},
select
: [
"ID"
,
"STAGE_ID"
,
"CREATED_TIME"
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
'crm.stagehistory.list'
,
[
'entityTypeId'
=>
130
,
'order'
=> [
'ID'
=>
'ASC'
],
'filter'
=> [
'OWNER_ID'
=>
29
],
'select'
=> [
'ID'
,
'STAGE_ID'
,
'CREATED_TIME'
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
"items"
:
[
{
"ID"
:
35
,
"TYPE_ID"
:
1
,
"OWNER_ID"
:
21
,
"CREATED_TIME"
:
"2024-04-25T14:59:11+00:00"
,
"CATEGORY_ID"
:
0
,
"STAGE_SEMANTIC_ID"
:
"P"
,
"STAGE_ID"
:
"NEW"
}
]
}
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
1724106224.858572
,
"finish"
:
1724106225.344968
,
"duration"
:
0.48639607429504395
,
"processing"
:
0.11864185333251953
,
"date_start"
:
"2024-08-15T22:15:44+00:00"
,
"date_finish"
:
"2024-08-15T22:15:45+00:00"
,
"operating"
:
0.11855506896972656
}
}
Returned Data
Returned Data
Name
type
Description
result
array
Root element of the response, contains an array of
items
. Each object is an array with keys
time
time
Information about the request execution time
Object items
Object items
Name
type
Description
ID
int
Record identifier
TYPE_ID
int
Record type. Can take the following values:
1
— creation of an element,
2
— transfer to an intermediate stage,
3
— transfer to the final stage,
5
— change of funnel
OWNER_ID
int
Identifier of the object in which the stage changed
CREATED_TIME
datetime
Identifier of the created element, equal to the time of transferring the element to the stage
Additionally, there are fields specific to different object types:
for leads and old invoices
for deals, new invoices, and SPAs
Name
type
Description
STATUS_SEMANTIC_ID
int
Stage semantics:
P
— intermediate stage,
S
— successful stage,
F
— failed stage
STATUS_ID
int
Identifier of the stage
Name
type
Description
CATEGORY_ID
int
Identifier of the funnel
STAGE_SEMANTIC_ID
int
Stage semantics:
P
— intermediate stage,
S
— successful stage,
F
— failed stage
STAGE_ID
int
Identifier of the stage
Error Handling
Error Handling
HTTP Status:
401
,
400
{
"error"
:
0
,
"error_description"
:
"SHIPMENT_DOCUMENT entity is not supported"
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
Action is allowed only for intranet users
User is not an intranet user
400
ENTITY_TYPE_NOT_SUPPORTED
Entity type
TYPE
is not supported
Occurs when an invalid
entityTypeId
is passed
400
INVALID_ARG_VALUE
Invalid filter: field '
field
' is not allowed in filter
The field
field
passed in
filter
is not available for filtering
400
INVALID_ARG_VALUE
Invalid filter: field '
field
' has invalid value
The value passed for field
field
in
filter
is incorrect
400
INVALID_ARG_VALUE
Invalid order: field '
field
' is not allowed in order
The field
field
passed in
order
is not available for sorting
400
INVALID_ARG_VALUE
Invalid order: allowed sort directions are
ASC, DESC
. But got '
orderValue
' for field '
field
'
The value
orderValue
passed for field
field
in the
order
parameter is incorrect
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
Overview of CRM
Fields of Main CRM Objects
Copied
Was the article helpful?
Yes
No
Previous
Get VAT Rate Fields
Next
Overview

---

