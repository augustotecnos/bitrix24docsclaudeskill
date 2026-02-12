---
description: 'CRM Leads API: CRUD operations, fields, events, communication'
methods:
- crm.activity.
- crm.deal.details.configuration.
- crm.item.details.configuration.
- crm.item.productrow.
- crm.item.update
- crm.lead.add
- crm.lead.contact.
- crm.lead.contact.add
- crm.lead.contact.delete
- crm.lead.contact.fields
- crm.lead.contact.items.delete
- crm.lead.contact.items.get
- crm.lead.contact.items.set
- crm.lead.delete
- crm.lead.details.configuration.
- crm.lead.details.configuration.forceCommonScopeForAll
- crm.lead.details.configuration.get
- crm.lead.details.configuration.reset
- crm.lead.details.configuration.set
- crm.lead.fields
- crm.lead.get
- crm.lead.list
- crm.lead.productrows.get
- crm.lead.productrows.set
- crm.lead.update
- crm.lead.userfield.
- crm.lead.userfield.add
- crm.lead.userfield.delete
- crm.lead.userfield.get
- crm.lead.userfield.list
pages: 36
title: 'CRM Leads API: CRUD operations, fields, events, communication'
---
# CRM Leads API: CRUD operations, fields, events, communication
> CRM Leads API: CRUD operations, fields, events, communication
> **36 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Leads in CRM: Overview of Methods](#leads-in-crm-overview-of-methods)
- [Create a New Lead crm.lead.add](#create-a-new-lead-crmleadadd)
- [Update Lead crm.lead.update](#update-lead-crmleadupdate)
- [Get lead by Id crm.lead.get](#get-lead-by-id-crmleadget)
- [Get the list of leads crm.lead.list](#get-the-list-of-leads-crmleadlist)
- [Delete lead crm.lead.delete](#delete-lead-crmleaddelete)
- [Get Lead Fields crm.lead.fields](#get-lead-fields-crmleadfields)
- [Add products to lead crm.lead.productrows.set](#add-products-to-lead-crmleadproductrowsset)
- [Get Lead Products crm.lead.productrows.get](#get-lead-products-crmleadproductrowsget)
- [Linking Leads to Contacts: Overview of Methods](#linking-leads-to-contacts-overview-of-methods)
- [Add Contact Binding to Lead crm.lead.contact.add](#add-contact-binding-to-lead-crmleadcontactadd)
- [Remove contact binding from lead crm.lead.contact.delete](#remove-contact-binding-from-lead-crmleadcontactdel)
- [Get a List of Related Contacts crm.lead.contact.items.get](#get-a-list-of-related-contacts-crmleadcontactitems)
- [Attach a list of contacts to a lead crm.lead.contact.items.set](#attach-a-list-of-contacts-to-a-lead-crmleadcontact)
- [Delete Contact List from Lead crm.lead.contact.items.delete](#delete-contact-list-from-lead-crmleadcontactitemsd)
- [Get Lead-Contact Fields crm.lead.contact.fields](#get-lead-contact-fields-crmleadcontactfields)
- [Custom Lead Fields: Overview of Methods](#custom-lead-fields-overview-of-methods)
- [Add Field crm.lead.userfield.add](#add-field-crmleaduserfieldadd)
- [Update Field crm.lead.userfield.update](#update-field-crmleaduserfieldupdate)
- [Get Field by Code crm.lead.userfield.get](#get-field-by-code-crmleaduserfieldget)
- [Get a list of fields crm.lead.userfield.list](#get-a-list-of-fields-crmleaduserfieldlist)
- [Delete Field crm.lead.userfield.delete](#delete-field-crmleaduserfielddelete)
- [Overview of Events When Working with Custom Lead Fields](#overview-of-events-when-working-with-custom-lead-f)
- [When Adding a Custom Field onCrmLeadUserFieldAdd](#when-adding-a-custom-field-oncrmleaduserfieldadd)
- [When updating a custom field onCrmLeadUserFieldUpdate](#when-updating-a-custom-field-oncrmleaduserfieldupd)
- [When Deleting a Custom Field onCrmLeadUserFieldDelete](#when-deleting-a-custom-field-oncrmleaduserfielddel)
- [When setting list values for the custom field onCrmLeadUserFieldSetEnumValues](#when-setting-list-values-for-the-custom-field-oncr)
- [Overview of Events When Working with Leads](#overview-of-events-when-working-with-leads)
- [Event onCrmLeadAdd](#event-oncrmleadadd)
- [Event onCrmLeadUpdate](#event-oncrmleadupdate)
- [Event onLeadDelete](#event-onleaddelete)
- [Managing Lead Cards: Overview of Methods](#managing-lead-cards-overview-of-methods)
- [Get parameters of crm.lead.details.configuration.get](#get-parameters-of-crmleaddetailsconfigurationget)
- [Reset Lead Card Settings crm.lead.details.configuration.reset](#reset-lead-card-settings-crmleaddetailsconfigurati)
- [Set Parameters for crm.lead.details.configuration.set](#set-parameters-for-crmleaddetailsconfigurationset)
- [Set a common lead card for all users crm.lead.details.configuration.forceCommonScopeForAll](#set-a-common-lead-card-for-all-users-crmleaddetail)

---

## Leads in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/index

Leads in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Leads in CRM: Overview of Methods
Leads in CRM: Overview of Methods
Connection of Leads with Other CRM Objects
Lead Card
Widgets
Features
Overview of Methods and Events
Main
Connection Between Leads and Contacts
Custom Fields
Managing Lead Cards
A lead is the starting point of the Sales Funnel. Its card contains information about the client's interest in a product or service: filled CRM forms, e-mails, calls, and chats with the client.
The main goal of working with leads is to determine their potential and convert them into deals for further selling of the product or service.
Quick navigation:
all methods and events
User documentation:
leads in Bitrix24
Connection of Leads with Other CRM Objects
Connection of Leads with Other CRM Objects
Products.
Adding, modifying, and deleting product items in deals is possible through the group of methods
crm.item.productrow.*
.
Deal.
The connection appears after converting the lead into a successful one.
Client.
A field in the lead card consisting of the associated company and contacts. The field is available in the repeat lead form. If repeat leads are disabled, the linking field appears after creating a company or contact based on the lead. There is one company in the lead, and access to it is made directly through the field
COMPANY_ID
. Multiple contacts can be specified, and interaction with them is conducted through a separate group of methods
crm.lead.contact.*
.
User Documentation
How to add products to deals, leads, and estimates
How to convert a lead
Repeat leads and deals
Deals in CRM: Overview of Methods
Lead Card
Lead Card
The main workspace in a lead is the General tab of its card. It consists of two parts:
The left part contains fields with information. If the system fields are insufficient, you can create your own custom fields. They allow storing information in various data formats: string, number, link, address, and others. To create, modify, retrieve, or delete custom lead fields, the group of methods
crm.lead.userfield.*
is used.
The right part contains the deal timeline. In it, you can create, edit, filter, and delete CRM activities — the group of methods
crm.activity.*
, and timeline records — the group of methods
crm.timeline.*
.
The parameters of the deal card can be managed depending on the funnel through the group of methods
crm.lead.details.configuration.*
.
User Documentation
CRM Card: Features and Settings
System Fields in CRM
Custom Fields in CRM
Timeline in CRM Entity
Widgets
Widgets
An application can be embedded into the lead card. Thanks to embedding, you can use the application without leaving the lead card.
There are two embedding scenarios:
Use special
embedding locations
. For example, by creating your own tab.
Create a
custom field
, into which the content of your application will be loaded.
Typical Use-Cases and Scenarios
Widget Embedding Mechanism
Embed a Widget in the CRM Card
Features
Features
Leads in CRM may be absent — this happens if the simple mode of CRM operation is activated.
It is impossible to convert a lead using the REST API. You can only change the stage to successful without creating new objects.
User Documentation
CRM Operating Modes
How to Convert a Lead
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
crm.lead.add
Creates a new lead
crm.lead.update
Modifies a lead
crm.lead.get
Returns a lead by ID
crm.lead.list
Returns a list of leads by filter
crm.lead.delete
Deletes a lead and all associated objects
crm.lead.fields
Returns the description of lead fields
crm.lead.productrows.set
Adds products to a lead
crm.lead.productrows.get
Returns the products of a lead
Event
Triggered
onCrmLeadAdd
When a lead is added
onCrmLeadUpdate
When a lead is modified
onCrmLeadDelete
When a lead is deleted
Connection Between Leads and Contacts
Connection Between Leads and Contacts
Method
Description
crm.lead.contact.add
Adds a contact binding to the specified lead
crm.lead.contact.delete
Removes a contact binding from the specified lead
crm.lead.contact.items.get
Retrieves a list of contacts associated with the lead
crm.lead.contact.items.set
Attaches a list of contacts to the specified lead
crm.lead.contact.items.delete
Removes the list of contacts from the lead
crm.lead.contact.fields
Retrieves the description of fields for lead-contact connection, used by methods of the
crm.lead.contact.*
family
Custom Fields
Custom Fields
Methods
Events
Method
Description
crm.lead.userfield.add
Creates a new field
crm.lead.userfield.update
Modifies a field
crm.lead.userfield.get
Returns a field by code
crm.lead.userfield.list
Returns a list of fields
crm.lead.userfield.delete
Deletes a field
Event
Triggered
onCrmLeadUserFieldAdd
When a custom field is added
onCrmLeadUserFieldUpdate
When a custom field is modified
onCrmLeadUserFieldDelete
When a custom field is deleted
onCrmLeadUserFieldSetEnumValues
When the set of values for a custom list-type field is modified
Managing Lead Cards
Managing Lead Cards
Method
Description
crm.lead.details.configuration.get
Retrieves the settings parameters for lead cards
crm.lead.details.configuration.reset
Resets the settings for lead cards
crm.lead.details.configuration.set
Sets the settings for lead cards
crm.lead.details.configuration.forceCommonScopeForAll
Forces a common lead card for all users
Copied
Was the article helpful?
Yes
No
Previous
Widgets
Next
Create New Lead

---

## Create a New Lead crm.lead.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/crm-lead-add

Create a New Lead crm.lead.add | Bitrix24 REST API and Marketplace Applications
Create a New Lead crm.lead.add
Create a New Lead crm.lead.add
Method Parameters
Parameter fields
Parameter params
Code Examples
Response Handling
Returned Data
Error Handling
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with permission to create leads
The method
crm.lead.add
creates a new lead.
Method Parameters
Method Parameters
Required parameters are marked with *
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
Optional array of options (
"optionName"=>"value"[, ...]
). The list of possible fields is described
below
Parameter fields
Parameter fields
Name
type
Description
ADDRESS
string
Address
ADDRESS_2
string
Second line of the address. In some countries, it is customary to split the address into 2 parts
ADDRESS_CITY
string
City
ADDRESS_COUNTRY
string
Country
ADDRESS_COUNTRY_CODE
string
Country code
ADDRESS_POSTAL_CODE
string
Postal code
ADDRESS_PROVINCE
string
State
ADDRESS_REGION
string
Region
ASSIGNED_BY_ID
user
Responsible person
BIRTHDATE
date
Date of birth
COMMENTS
string
Comments
COMPANY_ID
crm_company
Link the lead to a company
COMPANY_TITLE
string
Company name specified in the corresponding lead field. To link an existing company, pass its id in the COMPANY_ID field
CONTACT_ID
crm_contact
Link the lead to a contact
CONTACT_IDS
crm_contact
List of contacts linked to the lead.
Contacts can be added or removed using the group of methods
crm.lead.contact.*
CURRENCY_ID
crm_currency
Currency identifier
EMAIL
crm_multifield
Email address. Multiple
HONORIFIC
crm_status
Salutation
IM
crm_multifield
Messenger. Multiple
LINK
crm_multifield
User ID linked through an open channel. Multiple
LAST_NAME
string
Last name
NAME
string
First name
SECOND_NAME
string
Middle name
OPENED
char
Indicator of lead availability to everyone. Acceptable values are
Y
or
N
.
OPPORTUNITY
double
Amount
IS_MANUAL_OPPORTUNITY
char
Indicator of manual calculation mode for the amount. Acceptable values are Y or N
ORIGINATOR_ID
string
Identifier of the data source.
Used only for linking to an external source
ORIGIN_ID
string
Identifier of the item in the data source. Used only for linking to an external source
PHONE
crm_multifield
Phone. Multiple
POST
string
Position
SOURCE_DESCRIPTION
string
Description of the source
SOURCE_ID
crm_status
Identifier of the source.
Default values:
SOURCE_ID
Name
CALL
Call
EMAIL
E-mail
WEB
Website
ADVERTISING
Advertising
PARTNER
Existing client
RECOMMENDATION
By recommendation
TRADE_SHOW
Trade show
WEBFORM
CRM form
CALLBACK
Callback
RC_GENERATOR
Sales generator
STORE
Online store
OTHER
Other
The list of all possible identifiers from the directory can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=SOURCE
STATUS_DESCRIPTION
string
Additional information about the stage
STATUS_ID
crm_status
Identifier of the lead stage. Default stages:
STATUS_ID
Name
NEW
Unprocessed
IN_PROCESS
In progress
PROCESSED
Processed
JUNK
Low-quality lead
CONVERTED
Quality lead
The list of all possible stages from the directory can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=STATUS
TITLE
string
Lead title
UTM_CAMPAIGN
string
Advertising campaign designation
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
UTM_MEDIUM
string
Type of traffic. CPC (ads), CPM (banners)
UTM_SOURCE
string
Advertising system. Google AdWords, and others
UTM_TERM
string
Search condition of the campaign. For example, keywords for contextual advertising
WEB
crm_multifield
Website. Multiple
UF_...
Custom fields. For example,
UF_CRM_25534736
.
Depending on the portal settings, leads may have a set of custom fields of defined types.
To create, modify, or delete custom fields in leads, use the methods
crm.lead.userfield.*
Note
Additionally, to find out the required format of fields, you can execute the method
crm.lead.fields
and check the format of the incoming values of these fields.
Note
When adding a lead, you cannot explicitly set the indicator for a repeat lead (the
IS_RETURN_CUSTOMER
field), however, this field automatically takes the value Y if you specify a value for
COMPANY_ID
or
CONTACT_ID
when adding the lead.
Parameter params
Parameter params
Name
type
Description
REGISTER_SONET_EVENT
boolean
Flag
Y
/
N
- register the event of adding a lead. Additionally, a notification will be sent to the person responsible for the lead
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
'{"fields":{"TITLE":"IP Titov","NAME":"Gleb","SECOND_NAME":"Egorovich","LAST_NAME":"Titov","STATUS_ID":"NEW","OPENED":"Y","ASSIGNED_BY_ID":1,"CURRENCY_ID":"USD","OPPORTUNITY":12500,"PHONE":[{"VALUE":"555888","VALUE_TYPE":"WORK"}],"WEB":[{"VALUE":"www.mysite.com","VALUE_TYPE":"WORK"}]},"params":{"REGISTER_SONET_EVENT":"Y"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"TITLE":"IP Titov","NAME":"Gleb","SECOND_NAME":"Egorovich","LAST_NAME":"Titov","STATUS_ID":"NEW","OPENED":"Y","ASSIGNED_BY_ID":1,"CURRENCY_ID":"USD","OPPORTUNITY":12500,"PHONE":[{"VALUE":"555888","VALUE_TYPE":"WORK"}],"WEB":[{"VALUE":"www.mysite.com","VALUE_TYPE":"WORK"}]},"params":{"REGISTER_SONET_EVENT":"Y"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.lead.add'
,
{
fields
:
{
TITLE
:
'IP Titov'
,
NAME
:
'Gleb'
,
SECOND_NAME
:
'Egorovich'
,
LAST_NAME
:
'Titov'
,
STATUS_ID
:
'NEW'
,
OPENED
:
'Y'
,
ASSIGNED_BY_ID
:
1
,
CURRENCY_ID
:
'USD'
,
OPPORTUNITY
:
12500
,
PHONE
: [
{
VALUE
:
'555888'
,
VALUE_TYPE
:
'WORK'
,
},
],
WEB
: [
{
VALUE
:
'www.mysite.com'
,
VALUE_TYPE
:
'WORK'
,
}
],
},
params
: {
REGISTER_SONET_EVENT
:
'Y'
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
info
(
`Lead created with ID
${result}
`
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.lead.add'
,
[
'fields'
=> [
'TITLE'
=>
'IP Titov'
,
'NAME'
=>
'Gleb'
,
'SECOND_NAME'
=>
'Egorovich'
,
'LAST_NAME'
=>
'Titov'
,
'STATUS_ID'
=>
'NEW'
,
'OPENED'
=>
'Y'
,
'ASSIGNED_BY_ID'
=>
1
,
'CURRENCY_ID'
=>
'USD'
,
'OPPORTUNITY'
=>
12500
,
'PHONE'
=> [
[
'VALUE'
=>
'555888'
,
'VALUE_TYPE'
=>
'WORK'
,
},
],
'WEB'
=> [
[
'VALUE'
=>
'www.mysite.com'
,
'VALUE_TYPE'
=>
'WORK'
,
},
],
],
'params'
=> [
'REGISTER_SONET_EVENT'
=>
'Y'
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
echo
'Lead created with ID '
.
$result
;
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
'Error creating lead: '
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
"crm.lead.add"
,
{
fields
:
{
TITLE
:
"IP Titov"
,
NAME
:
"Gleb"
,
SECOND_NAME
:
"Egorovich"
,
LAST_NAME
:
"Titov"
,
STATUS_ID
:
"NEW"
,
OPENED
:
"Y"
,
ASSIGNED_BY_ID
:
1
,
CURRENCY_ID
:
"USD"
,
OPPORTUNITY
:
12500
,
PHONE
: [
{
VALUE
:
"555888"
,
VALUE_TYPE
:
"WORK"
,
},
] ,
WEB
: [
{
VALUE
:
"www.mysite.com"
,
VALUE_TYPE
:
"WORK"
,
}
],
},
params
: {
REGISTER_SONET_EVENT
:
"Y"
,
}
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
return
;
}
console
.
info
(
`Lead created with ID
${result.data()}
`
);
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
'crm.lead.add'
,
[
'fields'
=> [
'TITLE'
=>
'IP Titov'
,
'NAME'
=>
'Gleb'
,
'SECOND_NAME'
=>
'Egorovich'
,
'LAST_NAME'
=>
'Titov'
,
'STATUS_ID'
=>
'NEW'
,
'OPENED'
=>
'Y'
,
'ASSIGNED_BY_ID'
=>
1
,
'CURRENCY_ID'
=>
'USD'
,
'OPPORTUNITY'
=>
12500
,
'PHONE'
=> [
[
'VALUE'
=>
'555888'
,
'VALUE_TYPE'
=>
'WORK'
,
},
],
'WEB'
=> [
[
'VALUE'
=>
'www.mysite.com'
,
'VALUE_TYPE'
=>
'WORK'
,
},
],
],
'params'
=> [
'REGISTER_SONET_EVENT'
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
Response Handling
Response Handling
HTTP status:
200
{
"result"
:
3465
,
"time"
:
{
"start"
:
1705764932.998683
,
"finish"
:
1705764937.173995
,
"duration"
:
4.1753120422363281
,
"processing"
:
3.3076529502868652
,
"date_start"
:
"2024-01-20T18:35:32+01:00"
,
"date_finish"
:
"2024-01-20T18:35:37+01:00"
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
Returned Data
Returned Data
Name
type
Description
result
integer
Root element of the response, contains the identifier of the created lead
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status: 40x, 50x Error
{
"error"
:
""
,
"error_description"
:
"Access denied."
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
Possible Errors
Possible Errors
Code
Error Text
Description
Empty value
Access denied.
The user does not have permission to add a lead
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
Delete lead crm.lead.delete
Get Lead Fields crm.lead.fields
Add Lead via Web Form
Add a lead with files via a web form
Add Repeat Lead
Add an activity to a new lead or deal depending on the CRM mode
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Lead

---

## Update Lead crm.lead.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/crm-lead-update

Update Lead crm.lead.update | Bitrix24 REST API and Marketplace Applications
Update Lead crm.lead.update
Update Lead crm.lead.update
Method Parameters
Parameter fields
Parameter params
Code Examples
Response Handling
Returned Data
Error Handling
Possible Errors
Statuses and System Error Codes
Scope:
crm
Who can execute the method: a user with permissions to edit CRM leads
The method
crm.lead.update
updates an existing lead.
Method Parameters
Method Parameters
Warning
It is highly recommended to pass the complete set of address fields when updating an address. The specifics of updating address fields are described
here
.
Required parameters are marked with *
Name
type
Description
id
*
integer
Lead identifier.
The identifier can be obtained using the methods
crm.lead.list
or
crm.lead.add
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
Only those fields that need to be changed should be passed in
fields
params
object
Optional set of options. (
"paramName"=>"value"[, ...]
). The list of possible fields is described
below
Parameter fields
Parameter fields
Name
type
Description
ADDRESS
string
Lead address
ADDRESS_2
string
Second line of the address. In some countries, it is customary to split the address into 2 parts
ADDRESS_CITY
string
City
ADDRESS_COUNTRY
string
Country
ADDRESS_COUNTRY_CODE
string
Country code
ADDRESS_POSTAL_CODE
string
Postal code
ADDRESS_PROVINCE
string
State
ADDRESS_REGION
string
Region
ASSIGNED_BY_ID
user
Responsible person
BIRTHDATE
date
Date of birth
COMMENTS
string
Comments
COMPANY_ID
crm_company
Link the lead to a company
COMPANY_TITLE
string
Company name specified in the corresponding lead field. To link an existing company, pass its id in the COMPANY_ID field
CONTACT_ID
crm_contact
Link the lead to a contact
CONTACT_IDS
crm_contact
List of contacts linked to the lead.
Contacts can be added or removed using the group of methods
crm.lead.contact.*
CURRENCY_ID
crm_currency
Currency identifier
EMAIL
crm_multifield
E-mail address. Multiple
HONORIFIC
crm_status
Salutation
IM
crm_multifield
Messenger. Multiple
LINK
crm_multifield
User ID linked through an open channel. Multiple
LAST_NAME
string
Last name
NAME
string
First name
SECOND_NAME
string
Middle name
OPENED
char
Indicator of lead availability for everyone. Acceptable values Y or N
OPPORTUNITY
double
Amount
IS_MANUAL_OPPORTUNITY
char
Indicator of manual calculation mode for the amount. Acceptable values Y or N
ORIGINATOR_ID
string
Identifier of the data source. Used only for linking to an external source
ORIGIN_ID
string
Identifier of the item in the data source. Used only for linking to an external source
PHONE
crm_multifield
Phone. Multiple
POST
string
Position
SOURCE_DESCRIPTION
string
Source description
SOURCE_ID
crm_status
Source identifier.
Default values:
SOURCE_ID
Name
CALL
Call
EMAIL
E-mail
WEB
Website
ADVERTISING
Advertising
PARTNER
Existing client
RECOMMENDATION
By recommendation
TRADE_SHOW
Trade show
WEBFORM
CRM form
CALLBACK
Callback
RC_GENERATOR
Sales generator
STORE
Online store
OTHER
Other
The list of all possible identifiers from the directory can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=SOURCE
STATUS_DESCRIPTION
string
Additional information about the stage
STATUS_ID
crm_status
Identifier of the lead stage. Default stages:
STATUS_ID
Name
NEW
New
IN_PROCESS
In process
PROCESSED
Processed
JUNK
Junk lead
CONVERTED
Converted lead
The list of all possible stages from the directory can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=STATUS
TITLE
string
Lead title
UTM_CAMPAIGN
string
Advertising campaign designation
UTM_CONTENT
string
Campaign content. For example, for contextual ads
UTM_MEDIUM
string
Type of traffic. CPC (ads), CPM (banners)
UTM_SOURCE
string
Advertising system. Google Ads, Facebook Ads, and others
UTM_TERM
string
Search term for the campaign. For example, keywords for contextual advertising
WEB
crm_multifield
Website. Multiple
UF_...
Custom fields. For example,
UF_CRM_25534736
.
Depending on the account settings, leads may have a set of custom fields of specific types.
To change file fields, it is recommended to use the method
crm.item.update
.
To create, modify, or delete custom fields in leads, use the methods
crm.lead.userfield.*
Note
Additionally, to find out the required format of fields, you can execute the method
crm.lead.fields
and check the format of the incoming values of these fields.
Note
When changing a lead, you cannot explicitly set the indicator for a repeat lead (the
IS_RETURN_CUSTOMER
field), however, this field automatically takes the value Y if you specify a value for
COMPANY_ID
or
CONTACT_ID
when changing the lead.
Parameter params
Parameter params
Name
type
Description
REGISTER_SONET_EVENT
char
Register an event for adding the lead in the activity stream. Additionally, a notification will be sent to the person responsible for the lead. Acceptable values
Y
or
N
Required parameters are marked with *
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
'{"id":1608,"fields":{"TITLE":"LLC Titov","NAME":"Gleb","SECOND_NAME":"Egorovich","LAST_NAME":"Titov","STATUS_ID":"NEW","OPENED":"Y","ASSIGNED_BY_ID":1,"CURRENCY_ID":"USD","OPPORTUNITY":12500,"PHONE":[{"VALUE":"555888","VALUE_TYPE":"WORK"}],"WEB":[{"VALUE":"www.mysite.com","VALUE_TYPE":"WORK"}]},"params":{"REGISTER_SONET_EVENT":"Y"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":1608,"fields":{"TITLE":"LLC Titov","NAME":"Gleb","SECOND_NAME":"Egorovich","LAST_NAME":"Titov","STATUS_ID":"NEW","OPENED":"Y","ASSIGNED_BY_ID":1,"CURRENCY_ID":"USD","OPPORTUNITY":12500,"PHONE":[{"VALUE":"555888","VALUE_TYPE":"WORK"}],"WEB":[{"VALUE":"www.mysite.com","VALUE_TYPE":"WORK"}]},"params":{"REGISTER_SONET_EVENT":"Y"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.lead.update"
,
{
id
:
1608
,
fields
:
{
TITLE
:
"LLC Titov"
,
NAME
:
"Gleb"
,
SECOND_NAME
:
"Egorovich"
,
LAST_NAME
:
"Titov"
,
STATUS_ID
:
"NEW"
,
OPENED
:
"Y"
,
ASSIGNED_BY_ID
:
1
,
CURRENCY_ID
:
"USD"
,
OPPORTUNITY
:
12500
,
PHONE
: [
{
VALUE
:
"555888"
,
VALUE_TYPE
:
"WORK"
,
},
],
WEB
: [
{
VALUE
:
"www.mysite.com"
,
VALUE_TYPE
:
"WORK"
,
}
],
},
params
: {
REGISTER_SONET_EVENT
:
"Y"
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
info
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
$id
=
123
;
// Example lead ID
$fields
= [
'TITLE'
=>
'Updated Lead Title'
,
'NAME'
=>
'John'
,
'LAST_NAME'
=>
'Doe'
,
'BIRTHDATE'
=> (
new
DateTime
(
'1980-01-01'
))->
format
(
DateTime
::
ATOM
),
'COMPANY_TITLE'
=>
'Example Company'
,
'STATUS_ID'
=>
'NEW'
,
'COMMENTS'
=>
'Updated comments for the lead.'
,
'PHONE'
=>
'1234567890'
,
'EMAIL'
=>
'john.doe@example.com'
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
()->
lead
()->
update
(
$id
,
$fields
,
$params
);
if
(
$result
->
isSuccess
()) {
print
(
$result
->
getCoreResponse
()->
getResponseData
()->
getResult
()[
0
]);
}
else
{
print
(
"Update failed."
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
"crm.lead.update"
,
{
id
:
1608
,
fields
:
{
TITLE
:
"LLC Titov"
,
NAME
:
"Gleb"
,
SECOND_NAME
:
"Egorovich"
,
LAST_NAME
:
"Titov"
,
STATUS_ID
:
"NEW"
,
OPENED
:
"Y"
,
ASSIGNED_BY_ID
:
1
,
CURRENCY_ID
:
"USD"
,
OPPORTUNITY
:
12500
,
PHONE
: [
{
VALUE
:
"555888"
,
VALUE_TYPE
:
"WORK"
,
},
],
WEB
: [
{
VALUE
:
"www.mysite.com"
,
VALUE_TYPE
:
"WORK"
,
}
],
},
params
: {
REGISTER_SONET_EVENT
:
"Y"
,
}
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
return
;
}
console
.
info
(result.
data
());
}
);
$fields
= [
'TITLE'
=>
$sTitle
,
'COMPANY_ID'
=>
123
,
'PHONE'
=> [
[
'VALUE'
=>
'555888'
,
'VALUE_TYPE'
=>
'WORK'
,
],
],
];
$result
=
CRest
::
call
(
'crm.lead.update'
,
[
'id'
=>
1608
,
'fields'
=>
$fields
,
],
[
'REGISTER_SONET_EVENT'
=>
'Y'
,
]
);
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
1705764932.998683
,
"finish"
:
1705764937.173995
,
"duration"
:
4.1753120422363281
,
"processing"
:
3.3076529502868652
,
"date_start"
:
"2024-01-20T18:35:32+01:00"
,
"date_finish"
:
"2024-01-20T18:35:37+01:00"
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
HTTP status: 40x, 50x Error
{
"error"
:
""
,
"error_description"
:
"ID is not defined or invalid."
}
Possible Errors
Possible Errors
Error Text
Description
ID is not defined or invalid
The parameter
id
is not a positive integer
Not found
The lead with the provided
id
does not exist
Access denied
The user does not have permission to edit the lead
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
Create New Lead
Next
Get Lead by Id

---

## Get lead by Id crm.lead.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/crm-lead-get

Get lead by Id crm.lead.get | Bitrix24 REST API and Marketplace Applications
Get lead by Id crm.lead.get
Get lead by Id crm.lead.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: a user with read access permission for the requested lead
The method
crm.lead.get
returns a lead by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Lead identifier.
The identifier can be obtained using the methods
crm.lead.list
or
crm.lead.add
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
'{"ID":123}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":123,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.lead.get'
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
'crm.lead.get'
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
return
;
}
echo
'Lead data: '
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
'Error getting lead data: '
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
'crm.lead.get'
,
{
id
:
123
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
return
;
}
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
'crm.lead.get'
,
[
'ID'
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
"123"
,
"TITLE"
:
"Lead #1591"
,
"HONORIFIC"
:
null
,
"NAME"
:
""
,
"SECOND_NAME"
:
null
,
"LAST_NAME"
:
null
,
"COMPANY_TITLE"
:
null
,
"COMPANY_ID"
:
null
,
"CONTACT_ID"
:
null
,
"IS_RETURN_CUSTOMER"
:
"N"
,
"BIRTHDATE"
:
""
,
"SOURCE_ID"
:
"1"
,
"SOURCE_DESCRIPTION"
:
null
,
"STATUS_ID"
:
"IN_PROCESS"
,
"STATUS_DESCRIPTION"
:
null
,
"POST"
:
null
,
"COMMENTS"
:
null
,
"CURRENCY_ID"
:
"USD"
,
"OPPORTUNITY"
:
"0.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"N"
,
"HAS_PHONE"
:
"N"
,
"HAS_EMAIL"
:
"N"
,
"HAS_IMOL"
:
"N"
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
"2024-05-23T18:18:25+02:00"
,
"DATE_MODIFY"
:
"2024-05-23T18:18:25+02:00"
,
"DATE_CLOSED"
:
""
,
"STATUS_SEMANTIC_ID"
:
"P"
,
"OPENED"
:
"Y"
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
"2024-05-23T18:18:25+02:00"
,
"ADDRESS"
:
null
,
"ADDRESS_2"
:
null
,
"ADDRESS_CITY"
:
null
,
"ADDRESS_POSTAL_CODE"
:
null
,
"ADDRESS_REGION"
:
null
,
"ADDRESS_PROVINCE"
:
null
,
"ADDRESS_COUNTRY"
:
null
,
"ADDRESS_COUNTRY_CODE"
:
null
,
"ADDRESS_LOC_ADDR_ID"
:
null
,
"UTM_SOURCE"
:
null
,
"UTM_MEDIUM"
:
null
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
"LAST_ACTIVITY_BY"
:
"1"
,
"LAST_ACTIVITY_TIME"
:
"2024-05-23T18:18:25+02:00"
,
"PHONE"
:
[
{
"ID"
:
"11658"
,
"VALUE_TYPE"
:
"OTHER"
,
"VALUE"
:
"+15454777777"
,
"TYPE_ID"
:
"PHONE"
}
]
,
"IM"
:
[
{
"ID"
:
"11660"
,
"VALUE_TYPE"
:
"OPENLINE"
,
"VALUE"
:
"imol|livechat|1|67|21"
,
"TYPE_ID"
:
"IM"
}
]
}
,
"time"
:
{
"start"
:
1705764932.998683
,
"finish"
:
1705764937.173995
,
"duration"
:
4.1753120422363281
,
"processing"
:
3.3076529502868652
,
"date_start"
:
"2024-01-20T18:35:32+02:00"
,
"date_finish"
:
"2024-01-20T18:35:37+02:00"
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
Returned Data
Returned Data
Name
type
Description
result
lead
Root element of the response. Contains information about the lead fields. The structure is described
below
time
time
Information about the request execution time
Type lead
Type lead
Name
type
Description
ID
integer
Integer identifier of the lead
TITLE
string
Title of the lead
HONORIFIC
crm_status
Type of address. Status from the directory. A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=HONORIFIC
NAME
string
Contact's first name
SECOND_NAME
string
Contact's middle name
LAST_NAME
string
Contact's last name
COMPANY_ID
crm_company
Link of the lead to the company
COMPANY_TITLE
string
Company name
CONTACT_ID
crm_contact
Link of the lead to the contact
IS_RETURN_CUSTOMER
char
Indicator of a returning lead. Allowed values Y or N
BIRTHDATE
date
Date of birth
SOURCE_ID
crm_status
Identifier of the source. Status from the directory. A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=SOURCE
SOURCE_DESCRIPTION
string
Description of the source
STATUS_ID
crm_status
Identifier of the lead stage. Status from the directory. A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=STATUS
STATUS_DESCRIPTION
string
Additional information about the stage
POST
string
Position
COMMENTS
string
Comments
CURRENCY_ID
crm_currency
Currency identifier
OPPORTUNITY
double
Estimated amount
IS_MANUAL_OPPORTUNITY
char
Indicator of manual calculation of the amount. Allowed values Y or N
HAS_PHONE
char
Indicator of phone field completion. Allowed values Y or N
HAS_EMAIL
char
Indicator of email field completion. Allowed values Y or N
HAS_IMOL
char
Indicator of the presence of an attached open line. Allowed values Y or N
ASSIGNED_BY_ID
user
Identifier of the user responsible for the lead
CREATED_BY_ID
user
Identifier of the user who created the lead
MODIFY_BY_ID
user
Identifier of the user who last modified the lead
MOVED_BY_ID
user
Identifier of the user who moved the item to the current stage
DATE_CREATE
datetime
Creation date
DATE_MODIFY
datetime
Modification date
DATE_CLOSED
datetime
Closing date
STATUS_SEMANTIC_ID
string
F (failed) – processed unsuccessfully
S (success) – processed successfully
P (processing) – lead is being processed
OPENED
char
Indicator of the lead's availability to everyone. Allowed values Y or N
ORIGINATOR_ID
string
Identifier of the data source. Used only for linking to an external source
ORIGIN_ID
string
Identifier of the item in the data source. Used only for linking to an external source
MOVED_TIME
datetime
Date of moving the item to the current stage
ADDRESS
string
Contact's address
ADDRESS_2
string
Second line of the address. In some countries, it is customary to split the address into 2 parts
ADDRESS_CITY
string
City
ADDRESS_POSTAL_CODE
string
Postal code
ADDRESS_REGION
string
Region
ADDRESS_PROVINCE
string
Province
ADDRESS_COUNTRY
string
Country
ADDRESS_COUNTRY_CODE
string
Country code
ADDRESS_LOC_ADDR_ID
string
Used for service purposes
UTM_SOURCE
string
Advertising system. Google Ads, Facebook Ads, and others
UTM_MEDIUM
string
Type of traffic. CPC (ads), CPM (banners)
UTM_CAMPAIGN
string
Designation of the advertising campaign
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
UTM_TERM
string
Search term of the campaign. For example, keywords for contextual advertising
LAST_ACTIVITY_BY
string
Identifier of the user responsible for the last activity in this lead (e.g., who created a new activity in the lead)
LAST_ACTIVITY_TIME
datetime
Time of the last activity
UF_...
Custom fields. For example,
UF_CRM_25534736
.
Depending on the account settings, leads may have a set of custom fields of specific types.
To create, modify, or delete custom fields in leads, use the methods
crm.lead.userfield.*
PHONE
crm_multifield
Array of phone numbers
IM
crm_multifield
Array of messengers
Error Handling
Error Handling
40x, 50x Error
{
"error"
:
""
,
"error_description"
:
"Not found"
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
Possible Errors
Possible Errors
Error Text
Description
ID is not defined or invalid
The
id
parameter is either not provided or is not a positive integer
Not found
A lead with the specified
id
was not found
Access denied
The user does not have permission to read the lead
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
Add an activity to a new lead or deal depending on the CRM mode
Copied
Was the article helpful?
Yes
No
Previous
Update Lead
Next
Get List of Leads

---

## Get the list of leads crm.lead.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/crm-lead-list

Get the list of leads crm.lead.list | Bitrix24 REST API and Marketplace Applications
Get the list of leads crm.lead.list
Get the list of leads crm.lead.list
Method Parameters
Code Examples
Some Practical Examples
Response Handling
Returned Data
Error Handling
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: user with read access permission for leads
The method
crm.lead.list
returns a list of leads based on the filter. It is an implementation of the list method for leads.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
select
array
The array contains a list of fields to select (see lead fields
crm-lead-fields
).
When selecting, use masks:
"*" - to select all fields (excluding custom and multiple fields)
"UF_*" - to select all custom fields (excluding multiple fields)
There are no masks for selecting multiple fields. To select multiple fields, specify the required ones in the selection list ("PHONE", "EMAIL", etc.).
There is no option to add a logical OR condition to the filter if you need to select by several different fields.
filter
object
An object for filtering the selected leads in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
correspond to lead fields
crm-lead-fields
.
The key can have an additional prefix that clarifies the behavior of the filter. Possible prefix values:
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
— LIKE, substring search. The "%" symbol in the filter value does not need to be passed. The search looks for the substring in any position of the string.
=%
— LIKE, substring search. The "%" symbol needs to be passed in the value. Examples:
"mol%" — searching for values starting with "mol"
"%mol" — searching for values ending with "mol"
"%mol%" — searching for values where "mol" can be in any position
%=
— LIKE (see description above)
!%
— NOT LIKE, substring search. The "%" symbol in the filter value does not need to be passed. The search goes from both sides.
=%
— NOT LIKE, substring search. The "%" symbol needs to be passed in the value. Examples:
"mol%" — searching for values not starting with "mol"
"%mol" — searching for values not ending with "mol"
"%mol%" — searching for values where the substring "mol" is not in any position
!%=
— NOT LIKE (see description above)
=
— equals, exact match (used by default)
!=
- not equal
!
— not equal
order
Possible values for
order
:
asc
— in ascending order
desc
— in descending order
start
integer
This parameter is used to control pagination.
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
— the number of the desired page
Also, see the description of
list methods
.
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
'{"select":["*","UF_*"],"start":50,"filter":{"=OPPORTUNITY":15000},"order":{"STATUS_ID":"ASC"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"select":["*","UF_*"],"start":50,"filter":{"=OPPORTUNITY":15000},"order":{"STATUS_ID":"ASC"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.lead.list'
,
{
select
: [
'*'
,
'UF_*'
],
filter
: {
'=OPPORTUNITY'
:
15000
,
},
order
: {
STATUS_ID
:
'ASC'
,
},
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
'crm.lead.list'
, {
select
: [
'*'
,
'UF_*'
],
filter
: {
'=OPPORTUNITY'
:
15000
,
},
order
: {
STATUS_ID
:
'ASC'
,
},
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.lead.list'
, {
select
: [
'*'
,
'UF_*'
],
filter
: {
'=OPPORTUNITY'
:
15000
,
},
order
: {
STATUS_ID
:
'ASC'
,
},
},
50
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
$order
= [];
$filter
= [];
// Define your filter criteria here
$select
= [
'ID'
,
'TITLE'
,
'HONORIFIC'
,
'NAME'
,
'SECOND_NAME'
,
'LAST_NAME'
,
'BIRTHDATE'
,
'COMPANY_TITLE'
,
'SOURCE_ID'
,
'SOURCE_DESCRIPTION'
,
'STATUS_ID'
,
'STATUS_DESCRIPTION'
,
'STATUS_SEMANTIC_ID'
,
'POST'
,
'ADDRESS'
,
'ADDRESS_2'
,
'ADDRESS_CITY'
,
'ADDRESS_POSTAL_CODE'
,
'ADDRESS_REGION'
,
'ADDRESS_PROVINCE'
,
'ADDRESS_COUNTRY'
,
'ADDRESS_COUNTRY_CODE'
,
'ADDRESS_LOC_ADDR_ID'
,
'CURRENCY_ID'
,
'OPPORTUNITY'
,
'IS_MANUAL_OPPORTUNITY'
,
'OPENED'
,
'COMMENTS'
,
'HAS_PHONE'
,
'HAS_EMAIL'
,
'HAS_IMOL'
,
'ASSIGNED_BY_ID'
,
'CREATED_BY_ID'
,
'MODIFY_BY_ID'
,
'MOVED_BY_ID'
,
'DATE_CREATE'
,
'DATE_MODIFY'
,
'MOVED_TIME'
,
'COMPANY_ID'
,
'CONTACT_ID'
,
'CONTACT_IDS'
,
'IS_RETURN_CUSTOMER'
,
'DATE_CLOSED'
,
'ORIGINATOR_ID'
,
'ORIGIN_ID'
,
'UTM_SOURCE'
,
'UTM_MEDIUM'
,
'UTM_CAMPAIGN'
,
'UTM_CONTENT'
,
'UTM_TERM'
,
'PHONE'
,
'EMAIL'
,
'WEB'
,
'IM'
,
'LINK'
];
$startItem
=
0
;
$leadsResult
=
$serviceBuilder
->
getCRMScope
()->
lead
()->
list
(
$order
,
$filter
,
$select
,
$startItem
);
foreach
(
$leadsResult
->
getLeads
()
as
$lead
) {
print
(
"ID:
{$lead->ID}
, TITLE:
{$lead->TITLE}
, NAME:
{$lead->NAME}
, BIRTHDATE: "
.
(
$lead
->BIRTHDATE ?
$lead
->BIRTHDATE->
format
(DATE_ATOM) :
'N/A'
) .
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
'crm.lead.list'
,
{
select
: [
'*'
,
'UF_*'
],
start
:
50
,
filter
: {
'=OPPORTUNITY'
:
15000
,
},
order
: {
STATUS_ID
:
'ASC'
,
},
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
return
;
}
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
'crm.lead.list'
,
[
'select'
=> [
'*'
,
'UF_*'
],
'start'
=>
50
,
'filter'
=> [
'=OPPORTUNITY'
=>
15000
,
],
'order'
=> [
'STATUS_ID'
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
Some Practical Examples
Some Practical Examples
Search for unconverted leads with an amount greater than zero
Search for a lead by phone
Selecting leads for the month
BX24
.
callMethod
(
"crm.lead.list"
,
{
order
: {
"STATUS_ID"
:
"ASC"
},
filter
: {
">OPPORTUNITY"
:
0
,
"!STATUS_ID"
:
"CONVERTED"
},
select
: [
"ID"
,
"TITLE"
,
"STATUS_ID"
,
"OPPORTUNITY"
,
"CURRENCY_ID"
],
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
{
result.
next
();
}
}
}
);
BX24
.
callMethod
(
"crm.lead.list"
,
{
filter
: {
"PHONE"
:
"555888"
},
select
: [
"ID"
,
"TITLE"
]
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
{
result.
next
();
}
}
}
);
$result
=
CRest
::
call
(
'crm.lead.list'
,
[
'filter'
=> [
'>DATE_CREATE'
=>
'2023-10-01T00:00:00'
,
'<DATE_CREATE'
=>
'2023-10-31T23:59:59'
,
],
'select'
=> [
'ID'
,
'DATE_CREATE'
,
],
]
);
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
"TITLE"
:
"Lead 1"
,
"HONORIFIC"
:
null
,
"NAME"
:
"Erasmus"
,
"SECOND_NAME"
:
null
,
"LAST_NAME"
:
"Golden of Ireland"
,
"COMPANY_TITLE"
:
null
,
"COMPANY_ID"
:
"0"
,
"CONTACT_ID"
:
"2069"
,
"IS_RETURN_CUSTOMER"
:
"N"
,
"BIRTHDATE"
:
""
,
"SOURCE_ID"
:
"CALL"
,
"SOURCE_DESCRIPTION"
:
null
,
"STATUS_ID"
:
"CONVERTED"
,
"STATUS_DESCRIPTION"
:
null
,
"POST"
:
null
,
"COMMENTS"
:
null
,
"CURRENCY_ID"
:
"USD"
,
"OPPORTUNITY"
:
"15000.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"Y"
,
"HAS_PHONE"
:
"Y"
,
"HAS_EMAIL"
:
"Y"
,
"HAS_IMOL"
:
"N"
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
"2021-05-31T15:10:16+02:00"
,
"DATE_MODIFY"
:
"2021-11-26T18:56:13+02:00"
,
"DATE_CLOSED"
:
"2021-07-16T16:43:44+02:00"
,
"STATUS_SEMANTIC_ID"
:
"S"
,
"OPENED"
:
"Y"
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
"2021-07-16T16:43:44+02:00"
,
"ADDRESS"
:
"7677 Hollow Ridge Alley"
,
"ADDRESS_2"
:
null
,
"ADDRESS_CITY"
:
null
,
"ADDRESS_POSTAL_CODE"
:
null
,
"ADDRESS_REGION"
:
null
,
"ADDRESS_PROVINCE"
:
null
,
"ADDRESS_COUNTRY"
:
"Indonesia"
,
"ADDRESS_COUNTRY_CODE"
:
null
,
"ADDRESS_LOC_ADDR_ID"
:
"1"
,
"UTM_SOURCE"
:
null
,
"UTM_MEDIUM"
:
null
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
"LAST_ACTIVITY_BY"
:
"1"
,
"LAST_ACTIVITY_TIME"
:
"2021-05-31T15:10:16+02:00"
,
"UF_CRM_1704817278"
:
null
,
"UF_CRM_1706782596092"
:
null
,
"UF_CRM_1708952993785"
:
false
}
,
{
"ID"
:
"6"
,
"TITLE"
:
"Lead 2"
,
"HONORIFIC"
:
null
,
"NAME"
:
"Ignacius"
,
"SECOND_NAME"
:
null
,
"LAST_NAME"
:
"Slayny"
,
"COMPANY_TITLE"
:
null
,
"COMPANY_ID"
:
"0"
,
"CONTACT_ID"
:
"2070"
,
"IS_RETURN_CUSTOMER"
:
"N"
,
"BIRTHDATE"
:
""
,
"SOURCE_ID"
:
"CALL"
,
"SOURCE_DESCRIPTION"
:
null
,
"STATUS_ID"
:
"CONVERTED"
,
"STATUS_DESCRIPTION"
:
null
,
"POST"
:
null
,
"COMMENTS"
:
null
,
"CURRENCY_ID"
:
"USD"
,
"OPPORTUNITY"
:
"15000.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"Y"
,
"HAS_PHONE"
:
"Y"
,
"HAS_EMAIL"
:
"Y"
,
"HAS_IMOL"
:
"N"
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
"2021-05-31T15:10:16+02:00"
,
"DATE_MODIFY"
:
"2021-11-26T18:56:13+02:00"
,
"DATE_CLOSED"
:
"2021-07-16T16:43:47+02:00"
,
"STATUS_SEMANTIC_ID"
:
"S"
,
"OPENED"
:
"Y"
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
"2021-07-16T16:43:47+02:00"
,
"ADDRESS"
:
"35 Mosinee Street"
,
"ADDRESS_2"
:
null
,
"ADDRESS_CITY"
:
null
,
"ADDRESS_POSTAL_CODE"
:
null
,
"ADDRESS_REGION"
:
null
,
"ADDRESS_PROVINCE"
:
null
,
"ADDRESS_COUNTRY"
:
"Japan"
,
"ADDRESS_COUNTRY_CODE"
:
null
,
"ADDRESS_LOC_ADDR_ID"
:
"2"
,
"UTM_SOURCE"
:
null
,
"UTM_MEDIUM"
:
null
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
"LAST_ACTIVITY_BY"
:
"1"
,
"LAST_ACTIVITY_TIME"
:
"2021-05-31T15:10:16+02:00"
,
"UF_CRM_1704817278"
:
null
,
"UF_CRM_1706782596092"
:
null
,
"UF_CRM_1708952993785"
:
true
}
,
48
more leads with similar structure
]
,
"next"
:
50
,
"total"
:
654
,
"time"
:
{
"start"
:
1718292234.554781
,
"finish"
:
1718292234.657739
,
"duration"
:
0.10295796394348145
,
"processing"
:
0.05574321746826172
,
"date_start"
:
"2024-06-13T18:23:54+02:00"
,
"date_finish"
:
"2024-06-13T18:23:54+02:00"
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
The root element of the response. Contains an array of objects that hold information about the fields of deals.
It should be noted that the structure of the fields may change due to the
select
parameter.
For information about the structure of a lead, see the method
crm.lead.get
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
HTTP Status: 40x, 50x Error
{
"error"
:
""
,
"error_description"
:
"Access denied."
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
Possible Errors
Possible Errors
Error Text
Description
Access denied
The user does not have permission to read leads
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
Add Repeat Lead
How to Find Duplicates in CRM by Phone and Email
Copied
Was the article helpful?
Yes
No
Previous
Get Lead by Id
Next
Delete Lead

---

## Delete lead crm.lead.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/crm-lead-delete

Delete lead crm.lead.delete | Bitrix24 REST API and Marketplace Applications
Delete lead crm.lead.delete
Delete lead crm.lead.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Scope:
crm
Who can execute the method: any user with permission to delete leads
The method
crm.lead.delete
removes a lead and all associated objects: activities, history, timeline records, and others.
Objects are deleted if they are not linked to other objects or entities. If the objects are linked to other entities, only the link to the deleted lead will be removed.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
The identifier of the lead.
The identifier can be obtained using the methods
crm.lead.list
or
crm.lead.add
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
'{"id":"123"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"123","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.delete
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
'crm.lead.delete'
,
{ id }
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
$id
=
123
;
// Example lead ID to delete
$result
=
$serviceBuilder
->
getCRMScope
()
->
lead
()
->
delete
(
$id
);
if
(
$result
->
isSuccess
()) {
print
(
"Lead with ID
$id
has been successfully deleted."
);
}
else
{
print
(
"Failed to delete lead with ID
$id
."
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
"An error occurred: "
.
$e
->
getMessage
());
}
const
id =
prompt
(
"Enter ID"
);
BX24
.
callMethod
(
'crm.lead.delete'
,
{ id },
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
}
);
require_once
(
'crest.php'
);
$id
=
readline
(
"Enter ID: "
);
$result
=
CRest
::
call
(
'crm.lead.delete'
,
[
'id'
=>
$id
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
1705764932.998683
,
"finish"
:
1705764937.173995
,
"duration"
:
4.1753120422363281
,
"processing"
:
3.3076529502868652
,
"date_start"
:
"2024-01-20T18:35:32+01:00"
,
"date_finish"
:
"2024-01-20T18:35:37+01:00"
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
Returned Data
Returned Data
Name
type
Description
result
boolean
The root element of the response, contains
true
in case of success
time
time
Information about the execution time of the request
Error Handling
Error Handling
40x, 50x Error
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
The user does not have permission to delete leads
Not found
The lead with the provided
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
Copied
Was the article helpful?
Yes
No
Previous
Get List of Leads
Next
Get Lead Fields

---

## Get Lead Fields crm.lead.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/crm-lead-fields

Get Lead Fields crm.lead.fields | Bitrix24 REST API and Marketplace Applications
Get Lead Fields crm.lead.fields
Get Lead Fields crm.lead.fields
Method Parameters
Code Examples
Response Handling
Returned Data
Field Description
Error Handling
Statuses and System Error Codes
Scope:
crm
Who can execute the method: any user
The method
crm.lead.fields
returns the description of lead fields, including custom ones. A table with the description of standard fields can be found in the article
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.fields
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
https://**put_your_bitrix24_address**/rest/crm.lead.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.lead.fields'
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
info
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
$fieldsResult
=
$serviceBuilder
->
getCRMScope
()
->
lead
()
->
fields
();
$fieldsDescription
=
$fieldsResult
->
getFieldsDescription
();
// Assuming you want to print the fields description
print_r
(
$fieldsDescription
);
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
'crm.lead.fields'
,
{},
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
'crm.lead.fields'
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
"Lead Title"
}
,
"HONORIFIC"
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
"HONORIFIC"
,
"title"
:
"Salutation"
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
"First Name"
}
,
"SECOND_NAME"
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
"Middle Name"
}
,
"LAST_NAME"
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
"Last Name"
}
,
"BIRTHDATE"
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
"Birthdate"
}
,
"COMPANY_TITLE"
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
"Company Name"
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
"Additional Source Information"
}
,
"STATUS_ID"
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
"STATUS"
,
"title"
:
"Stage"
}
,
"STATUS_DESCRIPTION"
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
"Additional Stage Information"
}
,
"STATUS_SEMANTIC_ID"
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
"Status Semantic"
}
,
"POST"
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
"Position"
}
,
"ADDRESS"
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
"Address"
}
,
"ADDRESS_2"
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
"Address (Line 2)"
}
,
"ADDRESS_CITY"
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
"City"
}
,
"ADDRESS_POSTAL_CODE"
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
"Postal Code"
}
,
"ADDRESS_REGION"
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
"Region"
}
,
"ADDRESS_PROVINCE"
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
"Province"
}
,
"ADDRESS_COUNTRY"
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
"Country"
}
,
"ADDRESS_COUNTRY_CODE"
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
"Country Code"
}
,
"ADDRESS_LOC_ADDR_ID"
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
"Location Address ID"
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
"HAS_PHONE"
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
"Phone Provided"
}
,
"HAS_EMAIL"
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
"Email Provided"
}
,
"HAS_IMOL"
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
"Open Channel Provided"
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
"Responsible User"
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
"CONTACT_IDS"
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
"Returning Lead"
}
,
"DATE_CLOSED"
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
"Closing Date"
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
"External Source ID"
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
"Element ID in External Source"
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
,
"PHONE"
:
{
"type"
:
"crm_multifield"
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
"Phone"
}
,
"EMAIL"
:
{
"type"
:
"crm_multifield"
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
"E-mail"
}
,
"WEB"
:
{
"type"
:
"crm_multifield"
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
"Website"
}
,
"IM"
:
{
"type"
:
"crm_multifield"
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
"Messenger"
}
,
"LINK"
:
{
"type"
:
"crm_multifield"
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
"LINK"
}
}
,
"time"
:
{
"start"
:
1716903269.951179
,
"finish"
:
1716903270.017765
,
"duration"
:
0.06658601760864258
,
"processing"
:
0.029553890228271484
,
"date_start"
:
"2024-05-28T16:34:29+02:00"
,
"date_finish"
:
"2024-05-28T16:34:30+02:00"
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
lead
The root element of the response. Contains information about lead fields. The structure is described
below
time
time
Information about the execution time of the request
Type lead
Type lead
Name
type
Description
ID
integer
Integer identifier of the lead
TITLE
string
Lead title
HONORIFIC
crm_status
Type of salutation. Status from the directory. A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=HONORIFIC
NAME
string
Contact's first name
SECOND_NAME
string
Contact's middle name
LAST_NAME
string
Contact's last name
BIRTHDATE
date
Birthdate
COMPANY_TITLE
string
Name of the company associated with the lead
SOURCE_ID
crm_status
Identifier of the source. Status from the directory. A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=SOURCE
SOURCE_DESCRIPTION
string
Description of the source
STATUS_ID
crm_status
Identifier of the lead's stage. Status from the directory. A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=STATUS
STATUS_DESCRIPTION
string
Additional information about the stage
STATUS_SEMANTIC_ID
string
F (failed) – processed unsuccessfully
S (success) – processed successfully
P (processing) – lead is being processed
POST
string
Position
ADDRESS
string
Contact's address
ADDRESS_2
string
Second line of the address. In some countries, it is customary to split the address into 2 parts
ADDRESS_CITY
string
City
ADDRESS_POSTAL_CODE
string
Postal code
ADDRESS_REGION
string
Region
ADDRESS_PROVINCE
string
Province
ADDRESS_COUNTRY
string
Country
ADDRESS_COUNTRY_CODE
string
Country code
ADDRESS_LOC_ADDR_ID
string
Identifier of the address from the location module
CURRENCY_ID
crm_currency
Identifier of the currency
OPPORTUNITY
double
Estimated amount
IS_MANUAL_OPPORTUNITY
char
Indicator of manual calculation of the amount. Allowed values Y or N
OPENED
char
Available to all. Allowed values Y or N
COMMENTS
string
Comments
HAS_PHONE
char
Indicator of whether the phone field is filled. Allowed values Y or N
HAS_EMAIL
char
Indicator of whether the email field is filled. Allowed values Y or N
HAS_IMOL
char
Indicator of whether there is an associated open channel. Allowed values Y or N
ASSIGNED_BY_ID
user
Identifier of the user responsible for the lead
CREATED_BY_ID
user
Identifier of the user who created the lead
MODIFY_BY_ID
user
Identifier of the user who last modified it
MOVED_BY_ID
user
Identifier of the user who moved the element to the current stage
DATE_CREATE
datetime
Creation date
DATE_MODIFY
datetime
Modification date
MOVED_TIME
datetime
Date of moving the element to the current stage
COMPANY_ID
crm_company
Linking the lead to a company (Client->Company field)
CONTACT_ID
crm_contact
Linking the lead to a contact (Client->Contact field. In the case of multiple linked contacts, this field will contain the ID of the first linked contact)
IS_RETURN_CUSTOMER
char
Indicator of a returning lead. Allowed values Y or N
DATE_CLOSED
datetime
Closing date
ORIGINATOR_ID
string
Identifier of the data source. Used only for linking to an external source
ORIGIN_ID
string
Identifier of the element in the data source. Used only for linking to an external source
UTM_SOURCE
string
Advertising system. Google Ads, Facebook Ads, and others
UTM_MEDIUM
string
Traffic type. CPC (ads), CPM (banners)
UTM_CAMPAIGN
string
Advertising campaign designation
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
UTM_TERM
string
Campaign search condition. For example, keywords for contextual advertising
LAST_ACTIVITY_TIME
datetime
Time of the last activity
LAST_ACTIVITY_BY
string
Identifier of the user responsible for the last activity in this lead (e.g., who created a new activity in the lead)
PHONE
crm_multifield
Contact's phone
EMAIL
crm_multifield
Email address
WEB
crm_multifield
Lead resource URL
IM
crm_multifield
Messengers
LINK
crm_multifield
UF_...
Custom fields
Field Description
Field Description
type
Field type. Described above
isRequired
Indicator of whether the field is mandatory when creating a new lead
isReadOnly
Indicator of whether the field value can be edited
isImmutable
Indicator of whether the field value can only be filled once when creating a new element
isMultiple
Indicator of whether the field can have multiple values. If true, values in the field are passed as an array
isDynamic
Indicates whether the field is
custom
title
Field name
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
Copied
Was the article helpful?
Yes
No
Previous
Delete Lead
Next
Add Products to Lead

---

## Add products to lead crm.lead.productrows.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/crm-lead-productrows-set

Add products to lead crm.lead.productrows.set | Bitrix24 REST API and Marketplace Applications
Add products to lead crm.lead.productrows.set
Add products to lead crm.lead.productrows.set
We are still updating this page
Some data may be missing — we will complete it soon.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.productrows.set
sets (creates or updates) the product items of a lead.
Parameter
Description
id
Lead identifier.
rows
Product items - an array of the form
array(array("field"=>"value"[, ...])[, ...])
, where "field" can take values from the method
crm.productrow.fields
. The product items of the lead that exist before the method call will be replaced with the new ones. After saving, the lead's total will be recalculated.
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
"crm.lead.productrows.set"
,
{
id
: id,
rows
:
[
{
"PRODUCT_ID"
:
689
,
"PRICE"
:
100.00
,
"QUANTITY"
:
2
},
{
"PRODUCT_ID"
:
690
,
"PRICE"
:
200.00
,
"QUANTITY"
:
1
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
$id
=
readline
(
"Enter ID"
);
try
{
$response
=
$b24Service
->core
->
call
(
'crm.lead.productrows.set'
,
[
'id'
=>
$id
,
'rows'
=> [
[
'PRODUCT_ID'
=>
689
,
'PRICE'
=>
100.00
,
'QUANTITY'
=>
2
],
[
'PRODUCT_ID'
=>
690
,
'PRICE'
=>
200.00
,
'QUANTITY'
=>
1
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
'Error setting lead product rows: '
.
$e
->
getMessage
();
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
"crm.lead.productrows.set"
,
{
id
: id,
rows
:
[
{
"PRODUCT_ID"
:
689
,
"PRICE"
:
100.00
,
"QUANTITY"
:
2
},
{
"PRODUCT_ID"
:
690
,
"PRICE"
:
200.00
,
"QUANTITY"
:
1
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
info
(result.
data
());
}
);
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get Lead Fields
Next
Get Lead Products

---

## Get Lead Products crm.lead.productrows.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/crm-lead-productrows-get

Get Lead Products crm.lead.productrows.get | Bitrix24 REST API and Marketplace Applications
Get Lead Products crm.lead.productrows.get
Get Lead Products crm.lead.productrows.get
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.productrows.get
returns the product rows of a lead.
Parameter
Description
id
*
Lead identifier.
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
"crm.lead.productrows.get"
,
{
id
: id }
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
$id
=
$_POST
[
'id'
];
try
{
$response
=
$b24Service
->core
->
call
(
'crm.lead.productrows.get'
,
[
'id'
=>
$id
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
'Error getting lead product rows: '
.
$e
->
getMessage
();
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
"crm.lead.productrows.get"
,
{
id
: id },
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
Copied
Was the article helpful?
Yes
No
Previous
Add Products to Lead
Next
Overview of methods

---

## Linking Leads to Contacts: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/management-communication/index

Linking Leads to Contacts: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Linking Leads to Contacts: Overview of Methods
Linking Leads to Contacts: Overview of Methods
Features of Duplicate Leads
Benefits of Linking Leads and Contacts
Overview of Methods
Using the group of methods
crm.lead.contact.*
, you can establish or remove the connection between contacts and leads. A lead linked to a contact becomes a duplicate.
Quick navigation:
all methods
User documentation:
The "Client" field in the CRM detail form
Features of Duplicate Leads
Features of Duplicate Leads
A duplicate lead is a request from a client who is already in the company's customer database. Duplicate leads have hidden contact information fields: "Phone", "Email", "Address", "Details". A duplicate lead can only be converted into a deal. When a known client makes a new request, a duplicate lead will automatically be created, linked to the client’s detail form, if the CRM is set to handle duplicate leads.
The methods
crm.lead.contact.add
and
crm.lead.contact.items.set
add a connection between a lead and one or more contacts. When this connection is established, the lead automatically becomes a duplicate.
To restore the ability to convert a lead into a contact, remove the connection with contacts using the methods
crm.lead.contact.delete
if there is one contact, and
crm.lead.contact.items.delete
if there are multiple contacts. Once the connection is removed, the lead will no longer be a duplicate.
User Documentation
Duplicate Leads and Deals
Benefits of Linking Leads and Contacts
Benefits of Linking Leads and Contacts
The lead detail form displays information about linked contacts: name, phone number, email, position.
You can call or send an email directly from the lead detail form without navigating to the contact detail form.
Communication with the client: emails, calls, and chats from open channels will be stored in both the contact detail form and the lead detail form. Communications are not attached to closed leads.
CoPilot in CRM processes client calls from the lead detail form: it transcribes recordings, summarizes conversations, and fills in fields in the CRM detail form.
When
generating documents from a template
, you can use symbolic codes that automatically insert data from linked contacts into the document.
User Documentation
CoPilot in CRM
Overview of Methods
Overview of Methods
Scope:
crm
Who can perform the method: depending on the method
Method
Description
crm.lead.contact.add
Adds a contact link to the specified lead
crm.lead.contact.delete
Removes a contact link from the specified lead
crm.lead.contact.items.get
Retrieves a list of contacts linked to the lead
crm.lead.contact.items.set
Attaches a list of contacts to the specified lead
crm.lead.contact.items.delete
Removes a list of contacts from the lead
crm.lead.contact.fields
Retrieves the description of fields for the lead-contact link used by the methods in the
crm.lead.contact.*
family
Copied
Was the article helpful?
Yes
No
Previous
Get Lead Products
Next
Add contact binding to lead

---

## Add Contact Binding to Lead crm.lead.contact.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/management-communication/crm-lead-contact-add

Add Contact Binding to Lead crm.lead.contact.add | Bitrix24 REST API and Marketplace Applications
Add Contact Binding to Lead crm.lead.contact.add
Add Contact Binding to Lead crm.lead.contact.add
Method Parameters
Parameter fields
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
This method adds a contact binding to the specified lead.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
The identifier of the lead to which the contact should be added. The lead identifier can be obtained using the
get lead list method
fields
*
object
Field values (detailed description provided
below
) for adding a contact to the lead in the form of a structure:
fields
:
{
"CONTACT_ID"
:
"value"
,
"SORT"
:
"value"
,
"IS_PRIMARY"
:
"value"
}
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
CONTACT_ID
*
integer
The identifier of the contact
SORT
integer
Sort index. Defaults to
10
IS_PRIMARY
string
Primary contact flag
Y
— yes
N
— no
Defaults to
N
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
'{"id":1,"fields":{"CONTACT_ID":1010,"SORT":10,"IS_PRIMARY":"Y"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.contact.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":1,"fields":{"CONTACT_ID":1010,"SORT":10,"IS_PRIMARY":"Y"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.contact.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.lead.contact.add'
,
{
id
:
1
,
fields
: {
'CONTACT_ID'
:
1010
,
'SORT'
:
10
,
'IS_PRIMARY'
:
'Y'
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
'crm.lead.contact.add'
,
[
'id'
=>
1
,
'fields'
=> [
'CONTACT_ID'
=>
1010
,
'SORT'
=>
10
,
'IS_PRIMARY'
=>
'Y'
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
'Error adding lead contact: '
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
"crm.lead.contact.add"
,
{
id
:
1
,
fields
:
{
"CONTACT_ID"
:
1010
,
"SORT"
:
10
,
"IS_PRIMARY"
:
"Y"
}
},
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
'crm.lead.contact.add'
,
[
'id'
=>
1
,
'fields'
=>
[
'CONTACT_ID'
=>
1010
,
'SORT'
=>
10
,
'IS_PRIMARY'
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
boolean
The result of the operation
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
"NOT_FOUND"
,
"error_description"
:
"Not found."
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
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Element not found
Required fields not provided
Other errors (e.g., fatal errors)
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
Remove contact binding from lead crm.lead.contact.delete
Get a List of Related Contacts crm.lead.contact.items.get
Attach a list of contacts to a lead crm.lead.contact.items.set
Delete Contact List from Lead crm.lead.contact.items.delete
Get Lead-Contact Fields crm.lead.contact.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Remove contact binding from lead

---

## Remove contact binding from lead crm.lead.contact.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/management-communication/crm-lead-contact-delete

Remove contact binding from lead crm.lead.contact.delete | Bitrix24 REST API and Marketplace Applications
Remove contact binding from lead crm.lead.contact.delete
Remove contact binding from lead crm.lead.contact.delete
Method Parameters
Parameter fields
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
This method removes the binding of a contact to the specified lead.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the lead from which to remove the contact binding. The lead identifier can be obtained using the
get lead list
method.
fields
*
object
Field values (detailed description provided
below
) for adding a contact to the lead in the form of a structure:
fields
:
{
"CONTACT_ID"
:
"value"
,
}
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
CONTACT_ID
*
integer
Identifier of the contact
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
'{"id":1,"fields":{"CONTACT_ID":1010}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.contact.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":1,"fields":{"CONTACT_ID":1010},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.contact.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.lead.contact.delete'
,
{
id
:
1
,
fields
: {
'CONTACT_ID'
:
1010
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
'crm.lead.contact.delete'
,
[
'id'
=>
1
,
'fields'
=> [
'CONTACT_ID'
=>
1010
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
'Error deleting lead contact: '
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
"crm.lead.contact.delete"
,
{
id
:
1
,
fields
:
{
"CONTACT_ID"
:
1010
,
}
},
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
'crm.lead.contact.delete'
,
[
'id'
=>
1
,
'fields'
=>
[
'CONTACT_ID'
=>
1010
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
boolean
Result of the operation
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
"NOT_FOUND"
,
"error_description"
:
"Not found."
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
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Element not found
Required fields not provided
Other errors (e.g., fatal errors)
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
Add Contact Binding to Lead crm.lead.contact.add
Get a List of Related Contacts crm.lead.contact.items.get
Attach a list of contacts to a lead crm.lead.contact.items.set
Delete Contact List from Lead crm.lead.contact.items.delete
Get Lead-Contact Fields crm.lead.contact.fields
Copied
Was the article helpful?
Yes
No
Previous
Add contact binding to lead
Next
Get list of related contacts

---

## Get a List of Related Contacts crm.lead.contact.items.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/management-communication/crm-lead-contact-items-get

Get a List of Related Contacts crm.lead.contact.items.get | Bitrix24 REST API and Marketplace Applications
Get a List of Related Contacts crm.lead.contact.items.get
Get a List of Related Contacts crm.lead.contact.items.get
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
This method retrieves a list of contacts associated with a lead.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
The identifier of the lead. The lead identifier can be obtained using the
get lead list method
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
'{"id":1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.contact.items.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":1,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.contact.items.get
try
{
const
response =
await
$b24.
callMethod
(
"crm.lead.contact.items.get"
,
{
id
:
1
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
'crm.lead.contact.items.get'
,
[
'id'
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
'Error getting lead contact items: '
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
"crm.lead.contact.items.get"
,
{
id
:
1
,
},
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
'crm.lead.contact.items.get'
,
[
'id'
=>
1
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
"CONTACT_ID"
:
1010
,
"SORT"
:
10
,
"ROLE_ID"
:
0
,
"IS_PRIMARY"
:
"Y"
}
,
{
"CONTACT_ID"
:
1011
,
"SORT"
:
20
,
"ROLE_ID"
:
0
,
"IS_PRIMARY"
:
"N"
}
]
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
array
The result as an array of objects
time
time
Information about the execution time of the request
The result is an array of objects, each containing the following fields:
Field
Description
CONTACT_ID
integer
The identifier of the contact
SORT
integer
The sorting index
ROLE_ID
integer
The role identifier (reserved)
IS_PRIMARY
string
The primary contact flag
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Not found."
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
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Element not found
Required fields not provided
Other errors (e.g., fatal errors)
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
Add Contact Binding to Lead crm.lead.contact.add
Remove contact binding from lead crm.lead.contact.delete
Attach a list of contacts to a lead crm.lead.contact.items.set
Delete Contact List from Lead crm.lead.contact.items.delete
Get Lead-Contact Fields crm.lead.contact.fields
Copied
Was the article helpful?
Yes
No
Previous
Remove contact binding from lead
Next
Attach list of contacts to lead

---

## Attach a list of contacts to a lead crm.lead.contact.items.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/management-communication/crm-lead-contact-items-set

Attach a list of contacts to a lead crm.lead.contact.items.set | Bitrix24 REST API and Marketplace Applications
Attach a list of contacts to a lead crm.lead.contact.items.set
Attach a list of contacts to a lead crm.lead.contact.items.set
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
This method attaches a list of contacts to the specified lead.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the lead. The lead identifier can be obtained using the
get lead list method
items
*
object
A set of contacts represented as an array of objects with the following fields:
CONTACT_ID
*
— identifier of the contact
SORT
— sorting index
IS_PRIMARY
— primary contact flag
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
'{"id":1,"items":[{"CONTACT_ID":1010,"SORT":10,"IS_PRIMARY":"Y"},{"CONTACT_ID":1020,"SORT":20,"IS_PRIMARY":"N"}]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.contact.items.set
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":1,"items":[{"CONTACT_ID":1010,"SORT":10,"IS_PRIMARY":"Y"},{"CONTACT_ID":1020,"SORT":20,"IS_PRIMARY":"N"}],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.contact.items.set
try
{
const
response =
await
$b24.
callMethod
(
"crm.lead.contact.items.set"
,
{
id
:
1
,
items
: [
{
"CONTACT_ID"
:
1010
,
"SORT"
:
10
,
"IS_PRIMARY"
:
"Y"
},
{
"CONTACT_ID"
:
1020
,
"SORT"
:
20
,
"IS_PRIMARY"
:
"N"
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
'crm.lead.contact.items.set'
,
[
'id'
=>
1
,
'items'
=> [
[
'CONTACT_ID'
=>
1010
,
'SORT'
=>
10
,
'IS_PRIMARY'
=>
'Y'
,
],
[
'CONTACT_ID'
=>
1020
,
'SORT'
=>
20
,
'IS_PRIMARY'
=>
'N'
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
'Error setting lead contact items: '
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
"crm.lead.contact.items.set"
,
{
id
:
1
,
items
: [
{
"CONTACT_ID"
:
1010
,
"SORT"
:
10
,
"IS_PRIMARY"
:
"Y"
},
{
"CONTACT_ID"
:
1020
,
"SORT"
:
20
,
"IS_PRIMARY"
:
"N"
}
]
},
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
'crm.lead.contact.items.set'
,
[
'id'
=>
1
,
'items'
=> [
[
'CONTACT_ID'
=>
1010
,
'SORT'
=>
10
,
'IS_PRIMARY'
=>
'Y'
],
[
'CONTACT_ID'
=>
1020
,
'SORT'
=>
20
,
'IS_PRIMARY'
=>
'N'
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
true
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
boolean
Result of the operation
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
"NOT_FOUND"
,
"error_description"
:
"Not found."
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
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Element not found
Required fields not provided
Other errors (e.g., fatal errors)
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
Add Contact Binding to Lead crm.lead.contact.add
Remove contact binding from lead crm.lead.contact.delete
Get a List of Related Contacts crm.lead.contact.items.get
Delete Contact List from Lead crm.lead.contact.items.delete
Get Lead-Contact Fields crm.lead.contact.fields
Copied
Was the article helpful?
Yes
No
Previous
Get list of related contacts
Next
Remove list of contacts from lead

---

## Delete Contact List from Lead crm.lead.contact.items.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/management-communication/crm-lead-contact-items-delete

Delete Contact List from Lead crm.lead.contact.items.delete | Bitrix24 REST API and Marketplace Applications
Delete Contact List from Lead crm.lead.contact.items.delete
Delete Contact List from Lead crm.lead.contact.items.delete
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
This method deletes the contact list from a lead.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Lead identifier. The lead identifier can be obtained using the
get lead list method
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
'{"id":1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.contact.items.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":1,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.lead.contact.items.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.lead.contact.items.delete"
,
{
id
:
1
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
'crm.lead.contact.items.delete'
,
[
'id'
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
'Error deleting lead contact items: '
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
"crm.lead.contact.items.delete"
,
{
id
:
1
,
},
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
'crm.lead.contact.items.delete'
,
[
'id'
=>
1
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
"2024-05-03T17:19:01+03:00"
,
"date_finish"
:
"2024-05-03T17:19:01+03:00"
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
Operation result
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
"NOT_FOUND"
,
"error_description"
:
"Not found."
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
ACCESS_DENIED
Insufficient permissions
NOT_FOUND
Element not found
Required fields not provided
Other errors (e.g., fatal errors)
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
Add Contact Binding to Lead crm.lead.contact.add
Remove contact binding from lead crm.lead.contact.delete
Get a List of Related Contacts crm.lead.contact.items.get
Attach a list of contacts to a lead crm.lead.contact.items.set
Get Lead-Contact Fields crm.lead.contact.fields
Copied
Was the article helpful?
Yes
No
Previous
Attach list of contacts to lead
Next
Get lead-contact binding fields

---

## Get Lead-Contact Fields crm.lead.contact.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/management-communication/crm-lead-contact-fields

Get Lead-Contact Fields crm.lead.contact.fields | Bitrix24 REST API and Marketplace Applications
Get Lead-Contact Fields crm.lead.contact.fields
Get Lead-Contact Fields crm.lead.contact.fields
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
This method retrieves the description of fields for the lead-contact relationship, used by methods in the
crm.lead.contact.*
family.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.lead.contact.fields
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
https://**put_your_bitrix24_address**/rest/crm.lead.contact.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.lead.contact.fields'
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
'crm.lead.contact.fields'
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
'Error fetching lead contact fields: '
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
"crm.lead.contact.fields"
,
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
'crm.lead.contact.fields'
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
"IS_PRIMARY"
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
"Primary"
}
,
"CONTACT_ID"
:
{
"type"
:
"integer"
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
"Contact"
}
}
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
object
Root element of the response containing fields:
SORT
— sorting index
IS_PRIMARY
— primary contact flag
CONTACT_ID
— contact identifier
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
Continue Learning
Continue Learning
Add Contact Binding to Lead crm.lead.contact.add
Remove contact binding from lead crm.lead.contact.delete
Get a List of Related Contacts crm.lead.contact.items.get
Attach a list of contacts to a lead crm.lead.contact.items.set
Delete Contact List from Lead crm.lead.contact.items.delete
Copied
Was the article helpful?
Yes
No
Previous
Remove list of contacts from lead
Next
Overview of Methods

---

## Custom Lead Fields: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/index

Custom Lead Fields: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Custom Lead Fields: Overview of Methods
Custom Lead Fields: Overview of Methods
Types of Custom Fields
Custom Field Settings
Errors When Working with Custom Fields
Common Causes of Server Errors
Overview of Methods
Custom fields store information about a lead in various data formats: string, number, link, address, and others.
Quick navigation:
all methods
User documentation:
Custom fields in CRM
Types of Custom Fields
Types of Custom Fields
Use the method
crm.userfield.types
to retrieve the available types of custom fields. The method will return the ID and name of the field types.
(
[ID] => double
[title] => Number
)
Use the method
crm.userfield.fields
to get a list of characteristics of custom fields. The method will return the codes of the characteristics along with their type and name.
[MANDATORY] => Array
(
[type] => char
[title] => Required
)
Custom Field Settings
Custom Field Settings
Use the method
crm.userfield.settings.fields
to obtain a list of available settings. The method will return the supported settings for the requested field type.
[DEFAULT_VALUE] => Array
(
[type] => double
[title] => Default value
)
[PRECISION] => Array
(
[type] => int
[title] => Precision
)
Errors When Working with Custom Fields
Errors When Working with Custom Fields
When creating or deleting custom fields, the request may be interrupted with an error
INTERNAL_SERVER_ERROR
. This is an internal server error. The cause of the error can be found in the server logs at the time of the request:
In cloud Bitrix24, submit a request to
technical support
to get details about the error.
In on-premise Bitrix24, request the server error log from the server administrator or hosting administrator. Then, contact
technical support
and attach the log for analysis.
Common Causes of Server Errors
Common Causes of Server Errors
Up to 1016 custom fields can be created for leads—this is a limitation of the database architecture. If there are already 1016 fields for leads in Bitrix24, attempting to create a new field will result in the method
crm.lead.userfield.add
returning an error
INTERNAL_SERVER_ERROR
.
You can check the number of custom fields for leads using the method
crm.lead.userfield.list
.
There is a limitation on servers for the execution time of a single request—
max_execution_time
. The standard time is 60 seconds. If the request takes longer, it will be interrupted with an error
INTERNAL_SERVER_ERROR
.
The time for
creating
or
deleting
a custom field for leads depends on the number of leads. When a field is created, it is added to all lead detail forms. When a field is deleted, it is removed from all detail forms. The fewer leads in your Bitrix24, the faster fields are created and deleted.
To check the number of leads in Bitrix24, use the method
crm.lead.list
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can perform the methods: depending on the method
Methods
Events
Method
Description
crm.lead.userfield.add
Creates a new custom field for leads
crm.lead.userfield.update
Updates an existing custom field for leads
crm.lead.userfield.get
Returns a custom field for leads by ID
crm.lead.userfield.list
Returns a list of custom fields for leads by filter
crm.lead.userfield.delete
Deletes a custom field for leads
Event
Triggered
onCrmLeadUserFieldAdd
When a custom field is added
onCrmLeadUserFieldUpdate
When a custom field is updated
onCrmLeadUserFieldDelete
When a custom field is deleted
onCrmLeadUserFieldSetEnumValues
When the set of values for a list-type custom field is changed
Copied
Was the article helpful?
Yes
No
Previous
Get lead-contact binding fields
Next
Add Field

---

## Add Field crm.lead.userfield.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/crm-lead-userfield-add

Add Field crm.lead.userfield.add | Bitrix24 REST API and Marketplace Applications
Add Field crm.lead.userfield.add
Add Field crm.lead.userfield.add
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.userfield.add
creates a new custom field for leads.
The system limitation on the field name is 20 characters. The custom field name always has the prefix
UF_CRM_
, meaning the actual length of the name is 13 characters.
Parameter
Description
fields
Set of fields – an array of the form
array("field"=>"value"[, ...])
, containing the description of the custom field.
LIST
Contains a set of list values for custom fields of type List. Specified when creating/updating the field. Each value is an array with the fields:
VALUE
- the value of the list item. This field is required when creating a new item.
SORT
- sorting.
DEF
- if equal to
Y
, the list item is the default value. For multiple fields, multiple
DEF=Y
are allowed. For non-multiple, the first will be considered default.
XML_ID
- external code of the value. This parameter is considered only when updating already existing values of the list item.
ID
- identifier of the value. If specified, it is considered an update of an existing list item value, not the creation of a new one. It only makes sense when calling the
*.userfield.update
methods.
DEL
- if equal to Y, the existing list item will be deleted. Used if the ID parameter is filled.
A complete description of the fields can be obtained by calling the method
crm.userfield.fields
.
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
"crm.lead.userfield.add"
,
{
fields
:
{
"FIELD_NAME"
:
"MY_STRING"
,
"EDIT_FORM_LABEL"
:
"My String"
,
"LIST_COLUMN_LABEL"
:
"My String"
,
"USER_TYPE_ID"
:
"string"
,
"XML_ID"
:
"MY_STRING"
,
"SETTINGS"
: {
"DEFAULT_VALUE"
:
"Hello, World!"
}
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
'crm.lead.userfield.add'
,
[
'fields'
=> [
'FIELD_NAME'
=>
'MY_STRING'
,
'EDIT_FORM_LABEL'
=>
'My String'
,
'LIST_COLUMN_LABEL'
=>
'My String'
,
'USER_TYPE_ID'
=>
'string'
,
'XML_ID'
=>
'MY_STRING'
,
'SETTINGS'
=> [
'DEFAULT_VALUE'
=>
'Hello, World!'
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
'Error adding lead user field: '
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
"crm.lead.userfield.add"
,
{
fields
:
{
"FIELD_NAME"
:
"MY_STRING"
,
"EDIT_FORM_LABEL"
:
"My String"
,
"LIST_COLUMN_LABEL"
:
"My String"
,
"USER_TYPE_ID"
:
"string"
,
"XML_ID"
:
"MY_STRING"
,
"SETTINGS"
: {
"DEFAULT_VALUE"
:
"Hello, World!"
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
dir
(result.
data
());
}
);
Example of creating a list type field
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
"crm.lead.userfield.add"
,
{
fields
:
{
"FIELD_NAME"
:
"MY_LIST"
,
"EDIT_FORM_LABEL"
:
"My List"
,
"LIST_COLUMN_LABEL"
:
"My List"
,
"USER_TYPE_ID"
:
"enumeration"
,
"LIST"
: [ {
"VALUE"
:
"Item #1"
}, {
"VALUE"
:
"Item #2"
}, {
"VALUE"
:
"Item #3"
}, {
"VALUE"
:
"Item #4"
}, {
"VALUE"
:
"Item #5"
} ],
"XML_ID"
:
"MY_LIST"
,
"SETTINGS"
: {
"LIST_HEIGHT"
:
3
}
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
'crm.lead.userfield.add'
,
[
'fields'
=> [
'FIELD_NAME'
=>
'MY_LIST'
,
'EDIT_FORM_LABEL'
=>
'My List'
,
'LIST_COLUMN_LABEL'
=>
'My List'
,
'USER_TYPE_ID'
=>
'enumeration'
,
'LIST'
=> [
[
'VALUE'
=>
'Item #1'
],
[
'VALUE'
=>
'Item #2'
],
[
'VALUE'
=>
'Item #3'
],
[
'VALUE'
=>
'Item #4'
],
[
'VALUE'
=>
'Item #5'
],
],
'XML_ID'
=>
'MY_LIST'
,
'SETTINGS'
=> [
'LIST_HEIGHT'
=>
3
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
'Error adding lead user field: '
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
"crm.lead.userfield.add"
,
{
fields
:
{
"FIELD_NAME"
:
"MY_LIST"
,
"EDIT_FORM_LABEL"
:
"My List"
,
"LIST_COLUMN_LABEL"
:
"My List"
,
"USER_TYPE_ID"
:
"enumeration"
,
"LIST"
: [ {
"VALUE"
:
"Item #1"
}, {
"VALUE"
:
"Item #2"
}, {
"VALUE"
:
"Item #3"
}, {
"VALUE"
:
"Item #4"
}, {
"VALUE"
:
"Item #5"
} ],
"XML_ID"
:
"MY_LIST"
,
"SETTINGS"
: {
"LIST_HEIGHT"
:
3
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
dir
(result.
data
());
}
);
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Field

---

## Update Field crm.lead.userfield.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/crm-lead-userfield-update

Update Field crm.lead.userfield.update | Bitrix24 REST API and Marketplace Applications
Update Field crm.lead.userfield.update
Update Field crm.lead.userfield.update
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.userfield.update
updates an existing custom field for leads.
Parameter
Description
id
Identifier of the custom field.
fields
Set of fields - an array in the form
array("field"=>"value"[, ...])
, where "updated field" can take values returned by the method
crm.userfield.fields
.
LIST
Contains a set of list values for custom fields of type List. Specified when creating/updating the field. Each value is an array with the following fields:
VALUE
- value of the list item. This field is required when creating a new item.
SORT
- sorting.
DEF
- if equal to
Y
, the list item is the default value. For multiple fields, several
DEF=Y
are allowed. For non-multiple fields, the first will be considered default.
XML_ID
- external code of the value. This parameter is considered only when updating already existing values of the list item.
ID
- identifier of the value. If specified, it is considered that this is an update of an existing value of the list item, not the creation of a new one.
DEL
- if equal to
Y
, the existing list item will be deleted. Used if the ID parameter is filled.
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
label =
prompt
(
"Enter new name"
);
const
response =
await
$b24.
callMethod
(
"crm.lead.userfield.update"
,
{
id
: id,
fields
:
{
"EDIT_FORM_LABEL"
: label,
"LIST_COLUMN_LABEL"
: label
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
if
(response.
more
())
response.
next
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
$id
=
readline
(
"Enter ID"
);
$label
=
readline
(
"Enter new name"
);
try
{
$response
=
$b24Service
->core
->
call
(
'crm.lead.userfield.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'EDIT_FORM_LABEL'
=>
$label
,
'LIST_COLUMN_LABEL'
=>
$label
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
print_r
(
$result
->
data
());
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
'Error updating lead user field: '
.
$e
->
getMessage
();
}
var
id =
prompt
(
"Enter ID"
);
var
label =
prompt
(
"Enter new name"
);
BX24
.
callMethod
(
"crm.lead.userfield.update"
,
{
id
: id,
fields
:
{
"EDIT_FORM_LABEL"
: label,
"LIST_COLUMN_LABEL"
: label
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
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Add Field
Next
Get Field by Code

---

## Get Field by Code crm.lead.userfield.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/crm-lead-userfield-get

Get Field by Code crm.lead.userfield.get | Bitrix24 REST API and Marketplace Applications
Get Field by Code crm.lead.userfield.get
Get Field by Code crm.lead.userfield.get
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.userfield.get
returns a custom field of leads by its identifier.
Parameter
Description
id
*
Identifier of the custom field.
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
"crm.lead.userfield.get"
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
(
'Error:'
, error);
}
$id
=
$_POST
[
'id'
];
try
{
$response
=
$b24Service
->core
->
call
(
'crm.lead.userfield.get'
,
[
'id'
=>
$id
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
'Error getting lead user field: '
.
$e
->
getMessage
();
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
"crm.lead.userfield.get"
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
Copied
Was the article helpful?
Yes
No
Previous
Update Field
Next
Get List of Fields

---

## Get a list of fields crm.lead.userfield.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/crm-lead-userfield-list

Get a list of fields crm.lead.userfield.list | Bitrix24 REST API and Marketplace Applications
Get a list of fields crm.lead.userfield.list
Get a list of fields crm.lead.userfield.list
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.userfield.list
returns a list of custom fields for leads based on the filter.
Parameter
Description
order
Sorting fields.
filter
Filter fields.
Example
Example
JS
PHP
BX24.js
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.lead.userfield.list'
,
{
order
: {
"SORT"
:
"ASC"
},
filter
: {
"MANDATORY"
:
"N"
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in chunks and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.lead.userfield.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"MANDATORY"
:
"N"
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.lead.userfield.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"MANDATORY"
:
"N"
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
'crm.lead.userfield.list'
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
'MANDATORY'
=>
'N'
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
'Error fetching lead user fields: '
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
"crm.lead.userfield.list"
,
{
order
: {
"SORT"
:
"ASC"
},
filter
: {
"MANDATORY"
:
"N"
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
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get Field by Code
Next
Delete Field

---

## Delete Field crm.lead.userfield.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/crm-lead-userfield-delete

Delete Field crm.lead.userfield.delete | Bitrix24 REST API and Marketplace Applications
Delete Field crm.lead.userfield.delete
Delete Field crm.lead.userfield.delete
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.userfield.delete
deletes a custom field from leads.
Parameter
Description
id
*
Identifier of the custom field.
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
"crm.lead.userfield.delete"
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
$id
=
readline
(
"Enter ID"
);
try
{
$response
=
$b24Service
->core
->
call
(
'crm.lead.userfield.delete'
,
[
'id'
=>
$id
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
'Error deleting user field: '
.
$e
->
getMessage
();
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
"crm.lead.userfield.delete"
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
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get List of Fields
Next
Overview of Events

---

## Overview of Events When Working with Custom Lead Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/events/index

Overview of Events When Working with Custom Lead Fields | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Custom Lead Fields
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in near real-time: receiving notifications about the creation, update, or deletion of custom lead fields.
Detailed information on working with events is described in the article
Concept and Benefits of Event Handling
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to events for custom lead fields through:
outgoing webhook
application
and the method
event.bind
An example of a handler for the event is described in the article
How to Test Your Handler for Bitrix24 Event Processing
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
onCrmLeadUserFieldAdd
When a custom field is added manually or via the method
crm.lead.userfield.add
onCrmLeadUserFieldUpdate
When a custom field is changed manually or via the method
crm.lead.userfield.update
onCrmLeadUserFieldDelete
When a custom field is deleted manually or via the method
crm.lead.userfield.delete
onCrmLeadUserFieldSetEnumValues
When the set of values for a list-type custom field is changed manually or via the method
crm.lead.userfield.update
Copied
Was the article helpful?
Yes
No
Previous
Delete Field
Next
When Adding a Custom Field

---

## When Adding a Custom Field onCrmLeadUserFieldAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/events/on-crm-lead-user-field-add

When Adding a Custom Field onCrmLeadUserFieldAdd | Bitrix24 REST API and Marketplace Applications
What the Handler Receives
When Adding a Custom Field onCrmLeadUserFieldAdd
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMLEADUSERFIELDADD
will trigger when a new custom field is added for leads.
What the Handler Receives
What the Handler Receives
Data is sent as a POST request
{
"event"
:
"ONCRMLEADUSERFIELDADD"
,
"event_handler_id"
:
"713"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6977"
,
"ENTITY_ID"
:
"CRM_LEAD"
,
"FIELD_NAME"
:
"UF_CRM_1742999523"
}
}
,
"ts"
:
"1742999523"
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
ONCRMLEADUSERFIELDADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the added custom field.
Contains the key
FIELDS
data.FIELDS
object
Object containing information about the fields of the added custom field.
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
Identifier of the added custom field
ENTITY_ID
string
Identifier of the object to which the custom field relates. In this case —
CRM_LEAD
FIELD_NAME
string
Name of the added custom field
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
Continue Exploring
Continue Exploring
Event Handler
Register a new event handler event.bind
When updating a custom field onCrmLeadUserFieldUpdate
When Deleting a Custom Field onCrmLeadUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Updating a Custom Field

---

## When updating a custom field onCrmLeadUserFieldUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/events/on-crm-lead-user-field-update

When updating a custom field onCrmLeadUserFieldUpdate | Bitrix24 REST API and Marketplace Applications
What the handler receives
When updating a custom field onCrmLeadUserFieldUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMLEADUSERFIELDUPDATE
will trigger when a custom field for leads is updated.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMLEADUSERFIELDUPDATE"
,
"event_handler_id"
:
"715"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6977"
,
"ENTITY_ID"
:
"CRM_LEAD"
,
"FIELD_NAME"
:
"UF_CRM_1742999523"
}
}
,
"ts"
:
"1742999566"
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
ONCRMLEADUSERFIELDUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated custom field.
Contains the key
FIELDS
data.FIELDS
object
Object containing information about the fields of the updated custom field.
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
Identifier of the updated custom field
ENTITY_ID
string
Identifier of the object to which the custom field belongs. In this case —
CRM_LEAD
FIELD_NAME
string
Name of the updated custom field
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
When Adding a Custom Field onCrmLeadUserFieldAdd
When Deleting a Custom Field onCrmLeadUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
When Adding a Custom Field
Next
When Deleting a Custom Field

---

## When Deleting a Custom Field onCrmLeadUserFieldDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/events/on-crm-lead-user-field-delete

When Deleting a Custom Field onCrmLeadUserFieldDelete | Bitrix24 REST API and Marketplace Applications
What the Handler Receives
When Deleting a Custom Field onCrmLeadUserFieldDelete
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMLEADUSERFIELDDELETE
will trigger when a custom field for leads is deleted.
What the Handler Receives
What the Handler Receives
Data is sent as a POST request
{
"event"
:
"ONCRMLEADUSERFIELDDELETE"
,
"event_handler_id"
:
"717"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6977"
,
"ENTITY_ID"
:
"CRM_LEAD"
,
"FIELD_NAME"
:
"UF_CRM_1742999523"
}
}
,
"ts"
:
"1742999576"
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
ONCRMLEADUSERFIELDDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted custom field.
Contains the key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted custom field.
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
Identifier of the deleted custom field
ENTITY_ID
string
Identifier of the object to which the custom field belonged. In this case —
CRM_LEAD
FIELD_NAME
string
Name of the deleted custom field
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
Continue Exploring
Continue Exploring
Event Handler
Register a new event handler event.bind
When Adding a Custom Field onCrmLeadUserFieldAdd
When updating a custom field onCrmLeadUserFieldUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Updating a Custom Field
Next
When Changing the Set of Values for a Custom List Field

---

## When setting list values for the custom field onCrmLeadUserFieldSetEnumValues

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/userfield/events/on-crm-lead-user-field-set-enum-values

When setting list values for the custom field onCrmLeadUserFieldSetEnumValues | Bitrix24 REST API and Marketplace Applications
What the handler receives
When setting list values for the custom field onCrmLeadUserFieldSetEnumValues
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMLEADUSERFIELDSETENUMVALUES
will trigger when setting list values for custom fields of leads.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMLEADUSERFIELDSETENUMVALUES"
,
"event_handler_id"
:
"719"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6977"
,
"ENTITY_ID"
:
"CRM_LEAD"
,
"FIELD_NAME"
:
"UF_CRM_1742999523"
}
}
,
"ts"
:
"1742999523"
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
ONCRMLEADUSERFIELDSETENUMVALUES
event_handler_id
integer
Event handler identifier
data
object
Object containing information about the custom field for which list values are set.
Contains the key
FIELDS
data.FIELDS
object
Object containing information about the custom field's fields.
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
Identifier of the custom field
ENTITY_ID
string
Identifier of the object to which the custom field belongs. In this case —
CRM_LEAD
FIELD_NAME
string
Name of the custom field
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
When Adding a Custom Field onCrmLeadUserFieldAdd
When updating a custom field onCrmLeadUserFieldUpdate
When Deleting a Custom Field onCrmLeadUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Custom Field
Next
Overview of Events

---

## Overview of Events When Working with Leads

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/events/index

Overview of Events When Working with Leads | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Leads
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, update, or deletion of leads.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to lead events through:
outgoing webhook
application
and the method
event.bind
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
onCrmLeadAdd
When a lead is added manually or via the
crm.lead.add
method
onCrmLeadUpdate
When a lead is updated manually or via the
crm.lead.update
method
onCrmLeadDelete
When a lead is deleted manually or via the
crm.lead.delete
method
Copied
Was the article helpful?
Yes
No
Previous
When Changing the Set of Values for a Custom List Field
Next
When Adding a Lead

---

## Event onCrmLeadAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/events/on-crm-lead-add

Event onCrmLeadAdd | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmLeadAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The
ONCRMLEADADD
event will trigger when a new lead is created.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMLEADADD"
,
"event_handler_id"
:
"707"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"1000983"
}
}
,
"ts"
:
"1742807175"
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
ONCRMLEADADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created lead.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created lead.
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
Identifier of the created lead
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
Event onCrmLeadUpdate
Event onLeadDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Updating a Lead

---

## Event onCrmLeadUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/events/on-crm-lead-update

Event onCrmLeadUpdate | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmLeadUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The
ONCRMLEADUPDATE
event will trigger when a lead is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMLEADUPDATE"
,
"event_handler_id"
:
"709"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"1000983"
}
}
,
"ts"
:
"1742807189"
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
ONCRMLEADUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated lead.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the updated lead.
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
Identifier of the updated lead
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
Event onCrmLeadAdd
Event onLeadDelete
Copied
Was the article helpful?
Yes
No
Previous
When Adding a Lead
Next
When Deleting a Lead

---

## Event onLeadDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/events/on-crm-lead-delete

Event onLeadDelete | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onLeadDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONLEADDELETE
will trigger when a lead is deleted.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONLEADDELETE"
,
"event_handler_id"
:
"711"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"1000983"
}
}
,
"ts"
:
"1742807199"
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
ONLEADDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted lead.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted lead.
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
Identifier of the deleted lead
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
Event onCrmLeadAdd
Event onCrmLeadUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Updating a Lead
Next
Overview of Methods

---

## Managing Lead Cards: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/custom-form/index

Managing Lead Cards: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Managing Lead Cards: Overview of Methods
Managing Lead Cards: Overview of Methods
Linking Lead Cards with Other Objects
Configuring Cards for Simple and Repeat Leads
Universal Methods for Managing Cards
Overview of Methods
The group of methods
crm.lead.details.configuration.*
manages the settings of the card for two views:
"General view" — the card view for all employees
"My view" — personal card settings for the employee
For each card view, sections can be configured, and within each section, a list of fields can be defined. For example, create a section called "Contact Information" and include the fields "Phone" and "Email." For fields that do not pertain to contact information, create a different section.
Quick navigation:
all methods
Linking Lead Cards with Other Objects
Linking Lead Cards with Other Objects
User.
The user identifier
userId
is used when setting personal card settings. The user identifier can be obtained using the method
user.get
.
Lead Fields.
The field identifiers are used when setting visible fields in the card section. The identifiers for system and custom lead fields can be obtained using the method
crm.lead.fields
.
Configuring Cards for Simple and Repeat Leads
Configuring Cards for Simple and Repeat Leads
Leads can be of two types: simple and repeat. A lead becomes repeat if the "Client" field is filled. Repeat leads do not have contact fields such as "Phone," "Email," or "Address" — this information is stored in the contact or company linked through the "Client" field.
For both simple and repeat lead cards, you can configure your view. Pass the parameter
leadCustomerType: 1
for a simple lead and
leadCustomerType: 2
for a repeat lead.
Universal Methods for Managing Cards
Universal Methods for Managing Cards
Alongside the methods
crm.deal.details.configuration.*
for configuring lead cards, you can use the group of universal methods
crm.item.details.configuration.*
. The capabilities of the methods are the same, but the execution time may differ.
Universal methods
crm.item.details.configuration.*
have an additional parameter
entityTypeId
— the ID of the object type. The
entityTypeId
parameter allows you to apply universal methods to any CRM object. To manage a lead card through a universal method, pass
entityTypeId: 1
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: any user
Method
Description
crm.lead.details.configuration.get
Retrieves lead card settings
crm.lead.details.configuration.reset
Resets lead card settings
crm.lead.details.configuration.set
Sets lead card settings
crm.lead.details.configuration.forceCommonScopeForAll
Forces a common lead card for all users
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Lead
Next
Get Card Parameters

---

## Get parameters of crm.lead.details.configuration.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/custom-form/crm-lead-details-configuration-get

Get parameters of crm.lead.details.configuration.get | Bitrix24 REST API and Marketplace Applications
Get parameters of crm.lead.details.configuration.get
Get parameters of crm.lead.details.configuration.get
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.details.configuration.get
retrieves the configuration parameters for lead cards. The method reads the personal settings of the specified user’s card or the general settings defined for all users.
Warning
Please note that the settings for repeated lead cards may differ from those for simple lead cards. The parameter
leadCustomerType
is used to switch between lead card settings.
Parameter
Description
scope
unknown
The scope of the settings. Allowed values:
P
- personal settings,
C
- common settings.
userId
unknown
User identifier. If not specified, the current user is taken. Required only when requesting personal settings.
extras
unknown
Additional parameters. Here, the parameter
leadCustomerType
can be specified for leads, with allowed values:
1
- simple leads,
2
- repeated leads.
Examples
Examples
JS
PHP
BX24.js
try
{
const
response1 =
await
$b24.
callMethod
(
"crm.lead.details.configuration.get"
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
result1 = response1.
getData
().
result
;
console
.
dir
(result1);
const
response2 =
await
$b24.
callMethod
(
"crm.lead.details.configuration.get"
,
{
scope
:
"C"
}
);
const
result2 = response2.
getData
().
result
;
console
.
dir
(result2);
const
response3 =
await
$b24.
callMethod
(
"crm.lead.details.configuration.get"
,
{
scope
:
"C"
,
extras
: {
leadCustomerType
:
2
}
}
);
const
result3 = response3.
getData
().
result
;
console
.
dir
(result3);
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
//Request personal settings for lead cards for the user with identifier 1.
$response1
=
$b24Service
->core
->
call
(
'crm.lead.details.configuration.get'
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
'Personal lead details configuration for user 1: '
.
print_r
(
$result1
,
true
);
//Request common settings for lead cards.
$response2
=
$b24Service
->core
->
call
(
'crm.lead.details.configuration.get'
,
[
'scope'
=>
'C'
,
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
'Common lead details configuration: '
.
print_r
(
$result2
,
true
);
//Request common settings for repeated lead cards.
$response3
=
$b24Service
->core
->
call
(
'crm.lead.details.configuration.get'
,
[
'scope'
=>
'C'
,
'extras'
=> [
'leadCustomerType'
=>
2
],
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
'Common lead details configuration for repeated leads: '
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
'Error fetching lead details configuration: '
.
$e
->
getMessage
();
}
//--
//Request personal settings for lead cards for the user with identifier 1.
BX24
.
callMethod
(
"crm.lead.details.configuration.get"
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
//Request common settings for lead cards.
BX24
.
callMethod
(
"crm.lead.details.configuration.get"
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
//Request common settings for repeated lead cards.
BX24
.
callMethod
(
"crm.lead.details.configuration.get"
,
{
scope
:
"C"
,
extras
: {
leadCustomerType
:
2
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

## Reset Lead Card Settings crm.lead.details.configuration.reset

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/custom-form/crm-lead-details-configuration-reset

Reset Lead Card Settings crm.lead.details.configuration.reset | Bitrix24 REST API and Marketplace Applications
Reset Lead Card Settings crm.lead.details.configuration.reset
Reset Lead Card Settings crm.lead.details.configuration.reset
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.details.configuration.reset
resets the settings of lead cards. It removes the personal settings of the specified user’s card or the general settings defined for all users.
Warning
Please note that the settings for repeat leads may differ from those for simple leads. The parameter
leadCustomerType
is used to switch between lead card settings.
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
User identifier. If not specified, the current user is taken. Required only when resetting personal settings.
extras
unknown
Additional parameters. Here, for leads, the parameter
leadCustomerType
can be specified, with allowed values:
1
- simple leads,
2
- repeat leads.
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
"crm.lead.details.configuration.reset"
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
'crm.lead.details.configuration.reset'
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
'Error resetting lead details configuration: '
.
$e
->
getMessage
();
}
//---
//Reset personal settings of the lead card for the user with identifier 1.
BX24
.
callMethod
(
"crm.lead.details.configuration.reset"
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

## Set Parameters for crm.lead.details.configuration.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/custom-form/crm-lead-details-configuration-set

Set Parameters for crm.lead.details.configuration.set | Bitrix24 REST API and Marketplace Applications
Set Parameters for crm.lead.details.configuration.set
Set Parameters for crm.lead.details.configuration.set
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.details.configuration.set
sets the lead card settings. This method records the personal settings of the specified user’s card or the general settings for all users.
Warning
Please note that the settings for repeat leads may differ from the settings for simple leads. The parameter
leadCustomerType
is used to switch between lead card settings.
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
User identifier. If not specified, the current user is used. Required only when setting personal settings.
extras
unknown
Additional parameters. Here, the parameter
leadCustomerType
can be specified for leads, with allowed values:
1
- simple leads,
2
- repeat leads.
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
"crm.lead.details.configuration.set"
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
"General Information"
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
"STATUS_ID"
},
{
name
:
"NAME"
},
{
name
:
"BIRTHDATE"
},
{
name
:
"POST"
},
{
name
:
"PHONE"
},
{
name
:
"EMAIL"
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
'crm.lead.details.configuration.set'
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
'General Information'
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
'STATUS_ID'
],
[
'name'
=>
'NAME'
],
[
'name'
=>
'BIRTHDATE'
],
[
'name'
=>
'POST'
],
[
'name'
=>
'PHONE'
],
[
'name'
=>
'EMAIL'
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
'Error setting lead details configuration: '
.
$e
->
getMessage
();
}
//---
//Setting personal lead card settings for the user with identifier 1.
BX24
.
callMethod
(
"crm.lead.details.configuration.set"
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
"General Information"
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
"STATUS_ID"
},
{
name
:
"NAME"
},
{
name
:
"BIRTHDATE"
},
{
name
:
"POST"
},
{
name
:
"PHONE"
},
{
name
:
"EMAIL"
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

## Set a common lead card for all users crm.lead.details.configuration.forceCommonScopeForAll

**Source:** https://apidocs.bitrix24.com/api-reference/crm/leads/custom-form/crm-lead-details-configuration-force-common-scope-for-all

Set a common lead card for all users crm.lead.details.configuration.forceCommonScopeForAll | Bitrix24 REST API and Marketplace Applications
Set a common lead card for all users crm.lead.details.configuration.forceCommonScopeForAll
Set a common lead card for all users crm.lead.details.configuration.forceCommonScopeForAll
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.lead.details.configuration.forceCommonScopeForAll
forcibly sets a common lead card for all users.
Warning
Please note that the settings for repeat leads may differ from the settings for simple leads. The parameter
leadCustomerType
is used to switch between lead card settings.
Parameter
Description
extras
unknown
Additional parameters. Here, for leads, the parameter
leadCustomerType
can be specified with the following acceptable values:
1
- simple leads,
2
- repeat leads
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
"crm.lead.details.configuration.forceCommonScopeForAll"
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
'crm.lead.details.configuration.forceCommonScopeForAll'
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
'Error setting common lead card for all users: '
.
$e
->
getMessage
();
}
//---
//Set a common lead card for all users.
BX24
.
callMethod
(
"crm.lead.details.configuration.forceCommonScopeForAll"
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
Overview of methods

---

