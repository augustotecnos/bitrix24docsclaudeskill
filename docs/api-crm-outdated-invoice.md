---
description: 'CRM Outdated Invoice API (deprecated): CRUD, statuses, events'
methods:
- crm.invoice.add
- crm.invoice.delete
- crm.invoice.fields
- crm.invoice.get
- crm.invoice.getexternallink
- crm.invoice.list
- crm.invoice.recurring.add
- crm.invoice.recurring.delete
- crm.invoice.recurring.expose
- crm.invoice.recurring.fields
- crm.invoice.recurring.get
- crm.invoice.recurring.list
- crm.invoice.recurring.update
- crm.invoice.status.add
- crm.invoice.status.delete
- crm.invoice.status.fields
- crm.invoice.status.get
- crm.invoice.status.list
- crm.invoice.status.update
- crm.invoice.update
- crm.invoice.userfield.add
- crm.invoice.userfield.delete
- crm.invoice.userfield.get
- crm.invoice.userfield.list
- crm.invoice.userfield.update
- crm.paysystem.fields
- crm.paysystem.list
- crm.persontype.fields
- crm.persontype.list
- crm.requisite.link.register
pages: 45
title: 'CRM Outdated Invoice API (deprecated): CRUD, statuses, events'
---
# CRM Outdated Invoice API (deprecated): CRUD, statuses, events
> CRM Outdated Invoice API (deprecated): CRUD, statuses, events
> **45 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Overview of Methods](#overview-of-methods)
- [Create a New Invoice Status crm.invoice.status.add](#create-a-new-invoice-status-crminvoicestatusadd)
- [Delete Invoice Status crm.invoice.status.delete](#delete-invoice-status-crminvoicestatusdelete)
- [Get Invoice Status by ID crm.invoice.status.get](#get-invoice-status-by-id-crminvoicestatusget)
- [Get Invoice Status Fields crm.invoice.status.fields](#get-invoice-status-fields-crminvoicestatusfields)
- [Get the List of Invoice Statuses crm.invoice.status.list](#get-the-list-of-invoice-statuses-crminvoicestatusl)
- [Update Invoice Status crm.invoice.status.update](#update-invoice-status-crminvoicestatusupdate)
- [About CRM Invoices](#about-crm-invoices)
- [Invoices (old)](#invoices-old)
- [Add Invoice crm.invoice.add](#add-invoice-crminvoiceadd)
- [Delete invoice crm.invoice.delete](#delete-invoice-crminvoicedelete)
- [Get invoice fields and the products included in it crm.invoice.fields](#get-invoice-fields-and-the-products-included-in-it)
- [Get Invoice by ID crm.invoice.get](#get-invoice-by-id-crminvoiceget)
- [Get the list of invoices crm.invoice.list](#get-the-list-of-invoices-crminvoicelist)
- [Add a setting for recurring invoice crm.invoice.recurring.add](#add-a-setting-for-recurring-invoice-crminvoicerecu)
- [Delete the recurring invoice setting crm.invoice.recurring.delete](#delete-the-recurring-invoice-setting-crminvoicerec)
- [Create a New Invoice from the Template crm.invoice.recurring.expose](#create-a-new-invoice-from-the-template-crminvoicer)
- [Get the template fields of the recurring invoice crm.invoice.recurring.fields](#get-the-template-fields-of-the-recurring-invoice-c)
- [Get the configuration of a recurring invoice by ID crm.invoice.recurring.get](#get-the-configuration-of-a-recurring-invoice-by-id)
- [Get a list of recurring invoice settings by filter crm.invoice.recurring.list](#get-a-list-of-recurring-invoice-settings-by-filter)
- [Change setting for recurring invoice crm.invoice.recurring.update](#change-setting-for-recurring-invoice-crminvoicerec)
- [Update Invoice crm.invoice.update](#update-invoice-crminvoiceupdate)
- [Create a custom field for invoices crm.invoice.userfield.add](#create-a-custom-field-for-invoices-crminvoiceuserf)
- [Delete Custom Field of Invoices crm.invoice.userfield.delete](#delete-custom-field-of-invoices-crminvoiceuserfiel)
- [Get Custom Field by ID crm.invoice.userfield.get](#get-custom-field-by-id-crminvoiceuserfieldget)
- [Get a List of Custom Fields by Filter crm.invoice.userfield.list](#get-a-list-of-custom-fields-by-filter-crminvoiceus)
- [Update Custom Field crm.invoice.userfield.update](#update-custom-field-crminvoiceuserfieldupdate)
- [Get Fields for Payment Methods crm.paysystem.fields](#get-fields-for-payment-methods-crmpaysystemfields)
- [Get a list of payment methods crm.paysystem.list](#get-a-list-of-payment-methods-crmpaysystemlist)
- [Get Fields for Payer Types crm.persontype.fields](#get-fields-for-payer-types-crmpersontypefields)
- [Get a list of payer types crm.persontype.list](#get-a-list-of-payer-types-crmpersontypelist)
- [Get a link to the invoice crm.invoice.getexternallink](#get-a-link-to-the-invoice-crminvoicegetexternallin)
- [Events](#events)
- [Event on invoice addition onCrmInvoiceAdd](#event-on-invoice-addition-oncrminvoiceadd)
- [Event onCrmInvoiceDelete](#event-oncrminvoicedelete)
- [Event onCrmInvoiceSetStatus for Invoice Status Change](#event-oncrminvoicesetstatus-for-invoice-status-cha)
- [Event onCrmInvoiceUpdate](#event-oncrminvoiceupdate)
- [Event for Adding Custom Field onCrmInvoiceUserFieldAdd](#event-for-adding-custom-field-oncrminvoiceuserfiel)
- [Event onCrmInvoiceUserFieldUpdate](#event-oncrminvoiceuserfieldupdate)
- [Event for Deleting a Custom Field onCrmInvoiceUserFieldDelete](#event-for-deleting-a-custom-field-oncrminvoiceuser)
- [Event for Changing Values of Custom List Field onCrmInvoiceUserFieldSetEnumValues](#event-for-changing-values-of-custom-list-field-onc)
- [Event for Adding a New Recurring Invoice onCrmInvoiceRecurringAdd](#event-for-adding-a-new-recurring-invoice-oncrminvo)
- [Event on Update Recurring Invoice onCrmInvoiceRecurringUpdate](#event-on-update-recurring-invoice-oncrminvoicerecu)
- [Event for Deleting Recurring Invoice onCrmInvoiceRecurringDelete](#event-for-deleting-recurring-invoice-oncrminvoicer)
- [Event for Issuing a New Invoice from Regular onCrmInvoiceRecurringExpose](#event-for-issuing-a-new-invoice-from-regular-oncrm)

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice-status-old/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: any user
Warning
Starting from version 19.0.0, it is recommended to use
common methods for working with directories
Method
Description
crm.invoice.status.add
Creates a new invoice status
crm.invoice.status.delete
Deletes an invoice status
crm.invoice.status.get
Retrieves an invoice status by its identifier
crm.invoice.status.fields
Gets the fields of the invoice status
crm.invoice.status.list
Retrieves a list of invoice statuses
crm.invoice.status.update
Updates an invoice status
Copied
Was the article helpful?
Yes
No
Previous
On Deleting a Unit of Measurement
Next
Create a New Invoice Status

---

## Create a New Invoice Status crm.invoice.status.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice-status-old/crm-invoice-status-add

Create a New Invoice Status crm.invoice.status.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create a New Invoice Status crm.invoice.status.add
Scope:
crm
Who can execute the method: any user
The method
crm.invoice.status.add
creates a new invoice status.
Warning
Starting from version 19.0.0, it is recommended to use the method
crm.status.add
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
array
A set of fields — an array in the form
array("field"=>"value"[, ...])
, containing the values of the invoice status fields.
Note
To find out the required format of the fields, execute the method
crm.invoice.status.fields
and check the format of the returned values for these fields.
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Delete an Invoice Status

---

## Delete Invoice Status crm.invoice.status.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice-status-old/crm-invoice-status-delete

Delete Invoice Status crm.invoice.status.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Invoice Status crm.invoice.status.delete
Scope:
crm
Who can execute the method: any user
The method
crm.invoice.status.delete
removes the invoice status.
Warning
Starting from version 19.0.0, it is recommended to use the method
crm.status.delete
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the invoice status
Copied
Was the article helpful?
Yes
No
Previous
Create a New Invoice Status
Next
Get Invoice Status by ID

---

## Get Invoice Status by ID crm.invoice.status.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice-status-old/crm-invoice-status-get

Get Invoice Status by ID crm.invoice.status.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Invoice Status by ID crm.invoice.status.get
Scope:
crm
Who can execute the method: any user
The method
crm.invoice.status.get
returns the status of an invoice by its ID.
Warning
Starting from version 19.0.0, it is recommended to use the method
crm.status.get
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
The ID of the invoice status
Copied
Was the article helpful?
Yes
No
Previous
Delete an Invoice Status
Next
Get All Fields of Invoice Status

---

## Get Invoice Status Fields crm.invoice.status.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice-status-old/crm-invoice-status-fields

Get Invoice Status Fields crm.invoice.status.fields | Bitrix24 REST API and Marketplace Applications
Get Invoice Status Fields crm.invoice.status.fields
Get Invoice Status Fields crm.invoice.status.fields
Scope:
crm
Who can execute the method: any user
The method
crm.invoice.status.fields
returns the description of the invoice status fields.
Warning
Starting from version 19.0.0, it is recommended to use the method
crm.status.fields
Without parameters
Returned Data
Returned Data
Required parameters are marked with *
Name
type
Description
ENTITY_ID
string
Identifier of the entity associated with the invoice. Read-only
ID
integer
Identifier of the invoice. Read-only
NAME
*
string
Name of the section
NAME_INIT
string
Read-only
SORT
*
integer
Sorting
STATUS_ID
string
Status. Read-only
SYSTEM
char
Whether it is system or not. Read-only
Copied
Was the article helpful?
Yes
No
Previous
Get Invoice Status by ID
Next
Get List of Invoice Statuses

---

## Get the List of Invoice Statuses crm.invoice.status.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice-status-old/crm-invoice-status-list

Get the List of Invoice Statuses crm.invoice.status.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the List of Invoice Statuses crm.invoice.status.list
Scope:
crm
Who can execute the method: any user
Warning
Starting from version 19.0.0, it is recommended to use the method
crm.status.list
The method
crm.invoice.status.list
returns a list of invoice statuses based on a filter. It is an implementation of list methods for invoice statuses.
Method Parameters
Method Parameters
See the description of
list methods
Copied
Was the article helpful?
Yes
No
Previous
Get All Fields of Invoice Status
Next
Update Invoice Status

---

## Update Invoice Status crm.invoice.status.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice-status-old/crm-invoice-status-update

Update Invoice Status crm.invoice.status.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Invoice Status crm.invoice.status.update
Scope:
crm
Who can execute the method: any user
The method
crm.invoice.status.update
returns the status of an invoice by its identifier.
Warning
Starting from version 19.0.0, it is recommended to use the method
crm.status.update
Method Parameters
Method Parameters
Name
type
Description
id
*
integer
Identifier of the invoice status
fields
*
array
Set of fields — an array in the form
array("field_to_update"=>"value"[, ...])
, where "field_to_update" can take values from the method
crm.invoice.status.fields
.
Note
To find out the required format of the fields, execute the method
crm.invoice.status.fields
and check the format of the returned values for these fields.
Copied
Was the article helpful?
Yes
No
Previous
Get List of Invoice Statuses
Next
Overview of Methods

---

## About CRM Invoices

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/index

About CRM Invoices | Bitrix24 REST API and Marketplace Applications
About CRM Invoices
About CRM Invoices
We are still updating this page
Some data may be missing here — we will complete it soon.
Was the article helpful?
Yes
No
Previous
Send a Message to the Feed
Next
List of Methods

---

## Invoices (old)

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/methods

Invoices (old) | Bitrix24 REST API and Marketplace Applications
Invoices (old)
Invoices (old)
Scope:
crm
Who can execute the method: any user
Method
Description
crm.invoice.add
Creates a new invoice.
crm.invoice.delete
Deletes an invoice.
crm.invoice.fields
Returns the description of the invoice fields and the items included in it.
crm.invoice.get
Returns an invoice by its identifier.
crm.invoice.list
Returns a list of invoices.
crm.invoice.recurring.add
Adds a new setting for a recurring invoice.
crm.invoice.recurring.delete
Deletes an existing setting for a recurring invoice template.
crm.invoice.recurring.expose
Creates a new invoice from a template.
crm.invoice.recurring.fields
Returns a list of fields for the recurring invoice template settings with descriptions.
crm.invoice.recurring.get
Returns the fields of the recurring invoice template settings by identifier.
crm.invoice.recurring.list
Returns a list of recurring invoice template settings based on a filter.
crm.invoice.recurring.update
Updates an existing setting for a recurring invoice template.
crm.invoice.update
Updates an existing invoice.
crm.invoice.userfield.add
Creates a new custom field for invoices.
crm.invoice.userfield.delete
Deletes a custom field for invoices.
crm.invoice.userfield.get
Returns a custom field for invoices by identifier.
crm.invoice.userfield.list
Returns a list of custom fields for invoices based on a filter.
crm.invoice.userfield.update
Updates an existing custom field for invoices.
crm.paysystem.fields
Returns the description of fields for payment methods.
crm.paysystem.list
Returns a list of payment methods.
crm.persontype.fields
Returns the description of fields for payer types.
crm.persontype.list
Returns a list of payer types.
crm.invoice.getexternallink
Returns a link to the invoice.
Copied
Was the article helpful?
Yes
No
Previous
About CRM Invoices
Next
Add Invoice

---

## Add Invoice crm.invoice.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-add

Add Invoice crm.invoice.add | Bitrix24 REST API and Marketplace Applications
Add Invoice crm.invoice.add
Add Invoice crm.invoice.add
Method Parameters
Code Examples
Example 1
Example 2
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method creates a new invoice.
If you need to specify any details of the buyer/seller in the invoice (since there can be multiple for a company), use the method
crm.requisite.link.register
.
The created invoice must include the seller and buyer companies:
UF_COMPANY_ID
, if the buyer is a company or
UF_CONTACT_ID
, if the buyer is a contact
UF_MYCOMPANY_ID
- seller
The identifiers specified in
crm.requisite.link.register
and in the created invoice must correspond to the buyer and seller.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
array
Field values for creating the invoice.
To find out the required format of the fields, execute the method
crm.invoice.fields
and check the format of the returned values for these fields
Code Examples
Code Examples
How to Use Examples in Documentation
Example 1
Example 1
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"ORDER_TOPIC":"Invoice for legal entity","STATUS_ID":"P","DATE_INSERT":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" now')'","PAY_VOUCHER_DATE":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" now')'","PAY_VOUCHER_NUM":"876","DATE_MARKED":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" now')'","REASON_MARKED":"Invoice paid immediately.","COMMENTS":"manager's comment","USER_DESCRIPTION":"comment for the client","DATE_BILL":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" now')'","DATE_PAY_BEFORE":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" +1 month')'","RESPONSIBLE_ID":1,"UF_DEAL_ID":10,"UF_COMPANY_ID":5,"UF_CONTACT_ID":2,"PERSON_TYPE_ID":2,"PAY_SYSTEM_ID":6,"INVOICE_PROPERTIES":{"COMPANY":"Ltd. \"New Technologies\"","COMPANY_ADR":"543000 Berlin, Peschanskaya St., 15, office 55 (legal)","INN":"","KPP":"","CONTACT_PERSON":"Boris Sokolov","EMAIL":"pr@logistics-north.com","PHONE":"+1 (495) 234-54-32","FAX":"","ZIP":"","CITY":"","LOCATION":"","ADDRESS":""},"PRODUCT_ROWS":[{"ID":0,"PRODUCT_ID":438,"PRODUCT_NAME":"Product 01","QUANTITY":1,"PRICE":100},{"ID":0,"PRODUCT_ID":515,"PRODUCT_NAME":"Product 77","QUANTITY":1,"PRICE":118}]}}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.add?auth=**put_access_token_here**
try
{
const
current =
new
Date
();
const
nextMonth =
new
Date
();
nextMonth.
setMonth
(current.
getMonth
() +
1
);
const
date2str =
function
(
d
)
{
return
d.
getFullYear
() +
'-'
+
paddatepart
(
1
+ d.
getMonth
()) +
'-'
+
paddatepart
(d.
getDate
()) +
'T'
+
paddatepart
(d.
getHours
()) +
':'
+
paddatepart
(d.
getMinutes
()) +
':'
+
paddatepart
(d.
getSeconds
()) +
'+02:00'
;
};
const
paddatepart =
function
(
part
)
{
return
part >=
10
? part.
toString
() :
'0'
+ part.
toString
();
};
const
response =
await
$b24.
callMethod
(
"crm.invoice.add"
,
{
"fields"
: {
"ORDER_TOPIC"
:
"Invoice for legal entity"
,
"STATUS_ID"
:
"P"
,
"DATE_INSERT"
:
date2str
(current),
"PAY_VOUCHER_DATE"
:
date2str
(current),
"PAY_VOUCHER_NUM"
:
"876"
,
"DATE_MARKED"
:
date2str
(current),
"REASON_MARKED"
:
"Invoice paid immediately."
,
"COMMENTS"
:
"manager's comment"
,
"USER_DESCRIPTION"
:
"comment for the client"
,
"DATE_BILL"
:
date2str
(current),
"DATE_PAY_BEFORE"
:
date2str
(nextMonth),
"RESPONSIBLE_ID"
:
1
,
"UF_DEAL_ID"
:
10
,
"UF_COMPANY_ID"
:
5
,
"UF_CONTACT_ID"
:
2
,
"PERSON_TYPE_ID"
:
2
,
"PAY_SYSTEM_ID"
:
6
,
"INVOICE_PROPERTIES"
: {
"COMPANY"
:
"Ltd. \"New Technologies\""
,
"COMPANY_ADR"
:
"543000 Berlin, Peschanskaya St., 15, office 55 (legal)"
,
"INN"
:
""
,
"KPP"
:
""
,
"CONTACT_PERSON"
:
"Boris Sokolov"
,
"EMAIL"
:
"pr@logistics-north.com"
,
"PHONE"
:
"+1 (495) 234-54-32"
,
"FAX"
:
""
,
"ZIP"
:
""
,
"CITY"
:
""
,
"LOCATION"
:
""
,
"ADDRESS"
:
""
},
"PRODUCT_ROWS"
: [
{
"ID"
:
0
,
"PRODUCT_ID"
:
438
,
"PRODUCT_NAME"
:
"Product 01"
,
"QUANTITY"
:
1
,
"PRICE"
:
100
},
{
"ID"
:
0
,
"PRODUCT_ID"
:
515
,
"PRODUCT_NAME"
:
"Product 77"
,
"QUANTITY"
:
1
,
"PRICE"
:
118
}
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
info
(
"Invoice created with ID "
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
$current
=
new
DateTime
();
$nextMonth
=
new
DateTime
();
$nextMonth
->
setDate
(
$current
->
format
(
'Y'
),
$current
->
format
(
'm'
) +
1
,
$current
->
format
(
'd'
));
$date2str
=
function
(
$d
)
{
return
$d
->
format
(
'Y-m-d\TH:i:sP'
);
};
$paddatepart
=
function
(
$part
)
{
return
$part
>=
10
?
$part
:
'0'
.
$part
;
};
$response
=
$b24Service
->core
->
call
(
"crm.invoice.add"
,
[
"fields"
=> [
"ORDER_TOPIC"
=>
"Invoice for legal entity"
,
"STATUS_ID"
=>
"P"
,
"DATE_INSERT"
=>
$date2str
(
$current
),
"PAY_VOUCHER_DATE"
=>
$date2str
(
$current
),
"PAY_VOUCHER_NUM"
=>
"876"
,
"DATE_MARKED"
=>
$date2str
(
$current
),
"REASON_MARKED"
=>
"Invoice paid immediately."
,
"COMMENTS"
=>
"manager's comment"
,
"USER_DESCRIPTION"
=>
"comment for the client"
,
"DATE_BILL"
=>
$date2str
(
$current
),
"DATE_PAY_BEFORE"
=>
$date2str
(
$nextMonth
),
"RESPONSIBLE_ID"
=>
1
,
"UF_DEAL_ID"
=>
10
,
"UF_COMPANY_ID"
=>
5
,
"UF_CONTACT_ID"
=>
2
,
"PERSON_TYPE_ID"
=>
2
,
"PAY_SYSTEM_ID"
=>
6
,
"INVOICE_PROPERTIES"
=> [
"COMPANY"
=>
"Ltd. \"New Technologies\""
,
"COMPANY_ADR"
=>
"543000 Berlin, Peschanskaya St., 15, office 55 (legal)"
,
"INN"
=>
""
,
"KPP"
=>
""
,
"CONTACT_PERSON"
=>
"Boris Sokolov"
,
"EMAIL"
=>
"pr@logistics-north.com"
,
"PHONE"
=>
"+1 (495) 234-54-32"
,
"FAX"
=>
""
,
"ZIP"
=>
""
,
"CITY"
=>
""
,
"LOCATION"
=>
""
,
"ADDRESS"
=>
""
],
"PRODUCT_ROWS"
=> [
[
"ID"
=>
0
,
"PRODUCT_ID"
=>
438
,
"PRODUCT_NAME"
=>
"Product 01"
,
"QUANTITY"
=>
1
,
"PRICE"
=>
100
],
[
"ID"
=>
0
,
"PRODUCT_ID"
=>
515
,
"PRODUCT_NAME"
=>
"Product 77"
,
"QUANTITY"
=>
1
,
"PRICE"
=>
118
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
'Invoice created with ID '
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
'Error creating invoice: '
.
$e
->
getMessage
();
}
var
current =
new
Date
();
var
nextMonth =
new
Date
();
nextMonth.
setMonth
(current.
getMonth
() +
1
);
var
date2str =
function
(
d
)
{
return
d.
getFullYear
() +
'-'
+
paddatepart
(
1
+ d.
getMonth
()) +
'-'
+
paddatepart
(d.
getDate
()) +
'T'
+
paddatepart
(d.
getHours
()) +
':'
+
paddatepart
(d.
getMinutes
()) +
':'
+
paddatepart
(d.
getSeconds
()) +
'+02:00'
;
};
var
paddatepart =
function
(
part
)
{
return
part >=
10
? part.
toString
() :
'0'
+ part.
toString
();
};
BX24
.
callMethod
(
"crm.invoice.add"
,
{
"fields"
: {
"ORDER_TOPIC"
:
"Invoice for legal entity"
,
"STATUS_ID"
:
"P"
,
"DATE_INSERT"
:
date2str
(current),
"PAY_VOUCHER_DATE"
:
date2str
(current),
"PAY_VOUCHER_NUM"
:
"876"
,
"DATE_MARKED"
:
date2str
(current),
"REASON_MARKED"
:
"Invoice paid immediately."
,
"COMMENTS"
:
"manager's comment"
,
"USER_DESCRIPTION"
:
"comment for the client"
,
"DATE_BILL"
:
date2str
(current),
"DATE_PAY_BEFORE"
:
date2str
(nextMonth),
"RESPONSIBLE_ID"
:
1
,
"UF_DEAL_ID"
:
10
,
"UF_COMPANY_ID"
:
5
,
"UF_CONTACT_ID"
:
2
,
"PERSON_TYPE_ID"
:
2
,
"PAY_SYSTEM_ID"
:
6
,
"INVOICE_PROPERTIES"
: {
"COMPANY"
:
"Ltd. \"New Technologies\""
,
"COMPANY_ADR"
:
"543000 Berlin, Peschanskaya St., 15, office 55 (legal)"
,
"INN"
:
""
,
"KPP"
:
""
,
"CONTACT_PERSON"
:
"Boris Sokolov"
,
"EMAIL"
:
"pr@logistics-north.com"
,
"PHONE"
:
"+1 (495) 234-54-32"
,
"FAX"
:
""
,
"ZIP"
:
""
,
"CITY"
:
""
,
"LOCATION"
:
""
,
"ADDRESS"
:
""
},
"PRODUCT_ROWS"
: [
{
"ID"
:
0
,
"PRODUCT_ID"
:
438
,
"PRODUCT_NAME"
:
"Product 01"
,
"QUANTITY"
:
1
,
"PRICE"
:
100
},
{
"ID"
:
0
,
"PRODUCT_ID"
:
515
,
"PRODUCT_NAME"
:
"Product 77"
,
"QUANTITY"
:
1
,
"PRICE"
:
118
}
]
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
"Invoice created with ID "
+ result.
data
());
}
);
require_once
(
'crest.php'
);
$current
=
new
DateTime
();
$nextMonth
= (
new
DateTime
())->
modify
(
'+1 month'
);
function
date2str
(
$d
)
{
return
$d
->
format
(
'Y-m-d\TH:i:s+02:00'
);
}
$result
=
CRest
::
call
(
'crm.invoice.add'
,
[
'fields'
=> [
'ORDER_TOPIC'
=>
'Invoice for legal entity'
,
'STATUS_ID'
=>
'P'
,
'DATE_INSERT'
=>
date2str
(
$current
),
'PAY_VOUCHER_DATE'
=>
date2str
(
$current
),
'PAY_VOUCHER_NUM'
=>
'876'
,
'DATE_MARKED'
=>
date2str
(
$current
),
'REASON_MARKED'
=>
'Invoice paid immediately.'
,
'COMMENTS'
=>
'manager\'s comment'
,
'USER_DESCRIPTION'
=>
'comment for the client'
,
'DATE_BILL'
=>
date2str
(
$current
),
'DATE_PAY_BEFORE'
=>
date2str
(
$nextMonth
),
'RESPONSIBLE_ID'
=>
1
,
'UF_DEAL_ID'
=>
8
,
'UF_COMPANY_ID'
=>
0
,
'UF_CONTACT_ID'
=>
3
,
'PERSON_TYPE_ID'
=>
1
,
'PAY_SYSTEM_ID'
=>
6
,
'INVOICE_PROPERTIES'
=> [
'FIO'
=>
'Gleb Titov'
,
'EMAIL'
=>
'boss@yt-soft.net'
,
'PHONE'
=>
''
,
'ZIP'
=>
''
,
'CITY'
=>
''
,
'LOCATION'
=>
''
,
'ADDRESS'
=>
''
],
'PRODUCT_ROWS'
=> [
[
'ID'
=>
0
,
'PRODUCT_ID'
=>
438
,
'PRODUCT_NAME'
=>
'Product 01'
,
'QUANTITY'
=>
1
,
'PRICE'
=>
100
],
[
'ID'
=>
0
,
'PRODUCT_ID'
=>
515
,
'PRODUCT_NAME'
=>
'Product 77'
,
'QUANTITY'
=>
1
,
'PRICE'
=>
118
]
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
Example 2
Example 2
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"ORDER_TOPIC":"Invoice for individual","STATUS_ID":"P","DATE_INSERT":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" now')'","PAY_VOUCHER_DATE":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" now')'","PAY_VOUCHER_NUM":"876","DATE_MARKED":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" now')'","REASON_MARKED":"paid","COMMENTS":"comment","USER_DESCRIPTION":"comment to the client","DATE_BILL":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" now')'","DATE_PAY_BEFORE":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" +1 month')'","RESPONSIBLE_ID":1,"UF_DEAL_ID":8,"UF_COMPANY_ID":0,"UF_CONTACT_ID":3,"PERSON_TYPE_ID":1,"PAY_SYSTEM_ID":6,"INVOICE_PROPERTIES":{"FIO":"Gleb Titov","EMAIL":"boss@yt-soft.net","PHONE":"","ZIP":"","CITY":"","LOCATION":"","ADDRESS":""},"PRODUCT_ROWS":[{"ID":0,"PRODUCT_ID":438,"PRODUCT_NAME":"Product 01","QUANTITY":1,"PRICE":100},{"ID":0,"PRODUCT_ID":515,"PRODUCT_NAME":"Product 77","QUANTITY":1,"PRICE":118}]}}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.add?auth=**put_access_token_here**
try
{
const
current =
new
Date
();
const
nextMonth =
new
Date
();
nextMonth.
setMonth
(current.
getMonth
() +
1
);
const
date2str =
function
(
d
)
{
return
d.
getFullYear
() +
'-'
+
paddatepart
(
1
+ d.
getMonth
()) +
'-'
+
paddatepart
(d.
getDate
()) +
'T'
+
paddatepart
(d.
getHours
()) +
':'
+
paddatepart
(d.
getMinutes
()) +
':'
+
paddatepart
(d.
getSeconds
()) +
'+02:00'
;
};
const
paddatepart =
function
(
part
)
{
return
part >=
10
? part.
toString
() :
'0'
+ part.
toString
();
};
const
response =
await
$b24.
callMethod
(
"crm.invoice.add"
,
{
"fields"
: {
"ORDER_TOPIC"
:
"Invoice for individual"
,
"STATUS_ID"
:
"P"
,
"DATE_INSERT"
:
date2str
(current),
"PAY_VOUCHER_DATE"
:
date2str
(current),
"PAY_VOUCHER_NUM"
:
"876"
,
"DATE_MARKED"
:
date2str
(current),
"REASON_MARKED"
:
"paid"
,
"COMMENTS"
:
"comment"
,
"USER_DESCRIPTION"
:
"comment to the client"
,
"DATE_BILL"
:
date2str
(current),
"DATE_PAY_BEFORE"
:
date2str
(nextMonth),
"RESPONSIBLE_ID"
:
1
,
"UF_DEAL_ID"
:
8
,
"UF_COMPANY_ID"
:
0
,
"UF_CONTACT_ID"
:
3
,
"PERSON_TYPE_ID"
:
1
,
"PAY_SYSTEM_ID"
:
6
,
"INVOICE_PROPERTIES"
: {
"FIO"
:
"Gleb Titov"
,
"EMAIL"
:
"boss@yt-soft.net"
,
"PHONE"
:
""
,
"ZIP"
:
""
,
"CITY"
:
""
,
"LOCATION"
:
""
,
"ADDRESS"
:
""
},
"PRODUCT_ROWS"
: [
{
"ID"
:
0
,
"PRODUCT_ID"
:
438
,
"PRODUCT_NAME"
:
"Product 01"
,
"QUANTITY"
:
1
,
"PRICE"
:
100
},
{
"ID"
:
0
,
"PRODUCT_ID"
:
515
,
"PRODUCT_NAME"
:
"Product 77"
,
"QUANTITY"
:
1
,
"PRICE"
:
118
}
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
info
(
"Invoice created with ID "
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
$current
=
new
DateTime
();
$nextMonth
=
new
DateTime
();
$nextMonth
->
setDate
(
$current
->
format
(
'Y'
),
$current
->
format
(
'm'
) +
1
,
$current
->
format
(
'd'
));
$date2str
=
function
(
$d
)
{
return
$d
->
format
(
'Y-m-d\TH:i:sP'
);
};
$paddatepart
=
function
(
$part
)
{
return
$part
>=
10
?
$part
:
'0'
.
$part
;
};
$response
=
$b24Service
->core
->
call
(
'crm.invoice.add'
,
[
'fields'
=> [
'ORDER_TOPIC'
=>
'Invoice for individual'
,
'STATUS_ID'
=>
'P'
,
'DATE_INSERT'
=>
$date2str
(
$current
),
'PAY_VOUCHER_DATE'
=>
$date2str
(
$current
),
'PAY_VOUCHER_NUM'
=>
'876'
,
'DATE_MARKED'
=>
$date2str
(
$current
),
'REASON_MARKED'
=>
'paid'
,
'COMMENTS'
=>
'comment'
,
'USER_DESCRIPTION'
=>
'comment to the client'
,
'DATE_BILL'
=>
$date2str
(
$current
),
'DATE_PAY_BEFORE'
=>
$date2str
(
$nextMonth
),
'RESPONSIBLE_ID'
=>
1
,
'UF_DEAL_ID'
=>
8
,
'UF_COMPANY_ID'
=>
0
,
'UF_CONTACT_ID'
=>
3
,
'PERSON_TYPE_ID'
=>
1
,
'PAY_SYSTEM_ID'
=>
6
,
'INVOICE_PROPERTIES'
=> [
'FIO'
=>
'Gleb Titov'
,
'EMAIL'
=>
'boss@yt-soft.net'
,
'PHONE'
=>
''
,
'ZIP'
=>
''
,
'CITY'
=>
''
,
'LOCATION'
=>
''
,
'ADDRESS'
=>
''
,
],
'PRODUCT_ROWS'
=> [
[
'ID'
=>
0
,
'PRODUCT_ID'
=>
438
,
'PRODUCT_NAME'
=>
'Product 01'
,
'QUANTITY'
=>
1
,
'PRICE'
=>
100
],
[
'ID'
=>
0
,
'PRODUCT_ID'
=>
515
,
'PRODUCT_NAME'
=>
'Product 77'
,
'QUANTITY'
=>
1
,
'PRICE'
=>
118
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
'Invoice created with ID '
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
'Error creating invoice: '
.
$e
->
getMessage
();
}
var
current =
new
Date
();
var
nextMonth =
new
Date
();
nextMonth.
setMonth
(current.
getMonth
() +
1
);
var
date2str =
function
(
d
)
{
return
d.
getFullYear
() +
'-'
+
paddatepart
(
1
+ d.
getMonth
()) +
'-'
+
paddatepart
(d.
getDate
()) +
'T'
+
paddatepart
(d.
getHours
()) +
':'
+
paddatepart
(d.
getMinutes
()) +
':'
+
paddatepart
(d.
getSeconds
()) +
'+02:00'
;
};
var
paddatepart =
function
(
part
)
{
return
part >=
10
? part.
toString
() :
'0'
+ part.
toString
();
};
BX24
.
callMethod
(
"crm.invoice.add"
,
{
"fields"
: {
"ORDER_TOPIC"
:
"Invoice for individual"
,
"STATUS_ID"
:
"P"
,
"DATE_INSERT"
:
date2str
(current),
"PAY_VOUCHER_DATE"
:
date2str
(current),
"PAY_VOUCHER_NUM"
:
"876"
,
"DATE_MARKED"
:
date2str
(current),
"REASON_MARKED"
:
"paid"
,
"COMMENTS"
:
"comment"
,
"USER_DESCRIPTION"
:
"comment to the client"
,
"DATE_BILL"
:
date2str
(current),
"DATE_PAY_BEFORE"
:
date2str
(nextMonth),
"RESPONSIBLE_ID"
:
1
,
"UF_DEAL_ID"
:
8
,
"UF_COMPANY_ID"
:
0
,
"UF_CONTACT_ID"
:
3
,
"PERSON_TYPE_ID"
:
1
,
"PAY_SYSTEM_ID"
:
6
,
"INVOICE_PROPERTIES"
: {
"FIO"
:
"Gleb Titov"
,
"EMAIL"
:
"boss@yt-soft.net"
,
"PHONE"
:
""
,
"ZIP"
:
""
,
"CITY"
:
""
,
"LOCATION"
:
""
,
"ADDRESS"
:
""
},
"PRODUCT_ROWS"
: [
{
"ID"
:
0
,
"PRODUCT_ID"
:
438
,
"PRODUCT_NAME"
:
"Product 01"
,
"QUANTITY"
:
1
,
"PRICE"
:
100
},
{
"ID"
:
0
,
"PRODUCT_ID"
:
515
,
"PRODUCT_NAME"
:
"Product 77"
,
"QUANTITY"
:
1
,
"PRICE"
:
118
}
]
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
"Invoice created with ID "
+ result.
data
());
}
);
require_once
(
'crest.php'
);
$current
=
new
DateTime
();
$nextMonth
= (
new
DateTime
())->
modify
(
'+1 month'
);
function
date2str
(
$d
)
{
return
$d
->
format
(
'Y-m-d\TH:i:s+02:00'
);
}
$result
=
CRest
::
call
(
'crm.invoice.add'
,
[
'fields'
=> [
'ORDER_TOPIC'
=>
'Invoice for individual'
,
'STATUS_ID'
=>
'P'
,
'DATE_INSERT'
=>
date2str
(
$current
),
'PAY_VOUCHER_DATE'
=>
date2str
(
$current
),
'PAY_VOUCHER_NUM'
=>
'876'
,
'DATE_MARKED'
=>
date2str
(
$current
),
'REASON_MARKED'
=>
'paid'
,
'COMMENTS'
=>
'comment'
,
'USER_DESCRIPTION'
=>
'comment to the client'
,
'DATE_BILL'
=>
date2str
(
$current
),
'DATE_PAY_BEFORE'
=>
date2str
(
$nextMonth
),
'RESPONSIBLE_ID'
=>
1
,
'UF_DEAL_ID'
=>
8
,
'UF_COMPANY_ID'
=>
0
,
'UF_CONTACT_ID'
=>
3
,
'PERSON_TYPE_ID'
=>
1
,
'PAY_SYSTEM_ID'
=>
6
,
'INVOICE_PROPERTIES'
=> [
'FIO'
=>
'Gleb Titov'
,
'EMAIL'
=>
'boss@yt-soft.net'
,
'PHONE'
=>
''
,
'ZIP'
=>
''
,
'CITY'
=>
''
,
'LOCATION'
=>
''
,
'ADDRESS'
=>
''
],
'PRODUCT_ROWS'
=> [
[
'ID'
=>
0
,
'PRODUCT_ID'
=>
438
,
'PRODUCT_NAME'
=>
'Product 01'
,
'QUANTITY'
=>
1
,
'PRICE'
=>
100
],
[
'ID'
=>
0
,
'PRODUCT_ID'
=>
515
,
'PRODUCT_NAME'
=>
'Product 77'
,
'QUANTITY'
=>
1
,
'PRICE'
=>
118
]
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
Copied
Was the article helpful?
Yes
No
Previous
List of Methods
Next
Delete Invoice

---

## Delete invoice crm.invoice.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-delete

Delete invoice crm.invoice.delete | Bitrix24 REST API and Marketplace Applications
Method parameters
Delete invoice crm.invoice.delete
Method parameters
Code examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method deletes an invoice.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
id
integer
Invoice identifier
Code examples
Code examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_invoice_id"}' \ # Replace 'your_invoice_id' with the actual invoice ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_invoice_id","auth":"**put_access_token_here**"}' \ # Replace 'your_invoice_id' with the actual invoice ID
https://**put_your_bitrix24_address**/rest/crm.invoice.delete
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
"crm.invoice.delete"
,
{
"id"
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
'crm.invoice.delete'
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
'Error deleting invoice: '
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
"crm.invoice.delete"
,
{
"id"
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
require_once
(
'crest.php'
);
$id
=
'your_invoice_id'
;
// Replace 'your_invoice_id' with the actual invoice ID
$result
=
CRest
::
call
(
'crm.invoice.delete'
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
Copied
Was the article helpful?
Yes
No
Previous
Add Invoice
Next
Get Invoice Fields and Included Items

---

## Get invoice fields and the products included in it crm.invoice.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-fields

Get invoice fields and the products included in it crm.invoice.fields | Bitrix24 REST API and Marketplace Applications
Get invoice fields and the products included in it crm.invoice.fields
Get invoice fields and the products included in it crm.invoice.fields
Code examples
Returned data
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a description of the fields of the
invoice
, including
custom fields
.
No parameters.
Code examples
Code examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.invoice.fields'
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
'crm.invoice.fields'
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
'Error fetching invoice fields: '
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
"crm.invoice.fields"
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
'crm.invoice.fields'
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
Returned data
Returned data
Required parameters are marked with *
Name
type
Description
Note
ID
integer
Identifier
Read-only
ACCOUNT_NUMBER
*
string
Number
COMMENTS
text
Manager's comment
CREATED_BY
integer
Created by user
Read-only
CURRENCY
crm_currency
Currency identifier
Read-only
DATE_BILL
date
Invoice date
DATE_INSERT
datetime
Creation date
DATE_MARKED
datetime
Rejection date
Specified if the invoice is rejected
DATE_PAY_BEFORE
date
Payment due date
DATE_PAYED
datetime
Date changed to paid status
Read-only
DATE_STATUS
datetime
Date of status change
Read-only
DATE_UPDATE
datetime
Date of modification
Read-only
EMP_PAYED_ID
integer
Identifier of the user who last marked the invoice as "paid"
Read-only
EMP_STATUS_ID
integer
Identifier of the user who last changed the invoice status
Read-only
LID
integer
Site identifier
Read-only
XML_ID
string
External code
ORDER_TOPIC
*
string
Subject
PAY_SYSTEM_ID
*
integer
Identifier of the printed form
PAY_VOUCHER_DATE
date
Payment date
Specified if the invoice is paid
PAY_VOUCHER_NUM
string
Payment document number
Specified if the invoice is paid
PAYED
char
Payment status
Read-only
PERSON_TYPE_ID
*
integer
Payer type identifier
PRICE
double
Amount
Read-only
REASON_MARKED
string
Status comment
Specified if the invoice is paid or rejected
RESPONSIBLE_EMAIL
string
Responsible person's e-mail
Read-only
RESPONSIBLE_ID
integer
Identifier of the responsible person
RESPONSIBLE_LAST_NAME
string
Last name of the responsible person
Read-only
RESPONSIBLE_LOGIN
string
Login of the responsible person
Read-only
RESPONSIBLE_NAME
string
First name of the responsible person
Read-only
RESPONSIBLE_PERSONAL_PHOTO
integer
Identifier of the responsible person's photo
Read-only
RESPONSIBLE_SECOND_NAME
string
Middle name of the responsible person
Read-only
RESPONSIBLE_WORK_POSITION
string
Position of the responsible person
Read-only
STATUS_ID
crm_status
Status identifier
Identifier of the "INVOICE_STATUS" reference
TAX_VALUE
double
Tax amount
Read-only
UF_COMPANY_ID
integer
Company identifier
Specified if the payer is a "Legal entity"
UF_CONTACT_ID
integer
Contact identifier
Specified if the payer is an "Individual", or as a contact person for the company
UF_MYCOMPANY_ID
integer
Identifier of your company
Specified as the company with the invoice details (link to the details is set separately)
UF_DEAL_ID
integer
Identifier of the related deal
USER_DESCRIPTION
string
Comment
PR_LOCATION
integer
Location identifier
Required if using tax mode on the document
INVOICE_PROPERTIES
array
List of properties
If the client is a company, the following keys can be specified (all values are of type string):
COMPANY
- Company name;
COMPANY_ADR
- Address;
CONTACT_PERSON
- Contact person;
EMAIL
- E-mail;
PHONE
- Phone;
INN
- Tax ID;
KPP
- Tax Registration Reason Code.
If the client is a contact:
FIO
- Full name;
ADDRESS
- Address;
EMAIL
- E-mail;
PHONE
- Phone.
PRODUCT_ROWS
array
List of product items
Fields of the product item:
ID
- Identifier (integer), specify 0 for a new record;
PRICE
- Price (double);
DISCOUNT_PRICE
- Discount per product unit (double);
PRODUCT_ID
- Identifier of the product in the catalog (integer), 0 if not from the catalog;
PRODUCT_NAME
- Name of the product item (string);
VAT_RATE
- VAT rate coefficient (double);
VAT_INCLUDED
- VAT included in the price ('Y' or 'N') (char);
MEASURE_CODE
- Measurement unit code (integer);
MEASURE_NAME
- Measurement unit designation (string);
CATALOG_XML_ID
- External catalog code (string), read-only;
PRODUCT_XML_ID
- External product item code (string), matches the external product code if it is from the catalog. Read-only.
QUANTITY
- Quantity.
Copied
Was the article helpful?
Yes
No
Previous
Delete Invoice
Next
Get Invoice by ID

---

## Get Invoice by ID crm.invoice.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-get

Get Invoice by ID crm.invoice.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Invoice by ID crm.invoice.get
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns an invoice by its ID.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Invoice ID
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_invoice_id"}' \ # Replace 'your_invoice_id' with the actual invoice ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_invoice_id","auth":"**put_access_token_here**"}' \ # Replace 'your_invoice_id' with the actual invoice ID
https://**put_your_bitrix24_address**/rest/crm.invoice.get
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
"crm.invoice.get"
,
{
"id"
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
'crm.invoice.get'
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
'Error getting invoice: '
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
"crm.invoice.get"
,
{
"id"
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
require_once
(
'crest.php'
);
$id
=
'your_invoice_id'
;
// Replace 'your_invoice_id' with the actual invoice ID
$result
=
CRest
::
call
(
'crm.invoice.get'
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
Copied
Was the article helpful?
Yes
No
Previous
Get Invoice Fields and Included Items
Next
Get List of Invoices

---

## Get the list of invoices crm.invoice.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-list

Get the list of invoices crm.invoice.list | Bitrix24 REST API and Marketplace Applications
Get the list of invoices crm.invoice.list
Get the list of invoices crm.invoice.list
Method parameters
Code examples
Fields returned by the method
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a list of invoices. It is an implementation of the list method for invoices.
When querying, use masks:
"*" — to select all fields (excluding custom fields)
"UF_*" — to select all custom fields.
The method does not return properties and line items of the invoice. To obtain properties and line items, use the method
crm.invoice.get
.
Method parameters
Method parameters
See the description of
list methods
.
Required parameters are marked with *
Name
type
Description
filter
Record filter. By default, all records are returned without filtering
order
Record sorting. Sorting is supported by the same fields as in the filter
Code examples
Code examples
How to Use Examples in Documentation
The example outputs data to the console. If you need to output data differently, implement your own data handling based on the results returned by
result.data()
and
result.error()
calls.
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"DATE_INSERT":"ASC"},"filter":{">PRICE":100},"select":["ID","ACCOUNT_NUMBER","ORDER_TOPIC","DATE_INSERT","STATUS_ID","PRICE","CURRENCY_ID"]}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"DATE_INSERT":"ASC"},"filter":{">PRICE":100},"select":["ID","ACCOUNT_NUMBER","ORDER_TOPIC","DATE_INSERT","STATUS_ID","PRICE","CURRENCY_ID"],"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.invoice.list'
,
{
"order"
: {
"DATE_INSERT"
:
"ASC"
},
"filter"
: {
">PRICE"
:
100
},
"select"
: [
"ID"
,
"ACCOUNT_NUMBER"
,
"ORDER_TOPIC"
,
"DATE_INSERT"
,
"STATUS_ID"
,
"PRICE"
,
"CURRENCY_ID"
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.invoice.list'
, {
"order"
: {
"DATE_INSERT"
:
"ASC"
},
"filter"
: {
">PRICE"
:
100
},
"select"
: [
"ID"
,
"ACCOUNT_NUMBER"
,
"ORDER_TOPIC"
,
"DATE_INSERT"
,
"STATUS_ID"
,
"PRICE"
,
"CURRENCY_ID"
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
'crm.invoice.list'
, {
"order"
: {
"DATE_INSERT"
:
"ASC"
},
"filter"
: {
">PRICE"
:
100
},
"select"
: [
"ID"
,
"ACCOUNT_NUMBER"
,
"ORDER_TOPIC"
,
"DATE_INSERT"
,
"STATUS_ID"
,
"PRICE"
,
"CURRENCY_ID"
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
'crm.invoice.list'
,
[
'order'
=> [
'DATE_INSERT'
=>
'ASC'
],
'filter'
=> [
'>PRICE'
=>
100
],
'select'
=> [
'ID'
,
'ACCOUNT_NUMBER'
,
'ORDER_TOPIC'
,
'DATE_INSERT'
,
'STATUS_ID'
,
'PRICE'
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
'Error fetching invoice list: '
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
"crm.invoice.list"
,
{
"order"
: {
"DATE_INSERT"
:
"ASC"
},
"filter"
: {
">PRICE"
:
100
},
"select"
: [
"ID"
,
"ACCOUNT_NUMBER"
,
"ORDER_TOPIC"
,
"DATE_INSERT"
,
"STATUS_ID"
,
"PRICE"
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
'crm.invoice.list'
,
[
'order'
=> [
'DATE_INSERT'
=>
'ASC'
],
'filter'
=> [
'>PRICE'
=>
100
],
'select'
=> [
'ID'
,
'ACCOUNT_NUMBER'
,
'ORDER_TOPIC'
,
'DATE_INSERT'
,
'STATUS_ID'
,
'PRICE'
,
'CURRENCY_ID'
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
Fields returned by the method
Fields returned by the method
Field
/
Type
Description
Note
ID
integer
Identifier
Read-only
ACCOUNT_NUMBER
string
Number
Required
COMMENTS
text
Manager's comment
CREATED_BY
integer
Created by user
Read-only
CURRENCY
crm_currency
Currency identifier
Read-only
DATE_BILL
date
Invoice date
DATE_INSERT
datetime
Creation date
DATE_MARKED
datetime
Rejection date
Specified if the invoice is rejected
DATE_PAY_BEFORE
date
Payment due date
DATE_PAYED
datetime
Date changed to paid status
Read-only
DATE_STATUS
datetime
Date of status change
Read-only
DATE_UPDATE
datetime
Date of update
Read-only
EMP_PAYED_ID
integer
Identifier of the user who last marked the invoice as paid
Read-only
EMP_STATUS_ID
integer
Identifier of the user who last changed the invoice status
Read-only
LID
integer
Site identifier
Read-only
IS_RECURRING
char
Flag for recurring deal template
XML_ID
string
External code
ORDER_TOPIC
string
Subject
Required
PAY_SYSTEM_ID
integer
Identifier of the payment form
Required
PAY_VOUCHER_DATE
date
Payment date
Specified if the invoice is paid
PAY_VOUCHER_NUM
string
Payment document number
Specified if the invoice is paid
PAYED
char
Paid status
Read-only
PERSON_TYPE_ID
integer
Payer type identifier
Required
PRICE
double
Amount
Read-only
REASON_MARKED
string
Status comment
Specified if the invoice is paid or rejected
RESPONSIBLE_EMAIL
string
Responsible person's e-mail
Read-only
RESPONSIBLE_ID
integer
Identifier of the responsible person
RESPONSIBLE_LAST_NAME
string
Last name of the responsible person
Read-only
RESPONSIBLE_LOGIN
string
Login of the responsible person
Read-only
RESPONSIBLE_NAME
string
First name of the responsible person
Read-only
RESPONSIBLE_PERSONAL_PHOTO
integer
Identifier of the responsible person's photo
Read-only
RESPONSIBLE_SECOND_NAME
string
Middle name of the responsible person
Read-only
RESPONSIBLE_WORK_POSITION
string
Position of the responsible person
Read-only
STATUS_ID
crm_status
Status identifier
Identifier of the "INVOICE_STATUS" reference
TAX_VALUE
double
Tax amount
Read-only
UF_COMPANY_ID
integer
Company identifier
Specified if the payer is a "Legal entity"
UF_CONTACT_ID
integer
Contact identifier
Specified if the payer is a "Natural person" or as a contact person of the company
UF_MYCOMPANY_ID
integer
Identifier of your company
Specified as the company with invoice details (link to details is set separately)
UF_DEAL_ID
integer
Identifier of the related deal
UF_QUOTE_ID
integer
Identifier of the related estimate
USER_DESCRIPTION
string
Comment
Copied
Was the article helpful?
Yes
No
Previous
Get Invoice by ID
Next
Add Settings for Recurring Invoice

---

## Add a setting for recurring invoice crm.invoice.recurring.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-recurring-add

Add a setting for recurring invoice crm.invoice.recurring.add | Bitrix24 REST API and Marketplace Applications
Add a setting for recurring invoice crm.invoice.recurring.add
Add a setting for recurring invoice crm.invoice.recurring.add
Method parameters
Code examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method adds a new setting for a recurring invoice.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
fields
array
Field values for creating a recurring invoice setting.
The required field is
INVOICE_ID
[ID of the invoice that has the parameter
IS_RECURRING=Y
].
To find out the required format of the fields, execute the method
crm.invoice.recurring.fields
and check the format of the returned values for these fields
Code examples
Code examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"INVOICE_ID":"10","IS_LIMIT":"N","START_DATE":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" +1 month')'","PARAMS":{"PERIOD":"day","IS_WORKING_ONLY":"N","INTERVAL":30,"DATE_PAY_BEFORE_OFFSET_TYPE":"month","DATE_PAY_BEFORE_OFFSET_VALUE":1}}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.recurring.add
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"INVOICE_ID":"10","IS_LIMIT":"N","START_DATE":"'$(date -Iseconds --utc --date='TZ="Europe/Berlin" +1 month')'","PARAMS":{"PERIOD":"day","IS_WORKING_ONLY":"N","INTERVAL":30,"DATE_PAY_BEFORE_OFFSET_TYPE":"month","DATE_PAY_BEFORE_OFFSET_VALUE":1}},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.recurring.add
try
{
const
current =
new
Date
();
const
nextMonth =
new
Date
();
nextMonth.
setMonth
(current.
getMonth
() +
1
);
const
date2str =
function
(
d
)
{
return
d.
getFullYear
() +
'-'
+
paddatepart
(
1
+ d.
getMonth
()) +
'-'
+
paddatepart
(d.
getDate
()) +
'T'
+
paddatepart
(d.
getHours
()) +
':'
+
paddatepart
(d.
getMinutes
()) +
':'
+
paddatepart
(d.
getSeconds
()) +
'+02:00'
;
};
const
paddatepart =
function
(
part
)
{
return
part >=
10
? part.
toString
() :
'0'
+ part.
toString
();
};
const
response =
await
$b24.
callMethod
(
"crm.invoice.recurring.add"
,
{
fields
:
{
"INVOICE_ID"
:
"10"
,
"IS_LIMIT"
:
"N"
,
"START_DATE"
:
date2str
(nextMonth),
"PARAMS"
: {
"PERIOD"
:
"day"
,
"IS_WORKING_ONLY"
:
"N"
,
"INTERVAL"
:
30
,
"DATE_PAY_BEFORE_OFFSET_TYPE"
:
"month"
,
"DATE_PAY_BEFORE_OFFSET_VALUE"
:
1
,
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
info
(
"Recurring invoice settings added. Record ID - "
+ result);
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
$current
=
new
DateTime
();
$nextMonth
=
new
DateTime
();
$nextMonth
->
setDate
(
$current
->
format
(
'Y'
),
$current
->
format
(
'm'
) +
1
,
$current
->
format
(
'd'
));
$date2str
=
function
(
$d
)
{
return
$d
->
format
(
'Y-m-d\TH:i:sP'
);
};
$paddatepart
=
function
(
$part
)
{
return
$part
>=
10
?
$part
:
'0'
.
$part
;
};
$response
=
$b24Service
->core
->
call
(
'crm.invoice.recurring.add'
,
[
'fields'
=> [
'INVOICE_ID'
=>
'10'
,
'IS_LIMIT'
=>
'N'
,
'START_DATE'
=>
$date2str
(
$nextMonth
),
'PARAMS'
=> [
'PERIOD'
=>
'day'
,
'IS_WORKING_ONLY'
=>
'N'
,
'INTERVAL'
=>
30
,
'DATE_PAY_BEFORE_OFFSET_TYPE'
=>
'month'
,
'DATE_PAY_BEFORE_OFFSET_VALUE'
=>
1
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
'Success: Recurring invoice settings added. Record ID - '
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
'Error adding recurring invoice settings: '
.
$e
->
getMessage
();
}
var
current =
new
Date
();
var
nextMonth =
new
Date
();
nextMonth.
setMonth
(current.
getMonth
() +
1
);
var
date2str =
function
(
d
)
{
return
d.
getFullYear
() +
'-'
+
paddatepart
(
1
+ d.
getMonth
()) +
'-'
+
paddatepart
(d.
getDate
()) +
'T'
+
paddatepart
(d.
getHours
()) +
':'
+
paddatepart
(d.
getMinutes
()) +
':'
+
paddatepart
(d.
getSeconds
()) +
'+02:00'
;
};
var
paddatepart =
function
(
part
)
{
return
part >=
10
? part.
toString
() :
'0'
+ part.
toString
();
};
BX24
.
callMethod
(
"crm.invoice.recurring.add"
,
{
fields
:
{
"INVOICE_ID"
:
"10"
,
"IS_LIMIT"
:
"N"
,
"START_DATE"
:
date2str
(nextMonth),
"PARAMS"
: {
"PERIOD"
:
"day"
,
"IS_WORKING_ONLY"
:
"N"
,
"INTERVAL"
:
30
,
"DATE_PAY_BEFORE_OFFSET_TYPE"
:
"month"
,
"DATE_PAY_BEFORE_OFFSET_VALUE"
:
1
,
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
info
(
"Recurring invoice settings added. Record ID - "
+ result.
data
());
}
);
require_once
(
'crest.php'
);
$current
=
new
DateTime
();
$nextMonth
= (
new
DateTime
())->
modify
(
'+1 month'
);
function
date2str
(
$d
)
{
return
$d
->
format
(
'Y-m-d\TH:i:s+02:00'
);
}
$result
=
CRest
::
call
(
'crm.invoice.recurring.add'
,
[
'fields'
=> [
'INVOICE_ID'
=>
10
,
'IS_LIMIT'
=>
'N'
,
'START_DATE'
=>
date2str
(
$nextMonth
),
'PARAMS'
=> [
'PERIOD'
=>
'day'
,
'IS_WORKING_ONLY'
=>
'N'
,
'INTERVAL'
=>
30
,
'DATE_PAY_BEFORE_OFFSET_TYPE'
=>
'month'
,
'DATE_PAY_BEFORE_OFFSET_VALUE'
=>
1
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
Copied
Was the article helpful?
Yes
No
Previous
Get List of Invoices
Next
Delete Settings for Recurring Invoice

---

## Delete the recurring invoice setting crm.invoice.recurring.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-recurring-delete

Delete the recurring invoice setting crm.invoice.recurring.delete | Bitrix24 REST API and Marketplace Applications
Delete the recurring invoice setting crm.invoice.recurring.delete
Delete the recurring invoice setting crm.invoice.recurring.delete
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method deletes an existing setting for the recurring invoice template.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the setting
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_recurring_invoice_id"}' \ # Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.recurring.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_recurring_invoice_id","auth":"**put_access_token_here**"}' \ # Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
https://**put_your_bitrix24_address**/rest/crm.invoice.recurring.delete
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
"crm.invoice.recurring.delete"
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
'crm.invoice.recurring.delete'
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
'Error deleting recurring invoice: '
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
"crm.invoice.recurring.delete"
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
require_once
(
'crest.php'
);
$id
=
'your_recurring_invoice_id'
;
// Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
$result
=
CRest
::
call
(
'crm.invoice.recurring.delete'
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
Copied
Was the article helpful?
Yes
No
Previous
Add Settings for Recurring Invoice
Next
Create New Invoice from Template

---

## Create a New Invoice from the Template crm.invoice.recurring.expose

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-recurring-expose

Create a New Invoice from the Template crm.invoice.recurring.expose | Bitrix24 REST API and Marketplace Applications
Create a New Invoice from the Template crm.invoice.recurring.expose
Create a New Invoice from the Template crm.invoice.recurring.expose
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method creates a new invoice from the recurring invoice template.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the recurring invoice template
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_recurring_invoice_id"}' \ # Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.recurring.expose
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_recurring_invoice_id","auth":"**put_access_token_here**"}' \ # Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
https://**put_your_bitrix24_address**/rest/crm.invoice.recurring.expose
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
"crm.invoice.recurring.expose"
,
{
id
: id,
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
'crm.invoice.recurring.expose'
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
'Error exposing recurring invoice: '
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
"crm.invoice.recurring.expose"
,
{
id
: id,
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
$id
=
'your_recurring_invoice_id'
;
// Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
$result
=
CRest
::
call
(
'crm.invoice.recurring.expose'
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
Copied
Was the article helpful?
Yes
No
Previous
Delete Settings for Recurring Invoice
Next
Get Fields for Recurring Invoice Template Settings

---

## Get the template fields of the recurring invoice crm.invoice.recurring.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-recurring-fields

Get the template fields of the recurring invoice crm.invoice.recurring.fields | Bitrix24 REST API and Marketplace Applications
Get the template fields of the recurring invoice crm.invoice.recurring.fields
Get the template fields of the recurring invoice crm.invoice.recurring.fields
Code Examples
Returned Data
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a list of fields for the recurring invoice template along with their descriptions.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.recurring.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.recurring.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.invoice.recurring.fields'
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
'crm.invoice.recurring.fields'
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
'Error fetching recurring invoice fields: '
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
"crm.invoice.recurring.fields"
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
'crm.invoice.recurring.fields'
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
Returned Data
Returned Data
Required parameters are marked with *
Field
/
Type
Description
Note
ID
integer
Identifier of the record in the recurring invoice settings table
Read-only
INVOICE_ID
integer
ID of the invoice template
Immutable
ACTIVE
char
Active flag. Values: Y/N
NEXT_EXECUTION
date
Date of the next creation of a new invoice from the template. Calculated by the system based on the specified parameters. If the value is empty, new invoices are not created
Read-only.
LAST_EXECUTION
date
Date of the last creation of a new invoice from the template
Read-only
COUNTER_REPEAT
integer
Number of invoices created from the template
Read-only
START_DATE
date
Start date for calculating the date of the next creation of a new invoice
SEND_BILL
char
Send the invoice to the email associated with the payer. Values: Y/N
EMAIL_ID
integer
ID of the field containing the payer's email
IS_LIMIT
char
Are there limitations on creating new invoices
LIMIT_REPEAT
integer
Maximum number of invoices that can be created from this template
Considered if
IS_LIMIT
is
T
LIMIT_DATE
date
Date until which invoices can be created from this template
Considered if
IS_LIMIT
is
D
PARAMS
unknown
Set of parameters for calculation - recurring_params:
PERIOD
- repetition period:
day - day
week - week
month - month
year - year
TYPE
- type of repetition for month and year:
if PERIOD is month
1 - calculation by the ordinal day number in the month
2 - calculation by the weekday numbers in the month
if PERIOD is year
1 - calculation by the ordinal day number in the specified month
2 - calculation by the weekday numbers in the specified month
INTERVAL
- offset in calculation
IS_WORKING_ONLY
- only working days are considered (Y/N)
WEEKDAY
- full name of the weekday (according to the formatting of the PHP method
date()
)
NUM_DAY_IN_MONTH
- ordinal date number in the month (PERIOD is month or year)
NUM_WEEKDAY_IN_MONTH
- ordinal weekday number in the month (PERIOD is month or year)
FIELD_YEARLY_INTERVAL_MONTH_NAME
- ordinal weekday number in the month (PERIOD is month or year)
DATE_PAY_BEFORE_OFFSET_TYPE
- offset value for calculating the payment term, calculation is made from the moment of creating a new invoice from the template:
day - day
week - week
month - month
year - year
DATE_PAY_BEFORE_OFFSET_VALUE
- offset value for calculating the payment term, calculation is made from the moment of creating a new invoice from the template
Copied
Was the article helpful?
Yes
No
Previous
Create New Invoice from Template
Next
Get Recurring Invoice Settings by ID

---

## Get the configuration of a recurring invoice by ID crm.invoice.recurring.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-recurring-get

Get the configuration of a recurring invoice by ID crm.invoice.recurring.get | Bitrix24 REST API and Marketplace Applications
Get the configuration of a recurring invoice by ID crm.invoice.recurring.get
Get the configuration of a recurring invoice by ID crm.invoice.recurring.get
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns the fields of the recurring invoice template configuration by ID.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the recurring invoice template configuration
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_recurring_invoice_id"}' \ # Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.recurring.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_recurring_invoice_id","auth":"**put_access_token_here**"}' \ # Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
https://**put_your_bitrix24_address**/rest/crm.invoice.recurring.get
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
"crm.invoice.recurring.get"
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
'crm.invoice.recurring.get'
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
'Error getting recurring invoice: '
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
"crm.invoice.recurring.get"
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
require_once
(
'crest.php'
);
$id
=
'your_recurring_invoice_id'
;
// Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
$result
=
CRest
::
call
(
'crm.invoice.recurring.get'
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
Copied
Was the article helpful?
Yes
No
Previous
Get Fields for Recurring Invoice Template Settings
Next
Get List of Recurring Invoice Settings by Filter

---

## Get a list of recurring invoice settings by filter crm.invoice.recurring.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-recurring-list

Get a list of recurring invoice settings by filter crm.invoice.recurring.list | Bitrix24 REST API and Marketplace Applications
Get a list of recurring invoice settings by filter crm.invoice.recurring.list
Get a list of recurring invoice settings by filter crm.invoice.recurring.list
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a list of recurring invoice template settings based on the filter.
When querying, use the mask "*" to select all fields (excluding custom and multiple fields).
Method Parameters
Method Parameters
See the description of
list methods
.
Code Examples
Code Examples
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"INVOICE_ID":"ASC"},"filter":{">COUNTER_REPEAT":5},"select":["ID","INVOICE_ID","NEXT_EXECUTION","LAST_EXECUTION","SEND_BILL","IS_LIMIT"]}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.recurring.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"INVOICE_ID":"ASC"},"filter":{">COUNTER_REPEAT":5},"select":["ID","INVOICE_ID","NEXT_EXECUTION","LAST_EXECUTION","SEND_BILL","IS_LIMIT"],"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.recurring.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.invoice.recurring.list'
,
{
order
: {
"INVOICE_ID"
:
"ASC"
},
filter
: {
">COUNTER_REPEAT"
:
5
},
select
: [
"ID"
,
"INVOICE_ID "
,
"NEXT_EXECUTION"
,
"LAST_EXECUTION"
,
"SEND_BILL"
,
"IS_LIMIT"
]
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.invoice.recurring.list'
, {
order
: {
"INVOICE_ID"
:
"ASC"
},
filter
: {
">COUNTER_REPEAT"
:
5
},
select
: [
"ID"
,
"INVOICE_ID "
,
"NEXT_EXECUTION"
,
"LAST_EXECUTION"
,
"SEND_BILL"
,
"IS_LIMIT"
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.invoice.recurring.list'
, {
order
: {
"INVOICE_ID"
:
"ASC"
},
filter
: {
">COUNTER_REPEAT"
:
5
},
select
: [
"ID"
,
"INVOICE_ID "
,
"NEXT_EXECUTION"
,
"LAST_EXECUTION"
,
"SEND_BILL"
,
"IS_LIMIT"
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
'crm.invoice.recurring.list'
,
[
'order'
=> [
'INVOICE_ID'
=>
'ASC'
],
'filter'
=> [
'>COUNTER_REPEAT'
=>
5
],
'select'
=> [
'ID'
,
'INVOICE_ID'
,
'NEXT_EXECUTION'
,
'LAST_EXECUTION'
,
'SEND_BILL'
,
'IS_LIMIT'
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
'Error fetching recurring invoices: '
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
"crm.invoice.recurring.list"
,
{
order
: {
"INVOICE_ID"
:
"ASC"
},
filter
: {
">COUNTER_REPEAT"
:
5
},
select
: [
"ID"
,
"INVOICE_ID "
,
"NEXT_EXECUTION"
,
"LAST_EXECUTION"
,
"SEND_BILL"
,
"IS_LIMIT"
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
'crm.invoice.recurring.list'
,
[
'order'
=> [
'INVOICE_ID'
=>
'ASC'
],
'filter'
=> [
'>COUNTER_REPEAT'
=>
5
],
'select'
=> [
'ID'
,
'INVOICE_ID'
,
'NEXT_EXECUTION'
,
'LAST_EXECUTION'
,
'SEND_BILL'
,
'IS_LIMIT'
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
Copied
Was the article helpful?
Yes
No
Previous
Get Recurring Invoice Settings by ID
Next
Update Settings for Recurring Invoice

---

## Change setting for recurring invoice crm.invoice.recurring.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-recurring-update

Change setting for recurring invoice crm.invoice.recurring.update | Bitrix24 REST API and Marketplace Applications
Change setting for recurring invoice crm.invoice.recurring.update
Change setting for recurring invoice crm.invoice.recurring.update
Method parameters
Code examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method updates an existing setting for the recurring invoice template.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the recurring invoice template setting
fields
array
Field values for updating the setting.
To find out the required format of the fields, execute the method
crm.invoice.recurring.fields
and check the format of the returned values for these fields
Code examples
Code examples
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_recurring_invoice_id","fields":{"SEND_BILL":"Y","EMAIL_ID":136,"PARAMS":{"MODE":"month","TYPE":2,"INTERVAL":3,"WEEKDAY":"Monday","NUM_WEEKDAY_IN_MONTH":4,"DATE_PAY_BEFORE_OFFSET_TYPE":"day","DATE_PAY_BEFORE_OFFSET_VALUE":15}}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.recurring.update
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_recurring_invoice_id","fields":{"SEND_BILL":"Y","EMAIL_ID":136,"PARAMS":{"MODE":"month","TYPE":2,"INTERVAL":3,"WEEKDAY":"Monday","NUM_WEEKDAY_IN_MONTH":4,"DATE_PAY_BEFORE_OFFSET_TYPE":"day","DATE_PAY_BEFORE_OFFSET_VALUE":15}},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.recurring.update
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
"crm.invoice.recurring.update"
,
{
id
: id,
fields
:
{
"SEND_BILL"
:
"Y"
,
"EMAIL_ID"
:
136
,
"PARAMS"
: {
"MODE"
:
"month"
,
"TYPE"
:
2
,
"INTERVAL"
:
3
,
"WEEKDAY"
:
"Monday"
,
"NUM_WEEKDAY_IN_MONTH"
:
4
,
"DATE_PAY_BEFORE_OFFSET_TYPE"
:
"day"
,
"DATE_PAY_BEFORE_OFFSET_VALUE"
:
15
,
}
},
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
$id
=
$_POST
[
'id'
];
$response
=
$b24Service
->core
->
call
(
'crm.invoice.recurring.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'SEND_BILL'
=>
'Y'
,
'EMAIL_ID'
=>
136
,
'PARAMS'
=> [
'MODE'
=>
'month'
,
'TYPE'
=>
2
,
'INTERVAL'
=>
3
,
'WEEKDAY'
=>
'Monday'
,
'NUM_WEEKDAY_IN_MONTH'
=>
4
,
'DATE_PAY_BEFORE_OFFSET_TYPE'
=>
'day'
,
'DATE_PAY_BEFORE_OFFSET_VALUE'
=>
15
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
echo
'Success: '
.
print_r
(
$result
,
true
);
// Your required data processing logic
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
'Error updating recurring invoice: '
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
"crm.invoice.recurring.update"
,
{
id
: id,
fields
:
{
"SEND_BILL"
:
"Y"
,
"EMAIL_ID"
:
136
,
"PARAMS"
: {
"MODE"
:
"month"
,
"TYPE"
:
2
,
"INTERVAL"
:
3
,
"WEEKDAY"
:
"Monday"
,
"NUM_WEEKDAY_IN_MONTH"
:
4
,
"DATE_PAY_BEFORE_OFFSET_TYPE"
:
"day"
,
"DATE_PAY_BEFORE_OFFSET_VALUE"
:
15
,
}
},
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
$id
=
'your_recurring_invoice_id'
;
// Replace 'your_recurring_invoice_id' with the actual recurring invoice ID
$result
=
CRest
::
call
(
'crm.invoice.recurring.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'SEND_BILL'
=>
'Y'
,
'EMAIL_ID'
=>
136
,
'PARAMS'
=> [
'MODE'
=>
'month'
,
'TYPE'
=>
2
,
'INTERVAL'
=>
3
,
'WEEKDAY'
=>
'Monday'
,
'NUM_WEEKDAY_IN_MONTH'
=>
4
,
'DATE_PAY_BEFORE_OFFSET_TYPE'
=>
'day'
,
'DATE_PAY_BEFORE_OFFSET_VALUE'
=>
15
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
Copied
Was the article helpful?
Yes
No
Previous
Get List of Recurring Invoice Settings by Filter
Next
Update Invoice

---

## Update Invoice crm.invoice.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-update

Update Invoice crm.invoice.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Invoice crm.invoice.update
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method updates an existing invoice.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Invoice identifier
fields
array
Field values for updating the invoice.
To find out the required format of the fields, execute the method
crm.invoice.fields
and check the format of the incoming values of these fields
Code Examples
Code Examples
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id": "**put_invoice_id_here**", "fields": {"DATE_BILL": "**put_date_here**", "USER_DESCRIPTION": "Comment for the client (updated).", "PRODUCT_ROWS": [{"ID": "**put_row_id_here**", "PRODUCT_ID": 703, "QUANTITY": 4, "PRICE": 779.60}]}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.update
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id": "**put_invoice_id_here**", "fields": {"DATE_BILL": "**put_date_here**", "USER_DESCRIPTION": "Comment for the client (updated).", "PRODUCT_ROWS": [{"ID": "**put_row_id_here**", "PRODUCT_ID": 703, "QUANTITY": 4, "PRICE": 779.60}]}, "auth": "**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.update
try
{
const
current =
new
Date
();
const
date2str =
function
(
d
)
{
return
d.
getFullYear
() +
'-'
+
paddatepart
(
1
+ d.
getMonth
()) +
'-'
+
paddatepart
(d.
getDate
()) +
'T'
+
paddatepart
(d.
getHours
()) +
':'
+
paddatepart
(d.
getMinutes
()) +
':'
+
paddatepart
(d.
getSeconds
()) +
'+02:00'
;
};
const
paddatepart =
function
(
part
)
{
return
part >=
10
? part.
toString
() :
'0'
+ part.
toString
();
};
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
'crm.invoice.get'
, {
"id"
: id});
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
const
fields =
clone
(result.
data
());
const
n = fields[
'PRODUCT_ROWS'
].
length
;
let
productUpdated =
false
;
fields[
"DATE_BILL"
] =
date2str
(current);
fields[
"USER_DESCRIPTION"
] =
"Comment for the client (updated)."
;
for
(
let
i
in
fields[
'PRODUCT_ROWS'
])
{
if
(fields[
'PRODUCT_ROWS'
][i][
"PRODUCT_ID"
] ==
703
)
{
const
rowId = fields[
'PRODUCT_ROWS'
][i][
"ID"
];
fields[
'PRODUCT_ROWS'
][i] = {
"ID"
: rowId,
"PRODUCT_ID"
:
703
,
"QUANTITY"
:
4
,
"PRICE"
:
779.60
};
productUpdated =
true
;
break
;
}
}
if
(!productUpdated && n >
0
)
{
fields[
'PRODUCT_ROWS'
][n] = {
"ID"
:
0
,
"PRODUCT_ID"
:
703
,
"QUANTITY"
:
5
,
"PRICE"
:
779.60
};
}
const
updateResponse =
await
$b24.
callMethod
(
'crm.invoice.update'
, {
"id"
: id,
"fields"
: fields});
const
updateResult = updateResponse.
getData
().
result
;
console
.
info
(
"Invoice updated with ID "
+ updateResult);
}
}
catch
(error)
{
console
.
error
(error);
}
function
clone
(
src
)
{
let
dst;
if
(src
instanceof
Object
)
{
dst = {};
for
(
let
i
in
src)
{
if
(src[i]
instanceof
Object
)
dst[i] =
clone
(src[i]);
else
dst[i] = src[i];
}
}
else
dst = src;
return
dst;
}
try
{
$current
=
new
DateTime
();
$date2str
=
function
(
$d
)
{
return
$d
->
format
(
'Y-m-d\TH:i:sP'
);
};
$id
=
readline
(
"Enter ID"
);
$response
=
$b24Service
->core
->
call
(
'crm.invoice.get'
,
[
"id"
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
echo
'Error getting invoice: '
.
$result
->
error
();
}
else
{
$fields
=
clone
(
$result
->
data
());
$n
=
count
(
$fields
[
'PRODUCT_ROWS'
]);
$productUpdated
=
false
;
$fields
[
"DATE_BILL"
] =
$date2str
(
$current
);
$fields
[
"USER_DESCRIPTION"
] =
"Comment for the client (updated)."
;
foreach
(
$fields
[
'PRODUCT_ROWS'
]
as
$key
=>
$row
) {
if
(
$row
[
"PRODUCT_ID"
] ==
703
) {
$rowId
=
$row
[
"ID"
];
$fields
[
'PRODUCT_ROWS'
][
$key
] = [
"ID"
=>
$rowId
,
"PRODUCT_ID"
=>
703
,
"QUANTITY"
=>
4
,
"PRICE"
=>
779.60
];
$productUpdated
=
true
;
break
;
}
}
if
(!
$productUpdated
&&
$n
>
0
) {
$fields
[
'PRODUCT_ROWS'
][
$n
] = [
"ID"
=>
0
,
"PRODUCT_ID"
=>
703
,
"QUANTITY"
=>
5
,
"PRICE"
=>
779.60
];
}
$responseUpdate
=
$b24Service
->core
->
call
(
'crm.invoice.update'
,
[
"id"
=>
$id
,
"fields"
=>
$fields
]
);
$resultUpdate
=
$responseUpdate
->
getResponseData
()
->
getResult
();
if
(
$resultUpdate
->
error
()) {
error_log
(
$resultUpdate
->
error
());
echo
'Error updating invoice: '
.
$resultUpdate
->
error
();
}
else
{
echo
'Invoice updated with ID: '
.
$resultUpdate
->
data
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
'Error: '
.
$e
->
getMessage
();
}
// Adding or updating a product in the invoice.
var
current =
new
Date
();
var
date2str =
function
(
d
)
{
return
d.
getFullYear
() +
'-'
+
paddatepart
(
1
+ d.
getMonth
()) +
'-'
+
paddatepart
(d.
getDate
()) +
'T'
+
paddatepart
(d.
getHours
()) +
':'
+
paddatepart
(d.
getMinutes
()) +
':'
+
paddatepart
(d.
getSeconds
()) +
'+02:00'
;
};
var
paddatepart =
function
(
part
)
{
return
part >=
10
? part.
toString
() :
'0'
+ part.
toString
();
};
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
'crm.invoice.get'
, {
"id"
: id}, addProduct);
function
addProduct
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
var
fields =
clone
(result.
data
());
var
n = fields[
'PRODUCT_ROWS'
].
length
;
var
productUpdated =
false
;
// Changing the "Invoice Date" field
fields[
"DATE_BILL"
] =
date2str
(current);
// Changing the "Comment (will be displayed in the invoice)"
fields[
"USER_DESCRIPTION"
] =
"Comment for the client (updated)."
;
// If the product with ID 703 is in the invoice, update its fields.
// If the product with ID 703 is not in the invoice, add it to the invoice.
// If VAT is used, it is read that the price includes it, and the indication of VAT inclusion in the price will
// be taken from the catalog.
for
(
var
i
in
fields[
'PRODUCT_ROWS'
])
{
if
(fields[
'PRODUCT_ROWS'
][i][
"PRODUCT_ID"
] ==
703
)
{
var
rowId = fields[
'PRODUCT_ROWS'
][i][
"ID"
]
fields[
'PRODUCT_ROWS'
][i] = {
"ID"
: rowId,
"PRODUCT_ID"
:
703
,
"QUANTITY"
:
4
,
"PRICE"
:
779.60
};
productUpdated =
true
;
break
;
}
}
if
(!productUpdated && n >
0
)
{
fields[
'PRODUCT_ROWS'
][n] = {
"ID"
:
0
,
"PRODUCT_ID"
:
703
,
"QUANTITY"
:
5
,
"PRICE"
:
779.60
};
}
BX24
.
callMethod
(
'crm.invoice.update'
, {
"id"
: id,
"fields"
: fields},
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
(
"Invoice updated with ID "
+ result.
data
());
}
}
);
}
}
function
clone
(
src
)
{
var
dst;
if
(src
instanceof
Object
)
{
dst = {};
for
(
var
i
in
src)
{
if
(src[i]
instanceof
Object
)
dst[i] =
clone
(src[i]);
else
dst[i] = src[i];
}
}
else
dst = src;
return
dst;
}
require_once
(
'crest.php'
);
$id
=
$_REQUEST
[
'id'
];
// Assuming ID is passed as a request parameter
$current
=
new
DateTime
();
$date2str
=
function
(
$d
)
{
return
$d
->
format
(
'Y-m-d\TH:i:s+02:00'
);
};
$fields
=
CRest
::
call
(
'crm.invoice.get'
,
[
'id'
=>
$id
]
)[
'result'
];
$n
=
count
(
$fields
[
'PRODUCT_ROWS'
]);
$productUpdated
=
false
;
$fields
[
"DATE_BILL"
] =
$date2str
(
$current
);
$fields
[
"USER_DESCRIPTION"
] =
"Comment for the client (updated)."
;
foreach
(
$fields
[
'PRODUCT_ROWS'
]
as
$i
=>
$row
) {
if
(
$row
[
"PRODUCT_ID"
] ==
703
) {
$fields
[
'PRODUCT_ROWS'
][
$i
] = [
"ID"
=>
$row
[
"ID"
],
"PRODUCT_ID"
=>
703
,
"QUANTITY"
=>
4
,
"PRICE"
=>
779.60
];
$productUpdated
=
true
;
break
;
}
}
if
(!
$productUpdated
&&
$n
>
0
) {
$fields
[
'PRODUCT_ROWS'
][
$n
] = [
"ID"
=>
0
,
"PRODUCT_ID"
=>
703
,
"QUANTITY"
=>
5
,
"PRICE"
=>
779.60
];
}
$result
=
CRest
::
call
(
'crm.invoice.update'
,
[
"id"
=>
$id
,
"fields"
=>
$fields
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
Update Settings for Recurring Invoice
Next
Create Custom Field for Invoices

---

## Create a custom field for invoices crm.invoice.userfield.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-user-field-add

Create a custom field for invoices crm.invoice.userfield.add | Bitrix24 REST API and Marketplace Applications
Create a custom field for invoices crm.invoice.userfield.add
Create a custom field for invoices crm.invoice.userfield.add
Method parameters
Code examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method creates a new custom field for invoices.
The system limitation on the field name is 20 characters. The custom field name always has the prefix
UF_CRM_
, meaning the actual length of the name is 13 characters.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
fields
A set of fields - an array of the form
array("field"=>"value"[, ...])
, containing the description of the custom field. A complete description of the fields can be obtained by calling the method
crm.userfield.fields
.
LIST
Contains a set of list values for custom fields of type List. It is specified when creating/updating the field. Each value is an array with the fields:
VALUE
- the value of the list item. This field is required when creating a new item.
SORT
- sorting.
DEF
- if equal to Y, the list item is the default value. For multiple fields, multiple DEF=Y are allowed. For non-multiple fields, the first will be considered default.
XML_ID
- external code of the value. This parameter is considered only when updating already existing list item values.
ID
- the identifier of the value. If specified, it is considered an update of an existing list item value, not the creation of a new one. It only makes sense when calling the methods
*.userfield.update
.
DEL
- if equal to Y, the existing list item will be deleted. It is applied if the ID parameter is filled.
Code examples
Code examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"SORT":"ASC"},"filter":{"%NAME":"Estimate"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.paysystem.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"SORT":"ASC"},"filter":{"%NAME":"Estimate"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.paysystem.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.paysystem.list'
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
"%NAME"
:
"Estimate"
,
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.paysystem.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"%NAME"
:
"Estimate"
,
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.paysystem.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"%NAME"
:
"Estimate"
,
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
'crm.paysystem.list'
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
'%NAME'
=>
'Estimate'
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
if
(
$response
->
more
()) {
$response
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
'Error listing payment systems: '
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
"crm.paysystem.list"
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"%NAME"
:
"Estimate"
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
'crm.paysystem.list'
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
'%NAME'
=>
'Estimate'
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
Copied
Was the article helpful?
Yes
No
Previous
Update Invoice
Next
Delete Custom Field for Invoices

---

## Delete Custom Field of Invoices crm.invoice.userfield.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-user-field-delete

Delete Custom Field of Invoices crm.invoice.userfield.delete | Bitrix24 REST API and Marketplace Applications
Delete Custom Field of Invoices crm.invoice.userfield.delete
Delete Custom Field of Invoices crm.invoice.userfield.delete
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
This method deletes a custom field of invoices.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the custom field
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id": "**put_id_here**"}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.userfield.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id": "**put_id_here**", "auth": "**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.userfield.delete
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
"crm.invoice.userfield.delete"
,
{
id
: id}
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
( error )
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
'crm.invoice.userfield.delete'
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
"crm.invoice.userfield.delete"
,
{
id
: id},
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
$id
=
$_REQUEST
[
'id'
];
// Assuming ID is passed as a request parameter
$result
=
CRest
::
call
(
'crm.invoice.userfield.delete'
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
Copied
Was the article helpful?
Yes
No
Previous
Create Custom Field for Invoices
Next
Get Custom Field for Invoices by ID

---

## Get Custom Field by ID crm.invoice.userfield.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-user-field-get

Get Custom Field by ID crm.invoice.userfield.get | Bitrix24 REST API and Marketplace Applications
Parameters
Get Custom Field by ID crm.invoice.userfield.get
Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns the user field of invoices by ID.
Parameters
Parameters
Name
type
Description
id
integer
Identifier of the user field
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id": "**put_id_here**"}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.userfield.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id": "**put_id_here**", "auth": "**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.userfield.get
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
"crm.invoice.userfield.get"
,
{
id
: id}
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
'crm.invoice.userfield.get'
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
"crm.invoice.userfield.get"
,
{
id
: id},
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
$id
=
$_REQUEST
[
'id'
];
// Assuming ID is passed as a request parameter
$result
=
CRest
::
call
(
'crm.invoice.userfield.get'
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
Copied
Was the article helpful?
Yes
No
Previous
Delete Custom Field for Invoices
Next
Get List of Custom Fields for Invoices by Filter

---

## Get a List of Custom Fields by Filter crm.invoice.userfield.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-user-field-list

Get a List of Custom Fields by Filter crm.invoice.userfield.list | Bitrix24 REST API and Marketplace Applications
Get a List of Custom Fields by Filter crm.invoice.userfield.list
Get a List of Custom Fields by Filter crm.invoice.userfield.list
Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a list of custom fields for invoices based on the filter.
Parameters
Parameters
Name
type
Description
order
Sorting fields
filter
Filter fields
Code Examples
Code Examples
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"SORT":"ASC"},"filter":{"MANDATORY":"N"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.userfield.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"SORT":"ASC"},"filter":{"MANDATORY":"N"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.userfield.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.invoice.userfield.list'
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.invoice.userfield.list'
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
'crm.invoice.userfield.list'
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
'crm.invoice.userfield.list'
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
$response
->
getResponseData
()->
getMore
()) {
$response
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
'Error fetching invoice user fields: '
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
"crm.invoice.userfield.list"
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
'crm.invoice.userfield.list'
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
Get Custom Field for Invoices by ID
Next
Update Custom Field for Invoices

---

## Update Custom Field crm.invoice.userfield.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-user-field-update

Update Custom Field crm.invoice.userfield.update | Bitrix24 REST API and Marketplace Applications
Update Custom Field crm.invoice.userfield.update
Update Custom Field crm.invoice.userfield.update
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method updates an existing custom field for invoices.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
Identifier of the custom field
fields
Set of fields - an array of the form
array("updatable field"=>"value"[, ...])
, where "updatable field" can take values from the method
crm.userfield.fields
LIST
Contains a set of list values for custom fields of type List. Specified when creating/updating the field. Each value is an array with the fields:
VALUE
- value of the list item. This field is required when creating a new item
SORT
- sorting
DEF
- if equal to Y, the list item is the default value. For multiple fields, multiple DEF=Y are allowed. For non-multiple fields, the first will be considered default
XML_ID
- external code of the value. This parameter is considered only when updating already existing values of the list item
ID
- identifier of the value. If specified, it is considered that this is an update of an existing list item value, not the creation of a new one. Makes sense only when calling the
*.userfield.update
methods
DEL
- if equal to Y, the existing list item will be deleted. Used if the ID parameter is filled
Code Examples
Code Examples
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id": "**put_id_here**", "fields": {"EDIT_FORM_LABEL": "**put_label_here**", "LIST_COLUMN_LABEL": "**put_label_here**"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.userfield.update
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id": "**put_id_here**", "fields": {"EDIT_FORM_LABEL": "**put_label_here**", "LIST_COLUMN_LABEL": "**put_label_here**"}, "auth": "**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.invoice.userfield.update
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
"crm.invoice.userfield.update"
,
{
id
: id,
fields
: {
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
'crm.invoice.userfield.update'
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
more
()) {
$response
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
"crm.invoice.userfield.update"
,
{
id
: id,
fields
: {
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
require_once
(
'crest.php'
);
$id
=
$_REQUEST
[
'id'
];
// Assuming ID is passed as a request parameter
$label
=
$_REQUEST
[
'label'
];
// Assuming label is passed as a request parameter
$result
=
CRest
::
call
(
'crm.invoice.userfield.update'
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
Get List of Custom Fields for Invoices by Filter
Next
Get Field for Payment Methods

---

## Get Fields for Payment Methods crm.paysystem.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-pay-system-fields

Get Fields for Payment Methods crm.paysystem.fields | Bitrix24 REST API and Marketplace Applications
Get Fields for Payment Methods crm.paysystem.fields
Get Fields for Payment Methods crm.paysystem.fields
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a description of the fields for payment methods.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.paysystem.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.paysystem.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.paysystem.fields"
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
'crm.paysystem.fields'
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
'Error fetching payment system fields: '
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
"crm.paysystem.fields"
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
'crm.paysystem.fields'
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
Copied
Was the article helpful?
Yes
No
Previous
Update Custom Field for Invoices
Next
Get List of Payment Methods

---

## Get a list of payment methods crm.paysystem.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-pay-system-list

Get a list of payment methods crm.paysystem.list | Bitrix24 REST API and Marketplace Applications
Get a list of payment methods crm.paysystem.list
Get a list of payment methods crm.paysystem.list
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a list of payment methods applicable to estimates or invoices.
Name
type
Description
order
Sorting fields
filter
Filtering fields
Code examples
Code examples
How to Use Examples in Documentation
The example outputs data to the console. If you need to display data differently, implement your own data handling for the results returned by
result.data()
and
result.error()
.
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"SORT":"ASC"},"filter":{"%NAME":"Estimate"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.paysystem.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"SORT":"ASC"},"filter":{"%NAME":"Estimate"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.paysystem.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.paysystem.list'
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
"%NAME"
:
"Estimate"
,
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
'crm.paysystem.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"%NAME"
:
"Estimate"
,
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.paysystem.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"%NAME"
:
"Estimate"
,
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
'crm.paysystem.list'
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
'%NAME'
=>
'Estimate'
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
if
(
$response
->
more
()) {
$response
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
'Error listing payment systems: '
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
"crm.paysystem.list"
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"%NAME"
:
"Estimate"
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
'crm.paysystem.list'
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
'%NAME'
=>
'Estimate'
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
Copied
Was the article helpful?
Yes
No
Previous
Get Field for Payment Methods
Next
Get Fields for Payer Types

---

## Get Fields for Payer Types crm.persontype.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-person-type-fields

Get Fields for Payer Types crm.persontype.fields | Bitrix24 REST API and Marketplace Applications
Get Fields for Payer Types crm.persontype.fields
Get Fields for Payer Types crm.persontype.fields
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a description of the fields for payer types.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.persontype.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.persontype.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.persontype.fields"
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
'crm.persontype.fields'
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
'Error fetching person type fields: '
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
"crm.persontype.fields"
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
'crm.persontype.fields'
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
Copied
Was the article helpful?
Yes
No
Previous
Get List of Payment Methods
Next
Get List of Payer Types

---

## Get a list of payer types crm.persontype.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-person-type-list

Get a list of payer types crm.persontype.list | Bitrix24 REST API and Marketplace Applications
Get a list of payer types crm.persontype.list
Get a list of payer types crm.persontype.list
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a list of payer types.
Note
For payment systems used in CRM (for invoices, deals), payer types should be retrieved through the
crm.persontype.list
method. If a payment system is being created for orders, then the
sale.persontype.list
method should be used.
Name
type
Description
order
Sorting fields
filter
Filter fields
Code examples
Code examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"ID":"ASC"},"filter":{"NAME":"CRM_COMPANY"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.persontype.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"ID":"ASC"},"filter":{"NAME":"CRM_COMPANY"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.persontype.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.persontype.list'
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
"NAME"
:
"CRM_COMPANY"
,
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in chunks and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.persontype.list'
, {
order
: {
"ID"
:
"ASC"
},
filter
: {
"NAME"
:
"CRM_COMPANY"
,
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.persontype.list'
, {
order
: {
"ID"
:
"ASC"
},
filter
: {
"NAME"
:
"CRM_COMPANY"
,
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
'crm.persontype.list'
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
'NAME'
=>
'CRM_COMPANY'
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
if
(
$response
->
more
()) {
$response
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
'Error listing person types: '
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
"crm.persontype.list"
, {
order
: {
"ID"
:
"ASC"
},
filter
: {
"NAME"
:
"CRM_COMPANY"
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
'crm.persontype.list'
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
'NAME'
=>
'CRM_COMPANY'
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
Copied
Was the article helpful?
Yes
No
Previous
Get Fields for Payer Types
Next
Get Link to Invoice

---

## Get a link to the invoice crm.invoice.getexternallink

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/crm-invoice-get-external-link

Get a link to the invoice crm.invoice.getexternallink | Bitrix24 REST API and Marketplace Applications
Get a link to the invoice crm.invoice.getexternallink
Get a link to the invoice crm.invoice.getexternallink
Method parameters
Code examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
Universal methods for invoices
The method returns a public link for the online invoice.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
id
integer
Invoice identifier
Code examples
Code examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_invoice_id"}' \ # Replace 'your_invoice_id' with the actual invoice ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.invoice.getexternallink
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_invoice_id","auth":"**put_access_token_here**"}' \ # Replace 'your_invoice_id' with the actual invoice ID
https://**put_your_bitrix24_address**/rest/crm.invoice.getexternallink
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
"crm.invoice.getexternallink"
,
{
"id"
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
log
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
'crm.invoice.getexternallink'
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
'Error calling crm.invoice.getexternallink: '
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
"crm.invoice.getexternallink"
,
{
"id"
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
log
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
'your_invoice_id'
;
// Replace 'your_invoice_id' with the actual invoice ID
$result
=
CRest
::
call
(
'crm.invoice.getexternallink'
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
Copied
Was the article helpful?
Yes
No
Previous
Get List of Payer Types
Next
Events

---

## Events

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/index

Events | Bitrix24 REST API and Marketplace Applications
Events
Events
Permissions
Scope
:
crm
|
Who can subscribe
:
any user
Event
Triggered
onCrmInvoiceAdd
when an invoice is created
onCrmInvoiceDelete
when an invoice is deleted
onCrmInvoiceSetStatus
when the status of an invoice is changed
onCrmInvoiceUpdate
when an invoice is updated
onCrmInvoiceUserFieldAdd
when a custom field is added
onCrmInvoiceUserFieldUpdate
when a custom field is modified
onCrmInvoiceUserFieldDelete
when a custom field is deleted
onCrmInvoiceUserFieldSetEnumValues
when the set of values for a custom list-type field is changed
onCrmInvoiceRecurringAdd
when a new recurring invoice is created
onCrmInvoiceRecurringUpdate
when a recurring invoice is updated
onCrmInvoiceRecurringDelete
when a recurring invoice is deleted
onCrmInvoiceRecurringExpose
when a new invoice is issued from a recurring invoice
Copied
Was the article helpful?
Yes
No
Previous
Get Link to Invoice
Next
On Invoice Addition

---

## Event on invoice addition onCrmInvoiceAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-add

Event on invoice addition onCrmInvoiceAdd | Bitrix24 REST API and Marketplace Applications
Parameters
Event on invoice addition onCrmInvoiceAdd
The event is triggered when an invoice is created.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
array
The array contains the field ID with the value of the created invoice identifier
Copied
Was the article helpful?
Yes
No
Previous
Events
Next
On Invoice Deletion

---

## Event onCrmInvoiceDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-delete

Event onCrmInvoiceDelete | Bitrix24 REST API and Marketplace Applications
Parameters
Event onCrmInvoiceDelete
This event is triggered when an invoice is deleted.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
array
The array contains the field ID with the value of the deleted invoice's identifier
Copied
Was the article helpful?
Yes
No
Previous
On Invoice Addition
Next
On Invoice Status Change

---

## Event onCrmInvoiceSetStatus for Invoice Status Change

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-set-status

Event onCrmInvoiceSetStatus for Invoice Status Change | Bitrix24 REST API and Marketplace Applications
Parameters
Event onCrmInvoiceSetStatus for Invoice Status Change
This event is triggered when the status of an invoice is changed.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
array
The array contains the field ID with the value of the invoice identifier whose status has been changed
Copied
Was the article helpful?
Yes
No
Previous
On Invoice Deletion
Next
On Invoice Update

---

## Event onCrmInvoiceUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-update

Event onCrmInvoiceUpdate | Bitrix24 REST API and Marketplace Applications
Parameters
Event onCrmInvoiceUpdate
The event is triggered when an invoice is updated.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
array
The array contains the field ID with the value of the updated invoice identifier
Copied
Was the article helpful?
Yes
No
Previous
On Invoice Status Change
Next
On Custom Field Addition

---

## Event for Adding Custom Field onCrmInvoiceUserFieldAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-user-field-add

Event for Adding Custom Field onCrmInvoiceUserFieldAdd | Bitrix24 REST API and Marketplace Applications
Parameters
Event for Adding Custom Field onCrmInvoiceUserFieldAdd
The event is triggered when a custom field is added.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the custom field
entityId
string
Symbolic identifier of the entity for which the field was created
fieldName
string
Name of the created custom field
Copied
Was the article helpful?
Yes
No
Previous
On Invoice Update
Next
On Custom Field Update

---

## Event onCrmInvoiceUserFieldUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-user-field-update

Event onCrmInvoiceUserFieldUpdate | Bitrix24 REST API and Marketplace Applications
Parameters
Event onCrmInvoiceUserFieldUpdate
The event is triggered when a custom field is updated.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the custom field
entityId
string
Symbolic identifier of the entity for which the field was created
fieldName
string
Name of the created custom field
Copied
Was the article helpful?
Yes
No
Previous
On Custom Field Addition
Next
On Custom Field Deletion

---

## Event for Deleting a Custom Field onCrmInvoiceUserFieldDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-user-field-delete

Event for Deleting a Custom Field onCrmInvoiceUserFieldDelete | Bitrix24 REST API and Marketplace Applications
Parameters
Event for Deleting a Custom Field onCrmInvoiceUserFieldDelete
The event is triggered when a custom field is deleted.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the custom field
entityId
string
Symbolic identifier of the entity for which the field was created
fieldName
string
Name of the created custom field
Copied
Was the article helpful?
Yes
No
Previous
On Custom Field Update
Next
On Changing Values for List-Type Custom Field

---

## Event for Changing Values of Custom List Field onCrmInvoiceUserFieldSetEnumValues

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-user-field-set-enum-values

Event for Changing Values of Custom List Field onCrmInvoiceUserFieldSetEnumValues | Bitrix24 REST API and Marketplace Applications
Parameters
Event for Changing Values of Custom List Field onCrmInvoiceUserFieldSetEnumValues
The event is triggered when the set of values for a custom list field is changed.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the custom field
entityId
string
Symbolic identifier of the entity for which the field was created
fieldName
string
Name of the created custom field
Copied
Was the article helpful?
Yes
No
Previous
On Custom Field Deletion
Next
On New Recurring Invoice Addition

---

## Event for Adding a New Recurring Invoice onCrmInvoiceRecurringAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-recurring-add

Event for Adding a New Recurring Invoice onCrmInvoiceRecurringAdd | Bitrix24 REST API and Marketplace Applications
Event for Adding a New Recurring Invoice onCrmInvoiceRecurringAdd
Event for Adding a New Recurring Invoice onCrmInvoiceRecurringAdd
This event is triggered when a new recurring invoice is created.
Name
type
Description
FIELDS
array
The array contains the following fields:
ID
— the value of the record identifier in the recurring invoice settings table
RECURRING_INVOICE_ID
— the value of the recurring invoice template identifier
Copied
Was the article helpful?
Yes
No
Previous
On Changing Values for List-Type Custom Field
Next
On Recurring Invoice Update

---

## Event on Update Recurring Invoice onCrmInvoiceRecurringUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-recurring-update

Event on Update Recurring Invoice onCrmInvoiceRecurringUpdate | Bitrix24 REST API and Marketplace Applications
Parameters
Event on Update Recurring Invoice onCrmInvoiceRecurringUpdate
The event is triggered when a recurring invoice is updated.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
array
The array contains the following fields:
ID
— the value of the record identifier in the recurring invoice settings table
RECURRING_INVOICE_ID
— the value of the recurring invoice template identifier
Copied
Was the article helpful?
Yes
No
Previous
On New Recurring Invoice Addition
Next
On Recurring Invoice Deletion

---

## Event for Deleting Recurring Invoice onCrmInvoiceRecurringDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-recurring-delete

Event for Deleting Recurring Invoice onCrmInvoiceRecurringDelete | Bitrix24 REST API and Marketplace Applications
Parameters
Event for Deleting Recurring Invoice onCrmInvoiceRecurringDelete
This event is triggered when a recurring invoice is deleted.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
array
The array contains the field ID with the value of the record identifier in the recurring invoice settings table
Copied
Was the article helpful?
Yes
No
Previous
On Recurring Invoice Update
Next
On Issuing New Invoice from Recurring

---

## Event for Issuing a New Invoice from Regular onCrmInvoiceRecurringExpose

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/invoice/events-invoice/on-crm-invoice-recurring-expose

Event for Issuing a New Invoice from Regular onCrmInvoiceRecurringExpose | Bitrix24 REST API and Marketplace Applications
Parameters
Event for Issuing a New Invoice from Regular onCrmInvoiceRecurringExpose
The event is triggered when a new invoice is issued from a recurring invoice.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
array
The array contains the following fields:
ID
— the identifier value of the record in the recurring invoice settings table
RECURRING_INVOICE_ID
— the identifier value of the recurring invoice template
INVOICE_ID
— the ID value of the new invoice created based on the recurring invoice
Copied
Was the article helpful?
Yes
No
Previous
On Recurring Invoice Deletion
Next
Overview of Methods

---

