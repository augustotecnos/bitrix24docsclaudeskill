---
description: 'CRM Universal Commerce: Payments, orders, product rows, delivery'
methods:
- crm.deal.list
- crm.invoice.list
- crm.item.delivery.get
- crm.item.delivery.list
- crm.item.payment.add
- crm.item.payment.delete
- crm.item.payment.delivery.add
- crm.item.payment.delivery.delete
- crm.item.payment.delivery.list
- crm.item.payment.delivery.setDelivery
- crm.item.payment.get
- crm.item.payment.list
- crm.item.payment.pay
- crm.item.payment.product.add
- crm.item.payment.product.delete
- crm.item.payment.product.list
- crm.item.payment.product.setQuantity
- crm.item.payment.unpay
- crm.item.payment.update
- crm.item.productrow.
- crm.item.productrow.add
- crm.item.productrow.delete
- crm.item.productrow.fields
- crm.item.productrow.get
- crm.item.productrow.getAvailableForPayment
- crm.item.productrow.list
- crm.item.productrow.set
- crm.item.productrow.update
- crm.orderentity.add
- crm.orderentity.deleteByFilter
pages: 36
title: 'CRM Universal Commerce: Payments, orders, product rows, delivery'
---
# CRM Universal Commerce: Payments, orders, product rows, delivery
> CRM Universal Commerce: Payments, orders, product rows, delivery
> **36 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Product Items](#product-items)
- [Add Product Row to CRM Object crm.item.productrow.add](#add-product-row-to-crm-object-crmitemproductrowadd)
- [Update the product row of a CRM object crm.item.productrow.update](#update-the-product-row-of-a-crm-object-crmitemprod)
- [Get information about a product item by id crm.item.productrow.get](#get-information-about-a-product-item-by-id-crmitem)
- [Save Product Row of CRM Object crm.item.productrow.set](#save-product-row-of-crm-object-crmitemproductrowse)
- [Get product rows of the CRM object crm.item.productrow.list](#get-product-rows-of-the-crm-object-crmitemproductr)
- [Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment](#get-unpaid-product-rows-of-crm-object-crmitemprodu)
- [Delete product row from CRM object crm.item.productrow.delete](#delete-product-row-from-crm-object-crmitemproductr)
- [Get the list of fields for product rows crm.item.productrow.fields](#get-the-list-of-fields-for-product-rows-crmitempro)
- [Linking an Order to Other CRM Objects](#linking-an-order-to-other-crm-objects)
- [Add Order Binding to CRM Object crm.orderentity.add](#add-order-binding-to-crm-object-crmorderentityadd)
- [Get a list of order bindings to CRM entities crm.orderentity.list](#get-a-list-of-order-bindings-to-crm-entities-crmor)
- [Remove Order Binding to CRM Object crm.orderentity.deleteByFilter](#remove-order-binding-to-crm-object-crmorderentityd)
- [Get Order Binding Fields crm.orderentity.getFields](#get-order-binding-fields-crmorderentitygetfields)
- [Overview of Methods](#overview-of-methods)
- [Add Payment crm.item.payment.add](#add-payment-crmitempaymentadd)
- [Update Payment Fields crm.item.payment.update](#update-payment-fields-crmitempaymentupdate)
- [Get Payment Information crm.item.payment.get](#get-payment-information-crmitempaymentget)
- [Get the list of payments crm.item.payment.list](#get-the-list-of-payments-crmitempaymentlist)
- [Delete Payment crm.item.payment.delete](#delete-payment-crmitempaymentdelete)
- [Change Payment Status to "Paid" crm.item.payment.pay](#change-payment-status-to-paid-crmitempaymentpay)
- [Change Payment Status to "Unpaid" crm.item.payment.unpay](#change-payment-status-to-unpaid-crmitempaymentunpa)
- [Generate a link for a specific payment salescenter.payment.getPublicUrl](#generate-a-link-for-a-specific-payment-salescenter)
- [Overview of Methods](#overview-of-methods)
- [Add Product Item to Payment crm.item.payment.product.add](#add-product-item-to-payment-crmitempaymentproducta)
- [Get a list of payment product items crm.item.payment.product.list](#get-a-list-of-payment-product-items-crmitempayment)
- [Remove product item from payment crm.item.payment.product.delete](#remove-product-item-from-payment-crmitempaymentpro)
- [Change Product Quantity crm.item.payment.product.setQuantity](#change-product-quantity-crmitempaymentproductsetqu)
- [Overview of Methods](#overview-of-methods)
- [Add Delivery Item to Payment crm.item.payment.delivery.add](#add-delivery-item-to-payment-crmitempaymentdeliver)
- [Get Delivery Item List by Specific Payment crm.item.payment.delivery.list](#get-delivery-item-list-by-specific-payment-crmitem)
- [Remove Delivery Item from Payment crm.item.payment.delivery.delete](#remove-delivery-item-from-payment-crmitempaymentde)
- [Reassign the delivery item to another document crm.item.payment.delivery.setDelivery](#reassign-the-delivery-item-to-another-document-crm)
- [Overview of Methods](#overview-of-methods)
- [Get Delivery Information by ID crm.item.delivery.get](#get-delivery-information-by-id-crmitemdeliveryget)
- [Get the list of deliveries for a CRM entity crm.item.delivery.list](#get-the-list-of-deliveries-for-a-crm-entity-crmite)

---

## Product Items

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/product-rows/index

Product Items | Bitrix24 REST API and Marketplace Applications
Description
Product Items
Description
Access Permissions
Automatic Actions After Any Change
Overview of Methods
Description
Description
The REST methods from the
crm.item.productrow.*
family allow you to work with product items linked to various CRM entities. These methods are universal and support any type of owner, except for old invoices:
leads
deals
contacts
companies
estimates
new invoices
SPAs
Access Permissions
Access Permissions
When calling REST methods, the access permissions of the user making the call are taken into account. Product items are not a standalone CRM entity and are always linked to some CRM object that acts as their owner. Therefore, during all operations, the user's permissions to access and manage the owner object (estimate, SPA, etc.) are checked. For example, if a user does not have read access to a particular entity, they will not be able to read its product items.
Automatic Actions After Any Change
Automatic Actions After Any Change
After any changes made to product items, all standard checks and procedures that occur when modifying a CRM object will be executed, including recalculating the total amount and triggering Automation rules after saving. This applies to all methods that create or modify product items:
crm.item.productrow.add
,
crm.item.productrow.update
,
crm.item.productrow.set
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can perform the methods: depending on the method
Method
Description
crm.item.productrow.add
Adds a product item
crm.item.productrow.update
Updates a product item
crm.item.productrow.get
Retrieves information about a product item by id
crm.item.productrow.set
Links a product item to a CRM object
crm.item.productrow.list
Retrieves a list of product items
crm.item.productrow.getAvailableForPayment
Retrieves a list of unpaid products
crm.item.productrow.delete
Deletes a product item
crm.item.productrow.fields
Retrieves a list of product item fields
Copied
Was the article helpful?
Yes
No
Previous
On Deleting a Custom CRM Type
Next
Add Product Item

---

## Add Product Row to CRM Object crm.item.productrow.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/product-rows/crm-item-productrow-add

Add Product Row to CRM Object crm.item.productrow.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Product Row to CRM Object crm.item.productrow.add
Method Parameters
Parameter fields
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the CRM object to which the product row is being added.
This method adds a product row to a CRM object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
Object containing field values for adding the product row to the CRM object
Parameter fields
Parameter fields
Name
type
Description
ownerId
*
integer
Identifier of the CRM object
ownerType
*
string
Identifier of the
CRM object type
. Pass the
Short symbolic code of the type
productId
catalog_product.id
Identifier of the product from the catalog
productName
string
Name of the product in the product row. If not provided, but
productId
is given, the product name from the product catalog is used
price
double
Price per unit of the product row, including discounts and taxes
quantity
double
Quantity of the product. Default is 1
discountTypeId
integer
Type of discount. Possible values:
1
— absolute value
2
— percentage value
Default is 2
discountRate
double
Discount value in percentage (if using the percentage discount type)
discountSum
double
Absolute discount value (if using the absolute discount type)
taxRate
double
Tax rate in percentage
taxIncluded
string
Indicator of whether the tax is included in the price. Possible values:
Y
– tax included
N
– tax not included
Default is N
measureCode
catalog_measure.code
Unit of measure code. If not provided and
productId
is given, the unit of measure from the product catalog is used
sort
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"ownerId":13142,"ownerType":"D","productId":9621,"price":80000,"quantity":2,"discountTypeId":2,"discountRate":20,"taxRate":20,"taxIncluded":"Y","measureCode":796,"sort":10}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.productrow.add
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"fields":{"ownerId":13142,"ownerType":"D","productId":9621,"price":80000,"quantity":2,"discountTypeId":2,"discountRate":20,"taxRate":20,"taxIncluded":"Y","measureCode":796,"sort":10},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.productrow.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.productrow.add'
, {
fields
: {
ownerId
:
13142
,
ownerType
:
'D'
,
productId
:
9621
,
price
:
80000.000000
,
quantity
:
2
,
discountTypeId
:
2
,
discountRate
:
20
,
taxRate
:
20
,
taxIncluded
:
'Y'
,
measureCode
:
796
,
sort
:
10
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.productrow.add'
,
[
'fields'
=> [
'ownerId'
=>
13142
,
'ownerType'
=>
'D'
,
'productId'
=>
9621
,
'price'
=>
80000.000000
,
'quantity'
=>
2
,
'discountTypeId'
=>
2
,
'discountRate'
=>
20
,
'taxRate'
=>
20
,
'taxIncluded'
=>
'Y'
,
'measureCode'
=>
796
,
'sort'
=>
10
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
'Error adding product row: '
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
'crm.item.productrow.add'
, {
fields
: {
ownerId
:
13142
,
ownerType
:
'D'
,
productId
:
9621
,
price
:
80000.000000
,
quantity
:
2
,
discountTypeId
:
2
,
discountRate
:
20
,
taxRate
:
20
,
taxIncluded
:
'Y'
,
measureCode
:
796
,
sort
:
10
,
},
},
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
log
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
'crm.item.productrow.add'
,
[
'fields'
=> [
'ownerId'
=>
13142
,
'ownerType'
=>
'D'
,
'productId'
=>
9621
,
'price'
=>
80000.000000
,
'quantity'
=>
2
,
'discountTypeId'
=>
2
,
'discountRate'
=>
20
,
'taxRate'
=>
20
,
'taxIncluded'
=>
'Y'
,
'measureCode'
=>
796
,
'sort'
=>
10
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
Successful Response
Successful Response
HTTP Status:
200
{
"result"
:
{
"productRow"
:
{
"id"
:
17647
,
"ownerId"
:
13142
,
"ownerType"
:
"D"
,
"productId"
:
9621
,
"price"
:
80000
,
"quantity"
:
2
,
"discountTypeId"
:
2
,
"discountRate"
:
20
,
"taxRate"
:
20
,
"taxIncluded"
:
"Y"
,
"measureCode"
:
796
,
"sort"
:
10
,
"type"
:
4
,
"productName"
:
"iphone 14"
,
"priceAccount"
:
80000
,
"priceExclusive"
:
66666.67
,
"priceNetto"
:
83333.34
,
"priceBrutto"
:
100000.01
,
"discountSum"
:
16666.67
,
"customized"
:
"Y"
,
"measureName"
:
"pcs"
,
"xmlId"
:
""
}
}
,
"time"
:
{
"start"
:
1716887721.77879
,
"finish"
:
1716887723.259695
,
"duration"
:
1.4809050559997559
,
"processing"
:
1.2986550331115723
,
"date_start"
:
"2024-05-28T12:15:21+02:00"
,
"date_finish"
:
"2024-05-28T12:15:23+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response
productRow
crm_item_product_row
Object containing information about the added product row
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
"OWNER_NOT_FOUND"
,
"error_description"
:
"Owner was not found"
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
ENTITY_TYPE_NOT_SUPPORTED
Working with this type of objects is not supported
ACCESS_DENIED
Access denied
OWNER_NOT_FOUND
The provided CRM object was not found
100
Required parameters were not provided
0
Other errors (e.g., fatal errors)
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
Product Items
Update the product row of a CRM object crm.item.productrow.update
Get the list of fields for product rows crm.item.productrow.fields
Get information about a product item by id crm.item.productrow.get
Save Product Row of CRM Object crm.item.productrow.set
Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment
Get product rows of the CRM object crm.item.productrow.list
Delete product row from CRM object crm.item.productrow.delete
Copied
Was the article helpful?
Yes
No
Previous
Product Items
Next
Update Product Item

---

## Update the product row of a CRM object crm.item.productrow.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/product-rows/crm-item-productrow-update

Update the product row of a CRM object crm.item.productrow.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update the product row of a CRM object crm.item.productrow.update
Method Parameters
Parameter fields
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the CRM object whose product row is being updated.
This method updates the product row of a CRM object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
crm_item_product_row.id
Identifier of the product row
fields
*
object
Object containing field values for updating the product row of the CRM object
Parameter fields
Parameter fields
Name
type
Description
productId
catalog_product.id
Identifier of the product from the catalog
productName
string
Name of the product in the product row
price
double
Price per unit of the product row, including discounts and taxes
quantity
double
Quantity of the product
discountTypeId
integer
Type of discount.
Possible values:
1
— absolute value
2
— percentage value
discountRate
double
Discount value in percentage (if using the percentage discount type)
discountSum
double
Absolute discount value (if using the absolute discount type)
taxRate
double
Tax rate in percentage
taxIncluded
string
Indicator of whether tax is included in the price.
Possible values:
Y
– tax included
N
– tax not included
measureCode
catalog_measure.code
Unit of measure code
sort
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":17648,"fields":{"productId":9621,"price":90000,"quantity":3,"discountTypeId":2,"discountRate":10,"taxRate":10,"taxIncluded":"Y","measureCode":796,"sort":20}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.productrow.update
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":17648,"fields":{"productId":9621,"price":90000,"quantity":3,"discountTypeId":2,"discountRate":10,"taxRate":10,"taxIncluded":"Y","measureCode":796,"sort":20},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.productrow.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.productrow.update'
, {
id
:
17648
,
fields
: {
productId
:
9621
,
price
:
90000.000000
,
quantity
:
3
,
discountTypeId
:
2
,
discountRate
:
10
,
taxRate
:
10
,
taxIncluded
:
'Y'
,
measureCode
:
796
,
sort
:
20
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.productrow.update'
,
[
'id'
=>
17648
,
'fields'
=> [
'productId'
=>
9621
,
'price'
=>
90000.000000
,
'quantity'
=>
3
,
'discountTypeId'
=>
2
,
'discountRate'
=>
10
,
'taxRate'
=>
10
,
'taxIncluded'
=>
'Y'
,
'measureCode'
=>
796
,
'sort'
=>
20
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
'Error updating product row: '
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
'crm.item.productrow.update'
, {
id
:
17648
,
fields
: {
productId
:
9621
,
price
:
90000.000000
,
quantity
:
3
,
discountTypeId
:
2
,
discountRate
:
10
,
taxRate
:
10
,
taxIncluded
:
'Y'
,
measureCode
:
796
,
sort
:
20
,
},
},
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
log
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
'crm.item.productrow.update'
,
[
'id'
=>
17648
,
'fields'
=> [
'productId'
=>
9621
,
'price'
=>
90000.000000
,
'quantity'
=>
3
,
'discountTypeId'
=>
2
,
'discountRate'
=>
10
,
'taxRate'
=>
10
,
'taxIncluded'
=>
'Y'
,
'measureCode'
=>
796
,
'sort'
=>
20
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
Successful Response
Successful Response
HTTP status:
200
{
"result"
:
{
"productRow"
:
{
"id"
:
17649
,
"ownerId"
:
13142
,
"ownerType"
:
"D"
,
"productId"
:
9621
,
"productName"
:
"iphone 14"
,
"price"
:
90000
,
"priceAccount"
:
90000
,
"priceExclusive"
:
81818.18
,
"priceNetto"
:
90909.09
,
"priceBrutto"
:
100000
,
"quantity"
:
3
,
"discountTypeId"
:
2
,
"discountRate"
:
10
,
"discountSum"
:
9090.91
,
"taxRate"
:
10
,
"taxIncluded"
:
"Y"
,
"customized"
:
"Y"
,
"measureCode"
:
796
,
"measureName"
:
"pcs"
,
"sort"
:
20
,
"xmlId"
:
"sale_basket_8147"
,
"type"
:
4
}
}
,
"time"
:
{
"start"
:
1716890008.714214
,
"finish"
:
1716890010.275307
,
"duration"
:
1.5610928535461426
,
"processing"
:
1.3967258930206299
,
"date_start"
:
"2024-05-28T12:53:28+02:00"
,
"date_finish"
:
"2024-05-28T12:53:30+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response
productRow
crm_item_product_row
Object containing information about the updated product row
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
"NOT_FOUND"
,
"error_description"
:
"Element not found"
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
ENTITY_TYPE_NOT_SUPPORTED
Working with this type of object is not supported
ACCESS_DENIED
Access denied
NOT_FOUND
Product row not found
INVALID_ARG_VALUE
Unknown field or the provided field is not available for update
100
Required parameters not provided
0
Other errors (e.g., fatal errors)
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
Product Items
Add Product Row to CRM Object crm.item.productrow.add
Get the list of fields for product rows crm.item.productrow.fields
Get information about a product item by id crm.item.productrow.get
Save Product Row of CRM Object crm.item.productrow.set
Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment
Get product rows of the CRM object crm.item.productrow.list
Delete product row from CRM object crm.item.productrow.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Product Item
Next
Get Product Item Information by ID

---

## Get information about a product item by id crm.item.productrow.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/product-rows/crm-item-productrow-get

Get information about a product item by id crm.item.productrow.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get information about a product item by id crm.item.productrow.get
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires read access permission for the object to which the product items are linked
This method retrieves information about a product item in the CRM.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
crm_item_product_row.id
Identifier of the product item
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
-d '{"id":17622}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.productrow.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":17622,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.productrow.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.productrow.get'
, {
id
:
17622
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.productrow.get'
,
[
'id'
=>
17622
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
'Error getting product row: '
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
'crm.item.productrow.get'
, {
id
:
17622
,
},
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
log
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
'crm.item.productrow.get'
,
[
'id'
=>
17622
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
{
"productRow"
:
{
"id"
:
17622
,
"ownerId"
:
13141
,
"ownerType"
:
"D"
,
"productId"
:
9621
,
"productName"
:
"iphone 14"
,
"price"
:
79999
,
"priceAccount"
:
79999
,
"priceExclusive"
:
79999
,
"priceNetto"
:
79999
,
"priceBrutto"
:
79999
,
"quantity"
:
11
,
"discountTypeId"
:
2
,
"discountRate"
:
0
,
"discountSum"
:
0
,
"taxRate"
:
null
,
"taxIncluded"
:
"Y"
,
"customized"
:
"Y"
,
"measureCode"
:
796
,
"measureName"
:
"pcs"
,
"sort"
:
10
,
"xmlId"
:
"sale_basket_8145"
,
"type"
:
4
,
"storeId"
:
19
}
}
,
"time"
:
{
"start"
:
1716821358.26828
,
"finish"
:
1716821358.701454
,
"duration"
:
0.43317389488220215
,
"processing"
:
0.240645170211792
,
"date_start"
:
"2024-05-27T17:49:18+02:00"
,
"date_finish"
:
"2024-05-27T17:49:18+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response
productRow
crm_item_product_row
Object containing information about the product item
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
"NOT_FOUND"
,
"error_description"
:
"Element not found"
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
ENTITY_TYPE_NOT_SUPPORTED
Working with this type of objects is not supported
ACCESS_DENIED
Access denied
NOT_FOUND
Product item not found
100
Required parameters not provided
0
Other errors (e.g., fatal errors)
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
Product Items
Add Product Row to CRM Object crm.item.productrow.add
Update the product row of a CRM object crm.item.productrow.update
Get the list of fields for product rows crm.item.productrow.fields
Save Product Row of CRM Object crm.item.productrow.set
Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment
Get product rows of the CRM object crm.item.productrow.list
Delete product row from CRM object crm.item.productrow.delete
Copied
Was the article helpful?
Yes
No
Previous
Update Product Item
Next
Link Product Item to CRM Object

---

## Save Product Row of CRM Object crm.item.productrow.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/product-rows/crm-item-productrow-set

Save Product Row of CRM Object crm.item.productrow.set | Bitrix24 REST API and Marketplace Applications
Method Parameters
Save Product Row of CRM Object crm.item.productrow.set
Method Parameters
Parameter productRows
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the CRM object for which the product row is being set.
This method saves the product row of a CRM object. Please note that this method will overwrite all existing product rows associated with the object. Thus, it replaces the existing product rows with those that were sent.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ownerId
*
integer
Identifier of the CRM object
ownerType
*
string
Identifier of the
CRM object type
. Pass the
Short symbolic code of the type
productRows
*
object[]
Array of objects containing information about the product rows to be saved in the object
Parameter productRows
Parameter productRows
Name
type
Description
productId
catalog_product.id
Identifier of the product from the catalog
productName
string
Name of the product in the product row.
If not provided and
productId
is given, the product name from the product catalog will be used
price
double
Price per unit of the product row, including discounts and taxes
quantity
double
Quantity of the product.
Default is 1
discountTypeId
integer
Type of discount.
Possible values:
1
— absolute value
2
— percentage value
Default is 2
discountRate
double
Discount value in percentage (if using the percentage discount type)
discountSum
double
Absolute discount value (if using the absolute discount type)
taxRate
double
Tax rate in percentage
taxIncluded
string
Indicator of whether tax is included in the price.
Possible values:
Y
– tax included
N
– tax not included
Default is N
measureCode
catalog_measure.code
Unit of measure code.
If not provided and
productId
is given, the unit of measure from the product catalog will be used
sort
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"ownerType":"D","ownerId":13143,"productRows":[{"productId":9621,"price":99999.99,"quantity":1,"sort":10},{"productId":9623,"price":15900,"quantity":2,"sort":10}]}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.productrow.set
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"ownerType":"D","ownerId":13143,"productRows":[{"productId":9621,"price":99999.99,"quantity":1,"sort":10},{"productId":9623,"price":15900,"quantity":2,"sort":10}],"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.productrow.set
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.productrow.set'
, {
ownerType
:
'D'
,
ownerId
:
13143
,
productRows
: [{
productId
:
9621
,
price
:
99999.99
,
quantity
:
1
,
sort
:
10
,
},
{
productId
:
9623
,
price
:
15900
,
quantity
:
2
,
sort
:
10
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.productrow.set'
,
[
'ownerType'
=>
'D'
,
'ownerId'
=>
13143
,
'productRows'
=> [
[
'productId'
=>
9621
,
'price'
=>
99999.99
,
'quantity'
=>
1
,
'sort'
=>
10
,
],
[
'productId'
=>
9623
,
'price'
=>
15900.00
,
'quantity'
=>
2
,
'sort'
=>
10
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
'Error setting product rows: '
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
'crm.item.productrow.set'
, {
ownerType
:
'D'
,
ownerId
:
13143
,
productRows
: [{
productId
:
9621
,
price
:
99999.99
,
quantity
:
1
,
sort
:
10
,
},
{
productId
:
9623
,
price
:
15900.00
,
quantity
:
2
,
sort
:
10
,
},
],
},
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
log
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
'crm.item.productrow.set'
,
[
'ownerType'
=>
'D'
,
'ownerId'
=>
13143
,
'productRows'
=> [
[
'productId'
=>
9621
,
'price'
=>
99999.99
,
'quantity'
=>
1
,
'sort'
=>
10
,
],
[
'productId'
=>
9623
,
'price'
=>
15900.00
,
'quantity'
=>
2
,
'sort'
=>
10
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
Successful Response
Successful Response
HTTP Status:
200
{
"result"
:
{
"productRows"
:
[
{
"id"
:
17654
,
"ownerId"
:
13143
,
"ownerType"
:
"D"
,
"productId"
:
9621
,
"productName"
:
"iphone 14"
,
"price"
:
99999.99
,
"priceAccount"
:
99999.99
,
"priceExclusive"
:
99999.99
,
"priceNetto"
:
99999.99
,
"priceBrutto"
:
99999.99
,
"quantity"
:
1
,
"discountTypeId"
:
2
,
"discountRate"
:
0
,
"discountSum"
:
0
,
"taxRate"
:
null
,
"taxIncluded"
:
"N"
,
"customized"
:
"Y"
,
"measureCode"
:
796
,
"measureName"
:
"pcs"
,
"sort"
:
10
,
"xmlId"
:
""
,
"type"
:
4
}
,
{
"id"
:
17655
,
"ownerId"
:
13143
,
"ownerType"
:
"D"
,
"productId"
:
9623
,
"productName"
:
"iphone 10xs"
,
"price"
:
15900
,
"priceAccount"
:
15900
,
"priceExclusive"
:
15900
,
"priceNetto"
:
15900
,
"priceBrutto"
:
15900
,
"quantity"
:
2
,
"discountTypeId"
:
2
,
"discountRate"
:
0
,
"discountSum"
:
0
,
"taxRate"
:
null
,
"taxIncluded"
:
"N"
,
"customized"
:
"Y"
,
"measureCode"
:
796
,
"measureName"
:
"pcs"
,
"sort"
:
10
,
"xmlId"
:
""
,
"type"
:
4
}
]
}
,
"time"
:
{
"start"
:
1716895718.887229
,
"finish"
:
1716895719.316293
,
"duration"
:
0.4290640354156494
,
"processing"
:
0.20114707946777344
,
"date_start"
:
"2024-05-28T14:28:38+02:00"
,
"date_finish"
:
"2024-05-28T14:28:39+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response
productRow
crm_item_product_row[]
Array of objects containing information about all product rows of the CRM object
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
"OWNER_NOT_FOUND"
,
"error_description"
:
"Owner was not found"
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
ENTITY_TYPE_NOT_SUPPORTED
Working with this type of objects is not supported
ACCESS_DENIED
Access denied
OWNER_NOT_FOUND
The provided CRM object was not found
100
Required parameters were not provided
0
Other errors (e.g., fatal errors)
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
Product Items
Add Product Row to CRM Object crm.item.productrow.add
Get the list of fields for product rows crm.item.productrow.fields
Get information about a product item by id crm.item.productrow.get
Update the product row of a CRM object crm.item.productrow.update
Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment
Get product rows of the CRM object crm.item.productrow.list
Delete product row from CRM object crm.item.productrow.delete
Copied
Was the article helpful?
Yes
No
Previous
Get Product Item Information by ID
Next
Get List of Product Items

---

## Get product rows of the CRM object crm.item.productrow.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/product-rows/crm-item-productrow-list

Get product rows of the CRM object crm.item.productrow.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get product rows of the CRM object crm.item.productrow.list
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires read access permission for the CRM object whose product rows are being selected.
The method retrieves product rows of the CRM object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
filter
*
object
Object for filtering selected records in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
correspond to the fields of the
crm_item_product_row
object.
The following keys must be present:
=ownerType
=ownerId
In
=ownerType
, pass the
Short symbolic code of the type
.
The key may have an additional prefix that specifies the behavior of the filter. Possible prefix values:
=
— equals (works with arrays as well)
%
— LIKE, substring search. The % symbol in the filter value does not need to be passed. The search looks for the substring in any position of the string.
>
— greater than
<
— less than
!=
— not equal
!%
— NOT LIKE, substring search. The % symbol in the filter value does not need to be passed. The search goes from both sides.
>=
— greater than or equal to
<=
— less than or equal to
=%
— LIKE, substring search. The % symbol needs to be passed in the value. Examples:
"mol%"
— searching for values starting with "mol"
"%mol"
— searching for values ending with "mol"
"%mol%"
— searching for values where "mol" can be in any position
%=
— LIKE (see description above)
!=%
— NOT LIKE, substring search. The % symbol needs to be passed in the value. Examples:
"mol%"
— searching for values not starting with "mol"
"%mol"
— searching for values not ending with "mol"
"%mol%"
— searching for values where the substring "mol" is not present in any position
!%=
— NOT LIKE (see description above)
order
object
Object for sorting selected elements of the shipment table in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
correspond to the fields of the
crm_item_product_row
object.
Possible values for
order
:
asc
— in ascending order
desc
— in descending order
start
integer
Parameter used for managing pagination.
The page size of results is always static: 50 records.
To select the second page of results, you need to pass the value
50
. To select the third page of results, the value is
100
, and so on.
The formula for calculating the value of the
start
parameter:
start = (N-1) * 50
, where
N
— the number of the desired page
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
-d '{"filter":{"=ownerType":"D","=ownerId":13142,">price":5000},"order":{"price":"desc"}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.productrow.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"filter":{"=ownerType":"D","=ownerId":13142,">price":5000},"order":{"price":"desc"},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.productrow.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.item.productrow.list'
,
{
filter
: {
"=ownerType"
:
'D'
,
"=ownerId"
:
13142
,
">price"
:
5000
,
},
order
: {
price
:
"desc"
},
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
'crm.item.productrow.list'
, {
filter
: {
"=ownerType"
:
'D'
,
"=ownerId"
:
13142
,
">price"
:
5000
,
},
order
: {
price
:
"desc"
},
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
'crm.item.productrow.list'
, {
filter
: {
"=ownerType"
:
'D'
,
"=ownerId"
:
13142
,
">price"
:
5000
,
},
order
: {
price
:
"desc"
},
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
'crm.item.productrow.list'
,
[
'filter'
=> [
"=ownerType"
=>
'D'
,
"=ownerId"
=>
13142
,
">price"
=>
5000
,
],
'order'
=> [
'price'
=>
"desc"
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
'Error listing product rows: '
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
'crm.item.productrow.list'
, {
filter
: {
"=ownerType"
:
'D'
,
"=ownerId"
:
13142
,
">price"
:
5000
,
},
order
: {
price
:
"desc"
},
},
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
log
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
'crm.item.productrow.list'
,
[
'filter'
=> [
"=ownerType"
=>
'D'
,
"=ownerId"
=>
13142
,
">price"
=>
5000
,
],
'order'
=> [
'price'
=>
"desc"
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
{
"result"
:
{
"productRows"
:
[
{
"id"
:
17649
,
"ownerId"
:
13142
,
"ownerType"
:
"D"
,
"productId"
:
9621
,
"productName"
:
"iphone 14"
,
"price"
:
90000
,
"priceAccount"
:
90000
,
"priceExclusive"
:
81818.18
,
"priceNetto"
:
90909.09
,
"priceBrutto"
:
100000
,
"quantity"
:
3
,
"discountTypeId"
:
2
,
"discountRate"
:
10
,
"discountSum"
:
9090.91
,
"taxRate"
:
10
,
"taxIncluded"
:
"Y"
,
"customized"
:
"Y"
,
"measureCode"
:
796
,
"measureName"
:
"pcs"
,
"sort"
:
20
,
"xmlId"
:
"sale_basket_8147"
,
"type"
:
4
,
"storeId"
:
19
}
,
{
"id"
:
17650
,
"ownerId"
:
13142
,
"ownerType"
:
"D"
,
"productId"
:
9623
,
"productName"
:
"iphone 10xs"
,
"price"
:
5550
,
"priceAccount"
:
5550
,
"priceExclusive"
:
5550
,
"priceNetto"
:
5550
,
"priceBrutto"
:
5550
,
"quantity"
:
1
,
"discountTypeId"
:
2
,
"discountRate"
:
0
,
"discountSum"
:
0
,
"taxRate"
:
null
,
"taxIncluded"
:
"Y"
,
"customized"
:
"Y"
,
"measureCode"
:
6
,
"measureName"
:
"m"
,
"sort"
:
10
,
"xmlId"
:
"sale_basket_8148"
,
"type"
:
4
,
"storeId"
:
17
}
]
}
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
1716905609.186602
,
"finish"
:
1716905609.434087
,
"duration"
:
0.24748492240905762
,
"processing"
:
0.06894516944885254
,
"date_start"
:
"2024-05-28T17:13:29+02:00"
,
"date_finish"
:
"2024-05-28T17:13:29+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response
productRows
crm_item_product_row[]
Array of objects containing information about the selected product rows of the CRM object
total
integer
Total number of records found
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
"ACCESS_DENIED"
,
"error_description"
:
"Access denied"
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
ACCESS_DENIED
Access denied
INVALID_ARG_VALUE
Invalid values for input parameters
100
Required parameters not provided
0
Other errors (e.g., fatal errors)
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
Product Items
Add Product Row to CRM Object crm.item.productrow.add
Get the list of fields for product rows crm.item.productrow.fields
Get information about a product item by id crm.item.productrow.get
Save Product Row of CRM Object crm.item.productrow.set
Update the product row of a CRM object crm.item.productrow.update
Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment
Delete product row from CRM object crm.item.productrow.delete
Copied
Was the article helpful?
Yes
No
Previous
Link Product Item to CRM Object
Next
Get List of Unpaid Products

---

## Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/product-rows/crm-item-productrow-get-available-for-payment

Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires read access permission for the CRM object whose product rows are being selected.
The method retrieves product rows of the CRM object for which the client has not yet been billed.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ownerId
*
integer
Identifier of the CRM object
ownerType
*
string
Identifier of the
CRM object type
. Pass the
Short symbolic code of the type
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
-d '{"ownerType":"D","ownerId":13144}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.productrow.getAvailableForPayment
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"ownerType":"D","ownerId":13144,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.productrow.getAvailableForPayment
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.productrow.getAvailableForPayment'
, {
ownerType
:
'D'
,
ownerId
:
13144
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.productrow.getAvailableForPayment'
,
[
'ownerType'
=>
'D'
,
'ownerId'
=>
13144
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
'Error getting available product rows for payment: '
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
'crm.item.productrow.getAvailableForPayment'
, {
ownerType
:
'D'
,
ownerId
:
13144
,
},
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
log
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
'crm.item.productrow.getAvailableForPayment'
,
[
'ownerType'
=>
'D'
,
'ownerId'
=>
13144
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
"productRows"
:
[
{
"id"
:
17657
,
"ownerId"
:
13144
,
"ownerType"
:
"D"
,
"productId"
:
9621
,
"productName"
:
"iphone 14"
,
"price"
:
79999
,
"priceAccount"
:
79999
,
"priceExclusive"
:
79999
,
"priceNetto"
:
79999
,
"priceBrutto"
:
79999
,
"quantity"
:
3
,
"discountTypeId"
:
2
,
"discountRate"
:
0
,
"discountSum"
:
0
,
"taxRate"
:
null
,
"taxIncluded"
:
"Y"
,
"customized"
:
"Y"
,
"measureCode"
:
796
,
"measureName"
:
"pcs"
,
"sort"
:
10
,
"xmlId"
:
"sale_basket_8149"
,
"type"
:
4
}
,
{
"id"
:
17658
,
"ownerId"
:
13144
,
"ownerType"
:
"D"
,
"productId"
:
9623
,
"productName"
:
"iphone 10xs"
,
"price"
:
5550
,
"priceAccount"
:
5550
,
"priceExclusive"
:
5550
,
"priceNetto"
:
5550
,
"priceBrutto"
:
5550
,
"quantity"
:
3
,
"discountTypeId"
:
2
,
"discountRate"
:
0
,
"discountSum"
:
0
,
"taxRate"
:
null
,
"taxIncluded"
:
"Y"
,
"customized"
:
"Y"
,
"measureCode"
:
796
,
"measureName"
:
"pcs"
,
"sort"
:
20
,
"xmlId"
:
"sale_basket_8150"
,
"type"
:
4
}
]
}
,
"time"
:
{
"start"
:
1716966560.3205
,
"finish"
:
1716966560.742781
,
"duration"
:
0.42228102684020996
,
"processing"
:
0.17676782608032227
,
"date_start"
:
"2024-05-29T10:09:20+02:00"
,
"date_finish"
:
"2024-05-29T10:09:20+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response
productRows
crm_item_product_row[]
Array of objects containing information about all product rows of the CRM object for which the client has not yet been billed
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
"ACCESS_DENIED"
,
"error_description"
:
"Access denied"
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
ACCESS_DENIED
Access denied
100
Required parameters not provided
0
Other errors (e.g., fatal errors)
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
Product Items
Add Product Row to CRM Object crm.item.productrow.add
Get the list of fields for product rows crm.item.productrow.fields
Get information about a product item by id crm.item.productrow.get
Save Product Row of CRM Object crm.item.productrow.set
Update the product row of a CRM object crm.item.productrow.update
Get product rows of the CRM object crm.item.productrow.list
Delete product row from CRM object crm.item.productrow.delete
Copied
Was the article helpful?
Yes
No
Previous
Get List of Product Items
Next
Delete Product Item

---

## Delete product row from CRM object crm.item.productrow.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/product-rows/crm-item-productrow-delete

Delete product row from CRM object crm.item.productrow.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete product row from CRM object crm.item.productrow.delete
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: access permission to modify the CRM object from which the product row is being deleted is required.
This method removes a product row from the CRM object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
crm_item_product_row.id
Identifier of the product row
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
-d '{"id":17655}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.productrow.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":17655,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.productrow.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.productrow.delete'
, {
id
:
17655
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.productrow.delete'
,
[
'id'
=>
17655
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
'Error deleting product row: '
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
'crm.item.productrow.delete'
, {
id
:
17655
,
},
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
log
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
'crm.item.productrow.delete'
,
[
'id'
=>
17655
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
null
,
"time"
:
{
"start"
:
1716898012.405785
,
"finish"
:
1716898013.536588
,
"duration"
:
1.130802869796753
,
"processing"
:
0.9562788009643555
,
"date_start"
:
"2024-05-28T15:06:52+03:00"
,
"date_finish"
:
"2024-05-28T15:06:53+03:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
any
Result of the operation. The value is always null
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
"NOT_FOUND"
,
"error_description"
:
"Element not found"
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
ENTITY_TYPE_NOT_SUPPORTED
Working with this type of objects is not supported
ACCESS_DENIED
Access denied
NOT_FOUND
Product row not found
100
Required parameters not provided
0
Other errors (e.g., fatal errors)
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
Product Items
Add Product Row to CRM Object crm.item.productrow.add
Get the list of fields for product rows crm.item.productrow.fields
Get information about a product item by id crm.item.productrow.get
Save Product Row of CRM Object crm.item.productrow.set
Update the product row of a CRM object crm.item.productrow.update
Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment
Get product rows of the CRM object crm.item.productrow.list
Copied
Was the article helpful?
Yes
No
Previous
Get List of Unpaid Products
Next
Get List of Product Item Fields

---

## Get the list of fields for product rows crm.item.productrow.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/product-rows/crm-item-productrow-fields

Get the list of fields for product rows crm.item.productrow.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get the list of fields for product rows crm.item.productrow.fields
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method retrieves the list of fields for product rows.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.productrow.fields
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/crm.item.productrow.fields?auth=**put_access_token_here**
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.productrow.fields'
, {}
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.productrow.fields'
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
'crm.item.productrow.fields'
, {},
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
log
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
'crm.item.productrow.fields'
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
HTTP status:
200
{
"result"
:
{
"fields"
:
{
"id"
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
"ownerId"
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
"Owner ID"
}
,
"ownerType"
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
"Owner Type"
}
,
"productId"
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
"Product"
}
,
"productName"
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
"Product Name"
}
,
"price"
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
"Price"
}
,
"priceExclusive"
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
"Price excluding tax with discount"
}
,
"priceNetto"
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
"PRICE_NETTO"
}
,
"priceBrutto"
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
"PRICE_BRUTTO"
}
,
"quantity"
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
"Quantity"
}
,
"discountTypeId"
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
"Discount Type"
}
,
"discountRate"
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
"Discount Rate"
}
,
"discountSum"
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
"Discount Sum"
}
,
"taxRate"
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
"Tax"
}
,
"taxIncluded"
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
"Tax included in price"
}
,
"customized"
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
"Customized"
}
,
"measureCode"
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
"Measure Code"
}
,
"measureName"
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
"Measure Name"
}
,
"sort"
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
"Sort"
}
,
"type"
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
"TYPE"
}
,
"storeId"
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
"STORE_ID"
}
}
}
,
"time"
:
{
"start"
:
1716812240.400023
,
"finish"
:
1716812242.151703
,
"duration"
:
1.7516798973083496
,
"processing"
:
0.09682416915893555
,
"date_start"
:
"2024-05-27T15:17:20+02:00"
,
"date_finish"
:
"2024-05-27T15:17:22+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response
fields
object
Object in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field
is the identifier of the
crm_item_product_row
object, and
value
is an object of type
crm_rest_field_description
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
0
,
"error_description"
:
"some error"
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
0
Other errors (e.g., fatal errors)
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
Product Items
Add Product Row to CRM Object crm.item.productrow.add
Update the product row of a CRM object crm.item.productrow.update
Get information about a product item by id crm.item.productrow.get
Save Product Row of CRM Object crm.item.productrow.set
Get Unpaid Product Rows of CRM Object crm.item.productrow.getAvailableForPayment
Get product rows of the CRM object crm.item.productrow.list
Delete product row from CRM object crm.item.productrow.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete Product Item
Next
Custom Fields in CRM

---

## Linking an Order to Other CRM Objects

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/order-entity/index

Linking an Order to Other CRM Objects | Bitrix24 REST API and Marketplace Applications
Linking an Order to Other CRM Objects
Linking an Order to Other CRM Objects
Scope:
crm
Who can execute the method: depending on the method
Method
Description
crm.orderentity.add
Adds a link between an order and a CRM object
crm.orderentity.list
Returns a list of order links to CRM objects
crm.orderentity.deleteByFilter
Deletes a link between an order and a CRM object
crm.orderentity.getFields
Returns a list of available fields for the order link
Copied
Was the article helpful?
Yes
No
Previous
Import a group of records
Next
Add Order Link to CRM Entity

---

## Add Order Binding to CRM Object crm.orderentity.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/order-entity/crm-order-entity-add

Add Order Binding to CRM Object crm.orderentity.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Order Binding to CRM Object crm.orderentity.add
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
Who can execute the method: online store administrator
This method adds a binding of an order to a CRM object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
Field values for creating the binding
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
orderId
*
sale_order.id
Order identifier
ownerTypeId
*
integer
Identifier of the
CRM object type
.
Binding is only possible to a deal or invoice
ownerId
*
integer
Identifier of the CRM object.
For deals, it can be obtained using the
crm.deal.list
method.
For invoices, it can be obtained using the
crm.invoice.list
Code Examples
Code Examples
How to Use Examples in Documentation
Add order binding to a deal:
cURL (Webhook)
cURL (OAuth)
JS
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
'{"fields":{"orderId":5125,"ownerId":6933,"ownerTypeId":2}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.orderentity.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"orderId":5125,"ownerId":6933,"ownerTypeId":2},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.orderentity.add
try
{
const
response =
await
$b24.
callMethod
(
"crm.orderentity.add"
,
{
fields
: {
orderId
:
5125
,
ownerId
:
6933
,
ownerTypeId
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
BX24
.
callMethod
(
"crm.orderentity.add"
,
{
fields
: {
orderId
:
5125
,
ownerId
:
6933
,
ownerTypeId
:
2
}
},
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.orderentity.add'
,
[
'fields'
=> [
'orderId'
=>
5125
,
'ownerId'
=>
6933
,
'ownerTypeId'
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
{
"dealOrder"
:
{
"orderId"
:
5125
,
"ownerId"
:
6933
,
"ownerTypeId"
:
2
}
}
,
"time"
:
{
"start"
:
1719325851.568441
,
"finish"
:
1719325852.546479
,
"duration"
:
0.9780380725860596
,
"processing"
:
0.32780981063842773
,
"date_start"
:
"2024-06-25T16:30:51+02:00"
,
"date_finish"
:
"2024-06-25T16:30:52+02:00"
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
Root element of the response
dealOrder
crm_orderentity
Object with information about the created binding
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
"201650000001"
,
"error_description"
:
"Duplicate entry for key [ownerId, ownerTypeId, orderId]"
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
Description
200040300020
Access Denied
Insufficient access permissions
201650000001
Duplicate entry for key [ownerId, ownerTypeId, orderId]
Binding already exists
200540400001
order does not exist
Order not found
0
Required fields: #FIELDS#
Required fields not specified (
#FIELDS#
— list of fields separated by commas)
0
Various order saving errors
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
Get a list of order bindings to CRM entities crm.orderentity.list
Remove Order Binding to CRM Object crm.orderentity.deleteByFilter
Get Order Binding Fields crm.orderentity.getFields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Retrieve List of Order Links to CRM Entities

---

## Get a list of order bindings to CRM entities crm.orderentity.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/order-entity/crm-order-entity-list

Get a list of order bindings to CRM entities crm.orderentity.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of order bindings to CRM entities crm.orderentity.list
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
Who can execute the method: online store manager
The method returns a list of order bindings to CRM entities.
Method Parameters
Method Parameters
Name
type
Description
select
array
An array of fields to select (see fields of the
crm_orderentity
object).
If the array is not provided or an empty array is passed, all available fields of the order binding to the CRM entity will be selected.
filter
object
An object for filtering selected records in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field_N
correspond to the fields of the
crm_orderentity
object.
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
character should not be passed in the filter value. The search looks for the substring in any position of the string
=%
— LIKE, substring search. The
%
character must be passed in the value. Examples:
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
character should not be passed in the filter value. The search goes from both sides
!=%
— NOT LIKE, substring search. The
%
character must be passed in the value. Examples:
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
An object for sorting records in the format
{"field_1": "order_1", ... "field_N": "order_N"}
, where
field_N
is the identifier of the
crm_orderentity
field.
Possible values for
order_N
:
asc
— in ascending order
desc
— in descending order
If the object is not provided or an empty object is passed, sorting will be in ascending order of the
crm_orderentity.OWNER_ID
field.
start
integer
This parameter is used for pagination control.
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
is the desired page number.
If you specify the value
-1
, all records that meet the filter conditions will be selected.
Code Examples
Code Examples
How to Use Examples in Documentation
Get the IDs of orders linked to three deals:
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
'{"select":["orderId","ownerId"],"filter":{"=ownerTypeId":2,"@ownerId":[6938,6937,6933]},"order":{"orderId":"asc"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.orderentity.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"select":["orderId","ownerId"],"filter":{"=ownerTypeId":2,"@ownerId":[6938,6937,6933]},"order":{"orderId":"asc"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.orderentity.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.orderentity.list'
,
{
select
: [
'orderId'
,
'ownerId'
,
],
filter
: {
'=ownerTypeId'
:
2
,
'@ownerId'
: [
6938
,
6937
,
6933
],
},
order
: {
orderId
:
'asc'
},
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.orderentity.list'
, {
select
: [
'orderId'
,
'ownerId'
,
],
filter
: {
'=ownerTypeId'
:
2
,
'@ownerId'
: [
6938
,
6937
,
6933
],
},
order
: {
orderId
:
'asc'
},
},
'orderId'
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
'crm.orderentity.list'
, {
select
: [
'orderId'
,
'ownerId'
,
],
filter
: {
'=ownerTypeId'
:
2
,
'@ownerId'
: [
6938
,
6937
,
6933
],
},
order
: {
orderId
:
'asc'
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
'crm.orderentity.list'
,
[
'select'
=> [
'orderId'
,
'ownerId'
,
],
'filter'
=> [
'=ownerTypeId'
=>
2
,
'@ownerId'
=> [
6938
,
6937
,
6933
],
],
'order'
=> [
'orderId'
=>
'asc'
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
'Error fetching order entities: '
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
"crm.orderentity.list"
,
{
select
: [
'orderId'
,
'ownerId'
,
],
filter
: {
'=ownerTypeId'
:
2
,
'@ownerId'
: [
6938
,
6937
,
6933
],
},
order
: {
orderId
:
'asc'
},
},)
.
then
(
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
log
(result.
data
);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.orderentity.list'
,
[
'select'
=> [
'orderId'
,
'ownerId'
,
],
'filter'
=> [
'=ownerTypeId'
=>
2
,
'@ownerId'
=> [
6938
,
6937
,
6933
],
],
'order'
=> [
'orderId'
=>
'asc'
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
"orderEntity"
:
[
{
"orderId"
:
5125
,
"ownerId"
:
6933
}
,
{
"orderId"
:
5127
,
"ownerId"
:
6937
}
,
{
"orderId"
:
5128
,
"ownerId"
:
6938
}
]
}
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
1719315806.858516
,
"finish"
:
1719315807.569731
,
"duration"
:
0.7112150192260742
,
"processing"
:
0.039324045181274414
,
"date_start"
:
"2024-06-25T13:43:26+02:00"
,
"date_finish"
:
"2024-06-25T13:43:27+02:00"
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
The root element of the response
orderEntity
crm_orderentity[]
An array of objects with information about the selected orders
total
integer
The total number of selected records
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
"200040300010"
,
"error_description"
:
"Access Denied"
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
Description
200040300010
Access Denied
Insufficient access permissions
200540400002
module sale does not exist
The
Online Store
(sale) module is missing
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
Add Order Binding to CRM Object crm.orderentity.add
Remove Order Binding to CRM Object crm.orderentity.deleteByFilter
Get Order Binding Fields crm.orderentity.getFields
Copied
Was the article helpful?
Yes
No
Previous
Add Order Link to CRM Entity
Next
Remove Order Link from CRM Entity

---

## Remove Order Binding to CRM Object crm.orderentity.deleteByFilter

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/order-entity/crm-order-entity-delete-by-filter

Remove Order Binding to CRM Object crm.orderentity.deleteByFilter | Bitrix24 REST API and Marketplace Applications
Method Parameters
Remove Order Binding to CRM Object crm.orderentity.deleteByFilter
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
Who can execute the method: online store administrator
This method removes the binding of an order to a CRM object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
Field values for removing the binding
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
orderId
*
sale_order.id
Order identifier
ownerTypeId
*
integer
Identifier of the
CRM object type
.
Binding is only possible to a deal or invoice
ownerId
*
integer
Identifier of the CRM object.
For deals, it can be obtained using the
crm.deal.list
method.
For invoices, it can be obtained using the
crm.invoice.list
Code Examples
Code Examples
How to Use Examples in Documentation
Add order binding to a deal:
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
'{"fields":{"orderId":5125,"ownerId":6933,"ownerTypeId":2}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.orderentity.deletebyfilter
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"orderId":5125,"ownerId":6933,"ownerTypeId":2},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.orderentity.deletebyfilter
try
{
const
response =
await
$b24.
callMethod
(
"crm.orderentity.deletebyfilter"
,
{
fields
: {
orderId
:
5125
,
ownerId
:
6933
,
ownerTypeId
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.orderentity.deletebyfilter'
,
[
'fields'
=> [
'orderId'
=>
5125
,
'ownerId'
=>
6933
,
'ownerTypeId'
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
'Error deleting order entity: '
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
"crm.orderentity.deletebyfilter"
,
{
fields
: {
orderId
:
5125
,
ownerId
:
6933
,
ownerTypeId
:
2
}
},
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.orderentity.deletebyfilter'
,
[
'fields'
=> [
'orderId'
=>
5125
,
'ownerId'
=>
6933
,
'ownerTypeId'
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
1719325693.109545
,
"finish"
:
1719325695.863527
,
"duration"
:
2.7539820671081543
,
"processing"
:
1.773292064666748
,
"date_start"
:
"2024-06-25T16:28:13+02:00"
,
"date_finish"
:
"2024-06-25T16:28:15+02:00"
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
Indicates whether the operation was successful
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
"0"
,
"error_description"
:
"Required fields: ownerId, orderId"
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
Description
200040300020
Access Denied
Insufficient access permissions
201640400004
entity relation is not exists
Order binding to the CRM object not found
200540400001
order does not exist
Order not found
0
Required fields: #FIELDS#
Required fields not specified (
#FIELDS#
— list of fields separated by commas)
0
Various order saving errors
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
Add Order Binding to CRM Object crm.orderentity.add
Get a list of order bindings to CRM entities crm.orderentity.list
Get Order Binding Fields crm.orderentity.getFields
Copied
Was the article helpful?
Yes
No
Previous
Retrieve List of Order Links to CRM Entities
Next
Get Order Link Fields

---

## Get Order Binding Fields crm.orderentity.getFields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/order-entity/crm-order-entity-get-fields

Get Order Binding Fields crm.orderentity.getFields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Order Binding Fields crm.orderentity.getFields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Errors
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: online store manager
The method returns a list of available order binding fields. Each field is described as a field settings structure
crm_rest_field_description
.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.orderentity.getFields
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
https://**put_your_bitrix24_address**/rest/crm.orderentity.getFields?auth=**put_access_token_here**
try
{
const
response =
await
$b24.
callMethod
(
"crm.orderentity.getFields"
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.orderentity.getFields'
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
'Error getting order entity fields: '
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
"crm.orderentity.getFields"
,
{},
)
.
then
(
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
log
(result.
data
());
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.orderentity.getFields'
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
"orderEntity"
:
{
"orderId"
:
{
"isImmutable"
:
true
,
"isReadOnly"
:
false
,
"isRequired"
:
true
,
"type"
:
"integer"
}
,
"ownerId"
:
{
"isImmutable"
:
true
,
"isReadOnly"
:
false
,
"isRequired"
:
true
,
"type"
:
"integer"
}
,
"ownerTypeId"
:
{
"isImmutable"
:
true
,
"isReadOnly"
:
false
,
"isRequired"
:
true
,
"type"
:
"integer"
}
}
}
,
"time"
:
{
"start"
:
1718962657.018204
,
"finish"
:
1718962657.773002
,
"duration"
:
0.7547979354858398
,
"processing"
:
0.01193094253540039
,
"date_start"
:
"2024-06-21T11:37:37+02:00"
,
"date_finish"
:
"2024-06-21T11:37:37+02:00"
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
Root element of the response
orderEntity
object
Object with a list of available fields in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field_N
is the identifier of the object
crm_orderentity
, and
value
is an object of type
crm_rest_field_description
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
"200040300010"
,
"error_description"
:
"Access Denied"
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
Description
200040300010
Access Denied
Insufficient access permissions
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
Add Order Binding to CRM Object crm.orderentity.add
Get a list of order bindings to CRM entities crm.orderentity.list
Remove Order Binding to CRM Object crm.orderentity.deleteByFilter
Copied
Was the article helpful?
Yes
No
Previous
Remove Order Link from CRM Entity
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute methods: depending on the method
Method
Description
crm.item.payment.add
Creates a payment for a CRM entity
crm.item.payment.update
Modifies the set of payment fields
crm.item.payment.get
Retrieves brief information about the payment
crm.item.payment.list
Gets a list of payments for a specific CRM entity
crm.item.payment.delete
Deletes a payment
crm.item.payment.pay
Changes the payment status to "Paid"
crm.item.payment.unpay
Changes the payment status to "Unpaid"
Copied
Was the article helpful?
Yes
No
Previous
Get Order Link Fields
Next
Add Payment

---

## Add Payment crm.item.payment.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/crm-item-payment-add

Add Payment crm.item.payment.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Payment crm.item.payment.add
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the CRM object to which the payment is added.
This method creates a payment for a CRM object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityId
*
integer
Identifier of the CRM object
entityTypeId
*
integer
Identifier of the
CRM object type
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
-d '{"entityId":13123,"entityTypeId":2}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.add
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"entityId":13123,"entityTypeId":2,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.add'
, {
entityId
:
13123
,
entityTypeId
:
2
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.add'
,
[
'entityId'
=>
13123
,
'entityTypeId'
=>
2
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
'Error adding payment: '
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
'crm.item.payment.add'
, {
entityId
:
13123
,
entityTypeId
:
2
},
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
log
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
'crm.item.payment.add'
,
[
'entityId'
=>
13123
,
'entityTypeId'
=>
2
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
1033
,
"time"
:
{
"start"
:
1716193064.749158
,
"finish"
:
1716193065.656833
,
"duration"
:
0.90767502784729
,
"processing"
:
0.6450831890106201
,
"date_start"
:
"2024-05-20T11:17:44+02:00"
,
"date_finish"
:
"2024-05-20T11:17:45+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
sale_order_payment.id
Identifier of the created payment
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
"Entity with identifier №13123000 does not exist"
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
0
Access denied
0
Invalid CRM object type
0
The provided CRM object was not found
100
Required fields were not provided
0
Other errors (e.g., fatal errors)
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
Delete Payment crm.item.payment.delete
Get Payment Information crm.item.payment.get
Get the list of payments crm.item.payment.list
Change Payment Status to "Paid" crm.item.payment.pay
Change Payment Status to "Unpaid" crm.item.payment.unpay
Update Payment Fields crm.item.payment.update
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Payment

---

## Update Payment Fields crm.item.payment.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/crm-item-payment-update

Update Payment Fields crm.item.payment.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Payment Fields crm.item.payment.update
Method Parameters
Fields Parameter
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the payment order
This method updates a limited set of payment fields (see
sale.payment.update
for extended functionality with payment fields).
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
sale_order_payment.id
Payment identifier
fields
*
object
Field values for updating the payment
Fields Parameter
Fields Parameter
Name
type
Description
paid
string
Payment status.
Possible values:
Y
– Paid
N
– Not paid
paySystemId
sale_paysystem.id
Payment system identifier
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
-d '{"id":1036,"fields":{"paid":"Y","paySystemId":110}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.update
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":1036,"fields":{"paid":"Y","paySystemId":110},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.update
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.update'
, {
id
:
1036
,
fields
: {
paid
:
"Y"
,
paySystemId
:
110
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.update'
,
[
'id'
=>
1036
,
'fields'
=> [
'paid'
=>
"Y"
,
'paySystemId'
=>
110
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
'Error updating payment: '
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
'crm.item.payment.update'
, {
id
:
1036
,
fields
: {
paid
:
"Y"
,
paySystemId
:
110
,
}
},
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
log
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
'crm.item.payment.update'
,
[
'id'
=>
1036
,
'fields'
=> [
'paid'
=>
'Y'
,
'paySystemId'
=>
110
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
1716212943.651507
,
"finish"
:
1716212944.578154
,
"duration"
:
0.9266471862792969
,
"processing"
:
0.6742370128631592
,
"date_start"
:
"2024-05-20T16:49:03+02:00"
,
"date_finish"
:
"2024-05-20T16:49:04+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation
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
"Insufficient permissions"
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
0
Payment not found or access denied
0
Payment system not found
100
Parameter id not specified
0
Other errors (e.g., fatal errors)
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
Delete Payment crm.item.payment.delete
Get Payment Information crm.item.payment.get
Get the list of payments crm.item.payment.list
Change Payment Status to "Paid" crm.item.payment.pay
Change Payment Status to "Unpaid" crm.item.payment.unpay
Add Payment crm.item.payment.add
Copied
Was the article helpful?
Yes
No
Previous
Add Payment
Next
Get Payment by ID

---

## Get Payment Information crm.item.payment.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/crm-item-payment-get

Get Payment Information crm.item.payment.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Payment Information crm.item.payment.get
Method Parameters
Code Examples
Successful Response
Returned Data
Key result. Object of type sale_order_payment_crm_simple
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: access permission to modify the payment order is required
This method retrieves brief information about the payment.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
sale_order_payment.id
Payment identifier
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
-d '{"id":1036}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":1036,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.get'
, {
id
:
1036
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.get'
,
[
'id'
=>
1036
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
'Error getting payment item: '
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
'crm.item.payment.get'
, {
id
:
1036
,
},
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
log
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
'crm.item.payment.get'
,
[
'id'
=>
1036
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
{
"id"
:
1036
,
"accountNumber"
:
"3653\/1"
,
"paid"
:
"Y"
,
"datePaid"
:
"2024-05-20T12:32:02+02:00"
,
"empPaidId"
:
1
,
"paySystemId"
:
6
,
"sum"
:
0
,
"currency"
:
"USD"
,
"paySystemName"
:
"Cash"
}
,
"time"
:
{
"start"
:
1716203536.414886
,
"finish"
:
1716203536.798211
,
"duration"
:
0.38332509994506836
,
"processing"
:
0.052394866943359375
,
"date_start"
:
"2024-05-20T14:12:16+02:00"
,
"date_finish"
:
"2024-05-20T14:12:16+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
sale_order_payment_crm_simple
Object containing brief information about the payment
time
time
Information about the request execution time
Key result. Object of type sale_order_payment_crm_simple
Key result. Object of type sale_order_payment_crm_simple
Name
type
Description
id
sale_order_payment.id
Payment identifier
accountNumber
string
System payment number
paid
string
Payment status
Possible values:
Y
– Paid
N
– Not paid
datePaid
datetime
Payment date
empPaidId
user.id
User who made the payment
paySystemId
sale_paysystem.id
Payment system identifier
sum
double
Payment amount
currency
string
Payment currency
paySystemName
string
Name of the payment system
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
"Insufficient permissions"
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
0
Payment not found or access denied
100
Parameter id not specified
0
Other errors (e.g., fatal errors)
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
Update Payment Fields crm.item.payment.update
Delete Payment crm.item.payment.delete
Get the list of payments crm.item.payment.list
Change Payment Status to "Paid" crm.item.payment.pay
Change Payment Status to "Unpaid" crm.item.payment.unpay
Add Payment crm.item.payment.add
Copied
Was the article helpful?
Yes
No
Previous
Update Payment
Next
Get List of Payments

---

## Get the list of payments crm.item.payment.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/crm-item-payment-list

Get the list of payments crm.item.payment.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of payments crm.item.payment.list
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires read access permission for the CRM object from which payments are selected.
The method retrieves a list of payments for a specific CRM object.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityId
*
integer
Identifier of the CRM object
entityTypeId
*
integer
Identifier of the
CRM object type
filter
object
Additional filter for cases when you need to get not all payments of the entity, but based on a more specific filter. The format description is provided in the
filter
parameter of the
sale.payment.list
method
order
object
The format description is provided in the
order
parameter of the
sale.payment.list
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"entityId":13123,"entityTypeId":2,"filter":{"@id":[1036,1037]}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"entityId":13123,"entityTypeId":2,"filter":{"@id":[1036,1037]},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.item.payment.list'
,
{
entityId
:
13123
,
entityTypeId
:
2
,
filter
: {
"@id"
: [
1036
,
1037
]
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
'crm.item.payment.list'
, {
entityId
:
13123
,
entityTypeId
:
2
,
filter
: {
"@id"
: [
1036
,
1037
]
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.list'
, {
entityId
:
13123
,
entityTypeId
:
2
,
filter
: {
"@id"
: [
1036
,
1037
]
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
'crm.item.payment.list'
,
[
'entityId'
=>
13123
,
'entityTypeId'
=>
2
,
'filter'
=> [
"@id"
=> [
1036
,
1037
]
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
'Error fetching payment list: '
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
'crm.item.payment.list'
, {
entityId
:
13123
,
entityTypeId
:
2
,
filter
: {
"@id"
: [
1036
,
1037
]
},
},
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
log
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
'crm.item.payment.list'
,
[
'entityId'
=>
13123
,
'entityTypeId'
=>
2
,
'filter'
=> [
'@id'
=> [
1036
,
1037
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
Successful Response
Successful Response
HTTP status:
200
{
"result"
:
[
{
"id"
:
1036
,
"accountNumber"
:
"3653\/1"
,
"paid"
:
"Y"
,
"datePaid"
:
"2024-05-20T12:32:02+02:00"
,
"empPaidId"
:
1
,
"paySystemId"
:
6
,
"sum"
:
0
,
"currency"
:
"USD"
,
"paySystemName"
:
"Cash"
}
,
{
"id"
:
1037
,
"accountNumber"
:
"3653\/2"
,
"paid"
:
"N"
,
"datePaid"
:
null
,
"empPaidId"
:
null
,
"paySystemId"
:
6
,
"sum"
:
0
,
"currency"
:
"USD"
,
"paySystemName"
:
"Cash"
}
]
,
"time"
:
{
"start"
:
1716205783.285524
,
"finish"
:
1716205783.702053
,
"duration"
:
0.41652917861938477
,
"processing"
:
0.15817594528198242
,
"date_start"
:
"2024-05-20T14:49:43+02:00"
,
"date_finish"
:
"2024-05-20T14:49:43+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
sale_order_payment_crm_simple[]
Array of objects containing brief information about the selected payments
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
0
,
"error_description"
:
"Insufficient permissions"
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
0
Access denied
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Update Payment Fields crm.item.payment.update
Delete Payment crm.item.payment.delete
Get Payment Information crm.item.payment.get
Change Payment Status to "Paid" crm.item.payment.pay
Change Payment Status to "Unpaid" crm.item.payment.unpay
Add Payment crm.item.payment.add
How to Save the Payment Date in the Deal Field
Copied
Was the article helpful?
Yes
No
Previous
Get Payment by ID
Next
Delete Payment

---

## Delete Payment crm.item.payment.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/crm-item-payment-delete

Delete Payment crm.item.payment.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Payment crm.item.payment.delete
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the payment order
This method deletes a payment.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
sale_order_payment.id
Payment identifier
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
-d '{"id":1035}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":1035,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.delete'
, {
id
:
1035
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.delete'
,
[
'id'
=>
1035
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
'Error deleting payment: '
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
'crm.item.payment.delete'
, {
id
:
1035
,
},
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
log
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
'crm.item.payment.delete'
,
[
'id'
=>
1035
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
1716196289.346624
,
"finish"
:
1716196289.96146
,
"duration"
:
0.6148362159729004
,
"processing"
:
0.37704014778137207
,
"date_start"
:
"2024-05-20T12:11:29+03:00"
,
"date_finish"
:
"2024-05-20T12:11:29+03:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of payment deletion
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
"Insufficient permissions"
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
0
Payment not found or access denied
100
Parameter id not specified
0
Other errors (e.g., fatal errors)
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
Update Payment Fields crm.item.payment.update
Get Payment Information crm.item.payment.get
Get the list of payments crm.item.payment.list
Change Payment Status to "Paid" crm.item.payment.pay
Change Payment Status to "Unpaid" crm.item.payment.unpay
Add Payment crm.item.payment.add
Copied
Was the article helpful?
Yes
No
Previous
Get List of Payments
Next
Change Status to "Paid"

---

## Change Payment Status to "Paid" crm.item.payment.pay

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/crm-item-payment-pay

Change Payment Status to "Paid" crm.item.payment.pay | Bitrix24 REST API and Marketplace Applications
Method Parameters
Change Payment Status to "Paid" crm.item.payment.pay
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: access permission to modify the payment order is required
This method changes the payment status to "Paid".
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
sale_order_payment.id
Payment identifier
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
-d '{"id":1038}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.pay
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":1038,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.pay
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.pay'
, {
id
:
1038
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.pay'
,
[
'id'
=>
1038
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
'Error paying item: '
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
'crm.item.payment.pay'
, {
id
:
1038
},
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
log
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
'crm.item.payment.pay'
,
[
'id'
=>
1038
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
1716208789.599812
,
"finish"
:
1716208790.791299
,
"duration"
:
1.1914870738983154
,
"processing"
:
0.9303650856018066
,
"date_start"
:
"2024-05-20T15:39:49+03:00"
,
"date_finish"
:
"2024-05-20T15:39:50+03:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation
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
"Insufficient permissions"
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
0
Payment not found or access denied
100
Parameter id not specified
0
Other errors (e.g., fatal errors)
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
Delete Payment crm.item.payment.delete
Get Payment Information crm.item.payment.get
Get the list of payments crm.item.payment.list
Update Payment Fields crm.item.payment.update
Change Payment Status to "Unpaid" crm.item.payment.unpay
Add Payment crm.item.payment.add
Copied
Was the article helpful?
Yes
No
Previous
Delete Payment
Next
Change Status to "Unpaid"

---

## Change Payment Status to "Unpaid" crm.item.payment.unpay

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/crm-item-payment-unpay

Change Payment Status to "Unpaid" crm.item.payment.unpay | Bitrix24 REST API and Marketplace Applications
Change Payment Status to "Unpaid" crm.item.payment.unpay
Change Payment Status to "Unpaid" crm.item.payment.unpay
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: access permission to modify the payment order is required
This method changes the payment status to "Unpaid".
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
sale_order_payment.id
Payment identifier
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
-d '{"id":1038}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.unpay
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":1038,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.unpay
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.unpay'
, {
id
:
1038
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.unpay'
,
[
'id'
=>
1038
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
'Error unpaying payment: '
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
'crm.item.payment.unpay'
, {
id
:
1038
},
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
log
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
'crm.item.payment.unpay'
,
[
'id'
=>
1038
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
1716209825.900064
,
"finish"
:
1716209826.931873
,
"duration"
:
1.0318090915679932
,
"processing"
:
0.7891800403594971
,
"date_start"
:
"2024-05-20T15:57:05+02:00"
,
"date_finish"
:
"2024-05-20T15:57:06+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation
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
"Insufficient permissions"
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
0
Payment not found or access denied
100
Parameter id not specified
0
Other errors (e.g., fatal errors)
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
Delete Payment crm.item.payment.delete
Get Payment Information crm.item.payment.get
Get the list of payments crm.item.payment.list
Update Payment Fields crm.item.payment.update
Change Payment Status to "Paid" crm.item.payment.pay
Add Payment crm.item.payment.add
Copied
Was the article helpful?
Yes
No
Previous
Change Status to "Paid"
Next
Generate Link for Specific Payment

---

## Generate a link for a specific payment salescenter.payment.getPublicUrl

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/salescenter-payment-get-public-url

Generate a link for a specific payment salescenter.payment.getPublicUrl | Bitrix24 REST API and Marketplace Applications
Generate a link for a specific payment salescenter.payment.getPublicUrl
Generate a link for a specific payment salescenter.payment.getPublicUrl
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
salescenter
Who can execute the method: any user
This method generates a link for a specific payment. The payment method selected will be passed to this particular payment.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
sale_order_payment.id
Payment identifier
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
'{"id":1063}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/salescenter.payment.getPublicUrl
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":1063,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/salescenter.payment.getPublicUrl
try
{
const
response =
await
$b24.
callMethod
(
'salescenter.payment.getPublicUrl'
, {
id
:
1063
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'salescenter.payment.getPublicUrl'
,
[
'id'
=>
1063
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
'Error getting public URL: '
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
'salescenter.payment.getPublicUrl'
, {
id
:
1063
,
},
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
log
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
'salescenter.payment.getPublicUrl'
,
[
'id'
=>
1063
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
{
"payment"
:
{
"url"
:
"http:\/\/account.home\/pub\/site\/10\/oformleniezakaza\/?orderId=3689\u0026access=f83b5926bd8cb4f0248b4b5a8e48b6fb\u0026paymentId=1063"
,
"shortUrl"
:
"http:\/\/account.home\/~tR9sB"
,
"qr"
:
"iVBORw0KGgoAAAANSUhEUgAAAXwAAAF8CAYAAADM5wDKAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAHaElEQVR4nO3csW7jVhRF0SjQ\/\/+y0owFN4GVeYou7+y1KhdjiCI5G8\/NuT0ej8dfAPzx\/p6+AAA+4\/71w+12m7wOXnDyx9jJ8536I7D2Tm78Y7v2jDb6\/l454QNECD5AhOADRAg+QITgA0QIPkCE4ANECD5AhOADRAg+QITgA0QIPkCE4ANECD5AxP3nf\/KzjbOuUzbOyU5d88Y56Kl7tXH+Wjde9673ygkfIELwASIEHyBC8AEiBB8gQvABIgQfIELwASIEHyBC8AEiBB8gQvABIgQfIELwASLeMo98YuNc8MZZ16lrPnm+tanhjRPHU3Tj9zjhA0QIPkCE4ANECD5AhOADRAg+QITgA0QIPkCE4ANECD5AhOADRAg+QITgA0QIPkDE+Dwy\/JuNk85wZU74ABGCDxAh+AARgg8QIfgAEYIPECH4ABGCDxAh+AARgg8QIfgAEYIPECH4ABGCDxBhHjli4+TvyTWfTCuf\/O7UNcMrnPABIgQfIELwASIEHyBC8AEiBB8gQvABIgQfIELwASIEHyBC8AEiBB8gQvABIgQfIGJ8Htkk7PVNPaOpSWdT0te38ZqvwAkfIELwASIEHyBC8AEiBB8gQvABIgQfIELwASIEHyBC8AEiBB8gQvABIgQfIELwASLeMo+8cU6Wz5ia7d34uTXu1ec54QNECD5AhOADRAg+QITgA0QIPkCE4ANECD5AhOADRAg+QITgA0QIPkCE4ANECD5AxHMe+WQSFv4Ptfncjd9XN3ZxwgeIEHyACMEHiBB8gAjBB4gQfIAIwQeIEHyACMEHiBB8gAjBB4gQfIAIwQeIEHyAiNvj176padbXTd2rk+\/r+f7ZNj7fKeVuOOEDRAg+QITgA0QIPkCE4ANECD5AhOADRAg+QITgA0QIPkCE4ANECD5AhOADRAg+QMT964ep6V2Tv6\/b+H03cp+vb2OvrsAJHyBC8AEiBB8gQvABIgQfIELwASIEHyBC8AEiBB8gQvABIgQfIELwASIEHyBC8AEinvPItYnjqZnTjdO7G+\/VyTVv\/L4bbZwa3t5JJ3yACMEHiBB8gAjBB4gQfIAIwQeIEHyACMEHiBB8gAjBB4gQfIAIwQeIEHyACMEHiLg9Nm6U\/mJa+XVT06yLXy9eYNJ5Fyd8gAjBB4gQfIAIwQeIEHyACMEHiBB8gAjBB4gQfIAIwQeIEHyACMEHiBB8gAjBB4i4f\/2wceZ040wxr6vNX5+oTVhvvOYT73q+TvgAEYIPECH4ABGCDxAh+AARgg8QIfgAEYIPECH4ABGCDxAh+AARgg8QIfgAEYIPEPGcR944N7pxEnbjfZ5ycq+mppU3TmdvvOaNrnCfnfABIgQfIELwASIEHyBC8AEiBB8gQvABIgQfIELwASIEHyBC8AEiBB8gQvABIgQfIOI5jzw13Tk1Fzw1rbxx0rlm47txYuM1X2Fq+L+6wn12wgeIEHyACMEHiBB8gAjBB4gQfIAIwQeIEHyACMEHiBB8gAjBB4gQfIAIwQeIEHyAiNtjeHO3NnM6ZeN9nrJxsvvExveZ3+OEDxAh+AARgg8QIfgAEYIPECH4ABGCDxAh+AARgg8QIfgAEYIPECH4ABGCDxAh+AAR968fzOd+xsl93jhju3FqeOoZnfzu1PfdaOM7+a5rdsIHiBB8gAjBB4gQfIAIwQeIEHyACMEHiBB8gAjBB4gQfIAIwQeIEHyACMEHiBB8gAjBB4gQfIAIwQeIuD1qe64AUU74ABGCDxDxD3Dwaiq9kYVcAAAAAElFTkSuQmCC"
}
}
,
"time"
:
{
"start"
:
1718372619.163703
,
"finish"
:
1718372619.567831
,
"duration"
:
0.4041280746459961
,
"processing"
:
0.15733885765075684
,
"date_start"
:
"2024-06-14T16:43:39+02:00"
,
"date_finish"
:
"2024-06-14T16:43:39+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response
url
string
Payment link
shortUrl
string
Short payment link
qr
string
QR code containing the short payment link
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
200640400001
,
"error_description"
:
"payment does not exist"
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
200640400001
Payment not found
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Add Payment crm.item.payment.add
Update Payment Fields crm.item.payment.update
Get Payment Information crm.item.payment.get
Get the list of payments crm.item.payment.list
Change Payment Status to "Paid" crm.item.payment.pay
Change Payment Status to "Unpaid" crm.item.payment.unpay
Delete Payment crm.item.payment.delete
Copied
Was the article helpful?
Yes
No
Previous
Change Status to "Unpaid"
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/products-in-payment/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: depending on the method
Method
Description
crm.item.payment.product.add
Adds a product item to the payment
crm.item.payment.product.list
Retrieves a list of product items in the payment
crm.item.payment.product.delete
Removes a product item from the payment
crm.item.payment.product.setQuantity
Changes the quantity of the product in the payment item
Copied
Was the article helpful?
Yes
No
Previous
Generate Link for Specific Payment
Next
Add Product Item

---

## Add Product Item to Payment crm.item.payment.product.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/products-in-payment/crm-item-payment-product-add

Add Product Item to Payment crm.item.payment.product.add | Bitrix24 REST API and Marketplace Applications
Add Product Item to Payment crm.item.payment.product.add
Add Product Item to Payment crm.item.payment.product.add
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the order to which the product item is being added
This method adds a product item to the payment.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
paymentId
*
sale_order_payment.id
Payment identifier.
Can be obtained using the method
sale.payment.list
rowId
*
integer
Identifier of the product item in the CRM object.
Can be obtained using
crm.item.productrow.list
quantity
*
double
Quantity of the product
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
-d '{"paymentId":1039,"rowId":17587,"quantity":2}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.product.add
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"paymentId":1039,"rowId":17587,"quantity":2,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.product.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.product.add'
, {
paymentId
:
1039
,
rowId
:
17587
,
quantity
:
2
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.product.add'
,
[
'paymentId'
=>
1039
,
'rowId'
=>
17587
,
'quantity'
=>
2
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
'Error adding payment product: '
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
'crm.item.payment.product.add'
, {
paymentId
:
1039
,
rowId
:
17587
,
quantity
:
2
},
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
log
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
'crm.item.payment.product.add'
,
[
'paymentId'
=>
1039
,
'rowId'
=>
17587
,
'quantity'
=>
2
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
1193
,
"time"
:
{
"start"
:
1716276648.349503
,
"finish"
:
1716276649.261574
,
"duration"
:
0.9120709896087646
,
"processing"
:
0.6422691345214844
,
"date_start"
:
"2024-05-21T10:30:48+02:00"
,
"date_finish"
:
"2024-05-21T10:30:49+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
integer
Identifier of the product item in the payment
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
0
,
"error_description"
:
"Payment has not been found"
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
0
Payment not found
0
Access denied
0
Product item not found
0
Insufficient product quantity to add to payment
0
Product quantity cannot be less than or equal to 0
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Change Product Quantity crm.item.payment.product.setQuantity
Get a list of payment product items crm.item.payment.product.list
Remove product item from payment crm.item.payment.product.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get List of Product Items

---

## Get a list of payment product items crm.item.payment.product.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/products-in-payment/crm-item-payment-product-list

Get a list of payment product items crm.item.payment.product.list | Bitrix24 REST API and Marketplace Applications
Get a list of payment product items crm.item.payment.product.list
Get a list of payment product items crm.item.payment.product.list
Method Parameters
Code Examples
Successful Response
Returned Data
Key result. Object of type crm_item_payment_product
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: read access permission for the payment order is required
This method retrieves a list of product items (goods or services) for a specific payment.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
paymentId
*
sale_order_payment.id
Payment identifier.
Can be obtained using the
sale.payment.list
method
filter
*
object
Object for filtering selected payment product items in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
:
id
quantity
An additional prefix can be specified for the key to clarify the filter behavior. Possible prefix values:
=
— equals, exact match (used by default)
%
— LIKE, substring search. The % symbol in the filter value does not need to be passed. The search looks for the substring in any position of the string
>
— greater than
<
— less than
!=
— not equal
!%
— NOT LIKE, substring search. The % symbol in the filter value does not need to be passed. The search goes from both sides.
>=
— greater than or equal to
<=
— less than or equal to
=%
— LIKE, substring search. The % symbol needs to be passed in the value. Examples:
"mol%"
— searching for values starting with "mol"
"%mol"
— searching for values ending with "mol"
"%mol%"
— searching for values where "mol" can be in any position
%=
— LIKE (see description above)
!=%
— NOT LIKE, substring search. The % symbol needs to be passed in the value. Examples:
"mol%"
— searching for values not starting with "mol"
"%mol"
— searching for values not ending with "mol"
"%mol%"
— searching for values where the substring "mol" is not present in any position
!%=
— NOT LIKE (see description above)
order
object
Object for sorting selected payment product items in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
:
id
quantity
Possible values for
order
:
asc
— in ascending order
desc
— in descending order
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
-d '{"paymentId":1039,"filter":{"\u003E=quantity":2,"@id":[1195,1196]}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.product.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"paymentId":1039,"filter":{"\u003E=quantity":2,"@id":[1195,1196]},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.product.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.item.payment.product.list'
,
{
paymentId
:
1039
,
filter
: {
">=quantity"
:
2
,
"@id"
: [
1195
,
1196
],
},
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
'crm.item.payment.product.list'
, {
paymentId
:
1039
,
filter
: {
">=quantity"
:
2
,
"@id"
: [
1195
,
1196
],
},
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
'crm.item.payment.product.list'
, {
paymentId
:
1039
,
filter
: {
">=quantity"
:
2
,
"@id"
: [
1195
,
1196
],
},
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
'crm.item.payment.product.list'
,
[
'paymentId'
=>
1039
,
'filter'
=> [
'>=quantity'
=>
2
,
'@id'
=> [
1195
,
1196
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
'Error fetching payment product list: '
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
'crm.item.payment.product.list'
, {
paymentId
:
1039
,
filter
: {
">=quantity"
:
2
,
"@id"
: [
1195
,
1196
],
},
},
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
log
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
'crm.item.payment.product.list'
,
[
'paymentId'
=>
1039
,
'filter'
=> [
">=quantity"
=>
2
,
"@id"
=> [
1195
,
1196
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
Successful Response
Successful Response
HTTP status:
200
{
"result"
:
[
{
"id"
:
1195
,
"paymentId"
:
1039
,
"quantity"
:
2
,
"rowId"
:
17587
}
,
{
"id"
:
1196
,
"paymentId"
:
1039
,
"quantity"
:
3
,
"rowId"
:
17588
}
]
,
"time"
:
{
"start"
:
1716286140.489916
,
"finish"
:
1716286140.802505
,
"duration"
:
0.3125889301300049
,
"processing"
:
0.053195953369140625
,
"date_start"
:
"2024-05-21T13:09:00+02:00"
,
"date_finish"
:
"2024-05-21T13:09:00+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
crm_item_payment_product[]
Array of objects containing information about the selected payment product items
time
time
Information about the execution time of the request
Key result. Object of type crm_item_payment_product
Key result. Object of type crm_item_payment_product
Name
type
Description
id
integer
Identifier of the product item in the payment
paymentId
sale_order_payment.id
Payment identifier
quantity
double
Quantity of the product
rowId
integer
Identifier of the product item in the CRM entity
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
"Payment has not been found"
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
0
Payment not found
0
Access denied
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Add Product Item to Payment crm.item.payment.product.add
Change Product Quantity crm.item.payment.product.setQuantity
Remove product item from payment crm.item.payment.product.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Product Item
Next
Delete Product Item

---

## Remove product item from payment crm.item.payment.product.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/products-in-payment/crm-item-payment-product-delete

Remove product item from payment crm.item.payment.product.delete | Bitrix24 REST API and Marketplace Applications
Remove product item from payment crm.item.payment.product.delete
Remove product item from payment crm.item.payment.product.delete
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the order from which the product item is removed.
The method removes a product item from the payment.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the product item in the payment.
Can be obtained using
crm.item.payment.product.list
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
-d '{"id":1194}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.product.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":1194,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.product.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.product.delete'
, {
id
:
1194
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.product.delete'
,
[
'id'
=>
1194
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
'Error deleting payment product: '
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
'crm.item.payment.product.delete'
, {
id
:
1194
,
},
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
log
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
'crm.item.payment.product.delete'
,
[
'id'
=>
1194
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
1716281948.98814
,
"finish"
:
1716281949.752528
,
"duration"
:
0.764387845993042
,
"processing"
:
0.488523006439209
,
"date_start"
:
"2024-05-21T11:59:08+03:00"
,
"date_finish"
:
"2024-05-21T11:59:09+03:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation
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
"Payable item has not been found"
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
0
Product item not found
0
Access denied
100
Parameter id not specified
0
Other errors (e.g., fatal errors)
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
Add Product Item to Payment crm.item.payment.product.add
Get a list of payment product items crm.item.payment.product.list
Remove product item from payment crm.item.payment.product.delete
Copied
Was the article helpful?
Yes
No
Previous
Get List of Product Items
Next
Change Product Quantity

---

## Change Product Quantity crm.item.payment.product.setQuantity

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/products-in-payment/crm-item-payment-product-set-quantity

Change Product Quantity crm.item.payment.product.setQuantity | Bitrix24 REST API and Marketplace Applications
Change Product Quantity crm.item.payment.product.setQuantity
Change Product Quantity crm.item.payment.product.setQuantity
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: access permission to modify the payment order is required
This method changes the quantity of a product in the payment line item.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the product line item in the payment
quantity
*
double
Quantity of the product
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
-d '{"id":1195,"quantity":3}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.product.setQuantity
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":1195,"quantity":3,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.product.setQuantity
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.product.setQuantity'
, {
id
:
1195
,
quantity
:
3
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.product.setQuantity'
,
[
'id'
=>
1195
,
'quantity'
=>
3
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
'Error setting product quantity: '
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
'crm.item.payment.product.setQuantity'
, {
id
:
1195
,
quantity
:
3
},
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
log
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
'crm.item.payment.product.setQuantity'
,
[
'id'
=>
1195
,
'quantity'
=>
3
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
1716282831.283905
,
"finish"
:
1716282832.02954
,
"duration"
:
0.7456350326538086
,
"processing"
:
0.4978060722351074
,
"date_start"
:
"2024-05-21T12:13:51+03:00"
,
"date_finish"
:
"2024-05-21T12:13:52+03:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation
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
"Payable item has not been found"
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
0
Product line item not found
0
Access denied
0
Quantity of the product cannot be less than or equal to 0
0
Insufficient product to add to payment
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Add Product Item to Payment crm.item.payment.product.add
Get a list of payment product items crm.item.payment.product.list
Remove product item from payment crm.item.payment.product.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete Product Item
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/delivery-in-payment/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: depending on the method
Method
Description
crm.item.payment.delivery.add
Adds a delivery item to the payment
crm.item.payment.delivery.list
Retrieves a list of delivery items for a specific payment
crm.item.payment.delivery.delete
Removes a delivery item from the payment
crm.item.payment.delivery.setDelivery
Reassigns a delivery item to another delivery document
Copied
Was the article helpful?
Yes
No
Previous
Change Product Quantity
Next
Add Delivery Item to Payment

---

## Add Delivery Item to Payment crm.item.payment.delivery.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/delivery-in-payment/crm-item-payment-delivery-add

Add Delivery Item to Payment crm.item.payment.delivery.add | Bitrix24 REST API and Marketplace Applications
Add Delivery Item to Payment crm.item.payment.delivery.add
Add Delivery Item to Payment crm.item.payment.delivery.add
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the order to which the delivery item is added.
This method adds a delivery item to the payment.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
paymentId
*
sale_order_payment.id
Payment identifier.
Can be obtained using the method
sale.payment.list
deliveryId
*
sale_order_shipment.id
Delivery identifier.
Can be obtained using the method
crm.item.delivery.list
(key id)
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
-d '{"paymentId":1039,"deliveryId":4072}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.delivery.add
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"paymentId":1039,"deliveryId":4072,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.delivery.add
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.delivery.add'
, {
paymentId
:
1039
,
deliveryId
:
4072
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.delivery.add'
,
[
'paymentId'
=>
1039
,
'deliveryId'
=>
4072
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
'Error adding payment delivery: '
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
'crm.item.payment.delivery.add'
, {
paymentId
:
1039
,
deliveryId
:
4072
},
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
log
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
'crm.item.payment.delivery.add'
,
[
'paymentId'
=>
1039
,
'deliveryId'
=>
4072
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
1199
,
"time"
:
{
"start"
:
1716295802.83799
,
"finish"
:
1716295804.17372
,
"duration"
:
1.3357298374176025
,
"processing"
:
0.8379831314086914
,
"date_start"
:
"2024-05-21T15:50:02+02:00"
,
"date_finish"
:
"2024-05-21T15:50:04+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
integer
Identifier of the delivery item in the payment
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
0
,
"error_description"
:
"Payment has not been found"
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
0
Payment not found
0
Access denied
0
Delivery item not found
100
Required parameters not provided
0
Other errors (e.g., fatal errors)
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
Get Delivery Item List by Specific Payment crm.item.payment.delivery.list
Remove Delivery Item from Payment crm.item.payment.delivery.delete
Reassign the delivery item to another document crm.item.payment.delivery.setDelivery
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get List of Delivery Items for a Specific Payment

---

## Get Delivery Item List by Specific Payment crm.item.payment.delivery.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/delivery-in-payment/crm-item-payment-delivery-list

Get Delivery Item List by Specific Payment crm.item.payment.delivery.list | Bitrix24 REST API and Marketplace Applications
Get Delivery Item List by Specific Payment crm.item.payment.delivery.list
Get Delivery Item List by Specific Payment crm.item.payment.delivery.list
Method Parameters
Code Examples
Successful Response
Returned Data
Key result. Object of type crm_item_payment_delivery
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: read access permission for the payment order is required
This method retrieves a list of delivery items for a specific payment.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
paymentId
*
sale_order_payment.id
Payment identifier.
Can be obtained using the method
sale.payment.list
filter
*
object
Object for filtering selected delivery items in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
Possible values for
field
:
id
quantity
An additional prefix can be assigned to the key to specify the filter behavior. Possible prefix values:
=
— equals, exact match (default)
%
— LIKE, substring search. The % symbol should not be included in the filter value. The search looks for the substring in any position of the string
>
— greater than
<
— less than
!=
— not equal
!%
— NOT LIKE, substring search. The % symbol should not be included in the filter value. The search goes from both sides.
>=
— greater than or equal to
<=
— less than or equal to
=%
— LIKE, substring search. The % symbol should be included in the value. Examples:
"mol%"
— searching for values starting with "mol"
"%mol"
— searching for values ending with "mol"
"%mol%"
— searching for values where "mol" can be in any position
%=
— LIKE (see description above)
!=%
— NOT LIKE, substring search. The % symbol should be included in the value. Examples:
"mol%"
— searching for values not starting with "mol"
"%mol"
— searching for values not ending with "mol"
"%mol%"
— searching for values where the substring "mol" is not present in any position
!%=
— NOT LIKE (see description above)
order
object
Object for sorting selected delivery items of the payment in the format
{"field_1": "order_1", ... "field_N": "order_N"}
.
Possible values for
field
:
id
quantity
Possible values for
order
:
asc
— in ascending order
desc
— in descending order
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
-d '{"paymentId":1040,"filter":{"@id":[1201], ">=quantity":1}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.delivery.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"paymentId":1040,"filter":{"@id":[1201], ">=quantity":1},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.delivery.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.item.payment.delivery.list'
,
{
paymentId
:
1040
,
filter
: {
">=quantity"
:
1
,
"@id"
: [
1201
],
},
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
'crm.item.payment.delivery.list'
, {
paymentId
:
1040
,
filter
: {
">=quantity"
:
1
,
"@id"
: [
1201
],
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
'crm.item.payment.delivery.list'
, {
paymentId
:
1040
,
filter
: {
">=quantity"
:
1
,
"@id"
: [
1201
],
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
'crm.item.payment.delivery.list'
,
[
'paymentId'
=>
1040
,
'filter'
=> [
">=quantity"
=>
1
,
"@id"
=> [
1201
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
'Error fetching payment delivery list: '
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
'crm.item.payment.delivery.list'
, {
paymentId
:
1040
,
filter
: {
">=quantity"
:
1
,
"@id"
: [
1201
],
},
},
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
log
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
'crm.item.payment.delivery.list'
,
[
'paymentId'
=>
1040
,
'filter'
=> [
'>=quantity'
=>
1
,
'@id'
=> [
1201
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
Successful Response
Successful Response
HTTP status:
200
{
"result"
:
[
{
"id"
:
1201
,
"paymentId"
:
1040
,
"quantity"
:
1
,
"deliveryId"
:
4073
}
]
,
"time"
:
{
"start"
:
1716301848.792584
,
"finish"
:
1716301849.095721
,
"duration"
:
0.30313706398010254
,
"processing"
:
0.05563783645629883
,
"date_start"
:
"2024-05-21T17:30:48+02:00"
,
"date_finish"
:
"2024-05-21T17:30:49+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
crm_item_payment_delivery[]
Array of objects containing information about the selected delivery items for the payment
time
time
Information about the execution time of the request
Key result. Object of type crm_item_payment_delivery
Key result. Object of type crm_item_payment_delivery
Name
type
Description
id
integer
Identifier of the delivery item in the payment
paymentId
sale_order_payment.id
Payment identifier
quantity
double
Quantity
deliveryId
sale_order_shipment.id
Delivery identifier
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
"Payment has not been found"
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
0
Payment not found
0
Access denied
100
Required parameters not provided
0
Other errors (e.g., fatal errors)
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
Add Delivery Item to Payment crm.item.payment.delivery.add
Remove Delivery Item from Payment crm.item.payment.delivery.delete
Reassign the delivery item to another document crm.item.payment.delivery.setDelivery
Copied
Was the article helpful?
Yes
No
Previous
Add Delivery Item to Payment
Next
Remove Delivery Item from Payment

---

## Remove Delivery Item from Payment crm.item.payment.delivery.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/delivery-in-payment/crm-item-payment-delivery-delete

Remove Delivery Item from Payment crm.item.payment.delivery.delete | Bitrix24 REST API and Marketplace Applications
Remove Delivery Item from Payment crm.item.payment.delivery.delete
Remove Delivery Item from Payment crm.item.payment.delivery.delete
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires access permission to modify the order from which the delivery item is removed.
The method removes a delivery item from the payment.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the delivery item in the payment.
Can be obtained using the method
crm.item.payment.delivery.list
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
-d '{"id":1199}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.delivery.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":1199,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.delivery.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.delivery.delete'
, {
id
:
1199
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.delivery.delete'
,
[
'id'
=>
1199
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
'Error deleting payment delivery: '
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
'crm.item.payment.delivery.delete'
, {
id
:
1199
,
},
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
log
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
'crm.item.payment.delivery.delete'
,
[
'id'
=>
1199
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
1716296091.028902
,
"finish"
:
1716296092.17101
,
"duration"
:
1.1421079635620117
,
"processing"
:
0.7571370601654053
,
"date_start"
:
"2024-05-21T15:54:51+03:00"
,
"date_finish"
:
"2024-05-21T15:54:52+03:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation
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
"Payable item has not been found"
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
0
Delivery item not found
0
Access denied
100
Parameter id not specified
0
Other errors (e.g., fatal errors)
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
Add Delivery Item to Payment crm.item.payment.delivery.add
Get Delivery Item List by Specific Payment crm.item.payment.delivery.list
Reassign the delivery item to another document crm.item.payment.delivery.setDelivery
Copied
Was the article helpful?
Yes
No
Previous
Get List of Delivery Items for a Specific Payment
Next
Reassign Delivery Item to Another Document

---

## Reassign the delivery item to another document crm.item.payment.delivery.setDelivery

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/payment/delivery-in-payment/crm-item-payment-delivery-set-delivery

Reassign the delivery item to another document crm.item.payment.delivery.setDelivery | Bitrix24 REST API and Marketplace Applications
Reassign the delivery item to another document crm.item.payment.delivery.setDelivery
Reassign the delivery item to another document crm.item.payment.delivery.setDelivery
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: access permission to modify the payment order is required
This method reassigns the delivery item to another delivery document.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the delivery item in the payment.
Can be obtained using the method
crm.item.payment.delivery.list
deliveryId
*
sale_order_shipment.id
Identifier of the delivery.
Can be obtained using the method
crm.item.delivery.list
(key id)
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
-d '{"id":1201,"deliveryId":4073}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.payment.delivery.setDelivery
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":1201,"deliveryId":4073,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.payment.delivery.setDelivery
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.payment.delivery.setDelivery'
, {
id
:
1201
,
deliveryId
:
4073
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.payment.delivery.setDelivery'
,
[
'id'
=>
1201
,
'deliveryId'
=>
4073
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
'Error setting delivery for payment: '
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
'crm.item.payment.delivery.setDelivery'
, {
id
:
1201
,
deliveryId
:
4073
,
},
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
log
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
'crm.item.payment.delivery.setDelivery'
,
[
'id'
=>
1201
,
'deliveryId'
=>
4073
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
1716296989.985067
,
"finish"
:
1716296991.216063
,
"duration"
:
1.2309961318969727
,
"processing"
:
0.8141369819641113
,
"date_start"
:
"2024-05-21T16:09:49+03:00"
,
"date_finish"
:
"2024-05-21T16:09:51+03:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Result of the operation
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
"Payable item has not been found"
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
0
Delivery item not found
0
Access denied
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Add Delivery Item to Payment crm.item.payment.delivery.add
Remove Delivery Item from Payment crm.item.payment.delivery.delete
Get Delivery Item List by Specific Payment crm.item.payment.delivery.list
Copied
Was the article helpful?
Yes
No
Previous
Remove Delivery Item from Payment
Next
Overview of Methods

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/delivery/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the methods: depending on the method
Method
Description
crm.item.delivery.get
Retrieves delivery information by id
crm.item.delivery.list
Retrieves a list of deliveries for a CRM entity
Copied
Was the article helpful?
Yes
No
Previous
Reassign Delivery Item to Another Document
Next
Get Delivery Information by ID

---

## Get Delivery Information by ID crm.item.delivery.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/delivery/crm-item-delivery-get

Get Delivery Information by ID crm.item.delivery.get | Bitrix24 REST API and Marketplace Applications
Get Delivery Information by ID crm.item.delivery.get
Get Delivery Information by ID crm.item.delivery.get
Method Parameters
Code Examples
Successful Response
Returned Data
Key result. Object of type
sale_order_shipment_crm_simple
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: read access permission for the delivery order is required
This method retrieves brief information about the delivery.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
sale_order_shipment.id
Delivery identifier
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
-d '{"id":4077}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.delivery.get
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"id":4077,"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.delivery.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.delivery.get'
, {
id
:
4077
,
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.item.delivery.get'
,
[
'id'
=>
4077
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
'Error getting delivery item: '
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
'crm.item.delivery.get'
, {
id
:
4077
,
},
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
log
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
'crm.item.delivery.get'
,
[
'id'
=>
4077
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
"id"
:
4077
,
"accountNumber"
:
"3657/2"
,
"priceDelivery"
:
79.99
,
"currency"
:
"USD"
,
"deducted"
:
"N"
,
"dateDeducted"
:
null
,
"deliveryId"
:
228
,
"deliveryName"
:
"Uber Taxi (Cargo)"
}
,
"time"
:
{
"start"
:
1716369295.614557
,
"finish"
:
1716369296.143089
,
"duration"
:
0.5285320281982422
,
"processing"
:
0.2371680736541748
,
"date_start"
:
"2024-05-22T12:14:55+02:00"
,
"date_finish"
:
"2024-05-22T12:14:56+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
sale_order_shipment_crm_simple
Object containing brief information about the delivery
time
time
Information about the request execution time
Key result. Object of type
Key result. Object of type
sale_order_shipment_crm_simple
sale_order_shipment_crm_simple
Name
type
Description
id
sale_order_shipment.id
Delivery identifier
accountNumber
string
System delivery number
deducted
string
Indicates whether the delivery has been shipped.
Possible values:
Y
— yes (shipped)
N
— no (not shipped)
dateDeducted
datetime
Date of the shipped flag change
priceDelivery
double
Delivery cost
currency
string
Delivery currency
deliveryId
sale_delivery_service.ID
Delivery service identifier
deliveryName
string
Delivery service name
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
0
,
"error_description"
:
"Insufficient permissions"
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
0
Payment not found or access denied
100
Parameter id not specified
0
Other errors (e.g., fatal errors)
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
Get the list of deliveries for a CRM entity crm.item.delivery.list
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get List of Deliveries

---

## Get the list of deliveries for a CRM entity crm.item.delivery.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/delivery/crm-item-delivery-list

Get the list of deliveries for a CRM entity crm.item.delivery.list | Bitrix24 REST API and Marketplace Applications
Get the list of deliveries for a CRM entity crm.item.delivery.list
Get the list of deliveries for a CRM entity crm.item.delivery.list
Method Parameters
Code Examples
Successful Response
Returned Data
Error Handling
Possible Error Codes
Continue Learning
Scope:
crm
Who can execute the method: requires read access permission for the crm entity from which deliveries are selected.
This method retrieves the list of deliveries for a specific crm entity.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityId
*
integer
Identifier of the crm entity
entityTypeId
*
integer
Identifier of the
crm entity type
filter
object
Additional filter for cases when you need to get not all deliveries of the crm entity, but based on a more specific filter.
The format of the
filter
parameter corresponds to what is described in the
sale.shipment.list
method
order
object
The format of the
order
parameter corresponds to what is described in the
sale.shipment.list
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"entityId":13127,"entityTypeId":2,"filter":{"@id":[4077,4078]}}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.delivery.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"entityId":13127,"entityTypeId":2,"filter":{"@id":[4077,4078]},"auth":"**put_access_token_here**"}' \
https://**put_your_bitrix24_address**/rest/crm.item.delivery.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.item.delivery.list'
,
{
entityId
:
13127
,
entityTypeId
:
2
,
filter
: {
"@id"
: [
4077
,
4078
]
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.item.delivery.list'
, {
entityId
:
13127
,
entityTypeId
:
2
,
filter
: {
"@id"
: [
4077
,
4078
]
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.delivery.list'
, {
entityId
:
13127
,
entityTypeId
:
2
,
filter
: {
"@id"
: [
4077
,
4078
]
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
'crm.item.delivery.list'
,
[
'entityId'
=>
13127
,
'entityTypeId'
=>
2
,
'filter'
=> [
'@id'
=> [
4077
,
4078
]
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
'Error fetching delivery list: '
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
'crm.item.delivery.list'
, {
entityId
:
13127
,
entityTypeId
:
2
,
filter
: {
"@id"
: [
4077
,
4078
]
},
},
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
log
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
'crm.item.delivery.list'
,
[
'entityId'
=>
13127
,
'entityTypeId'
=>
2
,
'filter'
=> [
"@id"
=> [
4077
,
4078
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
Successful Response
Successful Response
HTTP status:
200
{
"result"
:
[
{
"id"
:
4077
,
"accountNumber"
:
"3657\/2"
,
"deducted"
:
"N"
,
"dateDeducted"
:
null
,
"deliveryId"
:
228
,
"priceDelivery"
:
79.99
,
"currency"
:
"USD"
,
"deliveryName"
:
"Uber Taxi (Cargo)"
}
,
{
"id"
:
4078
,
"accountNumber"
:
"3657\/3"
,
"deducted"
:
"N"
,
"dateDeducted"
:
null
,
"deliveryId"
:
228
,
"priceDelivery"
:
79.99
,
"currency"
:
"USD"
,
"deliveryName"
:
"Uber Taxi (Cargo)"
}
]
,
"time"
:
{
"start"
:
1716369036.246855
,
"finish"
:
1716369036.734466
,
"duration"
:
0.4876110553741455
,
"processing"
:
0.18442106246948242
,
"date_start"
:
"2024-05-22T12:10:36+02:00"
,
"date_finish"
:
"2024-05-22T12:10:36+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
sale_order_shipment_crm_simple
Array of objects containing brief information about the selected deliveries
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
0
,
"error_description"
:
"Insufficient permissions"
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
0
Access denied
100
Required fields not provided
0
Other errors (e.g., fatal errors)
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
Get Delivery Information by ID crm.item.delivery.get
Copied
Was the article helpful?
Yes
No
Previous
Get Delivery Information by ID
Next
Overview of Methods

---

