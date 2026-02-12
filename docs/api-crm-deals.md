---
description: 'CRM Deals API: CRUD, contacts, events, custom forms, product rows'
methods:
- crm.activity.
- crm.category.
- crm.category.get
- crm.category.list
- crm.currency.list
- crm.deal.add
- crm.deal.contact.
- crm.deal.contact.add
- crm.deal.contact.delete
- crm.deal.contact.fields
- crm.deal.contact.items.
- crm.deal.contact.items.delete
- crm.deal.contact.items.get
- crm.deal.contact.items.set
- crm.deal.delete
- crm.deal.details.configuration.
- crm.deal.details.configuration.forceCommonScopeForAll
- crm.deal.details.configuration.get
- crm.deal.details.configuration.reset
- crm.deal.details.configuration.set
- crm.deal.fields
- crm.deal.get
- crm.deal.list
- crm.deal.productrows.get
- crm.deal.productrows.set
- crm.deal.recurring.
- crm.deal.recurring.add
- crm.deal.recurring.delete
- crm.deal.recurring.expose
- crm.deal.recurring.fields
pages: 27
title: 'CRM Deals API: CRUD, contacts, events, custom forms, product rows'
---
# CRM Deals API: CRUD, contacts, events, custom forms, product rows
> CRM Deals API: CRUD, contacts, events, custom forms, product rows
> **27 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Deals in CRM: Overview of Methods](#deals-in-crm-overview-of-methods)
- [Create a new deal crm.deal.add](#create-a-new-deal-crmdealadd)
- [Update Deal crm.deal.update](#update-deal-crmdealupdate)
- [Get Deal by Id crm.deal.get](#get-deal-by-id-crmdealget)
- [Get a list of deals crm.deal.list](#get-a-list-of-deals-crmdeallist)
- [Delete deal crm.deal.delete](#delete-deal-crmdealdelete)
- [Get Deal Fields crm.deal.fields](#get-deal-fields-crmdealfields)
- [Set Products in Deal crm.deal.productrows.set](#set-products-in-deal-crmdealproductrowsset)
- [Get Deal Product Rows crm.deal.productrows.get](#get-deal-product-rows-crmdealproductrowsget)
- [Overview of Events When Working with Deals](#overview-of-events-when-working-with-deals)
- [Event when creating a deal onCrmDealAdd](#event-when-creating-a-deal-oncrmdealadd)
- [Event on deal update onCrmDealUpdate](#event-on-deal-update-oncrmdealupdate)
- [Event on deal deletion onCrmDealDelete](#event-on-deal-deletion-oncrmdealdelete)
- [Event on changing the deal's Sales Funnel onCrmDealMoveToCategory](#event-on-changing-the-deals-sales-funnel-oncrmdeal)
- [Linking Deals to Contacts: Overview of Methods](#linking-deals-to-contacts-overview-of-methods)
- [Add Contact to Deal crm.deal.contact.add](#add-contact-to-deal-crmdealcontactadd)
- [Add Multiple Contacts to a Deal crm.deal.contact.items.set](#add-multiple-contacts-to-a-deal-crmdealcontactitem)
- [Get Fields for Deal-Contact Connection crm.deal.contact.fields](#get-fields-for-deal-contact-connection-crmdealcont)
- [Get a set of contacts associated with a deal crm.deal.contact.items.get](#get-a-set-of-contacts-associated-with-a-deal-crmde)
- [Remove Contact from Specified Deal crm.deal.contact.delete](#remove-contact-from-specified-deal-crmdealcontactd)
- [Delete the set of contacts associated with the specified deal crm.deal.contact.items.delete](#delete-the-set-of-contacts-associated-with-the-spe)
- [Managing Deal Cards: Overview of Methods](#managing-deal-cards-overview-of-methods)
- [Get parameters of crm.deal.details.configuration.get](#get-parameters-of-crmdealdetailsconfigurationget)
- [Reset Deal Card Settings crm.deal.details.configuration.reset](#reset-deal-card-settings-crmdealdetailsconfigurati)
- [Set Parameters for the Individual Card crm.deal.details.configuration.set](#set-parameters-for-the-individual-card-crmdealdeta)
- [Set a common card for all users crm.deal.details.configuration.forceCommonScopeForAll](#set-a-common-card-for-all-users-crmdealdetailsconf)
- [Widgets](#widgets)

---

## Deals in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/index

Deals in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Deals in CRM: Overview of Methods
Deals in CRM: Overview of Methods
Connection of Deals with Other CRM Objects
Sales Funnels and Deal Stages
How to Change a Deal's Funnel
Deal Card
Widgets
Recurring Deals
Overview of Methods and Events
Main
Recurring Deals
Custom Fields
Deal Contacts
Managing Deal Cards
A deal is one of the key objects in CRM, where you can:
manage the sales process of a product or service, including tracking stages and accepting online payments
engage in dialogue with the client: calls, e-mails, chats in open channels
view the history of interactions: activities, timeline records
Quick navigation:
all methods and events
User documentation:
deals in Bitrix24
Connection of Deals with Other CRM Objects
Connection of Deals with Other CRM Objects
Client.
A field in the deal card that consists of the associated company and contacts. All activities related to calls, e-mails, and chats with the contact or company will be saved in the active deal card. There can be only one company in the field, and it is accessed directly through the deal field
COMPANY_ID
. Multiple contacts can be specified, and interaction with them is conducted through a separate group of methods
crm.deal.contact.*
.
Products.
Adding, modifying, and deleting product items in deals can be done through the group of methods
crm.item.productrow.*
.
Payments.
Adding, modifying, and deleting payment documents in deals can be done through the group of methods
crm.item.payment.*
.
User Documentation
Connection between deals, contacts, and companies
How to add products to deals, leads, and estimates
How to accept payments from clients and work with receipts in Bitrix24
Sales Funnels and Deal Stages
Sales Funnels and Deal Stages
You can create various sales funnels for deals and manage them through the group of methods
crm.category.*
where
entityTypeId
of the deal =
2
.
Each funnel will have its own stages. These can be managed through the group of CRM reference methods —
crm.status.*
. The
ENTITY_ID
of deal statuses is unique for each direction —
DEAL_STAGE_xx
.
You can retrieve the history of a deal's movement through stages using the method
crm.stagehistory.list
.
User Documentation
Sales funnels: how to divide work by departments in CRM
How to Change a Deal's Funnel
How to Change a Deal's Funnel
The method
crm.deal.update
can only change the stage of a deal within the current funnel. If you pass a
STAGE_ID
that does not belong to the current funnel, nothing will change.
To move a deal to a stage in another funnel, use the method
crm.item.update
with the following parameters:
entityTypeId
—
2
for the deal,
id
— the
id
of the deal you are moving,
categoryId
— the
id
of the funnel to which you are moving the deal. This can be obtained using the method
crm.category.list
stageId
— the
id
of the stage in the new funnel. This can be obtained using the method
crm.status.list
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
'{"entityTypeId":2,"id":233,"fields":{"STAGE_ID":"EXECUTING","categoryId":0}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"id":233,"fields":{"STAGE_ID":"EXECUTING","categoryId":0},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.update'
,
{
entityTypeId
:
2
,
id
:
233
,
fields
: {
STAGE_ID
:
'EXECUTING'
,
categoryId
:
0
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
(
'Updated item with ID:'
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
'crm.item.update'
,
[
'entityTypeId'
=>
2
,
'id'
=>
233
,
'fields'
=> [
'STAGE_ID'
=>
'EXECUTING'
,
'categoryId'
=>
0
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
'Error updating item: '
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
"crm.item.update"
,
{
entityTypeId
:
2
,
id
:
233
,
fields
:
{
"STAGE_ID"
:
"EXECUTING"
,
"categoryId"
:
0
},
},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
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
'crm.item.update'
,
[
'entityTypeId'
=>
2
,
'id'
=>
233
,
'fields'
=> [
'STAGE_ID'
=>
'EXECUTING'
,
'categoryId'
=>
0
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
Deal Card
Deal Card
The main workspace in a deal is the General tab of its card. It consists of two parts:
the left part, which contains fields with information. If the system fields are insufficient, you can create your own custom fields. They allow you to store information in various data formats: string, number, link, address, and others. To create, modify, retrieve, or delete custom deal fields, the group of methods
crm.deal.userfield.*
is used.
the right part, which contains the deal's timeline. In it, you can create, edit, filter, and delete CRM activities — the group of methods
crm.activity.*
, and timeline records — the group of methods
crm.timeline.*
.
The parameters of the deal card can be managed depending on the funnel through the group of methods
crm.deal.details.configuration.*
.
User Documentation
CRM Card: capabilities and settings
System fields in CRM
Custom fields in CRM
Timeline in a CRM entity
Widgets
Widgets
You can embed an application into the deal card. By embedding, you can use the application without leaving the deal card.
There are two embedding scenarios:
Use special
embedding locations
. For example, by creating your own tab.
Create a
custom field
, into which the interface of your application will be loaded.
Typical Use-Cases and Scenarios
Widget Embedding Mechanism
Embed a Widget in the CRM Card
Recurring Deals
Recurring Deals
Automatic creation of similar
recurring deals
based on templates. To manage templates, the group of methods
crm.deal.recurring.*
is used.
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can execute the method: depending on the method
Main
Main
Methods
Events
Method
Description
crm.deal.add
Creates a new deal
crm.deal.update
Modifies a deal
crm.deal.get
Returns a deal by ID
crm.deal.list
Returns a list of deals by filter
crm.deal.delete
Deletes a deal and all associated objects
crm.deal.fields
Returns the description of deal fields
crm.deal.productrows.set
Adds products to a deal
crm.deal.productrows.get
Returns products of a deal
Event
Triggered
onCrmDealAdd
When a deal is created
onCrmDealUpdate
When a deal is modified
onCrmDealDelete
When a deal is deleted
onCrmDealMoveToCategory
When the deal's funnel is changed
Recurring Deals
Recurring Deals
Methods
Events
Method
Description
crm.deal.recurring.add
Creates a new recurring deal
crm.deal.recurring.fields
Returns a list of fields for the recurring deal template
crm.deal.recurring.expose
Creates a new deal from a template
crm.deal.recurring.update
Modifies existing settings for the recurring deal template
crm.deal.recurring.get
Retrieves the settings fields of the recurring deal template by Id
crm.deal.recurring.list
Retrieves a list of settings for recurring deal templates
crm.deal.recurring.delete
Deletes existing settings for the recurring deal template
Event
Triggered
onCrmDealRecurringAdd
When a new recurring deal is created
onCrmDealRecurringUpdate
When a recurring deal is modified
onCrmDealRecurringDelete
When a recurring deal is deleted
onCrmDealRecurringExpose
When a new deal is created from a recurring deal
Custom Fields
Custom Fields
Methods
Events
Method
Description
crm.deal.userfield.add
Creates a new custom field for deals
crm.deal.userfield.update
Modifies an existing custom field for deals
crm.deal.userfield.get
Retrieves a custom field for deals by Id
crm.deal.userfield.list
Retrieves a list of custom fields for deals
crm.deal.userfield.delete
Deletes a custom field for deals
Event
Triggered
onCrmDealUserFieldAdd
When a custom field is added
onCrmDealUserFieldUpdate
When a custom field is modified
onCrmDealUserFieldDelete
When a custom field is deleted
onCrmDealUserFieldSetEnumValues
When the set of values for a custom list-type field is changed
Deal Contacts
Deal Contacts
Method
Description
crm.deal.contact.add
Adds a contact to a deal
crm.deal.contact.items.set
Adds multiple contacts to a deal
crm.deal.contact.fields
Returns the fields for the deal-contact relationship
crm.deal.contact.items.get
Retrieves the set of contacts associated with the deal
crm.deal.contact.delete
Removes a contact from the specified deal
crm.deal.contact.items.delete
Removes a set of contacts associated with the specified deal
Managing Deal Cards
Managing Deal Cards
Method
Description
crm.deal.details.configuration.get
Retrieves the settings for deal cards
crm.deal.details.configuration.reset
Resets the settings for deal cards
crm.deal.details.configuration.set
Allows setting the settings for deal cards
crm.deal.details.configuration.forceCommonScopeForAll
Forces a common deal card for all users
Copied
Was the article helpful?
Yes
No
Previous
Widgets
Next
Create a new deal

---

## Create a new deal crm.deal.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/crm-deal-add

Create a new deal crm.deal.add | Bitrix24 REST API and Marketplace Applications
Create a new deal crm.deal.add
Create a new deal crm.deal.add
Method Parameters
Parameter fields
Parameter params
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with the "add" access permission for deals
The method
crm.deal.add
creates a new deal.
Method Parameters
Method Parameters
Name
type
Description
fields
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where:
field_n
— field name
value_n
— field value
The list of available fields is described
below
params
object
Object containing an additional set of parameters (
detailed description
)
Parameter fields
Parameter fields
Name
type
Description
TITLE
string
Deal title.
By default, it is generated using the template
Deal #{id}
, where
id
is the element identifier
TYPE_ID
crm_status
String identifier of the deal type.
The list of available deal types can be obtained using the method
crm.status.list
with the filter
{ ENTITY_ID: 'DEAL_TYPE' }
.
By default — the first available deal type
CATEGORY_ID
crm_category
Identifier of the funnel. Must be greater than or equal to 0.
The list of available funnels can be obtained using the method
crm.category.list
by passing
entityTypeId = 2
.
By default — the identifier of the default funnel
STAGE_ID
crm_status
Stage of the deal.
The list of available stages can be obtained using the method
crm.status.list
with the filter:
{ ENTITY_ID: "DEAL_STAGE" }
— if the deal is in the general funnel (direction)
{ ENTITY_ID: "DEAL_STAGE_{categoryId}" }
— if the deal is not in the general funnel, where
categoryId
is the identifier of the deal
funnel
By default — the first available stage relative to the funnel
IS_RECURRING
char
Is the deal a template for a recurring deal? Possible values:
Y
— yes
N
— no
By default
N
IS_RETURN_CUSTOMER
char
Is the deal a repeat? Possible values:
Y
— yes
N
— no
By default
N
IS_REPEATED_APPROACH
char
Is the deal a repeated approach? Possible values:
Y
— yes
N
— no
By default
N
PROBABILITY
integer
Probability, %
CURRENCY_ID
crm_currency
Currency.
The list of available currencies can be obtained using the method
crm.currency.list
OPPORTUNITY
double
Amount.
By default
0.00
IS_MANUAL_OPPORTUNITY
char
Is manual calculation of the amount enabled? Possible values:
Y
— yes
N
— no
By default
N
TAX_VALUE
double
Tax amount.
By default
0.00
COMPANY_ID
crm_company
Identifier of the company associated with the deal.
The list of companies can be obtained using the method
crm.item.list
by passing
entityTypeId = 4
CONTACT_ID
crm_contact
Contact. Deprecated
CONTACT_IDS
crm_contact[]
List of contacts associated with the deal.
The list of contacts can be obtained using the method
crm.item.list
by passing
entityTypeId = 3
BEGINDATE
date
Start date.
By default — the date of deal creation
CLOSEDATE
date
Completion date.
By default — the date of deal creation plus 7 days
OPENED
char
Is the deal available to everyone? Possible values:
Y
— yes
N
— no
By default
Y
. The default value can be changed in CRM settings
CLOSED
char
Is the deal closed? Possible values:
Y
— yes
N
— no
By default
N
COMMENTS
string
Comment. Supports bb-codes
ASSIGNED_BY_ID
user
Responsible person.
By default — the user calling this method
SOURCE_ID
crm_status
String identifier of the source type.
The list of available sources can be obtained using the method
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
By default — the first available source type
SOURCE_DESCRIPTION
string
Additional information about the source
ADDITIONAL_INFO
string
Additional information
LOCATION_ID
location
Client's location. System field
ORIGINATOR_ID
string
Identifier of the data source.
Used only for linking to an external source
ORIGIN_ID
string
Identifier of the element in the data source.
Used only for linking to an external source
UTM_SOURCE
string
Advertising system (Google-Adwords and others)
UTM_MEDIUM
string
Type of traffic. Possible values:
CPC
— ads
CPM
— banners
UTM_CAMPAIGN
string
Designation of the advertising campaign
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
UTM_TERM
string
Search term of the campaign. For example, keywords for contextual advertising
TRACE
string
Information for Sales Intelligence — read more in the article
How to Transfer Information to Sales Intelligence
UF_CRM_...
Custom fields. For example,
UF_CRM_25534736
.
Depending on the portal settings, deals may have a set of custom fields of specific types.
You can add a custom field to a deal using the method
crm.deal.userfield.add
PARENT_ID_...
crm_entity
Relationship fields.
If there are SPAs related to deals on the portal, there is a field for each such SPA that stores the relationship between this SPA and the deal. The field itself stores the identifier of the element of that SPA.
For example, the field
PARENT_ID_153
— relationship with the SPA
entityTypeId=153
, stores the identifier of the element of this SPA related to the current deal
Parameter params
Parameter params
Name
type
Description
REGISTER_SONET_EVENT
boolean
Should the event of adding a deal be registered in the live feed? Possible values:
Y
— yes
N
— no
By default
Y
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
'{"FIELDS":{"TITLE":"New Deal #1","TYPE_ID":"COMPLEX","CATEGORY_ID":0,"STAGE_ID":"PREPARATION","IS_RECURRING":"N","IS_RETURN_CUSTOMER":"Y","IS_REPEATED_APPROACH":"Y","PROBABILITY":99,"CURRENCY_ID":"EUR","OPPORTUNITY":1000000,"IS_MANUAL_OPPORTUNITY":"Y","TAX_VALUE":0.10,"COMPANY_ID":9,"CONTACT_IDS":[84,83],"BEGINDATE":"'
"
$(date --iso-8601=seconds)
"
'","CLOSEDATE":"'
"
$(date --iso-8601=seconds --date='+10 days')
"
'", "OPENED":"Y","CLOSED":"N","COMMENTS":"Example comment","SOURCE_ID":"CALLBACK","SOURCE_DESCRIPTION":"Additional information about the source","ADDITIONAL_INFO":"Additional information","UTM_SOURCE":"google","UTM_MEDIUM":"CPC","PARENT_ID_1220":22,"UF_CRM_1721244482250":"Hello world!"},"PARAMS":{"REGISTER_SONET_EVENT":"N"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"FIELDS":{"TITLE":"New Deal #1","TYPE_ID":"COMPLEX","CATEGORY_ID":0,"STAGE_ID":"PREPARATION","IS_RECURRING":"N","IS_RETURN_CUSTOMER":"Y","IS_REPEATED_APPROACH":"Y","PROBABILITY":99,"CURRENCY_ID":"EUR","OPPORTUNITY":1000000,"IS_MANUAL_OPPORTUNITY":"Y","TAX_VALUE":0.10,"COMPANY_ID":9,"CONTACT_IDS":[84,83],"BEGINDATE":"'
"
$(date --iso-8601=seconds)
"
'","CLOSEDATE":"'
"
$(date --iso-8601=seconds --date='+10 days')
"
'", "OPENED":"Y","CLOSED":"N","COMMENTS":"Example comment","SOURCE_ID":"CALLBACK","SOURCE_DESCRIPTION":"Additional information about the source","ADDITIONAL_INFO":"Additional information","UTM_SOURCE":"google","UTM_MEDIUM":"CPC","PARENT_ID_1220":22,"UF_CRM_1721244482250":"Hello world!"},"PARAMS":{"REGISTER_SONET_EVENT":"N"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.deal.add
try
{
const
day =
60
*
60
*
24
*
1000
;
const
now =
new
Date
();
const
after10Days =
new
Date
(now.
getTime
() +
10
* day);
const
response =
await
$b24.
callMethod
(
'crm.deal.add'
,
{
fields
: {
TITLE
:
"New Deal #1"
,
TYPE_ID
:
"COMPLEX"
,
CATEGORY_ID
:
0
,
STAGE_ID
:
"PREPARATION"
,
IS_RECURRING
:
"N"
,
IS_RETURN_CUSTOMER
:
"Y"
,
IS_REPEATED_APPROACH
:
"Y"
,
PROBABILITY
:
99
,
CURRENCY_ID
:
"EUR"
,
OPPORTUNITY
:
1000000
,
IS_MANUAL_OPPORTUNITY
:
"Y"
,
TAX_VALUE
:
0.10
,
COMPANY_ID
:
9
,
CONTACT_IDS
: [
84
,
83
],
BEGINDATE
: now.
toISOString
(),
CLOSEDATE
: after10Days.
toISOString
(),
OPENED
:
"Y"
,
CLOSED
:
"N"
,
COMMENTS
:
"[B]Example comment[/B]"
,
SOURCE_ID
:
"CALLBACK"
,
SOURCE_DESCRIPTION
:
"Additional information about the source"
,
ADDITIONAL_INFO
:
"Additional information"
,
UTM_SOURCE
:
"google"
,
UTM_MEDIUM
:
"CPC"
,
PARENT_ID_1220
:
22
,
UF_CRM_1721244482250
:
"Hello world!"
,
},
params
: {
REGISTER_SONET_EVENT
:
"N"
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
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result)
;
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
$fields
= [
'TITLE'
=>
'New Deal'
,
'TYPE_ID'
=>
'GIG'
,
'CATEGORY_ID'
=>
'1'
,
'STAGE_ID'
=>
'C1:NEW'
,
'CURRENCY_ID'
=>
'USD'
,
'OPPORTUNITY'
=>
'10000'
,
'BEGINDATE'
=> (
new
DateTime
())->
format
(
DateTime
::
ATOM
),
'CLOSEDATE'
=> (
new
DateTime
(
'+1 month'
))->
format
(
DateTime
::
ATOM
),
'COMMENTS'
=>
'This is a test deal.'
,
];
$params
= [
'REGISTER_SONET_EVENT'
=>
'Y'
,
];
$result
=
$serviceBuilder
->
getCRMScope
()
->
deal
()
->
add
(
$fields
,
$params
);
print
(
$result
->
getId
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
const
day =
60
*
60
*
24
*
1000
;
const
now =
new
Date
();
const
after10Days =
new
Date
(now.
getTime
() +
10
* day);
BX24
.
callMethod
(
'crm.deal.add'
,
{
fields
: {
TITLE
:
"New Deal #1"
,
TYPE_ID
:
"COMPLEX"
,
CATEGORY_ID
:
0
,
STAGE_ID
:
"PREPARATION"
,
IS_RECURRING
:
"N"
,
IS_RETURN_CUSTOMER
:
"Y"
,
IS_REPEATED_APPROACH
:
"Y"
,
PROBABILITY
:
99
,
CURRENCY_ID
:
"EUR"
,
OPPORTUNITY
:
1000000
,
IS_MANUAL_OPPORTUNITY
:
"Y"
,
TAX_VALUE
:
0.10
,
COMPANY_ID
:
9
,
CONTACT_IDS
: [
84
,
83
],
BEGINDATE
: now.
toISOString
(),
CLOSEDATE
: after10Days.
toISOString
(),
OPENED
:
"Y"
,
CLOSED
:
"N"
,
COMMENTS
:
"[B]Example comment[/B]"
,
SOURCE_ID
:
"CALLBACK"
,
SOURCE_DESCRIPTION
:
"Additional information about the source"
,
ADDITIONAL_INFO
:
"Additional information"
,
UTM_SOURCE
:
"google"
,
UTM_MEDIUM
:
"CPC"
,
PARENT_ID_1220
:
22
,
UF_CRM_1721244482250
:
"Hello world!"
,
},
params
: {
REGISTER_SONET_EVENT
:
"N"
,
},
},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result.
data
())
;
},
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
'crm.deal.add'
,
[
'FIELDS'
=> [
'TITLE'
=>
'New Deal #1'
,
'TYPE_ID'
=>
'COMPLEX'
,
'CATEGORY_ID'
=>
0
,
'STAGE_ID'
=>
'PREPARATION'
,
'IS_RECURRING'
=>
'N'
,
'IS_RETURN_CUSTOMER'
=>
'Y'
,
'IS_REPEATED_APPROACH'
=>
'Y'
,
'PROBABILITY'
=>
99
,
'CURRENCY_ID'
=>
'EUR'
,
'OPPORTUNITY'
=>
1000000
,
'IS_MANUAL_OPPORTUNITY'
=>
'Y'
,
'TAX_VALUE'
=>
0.10
,
'COMPANY_ID'
=>
9
,
'CONTACT_IDS'
=> [
84
,
83
],
'BEGINDATE'
=> (
new
DateTime
())->
format
(
DateTime
::
ATOM
),
'CLOSEDATE'
=> (
new
DateTime
(
'+10 days'
))->
format
(
DateTime
::
ATOM
),
'OPENED'
=>
'Y'
,
'CLOSED'
=>
'N'
,
'COMMENTS'
=>
'Example comment'
,
'SOURCE_ID'
=>
'CALLBACK'
,
'SOURCE_DESCRIPTION'
=>
'Additional information about the source'
,
'ADDITIONAL_INFO'
=>
'Additional information'
,
'UTM_SOURCE'
=>
'google'
,
'UTM_MEDIUM'
=>
'CPC'
,
'PARENT_ID_1220'
=>
22
,
'UF_CRM_1721244482250'
=>
'Hello world!'
,
],
'PARAMS'
=> [
'REGISTER_SONET_EVENT'
=>
'N'
,
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
Response Handling
Response Handling
HTTP status:
200
{
"result"
:
394
,
"time"
:
{
"start"
:
1725013197.635808
,
"finish"
:
1725013198.580873
,
"duration"
:
0.9450650215148926
,
"processing"
:
0.6822988986968994
,
"date_start"
:
"2024-08-30T12:19:57+02:00"
,
"date_finish"
:
"2024-08-30T12:19:58+02:00"
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
Root element of the response, contains the identifier of the created deal
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
""
,
"error_description"
:
"Parameter 'fields' must be array."
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
-
Parameter 'fields' must be array
The parameter
fields
is not an object
-
Parameter 'params' must be array
The parameter
params
is not an object
-
Access denied
The user does not have permission to "add" deals
-
Disk resource exhausted
-
Invalid value for the "Currency" field
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
Update Deal crm.deal.update
Get Deal by Id crm.deal.get
Get a list of deals crm.deal.list
Delete deal crm.deal.delete
Get Deal Fields crm.deal.fields
Add a deal and company with requisites
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Update a deal

---

## Update Deal crm.deal.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/crm-deal-update

Update Deal crm.deal.update | Bitrix24 REST API and Marketplace Applications
Update Deal crm.deal.update
Update Deal crm.deal.update
Method Parameters
Parameter fields
Parameter params
Code Examples
Method Explanation
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with "edit" access permission for deals
The method
crm.deal.update
updates an existing deal.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the deal.
The identifier can be obtained using the methods
crm.deal.list
or
crm.deal.add
fields
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where:
field_n
— field name
value_n
— new field value
The list of available fields is described
below
.
An incorrect field in
fields
will be ignored.
Only the fields that need to be changed should be passed in
fields
params
object
Set of additional parameters (
detailed description
)
Parameter fields
Parameter fields
Name
type
Description
TITLE
string
Title of the deal
TYPE_ID
crm_status
String identifier of the deal type.
The list of available deal types can be found using the method
crm.status.list
with the filter
{ ENTITY_ID: 'DEAL_TYPE' }
STAGE_ID
crm_status
Stage of the deal.
The list of available stages can be found using the method
crm.status.list
with the filter:
{ ENTITY_ID: "DEAL_STAGE" }
— if the deal is in the general Sales Funnel
{ ENTITY_ID: "DEAL_STAGE_{categoryId}" }
— if the deal is not in the general Sales Funnel, where
categoryId
is the identifier of the
funnel
and equals
CATEGORY_ID
of the deal.
If it is necessary to change the funnel of the deal, use the method
crm.item.update
, with the
entityTypeId
of the deal being
2
IS_RECURRING
char
Is the deal a template for a recurring deal? Possible values:
Y
— yes
N
— no
IS_RETURN_CUSTOMER
char
Is the deal a repeat? Possible values:
Y
— yes
N
— no
IS_REPEATED_APPROACH
char
Is the deal a repeated approach? Possible values:
Y
— yes
N
— no
PROBABILITY
integer
Probability, %
CURRENCY_ID
crm_currency
Currency.
The list of available currencies can be found using the method
crm.currency.list
OPPORTUNITY
double
Amount
IS_MANUAL_OPPORTUNITY
char
Is manual calculation mode enabled? Possible values:
Y
— yes
N
— no
TAX_VALUE
double
Tax amount
COMPANY_ID
crm_company
Identifier of the company associated with the deal.
The list of companies can be found using the method
crm.item.list
with
entityTypeId = 4
CONTACT_ID
crm_contact
Contact. Deprecated
CONTACT_IDS
crm_contact[]
List of contacts associated with the deal.
The list of contacts can be found using the method
crm.item.list
with
entityTypeId = 3
BEGINDATE
date
Start date
CLOSEDATE
date
End date
OPENED
char
Is the deal available to everyone? Possible values:
Y
— yes
N
— no
CLOSED
char
Is the deal closed? Possible values:
Y
— yes
N
— no
COMMENTS
string
Comment. Supports bb-codes
ASSIGNED_BY_ID
user
Responsible person
SOURCE_ID
crm_status
String identifier of the source type.
The list of available sources can be found using the method
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
SOURCE_DESCRIPTION
string
Additional information about the source
ADDITIONAL_INFO
string
Additional information
LOCATION_ID
location
Client's location. System field
ORIGINATOR_ID
string
Identifier of the data source.
Used only for linking to an external source
ORIGIN_ID
string
Identifier of the element in the data source.
Used only for linking to an external source
UTM_SOURCE
string
Advertising system (Google-Adwords and others)
UTM_MEDIUM
string
Type of traffic. Possible values:
CPC
— ads
CPM
— banners
UTM_CAMPAIGN
string
Identifier of the advertising campaign
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
UTM_TERM
string
Search condition of the campaign. For example, keywords for contextual advertising
UF_CRM_...
Custom fields. For example,
UF_CRM_25534736
.
Depending on the portal settings, deals may have a set of custom fields of defined types.
Values of multiple fields are passed as an array.
To change file fields, it is recommended to use the method
crm.item.update
.
You can add a custom field to a deal using the method
crm.deal.userfield.add
PARENT_ID_...
crm_entity
Relationship fields.
If there are smart processes related to deals on the portal, for each such smart process, there is a field that stores the relationship between this smart process and the deal. The field itself stores the identifier of the element of that smart process.
For example, the field
PARENT_ID_153
— relationship with the smart process
entityTypeId=153
, stores the identifier of the element of this smart process related to the current deal
Parameter params
Parameter params
Name
type
Description
REGISTER_SONET_EVENT
boolean
Should the event of the deal change be registered in the live feed? Possible values:
Y
— yes
N
— no
REGISTER_HISTORY_EVENT
boolean
Should a record be created in the history? Possible values:
Y
— yes
N
— no
Related methods and topics
Update existing settings for the recurring deal template crm.deal.recurring.update
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
'{"ID":123,"FIELDS":{"TITLE":"New deal title!","TYPE_ID":"GOODS","STAGE_ID":"WON","IS_RECCURING":"Y","IS_RETURN_CUSTOMER":"Y","OPPORTUNITY":9999.99,"IS_MANUAL_OPPORTUNITY":"Y","ASSIGNED_BY_ID":1,"UF_CRM_1725365197310":"String","PARENT_ID_1032":1},"PARAMS":{"REGISTER_SONET_EVENT":"N","REGISTER_HISTORY_EVENT":"N"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":123,"FIELDS":{"TITLE":"New deal title!","TYPE_ID":"GOODS","STAGE_ID":"WON","IS_RECCURING":"Y","IS_RETURN_CUSTOMER":"Y","OPPORTUNITY":9999.99,"IS_MANUAL_OPPORTUNITY":"Y","ASSIGNED_BY_ID":1,"UF_CRM_1725365197310":"String","PARENT_ID_1032":1},"PARAMS":{"REGISTER_SONET_EVENT":"N","REGISTER_HISTORY_EVENT":"N"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.deal.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.update'
,
{
id
:
123
,
fields
: {
TITLE
:
"New deal title!"
,
TYPE_ID
:
"GOODS"
,
STAGE_ID
:
"WON"
,
IS_RECCURING
:
"Y"
,
IS_RETURN_CUSTOMER
:
"Y"
,
OPPORTUNITY
:
9999.99
,
IS_MANUAL_OPPORTUNITY
:
"Y"
,
ASSIGNED_BY_ID
:
1
,
UF_CRM_1725365197310
:
"String"
,
PARENT_ID_1032
:
1
,
},
params
: {
REGISTER_SONET_EVENT
:
"N"
,
REGISTER_HISTORY_EVENT
:
"N"
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
result.
error
() ?
console
.
error
(result.
error
()) :
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
'crm.deal.update'
,
[
'id'
=>
123
,
'fields'
=> [
'TITLE'
=>
"New deal title!"
,
'TYPE_ID'
=>
"GOODS"
,
'STAGE_ID'
=>
"WON"
,
'IS_RECCURING'
=>
"Y"
,
'IS_RETURN_CUSTOMER'
=>
"Y"
,
'OPPORTUNITY'
=>
9999.99
,
'IS_MANUAL_OPPORTUNITY'
=>
"Y"
,
'ASSIGNED_BY_ID'
=>
1
,
'UF_CRM_1725365197310'
=>
"String"
,
'PARENT_ID_1032'
=>
1
,
],
'params'
=> [
'REGISTER_SONET_EVENT'
=>
"N"
,
'REGISTER_HISTORY_EVENT'
=>
"N"
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
$response
->
getError
()) {
echo
'Error: '
.
$response
->
getError
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
,
true
);
// Your logic for processing data
processData
(
$result
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
'Error updating deal: '
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
'crm.deal.update'
,
{
id
:
123
,
fields
: {
TITLE
:
"New deal title!"
,
TYPE_ID
:
"GOODS"
,
STAGE_ID
:
"WON"
,
IS_RECCURING
:
"Y"
,
IS_RETURN_CUSTOMER
:
"Y"
,
OPPORTUNITY
:
9999.99
,
IS_MANUAL_OPPORTUNITY
:
"Y"
,
ASSIGNED_BY_ID
:
1
,
UF_CRM_1725365197310
:
"String"
,
PARENT_ID_1032
:
1
,
},
params
: {
REGISTER_SONET_EVENT
:
"N"
,
REGISTER_HISTORY_EVENT
:
"N"
,
},
},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result.
data
())
;
},
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
'crm.deal.update'
,
[
'ID'
=>
123
,
'FIELDS'
=> [
'TITLE'
=>
'New deal title!'
,
'TYPE_ID'
=>
'GOODS'
,
'STAGE_ID'
=>
'WON'
,
'IS_RECCURING'
=>
'Y'
,
'IS_RETURN_CUSTOMER'
=>
'Y'
,
'OPPORTUNITY'
=>
9999.99
,
'IS_MANUAL_OPPORTUNITY'
=>
'Y'
,
'ASSIGNED_BY_ID'
=>
1
,
'UF_CRM_1725365197310'
=>
'String'
,
'PARENT_ID_1032'
=>
1
,
],
'PARAMS'
=> [
'REGISTER_SONET_EVENT'
=>
'N'
,
'REGISTER_HISTORY_EVENT'
=>
'N'
,
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
Method Explanation
Method Explanation
For managing deal contacts, it is not recommended to use the fields
CONTACT_IDS
and
CONTACT_ID
.
Use the methods
crm.deal.contact.*
for working with a single contact, and the methods
crm.deal.contact.items.*
for working with a group of deal contacts.
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
1725365418.056843
,
"finish"
:
1725365419.671506
,
"duration"
:
1.6146628856658936
,
"processing"
:
1.3475170135498047
,
"date_start"
:
"2024-09-03T14:10:18+02:00"
,
"date_finish"
:
"2024-09-03T14:10:19+02:00"
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
HTTP status:
400
{
"error"
:
""
,
"error_description"
:
"Parameter 'fields' must be array."
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
-
ID is not defined or invalid
The parameter
id
is not a positive integer
-
Not found
The deal with the provided
id
does not exist
-
Parameter 'fields' must be array
The parameter
fields
is not an object
-
Parameter 'params' must be array
The parameter
params
is not an object
-
Access denied
The user does not have permission to "edit" deals
-
Disk resource exhausted
-
Invalid value for the "Currency" field
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
Create a new deal crm.deal.add
Get Deal by Id crm.deal.get
Get a list of deals crm.deal.list
Delete deal crm.deal.delete
Get Deal Fields crm.deal.fields
Update CRM Item: crm.item.update
How to Save the Payment Date in the Deal Field
Copied
Was the article helpful?
Yes
No
Previous
Create a new deal
Next
Get a deal by Id

---

## Get Deal by Id crm.deal.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/crm-deal-get

Get Deal by Id crm.deal.get | Bitrix24 REST API and Marketplace Applications
Get Deal by Id crm.deal.get
Get Deal by Id crm.deal.get
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
Who can execute the method: any user with "read" access permission for deals
The method
crm.deal.get
returns a deal by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the deal.
The identifier can be obtained using the methods
crm.deal.list
or
crm.deal.add
Related methods and topics
Get the fields of the recurring deal template settings by Id crm.deal.recurring.get
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
'{"ID":410}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":410,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.deal.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.get'
,
{
id
:
410
,
}
);
const
result = response.
getData
().
result
;
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result)
;
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
'crm.deal.get'
,
[
'id'
=>
410
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
'Deal data: '
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
'Error getting deal: '
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
'crm.deal.get'
,
{
id
:
410
,
},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result.
data
())
;
},
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
'crm.deal.get'
,
[
'ID'
=>
410
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
"410"
,
"TITLE"
:
"New Deal #1"
,
"TYPE_ID"
:
"COMPLEX"
,
"STAGE_ID"
:
"PREPARATION"
,
"PROBABILITY"
:
"99"
,
"CURRENCY_ID"
:
"EUR"
,
"OPPORTUNITY"
:
"1000000.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"Y"
,
"TAX_VALUE"
:
"0.00"
,
"LEAD_ID"
:
null
,
"COMPANY_ID"
:
"9"
,
"CONTACT_ID"
:
"84"
,
"QUOTE_ID"
:
null
,
"BEGINDATE"
:
"2024-08-30T02:00:00+02:00"
,
"CLOSEDATE"
:
"2024-09-09T02:00:00+02:00"
,
"ASSIGNED_BY_ID"
:
"1"
,
"CREATED_BY_ID"
:
"1"
,
"MODIFY_BY_ID"
:
"1"
,
"DATE_CREATE"
:
"2024-08-30T14:29:00+02:00"
,
"DATE_MODIFY"
:
"2024-08-30T14:29:00+02:00"
,
"OPENED"
:
"Y"
,
"CLOSED"
:
"N"
,
"COMMENTS"
:
"[B]Example comment[\/B]"
,
"ADDITIONAL_INFO"
:
"Additional information"
,
"LOCATION_ID"
:
null
,
"CATEGORY_ID"
:
"0"
,
"STAGE_SEMANTIC_ID"
:
"P"
,
"IS_NEW"
:
"N"
,
"IS_RECURRING"
:
"N"
,
"IS_RETURN_CUSTOMER"
:
"N"
,
"IS_REPEATED_APPROACH"
:
"N"
,
"SOURCE_ID"
:
"CALLBACK"
,
"SOURCE_DESCRIPTION"
:
"Additional information about the source"
,
"ORIGINATOR_ID"
:
null
,
"ORIGIN_ID"
:
null
,
"MOVED_BY_ID"
:
"1"
,
"MOVED_TIME"
:
"2024-08-30T14:29:00+02:00"
,
"LAST_ACTIVITY_TIME"
:
"2024-08-30T14:29:00+02:00"
,
"UTM_SOURCE"
:
"google"
,
"UTM_MEDIUM"
:
"CPC"
,
"UTM_CAMPAIGN"
:
null
,
"UTM_CONTENT"
:
null
,
"UTM_TERM"
:
null
,
"PARENT_ID_1220"
:
"22"
,
"LAST_ACTIVITY_BY"
:
"1"
,
"UF_CRM_1721244482250"
:
"Hello world!"
}
,
"time"
:
{
"start"
:
1725020945.541275
,
"finish"
:
1725020946.179076
,
"duration"
:
0.637800931930542
,
"processing"
:
0.21427488327026367
,
"date_start"
:
"2024-08-30T14:29:05+02:00"
,
"date_finish"
:
"2024-08-30T14:29:06+02:00"
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
deal
Root element of the response. Contains information about the deal fields. The structure is described
below
time
time
Information about the request execution time
Type deal
Type deal
Name
type
Description
ID
integer
Identifier of the deal
TITLE
string
Title
TYPE_ID
crm_status
String identifier of the deal type.
To learn more about the obtained deal type, you can use the method
crm.status.list
, passing the filter:
{
ENTITY_ID: 'DEAL_TYPE',
STATUS_ID: TYPE_ID,
}
CATEGORY_ID
crm_category
Funnel. To learn more about this funnel, you can use the method
crm.category.get
, passing
entityTypeId = 2
and
id = CATEGORY_ID
STAGE_ID
crm_status
String identifier of the deal stage.
To learn more about the obtained stage, you can use the method
crm.status.list
, passing the filter:
{
ENTITY_ID: entityId,
STATUS_ID: statusId,
}
where:
entityId
is equal to:
DEAL_STAGE
if the deal is in the general funnel (
CATEGORY_ID = 0
)
DEAL_STAGE_{categoryId}
, where
categoryId = CATEGORY_ID
statusId
is equal to
STAGE_ID
STAGE_SEMANTIC_ID
string
Stage group. Possible values:
P
— in progress
S
— successful
F
— unsuccessful
IS_NEW
char
Indicates whether the deal is new. Possible values:
Y
— yes
N
— no
IS_RECURRING
char
Indicates whether the deal is recurring. Possible values:
Y
— yes
N
— no
IS_RETURN_CUSTOMER
char
Indicates whether the deal is a repeat. Possible values:
Y
— yes
N
— no
IS_REPEATED_APPROACH
char
Indicates whether the approach is repeated. Possible values:
Y
— yes
N
— no
PROBABILITY
integer
Probability, %
CURRENCY_ID
crm_currency
Currency
OPPORTUNITY
double
Amount
IS_MANUAL_OPPORTUNITY
char
Indicates whether manual mode for amount calculation is enabled. Possible values:
Y
— yes
N
— no
TAX_VALUE
double
Tax rate
COMPANY_ID
crm_company
Identifier of the company.
To learn more about the company, you can use the method
crm.item.get
, passing
entityTypeId = 4
and
id = COMPANY_ID
CONTACT_ID
crm_contact
Identifier of the contact. Deprecated
CONTACT_IDS
crm_contact[]
List of contact identifiers.
To learn more about the list of contacts, you can use the method
crm.item.list
, passing
entityTypeId = 3
and the filter
{ '@id': CONTACT_IDS }
QUOTE_ID
crm_quote
Identifier of the estimate based on which the deal was created.
To learn more about the estimate, you can use the method
crm.item.get
, passing
entityTypeId = 7
and
id = QUOTE_ID
BEGINDATE
date
Start date
CLOSEDATE
date
Close date
OPENED
char
Is the deal available to everyone? Possible values:
Y
— yes
N
— no
CLOSED
char
Is the deal closed? Possible values:
Y
— yes
N
— no
COMMENTS
string
Comment
ASSIGNED_BY_ID
user
Responsible person
CREATED_BY_ID
user
Created by
MODIFY_BY_ID
user
Modified by
MOVED_BY_ID
user
Identifier of the user who last changed the stage
DATE_CREATE
datetime
Creation date
DATE_MODIFY
datetime
Modification date
MOVED_TIME
datetime
Date of the last stage change
SOURCE_ID
crm_status
Source.
To learn more about the obtained source, you can use the method
crm.status.list
, passing the filter:
{
ENTITY_ID: 'SOURCE',
STATUS_ID: SOURCE_ID,
}
SOURCE_DESCRIPTION
string
Additional information about the source
LEAD_ID
crm_lead
Identifier of the lead based on which the deal was created.
To learn more about the lead, you can use the method
crm.item.get
, passing
entityTypeId = 1
and
id = LEAD_ID
ADDITIONAL_INFO
string
Additional information
LOCATION_ID
location
Location. System field
ORIGINATOR_ID
string
External source
ORIGIN_ID
string
Identifier of the element in the external source
UTM_SOURCE
string
Advertising system
UTM_MEDIUM
string
Traffic type
UTM_CAMPAIGN
string
Advertising campaign designation
UTM_CONTENT
string
Content of the campaign
UTM_TERM
string
Search condition of the campaign
LAST_ACTIVITY_TIME
datetime
Date of the last activity in the timeline
LAST_ACTIVITY_BY
user
Author of the last activity in the timeline
UF_CRM_...
any
User-defined fields. For example,
UF_CRM_25534736
.
Depending on the portal settings, deals may have a set of user-defined fields of specific types. Read more in the section
about user-defined fields
PARENT_ID_...
crm_entity
Relationship fields.
If there are smart processes related to deals on the portal, for each such smart process, there is a field that stores the relationship between this smart process and the deal. The field itself stores the identifier of the element of that smart process.
For example, the field
PARENT_ID_153
— relationship with the smart process
entityTypeId=153
, stores the identifier of the element of this smart process related to the current deal
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
""
,
"error_description"
:
"Parameter 'fields' must be array."
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
-
ID is not defined or invalid
The
id
parameter is either not provided or is not a positive integer
-
Access denied
The user does not have permission to "read" this deal
-
Not found
No deal exists with the provided
id
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
Create a new deal crm.deal.add
Update Deal crm.deal.update
Get a list of deals crm.deal.list
Delete deal crm.deal.delete
Get Deal Fields crm.deal.fields
Copied
Was the article helpful?
Yes
No
Previous
Update a deal
Next
Get a list of deals

---

## Get a list of deals crm.deal.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/crm-deal-list

Get a list of deals crm.deal.list | Bitrix24 REST API and Marketplace Applications
Get a list of deals crm.deal.list
Get a list of deals crm.deal.list
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
Who can execute the method: any user with "read" access permission for deals
The method
crm.deal.list
returns a list of deals based on a filter. It is an implementation of the list method for deals.
Method Parameters
Method Parameters
Name
type
Description
select
string[]
A list of fields that should be filled for deals in the selection.
You can use the following masks for selection:
'*'
— to select all fields (excluding custom and multiple fields)
'UF_*'
— to select all custom fields (excluding multiple fields)
You can find the list of available fields for selection using the method
crm.deal.fields
.
By default, all fields are taken —
'*'
+ Custom fields —
'UF_*'
filter
object
An object in the format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where:
field_n
— the name of the field by which the selection of elements will be filtered
value_n
— the filter value
You can add a prefix to the keys
field_n
to specify the filter operation.
Possible prefix values:
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
symbol in the filter value does not need to be passed. The search looks for a substring in any position of the string
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
=
— equal, exact match (used by default)
!=
— not equal
!
— not equal
The LIKE filter does not work with fields of type
crm_status
,
crm_contact
,
crm_company
(deal type
TYPE_ID
, stage
STAGE_ID
, etc.).
You can find the list of available fields for filtering using the method
crm.deal.fields
.
The filter does not support the field
CONTACT_IDS
, for filtering by contacts use the method
crm.item.list
order
object
An object in the format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where:
field_n
— the name of the field by which the selection of deals will be sorted
value_n
— a
string
value equal to:
ASC
— ascending sort
DESC
— descending sort
You can find the list of available fields for sorting using the method
crm.deal.fields
start
integer
This parameter is used to manage pagination.
The page size of results is always static — 50 records.
To select the second page of results, pass the value
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
— the desired page number
Also, see the description of
list methods
.
Related methods and topics
Get a list of recurring deal template settings crm.deal.recurring.list
Code Examples
Code Examples
How to Use Examples in Documentation
Get a list of deals where:
the funnel ID is
1
the deal type is
COMPLEX
the title ends with
a
the stage is
C1:NEW
the amount is greater than 10000 but less than or equal to 20000
manual mode for amount calculation is enabled
the responsible person is either the user with
id = 1
or the user with
id = 6
the deal was created at least 6 months ago
Set the following sort order for this selection: title and amount in ascending order.
For clarity, select only the necessary fields:
Identifier
ID
Title
TITLE
Deal type
TYPE_ID
Funnel ID
CATEGORY_ID
Stage
STAGE_ID
Amount
OPPORTUNITY
Is manual mode enabled
IS_MANUAL_OPPORTUNITY
Responsible
ASSIGNED_BY_ID
Creation date
DATE_CREATE
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
'{"SELECT":["ID","TITLE","TYPE_ID","CATEGORY_ID","STAGE_ID","OPPORTUNITY","IS_MANUAL_OPPORTUNITY","ASSIGNED_BY_ID","DATE_CREATE"],"FILTER":{"=%TITLE":"%a","CATEGORY_ID":1,"TYPE_ID":"COMPLEX","STAGE_ID":"C1:NEW",">OPPORTUNITY":10000,"<=OPPORTUNITY":20000,"IS_MANUAL_OPPORTUNITY":"Y","@ASSIGNED_BY_ID":[1,6],">DATE_CREATE":"'
"
$(date --date='-6 months' +%Y-%m-%d)
"
'"},"ORDER":{"TITLE":"ASC","OPPORTUNITY":"ASC"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"SELECT":["ID","TITLE","TYPE_ID","CATEGORY_ID","STAGE_ID","OPPORTUNITY","IS_MANUAL_OPPORTUNITY","ASSIGNED_BY_ID","DATE_CREATE"],"FILTER":{"=%TITLE":"%a","CATEGORY_ID":1,"TYPE_ID":"COMPLEX","STAGE_ID":"C1:NEW",">OPPORTUNITY":10000,"<=OPPORTUNITY":20000,"IS_MANUAL_OPPORTUNITY":"Y","@ASSIGNED_BY_ID":[1,6],">DATE_CREATE":"'
"
$(date --date='-6 months' +%Y-%m-%d)
"
'"},"ORDER":{"TITLE":"ASC","OPPORTUNITY":"ASC"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.deal.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
const
now =
new
Date
();
const
sixMonthAgo =
new
Date
();
sixMonthAgo.
setMonth
(now.
getMonth
() -
6
);
try
{
const
response =
await
$b24.
callListMethod
(
'crm.deal.list'
,
{
select
: [
'ID'
,
'TITLE'
,
'TYPE_ID'
,
'CATEGORY_ID'
,
'STAGE_ID'
,
'OPPORTUNITY'
,
'IS_MANUAL_OPPORTUNITY'
,
'ASSIGNED_BY_ID'
,
'DATE_CREATE'
,
],
filter
: {
'=%TITLE'
:
'%a'
,
CATEGORY_ID
:
1
,
TYPE_ID
:
'COMPLEX'
,
STAGE_ID
:
'C1:NEW'
,
'>OPPORTUNITY'
:
10000
,
'<=OPPORTUNITY'
:
20000
,
IS_MANUAL_OPPORTUNITY
:
'Y'
,
'@ASSIGNED_BY_ID'
: [
1
,
6
],
'>DATE_CREATE'
: sixMonthAgo,
},
order
: {
TITLE
:
'ASC'
,
OPPORTUNITY
:
'ASC'
,
},
},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result.
data
())
;
},
);
}
catch
(error) {
console
.
error
(
'Request failed'
, error);
}
// fetchListMethod is preferred when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
const
now =
new
Date
();
const
sixMonthAgo =
new
Date
();
sixMonthAgo.
setMonth
(now.
getMonth
() -
6
);
try
{
const
generator = $b24.
fetchListMethod
(
'crm.deal.list'
, {
select
: [
'ID'
,
'TITLE'
,
'TYPE_ID'
,
'CATEGORY_ID'
,
'STAGE_ID'
,
'OPPORTUNITY'
,
'IS_MANUAL_OPPORTUNITY'
,
'ASSIGNED_BY_ID'
,
'DATE_CREATE'
,
],
filter
: {
'=%TITLE'
:
'%a'
,
CATEGORY_ID
:
1
,
TYPE_ID
:
'COMPLEX'
,
STAGE_ID
:
'C1:NEW'
,
'>OPPORTUNITY'
:
10000
,
'<=OPPORTUNITY'
:
20000
,
IS_MANUAL_OPPORTUNITY
:
'Y'
,
'@ASSIGNED_BY_ID'
: [
1
,
6
],
'>DATE_CREATE'
: sixMonthAgo,
},
order
: {
TITLE
:
'ASC'
,
OPPORTUNITY
:
'ASC'
,
},
},
'ID'
);
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
, entity);
}
}
}
catch
(error) {
console
.
error
(
'Request failed'
, error);
}
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
const
now =
new
Date
();
const
sixMonthAgo =
new
Date
();
sixMonthAgo.
setMonth
(now.
getMonth
() -
6
);
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.list'
, {
select
: [
'ID'
,
'TITLE'
,
'TYPE_ID'
,
'CATEGORY_ID'
,
'STAGE_ID'
,
'OPPORTUNITY'
,
'IS_MANUAL_OPPORTUNITY'
,
'ASSIGNED_BY_ID'
,
'DATE_CREATE'
,
],
filter
: {
'=%TITLE'
:
'%a'
,
CATEGORY_ID
:
1
,
TYPE_ID
:
'COMPLEX'
,
STAGE_ID
:
'C1:NEW'
,
'>OPPORTUNITY'
:
10000
,
'<=OPPORTUNITY'
:
20000
,
IS_MANUAL_OPPORTUNITY
:
'Y'
,
'@ASSIGNED_BY_ID'
: [
1
,
6
],
'>DATE_CREATE'
: sixMonthAgo,
},
order
: {
TITLE
:
'ASC'
,
OPPORTUNITY
:
'ASC'
,
},
},
0
);
const
result = response.
getData
().
result
|| [];
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
, entity);
}
}
catch
(error) {
console
.
error
(
'Request failed'
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
'crm.deal.list'
,
[
'select'
=> [
'ID'
,
'TITLE'
,
'TYPE_ID'
,
'CATEGORY_ID'
,
'STAGE_ID'
,
'OPPORTUNITY'
,
'IS_MANUAL_OPPORTUNITY'
,
'ASSIGNED_BY_ID'
,
'DATE_CREATE'
,
],
'filter'
=> [
'=%TITLE'
=>
'%a'
,
'CATEGORY_ID'
=>
1
,
'TYPE_ID'
=>
'COMPLEX'
,
'STAGE_ID'
=>
'C1:NEW'
,
'>OPPORTUNITY'
=>
10000
,
'<=OPPORTUNITY'
=>
20000
,
'IS_MANUAL_OPPORTUNITY'
=>
'Y'
,
'@ASSIGNED_BY_ID'
=> [
1
,
6
],
'>DATE_CREATE'
=>
$sixMonthAgo
,
],
'order'
=> [
'TITLE'
=>
'ASC'
,
'OPPORTUNITY'
=>
'ASC'
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
'Error fetching deal list: '
.
$e
->
getMessage
();
}
const
now =
new
Date
();
const
sixMonthAgo =
new
Date
();
sixMonthAgo.
setMonth
(now.
getMonth
() -
6
);
BX24
.
callMethod
(
'crm.deal.list'
,
{
select
: [
'ID'
,
'TITLE'
,
'TYPE_ID'
,
'CATEGORY_ID'
,
'STAGE_ID'
,
'OPPORTUNITY'
,
'IS_MANUAL_OPPORTUNITY'
,
'ASSIGNED_BY_ID'
,
'DATE_CREATE'
,
],
filter
: {
'=%TITLE'
:
'%a'
,
CATEGORY_ID
:
1
,
TYPE_ID
:
'COMPLEX'
,
STAGE_ID
:
'C1:NEW'
,
'>OPPORTUNITY'
:
10000
,
'<=OPPORTUNITY'
:
20000
,
IS_MANUAL_OPPORTUNITY
:
'Y'
,
'@ASSIGNED_BY_ID'
: [
1
,
6
],
'>DATE_CREATE'
: sixMonthAgo,
},
order
: {
TITLE
:
'ASC'
,
OPPORTUNITY
:
'ASC'
,
},
},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result.
data
())
;
},
);
require_once
(
'crest.php'
);
$sixMonthAgo
= (
new
DateTime
())->
modify
(
'-6 months'
)->
format
(
'Y-m-d'
);
$result
=
CRest
::
call
(
'crm.deal.list'
,
[
'SELECT'
=> [
'ID'
,
'TITLE'
,
'TYPE_ID'
,
'CATEGORY_ID'
,
'STAGE_ID'
,
'OPPORTUNITY'
,
'IS_MANUAL_OPPORTUNITY'
,
'ASSIGNED_BY_ID'
,
'DATE_CREATE'
,
],
'FILTER'
=> [
'=%TITLE'
=>
'%a'
,
'CATEGORY_ID'
=>
1
,
'TYPE_ID'
=>
'COMPLEX'
,
'STAGE_ID'
=>
'C1:NEW'
,
'>OPPORTUNITY'
=>
10000
,
'<=OPPORTUNITY'
=>
20000
,
'IS_MANUAL_OPPORTUNITY'
=>
'Y'
,
'@ASSIGNED_BY_ID'
=> [
1
,
6
],
'>DATE_CREATE'
=>
$sixMonthAgo
,
],
'ORDER'
=> [
'TITLE'
=>
'ASC'
,
'OPPORTUNITY'
=>
'ASC'
,
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
"37"
,
"TITLE"
:
"[A] Deal"
,
"TYPE_ID"
:
"COMPLEX"
,
"CATEGORY_ID"
:
"1"
,
"STAGE_ID"
:
"C1:NEW"
,
"OPPORTUNITY"
:
"19999.99"
,
"IS_MANUAL_OPPORTUNITY"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"1"
,
"DATE_CREATE"
:
"2024-09-02T18:37:18+02:00"
}
,
{
"ID"
:
"38"
,
"TITLE"
:
"[A] Deal"
,
"TYPE_ID"
:
"COMPLEX"
,
"CATEGORY_ID"
:
"1"
,
"STAGE_ID"
:
"C1:NEW"
,
"OPPORTUNITY"
:
"20000.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"6"
,
"DATE_CREATE"
:
"2024-09-02T18:37:38+02:00"
}
,
{
"ID"
:
"39"
,
"TITLE"
:
"[B] Sale"
,
"TYPE_ID"
:
"COMPLEX"
,
"CATEGORY_ID"
:
"1"
,
"STAGE_ID"
:
"C1:NEW"
,
"OPPORTUNITY"
:
"12500.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"1"
,
"DATE_CREATE"
:
"2024-04-09T23:11:01+02:00"
}
,
{
"ID"
:
"40"
,
"TITLE"
:
"[B] Deal"
,
"TYPE_ID"
:
"COMPLEX"
,
"CATEGORY_ID"
:
"1"
,
"STAGE_ID"
:
"C1:NEW"
,
"OPPORTUNITY"
:
"13500.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"6"
,
"DATE_CREATE"
:
"2024-08-08T19:00:14+02:00"
}
,
{
"ID"
:
"41"
,
"TITLE"
:
"[C] Deal"
,
"TYPE_ID"
:
"COMPLEX"
,
"CATEGORY_ID"
:
"1"
,
"STAGE_ID"
:
"C1:NEW"
,
"OPPORTUNITY"
:
"11500.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"6"
,
"DATE_CREATE"
:
"2024-05-08T09:38:23+02:00"
}
,
{
"ID"
:
"42"
,
"TITLE"
:
"[D] Deal"
,
"TYPE_ID"
:
"COMPLEX"
,
"CATEGORY_ID"
:
"1"
,
"STAGE_ID"
:
"C1:NEW"
,
"OPPORTUNITY"
:
"18500.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"6"
,
"DATE_CREATE"
:
"2024-07-02T15:38:32+02:00"
}
]
,
"total"
:
6
,
"time"
:
{
"start"
:
1725292115.026221
,
"finish"
:
1725292115.907058
,
"duration"
:
0.8808369636535645
,
"processing"
:
0.2484450340270996
,
"date_start"
:
"2024-09-02T17:48:35+02:00"
,
"date_finish"
:
"2024-09-02T17:48:35+02:00"
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
deal[]
The root element of the response. Contains an array of objects with information about the fields of deals.
Note that the structure of fields may change due to the
select
parameter
total
integer
The total number of found items
next
integer
Contains the value to be passed in the next request in the
start
parameter to get the next batch of data.
The
next
parameter appears in the response if the number of items matching your request exceeds
50
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
""
,
"error_description"
:
"Parameter 'filter' must be array."
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
-
Access denied
The user does not have permission to "read" deals
-
Parameter 'order' must be array
A non-object was passed to the
order
parameter
-
Parameter 'filter' must be array
A non-object was passed to the
filter
parameter
-
Failed to get list. General error
An unknown error occurred
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
Create a new deal crm.deal.add
Update Deal crm.deal.update
Get Deal by Id crm.deal.get
Delete deal crm.deal.delete
Get Deal Fields crm.deal.fields
Add an activity to a new lead or deal depending on the CRM mode
Copied
Was the article helpful?
Yes
No
Previous
Get a deal by Id
Next
Delete a deal

---

## Delete deal crm.deal.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/crm-deal-delete

Delete deal crm.deal.delete | Bitrix24 REST API and Marketplace Applications
Delete deal crm.deal.delete
Delete deal crm.deal.delete
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
Who can execute the method: any user with "delete" access permission for deals
The method
crm.deal.delete
removes a deal and all associated objects.
Deleting a deal will result in the removal of all related objects, such as activities, history, Timeline activities, and others.
Objects are deleted if they are not linked to other entities or items. If the objects are linked to other entities, only the link to the deleted deal will be removed.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the deal.
The identifier can be obtained using the methods
crm.deal.list
or
crm.deal.add
Related methods and topics
Delete existing settings for the recurring deal template crm.deal.recurring.delete
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
'{"ID":12}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":12,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.deal.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.delete'
,
{
id
:
12
,
}
);
const
result = response.
getData
().
result
;
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result)
;
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
'crm.deal.delete'
,
[
'id'
=>
12
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
'Info: '
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
'Error deleting deal: '
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
'crm.deal.delete'
,
{
id
:
12
,
},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result.
data
())
;
},
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
'crm.deal.delete'
,
[
'ID'
=>
12
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
1725019350.037109
,
"finish"
:
1725019355.903999
,
"duration"
:
5.86689019203186
,
"processing"
:
5.262096881866455
,
"date_start"
:
"2024-08-30T14:02:30+02:00"
,
"date_finish"
:
"2024-08-30T14:02:35+02:00"
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
Information about the request execution time
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
""
,
"error_description"
:
"ID is not defined or invalid."
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
Description
Value
ID is not defined or invalid
The
id
parameter either has no value or is not a positive integer
Access denied
The user does not have permission to "delete" deals
Not found
A deal with the provided
id
does not exist
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
Create a new deal crm.deal.add
Update Deal crm.deal.update
Get Deal by Id crm.deal.get
Get a list of deals crm.deal.list
Get Deal Fields crm.deal.fields
Copied
Was the article helpful?
Yes
No
Previous
Get a list of deals
Next
Get deal fields

---

## Get Deal Fields crm.deal.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/crm-deal-fields

Get Deal Fields crm.deal.fields | Bitrix24 REST API and Marketplace Applications
Get Deal Fields crm.deal.fields
Get Deal Fields crm.deal.fields
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
crm.deal.fields
returns a description of the deal fields, including custom fields. A table with the description of standard fields can be found in the article
Fields of Main CRM Entities
.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.fields
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
https://**put_your_bitrix24_address**/rest/crm.deal.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.fields'
,
{}
);
const
result = response.
getData
().
result
;
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result)
;
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
$id
=
123
;
// Example deal ID
$dealService
=
$serviceBuilder
->
getCRMScope
()->
deal
();
$dealResult
=
$dealService
->
get
(
$id
);
$itemResult
=
$dealResult
->
deal
();
print
(
"ID: "
.
$itemResult
->ID . PHP_EOL);
print
(
"Title: "
.
$itemResult
->TITLE . PHP_EOL);
print
(
"Type ID: "
.
$itemResult
->TYPE_ID . PHP_EOL);
print
(
"Category ID: "
.
$itemResult
->CATEGORY_ID . PHP_EOL);
print
(
"Stage ID: "
.
$itemResult
->STAGE_ID . PHP_EOL);
print
(
"Is New: "
. (
$itemResult
->IS_NEW ?
'Yes'
:
'No'
) . PHP_EOL);
print
(
"Is Recurring: "
. (
$itemResult
->IS_RECURRING ?
'Yes'
:
'No'
) . PHP_EOL);
print
(
"Probability: "
.
$itemResult
->PROBABILITY . PHP_EOL);
print
(
"Currency ID: "
.
$itemResult
->CURRENCY_ID . PHP_EOL);
print
(
"Opportunity: "
.
$itemResult
->OPPORTUNITY . PHP_EOL);
print
(
"Lead ID: "
.
$itemResult
->LEAD_ID . PHP_EOL);
print
(
"Company ID: "
.
$itemResult
->COMPANY_ID . PHP_EOL);
print
(
"Begin Date: "
. (
$itemResult
->BEGINDATE ?
$itemResult
->BEGINDATE->
format
(DATE_ATOM) :
'N/A'
) . PHP_EOL);
print
(
"Close Date: "
. (
$itemResult
->CLOSEDATE ?
$itemResult
->CLOSEDATE->
format
(DATE_ATOM) :
'N/A'
) . PHP_EOL);
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
'crm.deal.fields'
,
{},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result.
data
())
;
},
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
'crm.deal.fields'
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
"TITLE"
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
"Title"
}
,
"TYPE_ID"
:
{
"type"
:
"crm_status"
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
"statusType"
:
"DEAL_TYPE"
,
"title"
:
"Type"
}
,
"CATEGORY_ID"
:
{
"type"
:
"crm_category"
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
"Sales Funnel"
}
,
"STAGE_ID"
:
{
"type"
:
"crm_status"
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
"statusType"
:
"DEAL_STAGE"
,
"title"
:
"Deal Stage"
}
,
"STAGE_SEMANTIC_ID"
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
"Stage Group"
}
,
"IS_NEW"
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
"New Deal"
}
,
"IS_RECURRING"
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
"Recurring Deal"
}
,
"IS_RETURN_CUSTOMER"
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
"Repeat Deal"
}
,
"IS_REPEATED_APPROACH"
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
"Repeated Approach"
}
,
"PROBABILITY"
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
"Probability"
}
,
"CURRENCY_ID"
:
{
"type"
:
"crm_currency"
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
"Currency"
}
,
"OPPORTUNITY"
:
{
"type"
:
"double"
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
"Amount"
}
,
"IS_MANUAL_OPPORTUNITY"
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
"IS_MANUAL_OPPORTUNITY"
}
,
"TAX_VALUE"
:
{
"type"
:
"double"
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
"Tax Rate"
}
,
"COMPANY_ID"
:
{
"type"
:
"crm_company"
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
"Company"
,
"settings"
:
{
"parentEntityTypeId"
:
4
}
}
,
"CONTACT_ID"
:
{
"type"
:
"crm_contact"
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
"isDeprecated"
:
true
,
"title"
:
"Contact"
}
,
"CONTACT_IDS"
:
{
"type"
:
"crm_contact"
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
true
,
"isDynamic"
:
false
,
"title"
:
"Contacts"
}
,
"QUOTE_ID"
:
{
"type"
:
"crm_quote"
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
"Estimate"
,
"settings"
:
{
"parentEntityTypeId"
:
7
}
}
,
"BEGINDATE"
:
{
"type"
:
"date"
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
"Start Date"
}
,
"CLOSEDATE"
:
{
"type"
:
"date"
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
"Close Date"
}
,
"OPENED"
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
"Available to All"
}
,
"CLOSED"
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
"Closed"
}
,
"COMMENTS"
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
"Comment"
}
,
"ASSIGNED_BY_ID"
:
{
"type"
:
"user"
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
"Assignee"
}
,
"CREATED_BY_ID"
:
{
"type"
:
"user"
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
"Created By"
}
,
"MODIFY_BY_ID"
:
{
"type"
:
"user"
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
"Modified By"
}
,
"MOVED_BY_ID"
:
{
"type"
:
"user"
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
"MOVED_BY_ID"
}
,
"DATE_CREATE"
:
{
"type"
:
"datetime"
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
"Creation Date"
}
,
"DATE_MODIFY"
:
{
"type"
:
"datetime"
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
"Modification Date"
}
,
"MOVED_TIME"
:
{
"type"
:
"datetime"
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
"MOVED_TIME"
}
,
"SOURCE_ID"
:
{
"type"
:
"crm_status"
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
"statusType"
:
"SOURCE"
,
"title"
:
"Source"
}
,
"SOURCE_DESCRIPTION"
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
"Additional Info about Source"
}
,
"LEAD_ID"
:
{
"type"
:
"crm_lead"
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
"Lead"
,
"settings"
:
{
"parentEntityTypeId"
:
1
}
}
,
"ADDITIONAL_INFO"
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
"Additional Information"
}
,
"LOCATION_ID"
:
{
"type"
:
"location"
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
"Location"
}
,
"ORIGINATOR_ID"
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
"External Source"
}
,
"ORIGIN_ID"
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
"Identifier in External Source"
}
,
"UTM_SOURCE"
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
"Advertising System"
}
,
"UTM_MEDIUM"
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
"Traffic Type"
}
,
"UTM_CAMPAIGN"
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
"Campaign Identifier"
}
,
"UTM_CONTENT"
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
"Campaign Content"
}
,
"UTM_TERM"
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
"Campaign Search Condition"
}
,
"LAST_ACTIVITY_TIME"
:
{
"type"
:
"datetime"
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
"LAST_ACTIVITY_TIME"
}
,
"LAST_ACTIVITY_BY"
:
{
"type"
:
"user"
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
"LAST_ACTIVITY_BY"
}
}
,
"time"
:
{
"start"
:
1724857659.824873
,
"finish"
:
1724857660.790877
,
"duration"
:
0.9660041332244873
,
"processing"
:
0.3691408634185791
,
"date_start"
:
"2024-08-28T17:07:39+02:00"
,
"date_finish"
:
"2024-08-28T17:07:40+02:00"
,
"operating"
:
0
}
}
Returned Data
Returned Data
Title
type
Description
result
object
An object in the format:
{
field_1: value_1,
field_2: value_2,
...
field_n: value_n,
}
where:
field_n
— deal field
value_n
— information about the field in the format
crm_rest_field_description
time
time
Information about the request execution time
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
Create a new deal crm.deal.add
Update Deal crm.deal.update
Get Deal by Id crm.deal.get
Get a list of deals crm.deal.list
Delete deal crm.deal.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete a deal
Next
Set products in a deal

---

## Set Products in Deal crm.deal.productrows.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/crm-deal-productrows-set

Set Products in Deal crm.deal.productrows.set | Bitrix24 REST API and Marketplace Applications
Set Products in Deal crm.deal.productrows.set
Set Products in Deal crm.deal.productrows.set
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: user with "modify" access permission for the deal
The method
crm.deal.productrows.set
creates or updates the product rows of a deal. To modify only one row, use the methods
crm.item.productrow.*
.
Name
type
Description
id
*
integer
Identifier of the deal. Can be obtained using the method to get the list of deals:
crm.deal.list
or when creating a deal:
crm.deal.add
rows
object[]
Product rows
An array of objects in the following format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where
field_n
— name of the product row field
value_n
— value of this field
The list of available fields is described
below
.
List of Available Fields for Product Rows
List of Available Fields for Product Rows
Name
type
Description
PRODUCT_ID
integer
Identifier of the product in the catalog. The list of products can be obtained using the method
catalog.product.list
0
if not from the catalog
Default -
0
PRODUCT_NAME
string
Name of the product row. If
PRODUCT_ID
is provided, the name will be taken from the product
If both
PRODUCT_ID
and
PRODUCT_NAME
are not provided, then
PRODUCT_NAME
will be equal to
[{id}]
, where
{id}
is the identifier of the created product row
PRICE
double
Final cost of the product per unit
Default -
0.0
PRICE_EXCLUSIVE
double
Cost per unit considering discounts, excluding taxes
PRICE_NETTO
double
Cost per unit excluding discounts and taxes
PRICE_BRUTTO
double
Cost per unit excluding discounts, but including taxes
QUANTITY
double
Quantity of product units
Default -
1.0
DISCOUNT_TYPE_ID
integer
Type of discount
Possible types:
1
- Absolute
2
- Percentage
Default -
2
DISCOUNT_RATE
double
Discount value in percentage (if percentage discount type is used)
Default -
0.0
DISCOUNT_SUM
double
Absolute discount value (if absolute discount type is used)
Default -
0.0
TAX_RATE
double
Tax rate in percentage
TAX_INCLUDED
boolean
Indicator of whether tax is included in the price
Possible values:
Y
– tax included
N
– tax not included
Default -
N
MEASURE_CODE
catalog_measure.code
Unit of measure code
If
PRODUCT_ID
is provided, the default value will be taken from the product, otherwise
0
MEASURE_NAME
string
Text representation of the unit of measure (e.g., pcs, kg, m, l, etc.)
If
PRODUCT_ID
is provided, the default value will be taken from the product, otherwise
""
SORT
integer
Sorting
Default -
0
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
'{"id":5,"rows":[{"PRODUCT_ID":456,"PRICE":1000,"QUANTITY":10,"DISCOUNT_TYPE_ID":1,"DISCOUNT_SUM":100,"TAX_RATE":13,"MEASURE_CODE":796,"MEASURE_NAME":"pcs","SORT":10},{"PRODUCT_NAME":"Product #2","PRICE":500,"QUANTITY":5,"DISCOUNT_TYPE_ID":2,"DISCOUNT_RATE":10,"TAX_RATE":10,"MEASURE_CODE":166,"MEASURE_NAME":"kg","SORT":20}]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.productrows.set
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":5,"rows":[{"PRODUCT_ID":456,"PRICE":1000,"QUANTITY":10,"DISCOUNT_TYPE_ID":1,"DISCOUNT_SUM":100,"TAX_RATE":13,"MEASURE_CODE":796,"MEASURE_NAME":"pcs","SORT":10},{"PRODUCT_NAME":"Product #2","PRICE":500,"QUANTITY":5,"DISCOUNT_TYPE_ID":2,"DISCOUNT_RATE":10,"TAX_RATE":10,"MEASURE_CODE":166,"MEASURE_NAME":"kg","SORT":20}],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.deal.productrows.set
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.productrows.set'
,
{
id
:
5
,
rows
: [
{
PRODUCT_ID
:
456
,
PRICE
:
1000
,
QUANTITY
:
10
,
DISCOUNT_TYPE_ID
:
1
,
DISCOUNT_SUM
:
100
,
TAX_RATE
:
13
,
MEASURE_CODE
:
796
,
MEASURE_NAME
:
"pcs"
,
SORT
:
10
,
},
{
PRODUCT_NAME
:
"Product #2"
,
PRICE
:
500
,
QUANTITY
:
5
,
DISCOUNT_TYPE_ID
:
2
,
DISCOUNT_RATE
:
10
,
TAX_RATE
:
10
,
MEASURE_CODE
:
166
,
MEASURE_NAME
:
"kg"
,
SORT
:
20
,
},
],
}
);
const
result = response.
getData
().
result
;
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result)
;
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
'crm.deal.productrows.set'
,
[
'id'
=>
5
,
'rows'
=> [
[
'PRODUCT_ID'
=>
456
,
'PRICE'
=>
1000
,
'QUANTITY'
=>
10
,
'DISCOUNT_TYPE_ID'
=>
1
,
'DISCOUNT_SUM'
=>
100
,
'TAX_RATE'
=>
13
,
'MEASURE_CODE'
=>
796
,
'MEASURE_NAME'
=>
"pcs"
,
'SORT'
=>
10
,
],
[
'PRODUCT_NAME'
=>
"Product #2"
,
'PRICE'
=>
500
,
'QUANTITY'
=>
5
,
'DISCOUNT_TYPE_ID'
=>
2
,
'DISCOUNT_RATE'
=>
10
,
'TAX_RATE'
=>
10
,
'MEASURE_CODE'
=>
166
,
'MEASURE_NAME'
=>
"kg"
,
'SORT'
=>
20
,
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
'Error setting deal product rows: '
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
'crm.deal.productrows.set'
,
{
id
:
5
,
rows
: [
{
PRODUCT_ID
:
456
,
PRICE
:
1000
,
QUANTITY
:
10
,
DISCOUNT_TYPE_ID
:
1
,
DISCOUNT_SUM
:
100
,
TAX_RATE
:
13
,
MEASURE_CODE
:
796
,
MEASURE_NAME
:
"pcs"
,
SORT
:
10
,
},
{
PRODUCT_NAME
:
"Product #2"
,
PRICE
:
500
,
QUANTITY
:
5
,
DISCOUNT_TYPE_ID
:
2
,
DISCOUNT_RATE
:
10
,
TAX_RATE
:
10
,
MEASURE_CODE
:
166
,
MEASURE_NAME
:
"kg"
,
SORT
:
20
,
},
],
},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result.
data
())
;
},
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
'crm.deal.productrows.set'
,
[
'id'
=>
5
,
'rows'
=> [
[
'PRODUCT_ID'
=>
456
,
'PRICE'
=>
1000
,
'QUANTITY'
=>
10
,
'DISCOUNT_TYPE_ID'
=>
1
,
'DISCOUNT_SUM'
=>
100
,
'TAX_RATE'
=>
13
,
'MEASURE_CODE'
=>
796
,
'MEASURE_NAME'
=>
"pcs"
,
'SORT'
=>
10
,
],
[
'PRODUCT_NAME'
=>
"Product #2"
,
'PRICE'
=>
500
,
'QUANTITY'
=>
5
,
'DISCOUNT_TYPE_ID'
=>
2
,
'DISCOUNT_RATE'
=>
10
,
'TAX_RATE'
=>
10
,
'MEASURE_CODE'
=>
166
,
'MEASURE_NAME'
=>
"kg"
,
'SORT'
=>
20
,
],
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
1735134795.171273
,
"finish"
:
1735134796.404978
,
"duration"
:
1.2337050437927246
,
"processing"
:
0.9462978839874268
,
"date_start"
:
"2024-12-25T15:53:15+02:00"
,
"date_finish"
:
"2024-12-25T15:53:16+02:00"
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
"ERROR_CORE"
,
"error_description"
:
"Discount Sum (DISCOUNT_SUM) is required if Percentage Discount Type (DISCOUNT_TYPE_ID) is defined and Discount Rate (DISCOUNT_RATE) is 100%<br>"
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
Description
Value
The parameter id is invalid or not defined.
The parameter
id
contains an incorrect value
Access denied
The user does not have permission to "modify" the deal
Not found
The deal with the provided
id
was not found
Discount Rate (
DISCOUNT_RATE
) is required if Percentage Discount Type (
DISCOUNT_TYPE_ID
) is defined.
DISCOUNT_TYPE_ID = 2
was provided and
DISCOUNT_RATE
was not provided
Discount Sum (
DISCOUNT_SUM
) is required if Percentage Discount Type (
DISCOUNT_TYPE_ID
) is defined and Discount Rate (
DISCOUNT_RATE
) is 100%
DISCOUNT_RATE = 100
and
DISCOUNT_TYPE_ID = 2
were provided and
DISCOUNT_SUM
was not provided
Discount Sum (
DISCOUNT_SUM
) is required if Monetary Discount Type (
DISCOUNT_TYPE_ID
) is defined.
DISCOUNT_TYPE_ID = 1
was provided and
DISCOUNT_SUM
was not provided
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
Get Deal Product Rows crm.deal.productrows.get
Copied
Was the article helpful?
Yes
No
Previous
Get deal fields
Next
Get deal products

---

## Get Deal Product Rows crm.deal.productrows.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/crm-deal-productrows-get

Get Deal Product Rows crm.deal.productrows.get | Bitrix24 REST API and Marketplace Applications
Get Deal Product Rows crm.deal.productrows.get
Get Deal Product Rows crm.deal.productrows.get
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: user with "read" access permission for the deal
The method
crm.deal.productrows.get
returns the product rows of a deal.
Name
type
Description
id
*
integer
Identifier of the deal. Can be obtained using the method to get the list of deals:
crm.deal.list
or when creating a deal:
crm.deal.add
Required parameters are marked with *
Code Examples
Code Examples
Get the product rows of the deal with
id = 5
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
'{"id":5}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.productrows.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":5,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.deal.productrows.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.productrows.get'
,
{
id
:
5
,
}
);
const
result = response.
getData
().
result
;
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result)
;
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
'crm.deal.productrows.get'
,
[
'id'
=>
5
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
'Error getting deal product rows: '
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
'crm.deal.productrows.get'
,
{
id
:
5
,
},
(
result
) =>
{
result.
error
()
?
console
.
error
(result.
error
())
:
console
.
info
(result.
data
())
;
},
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
'crm.deal.productrows.get'
,
[
'id'
=>
5
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
"5"
,
"OWNER_ID"
:
"5"
,
"OWNER_TYPE"
:
"D"
,
"PRODUCT_ID"
:
450
,
"PRODUCT_NAME"
:
"Product #2"
,
"ORIGINAL_PRODUCT_NAME"
:
"Product #2"
,
"PRODUCT_DESCRIPTION"
:
null
,
"PRICE"
:
899.1
,
"PRICE_EXCLUSIVE"
:
899.1
,
"PRICE_NETTO"
:
999
,
"PRICE_BRUTTO"
:
999
,
"PRICE_ACCOUNT"
:
"899.10"
,
"QUANTITY"
:
1
,
"DISCOUNT_TYPE_ID"
:
2
,
"DISCOUNT_RATE"
:
10
,
"DISCOUNT_SUM"
:
99.9
,
"TAX_RATE"
:
null
,
"TAX_INCLUDED"
:
"Y"
,
"CUSTOMIZED"
:
"Y"
,
"MEASURE_CODE"
:
796
,
"MEASURE_NAME"
:
"pcs"
,
"SORT"
:
10
,
"XML_ID"
:
"sale_basket_651"
,
"TYPE"
:
1
,
"STORE_ID"
:
0
,
"RESERVE_ID"
:
31
,
"DATE_RESERVE_END"
:
"12/26/2024"
,
"RESERVE_QUANTITY"
:
1
}
,
{
"ID"
:
"4"
,
"OWNER_ID"
:
"5"
,
"OWNER_TYPE"
:
"D"
,
"PRODUCT_ID"
:
449
,
"PRODUCT_NAME"
:
"Product #1"
,
"ORIGINAL_PRODUCT_NAME"
:
"Product #1"
,
"PRODUCT_DESCRIPTION"
:
"Detailed description"
,
"PRICE"
:
100
,
"PRICE_EXCLUSIVE"
:
100
,
"PRICE_NETTO"
:
100
,
"PRICE_BRUTTO"
:
100
,
"PRICE_ACCOUNT"
:
"100.00"
,
"QUANTITY"
:
1
,
"DISCOUNT_TYPE_ID"
:
2
,
"DISCOUNT_RATE"
:
0
,
"DISCOUNT_SUM"
:
0
,
"TAX_RATE"
:
null
,
"TAX_INCLUDED"
:
"Y"
,
"CUSTOMIZED"
:
"Y"
,
"MEASURE_CODE"
:
796
,
"MEASURE_NAME"
:
"pcs"
,
"SORT"
:
20
,
"XML_ID"
:
"sale_basket_650"
,
"TYPE"
:
1
,
"STORE_ID"
:
1
,
"RESERVE_ID"
:
30
,
"DATE_RESERVE_END"
:
"12/26/2024"
,
"RESERVE_QUANTITY"
:
1
}
]
,
"time"
:
{
"start"
:
1734969122.936213
,
"finish"
:
1734969123.586089
,
"duration"
:
0.6498758792877197
,
"processing"
:
0.14046597480773926
,
"date_start"
:
"2024-12-23T17:52:02+02:00"
,
"date_finish"
:
"2024-12-23T17:52:03+02:00"
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
productrow[]
Root element of the response containing an array of deal product rows
time
time
Information about the execution time of the request
Product Row Type
Product Row Type
Name
type
Description
ID
integer
Identifier of the product row
OWNER_ID
integer
Identifier of the entity to which the product is linked. For this method, it will always equal the
id
of the deal
OWNER_TYPE
string
String identifier of the entity type to which the product is linked. For this method, it will always equal
D
PRODUCT_ID
integer
Identifier of the product in the catalog.
0
if not from the catalog
For more detailed information about the product, use
catalog.product.get
PRODUCT_NAME
string
Name of the product row
ORIGINAL_PRODUCT_NAME
string
Name of the product row in the catalog
PRODUCT_DESCRIPTION
string
Description of the product row
PRICE
double
Final cost of the product per unit
PRICE_EXCLUSIVE
double
Cost per unit considering discounts, excluding taxes
PRICE_NETTO
double
Cost per unit excluding discounts and taxes
PRICE_BRUTTO
double
Cost per unit excluding discounts but including taxes
PRICE_ACCOUNT
string
Cost of the product in "report currency"
QUANTITY
integer
Quantity of product units
DISCOUNT_TYPE_ID
integer
Type of discount
Possible types:
1
- Absolute
2
- Percentage
DISCOUNT_RATE
double
Discount value in percentage (if using the percentage discount type)
DISCOUNT_SUM
double
Absolute discount value (if using the absolute discount type)
TAX_RATE
double
Tax rate in percentage
TAX_INCLUDED
boolean
Indicator of whether tax is included in the price
Possible values:
Y
– tax included
N
– tax not included
CUSTOMIZED
boolean
Customized (Deprecated)
Possible values:
Y
- Yes
N
- No
MEASURE_CODE
catalog_measure.code
Measure unit code
MEASURE_NAME
string
Text representation of the measure unit (e.g., pcs, kg, m, l, etc.)
SORT
integer
Sorting
XML_ID
string
External code of the product
TYPE
integer
Type of product
Possible values:
1
- Simple product
4
- Trade offer/variation
7
- Service
STORE_ID
integer
Identifier of the inventory. For detailed information about the inventory, use
catalog.store.get
RESERVE_ID
integer
Identifier of the reserve
DATE_RESERVE_END
date
Date of reserve expiration
RESERVE_QUANTITY
integer
Quantity of reserved product units
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
""
,
"error_description"
:
"The parameter id is invalid or not defined."
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
Description
Value
The parameter id is invalid or not defined.
The parameter
id
has an incorrect value
Access denied
The user does not have permission to "read" the deal
Not found
The deal with the provided
id
was not found
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
Set Products in Deal crm.deal.productrows.set
Copied
Was the article helpful?
Yes
No
Previous
Set products in a deal
Next
Overview of Events

---

## Overview of Events When Working with Deals

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/events/index

Overview of Events When Working with Deals | Bitrix24 REST API and Marketplace Applications
Overview of Events When Working with Deals
Overview of Events When Working with Deals
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, updating, deletion, and movement of deals.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to the events
onCrmDealAdd
,
onCrmDealUpdate
, and
onCrmDealDelete
through:
outgoing webhook
application
and the method
event.bind
You can subscribe to the event
onCrmDealMoveToCategory
only through the
application
and the method
event.bind
.
An example of a handler code for the event is described in the article
How to Test Your Handler for Processing Bitrix24 Events
.
Server Availability for Sending and Receiving Events
Server Availability for Sending and Receiving Events
The event handler server must be accessible from the outside. To configure the accessibility of the event handler server and application, refer to the article
Required network access
.
For cloud Bitrix24, no additional configuration is required. For on-premise Bitrix24, configure accessibility on the server or hosting according to the article
Required network access
.
Overview of Events
Overview of Events
Scope:
crm
Who can subscribe: any user
Event
Triggered By
onCrmDealAdd
When a deal is created manually or via the method
crm.deal.add
onCrmDealUpdate
When a deal is modified manually or via the method
crm.deal.update
onCrmDealDelete
When a deal is deleted manually or via the method
crm.deal.delete
onCrmDealMoveToCategory
When the deal's funnel is changed manually or via the method
crm.item.update
Copied
Was the article helpful?
Yes
No
Previous
Get deal products
Next
When Creating a Deal

---

## Event when creating a deal onCrmDealAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/events/on-crm-deal-add

Event when creating a deal onCrmDealAdd | Bitrix24 REST API and Marketplace Applications
Event when creating a deal onCrmDealAdd
Event when creating a deal onCrmDealAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMDEALADD
will trigger when a deal is created.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMDEALADD"
,
"event_handler_id"
:
"185"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6641"
}
}
,
"ts"
:
"1735374081"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"L"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic code of the event.
In this case —
ONCRMDEALADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created deal.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created deal.
The structure is described
below
ts
timestamp
Date and time of sending the event from the
event queue
auth
object
Object containing authorization parameters and information about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
integer
Identifier of the created deal
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
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
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event on deal update onCrmDealUpdate
Event on deal deletion onCrmDealDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Updating a Deal

---

## Event on deal update onCrmDealUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/events/on-crm-deal-update

Event on deal update onCrmDealUpdate | Bitrix24 REST API and Marketplace Applications
Event on deal update onCrmDealUpdate
Event on deal update onCrmDealUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMDEALUPDATE
will trigger when a deal is updated.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMDEALUPDATE"
,
"event_handler_id"
:
"201"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"759"
}
}
,
"ts"
:
"1736405807"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"F"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic code of the event.
In this case —
ONCRMDEALUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated deal.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the updated deal.
The structure is described
below
ts
timestamp
Date and time the event was sent from the
event queue
auth
object
Object containing authorization parameters and information about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
integer
Identifier of the updated deal
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
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
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event when creating a deal onCrmDealAdd
Event on deal deletion onCrmDealDelete
Copied
Was the article helpful?
Yes
No
Previous
When Creating a Deal
Next
When Deleting a Deal

---

## Event on deal deletion onCrmDealDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/events/on-crm-deal-delete

Event on deal deletion onCrmDealDelete | Bitrix24 REST API and Marketplace Applications
Event on deal deletion onCrmDealDelete
Event on deal deletion onCrmDealDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMDEALDELETE
will trigger upon the deletion of a deal.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMDEALDELETE"
,
"event_handler_id"
:
"647"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"1765"
}
}
,
"ts"
:
"1736405294"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"L"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic code of the event.
In this case —
ONCRMDEALDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted deal.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted deal.
The structure is described
below
ts
timestamp
Date and time of the event sent from the
event queue
auth
object
Object containing authorization parameters and information about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
integer
Identifier of the deleted deal
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
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
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event on deal update onCrmDealUpdate
Event when creating a deal onCrmDealAdd
Copied
Was the article helpful?
Yes
No
Previous
When Updating a Deal
Next
When Changing the Sales Funnel

---

## Event on changing the deal's Sales Funnel onCrmDealMoveToCategory

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/events/on-crm-deal-move-to-category

Event on changing the deal's Sales Funnel onCrmDealMoveToCategory | Bitrix24 REST API and Marketplace Applications
Event on changing the deal's Sales Funnel onCrmDealMoveToCategory
Event on changing the deal's Sales Funnel onCrmDealMoveToCategory
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMDEALMOVETOCATEGORY
will trigger when the deal's Sales Funnel changes.
Currently, you can only subscribe to the event from the
application
.
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMDEALMOVETOCATEGORY"
,
"event_handler_id"
:
"655"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6675"
,
"CATEGORY_ID"
:
"1"
,
"STAGE_ID"
:
"C1:NEW"
}
}
,
"ts"
:
"1736424182"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"L"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic event code.
In this case —
ONCRMDEALMOVETOCATEGORY
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the modified deal.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the modified deal.
The structure is described
below
ts
timestamp
Date and time the event was sent from the
event queue
auth
object
Object containing authorization parameters and data about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
integer
Identifier of the modified deal
CATEGORY_ID
integer
Identifier of the new Sales Funnel
STAGE_ID
string
Identifier of the new deal stage
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
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
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event when creating a deal onCrmDealAdd
Event on deal update onCrmDealUpdate
Event on deal deletion onCrmDealDelete
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Deal
Next
Overview of Methods

---

## Linking Deals to Contacts: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/contacts/index

Linking Deals to Contacts: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Linking Deals to Contacts: Overview of Methods
Linking Deals to Contacts: Overview of Methods
Benefits of Linking Deals to Contacts
Overview of Methods
Using the group of methods
crm.deal.contact.*
, you can establish or remove the connection between contacts and a deal. Use the methods
crm.deal.contact.*
for working with a single contact, and the methods
crm.deal.contact.items.*
for managing a group of contacts.
Quick navigation:
all methods
Benefits of Linking Deals to Contacts
Benefits of Linking Deals to Contacts
The deal detail form displays information about related contacts: name, phone number, e-mail, and position.
You can call or send an e-mail directly from the deal detail form without navigating to the contact detail form.
Communication with the client: e-mails, calls, and chats from open lines will be stored in both the contact detail form and the deal detail form. Communications are not attached to closed deals.
CoPilot in CRM processes client calls from the deal detail form: it transcribes recordings, summarizes conversations, and fills in fields in the CRM activity.
When
generating documents from a template
, you can use symbolic codes that automatically insert data from related contacts into the document.
User Documentation
CoPilot in CRM
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: depending on the method
Method
Description
crm.deal.contact.add
Adds a contact to a deal
crm.deal.contact.items.set
Adds multiple contacts to a deal
crm.deal.contact.fields
Returns the fields for the deal-contact link
crm.deal.contact.items.get
Retrieves a set of contacts linked to a deal
crm.deal.contact.delete
Removes a contact from the specified deal
crm.deal.contact.items.delete
Deletes a set of contacts linked to the specified deal
Copied
Was the article helpful?
Yes
No
Previous
When Changing the Set of Values for a List-Type Custom Field
Next
Add a single contact

---

## Add Contact to Deal crm.deal.contact.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/contacts/crm-deal-contact-add

Add Contact to Deal crm.deal.contact.add | Bitrix24 REST API and Marketplace Applications
Add Contact to Deal crm.deal.contact.add
Add Contact to Deal crm.deal.contact.add
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.contact.add
adds a contact to the specified deal.
Parameter
Description
id
Identifier of the deal.
fields
An object with the following
fields
:
CONTACT_ID
- identifier of the contact (required field)
SORT
- sorting index
IS_PRIMARY
- primary contact flag
Note
To find out the required format for the fields, execute the method
crm.deal.contact.fields
and check the format of the incoming values for these fields.
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Add multiple contacts

---

## Add Multiple Contacts to a Deal crm.deal.contact.items.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/contacts/crm-deal-contact-items-set

Add Multiple Contacts to a Deal crm.deal.contact.items.set | Bitrix24 REST API and Marketplace Applications
Add Multiple Contacts to a Deal crm.deal.contact.items.set
Add Multiple Contacts to a Deal crm.deal.contact.items.set
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.contact.items.set
sets a collection of contacts associated with the specified deal.
Parameter
Description
id
Identifier of the deal.
items
A collection of contacts represented as an array of objects with the following
fields
:
CONTACT_ID
- identifier of the contact (required field)
SORT
- sorting index
IS_PRIMARY
- primary contact flag
Copied
Was the article helpful?
Yes
No
Previous
Add a single contact
Next
Get fields for the deal-contact relationship

---

## Get Fields for Deal-Contact Connection crm.deal.contact.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/contacts/crm-deal-contact-fields

Get Fields for Deal-Contact Connection crm.deal.contact.fields | Bitrix24 REST API and Marketplace Applications
Get Fields for Deal-Contact Connection crm.deal.contact.fields
Get Fields for Deal-Contact Connection crm.deal.contact.fields
Example
Returned Fields
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.contact.fields
returns the description of the fields used by the methods of the
crm.deal.contact.*
family, namely
crm.deal.contact.items.get
,
crm.deal.contact.items.set
,
crm.deal.contact.add
, etc.
Without parameters.
Example
Example
JS
PHP
BX24.js
try
{
const
response =
await
$b24.
callMethod
(
"crm.deal.contact.fields"
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
'crm.deal.contact.fields'
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
'Error fetching deal contact fields: '
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
"crm.deal.contact.fields"
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
dir
(result.
data
());
}
);
How to Use Examples in Documentation
Returned Fields
Returned Fields
Field
Description
SORT
integer
Sort index (number). Determines the order in which linked contacts will be displayed in the deal.
IS_PRIMARY
char
[Y/N] Indicates whether the binding is primary. There is always a primary contact in the deal. For it,
IS_PRIMARY=Y
, for others
IS_PRIMARY=N
.
CONTACT_ID
integer
Identifier of the contact linked to the deal (number).
Copied
Was the article helpful?
Yes
No
Previous
Add multiple contacts
Next
Get contacts associated with the deal

---

## Get a set of contacts associated with a deal crm.deal.contact.items.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/contacts/crm-deal-contact-items-get

Get a set of contacts associated with a deal crm.deal.contact.items.get | Bitrix24 REST API and Marketplace Applications
Get a set of contacts associated with a deal crm.deal.contact.items.get
Get a set of contacts associated with a deal crm.deal.contact.items.get
Example
Response in case of success
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.contact.items.get
returns a set of contacts associated with the specified deal.
Parameter
Description
id
*
Identifier of the deal.
Required parameters are marked with *
Example
Example
JS
PHP
BX24.js
try
{
const
id =
prompt
(
"Enter ID"
);
const
response =
await
$b24.
callMethod
(
"crm.deal.contact.items.get"
,
{
id
: id
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
(error)
{
console
.
error
(error);
}
try
{
$dealId
=
123
;
// Replace with the actual deal ID
$result
=
$serviceBuilder
->
getCRMScope
()
->
dealContact
()
->
itemsGet
(
$dealId
);
foreach
(
$result
->
getDealContacts
()
as
$item
) {
print
(
"CONTACT_ID: "
.
$item
->CONTACT_ID .
"\n"
);
print
(
"SORT: "
.
$item
->SORT .
"\n"
);
print
(
"ROLE_ID: "
.
$item
->ROLE_ID .
"\n"
);
print
(
"IS_PRIMARY: "
.
$item
->IS_PRIMARY .
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
var
id =
prompt
(
"Enter ID"
);
BX24
.
callMethod
(
"crm.deal.contact.items.get"
,
{
id
: id
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
How to Use Examples in Documentation
Response in case of success
Response in case of success
The result is returned as an array of objects, each containing the following fields:
Field
Description
CONTACT_ID
Identifier of the contact
SORT
Sort index
ROLE_ID
Identifier of the role (reserved)
IS_PRIMARY
Flag for primary contact
Copied
Was the article helpful?
Yes
No
Previous
Get fields for the deal-contact relationship
Next
Remove a contact from the specified deal

---

## Remove Contact from Specified Deal crm.deal.contact.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/contacts/crm-deal-contact-delete

Remove Contact from Specified Deal crm.deal.contact.delete | Bitrix24 REST API and Marketplace Applications
Remove Contact from Specified Deal crm.deal.contact.delete
Remove Contact from Specified Deal crm.deal.contact.delete
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.contact.delete
removes a contact from the specified deal.
Parameter
Description
id
*
Identifier of the deal.
fields
An object with the following
fields
:
CONTACT_ID
- identifier of the contact (required field)
Required parameters are marked with *
Copied
Was the article helpful?
Yes
No
Previous
Get contacts associated with the deal
Next
Remove a set of contacts associated with the specified deal

---

## Delete the set of contacts associated with the specified deal crm.deal.contact.items.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/contacts/crm-deal-contact-items-delete

Delete the set of contacts associated with the specified deal crm.deal.contact.items.delete | Bitrix24 REST API and Marketplace Applications
Delete the set of contacts associated with the specified deal crm.deal.contact.items.delete
Delete the set of contacts associated with the specified deal crm.deal.contact.items.delete
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.contact.items.delete
clears the set of contacts associated with the specified deal.
Parameter
Description
id
*
Identifier of the deal.
Required parameters are marked with *
Example
Example
JS
PHP
BX24.js
try
{
const
id =
prompt
(
"Enter ID"
);
const
response =
await
$b24.
callMethod
(
"crm.deal.contact.items.delete"
,
{
id
: id
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
info
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
$dealId
=
123
;
// Replace with the actual deal ID you want to delete contacts from
$result
=
$serviceBuilder
->
getCRMScope
()->
dealContact
()->
itemsDelete
(
$dealId
);
if
(
$result
->
isSuccess
()) {
print
(
"Successfully deleted contacts from deal ID:
$dealId
"
);
}
else
{
print
(
"Failed to delete contacts. Result: "
.
json_encode
(
$result
));
}
}
catch
(
Throwable
$e
) {
print
(
"An error occurred: "
.
$e
->
getMessage
());
}
var
id =
prompt
(
"Enter ID"
);
BX24
.
callMethod
(
"crm.deal.contact.items.delete"
,
{
id
: id
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
Required parameters are marked with *
Copied
Was the article helpful?
Yes
No
Previous
Remove a contact from the specified deal
Next
Overview of Methods

---

## Managing Deal Cards: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/custom-form/index

Managing Deal Cards: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Managing Deal Cards: Overview of Methods
Managing Deal Cards: Overview of Methods
Linking Deal Cards with Other Objects
Universal Methods for Managing Cards
Overview of Methods
The group of methods
crm.deal.details.configuration.*
manages the settings of the card for two views:
"General view" — the card view for all employees
"My view" — personal card settings for the employee
For each card view, sections can be configured, and within each section, a list of fields can be defined. For example, create a section called "Payment Information" and include the fields "Amount and Currency" and "Advance" within it. For fields that do not pertain to payment information, create a different section.
Quick navigation:
all methods
Linking Deal Cards with Other Objects
Linking Deal Cards with Other Objects
User.
The user identifier
userId
is used when setting personal card settings. The user identifier can be obtained using the method
user.get
.
Deal Fields.
The identifiers of the fields are used when setting visible fields in the card section. The identifiers for system and custom deal fields can be obtained using the method
crm.deal.fields
.
Deal Funnels.
Different deal funnels can have their own card views configured. For the "Sales" funnel, create a card view with specific sections and fields. For the "Service" funnel — with different ones.
To switch between card settings for different funnels, use the parameter
dealCategoryId
— the ID of the deal funnel.
To obtain the IDs of deal funnels, use the method
crm.category.list
with the parameter
entityTypeId: 2
.
Universal Methods for Managing Cards
Universal Methods for Managing Cards
Alongside the methods
crm.deal.details.configuration.*
for configuring deal cards, the group of universal methods
crm.item.details.configuration.*
can also be used. The capabilities of these methods are the same, but the execution time may differ.
Universal methods
crm.item.details.configuration.*
have an additional parameter
entityTypeId
— the ID of the object type. The
entityTypeId
parameter allows universal methods to be applied to any CRM object. To manage a deal card through a universal method, pass
entityTypeId: 2
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: any user
Method
Description
crm.deal.details.configuration.get
Retrieves the settings of deal cards
crm.deal.details.configuration.reset
Resets the settings of deal cards
crm.deal.details.configuration.set
Allows setting the settings of deal cards
crm.deal.details.configuration.forceCommonScopeForAll
Forcefully sets a common deal card for all users
Copied
Was the article helpful?
Yes
No
Previous
Remove a set of contacts associated with the specified deal
Next
Get Card Parameters

---

## Get parameters of crm.deal.details.configuration.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/custom-form/crm-deal-details-configuration-get

Get parameters of crm.deal.details.configuration.get | Bitrix24 REST API and Marketplace Applications
Get parameters of crm.deal.details.configuration.get
Get parameters of crm.deal.details.configuration.get
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.details.configuration.get
retrieves the settings for deal cards. It reads the personal settings of the specified user or the general settings defined for all users.
Warning
Please note that the settings for deal cards of different directions (or funnels) may differ from each other.
To switch between the settings of deal cards for different directions, the parameter
dealCategoryId
is used.
Parameter
Description
scope
unknown
The scope of the settings. Acceptable values:
P
- personal settings,
C
- general settings.
userId
unknown
User identifier. If not specified, the current one is used. Required only when requesting personal settings.
extras
unknown
Additional parameters. Here, the parameter
dealCategoryId
can be specified for deals.
Examples
Examples
PHP
BX24.js
try
{
//Request personal settings for deal cards for the user with ID 1.
$response1
=
$b24Service
->core
->
call
(
"crm.deal.details.configuration.get"
,
[
'scope'
=>
"P"
,
'userId'
=>
1
]
);
$result1
=
$response1
->
getResponseData
()
->
getResult
();
echo
'Personal deal details configuration for user 1: '
.
print_r
(
$result1
,
true
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
'Error getting personal deal details configuration: '
.
$e
->
getMessage
();
}
try
{
//Request general settings for deal cards for the general direction.
$response2
=
$b24Service
->core
->
call
(
"crm.deal.details.configuration.get"
,
[
'scope'
=>
"C"
]
);
$result2
=
$response2
->
getResponseData
()
->
getResult
();
echo
'Common deal details configuration for general direction: '
.
print_r
(
$result2
,
true
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
'Error getting common deal details configuration: '
.
$e
->
getMessage
();
}
try
{
//Request general settings for deal cards for the direction with ID 1.
$response3
=
$b24Service
->core
->
call
(
"crm.deal.details.configuration.get"
,
[
'scope'
=>
"C"
,
'extras'
=> [
'dealCategoryId'
=>
1
]
]
);
$result3
=
$response3
->
getResponseData
()
->
getResult
();
echo
'Common deal details configuration for direction with ID 1: '
.
print_r
(
$result3
,
true
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
'Error getting common deal details configuration for direction with ID 1: '
.
$e
->
getMessage
();
}
//--
//Request personal settings for deal cards for the user with ID 1.
BX24
.
callMethod
(
"crm.deal.details.configuration.get"
,
{
scope
:
"P"
,
userId
:
1
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
//Request general settings for deal cards for the general direction.
BX24
.
callMethod
(
"crm.deal.details.configuration.get"
,
{
scope
:
"C"
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
//Request general settings for deal cards for the direction with ID 1.
BX24
.
callMethod
(
"crm.deal.details.configuration.get"
,
{
scope
:
"C"
,
extras
: {
dealCategoryId
:
1
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
//--
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Reset Card Parameters

---

## Reset Deal Card Settings crm.deal.details.configuration.reset

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/custom-form/crm-deal-details-configuration-reset

Reset Deal Card Settings crm.deal.details.configuration.reset | Bitrix24 REST API and Marketplace Applications
Reset Deal Card Settings crm.deal.details.configuration.reset
Reset Deal Card Settings crm.deal.details.configuration.reset
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.details.configuration.reset
resets the settings of deal cards. It removes personal settings for the specified user or the general settings defined for all users.
Warning
Please note that the settings for deal cards of different directions (or funnels) may differ from each other.
To switch between the settings of deal cards of different directions, the parameter
dealCategoryId
is used.
Parameter
Description
scope
unknown
The scope of the settings. Allowed values:
P
- personal settings,
C
- general settings.
userId
unknown
User identifier. If not specified, the current user is taken. Needed only when resetting personal settings.
extras
unknown
Additional parameters. Here, the parameter
dealCategoryId
can be specified for deals.
Examples
Examples
JS
PHP
BX24.js
try
{
const
response =
await
$b24.
callMethod
(
"crm.deal.details.configuration.reset"
,
{
scope
:
"P"
,
userId
:
1
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
'crm.deal.details.configuration.reset'
,
[
'scope'
=>
'P'
,
'userId'
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
'Error resetting deal details configuration: '
.
$e
->
getMessage
();
}
//---
//Reset personal settings of the general direction deal card for the user with identifier 1.
BX24
.
callMethod
(
"crm.deal.details.configuration.reset"
,
{
scope
:
"P"
,
userId
:
1
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
//---
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get Card Parameters
Next
Set Individual Card Parameters

---

## Set Parameters for the Individual Card crm.deal.details.configuration.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/custom-form/crm-deal-details-configuration-set

Set Parameters for the Individual Card crm.deal.details.configuration.set | Bitrix24 REST API and Marketplace Applications
Set Parameters for the Individual Card crm.deal.details.configuration.set
Set Parameters for the Individual Card crm.deal.details.configuration.set
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.details.configuration.set
allows you to set the settings for deal cards. The method records the personal settings of the specified user’s card or general settings for all users.
Warning
Please note that the settings for deal cards of different directions (or funnels) may differ from each other.
To switch between the settings of deal cards of different directions, the parameter
dealCategoryId
is used.
Parameter
Description
scope
unknown
The scope of the settings. Acceptable values:
P
- personal settings,
C
- general settings.
userId
unknown
User identifier. If not specified, the current one is used. Required only when setting personal settings.
extras
unknown
Additional parameters. Here, for deals, the parameter
dealCategoryId
can be specified.
Examples
Examples
JS
PHP
BX24.js
try
{
const
response =
await
$b24.
callMethod
(
"crm.deal.details.configuration.set"
,
{
scope
:
"P"
,
userId
:
1
,
data
:
[
{
name
:
"main"
,
title
:
"About the Deal"
,
type
:
"section"
,
elements
:
[
{
name
:
"TITLE"
},
{
name
:
"OPPORTUNITY_WITH_CURRENCY"
},
{
name
:
"STAGE_ID"
},
{
name
:
"BEGINDATE"
},
{
name
:
"CLOSEDATE"
},
{
name
:
"CLIENT"
}
]
},
{
name
:
"additional"
,
title
:
"Additional Information"
,
type
:
"section"
,
elements
:
[
{
name
:
"TYPE_ID"
},
{
name
:
"SOURCE_ID"
},
{
name
:
"SOURCE_DESCRIPTION"
},
{
name
:
"OPENED"
},
{
name
:
"ASSIGNED_BY_ID"
},
{
name
:
"OBSERVER"
},
{
name
:
"COMMENTS"
}
]
},
{
name
:
"products"
,
title
:
"Products"
,
type
:
"section"
,
elements
:
[
{
name
:
"PRODUCT_ROW_SUMMARY"
}
]
}
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
'crm.deal.details.configuration.set'
,
[
'scope'
=>
'P'
,
'userId'
=>
1
,
'data'
=> [
[
'name'
=>
'main'
,
'title'
=>
'About the Deal'
,
'type'
=>
'section'
,
'elements'
=> [
[
'name'
=>
'TITLE'
],
[
'name'
=>
'OPPORTUNITY_WITH_CURRENCY'
],
[
'name'
=>
'STAGE_ID'
],
[
'name'
=>
'BEGINDATE'
],
[
'name'
=>
'CLOSEDATE'
],
[
'name'
=>
'CLIENT'
],
],
],
[
'name'
=>
'additional'
,
'title'
=>
'Additional Information'
,
'type'
=>
'section'
,
'elements'
=> [
[
'name'
=>
'TYPE_ID'
],
[
'name'
=>
'SOURCE_ID'
],
[
'name'
=>
'SOURCE_DESCRIPTION'
],
[
'name'
=>
'OPENED'
],
[
'name'
=>
'ASSIGNED_BY_ID'
],
[
'name'
=>
'OBSERVER'
],
[
'name'
=>
'COMMENTS'
],
],
],
[
'name'
=>
'products'
,
'title'
=>
'Products'
,
'type'
=>
'section'
,
'elements'
=> [
[
'name'
=>
'PRODUCT_ROW_SUMMARY'
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
console.
dir
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
'Error setting deal details configuration: '
.
$e
->
getMessage
();
}
//---
//Setting personal settings for the general direction deal card for the user with identifier 1.
BX24
.
callMethod
(
"crm.deal.details.configuration.set"
,
{
scope
:
"P"
,
userId
:
1
,
data
:
[
{
name
:
"main"
,
title
:
"About the Deal"
,
type
:
"section"
,
elements
:
[
{
name
:
"TITLE"
},
{
name
:
"OPPORTUNITY_WITH_CURRENCY"
},
{
name
:
"STAGE_ID"
},
{
name
:
"BEGINDATE"
},
{
name
:
"CLOSEDATE"
},
{
name
:
"CLIENT"
}
]
},
{
name
:
"additional"
,
title
:
"Additional Information"
,
type
:
"section"
,
elements
:
[
{
name
:
"TYPE_ID"
},
{
name
:
"SOURCE_ID"
},
{
name
:
"SOURCE_DESCRIPTION"
},
{
name
:
"OPENED"
},
{
name
:
"ASSIGNED_BY_ID"
},
{
name
:
"OBSERVER"
},
{
name
:
"COMMENTS"
}
]
},
{
name
:
"products"
,
title
:
"Products"
,
type
:
"section"
,
elements
:
[
{
name
:
"PRODUCT_ROW_SUMMARY"
}
]
}
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
//---
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Reset Card Parameters
Next
Set Common Card for All Users

---

## Set a common card for all users crm.deal.details.configuration.forceCommonScopeForAll

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/custom-form/crm-deal-details-configuration-force-common-scope-for-all

Set a common card for all users crm.deal.details.configuration.forceCommonScopeForAll | Bitrix24 REST API and Marketplace Applications
Set a common card for all users crm.deal.details.configuration.forceCommonScopeForAll
Set a common card for all users crm.deal.details.configuration.forceCommonScopeForAll
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.details.configuration.forceCommonScopeForAll
forcibly sets a common deal card for all users.
Warning
Please note that the settings for deal cards of different directions (or funnels) may differ from each other.
To switch between the settings of deal cards of different directions, the parameter
dealCategoryId
is used.
Parameter
Description
extras
unknown
Additional parameters. Here, the parameter
dealCategoryId
can be specified for deals.
Examples
Examples
JS
PHP
BX24.js
try
{
const
response =
await
$b24.
callMethod
(
"crm.deal.details.configuration.forceCommonScopeForAll"
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
'crm.deal.details.configuration.forceCommonScopeForAll'
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
'Error setting common deal card scope for all users: '
.
$e
->
getMessage
();
}
//---
//Set a common deal card for all users.
BX24
.
callMethod
(
"crm.deal.details.configuration.forceCommonScopeForAll"
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
dir
(result.
data
());
}
);
//---
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Set Individual Card Parameters
Next
Widgets

---

## Widgets

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/widgets

Widgets | Bitrix24 REST API and Marketplace Applications
Widgets
Widgets
Context Menu Item in the CRM_XXX_LIST_MENU, CRM_DYNAMIC_XXX_LIST_MENU
Dropdown Menu Item Above the CRM Entity List CRM_XXX_LIST_TOOLBAR, CRM_DYNAMIC_XXX_LIST_TOOLBAR
Tab in the detail form of the CRM entity CRM_XXX_DETAIL_TAB, CRM_DYNAMIC_XXX_DETAIL_TAB
Button above the timeline of the CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY card
Dropdown Menu Item of the Top Button in the CRM_XXX_DETAIL_TOOLBAR, CRM_DYNAMIC_XXX_DETAIL_TOOLBAR
Context Menu Item for the Deal in the CRM Element Card CRM_XXX_ACTIVITY_TIMELINE_MENU, CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU
Dropdown Menu Item for the Document Generator CRM_XXX_DOCUMENTGENERATOR_BUTTON
Dropdown Menu Item of the Top Button in the CRM Robot Designer CRM_XXX_ROBOT_DESIGNER_TOOLBAR
Menu Item in CRM Sales Funnels Toolbar
CRM Analytics Menu Item CRM_ANALYTICS_MENU
Dropdown Menu Item of the Top Button in CRM Analytics CRM_ANALYTICS_TOOLBAR
Was the article helpful?
Yes
No
Previous
Set Common Card for All Users
Next
Overview of Methods

---

