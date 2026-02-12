---
description: 'CRM Contacts API: CRUD operations, events, custom forms'
methods:
- crm.activity.
- crm.address.
- crm.contact.add
- crm.contact.company.
- crm.contact.company.add
- crm.contact.company.delete
- crm.contact.company.fields
- crm.contact.company.items.delete
- crm.contact.company.items.get
- crm.contact.company.items.set
- crm.contact.delete
- crm.contact.details.configuration.
- crm.contact.details.configuration.forceCommonScopeForAll
- crm.contact.details.configuration.get
- crm.contact.details.configuration.reset
- crm.contact.details.configuration.set
- crm.contact.fields
- crm.contact.get
- crm.contact.list
- crm.contact.update
- crm.contact.userfield.
- crm.contact.userfield.add
- crm.contact.userfield.delete
- crm.contact.userfield.get
- crm.contact.userfield.list
- crm.contact.userfield.update
- crm.enum.addresstype
- crm.item.details.configuration.
- crm.item.list
- crm.item.update
pages: 16
title: 'CRM Contacts API: CRUD operations, events, custom forms'
---
# CRM Contacts API: CRUD operations, events, custom forms
> CRM Contacts API: CRUD operations, events, custom forms
> **16 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Contacts in CRM: Overview of Methods](#contacts-in-crm-overview-of-methods)
- [Create a new contact crm.contact.add](#create-a-new-contact-crmcontactadd)
- [Update Contact crm.contact.update](#update-contact-crmcontactupdate)
- [Get Contact by Id crm.contact.get](#get-contact-by-id-crmcontactget)
- [Get the list of contacts crm.contact.list](#get-the-list-of-contacts-crmcontactlist)
- [Delete contact crm.contact.delete](#delete-contact-crmcontactdelete)
- [Get Contact Fields crm.contact.fields](#get-contact-fields-crmcontactfields)
- [Overview of Events When Working with Contacts](#overview-of-events-when-working-with-contacts)
- [Event onCrmContactAdd](#event-oncrmcontactadd)
- [Event onCrmContactUpdate](#event-oncrmcontactupdate)
- [Event onCrmContactDelete](#event-oncrmcontactdelete)
- [Managing Contact Cards: Overview of Methods](#managing-contact-cards-overview-of-methods)
- [Get Parameters of crm.contact.details.configuration.get](#get-parameters-of-crmcontactdetailsconfigurationge)
- [Set Parameters for Individual Card crm.contact.details.configuration.set](#set-parameters-for-individual-card-crmcontactdetai)
- [Set Common Contact Card for All Users crm.contact.details.configuration.forceCommonScopeForAll](#set-common-contact-card-for-all-users-crmcontactde)
- [Reset Contact Card Parameters crm.contact.details.configuration.reset](#reset-contact-card-parameters-crmcontactdetailscon)

---

## Contacts in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/index

Contacts in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Contact Connection with Other CRM Objects
Contacts in CRM: Overview of Methods
Contact Connection with Other CRM Objects
Contact Card
Widgets
Overview of Methods and Events
Basic
Companies
Custom Fields
Managing Contact Cards
A contact is a CRM object that stores data about clients—individuals. The contact card contains phone numbers, email addresses, and messenger identifiers in a special format that allows communication with the client directly through Bitrix.
Quick navigation:
all methods and events
User documentation:
contacts in Bitrix24
Contact Connection with Other CRM Objects
Contact Connection with Other CRM Objects
Deal, lead, SPA.
Any CRM object that has the standard field
Client
is connected to contacts. The connection is managed through groups of methods for
deals
,
leads
, and
SPAs
.
Company.
A single contact can be linked to multiple companies. This connection is managed using the group of methods
crm.contact.company.*
. When you select a company in the
Client
field in deals or SPAs, all associated contacts are automatically pulled into the field.
Requisites.
The requisites themselves are a separate object, and methods from the group
crm.requisite.*
and
crm.address.*
are used to create or modify them. They are displayed in the
Requisites
field of the contact card.
User Documentation
Connection between deals, contacts, and companies
Requisite connections with CRM objects
Changes in working with addresses and requisites in CRM
Contact Card
Contact Card
The main workspace in a contact is the General tab of its card. It consists of two parts:
The left part contains fields with information. If the system fields are insufficient, you can create your own custom fields. They allow you to store information in various data formats: string, number, link, address, and others. The group of methods
crm.contact.userfield.*
is used to create, modify, retrieve, or delete custom contact fields.
The right part contains the contact's timeline. In it, you can create, edit, filter, and delete CRM activities using the group of methods
crm.activity.*
, and timeline records using the group of methods
crm.timeline.*
.
The parameters of the contact card can be managed through the group of methods
crm.contact.details.configuration.*
.
User Documentation
CRM Card: Features and Settings
System Fields in CRM
Custom Fields in CRM
Timeline in CRM Entity
Widgets
Widgets
You can embed an application into the contact card. Thanks to embedding, you can use the application without leaving the contact card.
There are two embedding scenarios:
Use special
embedding locations
. For example, by creating your own tab.
Create a
custom field
where the interface of your application will be loaded.
Typical use-cases and scenarios
Widget embedding mechanism
Embed a widget in the CRM card
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can perform methods: depending on the method
Basic
Basic
Methods
Events
Method
Description
crm.contact.add
Creates a new contact
crm.contact.update
Updates an existing contact
crm.contact.get
Returns a contact by ID
crm.contact.list
Returns a list of contacts by filter
crm.contact.delete
Deletes a contact and all associated objects
crm.contact.fields
Returns the description of contact fields, including custom fields
Event
Triggered
onCrmContactAdd
When a contact is created
onCrmContactUpdate
When a contact is updated
onCrmContactDelete
When a contact is deleted
Companies
Companies
Method
Description
crm.contact.company.add
Adds a company to the specified contact
crm.contact.company.items.get
Retrieves the set of companies associated with the specified contact
crm.contact.company.items.set
Sets the set of companies associated with the specified contact
crm.contact.company.delete
Removes a company from the specified contact
crm.contact.company.items.delete
Clears the set of companies associated with the specified contact
crm.contact.company.fields
Returns the description of fields for contact-company connection
Custom Fields
Custom Fields
Methods
Events
Method
Description
crm.contact.userfield.add
Creates a custom field for contacts
crm.contact.userfield.update
Modifies an existing custom field for contacts
crm.contact.userfield.get
Returns a custom field for contacts by Id
crm.contact.userfield.list
Returns a list of custom fields for contacts
crm.contact.userfield.delete
Deletes a custom field for contacts
Event
Triggered
onCrmContactUserFieldAdd
When a custom field is added
onCrmContactUserFieldUpdate
When a custom field is updated
onCrmContactUserFieldDelete
When a custom field is deleted
onCrmContactUserFieldSetEnumValues
When the set of values for a list-type custom field is changed
Managing Contact Cards
Managing Contact Cards
Method
Description
crm.contact.details.configuration.get
Retrieves the settings of contact cards
crm.contact.details.configuration.reset
Resets the settings of contact cards
crm.contact.details.configuration.set
Sets the settings of contact cards
crm.contact.details.configuration.forceCommonScopeForAll
Allows forcing a common contact card for all users
Copied
Was the article helpful?
Yes
No
Previous
Set Common Card for All Users
Next
Create new contact

---

## Create a new contact crm.contact.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/crm-contact-add

Create a new contact crm.contact.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create a new contact crm.contact.add
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
Who can execute the method: any user with "add|import" access permission for contacts
The method
crm.contact.add
creates a new contact.
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
.
An incorrect field in
fields
will be ignored
params
object
Object containing a set of additional parameters.
The structure and possible values are described
below
Parameter fields
Parameter fields
Name
type
Description
HONORIFIC
crm_status
Salutation.
The list of available salutation types can be obtained using the method
crm.status.list
with the filter
{ ENTITY_ID: "HONORIFIC" }
.
Default — the first available salutation type
NAME
string
First name
SECOND_NAME
string
Middle name
LAST_NAME
string
Last name
PHOTO
file
Photo
BIRTHDATE
date
Date of birth
TYPE_ID
crm_status
Contact type.
The list of available contact types can be obtained using the method
crm.status.list
with the filter
{ ENTITY_ID: "CONTACT_TYPE" }
.
Default — the first available contact type
SOURCE_ID
crm_status
Source.
The list of available source types can be obtained using the method
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
Default — the first available source type
SOURCE_DESCRIPTION
string
Additional information about the source
POST
string
Position
COMMENTS
string
Comment. Supports BB codes
OPENED
boolean
Is it available to everyone? Possible values:
Y
— yes
N
— no
Default
Y
. The default value can be changed in CRM settings
EXPORT
boolean
Is the contact included in the export? Possible values:
Y
— yes
N
— no
Default
Y
ASSIGNED_BY_ID
user
Identifier of the user responsible for the element.
Default — the identifier of the user calling the method
COMPANY_ID
crm_company
Identifier of the main company for the contact.
The list of companies can be obtained using the method
crm.item.list
with
entityTypeId = 4
COMPANY_IDS
crm_company[]
Array of identifiers of companies to which the contact is linked.
The list of companies can be obtained using the method
crm.item.list
with
entityTypeId = 4
UTM_SOURCE
string
Advertising system (Google Ads, etc.)
UTM_MEDIUM
string
Traffic type. Possible values:
CPC
— ads
CPM
— banners
UTM_CAMPAIGN
string
Advertising campaign designation
UTM_CONTENT
string
Campaign content. For example, for contextual ads
UTM_TERM
string
Campaign search condition. For example, keywords for contextual advertising
TRACE
string
Information for
Sales Intelligence
PHONE
crm_multifield[]
Phone
EMAIL
crm_multifield[]
E-mail
WEB
crm_multifield[]
Website
IM
crm_multifield[]
Messenger
LINK
crm_multifield[]
Links. Service field
UF_...
Custom fields. For example,
UF_CRM_25534736
.
Depending on the account settings, contacts may have a set of custom fields of specific types.
You can add a custom field to a contact using the method
crm.contact.userfield.add
PARENT_ID_...
Relationship fields.
If there are SPAs related to contacts in the account, there is a field for each such SPA that stores the relationship between that SPA and the contact. The field itself stores the identifier of the element of that SPA.
For example, the field
PARENT_ID_153
— relationship with the SPA
entityTypeId=153
. It stores the identifier of the element of that SPA related to the current contact
Fields for linking with external data sources
If the contact is created by an external system, then:
the field
ORIGINATOR_ID
stores the string identifier of that system
the field
ORIGIN_ID
stores the string identifier of the contact in that external system
the field
ORIGIN_VERSION
stores the version of the contact data in that external system
Name
type
Description
ORIGINATOR_ID
string
Identifier of the external system that is the source of data about this contact
ORIGIN_ID
string
Version of the contact data in the external system. Used to protect data from accidental overwriting by the external system.
If the data was imported and not changed in the external system, such data can be edited in CRM without fear that the next export will overwrite the data
ORIGIN_VERSION
string
Original version
Import
The fields are available for filling when the parameter
IMPORT = 'Y'
is passed in the
params
parameter.
Name
type
Description
DATE_CREATE
datetime
Creation date.
Available when
IMPORT = Y
is passed in
params
.
Cannot be earlier than the creation date of the last created contact
DATE_MODIFY
datetime
Modification date.
Available when
IMPORT = Y
is passed in
params
CREATED_BY_ID
user
Created by.
Available when
IMPORT = Y
is passed in
params
MODIFY_BY_ID
user
Modified by.
Available when
IMPORT = Y
is passed in
params
Deprecated fields
Address fields in the contact are deprecated and are only used in compatibility mode. To work with the address, use
requisites
.
Name
type
Description
ADDRESS
string
Address
ADDRESS_2
string
Second line of the address
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
integer
Location address identifier
Parameter params
Parameter params
Name
type
Description
REGISTER_SONET_EVENT
boolean
Should the event of adding a contact be registered in the live feed? Possible values:
Y
— yes
N
— no
Default
N
IMPORT
boolean
Is import mode enabled? Possible values:
Y
— yes
To pass the value
No
, you must either not pass the parameter at all or pass the value
0
,
''
Default
No
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
'{"FIELDS":{"HONORIFIC":"HNR_RU_1","NAME":"John","SECOND_NAME":"Ivanovich","LAST_NAME":"Ivanov","PHOTO":{"fileData":"**put_photo_data_here**"},"BIRTHDATE":"11.11.2001","TYPE_ID":"PARTNER","SOURCE_ID":"WEB","SOURCE_DESCRIPTION":"*Additional information about the source*","POST":"Administrator","COMMENTS":"**put_comment_here**","OPENED":"Y","EXPORT":"N","ASSIGNED_BY_ID":6,"COMPANY_ID":12,"COMPANY_IDS":[12,13,15],"UTM_SOURCE":"google","UTM_MEDIUM":"CPC","UTM_CAMPAIGN":"summer_sale","UTM_CONTENT":"header_banner","UTM_TERM":"discount","PHONE":[{"VALUE":"+12333333555","VALUE_TYPE":"WORK"},{"VALUE":"+15599888666","VALUE_TYPE":"HOME"}],"EMAIL":[{"VALUE":"ivanov@example.mailing","VALUE_TYPE":"MAILING"},{"VALUE":"ivanov@example.work","VALUE_TYPE":"WORK"}],"UF_CRM_1720697698689":"Example value of a custom field with type \"String\"","PARENT_ID_1224":12}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"FIELDS":{"HONORIFIC":"HNR_RU_1","NAME":"John","SECOND_NAME":"Ivanovich","LAST_NAME":"Ivanov","PHOTO":{"fileData":"**put_photo_data_here**"},"BIRTHDATE":"11.11.2001","TYPE_ID":"PARTNER","SOURCE_ID":"WEB","SOURCE_DESCRIPTION":"*Additional information about the source*","POST":"Administrator","COMMENTS":"**put_comment_here**","OPENED":"Y","EXPORT":"N","ASSIGNED_BY_ID":6,"COMPANY_ID":12,"COMPANY_IDS":[12,13,15],"UTM_SOURCE":"google","UTM_MEDIUM":"CPC","UTM_CAMPAIGN":"summer_sale","UTM_CONTENT":"header_banner","UTM_TERM":"discount","PHONE":[{"VALUE":"+12333333555","VALUE_TYPE":"WORK"},{"VALUE":"+15599888666","VALUE_TYPE":"HOME"}],"EMAIL":[{"VALUE":"ivanov@example.mailing","VALUE_TYPE":"MAILING"},{"VALUE":"ivanov@example.work","VALUE_TYPE":"WORK"}],"UF_CRM_1720697698689":"Example value of a custom field with type \"String\"","PARENT_ID_1224":12},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.add'
,
{
fields
: {
HONORIFIC
:
"HNR_RU_1"
,
NAME
:
"John"
,
SECOND_NAME
:
"Ivanovich"
,
LAST_NAME
:
"Ivanov"
,
PHOTO
: {
fileData
:
document
.
getElementById
(
'photo'
),
},
BIRTHDATE
:
'11.11.2001'
,
TYPE_ID
:
"PARTNER"
,
SOURCE_ID
:
"WEB"
,
SOURCE_DESCRIPTION
:
"*Additional information about the source*"
,
POST
:
"Administrator"
,
COMMENTS
:
`
Example comment inside the contact
[B]Bold text[/B]
[I]Italic[/I]
[U]Underlined[/U]
[S]Strikethrough[/S]
[B][I][U][S]Mix[/S][/U][/I][/B]
[LIST]
[*]List item #1
[*]List item #2
[*]List item #3
[/LIST]
[LIST=1]
[*]Numbered list item #1
[*]Numbered list item #2
[*]Numbered list item #3
[/LIST]
`
,
OPENED
:
"Y"
,
EXPORT
:
"N"
,
ASSIGNED_BY_ID
:
6
,
COMPANY_ID
:
12
,
COMPANY_IDS
: [
12
,
13
,
15
],
UTM_SOURCE
:
"google"
,
UTM_MEDIUM
:
"CPC"
,
UTM_CAMPAIGN
:
"summer_sale"
,
UTM_CONTENT
:
"header_banner"
,
UTM_TERM
:
"discount"
,
PHONE
: [
{
VALUE
:
"+12333333555"
,
VALUE_TYPE
:
"WORK"
,
},
{
VALUE
:
"+15599888666"
,
VALUE_TYPE
:
"HOME"
,
}
],
EMAIL
: [
{
VALUE
:
"ivanov@example.mailing"
,
VALUE_TYPE
:
"MAILING"
,
},
{
VALUE
:
"ivanov@example.work"
,
VALUE_TYPE
:
"WORK"
,
}
],
UF_CRM_1720697698689
:
"Example value of a custom field with type \"String\""
,
PARENT_ID_1224
:
12
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
'crm.contact.add'
,
[
'fields'
=> [
'HONORIFIC'
=>
'HNR_RU_1'
,
'NAME'
=>
'John'
,
'SECOND_NAME'
=>
'Ivanovich'
,
'LAST_NAME'
=>
'Ivanov'
,
'PHOTO'
=> [
'fileData'
=> document.
getElementById
(
'photo'
),
],
'BIRTHDATE'
=>
'11.11.2001'
,
'TYPE_ID'
=>
'PARTNER'
,
'SOURCE_ID'
=>
'WEB'
,
'SOURCE_DESCRIPTION'
=>
'*Additional information about the source*'
,
'POST'
=>
'Administrator'
,
'COMMENTS'
=> `
Example comment inside the contact
[B]Bold text[/B]
[I]Italic[/I]
[U]Underlined[/U]
[S]Strikethrough[/S]
[B][I][U][S]Mix[/S][/U][/I][/B]
[LIST]
[*]List item #
1
[*]List item #
2
[*]List item #
3
[/LIST]
[LIST=
1
]
[*]Numbered
list
item #
1
[*]Numbered
list
item #
2
[*]Numbered
list
item #
3
[/LIST]
`,
'OPENED'
=>
'Y'
,
'EXPORT'
=>
'N'
,
'ASSIGNED_BY_ID'
=>
6
,
'COMPANY_ID'
=>
12
,
'COMPANY_IDS'
=> [
12
,
13
,
15
],
'UTM_SOURCE'
=>
'google'
,
'UTM_MEDIUM'
=>
'CPC'
,
'UTM_CAMPAIGN'
=>
'summer_sale'
,
'UTM_CONTENT'
=>
'header_banner'
,
'UTM_TERM'
=>
'discount'
,
'PHONE'
=> [
[
'VALUE'
=>
'+12333333555'
,
'VALUE_TYPE'
=>
'WORK'
,
],
[
'VALUE'
=>
'+15599888666'
,
'VALUE_TYPE'
=>
'HOME'
,
]
],
'EMAIL'
=> [
[
'VALUE'
=>
'ivanov@example.mailing'
,
'VALUE_TYPE'
=>
'MAILING'
,
],
[
'VALUE'
=>
'ivanov@example.work'
,
'VALUE_TYPE'
=>
'WORK'
,
]
],
'UF_CRM_1720697698689'
=>
'Example value of a custom field with type "String"'
,
'PARENT_ID_1224'
=>
12
,
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
'Error adding contact: '
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
'crm.contact.add'
,
{
fields
: {
HONORIFIC
:
"HNR_RU_1"
,
NAME
:
"John"
,
SECOND_NAME
:
"Ivanovich"
,
LAST_NAME
:
"Ivanov"
,
PHOTO
: {
fileData
:
document
.
getElementById
(
'photo'
),
},
BIRTHDATE
:
'11.11.2001'
,
TYPE_ID
:
"PARTNER"
,
SOURCE_ID
:
"WEB"
,
SOURCE_DESCRIPTION
:
"*Additional information about the source*"
,
POST
:
"Administrator"
,
COMMENTS
:
`
Example comment inside the contact
[B]Bold text[/B]
[I]Italic[/I]
[U]Underlined[/U]
[S]Strikethrough[/S]
[B][I][U][S]Mix[/S][/U][/I][/B]
[LIST]
[*]List item #1
[*]List item #2
[*]List item #3
[/LIST]
[LIST=1]
[*]Numbered list item #1
[*]Numbered list item #2
[*]Numbered list item #3
[/LIST]
`
,
OPENED
:
"Y"
,
EXPORT
:
"N"
,
ASSIGNED_BY_ID
:
6
,
COMPANY_ID
:
12
,
COMPANY_IDS
: [
12
,
13
,
15
],
UTM_SOURCE
:
"google"
,
UTM_MEDIUM
:
"CPC"
,
UTM_CAMPAIGN
:
"summer_sale"
,
UTM_CONTENT
:
"header_banner"
,
UTM_TERM
:
"discount"
,
PHONE
: [
{
VALUE
:
"+12333333555"
,
VALUE_TYPE
:
"WORK"
,
},
{
VALUE
:
"+15599888666"
,
VALUE_TYPE
:
"HOME"
,
}
],
EMAIL
: [
{
VALUE
:
"ivanov@example.mailing"
,
VALUE_TYPE
:
"MAILING"
,
},
{
VALUE
:
"ivanov@example.work"
,
VALUE_TYPE
:
"WORK"
,
}
],
UF_CRM_1720697698689
:
"Example value of a custom field with type \"String\""
,
PARENT_ID_1224
:
12
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
'crm.contact.add'
,
[
'FIELDS'
=> [
'HONORIFIC'
=>
'HNR_RU_1'
,
'NAME'
=>
'John'
,
'SECOND_NAME'
=>
'Ivanovich'
,
'LAST_NAME'
=>
'Ivanov'
,
'PHOTO'
=> [
'fileData'
=>
$_FILES
[
'photo'
]
],
'BIRTHDATE'
=>
'11.11.2001'
,
'TYPE_ID'
=>
'PARTNER'
,
'SOURCE_ID'
=>
'WEB'
,
'SOURCE_DESCRIPTION'
=>
'*Additional information about the source*'
,
'POST'
=>
'Administrator'
,
'COMMENTS'
=> `
Example comment inside the contact
[B]Bold text[/B]
[I]Italic[/I]
[U]Underlined[/U]
[S]Strikethrough[/S]
[B][I][U][S]Mix[/S][/U][/I][/B]
[LIST]
[*]List item #
1
[*]List item #
2
[*]List item #
3
[/LIST]
[LIST=
1
]
[*]Numbered
list
item #
1
[*]Numbered
list
item #
2
[*]Numbered
list
item #
3
[/LIST]
`,
'OPENED'
=>
'Y'
,
'EXPORT'
=>
'N'
,
'ASSIGNED_BY_ID'
=>
6
,
'COMPANY_ID'
=>
12
,
'COMPANY_IDS'
=> [
12
,
13
,
15
],
'UTM_SOURCE'
=>
'google'
,
'UTM_MEDIUM'
=>
'CPC'
,
'UTM_CAMPAIGN'
=>
'summer_sale'
,
'UTM_CONTENT'
=>
'header_banner'
,
'UTM_TERM'
=>
'discount'
,
'PHONE'
=> [
[
'VALUE'
=>
'+12333333555'
,
'VALUE_TYPE'
=>
'WORK'
,
],
[
'VALUE'
=>
'+15599888666'
,
'VALUE_TYPE'
=>
'HOME'
,
]
],
'EMAIL'
=> [
[
'VALUE'
=>
'ivanov@example.mailing'
,
'VALUE_TYPE'
=>
'MAILING'
,
],
[
'VALUE'
=>
'ivanov@example.work'
,
'VALUE_TYPE'
=>
'WORK'
,
]
],
'UF_CRM_1720697698689'
=>
'Example value of a custom field with type "String"'
,
'PARENT_ID_1224'
=>
12
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
46
,
"time"
:
{
"start"
:
1723713732.235658
,
"finish"
:
1723713733.742049
,
"duration"
:
1.5063910484313965
,
"processing"
:
1.1416668891906738
,
"date_start"
:
"2024-08-15T11:22:12+02:00"
,
"date_finish"
:
"2024-08-15T11:22:13+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
integer
Root element of the response, contains the identifier of the created contact
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
The user does not have permission to "Add" or "Import" contacts
-
Disk resource exhausted
ERROR_CORE
The field
Work e-mail
contains an invalid address
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
Update Contact crm.contact.update
Get Contact by Id crm.contact.get
Get the list of contacts crm.contact.list
Delete contact crm.contact.delete
Get Contact Fields crm.contact.fields
Add Contact via Web Form
Add a contact with details via a web form
How to Change or Delete Phone Numbers and Emails
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Update contact

---

## Update Contact crm.contact.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/crm-contact-update

Update Contact crm.contact.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Contact crm.contact.update
Method Parameters
Parameter fields
Parameter params
Code Examples
Working with Multiple Fields
Update a Multiple Field
Delete a Single Value from a Multiple Field
Add a New Value to a Multiple Field
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with "edit" access permission for contacts
The method
crm.contact.update
updates an existing contact.
It is recommended to pass the complete set of address fields when updating the address.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the contact to be changed.
The identifier can be obtained using the methods
crm.contact.list
or
crm.contact.add
fields
*
object
Object in the format:
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
Object containing a set of additional parameters.
The structure and possible values are described
below
Parameter fields
Parameter fields
Name
type
Description
HONORIFIC
crm_status
Salutation.
The list of available salutation types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "HONORIFIC" }
NAME
string
First name
SECOND_NAME
string
Middle name
LAST_NAME
string
Last name
PHOTO
file
Photo
BIRTHDATE
date
Date of birth
TYPE_ID
crm_status
Contact type.
The list of available contact types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "CONTACT_TYPE" }
SOURCE_ID
crm_status
Source
The list of available source types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
SOURCE_DESCRIPTION
string
Additional information about the source
POST
string
Position
COMMENTS
string
Comment. Supports BB codes
OPENED
boolean
Is it available to everyone? Possible values:
Y
— yes
N
— no
EXPORT
boolean
Is the contact participating in the export? Possible values:
Y
— yes
N
— no
ASSIGNED_BY_ID
user
Identifier of the user responsible for the item
COMPANY_ID
crm_company
Identifier of the main company for the contact.
The list of companies can be obtained using the method
crm.item.list
with
entityTypeId = 4
COMPANY_IDS
crm_company[]
Array of identifiers of companies to which the contact is linked.
The list of companies can be obtained using the method
crm.item.list
with
entityTypeId = 4
UTM_SOURCE
string
Advertising system (Google Ads, etc.)
UTM_MEDIUM
string
Type of traffic. Possible values:
CPC
— ads
CPM
— banners
UTM_CAMPAIGN
string
Advertising campaign designation
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
UTM_TERM
string
Search condition of the campaign. For example, keywords for contextual advertising
PHONE
crm_multifield[]
Phone
EMAIL
crm_multifield[]
E-mail
WEB
crm_multifield[]
Website
IM
crm_multifield[]
Messenger
LINK
crm_multifield[]
Links. Service field
UF_...
Custom fields. For example,
UF_CRM_25534736
.
Depending on the account settings, contacts may have a set of custom fields of specific types.
To change file fields, it is recommended to use the method
crm.item.update
.
A custom field can be added to a contact using the method
crm.contact.userfield.add
PARENT_ID_...
Relationship fields.
If there are smart processes related to contacts in the account, there is a field for each such smart process that stores the relationship between this smart process and the contact. The field itself stores the identifier of the element of that smart process.
For example, the field
PARENT_ID_153
— relationship with the smart process
entityTypeId=153
. It stores the identifier of the element of this smart process related to the current contact
Fields for external data sources
If the contact was created by an external system, then:
the field
ORIGINATOR_ID
stores the string identifier of that system
the field
ORIGIN_ID
stores the string identifier of the contact in that external system
the field
ORIGIN_VERSION
stores the version of the contact data in that external system
Name
type
Description
ORIGINATOR_ID
string
Identifier of the external system that is the source of data about this contact
ORIGIN_ID
string
Version of the contact data in the external system. Used to protect data from accidental overwriting by the external system.
If the data was imported and not changed in the external system, then such data can be edited in CRM without fear that the next export will lead to data overwriting
ORIGIN_VERSION
string
Version of the original
Deprecated fields
Address fields in the contact are deprecated and are only used in compatibility mode. To work with the address, use
requisites
.
Name
type
Description
ADDRESS
string
Address
ADDRESS_2
string
Second line of the address
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
integer
Identifier of the location address
Parameter params
Parameter params
Name
type
Description
REGISTER_SONET_EVENT
boolean
Should the update event of the contact be registered in the activity stream? Possible values:
Y
— yes
N
— no
Default is
N
REGISTER_HISTORY_EVENT
boolean
Should the update of the contact be registered in the history? Possible values:
Y
— yes
N
— no
Default is
Y
Code Examples
Code Examples
How to Use Examples in Documentation
Update contact with
id = 43
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
'{"ID":43,"FIELDS":{"NAME":"John","BIRTHDATE":"11.11.1999","TYPE_ID":"RECOMMENDATION","SOURCE_ID":"WEB","POST":"Network Administrator","COMMENTS":"New comment","OPENED":"N","EXPORT":"Y","ASSIGNED_BY_ID":1,"COMPANY_ID":12,"COMPANY_IDS":[13,15],"UF_CRM_1720697698689":"Example of a new value for a custom field of type \"String\"","PARENT_ID_1224":14},"PARAMS":{"REGISTER_SONET_EVENT":"N","REGISTER_HISTORY_EVENT":"N"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":43,"FIELDS":{"NAME":"John","BIRTHDATE":"11.11.1999","TYPE_ID":"RECOMMENDATION","SOURCE_ID":"WEB","POST":"Network Administrator","COMMENTS":"New comment","OPENED":"N","EXPORT":"Y","ASSIGNED_BY_ID":1,"COMPANY_ID":12,"COMPANY_IDS":[13,15],"UF_CRM_1720697698689":"Example of a new value for a custom field of type \"String\"","PARENT_ID_1224":14},"PARAMS":{"REGISTER_SONET_EVENT":"N","REGISTER_HISTORY_EVENT":"N"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.update'
,
{
id
:
43
,
fields
: {
NAME
:
"John"
,
BIRTHDATE
:
'11.11.1999'
,
TYPE_ID
:
"RECOMMENDATION"
,
SOURCE_ID
:
"WEB"
,
POST
:
"Network Administrator"
,
COMMENTS
:
"New comment"
,
OPENED
:
"N"
,
EXPORT
:
"Y"
,
ASSIGNED_BY_ID
:
1
,
COMPANY_ID
:
12
,
COMPANY_IDS
: [
13
,
15
],
UF_CRM_1720697698689
:
"Example of a new value for a custom field of type \"String\""
,
PARENT_ID_1224
:
14
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
$contactId
=
123
;
// Example contact ID
$fields
= [
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
'1990-01-01'
))->
format
(
DateTime
::
ATOM
),
'PHONE'
=>
'123456789'
,
'EMAIL'
=>
'john.doe@example.com'
,
'ADDRESS'
=>
'123 Main St'
,
'ADDRESS_CITY'
=>
'Anytown'
,
'ADDRESS_COUNTRY'
=>
'USA'
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
contact
()
->
update
(
$contactId
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
'Update failed.'
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
'Error: '
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
'crm.contact.update'
,
{
id
:
43
,
fields
: {
NAME
:
"John"
,
BIRTHDATE
:
'11.11.1999'
,
TYPE_ID
:
"RECOMMENDATION"
,
SOURCE_ID
:
"WEB"
,
POST
:
"Network Administrator"
,
COMMENTS
:
"New comment"
,
OPENED
:
"N"
,
EXPORT
:
"Y"
,
ASSIGNED_BY_ID
:
1
,
COMPANY_ID
:
12
,
COMPANY_IDS
: [
13
,
15
],
UF_CRM_1720697698689
:
"Example of a new value for a custom field of type \"String\""
,
PARENT_ID_1224
:
14
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
'crm.contact.update'
,
[
'ID'
=>
43
,
'FIELDS'
=> [
'NAME'
=>
'John'
,
'BIRTHDATE'
=>
'11.11.1999'
,
'TYPE_ID'
=>
'RECOMMENDATION'
,
'SOURCE_ID'
=>
'WEB'
,
'POST'
=>
'Network Administrator'
,
'COMMENTS'
=>
'New comment'
,
'OPENED'
=>
'N'
,
'EXPORT'
=>
'Y'
,
'ASSIGNED_BY_ID'
=>
1
,
'COMPANY_ID'
=>
12
,
'COMPANY_IDS'
=> [
13
,
15
],
'UF_CRM_1720697698689'
=>
'Example of a new value for a custom field of type "String"'
,
'PARENT_ID_1224'
=>
14
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
Working with Multiple Fields
Working with Multiple Fields
Update a Multiple Field
Update a Multiple Field
To overwrite an existing value of a multiple field, pass the
ID
of the field you want to change and its new value/type.
Suppose there are the following values for the
PHONE
field:
[
{
"ID"
:
"222"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"111111"
,
"TYPE_ID"
:
"PHONE"
}
,
{
"ID"
:
"223"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"222222"
,
"TYPE_ID"
:
"PHONE"
}
,
{
"ID"
:
"224"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"333333"
,
"TYPE_ID"
:
"PHONE"
}
]
To change the value of the phone with
ID = 223
, pass the following
fields
parameter:
{
"fields"
:
{
"PHONE"
:
[
{
"ID"
:
223
,
"VALUE"
:
"444444"
,
"VALUE_TYPE"
:
"MOBILE"
}
]
}
}
Delete a Single Value from a Multiple Field
Delete a Single Value from a Multiple Field
To delete one of the values from a multiple field, pass their identifiers and either the parameter
DELETE = 'Y'
or an empty
VALUE
.
Suppose there are the following values for the
PHONE
field:
[
{
"ID"
:
"222"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"111111"
,
"TYPE_ID"
:
"PHONE"
}
,
{
"ID"
:
"223"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"222222"
,
"TYPE_ID"
:
"PHONE"
}
,
{
"ID"
:
"224"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"333333"
,
"TYPE_ID"
:
"PHONE"
}
,
{
"ID"
:
"225"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"44444"
,
"TYPE_ID"
:
"PHONE"
}
]
Let's consider ways to delete all values except for the phone with
ID = 225
:
{
"fields"
:
{
"PHONE"
:
[
{
"ID"
:
222
,
"DELETE"
:
"Y"
}
,
{
"ID"
:
223
,
"VALUE"
:
""
}
,
{
"ID"
:
224
}
]
}
}
As a result, the following will remain:
[
{
"ID"
:
"225"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"44444"
,
"TYPE_ID"
:
"PHONE"
}
]
Add a New Value to a Multiple Field
Add a New Value to a Multiple Field
To add a new value, simply enter it. Existing values will not be changed.
Example of adding a new value
55555
:
{
"fields"
:
{
"PHONE"
:
[
{
"VALUE"
:
"55555"
,
"VALUE_TYPE"
:
"WORK"
}
]
}
}
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
1723820393.459406
,
"finish"
:
1723820396.129949
,
"duration"
:
2.6705431938171387
,
"processing"
:
2.1193439960479736
,
"date_start"
:
"2024-08-16T16:59:53+02:00"
,
"date_finish"
:
"2024-08-16T16:59:56+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Root element of the response,
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
"Contact is not found"
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
The
fields
parameter is not an object
-
Parameter 'params' must be array
The
params
parameter is not an object
-
Access denied
The user does not have permission to "Edit" contacts
-
Disk resource exhausted
ERROR_CORE
The field
Work e-mail
contains an incorrect address
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
Create a new contact crm.contact.add
Get Contact by Id crm.contact.get
Get the list of contacts crm.contact.list
Delete contact crm.contact.delete
Get Contact Fields crm.contact.fields
How to Change or Delete Phone Numbers and Emails
Copied
Was the article helpful?
Yes
No
Previous
Create new contact
Next
Get contact by Id

---

## Get Contact by Id crm.contact.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/crm-contact-get

Get Contact by Id crm.contact.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Contact by Id crm.contact.get
Method Parameters
Code Examples
Response Handling
Returned Data
contact
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with "read" access permission for contacts
The method
crm.contact.get
returns a contact by its identifier.
To get a list of companies associated with the contact, use the method
crm.contact.company.items.get
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the contact. Can be obtained using the methods
crm.contact.list
or
crm.contact.add
Code Examples
Code Examples
How to Use Examples in Documentation
Get contact with
id = 23
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
'{"ID":23}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":23,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.get'
,
{
id
:
23
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
$contactId
=
123
;
// Example contact ID
$contactResult
=
$serviceBuilder
->
getCRMScope
()
->
contact
()
->
get
(
$contactId
);
$itemResult
=
$contactResult
->
contact
();
print
(
"ID: "
.
$itemResult
->ID . PHP_EOL);
print
(
"Name: "
.
$itemResult
->NAME . PHP_EOL);
print
(
"Last Name: "
.
$itemResult
->LAST_NAME . PHP_EOL);
print
(
"Birthday: "
.
$itemResult
->BIRTHDATE?->
format
(DATE_ATOM) . PHP_EOL);
print
(
"Created Date: "
.
$itemResult
->DATE_CREATE->
format
(DATE_ATOM) . PHP_EOL);
print
(
"Modified Date: "
.
$itemResult
->DATE_MODIFY->
format
(DATE_ATOM) . PHP_EOL);
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
'crm.contact.get'
,
{
id
:
23
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
'crm.contact.get'
,
[
'ID'
=>
23
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
"43"
,
"POST"
:
"Administrator"
,
"COMMENTS"
:
"\nExample comment inside the contact\n\n[B]Bold text[\/B]\n[I]Italic[\/I]\n[U]Underlined[\/U]\n[S]Strikethrough[\/S]\n[B][I][U][S]Mix[\/S][\/U][\/I][\/B]\n\n[LIST]\n[*]List item #1\n[*]List item #2\n[*]List item #3\n[\/LIST]\n\n[LIST=1]\n[*]Numbered list item #1\n[*]Numbered list item #2\n[*]Numbered list item #3\n[\/LIST]\n"
,
"HONORIFIC"
:
"HNR_EN_1"
,
"NAME"
:
"John"
,
"SECOND_NAME"
:
"Doe"
,
"LAST_NAME"
:
"Smith"
,
"PHOTO"
:
null
,
"LEAD_ID"
:
null
,
"TYPE_ID"
:
"PARTNER"
,
"SOURCE_ID"
:
"WEB"
,
"SOURCE_DESCRIPTION"
:
"*Additional information about the source*"
,
"COMPANY_ID"
:
"12"
,
"BIRTHDATE"
:
"2001-11-11T02:00:00+02:00"
,
"EXPORT"
:
"N"
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
"DATE_CREATE"
:
"2024-08-15T10:38:21+02:00"
,
"DATE_MODIFY"
:
"2024-08-15T10:38:21+02:00"
,
"ASSIGNED_BY_ID"
:
"6"
,
"CREATED_BY_ID"
:
"1"
,
"MODIFY_BY_ID"
:
"1"
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
"ORIGIN_VERSION"
:
null
,
"FACE_ID"
:
null
,
"LAST_ACTIVITY_TIME"
:
"2024-08-15T10:38:21+02:00"
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
"ADDRESS_LOC_ADDR_ID"
:
null
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
"summer_sale"
,
"UTM_CONTENT"
:
"header_banner"
,
"UTM_TERM"
:
"discount"
,
"PARENT_ID_1224"
:
"12"
,
"LAST_ACTIVITY_BY"
:
"1"
,
"UF_CRM_1720697698689"
:
"Example value of a custom field with type \u0022String\u0022"
,
"PHONE"
:
[
{
"ID"
:
"156"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"+13333333555"
,
"TYPE_ID"
:
"PHONE"
}
,
{
"ID"
:
"157"
,
"VALUE_TYPE"
:
"HOME"
,
"VALUE"
:
"+15599888666"
,
"TYPE_ID"
:
"PHONE"
}
]
,
"EMAIL"
:
[
{
"ID"
:
"158"
,
"VALUE_TYPE"
:
"MAILING"
,
"VALUE"
:
"johnsmith@example.mailing"
,
"TYPE_ID"
:
"EMAIL"
}
,
{
"ID"
:
"159"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"johnsmith@example.work"
,
"TYPE_ID"
:
"EMAIL"
}
]
}
,
"time"
:
{
"start"
:
1723736139.883652
,
"finish"
:
1723736140.299369
,
"duration"
:
0.41571712493896484
,
"processing"
:
0.14158892631530762
,
"date_start"
:
"2024-08-15T17:35:39+02:00"
,
"date_finish"
:
"2024-08-15T17:35:40+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
contact
Root element of the response. Contains information about the contact fields. The structure is described
below
time
time
Object containing information about the request execution time
contact
contact
Name
type
Description
ID
integer
Identifier of the contact
POST
string
Position
COMMENTS
text
Comment
HONORIFIC
crm_status
Salutation
NAME
string
First name
SECOND_NAME
string
Middle name
LAST_NAME
string
Last name
PHOTO
file
Photo
LEAD_ID
crm_lead
Identifier of the lead based on which the contact was created
TYPE_ID
crm_status
Type of contact
SOURCE_ID
crm_status
Source
SOURCE_DESCRIPTION
text
Additional information about the source
COMPANY_ID
crm_company
Identifier of the main company
BIRTHDATE
date
Date of birth
EXPORT
boolean
Whether the contact is included in the export. Possible values:
Y
— yes
N
— no
HAS_PHONE
boolean
Whether a phone is set. Possible values:
Y
— yes
N
— no
HAS_EMAIL
boolean
Whether an e-mail is set. Possible values:
Y
— yes
N
— no
HAS_IMOL
boolean
Whether an open channel is set. Possible values:
Y
— yes
N
— no
DATE_CREATE
datetime
Creation date
DATE_MODIFY
datetime
Modification date
ASSIGNED_BY_ID
user
Responsible person
CREATED_BY_ID
user
Created by
MODIFY_BY_ID
user
Modified by
OPENED
boolean
Available to everyone. Possible values:
Y
— yes
N
— no
FACE_ID
integer
Link to faces from the
faceid
module
LAST_ACTIVITY_TIME
datetime
Last activity
LAST_ACTIVITY_BY
user
Who performed the last activity in the timeline
UTM_SOURCE
string
Advertising system (Google Ads, Facebook Ads, etc.)
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
Search condition of the campaign. For example, keywords for contextual advertising
PHONE
crm_multifield[]
Phone
EMAIL
crm_multifield[]
E-mail
WEB
crm_multifield[]
Website
IM
crm_multifield[]
Messenger
LINK
crm_multifield[]
Links. Service field
Fields for external data source connections
If the contact was created by an external system, then:
the field
ORIGINATOR_ID
stores the string identifier of that system
the field
ORIGIN_ID
stores the string identifier of the contact in that external system
the field
ORIGIN_VERSION
stores the version of the contact data in that external system
Name
type
Description
ORIGINATOR_ID
string
External source
ORIGIN_ID
string
Identifier of the element in the external source
ORIGIN_VERSION
string
Version of the original
Deprecated Fields
Address fields in the contact are deprecated and are only used for compatibility mode. To work with the address, use
details
.
Name
type
Description
ADDRESS
string
Address
ADDRESS_2
string
Second line of the address
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
ADDRESS_LOC_ADDR_ID
integer
Identifier of the location address
Fields of type
crm_multifield
Fields of type
crm_multifield
(
PHONE
,
EMAIL
,
WEB
,
IM
,
LINK
) are explicitly returned by this method only if the values of this field are not equal to
null
.
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
parameter is not provided or the provided value is not a positive integer
Access denied
The user does not have permission to "Read" the contact
Not found
The contact with the provided
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
Create a new contact crm.contact.add
Update Contact crm.contact.update
Get the list of contacts crm.contact.list
Delete contact crm.contact.delete
Get Contact Fields crm.contact.fields
How to Change or Delete Phone Numbers and Emails
Add Calendar Event for Client Interaction
How to Send an Email to a Client on Behalf of an Employee
Copied
Was the article helpful?
Yes
No
Previous
Update contact
Next
Get list of contacts

---

## Get the list of contacts crm.contact.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/crm-contact-list

Get the list of contacts crm.contact.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of contacts crm.contact.list
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
Who can execute the method: any user with "read" access permission for contacts
The method
crm.contact.list
returns a list of contacts based on a filter. It is an implementation of the list method for contacts.
To get a list of companies associated with a contact, use the method
crm.contact.company.items.get
Method Parameters
Method Parameters
Name
type
Description
select
string[]
List of fields that should be filled in the contacts in the selection.
You can use masks in the selection:
'*'
— to select all fields (excluding custom and multiple fields)
'UF_*'
— to select all custom fields (excluding multiple fields)
There are no masks for selecting multiple fields. To select multiple fields, specify the required ones in the selection list (
PHONE
,
EMAIL
, etc.).
You can find the list of available fields for selection using the method
crm.contact.fields
.
By default, all fields are taken —
'*'
+ Custom fields —
'UF_*'
filter
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
— the name of the field by which the selection of elements will be filtered
value_n
— the filter value
You can add a prefix to the keys
field_n
to clarify the filter operation.
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
— equals, exact match (used by default)
!=
— not equal
!
— not equal
The fields Phone (
PHONE
), Email (
EMAIL
), Website (
WEB
), Messengers (
IM
), Links (
LINK
) — are multiple. Filters for them only work on exact matches.
Also, the
LIKE
filter does not work with fields of type
crm_status
,
crm_contact
,
crm_company
— for example, Contact Type (
TYPE_ID
), Salutation (
HONORIFIC
), etc.
You can find the list of available fields for filtering using the method
crm.contact.fields
.
The
logic
key in the filter is not supported. To use complex logic in the filter, use the method
crm.item.list
order
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
— the name of the field by which the selection of contacts will be sorted
value_n
— a
string
value equal to:
ASC
— ascending sort
DESC
— descending sort
You can find the list of available fields for sorting using the method
crm.contact.fields
start
integer
Parameter for managing pagination.
The page size of results is always static — 50 records.
To select the second page of results, pass the value
50
. To select the third page of results — the value
100
, and so on.
The formula for calculating the value of the
start
parameter:
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
Get a list of contacts where:
the source is CRM Form
first name and last name are not empty
first name or last name starts with "I"
are participating in the export
e-mail equals 'special-for@example.com'
the responsible person's ID is either 1 or 6
created less than 6 months ago
Set the order of sorting the selection: first name and last name in ascending order.
For clarity, select only the necessary fields:
Contact ID
First Name
Last Name
E-mail
Participating in export
Responsible
Creation Date
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
'{"FILTER":{"SOURCE_ID":"CRM_FORM","!=NAME":"","!=LAST_NAME":"","=%NAME":"I%","=%LAST_NAME":"I%","EMAIL":"special-for@example.com","@ASSIGNED_BY_ID":[1,6],"IMPORT":"Y",">=DATE_CREATE":"**put_six_month_ago_date_here**"},"ORDER":{"LAST_NAME":"ASC","NAME":"ASC"},"SELECT":["ID","NAME","LAST_NAME","EMAIL","EXPORT","ASSIGNED_BY_ID","DATE_CREATE"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"FILTER":{"SOURCE_ID":"CRM_FORM","!=NAME":"","!=LAST_NAME":"","=%NAME":"I%","=%LAST_NAME":"I%","EMAIL":"special-for@example.com","@ASSIGNED_BY_ID":[1,6],"IMPORT":"Y",">=DATE_CREATE":"**put_six_month_ago_date_here**"},"ORDER":{"LAST_NAME":"ASC","NAME":"ASC"},"SELECT":["ID","NAME","LAST_NAME","EMAIL","EXPORT","ASSIGNED_BY_ID","DATE_CREATE"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
const
sixMonthAgo =
new
Date
();
sixMonthAgo.
setMonth
(
new
Date
().
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
'crm.contact.list'
,
{
filter
: {
"SOURCE_ID"
:
"CRM_FORM"
,
"!=NAME"
:
""
,
"!=LAST_NAME"
:
""
,
"=%NAME"
:
"I%"
,
"=%LAST_NAME"
:
"I%"
,
"EMAIL"
:
"special-for@example.com"
,
"@ASSIGNED_BY_ID"
: [
1
,
6
],
"IMPORT"
:
"Y"
,
">=DATE_CREATE"
: sixMonthAgo.
toISOString
(),
},
order
: {
LAST_NAME
:
"ASC"
,
NAME
:
"ASC"
,
},
select
: [
"ID"
,
"NAME"
,
"LAST_NAME"
,
"EMAIL"
,
"EXPORT"
,
"ASSIGNED_BY_ID"
,
"DATE_CREATE"
,
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
}
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
sixMonthAgo =
new
Date
();
sixMonthAgo.
setMonth
(
new
Date
().
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
'crm.contact.list'
, {
filter
: {
"SOURCE_ID"
:
"CRM_FORM"
,
"!=NAME"
:
""
,
"!=LAST_NAME"
:
""
,
"=%NAME"
:
"I%"
,
"=%LAST_NAME"
:
"I%"
,
"EMAIL"
:
"special-for@example.com"
,
"@ASSIGNED_BY_ID"
: [
1
,
6
],
"IMPORT"
:
"Y"
,
">=DATE_CREATE"
: sixMonthAgo.
toISOString
(),
},
order
: {
LAST_NAME
:
"ASC"
,
NAME
:
"ASC"
,
},
select
: [
"ID"
,
"NAME"
,
"LAST_NAME"
,
"EMAIL"
,
"EXPORT"
,
"ASSIGNED_BY_ID"
,
"DATE_CREATE"
,
],
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
sixMonthAgo =
new
Date
();
sixMonthAgo.
setMonth
(
new
Date
().
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
'crm.contact.list'
, {
filter
: {
"SOURCE_ID"
:
"CRM_FORM"
,
"!=NAME"
:
""
,
"!=LAST_NAME"
:
""
,
"=%NAME"
:
"I%"
,
"=%LAST_NAME"
:
"I%"
,
"EMAIL"
:
"special-for@example.com"
,
"@ASSIGNED_BY_ID"
: [
1
,
6
],
"IMPORT"
:
"Y"
,
">=DATE_CREATE"
: sixMonthAgo.
toISOString
(),
},
order
: {
LAST_NAME
:
"ASC"
,
NAME
:
"ASC"
,
},
select
: [
"ID"
,
"NAME"
,
"LAST_NAME"
,
"EMAIL"
,
"EXPORT"
,
"ASSIGNED_BY_ID"
,
"DATE_CREATE"
,
],
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
$sixMonthAgo
=
new
DateTime
();
$sixMonthAgo
->
setDate
((
new
DateTime
())->
getMonth
() -
6
);
$response
=
$b24Service
->core
->
call
(
'crm.contact.list'
,
[
'filter'
=> [
'SOURCE_ID'
=>
'CRM_FORM'
,
'!=NAME'
=>
''
,
'!=LAST_NAME'
=>
''
,
'=%NAME'
=>
'I%'
,
'=%LAST_NAME'
=>
'I%'
,
'EMAIL'
=>
'special-for@example.com'
,
'@ASSIGNED_BY_ID'
=> [
1
,
6
],
'IMPORT'
=>
'Y'
,
'>=DATE_CREATE'
=>
$sixMonthAgo
->
format
(
'Y-m-d\TH:i:s'
),
],
'order'
=> [
'LAST_NAME'
=>
'ASC'
,
'NAME'
=>
'ASC'
,
],
'select'
=> [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'EMAIL'
,
'EXPORT'
,
'ASSIGNED_BY_ID'
,
'DATE_CREATE'
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
'Error fetching contact list: '
.
$e
->
getMessage
();
}
const
sixMonthAgo =
new
Date
();
sixMonthAgo.
setMonth
((
new
Date
()).
getMonth
() -
6
);
BX24
.
callMethod
(
'crm.contact.list'
,
{
filter
: {
"SOURCE_ID"
:
"CRM_FORM"
,
"!=NAME"
:
""
,
"!=LAST_NAME"
:
""
,
"=%NAME"
:
"I%"
,
"=%LAST_NAME"
:
"I%"
,
"EMAIL"
:
"special-for@example.com"
,
"@ASSIGNED_BY_ID"
: [
1
,
6
],
"IMPORT"
:
"Y"
,
">=DATE_CREATE"
: sixMonthAgo.
toISOString
(),
},
order
: {
LAST_NAME
:
"ASC"
,
NAME
:
"ASC"
,
},
select
: [
"ID"
,
"NAME"
,
"LAST_NAME"
,
"EMAIL"
,
"EXPORT"
,
"ASSIGNED_BY_ID"
,
"DATE_CREATE"
,
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
$sixMonthAgo
=
new
DateTime
();
$sixMonthAgo
->
modify
(
'-6 months'
);
$result
=
CRest
::
call
(
'crm.contact.list'
,
[
'FILTER'
=> [
'SOURCE_ID'
=>
'CRM_FORM'
,
'!=NAME'
=>
''
,
'!=LAST_NAME'
=>
''
,
'=%NAME'
=>
'I%'
,
'=%LAST_NAME'
=>
'I%'
,
'EMAIL'
=>
'special-for@example.com'
,
'@ASSIGNED_BY_ID'
=> [
1
,
6
],
'IMPORT'
=>
'Y'
,
'>=DATE_CREATE'
=>
$sixMonthAgo
->
format
(
DateTime
::
ATOM
),
],
'ORDER'
=> [
'LAST_NAME'
=>
'ASC'
,
'NAME'
=>
'ASC'
,
],
'SELECT'
=> [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'EMAIL'
,
'EXPORT'
,
'ASSIGNED_BY_ID'
,
'DATE_CREATE'
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
[
{
"ID"
:
"75"
,
"NAME"
:
"Anastasia"
,
"LAST_NAME"
:
"Ilyina"
,
"EXPORT"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"6"
,
"DATE_CREATE"
:
"2024-02-26T00:00:00+02:00"
,
"EMAIL"
:
[
{
"ID"
:
"215"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"special-for@example.com"
,
"TYPE_ID"
:
"EMAIL"
}
]
}
,
{
"ID"
:
"74"
,
"NAME"
:
"Artem"
,
"LAST_NAME"
:
"Isaev"
,
"EXPORT"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"1"
,
"DATE_CREATE"
:
"2024-08-15T00:00:00+02:00"
,
"EMAIL"
:
[
{
"ID"
:
"214"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"special-for@example.com"
,
"TYPE_ID"
:
"EMAIL"
}
]
}
,
{
"ID"
:
"78"
,
"NAME"
:
"Artem"
,
"LAST_NAME"
:
"Isaev"
,
"EXPORT"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"1"
,
"DATE_CREATE"
:
"2024-08-15T00:00:00+02:00"
,
"EMAIL"
:
[
{
"ID"
:
"218"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"special-for@example.com"
,
"TYPE_ID"
:
"EMAIL"
}
]
}
,
{
"ID"
:
"77"
,
"NAME"
:
"Inna"
,
"LAST_NAME"
:
"Kuznetsova"
,
"EXPORT"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"6"
,
"DATE_CREATE"
:
"2024-07-01T00:00:00+02:00"
,
"EMAIL"
:
[
{
"ID"
:
"217"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"special-for@example.com"
,
"TYPE_ID"
:
"EMAIL"
}
]
}
,
{
"ID"
:
"73"
,
"NAME"
:
"Ivan"
,
"LAST_NAME"
:
"Petrov"
,
"EXPORT"
:
"Y"
,
"ASSIGNED_BY_ID"
:
"1"
,
"DATE_CREATE"
:
"2024-02-20T00:00:00+02:00"
,
"EMAIL"
:
[
{
"ID"
:
"213"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"special-for@example.com"
,
"TYPE_ID"
:
"EMAIL"
}
]
}
]
,
"total"
:
5
,
"time"
:
{
"start"
:
1723807142.916445
,
"finish"
:
1723807143.44846
,
"duration"
:
0.5320150852203369
,
"processing"
:
0.1967020034790039
,
"date_start"
:
"2024-08-16T13:19:02+02:00"
,
"date_finish"
:
"2024-08-16T13:19:03+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
contact[]
The root element of the response. An array containing information about the found contacts.
The fields of an individual contact are configured by the
select
parameter
total
integer
The total number of contacts found based on the specified conditions
next
integer
Contains the value to be passed in the next request in the
start
parameter to get the next batch of data.
The
next
parameter appears in the response if the number of elements matching your request exceeds
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
Possible Error Codes
Possible Error Codes
Code
Description
Value
-
Access denied
The user does not have permission for "Read" contacts
-
Parameter 'order' must be array
A non-array was passed to the
order
parameter
-
Parameter 'filter' must be array
A non-array was passed to the
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
Create a new contact crm.contact.add
Update Contact crm.contact.update
Get Contact by Id crm.contact.get
Delete contact crm.contact.delete
Get Contact Fields crm.contact.fields
How to Find Duplicates in CRM by Phone and Email
Copied
Was the article helpful?
Yes
No
Previous
Get contact by Id
Next
Delete contact

---

## Delete contact crm.contact.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/crm-contact-delete

Delete contact crm.contact.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete contact crm.contact.delete
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
Who can execute the method: any user with "delete" access permission for contacts
The method
crm.contact.delete
removes a contact and all associated objects.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the contact.
The identifier can be obtained using the methods
crm.contact.list
or
crm.contact.add
Code Examples
Code Examples
How to Use Examples in Documentation
Delete contact with
id = 50
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
'{"ID":50}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":50,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.delete'
,
{
id
:
50
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
'crm.contact.delete'
,
[
'id'
=>
50
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
'Error deleting contact: '
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
'crm.contact.delete'
,
{
id
:
50
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
'crm.contact.delete'
,
[
'ID'
=>
50
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
1723727109.430573
,
"finish"
:
1723727210.611973
,
"duration"
:
101.18140006065369
,
"processing"
:
100.78639197349548
,
"date_start"
:
"2024-08-15T15:05:09+02:00"
,
"date_finish"
:
"2024-08-15T15:06:50+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Root element of the response.
Returns
true
on success
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
Code
Description
Value
-
ID is not defined or invalid
The
id
parameter is not provided or the provided value is not a positive integer
-
Access denied
The user does not have permission to "Delete" the contact
ERROR_CORE
Element not found
Contact with the provided
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
Create a new contact crm.contact.add
Update Contact crm.contact.update
Get Contact by Id crm.contact.get
Get the list of contacts crm.contact.list
Get Contact Fields crm.contact.fields
Copied
Was the article helpful?
Yes
No
Previous
Get list of contacts
Next
Get contact fields

---

## Get Contact Fields crm.contact.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/crm-contact-fields

Get Contact Fields crm.contact.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Contact Fields crm.contact.fields
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a description of contact fields, including custom fields.
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
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.fields
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
https://**put_your_bitrix24_address**/rest/crm.contact.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.fields'
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
(
'Contact fields'
, result);
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
'crm.contact.fields'
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
'Contact fields: '
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
'Error fetching contact fields: '
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
"crm.contact.fields"
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
(
"Contact fields"
, result.
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
'crm.contact.fields'
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
"Last Name"
}
,
"PHOTO"
:
{
"type"
:
"file"
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
"Photo"
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
"CONTACT_TYPE"
,
"title"
:
"Contact Type"
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
"Additional Source Info"
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
"Address (line 2)"
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
"State"
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
"Available to all"
}
,
"EXPORT"
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
"Participates in contact export"
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
"Phone set"
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
"E-mail set"
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
"Open channel set"
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
"Responsible"
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
"Created by"
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
"Modified by"
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
"isDeprecated"
:
true
,
"title"
:
"Company"
}
,
"COMPANY_IDS"
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
true
,
"isDynamic"
:
false
,
"title"
:
"COMPANY_IDS"
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
"ORIGIN_VERSION"
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
"Original Version"
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
"Last Activity"
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
"Last Activity Author"
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
1715004755.782705
,
"finish"
:
1715004756.118899
,
"duration"
:
0.3361940383911133
,
"processing"
:
0.10344505310058594
,
"date_start"
:
"2024-05-06T17:12:35+03:00"
,
"date_finish"
:
"2024-05-06T17:12:36+03:00"
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
ID
integer
Contact identifier. Read-only
HONORIFIC
crm_status
Salutation.
You can get the values of the directory using the method
crm.status.list
with a filter by
ENTITY_ID=HONORIFIC
NAME
string
First Name
SECOND_NAME
string
Middle Name
LAST_NAME
string
Last Name
PHOTO
file
Photo
BIRTHDATE
date
Birthdate
TYPE_ID
crm_status
Contact Type.
You can get the values of the directory using the method
crm.status.list
with a filter by
ENTITY_ID=CONTACT_TYPE
SOURCE_ID
crm_status
Source.
You can get the values of the directory using the method
crm.status.list
with a filter by
ENTITY_ID=SOURCE
SOURCE_DESCRIPTION
string
Additional Source Info
POST
string
Position
COMMENTS
string
Comment. Supports BB codes
OPENED
char
Available to all. Possible values:
Y
— yes
N
— no
Considered in the access permission work for roles with "All Open" access level
EXPORT
char
Participates in contact export. Possible values:
Y
— yes
N
— no
HAS_PHONE
char
Is phone set. Possible values:
Y
— yes
N
— no
Read-only
HAS_EMAIL
char
Is e-mail set. Possible values:
Y
— yes
N
— no
Read-only
HAS_IMOL
char
Is open channel set. Possible values:
Y
— yes
N
— no
Read-only
ASSIGNED_BY_ID
user
Responsible
CREATED_BY_ID
user
Created by. Read-only
MODIFY_BY_ID
user
Modified by. Read-only
DATE_CREATE
datetime
Creation Date. Read-only
DATE_MODIFY
datetime
Modification Date. Read-only
COMPANY_ID
crm_company
Main company of the contact
COMPANY_IDS
crm_company
Contact association with companies. Multiple.
In the methods
crm.contact.update
and
crm.contact.add
it is used to submit an array of companies.
In the methods
crm.contact.list
and
crm.contact.get
this field is not present and you need to use
crm.contact.company.items.get
to get the list of companies
LEAD_ID
crm_lead
Identifier of the lead associated with the contact. Read-only
UTM_SOURCE
string
Advertising system (Google Ads, etc.)
UTM_MEDIUM
string
Traffic type. Possible values:
CPC
— ads
CPM
— banners
UTM_CAMPAIGN
string
Campaign identifier
UTM_CONTENT
string
Campaign content. For example, for contextual ads
UTM_TERM
string
Campaign search condition. For example, keywords for contextual advertising
LAST_ACTIVITY_TIME
datetime
Last activity date in the timeline. Read-only
LAST_ACTIVITY_BY
user
Author of the last activity in the timeline. Read-only
PHONE
crm_multifield
Phones. Multiple
EMAIL
crm_multifield
E-mail. Multiple
WEB
crm_multifield
Websites. Multiple
IM
crm_multifield
Messengers. Multiple
LINK
crm_multifield
Links. Multiple. Service field.
UF_...
Custom fields. For example,
UF_CRM_25534736
.
Depending on the account settings, contacts may have a set of custom fields of defined types.
You can add a custom field to a contact using the method
crm.contact.userfield.add
PARENT_ID_...
Relationship fields.
If there are smart processes related to contacts in the account, for each such smart process there is a field that stores the relationship between this smart process and the contact. The field itself stores the identifier of the element of that smart process.
For example, the field
PARENT_ID_153
— relationship with the smart process
entityTypeId=153
. It stores the identifier of the element of this smart process associated with the current contact
Fields for External Data Sources
If the contact was created by an external system, then:
the field
ORIGINATOR_ID
stores the string identifier of that system
the field
ORIGIN_ID
stores the string identifier of the contact in that external system
the field
ORIGIN_VERSION
stores the version of the contact data in that external system
Name
type
Description
ORIGINATOR_ID
string
Identifier of the external system that is the source of data about this contact
ORIGIN_ID
string
Identifier of the contact in the external system
ORIGIN_VERSION
string
Version of the contact data in the external system.
Used to protect data from accidental overwriting by the external system.
If the data was imported and not changed in the external system, then such data can be edited in CRM without fear that the next export will lead to data overwriting
Deprecated Fields
Address fields in the contact are deprecated and are only used for compatibility mode. To work with the address, use
requisites
.
Name
type
Description
ADDRESS
string
Address
ADDRESS_2
string
Second line of address
ADDRESS_CITY
string
City
ADDRESS_POSTAL_CODE
string
Postal Code
ADDRESS_REGION
string
Region
ADDRESS_PROVINCE
string
State
ADDRESS_COUNTRY
string
Country
ADDRESS_COUNTRY_CODE
string
Country Code
ADDRESS_LOC_ADDR_ID
location
Location Address ID
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
Create a new contact crm.contact.add
Update Contact crm.contact.update
Get Contact by Id crm.contact.get
Get the list of contacts crm.contact.list
Delete contact crm.contact.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete contact
Next
Overview of Methods

---

## Overview of Events When Working with Contacts

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/events/index

Overview of Events When Working with Contacts | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Contacts
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, updating, or deletion of contacts.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to contact events through:
outgoing webhook
application
and the method
event.bind
An example of a handler for the event is described in the article
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
Triggered
onCrmContactAdd
When a contact is created manually or via the
crm.contact.add
method
onCrmContactUpdate
When a contact is updated manually or via the
crm.contact.update
method
onCrmContactDelete
When a contact is deleted manually or via the
crm.contact.delete
method
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Custom Field
Next
When Creating a Contact

---

## Event onCrmContactAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/events/on-crm-contact-add

Event onCrmContactAdd | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmContactAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
onCrmContactAdd
will trigger when a contact is created.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMCONTACTADD"
,
"event_handler_id"
:
"11"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"89"
}
}
,
"ts"
:
"1724695689"
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
ONCRMCONTACTADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created contact.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created contact.
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
Identifier of the created contact
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
Overview of Events When Working with Contacts
Event onCrmContactUpdate
Event onCrmContactDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Updating a Contact

---

## Event onCrmContactUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/events/on-crm-contact-update

Event onCrmContactUpdate | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmContactUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The
onCrmContactUpdate
event will trigger when a contact is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMCONTACTUPDATE"
,
"event_handler_id"
:
"12"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"82"
}
}
,
"ts"
:
"1724697689"
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
Symbolic event code.
In this case —
ONCRMCONTACTUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated contact.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the updated contact.
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
Identifier of the updated contact
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
Overview of Events When Working with Contacts
Event onCrmContactAdd
Event onCrmContactDelete
Copied
Was the article helpful?
Yes
No
Previous
When Creating a Contact
Next
When Deleting a Contact

---

## Event onCrmContactDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/events/on-crm-contact-delete

Event onCrmContactDelete | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmContactDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The
onCrmContactDelete
event will trigger when a contact is deleted.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMCONTACTDELETE"
,
"event_handler_id"
:
"13"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"89"
}
}
,
"ts"
:
"1724696255"
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
ONCRMCONTACTDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted contact
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted contact.
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
Identifier of the deleted contact
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
Overview of Events When Working with Contacts
Event onCrmContactAdd
Event onCrmContactUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Updating a Contact
Next
Overview of Methods

---

## Managing Contact Cards: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/custom-form/index

Managing Contact Cards: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Managing Contact Cards: Overview of Methods
Managing Contact Cards: Overview of Methods
Connection of Contact Cards with Other Objects
Universal Methods for Managing Cards
Overview of Methods
The group of methods
crm.contact.details.configuration.*
manages the settings of the card for two views:
"General view" — the card view for all employees
"My view" — personal card settings for the employee
For each card view, sections can be configured, and within each section, a list of fields can be defined. For example, create a section "Contact Information" and display the fields "Phone" and "Email" within it. For fields that do not relate to contact information, create a different section.
Quick navigation:
all methods
User documentation:
CRM Views
Connection of Contact Cards with Other Objects
Connection of Contact Cards with Other Objects
User.
The user identifier
userId
is used when setting personal card settings. The user identifier can be obtained using the method
user.get
.
Contact Fields.
Field identifiers are used when setting visible fields in the card section. The identifiers for system and custom contact fields can be obtained using the method
crm.contact.fields
.
Universal Methods for Managing Cards
Universal Methods for Managing Cards
Alongside the methods
crm.contact.details.configuration.*
for configuring the contact card, the group of universal methods
crm.item.details.configuration.*
can also be used. The capabilities of the methods are the same; the difference may lie in the execution time of the request.
The methods
crm.item.details.configuration.*
have an additional parameter
entityTypeId
— the ID of the object type. The
entityTypeId
parameter allows the universal methods to be applied to any CRM object. To manage the contact card through the universal method, pass
entityTypeId
=
3
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: any user
Method
Description
crm.contact.details.configuration.get
Retrieves the parameters of the contact card
crm.contact.details.configuration.set
Sets the parameters of the individual card
crm.contact.details.configuration.forceCommonScopeForAll
Sets a common card for all users
crm.contact.details.configuration.reset
Resets the card parameters
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Contact
Next
Get Card Parameters

---

## Get Parameters of crm.contact.details.configuration.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/custom-form/crm-contact-details-configuration-get

Get Parameters of crm.contact.details.configuration.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Parameters of crm.contact.details.configuration.get
Method Parameters
Code Examples
Response Handling
Returned Values
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method:
Any user has the right to access their own and shared settings
Only an administrator has the right to access others' settings
The method retrieves the settings for contact cards: it reads the personal settings of the specified user or the shared settings defined for all users.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
scope
string
The scope of the settings.
Possible values:
P
— personal settings
C
— shared settings
Default —
P
userId
user
User identifier. Required only when requesting someone else's personal settings.
If not specified, the current user is taken
Code Examples
Code Examples
How to Use Examples in Documentation
Get personal card configuration
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
'{"scope":"P","userId":6}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.details.configuration.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"scope":"P","userId":6,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.details.configuration.get
BX24
.
callMethod
(
'crm.contact.details.configuration.get'
,
{
scope
:
"P"
,
userId
:
6
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
'crm.contact.details.configuration.get'
,
[
'scope'
=>
'P'
,
'userId'
=>
6
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
Get shared card configuration
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
'{"scope":"C"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.details.configuration.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"scope":"C","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.details.configuration.get
BX24
.
callMethod
(
'crm.contact.details.configuration.get'
,
{
scope
:
"C"
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
'crm.contact.details.configuration.get'
,
[
'scope'
=>
'C'
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
"name"
:
"main"
,
"title"
:
"About the Contact"
,
"type"
:
"section"
,
"elements"
:
[
{
"name"
:
"LAST_NAME"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"PHOTO"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"NAME"
,
"optionFlags"
:
"1"
}
,
{
"name"
:
"SECOND_NAME"
,
"optionFlags"
:
"1"
}
,
{
"name"
:
"BIRTHDATE"
,
"optionFlags"
:
"1"
}
,
{
"name"
:
"PHONE"
,
"optionFlags"
:
"1"
,
"options"
:
{
"defaultCountry"
:
"AU"
}
}
,
{
"name"
:
"EMAIL"
,
"optionFlags"
:
"1"
}
]
}
,
{
"name"
:
"additional"
,
"title"
:
"Additional"
,
"type"
:
"section"
,
"elements"
:
[
{
"name"
:
"TYPE_ID"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"SOURCE_ID"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"OPENED"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"EXPORT"
,
"optionFlags"
:
"0"
}
,
{
"name"
:
"ASSIGNED_BY_ID"
,
"optionFlags"
:
"0"
}
]
}
]
,
"time"
:
{
"start"
:
1724677217.639681
,
"finish"
:
1724677217.986853
,
"duration"
:
0.3471717834472656
,
"processing"
:
0.01840806007385254
,
"date_start"
:
"2024-08-26T15:00:17+02:00"
,
"date_finish"
:
"2024-08-26T15:00:17+02:00"
,
"operating"
:
0
}
}
Returned Values
Returned Values
Name
type
Description
result
section[]
The root element of the response.
Contains the configuration of the sections of the detail form of the entity.
Returns
null
if there is no configuration
time
time
Information about the execution time of the request
section
section
Describes an individual section with fields inside the entity card
Name
type
Description
name
string
Unique name of the section used for identification
title
string
Title of the section
type
string
Type of the section
elements
section_element[]
List of fields displayed in the entity card with additional settings
section_element
section_element
Configuration of an individual field within the section
Name
type
Description
name
string
Field identifier
optionFlags
boolean
Whether to always show the field.
Possible values:
"1"
— yes
"0"
— no
options
object
Additional options for the field.
The structure is described
below
options
options
Name
type
Fields where the option is available
Description
defaultAddressType
integer
ADDRESS
Identifier for the default address type
defaultCountry
string
PHONE
CLIENT
COMPANY
CONTACT
MYCOMPANY_ID
Country code for the default phone number format — a string of two Latin letters.
For example
"DE"
isPayButtonVisible
boolean
OPPORTUNITY_WITH_CURRENCY
Whether the payment acceptance button is visible.
Possible values:
'true'
— visible
'false'
— hidden
isPaymentDocumentsVisible
boolean
OPPORTUNITY_WITH_CURRENCY
Whether the "Payment and Delivery" block is visible.
Possible values:
'true'
— visible
'false'
— hidden
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
Possible Error Codes
Possible Error Codes
Code
Description
Value
Empty value
Access denied.
The user does not have administrative rights
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
Managing Contact Cards: Overview of Methods
Set Parameters for Individual Card crm.contact.details.configuration.set
Set Common Contact Card for All Users crm.contact.details.configuration.forceCommonScopeForAll
Reset Contact Card Parameters crm.contact.details.configuration.reset
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Set Individual Card Parameters

---

## Set Parameters for Individual Card crm.contact.details.configuration.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/custom-form/crm-contact-details-configuration-set

Set Parameters for Individual Card crm.contact.details.configuration.set | Bitrix24 REST API and Marketplace Applications
Method Parameters
Set Parameters for Individual Card crm.contact.details.configuration.set
Method Parameters
section
Code Examples
Response Handling
Returned Values
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method:
Any user has the right to retrieve their own and common settings
Only an administrator has the right to retrieve others' settings
The method sets the contact card settings: it writes personal settings for the specified user or common settings for all users.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
scope
string
The scope of the settings.
Possible values:
P
— personal settings
C
— common settings
Default —
P
userId
user
User identifier. Required only when setting personal settings.
If not specified — takes the
id
of the current user
data
*
section[]
The list
section
describes the configuration of the field sections in the item card.
The structure is described
below
section
section
Describes a specific section with fields within the contact card.
Required parameters are marked with *
Name
type
Description
name
*
string
Unique name of the section
title
*
string
Title of the section.
Displayed in the item card
type
*
string
Type of the section.
Currently, only the value
'section'
is available
elements
section_element[]
The array
section_element
describes the configuration of fields in the section.
The structure is described
below
section_element
section_element
Configuration of a specific field within the section.
Required parameters are marked with *
Name
type
Description
name
*
string
Field identifier.
The list of available fields can be found using
crm.contact.fields
optionFlags
integer
Whether to always show the field:
1
— yes
0
— no
Default —
0
options
object
Additional
list of options
for the field
section_element.options
section_element.options
Name
type
Fields where the option is available
Description
defaultAddressType
integer
ADDRESS
Identifier of the default address type. To find possible address types, use
crm.enum.addresstype
defaultCountry
string
PHONE
CLIENT
COMPANY
CONTACT
MYCOMPANY_ID
Country code for the default phone number format — a string of two Latin letters.
For example,
"GB"
isPayButtonVisible
boolean
OPPORTUNITY_WITH_CURRENCY
Whether the payment acceptance button is shown.
Possible values:
'true'
— shown
'false'
— hidden
Default —
true
isPaymentDocumentsVisible
boolean
OPPORTUNITY_WITH_CURRENCY
Whether the "Payment and Delivery" block is shown.
Possible values:
'true'
— shown
'false'
— hidden
Default —
true
Code Examples
Code Examples
How to Use Examples in Documentation
For the user with
id = 1
, set the following configuration for the contact item card:
Section 1 —
Personal Data
First Name
Always show
Last Name
Always show
Middle Name
Date of Birth
Phone
Always show
Default country:
United Kingdom (+44)
Address
Always show
Default address type:
Registration Address
(see
crm.enum.addresstype
)
Section 2 —
Main Information
Contact Type
Source
Position
Section 3 —
Additional Information
Photo
Comment
Custom Field #1
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
'{"userId":1,"data":[{"name":"section_1","title":"Personal Data","type":"section","elements":[{"name":"NAME","optionFlags":1},{"name":"LAST_NAME","optionFlags":1},{"name":"SECOND_NAME"},{"name":"BIRTHDATE"},{"name":"PHONE","optionFlags":1,"options":{"defaultCountry":"GB"}},{"name":"ADDRESS","optionFlags":1,"options":{"defaultAddressType":4}}]},{"name":"section_2","title":"Main Information","type":"section","elements":[{"name":"TYPE_ID"},{"name":"SOURCE_ID"},{"name":"POST"}]},{"name":"section_3","title":"Additional Information","type":"section","elements":[{"name":"PHOTO"},{"name":"COMMENTS"},{"name":"UF_CRM_1720697698689"}]}]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.details.configuration.set
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"userId":1,"data":[{"name":"section_1","title":"Personal Data","type":"section","elements":[{"name":"NAME","optionFlags":1},{"name":"LAST_NAME","optionFlags":1},{"name":"SECOND_NAME"},{"name":"BIRTHDATE"},{"name":"PHONE","optionFlags":1,"options":{"defaultCountry":"GB"}},{"name":"ADDRESS","optionFlags":1,"options":{"defaultAddressType":4}}]},{"name":"section_2","title":"Main Information","type":"section","elements":[{"name":"TYPE_ID"},{"name":"SOURCE_ID"},{"name":"POST"}]},{"name":"section_3","title":"Additional Information","type":"section","elements":[{"name":"PHOTO"},{"name":"COMMENTS"},{"name":"UF_CRM_1720697698689"}]}],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.details.configuration.set
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.details.configuration.set'
,
{
userId
:
1
,
data
: [
{
name
:
"section_1"
,
title
:
"Personal Data"
,
type
:
"section"
,
elements
: [
{
name
:
"NAME"
,
optionFlags
:
1
,
},
{
name
:
"LAST_NAME"
,
optionFlags
:
1
,
},
{
name
:
"SECOND_NAME"
,
},
{
name
:
"BIRTHDATE"
,
},
{
name
:
"PHONE"
,
optionFlags
:
1
,
options
: {
defaultCountry
:
"GB"
,
},
},
{
name
:
"ADDRESS"
,
optionFlags
:
1
,
options
: {
defaultAddressType
:
4
,
},
},
],
},
{
name
:
"section_2"
,
title
:
"Main Information"
,
type
:
"section"
,
elements
: [
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
"POST"
},
],
},
{
name
:
"section_3"
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
: [
{
name
:
"PHOTO"
},
{
name
:
"COMMENTS"
},
{
name
:
"UF_CRM_1720697698689"
},
],
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
'crm.contact.details.configuration.set'
,
[
'userId'
=>
1
,
'data'
=> [
[
'name'
=>
"section_1"
,
'title'
=>
"Personal Data"
,
'type'
=>
"section"
,
'elements'
=> [
[
'name'
=>
"NAME"
,
'optionFlags'
=>
1
,
],
[
'name'
=>
"LAST_NAME"
,
'optionFlags'
=>
1
,
],
[
'name'
=>
"SECOND_NAME"
,
],
[
'name'
=>
"BIRTHDATE"
,
],
[
'name'
=>
"PHONE"
,
'optionFlags'
=>
1
,
'options'
=> [
'defaultCountry'
=>
"GB"
,
],
],
[
'name'
=>
"ADDRESS"
,
'optionFlags'
=>
1
,
'options'
=> [
'defaultAddressType'
=>
4
,
],
],
],
],
[
'name'
=>
"section_2"
,
'title'
=>
"Main Information"
,
'type'
=>
"section"
,
'elements'
=> [
[
'name'
=>
"TYPE_ID"
],
[
'name'
=>
"SOURCE_ID"
],
[
'name'
=>
"POST"
],
],
],
[
'name'
=>
"section_3"
,
'title'
=>
"Additional Information"
,
'type'
=>
"section"
,
'elements'
=> [
[
'name'
=>
"PHOTO"
],
[
'name'
=>
"COMMENTS"
],
[
'name'
=>
"UF_CRM_1720697698689"
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
'Error setting contact details configuration: '
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
'crm.contact.details.configuration.set'
,
{
userId
:
1
,
data
: [
{
name
:
"section_1"
,
title
:
"Personal Data"
,
type
:
"section"
,
elements
: [
{
name
:
"NAME"
,
optionFlags
:
1
,
},
{
name
:
"LAST_NAME"
,
optionFlags
:
1
,
},
{
name
:
"SECOND_NAME"
,
},
{
name
:
"BIRTHDATE"
,
},
{
name
:
"PHONE"
,
optionFlags
:
1
,
options
: {
defaultCountry
:
"GB"
,
},
},
{
name
:
"ADDRESS"
,
optionFlags
:
1
,
options
: {
defaultAddressType
:
4
,
},
},
],
},
{
name
:
"section_2"
,
title
:
"Main Information"
,
type
:
"section"
,
elements
: [
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
"POST"
},
],
},
{
name
:
"section_3"
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
: [
{
name
:
"PHOTO"
},
{
name
:
"COMMENTS"
},
{
name
:
"UF_CRM_1720697698689"
},
],
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
'crm.contact.details.configuration.set'
,
[
'userId'
=>
1
,
'data'
=> [
[
'name'
=>
'section_1'
,
'title'
=>
'Personal Data'
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
'NAME'
,
'optionFlags'
=>
1
,
],
[
'name'
=>
'LAST_NAME'
,
'optionFlags'
=>
1
,
],
[
'name'
=>
'SECOND_NAME'
,
],
[
'name'
=>
'BIRTHDATE'
,
],
[
'name'
=>
'PHONE'
,
'optionFlags'
=>
1
,
'options'
=> [
'defaultCountry'
=>
'GB'
,
],
],
[
'name'
=>
'ADDRESS'
,
'optionFlags'
=>
1
,
'options'
=> [
'defaultAddressType'
=>
4
,
],
],
],
],
[
'name'
=>
'section_2'
,
'title'
=>
'Main Information'
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
'POST'
],
],
],
[
'name'
=>
'section_3'
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
'PHOTO'
],
[
'name'
=>
'COMMENTS'
],
[
'name'
=>
'UF_CRM_1720697698689'
],
],
],
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
1724677217.639681
,
"finish"
:
1724677217.986853
,
"duration"
:
0.3471717834472656
,
"processing"
:
0.01840806007385254
,
"date_start"
:
"2024-08-26T15:00:17+02:00"
,
"date_finish"
:
"2024-08-26T15:00:17+02:00"
,
"operating"
:
0
}
}
Returned Values
Returned Values
Name
type
Description
result
boolean
Root element of the response.
Returns
true
on success
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
""
,
"error_description"
:
"Element at index 0 in section at index 1 does not have name."
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
Empty value
Access denied.
The user does not have administrative rights
Empty value
Parameter 'data' must be array.
A non-array was passed in
data
Empty value
The data must be indexed array.
A non-indexed array was passed in
data
Empty value
There are no data to write.
An empty array was passed in
data
Empty value
Section at index
i
has type
data[i].type
. The expected type is 'section'.
The value in
data[i].type
is different from
'section'
Empty value
Section at index
i
does not have name.
An empty value was passed in
data[i].name
Empty value
Section at index
i
does not have title.
An empty value was passed in
data[i].title
Empty value
Element at index
j
in section at index
i
does not have name.
An empty value was passed in
data[i].elements[j].name
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
Managing Contact Cards: Overview of Methods
Get Parameters of crm.contact.details.configuration.get
Set Common Contact Card for All Users crm.contact.details.configuration.forceCommonScopeForAll
Reset Contact Card Parameters crm.contact.details.configuration.reset
Copied
Was the article helpful?
Yes
No
Previous
Get Card Parameters
Next
Set Common Card for All Users

---

## Set Common Contact Card for All Users crm.contact.details.configuration.forceCommonScopeForAll

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/custom-form/crm-contact-details-configuration-force-common-scope-for-all

Set Common Contact Card for All Users crm.contact.details.configuration.forceCommonScopeForAll | Bitrix24 REST API and Marketplace Applications
Code Examples
Set Common Contact Card for All Users crm.contact.details.configuration.forceCommonScopeForAll
Code Examples
Response Handling
Returned Values
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: Administrator
This method allows you to forcibly set a common contact card for all users.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.details.configuration.forceCommonScopeForAll
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
https://**put_your_bitrix24_address**/rest/crm.contact.details.configuration.forceCommonScopeForAll
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.details.configuration.forceCommonScopeForAll'
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
$response
=
$b24Service
->core
->
call
(
'crm.contact.details.configuration.forceCommonScopeForAll'
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
'Error calling crm.contact.details.configuration.forceCommonScopeForAll: '
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
'crm.contact.details.configuration.forceCommonScopeForAll'
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
'crm.contact.details.configuration.forceCommonScopeForAll'
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
true
,
"time"
:
{
"start"
:
1724671860.18392
,
"finish"
:
1724671860.843895
,
"duration"
:
0.6599750518798828
,
"processing"
:
0.09691596031188965
,
"date_start"
:
"2024-08-26T13:31:00+02:00"
,
"date_finish"
:
"2024-08-26T13:31:00+02:00"
,
"operating"
:
0
}
}
Returned Values
Returned Values
Name
type
Description
result
boolean
Root element of the response.
Returns
true
on success
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
Possible Error Codes
Possible Error Codes
Code
Description
Value
Empty value
Access denied.
The user does not have administrative rights
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
Managing Contact Cards: Overview of Methods
Get Parameters of crm.contact.details.configuration.get
Set Parameters for Individual Card crm.contact.details.configuration.set
Reset Contact Card Parameters crm.contact.details.configuration.reset
Copied
Was the article helpful?
Yes
No
Previous
Set Individual Card Parameters
Next
Reset Card Parameters

---

## Reset Contact Card Parameters crm.contact.details.configuration.reset

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/custom-form/crm-contact-details-configuration-reset

Reset Contact Card Parameters crm.contact.details.configuration.reset | Bitrix24 REST API and Marketplace Applications
Method Parameters
Reset Contact Card Parameters crm.contact.details.configuration.reset
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
Any user has the right to retrieve their own and common settings
Only an administrator has the right to retrieve others' settings
This method resets the contact card settings: it removes the personal settings of the specified user or the common settings defined for all users.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
scope
string
The scope of the settings.
Possible values:
P
— personal settings
C
— common settings
Default —
P
userId
user
User identifier. Required only when resetting personal settings.
If not specified, the
id
of the current user is used
Code Examples
Code Examples
How to Use Examples in Documentation
Reset Common Configuration
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
'{"scope":"C"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.details.configuration.reset
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"scope":"C","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.details.configuration.reset
BX24
.
callMethod
(
'crm.contact.details.configuration.reset'
,
{
scope
:
"C"
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
'crm.contact.details.configuration.reset'
,
[
'scope'
=>
'C'
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
Reset Personal Configuration
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
'{"scope":"P","userId":6}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.details.configuration.reset
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"scope":"P","userId":6,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.details.configuration.reset
BX24
.
callMethod
(
'crm.contact.details.configuration.reset'
,
{
scope
:
"P"
,
userId
:
6
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
'crm.contact.details.configuration.reset'
,
[
'scope'
=>
'P'
,
'userId'
=>
6
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
1724682584.069094
,
"finish"
:
1724682584.38436
,
"duration"
:
0.31526613235473633
,
"processing"
:
0.025727033615112305
,
"date_start"
:
"2024-08-26T16:29:44+02:00"
,
"date_finish"
:
"2024-08-26T16:29:44+02:00"
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
The root element of the response.
Returns
true
in case of successful settings reset
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
Possible Error Codes
Possible Error Codes
Code
Description
Value
Empty value
Access denied.
The user does not have administrative rights
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
Managing Contact Cards: Overview of Methods
Get Parameters of crm.contact.details.configuration.get
Set Parameters for Individual Card crm.contact.details.configuration.set
Set Common Contact Card for All Users crm.contact.details.configuration.forceCommonScopeForAll
Copied
Was the article helpful?
Yes
No
Previous
Set Common Card for All Users
Next
Overview of Methods

---

