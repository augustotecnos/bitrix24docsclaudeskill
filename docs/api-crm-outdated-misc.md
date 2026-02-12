---
description: 'CRM Outdated Misc (deprecated): VAT, measures, categories, streams'
methods:
- crm.category.
- crm.category.add
- crm.category.delete
- crm.category.fields
- crm.category.get
- crm.category.list
- crm.category.update
- crm.deal.category.add
- crm.deal.category.default.get
- crm.deal.category.default.set
- crm.deal.category.delete
- crm.deal.category.fields
- crm.deal.category.get
- crm.deal.category.list
- crm.deal.category.stage.list
- crm.deal.category.status
- crm.deal.category.update
- crm.dealcategory.add
- crm.dealcategory.default.get
- crm.dealcategory.default.set
- crm.dealcategory.delete
- crm.dealcategory.fields
- crm.dealcategory.get
- crm.dealcategory.list
- crm.dealcategory.stage.list
- crm.dealcategory.status
- crm.dealcategory.update
- crm.item.productrow.
- crm.livefeedmessage.add
- crm.livefeedmessage.md
pages: 32
title: 'CRM Outdated Misc (deprecated): VAT, measures, categories, streams'
---
# CRM Outdated Misc (deprecated): VAT, measures, categories, streams
> CRM Outdated Misc (deprecated): VAT, measures, categories, streams
> **32 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Deprecated CRM Methods](#deprecated-crm-methods)
- [Overview of Methods](#overview-of-methods)
- [Add Measurement Unit crm.measure.add](#add-measurement-unit-crmmeasureadd)
- [Update Measurement Unit crm.measure.update](#update-measurement-unit-crmmeasureupdate)
- [Get the values of the fields of the unit of measurement crm.measure.get](#get-the-values-of-the-fields-of-the-unit-of-measur)
- [Get the list of measurement units crm.measure.list](#get-the-list-of-measurement-units-crmmeasurelist)
- [Delete Measurement Unit crm.measure.delete](#delete-measurement-unit-crmmeasuredelete)
- [Get available fields of crm.measure.fields](#get-available-fields-of-crmmeasurefields)
- [Event Overview](#event-overview)
- [Event for Adding a New Unit of Measurement onCrmMeasureAdd](#event-for-adding-a-new-unit-of-measurement-oncrmme)
- [Event onCrmMeasureUpdate](#event-oncrmmeasureupdate)
- [Event onCrmMeasureDelete](#event-oncrmmeasuredelete)
- [Deal Categories](#deal-categories)
- [Create a new deal category crm.dealcategory.add](#create-a-new-deal-category-crmdealcategoryadd)
- [Delete deal category crm.dealcategory.delete](#delete-deal-category-crmdealcategorydelete)
- [Get Deal Category crm.dealcategory.get](#get-deal-category-crmdealcategoryget)
- [Get descriptions of fields for deal categories crm.dealcategory.fields](#get-descriptions-of-fields-for-deal-categories-crm)
- [Filter Deal Categories crm.dealcategory.list](#filter-deal-categories-crmdealcategorylist)
- [Update deal category crm.dealcategory.update](#update-deal-category-crmdealcategoryupdate)
- [Get Settings for Default Deal Category crm.dealcategory.default.get](#get-settings-for-default-deal-category-crmdealcate)
- [Set Default Deal Category Settings crm.dealcategory.default.set](#set-default-deal-category-settings-crmdealcategory)
- [Get the identifier of the directory where the stages of deals are stored crm.dealcategory.status](#get-the-identifier-of-the-directory-where-the-stag)
- [Get the list of deal stages for the method crm.dealcategory.stage.list](#get-the-list-of-deal-stages-for-the-method-crmdeal)
- [CRM Feed](#crm-feed)
- [Send a message to the CRM Feed crm.livefeedmessage.add](#send-a-message-to-the-crm-feed-crmlivefeedmessagea)
- [VAT Rates: Overview of Methods](#vat-rates-overview-of-methods)
- [Create VAT Rate crm.vat.add](#create-vat-rate-crmvatadd)
- [Update Existing VAT Rate crm.vat.update](#update-existing-vat-rate-crmvatupdate)
- [Get VAT Rate by ID crm.vat.get](#get-vat-rate-by-id-crmvatget)
- [Get a list of VAT rates by filter crm.vat.list](#get-a-list-of-vat-rates-by-filter-crmvatlist)
- [Delete VAT Rate crm.vat.delete](#delete-vat-rate-crmvatdelete)
- [Get VAT Rate Fields crm.vat.fields](#get-vat-rate-fields-crmvatfields)

---

## Deprecated CRM Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/index

Deprecated CRM Methods | Bitrix24 REST API and Marketplace Applications
Deprecated CRM Methods
Deprecated CRM Methods
Scope:
crm
Who can execute the method: any user
Space
Description
Catalog
Methods for working with product catalogs
Product Items
Methods for working with product items
Units of Measurement
Methods for working with units of measurement
Invoice Statuses
Methods for working with invoice statuses
Deal Directions
Methods for working with deal directions
Products
Methods for working with products
Product Sections
Methods for working with product sections
CRM Stream
Methods for working with the Stream
Invoices
Methods for working with invoices
Copied
Was the article helpful?
Yes
No
Previous
Status
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: any user
Method
Description
crm.measure.add
Adds a new unit of measurement
crm.measure.update
Updates an existing unit of measurement
crm.measure.get
Returns the values of all fields of a unit of measurement by its identifier
crm.measure.list
Returns a list of units of measurement
crm.measure.delete
Deletes a unit of measurement
crm.measure.fields
Returns the description of fields for units of measurement
Copied
Was the article helpful?
Yes
No
Previous
Get List of Fields by Filter
Next
Add Unit of Measurement

---

## Add Measurement Unit crm.measure.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/crm-measure-add

Add Measurement Unit crm.measure.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Measurement Unit crm.measure.add
Method Parameters
Parameter fields
Code Examples
Continue Learning
Scope:
crm
Who can execute the method: any user
This method adds a new measurement unit.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
array
Set of fields — an array of the form
array("field"=>"value"[, ...])
, containing the values of the measurement unit fields.
To find out the required format of the fields, execute the method
crm.measure.fields
and check the format of the received values for these fields
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
CODE
*
integer
Code
MEASURE_TITLE
*
string
Name of the measurement unit
SYMBOL_RUS
string
Symbol
SYMBOL_INTL
string
International symbol
SYMBOL_LETTER_INTL
string
International letter code
IS_DEFAULT
char
Default
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
'{"fields":{"CODE":"212","MEASURE_TITLE":"Watt","SYMBOL_RUS":"W","SYMBOL_INTL":"W","SYMBOL_LETTER_INTL":"WTT","IS_DEFAULT":"N"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.measure.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"CODE":"212","MEASURE_TITLE":"Watt","SYMBOL_RUS":"W","SYMBOL_INTL":"W","SYMBOL_LETTER_INTL":"WTT","IS_DEFAULT":"N"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.measure.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.measure.add'
,
{
fields
: {
"CODE"
:
"212"
,
"MEASURE_TITLE"
:
"Watt"
,
"SYMBOL_RUS"
:
"W"
,
"SYMBOL_INTL"
:
"W"
,
"SYMBOL_LETTER_INTL"
:
"WTT"
,
"IS_DEFAULT"
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
(
'Created measurement unit with ID '
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
$response
=
$b24Service
->core
->
call
(
'crm.measure.add'
,
[
'fields'
=> [
'CODE'
=>
'212'
,
'MEASURE_TITLE'
=>
'Watt'
,
'SYMBOL_RUS'
=>
'W'
,
'SYMBOL_INTL'
=>
'W'
,
'SYMBOL_LETTER_INTL'
=>
'WTT'
,
'IS_DEFAULT'
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
echo
'Created measurement unit with ID '
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
'Error creating measurement unit: '
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
"crm.measure.add"
,
{
fields
: {
"CODE"
:
"212"
,
"MEASURE_TITLE"
:
"Watt"
,
"SYMBOL_RUS"
:
"W"
,
"SYMBOL_INTL"
:
"W"
,
"SYMBOL_LETTER_INTL"
:
"WTT"
,
"IS_DEFAULT"
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
console
.
info
(
"Created measurement unit with ID "
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
'crm.measure.add'
,
[
'fields'
=>
[
'CODE'
=>
'212'
,
'MEASURE_TITLE'
=>
'Watt'
,
'SYMBOL_RUS'
=>
'W'
,
'SYMBOL_INTL'
=>
'W'
,
'SYMBOL_LETTER_INTL'
=>
'WTT'
,
'IS_DEFAULT'
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
Continue Learning
Continue Learning
Update Measurement Unit crm.measure.update
Get the values of the fields of the unit of measurement crm.measure.get
Get the list of measurement units crm.measure.list
Delete Measurement Unit crm.measure.delete
Get available fields of crm.measure.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Unit of Measurement

---

## Update Measurement Unit crm.measure.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/crm-measure-update

Update Measurement Unit crm.measure.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Measurement Unit crm.measure.update
Method Parameters
Code Examples
Continue Learning
Scope:
crm
Who can execute the method: any user
This method updates an existing measurement unit.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
Identifier of the measurement unit
fields
array
Set of fields
— an array of the form
array("field_to_update"=>"value"[, ...])
, where the field to update can take values returned by the method
crm.measure.fields
.
To find out the required format of the fields, execute the method
crm.measure.fields
and check the format of the returned values for these fields
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
'{"id":"**put_id_here**","fields":{"MEASURE_TITLE":"**put_new_title_here**"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.measure.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"**put_id_here**","fields":{"MEASURE_TITLE":"**put_new_title_here**"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.measure.update
try
{
const
id =
prompt
(
"Enter ID"
);
const
title =
prompt
(
"Enter new name for the measurement unit"
);
const
response =
await
$b24.
callMethod
(
"crm.measure.update"
,
{
id
: id,
fields
: {
"MEASURE_TITLE"
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
$title
=
readline
(
"Enter new name for the measurement unit"
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
'crm.measure.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'MEASURE_TITLE'
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
'Error updating measure: '
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
title =
prompt
(
"Enter new name for the measurement unit"
);
BX24
.
callMethod
(
"crm.measure.update"
,
{
id
: id,
fields
: {
"MEASURE_TITLE"
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
''
;
// Set the ID here
$title
=
''
;
// Set the new title here
$result
=
CRest
::
call
(
'crm.measure.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'MEASURE_TITLE'
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
Continue Learning
Continue Learning
Add Measurement Unit crm.measure.add
Get the values of the fields of the unit of measurement crm.measure.get
Get the list of measurement units crm.measure.list
Delete Measurement Unit crm.measure.delete
Get available fields of crm.measure.fields
Copied
Was the article helpful?
Yes
No
Previous
Add Unit of Measurement
Next
Retrieve Unit of Measurement Field Values

---

## Get the values of the fields of the unit of measurement crm.measure.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/crm-measure-get

Get the values of the fields of the unit of measurement crm.measure.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the values of the fields of the unit of measurement crm.measure.get
Method Parameters
Code Examples
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns the values of all fields of the unit of measurement by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
Description
id
*
Identifier of the unit of measurement
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
'{"id":"**put_id_here**"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.measure.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"**put_id_here**","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.measure.get
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
"crm.measure.get"
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
'crm.measure.get'
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
'Error getting measure: '
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
"crm.measure.get"
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
''
;
// Set the ID here
$result
=
CRest
::
call
(
'crm.measure.get'
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
Continue Learning
Continue Learning
Add Measurement Unit crm.measure.add
Update Measurement Unit crm.measure.update
Get the list of measurement units crm.measure.list
Delete Measurement Unit crm.measure.delete
Get available fields of crm.measure.fields
Copied
Was the article helpful?
Yes
No
Previous
Update Unit of Measurement
Next
Get List of Units of Measurement

---

## Get the list of measurement units crm.measure.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/crm-measure-list

Get the list of measurement units crm.measure.list | Bitrix24 REST API and Marketplace Applications
Code examples
Get the list of measurement units crm.measure.list
Code examples
Continue exploring
Scope:
crm
Who can execute the method: any user
The method returns a list of measurement units.
See the description of
list methods
.
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
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"ID":"ASC"},"filter":{"IS_DEFAULT":"Y"},"select":["ID","CODE","STAGE_ID","SYMBOL_INTL","SYMBOL_INTL"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.measure.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"ID":"ASC"},"filter":{"IS_DEFAULT":"Y"},"select":["ID","CODE","STAGE_ID","SYMBOL_INTL","SYMBOL_INTL"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.measure.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.measure.list'
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
"IS_DEFAULT"
:
"Y"
},
select
: [
"ID"
,
"CODE"
,
"STAGE_ID"
,
"SYMBOL_INTL"
,
"SYMBOL_INTL"
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.measure.list'
, {
order
: {
"ID"
:
"ASC"
},
filter
: {
"IS_DEFAULT"
:
"Y"
},
select
: [
"ID"
,
"CODE"
,
"STAGE_ID"
,
"SYMBOL_INTL"
,
"SYMBOL_INTL"
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.measure.list'
, {
order
: {
"ID"
:
"ASC"
},
filter
: {
"IS_DEFAULT"
:
"Y"
},
select
: [
"ID"
,
"CODE"
,
"STAGE_ID"
,
"SYMBOL_INTL"
,
"SYMBOL_INTL"
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
'crm.measure.list'
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
'IS_DEFAULT'
=>
'Y'
],
'select'
=> [
'ID'
,
'CODE'
,
'STAGE_ID'
,
'SYMBOL_INTL'
,
'SYMBOL_INTL'
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
'Error fetching measure list: '
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
"crm.measure.list"
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
"IS_DEFAULT"
:
"Y"
},
select
: [
"ID"
,
"CODE"
,
"STAGE_ID"
,
"SYMBOL_INTL"
,
"SYMBOL_INTL"
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
'crm.measure.list'
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
'IS_DEFAULT'
=>
'Y'
],
'select'
=> [
'ID'
,
'CODE'
,
'STAGE_ID'
,
'SYMBOL_INTL'
,
'SYMBOL_INTL'
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
Continue exploring
Continue exploring
Add Measurement Unit crm.measure.add
Update Measurement Unit crm.measure.update
Get the values of the fields of the unit of measurement crm.measure.get
Delete Measurement Unit crm.measure.delete
Get available fields of crm.measure.fields
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Unit of Measurement Field Values
Next
Delete Unit of Measurement

---

## Delete Measurement Unit crm.measure.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/crm-measure-delete

Delete Measurement Unit crm.measure.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Measurement Unit crm.measure.delete
Method Parameters
Code Examples
Continue Learning
Scope:
crm
Who can execute the method: any user
This method deletes a measurement unit.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
Description
id
*
Identifier of the measurement unit
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
'{"id":"**put_id_here**"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.measure.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"**put_id_here**","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.measure.delete
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
"crm.measure.delete"
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
'crm.measure.delete'
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
'Error deleting measure: '
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
"crm.measure.delete"
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
''
;
// Set the ID here
$result
=
CRest
::
call
(
'crm.measure.delete'
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
Continue Learning
Continue Learning
Add Measurement Unit crm.measure.add
Update Measurement Unit crm.measure.update
Get the values of the fields of the unit of measurement crm.measure.get
Get the list of measurement units crm.measure.list
Get available fields of crm.measure.fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of Units of Measurement
Next
Retrieve Available Unit of Measurement Fields

---

## Get available fields of crm.measure.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/crm-measure-fields

Get available fields of crm.measure.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get available fields of crm.measure.fields
Code Examples
Returned Fields
Continue Learning
Scope:
crm
Who can execute the method: any user
The method returns a description of the fields for measurement units.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.measure.fields
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
https://**put_your_bitrix24_address**/rest/crm.measure.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.measure.fields"
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
'crm.measure.fields'
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
'Error fetching CRM measure fields: '
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
"crm.measure.fields"
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
'crm.measure.fields'
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
Returned Fields
Returned Fields
Field
type
Description
Note
CODE
integer
Unit code
Required
ID
integer
Identifier
Read-only
IS_DEFAULT
char
Default
MEASURE_TITLE
string
Measurement unit name
Required
SYMBOL_INTL
string
International symbol
SYMBOL_LETTER_INTL
string
International letter code
SYMBOL_RUS
string
Symbol
Continue Learning
Continue Learning
Add Measurement Unit crm.measure.add
Update Measurement Unit crm.measure.update
Get the values of the fields of the unit of measurement crm.measure.get
Get the list of measurement units crm.measure.list
Delete Measurement Unit crm.measure.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete Unit of Measurement
Next
Overview of Events

---

## Event Overview

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/events/index

Event Overview | Bitrix24 REST API and Marketplace Applications
Event Overview
Event Overview
Scope:
crm
Who can subscribe: any user
Event
Triggered
onCrmMeasureAdd
After a new unit of measurement is added to the account
onCrmMeasureUpdate
After a unit of measurement is updated in the account
onCrmMeasureDelete
After a unit of measurement is deleted from the account
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Available Unit of Measurement Fields
Next
On Adding a New Unit of Measurement

---

## Event for Adding a New Unit of Measurement onCrmMeasureAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/events/on-crm-measure-add

Event for Adding a New Unit of Measurement onCrmMeasureAdd | Bitrix24 REST API and Marketplace Applications
Response Handling
Event for Adding a New Unit of Measurement onCrmMeasureAdd
Response Handling
Error Handling
Scope:
crm
Who can subscribe:
any user
The event
onCrmMeasureAdd
is triggered after a new unit of measurement is added to the account.
Response Handling
Response Handling
HTTP status:
200
Returns an array:
array
(
'FIELDS'
=>
array
(
'ID'
=>
$id
))
where
$id
is the identifier of the created unit of measurement.
Error Handling
Error Handling
HTTP status:
40x
,
50x
In case of errors, the exception
\Bitrix\Rest\RestException
is thrown.
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
On Updating a Unit of Measurement

---

## Event onCrmMeasureUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/events/on-crm-measure-update

Event onCrmMeasureUpdate | Bitrix24 REST API and Marketplace Applications
Response Handling
Event onCrmMeasureUpdate
Response Handling
Error Handling
Scope:
crm
Who can subscribe:
any user
The event
onCrmMeasureUpdate
is triggered after the unit of measurement is changed on the account.
Response Handling
Response Handling
HTTP status:
200
Returns an array:
array
(
'FIELDS'
=>
array
(
'ID'
=>
$id
))
where
$id
is the identifier of the modified unit of measurement.
Error Handling
Error Handling
HTTP status:
40x
,
50x
In case of errors, the exception
\Bitrix\Rest\RestException
is thrown.
Copied
Was the article helpful?
Yes
No
Previous
On Adding a New Unit of Measurement
Next
On Deleting a Unit of Measurement

---

## Event onCrmMeasureDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/measure/events/on-crm-measure-delete

Event onCrmMeasureDelete | Bitrix24 REST API and Marketplace Applications
Response Handling
Event onCrmMeasureDelete
Response Handling
Error Handling
Scope:
crm
Who can subscribe:
any user
The event
onCrmMeasureDelete
is triggered after a unit of measurement is deleted from the account.
Response Handling
Response Handling
HTTP status:
200
Returns an array:
array
(
'FIELDS'
=>
array
(
'ID'
=>
$id
))
where
$id
is the identifier of the deleted unit of measurement.
Error Handling
Error Handling
HTTP status:
40x
,
50x
In case of errors, the exception
\Bitrix\Rest\RestException
is thrown.
Copied
Was the article helpful?
Yes
No
Previous
On Updating a Unit of Measurement
Next
Overview of Methods

---

## Deal Categories

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/index

Deal Categories | Bitrix24 REST API and Marketplace Applications
Deal Categories
Deal Categories
Scope:
crm
Who can execute methods: any user
Method
Description
crm.deal.category.add
Creates a new deal category
crm.deal.category.delete
Deletes a deal category
crm.deal.category.get
Retrieves a deal category by its identifier
crm.deal.category.fields
Gets the fields of the invoice status
crm.deal.category.list
Retrieves the description of deal category fields
crm.deal.category.update
Updates an existing deal category
crm.deal.category.default.get
Gets the settings for the default deal category
crm.deal.category.default.set
Sets the settings for the default deal category
crm.deal.category.status
Returns the identifier of the directory where deal stages are stored
crm.deal.category.stage.list
Returns a list of deal stages for the category
Copied
Was the article helpful?
Yes
No
Previous
Update Invoice Status
Next
Create Deal Direction

---

## Create a new deal category crm.dealcategory.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-add

Create a new deal category crm.dealcategory.add | Bitrix24 REST API and Marketplace Applications
Create a new deal category crm.dealcategory.add
Create a new deal category crm.dealcategory.add
Method parameters
Code examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
crm.category.add
The method creates a new deal category.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
fields
array
Field values for creating a deal category.
To find out the required format of the fields, execute the method
crm.dealcategory.fields
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
-d '{"fields":{"NAME":"New Category","SORT":"20"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.add
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"NAME":"New Category","SORT":"20"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.dealcategory.add'
,
{
fields
:
{
"NAME"
:
"New Category"
,
"SORT"
:
"20"
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
'Created category with ID '
+ result);
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
'crm.dealcategory.add'
,
[
'fields'
=> [
'NAME'
=>
'New Category'
,
'SORT'
=>
'20'
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
'Created category with ID '
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
'Error creating deal category: '
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
"crm.dealcategory.add"
,
{
fields
:
{
"NAME"
:
"New Category"
,
"SORT"
:
"20"
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
"Created category with ID "
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
'crm.dealcategory.add'
,
[
'fields'
=>
[
'NAME'
=>
'New Category'
,
'SORT'
=>
'20'
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
Overview of Methods
Next
Delete Deal Direction

---

## Delete deal category crm.dealcategory.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-delete

Delete deal category crm.dealcategory.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete deal category crm.dealcategory.delete
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
crm.category.delete
The method deletes a deal category.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the category
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
-d '{"id":"1"}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"1","auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.delete
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
"crm.dealcategory.delete"
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
'crm.dealcategory.delete'
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
'Error deleting deal category: '
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
"crm.dealcategory.delete"
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
1
;
// Replace 1 with the actual ID
$result
=
CRest
::
call
(
'crm.dealcategory.delete'
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
Create Deal Direction
Next
Get Deal Direction

---

## Get Deal Category crm.dealcategory.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-get

Get Deal Category crm.dealcategory.get | Bitrix24 REST API and Marketplace Applications
Get Deal Category crm.dealcategory.get
Get Deal Category crm.dealcategory.get
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
crm.category.get
The method returns the deal category by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the category
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
-d '{"id":"1"}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"1","auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.get
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
"crm.dealcategory.get"
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
'crm.dealcategory.get'
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
'Error getting deal category: '
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
"crm.dealcategory.get"
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
1
;
// Replace 1 with the actual ID
$result
=
CRest
::
call
(
'crm.dealcategory.get'
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
Delete Deal Direction
Next
Get All Fields of Deal Direction

---

## Get descriptions of fields for deal categories crm.dealcategory.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-fields

Get descriptions of fields for deal categories crm.dealcategory.fields | Bitrix24 REST API and Marketplace Applications
Get descriptions of fields for deal categories crm.dealcategory.fields
Get descriptions of fields for deal categories crm.dealcategory.fields
Code Examples
Returned Data
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
crm.category.fields
The method returns descriptions of fields for deal categories.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.dealcategory.fields"
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
'crm.dealcategory.fields'
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
'Error fetching deal category fields: '
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
"crm.dealcategory.fields"
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
'crm.dealcategory.fields'
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
Name
type
Description
CREATED_DATE
datetime
Creation date
ID
integer
Identifier of the deal category
IS_LOCKED
char
Locked
NAME
*
string
Name of the category
SORT
integer
Sorting
Copied
Was the article helpful?
Yes
No
Previous
Get Deal Direction
Next
Get List of Deal Directions by Filter

---

## Filter Deal Categories crm.dealcategory.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-list

Filter Deal Categories crm.dealcategory.list | Bitrix24 REST API and Marketplace Applications
Filter Deal Categories crm.dealcategory.list
Filter Deal Categories crm.dealcategory.list
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
crm.category.list
The method returns a list of deal categories based on the filter. It is an implementation of list methods for deal categories.
Method Parameters
Method Parameters
See the description of
list methods
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
-d '{"order":{"SORT":"ASC"},"filter":{"IS_LOCKED":"N"},"select":["ID","NAME","SORT"]}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"SORT":"ASC"},"filter":{"IS_LOCKED":"N"},"select":["ID","NAME","SORT"],"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.dealcategory.list'
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
"IS_LOCKED"
:
"N"
},
select
: [
"ID"
,
"NAME"
,
"SORT"
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.dealcategory.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"IS_LOCKED"
:
"N"
},
select
: [
"ID"
,
"NAME"
,
"SORT"
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.dealcategory.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"IS_LOCKED"
:
"N"
},
select
: [
"ID"
,
"NAME"
,
"SORT"
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
'crm.dealcategory.list'
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
'IS_LOCKED'
=>
'N'
],
'select'
=> [
'ID'
,
'NAME'
,
'SORT'
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
'Error fetching deal categories: '
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
"crm.dealcategory.list"
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
"IS_LOCKED"
:
"N"
},
//Y - all categories, N - all categories except deleted. Deleted categories are not permanently removed from the database but only blocked.
select
: [
"ID"
,
"NAME"
,
"SORT"
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
'crm.dealcategory.list'
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
'IS_LOCKED'
=>
'N'
],
'select'
=> [
'ID'
,
'NAME'
,
'SORT'
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
Get All Fields of Deal Direction
Next
Update Deal Direction

---

## Update deal category crm.dealcategory.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-update

Update deal category crm.dealcategory.update | Bitrix24 REST API and Marketplace Applications
Parameters
Update deal category crm.dealcategory.update
Parameters
Code examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
crm.category.update
The method updates an existing deal category.
Parameters
Parameters
Name
type
Description
id
integer
Identifier of the category
fields
array
Field values for updating the deal category.
To find out the required format of the fields, execute the method
crm.dealcategory.fields
and check the format of the incoming values of these fields (except for fields marked with the attributes
isReadOnly
and
isImmutable
)
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
-d '{"id":"1","fields":{"SORT":"100"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.update
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"1","fields":{"SORT":"100"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.update
try
{
const
id =
prompt
(
"Enter ID"
);
const
sort =
prompt
(
"Enter sort order"
);
const
parsedSort =
parseInt
(sort);
if
(
isNaN
(parsedSort) || parsedSort <
0
)
{
parsedSort =
0
;
}
const
response =
await
$b24.
callMethod
(
"crm.dealcategory.update"
,
{
id
: id,
fields
: {
"SORT"
: parsedSort }
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
= (
int
)
readline
(
"Enter ID"
);
$sort
= (
int
)
readline
(
"Enter sort order"
);
if
(
is_nan
(
$sort
) ||
$sort
<
0
) {
$sort
=
0
;
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
'crm.dealcategory.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'SORT'
=>
$sort
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
'Error updating deal category: '
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
sort =
prompt
(
"Enter sort order"
);
sort =
parseInt
(sort);
if
(
isNaN
(sort) || sort <
0
)
{
sort =
0
;
}
BX24
.
callMethod
(
"crm.dealcategory.update"
,
{
id
: id,
fields
: {
"SORT"
: sort }
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
1
;
// Replace 1 with the actual ID
$sort
=
100
;
// Replace 100 with the actual sort value
$result
=
CRest
::
call
(
'crm.dealcategory.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'SORT'
=>
$sort
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
Get List of Deal Directions by Filter
Next
Get Default Direction Settings

---

## Get Settings for Default Deal Category crm.dealcategory.default.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-default-get

Get Settings for Default Deal Category crm.dealcategory.default.get | Bitrix24 REST API and Marketplace Applications
Get Settings for Default Deal Category crm.dealcategory.default.get
Get Settings for Default Deal Category crm.dealcategory.default.get
Code Examples
Result:
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use funnel methods
crm.category.*
The method retrieves settings for the default deal category.
Without parameters
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.default.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.default.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.dealcategory.default.get'
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
'crm.dealcategory.default.get'
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
'Error getting default deal category: '
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
"crm.dealcategory.default.get"
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
'crm.dealcategory.default.get'
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
Result:
Result:
{
ID
:
0
,
NAME
:
"Default"
}
Copied
Was the article helpful?
Yes
No
Previous
Update Deal Direction
Next
Set Default Direction Settings

---

## Set Default Deal Category Settings crm.dealcategory.default.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-default-set

Set Default Deal Category Settings crm.dealcategory.default.set | Bitrix24 REST API and Marketplace Applications
Set Default Deal Category Settings crm.dealcategory.default.set
Set Default Deal Category Settings crm.dealcategory.default.set
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use funnel methods
crm.category.*
This method records the settings for the default deal category.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
name
string
Name of the default category
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
-d '{"name":""}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.default.set
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"name":"","auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.default.set
try
{
const
response =
await
$b24.
callMethod
(
'crm.dealcategory.default.set'
,
{
"name"
:
""
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
'crm.dealcategory.default.set'
,
[
'name'
=>
''
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
'Error setting default deal category: '
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
"crm.dealcategory.default.set"
,
{
"name"
:
""
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
'crm.dealcategory.default.set'
,
[
'name'
=>
''
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
Get Default Direction Settings
Next
Get Identifier of the Reference with Deal Stages

---

## Get the identifier of the directory where the stages of deals are stored crm.dealcategory.status

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-status

Get the identifier of the directory where the stages of deals are stored crm.dealcategory.status | Bitrix24 REST API and Marketplace Applications
Get the identifier of the directory where the stages of deals are stored crm.dealcategory.status
Get the identifier of the directory where the stages of deals are stored crm.dealcategory.status
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use the funnel methods
crm.category.*
The method returns the identifier of the directory for storing stages based on the deal direction identifier.
This is a string of the format
DEAL_STAGE_[Direction Identifier]
. For example, for a direction with identifier 1, the string
"DEAL_STAGE_1"
will be returned.
The identifier is intended for use with the family of methods
crm.status.*
. For example, to create a new stage for a direction, it needs to be passed to the method
crm.status.add
as the
ENTITY_ID
parameter.
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Direction identifier
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
-d '{"id":"1"}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.status
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"1","auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.status
try
{
const
response =
await
$b24.
callMethod
(
"crm.dealcategory.status"
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
'crm.dealcategory.status'
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
'Error fetching deal category status: '
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
"crm.dealcategory.status"
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
1
;
// Replace 1 with the actual ID
$result
=
CRest
::
call
(
'crm.dealcategory.status'
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
Set Default Direction Settings
Next
Get List of Stages

---

## Get the list of deal stages for the method crm.dealcategory.stage.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/category-old/crm-deal-category-stage-list

Get the list of deal stages for the method crm.dealcategory.stage.list | Bitrix24 REST API and Marketplace Applications
Get the list of deal stages for the method crm.dealcategory.stage.list
Get the list of deal stages for the method crm.dealcategory.stage.list
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use funnel methods
crm.category.*
The method returns a list of deal stages for the category by its identifier. It is equivalent to calling the method
crm.status.list
with the
ENTITY_ID
parameter equal to the result of calling
crm.dealcategory.status
.
Method Parameters
Method Parameters
Name
type
Description
id
integer
Identifier of the category. If
id = 0
or nothing
is specified
, it will return the statuses of the "default" category. If
id > 0
for a non-existent category
, it returns nothing
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
-d '{"id":"1"}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.dealcategory.stage.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"1","auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.dealcategory.stage.list
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
'crm.dealcategory.stage.list'
,
{
id
: id },
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
'crm.dealcategory.stage.list'
, {
id
: id },
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
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
'crm.dealcategory.stage.list'
, {
id
: id },
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
'crm.dealcategory.stage.list'
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
"crm.dealcategory.stage.list"
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
1
;
// Replace 1 with the actual ID
$result
=
CRest
::
call
(
'crm.dealcategory.stage.list'
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
Empty quotes or not passing the parameter at all
For example, specifying id = 10, but there is no category with id=10 in the system.
Copied
Was the article helpful?
Yes
No
Previous
Get Identifier of the Reference with Deal Stages
Next
List of Methods

---

## CRM Feed

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/stream-old/index

CRM Feed | Bitrix24 REST API and Marketplace Applications
CRM Feed
CRM Feed
Scope:
crm
Who can execute methods: any user
Method
Description
crm.livefeedmessage.md
Sends a message to the CRM Feed
Copied
Was the article helpful?
Yes
No
Previous
On Deleting a Section
Next
Send a Message to the Feed

---

## Send a message to the CRM Feed crm.livefeedmessage.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/stream-old/crm-live-feed-message-add

Send a message to the CRM Feed crm.livefeedmessage.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Send a message to the CRM Feed crm.livefeedmessage.add
Method Parameters
Code Examples
Example 1
Example 2
Additional
Scope:
crm
Who can execute the method: any user
This method adds a message to the CRM feed.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
POST_TITLE
string
Message title
MESSAGE
text
Message text.
SPERM
Permissions to view the message, example:
"SPERM": {
"CRMCONTACT": ["CRMCONTACT3", "CRMCONTACT7"], // CRM contacts
"CRMCOMPANY": ["CRMCOMPANY1", "CRMCOMPANY3"], // CRM companies
"CRMDEAL": ["CRMDEAL3", "CRMDEAL5"], // CRM deals
"CRMLEAD": ["CRMLEAD9", "CRMLEAD11"], // CRM leads
"SG": ["SG5", "SG9"], // social network workgroups
"U": ["U1", "U3"], // users
"DR": ["DR1", "DR7"], // departments with subdivisions
}
ENTITYTYPEID
integer
Type of the entity where the message is published:
1 - lead;
2 - deal;
3 - contact;
4 - company
ENTITYID
integer
ID of the specific lead/deal/contact/company where the message is published.
FILES
file
Message files
Code Examples
Code Examples
How to Use Examples in Documentation
Example 1
Example 1
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"POST_TITLE":"A bit about the service","MESSAGE":"Bitrix24 is built on the Bitrix Framework platform.","SPERM":{"CRMCONTACT":["CRMCONTACT3","CRMCONTACT7"],"CRMCOMPANY":["CRMCOMPANY1","CRMCOMPANY3"],"CRMDEAL":["CRMDEAL3","CRMDEAL5"],"CRMLEAD":["CRMLEAD9","CRMLEAD11"],"SG":["SG5","SG9"],"U":["U1","U3"],"DR":["DR1","DR7"]},"ENTITYTYPEID":3,"ENTITYID":3}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.livefeedmessage.add
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"POST_TITLE":"A bit about the service","MESSAGE":"Bitrix24 is built on the Bitrix Framework platform.","SPERM":{"CRMCONTACT":["CRMCONTACT3","CRMCONTACT7"],"CRMCOMPANY":["CRMCOMPANY1","CRMCOMPANY3"],"CRMDEAL":["CRMDEAL3","CRMDEAL5"],"CRMLEAD":["CRMLEAD9","CRMLEAD11"],"SG":["SG5","SG9"],"U":["U1","U3"],"DR":["DR1","DR7"]},"ENTITYTYPEID":3,"ENTITYID":3},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.livefeedmessage.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.livefeedmessage.add"
,
{
fields
:
{
"POST_TITLE"
:
"A bit about the service"
,
"MESSAGE"
:
"Bitrix24 is built on the Bitrix Framework platform."
,
"SPERM"
: {
"CRMCONTACT"
: [
"CRMCONTACT3"
,
"CRMCONTACT7"
],
"CRMCOMPANY"
: [
"CRMCOMPANY1"
,
"CRMCOMPANY3"
],
"CRMDEAL"
: [
"CRMDEAL3"
,
"CRMDEAL5"
],
"CRMLEAD"
: [
"CRMLEAD9"
,
"CRMLEAD11"
],
"SG"
: [
"SG5"
,
"SG9"
],
"U"
: [
"U1"
,
"U3"
],
"DR"
: [
"DR1"
,
"DR7"
],
},
"ENTITYTYPEID"
:
3
,
"ENTITYID"
:
3
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
"Message created with ID "
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
'crm.livefeedmessage.add'
,
[
'fields'
=> [
'POST_TITLE'
=>
'A bit about the service'
,
'MESSAGE'
=>
'Bitrix24 is built on the Bitrix Framework platform.'
,
'SPERM'
=> [
'CRMCONTACT'
=> [
'CRMCONTACT3'
,
'CRMCONTACT7'
],
'CRMCOMPANY'
=> [
'CRMCOMPANY1'
,
'CRMCOMPANY3'
],
'CRMDEAL'
=> [
'CRMDEAL3'
,
'CRMDEAL5'
],
'CRMLEAD'
=> [
'CRMLEAD9'
,
'CRMLEAD11'
],
'SG'
=> [
'SG5'
,
'SG9'
],
'U'
=> [
'U1'
,
'U3'
],
'DR'
=> [
'DR1'
,
'DR7'
],
],
'ENTITYTYPEID'
=>
3
,
'ENTITYID'
=>
3
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
'Message created with ID '
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
'Error creating live feed message: '
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
"crm.livefeedmessage.add"
,
{
fields
:
{
"POST_TITLE"
:
"A bit about the service"
,
"MESSAGE"
:
"Bitrix24 is built on the Bitrix Framework platform."
,
"SPERM"
: {
"CRMCONTACT"
: [
"CRMCONTACT3"
,
"CRMCONTACT7"
],
"CRMCOMPANY"
: [
"CRMCOMPANY1"
,
"CRMCOMPANY3"
],
"CRMDEAL"
: [
"CRMDEAL3"
,
"CRMDEAL5"
],
"CRMLEAD"
: [
"CRMLEAD9"
,
"CRMLEAD11"
],
"SG"
: [
"SG5"
,
"SG9"
],
"U"
: [
"U1"
,
"U3"
],
"DR"
: [
"DR1"
,
"DR7"
],
},
"ENTITYTYPEID"
:
3
,
"ENTITYID"
:
3
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
console
.
info
(
"Message created with ID "
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
'crm.livefeedmessage.add'
,
[
'fields'
=> [
'POST_TITLE'
=>
'A bit about the service'
,
'MESSAGE'
=>
'Bitrix24 is built on the Bitrix Framework platform.'
,
'SPERM'
=> [
'CRMCONTACT'
=> [
'CRMCONTACT3'
,
'CRMCONTACT7'
],
'CRMCOMPANY'
=> [
'CRMCOMPANY1'
,
'CRMCOMPANY3'
],
'CRMDEAL'
=> [
'CRMDEAL3'
,
'CRMDEAL5'
],
'CRMLEAD'
=> [
'CRMLEAD9'
,
'CRMLEAD11'
],
'SG'
=> [
'SG5'
,
'SG9'
],
'U'
=> [
'U1'
,
'U3'
],
'DR'
=> [
'DR1'
,
'DR7'
],
],
'ENTITYTYPEID'
=>
3
,
'ENTITYID'
=>
3
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
Example 2
Example 2
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"POST_TITLE":"POST_TITLE","MESSAGE":"MESSAGE","SPERM":{"CRMLEAD":["CRMLEAD9","CRMLEAD11"],"U":["U1"]},"ENTITYTYPEID":1,"ENTITYID":56374,"FILES":[["1.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="],["2.gif","..."]]}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.livefeedmessage.add
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"POST_TITLE":"POST_TITLE","MESSAGE":"MESSAGE","SPERM":{"CRMLEAD":["CRMLEAD9","CRMLEAD11"],"U":["U1"]},"ENTITYTYPEID":1,"ENTITYID":56374,"FILES":[["1.gif","R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="],["2.gif","..."]]},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.livefeedmessage.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.livefeedmessage.add"
,
{
fields
:
{
"POST_TITLE"
:
"POST_TITLE"
,
"MESSAGE"
:
"MESSAGE"
,
"SPERM"
: {
"CRMLEAD"
: [
"CRMLEAD9"
,
"CRMLEAD11"
],
"U"
: [
"U1"
],
},
"ENTITYTYPEID"
:
1
,
"ENTITYID"
:
56374
,
"FILES"
: [
[
"1.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
[
"2.gif"
,
"..."
]
],
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
"Message created with ID "
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
'crm.livefeedmessage.add'
,
[
'fields'
=> [
'POST_TITLE'
=>
'POST_TITLE'
,
'MESSAGE'
=>
'MESSAGE'
,
'SPERM'
=> [
'CRMLEAD'
=> [
'CRMLEAD9'
,
'CRMLEAD11'
],
'U'
=> [
'U1'
],
],
'ENTITYTYPEID'
=>
1
,
'ENTITYID'
=>
56374
,
'FILES'
=> [
[
'1.gif'
,
'R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=='
],
[
'2.gif'
,
'...'
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
'Message created with ID '
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
'Error creating message: '
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
"crm.livefeedmessage.add"
,
{
fields
:
{
"POST_TITLE"
:
"POST_TITLE"
,
"MESSAGE"
:
"MESSAGE"
,
"SPERM"
: {
"CRMLEAD"
: [
"CRMLEAD9"
,
"CRMLEAD11"
],
"U"
: [
"U1"
],
},
"ENTITYTYPEID"
:
1
,
"ENTITYID"
:
56374
,
"FILES"
: [
[
"1.gif"
,
"R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=="
],
[
"2.gif"
,
"..."
]
],
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
"Message created with ID "
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
'crm.livefeedmessage.add'
,
[
'fields'
=> [
'POST_TITLE'
=>
'POST_TITLE'
,
'MESSAGE'
=>
'MESSAGE'
,
'SPERM'
=> [
'CRMLEAD'
=> [
'CRMLEAD9'
,
'CRMLEAD11'
],
'U'
=> [
'U1'
],
],
'ENTITYTYPEID'
=>
1
,
'ENTITYID'
=>
56374
,
'FILES'
=> [
[
'1.gif'
,
'R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw=='
],
[
'2.gif'
,
'...'
]
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
Additional
Additional
crm.timeline.comment.add
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
About CRM Invoices

---

## VAT Rates: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/vat/index

VAT Rates: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Connection of VAT Rates with Other Objects
VAT Rates: Overview of Methods
Connection of VAT Rates with Other Objects
Overview of Methods
Setting the VAT rate for products or product items allows for automation of:
calculation of the final cost of a product or service
data transfer to documents
integration with payment systems
data exchange with cash registers
Quick navigation:
all methods
User documentation:
Taxes in CRM
Connection of VAT Rates with Other Objects
Connection of VAT Rates with Other Objects
Product items
are goods or services listed in a deal or another CRM entity. Product items may not be present in the trade catalog. Changing the VAT rate for a product in one deal does not affect the rate of a similar product in another entity. To set VAT for a product item in a deal or another CRM entity, use the
taxRate
parameter of the
crm.item.productrow.*
method group.
Goods and services
are company products with fixed sales conditions stored in the trade catalog. When selecting a product from the catalog in a deal or another CRM entity, it will automatically be added with the rate specified in the catalog. To set the VAT for a product or service in the trade catalog, use the
vatId
parameter of the
catalog.product.*
method group.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: depending on the method
Method
Description
crm.vat.add
Creates a new VAT rate
crm.vat.delete
Deletes a VAT rate
crm.vat.get
Returns the VAT rate by identifier
crm.vat.fields
Returns the description of VAT rate fields
crm.vat.list
Returns a list of VAT rates
crm.vat.update
Updates an existing VAT rate
Copied
Was the article helpful?
Yes
No
Previous
On Issuing New Invoice from Recurring
Next
Create VAT Rate

---

## Create VAT Rate crm.vat.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/vat/crm-vat-add

Create VAT Rate crm.vat.add | Bitrix24 REST API and Marketplace Applications
Create VAT Rate crm.vat.add
Create VAT Rate crm.vat.add
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
Who can execute the method: user with CRM administrator rights
Method development has been halted
The method
crm.vat.add
continues to function, but there is a more relevant alternative
catalog.vat.add
.
The method
crm.vat.add
creates a new VAT rate in CRM.
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
field_n
— field name
value_n
— field value
The list of available fields is described
below
Parameter fields
Parameter fields
Name
type
Description
ACTIVE
string
Activity of the rate:
Y
— active,
N
— inactive.
Default —
Y
C_SORT
integer
Sorting.
Default — 100
NAME
*
string
Name of the rate
RATE
*
double
VAT rate value, %
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
'{"fields":{"ACTIVE":"Y","C_SORT":100,"NAME":"VAT 20%","RATE":20.0}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.vat.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"ACTIVE":"Y","C_SORT":100,"NAME":"VAT 20%","RATE":20.0},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.vat.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.vat.add"
,
{
fields
: {
ACTIVE
:
"Y"
,
C_SORT
:
100
,
NAME
:
"VAT 20%"
,
RATE
:
20.0
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
'crm.vat.add'
,
[
'fields'
=> [
'ACTIVE'
=>
'Y'
,
'C_SORT'
=>
100
,
'NAME'
=>
'VAT 20%'
,
'RATE'
=>
20.0
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
'Error adding VAT: '
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
"crm.vat.add"
,
{
fields
: {
ACTIVE
:
"Y"
,
C_SORT
:
100
,
NAME
:
"VAT 20%"
,
RATE
:
20.0
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
'crm.vat.add'
,
[
'fields'
=> [
'ACTIVE'
=>
'Y'
,
'C_SORT'
=>
100
,
'NAME'
=>
'VAT 20%'
,
'RATE'
=>
20.0
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
13
,
"time"
:
{
"start"
:
1751982588.245153
,
"finish"
:
1751982588.287266
,
"duration"
:
0.04211306571960449
,
"processing"
:
0.005285978317260742
,
"date_start"
:
"2025-07-08T16:49:48+02:00"
,
"date_finish"
:
"2025-07-08T16:49:48+02:00"
,
"operating_reset_at"
:
1751983188
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
Root element of the response, contains the identifier of the created VAT rate
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
"Invalid parameters."
,
"error_description"
:
"Invalid parameters were provided."
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
The Commercial Catalog module is not installed.
The catalog module is not installed
400
Invalid parameters.
Invalid parameters were provided
400
Access denied.
No rights to perform the operation
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
Get a list of VAT rates by filter crm.vat.list
Get VAT Rate by ID crm.vat.get
Update Existing VAT Rate crm.vat.update
Delete VAT Rate crm.vat.delete
Get VAT Rate Fields crm.vat.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update VAT Rate

---

## Update Existing VAT Rate crm.vat.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/vat/crm-vat-update

Update Existing VAT Rate crm.vat.update | Bitrix24 REST API and Marketplace Applications
Update Existing VAT Rate crm.vat.update
Update Existing VAT Rate crm.vat.update
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
Who can execute the method: user with CRM administrator rights
Method development halted
The method
crm.vat.update
is still operational, but there is a more relevant alternative
catalog.vat.update
.
The method
crm.vat.update
updates the parameters of an existing VAT rate.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the VAT rate to be updated. You can get a list of rates using the
crm.vat.list
method
fields
*
object
Array of fields to update. The list of available fields is described
below
Parameter fields
Parameter fields
Name
type
Description
ACTIVE
string
Activity of the rate:
Y
— active,
N
— inactive.
C_SORT
integer
Sorting
NAME
*
string
Name of the rate
RATE
*
double
VAT rate value, %
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
'{"id":7,"fields":{"ACTIVE":"N","NAME":"VAT 20% (inactive)"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.vat.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":7,"fields":{"ACTIVE":"N","NAME":"VAT 20% (inactive)"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.vat.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.vat.update"
,
{
id
:
7
,
fields
: {
ACTIVE
:
"N"
,
NAME
:
"VAT 20% (inactive)"
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
'crm.vat.update'
,
[
'id'
=>
7
,
'fields'
=> [
'ACTIVE'
=>
'N'
,
'NAME'
=>
'VAT 20% (inactive)'
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
'Error updating VAT: '
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
"crm.vat.update"
,
{
id
:
7
,
fields
: {
ACTIVE
:
"N"
,
NAME
:
"VAT 20% (inactive)"
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
'crm.vat.update'
,
[
'id'
=>
7
,
'fields'
=> [
'ACTIVE'
=>
'N'
,
'NAME'
=>
'VAT 20% (inactive)'
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
13
,
"time"
:
{
"start"
:
1752045209.496356
,
"finish"
:
1752045209.539975
,
"duration"
:
0.04361891746520996
,
"processing"
:
0.009280920028686523
,
"date_start"
:
"2025-07-09T10:13:29+02:00"
,
"date_finish"
:
"2025-07-09T10:13:29+02:00"
,
"operating_reset_at"
:
1752045809
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
Root element of the response, contains the identifier of the updated rate
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
"Invalid identifier."
,
"error_description"
:
"An invalid identifier was provided."
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
The Commercial Catalog module is not installed.
The catalog module is not installed
400
Invalid parameters.
Invalid parameters were provided
400
Access denied.
No rights to perform the operation
400
Invalid identifier.
An invalid identifier was provided
400
Error on updating VAT rate.
Error updating the VAT rate
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
Get VAT Rate Fields crm.vat.fields
Get a list of VAT rates by filter crm.vat.list
Get VAT Rate by ID crm.vat.get
Create VAT Rate crm.vat.add
Delete VAT Rate crm.vat.delete
Copied
Was the article helpful?
Yes
No
Previous
Create VAT Rate
Next
Get VAT Rate

---

## Get VAT Rate by ID crm.vat.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/vat/crm-vat-get

Get VAT Rate by ID crm.vat.get | Bitrix24 REST API and Marketplace Applications
Get VAT Rate by ID crm.vat.get
Get VAT Rate by ID crm.vat.get
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
Method development has been halted
The method
crm.vat.get
is still operational, but there is a more relevant alternative
catalog.vat.get
.
The method
crm.vat.get
returns the VAT rate parameters by ID.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the VAT rate. You can get a list of rates using the method
crm.vat.list
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
'{"id":7}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.vat.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":7,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.vat.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.vat.get'
,
{
id
:
7
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
'crm.vat.get'
,
[
'id'
=>
7
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
'Error getting VAT information: '
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
"crm.vat.get"
,
{
id
:
7
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
'crm.vat.get'
,
[
'id'
=>
7
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
"13"
,
"ACTIVE"
:
"Y"
,
"NAME"
:
"VAT 20%"
,
"RATE"
:
"20.00"
,
"C_SORT"
:
"100"
}
,
"time"
:
{
"start"
:
1752043855.534128
,
"finish"
:
1752043855.598301
,
"duration"
:
0.06417298316955566
,
"processing"
:
0.008214235305786133
,
"date_start"
:
"2025-07-09T09:50:55+02:00"
,
"date_finish"
:
"2025-07-09T09:50:55+02:00"
,
"operating_reset_at"
:
1752044455
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
Identifier of the VAT rate
ACTIVE
string
Activity status of the rate
C_SORT
integer
Sorting order
NAME
string
Name of the rate
RATE
double
Value of the VAT rate, %
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
"VAT rate not found."
,
"error_description"
:
"VAT rate not found."
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
The Commercial Catalog module is not installed.
The catalog module is not installed
400
Access denied.
No permission to perform the operation
400
VAT rate not found.
VAT rate not found
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
Get VAT Rate Fields crm.vat.fields
Get a list of VAT rates by filter crm.vat.list
Create VAT Rate crm.vat.add
Update Existing VAT Rate crm.vat.update
Delete VAT Rate crm.vat.delete
Copied
Was the article helpful?
Yes
No
Previous
Update VAT Rate
Next
Get List of VAT Rates

---

## Get a list of VAT rates by filter crm.vat.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/vat/crm-vat-list

Get a list of VAT rates by filter crm.vat.list | Bitrix24 REST API and Marketplace Applications
Get a list of VAT rates by filter crm.vat.list
Get a list of VAT rates by filter crm.vat.list
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
Method development has been halted
The method
crm.vat.list
continues to function, but there is a more current equivalent
catalog.vat.list
.
The method
crm.vat.list
returns a list of VAT rates based on a filter.
It is an implementation of the
list method
for VAT rates.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
order
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
field_n
— the name of the field by which the selection of rates will be sorted
value_n
— a
string
value equal to:
ASC
— ascending sort
DESC
— descending sort
The list of available fields for sorting can be found using the method
crm.vat.fields
filter
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
field_n
— the name of the field by which the selection of elements will be filtered
value_n
— the filter value
The list of available fields for filtering can be found using the method
crm.vat.fields
select
array
Array of returned fields. If not specified, all fields are returned
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
'{"order":{"ID":"ASC"},"filter":{"ACTIVE":"Y"},"select":["ID","NAME","RATE"]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.vat.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"ID":"ASC"},"filter":{"ACTIVE":"Y"},"select":["ID","NAME","RATE"],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.vat.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.vat.list'
,
{
order
: {
ID
:
"ASC"
},
filter
: {
ACTIVE
:
"Y"
},
select
: [
"ID"
,
"NAME"
,
"RATE"
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
'crm.vat.list'
, {
order
: {
ID
:
"ASC"
},
filter
: {
ACTIVE
:
"Y"
},
select
: [
"ID"
,
"NAME"
,
"RATE"
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.vat.list'
, {
order
: {
ID
:
"ASC"
},
filter
: {
ACTIVE
:
"Y"
},
select
: [
"ID"
,
"NAME"
,
"RATE"
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
'crm.vat.list'
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
'ACTIVE'
=>
'Y'
],
'select'
=> [
'ID'
,
'NAME'
,
'RATE'
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
'Error fetching VAT list: '
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
"crm.vat.list"
,
{
order
: {
ID
:
"ASC"
},
filter
: {
ACTIVE
:
"Y"
},
select
: [
"ID"
,
"NAME"
,
"RATE"
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
'crm.vat.list'
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
'ACTIVE'
=>
'Y'
],
'select'
=> [
'ID'
,
'NAME'
,
'RATE'
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
"No VAT"
,
"RATE"
:
null
}
,
{
"ID"
:
"3"
,
"NAME"
:
"VAT 20%"
,
"RATE"
:
"20.00"
}
,
{
"ID"
:
"7"
,
"NAME"
:
"12"
,
"RATE"
:
"12.00"
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
1752044697.589623
,
"finish"
:
1752044697.66439
,
"duration"
:
0.0747671127319336
,
"processing"
:
0.00588679313659668
,
"date_start"
:
"2025-07-09T10:04:57+03:00"
,
"date_finish"
:
"2025-07-09T10:04:57+03:00"
,
"operating_reset_at"
:
1752045297
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
The root element of the response. Contains an array of objects with information about VAT rate fields.
The structure of the fields may change due to the
select
parameter
total
integer
The total number of found items
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
"Inadmissible fields for selection"
,
"error_description"
:
"Invalid fields for selection were provided."
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
The Commercial Catalog module is not installed.
The catalog module is not installed
400
Access denied.
No permission to perform the operation
400
"Inadmissible fields for selection.
Invalid fields for selection were provided
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
Get VAT Rate Fields crm.vat.fields
Get VAT Rate by ID crm.vat.get
Create VAT Rate crm.vat.add
Update Existing VAT Rate crm.vat.update
Delete VAT Rate crm.vat.delete
Copied
Was the article helpful?
Yes
No
Previous
Get VAT Rate
Next
Delete VAT Rate

---

## Delete VAT Rate crm.vat.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/vat/crm-vat-delete

Delete VAT Rate crm.vat.delete | Bitrix24 REST API and Marketplace Applications
Delete VAT Rate crm.vat.delete
Delete VAT Rate crm.vat.delete
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
Who can execute the method: user with CRM administrator rights
Method development halted
The method
crm.vat.delete
continues to function, but there is a more relevant alternative
catalog.vat.delete
.
The method
crm.vat.delete
removes a VAT rate by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the VAT rate to be deleted.
You can obtain a list of rates with identifiers using the method
crm.vat.list
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
'{"id":7}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.vat.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":7,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.vat.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.vat.delete"
,
{
id
:
7
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
'crm.vat.delete'
,
[
'id'
=>
7
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
'Error deleting VAT: '
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
"crm.vat.delete"
,
{
id
:
7
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
'crm.vat.delete'
,
[
'id'
=>
7
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
1751983429.678159
,
"finish"
:
1751983429.873604
,
"duration"
:
0.19544506072998047
,
"processing"
:
0.01796698570251465
,
"date_start"
:
"2025-07-08T17:03:49+02:00"
,
"date_finish"
:
"2025-07-08T17:03:49+02:00"
,
"operating_reset_at"
:
1751984029
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
"Invalid identifier."
,
"error_description"
:
"An invalid identifier was provided."
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
The Commercial Catalog module is not installed.
The catalog module is not installed
400
Invalid identifier.
An invalid identifier was provided
400
Access denied.
No rights to perform the operation
400
Error on deleting VAT rate.
Error while deleting the VAT rate
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
Get VAT Rate Fields crm.vat.fields
Get a list of VAT rates by filter crm.vat.list
Get VAT Rate by ID crm.vat.get
Create VAT Rate crm.vat.add
Update Existing VAT Rate crm.vat.update
Copied
Was the article helpful?
Yes
No
Previous
Get List of VAT Rates
Next
Get VAT Rate Fields

---

## Get VAT Rate Fields crm.vat.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/vat/crm-vat-fields

Get VAT Rate Fields crm.vat.fields | Bitrix24 REST API and Marketplace Applications
Get VAT Rate Fields crm.vat.fields
Get VAT Rate Fields crm.vat.fields
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
Method development has been halted
The method
crm.vat.fields
continues to function, but there is a more relevant alternative
catalog.vat.getFields
.
The method
crm.vat.fields
returns the description of VAT rate fields.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.vat.fields
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
https://**put_your_bitrix24_address**/rest/crm.vat.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.vat.fields"
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
'crm.vat.fields'
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
'Error fetching VAT fields: '
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
"crm.vat.fields"
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
'crm.vat.fields'
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
"size"
:
"11"
,
"isRequired"
:
false
,
"isReadOnly"
:
true
,
"title"
:
"ID"
}
,
"TIMESTAMP_X"
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
"title"
:
"Modification Date"
}
,
"ACTIVE"
:
{
"type"
:
"string"
,
"size"
:
"1"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"title"
:
"Activity"
}
,
"C_SORT"
:
{
"type"
:
"integer"
,
"size"
:
"18"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"title"
:
"Sorting"
}
,
"NAME"
:
{
"type"
:
"string"
,
"size"
:
"50"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"title"
:
"Name"
}
,
"RATE"
:
{
"type"
:
"double"
,
"size"
:
"18,2"
,
"isRequired"
:
false
,
"isReadOnly"
:
false
,
"title"
:
"Rate"
}
}
,
"time"
:
{
"start"
:
1751984389.802849
,
"finish"
:
1751984389.832249
,
"duration"
:
0.029399871826171875
,
"processing"
:
0.0001289844512939453
,
"date_start"
:
"2025-07-08T17:19:49+02:00"
,
"date_finish"
:
"2025-07-08T17:19:49+02:00"
,
"operating_reset_at"
:
1751984989
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
integer
Identifier of the VAT rate
TIMESTAMP_X
datetime
Modification date
ACTIVE
string
Activity of the rate
C_SORT
integer
Sorting
NAME
string
Name of the rate
RATE
double
Value of the VAT rate, %
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
Get a list of VAT rates by filter crm.vat.list
Get VAT Rate by ID crm.vat.get
Create VAT Rate crm.vat.add
Update Existing VAT Rate crm.vat.update
Delete VAT Rate crm.vat.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete VAT Rate
Next
Get Stage Movement History

---

