---
description: 'CRM Requisites: Presets, bank details, events'
methods:
- crm.enum.addresstype
- crm.enum.ownertype
- crm.requisite.bankdetail.add
- crm.requisite.bankdetail.delete
- crm.requisite.bankdetail.fields
- crm.requisite.bankdetail.get
- crm.requisite.bankdetail.list
- crm.requisite.bankdetail.update
- crm.requisite.list
- crm.requisite.preset.add
- crm.requisite.preset.countries
- crm.requisite.preset.delete
- crm.requisite.preset.field.add
- crm.requisite.preset.field.availabletoadd
- crm.requisite.preset.field.delete
- crm.requisite.preset.field.fields
- crm.requisite.preset.field.get
- crm.requisite.preset.field.list
- crm.requisite.preset.field.update
- crm.requisite.preset.fields
- crm.requisite.preset.get
- crm.requisite.preset.list
- crm.requisite.preset.update
- crm.requisite.userfield.add
pages: 36
title: 'CRM Requisites: Presets, bank details, events'
---
# CRM Requisites: Presets, bank details, events
> CRM Requisites: Presets, bank details, events
> **36 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [About Requisite Templates](#about-requisite-templates)
- [Create a Template crm.requisite.preset.add](#create-a-template-crmrequisitepresetadd)
- [Update Requisite Template crm.requisite.preset.update](#update-requisite-template-crmrequisitepresetupdate)
- [Get a list of countries for the template crm.requisite.preset.countries](#get-a-list-of-countries-for-the-template-crmrequis)
- [Get Requisite Template Fields by ID crm.requisite.preset.get](#get-requisite-template-fields-by-id-crmrequisitepr)
- [Get a list of requisites templates by filter crm.requisite.preset.list](#get-a-list-of-requisites-templates-by-filter-crmre)
- [Delete the CRM Requisite Template <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-ub973vgc">crm.requisite.preset.delete</code>](#delete-the-crm-requisite-template-code-classyfm-cl)
- [Get Description of the Fields of the Requisite Template crm.requisite.preset.fields](#get-description-of-the-fields-of-the-requisite-tem)
- [Working with Custom Fields in the Requisite Template](#working-with-custom-fields-in-the-requisite-templa)
- [Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add](#add-a-custom-field-to-the-crm-requisite-template-c)
- [Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update](#update-custom-field-of-a-given-requisite-template-)
- [Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd](#get-fields-available-for-addition-to-the-requisite)
- [Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get](#get-custom-field-of-requisite-template-by-id-crmre)
- [Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list](#get-a-list-of-all-customizable-fields-for-a-specif)
- [Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete](#delete-custom-field-from-crm-requisite-template-cr)
- [Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields](#get-description-of-custom-fields-for-the-requisite)
- [About Bank Details](#about-bank-details)
- [Create a new bank detail crm.requisite.bankdetail.add](#create-a-new-bank-detail-crmrequisitebankdetailadd)
- [Update Bank Details crm.requisite.bankdetail.update](#update-bank-details-crmrequisitebankdetailupdate)
- [Get bank details by id crm.requisite.bankdetail.get](#get-bank-details-by-id-crmrequisitebankdetailget)
- [Get a list of bank details by filter crm.requisite.bankdetail.list](#get-a-list-of-bank-details-by-filter-crmrequisiteb)
- [Delete bank detail crm.requisite.bankdetail.delete](#delete-bank-detail-crmrequisitebankdetaildelete)
- [Get Description of Bank Details Fields crm.requisite.bankdetail.fields](#get-description-of-bank-details-fields-crmrequisit)
- [Overview of Events](#overview-of-events)
- [Event onCrmAddressRegister](#event-oncrmaddressregister)
- [Event onCrmAddressUnregister](#event-oncrmaddressunregister)
- [Event onCrmRequisiteAdd](#event-oncrmrequisiteadd)
- [Event onCrmRequisiteUpdate](#event-oncrmrequisiteupdate)
- [Event onCrmRequisiteDelete](#event-oncrmrequisitedelete)
- [Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd](#event-when-adding-a-custom-field-of-a-requisite-on)
- [Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues](#event-on-changing-the-set-of-values-for-a-custom-l)
- [Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate](#event-on-changing-user-field-of-the-requisite-oncr)
- [Event onCrmRequisiteUserFieldDelete](#event-oncrmrequisiteuserfielddelete)
- [Event on adding bank details onCrmBankDetailAdd](#event-on-adding-bank-details-oncrmbankdetailadd)
- [Event onCrmBankDetailUpdate](#event-oncrmbankdetailupdate)
- [Event onCrmBankDetailDelete](#event-oncrmbankdetaildelete)

---

## About Requisite Templates

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/index

About Requisite Templates | Bitrix24 REST API and Marketplace Applications
Fields of the Requisite Template
About Requisite Templates
Fields of the Requisite Template
Overview of Methods
Scope:
crm
Who can execute methods: any user
Fields of the Requisite Template
Fields of the Requisite Template
Name
Description
Read
Write
Required
Immutable
ID
integer
Identifier of the requisite. Automatically created and unique within the account
Yes
No
No
Yes
ENTITY_TYPE_ID
integer
Identifier of the parent object's type.
The identifiers of CRM object types are provided by the method
crm.enum.ownertype
Yes
Yes
Yes
Yes
COUNTRY_ID
integer
Identifier of the country corresponding to the set of fields in the requisite template (to get available values, see the method
crm.requisite.preset.countries
)
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
Modification date. Contains an empty string if the template has not been changed since creation
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
string
Name of the requisite
Yes
Yes
Yes
No
XML_ID
string
External key. Used for exchange operations. Identifier of the external information base object.
The purpose of the field may change by the final developer.
Each application ensures the uniqueness of values in this field. It is recommended to use a unique prefix to avoid collisions with other applications.
Values of the form
#CRM_REQUISITE_PRESET_DEF_...
are reserved in CRM for identifying templates that are used by default. These identifiers should not be used for your purposes, as this may lead to logic violations
Yes
Yes
No
No
ACTIVE
char
Activity status. Uses values
Y
or
N
. Determines the availability of the template in the selection list when adding requisites
Yes
Yes
No
No
SORT
integer
Sorting
Yes
Yes
No
No
Overview of Methods
Overview of Methods
Method
Description
crm.requisite.preset.add
Creates a new requisite template
crm.requisite.preset.update
Modifies a requisite template
crm.requisite.preset.countries
Returns a possible list of countries for requisite templates
crm.requisite.preset.get
Returns a requisite template by identifier
crm.requisite.preset.list
Returns a list of requisite templates by filter
crm.requisite.preset.delete
Deletes a requisite template
crm.requisite.preset.fields
Returns a formal description of the fields of the requisite template
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Create Template

---

## Create a Template crm.requisite.preset.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/crm-requisite-preset-add

Create a Template crm.requisite.preset.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create a Template crm.requisite.preset.add
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
This method creates a new requisites template.
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
for adding the template
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
ENTITY_TYPE_ID
*
integer
Identifier of the parent object's type. Currently, this is only "Requisite" (identifier
8
).
The identifiers of CRM object types are provided by the method
crm.enum.ownertype
COUNTRY_ID
*
integer
Identifier of the country corresponding to the set of fields in the requisites template (for available values, see the method
crm.requisite.preset.countries
)
NAME
*
string
Name of the requisite
XML_ID
string
External key. Used for exchange operations. Identifier of the external information base object.
The purpose of the field may change by the final developer.
Each application ensures the uniqueness of values in this field. It is recommended to use a unique prefix to avoid collisions with other applications.
Values of the form
#CRM_REQUISITE_PRESET_DEF_...
are reserved in CRM for identifying templates that are used by default. These identifiers should not be used for your purposes, as this may lead to logic violations
ACTIVE
char
Activity status. Values
Y
or
N
are used. Determines the availability of the template in the selection list when adding requisites
SORT
integer
Sorting
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
'{"fields":{"ENTITY_TYPE_ID":8,"COUNTRY_ID":1,"NAME":"IP","XML_ID":"EXAMPLE_COMPANY__VALUE_1","ACTIVE":"Y","SORT":520}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"ENTITY_TYPE_ID":8,"COUNTRY_ID":1,"NAME":"IP","XML_ID":"EXAMPLE_COMPANY__VALUE_1","ACTIVE":"Y","SORT":520},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.add"
,
{
fields
:
{
"ENTITY_TYPE_ID"
:
8
,
// For the requisites template, "Requisite" (identifier 8) is always specified, see crm.enum.ownertype
"COUNTRY_ID"
:
1
,
// USA
"NAME"
:
"IP"
,
"XML_ID"
:
"EXAMPLE_COMPANY__VALUE_1"
,
// Unique external identifier
"ACTIVE"
:
"Y"
,
"SORT"
:
520
// Order in the list of templates
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
"Template created with ID "
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
'crm.requisite.preset.add'
,
[
'fields'
=> [
'ENTITY_TYPE_ID'
=>
8
,
'COUNTRY_ID'
=>
1
,
'NAME'
=>
'IP'
,
'XML_ID'
=>
'EXAMPLE_COMPANY__VALUE_1'
,
'ACTIVE'
=>
'Y'
,
'SORT'
=>
520
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
'Template created with ID '
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
'Error creating template: '
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
"crm.requisite.preset.add"
,
{
fields
:
{
"ENTITY_TYPE_ID"
:
8
,
// For the requisites template, "Requisite" (identifier 8) is always specified, see crm.enum.ownertype
"COUNTRY_ID"
:
1
,
// USA
"NAME"
:
"IP"
,
"XML_ID"
:
"EXAMPLE_COMPANY__VALUE_1"
,
// Unique external identifier
"ACTIVE"
:
"Y"
,
"SORT"
:
520
// Order in the list of templates
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
"Template created with ID "
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
'crm.requisite.preset.add'
,
[
'fields'
=>
[
'ENTITY_TYPE_ID'
=>
8
,
'COUNTRY_ID'
=>
1
,
'NAME'
=>
'IP'
,
'XML_ID'
=>
'EXAMPLE_COMPANY__VALUE_1'
,
'ACTIVE'
=>
'Y'
,
'SORT'
=>
520
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
347
,
"time"
:
{
"start"
:
1716543593.35189
,
"finish"
:
1716543593.683898
,
"duration"
:
0.33200788497924805
,
"processing"
:
0.016175031661987305
,
"date_start"
:
"2024-05-24T11:39:53+02:00"
,
"date_finish"
:
"2024-05-24T11:39:53+02:00"
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
Identifier of the created requisites template
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
"ENTITY_TYPE_ID is not defined or invalid"
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
The identifier of the parent object's type is not defined or has an invalid value
Access denied
Insufficient access permissions to add the template
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
Update Requisite Template crm.requisite.preset.update
Get a list of countries for the template crm.requisite.preset.countries
Get Requisite Template Fields by ID crm.requisite.preset.get
Get a list of requisites templates by filter crm.requisite.preset.list
Delete the CRM Requisite Template `crm.requisite.preset.delete`
Get Description of the Fields of the Requisite Template crm.requisite.preset.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Requisite Template

---

## Update Requisite Template crm.requisite.preset.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/crm-requisite-preset-update

Update Requisite Template crm.requisite.preset.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Requisite Template crm.requisite.preset.update
Method Parameters
fields Parameter
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
This method updates the requisite template.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the requisite template to be updated. Can be obtained using the method
crm.requisite.preset.list
fields
*
array
Set of template fields — an object of the form
{"field": "value"[, ...]}
, the values of which need to be changed
fields Parameter
fields Parameter
Required parameters are marked with *
Name
type
Description
NAME
*
string
Name of the requisite
XML_ID
string
External key. Used for exchange operations. Identifier of the external information base object.
The purpose of the field may change by the final developer.
Each application ensures the uniqueness of values in this field. It is recommended to use a unique prefix to avoid collisions with other applications.
Values of the form
#CRM_REQUISITE_PRESET_DEF_...
are reserved in CRM for identifying templates that are used by default. These identifiers should not be used for your purposes, as this may lead to logic violations
ACTIVE
char
Activity status. Uses values
Y
or
N
. Determines the availability of the template in the selection list when adding requisites
SORT
integer
Sorting
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
'{"id":347,"fields":{"NAME":"IP (archive)","ACTIVE":"N"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":347,"fields":{"NAME":"IP (archive)","ACTIVE":"N"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.update"
,
{
id
:
347
,
// Identifier of the template to be updated.
fields
:
{
"NAME"
:
"IP (archive)"
,
"ACTIVE"
:
"N"
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
'crm.requisite.preset.update'
,
[
'id'
=>
347
,
'fields'
=> [
'NAME'
=>
'IP (archive)'
,
'ACTIVE'
=>
'N'
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
'Error updating requisite preset: '
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
"crm.requisite.preset.update"
,
{
id
:
347
,
// Identifier of the template to be updated.
fields
:
{
"NAME"
:
"IP (archive)"
,
"ACTIVE"
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
'crm.requisite.preset.update'
,
[
'id'
=>
347
,
'fields'
=>
[
'NAME'
=>
'IP (archive)'
,
'ACTIVE'
=>
'N'
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
1716566193.821566
,
"finish"
:
1716566194.075617
,
"duration"
:
0.25405097007751465
,
"processing"
:
0.03606295585632324
,
"date_start"
:
"2024-05-24T17:56:33+02:00"
,
"date_finish"
:
"2024-05-24T17:56:34+02:00"
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
Result of updating the template:
true
— template updated
false
— template not updated
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
"The Preset with ID '347' is not found"
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
The Preset with ID '347' is not found
Template with the specified identifier not found
Access denied
Insufficient access permissions to update the template
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
Create a Template crm.requisite.preset.add
Get a list of countries for the template crm.requisite.preset.countries
Get Requisite Template Fields by ID crm.requisite.preset.get
Get a list of requisites templates by filter crm.requisite.preset.list
Delete the CRM Requisite Template `crm.requisite.preset.delete`
Get Description of the Fields of the Requisite Template crm.requisite.preset.fields
Copied
Was the article helpful?
Yes
No
Previous
Create Template
Next
Get List of Countries for Template

---

## Get a list of countries for the template crm.requisite.preset.countries

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/crm-requisite-preset-countries

Get a list of countries for the template crm.requisite.preset.countries | Bitrix24 REST API and Marketplace Applications
Code Examples
Get a list of countries for the template crm.requisite.preset.countries
Code Examples
Response Handling
Returned Data
Fields of the country object
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a possible list of countries for
requisite templates
. Country identifiers are used as values for the
COUNTRY_ID
field of the template.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.countries
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
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.countries
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.preset.countries'
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
'crm.requisite.preset.countries'
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
'Error fetching countries: '
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
"crm.requisite.preset.countries"
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
'crm.requisite.preset.countries'
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
"CODE"
:
"US"
,
"TITLE"
:
"United States"
}
,
{
"ID"
:
4
,
"CODE"
:
"BY"
,
"TITLE"
:
"Belarus"
}
,
{
"ID"
:
6
,
"CODE"
:
"KZ"
,
"TITLE"
:
"Kazakhstan"
}
,
{
"ID"
:
14
,
"CODE"
:
"UA"
,
"TITLE"
:
"Ukraine"
}
,
{
"ID"
:
34
,
"CODE"
:
"BR"
,
"TITLE"
:
"Brazil"
}
,
{
"ID"
:
46
,
"CODE"
:
"DE"
,
"TITLE"
:
"Germany"
}
,
{
"ID"
:
77
,
"CODE"
:
"CO"
,
"TITLE"
:
"Colombia"
}
,
{
"ID"
:
110
,
"CODE"
:
"PL"
,
"TITLE"
:
"Poland"
}
,
{
"ID"
:
122
,
"CODE"
:
"US"
,
"TITLE"
:
"United States"
}
,
{
"ID"
:
132
,
"CODE"
:
"FR"
,
"TITLE"
:
"France"
}
]
,
"time"
:
{
"start"
:
1716549490.84839
,
"finish"
:
1716549491.239788
,
"duration"
:
0.39139795303344727
,
"processing"
:
0.017835140228271484
,
"date_start"
:
"2024-05-24T13:18:10+02:00"
,
"date_finish"
:
"2024-05-24T13:18:11+02:00"
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
An array of objects describing countries
time
time
Information about the request execution time
Fields of the country object
Fields of the country object
Name
type
Description
ID
integer
Identifier
CODE
string
Character code according to the
ISO 3166-1
standard
TITLE
string
Name
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
Create a Template crm.requisite.preset.add
Update Requisite Template crm.requisite.preset.update
Get Requisite Template Fields by ID crm.requisite.preset.get
Get a list of requisites templates by filter crm.requisite.preset.list
Delete the CRM Requisite Template `crm.requisite.preset.delete`
Get Description of the Fields of the Requisite Template crm.requisite.preset.fields
Copied
Was the article helpful?
Yes
No
Previous
Update Requisite Template
Next
Get Requisite Template Fields by ID

---

## Get Requisite Template Fields by ID crm.requisite.preset.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/crm-requisite-preset-get

Get Requisite Template Fields by ID crm.requisite.preset.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Requisite Template Fields by ID crm.requisite.preset.get
Method Parameters
Code Examples
Response Handling
Returned Data
Description of Requisite Template Fields
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method returns the requisite template by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the requisite template. Can be obtained using the method
crm.requisite.preset.list
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
'{"id":347}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":347,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.get
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.get"
,
{
id
:
347
}
// Identifier of the requisite template.
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
'crm.requisite.preset.get'
,
[
'id'
=>
347
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
'Error getting requisite preset: '
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
"crm.requisite.preset.get"
,
{
id
:
347
},
// Identifier of the requisite template.
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
'crm.requisite.preset.get'
,
[
'id'
=>
347
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
"347"
,
"ENTITY_TYPE_ID"
:
"8"
,
"COUNTRY_ID"
:
"1"
,
"DATE_CREATE"
:
"2024-05-24T15:45:44+02:00"
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
"Individual Entrepreneur"
,
"XML_ID"
:
"EXAMPLE_COMPANY__VALUE_1"
,
"ACTIVE"
:
"Y"
,
"SORT"
:
"520"
}
,
"time"
:
{
"start"
:
1716558423.336056
,
"finish"
:
1716558424.695338
,
"duration"
:
1.3592820167541504
,
"processing"
:
0.06150317192077637
,
"date_start"
:
"2024-05-24T15:47:03+02:00"
,
"date_finish"
:
"2024-05-24T15:47:04+02:00"
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
An object containing the values of the template fields
time
time
Information about the request execution time
Description of Requisite Template Fields
Description of Requisite Template Fields
Name
type
Description
ID
integer
Identifier of the requisite. Automatically created and unique within the account
ENTITY_TYPE_ID
integer
Identifier of the parent object type.
The identifiers of CRM object types are provided by the method
crm.enum.ownertype
COUNTRY_ID
integer
Identifier of the country corresponding to the requisite template field set (for available values see the method
crm.requisite.preset.countries
)
DATE_CREATE
datetime
Creation date
DATE_MODIFY
datetime
Modification date. Contains an empty string if the template has not been changed since creation
CREATED_BY_ID
user
Identifier of the user who created the requisite
MODIFY_BY_ID
user
Identifier of the user who modified the requisite
NAME
string
Name of the requisite
XML_ID
string
External key. Used for exchange operations. Identifier of the external information base object.
The purpose of the field may change by the final developer.
Each application ensures the uniqueness of values in this field. It is recommended to use a unique prefix to avoid collisions with other applications.
Values of the form
#CRM_REQUISITE_PRESET_DEF_...
are reserved in CRM for identifying templates that are used by default. These identifiers should not be used for your purposes, as this may lead to logic violations
ACTIVE
char
Activity status. Uses values
Y
or
N
. Determines the availability of the template in the selection list when adding requisites
SORT
integer
Sorting
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
"The Preset with ID '347' is not found"
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
The Preset with ID '347' is not found
The template with the specified identifier was not found
Access denied
Insufficient access permissions to retrieve the template
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
Create a Template crm.requisite.preset.add
Update Requisite Template crm.requisite.preset.update
Get a list of countries for the template crm.requisite.preset.countries
Get a list of requisites templates by filter crm.requisite.preset.list
Delete the CRM Requisite Template `crm.requisite.preset.delete`
Get Description of the Fields of the Requisite Template crm.requisite.preset.fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of Countries for Template
Next
Get List of Requisite Templates by Filter

---

## Get a list of requisites templates by filter crm.requisite.preset.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/crm-requisite-preset-list

Get a list of requisites templates by filter crm.requisite.preset.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of requisites templates by filter crm.requisite.preset.list
Method Parameters
Description of requisites template fields
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
The method returns a list of requisites templates based on the filter.
Method Parameters
Method Parameters
Name
type
Description
select
array
An array of fields to select (see
template fields
).
If the array is not provided or an empty array is passed, all available template fields will be selected.
filter
object
An object for filtering selected templates in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
correspond to
template fields
.
An additional prefix can be set for the key to clarify the filter behavior. Possible prefix values:
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
symbol in the filter value does not need to be passed. The search looks for the substring in any position of the string.
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
!%
— NOT LIKE, substring search. The
%
symbol in the filter value does not need to be passed. The search goes from both sides.
!=%
— NOT LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
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
An object for sorting selected templates in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
correspond to
template fields
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
Description of requisites template fields
Description of requisites template fields
Name
type
Description
ID
integer
Identifier of the requisite. Automatically created and unique within the account.
ENTITY_TYPE_ID
integer
Identifier of the parent object's type.
The identifiers of CRM object types are provided by the method
crm.enum.ownertype
.
COUNTRY_ID
integer
Identifier of the country corresponding to the set of requisites template fields (to get available values, see the method
crm.requisite.preset.countries
).
DATE_CREATE
datetime
Creation date.
DATE_MODIFY
datetime
Modification date. Contains an empty string if the template has not been modified since creation.
CREATED_BY_ID
user
Identifier of the user who created the requisite.
MODIFY_BY_ID
user
Identifier of the user who modified the requisite.
NAME
string
Name of the requisite.
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information base.
The purpose of the field may change by the final developer.
Each application ensures the uniqueness of values in this field. It is recommended to use a unique prefix to avoid collisions with other applications.
Values of the form
#CRM_REQUISITE_PRESET_DEF_...
are reserved in CRM for identifying templates that are used by default. These identifiers should not be used for your purposes, as this may lead to logic violations.
ACTIVE
char
Activity status. Uses values
Y
or
N
. Determines the availability of the template in the selection list when adding requisites.
SORT
integer
Sorting.
Code Examples
Code Examples
How to Use Examples in Documentation
Searching for templates by country binding:
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
'{"order":{"ID":"ASC"},"filter":{"COUNTRY_ID":"1"},"select":["ID","NAME"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"ID":"ASC"},"filter":{"COUNTRY_ID":"1"},"select":["ID","NAME"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.list
// callListMethod is recommended when you need to get the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.requisite.preset.list'
,
{
order
: {
"ID"
:
"ASC"
},
filter
: {
"COUNTRY_ID"
:
"1"
},
select
: [
"ID"
,
"NAME"
]
},
(
progress
) =>
{
if
(progress.
error
())
console
.
error
(progress.
error
());
else
{
console
.
dir
(progress.
data
());
if
(progress.
more
())
progress.
next
();
}
}
)
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
'crm.requisite.preset.list'
, {
order
: {
"ID"
:
"ASC"
},
filter
: {
"COUNTRY_ID"
:
"1"
},
select
: [
"ID"
,
"NAME"
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
dir
(entity);
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
'crm.requisite.preset.list'
, {
order
: {
"ID"
:
"ASC"
},
filter
: {
"COUNTRY_ID"
:
"1"
},
select
: [
"ID"
,
"NAME"
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
dir
(entity);
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.requisite.preset.list'
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
'COUNTRY_ID'
=>
'1'
],
'select'
=> [
'ID'
,
'NAME'
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
'Error fetching requisite presets: '
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
"crm.requisite.preset.list"
,
{
order
: {
"ID"
:
"ASC"
},
filter
: {
"COUNTRY_ID"
:
"1"
},
select
: [
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
'crm.requisite.preset.list'
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
'COUNTRY_ID'
=>
'1'
],
'select'
=> [
'ID'
,
'NAME'
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
"1"
,
"NAME"
:
"Organization"
}
,
{
"ID"
:
"2"
,
"NAME"
:
"Sole Proprietor"
}
,
{
"ID"
:
"3"
,
"NAME"
:
"Individual"
}
,
{
"ID"
:
"4"
,
"NAME"
:
"Organization (additional)"
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
1716564019.674636
,
"finish"
:
1716564020.067474
,
"duration"
:
0.3928380012512207
,
"processing"
:
0.02863287925720215
,
"date_start"
:
"2024-05-24T17:20:19+02:00"
,
"date_finish"
:
"2024-05-24T17:20:20+02:00"
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
An array of objects with information about the selected templates. Each element contains the selected
template fields
.
total
integer
Total number of records found.
time
time
Information about the execution time of the request.
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
Insufficient access permissions to retrieve the list of templates.
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
Create a Template crm.requisite.preset.add
Update Requisite Template crm.requisite.preset.update
Get a list of countries for the template crm.requisite.preset.countries
Get Requisite Template Fields by ID crm.requisite.preset.get
Delete the CRM Requisite Template `crm.requisite.preset.delete`
Get Description of the Fields of the Requisite Template crm.requisite.preset.fields
Add a Company with Details via Web Form
Add a contact with details via a web form
Copied
Was the article helpful?
Yes
No
Previous
Get Requisite Template Fields by ID
Next
Delete Requisite Template

---

## Delete the CRM Requisite Template <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-ub973vgc">crm.requisite.preset.delete</code>

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/crm-requisite-preset-delete

Delete the CRM Requisite Template <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-ub973vgc">crm.requisite.preset.delete</code> | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete the CRM Requisite Template
crm.requisite.preset.delete
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
This method deletes a requisite template by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the requisite template. It can be obtained using the method
crm.requisite.preset.list
Code Examples
Code Examples
How to Use Examples in Documentation
Searching for templates by country binding:
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
'{"id":347}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":347,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.delete"
,
{
id
:
347
// Identifier of the template to be deleted
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
'crm.requisite.preset.delete'
,
[
'id'
=>
347
,    // Identifier of the template to be deleted
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
'Error deleting preset: '
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
"crm.requisite.preset.delete"
,
{
id
:
347
// Identifier of the template to be deleted
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
'crm.requisite.preset.delete'
,
[
'id'
=>
347
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
1716554949.294631
,
"finish"
:
1716554949.795059
,
"duration"
:
0.5004279613494873
,
"processing"
:
0.057311058044433594
,
"date_start"
:
"2024-05-24T14:49:09+02:00"
,
"date_finish"
:
"2024-05-24T14:49:09+02:00"
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
Result of the template deletion:
true
— template deleted
false
— template not deleted
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
"The Preset with ID '347' is not found"
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
The Preset with ID '347' is not found
Template with the specified identifier not found
You cannot delete the template as requisites have already been created for it
Cannot delete the template for which requisites have been created. To delete the template, first delete the requisites
Access denied
Insufficient access permissions to delete the template
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
Create a Template crm.requisite.preset.add
Update Requisite Template crm.requisite.preset.update
Get a list of countries for the template crm.requisite.preset.countries
Get Requisite Template Fields by ID crm.requisite.preset.get
Get a list of requisites templates by filter crm.requisite.preset.list
Get Description of the Fields of the Requisite Template crm.requisite.preset.fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of Requisite Templates by Filter
Next
Get Description of Requisite Template Fields

---

## Get Description of the Fields of the Requisite Template crm.requisite.preset.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/crm-requisite-preset-fields

Get Description of the Fields of the Requisite Template crm.requisite.preset.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Description of the Fields of the Requisite Template crm.requisite.preset.fields
Code Examples
Response Handling
Returned Data
Description of the Requisite Template Fields
Description of Attributes
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a formal description of the fields of the requisite template.
No parameters.
Code Examples
Code Examples
How to Use Examples in Documentation
Searching for templates by country binding:
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.fields
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
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.fields"
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
'crm.requisite.preset.fields'
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
'Error fetching requisite preset fields: '
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
"crm.requisite.preset.fields"
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
'crm.requisite.preset.fields'
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
"Object Type ID"
}
,
"COUNTRY_ID"
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
"Country ID"
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
"Name"
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
}
,
"time"
:
{
"start"
:
1716555914.663808
,
"finish"
:
1716555914.996533
,
"duration"
:
0.33272480964660645
,
"processing"
:
0.008843183517456055
,
"date_start"
:
"2024-05-24T15:05:14+02:00"
,
"date_finish"
:
"2024-05-24T15:05:14+02:00"
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
Description of the Requisite Template Fields
Description of the Requisite Template Fields
Name
type
Description
ID
integer
Identifier of the requisite. Created automatically and unique within the account
ENTITY_TYPE_ID
integer
Identifier of the parent object's type. Currently, this is only "Requisite" (identifier
8
).
The identifiers of CRM object types are provided by the method
crm.enum.ownertype
COUNTRY_ID
integer
Identifier of the country corresponding to the set of fields of the requisite template (to get available values, see the method
crm.requisite.preset.countries
)
DATE_CREATE
datetime
Creation date
DATE_MODIFY
datetime
Modification date. Contains an empty string if the template has not been changed since creation
CREATED_BY_ID
user
Identifier of the user who created the requisite
MODIFY_BY_ID
user
Identifier of the user who modified the requisite
NAME
string
Name of the requisite
XML_ID
string
External key. Used for exchange operations. Identifier of the external information base object.
The purpose of the field may change by the final developer.
Each application ensures the uniqueness of values in this field. It is recommended to use a unique prefix to avoid collisions with other applications.
In CRM, values of the form
#CRM_REQUISITE_PRESET_DEF_...
are reserved for identifying templates that are used by default. These identifiers should not be used for your purposes, as this may lead to logic violations
ACTIVE
char
Activity status. Uses values
Y
or
N
. Determines the availability of the template in the selection list when adding requisites
SORT
integer
Sorting
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
Required attribute. Possible values:
true — yes
false — no
isReadOnly
boolean
Read-only attribute. Possible values:
true — yes
false — no
isImmutable
boolean
Immutable attribute. Possible values:
true — yes
false — no
isMultiple
boolean
Multi-field attribute. Possible values:
true — yes
false — no
isDynamic
boolean
Custom attribute. Possible values:
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
Create a Template crm.requisite.preset.add
Update Requisite Template crm.requisite.preset.update
Get a list of countries for the template crm.requisite.preset.countries
Get Requisite Template Fields by ID crm.requisite.preset.get
Get a list of requisites templates by filter crm.requisite.preset.list
Delete the CRM Requisite Template `crm.requisite.preset.delete`
Copied
Was the article helpful?
Yes
No
Previous
Delete Requisite Template
Next
Overview of Methods

---

## Working with Custom Fields in the Requisite Template

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/fields/index

Working with Custom Fields in the Requisite Template | Bitrix24 REST API and Marketplace Applications
Working with Custom Fields in the Requisite Template
Working with Custom Fields in the Requisite Template
Fields Describing the Custom Field in the Requisite Template
Overview of Methods
Scope:
crm
Who can perform the methods: any user
Custom fields are fields that can be added or removed from the template.
In the requisites editing form, in addition to the system fields that are present in any requisite (such as
Name
or
Comment
), there are other fields (like
Tax ID
and
KPP
) that are customizable. The methods in this section are designed to manage the list of such fields for a specific template.
Custom fields can be divided into two categories: pre-installed and user-defined.
The set of pre-installed fields is fixed for each supported country. Any such field can be added to a template related to the corresponding country if it is not already present in the template. Pre-installed fields have the prefix
RQ_
.
User-defined fields are added either by the user or through the corresponding
REST methods
. A created user-defined field can be added to a template. User-defined fields can be added to templates of any supported country. User-defined fields have the prefix
UF_
. If a user-defined field is used in templates for different countries, it is essential to ensure that it has the same meaning and name in the interface for them.
The
FIELD_NAME
field is essentially a reference to an existing field, either pre-installed or user-defined.
Fields Describing the Custom Field in the Requisite Template
Fields Describing the Custom Field in the Requisite Template
Name
type
Description
Read
Write
Required
ID
integer
Identifier of the field. Automatically created and unique within the template
Yes
No
No
FIELD_NAME
string
Name of the field
Yes
Yes
Yes
FIELD_TITLE
string
Alternative name for the field in the requisite.
The alternative name is displayed in various forms for filling out requisites. Depending on the specific form, the alternative name may or may not be used
Yes
Yes
No
SORT
integer
Sorting. Order in the list of fields in the template
Yes
Yes
No
IN_SHORT_LIST
char
Show in the short list. Deprecated field, currently not used. Retained for backward compatibility. Can take values
Y
or
N
Yes
Yes
No
Use the method
crm.requisite.preset.field.fields
to get a formal description of the fields.
Overview of Methods
Overview of Methods
Method
Description
crm.requisite.preset.field.add
Adds a custom field to the requisites template
crm.requisite.preset.field.update
Modifies a custom field in the requisites template
crm.requisite.preset.field.availabletoadd
Returns fields available for addition to the specified requisites template
crm.requisite.preset.field.get
Returns the description of the custom field in the requisites template by identifier
crm.requisite.preset.field.list
Returns a list of all custom fields for a specific requisites template
crm.requisite.preset.field.delete
Removes a custom field from the requisites template
crm.requisite.preset.field.fields
Returns a formal description of the fields describing the custom field in the requisites template
Copied
Was the article helpful?
Yes
No
Previous
Get Description of Requisite Template Fields
Next
Add Custom Field to Requisite Template

---

## Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/fields/crm-requisite-preset-field-add

Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add | Bitrix24 REST API and Marketplace Applications
Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add
Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add
Method Parameters
Fields Parameter
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
This method adds a custom field to the requisite template. You can use the method
crm.requisite.preset.field.availabletoadd
to retrieve the fields available for addition to the template.
Before adding a user-defined field
UF_...
to the template, it must be created using the method
crm.requisite.userfield.add
or ensure that it already exists.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
preset
*
object
An object containing the identifier of the template to which the custom field is added (e.g.,
{"ID": 27}
).
Template identifiers can be obtained using the method
crm.requisite.preset.list
fields
*
object
A set of fields — an object of the form
{"field": "value"[, ...]}
for adding the custom field to the template
Fields Parameter
Fields Parameter
Required parameters are marked with *
Name
type
Description
FIELD_NAME
*
string
The name of the field.
FIELD_TITLE
string
An alternative name for the field in the requisite.
The alternative name is displayed in various forms for filling out requisites. Depending on the specific form, the alternative name may or may not be used
SORT
integer
Sorting. The order in the list of template fields
IN_SHORT_LIST
char
Show in the short list. Deprecated field, currently not used. Retained for backward compatibility. Can take values
Y
or
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
'{"preset":{"ID":27},"fields":{"FIELD_NAME":"RQ_NAME","FIELD_TITLE":"TEST","IN_SHORT_LIST":"N","SORT":580}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.field.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"preset":{"ID":27},"fields":{"FIELD_NAME":"RQ_NAME","FIELD_TITLE":"TEST","IN_SHORT_LIST":"N","SORT":580},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.field.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.field.add"
,
{
preset
:
{
"ID"
:
27
// Template identifier
},
fields
:
// Object describing the custom field
{
"FIELD_NAME"
:
"RQ_NAME"
,
"FIELD_TITLE"
:
"TEST"
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
580
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
"Custom field with ID "
+ result +
" added to the template"
);
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
'crm.requisite.preset.field.add'
,
[
'preset'
=> [
'ID'
=>
27
, // Template identifier
],
'fields'
=> [ // Object describing the custom field
'FIELD_NAME'
=>
'RQ_NAME'
,
'FIELD_TITLE'
=>
'TEST'
,
'IN_SHORT_LIST'
=>
'N'
,
'SORT'
=>
580
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
'Custom field with ID '
.
$result
.
' added to the template'
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
'Error adding custom field: '
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
"crm.requisite.preset.field.add"
,
{
preset
:
{
"ID"
:
27
// Template identifier
},
fields
:
// Object describing the custom field
{
"FIELD_NAME"
:
"RQ_NAME"
,
"FIELD_TITLE"
:
"TEST"
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
580
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
"Custom field with ID "
+ result.
data
() +
" added to the template"
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
'crm.requisite.preset.field.add'
,
[
'preset'
=> [
'ID'
=>
27
],
'fields'
=> [
'FIELD_NAME'
=>
'RQ_NAME'
,
'FIELD_TITLE'
=>
'TEST'
,
'IN_SHORT_LIST'
=>
'N'
,
'SORT'
=>
580
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
3
,
"time"
:
{
"start"
:
1716811635.108203
,
"finish"
:
1716811635.503093
,
"duration"
:
0.39489006996154785
,
"processing"
:
0.043524980545043945
,
"date_start"
:
"2024-05-27T14:07:15+02:00"
,
"date_finish"
:
"2024-05-27T14:07:15+02:00"
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
Identifier of the added field
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP Status:
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
"The field 'RQ_NAME' cannot be added."
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
The field 'RQ_NAME' cannot be added
The field cannot be added. The field may already exist in the template or it is not available for the country to which the template belongs
The Preset with ID '27' is not found
Template with the specified identifier not found
Access denied
Insufficient access permissions to add the custom field to the requisite template
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
Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update
Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd
Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get
Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list
Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete
Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Custom Field of a Given Requisite Template

---

## Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/fields/crm-requisite-preset-field-update

Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update
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
This method updates a custom field in the requisite template.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the custom field to be updated.
Identifiers of custom fields in the requisite template can be obtained using the
crm.requisite.preset.field.list
method.
preset
*
object
An object containing the identifier of the template to which the custom field is added (e.g.,
{"ID": 27}
).
Template identifiers can be obtained using the
crm.requisite.preset.list
method.
fields
*
object
An object with fields and their values that need to be updated. The
crm.requisite.preset.field.fields
method allows you to get the description of the fields that can be modified.
The API requires a value to be specified in the
FIELD_NAME
field. If it does not need to be changed, the current value can be specified.
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
FIELD_NAME
*
string
Name of the field.
The API requires a value to be specified in this field. If it does not need to be changed, the current value can be specified.
FIELD_TITLE
string
Alternative name of the field for the requisite.
The alternative name is displayed in various forms for filling out requisites. Depending on the specific form, the alternative name may or may not be used.
SORT
integer
Sorting. Order in the list of template fields.
IN_SHORT_LIST
char
Show in the short list. Deprecated field, currently not used. Retained for backward compatibility. Can take values
Y
or
N
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
'{"ID":1,"preset":{"ID":27},"fields":{"FIELD_NAME":"RQ_NAME","FIELD_TITLE":"Name","IN_SHORT_LIST":"Y"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.field.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":1,"preset":{"ID":27},"fields":{"FIELD_NAME":"RQ_NAME","FIELD_TITLE":"Name","IN_SHORT_LIST":"Y"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.field.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.field.update"
,
{
ID
:
1
,
preset
:
{
"ID"
:
27
},
fields
:
{
"FIELD_NAME"
:
"RQ_NAME"
,
"FIELD_TITLE"
:
"Name"
,
"IN_SHORT_LIST"
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
'crm.requisite.preset.field.update'
,
[
'ID'
=>
1
,
'preset'
=> [
'ID'
=>
27
,
],
'fields'
=> [
'FIELD_NAME'
=>
'RQ_NAME'
,
'FIELD_TITLE'
=>
'Name'
,
'IN_SHORT_LIST'
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
'Error updating preset field: '
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
"crm.requisite.preset.field.update"
,
{
ID
:
1
,
// Identifier of the custom field to be updated
preset
:
{
"ID"
:
27
// Identifier of the requisite template
},
fields
:
// Values of the fields to be updated
{
"FIELD_NAME"
:
"RQ_NAME"
,
// The API requires a value to be specified in this field. If
// the value does not need to be changed, keep the current one.
"FIELD_TITLE"
:
"Name"
,
"IN_SHORT_LIST"
:
"Y"
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
'crm.requisite.preset.field.update'
,
[
'ID'
=>
1
,
'preset'
=> [
'ID'
=>
27
],
'fields'
=> [
'FIELD_NAME'
=>
'RQ_NAME'
,
'FIELD_TITLE'
=>
'Name'
,
'IN_SHORT_LIST'
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
1716898310.398361
,
"finish"
:
1716898310.936332
,
"duration"
:
0.537971019744873
,
"processing"
:
0.09376883506774902
,
"date_start"
:
"2024-05-28T14:11:50+02:00"
,
"date_finish"
:
"2024-05-28T14:11:50+02:00"
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
Result of updating the custom field:
true
— updated
false
— not updated
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
""
,
"error_description"
:
"The PresetField with ID '27' is not found"
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
The PresetField with ID '1' is not found
The field with the specified identifier was not found.
The Preset with ID '27' is not found
The template with the specified identifier was not found.
ID is not defined or invalid
The field identifier is not specified or has an invalid value.
Access denied
Insufficient access permissions to delete the field from the requisite template.
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
Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add
Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd
Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get
Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list
Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete
Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields
Copied
Was the article helpful?
Yes
No
Previous
Add Custom Field to Requisite Template
Next
Get Fields Available for Addition to Requisite Template

---

## Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/fields/crm-requisite-preset-field-available-to-add

Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd
Method Parameters
Code Examples
Response Handling
Returned Data
Field Descriptions
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns fields available for addition to the specified requisite template.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
preset
*
object
An object containing the identifier of the template for which to retrieve the list of available customizable fields.
Template identifiers can be obtained using the
crm.requisite.preset.list
method.
Fields with the prefix
UF_
in the response are custom fields (see
methods
for working with custom requisite fields)
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
'{"preset":{"ID":27}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.field.availabletoadd
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"preset":{"ID":27},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.field.availabletoadd
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.field.availabletoadd"
,
{
preset
:
{
"ID"
:
27
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
'crm.requisite.preset.field.availabletoadd'
,
[
'preset'
=> [
'ID'
=>
27
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
'Error checking available fields: '
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
"crm.requisite.preset.field.availabletoadd"
,
{
preset
:
{
"ID"
:
27
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
'crm.requisite.preset.field.availabletoadd'
,
[
'preset'
=> [
'ID'
=>
27
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
[
"RQ_FIRST_NAME"
,
"RQ_LAST_NAME"
,
"RQ_SECOND_NAME"
,
"RQ_COMPANY_NAME"
,
"RQ_COMPANY_FULL_NAME"
,
"RQ_COMPANY_REG_DATE"
,
"RQ_DIRECTOR"
,
"RQ_ACCOUNTANT"
,
"RQ_ADDR"
,
"RQ_CONTACT"
,
"RQ_EMAIL"
,
"RQ_PHONE"
,
"RQ_FAX"
,
"RQ_IDENT_DOC"
,
"RQ_IDENT_DOC_SER"
,
"RQ_IDENT_DOC_NUM"
,
"RQ_IDENT_DOC_DATE"
,
"RQ_IDENT_DOC_ISSUED_BY"
,
"RQ_IDENT_DOC_DEP_CODE"
,
"RQ_INN"
,
"RQ_KPP"
,
"RQ_IFNS"
,
"RQ_OGRN"
,
"RQ_OGRNIP"
,
"RQ_OKPO"
,
"RQ_OKTMO"
,
"RQ_OKVED"
,
"RQ_ST_CERT_SER"
,
"RQ_ST_CERT_NUM"
,
"RQ_ST_CERT_DATE"
,
"RQ_SIGNATURE"
,
"RQ_STAMP"
,
"UF_CRM_1707997209"
,
"UF_CRM_1707997236"
,
"UF_CRM_1707997253"
,
"UF_CRM_1708012333"
]
}
Returned Data
Returned Data
Name
type
Description
result
array
An array with the names of fields that can be added to the specified requisite template
time
time
Information about the execution time of the request
Field Descriptions
Field Descriptions
Name
type
Description
RQ_FIRST_NAME
string
First name
RQ_LAST_NAME
string
Last name
RQ_SECOND_NAME
string
Middle name
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
RQ_IDENT_DOC
string
Type of document
RQ_IDENT_DOC_SER
string
Series
RQ_IDENT_DOC_NUM
string
Number
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
Tax Identification Number
RQ_KPP
string
Tax Registration Reason Code
RQ_IFNS
string
Tax Authority Code
RQ_OGRN
string
Primary State Registration Number
RQ_OGRNIP
string
Individual Entrepreneur Registration Number
RQ_OKPO
string
All-Russian Classifier of Enterprises and Organizations Code
RQ_OKTMO
string
All-Russian Classifier of Territories Code
RQ_OKVED
string
All-Russian Classifier of Economic Activities Code
RQ_ST_CERT_SER
string
Series of State Registration Certificate
RQ_ST_CERT_NUM
string
Number of State Registration Certificate
RQ_ST_CERT_DATE
string
Date of State Registration Certificate
UF_CRM_1707997209
double
Custom Field of Type "Number"
UF_CRM_1707997236
boolean
Custom Field of Type "Yes/No"
UF_CRM_1707997253
datetime
Custom Field of Type "Date"
UF_CRM_1708012333
string
Custom Field of Type "String"
Error Handling
Error Handling
HTTP Status:
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
"Template not found."
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
Template not found
The template for which to retrieve the list of available fields was not found
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
Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add
Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update
Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get
Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list
Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete
Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields
Copied
Was the article helpful?
Yes
No
Previous
Update Custom Field of a Given Requisite Template
Next
Get Custom Field of Requisite Template by ID

---

## Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/fields/crm-requisite-preset-field-get

Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get
Method Parameters
Code Examples
Response Handling
Returned Data
Fields Describing the Custom Field of the Requisite Template
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns the description of the custom field of the requisite template by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the custom field.
Identifiers of custom fields of the requisite template can be obtained using the
crm.requisite.preset.field.list
method
preset
*
object
An object containing the identifier of the template from which the information about the custom field is extracted (for example,
{"ID": 27}
).
Template identifiers can be obtained using the
crm.requisite.preset.list
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
'{"ID":1,"preset":{"ID":27}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.field.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":1,"preset":{"ID":27},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.field.get
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.field.get"
,
{
ID
:
1
,
// Identifier of the custom field
preset
:
{
"ID"
:
27
// Identifier of the requisite template
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
'crm.requisite.preset.field.get'
,
[
'ID'
=>
1
,
'preset'
=> [
'ID'
=>
27
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
'Error getting preset field: '
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
"crm.requisite.preset.field.get"
,
{
ID
:
1
,
// Identifier of the custom field
preset
:
{
"ID"
:
27
// Identifier of the requisite template
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
'crm.requisite.preset.field.get'
,
[
'ID'
=>
1
,
'preset'
=> [
'ID'
=>
27
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
"ID"
:
1
,
"FIELD_NAME"
:
"RQ_NAME"
,
"FIELD_TITLE"
:
"TEST"
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
580
}
,
"time"
:
{
"start"
:
1716826213.057061
,
"finish"
:
1716826213.541336
,
"duration"
:
0.48427510261535645
,
"processing"
:
0.025674104690551758
,
"date_start"
:
"2024-05-27T18:10:13+02:00"
,
"date_finish"
:
"2024-05-27T18:10:13+02:00"
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
An object containing fields that describe the custom field of the requisite template
time
time
Information about the execution time of the request
Fields Describing the Custom Field of the Requisite Template
Fields Describing the Custom Field of the Requisite Template
Name
type
Description
ID
integer
Identifier of the field. Created automatically and unique within the template
FIELD_TITLE
string
Alternative name of the field for the requisite.
The alternative name is displayed in various forms for filling out requisites. Depending on the specific form, the alternative name may or may not be used
IN_SHORT_LIST
char
Show in the short list. Deprecated field, currently not used. Retained for backward compatibility. Can take values
Y
or
N
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
"The PresetField with ID '1' is not found"
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
The PresetField with ID '1' is not found
The custom field of the template with the specified identifier was not found
The Preset with ID '27' is not found
The template with the specified identifier was not found
Access denied
Insufficient access permissions to retrieve the custom field of the template
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
Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add
Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update
Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd
Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list
Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete
Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields
Copied
Was the article helpful?
Yes
No
Previous
Get Fields Available for Addition to Requisite Template
Next
Get List of All Custom Fields of a Given Requisite Template

---

## Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/fields/crm-requisite-preset-field-list

Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list
Method Parameters
Code Examples
Response Handling
Returned Data
Fields Describing the Customizable Field of the Requisites Template
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a list of all customizable fields for a specific requisites template.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
preset
*
object
An object containing the identifier value of the template from which the list of customizable fields is extracted (for example,
{"ID": 27}
). Template identifiers can be obtained using the
crm.requisite.preset.list
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
'{"preset":{"ID":27}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.field.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"preset":{"ID":27},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.field.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.requisite.preset.field.list'
,
{
preset
: {
"ID"
:
27
}
}
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
'crm.requisite.preset.field.list'
, {
preset
: {
"ID"
:
27
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.preset.field.list'
, {
preset
: {
"ID"
:
27
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
'crm.requisite.preset.field.list'
,
[
'preset'
=> [
'ID'
=>
27
]
}
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
'Error fetching preset field list: '
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
"crm.requisite.preset.field.list"
,
{
preset
:
{
"ID"
:
27
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
'crm.requisite.preset.field.list'
,
[
'preset'
=> [
'ID'
=>
27
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
[
{
"ID"
:
1
,
"FIELD_NAME"
:
"RQ_INN"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"Y"
,
"SORT"
:
510
}
,
{
"ID"
:
2
,
"FIELD_NAME"
:
"RQ_COMPANY_NAME"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"Y"
,
"SORT"
:
520
}
,
{
"ID"
:
3
,
"FIELD_NAME"
:
"RQ_COMPANY_FULL_NAME"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
530
}
,
{
"ID"
:
4
,
"FIELD_NAME"
:
"RQ_OGRN"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
540
}
,
{
"ID"
:
5
,
"FIELD_NAME"
:
"RQ_KPP"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"Y"
,
"SORT"
:
550
}
,
{
"ID"
:
6
,
"FIELD_NAME"
:
"RQ_COMPANY_REG_DATE"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
560
}
,
{
"ID"
:
7
,
"FIELD_NAME"
:
"RQ_OKPO"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
570
}
,
{
"ID"
:
8
,
"FIELD_NAME"
:
"RQ_OKTMO"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
580
}
,
{
"ID"
:
9
,
"FIELD_NAME"
:
"RQ_DIRECTOR"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
590
}
,
{
"ID"
:
10
,
"FIELD_NAME"
:
"RQ_ACCOUNTANT"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
600
}
,
{
"ID"
:
11
,
"FIELD_NAME"
:
"RQ_ADDR"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
610
}
,
{
"ID"
:
12
,
"FIELD_NAME"
:
"RQ_SIGNATURE"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
620
}
,
{
"ID"
:
13
,
"FIELD_NAME"
:
"RQ_STAMP"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"N"
,
"SORT"
:
630
}
,
{
"ID"
:
14
,
"FIELD_NAME"
:
"UF_CRM_1703689889"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"Y"
,
"SORT"
:
640
}
,
{
"ID"
:
15
,
"FIELD_NAME"
:
"UF_CRM_1703690003"
,
"FIELD_TITLE"
:
""
,
"IN_SHORT_LIST"
:
"Y"
,
"SORT"
:
650
}
]
,
"time"
:
{
"start"
:
1716895759.934609
,
"finish"
:
1716895760.407579
,
"duration"
:
0.47297000885009766
,
"processing"
:
0.023286104202270508
,
"date_start"
:
"2024-05-28T13:29:19+02:00"
,
"date_finish"
:
"2024-05-28T13:29:20+02:00"
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
An array of objects describing the customizable fields of the requisites template. Each element contains
fields
of the customizable field template
total
integer
The total number of records found
time
time
Information about the execution time of the request
Fields Describing the Customizable Field of the Requisites Template
Fields Describing the Customizable Field of the Requisites Template
Name
type
Description
ID
integer
The identifier of the field. Created automatically and unique within the template
FIELD_NAME
string
The name of the field
FIELD_TITLE
string
An alternative name for the field for the requisite.
The alternative name is displayed in various forms for filling out requisites. Depending on the specific form, the alternative name may or may not be used
SORT
integer
Sorting. The order in the list of template fields
IN_SHORT_LIST
char
Show in the short list. Deprecated field, currently not used. Retained for backward compatibility. Can take values
Y
or
N
Error Handling
Error Handling
HTTP Status:
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
"The Preset with ID '27' is not found"
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
The Preset with ID '27' is not found
The template with the specified identifier was not found
Access denied
Insufficient access permissions to retrieve the list of customizable fields of the template
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
Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add
Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update
Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd
Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get
Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete
Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields
Copied
Was the article helpful?
Yes
No
Previous
Get Custom Field of Requisite Template by ID
Next
Remove Custom Field from Requisite Template

---

## Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/fields/crm-requisite-preset-field-delete

Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete
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
This method deletes a custom field from the requisite template.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the custom field to be deleted.
Identifiers of custom fields in the requisite template can be obtained using the
crm.requisite.preset.field.list
method.
preset
*
object
An object containing the identifier of the template from which the custom field is being deleted (for example,
{"ID": 27}
).
Template identifiers can be obtained using the
crm.requisite.preset.list
method.
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
'{"ID":27,"preset":{"ID":1}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.field.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":27,"preset":{"ID":1},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.field.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.preset.field.delete"
,
{
ID
:
27
,
preset
:
{
"ID"
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
'crm.requisite.preset.field.delete'
,
[
'ID'
=>
27
,
'preset'
=> [
'ID'
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
'Error deleting preset field: '
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
"crm.requisite.preset.field.delete"
,
{
ID
:
27
,
// Identifier of the custom field to be deleted from the template
preset
:
{
"ID"
:
1
// Identifier of the requisite template
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
'crm.requisite.preset.field.delete'
,
[
'ID'
=>
27
,
'preset'
=> [
'ID'
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
1716819592.314096
,
"finish"
:
1716819592.798008
,
"duration"
:
0.48391199111938477
,
"processing"
:
0.06737184524536133
,
"date_start"
:
"2024-05-27T16:19:52+02:00"
,
"date_finish"
:
"2024-05-27T16:19:52+02:00"
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
Result of deleting the custom field from the template:
true
— deleted
false
— not deleted
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
"The PresetField with ID '27' is not found"
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
The PresetField with ID '27' is not found
The field with the specified identifier was not found.
The Preset with ID '1' is not found
The template with the specified identifier was not found.
ID is not defined or invalid
The template identifier is not specified or has an invalid value.
Access denied
Insufficient access permissions to delete the field from the requisite template.
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
Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add
Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update
Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd
Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get
Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list
Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of All Custom Fields of a Given Requisite Template
Next
Get Description of Custom Fields of Requisite Template

---

## Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/presets/fields/crm-requisite-preset-field-fields

Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Description of Custom Fields for the Requisite Template crm.requisite.preset.field.fields
Code Examples
Response Handling
Returned Data
Description of Fields Describing the Customizable Field of the Requisite Template
Description of Attributes
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method returns a formal description of the fields that describe the customizable field of the requisite template.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.preset.field.fields
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
https://**put_your_bitrix24_address**/rest/crm.requisite.preset.field.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.preset.field.fields'
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
'crm.requisite.preset.field.fields'
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
'Error fetching preset field fields: '
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
"crm.requisite.preset.field.fields"
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
'crm.requisite.preset.field.fields'
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
"FIELD_NAME"
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
"Name"
}
,
"FIELD_TITLE"
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
"Title in Template"
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
"Sorting"
}
,
"IN_SHORT_LIST"
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
"Show in Short List"
}
}
,
"time"
:
{
"start"
:
1716823643.597269
,
"finish"
:
1716823643.949143
,
"duration"
:
0.35187387466430664
,
"processing"
:
0.012942075729370117
,
"date_start"
:
"2024-05-27T17:27:23+02:00"
,
"date_finish"
:
"2024-05-27T17:27:23+02:00"
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
An object in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field
is the field identifier, and
value
is the object with
field attributes
time
time
Information about the request execution time
Description of Fields Describing the Customizable Field of the Requisite Template
Description of Fields Describing the Customizable Field of the Requisite Template
Title
type
Description
ID
integer
Field identifier. Created automatically and unique within the template
FIELD_NAME
string
Field name
FIELD_TITLE
string
Alternative field name for the requisite.
The alternative name is displayed in various forms for filling out requisites. Depending on the specific form, the alternative name may or may not be used
SORT
integer
Sorting. Order in the list of template fields
IN_SHORT_LIST
char
Show in short list. Deprecated field, currently not used. Retained for backward compatibility. Can take values
Y
or
N
Description of Attributes
Description of Attributes
Title
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
Add a Custom Field to the CRM Requisite Template crm.requisite.preset.field.add
Update Custom Field of a Given Requisite Template crm.requisite.preset.field.update
Get Fields Available for Addition to the Requisite Template crm.requisite.preset.field.availabletoadd
Get Custom Field of Requisite Template by ID crm.requisite.preset.field.get
Get a list of all customizable fields for a specified CRM requisites template crm.requisite.preset.field.list
Delete Custom Field from CRM Requisite Template crm.requisite.preset.field.delete
Copied
Was the article helpful?
Yes
No
Previous
Remove Custom Field from Requisite Template
Next
Overview of methods

---

## About Bank Details

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/bank-detail/index

About Bank Details | Bitrix24 REST API and Marketplace Applications
About Bank Details
About Bank Details
Scope:
crm
Who can perform methods: any user
Bank details are a strict sequence of numbers required for conducting operations with a bank account. They can be used to send a cashless payment or deposit money into the account through the cashier.
The mandatory bank details include:
account number
correspondent account number
bank identification code (BIC) and full name of the bank
In CRM, bank details are linked to the universal details object. Multiple bank details can be associated with a single detail.
Fields of Bank Details
Name
type
Description
Read
Write
Required
Immutable
ID
integer
Identifier of the bank detail. Created automatically and unique within the account
Yes
No
No
No
ENTITY_ID
integer
Identifier of the parent object. Currently, it can only be the identifier of the detail.
Identifiers of details can be obtained using the method
crm.requisite.list
Yes
Yes
Yes
Yes
COUNTRY_ID
integer
Identifier of the country corresponding to the set of bank detail fields (see method
crm.requisite.preset.countries
for available values).
The country code of the bank detail matches the country code in the linked detail template, the identifier of which is specified in the
ENTITY_ID
field
Yes
Yes
No
No
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
Identifier of the user who created the detail
Yes
No
No
No
MODIFY_BY_ID
user
Identifier of the user who modified the detail
Yes
No
No
No
NAME
*
string
Name of the bank detail
Yes
Yes
No
No
CODE
string
Symbolic code of the detail
Yes
Yes
No
No
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information base.
The purpose of the field may change by the final developer. Each application ensures the uniqueness of values in this field.
It is recommended to use a unique prefix to avoid collisions with other applications
Yes
Yes
No
No
ACTIVE
char
Activity status. Values
Y
or
N
are used.
Currently, the field does not actually affect anything
Yes
Yes
No
No
SORT
integer
Sorting
Yes
Yes
No
No
RQ_BANK_NAME
string
Name of the bank
Yes
Yes
No
No
RQ_BANK_ADDR
string
Address of the bank
Yes
Yes
No
No
RQ_BANK_CODE
string
Bank Code (for country BR)
Yes
Yes
No
No
RQ_BANK_ROUTE_NUM
string
Bank Routing Number
Yes
Yes
No
No
RQ_BIK
string
BIC
Yes
Yes
No
No
RQ_CODEB
string
Code Banque (for country FR)
Yes
Yes
No
No
RQ_CODEG
string
Code Guichet (for country FR)
Yes
Yes
No
No
RQ_RIB
string
Clé RIB (for country FR)
Yes
Yes
No
No
RQ_MFO
string
MFO
Yes
Yes
No
No
RQ_ACC_NAME
string
Bank Account Holder Name
Yes
Yes
No
No
RQ_ACC_NUM
string
Bank Account Number
Yes
Yes
No
No
RQ_ACC_TYPE
string
Tipo da conta (for country BR)
Yes
Yes
No
No
RQ_AGENCY_NAME
string
Agência (for country BR)
Yes
Yes
No
No
RQ_IIK
string
IIK
Yes
Yes
No
No
RQ_ACC_CURRENCY
string
Currency of the account
Yes
Yes
No
No
RQ_COR_ACC_NUM
string
Correspondent account
Yes
Yes
No
No
RQ_IBAN
string
IBAN
Yes
Yes
No
No
RQ_SWIFT
string
SWIFT
Yes
Yes
No
No
RQ_BIC
string
BIC
Yes
Yes
No
No
COMMENTS
string
Comment
Yes
Yes
No
No
ORIGINATOR_ID
string
Identifier of the external information base. The purpose of the field may change by the final developer
Yes
Yes
No
No
Overview of Methods
Overview of Methods
Method
Description
crm.requisite.bankdetail.add
Creates a new bank detail
crm.requisite.bankdetail.update
Modifies an existing bank detail
crm.requisite.bankdetail.get
Returns the bank detail by identifier
crm.requisite.bankdetail.list
Returns a list of bank details by filter
crm.requisite.bankdetail.delete
Deletes a bank detail
crm.requisite.bankdetail.fields
Returns a formal description of bank detail fields
Copied
Was the article helpful?
Yes
No
Previous
Get detail fields
Next
Create New Bank Detail

---

## Create a new bank detail crm.requisite.bankdetail.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/bank-detail/crm-requisite-bank-detail-add

Create a new bank detail crm.requisite.bankdetail.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create a new bank detail crm.requisite.bankdetail.add
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
This method creates a new bank detail.
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
for adding a bank detail
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
ENTITY_ID
*
integer
Identifier of the parent object. Currently, it can only be the identifier of the detail. Identifiers of details can be obtained using the method
crm.requisite.list
COUNTRY_ID
integer
Identifier of the country corresponding to the set of bank detail fields (see the method
crm.requisite.preset.countries
for available values).
The country code of the bank detail matches the country code in the linked detail template, the identifier of which is specified in the
ENTITY_ID
field
NAME
*
string
Name of the bank detail
CODE
string
Symbolic code of the detail
XML_ID
string
External key. Used for exchange operations. Identifier of the external information base object.
The purpose of the field may change by the final developer. Each application ensures the uniqueness of values in this field.
It is recommended to use a unique prefix to avoid collisions with other applications
ACTIVE
char
Activity status. Values
Y
or
N
are used.
Currently, the field does not actually affect anything
SORT
integer
Sorting
RQ_BANK_NAME
string
Bank name
RQ_BANK_ADDR
string
Bank address
RQ_BANK_CODE
string
Bank code (for country BR)
RQ_BANK_ROUTE_NUM
string
Bank Routing Number
RQ_BIK
string
BIK
RQ_CODEB
string
Code Banque (for country FR)
RQ_CODEG
string
Code Guichet (for country FR)
RQ_RIB
string
Clé RIB (for country FR)
RQ_MFO
string
MFO
RQ_ACC_NAME
string
Bank Account Holder Name
RQ_ACC_NUM
string
Bank Account Number
RQ_ACC_TYPE
string
Tipo da conta (for country BR)
RQ_AGENCY_NAME
string
Agência (for country BR)
RQ_IIK
string
IIK
RQ_ACC_CURRENCY
string
Account currency
RQ_COR_ACC_NUM
string
Correspondent account
RQ_IBAN
string
IBAN
RQ_SWIFT
string
SWIFT
RQ_BIC
string
BIC
COMMENTS
string
Comment
ORIGINATOR_ID
string
Identifier of the external information base. The purpose of the field may change by the final developer
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
'{"fields":{"ENTITY_ID":27,"COUNTRY_ID":1,"NAME":"Superbank","RQ_BANK_NAME":"Ltd. Superbank","RQ_BANK_ADDR":"117312, New York, 19 Vavilova St.","RQ_BIK":"044525225","RQ_ACC_NUM":"40702810938000060473","RQ_ACC_CURRENCY":"USD","RQ_COR_ACC_NUM":"30101810400000000225","XML_ID":"1e4641fd-2dd9-31e6-b2f2-105056c00008","ACTIVE":"Y","SORT":600}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.bankdetail.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"ENTITY_ID":27,"COUNTRY_ID":1,"NAME":"Superbank","RQ_BANK_NAME":"Ltd. Superbank","RQ_BANK_ADDR":"117312, New York, 19 Vavilova St.","RQ_BIK":"044525225","RQ_ACC_NUM":"40702810938000060473","RQ_ACC_CURRENCY":"USD","RQ_COR_ACC_NUM":"30101810400000000225","XML_ID":"1e4641fd-2dd9-31e6-b2f2-105056c00008","ACTIVE":"Y","SORT":600},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.bankdetail.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.bankdetail.add"
,
{
fields
:
{
"ENTITY_ID"
:
27
,
// Identifier of the detail
"COUNTRY_ID"
:
1
,
// Country code (USA)
"NAME"
:
"Superbank"
,
// Name of the bank detail
"RQ_BANK_NAME"
:
"Ltd. Superbank"
,
// Bank name
"RQ_BANK_ADDR"
:
"117312, New York, 19 Vavilova St."
,
"RQ_BIK"
:
"044525225"
,
"RQ_ACC_NUM"
:
"40702810938000060473"
,
"RQ_ACC_CURRENCY"
:
"USD"
,
"RQ_COR_ACC_NUM"
:
"30101810400000000225"
,
"XML_ID"
:
"1e4641fd-2dd9-31e6-b2f2-105056c00008"
,
"ACTIVE"
:
"Y"
,
"SORT"
:
600
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
"Created bank detail with ID "
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
'crm.requisite.bankdetail.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
27
,
'COUNTRY_ID'
=>
1
,
'NAME'
=>
'Superbank'
,
'RQ_BANK_NAME'
=>
'Ltd. Superbank'
,
'RQ_BANK_ADDR'
=>
'117312, New York, 19 Vavilova St.'
,
'RQ_BIK'
=>
'044525225'
,
'RQ_ACC_NUM'
=>
'40702810938000060473'
,
'RQ_ACC_CURRENCY'
=>
'USD'
,
'RQ_COR_ACC_NUM'
=>
'30101810400000000225'
,
'XML_ID'
=>
'1e4641fd-2dd9-31e6-b2f2-105056c00008'
,
'ACTIVE'
=>
'Y'
,
'SORT'
=>
600
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
'Created bank detail with ID '
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
'Error creating bank detail: '
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
"crm.requisite.bankdetail.add"
,
{
fields
:
{
"ENTITY_ID"
:
27
,
// Identifier of the detail
"COUNTRY_ID"
:
1
,
// Country code (USA)
"NAME"
:
"Superbank"
,
// Name of the bank detail
"RQ_BANK_NAME"
:
"Ltd. Superbank"
,
// Bank name
"RQ_BANK_ADDR"
:
"117312, New York, 19 Vavilova St."
,
"RQ_BIK"
:
"044525225"
,
"RQ_ACC_NUM"
:
"40702810938000060473"
,
"RQ_ACC_CURRENCY"
:
"USD"
,
"RQ_COR_ACC_NUM"
:
"30101810400000000225"
,
"XML_ID"
:
"1e4641fd-2dd9-31e6-b2f2-105056c00008"
,
"ACTIVE"
:
"Y"
,
"SORT"
:
600
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
"Created bank detail with ID "
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
'crm.requisite.bankdetail.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
27
,
'COUNTRY_ID'
=>
1
,
'NAME'
=>
'Superbank'
,
'RQ_BANK_NAME'
=>
'Ltd. Superbank'
,
'RQ_BANK_ADDR'
=>
'117312, New York, 19 Vavilova St.'
,
'RQ_BIK'
=>
'044525225'
,
'RQ_ACC_NUM'
=>
'40702810938000060473'
,
'RQ_ACC_CURRENCY'
=>
'USD'
,
'RQ_COR_ACC_NUM'
=>
'30101810400000000225'
,
'XML_ID'
=>
'1e4641fd-2dd9-31e6-b2f2-105056c00008'
,
'ACTIVE'
=>
'Y'
,
'SORT'
=>
600
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
357
,
"time"
:
{
"start"
:
1717429942.060649
,
"finish"
:
1717429942.626925
,
"duration"
:
0.5662760734558105
,
"processing"
:
0.09111285209655762
,
"date_start"
:
"2024-06-03T17:52:22+02:00"
,
"date_finish"
:
"2024-06-03T17:52:22+02:00"
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
Identifier of the created bank detail
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
Possible Errors
Possible Errors
Error Text
Description
ENTITY_ID is not defined or invalid
The identifier of the detail is not defined or has an invalid value
Access denied
Insufficient access permissions to add a bank detail
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
Update Bank Details crm.requisite.bankdetail.update
Get bank details by id crm.requisite.bankdetail.get
Get a list of bank details by filter crm.requisite.bankdetail.list
Delete bank detail crm.requisite.bankdetail.delete
Get Description of Bank Details Fields crm.requisite.bankdetail.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Bank Detail

---

## Update Bank Details crm.requisite.bankdetail.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/bank-detail/crm-requisite-bank-detail-update

Update Bank Details crm.requisite.bankdetail.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Bank Details crm.requisite.bankdetail.update
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
This method updates an existing bank detail.
Method Parameters
Method Parameters
Required parameters are marked with *
Parameter
Description
id
*
integer
Identifier of the bank detail.
Bank detail identifiers can be obtained using the
crm.requisite.bankdetail.list
method.
fields
*
object
Set of bank detail fields — an object of the form
{"field": "value"[, ...]}
, the values of which need to be changed.
Parameter fields
Parameter fields
Name
type
Description
NAME
string
Name of the bank detail.
CODE
string
Symbolic code of the detail.
XML_ID
string
External key. Used for exchange operations. Identifier of the external information base object.
The purpose of the field may change by the final developer. Each application ensures the uniqueness of values in this field.
It is recommended to use a unique prefix to avoid collisions with other applications.
ACTIVE
char
Activity status. Values
Y
or
N
are used.
Currently, this field does not affect anything.
SORT
integer
Sorting.
RQ_BANK_NAME
string
Name of the bank.
RQ_BANK_ADDR
string
Address of the bank.
RQ_BANK_CODE
string
Bank Code (for country BR).
RQ_BANK_ROUTE_NUM
string
Bank Routing Number.
RQ_BIK
string
BIK.
RQ_CODEB
string
Code Banque (for country FR).
RQ_CODEG
string
Code Guichet (for country FR).
RQ_RIB
string
Clé RIB (for country FR).
RQ_MFO
string
MFO.
RQ_ACC_NAME
string
Bank Account Holder Name.
RQ_ACC_NUM
string
Bank Account Number.
RQ_ACC_TYPE
string
Tipo da conta (for country BR).
RQ_AGENCY_NAME
string
Agência (for country BR).
RQ_IIK
string
IIK.
RQ_ACC_CURRENCY
string
Account Currency.
RQ_COR_ACC_NUM
string
Correspondent Account Number.
RQ_IBAN
string
IBAN.
RQ_SWIFT
string
SWIFT.
RQ_BIC
string
BIC.
COMMENTS
string
Comment.
ORIGINATOR_ID
string
Identifier of the external information base. The purpose of the field may change by the final developer.
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
'{"id":357,"fields":{"NAME":"Superbank Ltd. (do not use)","COMMENTS":"Outdated","SORT":10000,"ACTIVE":"N"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.bankdetail.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":357,"fields":{"NAME":"Superbank Ltd. (do not use)","COMMENTS":"Outdated","SORT":10000,"ACTIVE":"N"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.bankdetail.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.requisite.bankdetail.update"
,
{
id
:
357
,
fields
:
{
"NAME"
:
"Superbank Ltd. (do not use)"
,
"COMMENTS"
:
"Outdated"
,
"SORT"
:
10000
,
"ACTIVE"
:
"N"
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
'crm.requisite.bankdetail.update'
,
[
'id'
=>
357
,
'fields'
=> [
'NAME'
=>
'Superbank Ltd. (do not use)'
,
'COMMENTS'
=>
'Outdated'
,
'SORT'
=>
10000
,
'ACTIVE'
=>
'N'
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
'Error updating bank detail: '
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
"crm.requisite.bankdetail.update"
,
{
id
:
357
,
fields
:
{
"NAME"
:
"Superbank Ltd. (do not use)"
,
"COMMENTS"
:
"Outdated"
,
"SORT"
:
10000
,
"ACTIVE"
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
'crm.requisite.bankdetail.update'
,
[
'id'
=>
357
,
'fields'
=> [
'NAME'
=>
'Superbank Ltd. (do not use)'
,
'COMMENTS'
=>
'Outdated'
,
'SORT'
=>
10000
,
'ACTIVE'
=>
'N'
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
1717509116.239588
,
"finish"
:
1717509116.78087
,
"duration"
:
0.5412819385528564
,
"processing"
:
0.173170804977417
,
"date_start"
:
"2024-06-04T15:51:56+02:00"
,
"date_finish"
:
"2024-06-04T15:51:56+02:00"
,
"operating"
:
0.17314410209655762
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of updating the bank detail:
true — updated
false — not updated
time
time
Information about the request execution time.
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
"The RequisiteBankDetail with ID '357' is not found."
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
The identifier of the bank detail is not specified or has an invalid value.
The Requisite with ID '357' is not found
The bank detail with the specified identifier was not found.
Access denied
Insufficient access permissions to update the bank detail.
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
Create a new bank detail crm.requisite.bankdetail.add
Get bank details by id crm.requisite.bankdetail.get
Get a list of bank details by filter crm.requisite.bankdetail.list
Delete bank detail crm.requisite.bankdetail.delete
Get Description of Bank Details Fields crm.requisite.bankdetail.fields
Copied
Was the article helpful?
Yes
No
Previous
Create New Bank Detail
Next
Get Bank Detail by ID

---

## Get bank details by id crm.requisite.bankdetail.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/bank-detail/crm-requisite-bank-detail-get

Get bank details by id crm.requisite.bankdetail.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get bank details by id crm.requisite.bankdetail.get
Method Parameters
Code Examples
Response Handling
Returned Data
Description of Bank Details Fields
Error Handling
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns bank details by identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the bank details.
Identifiers of bank details can be obtained using the method
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
'{"id":357}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.bankdetail.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":357,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.bankdetail.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.bankdetail.get'
,
{
id
:
357
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
'crm.requisite.bankdetail.get'
,
[
'id'
=>
357
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
'Error getting bank detail: '
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
"crm.requisite.bankdetail.get"
,
{
id
:
357
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
'crm.requisite.bankdetail.get'
,
[
'id'
=>
357
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
"357"
,
"ENTITY_ID"
:
"27"
,
"COUNTRY_ID"
:
"1"
,
"DATE_CREATE"
:
"2024-06-03T17:52:22+02:00"
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
"Ltd. Superbank"
,
"CODE"
:
null
,
"XML_ID"
:
"1e4641fd-2dd9-31e6-b2f2-105056c00008"
,
"ORIGINATOR_ID"
:
null
,
"ACTIVE"
:
"Y"
,
"SORT"
:
"600"
,
"RQ_BANK_NAME"
:
"Ltd. Superbank"
,
"RQ_BANK_CODE"
:
null
,
"RQ_BANK_ADDR"
:
"117312, New York, Vavilova Street, House 19"
,
"RQ_BANK_ROUTE_NUM"
:
null
,
"RQ_BIK"
:
"044525225"
,
"RQ_MFO"
:
null
,
"RQ_ACC_NAME"
:
null
,
"RQ_ACC_NUM"
:
"40702810938000060473"
,
"RQ_ACC_TYPE"
:
null
,
"RQ_IIK"
:
null
,
"RQ_ACC_CURRENCY"
:
"USD"
,
"RQ_COR_ACC_NUM"
:
"30101810400000000225"
,
"RQ_IBAN"
:
null
,
"RQ_SWIFT"
:
null
,
"RQ_BIC"
:
null
,
"RQ_CODEB"
:
null
,
"RQ_CODEG"
:
null
,
"RQ_RIB"
:
null
,
"RQ_AGENCY_NAME"
:
null
,
"COMMENTS"
:
null
}
,
"time"
:
{
"start"
:
1717495619.077607
,
"finish"
:
1717495619.708617
,
"duration"
:
0.6310100555419922
,
"processing"
:
0.07691788673400879
,
"date_start"
:
"2024-06-04T12:06:59+02:00"
,
"date_finish"
:
"2024-06-04T12:06:59+02:00"
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
Object containing the values of the bank details fields
time
time
Information about the request execution time
Description of Bank Details Fields
Description of Bank Details Fields
Name
type
Description
ID
integer
Identifier of the bank details. Automatically created and unique within the account
ENTITY_TYPE_ID
integer
Identifier of the parent object's type. Can only be
Requisite
(value
8
).
Identifiers of object types are returned by the method
crm.enum.ownertype
ENTITY_ID
integer
Identifier of the parent object. Currently can only be the identifier of the requisite.
Identifiers of requisites can be obtained using the method
crm.requisite.list
COUNTRY_ID
integer
Identifier of the country corresponding to the set of bank details fields (see method
crm.requisite.preset.countries
for available values).
The country code of the bank details matches the country code in the linked requisite template, the identifier of which is specified in the
ENTITY_ID
field
DATE_CREATE
datetime
Creation date
DATE_MODIFY
datetime
Modification date
CREATED_BY_ID
user
Identifier of the user who created the requisite
MODIFY_BY_ID
user
Identifier of the user who modified the requisite
NAME
*
string
Name of the bank details
CODE
string
Symbolic code of the requisite
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information base.
The purpose of the field may change by the final developer. Each application ensures the uniqueness of values in this field.
It is recommended to use a unique prefix to avoid collisions with other applications
ACTIVE
char
Activity indicator. Uses values
Y
or
N
.
Currently, the field does not actually affect anything
SORT
integer
Sorting
RQ_BANK_NAME
string
Name of the bank
RQ_BANK_ADDR
string
Address of the bank
RQ_BANK_CODE
string
Bank Code (for country BR)
RQ_BANK_ROUTE_NUM
string
Bank Routing Number
RQ_BIK
string
BIK
RQ_CODEB
string
Code Banque (for country FR)
RQ_CODEG
string
Code Guichet (for country FR)
RQ_RIB
string
Clé RIB (for country FR)
RQ_MFO
string
MFO
RQ_ACC_NAME
string
Bank Account Holder Name
RQ_ACC_NUM
string
Bank Account Number
RQ_ACC_TYPE
string
Tipo da conta (for country BR)
RQ_AGENCY_NAME
string
Agência (for country BR)
RQ_IIK
string
IIK
RQ_ACC_CURRENCY
string
Currency of the account
RQ_COR_ACC_NUM
string
Correspondent account
RQ_IBAN
string
IBAN
RQ_SWIFT
string
SWIFT
RQ_BIC
string
BIC
COMMENTS
string
Comment
ORIGINATOR_ID
string
Identifier of the external information base. The purpose of the field may change by the final developer
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
"The RequisiteBankDetail with ID '357' is not found"
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
The identifier of the bank details is not defined or has an invalid value
The RequisiteBankDetail with ID '357' is not found
The bank details with the specified identifier were not found
Access denied
Insufficient access permissions to retrieve bank details
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
Create a new bank detail crm.requisite.bankdetail.add
Update Bank Details crm.requisite.bankdetail.update
Get a list of bank details by filter crm.requisite.bankdetail.list
Delete bank detail crm.requisite.bankdetail.delete
Get Description of Bank Details Fields crm.requisite.bankdetail.fields
Copied
Was the article helpful?
Yes
No
Previous
Update Bank Detail
Next
Get List of Bank Details by Filter

---

## Get a list of bank details by filter crm.requisite.bankdetail.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/bank-detail/crm-requisite-bank-detail-list

Get a list of bank details by filter crm.requisite.bankdetail.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of bank details by filter crm.requisite.bankdetail.list
Method Parameters
Description of Bank Detail Fields
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
The method returns a list of bank details based on the filter.
Method Parameters
Method Parameters
Name
type
Description
select
array
The array contains a list of fields to select (see
bank detail fields
).
If the array is not provided or an empty array is passed, all available bank detail fields will be selected.
filter
object
An object for filtering the selected bank details in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
correspond to
bank detail fields
.
An additional prefix can be assigned to the key to specify the filter behavior. Possible prefix values:
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
symbol does not need to be passed in the filter value. The search looks for the substring in any position of the string.
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
!%
— NOT LIKE, substring search. The
%
symbol does not need to be passed in the filter value. The search goes from both sides.
!=%
— NOT LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
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
An object for sorting the selected bank details in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
correspond to
bank detail fields
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
The parameter is used for managing pagination.
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
— the number of the desired page
Description of Bank Detail Fields
Description of Bank Detail Fields
Name
type
Description
ID
integer
Identifier of the bank detail. Automatically created and unique within the account.
ENTITY_ID
integer
Identifier of the parent object. Currently, it can only be the identifier of the detail.
Identifiers of details can be obtained using the method
crm.requisite.list
.
COUNTRY_ID
integer
Identifier of the country corresponding to the set of bank detail fields (see the method
crm.requisite.preset.countries
for available values).
The country code of the bank detail matches the country code in the linked detail template, the identifier of which is specified in the
ENTITY_ID
field.
DATE_CREATE
datetime
Creation date.
DATE_MODIFY
datetime
Modification date.
CREATED_BY_ID
user
Identifier of the user who created the detail.
MODIFY_BY_ID
user
Identifier of the user who modified the detail.
NAME
string
Name of the bank detail.
CODE
string
Symbolic code of the detail.
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information base.
The purpose of the field may change by the final developer. Each application ensures the uniqueness of values in this field.
It is recommended to use a unique prefix to avoid collisions with other applications.
ACTIVE
char
Activity indicator. Values
Y
or
N
are used.
Currently, the field does not actually affect anything.
SORT
integer
Sorting.
RQ_BANK_NAME
string
Name of the bank.
RQ_BANK_ADDR
string
Address of the bank.
RQ_BANK_CODE
string
Bank Code (for country BR).
RQ_BANK_ROUTE_NUM
string
Bank Routing Number.
RQ_BIK
string
BIK.
RQ_CODEB
string
Code Banque (for country FR).
RQ_CODEG
string
Code Guichet (for country FR).
RQ_RIB
string
Clé RIB (for country FR).
RQ_MFO
string
MFO.
RQ_ACC_NAME
string
Bank Account Holder Name.
RQ_ACC_NUM
string
Bank Account Number.
RQ_ACC_TYPE
string
Tipo da conta (for country BR).
RQ_AGENCY_NAME
string
Agência (for country BR).
RQ_IIK
string
IIK.
RQ_ACC_CURRENCY
string
Account Currency.
RQ_COR_ACC_NUM
string
Correspondent Account Number.
RQ_IBAN
string
IBAN.
RQ_SWIFT
string
SWIFT.
RQ_BIC
string
BIC.
COMMENTS
string
Comment.
ORIGINATOR_ID
string
Identifier of the external information base. The purpose of the field may change by the final developer.
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
'{"order":{"DATE_CREATE":"ASC"},"filter":{"COUNTRY_ID":"1"},"select":["ENTITY_ID","ID","NAME"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.bankdetail.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"DATE_CREATE":"ASC"},"filter":{"COUNTRY_ID":"1"},"select":["ENTITY_ID","ID","NAME"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.bankdetail.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.requisite.bankdetail.list'
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
"COUNTRY_ID"
:
"1"
},
select
: [
"ENTITY_ID"
,
"ID"
,
"NAME"
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
'crm.requisite.bankdetail.list'
, {
order
: {
"DATE_CREATE"
:
"ASC"
},
filter
: {
"COUNTRY_ID"
:
"1"
},
select
: [
"ENTITY_ID"
,
"ID"
,
"NAME"
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.bankdetail.list'
, {
order
: {
"DATE_CREATE"
:
"ASC"
},
filter
: {
"COUNTRY_ID"
:
"1"
},
select
: [
"ENTITY_ID"
,
"ID"
,
"NAME"
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
'crm.requisite.bankdetail.list'
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
'COUNTRY_ID'
=>
'1'
],
'select'
=> [
'ENTITY_ID'
,
'ID'
,
'NAME'
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
'Error listing bank details: '
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
"crm.requisite.bankdetail.list"
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
"COUNTRY_ID"
:
"1"
},
select
: [
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
'crm.requisite.bankdetail.list'
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
'COUNTRY_ID'
=>
'1'
],
'select'
=> [
'ENTITY_ID'
,
'ID'
,
'NAME'
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
[
{
"ENTITY_ID"
:
"27"
,
"ID"
:
"11"
,
"NAME"
:
"Tinkoff"
}
,
{
"ENTITY_ID"
:
"30"
,
"ID"
:
"15"
,
"NAME"
:
"ALPHA-BANK JSC"
}
,
{
"ENTITY_ID"
:
"30"
,
"ID"
:
"16"
,
"NAME"
:
"Tinkoff Bank JSC"
}
,
{
"ENTITY_ID"
:
"45"
,
"ID"
:
"17"
,
"NAME"
:
"Tinkoff Bank JSC"
}
,
{
"ENTITY_ID"
:
"45"
,
"ID"
:
"18"
,
"NAME"
:
"ALPHA-BANK JSC"
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
1717498684.70562
,
"finish"
:
1717498685.13295
,
"duration"
:
0.42733001708984375
,
"processing"
:
0.020370006561279297
,
"date_start"
:
"2024-06-04T12:58:04+02:00"
,
"date_finish"
:
"2024-06-04T12:58:05+02:00"
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
An array of objects with information from the selected bank details. Each element contains the selected
bank detail fields
.
total
integer
Total number of records found.
time
time
Information about the execution time of the request.
Error Handling
Error Handling
HTTP Status:
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
Insufficient access permissions to retrieve the list of bank details.
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
Create a new bank detail crm.requisite.bankdetail.add
Update Bank Details crm.requisite.bankdetail.update
Get bank details by id crm.requisite.bankdetail.get
Delete bank detail crm.requisite.bankdetail.delete
Get Description of Bank Details Fields crm.requisite.bankdetail.fields
Copied
Was the article helpful?
Yes
No
Previous
Get Bank Detail by ID
Next
Delete Bank Detail

---

## Delete bank detail crm.requisite.bankdetail.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/bank-detail/crm-requisite-bank-detail-delete

Delete bank detail crm.requisite.bankdetail.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete bank detail crm.requisite.bankdetail.delete
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
This method deletes a bank detail.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the bank detail. Bank detail identifiers can be obtained using the method
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
'{"id":357}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.bankdetail.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":357,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.requisite.bankdetail.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.bankdetail.delete'
,
{
id
:
357
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
'crm.requisite.bankdetail.delete'
,
[
'id'
=>
357
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
'Error deleting bank detail: '
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
"crm.requisite.bankdetail.delete"
,
{
id
:
357
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
'crm.requisite.bankdetail.delete'
,
[
'id'
=>
357
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
1716554949.294631
,
"finish"
:
1716554949.795059
,
"duration"
:
0.5004279613494873
,
"processing"
:
0.057311058044433594
,
"date_start"
:
"2024-05-24T14:49:09+02:00"
,
"date_finish"
:
"2024-05-24T14:49:09+02:00"
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
Result of deleting the bank detail:
true — deleted
false — not deleted
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
"The RequisiteBankDetail with ID '357' is not found"
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
The identifier of the bank detail is not specified or has an invalid value
The RequisiteBankDetail with ID '357' is not found
The bank detail with the specified identifier was not found
Access denied
Insufficient access permissions to delete the bank detail
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
Create a new bank detail crm.requisite.bankdetail.add
Update Bank Details crm.requisite.bankdetail.update
Get bank details by id crm.requisite.bankdetail.get
Get a list of bank details by filter crm.requisite.bankdetail.list
Get Description of Bank Details Fields crm.requisite.bankdetail.fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of Bank Details by Filter
Next
Get Description of Bank Detail Fields

---

## Get Description of Bank Details Fields crm.requisite.bankdetail.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/bank-detail/crm-requisite-bank-detail-fields

Get Description of Bank Details Fields crm.requisite.bankdetail.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Description of Bank Details Fields crm.requisite.bankdetail.fields
Code Examples
Response Handling
Returned Data
Description of Bank Details Fields
Description of Attributes
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a formal description of the bank details fields.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.requisite.bankdetail.fields
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
https://**put_your_bitrix24_address**/rest/crm.requisite.bankdetail.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.requisite.bankdetail.fields'
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
'crm.requisite.bankdetail.fields'
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
'Error fetching bank detail fields: '
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
"crm.requisite.bankdetail.fields"
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
'crm.requisite.bankdetail.fields'
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
"COUNTRY_ID"
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
"Country ID"
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
"RQ_BANK_NAME"
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
"Bank Name"
}
,
"RQ_BANK_ADDR"
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
"Bank Address"
}
,
"RQ_BANK_CODE"
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
"RQ_BANK_CODE"
}
,
"RQ_AGENCY_NAME"
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
"RQ_AGENCY_NAME"
}
,
"RQ_BANK_ROUTE_NUM"
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
"RQ_BANK_ROUTE_NUM"
}
,
"RQ_BIK"
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
"BIK"
}
,
"RQ_MFO"
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
"RQ_MFO"
}
,
"RQ_ACC_NAME"
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
"RQ_ACC_NAME"
}
,
"RQ_ACC_NUM"
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
"Account Number"
}
,
"RQ_ACC_TYPE"
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
"RQ_ACC_TYPE"
}
,
"RQ_IIK"
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
"RQ_IIK"
}
,
"RQ_ACC_CURRENCY"
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
"Account Currency"
}
,
"RQ_COR_ACC_NUM"
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
"Correspondent Account"
}
,
"RQ_IBAN"
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
"IBAN"
}
,
"RQ_SWIFT"
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
"SWIFT"
}
,
"RQ_BIC"
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
"RQ_BIC"
}
,
"RQ_CODEB"
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
"RQ_CODEB"
}
,
"RQ_CODEG"
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
"RQ_CODEG"
}
,
"RQ_RIB"
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
"RQ_RIB"
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
}
,
"time"
:
{
"start"
:
1717409814.796487
,
"finish"
:
1717409815.225673
,
"duration"
:
0.4291858673095703
,
"processing"
:
0.013273000717163086
,
"date_start"
:
"2024-06-03T12:16:54+02:00"
,
"date_finish"
:
"2024-06-03T12:16:55+02:00"
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
Description of Bank Details Fields
Description of Bank Details Fields
Name
type
Description
ID
integer
Identifier of the bank detail. Created automatically and unique within the account
ENTITY_ID
integer
Identifier of the parent object. Currently, it can only be the identifier of the detail.
Identifiers of details can be obtained using the method
crm.requisite.list
COUNTRY_ID
integer
Identifier of the country corresponding to the set of bank detail fields (see the method
crm.requisite.preset.countries
for available values).
The country code of the bank detail matches the country code in the linked detail template, the identifier of which is specified in the
ENTITY_ID
field
DATE_CREATE
datetime
Creation date
DATE_MODIFY
datetime
Modification date
CREATED_BY_ID
user
Identifier of the user who created the detail
MODIFY_BY_ID
user
Identifier of the user who modified the detail
NAME
string
Name of the bank detail
CODE
string
Symbolic code of the detail
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information base.
The purpose of the field may change by the final developer. Each application ensures the uniqueness of values in this field.
It is recommended to use a unique prefix to avoid collisions with other applications
ACTIVE
char
Activity status. Values
Y
or
N
are used.
Currently, the field does not actually affect anything
SORT
integer
Sorting
RQ_BANK_NAME
string
Name of the bank
RQ_BANK_ADDR
string
Address of the bank
RQ_BANK_CODE
string
Bank Code (for country BR)
RQ_BANK_ROUTE_NUM
string
Bank Routing Number
RQ_BIK
string
BIK
RQ_CODEB
string
Bank Code (for country FR)
RQ_CODEG
string
Branch Code (for country FR)
RQ_RIB
string
RIB Key (for country FR)
RQ_MFO
string
MFO
RQ_ACC_NAME
string
Bank Account Holder Name
RQ_ACC_NUM
string
Bank Account Number
RQ_ACC_TYPE
string
Account Type (for country BR)
RQ_AGENCY_NAME
string
Agency (for country BR)
RQ_IIK
string
IIK
RQ_ACC_CURRENCY
string
Account Currency
RQ_COR_ACC_NUM
string
Correspondent Account
RQ_IBAN
string
IBAN
RQ_SWIFT
string
SWIFT
RQ_BIC
string
BIC
COMMENTS
string
Comment
ORIGINATOR_ID
string
Identifier of the external information base. The purpose of the field may change by the final developer
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
Required attribute. Possible values:
true — yes
false — no
isReadOnly
boolean
Read-only attribute. Possible values:
true — yes
false — no
isImmutable
boolean
Immutable attribute. Possible values:
true — yes
false — no
isMultiple
boolean
Multi-field attribute. Possible values:
true — yes
false — no
isDynamic
boolean
Custom attribute. Possible values:
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
Create a new bank detail crm.requisite.bankdetail.add
Update Bank Details crm.requisite.bankdetail.update
Get bank details by id crm.requisite.bankdetail.get
Get a list of bank details by filter crm.requisite.bankdetail.list
Delete bank detail crm.requisite.bankdetail.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete Bank Detail
Next
Overview of Methods

---

## Overview of Events

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/index

Overview of Events | Bitrix24 REST API and Marketplace Applications
Overview of Events
Overview of Events
Scope:
crm
Who can subscribe:
any user
Event
Triggered
onCrmAddressRegister
When an address is registered
onCrmAddressUnregister
When an address is removed
onCrmRequisiteAdd
When a requisite is added
onCrmRequisiteUpdate
When a requisite is updated
onCrmRequisiteDelete
When a requisite is deleted
onCrmRequisiteUserFieldAdd
When a user field is added
onCrmRequisiteUserFieldSetEnumValues
When the set of values for a list-type user field is changed
onCrmRequisiteUserFieldUpdate
When a user field is updated
onCrmRequisiteUserFieldDelete
When a user field is deleted
onCrmBankDetailAdd
When a bank detail is added
onCrmBankDetailUpdate
When a bank detail is updated
onCrmBankDetailDelete
When a bank detail is deleted
Copied
Was the article helpful?
Yes
No
Previous
Get the Description of Requisite Connection Fields
Next
When Registering an Address

---

## Event onCrmAddressRegister

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-address-register

Event onCrmAddressRegister | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmAddressRegister
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue your study
Scope:
crm
Who can subscribe:
any user
The
onCrmAddressRegister
event is triggered when an address is registered.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
[
'event'
=>
'onCrmAddressRegister'
,
'data'
=> [
'FIELDS'
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
'ANCHOR_ID'
=>
17192
,
'ANCHOR_TYPE_ID'
=>
3
,
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic event code. In this case, it is
onCrmAddressRegister
data
*
array
Array with the registered address data
ts
*
timestamp
Date and time of the event sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with the fields of the registered address
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
TYPE_ID
*
integer
Identifier of the address type. Enumeration element "Address Type".
The enumeration elements "Address Type" are returned by the method
crm.enum.addresstype
ENTITY_TYPE_ID
*
integer
Identifier of the parent object type.
Object type identifiers are returned by the method
crm.enum.ownertype
.
Addresses can only be linked to Requisites (and requisites are linked to companies or contacts) or Leads. For backward compatibility, the ability to link Addresses to Contacts or Companies is retained. However, this link is only possible on some older accounts where the old address handling mode was specifically enabled by support
ENTITY_ID
*
integer
Identifier of the parent object
ANCHOR_ID
*
integer
Identifier of the main parent object.
This field is for internal use. The value is automatically filled when adding an address.
This field contains the identifier of the parent object of the requisite (company or contact) if the address is linked to the requisite. If the address is linked to a lead, then this value will be the lead identifier
ANCHOR_TYPE_ID
*
integer
Identifier of the type of the main parent object.
This field is for internal use. The value is automatically filled when adding an address.
Object type identifiers are returned by the method
crm.enum.ownertype
.
This field contains the identifier of the type of the parent object of the requisite (company or contact) if the address is linked to the requisite. If the address is linked to a lead, then this value will be the lead type identifier
Parameter auth[]
Parameter auth[]
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
Continue your study
Continue your study
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Unregistering an Address

---

## Event onCrmAddressUnregister

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-address-unregister

Event onCrmAddressUnregister | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmAddressUnregister
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmAddressUnregister
is triggered when an address is deleted.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
[
'event'
=>
'onCrmAddressUnregister'
,
'data'
=> [
'FIELDS'
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
'ANCHOR_ID'
=>
17192
,
'ANCHOR_TYPE_ID'
=>
3
,
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic event code. In this case, it is
onCrmAddressUnregister
data
*
array
Array with the data of the deleted address
ts
*
timestamp
Date and time the event was sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with the fields of the deleted address
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
TYPE_ID
*
integer
Identifier of the address type. Enumeration element "Address Type".
The enumeration elements "Address Type" are returned by the method
crm.enum.addresstype
ENTITY_TYPE_ID
*
integer
Identifier of the parent object's type.
Object type identifiers are returned by the method
crm.enum.ownertype
.
Addresses can only be linked to Requisites (which are linked to companies or contacts) or Leads. For backward compatibility, the ability to link Addresses to Contacts or Companies is retained. However, this linkage is only possible on some older accounts where the old address handling mode was specifically enabled by technical support.
ENTITY_ID
*
integer
Identifier of the parent object
ANCHOR_ID
*
integer
Identifier of the main parent object.
This field is for internal use. The value is automatically filled when the address is added.
This field contains the identifier of the parent object of the requisite (company or contact) if the address is linked to a requisite. If the address is linked to a lead, this value will be the lead identifier.
ANCHOR_TYPE_ID
*
integer
Identifier of the type of the main parent object.
This field is for internal use. The value is automatically filled when the address is added.
Object type identifiers are returned by the method
crm.enum.ownertype
.
This field contains the identifier of the type of the parent object of the requisite (company or contact) if the address is linked to a requisite. If the address is linked to a lead, this value will be the lead type identifier.
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Registering an Address
Next
When Adding a Requisite

---

## Event onCrmRequisiteAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-requisite-add

Event onCrmRequisiteAdd | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmRequisiteAdd
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmRequisiteAdd
is triggered when a requisite is added.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
[
'event'
=>
'onCrmRequisiteAdd'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
27
,
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic event code. In this case, it is
onCrmRequisiteAdd
data
*
array
Array with data of the added requisite
ts
*
timestamp
Date and time the event was sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with fields of the added requisite
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the requisite. It can be obtained using the method
crm.requisite.list
.
Automatically created and unique within the account
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Unregistering an Address
Next
When Updating a Requisite

---

## Event onCrmRequisiteUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-requisite-update

Event onCrmRequisiteUpdate | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmRequisiteUpdate
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmRequisiteUpdate
is triggered when a requisite is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
[
'event'
=>
'onCrmRequisiteUpdate'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
27
,
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic event code. In this case, it is
onCrmRequisiteUpdate
data
*
array
Array with the updated requisite data
ts
*
timestamp
Date and time the event was sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with the fields of the updated requisite
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the requisite. It can be obtained using the method
crm.requisite.list
.
Automatically created and unique within the account
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Adding a Requisite
Next
When Deleting a Requisite

---

## Event onCrmRequisiteDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-requisite-delete

Event onCrmRequisiteDelete | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmRequisiteDelete
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The
onCrmRequisiteDelete
event is triggered when a requisite is deleted.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
[
'event'
=>
'onCrmRequisiteDelete'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
27
,
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic event code. In this case, it is
onCrmRequisiteDelete
data
*
array
Array with data of the deleted requisite
ts
*
timestamp
Date and time the event was sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with fields of the deleted requisite
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the requisite. It can be obtained using the method
crm.requisite.list
.
Automatically created and unique within the account
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Updating a Requisite
Next
When Adding a Custom Field

---

## Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-requisite-user-field-add

Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd | Bitrix24 REST API and Marketplace Applications
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmRequisiteUserFieldAdd
is triggered when a custom field of a requisite is added.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
[
'event'
=>
'onCrmRequisiteUserFieldAdd'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
235
,
'ENTITY_ID'
=>
'CRM_REQUISITE'
,
'FIELD_NAME'
=>
'NEWTECH_v1_STRING'
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic code of the event. In this case, it is
onCrmRequisiteUserFieldAdd
data
*
array
Array with the data of the added custom field of the requisite
ts
*
timestamp
Date and time of the event sent from the
event queue
auth
*
array
Authorization parameters and data about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with the fields of the added custom field of the requisite
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the added custom field of the requisite
ENTITY_ID
*
string
Symbolic identifier of the entity for which the field was added
FIELD_NAME
*
string
Symbolic code of the added custom field
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Requisite
Next
When Changing the Set of Values for a List-Type Custom Field

---

## Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-requisite-user-field-set-enum-values

Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues | Bitrix24 REST API and Marketplace Applications
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmRequisiteUserFieldSetEnumValues
is triggered when the set of values for a custom list-type field is changed.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
[
'event'
=>
'onCrmRequisiteUserFieldSetEnumValues'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
235
,
'ENTITY_ID'
=>
'CRM_REQUISITE'
,
'FIELD_NAME'
=>
'NEWTECH_v1_STRING'
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic code of the event. In this case, it is
onCrmRequisiteUserFieldSetEnumValues
data
*
array
Array with data of the custom field of the requisite for which the set of values was changed
ts
*
timestamp
Date and time of the event sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with fields of the custom field of the requisite for which the set of values was changed
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the custom field of the requisite for which the set of values was changed
ENTITY_ID
*
string
Symbolic identifier of the object to which the custom field belongs
FIELD_NAME
*
string
Symbolic code of the custom field for which the set of values was changed
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Adding a Custom Field
Next
When Updating a Custom Field

---

## Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-requisite-user-field-update

Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate | Bitrix24 REST API and Marketplace Applications
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmRequisiteUserFieldUpdate
is triggered when a user field of the requisite is changed.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
[
'event'
=>
'onCrmRequisiteUserFieldUpdate'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
235
,
'ENTITY_ID'
=>
'CRM_REQUISITE'
,
'FIELD_NAME'
=>
'NEWTECH_v1_STRING'
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic event code. In this case, it is
onCrmRequisiteUserFieldUpdate
data
*
array
Array with data of the changed user field of the requisite
ts
*
timestamp
Date and time of the event sent from the
event queue
auth
*
array
Authorization parameters and data about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with fields of the changed user field of the requisite
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the changed user field of the requisite
ENTITY_ID
*
string
Symbolic identifier of the object for which the field was changed
FIELD_NAME
*
string
Symbolic code of the changed user field
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Changing the Set of Values for a List-Type Custom Field
Next
When Deleting a Custom Field

---

## Event onCrmRequisiteUserFieldDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-requisite-user-field-delete

Event onCrmRequisiteUserFieldDelete | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmRequisiteUserFieldDelete
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmRequisiteUserFieldDelete
is triggered when a custom requisites field is deleted.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
[
'event'
=>
'onCrmRequisiteUserFieldDelete'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
235
,
'ENTITY_ID'
=>
'CRM_REQUISITE'
,
'FIELD_NAME'
=>
'NEWTECH_v1_STRING'
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic event code. In this case, it is
onCrmRequisiteUserFieldDelete
data
*
array
Array with data of the deleted custom requisites field
ts
*
timestamp
Date and time the event was sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with fields of the deleted custom requisites field
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the deleted custom requisites field
ENTITY_ID
*
string
Symbolic identifier of the object for which the field was deleted
FIELD_NAME
*
string
Symbolic code of the deleted custom requisites field
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Updating a Custom Field
Next
When Adding Bank Details

---

## Event on adding bank details onCrmBankDetailAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-bank-detail-add

Event on adding bank details onCrmBankDetailAdd | Bitrix24 REST API and Marketplace Applications
Event on adding bank details onCrmBankDetailAdd
Event on adding bank details onCrmBankDetailAdd
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmBankDetailAdd
is triggered when a bank detail is added.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
[
'event'
=>
'onCrmBankDetailAdd'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
357
,
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic event code. In this case, it is
onCrmBankDetailAdd
data
*
array
Array with the data of the added bank detail
ts
*
timestamp
Date and time of the event sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with the fields of the added bank detail
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the added bank detail. It is created automatically and is unique within the account
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event onCrmBankDetailUpdate
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Custom Field
Next
When Updating Bank Details

---

## Event onCrmBankDetailUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-bank-detail-update

Event onCrmBankDetailUpdate | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmBankDetailUpdate
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmBankDetailUpdate
is triggered when a bank detail is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
[
'event'
=>
'onCrmBankDetailUpdate'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
357
,
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic code of the event. In this case, it is
onCrmBankDetailUpdate
data
*
array
Array with the updated bank detail data
ts
*
timestamp
Date and time the event was sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with the fields of the updated bank detail
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the updated bank detail
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailDelete
Copied
Was the article helpful?
Yes
No
Previous
When Adding Bank Details
Next
When Deleting Bank Details

---

## Event onCrmBankDetailDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/requisites/events/on-crm-bank-detail-delete

Event onCrmBankDetailDelete | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmBankDetailDelete
What the handler receives
Parameter data[]
Parameter FIELDS[]
Parameter auth[]
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event
onCrmBankDetailDelete
is triggered when a bank detail is deleted.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
[
'event'
=>
'onCrmBankDetailDelete'
,
'data'
=> [
'FIELDS'
=> [
'ID'
=>
357
,
],
],
'ts'
=>
'1466439714'
,
'auth'
=> [
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'crm'
,
'domain'
=>
'some-domain.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://some-domain.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
],
]
Required parameters are marked with *
Parameter
type
Description
event
*
string
Symbolic event code. In this case, it is
onCrmBankDetailDelete
data
*
array
Array with the data of the deleted bank detail
ts
*
timestamp
Date and time the event was sent from the
event queue
auth
*
array
Authorization parameters and information about the account where the event occurred
Parameter data[]
Parameter data[]
Required parameters are marked with *
Parameter
type
Description
FIELDS
*
array
Array with the fields of the deleted bank detail
Parameter FIELDS[]
Parameter FIELDS[]
Required parameters are marked with *
Parameter
type
Description
ID
*
integer
Identifier of the deleted bank detail
Parameter auth[]
Parameter auth[]
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
Event onCrmAddressRegister
Event onCrmAddressUnregister
Event onCrmRequisiteAdd
Event onCrmRequisiteUpdate
Event onCrmRequisiteDelete
Event when adding a custom field of a requisite onCrmRequisiteUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmRequisiteUserFieldSetEnumValues
Event on changing user field of the requisite onCrmRequisiteUserFieldUpdate
Event onCrmRequisiteUserFieldDelete
Event on adding bank details onCrmBankDetailAdd
Event onCrmBankDetailUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Updating Bank Details
Next
Overview of Methods

---

