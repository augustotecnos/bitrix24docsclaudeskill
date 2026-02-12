---
description: 'Tutorials: Sales, chat bots, telephony, AI, open lines'
methods:
- crm.currency.list
- event.bind
- event.test
pages: 13
title: 'Tutorials: Sales, chat bots, telephony, AI, open lines'
---
# Tutorials: Sales, chat bots, telephony, AI, open lines
> Tutorials: Sales, chat bots, telephony, AI, open lines
> **13 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Tutorials: Ready-made Use Cases for REST API](#tutorials-ready-made-use-cases-for-rest-api)
- [Typical use-cases for REST API in online sales](#typical-use-cases-for-rest-api-in-online-sales)
- [Create an item with a product from the catalog in a quantity of 4 units with an arbitrary price](#create-an-item-with-a-product-from-the-catalog-in-)
- [Create an item with a product that does not exist on the site (2 pcs at a price of 900 rubles)](#create-an-item-with-a-product-that-does-not-exist-)
- [Set Up Delivery Service for CRM](#set-up-delivery-service-for-crm)
- [Tutorials and use-cases for REST in the AI module](#tutorials-and-use-cases-for-rest-in-the-ai-module)
- [Add a New Prompt "Joke"](#add-a-new-prompt-joke)
- [Example of Creating a Chatbot](#example-of-creating-a-chatbot)
- [Example of Creating a Chatbot for Open Channels](#example-of-creating-a-chatbot-for-open-channels)
- [Example of Creating a Support Channel](#example-of-creating-a-support-channel)
- [Typical use-cases and scenarios example](#typical-use-cases-and-scenarios-example)
- [Tutorials and use-cases for REST in the Open Channels module](#tutorials-and-use-cases-for-rest-in-the-open-chann)
- [How to Create an Open Channel Connector for Chat on the Site](#how-to-create-an-open-channel-connector-for-chat-o)

---

## Tutorials: Ready-made Use Cases for REST API

**Source:** https://apidocs.bitrix24.com/tutorials/index

Tutorials: Ready-made Use Cases for REST API | Bitrix24 REST API and Marketplace Applications
How to Use Tutorials
Tutorials: Ready-made Use Cases for REST API
How to Use Tutorials
Structure of Tutorials
Tips for Beginners
Categories of Tutorials
How to Provide Feedback on Tutorials
Tutorials are a practical guide for developers on the Bitrix24 REST API. They help solve typical tasks: creating or modifying entities, setting up integrations with external systems.
How to Use Tutorials
How to Use Tutorials
As educational material for making your first requests. Suitable for developers who are starting to work with the Bitrix24 REST API. Tutorials will help you understand how to form requests and process responses. For example, the tutorial
How to Attach a Task to a SPA
.
As templates for real scenarios. Tutorials can be used as a basis for your own solutions: adapt the examples to your needs, add error handling logic, logging. For example, the tutorial
How to Create an Open Channel Connector for Chat on the Site
.
For quickly solving specific tasks. Tutorials will help you find a ready-made code example that you can use immediately. For example, the tutorial
How to Set Up Rounding for a Custom Number Field
.
Structure of Tutorials
Structure of Tutorials
Tutorials consist of:
a brief description of the task being solved,
examples of methods in PHP and JavaScript,
descriptions of the parameters used,
examples of server responses in JSON format,
examples of general code for applications in PHP and JavaScript,
explanations and tips,
links to related articles.
Tips for Beginners
Tips for Beginners
Explore the sections
Getting Started
,
How to Make Your First Request
.
Start with simple scenarios, such as filtering data in the tutorial
How to Filter Elements by Stage Name
. It does not use methods for modifying or deleting entities, so the data within the entities will be safe.
Example algorithm for working with the section:
Select a
category
from the menu that interests you, such as CRM.
Find the tutorial that corresponds to your task.
Follow the step-by-step instructions and examples.
Adapt the code to your needs.
Check the result and ensure everything works.
Contact
Bitrix24 Support
if you encounter difficulties.
Categories of Tutorials
Categories of Tutorials
CRM
How to work with CRM entities: contacts, deals, SPAs, custom fields, widgets, and Sales Intelligence
Online Sales and E-commerce
How to integrate trading functions: create product items, set up delivery, implement a cash register
Workflows
How to embed actions, complete processes, configure Automation rule parameters
CoPilot
How to add a custom prompt
Chatbots
How to create a chatbot, configure it for Open Channels, create a support channel
Telephony
How to implement custom scenarios for integration with a call center
Tasks
How to create tasks with files, attach them to SPAs, add comments
Open Channels
How to create a connector for online chat on the site and integrate it with Bitrix24
How to Provide Feedback on Tutorials
How to Provide Feedback on Tutorials
If you want to add your scenario or improve an existing one:
send a
pull request
with your solution to the documentation repository,
write an
issue
with your idea suggestion.
Was the article helpful?
Yes
No
Previous
How to Use Examples
Next
How to do... in CRM?

---

## Typical use-cases for REST API in online sales

**Source:** https://apidocs.bitrix24.com/tutorials/sale/index

Typical use-cases for REST API in online sales | Bitrix24 REST API and Marketplace Applications
Typical use-cases for REST API in online sales
Typical use-cases for REST API in online sales
In this section, you will find examples for solving typical tasks related to online sales:
Create an item with a product from the catalog in a quantity of 4 units with an arbitrary price
Create an item with a product that does not exist on the site (2 pcs at a price of 900 rubles)
Set Up Delivery Service for CRM
Was the article helpful?
Yes
No
Previous
Embed a Widget in a CRM Detail Form
Next
Create a position with a product from the catalog in a quantity of 4 units with a custom price

---

## Create an item with a product from the catalog in a quantity of 4 units with an arbitrary price

**Source:** https://apidocs.bitrix24.com/tutorials/sale/example-position-with-custom-price

Create an item with a product from the catalog in a quantity of 4 units with an arbitrary price | Bitrix24 REST API and Marketplace Applications
Create an item with a product from the catalog in a quantity of 4 units with an arbitrary price
Create an item with a product from the catalog in a quantity of 4 units with an arbitrary price
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
'{"fields":{"orderId":5147,"quantity":4,"productId":6544,"currency":"USD","price":1100,"discountPrice":-1070,"customPrice":"Y"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/sale.basketitem.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"orderId":5147,"quantity":4,"productId":6544,"currency":"USD","price":1100,"discountPrice":-1070,"customPrice":"Y"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/sale.basketitem.add
BX24
.
callMethod
(
"sale.basketitem.add"
,
{
fields
: {
// minimum set of required fields
orderId
:
5147
,
quantity
:
4
,
productId
:
6544
,
currency
:
'USD'
,
price
:
1100
,
discountPrice
: -
1070
,
// price in the catalog – 30 USD, indicating the markup
customPrice
:
'Y'
,
}
},
)
.
then
(
function
(
result
)
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
{
console
.
log
(result.
data
());
}
},
function
(
error
)
{
console
.
info
(error);
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
'sale.basketitem.add'
,
[
'fields'
=>
[
'orderId'
=>
5147
,
'quantity'
=>
4
,
'productId'
=>
6544
,
'currency'
=>
'USD'
,
'price'
=>
1100
,
'discountPrice'
=> -
1070
,
'customPrice'
=>
'Y'
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
Result
Result
{
"result"
:
{
"basketItem"
:
{
"basePrice"
:
30
,
"canBuy"
:
"Y"
,
"catalogXmlId"
:
"FUTURE-1C-CATALOG"
,
"currency"
:
"USD"
,
"customPrice"
:
"N"
,
"dateInsert"
:
"2024-04-23T15:59:37+02:00"
,
"dateUpdate"
:
"2024-04-23T15:59:37+02:00"
,
"dimensions"
:
"a:3:{s:5:\"WIDTH\";N;s:6:\"HEIGHT\";N;s:6:\"LENGTH\";N;}"
,
"discountPrice"
:
-1070
,
"id"
:
6790
,
"measureCode"
:
"768"
,
"measureName"
:
"pcs"
,
"name"
:
"Product"
,
"orderId"
:
5147
,
"price"
:
1000
,
"productId"
:
1245
,
"productXmlId"
:
"1245"
,
"properties"
:
[
]
,
"quantity"
:
1
,
"reservations"
:
[
]
,
"sort"
:
100
,
"vatIncluded"
:
"N"
,
"vatRate"
:
null
,
"weight"
:
0
,
"xmlId"
:
"bx_6627bec8c4fdc"
}
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
1713880776.108755
,
"finish"
:
1713880777.704221
,
"duration"
:
1.595465898513794
,
"processing"
:
0.973701000213623
,
"date_start"
:
"2024-04-23T15:59:36+02:00"
,
"date_finish"
:
"2024-04-23T15:59:37+02:00"
,
"operating"
:
0
}
}
Was the article helpful?
Yes
No
Previous
Typical use-cases for REST API in online sales
Next
Create a position with a product that does not exist on the site

---

## Create an item with a product that does not exist on the site (2 pcs at a price of 900 rubles)

**Source:** https://apidocs.bitrix24.com/tutorials/sale/example-position-that-is-not-on-the-site

Create an item with a product that does not exist on the site (2 pcs at a price of 900 rubles) | Bitrix24 REST API and Marketplace Applications
Create an item with a product that does not exist on the site (2 pcs at a price of 900 rubles)
Create an item with a product that does not exist on the site (2 pcs at a price of 900 rubles)
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
'{"fields":{"orderId":5147,"productId":0,"name":"Test Product","quantity":2,"basePrice":1000,"price":900,"discountPrice":100,"customPrice":"Y","canBuy":"Y","weight":40,"measureCode":"768","measureName":"pcs","sort":400,"xmlId":"BasketPositionId","dimensions":"a:3:{s:5:\"WIDTH\";i:244;s:6:\"HEIGHT\";i:100;s:6:\"LENGTH\";i:31;}","vatRate":10,"vatIncluded":"Y","productXmlId":"ProductKey","currency":"RUB"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/sale.basketitem.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"orderId":5147,"productId":0,"name":"Test Product","quantity":2,"basePrice":1000,"price":900,"discountPrice":100,"customPrice":"Y","canBuy":"Y","weight":40,"measureCode":"768","measureName":"pcs","sort":400,"xmlId":"BasketPositionId","dimensions":"a:3:{s:5:\"WIDTH\";i:244;s:6:\"HEIGHT\";i:100;s:6:\"LENGTH\";i:31;}","vatRate":10,"vatIncluded":"Y","productXmlId":"ProductKey","currency":"RUB"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/sale.basketitem.add
BX24
.
callMethod
(
"sale.basketitem.add"
,
{
fields
: {
// all fields are filled
orderId
:
5147
,
productId
:
0
,
name
:
'Test Product'
,
quantity
:
2
,
basePrice
:
1000
,
price
:
900
,
discountPrice
:
100
,
customPrice
:
'Y'
,
canBuy
:
'Y'
,
weight
:
40
,
measureCode
:
'768'
,
measureName
:
'pcs'
,
sort
:
400
,
xmlId
:
'BasketPositionId'
,
dimensions
:
'a:3:{s:5:"WIDTH";i:244;s:6:"HEIGHT";i:100;s:6:"LENGTH";i:31;}'
,
// serialized array
vatRate
:
10
,
vatIncluded
:
'Y'
,
productXmlId
:
'ProductKey'
,
currency
:
'RUB'
,
}
},
)
.
then
(
function
(
result
)
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
{
console
.
log
(result.
data
());
}
},
function
(
error
)
{
console
.
info
(error);
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
'sale.basketitem.add'
,
[
'fields'
=>
[
'orderId'
=>
5147
,
'productId'
=>
0
,
'name'
=>
'Test Product'
,
'quantity'
=>
2
,
'basePrice'
=>
1000
,
'price'
=>
900
,
'discountPrice'
=>
100
,
'customPrice'
=>
'Y'
,
'canBuy'
=>
'Y'
,
'weight'
=>
40
,
'measureCode'
=>
'768'
,
'measureName'
=>
'pcs'
,
'sort'
=>
400
,
'xmlId'
=>
'BasketPositionId'
,
'dimensions'
=>
'a:3:{s:5:"WIDTH";i:244;s:6:"HEIGHT";i:100;s:6:"LENGTH";i:31;}'
,
'vatRate'
=>
10
,
'vatIncluded'
=>
'Y'
,
'productXmlId'
=>
'ProductKey'
,
'currency'
=>
'RUB'
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
Result
Result
{
"result"
:
{
"basketItem"
:
{
"basePrice"
:
1000
,
"canBuy"
:
"Y"
,
"currency"
:
"RUB"
,
"customPrice"
:
"Y"
,
"dateInsert"
:
"2024-04-23T18:51:28+02:00"
,
"dateUpdate"
:
"2024-04-23T18:51:28+02:00"
,
"dimensions"
:
"a:3:{s:5:\"WIDTH\";i:244;s:6:\"HEIGHT\";i:100;s:6:\"LENGTH\";i:31;}"
,
"discountPrice"
:
100
,
"id"
:
6791
,
"measureCode"
:
"768"
,
"measureName"
:
"pcs"
,
"name"
:
"Test Product"
,
"orderId"
:
5147
,
"price"
:
900
,
"productId"
:
0
,
"productXmlId"
:
"ProductKey"
,
"properties"
:
[
]
,
"quantity"
:
2
,
"reservations"
:
[
]
,
"sort"
:
400
,
"vatIncluded"
:
"Y"
,
"vatRate"
:
10
,
"weight"
:
40
,
"xmlId"
:
"BasketPositionId"
}
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
1713891087.689427
,
"finish"
:
1713891089.165652
,
"duration"
:
1.4762251377105713
,
"processing"
:
0.8683149814605713
,
"date_start"
:
"2024-04-23T18:51:27+02:00"
,
"date_finish"
:
"2024-04-23T18:51:29+02:00"
,
"operating"
:
0
}
}
Was the article helpful?
Yes
No
Previous
Create a position with a product from the catalog in a quantity of 4 units with a custom price
Next
Set up a delivery service for CRM

---

## Set Up Delivery Service for CRM

**Source:** https://apidocs.bitrix24.com/tutorials/sale/delivery-in-crm

Set Up Delivery Service for CRM | Bitrix24 REST API and Marketplace Applications
Set Up Delivery Service for CRM
Set Up Delivery Service for CRM
1. Create Delivery Handler
2.Create Delivery Service
3.Create Shipment Properties
Property Address From
Property Address To
4. Link Shipment Properties to Delivery Service
5. Add Services to Delivery Services
Notifications about Delivery Statuses
Scope:
sale
Who can perform methods: administrator
You can connect external delivery services to Bitrix24. This allows the manager to work with the delivery service in CRM cards: calculating costs and tracking status.
To set up the delivery service, we will sequentially execute the following methods:
sale.delivery.handler.add
— register the delivery handler,
sale.delivery.add
— create the parent service and profiles linked to the handler,
sale.shipmentproperty.add
— add shipment properties for addresses,
sale.propertyrelation.add
— link properties to delivery profiles.
sale.delivery.extra.service.add
— connect additional services.
1 Create Delivery Handler
1. Create Delivery Handler
We will register the handler using
sale.delivery.handler.add
. We will pass four parameters to the method.
CODE
— symbolic code of the delivery handler. For example, we will specify
uber
.
NAME
— name of the delivery handler. We will pass
Uber
.
SETTINGS
— object with information about the handler's settings.
CALCULATE_URL
— URL for calculating delivery costs, for example
https://gateway.bx/calculate.php
.
CREATE_DELIVERY_REQUEST_URL
— URL for creating a delivery request. We will specify
https://gateway.bx/create_delivery_request.php
.
CANCEL_DELIVERY_REQUEST_URL
— URL for canceling a delivery, for example
https://gateway.bx/cancel_delivery_request.php
.
HAS_CALLBACK_TRACKING_SUPPORT
— indicator of whether the service will send notifications. We will set it to
Y
. Notifications can be created using
sale.delivery.request.sendmessage
.
CONFIG
— list of settings. We will specify
MY_FIRST_SETTING
and
MY_SECOND_SETTING
with the type
STRING
.
PROFILES
— array of delivery profiles. The handler must have at least one profile. We will set
Taxi
and
Cargo
.
The delivery service at the specified URLs must accept the request, process it, and return a response in the format expected by the CRM.
For more details on the request and response formats, refer to the section
Webhooks for Delivery Operations
.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'sale.delivery.handler.add'
,
{
CODE
:
"uber"
,
NAME
:
"Uber"
,
SETTINGS
: {
CALCULATE_URL
:
"https://gateway.bx/calculate.php"
,
CREATE_DELIVERY_REQUEST_URL
:
"https://gateway.bx/create_delivery_request.php"
,
CANCEL_DELIVERY_REQUEST_URL
:
"https://gateway.bx/cancel_delivery_request.php"
,
HAS_CALLBACK_TRACKING_SUPPORT
:
"Y"
,
CONFIG
: [
{
TYPE
:
"STRING"
,
CODE
:
"MY_FIRST_SETTING"
,
NAME
:
"My first setting"
,
},
{
TYPE
:
"STRING"
,
CODE
:
"MY_SECOND_SETTING"
,
NAME
:
"My second setting"
,
},
],
},
PROFILES
: [
{
NAME
:
"Taxi"
,
CODE
:
"TAXI"
,
DESCRIPTION
:
"Taxi Delivery"
,
},
{
NAME
:
"Cargo"
,
CODE
:
"CARGO"
,
DESCRIPTION
:
"Cargo Delivery"
,
},
],
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
'sale.delivery.handler.add'
,
[
'CODE'
=>
'uber'
,
'NAME'
=>
'Uber'
,
'SETTINGS'
=> [
'CALCULATE_URL'
=>
'https://gateway.bx/calculate.php'
,
'CREATE_DELIVERY_REQUEST_URL'
=>
'https://gateway.bx/create_delivery_request.php'
,
'CANCEL_DELIVERY_REQUEST_URL'
=>
'https://gateway.bx/cancel_delivery_request.php'
,
'HAS_CALLBACK_TRACKING_SUPPORT'
=>
'Y'
,
'CONFIG'
=> [
[
'TYPE'
=>
'STRING'
,
'CODE'
=>
'MY_FIRST_SETTING'
,
'NAME'
=>
'My first setting'
,
],
[
'TYPE'
=>
'STRING'
,
'CODE'
=>
'MY_SECOND_SETTING'
,
'NAME'
=>
'My second setting'
,
],
],
},
'PROFILES'
=> [
[
'NAME'
=>
'Taxi'
,
'CODE'
=>
'TAXI'
,
'DESCRIPTION'
=>
'Taxi Delivery'
,
},
[
'NAME'
=>
'Cargo'
,
'CODE'
=>
'CARGO'
,
'DESCRIPTION'
=>
'Cargo Delivery'
,
},
],
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
If the handler is successfully added, the method will return its identifier. If you receive an
error
, refer to the documentation for possible errors in the method
sale.delivery.handler.add
.
{
"result"
:
23
,
"time"
:
{
"start"
:
1714736790.260814
,
"finish"
:
1714736791.896773
,
"duration"
:
1.6359591484069824
,
"processing"
:
0.03880000114440918
,
"date_start"
:
"2024-05-03T14:46:30+02:00"
,
"date_finish"
:
"2024-05-03T14:46:31+02:00"
}
}
2 Create Delivery Service
2.Create Delivery Service
We will create the delivery service using the method
sale.delivery.add
. We will pass the following parameters to the method:
REST_CODE
— symbolic code of the delivery handler. We will specify
uber
, which we set in the first step.
NAME
— name of the delivery service, for example,
Uber Taxi
.
CURRENCY
— symbolic code of the currency. We will pass
USD
. You can get a list of currencies using the method
crm.currency.list
.
ACTIVE
— flag indicating whether the delivery service is active. We will set it to
Y
.
CONFIG
— values of the handler's settings. We will pass values for
MY_FIRST_SETTING
and
MY_SECOND_SETTING
, which we set in the first step.
JS
PHP
BX24
.
callMethod
(
'sale.delivery.add'
,
{
REST_CODE
:
"uber"
,
NAME
:
"Uber Taxi"
,
CURRENCY
:
"USD"
,
ACTIVE
:
"Y"
,
CONFIG
: [
{
CODE
:
"MY_FIRST_SETTING"
,
VALUE
:
"My first setting value"
,
},
{
CODE
:
"MY_SECOND_SETTING"
,
VALUE
:
"My second setting value"
,
},
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
'sale.delivery.add'
,
[
'REST_CODE'
=>
'uber'
,
'NAME'
=>
'Uber Taxi'
,
'CURRENCY'
=>
'USD'
,
'ACTIVE'
=>
'Y'
,
'CONFIG'
=> [
[
'CODE'
=>
'MY_FIRST_SETTING'
,
'VALUE'
=>
'My first setting value'
,
},
[
'CODE'
=>
'MY_SECOND_SETTING'
,
'VALUE'
=>
'My second setting value'
,
},
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
If the delivery service is successfully created, the method will return the parent service object and an array of profiles. If you receive an
error
, refer to the documentation for possible errors in the method
sale.delivery.add
.
{
"result"
:
{
"parent"
:
{
"NAME"
:
"Uber Taxi"
,
"ACTIVE"
:
"Y"
,
"DESCRIPTION"
:
""
,
"CURRENCY"
:
"USD"
,
"ID"
:
226
,
"PARENT_ID"
:
null
,
"SORT"
:
100
,
"LOGOTYPE"
:
null
}
,
"profiles"
:
[
{
"NAME"
:
"Taxi"
,
"ACTIVE"
:
"Y"
,
"DESCRIPTION"
:
"Taxi Delivery"
,
"CURRENCY"
:
"USD"
,
"ID"
:
227
,
"PARENT_ID"
:
226
,
"SORT"
:
100
,
"LOGOTYPE"
:
null
}
,
{
"NAME"
:
"Cargo"
,
"ACTIVE"
:
"Y"
,
"DESCRIPTION"
:
"Cargo Delivery"
,
"CURRENCY"
:
"USD"
,
"ID"
:
228
,
"PARENT_ID"
:
226
,
"SORT"
:
100
,
"LOGOTYPE"
:
null
}
]
}
,
"time"
:
{
"start"
:
1714737122.600765
,
"finish"
:
1714737122.894801
,
"duration"
:
0.2940359115600586
,
"processing"
:
0.0942530632019043
,
"date_start"
:
"2024-05-03T14:52:02+02:00"
,
"date_finish"
:
"2024-05-03T14:52:02+02:00"
}
}
3 Create Shipment Properties
3.Create Shipment Properties
In the shipment, the manager specifies the shipping address and delivery address. We will sequentially create two properties
Address From
and
Address To
using the method
sale.shipmentproperty.add
.
Property Address From
Property Address From
We will pass an object
fields
with the values of the
Address From
property fields to the method.
personTypeId
— identifier of the payer type. We will pass
3
. You can get a list of types using the method
sale.persontype.list
.
propsGroupId
— identifier of the property group. We will specify
6
. You can get a list of groups using the method
sale.propertygroup.list
.
name
— name of the shipment property. We will specify
Address From
.
active
— flag indicating whether it is active. We will pass
Y
.
sort
— sorting.
type
— type of the shipment property. We will pass
ADDRESS
. For a list of possible values, see the documentation for the method
sale.shipmentproperty.add
.
required
— flag indicating whether the property is required. We will specify
Y
.
isAddressFrom
— flag indicating whether the shipment property is used as the sender's address. We will pass
Y
.
JS
PHP
BX24
.
callMethod
(
'sale.shipmentproperty.add'
, {
fields
: {
personTypeId
:
3
,
propsGroupId
:
6
,
name
:
"Address From"
,
active
:
"Y"
,
sort
:
"100"
,
type
:
"ADDRESS"
,
required
:
"Y"
,
isAddressFrom
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
'sale.shipmentproperty.add'
,
[
'fields'
=> [
'personTypeId'
=>
3
,
'propsGroupId'
=>
6
,
'name'
=>
'Address From'
,
'active'
=>
'Y'
,
'sort'
=>
'100'
,
'type'
=>
'ADDRESS'
,
'required'
=>
'Y'
,
'isAddressFrom'
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
If the property is successfully added, the method will return a
property
object with the property identifier. If you receive an
error
, refer to the documentation for possible errors in the method
sale.shipmentproperty.add
.
{
"result"
:
{
"property"
:
{
"active"
:
"Y"
,
"code"
:
""
,
"defaultValue"
:
""
,
"description"
:
""
,
"id"
:
102
,
"isAddressFrom"
:
"Y"
,
"isAddressTo"
:
"N"
,
"maxLength"
:
""
,
"name"
:
"Address From"
,
"personTypeId"
:
3
,
"propsGroupId"
:
6
,
"required"
:
"Y"
,
"settings"
:
[
]
,
"sort"
:
100
,
"type"
:
"ADDRESS"
,
"xmlId"
:
""
}
}
,
"time"
:
{
"start"
:
1714741422.531968
,
"finish"
:
1714741422.644666
,
"duration"
:
0.11269783973693848
,
"processing"
:
0.06191205978393555
,
"date_start"
:
"2024-05-03T15:43:42+02:00"
,
"date_finish"
:
"2024-05-03T15:43:42+02:00"
}
}
Property Address To
Property Address To
In the
fields
object for the
Address To
property, we will pass the name
Address To
. The other parameters will be similar to
Address From
.
JS
PHP
BX24
.
callMethod
(
'sale.shipmentproperty.add'
, {
fields
: {
personTypeId
:
3
,
propsGroupId
:
6
,
name
:
"Address To"
,
active
:
"Y"
,
sort
:
"100"
,
type
:
"ADDRESS"
,
required
:
"Y"
,
isAddressTo
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
'sale.shipmentproperty.add'
,
[
'fields'
=> [
'personTypeId'
=>
3
,
'propsGroupId'
=>
6
,
'name'
=>
'Address To'
,
'active'
=>
'Y'
,
'sort'
=>
'100'
,
'type'
=>
'ADDRESS'
,
'required'
=>
'Y'
,
'isAddressTo'
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
If the property is successfully added, the method will return a
property
object with the property identifier. If you receive an
error
, refer to the documentation for possible errors in the method
sale.shipmentproperty.add
.
{
"result"
:
{
"property"
:
{
"active"
:
"Y"
,
"code"
:
""
,
"defaultValue"
:
""
,
"description"
:
""
,
"id"
:
103
,
"isAddressFrom"
:
"N"
,
"isAddressTo"
:
"Y"
,
"maxLength"
:
""
,
"name"
:
"Address To"
,
"personTypeId"
:
3
,
"propsGroupId"
:
6
,
"required"
:
"Y"
,
"settings"
:
[
]
,
"sort"
:
100
,
"type"
:
"ADDRESS"
,
"xmlId"
:
""
}
}
,
"time"
:
{
"start"
:
1714741719.195657
,
"finish"
:
1714741719.368018
,
"duration"
:
0.17236113548278809
,
"processing"
:
0.0712430477142334
,
"date_start"
:
"2024-05-03T15:48:39+02:00"
,
"date_finish"
:
"2024-05-03T15:48:39+02:00"
}
}
4 Link Shipment Properties to Delivery Service
4. Link Shipment Properties to Delivery Service
To link the properties
Address From
and
Address To
to the profiles
Taxi
and
Cargo
, we will call the method
sale.propertyrelation.add
four times. We will pass an object
fields
with the values for linking properties.
entityId
— identifier of the delivery profile. For the
Taxi
profile, we will pass
227
, and for
Cargo
, we will pass
228
, which were obtained
in the second step
.
entityType
— type of the object. Possible values:
P
— payment system,
D
— delivery,
L
— landing,
T
— trading platform. We will specify the value
D
.
propertyId
— identifier of the property. For
Address From
, we will specify
102
, and for
Address To
, we will specify
103
, which were obtained
in the third step
.
JS
PHP
BX24
.
callMethod
(
'sale.propertyrelation.add'
,
{
fields
: {
entityId
:
227
,
entityType
:
'D'
,
propertyId
:
102
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
'sale.propertyrelation.add'
,
[
'fields'
=> [
'entityId'
=>
227
,
'entityType'
=>
'D'
,
'propertyId'
=>
102
]
]
);
We will call the method
sale.propertyrelation.add
in sequence.
Service
Taxi
, property
Address From
— pass
entityId: 227, propertyId: 102
.
Service
Taxi
, property
Address To
— pass
entityId: 227, propertyId: 103
.
Service
Cargo
, property
Address From
— pass
entityId: 228, propertyId: 102
.
Service
Cargo
, property
Address To
— pass
entityId: 228, propertyId: 103
.
If the links are successfully added, the method will return objects with information about them. If you receive an
error
, refer to the documentation for possible errors in the method
sale.propertyrelation.add
.
{
"result"
:
{
"propertyRelation"
:
{
"entityId"
:
227
,
"entityType"
:
"D"
,
"propertyId"
:
102
}
}
,
"time"
:
{
"start"
:
1712244475.495277
,
"finish"
:
1712244476.402808
,
"duration"
:
0.9075310230255127
,
"processing"
:
0.08538603782653809
,
"date_start"
:
"2024-05-03T18:27:55+02:00"
,
"date_finish"
:
"2024-05-03T18:27:56+02:00"
}
}
5 Add Services to Delivery Services
5. Add Services to Delivery Services
To add an additional service to the delivery service, we will call the method
sale.delivery.extra.service.add
. We will pass the following parameters:
DELIVERY_ID
— identifier of the delivery service to which the service will be linked. For the
Taxi
profile, we will specify the identifier
227
, which was obtained
in the second step
. For other profiles, substitute your own identifier. You can get a list of delivery service identifiers using the method
sale.delivery.getlist
.
ACTIVE
— flag indicating whether the service is active. Possible values:
Y
— yes,
N
— no. We will pass
Y
.
CODE
— symbolic code of the service. We will specify
door_delivery
.
NAME
— name of the service, for example,
Door Delivery
.
TYPE
— type of service. Possible values:
enum
— list,
checkbox
— single service,
quantity
— quantitative service. We will specify
checkbox
.
PRICE
— cost of the service type in the currency of the delivery service. We will specify
1000
.
For services of type
enum
, the cost is specified using the
ITEMS
parameter. For more details, refer to the documentation for the method
sale.delivery.extra.service.add
.
JS
PHP
BX24
.
callMethod
(
'sale.delivery.extra.service.add'
, {
DELIVERY_ID
:
227
,
ACTIVE
:
"Y"
,
CODE
:
"door_delivery"
,
NAME
:
"Door Delivery"
,
TYPE
:
"checkbox"
,
PRICE
:
1000
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
'sale.delivery.extra.service.add'
,
[
'DELIVERY_ID'
=>
227
,
'ACTIVE'
=>
'Y'
,
'CODE'
=>
'door_delivery'
,
'NAME'
=>
'Door Delivery'
,
'TYPE'
=>
'checkbox'
,
'PRICE'
=>
1000
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
If the service is added, the method will return the identifier in the
result
parameter. If you receive an
error
, refer to the documentation for possible errors in the method
sale.delivery.extra.service.add
.
{
"result"
:
140
,
"time"
:
{
"start"
:
1714739042.228152
,
"finish"
:
1714739042.50093
,
"duration"
:
0.2727780342102051
,
"processing"
:
0.09131193161010742
,
"date_start"
:
"2024-05-03T15:24:02+02:00"
,
"date_finish"
:
"2024-05-03T15:24:02+02:00"
}
}
Notifications about Delivery Statuses
Notifications about Delivery Statuses
To send notifications about the progress of delivery, you can use the methods from the group
sale.delivery.request.*
.
Method
Description
sale.delivery.request.update
Updates the delivery order object: status and set of its properties
sale.delivery.request.sendmessage
Sends a message to the manager or recipient about the current status of the delivery order
sale.delivery.request.delete
Notifies about the cancellation of the delivery order on the external system side and attempts to cancel the delivery order on the Bitrix24 side
Copied
Was the article helpful?
Yes
No
Previous
Create a position with a product that does not exist on the site
Next
Typical use-cases for REST API in workflows and Automation rules

---

## Tutorials and use-cases for REST in the AI module

**Source:** https://apidocs.bitrix24.com/tutorials/ai/index

Tutorials and use-cases for REST in the AI module | Bitrix24 REST API and Marketplace Applications
Tutorials and use-cases for REST in the AI module
Tutorials and use-cases for REST in the AI module
Add a New Prompt "Joke"
Was the article helpful?
Yes
No
Previous
How to bulk terminate workflows with a date filter
Next
Add a new prompt "Joke"

---

## Add a New Prompt "Joke"

**Source:** https://apidocs.bitrix24.com/tutorials/ai/add-joke-prompt

Add a New Prompt "Joke" | Bitrix24 REST API and Marketplace Applications
Add a New Prompt "Joke"
Add a New Prompt "Joke"
Registering a new prompt can be done using the method
ai.prompt.register
. Let's look at how to use it by adding a category for jokes.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'ai.prompt.register'
,
{
category
: [
"livefeed"
,
"livefeed_comments"
],
code
:
'rest_joke'
,
icon
:
'smile'
,
prompt
:
'Tell a joke'
,
translate
: {
"en"
:
"A joke"
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
'ai.prompt.register'
,
[
'category'
=> [
"livefeed"
,
"livefeed_comments"
],
'code'
=>
'rest_joke'
,
'icon'
=>
'smile'
,
'prompt'
=>
'Tell a joke'
,
'translate'
=> [
"en"
=>
"A joke"
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
After executing the command, a CoPilot option will appear that can generate jokes.
The "Joke" menu item is now clickable. Let's make it a parent item by adding sub-items (after this, the parent item will no longer be clickable).
To do this, you need to add the parent section code
parent_code
to the original code, as well as
sort
for sorting the items among themselves.
JS
PHP
BX24
.
callMethod
(
'ai.prompt.register'
,
{
category
: [
"livefeed"
,
"livefeed_comments"
],
code
:
'rest_joke_wolf'
,
icon
:
'smile'
,
prompt
:
'Tell a joke about a wolf'
,
translate
: {
"en"
:
"A joke about wolf"
},
parent_code
:
'rest_joke'
,
sort
:
100
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
'ai.prompt.register'
,
[
'category'
=> [
"livefeed"
,
"livefeed_comments"
],
'code'
=>
'rest_joke_wolf'
,
'icon'
=>
'smile'
,
'prompt'
=>
'Tell a joke about a wolf'
,
'translate'
=> [
"en"
=>
"A joke about wolf"
],
'parent_code'
=>
'rest_joke'
,
'sort'
=>
100
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
To embed a sub-item into existing items, find out the code of that item and use the previous code. The code can be found by opening the comment on the post in the news feed. At this moment, a command is sent to retrieve information about CoPilot, where everything is shown.
There are also visual categories where you can place your items.
Pass the parameter
section
in the command, which can be either
create
or
edit
. This visual separation indicates whether the pre-prompt changes text or creates it.
How to Change a Prompt
How to Change a Prompt
If you no longer need the pre-prompt or want to change it, execute the command
ai.prompt.unregister
:
JS
PHP
BX24
.
callMethod
(
'ai.prompt.unregister'
,
{
code
:
'rest_joke_wolf'
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
'ai.prompt.unregister'
,
[
'code'
=>
'rest_joke_wolf'
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
Copied
Was the article helpful?
Yes
No
Previous
Tutorials and use-cases of REST in the AI module
Next
Example of Creating a Chatbot

---

## Example of Creating a Chatbot

**Source:** https://apidocs.bitrix24.com/tutorials/chat-bots/index

Example of Creating a Chatbot | Bitrix24 REST API and Marketplace Applications
Chatbot Code
Example of Creating a Chatbot
Chatbot Code
Launching the Chatbot on the Cloud Account
Launching the Chatbot for On-Premise Account
As an example, let's create a chatbot that will inform the user about their overdue tasks.
The chatbot will know and process only one command — "What's burning?", returning a list of overdue tasks. Similarly, its functionality can always be expanded to receive necessary reports directly in the chat based on any data in
Bitrix24
.
Chatbot Code
Chatbot Code
<?php
/**
* Useful chatbot with reports for Bitrix24
*/
$appsConfig
=
array
();
$configFileName
=
'/config_'
.
trim
(
str_replace
(
'.'
,
'_'
,
$_REQUEST
[
'auth'
][
'domain'
])) .
'.php'
;
if
(
file_exists
(
__DIR__
.
$configFileName
)) {
include_once
__DIR__
.
$configFileName
;
}
// receive event "new message for bot"
if
(
$_REQUEST
[
'event'
] ==
'ONIMBOTMESSAGEADD'
) {
// check the event — register this application or not
if
(!
isset
(
$appsConfig
[
$_REQUEST
[
'auth'
][
'application_token'
]])) {
return
false
;
}
// response time
$arReport
=
getAnswer
(
$_REQUEST
[
'data'
][
'PARAMS'
][
'MESSAGE'
],
$_REQUEST
[
'data'
][
'PARAMS'
][
'FROM_USER_ID'
]);
$arReport
[
'attach'
][] =
array
(
"MESSAGE"
=>
'Once you deal with these tasks, just ask again [send=what is burning]What\'s burning?[/send] and I will provide a new summary!'
);
// send answer message
$result
=
restCommand
(
'imbot.message.add'
,
array
(
"DIALOG_ID"
=>
$_REQUEST
[
'data'
][
'PARAMS'
][
'DIALOG_ID'
],
"MESSAGE"
=>
$arReport
[
'title'
] .
"\n"
.
$arReport
[
'report'
] .
"\n"
,
"ATTACH"
=>
array_merge
(
$arReport
[
'attach'
]
),
),
$_REQUEST
[
"auth"
]);
}
// receive event "open private dialog with bot" or "join bot to group chat"
else
{
if
(
$_REQUEST
[
'event'
] ==
'ONIMBOTJOINCHAT'
) {
// check the event — register this application or not
if
(!
isset
(
$appsConfig
[
$_REQUEST
[
'auth'
][
'application_token'
]])) {
return
false
;
}
// send help message how to use chat-bot. For private chat and for group chat need send different instructions.
$result
=
restCommand
(
'imbot.message.add'
,
array
(
'DIALOG_ID'
=>
$_REQUEST
[
'data'
][
'PARAMS'
][
'DIALOG_ID'
],
'MESSAGE'
=>
'Hello! I am ReportBot, reporting everything as it is.'
,
"ATTACH"
=>
array
(
array
(
'MESSAGE'
=>
'[send=what is burning]What\'s burning?[/send]'
),
),
),
$_REQUEST
[
"auth"
]);
}
// receive event "delete chat-bot"
else
{
if
(
$_REQUEST
[
'event'
] ==
'ONIMBOTDELETE'
) {
// check the event — register this application or not
if
(!
isset
(
$appsConfig
[
$_REQUEST
[
'auth'
][
'application_token'
]])) {
return
false
;
}
// unset application variables
unset
(
$appsConfig
[
$_REQUEST
[
'auth'
][
'application_token'
]]);
// save params
saveParams
(
$appsConfig
);
}
// receive event "Application install"
else
{
if
(
$_REQUEST
[
'event'
] ==
'ONAPPINSTALL'
) {
// handler for events
$handlerBackUrl
= (
$_SERVER
[
'SERVER_PORT'
] ==
443
?
'https'
:
'http'
) .
'://'
.
$_SERVER
[
'SERVER_NAME'
] . (
in_array
(
$_SERVER
[
'SERVER_PORT'
],
array
(
80
,
443
)) ?
''
:
':'
.
$_SERVER
[
'SERVER_PORT'
]) .
$_SERVER
[
'SCRIPT_NAME'
];
// If your application supports different localizations
// use $_REQUEST['data']['LANGUAGE_ID'] to load correct localization
// register new bot
$result
=
restCommand
(
'imbot.register'
,
array
(
'CODE'
=>
'ReportBot'
,
//
string
identifier of the bot, unique within your application, required field
'TYPE'
=>
'B'
,
// Type of bot, B - bot, responses come immediately, H - human, responses come with a delay of
2
to
10
seconds
'EVENT_MESSAGE_ADD'
=>
$handlerBackUrl
,
// Link to the message sending event handler
for
the bot, required field
'EVENT_WELCOME_MESSAGE'
=>
$handlerBackUrl
,
// Link to the event handler
for
opening a dialog with the bot
or
inviting it to a group chat, required field
'EVENT_BOT_DELETE'
=>
$handlerBackUrl
,
// Link to the event handler
for
deleting the bot
from
the client side, required field
'PROPERTIES'
=>
array
( // Personal data of the chatbot, required field
'NAME'
=>
'ReportBot'
,
// Name of the bot, required one of the fields NAME
or
LAST_NAME
'LAST_NAME'
=>
''
,
// Last name of the bot, required one of the fields NAME
or
LAST_NAME
'COLOR'
=>
'AQUA'
,
// Color of the bot
for
the mobile application RED, GREEN, MINT, LIGHT_BLUE, DARK_BLUE, PURPLE, AQUA, PINK, LIME, BROWN, AZURE, KHAKI, SAND, MARENGO, GRAY, GRAPHITE
'EMAIL'
=>
'no@mail.com'
,
// Email
for
contact
'PERSONAL_BIRTHDAY'
=>
'2016-03-23'
,
// Birthday in YYYY-mm-dd format
'WORK_POSITION'
=>
'Reporting on tasks'
,
// Position held, used
as
a description of the bot
'PERSONAL_WWW'
=>
''
,
// Link to the website
'PERSONAL_GENDER'
=>
'M'
,
// Gender of the bot, acceptable values M — male, F — female,
empty
if
not required to specify
'PERSONAL_PHOTO'
=>
'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'
,
// Bot avatar - base64
),
),
$_REQUEST
[
"auth"
]);
// save params
$appsConfig
[
$_REQUEST
[
'auth'
][
'application_token'
]] =
array
(
'BOT_ID'
=>
$result
[
'result'
],
'LANGUAGE_ID'
=>
$_REQUEST
[
'data'
][
'LANGUAGE_ID'
],
);
saveParams
(
$appsConfig
);
// write debug log
// writeToLog($result, 'ReportBot register');
}
}
}
}
/**
* Save application configuration.
*
*
@param
$params
*
*
@return
bool
*/
function
saveParams
(
$params
)
{
$config
=
"<?php\n"
;
$config
.=
"\$appsConfig = "
.
var_export
(
$params
,
true
) .
";\n"
;
$config
.=
"?>"
;
$configFileName
=
'/config_'
.
trim
(
str_replace
(
'.'
,
'_'
,
$_REQUEST
[
'auth'
][
'domain'
])) .
'.php'
;
file_put_contents
(
__DIR__
.
$configFileName
,
$config
);
return
true
;
}
/**
* Send rest query to Bitrix24.
*
*
@param
$method - Rest method, ex: methods
*
@param
array $params - Method params, ex: array()
*
@param
array $auth   - Authorize data, ex: array('domain' => 'https://test.bitrix24.com', 'access_token' => '7inpwszbuu8vnwr5jmabqa467rqur7u6')
*
*
@return
mixed
*/
function
restCommand
(
$method
,
array
$params
=
array
(
),
array
$auth
=
array
(
)
)
{
$queryUrl
=
'https://'
.
$auth
[
'domain'
] .
'/rest/'
.
$method
;
$queryData
=
http_build_query
(
array_merge
(
$params
,
array
(
'auth'
=>
$auth
[
'access_token'
])));
// writeToLog(array('URL' => $queryUrl, 'PARAMS' => array_merge($params, array("auth" => $auth["access_token"]))), 'ReportBot send data');
$curl
=
curl_init
();
curl_setopt_array
(
$curl
,
array
(
CURLOPT_POST           =>
1
,
CURLOPT_HEADER         =>
0
,
CURLOPT_RETURNTRANSFER =>
1
,
CURLOPT_URL            =>
$queryUrl
,
CURLOPT_POSTFIELDS     =>
$queryData
,
));
$result
=
curl_exec
(
$curl
);
curl_close
(
$curl
);
$result
=
json_decode
(
$result
,
1
);
return
$result
;
}
/**
* Generate report based on the command
*
*
@param
string $text string sent by the user
*
@param
int $user identifier of the user who wrote to us
*
*
@return
array
*/
function
getAnswer
(
$command
=
''
,
$user
)
{
switch
(
strtolower
(
$command
)) {
case
'what is burning'
:
$arResult
=
b24BadTasks
(
$user
);
break
;
default
:
$arResult
=
array
(
'title'
=>
'I\'m confused'
,
'report'
=>
'I don\'t understand what you want to know. Or maybe I just can\'t...'
,
);
}
return
$arResult
;
}
function
b24BadTasks
(
$user
)
{
$tasks
=
restCommand
(
'task.item.list'
,
array
(
'ORDER'
=>
array
(
'DEADLINE'
=>
'desc'
),
'FILTER'
=>
array
(
'RESPONSIBLE_ID'
=>
$user
,
'<DEADLINE'
=>
date
(
"Y-m-d"
)),
'PARAMS'
=>
array
(),
'SELECT'
=>
array
()
),
$_REQUEST
[
"auth"
]);
if
(
count
(
$tasks
[
'result'
]) >
0
) {
$arTasks
=
array
();
foreach
(
$tasks
[
'result'
]
as
$id
=>
$arTask
) {
$arTasks
[] =
array
(
'LINK'
=>
array
(
'NAME'
=>
$arTask
[
'TITLE'
],
'LINK'
=>
'https://'
.
$_REQUEST
[
'auth'
][
'domain'
].
'/company/personal/user/'
.
$arTask
[
'RESPONSIBLE_ID'
].
'/tasks/task/view/'
.
$arTask
[
'ID'
].
'/'
)
);
$arTasks
[] =
array
(
'DELIMITER'
=>
array
(
'SIZE'
=>
400
,
'COLOR'
=>
'#c6c6c6'
)
);
}
$arReport
=
array
(
'title'
=>
'Yes, some tasks are overdue, for example:'
,
'report'
=>
''
,
'attach'
=>
$arTasks
);
}
else
{
$arReport
=
array
(
'title'
=>
'You are doing great!'
,
'report'
=>
'Nothing to worry about - no overdue tasks'
,
);
}
return
$arReport
;
}
You can create a new chatbot application either as "for personal use" or in the account for publication to all
Bitrix24
users through the
Market
.
Warning
Using an HTTPS certificate for chatbots is not mandatory, but it is highly recommended to protect client confidential data. The application must be in
UTF-8
encoding.
Launching the Chatbot on the Cloud Account
Launching the Chatbot on the Cloud Account
You can take the example chatbot code, upload it to your server, and launch the chatbot on your account. Publication through the
Market
is not required. In
Bitrix24
, you can install local applications:
In the left menu, expand
Applications
(1) and click on
Developer resources
(2). In the opened slider, select
Other
(3)
Then select the scenario
Local application
:
Configure the settings. At the top, specify the bot's name, in this example — "ReportBot". Then select the application type —
Server
:
Enable the option
Uses only API
. Since the script is written in such a way that it acts as a handler for all events, specify both links to the same URL in the application form.
Finally, grant the application access permissions:
Web messenger (im)
— without this permission, it is impossible to send messages to the user
Creating and managing Chatbots (imbot)
— without these permissions, the application will not be able to register the chatbot
Tasks (task)
and
Tasks (extended rights) (task_extended)
— without these permissions, the application will not be able to generate a report on tasks to inform the user through the chatbot
After these actions, a message will appear in the general chat indicating that a new user — the chatbot named "ReportBot" has joined the account. You can open a chat with it, click on the link "What's burning?" and receive your list of overdue tasks.
Typical use-cases and scenarios
Download
the "EchoBot" example from GitHub
Launching the Chatbot for On-Premise Account
Launching the Chatbot for On-Premise Account
For the on-premise version of
Bitrix24
, the process is slightly different:
Install and activate the PHP extension
cURL
on the server for the application to work correctly. In the BitrixVM virtual machine, this can be done through the menu:
7. Manage pool web servers >
1. Manage PHP extensions
Place the folder with the chatbot on your server or on your product installation
The application files must be accessible externally without authorization. Set the folder with the chatbot to "read for unauthorized users". Access rights settings are performed in folder properties
On the account, go to the local applications installation interface
Applications > Developer resources > Other > Local application
Fill in the settings similarly to the instructions for the cloud account:
specify the name
indicate the path to the handler and the path to the initial installation file
enable the option
Uses only API
add permissions to the application
task
,
task_extended
,
im
,
imbot
Click the
Save
button.
Copied
Was the article helpful?
Yes
No
Previous
Add a new prompt "Joke"
Next
Example of Creating an Open Channel Chatbot

---

## Example of Creating a Chatbot for Open Channels

**Source:** https://apidocs.bitrix24.com/tutorials/chat-bots/open-lines-bot

Example of Creating a Chatbot for Open Channels | Bitrix24 REST API and Marketplace Applications
Example of Creating a Chatbot for Open Channels
Example of Creating a Chatbot for Open Channels
Download the Example Chatbot for Open Channels
Running on Your Account
The process of creating a chatbot for
Open Channels
is similar to
creating a regular chatbot
, but there are two differences:
When creating a chatbot for
Open Channels
, in
imbot.register
, the
TYPE
parameter must be set to
O
.
If you need to extend the capabilities of an existing chatbot, you should pass the new key
OPENLINE => Y
, and then the chatbot will operate in hybrid mode.
In hybrid mode, the chatbot must function correctly in group chats, personal chats, and open channel chats. To achieve this, you need to check the
CHAT_ENTITY_TYPE
parameter in all incoming events (
ONIMBOTMESSAGEADD
and
ONIMBOTJOINCHAT
) — for
Open Channels
, it should be
CHAT_ENTITY_TYPE => LINES
.
In all other respects, this is the familiar and already known
chatbot
.
For closer integration with
Open Channels
, you need to have access permission for the scope
imopenlines
.
With this permission, the following commands will be available:
imopenlines.network.join
— connecting your company's open line to the
Bitrix24
account, after which employees will be able to message you.
imopenlines.bot.session.operator
— switching the conversation to a free operator.
imopenlines.bot.session.transfer
— transferring the conversation to a specific operator.
imopenlines.bot.session.finish
— ending the current session.
Warning
Using an HTTPS certificate for chatbots is not mandatory, but it is highly recommended to protect client confidential data. The application must be encoded in
UTF-8
.
Download the Example Chatbot for Open Channels
Download the Example Chatbot for Open Channels
As an example of a chatbot for open channels, we have prepared the "ITR Bot." You can obtain it in the following ways:
download
from GitHub, file
itr.php
.
find and copy it in the
"Bitrix24 on-premise"
product in the folder
\Bitrix\ImBot\Bot\OpenlinesMenuExample
.
This chatbot serves as the first line of support: initially, all messages will go to it, and only then to employees in the queue. The time after which messages will be forwarded from the chatbot to employees is set in the open line settings.
Additionally, a class for building multi-level menus in chats has been added to the chatbot.
Running on Your Account
Running on Your Account
You can
take the example chatbot code
above, upload it to your server, and run the chatbot on your account as a local application without publishing it through
Marketplace
:
In the left menu under
Applications
(1), go to the
Developer's area
(2) and select
Other
(3):
Use the
Local application
script (4):
Select the application type
Server
and configure its parameters:
Change the bot's name.
Enable the option
Uses only API
and grant the application access permissions for:
Creating and managing Chatbots
— without these permissions, the application will not be able to register the chatbot.
Open Channels
— without these permissions, the application will not be able to work with open channels.
Since the script is written in such a way that it acts as a handler for all events, the URLs in the
Your handler path
and
Initial setup path
fields will lead to the same URL.
After saving the settings, additional fields will appear:
Application code (client_id)
and
Application key (client_secret)
.
Copy the data from these fields and paste it into the
itr.php
file.
In the bot settings, click
Reinstall
. Now the bot is ready to work.
This bot does not publish messages indicating that it has been invited to the account. After installation, it will be available in the open channels settings. Select it as responsible and specify the time after which the conversation will be transferred from the chatbot to the queue for employees:
Note
The client can switch to an operator earlier by sending the message
0
or selecting the menu item
0. Wait operator answer
.
With any chatbot, pressing
0
will redirect the user to an operator; no additional processing is required.
Below is a dialogue: first, "ITR Bot" responds, the client clicks on the menu items, and then the queue switches to the operator as the client selected the menu item
0. Wait operator answer
:
You can configure your own menu in "ITR Bot" in the
itrRun
method:
/**
* Run ITR menu
*
*
@param
$portalId
*
@param
$dialogId
*
@param
$userId
*
@param
string $message
*
@return
bool
*/
function
itrRun
(
$portalId
,
$dialogId
,
$userId
,
$message
=
''
)
{
if
(
$userId
<=
0
)
return
false
;
$menu0
=
new
ItrMenu
(
0
);
$menu0
->
setText
(
'Main menu (#0)'
);
$menu0
->
addItem
(
1
,
'Text'
,
ItrItem
::
sendText
(
'Text message (for #USER_NAME#)'
));
$menu0
->
addItem
(
2
,
'Text without menu'
,
ItrItem
::
sendText
(
'Text message without menu'
,
true
));
$menu0
->
addItem
(
3
,
'Open menu #1'
,
ItrItem
::
openMenu
(
1
));
$menu0
->
addItem
(
0
,
'Wait operator answer'
,
ItrItem
::
sendText
(
'Wait operator answer'
,
true
));
$menu1
=
new
ItrMenu
(
1
);
$menu1
->
setText
(
'Second menu (#1)'
);
$menu1
->
addItem
(
2
,
'Transfer to queue'
,
ItrItem
::
transferToQueue
(
'Transfer to queue'
));
$menu1
->
addItem
(
3
,
'Transfer to user'
,
ItrItem
::
transferToUser
(
1
,
false
,
'Transfer to user #1'
));
$menu1
->
addItem
(
4
,
'Transfer to bot'
,
ItrItem
::
transferToBot
(
'marta'
,
true
,
'Transfer to bot Marta'
,
'Marta not found :('
));
$menu1
->
addItem
(
5
,
'Finish session'
,
ItrItem
::
finishSession
(
'Finish session'
));
$menu1
->
addItem
(
6
,
'Exec function'
,
ItrItem
::
execFunction
(function(
$context
){
$result
=
restCommand
(
'imbot.message.add'
,
Array
(
"DIALOG_ID"
=>
$_REQUEST
[
'data'
][
'PARAMS'
][
'DIALOG_ID'
],
"MESSAGE"
=>
'Function executed (action)'
,
),
$_REQUEST
[
"auth"
]);
writeToLog
(
$result
,
'Exec function'
);
},
'Function executed (text)'
));
$menu1
->
addItem
(
9
,
'Back to main menu'
,
ItrItem
::
openMenu
(
0
));
$itr
=
new
Itr
(
$portalId
,
$dialogId
,
0
,
$userId
);
$itr
->
addMenu
(
$menu0
);
$itr
->
addMenu
(
$menu1
);
$itr
->
run
(
prepareText
(
$message
));
return
true
;
}
Copied
Was the article helpful?
Yes
No
Previous
Example of Creating a Chatbot
Next
Example of Creating a Support Channel

---

## Example of Creating a Support Channel

**Source:** https://apidocs.bitrix24.com/tutorials/chat-bots/support-bot

Example of Creating a Support Channel | Bitrix24 REST API and Marketplace Applications
Example of Creating a Support Channel
Example of Creating a Support Channel
With the
Open Channels
module, you can organize technical support for any
Bitrix24
application, including chatbots.
To do this, follow these steps:
Go to the
Contact Center
section and connect the communication channel
Bitrix24.Network
:
After that, the connection settings form for
Bitrix24.Network
will be available:
Be sure to fill in the
Name
and
Short Description
fields, and set an
Avatar
— this will help clients find you more easily.
Once a user enters your Open Channel
Bitrix24.Network
, they will automatically receive a welcome message:
Create a new open line for technical support for your product or select an existing one:
Using the method
imopenlines.network.join
, you can automatically connect your open line to the user account:
$result
=
restCommand
(
'imopenlines.network.join'
,
Array
(
'CODE'
=>
'a588e1a88baaf301b9d0b0b33b1eefc2b'
// code
for
searching
from
the connectors page
),
$_REQUEST
[
"auth"
]
);
After setting up the Open Line, you can send a welcome message to the client using the method
imopenlines.network.message.add
:
Thank you
for
setting up, we will be happy to help. If you have any questions, feel free to write in this chat. Have a great day! :)
Note
restCommand
is a method for sending data to
Bitrix24
, this method is available in
EchoBot
and is presented here as an example. You can use your own function or the javascript method
BX24.callMethod
, as well as
bitrix24-php-sdk
. You can also open such a support channel through the javascript method
BX24.im.openMessenger
.
Copied
Was the article helpful?
Yes
No
Previous
Example of Creating an Open Channel Chatbot
Next
User scenarios and example

---

## Typical use-cases and scenarios example

**Source:** https://apidocs.bitrix24.com/tutorials/telephony/index

Typical use-cases and scenarios example | Bitrix24 REST API and Marketplace Applications
Typical use-cases and scenarios example
Typical use-cases and scenarios example
We are still updating this page
Some data may be missing — we will fill it in shortly.
An incoming call to the PBX on a specific user's internal number should display the call card for the employee in Bitrix24, using the method
telephony.externalcall.register
.
An incoming call from an unknown number, not registered in the CRM, should enter a processing queue from the list of users who should answer incoming calls:
Simultaneous queue: all employees who are not currently answering other calls will simultaneously see the call card when one of them starts answering the call, while the others will lose the card. First, we use
telephony.externalcall.register
for the first in the queue, then
telephony.externalcall.show
for the others.
Sequential queue: each of the employees in the queue who are not currently answering other calls will see the call card for a certain period, 3-5-7 seconds. If the employee does not start answering the call, the card disappears, and the call is transferred to the next in line. First, we use
telephony.externalcall.register
for the first in the queue, then
telephony.externalcall.hide
and
telephony.externalcall.show
for the next.
An incoming call from a known number is displayed as a call card in Bitrix24 for the manager responsible for the corresponding CRM entity. First,
telephony.externalcall.register
with
SHOW = 0
, which will return either
CREATED_LEAD
if the phone was not found in the CRM and a new lead was created, or a pair of
CRM_ENTITY_TYPE
and
CRM_ENTITY_ID
indicating the found existing client. Simultaneously,
CRM_ACTIVITY_ID
is returned with the identifier of the new activity in the CRM, where the call will be recorded later. Knowing the identifier of the entity in the CRM, we can use CRM methods to get the identifier of the manager responsible for the client, transfer the call to them, and show them the call card using
telephony.externalcall.show
.
An employee in Bitrix24 clicks on the phone number in the CRM interface. The application initiates an outgoing call to the specified number on the PBX side, triggering the event
onexternalcallstart
, and the employee sees the call card using
telephony.externalcall.register
.
The call is completed, either incoming or outgoing. The fact of the call and the recording are recorded in relation to the CRM entity using
telephony.externalcall.finish
. If at the time of call completion the recording is not yet ready on the PBX, instead of
telephony.externalcall.finish
, we first simply hide the call card using
telephony.externalcall.hide
, and then, when the recording is ready, we call
telephony.externalcall.finish
.
An incoming call occurred on the PBX at a time when there was no connection between the PBX and Bitrix24 for some reason. After the connection is restored, information about the occurred call is recorded in Bitrix24, points 1-3, but without showing the call card – a sequential call of the methods
telephony.externalcall.register
with the parameter
SHOW = 0
and
telephony.externalcall.finish
.
Note
To ensure the recording is added to the call during the calling scenario, applications must pass
CALL_LIST_ID
that they receive in the
event
at the start of the call.
Example
Example
<?php
/**
* Created by PhpStorm.
* User: sv
* Date: 01.11.16
* Time: 10:44
*/
// ini_set('display_errors','Off');
// forming the URL of our script for use in AJAX requests from the application interface
$script_url
= (
$_SERVER
[
'SERVER_PORT'
] ==
443
?
'https'
:
'http'
) .
'://'
.
$_SERVER
[
'SERVER_NAME'
] . (
in_array
(
$_SERVER
[
'SERVER_PORT'
],
array
(
80
,
443
)) ?
''
:
':'
.
$_SERVER
[
'SERVER_PORT'
]) .
$_SERVER
[
'SCRIPT_NAME'
];
$appsConfig
=
array
();
$b24domain
=
$_REQUEST
[
'DOMAIN'
];
// if we received an outgoing call event, then authorization is passed through the auth node in the request array
// but we only need the domain from there, we have already saved the authorization by this point
if
(!
empty
(
$_REQUEST
[
'auth'
])) {
$b24domain
=
$_REQUEST
[
'auth'
][
'domain'
];
}
$configFileName
=
'/config_'
.
trim
(
str_replace
(
'.'
,
'_'
,
$b24domain
)) .
'.php'
;
echo
getcwd
().
$configFileName
.
"<br/>"
;
if
(
file_exists
(
getcwd
() .
$configFileName
)) {
include_once
getcwd
() .
$configFileName
;
}
else
{
// saving tokens for the user setting up the application
$appsConfig
=
$_REQUEST
;
saveParams
(
$appsConfig
);
// registering the outgoing call event
restCommand
(
'event.bind'
,
array
(
"event"
=>
'ONEXTERNALCALLSTART'
,
"handler"
=>
$script_url
.
"?action=outcoming"
,
),
$b24domain
,
$appsConfig
[
'AUTH_ID'
]);
/* test event to check the mechanism
restCommand('event.bind', array(
"event" => 'ONAPPTEST',
"handler" => $script_url."?action=test",
),
$b24domain, $appsConfig['AUTH_ID']);
*/
}
$action
=
$_REQUEST
[
'action'
];
// we just launched the application in the Bitrix24 interface
if
(
$action
==
''
) {
?>
<html>
<head>
<meta charset=
"utf-8"
><meta http-equiv=
"X-UA-Compatible"
content=
"IE=edge"
>
<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"
></script>
<!-- Latest compiled
and
minified CSS -->
<link rel=
"stylesheet"
href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
integrity=
"sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u"
crossorigin=
"anonymous"
>
<!-- Optional theme -->
<link rel=
"stylesheet"
href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap-theme.min.css"
integrity=
"sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp"
crossorigin=
"anonymous"
>
<!-- Latest compiled
and
minified JavaScript -->
<script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"
integrity=
"sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa"
crossorigin=
"anonymous"
></script>
<script src=
"//api.bitrix24.com/api/v1/"
></script>
</head>
<body>
<div
class
="
form
-
group
">
<
label
for
="
IncomingNumber
">
Incoming
call
number
</
label
>
<
input
type
="
text
"
class
="
form
-
control
"
id
="
incomingNumber
"
placeholder
="
phone
">
</
div
>
<
div
class
="
form
-
group
">
<
label
for
="
user1
">
User
1</
label
>
<
input
type
="
text
"
class
="
form
-
control
"
id
="
user1
"
placeholder
="
user
id
"
value
="1">
</
div
>
<
div
class
="
form
-
group
">
<
label
for
="
user2
">
User
2 (
for
call
transfer
)</
label
>
<
input
type
="
text
"
class
="
form
-
control
"
id
="
user2
"
placeholder
="
user
id
">
</
div
>
<
a
class
="
btn
btn
-
default
"
href
="#"
role
="
button
"
id
="
incoming
">
Incoming
</
a
>
<
a
class
="
btn
btn
-
default
"
href
="#"
role
="
button
"
id
="
redirect
">
Redirect
</
a
>
<
a
class
="
btn
btn
-
default
"
href
="#"
role
="
button
"
id
="
drop
">
Drop
</
a
>
<
a
class
="
btn
btn
-
default
"
href
="#"
role
="
button
"
id
="
test
">
Event
test
</
a
>
<
div
id
="
debug
"></
div
>
<?
php
//
if
you
'
re
curious
,
you
can
see
what
authorization
parameters
Bitrix24
passes
to
the
application
script
//
when
the
application
is
executed
in
a
frame
inside
Bitrix24
//
echo
"<
pre
>";
//
print_r
($
_REQUEST
);
//
echo
"</
pre
>";
?>
<
script
>
$( "#
incoming
" ).
on
( "
click
",
function
(
event
)
{
// here we simulate the operation of an external PBX, in particular, receiving an incoming call
// hence AJAX, passing authorization parameters, etc.
// in real practice, REST telephony will be called from the PBX side, and there we have already saved
// authorization tokens (see $appsConfig) and we know which Bitrix24 to send the
// REST call to, which users to show the card to, etc.
auth = BX24.
getAuth
();
$.
ajax
({
url
:
"<?=
$script_url
?>"
,
data
: {
action
:
'incoming'
,
user1
: $(
"#user1"
).
val
(),
phone: $(
"#incomingNumber"
).
val
(),
DOMAIN: auth[
'domain'
]
},
success:
function
(
result
)
{
$(
"#debug"
).
html
( result );
}
});
});
$(
"#redirect"
).
on
(
"click"
, function( event ) {
auth = BX24.
getAuth
();
$.
ajax
({
url
:
"<?=
$script_url
?>"
,
data
: {
action
:
'redirect'
,
user1
: $(
"#user1"
).
val
(),
user2: $(
"#user2"
).
val
(),
DOMAIN: auth[
'domain'
]
},
success:
function
(
result
)
{
$(
"#debug"
).
html
( result );
}
});
});
$(
"#drop"
).
on
(
"click"
, function( event ) {
auth = BX24.
getAuth
();
$.
ajax
({
url
:
"<?=
$script_url
?>"
,
data
: {
action
:
'drop'
,
user1
: $(
"#user1"
).
val
(),
user2: $(
"#user2"
).
val
(),
DOMAIN: auth[
'domain'
]
},
success:
function
(
result
)
{
$(
"#debug"
).
html
( result );
}
});
});
/* initiating a test event on the server script side, nothing important
$( "#test" ).on( "click", function( event ) {
auth = BX24.getAuth();
$.ajax({
url: "<?=$script_url?>",
data: {
action: 'eventtest',
DOMAIN: auth['domain']
},
success: function( result ) {
$( "#debug" ).html( result );
}
});
});
*/
</script>
</body>
</html>
<?php
}
else
{
switch
(
$action
) {
case
'test'
:
writeToLog
(
array
(
'test'
=>
$_REQUEST
),
'telephony test event'
);
break
;
case
'outcoming'
:
writeToLog
(
array
(
'outcoming'
=>
$_REQUEST
),
'telephony event'
);
$result
=
restCommand
(
'telephony.externalCall.register'
,
array
(
"USER_ID"
=>
$_REQUEST
[
'data'
][
'USER_ID'
],
"PHONE_NUMBER"
=>
$_REQUEST
[
'data'
][
'PHONE_NUMBER'
],
"TYPE"
=>
'1'
,
"CRM_CREATE"
=>
1
),
$b24domain
,
$appsConfig
[
'AUTH_ID'
]);
$appsConfig
[
'CALL'
] =
$result
[
'result'
];
saveParams
(
$appsConfig
);
break
;
case
'eventtest'
:
writeToLog
(
array
(
'eventtest'
=>
$_REQUEST
),
'test event call'
);
$result
=
restCommand
(
'event.test'
,
array
(
),
$b24domain
,
$appsConfig
[
'AUTH_ID'
]);
echo
"test event call"
;
break
;
case
'incoming'
:
$result
=
restCommand
(
'telephony.externalCall.register'
,
array
(
"USER_ID"
=>
$_REQUEST
[
'user1'
],
"PHONE_NUMBER"
=>
$_REQUEST
[
'phone'
],
"TYPE"
=>
'2'
,
"CRM_CREATE"
=>
true
),
$b24domain
,
$appsConfig
[
'AUTH_ID'
]);
$appsConfig
[
'CALL'
] =
$result
[
'result'
];
saveParams
(
$appsConfig
);
echo
"incoming <pre>"
;
print_r
(
$appsConfig
);
echo
"</pre>"
;
break
;
case
'redirect'
:
echo
"redirect <pre>"
;
print_r
(
$appsConfig
);
echo
"</pre>"
;
if
(
$appsConfig
[
'CALL'
][
'CALL_ID'
] !=
''
) {
$result
=
restCommand
(
'telephony.externalCall.hide'
,
array
(
"CALL_ID"
=>
$appsConfig
[
'CALL'
][
'CALL_ID'
],
"USER_ID"
=>
$_REQUEST
[
'user1'
]
),
$b24domain
,
$appsConfig
[
'AUTH_ID'
]);
$result
=
restCommand
(
'telephony.externalCall.show'
,
array
(
"CALL_ID"
=>
$appsConfig
[
'CALL'
][
'CALL_ID'
],
"USER_ID"
=>
$_REQUEST
[
'user2'
]
),
$b24domain
,
$appsConfig
[
'AUTH_ID'
]);
}
echo
"redirected to "
.
$_REQUEST
[
'user2'
];
break
;
case
'drop'
:
writeToLog
(
array
(
'config'
=>
$appsConfig
),
'call is finishing'
);
if
(
$appsConfig
[
'CALL'
][
'CALL_ID'
] !=
''
) {
$result
=
restCommand
(
'telephony.externalCall.finish'
,
array
(
"CALL_ID"
=>
$appsConfig
[
'CALL'
][
'CALL_ID'
],
"USER_ID"
=>
$_REQUEST
[
'user1'
],
"DURATION"
=>
'120'
,
"STATUS_CODE"
=>
'200'
,
"ADD_TO_CHAT"
=>
true
),
$b24domain
,
$appsConfig
[
'AUTH_ID'
]);
$appsConfig
[
'CALL'
] =
$result
[
'result'
];
saveParams
(
$appsConfig
);
echo
"finished <pre>"
;
print_r
(
$appsConfig
);
echo
"</pre>"
;
writeToLog
(
array
(
'request'
=>
$_REQUEST
,
'config'
=>
$appsConfig
),
'call is finished'
);
}
echo
"dropped and saved"
;
break
;
}
}
?>
/**
* Save application configuration.
*
*
@param
$params
*
*
@return
bool
*/
function
saveParams
(
$params
)
{
$config
=
"<?php\n"
;
$config
.=
"\$appsConfig = "
.
var_export
(
$params
,
true
) .
";\n"
;
$config
.=
"?>"
;
$configFileName
=
'/config_'
.
trim
(
str_replace
(
'.'
,
'_'
,
$_REQUEST
[
'DOMAIN'
])) .
'.php'
;
file_put_contents
(
getcwd
() .
$configFileName
,
$config
);
return
true
;
}
/**
* Send rest query to Bitrix24.
*
*
@param
$method - Rest method, ex: methods
*
@param
array $params - Method params, ex: array()
*
@param
array $auth   - Authorize data, ex: array('domain' => 'https://test.bitrix24.com', 'access_token' => '7inpwszbuu8vnwr5jmabqa467rqur7u6')
*
*
@return
mixed
*/
function
restCommand
(
$method
,
array
$params
=
array
(
),
$auth_domain
,
$access_token
)
{
$queryUrl
=
'https://'
.
$auth_domain
.
'/rest/'
.
$method
;
$queryData
=
http_build_query
(
array_merge
(
$params
,
array
(
'auth'
=>
$access_token
)));
writeToLog
(
array
(
'URL'
=>
$queryUrl
,
'PARAMS'
=>
array_merge
(
$params
,
array
(
"auth"
=>
$access_token
))),
'telephony send data'
);
$curl
=
curl_init
();
curl_setopt_array
(
$curl
,
array
(
CURLOPT_SSL_VERIFYPEER =>
0
,
CURLOPT_POST		   =>
1
,
CURLOPT_HEADER		 =>
0
,
CURLOPT_RETURNTRANSFER =>
1
,
CURLOPT_URL			=>
$queryUrl
,
CURLOPT_POSTFIELDS	 =>
$queryData
,
CURLOPT_VERBOSE		 =>
1
));
$result
=
curl_exec
(
$curl
);
writeToLog
(
array
(
'raw'
=>
$result
),
'telephony got data'
);
curl_close
(
$curl
);
$result
=
json_decode
(
$result
,
1
);
return
$result
;
}
/**
* Write data to log file.
*
*
@param
mixed  $data
*
@param
string $title
*
*
@return
bool
*/
function
writeToLog
(
$data
,
$title
=
''
)
{
$log
=
"\n------------------------\n"
;
$log
.=
date
(
"Y.m.d G:i:s"
) .
"\n"
;
$log
.= (
strlen
(
$title
) >
0
?
$title
:
'DEBUG'
) .
"\n"
;
$log
.=
print_r
(
$data
,
1
);
$log
.=
"\n------------------------\n"
;
file_put_contents
(
getcwd
() .
'/tel.log'
,
$log
, FILE_APPEND);
return
true
;
}
?>
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Example of Creating a Support Channel
Next
Typical use-cases for REST API in Tasks and tutorials

---

## Tutorials and use-cases for REST in the Open Channels module

**Source:** https://apidocs.bitrix24.com/tutorials/openlines/index

Tutorials and use-cases for REST in the Open Channels module | Bitrix24 REST API and Marketplace Applications
Tutorials and use-cases for REST in the Open Channels module
Tutorials and use-cases for REST in the Open Channels module
How to Create an Open Channel Connector for Chat on the Site
Was the article helpful?
Yes
No
Previous
How to attach a task to an SPA
Next
How to create an open channels connector for chat on the site

---

## How to Create an Open Channel Connector for Chat on the Site

**Source:** https://apidocs.bitrix24.com/tutorials/openlines/example-connector

How to Create an Open Channel Connector for Chat on the Site | Bitrix24 REST API and Marketplace Applications
How to Create an Open Channel Connector for Chat on the Site
How to Create an Open Channel Connector for Chat on the Site
1. Create the file function.php
getConnectorID
getChat
saveMessage
getLine
setLine
convertBB
Example code for the file function.php
2. Create the file install_connector.php
Set up the event handler URL
Create a directory to store chats
Register the connector
Register the event handler
Example code for the file install_connector.php
3. Create the file handler.php
Set up widget parameters
Activate the connector
Supplement the connector settings
Save the open line
Confirm message delivery
Example code for the file handler.php
4. Create the file ajax.php
Prepare variables
Load chat history
Send a message
Example code for the file ajax.php
5. Create the file index.php
Example code for the file index.php
6. Run the connector
The example works only with application authorization. It will not work when using webhooks.
To use the example, configure the CRest class. For detailed information, read the article
Loading and Using CRest PHP SDK
.
You can create an online chat on the site. When a visitor writes a message, the open channel connector sends the text to Bitrix24. An employee replies from Bitrix24 — the response is displayed on the site.
To set up the connector and create an online chat, we will perform six steps:
Create a file
function.php
with helper functions and a class for working with the API.
Create a file
install_connector.php
to register the connector. In the file, we will call the methods:
imconnector.register
— register the connector in Bitrix24,
event.bind
— subscribe to the event
OnImConnectorMessageAdd
.
Create a handler
handler.php
for events from Bitrix24. In the file, we will call the methods:
imconnector.activate
— activate the connector,
imconnector.connector.data.set
— pass widget data,
imconnector.send.status.delivery
— confirm message delivery.
Create a file
ajax.php
for data exchange between the widget and Bitrix24. In the file, we will call the method
imconnector.send.messages
to send messages.
Create a public page
index.php
with the chat interface.
Run the script
install_connector.php
to register the connector in the system.
As a result, we will have a chat that is integrated with Bitrix24 and ready to receive messages from users.
The dialogue is tied to:
the user's session — each visitor receives an independent conversation,
the site's domain — message exchange works only at the specified address.
1 Create the file function.php
1. Create the file function.php
Create the file
function.php
and define helper functions.
In the example, the chat history is stored in files. In real projects, it is recommended to use a database.
getConnectorID
getConnectorID
The function
getConnectorID
returns a unique identifier for the connector
example_connector_1
.
How to Use Examples in Documentation
include_once
(
'crest.php'
);
function
getConnectorID
(
)
{
return
'example_connector_1'
;
}
getChat
getChat
The function
getChat
returns the chat history
$chatID
from a file. If the file exists, it returns an array of messages
$result
. If not, it returns an empty array.
It takes the parameter
$chatID
— the chat identifier.
function
getChat
(
$chatID
)
{
$result
= [];
if
(
file_exists
(
__DIR__
.
'/chats/'
.
$chatID
.
'.txt'
))
{
$result
=
json_decode
(
file_get_contents
(
__DIR__
.
'/chats/'
.
$chatID
.
'.txt'
),
1
);
}
return
$result
;
}
saveMessage
saveMessage
The function
saveMessage
saves a new message
$arMessage
to the chat file
$chatID
.
Parameters:
$chatID
— the chat identifier,
$arMessage
— an array with message data.
The function returns the message number if it was saved, or
false
in case of a write error.
function
saveMessage
(
$chatID
,
$arMessage
)
{
$arMessages
=
getChat
(
$chatID
);
$count
=
count
(
$arMessages
);
$arMessages
[
'message'
.
$count
] =
$arMessage
;
if
(
file_put_contents
(
__DIR__
.
'/chats/'
.
$chatID
.
'.txt'
,
json_encode
(
$arMessages
)))
{
$return
=
$count
;
}
else
{
$return
=
false
;
}
return
$return
;
}
getLine
getLine
The function
getLine
returns the line identifier from the file
line_id.txt
, if the file exists. If the file does not exist, it returns
false
or an empty string.
function
getLine
(
)
{
return
file_get_contents
(
__DIR__
.
'/line_id.txt'
);
}
setLine
setLine
The function
setLine
saves the line identifier to the file
line_id.txt
. It takes the parameter
$line_id
— the open line identifier. In case of successful writing, the function returns the number of bytes written, otherwise —
false
.
function
setLine
(
$line_id
)
{
return
file_put_contents
(
__DIR__
.
'/line_id.txt'
,
intVal
(
$line_id
));
}
convertBB
convertBB
The function
convertBB
converts BB codes to HTML. It takes the parameter
$var
— text with tags like
[b]bold[/b]
. It returns text with HTML tags, for example,
<strong>bold</strong>
.
function
convertBB
(
$var
)
{
$search
=
array
(
'/\[b\](.*?)\[\/b\]/is'
,
'/\[br\]/is'
,
'/\[i\](.*?)\[\/i\]/is'
,
'/\[u\](.*?)\[\/u\]/is'
,
'/\[img\](.*?)\[\/img\]/is'
,
'/\[url\](.*?)\[\/url\]/is'
,
'/\[url\=(.*?)\](.*?)\[\/url\]/is'
);
$replace
=
array
(
'<strong>$1</strong>'
,
'<br>'
,
'<em>$1</em>'
,
'<u>$1</u>'
,
'<img src="$1" />'
,
'<a href="$1">$1</a>'
,
'<a href="$1">$2</a>'
);
$var
=
preg_replace
(
$search
,
$replace
,
$var
);
return
$var
;
}
Example code for the file function.php
Example code for the file function.php
<?php
include_once
(
'crest.php'
);
function
getConnectorID
(
)
{
return
'example_connector_1'
;
}
function
getChat
(
$chatID
)
{
$result
= [];
if
(
file_exists
(
__DIR__
.
'/chats/'
.
$chatID
.
'.txt'
))
{
$result
=
json_decode
(
file_get_contents
(
__DIR__
.
'/chats/'
.
$chatID
.
'.txt'
),
1
);
}
return
$result
;
}
function
saveMessage
(
$chatID
,
$arMessage
)
{
$arMessages
=
getChat
(
$chatID
);
$count
=
count
(
$arMessages
);
$arMessages
[
'message'
.
$count
] =
$arMessage
;
if
(
file_put_contents
(
__DIR__
.
'/chats/'
.
$chatID
.
'.txt'
,
json_encode
(
$arMessages
)))
{
$return
=
$count
;
}
else
{
$return
=
false
;
}
return
$return
;
}
function
getLine
(
)
{
return
file_get_contents
(
__DIR__
.
'/line_id.txt'
);
}
function
setLine
(
$line_id
)
{
return
file_put_contents
(
__DIR__
.
'/line_id.txt'
,
intVal
(
$line_id
));
}
function
convertBB
(
$var
)
{
$search
=
array
(
'/\[b\](.*?)\[\/b\]/is'
,
'/\[br\]/is'
,
'/\[i\](.*?)\[\/i\]/is'
,
'/\[u\](.*?)\[\/u\]/is'
,
'/\[img\](.*?)\[\/img\]/is'
,
'/\[url\](.*?)\[\/url\]/is'
,
'/\[url\=(.*?)\](.*?)\[\/url\]/is'
);
$replace
=
array
(
'<strong>$1</strong>'
,
'<br>'
,
'<em>$1</em>'
,
'<u>$1</u>'
,
'<img src="$1" />'
,
'<a href="$1">$1</a>'
,
'<a href="$1">$2</a>'
);
$var
=
preg_replace
(
$search
,
$replace
,
$var
);
return
$var
;
}
2 Create the file install_connector.php
2. Create the file install_connector.php
To register the connector in Bitrix24, create the file
install_connector.php
. In the file, include
function.php
, which we created in the first step.
require_once
(
'function.php'
);
Set up the event handler URL
Set up the event handler URL
In the parameter
$handlerUrl
, specify the address of the script that will receive events from Bitrix24. We will create the file with the script
handler.php
in the third step.
The address must be valid, accessible from the outside, and support HTTPS.
$handlerUrl
=
'https://yourdomain.com/handler.php'
;
Create a directory to store chats
Create a directory to store chats
Create a folder
/chats/
to store the history of conversations.
Use
@mkdir()
to create the directory with permissions
0775
.
The flag
true
allows creating nested folders.
Check if the folder was created successfully.
@
mkdir
(
__DIR__
.
'/chats/'
,
0775
,
true
);
if
(!
file_exists
(
__DIR__
.
'/chats/'
))
{
echo
'error create dir "chats"'
;
}
Register the connector
Register the connector
Get the connector identifier
$connector_id
through the function
getConnectorID()
from
function.php
.
To register the connector, use the method
imconnector.register
. We will pass the following data to it:
ID
— the connector identifier
$connector_id
.
NAME
— the name of the connector. We will specify
ExampleSiteChat
.
ICON
— an array for describing the connector's icon in an active state.
DATA_IMAGE
— DATA representation of the SVG icon. For example,
data:image/svg+xml;charset=US-ASCII,…
.
COLOR
— color. We will specify
#a6ffa3
.
SIZE
— size. We will pass
100%
.
POSITION
— position of the SVG. We will set it to
center
.
ICON_DISABLED
— an array for describing the icon when the connector is disabled. It is similar to the
ICON
array.
PLACEMENT_HANDLER
— the URL of the event handler. We will pass
$handlerUrl
.
$connector_id
=
getConnectorID
();
$result
=
CRest
::
call
(
'imconnector.register'
,
[
'ID'
=>
$connector_id
,
'NAME'
=>
'ExampleSiteChat'
,
'ICON'
=> [
'DATA_IMAGE'
=>
'data:image/svg+xml;charset=US-ASCII,...'
,
'COLOR'
=>
'#a6ffa3'
,
'SIZE'
=>
'100%'
,
'POSITION'
=>
'center'
,
],
'ICON_DISABLED'
=> [
'DATA_IMAGE'
=>
'data:image/svg+xml;charset=US-ASCII,...'
,
'SIZE'
=>
'100%'
,
'POSITION'
=>
'center'
,
'COLOR'
=>
'#ffb3a3'
,
],
'PLACEMENT_HANDLER'
=>
$handlerUrl
,
]
);
Register the event handler
Register the event handler
After successfully registering the connector, we will subscribe to the event
OnImConnectorMessageAdd
. It is triggered when a new message is received from the user.
To register the event handler, use the method
event.bind
. We will pass the following parameters to it:
event
— the name of the event. We will pass
OnImConnectorMessageAdd
.
handler
— a link to the event handler. We will specify
$handlerUrl
.
After registration, we will output the message
successfully
.
if
(!
empty
(
$result
[
'result'
]))
{
$resultEvent
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
'OnImConnectorMessageAdd'
,
'handler'
=>
$handlerUrl
,
]
);
if
(!
empty
(
$resultEvent
[
'result'
]))
{
echo
'successfully'
;
}
}
Example code for the file install_connector.php
Example code for the file install_connector.php
<?php
require_once
(
'function.php'
);
$handlerUrl
=
'https://yourdomain.com/handler.php'
;
//create dir for save chats (recommend using database)
@
mkdir
(
__DIR__
.
'/chats/'
,
0775
,
true
);
if
(!
file_exists
(
__DIR__
.
'/chats/'
))
{
echo
'error create dir "chats"'
;
}
else
{
$connector_id
=
getConnectorID
();
$result
=
CRest
::
call
(
'imconnector.register'
,
[
'ID'
=>
$connector_id
,
'NAME'
=>
'ExampleSiteChat'
,
'ICON'
=> [
'DATA_IMAGE'
=>
'data:image/svg+xml;charset=US-ASCII,%3Csvg%20version%3D%221.1%22%20id%3D%22Layer_1%22%20xmlns%3D%22http%3A//www.w3.org/2000/svg%22%20x%3D%220px%22%20y%3D%220px%22%0A%09%20viewBox%3D%220%200%2070%2071%22%20style%3D%22enable-background%3Anew%200%200%2070%2071%3B%22%20xml%3Aspace%3D%22preserve%22%3E%0A%3Cpath%20fill%3D%22%230C99BA%22%20class%3D%22st0%22%20d%3D%22M34.7%2C64c-11.6%2C0-22-7.1-26.3-17.8C4%2C35.4%2C6.4%2C23%2C14.5%2C14.7c8.1-8.2%2C20.4-10.7%2C31-6.2%0A%09c12.5%2C5.4%2C19.6%2C18.8%2C17%2C32.2C60%2C54%2C48.3%2C63.8%2C34.7%2C64L34.7%2C64z%20M27.8%2C29c0.8-0.9%2C0.8-2.3%2C0-3.2l-1-1.2h19.3c1-0.1%2C1.7-0.9%2C1.7-1.8%0A%09v-0.9c0-1-0.7-1.8-1.7-1.8H26.8l1.1-1.2c0.8-0.9%2C0.8-2.3%2C0-3.2c-0.4-0.4-0.9-0.7-1.5-0.7s-1.1%2C0.2-1.5%2C0.7l-4.6%2C5.1%0A%09c-0.8%2C0.9-0.8%2C2.3%2C0%2C3.2l4.6%2C5.1c0.4%2C0.4%2C0.9%2C0.7%2C1.5%2C0.7C26.9%2C29.6%2C27.4%2C29.4%2C27.8%2C29L27.8%2C29z%20M44%2C41c-0.5-0.6-1.3-0.8-2-0.6%0A%09c-0.7%2C0.2-1.3%2C0.9-1.5%2C1.6c-0.2%2C0.8%2C0%2C1.6%2C0.5%2C2.2l1%2C1.2H22.8c-1%2C0.1-1.7%2C0.9-1.7%2C1.8v0.9c0%2C1%2C0.7%2C1.8%2C1.7%2C1.8h19.3l-1%2C1.2%0A%09c-0.5%2C0.6-0.7%2C1.4-0.5%2C2.2c0.2%2C0.8%2C0.7%2C1.4%2C1.5%2C1.6c0.7%2C0.2%2C1.5%2C0%2C2-0.6l4.6-5.1c0.8-0.9%2C0.8-2.3%2C0-3.2L44%2C41z%20M23.5%2C32.8%0A%09c-1%2C0.1-1.7%2C0.9-1.7%2C1.8v0.9c0%2C1%2C0.7%2C1.8%2C1.7%2C1.8h23.4c1-0.1%2C1.7-0.9%2C1.7-1.8v-0.9c0-1-0.7-1.8-1.7-1.9L23.5%2C32.8L23.5%2C32.8z%22/%3E%0A%3C/svg%3E%0A'
,
'COLOR'
=>
'#a6ffa3'
,
'SIZE'
=>
'100%'
,
'POSITION'
=>
'center'
,
],
'ICON_DISABLED'
=> [
'DATA_IMAGE'
=>
'data:image/svg+xml;charset=US-ASCII,%3Csvg%20version%3D%221.1%22%20id%3D%22Layer_1%22%20xmlns%3D%22http%3A//www.w3.org/2000/svg%22%20x%3D%220px%22%20y%3D%220px%22%0A%09%20viewBox%3D%220%200%2070%2071%22%20style%3D%22enable-background%3Anew%200%200%2070%2071%3B%22%20xml%3Aspace%3D%22preserve%22%3E%0A%3Cpath%20fill%3D%22%230C99BA%22%20class%3D%22st0%22%20d%3D%22M34.7%2C64c-11.6%2C0-22-7.1-26.3-17.8C4%2C35.4%2C6.4%2C23%2C14.5%2C14.7c8.1-8.2%2C20.4-10.7%2C31-6.2%0A%09c12.5%2C5.4%2C19.6%2C18.8%2C17%2C32.2C60%2C54%2C48.3%2C63.8%2C34.7%2C64L34.7%2C64z%20M27.8%2C29c0.8-0.9%2C0.8-2.3%2C0-3.2l-1-1.2h19.3c1-0.1%2C1.7-0.9%2C1.7-1.8%0A%09v-0.9c0-1-0.7-1.8-1.7-1.8H26.8l1.1-1.2c0.8-0.9%2C0.8-2.3%2C0-3.2c-0.4-0.4-0.9-0.7-1.5-0.7s-1.1%2C0.2-1.5%2C0.7l-4.6%2C5.1%0A%09c-0.8%2C0.9-0.8%2C2.3%2C0%2C3.2l4.6%2C5.1c0.4%2C0.4%2C0.9%2C0.7%2C1.5%2C0.7C26.9%2C29.6%2C27.4%2C29.4%2C27.8%2C29L27.8%2C29z%20M44%2C41c-0.5-0.6-1.3-0.8-2-0.6%0A%09c-0.7%2C0.2-1.3%2C0.9-1.5%2C1.6c-0.2%2C0.8%2C0%2C1.6%2C0.5%2C2.2l1%2C1.2H22.8c-1%2C0.1-1.7%2C0.9-1.7%2C1.8v0.9c0%2C1%2C0.7%2C1.8%2C1.7%2C1.8h19.3l-1%2C1.2%0A%09c-0.5%2C0.6-0.7%2C1.4-0.5%2C2.2c0.2%2C0.8%2C0.7%2C1.4%2C1.5%2C1.6c0.7%2C0.2%2C1.5%2C0%2C2-0.6l4.6-5.1c0.8-0.9%2C0.8-2.3%2C0-3.2L44%2C41z%20M23.5%2C32.8%0A%09c-1%2C0.1-1.7%2C0.9-1.7%2C1.8v0.9c0%2C1%2C0.7%2C1.8%2C1.7%2C1.8h23.4c1-0.1%2C1.7-0.9%2C1.7-1.8v-0.9c0-1-0.7-1.8-1.7-1.9L23.5%2C32.8L23.5%2C32.8z%22/%3E%0A%3C/svg%3E%0A'
,
'SIZE'
=>
'100%'
,
'POSITION'
=>
'center'
,
'COLOR'
=>
'#ffb3a3'
,
],
'PLACEMENT_HANDLER'
=>
$handlerUrl
,
]
);
if
(!
empty
(
$result
[
'result'
]))
{
$resultEvent
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
'OnImConnectorMessageAdd'
,
'handler'
=>
$handlerUrl
,
]
);
if
(!
empty
(
$resultEvent
[
'result'
]))
{
echo
'successfully'
;
}
}
}
3 Create the file handler.php
3. Create the file handler.php
Create the file
handler.php
to process events from Bitrix24. In the file, include
function.php
, which we created in the first step.
require_once
(
'function.php'
);
Set up widget parameters
Set up widget parameters
$widgetUri
— specify the URL of the page with the widget icon.
$widgetName
— set the name of the connector in the widget.
$connector_id
— pass the connector identifier through the function
getConnectorID
from the file
function.php
.
$widgetUri
=
''
;
$widgetName
=
'ExampleSiteChatWidget'
;
$connector_id
=
getConnectorID
();
The variables
$widgetUri
and
$widgetName
are required if you need to show the connector in the list of connectors in the widget on the site. In other cases, they can be left empty.
Activate the connector
Activate the connector
In the array
$options
, pass the processed data from
PLACEMENT_OPTIONS
. The array contains the line identifier and the connector status.
To activate the connector, use the method
imconnector.activate
. We will pass the following data to it:
CONNECTOR
— the connector identifier
$connector_id
.
LINE
— the open line identifier. We will specify
intVal($options['LINE'])
.
ACTIVE
— the connector status. We will pass
intVal($options['ACTIVE_STATUS'])
. Possible values:
1
— active,
0
— inactive.
$options
=
json_decode
(
$_REQUEST
[
'PLACEMENT_OPTIONS'
],
true
);
$result
=
CRest
::
call
(
'imconnector.activate'
,
[
'CONNECTOR'
=>
$connector_id
,
'LINE'
=>
intVal
(
$options
[
'LINE'
]),
'ACTIVE'
=>
intVal
(
$options
[
'ACTIVE_STATUS'
]),
]
);
Supplement the connector settings
Supplement the connector settings
If the connector is activated and
widgetUri
and
widgetName
are specified, we will supplement the connector settings using the method
imconnector.connector.data.set
. We will pass the following data to it:
CONNECTOR
— the connector identifier
$connector_id
.
LINE
— the open line identifier. We will specify
intVal($options['LINE'])
.
DATA
— an array with data to save.
id
— the identifier of the account connected to this connector. We will specify
$connector_id.'line'.intVal($options['LINE'])
— a combination of the connector and line identifiers.
url_im
— the link to the chat. We will pass the parameter
$widgetUri
.
name
— the name of the connector in the widget. We will pass the parameter
$widgetName
.
$resultWidgetData
=
CRest
::
call
(
'imconnector.connector.data.set'
,
[
'CONNECTOR'
=>
$connector_id
,
'LINE'
=>
intVal
(
$options
[
'LINE'
]),
'DATA'
=> [
'id'
=>
$connector_id
.
'line'
.
intVal
(
$options
[
'LINE'
]),
'url_im'
=>
$widgetUri
,
'name'
=>
$widgetName
],
]
);
Save the open line
Save the open line
After successful activation:
save the line identifier to a file using the function
setLine
from the file
function.php
,
output the message
successfully
.
if
(!
empty
(
$resultWidgetData
[
'result'
]))
{
setLine
(
$options
[
'LINE'
]);
echo
'successfully'
;
}
Confirm message delivery
Confirm message delivery
When the event
ONIMCONNECTORMESSAGEADD
is triggered, and a message is received for the connector with the identifier
$connector_id
, save the message using the function
saveMessage
.
Confirm message delivery using the method
imconnector.send.status.delivery
. We will pass the following data to it:
CONNECTOR
— the connector identifier
$connector_id
.
LINE
— the open line identifier. We will specify it using the function
getLine
from the file
function.php
.
MESSAGES
— an array of messages.
im
— the element from the incoming message of the open line.
message
— an array of message identifiers. We will pass
$idMess
, which is obtained from the function
saveMessage
.
chat
— the chat identifier.
if
(
$_REQUEST
[
'event'
] ==
'ONIMCONNECTORMESSAGEADD'
&& !
empty
(
$_REQUEST
[
'data'
][
'CONNECTOR'
])
&&
$_REQUEST
[
'data'
][
'CONNECTOR'
] ==
$connector_id
&& !
empty
(
$_REQUEST
[
'data'
][
'MESSAGES'
])
)
{
foreach
(
$_REQUEST
[
'data'
][
'MESSAGES'
]
as
$arMessage
)
{
$idMess
=
saveMessage
(
$arMessage
[
'chat'
][
'id'
],
$arMessage
);
$resultDelivery
=
CRest
::
call
(
'imconnector.send.status.delivery'
,
[
'CONNECTOR'
=>
$connector_id
,
'LINE'
=>
getLine
(),
'MESSAGES'
=> [
[
'im'
=>
$arMessage
[
'im'
],
'message'
=> [
'id'
=> [
$idMess
]
],
'chat'
=> [
'id'
=>
$arMessage
[
'chat'
][
'id'
]
},
],
]
]
);
}
}
Example code for the file handler.php
Example code for the file handler.php
<?php
require_once
(
'function.php'
);
$widgetUri
=
''
;
$widgetName
=
'ExampleSiteChatWidget'
;
$connector_id
=
getConnectorID
();
if
(!
empty
(
$_REQUEST
[
'PLACEMENT_OPTIONS'
]) &&
$_REQUEST
[
'PLACEMENT'
] ==
'SETTING_CONNECTOR'
)
{
//activate connector
$options
=
json_decode
(
$_REQUEST
[
'PLACEMENT_OPTIONS'
],
true
);
$result
=
CRest
::
call
(
'imconnector.activate'
,
[
'CONNECTOR'
=>
$connector_id
,
'LINE'
=>
intVal
(
$options
[
'LINE'
]),
'ACTIVE'
=>
intVal
(
$options
[
'ACTIVE_STATUS'
]),
]
);
if
(!
empty
(
$result
[
'result'
]))
{
//add data widget
if
(!
empty
(
$widgetUri
) && !
empty
(
$widgetName
))
{
$resultWidgetData
=
CRest
::
call
(
'imconnector.connector.data.set'
,
[
'CONNECTOR'
=>
$connector_id
,
'LINE'
=>
intVal
(
$options
[
'LINE'
]),
'DATA'
=> [
'id'
=>
$connector_id
.
'line'
.
intVal
(
$options
[
'LINE'
]),
'url_im'
=>
$widgetUri
,
'name'
=>
$widgetName
],
]
);
if
(!
empty
(
$resultWidgetData
[
'result'
]))
{
setLine
(
$options
[
'LINE'
]);
echo
'successfully'
;
}
}
else
{
setLine
(
$options
[
'LINE'
]);
echo
'successfully'
;
}
}
}
if
(
$_REQUEST
[
'event'
] ==
'ONIMCONNECTORMESSAGEADD'
&& !
empty
(
$_REQUEST
[
'data'
][
'CONNECTOR'
])
&&
$_REQUEST
[
'data'
][
'CONNECTOR'
] ==
$connector_id
&& !
empty
(
$_REQUEST
[
'data'
][
'MESSAGES'
])
)
{
foreach
(
$_REQUEST
[
'data'
][
'MESSAGES'
]
as
$arMessage
)
{
$idMess
=
saveMessage
(
$arMessage
[
'chat'
][
'id'
],
$arMessage
);
$resultDelivery
=
CRest
::
call
(
'imconnector.send.status.delivery'
,
[
'CONNECTOR'
=>
$connector_id
,
'LINE'
=>
getLine
(),
'MESSAGES'
=> [
[
'im'
=>
$arMessage
[
'im'
],
'message'
=> [
'id'
=> [
$idMess
]
],
'chat'
=> [
'id'
=>
$arMessage
[
'chat'
][
'id'
]
},
],
]
]
);
}
}
4 Create the file ajax.php
4. Create the file ajax.php
Create the file
ajax.php
to handle AJAX requests from the chat widget on the site. In the file, include
function.php
, which contains the necessary functions.
require_once
(
'function.php'
);
session_start
();
Prepare variables
Prepare variables
$chatID
— the chat identifier. Create it based on the domain
HTTP_ORIGIN
and the user session
session_id()
.
$type
— the request type. Pass the value from the form
$_POST['type']
. Possible values:
chat_history
— load history,
send_message
— send a message.
$connector_id
— the connector identifier. Obtain it using the function
getConnectorID
from
function.php
.
$line_id
— the open line identifier. Obtain it using the function
getLine
from
function.php
.
$chatID
=
'chat'
.
md5
(
$_SERVER
[
'HTTP_ORIGIN'
]) .
md5
(
session_id
());
$type
=
$_POST
[
'type'
];
$connector_id
=
getConnectorID
();
$line_id
=
getLine
();
Load chat history
Load chat history
For an AJAX request of type
chat_history
, load messages using the function
getChat
from
function.php
.
Output each message as a block.
If the element
im
exists, the message came from Bitrix24. Display it on the left with a gray background
#fbfbfb
.
If the element
im
does not exist — the message is from the user. Display it on the right with a light blue background
#ccf2ff
.
Process the text using the function
convertBB()
from
function.php
.
if
(
$type
==
'chat_history'
):
$arChat
=
getChat
(
$chatID
);
if
(!
empty
(
$arChat
)):
foreach
(
$arChat
as
$item
):
?>
<div
class
="
col
-12
alert
alert
-
warning
text
-<?=(!
empty
($
item
['
im
'])) ? '
left
' : '
right
'?>"
style
="
background
-
color
: <?=(!
empty
($
item
['
im
'])) ? '#
fbfbfb
' : '#
ccf2ff
'?>">
<?=
convertBB
($
item
['
message
']['
text
'])?>
</
div
>
<?
php
endforeach
;
endif
;
Send a message
Send a message
For an AJAX request of type
send_message
, form the message structure
$arMessage
and send it to Bitrix24.
Structure of the array arMessage
Structure of the array $arMessage
user
— an array describing the user:
id
— the user identifier, which matches the chat identifier. Pass
$chatID
.
name
— the user's name. Protect against XSS attacks using
htmlspecialchars
and pass the value from the form
$_POST['name']
.
message
— an array describing the message:
date
— the message time in
timestamp
format.
text
— the message text. Protect against XSS attacks using
htmlspecialchars
and pass the value from the form
$_POST['message']
.
chat
— an array describing the chat:
id
— the chat identifier. Pass
$chatID
.
url
— the link to the chat in the external system. Protect against XSS attacks using
htmlspecialchars
and pass the address of the page
HTTP_REFERER
.
elseif
(
$type
==
'send_message'
):
$arMessage
= [
'user'
=> [
'id'
=>
$chatID
,
'name'
=>
htmlspecialchars
(
$_POST
[
'name'
]),
],
'message'
=> [
'id'
=>
false
,
'date'
=>
time
(),
'text'
=>
htmlspecialchars
(
$_POST
[
'message'
]),
],
'chat'
=> [
'id'
=>
$chatID
,
'url'
=>
htmlspecialchars
(
$_SERVER
[
'HTTP_REFERER'
]),
],
];
Save the message locally
Save the message locally
Add the message to the file using the function
saveMessage
. Save the message number in the variable
$id
.
$id
=
saveMessage
(
$chatID
,
$arMessage
);
Pass the message to Bitrix24
Pass the message to Bitrix24
To send the message to the open line, use the method
imconnector.send.messages
. We will pass the following data to it:
CONNECTOR
— the connector identifier
$connector_id
.
LINE
— the open line identifier. We will specify
$line_id
, which is obtained using
getLine
.
MESSAGES
— an array of messages. Each message is described by a separate array. We will pass
[$arMessage]
.
if
(
$id
!==
false
)
{
$arMessage
[
'message'
][
'id'
] =
$id
;
$result
=
CRest
::
call
(
'imconnector.send.messages'
,
[
'CONNECTOR'
=>
$connector_id
,
'LINE'
=>
$line_id
,
'MESSAGES'
=> [
$arMessage
],
]
);
}
echo
json_encode
(
[
'chat'
=>
$chatID
,
'post'
=>
$_POST
,
'result'
=>
$result
]
);
Example code for the file ajax.php
Example code for the file ajax.php
<?php
require_once
(
'function.php'
);
session_start
();
$chatID
=
'chat'
.
md5
(
$_SERVER
[
'HTTP_ORIGIN'
]) .
md5
(
session_id
());
$type
=
$_POST
[
'type'
];
$connector_id
=
getConnectorID
();
$line_id
=
getLine
();
/*
simple example save chat, must lost any data
recommend using database
*/
if
(
$type
==
'chat_history'
):
$arChat
=
getChat
(
$chatID
);
if
(!
empty
(
$arChat
)):
foreach
(
$arChat
as
$item
):
?>
<div
class
="
col
-12
alert
alert
-
warning
text
-<?=(!
empty
($
item
['
im
'])) ? '
left
' : '
right
'?>"
style
="
background
-
color
: <?=(!
empty
($
item
['
im
'])) ? '#
fbfbfb
' : '#
ccf2ff
'?>">
<?=
convertBB
($
item
['
message
']['
text
'])?>
</
div
>
<?
php
endforeach
;
endif
;
elseif
($
type
== '
send_message
'):
$
arMessage
= [
'
user
' => [
'
id
' => $
chatID
,
'
name
' =>
htmlspecialchars
($
_POST
['
name
']),
],
'
message
' => [
'
id
' =>
false
,
'
date
' =>
time
(),
'
text
' =>
htmlspecialchars
($
_POST
['
message
']),
],
'
chat
' => [
'
id
' => $
chatID
,
'
url
' =>
htmlspecialchars
($
_SERVER
['
HTTP_REFERER
']),
],
];
$
id
=
saveMessage
($
chatID
, $
arMessage
);
$
result
['
error
'] = '
error_save
';
if
($
id
!==
false
)
{
$arMessage
[
'message'
][
'id'
] =
$id
;
$result
=
CRest
::
call
(
'imconnector.send.messages'
,
[
'CONNECTOR'
=>
$connector_id
,
'LINE'
=>
$line_id
,
'MESSAGES'
=> [
$arMessage
],
]
);
}
echo
json_encode
(
[
'chat'
=>
$chatID
,
'post'
=>
$_POST
,
'result'
=>
$result
]
);
endif
;
5 Create the file index.php
5. Create the file index.php
Create a public chat page for visitors — the file
index.php
.
Include external libraries Bootstrap and jQuery.
Create a chat container consisting of two parts:
chat_history
— message history,
chat_form
— message sending form.
Implement the chat logic through JavaScript.
Add the function
updateChat
, which updates the message history every five seconds. It sends a POST request to
ajax.php
with the parameter
type=chat_history
, receives the HTML markup of the messages, and inserts it into
#chat_history
.
Handle message sending. Collect data using the
serialize
function and perform a request to
ajax.php
with the parameter
type=send_message
.
Example code for the file index.php
Example code for the file index.php
<body>
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
crossorigin="anonymous">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<div class="container-fluid">
<div class="m-5">
<div id="chat_history" class="row">
<div class="spinner-border m-5 text-success" role="status">
<span class="sr-only">Loading...</span>
</div>
</div>
<div id="chat_form" class="mt-5 mr-auto ml-auto mb-5">
<form id="form_message">
<div class="form-group">
<label for="name">Name</label>
<input type="text" class="form-control" placeholder="Name">
</div>
<div class="form-group">
<label for="message">Message</label>
<textarea class="form-control" name="message" rows="3" placeholder="your message here"></textarea>
</div>
<input class="btn btn-primary" type="submit" name="send" value="send">
</form>
</div>
</div>
</div>
<script>
$(document).ready(function () {
function updateChat()
{
$.ajax({
'method': 'POST',
'dataType': 'html',
'url': 'ajax.php',
'data': 'type=chat_history',
success: function (data) {//success callback
$('#chat_history').text('').html(data);
}
});
}
setInterval(updateChat, 5000);
updateChat();
$('#form_message').on('submit', function (el) {//event submit form
el.preventDefault();//the default action of the event will not be triggered
$('#chat_form').addClass('spinner-border');
$('#form_message').hide();
var formData = $(this).serialize();
$.ajax({
'method': 'POST',
'dataType': 'json',
'url': 'ajax.php',
'data': formData + '&type=send_message',
success: function (data) {//success callback
updateChat();
$('#chat_form').removeClass('spinner-border');
$('#form_message textarea[name=message]').val('');
$('#form_message').show();
}
});
});
});
</script>
</body>
6 Run the connector
6. Run the connector
Place the files
function.php
,
handler.php
,
install_connector.php
,
ajax.php
,
index.php
in one folder on the server. For example, in the folder
/myconnector/
.
In the browser, open the page
https://your_site.com/myconnector/install_connector.php
and see one of two messages:
successfully
— the folder
/chats/
was created, the connector was registered,
error create dir "chats"
— the script cannot create the folder
/chats/
, the connector setup was not completed. To fix this, you need to correctly configure the permissions.
Connect the connector in Bitrix24.
In Bitrix24, go to the page
CRM > Clients > Contact Center
.
Find the block named ExampleSiteChat.
Click Connect.
If the message
successfully
appears, the connector is activated.
Start a dialogue in the chat.
In the browser, open the page
https://your_site.com/myconnector/index.php
.
Write a message. It should arrive in Bitrix24.
Reply — the response will appear on the site.
Copied
Was the article helpful?
Yes
No
Previous
Tutorials and use-cases for REST in the Open Channels module
Next
Overview

---

