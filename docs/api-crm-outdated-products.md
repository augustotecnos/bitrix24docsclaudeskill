---
description: 'CRM Outdated Products/Catalog API (deprecated): Products, sections'
methods:
- crm.catalog.fields
- crm.catalog.get
- crm.catalog.list
- crm.item.productrow.fields
- crm.item.productrow.list
- crm.product.add
- crm.product.delete
- crm.product.fields
- crm.product.get
- crm.product.list
- crm.product.property.add
- crm.product.property.delete
- crm.product.property.enumeration.fields
- crm.product.property.fields
- crm.product.property.get
- crm.product.property.list
- crm.product.property.settings.fields
- crm.product.property.types
- crm.product.property.update
- crm.product.update
- crm.productrow.fields
- crm.productrow.list
- crm.productsection.add
- crm.productsection.delete
- crm.productsection.fields
- crm.productsection.get
- crm.productsection.list
- crm.productsection.update
pages: 41
title: 'CRM Outdated Products/Catalog API (deprecated): Products, sections'
---
# CRM Outdated Products/Catalog API (deprecated): Products, sections
> CRM Outdated Products/Catalog API (deprecated): Products, sections
> **41 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Overview of Methods](#overview-of-methods)
- [Get product catalog by ID crm.catalog.get](#get-product-catalog-by-id-crmcatalogget)
- [Get a list of product catalogs crm.catalog.list](#get-a-list-of-product-catalogs-crmcataloglist)
- [Get Product Catalog Fields crm.catalog.fields](#get-product-catalog-fields-crmcatalogfields)
- [Product Items](#product-items)
- [Get descriptions of fields for product items crm.productrow.fields](#get-descriptions-of-fields-for-product-items-crmpr)
- [Get the list of order properties crm.productrow.list](#get-the-list-of-order-properties-crmproductrowlist)
- [Products](#products)
- [Add Product crm.product.add](#add-product-crmproductadd)
- [Delete product crm.product.delete](#delete-product-crmproductdelete)
- [Get Product Fields crm.product.fields](#get-product-fields-crmproductfields)
- [Get Product by ID crm.product.get](#get-product-by-id-crmproductget)
- [Get a list of products by filter crm.product.list](#get-a-list-of-products-by-filter-crmproductlist)
- [Update Product crm.product.update](#update-product-crmproductupdate)
- [Get a list of product property types crm.product.property.types](#get-a-list-of-product-property-types-crmproductpro)
- [Get Product Property Fields crm.product.property.fields](#get-product-property-fields-crmproductpropertyfiel)
- [Get the fields of additional settings for the custom type crm.product.property.settings.fields](#get-the-fields-of-additional-settings-for-the-cust)
- [Get Fields of Enumeration Type Property crm.product.property.enumeration.fields](#get-fields-of-enumeration-type-property-crmproduct)
- [Add Product Property crm.product.property.add](#add-product-property-crmproductpropertyadd)
- [Get product property by ID crm.product.property.get](#get-product-property-by-id-crmproductpropertyget)
- [Get a list of product properties crm.product.property.list](#get-a-list-of-product-properties-crmproductpropert)
- [Update Product Property crm.product.property.update](#update-product-property-crmproductpropertyupdate)
- [Delete Product Property crm.product.property.delete](#delete-product-property-crmproductpropertydelete)
- [Events](#events)
- [Event onCrmProductAdd](#event-oncrmproductadd)
- [Event onCrmProductUpdate](#event-oncrmproductupdate)
- [Event onCrmProductDelete](#event-oncrmproductdelete)
- [Event for Adding Product Property onCrmProductPropertyAdd](#event-for-adding-product-property-oncrmproductprop)
- [Event onCrmProductPropertyUpdate](#event-oncrmproductpropertyupdate)
- [Event onCrmProductPropertyDelete](#event-oncrmproductpropertydelete)
- [Overview of Methods](#overview-of-methods)
- [Add a New Product Section crm.productsection.add](#add-a-new-product-section-crmproductsectionadd)
- [Update Product Section <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-7nriil7i">crm.productsection.update</code>](#update-product-section-code-classyfm-clipboard-inl)
- [Get Product Section by ID crm.productsection.get](#get-product-section-by-id-crmproductsectionget)
- [Get the list of sections crm.productsection.list](#get-the-list-of-sections-crmproductsectionlist)
- [Delete Product Section crm.productsection.delete](#delete-product-section-crmproductsectiondelete)
- [Get Fields of the Product Section crm.productsection.fields](#get-fields-of-the-product-section-crmproductsectio)
- [Events](#events)
- [Event for Adding a New Product Section onCrmProductSectionAdd](#event-for-adding-a-new-product-section-oncrmproduc)
- [Event onCrmProductSectionUpdate](#event-oncrmproductsectionupdate)
- [Event onCrmProductSectionDelete](#event-oncrmproductsectiondelete)

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/catalog/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: any user
Method
Description
crm.catalog.fields
Returns the description of product catalog fields
crm.catalog.get
Retrieves the product catalog by ID
crm.catalog.list
Returns a list of product catalogs
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get Product Catalog by ID

---

## Get product catalog by ID crm.catalog.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/catalog/crm-catalog-get

Get product catalog by ID crm.catalog.get | Bitrix24 REST API and Marketplace Applications
Method parameters
Get product catalog by ID crm.catalog.get
Method parameters
Code examples
Scope:
crm
Who can execute the method: any user
The method returns the product catalog by ID.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the product catalog
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
'{"id":"your_id_here"}'
\
# Replace 'your_id_here' with the actual ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.catalog.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"your_id_here"}'
\
# Replace 'your_id_here' with the actual ID
https://**put_your_bitrix24_address**/rest/crm.catalog.get?auth=**put_access_token_here**
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
"crm.catalog.get"
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
'crm.catalog.get'
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
'Error calling crm.catalog.get: '
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
"crm.catalog.get"
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
'your_id_here'
;
// Replace 'your_id_here' with the actual ID
$result
=
CRest
::
call
(
'crm.catalog.get'
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
Overview of Methods
Next
Get List of Product Catalogs

---

## Get a list of product catalogs crm.catalog.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/catalog/crm-catalog-list

Get a list of product catalogs crm.catalog.list | Bitrix24 REST API and Marketplace Applications
Code examples
Get a list of product catalogs crm.catalog.list
Scope:
crm
Who can execute the method: any user
The method returns a list of product catalogs. It is an implementation of the list method for product catalogs.
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
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.catalog.list
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
https://**put_your_bitrix24_address**/rest/crm.catalog.list?auth=**put_access_token_here**
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.catalog.list'
,
{},
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
'crm.catalog.list'
, {},
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
'crm.catalog.list'
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
'crm.catalog.list'
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
'Error fetching catalog list: '
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
"crm.catalog.list"
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
'crm.catalog.list'
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
Get Product Catalog by ID
Next
Get Product Catalog Fields

---

## Get Product Catalog Fields crm.catalog.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/catalog/crm-catalog-fields

Get Product Catalog Fields crm.catalog.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Product Catalog Fields crm.catalog.fields
Code Examples
Returned Data
Scope:
crm
Who can execute the method: any user
The method returns the description of the product catalog fields.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.catalog.fields
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
https://**put_your_bitrix24_address**/rest/crm.catalog.fields?auth=**put_access_token_here**
try
{
const
response =
await
$b24.
callMethod
(
'crm.catalog.fields'
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
'crm.catalog.fields'
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
'Error fetching catalog fields: '
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
"crm.catalog.fields"
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
'crm.catalog.fields'
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
Name
type
Description
ID
integer
Identifier. Read-only
NAME
string
Title
ORIGINATOR_ID
string
Identifier of the data source. Used only for linking to an external source
ORIGIN_ID
string
Identifier of the element in the data source. Used only for linking to an external source
XML_ID
string
Symbolic code. Read-only
Copied
Was the article helpful?
Yes
No
Previous
Get List of Product Catalogs
Next
Overview of Methods

---

## Product Items

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/productrow-old/index

Product Items | Bitrix24 REST API and Marketplace Applications
Product Items
Product Items
Scope:
crm
Who can execute methods: any user
Method
Description
crm.productrow.fields
Retrieves all fields of product items
crm.productrow.list
Retrieves a list of product item fields based on a filter
Copied
Was the article helpful?
Yes
No
Previous
Get Product Catalog Fields
Next
Retrieve All Fields of Product Items

---

## Get descriptions of fields for product items crm.productrow.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/productrow-old/crm-productrow-fields

Get descriptions of fields for product items crm.productrow.fields | Bitrix24 REST API and Marketplace Applications
Get descriptions of fields for product items crm.productrow.fields
Get descriptions of fields for product items crm.productrow.fields
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
crm.item.productrow.fields
The method retrieves information about the data structure of product items in CRM, including field types and their purposes.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.productrow.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.productrow.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.productrow.fields'
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
'crm.productrow.fields'
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
'Error fetching product row fields: '
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
"crm.productrow.fields"
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
'crm.productrow.fields'
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
Overview of Methods
Next
Get List of Fields by Filter

---

## Get the list of order properties crm.productrow.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/productrow-old/crm-productrow-list

Get the list of order properties crm.productrow.list | Bitrix24 REST API and Marketplace Applications
Get the list of order properties crm.productrow.list
Get the list of order properties crm.productrow.list
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Warning
The method is deprecated. It is recommended to use
crm.item.productrow.list
The method returns a list of product items based on the filter. It is an implementation of the list method for product items. The owner of the product items is determined by the required fields
OWNER_TYPE
and
OWNER_ID
, where
OWNER_TYPE
is a one-character code for the type ("D" - deal, "L" - lead), and
OWNER_ID
is the identifier.
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
-d '{"filter":{"OWNER_TYPE":"D","OWNER_ID":"1"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.productrow.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"filter":{"OWNER_TYPE":"D","OWNER_ID":"1"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.productrow.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
var
ownerType =
prompt
(
"Enter owner type (D, L)"
);
var
ownerId =
prompt
(
"Enter owner ID"
);
try
{
const
response =
await
$b24.
callListMethod
(
'crm.productrow.list'
,
{
filter
: {
"OWNER_TYPE"
: ownerType,
"OWNER_ID"
: ownerId
}
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
// fetchListMethod is preferred when working with large data sets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
var
ownerType =
prompt
(
"Enter owner type (D, L)"
);
var
ownerId =
prompt
(
"Enter owner ID"
);
try
{
const
generator = $b24.
fetchListMethod
(
'crm.productrow.list'
, {
filter
: {
"OWNER_TYPE"
: ownerType,
"OWNER_ID"
: ownerId
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
var
ownerType =
prompt
(
"Enter owner type (D, L)"
);
var
ownerId =
prompt
(
"Enter owner ID"
);
try
{
const
response =
await
$b24.
callMethod
(
'crm.productrow.list'
, {
filter
: {
"OWNER_TYPE"
: ownerType,
"OWNER_ID"
: ownerId
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
$ownerType
=
readline
(
"Enter owner type (D, L): "
);
$ownerId
=
readline
(
"Enter owner ID: "
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
'crm.productrow.list'
,
[
'filter'
=> [
'OWNER_TYPE'
=>
$ownerType
,
'OWNER_ID'
=>
$ownerId
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
'Error: '
.
$e
->
getMessage
();
}
var
ownerType =
prompt
(
"Enter owner type (D, L)"
);
var
ownerId =
prompt
(
"Enter owner ID"
);
BX24
.
callMethod
(
"crm.productrow.list"
,
{
filter
:
{
"OWNER_TYPE"
: ownerType,
"OWNER_ID"
: ownerId
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
$ownerType
=
'D'
;
// Replace 'D' with the desired owner type
$ownerId
=
1
;
// Replace 1 with the actual owner ID
$result
=
CRest
::
call
(
'crm.productrow.list'
,
[
'filter'
=>
[
'OWNER_TYPE'
=>
$ownerType
,
'OWNER_ID'
=>
$ownerId
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
Retrieve All Fields of Product Items
Next
Overview of Methods

---

## Products

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/index

Products | Bitrix24 REST API and Marketplace Applications
Products
Products
Scope:
crm
Who can perform the method: depends on the method
Method
Description
crm.product.add
Creates a new product
crm.product.delete
Deletes a product
crm.product.fields
Returns the description of product fields
crm.product.get
Returns a product by its identifier
crm.product.list
Returns a list of products based on a filter
crm.product.update
Updates an existing product
crm.product.property.types
Returns a list of product property types
crm.product.property.fields
Returns the description of fields for product properties
crm.product.property.settings.fields
Returns the description of fields for additional settings of custom product properties
crm.product.property.enumeration.fields
Returns the description of fields for list-type product property elements
crm.product.property.add
Creates a new product property
crm.product.property.get
Returns a product property by its identifier
crm.product.property.list
Returns a list of product properties
crm.product.property.update
Updates an existing product property
crm.product.property.delete
Deletes a product property
A complete list of
product events
is provided in the article
Events
.
Copied
Was the article helpful?
Yes
No
Previous
Get List of Stages
Next
Add Product

---

## Add Product crm.product.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-add

Add Product crm.product.add | Bitrix24 REST API and Marketplace Applications
Add Product crm.product.add
Add Product crm.product.add
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: administrator, user with the "Allow to change settings" access permission in CRM
Method development halted
The method
crm.product.add
continues to function, but there are more relevant alternatives
catalog.product.*
.
The method
crm.product.add
creates a new product.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
array
Field values for creating a product.
To find out the required field format, execute the method
crm.product.fields
and check the format of the returned field values
Note
Starting from version
CRM 21.700.0
, support for auto-generating the product's symbolic code has been included.
If the generated symbolic code exceeds 100 characters, it is automatically truncated to 100 characters. This should be taken into account when creating requests by passing a unique value at the beginning/middle of the product name to avoid duplicate symbolic codes.
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
-d '{"fields":{"NAME":"Plastic Chair","CURRENCY_ID":"USD","PRICE":4900,"SORT":500}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.add
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"NAME":"Plastic Chair","CURRENCY_ID":"USD","PRICE":4900,"SORT":500},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.product.add'
,
{
fields
:
{
"NAME"
:
"Plastic Chair"
,
"CURRENCY_ID"
:
"USD"
,
"PRICE"
:
4900
,
"SORT"
:
500
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
'Created new product with ID '
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
$fields
= [
'NAME'
=>
'Sample Product'
,
'PRICE'
=>
'100.00'
,
'CURRENCY_ID'
=>
'USD'
,
'ACTIVE'
=>
'Y'
,
'DATE_CREATE'
=> (
new
DateTime
())->
format
(
DateTime
::
ATOM
),
'TIMESTAMP_X'
=> (
new
DateTime
())->
format
(
DateTime
::
ATOM
),
'CREATED_BY'
=>
1
,
'MODIFIED_BY'
=>
1
,
'CATALOG_ID'
=>
1
,
'DESCRIPTION'
=>
'This is a sample product.'
,
'VAT_ID'
=>
1
,
'VAT_INCLUDED'
=>
'Y'
,
'MEASURE'
=>
1
,
'SECTION_ID'
=>
1
,
'SORT'
=>
100
,
'XML_ID'
=>
'sample_product_001'
,
];
$result
=
$serviceBuilder
->
getCRMScope
()->
product
()->
add
(
$fields
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
"crm.product.add"
,
{
fields
:
{
"NAME"
:
"Plastic Chair"
,
"CURRENCY_ID"
:
"USD"
,
"PRICE"
:
4900
,
"SORT"
:
500
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
"Created new product with ID "
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
'crm.product.add'
,
[
'fields'
=> [
'NAME'
=>
'Plastic Chair'
,
'CURRENCY_ID'
=>
'USD'
,
'PRICE'
=>
4900
,
'SORT'
=>
500
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
Delete Product

---

## Delete product crm.product.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-delete

Delete product crm.product.delete | Bitrix24 REST API and Marketplace Applications
Delete product crm.product.delete
Delete product crm.product.delete
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: administrator, user with the "Allow to modify settings" access permission in CRM
Method development has been halted
The method
crm.product.delete
is still operational, but there are more relevant alternatives
catalog.product.*
.
The method
crm.product.delete
removes a product.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Product identifier
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
-d '{"id":"your_product_id"}' \ # Replace 'your_product_id' with the actual product ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_product_id"}' \ # Replace 'your_product_id' with the actual product ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.delete
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
"crm.product.delete"
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
try
{
$productId
=
123
;
// Example product ID
$result
=
$serviceBuilder
->
getCRMScope
()->
product
()->
delete
(
$productId
);
if
(
$result
->
isSuccess
()) {
print
(
"Item deleted successfully."
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
"crm.product.delete"
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
'your_product_id'
;
// Replace 'your_product_id' with the actual product ID
$result
=
CRest
::
call
(
'crm.product.delete'
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
Add Product
Next
Get Product Fields

---

## Get Product Fields crm.product.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-fields

Get Product Fields crm.product.fields | Bitrix24 REST API and Marketplace Applications
Get Product Fields crm.product.fields
Get Product Fields crm.product.fields
Code Examples
Returned Data
Scope:
crm
Who can execute the method: any user
Method development has been halted
The method
crm.product.fields
continues to function, but there are more relevant alternatives
catalog.product.*
.
The method
crm.product.fields
returns the description of product fields.
Without parameters.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.product.fields"
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
$fieldsResult
=
$serviceBuilder
->
getCRMScope
()->
product
()->
fields
();
$fieldsDescription
=
$fieldsResult
->
getFieldsDescription
();
foreach
(
$fieldsDescription
as
$field
) {
if
(
isset
(
$field
[
'DATE_CREATE'
])) {
$field
[
'DATE_CREATE'
] = (
new
DateTime
(
$field
[
'DATE_CREATE'
]))->
format
(
DateTime
::
ATOM
);
}
if
(
isset
(
$field
[
'TIMESTAMP_X'
])) {
$field
[
'TIMESTAMP_X'
] = (
new
DateTime
(
$field
[
'TIMESTAMP_X'
]))->
format
(
DateTime
::
ATOM
);
}
print
(
$field
[
'ID'
] .
': '
.
$field
[
'NAME'
] . PHP_EOL);
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
() . PHP_EOL);
}
BX24
.
callMethod
(
"crm.product.fields"
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
'crm.product.fields'
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
ACTIVE
char
Active
CATALOG_ID
integer
Catalog identifier
CREATED_BY
integer
Created by
CURRENCY_ID
string
Currency identifier
DATE_CREATE
datetime
Product creation date
DESCRIPTION
string
Description
DESCRIPTION_TYPE
string
Description type
DETAIL_PICTURE
product_file
Detailed picture, field available in the old product card
ID
integer
Product identifier
MEASURE
integer
Unit of measurement
MODIFIED_BY
integer
Modified by
NAME
*
string
Name
PREVIEW_PICTURE
product_file
Preview picture, field available in the old product card
PRICE
double
Price
SECTION_ID
integer
Section identifier
SORT
integer
Sorting
TIMESTAMP_X
datetime
Product modification date
VAT_ID
integer
VAT rate identifier
VAT_INCLUDED
char
VAT included in price
XML_ID
string
External code
Copied
Was the article helpful?
Yes
No
Previous
Delete Product
Next
Get Product by ID

---

## Get Product by ID crm.product.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-get

Get Product by ID crm.product.get | Bitrix24 REST API and Marketplace Applications
Get Product by ID crm.product.get
Get Product by ID crm.product.get
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Method development has been halted
The method
crm.product.get
continues to function, but there are more relevant alternatives
catalog.product.*
.
The method
crm.product.get
returns a product by its ID.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Product ID
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
-d '{"id":"your_product_id"}' \ # Replace 'your_product_id' with the actual product ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_product_id","auth":"**put_access_token_here**"}' \ # Replace 'your_product_id' with the actual product ID
https://**put_your_bitrix24_address**/rest/crm.product.get
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
"crm.product.get"
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
try
{
$productId
=
1
;
// Example product ID
$productService
=
$serviceBuilder
->
getCRMScope
()->
product
();
$productResult
=
$productService
->
get
(
$productId
);
$itemResult
=
$productResult
->
product
();
print
(
"ID: "
.
$itemResult
->ID .
"\n"
);
print
(
"Catalog ID: "
.
$itemResult
->CATALOG_ID .
"\n"
);
print
(
"Price: "
.
$itemResult
->PRICE .
"\n"
);
print
(
"Currency ID: "
.
$itemResult
->CURRENCY_ID .
"\n"
);
print
(
"Name: "
.
$itemResult
->NAME .
"\n"
);
print
(
"Code: "
.
$itemResult
->CODE .
"\n"
);
print
(
"Description: "
.
$itemResult
->DESCRIPTION .
"\n"
);
print
(
"Description Type: "
.
$itemResult
->DESCRIPTION_TYPE .
"\n"
);
print
(
"Active: "
.
$itemResult
->ACTIVE .
"\n"
);
print
(
"Section ID: "
.
$itemResult
->SECTION_ID .
"\n"
);
print
(
"Sort: "
.
$itemResult
->SORT .
"\n"
);
print
(
"VAT ID: "
.
$itemResult
->VAT_ID .
"\n"
);
print
(
"VAT Included: "
.
$itemResult
->VAT_INCLUDED .
"\n"
);
print
(
"Measure: "
.
$itemResult
->MEASURE .
"\n"
);
print
(
"XML ID: "
.
$itemResult
->XML_ID .
"\n"
);
print
(
"Preview Picture: "
.
$itemResult
->PREVIEW_PICTURE .
"\n"
);
print
(
"Detail Picture: "
.
$itemResult
->DETAIL_PICTURE .
"\n"
);
print
(
"Date Create: "
.
$itemResult
->DATE_CREATE .
"\n"
);
print
(
"Timestamp X: "
.
$itemResult
->TIMESTAMP_X .
"\n"
);
print
(
"Modified By: "
.
$itemResult
->MODIFIED_BY .
"\n"
);
print
(
"Created By: "
.
$itemResult
->CREATED_BY .
"\n"
);
}
catch
(\
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
() .
"\n"
);
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
"crm.product.get"
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
'your_product_id'
;
// Replace 'your_product_id' with the actual product ID
$result
=
CRest
::
call
(
'crm.product.get'
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
Get Product Fields
Next
Get List of Products by Filter

---

## Get a list of products by filter crm.product.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-list

Get a list of products by filter crm.product.list | Bitrix24 REST API and Marketplace Applications
Get a list of products by filter crm.product.list
Get a list of products by filter crm.product.list
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Method development has been discontinued
The method
crm.product.list
continues to function, but there are more current alternatives
catalog.product.*
.
The method
crm.product.list
returns a list of products based on the filter.
Method Parameters
Method Parameters
See the description of
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"NAME":"ASC"},"filter":{"CATALOG_ID":"your_catalog_id"},"select":["ID","NAME","CURRENCY_ID","PRICE"]}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"NAME":"ASC"},"filter":{"CATALOG_ID":"your_catalog_id"},"select":["ID","NAME","CURRENCY_ID","PRICE"],"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
var
catalogId =
prompt
(
"Enter catalog ID"
);
try
{
const
response =
await
$b24.
callListMethod
(
'crm.product.list'
,
{
order
: {
"NAME"
:
"ASC"
},
filter
: {
"CATALOG_ID"
: catalogId },
select
: [
"ID"
,
"NAME"
,
"CURRENCY_ID"
,
"PRICE"
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
var
catalogId =
prompt
(
"Enter catalog ID"
);
try
{
const
generator = $b24.
fetchListMethod
(
'crm.product.list'
, {
order
: {
"NAME"
:
"ASC"
},
filter
: {
"CATALOG_ID"
: catalogId },
select
: [
"ID"
,
"NAME"
,
"CURRENCY_ID"
,
"PRICE"
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. Suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
var
catalogId =
prompt
(
"Enter catalog ID"
);
try
{
const
response =
await
$b24.
callMethod
(
'crm.product.list'
, {
order
: {
"NAME"
:
"ASC"
},
filter
: {
"CATALOG_ID"
: catalogId },
select
: [
"ID"
,
"NAME"
,
"CURRENCY_ID"
,
"PRICE"
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
$order
= [];
// Define your order array
$filter
= [];
// Define your filter array
$select
= [
'ID'
,
'CATALOG_ID'
,
'PRICE'
,
'CURRENCY_ID'
,
'NAME'
,
'CODE'
,
'DESCRIPTION'
,
'DESCRIPTION_TYPE'
,
'ACTIVE'
,
'SECTION_ID'
,
'SORT'
,
'VAT_ID'
,
'VAT_INCLUDED'
,
'MEASURE'
,
'XML_ID'
,
'PREVIEW_PICTURE'
,
'DETAIL_PICTURE'
,
'DATE_CREATE'
,
'TIMESTAMP_X'
,
'MODIFIED_BY'
,
'CREATED_BY'
];
$startItem
=
0
;
// Define your start item
$result
=
$serviceBuilder
->
getCRMScope
()
->
product
()
->
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
$result
->
getProducts
()
as
$product
) {
print
(
"ID:
{$product->ID}
\n"
);
print
(
"Catalog ID:
{$product->CATALOG_ID}
\n"
);
print
(
"Price:
{$product->PRICE}
\n"
);
print
(
"Currency ID:
{$product->CURRENCY_ID}
\n"
);
print
(
"Name:
{$product->NAME}
\n"
);
print
(
"Code:
{$product->CODE}
\n"
);
print
(
"Description:
{$product->DESCRIPTION}
\n"
);
print
(
"Description Type:
{$product->DESCRIPTION_TYPE}
\n"
);
print
(
"Active:
{$product->ACTIVE}
\n"
);
print
(
"Section ID:
{$product->SECTION_ID}
\n"
);
print
(
"Sort:
{$product->SORT}
\n"
);
print
(
"VAT ID:
{$product->VAT_ID}
\n"
);
print
(
"VAT Included:
{$product->VAT_INCLUDED}
\n"
);
print
(
"Measure:
{$product->MEASURE}
\n"
);
print
(
"XML ID:
{$product->XML_ID}
\n"
);
print
(
"Preview Picture:
{$product->PREVIEW_PICTURE}
\n"
);
print
(
"Detail Picture:
{$product->DETAIL_PICTURE}
\n"
);
print
(
"Date Create: "
. (
new
DateTime
(
$product
->DATE_CREATE))->
format
(
DateTime
::
ATOM
) .
"\n"
);
print
(
"Timestamp X: "
. (
new
DateTime
(
$product
->TIMESTAMP_X))->
format
(
DateTime
::
ATOM
) .
"\n"
);
print
(
"Modified By:
{$product->MODIFIED_BY}
\n"
);
print
(
"Created By:
{$product->CREATED_BY}
\n"
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
var
catalogId =
prompt
(
"Enter catalog ID"
);
BX24
.
callMethod
(
"crm.product.list"
,
{
order
: {
"NAME"
:
"ASC"
},
filter
: {
"CATALOG_ID"
: catalogId },
select
: [
"ID"
,
"NAME"
,
"CURRENCY_ID"
,
"PRICE"
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
To get product properties, you need to specify
PROPERTY_*
in
select
.
$arFields[
'select'
] =
array
(
'*'
,
'PROPERTY_*'
);
require_once
(
'crest.php'
);
$catalogId
=
'your_catalog_id'
;
// Replace 'your_catalog_id' with the actual catalog ID
$result
=
CRest
::
call
(
'crm.product.list'
,
[
'order'
=> [
'NAME'
=>
'ASC'
],
'filter'
=> [
'CATALOG_ID'
=>
$catalogId
],
'select'
=> [
'ID'
,
'NAME'
,
'CURRENCY_ID'
,
'PRICE'
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
Get Product by ID
Next
Update Product

---

## Update Product crm.product.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-update

Update Product crm.product.update | Bitrix24 REST API and Marketplace Applications
Update Product crm.product.update
Update Product crm.product.update
Method Parameters
Code Examples
Example 1
Example 2
Scope:
crm
Who can execute the method: administrator, user with the "Allow to modify settings" access permission in CRM
Method development has been halted
The method
crm.product.update
continues to function, but there are more relevant alternatives
catalog.product.*
.
The method
crm.product.update
updates an existing product.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Product identifier
fields
array
Set of fields
- an array of the form
array("field_to_update"=>"value"[, ...])
, where "field_to_update" can take values returned by the method
crm.product.fields
.
It is mandatory to specify
CURRENCY_ID
to set the price.
To find out the required format of the fields, execute the method
crm.product.fields
and check the format of the returned values for these fields.
To delete a file in the
valueId
field, specify the identifier of the property value, not the file identifier
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
-d '{"id":"your_product_id","fields":{"CURRENCY_ID":"USD","PRICE":5000}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.update
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_product_id","fields":{"CURRENCY_ID":"USD","PRICE":5000},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.update
try
{
const
response =
await
$b24.
callMethod
(
"crm.product.update"
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
"PRICE"
:
5000
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
'crm.product.update'
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
'PRICE'
=>
5000
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
'Error updating product: '
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
"crm.product.update"
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
"PRICE"
:
5000
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
$id
=
'your_product_id'
;
// Replace 'your_product_id' with the actual product ID
$result
=
CRest
::
call
(
'crm.product.update'
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
'PRICE'
=>
5000
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
JS
PHP
BX24.js
PHP CRest
try
{
const
response =
await
$b24.
callMethod
(
"crm.product.update"
,
{
id
:
4611
,
fields
:
{
"PROPERTY_186"
: [
{
"valueId"
:
0
,
"fileData"
: [
"1.jpg"
,
"/9j/4AAQSkZJRgABAQEAYABgAAD/2wBDAAIBAQIBAQICAgICAgICAwUDAwMDAwYEBAMFBwYH"
+
"BwcGBwcICQsJCAgKCAcHCg0KCgsMDAwMBwkODw0MDgsMDAz/2wBDAQICAgMDAwYDAwYMCAcIDAwMDAwMDAwMDAwMDAwMD"
+
"AwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAz/wAARCAARABEDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAA"
+
"AAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fA"
+
"kM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWW"
+
"l5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBA"
+
"QEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRob"
+
"HBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYa"
+
"HiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oA"
+
"DAMBAAIRAxEAPwDqvg78Hf8Ahawjt7eO+n1Ce5NvDDbso3YVWycg4xkkkkAAZOACa0vjF+z3J8ILO6j1CHULXULdI5Fjl"
+
"kR0dWYDIKjDDkjIPUEdQRR+z38YofhBcQ6hHdR2+oWt20sayQtIrqyBCDgdCNw4IPPBBwa2P2hv2ho/jdbXV1dXVu140U"
+
"UEMMFu8caIrhsDcM9SzZYk5PpgD+OcViuKVxTGlSi/qN1d2le/MtFpbl5d366q2vDk2TeGUvDJ4jEPBfXvqVaXvVoLEfW"
+
"FCfIlDnvzX5bLlu38k/F6KKK/Xj+EQooooAKKKKAP/9k="
]
},
{
"valueId"
:
124
,
"value"
: {
"remove"
:
"Y"
}
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
'crm.product.update'
,
[
'id'
=>
4611
,
'fields'
=> [
'PROPERTY_186'
=> [
[
'valueId'
=>
0
,
'fileData'
=> [
'1.jpg'
,
'/9j/4AAQSkZJRgABAQEAYABgAAD/2wBDAAIBAQIBAQICAgICAgICAwUDAwMDAwYEBAMFBwYH'
.
'BwcGBwcICQsJCAgKCAcHCg0KCgsMDAwMBwkODw0MDgsMDAz/2wBDAQICAgMDAwYDAwYMCAcIDAwMDAwMDAwMDAwMDAwMD'
.
'AwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAz/wAARCAARABEDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAA'
.
'AAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fA'
.
'kM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWW'
.
'l5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBA'
.
'QEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRob'
.
'HBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYa'
.
'HiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oA'
.
'DAMBAAIRAxEAPwDqvg78Hf8Ahawjt7eO+n1Ce5NvDDbso3YVWycg4xkkkkAAZOACa0vjF+z3J8ILO6j1CHULXULdI5Fjl'
.
'kR0dWYDIKjDDkjIPUEdQRR+z38YofhBcQ6hHdR2+oWt20sayQtIrqyBCDgdCNw4IPPBBwa2P2hv2ho/jdbXV1dXVu140U'
.
'UEMMFu8caIrhsDcM9SzZYk5PpgD+OcViuKVxTGlSi/qN1d2le/MtFpbl5d366q2vDk2TeGUvDJ4jEPBfXvqVaXvVoLEfW'
.
'FCfIlDnvzX5bLlu38k/F6KKK/Xj+EQooooAKKKKAP/9k='
]
],
[
'valueId'
=>
124
,
'value'
=> [
'remove'
=>
'Y'
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
'Error updating product: '
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
"crm.product.update"
,
{
id
:
4611
,
fields
:
{
"PROPERTY_186"
: [
{
"valueId"
:
0
,
"fileData"
: [
"1.jpg"
,
"/9j/4AAQSkZJRgABAQEAYABgAAD/2wBDAAIBAQIBAQICAgICAgICAwUDAwMDAwYEBAMFBwYH"
+
"BwcGBwcICQsJCAgKCAcHCg0KCgsMDAwMBwkODw0MDgsMDAz/2wBDAQICAgMDAwYDAwYMCAcIDAwMDAwMDAwMDAwMDAwMD"
+
"AwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAz/wAARCAARABEDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAA"
+
"AAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fA"
+
"kM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWW"
+
"l5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBA"
+
"QEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRob"
+
"HBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYa"
+
"HiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oA"
+
"DAMBAAIRAxEAPwDqvg78Hf8Ahawjt7eO+n1Ce5NvDDbso3YVWycg4xkkkkAAZOACa0vjF+z3J8ILO6j1CHULXULdI5Fjl"
+
"kR0dWYDIKjDDkjIPUEdQRR+z38YofhBcQ6hHdR2+oWt20sayQtIrqyBCDgdCNw4IPPBBwa2P2hv2ho/jdbXV1dXVu140U"
+
"UEMMFu8caIrhsDcM9SzZYk5PpgD+OcViuKVxTGlSi/qN1d2le/MtFpbl5d366q2vDk2TeGUvDJ4jEPBfXvqVaXvVoLEfW"
+
"FCfIlDnvzX5bLlu38k/F6KKK/Xj+EQooooAKKKKAP/9k="
]
},
{
"valueId"
:
124
,
"value"
: {
"remove"
:
"Y"
}
}
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
'crm.product.update'
,
[
'id'
=>
4611
,
'fields'
=> [
'PROPERTY_186'
=> [
[
'valueId'
=>
0
,
'fileData'
=> [
'1.jpg'
,
'/9j/4AAQSkZJRgABAQEAYABgAAD/2wBDAAIBAQIBAQICAgICAgICAwUDAwMDAwYEBAMFBwYH'
.
'BwcGBwcICQsJCAgKCAcHCg0KCgsMDAwMBwkODw0MDgsMDAz/2wBDAQICAgMDAwYDAwYMCAcIDAwMDAwMDAwMDAwMDAwMD'
.
'AwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAz/wAARCAARABEDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAA'
.
'AAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fA'
.
'kM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWW'
.
'l5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBA'
.
'QEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRob'
.
'HBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYa'
.
'HiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oA'
.
'DAMBAAIRAxEAPwDqvg78Hf8Ahawjt7eO+n1Ce5NvDDbso3YVWycg4xkkkkAAZOACa0vjF+z3J8ILO6j1CHULXULdI5Fjl'
.
'kR0dWYDIKjDDkjIPUEdQRR+z38YofhBcQ6hHdR2+oWt20sayQtIrqyBCDgdCNw4IPPBBwa2P2hv2ho/jdbXV1dXVu140U'
.
'UEMMFu8caIrhsDcM9SzZYk5PpgD+OcViuKVxTGlSi/qN1d2le/MtFpbl5d366q2vDk2TeGUvDJ4jEPBfXvqVaXvVoLEfW'
.
'FCfIlDnvzX5bLlu38k/F6KKK/Xj+EQooooAKKKKAP/9k='
]
],
[
'valueId'
=>
124
,
'value'
=> [
'remove'
=>
'Y'
]
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
Get List of Products by Filter
Next
Get List of Product Property Types

---

## Get a list of product property types crm.product.property.types

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-property-types

Get a list of product property types crm.product.property.types | Bitrix24 REST API and Marketplace Applications
Get a list of product property types crm.product.property.types
Get a list of product property types crm.product.property.types
Scope:
crm
Who can execute the method: any user
Method development has been halted
The method
crm.product.property.types
is still operational, but there is a more relevant alternative
catalog.productPropertyFeature.*
.
The method
crm.product.property.types
returns a list of product property types.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":10}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.property.types
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":10,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.property.types
try
{
const
response =
await
$b24.
callMethod
(
"crm.product.property.types"
,
{
id
:
10
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
'crm.product.property.types'
,
[
'id'
=>
10
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
'Error calling crm.product.property.types: '
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
"crm.product.property.types"
,
{
id
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
'crm.product.property.types'
,
[
'id'
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
Copied
Was the article helpful?
Yes
No
Previous
Update Product
Next
Get Product Property Fields

---

## Get Product Property Fields crm.product.property.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-property-fields

Get Product Property Fields crm.product.property.fields | Bitrix24 REST API and Marketplace Applications
Get Product Property Fields crm.product.property.fields
Get Product Property Fields crm.product.property.fields
Scope:
crm
Who can execute the method: any user
Method development has been halted
The method
crm.product.property.fields
is still operational, but there is a more relevant alternative
catalog.productProperty.getFields
.
The method
crm.product.property.fields
returns the description of fields for product properties.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.property.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.property.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.product.property.fields"
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
'crm.product.property.fields'
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
'Error fetching product property fields: '
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
"crm.product.property.fields"
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
'crm.product.property.fields'
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
Get List of Product Property Types
Next
Get Fields of Additional Settings for Custom Type Properties

---

## Get the fields of additional settings for the custom type crm.product.property.settings.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-property-settings-fields

Get the fields of additional settings for the custom type crm.product.property.settings.fields | Bitrix24 REST API and Marketplace Applications
Get the fields of additional settings for the custom type crm.product.property.settings.fields
Get the fields of additional settings for the custom type crm.product.property.settings.fields
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Method development has been halted
The method
crm.product.property.settings.fields
continues to function, but there is a more relevant alternative
catalog.productPropertyFeature.*
.
The method
crm.product.property.settings.fields
returns a description of the fields for additional settings of custom type product properties.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
propertyType
Property type
userType
Custom property type
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
-d '{"propertyType":"S","userType":"HTML"}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.property.settings.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"propertyType":"S","userType":"HTML","auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.property.settings.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.product.property.settings.fields"
,
{
propertyType
:
"S"
,
userType
:
"HTML"
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
'crm.product.property.settings.fields'
,
[
'propertyType'
=>
'S'
,
'userType'
=>
'HTML'
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
'Error fetching product property settings fields: '
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
"crm.product.property.settings.fields"
,
{
propertyType
:
"S"
,
userType
:
"HTML"
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
'crm.product.property.settings.fields'
,
[
'propertyType'
=>
'S'
,
'userType'
=>
'HTML'
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
Get Product Property Fields
Next
Get Fields of List Type Property Element

---

## Get Fields of Enumeration Type Property crm.product.property.enumeration.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-property-enumeration-fields

Get Fields of Enumeration Type Property crm.product.property.enumeration.fields | Bitrix24 REST API and Marketplace Applications
Get Fields of Enumeration Type Property crm.product.property.enumeration.fields
Get Fields of Enumeration Type Property crm.product.property.enumeration.fields
Scope:
crm
Who can execute the method: any user
Method development has been halted
The method
crm.product.property.enumeration.fields
is still operational, but there is a more relevant alternative
catalog.productPropertyEnum.*
.
The method
crm.product.property.enumeration.fields
returns the description of the fields of the enumeration type product property.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.property.enumeration.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.property.enumeration.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.product.property.enumeration.fields"
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
'crm.product.property.enumeration.fields'
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
'Error fetching product property enumeration fields: '
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
"crm.product.property.enumeration.fields"
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
'crm.product.property.enumeration.fields'
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
Get Fields of Additional Settings for Custom Type Properties
Next
Add Product Property

---

## Add Product Property crm.product.property.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-property-add

Add Product Property crm.product.property.add | Bitrix24 REST API and Marketplace Applications
Add Product Property crm.product.property.add
Add Product Property crm.product.property.add
Method Parameters
Code Examples
Example 1
Example 2
Scope:
crm
Who can execute the method: administrator, user with the "Allow to modify settings" access permission in CRM
Method development has been halted
The method
crm.product.property.add
continues to function, but there is a more relevant alternative
catalog.productProperty.add
.
The method
crm.product.property.add
creates a new product property.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
array
Field values for creating a product property.
To find out the required format of the fields, execute the method
crm.product.property.fields
and check the format of the received values for these fields
Code Examples
Code Examples
How to Use Examples in Documentation
Example 1
Example 1
JS
PHP
BX24.js
PHP CRest
try
{
const
getCatalogId
=
async
(
) =>
{
try
{
const
catalogListResponse =
await
$b24.
callMethod
(
"crm.catalog.list"
,
{
filter
: {
"ORIGINATOR_ID"
:
""
,
"ORIGIN_ID"
:
""
}}
);
if
(catalogListResponse.
error
())
{
console
.
error
(catalogListResponse.
error
());
}
else
{
let
catalogId =
0
;
if
(catalogListResponse.
total
() !==
1
)
{
catalogId =
0
;
}
else
{
const
data = catalogListResponse.
getData
().
result
;
if
(data && data
instanceof
Array
&&
typeof
(data[
0
]) ===
"object"
&& data[
0
][
"ID"
])
{
catalogId =
parseInt
(data[
0
][
"ID"
]);
}
}
if
(catalogId <=
0
)
{
console
.
error
(
"Failed to retrieve the CRM product catalog ID"
);
}
else
{
await
addPropertyExample
(catalogId);
}
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
};
const
addPropertyExample
=
async
(
catalogId
) =>
{
try
{
const
propertyAddResponse =
await
$b24.
callMethod
(
"crm.product.property.add"
,
{
fields
: {
"ACTIVE"
:
"Y"
,
"IBLOCK_ID"
: catalogId,
"NAME"
:
"Property - HTML/Text"
,
"SORT"
:
500
,
"DEFAULT_VALUE"
: {
"TYPE"
:
"html"
,
"TEXT"
:
"<u><b>Delicious</b> \"<span style=\"color: #00a650;\">African bananas</span>\"</u>"
},
"USER_TYPE_SETTINGS"
: {
"HEIGHT"
:
300
},
"USER_TYPE"
:
"HTML"
,
"PROPERTY_TYPE"
:
"S"
}
}
);
const
result = propertyAddResponse.
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
};
const
start
=
async
(
) =>
{
await
getCatalogId
();
};
start
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
try
{
$responseCatalog
=
$b24Service
->core
->
call
(
'crm.catalog.list'
,
[
'filter'
=> [
'ORIGINATOR_ID'
=>
''
,
'ORIGIN_ID'
=>
''
],
]
);
$catalogId
=
0
;
$resultCatalog
=
$responseCatalog
->
getResponseData
()
->
getResult
();
if
(
$resultCatalog
->
total
() !==
1
) {
$catalogId
=
0
;
}
else
{
$data
=
$resultCatalog
->
data
();
if
(
$data
&&
is_array
(
$data
) &&
is_object
(
$data
[
0
]) &&
isset
(
$data
[
0
][
"ID"
])) {
$catalogId
= (
int
)
$data
[
0
][
"ID"
];
}
}
if
(
$catalogId
<=
0
) {
throw
new
Exception
(
"Failed to retrieve the CRM product catalog ID"
);
}
else
{
$responseProperty
=
$b24Service
->core
->
call
(
'crm.product.property.add'
,
[
'fields'
=> [
'ACTIVE'
=>
'Y'
,
'IBLOCK_ID'
=>
$catalogId
,
'NAME'
=>
'Property - HTML/Text'
,
'SORT'
=>
500
,
'DEFAULT_VALUE'
=> [
'TYPE'
=>
'html'
,
'TEXT'
=>
'<u><b>Delicious</b> "<span style="color: #00a650;">African bananas</span>"</u>'
,
],
'USER_TYPE_SETTINGS'
=> [
'HEIGHT'
=>
300
,
],
'USER_TYPE'
=>
'HTML'
,
'PROPERTY_TYPE'
=>
'S'
,
],
]
);
$resultProperty
=
$responseProperty
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
$resultProperty
,
true
);
// Your logic for processing data
processData
(
$resultProperty
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
'Error adding product property: '
.
$e
->
getMessage
();
}
// Creating a custom property of type S:HTML
function
addPropertyExample
(
catalogId
)
{
BX24
.
callMethod
(
"crm.product.property.add"
,
{
fields
: {
"ACTIVE"
:
"Y"
,
"IBLOCK_ID"
: catalogId,
"NAME"
:
"Property - HTML/Text"
,
"SORT"
:
500
,
"DEFAULT_VALUE"
: {
"TYPE"
:
"html"
,
"TEXT"
:
"<u><b>Delicious</b> \"<span style=\"color: #00a650;\">African bananas</span>\"</u>"
},
"USER_TYPE_SETTINGS"
: {
"HEIGHT"
:
300
},
"USER_TYPE"
:
"HTML"
,
"PROPERTY_TYPE"
:
"S"
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
}
function
getCatalogId
(
)
{
BX24
.
callMethod
(
"crm.catalog.list"
,
{
filter
: {
"ORIGINATOR_ID"
:
""
,
"ORIGIN_ID"
:
""
}},
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
var
catalogId =
0
;
if
(result.
total
() !==
1
)
{
catalogId =
0
}
else
{
data = result.
data
();
if
(data && data
instanceof
Array
&&
typeof
(data[
0
]) ===
"object"
&& data[
0
][
"ID"
])
{
catalogId =
parseInt
(data[
0
][
"ID"
]);
}
}
if
(catalogId <=
0
)
{
console
.
error
(
"Failed to retrieve the CRM product catalog ID"
);
}
else
{
addPropertyExample
(catalogId);
}
}
}
);
}
function
start
(
)
{
getCatalogId
();
}
start
();
require_once
(
'crest.php'
);
// Function to add a custom property
function
addPropertyExample
(
$catalogId
)
{
$result
=
CRest
::
call
(
'crm.product.property.add'
,
[
'fields'
=> [
'ACTIVE'
=>
'Y'
,
'IBLOCK_ID'
=>
$catalogId
,
'NAME'
=>
'Property - HTML/Text'
,
'SORT'
=>
500
,
'DEFAULT_VALUE'
=> [
'TYPE'
=>
'html'
,
'TEXT'
=>
'<u><b>Delicious</b> "<span style="color: #00a650;">African bananas</span>"</u>'
],
'USER_TYPE_SETTINGS'
=> [
'HEIGHT'
=>
300
],
'USER_TYPE'
=>
'HTML'
,
'PROPERTY_TYPE'
=>
'S'
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
}
// Function to get catalog ID
function
getCatalogId
(
)
{
$result
=
CRest
::
call
(
'crm.catalog.list'
,
[
'filter'
=> [
'ORIGINATOR_ID'
=>
''
,
'ORIGIN_ID'
=>
''
]]
);
if
(
$result
[
'error'
]) {
echo
'Error: '
.
$result
[
'error_description'
];
}
else
{
$catalogId
=
0
;
if
(
$result
[
'total'
] !==
1
) {
$catalogId
=
0
;
}
else
{
$data
=
$result
[
'result'
];
if
(
$data
&&
is_array
(
$data
) &&
isset
(
$data
[
0
][
'ID'
])) {
$catalogId
=
intval
(
$data
[
0
][
'ID'
]);
}
}
if
(
$catalogId
<=
0
) {
echo
"Failed to retrieve the CRM product catalog ID"
;
}
else
{
addPropertyExample
(
$catalogId
);
}
}
}
// Start the process
getCatalogId
();
Example 2
Example 2
JS
PHP
BX24.js
PHP CRest
try
{
const
getCatalogId
=
async
(
) =>
{
try
{
const
response =
await
$b24.
callMethod
(
"crm.catalog.list"
,
{
filter
: {
"ORIGINATOR_ID"
:
""
,
"ORIGIN_ID"
:
""
}}
);
if
(response.
error
())
{
console
.
error
(response.
error
());
}
else
{
let
catalogId =
0
;
if
(response.
total
() !==
1
)
{
catalogId =
0
;
}
else
{
const
data = response.
getData
().
result
;
if
(data && data
instanceof
Array
&&
typeof
(data[
0
]) ===
"object"
&& data[
0
][
"ID"
])
{
catalogId =
parseInt
(data[
0
][
"ID"
]);
}
}
if
(catalogId <=
0
)
{
console
.
error
(
"Failed to retrieve the CRM product catalog ID"
);
}
else
{
await
addPropertyExample
(catalogId);
}
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
};
const
addPropertyExample
=
async
(
catalogId
) =>
{
try
{
const
response =
await
$b24.
callMethod
(
"crm.product.property.add"
,
{
fields
: {
"ACTIVE"
:
"Y"
,
"IBLOCK_ID"
: catalogId,
"NAME"
:
"Property - List"
,
"SORT"
:
510
,
"MULTIPLE"
:
"Y"
,
"ROW_COUNT"
:
7
,
"LIST_TYPE"
:
"L"
,
"PROPERTY_TYPE"
:
"L"
,
"VALUES"
: {
"n0"
: {
"ID"
:
"n0"
,
"VALUE"
:
"List value 1"
,
"SORT"
:
100
,
"DEF"
:
"Y"
},
"n1"
: {
"ID"
:
"n1"
,
"VALUE"
:
"List value 2"
,
"SORT"
:
200
,
"DEF"
:
"N"
},
"n2"
: {
"ID"
:
"n2"
,
"VALUE"
:
"List value 3"
,
"SORT"
:
300
,
"DEF"
:
"Y"
},
"n3"
: {
"ID"
:
"n3"
,
"VALUE"
:
"List value 4"
,
"SORT"
:
400
,
"DEF"
:
"N"
},
"n4"
: {
"ID"
:
"n4"
,
"VALUE"
:
"List value 5"
,
"SORT"
:
500
,
"DEF"
:
"N"
},
"n5"
: {
"ID"
:
"n5"
,
"VALUE"
:
"List value 6"
,
"SORT"
:
600
,
"DEF"
:
"N"
},
"n6"
: {
"ID"
:
"n6"
,
"VALUE"
:
"List value 7"
,
"SORT"
:
700
,
"DEF"
:
"N"
},
"n7"
: {
"ID"
:
"n7"
,
"VALUE"
:
"List value 8"
,
"SORT"
:
800
,
"DEF"
:
"N"
}
}
}
}
);
console
.
dir
(response.
getData
().
result
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
};
const
start
=
async
(
) =>
{
await
getCatalogId
();
};
start
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.catalog.list'
,
[
'filter'
=> [
'ORIGINATOR_ID'
=>
''
,
'ORIGIN_ID'
=>
''
],
]
);
if
(
$response
->
getError
()) {
error_log
(
$response
->
getError
());
echo
'Error getting catalog list: '
.
$response
->
getError
();
}
else
{
$catalogId
=
0
;
$result
=
$response
->
getResponseData
()->
getResult
();
if
(
$result
->
total
() !==
1
) {
$catalogId
=
0
;
}
else
{
$data
=
$result
->
getData
();
if
(
$data
&&
is_array
(
$data
) &&
is_object
(
$data
[
0
]) &&
isset
(
$data
[
0
][
"ID"
])) {
$catalogId
= (
int
)
$data
[
0
][
"ID"
];
}
}
if
(
$catalogId
<=
0
) {
error_log
(
"Failed to retrieve the CRM product catalog ID"
);
echo
"Failed to retrieve the CRM product catalog ID"
;
}
else
{
$response
=
$b24Service
->core
->
call
(
'crm.product.property.add'
,
[
'fields'
=> [
'ACTIVE'
=>
'Y'
,
'IBLOCK_ID'
=>
$catalogId
,
'NAME'
=>
'Property - List'
,
'SORT'
=>
510
,
'MULTIPLE'
=>
'Y'
,
'ROW_COUNT'
=>
7
,
'LIST_TYPE'
=>
'L'
,
'PROPERTY_TYPE'
=>
'L'
,
'VALUES'
=> [
'n0'
=> [
'ID'
=>
'n0'
,
'VALUE'
=>
'List value 1'
,
'SORT'
=>
100
,
'DEF'
=>
'Y'
,
],
'n1'
=> [
'ID'
=>
'n1'
,
'VALUE'
=>
'List value 2'
,
'SORT'
=>
200
,
'DEF'
=>
'N'
,
],
'n2'
=> [
'ID'
=>
'n2'
,
'VALUE'
=>
'List value 3'
,
'SORT'
=>
300
,
'DEF'
=>
'Y'
,
],
'n3'
=> [
'ID'
=>
'n3'
,
'VALUE'
=>
'List value 4'
,
'SORT'
=>
400
,
'DEF'
=>
'N'
,
],
'n4'
=> [
'ID'
=>
'n4'
,
'VALUE'
=>
'List value 5'
,
'SORT'
=>
500
,
'DEF'
=>
'N'
,
],
'n5'
=> [
'ID'
=>
'n5'
,
'VALUE'
=>
'List value 6'
,
'SORT'
=>
600
,
'DEF'
=>
'N'
,
],
'n6'
=> [
'ID'
=>
'n6'
,
'VALUE'
=>
'List value 7'
,
'SORT'
=>
700
,
'DEF'
=>
'N'
,
],
'n7'
=> [
'ID'
=>
'n7'
,
'VALUE'
=>
'List value 8'
,
'SORT'
=>
800
,
'DEF'
=>
'N'
,
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
()->
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
function
addPropertyExample
(
catalogId
)
{
BX24
.
callMethod
(
"crm.product.property.add"
,
{
fields
: {
"ACTIVE"
:
"Y"
,
"IBLOCK_ID"
: catalogId,
"NAME"
:
"Property - List"
,
"SORT"
:
510
,
"MULTIPLE"
:
"Y"
,
"ROW_COUNT"
:
7
,
"LIST_TYPE"
:
"L"
,
"PROPERTY_TYPE"
:
"L"
,
"VALUES"
: {
"n0"
: {
"ID"
:
"n0"
,
"VALUE"
:
"List value 1"
,
"SORT"
:
100
,
"DEF"
:
"Y"
},
"n1"
: {
"ID"
:
"n1"
,
"VALUE"
:
"List value 2"
,
"SORT"
:
200
,
"DEF"
:
"N"
},
"n2"
: {
"ID"
:
"n2"
,
"VALUE"
:
"List value 3"
,
"SORT"
:
300
,
"DEF"
:
"Y"
},
"n3"
: {
"ID"
:
"n3"
,
"VALUE"
:
"List value 4"
,
"SORT"
:
400
,
"DEF"
:
"N"
},
"n4"
: {
"ID"
:
"n4"
,
"VALUE"
:
"List value 5"
,
"SORT"
:
500
,
"DEF"
:
"N"
},
"n5"
: {
"ID"
:
"n5"
,
"VALUE"
:
"List value 6"
,
"SORT"
:
600
,
"DEF"
:
"N"
},
"n6"
: {
"ID"
:
"n6"
,
"VALUE"
:
"List value 7"
,
"SORT"
:
700
,
"DEF"
:
"N"
},
"n7"
: {
"ID"
:
"n7"
,
"VALUE"
:
"List value 8"
,
"SORT"
:
800
,
"DEF"
:
"N"
}
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
}
function
getCatalogId
(
)
{
BX24
.
callMethod
(
"crm.catalog.list"
,
{
filter
: {
"ORIGINATOR_ID"
:
""
,
"ORIGIN_ID"
:
""
}},
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
var
catalogId =
0
;
if
(result.
total
() !==
1
)
{
catalogId =
0
}
else
{
data = result.
data
();
if
(data && data
instanceof
Array
&&
typeof
(data[
0
]) ===
"object"
&& data[
0
][
"ID"
])
{
catalogId =
parseInt
(data[
0
][
"ID"
]);
}
}
if
(catalogId <=
0
)
{
console
.
error
(
"Failed to retrieve the CRM product catalog ID"
);
}
else
{
addPropertyExample
(catalogId);
}
}
}
);
}
function
start
(
)
{
getCatalogId
();
}
start
();
require_once
(
'crest.php'
);
function
addPropertyExample
(
$catalogId
)
{
$result
=
CRest
::
call
(
'crm.product.property.add'
,
[
'fields'
=> [
'ACTIVE'
=>
'Y'
,
'IBLOCK_ID'
=>
$catalogId
,
'NAME'
=>
'Property - List'
,
'SORT'
=>
510
,
'MULTIPLE'
=>
'Y'
,
'ROW_COUNT'
=>
7
,
'LIST_TYPE'
=>
'L'
,
'PROPERTY_TYPE'
=>
'L'
,
'VALUES'
=> [
'n0'
=> [
'ID'
=>
'n0'
,
'VALUE'
=>
'List value 1'
,
'SORT'
=>
100
,
'DEF'
=>
'Y'
},
'n1'
=> [
'ID'
=>
'n1'
,
'VALUE'
=>
'List value 2'
,
'SORT'
=>
200
,
'DEF'
=>
'N'
},
'n2'
=> [
'ID'
=>
'n2'
,
'VALUE'
=>
'List value 3'
,
'SORT'
=>
300
,
'DEF'
=>
'Y'
],
// Continue
for
other values...
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
}
function
getCatalogId
(
)
{
$result
=
CRest
::
call
(
'crm.catalog.list'
,
[
'filter'
=> [
'ORIGINATOR_ID'
=>
''
,
'ORIGIN_ID'
=>
''
]]
);
if
(
isset
(
$result
[
'error'
])) {
echo
'Error: '
.
$result
[
'error_description'
];
}
else
{
$catalogId
=
0
;
if
(
count
(
$result
[
'result'
]) !==
1
) {
echo
"Failed to retrieve the CRM product catalog ID"
;
}
else
{
$data
=
$result
[
'result'
];
if
(
isset
(
$data
[
0
][
'ID'
])) {
$catalogId
=
intval
(
$data
[
0
][
'ID'
]);
addPropertyExample
(
$catalogId
);
}
}
}
}
getCatalogId
();
Copied
Was the article helpful?
Yes
No
Previous
Get Fields of List Type Property Element
Next
Get Product Property by ID

---

## Get product property by ID crm.product.property.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-property-get

Get product property by ID crm.product.property.get | Bitrix24 REST API and Marketplace Applications
Get product property by ID crm.product.property.get
Get product property by ID crm.product.property.get
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
Method development has been halted
The method
crm.product.property.get
continues to function, but there is a more relevant alternative
catalog.productProperty.get
.
The method
crm.product.property.get
returns the property of products by ID.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the product property
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
-d '{"id":"your_product_id"}' \ # Replace 'your_product_id' with the actual product ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_property_id"}' \ # Replace 'your_property_id' with the actual property ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.property.get
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
"crm.product.property.get"
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
'crm.product.property.get'
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
'Error calling crm.product.property.get: '
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
"crm.product.property.get"
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
require_once
(
'crest.php'
);
$id
=
'your_property_id'
;
// Replace 'your_property_id' with the actual property ID
$result
=
CRest
::
call
(
'crm.product.property.get'
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
Add Product Property
Next
Get List of Product Properties

---

## Get a list of product properties crm.product.property.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-property-list

Get a list of product properties crm.product.property.list | Bitrix24 REST API and Marketplace Applications
Get a list of product properties crm.product.property.list
Get a list of product properties crm.product.property.list
Method parameters
Code examples
Scope:
crm
Who can execute the method: any user
Method development has been halted
The method
crm.product.property.list
continues to function, but there is a more current equivalent
catalog.productProperty.list
.
The method
crm.product.property.list
returns a list of product properties.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
order
Sorting
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
-d '{"order":{"SORT":"ASC"},"filter":{"PROPERTY_TYPE":"S","USER_TYPE":"HTML"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.property.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"order":{"SORT":"ASC"},"filter":{"PROPERTY_TYPE":"S","USER_TYPE":"HTML"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.property.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.product.property.list'
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
"PROPERTY_TYPE"
:
"S"
,
"USER_TYPE"
:
"HTML"
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
'crm.product.property.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"PROPERTY_TYPE"
:
"S"
,
"USER_TYPE"
:
"HTML"
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
'crm.product.property.list'
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"PROPERTY_TYPE"
:
"S"
,
"USER_TYPE"
:
"HTML"
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
'crm.product.property.list'
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
'PROPERTY_TYPE'
=>
'S'
,
'USER_TYPE'
=>
'HTML'
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
'Error fetching product properties: '
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
"crm.product.property.list"
, {
order
: {
"SORT"
:
"ASC"
},
filter
: {
"PROPERTY_TYPE"
:
"S"
,
"USER_TYPE"
:
"HTML"
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
'crm.product.property.list'
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
'PROPERTY_TYPE'
=>
'S'
,
'USER_TYPE'
=>
'HTML'
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
Get Product Property by ID
Next
Update Product Property

---

## Update Product Property crm.product.property.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-property-update

Update Product Property crm.product.property.update | Bitrix24 REST API and Marketplace Applications
Update Product Property crm.product.property.update
Update Product Property crm.product.property.update
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: administrator, user with the "Allow changing settings" access permission in CRM
Method development halted
The method
crm.product.property.update
is still operational, but there is a more current equivalent
catalog.productProperty.update
.
The method
crm.product.property.update
updates an existing product property.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Identifier of the product property
fields
array
Field values for updating the product property.
To find out the required format of the fields, execute the method
crm.product.property.fields
and check the format of the incoming values for these fields
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
-d '{"id":"your_property_id","fields":{"NAME":"New Property Name"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.property.update
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_property_id","fields":{"NAME":"New Property Name"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.product.property.update
try
{
const
id =
prompt
(
"Enter ID"
);
const
propertyName =
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
"crm.product.property.update"
,
{
id
: id,
fields
:
{
"NAME"
: propertyName
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
$propertyName
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
'crm.product.property.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'NAME'
=>
$propertyName
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
'Error updating product property: '
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
propertyName =
prompt
(
"Enter new name"
);
BX24
.
callMethod
(
"crm.product.property.update"
,
{
id
: id,
fields
:
{
"NAME"
: propertyName
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
'your_property_id'
;
// Replace 'your_property_id' with the actual property ID
$propertyName
=
'New Property Name'
;
// Replace 'New Property Name' with the new name
$result
=
CRest
::
call
(
'crm.product.property.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'NAME'
=>
$propertyName
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
Get List of Product Properties
Next
Delete Product Property

---

## Delete Product Property crm.product.property.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/crm-product-property-delete

Delete Product Property crm.product.property.delete | Bitrix24 REST API and Marketplace Applications
Delete Product Property crm.product.property.delete
Delete Product Property crm.product.property.delete
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: administrator, user with the "Allow to modify settings" access permission in CRM
Method development halted
The method
crm.product.property.delete
is still operational, but there is a more relevant alternative
catalog.productProperty.delete
.
The method
crm.product.property.delete
removes a product property.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
integer
Product identifier
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
-d '{"id":"your_property_id"}' \ # Replace 'your_property_id' with the actual property ID
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.product.property.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":"your_property_id","auth":"**put_access_token_here**"}' \ # Replace 'your_property_id' with the actual property ID
https://**put_your_bitrix24_address**/rest/crm.product.property.delete
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
"crm.product.property.delete"
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
'crm.product.property.delete'
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
'Error deleting product property: '
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
"crm.product.property.delete"
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
require_once
(
'crest.php'
);
$id
=
'your_property_id'
;
// Replace 'your_property_id' with the actual property ID
$result
=
CRest
::
call
(
'crm.product.property.delete'
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
Update Product Property
Next
Events

---

## Events

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/events-custom/index

Events | Bitrix24 REST API and Marketplace Applications
Events
Events
Scope:
crm
Who can subscribe: any user
Event
Triggered by
onCrmProductAdd
when a product is created
onCrmProductUpdate
when a product is updated
onCrmProductDelete
when a product is deleted
onCrmProductPropertyAdd
when a product property is created
onCrmProductPropertyUpdate
when a product property is updated
onCrmProductPropertyDelete
when a product property is deleted
Copied
Was the article helpful?
Yes
No
Previous
Delete Product Property
Next
On Product Addition

---

## Event onCrmProductAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/events-custom/on-crm-product-add

Event onCrmProductAdd | Bitrix24 REST API and Marketplace Applications
Parameters
Event onCrmProductAdd
Event development has been halted
The event
onCrmProductAdd
is still operational, but it has a more relevant counterpart
CATALOG.PRODUCT.ON.ADD
.
The event is triggered when a product is created.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
The array contains the field ID with the value of the created product's identifier
Copied
Was the article helpful?
Yes
No
Previous
Events
Next
On Product Update

---

## Event onCrmProductUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/events-custom/on-crm-product-update

Event onCrmProductUpdate | Bitrix24 REST API and Marketplace Applications
Parameters
Event onCrmProductUpdate
Event development has been halted
The event
onCrmProductUpdate
is still operational, but there is a more relevant alternative
CATALOG.PRODUCT.ON.UPDATE
.
The event is triggered when a product is updated.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
The array contains the ID field with the value of the updated product's identifier
Copied
Was the article helpful?
Yes
No
Previous
On Product Addition
Next
On Product Deletion

---

## Event onCrmProductDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/events-custom/on-crm-product-delete

Event onCrmProductDelete | Bitrix24 REST API and Marketplace Applications
Parameters
Event onCrmProductDelete
Event development has been halted
The event
onCrmProductDelete
is still operational, but there is a more relevant alternative
CATALOG.PRODUCT.ON.DELETE
.
The event is triggered when a product is deleted.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
The array contains the ID field with the value of the deleted product's identifier
Copied
Was the article helpful?
Yes
No
Previous
On Product Update
Next
On Product Property Addition

---

## Event for Adding Product Property onCrmProductPropertyAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/events-custom/on-crm-product-property-add

Event for Adding Product Property onCrmProductPropertyAdd | Bitrix24 REST API and Marketplace Applications
Parameters
Event for Adding Product Property onCrmProductPropertyAdd
This event is triggered when a product property is added.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
The array contains the field ID with the value of the created property identifier
Copied
Was the article helpful?
Yes
No
Previous
On Product Deletion
Next
On Product Property Update

---

## Event onCrmProductPropertyUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/events-custom/on-crm-product-property-update

Event onCrmProductPropertyUpdate | Bitrix24 REST API and Marketplace Applications
Parameters
Event onCrmProductPropertyUpdate
This event is triggered when a product property is changed.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
The array contains the field ID with the value of the modified property
Copied
Was the article helpful?
Yes
No
Previous
On Product Property Addition
Next
On Product Property Deletion

---

## Event onCrmProductPropertyDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/products/events-custom/on-crm-product-property-delete

Event onCrmProductPropertyDelete | Bitrix24 REST API and Marketplace Applications
Parameters
Event onCrmProductPropertyDelete
The event is triggered when a product property is deleted.
Parameters
Parameters
Required parameters are marked with *
Name
type
Description
FIELDS
The array contains the field ID with the value of the deleted property identifier
Copied
Was the article helpful?
Yes
No
Previous
On Product Property Update
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: any user
Method
Description
crm.productsection.add
Creates a new product section.
crm.productsection.delete
Deletes a product section.
crm.productsection.fields
Returns the description of the product section fields.
crm.productsection.get
Returns the product section by its identifier.
crm.productsection.list
Returns a list of product sections based on a filter.
crm.productsection.update
Updates an existing product section.
Copied
Was the article helpful?
Yes
No
Previous
On Product Property Deletion
Next
Add New Product Section

---

## Add a New Product Section crm.productsection.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/crm-product-section-add

Add a New Product Section crm.productsection.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add a New Product Section crm.productsection.add
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
The method
crm.productsection.add
creates a new product section.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
array
A set of fields — an array of the form
array("field"=>"value"[, ...])
, containing the values of the product section fields.
Note
To find out the required format of the fields, execute the method
crm.productsection.fields
and check the format of the returned values for these fields.
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
catalogId=$(prompt "Enter catalog ID")
sectionId=$(prompt "Enter parent section ID (0 if at root)")
sectionName=$(prompt "Enter section name")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"fields": {
"CATALOG_ID": '"$catalogId"',
"NAME": "'"$sectionName"'",
"SECTION_ID": '"$sectionId"'
}
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.productsection.add
catalogId=$(prompt "Enter catalog ID")
sectionId=$(prompt "Enter parent section ID (0 if at root)")
sectionName=$(prompt "Enter section name")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"fields": {
"CATALOG_ID": '"$catalogId"',
"NAME": "'"$sectionName"'",
"SECTION_ID": '"$sectionId"'
},
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/crm.productsection.add
try
{
const
catalogId =
prompt
(
"Enter catalog ID"
);
const
sectionId =
prompt
(
"Enter parent section ID (0 if at root)"
);
const
sectionName =
prompt
(
"Enter section name"
);
const
response =
await
$b24.
callMethod
(
"crm.productsection.add"
,
{
fields
:
{
CATALOG_ID
: catalogId,
NAME
: sectionName,
SECTION_ID
: sectionId
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
"A new section has been created with ID "
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
$catalogId
=
readline
(
"Enter catalog ID"
);
$sectionId
=
readline
(
"Enter parent section ID (0 if at root)"
);
$sectionName
=
readline
(
"Enter section name"
);
$response
=
$b24Service
->core
->
call
(
"crm.productsection.add"
,
[
'fields'
=> [
'CATALOG_ID'
=>
$catalogId
,
'NAME'
=>
$sectionName
,
'SECTION_ID'
=>
$sectionId
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
"A new section has been created with ID "
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
'Error creating product section: '
.
$e
->
getMessage
();
}
var
catalogId =
prompt
(
"Enter catalog ID"
);
var
sectionId =
prompt
(
"Enter parent section ID (0 if at root)"
);
var
sectionName =
prompt
(
"Enter section name"
);
BX24
.
callMethod
(
"crm.productsection.add"
,
{
fields
:
{
CATALOG_ID
: catalogId,
NAME
: sectionName,
SECTION_ID
: sectionId
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
"A new section has been created with ID "
+ result.
data
());
}
);
require_once
(
'crest.php'
);
$catalogId
=
readline
(
"Enter catalog ID: "
);
$sectionId
=
readline
(
"Enter parent section ID (0 if at root): "
);
$sectionName
=
readline
(
"Enter section name: "
);
$result
=
CRest
::
call
(
'crm.productsection.add'
,
[
'fields'
=> [
'CATALOG_ID'
=>
$catalogId
,
'NAME'
=>
$sectionName
,
'SECTION_ID'
=>
$sectionId
]
]
);
if
(
isset
(
$result
[
'error'
])) {
echo
"Error: "
.
$result
[
'error_description'
] .
"\n"
;
}
else
{
echo
"A new section has been created with ID "
.
$result
[
'result'
] .
"\n"
;
}
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Product Section

---

## Update Product Section <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-7nriil7i">crm.productsection.update</code>

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/crm-product-section-update

Update Product Section <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-7nriil7i">crm.productsection.update</code> | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Product Section
crm.productsection.update
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
The method
crm.productsection.update
updates an existing product section.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the product section
fields
array
Set of fields
— an array in the form
array("field_to_update"=>"value"[, ...])
, where "field_to_update" can take values from the returned method
crm.productsection.fields
.
Note
To find out the required format of the fields, execute the method
crm.productsection.fields
and check the format of the returned values for those fields.
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
id=$(prompt "Enter ID")
sectionName=$(prompt "Enter section name")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"id": '"$id"',
"fields": {
"NAME": "'"$sectionName"'"
}
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.productsection.update
id=$(prompt "Enter ID")
sectionName=$(prompt "Enter section name")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"id": '"$id"',
"fields": {
"NAME": "'"$sectionName"'"
},
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/crm.productsection.update
try
{
const
id =
prompt
(
"Enter ID"
);
const
sectionName =
prompt
(
"Enter section name"
);
const
response =
await
$b24.
callMethod
(
"crm.productsection.update"
,
{
id
: id,
fields
:
{
"NAME"
: sectionName
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
"Enter ID: "
);
$sectionName
=
readline
(
"Enter section name: "
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
'crm.productsection.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'NAME'
=>
$sectionName
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
'Error updating product section: '
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
sectionName =
prompt
(
"Enter section name"
);
BX24
.
callMethod
(
"crm.productsection.update"
,
{
id
: id,
fields
:
{
"NAME"
: sectionName
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
$id
=
readline
(
"Enter ID: "
);
$sectionName
=
readline
(
"Enter section name: "
);
$result
=
CRest
::
call
(
'crm.productsection.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'NAME'
=>
$sectionName
]
]
);
if
(
isset
(
$result
[
'error'
])) {
echo
"Error: "
.
$result
[
'error_description'
] .
"\n"
;
}
else
{
echo
"Updated section with ID "
.
$id
.
"\n"
;
echo
'<PRE>'
;
print_r
(
$result
[
'result'
]);
echo
'</PRE>'
;
}
Copied
Was the article helpful?
Yes
No
Previous
Add New Product Section
Next
Get Product Section by ID

---

## Get Product Section by ID crm.productsection.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/crm-product-section-get

Get Product Section by ID crm.productsection.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Product Section by ID crm.productsection.get
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
The method
crm.productsection.get
returns the product section
by its ID.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Product section ID
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
id=$(prompt "Enter ID")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"id": '"$id"'
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.productsection.get
id=$(prompt "Enter ID")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"id": '"$id"',
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/crm.productsection.get
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
"crm.productsection.get"
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
'crm.productsection.get'
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
'Error getting product section: '
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
"crm.productsection.get"
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
'crm.productsection.get'
,
[
'id'
=>
$id
]
);
if
(
isset
(
$result
[
'error'
])) {
echo
"Error: "
.
$result
[
'error_description'
] .
"\n"
;
}
else
{
echo
'<PRE>'
;
print_r
(
$result
[
'result'
]);
echo
'</PRE>'
;
}
Copied
Was the article helpful?
Yes
No
Previous
Update Product Section
Next
Get List of Product Sections by Filter

---

## Get the list of sections crm.productsection.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/crm-product-section-list

Get the list of sections crm.productsection.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of sections crm.productsection.list
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
The method
crm.productsection.list
returns a list of product sections based on a filter. It is an implementation of a list method for product sections. It is expected that the filter will define the
CATALOG_ID
parameter. Otherwise, sections will be selected from the default catalog.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
select
array
The array contains a list of fields to select
filter
object
An object for filtering the selected items
order
object
An object for sorting the selected items
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
catalogId=$(prompt "Enter the catalog ID")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"order": { "NAME": "ASC" },
"filter": { "CATALOG_ID": '"$catalogId"' },
"select": [ "ID", "NAME" ]
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.productsection.list
catalogId=$(prompt "Enter the catalog ID")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"order": { "NAME": "ASC" },
"filter": { "CATALOG_ID": '"$catalogId"' },
"select": [ "ID", "NAME" ],
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/crm.productsection.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
var
catalogId =
prompt
(
"Enter the catalog ID"
);
try
{
const
response =
await
$b24.
callListMethod
(
'crm.productsection.list'
,
{
order
: {
"NAME"
:
"ASC"
},
filter
: {
"CATALOG_ID"
: catalogId },
select
: [
"ID"
,
"NAME"
]
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
var
catalogId =
prompt
(
"Enter the catalog ID"
);
try
{
const
generator = $b24.
fetchListMethod
(
'crm.productsection.list'
, {
order
: {
"NAME"
:
"ASC"
},
filter
: {
"CATALOG_ID"
: catalogId },
select
: [
"ID"
,
"NAME"
]
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
var
catalogId =
prompt
(
"Enter the catalog ID"
);
try
{
const
response =
await
$b24.
callMethod
(
'crm.productsection.list'
, {
order
: {
"NAME"
:
"ASC"
},
filter
: {
"CATALOG_ID"
: catalogId },
select
: [
"ID"
,
"NAME"
]
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
$catalogId
=
readline
(
"Enter the catalog ID"
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
'crm.productsection.list'
,
[
'order'
=> [
'NAME'
=>
'ASC'
],
'filter'
=> [
'CATALOG_ID'
=>
$catalogId
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
'Error: '
.
$e
->
getMessage
();
}
var
catalogId =
prompt
(
"Enter the catalog ID"
);
BX24
.
callMethod
(
"crm.productsection.list"
,
{
order
: {
"NAME"
:
"ASC"
},
filter
: {
"CATALOG_ID"
: catalogId },
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
$catalogId
=
readline
(
"Enter the catalog ID: "
);
$result
=
CRest
::
call
(
'crm.productsection.list'
,
[
'order'
=> [
'NAME'
=>
'ASC'
],
'filter'
=> [
'CATALOG_ID'
=>
$catalogId
],
'select'
=> [
'ID'
,
'NAME'
]
]
);
if
(
isset
(
$result
[
'error'
])) {
echo
"Error: "
.
$result
[
'error_description'
] .
"\n"
;
}
else
{
echo
'<PRE>'
;
print_r
(
$result
[
'result'
]);
echo
'</PRE>'
;
}
Copied
Was the article helpful?
Yes
No
Previous
Get Product Section by ID
Next
Delete Product Section

---

## Delete Product Section crm.productsection.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/crm-product-section-delete

Delete Product Section crm.productsection.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Product Section crm.productsection.delete
Method Parameters
Code Examples
Scope:
crm
Who can execute the method: any user
The method
crm.productsection.delete
removes a product catalog section.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the product section
Code Examples
Code Examples
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
id=$(prompt "Enter ID")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"id": '"$id"'
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.productsection.delete
id=$(prompt "Enter ID")
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"id": '"$id"',
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/crm.productsection.delete
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
"crm.productsection.delete"
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
'crm.productsection.delete'
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
'Error deleting product section: '
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
"crm.productsection.delete"
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
'crm.productsection.delete'
,
[
'id'
=>
$id
]
);
if
(
isset
(
$result
[
'error'
])) {
echo
"Error: "
.
$result
[
'error_description'
] .
"\n"
;
}
else
{
echo
"Deleted section with ID "
.
$id
.
"\n"
;
}
Copied
Was the article helpful?
Yes
No
Previous
Get List of Product Sections by Filter
Next
Get Fields of Product Section

---

## Get Fields of the Product Section crm.productsection.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/crm-product-section-fields

Get Fields of the Product Section crm.productsection.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Fields of the Product Section crm.productsection.fields
Code Examples
Fields
Scope:
crm
Who can execute the method: any user
The method
crm.productsection.fields
returns the description of the
fields of the section
of the product.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.productsection.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/crm.productsection.fields
try
{
const
response =
await
$b24.
callMethod
(
"crm.productsection.fields"
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
'crm.productsection.fields'
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
'Error fetching product section fields: '
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
"crm.productsection.fields"
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
'crm.productsection.fields'
,
[]
);
if
(
isset
(
$result
[
'error'
])) {
echo
"Error: "
.
$result
[
'error_description'
] .
"\n"
;
}
else
{
echo
'<PRE>'
;
print_r
(
$result
[
'result'
]);
echo
'</PRE>'
;
}
Fields
Fields
Name
type
Description
Note
CATALOG_ID
integer
Catalog identifier
Immutable
ID
integer
Section identifier
Read-only
NAME
string
Section name
Required
SECTION_ID
integer
Identifier of the linked section
XML_ID
string
Symbolic code
Copied
Was the article helpful?
Yes
No
Previous
Delete Product Section
Next
Overview of Events

---

## Events

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/events/index

Events | Bitrix24 REST API and Marketplace Applications
Events
Events
Scope:
crm
Who can subscribe: any user
Event
Triggered
onCrmProductSectionAdd
After adding a section
onCrmProductSectionUpdate
After updating a section
onCrmProductSectionDelete
After deleting a section
Copied
Was the article helpful?
Yes
No
Previous
Get Fields of Product Section
Next
On Adding a Section

---

## Event for Adding a New Product Section onCrmProductSectionAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/events/on-crm-product-section-add

Event for Adding a New Product Section onCrmProductSectionAdd | Bitrix24 REST API and Marketplace Applications
Handling the Response
Event for Adding a New Product Section onCrmProductSectionAdd
Handling the Response
Error Handling
Scope:
crm
Who can subscribe: any user
The event
onCrmProductSectionAdd
is triggered after a section is added.
Handling the Response
Handling the Response
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
Error Handling
Error Handling
HTTP status:
400
In case of an error or if the section is created
not in the CRM information block
, it throws the exception
\Bitrix\Rest\RestException
.
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
On Updating a Section

---

## Event onCrmProductSectionUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/events/on-crm-product-section-update

Event onCrmProductSectionUpdate | Bitrix24 REST API and Marketplace Applications
Response Handling
Event onCrmProductSectionUpdate
Response Handling
Error Handling
Scope:
crm
Who can subscribe: any user
The event
onCrmProductSectionUpdate
is triggered after the section is modified.
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
Error Handling
Error Handling
HTTP status:
400
In case of an error or if the section is
not in the CRM information block
, it throws the exception
\Bitrix\Rest\RestException
.
Copied
Was the article helpful?
Yes
No
Previous
On Adding a Section
Next
On Deleting a Section

---

## Event onCrmProductSectionDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/outdated/product-section/events/on-crm-product-section-delete

Event onCrmProductSectionDelete | Bitrix24 REST API and Marketplace Applications
Response Handling
Event onCrmProductSectionDelete
Response Handling
Error Handling
Scope:
crm
Who can subscribe: any user
The event
onCrmProductSectionDelete
is triggered after a section is deleted.
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
Error Handling
Error Handling
HTTP status:
400
In case of an error or if the section is deleted
not in the CRM information block
, it throws the exception
\Bitrix\Rest\RestException
.
Copied
Was the article helpful?
Yes
No
Previous
On Updating a Section
Next
Overview of Methods

---

