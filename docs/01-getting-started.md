---
description: First steps, authentication, making API calls, error codes, limits
methods:
- crm.deal.add
- crm.deal.add.json
- crm.item.add
- placement.list
pages: 9
title: First steps, authentication, making API calls, error codes, limits
---
# First steps, authentication, making API calls, error codes, limits
> First steps, authentication, making API calls, error codes, limits
> **9 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Getting Started](#getting-started)
- [How to Access the REST API?](#how-to-access-the-rest-api)
- [How to Make Your First API Request?](#how-to-make-your-first-api-request)
- [How to Use Examples in Documentation](#how-to-use-examples-in-documentation)
- [REST API Limits](#rest-api-limits)
- [Error Codes](#error-codes)
- [Meetups, Broadcasts, and Recordings for Developers](#meetups-broadcasts-and-recordings-for-developers)
- [Support and Community for Developers](#support-and-community-for-developers)
- [Feedback](#feedback)

---

## Getting Started

**Source:** https://apidocs.bitrix24.com/first-steps/index

Getting Started | Bitrix24 REST API and Marketplace Applications
Getting Started
Getting Started
Accessing the REST API
Setting Up and Using the REST API
First API Request
Request Examples
SDK for Bitrix24 Development
Local Integrations
Ready-Made Scenarios
Mass-Market Applications
API Reference
The documentation for the Bitrix24 REST API describes API methods, request examples, and integration scenarios for application and external service development.
Below is the recommended sequence for studying the documentation, which will help:
understand the structure of the documentation,
master the basic capabilities of the API,
move on to more complex scenarios.
To understand the architecture of applications, authorization principles, working with the REST API, and the environment structure, study the
Bitrix24 REST API Training Course
.
Accessing the REST API
Accessing the REST API
The section
How to Access the REST API
describes how to activate the trial period and gain access to all methods and capabilities of the Bitrix24 REST API. It also includes information about NFR keys for partner developments.
Setting Up and Using the REST API
Setting Up and Using the REST API
The section
Setting Up and Using the REST API
is dedicated to parameters that affect integration operations:
authorization domains,
access permissions,
method call specifics,
environment configuration,
request limits.
This section also contains the article
Configuring Access: Cloud and On-Premise Versions
, which describes how to set up network access for incoming and outgoing requests and how to add IP addresses to the allowed list.
First API Request
First API Request
The section
How to Make Your First API Request
explains how to create an incoming webhook and make your first REST API method call. This allows you to verify the API's functionality and the correctness of the settings.
Request Examples
Request Examples
The section
How to Use Examples in Documentation
describes how to work with request examples, which programming languages are used, and how to connect to libraries. It also shows how to adapt examples to your task and make real requests to the API.
SDK for Bitrix24 Development
SDK for Bitrix24 Development
The section
SDK for Bitrix24 Development
describes ready-made libraries for development and provides information on connecting the MCP service for AI assistants in the development environment.
Local Integrations
Local Integrations
The section
Overview of Tools for Local Integrations
is dedicated to tools for creating integrations that work within Bitrix24 and do not require publication in the Marketplace. This section includes examples of working with local webhooks and applications for task automation and data exchange.
Ready-Made Scenarios
Ready-Made Scenarios
The section
Tutorials: Ready-made Use Cases for REST API
contains step-by-step guides and ready-made scenarios for using the Bitrix24 REST API. For example, how to create and configure a cash register handler or how to retrieve a client's address from the CRM. These examples can be used as a basis for your own solutions.
Mass-Market Applications
Mass-Market Applications
The section
Overview of Mass-Market Applications
describes the principles of working with mass-market applications from the Bitrix24 Marketplace, as well as opportunities for monetization and promotion.
API Reference
API Reference
The section
API Reference
contains descriptions of methods and capabilities of the Bitrix24 REST API. This material helps navigate the API and select methods for specific functionalities.
Was the article helpful?
Yes
No
Previous
What the Bitrix24 REST API Allows
Next
How to Access the REST API

---

## How to Access the REST API?

**Source:** https://apidocs.bitrix24.com/first-steps/access-to-rest-api

How to Access the REST API? | Bitrix24 REST API and Marketplace Applications
How to Access the REST API?
How to Access the REST API?
To use the REST API in Bitrix24, there are several important points to consider.
First, the REST API is only available on
paid plans
of Bitrix24, as well as during the demo plan. If you plan to automate for your specific Bitrix24, you need to switch to a paid plan.
Before purchasing a paid plan, you can test the capabilities of the REST API for 15 days by enabling the
demo plan
on your account. To find out your account's current plan and whether the trial subscription is active, you can use the "My Plan" button in the header of the account.
Technology partners
developing solutions for
listing in Bitrix24 Market
can request a special NFR sandbox for the account where development is taking place. Upon approval of the request, Bitrix24 support will activate a special partner plan that supports the REST API on the specified account. The request for an NFR sandbox can be submitted through the chat in the Developer's area. This will allow you to use the REST API for developing and testing your solutions before publishing them in the Market.
Second, the capabilities of the REST API are limited by the permissions that the specific user making the requests has on the account, as any REST API call is made "on behalf of" that user. To have maximum access to the data and functionality of the account, it is advisable to use an administrator account. However, this does not mean that only the account administrator can use the REST API—any user has access to the REST API through the "Developer resources" section within Bitrix24. Just keep in mind that through the REST API, users can only access the functionality and data that is available to them through the user interface of the account.
Once you have confirmed that the REST API is available on your account, you can proceed to
make your first REST API call
.
Was the article helpful?
Yes
No
Previous
Getting Started
Next
How to Make Your First API Request

---

## How to Make Your First API Request?

**Source:** https://apidocs.bitrix24.com/first-steps/first-rest-api-call

How to Make Your First API Request? | Bitrix24 REST API and Marketplace Applications
Incoming Webhook
How to Make Your First API Request?
Incoming Webhook
Request Generator
Log into your Bitrix24 account and navigate to the Developer resources section via the link in the left menu. To see this menu item, you need to expand the Applications section.
Incoming Webhook
Incoming Webhook
In the opened slider, click on the "Other" section, and then select the "Incoming Webhook" block.
Incoming Webhook
The simplest way to use REST is through what is known as an
incoming webhook
, which is a permanent "key" API with the permissions of the user who created this webhook.
When you open the incoming webhook creation slider, you will see that Bitrix24 has already generated a unique code for this webhook.
Keep the code secret!
This code is essentially an access key or password for the webhook, so you must ensure that it remains confidential.
Request Generator
Request Generator
Below the webhook code in the slider, you will see the
Request Generator
block.
It allows you to make various requests to the Bitrix24 REST API directly from the Bitrix24 interface by selecting different methods from the list and configuring the corresponding method parameters. You can find information about specific parameters in the documentation by following the links provided.
Once you have specified the parameters and their values, Bitrix24 will generate the complete HTTP request for you. You can preview it, copy it to an external system (or browser) for execution, or you can execute it right here and now by clicking the
Execute
button.
When you execute the request, you will receive a response from Bitrix24 in JSON format. Congratulations on your first successful call to the Bitrix24 REST API!
Note
Incoming webhooks are a very convenient tool for using the REST API to solve individual tasks. However, if you want to implement more complex scenarios in your Bitrix24 that involve
different users
, or if you want to develop a
mass-market solution
for placement in the Bitrix24 Marketplace, you will need to use
OAuth 2.0 authorization
with temporary secure authorization tokens for working with REST.
Was the article helpful?
Yes
No
Previous
How to Access the REST API
Next
How to Use Examples

---

## How to Use Examples in Documentation

**Source:** https://apidocs.bitrix24.com/first-steps/how-to-use-examples

How to Use Examples in Documentation | Bitrix24 REST API and Marketplace Applications
Curl Requests
How to Use Examples in Documentation
Curl Requests
Connecting Libraries and SDKs
JavaScript Using bx24.js
JavaScript Using B24JsSDK
PHP Using B24PhpSDK
PHP Using CRest SDK
The documentation includes code examples for various programming languages in the method descriptions and additional tutorials. Each example is often presented in four formats: a curl request with parameters, JS code using the BX24.js library, PHP code using the CRest SDK, and PHP code using the official B24PhpSdk, as well as JS code using the official B24JsSdk.
Curl Requests
Curl Requests
When using the Bitrix24 REST API via curl, no libraries or SDKs are required. You can create parameters for calling any REST method. You just need to be careful about the correct formation of parameters, especially when it comes to parameters that accept arrays or structures as values.
Example of making a request to the Bitrix24 REST API via curl using a temporary access token
OAuth 2.0
:
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{
"fields": {
"title": "New Deal",
"typeId": "SALE",
"stageId": "NEW"
},
auth=YOUR_ACCESS_TOKEN
}'
\
https://your-domain.bitrix24.com/rest/crm.deal.add.json
Example of making a request to the Bitrix24 REST API via curl using an
incoming webhook
:
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{
"fields": {
"title": "New Deal",
"typeId": "SALE",
"stageId": "NEW"
}
}'
\
https://your-domain.bitrix24.com/rest/_USER_ID_/_CODE_/crm.deal.add.json
Replace
USER_ID
and
CODE
with actual values from the incoming webhook.
Connecting Libraries and SDKs
Connecting Libraries and SDKs
To use the examples, you need to include the corresponding library or SDK in your code. Below are instructions and examples for each option.
JavaScript Using bx24.js
JavaScript Using bx24.js
Examples using the standard
bx24.js library
are intended for use within
local
or
mass-market applications
. Unfortunately, you cannot simply use it by including the library on an external site or local HTML page.
However, once you understand the concept of a local or even mass-market application, using the JavaScript examples from the documentation will become very straightforward. To use the JavaScript examples, you only need to include the following script:
<
script
src
=
"//api.bitrix24.com/api/v1/"
>
</
script
>
Example of using bx24.js:
<script src=
"//api.bitrix24.com/api/v1/"
></script>
<
script
>
BX24
.
callMethod
(
"crm.deal.add"
,
{
fields
: {
TITLE
:
"New Deal"
,
TYPE_ID
:
"SALE"
,
STAGE_ID
:
"NEW"
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
log
(result.
data
());
}
}
);
</
script
>
Additional information about BX24.js can be found in the section
Connecting and Using BX24.js
. Note that this library can only be used within applications that open in frames in the Bitrix24 user interface. Read more about this in the section on
widgets
.
JavaScript Using B24JsSDK
JavaScript Using B24JsSDK
Unlike bx24.js, B24JsSDK can be used in any web applications, both as front-end and back-end on Node.js.
This distinction requires a slightly different approach to including the library. Detailed information can be found in
Installation and Usage of B24JsSDK
. Here is an example of including B24JsSDK as a browser UMD library:
<
script
src
=
"https://unpkg.com/@bitrix24/b24jssdk@latest/dist/umd/index.min.js"
>
</
script
>
After including, the library will be available through the global variable
B24Js
. The example below assumes that the code is used within applications that open in frames in the Bitrix24 user interface:
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
`New Deal`
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
The library also supports working with incoming webhooks. However, in this case, it should be used on the back-end in Node.js. Calling the REST API using an incoming webhook from the front-end is unsafe, as any user who opens such an application can see the webhook and use it for unauthorized access to Bitrix24 with the rights of the user who created the webhook.
PHP Using B24PhpSDK
PHP Using B24PhpSDK
To start using it, you need to install and include B24PhpSDK. Detailed information can be found in
Loading and Using B24PhpSDK
.
Example of using B24PhpSDK with an incoming webhook:
declare
(strict_types=
1
);
// Include the base SDK class
use
Bitrix24
\
SDK
\
Services
\
ServiceBuilderFactory
;
// ensure the path to autoload.php is correct. It may be different if
// you are using your own folder structure
require_once
'vendor/autoload.php'
;
$B24
=
ServiceBuilderFactory
::
createServiceBuilderFromWebhook
(
'--insert your webhook code here--'
);
$result
=
$B24
->
getCRMScope
()->
deal
()->
add
([
'TITLE'
=>
'New Deal'
,
'TYPE_ID'
=>
'SALE'
,
'STAGE_ID'
=>
'NEW'
])->
getId
();
PHP Using CRest SDK
PHP Using CRest SDK
To use the PHP examples, you need to install and include the CRest SDK. Detailed information can be found in
Loading and Using CRest PHP SDK
.
Example of using CRest SDK:
require_once
(
'crest.php'
);
// include CRest PHP SDK
// make a request to the REST API
$result
=
CRest
::
call
(
'crm.deal.add'
,
[
'fields'
=> [
'TITLE'
=>
'New Deal'
,
'TYPE_ID'
=>
'SALE'
,
'STAGE_ID'
=>
'NEW'
]
]
);
// Process the response from Bitrix24
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
}
else
{
print_r
(
$result
[
'result'
]);
}
Copied
Was the article helpful?
Yes
No
Previous
How to Make Your First API Request
Next
Ready-to-use REST API scenarios

---

## REST API Limits

**Source:** https://apidocs.bitrix24.com/limits

REST API Limits | Bitrix24 REST API and Marketplace Applications
Request Intensity Limits
REST API Limits
Request Intensity Limits
What to Do If You Need to Make Many Requests?
Resource Consumption Limits
The limits on request intensity and resource consumption described in this section apply to the cloud version of Bitrix24. On-premise installations can independently manage the load generated by REST requests through their own server settings.
The restrictions on the REST API in the cloud version are implemented to regulate overall load—ensuring that a specific Bitrix24, which inefficiently uses automation resources, does not create problems for other users of the service.
Request Intensity Limits
Request Intensity Limits
The limit on request intensity to Bitrix24 is implemented based on the Leaky Bucket Algorithm. This allows applications to temporarily make requests very intensively while preventing them from doing so continuously.
Here's how it works:
Each incoming request from an application increases a conditional "request counter" on the Bitrix24 side.
Once the "counter" value exceeds the threshold value X, each subsequent incoming request is blocked. The application receives a status
503
with the error code
QUERY_LIMIT_EXCEEDED
in response.
Simultaneously, the counter value automatically decreases by Y every second.
From the logic of this mechanism, two conclusions can be drawn:
If your application makes no more than Y requests per second, it will never encounter the
QUERY_LIMIT_EXCEEDED
error.
If the nature of your application requires making many requests temporarily, this is possible. There is no restriction stating "you cannot make more than Y requests per second." You can make a significant number of requests per second, just not continuously. For example, this occurs in integrations with telephony when several incoming calls happen simultaneously for reasons beyond the application's control.
The threshold values X and Y mentioned above depend on the tariff plan.
Tariff
Counter Decrease Rate
,
Y
Limit Before Blocking
,
X
Enterprise
5 per sec
250
Others
2 per sec
50
Important Features
It is important to know that request intensity is tracked separately for each Bitrix24 account. In other words, if your application uses REST too intensively on one account and hits the limits, it will not affect the application's operation on another account. This means that users on different accounts can use your solutions with varying intensity, allowing you to make the application logic quite flexible.
On the other hand, Bitrix24 only considers the IP address from which the REST request is made. In other words, if your server hosts several applications that all work with the same Bitrix24, the request intensity limit will be shared among all applications. Keep this feature in mind when designing.
What to Do If You Need to Make Many Requests?
What to Do If You Need to Make Many Requests?
In fact, the REST API limits in Bitrix24 are quite lenient for products of its class. Even making 2 requests per second allows for 172,800 requests per day on the account. As you may have understood from the description of the limitation mechanism, Bitrix24 allows for more requests.
Moreover,
request
does not equal
record
.
In particular, to retrieve data from Bitrix24, you can almost always use list methods *.list, which return 50 records per request. In other words, with the same minimal intensity of 2 requests per second, you can retrieve 8,640,000 leads or deals from Bitrix24 in a day.
Additionally, the Bitrix24 REST API has a batch method that allows you to execute 50 requests in one hit. The counter will increase by one, while the application effectively performs 50 different REST requests.
Using batch, where 50 requests to list methods *.list are executed sequentially, allows you to retrieve 2,500 records from Bitrix24 in one hit (50 requests with 50 records each). With this approach, you can obtain 432,000,000 records in a day.
Of course, it should be noted that besides request intensity, resource consumption limits also come into play in such cases, and in practice, you are unlikely to be able to retrieve such volumes of data in such a short time. Overall, REST as an approach is not designed for such mass and intensive data exchange. This is why a completely different mechanism is used in Bitrix24 for the built-in BI connector, which is intended for obtaining large data sets.
Nevertheless, combining batch with list methods and properly accounting for request intensity successfully addresses the overwhelming majority of tasks faced by developers.
Resource Consumption Limits
Resource Consumption Limits
In the cloud version of Bitrix24, all REST request responses include an array
time
with additional information about the request execution time, which now has an additional key
operating
that indicates the execution time for a specific method.
For example:
{
...
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
The execution time data for each individual method is summed.
Triggering Limits
If the total execution time for requests exceeds 480 seconds within a 10-minute period, this method is blocked for all applications and webhooks of that account. All other methods continue to operate.
The key
operating_reset_at
returns the time in
timestamp
format when a portion of the limit for that method will be released.
The described metrics are calculated within Bitrix24 and depend on a number of interdependent factors: the volume of data in the account, the intensity of user interactions with the account, and other applications, etc.
The same request on different accounts can yield different
operating
values simply because, on one account, Bitrix24 has to process 10 records to get a result, while on another, it has to process 10,000 records. In other words, the resource consumption of your request is unpredictable on the application side.
However, there are
a number of recommendations
that you can follow to reduce the risks of triggering resource consumption limits.
Copied
Was the article helpful?
Yes
No
Previous
How to Update and Delete Files
Next
Error Codes

---

## Error Codes

**Source:** https://apidocs.bitrix24.com/error-codes

Error Codes | Bitrix24 REST API and Marketplace Applications
Error Codes
Error Codes
To handle errors that occur during request execution, it is necessary to analyze the HTTP response status or the presence of a special JSON structure in the response:
{
"error"
:
"ERROR_HANDLER_ALREADY_EXIST"
,
"error_description"
:
"Handler already exists!"
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
A list of specific error codes that occur when calling a particular REST API method is described for each method separately. There is also a list of system errors that are independent of the logic of a specific REST API request.
Statuses and Codes of System Errors
Statuses and Codes of System Errors
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
Was the article helpful?
Yes
No
Previous
REST API Limits
Next
Meetups for Developers

---

## Meetups, Broadcasts, and Recordings for Developers

**Source:** https://apidocs.bitrix24.com/meetups

Meetups, Broadcasts, and Recordings for Developers | Bitrix24 REST API and Marketplace Applications
CRM Timeline Widgets, Integrating E-Signing Solutions  - Episode 9 of Bitrix24 REST API Series
Meetups, Broadcasts, and Recordings for Developers
CRM Timeline Widgets, Integrating E-Signing Solutions  - Episode 9 of Bitrix24 REST API Series
Bitrix24 Vibe: Custom Widgets for Start Page - Episode 8 of Bitrix24 REST API Series
B24PHPSDK Quick Start, local application with token storage - Episode 7 of Bitrix24 REST API Series
B24PHPSDK Quick Start, local application - Episode 6 of Bitrix24 REST API Series
B24PHPSDK Quick Start, Incoming Webhook - Episode 5 of Bitrix24 REST API Series
Offline events - Episode 4 of Bitrix24 REST API Series
Automation rules & triggers - Episode 3 of Bitrix24 REST API Series
Widgets, Tips and Tricks - Episode 2 of Bitrix24 REST API Series
CRM Timeline Widgets, Integrating E-Signing Solutions  - Episode 9 of Bitrix24 REST API Series
CRM Timeline Widgets, Integrating E-Signing Solutions  - Episode 9 of Bitrix24 REST API Series
Example:
Github
B24PHPSDK:
GitHub
Bitrix24 Vibe: Custom Widgets for Start Page - Episode 8 of Bitrix24 REST API Series
Bitrix24 Vibe: Custom Widgets for Start Page - Episode 8 of Bitrix24 REST API Series
Example:
Github
B24PHPSDK:
GitHub
B24PHPSDK Quick Start, local application with token storage - Episode 7 of Bitrix24 REST API Series
B24PHPSDK Quick Start, local application with token storage - Episode 7 of Bitrix24 REST API Series
Example:
Github
B24PHPSDK:
GitHub
B24PHPSDK Quick Start, local application - Episode 6 of Bitrix24 REST API Series
B24PHPSDK Quick Start, local application - Episode 6 of Bitrix24 REST API Series
Example:
Github
B24PHPSDK:
GitHub
B24PHPSDK Quick Start, Incoming Webhook - Episode 5 of Bitrix24 REST API Series
B24PHPSDK Quick Start, Incoming Webhook - Episode 5 of Bitrix24 REST API Series
Example:
Github
B24PHPSDK:
GitHub
Offline events - Episode 4 of Bitrix24 REST API Series
Offline events - Episode 4 of Bitrix24 REST API Series
Speaker:
Serg Vostrikov, the Head of Market and integrations unit
Automation rules & triggers - Episode 3 of Bitrix24 REST API Series
Automation rules & triggers - Episode 3 of Bitrix24 REST API Series
Speaker:
Serg Vostrikov, the Head of Market and integrations unit
Widgets, Tips and Tricks - Episode 2 of Bitrix24 REST API Series
Widgets, Tips and Tricks - Episode 2 of Bitrix24 REST API Series
Speaker:
Serg Vostrikov, the Head of Market and integrations unit
Was the article helpful?
Yes
No
Previous
Error Codes
Next
Support and Community for Developers

---

## Support and Community for Developers

**Source:** https://apidocs.bitrix24.com/support

Support and Community for Developers | Bitrix24 REST API and Marketplace Applications
Where to Get Help?
Support and Community for Developers
Where to Get Help?
Technical Support
Questions About Documentation
Where to Get Help?
Where to Get Help?
We strive to enhance our developer documentation by providing practical examples for the most common tasks related to using the Bitrix24 REST API.
In addition to the documentation, you can seek advice and assistance from other developers in the open chat:
B24 REST and Apps
. This chat discusses questions related to using the REST API and creating local and mass-market solutions.
How to Ask Questions in Chats
If you are joining these chats for the first time, it’s advisable to follow some simple guidelines:
Before asking a question, try to search for the necessary information in the documentation or through search engines. Chat participants are not search engines to do this for you.
Attempt various solutions to your problem. Even if you don't fully succeed, you will be able to articulate your issue more specifically, making the conversation more effective.
Try to ask specific technical questions. It’s difficult to respond to a question like "I can't add a button in Bitrix24, what should I do?". It’s easy to answer a question like "I registered a widget handler in CRM_DEAL_DETAIL_TAB from a local application, checked the presence of the widget with a request to the placement.list method, but users accessing the deal detail form do not see my widget."
If you believe that a method is not working as expected or as it did previously, provide an example request with the parameters you passed to the method and show the response from the REST API. The issue is always with the data. Until you explain how you specifically used the method, no one will be able to help you.
News, tips, and recommendations for developers of mass-market solutions can always be found in the
Bitrix24.Market Live
channel.
Technical Support
Technical Support
Support is provided to developers of
mass-market solutions
in the developer's area, where you can address both technical issues related to the REST API and questions regarding the placement of solutions in the Bitrix24 Market.
For questions regarding the Bitrix24 REST API, you can contact
technical support
.
Questions About Documentation
Questions About Documentation
All of this documentation is stored in the
GitHub repository
. If any articles raise questions, you can add relevant
issues
directly there. We strive to respond to them or make changes to the documentation to improve clarity.
You can also help others by correcting errors in the documentation, adding useful edits, or even entire articles through a
pull request
.
You can easily make edits to the article you are reading by clicking the edit button located in the upper right corner of any documentation page:
Learn more about how to
make changes to the documentation
.
Become a contributor to the documentation, share your invaluable experience using the Bitrix24 REST API, and other developers following in your footsteps will be grateful, and your name will forever be etched in the documentation commits!
Was the article helpful?
Yes
No
Previous
Meetups for Developers
Next
Feedback

---

## Feedback

**Source:** https://apidocs.bitrix24.com/feedback

Feedback | Bitrix24 REST API and Marketplace Applications
Feedback
Feedback
All of this documentation is stored in the
GitHub repository
. If you have any questions about specific articles, you can add the relevant
issues
right there. We strive to respond to them or make changes to the documentation to enhance its clarity.
Was the article helpful?
Yes
No
Previous
Support and Community for Developers

---

