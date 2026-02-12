---
description: 'CRM Quotes/Estimates API: CRUD operations, fields, events'
methods:
- crm.activity.
- crm.item.productrow.
- crm.productrow.fields
- crm.quote.add
- crm.quote.delete
- crm.quote.fields
- crm.quote.get
- crm.quote.list
- crm.quote.productrows.get
- crm.quote.productrows.set
- crm.quote.update
- crm.quote.userfield.
- crm.quote.userfield.add
- crm.quote.userfield.delete
- crm.quote.userfield.get
- crm.quote.userfield.list
- crm.quote.userfield.update
- crm.requisite.link.register
- crm.status.list
- crm.timeline.
- crm.userfield.fields
- crm.userfield.settings.fields
- crm.userfield.types
- event.bind
pages: 24
title: 'CRM Quotes/Estimates API: CRUD operations, fields, events'
---
# CRM Quotes/Estimates API: CRUD operations, fields, events
> CRM Quotes/Estimates API: CRUD operations, fields, events
> **24 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Estimates in CRM: Overview of Methods](#estimates-in-crm-overview-of-methods)
- [Add estimate crm.quote.add](#add-estimate-crmquoteadd)
- [Delete estimate crm.quote.delete](#delete-estimate-crmquotedelete)
- [Get Fields of the Estimate crm.quote.fields](#get-fields-of-the-estimate-crmquotefields)
- [Get an estimate by ID crm.quote.get](#get-an-estimate-by-id-crmquoteget)
- [Get a list of estimates by filter crm.quote.list](#get-a-list-of-estimates-by-filter-crmquotelist)
- [Update the estimate crm.quote.update](#update-the-estimate-crmquoteupdate)
- [Get product rows of the quote crm.quote.productrows.get](#get-product-rows-of-the-quote-crmquoteproductrowsg)
- [Create/Update Product Items in crm.quote.productrows.set](#createupdate-product-items-in-crmquoteproductrowss)
- [Custom Fields for Estimates: Overview of Methods](#custom-fields-for-estimates-overview-of-methods)
- [Create a custom field for estimates crm.quote.userfield.add](#create-a-custom-field-for-estimates-crmquoteuserfi)
- [Delete Custom Field for Quotes crm.quote.userfield.delete](#delete-custom-field-for-quotes-crmquoteuserfieldde)
- [Get Custom Fields of Quotes by ID crm.quote.userfield.get](#get-custom-fields-of-quotes-by-id-crmquoteuserfiel)
- [Get a list of custom fields for estimates by filter crm.quote.userfield.list](#get-a-list-of-custom-fields-for-estimates-by-filte)
- [Update Custom Field for Quotes crm.quote.userfield.update](#update-custom-field-for-quotes-crmquoteuserfieldup)
- [Overview of Events When Working with Custom Fields in Estimates](#overview-of-events-when-working-with-custom-fields)
- [When Adding a Custom Field onCrmQuoteUserFieldAdd](#when-adding-a-custom-field-oncrmquoteuserfieldadd)
- [When updating a custom field onCrmQuoteUserFieldUpdate](#when-updating-a-custom-field-oncrmquoteuserfieldup)
- [When Deleting a Custom Field onCrmQuoteUserFieldDelete](#when-deleting-a-custom-field-oncrmquoteuserfieldde)
- [When setting list values for the custom field onCrmQuoteUserFieldSetEnumValues](#when-setting-list-values-for-the-custom-field-oncr)
- [Overview of Events When Working with Estimates](#overview-of-events-when-working-with-estimates)
- [Event when adding an estimate onCrmQuoteAdd](#event-when-adding-an-estimate-oncrmquoteadd)
- [Event on updating the estimate onCrmQuoteUpdate](#event-on-updating-the-estimate-oncrmquoteupdate)
- [Event on deleting an estimate onCrmQuoteDelete](#event-on-deleting-an-estimate-oncrmquotedelete)

---

## Estimates in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/index

Estimates in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Connection of Estimates with Other CRM Entities
Estimates in CRM: Overview of Methods
Connection of Estimates with Other CRM Entities
Estimate Detail Form
Widgets
Overview of Methods and Events
Main
Custom Fields
An estimate is a CRM entity that allows you to create printed documents and send them to clients before a deal.
Quick navigation:
all methods and events
User documentation:
estimates in Bitrix24
Connection of Estimates with Other CRM Entities
Connection of Estimates with Other CRM Entities
Deal.
An estimate can be created based on a deal and vice versa. The connection is established in the estimate field
DEAL_ID
.
Products.
Adding, modifying, and deleting product items in estimates can be done through the group of methods
crm.item.productrow.*
.
Details.
Buyer details are pulled into the estimate form from the associated contact or company. Seller details are pulled from the field
MYCOMPANY_ID
.
Client.
This field in the estimate detail form consists of the associated company and contacts. There is one company in the field, and it is accessed directly through the field
COMPANY_ID
. Multiple contacts can be specified, and their modification is done through an array of data in the multiple field
CONTACT_IDS
.
User Documentation
How to add products to deals, leads, and estimates
How to use your company details
Estimate Detail Form
Estimate Detail Form
The main workspace in an estimate is the General tab of its detail form. It consists of two parts:
The left part contains fields with information. If the system fields are insufficient, you can create your own custom fields. They allow you to store information in various data formats: string, number, link, address, and others. To create, modify, retrieve, or delete custom fields for estimates, the group of methods
crm.quote.userfield.*
is used.
The right part contains the estimate timeline. In it, you can create, edit, filter, and delete CRM activities — the group of methods
crm.activity.*
, and timeline records — the group of methods
crm.timeline.*
.
User Documentation
CRM Detail Form: Features and Settings
System Fields in CRM
Custom Fields in CRM
Timeline in CRM Entity
Widgets
Widgets
You can embed an application into the estimate detail form. This allows you to use the application without leaving the estimate detail form.
There are two embedding scenarios:
Use special
embedding locations
. For example, by creating your own tab.
Create a
custom field
where the content of your application will be loaded.
Typical use-cases and scenarios
Widget Embedding Mechanism
Embed a Widget in a CRM Detail Form
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can execute the method: any user
Main
Main
Methods
Events
Method
Description
crm.quote.add
Creates a new estimate
crm.quote.update
Modifies an existing estimate
crm.quote.get
Returns an estimate by ID
crm.quote.list
Returns a list of estimates by filter
crm.quote.delete
Deletes an estimate and all related objects
crm.quote.fields
Returns the description of estimate fields
crm.quote.productrows.get
Returns the product items of the estimate
crm.quote.productrows.set
Sets (creates or updates) the product items of the estimate
Event
Triggered
onCrmQuoteAdd
When an estimate is created
onCrmQuoteUpdate
When an estimate is updated
onCrmQuoteDelete
When an estimate is deleted
Custom Fields
Custom Fields
Methods
Events
Method
Description
crm.quote.userfield.add
Creates a new custom field for estimates
crm.quote.userfield.update
Updates an existing custom field for estimates
crm.quote.userfield.get
Returns a custom field for estimates by ID
crm.quote.userfield.list
Returns a list of custom fields for estimates by filter
crm.quote.userfield.delete
Deletes a custom field for estimates
Event
Triggered
onCrmQuoteUserFieldAdd
When a custom field is added
onCrmQuoteUserFieldUpdate
When a custom field is modified
onCrmQuoteUserFieldDelete
When a custom field is deleted
onCrmQuoteUserFieldSetEnumValues
When the set of values for a custom field of list type is changed
Copied
Was the article helpful?
Yes
No
Previous
Set Common Card for All Users
Next
Add estimate

---

## Add estimate crm.quote.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/crm-quote-add

Add estimate crm.quote.add | Bitrix24 REST API and Marketplace Applications
Add estimate crm.quote.add
Add estimate crm.quote.add
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.add
creates a new estimate. If you need to specify any details of the buyer/seller in the estimate (since there may be several for a company), use the method
crm.requisite.link.register
.
The created estimate must include the seller and buyer companies:
COMPANY_ID
, if the buyer is a company or
CONTACT_ID
, if the buyer is a contact.
MYCOMPANY_ID
- seller.
The identifiers specified in
crm.requisite.link.register
and in the created estimate must correspond to the buyer and seller.
Parameter
/
Type
Description
fields
unknown
Set of fields - an array of the form
array("field"=>"value"[, ...])
, containing the values of the estimate fields, where "field" can take values returned by the method
crm.quote.fields
.
Note
To find out the required format of the fields, execute the method
crm.quote.fields
and check the format of the returned values for these fields.
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
"crm.quote.add"
,
{
fields
:
{
"TITLE"
:
"Draft"
,
"STATUS_ID"
:
"DRAFT"
,
"OPENED"
:
"Y"
,
"ASSIGNED_BY_ID"
:
1
,
"CURRENCY_ID"
:
"USD"
,
"OPPORTUNITY"
:
5000
,
"COMPANY_ID"
:
1
,
"COMMENTS"
:
"New estimate."
,
"BEGINDATE"
:
"2016-03-01T12:00:00"
,
"CLOSEDATE"
:
"2016-04-01T12:00:00"
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
"Estimate created with ID "
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
'crm.quote.add'
,
[
'fields'
=> [
'TITLE'
=>
'Draft'
,
'STATUS_ID'
=>
'DRAFT'
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
5000
,
'COMPANY_ID'
=>
1
,
'COMMENTS'
=>
'New estimate.'
,
'BEGINDATE'
=>
'2016-03-01T12:00:00'
,
'CLOSEDATE'
=>
'2016-04-01T12:00:00'
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
'Estimate created with ID '
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
'Error creating quote: '
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
"crm.quote.add"
,
{
fields
:
{
"TITLE"
:
"Draft"
,
"STATUS_ID"
:
"DRAFT"
,
"OPENED"
:
"Y"
,
"ASSIGNED_BY_ID"
:
1
,
"CURRENCY_ID"
:
"USD"
,
"OPPORTUNITY"
:
5000
,
"COMPANY_ID"
:
1
,
"COMMENTS"
:
"New estimate."
,
"BEGINDATE"
:
"2016-03-01T12:00:00"
,
"CLOSEDATE"
:
"2016-04-01T12:00:00"
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
"Estimate created with ID "
+ result.
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
Overview of methods
Next
Delete estimate

---

## Delete estimate crm.quote.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/crm-quote-delete

Delete estimate crm.quote.delete | Bitrix24 REST API and Marketplace Applications
Delete estimate crm.quote.delete
Delete estimate crm.quote.delete
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm
Who can perform the method: any user
The method
crm.quote.delete
deletes an
estimate
and all related objects.
Parameter
/
Type
Description
id
unknown
Identifier of the estimate.
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
"crm.quote.delete"
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
'crm.quote.delete'
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
'Error deleting estimate: '
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
"crm.quote.delete"
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
Add estimate
Next
Get estimate fields

---

## Get Fields of the Estimate crm.quote.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/crm-quote-fields

Get Fields of the Estimate crm.quote.fields | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Fields of the Estimate crm.quote.fields
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
crm.quote.fields
returns the description of the fields of the estimate, including custom fields.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.quote.fields
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
https://**put_your_bitrix24_address**/rest/crm.quote.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.quote.fields"
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
'crm.quote.fields'
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
'Error fetching quote fields: '
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
"crm.quote.fields"
,
{},
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
dir
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
'crm.quote.fields'
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
"QUOTE_NUMBER"
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
"Estimate Number"
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
"Subject"
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
"QUOTE_STATUS"
,
"title"
:
"Estimate Stage"
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
}
,
"MYCOMPANY_ID"
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
"Your Company Details"
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
"Issue Date"
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
"Deadline"
}
,
"ACTUAL_DATE"
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
"ACTUAL_DATE"
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
"Available to Everyone"
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
"CONTENT"
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
"Content"
}
,
"TERMS"
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
"Terms"
}
,
"CLIENT_TITLE"
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
"Client"
}
,
"CLIENT_ADDR"
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
"CLIENT_CONTACT"
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
"CLIENT_EMAIL"
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
"E-mail"
}
,
"CLIENT_PHONE"
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
"CLIENT_TP_ID"
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
"Tax ID"
}
,
"CLIENT_TPA_ID"
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
"Lead"
}
,
"DEAL_ID"
:
{
"type"
:
"crm_deal"
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
"Deal"
}
,
"PERSON_TYPE_ID"
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
"Client Type"
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
"LAST_COMMUNICATION_TIME"
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
"LAST_COMMUNICATION_TIME"
}
,
"UF_CRM_6710EFCBAF22C"
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
true
,
"title"
:
"UF_CRM_6710EFCBAF22C"
,
"listLabel"
:
"End of RK"
,
"formLabel"
:
"End of RK"
,
"filterLabel"
:
"End of RK"
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
}
}
}
,
"time"
:
{
"start"
:
1750416943.169864
,
"finish"
:
1750416943.26074
,
"duration"
:
0.09087610244750977
,
"processing"
:
0.05633091926574707
,
"date_start"
:
"2025-06-20T13:55:43+02:00"
,
"date_finish"
:
"2025-06-20T13:55:43+02:00"
,
"operating_reset_at"
:
1750417543
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
Object with the description of the fields of the estimate in the format
crm_rest_field_description
time
time
Information about the execution time of the request
Main Fields
Main Fields
Name
type
Description
ASSIGNED_BY_ID
integer
Responsible
BEGINDATE
date
Issue date of the estimate
CLOSED
char
Flag for completion of the estimate
CLOSEDATE
date
Completion date of the estimate
COMMENTS
string
Comment
COMPANY_ID
integer
Identifier of the company associated with the estimate
CONTACT_IDS
integer
Identifiers of contacts associated with the estimate. Multiple
CONTENT
string
Content of the estimate
CREATED_BY_ID
integer
Identifier of the user who created the estimate. Read-only
CURRENCY_ID
crm_currency
Currency of the estimate
DATE_CREATE
datetime
Creation date of the estimate. Read-only
DATE_MODIFY
datetime
Modification date of the estimate. Read-only
DEAL_ID
integer
Identifier of the deal associated with the estimate
ID
integer
Identifier of the estimate. Read-only
LEAD_ID
integer
Identifier of the lead associated with the estimate
LOCATION_ID
integer
Client's location
MODIFY_BY_ID
integer
Identifier of the user who modified the estimate. Read-only
MYCOMPANY_ID
integer
Identifier of the company making the estimate
OPENED
char
Flag for availability of the estimate to everyone
OPPORTUNITY
double
Amount of the estimate
PERSON_TYPE_ID
integer
Payer type
QUOTE_NUMBER
string
Estimate number. Read-only
STATUS_ID
crm_status
Stage of the estimate. You can get the values of the directory using the method
crm.status.list
with the filter
ENTITY_ID=QUOTE_STATUS
TAX_VALUE
double
Tax rate
TERMS
string
Terms of the estimate
TITLE
string
Title of the estimate
UTM_CAMPAIGN
string
dvertising campaign identifier
UTM_CONTENT
string
Content of the advertising campaign. For example, for contextual ads
UTM_MEDIUM
string
Traffic type. For example, CPC for ads or CPM for banners
UTM_SOURCE
string
Advertising system. For example, Google Ads
UTM_TERM
string
Campaign search condition. For example, keywords for contextual advertising
LAST_ACTIVITY_TIME
datetime
Time of the last activity. Read-only
LAST_ACTIVITY_BY
integer
Identifier of the user who performed the last activity. Read-only
LAST_COMMUNICATION_TIME
string
Time of the last communication. Read-only
UF_...
Custom fields. For example,
UF_CRM_25534736
.
You can add a custom field to the estimate using the method
crm.quote.userfield.add
Deprecated Fields
Deprecated Fields
The following fields are kept only for compatibility and are not recommended for use.
Name
type
Description
CLIENT_ADDR
string
Client's address
CLIENT_CONTACT
string
Client's contact person
CLIENT_EMAIL
string
Client's email
CLIENT_PHONE
string
Client's phone
CLIENT_TITLE
string
Client's name
CLIENT_TP_ID
string
Client's Tax ID
CLIENT_TPA_ID
string
Client's KPP
CONTACT_ID
integer
Identifier of the contact associated with the estimate
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
Add estimate crm.quote.add
Get an estimate by ID crm.quote.get
Update the estimate crm.quote.update
Delete estimate crm.quote.delete
Create a custom field for estimates crm.quote.userfield.add
Copied
Was the article helpful?
Yes
No
Previous
Delete estimate
Next
Get estimate by ID

---

## Get an estimate by ID crm.quote.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/crm-quote-get

Get an estimate by ID crm.quote.get | Bitrix24 REST API and Marketplace Applications
Get an estimate by ID crm.quote.get
Get an estimate by ID crm.quote.get
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.get
returns an estimate by its ID.
Parameter
/
Type
Description
id
unknown
The ID of the estimate.
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
"crm.quote.get"
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
( error )
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
'crm.quote.get'
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
'Error getting quote: '
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
"crm.quote.get"
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
Get estimate fields
Next
Get list of estimates by filter

---

## Get a list of estimates by filter crm.quote.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/crm-quote-list

Get a list of estimates by filter crm.quote.list | Bitrix24 REST API and Marketplace Applications
Example
Get a list of estimates by filter crm.quote.list
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.list
returns a list of estimates by filter. It is an implementation of the list method for estimates.
See the description of
list methods
.
Example
Example
JS
PHP
BX24.js
// callListMethod is recommended when you need to retrieve the entire set of list data and the number of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.quote.list'
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
"=COMPANY_ID"
:
1
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
]
},
(
progress
) =>
{
if
(progress.
error
()) {
console
.
error
(progress.
error
());
}
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
()) {
progress.
next
();
}
}
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
try
{
const
generator = $b24.
fetchListMethod
(
'crm.quote.list'
, {
order
: {
"STATUS_ID"
:
"ASC"
},
filter
: {
"=COMPANY_ID"
:
1
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
] },
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
dir
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.quote.list'
, {
order
: {
"STATUS_ID"
:
"ASC"
},
filter
: {
"=COMPANY_ID"
:
1
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
] },
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
dir
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
'crm.quote.list'
,
[
'order'
=> [
'STATUS_ID'
=>
'ASC'
],
'filter'
=> [
'=COMPANY_ID'
=>
1
],
'select'
=> [
'ID'
,
'TITLE'
,
'STATUS_ID'
,
'OPPORTUNITY'
,
'CURRENCY_ID'
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
'Error fetching quote list: '
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
"crm.quote.list"
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
"=COMPANY_ID"
:
1
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
Copied
Was the article helpful?
Yes
No
Previous
Get estimate by ID
Next
Update estimate

---

## Update the estimate crm.quote.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/crm-quote-update

Update the estimate crm.quote.update | Bitrix24 REST API and Marketplace Applications
Update the estimate crm.quote.update
Update the estimate crm.quote.update
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.update
updates an existing estimate.
Parameter
/
Type
Description
id
unknown
Identifier of the estimate.
fields
unknown
Set of fields
- an array of the form
array("field_to_update"=>"value"[, ...])
, where "field_to_update" can take values returned by the method
crm.quote.fields
.
To find out the required format of the fields, execute the method
crm.quote.fields
and check the format of the returned values for these fields.
params
unknown
Set of parameters.
REGISTER_HISTORY_EVENT
- create a record in history, default value: "Y". Additionally, a notification will be sent to the person responsible for the estimate.
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
"crm.quote.update"
,
{
id
: id,
fields
: {
"STATUS_ID"
:
"SENT"
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
'crm.quote.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'STATUS_ID'
=>
'SENT'
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
'Error updating estimate: '
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
"crm.quote.update"
,
{
id
: id,
fields
: {
"STATUS_ID"
:
"SENT"
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
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get list of estimates by filter
Next
Get product items of the estimate

---

## Get product rows of the quote crm.quote.productrows.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/crm-quote-product-rows-get

Get product rows of the quote crm.quote.productrows.get | Bitrix24 REST API and Marketplace Applications
Get product rows of the quote crm.quote.productrows.get
Get product rows of the quote crm.quote.productrows.get
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.productrows.get
returns the product rows of the quote.
Parameter
/
Type
Description
id
unknown
Identifier of the quote.
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
"crm.quote.productrows.get"
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
'crm.quote.productrows.get'
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
'Error getting quote product rows: '
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
"crm.quote.productrows.get"
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
Update estimate
Next
Create/Update product items of the estimate

---

## Create/Update Product Items in crm.quote.productrows.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/crm-quote-product-rows-set

Create/Update Product Items in crm.quote.productrows.set | Bitrix24 REST API and Marketplace Applications
Create/Update Product Items in crm.quote.productrows.set
Create/Update Product Items in crm.quote.productrows.set
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.productrows.set
sets (creates or updates) the product items of the quote.
Parameter
/
Type
Description
id
unknown
Identifier of the quote.
rows
unknown
Product items - an array of the form
array(array("field"=>"value"[, ...])[, ...])
, where "field" can take values returned by the method
crm.productrow.fields
. The product items of the quote that exist before the method call will be replaced with the new ones. After saving, the total amount of the quote will be recalculated.
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
"crm.quote.productrows.set"
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
1
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
2
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
'crm.quote.productrows.set'
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
1
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
2
,
'PRICE'
=>
200.00
,
'QUANTITY'
=>
1
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
'Error setting quote product rows: '
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
"crm.quote.productrows.set"
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
1
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
2
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
Get product items of the estimate
Next
Overview of Methods

---

## Custom Fields for Estimates: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/index

Custom Fields for Estimates: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Types of Custom Fields
Custom Fields for Estimates: Overview of Methods
Types of Custom Fields
Custom Field Settings
Errors When Working with Custom Fields
Common Causes of Server Errors
Overview of Methods
Custom fields store information about an estimate in various data formats: string, number, link, address, and others.
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
[title] => Mandatory
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
You can create 1016 custom fields for estimates — this is a limitation of the database architecture. If there are already 1016 fields for estimates in Bitrix24, attempting to create a new field will result in the method
crm.quote.userfield.add
returning an error
INTERNAL_SERVER_ERROR
.
You can check the number of custom fields for estimates using the method
crm.quote.userfield.list
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
a custom field for an estimate depends on the number of estimates. When a field is created, it is added to all estimate detail forms. When a field is deleted, it is removed from all detail forms. The fewer estimates you have in your Bitrix24, the faster fields are created and deleted.
To check the number of estimates in Bitrix24, use the method
crm.quote.list
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: depending on the method
Methods
Events
Method
Description
crm.quote.userfield.add
Creates a new custom field for estimates
crm.quote.userfield.update
Updates an existing custom field for estimates
crm.quote.userfield.get
Returns a custom field for estimates by ID
crm.quote.userfield.list
Returns a list of custom fields for estimates by filter
crm.quote.userfield.delete
Deletes a custom field for estimates
Event
Triggered
onCrmQuoteUserFieldAdd
When a custom field is added
onCrmQuoteUserFieldUpdate
When a custom field is updated
onCrmQuoteUserFieldDelete
When a custom field is deleted
onCrmQuoteUserFieldSetEnumValues
When the set of values for a custom field of list type is changed
Copied
Was the article helpful?
Yes
No
Previous
Create/Update product items of the estimate
Next
Create a Custom Field for Estimates

---

## Create a custom field for estimates crm.quote.userfield.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/crm-quote-user-field-add

Create a custom field for estimates crm.quote.userfield.add | Bitrix24 REST API and Marketplace Applications
Create a custom field for estimates crm.quote.userfield.add
Create a custom field for estimates crm.quote.userfield.add
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.userfield.add
creates a new custom field for estimates.
The system limit for the field name is 20 characters. The custom field name always has the prefix
UF_CRM_
, meaning the actual length of the name is 13 characters.
Parameter
/
Type
Description
fields
unknown
A set of fields - an array of the form
array("field"=>"value"[, ...])
, containing the description of the custom field. A complete description of the fields can be obtained by calling the method
crm.userfield.fields
.
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
'crm.quote.userfield.add'
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
'crm.quote.userfield.add'
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
"crm.quote.userfield.add"
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
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Delete a Custom Field for Estimates

---

## Delete Custom Field for Quotes crm.quote.userfield.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/crm-quote-user-field-delete

Delete Custom Field for Quotes crm.quote.userfield.delete | Bitrix24 REST API and Marketplace Applications
Delete Custom Field for Quotes crm.quote.userfield.delete
Delete Custom Field for Quotes crm.quote.userfield.delete
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.userfield.delete
removes a custom field for quotes.
Parameter
/
Type
Description
id
unknown
Identifier of the custom field.
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
"crm.quote.userfield.delete"
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
'crm.quote.userfield.delete'
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
"crm.quote.userfield.delete"
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
Create a Custom Field for Estimates
Next
Get Custom Fields for Estimates by ID

---

## Get Custom Fields of Quotes by ID crm.quote.userfield.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/crm-quote-user-field-get

Get Custom Fields of Quotes by ID crm.quote.userfield.get | Bitrix24 REST API and Marketplace Applications
Get Custom Fields of Quotes by ID crm.quote.userfield.get
Get Custom Fields of Quotes by ID crm.quote.userfield.get
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.userfield.get
returns the custom field of quotes by ID.
Parameter
/
Type
Description
id
unknown
Identifier of the custom field.
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
"crm.quote.userfield.get"
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
( error )
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
'crm.quote.userfield.get'
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
'Error getting user field: '
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
"crm.quote.userfield.get"
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
Delete a Custom Field for Estimates
Next
Get a List of Custom Fields for Estimates by Filter

---

## Get a list of custom fields for estimates by filter crm.quote.userfield.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/crm-quote-user-field-list

Get a list of custom fields for estimates by filter crm.quote.userfield.list | Bitrix24 REST API and Marketplace Applications
Get a list of custom fields for estimates by filter crm.quote.userfield.list
Get a list of custom fields for estimates by filter crm.quote.userfield.list
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.userfield.list
returns a list of custom fields for estimates by filter.
Parameter
/
Type
Description
order
unknown
Sorting fields.
filter
unknown
Filter fields.
Example
Example
JS
PHP
BX24.js
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
var
id =
prompt
(
"Enter ID"
);
try
{
const
response =
await
$b24.
callListMethod
(
'crm.quote.userfield.list'
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
, progress);
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
var
id =
prompt
(
"Enter ID"
);
try
{
const
generator = $b24.
fetchListMethod
(
'crm.quote.userfield.list'
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
}
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
var
id =
prompt
(
"Enter ID"
);
try
{
const
response =
await
$b24.
callMethod
(
'crm.quote.userfield.list'
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
}
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
'crm.quote.userfield.list'
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
'Error: '
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
"crm.quote.userfield.list"
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
Get Custom Fields for Estimates by ID
Next
Modify a Custom Field for Estimates

---

## Update Custom Field for Quotes crm.quote.userfield.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/crm-quote-user-field-update

Update Custom Field for Quotes crm.quote.userfield.update | Bitrix24 REST API and Marketplace Applications
Update Custom Field for Quotes crm.quote.userfield.update
Update Custom Field for Quotes crm.quote.userfield.update
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.quote.userfield.update
updates an existing custom field for quotes.
Parameter
/
Type
Description
id
unknown
Identifier of the custom field.
fields
unknown
Set of fields - an array of the form
array("field_to_update"=>"value"[, ...])
, where "field_to_update" can take values returned by the method
crm.userfield.fields
.
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
"crm.quote.userfield.update"
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
'crm.quote.userfield.update'
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
$response
->
getResponseData
()->
more
()) {
$response
->
getResponseData
()->
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
"crm.quote.userfield.update"
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
Get a List of Custom Fields for Estimates by Filter
Next
Overview of Events

---

## Overview of Events When Working with Custom Fields in Estimates

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/events/index

Overview of Events When Working with Custom Fields in Estimates | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Custom Fields in Estimates
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes almost in real-time: receiving notifications about the creation, updating, or deletion of custom fields in estimates.
Detailed work with events is described in the article
Concept and Benefits of Event Handling
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to events for custom fields in estimates through:
outgoing webhook
application
and the method
event.bind
An example of a handler for the event is described in the article
How to Test Your Handler for Handling Bitrix24 Events
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
onCrmQuoteUserFieldAdd
When a custom field is added manually or via the method
crm.quote.userfield.add
onCrmQuoteUserFieldUpdate
When a custom field is updated manually or via the method
crm.quote.userfield.update
onCrmQuoteUserFieldDelete
When a custom field is deleted manually or via the method
crm.quote.userfield.delete
onCrmQuoteUserFieldSetEnumValues
When the set of values for a list-type custom field is changed manually or via the method
crm.quote.userfield.update
Copied
Was the article helpful?
Yes
No
Previous
Modify a Custom Field for Estimates
Next
When Adding a Custom Field

---

## When Adding a Custom Field onCrmQuoteUserFieldAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/events/on-crm-quote-user-field-add

When Adding a Custom Field onCrmQuoteUserFieldAdd | Bitrix24 REST API and Marketplace Applications
What the Handler Receives
When Adding a Custom Field onCrmQuoteUserFieldAdd
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMQUOTEUSERFIELDADD
will trigger when a new custom field is added for estimates.
What the Handler Receives
What the Handler Receives
Data is sent as a POST request
{
"event"
:
"ONCRMQUOTEUSERFIELDADD"
,
"event_handler_id"
:
"753"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6981"
,
"ENTITY_ID"
:
"CRM_QUOTE"
,
"FIELD_NAME"
:
"UF_CRM_QUOTE_1743678817"
}
}
,
"ts"
:
"1743678828"
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
ONCRMQUOTEUSERFIELDADD
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
CRM_QUOTE
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
When updating a custom field onCrmQuoteUserFieldUpdate
When Deleting a Custom Field onCrmQuoteUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Updating a Custom Field

---

## When updating a custom field onCrmQuoteUserFieldUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/events/on-crm-quote-user-field-update

When updating a custom field onCrmQuoteUserFieldUpdate | Bitrix24 REST API and Marketplace Applications
What the handler receives
When updating a custom field onCrmQuoteUserFieldUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMQUOTEUSERFIELDUPDATE
will trigger when a custom field is updated for estimates.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMQUOTEUSERFIELDUPDATE"
,
"event_handler_id"
:
"755"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6841"
,
"ENTITY_ID"
:
"CRM_QUOTE"
,
"FIELD_NAME"
:
"UF_CRM_6710EFCA2D1C0"
}
}
,
"ts"
:
"1743678840"
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
ONCRMQUOTEUSERFIELDUPDATE
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
CRM_QUOTE
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
When Adding a Custom Field onCrmQuoteUserFieldAdd
When Deleting a Custom Field onCrmQuoteUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
When Adding a Custom Field
Next
When Deleting a Custom Field

---

## When Deleting a Custom Field onCrmQuoteUserFieldDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/events/on-crm-quote-user-field-delete

When Deleting a Custom Field onCrmQuoteUserFieldDelete | Bitrix24 REST API and Marketplace Applications
What the handler receives
When Deleting a Custom Field onCrmQuoteUserFieldDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue Learning
Scope:
crm
Who can subscribe: any user
The event
ONCRMQUOTEUSERFIELDDELETE
will trigger when a custom field for estimates is deleted.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMQUOTEUSERFIELDDELETE"
,
"event_handler_id"
:
"757"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6841"
,
"ENTITY_ID"
:
"CRM_QUOTE"
,
"FIELD_NAME"
:
"UF_CRM_6710EFCA2D1C0"
}
}
,
"ts"
:
"1743678847"
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
ONCRMQUOTEUSERFIELDDELETE
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
CRM_QUOTE
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
When Adding a Custom Field onCrmQuoteUserFieldAdd
When updating a custom field onCrmQuoteUserFieldUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Updating a Custom Field
Next
When Changing Values for a List-Type Field

---

## When setting list values for the custom field onCrmQuoteUserFieldSetEnumValues

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/user-field/events/on-crm-quote-user-field-set-enum-values

When setting list values for the custom field onCrmQuoteUserFieldSetEnumValues | Bitrix24 REST API and Marketplace Applications
What the handler receives
When setting list values for the custom field onCrmQuoteUserFieldSetEnumValues
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMQUOTEUSERFIELDSETENUMVALUES
will trigger when setting list values for the custom field of quotes.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMQUOTEUSERFIELDSETENUMVALUES"
,
"event_handler_id"
:
"759"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6981"
,
"ENTITY_ID"
:
"CRM_QUOTE"
,
"FIELD_NAME"
:
"UF_CRM_QUOTE_1743678817"
}
}
,
"ts"
:
"1743678828"
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
ONCRMQUOTEUSERFIELDSETENUMVALUES
event_handler_id
integer
Identifier of the event handler
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
Identifier of the object to which the custom field relates. In this case —
CRM_QUOTE
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
When updating a custom field onCrmQuoteUserFieldUpdate
When Deleting a Custom Field onCrmQuoteUserFieldDelete
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Custom Field
Next
Overview of events

---

## Overview of Events When Working with Estimates

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/events/index

Overview of Events When Working with Estimates | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Estimates
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, updating, or deletion of estimates.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to estimate events through:
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
onCrmQuoteAdd
When an estimate is created manually or via the method
crm.quote.add
onCrmQuoteUpdate
When an estimate is updated manually or via the method
crm.quote.update
onCrmQuoteDelete
When an estimate is deleted manually or via the method
crm.quote.delete
Copied
Was the article helpful?
Yes
No
Previous
When Changing Values for a List-Type Field
Next
When adding an estimate

---

## Event when adding an estimate onCrmQuoteAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/events/on-crm-quote-add

Event when adding an estimate onCrmQuoteAdd | Bitrix24 REST API and Marketplace Applications
Event when adding an estimate onCrmQuoteAdd
Event when adding an estimate onCrmQuoteAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMQUOTEADD
will trigger when an estimate is added.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMQUOTEADD"
,
"event_handler_id"
:
"747"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"71"
}
}
,
"ts"
:
"1743678788"
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
ONCRMQUOTEADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the added estimate.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the added estimate.
The structure is described
below
ts
timestamp
Date and time of sending the event from the
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
Identifier of the added estimate
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
Event on updating the estimate onCrmQuoteUpdate
Event on deleting an estimate onCrmQuoteDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of events
Next
When updating an estimate

---

## Event on updating the estimate onCrmQuoteUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/events/on-crm-quote-update

Event on updating the estimate onCrmQuoteUpdate | Bitrix24 REST API and Marketplace Applications
Event on updating the estimate onCrmQuoteUpdate
Event on updating the estimate onCrmQuoteUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMQUOTEUPDATE
will trigger when an estimate is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMQUOTEUPDATE"
,
"event_handler_id"
:
"749"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"71"
}
}
,
"ts"
:
"1743678800"
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
ONCRMQUOTEUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated estimate.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the updated estimate.
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
Identifier of the updated estimate
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
Event when adding an estimate onCrmQuoteAdd
Event on deleting an estimate onCrmQuoteDelete
Copied
Was the article helpful?
Yes
No
Previous
When adding an estimate
Next
When deleting an estimate

---

## Event on deleting an estimate onCrmQuoteDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/quote/events/on-crm-quote-delete

Event on deleting an estimate onCrmQuoteDelete | Bitrix24 REST API and Marketplace Applications
Event on deleting an estimate onCrmQuoteDelete
Event on deleting an estimate onCrmQuoteDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMQUOTEDELETE
will trigger upon the deletion of an estimate.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMQUOTEDELETE"
,
"event_handler_id"
:
"751"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"71"
}
}
,
"ts"
:
"1743678805"
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
ONCRMQUOTEDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted estimate.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted estimate.
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
Identifier of the deleted estimate
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
Event when adding an estimate onCrmQuoteAdd
Event on updating the estimate onCrmQuoteUpdate
Copied
Was the article helpful?
Yes
No
Previous
When updating an estimate
Next
Overview of Methods

---

