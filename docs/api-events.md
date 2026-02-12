---
description: 'Events API: Event handlers, bindings, offline events'
methods:
- crm.deal.update
- event.bind
- event.get
- event.offline
- event.test
- event.unbind
pages: 13
title: 'Events API: Event handlers, bindings, offline events'
---
# Events API: Event handlers, bindings, offline events
> Events API: Event handlers, bindings, offline events
> **13 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Event Handler](#event-handler)
- [Get a list of available events](#get-a-list-of-available-events)
- [Register a new event handler event.bind](#register-a-new-event-handler-eventbind)
- [How to Test Your Handler for Bitrix24 Event Processing](#how-to-test-your-handler-for-bitrix24-event-proces)
- [Get a List of Registered Event Handlers event.get](#get-a-list-of-registered-event-handlers-eventget)
- [Unbind Registered Event Handler event.unbind](#unbind-registered-event-handler-eventunbind)
- [Security in Handlers](#security-in-handlers)
- [Features, Advantages, and Disadvantages of Offline Events](#features-advantages-and-disadvantages-of-offline-e)
- [Get a list of offline events event.offline.list](#get-a-list-of-offline-events-eventofflinelist)
- [Get a List of Offline Events with <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-5c1gaftv">event.offline.get</code>](#get-a-list-of-offline-events-with-code-classyfm-cl)
- [Clear records in the offline event queue event.offline.clear](#clear-records-in-the-offline-event-queue-eventoffl)
- [Register Errors for Processing Offline Events event.offline.error](#register-errors-for-processing-offline-events-even)
- [Event of Queue Change onOfflineEvent](#event-of-queue-change-onofflineevent)

---

## Event Handler

**Source:** https://apidocs.bitrix24.com/api-reference/events/index

Event Handler | Bitrix24 REST API and Marketplace Applications
Event Handler
Event Handler
How Events Work
Features of Operation
What Comes to the Handler
Authorization Tokens
How to Subscribe to an Event via Webhook
Event Limitations
Overview of Methods and Events
Continue Learning
Quick navigation:
all methods and events
Events in Bitrix24 are notifications about data changes, such as the creation of a deal or the deletion of a product. When an application or webhook subscribes to an event, the system starts generating these notifications for it. To receive events, set up a handler.
An event handler is an external URL to which Bitrix24 sends a POST request with data about the change. The handler allows you to:
synchronize data with an external system,
trigger automation scenarios,
validate data according to business logic rules.
The handler URL must be accessible from the external network. Do not use addresses on localhost or in a local network. Check the availability of your URL using public services.
How Events Work
How Events Work
The application registers a handler for the desired event using the
event.bind
method.
The user performs an action in Bitrix24, such as modifying a task.
Bitrix24 sends a notification to the application via the queue server.
Features of Operation
Features of Operation
Events are not processed directly. First, Bitrix24 places the event in a queue on a special server. From there, a POST request is sent to your handler. As a result, the request may arrive with a slight delay.
The server checks the response speed of the handler. If the handler responds slowly, the server reduces the frequency of calls. The intervals between requests increase.
Current
queue server addresses
.
What Comes to the Handler
What Comes to the Handler
The system sends a request in JSON format. The main keys are:
event
— the name of the event,
ts
— a timestamp in Unix timestamp format,
data
— event data, such as the identifier of the modified element,
auth
— authorization parameters, including
OAuth 2.0 tokens
.
Example request:
array
(
'event'
=>
'ONAPPINSTALL'
,
'data'
=>
array
(
'VERSION'
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
'entity,im'
,
'domain'
=>
'portal.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix24.tech/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://portal.bitrix24.com/rest/'
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
Authorization Tokens
Authorization Tokens
OAuth 2.0 tokens in the request are tied to the user who performed the action. If the event is triggered automatically, for example, by an automation rule or workflow, the user ID will be
0
. In this case, tokens are not passed to the handler.
To ensure that the application can always make callbacks to Bitrix24, save the tokens of the user who installed the application. Use these tokens for any subsequent requests on behalf of the application.
How to Subscribe to an Event via Webhook
How to Subscribe to an Event via Webhook
In Bitrix24, open the
Developer resources > Other > Outgoing Webhook
section.
Specify the handler URL.
Select one or more events from the list, such as
OnCrmDealAdd
.
Save the webhook. The Application Token field will be generated automatically.
Example request:
{
"event"
:
"ONCRMDEALADD"
,
"event_handler_id"
:
"975"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"7405"
}
}
,
"ts"
:
"1766047124"
,
"auth"
:
{
"domain"
:
"portal.bitrix24.com"
,
"client_endpoint"
:
"https://portal.bitrix24.com/rest/"
,
"server_endpoint"
:
"https://oauth.bitrix24.tech/rest/"
,
"member_id"
:
"d897063e1ce7c5eb9f04b9751eef5915"
,
"application_token"
:
"jvh9y1ulvt2m6k5or90v9mg8nn32ozas"
}
}
Note that the request from the outgoing webhook does not include user OAuth 2.0 tokens.
Event Limitations
Event Limitations
Events have two main limitations:
Load cannot be regulated
. During mass data changes, you will receive many consecutive calls. If a thousand deals are changed simultaneously in Bitrix24, the handler will receive a thousand calls.
No retries
. If your server did not respond or returned an error, the Bitrix24 queue server will log the failure but will not resend the event.
If it is important to process all events without loss, use
offline events
. They allow you to retrieve events from the queue manually.
Overview of Methods and Events
Overview of Methods and Events
Methods
Events
Method
Description
event.bind
Registers a new event handler
event.get
Retrieves a list of registered event handlers
event.offline.clear
Clears records in the offline events queue
event.offline.error
Registers errors in processing the offline events queue
event.offline.get
Retrieves a list of offline events with "clearing"
event.offline.list
Retrieves a list of offline events
event.unbind
Unregisters a registered event handler
events
Retrieves a list of available events
Event
Description
onOfflineEvent
When the offline events queue changes
Continue Learning
Continue Learning
Security in Handlers
Offline Events
Required Network Access
Copied
Was the article helpful?
Yes
No
Previous
Check Access Permissions
Next
Get a List of Available Events

---

## Get a list of available events

**Source:** https://apidocs.bitrix24.com/api-reference/events/events

Get a list of available events | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of available events
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Who can execute the method: any user
The
events
method returns a comprehensive list of available events.
The method works only in the context of authorizing the
application
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
SCOPE
string
The method will return events belonging to the specified permission
FULL
boolean
The method will return the complete list of events. This parameter will be ignored if the
SCOPE
parameter is provided
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
Example #1
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"SCOPE": "user",
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/events
Example #2
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"FULL": true,
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/events
Example #1
BX24
.
callMethod
(
"events"
,
{
"SCOPE"
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
dir
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
"events"
,
{
"FULL"
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
dir
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
'events'
,
[
'SCOPE'
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
'events'
,
[
'FULL'
=>
true
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
"ONAPPUNINSTALL"
,
"ONAPPINSTALL"
,
"ONAPPUPDATE"
,
"ONAPPPAYMENT"
,
"ONAPPTEST"
,
"ONAPPMETHODCONFIRM"
,
"ONOFFLINEEVENT"
,
"ONUSERADD"
,
"ONCRMINVOICEADD"
,
"ONCRMINVOICEUPDATE"
,
"ONCRMINVOICEDELETE"
,
"ONCRMINVOICESETSTATUS"
,
"ONCRMLEADADD"
,
"ONCRMLEADUPDATE"
,
"ONCRMLEADDELETE"
,
"ONCRMLEADUSERFIELDADD"
,
"ONCRMLEADUSERFIELDUPDATE"
,
"ONCRMLEADUSERFIELDDELETE"
,
"ONCRMLEADUSERFIELDSETENUMVALUES"
,
"ONCRMDEALADD"
,
"ONCRMDEALUPDATE"
,
"ONCRMDEALDELETE"
,
"ONCRMDEALMOVETOCATEGORY"
,
"ONCRMDEALUSERFIELDADD"
,
"ONCRMDEALUSERFIELDUPDATE"
,
"ONCRMDEALUSERFIELDDELETE"
,
"ONCRMDEALUSERFIELDSETENUMVALUES"
,
"ONCRMCOMPANYADD"
,
"ONCRMCOMPANYUPDATE"
,
"ONCRMCOMPANYDELETE"
,
"ONCRMCOMPANYUSERFIELDADD"
,
"ONCRMCOMPANYUSERFIELDUPDATE"
,
"ONCRMCOMPANYUSERFIELDDELETE"
,
"ONCRMCOMPANYUSERFIELDSETENUMVALUES"
,
"ONCRMCONTACTADD"
,
"ONCRMCONTACTUPDATE"
,
"ONCRMCONTACTDELETE"
,
"ONCRMCONTACTUSERFIELDADD"
,
"ONCRMCONTACTUSERFIELDUPDATE"
,
"ONCRMCONTACTUSERFIELDDELETE"
,
"ONCRMCONTACTUSERFIELDSETENUMVALUES"
,
"ONCRMQUOTEADD"
,
"ONCRMQUOTEUPDATE"
,
"ONCRMQUOTEDELETE"
,
"ONCRMQUOTEUSERFIELDADD"
,
"ONCRMQUOTEUSERFIELDUPDATE"
,
"ONCRMQUOTEUSERFIELDDELETE"
,
"ONCRMQUOTEUSERFIELDSETENUMVALUES"
,
"ONCRMINVOICEUSERFIELDADD"
,
"ONCRMINVOICEUSERFIELDUPDATE"
,
"ONCRMINVOICEUSERFIELDDELETE"
,
"ONCRMINVOICEUSERFIELDSETENUMVALUES"
,
"ONCRMCURRENCYADD"
,
"ONCRMCURRENCYUPDATE"
,
"ONCRMCURRENCYDELETE"
,
"ONCRMPRODUCTADD"
,
"ONCRMPRODUCTUPDATE"
,
"ONCRMPRODUCTDELETE"
,
"ONCRMPRODUCTPROPERTYADD"
,
"ONCRMPRODUCTPROPERTYUPDATE"
,
"ONCRMPRODUCTPROPERTYDELETE"
,
"ONCRMPRODUCTSECTIONADD"
,
"ONCRMPRODUCTSECTIONUPDATE"
,
"ONCRMPRODUCTSECTIONDELETE"
,
"ONCRMACTIVITYADD"
,
"ONCRMACTIVITYUPDATE"
,
"ONCRMACTIVITYDELETE"
,
"ONCRMREQUISITEADD"
,
"ONCRMREQUISITEUPDATE"
,
"ONCRMREQUISITEDELETE"
,
"ONCRMREQUISITEUSERFIELDADD"
,
"ONCRMREQUISITEUSERFIELDUPDATE"
,
"ONCRMREQUISITEUSERFIELDDELETE"
,
"ONCRMREQUISITEUSERFIELDSETENUMVALUES"
,
"ONCRMBANKDETAILADD"
,
"ONCRMBANKDETAILUPDATE"
,
"ONCRMBANKDETAILDELETE"
,
"ONCRMADDRESSREGISTER"
,
"ONCRMADDRESSUNREGISTER"
,
"ONCRMMEASUREADD"
,
"ONCRMMEASUREUPDATE"
,
"ONCRMMEASUREDELETE"
,
"ONCRMDEALRECURRINGADD"
,
"ONCRMDEALRECURRINGUPDATE"
,
"ONCRMDEALRECURRINGDELETE"
,
"ONCRMDEALRECURRINGEXPOSE"
,
"ONCRMINVOICERECURRINGADD"
,
"ONCRMINVOICERECURRINGUPDATE"
,
"ONCRMINVOICERECURRINGDELETE"
,
"ONCRMINVOICERECURRINGEXPOSE"
,
"ONCRMTIMELINECOMMENTADD"
,
"ONCRMTIMELINECOMMENTUPDATE"
,
"ONCRMTIMELINECOMMENTDELETE"
,
"ONCRMDYNAMICITEMADD"
,
"ONCRMDYNAMICITEMUPDATE"
,
"ONCRMDYNAMICITEMDELETE"
,
"ONCRMDYNAMICITEMADD_147"
,
"ONCRMDYNAMICITEMUPDATE_147"
,
"ONCRMDYNAMICITEMDELETE_147"
,
"ONCRMTYPEADD"
,
"ONCRMTYPEUPDATE"
,
"ONCRMTYPEDELETE"
,
"ONCRMDOCUMENTGENERATORDOCUMENTADD"
,
"ONCRMDOCUMENTGENERATORDOCUMENTUPDATE"
,
"ONCRMDOCUMENTGENERATORDOCUMENTDELETE"
,
"ONTASKADD"
,
"ONTASKUPDATE"
,
"ONTASKDELETE"
,
"ONTASKCOMMENTADD"
,
"ONTASKCOMMENTUPDATE"
,
"ONTASKCOMMENTDELETE"
]
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response
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
Register a new event handler event.bind
Get a List of Registered Event Handlers event.get
Unbind Registered Event Handler event.unbind
Security in Handlers
Features, Advantages, and Disadvantages of Offline Events
Get a list of offline events event.offline.list
Get a List of Offline Events with `event.offline.get`
Clear records in the offline event queue event.offline.clear
Register Errors for Processing Offline Events event.offline.error
Event of Queue Change onOfflineEvent
Copied
Was the article helpful?
Yes
No
Previous
Event Handler
Next
Register a Handler

---

## Register a new event handler event.bind

**Source:** https://apidocs.bitrix24.com/api-reference/events/event-bind

Register a new event handler event.bind | Bitrix24 REST API and Marketplace Applications
Register a new event handler event.bind
Register a new event handler event.bind
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Who can execute the method: any user
The method
event.bind
registers a new event handler.
The method works only in the context of
application
authorization. It can operate both under a user with portal administration rights and under a regular user. The method for a user without administrator rights is available with limitations:
Offline events are not available; attempting to set them will raise an exception.
Events are set on behalf of the current user (see the description of the
auth_type
parameter). Explicitly specifying an
auth_type
different from the
ID
of the current user will also raise an exception.
Note
Since requests will come from Bitrix servers, any URL must be accessible for GET/POST requests from the outside.
The interface for this method is
BX24.callBind
.
Note
When deleting and updating the application, its actions will be removed. Therefore, in the installer of each version, they need to be set from scratch.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
event
*
string
Event name
handler
*
string
Link to the event handler
auth_type
integer
User ID under which the event handler is authorized. By default, the authorization of the user whose actions triggered the event will be used
event_type
string
Values:
online\|offline
. By default,
event_type=online
, and the method's behavior does not change. If
event_type=offline
is called, the method works with
offline events
auth_connector
string
Source key. This parameter is intended for
offline events
. It allows excluding false event triggers
options
string
Additional settings for the registered event, if any
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"event": "ONCRMLEADADD",
"handler": "https://www.my-domain.com/handler/",
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/event.bind
BX24
.
callBind
(
'ONCRMLEADADD'
,
'https://www.my-domain.com/handler/'
,
15
,
(
result
) =>
console
.
log
(result)
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
'event.bind'
,
[
'event'
=>
'ONCRMLEADADD'
,
'handler'
=>
'https://www.my-domain.com/handler/'
,
'auth_type'
=>
15
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
1721296536.908506
,
"finish"
:
1721296537.007365
,
"duration"
:
0.09885907173156738
,
"processing"
:
0.03251290321350098
,
"date_start"
:
"2024-07-18T11:55:36+02:00"
,
"date_finish"
:
"2024-07-18T11:55:37+02:00"
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
Success of execution
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
"ERROR_EVENT_NOT_FOUND"
,
"error_description"
:
"Event not found"
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
ERROR_EVENT_NOT_FOUND
Event not found
Incorrect event specified
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
Get a list of available events
Get a List of Registered Event Handlers event.get
Unbind Registered Event Handler event.unbind
Security in Handlers
Features, Advantages, and Disadvantages of Offline Events
Get a list of offline events event.offline.list
Get a List of Offline Events with `event.offline.get`
Clear records in the offline event queue event.offline.clear
Register Errors for Processing Offline Events event.offline.error
Event of Queue Change onOfflineEvent
How to Create an Open Channel Connector for Chat on the Site
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Available Events
Next
How to Test Your Handler

---

## How to Test Your Handler for Bitrix24 Event Processing

**Source:** https://apidocs.bitrix24.com/api-reference/events/test-handler

How to Test Your Handler for Bitrix24 Event Processing | Bitrix24 REST API and Marketplace Applications
Step 1
How to Test Your Handler for Bitrix24 Event Processing
Step 1
Step 2
Step 3
Result
After registering the handler ONAPPTEST, the method
event.test
is called manually. This triggers the specified event and allows you to verify that the handler is indeed capable of receiving event data.
Step 1
Step 1
Create a file named handler.php on your server. Ensure it is accessible from the internet. Next to the file, create a folder named \log.
Code for the file handler.php.
How to Use Examples in Documentation
PHP
<?php
file_put_contents
(
__DIR__
.
'/log/'
.
time
() .
'.txt'
,
var_export
(
$_REQUEST
,
true
)
);
?>
Step 2
Step 2
Register the event by specifying the path to the file created in Step 1 in the
handler
field.
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
'{"event":"ONAPPTEST","handler":"https://example.com/handler.php","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/event.bind
BX24
.
callMethod
(
'event.bind'
,
{
'event'
:
'ONAPPTEST'
,
'handler'
:
'https://example.com/handler.php'
},
function
(
eventBind
) {
if
(eventBind.
data
()) {
console
.
log
(
'event bind successful'
);
}
}
);
<?php
$eventBind
=
CRest
::
call
(
'event.bind'
,
[
'event'
=>
'ONAPPTEST'
,
'handler'
=>
'https://example.com/handler.php'
]
);
if
(
$eventBind
[
'result'
])
{
echo
'event bind successful'
;
}
?>
Step 3
Step 3
Trigger the event by calling the method with arbitrary data.
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
'{"any":"data","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/event.test
BX24
.
callMethod
(
'event.test'
,
{
'any'
:
'data'
},
function
(
result
) {
if
(result.
data
()) {
console
.
log
(
'successful'
);
}
}
);
<?php
$result
=
CRest
::
call
(
'event.test'
,
[
'any'
=>
'data'
]
);
if
(
$result
[
'result'
])
{
echo
'successful'
;
}
?>
Result
Result
Upon a successful call, a file with standard event data is created in the \log folder.
PHP
array
(
'event'
=>
'ONAPPTEST'
,
'data'
=>
array
(
'QUERY'
=>
array
(
'any'
=>
'data'
,
),
'LANGUAGE_ID'
=>
'en'
,
),
'ts'
=>
'1573120286'
,
'auth'
=>
array
(...)
)
Copied
Was the article helpful?
Yes
No
Previous
Register a Handler
Next
Get a List of Handlers

---

## Get a List of Registered Event Handlers event.get

**Source:** https://apidocs.bitrix24.com/api-reference/events/event-get

Get a List of Registered Event Handlers event.get | Bitrix24 REST API and Marketplace Applications
Code Examples
Get a List of Registered Event Handlers event.get
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Who can execute the method: any user
The
event.get
method allows you to retrieve a list of registered event handlers.
The method works only in the context of authorizing the
application
.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/event.get
try
{
const
response =
await
$b24.
callMethod
(
'event.get'
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
(
'Error:'
, error);
}
try
{
$eventService
=
$serviceBuilder
->
getMainScope
()->
event
();
$result
=
$eventService
->
get
();
$eventHandlers
=
$result
->
getEventHandlers
();
foreach
(
$eventHandlers
as
$handler
) {
print
(
"Event: "
.
$handler
->event .
"\n"
);
print
(
"Handler: "
.
$handler
->handler .
"\n"
);
print
(
"Auth Type: "
.
$handler
->auth_type .
"\n"
);
print
(
"Offline: "
.
$handler
->offline .
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
());
}
BX24
.
callMethod
(
"event.get"
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
'event.get'
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
"event"
:
"ONCRMLEADADD"
,
"handler"
:
"https:\/\/www.my-domain.com\/handler\/"
,
"auth_type"
:
"0"
,
"offline"
:
0
}
,
{
"event"
:
"ONCRMLEADADD"
,
"handler"
:
"https:\/\/www.my-domain.com\/handler\/"
,
"auth_type"
:
"15"
,
"offline"
:
0
}
]
,
"time"
:
{
"start"
:
1721297941.536696
,
"finish"
:
1721297941.661148
,
"duration"
:
0.12445211410522461
,
"processing"
:
0.0029609203338623047
,
"date_start"
:
"2024-07-18T12:19:01+02:00"
,
"date_finish"
:
"2024-07-18T12:19:01+02:00"
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
Get a list of available events
Register a new event handler event.bind
Unbind Registered Event Handler event.unbind
Security in Handlers
Features, Advantages, and Disadvantages of Offline Events
Get a list of offline events event.offline.list
Get a List of Offline Events with `event.offline.get`
Clear records in the offline event queue event.offline.clear
Register Errors for Processing Offline Events event.offline.error
Event of Queue Change onOfflineEvent
Copied
Was the article helpful?
Yes
No
Previous
How to Test Your Handler
Next
Unregister a Handler

---

## Unbind Registered Event Handler event.unbind

**Source:** https://apidocs.bitrix24.com/api-reference/events/event-unbind

Unbind Registered Event Handler event.unbind | Bitrix24 REST API and Marketplace Applications
Method Parameters
Unbind Registered Event Handler event.unbind
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
See Also
Continue Learning
Who can execute the method: administrator
The
event.unbind
method cancels a registered event handler.
This method works only in the context of
application
authorization and only when authorized under a user with administrative rights to the account.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
event
*
string
Event name
handler
*
string
Link to the event handler
auth_type
integer
User identifier under which the event handler is authorized.
Note
If you need to remove event handlers set with an empty
auth_type
(authorized on behalf of the user who triggered the event), but keep the other handlers, specify
auth_type=0
or an empty value for the parameter.
event_type
string
Values:
online\|offline
. By default,
event_type=online
, and the method's behavior remains unchanged. If
event_type=offline
is called, the method works with
offline events
If any parameters are not specified, all event handlers that meet the other requirements will be removed.
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
PHP (B24PhpSdk)
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"event": "ONCRMLEADADD",
"handler": "https://www.my-domain.com/handler/",
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/event.unbind
BX24
.
callUnbind
(
'ONCRMLEADADD'
,
'https://www.my-domain.com/handler/'
,
15
,
(
result
) =>
console
.
log
(result)
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
'event.unbind'
,
[
'EVENT'
=>
'ONCRMLEADADD'
,
'HANDLER'
=>
'https://www.my-domain.com/handler/'
,
'AUTH_TYPE'
=>
15
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
try
{
$eventCode
=
'your_event_code'
;
// Replace with your actual event code
$handlerUrl
=
'https://your.handler.url'
;
// Replace with your actual handler URL
$userId
=
null
;
// Replace with your actual user ID or leave as null
$result
=
$serviceBuilder
->
getMainScope
()
->
event
()
->
unbind
(
$eventCode
,
$handlerUrl
,
$userId
);
print
(
$result
->
getUnbindedHandlersCount
());
}
catch
(
Throwable
$e
) {
print
(
'Error: '
.
$e
->
getMessage
());
}
Response Handling
Response Handling
HTTP status:
200
The method returns the number of event handlers removed upon invocation.
{
"result"
:
{
"count"
:
1
}
,
"time"
:
{
"start"
:
1721298360.468008
,
"finish"
:
1721298360.553977
,
"duration"
:
0.0859689712524414
,
"processing"
:
0.0023431777954101562
,
"date_start"
:
"2024-07-18T12:26:00+02:00"
,
"date_finish"
:
"2024-07-18T12:26:00+02:00"
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
See Also
See Also
Call the interface to remove a registered event handler BX24.callUnbind
Continue Learning
Continue Learning
Get a list of available events
Register a new event handler event.bind
Get a List of Registered Event Handlers event.get
Security in Handlers
Features, Advantages, and Disadvantages of Offline Events
Get a list of offline events event.offline.list
Get a List of Offline Events with `event.offline.get`
Clear records in the offline event queue event.offline.clear
Register Errors for Processing Offline Events event.offline.error
Event of Queue Change onOfflineEvent
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Handlers
Next
Security

---

## Security in Handlers

**Source:** https://apidocs.bitrix24.com/api-reference/events/safe-event-handlers

Security in Handlers | Bitrix24 REST API and Marketplace Applications
Continue Learning
Security in Handlers
The application developer in event handlers must ensure that the handler is being called by Bitrix24 and not by malicious actors. To achieve this, Bitrix24 passes an additional parameter
application_token
when invoking handlers.
The first time, the parameter is sent to the event handler
OnAppInstall
along with the authorization data of the user who installed the application. Using this authorization data, the
OnAppInstall
event handler can verify the validity of the received
access_token
and then store the application_token for future reference, allowing it to compare the received application_token with the stored one in its other event handlers.
This is particularly relevant in the event handler
OnAppUninstall
, as no authorization data is passed to it (the application has already been removed from Bitrix24). Therefore, in the case of OnAppUninstall, verifying the application_token against the stored value becomes the only way to ensure that the event handler was indeed called by Bitrix24.
Continue Learning
Continue Learning
Get a list of available events
Register a new event handler event.bind
Get a List of Registered Event Handlers event.get
Unbind Registered Event Handler event.unbind
Features, Advantages, and Disadvantages of Offline Events
Get a list of offline events event.offline.list
Get a List of Offline Events with `event.offline.get`
Clear records in the offline event queue event.offline.clear
Register Errors for Processing Offline Events event.offline.error
Event of Queue Change onOfflineEvent
Copied
Was the article helpful?
Yes
No
Previous
Unregister a Handler
Next
Offline Events

---

## Features, Advantages, and Disadvantages of Offline Events

**Source:** https://apidocs.bitrix24.com/api-reference/events/offline-events

Features, Advantages, and Disadvantages of Offline Events | Bitrix24 REST API and Marketplace Applications
Features, Advantages, and Disadvantages of Offline Events
Features, Advantages, and Disadvantages of Offline Events
How Offline Events Work
Why Offline Events Are Needed
How to Build Work with Offline Events
Method event.offline.get
How to Avoid Cycles in Processing
Disadvantages of the Offline Event Mechanism
"Tricks" for Using Offline Events
Continue Your Learning
You can register an offline event handler using the same method
event.bind
. However, the parameters will differ slightly:
Parameter
type
Description
event
string
Event name
event_type
string
Must be
offline
auth_connector
string
Source key. Allows you to
exclude false triggers
options
array
Additional settings for the registered event. Possible values depend on the specific event
First, you need to set the
event_type
parameter to
offline
.
Secondly, there is no longer a need to specify the
handler
parameter, as it will not be Bitrix24 calling your handler; instead, the application will need to call Bitrix24 to get information about the events that occurred.
How Offline Events Work
How Offline Events Work
Unlike regular events, offline events do not trigger external application handlers but log the changes that occurred.
The application can retrieve data from this log using the
event.offline.list
and
event.offline.get
methods.
In the case of multiple changes to the same object, for example, when a user edits a single deal, the log will contain only one entry for that. The entry will be marked with the date and time of the most recent change.
No matter how many times we change the same deal, it will not add new offline events one after another; instead, it will update the existing information. If the same deal is updated 1000 times, there will be only one entry in the offline events indicating which deal was changed.
Why Offline Events Are Needed
Why Offline Events Are Needed
The purpose of offline events is primarily for synchronizing data between Bitrix24 and an external system.
Such tasks often do not require real-time responses. For these tasks, it is not necessary to react immediately to every change.
It is important that when your application queries Bitrix24, you are fully aware of which Bitrix24 objects have been changed, added, or deleted since the last time the application accessed Bitrix24.
Even if the same deal has been changed a hundred times, to synchronize this deal with an external system, it is sufficient to take only the current state of the deal at the time of synchronization.
That is why Bitrix24 does not log every change of the same object in the offline events. This significantly simplifies application development for you.
How to Build Work with Offline Events
How to Build Work with Offline Events
At regular intervals, your application should request a list of occurred events.
Then, using standard REST API methods, the application should retrieve the current information about the changed objects and send the updated data to the external system, etc.
Most importantly, in the final step, the application must inform Bitrix24 that these events have been processed by the application and that there is no need to retain information about them.
If this is not done, each time you access the list of offline events, you will receive more and more accumulated events.
Method event.offline.get
Method event.offline.get
Using
event.offline.get
, you can parse all accumulated events, retrieving them in batches of 50.
The method is optimized for asynchronous use. This means that each parallel call to
event.offline.get
will reliably receive its events, without overlapping with other events, regardless of how intensively you request this data.
Moreover, each call to the
event.offline.get
method with default parameters will not only retrieve the next 50 log entries but will also delete those entries.
Consequently, there may be a situation where your application made a request to
event.offline.get
, but for some reason (due to memory overflow, network issues, etc.) did not process those events. However, on the Bitrix24 side, the information about those events has already been deleted and cannot be restored.
To ensure the processing of all offline events, you can call the
event.offline.get
method with the parameter
clear = 0
. In this case, the batch of returned events will not be deleted in Bitrix24. Instead, it will be marked with a unique identifier
process_id
and "hidden."
After processing the received events, the application must inform Bitrix24 that these events can be deleted.
To do this, the application should call the
method
event.offline.clear
, specifying the
process_id
parameter — the unique identifier obtained when calling the
event.offline.get
method, and optionally specifying the
message_id
parameter as an array of identifiers for specific events that need to be deleted.
How to Avoid Cycles in Processing
How to Avoid Cycles in Processing
Imagine a situation where your application receives an event about a deal change.
Then it requests the current information about the deal using the corresponding REST API method. After that, it wants to change the same deal in Bitrix24 based on its business logic. For this, the application calls the
crm.deal.update
method.
In the case of regular events, as soon as the application calls the
crm.deal.update
method, Bitrix24 immediately sends the
ONCRMDEALUPDATE
event to the handler registered by the application.
This creates a closed loop where changing the deal on the Bitrix24 side triggers the handler in the application, which changes the deal data in Bitrix24, which triggers the handler in the application, which… and so on.
Handling such a situation requires certain conditions in the application.
In the case of offline events, such a cycle can be avoided. To do this, when registering the offline event handler, you need to specify the
auth_connector
parameter.
This creates a separate queue of offline events tied to a specific data exchange channel between Bitrix24 and the application.
Then, you need to use this same parameter when you call
crm.deal.update
if you want to change data in Bitrix24 without triggering a repeated offline event.
The entire scheme using the
auth_connector
parameter is designed so that when the application modifies data, it informs Bitrix24: do not notify me about changes that I initiated myself.
The conclusion is that if you are using the offline event mechanism in Bitrix24, all modifying requests from your application should be executed with the
auth_connector
parameter to avoid unnecessary events. This will greatly simplify your life.
It is worth noting that this parameter is currently supported in Bitrix24 on the Pro plan and above. Keep this in mind during development.
Disadvantages of the Offline Event Mechanism
Disadvantages of the Offline Event Mechanism
The offline event mechanism has its advantages, but you should also understand the downsides of this approach.
First, unlike regular events, where Bitrix24 calls your handlers, with offline events, you will need to create some mechanism that periodically queries Bitrix24. This is especially non-trivial for
mass-market applications
that may be installed on hundreds or thousands of different Bitrix24 instances.
Secondly, since your application will be querying Bitrix24 for new events via the REST API, the usual rate limits on requests per second and total execution time for requests will apply. You can learn more about the limits from the
relevant article
.
The main takeaway is that retrieving offline events may take longer than it would for regular online events.
"Tricks" for Using Offline Events
"Tricks" for Using Offline Events
However, there is a clever possibility that somewhat combines the advantages of online and offline events.
Namely, the
special event
ONOFFLINEEVENT
. By subscribing to it in the usual way, that is, by specifying your handler on the application side, you will receive calls to this handler if new entries appear in the offline events queue.
In the
minTimeout
parameter, you can specify a timeout in seconds. In this case, your handler will only be called if the specified number of seconds has passed since the last call.
This setting is very convenient if you do not want your application to receive signals too frequently when there may be too few offline events accumulated.
Thus, your application, on one hand, automatically receives a signal from Bitrix24 that it is time to fetch offline events. This means you do not need to devise a scheme for periodic polling of Bitrix24.
On the other hand, you can independently retrieve the events that interest you from the offline events queue with all the advantages of this mechanism.
Continue Your Learning
Continue Your Learning
Get a list of available events
Register a new event handler event.bind
Get a List of Registered Event Handlers event.get
Unbind Registered Event Handler event.unbind
Security in Handlers
Get a list of offline events event.offline.list
Get a List of Offline Events with `event.offline.get`
Clear records in the offline event queue event.offline.clear
Register Errors for Processing Offline Events event.offline.error
Event of Queue Change onOfflineEvent
Copied
Was the article helpful?
Yes
No
Previous
Security
Next
Get a List of Offline Events

---

## Get a list of offline events event.offline.list

**Source:** https://apidocs.bitrix24.com/api-reference/events/event-offline-list

Get a list of offline events event.offline.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of offline events event.offline.list
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Who can execute the method: any user
The method
event.offline.list
is used to read the current queue without making changes to its state, unlike
event.offline.get
. The availability of offline events can be checked through the
feature.get
method.
The method works only in the context of application authorization
application
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
filter
array
Record filter. By default, all records are returned without filtering. Filtering is supported by the fields:
ID
,
TIMESTAMP_X
,
EVENT_NAME
,
MESSAGE_ID
,
PROCESS_ID
,
ERROR
with standard operations like
=
,
>
,
<
,
<=
, and so on
order
array
Record sorting. Sorting is supported by the same fields as in the filter, and an array of the form `[field=>ASC
DESC]
is accepted. By default —
[ID:ASC]`
start
integer
This parameter is used to manage pagination.
The page size of results is always static: 50 records.
To select the second page of results, you need to pass the value
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
is the desired page number
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"filter": {
"ERROR": 0
},
"order": {
"ID": "DESC"
},
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/event.offline.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'event.offline.list'
,
{
"filter"
: {
"ERROR"
:
0
},
"order"
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'event.offline.list'
, {
"filter"
: {
"ERROR"
:
0
},
"order"
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'event.offline.list'
, {
"filter"
: {
"ERROR"
:
0
},
"order"
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
'event.offline.list'
,
[
'filter'
=> [
'ERROR'
=>
0
,
],
'order'
=> [
'ID'
=>
'DESC'
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
'Error fetching offline events: '
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
"event.offline.list"
,
{
"filter"
: {
"ERROR"
:
0
},
"order"
: {
"ID"
:
"DESC"
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
'event.offline.list'
,
[
'filter'
=> [
'ERROR'
=>
0
],
'order'
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
"2"
,
"TIMESTAMP_X"
:
"2024-07-18T12:32:31+02:00"
,
"EVENT_NAME"
:
"ONCRMCOMPANYADD"
,
"EVENT_DATA"
:
false
,
"EVENT_ADDITIONAL"
:
false
,
"MESSAGE_ID"
:
"2"
,
"PROCESS_ID"
:
""
,
"ERROR"
:
"0"
}
,
{
"ID"
:
"1"
,
"TIMESTAMP_X"
:
"2024-07-18T12:32:31+02:00"
,
"EVENT_NAME"
:
"ONCRMLEADADD"
,
"EVENT_DATA"
:
false
,
"EVENT_ADDITIONAL"
:
false
,
"MESSAGE_ID"
:
"1"
,
"PROCESS_ID"
:
""
,
"ERROR"
:
"0"
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
1721299537.90267
,
"finish"
:
1721299538.02201
,
"duration"
:
0.11934018135070801
,
"processing"
:
0.0029511451721191406
,
"date_start"
:
"2024-07-18T12:45:37+02:00"
,
"date_finish"
:
"2024-07-18T12:45:38+02:00"
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
total
integer
Total number of records found
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
Get a list of available events
Register a new event handler event.bind
Get a List of Registered Event Handlers event.get
Unbind Registered Event Handler event.unbind
Security in Handlers
Features, Advantages, and Disadvantages of Offline Events
Get a List of Offline Events with `event.offline.get`
Clear records in the offline event queue event.offline.clear
Register Errors for Processing Offline Events event.offline.error
Event of Queue Change onOfflineEvent
Copied
Was the article helpful?
Yes
No
Previous
Offline Events
Next
Get a List of Offline Events with "Cleanup"

---

## Get a List of Offline Events with <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-5c1gaftv">event.offline.get</code>

**Source:** https://apidocs.bitrix24.com/api-reference/events/event-offline-get

Get a List of Offline Events with <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-5c1gaftv">event.offline.get</code> | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a List of Offline Events with
event.offline.get
Method Parameters
Additional Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Who can execute the method: any user
The method
event.offline.get
returns the first queued offline events to the application according to the filter settings. The availability of offline events can be checked using the
feature.get
method.
This method works only in the context of
application
authorization.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
filter
array
Record filter. By default, all records are returned without filtering. Filtering is supported by fields:
ID
,
TIMESTAMP_X
,
EVENT_NAME
,
MESSAGE_ID
with standard operations like
=
,
>
,
<
,
<=
, and so on.
Important: the operation type is placed before the field name in the filter
order
array
Record sorting. Sorting is supported by the same fields as in the filter, and an array of the form `[field=>ASC
DESC]` is accepted. By default — [TIMESTAMP_X:ASC]
limit
integer
Number of records to select. Default is 50
Additional Parameters
Additional Parameters
Name
type
Description
clear
integer
Values: `0
1
— whether to delete the selected records. Default is
1`
process_id
string
Process identifier. Used if you need to re-select any unprocessed records from the current process
auth_connector
string
Source key. Used if the
auth_connector
value was specified in the
event.bind
method
error
integer
Values: `0
1
— whether to return erroneous records. Default is
0`
Note
The method supports multithreaded parsing. This means that multiple parallel requests to /rest/event.offline.get are allowed (subject to limits on the number of requests per unit of time), and each will receive different sets of records.
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"filter":{"=MESSAGE_ID":1,"=EVENT_NAME":"ONCRMLEADADD",">=ID":1},"auth_connector":"BxTest","auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/event.offline.get
try
{
const
response =
await
$b24.
callMethod
(
'event.offline.get'
,
{
filter
: {
'=MESSAGE_ID'
:
1
,
'=EVENT_NAME'
:
'ONCRMLEADADD'
,
'>=ID'
:
1
},
auth_connector
:
'BxTest'
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
processResult
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
'event.offline.get'
,
[
'filter'
=> [
'=MESSAGE_ID'
=>
1
,
'=EVENT_NAME'
=>
'ONCRMLEADADD'
,
'>=ID'
=>
1
],
'auth_connector'
=>
'BxTest'
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
BX24
.
callMethod
(
"event.offline.get"
,
{
"filter"
: {
"=MESSAGE_ID"
:
1
,
"=EVENT_NAME"
:
"ONCRMLEADADD"
,
">=ID"
:
1
},
"auth_connector"
:
"BxTest"
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
'event.offline.get'
,
[
'filter'
=> [
'=MESSAGE_ID'
=>
1
,
'=EVENT_NAME'
=>
'ONCRMLEADADD'
,
'>=ID'
=>
1
],
'auth_connector'
=>
'BxTest'
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
"process_id"
:
null
,
"events"
:
[
{
"ID"
:
"1"
,
"TIMESTAMP_X"
:
"2024-07-18T12:32:31+02:00"
,
"EVENT_NAME"
:
"ONCRMLEADADD"
,
"EVENT_DATA"
:
false
,
"EVENT_ADDITIONAL"
:
false
,
"MESSAGE_ID"
:
"1"
}
]
}
,
"time"
:
{
"start"
:
1721299720.388504
,
"finish"
:
1721299720.509809
,
"duration"
:
0.12130498886108398
,
"processing"
:
0.008239030838012695
,
"date_start"
:
"2024-07-18T12:48:40+02:00"
,
"date_finish"
:
"2024-07-18T12:48:40+02:00"
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
Get a list of available events
Register a new event handler event.bind
Get a List of Registered Event Handlers event.get
Unbind Registered Event Handler event.unbind
Security in Handlers
Features, Advantages, and Disadvantages of Offline Events
Get a list of offline events event.offline.list
Clear records in the offline event queue event.offline.clear
Register Errors for Processing Offline Events event.offline.error
Event of Queue Change onOfflineEvent
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Offline Events
Next
Clear Offline Event Queues

---

## Clear records in the offline event queue event.offline.clear

**Source:** https://apidocs.bitrix24.com/api-reference/events/event-offline-clear

Clear records in the offline event queue event.offline.clear | Bitrix24 REST API and Marketplace Applications
Method parameters
Clear records in the offline event queue event.offline.clear
Method parameters
Code examples
Response handling
Returned data
Error handling
Statuses and System Error Codes
Continue learning
Who can execute the method: any user
The method
event.offline.clear
clears records in the offline event queue. The availability of offline events can be checked through the method
feature.get
.
The method works only in the context of application authorization
application
.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
process_id
*
string
Identifier of the process that handles the records
id
array
Array of identifiers of the records to be cleared. By default, all records marked with the provided
process_id
will be cleared
message_id
array
Array of values of the
MESSAGE_ID
field of the records to be cleared. Ignored if the
id
parameter is specified. By default, all records marked with the provided
process_id
will be cleared
Code examples
Code examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"process_id": "yh3gu929sf0d32lsfysqas2y1hlpp09q",
"id": [2],
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/event.offline.clear
try
{
const
response =
await
$b24.
callMethod
(
'event.offline.clear'
,
{
'process_id'
:
'yh3gu929sf0d32lsfysqas2y1hlpp09q'
,
'id'
: [
2
]
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
'event.offline.clear'
,
[
'process_id'
=>
'yh3gu929sf0d32lsfysqas2y1hlpp09q'
,
'id'
=> [
2
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
'Error clearing offline event: '
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
"event.offline.clear"
,
{
"process_id"
:
"yh3gu929sf0d32lsfysqas2y1hlpp09q"
,
"id"
: [
2
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
'event.offline.clear'
,
[
'process_id'
=>
'yh3gu929sf0d32lsfysqas2y1hlpp09q'
,
'id'
=> [
2
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
Response handling
Response handling
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
1721300421.210707
,
"finish"
:
1721300421.331026
,
"duration"
:
0.12031912803649902
,
"processing"
:
0.0022459030151367188
,
"date_start"
:
"2024-07-18T13:00:21+02:00"
,
"date_finish"
:
"2024-07-18T13:00:21+02:00"
,
"operating"
:
0
}
}
Returned data
Returned data
Name
type
Description
result
boolean
Success of execution
time
time
Information about the execution time of the request
Error handling
Error handling
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
Continue learning
Continue learning
Get a list of available events
Register a new event handler event.bind
Get a List of Registered Event Handlers event.get
Unbind Registered Event Handler event.unbind
Security in Handlers
Features, Advantages, and Disadvantages of Offline Events
Get a list of offline events event.offline.list
Get a List of Offline Events with `event.offline.get`
Register Errors for Processing Offline Events event.offline.error
Event of Queue Change onOfflineEvent
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Offline Events with "Cleanup"
Next
Register Queue Processing Errors

---

## Register Errors for Processing Offline Events event.offline.error

**Source:** https://apidocs.bitrix24.com/api-reference/events/event-offline-error

Register Errors for Processing Offline Events event.offline.error | Bitrix24 REST API and Marketplace Applications
Method Parameters
Register Errors for Processing Offline Events event.offline.error
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Who can execute the method: any user
The method
event.offline.error
saves a record in the database with an error mark when using offline events. The availability of offline events can be checked through the method
feature.get
.
The method works only in the context of authorizing the
application
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
process_id
*
string
Identifier of the process that is handling the records
message_id
array
Array of values for the
MESSAGE_ID
field of the records to be marked as erroneous
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"process_id": "yh3gu929sf0d32lsfysqas2y1hlpp09q",
"message_id": [2],
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/event.offline.error
try
{
const
response =
await
$b24.
callMethod
(
'event.offline.error'
,
{
'process_id'
:
'yh3gu929sf0d32lsfysqas2y1hlpp09q'
,
'message_id'
: [
2
]
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
'event.offline.error'
,
[
'process_id'
=>
'yh3gu929sf0d32lsfysqas2y1hlpp09q'
,
'message_id'
=> [
2
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
'Error handling offline event: '
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
"event.offline.error"
,
{
"process_id"
:
"yh3gu929sf0d32lsfysqas2y1hlpp09q"
,
"message_id"
: [
2
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
'event.offline.error'
,
[
'process_id'
=>
'yh3gu929sf0d32lsfysqas2y1hlpp09q'
,
'message_id'
=> [
2
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
1721300231.498173
,
"finish"
:
1721300231.596196
,
"duration"
:
0.0980229377746582
,
"processing"
:
0.0019490718841552734
,
"date_start"
:
"2024-07-18T12:57:11+02:00"
,
"date_finish"
:
"2024-07-18T12:57:11+02:00"
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
Success of execution
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
Get a list of available events
Register a new event handler event.bind
Get a List of Registered Event Handlers event.get
Unbind Registered Event Handler event.unbind
Security in Handlers
Features, Advantages, and Disadvantages of Offline Events
Get a list of offline events event.offline.list
Get a List of Offline Events with `event.offline.get`
Clear records in the offline event queue event.offline.clear
Event of Queue Change onOfflineEvent
Copied
Was the article helpful?
Yes
No
Previous
Clear Offline Event Queues
Next
Queue Change Event

---

## Event of Queue Change onOfflineEvent

**Source:** https://apidocs.bitrix24.com/api-reference/events/on-offline-event

Event of Queue Change onOfflineEvent | Bitrix24 REST API and Marketplace Applications
Event of Queue Change onOfflineEvent
Event of Queue Change onOfflineEvent
What the Handler Receives
Request Parameters
Parameter data
Parameter auth
Continue Learning
Who can subscribe: any user
The
onOfflineEvent
notifies about the occurrence of new offline events at certain intervals.
The application can subscribe to two types of events.
Regular: the event triggers an external URL and performs an action defined by that address.
Offline: instead of calling an external URL, events are locally saved on the account, from where they can later be retrieved using the methods
event.offline.*
.
For the
onOfflineEvent
, the necessity of sending a notification is determined based on the local saving, and then it is sent as a regular event to the external URL.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
{
"event": "ONOFFLINEEVENT",
"data": {
"type": "add",
"event": "onTaskAdd",
"handler": "https://example.com/handler.php",
"minTimeout": 5
},
"ts": "1466439714",
"auth": {
"access_token": "s6p6eclrvim6da22ft9ch94ekreb52lv",
"expires_in": "3600",
"scope": "task",
"domain": "some-domain.bitrix24.com",
"server_endpoint": "https://oauth.bitrix.info/rest/",
"status": "F",
"client_endpoint": "https://some-domain.bitrix24.com/rest/",
"member_id": "a223c6b3710f85df22e9377d6c4f7553",
"refresh_token": "4s386p3q0tr8dy89xvmt96234v3dljg8",
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
Symbolic code of the event —
ONOFFLINEEVENT
data
*
array
Data about the event in the queue.
The structure is described
below
ts
*
timestamp
Date and time of the event sending
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
type
*
string
Type of change:
add
,
remove
,
update
event
*
string
Name of the event. For example,
onTaskAdd
handler
*
string
URL of the event handler
minTimeout
integer
Minimum delay before sending the event in seconds. Used for event grouping. Default is 1 sec. If the parameter value:
is
0
, regardless of the number of events added to the offline queue, only one event will be sent to the handler's address within one hit
is greater than
0
, upon the first trigger, it sends one event. Then a pause is made for at least the timeout duration before sending the next event
The
minTimeout
field appears only if the event is added to the queue with a delay
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
Address of the Bitrix24 authorization server needed for refreshing OAuth 2.0 tokens
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
General path for API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
*
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event processing
offline_event — the application is not always able to receive events. It may be hidden behind firewalls, reside in an internal network, and so on. In this case, the offline event mechanism is used, where the application subscribes to events but does not specify a handler URL.
Continue Learning
Continue Learning
Get a list of available events
Register a new event handler event.bind
Get a List of Registered Event Handlers event.get
Unbind Registered Event Handler event.unbind
Security in Handlers
Features, Advantages, and Disadvantages of Offline Events
Get a list of offline events event.offline.list
Get a List of Offline Events with `event.offline.get`
Clear records in the offline event queue event.offline.clear
Register Errors for Processing Offline Events event.offline.error
Copied
Was the article helpful?
Yes
No
Previous
Register Queue Processing Errors
Next
General Methods and Events

---

