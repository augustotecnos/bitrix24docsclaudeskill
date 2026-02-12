---
description: API call settings, performance, interactivity, cloud vs on-premise
methods:
- crm.deal.add
- crm.deal.add.json
- crm.item.list
- crm.lead.add
- crm.lead.add.json
- crm.lead.list
- event.add
- user.current
- user.search
pages: 22
title: API call settings, performance, interactivity, cloud vs on-premise
---
# API call settings, performance, interactivity, cloud vs on-premise
> API call settings, performance, interactivity, cloud vs on-premise
> **22 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Setting Up and Using the REST API](#setting-up-and-using-the-rest-api)
- [How to Call REST API Methods](#how-to-call-rest-api-methods)
- [Authorization in REST](#authorization-in-rest)
- [How to Make a Request](#how-to-make-a-request)
- [Data Encoding](#data-encoding)
- [Features of List Methods](#features-of-list-methods)
- [How to Execute Batch Requests](#how-to-execute-batch-requests)
- [Features of REST Calls When Changing the Bitrix24 Address](#features-of-rest-calls-when-changing-the-bitrix24-)
- [Interactive Applications](#interactive-applications)
- [Push&Pull in the Browser](#pushpull-in-the-browser)
- [Custom Push&Pull Client](#custom-pushpull-client)
- [Push&Pull](#pushpull)
- [Organize Instant Communications within Applications pull.application.config.get](#organize-instant-communications-within-application)
- [Send Events to the RT Channel of the pull.application.event.add](#send-events-to-the-rt-channel-of-the-pullapplicati)
- [Send push notifications to a mobile device using the method pull.application.push.add](#send-push-notifications-to-a-mobile-device-using-t)
- [General Recommendations](#general-recommendations)
- [Limits](#limits)
- [Incoming Event Queue](#incoming-event-queue)
- [Retrieve Large Volumes of Data](#retrieve-large-volumes-of-data)
- [Differences in Using REST API in Cloud and On-Premise Bitrix24](#differences-in-using-rest-api-in-cloud-and-on-prem)
- [Required Network Access](#required-network-access)
- [Security Recommendations for Applications Using REST API](#security-recommendations-for-applications-using-re)

---

## Setting Up and Using the REST API

**Source:** https://apidocs.bitrix24.com/settings/index

Setting Up and Using the REST API | Bitrix24 REST API and Marketplace Applications
Configure REST Calls
Setting Up and Using the REST API
Configure REST Calls
Perform Authorization
Install and Configure the Application
Configure Application Operation in the Cloud and On-Premise
Implement an Interactive Interface and Instant Events
Optimize Performance Under Load
This section contains answers to practical questions that arise during integration development:
how to securely access the REST,
configure different types of applications,
optimize load.
To make your first request, check out the
Getting Started
section.
To find a specific REST API method, use the
Method Reference
.
Configure REST Calls
Configure REST Calls
Review materials that explain how to form requests, encode data, and handle sequential queries.
What a basic request looks like and how response formats differ —
How to Make a Request
.
How to perform sequential method calls and pass results between requests —
How to Execute a Batch of Requests
.
What to do if parameters contain special characters —
Data Encoding
.
How to properly retrieve lists and work with the
start
parameter —
Features of List Methods
.
Why a request stopped working after changing the domain and how to handle redirects —
Features of REST Calls When Changing the Bitrix24 Address
.
Perform Authorization
Perform Authorization
Choose an authorization method — from simple webhooks to a full OAuth 2.0 cycle, set up automatic token renewal and error handling.
How webhooks and the OAuth protocol differ —
Authorization in REST
.
How OAuth authorization works step by step —
Complete OAuth 2.0 Authorization Protocol
.
How to perform authorization directly in the application interface or through the installation event —
Simplified Token Acquisition
.
How to avoid losing access overnight and when to refresh the
refresh_token
—
Automatic Renewal of OAuth 2.0 Tokens
.
How to deal with errors like
invalid_client
,
insufficient_scope
, and others —
Error Codes
.
Install and Configure the Application
Install and Configure the Application
Choose the appropriate scenario and follow the instructions for local, mass-market, or configuration solutions.
Select the suitable application option —
Application Installation Options in Bitrix24
.
How to add a local application —
Overview of Installing Local Applications
.
How to create and install a mass-market solution —
Overview of Installing Mass-Market Applications
.
When to call
installFinish
and what to check before launching —
Completing Application Installation
.
How to publish ready-made sites, industry CRMs, and smart scenarios —
Installing Site Templates
,
Installing Industry CRMs
,
Installing Solutions with Smart Scenarios
.
What data is deleted when an application is removed and how to handle the deletion event —
Uninstalling Applications
.
Configure Application Operation in the Cloud and On-Premise
Configure Application Operation in the Cloud and On-Premise
Compare the requirements of the cloud and on-premise versions, configure the network, and expand the API if necessary.
What is important to consider for the application to work in the on-premise version —
Differences in Using the REST API
.
Why a method may be unavailable —
Versioning of Modules in On-Premise Bitrix24
.
Which domains to open and where to get the list of IPs for event queues —
Required Network Access
.
What to do if the corporate network is isolated and you need to replace the authorization server —
Application Authorization in Isolated On-Premise Bitrix24
.
How to add your own methods and new scopes —
Adding Custom Methods to the On-Premise Bitrix24 REST API
.
What security requirements to consider during development —
Security Recommendations for Applications Using the REST API
.
Implement an Interactive Interface and Instant Events
Implement an Interactive Interface and Instant Events
Use Push & Pull to instantly respond to user actions in the interface.
What interactive options are available —
Interactive Applications
.
How to create and configure your own Push & Pull client —
Custom Push & Pull Client
.
Which methods to use to get connection parameters and send push events —
Push & Pull
.
Optimize Performance Under Load
Optimize Performance Under Load
Apply recommendations for optimizing requests, working with queues, and controlling limits.
How to reduce the number of requests and speed up responses —
General Recommendations
.
How to export thousands of items and avoid counting the total —
Retrieve Large Volumes of Data
.
How to build an incoming queue and protect handlers from spikes —
Incoming Event Queue
.
What limitations apply to the REST API —
Limits
.
Copied
Was the article helpful?
Yes
No
Previous
MCP Server for AI
Next
How to Call REST API Methods

---

## How to Call REST API Methods

**Source:** https://apidocs.bitrix24.com/settings/how-to-call-rest-api/index

How to Call REST API Methods | Bitrix24 REST API and Marketplace Applications
How to Call REST API Methods
How to Call REST API Methods
Authorization in REST
How to Execute Batch Requests
Features of REST Calls When Changing the Bitrix24 Address
Data Encoding
How to Make a Request
Features of List Methods
Was the article helpful?
Yes
No
Previous
Section Overview
Next
Authorization in REST

---

## Authorization in REST

**Source:** https://apidocs.bitrix24.com/settings/how-to-call-rest-api/authorization

Authorization in REST | Bitrix24 REST API and Marketplace Applications
Authorization in REST
Authorization in REST
Local Incoming Webhooks
Local and Mass-Market Applications Using OAuth 2.0
The Bitrix24 REST API is an API that can be accessed by making HTTP requests to specific addresses of a particular Bitrix24 account. In fact, such requests can be made from any software that supports the HTTP protocol.
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
"auth": "YOUR_ACCESS_TOKEN"
}'
\
https://your-domain.bitrix24.com/rest/crm.deal.add.json
In addition to the parameters of a specific method, it is necessary to pass some authorization data when making a request, without which the request will be considered unauthorized and blocked by Bitrix24.
Moreover, REST API methods are always called "on behalf of" a specific user of the Bitrix24 account. Essentially, the entire REST API is another way to use the existing functionality of Bitrix24, where the user directly accesses the product's functionality instead of using the user interface, calling various REST API methods.
There are two options for passing authorization data in requests to the REST API:
Specifying a permanent incoming local webhook code;
Specifying a temporary OAuth 2.0 authorization token, which is used in local and mass-market applications.
Local Incoming Webhooks
Local Incoming Webhooks
Example of accessing the REST API using an incoming local webhook:
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
https://your-domain.bitrix24.com/rest/1/8g9l071eismy9q2l/crm.deal.add.json
In this example, the following is specified:
The address of a specific Bitrix24 account (
your-domain.bitrix24.com
);
The user ID of the person who created the webhook (
1
);
The secret code of the webhook (
8g9l071eismy9q2l
);
The REST API method that adds a deal to the CRM (
crm.deal.add
).
The values of the method parameters (
fields
) were passed as a POST request.
In fact, "authorization" in this way of accessing the REST API is the user ID and the secret code of the webhook.
Webhooks are ideal for:
Organizing one-time data import-export;
Simple integrations with external and internal company systems (ERP, time tracking, auto-monitoring of software and hardware, etc.);
Use in automating the processing of leads and deals (triggers and actions in CRM automation rules);
Using webhooks is simpler for technical implementation, as it does not require the implementation of the OAuth 2.0 protocol. Each user can add webhooks "for themselves," and the REST API called within such webhooks will be limited to the rights of the specific user-owner.
You can learn more about webhooks in the
corresponding lesson
of our video course for developers.
Local and Mass-Market Applications Using OAuth 2.0
Local and Mass-Market Applications Using OAuth 2.0
Example of accessing the REST API using a temporary authorization token:
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
"auth": "807ca26600631fce00007a4b00000001f0f107255033363e91ab16442bd901b2571ed9"
}'
\
https://your-domain.bitrix24.com/rest/crm.deal.add.json
In this example, the following is specified:
The address of a specific Bitrix24 account (
your-domain.bitrix24.com
);
The REST API method that adds a deal to the CRM (
crm.deal.add
);
The authorization token specified in the
auth
parameter (
807ca26600631fce00007a4b00000001f0f107255033363e91ab16442bd901b2571ed9
).
The values of the method parameters (
fields
) were passed as a POST request.
"Authorization" in this way of accessing the REST API is the token specified in the
auth
parameter. It contains a number of important system values, including the ID of the specific Bitrix24 user on behalf of whom the REST API is being accessed.
You can learn how local and mass-market applications obtain authorization tokens in the
corresponding section
of the documentation.
Local applications
, unlike local webhooks, are better suited for tasks that require creating a user interface:
Various reports;
Additional auto-handlers within specific business logic;
Solutions that require user access management;
Chatbots and applications that extend the functionality of the Bitrix24 messenger;
Additional operations for automated Bitrix24 workflows.
Local applications support all capabilities of the REST API and call REST using the OAuth 2.0 authorization protocol, but are installed only on a specific Bitrix24 account, without publication in the solutions catalog. Administrative access is required to add a local application.
Mass-market solutions
are published in our
application catalog
. They are available for installation to an unlimited number of users, and moreover, you can make them paid, selling their functionality on a subscription model.
Unlike the development of local applications for a specific project or client, where the relationship between the developer and the user is governed by their bilateral agreements, the publication of mass-market solutions in the Bitrix24 Marketplace catalog is regulated by Bitrix24 rules, which you will need to familiarize yourself with carefully.
Copied
Was the article helpful?
Yes
No
Previous
How to Call REST API Methods
Next
How a Request is Made

---

## How to Make a Request

**Source:** https://apidocs.bitrix24.com/settings/how-to-call-rest-api/general-principles

How to Make a Request | Bitrix24 REST API and Marketplace Applications
Request Result
How to Make a Request
As already mentioned in the article about
authorization in REST API
, a request to the REST API method is an HTTP request to a specific address of a particular Bitrix24 in the following format:
https://your-domain.bitrix24.com/rest/method-name?param1=value1&param2=value2....
Most methods support passing an array of parameters as a
POST
request in
JSON
format. All methods support the
GET
protocol and
POST
in
multipart/form-data
format.
In response to a request, the REST API returns the result in
JSON
or
XML
format depending on what the user requested, containing meaningful data or
error information
. We recommend trying to
make a simple request
before you start exploring the Bitrix24 REST API in depth.
Request Result
Request Result
The default response format is
JSON
, but it is possible to receive a response in
XML
format if necessary. To do this, you need to add the desired format to the name of the REST method:
.json
or
.xml
.
Please note the result of
batch
in both variations:
batch (json)
batch (xml)
Request:
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{
"halt": 0,
"cmd": {
"get_user": "user.current"
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/batch
Result:
{
"result"
:
{
"result"
:
{
"get_user"
:
{
"ID"
:
"1"
,
"ACTIVE"
:
true
,
"NAME"
:
"Administrator"
,
"LAST_NAME"
:
"Fusion"
,
"EMAIL"
:
"info@efusion.com"
,
"LAST_LOGIN"
:
"2024-08-29T10:29:54+02:00"
,
"DATE_REGISTER"
:
"2023-08-24T03:00:00+02:00"
,
"IS_ONLINE"
:
"Y"
,
"TIMESTAMP_X"
:
"24.08.2023 13:19:39"
,
"LAST_ACTIVITY_DATE"
:
"2024-08-29 10:59:12"
,
"PERSONAL_GENDER"
:
""
,
"PERSONAL_BIRTHDAY"
:
""
,
"UF_EMPLOYMENT_DATE"
:
""
,
"UF_DEPARTMENT"
:
[
1
]
}
}
,
"result_error"
:
[
]
,
"result_total"
:
[
]
,
"result_next"
:
[
]
,
"result_time"
:
{
"get_user"
:
{
"start"
:
1724918931.686765
,
"finish"
:
1724918931.689633
,
"duration"
:
0.0028679370880126953
,
"processing"
:
0.0027151107788085938
,
"date_start"
:
"2024-08-29T11:08:51+02:00"
,
"date_finish"
:
"2024-08-29T11:08:51+02:00"
}
}
}
,
"time"
:
{
"start"
:
1724918931.634301
,
"finish"
:
1724918931.689674
,
"duration"
:
0.05537295341491699
,
"processing"
:
0.0031290054321289062
,
"date_start"
:
"2024-08-29T11:08:51+02:00"
,
"date_finish"
:
"2024-08-29T11:08:51+02:00"
}
}
Request:
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{
"halt": 0,
"cmd": {
"get_user": "user.current"
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/batch.xml
Result:
<
response
>
<
result
>
<
result
>
<
get_user
>
<
ID
>
1
</
ID
>
<
ACTIVE
>
1
</
ACTIVE
>
<
NAME
>
Administrator
</
NAME
>
<
LAST_NAME
>
Fusion
</
LAST_NAME
>
<
EMAIL
>
info@efusion.com
</
EMAIL
>
<
LAST_LOGIN
>
2024-08-29T10:29:54+02:00
</
LAST_LOGIN
>
<
DATE_REGISTER
>
2023-08-24T03:00:00+02:00
</
DATE_REGISTER
>
<
IS_ONLINE
>
Y
</
IS_ONLINE
>
<
TIMESTAMP_X
>
24.08.2023 13:19:39
</
TIMESTAMP_X
>
<
LAST_ACTIVITY_DATE
>
2024-08-29 10:59:12
</
LAST_ACTIVITY_DATE
>
<
PERSONAL_GENDER
>
</
PERSONAL_GENDER
>
<
PERSONAL_BIRTHDAY
>
</
PERSONAL_BIRTHDAY
>
<
UF_EMPLOYMENT_DATE
>
</
UF_EMPLOYMENT_DATE
>
<
UF_DEPARTMENT
>
<
item
>
1
</
item
>
</
UF_DEPARTMENT
>
</
get_user
>
</
result
>
<
result_error
>
</
result_error
>
<
result_total
>
</
result_total
>
<
result_next
>
</
result_next
>
<
result_time
>
<
get_user
>
<
start
>
1724918984.0348
</
start
>
<
finish
>
1724918984.0386
</
finish
>
<
duration
>
0.0037539005279541
</
duration
>
<
processing
>
0.0035719871520996
</
processing
>
<
date_start
>
2024-08-29T11:09:44+02:00
</
date_start
>
<
date_finish
>
2024-08-29T11:09:44+02:00
</
date_finish
>
</
get_user
>
</
result_time
>
</
result
>
<
time
>
<
start
>
1724918983.9771
</
start
>
<
finish
>
1724918984.0386
</
finish
>
<
duration
>
0.06153392791748
</
duration
>
<
processing
>
0.0040559768676758
</
processing
>
<
date_start
>
2024-08-29T11:09:43+02:00
</
date_start
>
<
date_finish
>
2024-08-29T11:09:44+02:00
</
date_finish
>
</
time
>
</
response
>
Note
JSON
is the primary response format. There is no need to append
.json
to the name of each method.
Copied
Was the article helpful?
Yes
No
Previous
Authorization in REST
Next
Data Encoding

---

## Data Encoding

**Source:** https://apidocs.bitrix24.com/settings/how-to-call-rest-api/data-encoding

Data Encoding | Bitrix24 REST API and Marketplace Applications
Basic Information
Data Encoding
Basic Information
Double URL Encoding
Encoding Complex Structures
Order of Parameters
Basic Information
Basic Information
Depending on the tool that generates and sends REST requests to the server, and the data being transmitted, it may be necessary to encode URL parameters; otherwise, the result of the method call will be unpredictable.
For example, suppose the task is to create a lead in the CRM with the name "John&Martin" via an incoming webhook. The full URL of the request according to the documentation for the method
crm.lead.add
looks like this:
https://b24-abcdef.bitrix24.com/rest/1/xxxxxxx/crm.lead.add?fields[TITLE]=John&Martin
After executing the request in any desired way (in a browser, in the command line with cURL, or via a script), you may find that the created lead's name does not match the request—it only shows "John." This happened because the lead's name contains the
&
symbol, which has a special meaning in URLs: it is used to separate request parameters.
As a result, the request formed two parameters—
fields[TITLE]
with the value
John
and a new parameter
Martin
with an empty value.
To ensure that Bitrix24 (and any web server in the world) understands that the ampersand is not a special character but part of the value, it must be converted to the sequence
%26
. The correct URL for the task will look like this:
https://b24-abcdef.bitrix24.com/rest/1/xxxxxxx/crm.lead.add?fields[TITLE]=John%26Martin
This transformation is called URL encoding. There are many characters that can appear in the value of a parameter but have a special role in URLs and "break" the request:
&
,
?
,
%
,
[
, etc. To ensure the request is formed correctly, all parameter values must be URL-encoded. Each programming language has a function for this transformation:
Javascript -
encodeURIComponent
;
PHP -
urlencode
;
Python -
urllib.quote_plus
;
another language - search for "my_language url encoding" or "my_language url encode."
If the request is being formed manually without using a programming language, you should use any service found by searching for "url encoding online."
Tip
You can check the correctness of the request formation using request testing services—such as
https://webhook.site
. It allows you to view each sent request, its headers, and the transmitted parameters in a convenient interface. Such services do not check the correctness of parameters concerning a specific REST API method but can help identify more general issues, like the one mentioned above.
Double URL Encoding
Double URL Encoding
When using the
batch
method, an array of requests is passed in the
cmd
parameter in the form of "method?parameter1=value&parameter2=7," which is practically how these requests would look
individually
, just without the first part of the address.
However, since such a URL becomes the value of a request parameter, it also needs to be URL-encoded. This means that first, as usual, the values of the request parameters must be URL-encoded, and then each request must be encoded as well, since they are now values of the
cmd
parameter of the
batch
request.
If we needed to create a lead from the example above as part of a batch request, the URL would look like this:
https://b24-abcdef.bitrix24.com/rest/1/xxxxxxx/batch?cmd[0]=crm.lead.add%3Ffields%5BTITLE%5D%3DJohn%2526Martin
Encoding Complex Structures
Encoding Complex Structures
Note
Generally speaking, to avoid such complexities, we strongly recommend using ready-made SDKs for working with the REST API. Such libraries automatically encode data, handle errors, simplify working with the API, and allow you to focus on the business logic of the application.
Bitrix24 offers developers several SDKs for working with the REST API in different programming languages:
B24PhpSdk
and
CRest PHP SDK
for PHP;
B24JsSDK
for JavaScript;
When accessing the API, it is often necessary to pass a nested data structure—an object of significant depth, an array within an object, an array of objects. The simplest way to do this is to perform a POST request with the data transmitted in JSON format:
cURL
PHP
Javascript
Python
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{
"fields": {
"TITLE": "My company",
"PHONE": [
{
"VALUE": "112233",
"VALUE_TYPE": "WORK"
},
{
"VALUE": "555888112",
"VALUE_TYPE": "OTHER"
}
]
}
}'
\
https://***/rest/***/crm.lead.add
$data
= [
"fields"
=> [
"TITLE"
=>
"My company"
,
"PHONE"
=> [
[
"VALUE"
=>
"112233"
,
"VALUE_TYPE"
=>
"WORK"
],
[
"VALUE"
=>
"555888112"
,
"VALUE_TYPE"
=>
"OTHER"
]
]
]
];
$ch
=
curl_init
();
curl_setopt
(
$ch
, CURLOPT_USERAGENT,
'php script'
);
curl_setopt
(
$ch
, CURLOPT_HEADER,
false
);
curl_setopt
(
$ch
, CURLOPT_RETURNTRANSFER,
true
);
curl_setopt
(
$ch
, CURLOPT_TIMEOUT,
5
);
curl_setopt
(
$ch
, CURLOPT_URL,
'https://***/rest/***/crm.lead.add'
);
curl_setopt
(
$ch
, CURLOPT_HTTPHEADER, [
'Content-Type: application/json'
]);
curl_setopt
(
$ch
, CURLOPT_POST,
1
);
curl_setopt
(
$ch
, CURLOPT_POSTFIELDS,
json_encode
(
$data
));
$raw
=
curl_exec
(
$ch
);
curl_close
(
$ch
);
data = {
fields
: {
TITLE
:
'My company'
,
PHONE
: [
{
VALUE
:
'112233'
,
VALUE_TYPE
:
'WORK'
},
{
VALUE
:
'555888112'
,
VALUE_TYPE
:
'OTHER'
}
]
}
};
fetch
(
'https://***/rest/***/crm.lead.add'
, {
method
:
'POST'
,
headers
: {
'Content-Type'
:
'application/json'
},
body
:
JSON
.
stringify
(data)
});
import
requests
data = {
'fields'
: {
'TITLE'
:
'My company'
,
'PHONE'
: [
{
'VALUE'
:
'112233'
,
'VALUE_TYPE'
:
'WORK'
},
{
'VALUE'
:
'555888112'
,
'VALUE_TYPE'
:
'OTHER'
}
]
}
}
r = requests.post(
'https://***/rest/***/crm.lead.add'
, json=data)
If sending JSON is not possible, the data can be sent via a GET or POST request. The GET request from the example above would look like this:
https://***/rest/***/crm.lead.add.json?fields[TITLE]=My%20company&fields[PHONE][0][VALUE]=112233&fields[PHONE][0][VALUE_TYPE]=WORK&fields[PHONE][1][VALUE]=555888112&fields[PHONE][1][VALUE_TYPE]=OTHER
In PHP, you can obtain a similar string from an array using the
http_build_query
function, while in JS, you can use third-party solutions (for example, the library
qs
).
When sending a POST request, it is necessary to specify the
Content-Type
of the sent data—
application/x-www-form-urlencoded
or
multipart/form-data; boundary=SomeBoundary
—and encode the data accordingly. Examples of request bodies:
application/x-www-form-urlencoded
multipart/form-data
fields[TITLE]=My%20company&fields[PHONE][0][VALUE]=112233&fields[PHONE][0][VALUE_TYPE]=WORK&fields[PHONE][1][VALUE]=555888112&fields[PHONE][1][VALUE_TYPE]=OTHER
--SomeBoundary
Content-Disposition: form-data; name="fields[TITLE]"
My company
--SomeBoundary
Content-Disposition: form-data; name="fields[PHONE][0][VALUE]"
112233
--SomeBoundary
Content-Disposition: form-data; name="fields[PHONE][0][VALUE_TYPE]"
WORK
--SomeBoundary
Content-Disposition: form-data; name="fields[PHONE][1][VALUE]"
555888112
--SomeBoundary
Content-Disposition: form-data; name="fields[PHONE][1][VALUE_TYPE]"
OTHER
--SomeBoundary
Order of Parameters
Order of Parameters
Some methods require strict adherence to the order of parameters in the request (for example,
task.commentitem.add
,
task.checklistitem.complete
).
This means that these parameters must not be passed as named (in PHP as an associative array, in JS as an object); otherwise, the execution result will be unpredictable and may result in an error. They must be presented as an indexed (ordered) array (starting from 0).
Example of
incorrect
comment addition to a task:
cURL
PHP
JS
curl
'https://***/rest/***/task.commentitem.add?TASKID=123&FIELDS[POST_MESSAGE]=test'
CRest
::
call
(
'task.commentitem.add'
,
[
'TASKID'
=>
123
,
'FIELDS'
=> [
'POST_MESSAGE'
=>
'text'
]
]
);
BX24
.
callMethod
(
'task.commentitem.add'
,
{
TASKID
:
123
,
FIELDS
: {
'POST_MESSAGE'
:
'text'
}
}
);
Example of
correct
comment addition to a task:
cURL
PHP
JS
curl
'https://***/rest/***/task.commentitem.add?0=123&1[POST_MESSAGE]=test'
CRest
::
call
(
'task.commentitem.add'
,
[
123
,
[
'POST_MESSAGE'
=>
'text'
]
]
);
BX24
.
callMethod
(
'task.commentitem.add'
,
[
123
,
{
'POST_MESSAGE'
:
'text'
}
]
);
Copied
Was the article helpful?
Yes
No
Previous
How a Request is Made
Next
Features of List Methods

---

## Features of List Methods

**Source:** https://apidocs.bitrix24.com/settings/how-to-call-rest-api/list-methods-pecularities

Features of List Methods | Bitrix24 REST API and Marketplace Applications
Features of List Methods
Features of List Methods
In the REST API, there are several methods that return lists of entities—lists of deals, users, task comments, etc.
Since the number of returned entities depends on specific conditions and parameters,
Bitrix24
returns them in "batches" of several items (currently no more than 50 at a time).
Example:
https://your-domain.bitrix24.com/rest/crm.item.list?entityTypeId=183&auth=d161f25928c3184678924ec127edd29a
//get a list of all custom CRM entities with ID 183 in JSON format.
When calling list methods, REST returns additional values in the response:
{
"result"
:
result of the method execution
,
"error"
:
error of the method execution
,
"total"
:
total number of records in the response of the list method
,
"next"
:
value to be sent to get the next page of data from the list method
}
To retrieve the next batch of entities, you need to execute the same request, specifying an additional parameter
start
with the value received in the
next
parameter of the response. When using
SDK BX24.js
, obtaining the next batch is done using the method
result.next()
.
Executing list methods can be quite "heavy" in terms of performance for
Bitrix24
, as the volume of processed data can be very large. To ensure your applications stay within the
limits of the REST API
, we recommend
reading the article
.
Copied
Was the article helpful?
Yes
No
Previous
Data Encoding
Next
How to Execute a Batch of Requests

---

## How to Execute Batch Requests

**Source:** https://apidocs.bitrix24.com/settings/how-to-call-rest-api/batch

How to Execute Batch Requests | Bitrix24 REST API and Marketplace Applications
Method Parameters
How to Execute Batch Requests
Method Parameters
Code Examples
Response Handling
Returned Data
Using Results
Who can execute the method: any user
This method is used to send multiple requests in succession, as well as related requests.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
halt
boolean
Determines whether to halt the sequence of requests in case of an error. Defaults to
false
cmd
array
An array of requests in standard format (keep in mind the
URL encoding
of request data; this means that the data for sub-requests must undergo double encoding)
Note
The number of requests in a batch is limited to 50.
The array of requests can have both numeric keys and associative keys. In the parameters of each subsequent request, you can use data from previous requests in the following format:
$result
[request_id][response_field]
where the request identifier is its key in the array of requests.
Starting from version
rest 24.0.0
, nesting is prohibited for the
batch
method (you cannot call another
batch
within a
batch
method call).
Code Examples
Code Examples
cURL (Webhook)
cURL (OAuth)
HTTP (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{
"halt": 0,
"cmd": {
"get_user": "user.current",
"get_department": "department.get?ID=$result[get_user][UF_DEPARTMENT][0]"
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/batch
curl -X POST \
-H
"Content-Type: application/json"
\
-d
'{
"halt": 0,
"cmd": {
"get_user": "user.current",
"get_department": "department.get?ID=$result[get_user][UF_DEPARTMENT][0]"
},
"auth":"**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/batch
https://**put_your_bitrix24_address**/rest/batch?auth=d161f25928c3184678924ec127edd29a&halt=0&cmd[get_user]=user.current%3F&cmd[get_department]=department.get%3FID%3D%2524result%255Bget_user%255D%255BUF_DEPARTMENT%255D
Note
Note
that the parameters are URL-encoded. It is mandatory to encode parameters; otherwise, the correctness of the result is not guaranteed.
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
'$result[get_user][UF_DEPARTMENT][0]'
}
}
},
function
(
result
) {
console
.
log
(
'Raw result: '
, result);
console
.
log
(
'get_user result: '
, result.
get_user
.
data
());
console
.
log
(
'get_department result: '
, result.
get_department
.
data
());
});
More about the
callBatch method in the BX24.JS SDK article
.
$result
=
\CRest
::
callBatch
(
// Commands
[
'get_user'
=> [
'method'
=>
'user.current'
,
'params'
=> []
],
'get_department'
=> [
'method'
=>
'department.get'
,
'params'
=> [
"ID"
=>
'$result[get_user][UF_DEPARTMENT][0]'
]
],
],
// Halt
false
);
echo
"<pre>"
;
var_dump
(
$result
);
echo
"</pre>"
;
Response Handling
Response Handling
Successful Result
Error Example (halt = 0)
Error Example (halt = 1)
{
"result"
: {
"result"
: {
"get_user"
: {
"ID"
:
"1"
,
"ACTIVE"
:
true
,
"NAME"
:
"John"
,
"LAST_NAME"
:
"Dou"
,
"EMAIL"
:
"my@example.com"
,
"LAST_LOGIN"
:
"2024-08-29T10:29:54+02:00"
,
"DATE_REGISTER"
:
"2023-08-24T03:00:00+02:00"
,
"IS_ONLINE"
:
"Y"
,
"TIMESTAMP_X"
:
"24.08.2023 13:19:39"
,
"LAST_ACTIVITY_DATE"
:
"2024-08-29 10:30:11"
,
"PERSONAL_GENDER"
:
""
,
"PERSONAL_BIRTHDAY"
:
""
,
"UF_EMPLOYMENT_DATE"
:
""
,
"UF_DEPARTMENT"
: [
1
]
},
"get_department"
: [
{
"ID"
:
"1"
,
"NAME"
:
"DEMO"
,
"SORT"
:
500
}
]
},
"result_error"
: [],
"result_total"
: {
"get_department"
:
1
},
"result_next"
: [],
"result_time"
: {
"get_user"
: {
"start"
:
1724916859.46156
,
"finish"
:
1724916859.464775
,
"duration"
:
0.0032150745391845703
,
"processing"
:
0.003075838088989258
,
"date_start"
:
"2024-08-29T10:34:19+02:00"
,
"date_finish"
:
"2024-08-29T10:34:19+02:00"
},
"get_department"
: {
"start"
:
1724916859.464944
,
"finish"
:
1724916859.471518
,
"duration"
:
0.006574153900146484
,
"processing"
:
0.005941152572631836
,
"date_start"
:
"2024-08-29T10:34:19+02:00"
,
"date_finish"
:
"2024-08-29T10:34:19+02:00"
}
}
},
"time"
: {
"start"
:
1724916859.421475
,
"finish"
:
1724916859.471588
,
"duration"
:
0.05011296272277832
,
"processing"
:
0.010200977325439453
,
"date_start"
:
"2024-08-29T10:34:19+02:00"
,
"date_finish"
:
"2024-08-29T10:34:19+02:00"
}
}
{
"result"
: {
"result"
: [],
"result_error"
: {
"get_user"
: {
"error"
:
"insufficient_scope"
,
"error_description"
:
""
},
"get_department"
: {
"error"
:
"insufficient_scope"
,
"error_description"
:
""
}
},
"result_total"
: [],
"result_next"
: [],
"result_time"
: []
},
"time"
: {
"start"
:
1724916638.077564
,
"finish"
:
1724916638.132399
,
"duration"
:
0.05483508110046387
,
"processing"
:
0.0017969608306884766
,
"date_start"
:
"2024-08-29T10:30:38+02:00"
,
"date_finish"
:
"2024-08-29T10:30:38+02:00"
}
}
{
"result"
: {
"result"
: [],
"result_error"
: {
"get_user"
: {
"error"
:
"insufficient_scope"
,
"error_description"
:
""
}
},
"result_total"
: [],
"result_next"
: [],
"result_time"
: []
},
"time"
: {
"start"
:
1724916725.460891
,
"finish"
:
1724916725.851307
,
"duration"
:
0.39041590690612793
,
"processing"
:
0.0005991458892822266
,
"date_start"
:
"2024-08-29T10:32:05+02:00"
,
"date_finish"
:
"2024-08-29T10:32:05+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
An object is returned with fields in the form of objects containing the results of the called methods
time
time
Information about the execution time of the request
Using Results
Using Results
Requests executed by the batch method are processed sequentially and can use data obtained from previous requests.
For example, a single execution of the batch method can perform a chain of actions:
BX24
.
callMethod
(
'batch'
,
{
'halt'
:
1
,
'cmd'
: {
'user_by_name'
:
'user.search?NAME=Test2'
,
'user_lead'
:
'crm.lead.add?fields[TITLE]=Test Assigned&fields[ASSIGNED_BY_ID]=$result[user_by_name][0][ID]'
}
},
function
(
result
)
{
console
.
log
(result.
answer
);
}
);
As a result:
user_by_name
— will find a user named
Test2
user_lead
— will create a lead with the responsible user found in
user_by_name
Note
Note
that in the
user_lead
request we use nesting
[0][ID]
. Since the
user.search
method is list-based, it can return up to 50 results, and in this case, we will take the identifier of the first returned user.
Warning
When designing a chain of commands, do not neglect the
halt
key — when enabled, it will stop the execution of the chain if one request in the chain returns an error.
Copied
Was the article helpful?
Yes
No
Previous
Features of List Methods
Next
Features of REST Calls When Changing the Bitrix24 Address

---

## Features of REST Calls When Changing the Bitrix24 Address

**Source:** https://apidocs.bitrix24.com/settings/how-to-call-rest-api/change-domen

Features of REST Calls When Changing the Bitrix24 Address | Bitrix24 REST API and Marketplace Applications
Why This Is Important to Keep in Mind
Features of REST Calls When Changing the Bitrix24 Address
Why This Is Important to Keep in Mind
Approach 1
Approach 2
New cloud Bitrix24 accounts are created with generated addresses in the format
b24-xxx.bitrix24.yy
. Users can change this address at any time, subject to certain limitations. These limitations depend on the plan being used.
Why This Is Important to Keep in Mind
Why This Is Important to Keep in Mind
If your application makes a REST call to Bitrix24 and uses a saved address on the application side, there may be a situation where this address is no longer valid.
When accessing an outdated address, Bitrix24 performs a redirect to the new one, but this redirect needs to be handled correctly in your code.
Most likely, if you are using GET parameters in your REST calls, you won't notice anything unusual, but with POST requests, it gets a bit more complicated.
In particular, if you are using PHP and curl, depending on the settings, a POST request during a redirect may "magically" turn into a GET request. In this case, the parameters sent in the POST request are simply lost.
Note
These features of working with the REST API are already taken into account in the
Bitrix SDK
.
Approach 1
Approach 1
When making a POST request, disable the redirect. If you receive a 302 status code, take the new address from the result and repeat the POST request, but to the new address.
Python
PHP
response = requests.post(url, allow_redirects=
False
)
if
response.status_code ==
302
:
response = requests.post(response.headers[
'Location'
])
<?php
$options
= [
'http'
=> [
'method'
=>
'POST'
,
'follow_location'
=>
false
]
];
$context
=
stream_context_create
(
$options
);
$response
=
file_get_contents
(
$url
,
false
,
$context
);
$headers
=
$http_response_header
;
$status_line
=
$headers
[
0
];
preg_match
(
'{HTTP\/\S*\s(\d{3})}'
,
$status_line
,
$match
);
$status_code
=
$match
[
1
];
if
(
$status_code
==
302
) {
foreach
(
$headers
as
$header
) {
if
(
stripos
(
$header
,
'Location:'
) ===
0
) {
$location
=
trim
(
substr
(
$header
,
9
));
$response
=
file_get_contents
(
$location
,
false
,
$context
);
break
;
}
}
}
?>
Approach 2
Approach 2
Use the option
curl_setopt($ch, CURLOPT_POSTREDIR, 3)
, which will allow you to handle the redirect situation.
Copied
Was the article helpful?
Yes
No
Previous
How to Execute a Batch of Requests
Next
Full Protocol

---

## Interactive Applications

**Source:** https://apidocs.bitrix24.com/settings/interactivity/index

Interactive Applications | Bitrix24 REST API and Marketplace Applications
Interactive Applications
Interactive Applications
By connecting to RT servers, you can:
create a truly interactive application
change states
instantly update the interface without the need to refresh the page in real-time
If you are building your own client, check out the
Working with Push & Pull server
. If you only need to add interactivity to an existing application, read about
Working with Push & Pull in the browser
.
Interactivity in applications is available out of the box starting from the
version
Push & Pull 18.5.500.
Learn more about interactivity in applications in the training course
REST API Bitrix24
.
Was the article helpful?
Yes
No
Previous
Uninstalling Applications
Next
Push&Pull in the Browser

---

## Push&Pull in the Browser

**Source:** https://apidocs.bitrix24.com/settings/interactivity/push-and-pull-in-browser

Push&Pull in the Browser | Bitrix24 REST API and Marketplace Applications
Push&Pull in the Browser
Push&Pull in the Browser
Let's look at how to work with the built-in Push & Pull client within the application. Here’s an example page for an application with a web interface:
<!
DOCTYPE
html>
<
html
>
<
head
>
<
title
>
Bitri24 application with Push & Pull
</
title
>
<
meta
http-equiv
=
"Content-Type"
content
=
"text/html; charset=utf-8"
/>
<
script
src
=
"//api.bitrix24.com/api/v1/"
>
</
script
>
<
script
src
=
"//api.bitrix24.com/api/v1/pull/"
>
</
script
>
</
head
>
<
body
>
<
script
>
window
.
appPullClient
=
new
BX
.
PullClient
({
restApplication
:
'myApplication_test.bitrix24.com'
,
restClient
:
BX24
,
userId
:
1
});
window
.
appPullClient
.
subscribe
({
moduleId
:
'application'
,
callback
:
function
(
data
) {
console
.
warn
(data);
// {command: '...', params: {...}, extra: {...}}
}.
bind
(
this
)
});
window
.
appPullClient
.
start
();
</
script
>
</
body
>
</
html
>
When initializing
BX.PullClient
, you need to specify the following parameters:
restApplication
— specify a custom string identifier for the application. (It must be unique for each account where your application is installed)
userId
— specify the identifier of the currently authorized user
Connecting the PullClient will allow the front-end of your application to receive events from the channel that will be sent there by the back-end of your application using the method
pull.application.event.add
.
Copied
Was the article helpful?
Yes
No
Previous
Interactive Applications
Next
Custom Push&Pull Client

---

## Custom Push&Pull Client

**Source:** https://apidocs.bitrix24.com/settings/interactivity/custom-push-and-pull-client

Custom Push&Pull Client | Bitrix24 REST API and Marketplace Applications
Application Development
Custom Push&Pull Client
Application Development
General Format of Commands from the Server
Error Handling
Format of Incoming Commands for Connection Management
channel_expire
config_expire and server_restart
In this article, you will find information on how to write your own client. If you don't need a new client but just want to add interactivity to an existing application, you may find the article
Push&Pull in the Browser
useful.
By connecting to RT servers, you can create a truly interactive application: the application's state changes, and the interface updates instantly without the need for AJAX requests.
Application Development
Application Development
There are two ways to connect to the service: Long polling and WebSocket.
When a user accesses the site, their browser, desktop, or mobile application establishes and maintains a persistent connection with the Push server. This is usually done using
WebSocket
, which is supported by 95% of modern browsers.
If the WebSocket technology is not supported by the browser,
Long Polling
is used instead — a persistent long polling method.
It is recommended to use WebSocket as the primary connection method. Long polling is only used for devices that do not support WebSocket or if the client frequently encounters issues when connecting to WebSocket.
To obtain data about the server and connection addresses, use the REST command
pull.application.config.get
.
To connect to the server, take the connection address of the desired type (for example,
websocket_secure
) from the server settings (the
server
field) and append all available channels through
/
. If a cloud push server is used on the account, you need to add the
clientId
parameter to the URL for connecting to the server.
Example connection for WebSocket for a cloud push server:
wss://rtc-cloud-ms1.bitrix.info/subws/?CHANNEL_ID=beb502091dfc9b93d7fd648aa4ec332e%3A7cc478c89de71ec78bf4820d3d814a3e.4f5466742ca1e59e263fee732a7dbe002889ba91%2F1ab4f7a440cea35a1abccd5c2566c688.b33914ef342e5cd21e4fbcf4ac92acd2e9ea3755&clientId=fcda45d0859442735f07b8bb5825ded1
Example connection for WebSocket for an on-premise push server:
wss://rt.bitrix24.com/sub/?CHANNEL_ID=46a437d2336d4a88e4e9b3cd956ecf45:6221e0eb48981fce67cf4756e82e8102.7910bb25e660bf211fdec15e33c5e25e4c3b644a/fb9f7e13dc3d595c5aefe1a0216c27a2.2887eebc6ae160713a732893462dce9d8e23a7b0
The lifetime of each channel is limited to 12 hours. You need to monitor the expiration time and make a repeated request to
pull.application.config.get
when one of the channels has expired.
To access the history in the channel, append special GET parameters to the above address:
&tag=
and
&time=
(for server version 2 and below) or
&mid=
(for version 3 and above). You will receive all necessary data for the GET parameters when parsing each command from the channel. After connecting with these parameters, you will have one-time access to messages that were not available for the current session.
General Format of Commands from the Server
General Format of Commands from the Server
For server version 3 and below, when commands are received, the text appears as follows:
#!NGINXNMS!#{"id":320146,"mid":"14526134350000000000320146","channel":"6221e0eb48981fce67cf4756e82e8102","tag":"672","time":"Thu, 29 Jun 2017 09:50:16 GMT","text":{...},"extra":{...}}}#!NGINXNME!#
#!NGINXNMS!#{"id":320147,"mid":"14526134350000000000320147","channel":"6221e0eb48981fce67cf4756e82e8102","tag":"673","time":"Thu, 29 Jun 2017 09:50:17 GMT","text":{...},"extra":{...}}}#!NGINXNME!#
To work with the command, you need to extract its content and convert it to JSON. The command text is located between the control phrases #!NGINXNMS!# and #!NGINXNME!#.
Starting from server version 4, use the addition of the GET parameter
&format=json
when connecting and when commands are received; it will be returned to you in JSON format:
[
{
"id"
:
320146
,
"mid"
:
"14526134350000000000320146"
,
"channel"
:
"6221e0eb48981fce67cf4756e82e8102"
,
"tag"
:
"672"
,
"time"
:
"Thu, 29 Jun 2017 09:50:16 GMT"
,
"text"
:
{
...
}
,
"extra"
:
{
...
}
}
}
,
{
"id"
:
320147
,
"mid"
:
"14526134350000000000320147"
,
"channel"
:
"6221e0eb48981fce67cf4756e82e8102"
,
"tag"
:
"673"
,
"time"
:
"Thu, 29 Jun 2017 09:50:17 GMT"
,
"text"
:
{
...
}
,
"extra"
:
{
...
}
}
}
]
The JSON structure of the command has the following unified format:
{
"id"
:
320146
,
"mid"
:
"14526134350000000000320146"
,
"channel"
:
"6221e0eb48981fce67cf4756e82e8102"
,
"tag"
:
"672"
,
"time"
:
"Mon, 03 Oct 2017 06:36:01 GMT"
,
"text"
:
{
"module_id"
:
"main"
,
"command"
:
"user_online"
,
"params"
:
{
...
}
,
}
,
"extra"
:
{
"server_time"
:
"2017-10-03T08:36:01+02:00"
,
"server_time_unix"
:
1507012561
,
"server_time_ago"
:
0
,
"revision"
:
16
,
"revisionMobile"
:
1
,
"channel"
:
"6221e0eb48981fce67cf4756e82e8102"
}
}
Where:
id
— message identifier
mid
— message identifier (only for server version 3 and above, used for restoring history from a specific message)
channel
— channel identifier (only for server version 3 and above, for earlier versions use
extra.channel
)
tag
— E-tag (for server version 2 and below, used for restoring history from a specific message)
time
— message time (for server version 2 and below, used for restoring history from a specific message)
text
— structure describing the command's action, containing the following keys:
module_id
— identifier of the module that sent the command (for marketplace applications —
appId
)
command
— command identifier
params
— additional data for executing the command
extra
— structure describing additional information:
server_time
— server time at the moment the command was generated (ATOM format)
server_time_unix
— server time at the moment the command was generated (in Unix timestamp format with the browser's timezone)
server_time_ago
— number of seconds that have passed since the command was sent
server_name
— name of the server that sent the command
revision
— revision of the push & pull module for the browser script
revisionMobile
— revision of the push & pull module for the mobile client
channel
— channel identifier (only for server version 1)
Error Handling
Error Handling
During operation with the server, various errors may occur. To avoid being blocked for suspicious activity, it is important to handle them correctly.
If connecting to the server results in errors, you should incrementally increase the connection time:
When an error occurs for the first time, the connection delay is 100ms.
On a repeated error - 15 seconds.
From 3 to 5 errors - 45 seconds.
From 5 to 10 errors - 10 minutes.
More than 10 consecutive errors - 1 hour.
When working with WebSocket, if errors occur more than 4 times, it is recommended to switch to Long polling. It is very likely that the WebSocket protocol is blocked on the client's computer (WebSocket closure codes
1006
and
1008
).
A full switch to Long polling makes sense if you have never been able to connect via WebSocket. If there have been successful connections before, it makes sense to switch temporarily for 10 to 30 minutes.
Format of Incoming Commands for Connection Management
Format of Incoming Commands for Connection Management
For your own implementation of the Push & Pull protocol, ensure you handle control commands.
channel_expire
channel_expire
Command about the expiration of the channel's lifetime.
{
"module_id"
:
"pull"
,
"command"
:
"channel_expire"
,
"params"
:
{
"action"
:
"reconnect"
,
"channel"
:
{
"id"
:
"46a437d2336d4a88e4e9b3cd956ecf45.7910bb25e660bf211fdec15e33c5e25e4c3b644a"
,
"type"
:
"shared"
}
,
"new_channel"
:
{
"id"
:
"fb9f7e13dc3d595c5aefe1a0216c27a2.2887eebc6ae160713a732893462dce9d8e23a7b0"
,
"start"
:
"2017-06-28T09:57:48+02:00"
,
"end"
:
"2017-06-28T21:57:48+02:00"
,
"type"
:
"shared"
}
}
}
Command Parameters
Command Parameters
Name
Description
action
Description of the required action
channel
Information about the channel for which the command was received
new_channel
Information about the new channel. Available only if
action == reconnect
Description of Command Handling
Description of Command Handling
Upon receiving the
channel_expire
command, depending on the value of
action
, perform the following steps:
action == reconnect
replace the current channel information with data from
new_channel
re-establish the connection to the server
action == get_config
disconnect from the server
request new channel data via REST
pull.application.config.get
re-establish the connection to the server
config_expire and server_restart
config_expire and server_restart
Command about changes to the server settings.
{
"module_id"
:
"pull"
,
"command"
:
"config_expire"
,
"params"
:
{
}
}
Description of Command Handling
Description of Command Handling
If the
config_expire
or
server_restart
command is received:
disconnect from the server
after a random interval (from 10 to 120 seconds), request new channel data via REST
pull.application.config.get
re-establish the connection to the server
Copied
Was the article helpful?
Yes
No
Previous
Push&Pull in the Browser
Next
Push&Pull

---

## Push&Pull

**Source:** https://apidocs.bitrix24.com/settings/interactivity/push-and-pull/index

Push&Pull | Bitrix24 REST API and Marketplace Applications
Push&Pull
Push&Pull
Access permissions
Scope
:
pull
|
Who can execute the method
:
administrator
REST methods available for working with notifications.
Method
Description
pull.application.config.get
Method for retrieving information about connecting to real-time servers and organizing instant communications within applications.
pull.application.event.add
Method for sending events to the application's RT channel.
pull.application.push.add
Method for sending push notifications to mobile devices within the Bitrix24 application.
See also
See also
Interactivity in applications
Copied
Was the article helpful?
Yes
No
Previous
Custom Push&Pull Client
Next
Organize instant communications within applications

---

## Organize Instant Communications within Applications pull.application.config.get

**Source:** https://apidocs.bitrix24.com/settings/interactivity/push-and-pull/pull-application-config-get

Organize Instant Communications within Applications pull.application.config.get | Bitrix24 REST API and Marketplace Applications
Organize Instant Communications within Applications pull.application.config.get
Organize Instant Communications within Applications pull.application.config.get
Examples
Response on Success
Response on Error
Possible Error Codes
See Also
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
pull
Who can execute the method: administrator
The method
pull.application.config.get
is used to retrieve information about connecting to real-time servers and organizing instant communications within applications.
By connecting to RT servers, you can:
create a truly interactive application,
change states,
instantly update the interface without the need to refresh the page in real-time.
Warning
The method will return data about connections to channels specifically created for your REST application. Within these channels, you will receive only your events.
Parameter
Description
CACHE
Y / N
Whether to return cached data or not, default is Y.
Examples
Examples
JavaScript
PHP
BX24
.
callMethod
(
'pull.application.config.get'
, {
'CACHE'
:
'Y'
,
},
function
(
result
){
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
().
ex
);
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
});
$result
=
restCommand
(
'pull.application.config.get'
, [
'CACHE'
=>
'Y'
,
],
$_REQUEST
[
"auth"
]);
How to Use Examples in Documentation
Response on Success
Response on Success
200 OK
{
"result"
:
{
"server"
:
{
"version"
:
4
,
"server_enabled"
:
true
,
"long_polling"
:
"http://rt.bitrix24.com/sub/"
,
"long_polling_secure"
:
"https://rt.bitrix24.com/sub/"
,
"websocket_enabled"
:
true
,
"websocket"
:
"ws://rt.bitrix24.com/sub/"
,
"websocket_secure"
:
"wss://rt.bitrix24.com/sub/"
,
"publish_enabled"
:
true
,
"publish"
:
"http://rt.bitrix24.com/pubweb/"
,
"publish_secure"
:
"https://rt.bitrix24.com/pubweb/"
}
,
"channels"
:
{
"shared"
:
{
"id"
:
"46a437d2336d4a88e4e9b3cd956ecf45.7910bb25e660bf211fdec15e33c5e25e4c3b644a"
,
"start"
:
"2017-06-28T12:04:00+02:00"
,
"end"
:
"2017-06-29T00:04:00+02:00"
,
"type"
:
"shared"
}
,
"private"
:
{
"id"
:
"925153cd80b6b5a4dbf8659d5be21d1:abe9e6964532000ab8b7acf092ba627b.605ea91793ad24be3f9745d662713b23a5803a94"
,
"public_id"
:
"abe9e6964532000ab8b7acf092ba627b.057ac8625ae4ac0da4ed093a19950f9dab7e29d0"
,
"start"
:
"2017-06-28T09:57:48+02:00"
,
"end"
:
"2017-06-28T21:57:48+02:00"
,
"type"
:
"private"
}
}
}
}
The
server
object describes the server configuration and paths for connecting to the real-time channel. The keys of the object:
version
- version of the installed server,
server_enabled
- whether the server is activated,
websocket_enabled
- whether websocket functionality is available,
long_polling
and
websocket
- connection paths,
long_polling_secure
and
websocket_secure
- connection paths when using the HTTPS protocol,
publish_enabled
- whether
message publishing capability
is available from the client side.
publish
and
publish_secure
- paths for publishing messages from the client,
clientId
- unique identifier of the account on the cloud push server. Returned if the account uses a cloud push server.
The
channels
object describes the data for connecting the user to the channels. The keys:
shared
- the shared channel of the account. Commands are published on this channel for all users of the account (including extranet users).
private
- the user's private channel. Commands are published on this channel only for the current user.
The channel array contains:
id
- channel identifier;
public_id
- public
channel identifier
;
start
- time of channel creation (in ATOM format);
end
- time of channel expiration (in ATOM format);
type
- type of channel.
Response on Error
Response on Error
200 Error, 50x Error
{
"error"
:
"SERVER_ERROR"
,
"error_description"
:
"Push & Pull server is not configured"
}
Keys:
error
- code of the occurred error
error_description
- brief description of the occurred error
Possible Error Codes
Possible Error Codes
Code
Description
SERVER_ERROR
The
Push & Pull
module is not configured on the account to work with the queue server.
WRONG_AUTH_TYPE
The method can only be used within
OAuth 2.0
or through
webhooks
.
See Also
See Also
Interactivity in Applications
Available starting from version 4 of the queue server.
Available only for version 4 of the queue server and only for private channels.
Copied
Was the article helpful?
Yes
No
Previous
Push&Pull
Next
Send events to the application's RT channel

---

## Send Events to the RT Channel of the pull.application.event.add

**Source:** https://apidocs.bitrix24.com/settings/interactivity/push-and-pull/pull-application-event-add

Send Events to the RT Channel of the pull.application.event.add | Bitrix24 REST API and Marketplace Applications
Send Events to the RT Channel of the pull.application.event.add
Send Events to the RT Channel of the pull.application.event.add
Examples
Response on Success
Response on Error
Possible Error Codes
See Also
We are still updating this page
Some data may be missing — we will complete it soon.
Scope:
pull
Who can execute the method: administrator
The method
pull.application.event.add
is used to send events to the RT channel of the application.
Parameter
Description
COMMAND
*
Type of event, string.
PARAMS
Arbitrary JSON array with data.
MODULE_ID
If commands are sent from different subsystems of the application, this can be specified through the module.
USER_ID
If USER_ID is not specified, the data will be sent to the general channel. If a user ID is specified, the data will be sent to a private channel. An administrator can send to multiple users and the general channel simultaneously, while a user without permissions can only send to themselves or the general channel.
Required parameters are marked with *
Examples
Examples
JavaScript
PHP
BX24
.
callMethod
(
'pull.application.event.add'
, {
'COMMAND'
:
'test'
,
'PARAMS'
:
'{"param1":"value1"}'
,
},
function
(
result
){
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
().
ex
);
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
});
$result
=
restCommand
(
'pull.application.event.add'
, [
'COMMAND'
=>
'test'
,
'PARAMS'
=> [
'param1'
=>
'value1'
],
],
$_REQUEST
[
"auth"
]);
How to Use Examples in Documentation
Response on Success
Response on Success
200 OK
{
"result"
:
true
}
Response on Error
Response on Error
200 Error, 50x Error
{
"error"
:
"WRONG_AUTH_TYPE"
,
"error_description"
:
"Get access to application config available only for application authorization."
}
Keys:
error
- code of the occurred error
error_description
- brief description of the occurred error
Possible Error Codes
Possible Error Codes
Code
Description
COMMAND_ERROR
The format of the MODULE_ID field is incorrect. Allowed are English letters in mixed case, digits, underscore, dot, and hyphen.
MODULE_ID_ERROR
The format of the MODULE_ID field is incorrect. Allowed are English letters in lowercase, digits, dot, and underscore.
USER_ID_ACCESS_ERROR
Only users with administrator rights can specify arbitrary users.
PARAMS_ERROR
An incorrect JSON object was passed.
WRONG_AUTH_TYPE
The method can only be used within
OAuth 2.0
.
See Also
See Also
Interactivity in Applications
Copied
Was the article helpful?
Yes
No
Previous
Organize instant communications within applications
Next
Send push notifications to mobile devices

---

## Send push notifications to a mobile device using the method pull.application.push.add

**Source:** https://apidocs.bitrix24.com/settings/interactivity/push-and-pull/pull-application-push-add

Send push notifications to a mobile device using the method pull.application.push.add | Bitrix24 REST API and Marketplace Applications
Send push notifications to a mobile device using the method pull.application.push.add
Send push notifications to a mobile device using the method pull.application.push.add
Parameters
Examples
Successful response
Error response
Possible error codes
See also
We are still updating this page
Some data may be missing — we will complete it soon.
Scope:
pull
Who can execute the method: administrator
The method
pull.application.push.add
is used to send a push notification to a mobile device within the Bitrix24 application.
Parameters
Parameters
Parameter
Description
USER_ID
*
Identifiers of the users receiving the push notifications.
TEXT
Custom text.
AVATAR
Link to an image.
Required parameters are marked with *
Examples
Examples
JavaScript
PHP
BX24
.
callMethod
(
'pull.application.push.add'
, {
'USER_ID'
: [
1
,
2
,
3
],
'TEXT'
:
'Hello, world!'
,
'AVATAR'
:
'https://files.shelenkov.com/images/avatar-johnson.jpg'
,
},
function
(
result
){
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
().
ex
);
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
});
$result
=
restCommand
(
'pull.application.push.add'
, [
'USER_ID'
=> [
1
,
2
,
3
],
'TEXT'
=>
'Hello, world!'
,
'AVATAR'
=>
'https://files.shelenkov.com/images/avatar-johnson.jpg'
,
],
$_REQUEST
[
"auth"
]);
How to Use Examples in Documentation
Successful response
Successful response
200 OK
{
"result"
:
true
}
Error response
Error response
200 Error, 50x Error
{
"error"
:
"WRONG_AUTH_TYPE"
,
"error_description"
:
"Send push notifications available only for application authorization."
}
Keys:
error
- code of the occurred error
error_description
- brief description of the occurred error
Possible error codes
Possible error codes
Code
Description
TEXT_ERROR
Message text was not provided.
EMPTY_APP_NAME
Error occurs if your application does not have a name assigned.
ACCESS_ERROR
The method can only be used by a user with administrator rights.
WRONG_AUTH_TYPE
The method can only be used within
OAuth 2.0
.
See also
See also
Interactivity in applications
Copied
Was the article helpful?
Yes
No
Previous
Send events to the application's RT channel
Next
General Recommendations

---

## General Recommendations

**Source:** https://apidocs.bitrix24.com/settings/performance/index

General Recommendations | Bitrix24 REST API and Marketplace Applications
Requests to Bitrix24
General Recommendations
Requests to Bitrix24
Event Handling and Outgoing Webhooks
There are certain
limits
when working with the REST API of the cloud version of Bitrix24. In the case of
on-premise installation
, the limitations depend on the specific server infrastructure settings on which Bitrix24 operates, meaning that the limits can vary both upwards and downwards.
However, there are several general recommendations that, if followed, will reduce the risk of your applications hitting the REST API limits.
Requests to Bitrix24
Requests to Bitrix24
Reduce the number of requests to Bitrix24:
Cache some data on your side to avoid unnecessary repeated requests that return the same data you have already received;
Use batch execution of requests with the
batch method
(the limit on request intensity takes into account the number of hits to Bitrix24, and using batch allows you to make several actual REST API requests in one hit).
Use the
start=-1 parameter
when calling list methods - this reduces the load on Bitrix24's server resources.
Try to request only the data that is actually needed (specify the list of required fields in the
select
parameter for those methods that support it).
Event Handling and Outgoing Webhooks
Event Handling and Outgoing Webhooks
As you know, the
event mechanism
in Bitrix24 operates using a special service - the event queue - which invokes your handlers.
It is important to consider that you cannot control the intensity of events.
Imagine that your application has registered a handler for
OnCRMDealUpdate
, and users on a specific Bitrix24 instance have massively (using a
workflow
or automation based on the REST API) updated 10K deals. The Bitrix24 event queue will immediately generate tasks to send 10K notifications to your handler.
Therefore, your handler must be prepared for potential peak loads. It should respond as quickly as possible - if the event queue does not receive a response from your handler when sending the next event, or if your handler responds slowly, subsequent calls will be executed with lower priority, resulting in longer delays.
Most importantly, if your handler cannot handle such a load and your server "crashes," you will simply not receive and will be unable to process some of the events sent to your handler. Bitrix24 does not resend events if the event handler does not respond at all or returns an error status from the web server.
Thus, we
strongly recommend
using the "
incoming queue
" for event processing. The concept of an “incoming queue” for handling HTTP requests implies that requests are not processed immediately upon arrival but are placed in a queue, from which they are subsequently retrieved and processed by your server or even a group of servers. This allows for better load management, increased stability, and scalability of the system.
Copied
Was the article helpful?
Yes
No
Previous
Send push notifications to mobile devices
Next
Limits

---

## Limits

**Source:** https://apidocs.bitrix24.com/settings/performance/limits

Limits | Bitrix24 REST API and Marketplace Applications
Request Intensity Limits
Limits
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
General Recommendations
Next
Incoming Queue

---

## Incoming Event Queue

**Source:** https://apidocs.bitrix24.com/settings/performance/queue

Incoming Event Queue | Bitrix24 REST API and Marketplace Applications
Incoming Event Queue
Incoming Event Queue
The concept of an
"incoming queue"
for processing HTTP requests implies that you do not handle requests to your event handlers immediately as they arrive, but instead place them in a queue from which they are sequentially retrieved and processed by your server or a group of servers.
Main Principle:
Main Principle:
Requests arrive at the server
: When Bitrix24 sends HTTP requests to your event handler, they first reach the server or load balancer. In response to the incoming request, your server immediately replies that the request has been accepted and is being processed (HTTP 200/202). Thus, from the perspective of the event queue, your handler operates as quickly as possible, which means it will be called with maximum priority in the future.
Requests are added to the queue
: Instead of immediate processing, you must save the data from the request in a special queue (for example, in a database, cache system, or distributed queue).
Retrieving requests from the queue
: Regardless of incoming requests, one or more handlers (workers) retrieve requests from the queue and process them one by one or in parallel, depending on available resources.
Advantages:
Advantages:
Load management
: Queues allow for sequential processing of requests and prevent server overload during traffic spikes.
Increased stability
: Even if the system experiences high load, requests are not lost but queued and processed later.
Scalability
: Queues make it easy to scale the system by adding more workers or servers to handle requests.
Improved response for clients
: Clients can immediately receive a message that their request has been accepted, rather than waiting for processing to complete.
Simple Implementation Option:
Simple Implementation Option:
1. Saving to a Database (DB-based Queue)
1.
Saving to a Database (DB-based Queue)
The simplest way is to save incoming requests to a database.
Requests arrive at the server
, and the request information (body, metadata) is saved to the database.
A
background process
or cron job regularly checks the database for new requests, processes them, and updates their status.
Example:
Bitrix24 sends a request to your event handler, and the request is saved in the
requests
table.
A background task checks the table every few seconds and processes requests.
Advantage
: Simplicity of implementation.
Disadvantages
: Possible performance degradation under high loads due to contention for database access.
Example in PHP:
Event Handler
Worker
// Save the request to the database, do nothing else!
$db
->
query
(
"INSERT INTO requests (data, status) VALUES ('
$data
', 'pending')"
);
// Select a batch of records from the queue for processing
$pendingRequests
=
$db
->
query
(
"SELECT * FROM requests WHERE status='pending'"
);
foreach
(
$pendingRequests
as
$request
) {
// Process the request
processRequest
(
$request
);
$db
->
query
(
"UPDATE requests SET status='processed' WHERE id="
.
$request
[
'id'
]);
}
2. Using Redis (or Memcached)
2.
Using Redis (or Memcached)
To improve performance, you can use
Redis
or
Memcached
as a simple queue.
Incoming requests are queued in Redis using the
LPUSH
command (add an element to the list).
Handlers (workers) retrieve requests using
RPOP
(take an element from the end of the list) and process them.
Advantages
: Fast operation, especially with large volumes of data and high loads.
Example in PHP:
Event Handler
Worker
// Save the request to the database, do nothing else!
$redis
->
lPush
(
'request_queue'
,
json_encode
(
$requestData
));
// Select a batch of records from the queue for processing
while
(
$request
=
$redis
->
rPop
(
'request_queue'
)) {
processRequest
(
json_decode
(
$request
));
}
3. RabbitMQ or Kafka (Advanced Solution)
3.
RabbitMQ or Kafka (Advanced Solution)
For more complex and larger systems, you can use queue systems like
RabbitMQ
or
Kafka
.
RabbitMQ
: This is a popular queue system that supports complex message routing scenarios, load balancing, and scaling. RabbitMQ supports message acknowledgment, ensuring their delivery.
Kafka
: Used in large systems for stream processing. Kafka allows distributing data among many consumers, enhancing scalability and reliability.
Advantages
: High scalability, reliability, and the ability for complex routing and load balancing.
Example of using RabbitMQ in PHP:
Event Handler
Worker
// Sends a message to the RabbitMQ queue, do nothing else!
$connection
=
new
AMQPStreamConnection
(
'localhost'
,
5672
,
'user'
,
'password'
);
$channel
=
$connection
->
channel
();
$channel
->
queue_declare
(
'request_queue'
,
false
,
true
,
false
,
false
);
$channel
->
basic_publish
(
new
AMQPMessage
(
json_encode
(
$requestData
)),
''
,
'request_queue'
);
// Process messages from the queue
$callback
=
function
(
$msg
)
{
processRequest
(
json_decode
(
$msg
->body));
};
$channel
->
basic_consume
(
'request_queue'
,
''
,
false
,
true
,
false
,
false
,
$callback
);
while
(
$channel
->
is_consuming
()) {
$channel
->
wait
();
}
Recommendations for Implementing an Incoming Queue
Recommendations for Implementing an Incoming Queue
For small systems
: You can start with a database to save requests, which is simpler and easier to implement.
For systems with moderate load
: Use Redis or Memcached to improve performance and real-time request processing.
For large and high-load systems
: Consider using specialized solutions like RabbitMQ or Kafka to ensure high availability, scalability, and processing of large volumes of data.
Copied
Was the article helpful?
Yes
No
Previous
Limits
Next
Retrieve Large Volumes of Data

---

## Retrieve Large Volumes of Data

**Source:** https://apidocs.bitrix24.com/settings/performance/huge-data

Retrieve Large Volumes of Data | Bitrix24 REST API and Marketplace Applications
Retrieve Large Volumes of Data
Retrieve Large Volumes of Data
Often, there is a need to import certain entities from the account via REST. However, when dealing with a large number of entities, the direct approach of setting a filter and passing
start = start + 50
in each subsequent request is not optimal. This is because using
start >= 0
requires an additional request to count the number of elements that meet the filter criteria for each request. This can be slow when there are many elements or when the filtering is complex.
Therefore, if you do not need the count of elements (for example, if you only need the last 10 records), or if you are importing all records based on a filter, you should pass
start = -1
.
This parameter will disable the count request and significantly speed up the data retrieval.
To perform the import, you will need to sort the records by
ID
and add a condition to the filter:
ID > value of the last element
. With each step, you will increase this value. The value of the last element should be taken from the last value of the received result.
The condition for stopping the import will be an empty response or when the number of elements in the response is less than 50.
Below is an example of code and a comparison of execution time with the classic approach. With 2,387,743 leads, using the same permissions and filter, the execution time decreased from 49.9 seconds to 0.097 seconds.
Example
Example
$tokenID
=
'XXXXXXXXXXXXXXXXXXXXX'
;
$host
=
'XXXX.bitrix24.com'
;
$user
=
1
;
/**
* Start from zero or from some previous step
*/
$leadID
=
0
;
$finish
=
false
;
while
(!
$finish
)
{
/**
* Continue until all data is retrieved; in this case, do not forget about the delay between hits.
* Alternatively, select only 50 each time, starting from the element where the last iteration stopped.
*/
$http
=
new
\Bitrix\Main\Web\HttpClient
();
$http
->
setTimeout
(
5
);
$http
->
setStreamTimeout
(
50
);
$json
=
$http
->
post
(
'https://'
.
$host
.
'/rest/'
.
$user
.
'/'
.
$tokenID
.
'/crm.lead.list/'
,
[
'order'
=> [
'ID'
=>
'ASC'
],
'filter'
=> [
'>ID'
=>
$leadID
],
'select'
=> [
'ID'
,
'TITLE'
,
'DATE_CREATE'
],
'start'
=> -
1
]
);
$result
=
\Bitrix\Main\Web\Json
::
decode
(
$json
);
if
(
count
(
$result
[
'result'
]) >
0
)
{
foreach
(
$result
[
'result'
]
as
$lead
)
{
$leadID
=
$lead
[
'ID'
];
}
// Do something
}
else
{
$finish
=
true
;
}
}
/*
//Results of the REST request using count.
Array
(
[result] => Array
(
[0] => Array()
[1] => Array()
.....
[49] => Array()
)
[next] => 50
[total] => 2387743
[time] => Array
(
[start] => 1581607213.4833
[finish] => 1581607263.3997
[duration] => 49.916450023651
[processing] => 49.899916887283
[date_start] => 2020-02-13T18:20:13+03:00
[date_finish] => 2020-02-13T18:21:03+03:00
)
)
//Results of the REST request without using count.
Array
(
[result] => Array
(
[0] => Array()
[1] => Array()
.....
[1] => Array()
)
[total] => 0
[time] => Array
(
[start] => 1581609136.3857
[finish] => 1581609136.4835
[duration] => 0.097883939743042
[processing] => 0.068500995635986
[date_start] => 2020-02-13T18:52:16+03:00
[date_finish] => 2020-02-13T18:52:16+03:00
)
)
Copied
Was the article helpful?
Yes
No
Previous
Incoming Queue
Next
Overview

---

## Differences in Using REST API in Cloud and On-Premise Bitrix24

**Source:** https://apidocs.bitrix24.com/settings/cloud-and-on-premise/index

Differences in Using REST API in Cloud and On-Premise Bitrix24 | Bitrix24 REST API and Marketplace Applications
Feature of On-Premise Bitrix24
Differences in Using REST API in Cloud and On-Premise Bitrix24
Feature of On-Premise Bitrix24
Bitrix24 Authorization Server
Network Limitations
Bitrix24 exists both as a cloud service and as on-premise installations on the client side.
The advantage of REST applications is that they can operate in both environments in the same way, especially if certain nuances that may arise are considered during the application's development.
Feature of On-Premise Bitrix24
Feature of On-Premise Bitrix24
In cloud Bitrix24, the REST API is always available in the "latest version." However, updates for the on-premise version may be released some time after they appear in the cloud due to the additional functionality that the on-premise Bitrix24 contains. Testing for compatibility with this functionality requires extra time.
Moreover, in the case of a specific on-premise installation, there is no guarantee that the owner has installed the latest available updates and has generally installed the necessary Bitrix24 modules for the application (for example, nothing prevents the telephony module from being completely disabled in on-premise Bitrix24). This means that when installing the application, there is no certainty about the availability of specific REST methods.
Therefore,
recommendation number 1
— in your solution's installation script, check the list of available methods and events by referring to the
methods
and
events
, and inform the user that they need to install updates for Bitrix24.
Bitrix24 Authorization Server
Bitrix24 Authorization Server
If your application refreshes authorization tokens using
refresh_token
, there are two options: obtain a new pair of tokens by making a request to
xxx.bitrix24.xxx/oauth/token/?grant_type=authorization_code...
or to the authorization server
oauth.bitrix.info/oauth/token/?grant_type=authorization_code...
In the case of cloud Bitrix24, both options will work equally well, as cloud Bitrix24 will simply "forward" your request to the actual authorization server; however, on-premise Bitrix24 may not do this.
Therefore,
recommendation number 2
— always address the authorization server directly for token refreshes. This will work for both cloud and on-premise.
Network Limitations
Network Limitations
When accessing REST methods, your application makes a request to a specific Bitrix24. However, REST events do not come directly from a specific Bitrix24 to your application; they go through an event queue located in the cloud, even if it concerns on-premise Bitrix24.
It is possible that the owner of the on-premise Bitrix24 has closed network access to the event queue server for some reason. In this case, events simply will not work. If you are implementing a solution while communicating with the client, you should recommend whitelisting the queue server's address.
The same applies to the authorization server. If network access to it is closed, REST will not work in on-premise Bitrix24, as on-premise Bitrix24 will not be able to validate the token that your application is using to access it.
There is an alternative option where you can specifically connect your own authorization and event mechanism for a particular client on their on-premise Bitrix24.
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Large Volumes of Data
Next
Network Access

---

## Required Network Access

**Source:** https://apidocs.bitrix24.com/settings/cloud-and-on-premise/network-access

Required Network Access | Bitrix24 REST API and Marketplace Applications
Required Network Access
Required Network Access
In the case of using the on-premise Bitrix24, the company's network administrator must consider the need to open access for incoming/outgoing requests from REST applications in the security policy.
For Bitrix24, the following must be opened:
Outgoing requests to
oauth.bitrix.info
(for the application mechanism)
Access to
*.bitrixsoft.com
. Without access to this resource, the "Developer resources" section for creating integrations and webhooks does not function
Outgoing requests to
https://www.bitrix24.*/util/
to display event names in the outgoing webhook creation interface
Incoming requests from application servers (the addresses depend on the specific applications)
If the application is being developed on its own server, the following must be opened:
Outgoing HTTPS requests to
oauth.bitrix.info
Outgoing HTTPS requests to the specific on-premise Bitrix24 server
Incoming HTTP/S requests from the server group
mp_actions-*
, if the application uses event mechanisms, Automation rules, or custom workflow actions
Incoming HTTP/S requests for the data type
application/x-www-form-urlencoded
Incoming HTTP/S requests may come from a dynamic (scale-based) group of servers with different IP addresses. A list of such IP addresses can be obtained in advance by querying
https://dl.bitrix24.com/webhook/app-world.json
.
Example request via
curl
:
$ curl https://dl.bitrix24.com/webhook/app-world.json
{
"nodes"
: [
"3.217.33.54"
,
"52.29.163.104"
]
}
The list of IP addresses received in the
nodes
array should be used to modify the firewall rules for incoming connections in the corporate network or on the on-premise VM.
The polling frequency for the above URI should be a maximum of once per minute, and it is better to do it once every 5-10 minutes. The scaling mechanism for the VM pool will ensure that 5-10 minutes before webhooks start arriving from a new address, it will already be present in the
nodes
list.
Note
Previously, the company indicated specific IPs that needed to be opened for requests. However, since these addresses change, it is better to rely on the IP addresses that resolve the specified domain names.
Copied
Was the article helpful?
Yes
No
Previous
Overview
Next
Security Recommendations

---

## Security Recommendations for Applications Using REST API

**Source:** https://apidocs.bitrix24.com/settings/cloud-and-on-premise/security-recommendations

Security Recommendations for Applications Using REST API | Bitrix24 REST API and Marketplace Applications
Security Recommendations for Applications Using REST API
Security Recommendations for Applications Using REST API
We are still updating this page
Some data may be missing here — we will complete it soon.
Was the article helpful?
Yes
No
Previous
Network Access
Next
Overview

---

