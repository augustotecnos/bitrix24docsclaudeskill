---
description: 'Vibe API: Vibe/social features'
methods:
- app.code
- app.com
- user.avatar
pages: 5
title: 'Vibe API: Vibe/social features'
---
# Vibe API: Vibe/social features
> Vibe API: Vibe/social features
> **5 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Widgets and Start page: the Vibe](#widgets-and-start-page-the-vibe)
- [Add Widget to Start Page: the Vibe landing.repowidget.register](#add-widget-to-start-page-the-vibe-landingrepowidge)
- [Unregister Widget for Vibe landing.repowidget.unregister](#unregister-widget-for-vibe-landingrepowidgetunregi)
- [Get the list of widgets landing.repowidget.getlist](#get-the-list-of-widgets-landingrepowidgetgetlist)
- [Enable Debug Mode landing.repowidget.debug](#enable-debug-mode-landingrepowidgetdebug)

---

## Widgets and Start page: the Vibe

**Source:** https://apidocs.bitrix24.com/api-reference/vibe/index

Widgets and Start page: the Vibe | Bitrix24 REST API and Marketplace Applications
Widgets and Start page: the Vibe
Widgets and Start page: the Vibe
How Widgets Work
Vue Directives
Interactive Actions
How the Widget Works
Examples of Vue Syntax for Vibe Widgets
Localization
Variables
Using Variables in openPath
Methods for Working with Widgets
The Vibe is the start page of
Bitrix24
, replacing the familiar
Feed
and allowing for a more personalized interface (details in
article
).
The administrator configures the page in the builder using ready-made blocks and widgets, similar to how it's done in
Sites
. In addition to the system widgets of
Bitrix24
, developers can add their own using the appropriate REST API methods.
Note
Widget
— a dynamic element of the Vibe that displays data obtained through the corresponding server handler. This allows widgets to be interactive, showing changing data in response to user actions.
For example, you can sort data in a table, load new data, open a slider with additional interface for your solution, etc.
Additionally, the Vibe created on your
Bitrix24
can be exported as a ready-made solution for publication in the
Market
.
How Widgets Work
How Widgets Work
The front-end of the widget is implemented based on the
Vue templating engine
. The widget retrieves data for display by making a request to an external handler.
In fact, when adding your widget to
Bitrix24
, you need to provide the Vue template markup, the necessary CSS classes, and the address of the handler that will be responsible for passing data to the Vue template.
Vue Directives
Vue Directives
In the widgets for the Vibe, we support the following Vue directives and constructs:
variables
{{ your_variable_name }}
conditional operator
v-if
/
v-else
conditional attributes
:class
,
:disabled
, etc.
loop
v-for
expressions, for example,
not_var{{ number + 1 }}
handlers
@click
and
v-on:click
Interactive Actions
Interactive Actions
Custom JS code cannot be added to the widgets, so only the following predefined functions can be used as event handlers for
@click
and
v-on:click
:
fetch(?params)
— calls the widget handler to obtain new data, passing the specified parameters
params
to the handler;
openApplication(?params)
— opens the slider of your application with the ability to pass arbitrary parameters
params
. Essentially, this is a way to call
openApplication
from the Vibe widget interface;
openPath(url)
— opens the
Bitrix24
page at the specified
url
in the slider. Essentially, this is a way to call
openPath
from the Vibe widget interface.
How the Widget Works
How the Widget Works
The most important part of the functionality lies in using
fetch(?params)
and your widget handler.
When a Bitrix24 administrator adds your widget to the Vibe page or when a regular user opens an already published Vibe page on their account, Bitrix24 makes a request to the widget handler URL you specified during widget registration.
Your handler returns a specific data structure defined by you in the form of a JSON string.
Vue executes the template code of your widget, substituting the data obtained from the handler in step 2. This forms the initial complete appearance of the widget.
If you used the
fetch
function (for example, with parameters
{'action': 'getItems'}
) in your template when clicking on a certain link,
Bitrix24
will again call your widget handler, passing those same parameters
{'action': 'getItems'}
in a POST request.
Your handler, upon receiving the request and analyzing the input parameters, should respond with a new set of data and return it again as a JSON string. This set can be either complete or partial to save traffic and improve the widget's performance.
The newly obtained data will be substituted back into your template.
In this straightforward manner, your widget can change its appearance and displayed data in response to user actions.
Examples of Vue Syntax for Vibe Widgets
Examples of Vue Syntax for Vibe Widgets
Localization
Localization
Use the standard syntax for accessing Vue variables to call
$Bitrix.Loc.getMessage
to display the value of a constant in the visible part of the markup:
<h3
class
="
w
-
title
">
{{
$Bitrix
.Loc.
getMessage
(
'W_TITLE'
) }}</h3>
Use the Vue conditional attribute syntax to assign the value of
$Bitrix.Loc.getMessage
to the desired node attribute:
<input
type=
"text"
class
="
task
-
widget__filter
"
:
placeholder
="$
Bitrix
.
Loc
.
getMessage
('
W_FILTER
')"
v
-
model
="
taskFilter
"
/>
Variables
Variables
Use the standard syntax for accessing Vue variables to display values in the visible part of the markup:
<td
class
="
task
-
widget__cell
">
{{ task.id }}</td>
Use the Vue conditional attribute syntax to assign the value of a variable to the desired node attribute:
<img :src=
"user.avatar"
class
="
task
-
widget__avatar
" />
Use logical expressions to apply optional classes:
<a href=
"#"
:
class
="
{
'task-widget__link--disabled'
: currentPage ===
1
}
">
Using Variables in openPath
Using Variables in openPath
Use backticks to reference Vue variables when forming the desired path:
<tr
v-
for
=
"(task, index) in taskItems"
:key=
"task.id"
@click=
"openPath(`/company/personal/user/${task.responsibleId}/tasks/task/view/${task.id}/`)"
>
Use string concatenation to form the path:
<tr
v-
for
=
"(task, index) in taskItems"
:key=
"task.id"
@click=
"openPath('/company/personal/user/' + task.responsibleId + '/tasks/task/view/' + task.id)"
>
Methods for Working with Widgets
Methods for Working with Widgets
Method
Description
landing.repowidget.register
Registers a widget
landing.repowidget.unregister
Unregisters a widget
landing.repowidget.getlist
Returns a list of widgets
landing.repowidget.debug
Enables debug mode
Copied
Was the article helpful?
Yes
No
Previous
Return Parameters to a Workflow Action or Automation Rule
Next
Add Widget

---

## Add Widget to Start Page: the Vibe landing.repowidget.register

**Source:** https://apidocs.bitrix24.com/api-reference/vibe/landing-repowidget-register

Add Widget to Start Page: the Vibe landing.repowidget.register | Bitrix24 REST API and Marketplace Applications
Add Widget to Start Page: the Vibe landing.repowidget.register
Add Widget to Start Page: the Vibe landing.repowidget.register
Method Parameters
Parameter fields
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
landing
Who can execute the method: any user
The method
landing.repowidget.register
adds a widget for the Start page: the Vibe. It returns an error or the
ID
of the added widget.
During the addition, a check is performed. If a widget with the code
code
has already been registered previously, its content will be updated. Widgets already placed on the Vibe will be automatically updated in case of content changes.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
code
*
string
Unique code for the widget. It is highly recommended to use a unique prefix for your widgets to avoid the risk of code conflicts with widgets from other developers
fields
*
object
Field values for creating the widget
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
NAME
string
Widget name
PREVIEW
string
URL of the widget cover image for the widget selection slider
DESCRIPTION
string
Widget description
CONTENT
string
Widget markup using Vue constructs
SECTIONS
string
Code of the section where the widget will be added. List of available sections:
widgets_company_life
— Company Life
widgets_new_employees
— New Employees
widgets_team
— Team
widgets_automation
— Automation
widgets_events
— Meetings and Events
widgets_profile
— Employee Profile
widgets_tasks
— Tasks and Projects
widgets_sales
— Sales and Clients
widgets_hr
— HR
widgets_other
— Other
widgets_separators
— Transitions and Separators
widgets_text
— Text
widgets_image
— Images
widgets_video
— Video
WIDGET_PARAMS
object
Parameters
for the Vue templater. If absent, the block will remain as regular HTML code with
{{}}
ACTIVE
char
Widget activity. Accepts values:
Y
- widget is active and available
N
- widget is inactive and unavailable
SITE_TEMPLATE_ID
string
Binding the widget to a specific site template.
Only for on-premise Bitrix24!
Parameter WIDGET_PARAMS
Parameter WIDGET_PARAMS
Required parameters are marked with *
Name
type
Description
rootNode
*
string
Selector for the root element in the markup that will be turned into a Vue component. The root element must be the only element in the passed template; all other markup will be cleared
lang
string
Array of language phrases used in constructs
{{$Bitrix.Loc.getMessage('W_EMPTY')}}
handler
*
string
Address of the
external handler
to which requests will be sent.
Important
: The handler must be accessible from the external network! Check the handler's availability with special services
style
string
Address of styles for the widget. Styles can also be set inline in the markup via the binding
:style="{borderBottom: '1px solid red'}"
demoData
*
object
Demo data for the widget that will be used to showcase the widget in the Vibe templates in
Bitrix24 Marketplace
.
If you are developing a widget for a specific Bitrix24 and do not plan to publish it in the Marketplace, you can specify any array as the parameter value; it will not be used anyway.
However, if you are preparing a mass-market solution with a widget, pay maximum attention to the demo data — they will be displayed in the preview slider of the Vibe template! Obviously, the structure of the demo data should match what your
handler
would return in normal widget usage
Code Examples
Code Examples
How to Use Examples in Documentation
JS
PHP
BX24.js
PHP CRest
try
{
const
response =
await
$b24.
callMethod
(
'landing.repowidget.register'
,
data
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
return
;
}
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
'landing.repowidget.register'
,
[
'code'
=>
'my_widget'
,
'fields'
=> [
'NAME'
=>
'My widget'
,
'PREVIEW'
=>
'https://my-app.com/vibe_preview.jpg'
,
'CONTENT'
=>
$content
,
'SECTIONS'
=>
'widgets_company_life'
,
'WIDGET_PARAMS'
=> [
'rootNode'
=>
'.my-app-w-container'
,
'lang'
=> [
'de'
=> [
'W_TITLE'
=>
'People and their ages'
,
'W_EMPTY'
=>
'Empty'
,
],
'en'
=> [
'W_TITLE'
=>
'People and their ages'
,
'W_EMPTY'
=>
'Empty'
,
},
],
'handler'
=>
'https://my-app.com/vibe.php'
,
'style'
=>
'https://my-app.com/vibe.css'
,
'demoData'
=> [
'desc'
=>
'Just a test widget'
,
'count'
=>
420
,
'persons'
=> [
[
'name'
=>
'Person 1'
,
'age'
=>
21
],
[
'name'
=>
'Person 2'
,
'age'
=>
42
],
[
'name'
=>
'Person 3'
,
'age'
=>
123
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
'Error registering repowidget: '
.
$e
->
getMessage
();
}
const
content =
`
<div class="my-app-w-container">
<h2 class="w-title" :style="{borderBottom: '1px solid red'}">
{{$Bitrix.Loc.getMessage('W_TITLE')}}
</h2>
<h3>Description: {{desc}}</h3>
<div v-for="(value) in persons">
<p>
<span class="w-name">{{value.name}}</span>:
<span class="w-age">{{value.age}}</span>
</p>
</div>
<div v-if="persons == null">
{{$Bitrix.Loc.getMessage('W_EMPTY')}}
</div>
<h4>Just a number {{count}}</h4>
<div class="w-buttons">
<button @click="fetch">Get data (without parameters)</button>
<button @click="fetch({param: 'a'})">Data for parameter 'a'</button>
<button @click="fetch({param: 'b'})">Data for parameter 'b'</button>
<button @click="openApplication({param1: '1', param2: 'false'})">Open application</button>
<button @click="openPath('/crm')">Open local address in slider</button>
</div>
</div>
`
;
const
data = {
code
:
'my_widget'
,
fields
: {
NAME
:
'My widget'
,
PREVIEW
:
'https://my-app.com/vibe_preview.jpg'
,
CONTENT
: content,
SECTIONS
:
'widgets_company_life'
,
WIDGET_PARAMS
: {
rootNode
:
'.my-app-w-container'
,
lang
: {
de
: {
W_TITLE
:
'People and their ages'
,
W_EMPTY
:
'Empty'
,
},
en
: {
W_TITLE
:
'People and their ages'
,
W_EMPTY
:
'Empty'
,
},
},
handler
:
'https://my-app.com/vibe.php'
,
style
:
'https://my-app.com/vibe.css'
,
demoData
: {
desc
:
'Just a test widget'
,
count
:
420
,
persons
: [
{
'name'
:
'Person 1'
,
'age'
:
21
},
{
'name'
:
'Person 2'
,
'age'
:
42
},
{
'name'
:
'Person 3'
,
'age'
:
123
},
],
},
},
},
};
BX24
.
callMethod
(
'landing.repowidget.register'
,
data,
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
$content
=
<<<'HTML'
<div class="my-app-w-container">
<h2 class="w-title" :style="{borderBottom: '1px solid red'}">
{{$Bitrix.Loc.getMessage('W_TITLE')}}
</h2>
<h3>Description: {{desc}}</h3>
<div v-for="(value) in persons">
<p>
<span class="w-name">{{value.name}}</span>:
<span class="w-age">{{value.age}}</span>
</p>
</div>
<div v-if="persons == null">
{{$Bitrix.Loc.getMessage('W_EMPTY')}}
</div>
<h4>Just a number {{count}}</h4>
<div class="w-buttons">
<button @click="fetch">Get data (without parameters)</button>
<button @click="fetch({param: 'a'})">Data for parameter 'a'</button>
<button @click="fetch({param: 'b'})">Data for parameter 'b'</button>
<button @click="openApplication({param1: '1', param2: 'false'})">Open application</button>
<button @click="openPath('/crm')">Open local address in slider</button>
</div>
</div>
HTML
;
$data
= [
'code'
=>
'my_widget'
,
'fields'
=> [
'NAME'
=>
'My widget'
,
'PREVIEW'
=>
'https://my-app.com/vibe_preview.jpg'
,
'CONTENT'
=>
$content
,
// Vue markup extracted into a separate variable for convenience
'SECTIONS'
=>
'widgets_company_life'
,
'WIDGET_PARAMS'
=> [
'rootNode'
=>
'.my-app-w-container'
,
'lang'
=> [
'de'
=> [
'W_TITLE'
=>
'People and their ages'
,
'W_EMPTY'
=>
'Empty!'
,
],
'en'
=> [
'W_TITLE'
=>
'People and their ages'
,
'W_EMPTY'
=>
'Empty!'
,
],
],
'handler'
=>
'https://my-app.com/vibe.php'
,
'style'
=>
'https://my-app.com/vibe.css'
,
'demoData'
=> [
'desc'
=>
'Just a test widget'
,
'count'
=>
420
,
'persons'
=> [
[
'name'
=>
'Person 1'
,
'age'
=>
21
,
],
[
'name'
=>
'Person 2'
,
'age'
=>
42
,
],
[
'name'
=>
'Person 3'
,
'age'
=>
123
,
],
],
],
],
],
];
$result
=
CRest
::
call
(
'landing.repowidget.register'
,
$data
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
10
,
"time"
:
{
"start"
:
1713949410.036288
,
"finish"
:
1713949411.632775
,
"duration"
:
1.596487045288086
,
"processing"
:
0.6458539962768555
,
"date_start"
:
"2024-04-24T11:03:30+02:00"
,
"date_finish"
:
"2024-04-24T11:03:31+02:00"
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
Identifier of the added widget
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
Unregister Widget for Vibe landing.repowidget.unregister
Get the list of widgets landing.repowidget.getlist
Enable Debug Mode landing.repowidget.debug
Copied
Was the article helpful?
Yes
No
Previous
Vibe and Widgets
Next
Remove Widget

---

## Unregister Widget for Vibe landing.repowidget.unregister

**Source:** https://apidocs.bitrix24.com/api-reference/vibe/landing-repowidget-unregister

Unregister Widget for Vibe landing.repowidget.unregister | Bitrix24 REST API and Marketplace Applications
Method Parameters
Unregister Widget for Vibe landing.repowidget.unregister
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
landing
Who can execute the method: any user
The method
landing.repowidget.unregister
removes the widget for Start page: the Vibe. On success, it returns
true
; otherwise, it returns
false
or an error with a description.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
code
*
string
Unique code of the widget to be removed
Code Examples
Code Examples
How to Use Examples in Documentation
JS
PHP
BX24.js
PHP CRest
try
{
const
response =
await
$b24.
callMethod
(
'landing.repowidget.unregister'
, {
code
:
'my_widget'
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
info
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
'landing.repowidget.unregister'
,
[
'code'
=>
'my_widget'
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
'Error unregistering repowidget: '
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
'landing.repowidget.unregister'
, {
code
:
'my_widget'
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
info
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
'landing.repowidget.unregister'
,
[
'code'
=>
'my_widget'
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
1713949410.036288
,
"finish"
:
1713949411.632775
,
"duration"
:
1.596487045288086
,
"processing"
:
0.6458539962768555
,
"date_start"
:
"2024-04-24T11:03:30+02:00"
,
"date_finish"
:
"2024-04-24T11:03:31+02:00"
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
Result of the widget removal
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
Add Widget to Start Page: the Vibe landing.repowidget.register
Get the list of widgets landing.repowidget.getlist
Enable Debug Mode landing.repowidget.debug
Copied
Was the article helpful?
Yes
No
Previous
Add Widget
Next
Get Widget List

---

## Get the list of widgets landing.repowidget.getlist

**Source:** https://apidocs.bitrix24.com/api-reference/vibe/landing-repowidget-get-list

Get the list of widgets landing.repowidget.getlist | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of widgets landing.repowidget.getlist
Method Parameters
Parameter params
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
landing
Who can execute the method: any user
The method
landing.repowidget.getlist
returns a list of widgets for the current application, filtered by the specified criteria.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
params
*
object
Array of fields to retrieve the list of widgets
Parameter params
Parameter params
Required parameters are marked with *
Name
type
Description
select
array
Array
with the list of fields
to be selected.
If not provided or an empty array is passed, all available widgets will be selected
filter
object
Object for filtering the selected records in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
can be found
in the table below
.
An additional prefix can be specified for the key to clarify the filter behavior. Possible prefix values:
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
symbol should not be included in the filter value. The search looks for the substring in any position of the string
=%
— LIKE, substring search. The
%
symbol must be included in the value. Examples:
"mol%" — searching for values starting with "mol"
"%mol" — searching for values ending with "mol"
"%mol%" — searching for values where "mol" can be in any position
%=
— LIKE (see description above)
!%
— NOT LIKE, substring search. The
%
symbol should not be included in the filter value. The search goes from both sides.
!=%
— NOT LIKE, substring search. The
%
symbol must be included in the value. Examples:
"mol%" — searching for values not starting with "mol"
"%mol" — searching for values not ending with "mol"
"%mol%" — searching for values where the substring "mol" is not present in any position
!%=
— NOT LIKE (see description above)
=
— equals, exact match (used by default)
!=
- not equal
!
— not equal
group
array
Array for grouping widgets. Grouping can be done
by fields
of the widget
order
object
Object for sorting the selected records in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
can be found
in the table below
.
Possible values for
order
:
asc
— in ascending order
desc
— in descending order
Fields field
Fields field
Fields of the widget object. Present in the request and response.
Name
type
Description
ID
integer
Widget identifier
XML_ID
string
Unique record code
APP_CODE
string
Code of the current application
ACTIVE
char
Widget activity. Accepts values:
Y
- widget is active and available
N
- widget is inactive and unavailable
NAME
string
Widget name
DESCRIPTION
string
Widget description
SECTIONS
string
Code of the
section
where the widget will be added
PREVIEW
string
URL of the widget cover image for the widget selection slider
WIDGET_PARAMS
object
Parameters
for the Vue template engine
CONTENT
string
Widget markup using Vue constructs
MANIFEST
object
Widget manifest
CREATED_BY_ID
integer
Identifier of the user who created the record
MODIFIED_BY_ID
integer
Identifier of the user who modified the record
DATE_CREATE
date
Creation date
DATE_MODIFY
date
Modification date
SITE_TEMPLATE_ID
string
Binding of the widget to a specific site template.
Only for on-premise Bitrix24!
Code Examples
Code Examples
How to Use Examples in Documentation
JS
PHP
BX24.js
PHP CRest
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'landing.repowidget.getlist'
,
{
params
: {
select
: [
'ID'
,
'NAME'
],
filter
: {
'>ID'
:
'1'
}
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'landing.repowidget.getlist'
, {
params
: {
select
: [
'ID'
,
'NAME'
],
filter
: {
'>ID'
:
'1'
}
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'landing.repowidget.getlist'
, {
params
: {
select
: [
'ID'
,
'NAME'
],
filter
: {
'>ID'
:
'1'
}
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
'landing.repowidget.getlist'
,
[
'params'
=> [
'select'
=> [
'ID'
,
'NAME'
],
'filter'
=> [
'>ID'
=>
'1'
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
'Error getting repowidget list: '
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
'landing.repowidget.getlist'
,
{
params
: {
select
: [
'ID'
,
'NAME'
],
filter
: {
'>ID'
:
'1'
}
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
info
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
'landing.repowidget.getList'
,
[
'params'
=> [
'select'
=> [
'ID'
,
'NAME'
],
'filter'
=> [
'>ID'
=>
'1'
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
[
{
"ID"
:
"4"
,
"XML_ID"
:
"my_widget"
,
"APP_CODE"
:
"app.code"
,
"ACTIVE"
:
"Y"
,
"NAME"
:
"My widget"
,
"DESCRIPTION"
:
null
,
"SECTIONS"
:
"widgets_company_life"
,
"SITE_TEMPLATE_ID"
:
null
,
"PREVIEW"
:
"https://my-app.com/vibe_preview.jpg"
,
"MANIFEST"
:
{
"block"
:
{
"type"
:
[
"mainpage"
]
,
"subtype"
:
[
"widgetvue"
]
,
"subtype_params"
:
{
"rootNode"
:
".w-container"
,
"demoData"
:
{
"desc"
:
"JustSome widget data"
,
"count"
:
"420"
}
,
"handler"
:
"https://my-app.com/vibe.php"
,
"style"
:
"https://my-app.com/vibe.css"
,
"lang"
:
{
"de"
:
{
"W_TITLE"
:
"People and their age"
,
"W_EMPTY"
:
"No people"
}
,
"en"
:
{
"W_TITLE"
:
"Widget title"
,
"W_EMPTY"
:
"Empty!"
}
}
}
}
}
,
"CONTENT"
:
"<div class=\"w-container\">{{desc}}</div>"
,
"CREATED_BY_ID"
:
"1"
,
"MODIFIED_BY_ID"
:
"1"
,
"DATE_CREATE"
:
"10.10.2024 15:55:30"
,
"DATE_MODIFY"
:
"16.10.2024 16:12:57"
}
]
,
"time"
:
{
"start"
:
1729162340.81773
,
"finish"
:
1729162344.800994
,
"duration"
:
3.9832639694213867
,
"processing"
:
3.8990869522094727
,
"date_start"
:
"2024-10-17T15:52:20+01:00"
,
"date_finish"
:
"2024-10-17T15:52:24+01:00"
,
"operating"
:
3.899045944213867
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Array of widgets. Each element of the array is an object, permissible fields are described
above
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
Add Widget to Start Page: the Vibe landing.repowidget.register
Unregister Widget for Vibe landing.repowidget.unregister
Enable Debug Mode landing.repowidget.debug
Copied
Was the article helpful?
Yes
No
Previous
Remove Widget
Next
Enable Debug Mode

---

## Enable Debug Mode landing.repowidget.debug

**Source:** https://apidocs.bitrix24.com/api-reference/vibe/landing-repowidget-debug

Enable Debug Mode landing.repowidget.debug | Bitrix24 REST API and Marketplace Applications
Method Parameters
Enable Debug Mode landing.repowidget.debug
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
landing
Who can execute the method: any user
The method
landing.repowidget.debug
enables debug mode for all widgets of the current application. In this case, the vue application will report more errors in the js console for developer convenience. By default, the mode is disabled.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
enable
boolean
Debug mode activation flag
Code Examples
Code Examples
How to Use Examples in Documentation
JS
PHP
BX24.js
PHP CRest
try
{
const
response =
await
$b24.
callMethod
(
'landing.repowidget.debug'
, {
enable
:
true
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
info
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
'landing.repowidget.debug'
,
[
'enable'
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
'Error calling landing repowidget debug: '
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
'landing.repowidget.debug'
, {
enable
:
true
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
info
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
'landing.repowidget.debug'
,
[
'enable'
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
true
,
"time"
:
{
"start"
:
1713949410.036288
,
"finish"
:
1713949411.632775
,
"duration"
:
1.596487045288086
,
"processing"
:
0.6458539962768555
,
"date_start"
:
"2024-04-24T11:03:30+02:00"
,
"date_finish"
:
"2024-04-24T11:03:31+02:00"
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
On success —
true
, otherwise — error
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
"APP_NOT_FOUND"
,
"error_description"
:
"Cannot find REST application"
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
APP_NOT_FOUND
REST application not found. Occurs when there are issues with the authorization of the REST application on the account
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
Add Widget to Start Page: the Vibe landing.repowidget.register
Unregister Widget for Vibe landing.repowidget.unregister
Get the list of widgets landing.repowidget.getlist
Copied
Was the article helpful?
Yes
No
Previous
Get Widget List
Next
About the Document Generator

---

