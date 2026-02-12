---
description: 'CRM Auxiliary: Enumerations, multifields, duplicates'
methods:
- crm.activity.
- crm.activity.todo.
- crm.address.
- crm.address.list
- crm.duplicate.findbycomm
- crm.duplicate.volatileType.fields
- crm.duplicate.volatileType.list
- crm.duplicate.volatileType.register
- crm.duplicate.volatileType.unregister
- crm.entity.mergeBatch
- crm.enum.
- crm.enum.activitydirection
- crm.enum.activitynotifytype
- crm.enum.activitypriority
- crm.enum.activitystatus
- crm.enum.activitytype
- crm.enum.addresstype
- crm.enum.contenttype
- crm.enum.fields
- crm.enum.getorderownertypes
- crm.enum.ownertype
- crm.enum.settings.mode
- crm.item.
- crm.item.productrow.
- crm.lead.add
- crm.lead.get
- crm.multifield.fields
- crm.orderentity.
- crm.orderentity.add
- crm.settings.mode.get
pages: 22
title: 'CRM Auxiliary: Enumerations, multifields, duplicates'
---
# CRM Auxiliary: Enumerations, multifields, duplicates
> CRM Auxiliary: Enumerations, multifields, duplicates
> **22 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Finding and Processing Duplicates in CRM: Overview of Methods](#finding-and-processing-duplicates-in-crm-overview-)
- [Get leads, contacts, and companies with matching data crm.duplicate.findbycomm](#get-leads-contacts-and-companies-with-matching-dat)
- [Merge Duplicates crm.entity.mergeBatch](#merge-duplicates-crmentitymergebatch)
- [Duplicate Search Settings for Any Fields](#duplicate-search-settings-for-any-fields)
- [Get a list of fields for duplicate search crm.duplicate.volatileType.fields](#get-a-list-of-fields-for-duplicate-search-crmdupli)
- [Get a list of custom fields involved in duplicate search crm.duplicate.volatileType.list](#get-a-list-of-custom-fields-involved-in-duplicate-)
- [Add Field to Duplicate Search crm.duplicate.volatileType.register](#add-field-to-duplicate-search-crmduplicatevolatile)
- [Remove Field from Duplicate Search crm.duplicate.volatileType.unregister](#remove-field-from-duplicate-search-crmduplicatevol)
- [Overview of Helper Methods](#overview-of-helper-methods)
- [Get Description of Multiple Fields crm.multifield.fields](#get-description-of-multiple-fields-crmmultifieldfi)
- [Enumerations: Overview of Methods](#enumerations-overview-of-methods)
- [Get Fields of CRM Enumeration Elements <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-ygg57fou">crm.enum.fields</code>](#get-fields-of-crm-enumeration-elements-code-classy)
- [Get Object Types for Order Binding crm.enum.getorderownertypes](#get-object-types-for-order-binding-crmenumgetorder)
- [Get CRM Object Types crm.enum.ownertype](#get-crm-object-types-crmenumownertype)
- [Get Address Types crm.enum.addresstype](#get-address-types-crmenumaddresstype)
- [Get Description of CRM Operation Modes crm.enum.settings.mode](#get-description-of-crm-operation-modes-crmenumsett)
- [Get enumeration items "Types of activities" crm.enum.activitytype](#get-enumeration-items-types-of-activities-crmenuma)
- [Get Activity Direction Enumeration Elements crm.enum.activitydirection](#get-activity-direction-enumeration-elements-crmenu)
- [Get the enumeration items "Activity Priorities" crm.enum.activitypriority](#get-the-enumeration-items-activity-priorities-crme)
- [Get enumeration items "Activity Notification Type" crm.enum.activitynotifytype](#get-enumeration-items-activity-notification-type-c)
- [Get enumeration items "Description Type" crm.enum.contenttype](#get-enumeration-items-description-type-crmenumcont)
- [Get enumeration items "Status" crm.enum.activitystatus](#get-enumeration-items-status-crmenumactivitystatus)

---

## Finding and Processing Duplicates in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/duplicates/index

Finding and Processing Duplicates in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Finding and Processing Duplicates in CRM: Overview of Methods
Finding and Processing Duplicates in CRM: Overview of Methods
Setting Up Duplicate Search in CRM
Searching for Duplicates via REST
Merging Duplicates
Overview of Methods
Searching and Merging Duplicates
Setting Up Duplicate Search
When working with a large customer database, some CRM elements, such as leads, contacts, or companies, may repeat. The first call from a customer creates a contact with a name and phone number. An email from the same customer creates a new contact with a name and email address — this is a duplicate. Duplicate contacts can be merged.
Quick navigation:
all methods and events
User documentation:
finding and processing duplicates in Bitrix24
Setting Up Duplicate Search in CRM
Setting Up Duplicate Search in CRM
In the Bitrix24 interface, duplicate search is available for three CRM objects: leads, contacts, and companies.
When initiating a search, the employee can choose which fields will be used to identify duplicates:
Leads
— Full Name, company name, phone, email
Contacts
— Full Name, phone, email, Tax ID, State Registration Number, and bank account
Companies
— company name, phone, email, Tax ID, State Registration Number, and bank account
Using REST methods, you can extend the duplicate search settings in Bitrix24 by adding additional fields, including custom ones. Additional fields in the search settings will appear in the interface for all employees.
To obtain a list of standard and custom fields that can be used to search for duplicates, execute the method
crm.duplicate.volatileType.fields
.
To get a list of non-standard fields that are already in use for searching, execute the method
crm.duplicate.volatileType.list
.
You can add a field to the duplicate search using the method
crm.duplicate.volatileType.register
, and remove a field from the search using
crm.duplicate.volatileType.unregister
.
Searching for Duplicates via REST
Searching for Duplicates via REST
To search for duplicates through an application or webhook, use the method
crm.duplicate.findbycomm
. This method allows you to search for duplicates based solely on email address and phone number.
The method crm.duplicate.findbycomm can be used to select a CRM element. For example, you have a
CRM activity of type email
that came from the email test@bitrix.com. To save this email in CRM without creating a duplicate, you need to check if there is a lead, contact, or company in the customer database with that email. The same email may be recorded for both a contact and the associated company. By executing the crm.duplicate.findbycomm request, you will receive the IDs of both elements along with their types, allowing you to decide whether to attach your email to the contact or the company.
Tutorial on using the method
How to search in CRM by phone and email
Merging Duplicates
Merging Duplicates
To merge duplicates, use the method
crm.entity.mergeBatch
. This method allows you to merge multiple elements of the same type. You can merge two leads, but you cannot merge a lead with a contact.
Full automatic merging is available in several cases:
The elements are identical to each other
The elements are not identical, but the differences in field values do not require manual processing. For example, one element has a filled field, while the other has the same field empty — the value from the filled field will be retained.
If automatic merging of the selected elements is not possible due to data conflicts, there may be several reasons:
The elements have filled fields with different values. You can check the values of all fields using the get method; for example, to check the fields of leads, use the method
crm.lead.get
.
The user making the merge request does not have access to one or more fields.
User documentation
How to restrict visibility of custom fields in CRM
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: any user with permission to modify and delete CRM elements
Searching and Merging Duplicates
Searching and Merging Duplicates
Method
Description
crm.duplicate.findbycomm
Returns a list of duplicates
crm.entity.mergeBatch
Merges duplicates
Setting Up Duplicate Search
Setting Up Duplicate Search
Method
Description
crm.duplicate.volatileType.fields
Returns a list of fields that can be used to search for duplicates
crm.duplicate.volatileType.list
Returns a list of non-standard fields involved in duplicate search
crm.duplicate.volatileType.register
Adds a field to the duplicate search
crm.duplicate.volatileType.unregister
Removes a field from the duplicate search
Copied
Was the article helpful?
Yes
No
Previous
Update the Composition of the Call List
Next
Retrieve Objects with Matching Data

---

## Get leads, contacts, and companies with matching data crm.duplicate.findbycomm

**Source:** https://apidocs.bitrix24.com/api-reference/crm/duplicates/crm-duplicate-find-by-comm

Get leads, contacts, and companies with matching data crm.duplicate.findbycomm | Bitrix24 REST API and Marketplace Applications
Get leads, contacts, and companies with matching data crm.duplicate.findbycomm
Get leads, contacts, and companies with matching data crm.duplicate.findbycomm
Method Parameters
Method Operation Features
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: user with read access permission to CRM entities
The method
crm.duplicate.findbycomm
returns the identifiers of leads, contacts, and companies that contain phone numbers or email addresses from a specified list. The search does not consider the phone extension.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
type
*
string
Type of communication. Possible values:
EMAIL
— email address
PHONE
— phone
values
*
string[]
Array of emails or phone numbers.
Maximum number of values — 20
entity_type
string
Type of object. Possible values:
LEAD
— lead
CONTACT
— contact
COMPANY
— company
If not specified — the search is performed across all three types
Method Operation Features
Method Operation Features
If 20 or more duplicates are found for one object, the other types are not returned. For example, if
entity_type
is not specified and duplicates are expected across all three objects, but there are 20 or more duplicates in leads, contacts and companies will not be returned. If there are 20 or more duplicates in contacts, we will receive duplicates for leads and contacts, while the company will be absent from the selection.
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
'{"entity_type":"CONTACT","type":"PHONE","values":["1234567","11223355"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.duplicate.findbycomm
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"auth":"**put_access_token_here**","entity_type":"CONTACT","type":"PHONE","values":["1234567","11223355"]}'
\
https://**put_your_bitrix24_address**/rest/crm.duplicate.findbycomm
try
{
const
response =
await
$b24.
callMethod
(
'crm.duplicate.findbycomm'
,
{
entity_type
:
'CONTACT'
,
type
:
'PHONE'
,
values
: [
'1234567'
,
'11223355'
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
'crm.duplicate.findbycomm'
,
[
'entity_type'
=>
'CONTACT'
,
'type'
=>
'PHONE'
,
'values'
=> [
'1234567'
,
'11223355'
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
'Duplicate data: '
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
'Error finding duplicates by communication: '
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
"crm.duplicate.findbycomm"
,
{
entity_type
:
"CONTACT"
,
type
:
"PHONE"
,
values
: [
"1234567"
,
"11223355"
]
},
function
(
result
) {
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
'crm.duplicate.findbycomm'
,
[
'entity_type'
=>
'CONTACT'
,
'type'
=>
'PHONE'
,
'values'
=> [
'1234567'
,
'11223355'
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
{
"CONTACT"
:
[
275
,
2297
]
}
,
"time"
:
{
"start"
:
1750684060.672785
,
"finish"
:
1750684060.724903
,
"duration"
:
0.05211806297302246
,
"processing"
:
0.018191099166870117
,
"date_start"
:
"2025-06-23T16:07:40+02:00"
,
"date_finish"
:
"2025-06-23T16:07:40+02:00"
,
"operating_reset_at"
:
1750684660
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
LEAD
integer[]
Array of identifiers of found leads
CONTACT
integer[]
Array of identifiers of found contacts
COMPANY
integer[]
Array of identifiers of found companies
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
"Communication type is not defined"
,
"error_description"
:
"Parameter 'type' is required."
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
403
Access denied
User does not have permission to read CRM entities
400
Communication type is not defined
Required parameter
type
is not specified
400
Communication type '{type}' is not supported in current context
An unsupported communication type was specified
400
Communication values is not defined
Required parameter
values
is not specified
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
Merge Duplicates crm.entity.mergeBatch
How to Find Duplicates in CRM by Phone and Email
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Merge Duplicates

---

## Merge Duplicates crm.entity.mergeBatch

**Source:** https://apidocs.bitrix24.com/api-reference/crm/duplicates/crm-entity-merge-batch

Merge Duplicates crm.entity.mergeBatch | Bitrix24 REST API and Marketplace Applications
Method Parameters
Merge Duplicates crm.entity.mergeBatch
Method Parameters
Parameter params
Method Operation Features
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: administrator
The method
crm.entity.mergeBatch
merges multiple entities into one.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
params
*
object
Object containing the entities to merge
(detailed description)
Parameter params
Parameter params
Name
type
Description
entityTypeId
*
integer
Identifier of the
CRM object type
. Possible values:
1
—
lead
2
—
deal
3
—
contact
4
—
company
7
—
estimate
31
—
invoice
128
—
SPA
. The identifier of a specific SPA can be found using the methods
crm.enum.ownertype
and
crm.type.list
entityIds
*
integer[]
Array of identifiers of the entities to be merged. At least two entities are required
Method Operation Features
Method Operation Features
You can only merge entities of the same type: lead with lead, contact with contact, SPA element with ID 128 with another SPA element with ID 128.
Full automatic merging is available in several cases:
the entities are identical,
the entities are not identical, but the differences in field values do not require manual processing. For example, if one entity has a field filled and the other has the same field empty — the value from the filled field will be retained.
The main entity in the merge will be the one whose
ID
is specified first in the
entityIds
array. Information from other entities will be transferred to the main entity. All entities except the main one will be deleted after a successful merge.
Manual Merging in Case of Conflict
Manual Merging in Case of Conflict
If the method returns a status of
CONFLICT
, you can continue the merge manually in the Bitrix24 interface via the link:
Contacts:
/crm/contact/merge/?id=1,2,3
Companies:
/crm/company/merge/?id=1,2,3
Leads:
/crm/lead/merge/?id=1,2,3
Deals:
/crm/deal/merge/?id=1,2,3
The
id
parameter contains the identifiers of the entities to be merged, separated by commas.
Invoices:
/crm/type/31/merge/?id[]=1&id[]=2
Estimates:
/crm/type/7/merge/?id[]=1&id[]=2
SPAs:
/crm/type/128/merge/?id[]=1&id[]=2
The
id[]
parameter contains the identifiers of the entities to be merged, passed as a repeating parameter.
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
'{"params":{"entityTypeId":3,"entityIds":[100,101,102]}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.entity.mergeBatch
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"auth":"**put_access_token_here**","params":{"entityTypeId":3,"entityIds":[100,101,102]}}'
\
https://**put_your_bitrix24_address**/rest/crm.entity.mergeBatch
try
{
const
response =
await
$b24.
callMethod
(
'crm.entity.mergeBatch'
,
{
params
: {
entityTypeId
:
3
,
entityIds
: [
100
,
101
,
102
]
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
'crm.entity.mergeBatch'
,
[
'params'
=> [
'entityTypeId'
=>
3
,
'entityIds'
=> [
100
,
101
,
102
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
'Error merging entities: '
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
'crm.entity.mergeBatch'
,
{
params
: {
entityTypeId
:
3
,
entityIds
: [
100
,
101
,
102
]
}
},
function
(
result
) {
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
'crm.entity.mergeBatch'
,
[
'params'
=> [
'entityTypeId'
=>
3
,
'entityIds'
=> [
100
,
101
,
102
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
{
"STATUS"
:
"SUCCESS"
,
"ENTITY_IDS"
:
[
101
,
102
]
}
,
"time"
:
{
"start"
:
1750754639.300838
,
"finish"
:
1750754641.350269
,
"duration"
:
2.049431085586548
,
"processing"
:
2.0271031856536865
,
"date_start"
:
"2025-06-24T11:43:59+02:00"
,
"date_finish"
:
"2025-06-24T11:44:01+02:00"
,
"operating_reset_at"
:
1750755239
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
STATUS
string
Status of the operation. Possible values:
SUCCESS
— the merge was successful
CONFLICT
— a data conflict occurred, automatic merging is not possible
ERROR
— an
error
occurred
ENTITY_IDS
integer[]
Array of identifiers of the entities that were deleted during the merge
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
0
,
"error_description"
:
"The parameter entityIds must contain at least two elements."
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
403
Access denied
The user does not have permission to modify or delete CRM entities
400
The parameter entityTypeId is required.
The required parameter
entityTypeId
is missing
400
The parameter entityIds does not contain valid elements.
No elements were provided or found for merging
400
The parameter entityIds must contain at least two elements.
At least two elements are required for merging
400
Owner was not found
The object was not found
400
Entity type {entityTypeName} is not supported
An unsupported object type was specified
400
CRM_FEATURE_RESTRICTION_ERROR
Plan restriction
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
crm.duplicate.findbycomm
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Objects with Matching Data
Next
Overview of Methods

---

## Duplicate Search Settings for Any Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/duplicates/volatile-type/index

Duplicate Search Settings for Any Fields | Bitrix24 REST API and Marketplace Applications
Duplicate Search Settings for Any Fields
Duplicate Search Settings for Any Fields
We are still updating this page
Some data may be missing here — we will complete it shortly.
Method
Description
crm.duplicate.volatileType.fields
List of fields available for use.
crm.duplicate.volatileType.list
List of custom fields involved in duplicate search.
crm.duplicate.volatileType.register
Add a field to the duplicate search.
crm.duplicate.volatileType.unregister
Remove a field from the duplicate search.
Was the article helpful?
Yes
No
Previous
Merge Duplicates
Next
Get a List of Fields Available for Use

---

## Get a list of fields for duplicate search crm.duplicate.volatileType.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/duplicates/volatile-type/crm-duplicate-volatile-type-fields

Get a list of fields for duplicate search crm.duplicate.volatileType.fields | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of fields for duplicate search crm.duplicate.volatileType.fields
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: administrator
The method
crm.duplicate.volatileType.fields
returns a list of standard and custom fields that can be used for finding duplicates in leads, contacts, and companies.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
integer
Identifier of the object type. Possible values:
1
—
lead
3
—
contact
4
—
company
If not specified, fields for all types will be returned
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
'{"entityTypeId":1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.duplicate.volatileType.fields
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.duplicate.volatileType.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.duplicate.volatileType.fields"
,
{
entityTypeId
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
'crm.duplicate.volatileType.fields'
,
[
'entityTypeId'
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
'Error calling crm.duplicate.volatileType.fields: '
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
"crm.duplicate.volatileType.fields"
,
{
entityTypeId
:
1
},
function
(
result
) {
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
'crm.duplicate.volatileType.fields'
,
[
'entityTypeId'
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
HTTP status:
200
{
"result"
:
[
{
"entityTypeId"
:
1
,
"fieldCode"
:
"TITLE"
,
"fieldTitle"
:
"Lead Name"
}
,
{
"entityTypeId"
:
1
,
"fieldCode"
:
"ADDRESS"
,
"fieldTitle"
:
"Address"
}
,
{
"entityTypeId"
:
1
,
"fieldCode"
:
"UF_CRM_1750854801"
,
"fieldTitle"
:
"String"
}
,
// ... other fields ...
]
,
"time"
:
{
"start"
:
1750854837.219779
,
"finish"
:
1750854837.296077
,
"duration"
:
0.07629799842834473
,
"processing"
:
0.028430938720703125
,
"date_start"
:
"2025-06-25T12:33:57+00:00"
,
"date_finish"
:
"2025-06-25T12:33:57+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
entityTypeId
integer
Object type
fieldCode
string
Field code
fieldTitle
string
Field name
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
crm.duplicate.volatileType.list
crm.duplicate.volatileType.register
crm.duplicate.volatileType.unregister
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get a List of Custom Fields Involved in Duplicate Search

---

## Get a list of custom fields involved in duplicate search crm.duplicate.volatileType.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/duplicates/volatile-type/crm-duplicate-volatile-type-list

Get a list of custom fields involved in duplicate search crm.duplicate.volatileType.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of custom fields involved in duplicate search crm.duplicate.volatileType.list
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: administrator
The method
crm.duplicate.volatileType.list
returns a list of custom fields that are already being used for duplicate searches in leads, contacts, and companies.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.duplicate.volatileType.list
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
https://**put_your_bitrix24_address**/rest/crm.duplicate.volatileType.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.duplicate.volatileType.list'
,
{}
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.duplicate.volatileType.list'
, {})
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.duplicate.volatileType.list'
, {},
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
'crm.duplicate.volatileType.list'
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
'Error fetching volatile types: '
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
"crm.duplicate.volatileType.list"
,
{},
function
(
result
) {
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
'crm.duplicate.volatileType.list'
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
[
{
"id"
:
3355
,
"entityTypeId"
:
1
,
"fieldCode"
:
"TITLE"
}
]
,
"time"
:
{
"start"
:
1750934651.513455
,
"finish"
:
1750934651.578262
,
"duration"
:
0.06480717658996582
,
"processing"
:
0.017321109771728516
,
"date_start"
:
"2025-06-26T13:44:11+02:00"
,
"date_finish"
:
"2025-06-26T13:44:11+02:00"
,
"operating_reset_at"
:
1750935251
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
id
integer
Record identifier
entityTypeId
integer
Object type
fieldCode
string
Field code
time
time
Information about the execution time of the request
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
crm.duplicate.volatileType.fields
crm.duplicate.volatileType.register
crm.duplicate.volatileType.unregister
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Fields Available for Use
Next
Add a Field to Duplicate Search

---

## Add Field to Duplicate Search crm.duplicate.volatileType.register

**Source:** https://apidocs.bitrix24.com/api-reference/crm/duplicates/volatile-type/crm-duplicate-volatile-type-register

Add Field to Duplicate Search crm.duplicate.volatileType.register | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Field to Duplicate Search crm.duplicate.volatileType.register
Method Parameters
Method Operation Features
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: administrator
The method
crm.duplicate.volatileType.register
adds a field to the duplicate search functionality in leads, contacts, or companies.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier for the object type. Possible values:
1
—
lead
3
—
contact
4
—
company
fieldCode
*
string
The code of the field to be added to the duplicate search. For example,
TITLE
,
RQ.DE.NAME
,
UF_CRM_1750854801
. You can get a list of available fields using the method
crm.duplicate.volatileType.fields
Method Operation Features
Method Operation Features
A total of 7 custom fields can be registered for duplicate searches. For example, if you have already added 3 fields for contacts and 4 fields for companies, attempting to add another field for any object type will result in the error
MAX_TYPES_COUNT_EXCEEDED
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
'{"entityTypeId":1,"fieldCode":"TITLE"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.duplicate.volatileType.register
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1,"fieldCode":"TITLE","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.duplicate.volatileType.register
try
{
const
response =
await
$b24.
callMethod
(
"crm.duplicate.volatileType.register"
,
{
entityTypeId
:
1
,
fieldCode
:
"TITLE"
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
'crm.duplicate.volatileType.register'
,
[
'entityTypeId'
=>
1
,
'fieldCode'
=>
'TITLE'
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
'Error registering volatile type: '
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
"crm.duplicate.volatileType.register"
,
{
entityTypeId
:
1
,
fieldCode
:
"TITLE"
},
function
(
result
) {
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
'crm.duplicate.volatileType.register'
,
[
'entityTypeId'
=>
1
,
'fieldCode'
=>
'TITLE'
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
{
"id"
:
3355
}
,
"time"
:
{
"start"
:
1750934251.736599
,
"finish"
:
1750934252.028757
,
"duration"
:
0.2921581268310547
,
"processing"
:
0.24904417991638184
,
"date_start"
:
"2025-06-26T13:37:31+02:00"
,
"date_finish"
:
"2025-06-26T13:37:32+02:00"
,
"operating_reset_at"
:
1750934851
,
"operating"
:
0.24902796745300293
}
}
Returned Data
Returned Data
Name
type
Description
id
integer
Identifier for the record of the field added to the duplicate search
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
"Field not found"
,
"error_description"
:
"The specified field was not found."
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
400
Field not found
The specified field was not found
400
MAX_TYPES_COUNT_EXCEEDED
The maximum number of custom field types in the duplicate search has been exceeded
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
crm.duplicate.volatileType.fields
crm.duplicate.volatileType.list
crm.duplicate.volatileType.unregister
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Custom Fields Involved in Duplicate Search
Next
Remove a Field from Duplicate Search

---

## Remove Field from Duplicate Search crm.duplicate.volatileType.unregister

**Source:** https://apidocs.bitrix24.com/api-reference/crm/duplicates/volatile-type/crm-duplicate-volatile-type-unregister

Remove Field from Duplicate Search crm.duplicate.volatileType.unregister | Bitrix24 REST API and Marketplace Applications
Method Parameters
Remove Field from Duplicate Search crm.duplicate.volatileType.unregister
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
Who can execute the method: administrator
The method
crm.duplicate.volatileType.unregister
removes a custom field from the duplicate search.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the field record to be removed. You can obtain the identifiers of records added to the duplicate search using the method
crm.duplicate.volatileType.list
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
'{"id":101}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.duplicate.volatileType.unregister
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":101,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.duplicate.volatileType.unregister
try
{
const
response =
await
$b24.
callMethod
(
"crm.duplicate.volatileType.unregister"
,
{
id
:
101
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
'crm.duplicate.volatileType.unregister'
,
[
'id'
=>
101
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
'Error unregistering volatile type: '
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
"crm.duplicate.volatileType.unregister"
,
{
id
:
101
},
function
(
result
) {
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
'crm.duplicate.volatileType.unregister'
,
[
'id'
=>
101
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
1750935024.602893
,
"finish"
:
1750935024.719883
,
"duration"
:
0.1169898509979248
,
"processing"
:
0.05846285820007324
,
"date_start"
:
"2025-06-26T13:50:24+02:00"
,
"date_finish"
:
"2025-06-26T13:50:24+02:00"
,
"operating_reset_at"
:
1750935624
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
"TYPE_IS_NOT_ASSIGNED"
,
"error_description"
:
"This type is not assigned."
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
400
TYPE_IS_NOT_ASSIGNED
Identifier of the added field record not found
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
crm.duplicate.volatileType.fields
crm.duplicate.volatileType.list
crm.duplicate.volatileType.register
Copied
Was the article helpful?
Yes
No
Previous
Add a Field to Duplicate Search
Next
Overview of methods

---

## Overview of Helper Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/index

Overview of Helper Methods | Bitrix24 REST API and Marketplace Applications
Multiple Fields
Overview of Helper Methods
Multiple Fields
Enumerations
VAT Rates
Overview of Methods
Multiple Fields
Enumerations
The helper method groups include multiple fields, enumerations, and VAT rates.
Quick navigation:
all methods and events
Multiple Fields
Multiple Fields
The method
crm.multifield.fields
returns information about the structure of multiple fields, such as phone numbers or e-mails. To populate a field with a value of
type
, pass the data in the structure returned by the method.
Example of passing data to fill in a mobile phone number:
PHONE
: [
{
VALUE
:
"555888"
,
VALUE_TYPE
:
"MOBILE"
,
},
] ,
Typical use-cases and scenarios
How to change phone numbers and e-mails using a contact example
Create a new lead crm.lead.add
Enumerations
Enumerations
The group of enumeration methods
crm.enum.*
returns information about the names and identifiers of CRM objects. For example, the method
crm.enum.ownertype
returns identifiers for smart processes, while the method
crm.enum.addresstype
returns identifiers for address types: legal, physical, delivery address.
Typical use-cases and scenarios
How to add a comment to the smart process timeline
How to get a client's address from CRM
VAT Rates
VAT Rates
The group of methods
catalog.vat.*
manages VAT rates. These methods allow you to
create
,
delete
,
update
, and
retrieve
VAT rate values.
To set the VAT for a product in a deal or another CRM object, use the
taxRate
parameter from the group of methods
crm.item.productrow.*
.
To set the VAT for a product or service in the product catalog, use the
vatId
parameter from the group of methods
catalog.product.*
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can perform methods: depending on the method
Multiple Fields
Multiple Fields
Method
Description
crm.multifield.fields
Returns the description of multiple fields
Enumerations
Enumerations
Method
Description
crm.enum.fields
Returns the description of enumeration fields
crm.enum.ownertype
Returns the types of objects in CRM
crm.enum.getorderownertypes
Returns the identifiers of object types to which order binding is available
crm.enum.addresstype
Returns the types of addresses
crm.enum.settings.mode
Returns the description of CRM operation modes
crm.enum.activitytype
Returns the enumeration items "Activity Types"
crm.enum.activitypriority
Returns the enumeration items "Activity Priorities"
crm.enum.activitydirection
Returns the enumeration items "Activity Direction" for e-mails and calls
crm.enum.activitynotifytype
Returns the enumeration items "Activity Start Notification Type" for meetings and calls
crm.enum.activitystatus
Returns the enumeration items "Status"
crm.enum.contenttype
Returns the enumeration items "Description Type"
Copied
Was the article helpful?
Yes
No
Previous
Delete Trigger
Next
Get Description of Multiple Fields

---

## Get Description of Multiple Fields crm.multifield.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/multifield/crm-multifield-fields

Get Description of Multiple Fields crm.multifield.fields | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Description of Multiple Fields crm.multifield.fields
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
crm.multifield.fields
returns the description of multiple fields used to store phone numbers, email addresses, and other contact information in leads, contacts, and companies.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.multifield.fields
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
https://**put_your_bitrix24_address**/rest/crm.multifield.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.multifield.fields'
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
'crm.multifield.fields'
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
'Error fetching multifield fields: '
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
"crm.multifield.fields"
,
{},
function
(
result
) {
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
'crm.multifield.fields'
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
"int"
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
"TYPE_ID"
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
"Field Type"
}
,
"VALUE"
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
"Value"
}
,
"VALUE_TYPE"
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
"Value Type"
}
}
,
"time"
:
{
"start"
:
1750684622.069806
,
"finish"
:
1750684622.120529
,
"duration"
:
0.05072283744812012
,
"processing"
:
0.00037217140197753906
,
"date_start"
:
"2025-06-23T16:17:02+02:00"
,
"date_finish"
:
"2025-06-23T16:17:02+02:00"
,
"operating_reset_at"
:
1750685222
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
Object with field descriptions
(detailed description)
time
time
Information about the request execution time
Fields of the result object
Fields of the result object
Name
type
Description
ID
integer
Identifier
TYPE_ID
string
Field Type
VALUE
string
Value
VALUE_TYPE
string
Value Type
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
Overview of Helper Methods
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Overview of methods

---

## Enumerations: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/index

Enumerations: Overview of Methods | Bitrix24 REST API and Marketplace Applications
How to Work with Enumeration Methods
Enumerations: Overview of Methods
How to Work with Enumeration Methods
Relationship of Enumeration Methods with CRM Objects
Overview of Methods
Enumeration methods return information about the values of types: address type, activity type, object type, and others.
Quick navigation:
all methods
How to Work with Enumeration Methods
How to Work with Enumeration Methods
Determine what data you need and select the enumeration method. For example, if you need to retrieve all legal addresses of a contact:
use the method
crm.enum.addresstype
to find out the identifier for the legal address type
use the obtained identifier in the
TYPE_ID
filter parameter in the method
crm.address.list
Relationship of Enumeration Methods with CRM Objects
Relationship of Enumeration Methods with CRM Objects
CRM Object.
The method
crm.enum.ownertype
returns identifiers for object types. Use the
ID
of the object type in the
entityTypeId
parameter value of the methods
crm.item.*
,
crm.activity.*
.
Typical use-cases and scenarios
How to attach a task to an SPA
Order.
The method
crm.enum.getorderownertypes
returns object types to which an order can be linked. Use the
id
of the object type in the
ownerTypeId
parameter value of the methods
crm.orderentity.*
.
Description Type.
The method
crm.enum.contenttype
returns types of descriptions. Use the
ID
of the description type in the
DESCRIPTION_TYPE
parameter value of the methods
crm.activity.*
.
Activity.
The method
crm.enum.activitytype
returns types of activities. Use the
ID
of the activity type in the
TYPE_ID
parameter value of the methods
crm.activity.*
.
Status.
The method
crm.enum.activitystatus
returns types of activity statuses. Use the
ID
of the activity status in the
STATUS
parameter value of the methods
crm.activity.*
.
Priority.
The method
crm.enum.activitypriority
returns types of activity priorities. Use the
ID
of the priority in the
PRIORITY
parameter value of the methods
crm.activity.*
.
Direction.
The method
crm.enum.activitydirection
returns types of activity directions. Use the
ID
of the direction in the
DIRECTION
parameter value of the methods
crm.activity.*
.
Typical use-cases and scenarios
How to send an e-mail to a client
Notification.
The method
crm.enum.activitynotifytype
returns types of notifications for activities. Use the
ID
of the notification type in the
NOTIFY_TYPE
parameter value of the methods
crm.activity.*
.
Address.
The method
crm.enum.addresstype
returns types of addresses. Use the
ID
of the address type in the
TYPE_ID
parameter value of the methods
crm.address.*
.
Typical use-cases and scenarios
How to get a client's address from CRM
CRM Operating Mode.
The method
crm.enum.settings.mode
returns the type of CRM. Use this method to decode the
ID
type value returned by the method
crm.settings.mode.get
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can perform methods: depending on the method
Method
Description
crm.enum.fields
Returns descriptions of enumeration fields
crm.enum.ownertype
Returns object types in CRM
crm.enum.getorderownertypes
Returns identifiers of object types to which order binding is available
crm.enum.addresstype
Returns types of addresses
crm.enum.settings.mode
Returns descriptions of CRM operating modes
crm.enum.activitytype
Returns enumeration items "Activity Types"
crm.enum.activitypriority
Returns enumeration items "Activity Priorities"
crm.enum.contenttype
Returns enumeration items "Description Type"
crm.enum.activitydirection
Returns enumeration items "Activity Direction" for emails and calls
crm.enum.activitynotifytype
Returns enumeration items "Notification Type for Activity Start" for meetings and calls
crm.enum.activitystatus
Returns enumeration items "Status"
Copied
Was the article helpful?
Yes
No
Previous
Get Description of Multiple Fields
Next
Get description of enumeration fields

---

## Get Fields of CRM Enumeration Elements <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-ygg57fou">crm.enum.fields</code>

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/crm-enum-fields

Get Fields of CRM Enumeration Elements <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-ygg57fou">crm.enum.fields</code> | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Fields of CRM Enumeration Elements
crm.enum.fields
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
crm.enum.fields
returns information about the fields of enumeration elements.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.fields
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
https://**put_your_bitrix24_address**/rest/crm.enum.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.enum.fields"
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
'crm.enum.fields'
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
'Error calling crm.enum.fields: '
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
"crm.enum.fields"
,
{},
function
(
result
) {
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
'crm.enum.fields'
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
"int"
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
"Name"
}
,
"SYMBOL_CODE"
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
"Symbol Code"
}
,
"SYMBOL_CODE_SHORT"
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
"Short Symbol Code"
}
}
,
"time"
:
{
"start"
:
1750152521.485259
,
"finish"
:
1750152521.526358
,
"duration"
:
0.041098833084106445
,
"processing"
:
0.00034499168395996094
,
"date_start"
:
"2025-06-17T12:28:41+02:00"
,
"date_finish"
:
"2025-06-17T12:28:41+02:00"
,
"operating_reset_at"
:
1750153121
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
Object with field descriptions
(detailed description)
time
time
Information about the request execution time
Fields of the result Object
Fields of the result Object
Name
type
Description
ID
object
Identifier
NAME
object
Name
SYMBOL_CODE
object
Symbol Code
SYMBOL_CODE_SHORT
object
Short Symbol Code
Description of Field Characteristics
Description of Field Characteristics
Name
type
Description
type
string
Data type of the field
isRequired
boolean
Required
isReadOnly
boolean
Read-only
isImmutable
boolean
Immutable
isMultiple
boolean
Multiple
isDynamic
boolean
Dynamic
title
string
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
Continue Learning
Continue Learning
Enumerations: Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Get IDs of objects to which an order can be linked

---

## Get Object Types for Order Binding crm.enum.getorderownertypes

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/crm-enum-get-order-owner-types

Get Object Types for Order Binding crm.enum.getorderownertypes | Bitrix24 REST API and Marketplace Applications
Get Object Types for Order Binding crm.enum.getorderownertypes
Get Object Types for Order Binding crm.enum.getorderownertypes
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
crm.enum.getorderownertypes
returns a list of object types to which an order can be bound. Use the
id
of the object type as the value for the
ownerTypeId
parameter in the methods
crm.orderentity.*
.
Currently, an
order binding
can only be done to a
deal
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.getorderownertypes
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
https://**put_your_bitrix24_address**/rest/crm.enum.getorderownertypes
try
{
const
response =
await
$b24.
callMethod
(
"crm.enum.getorderownertypes"
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
'crm.enum.getorderownertypes'
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
'Error fetching order owner types: '
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
"crm.enum.getorderownertypes"
,
{},
function
(
result
) {
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
'crm.enum.getorderownertypes'
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
[
{
"attribute"
:
"DYN"
,
"code"
:
"DEAL"
,
"id"
:
2
,
"name"
:
"Deal"
}
]
,
"time"
:
{
"start"
:
1750152924.723585
,
"finish"
:
1750152924.781251
,
"duration"
:
0.05766606330871582
,
"processing"
:
0.020370960235595703
,
"date_start"
:
"2025-06-17T12:35:24+02:00"
,
"date_finish"
:
"2025-06-17T12:35:24+02:00"
,
"operating_reset_at"
:
1750153524
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
Array of object types
(detailed description)
time
time
Information about the request execution time
Fields of the result Array
Fields of the result Array
Name
type
Description
attribute
string
Object type attribute
code
string
Object type code
id
integer
Object type identifier
name
string
Object type name
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
Enumerations: Overview of Methods
Add Order Binding to CRM Object crm.orderentity.add
Copied
Was the article helpful?
Yes
No
Previous
Get description of enumeration fields
Next
Get CRM object types

---

## Get CRM Object Types crm.enum.ownertype

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/crm-enum-owner-type

Get CRM Object Types crm.enum.ownertype | Bitrix24 REST API and Marketplace Applications
Get CRM Object Types crm.enum.ownertype
Get CRM Object Types crm.enum.ownertype
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
crm.enum.ownertype
returns the identifiers of CRM object types and SPA. Use the
ID
of the object type as the value for the
entityTypeId
parameter in the methods
crm.item.*
,
crm.activity.*
.
The identifiers of SPA in each Bitrix24 are unique and may differ from those provided in the example.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.ownertype
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
https://**put_your_bitrix24_address**/rest/crm.enum.ownertype
try
{
const
response =
await
$b24.
callMethod
(
'crm.enum.ownertype'
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
'crm.enum.ownertype'
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
'Error calling crm.enum.ownertype: '
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
"crm.enum.ownertype"
,
{},
function
(
result
) {
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
'crm.enum.ownertype'
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
[
{
"ID"
:
1
,
"NAME"
:
"Lead"
,
"SYMBOL_CODE"
:
"LEAD"
,
"SYMBOL_CODE_SHORT"
:
"L"
}
,
{
"ID"
:
2
,
"NAME"
:
"Deal"
,
"SYMBOL_CODE"
:
"DEAL"
,
"SYMBOL_CODE_SHORT"
:
"D"
}
,
{
"ID"
:
3
,
"NAME"
:
"Contact"
,
"SYMBOL_CODE"
:
"CONTACT"
,
"SYMBOL_CODE_SHORT"
:
"C"
}
,
{
"ID"
:
4
,
"NAME"
:
"Company"
,
"SYMBOL_CODE"
:
"COMPANY"
,
"SYMBOL_CODE_SHORT"
:
"CO"
}
,
{
"ID"
:
5
,
"NAME"
:
"Invoice (old version)"
,
"SYMBOL_CODE"
:
"INVOICE"
,
"SYMBOL_CODE_SHORT"
:
"I"
}
,
{
"ID"
:
31
,
"NAME"
:
"Invoice"
,
"SYMBOL_CODE"
:
"SMART_INVOICE"
,
"SYMBOL_CODE_SHORT"
:
"SI"
}
,
{
"ID"
:
7
,
"NAME"
:
"Estimate"
,
"SYMBOL_CODE"
:
"QUOTE"
,
"SYMBOL_CODE_SHORT"
:
"Q"
}
,
{
"ID"
:
8
,
"NAME"
:
"Requisites"
,
"SYMBOL_CODE"
:
"REQUISITE"
,
"SYMBOL_CODE_SHORT"
:
"RQ"
}
,
{
"ID"
:
36
,
"NAME"
:
"Document"
,
"SYMBOL_CODE"
:
"SMART_DOCUMENT"
,
"SYMBOL_CODE_SHORT"
:
"DO"
}
,
{
"ID"
:
39
,
"NAME"
:
"Company Document"
,
"SYMBOL_CODE"
:
"SMART_B2E_DOC"
,
"SYMBOL_CODE_SHORT"
:
"SBD"
}
,
{
"ID"
:
177
,
"NAME"
:
"Equipment Purchase"
,
"SYMBOL_CODE"
:
"DYNAMIC_177"
,
"SYMBOL_CODE_SHORT"
:
"Tb1"
}
,
{
"ID"
:
156
,
"NAME"
:
"Purchase"
,
"SYMBOL_CODE"
:
"DYNAMIC_156"
,
"SYMBOL_CODE_SHORT"
:
"T9c"
}
]
,
"time"
:
{
"start"
:
1750153184.228934
,
"finish"
:
1750153184.262921
,
"duration"
:
0.03398704528808594
,
"processing"
:
0.0008471012115478516
,
"date_start"
:
"2025-06-17T12:39:44+02:00"
,
"date_finish"
:
"2025-06-17T12:39:44+02:00"
,
"operating_reset_at"
:
1750153784
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
Array with owner types
(detailed description)
time
time
Information about the request execution time
Fields of the result array
Fields of the result array
Name
type
Description
ID
integer
Identifier of the owner type
NAME
string
Name of the owner type
SYMBOL_CODE
string
Symbolic code
SYMBOL_CODE_SHORT
string
Short symbolic code
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
Enumerations: Overview of Methods
How to Attach a Task to a SPA
Copied
Was the article helpful?
Yes
No
Previous
Get IDs of objects to which an order can be linked
Next
Get address types

---

## Get Address Types crm.enum.addresstype

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/crm-enum-address-type

Get Address Types crm.enum.addresstype | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Address Types crm.enum.addresstype
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
crm.enum.addresstype
returns a list of address types. Use the
ID
of the address type as the value for the
TYPE_ID
parameter in the methods
crm.address.*
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.addresstype
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
https://**put_your_bitrix24_address**/rest/crm.enum.addresstype
try
{
const
response =
await
$b24.
callMethod
(
"crm.enum.addresstype"
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
'crm.enum.addresstype'
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
'Error calling crm.enum.addresstype: '
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
"crm.enum.addresstype"
,
{},
function
(
result
) {
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
'crm.enum.addresstype'
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
[
{
"ID"
:
11
,
"NAME"
:
"Delivery Address"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
1
,
"NAME"
:
"Actual Address"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
6
,
"NAME"
:
"Legal Address"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
4
,
"NAME"
:
"Registration Address"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
8
,
"NAME"
:
"Correspondence Address"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
9
,
"NAME"
:
"Beneficiary Address"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
]
,
"time"
:
{
"start"
:
1750152255.931318
,
"finish"
:
1750152255.967967
,
"duration"
:
0.03664898872375488
,
"processing"
:
0.0003609657287597656
,
"date_start"
:
"2025-06-17T12:24:15+02:00"
,
"date_finish"
:
"2025-06-17T12:24:15+02:00"
,
"operating_reset_at"
:
1750152855
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
Array of address types
(detailed description)
time
time
Information about the request execution time
Fields of the result array
Fields of the result array
Name
type
Description
ID
integer
Identifier of the address type
NAME
string
Name of the address type
SYMBOL_CODE
string
Symbolic code
SYMBOL_CODE_SHORT
string
Short symbolic code
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
Enumerations: Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
Get CRM object types
Next
Get descriptions of CRM operation modes

---

## Get Description of CRM Operation Modes crm.enum.settings.mode

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/crm-enum-settings-mode

Get Description of CRM Operation Modes crm.enum.settings.mode | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Description of CRM Operation Modes crm.enum.settings.mode
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
crm.enum.settings.mode
returns a list of CRM operation modes. Use this method to decode the
ID
value of the type returned by the method
crm.settings.mode.get
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.settings.mode
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
https://**put_your_bitrix24_address**/rest/crm.enum.settings.mode
try
{
const
response =
await
$b24.
callMethod
(
"crm.enum.settings.mode"
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
'crm.enum.settings.mode'
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
'Error calling crm.enum.settings.mode: '
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
"crm.enum.settings.mode"
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
});
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
'crm.enum.settings.mode'
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
[
{
"ID"
:
1
,
"NAME"
:
"Classic CRM"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
2
,
"NAME"
:
"Simple CRM"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
]
,
"time"
:
{
"start"
:
1750153429.516902
,
"finish"
:
1750153429.650327
,
"duration"
:
0.13342499732971191
,
"processing"
:
0.0002980232238769531
,
"date_start"
:
"2025-06-17T12:43:49+03:00"
,
"date_finish"
:
"2025-06-17T12:43:49+03:00"
,
"operating_reset_at"
:
1750154029
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
Array of CRM operation modes
(detailed description)
time
time
Information about the request execution time
Fields of the result Array
Fields of the result Array
Name
type
Description
ID
integer
Identifier of the operation mode
NAME
string
Name of the operation mode
SYMBOL_CODE
string
Symbolic code
SYMBOL_CODE_SHORT
string
Short symbolic code
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
Enumerations: Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
Get address types
Next
Types of Activities

---

## Get enumeration items "Types of activities" crm.enum.activitytype

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/outdated/crm-enum-activity-type

Get enumeration items "Types of activities" crm.enum.activitytype | Bitrix24 REST API and Marketplace Applications
Get enumeration items "Types of activities" crm.enum.activitytype
Get enumeration items "Types of activities" crm.enum.activitytype
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
Method development has been discontinued
The method
crm.enum.activitytype
continues to function, but it is related to deprecated methods
crm.activity.*
. A more current alternative is the methods
crm.activity.todo.*
.
The method
crm.enum.activitytype
returns a list of types for the
TYPE_ID
field of
activities
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.activitytype
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
https://**put_your_bitrix24_address**/rest/crm.enum.activitytype
try
{
const
response =
await
$b24.
callMethod
(
"crm.enum.activitytype"
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
'crm.enum.activitytype'
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
'Error calling crm.enum.activitytype: '
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
"crm.enum.activitytype"
,
{},
function
(
result
) {
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
'crm.enum.activitytype'
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
[
{
"ID"
:
0
,
"NAME"
:
""
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
1
,
"NAME"
:
"Meeting"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
2
,
"NAME"
:
"Call"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
3
,
"NAME"
:
"Task"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
4
,
"NAME"
:
"E-mail"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
5
,
"NAME"
:
"Action"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
6
,
"NAME"
:
"Custom Action"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
]
,
"time"
:
{
"start"
:
1750152062.819392
,
"finish"
:
1750152062.85849
,
"duration"
:
0.03909802436828613
,
"processing"
:
0.0004849433898925781
,
"date_start"
:
"2025-06-17T12:21:02+02:00"
,
"date_finish"
:
"2025-06-17T12:21:02+02:00"
,
"operating_reset_at"
:
1750152662
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
Array with activity types
(detailed description)
time
time
Information about the request execution time
Fields of the result array
Fields of the result array
Name
type
Description
ID
integer
Identifier of the activity type
NAME
string
Name of the activity type
SYMBOL_CODE
string
Symbolic code
SYMBOL_CODE_SHORT
string
Short symbolic code
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
Enumerations: Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
Get descriptions of CRM operation modes
Next
Activity Direction

---

## Get Activity Direction Enumeration Elements crm.enum.activitydirection

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/outdated/crm-enum-activity-direction

Get Activity Direction Enumeration Elements crm.enum.activitydirection | Bitrix24 REST API and Marketplace Applications
Get Activity Direction Enumeration Elements crm.enum.activitydirection
Get Activity Direction Enumeration Elements crm.enum.activitydirection
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
Method development has been discontinued
The method
crm.enum.activitydirection
continues to function, but it is considered deprecated in favor of the more current methods
crm.activity.*
. A more relevant alternative is the methods
crm.activity.todo.*
.
The method
crm.enum.activitydirection
returns activity directions for the
DIRECTION
field of
deals, e-mails, and calls
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.activitydirection
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
https://**put_your_bitrix24_address**/rest/crm.enum.activitydirection
try
{
const
response =
await
$b24.
callMethod
(
"crm.enum.activitydirection"
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
'crm.enum.activitydirection'
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
'Error calling crm.enum.activitydirection: '
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
"crm.enum.activitydirection"
,
{},
function
(
result
) {
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
'crm.enum.activitydirection'
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
[
{
"ID"
:
0
,
"NAME"
:
""
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
1
,
"NAME"
:
"Incoming"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
2
,
"NAME"
:
"Outgoing"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
]
,
"time"
:
{
"start"
:
1750149628.891727
,
"finish"
:
1750149628.919669
,
"duration"
:
0.02794194221496582
,
"processing"
:
0.00030112266540527344
,
"date_start"
:
"2025-06-17T11:40:28+02:00"
,
"date_finish"
:
"2025-06-17T11:40:28+02:00"
,
"operating_reset_at"
:
1750150228
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
Array of activity directions
(detailed description)
time
time
Information about the request execution time
Fields of the result Array
Fields of the result Array
Name
type
Description
ID
integer
Identifier of the activity direction
NAME
string
Name of the activity direction
SYMBOL_CODE
string
Symbolic code
SYMBOL_CODE_SHORT
string
Short symbolic code
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
Enumerations: Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
Types of Activities
Next
Activity Priorities

---

## Get the enumeration items "Activity Priorities" crm.enum.activitypriority

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/outdated/crm-enum-activity-priority

Get the enumeration items "Activity Priorities" crm.enum.activitypriority | Bitrix24 REST API and Marketplace Applications
Get the enumeration items "Activity Priorities" crm.enum.activitypriority
Get the enumeration items "Activity Priorities" crm.enum.activitypriority
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
Method development has been discontinued
The method
crm.enum.activitypriority
continues to function, but it is considered deprecated in favor of the more current methods
crm.activity.todo.*
.
The method
crm.enum.activitypriority
returns a list of priorities for the
PRIORITY
field of
activities
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.activitypriority
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
https://**put_your_bitrix24_address**/rest/crm.enum.activitypriority
try
{
const
response =
await
$b24.
callMethod
(
"crm.enum.activitypriority"
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
'crm.enum.activitypriority'
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
'Error calling crm.enum.activitypriority: '
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
"crm.enum.activitypriority"
,
{},
function
(
result
) {
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
'crm.enum.activitypriority'
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
[
{
"ID"
:
0
,
"NAME"
:
""
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
1
,
"NAME"
:
"low"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
2
,
"NAME"
:
"medium"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
3
,
"NAME"
:
"high"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
]
,
"time"
:
{
"start"
:
1750151772.540903
,
"finish"
:
1750151772.60146
,
"duration"
:
0.060556888580322266
,
"processing"
:
0.00045800209045410156
,
"date_start"
:
"2025-06-17T12:16:12+02:00"
,
"date_finish"
:
"2025-06-17T12:16:12+02:00"
,
"operating_reset_at"
:
1750152372
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
Array of priorities
(detailed description)
time
time
Information about the request execution time
Fields of the result array
Fields of the result array
Name
type
Description
ID
integer
Priority identifier
NAME
string
Priority name
SYMBOL_CODE
string
Symbolic code
SYMBOL_CODE_SHORT
string
Short symbolic code
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
Enumerations: Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
Activity Direction
Next
Notification Type for Activity Start

---

## Get enumeration items "Activity Notification Type" crm.enum.activitynotifytype

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/outdated/crm-enum-activity-notify-type

Get enumeration items "Activity Notification Type" crm.enum.activitynotifytype | Bitrix24 REST API and Marketplace Applications
Get enumeration items "Activity Notification Type" crm.enum.activitynotifytype
Get enumeration items "Activity Notification Type" crm.enum.activitynotifytype
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
Method development has been discontinued
The method
crm.enum.activitynotifytype
continues to function, but it is related to deprecated methods
crm.activity.*
. A more current alternative is the methods
crm.activity.todo.*
.
The method
crm.enum.activitynotifytype
returns notification types for the
NOTIFY_TYPE
field of
meetings and calls
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.activitynotifytype
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
https://**put_your_bitrix24_address**/rest/crm.enum.activitynotifytype
try
{
const
response =
await
$b24.
callMethod
(
"crm.enum.activitynotifytype"
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
'crm.enum.activitynotifytype'
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
'Error calling crm.enum.activitynotifytype: '
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
"crm.enum.activitynotifytype"
,
{},
function
(
result
) {
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
'crm.enum.activitynotifytype'
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
[
{
"ID"
:
0
,
"NAME"
:
""
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
1
,
"NAME"
:
"min."
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
2
,
"NAME"
:
"hr."
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
3
,
"NAME"
:
"day."
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
]
,
"time"
:
{
"start"
:
1750150460.961181
,
"finish"
:
1750150461.006235
,
"duration"
:
0.045053958892822266
,
"processing"
:
0.00042510032653808594
,
"date_start"
:
"2025-06-17T11:54:20+02:00"
,
"date_finish"
:
"2025-06-17T11:54:21+02:00"
,
"operating_reset_at"
:
1750151061
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
Array with notification types for activity start
(detailed description)
time
time
Information about the request execution time
Fields of the result array
Fields of the result array
Name
type
Description
ID
integer
Identifier of the notification type
NAME
string
Name of the notification type
SYMBOL_CODE
string
Symbolic code
SYMBOL_CODE_SHORT
string
Short symbolic code
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
Enumerations: Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
Activity Priorities
Next
Description Type

---

## Get enumeration items "Description Type" crm.enum.contenttype

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/outdated/crm-enum-content-type

Get enumeration items "Description Type" crm.enum.contenttype | Bitrix24 REST API and Marketplace Applications
Get enumeration items "Description Type" crm.enum.contenttype
Get enumeration items "Description Type" crm.enum.contenttype
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
Method development has been discontinued
The method
crm.enum.contenttype
continues to function, but it is related to deprecated methods
crm.activity.*
. A more current equivalent is the methods
crm.activity.todo.*
.
The method
crm.enum.contenttype
returns description types for the
DESCRIPTION_TYPE
field of
deals
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.contenttype
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
https://**put_your_bitrix24_address**/rest/crm.enum.contenttype
try
{
const
response =
await
$b24.
callMethod
(
'crm.enum.contenttype'
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
'crm.enum.contenttype'
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
'Error calling crm.enum.contenttype: '
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
"crm.enum.contenttype"
,
{},
function
(
result
) {
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
'crm.enum.contenttype'
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
[
{
"ID"
:
0
,
"NAME"
:
""
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
1
,
"NAME"
:
"Plain text"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
2
,
"NAME"
:
"bbCode"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
3
,
"NAME"
:
"HTML"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
]
,
"time"
:
{
"start"
:
1750152369.176959
,
"finish"
:
1750152369.209383
,
"duration"
:
0.032423973083496094
,
"processing"
:
0.0003228187561035156
,
"date_start"
:
"2025-06-17T12:26:09+02:00"
,
"date_finish"
:
"2025-06-17T12:26:09+02:00"
,
"operating_reset_at"
:
1750152969
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
Array with description types
(detailed description)
time
time
Information about the request execution time
Fields of the result array
Fields of the result array
Name
type
Description
ID
integer
Identifier of the description type
NAME
string
Name of the description type
SYMBOL_CODE
string
Symbolic code
SYMBOL_CODE_SHORT
string
Short symbolic code
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
Enumerations: Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
Notification Type for Activity Start
Next
Status

---

## Get enumeration items "Status" crm.enum.activitystatus

**Source:** https://apidocs.bitrix24.com/api-reference/crm/auxiliary/enum/outdated/crm-enum-activity-status

Get enumeration items "Status" crm.enum.activitystatus | Bitrix24 REST API and Marketplace Applications
Get enumeration items "Status" crm.enum.activitystatus
Get enumeration items "Status" crm.enum.activitystatus
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
Method development has been discontinued
The method
crm.enum.activitystatus
continues to function, but it is related to deprecated methods
crm.activity.*
. A more current equivalent is the methods
crm.activity.todo.*
.
The method
crm.enum.activitystatus
returns a list of statuses for the
STATUS
field of
deals
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.enum.activitystatus
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
https://**put_your_bitrix24_address**/rest/crm.enum.activitystatus
try
{
const
response =
await
$b24.
callMethod
(
"crm.enum.activitystatus"
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
'crm.enum.activitystatus'
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
'Error calling crm.enum.activitystatus: '
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
"crm.enum.activitystatus"
,
{},
function
(
result
) {
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
'crm.enum.activitystatus'
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
[
{
"ID"
:
0
,
"NAME"
:
""
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
1
,
"NAME"
:
"Pending"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
2
,
"NAME"
:
"Completed"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
,
{
"ID"
:
3
,
"NAME"
:
"Automatically completed"
,
"SYMBOL_CODE"
:
null
,
"SYMBOL_CODE_SHORT"
:
null
}
]
,
"time"
:
{
"start"
:
1750151888.721577
,
"finish"
:
1750151888.752062
,
"duration"
:
0.030485153198242188
,
"processing"
:
0.00038313865661621094
,
"date_start"
:
"2025-06-17T12:18:08+02:00"
,
"date_finish"
:
"2025-06-17T12:18:08+02:00"
,
"operating_reset_at"
:
1750152488
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
Array of activity statuses
(detailed description)
time
time
Information about the request execution time
Fields of the result array
Fields of the result array
Name
type
Description
ID
integer
Identifier of the activity status
NAME
string
Name of the activity status
SYMBOL_CODE
string
Symbolic code
SYMBOL_CODE_SHORT
string
Short symbolic code
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
Enumerations: Overview of Methods
Copied
Was the article helpful?
Yes
No
Previous
Description Type
Next
Overview of Methods

---

