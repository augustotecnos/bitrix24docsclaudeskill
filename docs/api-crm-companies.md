---
description: 'CRM Companies API: CRUD operations, fields, events, communication'
methods:
- crm.activity.
- crm.address.
- crm.company.add
- crm.company.contact.
- crm.company.contact.add
- crm.company.contact.delete
- crm.company.contact.fields
- crm.company.contact.items.delete
- crm.company.contact.items.get
- crm.company.contact.items.set
- crm.company.delete
- crm.company.details.configuration.
- crm.company.details.configuration.forceCommonScopeForAll
- crm.company.details.configuration.get
- crm.company.details.configuration.reset
- crm.company.details.configuration.set
- crm.company.fields
- crm.company.get
- crm.company.list
- crm.company.update
- crm.company.userfield.
- crm.company.userfield.add
- crm.company.userfield.delete
- crm.company.userfield.get
- crm.company.userfield.list
- crm.company.userfield.update
- crm.company.userfield.updates
- crm.requisite.
- crm.timeline.
- crm.userfield.fields
pages: 34
title: 'CRM Companies API: CRUD operations, fields, events, communication'
---
# CRM Companies API: CRUD operations, fields, events, communication
> CRM Companies API: CRUD operations, fields, events, communication
> **34 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Companies in CRM: Overview of Methods](#companies-in-crm-overview-of-methods)
- [Create a New Company crm.company.add](#create-a-new-company-crmcompanyadd)
- [Delete company crm.company.delete](#delete-company-crmcompanydelete)
- [Get Company Fields Description crm.company.fields](#get-company-fields-description-crmcompanyfields)
- [Get Company Information crm.company.get](#get-company-information-crmcompanyget)
- [Get a list of companies by filter crm.company.list](#get-a-list-of-companies-by-filter-crmcompanylist)
- [Update an Existing Company crm.company.update](#update-an-existing-company-crmcompanyupdate)
- [Company Contacts: Overview of Methods](#company-contacts-overview-of-methods)
- [Add contact to the specified company crm.company.contact.add](#add-contact-to-the-specified-company-crmcompanycon)
- [Delete Contact from Specified Company crm.company.contact.delete](#delete-contact-from-specified-company-crmcompanyco)
- [Get Field Descriptions for Company-Contact crm.company.contact.fields](#get-field-descriptions-for-company-contact-crmcomp)
- [Clear the set of contacts associated with the specified company crm.company.contact.items.delete](#clear-the-set-of-contacts-associated-with-the-spec)
- [Get a set of contacts associated with the specified company crm.company.contact.items.get](#get-a-set-of-contacts-associated-with-the-specifie)
- [Set a set of contacts associated with the specified company crm.company.contact.items.set](#set-a-set-of-contacts-associated-with-the-specifie)
- [Custom Company Fields: Overview of Methods](#custom-company-fields-overview-of-methods)
- [Create a new custom field for companies crm.company.userfield.add](#create-a-new-custom-field-for-companies-crmcompany)
- [Delete custom field for companies crm.company.userfield.delete](#delete-custom-field-for-companies-crmcompanyuserfi)
- [Get Company User Field by ID crm.company.userfield.get](#get-company-user-field-by-id-crmcompanyuserfieldge)
- [Get a list of custom company fields by filter crm.company.userfield.list](#get-a-list-of-custom-company-fields-by-filter-crmc)
- [Update Existing User Field for Companies crm.company.userfield.update](#update-existing-user-field-for-companies-crmcompan)
- [Overview of Events When Working with Company User Fields](#overview-of-events-when-working-with-company-user-)
- [When Adding a Custom Field onCrmCompanyUserFieldAdd](#when-adding-a-custom-field-oncrmcompanyuserfieldad)
- [When Deleting a Custom Field onCrmCompanyUserFieldDelete](#when-deleting-a-custom-field-oncrmcompanyuserfield)
- [When setting list values for the custom field onCrmCompanyUserFieldSetEnumValues](#when-setting-list-values-for-the-custom-field-oncr)
- [When updating a custom field onCrmCompanyUserFieldUpdate](#when-updating-a-custom-field-oncrmcompanyuserfield)
- [Overview of Events When Working with Companies](#overview-of-events-when-working-with-companies)
- [Event on creating a company onCrmCompanyAdd](#event-on-creating-a-company-oncrmcompanyadd)
- [Event onCrmCompanyDelete](#event-oncrmcompanydelete)
- [Event on Company Update onCrmCompanyUpdate](#event-on-company-update-oncrmcompanyupdate)
- [Managing Company Cards: Overview of Methods](#managing-company-cards-overview-of-methods)
- [Get parameters for crm.company.details.configuration.get](#get-parameters-for-crmcompanydetailsconfigurationg)
- [Reset Company Card Settings crm.company.details.configuration.reset](#reset-company-card-settings-crmcompanydetailsconfi)
- [Set Parameters for the CRM Company Detail Card crm.company.details.configuration.set](#set-parameters-for-the-crm-company-detail-card-crm)
- [Set a common company card for all users crm.company.details.configuration.forceCommonScopeForAll](#set-a-common-company-card-for-all-users-crmcompany)

---

## Companies in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/index

Companies in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Companies in CRM: Overview of Methods
Companies in CRM: Overview of Methods
Company Connection with Other CRM Objects
Company Card
Widgets
Overview of Methods and Events
Main
Custom Fields
Contacts
Managing Company Cards
A company is a CRM object that stores client data for legal entities. The company card contains:
phone numbers, email addresses, and messenger identifiers in a special format. These allow direct communication with the client from Bitrix.
details for generating invoices, contracts, and any other types of printed documents based on templates.
Quick navigation:
all methods and events
User documentation:
companies in Bitrix24
Company Connection with Other CRM Objects
Company Connection with Other CRM Objects
Deal, lead, SPA.
Any CRM object that has the standard field
Client
is linked to a company. The connection is managed through groups of methods for
deals
,
leads
,
SPAs
, using the
COMPANY_ID
field.
Contact.
Multiple contacts can be associated with a single company. This connection is managed using the group of methods
crm.company.contact.*
. When you select a company in the
Client
field of deals or SPAs, all related contacts are automatically pulled into the field.
Details.
The details themselves are a separate object, and methods from the group
crm.requisite.*
and
crm.address.*
are used to create or modify them. They are displayed in the
Details
field of the company card.
User Documentation
Connection between deals, contacts, and companies
Connections of details with CRM objects
Changes in working with addresses and details in CRM
Company Card
Company Card
The main workspace in a company is the General tab of its card. It consists of two parts:
the left part, which contains fields with information. If the system fields are insufficient, you can create your own custom fields. These allow you to store information in various data formats: string, number, link, address, and others. The group of methods
crm.company.userfield.*
is used to create, modify, retrieve, or delete custom fields for companies.
the right part, which contains the contact timeline. In it, you can create, edit, filter, and delete CRM activities using the group of methods
crm.activity.*
, and timeline records using the group of methods
crm.timeline.*
.
The parameters of the company card can be managed through the group of methods
crm.company.details.configuration.*
.
User Documentation
CRM Card: Features and Settings
System Fields in CRM
Custom Fields in CRM
Timeline in CRM Entity
Widgets
Widgets
You can embed an application into the company card. This allows you to use the application without leaving the company card.
There are two embedding scenarios:
Use special
embedding locations
. For example, by creating your own tab.
Create a
custom field
where the interface of your application will be loaded.
Typical use-cases and scenarios
Widget Embedding Mechanism
Embed a Widget in the CRM Card
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can execute methods: depending on the method
Main
Main
Methods
Events
Method
Description
crm.company.add
Creates a new company
crm.company.update
Updates an existing company
crm.company.get
Returns a company by ID
crm.company.list
Returns a list of companies by filter
crm.company.delete
Deletes a company and all related objects
crm.company.fields
Returns the description of company fields
Event
Triggered
onCrmCompanyAdd
when a company is created
onCrmCompanyUpdate
when a company is updated
onCrmCompanyDelete
when a company is deleted
Custom Fields
Custom Fields
Methods
Events
Method
Description
crm.company.userfield.add
Creates a new custom field for companies
crm.company.userfield.update
Updates an existing custom field for companies
crm.company.userfield.get
Returns a custom field for companies by ID
crm.company.userfield.list
Returns a list of custom fields for companies by filter
crm.company.userfield.delete
Deletes a custom field for companies
Event
Triggered
onCrmCompanyUserFieldAdd
when a custom field is added
onCrmCompanyUserFieldUpdate
when a custom field is modified
onCrmCompanyUserFieldDelete
when a custom field is deleted
onCrmCompanyUserFieldSetEnumValues
when the set of values for a custom field of list type is changed
Contacts
Contacts
Method
Description
crm.company.contact.add
Adds a contact to the specified company
crm.company.contact.items.get
Returns a set of contacts associated with the specified company
crm.company.contact.items.set
Sets the set of contacts associated with the specified company
crm.company.contact.delete
Deletes a contact from the specified company
crm.company.contact.items.delete
Clears the set of contacts associated with the specified company
crm.company.contact.fields
Returns the description of fields for the company-contact connection
Managing Company Cards
Managing Company Cards
Method
Description
crm.company.details.configuration.get
Retrieves the settings for company cards
crm.company.details.configuration.reset
Resets the settings for company cards
crm.company.details.configuration.set
Sets the settings for company cards
crm.company.details.configuration.forceCommonScopeForAll
Allows forcing a common company card for all users
Copied
Was the article helpful?
Yes
No
Previous
Reset Card Parameters
Next
Create a New Company

---

## Create a New Company crm.company.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/crm-company-add

Create a New Company crm.company.add | Bitrix24 REST API and Marketplace Applications
Create a New Company crm.company.add
Create a New Company crm.company.add
Parameters
Examples
Continue Learning
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.add
creates a new company.
Parameters
Parameters
Parameter
Description
fields
array
Set of fields - an array in the form array("field"=>"value"[, ...]), containing the values of the company fields.
Note
To find out the required format of the fields, execute the method
crm.company.fields
and check the format of the received values for these fields.
params
array
Set of parameters. REGISTER_SONET_EVENT - register the event of adding a company in the live feed. A notification will also be sent to the person responsible for the company.
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
"crm.company.add"
,
{
fields
:
{
"TITLE"
:
"LLC Smith"
,
"COMPANY_TYPE"
:
"CUSTOMER"
,
"INDUSTRY"
:
"MANUFACTURING"
,
"EMPLOYEES"
:
"EMPLOYEES_2"
,
"CURRENCY_ID"
:
"USD"
,
"REVENUE"
:
3000000
,
"LOGO"
: {
"fileData"
:
document
.
getElementById
(
'logo'
) },
"OPENED"
:
"Y"
,
"ASSIGNED_BY_ID"
:
1
,
"PHONE"
: [ {
"VALUE"
:
"555888"
,
"VALUE_TYPE"
:
"WORK"
} ]
},
params
: {
"REGISTER_SONET_EVENT"
:
"Y"
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
"Company created with ID "
+ result);
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
'crm.company.add'
,
[
'fields'
=> [
'TITLE'
=>
'LLC Smith'
,
'COMPANY_TYPE'
=>
'CUSTOMER'
,
'INDUSTRY'
=>
'MANUFACTURING'
,
'EMPLOYEES'
=>
'EMPLOYEES_2'
,
'CURRENCY_ID'
=>
'USD'
,
'REVENUE'
=>
3000000
,
'LOGO'
=> [
'fileData'
=>
$_POST
[
'logo'
]],
'OPENED'
=>
'Y'
,
'ASSIGNED_BY_ID'
=>
1
,
'PHONE'
=> [[
'VALUE'
=>
'555888'
,
'VALUE_TYPE'
=>
'WORK'
]],
],
'params'
=> [
'REGISTER_SONET_EVENT'
=>
'Y'
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
'Company created with ID '
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
'Error creating company: '
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
"crm.company.add"
,
{
fields
:
{
"TITLE"
:
"LLC Smith"
,
"COMPANY_TYPE"
:
"CUSTOMER"
,
"INDUSTRY"
:
"MANUFACTURING"
,
"EMPLOYEES"
:
"EMPLOYEES_2"
,
"CURRENCY_ID"
:
"USD"
,
"REVENUE"
:
3000000
,
"LOGO"
: {
"fileData"
:
document
.
getElementById
(
'logo'
) },
"OPENED"
:
"Y"
,
"ASSIGNED_BY_ID"
:
1
,
"PHONE"
: [ {
"VALUE"
:
"555888"
,
"VALUE_TYPE"
:
"WORK"
} ]
},
params
: {
"REGISTER_SONET_EVENT"
:
"Y"
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
(
"Company created with ID "
+ result.
data
());
}
);
How to Use Examples in Documentation
Continue Learning
Continue Learning
Companies in CRM: Overview of Methods
Add a Company via Web Form
Add a Company with Details via Web Form
Add a deal and company with requisites
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Delete a Company

---

## Delete company crm.company.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/crm-company-delete

Delete company crm.company.delete | Bitrix24 REST API and Marketplace Applications
Parameters
Delete company crm.company.delete
Parameters
Examples
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.delete
removes a company and all associated objects.
Parameters
Parameters
Parameter
Description
id
unknown
Company identifier.
Examples
Examples
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
"crm.company.delete"
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
'crm.company.delete'
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
'Error deleting company: '
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
"crm.company.delete"
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
Create a New Company
Next
Get Company Field Descriptions

---

## Get Company Fields Description crm.company.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/crm-company-fields

Get Company Fields Description crm.company.fields | Bitrix24 REST API and Marketplace Applications
Get Company Fields Description crm.company.fields
Get Company Fields Description crm.company.fields
Parameters
Examples
Fields
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.fields
returns the description of
company fields
, including
custom fields
.
Parameters
Parameters
No parameters.
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
'crm.company.fields'
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
'crm.company.fields'
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
'Error fetching company fields: '
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
"crm.company.fields"
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
Fields
Fields
Field
Description
Note
ADDRESS
string
Company address
ADDRESS_2
string
Second line of the address
In some countries, it is customary to split the address into 2 parts
ADDRESS_CITY
string
City
ADDRESS_COUNTRY
string
Country
ADDRESS_COUNTRY_CODE
string
Country code
ADDRESS_LEGAL
string
ADDRESS_POSTAL_CODE
string
Postal code
ADDRESS_PROVINCE
string
Province
ADDRESS_REGION
string
Region
ASSIGNED_BY_ID
user
Linked to user by ID
BANKING_DETAILS
string
Banking details
COMMENTS
string
Comments
COMPANY_TYPE
crm_status
Company type
CREATED_BY_ID
user
Created by
Read-only
CURRENCY_ID
crm_currency
Currency
DATE_CREATE
datetime
Creation date
Read-only
DATE_MODIFY
datetime
Modification date
Read-only
EMAIL
crm_multifield
Email address
Multiple
EMPLOYEES
crm_status
Number of employees
HAS_EMAIL
char
Email field filled check
Read-only
HAS_PHONE
char
Phone field filled check
Read-only
ID
integer
Company ID
Read-only
IM
crm_multifield
Messengers
Multiple
INDUSTRY
crm_status
Industry
IS_MY_COMPANY
char
LEAD_ID
crm_lead
Lead ID associated with the company
Read-only
LOGO
file
Logo
MODIFY_BY_ID
user
ID of the last modification author
Read-only
OPENED
char
Available to everyone
ORIGINATOR_ID
string
Data source ID
Used only for linking to an external source.
ORIGIN_ID
string
Element ID in the data source
Used only for linking to an external source.
ORIGIN_VERSION
string
Original version
Used to protect data from accidental overwriting by an external system. If the data was imported and not modified in the external system, such data can be edited in CRM without fear that the next export will overwrite the data
PHONE
crm_multifield
Company phone
Multiple
REG_ADDRESS
string
Legal address of the company
Deprecated, used for compatibility.
REG_ADDRESS_2
string
Second line of the legal address
In some countries, it is customary to split the address into 2 parts. Deprecated, used for compatibility.
REG_ADDRESS_CITY
string
City of the legal address
Deprecated, used for compatibility.
REG_ADDRESS_COUNTRY
string
Country of the legal address
Deprecated, used for compatibility.
REG_ADDRESS_COUNTRY_CODE
string
Country code of the legal address
Deprecated, used for compatibility.
REG_ADDRESS_LEGAL
string
Deprecated, used for compatibility.
REG_ADDRESS_POSTAL_CODE
string
Postal code of the legal address
Deprecated, used for compatibility.
REG_ADDRESS_PROVINCE
string
Province of the legal address
Deprecated, used for compatibility.
REG_ADDRESS_REGION
string
Region of the legal address
Deprecated, used for compatibility.
REVENUE
double
Annual revenue
TITLE
string
Title
Required
UTM_CAMPAIGN
string
Advertising campaign designation
UTM_CONTENT
string
Campaign content
For example, for contextual ads.
UTM_MEDIUM
string
Traffic type
CPC (ads), CPM (banners)
UTM_SOURCE
string
Advertising system
Google-Adwords and others.
UTM_TERM
string
Campaign search term
For example, keywords for contextual advertising.
WEB
crm_multifield
Company resource URLs
Multiple
Copied
Was the article helpful?
Yes
No
Previous
Delete a Company
Next
Get Company Information

---

## Get Company Information crm.company.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/crm-company-get

Get Company Information crm.company.get | Bitrix24 REST API and Marketplace Applications
Get Company Information crm.company.get
Get Company Information crm.company.get
Parameters
Examples
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.get
returns a
company
by its identifier.
Parameters
Parameters
Parameter
Description
id
unknown
Company identifier.
Examples
Examples
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
"crm.company.get"
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
$id
=
readline
(
"Enter ID: "
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
'crm.company.get'
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
'Error getting company: '
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
"crm.company.get"
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
Get Company Field Descriptions
Next
Get List of Companies by Filter

---

## Get a list of companies by filter crm.company.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/crm-company-list

Get a list of companies by filter crm.company.list | Bitrix24 REST API and Marketplace Applications
Get a list of companies by filter crm.company.list
Get a list of companies by filter crm.company.list
Parameters
Examples
Continue exploring
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.list
returns a list of companies based on the filter. It is an implementation of the list method for companies.
When querying, use masks:
"*" - to select all fields (excluding custom and multiple fields)
"UF_*" - to select all custom fields (excluding multiple fields)
There is no mask for selecting multiple fields. To select multiple fields, specify the required ones in the selection list ("PHONE", "EMAIL", etc.).
Parameters
Parameters
See the description of
list methods
.
Examples
Examples
Searching for companies by industry and type
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
'crm.company.list'
,
{
order
: {
"DATE_CREATE"
:
"ASC"
},
filter
: {
"INDUSTRY"
:
"MANUFACTURING"
,
"COMPANY_TYPE"
:
"CUSTOMER"
},
select
: [
"ID"
,
"TITLE"
,
"CURRENCY_ID"
,
"REVENUE"
]
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
'crm.company.list'
, {
order
: {
"DATE_CREATE"
:
"ASC"
},
filter
: {
"INDUSTRY"
:
"MANUFACTURING"
,
"COMPANY_TYPE"
:
"CUSTOMER"
},
select
: [
"ID"
,
"TITLE"
,
"CURRENCY_ID"
,
"REVENUE"
]
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.company.list'
, {
order
: {
"DATE_CREATE"
:
"ASC"
},
filter
: {
"INDUSTRY"
:
"MANUFACTURING"
,
"COMPANY_TYPE"
:
"CUSTOMER"
},
select
: [
"ID"
,
"TITLE"
,
"CURRENCY_ID"
,
"REVENUE"
]
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
'crm.company.list'
,
[
'order'
=> [
'DATE_CREATE'
=>
'ASC'
],
'filter'
=> [
'INDUSTRY'
=>
'MANUFACTURING'
,
'COMPANY_TYPE'
=>
'CUSTOMER'
],
'select'
=> [
'ID'
,
'TITLE'
,
'CURRENCY_ID'
,
'REVENUE'
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
'Error fetching company list: '
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
"crm.company.list"
,
{
order
: {
"DATE_CREATE"
:
"ASC"
},
filter
: {
"INDUSTRY"
:
"MANUFACTURING"
,
"COMPANY_TYPE"
:
"CUSTOMER"
},
select
: [
"ID"
,
"TITLE"
,
"CURRENCY_ID"
,
"REVENUE"
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
Searching for a company by phone
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
'crm.company.list'
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
'crm.company.list'
, {
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
] },
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.company.list'
, {
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
] },
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
'crm.company.list'
,
[
'filter'
=> [
'PHONE'
=>
'555888'
],
'select'
=> [
'ID'
,
'TITLE'
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
'Error fetching company list: '
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
"crm.company.list"
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
Continue exploring
Continue exploring
How to Find Duplicates in CRM by Phone and Email
Copied
Was the article helpful?
Yes
No
Previous
Get Company Information
Next
Update an Existing Company

---

## Update an Existing Company crm.company.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/crm-company-update

Update an Existing Company crm.company.update | Bitrix24 REST API and Marketplace Applications
Update an Existing Company crm.company.update
Update an Existing Company crm.company.update
Parameters
Examples
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.update
updates an existing company.
Warning
It is strongly recommended to pass the complete set of address fields when updating the address in the update method. The specifics of updating address fields are described
here
.
Parameters
Parameters
Parameter
Description
id
unknown
Company identifier.
fields
unknown
Set of fields
- an array in the form array("field to update"=>"value"[, ...]), where "field to update" can take values returned by the method
crm.company.fields
.
Note
To find out the required format of the fields, execute the method
crm.company.fields
and check the format of the returned values for these fields.
params
unknown
Set of parameters.
REGISTER_SONET_EVENT
- register an event of the company change in the live feed. A notification will also be sent to the person responsible for the company.
Examples
Examples
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
"crm.company.update"
,
{
id
: id,
fields
:
{
"CURRENCY_ID"
:
"USD"
,
"REVENUE"
:
500000
,
"EMPLOYEES"
:
"EMPLOYEES_3"
},
params
: {
"REGISTER_SONET_EVENT"
:
"Y"
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
'crm.company.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'CURRENCY_ID'
=>
'USD'
,
'REVENUE'
=>
500000
,
'EMPLOYEES'
=>
'EMPLOYEES_3'
,
],
'params'
=> [
'REGISTER_SONET_EVENT'
=>
'Y'
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
'Error updating company: '
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
"crm.company.update"
,
{
id
: id,
fields
:
{
"CURRENCY_ID"
:
"USD"
,
"REVENUE"
:
500000
,
"EMPLOYEES"
:
"EMPLOYEES_3"
},
params
: {
"REGISTER_SONET_EVENT"
:
"Y"
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
info
(result.
data
());
}
}
);
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get List of Companies by Filter
Next
Overview of methods

---

## Company Contacts: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/contacts/index

Company Contacts: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Benefits of Connecting Companies and Contacts
Company Contacts: Overview of Methods
Benefits of Connecting Companies and Contacts
Overview of Methods
Using the group of methods
crm.company.contact.*
, you can manage the relationships between contacts and companies: establishing or removing connections for a contact or a group of contacts.
Quick navigation:
all methods
User documentation:
Link deals, contacts and companies
Benefits of Connecting Companies and Contacts
Benefits of Connecting Companies and Contacts
When you select a company in the
Client
field of deals or SPAs, all related contacts are automatically populated in the field.
The company detail form displays information about related contacts: name, phone number, e-mail, position.
From the company detail form, you can call or send an e-mail without navigating to the contact detail form.
When
generating documents from a template
, you can use symbolic codes that will automatically insert data from related contacts into the document.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: depending on the method
Method
Description
crm.company.contact.add
Adds a contact to the specified company
crm.company.contact.delete
Removes a contact from the specified company
crm.company.contact.fields
Returns the description of fields for the company-contact relationship
crm.company.contact.items.delete
Clears the set of contacts associated with the specified company
crm.company.contact.items.get
Returns the set of contacts associated with the specified company
crm.company.contact.items.set
Establishes the set of contacts associated with the specified company
Copied
Was the article helpful?
Yes
No
Previous
Update an Existing Company
Next
Add contact to company

---

## Add contact to the specified company crm.company.contact.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/contacts/crm-company-contact-add

Add contact to the specified company crm.company.contact.add | Bitrix24 REST API and Marketplace Applications
Parameters
Add contact to the specified company crm.company.contact.add
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.contact.add
adds a contact to the specified company.
Parameters
Parameters
Parameter
Description
id
integer
Company identifier.
fields
object
Object with the following fields:
CONTACT_ID
- contact identifier (required parameter)
SORT
- sorting index
IS_PRIMARY
- primary contact flag
Note
To find out the required format of the fields, execute the method
crm.company.fields
and check the format of the returned values for these fields.
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Remove contact from company

---

## Delete Contact from Specified Company crm.company.contact.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/contacts/crm-company-contact-delete

Delete Contact from Specified Company crm.company.contact.delete | Bitrix24 REST API and Marketplace Applications
Delete Contact from Specified Company crm.company.contact.delete
Delete Contact from Specified Company crm.company.contact.delete
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.contact.delete
removes a contact from the specified company.
Parameters
Parameters
Parameter
Description
id
unknown
Identifier of the contact.
fields
unknown
Object with the following fields:
CONTACT_ID
- identifier of the contact (required field)
Copied
Was the article helpful?
Yes
No
Previous
Add contact to company
Next
Get field descriptions

---

## Get Field Descriptions for Company-Contact crm.company.contact.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/contacts/crm-company-contact-fields

Get Field Descriptions for Company-Contact crm.company.contact.fields | Bitrix24 REST API and Marketplace Applications
Get Field Descriptions for Company-Contact crm.company.contact.fields
Get Field Descriptions for Company-Contact crm.company.contact.fields
Parameters
Examples
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.contact.fields
returns the field descriptions for the company-contact relationship, used by methods in the
crm.company.contact.*
family, such as
crm.company.contact.items.get
,
crm.company.contact.items.set
,
crm.company.contact.add
, etc.
Parameters
Parameters
No parameters.
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
'crm.company.contact.fields'
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
'crm.company.contact.fields'
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
'Error fetching company contact fields: '
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
"crm.company.contact.fields"
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
Copied
Was the article helpful?
Yes
No
Previous
Remove contact from company
Next
Clear contact set

---

## Clear the set of contacts associated with the specified company crm.company.contact.items.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/contacts/crm-company-contact-items-delete

Clear the set of contacts associated with the specified company crm.company.contact.items.delete | Bitrix24 REST API and Marketplace Applications
Clear the set of contacts associated with the specified company crm.company.contact.items.delete
Clear the set of contacts associated with the specified company crm.company.contact.items.delete
Parameters
Examples
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.contact.items.delete
clears the set of contacts associated with the specified company.
Parameters
Parameters
Parameter
Description
id
unknown
Company identifier.
Examples
Examples
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
"crm.company.contact.items.delete"
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
'crm.company.contact.items.delete'
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
'Error deleting company contact item: '
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
"crm.company.contact.items.delete"
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
Get field descriptions
Next
Get contact set

---

## Get a set of contacts associated with the specified company crm.company.contact.items.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/contacts/crm-company-contact-items-get

Get a set of contacts associated with the specified company crm.company.contact.items.get | Bitrix24 REST API and Marketplace Applications
Get a set of contacts associated with the specified company crm.company.contact.items.get
Get a set of contacts associated with the specified company crm.company.contact.items.get
Parameters
Examples
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can perform the method: any user
The method
crm.company.contact.items.get
returns a set of contacts associated with the specified company.
Parameters
Parameters
Parameter
Description
id
unknown
Company identifier.
The result is returned as an array of objects, each containing the following fields:
Field
Description
CONTACT_ID
unknown
Contact identifier
SORT
unknown
Sort index
ROLE_ID
unknown
Role identifier (reserved)
IS_PRIMARY
unknown
Primary contact flag
Examples
Examples
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
"crm.company.contact.items.get"
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
'crm.company.contact.items.get'
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
'Error getting company contact items: '
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
"crm.company.contact.items.get"
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
Clear contact set
Next
Set contact set

---

## Set a set of contacts associated with the specified company crm.company.contact.items.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/contacts/crm-company-contact-items-set

Set a set of contacts associated with the specified company crm.company.contact.items.set | Bitrix24 REST API and Marketplace Applications
Set a set of contacts associated with the specified company crm.company.contact.items.set
Set a set of contacts associated with the specified company crm.company.contact.items.set
We are still updating this page
Some data may be missing — we will complete it soon.
Scope:
crm
Who can execute the method: any user
The method
crm.company.contact.items.set
sets a set of contacts associated with the specified company.
Parameters
Parameters
Parameter
Description
id
unknown
Company identifier.
items
unknown
A set of contacts in the form of an array of objects with the following fields:
CONTACT_ID
- contact identifier (required field)
SORT
- sorting index
IS_PRIMARY
- primary contact flag
Copied
Was the article helpful?
Yes
No
Previous
Get contact set
Next
Overview of Methods

---

## Custom Company Fields: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/index

Custom Company Fields: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Types of Custom Fields
Custom Company Fields: Overview of Methods
Types of Custom Fields
Custom Field Settings
Errors When Working with Custom Fields
Common Causes of Server Errors
Overview of Methods
Custom fields store information about a company in various data formats: string, number, link, address, and others.
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
to obtain error details.
In on-premise Bitrix24, request the server error log from the server administrator or hosting administrator. Then, contact
technical support
and attach the log for analysis.
Common Causes of Server Errors
Common Causes of Server Errors
Up to 1016 custom fields can be created for companies—this is a limitation of the database architecture. If there are already 1016 fields for companies in Bitrix24, attempting to create a new field will result in an error
INTERNAL_SERVER_ERROR
when using the method
crm.company.userfield.add
.
You can check the number of custom fields for companies using the method
crm.company.userfield.list
.
There is a limitation on servers for the execution time of a single request—
max_execution_time
. The standard time is 60 seconds. If the request takes longer, it will be interrupted with an error
INTERNAL_SERVER_ERROR
.
The time to create or delete a custom field for a company depends on the number of companies. When a field is created, it is added to all company detail forms. When a field is deleted, it is removed from all detail forms. The fewer companies in your Bitrix24, the faster fields are created and deleted.
To check the number of companies in Bitrix24, use the method
crm.company.list
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: depending on the method
Method
Description
crm.company.userfield.add
Creates a new custom field for companies
crm.company.userfield.get
Returns a custom field for companies by ID
crm.company.userfield.list
Returns a list of custom fields for companies by filter
crm.company.userfield.update
Updates an existing custom field for companies
crm.company.userfield.delete
Deletes a custom field for companies
Copied
Was the article helpful?
Yes
No
Previous
Set contact set
Next
Create a New Field

---

## Create a new custom field for companies crm.company.userfield.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/crm-company-userfield-add

Create a new custom field for companies crm.company.userfield.add | Bitrix24 REST API and Marketplace Applications
Create a new custom field for companies crm.company.userfield.add
Create a new custom field for companies crm.company.userfield.add
Parameters
Examples
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can perform the method: any user
The method
crm.company.userfield.add
creates a new custom field for companies.
The system limitation on the field name is 20 characters. The custom field name always has the prefix UF_CRM_, meaning the actual length of the name is 13 characters.
Parameters
Parameters
Parameter
Description
fields
array
A set of fields - an array of the form array("field"=>"value"[, ...]), containing the description of the custom field.
LIST
unknown
Contains a set of list values for custom fields of type List. It is specified when creating/updating the field. Each value is an array with the fields:
VALUE
- the value of the list item. This field is mandatory when creating a new item.
SORT
- sorting.
DEF
- if equal to Y, the list item is the default value. For multiple fields, several DEF=Y are allowed. For non-multiple fields, the first will be considered default.
XML_ID
- external code of the value. This parameter is considered only when updating already existing values of the list item.
ID
- identifier of the value. If specified, it is considered an update of an existing list item value, not the creation of a new one. It only makes sense when calling the
*.userfield.update
methods.
DEL
- if equal to Y, the existing list item will be deleted. This is applied if the ID parameter is filled.
A complete description of the fields can be obtained by calling the method
crm.userfield.fields
.
Examples
Examples
Example #1: Creating a text field
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
"crm.company.userfield.add"
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
"Hello, world!"
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
'crm.company.userfield.add'
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
'Hello, world!'
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
'Error adding company user field: '
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
"crm.company.userfield.add"
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
"Hello, world!"
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
Example #2: Creating a list
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
"crm.company.userfield.add"
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
: [
{
"VALUE"
:
"Item #1"
},
{
"VALUE"
:
"Item #2"
},
{
"VALUE"
:
"Item #3"
},
{
"VALUE"
:
"Item #4"
},
{
"VALUE"
:
"Item #5"
}
],
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
'crm.company.userfield.add'
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
'Error adding company user field: '
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
"crm.company.userfield.add"
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
: [
{
"VALUE"
:
"Item #1"
},
{
"VALUE"
:
"Item #2"
},
{
"VALUE"
:
"Item #3"
},
{
"VALUE"
:
"Item #4"
},
{
"VALUE"
:
"Item #5"
}
],
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
Delete a Field

---

## Delete custom field for companies crm.company.userfield.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/crm-company-userfield-delete

Delete custom field for companies crm.company.userfield.delete | Bitrix24 REST API and Marketplace Applications
Delete custom field for companies crm.company.userfield.delete
Delete custom field for companies crm.company.userfield.delete
Parameters
Examples
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.userfield.delete
deletes a custom field for companies.
Parameters
Parameters
Parameter
Description
id
unknown
Identifier of the custom field.
Examples
Examples
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
"crm.company.userfield.delete"
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
'crm.company.userfield.delete'
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
"crm.company.userfield.delete"
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
Create a New Field
Next
Get a Field by ID

---

## Get Company User Field by ID crm.company.userfield.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/crm-company-userfield-get

Get Company User Field by ID crm.company.userfield.get | Bitrix24 REST API and Marketplace Applications
Get Company User Field by ID crm.company.userfield.get
Get Company User Field by ID crm.company.userfield.get
Parameters
Example
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
crm.company.userfield.get(id)
The method
crm.company.userfield.get
returns the company user field by its identifier.
Parameters
Parameters
Parameter
Description
id
unknown
Identifier of the user field.
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
"crm.company.userfield.get"
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
'crm.company.userfield.get'
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
'Error getting company user field: '
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
"crm.company.userfield.get"
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
Delete a Field
Next
Get a List of Fields by Filter

---

## Get a list of custom company fields by filter crm.company.userfield.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/crm-company-userfield-list

Get a list of custom company fields by filter crm.company.userfield.list | Bitrix24 REST API and Marketplace Applications
Get a list of custom company fields by filter crm.company.userfield.list
Get a list of custom company fields by filter crm.company.userfield.list
Parameters
Example
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.userfield.list
returns a list of custom company fields based on the filter.
Parameters
Parameters
Parameter
Description
order
array
Sorting fields.
filter
array
Filtering fields.
START
The ordinal number of the list item from which to return the next items when calling the current method. Details in the article
Features of List Methods
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
'crm.company.userfield.list'
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.company.userfield.list'
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.company.userfield.list'
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
'crm.company.userfield.list'
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
'Error fetching company user fields: '
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
"crm.company.userfield.list"
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
Get a Field by ID
Next
Update an Existing Field

---

## Update Existing User Field for Companies crm.company.userfield.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/crm-company-userfield-update

Update Existing User Field for Companies crm.company.userfield.update | Bitrix24 REST API and Marketplace Applications
Update Existing User Field for Companies crm.company.userfield.update
Update Existing User Field for Companies crm.company.userfield.update
Parameters
Example
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.userfield.update
updates an existing user field for companies.
Parameters
Parameters
Parameter
Description
id
unknown
Identifier of the user field.
fields
unknown
Set of fields - an array in the form array("field to update"=>"value"[, ...]), where "field to update" can take values returned by the method
crm.userfield.fields
.
LIST
unknown
Contains a set of list values for user fields of type List. Specified when creating/updating the field. Each value is an array with the following fields:
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
- identifier of the value. If specified, it is considered that this is an update of an existing list item value, not the creation of a new one. Makes sense only when calling
*.userfield.update
methods.
DEL
- if equal to
Y
, the existing list item will be deleted. Applied if the
ID
parameter is filled.
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
"crm.company.userfield.update"
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
$_POST
[
'id'
];
$label
=
$_POST
[
'label'
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
'crm.company.userfield.update'
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
'Error updating user field: '
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
"crm.company.userfield.update"
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
Get a List of Fields by Filter
Next
Overview of events

---

## Overview of Events When Working with Company User Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/events/index

Overview of Events When Working with Company User Fields | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Company User Fields
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, update, or deletion of company user fields.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to company user field events through:
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
Triggered
onCrmCompanyUserFieldAdd
When a user field is added manually or via the method
crm.company.userfield.add
onCrmCompanyUserFieldUpdate
When a user field is changed manually or via the method
crm.company.userfield.update
onCrmCompanyUserFieldDelete
When a user field is deleted manually or via the method
crm.company.userfield.delete
onCrmCompanyUserFieldSetEnumValues
When the set of values for a list-type user field is changed manually or via the method
crm.company.userfield.updates
Copied
Was the article helpful?
Yes
No
Previous
Update an Existing Field
Next
When adding a custom field

---

## When Adding a Custom Field onCrmCompanyUserFieldAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/events/on-crm-company-user-field-add

When Adding a Custom Field onCrmCompanyUserFieldAdd | Bitrix24 REST API and Marketplace Applications
What the Handler Receives
When Adding a Custom Field onCrmCompanyUserFieldAdd
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Learning
Scope:
crm
Who can subscribe: any user
The event
ONCRMCOMPANYUSERFIELDADD
will trigger when a new custom field is added for companies.
What the Handler Receives
What the Handler Receives
Data is sent as a POST request
{
"event"
:
"ONCRMCOMPANYUSERFIELDADD"
,
"event_handler_id"
:
"739"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6979"
,
"ENTITY_ID"
:
"CRM_COMPANY"
,
"FIELD_NAME"
:
"UF_CRM_1743165530"
}
}
,
"ts"
:
"1743165530"
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
ONCRMCOMPANYUSERFIELDADD
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
Identifier of the object to which the custom field belongs. In this case —
CRM_COMPANY
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
Continue Learning
Continue Learning
Event Handler
Register a new event handler event.bind
When updating a custom field onCrmCompanyUserFieldUpdate
When Deleting a Custom Field onCrmCompanyUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of events
Next
When deleting a custom field

---

## When Deleting a Custom Field onCrmCompanyUserFieldDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/events/on-crm-company-user-field-delete

When Deleting a Custom Field onCrmCompanyUserFieldDelete | Bitrix24 REST API and Marketplace Applications
What the Handler Receives
When Deleting a Custom Field onCrmCompanyUserFieldDelete
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Learning
Scope:
crm
Who can subscribe: any user
The event
ONCRMCOMPANYUSERFIELDDELETE
will trigger when a custom field for companies is deleted.
What the Handler Receives
What the Handler Receives
Data is sent as a POST request
{
"event"
:
"ONCRMCOMPANYUSERFIELDDELETE"
,
"event_handler_id"
:
"743"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6979"
,
"ENTITY_ID"
:
"CRM_COMPANY"
,
"FIELD_NAME"
:
"UF_CRM_1743165530"
}
}
,
"ts"
:
"1743165546"
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
ONCRMCOMPANYUSERFIELDDELETE
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
CRM_COMPANY
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
Continue Learning
Continue Learning
Event Handler
Register a new event handler event.bind
When Adding a Custom Field onCrmCompanyUserFieldAdd
When updating a custom field onCrmCompanyUserFieldUpdate
Copied
Was the article helpful?
Yes
No
Previous
When adding a custom field
Next
When changing values for a List type field

---

## When setting list values for the custom field onCrmCompanyUserFieldSetEnumValues

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/events/on-crm-company-user-field-set-enum-values

When setting list values for the custom field onCrmCompanyUserFieldSetEnumValues | Bitrix24 REST API and Marketplace Applications
What the handler receives
When setting list values for the custom field onCrmCompanyUserFieldSetEnumValues
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMCOMPANYUSERFIELDSETENUMVALUES
will trigger when setting list values for a company's custom field.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMCOMPANYUSERFIELDSETENUMVALUES"
,
"event_handler_id"
:
"745"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6979"
,
"ENTITY_ID"
:
"CRM_COMPANY"
,
"FIELD_NAME"
:
"UF_CRM_1743165530"
}
}
,
"ts"
:
"1743165530"
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
ONCRMCOMPANYUSERFIELDSETENUMVALUES
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
Object containing information about the fields of the custom field.
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
Identifier of the custom field
ENTITY_ID
string
Identifier of the object to which the custom field belongs. In this case —
CRM_COMPANY
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
When Adding a Custom Field onCrmCompanyUserFieldAdd
When updating a custom field onCrmCompanyUserFieldUpdate
When Deleting a Custom Field onCrmCompanyUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
When deleting a custom field
Next
When updating a custom field

---

## When updating a custom field onCrmCompanyUserFieldUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/userfields/events/on-crm-company-user-field-update

When updating a custom field onCrmCompanyUserFieldUpdate | Bitrix24 REST API and Marketplace Applications
What the handler receives
When updating a custom field onCrmCompanyUserFieldUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMCOMPANYUSERFIELDUPDATE
will trigger when a custom field for companies is updated.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMCOMPANYUSERFIELDUPDATE"
,
"event_handler_id"
:
"741"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6979"
,
"ENTITY_ID"
:
"CRM_COMPANY"
,
"FIELD_NAME"
:
"UF_CRM_1743165530"
}
}
,
"ts"
:
"1743165540"
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
ONCRMCOMPANYUSERFIELDUPDATE
event_handler_id
integer
Event handler identifier
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
CRM_COMPANY
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
When Adding a Custom Field onCrmCompanyUserFieldAdd
When Deleting a Custom Field onCrmCompanyUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
When changing values for a List type field
Next
Overview of events

---

## Overview of Events When Working with Companies

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/events/index

Overview of Events When Working with Companies | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Companies
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, updating, or deletion of companies.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to company events through:
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
Triggered
onCrmCompanyAdd
When a company is created manually or via the method
crm.company.add
onCrmCompanyUpdate
When a company is updated manually or via the method
crm.company.update
onCrmCompanyDelete
When a company is deleted manually or via the method
crm.company.delete
Copied
Was the article helpful?
Yes
No
Previous
When updating a custom field
Next
When creating a company

---

## Event on creating a company onCrmCompanyAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/events/on-crm-company-add

Event on creating a company onCrmCompanyAdd | Bitrix24 REST API and Marketplace Applications
Event on creating a company onCrmCompanyAdd
Event on creating a company onCrmCompanyAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMCOMPANYADD
will trigger when a company is created.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMCOMPANYADD"
,
"event_handler_id"
:
"733"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"2917"
}
}
,
"ts"
:
"1743165480"
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
ONCRMCOMPANYADD
event_handler_id
integer
Event handler identifier
data
object
Object containing information about the created company.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created company.
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
Identifier of the created company
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
Event on Company Update onCrmCompanyUpdate
Event onCrmCompanyDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of events
Next
When deleting a company

---

## Event onCrmCompanyDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/events/on-crm-company-delete

Event onCrmCompanyDelete | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmCompanyDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMCOMPANYDELETE
will trigger upon the deletion of a company.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMCOMPANYDELETE"
,
"event_handler_id"
:
"737"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"2917"
}
}
,
"ts"
:
"1743165496"
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
ONCRMCOMPANYDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted company.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted company.
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
Identifier of the deleted company
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
Event on creating a company onCrmCompanyAdd
Event on Company Update onCrmCompanyUpdate
Copied
Was the article helpful?
Yes
No
Previous
When creating a company
Next
When updating a company

---

## Event on Company Update onCrmCompanyUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/events/on-crm-company-update

Event on Company Update onCrmCompanyUpdate | Bitrix24 REST API and Marketplace Applications
Event on Company Update onCrmCompanyUpdate
Event on Company Update onCrmCompanyUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMCOMPANYUPDATE
will trigger when a company is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMCOMPANYUPDATE"
,
"event_handler_id"
:
"735"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"2917"
}
}
,
"ts"
:
"1743165490"
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
ONCRMCOMPANYUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated company.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the updated company.
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
Identifier of the updated company
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
Event on creating a company onCrmCompanyAdd
Event onCrmCompanyDelete
Copied
Was the article helpful?
Yes
No
Previous
When deleting a company
Next
Overview of Methods

---

## Managing Company Cards: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/custom-form/index

Managing Company Cards: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Managing Company Cards: Overview of Methods
Managing Company Cards: Overview of Methods
Connection of Company Cards with Other Objects
Overview of Methods
The group of methods
crm.company.details.configuration.*
manages the settings of the card for two views:
"General view" — the card view for all employees
"My view" — personal card settings for the employee
In the view, you can configure the sections of the card, for example, create a section for "Contact Information." Within the section, you can set the list of fields — in the "Contact Information" section, you can display the fields "Phone" and "Email." Fields that are not related to contact information should be displayed in another section.
Quick navigation:
all methods
Connection of Company Cards with Other Objects
Connection of Company Cards with Other Objects
User.
The user identifier
userId
is used when setting personal card settings. You can obtain the user identifier using the method
user.get
.
Company Fields.
The identifiers of the fields are used when setting visible fields in the card section. You can obtain the identifiers of system and custom company fields using the method
crm.company.fields
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: any user
Method
Description
crm.company.details.configuration.get
Retrieves the settings of company cards
crm.company.details.configuration.reset
Resets the settings of company cards
crm.company.details.configuration.set
Sets the settings of company cards
crm.company.details.configuration.forceCommonScopeForAll
Allows forcing the common company card for all users
Copied
Was the article helpful?
Yes
No
Previous
When updating a company
Next
Get Card Parameters

---

## Get parameters for crm.company.details.configuration.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/custom-form/crm-company-details-configuration-get

Get parameters for crm.company.details.configuration.get | Bitrix24 REST API and Marketplace Applications
Get parameters for crm.company.details.configuration.get
Get parameters for crm.company.details.configuration.get
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.details.configuration.get
retrieves the settings for company cards. The method reads the personal settings of the specified user or the general settings defined for all users.
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
User identifier. If not specified, the current one is used. Required only when requesting personal settings.
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
"crm.company.details.configuration.get"
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
"crm.company.details.configuration.get"
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
//Request personal settings for the company card for the user with identifier 1.
$response1
=
$b24Service
->core
->
call
(
'crm.company.details.configuration.get'
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
'Personal company details configuration for user 1: '
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
'Error getting personal company details configuration: '
.
$e
->
getMessage
();
}
try
{
//Request common settings for the company card.
$response2
=
$b24Service
->core
->
call
(
'crm.company.details.configuration.get'
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
'Common company details configuration: '
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
'Error getting common company details configuration: '
.
$e
->
getMessage
();
}
//--
//Request personal settings for the company card for the user with identifier 1.
BX24
.
callMethod
(
"crm.company.details.configuration.get"
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
//Request common settings for the company card.
BX24
.
callMethod
(
"crm.company.details.configuration.get"
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
//---
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

## Reset Company Card Settings crm.company.details.configuration.reset

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/custom-form/crm-company-details-configuration-reset

Reset Company Card Settings crm.company.details.configuration.reset | Bitrix24 REST API and Marketplace Applications
Reset Company Card Settings crm.company.details.configuration.reset
Reset Company Card Settings crm.company.details.configuration.reset
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.details.configuration.reset
resets the settings of company cards. It removes personal settings for the specified user or general settings defined for all users.
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
"crm.company.details.configuration.reset"
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
'crm.company.details.configuration.reset'
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
'Error resetting company details configuration: '
.
$e
->
getMessage
();
}
//---
//Reset personal settings of the company card for the user with identifier 1.
BX24
.
callMethod
(
"crm.company.details.configuration.reset"
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

## Set Parameters for the CRM Company Detail Card crm.company.details.configuration.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/custom-form/crm-company-details-configuration-set

Set Parameters for the CRM Company Detail Card crm.company.details.configuration.set | Bitrix24 REST API and Marketplace Applications
Set Parameters for the CRM Company Detail Card crm.company.details.configuration.set
Set Parameters for the CRM Company Detail Card crm.company.details.configuration.set
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.company.details.configuration.set
sets the settings for company cards. This method records personal settings for the specified user or general settings for all users.
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
User identifier. If not specified, the current user is used. Required only when setting personal settings.
data
unknown
Array of parameters.
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
"crm.company.details.configuration.set"
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
"About the Company"
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
"LOGO"
},
{
name
:
"COMPANY_TYPE"
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
},
{
name
:
"CONTACT"
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
"INDUSTRY"
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
'crm.company.details.configuration.set'
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
'About the Company'
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
'LOGO'
],
[
'name'
=>
'COMPANY_TYPE'
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
[
'name'
=>
'CONTACT'
]
]
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
'INDUSTRY'
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
'COMMENTS'
]
]
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
'Error setting company details configuration: '
.
$e
->
getMessage
();
}
//Setting personal settings for the company card for the user with identifier 1.
BX24
.
callMethod
(
"crm.company.details.configuration.set"
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
"About the Company"
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
"LOGO"
},
{
name
:
"COMPANY_TYPE"
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
},
{
name
:
"CONTACT"
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
"INDUSTRY"
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

## Set a common company card for all users crm.company.details.configuration.forceCommonScopeForAll

**Source:** https://apidocs.bitrix24.com/api-reference/crm/companies/custom-form/crm-company-details-configuration-force-common-scope-for-all

Set a common company card for all users crm.company.details.configuration.forceCommonScopeForAll | Bitrix24 REST API and Marketplace Applications
Examples
Set a common company card for all users crm.company.details.configuration.forceCommonScopeForAll
We are still updating this page
Some data may be missing — we will complete it soon.
Scope:
crm
Who can execute the method: any user
The method
crm.company.details.configuration.forceCommonScopeForAll
allows you to forcibly set a common company card for all users.
Without parameters
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
"crm.company.details.configuration.forceCommonScopeForAll"
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
'crm.company.details.configuration.forceCommonScopeForAll'
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
'Error setting common company card for all users: '
.
$e
->
getMessage
();
}
//---
//Set a common company card for all users.
BX24
.
callMethod
(
"crm.company.details.configuration.forceCommonScopeForAll"
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

