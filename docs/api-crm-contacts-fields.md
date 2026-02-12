---
description: 'CRM Contacts: User fields, company associations'
methods:
- crm.contact.add
- crm.contact.company.
- crm.contact.company.add
- crm.contact.company.delete
- crm.contact.company.fields
- crm.contact.company.items.delete
- crm.contact.company.items.get
- crm.contact.company.items.set
- crm.contact.list
- crm.contact.userfield.
- crm.contact.userfield.add
- crm.contact.userfield.delete
- crm.contact.userfield.get
- crm.contact.userfield.list
- crm.contact.userfield.update
- crm.item.list
- crm.status.entity.types
- crm.userfield.fields
- crm.userfield.settings.fields
- crm.userfield.types
- event.bind
pages: 18
title: 'CRM Contacts: User fields, company associations'
---
# CRM Contacts: User fields, company associations
> CRM Contacts: User fields, company associations
> **18 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Contact-Company Relationship: Overview of Methods](#contact-company-relationship-overview-of-methods)
- [Add a Company to the Specified Contact crm.contact.company.add](#add-a-company-to-the-specified-contact-crmcontactc)
- [Remove a company from the specified contact crm.contact.company.delete](#remove-a-company-from-the-specified-contact-crmcon)
- [Get Fields for Contact-Company crm.contact.company.fields](#get-fields-for-contact-company-crmcontactcompanyfi)
- [Get a set of companies associated with the specified contact crm.contact.company.items.get](#get-a-set-of-companies-associated-with-the-specifi)
- [Set the set of companies associated with the specified contact crm.contact.company.items.set](#set-the-set-of-companies-associated-with-the-speci)
- [Clear the set of companies associated with the specified contact crm.contact.company.items.delete](#clear-the-set-of-companies-associated-with-the-spe)
- [Custom Contact Fields: Overview of Methods](#custom-contact-fields-overview-of-methods)
- [Create a Custom Field for Contacts crm.contact.userfield.add](#create-a-custom-field-for-contacts-crmcontactuserf)
- [Update Existing Custom Contact Field crm.contact.userfield.update](#update-existing-custom-contact-field-crmcontactuse)
- [Get Custom Contact Field by Id crm.contact.userfield.get](#get-custom-contact-field-by-id-crmcontactuserfield)
- [Get a list of custom fields for contacts crm.contact.userfield.list](#get-a-list-of-custom-fields-for-contacts-crmcontac)
- [Delete Custom Contact Field crm.contact.userfield.delete](#delete-custom-contact-field-crmcontactuserfielddel)
- [Overview of Events When Working with Custom Contact Fields](#overview-of-events-when-working-with-custom-contac)
- [Event onCrmContactUserFieldAdd](#event-oncrmcontactuserfieldadd)
- [Event onCrmContactUserFieldUpdate](#event-oncrmcontactuserfieldupdate)
- [Event on changing the set of values for a custom list-type field onCrmContactUserFieldSetEnumValues](#event-on-changing-the-set-of-values-for-a-custom-l)
- [Event onCrmContactUserFieldDelete](#event-oncrmcontactuserfielddelete)

---

## Contact-Company Relationship: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/company/index

Contact-Company Relationship: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Benefits of the Relationship Between Contacts and Companies
Contact-Company Relationship: Overview of Methods
Benefits of the Relationship Between Contacts and Companies
Overview of Methods
Using the group of methods
crm.contact.company.*
, you can establish or remove the relationship between a contact and a company or a group of companies.
Quick navigation:
all methods
User documentation:
Relationship between deals, contacts, and companies
Benefits of the Relationship Between Contacts and Companies
Benefits of the Relationship Between Contacts and Companies
The contact card displays information about the companies: name, phone number, e-mail, address, company type, and industry.
You can call or send an e-mail directly from the contact card without navigating to the company card.
When
generating documents from a template
, you can use symbolic codes that will automatically insert data from related companies into the document.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: depending on the method
Method
Description
crm.contact.company.add
Adds a company to the specified contact
crm.contact.company.delete
Removes a company from the specified contact
crm.contact.company.fields
Returns the description of fields for the contact-company relationship
crm.contact.company.items.get
Returns a set of companies associated with the specified contact
crm.contact.company.items.set
Establishes a set of companies associated with the specified contact
crm.contact.company.items.delete
Clears the set of companies associated with the specified contact
Copied
Was the article helpful?
Yes
No
Previous
Get contact fields
Next
Add a Company to the Specified Contact

---

## Add a Company to the Specified Contact crm.contact.company.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/company/crm-contact-company-add

Add a Company to the Specified Contact crm.contact.company.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add a Company to the Specified Contact crm.contact.company.add
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
Who can execute the method: any user with "edit" access permission for contacts
The method
crm.contact.company.add
adds a company to the specified contact.
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
Can be obtained using the methods
crm.contact.list
or
crm.contact.add
fields
*
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
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
COMPANY_ID
*
crm_entity
Identifier of the company that will be linked to the contact.
The identifier can be obtained using the method
crm.item.list
with
entityTypeId = 4
IS_PRIMARY
boolean
Indicates whether the link is primary. Possible values:
Y
— yes
N
— no
For the first added element,
IS_PRIMARY
is
Y
by default.
Passing
IS_PRIMARY = Y
for a new and not first link overrides the existing primary link
SORT
integer
Sort index.
By default,
i + 10
, where
i
is the maximum sort index of existing links for the current contact or
0
if there are none
Code Examples
Code Examples
How to Use Examples in Documentation
Example of adding a contact-company link, where:
contact identifier —
54
company identifier —
32
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
'{"id":54,"fields":{"COMPANY_ID":32,"IS_PRIMARY":"Y","SORT":1000}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.company.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":54,"fields":{"COMPANY_ID":32,"IS_PRIMARY":"Y","SORT":1000},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.company.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.company.add'
,
{
id
:
54
,
fields
: {
COMPANY_ID
:
32
,
IS_PRIMARY
:
"Y"
,
SORT
:
1000
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
$response
=
$b24Service
->core
->
call
(
'crm.contact.company.add'
,
[
'id'
=>
54
,
'fields'
=> [
'COMPANY_ID'
=>
32
,
'IS_PRIMARY'
=>
'Y'
,
'SORT'
=>
1000
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
'Error adding contact company: '
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
'crm.contact.company.add'
,
{
id
:
54
,
fields
: {
COMPANY_ID
:
32
,
IS_PRIMARY
:
"Y"
,
SORT
:
1000
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
'crm.contact.company.add'
,
[
'id'
=>
54
,
'fields'
=> [
'COMPANY_ID'
=>
32
,
'IS_PRIMARY'
=>
'Y'
,
'SORT'
=>
1000
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
1724068028.331234
,
"finish"
:
1724068028.726591
,
"duration"
:
0.3953571319580078
,
"processing"
:
0.13033390045166016
,
"date_start"
:
"2024-08-19T13:47:08+02:00"
,
"date_finish"
:
"2024-08-19T13:47:08+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Root element of the response. Contains:
true
— on success
false
— on failure (most likely the company you are trying to add is already linked)
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
"The parameter 'ownerEntityID' is invalid or not defined."
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
The parameter 'ownerEntityID' is invalid or not defined
The
id
is less than 0 or not provided at all
-
The parameter 'fields' must be array
The
fields
is not an object
ACCESS_DENIED
Access denied!
The user does not have permission to edit contacts
-
Not found
Contact with the provided
id
not found
-
The parameter 'fields' is not valid
Can occur for several reasons:
if the required parameter
fields.COMPANY_ID
is not provided
if the provided parameter
fields.COMPANY_ID
is less than or equal to 0
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
Remove a company from the specified contact crm.contact.company.delete
Get Fields for Contact-Company crm.contact.company.fields
Get a set of companies associated with the specified contact crm.contact.company.items.get
Set the set of companies associated with the specified contact crm.contact.company.items.set
Clear the set of companies associated with the specified contact crm.contact.company.items.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Remove a Company from the Specified Contact

---

## Remove a company from the specified contact crm.contact.company.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/company/crm-contact-company-delete

Remove a company from the specified contact crm.contact.company.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Remove a company from the specified contact crm.contact.company.delete
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
Who can execute the method: any user with "edit" access permission for contacts
The method
crm.contact.company.delete
removes a company from the specified contact.
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
fields
*
object
An object containing information about which company needs to be removed from the bindings.
Contains a single key
COMPANY_ID
fields.COMPANY_ID
*
integer
Identifier of the company that needs to be removed from the bindings
Remove primary binding
If the primary binding is removed, the first available binding will become the new primary binding.
Code Examples
Code Examples
How to Use Examples in Documentation
Example of removing the contact-company link, where:
contact identifier —
54
company identifier —
32
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
'{"id":54,"fields":{"COMPANY_ID":32}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.contact.company.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":54,"fields":{"COMPANY_ID":32},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.company.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.company.delete'
,
{
id
:
54
,
fields
: {
COMPANY_ID
:
32
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
$response
=
$b24Service
->core
->
call
(
'crm.contact.company.delete'
,
[
'id'
=>
54
,
'fields'
=> [
'COMPANY_ID'
=>
32
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
'Error deleting company from contact: '
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
'crm.contact.company.delete'
,
{
id
:
54
,
fields
: {
COMPANY_ID
:
32
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
'crm.contact.company.delete'
,
[
'id'
=>
54
,
'fields'
=> [
'COMPANY_ID'
=>
32
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
1724072653.79827
,
"finish"
:
1724072717.749956
,
"duration"
:
63.95168590545654
,
"processing"
:
63.63148093223572
,
"date_start"
:
"2024-08-19T15:04:13+02:00"
,
"date_finish"
:
"2024-08-19T15:05:17+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Root element of the response. Contains:
true
— in case of success
false
— in case of failure (most likely the company you are trying to remove is not linked to the contact)
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
"The parameter 'ownerEntityID' is invalid or not defined."
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
The parameter 'ownerEntityID' is invalid or not defined
The provided
id
is less than 0
-
The parameter 'fields' must be array
An object was not provided in
fields
ACCESS_DENIED
Access denied!
The user does not have permission to edit contacts
-
Not found
Contact with the provided
id
was not found
-
The parameter 'fields' is not valid
Can occur for several reasons:
if the required parameter
fields.COMPANY_ID
is not provided
if the provided parameter
fields.COMPANY_ID
is less than or equal to 0
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
Add a Company to the Specified Contact crm.contact.company.add
Get Fields for Contact-Company crm.contact.company.fields
Get a set of companies associated with the specified contact crm.contact.company.items.get
Set the set of companies associated with the specified contact crm.contact.company.items.set
Clear the set of companies associated with the specified contact crm.contact.company.items.delete
Copied
Was the article helpful?
Yes
No
Previous
Add a Company to the Specified Contact
Next
Get Fields for Linking Contact-Company

---

## Get Fields for Contact-Company crm.contact.company.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/company/crm-contact-company-fields

Get Fields for Contact-Company crm.contact.company.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Fields for Contact-Company crm.contact.company.fields
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
crm.contact.company.fields
returns the description of fields for the contact-company relationship.
No parameters.
Code Examples
Code Examples
How to Use Examples in Documentation
Get the list of fields for the contact-company relationship
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.company.fields
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
https://**put_your_bitrix24_address**/rest/crm.contact.company.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.company.fields'
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
'crm.contact.company.fields'
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
'Error fetching contact company fields: '
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
'crm.contact.company.fields'
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
'crm.contact.company.fields'
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
"COMPANY_ID"
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
"Company"
}
}
,
"time"
:
{
"start"
:
1724065480.986461
,
"finish"
:
1724065481.321185
,
"duration"
:
0.33472418785095215
,
"processing"
:
0.01616501808166504
,
"date_start"
:
"2024-08-19T13:04:40+02:00"
,
"date_finish"
:
"2024-08-19T13:04:41+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Object in the format:
{
field_1: value_1,
field_2: value_2,
...
field_n: value_n,
}
where:
field_n
— field of the element
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
Add a Company to the Specified Contact crm.contact.company.add
Remove a company from the specified contact crm.contact.company.delete
Get a set of companies associated with the specified contact crm.contact.company.items.get
Set the set of companies associated with the specified contact crm.contact.company.items.set
Clear the set of companies associated with the specified contact crm.contact.company.items.delete
Copied
Was the article helpful?
Yes
No
Previous
Remove a Company from the Specified Contact
Next
Get Set of Companies Linked to the Specified Contact

---

## Get a set of companies associated with the specified contact crm.contact.company.items.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/company/crm-contact-company-items-get

Get a set of companies associated with the specified contact crm.contact.company.items.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a set of companies associated with the specified contact crm.contact.company.items.get
Method Parameters
Code Examples
Response Handling
Returned Data
Parameter contact_company_binding
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with "read" access permission for contacts
The method
crm.contact.company.items.get
returns a set of companies associated with the specified contact.
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
Example of retrieving all associated companies for a contact with
id = 54
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
'{"id":54}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.company.items.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":54,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.company.items.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.company.items.get'
,
{
id
:
54
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
'crm.contact.company.items.get'
,
[
'id'
=>
54
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
'Error getting contact company items: '
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
'crm.contact.company.items.get'
,
{
id
:
54
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
'crm.contact.company.items.get'
,
[
'id'
=>
54
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
"COMPANY_ID"
:
7
,
"SORT"
:
100
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
"COMPANY_ID"
:
8
,
"SORT"
:
110
,
"ROLE_ID"
:
0
,
"IS_PRIMARY"
:
"N"
}
,
{
"COMPANY_ID"
:
9
,
"SORT"
:
120
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
1724078791.470108
,
"finish"
:
1724078791.969407
,
"duration"
:
0.4992990493774414
,
"processing"
:
0.19150400161743164
,
"date_start"
:
"2024-08-19T16:46:31+02:00"
,
"date_finish"
:
"2024-08-19T16:46:31+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
contact_company_binding[]
Root element of the response. Contains an array with information about the companies associated with the contact
time
time
Information about the execution time of the request
Parameter contact_company_binding
Parameter contact_company_binding
Name
type
Description
COMPANY_ID
integer
Identifier of the company
SORT
integer
Sort index
ROLE_ID
integer
Identifier of the role (reserved)
IS_PRIMARY
boolean
Indicates whether the binding is primary. Possible values:
Y
— yes
N
— no
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
""
,
"error_description"
:
"The parameter ownerEntityID is invalid or not defined."
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
The parameter 'ownerEntityID' is invalid or not defined
The provided
id
is less than 0 or not provided at all
ACCESS_DENIED
Access denied!
The user does not have permission to read contacts
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
Add a Company to the Specified Contact crm.contact.company.add
Remove a company from the specified contact crm.contact.company.delete
Get Fields for Contact-Company crm.contact.company.fields
Set the set of companies associated with the specified contact crm.contact.company.items.set
Clear the set of companies associated with the specified contact crm.contact.company.items.delete
Copied
Was the article helpful?
Yes
No
Previous
Get Fields for Linking Contact-Company
Next
Set of Companies Linked to the Specified Contact

---

## Set the set of companies associated with the specified contact crm.contact.company.items.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/company/crm-contact-company-items-set

Set the set of companies associated with the specified contact crm.contact.company.items.set | Bitrix24 REST API and Marketplace Applications
Method Parameters
Set the set of companies associated with the specified contact crm.contact.company.items.set
Method Parameters
Structure of the Binding Object
Code Examples
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
crm.contact.company.items.set
sets the set of companies associated with the specified contact.
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
items
*
object[]
A set of objects that describe the associated companies for the contact. The structure of an individual binding object is described
below
Structure of the Binding Object
Structure of the Binding Object
Required parameters are marked with *
Name
type
Description
COMPANY_ID
*
crm_entity
Identifier of the company that will be associated with the contact.
The identifier can be obtained using the method
crm.item.list
with
entityTypeId = 4
IS_PRIMARY
boolean
Indicates whether the binding is primary. Possible values:
Y
— yes
N
— no
If there is no binding with
IS_PRIMARY = Y
, it will be set for the first binding in
items
.
If multiple bindings are provided with
IS_PRIMARY = Y
, the first binding with
IS_PRIMARY = Y
will be considered primary
SORT
integer
Sort index.
By default,
i + 10
, where
i
is the maximum sort index of existing and provided bindings for the current contact or
0
if
SORT
is not provided for any of the bindings and if the contact has no bindings.
If an existing binding is provided without the
SORT
parameter, the default value will not be set (the value will remain the same)
Code Examples
Code Examples
How to Use Examples in Documentation
Set the following associated companies for the contact with
id = 82
:
company with
id = 8
, make it primary and set
SORT = 100
company with
id = 9
, set
SORT = 200
company with
id = 10
, set
SORT = 400
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
'{"id":82,"items":[{"COMPANY_ID":8,"IS_PRIMARY":"Y","SORT":100},{"COMPANY_ID":9,"SORT":200},{"COMPANY_ID":10,"SORT":400}]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.company.items.set
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":82,"items":[{"COMPANY_ID":8,"IS_PRIMARY":"Y","SORT":100},{"COMPANY_ID":9,"SORT":200},{"COMPANY_ID":10,"SORT":400}],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.company.items.set
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.company.items.set'
,
{
id
:
82
,
items
: [
{
COMPANY_ID
:
8
,
IS_PRIMARY
:
"Y"
,
SORT
:
100
,
},
{
COMPANY_ID
:
9
,
SORT
:
200
,
},
{
COMPANY_ID
:
10
,
SORT
:
400
,
}
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
'crm.contact.company.items.set'
,
[
'id'
=>
82
,
'items'
=> [
[
'COMPANY_ID'
=>
8
,
'IS_PRIMARY'
=>
'Y'
,
'SORT'
=>
100
,
],
[
'COMPANY_ID'
=>
9
,
'SORT'
=>
200
,
],
[
'COMPANY_ID'
=>
10
,
'SORT'
=>
400
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
// Your logic for processing data
processData
(
$result
->
data
());
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
'Error setting company items for contact: '
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
'crm.contact.company.items.set'
,
{
id
:
82
,
items
: [
{
COMPANY_ID
:
8
,
IS_PRIMARY
:
"Y"
,
SORT
:
100
,
},
{
COMPANY_ID
:
9
,
SORT
:
200
,
},
{
COMPANY_ID
:
10
,
SORT
:
400
,
}
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
'crm.contact.company.items.set'
,
[
'id'
=>
82
,
'items'
=> [
[
'COMPANY_ID'
=>
8
,
'IS_PRIMARY'
=>
'Y'
,
'SORT'
=>
100
,
],
[
'COMPANY_ID'
=>
9
,
'SORT'
=>
200
,
],
[
'COMPANY_ID'
=>
10
,
'SORT'
=>
400
,
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
1724139480.073569
,
"finish"
:
1724139481.016709
,
"duration"
:
0.9431400299072266
,
"processing"
:
0.4230809211730957
,
"date_start"
:
"2024-08-20T09:38:00+02:00"
,
"date_finish"
:
"2024-08-20T09:38:01+02:00"
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
Root element of the response. Contains
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
""
,
"error_description"
:
"The parameter items must be array."
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
The parameter ownerEntityID is invalid or not defined
The provided
id
is less than 0 or not provided at all
-
The parameter items must be array
A non-array value was provided in
items
ACCESS_DENIED
Access denied!
The user does not have permission to edit contacts
-
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
Add a Company to the Specified Contact crm.contact.company.add
Remove a company from the specified contact crm.contact.company.delete
Get Fields for Contact-Company crm.contact.company.fields
Get a set of companies associated with the specified contact crm.contact.company.items.get
Clear the set of companies associated with the specified contact crm.contact.company.items.delete
Copied
Was the article helpful?
Yes
No
Previous
Get Set of Companies Linked to the Specified Contact
Next
Clear the Set of Companies Linked to the Specified Contact

---

## Clear the set of companies associated with the specified contact crm.contact.company.items.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/company/crm-contact-company-items-delete

Clear the set of companies associated with the specified contact crm.contact.company.items.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Clear the set of companies associated with the specified contact crm.contact.company.items.delete
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
Who can execute the method: any user with "edit" access permission for contacts
The method
crm.contact.company.items.delete
clears the set of companies associated with the specified contact.
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
Example of deleting all linked companies for a contact with
id = 54
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
'{"id":54}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.company.items.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":54,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.company.items.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.company.items.delete'
,
{
id
:
54
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
'crm.contact.company.items.delete'
,
[
'id'
=>
54
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
'Error deleting contact company item: '
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
'crm.contact.company.items.delete'
,
{
id
:
54
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
'crm.contact.company.items.delete'
,
[
'id'
=>
54
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
1724075916.767978
,
"finish"
:
1724075917.346106
,
"duration"
:
0.5781280994415283
,
"processing"
:
0.2096860408782959
,
"date_start"
:
"2024-08-19T15:58:36+02:00"
,
"date_finish"
:
"2024-08-19T15:58:37+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Root element of the response. Contains
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
"The parameter ownerEntityID is invalid or not defined."
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
The parameter 'ownerEntityID' is invalid or not defined
The provided
id
is less than 0 or not provided at all
ACCESS_DENIED
Access denied!
The user does not have permission to edit contacts
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
Add a Company to the Specified Contact crm.contact.company.add
Remove a company from the specified contact crm.contact.company.delete
Get Fields for Contact-Company crm.contact.company.fields
Get a set of companies associated with the specified contact crm.contact.company.items.get
Set the set of companies associated with the specified contact crm.contact.company.items.set
Copied
Was the article helpful?
Yes
No
Previous
Set of Companies Linked to the Specified Contact
Next
Overview of Methods

---

## Custom Contact Fields: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/index

Custom Contact Fields: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Types of Custom Fields
Custom Contact Fields: Overview of Methods
Types of Custom Fields
Custom Field Settings
Errors When Working with Custom Fields
Common Causes of Server Errors
Overview of Methods
Custom fields store information about a contact in various data formats: string, number, link, address, and others.
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
. This is an internal server error. The reason for the error can be found in the server logs at the time of the request:
In the cloud Bitrix24, submit a request to
technical support
to get details about the error.
In the on-premise Bitrix24, request the server error log from the server administrator or hosting administrator. Then, contact
technical support
and attach the log for analysis.
Common Causes of Server Errors
Common Causes of Server Errors
You can create 1016 custom fields for contacts — this is a limitation of the database architecture. If there are already 1016 fields for contacts in Bitrix24, attempting to create a new field will result in the method
crm.contact.userfield.add
returning an error
INTERNAL_SERVER_ERROR
.
You can check the number of custom fields for contacts using the method
crm.contact.userfield.list
.
There is a limitation on servers for the execution time of a single request —
max_execution_time
. The standard time is 60 seconds. If the request takes longer, it is interrupted with an error
INTERNAL_SERVER_ERROR
.
The time for
creating
or
deleting
a contact custom field depends on the number of contacts. When a field is created, it is added to all contact detail forms. When a field is deleted, it is removed from all detail forms. The fewer contacts you have in your Bitrix24, the faster fields are created and deleted.
To check the number of contacts in Bitrix24, use the method
crm.contact.list
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can perform the methods: depending on the method
Method
Description
crm.contact.userfield.add
Creates a new custom field for contacts
crm.contact.userfield.update
Updates an existing custom field for contacts
crm.contact.userfield.get
Returns a custom field for contacts by ID
crm.contact.userfield.list
Returns a list of custom fields for contacts by filter
crm.contact.userfield.delete
Deletes a custom field for contacts
Copied
Was the article helpful?
Yes
No
Previous
Clear the Set of Companies Linked to the Specified Contact
Next
Create a Custom Field for Contacts

---

## Create a Custom Field for Contacts crm.contact.userfield.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/crm-contact-userfield-add

Create a Custom Field for Contacts crm.contact.userfield.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create a Custom Field for Contacts crm.contact.userfield.add
Method Parameters
Parameter fields
Parameter SETTINGS
Type uf_enum_element
Code Examples
Example of Creating a String Type Custom Field
Example of Creating a List Type Custom Field
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
crm.contact.userfield.add
creates a new custom field for contacts.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
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
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
USER_TYPE_ID
*
string
The data type of the custom field. Possible values:
string
— string
integer
— integer
double
— number
boolean
— yes/no
datetime
— date/time
date
— date
money
— money
url
— link
address
— address
enumeration
— list
file
— file
employee
— link to employee
crm_status
— link to CRM directory
iblock_section
— link to information block sections
iblock_element
— link to information block elements
crm
— link to CRM elements
custom field types
FIELD_NAME
*
string
Field code. Unique.
The system limit for the field code is 20 characters. The prefix
UF_CRM_
is always added to the custom field name, meaning the actual length of the name is 13 characters.
Allowed characters:
A-Z
,
0-9
, and
_
LABEL
string
Default name of the custom field.
The provided value will be set in the following fields:
LIST_FILTER_LABEL
,
LIST_COLUMN_LABEL
,
EDIT_FORM_LABEL
,
ERROR_MESSAGE
,
HELP_MESSAGE
, if no value is provided for them
XML_ID
string
External code
LIST_FILTER_LABEL
string
|
lang_map
Filter label in the list.
When a string is provided, it will be set for all language identifiers.
When a
lang_map
type value is provided, the value from
LABEL
will be set for all languages not provided.
By default, the value passed in
LABEL
is set for all language identifiers
LIST_COLUMN_LABEL
string
|
lang_map
Header in the list.
When a string is provided, it will be set for all language identifiers.
When a
lang_map
type value is provided, the value from
LABEL
will be set for all languages not provided.
By default, the value passed in
LABEL
is set for all language identifiers
EDIT_FORM_LABEL
string
|
lang_map
Label in the edit form.
When a string is provided, it will be set for all language identifiers.
When a
lang_map
type value is provided, the value from
LABEL
will be set for all languages not provided.
By default, the value passed in
LABEL
is set for all language identifiers
ERROR_MESSAGE
string
|
lang_map
Error message.
When a string is provided, it will be set for all language identifiers.
When a
lang_map
type value is provided, the value from
LABEL
will be set for all languages not provided.
By default, the value passed in
LABEL
is set for all language identifiers
HELP_MESSAGE
string
|
lang_map
Help.
When a string is provided, it will be set for all language identifiers.
When a
lang_map
type value is provided, the value from
LABEL
will be set for all languages not provided.
By default, the value passed in
LABEL
is set for all language identifiers
MULTIPLE
boolean
Is the field multiple. Possible values:
Y
— yes
N
— no
Fields of type
boolean
cannot be multiple.
By default
N
MANDATORY
boolean
Is the field mandatory. Possible values:
Y
— yes
N
— no
By default
N
SHOW_FILTER
boolean
Show the field in the filter. Possible values:
Y
— yes
N
— no
By default
N
SETTINGS
object
Additional field parameters. Each field type (
USER_TYPE_ID
) has its own set of available settings, which are described
below
LIST
uf_enum_element[]
List of possible values for the custom field of type
enumeration
. For custom fields of other types, this parameter is meaningless.
By default
[]
SORT
integer
Sort index. Must be greater than zero.
By default
100
SHOW_IN_LIST
boolean
Show the custom field in the list.
This parameter has no effect within
crm
.
Possible values:
Y
— yes
N
— no
By default
N
EDIT_IN_LIST
boolean
Allow user editing. Possible values:
Y
— yes
N
— no
By default
Y
IS_SEARCHABLE
boolean
Are the field values included in the search.
This parameter has no effect within
crm
.
Possible values:
Y
— yes
N
— no
By default
N
Parameter SETTINGS
Parameter SETTINGS
Each type of custom field has its own set of additional settings. This method only supports those described below.
string
integer
double
boolean
date|datetime
enumeration
iblock_section|iblock_element
crm_status
crm
Name
type
Description
DEFAULT_VALUE
string
Default value.
By default
''
ROWS
integer
Number of rows in the input field. Must be greater than 0.
By default
1
Name
type
Description
DEFAULT_VALUE
integer
Default value
Name
type
Description
DEFAULT_VALUE
double
Default value
PRECISION
integer
Number precision. Must be greater than or equal to 0.
By default
2
Name
type
Description
DEFAULT_VALUE
integer
Default value, where
1
— yes,
0
— no.
Possible values:
>= 1
-> 1
<= 0
-> 0
By default
0
DISPLAY
string
Appearance. Possible values:
CHECKBOX
— checkbox
RADIO
— radio buttons
DROPDOWN
— dropdown list
By default
CHECKBOX
Name
type
Description
DEFAULT_VALUE
object
Default value.
Object format:
{
VALUE: datetime|date,
TYPE: 'NONE'|'NOW'|'FIXED',
}
where:
VALUE
— default value of type
datetime
or
date
TYPE
— type of default value:
NONE
— do not set a default value
NOW
— use the current time/date
FIXED
— use the time/date from
VALUE
Default value:
{
VALUE: '',
TYPE: 'NONE',
}
Name
type
Description
DISPLAY
string
Appearance. Possible values:
LIST
— list
UI
— input list
CHECKBOX
— checkboxes
DIALOG
— entity selection dialog
By default
LIST
LIST_HEIGHT
Height of the list. Must be greater than 0.
Available only when
DISPLAY = LIST
or
DISPLAY = UI
.
By default
1
Name
type
Description
IBLOCK_TYPE_ID
string
Identifier of the information block type.
By default
''
IBLOCK_ID
string
Identifier of the information block.
By default
0
DEFAULT_VALUE
string
Default value.
By default
''
DISPLAY
string
Appearance. Possible values:
DIALOG
— dialog
UI
— input list
LIST
— list
CHECKBOX
— checkboxes
By default
LIST
LIST_HEIGHT
integer
Height of the list. Must be greater than 0.
By default
1
ACTIVE_FILTER
boolean
Show elements with the active flag enabled. Possible values:
Y
— yes
N
— no
By default
N
Name
type
Description
ENTITY_TYPE
string
Identifier of the directory type.
Use
crm.status.entity.types
to find possible values.
By default
''
If none of the following options are provided, the link to leads will be enabled by default (
LEAD = Y
).
Name
type
Description
LEAD
boolean
Is the link to
Leads
enabled. Possible values:
Y
— yes
N
— no
By default
N
CONTACT
boolean
Is the link to
Contacts
enabled. Possible values:
Y
— yes
N
— no
By default
N
COMPANY
boolean
Is the link to
Companies
enabled. Possible values:
Y
— yes
N
— no
By default
N
DEAL
boolean
Is the link to
Deals
enabled. Possible values:
Y
— yes
N
— no
By default
N
Type uf_enum_element
Type uf_enum_element
Name
type
Description
VALUE
string
Value of the list element.
List elements with an empty or missing
VALUE
will be ignored
SORT
integer
Sort index. Must be greater than or equal to 0.
By default
0
DEF
boolean
Is the list element the default value. Possible values:
Y
— yes
N
— no
For a multiple field, multiple
DEF = Y
are allowed. For a non-multiple field, the first provided list element with
DEF = Y
will be considered the default value.
By default
N
XML_ID
string
External code of the value. Must be unique within the list elements of the custom field
Code Examples
Code Examples
How to Use Examples in Documentation
Example of Creating a String Type Custom Field
Example of Creating a String Type Custom Field
cURL (Webhook)
cURL (OAuth)
JS
PHP
PHP (B24PhpSdk)
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"LABEL":"Field \'
Hello, World!\'
","
USER_TYPE_ID
":"
string
","
FIELD_NAME
":"
HELLO_WORLD
","
MULTIPLE
":"
Y
","
MANDATORY
":"
Y
","
SHOW_FILTER
":"
Y
","
SETTINGS
":{"
DEFAULT_VALUE
":"
Hello, World! Default value
","
ROWS
":3},"
SORT
":1000,"
EDIT_IN_LIST
":"
Y
","
LIST_FILTER_LABEL
":"
Hello, World! Filter
","
LIST_COLUMN_LABEL
":{"
en
":"
Hello, World! Column
","
de
":"
Hallo, Welt! Spalte
"},"
EDIT_FORM_LABEL
":{"
en
":"
Hello, World! Edit
","
de
":"
Hallo, Welt! Bearbeiten
"},"
ERROR_MESSAGE
":{"
en
":"
Hello, World! Error
","
de
":"
Hallo, Welt! Fehler
"},"
HELP_MESSAGE
":{"
en
":"
Hello, World! Help
","
de
":"
Hallo, Welt! Hilfe
"}}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.contact.userfield.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"LABEL":"Field \'
Hello, World!\'
","
USER_TYPE_ID
":"
string
","
FIELD_NAME
":"
HELLO_WORLD
","
MULTIPLE
":"
Y
","
MANDATORY
":"
Y
","
SHOW_FILTER
":"
Y
","
SETTINGS
":{"
DEFAULT_VALUE
":"
Hello, World! Default value
","
ROWS
":3},"
SORT
":1000,"
EDIT_IN_LIST
":"
Y
","
LIST_FILTER_LABEL
":"
Hello, World! Filter
","
LIST_COLUMN_LABEL
":{"
en
":"
Hello, World! Column
","
de
":"
Hallo, Welt! Spalte
"},"
EDIT_FORM_LABEL
":{"
en
":"
Hello, World! Edit
","
de
":"
Hallo, Welt! Bearbeiten
"},"
ERROR_MESSAGE
":{"
en
":"
Hello, World! Error
","
de
":"
Hallo, Welt! Fehler
"},"
HELP_MESSAGE
":{"
en
":"
Hello, World! Help
","
de
":"
Hallo, Welt! Hilfe
"}},"
auth
":"
**put_access_token_here**
"}' \
https://**put_your_bitrix24_address**/rest/crm.contact.userfield.add
BX24
.
callMethod
(
'crm.contact.userfield.add'
,
{
fields
: {
LABEL
:
"Field \'Hello, World!\'"
,
USER_TYPE_ID
:
"string"
,
FIELD_NAME
:
"HELLO_WORLD"
,
MULTIPLE
:
"Y"
,
MANDATORY
:
"Y"
,
SHOW_FILTER
:
"Y"
,
SETTINGS
: {
DEFAULT_VALUE
:
"Hello, World! Default value"
,
ROWS
:
3
,
},
SORT
:
1000
,
EDIT_IN_LIST
:
"Y"
,
LIST_FILTER_LABEL
:
"Hello, World! Filter"
,
LIST_COLUMN_LABEL
: {
"en"
:
"Hello, World! Column"
,
"de"
:
"Hallo, Welt! Spalte"
},
EDIT_FORM_LABEL
: {
"en"
:
"Hello, World! Edit"
,
"de"
:
"Hallo, Welt! Bearbeiten"
},
ERROR_MESSAGE
: {
"en"
:
"Hello, World! Error"
,
"de"
:
"Hallo, Welt! Fehler"
},
HELP_MESSAGE
: {
"en"
:
"Hello, World! Help"
,
"de"
:
"Hallo, Welt! Hilfe"
},
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
'crm.contact.userfield.add'
,
[
'fields'
=> [
'LABEL'
=>
"Field 'Hello, World!'"
,
'USER_TYPE_ID'
=>
"string"
,
'FIELD_NAME'
=>
"HELLO_WORLD"
,
'MULTIPLE'
=>
"Y"
,
'MANDATORY'
=>
"Y"
,
'SHOW_FILTER'
=>
"Y"
,
'SETTINGS'
=> [
'DEFAULT_VALUE'
=>
"Hello, World! Default value"
,
'ROWS'
=>
3
,
],
'SORT'
=>
1000
,
'EDIT_IN_LIST'
=>
"Y"
,
'LIST_FILTER_LABEL'
=>
"Hello, World! Filter"
,
'LIST_COLUMN_LABEL'
=> [
'en'
=>
"Hello, World! Column"
,
'de'
=>
"Hallo, Welt! Spalte"
],
'EDIT_FORM_LABEL'
=> [
'en'
=>
"Hello, World! Edit"
,
'de'
=>
"Hallo, Welt! Bearbeiten"
],
'ERROR_MESSAGE'
=> [
'en'
=>
"Hello, World! Error"
,
'de'
=>
"Hallo, Welt! Fehler"
],
'HELP_MESSAGE'
=> [
'en'
=>
"Hello, World! Help"
,
'de'
=>
"Hallo, Welt! Hilfe"
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
try
{
$userfieldItemFields
= [
'FIELD_NAME'
=>
'UF_CRM_example'
,
'USER_TYPE_ID'
=>
'string'
,
'XML_ID'
=>
'xml_example'
,
'SORT'
=>
'100'
,
'MULTIPLE'
=>
'N'
,
'MANDATORY'
=>
'Y'
,
'SHOW_FILTER'
=>
'Y'
,
'SHOW_IN_LIST'
=>
'Y'
,
'EDIT_IN_LIST'
=>
'Y'
,
'IS_SEARCHABLE'
=>
'Y'
,
'EDIT_FORM_LABEL'
=>
'Example Field'
,
'LIST_COLUMN_LABEL'
=>
'Example Column'
,
'LIST_FILTER_LABEL'
=>
'Example Filter'
,
'ERROR_MESSAGE'
=>
'Error occurred'
,
'HELP_MESSAGE'
=>
'Help message'
,
'LIST'
=>
'list_value'
,
'SETTINGS'
=>
'settings_value'
,
];
$result
=
$serviceBuilder
->
getCRMScope
()
->
contactUserfield
()
->
add
(
$userfieldItemFields
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
Example of Creating a List Type Custom Field
Example of Creating a List Type Custom Field
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
'{"fields":{"LABEL":"Custom Field (list)","USER_TYPE_ID":"enumeration","FIELD_NAME":"ENUMERATION_EXAMPLE","MULTIPLE":"N","MANDATORY":"N","SHOW_FILTER":"Y","LIST":[{"VALUE":"List Item #1","DEF":"Y","XML_ID":"XML_ID_1","SORT":100},{"VALUE":"List Item #2","XML_ID":"XML_ID_2","SORT":200},{"VALUE":"List Item #3","XML_ID":"XML_ID_3","SORT":300},{"VALUE":"List Item #4","XML_ID":"XML_ID_4","SORT":400}],"SETTINGS":{"DISPLAY":"UI","LIST_HEIGHT":2},"SORT":2000}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.contact.userfield.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"LABEL":"Custom Field (list)","USER_TYPE_ID":"enumeration","FIELD_NAME":"ENUMERATION_EXAMPLE","MULTIPLE":"N","MANDATORY":"N","SHOW_FILTER":"Y","LIST":[{"VALUE":"List Item #1","DEF":"Y","XML_ID":"XML_ID_1","SORT":100},{"VALUE":"List Item #2","XML_ID":"XML_ID_2","SORT":200},{"VALUE":"List Item #3","XML_ID":"XML_ID_3","SORT":300},{"VALUE":"List Item #4","XML_ID":"XML_ID_4","SORT":400}],"SETTINGS":{"DISPLAY":"UI","LIST_HEIGHT":2},"SORT":2000},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.userfield.add
BX24
.
callMethod
(
'crm.contact.userfield.add'
,
{
fields
: {
LABEL
:
"Custom Field (list)"
,
USER_TYPE_ID
:
"enumeration"
,
FIELD_NAME
:
"ENUMERATION_EXAMPLE"
,
MULTIPLE
:
"N"
,
MANDATORY
:
"N"
,
SHOW_FILTER
:
"Y"
,
LIST
: [
{
VALUE
:
"List Item #1"
,
DEF
:
"Y"
,
XML_ID
:
"XML_ID_1"
,
SORT
:
100
,
},
{
VALUE
:
"List Item #2"
,
XML_ID
:
"XML_ID_2"
,
SORT
:
200
,
},
{
VALUE
:
"List Item #3"
,
XML_ID
:
"XML_ID_3"
,
SORT
:
300
,
},
{
VALUE
:
"List Item #4"
,
XML_ID
:
"XML_ID_4"
,
SORT
:
400
,
},
],
SETTINGS
: {
DISPLAY
:
"UI"
,
LIST_HEIGHT
:
2
,
},
SORT
:
2000
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
'crm.contact.userfield.add'
,
[
'fields'
=> [
'LABEL'
=>
"Custom Field (list)"
,
'USER_TYPE_ID'
=>
"enumeration"
,
'FIELD_NAME'
=>
"ENUMERATION_EXAMPLE"
,
'MULTIPLE'
=>
"N"
,
'MANDATORY'
=>
"N"
,
'SHOW_FILTER'
=>
"Y"
,
'LIST'
=> [
[
'VALUE'
=>
"List Item #1"
,
'DEF'
=>
"Y"
,
'XML_ID'
=>
"XML_ID_1"
,
'SORT'
=>
100
,
],
[
'VALUE'
=>
"List Item #2"
,
'XML_ID'
=>
"XML_ID_2"
,
'SORT'
=>
200
,
],
[
'VALUE'
=>
"List Item #3"
,
'XML_ID'
=>
"XML_ID_3"
,
'SORT'
=>
300
,
],
[
'VALUE'
=>
"List Item #4"
,
'XML_ID'
=>
"XML_ID_4"
,
'SORT'
=>
400
,
],
],
'SETTINGS'
=> [
'DISPLAY'
=>
"UI"
,
'LIST_HEIGHT'
=>
2
,
],
'SORT'
=>
2000
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
399
,
"time"
:
{
"start"
:
1724239307.903115
,
"finish"
:
1724239308.567422
,
"duration"
:
0.6643068790435791
,
"processing"
:
0.20090818405151367
,
"date_start"
:
"2024-08-21T13:21:47+02:00"
,
"date_finish"
:
"2024-08-21T13:21:48+02:00"
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
Root element of the response, contains the identifier of the created custom field
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
400
This method may return errors not immediately, but by collecting several and concatenating them into a string:
\n
.
{
"error"
:
""
,
"error_description"
:
"The 'USER_TYPE_ID' field is not found."
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
Access denied
The user does not have administrative rights
The 'FIELD_NAME' field is not found
Either an empty
FIELD_NAME
was provided, or it was not provided at all
Field name is too long (more than 50 characters)
The provided
FIELD_NAME
contains more than 50 characters
Field name contains invalid characters. Allowed are:
A-Z
,
0-9
, and
_
The provided
FIELD_NAME
contains invalid characters
The 'USER_TYPE_ID' field is not found
Either an empty
USER_TYPE_ID
was provided, or it was not provided at all
Invalid user type specified
The provided
USER_TYPE_ID
does not exist
List item with XML_ID=
XML_ID
already exists
The provided
XML_ID
in list items are not unique
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
Update Existing Custom Contact Field crm.contact.userfield.update
Get Custom Contact Field by Id crm.contact.userfield.get
Get a list of custom fields for contacts crm.contact.userfield.list
Delete Custom Contact Field crm.contact.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Modify an Existing Custom Field for Contacts

---

## Update Existing Custom Contact Field crm.contact.userfield.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/crm-contact-userfield-update

Update Existing Custom Contact Field crm.contact.userfield.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Existing Custom Contact Field crm.contact.userfield.update
Method Parameters
Parameter fields
Parameter SETTINGS
Type uf_enum_element
Code Examples
Example of Updating a String Type Custom Field
Example of Updating a List Type Custom Field
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
crm.contact.userfield.update
updates an existing custom contact field.
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
The identifier can be obtained using the methods
crm.contact.userfield.add
and
crm.contact.userfield.list
fields
*
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
Parameter fields
Parameter fields
Parameter
type
Description
MANDATORY
boolean
Is the field mandatory? Possible values:
Y
— yes
N
— no
SHOW_FILTER
boolean
Should the field be shown in the filter? Possible values:
Y
— yes
N
— no
XML_ID
string
External code
SETTINGS
object
Additional field parameters. Each field type (
USER_TYPE_ID
) has its own set of available settings, which are described
below
.
The field only overwrites the passed values
LIST
uf_enum_element[]
List of possible values for a custom field of type
enumeration
. This parameter is meaningless for custom fields of other types
SORT
integer
Sort index. Must be greater than zero
SHOW_IN_LIST
boolean
Should the custom field be shown in the list?
This parameter has no effect within
crm
.
Possible values:
Y
— yes
N
— no
EDIT_IN_LIST
boolean
Allow user editing? Possible values:
Y
— yes
N
— no
IS_SEARCHABLE
boolean
Are the field values included in the search?
This parameter has no effect within
crm
.
Possible values:
Y
— yes
N
— no
LIST_FILTER_LABEL
string
|
lang_map
Filter label in the list.
When passing a string, it is set for each language.
For languages where no value is explicitly specified,
''
will be recorded.
The field completely overwrites the previous value
LIST_COLUMN_LABEL
string
|
lang_map
Header in the list.
When passing a string, it is set for each language.
For languages where no value is explicitly specified,
''
will be recorded.
The field completely overwrites the previous value
EDIT_FORM_LABEL
string
|
lang_map
Label in the edit form.
When passing a string, it is set for each language.
For languages where no value is explicitly specified,
''
will be recorded.
The field completely overwrites the previous value
ERROR_MESSAGE
string
|
lang_map
Error message.
When passing a string, it is set for each language.
For languages where no value is explicitly specified,
''
will be recorded.
The field completely overwrites the previous value
HELP_MESSAGE
string
|
lang_map
Help message.
When passing a string, it is set for each language.
For languages where no value is explicitly specified,
''
will be recorded.
The field completely overwrites the previous value
Parameter SETTINGS
Parameter SETTINGS
Each type of custom field has its own set of additional settings. This method supports changing only those described below.
string
integer
double
boolean
datetime
enumeration
iblock_section|iblock_element
crm_status
crm
Name
type
Description
DEFAULT_VALUE
string
Default value
ROWS
integer
Number of rows in the input field. Must be greater than 0 and less than 50.
If a value <= 0 is passed, it will be set to
1
.
If a value >= 50 is passed, it will be set to
50
Name
type
Description
DEFAULT_VALUE
integer
Default value
Name
type
Description
DEFAULT_VALUE
double
Default value
PRECISION
integer
Number precision. Must be greater than or equal to 0.
If an invalid value is passed, it will be set to
2
Name
type
Description
DEFAULT_VALUE
integer
Default value, where
1
— yes,
0
— no.
When passing a value, it will be set according to the rule:
>= 1
-> 1
<= 0
-> 0
DISPLAY
string
Appearance. Possible values:
CHECKBOX
— checkbox
RADIO
— radio buttons
DROPDOWN
— dropdown list
Name
type
Description
DEFAULT_VALUE
object
Default value. Object format:
{
VALUE: datetime,
TYPE: 'NONE'|'NOW'|'FIXED',
}
where
VALUE
— default value of type
datetime
TYPE
— type of default value:
NONE
— do not set a default value
NOW
— use the current time/date
FIXED
— use the time/date from
VALUE
If an invalid value is passed, it will be set to:
VALUE: '',
TYPE: 'NONE',
Name
type
Description
DISPLAY
string
Appearance. Possible values:
LIST
— list
UI
— input list
CHECKBOX
— checkboxes
DIALOG
— entity selection dialog
LIST_HEIGHT
List height. Must be greater than 0
Name
type
Description
IBLOCK_TYPE_ID
string
Identifier of the information block type
IBLOCK_ID
string
Identifier of the information block
DEFAULT_VALUE
string
Default value
DISPLAY
string
Appearance. Possible values:
DIALOG
— dialog
UI
— input list
LIST
— list
CHECKBOX
— checkboxes
LIST_HEIGHT
integer
List height. Must be greater than 0
ACTIVE_FILTER
boolean
Should elements with the active flag be shown? Possible values:
Y
— yes
N
— no
Name
type
Description
ENTITY_TYPE
string
Identifier of the reference type.
Use
crm.status.entity.types
to find out possible values
If none of the following options are passed, the binding to leads will be enabled by default (
LEAD = Y
)
Name
type
Description
LEAD
boolean
Is the binding to
Leads
enabled? Possible values:
Y
— yes
N
— no
CONTACT
boolean
Is the binding to
Contacts
enabled? Possible values:
Y
— yes
N
— no
COMPANY
boolean
Is the binding to
Companies
enabled? Possible values:
Y
— yes
N
— no
DEAL
boolean
Is the binding to
Deals
enabled? Possible values:
Y
— yes
N
— no
Type uf_enum_element
Type uf_enum_element
Name
type
Description
ID
string
Identifier of the list item. When passing this parameter, the corresponding list item will be changed; otherwise, a new list item will be added.
The identifier can be obtained using the method
crm.contact.userfield.get
DEL
boolean
Flag necessary for deleting a list item. Makes sense only when passing
ID
.
Possible values:
Y
— delete
N
— do not delete
Default is
N
VALUE
string
Value of the list item
SORT
integer
Sort index. Must be greater than or equal to 0
DEF
boolean
Is the list item the default value? Possible values:
Y
— yes
N
— no
For a multiple field, multiple
DEF = Y
is allowed. For a non-multiple field, the first passed list item with
DEF = Y
will be considered the default value
XML_ID
string
External code of the value. Must be unique within the list items of the custom field
Code Examples
Code Examples
How to Use Examples in Documentation
Example of Updating a String Type Custom Field
Example of Updating a String Type Custom Field
cURL (Webhook)
cURL (OAuth)
JS
PHP
PHP (B24PhpSdk)
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":536,"fields":{"MANDATORY":"N","SHOW_FILTER":"N","SETTINGS":{"DEFAULT_VALUE":"Hello, World! Default value (changed)","ROWS":10},"SORT":2000,"EDIT_IN_LIST":"N","LIST_FILTER_LABEL":"Hello, World! Filter (changed)","LIST_COLUMN_LABEL":{"en":"Hello, World! Column (changed)","de":"Hallo, Welt! Spalte (geändert)"},"EDIT_FORM_LABEL":{"en":"Hello, World! Edit (changed)","de":"Hallo, Welt! Bearbeiten (geändert)"},"ERROR_MESSAGE":{"en":"Hello, World! Error (changed)","de":"Hallo, Welt! Fehler (geändert)"},"HELP_MESSAGE":{"en":"Hello, World! Help (changed)","de":"Hallo, Welt! Hilfe (geändert)"}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.contact.userfield.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":536,"fields":{"MANDATORY":"N","SHOW_FILTER":"N","SETTINGS":{"DEFAULT_VALUE":"Hello, World! Default value (changed)","ROWS":10},"SORT":2000,"EDIT_IN_LIST":"N","LIST_FILTER_LABEL":"Hello, World! Filter (changed)","LIST_COLUMN_LABEL":{"en":"Hello, World! Column (changed)","de":"Hallo, Welt! Spalte (geändert)"},"EDIT_FORM_LABEL":{"en":"Hello, World! Edit (changed)","de":"Hallo, Welt! Bearbeiten (geändert)"},"ERROR_MESSAGE":{"en":"Hello, World! Error (changed)","de":"Hallo, Welt! Fehler (geändert)"},"HELP_MESSAGE":{"en":"Hello, World! Help (changed)","de":"Hallo, Welt! Hilfe (geändert)"}}, "auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.userfield.update
BX24
.
callMethod
(
'crm.contact.userfield.update'
,
{
id
:
536
,
fields
: {
MANDATORY
:
"N"
,
SHOW_FILTER
:
"N"
,
SETTINGS
: {
DEFAULT_VALUE
:
"Hello, World! Default value (changed)"
,
ROWS
:
10
,
},
SORT
:
2000
,
EDIT_IN_LIST
:
"N"
,
LIST_FILTER_LABEL
:
"Hello, World! Filter (changed)"
,
LIST_COLUMN_LABEL
: {
"en"
:
"Hello, World! Column (changed)"
,
"de"
:
"Hallo, Welt! Spalte (geändert)"
},
EDIT_FORM_LABEL
: {
"en"
:
"Hello, World! Edit (changed)"
,
"de"
:
"Hallo, Welt! Bearbeiten (geändert)"
},
ERROR_MESSAGE
: {
"en"
:
"Hello, World! Error (changed)"
,
"de"
:
"Hallo, Welt! Fehler (geändert)"
},
HELP_MESSAGE
: {
"en"
:
"Hello, World! Help (changed)"
,
"de"
:
"Hallo, Welt! Hilfe (geändert)"
},
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
'crm.contact.userfield.update'
,
[
'id'
=>
536
,
'fields'
=> [
'MANDATORY'
=>
"N"
,
'SHOW_FILTER'
=>
"N"
,
'SETTINGS'
=> [
'DEFAULT_VALUE'
=>
"Hello, World! Default value (changed)"
,
'ROWS'
=>
10
,
],
'SORT'
=>
2000
,
'EDIT_IN_LIST'
=>
"N"
,
'LIST_FILTER_LABEL'
=>
"Hello, World! Filter (changed)"
,
'LIST_COLUMN_LABEL'
=> [
'en'
=>
"Hello, World! Column (changed)"
,
'de'
=>
"Hallo, Welt! Spalte (geändert)"
],
'EDIT_FORM_LABEL'
=> [
'en'
=>
"Hello, World! Edit (changed)"
,
'de'
=>
"Hallo, Welt! Bearbeiten (geändert)"
],
'ERROR_MESSAGE'
=> [
'en'
=>
"Hello, World! Error (changed)"
,
'de'
=>
"Hallo, Welt! Fehler (geändert)"
],
'HELP_MESSAGE'
=> [
'en'
=>
"Hello, World! Help (changed)"
,
'de'
=>
"Hallo, Welt! Hilfe (geändert)"
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
try
{
$contactUserfieldItemId
=
123
;
// Example ID
$userfieldFieldsToUpdate
= [
'FIELD_NAME'
=>
'New Field Name'
,
'USER_TYPE_ID'
=>
'string'
,
'SORT'
=>
'100'
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
'Y'
,
'SHOW_IN_LIST'
=>
'Y'
,
'EDIT_IN_LIST'
=>
'Y'
,
'IS_SEARCHABLE'
=>
'Y'
,
'EDIT_FORM_LABEL'
=>
'New Label'
,
'LIST_COLUMN_LABEL'
=>
'Column Label'
,
'LIST_FILTER_LABEL'
=>
'Filter Label'
,
'ERROR_MESSAGE'
=>
'Error Message'
,
'HELP_MESSAGE'
=>
'Help Message'
,
'LIST'
=>
''
,
'SETTINGS'
=>
''
,
];
$result
=
$serviceBuilder
->
getCRMScope
()
->
contactUserfield
()
->
update
(
$contactUserfieldItemId
,
$userfieldFieldsToUpdate
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
Example of Updating a List Type Custom Field
Example of Updating a List Type Custom Field
Current list items:
[
{
"ID"
:
"115"
,
"SORT"
:
"100"
,
"VALUE"
:
"List item #1"
,
"DEF"
:
"Y"
,
"XML_ID"
:
"XML_ID_1"
}
,
{
"ID"
:
"116"
,
"SORT"
:
"200"
,
"VALUE"
:
"List item #2"
,
"DEF"
:
"N"
,
"XML_ID"
:
"XML_ID_2"
}
,
{
"ID"
:
"117"
,
"SORT"
:
"300"
,
"VALUE"
:
"List item #3"
,
"DEF"
:
"N"
,
"XML_ID"
:
"XML_ID_3"
}
,
{
"ID"
:
"118"
,
"SORT"
:
"400"
,
"VALUE"
:
"List item #4"
,
"DEF"
:
"N"
,
"XML_ID"
:
"XML_ID_4"
}
]
Change it as follows:
remove list items with
ID = 115
and
ID = 116
update the list item with
ID  = 117
:
VALUE
: “List item #3” -> “List item #3 (changed)”
SORT
: 300 -> 50
add a new list item “List item #5”
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
'{"fields":{"MANDATORY":"N","SHOW_FILTER":"Y","LIST":[{"ID":115,"DEL":"Y"},{"ID":116,"DEL":"Y"},{"ID":117,"VALUE":"List item #3 (changed)","SORT":50},{"VALUE":"List item #5","XML_ID":"XML_ID_5","SORT":500}],"SETTINGS":{"DISPLAY":"DIALOG","LIST_HEIGHT":3},"SORT":1000}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.contact.userfield.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"MANDATORY":"N","SHOW_FILTER":"Y","LIST":[{"ID":115,"DEL":"Y"},{"ID":116,"DEL":"Y"},{"ID":117,"VALUE":"List item #3 (changed)","SORT":50},{"VALUE":"List item #5","XML_ID":"XML_ID_5","SORT":500}],"SETTINGS":{"DISPLAY":"DIALOG","LIST_HEIGHT":3},"SORT":1000},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.userfield.update
BX24
.
callMethod
(
'crm.contact.userfield.update'
,
{
fields
: {
MANDATORY
:
"N"
,
SHOW_FILTER
:
"Y"
,
LIST
: [
{
ID
:
115
,
DEL
:
"Y"
},
{
ID
:
116
,
DEL
:
"Y"
,
},
{
ID
:
117
,
VALUE
:
"List item #3 (changed)"
,
SORT
:
50
,
},
{
VALUE
:
"List item #5"
,
XML_ID
:
"XML_ID_5"
,
SORT
:
500
,
},
],
SETTINGS
: {
DISPLAY
:
"DIALOG"
,
LIST_HEIGHT
:
3
,
},
SORT
:
1000
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
'crm.contact.userfield.update'
,
[
'fields'
=> [
'MANDATORY'
=>
"N"
,
'SHOW_FILTER'
=>
"Y"
,
'LIST'
=> [
[
'ID'
=>
115
,
'DEL'
=>
"Y"
],
[
'ID'
=>
116
,
'DEL'
=>
"Y"
,
],
[
'ID'
=>
117
,
'VALUE'
=>
"List item #3 (changed)"
,
'SORT'
=>
50
,
],
[
'VALUE'
=>
"List item #5"
,
'XML_ID'
=>
"XML_ID_5"
,
'SORT'
=>
500
,
],
],
'SETTINGS'
=> [
'DISPLAY'
=>
"DIALOG"
,
'LIST_HEIGHT'
=>
3
,
],
'SORT'
=>
1000
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
1724419843.518672
,
"finish"
:
1724419844.120328
,
"duration"
:
0.6016559600830078
,
"processing"
:
0.1907808780670166
,
"date_start"
:
"2024-08-23T15:30:43+02:00"
,
"date_finish"
:
"2024-08-23T15:30:44+02:00"
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
-
Parameter 'fields' must be array
The passed
fields
is not an object
-
ID is not defined or invalid
The passed
id
is less than zero or not passed at all
-
Access denied
Occurs when:
the user does not have administrative rights
the user tries to delete a custom field not linked to contacts
ERROR_NOT_FOUND
The entity with ID 'id' is not found
The custom field with the passed
id
does not exist
ERROR_CORE
List item with value XML_ID=
XML_ID
already exists
The passed
XML_ID
for the list item must be unique within the list items of a given custom field
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
Create a Custom Field for Contacts crm.contact.userfield.add
Get Custom Contact Field by Id crm.contact.userfield.get
Get a list of custom fields for contacts crm.contact.userfield.list
Delete Custom Contact Field crm.contact.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Create a Custom Field for Contacts
Next
Retrieve a Custom Field for Contacts by Id

---

## Get Custom Contact Field by Id crm.contact.userfield.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/crm-contact-userfield-get

Get Custom Contact Field by Id crm.contact.userfield.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Custom Contact Field by Id crm.contact.userfield.get
Method Parameters
Code Examples
Response Handling
Returned Data
userfield
Parameter settings
Type uf_enum_element
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: administrator
The method
crm.contact.userfield.get
returns a custom contact field by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the custom field associated with the contact.
The identifier can be obtained using the methods
crm.contact.userfield.add
or
crm.contact.userfield.list
Code Examples
Code Examples
How to Use Examples in Documentation
Get the custom field with
id = 399
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
'{"id":399}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.userfield.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":399,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.userfield.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.userfield.get'
,
{
id
:
399
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
'crm.contact.userfield.get'
,
[
'id'
=>
399
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
'Error getting contact user field: '
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
'crm.contact.userfield.get'
,
{
id
:
399
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
'crm.contact.userfield.get'
,
[
'id'
=>
399
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
"ID"
:
"399"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_HELLO_WORLD"
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
"1000"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"Y"
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
"Y"
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
3
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
"Hello, World! Default value"
}
,
"EDIT_FORM_LABEL"
:
{
"ar"
:
"Field \u0027Hello, World!\u0027"
,
"br"
:
"Field \u0027Hello, World!\u0027"
,
"en"
:
"Hello, World! Edit"
,
"fr"
:
"Field \u0027Hello, World!\u0027"
,
"id"
:
"Field \u0027Hello, World!\u0027"
,
"it"
:
"Field \u0027Hello, World!\u0027"
,
"ja"
:
"Field \u0027Hello, World!\u0027"
,
"la"
:
"Field \u0027Hello, World!\u0027"
,
"ms"
:
"Field \u0027Hello, World!\u0027"
,
"pl"
:
"Field \u0027Hello, World!\u0027"
,
"ru"
:
"Hello, World! Edit"
,
"sc"
:
"Field \u0027Hello, World!\u0027"
,
"tc"
:
"Field \u0027Hello, World!\u0027"
,
"th"
:
"Field \u0027Hello, World!\u0027"
,
"tr"
:
"Field \u0027Hello, World!\u0027"
,
"vn"
:
"Field \u0027Hello, World!\u0027"
}
,
"LIST_COLUMN_LABEL"
:
{
"ar"
:
"Field \u0027Hello, World!\u0027"
,
"br"
:
"Field \u0027Hello, World!\u0027"
,
"en"
:
"Hello, World! Column"
,
"fr"
:
"Field \u0027Hello, World!\u0027"
,
"id"
:
"Field \u0027Hello, World!\u0027"
,
"it"
:
"Field \u0027Hello, World!\u0027"
,
"ja"
:
"Field \u0027Hello, World!\u0027"
,
"la"
:
"Field \u0027Hello, World!\u0027"
,
"ms"
:
"Field \u0027Hello, World!\u0027"
,
"pl"
:
"Field \u0027Hello, World!\u0027"
,
"ru"
:
"Hello, World! Column"
,
"sc"
:
"Field \u0027Hello, World!\u0027"
,
"tc"
:
"Field \u0027Hello, World!\u0027"
,
"th"
:
"Field \u0027Hello, World!\u0027"
,
"tr"
:
"Field \u0027Hello, World!\u0027"
,
"vn"
:
"Field \u0027Hello, World!\u0027"
}
,
"LIST_FILTER_LABEL"
:
{
"ar"
:
"Hello, World! Filter"
,
"br"
:
"Hello, World! Filter"
,
"en"
:
"Hello, World! Filter"
,
"fr"
:
"Hello, World! Filter"
,
"id"
:
"Hello, World! Filter"
,
"it"
:
"Hello, World! Filter"
,
"ja"
:
"Hello, World! Filter"
,
"la"
:
"Hello, World! Filter"
,
"ms"
:
"Hello, World! Filter"
,
"pl"
:
"Hello, World! Filter"
,
"ru"
:
"Hello, World! Filter"
,
"sc"
:
"Hello, World! Filter"
,
"tc"
:
"Hello, World! Filter"
,
"th"
:
"Hello, World! Filter"
,
"tr"
:
"Hello, World! Filter"
,
"vn"
:
"Hello, World! Filter"
}
,
"ERROR_MESSAGE"
:
{
"ar"
:
"Field \u0027Hello, World!\u0027"
,
"br"
:
"Field \u0027Hello, World!\u0027"
,
"en"
:
"Hello, World! Error"
,
"fr"
:
"Field \u0027Hello, World!\u0027"
,
"id"
:
"Field \u0027Hello, World!\u0027"
,
"it"
:
"Field \u0027Hello, World!\u0027"
,
"ja"
:
"Field \u0027Hello, World!\u0027"
,
"la"
:
"Field \u0027Hello, World!\u0027"
,
"ms"
:
"Field \u0027Hello, World!\u0027"
,
"pl"
:
"Field \u0027Hello, World!\u0027"
,
"ru"
:
"Hello, World! Error"
,
"sc"
:
"Field \u0027Hello, World!\u0027"
,
"tc"
:
"Field \u0027Hello, World!\u0027"
,
"th"
:
"Field \u0027Hello, World!\u0027"
,
"tr"
:
"Field \u0027Hello, World!\u0027"
,
"vn"
:
"Field \u0027Hello, World!\u0027"
}
,
"HELP_MESSAGE"
:
{
"ar"
:
"Field \u0027Hello, World!\u0027"
,
"br"
:
"Field \u0027Hello, World!\u0027"
,
"en"
:
"Hello, World! Help"
,
"fr"
:
"Field \u0027Hello, World!\u0027"
,
"id"
:
"Field \u0027Hello, World!\u0027"
,
"it"
:
"Field \u0027Hello, World!\u0027"
,
"ja"
:
"Field \u0027Hello, World!\u0027"
,
"la"
:
"Field \u0027Hello, World!\u0027"
,
"ms"
:
"Field \u0027Hello, World!\u0027"
,
"pl"
:
"Field \u0027Hello, World!\u0027"
,
"ru"
:
"Hello, World! Help"
,
"sc"
:
"Field \u0027Hello, World!\u0027"
,
"tc"
:
"Field \u0027Hello, World!\u0027"
,
"th"
:
"Field \u0027Hello, World!\u0027"
,
"tr"
:
"Field \u0027Hello, World!\u0027"
,
"vn"
:
"Field \u0027Hello, World!\u0027"
}
}
,
"time"
:
{
"start"
:
1724318753.341079
,
"finish"
:
1724318753.621247
,
"duration"
:
0.2801680564880371
,
"processing"
:
0.023567914962768555
,
"date_start"
:
"2024-08-22T11:25:53+02:00"
,
"date_finish"
:
"2024-08-22T11:25:53+02:00"
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
userfield
Root element of the response, contains information about the custom field
time
time
Information about the request execution time
userfield
userfield
Parameter
type
Description
ID
integer
Identifier of the custom field
ENTITY_ID
string
String identifier binding the custom field to the entity.
In the case of methods
crm.contact.userfield.*
, the value
CRM_CONTACT
is automatically assigned
FIELD_NAME
string
Field code. Unique
USER_TYPE_ID
string
Data type of the custom field. Possible values:
string
— string
integer
— integer
double
— number
boolean
— yes/no
datetime
— date/time
date
— date
money
— money
url
— link
address
— address
enumeration
— list
file
— file
employee
— employee binding
crm_status
— binding to CRM directory
iblock_section
— binding to information block sections
iblock_element
— binding to information block elements
crm
— binding to CRM elements
custom field types
XML_ID
string
External code
SORT
integer
Sort index
MULTIPLE
boolean
Indicates whether the field is multiple. Possible values:
Y
— yes
N
— no
MANDATORY
boolean
Indicates whether the field is mandatory. Possible values:
Y
— yes
N
— no
SHOW_FILTER
boolean
Indicates whether to show the field in the filter. Possible values:
N
— do not show
I
— exact match
E
— mask
S
— substring
SHOW_IN_LIST
boolean
Indicates whether to show the custom field in the list.
This parameter does not affect anything within
crm
.
Possible values:
Y
— yes
N
— no
EDIT_IN_LIST
boolean
Allows user editing. Possible values:
Y
— yes
N
— no
IS_SEARCHABLE
boolean
Indicates whether the field values participate in search.
This parameter does not affect anything within
crm
.
Possible values:
Y
— yes
N
— no
SETTINGS
object
Additional field parameters. Each field type (
USER_TYPE_ID
) has its own set of available settings, which are described
below
LIST
uf_enum_element[]
List of possible values for the custom field of type
enumeration
. For custom fields of other types, this parameter is meaningless
EDIT_FORM_LABEL
lang_map
Label in the edit form
LIST_COLUMN_LABEL
lang_map
Header in the list
LIST_FILTER_LABEL
lang_map
Filter label in the list
ERROR_MESSAGE
lang_map
Error message
HELP_MESSAGE
lang_map
Help
USER_TYPE_OWNER
string
CLIENT_ID
of the application that serves this field type.
Returned when the field type is custom
Parameter settings
Parameter settings
double
boolean
date
integer
datetime
string
enumeration
iblock_section|iblock_element
crm_status
crm
money
address
url
file
Name
type
Description
PRECISION
integer
Precision (number of decimal places)
SIZE
integer
Input field size for display
MIN_VALUE
double
Minimum value (0 — do not check)
MAX_VALUE
double
Maximum value (0 — do not check)
DEFAULT_VALUE
double
Default value
Name
type
Description
DEFAULT_VALUE
integer
Indicates whether it is the default value. Possible values:
0
— no
1
— yes
DISPLAY
string
Appearance. Possible values:
CHECKBOX
— checkbox
RADIO
— radio buttons
DROPDOWN
— dropdown list
LABEL
string[]
Labels for values, where:
array element with index
0
— label for value
No
array element with index
1
— label for value
Yes
LABEL_CHECKBOX
string
Checkbox label
Name
type
Description
DEFAULT_VALUE
object
Default value. Object format:
{
TYPE: 'NONE'|'FIXED'|'NONE',
VALUE: date
}
where:
TYPE
— type of default value:
NONE
— absent
NOW
— current date
FIXED
— date from the
VALUE
VALUE
is of type
date
Name
type
Description
SIZE
integer
Input field size for display
MIN_VALUE
integer
Minimum value (0 — do not check)
MAX_VALUE
integer
Maximum value (0 — do not check)
DEFAULT_VALUE
integer
Default value
Name
type
Description
DEFAULT_VALUE
object
Default value. Object format:
{
TYPE: 'NONE'|'FIXED'|'NONE',
VALUE: datetime
}
where:
TYPE
— type of default value:
NONE
— absent
NOW
— current date with time
FIXED
— date with time from the
VALUE
VALUE
is of type
datetime
USE_SECOND
boolean
Whether to use seconds. Possible values:
Y
— yes
N
— no
USE_TIMEZONE
boolean
Whether to use time zones. Possible values:
Y
— yes
N
— no
Name
type
Description
SIZE
integer
Input field size for display
ROWS
integer
Number of lines in the input field
REGEXP
string
Regular expression for validation
MIN_LENGTH
integer
Minimum string length (0 — do not check)
MAX_LENGTH
integer
Maximum string length (0 — do not check)
DEFAULT_VALUE
string
Default value
Name
type
Description
DISPLAY
string
Appearance. Possible values:
LIST
— list
CHECKBOX
— checkboxes
UI
— input list
DIALOG
— entity selection dialog
LIST_HEIGHT
integer
List height
CAPTION_NO_VALUE
string
Label when no value is present
SHOW_NO_VALUE
boolean
Whether to show empty value for mandatory field. Possible values:
Y
— yes
N
— no
Name
type
Description
DISPLAY
string
Appearance. Possible values:
LIST
— list
CHECKBOX
— checkboxes
UI
— input list
DIALOG
— entity selection dialog
LIST_HEIGHT
integer
List height
IBLOCK_ID
integer
Identifier of the information block
DEFAULT_VALUE
integer
Default value
ACTIVE_FILTER
boolean
Show only active elements. Possible values:
Y
— yes
N
— no
Name
type
Description
ENTITY_TYPE
object
CRM directory. Structure is similar to the returned elements of the method
crm.status.entity.types
Name
type
Description
LEAD
boolean
Whether binding to Leads is enabled
CONTACT
boolean
Whether binding to Contacts is enabled
COMPANY
boolean
Whether binding to Companies is enabled
DEAL
boolean
Whether binding to Deals is enabled
ORDER
boolean
Whether binding to Orders is enabled
QUOTE
boolean
Whether binding to Estimates is enabled
SMART_INVOICE
boolean
Whether binding to New Invoices is enabled
DYNAMIC_...
boolean
Whether binding to a specific SPA is enabled.
Each such field has the form:
DYNAMIC_{entityTypeId}
, where
entityTypeId
is the identifier of the type of SPA to which the binding is enabled
Name
type
Description
DEFAULT_VALUE
string
Default value.
The value of this field has the format:
{VALUE}\|{CURRENCY}
, where:
VALUE
— default amount of money
CURRENCY
— string identifier of the currency
For example:
300\|USD
— 300 dollars
Name
type
Description
SHOW_MAP
boolean
Show map
Name
type
Description
POPUP
boolean
Open in a new window
SIZE
integer
Input field size for display
MIN_LENGTH
integer
Minimum string length (0 — do not check)
MAX_LENGTH
integer
Maximum string length (0 — do not check)
DEFAULT_VALUE
string
Default value
ROWS
integer
Number of lines in the input field
Name
type
Description
SIZE
integer
Input field size for display
LIST_WIDTH
integer
Maximum width for display in the list
LIST_HEIGHT
integer
Maximum height for display in the list
MAX_SHOW_SIZE
integer
Maximum allowed size for display in the list (0 — no limit)
MAX_ALLOWED_SIZE
integer
Maximum allowed file size for upload (0 — do not check)
EXTENSIONS
string[]
Allowed extensions
TARGET_BLANK
boolean
Open file in a new tab
Type uf_enum_element
Type uf_enum_element
Name
type
Description
ID
integer
Identifier of the list element
VALUE
string
Value of the list element
SORT
integer
Sort index
DEF
boolean
Indicates whether the list element is the default value. Possible values:
Y
— yes
N
— no
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
Access denied
Occurs when:
the user does not have administrative rights
the user attempts to access a custom field not linked to contacts
-
ID is not defined or invalid
The provided
id
is less than or equal to zero, or is not provided at all
ERROR_NOT_FOUND
The entity with ID 'id' is not found
The custom field with the provided
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
Create a Custom Field for Contacts crm.contact.userfield.add
Update Existing Custom Contact Field crm.contact.userfield.update
Get a list of custom fields for contacts crm.contact.userfield.list
Delete Custom Contact Field crm.contact.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Modify an Existing Custom Field for Contacts
Next
Get a List of Custom Fields for Contacts

---

## Get a list of custom fields for contacts crm.contact.userfield.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/crm-contact-userfield-list

Get a list of custom fields for contacts crm.contact.userfield.list | Bitrix24 REST API and Marketplace Applications
Get a list of custom fields for contacts crm.contact.userfield.list
Get a list of custom fields for contacts crm.contact.userfield.list
Method Parameters
Available Fields for Filtering
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
crm.contact.userfield.list
returns a list of custom fields for contacts based on a filter.
It also outputs information about these fields, but without the name assigned to the field by the user, only the internal identifier. If you need the user-defined field name, use the method
crm.contact.list
, which outputs both standard and custom fields.
Method Parameters
Method Parameters
Name
type
Description
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
— the name of the field by which the selection of custom fields will be filtered
value_n
— the filter value (only exact matches are available)
All conditions for individual fields are combined using
AND
. See the
list of available fields for filtering
below
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
— the name of the field by which the selection of elements will be sorted
value_n
— a
string
value equal to:
ASC
— ascending sort
DESC
— descending sort
Available fields for sorting:
ID
— identifier of the custom field
FIELD_NAME
— code of the custom field
USER_TYPE_ID
— type of the custom field
XML_ID
— external code
SORT
— sort index
By default:
{
"SORT"
:
"ASC"
,
"ID"
:
"ASC"
}
Available Fields for Filtering
Available Fields for Filtering
Name
type
Description
ID
integer
Identifier of the custom field
FIELD_NAME
string
Code of the custom field
USER_TYPE_ID
string
Type of the custom field. Possible values:
string
— string
integer
— integer
double
— number
boolean
— yes/no
datetime
— date/time
date
— date
money
— money
url
— link
address
— address
enumeration
— list
file
— file
employee
— binding to an employee
crm_status
— binding to the CRM directory
iblock_section
— binding to information block sections
iblock_element
— binding to information block elements
crm
— binding to CRM elements
custom field types
XML_ID
string
External code
SORT
integer
Sort index
MULTIPLE
boolean
Is the custom field multiple (
Y
— yes /
N
— no)
MANDATORY
boolean
Is the custom field mandatory (
Y
— yes /
N
— no)
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
boolean
Show in the list (
Y
— yes /
N
— no).
This parameter does not affect anything within
crm
EDIT_IN_LIST
boolean
Allow user editing (
Y
— yes /
N
— no)
IS_SEARCHABLE
boolean
Are field values included in the search (
Y
— yes /
N
— no)
This parameter does not affect anything within
crm
LANG
string
Language identifier
. When filtering by this parameter, a set of fields with values in the provided language will be returned:
EDIT_FORM_LABEL
— label in the edit form
LIST_COLUMN_LABEL
— header in the list
LIST_FILTER_LABEL
— filter label in the list
ERROR_MESSAGE
— error message
HELP_MESSAGE
— help
Code Examples
Code Examples
How to Use Examples in Documentation
Get a list of custom fields that:
are multiple
are mandatory
have custom field labels in German
Set the following sort order for this selection: field type and sort index in ascending order.
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
'{"filter":{"MULTIPLE":"Y","MANDATORY":"Y","LANG":"de"},"order":{"USER_TYPE_ID":"ASC","SORT":"ASC"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.userfield.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"filter":{"MULTIPLE":"Y","MANDATORY":"Y","LANG":"de"},"order":{"USER_TYPE_ID":"ASC","SORT":"ASC"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.userfield.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.contact.userfield.list'
,
{
filter
: {
MULTIPLE
:
"Y"
,
MANDATORY
:
"Y"
,
LANG
:
"de"
,
},
order
: {
USER_TYPE_ID
:
"ASC"
,
SORT
:
"ASC"
,
},
},
(
progress
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.contact.userfield.list'
, {
filter
: {
MULTIPLE
:
"Y"
,
MANDATORY
:
"Y"
,
LANG
:
"de"
,
},
order
: {
USER_TYPE_ID
:
"ASC"
,
SORT
:
"ASC"
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.userfield.list'
, {
filter
: {
MULTIPLE
:
"Y"
,
MANDATORY
:
"Y"
,
LANG
:
"de"
,
},
order
: {
USER_TYPE_ID
:
"ASC"
,
SORT
:
"ASC"
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
'crm.contact.userfield.list'
,
[
'filter'
=> [
'MULTIPLE'
=>
'Y'
,
'MANDATORY'
=>
'Y'
,
'LANG'
=>
'de'
,
],
'order'
=> [
'USER_TYPE_ID'
=>
'ASC'
,
'SORT'
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
'Error fetching user fields: '
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
'crm.contact.userfield.list'
,
{
filter
: {
MULTIPLE
:
"Y"
,
MANDATORY
:
"Y"
,
LANG
:
"de"
,
},
order
: {
USER_TYPE_ID
:
"ASC"
,
SORT
:
"ASC"
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
'crm.contact.userfield.list'
,
[
'filter'
=> [
'MULTIPLE'
=>
"Y"
,
'MANDATORY'
=>
"Y"
,
'LANG'
=>
"de"
,
],
'order'
=> [
'USER_TYPE_ID'
=>
"ASC"
,
'SORT'
=>
"ASC"
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
"474"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724412832"
,
"USER_TYPE_ID"
:
"address"
,
"XML_ID"
:
null
,
"SORT"
:
"300"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"Y"
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
"SHOW_MAP"
:
"Y"
}
,
"EDIT_FORM_LABEL"
:
"Custom Field (Address)"
,
"LIST_COLUMN_LABEL"
:
"Custom Field (Address)"
,
"LIST_FILTER_LABEL"
:
"Custom Field (Address)"
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
"475"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724412867"
,
"USER_TYPE_ID"
:
"crm"
,
"XML_ID"
:
null
,
"SORT"
:
"1400"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"Y"
,
"SHOW_FILTER"
:
"I"
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
"CONTACT"
:
"Y"
,
"COMPANY"
:
"Y"
,
"DYNAMIC_1224"
:
"Y"
,
"DYNAMIC_1226"
:
"Y"
,
"DYNAMIC_1268"
:
"Y"
,
"DYNAMIC_1278"
:
"Y"
,
"LEAD"
:
null
}
,
"EDIT_FORM_LABEL"
:
"Custom Field (Binding to CRM Elements)"
,
"LIST_COLUMN_LABEL"
:
"Custom Field (Binding to CRM Elements)"
,
"LIST_FILTER_LABEL"
:
"Custom Field (Binding to CRM Elements)"
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
"472"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724412764"
,
"USER_TYPE_ID"
:
"date"
,
"XML_ID"
:
null
,
"SORT"
:
"2000"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"Y"
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
"VALUE"
:
"2024-08-22"
,
"TYPE"
:
"FIXED"
}
}
,
"EDIT_FORM_LABEL"
:
"Custom Field (Date)"
,
"LIST_COLUMN_LABEL"
:
"Custom Field (Date)"
,
"LIST_FILTER_LABEL"
:
"Custom Field (Date)"
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
"471"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724412713"
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
"1500"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"Y"
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
150
}
,
"EDIT_FORM_LABEL"
:
"Custom Field (Number)"
,
"LIST_COLUMN_LABEL"
:
"Custom Field (Number)"
,
"LIST_FILTER_LABEL"
:
"Custom Field (Number)"
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
"473"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724412805"
,
"USER_TYPE_ID"
:
"employee"
,
"XML_ID"
:
null
,
"SORT"
:
"800"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"Y"
,
"SHOW_FILTER"
:
"I"
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
[
]
,
"EDIT_FORM_LABEL"
:
"Custom Field (Employee)"
,
"LIST_COLUMN_LABEL"
:
"Custom Field (Employee)"
,
"LIST_FILTER_LABEL"
:
"Custom Field (Employee)"
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
"476"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724412914"
,
"USER_TYPE_ID"
:
"file"
,
"XML_ID"
:
null
,
"SORT"
:
"1200"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"Y"
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
"LIST_WIDTH"
:
0
,
"LIST_HEIGHT"
:
0
,
"MAX_SHOW_SIZE"
:
0
,
"MAX_ALLOWED_SIZE"
:
0
,
"EXTENSIONS"
:
[
]
,
"TARGET_BLANK"
:
"Y"
}
,
"EDIT_FORM_LABEL"
:
"Custom Field (File)"
,
"LIST_COLUMN_LABEL"
:
"Custom Field (File)"
,
"LIST_FILTER_LABEL"
:
"Custom Field (File)"
,
"ERROR_MESSAGE"
:
null
,
"HELP_MESSAGE"
:
null
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
1724435524.016968
,
"finish"
:
1724435527.855702
,
"duration"
:
3.8387339115142822
,
"processing"
:
0.366832971572876
,
"date_start"
:
"2024-08-23T19:52:04+02:00"
,
"date_finish"
:
"2024-08-23T19:52:07+02:00"
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
userfield[]
Root element of the response, contains a list of custom fields.
The structure of an individual custom field is identical to
userfield
except that the fields:
EDIT_FORM_LABEL
,
LIST_COLUMN_LABEL
,
LIST_FILTER_LABEL
,
ERROR_MESSAGE
,
HELP_MESSAGE
are returned either as
string
when passing
filter.LANG
, or are not returned at all
total
integer
Number of found custom fields
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
Parameter 'order' must be array
The provided
order
is not an object
-
Parameter 'filter' must be array
The provided
filter
is not an object
-
Access denied
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
Create a Custom Field for Contacts crm.contact.userfield.add
Update Existing Custom Contact Field crm.contact.userfield.update
Get Custom Contact Field by Id crm.contact.userfield.get
Delete Custom Contact Field crm.contact.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Retrieve a Custom Field for Contacts by Id
Next
Delete a Custom Field for Contacts

---

## Delete Custom Contact Field crm.contact.userfield.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/crm-contact-userfield-delete

Delete Custom Contact Field crm.contact.userfield.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Custom Contact Field crm.contact.userfield.delete
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
crm.contact.userfield.delete
removes a custom contact field.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the custom field associated with the contact.
The identifier can be obtained using the methods
crm.contact.userfield.add
or
crm.contact.userfield.list
Code Examples
Code Examples
How to Use Examples in Documentation
Delete the custom field with
id = 432
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
'{"id":432}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.contact.userfield.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":432,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.contact.userfield.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.contact.userfield.delete'
,
{
id
:
432
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
$userfieldId
=
123
;
// Replace with the actual userfield ID you want to delete
$result
=
$serviceBuilder
->
getCRMScope
()
->
contactUserfield
()
->
delete
(
$userfieldId
);
if
(
$result
->
isSuccess
()) {
print
(
"Deleted item successfully."
);
}
else
{
print
(
"Failed to delete item."
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
BX24
.
callMethod
(
'crm.contact.userfield.delete'
,
{
id
:
432
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
'crm.contact.userfield.delete'
,
[
'id'
=>
432
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
1724316817.995457
,
"finish"
:
1724316818.640754
,
"duration"
:
0.6452970504760742
,
"processing"
:
0.3215677738189697
,
"date_start"
:
"2024-08-22T10:53:37+02:00"
,
"date_finish"
:
"2024-08-22T10:53:38+02:00"
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
ID is not defined or invalid
The provided
id
is either less than or equal to zero, or not provided at all
-
Access denied
Occurs when:
the user does not have administrative rights
the user attempts to delete a custom field not associated with contacts
ERROR_NOT_FOUND
The entity with ID 'id' is not found
The custom field with the provided
id
does not exist
-
Error deleting
FIELD_NAME
for object
ENTITY_ID
Unknown error during deletion
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
Create a Custom Field for Contacts crm.contact.userfield.add
Update Existing Custom Contact Field crm.contact.userfield.update
Get Custom Contact Field by Id crm.contact.userfield.get
Get a list of custom fields for contacts crm.contact.userfield.list
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Custom Fields for Contacts
Next
Overview of Events

---

## Overview of Events When Working with Custom Contact Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/events/index

Overview of Events When Working with Custom Contact Fields | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Custom Contact Fields
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, updating, or deletion of custom contact fields.
Detailed information on working with events is described in the article
Concept and Benefits of Event Handling
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to events for custom contact fields through:
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
Triggered
onCrmContactUserFieldAdd
When a custom field is added manually or via the method
crm.contact.userfield.add
onCrmContactUserFieldUpdate
When a custom field is changed manually or via the method
crm.contact.userfield.update
onCrmContactUserFieldDelete
When a custom field is deleted manually or via the method
crm.contact.userfield.delete
onCrmContactUserFieldSetEnumValues
When the set of values for a list-type custom field is changed manually or via the method
crm.contact.userfield.update
Copied
Was the article helpful?
Yes
No
Previous
Delete a Custom Field for Contacts
Next
When Adding a Custom Field

---

## Event onCrmContactUserFieldAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/events/on-crm-contact-user-field-add

Event onCrmContactUserFieldAdd | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmContactUserFieldAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
onCrmContactUserFieldAdd
is triggered when a custom field is added to a contact.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMCONTACTUSERFIELDADD"
,
"event_handler_id"
:
"14"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"553"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724770216"
}
}
,
"ts"
:
"1724770216"
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
ONCRMCONTACTUSERFIELDADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created custom field.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created custom field.
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
Identifier of the created custom field
ENTITY_ID
userFieldEntityId
Type of CRM object to which the custom field is attached.
In this case —
CRM_CONTACT
FIELD_NAME
string
Code of the created custom field
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
Overview of Events When Working with Custom Contact Fields
Event onCrmContactUserFieldUpdate
Event on changing the set of values for a custom list-type field onCrmContactUserFieldSetEnumValues
Event onCrmContactUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Updating a Custom Field

---

## Event onCrmContactUserFieldUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/events/on-crm-contact-user-field-update

Event onCrmContactUserFieldUpdate | Bitrix24 REST API and Marketplace Applications
Event onCrmContactUserFieldUpdate
Event onCrmContactUserFieldUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
onCrmContactUserFieldUpdate
is triggered when a custom field is changed for contacts.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMCONTACTUSERFIELDUPDATE"
,
"event_handler_id"
:
"15"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"554"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724771514"
}
}
,
"ts"
:
"1724775198"
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
ONCRMCONTACTUSERFIELDUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the changed custom field
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the changed custom field
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
Identifier of the changed custom field
ENTITY_ID
userFieldEntityId
Type of CRM object to which the custom field is attached.
In this case —
CRM_CONTACT
FIELD_NAME
string
Code of the changed custom field
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
Overview of Events When Working with Custom Contact Fields
Event onCrmContactUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmContactUserFieldSetEnumValues
Event onCrmContactUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
When Adding a Custom Field
Next
When Changing the Set of Values for a List-Type Custom Field

---

## Event on changing the set of values for a custom list-type field onCrmContactUserFieldSetEnumValues

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/events/on-crm-contact-user-field-set-enum-values

Event on changing the set of values for a custom list-type field onCrmContactUserFieldSetEnumValues | Bitrix24 REST API and Marketplace Applications
Event on changing the set of values for a custom list-type field onCrmContactUserFieldSetEnumValues
Event on changing the set of values for a custom list-type field onCrmContactUserFieldSetEnumValues
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
onCrmContactUserFieldSetEnumValues
is triggered when the set of values for a custom list-type field on contacts is changed.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMCONTACTUSERFIELDSETENUMVALUES"
,
"event_handler_id"
:
"17"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"554"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724771514"
}
}
,
"ts"
:
"1724771547"
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
ONCRMCONTACTUSERFIELDSETENUMVALUES
event_handler_id
integer
Event handler identifier
data
object
Object containing information about the custom field whose list of possible values has changed.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the custom field whose list of possible values has changed.
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
Identifier of the custom field whose list of possible values has changed
ENTITY_ID
userFieldEntityId
Type of CRM object to which the custom field is linked.
In this case —
CRM_CONTACT
FIELD_NAME
string
Code of the custom field whose list of possible values has changed
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
Overview of Events When Working with Custom Contact Fields
Event onCrmContactUserFieldAdd
Event onCrmContactUserFieldUpdate
Event onCrmContactUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
When Updating a Custom Field
Next
When Deleting a Custom Field

---

## Event onCrmContactUserFieldDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/contacts/userfield/events/on-crm-contact-user-field-delete

Event onCrmContactUserFieldDelete | Bitrix24 REST API and Marketplace Applications
Event onCrmContactUserFieldDelete
Event onCrmContactUserFieldDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
onCrmContactUserFieldDelete
is triggered when a custom field is deleted from a contact.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMCONTACTUSERFIELDDELETE"
,
"event_handler_id"
:
"16"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"553"
,
"ENTITY_ID"
:
"CRM_CONTACT"
,
"FIELD_NAME"
:
"UF_CRM_1724770216"
}
}
,
"ts"
:
"1724771239"
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
ONCRMCONTACTUSERFIELDDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted custom field.
Contains a single key
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
Identifier of the deleted custom field
ENTITY_ID
userFieldEntityId
Type of CRM object to which the custom field is attached.
In this case —
CRM_CONTACT
FIELD_NAME
string
Code of the deleted custom field
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
Overview of Events When Working with Custom Contact Fields
Event onCrmContactUserFieldAdd
Event onCrmContactUserFieldUpdate
Event on changing the set of values for a custom list-type field onCrmContactUserFieldSetEnumValues
Copied
Was the article helpful?
Yes
No
Previous
When Changing the Set of Values for a List-Type Custom Field
Next
Overview of Events

---

