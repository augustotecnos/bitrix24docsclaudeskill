---
description: 'Common/System API: System info, scopes, methods, health checks'
methods:
- app.info
- app.option.get
- app.option.set
- crm.activity.add
- crm.documentgenerator
- crm.lead.add
- event.bind
- user.access
- user.add
- user.admin
- user.counters
- user.current
- user.fields
- user.get
- user.history.fields.list
- user.history.list
- user.online
- user.option.get
- user.option.set
- user.search
- user.update
- user.userfield
pages: 27
title: 'Common/System API: System info, scopes, methods, health checks'
---
# Common/System API: System info, scopes, methods, health checks
> Common/System API: System info, scopes, methods, health checks
> **27 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Access Permissions for Methods](#access-permissions-for-methods)
- [Available Scopes in Bitrix24](#available-scopes-in-bitrix24)
- [Method Calls with Confirmation](#method-calls-with-confirmation)
- [General Methods and Events](#general-methods-and-events)
- [Overview of Methods](#overview-of-methods)
- [Get a list of available methods method.get](#get-a-list-of-available-methods-methodget)
- [Get a List of Available Permissions Scope](#get-a-list-of-available-permissions-scope)
- [Show information about the app app.info](#show-information-about-the-app-appinfo)
- [Get Access Permission Names access.name](#get-access-permission-names-accessname)
- [Get information about feature availability on the account feature.get](#get-information-about-feature-availability-on-the-)
- [Get Current Server Time server.time](#get-current-server-time-servertime)
- [Get a List of Available Methods](#get-a-list-of-available-methods)
- [Overview of Methods](#overview-of-methods)
- [Determine Access Permissions for Application Settings user.admin](#determine-access-permissions-for-application-setti)
- [Determine the user.access permissions set](#determine-the-useraccess-permissions-set)
- [Get Basic Information About the Current User Profile](#get-basic-information-about-the-current-user-profi)
- [Overview of Methods](#overview-of-methods)
- [Bind Data to the app.option.set Method](#bind-data-to-the-appoptionset-method)
- [Get Application-Linked Data app.option.get](#get-application-linked-data-appoptionget)
- [Bind Data to User and Application user.option.set](#bind-data-to-user-and-application-useroptionset)
- [Get User Data Associated with the Application user.option.get](#get-user-data-associated-with-the-application-user)
- [List of Events](#list-of-events)
- [Event after successful installation of the application OnAppInstall](#event-after-successful-installation-of-the-applica)
- [Event on Application Uninstallation onAppUninstall](#event-on-application-uninstallation-onappuninstall)
- [Event onAppPayment](#event-onapppayment)
- [Event on receiving permission to use onAppMethodConfirm methods](#event-on-receiving-permission-to-use-onappmethodco)
- [Event onUserAdd](#event-onuseradd)

---

## Access Permissions for Methods

**Source:** https://apidocs.bitrix24.com/api-reference/scopes/index

Access Permissions for Methods | Bitrix24 REST API and Marketplace Applications
Access Permissions for Methods
Access Permissions for Methods
Access permissions for executing specific REST API methods are managed through a scope mechanism (SCOPE). When you add a mass-market solution in the Partner's area or an on-premise solution to your specific Bitrix24, you specify the list of necessary Bitrix24 scopes required for the application to function.
The binding to a specific scope is indicated in the description of each REST method at the very beginning. For example,
Scope:
CRM
Who can execute the method: any user
Also, pay attention to the note "Who can execute the method." Some methods can only be called on behalf of a user with administrative rights in a specific Bitrix24.
Let's consider a specific situation where your solution integrates Bitrix24 with external telephony, and you are using the methods
telephony.externalcall.register
and
telephony.externalcall.finish
, which also add leads to the CRM, but do not explicitly call CRM methods like
crm.lead.add
and
crm.activity.add
. In this case, your application will require the telephony scope, while the crm scope will not be necessary.
Available Scopes in Bitrix24
Method Calls with Confirmation
Copied
Was the article helpful?
Yes
No
Previous
Data Types and Parameter Formats
Next
Available scopes

---

## Available Scopes in Bitrix24

**Source:** https://apidocs.bitrix24.com/api-reference/scopes/permissions

Available Scopes in Bitrix24 | Bitrix24 REST API and Marketplace Applications
Available Scopes in Bitrix24
Available Scopes in Bitrix24
Scope Code
Scope Name
Bitrix24 Tool
ai_admin
Channel for registering a custom service for processing requests
Copilot
biconnector
BI Analytics Connector
BIconnector
bizproc
Business Processes
Business Processes, RPA, CRM Automation Rules
booking
Online Booking
Online Booking
calendar
Calendar
Calendar
call
Telephony (making calls). The scope includes methods:
voximplant.infocall.startwithsound
,
voximplant.infocall.startwithtext
Telephony
catalog
Trade Catalog
Trade Catalog, inventory management
crm
CRM
CRM
documentgenerator, crm.documentgenerator
Document Generator
,
CRM Document Generator
Document Generator
delivery
Deliveries
Online Store, CRM
department
Company Structure
Company Structure
disk
Drive
Bitrix24.Drive
entity
Data Storage
Data Storage
im
Chat and Notifications
Chat and Notifications
imbot
Creating and Managing Chat Bots
Chat Bots
imopenlines
Open Channels
Open Channels
landing
Sites
Sites
lists
Lists
Universal Lists
log
Live Feed
News Feed
mailservice
Mail Services
Mail Services
messageservice
Message Service
Message Service
pay_system
Payment Systems
Payment Systems
pull
Pull&Push
Pull&Push
rpa
Business Automation
Business Automation
sale
Online Store
Online Store
sign.b2e
e-Signature for HR + Government Key
e-Signature for HR, Signature
sonet_group, socialnetwork
Social Network Workgroups
Social Network Workgroups
task
Tasks
Tasks
telephony
Telephony
Telephony
timeman
Time Tracking
Time Tracking
user
Users
Versions:
user_brief
— Users (minimal)
user_basic
— Users (basic)
Users
user.userfield
User Custom Fields
User Custom Fields
userfieldconfig
User Field Settings
User Field Settings
userconsent
Working with Agreements
Working with Agreements
vote
Polls, Votes
Working with Polls, Votes
In addition, three deprecated scopes are available — tasks, tasks_extended, tasksmobile. They should not be used.
Was the article helpful?
Yes
No
Previous
Method permissions
Next
Confirmation methods

---

## Method Calls with Confirmation

**Source:** https://apidocs.bitrix24.com/api-reference/scopes/confirmation

Method Calls with Confirmation | Bitrix24 REST API and Marketplace Applications
Method Calls with Confirmation
Method Calls with Confirmation
Some methods require the account administrator's permission to be called. When such a method is invoked by the application, the account administrator will receive a notification asking to allow or deny the call, while the application will receive an error.
The permission or denial is granted to a specific authorization token used to call the method. This means that the permission is valid for the lifetime of the token, and a new permission must be obtained when receiving the next token.
How to Use Examples in Documentation
GET
https
:
//portal.bitrix24.com/rest/voximplant.user.get?auth=fkp963yuv1ggkfbs5z3f5hy8lilm0iw6&USER_ID=1
HTTP
/
1.1
401
Unauthorized
{
"error"
:
"METHOD_CONFIRM_WAITING"
,
"error_description"
:
"Waiting for confirmation"
}
Calling the method before receiving confirmation or a response will yield the same reply, but without a request for re-confirmation.
When the administrator confirms or denies the permission, an event handler
OnAppMethodConfirm
will be triggered, passing the confirmation result and the token to which this permission was granted:
array
(
'event'
=>
'ONAPPMETHODCONFIRM'
,
'data'
=>
array
(
'TOKEN'
=>
'fkp963yuv1ggkfbs5z3f5hy8lilm0iw6'
,
'METHOD'
=>
'voximplant.user.get'
,
'CONFIRMED'
=>
'1'
,
'LANGUAGE_ID'
=>
'de'
,
),
'ts'
=>
'1478790852'
,
'auth'
=>
array
(
'domain'
=>
'portal.bitrix24.com'
,
'client_endpoint'
=>
'https://portal.bitrix24.com/rest/'
,
'server_andpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'member_id'
=>
'74ef8a46a75104de55d5d4a61b98ab6d'
,
'application_token'
=>
'c289487163b58658eae5e8b42eaf11b8'
,
),
If the administrator allows the action, the application can use the same authorization token to work with the requested method:
GET
https
:
//portal.bitrix24.com/rest/voximplant.user.get?auth=fkp963yuv1ggkfbs5z3f5hy8lilm0iw6&USER_ID=1
HTTP
/
1.1
200
OK
{
"result"
: [
{
"DEFAULT_LINE"
:
null
,
"ID"
:
"1"
,
"INNER_NUMBER"
:
null
,
"PHONE_ENABLED"
:
"Y"
,
"SIP_LOGIN"
:
"****"
,
"SIP_PASSWORD"
:
"*****"
,
"SIP_SERVER"
:
"*****"
}
]
}
In the case of denial, a corresponding error will be returned:
GET
https
:
//portal.bitrix24.com/rest/voximplant.user.get?auth=fkp963yuv1ggkfbs5z3f5hy8lilm0iw6&USER_ID=1
HTTP
/
1.1
403
Forbidden
{
"error"
:
"METHOD_CONFIRM_DENIED"
,
"error_description"
:
"Method call denied"
}
List of Methods Requiring Confirmation
List of Methods Requiring Confirmation
Get User Settings voximplant.user.get
Copied
Was the article helpful?
Yes
No
Previous
Available scopes
Next
Widget embedding mechanism

---

## General Methods and Events

**Source:** https://apidocs.bitrix24.com/api-reference/common/index

General Methods and Events | Bitrix24 REST API and Marketplace Applications
General Methods and Events
General Methods and Events
Methods Related to Current User Permissions
Storing and Retrieving Application Settings
System Events
Several general methods available to the application regardless of the permissions requested by the application:
Method
Description
scope
Displays permissions.
app.info
Displays application information.
access.name
Retrieves access permission names.
server.time
Returns the current server time in ATOM format.
feature.get
Checks the availability of features on the account.
method.get
Checks the availability of a specific method.
Methods Related to Current User Permissions
Methods Related to Current User Permissions
Method
Description
user.admin
Determines if the current user has permissions to manage application settings.
user.access
Determines if the current user has at least one of the specified
ACCESS
permissions.
Storing and Retrieving Application Settings
Storing and Retrieving Application Settings
Method
Description
app.option.set
Set your application settings to be stored in Bitrix24.
app.option.get
Retrieve saved application settings from Bitrix24.
user.option.set
Set your current user settings to be stored in Bitrix24.
user.option.get
Retrieve saved settings of the current user from Bitrix24.
System Events
System Events
Event
Description
OnAppInstall
Triggered after the application is successfully installed on a specific Bitrix24 account.
OnAppUninstall
Triggered after the application is removed from a specific Bitrix24 account.
OnAppMethodConfirm
Triggered after the portal administrator allows the use of a special class of methods.
onAppPayment
Triggered when the application is paid for.
onAppUserAdd
Triggered when a user is added to Bitrix24.
Was the article helpful?
Yes
No
Previous
Queue Change Event
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/common/system/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
basic
Who can execute the method: any user
Method
Description
method.get
Check the existence of the method
scope
Retrieve a list of available scopes
app.info
Get information about the account
access.name
Retrieve names of access permissions
feature.get
Check the availability of features
server.time
Get the server time
methods
Retrieve a list of available methods (deprecated)
Copied
Was the article helpful?
Yes
No
Previous
General Methods and Events
Next
Get a List of Available Methods

---

## Get a list of available methods method.get

**Source:** https://apidocs.bitrix24.com/api-reference/common/system/method-get

Get a list of available methods method.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of available methods method.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The
method.get
method returns two parameters
isExisting
and
isAvailable
, which determine the existence of the method on the account and its availability for invocation.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
name
string
The name of the method to check in lowercase, for example
user.get
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
'{
"name": "user.get"
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/method.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"name": "user.get",
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/method.get
try
{
const
response =
await
$b24.
callMethod
(
"method.get"
,
{
"name"
:
"user.get"
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
'method.get'
,
[
'name'
=>
'user.get'
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
'Error calling method: '
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
"method.get"
,
{
"name"
:
"user.get"
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
log
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
'method.get'
,
[
'name'
=>
'user.get'
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
"isExisting"
:
true
,
"isAvailable"
:
true
}
,
"time"
:
{
"start"
:
1721983189.4629
,
"finish"
:
1721983189.50346
,
"duration"
:
0.0405528545379639
,
"processing"
:
0.000152111053466796
,
"date_start"
:
"2024-07-26T08:39:49+00:00"
,
"date_finish"
:
"2024-07-26T08:39:49+00:00"
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
Two parameters are returned:
isExisting => true/false
— determines whether the method exists on this account
isAvailable => true/false
— determines the availability of the method for invocation with the current access permissions (
scope
) of the application
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
Get a List of Available Permissions Scope
Show information about the app app.info
Get Access Permission Names access.name
Get information about feature availability on the account feature.get
Get Current Server Time server.time
Get a List of Available Methods
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get a List of Available Permissions

---

## Get a List of Available Permissions Scope

**Source:** https://apidocs.bitrix24.com/api-reference/common/system/scope

Get a List of Available Permissions Scope | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a List of Available Permissions Scope
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The
scope
method returns a list of permissions.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
full
boolean
If the parameter is set to
true
, the method will return the complete
list of permissions
If the method is called without parameters, it will return all permissions available for this application.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"full": true
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/scope
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"full": true,
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/scope
try
{
const
response =
await
$b24.
callMethod
(
"scope"
,
{
"full"
:
true
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
'scope'
,
[
'full'
=>
true
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
'Error calling scope method: '
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
"scope"
,
{
"full"
:
true
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
log
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
'scope'
,
[
'full'
=>
true
,
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
"department"
,
"entity"
,
"log"
,
"user"
]
,
"time"
:
{
"start"
:
1721993326.41019
,
"finish"
:
1721993326.44899
,
"duration"
:
0.0387959480285645
,
"processing"
:
0.000020980834960937
,
"date_start"
:
"2024-07-26T11:28:46+00:00"
,
"date_finish"
:
"2024-07-26T11:28:46+00:00"
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
An array containing the list of permissions
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
Get a list of available methods method.get
Show information about the app app.info
Get Access Permission Names access.name
Get information about feature availability on the account feature.get
Get Current Server Time server.time
Get a List of Available Methods
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Available Methods
Next
Show Application Information

---

## Show information about the app app.info

**Source:** https://apidocs.bitrix24.com/api-reference/common/system/app-info

Show information about the app app.info | Bitrix24 REST API and Marketplace Applications
Code Examples
Show information about the app app.info
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The method
app.info
returns information about the application.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/app.info
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/app.info
try
{
const
response =
await
$b24.
callMethod
(
'app.info'
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
log
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
$applicationInfoResult
=
$serviceBuilder
->
getMainScope
()->
main
()->
getApplicationInfo
();
$itemResult
=
$applicationInfoResult
->
applicationInfo
();
print
(
"ID: "
.
$itemResult
->ID . PHP_EOL);
print
(
"Code: "
.
$itemResult
->CODE . PHP_EOL);
print
(
"Scope: "
.
json_encode
(
$itemResult
->SCOPE, JSON_THROW_ON_ERROR) . PHP_EOL);
print
(
"Version: "
.
$itemResult
->VERSION . PHP_EOL);
print
(
"Status: "
.
$itemResult
->
getStatus
()->
getStatusCode
() . PHP_EOL);
print
(
"Installed: "
. (
$itemResult
->INSTALLED ?
'true'
:
'false'
) . PHP_EOL);
print
(
"Payment Expired: "
.
$itemResult
->PAYMENT_EXPIRED . PHP_EOL);
print
(
"Days: "
.
$itemResult
->DAYS . PHP_EOL);
print
(
"License: "
.
$itemResult
->LICENSE . PHP_EOL);
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
() . PHP_EOL);
}
BX24
.
callMethod
(
"app.info"
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
log
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
'app.info'
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
5
,
"CODE"
:
"telefum24.kp10"
,
"VERSION"
:
4
,
"STATUS"
:
"F"
,
"INSTALLED"
:
true
,
"PAYMENT_EXPIRED"
:
"N"
,
"DAYS"
:
null
,
"LANGUAGE_ID"
:
"de"
,
"LICENSE"
:
"de_ent10000"
,
"LICENSE_TYPE"
:
"ent10000"
,
"LICENSE_FAMILY"
:
"ent"
}
,
"time"
:
{
"start"
:
1722841503.0585
,
"finish"
:
1722841503.09885
,
"duration"
:
0.0403509140014648
,
"processing"
:
0.00533103942871094
,
"date_start"
:
"2024-08-05T07:05:03+00:00"
,
"date_finish"
:
"2024-08-05T07:05:03+00:00"
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
The object contains information about the application:
ID
— local identifier of the application on the account
CODE
— application code
VERSION
— installed version of the application
STATUS
— status of the application. Possible values:
F
(Free) — free
D
(Demo) — demo version
T
(Trial) — trial version (time-limited)
P
(Paid) — paid application
L
(Local) — local application
S
(Subscription) — subscription application
INSTALLED
— [true|false] status of the application's installation. If the application is not installed, it is only available to account administrators and should signal the end of installation by calling
BX24.installFinish
PAYMENT_EXPIRED
— [Y|N] flag indicating whether the paid period or trial period has expired
DAYS
— number of days remaining until the end of the paid period or trial period
LICENSE
— designation of the plan with the region indicated as a prefix. Consists of the base language of the account and the identifier of the plan. In cases where the composition of the plans has changed while retaining the public name (such as CRM+, Team, and Company), it is not possible to determine which plan is active based on this field. Examples of possible values:
de_project
— Project plan
de_basic
— Basic plan
de_std
— Standard plan
de_pro100
— Professional plan
de_ent250
— Enterprise 250
de_ent500
— Enterprise 500
de_ent1000
— Enterprise 1000
de_ent2000
— Enterprise 2000
de_ent10000
— Enterprise 10000
time
time
Information about the request execution time
After the paid period expires, the application will continue to operate during the grace period, after which it will automatically switch to demo mode or be blocked. At this point, the value of the
PAYMENT_EXPIRED
flag will be
Y
, and the
DAYS
field will contain a negative number.
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
ACCESS_DENIED
Access denied! Application context required
Method called outside the application context
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
Get a list of available methods method.get
Get a List of Available Permissions Scope
Get Access Permission Names access.name
Get information about feature availability on the account feature.get
Get Current Server Time server.time
Get a List of Available Methods
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Available Permissions
Next
Get Access Permission Names

---

## Get Access Permission Names access.name

**Source:** https://apidocs.bitrix24.com/api-reference/common/system/access-name

Get Access Permission Names access.name | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Access Permission Names access.name
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The method
access.name
retrieves the names of access permissions.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ACCESS
*
array
List of permission identifiers for which names need to be retrieved
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"ACCESS": ["G2", "AU"]
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/access.name
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"ACCESS": ["G2", "AU"],
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/access.name
try
{
const
response =
await
$b24.
callMethod
(
'access.name'
,
{
'ACCESS'
: [
'G2'
,
'AU'
]
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
'access.name'
,
[
'ACCESS'
=> [
'G2'
,
'AU'
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
'Error calling access.name: '
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
"access.name"
,
{
"ACCESS"
: [
"G2"
,
"AU"
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
console
.
log
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
'access.name'
,
[
'ACCESS'
=> [
'G2'
,
'AU'
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
"G2"
:
{
"provider"
:
""
,
"name"
:
"All visitors"
,
"provider_id"
:
"other"
}
,
"AU"
:
{
"provider"
:
""
,
"name"
:
"All authorized users"
,
"provider_id"
:
"other"
}
}
,
"time"
:
{
"start"
:
1722002504.2838
,
"finish"
:
1722002504.32483
,
"duration"
:
0.0410301685333252
,
"processing"
:
0.00145506858825684
,
"date_start"
:
"2024-07-26T14:01:44+00:00"
,
"date_finish"
:
"2024-07-26T14:01:44+00:00"
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
Objects describing permissions
time
time
Information about the request execution time
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
Get a list of available methods method.get
Get a List of Available Permissions Scope
Show information about the app app.info
Get information about feature availability on the account feature.get
Get Current Server Time server.time
Get a List of Available Methods
Copied
Was the article helpful?
Yes
No
Previous
Show Application Information
Next
Get Information on Feature Availability on Account

---

## Get information about feature availability on the account feature.get

**Source:** https://apidocs.bitrix24.com/api-reference/common/system/feature-get

Get information about feature availability on the account feature.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get information about feature availability on the account feature.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The method
feature.get
returns information about the availability of features on a specific account.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
CODE
*
string
Available keys:
rest_offline_extended
— availability of offline events
rest_auth_connector
— availability of the
auth_connector
key in events
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"CODE": "rest_offline_extended"
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/feature.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"CODE": "rest_offline_extended",
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/feature.get
try
{
const
response =
await
$b24.
callMethod
(
"feature.get"
,
{
"CODE"
:
"rest_offline_extended"
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
'feature.get'
,
[
'CODE'
=>
'rest_offline_extended'
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
'Error getting feature: '
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
"feature.get"
,
{
"CODE"
:
"rest_offline_extended"
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
log
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
'feature.get'
,
[
'CODE'
=>
'rest_offline_extended'
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
"value"
:
"Y"
}
,
"time"
:
{
"start"
:
1722434594.84942
,
"finish"
:
1722434594.90542
,
"duration"
:
0.0560011863708496
,
"processing"
:
0.000065088272094726
,
"date_start"
:
"2024-07-31T14:03:14+00:00"
,
"date_finish"
:
"2024-07-31T14:03:14+00:00"
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
The object contains information about the method's availability:
value
— (Y/N) presence of the feature on the account
lang_selfhosted
—
lang
is replaced with en, de, ua, kz, etc. (used for on-premise
Bitrix24
)
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
"CODE_EMPTY"
,
"error_description"
:
"CODE can't be empty"
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
CODE_EMPTY
CODE can't be empty
The CODE parameter was not provided
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
Get a list of available methods method.get
Get a List of Available Permissions Scope
Show information about the app app.info
Get Access Permission Names access.name
Get Current Server Time server.time
Get a List of Available Methods
Copied
Was the article helpful?
Yes
No
Previous
Get Access Permission Names
Next
Get Current Server Time

---

## Get Current Server Time server.time

**Source:** https://apidocs.bitrix24.com/api-reference/common/system/server-time

Get Current Server Time server.time | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Current Server Time server.time
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The method
server.time
returns the current server time in the format
YYYY-MM-DDThh:mm:ss±hh:mm
.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/server.time
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/server.time
try
{
const
response =
await
$b24.
callMethod
(
"server.time"
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
log
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
'server.time'
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
'Server time: '
.
$result
->
data
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
'Error getting server time: '
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
"server.time"
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
log
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
'server.time'
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
{
"result"
:
"2024-08-05T09:02:13+00:00"
,
"time"
:
{
"start"
:
1722848533.40768
,
"finish"
:
1722848533.44277
,
"duration"
:
0.0350871086120606
,
"processing"
:
0.000040054321289062
,
"date_start"
:
"2024-08-05T09:02:13+00:00"
,
"date_finish"
:
"2024-08-05T09:02:13+00:00"
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
string
Server time in the format
YYYY-MM-DDThh:mm:ss±hh:mm
time
time
Information about the request execution time
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
Get a list of available methods method.get
Get a List of Available Permissions Scope
Show information about the app app.info
Get Access Permission Names access.name
Get information about feature availability on the account feature.get
Get a List of Available Methods
Copied
Was the article helpful?
Yes
No
Previous
Get Information on Feature Availability on Account
Next
Get a List of Available Methods (Deprecated)

---

## Get a List of Available Methods

**Source:** https://apidocs.bitrix24.com/api-reference/common/system/methods

Get a List of Available Methods | Bitrix24 REST API and Marketplace Applications
Get a List of Available Methods
Get a List of Available Methods
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The
methods
method retrieves a list of available methods.
Method Development Halted
The
methods
method continues to function, but it lacks information on some methods. A more current alternative is the
method.get
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
full
boolean
If the parameter is set to
true
, the method will return a list of all methods
scope
string
Display of methods included in the specified permission. If the parameter is provided without a value (
methods?scope=&auth=xxxxx
), all common methods will be displayed.
If the method is called without parameters, it will return a list of all methods available to the current application.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"scope": "user"
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/methods
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"scope": "user",
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/methods
try
{
const
response =
await
$b24.
callMethod
(
"methods"
,
{
"scope"
:
"user"
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
'methods'
,
[
'scope'
=>
'user'
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
'Error calling method: '
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
"methods"
,
{
"scope"
:
"user"
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
log
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
'methods'
,
[
'scope'
=>
'user'
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
"user.fields"
,
"user.current"
,
"user.get"
,
"user.search"
,
"user.add"
,
"user.update"
,
"user.online"
,
"user.counters"
,
"user.history.list"
,
"user.history.fields.list"
]
,
"time"
:
{
"start"
:
1721986432.32646
,
"finish"
:
1721986432.3598
,
"duration"
:
0.0333478450775147
,
"processing"
:
0.000032901763916015
,
"date_start"
:
"2024-07-26T09:33:52+00:00"
,
"date_finish"
:
"2024-07-26T09:33:52+00:00"
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
An array containing the list of permissions
time
time
Information about the request execution time
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
Get a list of available methods method.get
Get a List of Available Permissions Scope
Show information about the app app.info
Get Access Permission Names access.name
Get information about feature availability on the account feature.get
Get Current Server Time server.time
Copied
Was the article helpful?
Yes
No
Previous
Get Current Server Time
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/common/users/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
basic
Who can execute the method: any user
Method
Description
user.admin
Determines whether the current user has the rights to manage application settings
user.access
Indicates whether the current user has at least one of the specified permissions
profile
Allows retrieving basic information about the current user without any scopes
other methods
Other methods for working with users in
Bitrix24
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Available Methods (Deprecated)
Next
Define Access Permissions for Managing Application Settings

---

## Determine Access Permissions for Application Settings user.admin

**Source:** https://apidocs.bitrix24.com/api-reference/common/users/user-admin

Determine Access Permissions for Application Settings user.admin | Bitrix24 REST API and Marketplace Applications
Code Examples
Determine Access Permissions for Application Settings user.admin
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
See Also
Scope:
basic
Who can execute the method: any user
The method
user.admin
determines whether the current user has the permissions to manage application settings.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/user.admin
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/user.admin
try
{
const
response =
await
$b24.
callMethod
(
'user.admin'
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
log
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
'user.admin'
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
'Error calling user.admin: '
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
"user.admin"
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
log
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
'user.admin'
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
true
,
"time"
:
{
"start"
:
1721998816.3694
,
"finish"
:
1721998816.43663
,
"duration"
:
0.0672309398651123
,
"processing"
:
0.000064849853515625
,
"date_start"
:
"2024-07-26T13:00:16+00:00"
,
"date_finish"
:
"2024-07-26T13:00:16+00:00"
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
Returns
true
if the current user has permissions to manage application settings,
false
otherwise
time
time
Information about the request execution time
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
Determine the user.access permissions set
Get Basic Information About the Current User Profile
See Also
See Also
BX24.isAdmin
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Define User Access Rights

---

## Determine the user.access permissions set

**Source:** https://apidocs.bitrix24.com/api-reference/common/users/user-access

Determine the user.access permissions set | Bitrix24 REST API and Marketplace Applications
Method Parameters
Determine the user.access permissions set
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The
user.access
method checks if the current user has at least one of the permissions specified in the
ACCESS
parameter.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ACCESS
*
array
Identifier or list of identifiers of the permissions to check access for
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"ACCESS": ["G2", "AU"]
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/user.access
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"ACCESS": ["G2", "AU"],
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/user.access
try
{
const
response =
await
$b24.
callMethod
(
'user.access'
,
{
"'ACCESS"
: [
"G2"
,
"AU"
]
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
'user.access'
,
[
"'ACCESS"
=> [
"G2"
,
"AU"
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
'Error calling user.access: '
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
"user.access"
,
{
"'ACCESS"
: [
"G2"
,
"AU"
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
console
.
log
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
'user.access'
,
[
'ACCESS'
=> [
'G2'
,
'AU'
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
1722001311.94644
,
"finish"
:
1722001311.98622
,
"duration"
:
0.0397801399230957
,
"processing"
:
0.000041961669921875
,
"date_start"
:
"2024-07-26T13:41:51+00:00"
,
"date_finish"
:
"2024-07-26T13:41:51+00:00"
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
Returns
true
if the current user has at least one of the permissions listed in the
ACCESS
parameter,
false
otherwise
time
time
Information about the request execution time
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
Determine Access Permissions for Application Settings user.admin
Get Basic Information About the Current User Profile
Copied
Was the article helpful?
Yes
No
Previous
Define Access Permissions for Managing Application Settings
Next
Retrieve Basic Information About the Current User

---

## Get Basic Information About the Current User Profile

**Source:** https://apidocs.bitrix24.com/api-reference/common/users/profile

Get Basic Information About the Current User Profile | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Basic Information About the Current User Profile
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The
profile
method allows you to retrieve basic information about the current user without any scopes, unlike
user.current
.
No parameters required.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/profile
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/profile
try
{
const
response =
await
$b24.
callMethod
(
"profile"
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
log
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
'profile'
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
'Error calling profile method: '
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
"profile"
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
log
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
'profile'
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
"ID"
:
"1"
,
"ADMIN"
:
true
,
"NAME"
:
"Vadim"
,
"LAST_NAME"
:
"Valeev"
,
"PERSONAL_GENDER"
:
""
,
"TIME_ZONE"
:
""
}
,
"time"
:
{
"start"
:
1722848182.67776
,
"finish"
:
1722848182.71787
,
"duration"
:
0.0401120185852051
,
"processing"
:
0.00115704536437988
,
"date_start"
:
"2024-08-05T08:56:22+00:00"
,
"date_finish"
:
"2024-08-05T08:56:22+00:00"
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
The object contains information about the user
time
time
Information about the request execution time
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
Determine Access Permissions for Application Settings user.admin
Determine the user.access permissions set
Copied
Was the article helpful?
Yes
No
Previous
Define User Access Rights
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/common/settings/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
basic
Who can execute the method: any user
Methods for working with application settings
Method
Description
app.option.set
This method binds data to the application
app.option.get
Retrieves data bound to the application
user.option.set
This method binds data to both the application and the user
user.option.get
Retrieves user data bound to the application
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Basic Information About the Current User
Next
Bind Data to Application

---

## Bind Data to the app.option.set Method

**Source:** https://apidocs.bitrix24.com/api-reference/common/settings/app-option-set

Bind Data to the app.option.set Method | Bitrix24 REST API and Marketplace Applications
Method Parameters
Bind Data to the app.option.set Method
Method Parameters
Code Examples
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: administrator
The
app.option.set
method binds data to the application.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
options
*
array
An array where the key is the name of the property to be saved, and the value is the property value. If a value with a new key is passed, the method will write it; if an existing one, it will update it.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"options": {
"data": "value",
"data2": "value2"
}
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/app.option.set
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"options": {
"data": "value",
"data2": "value2"
},
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/app.option.set
try
{
const
response =
await
$b24.
callMethod
(
'app.option.set'
,
{
"options"
: {
"data"
:
"value"
,
"data2"
:
"value2"
,
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
log
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
'app.option.set'
,
[
'options'
=> [
'data'
=>
'value'
,
'data2'
=>
'value2'
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
$result
->
data
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
'Error setting app options: '
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
'app.option.set'
,
{
"options"
: {
"data"
:
"value"
,
"data2"
:
"value2"
,
}
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
log
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
'app.option.set'
,
[
'options'
=> [
'data'
=>
'value'
,
'data2'
=>
'value2'
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
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
"ArgumentNullException"
,
"error_description"
:
"options is empty"
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
ArgumentNullException
options is empty
Empty array
options
AccessException
Application context required / Administrator authorization required
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
Get Application-Linked Data app.option.get
Bind Data to User and Application user.option.set
Get User Data Associated with the Application user.option.get
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Retrieve Bound Data from Application

---

## Get Application-Linked Data app.option.get

**Source:** https://apidocs.bitrix24.com/api-reference/common/settings/app-option-get

Get Application-Linked Data app.option.get | Bitrix24 REST API and Marketplace Applications
Parameters
Get Application-Linked Data app.option.get
Parameters
Code Examples
Response Handling
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The method
app.option.get
retrieves data linked to the application. If no input is provided, it will return all properties recorded via
app.option.set
.
Parameters
Parameters
Name
type
Description
option
string
A string, one of the keys from the property
app.option.set
.
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
Example #1
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"option": "data"
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/app.option.get
Example #2
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/app.option.get
Example #1
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"option": "data",
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/app.option.get
Example #2
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/app.option.get
Example #1
BX24
.
callMethod
(
'app.option.get'
,
{
"option"
:
"data"
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
log
(result.
data
());
}
);
Example #2
BX24
.
callMethod
(
'app.option.get'
, {},
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
log
(result.
data
());
}
);
Example #1
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
'app.option.get'
,
[
'option'
=>
'data'
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
Example #2
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
'app.option.get'
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
"data"
:
"value"
,
"data2"
:
"value2"
}
The method returns data linked to the application.
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
"AccessException"
,
"error_description"
:
"Application context required / User authorization required"
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
AccessException
Application context required / Administrator authorization required
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
Bind Data to the app.option.set Method
Bind Data to User and Application user.option.set
Get User Data Associated with the Application user.option.get
Copied
Was the article helpful?
Yes
No
Previous
Bind Data to Application
Next
Bind Data to User and Application

---

## Bind Data to User and Application user.option.set

**Source:** https://apidocs.bitrix24.com/api-reference/common/settings/user-option-set

Bind Data to User and Application user.option.set | Bitrix24 REST API and Marketplace Applications
Method Parameters
Bind Data to User and Application user.option.set
Method Parameters
Code Examples
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The method
user.option.set
binds data to the application and user.
The application can be bound to the user who installed it if it is a
headless application
or to the user with whom it interacts if it is a
UI application
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
options
*
array
An array where the key is the name of the property to be saved, and the value is the property value. If a value with a new key is passed, the method will write it; if an existing one, it will update it.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"options": {
"data": "value",
"data2": "value2"
}
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/user.option.set
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"options": {
"data": "value",
"data2": "value2"
},
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/user.option.set
try
{
const
response =
await
$b24.
callMethod
(
'user.option.set'
,
{
"options"
: {
"data"
:
"value"
,
"data2"
:
"value2"
,
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
log
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
'user.option.set'
,
[
'options'
=> [
'data'
=>
'value'
,
'data2'
=>
'value2'
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
$result
->
data
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
'Error setting user options: '
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
'user.option.set'
,
{
"options"
: {
"data"
:
"value"
,
"data2"
:
"value2"
,
}
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
log
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
'user.option.set'
,
[
'options'
=> [
'data'
=>
'value'
,
'data2'
=>
'value2'
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
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
"ArgumentNullException"
,
"error_description"
:
"options is empty"
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
ArgumentNullException
options is empty
Empty array
options
AccessException
Application context required / Administrator authorization required
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
Bind Data to the app.option.set Method
Get Application-Linked Data app.option.get
Get User Data Associated with the Application user.option.get
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Bound Data from Application
Next
Retrieve Saved User Settings

---

## Get User Data Associated with the Application user.option.get

**Source:** https://apidocs.bitrix24.com/api-reference/common/settings/user-option-get

Get User Data Associated with the Application user.option.get | Bitrix24 REST API and Marketplace Applications
Parameters
Get User Data Associated with the Application user.option.get
Parameters
Code Examples
Response Handling
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
basic
Who can execute the method: any user
The method
user.option.get
retrieves user data associated with the application. If no input is provided, it will return all properties recorded through
user.option.set
.
Parameters
Parameters
Name
type
Description
option
string
A string, one of the keys from the property
user.option.set
.
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
Example #1
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"option": "data"
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/user.option.get
Example #2
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/user.option.get
Example #1
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"option": "data",
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/user.option.get
Example #2
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/user.option.get
Example #1
BX24
.
callMethod
(
'user.option.get'
,
{
"option"
:
"data"
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
log
(result.
data
());
}
);
Example #2
BX24
.
callMethod
(
'user.option.get'
, {},
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
log
(result.
data
());
}
);
Example #1
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
'user.option.get'
,
[
'option'
=>
'data'
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
Example #2
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
'user.option.get'
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
"data"
:
"value"
,
"data2"
:
"value2"
}
The method returns user data associated with the application.
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
"AccessException"
,
"error_description"
:
"Application context required / User authorization required"
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
AccessException
Application context required / Administrator authorization required
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
Bind Data to the app.option.set Method
Get Application-Linked Data app.option.get
Bind Data to User and Application user.option.set
Copied
Was the article helpful?
Yes
No
Previous
Bind Data to User and Application
Next
Overview of Events

---

## List of Events

**Source:** https://apidocs.bitrix24.com/api-reference/common/events/index

List of Events | Bitrix24 REST API and Marketplace Applications
List of Events
List of Events
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope
:
basic
|
Who can subscribe
:
any user
Method
Description
Version
onAppInstall
This event is triggered immediately after the application is successfully installed on Bitrix24.
onAppUninstall
This event is triggered when the application is uninstalled.
onAppMethodConfirm
This event is triggered when the portal administrator makes a decision regarding a request to use methods that require confirmation.
onAppPayment
This event is triggered when the application is paid for.
onAppUserAdd
This event is triggered when a user is added to Bitrix24.
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Saved User Settings
Next
After Successful Installation of the Application

---

## Event after successful installation of the application OnAppInstall

**Source:** https://apidocs.bitrix24.com/api-reference/common/events/on-app-install

Event after successful installation of the application OnAppInstall | Bitrix24 REST API and Marketplace Applications
Event after successful installation of the application OnAppInstall
Event after successful installation of the application OnAppInstall
What the handler receives
Request parameters
Parameter data
Parameter auth
Continue exploring
Scope:
basic
Who can subscribe: any user
The
OnAppInstall
event is triggered immediately after the application is successfully installed on Bitrix24. The
application_token
is passed to the handler, which is important to save. For more details, refer to the article
Security in Handlers
.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
array(
'event' => 'ONAPPINSTALL',
'data' => array(
'VERSION' => '1.0.0',
'ACTIVE' => 'Y',
'INSTALLED' => 'Y',
'LANGUAGE_ID' => 'en'
),
'ts' => '1696527000',
'auth' => array(
'domain' => 'some-domain.bitrix24.com',
'server_endpoint' => 'https://oauth.bitrix.info/rest/',
'status' => 'F',
'client_endpoint' => 'https://some-domain.bitrix24.com/rest/',
'member_id' => 'a223c6b3710f85df22e9377d6c4f7553',
'application_token' => '51856fefc120afa4b628cc82d3935cce',
),
)
Request parameters
Request parameters
Required parameters are marked with *
Name
type
Description
event
*
string
Symbolic code of the event. In this case —
ONAPPINSTALL
data
*
object
Data about the installed application.
The structure is described
below
ts
*
timestamp
Date and time of sending the event from the queue
auth
*
object
Object containing authorization parameters and data about the account where the event occurred.
The structure is described
below
Parameter data
Parameter data
Required parameters are marked with *
Name
type
Description
LANGUAGE_ID
*
string
Installed language:
en
,
de
and others
VERSION
*
integer
Version of the installed application
ACTIVE
*
string
Status of the application's activity.
Possible values:
Y
— active
N
— inactive
INSTALLED
*
string
Is the application ready for use.
Possible values:
Y
— ready
N
— not fully installed
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
domain
*
string
Address of the Bitrix24 account
server_endpoint
*
string
Address of the authorization server for token renewal
status
*
string
Status of the application that subscribed to this event:
L
— local application
F
— free mass-market application
client_endpoint
*
string
General path for API method calls of the account
member_id
*
string
Unique identifier of the account
application_token
*
string
Token for secure event handling
The handler for this event can be set in the installation script of the application, which is specified in the version card in a separate field.
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event onAppPayment
Event on receiving permission to use onAppMethodConfirm methods
Event onUserAdd
Event on Application Uninstallation onAppUninstall
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Uninstalling the Application

---

## Event on Application Uninstallation onAppUninstall

**Source:** https://apidocs.bitrix24.com/api-reference/common/events/on-app-uninstall

Event on Application Uninstallation onAppUninstall | Bitrix24 REST API and Marketplace Applications
Event on Application Uninstallation onAppUninstall
Event on Application Uninstallation onAppUninstall
What the handler receives
Request Parameters
Parameter data
Parameter auth
Continue Learning
Scope:
basic
Who can subscribe: any user
The
onAppUninstall
event is triggered when an application is uninstalled.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event": "ONAPPUNINSTALL",
"data": {
"LANGUAGE_ID" => "en",
"CLEAN": 1
},
"ts": "1466439714",
"auth": {
"domain": "some-domain.bitrix24.com",
"server_endpoint": "https://oauth.bitrix.info/rest/",
"client_endpoint": "https://some-domain.bitrix24.com/rest/",
"member_id": "a223c6b3710f85df22e9377d6c4f7553",
"application_token": "51856fefc120afa4b628cc82d3935cce"
}
}
Request Parameters
Request Parameters
Required parameters are marked with *
Name
type
Description
event
*
string
Symbolic event code —
ONAPPUNINSTALL
data
*
array
Data about the uninstalled application.
The structure is described
below
ts
*
timestamp
Date and time the event was sent from the queue
auth
*
array
Authorization and account data.
The structure is described
below
Parameter data
Parameter data
Required parameters are marked with *
Name
type
Description
LANGUAGE_ID
*
string
Set language:
en
,
de
, and others
CLEAN
*
integer
Value of the "Clear application data" option set by the user when uninstalling the application. Values:
1
or
0
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
domain
*
string
Bitrix24 account address
server_endpoint
*
string
Authorization server address for token refresh
client_endpoint
*
string
General path for API method calls for the account
member_id
*
string
Unique identifier of the account
application_token
*
string
Token for secure event processing
When an application is uninstalled, all access permissions for the application to the API are removed. Therefore, even though the event handler will receive authorization data, it can no longer use the API on behalf of the uninstalled application.
Continue Learning
Continue Learning
Event Handler
Register a new event handler event.bind
Event after successful installation of the application OnAppInstall
Event onAppPayment
Event on receiving permission to use onAppMethodConfirm methods
Event onUserAdd
Copied
Was the article helpful?
Yes
No
Previous
After Successful Installation of the Application
Next
When Paying for the Application

---

## Event onAppPayment

**Source:** https://apidocs.bitrix24.com/api-reference/common/events/on-app-payment

Event onAppPayment | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onAppPayment
What the handler receives
Request parameters
Parameter data
Parameter auth
Continue exploring
Scope:
basic
Who can subscribe: any user
The
onAppPayment
event is triggered when an application is paid for.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event": "ONAPPPAYMENT",
"data": {
"CODE": "bitrix.gds_company",
"VERSION": 1,
"STATUS": "S",
"PAYMENT_EXPIRED": "N",
"DAYS": 28,
"LANGUAGE_ID": "de",
},
"ts": "1466439714",
"auth": {
"domain": "some-domain.bitrix24.com",
"server_endpoint": "https://oauth.bitrix.info/rest/",
"client_endpoint": "https://some-domain.bitrix24.com/rest/",
}
}
Request parameters
Request parameters
Required parameters are marked with *
Name
type
Description
event
*
string
Symbolic event code —
ONAPPPAYMENT
data
*
array
Payment data.
The structure is described
below
ts
*
timestamp
Date and time of the event sent from the queue
auth
*
array
Authorization and account data.
The structure is described
below
Parameter data
Parameter data
Required parameters are marked with *
Name
type
Description
CODE
*
string
Application code
VERSION
*
integer
Installed application version
STATUS
*
string
Application status. Possible values:
F
(Free) — free
D
(Demo) — demo version
T
(Trial) — time-limited trial version
P
(Paid) — paid application
PAYMENT_EXPIRED
*
string
[Y|N] Flag indicating whether the paid period or trial period has expired
DAYS
*
integer
Number of days remaining until the end of the paid period or trial period
LANGUAGE_ID
*
string
Installed language:
de
,
en
, and others
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
domain
*
string
Bitrix24 account address
server_endpoint
*
string
Authorization server address for token renewal
client_endpoint
*
string
Common path for API method calls to the account
member_id
*
string
Unique account identifier
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Show information about the app app.info
Event after successful installation of the application OnAppInstall
Event on receiving permission to use onAppMethodConfirm methods
Event onUserAdd
Event on Application Uninstallation onAppUninstall
Copied
Was the article helpful?
Yes
No
Previous
When Uninstalling the Application
Next
When Receiving Permission to Use Methods

---

## Event on receiving permission to use onAppMethodConfirm methods

**Source:** https://apidocs.bitrix24.com/api-reference/common/events/on-app-method-confirm

Event on receiving permission to use onAppMethodConfirm methods | Bitrix24 REST API and Marketplace Applications
Event on receiving permission to use onAppMethodConfirm methods
Event on receiving permission to use onAppMethodConfirm methods
What the handler receives
Request parameters
Parameter data
Parameter auth
Continue your exploration
Scope:
basic
Who can subscribe: any user
The
onAppMethodConfirm
event is triggered upon receiving the
administrator's decision
from the account to use the methods.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event" => "ONAPPMETHODCONFIRM",
"data": {
"TOKEN" => "fkp963yuv1ggkfbs5z3f5hy8lilm0iw6",
"METHOD" => "voximplant.user.get",
"CONFIRMED" => "1",
"LANGUAGE_ID" => "en"
},
"ts": "1478790852",
"auth": {
"domain" => "portal.bitrix24.com",
"client_endpoint" => "https://portal.bitrix24.com/rest/",
"server_andpoint" => "https://oauth.bitrix.info/rest/",
"member_id" => "74ef8a46a75104de55d5d4a61b98ab6d",
"application_token" => "c289487163b58658eae5e8b42eaf11b8"
}
}
Request parameters
Request parameters
Required parameters are marked with *
Name
type
Description
event
*
string
Symbolic event code —
ONAPPMETHODCONFIRM
data
*
array
Data about the allowed methods.
The structure is described
below
ts
*
timestamp
Date and time of event sending
auth
*
array
Authorization and account data.
The structure is described
below
Parameter data
Parameter data
Required parameters are marked with *
Name
type
Description
TOKEN
*
string
Authorization token with which permission was requested
METHOD
*
string
API method for which permission was requested
CONFIRMED
*
string
Permission result:
0
— denied,
1
— granted
LANGUAGE_ID
*
string
Set language:
en
,
de
and others
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
domain
*
string
Bitrix24 account address
server_endpoint
*
string
Authorization server address for token refresh
client_endpoint
*
string
Common path for API method calls of the account
member_id
*
string
Unique account identifier
application_token
*
string
Token for secure event processing
Continue your exploration
Continue your exploration
Event Handler
Register a new event handler event.bind
Event after successful installation of the application OnAppInstall
Event onAppPayment
Event onUserAdd
Event on Application Uninstallation onAppUninstall
Copied
Was the article helpful?
Yes
No
Previous
When Paying for the Application
Next
When Adding a User

---

## Event onUserAdd

**Source:** https://apidocs.bitrix24.com/api-reference/common/events/on-user-add

Event onUserAdd | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onUserAdd
What the handler receives
Request parameters
Parameter data
Parameter auth
Continue exploring
Scope:
basic
Who can subscribe: any user
The
onUserAdd
event is triggered when a user is added to Bitrix24. The event occurs not after the invitation, but after the user logs into the account and completes the registration.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted in the form of a POST request
{
"event": "ONUSERADD",
"data": {
"ID": 123,
"ACTIVE": "Y",
"EMAIL": "user@example.com",
"NAME": "John",
"LAST_NAME": "Doe",
"PERSONAL_GENDER": "M",
"PERSONAL_BIRTHDAY": "1990-01-01",
"UF_DEPARTMENT": [1, 2],
"DATE_REGISTER": "2024-04-05T10:00:00+02:00",
"WORK_POSITION": "Developer",
"UF_EMPLOYMENT_DATE": "2024-04-05"
},
"ts": "1466439714",
"auth": {
"domain": "some-domain.bitrix24.com",
"server_endpoint": "https://oauth.bitrix.info/rest/",
"client_endpoint": "https://some-domain.bitrix24.com/rest/",
"member_id": "a223c6b3710f85df22e9377d6c4f7553"
}
}
Request parameters
Request parameters
Required parameters are marked with *
Name
type
Description
event
*
string
Symbolic event code —
ONUSERADD
data
*
array
Data of the added user.
The structure is described
below
ts
*
timestamp
Date and time the event was sent
auth
*
array
Authorization and account data.
The structure is described
below
Parameter data
Parameter data
Required parameters are marked with *
Name
type
Description
ID
*
integer
User identifier
ACTIVE
*
string
Active flag.
Possible values:
Y
— yes
N
— no
EMAIL
string
User's email
NAME
string
User's first name
LAST_NAME
string
User's last name
PERSONAL_GENDER
string
Gender:
M
— male,
F
— female
PERSONAL_BIRTHDAY
string
Date of birth in
YYYY-MM-DD
format
UF_DEPARTMENT
array
|
null
Array of department
ID
s. May be absent for Extranet users
DATE_REGISTER
*
string
Registration date in
ISO 8601
format
WORK_POSITION
string
User's position
UF_EMPLOYMENT_DATE
string
Employment date in
YYYY-MM-DD
format
Some fields may be absent or have a value of
null
if the application does not have access to them.
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
*
string
Token for accessing the API
expires_in
*
integer
Time in seconds until the token expires
scope
*
string
Scope
within which the event occurred
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
Common path for API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
*
string
Token for refreshing authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event after successful installation of the application OnAppInstall
Event onAppPayment
Event on receiving permission to use onAppMethodConfirm methods
Event on Application Uninstallation onAppUninstall
Copied
Was the article helpful?
Yes
No
Previous
When Receiving Permission to Use Methods
Next
Overview of methods

---

