---
description: 'Widgets UI Interaction: Page background workers, call cards, dialogs'
methods:
- placement.bind
- placement.bindEvent
- placement.call
- placement.getInterface
- placement.info
pages: 41
title: 'Widgets UI Interaction: Page background workers, call cards, dialogs'
---
# Widgets UI Interaction: Page background workers, call cards, dialogs
> Widgets UI Interaction: Page background workers, call cards, dialogs
> **41 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Interaction with UI from Widgets](#interaction-with-ui-from-widgets)
- [Special Interaction Features](#special-interaction-features)
- [Get Information About the Call Context of BX24.placement.info](#get-information-about-the-call-context-of-bx24plac)
- [Get Information About the JS Interface of the Current Placement BX24.placement.getInterface](#get-information-about-the-js-interface-of-the-curr)
- [Call the Registered Interface Command BX24.placement.call](#call-the-registered-interface-command-bx24placemen)
- [Set Up an Event Handler for the Interface BX24.placement.bindEvent](#set-up-an-event-handler-for-the-interface-bx24plac)
- [Interaction with CRM Card](#interaction-with-crm-card)
- [Interaction with the CALL_CARD](#interaction-with-the-callcard)
- [Get Call Status getStatus](#get-call-status-getstatus)
- [Disable Auto-Close disableAutoClose](#disable-auto-close-disableautoclose)
- [Disable Auto-Close enableAutoClose](#disable-auto-close-enableautoclose)
- [Event of Client Change CallCard::EntityChanged](#event-of-client-change-callcardentitychanged)
- [Event Before Closing the CallCard CallCard::BeforeClose](#event-before-closing-the-callcard-callcardbeforecl)
- [Event of Call Status Change CallCard::CallStateChanged](#event-of-call-status-change-callcardcallstatechang)
- [WebRTC Integration Scenario](#webrtc-integration-scenario)
- [Call Card](#call-card)
- [Disable Operator Microphone from the CallCardSetMute Application](#disable-operator-microphone-from-the-callcardsetmu)
- [Set a Call on Hold from the CallCardSetHold Application](#set-a-call-on-hold-from-the-callcardsethold-applic)
- [Change the state of the call card interface from the CallCardSetUiState application](#change-the-state-of-the-call-card-interface-from-t)
- [Get a List of Available Call Card UI States CallCardGetListUiStates](#get-a-list-of-available-call-card-ui-states-callca)
- [Change the title of the call card from the CallCardSetCardTitle application](#change-the-title-of-the-call-card-from-the-callcar)
- [Change Text in the Center of the Call Card from the Application CallCardSetStatusText](#change-text-in-the-center-of-the-call-card-from-th)
- [Close the call card from the CallCardClose application](#close-the-call-card-from-the-callcardclose-applica)
- [Event Overview](#event-overview)
- [After Creating the Call Card BackgroundCallCard::initialized](#after-creating-the-call-card-backgroundcallcardini)
- [When saving a comment in the call card BackgroundCallCard::addCommentButtonClick](#when-saving-a-comment-in-the-call-card-backgroundc)
- [On Clicking the Mute Button BackgroundCallCard::muteButtonClick](#on-clicking-the-mute-button-backgroundcallcardmute)
- [On Clicking the Hold Call Button BackgroundCallCard::holdButtonClick](#on-clicking-the-hold-call-button-backgroundcallcar)
- [On Clicking the Call End Button BackgroundCallCard::closeButtonClick](#on-clicking-the-call-end-button-backgroundcallcard)
- [When selecting an operator to whom the current operator wants to transfer the call BackgroundCallCard::transferButtonClick](#when-selecting-an-operator-to-whom-the-current-ope)
- [On Clicking the "Return to Call" Button BackgroundCallCard::cancelTransferButtonClick](#on-clicking-the-return-to-call-button-backgroundca)
- [On clicking the "redirect" button BackgroundCallCard::completeTransferButtonClick](#on-clicking-the-redirect-button-backgroundcallcard)
- [On Clicking the "End" Button BackgroundCallCard::hangupButtonClick](#on-clicking-the-end-button-backgroundcallcardhangu)
- [On Clicking the "Next" Button BackgroundCallCard::nextButtonClick](#on-clicking-the-next-button-backgroundcallcardnext)
- [On Clicking the "Skip" Button BackgroundCallCard::skipButtonClick](#on-clicking-the-skip-button-backgroundcallcardskip)
- [On Clicking the "Reply" Button BackgroundCallCard::answerButtonClick](#on-clicking-the-reply-button-backgroundcallcardans)
- [In the Call Review Card when changing the current entity BackgroundCallCard::entityChanged](#in-the-call-review-card-when-changing-the-current-)
- [On Clicking the "Call Back" Button BackgroundCallCard::makeCallButtonClick](#on-clicking-the-call-back-button-backgroundcallcar)
- [When Evaluating Call Quality BackgroundCallCard::qualityMeterClick](#when-evaluating-call-quality-backgroundcallcardqua)
- [On pressing one of the numeric buttons on the phone BackgroundCallCard::dialpadButtonClick](#on-pressing-one-of-the-numeric-buttons-on-the-phon)
- [On Clicking the "Notify Administrator" Button BackgroundCallCard::notifyAdminButtonClick](#on-clicking-the-notify-administrator-button-backgr)

---

## Interaction with UI from Widgets

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/index

Interaction with UI from Widgets | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Interaction with UI from Widgets
We are still updating this page
Some data may be missing — we will complete it soon.
This section describes the methods that enable the integration of third-party applications into the Bitrix24 interface. The unique aspect of these methods is that they do not make a physical request to the server but work with the page where the application is embedded. Data exchange occurs via
postMessage
.
Overview of Methods
Overview of Methods
Scope:
placement
Method
Description
BX24.placement.info
Retrieves information about the context of the call
BX24.placement.getInterface
Retrieves information about the JS interface of the current embedding location: a list of possible commands and events
BX24.placement.call
Calls a registered interface command
BX24.placement.bindEvent
Sets an event handler for the interface
Copied
Was the article helpful?
Yes
No
Previous
Close custom slider
Next
Special Features of Some Widgets

---

## Special Interaction Features

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/special-js-tools

Special Interaction Features | Bitrix24 REST API and Marketplace Applications
Special Interaction Features
Special Interaction Features
We are still updating this page
Some data may be missing here — we will complete it soon.
Was the article helpful?
Yes
No
Previous
Interaction with UI from Widgets
Next
Get Execution Context

---

## Get Information About the Call Context of BX24.placement.info

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/bx24-placement-info

Get Information About the Call Context of BX24.placement.info | Bitrix24 REST API and Marketplace Applications
Code Example
Get Information About the Call Context of BX24.placement.info
Code Example
Result
Continue Your Learning
Scope:
placement
The method
BX24.placement.info
retrieves information about the context of the embedding handler call.
No parameters.
Code Example
Code Example
How to Use Examples in Documentation
BX24
.
ready
(
function
(
) {
BX24
.
init
(
function
(
) {
var
placementInfo =
BX24
.
placement
.
info
();
console
.
info
(
"placement = "
+ placementInfo[
"placement"
]
+
", options = "
+ placementInfo[
"options"
]);
});
});
Result
Result
{
"placement"
:
"CRM_LEAD_LIST_MENU"
,
"options"
:
{
"ID"
:
"1348"
}
}
Continue Your Learning
Continue Your Learning
Get Information About the JS Interface of the Current Placement BX24.placement.getInterface
Call the Registered Interface Command BX24.placement.call
Set Up an Event Handler for the Interface BX24.placement.bindEvent
Copied
Was the article helpful?
Yes
No
Previous
Special Features of Some Widgets
Next
Get List of Methods and Events

---

## Get Information About the JS Interface of the Current Placement BX24.placement.getInterface

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/bx24-placement-get-interface

Get Information About the JS Interface of the Current Placement BX24.placement.getInterface | Bitrix24 REST API and Marketplace Applications
Parameters
Get Information About the JS Interface of the Current Placement BX24.placement.getInterface
Parameters
Code Example
Result
Continue Your Learning
Scope:
placement
The method
BX24.placement.getInterface
allows you to retrieve information about the JS interface of the current placement: a list of available commands and events.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
callback
*
callable
Callback function.
The
callback
handler will receive an object of the form
{command: array, event: array}
, where:
command
— list of available commands
event
— list of available events
For example: the placement
CALL_CARD
is intended for working with the call card in the CRM
Code Example
Code Example
How to Use Examples in Documentation
BX24
.
ready
(
function
(
) {
BX24
.
init
(
function
(
) {
BX24
.
placement
.
getInterface
(
(
result
) =>
{
console
.
info
(result);
});
});
});
Result
Result
{
"command"
:
[
"getStatus"
,
"disableAutoClose"
,
"enableAutoClose"
…
]
,
"event"
:
[
{
"CallCard::EntityChanged"
,
"CallCard::CallStateChanged"
,
"CallCard::BeforeClose"
…
}
]
}
Continue Your Learning
Continue Your Learning
Get Information About the Call Context of BX24.placement.info
Call the Registered Interface Command BX24.placement.call
Set Up an Event Handler for the Interface BX24.placement.bindEvent
Copied
Was the article helpful?
Yes
No
Previous
Get Execution Context
Next
Call Widget Method

---

## Call the Registered Interface Command BX24.placement.call

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/bx24-placement-call

Call the Registered Interface Command BX24.placement.call | Bitrix24 REST API and Marketplace Applications
Parameters
Call the Registered Interface Command BX24.placement.call
Parameters
Code Example
Continue Learning
Scope:
placement
The method
BX24.placement.call
invokes a registered interface command.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
command
*
string
The command to be invoked
parameters
object
Parameters to be passed
callback
*
callable
Callback function
Code Example
Code Example
How to Use Examples in Documentation
BX24
.
ready
(
function
(
) {
BX24
.
init
(
function
(
) {
BX24
.
placement
.
call
(
'getStatus'
, {},
function
(
result
) {
console
.
log
(result);
});
BX24
.
placement
.
call
(
'CallCardSetCardTitle'
, {
title
:
'hello world!'
},
function
(
result
) {
console
.
log
(result);
});
});
});
Continue Learning
Continue Learning
Get Information About the Call Context of BX24.placement.info
Get Information About the JS Interface of the Current Placement BX24.placement.getInterface
Set Up an Event Handler for the Interface BX24.placement.bindEvent
Copied
Was the article helpful?
Yes
No
Previous
Get List of Methods and Events
Next
Register Event Handler

---

## Set Up an Event Handler for the Interface BX24.placement.bindEvent

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/bx24-placement-bind-event

Set Up an Event Handler for the Interface BX24.placement.bindEvent | Bitrix24 REST API and Marketplace Applications
Parameters
Set Up an Event Handler for the Interface BX24.placement.bindEvent
Parameters
Code Example
Continue Learning
Scope:
placement
The method
BX24.placement.bindEvent
sets an event handler for the interface. The event must be registered on the calling side; otherwise, nothing will happen.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
event
*
string
The name of the event to which the handler subscribes
callback
*
callable
The callback function.
The
callback
handler may or may not receive data depending on the event it subscribes to.
Code Example
Code Example
How to Use Examples in Documentation
BX24
.
ready
(
function
(
) {
BX24
.
init
(
function
(
) {
BX24
.
placement
.
bindEvent
(
'BackgroundCallCard::initialized'
,
event
=>
{
// some code
});
BX24
.
placement
.
bindEvent
(
'CallCard::CallStateChanged'
,
(
callState
) =>
{
console
.
log
(callState);
});
});
});
Continue Learning
Continue Learning
Get Information About the Call Context of BX24.placement.info
Get Information About the JS Interface of the Current Placement BX24.placement.getInterface
Call the Registered Interface Command BX24.placement.call
Copied
Was the article helpful?
Yes
No
Previous
Call Widget Method
Next
Interaction with CRM Card

---

## Interaction with CRM Card

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/crm-card

Interaction with CRM Card | Bitrix24 REST API and Marketplace Applications
Continue Your Exploration
Interaction with CRM Card
We are still updating this page
Some data may be missing here — we will complete it soon.
In the CRM card, an additional command
reloadData
is available, which will refresh the CRM interface data. This command is solely for transmitting data to the CRM card; therefore, until the card is actually saved by the user, the values will not be stored in the database.
BX24
.
placement
.
call
(
'reloadData'
,
function
(
){
console
.
log
(
'reload call'
)});
The js interface is exclusively for sending data to the form. Until the form is saved by the user, the value will not be stored in the database.
Continue Your Exploration
Continue Your Exploration
Call the Registered Interface Command BX24.placement.call
Copied
Was the article helpful?
Yes
No
Previous
Register Event Handler
Next
Interaction with the Call Card

---

## Interaction with the CALL_CARD

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/call-card/index

Interaction with the CALL_CARD | Bitrix24 REST API and Marketplace Applications
Interaction with the CALL_CARD
Interaction with the CALL_CARD
Overview of Methods
Overview of Events
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
telephony
Who can execute methods and subscribe to events:
any user
The placement
CALL_CARD
is designed for working with the call card in the CRM:
The interface is returned by calling
BX24.placement.getInterface
.
Overview of Methods
Overview of Methods
Method
Description
getStatus
Returns information about the current call
disableAutoClose
Disables automatic closing of the card for 60 seconds after the call ends
enableAutoClose
Enables automatic closing of the card after the call ends
Overview of Events
Overview of Events
Event
Triggered
CallCard::EntityChanged
When the current client changes in dial mode
CallCard::BeforeClose
Before closing the call card
CallCard::CallStateChanged
When the state of the current call changes
Copied
Was the article helpful?
Yes
No
Previous
Interaction with CRM Card
Next
Get Call Status

---

## Get Call Status getStatus

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/call-card/get-status

Get Call Status getStatus | Bitrix24 REST API and Marketplace Applications
Get Call Status getStatus
Get Call Status getStatus
Code Examples
Response Handling
Returned Data
Continue Learning
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
telephony
Who can execute the method: any user
The method returns information about the current call.
No parameters.
Code Examples
Code Examples
How to Use Examples in Documentation
Calling the placement method. The result is returned in a callback.
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
'{"PLACEMENT":"getStatus","PARAMS":{}}'
\
"https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/placement.call"
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"PLACEMENT":"getStatus","PARAMS":{}}'
\
"https://**put_your_bitrix24_address**/rest/placement.call?auth=**put_access_token_here**"
BX24
.
placement
.
call
(
'getStatus'
, {},
function
(
result
) {
console
.
log
(result);
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
'placement.call'
,
[
'PLACEMENT'
=>
'getStatus'
,
'PARAMS'
=> (
object
)[]
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
Returned Data
Returned Data
Name
type
Description
CALL_ID
string
ID of the current call
PHONE_NUMBER
string
Client's phone number
CRM_ENTITY_TYPE
string
Type of the CRM entity associated with the call (
CONTACT
,
LEAD
,
COMPANY
)
CRM_ENTITY_ID
int
ID of the CRM entity associated with the call
CRM_ACTIVITY_ID
int
ID of the CRM activity related to the call
CALL_DIRECTION
string
Direction of the call (
incoming
,
outgoing
,
incomingTransfer
,
callback
)
CALL_LIST_MODE
bool
Indicator of operation in call list mode
CRM_BINDINGS
Array of bindings of the call to CRM entities
Continue Learning
Continue Learning
Disable Auto-Close disableAutoClose
Disable Auto-Close enableAutoClose
Event of Client Change CallCard::EntityChanged
Event Before Closing the CallCard CallCard::BeforeClose
Event of Call Status Change CallCard::CallStateChanged
Copied
Was the article helpful?
Yes
No
Previous
Interaction with the Call Card
Next
Disable Auto-Close

---

## Disable Auto-Close disableAutoClose

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/call-card/disable-auto-close

Disable Auto-Close disableAutoClose | Bitrix24 REST API and Marketplace Applications
Disable Auto-Close disableAutoClose
Disable Auto-Close disableAutoClose
Code Examples
Continue Learning
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
telephony
Who can execute the method: any user
This method disables the automatic closing of the card for 60 seconds after the call ends. It also blocks incoming calls until the card is closed.
No parameters.
Code Examples
Code Examples
How to Use Examples in Documentation
Calling the placement method. The result is returned in the callback.
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
'{"PLACEMENT":"disableAutoClose","PARAMS":{}}'
\
"https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/placement.call"
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"PLACEMENT":"disableAutoClose","PARAMS":{}}'
\
"https://**put_your_bitrix24_address**/rest/placement.call?auth=**put_access_token_here**"
BX24
.
placement
.
call
(
'disableAutoClose'
, {},
function
(
result
) {
console
.
log
(result);
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
'placement.call'
,
[
'PLACEMENT'
=>
'disableAutoClose'
,
'PARAMS'
=> (
object
)[]
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
Continue Learning
Continue Learning
Get Call Status getStatus
Disable Auto-Close enableAutoClose
Event of Client Change CallCard::EntityChanged
Event Before Closing the CallCard CallCard::BeforeClose
Event of Call Status Change CallCard::CallStateChanged
Copied
Was the article helpful?
Yes
No
Previous
Get Call Status
Next
Enable Auto-Close

---

## Disable Auto-Close enableAutoClose

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/call-card/enable-auto-close

Disable Auto-Close enableAutoClose | Bitrix24 REST API and Marketplace Applications
Disable Auto-Close enableAutoClose
Disable Auto-Close enableAutoClose
Code Examples
Continue Learning
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
telephony
Who can execute the method: any user
This method includes automatic closure of the card upon call completion. If the call has already ended, the call card will be closed.
No parameters.
Code Examples
Code Examples
How to Use Examples in Documentation
Calling the placement method. The result is returned in the callback.
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
'{"PLACEMENT":"enableAutoClose","PARAMS":{}}'
\
"https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/placement.call"
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"PLACEMENT":"enableAutoClose","PARAMS":{}}'
\
"https://**put_your_bitrix24_address**/rest/placement.call?auth=**put_access_token_here**"
BX24
.
placement
.
call
(
'enableAutoClose'
, {},
function
(
result
) {
console
.
log
(result);
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
'placement.call'
,
[
'PLACEMENT'
=>
'enableAutoClose'
,
'PARAMS'
=> (
object
)[]
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
Continue Learning
Continue Learning
Get Call Status getStatus
Disable Auto-Close disableAutoClose
Event of Client Change CallCard::EntityChanged
Event Before Closing the CallCard CallCard::BeforeClose
Event of Call Status Change CallCard::CallStateChanged
Copied
Was the article helpful?
Yes
No
Previous
Disable Auto-Close
Next
Client Change Event

---

## Event of Client Change CallCard::EntityChanged

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/call-card/call-card-entity-changed

Event of Client Change CallCard::EntityChanged | Bitrix24 REST API and Marketplace Applications
What the Handler Receives
Event of Client Change CallCard::EntityChanged
What the Handler Receives
Event Subscription
Continue Your Exploration
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
telephony
Who can subscribe:
any user
The
CallCard::EntityChanged
event occurs when the current client changes during a call review.
What the Handler Receives
What the Handler Receives
The event handler receives an object with the fields specified below.
Parameter
type
Description
PHONE_NUMBER
string
Client's phone number
CRM_ENTITY_TYPE
string
Type of the CRM entity associated with the call (
CONTACT
,
LEAD
,
COMPANY
)
CRM_ENTITY_ID
int
ID of the CRM entity associated with the call
Event Subscription
Event Subscription
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
'{"PLACEMENT":"CallCard::EntityChanged","HANDLER":"**your_handler_url_here**"}'
\
"https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/placement.bindEvent"
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"PLACEMENT":"CallCard::EntityChanged","HANDLER":"**your_handler_url_here**"}'
\
"https://**put_your_bitrix24_address**/rest/placement.bindEvent?auth=**put_access_token_here**"
BX24
.
placement
.
bindEvent
(
"CallCard::EntityChanged"
,
function
(
callState
) {
console
.
log
(callState);
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
'placement.bindEvent'
,
[
'PLACEMENT'
=>
'CallCard::EntityChanged'
,
'HANDLER'
=>
'**your_handler_url_here**'
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
Continue Your Exploration
Continue Your Exploration
Get Call Status getStatus
Disable Auto-Close disableAutoClose
Disable Auto-Close enableAutoClose
Event Before Closing the CallCard CallCard::BeforeClose
Event of Call Status Change CallCard::CallStateChanged
Copied
Was the article helpful?
Yes
No
Previous
Enable Auto-Close
Next
Before Closing Card Event

---

## Event Before Closing the CallCard CallCard::BeforeClose

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/call-card/call-card-before-close

Event Before Closing the CallCard CallCard::BeforeClose | Bitrix24 REST API and Marketplace Applications
Event Before Closing the CallCard CallCard::BeforeClose
Event Before Closing the CallCard CallCard::BeforeClose
Event Subscription
Continue Learning
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
telephony
Who can subscribe:
any user
The
CallCard::BeforeClose
event occurs before the call card is closed.
No parameters are passed to the handler.
Event Subscription
Event Subscription
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
'{"PLACEMENT":"CallCard::BeforeClose","HANDLER":"**your_handler_url_here**"}'
\
"https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/placement.bindEvent"
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"PLACEMENT":"CallCard::BeforeClose","HANDLER":"**your_handler_url_here**"}'
\
"https://**put_your_bitrix24_address**/rest/placement.bindEvent?auth=**put_access_token_here**"
BX24
.
placement
.
bindEvent
(
"CallCard::BeforeClose"
,
function
(
callState
) {
console
.
log
(callState);
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
'placement.bindEvent'
,
[
'PLACEMENT'
=>
'CallCard::BeforeClose'
,
'HANDLER'
=>
'**your_handler_url_here**'
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
Continue Learning
Continue Learning
Get Call Status getStatus
Disable Auto-Close disableAutoClose
Disable Auto-Close enableAutoClose
Event of Client Change CallCard::EntityChanged
Event of Call Status Change CallCard::CallStateChanged
Copied
Was the article helpful?
Yes
No
Previous
Client Change Event
Next
Call Status Change Event

---

## Event of Call Status Change CallCard::CallStateChanged

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/call-card/call-card-call-state-changed

Event of Call Status Change CallCard::CallStateChanged | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event of Call Status Change CallCard::CallStateChanged
What the handler receives
Parameter data[]
Event Subscription
Continue Learning
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
telephony
Who can subscribe:
any user
The event
CallCard::CallStateChanged
occurs when the status of the current call changes.
What the handler receives
What the handler receives
The specified arguments are passed to the handler.
Required parameters are marked with *
Parameter
type
Description
PHONE_NUMBER
*
callState
Current state of the call (
idle
,
connecting
,
connected
)
additionalParams
object
Object with additional fields
Parameter data[]
Parameter data[]
Parameter
type
Description
failedCode
string
Call completion code. Passed only in case of an unsuccessful call completion when transitioning to the
idle
state
Event Subscription
Event Subscription
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
'{"PLACEMENT":"CallCard::CallStateChanged","HANDLER":"**your_handler_url_here**"}'
\
"https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/placement.bindEvent"
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"PLACEMENT":"CallCard::CallStateChanged","HANDLER":"**your_handler_url_here**"}'
\
"https://**put_your_bitrix24_address**/rest/placement.bindEvent?auth=**put_access_token_here**"
BX24
.
placement
.
bindEvent
(
"CallCard::CallStateChanged"
,
function
(
callState
) {
console
.
log
(callState);
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
'placement.bindEvent'
,
[
'PLACEMENT'
=>
'CallCard::CallStateChanged'
,
'HANDLER'
=>
'**your_handler_url_here**'
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
Continue Learning
Continue Learning
Get Call Status getStatus
Disable Auto-Close disableAutoClose
Disable Auto-Close enableAutoClose
Event of Client Change CallCard::EntityChanged
Event Before Closing the CallCard CallCard::BeforeClose
Copied
Was the article helpful?
Yes
No
Previous
Before Closing Card Event
Next
WebRTC Integration Scenario

---

## WebRTC Integration Scenario

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/index

WebRTC Integration Scenario | Bitrix24 REST API and Marketplace Applications
Integration Registration
WebRTC Integration Scenario
Integration Registration
Usage Scenario
Integration Registration
Integration Registration
Registration of the integration for the "client" on each page.
There is a special integration area that is formed as an invisible frame on each Bitrix24 page. Registration is done as follows:
'placement.bind'
,
[
'PLACEMENT'
=>
'PAGE_BACKGROUND_WORKER'
,
'HANDLER'
=>
'http://example.com/placement/?ty=1'
,
'OPTIONS'
=> [
'errorHandlerUrl'
=>
'http://example.com/logg.php?ty=1'
,
],
'LANG_ALL'
=> [
'de'
=> [
'TITLE'
=>
'test'
,
]
]
]
An important distinction from a regular integration is the
Options[errorHandlerUrl]
parameter. This handler receives a signal that we are disabling the integration on a specific Bitrix24 account if the handler specified in Handler responds too slowly. Since the integration is formed on each page, it is crucial that the integration handler is called quickly (currently, we consider "not quickly" to be when the handler takes longer than 5 seconds three times). In case of a shutdown, the handler will need to be re-registered in this Bitrix24.
Usage Scenario
Usage Scenario
Working with telephony remains the same as before. Call registration is performed using the method
telephony.externalcall.register
. This same method "raises" the call card. Obviously, this should occur if the WebRTC client in the integration described above has started processing the call.
Furthermore, the integration can interact with the open call card, managing buttons and button press events. For working with the call card through the
PAGE_BACKGROUND_WORKER
placement, 9 methods have been added to retrieve and modify card data, along with 17 events to handle user activity.
The key event is
BackgroundCallCard::initialized
. It is triggered upon the creation of the call card, after which it becomes possible to manage this card. Therefore, it is strongly recommended that all method calls from the application side be made specifically in the event handler function for this event.
Copied
Was the article helpful?
Yes
No
Previous
Call Status Change Event
Next
Call Card

---

## Call Card

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/card

Call Card | Bitrix24 REST API and Marketplace Applications
General Description
Call Card
General Description
Card States
To manage the call card, it is advisable to familiarize yourself with the
scenarios
.
General Description
General Description
To change the title of the card (area 1), you need to call the method
CallCardSetCardTitle
and pass an object with the
title
property.
BX24
.
placement
.
call
(
'CallCardSetCardTitle'
, {
title
:
'Card Title'
},
() =>
{
//some code });
To change the text in area 2, you need to call the method
CallCardSetStatusText
and pass an object with the
statusText
property.
BX24
.
placement
.
call
(
'CallCardSetStatusText'
, {
statusText
:
'Status Text'
},
() =>
{
//some code });
The call card has a total of 12 interface states. You can retrieve them by calling the method
CallCardGetListUiStates
. An array of available call card states will be passed to the callback function.
BX24
.
placement
.
call
(
'CallCardGetListUiStates'
,
(
data
) =>
{
console
.
log
(data); });
To switch to another state of the card, call the method
CallCardSetUiState
and pass an object with the
uiState
property.
BX24
.
placement
.
call
(
'CallCardSetUiState'
, {
uiState
:
'connected'
},
() =>
{
//some code });
To handle button presses by the operator in the call card, you need to subscribe to the corresponding events.
Card States
Card States
State
Description
Handles Button Presses
[incoming](*incoming)
For accepting incoming calls
Answer -
BackgroundCallCard::answerButtonClick
Skip -
BackgroundCallCard::skipButtonClick
[transferIncoming](*transferIncoming)
For accepting a redirected incoming call
Answer -
BackgroundCallCard::answerButtonClick
Skip -
BackgroundCallCard::skipButtonClick
[outgoing](*outgoing)
For displaying the outgoing call card
Call -
BackgroundCallCard::makeCallButtonClick
[connectingIncoming](*connectingIncoming)
For displaying the card while connecting to an incoming call
Hang up -
BackgroundCallCard::hangupButtonClick
[connectingOutgoing](*connectingOutgoing)
For displaying the card while connecting to an outgoing call
Hang up -
BackgroundCallCard::hangupButtonClick
[connected](*connected)
For displaying after connecting to the call
Hang up -
BackgroundCallCard::hangupButtonClick
Put on hold -
BackgroundCallCard::holdButtonClick
Mute -
BackgroundCallCard::muteButtonClick
Transfer to another operator -
BackgroundCallCard::transferButtonClick
Pressing the dial pad buttons -
BackgroundCallCard::dialpadButtonClick
Rate call quality -
BackgroundCallCard::qualityMeterClick
[transferring](*transferring)
For confirming the transfer of the call to another operator
Transfer -
BackgroundCallCard::completeTransferButtonClick
Return to the call -
BackgroundCallCard::cancelTransferButtonClick
[transferFailed](*transferFailed)
If the call transfer failed
Return to the call -
BackgroundCallCard::cancelTransferButtonClick
[transferConnected](*transferConnected)
If the transfer was successful and you need to exit the call card
Hang up -
BackgroundCallCard::hangupButtonClick
[error](*error)
If an error occurred
Close -
BackgroundCallCard::closeButtonClick
[moneyError](*moneyError)
If the account has run out of funds and the administrator of the account needs to be informed
Notify administrator -
BackgroundCallCard::notifyAdminButtonClick
Close -
BackgroundCallCard::closeButtonClick
[redial](*redial)
If the subscriber is busy, allow the operator to call this number again without hiding the call card
Call again -
BackgroundCallCard::makeCallButtonClick
Timer in the Call Card
By default, when transitioning to the
connected
state, the call timer automatically starts. This behavior can be disabled by passing in addition to
uiState: 'connected'
the property
disableAutoStartTimer
with the value
true
. When transitioning to other states, the timer will stop.
Copied
Was the article helpful?
Yes
No
Previous
WebRTC Integration Scenario
Next
Mute the Operator's Microphone from the Application

---

## Disable Operator Microphone from the CallCardSetMute Application

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/call-card-set-mute

Disable Operator Microphone from the CallCardSetMute Application | Bitrix24 REST API and Marketplace Applications
Disable Operator Microphone from the CallCardSetMute Application
Disable Operator Microphone from the CallCardSetMute Application
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
telephony
Who can execute the method: any user
The
CallCardSetMute
method allows the application to disable the operator's microphone.
The application must pass an object to the method with the property muted, which contains a boolean value: true - the microphone should be off, false - on. No data is passed to the callback function.
Example
Example
BX24
.
placement
.
bindEvent
(
'BackgroundCallCard::initialized'
,
event
=>
{
BX24
.
placement
.
call
(
'CallCardSetMute'
, {
muted
:
true
},
() =>
{
// some code
});
});
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Call Card
Next
Put the Call on Hold from the Application

---

## Set a Call on Hold from the CallCardSetHold Application

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/call-card-set-hold

Set a Call on Hold from the CallCardSetHold Application | Bitrix24 REST API and Marketplace Applications
Set a Call on Hold from the CallCardSetHold Application
Set a Call on Hold from the CallCardSetHold Application
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
telephony
Who can execute the method: any user
The
CallCardSetHold
method allows the application to place a call on hold.
The application must pass an object with the property held to the method, which contains a boolean value: true - to enable hold, false - to disable hold. No data is passed to the callback function.
Example
Example
BX24
.
placement
.
bindEvent
(
'BackgroundCallCard::initialized'
,
event
=>
{
BX24
.
placement
.
call
(
'CallCardSetHold'
, {
held
:
true
},
() =>
{
// some code
});
});
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Mute the Operator's Microphone from the Application
Next
Change the Call Card Interface State from the Application

---

## Change the state of the call card interface from the CallCardSetUiState application

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/call-card-set-ui-state

Change the state of the call card interface from the CallCardSetUiState application | Bitrix24 REST API and Marketplace Applications
Change the state of the call card interface from the CallCardSetUiState application
Change the state of the call card interface from the CallCardSetUiState application
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
telephony
Who can execute the method: any user
The
CallCardSetUiState
method allows the application to change the state of the call card interface.
The application must pass an object with the property uiState to the method, where the value should be one of those obtained from the getListUiStates method. No data is passed to the callback function.
Example
Example
BX24
.
placement
.
bindEvent
(
'BackgroundCallCard::initialized'
,
event
=>
{
BX24
.
placement
.
call
(
'CallCardSetUiState'
, {
uiState
:
'connected'
},
() =>
{
// some code
})
});
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Put the Call on Hold from the Application
Next
Get a List of Available Call Card Interface States

---

## Get a List of Available Call Card UI States CallCardGetListUiStates

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/call-card-get-list-ui-states

Get a List of Available Call Card UI States CallCardGetListUiStates | Bitrix24 REST API and Marketplace Applications
Get a List of Available Call Card UI States CallCardGetListUiStates
Get a List of Available Call Card UI States CallCardGetListUiStates
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can execute the method: any user
The
CallCardGetListUiStates
method allows you to retrieve a list of available call card UI states.
When called, an object containing all possible call card UI states is passed to the callback function.
Example
Example
BX24
.
placement
.
bindEvent
(
'BackgroundCallCard::initialized'
,
event
=>
{
BX24
.
placement
.
call
(
'CallCardGetListUiStates'
,
data
=>
{
// some code
})
});
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Change the Call Card Interface State from the Application
Next
Change the Call Card Title from the Application

---

## Change the title of the call card from the CallCardSetCardTitle application

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/call-card-set-card-title

Change the title of the call card from the CallCardSetCardTitle application | Bitrix24 REST API and Marketplace Applications
Change the title of the call card from the CallCardSetCardTitle application
Change the title of the call card from the CallCardSetCardTitle application
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can execute the method: any user
The
CallCardSetCardTitle
method allows you to change the title of the call card from the application.
When called, you need to pass an object with the property title. Nothing is passed to the callback function.
Example
Example
BX24
.
placement
.
bindEvent
(
'BackgroundCallCard::initialized'
,
event
=>
{
BX24
.
placement
.
call
(
'CallCardSetCardTitle'
, {
title
:
'hello world!'
},
() =>
{
// some code
})
});
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Available Call Card Interface States
Next
Change the Text in the Center of the Call Card from the Application

---

## Change Text in the Center of the Call Card from the Application CallCardSetStatusText

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/call-card-set-status-text

Change Text in the Center of the Call Card from the Application CallCardSetStatusText | Bitrix24 REST API and Marketplace Applications
Change Text in the Center of the Call Card from the Application CallCardSetStatusText
Change Text in the Center of the Call Card from the Application CallCardSetStatusText
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can execute the method: any user
The
CallCardSetStatusText
method allows the application to change the text in the center of the call card.
When called, it requires an object with the property statusText. Nothing is passed to the callback function.
Example
Example
BX24
.
placement
.
bindEvent
(
'BackgroundCallCard::initialized'
,
event
=>
{
BX24
.
placement
.
call
(
'CallCardSetStatusText'
, {
statusText
:
'hello world!'
},
() =>
{
// some code
})
});
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Change the Call Card Title from the Application
Next
Close the Call Card from the Application

---

## Close the call card from the CallCardClose application

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/call-card-close

Close the call card from the CallCardClose application | Bitrix24 REST API and Marketplace Applications
Close the call card from the CallCardClose application
Close the call card from the CallCardClose application
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
telephony
Who can execute the method: any user
The
CallCardClose
method allows the application to close the call card.
Warning
Attention! After calling this method, the call card will be closed, and no further operations can be performed on it.
Example
Example
BX24
.
placement
.
bindEvent
(
'BackgroundCallCard::initialized'
,
event
=>
{
BX24
.
placement
.
call
(
'CallCardClose'
, {},
() =>
{
// some code
})
});
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Change the Text in the Center of the Call Card from the Application
Next
Overview of Events

---

## Event Overview

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/index

Event Overview | Bitrix24 REST API and Marketplace Applications
Event Overview
Event Overview
BackgroundCallCard::addCommentButtonClick
When saving a comment in the call card
BackgroundCallCard::answerButtonClick
When clicking the "answer" button
BackgroundCallCard::cancelTransferButtonClick
When clicking the "return to call" button
BackgroundCallCard::closeButtonClick
When clicking the call end button
BackgroundCallCard::completeTransferButtonClick
When clicking the "redirect" button
BackgroundCallCard::dialpadButtonClick
When pressing one of the numeric buttons on the phone
BackgroundCallCard::entityChanged
In the call card when changing the current caller
BackgroundCallCard::hangupButtonClick
When clicking the "hang up" button
BackgroundCallCard::holdButtonClick
When clicking the hold call button
BackgroundCallCard::initialized
After creating the call card
BackgroundCallCard::makeCallButtonClick
When clicking the "call back" button
BackgroundCallCard::muteButtonClick
When clicking the microphone mute button
BackgroundCallCard::nextButtonClick
When clicking the "next" button
BackgroundCallCard::notifyAdminButtonClick
When clicking the "notify administrator" button
BackgroundCallCard::qualityMeterClick
When rating the call quality
BackgroundCallCard::skipButtonClick
When clicking the "skip" button
BackgroundCallCard::transferButtonClick
When selecting the operator to whom the current operator wants to transfer the call
Was the article helpful?
Yes
No
Previous
Close the Call Card from the Application
Next
After creating the call card

---

## After Creating the Call Card BackgroundCallCard::initialized

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/initialized

After Creating the Call Card BackgroundCallCard::initialized | Bitrix24 REST API and Marketplace Applications
After Creating the Call Card BackgroundCallCard::initialized
After Creating the Call Card BackgroundCallCard::initialized
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::initialized
occurs after the call card is created. The callback function will receive the phone number.
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When saving a comment in the call card

---

## When saving a comment in the call card BackgroundCallCard::addCommentButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/add-comment-button-click

When saving a comment in the call card BackgroundCallCard::addCommentButtonClick | Bitrix24 REST API and Marketplace Applications
When saving a comment in the call card BackgroundCallCard::addCommentButtonClick
When saving a comment in the call card BackgroundCallCard::addCommentButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::addCommentButtonClick
occurs when a comment is saved in the call card. The text of the comment is passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
After creating the call card
Next
When pressing the mute button

---

## On Clicking the Mute Button BackgroundCallCard::muteButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/mute-button-click

On Clicking the Mute Button BackgroundCallCard::muteButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the Mute Button BackgroundCallCard::muteButtonClick
On Clicking the Mute Button BackgroundCallCard::muteButtonClick
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::muteButtonClick
occurs when the mute button is clicked. A boolean value is passed to the callback function: true - mute is expected, false - unmute is expected.
Copied
Was the article helpful?
Yes
No
Previous
When saving a comment in the call card
Next
When pressing the hold call button

---

## On Clicking the Hold Call Button BackgroundCallCard::holdButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/hold-button-click

On Clicking the Hold Call Button BackgroundCallCard::holdButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the Hold Call Button BackgroundCallCard::holdButtonClick
On Clicking the Hold Call Button BackgroundCallCard::holdButtonClick
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::holdButtonClick
occurs when the hold call button is clicked. A boolean value is passed to the callback function: true - hold is expected to be activated, false - hold is expected to be deactivated.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the mute button
Next
When pressing the end call button

---

## On Clicking the Call End Button BackgroundCallCard::closeButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/close-button-click

On Clicking the Call End Button BackgroundCallCard::closeButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the Call End Button BackgroundCallCard::closeButtonClick
On Clicking the Call End Button BackgroundCallCard::closeButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::closeButtonClick
occurs when the call end button is clicked. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the hold call button
Next
When selecting the operator to whom the current operator wants to transfer the call

---

## When selecting an operator to whom the current operator wants to transfer the call BackgroundCallCard::transferButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/transfer-button-click

When selecting an operator to whom the current operator wants to transfer the call BackgroundCallCard::transferButtonClick | Bitrix24 REST API and Marketplace Applications
When selecting an operator to whom the current operator wants to transfer the call BackgroundCallCard::transferButtonClick
When selecting an operator to whom the current operator wants to transfer the call BackgroundCallCard::transferButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::transferButtonClick
occurs when selecting an operator to whom the current operator wants to transfer the call. The callback function receives an object with the properties
phoneNumber
— the number of the current call and
target
— the identifier of the Bitrix24 user.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the end call button
Next
When pressing the "return to call" button

---

## On Clicking the "Return to Call" Button BackgroundCallCard::cancelTransferButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/cancel-transfer-button-click

On Clicking the "Return to Call" Button BackgroundCallCard::cancelTransferButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the "Return to Call" Button BackgroundCallCard::cancelTransferButtonClick
On Clicking the "Return to Call" Button BackgroundCallCard::cancelTransferButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::cancelTransferButtonClick
refers to clicking the "Return to Call" button. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When selecting the operator to whom the current operator wants to transfer the call
Next
When pressing the "redirect" button

---

## On clicking the "redirect" button BackgroundCallCard::completeTransferButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/complete-transfer-button-click

On clicking the "redirect" button BackgroundCallCard::completeTransferButtonClick | Bitrix24 REST API and Marketplace Applications
On clicking the "redirect" button BackgroundCallCard::completeTransferButtonClick
On clicking the "redirect" button BackgroundCallCard::completeTransferButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::completeTransferButtonClick
refers to clicking the "redirect" button. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the "return to call" button
Next
When pressing the "hang up" button

---

## On Clicking the "End" Button BackgroundCallCard::hangupButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/hang-up-button-click

On Clicking the "End" Button BackgroundCallCard::hangupButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the "End" Button BackgroundCallCard::hangupButtonClick
On Clicking the "End" Button BackgroundCallCard::hangupButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::hangupButtonClick
refers to clicking the "End" button. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the "redirect" button
Next
When pressing the "next" button

---

## On Clicking the "Next" Button BackgroundCallCard::nextButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/next-button-click

On Clicking the "Next" Button BackgroundCallCard::nextButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the "Next" Button BackgroundCallCard::nextButtonClick
On Clicking the "Next" Button BackgroundCallCard::nextButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::nextButtonClick
occurs when the "Next" button is clicked. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the "hang up" button
Next
When pressing the "skip" button

---

## On Clicking the "Skip" Button BackgroundCallCard::skipButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/skip-button-click

On Clicking the "Skip" Button BackgroundCallCard::skipButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the "Skip" Button BackgroundCallCard::skipButtonClick
On Clicking the "Skip" Button BackgroundCallCard::skipButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::skipButtonClick
refers to clicking the "skip" button. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the "next" button
Next
When pressing the "answer" button

---

## On Clicking the "Reply" Button BackgroundCallCard::answerButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/answer-button-click

On Clicking the "Reply" Button BackgroundCallCard::answerButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the "Reply" Button BackgroundCallCard::answerButtonClick
On Clicking the "Reply" Button BackgroundCallCard::answerButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::answerButtonClick
refers to clicking the "reply" button. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the "skip" button
Next
In the call list when changing the current caller

---

## In the Call Review Card when changing the current entity BackgroundCallCard::entityChanged

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/entity-changed

In the Call Review Card when changing the current entity BackgroundCallCard::entityChanged | Bitrix24 REST API and Marketplace Applications
In the Call Review Card when changing the current entity BackgroundCallCard::entityChanged
In the Call Review Card when changing the current entity BackgroundCallCard::entityChanged
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::entityChanged
occurs in the call review card when changing the current entity. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the "answer" button
Next
When pressing the "call back" button

---

## On Clicking the "Call Back" Button BackgroundCallCard::makeCallButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/make-call-button-click

On Clicking the "Call Back" Button BackgroundCallCard::makeCallButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the "Call Back" Button BackgroundCallCard::makeCallButtonClick
On Clicking the "Call Back" Button BackgroundCallCard::makeCallButtonClick
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::makeCallButtonClick
refers to clicking the "Call Back" button. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
In the call list when changing the current caller
Next
When assessing the call quality

---

## When Evaluating Call Quality BackgroundCallCard::qualityMeterClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/quality-meter-click

When Evaluating Call Quality BackgroundCallCard::qualityMeterClick | Bitrix24 REST API and Marketplace Applications
When Evaluating Call Quality BackgroundCallCard::qualityMeterClick
When Evaluating Call Quality BackgroundCallCard::qualityMeterClick
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::qualityMeterClick
occurs when evaluating call quality. An integer value from 1 to 5 is passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the "call back" button
Next
When pressing one of the phone's digit buttons

---

## On pressing one of the numeric buttons on the phone BackgroundCallCard::dialpadButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/dialpad-button-click

On pressing one of the numeric buttons on the phone BackgroundCallCard::dialpadButtonClick | Bitrix24 REST API and Marketplace Applications
On pressing one of the numeric buttons on the phone BackgroundCallCard::dialpadButtonClick
On pressing one of the numeric buttons on the phone BackgroundCallCard::dialpadButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::dialpadButtonClick
occurs when one of the numeric buttons on the phone is pressed. The pressed character is passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When assessing the call quality
Next
When pressing the "notify admin" button

---

## On Clicking the "Notify Administrator" Button BackgroundCallCard::notifyAdminButtonClick

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-interaction/page-background-worker/events/notify-admin-button-click

On Clicking the "Notify Administrator" Button BackgroundCallCard::notifyAdminButtonClick | Bitrix24 REST API and Marketplace Applications
On Clicking the "Notify Administrator" Button BackgroundCallCard::notifyAdminButtonClick
On Clicking the "Notify Administrator" Button BackgroundCallCard::notifyAdminButtonClick
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
telephony
Who can subscribe:
any user
The event
BackgroundCallCard::notifyAdminButtonClick
refers to clicking the "Notify Administrator" button. No parameters are passed to the callback function.
Copied
Was the article helpful?
Yes
No
Previous
When pressing one of the phone's digit buttons
Next
Overview of Methods

---

