---
description: BX24 JavaScript SDK reference and usage
methods:
- crm.item.add
- event.bind
- event.unbind
- user.current
- user.get
pages: 20
title: BX24 JavaScript SDK reference and usage
---
# BX24 JavaScript SDK reference and usage
> BX24 JavaScript SDK reference and usage
> **20 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [SDK for Bitrix24 Development](#sdk-for-bitrix24-development)
- [Installation and Usage of B24JsSDK](#installation-and-usage-of-b24jssdk)
- [Connecting and Using BX24.js](#connecting-and-using-bx24js)
- [Calling REST Methods](#calling-rest-methods)
- [Call the REST service method with specified parameters BX24.callMethod](#call-the-rest-service-method-with-specified-parame)
- [Send a batch of requests with BX24.callBatch](#send-a-batch-of-requests-with-bx24callbatch)
- [Call the interface to register a new event handler callBind](#call-the-interface-to-register-a-new-event-handler)
- [Call the interface to remove a registered event handler BX24.callUnbind](#call-the-interface-to-remove-a-registered-event-ha)
- [Overview of System Functions](#overview-of-system-functions)
- [Initialize the BX24.init Library](#initialize-the-bx24init-library)
- [Handle the first launch event of the application by the user BX24.install](#handle-the-first-launch-event-of-the-application-b)
- [Notify about the completion of the installer BX24.installFinish](#notify-about-the-completion-of-the-installer-bx24i)
- [Get Data for OAuth 2.0 BX24.getAuth](#get-data-for-oauth-20-bx24getauth)
- [Force Update Authorization Key BX24.refreshAuth](#force-update-authorization-key-bx24refreshauth)
- [Overview of Methods](#overview-of-methods)
- [Set Settings for User BX24.userOption.set](#set-settings-for-user-bx24useroptionset)
- [Get User Settings BX24.userOption.get](#get-user-settings-bx24useroptionget)
- [Set Settings for the Application BX24.appOption.set](#set-settings-for-the-application-bx24appoptionset)
- [Get Application Settings BX24.appOption.get](#get-application-settings-bx24appoptionget)
- [MCP Server for Working with Bitrix24 REST API](#mcp-server-for-working-with-bitrix24-rest-api)

---

## SDK for Bitrix24 Development

**Source:** https://apidocs.bitrix24.com/sdk/index

SDK for Bitrix24 Development | Bitrix24 REST API and Marketplace Applications
JavaScript SDK
SDK for Bitrix24 Development
JavaScript SDK
PHP SDK
Additional Tools
The Bitrix24 SDK consists of ready-made libraries for the REST API. They accelerate integration and simplify the creation of applications for Bitrix24.
JavaScript SDK
JavaScript SDK
B24JsSDK
is a universal JavaScript library for browsers and Node.js. It supports modern language features such as async/await and automatic data type conversion.
Use B24JsSDK:
if you need to develop an external web application or a backend service on Node.js,
if support for batch requests
batch
, typical Bitrix24 objects, and logging is required,
if flexible authorization through
OAuth
or
webhooks
is necessary.
BX24.js
is a classic SDK for applications embedded within the Bitrix24 interface. Authorization is available only through the
OAuth protocol
.
Use BX24.js:
if the application operates within the Bitrix24 interface,
if quick access to the REST API with ready-made authorization through
OAuth
is needed,
if built-in UI tools are required.
PHP SDK
PHP SDK
B24PhpSDK
is a full-fledged PHP client with strict typing, autocompletion, and support for generators for efficient handling of large data sets. Authorization is available through
webhooks
and the
OAuth protocol
.
Use B24PhpSDK:
if you need to create a complex mass-market application for a marketplace,
if IDE autocompletion, strict typing, and events for token handling are required,
if efficient handling of large data sets through PHP generators is important.
CRest PHP SDK
is a simple starter kit in PHP. It comes with a ready-made
CRest
class.
Use CRest PHP SDK:
if you need to quickly test the API or create a simple integration,
if you plan to develop a local application for internal needs,
if minimal configuration for working with
webhooks
or
OAuth
is required.
Additional Tools
Additional Tools
MCP
is an auxiliary service for AI assistants in the development environment. MCP provides AI assistants with structured data and specifications for REST API methods, helps generate correct code, and speeds up application creation.
UI Kit
is a set of Vue components for creating interfaces in the Bitrix24 brand style. It ensures consistency in visual language and accelerates frontend development.
Copied
Was the article helpful?
Yes
No
Previous
How to Fix the "Site Does Not Allow Connection" Error When Opening the Application
Next
Installation and Usage

---

## Installation and Usage of B24JsSDK

**Source:** https://apidocs.bitrix24.com/sdk/b24jssdk/index

Installation and Usage of B24JsSDK | Bitrix24 REST API and Marketplace Applications
Installation and Usage of B24JsSDK
Installation and Usage of B24JsSDK
Installation
Installation in Node.js / Nuxt
Usage in the Browser
Usage with Webhooks
Usage in Frontend Applications
Examples
B24JsSDK
is the official library for working with the Bitrix24 REST API in JavaScript. Unlike
BX24.JS
, B24JsSDK offers the following advantages:
Works both on the frontend in the browser and on the backend in Node.js;
Supports authorization via tokens and webhooks;
Formats REST API data into corresponding JavaScript types (numbers, IBAN accounts, dates, etc.);
Utilizes modern language features - async/await, promises, AsyncGenerator;
Automatically generates unique request identifiers, simplifying debugging;
And much more!
Installation
Installation
There are several ways to install the SDK:
For generating and server-side rendering applications on Node.js and Nuxt;
For using the UMD version of the SDK in the browser via CDN or from a local server.
Installation in Node.js / Nuxt
Installation in Node.js / Nuxt
Details can be found in the
B24JsSDK documentation
.
Usage in the Browser
Usage in the Browser
Include the library via CDN by adding the following tag to your HTML file:
<
script
src
=
"https://unpkg.com/@bitrix24/b24jssdk@latest/dist/umd/index.min.js"
>
</
script
>
Or download the UMD version from
unpkg.com
and add it to your project:
<
script
src
=
"/path/to/umd/index.min.js"
>
</
script
>
After including, the library will be available through the global variable
B24Js
. Here’s an example of initialization:
<!DOCTYPE
html
>
<
html
lang
=
"en"
>
<
head
>
<
meta
charset
=
"UTF-8"
>
<
meta
name
=
"viewport"
content
=
"width=device-width, initial-scale=1.0"
>
<
title
>
Bitrix24 Frame Demo
</
title
>
</
head
>
<
body
>
<
p
>
See the result in the developer console
</
p
>
<
script
src
=
"https://unpkg.com/@bitrix24/b24jssdk@latest/dist/umd/index.min.js"
>
</
script
>
<
script
>
document
.
addEventListener
(
'DOMContentLoaded'
,
async
() => {
try
{
let
$b24 =
await
B24Js.
initializeB24Frame
();
}
catch
(error)
{
console
.
error
(error);
}
});
</
script
>
</
body
>
</
html
>
Usage with Webhooks
Usage with Webhooks
For working with local webhooks, use them only in
server applications
.
Example of server usage of the SDK:
https://github.com/bitrix24/b24sdk-examples/tree/main/js/05-node-hook
Usage in Frontend Applications
Usage in Frontend Applications
<
script
src
=
"https://unpkg.com/@bitrix24/b24jssdk@latest/dist/umd/index.min.js"
>
</
script
>
<
script
type
=
"module"
>
try
{
const
$logger = B24Js.
LoggerBrowser
.
build
(
'local-app'
,
true
);
const
$b24 =
await
B24Js.
initializeB24Frame
();
$b24.
setLogger
(
B24Js.
LoggerBrowser
.
build
(
'Core'
)
);
$logger.
warn
(
'B24Frame.init'
);
const
response =
await
$b24.
callMethod
(
'crm.item.add'
,
{
entityTypeId
: B24Js.
EnumCrmEntityTypeId
.
deal
,
fields
: {
title
:
`New Deal
${B24Js.Text.getUuidRfc4122()}
`
,
typeId
:
'SALE'
,
stageId
:
'NEW'
}
}
);
const
newDeal = response.
getData
().
result
.
item
;
$logger.
info
(
`
${B24Js.Text.getDateForLog()}
crm.item.add >>`
,
{
newId
: newDeal.
id
,
createdTime
: B24Js.
Text
.
toDateTime
(newDeal.
createdTime
).
toFormat
(
'HH:mm:ss'
),
fields
: newDeal
}
);
// Open the added deal in the standard slider
$b24.
slider
.
openPath
(
$b24.
slider
.
getUrl
(
`/crm/deal/details/
${newDeal.id}
/`
),
950
);
}
catch
( error )
{
console
.
error
(error);
}
</
script
>
Examples
Examples
Examples of using the SDK can be found in the repository:
https://github.com/bitrix24/b24sdk-examples/tree/main/js
:
Creating a user interface in the style of Bitrix24;
Using webhooks;
Authorization via tokens;
Using the UMD version in the browser;
Using the SDK on the backend in Node.js.
Copied
Was the article helpful?
Yes
No
Previous
Overview of Tools
Next
Connection and Usage

---

## Connecting and Using BX24.js

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/index

Connecting and Using BX24.js | Bitrix24 REST API and Marketplace Applications
Connecting and Using BX24.js
Connecting and Using BX24.js
If your application implements a user interface within Bitrix24 (displayed on a special page or using embedding tools), you can take advantage of the capabilities of a special JS library. It:
first, serves as a JS SDK for REST, allowing you to access REST directly from the front-end of your application without delving into
authorization implementation
via OAuth 2.0,
second, offers a range of additional features for interacting your application's user interface with the Bitrix24 interface:
frame size management,
calling standard dialogs,
etc.
The library is connected as follows:
<script src=
"//api.bitrix24.com/api/v1/"
></script>
The library cannot be used for external applications and webhooks.
Was the article helpful?
Yes
No
Previous
Installation and Usage
Next
Calling REST Methods

---

## Calling REST Methods

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/how-to-call-rest-methods/index

Calling REST Methods | Bitrix24 REST API and Marketplace Applications
Calling REST Methods
Calling REST Methods
Calling a
REST
method is a cross-domain request to the current Bitrix24 REST service on behalf of the current user. The authorization of the request is performed automatically based on the OAuth 2.0 protocol.
Sending a request
Processing the request result
Batch execution of requests
Was the article helpful?
Yes
No
Previous
Connection and Usage
Next
Call Method

---

## Call the REST service method with specified parameters BX24.callMethod

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/how-to-call-rest-methods/bx24-call-method

Call the REST service method with specified parameters BX24.callMethod | Bitrix24 REST API and Marketplace Applications
Sending a request
Call the REST service method with specified parameters BX24.callMethod
Sending a request
Parameters
Example
Handling the request result
Example of retrieving a paginated list of users
Continue your exploration
Sending a request
Sending a request
void
BX24
.
callMethod
(
String
method,
Object
params[,
Function
callback
]
);
The method
BX24.callMethod
invokes the specified REST service method with the given parameters. The parameters of the method are represented by the
params
object, which is an associative array converted into a POST request string. The values of the array elements can be strings or references to DOM elements of form fields (see file uploads below).
If called before
BX24.init
, the request execution will be delayed.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
method
*
string
The name of the REST API method to be called
params
object
Parameters passed to the method. Must match the expected parameters of the called method
callback
function
The callback function that will be executed after receiving a response from the server
Example
Example
BX24
.
init
(
() =>
{
BX24
.
callMethod
(
'user.get'
, {
ID
:
10
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
if
(result.
data
())
{
const
user = result.
data
()[
0
];
if
(user)
{
alert
(
'User №'
+ user.
ID
+
' is named '
+ user.
NAME
);
}
}
});
});
How to Use Examples in Documentation
Warning
In on-premise versions, REST methods are called using the method
BX.rest.callMethod()
, not
BX24.callMethod()
.
Handling the request result
Handling the request result
The result handler of the request is a function. It receives an
ajaxResult
object, which provides the following methods:
data()
— returns the response data of the method. The type of returned data can be an array, object, or scalar value, depending on the specific API method
error()
— returns an error object if an error is present, and
undefined
otherwise. The error object contains the fields
status
and
ex
, where
ex
includes
error
and
error_description
more()
— returns
true
if there is more data to load, and
false
otherwise. Applicable if the method returns a list of data
total()
— returns the total number of available records. Applicable if the method returns a list of data
time()
— returns an object with information about the request execution time. It may return
undefined
if the information is unavailable.
next(cb: Function)
— requests the next page of data. If a function
cb
is provided, it will be used as the result handler for the next request. Returns
false
if there is no more data to load, or an
XMLHttpRequest
object if the request was initiated.
Example of retrieving a paginated list of users
Example of retrieving a paginated list of users
BX24
.
init
(
() =>
{
BX24
.
callMethod
(
'user.get'
, {
sort
:
'ID'
,
order
:
'ASC'
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
alert
(
'Request error: '
+ result.
error
());
}
else
{
console
.
log
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
});
});
How to Use Examples in Documentation
Continue your exploration
Continue your exploration
Call the interface to register a new event handler callBind
Call the interface to remove a registered event handler BX24.callUnbind
Send a batch of requests with BX24.callBatch
Copied
Was the article helpful?
Yes
No
Previous
Calling REST Methods
Next
Send Batch of Requests

---

## Send a batch of requests with BX24.callBatch

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/how-to-call-rest-methods/bx24-call-batch

Send a batch of requests with BX24.callBatch | Bitrix24 REST API and Marketplace Applications
Send a batch of requests with BX24.callBatch
Send a batch of requests with BX24.callBatch
Parameters
Example
Continue Learning
In some cases, there is a need to send multiple requests in succession. For example, when creating necessary entities during the application installation process. To optimize the process, batch execution of requests can be used.
void
BX24
.
callBatch
(
Object
|
Array
calls,
[
Function
callback[,
Boolean
bHaltOnError =
false
]]
);
The function
BX24.callBatch
sends a batch of requests to the REST service. If called before
BX24.init
, the request execution will be delayed.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
calls
*
object
|
array
A regular or associative array (object) with requests. Each request is either an array
[method_name, method_parameters]
or an object
{method: method_name, params: method_parameters}
.
In the method parameters, macros can be used to access the results of previous requests in the current batch. A macro can be constructed like this:
$result[request_identifier][response_field]
, where the request identifier is its key in the request batch array
callback
function
A handler function for the batch request result. It will receive an array or associative array (object) of
ajaxResult
objects with keys corresponding to the keys from the request batch
bHaltOnError
boolean
Flag "halt execution of the batch in case of an error". Default is
false
(do not halt)
Example
Example
BX24
.
init
(
() =>
{
const
prepareMessage
= (
name, lastName, departmentNumber
) => {
return
`The current user
${name}
${lastName}
is assigned to the departmen
${departmentNumber >
1
?
'ts '
:
't '
}
`
;
};
BX24
.
callBatch
({
get_user
: [
'user.current'
, {}],
get_department
: {
method
:
'department.get'
,
params
: {
ID
:
'$result[get_user][UF_DEPARTMENT]'
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
get_user
.
error
() || result.
get_department
.
error
())
{
if
(result.
get_user
.
error
())
{
console
.
error
(result.
get_user
.
error
());
}
if
(result.
get_department
.
error
())
{
console
.
error
(result.
get_department
.
error
());
}
}
else
{
const
departmentNumber = result.
get_department
.
data
().
length
;
let
message =
prepareMessage
(result.
get_user
.
data
().
NAME
, result.
get_user
.
data
().
LAST_NAME
, departmentNumber);
for
(
let
i =
0
; i < departmentNumber; i++)
{
message += i ===
0
?
''
:
', '
;
message += result.
get_department
.
data
()[i].
NAME
;
}
alert
(message);
}
},
true
);
});
How to Use Examples in Documentation
Continue Learning
Continue Learning
Call the interface to register a new event handler callBind
Call the interface to remove a registered event handler BX24.callUnbind
Call the REST service method with specified parameters BX24.callMethod
Copied
Was the article helpful?
Yes
No
Previous
Call Method
Next
Call Event Handler Registration Interface

---

## Call the interface to register a new event handler callBind

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/how-to-call-rest-methods/bx24-call-bind

Call the interface to register a new event handler callBind | Bitrix24 REST API and Marketplace Applications
Call the interface to register a new event handler callBind
Call the interface to register a new event handler callBind
Parameters
Example
Continue your exploration
BX24
.
callBind
(
String
event,
String
handler[
Integer
auth_type[
Function
callback
]
]
);
This interface is for the method
event.bind
, which registers a new
event
handler.
Note
Works only when authorized as a user with
portal administration
rights.
Parameters
Parameters
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
Identifier of the user under which the event handler is authorized. By default, the authorization of the user whose actions triggered the event will be used
callback
function
Function to handle the result of the method call
Example
Example
BX24.callBind('OnAppUninstall', 'http://www.my-domain.com/handler/');
How to Use Examples in Documentation
Continue your exploration
Continue your exploration
Call the interface to remove a registered event handler BX24.callUnbind
Call the REST service method with specified parameters BX24.callMethod
Send a batch of requests with BX24.callBatch
Copied
Was the article helpful?
Yes
No
Previous
Send Batch of Requests
Next
Call Event Handler Deletion Interface

---

## Call the interface to remove a registered event handler BX24.callUnbind

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/how-to-call-rest-methods/bx24-call-unbind

Call the interface to remove a registered event handler BX24.callUnbind | Bitrix24 REST API and Marketplace Applications
Call the interface to remove a registered event handler BX24.callUnbind
Call the interface to remove a registered event handler BX24.callUnbind
Parameters
Example
Continue exploring
BX24
.
callUnbind
(
String
event,
String
handler[
Integer
auth_type[
Function
callback
]
]
);
The interface for the method
event.unbind
, which removes a registered
event
handler.
Note
Works only when authorized as a user with administrative rights on the account.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
event
string
Event name
handler
string
Link to the event handler
auth_type
integer
Identifier of the user under which the event handler is authorized.
Note
If you need to remove event handlers set with an empty
auth_type
(authorized on behalf of the user who triggered the event), but keep the other handlers, specify
auth_type=0
or an empty value for the parameter. If you need to remove event handlers for all users, specify the value
null
.
callback
function
Function to handle the result of the method call
Example
Example
BX24
.
callUnbind
(
'OnAppUninstall'
,
'http://www.my-domain.com/handler/'
);
How to Use Examples in Documentation
Continue exploring
Continue exploring
Call the interface to register a new event handler callBind
Call the REST service method with specified parameters BX24.callMethod
Send a batch of requests with BX24.callBatch
Copied
Was the article helpful?
Yes
No
Previous
Call Event Handler Registration Interface
Next
Overview of System Functions

---

## Overview of System Functions

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/system-functions/index

Overview of System Functions | Bitrix24 REST API and Marketplace Applications
Overview of System Functions
Overview of System Functions
Function
Description
BX24.init
Adds an event handler for the "library is ready" event
BX24.install
Allows setting an event handler for the "application is launched for the first time for the current user" event
BX24.installFinish
Function that signals the completion of the application's installer or setup process
BX24.getAuth
Retrieves the current authorization data via the OAuth 2.0 protocol
BX24.refreshAuth
Forces an update of the authorization key
Was the article helpful?
Yes
No
Previous
Call Event Handler Deletion Interface
Next
Initialize the Library

---

## Initialize the BX24.init Library

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/system-functions/bx24-init

Initialize the BX24.init Library | Bitrix24 REST API and Marketplace Applications
Initialize the BX24.init Library
Initialize the BX24.init Library
Function Parameters
Example
Continue Learning
BX24
.
init
(
someCallback
:
function
):
void
;
The method executes the
someCallback
function in the context of the application page after the account data has been retrieved. It makes sense to perform all functions that interact with the target account after initialization.
The
BX24.init
function adds an event handler for the "library ready" event. During application initialization, the library requests data for operation from the parent frame. Some actions can only be performed after this data has been received (for example, working with application settings, current user permissions, sending requests to REST, etc.).
Function Parameters
Function Parameters
Name
type
Description
someCallback
function
Accepts a function that will be executed upon success
Example
Example
document
.
addEventListener
(
"DOMContentLoaded"
,
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
console
.
log
(
"BX24 initialized successfully."
);
// Make an API call to fetch current user information
BX24
.
callMethod
(
'user.current'
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
(
"Error fetching user data: "
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
"User data: "
, result.
data
());
}
}
);
});
});
How to Use Examples in Documentation
Continue Learning
Continue Learning
Handle the first launch event of the application by the user BX24.install
Notify about the completion of the installer BX24.installFinish
Get Data for OAuth 2.0 BX24.getAuth
Force Update Authorization Key BX24.refreshAuth
Copied
Was the article helpful?
Yes
No
Previous
Overview of System Functions
Next
Handle the First Launch Event of the Application by the User

---

## Handle the first launch event of the application by the user BX24.install

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/system-functions/bx24-install

Handle the first launch event of the application by the user BX24.install | Bitrix24 REST API and Marketplace Applications
Handle the first launch event of the application by the user BX24.install
Handle the first launch event of the application by the user BX24.install
Function Parameters
Example
Continue Learning
BX24
.
install
(
someCallback
:
function
|string):
void
;
The
BX24.install
function allows you to set a handler for the event "the application is launched for the first time by the current user." This event occurs immediately after the "library is ready for use" event, but before the handlers set in
BX24.init
are executed. The handler must signal the completion of the setup process by calling the
BX24.installFinish
function.
If a string is passed as the handler, it is treated as a link to a js file that needs to be loaded and executed when the event is triggered. In any case, if the current user is launching the application for the first time and at least one handler for this event is set,
BX24.init
will only be triggered after the call to
BX24.installFinish
.
Function Parameters
Function Parameters
Name
type
Description
someCallback
function
Accepts a function that will be executed upon success
someCallback
string
If a string is provided, it is the path to the js file. The file will be loaded first, then the
BX24.installFinish
function will be called
Example
Example
BX24
.
install
(
function
(
){
BX24
.
callMethod
(
'user.current'
, {},
function
(
res
){
alert
(
'The Hello World application greets you, '
+ res.
data
().
NAME
+
'!'
);
BX24
.
installFinish
();
});
});
How to Use Examples in Documentation
Continue Learning
Continue Learning
Initialize the BX24.init Library
Notify about the completion of the installer BX24.installFinish
Get Data for OAuth 2.0 BX24.getAuth
Force Update Authorization Key BX24.refreshAuth
Copied
Was the article helpful?
Yes
No
Previous
Initialize the Library
Next
Notify About the Completion of the Installer

---

## Notify about the completion of the installer BX24.installFinish

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/system-functions/bx24-install-finish

Notify about the completion of the installer BX24.installFinish | Bitrix24 REST API and Marketplace Applications
Notify about the completion of the installer BX24.installFinish
Notify about the completion of the installer BX24.installFinish
Example
Continue your study
BX24
.
installFinish
():
void
;
The function
BX24.installFinish
indicates the completion of the installer or application setup.
If the function is called during the installer startup phase, the page will reload and the application will launch. If called during the setup phase, it will trigger the handlers for
BX24.init
. In other cases, there will be no effect from the call.
No parameters.
Example
Example
document
.
addEventListener
(
"DOMContentLoaded"
,
function
(
) {
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
});
Continue your study
Continue your study
Initialize the BX24.init Library
Handle the first launch event of the application by the user BX24.install
Get Data for OAuth 2.0 BX24.getAuth
Force Update Authorization Key BX24.refreshAuth
Copied
Was the article helpful?
Yes
No
Previous
Handle the First Launch Event of the Application by the User
Next
Retrieve Data for OAuth 2.0

---

## Get Data for OAuth 2.0 BX24.getAuth

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/system-functions/bx24-get-auth

Get Data for OAuth 2.0 BX24.getAuth | Bitrix24 REST API and Marketplace Applications
Get Data for OAuth 2.0 BX24.getAuth
Get Data for OAuth 2.0 BX24.getAuth
Example
Continue Learning
BX24
.
getAuth
(): boolean|object;
The function
BX24.getAuth
retrieves the current authorization data via the OAuth 2.0 protocol. It returns an object in the following format:
{
access_token
:
"cd4b8566006efd82005fdecc000000007dccbb3dcc7411d1e5878338535115c7e"
,
domain
:
"b24.yurta.bx"
,
expires_in
:
1720011727002
,
member_id
:
"42bc01fbd89dd1d45d13506933f6f4fc"
,
refresh_token
:
"bdc"
}
The expiration date is provided as a
date
object.
It only works after
BX24.init
. If called before the application is initialized or after the token has expired, it will return
false
. When the token expires, a new one is automatically generated on the next call to
BX24.callMethod
or
BX24.refreshAuth
.
No parameters required.
Example
Example
document
.
addEventListener
(
"DOMContentLoaded"
,
function
(
) {
BX24
.
init
(
() =>
{
const
authInfo =
BX24
.
getAuth
();
console
.
log
(
'B24: authInfo: '
, authInfo);
});
});
How to Use Examples in Documentation
Continue Learning
Continue Learning
Initialize the BX24.init Library
Handle the first launch event of the application by the user BX24.install
Notify about the completion of the installer BX24.installFinish
Force Update Authorization Key BX24.refreshAuth
Copied
Was the article helpful?
Yes
No
Previous
Notify About the Completion of the Installer
Next
Force Update the Authorization Key

---

## Force Update Authorization Key BX24.refreshAuth

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/system-functions/bx24-refresh-auth

Force Update Authorization Key BX24.refreshAuth | Bitrix24 REST API and Marketplace Applications
Function Parameters
Force Update Authorization Key BX24.refreshAuth
Function Parameters
Example
Continue Learning
BX24
.
refreshAuth
(
someCallback
:
function
): object
The
BX24.refreshAuth
function forcefully updates the authorization key. The handler function
someCallback
will receive an object similar to
BX24.getAuth()
. It only works after
BX24.init
.
Function Parameters
Function Parameters
Name
type
Description
someCallback
function
Accepts a function that will be executed upon success
Example
Example
BX24
.
init
(
() =>
{
const
authInfo =
BX24
.
getAuth
();
console
.
log
(
'BX24: current authInfo: '
, authInfo);
const
button =
document
.
createElement
(
'button'
);
button.
textContent
=
'Refresh auth'
;
button.
addEventListener
(
'click'
,
() =>
{
BX24
.
refreshAuth
(
(
refreshedAuthInfo
) =>
{
console
.
log
(
'BX24: refreshed authInfo: '
, refreshedAuthInfo);
})
});
document
.
body
.
appendChild
(button);
});
How to Use Examples in Documentation
Continue Learning
Continue Learning
Initialize the BX24.init Library
Handle the first launch event of the application by the user BX24.install
Notify about the completion of the installer BX24.installFinish
Get Data for OAuth 2.0 BX24.getAuth
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Data for OAuth 2.0
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/options/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Two objects are used to work with application settings:
BX24.userOption
— works with the settings of the current user. This object operates after
BX24.init
. The value of user settings is set immediately.
BX24.appOption
— works with the general settings of the application. This object operates after
BX24.init
. Setting application settings is available only to users with application management access permission (see
BX24.isAdmin
). A completion handler may be required for application settings (the
callback
parameter in
BX24.appOption.set
).
Method
Description
BX24.userOption.set
This method sets the settings for the current user
BX24.userOption.get
This method returns the settings for the current user
BX24.appOption.set
This method sets the general settings for the current application
BX24.appOption.get
This method returns the setting by its code
Copied
Was the article helpful?
Yes
No
Previous
Force Update the Authorization Key
Next
Set User Settings

---

## Set Settings for User BX24.userOption.set

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/options/bx24-user-option-set

Set Settings for User BX24.userOption.set | Bitrix24 REST API and Marketplace Applications
Method Parameters
Set Settings for User BX24.userOption.set
Method Parameters
Code Example
Continue Learning
BX24
.
userOption
.
set
(string name, string value):
void
;
The method
BX24.userOption.set
sets the
value
of the setting named
name
for the current user. The value is set immediately.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
name
*
string
Parameter code
value
*
mixed
Parameter value
Code Example
Code Example
BX24
.
init
(
() =>
{
BX24
.
userOption
.
set
(
'param_str'
,
'str'
);
BX24
.
userOption
.
set
(
'param_numb'
,
1
);
BX24
.
userOption
.
set
(
'param_obj'
, {
foo
:
'bar'
});
});
How to Use Examples in Documentation
Continue Learning
Continue Learning
Get User Settings BX24.userOption.get
Set Settings for the Application BX24.appOption.set
Get Application Settings BX24.appOption.get
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get User Settings

---

## Get User Settings BX24.userOption.get

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/options/bx24-user-option-get

Get User Settings BX24.userOption.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get User Settings BX24.userOption.get
Method Parameters
Code Examples
Continue Learning
BX24
.
userOption
.
get
(string name): mixed;
The method
BX24.userOption.get
returns the value of the setting with the name
name
for the current user.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
name
*
string
Parameter code
Code Examples
Code Examples
BX24
.
init
(
() =>
{
BX24
.
userOption
.
set
(
'param_str'
,
'str'
);
BX24
.
userOption
.
set
(
'param_numb'
,
1
);
BX24
.
userOption
.
set
(
'param_obj'
, {
foo
:
'bar'
});
console
.
log
(
BX24
.
userOption
.
get
(
'param_str'
));
//will return str
console
.
log
(
BX24
.
userOption
.
get
(
'param_numb'
));
//will return 1
console
.
log
(
BX24
.
userOption
.
get
(
'param_obj'
));
//will return {foo: 'bar'}
});
How to Use Examples in Documentation
Continue Learning
Continue Learning
Set Settings for User BX24.userOption.set
Set Settings for the Application BX24.appOption.set
Get Application Settings BX24.appOption.get
Copied
Was the article helpful?
Yes
No
Previous
Set User Settings
Next
Set Application Settings

---

## Set Settings for the Application BX24.appOption.set

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/options/bx24-app-option-set

Set Settings for the Application BX24.appOption.set | Bitrix24 REST API and Marketplace Applications
Method Parameters
Set Settings for the Application BX24.appOption.set
Method Parameters
Code Example
Continue Learning
BX24
.
appOption
.
set
(string name, mixed value[,
Function
callback]):
void
;
The method
BX24.appOption.set
sets global settings for the current application.
Setting application values is only available to users with application management access permission (see
BX24.isAdmin
). A completion handler may be required for application settings (see the
callback
parameter below).
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
name
*
string
Parameter code
value
*
mixed
Parameter value
callback
function
Callback after saving. The current application settings will be passed as an argument
Code Example
Code Example
BX24
.
init
(
() =>
{
BX24
.
appOption
.
set
(
'param_str'
,
'str1'
,
(
params
) =>
console
.
log
(params));
BX24
.
appOption
.
set
(
'param_numb'
,
1
);
});
How to Use Examples in Documentation
Continue Learning
Continue Learning
Set Settings for User BX24.userOption.set
Get User Settings BX24.userOption.get
Get Application Settings BX24.appOption.get
Copied
Was the article helpful?
Yes
No
Previous
Get User Settings
Next
Get Application Settings

---

## Get Application Settings BX24.appOption.get

**Source:** https://apidocs.bitrix24.com/sdk/bx24-js-sdk/options/bx24-app-option-get

Get Application Settings BX24.appOption.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Application Settings BX24.appOption.get
Method Parameters
Code Examples
Continue Learning
BX24
.
appOption
.
get
(string name, mixed value): mixed;
The method
BX24.appOption.get
returns a setting by its code.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
name
*
string
Parameter code
Code Examples
Code Examples
BX24
.
init
(
() =>
{
BX24
.
appOption
.
set
(
'param_str'
,
'str1'
,
(
params
) =>
console
.
log
(params));
BX24
.
appOption
.
set
(
'param_numb'
,
1
);
console
.
log
(
BX24
.
appOption
.
get
(
'param_str'
));
//will return str1
console
.
log
(
BX24
.
appOption
.
get
(
'param_numb'
));
//will return 1
});
How to Use Examples in Documentation
Continue Learning
Continue Learning
Set Settings for User BX24.userOption.set
Get User Settings BX24.userOption.get
Set Settings for the Application BX24.appOption.set
Copied
Was the article helpful?
Yes
No
Previous
Set Application Settings
Next
Overview of Methods

---

## MCP Server for Working with Bitrix24 REST API

**Source:** https://apidocs.bitrix24.com/sdk/mcp

MCP Server for Working with Bitrix24 REST API | Bitrix24 REST API and Marketplace Applications
What is MCP
MCP Server for Working with Bitrix24 REST API
What is MCP
How to Connect to the MCP Server
Cursor
GitHub Copilot Chat, VS Code
Claude Desktop, Anthropic
Gemini Code Assist CLI
Request Examples
Cursor
GitHub Copilot Chat, VS Code
Claude Desktop, Anthropic
Gemini Code Assist CLI
When a developer asks the AI assistant in the development environment to write code for integration with Bitrix24, the neural network may suggest non-existent methods or pass unnecessary parameters. MCP provides the assistant with direct access to up-to-date documentation, making the responses more accurate.
What is MCP
What is MCP
MCP (Model Context Provider) is a server that transmits structured data to the AI assistant: method descriptions, parameter lists, acceptable values, and usage hints.
MCP allows:
obtaining relevant API methods and fields for a specific task,
working with structured data instead of free text,
reducing the number of errors and code corrections.
How to Connect to the MCP Server
How to Connect to the MCP Server
Specify the server address
https://mcp-dev.bitrix24.com/mcp
in the development environment settings.
The server is accessible without authorization.
Cursor
Cursor
Open
File > Preferences > Cursor Settings > Tools & MCP > New MCP server
. Cursor will open the system file
mcp.json
.
Add the configuration by creating a new array element
mcpServers
in the
mcp.json
file:
{
"mcpServers"
:
{
"b24-dev-mcp"
:
{
"url"
:
"https://mcp-dev.bitrix24.com/mcp"
,
"timeout"
:
30000
}
}
}
Save the file. On the
File > Preferences > Cursor Settings > Tools & MCP
page, a green indicator will appear next to the server along with a list of available tools.
When composing a request, add the
mcp.json
file to the context.
Alternative way to add MCP:
<
a
href
=
"https://cursor.com/en-US/install-mcp?name=b24-dev-mcp&config=eyJ1cmwiOiJodHRwczovL21jcC1kZXYuYml0cml4MjQuY29tL21jcCIsInRpbWVvdXQiOjMwMDAwfQ%3D%3D"
>
<
img
src
=
"https://cursor.com/deeplink/mcp-install-dark.svg"
alt
=
"Add b24-dev-mcp MCP server to Cursor"
height
=
"32"
/>
</
a
>
GitHub Copilot Chat, VS Code
GitHub Copilot Chat, VS Code
For setup, use the instructions from
GitHub
.
Create a file
.vscode/mcp.json
in the root of the project. The content of the file:
{
"servers"
:
{
"b24-dev-mcp"
:
{
"url"
:
"https://mcp-dev.bitrix24.com/mcp"
,
"type"
:
"http"
}
}
,
"inputs"
:
[
]
}
Start the MCP agent by clicking the
Start
button that will appear in the
.vscode/mcp.json
file.
Select the configured MCP agent in the chat. Copilot will request context from MCP when generating code.
Claude Desktop, Anthropic
Claude Desktop, Anthropic
Go to
Settings > Connectors
.
Click
Add custom connector
.
Fill in the fields:
Name
:
b24-dev-mcp
;
URL
:
https://mcp-dev.bitrix24.com/mcp
.
Save the settings. Claude will automatically determine when to use MCP.
Gemini Code Assist CLI
Gemini Code Assist CLI
Add the MCP server with the command:
gemini mcp add --transport http b24-dev-mcp https://mcp-dev.bitrix24.com/mcp
Check that the server appears in the list with the command
gemini mcp list
. Gemini will automatically determine when to use MCP.
Request Examples
Request Examples
The MCP server automatically provides the assistant with up-to-date Bitrix24 REST API data, but the ways to interact between the development environment and MCP vary.
Cursor
Cursor
Feature
: It is necessary to connect the MCP configuration in the chat context.
Add the
mcp.json
file to the chat context.
Send a request in the chat with the AI assistant — "Write a
curl
request to create a lead in Bitrix24."
The assistant will refer to the MCP server.
MCP will return information about the method and its parameters from the documentation.
The assistant will generate code based on the MCP response.
GitHub Copilot Chat, VS Code
GitHub Copilot Chat, VS Code
Feature
: It is necessary to select MCP as the agent to execute the request.
Select the MCP agent and send a request in the chat with the AI assistant — "Create a lead in Bitrix24 with contact information and source 'website'. Show an example in JavaScript."
Copilot will automatically use the selected MCP agent.
MCP will return information about the method and its parameters from the documentation.
The assistant will generate code based on the MCP response.
Claude Desktop, Anthropic
Claude Desktop, Anthropic
Feature
: Automatic determination of the need to use MCP.
Send a request in the chat with the AI assistant — "Write a request to create a new lead in Bitrix24. The lead will include the data: name, company, and phone."
Claude will determine that data from the connected MCP is needed and will send the request.
MCP will return information about the method and its parameters from the documentation.
The assistant will generate code based on the MCP response.
Gemini Code Assist CLI
Gemini Code Assist CLI
Feature
: Automatic determination of the need to use MCP.
Execute the command
gemini chat
and send a request — "Gather a
curl
request to create a lead with fields name, phone, and source 'site'."
Gemini will determine that data from the connected MCP is needed and will send the request.
MCP will return a description of the appropriate method and its parameters from the documentation.
Gemini will generate code based on the MCP response.
Copied
Was the article helpful?
Yes
No
Previous
Working in the Context of the Current User
Next
Section Overview

---

