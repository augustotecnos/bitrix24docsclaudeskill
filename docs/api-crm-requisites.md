---
description: 'CRM Requisites: Core, addresses, links, user fields'
methods:
- crm.address.
- crm.address.add
- crm.address.delete
- crm.address.fields
- crm.address.list
- crm.address.update
- crm.company.list
- crm.contact.list
- crm.deal.list
- crm.enum.addresstype
- crm.enum.ownertype
- crm.item.list
- crm.quote.list
- crm.requisite.add
- crm.requisite.bankdetail.add
- crm.requisite.bankdetail.delete
- crm.requisite.bankdetail.fields
- crm.requisite.bankdetail.get
- crm.requisite.bankdetail.list
- crm.requisite.bankdetail.update
- crm.requisite.delete
- crm.requisite.fields
- crm.requisite.get
- crm.requisite.link.fields
- crm.requisite.link.get
- crm.requisite.link.list
- crm.requisite.link.register
- crm.requisite.link.unregister
- crm.requisite.list
- crm.requisite.preset.
pages: 26
title: 'CRM Requisites: Core, addresses, links, user fields'
---
# CRM Requisites: Core, addresses, links, user fields
> CRM Requisites: Core, addresses, links, user fields
> **26 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Details in CRM: Overview of Methods](#details-in-crm-overview-of-methods)
- [About Addresses](#about-addresses)
- [Add Address crm.address.add](#add-address-crmaddressadd)
- [Update Address for crm.address.update](#update-address-for-crmaddressupdate)
- [Get a List of Addresses by Filter crm.address.list](#get-a-list-of-addresses-by-filter-crmaddresslist)
- [Delete address crm.address.delete](#delete-address-crmaddressdelete)
- [Get Description of Address Fields crm.address.fields](#get-description-of-address-fields-crmaddressfields)
- [About Universal Requisites](#about-universal-requisites)
- [Add Requisite crm.requisite.add](#add-requisite-crmrequisiteadd)
- [Update Requisite crm.requisite.update](#update-requisite-crmrequisiteupdate)
- [Get Requisite by ID crm.requisite.get](#get-requisite-by-id-crmrequisiteget)
- [Get a List of Requisites by Filter crm.requisite.list](#get-a-list-of-requisites-by-filter-crmrequisitelis)
- [Delete Requisite and Related Objects crm.requisite.delete](#delete-requisite-and-related-objects-crmrequisited)
- [Get CRM Requisite Fields](#get-crm-requisite-fields)
- [About Custom Fields for Requisites](#about-custom-fields-for-requisites)
- [Create a New Custom Field for crm.requisite.userfield.add](#create-a-new-custom-field-for-crmrequisiteuserfiel)
- [Update Custom Field of Requisite crm.requisite.userfield.update](#update-custom-field-of-requisite-crmrequisiteuserf)
- [Get User Field by ID crm.requisite.userfield.get](#get-user-field-by-id-crmrequisiteuserfieldget)
- [Get a list of custom fields of the requisite by filter crm.requisite.userfield.list](#get-a-list-of-custom-fields-of-the-requisite-by-fi)
- [Delete User Field of Requisite crm.requisite.userfield.delete](#delete-user-field-of-requisite-crmrequisiteuserfie)
- [Links Between Requisites and CRM Objects](#links-between-requisites-and-crm-objects)
- [Register Requisite Link with Object crm.requisite.link.register](#register-requisite-link-with-object-crmrequisiteli)
- [Get the link of the requisite with the object crm.requisite.link.get](#get-the-link-of-the-requisite-with-the-object-crmr)
- [Get a list of links for requisites crm.requisite.link.list](#get-a-list-of-links-for-requisites-crmrequisitelin)
- [Unlink Requisite from Object crm.requisite.link.unregister](#unlink-requisite-from-object-crmrequisitelinkunreg)
- [Get Description of CRM Requisite Link Fields](#get-description-of-crm-requisite-link-fields)

---

## Details in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/index

Details in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Details in CRM: Overview of Methods
Details in CRM: Overview of Methods
Connection of Details with Other CRM Entities
Details Templates
Overview of Methods and Events
Basic
Addresses
Banking Details
Custom Requisite Fields
Connections of Requisites with CRM Entities
Requisites Templates
Fields of Requisites Templates
Details are separate CRM entities that store data used in closing deals: Tax Identification Number (TIN), Tax Registration Reason Code (TRRC), Primary State Registration Number (PSRN), banking details, and addresses. Everything necessary for document templates.
The
Details
field is available:
in contacts and companies — where buyer data is stored
in your companies — where your company's data, acting as the seller, is stored. This type of company is located in a separate section in the CRM settings
Quick navigation:
all methods and events
User documentation:
add company details
,
use of company details
Connection of Details with Other CRM Entities
Connection of Details with Other CRM Entities
Contact.
The default details template is Person.
Company.
The default details template is Company.
My Company.
The details of the company selected as the main seller are automatically filled in all documents.
Address.
A separate entity accessible through the standard
Address
field. Addresses can only be linked to Details or Leads. To work with addresses, use the group of methods
crm.address.*
, where the details ID is passed in the
ENTITY_ID
parameter.
Documents.
Any printed forms: invoices, acts, contracts, and others generated through the document generator.
User Documentation
Connections of requisites with CRM entities
Updates in working with addresses and contact or company details in CRM
Documents in CRM: how to create and send in a couple of minutes
Details Templates
Details Templates
Any detail for a contact or company is created within templates. A template consists of a set of fields characteristic of a specific type of legal and natural persons:
the Company template consists of fields for legal entities such as LLC:
VAT ID
,
Company Name
the Person template consists of other fields:
First Name
,
Last Name
You can add, modify, and delete details templates through the group of methods
crm.requisite.preset.*
.
Manage the list of fields for a specific template —
crm.requisite.preset.field.*
.
Create and modify custom fields that can be used in the template —
crm.requisite.userfield.*
.
User Documentation
Contact or company details templates
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can execute methods: depending on the method
Basic
Basic
Methods
Events
Method
Description
crm.requisite.add
Creates a new requisite
crm.requisite.update
Updates an existing requisite
crm.requisite.get
Returns a requisite by ID
crm.requisite.list
Returns a list of requisites by filter
crm.requisite.delete
Deletes a requisite and all associated objects
crm.requisite.fields
Returns the description of requisite fields
Event
Triggered
onCrmRequisiteAdd
When a requisite is added
onCrmRequisiteUpdate
When a requisite is modified
onCrmRequisiteDelete
When a requisite is deleted
Addresses
Addresses
Methods
Events
Method
Description
crm.address.add
Adds a new address for a requisite or lead
crm.address.update
Modifies an address for a requisite or lead
crm.address.list
Returns a list of addresses by filter
crm.address.delete
Deletes an address
crm.address.fields
Returns the formal description of address fields
Event
Triggered
onCrmAddressRegister
When an address is registered
onCrmAddressUnregister
When an address is deleted
Banking Details
Banking Details
Methods
Events
Method
Description
crm.requisite.bankdetail.add
Creates a new banking requisite
crm.requisite.bankdetail.update
Modifies an existing banking requisite
crm.requisite.bankdetail.get
Returns a banking requisite by ID
crm.requisite.bankdetail.list
Returns a list of banking requisites by filter
crm.requisite.bankdetail.delete
Deletes a banking requisite
crm.requisite.bankdetail.fields
Returns the formal description of banking requisite fields
Event
Triggered
onCrmBankDetailAdd
When a banking requisite is added
onCrmBankDetailUpdate
When a banking requisite is modified
onCrmBankDetailDelete
When a banking requisite is deleted
Custom Requisite Fields
Custom Requisite Fields
Methods
Events
Method
Description
crm.requisite.userfield.add.md
Creates a new custom field for a requisite
crm.requisite.userfield.update.md
Modifies an existing custom field for a requisite
crm.requisite.userfield.get.md
Returns a custom field for a requisite by ID
crm.requisite.userfield.list.md
Returns a list of custom fields for a requisite by filter
crm.requisite.userfield.delete.md
Deletes a custom field for a requisite
Event
Triggered
onCrmRequisiteUserFieldAdd
When a custom field is added
onCrmRequisiteUserFieldUpdate
When a custom field is modified
onCrmRequisiteUserFieldDelete
When a custom field is deleted
onCrmRequisiteUserFieldSetEnumValues
When the set of values for a custom field of list type is modified
Connections of Requisites with CRM Entities
Connections of Requisites with CRM Entities
Method
Description
crm.requisite.link.register
Registers the connection of requisites with an entity
crm.requisite.link.get
Returns the connection of requisites with an entity
crm.requisite.link.list
Returns a list of requisites connections by filter
crm.requisite.link.unregister
Deletes the connection of requisites with an entity
crm.requisite.link.fields
Returns the formal description of fields for requisites connections
Requisites Templates
Requisites Templates
Method
Description
crm.requisite.preset.add
Creates a new requisites template
crm.requisite.preset.update
Modifies a requisites template
crm.requisite.preset.countries
Returns a possible list of countries for requisites templates
crm.requisite.preset.get
Returns a requisites template by ID
crm.requisite.preset.list
Returns a list of requisites templates by filter
crm.requisite.preset.delete
Deletes a requisites template
crm.requisite.preset.fields
Returns the formal description of fields for requisites templates
Fields of Requisites Templates
Fields of Requisites Templates
Method
Description
crm.requisite.preset.field.add
Adds a customizable field to the requisites template
crm.requisite.preset.field.update
Modifies a customizable field in the requisites template
crm.requisite.preset.field.availabletoadd
Returns fields available for addition to the specified requisites template
crm.requisite.preset.field.get
Returns the description of a customizable field in the requisites template by ID
crm.requisite.preset.field.list
Returns a list of all customizable fields for a specific requisites template
crm.requisite.preset.field.delete
Deletes a customizable field from the requisites template
crm.requisite.preset.field.fields
Returns the formal description of fields that describe the customizable field in the requisites template
Copied
Was the article helpful?
Yes
No
Previous
When deleting an estimate
Next
Overview of Methods

---

## About Addresses

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/addresses/index

About Addresses | Bitrix24 REST API and Marketplace Applications
Address Fields
About Addresses
Address Fields
Overview of Methods
Scope:
crm
Who can execute the method: any user
Address Fields
Address Fields
Name
Description
Read
Write
Required
Immutable
TYPE_ID
integer
Identifier for the address type. Enumeration element "Address Type".
Enumeration elements for "Address Type" can be obtained using the method
crm.enum.addresstype
Yes
Yes
Yes
Yes
ENTITY_TYPE_ID
integer
Identifier for the parent object type.
Identifiers for object types can be obtained using the method
crm.enum.ownertype
.
Addresses can only be linked to Requisites (which are already linked to companies or contacts) or Leads. For backward compatibility, the ability to link Addresses to Contacts or Companies has been retained. However, this linkage is only possible on some older accounts where the old address handling mode was specifically enabled by technical support.
Yes
Yes
Yes
Yes
ENTITY_ID
string
Identifier for the parent object
Yes
Yes
Yes
Yes
ADDRESS_1
string
Street, house, building, structure
Yes
Yes
No
No
ADDRESS_2
string
Apartment / office
Yes
Yes
No
No
CITY
string
City
Yes
Yes
No
No
POSTAL_CODE
string
Postal code
Yes
Yes
No
No
REGION
string
Region
Yes
Yes
No
No
PROVINCE
string
Province
Yes
Yes
No
No
COUNTRY
string
Country
Yes
Yes
No
No
COUNTRY_CODE
string
Country code
Yes
Yes
No
No
LOC_ADDR_ID
integer
Identifier for the location address.
This field contains the identifier of the address object in the
Location
module, associated with the CRM address object. Each CRM address corresponds to an address object in the
location
module. This can be used to copy an existing address into CRM with location information that is not present in the CRM address fields.
If the identifier of the
location
address is specified when creating an address, a copy of the
location
address is created and linked to the newly created CRM address. If no values are specified for the string address fields in this case, they will be filled from the location address.
However, if at least one string field is specified, only the specified fields will be saved in the CRM address, and their values will overwrite the corresponding values in the location address object. The same behavior will occur when updating the address
Yes
Yes
No
No
ANCHOR_TYPE_ID
integer
Identifier for the main parent object type.
This field is for internal use. The value is automatically filled when the address is added.
Identifiers for object types can be obtained using the method
crm.enum.ownertype
.
This field contains the identifier for the parent object type of the requisite (company or contact) if the address is linked to a requisite. If the address is linked to a lead, this value will be the lead type identifier
Yes
No
No
No
ANCHOR_ID
integer
This field is for internal use. The value is automatically filled when the address is added.
This field contains the identifier for the parent object of the requisite (company or contact) if the address is linked to a requisite. If the address is linked to a lead, this value will be the lead identifier
Yes
No
No
No
Use the method
crm.address.fields
to obtain a formal description of the address fields.
Overview of Methods
Overview of Methods
Method
Description
crm.address.add
Adds a new address for a requisite or lead
crm.address.update
Modifies the address for a requisite or lead
crm.address.list
Returns a list of addresses based on a filter
crm.address.delete
Deletes an address
crm.address.fields
Returns a formal description of the address fields
Copied
Was the article helpful?
Yes
No
Previous
Get Description of Custom Fields of Requisite Template
Next
Add address

---

## Add Address crm.address.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/addresses/crm-address-add

Add Address crm.address.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Address crm.address.add
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
Who can execute the method: any user
This method adds a new address for a requisite or lead. For the user, this address appears as the address of a contact, company, or lead.
Multiple addresses of different
types
can be created, linked to a single requisite.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
A set of fields — an object of the form
{"field": "value"[, ...]}
for adding the address
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
TYPE_ID
*
integer
Identifier of the address type. Enumeration element "Address Type".
Elements of the enumeration "Address Type" can be obtained using the method
crm.enum.addresstype
ENTITY_TYPE_ID
*
integer
Identifier of the parent object's type.
Identifiers of object types can be obtained using the method
crm.enum.ownertype
.
Addresses can only be linked to Requisites (and requisites are linked to companies or contacts) or Leads.
For backward compatibility, the ability to link Addresses with Contacts or Companies is retained. However, this linkage is only possible on some older accounts where the old address handling mode was specifically enabled by technical support.
ENTITY_ID
*
string
Identifier of the parent object (
requisite
or
lead
)
ADDRESS_1
string
Street, house, building, structure
ADDRESS_2
string
Apartment / office
CITY
string
City
POSTAL_CODE
string
Postal code
REGION
string
District
PROVINCE
string
State
COUNTRY
string
Country
COUNTRY_CODE
string
Country code.
Not used, retained for backward compatibility. An empty string can be specified as a value.
LOC_ADDR_ID
integer
Identifier of the location address.
This field contains the identifier of the address object in the
Location
module, linked to the CRM address object. Each CRM address corresponds to an address object in the
location
module. This can be used to copy an existing address in CRM with location information that is not in the CRM address fields.
If the identifier of the
location
module address is specified when creating the address, a copy of the
location
address is created and linked to the created CRM address. If no values are specified for the string address fields in this case, they will be filled from the location address.
If at least one string field is specified, only the specified fields will be saved in the CRM address, and their values will overwrite the corresponding values in the location address object. The same behavior will occur when updating the address.
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
'{"fields":{"TYPE_ID":1,"ENTITY_TYPE_ID":8,"ENTITY_ID":1,"ADDRESS_1":"4 Peace Avenue","ADDRESS_2":"Drama Theater","CITY":"City","POSTAL_CODE":"000000","REGION":"Urban District","PROVINCE":"Region","COUNTRY":"USA"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.address.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"TYPE_ID":1,"ENTITY_TYPE_ID":8,"ENTITY_ID":1,"ADDRESS_1":"4 Peace Avenue","ADDRESS_2":"Drama Theater","CITY":"City","POSTAL_CODE":"000000","REGION":"Urban District","PROVINCE":"Region","COUNTRY":"USA"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.address.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.address.add"
,
{
fields
:
{
"TYPE_ID"
:
1
,
// Address type, see crm.enum.addresstype
"ENTITY_TYPE_ID"
:
8
,
// Object type (requisite or lead)
"ENTITY_ID"
:
1
,
// Identifier of the requisite
"ADDRESS_1"
:
"4 Peace Avenue"
,
"ADDRESS_2"
:
"Drama Theater"
,
"CITY"
:
"City"
,
"POSTAL_CODE"
:
"00000"
,
"REGION"
:
"Urban District"
,
"PROVINCE"
:
"Region"
,
"COUNTRY"
:
"USA"
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
'crm.address.add'
,
[
'fields'
=> [
'TYPE_ID'
=>
1
,
'ENTITY_TYPE_ID'
=>
8
,
'ENTITY_ID'
=>
1
,
'ADDRESS_1'
=>
'4 Peace Avenue'
,
'ADDRESS_2'
=>
'Drama Theater'
,
'CITY'
=>
'City'
,
'POSTAL_CODE'
=>
'00000'
,
'REGION'
=>
'Urban District'
,
'PROVINCE'
=>
'Region'
,
'COUNTRY'
=>
'USA'
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
'Error adding address: '
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
"crm.address.add"
,
{
fields
:
{
"TYPE_ID"
:
1
,
// Address type, see crm.enum.addresstype
"ENTITY_TYPE_ID"
:
8
,
// Object type (requisite or lead)
"ENTITY_ID"
:
1
,
// Identifier of the requisite
"ADDRESS_1"
:
"4 Peace Avenue"
,
"ADDRESS_2"
:
"Drama Theater"
,
"CITY"
:
"City"
,
"POSTAL_CODE"
:
"00000"
,
"REGION"
:
"Urban District"
,
"PROVINCE"
:
"Region"
,
"COUNTRY"
:
"USA"
,
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
'crm.address.add'
,
[
'fields'
=> [
'TYPE_ID'
=>
1
,
'ENTITY_TYPE_ID'
=>
8
,
'ENTITY_ID'
=>
1
,
'ADDRESS_1'
=>
'4 Peace Avenue'
,
'ADDRESS_2'
=>
'Drama Theater'
,
'CITY'
=>
'City'
,
'POSTAL_CODE'
=>
'00000'
,
'REGION'
=>
'Urban District'
,
'PROVINCE'
=>
'Region'
,
'COUNTRY'
=>
'USA'
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
1712922620.724857
,
"finish"
:
1712922623.393783
,
"duration"
:
2.6689260005950928
,
"processing"
:
2.210068941116333
,
"date_start"
:
"2024-04-12T14:50:20+02:00"
,
"date_finish"
:
"2024-04-12T14:50:23+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of adding the address:
true
— added
false
— not added
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
""
,
"error_description"
:
"ENTITY_ID is not defined or invalid."
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
TYPE_ID is not defined or invalid
Address type identifier is not specified or has an invalid value
ENTITY_TYPE_ID is not defined or invalid
Parent object type identifier is not specified or has an invalid value.
ENTITY_ID is not defined or invalid
Parent object identifier is not specified or has an invalid value
TypeAddress exists
An address of this type already exists for the specified parent object
Access denied
Insufficient access permissions to add the address
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
Update Address for crm.address.update
Get a List of Addresses by Filter crm.address.list
Delete address crm.address.delete
Get Description of Address Fields crm.address.fields
Add a Company with Details via Web Form
Add a contact with details via a web form
Add a deal and company with requisites
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Update address of detail

---

## Update Address for crm.address.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/addresses/crm-address-update

Update Address for crm.address.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Address for crm.address.update
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
Who can execute the method: any user
This method updates the address for a contact or lead.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
A set of fields — an object of the form
{"field": "value"[, ...]}
to update the address.
Values for the fields
TYPE_ID
,
ENTITY_TYPE_ID
,
ENTITY_ID
must be specified as they identify the address being modified. Other fields are specified if their values need to be changed
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
TYPE_ID
*
integer
Identifier for the address type. Enumeration element "Address Type".
Enumeration elements for "Address Type" can be retrieved using the method
crm.enum.addresstype
ENTITY_TYPE_ID
*
integer
Identifier for the parent object type.
Object type identifiers can be retrieved using the method
crm.enum.ownertype
.
Addresses can only be linked to Contacts (which are linked to companies or contacts) or Leads.
For backward compatibility, the ability to link Addresses to Contacts or Companies has been retained. However, this linkage is only possible on some older accounts where the old address handling mode was specifically enabled by support.
ENTITY_ID
*
string
Identifier for the parent object
ADDRESS_1
string
Street, house, building, structure
ADDRESS_2
string
Apartment / office
CITY
string
City
POSTAL_CODE
string
Postal code
REGION
string
District
PROVINCE
string
State
COUNTRY
string
Country
COUNTRY_CODE
string
Country code.
Not used, retained for backward compatibility. An empty string can be specified as a value.
LOC_ADDR_ID
integer
Identifier for the location address.
This field contains the identifier of the address object in the
Location
module, linked to the CRM address object. Each CRM address corresponds to an address object in the
location
module. This can be used to copy an existing address into CRM with location information that is not present in the CRM address fields.
If the identifier of the
location
module address is specified when creating an address, a copy of the
location
address is created and linked to the newly created CRM address. If no values are specified for the string address fields in this case, they will be filled from the location address.
If at least one string field is specified, only the specified fields will be saved in the CRM address, and their values will overwrite the corresponding values in the location address object. The same behavior will occur when updating the address.
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
'{"fields":{"TYPE_ID":1,"ENTITY_TYPE_ID":3,"ENTITY_ID":1,"ADDRESS_1":"Street, 261","CITY":"Los Angeles"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.address.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"TYPE_ID":1,"ENTITY_TYPE_ID":3,"ENTITY_ID":1,"ADDRESS_1":"Street, 261","CITY":"Los Angeles"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.address.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.address.update"
,
{
fields
:
{
"TYPE_ID"
:
1
,
//
"ENTITY_TYPE_ID"
:
3
,
// - Identifying fields.
"ENTITY_ID"
:
1
,
//
"ADDRESS_1"
:
"Street, 261"
,
// - Fields whose values are changing.
"CITY"
:
"Los Angeles"
//
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
'crm.address.update'
,
[
'fields'
=> [
'TYPE_ID'
=>
1
,
'ENTITY_TYPE_ID'
=>
3
,
'ENTITY_ID'
=>
1
,
'ADDRESS_1'
=>
'Street, 261'
,
'CITY'
=>
'Los Angeles'
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
'Error updating address: '
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
"crm.address.update"
,
{
fields
:
{
"TYPE_ID"
:
1
,
//
"ENTITY_TYPE_ID"
:
3
,
// - Identifying fields.
"ENTITY_ID"
:
1
,
//
"ADDRESS_1"
:
"Street, 261"
,
// - Fields whose values are changing.
"CITY"
:
"Los Angeles"
//
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
'crm.address.update'
,
[
'fields'
=> [
'TYPE_ID'
=>
1
,
'ENTITY_TYPE_ID'
=>
3
,
'ENTITY_ID'
=>
1
,
'ADDRESS_1'
=>
'Street, 261'
,
'CITY'
=>
'Los Angeles'
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
1712922620.724857
,
"finish"
:
1712922623.393783
,
"duration"
:
2.6689260005950928
,
"processing"
:
2.210068941116333
,
"date_start"
:
"2024-04-12T14:50:20+02:00"
,
"date_finish"
:
"2024-04-12T14:50:23+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the address update:
true
— updated
false
— not updated
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
""
,
"error_description"
:
"ENTITY_ID is not defined or invalid."
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
TYPE_ID is not defined or invalid
Address type identifier is not specified or has an invalid value
ENTITY_TYPE_ID is not defined or invalid
Parent object type identifier is not specified or has an invalid value.
ENTITY_ID is not defined or invalid
Parent object identifier is not specified or has an invalid value.
TypeAddress not found
Address not found
Access denied
Insufficient access permissions to update the address
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
Add Address crm.address.add
Get a List of Addresses by Filter crm.address.list
Delete address crm.address.delete
Get Description of Address Fields crm.address.fields
Copied
Was the article helpful?
Yes
No
Previous
Add address
Next
Get list of addresses by filter

---

## Get a List of Addresses by Filter crm.address.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/addresses/crm-address-list

Get a List of Addresses by Filter crm.address.list | Bitrix24 REST API and Marketplace Applications
Get a List of Addresses by Filter crm.address.list
Get a List of Addresses by Filter crm.address.list
Method Parameters
Description of Address Fields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a list of addresses based on the filter.
Addresses are moved to the details. In the CRM card, they are displayed as a separate field.
Multiple details can be linked to a CRM object. Within a detail, there can be several addresses (each of a different type).
Method Parameters
Method Parameters
Name
type
Description
select
array
An array of fields to select (see
address fields
).
If the array is not provided or an empty array is passed, all available address fields will be selected.
filter
object
An object for filtering selected addresses in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
correspond to
address fields
.
An additional prefix can be assigned to the key to clarify the filter's behavior. Possible prefix values:
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
symbol should not be included in the filter value. The search looks for the substring in any position of the string.
=%
— LIKE, substring search. The
%
symbol must be included in the value. Examples:
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
!%
— NOT LIKE, substring search. The
%
symbol should not be included in the filter value. The search goes from both sides.
!=%
— NOT LIKE, substring search. The
%
symbol must be included in the value. Examples:
"mol%"
— searches for values not starting with "mol"
"%mol"
— searches for values not ending with "mol"
"%mol%"
— searches for values where the substring "mol" is not present in any position
!%=
— NOT LIKE (similar to
!=%
)
=
— equals, exact match (used by default)
!=
— not equal
!
— not equal
order
object
An object for sorting selected addresses in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
correspond to
address fields
.
Possible values for
order
:
asc
— in ascending order
desc
— in descending order
start
integer
This parameter is used to manage pagination.
The page size of results is always static: 50 records.
To select the second page of results, you need to pass the value
50
. To select the third page of results, the value is
100
, and so on.
The formula for calculating the
start
parameter value:
start = (N-1) * 50
, where
N
is the desired page number
Description of Address Fields
Description of Address Fields
Name
type
Description
TYPE_ID
integer
Identifier of the address type. Enumeration element "Address Type".
Enumeration elements for "Address Type" can be obtained using the method
crm.enum.addresstype
ENTITY_TYPE_ID
integer
Identifier of the parent object's type.
Object type identifiers can be obtained using the method
crm.enum.ownertype
.
Addresses can only be linked to Details (and details to companies or contacts) or Leads.
For backward compatibility, the ability to link Addresses to Contacts or Companies is retained. However, this link is only possible on some older accounts where the old address handling mode was specifically enabled by support.
ENTITY_ID
string
Identifier of the parent object
ADDRESS_1
string
Street, house, building, structure
ADDRESS_2
string
Apartment / office
CITY
string
City
POSTAL_CODE
string
Postal code
REGION
string
Region
PROVINCE
string
Province
COUNTRY
string
Country
COUNTRY_CODE
string
Country code.
Not used, retained for backward compatibility. An empty string can be specified as a value.
LOC_ADDR_ID
integer
Identifier of the location address.
This field contains the identifier of the address object in the
Location
module, linked to the CRM address object. Each CRM address corresponds to an address object in the
location
module. This can be used to copy an existing address into CRM with location information that is not present in the CRM address fields.
If the identifier of the
location
module address is specified when creating an address, a copy of the
location
address is created and linked to the created CRM address. If no values are specified for the string fields of the address in this case, they will be filled from the location address.
If at least one string field was specified, only the specified fields will be saved in the CRM address, and their values will overwrite the corresponding values in the location address object. The same behavior will occur when updating the address.
ANCHOR_TYPE_ID
integer
Identifier of the main parent object's type.
This field is for internal use. The value is automatically filled when adding an address.
Object type identifiers can be obtained using the method
crm.enum.ownertype
.
This field contains the identifier of the parent object's type of the detail (company or contact) if the address is linked to the detail. If the address is linked to a lead, this value will be the lead type identifier.
ANCHOR_ID
integer
This field is for internal use. The value is automatically filled when adding an address.
This field contains the identifier of the parent object of the detail (company or contact) if the address is linked to the detail. If the address is linked to a lead, this value will be the lead identifier.
Code Examples
Code Examples
How to Use Examples in Documentation
Searching for addresses linked to the Detail type:
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
'{"order":{"TYPE_ID":"asc"},"filter":{"ENTITY_TYPE_ID":8,"ENTITY_ID":7335},"limit":10}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.address.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"TYPE_ID":"asc"},"filter":{"ENTITY_TYPE_ID":8,"ENTITY_ID":7335},"limit":10,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.address.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.address.list'
,
{
order
: {
"TYPE_ID"
:
"asc"
},
filter
: {
"ENTITY_TYPE_ID"
:
8
,
"ENTITY_ID"
:
7335
},
limit
:
10
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.address.list'
, {
order
: {
"TYPE_ID"
:
"asc"
},
filter
: {
"ENTITY_TYPE_ID"
:
8
,
"ENTITY_ID"
:
7335
},
limit
:
10
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
'crm.address.list'
, {
order
: {
"TYPE_ID"
:
"asc"
},
filter
: {
"ENTITY_TYPE_ID"
:
8
,
"ENTITY_ID"
:
7335
},
limit
:
10
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
'crm.address.list'
,
[
'order'
=> [
'TYPE_ID'
=>
'asc'
],
'filter'
=> [
'ENTITY_TYPE_ID'
=>
8
,
'ENTITY_ID'
=>
7335
],
'limit'
=>
10
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
'Error fetching address list: '
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
"crm.address.list"
,
{
order
: {
"TYPE_ID"
:
"asc"
},
filter
: {
"ENTITY_TYPE_ID"
:
8
,
"ENTITY_ID"
:
7335
},
limit
:
10
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
'crm.address.list'
,
[
'order'
=> [
'TYPE_ID'
=>
'asc'
],
'filter'
=> [
'ENTITY_TYPE_ID'
=>
8
,
'ENTITY_ID'
=>
7335
],
'limit'
=>
10
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
"TYPE_ID"
:
"1"
,
"ENTITY_TYPE_ID"
:
"8"
,
"ENTITY_ID"
:
"7335"
,
"ADDRESS_1"
:
"Address 1"
,
"ADDRESS_2"
:
"701"
,
"CITY"
:
"Los Angeles"
,
"POSTAL_CODE"
:
"625003"
,
"REGION"
:
"California"
,
"PROVINCE"
:
"California"
,
"COUNTRY"
:
"USA"
,
"COUNTRY_CODE"
:
null
,
"LOC_ADDR_ID"
:
"479"
,
"ANCHOR_TYPE_ID"
:
"3"
,
"ANCHOR_ID"
:
"17192"
}
]
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
1716301758.664873
,
"finish"
:
1716301759.73158
,
"duration"
:
1.0667071342468262
,
"processing"
:
0.028820037841796875
,
"date_start"
:
"2024-05-21T16:29:18+02:00"
,
"date_finish"
:
"2024-05-21T16:29:19+02:00"
,
"operating"
:
0
}
}
If a contact has 2 different details to which addresses are linked:
HTTP Status:
200
{
"result"
:
[
{
"TYPE_ID"
:
"1"
,
"ENTITY_TYPE_ID"
:
"8"
,
"ENTITY_ID"
:
"7335"
,
"ADDRESS_1"
:
"Address 2"
,
"ADDRESS_2"
:
"701"
,
"CITY"
:
"Los Angeles"
,
"POSTAL_CODE"
:
"625003"
,
"REGION"
:
"California"
,
"PROVINCE"
:
"California"
,
"COUNTRY"
:
"USA"
,
"COUNTRY_CODE"
:
null
,
"LOC_ADDR_ID"
:
"479"
,
"ANCHOR_TYPE_ID"
:
"3"
,
"ANCHOR_ID"
:
"17192"
}
,
{
"TYPE_ID"
:
"1"
,
"ENTITY_TYPE_ID"
:
"8"
,
"ENTITY_ID"
:
"7335"
,
"ADDRESS_1"
:
"Address"
,
"ADDRESS_2"
:
"2"
,
"CITY"
:
"Los Angeles"
,
"POSTAL_CODE"
:
"666000"
,
"REGION"
:
"California"
,
"PROVINCE"
:
"California"
,
"COUNTRY"
:
"USA"
,
"COUNTRY_CODE"
:
null
,
"LOC_ADDR_ID"
:
"129"
,
"ANCHOR_TYPE_ID"
:
"3"
,
"ANCHOR_ID"
:
"17192"
}
]
,
"total"
:
2
,
"time"
:
{
"start"
:
1716301758.664873
,
"finish"
:
1716301759.73158
,
"duration"
:
1.0667071342468262
,
"processing"
:
0.028820037841796875
,
"date_start"
:
"2024-05-21T16:29:18+02:00"
,
"date_finish"
:
"2024-05-21T16:29:19+02:00"
,
"operating"
:
0
}
}
Additional Information about the Result
The
ANCHOR_TYPE_ID
field is filled with a value from
crm.enum.ownertype
(in this example, it is Contacts), and the
ANCHOR_ID
field contains the ID of the object (in this case, the Contact).
The
ANCHOR_TYPE_ID
and
ANCHOR_ID
fields in the two examples above are the same, indicating that both addresses belong to the same Contact.
Returned Data
Returned Data
Name
type
Description
result
array
An array of objects with information about the selected addresses. Each element contains the selected
address fields
total
integer
The total number of records found
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP Status:
40x
,
50x
{
"error"
:
0
,
"error_description"
:
"error"
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
Access denied
Insufficient access rights to retrieve the list of addresses. No read access to companies, contacts, leads
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
Add Address crm.address.add
Update Address for crm.address.update
Delete address crm.address.delete
Get Description of Address Fields crm.address.fields
Copied
Was the article helpful?
Yes
No
Previous
Update address of detail
Next
Delete address

---

## Delete address crm.address.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/addresses/crm-address-delete

Delete address crm.address.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete address crm.address.delete
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
Who can execute the method: any user
The method deletes an address.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
A set of fields — an object of the form
{"field": "value"[, ...]}
for deleting the address
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
TYPE_ID
*
integer
Identifier of the address type. Enumeration element "Address Type".
Enumeration elements for "Address Type" can be obtained using the method
crm.enum.addresstype
ENTITY_TYPE_ID
*
integer
Identifier of the parent object's type.
Identifiers for object types can be obtained using the method
crm.enum.ownertype
.
Addresses can only be linked to Details (which are already linked to companies or contacts) or Leads.
For backward compatibility, the ability to link Addresses to Contacts or Companies has been retained. However, this linkage is only possible on some older accounts where the old address handling mode was specifically enabled by technical support.
ENTITY_ID
*
string
Identifier of the parent object (
detail
or
lead
)
Code Examples
Code Examples
How to Use Examples in Documentation
Searching for addresses linked to the Detail type:
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
'{"fields":{"TYPE_ID":1,"ENTITY_TYPE_ID":3,"ENTITY_ID":1}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.address.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"TYPE_ID":1,"ENTITY_TYPE_ID":3,"ENTITY_ID":1},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.address.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.address.delete"
,
{
fields
:
{
"TYPE_ID"
:
1
,
"ENTITY_TYPE_ID"
:
3
,
"ENTITY_ID"
:
1
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
'crm.address.delete'
,
[
'fields'
=> [
'TYPE_ID'
=>
1
,
'ENTITY_TYPE_ID'
=>
3
,
'ENTITY_ID'
=>
1
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
'Error deleting address: '
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
"crm.address.delete"
,
{
fields
:
{
"TYPE_ID"
:
1
,
"ENTITY_TYPE_ID"
:
3
,
"ENTITY_ID"
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
'crm.address.delete'
,
[
'fields'
=> [
'TYPE_ID'
=>
1
,
'ENTITY_TYPE_ID'
=>
3
,
'ENTITY_ID'
=>
1
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
1712922620.724857
,
"finish"
:
1712922623.393783
,
"duration"
:
2.6689260005950928
,
"processing"
:
2.210068941116333
,
"date_start"
:
"2024-04-12T14:50:20+02:00"
,
"date_finish"
:
"2024-04-12T14:50:23+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the address deletion:
true
— deleted
false
— not deleted
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
""
,
"error_description"
:
"TypeAddress not found."
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
TYPE_ID is not defined or invalid
The address type identifier is not specified or has an invalid value
ENTITY_TYPE_ID is not defined or invalid
The parent object type identifier is not specified or has an invalid value
ENTITY_ID is not defined or invalid
The parent object identifier is not specified or has an invalid value
TypeAddress not found
The address to delete was not found
Access denied
Insufficient access permissions to delete the address
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
Add Address crm.address.add
Update Address for crm.address.update
Get a List of Addresses by Filter crm.address.list
Get Description of Address Fields crm.address.fields
Copied
Was the article helpful?
Yes
No
Previous
Get list of addresses by filter
Next
Get description of address fields

---

## Get Description of Address Fields crm.address.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/addresses/crm-address-fields

Get Description of Address Fields crm.address.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Description of Address Fields crm.address.fields
Code Examples
Response Handling
Returned Data
Description of Address Fields
Description of Attributes
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a formal description of the address fields.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.address.fields
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
https://**put_your_bitrix24_address**/rest/crm.address.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.address.fields'
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
'crm.address.fields'
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
'Error fetching CRM address fields: '
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
"crm.address.fields"
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
'crm.address.fields'
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
HTTP Status:
200
{
"result"
:
{
"TYPE_ID"
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
"TYPE_ID"
}
,
"ENTITY_TYPE_ID"
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
"ENTITY_TYPE_ID"
}
,
"ENTITY_ID"
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
"ENTITY_ID"
}
,
"ADDRESS_1"
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
"Street, house, building, structure"
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
"Apartment / office"
}
,
"CITY"
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
"POSTAL_CODE"
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
"Postal code"
}
,
"REGION"
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
"PROVINCE"
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
"COUNTRY"
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
"COUNTRY_CODE"
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
"COUNTRY_CODE"
}
,
"LOC_ADDR_ID"
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
"Location address identifier"
}
,
"ANCHOR_TYPE_ID"
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
"ANCHOR_TYPE_ID"
}
,
"ANCHOR_ID"
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
"ANCHOR_ID"
}
}
,
"time"
:
{
"start"
:
1712938174.436428
,
"finish"
:
1712938175.432068
,
"duration"
:
0.9956400394439697
,
"processing"
:
0.5710320472717285
,
"date_start"
:
"2024-04-12T19:09:34+02:00"
,
"date_finish"
:
"2024-04-12T19:09:35+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
An object in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field
is the field identifier and
value
is the object with
field attributes
time
time
Information about the request execution time
Description of Address Fields
Description of Address Fields
Name
type
Description
TYPE_ID
integer
Identifier of the address type. Enumeration element "Address Type".
Enumeration elements "Address Type" can be obtained using the method
crm.enum.addresstype
ENTITY_TYPE_ID
integer
Identifier of the parent object type.
Object type identifiers can be obtained using the method
crm.enum.ownertype
.
Addresses can only be linked to Requisites (and requisites to companies or contacts) or Leads.
For backward compatibility, the ability to link Addresses to Contacts or Companies has been retained. However, this link is only possible on some old accounts where the old address handling mode has been specifically enabled by support.
ENTITY_ID
string
Identifier of the parent object
ADDRESS_1
string
Street, house, building, structure
ADDRESS_2
string
Apartment / office
CITY
string
City
POSTAL_CODE
string
Postal code
REGION
string
Region
PROVINCE
string
Province
COUNTRY
string
Country
COUNTRY_CODE
string
Country code.
Not used, retained for backward compatibility. An empty string can be specified as a value.
LOC_ADDR_ID
integer
Identifier of the location address.
This field contains the identifier of the address object in the
Location
module, associated with the CRM address object. Each CRM address corresponds to an address object in the
location
module. This can be used to copy an existing address into CRM with location information that is not present in the CRM address fields.
If the identifier of the
location
module address is specified when creating an address, a copy of the
location
address is created and linked to the created CRM address. If no values are specified for the string address fields in this case, they will be filled from the location address.
If at least one string field is specified, only the specified fields will be saved in the CRM address, and their values will overwrite the corresponding values in the location address object. The same behavior will occur when updating the address.
ANCHOR_TYPE_ID
integer
Identifier of the main parent object type.
This field is for internal use. The value is automatically filled when adding an address.
Object type identifiers can be obtained using the method
crm.enum.ownertype
.
This field contains the identifier of the parent object type of the requisite (company or contact) if the address is linked to a requisite. If the address is linked to a lead, this value will be the lead type identifier.
ANCHOR_ID
integer
This field is for internal use. The value is automatically filled when adding an address.
This field contains the identifier of the parent object of the requisite (company or contact) if the address is linked to a requisite. If the address is linked to a lead, this value will be the lead identifier.
Description of Attributes
Description of Attributes
Name
type
Description
type
string
Field type
isRequired
boolean
"Required" attribute. Possible values:
true — yes
false — no
isReadOnly
boolean
"Read-only" attribute. Possible values:
true — yes
false — no
isImmutable
boolean
"Immutable" attribute. Possible values:
true — yes
false — no
isMultiple
boolean
"Multiple" attribute. Possible values:
true — yes
false — no
isDynamic
boolean
"Custom" attribute. Possible values:
true — yes
false — no
title
string
Field identifier
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
Add Address crm.address.add
Update Address for crm.address.update
Get a List of Addresses by Filter crm.address.list
Delete address crm.address.delete
Add a Company with Details via Web Form
Add a contact with details via a web form
Copied
Was the article helpful?
Yes
No
Previous
Delete address
Next
Overview of methods

---

## About Universal Requisites

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/universal/index

About Universal Requisites | Bitrix24 REST API and Marketplace Applications
Requisite Fields
About Universal Requisites
Requisite Fields
Overview of Methods
Scope:
crm
Who can execute the method: any user
Company requisites are details that allow for the precise identification of an organization. Every officially registered company has a set of such data, including: name, legal address, TIN, OGRN, KPP, OKPO code, OKVED code, and others.
We explain more in the article
What are your company's requisites
Requisite Fields
Requisite Fields
Name
type
Description
Read
Write
Required
Immutable
ID
integer
Identifier of the requisite, can be obtained using the method
crm.requisite.list
. Created automatically and is unique within the account.
Yes
No
No
No
ENTITY_TYPE_ID
*
integer
Identifier of the parent entity type.
Currently, this can only be:
3
— contact
4
— company
Identifiers of all CRM entity types can be obtained from the method
crm.enum.ownertype
Yes
Yes
Yes
Yes
ENTITY_ID
*
integer
Identifier of the parent entity (contact or company).
The identifier can be obtained using the method
crm.company.list
for companies and the method
crm.contact.list
for contacts
Yes
Yes
Yes
Yes
PRESET_ID
*
integer
Identifier of the requisites template.
Template identifiers can be obtained using the method
crm.requisite.preset.list
Yes
Yes
Yes
Yes
DATE_CREATE
datetime
Creation date
Yes
No
No
No
DATE_MODIFY
datetime
Modification date
Yes
No
No
No
CREATED_BY_ID
user
Identifier of the user who created the requisite
Yes
No
No
No
MODIFY_BY_ID
user
Identifier of the user who modified the requisite
Yes
No
No
No
NAME
*
string
Name of the requisite
Yes
Yes
Yes
No
CODE
string
Symbolic code of the requisite
Yes
Yes
No
No
XML_ID
string
External key, used for exchange operations.
Identifier of the object in the external information database.
The purpose of the field may change by the final developer
Yes
Yes
No
No
ORIGINATOR_ID
string
Identifier of the external information database.
The purpose of the field may change by the final developer
Yes
Yes
No
No
ACTIVE
char
Activity status.
Values
Y
or
N
are used.
Currently, the field does not actually affect anything
Yes
Yes
No
No
ADDRESS_ONLY
char
Status indicator when the requisite is used only for storing the address.
Values
Y
or
N
are used. When
Y
, the requisites are not displayed in the entity detail form, but the address is shown
Yes
Yes
No
No
SORT
integer
Sorting. Order in the list of entity requisites when there are multiple
Yes
Yes
No
No
RQ_NAME
string
Full name
Yes
Yes
No
No
RQ_FIRST_NAME
string
First name
Yes
Yes
No
No
RQ_LAST_NAME
string
Last name
Yes
Yes
No
No
RQ_SECOND_NAME
string
Middle name
Yes
Yes
No
No
RQ_COMPANY_ID
string
Identifier of the organization
Yes
Yes
No
No
RQ_COMPANY_NAME
string
Short name of the organization
Yes
Yes
No
No
RQ_COMPANY_FULL_NAME
string
Full name of the organization
Yes
Yes
No
No
RQ_COMPANY_REG_DATE
string
Date of state registration
Yes
Yes
No
No
RQ_DIRECTOR
string
General Director
Yes
Yes
No
No
RQ_ACCOUNTANT
string
Chief Accountant
Yes
Yes
No
No
RQ_CEO_NAME
string
Full name of the first leader
Yes
Yes
No
No
RQ_CEO_WORK_POS
string
Position of the first leader
Yes
Yes
No
No
RQ_CONTACT
string
Contact person
Yes
Yes
No
No
RQ_EMAIL
string
E-Mail
Yes
Yes
No
No
RQ_PHONE
string
Phone
Yes
Yes
No
No
RQ_FAX
string
Fax
Yes
Yes
No
No
RQ_IDENT_TYPE
crm_status
Identification method
Yes
Yes
No
No
RQ_IDENT_DOC
string
Type of document
Yes
Yes
No
No
RQ_IDENT_DOC_SER
string
Series
Yes
Yes
No
No
RQ_IDENT_DOC_NUM
string
Number
Yes
Yes
No
No
RQ_IDENT_DOC_PERS_NUM
string
Personal number
Yes
Yes
No
No
RQ_IDENT_DOC_DATE
string
Date of issue
Yes
Yes
No
No
RQ_IDENT_DOC_ISSUED_BY
string
Issued by
Yes
Yes
No
No
RQ_IDENT_DOC_DEP_CODE
string
Department code
Yes
Yes
No
No
RQ_INN
string
TIN
Yes
Yes
No
No
RQ_KPP
string
KPP
Yes
Yes
No
No
RQ_USRLE
string
Handelsregisternummer (for country DE)
Yes
Yes
No
No
RQ_IFNS
string
IFNS
Yes
Yes
No
No
RQ_OGRN
string
OGRN
Yes
Yes
No
No
RQ_OGRNIP
string
OGRNIP
Yes
Yes
No
No
RQ_OKPO
string
OKPO
Yes
Yes
No
No
RQ_OKTMO
string
OKTMO
Yes
Yes
No
No
RQ_OKVED
string
OKVED
Yes
Yes
No
No
RQ_EDRPOU
string
EDRPOU
Yes
Yes
No
No
RQ_DRFO
string
DRFO
Yes
Yes
No
No
RQ_KBE
string
KBE
Yes
Yes
No
No
RQ_IIN
string
IIN
Yes
Yes
No
No
RQ_BIN
string
BIN
Yes
Yes
No
No
RQ_ST_CERT_SER
string
Series of the state registration certificate
Yes
Yes
No
No
RQ_ST_CERT_NUM
string
Number of the state registration certificate
Yes
Yes
No
No
RQ_ST_CERT_DATE
string
Date of the state registration certificate
Yes
Yes
No
No
RQ_VAT_PAYER
char
VAT payer (for country UA).
Values
Y
or
N
are used
Yes
Yes
No
No
RQ_VAT_ID
string
VAT ID (identification number of the VAT payer)
Yes
Yes
No
No
RQ_VAT_CERT_SER
string
Series of the VAT certificate
Yes
Yes
No
No
RQ_VAT_CERT_NUM
string
Number of the VAT certificate
Yes
Yes
No
No
RQ_VAT_CERT_DATE
string
Date of the VAT certificate
Yes
Yes
No
No
RQ_RESIDENCE_COUNTRY
string
Country of residence
Yes
Yes
No
No
RQ_BASE_DOC
string
Basis of the action
Yes
Yes
No
No
RQ_REGON
string
REGON (for country PL)
Yes
Yes
No
No
RQ_KRS
string
KRS (for country PL)
Yes
Yes
No
No
RQ_PESEL
string
PESEL (for country PL)
Yes
Yes
No
No
RQ_LEGAL_FORM
string
Legal form (for country FR)
Yes
Yes
No
No
RQ_SIRET
string
Siret number (for country FR)
Yes
Yes
No
No
RQ_SIREN
string
Siren number (for country FR)
Yes
Yes
No
No
RQ_CAPITAL
string
Share capital (for country FR)
Yes
Yes
No
No
RQ_RCS
string
RCS (for country FR)
Yes
Yes
No
No
RQ_CNPJ
string
CNPJ (for country BR)
Yes
Yes
No
No
RQ_STATE_REG
string
State Registration (IE) (for country BR)
Yes
Yes
No
No
RQ_MNPL_REG
string
Municipal Registration (IM) (for country BR)
Yes
Yes
No
No
RQ_CPF
string
CPF (for country BR)
Yes
Yes
No
No
UF_CRM_...
Custom fields. For example,
UF_CRM_1694526604
.
Requisites can have a set of custom fields with types:
string
,
boolean
,
double
,
datetime
.
You can add a custom field to requisites using the method
crm.requisite.userfield.add
Yes
Yes
No
No
Overview of Methods
Overview of Methods
Method
Description
crm.requisite.add
Creates a new requisite
crm.requisite.update
Updates an existing requisite
crm.requisite.get
Returns the requisite by identifier
crm.requisite.list
Returns a list of requisites by filter
crm.requisite.delete
Deletes the requisite and all related objects
crm.requisite.fields
Returns the description of requisite fields
Copied
Was the article helpful?
Yes
No
Previous
Get description of address fields
Next
Add detail

---

## Add Requisite crm.requisite.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/universal/crm-requisite-add

Add Requisite crm.requisite.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Requisite crm.requisite.add
Method Parameters
Parameter fields
Code Examples
Response on Success
Returned Data
Response on Error
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method adds a new requisite.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
Set of fields — an object of the form
{"field": "value"[, ...]}
for adding the requisite
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
ENTITY_TYPE_ID
*
integer
Identifier of the parent entity type.
Currently, this can only be:
3
— contact
4
— company
Identifiers for all CRM entity types can be retrieved using the method
crm.enum.ownertype
ENTITY_ID
*
integer
Identifier of the parent entity (contact or company).
The identifier can be obtained using the method
crm.company.list
for a company and the method
crm.contact.list
for a contact
PRESET_ID
*
integer
Identifier of the requisite template.
Template identifiers can be obtained using the method
crm.requisite.preset.list
NAME
*
string
Name of the requisite
CODE
string
Symbolic code of the requisite
XML_ID
string
External key, used for exchange operations.
Identifier of the external information database.
The purpose of the field may change by the final developer
ORIGINATOR_ID
string
Identifier of the external information database.
The purpose of the field may change by the final developer
ACTIVE
char
Activity status.
Values
Y
or
N
are used.
Currently, the field does not affect anything
ADDRESS_ONLY
char
Status indicator when the requisite is used only for storing the address.
Values
Y
or
N
are used. When set to
Y
, the requisites are not displayed in the entity card, but the address is shown
SORT
integer
Sorting.
Order in the list of requisites of the entity when there are multiple
RQ_NAME
string
Full name
RQ_FIRST_NAME
string
First name
RQ_LAST_NAME
string
Last name
RQ_SECOND_NAME
string
Middle name
RQ_COMPANY_ID
string
Identifier of the organization
RQ_COMPANY_NAME
string
Short name of the organization
RQ_COMPANY_FULL_NAME
string
Full name of the organization
RQ_COMPANY_REG_DATE
string
Date of state registration
RQ_DIRECTOR
string
General director
RQ_ACCOUNTANT
string
Chief accountant
RQ_CEO_NAME
string
Full name of the first leader
RQ_CEO_WORK_POS
string
Position of the first leader
RQ_CONTACT
string
Contact person
RQ_EMAIL
string
E-Mail
RQ_PHONE
string
Phone
RQ_FAX
string
Fax
RQ_IDENT_TYPE
crm_status
Method of identification
RQ_IDENT_DOC
string
Type of document
RQ_IDENT_DOC_SER
string
Series
RQ_IDENT_DOC_NUM
string
Number
RQ_IDENT_DOC_PERS_NUM
string
Personal number
RQ_IDENT_DOC_DATE
string
Date of issue
RQ_IDENT_DOC_ISSUED_BY
string
Issued by
RQ_IDENT_DOC_DEP_CODE
string
Department code
RQ_INN
string
Taxpayer Identification Number
RQ_KPP
string
Tax Registration Reason Code
RQ_USRLE
string
Handelsregisternummer (for country DE)
RQ_IFNS
string
Tax Authority
RQ_OGRN
string
Primary State Registration Number
RQ_OGRNIP
string
OGRNIP
RQ_OKPO
string
OKPO
RQ_OKTMO
string
OKTMO
RQ_OKVED
string
OKVED
RQ_EDRPOU
string
EDRPOU
RQ_DRFO
string
DRFO
RQ_KBE
string
KBE
RQ_IIN
string
IIN
RQ_BIN
string
BIN
RQ_ST_CERT_SER
string
Series of the state registration certificate
RQ_ST_CERT_NUM
string
Number of the state registration certificate
RQ_ST_CERT_DATE
string
Date of the state registration certificate
RQ_VAT_PAYER
char
VAT payer (for country UA).
Values
Y
or
N
are used
RQ_VAT_ID
string
VAT ID (identification number of VAT payer)
RQ_VAT_CERT_SER
string
Series of the VAT certificate
RQ_VAT_CERT_NUM
string
Number of the VAT certificate
RQ_VAT_CERT_DATE
string
Date of the VAT certificate
RQ_RESIDENCE_COUNTRY
string
Country of residence
RQ_BASE_DOC
string
Basis for action
RQ_REGON
string
REGON (for country PL)
RQ_KRS
string
KRS (for country PL)
RQ_PESEL
string
PESEL (for country PL)
RQ_LEGAL_FORM
string
Legal form (for country FR)
RQ_SIRET
string
Siret number (for country FR)
RQ_SIREN
string
Siren number (for country FR)
RQ_CAPITAL
string
Share capital (for country FR)
RQ_RCS
string
RCS (for country FR)
RQ_CNPJ
string
CNPJ (for country BR)
RQ_STATE_REG
string
State Registration (IE) (for country BR)
RQ_MNPL_REG
string
Municipal Registration (IM) (for country BR)
RQ_CPF
string
CPF (for country BR)
UF_CRM_...
Custom fields. For example,
UF_CRM_1694526604
.
Requisites can have a set of custom fields with types:
string
,
boolean
,
double
,
datetime
.
You can add a custom field to requisites using the method
crm.requisite.userfield.add
Which fields with the prefix
RQ_
can be specified?
When creating a requisite, only those fields with the prefix
RQ_
that are present in the requisite template linked to the created requisite (see the field
PRESET_ID
) should be specified. The values of other fields will be saved but will not be visible to the user.
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
'{"fields":{"ENTITY_TYPE_ID":4,"ENTITY_ID":1,"PRESET_ID":1,"NAME":"Organization","ACTIVE":"Y","ADDRESS_ONLY":"N","SORT":500,"RQ_COMPANY_NAME":"Ltd. \"QuickBooks and other similar platforms\"","RQ_COMPANY_FULL_NAME":"LIMITED LIABILITY COMPANY \"QuickBooks and other similar platforms\"","RQ_COMPANY_REG_DATE":"06.04.2007","RQ_DIRECTOR":"SMITH JOHN","RQ_INN":"7717586110","RQ_KPP":"770501001","RQ_OGRN":"5077746476209","UF_CRM_1707997209":"56","UF_CRM_1708012333":"Category 1","XML_ID":"5e4641fd-1dd9-11e6-b2f2-005056c00008"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"ENTITY_TYPE_ID":4,"ENTITY_ID":1,"PRESET_ID":1,"NAME":"Organization","ACTIVE":"Y","ADDRESS_ONLY":"N","SORT":500,"RQ_COMPANY_NAME":"Ltd. \"QuickBooks and other similar platforms\"","RQ_COMPANY_FULL_NAME":"LIMITED LIABILITY COMPANY \"QuickBooks and other similar platforms\"","RQ_COMPANY_REG_DATE":"06.04.2007","RQ_DIRECTOR":"SMITH JOHN","RQ_INN":"7717586110","RQ_KPP":"770501001","RQ_OGRN":"5077746476209","UF_CRM_1707997209":"56","UF_CRM_1708012333":"Category 1","XML_ID":"5e4641fd-1dd9-11e6-b2f2-005056c00008","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.add"
,
{
fields
:
{
"ENTITY_TYPE_ID"
:
4
,
"ENTITY_ID"
:
1
,
"PRESET_ID"
:
1
,
"NAME"
:
"Organization"
,
"ACTIVE"
:
"Y"
,
"ADDRESS_ONLY"
:
"N"
,
"SORT"
:
500
,
"RQ_COMPANY_NAME"
:
"Ltd. \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_FULL_NAME"
:
"LIMITED LIABILITY COMPANY \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_REG_DATE"
:
"06.04.2007"
,
"RQ_DIRECTOR"
:
"SMITH JOHN"
,
"RQ_INN"
:
"7717586110"
,
"RQ_KPP"
:
"770501001"
,
"RQ_OGRN"
:
"5077746476209"
,
"UF_CRM_1707997209"
:
"56"
,
"UF_CRM_1708012333"
:
"Category 1"
,
"XML_ID"
:
"5e4641fd-1dd9-11e6-b2f2-005056c00008"
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
"Requisite created with ID "
+ result);
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
'crm.requisite.add'
,
[
'fields'
=> [
'ENTITY_TYPE_ID'
=>
4
,
'ENTITY_ID'
=>
1
,
'PRESET_ID'
=>
1
,
'NAME'
=>
'Organization'
,
'ACTIVE'
=>
'Y'
,
'ADDRESS_ONLY'
=>
'N'
,
'SORT'
=>
500
,
"RQ_COMPANY_NAME"
=>
"Ltd. \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_FULL_NAME"
=>
"LIMITED LIABILITY COMPANY \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_REG_DATE"
=>
"06.04.2007"
,
"RQ_DIRECTOR"
=>
"SMITH JOHN"
,
'RQ_INN'
=>
'7717586110'
,
'RQ_KPP'
=>
'770501001'
,
'RQ_OGRN'
=>
'5077746476209'
,
'UF_CRM_1707997209'
=>
'56'
,
'UF_CRM_1708012333'
=>
'Category 1'
,
'XML_ID'
=>
'5e4641fd-1dd9-11e6-b2f2-005056c00008'
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
'Requisite created with ID '
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
'Error creating requisite: '
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
"crm.requisite.add"
,
{
fields
:
{
"ENTITY_TYPE_ID"
:
4
,
"ENTITY_ID"
:
1
,
"PRESET_ID"
:
1
,
"NAME"
:
"Organization"
,
"ACTIVE"
:
"Y"
,
"ADDRESS_ONLY"
:
"N"
,
"SORT"
:
500
,
"RQ_COMPANY_NAME"
:
"Ltd. \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_FULL_NAME"
:
"LIMITED LIABILITY COMPANY \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_REG_DATE"
:
"06.04.2007"
,
"RQ_DIRECTOR"
:
"SMITH JOHN"
,
"RQ_INN"
:
"7717586110"
,
"RQ_KPP"
:
"770501001"
,
"RQ_OGRN"
:
"5077746476209"
,
"UF_CRM_1707997209"
:
"56"
,
"UF_CRM_1708012333"
:
"Category 1"
,
"XML_ID"
:
"5e4641fd-1dd9-11e6-b2f2-005056c00008"
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
"Requisite created with ID "
+ result.
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
'crm.requisite.add'
,
[
'fields'
=> [
"ENTITY_TYPE_ID"
=>
4
,
"ENTITY_ID"
=>
1
,
"PRESET_ID"
=>
1
,
"NAME"
=>
"Organization"
,
"ACTIVE"
=>
"Y"
,
"ADDRESS_ONLY"
=>
"N"
,
"SORT"
=>
500
,
"RQ_COMPANY_NAME"
=>
"Ltd. \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_FULL_NAME"
=>
"LIMITED LIABILITY COMPANY \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_REG_DATE"
=>
"06.04.2007"
,
"RQ_DIRECTOR"
=>
"SMITH JOHN"
,
"RQ_INN"
=>
"7717586110"
,
"RQ_KPP"
=>
"770501001"
,
"RQ_OGRN"
=>
"5077746476209"
,
"UF_CRM_1707997209"
=>
"56"
,
"UF_CRM_1708012333"
=>
"Category 1"
,
"XML_ID"
=>
"5e4641fd-1dd9-11e6-b2f2-005056c00008"
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
Response on Success
Response on Success
HTTP status:
200
{
"result"
:
27
,
"time"
:
{
"start"
:
1716998748.040801
,
"finish"
:
1716998749.444508
,
"duration"
:
1.4037070274353027
,
"processing"
:
0.32904696464538574
,
"date_start"
:
"2024-05-29T18:05:48+02:00"
,
"date_finish"
:
"2024-05-29T18:05:49+02:00"
,
"operating"
:
0.32897305488586426
}
}
Returned Data
Returned Data
Name
type
Description
result
integer
Identifier of the created requisite
time
time
Information about the execution time of the request
Response on Error
Response on Error
HTTP status:
400
{
"error"
:
""
,
"error_description"
:
"ENTITY_TYPE_ID is not defined or invalid."
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
Empty string
ENTITY_TYPE_ID is not defined or invalid.
Identifier of the parent entity type is not defined or has an invalid value
Empty string
ENTITY_ID is not defined or invalid.
Identifier of the parent entity is not defined or has an invalid value
Empty string
PRESET_ID is not defined or invalid.
Identifier of the requisite template is not defined or has an invalid value
Empty string
Entity not found.
The entity for which the requisite is being created was not found
Empty string
Access denied.
Insufficient access permissions to add the requisite
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
About Universal Requisites
Update Requisite crm.requisite.update
Get Requisite by ID crm.requisite.get
Get a List of Requisites by Filter crm.requisite.list
Delete Requisite and Related Objects crm.requisite.delete
Get CRM Requisite Fields
Add a Company with Details via Web Form
Add a contact with details via a web form
Add a deal and company with requisites
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Update detail

---

## Update Requisite crm.requisite.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/universal/crm-requisite-update

Update Requisite crm.requisite.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Requisite crm.requisite.update
Method Parameters
Parameter fields
Code Examples
Response on Success
Returned Data
Response on Error
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method updates an existing requisite.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the requisite, can be obtained using the method
crm.requisite.list
fields
*
object
Set of requisite fields — an object of the form
"field": "value"[, ...]}
, the values of which need to be changed
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
NAME
*
string
Name of the requisite
CODE
string
Symbolic code of the requisite
XML_ID
string
External key, used for exchange operations.
Identifier of the external information base object.
The purpose of the field may change by the final developer
ORIGINATOR_ID
string
Identifier of the external information base.
The purpose of the field may change by the final developer
ACTIVE
char
Activity status.
Values
Y
or
N
are used.
Currently, the field does not actually affect anything
ADDRESS_ONLY
char
Status indicator when the requisite is used only for storing the address.
Values
Y
or
N
are used. When set to
Y
, the requisites are not displayed in the entity card, but the address is shown
SORT
integer
Sorting.
Order in the list of entity requisites when there are multiple
RQ_NAME
string
Full name
RQ_FIRST_NAME
string
First name
RQ_LAST_NAME
string
Last name
RQ_SECOND_NAME
string
Middle name
RQ_COMPANY_ID
string
Identifier of the organization
RQ_COMPANY_NAME
string
Short name of the organization
RQ_COMPANY_FULL_NAME
string
Full name of the organization
RQ_COMPANY_REG_DATE
string
Date of state registration
RQ_DIRECTOR
string
General director
RQ_ACCOUNTANT
string
Chief accountant
RQ_CEO_NAME
string
Full name of the first leader
RQ_CEO_WORK_POS
string
Position of the first leader
RQ_CONTACT
string
Contact person
RQ_EMAIL
string
E-Mail
RQ_PHONE
string
Phone
RQ_FAX
string
Fax
RQ_IDENT_TYPE
crm_status
Method of identification
RQ_IDENT_DOC
string
Type of document
RQ_IDENT_DOC_SER
string
Series
RQ_IDENT_DOC_NUM
string
Number
RQ_IDENT_DOC_PERS_NUM
string
Personal number
RQ_IDENT_DOC_DATE
string
Date of issue
RQ_IDENT_DOC_ISSUED_BY
string
Issued by
RQ_IDENT_DOC_DEP_CODE
string
Department code
RQ_INN
string
Taxpayer Identification Number
RQ_KPP
string
Tax Registration Reason Code
RQ_USRLE
string
Handelsregisternummer (for country DE)
RQ_IFNS
string
Tax Authority
RQ_OGRN
string
Primary State Registration Number
RQ_OGRNIP
string
Individual Entrepreneur Registration Number
RQ_OKPO
string
All-Russian Classifier of Enterprises and Organizations
RQ_OKTMO
string
All-Russian Classifier of Territorial Units
RQ_OKVED
string
All-Russian Classifier of Economic Activities
RQ_EDRPOU
string
Unified State Register of Enterprises and Organizations
RQ_DRFO
string
Tax Registration Number
RQ_KBE
string
Classification of Business Entities
RQ_IIN
string
Individual Identification Number
RQ_BIN
string
Business Identification Number
RQ_ST_CERT_SER
string
Series of the state registration certificate
RQ_ST_CERT_NUM
string
Number of the state registration certificate
RQ_ST_CERT_DATE
string
Date of the state registration certificate
RQ_VAT_PAYER
char
VAT payer (for country UA).
Values
Y
or
N
are used
RQ_VAT_ID
string
VAT ID (identification number of the VAT payer)
RQ_VAT_CERT_SER
string
Series of the VAT certificate
RQ_VAT_CERT_NUM
string
Number of the VAT certificate
RQ_VAT_CERT_DATE
string
Date of the VAT certificate
RQ_RESIDENCE_COUNTRY
string
Country of residence
RQ_BASE_DOC
string
Basis for action
RQ_REGON
string
REGON (for country PL)
RQ_KRS
string
KRS (for country PL)
RQ_PESEL
string
PESEL (for country PL)
RQ_LEGAL_FORM
string
Legal form (for country FR)
RQ_SIRET
string
Siret number (for country FR)
RQ_SIREN
string
Siren number (for country FR)
RQ_CAPITAL
string
Share capital (for country FR)
RQ_RCS
string
RCS (for country FR)
RQ_CNPJ
string
CNPJ (for country BR)
RQ_STATE_REG
string
State Registration (IE) (for country BR)
RQ_MNPL_REG
string
Municipal Registration (IM) (for country BR)
RQ_CPF
string
CPF (for country BR)
UF_CRM_...
Custom fields. For example,
UF_CRM_1694526604
.
Requisites can have a set of custom fields with types:
string
,
boolean
,
double
,
datetime
.
You can add a custom field to requisites using the method
crm.requisite.userfield.add
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
'{"id":27,"fields":{"RQ_OKPO":"80715150","RQ_OKTMO":"45381000000","UF_CRM_1707997209":"78","UF_CRM_1708012333":"Category 3"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":27,"fields":{"RQ_OKPO":"80715150","RQ_OKTMO":"45381000000","UF_CRM_1707997209":"78","UF_CRM_1708012333":"Category 3"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.update"
,
{
id
:
27
,
fields
:
{
"RQ_OKPO"
:
"80715150"
,
"RQ_OKTMO"
:
"45381000000"
,
"UF_CRM_1707997209"
:
"78"
,
"UF_CRM_1708012333"
:
"Category 3"
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
$response
=
$b24Service
->core
->
call
(
'crm.requisite.update'
,
[
'id'
=>
27
,
'fields'
=> [
'RQ_OKPO'
=>
'80715150'
,
'RQ_OKTMO'
=>
'45381000000'
,
'UF_CRM_1707997209'
=>
'78'
,
'UF_CRM_1708012333'
=>
'Category 3'
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
'Error updating requisite: '
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
"crm.requisite.update"
,
{
id
:
27
,
fields
:
{
"RQ_OKPO"
:
"80715150"
,
"RQ_OKTMO"
:
"45381000000"
,
"UF_CRM_1707997209"
:
"78"
,
"UF_CRM_1708012333"
:
"Category 3"
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
'crm.requisite.update'
,
[
'id'
=>
27
,
'fields'
=> [
'RQ_OKPO'
=>
'80715150'
,
'RQ_OKTMO'
=>
'45381000000'
,
'UF_CRM_1707997209'
=>
'78'
,
'UF_CRM_1708012333'
=>
'Category 3'
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
Response on Success
Response on Success
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
1717163055.335685
,
"finish"
:
1717163055.892722
,
"duration"
:
0.5570368766784668
,
"processing"
:
0.17116189002990723
,
"date_start"
:
"2024-05-31T15:44:15+02:00"
,
"date_finish"
:
"2024-05-31T15:44:15+02:00"
,
"operating"
:
0.17112517356872559
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Returns the value:
true
— requisite changed
false
— requisite not changed
time
time
Information about the request execution time
Response on Error
Response on Error
HTTP status:
400
{
"error"
:
""
,
"error_description"
:
"The Requisite with ID '57' is not found"
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
Empty string
The Requisite with ID '57' is not found
The requisite with the specified identifier was not found
Empty string
ID is not defined or invalid.
The requisite identifier is not specified or has an invalid value
Empty string
ENTITY_TYPE_ID is not defined or invalid.
The identifier of the parent entity type is not specified or has an invalid value
Empty string
ENTITY_ID is not defined or invalid.
The identifier of the parent entity is not specified or has an invalid value
Empty string
PRESET_ID is not defined or invalid.
The identifier of the requisite template is not specified or has an invalid value
Empty string
Access denied.
Insufficient access permissions to modify the requisite
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
About Universal Requisites
Add Requisite crm.requisite.add
Get Requisite by ID crm.requisite.get
Get a List of Requisites by Filter crm.requisite.list
Delete Requisite and Related Objects crm.requisite.delete
Get CRM Requisite Fields
Copied
Was the article helpful?
Yes
No
Previous
Add detail
Next
Get detail by id

---

## Get Requisite by ID crm.requisite.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/universal/crm-requisite-get

Get Requisite by ID crm.requisite.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Requisite by ID crm.requisite.get
Method Parameters
Code Examples
Successful Response
Returned Data
Error Response
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method retrieves the requisite by its identifier
id
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
Identifier of the requisite.
The identifier can be obtained using the
crm.requisite.list
method
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
'{"id":27}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":27,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.get
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.get"
,
{
id
:
27
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
'crm.requisite.get'
,
[
'id'
=>
27
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
'Error getting requisite: '
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
"crm.requisite.get"
,
{
id
:
27
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
'crm.requisite.get'
,
[
'id'
=>
27
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
Successful Response
Successful Response
HTTP Status:
200
{
"result"
:
{
"ID"
:
"27"
,
"ENTITY_TYPE_ID"
:
"4"
,
"ENTITY_ID"
:
"1"
,
"PRESET_ID"
:
"1"
,
"DATE_CREATE"
:
"2024-05-29T18:05:49+02:00"
,
"DATE_MODIFY"
:
""
,
"CREATED_BY_ID"
:
"1"
,
"MODIFY_BY_ID"
:
null
,
"NAME"
:
"Organization"
,
"CODE"
:
null
,
"XML_ID"
:
"5e4641fd-1dd9-11e6-b2f2-005056c00008"
,
"ORIGINATOR_ID"
:
null
,
"ACTIVE"
:
"Y"
,
"ADDRESS_ONLY"
:
"N"
,
"SORT"
:
"500"
,
"RQ_NAME"
:
null
,
"RQ_FIRST_NAME"
:
null
,
"RQ_LAST_NAME"
:
null
,
"RQ_SECOND_NAME"
:
null
,
"RQ_COMPANY_ID"
:
null
,
"RQ_COMPANY_NAME"
:
"Ltd. \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_FULL_NAME"
:
"LIMITED LIABILITY COMPANY \"QuickBooks and other similar platforms\""
,
"RQ_COMPANY_REG_DATE"
:
"06.04.2007"
,
"RQ_DIRECTOR"
:
"RYZHIKOV SERGEY VLADIMIROVICH"
,
"RQ_ACCOUNTANT"
:
null
,
"RQ_CEO_NAME"
:
null
,
"RQ_CEO_WORK_POS"
:
null
,
"RQ_CONTACT"
:
null
,
"RQ_EMAIL"
:
null
,
"RQ_PHONE"
:
null
,
"RQ_FAX"
:
null
,
"RQ_IDENT_TYPE"
:
null
,
"RQ_IDENT_DOC"
:
null
,
"RQ_IDENT_DOC_SER"
:
null
,
"RQ_IDENT_DOC_NUM"
:
null
,
"RQ_IDENT_DOC_PERS_NUM"
:
null
,
"RQ_IDENT_DOC_DATE"
:
null
,
"RQ_IDENT_DOC_ISSUED_BY"
:
null
,
"RQ_IDENT_DOC_DEP_CODE"
:
null
,
"RQ_INN"
:
"7717586110"
,
"RQ_KPP"
:
"770501001"
,
"RQ_USRLE"
:
null
,
"RQ_IFNS"
:
null
,
"RQ_OGRN"
:
"5077746476209"
,
"RQ_OGRNIP"
:
null
,
"RQ_OKPO"
:
null
,
"RQ_OKTMO"
:
null
,
"RQ_OKVED"
:
null
,
"RQ_EDRPOU"
:
null
,
"RQ_DRFO"
:
null
,
"RQ_KBE"
:
null
,
"RQ_IIN"
:
null
,
"RQ_BIN"
:
null
,
"RQ_ST_CERT_SER"
:
null
,
"RQ_ST_CERT_NUM"
:
null
,
"RQ_ST_CERT_DATE"
:
null
,
"RQ_VAT_PAYER"
:
"N"
,
"RQ_VAT_ID"
:
null
,
"RQ_VAT_CERT_SER"
:
null
,
"RQ_VAT_CERT_NUM"
:
null
,
"RQ_VAT_CERT_DATE"
:
null
,
"RQ_RESIDENCE_COUNTRY"
:
null
,
"RQ_BASE_DOC"
:
null
,
"RQ_REGON"
:
null
,
"RQ_KRS"
:
null
,
"RQ_PESEL"
:
null
,
"RQ_LEGAL_FORM"
:
null
,
"RQ_SIRET"
:
null
,
"RQ_SIREN"
:
null
,
"RQ_CAPITAL"
:
null
,
"RQ_RCS"
:
null
,
"RQ_CNPJ"
:
null
,
"RQ_STATE_REG"
:
null
,
"RQ_MNPL_REG"
:
null
,
"RQ_CPF"
:
null
}
,
"time"
:
{
"start"
:
1717078089.78188
,
"finish"
:
1717078090.270494
,
"duration"
:
0.4886140823364258
,
"processing"
:
0.09770989418029785
,
"date_start"
:
"2024-05-30T16:08:09+02:00"
,
"date_finish"
:
"2024-05-30T16:08:10+02:00"
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
Object
An object containing the values of
requisite fields
time
time
Information about the execution time of the request
Error Response
Error Response
HTTP Status:
400
{
"error"
:
""
,
"error_description"
:
"The Requisite with ID '27' is not found"
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
Empty string
The Requisite with ID '27' is not found
The requisite with the specified identifier was not found
Empty string
Access denied.
Insufficient access permissions to retrieve the requisite
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
About Universal Requisites
Add Requisite crm.requisite.add
Update Requisite crm.requisite.update
Get a List of Requisites by Filter crm.requisite.list
Delete Requisite and Related Objects crm.requisite.delete
Get CRM Requisite Fields
Copied
Was the article helpful?
Yes
No
Previous
Update detail
Next
Get list of details by filter

---

## Get a List of Requisites by Filter crm.requisite.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/universal/crm-requisite-list

Get a List of Requisites by Filter crm.requisite.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a List of Requisites by Filter crm.requisite.list
Method Parameters
Code Example
Successful Response
Returned Data
Error Response
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method retrieves a list of requisites based on a filter.
Method Parameters
Method Parameters
Name
type
Description
select
array
An array containing the list of fields to be selected (see
requisite fields
).
If not provided or an empty array is passed, all available requisite fields will be selected.
filter
object
An object for filtering the selected requisites in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
correspond to
requisite fields
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
symbol does not need to be included in the filter value. The search looks for the substring in any position of the string.
=%
— LIKE, substring search. The
%
symbol must be included in the value. Examples:
"mol%" — searching for values starting with "mol"
"%mol" — searching for values ending with "mol"
"%mol%" — searching for values where "mol" can be in any position.
%=
— LIKE (see description above)
!%
— NOT LIKE, substring search. The
%
symbol does not need to be included in the filter value. The search is performed from both sides.
!=%
— NOT LIKE, substring search. The
%
symbol must be included in the value. Examples:
"mol%" — searching for values not starting with "mol"
"%mol" — searching for values not ending with "mol"
"%mol%" — searching for values where the substring "mol" is not present in any position.
!%=
— NOT LIKE (see description above)
=
— equal, exact match (used by default)
!=
— not equal
!
— not equal
order
object
An object for sorting the selected requisites in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
correspond to
requisite fields
.
Possible values for
order
:
asc
— ascending order
desc
— descending order
start
integer
This parameter is used for pagination control.
The page size of results is always static: 50 records.
To select the second page of results, the value
50
must be passed. To select the third page of results, the value is
100
, and so on.
The formula for calculating the
start
parameter value:
start = (N-1) * 50
, where
N
is the desired page number
Code Example
Code Example
How to Use Examples in Documentation
Retrieving requisites by template ID
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
'{"order":{"DATE_CREATE":"ASC"},"filter":{"PRESET_ID":"1"},"select":["ENTITY_TYPE_ID","ENTITY_ID","ID","NAME"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"DATE_CREATE":"ASC"},"filter":{"PRESET_ID":"1"},"select":["ENTITY_TYPE_ID","ENTITY_ID","ID","NAME"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.list
BX24
.
callMethod
(
"crm.requisite.list"
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
"PRESET_ID"
:
"1"
},
select
: [
"ENTITY_TYPE_ID"
,
"ENTITY_ID"
,
"ID"
,
"NAME"
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
'crm.requisite.list'
,
[
'order'
=> [
"DATE_CREATE"
=>
"ASC"
],
'filter'
=> [
"PRESET_ID"
=>
"1"
],
'select'
=> [
"ENTITY_TYPE_ID"
,
"ENTITY_ID"
,
"ID"
,
"NAME"
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
Retrieving the value of a custom field in requisites
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
'{"order":{},"filter":{"ID":"51"},"select":["UF_CRM_1707997209"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{},"filter":{"ID":"51"},"select":["UF_CRM_1707997209"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.list
BX24
.
callMethod
(
"crm.requisite.list"
,
{
order
: {},
filter
: {
"ID"
:
"51"
},
// Requisite ID
select
: [
"UF_CRM_1707997209"
]
// Custom field ID
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
'crm.requisite.list'
,
[
'order'
=> [],
'filter'
=> [
'ID'
=>
'51'
],
'select'
=> [
'UF_CRM_1707997209'
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
Successful Response
Successful Response
HTTP status:
200
Response from example 1:
{
"result"
:
[
{
"ENTITY_TYPE_ID"
:
"4"
,
"ENTITY_ID"
:
"3027"
,
"ID"
:
"40"
,
"NAME"
:
"Organization"
}
,
{
"ENTITY_TYPE_ID"
:
"4"
,
"ENTITY_ID"
:
"3028"
,
"ID"
:
"41"
,
"NAME"
:
"Head Office Requisites"
}
,
{
"ENTITY_TYPE_ID"
:
"4"
,
"ENTITY_ID"
:
"3028"
,
"ID"
:
"42"
,
"NAME"
:
"Branch in Chernyakhovsk"
}
]
,
"total"
:
3
,
"time"
:
{
"start"
:
1717150154.197056
,
"finish"
:
1717150154.505106
,
"duration"
:
0.30804991722106934
,
"processing"
:
0.030454158782958984
,
"date_start"
:
"2024-05-31T12:09:14+02:00"
,
"date_finish"
:
"2024-05-31T12:09:14+02:00"
,
"operating"
:
0
}
}
Response from example 2:
{
"result"
:
[
{
"UF_CRM_1707997209"
:
"45"
}
]
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
1717151052.551011
,
"finish"
:
1717151052.94743
,
"duration"
:
0.39641880989074707
,
"processing"
:
0.028468847274780273
,
"date_start"
:
"2024-05-31T12:24:12+02:00"
,
"date_finish"
:
"2024-05-31T12:24:12+02:00"
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
An array of objects containing information from the selected requisites. Each element contains the selected
requisite fields
total
integer
The total number of records found
time
time
Information about the execution time of the request
Error Response
Error Response
HTTP status:
400
{
"error"
:
0
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
0
Access denied.
Insufficient access permissions to retrieve the list of requisites.
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
About Universal Requisites
Add Requisite crm.requisite.add
Update Requisite crm.requisite.update
Get Requisite by ID crm.requisite.get
Delete Requisite and Related Objects crm.requisite.delete
Get CRM Requisite Fields
Copied
Was the article helpful?
Yes
No
Previous
Get detail by id
Next
Delete detail and related objects

---

## Delete Requisite and Related Objects crm.requisite.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/universal/crm-requisite-delete

Delete Requisite and Related Objects crm.requisite.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Requisite and Related Objects crm.requisite.delete
Method Parameters
Code Examples
Successful Response
Returned Data
Error Response
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method deletes a requisite and all associated objects (links to other entities, addresses, bank details).
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the requisite.
The identifier can be obtained using the
crm.requisite.list
method
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
'{"id":27}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":27,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.delete'
,
{
id
:
27
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
$response
=
$b24Service
->core
->
call
(
'crm.requisite.delete'
,
[
'id'
=>
27
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
'Error deleting requisite: '
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
"crm.requisite.delete"
,
{
id
:
27
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
'crm.requisite.delete'
,
[
'id'
=>
27
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
Successful Response
Successful Response
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
1717166469.477791
,
"finish"
:
1717166470.500321
,
"duration"
:
1.0225298404693604
,
"processing"
:
0.3063521385192871
,
"date_start"
:
"2024-05-31T16:41:09+02:00"
,
"date_finish"
:
"2024-05-31T16:41:10+02:00"
,
"operating"
:
0.30628108978271484
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Returns the value:
true
— requisite deleted
false
— requisite not deleted
time
time
Information about the request execution time
Error Response
Error Response
HTTP status:
400
{
"error"
:
""
,
"error_description"
:
"The Requisite with ID '57' is not found"
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
Empty string
The Requisite with ID '57' is not found
The requisite with the specified identifier was not found
Empty string
ID is not defined or invalid.
The requisite identifier is not specified or has an invalid value
Empty string
Access denied.
Insufficient access permissions to delete the requisite
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
About Universal Requisites
Add Requisite crm.requisite.add
Update Requisite crm.requisite.update
Get Requisite by ID crm.requisite.get
Get a List of Requisites by Filter crm.requisite.list
Get CRM Requisite Fields
Copied
Was the article helpful?
Yes
No
Previous
Get list of details by filter
Next
Get detail fields

---

## Get CRM Requisite Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/universal/crm-requisite-fields

Get CRM Requisite Fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get CRM Requisite Fields
Code Examples
Successful Response
Returned Data
Attribute Descriptions
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method retrieves the description of the requisite fields.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.fields
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
https://**put_your_bitrix24_address**/rest/crm.requisite.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.fields'
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
'crm.requisite.fields'
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
'Error fetching requisite fields: '
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
"crm.requisite.fields"
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
'crm.requisite.fields'
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
Successful Response
Successful Response
HTTP Status:
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
"ENTITY_TYPE_ID"
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
"Entity Type ID"
}
,
"ENTITY_ID"
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
"Entity ID"
}
,
"PRESET_ID"
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
"Preset ID"
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
"Name"
}
,
"CODE"
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
"Code"
}
,
"XML_ID"
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
"External Code"
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
"ORIGINATOR_ID"
}
,
"ACTIVE"
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
"Active"
}
,
"ADDRESS_ONLY"
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
"ADDRESS_ONLY"
}
,
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
"Sort Order"
}
,
"RQ_NAME"
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
"Full Name"
}
,
"RQ_FIRST_NAME"
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
"RQ_LAST_NAME"
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
"RQ_SECOND_NAME"
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
"RQ_COMPANY_ID"
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
"RQ_COMPANY_ID"
}
,
"RQ_COMPANY_NAME"
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
"Abbreviated Organization Name"
}
,
"RQ_COMPANY_FULL_NAME"
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
"Full Organization Name"
}
,
"RQ_COMPANY_REG_DATE"
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
"State Registration Date"
}
,
"RQ_DIRECTOR"
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
"General Director"
}
,
"RQ_ACCOUNTANT"
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
"Chief Accountant"
}
,
"RQ_CEO_NAME"
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
"RQ_CEO_NAME"
}
,
"RQ_CEO_WORK_POS"
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
"RQ_CEO_WORK_POS"
}
,
"RQ_CONTACT"
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
"Contact Person"
}
,
"RQ_EMAIL"
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
"E-Mail"
}
,
"RQ_PHONE"
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
"Phone"
}
,
"RQ_FAX"
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
"Fax"
}
,
"RQ_IDENT_TYPE"
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
[
"RQ_IDENT_TYPE_CO"
]
,
"title"
:
"RQ_IDENT_TYPE"
}
,
"RQ_IDENT_DOC"
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
"Document Type"
}
,
"RQ_IDENT_DOC_SER"
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
"Series"
}
,
"RQ_IDENT_DOC_NUM"
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
"Number"
}
,
"RQ_IDENT_DOC_PERS_NUM"
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
"RQ_IDENT_DOC_PERS_NUM"
}
,
"RQ_IDENT_DOC_DATE"
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
"Issue Date"
}
,
"RQ_IDENT_DOC_ISSUED_BY"
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
"Issued By"
}
,
"RQ_IDENT_DOC_DEP_CODE"
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
"Department Code"
}
,
"RQ_INN"
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
"INN"
}
,
"RQ_KPP"
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
"KPP"
}
,
"RQ_USRLE"
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
"RQ_USRLE"
}
,
"RQ_IFNS"
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
"IFNS"
}
,
"RQ_OGRN"
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
"OGRN"
}
,
"RQ_OGRNIP"
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
"OGRNIP"
}
,
"RQ_OKPO"
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
"OKPO"
}
,
"RQ_OKTMO"
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
"OKTMO"
}
,
"RQ_OKVED"
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
"OKVED"
}
,
"RQ_EDRPOU"
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
"RQ_EDRPOU"
}
,
"RQ_DRFO"
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
"RQ_DRFO"
}
,
"RQ_KBE"
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
"RQ_KBE"
}
,
"RQ_IIN"
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
"RQ_IIN"
}
,
"RQ_BIN"
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
"RQ_BIN"
}
,
"RQ_ST_CERT_SER"
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
"Certificate Series of State Registration"
}
,
"RQ_ST_CERT_NUM"
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
"Certificate Number of State Registration"
}
,
"RQ_ST_CERT_DATE"
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
"Date of State Registration Certificate"
}
,
"RQ_VAT_PAYER"
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
"RQ_VAT_PAYER"
}
,
"RQ_VAT_ID"
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
"RQ_VAT_ID"
}
,
"RQ_VAT_CERT_SER"
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
"RQ_VAT_CERT_SER"
}
,
"RQ_VAT_CERT_NUM"
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
"RQ_VAT_CERT_NUM"
}
,
"RQ_VAT_CERT_DATE"
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
"RQ_VAT_CERT_DATE"
}
,
"RQ_RESIDENCE_COUNTRY"
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
"RQ_RESIDENCE_COUNTRY"
}
,
"RQ_BASE_DOC"
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
"RQ_BASE_DOC"
}
,
"RQ_REGON"
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
"RQ_REGON"
}
,
"RQ_KRS"
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
"RQ_KRS"
}
,
"RQ_PESEL"
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
"RQ_PESEL"
}
,
"RQ_LEGAL_FORM"
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
"RQ_LEGAL_FORM"
}
,
"RQ_SIRET"
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
"RQ_SIRET"
}
,
"RQ_SIREN"
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
"RQ_SIREN"
}
,
"RQ_CAPITAL"
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
"RQ_CAPITAL"
}
,
"RQ_RCS"
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
"RQ_RCS"
}
,
"RQ_CNPJ"
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
"RQ_CNPJ"
}
,
"RQ_STATE_REG"
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
"RQ_STATE_REG"
}
,
"RQ_MNPL_REG"
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
"RQ_MNPL_REG"
}
,
"RQ_CPF"
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
"RQ_CPF"
}
,
"UF_CRM_1694526604"
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
true
,
"title"
:
"UF_CRM_1694526604"
,
"listLabel"
:
"PP - String"
,
"formLabel"
:
"PP - String"
,
"filterLabel"
:
"PP - String"
,
"settings"
:
{
"SIZE"
:
20
,
"ROWS"
:
1
,
"REGEXP"
:
""
,
"MIN_LENGTH"
:
0
,
"MAX_LENGTH"
:
0
,
"DEFAULT_VALUE"
:
null
}
}
,
"UF_CRM_1707997209"
:
{
"type"
:
"double"
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
true
,
"title"
:
"UF_CRM_1707997209"
,
"listLabel"
:
"PP - Number"
,
"formLabel"
:
"PP - Number"
,
"filterLabel"
:
"PP - Number"
,
"settings"
:
{
"PRECISION"
:
2
,
"SIZE"
:
20
,
"MIN_VALUE"
:
0
,
"MAX_VALUE"
:
0
,
"DEFAULT_VALUE"
:
null
}
}
,
"UF_CRM_1707997236"
:
{
"type"
:
"boolean"
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
true
,
"title"
:
"UF_CRM_1707997236"
,
"listLabel"
:
"PP - Yes/No"
,
"formLabel"
:
"PP - Yes/No"
,
"filterLabel"
:
"PP - Yes/No"
,
"settings"
:
{
"DEFAULT_VALUE"
:
0
,
"DISPLAY"
:
"CHECKBOX"
,
"LABEL"
:
[
""
,
""
]
,
"LABEL_CHECKBOX"
:
"PP - Yes/No"
}
}
,
"UF_CRM_1707997253"
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
true
,
"title"
:
"UF_CRM_1707997253"
,
"listLabel"
:
"PP - Date"
,
"formLabel"
:
"PP - Date"
,
"filterLabel"
:
"PP - Date"
,
"settings"
:
{
"DEFAULT_VALUE"
:
{
"TYPE"
:
"NONE"
,
"VALUE"
:
""
}
,
"USE_SECOND"
:
"Y"
,
"USE_TIMEZONE"
:
"N"
}
}
}
,
"time"
:
{
"start"
:
1716902185.003805
,
"finish"
:
1716902185.379388
,
"duration"
:
0.3755831718444824
,
"processing"
:
0.016958951950073242
,
"date_start"
:
"2024-05-28T15:16:25+02:00"
,
"date_finish"
:
"2024-05-28T15:16:25+02:00"
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
An object in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field
is the identifier of the
requisite field
, and
value
is an object with
field attributes
time
time
Information about the execution time of the request
Attribute Descriptions
Attribute Descriptions
Attribute Purpose
Description
type
string
Field type
isRequired
boolean
Required attribute
true
— yes
false
— no
isReadOnly
boolean
Read-only attribute
true
— yes
false
— no
isImmutable
boolean
Immutable attribute
true
— yes
false
— no
isMultiple
boolean
Multi-field attribute
true
— yes
false
— no
isDynamic
boolean
Custom attribute
true
— yes
false
— no
title
string
Field identifier
listLabel
string
Custom field attribute. Contains the field name in lists
formLabel
string
Custom field attribute. Contains the field name in the detail form
filterLabel
string
Custom field attribute. Contains the field name in the filter
settings
object
Custom field attribute. An object with specific settings for a particular field type. See
custom requisite fields
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
About Universal Requisites
Add Requisite crm.requisite.add
Update Requisite crm.requisite.update
Get Requisite by ID crm.requisite.get
Get a List of Requisites by Filter crm.requisite.list
Delete Requisite and Related Objects crm.requisite.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete detail and related objects
Next
Overview of Methods

---

## About Custom Fields for Requisites

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/user-fields/index

About Custom Fields for Requisites | Bitrix24 REST API and Marketplace Applications
Fields Describing a Custom Field for Requisites
About Custom Fields for Requisites
Fields Describing a Custom Field for Requisites
Overview of Methods
Scope:
crm
Who can execute methods: any user
This section presents methods for working with custom fields for requisites. Custom fields can only be created for requisites of the following types:
string
,
boolean
,
double
,
datetime
.
For a description of general methods for working with custom fields, see the section
Custom Fields in CRM
.
Fields Describing a Custom Field for Requisites
Fields Describing a Custom Field for Requisites
Name
type
Description
Read
Write
Required
Immutable
Multiple
ID
int
Identifier of the custom field
Yes
No
No
No
No
ENTITY_ID
string
Identifier of the entity to which the custom field belongs. For requisites, this is always
CRM_REQUISITE
Yes
Yes
Yes
Yes
No
FIELD_NAME
string
Symbolic code. For requisites, it always starts with the prefix
UF_CRM_
Yes
Yes
Yes
Yes
No
USER_TYPE_ID
string
Data type (
string
,
boolean
,
double
or
datetime
)
Yes
Yes
Yes
Yes
No
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information base.
The purpose of the field may change by the final developer
Yes
Yes
No
No
No
SORT
int
Sorting
Yes
Yes
No
No
No
MULTIPLE
char
Indicator of multiplicity. Possible values:
Y
— yes
N
— no
MANDATORY
char
Indicator of necessity. Possible values:
Y
— yes
N
— no
SHOW_FILTER
char
Show in the list filter. Possible values:
N
— do not show
I
— exact match
E
— mask
S
— substring
SHOW_IN_LIST
char
Show in the list. Possible values:
Y
— yes
N
— no
EDIT_IN_LIST
char
Allow user editing. Possible values:
Y
— yes
N
— no
IS_SEARCHABLE
char
Are the field values included in the search. Possible values:
Y
— yes
N
— no
EDIT_FORM_LABEL
string
Label in the edit form
Yes
Yes
No
No
No
LIST_COLUMN_LABEL
string
Header in the list
Yes
Yes
No
No
No
LIST_FILTER_LABEL
string
Filter label in the list
Yes
Yes
No
No
No
ERROR_MESSAGE
string
Error message
Yes
Yes
No
No
No
HELP_MESSAGE
string
Help
Yes
Yes
No
No
No
LIST
uf_enum_element
List elements. For detailed information, see the section
Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields
Yes
Yes
No
No
Yes
SETTINGS
object
Additional settings (dependent on type). For detailed information, see the section
Get the field settings description for the custom field type crm.userfield.settings.fields
Yes
Yes
No
No
No
Overview of Methods
Overview of Methods
Method
Description
crm.requisite.userfield.add.md
Creates a new custom field for a requisite
crm.requisite.userfield.update.md
Modifies an existing custom field for a requisite
crm.requisite.userfield.get.md
Returns a custom field for a requisite by identifier
crm.requisite.userfield.list.md
Returns a list of custom fields for requisites by filter
crm.requisite.userfield.delete.md
Deletes a custom field for a requisite
Copied
Was the article helpful?
Yes
No
Previous
Get Description of Bank Detail Fields
Next
Create a New Custom Requisite Field

---

## Create a New Custom Field for crm.requisite.userfield.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/user-fields/crm-requisite-userfield-add

Create a New Custom Field for crm.requisite.userfield.add | Bitrix24 REST API and Marketplace Applications
Create a New Custom Field for crm.requisite.userfield.add
Create a New Custom Field for crm.requisite.userfield.add
Method Parameters
Parameter fields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method creates a new custom field for the requisite.
Limitations for the custom field symbolic code
The system limitation for the field name is 20 characters. The custom field name always has the prefix
UF_CRM_
, meaning the actual length of the name is 13 characters.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
A set of fields — an object of the form
{"field": "value"[, ...]}
for adding a custom requisite field
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
ENTITY_ID
*
string
The identifier of the entity to which the custom field belongs. For requisites, this is always
CRM_REQUISITE
FIELD_NAME
*
string
Symbolic code. For requisites, it always starts with the prefix
UF_CRM_
USER_TYPE_ID
*
string
Data type (
string
,
boolean
,
double
, or
datetime
)
XML_ID
string
External key. Used for exchange operations. Identifier of the external information base object.
The purpose of the field may change by the final developer
SORT
int
Sorting
MULTIPLE
char
Multiplicity indicator. Possible values:
Y
— yes
N
— no
Defaults to
N
MANDATORY
char
Mandatory indicator. Possible values:
Y
— yes
N
— no
Defaults to
N
SHOW_FILTER
char
Whether to show in the list filter. Possible values:
N
— do not show
I
— exact match
E
— mask
S
— substring
Defaults to
N
SHOW_IN_LIST
char
Whether to show in the list. Possible values:
Y
— yes
N
— no
Defaults to
Y
EDIT_IN_LIST
char
Whether to allow editing by the user. Possible values:
Y
— yes
N
— no
Defaults to
Y
IS_SEARCHABLE
char
Whether the field values participate in the search. Possible values:
Y
— yes
N
— no
Defaults to
N
EDIT_FORM_LABEL
string
Label in the edit form
LIST_COLUMN_LABEL
string
Header in the list
LIST_FILTER_LABEL
string
Filter label in the list
ERROR_MESSAGE
string
Error message
HELP_MESSAGE
string
Help
LIST
uf_enum_element
List elements. For more details, see the section
Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields
SETTINGS
object
Additional settings (dependent on the type). For more details, see the section
Get the field settings description for the custom field type crm.userfield.settings.fields
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
'{"fields":{"USER_TYPE_ID":"string","ENTITY_ID":"CRM_REQUISITE","SORT":100,"MULTIPLE":"N","MANDATORY":"N","SHOW_FILTER":"E","SHOW_IN_LIST":"Y","EDIT_FORM_LABEL":"PP - String","LIST_COLUMN_LABEL":"PP - String","LIST_FILTER_LABEL":"PP - String","FIELD_NAME":"NEWTECH_v1_STRING"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.userfield.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"USER_TYPE_ID":"string","ENTITY_ID":"CRM_REQUISITE","SORT":100,"MULTIPLE":"N","MANDATORY":"N","SHOW_FILTER":"E","SHOW_IN_LIST":"Y","EDIT_FORM_LABEL":"PP - String","LIST_COLUMN_LABEL":"PP - String","LIST_FILTER_LABEL":"PP - String","FIELD_NAME":"NEWTECH_v1_STRING"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.userfield.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.userfield.add"
,
{
fields
:
{
"USER_TYPE_ID"
:
"string"
,
"ENTITY_ID"
:
"CRM_REQUISITE"
,
"SORT"
:
100
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"E"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_FORM_LABEL"
:
"PP - String"
,
"LIST_COLUMN_LABEL"
:
"PP - String"
,
"LIST_FILTER_LABEL"
:
"PP - String"
,
"FIELD_NAME"
:
"NEWTECH_v1_STRING"
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
'crm.requisite.userfield.add'
,
[
'fields'
=> [
'USER_TYPE_ID'
=>
'string'
,
'ENTITY_ID'
=>
'CRM_REQUISITE'
,
'SORT'
=>
100
,
'MULTIPLE'
=>
'N'
,
'MANDATORY'
=>
'N'
,
'SHOW_FILTER'
=>
'E'
,
'SHOW_IN_LIST'
=>
'Y'
,
'EDIT_FORM_LABEL'
=>
'PP - String'
,
'LIST_COLUMN_LABEL'
=>
'PP - String'
,
'LIST_FILTER_LABEL'
=>
'PP - String'
,
'FIELD_NAME'
=>
'NEWTECH_v1_STRING'
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
'Error adding user field: '
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
"crm.requisite.userfield.add"
,
{
fields
:
{
"USER_TYPE_ID"
:
"string"
,
"ENTITY_ID"
:
"CRM_REQUISITE"
,
"SORT"
:
100
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"E"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_FORM_LABEL"
:
"PP - String"
,
"LIST_COLUMN_LABEL"
:
"PP - String"
,
"LIST_FILTER_LABEL"
:
"PP - String"
,
"FIELD_NAME"
:
"NEWTECH_v1_STRING"
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
'crm.requisite.userfield.add'
,
[
'fields'
=> [
'USER_TYPE_ID'
=>
'string'
,
'ENTITY_ID'
=>
'CRM_REQUISITE'
,
'SORT'
=>
100
,
'MULTIPLE'
=>
'N'
,
'MANDATORY'
=>
'N'
,
'SHOW_FILTER'
=>
'E'
,
'SHOW_IN_LIST'
=>
'Y'
,
'EDIT_FORM_LABEL'
=>
'PP - String'
,
'LIST_COLUMN_LABEL'
=>
'PP - String'
,
'LIST_FILTER_LABEL'
=>
'PP - String'
,
'FIELD_NAME'
=>
'NEWTECH_v1_STRING'
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
235
,
"time"
:
{
"start"
:
1717681176.885836
,
"finish"
:
1717681177.353738
,
"duration"
:
0.46790218353271484
,
"processing"
:
0.084564208984375
,
"date_start"
:
"2024-06-06T15:39:36+02:00"
,
"date_finish"
:
"2024-06-06T15:39:37+02:00"
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
Identifier of the created custom field
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
"ERROR_CORE"
,
"error_description"
:
"Field UF_CRM_NEWTECH_V1_STRING for object CRM_REQUISITE already exists."
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
ERROR_CORE
Field UF_CRM_NEWTECH_V1_STRING for object CRM_REQUISITE already exists
Attempt to recreate a custom field with the same symbolic code
Empty string
The 'USER_TYPE_ID' field is not found
Data type for the custom field not specified
Empty string
The 'FIELD_NAME' field is not found
Symbolic code for the custom field not specified
Empty string
Access denied
Insufficient access permissions to add a custom field
ERROR_CORE
Fail to create new user field
Failed to create a custom field
ERROR_CORE
Fail to save enumeration field values
Failed to save values for the custom list-type field (e.g., when there is a duplication of the external key of one of the values)
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
Update Custom Field of Requisite crm.requisite.userfield.update
Get User Field by ID crm.requisite.userfield.get
Get a list of custom fields of the requisite by filter crm.requisite.userfield.list
Delete User Field of Requisite crm.requisite.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update a Custom Requisite Field

---

## Update Custom Field of Requisite crm.requisite.userfield.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/user-fields/crm-requisite-userfield-update

Update Custom Field of Requisite crm.requisite.userfield.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Custom Field of Requisite crm.requisite.userfield.update
Method Parameters
Parameter fields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method updates an existing custom field of a requisite.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the custom field. Can be obtained using the method
crm.requisite.userfield.list
fields
*
object
Set of fields — an object of the form
{"field": "value"[, ...]}
, the values of which need to be changed
Parameter fields
Parameter fields
Name
type
Description
XML_ID
string
External key. Used for data exchange operations. Identifier of the object in the external information base.
The purpose of the field may change by the final developer
SORT
integer
Sorting
MULTIPLE
char
Multiplicity indicator. Possible values:
Y
— yes
N
— no
MANDATORY
char
Mandatory indicator. Possible values:
Y
— yes
N
— no
SHOW_FILTER
char
Show in the list filter. Possible values:
N
— do not show
I
— exact match
E
— mask
S
— substring
SHOW_IN_LIST
char
Show in the list. Possible values:
Y
— yes
N
— no
EDIT_IN_LIST
char
Allow user editing. Possible values:
Y
— yes
N
— no
IS_SEARCHABLE
char
Are the field values included in the search. Possible values:
Y
— yes
N
— no
EDIT_FORM_LABEL
string
Label in the edit form
LIST_COLUMN_LABEL
string
Header in the list
LIST_FILTER_LABEL
string
Filter label in the list
ERROR_MESSAGE
string
Error message
HELP_MESSAGE
string
Help
LIST
uf_enum_element
List elements. For detailed information, see the section
Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields
SETTINGS
object
Additional settings (depend on the type). For detailed information, see the section
Get the field settings description for the custom field type crm.userfield.settings.fields
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
'{"id":235,"fields":{"EDIT_FORM_LABEL":"Category","LIST_COLUMN_LABEL":"Category","LIST_FILTER_LABEL":"Category"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.userfield.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":235,"fields":{"EDIT_FORM_LABEL":"Category","LIST_COLUMN_LABEL":"Category","LIST_FILTER_LABEL":"Category"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.userfield.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.userfield.update"
,
{
id
:
235
,
fields
:
{
"EDIT_FORM_LABEL"
: title,
"LIST_COLUMN_LABEL"
: title,
"LIST_FILTER_LABEL"
: title
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
$title
=
"Category"
;
try
{
$response
=
$b24Service
->core
->
call
(
'crm.requisite.userfield.update'
,
[
'id'
=>
235
,
'fields'
=> [
'EDIT_FORM_LABEL'
=>
$title
,
'LIST_COLUMN_LABEL'
=>
$title
,
'LIST_FILTER_LABEL'
=>
$title
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
'Error updating user field: '
.
$e
->
getMessage
();
}
const
title =
"Category"
;
BX24
.
callMethod
(
"crm.requisite.userfield.update"
,
{
id
:
235
,
fields
:
{
"EDIT_FORM_LABEL"
: title,
"LIST_COLUMN_LABEL"
: title,
"LIST_FILTER_LABEL"
: title
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
require_once
(
'crest.php'
);
$title
=
"Category"
;
$result
=
CRest
::
call
(
'crm.requisite.userfield.update'
,
[
'id'
=>
235
,
'fields'
=>
[
'EDIT_FORM_LABEL'
=>
$title
,
'LIST_COLUMN_LABEL'
=>
$title
,
'LIST_FILTER_LABEL'
=>
$title
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
1717769551.504986
,
"finish"
:
1717769551.817433
,
"duration"
:
0.31244707107543945
,
"processing"
:
0.04784202575683594
,
"date_start"
:
"2024-06-07T16:12:31+02:00"
,
"date_finish"
:
"2024-06-07T16:12:31+02:00"
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
Result of updating the custom field of the requisite:
true — updated
false — not updated
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
""
,
"error_description"
:
"The entity with ID '235' is not found."
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
Empty string
Operation is not allowed. Entity ID is not defined
Custom field with the specified identifier not found
Empty string
The entity with ID '235' is not found
Custom field with the specified identifier not found
Empty string
ID is not defined or invalid
Identifier of the custom field is not specified or has an invalid value
Empty string
Access denied
Insufficient access permissions to modify the custom field
ERROR_CORE
Fail to update user field
Failed to update the custom field
ERROR_CORE
Fail to save enumeration field values
Failed to save values of the custom list-type field (e.g., when a duplicate external key of one of the values occurred)
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
Create a New Custom Field for crm.requisite.userfield.add
Get User Field by ID crm.requisite.userfield.get
Get a list of custom fields of the requisite by filter crm.requisite.userfield.list
Delete User Field of Requisite crm.requisite.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Create a New Custom Requisite Field
Next
Get a Custom Field by ID

---

## Get User Field by ID crm.requisite.userfield.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/user-fields/crm-requisite-userfield-get

Get User Field by ID crm.requisite.userfield.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get User Field by ID crm.requisite.userfield.get
Method Parameters
Code Examples
Response Handling
Returned Data
Description of User Field of the Requisite
Error Handling
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns the user field of the requisite by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the user field. Can be obtained using the method
crm.requisite.userfield.list
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
'{"id":235}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.userfield.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":235,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.userfield.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.userfield.get'
,
{
id
:
235
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
'crm.requisite.userfield.get'
,
[
'id'
=>
235
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
'Error getting user field: '
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
"crm.requisite.userfield.get"
,
{
id
:
235
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
'crm.requisite.userfield.get'
,
[
'id'
=>
235
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
"235"
,
"ENTITY_ID"
:
"CRM_REQUISITE"
,
"FIELD_NAME"
:
"UF_CRM_NEWTECH_V1_STRING"
,
"USER_TYPE_ID"
:
"string"
,
"XML_ID"
:
null
,
"SORT"
:
"100"
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"N"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_IN_LIST"
:
"Y"
,
"IS_SEARCHABLE"
:
"N"
,
"SETTINGS"
:
{
"SIZE"
:
20
,
"ROWS"
:
1
,
"REGEXP"
:
""
,
"MIN_LENGTH"
:
0
,
"MAX_LENGTH"
:
0
,
"DEFAULT_VALUE"
:
""
}
,
"EDIT_FORM_LABEL"
:
{
"en"
:
"PP - String"
,
"de"
:
"PP - String"
}
,
"LIST_COLUMN_LABEL"
:
{
"en"
:
"PP - String"
,
"de"
:
"PP - String"
}
,
"LIST_FILTER_LABEL"
:
{
"en"
:
"PP - String"
,
"de"
:
"PP - String"
}
,
"ERROR_MESSAGE"
:
{
"en"
:
"UF_CRM_NEWTECH_V1_STRING"
,
"de"
:
"UF_CRM_NEWTECH_V1_STRING"
}
,
"HELP_MESSAGE"
:
{
"en"
:
"UF_CRM_NEWTECH_V1_STRING"
,
"de"
:
"UF_CRM_NEWTECH_V1_STRING"
}
}
,
"time"
:
{
"start"
:
1717686921.82579
,
"finish"
:
1717686922.874864
,
"duration"
:
1.0490741729736328
,
"processing"
:
0.05396890640258789
,
"date_start"
:
"2024-06-06T17:15:21+02:00"
,
"date_finish"
:
"2024-06-06T17:15:22+02:00"
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
Object containing field values describing the user field of the requisite
time
time
Information about the execution time of the request
Description of User Field of the Requisite
Description of User Field of the Requisite
Name
type
Description
ID
int
Identifier of the user field
ENTITY_ID
string
Identifier of the entity to which the user field belongs. For requisites, this is always
CRM_REQUISITE
FIELD_NAME
string
Symbolic code. For requisites, it always starts with the prefix
UF_CRM_
USER_TYPE_ID
string
Data type (
string
,
boolean
,
double
or
datetime
)
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information base.
The purpose of the field may change by the final developer
SORT
int
Sorting
MULTIPLE
char
Multiplicity indicator. Possible values:
Y
— yes
N
— no
MANDATORY
char
Mandatory indicator. Possible values:
Y
— yes
N
— no
SHOW_FILTER
char
Whether to show in the list filter. Possible values:
N
— do not show
I
— exact match
E
— mask
S
— substring
SHOW_IN_LIST
char
Whether to show in the list. Possible values:
Y
— yes
N
— no
EDIT_IN_LIST
char
Whether to allow editing by the user. Possible values:
Y
— yes
N
— no
IS_SEARCHABLE
char
Whether the field values participate in search. Possible values:
Y
— yes
N
— no
EDIT_FORM_LABEL
string
Label in the edit form
LIST_COLUMN_LABEL
string
Header in the list
LIST_FILTER_LABEL
string
Filter label in the list
ERROR_MESSAGE
string
Error message
HELP_MESSAGE
string
Help
LIST
uf_enum_element
List elements. For detailed information, see the section
Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields
SETTINGS
object
Additional settings (dependent on type). For detailed information, see the section
Get the field settings description for the custom field type crm.userfield.settings.fields
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
"ERROR_NOT_FOUND"
,
"error_description"
:
"The entity with ID '235' is not found."
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
Empty string
ID is not defined or invalid
The identifier of the user field is not set or has an invalid value
ERROR_NOT_FOUND
The entity with ID '235' is not found
The user field with the specified identifier was not found
Empty string
Access denied
Insufficient access permissions to retrieve the user field
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
Create a New Custom Field for crm.requisite.userfield.add
Update Custom Field of Requisite crm.requisite.userfield.update
Get a list of custom fields of the requisite by filter crm.requisite.userfield.list
Delete User Field of Requisite crm.requisite.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Update a Custom Requisite Field
Next
Get a List of Custom Requisite Fields by Filter

---

## Get a list of custom fields of the requisite by filter crm.requisite.userfield.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/user-fields/crm-requisite-userfield-list

Get a list of custom fields of the requisite by filter crm.requisite.userfield.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of custom fields of the requisite by filter crm.requisite.userfield.list
Method Parameters
Description of custom field of requisite
Code Examples
Response Handling
Returned Data
Error Handling
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a list of custom fields of the requisite based on the filter.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
order
object
Object for sorting the selected custom fields in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
:
ID
ENTITY_ID
FIELD_NAME
USER_TYPE_ID
XML_ID
SORT
Possible values for
order
:
asc — in ascending order
desc — in descending order
filter
object
Object for filtering the selected requisites in the format
{"field_1": "value_1", ... "field_N": "value_N"}
. This method's filter only supports simple value comparisons.
Possible values for
field
:
ID
ENTITY_ID
FIELD_NAME
USER_TYPE_ID
XML_ID
SORT
MULTIPLE
MANDATORY
SHOW_FILTER
SHOW_IN_LIST
EDIT_IN_LIST
IS_SEARCHABLE
LANG
Additional prefixes in keys that clarify filter behavior are not provided. The
equals
operation is always used.
Possible values for
value
correspond to
field descriptions
Description of custom field of requisite
Description of custom field of requisite
Name
type
Description
ID
int
Identifier of the custom field
ENTITY_ID
string
Identifier of the entity to which the custom field belongs. For requisites, this is always
CRM_REQUISITE
FIELD_NAME
*
string
Symbolic code. For requisites, it always starts with the prefix
UF_CRM_
USER_TYPE_ID
*
string
Data type (
string
,
boolean
,
double
or
datetime
)
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information base.
The purpose of the field may change by the final developer
SORT
int
Sorting
MULTIPLE
char
Multiplicity indicator. Possible values:
Y
— yes
N
— no
MANDATORY
char
Mandatory indicator. Possible values:
Y
— yes
N
— no
SHOW_FILTER
char
Show in the list filter. Possible values:
N
— do not show
I
— exact match
E
— mask
S
— substring
SHOW_IN_LIST
char
Show in the list. Possible values:
Y
— yes
N
— no
EDIT_IN_LIST
char
Allow user editing. Possible values:
Y
— yes
N
— no
IS_SEARCHABLE
char
Are field values included in search. Possible values:
Y
— yes
N
— no
EDIT_FORM_LABEL
string
Label in the edit form
LIST_COLUMN_LABEL
string
Header in the list
LIST_FILTER_LABEL
string
Filter label in the list
ERROR_MESSAGE
string
Error message
HELP_MESSAGE
string
Help
LIST
uf_enum_element
List elements. For detailed information, see the section
Get Field Descriptions for Custom Field Type "Enumeration" (List) crm.userfield.enumeration.fields
SETTINGS
object
Additional settings (depend on type). For detailed information, see the section
Get the field settings description for the custom field type crm.userfield.settings.fields
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
'{"order":{"SORT":"ASC"},"filter":{"MANDATORY":"N","LANG":"en"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.userfield.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"SORT":"ASC"},"filter":{"MANDATORY":"N","LANG":"en"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.userfield.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.requisite.userfield.list'
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
,
"LANG"
:
"en"
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
// fetchListMethod is preferred when working with large data sets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.requisite.userfield.list'
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
,
"LANG"
:
"en"
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.userfield.list'
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
,
"LANG"
:
"en"
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
'crm.requisite.userfield.list'
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
,
'LANG'
=>
'en'
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
'Error listing requisite user fields: '
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
"crm.requisite.userfield.list"
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
,
"LANG"
:
"en"
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
'crm.requisite.userfield.list'
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
,
'LANG'
:
'en'
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
"232"
,
"ENTITY_ID"
:
"CRM_REQUISITE"
,
"FIELD_NAME"
:
"UF_CRM_NEWTECH_V1_BOOLEAN"
,
"USER_TYPE_ID"
:
"boolean"
,
"XML_ID"
:
null
,
"SORT"
:
"100"
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"E"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_IN_LIST"
:
"Y"
,
"IS_SEARCHABLE"
:
"N"
,
"SETTINGS"
:
{
"DEFAULT_VALUE"
:
0
,
"DISPLAY"
:
"CHECKBOX"
,
"LABEL"
:
[
""
,
""
]
,
"LABEL_CHECKBOX"
:
"UF - Yes/No"
}
,
"EDIT_FORM_LABEL"
:
"UF - Yes/No"
,
"LIST_COLUMN_LABEL"
:
"UF - Yes/No"
,
"LIST_FILTER_LABEL"
:
"UF - Yes/No"
,
"ERROR_MESSAGE"
:
null
,
"HELP_MESSAGE"
:
null
}
,
{
"ID"
:
"233"
,
"ENTITY_ID"
:
"CRM_REQUISITE"
,
"FIELD_NAME"
:
"UF_CRM_NEWTECH_V1_DATETIME"
,
"USER_TYPE_ID"
:
"datetime"
,
"XML_ID"
:
null
,
"SORT"
:
"100"
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"E"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_IN_LIST"
:
"Y"
,
"IS_SEARCHABLE"
:
"N"
,
"SETTINGS"
:
{
"DEFAULT_VALUE"
:
{
"TYPE"
:
"NONE"
,
"VALUE"
:
""
}
,
"USE_SECOND"
:
"Y"
,
"USE_TIMEZONE"
:
"N"
}
,
"EDIT_FORM_LABEL"
:
"UF - Date"
,
"LIST_COLUMN_LABEL"
:
"UF - Date"
,
"LIST_FILTER_LABEL"
:
"UF - Date"
,
"ERROR_MESSAGE"
:
null
,
"HELP_MESSAGE"
:
null
}
,
{
"ID"
:
"234"
,
"ENTITY_ID"
:
"CRM_REQUISITE"
,
"FIELD_NAME"
:
"UF_CRM_NEWTECH_V1_DOUBLE"
,
"USER_TYPE_ID"
:
"double"
,
"XML_ID"
:
null
,
"SORT"
:
"100"
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"E"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_IN_LIST"
:
"Y"
,
"IS_SEARCHABLE"
:
"N"
,
"SETTINGS"
:
{
"PRECISION"
:
2
,
"SIZE"
:
20
,
"MIN_VALUE"
:
0
,
"MAX_VALUE"
:
0
,
"DEFAULT_VALUE"
:
null
}
,
"EDIT_FORM_LABEL"
:
"PP - Number"
,
"LIST_COLUMN_LABEL"
:
"PP - Number"
,
"LIST_FILTER_LABEL"
:
"PP - Number"
,
"ERROR_MESSAGE"
:
null
,
"HELP_MESSAGE"
:
null
}
,
{
"ID"
:
"235"
,
"ENTITY_ID"
:
"CRM_REQUISITE"
,
"FIELD_NAME"
:
"UF_CRM_NEWTECH_V1_STRING"
,
"USER_TYPE_ID"
:
"string"
,
"XML_ID"
:
null
,
"SORT"
:
"100"
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"N"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_IN_LIST"
:
"Y"
,
"IS_SEARCHABLE"
:
"N"
,
"SETTINGS"
:
{
"SIZE"
:
20
,
"ROWS"
:
1
,
"REGEXP"
:
""
,
"MIN_LENGTH"
:
0
,
"MAX_LENGTH"
:
0
,
"DEFAULT_VALUE"
:
""
}
,
"EDIT_FORM_LABEL"
:
"PP - String"
,
"LIST_COLUMN_LABEL"
:
"PP - String"
,
"LIST_FILTER_LABEL"
:
"PP - String"
,
"ERROR_MESSAGE"
:
"UF_CRM_NEWTECH_V1_STRING"
,
"HELP_MESSAGE"
:
"UF_CRM_NEWTECH_V1_STRING"
}
]
,
"total"
:
4
,
"time"
:
{
"start"
:
1717754823.56747
,
"finish"
:
1717754823.938955
,
"duration"
:
0.37148499488830566
,
"processing"
:
0.007915973663330078
,
"date_start"
:
"2024-06-07T12:07:03+02:00"
,
"date_finish"
:
"2024-06-07T12:07:03+02:00"
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
Array of objects with information from the selected custom fields. Each element contains the selected
fields describing the custom field of the requisite
total
integer
Total number of records found
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
40x
,
50x
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
Insufficient access permissions to retrieve the list of custom fields of the requisite
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
Create a New Custom Field for crm.requisite.userfield.add
Update Custom Field of Requisite crm.requisite.userfield.update
Get User Field by ID crm.requisite.userfield.get
Delete User Field of Requisite crm.requisite.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Get a Custom Field by ID
Next
Delete a Custom Requisite Field

---

## Delete User Field of Requisite crm.requisite.userfield.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/user-fields/crm-requisite-userfield-delete

Delete User Field of Requisite crm.requisite.userfield.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete User Field of Requisite crm.requisite.userfield.delete
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
Who can execute the method: any user
This method deletes a user field of the requisite.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the user field. Can be obtained using the method
crm.requisite.userfield.list
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
'{"id":235}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.userfield.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":235,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.userfield.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.userfield.delete'
,
{
id
:
235
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
$response
=
$b24Service
->core
->
call
(
'crm.requisite.userfield.delete'
,
[
'id'
=>
235
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
BX24
.
callMethod
(
"crm.requisite.userfield.delete"
,
{
id
:
235
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
'crm.requisite.userfield.delete'
,
[
'id'
=>
235
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
1717771689.639506
,
"finish"
:
1717771690.189804
,
"duration"
:
0.5502979755401611
,
"processing"
:
0.10051202774047852
,
"date_start"
:
"2024-06-07T16:48:09+02:00"
,
"date_finish"
:
"2024-06-07T16:48:10+02:00"
,
"operating"
:
0.1004788875579834
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of deleting the user field:
true — deleted
false — not deleted
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
""
,
"error_description"
:
"The entity with ID '235' is not found."
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
Error Message
Description
Empty string
The entity with ID '235' is not found
The user field with the specified identifier was not found
Empty string
ID is not defined or invalid
The identifier of the user field is not specified or has an invalid value
Empty string
Access denied
Insufficient access permissions to delete the user field
ERROR_CORE
Fail to delete user field
Failed to delete the user field
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
Create a New Custom Field for crm.requisite.userfield.add
Get User Field by ID crm.requisite.userfield.get
Get a list of custom fields of the requisite by filter crm.requisite.userfield.list
Update Custom Field of Requisite crm.requisite.userfield.update
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Custom Requisite Fields by Filter
Next
Overview of Methods

---

## Links Between Requisites and CRM Objects

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/links/index

Links Between Requisites and CRM Objects | Bitrix24 REST API and Marketplace Applications
Links Between Requisites and CRM Objects
Links Between Requisites and CRM Objects
Fields of the Link Between Requisite and CRM Object
Overview of Methods
Scope:
crm
Who can perform methods: any user
Links maintain the correspondence between a CRM object and the requisites used in the context of that object.
For example, there is an invoice. To print it, the requisites of the selling company (my company) and the buying company (the client) are required. Since a company may have multiple requisites, it is unclear which ones to use for printing the invoice. This is where the link is needed to specify the required requisites.
The fields
REQUISITE_ID
and
BANK_DETAIL_ID
store the identifiers of the requisite and bank requisite, respectively, used for the buying company. The fields
MC_REQUISITE_ID
and
MC_BANK_DETAIL_ID
store similar identifiers for the selling company.
If any identifier has a value of
0
, it is considered unselected. The requisites of the selling company or the bank requisites may not be selected.
Fields of the Link Between Requisite and CRM Object
Fields of the Link Between Requisite and CRM Object
Name
type
Description
Read
Write
Required
Immutable
ENTITY_TYPE_ID
integer
Identifier of the object type to which the link pertains.
The following types can be used:
deal (value
2
)
old invoice (value
5
)
estimate (value
7
)
new invoice (value
31
)
other dynamic objects (to get possible values, see the method
crm.type.list
).
Identifiers of CRM object types can be obtained using the method
crm.enum.ownertype
Yes
Yes
Yes
Yes
ENTITY_ID
integer
Identifier of the object to which the link pertains.
Identifiers of objects can be obtained using the following methods:
crm.deal.list
,
crm.quote.list
,
crm.item.list
.
Yes
Yes
Yes
Yes
REQUISITE_ID
integer
Identifier of the client's requisite selected for the object.
Identifiers of requisites can be obtained using the method
crm.requisite.list
Yes
Yes
Yes
No
BANK_DETAIL_ID
integer
Identifier of the client's bank requisite selected for the object.
Identifiers of bank requisites can be obtained using the method
crm.requisite.bankdetail.list
Yes
Yes
Yes
No
MC_REQUISITE_ID
integer
Identifier of my company's requisite selected for the object.
Identifiers of requisites can be obtained using the method
crm.requisite.list
Yes
Yes
Yes
No
MC_BANK_DETAIL_ID
integer
Identifier of my company's bank requisite selected for the object.
Identifiers of bank requisites can be obtained using the method
crm.requisite.bankdetail.list
Yes
Yes
Yes
No
Overview of Methods
Overview of Methods
Method
Description
crm.requisite.link.register
Registers the link between requisites and an object
crm.requisite.link.get
Returns the link between requisites and an object
crm.requisite.link.list
Returns a list of links between requisites based on a filter
crm.requisite.link.unregister
Removes the link between requisites and an object
crm.requisite.link.fields
Returns a formal description of the fields of the requisites link
Copied
Was the article helpful?
Yes
No
Previous
Delete a Custom Requisite Field
Next
Register a Connection of Requisites with an Object

---

## Register Requisite Link with Object crm.requisite.link.register

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/links/crm-requisite-link-register

Register Requisite Link with Object crm.requisite.link.register | Bitrix24 REST API and Marketplace Applications
Register Requisite Link with Object crm.requisite.link.register
Register Requisite Link with Object crm.requisite.link.register
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
Who can execute the method: any user
This method registers a link between requisites and an object.
For successful registration, the requisite IDs must belong to the client and seller selected in the linked object. If a requisite is not available, its ID is passed as
0
. You can even specify all requisite IDs as zero. In this case, it is considered that the requisites are not linked to the object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
A set of fields for the requisite link — an object of the form
{"field": "value"[, ...]}
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
ENTITY_TYPE_ID
*
integer
Identifier of the object type to which the link belongs.
The following types can be used:
deal (value
2
)
old invoice (value
5
)
estimate (value
7
)
new invoice (value
31
)
other dynamic objects (for possible values, see the method
crm.type.list
).
You can obtain CRM object type identifiers using the method
crm.enum.ownertype
ENTITY_ID
*
integer
Identifier of the object to which the link belongs.
Object identifiers can be obtained using the following methods:
crm.deal.list
,
crm.quote.list
,
crm.item.list
REQUISITE_ID
*
integer
Identifier of the client's requisite selected for the object.
Requisite identifiers can be obtained using the method
crm.requisite.list
BANK_DETAIL_ID
*
integer
Identifier of the client's bank requisite selected for the object.
Bank requisite identifiers can be obtained using the method
crm.requisite.bankdetail.list
MC_REQUISITE_ID
*
integer
Identifier of my company's requisite selected for the object.
Requisite identifiers can be obtained using the method
crm.requisite.list
MC_BANK_DETAIL_ID
*
integer
Identifier of my company's bank requisite selected for the object.
Bank requisite identifiers can be obtained using the method
crm.requisite.bankdetail.list
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
'{"fields":{"ENTITY_TYPE_ID":31,"ENTITY_ID":315,"REQUISITE_ID":60,"BANK_DETAIL_ID":24,"MC_REQUISITE_ID":2,"MC_BANK_DETAIL_ID":2}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.link.register
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"ENTITY_TYPE_ID":31,"ENTITY_ID":315,"REQUISITE_ID":60,"BANK_DETAIL_ID":24,"MC_REQUISITE_ID":2,"MC_BANK_DETAIL_ID":2},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.link.register
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.link.register"
, {
fields
: {
ENTITY_TYPE_ID
:
31
,
ENTITY_ID
:
315
,
REQUISITE_ID
:
60
,
BANK_DETAIL_ID
:
24
,
MC_REQUISITE_ID
:
2
,
MC_BANK_DETAIL_ID
:
2
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
'crm.requisite.link.register'
,
[
'fields'
=> [
'ENTITY_TYPE_ID'
=>
31
,
'ENTITY_ID'
=>
315
,
'REQUISITE_ID'
=>
60
,
'BANK_DETAIL_ID'
=>
24
,
'MC_REQUISITE_ID'
=>
2
,
'MC_BANK_DETAIL_ID'
=>
2
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
'Error registering requisite link: '
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
"crm.requisite.link.register"
, {
fields
: {
ENTITY_TYPE_ID
:
31
,
ENTITY_ID
:
315
,
REQUISITE_ID
:
60
,
// Identifier of the requisite belonging to the buyer
BANK_DETAIL_ID
:
24
,
// Identifier of the bank requisite belonging to the buyer
MC_REQUISITE_ID
:
2
,
// Identifier of the requisite belonging to the selling company
MC_BANK_DETAIL_ID
:
2
// Identifier of the bank requisite belonging to the selling company
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
'crm.requisite.link.register'
,
[
'fields'
=>
[
'ENTITY_TYPE_ID'
=>
31
,
'ENTITY_ID'
=>
315
,
'REQUISITE_ID'
=>
60
,
'BANK_DETAIL_ID'
=>
24
,
'MC_REQUISITE_ID'
=>
2
,
'MC_BANK_DETAIL_ID'
=>
2
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
1718729280.575321
,
"finish"
:
1718729281.296214
,
"duration"
:
0.720893144607544
,
"processing"
:
0.1967611312866211
,
"date_start"
:
"2024-06-18T18:48:00+02:00"
,
"date_finish"
:
"2024-06-18T18:48:01+02:00"
,
"operating"
:
0.1967298984527588
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the link registration:
true
— link registered
false
— link not registered
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
""
,
"error_description"
:
"Entity is not found"
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
ENTITY_TYPE_ID is not defined or invalid
Object type identifier is not set or has an invalid value
ENTITY_ID is not defined or invalid
Object identifier is not set or has an invalid value
REQUISITE_ID is not defined or invalid
Client requisite identifier is not set or has an invalid value
BANK_DETAIL_ID is not defined or invalid
Client bank requisite identifier is not set or has an invalid value
MC_REQUISITE_ID is not defined or invalid
My company requisite identifier is not set or has an invalid value
MC_BANK_DETAIL_ID is not defined or invalid
My company bank requisite identifier is not set or has an invalid value
The Requisite with ID '60' is not found
Client requisite with the specified identifier not found
The Requisite with ID '60' is not assigned to Company with ID '5'
Client requisite with the specified identifier does not belong to the company specified in the object
The BankDetail with ID '24' is not found
Client bank requisite with the specified identifier not found
The BankDetail with ID '24' is not assigned to Requisite with ID '60'
Client bank requisite with the specified identifier does not belong to the specified requisite
The Requisite of your company with ID '2' is not found
My company requisite with the specified identifier not found
The Requisite with ID '2' is not assigned to your company with ID '3010'
My company requisite with the specified identifier does not belong to my company specified in the object
The BankDetail of your company with ID '2' is not found
My company bank requisite with the specified identifier not found
The BankDetail of your company with ID '2' is not assigned to Requisite of your company with ID '2'
My company bank requisite with the specified identifier does not belong to the specified requisite
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
Get the link of the requisite with the object crm.requisite.link.get
Get a list of links for requisites crm.requisite.link.list
Unlink Requisite from Object crm.requisite.link.unregister
Get Description of CRM Requisite Link Fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get the Connection of a Requisite with an Object

---

## Get the link of the requisite with the object crm.requisite.link.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/links/crm-requisite-link-get

Get the link of the requisite with the object crm.requisite.link.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the link of the requisite with the object crm.requisite.link.get
Method Parameters
Code Examples
Response Handling
Returned Data
Description of the requisite link fields with the CRM object
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns the link of the requisites with the object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the object type to which the link belongs.
The following types can be used:
deal (value
2
)
old invoice (value
5
)
estimate (value
7
)
new invoice (value
31
)
other dynamic objects (to get possible values, see the method
crm.type.list
).
Identifiers of CRM object types can be obtained using the method
crm.enum.ownertype
entityId
*
integer
Identifier of the object to which the link belongs.
Identifiers of objects can be obtained using the following methods:
crm.deal.list
,
crm.quote.list
,
crm.item.list
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
'{"entityTypeId":31,"entityId":315}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.link.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":31,"entityId":315,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.link.get
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.link.get"
, {
entityTypeId
:
31
,
// Identifier of the type (Invoice)
entityId
:
315
,
// Identifier of the invoice
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
'crm.requisite.link.get'
,
[
'entityTypeId'
=>
31
,
'entityId'
=>
315
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
'Error getting requisite link: '
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
"crm.requisite.link.get"
, {
entityTypeId
:
31
,
// Identifier of the type (Invoice)
entityId
:
315
,
// Identifier of the invoice
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
'crm.requisite.link.get'
,
[
'entityTypeId'
=>
31
,
'entityId'
=>
315
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
"ENTITY_TYPE_ID"
:
31
,
"ENTITY_ID"
:
315
,
"REQUISITE_ID"
:
"60"
,
"BANK_DETAIL_ID"
:
"24"
,
"MC_REQUISITE_ID"
:
"2"
,
"MC_BANK_DETAIL_ID"
:
"2"
}
,
"time"
:
{
"start"
:
1718378061.651857
,
"finish"
:
1718378062.098295
,
"duration"
:
0.4464380741119385
,
"processing"
:
0.07567882537841797
,
"date_start"
:
"2024-06-14T17:14:21+02:00"
,
"date_finish"
:
"2024-06-14T17:14:22+02:00"
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
Object
An object containing the values of the requisite link fields
time
time
Information about the execution time of the request
Description of the requisite link fields with the CRM object
Description of the requisite link fields with the CRM object
Name
type
Description
ENTITY_TYPE_ID
integer
Identifier of the object type to which the link belongs.
The following types can be used:
deal (value
2
)
old invoice (value
5
)
estimate (value
7
)
new invoice (value
31
)
other dynamic objects (to get possible values, see the method
crm.type.list
).
Identifiers of CRM object types can be obtained using the method
crm.enum.ownertype
ENTITY_ID
integer
Identifier of the object to which the link belongs.
Identifiers of objects can be obtained using the following methods:
crm.deal.list
,
crm.quote.list
,
crm.item.list
REQUISITE_ID
integer
Identifier of the client's requisite selected for the object.
Identifiers of requisites can be obtained using the method
crm.requisite.list
BANK_DETAIL_ID
integer
Identifier of the client's bank requisite selected for the object.
Identifiers of bank requisites can be obtained using the method
crm.requisite.bankdetail.list
MC_REQUISITE_ID
integer
Identifier of my company's requisite selected for the object.
Identifiers of requisites can be obtained using the method
crm.requisite.list
MC_BANK_DETAIL_ID
integer
Identifier of my company's bank requisite selected for the object.
Identifiers of bank requisites can be obtained using the method
crm.requisite.bankdetail.list
Error Handling
Error Handling
HTTP status:
40x
,
50x
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
Possible Error Codes
Possible Error Codes
Code
Description
entityTypeId is not defined or invalid
The object type identifier is not set or has an invalid value
entityId is not defined or invalid
The object identifier is not set or has an invalid value
Not found
The requisite link was not found
Access denied
Insufficient access permissions to retrieve the requisite link
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
Register Requisite Link with Object crm.requisite.link.register
Get a list of links for requisites crm.requisite.link.list
Unlink Requisite from Object crm.requisite.link.unregister
Get Description of CRM Requisite Link Fields
Copied
Was the article helpful?
Yes
No
Previous
Register a Connection of Requisites with an Object
Next
Get a List of Requisite Connections

---

## Get a list of links for requisites crm.requisite.link.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/links/crm-requisite-link-list

Get a list of links for requisites crm.requisite.link.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of links for requisites crm.requisite.link.list
Method Parameters
Description of the requisite link fields with the CRM object
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a list of links for requisites based on the filter.
Method Parameters
Method Parameters
Name
type
Description
select
array
An array of fields to select (see
requisite link fields
).
If the array is not provided or an empty array is passed, all available fields for requisite links will be selected.
filter
object
An object for filtering the selected requisite links in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
correspond to
requisite link fields
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
— IN, an array is passed as the value
!@
— NOT IN, an array is passed as the value
%
— LIKE, substring search. The
%
symbol should not be included in the filter value. The search looks for the substring in any position of the string.
=%
— LIKE, substring search. The
%
symbol should be included in the value. Examples:
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
!%
— NOT LIKE, substring search. The
%
symbol should not be included in the filter value. The search goes from both sides.
!=%
— NOT LIKE, substring search. The
%
symbol should be included in the value. Examples:
"mol%"
— searches for values not starting with "mol"
"%mol"
— searches for values not ending with "mol"
"%mol%"
— searches for values where the substring "mol" is not present in any position
!%=
— NOT LIKE (similar to
!=%
)
=
— equal, exact match (used by default)
!=
— not equal
!
— not equal
order
object
An object for sorting the selected requisite links in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
correspond to
requisite link fields
.
Possible values for
order
:
asc
— in ascending order
desc
— in descending order
start
integer
This parameter is used for managing pagination.
The page size of results is always static: 50 records.
To select the second page of results, the value
50
must be passed. To select the third page of results, the value is
100
, and so on.
The formula for calculating the
start
parameter value:
start = (N-1) * 50
, where
N
is the desired page number
Description of the requisite link fields with the CRM object
Description of the requisite link fields with the CRM object
Name
type
Description
ENTITY_TYPE_ID
integer
Identifier of the object type to which the link belongs.
The following types can be used:
deal (value
2
)
old invoice (value
5
)
estimate (value
7
)
new invoice (value
31
)
other dynamic objects (to get possible values, see the method
crm.type.list
).
Identifiers for CRM object types can be obtained using the method
crm.enum.ownertype
ENTITY_ID
integer
Identifier of the object to which the link belongs.
Identifiers of objects can be obtained using the following methods:
crm.deal.list
,
crm.quote.list
,
crm.item.list
REQUISITE_ID
integer
Identifier of the client's requisite selected for the object.
Identifiers of requisites can be obtained using the method
crm.requisite.list
BANK_DETAIL_ID
integer
Identifier of the client's bank requisite selected for the object.
Identifiers of bank requisites can be obtained using the method
crm.requisite.bankdetail.list
MC_REQUISITE_ID
integer
Identifier of my company's requisite selected for the object.
Identifiers of requisites can be obtained using the method
crm.requisite.list
MC_BANK_DETAIL_ID
integer
Identifier of my company's bank requisite selected for the object.
Identifiers of bank requisites can be obtained using the method
crm.requisite.bankdetail.list
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
'{"order":{"ENTITY_ID":"ASC"},"filter":{"@ENTITY_TYPE_ID":[1,2,7,31]}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.link.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"ENTITY_ID":"ASC"},"filter":{"@ENTITY_TYPE_ID":[1,2,7,31]},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.link.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.requisite.link.list'
,
{
order
: {
"ENTITY_ID"
:
"ASC"
},
filter
: {
"@ENTITY_TYPE_ID"
: [
1
,
2
,
7
,
31
] }
// Leads, deals, estimates, invoices.
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
);
const
items = response.
getData
() || [];
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
, entity); }
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.requisite.link.list'
, {
order
: {
"ENTITY_ID"
:
"ASC"
},
filter
: {
"@ENTITY_TYPE_ID"
: [
1
,
2
,
7
,
31
] }
// Leads, deals, estimates, invoices.
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
, entity); }
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.link.list'
, {
order
: {
"ENTITY_ID"
:
"ASC"
},
filter
: {
"@ENTITY_TYPE_ID"
: [
1
,
2
,
7
,
31
] }
// Leads, deals, estimates, invoices.
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
, entity); }
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
'crm.requisite.link.list'
,
[
'order'
=> [
'ENTITY_ID'
=>
'ASC'
],
'filter'
=> [
'@ENTITY_TYPE_ID'
=> [
1
,
2
,
7
,
31
]],
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
'Error fetching requisite links: '
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
"crm.requisite.link.list"
, {
order
: {
"ENTITY_ID"
:
"ASC"
},
filter
: {
"@ENTITY_TYPE_ID"
: [
1
,
2
,
7
,
31
]}
// Leads, deals, estimates, invoices.
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
'crm.requisite.link.list'
,
[
'order'
=> [
'ENTITY_ID'
=>
'ASC'
],
'filter'
=> [
'@ENTITY_TYPE_ID'
=> [
1
,
2
,
7
,
31
]]
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
"ENTITY_TYPE_ID"
:
"7"
,
"ENTITY_ID"
:
"1"
,
"REQUISITE_ID"
:
"0"
,
"BANK_DETAIL_ID"
:
"0"
,
"MC_REQUISITE_ID"
:
"0"
,
"MC_BANK_DETAIL_ID"
:
"0"
}
,
{
"ENTITY_TYPE_ID"
:
"7"
,
"ENTITY_ID"
:
"2"
,
"REQUISITE_ID"
:
"0"
,
"BANK_DETAIL_ID"
:
"0"
,
"MC_REQUISITE_ID"
:
"0"
,
"MC_BANK_DETAIL_ID"
:
"0"
}
,
{
"ENTITY_TYPE_ID"
:
"7"
,
"ENTITY_ID"
:
"3"
,
"REQUISITE_ID"
:
"0"
,
"BANK_DETAIL_ID"
:
"0"
,
"MC_REQUISITE_ID"
:
"0"
,
"MC_BANK_DETAIL_ID"
:
"0"
}
,
{
"ENTITY_TYPE_ID"
:
"7"
,
"ENTITY_ID"
:
"4"
,
"REQUISITE_ID"
:
"7"
,
"BANK_DETAIL_ID"
:
"0"
,
"MC_REQUISITE_ID"
:
"2"
,
"MC_BANK_DETAIL_ID"
:
"2"
}
,
{
"ENTITY_TYPE_ID"
:
"7"
,
"ENTITY_ID"
:
"5"
,
"REQUISITE_ID"
:
"0"
,
"BANK_DETAIL_ID"
:
"0"
,
"MC_REQUISITE_ID"
:
"2"
,
"MC_BANK_DETAIL_ID"
:
"2"
}
,
{
"ENTITY_TYPE_ID"
:
"7"
,
"ENTITY_ID"
:
"6"
,
"REQUISITE_ID"
:
"0"
,
"BANK_DETAIL_ID"
:
"0"
,
"MC_REQUISITE_ID"
:
"2"
,
"MC_BANK_DETAIL_ID"
:
"2"
}
,
{
"ENTITY_TYPE_ID"
:
"2"
,
"ENTITY_ID"
:
"25"
,
"REQUISITE_ID"
:
"38"
,
"BANK_DETAIL_ID"
:
"0"
,
"MC_REQUISITE_ID"
:
"0"
,
"MC_BANK_DETAIL_ID"
:
"0"
}
,
{
"ENTITY_TYPE_ID"
:
"31"
,
"ENTITY_ID"
:
"315"
,
"REQUISITE_ID"
:
"60"
,
"BANK_DETAIL_ID"
:
"24"
,
"MC_REQUISITE_ID"
:
"2"
,
"MC_BANK_DETAIL_ID"
:
"2"
}
]
,
"total"
:
8
,
"time"
:
{
"start"
:
1718709631.410351
,
"finish"
:
1718709631.771324
,
"duration"
:
0.36097288131713867
,
"processing"
:
0.015230178833007812
,
"date_start"
:
"2024-06-18T13:20:31+02:00"
,
"date_finish"
:
"2024-06-18T13:20:31+02:00"
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
An array of objects with information from the selected requisite links. Each element contains the selected
requisite link fields
total
integer
Total number of records found
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
0
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
Access denied
Insufficient access permissions to retrieve the list of requisite links
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
Register Requisite Link with Object crm.requisite.link.register
Get the link of the requisite with the object crm.requisite.link.get
Unlink Requisite from Object crm.requisite.link.unregister
Get Description of CRM Requisite Link Fields
Copied
Was the article helpful?
Yes
No
Previous
Get the Connection of a Requisite with an Object
Next
Remove the Connection of a Requisite with an Object

---

## Unlink Requisite from Object crm.requisite.link.unregister

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/links/crm-requisite-link-unregister

Unlink Requisite from Object crm.requisite.link.unregister | Bitrix24 REST API and Marketplace Applications
Method Parameters
Unlink Requisite from Object crm.requisite.link.unregister
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
Who can execute the method: any user
This method removes the link between requisites and the object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the object type to which the link belongs.
The following types can be used:
deal (value
2
)
old invoice (value
5
)
estimate (value
7
)
new invoice (value
31
)
other dynamic objects (to get possible values, see the method
crm.type.list
).
Identifiers of CRM object types can be obtained using the method
crm.enum.ownertype
entityId
*
integer
Identifier of the object to which the link belongs.
Identifiers of objects can be obtained using the following methods:
crm.deal.list
,
crm.quote.list
,
crm.item.list
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
'{"entityTypeId":31,"entityId":315}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.link.unregister
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":31,"entityId":315,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.link.unregister
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.link.unregister"
, {
entityTypeId
:
31
,
entityId
:
315
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
'crm.requisite.link.unregister'
,
[
'entityTypeId'
=>
31
,
'entityId'
=>
315
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
'Error unregistering requisite link: '
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
"crm.requisite.link.unregister"
, {
entityTypeId
:
31
,
entityId
:
315
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
'crm.requisite.link.unregister'
,
[
'entityTypeId'
=>
31
,
'entityId'
=>
315
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
1718797597.015625
,
"finish"
:
1718797598.098317
,
"duration"
:
1.0826919078826904
,
"processing"
:
0.13887691497802734
,
"date_start"
:
"2024-06-19T13:46:37+02:00"
,
"date_finish"
:
"2024-06-19T13:46:38+02:00"
,
"operating"
:
0.1388249397277832
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the link removal:
true
— link removed
false
— link not removed
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
40x
,
50x
{
"error"
:
""
,
"error_description"
:
"entityId is not defined or invalid."
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
entityTypeId is not defined or invalid
Object type identifier is not set or has an invalid value
entityId is not defined or invalid
Object identifier is not set or has an invalid value
Access denied
Insufficient access permissions to remove the requisite link
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
Register Requisite Link with Object crm.requisite.link.register
Get the link of the requisite with the object crm.requisite.link.get
Get a list of links for requisites crm.requisite.link.list
Get Description of CRM Requisite Link Fields
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Requisite Connections
Next
Get the Description of Requisite Connection Fields

---

## Get Description of CRM Requisite Link Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/links/crm-requisite-link-fields

Get Description of CRM Requisite Link Fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Description of CRM Requisite Link Fields
Code Examples
Response Handling
Returned Data
Description of Requisite Link Fields with CRM Object
Description of Attributes
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a formal description of the requisite link fields.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.link.fields
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
https://**put_your_bitrix24_address**/rest/crm.requisite.link.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.link.fields'
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
'crm.requisite.link.fields'
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
'Error calling crm.requisite.link.fields: '
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
"crm.requisite.link.fields"
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
'crm.requisite.link.fields'
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
HTTP Status:
200
{
"result"
:
{
"ENTITY_TYPE_ID"
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
"Object Type ID"
}
,
"ENTITY_ID"
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
"Object ID"
}
,
"REQUISITE_ID"
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
"Link to Requisites"
}
,
"BANK_DETAIL_ID"
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
"Link to Bank Requisites"
}
,
"MC_REQUISITE_ID"
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
"Link to My Company's Requisites"
}
,
"MC_BANK_DETAIL_ID"
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
"Link to My Company's Bank Requisites"
}
}
,
"time"
:
{
"start"
:
1718295307.777351
,
"finish"
:
1718295308.177586
,
"duration"
:
0.4002351760864258
,
"processing"
:
0.010699987411499023
,
"date_start"
:
"2024-06-13T18:15:07+02:00"
,
"date_finish"
:
"2024-06-13T18:15:08+02:00"
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
An object in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field
is the field identifier and
value
is the object with
field attributes
time
time
Information about the request execution time
Description of Requisite Link Fields with CRM Object
Description of Requisite Link Fields with CRM Object
Name
type
Description
ENTITY_TYPE_ID
integer
Identifier of the object type to which the link belongs.
The following types can be used:
deal (value
2
)
old invoice (value
5
)
estimate (value
7
)
new invoice (value
31
)
other dynamic objects (to get possible values, see the method
crm.type.list
).
Object type identifiers can be obtained using the method
crm.enum.ownertype
ENTITY_ID
integer
Identifier of the object to which the link belongs.
Object identifiers can be obtained using the following methods:
crm.deal.list
,
crm.quote.list
,
crm.item.list
REQUISITE_ID
integer
Identifier of the client's requisite selected for the object.
Requisite identifiers can be obtained using the method
crm.requisite.list
BANK_DETAIL_ID
integer
Identifier of the client's bank requisite selected for the object.
Bank requisite identifiers can be obtained using the method
crm.requisite.bankdetail.list
MC_REQUISITE_ID
integer
Identifier of my company's requisite selected for the object.
Requisite identifiers can be obtained using the method
crm.requisite.list
MC_BANK_DETAIL_ID
integer
Identifier of my company's bank requisite selected for the object.
Bank requisite identifiers can be obtained using the method
crm.requisite.bankdetail.list
Description of Attributes
Description of Attributes
Name
type
Description
type
string
Field type
isRequired
boolean
"Required" attribute. Possible values:
true — yes
false — no
isReadOnly
boolean
"Read-only" attribute. Possible values:
true — yes
false — no
isImmutable
boolean
"Immutable" attribute. Possible values:
true — yes
false — no
isMultiple
boolean
"Multiple" attribute. Possible values:
true — yes
false — no
isDynamic
boolean
"Custom" attribute. Possible values:
true — yes
false — no
title
string
Field identifier
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
Register Requisite Link with Object crm.requisite.link.register
Get the link of the requisite with the object crm.requisite.link.get
Get a list of links for requisites crm.requisite.link.list
Unlink Requisite from Object crm.requisite.link.unregister
Copied
Was the article helpful?
Yes
No
Previous
Remove the Connection of a Requisite with an Object
Next
Overview of Events

---

