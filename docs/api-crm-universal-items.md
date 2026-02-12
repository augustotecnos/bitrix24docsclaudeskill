---
description: 'CRM Universal Items API: Generic CRUD for any CRM entity type'
methods:
- crm.activity.
- crm.category.list
- crm.company.fields
- crm.contact.fields
- crm.deal.fields
- crm.item.
- crm.item.add
- crm.item.batchImport
- crm.item.delete
- crm.item.details.configuration.
- crm.item.details.configuration.forceCommonScopeForAll
- crm.item.details.configuration.get
- crm.item.details.configuration.reset
- crm.item.details.configuration.set
- crm.item.fields
- crm.item.get
- crm.item.import
- crm.item.list
- crm.item.payment.
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
pages: 21
title: 'CRM Universal Items API: Generic CRUD for any CRM entity type'
---
# CRM Universal Items API: Generic CRUD for any CRM entity type
> CRM Universal Items API: Generic CRUD for any CRM entity type
> **21 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Universal Methods for Core Elements](#universal-methods-for-core-elements)
- [Invoices: Overview of Methods](#invoices-overview-of-methods)
- [Create a new CRM entity crm.item.add](#create-a-new-crm-entity-crmitemadd)
- [Update CRM Item: crm.item.update](#update-crm-item-crmitemupdate)
- [Get Item by Id crm.item.get](#get-item-by-id-crmitemget)
- [Get a list of crm.item.list elements](#get-a-list-of-crmitemlist-elements)
- [Delete CRM Item - crm.item.delete](#delete-crm-item---crmitemdelete)
- [Get Fields of CRM Item <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-dvfugi04">crm.item.fields</code>](#get-fields-of-crm-item-code-classyfm-clipboard-inl)
- [CRM Object Fields](#crm-object-fields)
- [Overview of CRM Object Events](#overview-of-crm-object-events)
- [Event for Creating a Custom Type CRM Object onCrmDynamicItemAdd](#event-for-creating-a-custom-type-crm-object-oncrmd)
- [Event for updating a custom type CRM object onCrmDynamicItemUpdate](#event-for-updating-a-custom-type-crm-object-oncrmd)
- [Event for Deleting a Custom CRM Object onCrmDynamicItemDelete](#event-for-deleting-a-custom-crm-object-oncrmdynami)
- [Overview of CRM Custom Type Events](#overview-of-crm-custom-type-events)
- [Event for Adding Custom CRM Type onCrmTypeAdd](#event-for-adding-custom-crm-type-oncrmtypeadd)
- [Event for updating custom CRM type onCrmTypeUpdate](#event-for-updating-custom-crm-type-oncrmtypeupdate)
- [Event on Deleting Custom CRM Type onCrmTypeDelete](#event-on-deleting-custom-crm-type-oncrmtypedelete)
- [Data Import into CRM](#data-import-into-crm)
- [Import a single record crm.item.import](#import-a-single-record-crmitemimport)
- [Import a Batch of CRM Records crm.item.batchImport](#import-a-batch-of-crm-records-crmitembatchimport)
- [Widgets Embedded in the Interface of Custom CRM Object Types](#widgets-embedded-in-the-interface-of-custom-crm-ob)

---

## Universal Methods for Core Elements

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/index

Universal Methods for Core Elements | Bitrix24 REST API and Marketplace Applications
Features of Working with Field Names
Universal Methods for Core Elements
Features of Working with Field Names
Binding to Requisites
Starting from crm 21.800.0
REST Methods
Events on SPA Elements
Continue Learning
We are still updating this page
Some data may be missing — we will fill it in shortly.
The methods
crm.item.*
provide capabilities for managing various CRM entities such as leads, deals, contacts, companies, invoices, estimates, and SPA elements. They allow you to retrieve fields, add, update, delete, and get lists of elements.
Features of Working with Field Names
Features of Working with Field Names
In the database, the names of element fields are stored in
UPPER_CASE
format. However, when working through REST, we convert them to
camelCase
. For example, the field
ASSIGNED_BY_ID
is transformed into
assignedById
.
Custom field names, in addition to the
_
character and letters, can contain numbers. Typically, they are separated, for instance, the field
UF_CRM_10_5186744711
is converted to
ufCrm10_5186744711
.
To make the code more readable, underscores between numbers are retained, while others are removed.
Problems arise when letters and numbers in a field are mixed together. For example,
UF_CRM_10_DIGIT10
is transformed into
ufCrm10Digit10
. When converting back, there is no way to determine whether the original field was named
UF_CRM_10_DIGIT10
or
UF_CRM_10_DIGIT_10
.
To resolve such conflicts, starting from version
CRM 21.1800.0
, a mechanism for preliminary analysis of field names was implemented. If conflicts are detected, the field name is not converted to
camelCase
and remains as is.
UPPER_CASE
camelCase
UF_CRM_3_DIGIT
ufCrm3Digit
UF_CRM_3_DIGIT10
ufCrm_3_DIGIT10
UF_CRM_3_DIGIT_10
ufCrm_3_DIGIT_10
UF_CRM_3_1747309727
ufCrm3_1747309727
UF_CRM_1747309879
ufCrm_1747309879
Starting from version
CRM 25.0.0
, a parameter
useOriginalUfNames
was added to the methods crm.item.* to control the format of custom field names in requests and responses:
Y
— original custom field names, for example
UF_CRM_2_1639669411830
N
— custom field names in camelCase, for example
ufCrm2_1639669411830
By default, custom field names are passed and returned in
camelCase
.
Binding to Requisites
Binding to Requisites
To manage the binding of requisites, you can use the methods
crm.requisite.link.*
.
Starting from crm 21.800.0
Starting from crm 21.800.0
Support for parent fields when working with CRM elements is introduced.
Each field has a code
parentId + {parentEntityTypeId}
.
The
fields
method in the field list will return information about fields with parents.
The
get
method will return the values of parent fields.
The
list
method will filter, sort, and include values of parent fields in the selection.
The
add
and
update
methods will support changes to the values of these fields.
REST Methods
REST Methods
Get Fields of CRM Item `crm.item.fields`
Create a new CRM entity crm.item.add
Update CRM Item: crm.item.update
Delete CRM Item - crm.item.delete
Get a list of crm.item.list elements
Events on SPA Elements
Events on SPA Elements
Event for Creating a Custom Type CRM Object onCrmDynamicItemAdd
Event for updating a custom type CRM object onCrmDynamicItemUpdate
Event for Deleting a Custom CRM Object onCrmDynamicItemDelete
Continue Learning
Continue Learning
How to Create a Custom Field in a SPA
Copied
Was the article helpful?
Yes
No
Previous
Determine the Current CRM Operating Mode
Next
Universal Methods for Invoices

---

## Invoices: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/invoice

Invoices: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Invoices: Overview of Methods
Invoices: Overview of Methods
Linking Invoices with Other CRM Objects
Invoice Detail Form
Widgets
Embedding Locations for New Invoices
Overview of Methods and Events
Main
Custom Fields
Product Items
Payments
Managing Invoice Detail Form Settings
An invoice is the final stage of a deal. It is created when all discussions are complete and the terms of the agreement are agreed upon. Multiple invoices can be created for different products and services within a single deal.
An invoice can be generated from a template and sent to the client as a document. In the invoice detail form, you can:
Manage the sales process of a product or service
Track the stages of working with the invoice
Accept online payments
Quick navigation:
all methods and events
User documentation:
New invoices in CRM
Linking Invoices with Other CRM Objects
Linking Invoices with Other CRM Objects
Deal.
Pass the deal ID in the
parentId2
parameter to link the new invoice with the deal.
Estimate.
Pass the estimate ID in the
parentId7
parameter to link the new invoice with the estimate.
Client.
This field in the invoice detail form consists of the associated company and contacts. All activities related to calls, e-mails, and chats with the contact or company will be saved in the invoice detail form. There can be one company in the field, and it is referenced through the invoice field
companyId
. Multiple contacts can be specified, and interactions with them are managed through the
contactIds
field; pass an array of contact IDs in this field.
Products.
Adding, modifying, and deleting product items in invoices can be done through the group of methods
crm.item.productrow.*
.
Payments.
Adding, modifying, and deleting payment documents in invoices can be done through the group of methods
crm.item.payment.*
.
Your Company Details.
Specify your company ID in the
mycompanyId
field so that its details are automatically used in documents. You can obtain your company ID using the method
crm.item.list
for the companies object with a filter on the
isMyCompany
field.
BX24
.
callMethod
(
'crm.item.list'
,
{
entityTypeId
:
4
,
filter
: {
"isMyCompany"
:
"Y"
,
},
},
(
result
) =>
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
return
;
}
console
.
info
(result.
data
());
},
);
User Documentation
How to accept payments from clients and work with receipts in Bitrix24
How to add products to deals, leads, and estimates
How to use your company details
Invoice Detail Form
Invoice Detail Form
The main workspace in invoices is the General tab of the detail form. It consists of two parts:
The left part contains fields with information. If the system fields are insufficient, you can create your own custom fields. They allow you to store information in various data formats: string, number, link, address, and others. To create, modify, retrieve, or delete custom fields for invoices, use the group of methods
userfieldconfig.*
.
The right part contains the invoice timeline. In it, you can create, edit, filter, and delete CRM activities — the group of methods
crm.activity.*
, and timeline records — the group of methods
crm.timeline.*
.
The parameters of the invoice detail form can be managed through the group of methods
crm.item.details.configuration.*
.
User Documentation
CRM Detail Form: Features and Settings
System Fields in CRM
Custom Fields in CRM
Timeline in CRM Entity
Widgets
Widgets
You can embed an application into the invoice detail form. This allows you to use the application without leaving the invoice detail form.
There are two embedding scenarios:
Use special
embedding locations
. For example, by creating your own tab.
Create a
custom field
where the interface of your application will be loaded.
Embedding Locations for New Invoices
Embedding Locations for New Invoices
CRM_SMART_INVOICE_DETAIL_TAB
— a tab in the detailed view of the CRM entity
CRM_SMART_INVOICE_DETAIL_ACTIVITY
— a button above the timeline of the detail form
CRM_SMART_INVOICE_DETAIL_TOOLBAR
— an item in the dropdown menu of the top button in the detail form
CRM_SMART_INVOICE_DOCUMENTGENERATOR_BUTTON
— an item in the dropdown menu of the document generator
CRM_SMART_INVOICE_LIST_MENU
— an item in the context menu in the list of entities
CRM_SMART_INVOICE_LIST_TOOLBAR
— an item in the dropdown menu above the list of entities
CRM_SMART_INVOICE_TIMELINE_MENU
— an item in the context menu of an activity in the detail form
CRM_SMART_INVOICE_ROBOT_DESIGNER_TOOLBAR
— an item in the dropdown menu of the top button of the robot designer
Typical use-cases and scenarios
Widget Embedding Mechanism
Embed a Widget in the CRM Detail Form
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can execute the method: depending on the method
Main
Main
CRM Object Identifier
entityTypeId
—
31
Methods
Events
crm.item.add
Creates a new CRM entity
crm.item.update
Updates an entity
crm.item.get
Returns an entity by Id
crm.item.list
Returns a list of entities by filter
crm.item.delete
Deletes an entity
crm.item.fields
Returns the fields of an entity
onCrmDynamicItemAdd
When a custom type CRM object is created
onCrmDynamicItemDelete
When a custom type CRM object is deleted
onCrmDynamicItemUpdate
When a custom type CRM object is modified
Custom Fields
Custom Fields
CRM Object Identifier
entityId
—
CRM_SMART_INVOICE
Method
Description
userfieldconfig.add
Creates a custom field
userfieldconfig.update
Modifies field settings
userfieldconfig.get
Returns the settings of a custom field by identifier
userfieldconfig.getTypes
Returns the set of available types of custom fields for the module
userfieldconfig.list
Returns a list of custom field settings
userfieldconfig.delete
Deletes a custom field
Product Items
Product Items
CRM Object Identifier
ownerType
—
SI
Method
Description
crm.item.productrow.add
Adds a product item
crm.item.productrow.update
Updates a product item
crm.item.productrow.get
Retrieves information about a product item by id
crm.item.productrow.set
Associates a product item with a CRM object
crm.item.productrow.list
Retrieves a list of product items
crm.item.productrow.getAvailableForPayment
Retrieves a list of unpaid products
crm.item.productrow.delete
Deletes a product item
crm.item.productrow.fields
Retrieves a list of product item fields
Payments
Payments
CRM Object Identifier
entityTypeId
—
31
Method
Description
crm.item.payment.add
Creates a payment for a CRM object
crm.item.payment.update
Modifies the set of payment fields
crm.item.payment.get
Retrieves brief information about a payment
crm.item.payment.list
Retrieves a list of payments for a specific CRM object
crm.item.payment.delete
Deletes a payment
crm.item.payment.pay
Changes the payment status to "Paid"
crm.item.payment.unpay
Changes the payment status to "Unpaid"
Product Items in Payment
Product Items in Payment
Method
Description
crm.item.payment.product.add
Adds a product item to the payment
crm.item.payment.product.list
Retrieves a list of product items in the payment
crm.item.payment.product.delete
Deletes a product item from the payment
crm.item.payment.product.setQuantity
Changes the quantity of a product in the payment item
Delivery in Payment
Delivery in Payment
Method
Description
crm.item.payment.delivery.add
Adds a delivery item to the payment
crm.item.payment.delivery.list
Retrieves a list of delivery items for a specific payment
crm.item.payment.delivery.delete
Deletes a delivery item from the payment
crm.item.payment.delivery.setDelivery
Reassociates the delivery item with another delivery document
Managing Invoice Detail Form Settings
Managing Invoice Detail Form Settings
CRM Object Identifier
entityTypeId
—
31
crm.item.details.configuration.forceCommonScopeForAll
Sets a common detail form for all users
crm.item.details.configuration.get
Retrieves the parameters of the detail form for entities
crm.item.details.configuration.reset
Resets the parameters of the detail form for entities
crm.item.details.configuration.set
Sets the parameters of the detail form for entities
Copied
Was the article helpful?
Yes
No
Previous
Universal Methods for Core Elements
Next
Overview of methods

---

## Create a new CRM entity crm.item.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/crm-item-add

Create a new CRM entity crm.item.add | Bitrix24 REST API and Marketplace Applications
Create a new CRM entity crm.item.add
Create a new CRM entity crm.item.add
Method Parameters
Parameter fields
Code Examples
Response Processing
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with the "add" access permission for the CRM object
This method is a universal way to create objects in CRM. With it, you can create various types of objects, such as deals, contacts, companies, and others.
To create an object, you need to pass the appropriate parameters, including the object type and its information: title, description, contact details, and other specifics.
After a successful request, a new object is created.
This method provides a flexible way to automate the process of creating objects and integrate CRM with other systems.
When creating an entity, a standard series of checks, modifications, and automatic actions are performed:
access permissions are checked
required fields are validated
required fields dependent on stages are validated
field values are checked for correctness
default values are assigned to fields
automation rules are triggered after saving
Next, we will look in detail at how to use this method and what parameters need to be passed.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
whose element we want to create
fields
*
object
Object format.
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where
field_n
— field name
value_n
— field value
Each CRM entity type has its own set of fields. This means that the set of fields for creating a Lead does not have to match the set of fields for creating a Contact or SPA.
The list of available fields for each entity type is described
below
.
An incorrect field in
fields
will be ignored
useOriginalUfNames
boolean
Parameter to control the format of custom field names in the request and response.
Possible values:
Y
— original names of custom fields, for example
UF_CRM_2_1639669411830
N
— custom field names in camelCase, for example
ufCrm2_1639669411830
Default is
N
Parameter fields
Parameter fields
Required parameters are marked with *
Lead
Deal
Contact
Company
Estimate
Invoice
Smart Process
CRM object identifier
entityTypeId:
1
Name
type
Description
title
string
Title of the entity.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the element
For example, for a lead with
id = 13
— 'Lead #13'
honorific
crm_status
String identifier of the lead's honorific (for example,
'HNR_RU_1' = 'Mr.'
).
The list of available honorifics can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "HONOFIRIC" }
.
Default is
null
name
string
First name.
Default is
null
secondName
string
Middle name.
Default is
null
lastName
string
Last name.
Default is
null
birthdate
date
Date of birth.
Default is
null
companyTitle
string
Company name.
Default is
null
sourceId
crm_status
String identifier of the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
Default is the first available source
sourceDescription
text
Additional information about the source.
Default is
null
stageId
crm_status
String identifier of the entity's stage.
For example,
'NEW' = 'Unprocessed'
.
The list of available stages can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "STATUS" }
Default is the first available stage
statusDescription
text
Additional information about the stage.
Default is
null
post
string
Position.
Default is
null
currencyId
crm_currency
Identifier of the entity's currency.
Default is the default currency
isManualOpportunity
boolean
Mode of calculating the amount. Possible values:
Y
— manual
N
— automatic
Default is
N
opportunity
double
Amount.
Default is
null
opened
boolean
Is the entity available to everyone? Possible values:
Y
— yes
N
— no
Default is
Y
. The default value can be changed in CRM settings
comments
text
Comment.
Default is
null
assignedById
user
Identifier of the user responsible for the entity.
Default is the identifier of the user calling the method
companyId
crm_company
Identifier of the company linked to the entity.
The list of companies can be obtained using the method
crm.item.list
with
entityTypeId = 4
.
Default is
null
contactId
crm_contact
Identifier of the contact linked to the entity.
The list of contacts can be obtained using the method
crm.item.list
with
entityTypeId = 3
.
Default is
null
contactIds
crm_contact[]
List of identifiers of contacts linked to the entity.
The list of contacts can be obtained using the method
crm.item.list
with
entityTypeId = 3
.
Default is
null
originatorId
string
External source.
Default is
null
originId
string
Identifier of the entity in the external source.
Default is
null
webformId
integer
Identifier of the CRM Form.
Default is
null
observers
user[]
Array of user identifiers who will be Observers in the entity.
Default is
null
utmSource
string
Advertising system. For example: Google Ads, Facebook Ads, and others.
Default is
null
utmMedium
string
Type of traffic. Possible values:
CPC — ads
CPM — banners
Default is
null
utmCampaign
string
Identifier of the advertising campaign.
Default is
null
utmContent
string
Content of the campaign. For example, for contextual ads.
Default is
null
utmTerm
string
Search term of the campaign. For example, keywords for contextual advertising.
Default is
null
ufCrm...
crm_userfield
Custom field.
Read about custom fields in the section
Custom Fields in CRM
Values of multiple fields are passed as an array.
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
fm
multifield[]
Array of multifields.
More about multifields can be read in the section
crm_multifield
Structure of a multifield:
typeId
— Type of multifield
valueType
— Type of value
value
— Value
Example:
fm: [
{
"valueType"
:
"WORK"
,
"value"
:
"+19999999999"
,
"typeId"
:
"PHONE"
},
{
"valueType"
:
"WORK"
,
"value"
:
"bitrix@bitrix.com"
,
"typeId"
:
"EMAIL"
}
]
Default is
null
CRM object identifier
entityTypeId:
2
Name
type
Description
title
string
Title of the entity
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the entity
For example, for a deal with
id = 13
=> 'Deal #13'
typeId
crm_status
String identifier of the entity type.
For example, for a deal:
'SALE' = 'Sale'
The list of available entity types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "DEAL_TYPE" }
By default — the first available entity type
categoryId
integer
Identifier of the
direction
(funnel) of the deal.
By default —
0
(general)
stageId
crm_status
String identifier of the entity stage.
For example,
'NEW' = 'Not Processed'
.
The list of available stages can be obtained using
crm.status.list
with the filter:
If the deal is in the general funnel (direction) —
{ ENTITY_ID: "DEAL_STAGE" }
If the deal is not in the general funnel (direction) —
{ ENTITY_ID: "DEAL_STAGE_{categoryId}" }
, where
categoryId
is the identifier of the funnel (
direction
) of the deal
By default — the first available stage relative to the funnel
isRecurring
boolean
Is the deal recurring? Possible values:
Y
— yes
N
— no
By default —
N
probability
integer
Probability %.
By default —
null
currencyId
crm_currency
Identifier of the currency of the entity.
By default — default currency
isManualOpportunity
boolean
Mode of calculating the amount. Possible values:
Y
— manual
N
— automatic
By default —
N
opportunity
double
Amount.
By default —
null
taxValue
double
Tax amount.
By default —
null
companyId
crm_company
Identifier of the company linked to the entity.
The list of companies can be obtained using the method
crm.item.list
with
entityTypeId = 4
.
By default —
null
contactId
crm_contact
Identifier of the contact linked to the entity.
The list of contacts can be obtained using the method
crm.item.list
with
entityTypeId = 3
.
By default —
null
contactIds
crm_contact[]
List of identifiers of contacts linked to the entity.
The list of contacts can be obtained using the method
crm.item.list
with
entityTypeId = 3
.
By default —
null
quoteId
crm_quote
Identifier of the estimate that will be linked to the deal
begindate
date
Start date of the entity.
By default — creation date
closedate
date
End date of the entity.
By default — creation date + 7 days
opened
boolean
Is the entity available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
comments
text
Comment.
By default —
null
assignedById
user
Identifier of the person responsible for the entity.
By default — identifier of the user calling the method
sourceId
crm_status
String identifier of the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
By default — the first available source
sourceDescription
text
Additional information about the source.
By default —
null
leadId
crm_lead
Identifier of the lead based on which the entity is created.
By default —
null
additionalInfo
string
Additional information.
By default —
null
originatorId
string
External source.
By default —
null
originId
string
Identifier of the entity in the external source.
By default —
null
observers
user[]
Array of user identifiers who will be Observers in the entity.
By default —
null
locationId
location
Identifier of the location. System field.
By default —
null
utmSource
string
Advertising system. Google Ads, Google AdWords, and others.
By default —
null
utmMedium
string
Type of traffic. Possible values:
CPC — ads
CPM — banners
By default —
null
utmCampaign
string
Identifier of the advertising campaign.
By default —
null
utmContent
string
Content of the campaign. For example, for contextual ads.
By default —
null
utmTerm
string
Search condition of the campaign. For example, keywords for contextual advertising.
By default —
null
ufCrm...
crm_userfield
User-defined field. See section
Custom Fields in CRM
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
3
Name
type
Description
honorific
crm_status
String identifier of the contact's salutation.
For example,
'HNR_US_1' = 'Mr.'
.
The list of available salutations can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "HONOFIRIC" }
.
By default —
null
name
string
First name.
By default —
null
secondName
string
Middle name.
By default —
null
lastName
string
Last name.
By default —
null
photo
file
Photograph.
By default —
null
birthdate
date
Date of birth.
By default —
null
typeId
crm_status
String identifier of the entity type.
For example, for a deal:
'SALE' = 'Sale'
.
The list of available entity types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "CONTACT_TYPE" }
.
By default — the first available entity type
sourceId
crm_status
String identifier of the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
By default — the first available source
sourceDescription
text
Additional information about the source.
By default —
null
post
string
Position.
By default —
null
comments
text
Comment.
By default —
null
opened
boolean
Is the entity available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
export
boolean
Is the contact included in the export?
By default —
Y
assignedById
user
Identifier of the person responsible for the entity.
By default — identifier of the user calling the method
companyId
crm_company
Identifier of the company linked to the entity.
The list of companies can be obtained using the method
crm.item.list
with
entityTypeId = 4
.
By default —
null
companyIds
crm_company
Array of identifiers of companies that will be linked to the entity
leadId
crm_lead
Identifier of the lead based on which the entity is created.
By default —
null
originatorId
string
External source.
By default —
null
originId
string
Identifier of the entity in the external source.
By default —
null
originVersion
string
Version of the original.
By default —
null
observers
user[]
Array of user identifiers who will be Observers in the entity.
By default —
null
utmSource
string
Advertising system. Google Ads, Google AdWords, and others.
By default —
null
utmMedium
string
Type of traffic. Possible values:
CPC — ads
CPM — banners
By default —
null
utmCampaign
string
Identifier of the advertising campaign.
By default —
null
utmContent
string
Content of the campaign. For example, for contextual ads.
By default —
null
utmTerm
string
Search condition of the campaign. For example, keywords for contextual advertising.
By default —
null
ufCrm...
crm_userfield
User-defined field. See section
Custom Fields in CRM
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
fm
multifield[]
Array of multi-fields.
More about multi-fields can be read in section
crm_multifield
Structure of a multi-field:
typeId
— Type of the multi-field
valueType
— Type of value
value
— Value
Example:
fm: [
{
"valueType"
:
"WORK"
,
"value"
:
"+19999999999"
,
"typeId"
:
"PHONE"
},
{
"valueType"
:
"WORK"
,
"value"
:
"bitrix@bitrix.com"
,
"typeId"
:
"EMAIL"
}
]
By default —
null
CRM object identifier
entityTypeId:
4
Name
type
Description
title
string
Name of the entity.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the entity
For example, for a company with
id = 13
=> 'Company #13'
typeId
crm_status
String identifier of the entity type.
For example, for a deal:
'SALE' = 'Sale'
.
The list of available entity types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "COMPANY_TYPE" }
.
By default — the first available entity type
logo
file
Logo.
By default —
null
bankingDetails
string
Banking details.
By default —
null
industry
crm_status
String identifier of the industry type.
For example,
'IT' = 'Information Technology'
.
The list of available industry types can be obtained using the method
crm.status.list
with the filter
{ ENTITY_ID: "INDUSTRY"}
.
By default — the first available industry type
employees
crm_status
String identifier of the number of employees type.
The value is taken from the available list, for example,
'EMPLOYEES_1' = 'less than 50'
.
The list of available employee counts can be obtained using the method
crm.status.list
with the filter
{ ENTITY_ID: "EMPLOYEES" }
.
By default — the first available employee count type
currencyId
crm_currency
Identifier of the entity's currency.
By default — default currency
revenue
double
Annual revenue.
By default —
0
opened
boolean
Is the entity available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
comments
text
Comment.
By default —
null
isMyCompany
boolean
Is the company my company?
By default —
N
assignedById
user
Identifier of the person responsible for the entity.
By default — identifier of the user calling the method
contactIds
crm_contact[]
List of contact identifiers linked to the entity.
The list of contacts can be obtained using the method
crm.item.list
with
entityTypeId = 3
.
By default —
null
leadId
crm_lead
Identifier of the lead based on which the entity is created.
By default —
null
originatorId
string
External source.
By default —
null
originId
string
Identifier of the entity in the external source.
By default —
null
originVersion
string
Version of the original.
By default —
null
observers
user[]
Array of user identifiers who will be Observers in the entity.
By default —
null
utmSource
string
Advertising system. Google Ads, Facebook Ads, and others.
By default —
null
utmMedium
string
Type of traffic. Possible values:
CPC — ads
CPM — banners
By default —
null
utmCampaign
string
Identifier of the advertising campaign.
By default —
null
utmContent
string
Content of the campaign. For example, for contextual ads.
By default —
null
utmTerm
string
Search condition of the campaign. For example, keywords for contextual advertising.
By default —
null
ufCrm...
crm_userfield
User-defined field. See section
Custom Fields in CRM
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
fm
multifield[]
Array of multifields.
More about multifields can be read in section
crm_multifield
Structure of a multifield:
typeId
— Type of multifield
valueType
— Type of value
value
— Value
Example:
fm: [
{
"valueType"
:
"WORK"
,
"value"
:
"+19999999999"
,
"typeId"
:
"PHONE"
},
{
"valueType"
:
"WORK"
,
"value"
:
"bitrix@bitrix.com"
,
"typeId"
:
"EMAIL"
}
]
By default —
null
CRM object identifier
entityTypeId:
7
Name
type
Description
title
string
Name of the entity.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the entity
For example, for an estimate with
id = 13
=> 'Estimate #13'
assignedById
user
Identifier of the person responsible for the entity.
By default — identifier of the user calling the method
opened
boolean
Is the entity available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
content
text
Content.
By default —
null
terms
text
Terms.
By default —
null
comments
text
Comment.
By default —
null
dealId
crm_deal
Identifier of the linked deal.
By default —
null
leadId
crm_lead
Identifier of the lead based on which the entity is created.
By default —
null
storageTypeId
integer
Identifier of the storage type. Possible values:
1
— file
2
— WebDAV
3
— Drive
By default:
If the
disk
module is installed -> Drive
If the
webdav
module is installed -> WebDAV
File
storageElementIds
integer
Array of files.
By default —
null
webformId
integer
Identifier of the CRM Form.
By default —
null
companyId
crm_company
Identifier of the company linked to the entity.
The list of companies can be obtained using the method
crm.item.list
with
entityTypeId = 4
.
By default —
null
contactId
crm_contact
Identifier of the contact linked to the entity.
The list of contacts can be obtained using the method
crm.item.list
with
entityTypeId = 3
By default —
null
contactIds
crm_contact[]
List of contact identifiers linked to the entity.
The list of contacts can be obtained using the method
crm.item.list
with
entityTypeId = 3
.
By default —
null
locationId
location
Identifier of the location. System field.
By default —
null
currencyId
crm_currency
Identifier of the entity's currency.
By default — default currency
isManualOpportunity
boolean
Mode of calculating the amount.
Y
— manual
N
— automatic
By default —
N
opportunity
double
Amount.
By default —
null
taxValue
double
Tax amount.
By default —
null
stageId
crm_status
String identifier of the entity's stage.
For example,
'DRAFT' = 'New'
.
The list of available stages can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "QUOTE_STATUS" }
.
By default — the first available stage
begindate
date
Start date of the entity.
By default — creation date of the entity
closedate
date
End date of the entity.
By default — creation date of the entity + 7 days
actualDate
date
Valid until.
By default — creation date of the entity + 7 days
mycompanyId
crm_company
Identifier of my company.
By default — identifier of the first available "my" company
utmSource
string
Advertising system. Google Ads, Facebook Ads, and others.
By default —
null
utmMedium
string
Type of traffic.
CPC — ads
CPM — banners
By default —
null
utmCampaign
string
Identifier of the advertising campaign.
By default —
null
utmContent
string
Content of the campaign. For example, for contextual ads.
By default —
null
utmTerm
string
Search condition of the campaign. For example, keywords for contextual advertising.
By default —
null
ufCrm...
crm_userfield
User-defined field. See section
Custom Fields in CRM
.
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
31
Name
type
Description
title
string
Name of the entity.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the entity
For example, for an invoice with
id = 13
=> 'Invoice #13'
xmlId
string
External code.
By default —
null
assignedById
user
Identifier of the person responsible for the entity.
By default — identifier of the user calling the method
opened
boolean
Indicates whether the entity is accessible to everyone. Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
webformId
integer
Identifier of the CRM Form.
By default —
null
begindate
date
Start date of the entity.
By default — creation date of the entity
closedate
date
End date of the entity.
By default — creation date of the entity + 7 days
companyId
crm_company
Identifier of the company linked to the entity.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
.
By default —
null
contactId
crm_contact
Identifier of the contact linked to the entity.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
contactIds
crm_contact[]
List of identifiers of contacts linked to the entity.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
observers
user[]
Array of user identifiers who will be Observers in the entity.
By default —
null
stageId
crm_status
String identifier of the stage of the entity.
For example,
'DT31_13:N' = 'New'
.
The list of available stages can be found using
crm.status.list
, applying the filter:
{ ENTITY_ID: "SMART_INVOICE_STAGE_{categoryId}" }
, where
categoryId
— identifier of the default invoice funnel. It can be found using
crm.category.list
with
entityTypeId = 31
.
By default — the first available stage
sourceId
crm_status
String identifier of the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be found using
crm.status.list
applying the filter
{ ENTITY_ID: "SOURCE" }
.
By default — the first available source
sourceDescription
text
Additional information about the source.
By default —
null
currencyId
crm_currency
Identifier of the currency of the entity.
By default — default currency
isManualOpportunity
boolean
Mode of calculating the amount. Possible values:
Y
— manual
N
— automatic
By default —
N
opportunity
double
Amount.
By default —
null
taxValue
double
Tax amount.
By default —
null
mycompanyId
crm_company
Identifier of my company.
By default — identifier of the first available "my" company
comments
text
Comment.
By default —
null
locationId
location
Identifier of the location. System field.
By default —
null
ufCrm...
crm_userfield
Custom field. See section
Custom Fields in CRM
.
Values of multiple fields are passed as an array
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
can be obtained using the
crm.type.list
method or created using the
crm.type.add
method.
Name
type
Description
title
string
Name of the entity.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the smart process
id
— identifier of the entity
For example, for the smart process element "HR" with
id = 13
=> 'HR #13'
xmlId
string
External code.
By default —
null
assignedById
user
Identifier of the person responsible for the entity.
By default — identifier of the user calling the method
opened
boolean
Indicates whether the entity is accessible to everyone.
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
webformId
integer
Identifier of the CRM Form.
By default —
null
begindate
date
Start date of the entity.
Available only when the
isBeginCloseDatesEnabled
setting is enabled for the corresponding smart process.
By default — creation date of the entity
closedate
date
End date of the entity.
Available only when the
isBeginCloseDatesEnabled
setting is enabled for the corresponding smart process.
By default — creation date of the entity + 7 days
companyId
crm_company
Identifier of the company linked to the entity.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
.
Available only when the
isClientEnabled
setting is enabled for the corresponding smart process.
By default —
null
contactId
crm_contact
Identifier of the contact linked to the entity.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
Available only when the
isClientEnabled
setting is enabled for the corresponding smart process.
By default —
null
contactIds
crm_contact[]
List of identifiers of contacts linked to the entity.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
Available only when the
isClientEnabled
setting is enabled for the corresponding smart process.
By default —
null
observers
user[]
Array of user identifiers who will be Observers in the entity.
Available only when the
isObserversEnabled
setting is enabled for the corresponding smart process.
By default —
null
categoryId
crm_category
Identifier of the funnel of the smart process entity.
The list of available funnels can be found using the
crm.category.list
applying the corresponding
entityTypeId
stageId
crm_status
String identifier of the stage of the entity.
For example,
'DT1220_30:NEW' = 'Start'
.
The list of available stages can be found using
crm.status.list
applying the filter
{ ENTITY_ID: "DYNAMIC_{entityTypeId}_STAGE_{categoryId}" }
, where
entityTypeId
— identifier of the smart process type
categoryId
— identifier of the funnel (direction) of the smart process element
More about funnels (directions)
.
Available only when the
isStagesEnabled
setting is enabled for the corresponding smart process.
By default — the first available stage relative to the funnel
sourceId
crm_status
String identifier of the source. (for example,
'CALL' = 'Call'
).
The list of available sources can be found using
crm.status.list
applying the filter
{ ENTITY_ID: "SOURCE" }
.
Available only when the
isSourceEnabled
setting is enabled for the corresponding smart process.
By default — the first available source
sourceDescription
text
Additional information about the source.
Available only when the
isSourceEnabled
setting is enabled for the corresponding smart process.
By default —
null
currencyId
crm_currency
Identifier of the currency of the entity.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding smart process.
By default — default currency
isManualOpportunity
boolean
Mode of calculating the amount. Possible values:
Y
— manual
N
— automatic
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding smart process.
By default —
N
opportunity
double
Amount.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding smart process.
By default —
null
taxValue
double
Tax amount.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding smart process.
By default —
null
mycompanyId
crm_company
Identifier of my company.
Available only when the
isMycompanyEnabled
setting is enabled for the corresponding smart process.
By default — Identifier of the first available "my" company
ufCrm...
crm_userfield
Custom field. See section
Custom Fields in CRM
.
Values of multiple fields are passed as an array
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
Smart Process Settings
You can read more about managing smart process settings in
Smart Processes: Overview of Methods
Code Examples
Code Examples
How to Use Examples in Documentation
Example of creating a deal
cURL (Webhook)
cURL (OAuth)
BX24.js
PHP CRest
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"fields":{"title":"New deal (specifically for the REST methods example)","typeId":"SERVICE","categoryId":9,"stageId":"C9:UC_KN8KFI","isReccurring":"Y","probability":50,"currencyId":"USD","isManualOpportunity":"Y","opportunity":999.99,"taxValue":99.9,"companyId":5,"contactId":4,"contactIds":[4,5],"quoteId":7,"begindate":"formatDate(monthAgo)","closedate":"formatDate(twelveDaysInAdvance)","opened":"N","comments":"commentsExample","assignedById":6,"sourceId":"WEB","sourceDescription":"There should be additional description about the source","leadId":102,"additionalInfo":"There should be additional information","observers":[2,3],"utmSource":"google","utmMedium":"CPC","ufCrm_1721244707107":1111.1,"parentId1220":2}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"fields":{"title":"New deal (specifically for the REST methods example)","typeId":"SERVICE","categoryId":9,"stageId":"C9:UC_KN8KFI","isReccurring":"Y","probability":50,"currencyId":"USD","isManualOpportunity":"Y","opportunity":999.99,"taxValue":99.9,"companyId":5,"contactId":4,"contactIds":[4,5],"quoteId":7,"begindate":"formatDate(monthAgo)","closedate":"formatDate(twelveDaysInAdvance)","opened":"N","comments":"commentsExample","assignedById":6,"sourceId":"WEB","sourceDescription":"There should be additional description about the source","leadId":102,"additionalInfo":"There should be additional information","observers":[2,3],"utmSource":"google","utmMedium":"CPC","ufCrm_1721244707107":1111.1,"parentId1220":2},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.add
const
formatDate
= (
date
) => {
return
date.
toISOString
().
slice
(
0
,
10
);
};
const
day =
60
*
60
*
24
*
1000
;
const
now =
new
Date
();
const
twelveDaysInAdvance =
new
Date
(now.
getTime
() +
12
* day);
const
monthAgo =
new
Date
(now.
getTime
() -
30
* day);
const
commentsExample =
`
Example comment within the deal
[B]Bold text[/B]
[I]Italic[/I]
[U]Underlined[/U]
[S]Strikethrough[/S]
[B][I][U][S]Mix[/S][/U][/I][/B]
[LIST]
[*]List item #1
[*]List item #2
[*]List item #3
[/LIST]
[LIST=1]
[*]Numbered list item #1
[*]Numbered list item #2
[*]Numbered list item #3
[/LIST]
`
;
BX24
.
callMethod
(
'crm.item.add'
,
{
entityTypeId
:
2
,
fields
:
{
title
:
"New deal (specifically for the REST methods example)"
,
typeId
:
"SERVICE"
,
categoryId
:
9
,
stageId
:
"C9:UC_KN8KFI"
,
isReccurring
:
"Y"
,
probability
:
50
,
currencyId
:
"USD"
,
isManualOpportunity
:
"Y"
,
opportunity
:
999.99
,
taxValue
:
99.9
,
companyId
:
5
,
contactId
:
4
,
contactIds
: [
4
,
5
],
quoteId
:
7
,
begindate
:
formatDate
(monthAgo),
closedate
:
formatDate
(twelveDaysInAdvance),
opened
:
"N"
,
comments
: commentsExample,
assignedById
:
6
,
sourceId
:
"WEB"
,
sourceDescription
:
"There should be additional description about the source"
,
leadId
:
102
,
additionalInfo
:
"There should be additional information"
,
observers
: [
2
,
3
],
utmSource
:
"google"
,
utmMedium
:
"CPC"
,
ufCrm_1721244707107
:
1111.1
,
parentId1220
:
2
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
'crm.item.add'
,
[
'entityTypeId'
=>
2
,
'fields'
=> [
'title'
=>
"New deal (specifically for the REST methods example)"
,
'typeId'
=>
"SERVICE"
,
'categoryId'
=>
9
,
'stageId'
=>
"C9:UC_KN8KFI"
,
'isReccurring'
=>
"Y"
,
'probability'
=>
50
,
'currencyId'
=>
"USD"
,
'isManualOpportunity'
=>
"Y"
,
'opportunity'
=>
999.99
,
'taxValue'
=>
99.9
,
'companyId'
=>
5
,
'contactId'
=>
4
,
'contactIds'
=> [
4
,
5
],
'quoteId'
=>
7
,
'begindate'
=>
formatDate
(monthAgo),
'closedate'
=>
formatDate
(twelveDaysInAdvance),
'opened'
=>
"N"
,
'comments'
=>
$commentsExample
,
'assignedById'
=>
6
,
'sourceId'
=>
"WEB"
,
'sourceDescription'
=>
"There should be additional description about the source"
,
'leadId'
=>
102
,
'additionalInfo'
=>
"There should be additional information"
,
'observers'
=> [
2
,
3
],
'utmSource'
=>
"google"
,
'utmMedium'
=>
"CPC"
,
'ufCrm_1721244707107'
=>
1111.1
,
'parentId1220'
=>
2
,
],
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
$entityTypeId
=
1
;
// Example entity type ID
$fields
= [
'title'
=>
'New Item'
,
'createdTime'
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
'updatedTime'
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
'begindate'
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
'closedate'
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
// Add other necessary fields as required
];
$result
=
$serviceBuilder
->
getCRMScope
()
->
item
()
->
add
(
$entityTypeId
,
$fields
);
print
(
"ID: "
.
$result
->
item
()->id . PHP_EOL);
print
(
"Title: "
.
$result
->
item
()->title . PHP_EOL);
print
(
"Created By: "
.
$result
->
item
()->createdBy . PHP_EOL);
print
(
"Updated By: "
.
$result
->
item
()->updatedBy . PHP_EOL);
print
(
"Created Time: "
.
$result
->
item
()->createdTime->
format
(
DateTime
::
ATOM
) . PHP_EOL);
print
(
"Updated Time: "
.
$result
->
item
()->updatedTime->
format
(
DateTime
::
ATOM
) . PHP_EOL);
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
() . PHP_EOL);
}
Example of creating an SPA item with a set of custom fields
Custom fields involved in the example
{
"ufCrm44_1721812760630"
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
"Custom field (string)"
,
"listLabel"
:
"Custom field (string)"
,
"formLabel"
:
"Custom field (string)"
,
"filterLabel"
:
"Custom field (string)"
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
""
}
,
"upperName"
:
"UF_CRM_44_1721812760630"
}
,
"ufCrm44_1721812814433"
:
{
"type"
:
"enumeration"
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
"items"
:
[
{
"ID"
:
"79"
,
"VALUE"
:
"List item #1"
}
,
{
"ID"
:
"80"
,
"VALUE"
:
"List item #2"
}
,
{
"ID"
:
"81"
,
"VALUE"
:
"List item #3"
}
,
{
"ID"
:
"82"
,
"VALUE"
:
"List item #4"
}
]
,
"title"
:
"Custom field (list)"
,
"listLabel"
:
"Custom field (list)"
,
"formLabel"
:
"Custom field (list)"
,
"filterLabel"
:
"Custom field (list)"
,
"settings"
:
{
"DISPLAY"
:
"LIST"
,
"LIST_HEIGHT"
:
1
,
"CAPTION_NO_VALUE"
:
""
,
"SHOW_NO_VALUE"
:
"Y"
}
,
"upperName"
:
"UF_CRM_44_1721812814433"
}
,
"ufCrm44_1721812853419"
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
"Custom field (date)"
,
"listLabel"
:
"Custom field (date)"
,
"formLabel"
:
"Custom field (date)"
,
"filterLabel"
:
"Custom field (date)"
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
,
"upperName"
:
"UF_CRM_44_1721812853419"
}
,
"ufCrm44_1721812885588"
:
{
"type"
:
"url"
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
true
,
"title"
:
"Multiple custom field (link)"
,
"listLabel"
:
"Multiple custom field (link)"
,
"formLabel"
:
"Multiple custom field (link)"
,
"filterLabel"
:
"Multiple custom field (link)"
,
"settings"
:
{
"POPUP"
:
"Y"
,
"SIZE"
:
20
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
,
"ROWS"
:
1
}
,
"upperName"
:
"UF_CRM_44_1721812885588"
}
,
"ufCrm44_1721812898903"
:
{
"type"
:
"file"
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
"Custom field (file)"
,
"listLabel"
:
"Custom field (file)"
,
"formLabel"
:
"Custom field (file)"
,
"filterLabel"
:
"Custom field (file)"
,
"settings"
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
"upperName"
:
"UF_CRM_44_1721812898903"
}
,
"ufCrm44_1721812915476"
:
{
"type"
:
"money"
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
"Custom field (money)"
,
"listLabel"
:
"Custom field (money)"
,
"formLabel"
:
"Custom field (money)"
,
"filterLabel"
:
"Custom field (money)"
,
"settings"
:
{
"DEFAULT_VALUE"
:
""
}
,
"upperName"
:
"UF_CRM_44_1721812915476"
}
,
"ufCrm44_1721812935209"
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
"Custom field (Yes/No)"
,
"listLabel"
:
"Custom field (Yes/No)"
,
"formLabel"
:
"Custom field (Yes/No)"
,
"filterLabel"
:
"Custom field (Yes/No)"
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
{
"en"
:
"Custom field (Yes/No)"
,
"de"
:
"Custom field (Yes/No)"
,
"th"
:
"Custom field (Yes/No)"
,
"la"
:
"Custom field (Yes/No)"
,
"tc"
:
"Custom field (Yes/No)"
,
"sc"
:
"Custom field (Yes/No)"
,
"br"
:
"Custom field (Yes/No)"
,
"ar"
:
"Custom field (Yes/No)"
,
"fr"
:
"Custom field (Yes/No)"
,
"vn"
:
"Custom field (Yes/No)"
,
"pl"
:
"Custom field (Yes/No)"
,
"tr"
:
"Custom field (Yes/No)"
,
"ja"
:
"Custom field (Yes/No)"
,
"it"
:
"Custom field (Yes/No)"
,
"ms"
:
"Custom field (Yes/No)"
,
"id"
:
"Custom field (Yes/No)"
}
}
,
"upperName"
:
"UF_CRM_44_1721812935209"
}
,
"ufCrm44_1721812948498"
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
true
,
"title"
:
"Custom field (number)"
,
"listLabel"
:
"Custom field (number)"
,
"formLabel"
:
"Custom field (number)"
,
"filterLabel"
:
"Custom field (number)"
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
,
"upperName"
:
"UF_CRM_44_1721812948498"
}
}
cURL (Webhook)
cURL (OAuth)
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
'{
"entityTypeId": 1302,
"fields": {
"ufCrm44_1721812760630": "String for custom field of type String",
"ufCrm44_1721812814433": 81,
"ufCrm44_1721812853419": "'
"
$(date '+%Y-%m-%d')
"
'",
"ufCrm44_1721812885588": [
"example.com",
"second-example.com"
],
"ufCrm44_1721812898903": [
"green_pixel.png",
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
],
"ufCrm44_1721812915476": "300|USD",
"ufCrm44_1721812935209": "Y",
"ufCrm44_1721812948498": 9999.9
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"entityTypeId": 1302,
"fields": {
"ufCrm44_1721812760630": "String for custom field of type String",
"ufCrm44_1721812814433": 81,
"ufCrm44_1721812853419": "'
"
$(date '+%Y-%m-%d')
"
'",
"ufCrm44_1721812885588": [
"example.com",
"second-example.com"
],
"ufCrm44_1721812898903": [
"green_pixel.png",
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
],
"ufCrm44_1721812915476": "300|USD",
"ufCrm44_1721812935209": "Y",
"ufCrm44_1721812948498": 9999.9
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/crm.item.add
const
greenPixelInBase64 =
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
;
BX24
.
callMethod
(
'crm.item.add'
,
{
entityTypeId
:
1302
,
fields
: {
ufCrm44_1721812760630
:
"String for custom field of type String"
,
ufCrm44_1721812814433
:
81
,
ufCrm44_1721812853419
: (
new
Date
()).
toISOString
().
slice
(
0
,
10
),
ufCrm44_1721812885588
: [
"example.com"
,
"second-example.com"
,
],
ufCrm44_1721812898903
: [
"green_pixel.png"
,
greenPixelInBase64,
],
ufCrm44_1721812915476
:
"300|USD"
,
ufCrm44_1721812935209
:
"Y"
,
ufCrm44_1721812948498
:
9999.9
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
'crm.item.add'
,
[
'entityTypeId'
=>
1302
,
'fields'
=> [
'ufCrm44_1721812760630'
=>
"String for custom field of type String"
,
'ufCrm44_1721812814433'
=>
81
,
'ufCrm44_1721812853419'
=>
date
(
'Y-m-d'
),
'ufCrm44_1721812885588'
=> [
"example.com"
,
"second-example.com"
,
],
'ufCrm44_1721812898903'
=> [
"green_pixel.png"
,
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
,
],
'ufCrm44_1721812915476'
=>
"300|USD"
,
'ufCrm44_1721812935209'
=>
"Y"
,
'ufCrm44_1721812948498'
=>
9999.9
,
],
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
Response Processing
Response Processing
HTTP Status:
200
Note
Disabled fields always return
null
{
"result"
:
{
"item"
:
{
"id"
:
342
,
"createdTime"
:
"2024-07-18T14:00:14+02:00"
,
"dateCreateShort"
:
null
,
"updatedTime"
:
"2024-07-18T14:00:14+02:00"
,
"dateModifyShort"
:
null
,
"createdBy"
:
1
,
"updatedBy"
:
1
,
"assignedById"
:
6
,
"opened"
:
"N"
,
"leadId"
:
102
,
"companyId"
:
5
,
"contactId"
:
4
,
"quoteId"
:
7
,
"title"
:
"New deal (specifically for the example of REST methods)"
,
"productId"
:
null
,
"categoryId"
:
9
,
"stageId"
:
"C9:UC_KN8KFI"
,
"stageSemanticId"
:
"P"
,
"isNew"
:
"N"
,
"isRecurring"
:
"N"
,
"isReturnCustomer"
:
"N"
,
"isRepeatedApproach"
:
"Y"
,
"closed"
:
"N"
,
"typeId"
:
"SERVICE"
,
"opportunity"
:
999.99
,
"isManualOpportunity"
:
"Y"
,
"taxValue"
:
0
,
"currencyId"
:
"USD"
,
"probability"
:
50
,
"comments"
:
"\nExample comment within the deal\n\n[B]Bold text[/B]\n[I]Italic[/I]\n[U]Underlined[/U]\n[S]Strikethrough[/S]\n[B][I][U][S]Mix[/S][/U][/I][/B]\n\n[LIST]\n[*]List item #1\n[*]List item #2\n[*]List item #3\n[/LIST]\n\n[LIST=1]\n[*]Numbered list item #1\n[*]Numbered list item #2\n[*]Numbered list item #3\n[/LIST]\n"
,
"begindate"
:
"2024-06-18T02:00:00+02:00"
,
"begindateShort"
:
null
,
"closedate"
:
"2024-07-30T02:00:00+02:00"
,
"closedateShort"
:
null
,
"eventDate"
:
null
,
"eventDateShort"
:
null
,
"eventId"
:
null
,
"eventDescription"
:
null
,
"locationId"
:
null
,
"webformId"
:
null
,
"sourceId"
:
"WEB"
,
"sourceDescription"
:
"There should be additional description about the source"
,
"originatorId"
:
null
,
"originId"
:
null
,
"additionalInfo"
:
"There should be additional information"
,
"searchContent"
:
null
,
"orderStage"
:
null
,
"movedBy"
:
1
,
"movedTime"
:
"2024-07-18T14:00:14+02:00"
,
"lastActivityBy"
:
1
,
"lastActivityTime"
:
"2024-07-18T14:00:14+02:00"
,
"isWork"
:
null
,
"isWon"
:
null
,
"isLose"
:
null
,
"receivedAmount"
:
null
,
"lostAmount"
:
null
,
"hasProducts"
:
null
,
"ufCrm_1721244707107"
:
1111.1
,
"parentId1220"
:
[
"1"
,
"2"
]
,
"utmSource"
:
"google"
,
"utmMedium"
:
"CPC"
,
"utmCampaign"
:
null
,
"utmContent"
:
null
,
"utmTerm"
:
null
,
"observers"
:
[
2
,
3
]
,
"contactIds"
:
[
4
,
5
]
,
"entityTypeId"
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
1721304013.245896
,
"finish"
:
1721304015.555471
,
"duration"
:
2.309574842453003
,
"processing"
:
1.8328988552093506
,
"date_start"
:
"2024-07-18T14:00:13+02:00"
,
"date_finish"
:
"2024-07-18T14:00:15+02:00"
,
"operating"
:
1.8328571319580078
}
}
By default, names of user-defined fields are passed and returned in camelCase, for example
ufCrm2_1639669411830
.
When passing the parameter
useOriginalUfNames
with the value
Y
, user-defined fields will be returned with their original names, for example
UF_CRM_2_1639669411830
.
Returned Data
Returned Data
Name
type
Description
result
object
The root element of the response, contains a single key
item
item
item
Information about the created item,
field descriptions
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
400
,
403
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"SPA not found"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action allowed only for intranet users
User is not an intranet user
400
NOT_FOUND
SPA not found
Occurs when an invalid
entityTypeId
is passed
400
ACCESS_DENIED
Access denied
User does not have permission to add items of type
entityTypeId
400
CRM_FIELD_ERROR_VALUE_NOT_VALID
Invalid value for field "
field
"
Incorrect value for field
field
400
100
Expected iterable value for multiple field, but got
type
instead
One of the multiple fields received a value of type
type
, while an iterable type was expected
400
CREATE_DYNAMIC_ITEM_RESTRICTED
You cannot create a new item due to your plan restrictions
Plan restrictions do not allow creating SPA items
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
Update CRM Item: crm.item.update
Get Item by Id crm.item.get
Get a list of crm.item.list elements
Delete CRM Item - crm.item.delete
Get Fields of CRM Item `crm.item.fields`
CRM Object Fields
How to Create a Vendor in CRM
Copied
Was the article helpful?
Yes
No
Previous
Get fields of custom type
Next
Update Entity

---

## Update CRM Item: crm.item.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/crm-item-update

Update CRM Item: crm.item.update | Bitrix24 REST API and Marketplace Applications
Update CRM Item: crm.item.update
Update CRM Item: crm.item.update
Method Parameters
Parameter fields
How to Update a Custom Field of Type File
Code Examples
Response Handling
Returned Values
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with "edit" access permission for CRM entity items
This method updates an item of a specific type in the CRM object by assigning new values from the
fields
parameter.
When updating an item, a standard series of checks, modifications, and automatic actions are performed:
access permissions are verified
required fields are checked for completion if the item's stage has changed within the same direction
dependent required fields are checked for completion if the item's stage has changed within the same direction
the correctness of field entries is verified
default values are assigned to fields
if it turns out that no field values have been changed before saving, the save
is not performed
automation rules are triggered after saving
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
whose item we want to change
id
*
integer
Identifier of the item we want to change.
Can be obtained using the
crm.item.list
or
crm.item.add
methods
fields
*
object
Object in the format
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where
field_n
— field name
value_n
— new field value
Each type of CRM entity has its own set of fields. This means that the set of fields for changing a Lead does not have to match the set of fields for changing a Contact or SPA.
The list of available fields for each type of entity is described
below
.
An incorrect field in
fields
will be ignored.
Note
Only those fields that need to be changed should be passed in
fields
useOriginalUfNames
boolean
Parameter to control the format of custom field names in the request and response.
Possible values:
Y
— original custom field names, e.g.,
UF_CRM_2_1639669411830
N
— custom field names in camelCase, e.g.,
ufCrm2_1639669411830
Default —
N
Parameter fields
Parameter fields
Required parameters are marked with *
Lead
Deal
Contact
Company
Estimate
Invoice
SPA
CRM object identifier
entityTypeId:
1
Name
type
Description
title
string
Item title
honorific
crm_status
String identifier for the lead's honorific (e.g.,
'HNR_RU_1' = 'Mr.'
).
The list of available honorifics can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "HONOFIRIC" }
name
string
First name
secondName
string
Middle name
lastName
string
Last name
birthdate
date
Date of birth
companyTitle
string
Company name
sourceId
crm_status
String identifier for the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
sourceDescription
text
Additional information about the source
stageId
crm_status
String identifier for the item's stage.
For example,
'NEW' = 'Unprocessed'
.
The list of available stages can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "STATUS" }
statusDescription
text
Additional information about the stage
post
string
Position
currencyId
crm_currency
Identifier of the item's currency
isManualOpportunity
boolean
Opportunity calculation mode. Possible values:
Y
— manual
N
— automatic
opportunity
double
Amount
opened
boolean
Is the item available to everyone? Possible values:
Y
— yes
N
— no
comments
text
Comment
assignedById
user
Identifier of the person responsible for the item
companyId
crm_company
Identifier of the company linked to the item.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
contactId
crm_contact
Identifier of the contact linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
contactIds
crm_contact[]
List of identifiers of contacts linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
originatorId
string
External source
originId
string
Identifier of the item in the external source
webformId
integer
Identifier of the CRM Form
observers
user[]
Array of user identifiers who will be observers in the item
utmSource
string
Advertising system. For example: Google Ads, Bing Ads, etc.
utmMedium
string
Traffic type. Possible values:
CPC — ads
CPM — banners
utmCampaign
string
Identifier of the advertising campaign
utmContent
string
Content of the campaign. For example, for contextual ads
utmTerm
string
Search condition of the campaign. For example, keywords for contextual advertising
ufCrm...
crm_userfield
Custom field.
Read about custom fields in the section
Custom Fields in CRM
Values of multiple fields are passed as an array.
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this item.
Each such field has the code
parentId + {parentEntityTypeId}
fm
multifield[]
Array of multifields.
More about multifields can be read in the section
crm_multifield
Structure of a multifield:
id
— Unique identifier of the multifield. If no multifield with this id exists, a new multifield will be created
typeId
— Type of the multifield
valueType
— Type of value
value
— Value
Example:
fm: {
"15"
: {
"valueType"
:
"WORK"
,
"value"
:
"+19999999999"
,
"typeId"
:
"PHONE"
},
"16"
: {
"valueType"
:
"WORK"
,
"value"
:
"bitrix@bitrix.com"
,
"typeId"
:
"EMAIL"
}
}
Default —
null
CRM object identifier
entityTypeId:
2
Name
type
Description
title
string
Item title
typeId
crm_status
String identifier for the entity type.
For example, for a deal:
'SALE' = 'Sale'
The list of available entity types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "DEAL_TYPE" }
categoryId
integer
Identifier of the
direction
(funnel) of the deal
stageId
crm_status
String identifier for the item's stage.
For example,
'NEW' = 'Unprocessed'
.
The list of available stages can be obtained using
crm.status.list
with the filter:
If the deal is in the general funnel (direction)  —
{ ENTITY_ID: "DEAL_STAGE" }
If the deal is not in the general funnel (direction) —
{ ENTITY_ID: "DEAL_STAGE_{categoryId}" }
, where
categoryId
is the identifier of the funnel (
direction
) of the deal
isRecurring
boolean
Is the deal recurring? Possible values:
Y
— yes
N
— no
probability
integer
Probability %
currencyId
crm_currency
Identifier of the item's currency
isManualOpportunity
boolean
Opportunity calculation mode. Possible values:
Y
— manual
N
— automatic
opportunity
double
Amount
taxValue
double
Tax amount
companyId
crm_company
Identifier of the company linked to the item.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
contactId
crm_contact
Identifier of the contact linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
contactIds
crm_contact[]
List of identifiers of contacts linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
quoteId
crm_quote
Identifier of the estimate that will be linked to the deal
begindate
date
Start date of the item
closedate
date
End date of the item
opened
boolean
Is the item available to everyone? Possible values:
Y
— yes
N
— no
comments
text
Comment
assignedById
user
Identifier of the person responsible for the item
sourceId
crm_status
String identifier for the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
sourceDescription
text
Additional information about the source
leadId
crm_lead
Identifier of the lead based on which the item is created
additionalInfo
string
Additional information
originatorId
string
External source
originId
string
Identifier of the item in the external source
observers
user[]
Array of user identifiers who will be observers in the item
locationId
location
Identifier of the location. Service field
utmSource
string
Advertising system. Google Ads, Bing Ads, etc.
utmMedium
string
Traffic type. Possible values:
CPC — ads
CPM — banners
utmCampaign
string
Identifier of the advertising campaign
utmContent
string
Content of the campaign. For example, for contextual ads
utmTerm
string
Search condition of the campaign. For example, keywords for contextual advertising
ufCrm...
crm_userfield
Custom field. See the section
Custom Fields in CRM
Values of multiple fields are passed as an array
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this item.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
3
Name
type
Description
honorific
crm_status
String identifier for the contact's honorific.
For example,
'HNR_RU_1' = 'Mr.'
.
The list of available honorifics can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "HONOFIRIC" }
name
string
First name
secondName
string
Middle name
lastName
string
Last name
photo
file
Photo
birthdate
date
Date of birth
typeId
crm_status
String identifier for the entity type.
For example, for a deal:
'SALE' = 'Sale'
.
The list of available entity types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "CONTACT_TYPE" }
sourceId
crm_status
String identifier for the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
sourceDescription
text
Additional information about the source
post
string
Position
comments
text
Comment
opened
boolean
Is the item available to everyone? Possible values:
Y
— yes
N
— no
export
boolean
Is the contact participating in the export?
assignedById
user
Identifier of the person responsible for the item
companyId
crm_company
Identifier of the company linked to the item.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
companyIds
crm_company
Array of identifiers of companies that will be linked to the item
leadId
crm_lead
Identifier of the lead based on which the item is created
originatorId
string
External source
originId
string
Identifier of the item in the external source
originVersion
string
Version of the original
observers
user[]
Array of user identifiers who will be observers in the item
utmSource
string
Advertising system. Google Ads, Bing Ads, etc.
utmMedium
string
Traffic type. Possible values:
CPC — ads
CPM — banners
utmCampaign
string
Identifier of the advertising campaign
utmContent
string
Content of the campaign. For example, for contextual ads
utmTerm
string
Search condition of the campaign. For example, keywords for contextual advertising
ufCrm...
crm_userfield
Custom field. See the section
Custom Fields in CRM
Values of multiple fields are passed as an array
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this item.
Each such field has the code
parentId + {parentEntityTypeId}
fm
multifield[]
Array of multifields.
More about multifields can be read in the section
crm_multifield
Structure of a multifield:
id
— Unique identifier of the multifield. If no multifield with this id exists, a new multifield will be created
typeId
— Type of the multifield
valueType
— Type of value
value
— Value
Example:
fm: {
"15"
: {
"valueType"
:
"WORK"
,
"value"
:
"+19999999999"
,
"typeId"
:
"PHONE"
},
"16"
: {
"valueType"
:
"WORK"
,
"value"
:
"bitrix@bitrix.com"
,
"typeId"
:
"EMAIL"
}
}
Default —
null
CRM object identifier
entityTypeId:
4
Name
type
Description
title
string
Item title
typeId
crm_status
String identifier for the entity type.
For example, for a deal:
'SALE' = 'Sale'
.
The list of available entity types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "COMPANY_TYPE" }
logo
file
Logo
bankingDetails
string
Banking details
industry
crm_status
String identifier for the industry type.
For example,
'IT' = 'Information Technology'
.
The list of available industry types can be obtained using the
crm.status.list
method with the filter
{ ENTITY_ID: "INDUSTRY"}
employees
crm_status
String identifier for the number of employees.
The value is taken from the available list, for example,
'EMPLOYEES_1' = 'less than 50'
.
The list of available employee counts can be obtained using the
crm.status.list
method with the filter
{ ENTITY_ID: "EMPLOYEES" }
currencyId
crm_currency
Identifier of the item's currency
revenue
double
Annual revenue
opened
boolean
Is the item available to everyone? Possible values:
Y
— yes
N
— no
comments
text
Comment
isMyCompany
boolean
Is the company my company?
assignedById
user
Identifier of the person responsible for the item
contactIds
crm_contact[]
List of identifiers of contacts linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
leadId
crm_lead
Identifier of the lead based on which the item is created.
originatorId
string
External source
originId
string
Identifier of the item in the external source
originVersion
string
Version of the original
observers
user[]
Array of user identifiers who will be observers in the item
utmSource
string
Advertising system. Google Ads, Bing Ads, etc.
utmMedium
string
Traffic type. Possible values:
CPC — ads
CPM — banners
utmCampaign
string
Identifier of the advertising campaign
utmContent
string
Content of the campaign. For example, for contextual ads
utmTerm
string
Search condition of the campaign. For example, keywords for contextual advertising
ufCrm...
crm_userfield
Custom field. See the section
Custom Fields in CRM
Values of multiple fields are passed as an array
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this item.
Each such field has the code
parentId + {parentEntityTypeId}
fm
multifield[]
Array of multifields.
More about multifields can be read in the section
crm_multifield
Structure of a multifield:
id
— Unique identifier of the multifield. If no multifield with this id exists, a new multifield will be created
typeId
— Type of the multifield
valueType
— Type of value
value
— Value
Example:
fm: {
"15"
: {
"valueType"
:
"WORK"
,
"value"
:
"+19999999999"
,
"typeId"
:
"PHONE"
},
"16"
: {
"valueType"
:
"WORK"
,
"value"
:
"bitrix@bitrix.com"
,
"typeId"
:
"EMAIL"
}
}
Default —
null
CRM object identifier
entityTypeId:
7
Name
type
Description
title
string
Item title
assignedById
user
Identifier of the person responsible for the item
opened
boolean
Is the item available to everyone? Possible values:
Y
— yes
N
— no
content
text
Content
terms
text
Terms
comments
text
Comment
dealId
crm_deal
Identifier of the linked deal
leadId
crm_lead
Identifier of the lead based on which the item is created
storageTypeId
integer
Identifier of the storage type. Possible values:
1
— file
2
— WebDAV
3
— Drive
storageElementIds
integer
Array of files
webformId
integer
Identifier of the CRM Form
companyId
crm_company
Identifier of the company linked to the item.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
contactId
crm_contact
Identifier of the contact linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
contactIds
crm_contact[]
List of identifiers of contacts linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
locationId
location
Identifier of the location. Service field
currencyId
crm_currency
Identifier of the item's currency
isManualOpportunity
boolean
Opportunity calculation mode.
Y
— manual
N
— automatic
opportunity
double
Amount
taxValue
double
Tax amount
stageId
crm_status
String identifier for the item's stage.
For example,
'DRAFT' = 'New'
.
The list of available stages can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "QUOTE_STATUS" }
begindate
date
Start date of the item
closedate
date
End date of the item
actualDate
date
Valid until
mycompanyId
crm_company
Identifier of my company
utmSource
string
Advertising system. Google Ads, Bing Ads, etc.
utmMedium
string
Traffic type.
CPC — ads
CPM — banners
utmCampaign
string
Identifier of the advertising campaign
utmContent
string
Content of the campaign. For example, for contextual ads
utmTerm
string
Search condition of the campaign. For example, keywords for contextual advertising
ufCrm...
crm_userfield
Custom field. See the section
Custom Fields in CRM
.
Values of multiple fields are passed as an array
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this item.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
31
Name
type
Description
title
string
Item title
xmlId
string
External code
assignedById
user
Identifier of the person responsible for the item
opened
boolean
Is the item available to everyone? Possible values:
Y
— yes
N
— no
webformId
integer
Identifier of the CRM Form
begindate
date
Start date of the item
closedate
date
End date of the item
companyId
crm_company
Identifier of the company linked to the item.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
contactId
crm_contact
Identifier of the contact linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
contactIds
crm_contact[]
List of identifiers of contacts linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
observers
user[]
Array of user identifiers who will be observers in the item
stageId
crm_status
String identifier for the item's stage.
For example,
'DT31_13:N' = 'New'
.
The list of available stages can be obtained using
crm.status.list
with the filter:
{ ENTITY_ID: "SMART_INVOICE_STAGE_{categoryId}" }
, where
categoryId
— identifier of the default invoice funnel. It can be obtained using
crm.category.list
with
entityTypeId = 31
sourceId
crm_status
String identifier for the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
sourceDescription
text
Additional information about the source
currencyId
crm_currency
Identifier of the item's currency
isManualOpportunity
boolean
Opportunity calculation mode. Possible values:
Y
— manual
N
— automatic
opportunity
double
Amount
taxValue
double
Tax amount
mycompanyId
crm_company
Identifier of my company
comments
text
Comment
locationId
location
Identifier of the location. Service field
ufCrm...
crm_userfield
Custom field. See the section
Custom Fields in CRM
.
Values of multiple fields are passed as an array
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this item.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
can be obtained using the
crm.type.list
method or created using the
crm.type.add
method.
Name
type
Description
title
string
Item title
xmlId
string
External code
assignedById
user
Identifier of the person responsible for the item
opened
boolean
Is the item available to everyone?
Y
— yes
N
— no
webformId
integer
Identifier of the CRM Form
begindate
date
Start date of the item.
Available only when the
isBeginCloseDatesEnabled
setting is enabled for the corresponding SPA.
closedate
date
End date of the item.
Available only when the
isBeginCloseDatesEnabled
setting is enabled for the corresponding SPA
companyId
crm_company
Identifier of the company linked to the item.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
.
Available only when the
isClientEnabled
setting is enabled for the corresponding SPA
contactId
crm_contact
Identifier of the contact linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
Available only when the
isClientEnabled
setting is enabled for the corresponding SPA
contactIds
crm_contact[]
List of identifiers of contacts linked to the item.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
Available only when the
isClientEnabled
setting is enabled for the corresponding SPA
observers
user[]
Array of user identifiers who will be observers in the item.
Available only when the
isObserversEnabled
setting is enabled for the corresponding SPA
categoryId
crm_category
Identifier of the funnel of the SPA item.
If the identifier is not specified, the SPA will be moved to the main funnel.
The list of available funnels can be obtained using the
crm.category.list
with the corresponding
entityTypeId
stageId
crm_status
String identifier for the item's stage.
For example,
'DT1220_30:NEW' = 'Start'
.
The list of available stages can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "DYNAMIC_{entityTypeId}_STAGE_{categoryId}" }
, where
entityTypeId
— identifier of the SPA type
categoryId
— identifier of the funnel (direction) of the SPA item
More about funnels (directions)
.
Available only when the
isStagesEnabled
setting is enabled for the corresponding SPA
sourceId
crm_status
String identifier for the source. (for example,
'CALL' = 'Call'
).
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
Available only when the
isSourceEnabled
setting is enabled for the corresponding SPA
sourceDescription
text
Additional information about the source.
Available only when the
isSourceEnabled
setting is enabled for the corresponding SPA
currencyId
crm_currency
Identifier of the item's currency.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
isManualOpportunity
boolean
Opportunity calculation mode. Possible values:
Y
— manual
N
— automatic
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
opportunity
double
Amount.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
taxValue
double
Tax amount.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
mycompanyId
crm_company
Identifier of my company.
Available only when the
isMycompanyEnabled
setting is enabled for the corresponding SPA
ufCrm...
crm_userfield
Custom field. See the section
Custom Fields in CRM
.
Values of multiple fields are passed as an array
To upload a file, the value of the custom field must be an array where the first element is the file name and the second is the content of the file encoded in
base64
.
parentId...
crm_entity
Parent field. An element of another type of CRM object linked to this item.
Each such field has the code
parentId + {parentEntityTypeId}
SPA Settings
More about managing SPA settings can be read in
Smart Processes: Overview of Methods
How to Update a Custom Field of Type File
How to Update a Custom Field of Type File
Upload a new file instead of the old one (non-multiple field)
To replace a file in a non-multiple field, simply upload the new file. The old one will be automatically deleted.
{
"fields"
:
{
"ufCrm1617027453943"
:
[
"myfile.pdf"
,
"...base64_encoded_file_content..."
]
}
}
Remove the value of the custom field of type file
To do this, simply pass an empty string (
''
) instead of the value.
Leave the value of the non-multiple field of type file unchanged
The simplest option is not to add a key with this field in
fields
.
But if you need to pass it and not change it, then the value should be passed as a list where the key
id
will be the file identifier.
{
"fields"
:
{
"ufCrm1617027453943"
:
{
"id"
:
433
}
}
}
Warning
If a value different from the current one is passed in
id
, the field value will be reset and the file will be deleted.
Working with a multiple field of type file
The value of a multiple field is an array. Each element of the array is subject to the same rules as for non-multiple values.
How to Partially Overwrite Values of a Multiple Field of Type File
For example, the current values in the multiple field of type file are
[12, 255, 44]
.
You need to keep files
12
and
44
, and upload a new one instead of
255
.
The request should look as follows:
{
"fields"
:
{
"ufCrm1617027453943"
:
[
{
"id"
:
12
}
,
{
"id"
:
44
}
,
[
"myNewFile.pdf"
,
"...base64_encoded_file_content..."
]
]
}
}
Code Examples
Code Examples
Update a deal with
id = 351
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
'{"entityTypeId":2,"id":351,"fields":{"title":"REST Deal #1","stageId":"C9:UC_NYL06U","assignedById":6,"observers":[1,2,3],"opened":"N","typeId":"SERVICE","opportunity":10000,"currencyId":"USD","additionalInfo":"Updating deal via REST","isManualOpportunity":"N","utmSource":"google","ufCrm_1721244707107":200.05,"parentId1220":2}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"id":351,"fields":{"title":"REST Deal #1","stageId":"C9:UC_NYL06U","assignedById":6,"observers":[1,2,3],"opened":"N","typeId":"SERVICE","opportunity":10000,"currencyId":"USD","additionalInfo":"Updating deal via REST","isManualOpportunity":"N","utmSource":"google","ufCrm_1721244707107":200.05,"parentId1220":2},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.update
BX24
.
callMethod
(
'crm.item.update'
,
{
entityTypeId
:
2
,
id
:
351
,
fields
: {
title
:
"REST Deal #1"
,
stageId
:
"C9:UC_NYL06U"
,
assignedById
:
6
,
observers
: [
1
,
2
,
3
],
opened
:
"N"
,
typeId
:
"SERVICE"
,
opportunity
:
10000
,
currencyId
:
"USD"
,
additionalInfo
:
"Updating deal via REST"
,
isManualOpportunity
:
"N"
,
utmSource
:
"google"
,
ufCrm_1721244707107
:
200.05
,
parentId1220
:
2
,
},
},
(
result
) =>
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
return
;
}
console
.
info
(result.
data
());
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
'crm.item.update'
,
[
'entityTypeId'
=>
2
,
'id'
=>
351
,
'fields'
=> [
'title'
=>
"REST Deal #1"
,
'stageId'
=>
"C9:UC_NYL06U"
,
'assignedById'
=>
6
,
'observers'
=> [
1
,
2
,
3
],
'opened'
=>
"N"
,
'typeId'
=>
"SERVICE"
,
'opportunity'
=>
10000
,
'currencyId'
=>
"USD"
,
'additionalInfo'
=>
"Updating deal via REST"
,
'isManualOpportunity'
=>
"N"
,
'utmSource'
=>
"google"
,
'ufCrm_1721244707107'
=>
200.05
,
'parentId1220'
=>
2
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
try
{
$entityTypeId
=
1
;
// Set your entity type ID
$id
=
123
;
// Set the ID of the item to update
$fields
= [
'TITLE'
=>
'Updated Title'
,
'DATE_MODIFIED'
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
// Example DateTime field
// Add other fields as necessary
];
$itemService
=
$serviceBuilder
->
getCRMScope
()->
item
();
$updateResult
=
$itemService
->
update
(
$entityTypeId
,
$id
,
$fields
);
if
(
$updateResult
->
isSuccess
()) {
print
(
"Item updated successfully: "
.
json_encode
(
$updateResult
));
}
else
{
print
(
"Failed to update item."
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
Response Handling
Response Handling
HTTP Status:
200
{
"result"
:
{
"item"
:
{
"id"
:
351
,
"createdTime"
:
"2024-07-23T19:10:26+02:00"
,
"dateCreateShort"
:
null
,
"updatedTime"
:
"2024-07-23T18:19:21+02:00"
,
"dateModifyShort"
:
null
,
"createdBy"
:
1
,
"updatedBy"
:
1
,
"assignedById"
:
6
,
"opened"
:
"N"
,
"leadId"
:
null
,
"companyId"
:
0
,
"contactId"
:
0
,
"quoteId"
:
null
,
"title"
:
"REST Deal #1"
,
"productId"
:
null
,
"categoryId"
:
9
,
"stageId"
:
"C9:UC_NYL06U"
,
"stageSemanticId"
:
"P"
,
"isNew"
:
"N"
,
"isRecurring"
:
"N"
,
"isReturnCustomer"
:
"N"
,
"isRepeatedApproach"
:
"N"
,
"closed"
:
"N"
,
"typeId"
:
"SERVICE"
,
"opportunity"
:
10000
,
"isManualOpportunity"
:
"N"
,
"taxValue"
:
0
,
"currencyId"
:
"USD"
,
"probability"
:
null
,
"comments"
:
""
,
"begindate"
:
"2024-07-23T02:00:00+02:00"
,
"begindateShort"
:
null
,
"closedate"
:
"2024-07-31T02:00:00+02:00"
,
"closedateShort"
:
null
,
"eventDate"
:
null
,
"eventDateShort"
:
null
,
"eventId"
:
null
,
"eventDescription"
:
null
,
"locationId"
:
null
,
"webformId"
:
0
,
"sourceId"
:
""
,
"sourceDescription"
:
""
,
"originatorId"
:
null
,
"originId"
:
null
,
"additionalInfo"
:
"Updating deal via REST"
,
"searchContent"
:
"351 Deal #351 10200.00 US Dollar No Invented Invented Sale Title2134234233 23.07.2024 31.07.2024"
,
"orderStage"
:
null
,
"movedBy"
:
1
,
"movedTime"
:
"2024-07-23T18:19:21+02:00"
,
"lastActivityBy"
:
1
,
"lastActivityTime"
:
"2024-07-23T18:10:26+02:00"
,
"isWork"
:
null
,
"isWon"
:
null
,
"isLose"
:
null
,
"receivedAmount"
:
null
,
"lostAmount"
:
null
,
"hasProducts"
:
null
,
"ufCrm_1721244707107"
:
200.05
,
"parentId1220"
:
2
,
"utmSource"
:
"google"
,
"utmMedium"
:
null
,
"utmCampaign"
:
null
,
"utmContent"
:
null
,
"utmTerm"
:
null
,
"observers"
:
[
1
,
2
,
3
]
,
"contactIds"
:
[
]
,
"entityTypeId"
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
1721751560.824475
,
"finish"
:
1721751564.481578
,
"duration"
:
3.6571030616760254
,
"processing"
:
3.1893951892852783
,
"date_start"
:
"2024-07-23T18:19:20+02:00"
,
"date_finish"
:
"2024-07-23T18:19:24+02:00"
,
"operating"
:
3.1893470287323
}
}
Returned Values
Returned Values
Name
type
Description
result
object
Root element of the response, contains a single key
item
item
item
Information about the updated item,
field descriptions
time
time
Information about the execution time of the request
By default, custom field names are passed and returned in camelCase, for example,
ufCrm2_1639669411830
.
When passing the parameter
useOriginalUfNames
with the value
Y
, custom fields will be returned with their original names, for example,
UF_CRM_2_1639669411830
.
Error Handling
Error Handling
HTTP Status:
400
,
403
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"SPA not found"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action is allowed only for intranet users
User is not an intranet user
400
NOT_FOUND
SPA not found
Occurs when an invalid
entityTypeId
is passed
400
ACCESS_DENIED
Access denied
User does not have permission to modify items of type
entityTypeId
400
CRM_FIELD_ERROR_VALUE_NOT_VALID
Invalid value for field "
field
"
Incorrect value passed for field
field
400
100
Expected iterable value for multiple field, but got
type
instead
One of the multiple fields received a value of type
type
, while an iterable type was expected
400
-
Insufficient rights to change the stage
If a user attempts to change the stage of an item without sufficient rights
400
UPDATE_DYNAMIC_ITEM_RESTRICTED
You cannot change the item due to your plan's restrictions
Plan restrictions do not allow changing SPA items
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
Create a new CRM entity crm.item.add
Get Item by Id crm.item.get
Get a list of crm.item.list elements
Delete CRM Item - crm.item.delete
Get Fields of CRM Item `crm.item.fields`
CRM Object Fields
Copied
Was the article helpful?
Yes
No
Previous
Create New CRM Entity
Next
Get Entity by Id

---

## Get Item by Id crm.item.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/crm-item-get

Get Item by Id crm.item.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Item by Id crm.item.get
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
Who can execute the method: any user with "read" access permission for CRM object elements
The method returns information about an item by its identifier and the identifier of the CRM object type.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
whose item we want to retrieve
id
*
integer
Identifier of the item whose information we want to obtain.
It can be retrieved using the
crm.item.list
method or when creating an item with
crm.item.add
useOriginalUfNames
boolean
This parameter is used to control the format of custom field names in the response.
Possible values:
Y
— original custom field names, e.g.,
UF_CRM_2_1639669411830
N
— custom field names in camelCase, e.g.,
ufCrm2_1639669411830
Default is
N
Code Examples
Code Examples
How to Use Examples in Documentation
Get information about a lead with
id = 250
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
'{"entityTypeId":1,"id":250,"useOriginalUfNames":"N"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1,"id":250,"useOriginalUfNames":"N","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.get'
,
{
entityTypeId
:
1
,
id
:
250
,
useOriginalUfNames
:
'N'
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
$entityTypeId
=
1
;
// Example entity type ID
$id
=
123
;
// Example item ID
$itemResult
=
$serviceBuilder
->
getCRMScope
()
->
item
()
->
get
(
$entityTypeId
,
$id
);
$item
=
$itemResult
->
item
();
print
(
"ID: "
.
$item
->id . PHP_EOL);
print
(
"XML ID: "
.
$item
->xmlId . PHP_EOL);
print
(
"Title: "
.
$item
->title . PHP_EOL);
print
(
"Created By: "
.
$item
->createdBy . PHP_EOL);
print
(
"Updated By: "
.
$item
->updatedBy . PHP_EOL);
print
(
"Moved By: "
.
$item
->movedBy . PHP_EOL);
print
(
"Created Time: "
.
$item
->createdTime->
format
(DATE_ATOM) . PHP_EOL);
print
(
"Updated Time: "
.
$item
->updatedTime->
format
(DATE_ATOM) . PHP_EOL);
print
(
"Moved Time: "
.
$item
->movedTime->
format
(DATE_ATOM) . PHP_EOL);
print
(
"Category ID: "
.
$item
->categoryId . PHP_EOL);
print
(
"Opened: "
. (
$item
->opened ?
'true'
:
'false'
) . PHP_EOL);
print
(
"Previous Stage ID: "
.
$item
->previousStageId . PHP_EOL);
print
(
"Begin Date: "
.
$item
->begindate->
format
(DATE_ATOM) . PHP_EOL);
print
(
"Close Date: "
.
$item
->closedate->
format
(DATE_ATOM) . PHP_EOL);
print
(
"Company ID: "
.
$item
->companyId . PHP_EOL);
print
(
"Contact ID: "
.
$item
->contactId . PHP_EOL);
print
(
"Opportunity: "
.
$item
->opportunity . PHP_EOL);
print
(
"Is Manual Opportunity: "
. (
$item
->isManualOpportunity ?
'true'
:
'false'
) . PHP_EOL);
print
(
"Tax Value: "
.
$item
->taxValue . PHP_EOL);
print
(
"Currency ID: "
.
$item
->currencyId . PHP_EOL);
print
(
"Opportunity Account: "
.
$item
->opportunityAccount . PHP_EOL);
print
(
"Tax Value Account: "
.
$item
->taxValueAccount . PHP_EOL);
print
(
"Account Currency ID: "
.
$item
->accountCurrencyId . PHP_EOL);
print
(
"My Company ID: "
.
$item
->mycompanyId . PHP_EOL);
print
(
"Source ID: "
.
$item
->sourceId . PHP_EOL);
print
(
"Source Description: "
.
$item
->sourceDescription . PHP_EOL);
print
(
"Webform ID: "
.
$item
->webformId . PHP_EOL);
print
(
"Assigned By ID: "
.
$item
->assignedById . PHP_EOL);
print
(
"Last Activity By: "
.
$item
->lastActivityBy . PHP_EOL);
print
(
"Last Activity Time: "
.
$item
->lastActivityTime->
format
(DATE_ATOM) . PHP_EOL);
print
(
"UTM Source: "
.
$item
->utmSource . PHP_EOL);
print
(
"UTM Medium: "
.
$item
->utmMedium . PHP_EOL);
print
(
"UTM Campaign: "
.
$item
->utmCampaign . PHP_EOL);
print
(
"UTM Content: "
.
$item
->utmContent . PHP_EOL);
print
(
"UTM Term: "
.
$item
->utmTerm . PHP_EOL);
print
(
"Observers: "
.
json_encode
(
$item
->observers) . PHP_EOL);
print
(
"Contact IDs: "
.
json_encode
(
$item
->contactIds) . PHP_EOL);
print
(
"Entity Type ID: "
.
$item
->entityTypeId . PHP_EOL);
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
() . PHP_EOL);
}
BX24
.
callMethod
(
'crm.item.get'
,
{
entityTypeId
:
1
,
id
:
250
,
useOriginalUfNames
:
'N'
,
},
(
result
) =>
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
return
;
}
console
.
info
(result.
data
());
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
'crm.item.get'
,
[
'entityTypeId'
=>
1
,
'id'
=>
250
,
'useOriginalUfNames'
=>
'N'
,
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
"item"
:
{
"id"
:
250
,
"createdTime"
:
"2024-07-22T18:00:08+02:00"
,
"dateCreateShort"
:
null
,
"updatedTime"
:
"2024-07-22T18:00:08+02:00"
,
"dateModifyShort"
:
null
,
"createdBy"
:
1
,
"updatedBy"
:
1
,
"assignedById"
:
1
,
"opened"
:
"Y"
,
"companyId"
:
0
,
"contactId"
:
0
,
"stageId"
:
"IN_PROCESS"
,
"isConvert"
:
null
,
"statusDescription"
:
null
,
"stageSemanticId"
:
"P"
,
"productId"
:
null
,
"opportunity"
:
999.9
,
"currencyId"
:
"USD"
,
"sourceId"
:
"TRADE_SHOW"
,
"sourceDescription"
:
"Admin Exhibition"
,
"title"
:
"Lead #250"
,
"name"
:
"Admin"
,
"lastName"
:
"Adminov"
,
"secondName"
:
"Adminovich"
,
"shortName"
:
null
,
"companyTitle"
:
"Administrative Company"
,
"post"
:
"Admin"
,
"address"
:
null
,
"comments"
:
"[B]Comment about admin[/B]"
,
"webformId"
:
0
,
"originatorId"
:
null
,
"originId"
:
null
,
"dateClosed"
:
null
,
"birthdate"
:
"2000-01-01T02:00:00+02:00"
,
"honorific"
:
"UC_N1LWUS"
,
"hasPhone"
:
"Y"
,
"hasEmail"
:
"Y"
,
"hasImol"
:
"N"
,
"login"
:
null
,
"isReturnCustomer"
:
"N"
,
"searchContent"
:
"250 Lead #250 Adminov Admin Adminovich Administrative Company 999.90 US Dollar 6111111111 111111111 11111111 1111111 111111 11111 1111 111 nqzva rknzcyr pbz In Process Exhibition Exhibition about Admin City Admin [O]Comment about admin[/O] 321"
,
"isManualOpportunity"
:
"Y"
,
"movedBy"
:
1
,
"movedTime"
:
"2024-07-22T17:00:08+02:00"
,
"lastActivityBy"
:
1
,
"lastActivityTime"
:
"2024-07-22T17:00:08+02:00"
,
"phoneMobile"
:
""
,
"phoneWork"
:
"+16111111111"
,
"phoneMailing"
:
""
,
"emailHome"
:
""
,
"emailWork"
:
"admin@example.com"
,
"emailMailing"
:
""
,
"skype"
:
null
,
"icq"
:
null
,
"imol"
:
""
,
"email"
:
"admin@example.com"
,
"phone"
:
"+16111111111"
,
"ufCrm_1720019876534"
:
"321"
,
"parentId1222"
:
null
,
"parentId1226"
:
null
,
"parentId1228"
:
null
,
"parentId1236"
:
null
,
"parentId1238"
:
null
,
"parentId1240"
:
null
,
"parentId1244"
:
null
,
"parentId1246"
:
null
,
"parentId1254"
:
null
,
"parentId1256"
:
null
,
"utmSource"
:
null
,
"utmMedium"
:
null
,
"utmCampaign"
:
null
,
"utmContent"
:
null
,
"utmTerm"
:
null
,
"observers"
:
[
]
,
"contactIds"
:
[
]
,
"entityTypeId"
:
1
}
}
,
"time"
:
{
"start"
:
1721660468.931424
,
"finish"
:
1721660469.416092
,
"duration"
:
0.4846680164337158
,
"processing"
:
0.16368508338928223
,
"date_start"
:
"2024-07-22T17:01:08+02:00"
,
"date_finish"
:
"2024-07-22T17:01:09+02:00"
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
Root element of the response. Contains a single key
item
item
item
Information about the item,
field description
time
time
Object containing information about the request execution time
By default, custom field names are returned in camelCase, e.g.,
ufCrm2_1639669411830
.
When passing the parameter
useOriginalUfNames
with the value
Y
, custom fields will be returned with their original names, e.g.,
UF_CRM_2_1639669411830
.
Error Handling
Error Handling
HTTP Status:
400
,
403
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Item not found"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action allowed only for intranet users
User is not an intranet user
400
NOT_FOUND
SPA not found
Occurs when an invalid
entityTypeId
is passed
400
NOT_FOUND
Item not found
Item with the given
id
of type
entityTypeId
does not exist
400
ACCESS_DENIED
You do not have permission to view this item
User does not have read access permission for items of type
entityTypeId
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
Create a new CRM entity crm.item.add
Update CRM Item: crm.item.update
Get a list of crm.item.list elements
Delete CRM Item - crm.item.delete
Get Fields of CRM Item `crm.item.fields`
CRM Object Fields
Copied
Was the article helpful?
Yes
No
Previous
Update Entity
Next
Get List of Entities

---

## Get a list of crm.item.list elements

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/crm-item-list

Get a list of crm.item.list elements | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of crm.item.list elements
Method Parameters
Code Examples
Example request with date filter using OR logic
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with "read" access permission for CRM object elements
The method retrieves a list of elements of a specific type of CRM object.
CRM object elements will not be included in the final selection if the user does not have "read" access permission for these elements.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
user-defined type
whose elements need to be retrieved
select
array
List of fields that should be populated in the selected elements.
Can contain only field names or
'*'
.
A list of all available fields for selection can be obtained using the
crm.item.fields
method. A list of standard fields is available in the article
CRM Object Fields
filter
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where
field_n
— field name by which the selection of elements will be filtered
value_n
— filter value
The filter can have unlimited nesting and number of conditions.
By default, all conditions are combined with
AND
. If you need to use
OR
, you can pass a special key
logic
with the value
OR
.
You can add a prefix to the
field_n
keys to clarify the filter operation.
Possible prefix values:
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
symbol in the filter value should not be passed. The search looks for a substring in any position of the string
=%
— LIKE, substring search. The
%
symbol should be passed in the value. Examples:
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
symbol in the filter value should not be passed. The search goes from both sides
!=%
— NOT LIKE, substring search. The
%
symbol should be passed in the value. Examples:
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
A list of all available fields for filtering can be obtained using the
crm.item.fields
method. A list of standard fields is available in the article
CRM Object Fields
order
object
Object format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where
field_n
— field name by which the selection of elements will be sorted
value_n
— value of type
string
equal to:
ASC
— ascending sort
DESC
— descending sort
A list of all available fields for sorting can be obtained using the
crm.item.fields
method. A list of standard fields is available in the article
CRM Object Fields
start
integer
This parameter is used to control pagination.
The page size of results is always static — 50 records.
To select the second page of results, pass the value
50
. To select the third page of results — the value
100
, and so on.
The formula for calculating the
start
parameter value:
start = (N-1) * 50
, where
N
— the desired page number
useOriginalUfNames
boolean
This parameter controls the format of user field names in the request and response.
Possible values:
Y
— original names of user fields, e.g.,
UF_CRM_2_1639669411830
N
— user field names in camelCase, e.g.,
ufCrm2_1639669411830
Default —
N
Code Examples
Code Examples
Get a list of leads where:
First name or last name is not empty
Are in the status "In Progress" or "Unprocessed".
Came from sources "Advertising" or "Website".
Are assigned to managers with IDs 1 or 6.
Have a deal amount from 5000 to 20000.
The calculation mode for the amount is manual.
Set the following sort order for this selection:
First name and last name in ascending order.
For clarity, we will choose only the fields we need:
Identifier
id
Title
title
First name
name
Last name
lastName
Stage identifier
stageId
Source identifier
sourceId
Responsible identifier
assignedById
Amount
opportunity
Amount calculation mode
isManualOpportunity
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
'{"entityTypeId":1,"select":["id","title","lastName","name","stageId","sourceId","assignedById","opportunity","isManualOpportunity"],"filter":{"0":{"logic":"OR","0":{"!=name":""},"1":{"!=lastName":""}},"@stageId":["NEW","IN_PROCESS"],"@sourceId":["WEB","ADVERTISING"],"@assignedById":[1,6],">=opportunity":5000,"<=opportunity":20000,"isManualOpportunity":"Y"},"order":{"lastName":"ASC","name":"ASC"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1,"select":["id","title","lastName","name","stageId","sourceId","assignedById","opportunity","isManualOpportunity"],"filter":{"0":{"logic":"OR","0":{"!=name":""},"1":{"!=lastName":""}},"@stageId":["NEW","IN_PROCESS"],"@sourceId":["WEB","ADVERTISING"],"@assignedById":[1,6],">=opportunity":5000,"<=opportunity":20000,"isManualOpportunity":"Y"},"order":{"lastName":"ASC","name":"ASC"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 elements). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.item.list'
,
{
entityTypeId
:
1
,
select
: [
"id"
,
"title"
,
"lastName"
,
"name"
,
"stageId"
,
"sourceId"
,
"assignedById"
,
"opportunity"
,
"isManualOpportunity"
,
],
filter
: {
"0"
: {
logic
:
"OR"
,
"0"
: {
"!=name"
:
""
,
},
"1"
: {
"!=lastName"
:
""
,
},
},
"@stageId"
: [
"NEW"
,
"IN_PROCESS"
],
"@sourceId"
: [
'WEB'
,
"ADVERTISING"
],
"@assignedById"
: [
1
,
6
],
">=opportunity"
:
5000
,
"<=opportunity"
:
20000
,
"isManualOpportunity"
:
"Y"
,
},
order
: {
lastName
:
'ASC'
,
name
:
'ASC'
,
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.item.list'
, {
entityTypeId
:
1
,
select
: [
"id"
,
"title"
,
"lastName"
,
"name"
,
"stageId"
,
"sourceId"
,
"assignedById"
,
"opportunity"
,
"isManualOpportunity"
,
],
filter
: {
"0"
: {
logic
:
"OR"
,
"0"
: {
"!=name"
:
""
,
},
"1"
: {
"!=lastName"
:
""
,
},
},
"@stageId"
: [
"NEW"
,
"IN_PROCESS"
],
"@sourceId"
: [
'WEB'
,
"ADVERTISING"
],
"@assignedById"
: [
1
,
6
],
">=opportunity"
:
5000
,
"<=opportunity"
:
20000
,
"isManualOpportunity"
:
"Y"
,
},
order
: {
lastName
:
'ASC'
,
name
:
'ASC'
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.list'
, {
entityTypeId
:
1
,
select
: [
"id"
,
"title"
,
"lastName"
,
"name"
,
"stageId"
,
"sourceId"
,
"assignedById"
,
"opportunity"
,
"isManualOpportunity"
,
],
filter
: {
"0"
: {
logic
:
"OR"
,
"0"
: {
"!=name"
:
""
,
},
"1"
: {
"!=lastName"
:
""
,
},
},
"@stageId"
: [
"NEW"
,
"IN_PROCESS"
],
"@sourceId"
: [
'WEB'
,
"ADVERTISING"
],
"@assignedById"
: [
1
,
6
],
">=opportunity"
:
5000
,
"<=opportunity"
:
20000
,
"isManualOpportunity"
:
"Y"
,
},
order
: {
lastName
:
'ASC'
,
name
:
'ASC'
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
$entityTypeId
=
1
;
// Replace with actual entity type ID
$order
= [];
// Replace with actual order array
$filter
= [];
// Replace with actual filter array
$select
= [];
// Replace with actual select array
$startItem
=
0
;
// Optional, can be adjusted as needed
$itemsResult
=
$serviceBuilder
->
getCRMScope
()
->
item
()
->
list
(
$entityTypeId
,
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
$itemsResult
->
getItems
()
as
$item
) {
print
(
"ID: "
.
$item
->id . PHP_EOL);
print
(
"XML ID: "
.
$item
->xmlId . PHP_EOL);
print
(
"Title: "
.
$item
->title . PHP_EOL);
print
(
"Created By: "
.
$item
->createdBy . PHP_EOL);
print
(
"Updated By: "
.
$item
->updatedBy . PHP_EOL);
print
(
"Created Time: "
.
$item
->createdTime->
format
(DATE_ATOM) . PHP_EOL);
print
(
"Updated Time: "
.
$item
->updatedTime->
format
(DATE_ATOM) . PHP_EOL);
// Add more fields as necessary
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
() . PHP_EOL);
}
BX24
.
callMethod
(
'crm.item.list'
,
{
entityTypeId
:
1
,
select
: [
"id"
,
"title"
,
"lastName"
,
"name"
,
"stageId"
,
"sourceId"
,
"assignedById"
,
"opportunity"
,
"isManualOpportunity"
,
],
filter
: {
"0"
: {
logic
:
"OR"
,
"0"
: {
"!=name"
:
""
,
},
"1"
: {
"!=lastName"
:
""
,
},
},
"@stageId"
: [
"NEW"
,
"IN_PROCESS"
],
"@sourceId"
: [
'WEB'
,
"ADVERTISING"
],
"@assignedById"
: [
1
,
6
],
">=opportunity"
:
5000
,
"<=opportunity"
:
20000
,
"isManualOpportunity"
:
"Y"
,
},
order
: {
lastName
:
'ASC'
,
name
:
'ASC'
,
},
},
(
result
) =>
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
return
;
}
console
.
info
(result.
data
());
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
'crm.item.list'
,
[
'entityTypeId'
=>
1
,
'select'
=> [
"id"
,
"title"
,
"lastName"
,
"name"
,
"stageId"
,
"sourceId"
,
"assignedById"
,
"opportunity"
,
"isManualOpportunity"
,
],
'filter'
=> [
"0"
=> [
"logic"
=>
"OR"
,
"0"
=> [
"!=name"
=>
""
,
],
"1"
=> [
"!=lastName"
=>
""
,
],
],
"@stageId"
=> [
"NEW"
,
"IN_PROCESS"
],
"@sourceId"
=> [
'WEB'
,
"ADVERTISING"
],
"@assignedById"
=> [
1
,
6
],
">=opportunity"
=>
5000
,
"<=opportunity"
=>
20000
,
"isManualOpportunity"
=>
"Y"
,
],
'order'
=> [
'lastName'
=>
'ASC'
,
'name'
=>
'ASC'
,
],
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
Example request with date filter using OR logic
Example request with date filter using OR logic
Filter deals
entityTypeId = 2
by two creation dates. For each date, set the start and end of the day range.
For clarity, we will choose only the fields we need:
Identifier
id
Title
title
Creation date
createdTime
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
'{"entityTypeId":2,"select":["id","title","createdTime"],"filter":{"0":{"logic":"OR","0":{">=createdTime":"2025-10-31T00:00:00+02:00","<createdTime":"2025-11-01T00:00:00+02:00"},"1":{">=createdTime":"2025-02-28T00:00:00+02:00","<createdTime":"2025-03-01T00:00:00+02:00"}}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"select":["id","title","createdTime"],"filter":{"0":{"logic":"OR","0":{">=createdTime":"2025-10-31T00:00:00+02:00","<createdTime":"2025-11-01T00:00:00+02:00"},"1":{">=createdTime":"2025-02-28T00:00:00+02:00","<createdTime":"2025-03-01T00:00:00+02:00"}}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.list
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.list'
,
{
entityTypeId
:
2
,
select
: [
'id'
,
'title'
,
'createdTime'
],
filter
: {
'0'
: {
logic
:
'OR'
,
'0'
: {
'>=createdTime'
:
'2025-10-31T00:00:00+02:00'
,
'<createdTime'
:
'2025-11-01T00:00:00+02:00'
,
},
'1'
: {
'>=createdTime'
:
'2025-02-28T00:00:00+02:00'
,
'<createdTime'
:
'2025-03-01T00:00:00+02:00'
,
},
},
},
},
);
const
items = response.
getData
().
items
|| [];
items.
forEach
(
(
item
) =>
{
console
.
info
(
`Deal #
${item.id}
:
${item.title}
(
${item.createdTime}
)`
);
});
}
catch
(error) {
console
.
error
(
'crm.item.list error'
, error);
}
try
{
$entityTypeId
=
2
;
$order
= [];
$filter
= [
"0"
=> [
"logic"
=>
"OR"
,
"0"
=> [
">=createdTime"
=>
"2025-10-31T00:00:00+02:00"
,
"<createdTime"
=>
"2025-11-01T00:00:00+02:00"
,
],
"1"
=> [
">=createdTime"
=>
"2025-02-28T00:00:00+02:00"
,
"<createdTime"
=>
"2025-03-01T00:00:00+02:00"
,
],
],
];
$select
= [
'id'
,
'title'
,
'createdTime'
];
$startItem
=
0
;
$itemsResult
=
$serviceBuilder
->
getCRMScope
()
->
item
()
->
list
(
$entityTypeId
,
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
$itemsResult
->
getItems
()
as
$item
) {
print
(
"ID: "
.
$item
->id . PHP_EOL);
print
(
"Title: "
.
$item
->title . PHP_EOL);
print
(
"Created Time: "
.
$item
->createdTime->
format
(DATE_ATOM) . PHP_EOL);
print
(PHP_EOL);
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
() . PHP_EOL);
}
BX24
.
callMethod
(
'crm.item.list'
,
{
entityTypeId
:
2
,
select
: [
'id'
,
'title'
,
'createdTime'
],
filter
: {
'0'
: {
logic
:
'OR'
,
'0'
: {
'>=createdTime'
:
'2025-10-31T00:00:00+02:00'
,
'<createdTime'
:
'2025-11-01T00:00:00+02:00'
,
},
'1'
: {
'>=createdTime'
:
'2025-02-28T00:00:00+02:00'
,
'<createdTime'
:
'2025-03-01T00:00:00+02:00'
,
},
},
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
(
'crm.item.list error'
, result.
error
());
return
;
}
const
{ items } = result.
data
();
items.
forEach
(
(
item
) =>
{
console
.
log
(
`Deal #
${item.id}
:
${item.title}
(
${item.createdTime}
)`
);
});
if
(result.
more
()) {
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
'crm.item.list'
,
[
'entityTypeId'
=>
2
,
'select'
=> [
'id'
,
'title'
,
'createdTime'
],
'filter'
=> [
"0"
=> [
"logic"
=>
"OR"
,
"0"
=> [
">=createdTime"
=>
"2025-10-31T00:00:00+02:00"
,
"<createdTime"
=>
"2025-11-01T00:00:00+02:00"
,
],
"1"
=> [
">=createdTime"
=>
"2025-02-28T00:00:00+02:00"
,
"<createdTime"
=>
"2025-03-01T00:00:00+02:00"
,
],
],
],
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
"items"
:
[
{
"id"
:
253
,
"assignedById"
:
6
,
"stageId"
:
"NEW"
,
"opportunity"
:
19000
,
"sourceId"
:
"WEB"
,
"title"
:
"Lead #253"
,
"name"
:
"Admin"
,
"lastName"
:
null
,
"isManualOpportunity"
:
"Y"
}
,
{
"id"
:
255
,
"assignedById"
:
1
,
"stageId"
:
"NEW"
,
"opportunity"
:
19600
,
"sourceId"
:
"WEB"
,
"title"
:
"Lead #255"
,
"name"
:
"John"
,
"lastName"
:
"Doe"
,
"isManualOpportunity"
:
"Y"
}
,
{
"id"
:
252
,
"assignedById"
:
1
,
"stageId"
:
"NEW"
,
"opportunity"
:
12000
,
"sourceId"
:
"ADVERTISING"
,
"title"
:
"Lead #252"
,
"name"
:
"John"
,
"lastName"
:
"Smith"
,
"isManualOpportunity"
:
"Y"
}
,
{
"id"
:
254
,
"assignedById"
:
6
,
"stageId"
:
"IN_PROCESS"
,
"opportunity"
:
19000
,
"sourceId"
:
"ADVERTISING"
,
"title"
:
"Lead #254"
,
"name"
:
"Cat"
,
"lastName"
:
"Smith"
,
"isManualOpportunity"
:
"Y"
}
]
}
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
1721724354.214286
,
"finish"
:
1721724354.805263
,
"duration"
:
0.5909769535064697
,
"processing"
:
0.24513697624206543
,
"date_start"
:
"2024-07-23T10:45:54+02:00"
,
"date_finish"
:
"2024-07-23T10:45:54+02:00"
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
Root element of the response. Contains a single key
items
items
item[]
Array with information about found elements.
Returned fields depend on the
select
parameter,
field description
total
integer
Total number of found elements
next
integer
Contains the value to be passed in the next request in the
start
parameter to get the next batch of data.
The
next
parameter appears in the response if the number of elements matching your request exceeds
50
.
time
time
Information about the execution time of the request
By default, user field names are passed and returned in camelCase, e.g.,
ufCrm2_1639669411830
.
When passing the
useOriginalUfNames
parameter with the value
Y
, user fields will be returned with their original names, e.g.,
UF_CRM_2_1639669411830
.
Error Handling
Error Handling
HTTP status:
400
,
403
{
"error"
:
"INVALID_ARG_VALUE"
,
"error_description"
:
"Invalid filter: field 'FIELD' is not allowed in filter"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action allowed only for intranet users
User is not an intranet user
400
NOT_FOUND
Smart process not found
Occurs when an invalid
entityTypeId
is passed
400
INVALID_ARG_VALUE
Invalid filter: field '
field
' is not allowed in filter
The field
field
passed in
filter
is not available for filtering
400
INVALID_ARG_VALUE
Invalid filter: field '
field
' has invalid value
The value passed for the field
field
in
filter
is incorrect
400
INVALID_ARG_VALUE
Invalid order: field '
field
' is not allowed in order
The field
field
passed in
order
is not available for sorting
400
INVALID_ARG_VALUE
Invalid order: allowed sort directions are
ASC, DESC
. But got '
orderValue
' for field '
field
'
The value
orderValue
passed for the field
field
in the
order
parameter is incorrect
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
Create a new CRM entity crm.item.add
Update CRM Item: crm.item.update
Get Item by Id crm.item.get
Delete CRM Item - crm.item.delete
Get Fields of CRM Item `crm.item.fields`
CRM Object Fields
How to Attach a Task to a SPA
How to Filter Items by Stage Name
How to Get a List of Activities from Deals
How to Get a List of Vendors
Copied
Was the article helpful?
Yes
No
Previous
Get Entity by Id
Next
Delete Entity

---

## Delete CRM Item - crm.item.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/crm-item-delete

Delete CRM Item - crm.item.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete CRM Item - crm.item.delete
Method Parameters
Code Examples
Response Handling
Returned Values
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with the "delete" access permission for CRM object items
This method deletes a CRM object item by its item ID and item type ID.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
The ID of the
system
or
user-defined type
whose item we want to delete
id
*
integer
The ID of the item to be deleted.
This can be obtained using the
crm.item.list
method or when creating an item with
crm.item.add
Code Examples
Code Examples
How to Use Examples in Documentation
Deleting an item with
id = 1
, belonging to a smart process with
entityTypeId = 1268
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
'{"entityTypeId":1268,"id":1}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1268,"id":1,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.delete'
,
{
entityTypeId
:
1268
,
id
:
1
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
'crm.item.delete'
,
[
'entityTypeId'
=>
1268
,
'id'
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
return
;
}
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
'Error deleting item: '
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
'crm.item.delete'
,
{
entityTypeId
:
1268
,
id
:
1
,
},
(
result
) =>
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
return
;
}
console
.
info
(result.
data
());
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
'crm.item.delete'
,
[
'entityTypeId'
=>
1268
,
'id'
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
]
,
"time"
:
{
"start"
:
1721657688.755373
,
"finish"
:
1721657689.65017
,
"duration"
:
0.8947970867156982
,
"processing"
:
0.6092040538787842
,
"date_start"
:
"2024-07-22T16:14:48+02:00"
,
"date_finish"
:
"2024-07-22T16:14:49+02:00"
,
"operating"
:
0
}
}
Returned Values
Returned Values
Name
type
Description
result
array
The root element of the response.
Returns an empty array
[]
in case of success
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
400
,
403
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Item not found"
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
allowed_only_intranet_user
Action allowed only for intranet users
User is not an intranet user
NOT_FOUND
Smart process not found
Occurs when an invalid
entityTypeId
is passed
NOT_FOUND
Item not found
An item with the given
id
of type
entityTypeId
does not exist
ACCESS_DENIED
Access denied
User does not have permission to delete items of type
entityTypeId
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
Create a new CRM entity crm.item.add
Update CRM Item: crm.item.update
Get Item by Id crm.item.get
Get a list of crm.item.list elements
Get Fields of CRM Item `crm.item.fields`
CRM Object Fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of Entities
Next
Get Entity Fields

---

## Get Fields of CRM Item <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-dvfugi04">crm.item.fields</code>

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/crm-item-fields

Get Fields of CRM Item <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-dvfugi04">crm.item.fields</code> | Bitrix24 REST API and Marketplace Applications
Get Fields of CRM Item <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-dvfugi04">crm.item.fields</code>
Get Fields of CRM Item
crm.item.fields
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
Who can execute the method: any user with "read" access permission for CRM object elements
This method retrieves a list of fields and their configuration for elements of type
entityTypeId
.
Warning
Elements belonging to different types of CRM objects will have different sets of fields.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the
system
or
custom type
whose fields we want to retrieve
useOriginalUfNames
boolean
This parameter controls the format of custom field names in the response.
Possible values:
Y
— original names of custom fields, e.g.,
UF_CRM_2_1639669411830
N
— custom field names in camelCase, e.g.,
ufCrm2_1639669411830
Default is
N
Code Examples
Code Examples
How to Use Examples in Documentation
Get the list of fields for elements of the SPA with
entityTypeId = 1268
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
'{"entityTypeId":1268,"useOriginalUfNames":"N"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.fields
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":1268,"useOriginalUfNames":"N","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.fields
try
{
const
response =
await
$b24.
callMethod
(
'crm.item.fields'
,
{
entityTypeId
:
1268
,
useOriginalUfNames
:
'N'
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
'crm.item.fields'
,
[
'entityTypeId'
=>
1268
,
'useOriginalUfNames'
=>
'N'
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
return
;
}
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
'Error fetching CRM item fields: '
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
'crm.item.fields'
,
{
entityTypeId
:
1268
,
useOriginalUfNames
:
'N'
,
},
(
result
) =>
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
return
;
}
console
.
info
(result.
data
());
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
'crm.item.fields'
,
[
'entityTypeId'
=>
1268
,
'useOriginalUfNames'
=>
'N'
,
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
,
"upperName"
:
"ID"
}
,
"title"
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
,
"upperName"
:
"TITLE"
}
,
"xmlId"
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
,
"upperName"
:
"XML_ID"
}
,
"createdTime"
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
"Created Time"
,
"upperName"
:
"CREATED_TIME"
}
,
"updatedTime"
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
"Updated Time"
,
"upperName"
:
"UPDATED_TIME"
}
,
"createdBy"
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
,
"upperName"
:
"CREATED_BY"
}
,
"updatedBy"
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
"Updated By"
,
"upperName"
:
"UPDATED_BY"
}
,
"assignedById"
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
,
"upperName"
:
"ASSIGNED_BY_ID"
}
,
"opened"
:
{
"type"
:
"boolean"
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
"Available to All"
,
"upperName"
:
"OPENED"
}
,
"webformId"
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
"Created by CRM Form"
,
"upperName"
:
"WEBFORM_ID"
}
,
"begindate"
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
"Start Date"
,
"upperName"
:
"BEGINDATE"
}
,
"closedate"
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
"End Date"
,
"upperName"
:
"CLOSEDATE"
}
,
"companyId"
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
,
"settings"
:
{
"parentEntityTypeId"
:
4
}
,
"upperName"
:
"COMPANY_ID"
}
,
"contactId"
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
,
"upperName"
:
"CONTACT_ID"
}
,
"contactIds"
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
,
"upperName"
:
"CONTACT_IDS"
}
,
"contacts"
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
"CONTACTS"
,
"upperName"
:
"CONTACTS"
}
,
"observers"
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
true
,
"isDynamic"
:
false
,
"title"
:
"Observers"
,
"upperName"
:
"OBSERVERS"
}
,
"categoryId"
:
{
"type"
:
"crm_category"
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
"Sales Funnel"
,
"upperName"
:
"CATEGORY_ID"
}
,
"movedTime"
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
"Moved Time"
,
"upperName"
:
"MOVED_TIME"
}
,
"movedBy"
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
"Moved By"
,
"upperName"
:
"MOVED_BY"
}
,
"stageId"
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
"DYNAMIC_1268_STAGE_52"
,
"title"
:
"Stage"
,
"upperName"
:
"STAGE_ID"
}
,
"previousStageId"
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
"statusType"
:
"DYNAMIC_1268_STAGE_52"
,
"title"
:
"Previous Stage"
,
"upperName"
:
"PREVIOUS_STAGE_ID"
}
,
"sourceId"
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
"SOURCE"
,
"title"
:
"Source"
,
"upperName"
:
"SOURCE_ID"
}
,
"sourceDescription"
:
{
"type"
:
"text"
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
"Additional Information about the Source"
,
"upperName"
:
"SOURCE_DESCRIPTION"
}
,
"currencyId"
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
,
"upperName"
:
"CURRENCY_ID"
}
,
"isManualOpportunity"
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
false
,
"title"
:
"Manual Opportunity Mode"
,
"upperName"
:
"IS_MANUAL_OPPORTUNITY"
}
,
"opportunity"
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
,
"upperName"
:
"OPPORTUNITY"
}
,
"taxValue"
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
"Tax Amount"
,
"upperName"
:
"TAX_VALUE"
}
,
"mycompanyId"
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
,
"settings"
:
{
"isMyCompany"
:
true
,
"parentEntityTypeId"
:
4
,
"isEmbeddedEditorEnabled"
:
true
}
,
"upperName"
:
"MYCOMPANY_ID"
}
,
"lastActivityBy"
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
"Last Activity By"
,
"upperName"
:
"LAST_ACTIVITY_BY"
}
,
"lastActivityTime"
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
"Last Activity"
,
"upperName"
:
"LAST_ACTIVITY_TIME"
}
,
"parentId1"
:
{
"type"
:
"crm_entity"
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
,
"settings"
:
{
"parentEntityTypeId"
:
1
}
,
"upperName"
:
"PARENT_ID_1"
}
,
"parentId2"
:
{
"type"
:
"crm_entity"
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
,
"settings"
:
{
"parentEntityTypeId"
:
2
}
,
"upperName"
:
"PARENT_ID_2"
}
,
"parentId1248"
:
{
"type"
:
"crm_entity"
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
"SPA #16"
,
"settings"
:
{
"parentEntityTypeId"
:
1248
}
,
"upperName"
:
"PARENT_ID_1248"
}
}
}
,
"time"
:
{
"start"
:
1721038185.626335
,
"finish"
:
1721038186.072804
,
"duration"
:
0.4464690685272217
,
"processing"
:
0.17344903945922852
,
"date_start"
:
"2024-07-15T12:09:45+02:00"
,
"date_finish"
:
"2024-07-15T12:09:46+02:00"
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
The root element of the response. Contains a single key
fields
fields
object
An object in the format:
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
By default, custom field names are returned in camelCase, e.g.,
ufCrm2_1639669411830
.
When passing the parameter
useOriginalUfNames
with the value
Y
, custom fields will be returned with their original names, e.g.,
UF_CRM_2_1639669411830
.
Error Handling
Error Handling
HTTP Status:
400
,
403
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"SPA not found"
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
Status
Code
Description
Value
403
allowed_only_intranet_user
Action allowed only for intranet users
User is not an intranet user
400
NOT_FOUND
SPA not found
Occurs when an invalid
entityTypeId
is passed
400
ACCESS_DENIED
You do not have permission to view this element
User does not have read access permission for elements of type
entityTypeId
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
Create a new CRM entity crm.item.add
Update CRM Item: crm.item.update
Get Item by Id crm.item.get
Get a list of crm.item.list elements
Delete CRM Item - crm.item.delete
CRM Object Fields
Copied
Was the article helpful?
Yes
No
Previous
Delete Entity
Next
CRM Object Fields

---

## CRM Object Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/object-fields

CRM Object Fields | Bitrix24 REST API and Marketplace Applications
CRM Object Fields
CRM Object Fields
Common Fields
Object Fields
Lead
Deal
Contact
Company
Estimate
Invoice
SPA
In the section
common fields
, you will find a list of standard fields used across all types of CRM objects.
The sections for each object type provide lists of standard fields specific to that object type:
lead
,
deal
,
contact
,
company
,
estimate
,
invoice
,
SPA
.
Use the method
crm.item.fields
with the specified
object type
in
entityTypeId
to get a complete list of fields for the object, including custom fields.
Common Fields
Common Fields
Name
type
Description
assignedById
user
Identifier of the user responsible for the item
createdBy
user
Identifier of the user who created the item
createdTime
datetime
Time of item creation
entityTypeId
integer
Identifier of the entity type
id
integer
Identifier of the item
lastActivityBy
user
Identifier of the user who last interacted in the timeline
lastActivityTime
datetime
Time of the last activity in the timeline
opened
boolean
Is the item open
parentId...
crm_entity
Parent field. An element of another CRM object type that is linked to this item.
Each such field has the code
parentId + {parentEntityTypeId}
ufCrm...
crm_userfield
Custom field. See the section
Custom Fields in CRM
.
Values of multiple fields are returned as an array
Value of the
file
type field is returned as an object:
id
— identifier
url
— link to the file on the account
urlMachine
— link to the file for the application
updatedBy
user
Identifier of the user who modified the item
updatedTime
datetime
Time of the last modification of the item
utmCampaign
string
Identifier of the advertising campaign
utmContent
string
Content of the campaign.
For example, for contextual ads
utmMedium
string
Type of traffic. Possible values:
CPC — ads
CPM — banners
utmSource
string
Advertising system. Google Ads and others
utmTerm
string
Search condition of the campaign.
For example, keywords for contextual advertising
webformId
integer
Identifier of the CRM form
Object Fields
Object Fields
Lead
Lead
Name
type
Description
dateCreateShort
datetime
Time of item creation (short format).
Field is disabled
dateModifyShort
datetime
Time of the last modification of the item (short format).
Field is disabled
companyId
crm_company
Identifier of the company linked to the item
contactId
crm_contact
Identifier of the contact linked to the item
stageId
crm_status
String identifier of the item's stage
isConvert
boolean
Has the lead been converted.
Field is disabled
statusDescription
text
Additional information about the stage
stageSemanticId
string
Group of the stage. Possible values:
P
— in progress
S
— successful
F
— unsuccessful
productId
string
Identifier of the product.
Deprecated.
Field is disabled
opportunity
double
Amount
currencyId
crm_currency
Identifier of the item's currency
sourceId
crm_status
String identifier of the source type
sourceDescription
text
Additional information about the source
title
string
Name of the item
name
string
First name
lastName
string
Last name
secondName
string
Middle name
shortName
string
Last name First name.
Short format: for example 'Smith John' -> 'Smith J.'.
Field is disabled
companyTitle
string
Company name
post
string
Position
address
text
Address.
Deprecated.
Field is disabled
comments
text
Comment
originatorId
string
External source
originId
string
Identifier of the item in the external source
dateClosed
datetime
Time of item closure
birthdate
date
Date of birth
honorific
crm_status
String identifier of the salutation type
hasPhone
boolean
Does the item have a phone
hasEmail
boolean
Does the item have an email
hasImol
boolean
Does the item have open channels
login
string
Login.
Deprecated.
Field is disabled
isReturnCustomer
boolean
Is the item a repeat customer
searchContent
text
Information for full-text search.
System field
isManualOpportunity
boolean
Is manual mode for calculating the amount set
movedBy
user
Identifier of the user who last changed the stage
movedTime
datetime
Time of the last stage change
phoneMobile
string
Mobile phone
phoneWork
string
Work phone
phoneMailing
string
Mailing phone
emailHome
string
Personal E-mail
emailWork
string
Work E-mail
emailMailing
string
Mailing email
skype
string
Skype
icq
string
ICQ
imol
string
IMOL
email
string
E-mail
phone
string
Phone
observers
user[]
List of user identifiers who are Observers
contactIds
crm_contact[]
List of contact identifiers linked to the item
fm
multifield
Array of multifields.
More about multifields can be found in the section
crm_multifield
Structure of the multifield:
id
— Unique identifier
typeId
— Type of multifield
valueType
— Type of value
value
— Value
Deal
Deal
Name
type
Description
dateCreateShort
datetime
Time of item creation (short format).
Field is disabled
dateModifyShort
datetime
Time of the last modification of the item (short format).
Field is disabled
leadId
crm_lead
Identifier of the lead based on which the item was created
companyId
crm_company
Identifier of the company linked to the item
contactId
crm_contact
Identifier of the contact linked to the item
quoteId
crm_quote
Identifier of the estimate linked to the item
title
string
Name of the item
productId
string
Identifier of the product.
Deprecated. Field is disabled
categoryId
crm_category
Identifier of the funnel (direction) of the item
stageId
crm_status
String identifier of the item's stage
stageSemanticId
string
Group of the stage
P
— in progress
S
— successful
F
— unsuccessful
isNew
boolean
Is the deal new
isRecurring
boolean
Is the deal recurring
isReturnCustomer
boolean
Is the item a repeat customer
isRepeatedApproach
boolean
Is the deal a repeated approach
closed
boolean
Is the deal closed
typeId
crm_status
String identifier of the deal type
opportunity
double
Amount
isManualOpportunity
boolean
Is manual mode for calculating the amount set
taxValue
double
Tax amount
currencyId
crm_currency
Identifier of the item's currency
probability
integer
Probability, %
comments
text
Comment
begindate
date
Start date of the item
begindateShort
datetime
Start time of the item (short format).
Field is disabled
closedate
date
Completion date of the item
closedateShort
datetime
End time of the item (short format).
Field is disabled
eventDate
datetime
Event date
eventDateShort
datetime
Event date (short format).
Field is disabled
eventId
crm_status
String identifier of the event type
eventDescription
text
Description of the event
locationId
location
Identifier of the location.
System field
sourceId
crm_status
String identifier of the source type
sourceDescription
text
Additional information about the source
originatorId
string
External source
originId
string
Identifier of the item in the external source
additionalInfo
string
Additional information
searchContent
text
Information for full-text search.
System field
orderStage
string
Payment status of the deal
movedBy
user
Identifier of the user who last changed the stage
movedTime
datetime
Time of the last stage change
isWork
boolean
Is the deal in progress.
Field is disabled
isWon
boolean
Is the deal won.
Field is disabled
isLose
boolean
Is the deal lost.
Field is disabled
receivedAmount
string
Amount received.
Field is disabled
lostAmount
string
Amount lost.
Field is disabled
hasProducts
boolean
Does the item contain products.
Field is disabled
observers
user[]
List of user identifiers who are Observers
contactIds
crm_contact[]
List of contact identifiers linked to the item
Contact
Contact
Name
type
Description
companyId
crm_company
Identifier of the company linked to the item
sourceId
crm_status
String identifier of the source type
sourceDescription
text
Additional information about the source
name
string
First name
lastName
string
Last name
secondName
string
Middle name
shortName
string
Last name First name.
Short format: for example 'Smith John' -> 'Smith J.'.
Field is disabled
photo
file
Photo
post
string
Position
address
text
Address.
Deprecated. Field is disabled
comments
text
Comment
leadId
crm_lead
Identifier of the lead based on which the item was created
export
boolean
Is exporting the contact allowed
typeId
crm_status
String identifier of the deal type
originatorId
string
External source
originId
string
Identifier of the item in the external source
originVersion
string
Version of the original
birthdate
date
Date of birth
honorific
crm_status
String identifier of the salutation type
hasPhone
boolean
Does the item have a phone
hasEmail
boolean
Does the item have an email
hasImol
boolean
Does the item have open channels
searchContent
text
Information for full-text search. System field
categoryId
crm_category
Identifier of the funnel (direction) of the item
login
string
Login.
Deprecated. Field is disabled
emailHome
string
Personal E-mail
emailWork
string
Work E-mail
emailMailing
string
Mailing email
phoneMobile
string
Mobile phone
phoneWork
string
Work phone
phoneMailing
string
Mailing phone
imol
string
IMOL
email
string
E-mail
phone
string
Phone
observers
user[]
List of user identifiers who are Observers
companyIds
crm_company[]
List of company identifiers linked to the item
fm
multifield
Array of multifields.
More about multifields can be found in the section
crm_multifield
Structure of the multifield:
id
— Unique identifier
typeId
— Type of multifield
valueType
— Type of value
value
— Value
Company
Company
Name
type
Description
title
string
Name of the item
logo
file
Logo
address
text
Address.
Deprecated. Field is disabled
addressLegal
text
Legal address.
Deprecated
bankingDetails
string
Banking details
comments
text
Comment
typeId
crm_status
String identifier of the deal type
industry
crm_status
String identifier of the industry type
revenue
double
Annual turnover
currencyId
crm_currency
Identifier of the item's currency
employees
crm_status
String identifier of the number of employees type
leadId
crm_lead
Identifier of the lead based on which the item was created
originatorId
string
External source
originId
string
Identifier of the item in the external source
originVersion
string
Version of the original
hasPhone
boolean
Does the item have a phone
hasEmail
boolean
Does the item have an email
hasImol
boolean
Does the item have open channels
isMyCompany
boolean
Is the company my company
searchContent
text
Information for full-text search.
System field
categoryId
crm_category
Identifier of the funnel (direction) of the item
emailHome
string
Personal E-mail
emailWork
string
Work E-mail
emailMailing
string
Mailing email
phoneMobile
string
Mobile phone
phoneWork
string
Work phone
phoneMailing
string
Mailing phone
imol
string
IMOL
email
string
E-mail
phone
string
Phone
ufLogo
file
Logo (document generator)
ufStamp
file
Company seal (document generator)
ufDirectorSign
file
Director's signature (document generator)
ufAccountantSign
file
Chief accountant's signature (document generator)
observers
user[]
List of user identifiers who are Observers
contactIds
crm_contact[]
List of contact identifiers linked to the item
fm
multifield
Array of multifields.
More about multifields can be found in the section
crm_multifield
Structure of the multifield:
id
— Unique identifier
typeId
— Type of multifield
valueType
— Type of value
value
— Value
Estimate
Estimate
Name
type
Description
dateCreateShort
datetime
Time of item creation (short format).
Field is disabled
dateModifyShort
datetime
Time of the last modification of the item (short format).
Field is disabled
leadId
crm_lead
Identifier of the lead based on which the item was created
dealId
crm_deal
Identifier of the deal linked to the item
companyId
crm_company
Identifier of the company linked to the item
contactId
crm_contact
Identifier of the contact linked to the item
personTypeId
integer
Identifier of the payer type
mycompanyId
crm_company
Identifier of "my" company
title
string
Name of the item
stageId
crm_status
String identifier of the item's stage
closed
boolean
Is the deal closed
opportunity
double
Amount
isManualOpportunity
boolean
Is manual mode for calculating the amount set
taxValue
double
Tax amount
currencyId
crm_currency
Identifier of the item's currency
comments
text
Comment
commentsType
integer
Identifier of the comment type.
Possible values:
0
— unknown
1
— text
2
— bb-code
3
— HTML
begindate
date
Start date of the item
begindateShort
datetime
Start time of the item (short format).
Field is disabled
closedate
date
Completion date of the item
closedateShort
datetime
End time of the item (short format).
Field is disabled
quoteNumber
string
Estimate number
content
text
Content
contentType
integer
Identifier of the content type.
Possible values:
0
— unknown
1
— text
2
— bb-code
3
— HTML
terms
text
Terms
termsType
integer
Identifier of the terms type.
Possible values:
0
— unknown
1
— text
2
— bb-code
3
— HTML
storageTypeId
integer
Identifier of the storage type
storageElementIds
integer[]
Array of files
locationId
location
Identifier of the location. System field
clientTitle
string
Client name
clientAddr
string
Client address
clientContact
string
Client contacts
clientEmail
string
Client E-mail
clientPhone
string
Client phone
clientTpId
string
Client TIN
clientTpaId
string
Client TPP
searchContent
text
Information for full-text search. System field
hasProducts
boolean
Does the item contain products.
Field is disabled
actualDate
date
Valid until
contactIds
crm_contact[]
List of contact identifiers linked to the item
Invoice
Invoice
Name
type
Description
xmlId
string
External code
title
string
Name of the item
movedBy
user
Identifier of the user who last changed the stage
movedTime
datetime
Time of the last stage change
categoryId
crm_category
Identifier of the funnel (direction) of the item
stageId
crm_status
String identifier of the item's stage
previousStageId
crm_status
Identifier of the previous stage type
begindate
date
Start date of the item
closedate
date
Completion date of the item
companyId
crm_company
Identifier of the company linked to the item
contactId
crm_contact
Identifier of the contact linked to the item
opportunity
double
Amount
isManualOpportunity
boolean
Is manual mode for calculating the amount set
taxValue
double
Tax amount
currencyId
crm_currency
Identifier of the item's currency
mycompanyId
crm_company
Identifier of "my" company
sourceId
crm_status
String identifier of the source type
sourceDescription
text
Additional information about the source
comments
text
Comment
accountNumber
string
Invoice number
locationId
location
Identifier of the location.
System field
observers
user[]
List of user identifiers who are Observers
contactIds
crm_contact[]
List of contact identifiers linked to the item
SPA
SPA
Name
type
Description
xmlId
string
External code
title
string
Name of the item
movedBy
user
Identifier of the user who last changed the stage.
Available only when the
isStagesEnabled
setting is enabled for the corresponding SPA
movedTime
datetime
Time of the last stage change.
Available only when the
isStagesEnabled
setting is enabled for the corresponding SPA
categoryId
crm_category
Identifier of the funnel (direction) of the item
stageId
crm_status
String identifier of the item's stage.
Available only when the
isStagesEnabled
setting is enabled for the corresponding SPA
previousStageId
crm_status
Identifier of the previous stage type.
Available only when the
isStagesEnabled
setting is enabled for the corresponding SPA
begindate
date
Start date of the item.
Available only when the
isBeginCloseDatesEnabled
setting is enabled for the corresponding SPA
closedate
date
Completion date of the item.
Available only when the
isBeginCloseDatesEnabled
setting is enabled for the corresponding SPA
companyId
crm_company
Identifier of the company linked to the item.
Available only when the
isClientEnabled
setting is enabled for the corresponding SPA
contactId
crm_contact
Identifier of the contact linked to the item.
Available only when the
isClientEnabled
setting is enabled for the corresponding SPA
opportunity
double
Amount.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
isManualOpportunity
boolean
Is manual mode for calculating the amount set.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
taxValue
double
Tax amount.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
currencyId
crm_currency
Identifier of the item's currency.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
opportunityAccount
double
Amount in accounting currency.
Deprecated. Field is disabled.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
taxValueAccount
double
Tax amount in accounting currency.
Deprecated. Field is disabled.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
accountCurrencyId
crm_currency
Accounting currency.
Field is disabled.
Available only when the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA
mycompanyId
crm_company
Identifier of "my" company.
Available only when the
isMycompanyEnabled
setting is enabled for the corresponding SPA
sourceId
crm_status
String identifier of the source type.
Available only when the
isSourceEnabled
setting is enabled for the corresponding SPA
sourceDescription
text
Additional information about the source.
Available only when the
isSourceEnabled
setting is enabled for the corresponding SPA
observers
user[]
List of user identifiers who are Observers.
Available only when the
isObserversEnabled
setting is enabled for the corresponding SPA
contactIds
crm_contact[]
List of contact identifiers linked to the item.
Available only when the
isClientEnabled
setting is enabled for the corresponding SPA
Copied
Was the article helpful?
Yes
No
Previous
Get Entity Fields
Next
Overview of Events

---

## Overview of CRM Object Events

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/events/index

Overview of CRM Object Events | Bitrix24 REST API and Marketplace Applications
Overview of CRM Object Events
Overview of CRM Object Events
There are three types of events — for adding, updating, and deleting a SPA element.
Events are triggered by actions on elements of ALL SPAs. Filtering by the desired type will need to be done on the event processing side.
The list of available events will include the following set:
onCrmDynamicItemAdd
— adding an element of any SPA
onCrmDynamicItemUpdate
— updating an element of any SPA
onCrmDynamicItemDelete
— deleting an element of any SPA
There is a theoretical possibility to subscribe to events of elements of a specific SPA. The names of such events look like
onCrmDynamicItemAdd_{entityTypeId}
. They are not displayed in the webhook creation interface but may work when subscribed through applications.
The events
onCrmDynamicItemAdd
,
onCrmDynamicItemUpdate
, and
onCrmDynamicItemDelete
should only be used for
User-defined CRM Types
and Invoices, as these events are not triggered for system CRM types.
More details on which events can be used for Leads, Deals, and so on are described on the event detail page.
Events
Events
Event for Creating a Custom Type CRM Object onCrmDynamicItemAdd
Event for updating a custom type CRM object onCrmDynamicItemUpdate
Event for Deleting a Custom CRM Object onCrmDynamicItemDelete
Copied
Was the article helpful?
Yes
No
Previous
CRM Object Fields
Next
On Creating a Custom CRM Object

---

## Event for Creating a Custom Type CRM Object onCrmDynamicItemAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/events/on-crm-dynamic-item-add

Event for Creating a Custom Type CRM Object onCrmDynamicItemAdd | Bitrix24 REST API and Marketplace Applications
Event for Creating a Custom Type CRM Object onCrmDynamicItemAdd
Event for Creating a Custom Type CRM Object onCrmDynamicItemAdd
What the Handler Receives
FIELDS Parameter
auth Parameter
Continue Learning
Scope:
crm
Who can subscribe:
any user
The event will trigger when an item of any
custom object type
is added to CRM.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
Event for creating a smart process item with
entityTypeId = 1220
:
{
"event"
:
"ONCRMDYNAMICITEMADD"
,
"event_handler_id"
:
"4"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"22"
,
"ENTITY_TYPE_ID"
:
"1220"
}
}
,
"ts"
:
"1723534033"
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
ONCRMDYNAMICITEMADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created custom type CRM object.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created custom type CRM object.
Structure is described
below
ts
timestamp
Date and time the event was sent from the
event queue
auth
object
Object containing authorization parameters and information about the account where the event occurred.
Structure is described
below
FIELDS Parameter
FIELDS Parameter
Parameter
type
Description
ID
integer
Identifier of the created custom type CRM object
ENTITY_TYPE_ID
integer
Identifier of the custom CRM type
auth Parameter
auth Parameter
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
System Object Type Events
Although
universal CRM methods
allow adding and modifying objects of standard types such as deals, leads, contacts, companies, and estimates, the
onCrmDynamicItemAdd
event will not trigger when adding the listed objects.
To track new deals, leads, and so on, you can use specific events:
Event when creating a deal onCrmDealAdd
Event onCrmLeadAdd
Event onCrmContactAdd
Event on creating a company onCrmCompanyAdd
Event when adding an estimate onCrmQuoteAdd
The
onCrmDynamicItemAdd
event will trigger when new invoices are added.
Continue Learning
Continue Learning
Event Handler
Register a new event handler event.bind
Overview of CRM Object Events
Event for updating a custom type CRM object onCrmDynamicItemUpdate
Event for Deleting a Custom CRM Object onCrmDynamicItemDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
On Updating a Custom CRM Object

---

## Event for updating a custom type CRM object onCrmDynamicItemUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/events/on-crm-dynamic-item-update

Event for updating a custom type CRM object onCrmDynamicItemUpdate | Bitrix24 REST API and Marketplace Applications
Event for updating a custom type CRM object onCrmDynamicItemUpdate
Event for updating a custom type CRM object onCrmDynamicItemUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event triggers when an element of any
custom object type
in CRM is modified.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
Event for changing an element with
id = 24
, belonging to a smart process with
entityTypeId = 1220
:
{
"event"
:
"ONCRMDYNAMICITEMUPDATE"
,
"event_handler_id"
:
"5"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"24"
,
"ENTITY_TYPE_ID"
:
"1220"
}
}
,
"ts"
:
"1723538517"
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
In this case,
ONCRMDYNAMICITEMUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the modified custom type CRM object.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the modified custom type CRM object.
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
Identifier of the modified custom type CRM object
ENTITY_TYPE_ID
integer
Identifier of the custom CRM type
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
Events of system object types
Although
universal CRM methods
allow adding and modifying objects of standard types such as deals, leads, contacts, companies, and estimates, the event
onCrmDynamicItemUpdate
will not trigger when modifying the listed objects.
To track changes to deals, leads, etc., you can use specific events:
Event on deal update onCrmDealUpdate
Event onCrmLeadUpdate
Event onCrmContactUpdate
Event on Company Update onCrmCompanyUpdate
Event on updating the estimate onCrmQuoteUpdate
When new invoices are modified, the event
onCrmDynamicItemUpdate
will trigger.
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Overview of CRM Object Events
Event for Creating a Custom Type CRM Object onCrmDynamicItemAdd
Event for Deleting a Custom CRM Object onCrmDynamicItemDelete
Copied
Was the article helpful?
Yes
No
Previous
On Creating a Custom CRM Object
Next
On Deleting a Custom CRM Object

---

## Event for Deleting a Custom CRM Object onCrmDynamicItemDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/events/on-crm-dynamic-item-delete

Event for Deleting a Custom CRM Object onCrmDynamicItemDelete | Bitrix24 REST API and Marketplace Applications
Event for Deleting a Custom CRM Object onCrmDynamicItemDelete
Event for Deleting a Custom CRM Object onCrmDynamicItemDelete
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Learning
Scope:
crm
Who can subscribe:
any user
The event will trigger upon the deletion of any
custom object type
item in CRM.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
The event for deleting an item with the identifier
23
, belonging to a smart process with
entityTypeId = 1220
:
{
"event"
:
"ONCRMDYNAMICITEMDELETE"
,
"event_handler_id"
:
"6"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"23"
,
"ENTITY_TYPE_ID"
:
"1220"
}
}
,
"ts"
:
"1723538149"
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
ONCRMDYNAMICITEMDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted custom CRM object.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted custom CRM object.
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
Identifier of the deleted custom CRM object
ENTITY_TYPE_ID
integer
Identifier of the custom CRM type
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
Events for System Object Types
Although
universal CRM methods
allow adding and modifying objects of standard types such as deals, leads, contacts, companies, and estimates, the event
onCrmDynamicItemDelete
will not trigger when deleting the listed objects.
To track deleted deals, leads, etc., you can use special events:
Event on deal deletion onCrmDealDelete
Event onLeadDelete
Event onCrmContactDelete
Event onCrmCompanyDelete
Event on deleting an estimate onCrmQuoteDelete
When deleting new invoices, the event
onCrmDynamicItemDelete
will trigger.
Continue Learning
Continue Learning
Event Handler
Register a new event handler event.bind
Overview of CRM Object Events
Event for Creating a Custom Type CRM Object onCrmDynamicItemAdd
Event for updating a custom type CRM object onCrmDynamicItemUpdate
Copied
Was the article helpful?
Yes
No
Previous
On Updating a Custom CRM Object
Next
Overview of Events

---

## Overview of CRM Custom Type Events

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/events/type/index

Overview of CRM Custom Type Events | Bitrix24 REST API and Marketplace Applications
Events
Overview of CRM Custom Type Events
The events
onCrmTypeAdd
,
onCrmTypeUpdate
,
onCrmTypeDelete
allow you to track the addition, modification, and deletion of
CRM custom types
.
Events
Events
Event for Adding Custom CRM Type onCrmTypeAdd
Event for updating custom CRM type onCrmTypeUpdate
Event on Deleting Custom CRM Type onCrmTypeDelete
Copied
Was the article helpful?
Yes
No
Previous
On Deleting a Custom CRM Object
Next
On Creating a Custom CRM Type

---

## Event for Adding Custom CRM Type onCrmTypeAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/events/type/on-crm-type-add

Event for Adding Custom CRM Type onCrmTypeAdd | Bitrix24 REST API and Marketplace Applications
Event for Adding Custom CRM Type onCrmTypeAdd
Event for Adding Custom CRM Type onCrmTypeAdd
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Exploring
Scope:
crm
Who can subscribe:
any user
The event triggers when a
custom CRM type
is added.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMTYPEADD"
,
"event_handler_id"
:
"7"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"45"
}
}
,
"ts"
:
"1723545943"
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
ONCRMTYPEADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created custom CRM type.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created custom CRM type.
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
Identifier of the created custom CRM type (primary key, not the type identifier)
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
Overview of CRM Custom Type Events
Event for updating custom CRM type onCrmTypeUpdate
Event on Deleting Custom CRM Type onCrmTypeDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
On Updating a Custom CRM Type

---

## Event for updating custom CRM type onCrmTypeUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/events/type/on-crm-type-update

Event for updating custom CRM type onCrmTypeUpdate | Bitrix24 REST API and Marketplace Applications
Event for updating custom CRM type onCrmTypeUpdate
Event for updating custom CRM type onCrmTypeUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe:
any user
The event triggers when a
custom CRM type
is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMTYPEUPDATE"
,
"event_handler_id"
:
"10"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"42"
}
}
,
"ts"
:
"1723548742"
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
ONCRMTYPEUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the modified custom CRM type.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the modified custom CRM type.
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
Identifier of the modified custom CRM type (primary key, not the type identifier)
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
Overview of CRM Custom Type Events
Event for Adding Custom CRM Type onCrmTypeAdd
Event on Deleting Custom CRM Type onCrmTypeDelete
Copied
Was the article helpful?
Yes
No
Previous
On Creating a Custom CRM Type
Next
On Deleting a Custom CRM Type

---

## Event on Deleting Custom CRM Type onCrmTypeDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/events/type/on-crm-type-delete

Event on Deleting Custom CRM Type onCrmTypeDelete | Bitrix24 REST API and Marketplace Applications
Event on Deleting Custom CRM Type onCrmTypeDelete
Event on Deleting Custom CRM Type onCrmTypeDelete
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Exploring
Scope:
crm
Who can subscribe:
any user
The event is triggered when a
custom CRM type
is deleted.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMTYPEDELETE"
,
"event_handler_id"
:
"9"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"45"
}
}
,
"ts"
:
"1723546073"
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
ONCRMTYPEDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted custom CRM type.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted custom CRM type.
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
Identifier of the deleted custom CRM type (primary key, not type identifier)
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
Overview of CRM Custom Type Events
Event for Adding Custom CRM Type onCrmTypeAdd
Event for updating custom CRM type onCrmTypeUpdate
Copied
Was the article helpful?
Yes
No
Previous
On Updating a Custom CRM Type
Next
Product Items

---

## Data Import into CRM

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/import/index

Data Import into CRM | Bitrix24 REST API and Marketplace Applications
Data Import into CRM
Data Import into CRM
Scope:
crm
Who can execute the method: any user with the "import" access permission for the CRM object
Import supports all major
CRM entities
:
Leads
Deals
Contacts
Companies
Estimates
Invoices
SPAs
There are two methods available for import:
crm.item.import
— import a single record
crm.item.batchImport
— batch import of records
Adding items through import, unlike adding through
crm.*.add
, has the following features:
Access permission checks are performed on import, not on adding items.
Automation rules and workflows will not be triggered on the added item.
When executed under the portal administrator, there is an option to set values for certain system fields:
Field
Description
createdTime
Date and time of record creation
updatedTime
Date and time of record update
movedTime
Date and time of stage change, if the object supports stages
createdBy
User who created the record
updatedBy
User who modified the record
movedBy
User who changed the stage, if the object supports stages
There are some restrictions on the values of these fields:
A monotonically increasing value for the
createdTime
field is required. This means that records cannot be created with a creation date earlier than any of the existing records.
The values of
createdTime
and
updatedTime
cannot be in the future.
The
updatedTime
cannot be earlier than
createdTime
.
The
movedTime
must be within the range between
createdTime
and
updatedTime
.
Copied
Was the article helpful?
Yes
No
Previous
Get Funnel Fields
Next
Import a single record

---

## Import a single record crm.item.import

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/import/crm-item-import

Import a single record crm.item.import | Bitrix24 REST API and Marketplace Applications
Method Parameters
Import a single record crm.item.import
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
Who can execute the method: any user with "import" access permission for the CRM object
A universal method for importing objects into CRM.
You can read about the differences between the import logic and the logic of regular element addition in the article
Data Import into CRM
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the system or
user-defined type
for which the element needs to be created
fields
*
object
Object format:
{
field_1
: value_1,
field_2
: value_2,
...,
field_n
: value_n,
}
field_n
— field name
value_n
— field value
For multi-fields, such as
PHONE
,
EMAIL
, pass the data in the
crm_multifield
structure:
{
field_name
: [
{
VALUE
:
"value_1"
,
VALUE_TYPE
:
"type_1"
},
{
VALUE
:
"value_2"
,
VALUE_TYPE
:
"type_2"
},
...
]
}
field_name
— field name, for example
PHONE
VALUE
— field value, for example a phone number
VALUE_TYPE
— value type, for example
WORK
Each CRM object has its own set of fields. This means that the set of fields for creating a Lead does not have to match the set of fields for creating a Contact or SPA.
The list of available fields for each type of object is described
below
.
An incorrect field in
fields
will be ignored.
You can also find out the set of fields using the universal method
crm.item.fields
or methods for specific CRM objects:
crm.lead.fields
crm.deal.fields
crm.contact.fields
crm.company.fields
crm.quote.fields
useOriginalUfNames
[
boolean
][1]
Parameter to control the format of user field names in the request and response.
Possible values:
Y
— original user field names, for example
UF_CRM_2_1639669411830
N
— user field names in camelCase, for example
ufCrm2_1639669411830
Default is
N
Parameter fields
Parameter fields
Required parameters are marked with *
Lead
Deal
Contact
Company
Estimate
Invoice
SPA
CRM object identifier
entityTypeId:
1
Name
type
Description
title
string
Name of the entity.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the element
For example, for a lead with
id = 13
— 'Lead #13'
honorific
crm_status
String identifier for the lead's salutation (e.g.,
'HNR_RU_1' = 'Mr.'
).
The list of available salutations can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "HONOFIRIC" }
.
By default —
null
name
string
First name.
By default —
null
secondName
string
Middle name.
By default —
null
lastName
string
Last name.
By default —
null
birthdate
date
Date of birth.
By default —
null
companyTitle
string
Company name.
By default —
null
sourceId
crm_status
String identifier for the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
By default, it takes the value of the first available source
sourceDescription
text
Additional information about the source.
By default —
null
stageId
crm_status
String identifier for the stage of the element.
For example,
'NEW' = 'Unprocessed'
.
The list of available stages can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "STATUS" }
By default, it takes the value of the first available stage
statusDescription
text
Additional information about the stage.
By default —
null
post
string
Position.
By default —
null
currencyId
crm_currency
Identifier for the currency of the element.
By default, it takes the default currency
isManualOpportunity
boolean
Calculation mode for the amount. Possible values:
Y
— manual
N
— automatic
By default —
N
opportunity
double
Amount.
By default —
null
opened
boolean
Is the element available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
comments
text
Comment.
By default —
null
assignedById
user
Identifier of the person responsible for the element.
By default, this is the identifier of the user who calls the method
companyId
crm_company
Identifier of the company linked to the element.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
.
By default —
null
contactId
crm_contact
Identifier of the contact linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
contactIds
crm_contact[]
List of identifiers of contacts linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
originatorId
string
External source.
By default —
null
originId
string
Identifier of the element in the external source.
By default —
null
webformId
integer
Identifier of the CRM Form.
By default —
null
observers
user[]
Array of user identifiers who will be observers of the element.
By default —
null
utmSource
string
Advertising system. For example: Google-Adwords
By default —
null
utmMedium
string
Type of traffic. Possible values:
CPC — ads
CPM — banners
By default —
null
utmCampaign
string
Identifier of the advertising campaign.
By default —
null
utmContent
string
Content of the campaign. For example, for contextual ads.
By default —
null
utmTerm
string
Search term for the campaign. For example, keywords for contextual advertising.
By default equals
null
ufCrm...
crm_userfield
User-defined field.
For information on user-defined fields, see the section
Custom Fields in CRM
Values of multiple fields are passed as an array.
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the base64 encoded content of the file.
parentId...
crm_entity
Parent field. An element of another type of CRM object that is linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
2
Name
type
Description
title
string
Name of the element.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the element
For example, for a deal with
id = 13
=> 'Deal #13'
typeId
crm_status
String identifier for the type of entity.
For example, for a deal:
'SALE' = 'Sale'
The list of available entity types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "DEAL_TYPE" }
By default — the first available entity type
categoryId
integer
Identifier of the
direction
(funnel) of the deal.
By default —
0
(general)
stageId
crm_status
String identifier for the stage of the element.
For example,
'NEW' = 'Unprocessed'
.
The list of available stages can be obtained using
crm.status.list
with the filter:
If the deal is in the general funnel (direction) —
{ ENTITY_ID: "DEAL_STAGE" }
If the deal is not in the general funnel (direction) —
{ ENTITY_ID: "DEAL_STAGE_{categoryId}" }
, where
categoryId
is the identifier of the funnel (
direction
) of the deal
By default — the first available stage relative to the funnel
isRecurring
boolean
Is the deal recurring? Possible values:
Y
— yes
N
— no
By default —
N
probability
integer
Probability %.
By default —
null
currencyId
crm_currency
Identifier for the currency of the element.
By default — the default currency
isManualOpportunity
boolean
Calculation mode for the amount. Possible values:
Y
— manual
N
— automatic
By default —
N
opportunity
double
Amount.
By default —
null
taxValue
double
Tax amount.
By default —
null
companyId
crm_company
Identifier of the company linked to the element.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
.
By default —
null
contactId
crm_contact
Identifier of the contact linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
contactIds
crm_contact[]
List of identifiers of contacts linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
quoteId
crm_quote
Identifier of the estimate that will be linked to the deal
begindate
date
Start date of the element.
By default — creation date
closedate
date
End date of the element.
By default — creation date + 7 days
opened
boolean
Is the element available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
comments
text
Comment.
By default —
null
assignedById
user
Identifier of the person responsible for the element.
By default — the identifier of the user who calls the method
sourceId
crm_status
String identifier for the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
By default — the first available source
sourceDescription
text
Additional information about the source.
By default —
null
leadId
crm_lead
Identifier of the lead based on which the element is created.
By default —
null
additionalInfo
string
Additional information.
By default —
null
originatorId
string
External source.
By default —
null
originId
string
Identifier of the element in the external source.
By default —
null
observers
user[]
Array of user identifiers who will be observers of the element.
By default —
null
locationId
location
Identifier of the location. Service field.
By default —
null
utmSource
string
Advertising system. For example: Google-Adwords
By default —
null
utmMedium
string
Type of traffic. Possible values:
CPC — ads
CPM — banners
By default —
null
utmCampaign
string
Identifier of the advertising campaign.
By default —
null
utmContent
string
Content of the campaign. For example, for contextual ads.
By default —
null
utmTerm
string
Search term for the campaign. For example, keywords for contextual advertising.
By default —
null
ufCrm...
crm_userfield
User-defined field. See the section
Custom Fields in CRM
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the base64 encoded content of the file.
parentId...
crm_entity
Parent field. An element of another type of CRM object that is linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
3
Name
type
Description
honorific
crm_status
String identifier for the contact's salutation.
For example,
'HNR_RU_1' = 'Mr.'
.
The list of available salutations can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "HONOFIRIC" }
.
By default —
null
name
string
First name.
By default —
null
secondName
string
Middle name.
By default —
null
lastName
string
Last name.
By default —
null
photo
file
Photo.
By default —
null
birthdate
date
Date of birth.
By default —
null
typeId
crm_status
String identifier for the type of entity.
For example, for a deal:
'SALE' = 'Sale'
.
The list of available entity types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "CONTACT_TYPE" }
.
By default — the first available entity type
sourceId
crm_status
String identifier for the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
By default — the first available source
sourceDescription
text
Additional information about the source.
By default —
null
post
string
Position.
By default —
null
comments
text
Comment.
By default —
null
opened
boolean
Is the element available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
export
boolean
Is the contact included in the export?
By default —
Y
assignedById
user
Identifier of the person responsible for the element.
By default — the identifier of the user who calls the method
companyId
crm_company
Identifier of the company linked to the element.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
.
By default —
null
companyIds
crm_company
Array of identifiers of companies that will be linked to the element
leadId
crm_lead
Identifier of the lead based on which the element is created.
By default —
null
originatorId
string
External source.
By default —
null
originId
string
Identifier of the element in the external source.
By default —
null
originVersion
string
Version of the original.
By default —
null
observers
user[]
Array of user identifiers who will be observers of the element.
By default —
null
utmSource
string
Advertising system. For example: Google-Adwords
By default —
null
utmMedium
string
Type of traffic. Possible values:
CPC — ads
CPM — banners
By default —
null
utmCampaign
string
Identifier of the advertising campaign.
By default —
null
utmContent
string
Content of the campaign. For example, for contextual ads.
By default —
null
utmTerm
string
Search term for the campaign. For example, keywords for contextual advertising.
By default —
null
ufCrm...
crm_userfield
User-defined field. See the section
Custom Fields in CRM
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the base64 encoded content of the file.
parentId...
crm_entity
Parent field. An element of another type of CRM object that is linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
4
Name
type
Description
title
string
Name of the element.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the element
For example, for a company with
id = 13
=> 'Company #13'
typeId
crm_status
String identifier for the type of entity.
For example, for a deal:
'SALE' = 'Sale'
.
The list of available entity types can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "COMPANY_TYPE" }
.
By default — the first available entity type
logo
file
Logo.
By default —
null
bankingDetails
string
Banking details.
By default —
null
industry
crm_status
String identifier for the type of industry.
For example,
'IT' = 'Information Technology'
.
The list of available industry types can be obtained using the
crm.status.list
method with the filter
{ ENTITY_ID: "INDUSTRY"}
.
By default — the first available industry type
employees
crm_status
String identifier for the number of employees.
The value is taken from the available list, for example,
'EMPLOYEES_1' = 'less than 50'
.
The list of available employee counts can be obtained using the
crm.status.list
method with the filter
{ ENTITY_ID: "EMPLOYEES" }
.
By default — the first available employee count type
currencyId
crm_currency
Identifier for the currency of the element.
By default — the default currency
revenue
double
Annual revenue.
By default —
0
opened
boolean
Is the element available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
comments
text
Comment.
By default —
null
isMyCompany
boolean
Is the company my company?
By default —
N
assignedById
user
Identifier of the person responsible for the element.
By default — the identifier of the user who calls the method
contactIds
crm_contact[]
List of identifiers of contacts linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
leadId
crm_lead
Identifier of the lead based on which the element is created.
By default —
null
originatorId
string
External source.
By default —
null
originId
string
Identifier of the element in the external source.
By default —
null
originVersion
string
Version of the original.
By default —
null
observers
user[]
Array of user identifiers who will be observers of the element.
By default —
null
utmSource
string
Advertising system. For example: Google-Adwords
By default —
null
utmMedium
string
Type of traffic. Possible values:
CPC — ads
CPM — banners
By default —
null
utmCampaign
string
Identifier of the advertising campaign.
By default —
null
utmContent
string
Content of the campaign. For example, for contextual ads.
By default —
null
utmTerm
string
Search term for the campaign. For example, keywords for contextual advertising.
By default —
null
ufCrm...
crm_userfield
User-defined field. See the section
Custom Fields in CRM
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the base64 encoded content of the file.
parentId...
crm_entity
Parent field. An element of another type of CRM object that is linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
7
Name
type
Description
title
string
Name of the element.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the element
For example, for an estimate with
id = 13
=> 'Estimate #13'
assignedById
user
Identifier of the person responsible for the element.
By default — the identifier of the user who calls the method
opened
boolean
Is the element available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
content
text
Content.
By default —
null
terms
text
Terms.
By default —
null
comments
text
Comment.
By default —
null
dealId
crm_deal
Identifier of the linked deal.
By default —
null
leadId
crm_lead
Identifier of the lead based on which the element is created.
By default —
null
storageTypeId
integer
Identifier of the storage type. Possible values:
1
— file
2
— WebDAV
3
— disk
By default:
If the
disk
module is enabled -> Disk
If the
webdav
module is enabled -> WebDAV
File
**storageElementIds**
[`integer`][1]
Array of files.
By default —
null
webformId
integer
Identifier of the CRM Form.
By default —
null
companyId
crm_company
Identifier of the company linked to the element.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
.
By default —
null
contactId
crm_contact
Identifier of the contact linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
By default —
null
contactIds
crm_contact[]
List of identifiers of contacts linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
locationId
location
Identifier of the location. Service field.
By default —
null
currencyId
crm_currency
Identifier for the currency of the element.
By default — the default currency
isManualOpportunity
boolean
Calculation mode for the amount.
Y
— manual
N
— automatic
By default —
N
opportunity
double
Amount.
By default —
null
taxValue
double
Tax amount.
By default —
null
stageId
crm_status
String identifier for the stage of the element.
For example,
'DRAFT' = 'New'
.
The list of available stages can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "QUOTE_STATUS" }
.
By default — the first available stage
begindate
date
Start date of the element.
By default — creation date of the element
closedate
date
End date of the element.
By default — creation date + 7 days
actualDate
date
Valid until.
By default — creation date + 7 days
mycompanyId
crm_company
Identifier of my company.
By default — identifier of the first available "my" company
utmSource
string
Advertising system. For example: Google-Adwords
By default —
null
utmMedium
string
Type of traffic.
CPC — ads
CPM — banners
By default —
null
utmCampaign
string
Identifier of the advertising campaign.
By default —
null
utmContent
string
Content of the campaign. For example, for contextual ads.
By default —
null
utmTerm
string
Search term for the campaign. For example, keywords for contextual advertising.
By default —
null
ufCrm...
crm_userfield
User-defined field. See the section
Custom Fields in CRM
.
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the base64 encoded content of the file.
parentId...
crm_entity
Parent field. An element of another type of CRM object that is linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
31
Name
type
Description
title
string
Name of the element.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the entity
id
— identifier of the element
For example, for an invoice with
id = 13
=> 'Invoice #13'
xmlId
string
External code.
By default —
null
assignedById
user
Identifier of the person responsible for the element.
By default — the identifier of the user who calls the method
opened
boolean
Is the element available to everyone? Possible values:
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
webformId
integer
Identifier of the CRM Form.
By default —
null
begindate
date
Start date of the element.
By default — creation date
closedate
date
End date of the element.
By default — creation date + 7 days
companyId
crm_company
Identifier of the company linked to the element.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
.
By default —
null
contactId
crm_contact
Identifier of the contact linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
contactIds
crm_contact[]
List of identifiers of contacts linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
By default —
null
observers
user[]
Array of user identifiers who will be observers of the element.
By default —
null
stageId
crm_status
String identifier for the stage of the element.
For example,
'DT31_13:N' = 'New'
.
The list of available stages can be obtained using
crm.status.list
, with the filter:
{ ENTITY_ID: "SMART_INVOICE_STAGE_{categoryId}" }
, where
categoryId
— identifier of the default invoice funnel. It can be obtained using
crm.category.list
with
entityTypeId = 31
.
By default — the first available stage
sourceId
crm_status
String identifier for the source.
For example,
'CALL' = 'Call'
.
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
By default — the first available source
sourceDescription
text
Additional information about the source.
By default —
null
currencyId
crm_currency
Identifier for the currency of the element.
By default — the default currency
isManualOpportunity
boolean
Calculation mode for the amount. Possible values:
Y
— manual
N
— automatic
By default —
N
opportunity
double
Amount.
By default —
null
taxValue
double
Tax amount.
By default —
null
mycompanyId
crm_company
Identifier of my company.
By default — identifier of the first available "my" company
comments
text
Comment.
By default —
null
locationId
location
Identifier of the location. Service field.
By default —
null
ufCrm...
crm_userfield
User-defined field. See the section
Custom Fields in CRM
.
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the base64 encoded content of the file.
parentId...
crm_entity
Parent field. An element of another type of CRM object that is linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
CRM object identifier
entityTypeId:
can be obtained using the
crm.type.list
method or created using the
crm.type.add
method.
Name
type
Description
title
string
Name of the element.
By default, it is generated using the template
{entityTypeName} #{id}
, where
entityTypeName
— name of the SPA
id
— identifier of the element
For example, for the SPA element "HR" with
id = 13
=> 'HR #13'
xmlId
string
External code.
By default —
null
assignedById
user
Identifier of the person responsible for the element.
By default — the identifier of the user who calls the method
opened
boolean
Is the element available to everyone?
Y
— yes
N
— no
By default —
Y
. The default value can be changed in the CRM settings
webformId
integer
Identifier of the CRM Form.
By default —
null
begindate
date
Start date of the element.
Available only if the
isBeginCloseDatesEnabled
setting is enabled for the corresponding SPA.
By default — creation date of the element
closedate
date
End date of the element.
Available only if the
isBeginCloseDatesEnabled
setting is enabled for the corresponding SPA.
By default — creation date + 7 days
companyId
crm_company
Identifier of the company linked to the element.
The list of companies can be obtained using the
crm.item.list
method with
entityTypeId = 4
.
Available only if the
isClientEnabled
setting is enabled for the corresponding SPA.
By default —
null
contactId
crm_contact
Identifier of the contact linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
Available only if the
isClientEnabled
setting is enabled for the corresponding SPA.
By default —
null
contactIds
crm_contact[]
List of identifiers of contacts linked to the element.
The list of contacts can be obtained using the
crm.item.list
method with
entityTypeId = 3
.
Available only if the
isClientEnabled
setting is enabled for the corresponding SPA.
By default —
null
observers
user[]
Array of user identifiers who will be observers of the element.
Available only if the
isObserversEnabled
setting is enabled for the corresponding SPA.
By default —
null
categoryId
crm_category
Identifier of the funnel of the SPA element.
The list of available funnels can be obtained using
crm.category.list
with the corresponding
entityTypeId
stageId
crm_status
String identifier for the stage of the element.
For example,
'DT1220_30:NEW' = 'Start'
.
The list of available stages can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "DYNAMIC_{entityTypeId}_STAGE_{categoryId}" }
, where
entityTypeId
— identifier of the SPA type
categoryId
— identifier of the funnel (direction) of the SPA element
Learn more about funnels (directions)
.
Available only if the
isStagesEnabled
setting is enabled for the corresponding SPA.
By default — the first available stage relative to the funnel
sourceId
crm_status
String identifier for the source. (e.g.,
'CALL' = 'Call'
).
The list of available sources can be obtained using
crm.status.list
with the filter
{ ENTITY_ID: "SOURCE" }
.
Available only if the
isSourceEnabled
setting is enabled for the corresponding SPA.
By default — the first available source
sourceDescription
text
Additional information about the source.
Available only if the
isSourceEnabled
setting is enabled for the corresponding SPA.
By default —
null
currencyId
crm_currency
Identifier for the currency of the element.
Available only if the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA.
By default — the default currency
isManualOpportunity
boolean
Calculation mode for the amount. Possible values:
Y
— manual
N
— automatic
Available only if the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA.
By default —
N
opportunity
double
Amount.
Available only if the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA.
By default —
null
taxValue
double
Tax amount.
Available only if the
isLinkWithProductsEnabled
setting is enabled for the corresponding SPA.
By default —
null
mycompanyId
crm_company
Identifier of my company.
Available only if the
isMycompanyEnabled
setting is enabled for the corresponding SPA.
By default — Identifier of the first available "my" company
ufCrm...
crm_userfield
User-defined field. See the section
Custom Fields in CRM
.
Values of multiple fields are passed as an array
To upload a file, the value of the user-defined field must be an array where the first element is the file name and the second is the base64 encoded content of the file.
parentId...
crm_entity
Parent field. An element of another type of CRM object that is linked to this element.
Each such field has the code
parentId + {parentEntityTypeId}
SPA Settings
For more information on managing SPA settings, you can read in
Smart Processes: Overview of Methods
Copied
To upload a file, the value of the user field must be an array where the first element is the file name and the second is the base64 encoded content of the file.
Code Examples
Code Examples
How to Use Examples in Documentation
How to import a deal
cURL (Webhook)
cURL (OAuth)
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
'{"entityTypeId":2,"fields":{"title":"New Deal (specifically for the REST methods example)","typeId":"SERVICE","categoryId":9,"stageId":"C9:UC_KN8KFI","isReccurring":"Y","probability":50,"currencyId":"USD","isManualOpportunity":"Y","opportunity":999.99,"taxValue":99.9,"companyId":5,"contactId":4,"contactIds":[4,5],"quoteId":7,"begindate":"formatDate(monthAgo)","closedate":"formatDate(twelveDaysInAdvance)","opened":"N","comments":"commentsExample","assignedById":6,"sourceId":"WEB","sourceDescription":"There should be additional description about the source","leadId":102,"additionalInfo":"There should be additional information","observers":[2,3],"utmSource":"google","utmMedium":"CPC","ufCrm_1721244707107":1111.1,"parentId1220":2}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.item.import
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"fields":{"title":"New Deal (specifically for the REST methods example)","typeId":"SERVICE","categoryId":9,"stageId":"C9:UC_KN8KFI","isReccurring":"Y","probability":50,"currencyId":"USD","isManualOpportunity":"Y","opportunity":999.99,"taxValue":99.9,"companyId":5,"contactId":4,"contactIds":[4,5],"quoteId":7,"begindate":"formatDate(monthAgo)","closedate":"formatDate(twelveDaysInAdvance)","opened":"N","comments":"commentsExample","assignedById":6,"sourceId":"WEB","sourceDescription":"There should be additional description about the source","leadId":102,"additionalInfo":"There should be additional information","observers":[2,3],"utmSource":"google","utmMedium":"CPC","ufCrm_1721244707107":1111.1,"parentId1220":2},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.import
const
formatDate
= (
date
) => {
return
date.
toISOString
().
slice
(
0
,
10
);
};
const
day =
60
*
60
*
24
*
1000
;
const
now =
new
Date
();
const
twelveDaysInAdvance =
new
Date
(now.
getTime
() +
12
* day);
const
monthAgo =
new
Date
(now.
getTime
() -
30
* day);
const
commentsExample =
`
Example comment inside the deal
[B]Bold text[/B]
[I]Italic[/I]
[U]Underlined[/U]
[S]Strikethrough[/S]
[B][I][U][S]Mix[/S][/U][/I][/B]
[LIST]
[*]List item #1
[*]List item #2
[*]List item #3
[/LIST]
[LIST=1]
[*]Numbered list item #1
[*]Numbered list item #2
[*]Numbered list item #3
[/LIST]
`
;
BX24
.
callMethod
(
'crm.item.import'
,
{
entityTypeId
:
2
,
fields
:
{
title
:
"New Deal (specifically for the REST methods example)"
,
typeId
:
"SERVICE"
,
categoryId
:
9
,
stageId
:
"C9:UC_KN8KFI"
,
isReccurring
:
"Y"
,
probability
:
50
,
currencyId
:
"USD"
,
isManualOpportunity
:
"Y"
,
opportunity
:
999.99
,
taxValue
:
99.9
,
companyId
:
5
,
contactId
:
4
,
contactIds
: [
4
,
5
],
quoteId
:
7
,
begindate
:
formatDate
(monthAgo),
closedate
:
formatDate
(twelveDaysInAdvance),
opened
:
"N"
,
comments
: commentsExample,
assignedById
:
6
,
sourceId
:
"WEB"
,
sourceDescription
:
"There should be additional description about the source"
,
leadId
:
102
,
additionalInfo
:
"There should be additional information"
,
observers
: [
2
,
3
],
utmSource
:
"google"
,
utmMedium
:
"CPC"
,
ufCrm_1721244707107
:
1111.1
,
parentId1220
:
2
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
'crm.item.import'
,
[
'entityTypeId'
=>
2
,
'fields'
=> [
'title'
=>
"New Deal (specifically for the REST methods example)"
,
'typeId'
=>
"SERVICE"
,
'categoryId'
=>
9
,
'stageId'
=>
"C9:UC_KN8KFI"
,
'isReccurring'
=>
"Y"
,
'probability'
=>
50
,
'currencyId'
=>
"USD"
,
'isManualOpportunity'
=>
"Y"
,
'opportunity'
=>
999.99
,
'taxValue'
=>
99.9
,
'companyId'
=>
5
,
'contactId'
=>
4
,
'contactIds'
=> [
4
,
5
],
'quoteId'
=>
7
,
'begindate'
=>
formatDate
(monthAgo),
'closedate'
=>
formatDate
(twelveDaysInAdvance),
'opened'
=>
"N"
,
'comments'
=>
$commentsExample
,
'assignedById'
=>
6
,
'sourceId'
=>
"WEB"
,
'sourceDescription'
=>
"There should be additional description about the source"
,
'leadId'
=>
102
,
'additionalInfo'
=>
"There should be additional information"
,
'observers'
=> [
2
,
3
],
'utmSource'
=>
"google"
,
'utmMedium'
=>
"CPC"
,
'ufCrm_1721244707107'
=>
1111.1
,
'parentId1220'
=>
2
,
],
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
How to create an SPA element with a set of user fields
User fields involved in the example
{
"ufCrm44_1721812760630"
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
"Custom field (string)"
,
"listLabel"
:
"Custom field (string)"
,
"formLabel"
:
"Custom field (string)"
,
"filterLabel"
:
"Custom field (string)"
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
""
}
,
"upperName"
:
"UF_CRM_44_1721812760630"
}
,
"ufCrm44_1721812814433"
:
{
"type"
:
"enumeration"
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
"items"
:
[
{
"ID"
:
"79"
,
"VALUE"
:
"List item #1"
}
,
{
"ID"
:
"80"
,
"VALUE"
:
"List item #2"
}
,
{
"ID"
:
"81"
,
"VALUE"
:
"List item #3"
}
,
{
"ID"
:
"82"
,
"VALUE"
:
"List item #4"
}
]
,
"title"
:
"Custom field (list)"
,
"listLabel"
:
"Custom field (list)"
,
"formLabel"
:
"Custom field (list)"
,
"filterLabel"
:
"Custom field (list)"
,
"settings"
:
{
"DISPLAY"
:
"LIST"
,
"LIST_HEIGHT"
:
1
,
"CAPTION_NO_VALUE"
:
""
,
"SHOW_NO_VALUE"
:
"Y"
}
,
"upperName"
:
"UF_CRM_44_1721812814433"
}
,
"ufCrm44_1721812853419"
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
"Custom field (date)"
,
"listLabel"
:
"Custom field (date)"
,
"formLabel"
:
"Custom field (date)"
,
"filterLabel"
:
"Custom field (date)"
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
,
"upperName"
:
"UF_CRM_44_1721812853419"
}
,
"ufCrm44_1721812885588"
:
{
"type"
:
"url"
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
true
,
"title"
:
"Multiple custom field (link)"
,
"listLabel"
:
"Multiple custom field (link)"
,
"formLabel"
:
"Multiple custom field (link)"
,
"filterLabel"
:
"Multiple custom field (link)"
,
"settings"
:
{
"POPUP"
:
"Y"
,
"SIZE"
:
20
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
,
"ROWS"
:
1
}
,
"upperName"
:
"UF_CRM_44_1721812885588"
}
,
"ufCrm44_1721812898903"
:
{
"type"
:
"file"
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
"Custom field (file)"
,
"listLabel"
:
"Custom field (file)"
,
"formLabel"
:
"Custom field (file)"
,
"filterLabel"
:
"Custom field (file)"
,
"settings"
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
"upperName"
:
"UF_CRM_44_1721812898903"
}
,
"ufCrm44_1721812915476"
:
{
"type"
:
"money"
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
"Custom field (money)"
,
"listLabel"
:
"Custom field (money)"
,
"formLabel"
:
"Custom field (money)"
,
"filterLabel"
:
"Custom field (money)"
,
"settings"
:
{
"DEFAULT_VALUE"
:
""
}
,
"upperName"
:
"UF_CRM_44_1721812915476"
}
,
"ufCrm44_1721812935209"
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
"Custom field (Yes/No)"
,
"listLabel"
:
"Custom field (Yes/No)"
,
"formLabel"
:
"Custom field (Yes/No)"
,
"filterLabel"
:
"Custom field (Yes/No)"
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
{
"en"
:
"Custom field (Yes/No)"
,
"ru"
:
"Custom field (Yes/No)"
,
"th"
:
"Custom field (Yes/No)"
,
"la"
:
"Custom field (Yes/No)"
,
"tc"
:
"Custom field (Yes/No)"
,
"sc"
:
"Custom field (Yes/No)"
,
"br"
:
"Custom field (Yes/No)"
,
"ar"
:
"Custom field (Yes/No)"
,
"fr"
:
"Custom field (Yes/No)"
,
"vn"
:
"Custom field (Yes/No)"
,
"pl"
:
"Custom field (Yes/No)"
,
"tr"
:
"Custom field (Yes/No)"
,
"ja"
:
"Custom field (Yes/No)"
,
"it"
:
"Custom field (Yes/No)"
,
"ms"
:
"Custom field (Yes/No)"
,
"id"
:
"Custom field (Yes/No)"
}
}
,
"upperName"
:
"UF_CRM_44_1721812935209"
}
,
"ufCrm44_1721812948498"
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
true
,
"title"
:
"Custom field (number)"
,
"listLabel"
:
"Custom field (number)"
,
"formLabel"
:
"Custom field (number)"
,
"filterLabel"
:
"Custom field (number)"
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
,
"upperName"
:
"UF_CRM_44_1721812948498"
}
}
cURL (Webhook)
cURL (OAuth)
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
'{
"entityTypeId": 1302,
"fields": {
"ufCrm44_1721812760630": "String for user field of type String",
"ufCrm44_1721812814433": 81,
"ufCrm44_1721812853419": "'
"
$(date '+%Y-%m-%d')
"
'",
"ufCrm44_1721812885588": [
"example.com",
"second-example.com"
],
"ufCrm44_1721812898903": [
"green_pixel.png",
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
],
"ufCrm44_1721812915476": "300|USD",
"ufCrm44_1721812935209": "Y",
"ufCrm44_1721812948498": 9999.9
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.item.import
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"entityTypeId": 1302,
"fields": {
"ufCrm44_1721812760630": "String for user field of type String",
"ufCrm44_1721812814433": 81,
"ufCrm44_1721812853419": "'
"
$(date '+%Y-%m-%d')
"
'",
"ufCrm44_1721812885588": [
"example.com",
"second-example.com"
],
"ufCrm44_1721812898903": [
"green_pixel.png",
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
],
"ufCrm44_1721812915476": "300|USD",
"ufCrm44_1721812935209": "Y",
"ufCrm44_1721812948498": 9999.9
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/crm.item.import
const
greenPixelInBase64 =
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
;
BX24
.
callMethod
(
'crm.item.import'
,
{
entityTypeId
:
1302
,
fields
: {
ufCrm44_1721812760630
:
"String for user field of type String"
,
ufCrm44_1721812814433
:
81
,
ufCrm44_1721812853419
: (
new
Date
()).
toISOString
().
slice
(
0
,
10
),
ufCrm44_1721812885588
: [
"example.com"
,
"second-example.com"
,
],
ufCrm44_1721812898903
: [
"green_pixel.png"
,
greenPixelInBase64,
],
ufCrm44_1721812915476
:
"300|USD"
,
ufCrm44_1721812935209
:
"Y"
,
ufCrm44_1721812948498
:
9999.9
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
'crm.item.import'
,
[
'entityTypeId'
=>
1302
,
'fields'
=> [
'ufCrm44_1721812760630'
=>
"String for user field of type String"
,
'ufCrm44_1721812814433'
=>
81
,
'ufCrm44_1721812853419'
=>
date
(
'Y-m-d'
),
'ufCrm44_1721812885588'
=> [
"example.com"
,
"second-example.com"
,
],
'ufCrm44_1721812898903'
=> [
"green_pixel.png"
,
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
,
],
'ufCrm44_1721812915476'
=>
"300|USD"
,
'ufCrm44_1721812935209'
=>
"Y"
,
'ufCrm44_1721812948498'
=>
9999.9
,
],
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
The method will return an
item
array with the identifier of the created element in case of success, or an error message.
HTTP status:
200
{
"result"
:
{
"item"
:
{
"id"
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
1722940215.145257
,
"finish"
:
1722940217.94124
,
"duration"
:
2.795983076095581
,
"processing"
:
2.4315829277038574
,
"date_start"
:
"2024-08-06T10:30:15+00:00"
,
"date_finish"
:
"2024-08-06T10:30:17+00:00"
,
"operating"
:
2.4314892292022705
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response.
Contains a single key —
item
item
object
Information about the created element.
Contains a single key —
id
id
int
Identifier of the created element
time
time
Information about the request execution time
By default, user field names are passed and returned in camelCase, for example
ufCrm2_1639669411830
.
When passing the parameter
useOriginalUfNames
with the value
Y
, user fields will be returned with original names, for example
UF_CRM_2_1639669411830
.
Error Handling
Error Handling
HTTP status:
401
,
400
,
403
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"SPA not found"
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
Status
Code
Description
Value
400
NOT_FOUND
SPA not found
Occurs when an invalid
entityTypeId
is passed
400
ACCESS_DENIED
Access denied
The user does not have permission to add elements of type
entityTypeId
400
CRM_FIELD_ERROR_VALUE_NOT_VALID
Invalid value for field "
field
"
An incorrect value for the field
field
was passed.
For system fields of type
createdTime
, if the request is not made by an administrator
400
100
Expected iterable value for multiple field, but got
type
instead
One of the multi-fields received a value of type
type
, while an iterable type was expected. This can also occur with an incorrect request (invalid JSON or request headers)
400
CREATE_DYNAMIC_ITEM_RESTRICTED
You cannot create a new element due to your plan restrictions
Plan restrictions do not allow creating SPA elements
401
INVALID_CREDENTIALS
Invalid authorization data for the request
Incorrect
user ID
and/or code in the request path
403
allowed_only_intranet_user
Action allowed only for intranet users
The user is not an intranet user
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
Data Import into CRM
Import a Batch of CRM Records crm.item.batchImport
Copied
Was the article helpful?
Yes
No
Previous
Import
Next
Import a group of records

---

## Import a Batch of CRM Records crm.item.batchImport

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/import/crm-item-batch-import

Import a Batch of CRM Records crm.item.batchImport | Bitrix24 REST API and Marketplace Applications
Import a Batch of CRM Records crm.item.batchImport
Import a Batch of CRM Records crm.item.batchImport
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
Who can execute the method: any user with "import" access permission for the CRM object
A universal method for importing objects into CRM. The differences from adding an object are described in more detail
here
.
The logic for adding items works similarly to the
crm.item.import
method.
Attention!
A maximum of 20 items can be imported in a single request.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
entityTypeId
*
integer
Identifier of the system or
user-defined type
for which the item needs to be created
data
*
array
An array of field values for the items. It can be viewed as an array where each element contains a set of
fields
described in the
crm.item.import
method
useOriginalUfNames
boolean
Parameter to control the format of custom field names in the request and response.
Possible values:
Y
— original names of custom fields, e.g.,
UF_CRM_2_1639669411830
N
— custom field names in camelCase, e.g.,
ufCrm2_1639669411830
Default is
N
Code Examples
Code Examples
How to Use Examples in Documentation
How to import deals
cURL (Webhook)
cURL (OAuth)
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
'{"entityTypeId":2,"data":[{"title":"New Deal (specifically for the REST methods example)","typeId":"SERVICE","categoryId":9,"stageId":"C9:UC_KN8KFI","isReccurring":"Y","probability":50,"currencyId":"USD","isManualOpportunity":"Y","opportunity":999.99,"taxValue":99.9,"companyId":5,"contactId":4,"contactIds":[4,5],"quoteId":7,"begindate":"formatDate(monthAgo)","closedate":"formatDate(twelveDaysInAdvance)","opened":"N","comments":"commentsExample","assignedById":6,"sourceId":"WEB","sourceDescription":"There should be additional description about the source","leadId":102,"additionalInfo":"There should be additional information","observers":[2,3],"utmSource":"google","utmMedium":"CPC","ufCrm_1721244707107":1111.1,"parentId1220":2},{"title":"New Deal (specifically for the REST methods example)","typeId":"SERVICE","categoryId":4,"stageId":"C9:UC_KN8KFI","isReccurring":"Y","probability":50,"currencyId":"USD","isManualOpportunity":"Y","opportunity":999.99,"taxValue":99.9,"companyId":5,"contactId":4,"contactIds":[4,5],"quoteId":7,"begindate":"formatDate(monthAgo)","closedate":"formatDate(twelveDaysInAdvance)","opened":"N","comments":"commentsExample","assignedById":6,"sourceId":"WEB","sourceDescription":"There should be additional description about the source","leadId":102,"additionalInfo":"There should be additional information","observers":[2,3],"utmSource":"google","utmMedium":"CPC","ufCrm_1721244707107":1111.1,"parentId1220":2}]}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.batchImport
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"entityTypeId":2,"data":[{"title":"New Deal (specifically for the REST methods example)","typeId":"SERVICE","categoryId":9,"stageId":"C9:UC_KN8KFI","isReccurring":"Y","probability":50,"currencyId":"USD","isManualOpportunity":"Y","opportunity":999.99,"taxValue":99.9,"companyId":5,"contactId":4,"contactIds":[4,5],"quoteId":7,"begindate":"formatDate(monthAgo)","closedate":"formatDate(twelveDaysInAdvance)","opened":"N","comments":"commentsExample","assignedById":6,"sourceId":"WEB","sourceDescription":"There should be additional description about the source","leadId":102,"additionalInfo":"There should be additional information","observers":[2,3],"utmSource":"google","utmMedium":"CPC","ufCrm_1721244707107":1111.1,"parentId1220":2},{"title":"New Deal (specifically for the REST methods example)","typeId":"SERVICE","categoryId":4,"stageId":"C9:UC_KN8KFI","isReccurring":"Y","probability":50,"currencyId":"USD","isManualOpportunity":"Y","opportunity":999.99,"taxValue":99.9,"companyId":5,"contactId":4,"contactIds":[4,5],"quoteId":7,"begindate":"formatDate(monthAgo)","closedate":"formatDate(twelveDaysInAdvance)","opened":"N","comments":"commentsExample","assignedById":6,"sourceId":"WEB","sourceDescription":"There should be additional description about the source","leadId":102,"additionalInfo":"There should be additional information","observers":[2,3],"utmSource":"google","utmMedium":"CPC","ufCrm_1721244707107":1111.1,"parentId1220":2}],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.item.batchImport
const
formatDate
= (
date
) => {
return
date.
toISOString
().
slice
(
0
,
10
);
};
const
day =
60
*
60
*
24
*
1000
;
const
now =
new
Date
();
const
twelveDaysInAdvance =
new
Date
(now.
getTime
() +
12
* day);
const
monthAgo =
new
Date
(now.
getTime
() -
30
* day);
const
commentsExample =
`
Example comment inside the deal
[B]Bold text[/B]
[I]Italic[/I]
[U]Underlined[/U]
[S]Strikethrough[/S]
[B][I][U][S]Mix[/S][/U][/I][/B]
[LIST]
[*]List item #1
[*]List item #2
[*]List item #3
[/LIST]
[LIST=1]
[*]Numbered list item #1
[*]Numbered list item #2
[*]Numbered list item #3
[/LIST]
`
;
const
deal = {
title
:
"New Deal (specifically for the REST methods example)"
,
typeId
:
"SERVICE"
,
categoryId
:
9
,
stageId
:
"C9:UC_KN8KFI"
,
isReccurring
:
"Y"
,
probability
:
50
,
currencyId
:
"USD"
,
isManualOpportunity
:
"Y"
,
opportunity
:
999.99
,
taxValue
:
99.9
,
companyId
:
5
,
contactId
:
4
,
contactIds
: [
4
,
5
],
quoteId
:
7
,
begindate
:
formatDate
(monthAgo),
closedate
:
formatDate
(twelveDaysInAdvance),
opened
:
"N"
,
comments
: commentsExample,
assignedById
:
6
,
sourceId
:
"WEB"
,
sourceDescription
:
"There should be additional description about the source"
,
leadId
:
102
,
additionalInfo
:
"There should be additional information"
,
observers
: [
2
,
3
],
utmSource
:
"google"
,
utmMedium
:
"CPC"
,
ufCrm_1721244707107
:
1111.1
,
parentId1220
:
2
,
};
const
secondDeal = {
title
:
"New Deal (specifically for the REST methods example)"
,
typeId
:
"SERVICE"
,
categoryId
:
4
,
stageId
:
"C9:UC_KN8KFI"
,
isReccurring
:
"Y"
,
probability
:
50
,
currencyId
:
"USD"
,
isManualOpportunity
:
"Y"
,
opportunity
:
999.99
,
taxValue
:
99.9
,
companyId
:
5
,
contactId
:
4
,
contactIds
: [
4
,
5
],
quoteId
:
7
,
begindate
:
formatDate
(monthAgo),
closedate
:
formatDate
(twelveDaysInAdvance),
opened
:
"N"
,
comments
: commentsExample,
assignedById
:
6
,
sourceId
:
"WEB"
,
sourceDescription
:
"There should be additional description about the source"
,
leadId
:
102
,
additionalInfo
:
"There should be additional information"
,
observers
: [
2
,
3
],
utmSource
:
"google"
,
utmMedium
:
"CPC"
,
ufCrm_1721244707107
:
1111.1
,
parentId1220
:
2
,
};
BX24
.
callMethod
(
'crm.item.batchImport'
,
{
entityTypeId
:
2
,
data
: [
deal,
secondDeal
]
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
}
);
require_once
(
'crest.php'
);
$deal
= [
'title'
=>
"New Deal (specifically for the REST methods example)"
,
'typeId'
=>
"SERVICE"
,
'categoryId'
=>
9
,
'stageId'
=>
"C9:UC_KN8KFI"
,
'isReccurring'
=>
"Y"
,
'probability'
=>
50
,
'currencyId'
=>
"USD"
,
'isManualOpportunity'
=>
"Y"
,
'opportunity'
=>
999.99
,
'taxValue'
=>
99.9
,
'companyId'
=>
5
,
'contactId'
=>
4
,
'contactIds'
=> [
4
,
5
],
'quoteId'
=>
7
,
'begindate'
=>
formatDate
(monthAgo),
'closedate'
=>
formatDate
(twelveDaysInAdvance),
'opened'
=>
"N"
,
'comments'
=>
$commentsExample
,
'assignedById'
=>
6
,
'sourceId'
=>
"WEB"
,
'sourceDescription'
=>
"There should be additional description about the source"
,
'leadId'
=>
102
,
'additionalInfo'
=>
"There should be additional information"
,
'observers'
=> [
2
,
3
],
'utmSource'
=>
"google"
,
'utmMedium'
=>
"CPC"
,
'ufCrm_1721244707107'
=>
1111.1
,
'parentId1220'
=>
2
];
$secondDeal
= [
'title'
=>
"New Deal (specifically for the REST methods example)"
,
'typeId'
=>
"SERVICE"
,
'categoryId'
=>
4
,
'stageId'
=>
"C9:UC_KN8KFI"
,
'isReccurring'
=>
"Y"
,
'probability'
=>
50
,
'currencyId'
=>
"USD"
,
'isManualOpportunity'
=>
"Y"
,
'opportunity'
=>
999.99
,
'taxValue'
=>
99.9
,
'companyId'
=>
5
,
'contactId'
=>
4
,
'contactIds'
=> [
4
,
5
],
'quoteId'
=>
7
,
'begindate'
=>
formatDate
(monthAgo),
'closedate'
=>
formatDate
(twelveDaysInAdvance),
'opened'
=>
"N"
,
'comments'
=>
$commentsExample
,
'assignedById'
=>
6
,
'sourceId'
=>
"WEB"
,
'sourceDescription'
=>
"There should be additional description about the source"
,
'leadId'
=>
102
,
'additionalInfo'
=>
"There should be additional information"
,
'observers'
=> [
2
,
3
],
'utmSource'
=>
"google"
,
'utmMedium'
=>
"CPC"
,
'ufCrm_1721244707107'
=>
1111.1
,
'parentId1220'
=>
2
];
$result
=
CRest
::
call
(
'crm.item.batchImport'
,
[
'entityTypeId'
=>
2
,
'data'
=> [
$deal
,
$secondDeal
,
],
],
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
How to create an SPA element with a set of custom fields
Custom fields involved in the example
{
"ufCrm44_1721812760630"
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
"Custom field (string)"
,
"listLabel"
:
"Custom field (string)"
,
"formLabel"
:
"Custom field (string)"
,
"filterLabel"
:
"Custom field (string)"
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
""
}
,
"upperName"
:
"UF_CRM_44_1721812760630"
}
,
"ufCrm44_1721812814433"
:
{
"type"
:
"enumeration"
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
"items"
:
[
{
"ID"
:
"79"
,
"VALUE"
:
"List item #1"
}
,
{
"ID"
:
"80"
,
"VALUE"
:
"List item #2"
}
,
{
"ID"
:
"81"
,
"VALUE"
:
"List item #3"
}
,
{
"ID"
:
"82"
,
"VALUE"
:
"List item #4"
}
]
,
"title"
:
"Custom field (list)"
,
"listLabel"
:
"Custom field (list)"
,
"formLabel"
:
"Custom field (list)"
,
"filterLabel"
:
"Custom field (list)"
,
"settings"
:
{
"DISPLAY"
:
"LIST"
,
"LIST_HEIGHT"
:
1
,
"CAPTION_NO_VALUE"
:
""
,
"SHOW_NO_VALUE"
:
"Y"
}
,
"upperName"
:
"UF_CRM_44_1721812814433"
}
,
"ufCrm44_1721812853419"
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
"Custom field (date)"
,
"listLabel"
:
"Custom field (date)"
,
"formLabel"
:
"Custom field (date)"
,
"filterLabel"
:
"Custom field (date)"
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
,
"upperName"
:
"UF_CRM_44_1721812853419"
}
,
"ufCrm44_1721812885588"
:
{
"type"
:
"url"
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
true
,
"title"
:
"Multiple custom field (link)"
,
"listLabel"
:
"Multiple custom field (link)"
,
"formLabel"
:
"Multiple custom field (link)"
,
"filterLabel"
:
"Multiple custom field (link)"
,
"settings"
:
{
"POPUP"
:
"Y"
,
"SIZE"
:
20
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
,
"ROWS"
:
1
}
,
"upperName"
:
"UF_CRM_44_1721812885588"
}
,
"ufCrm44_1721812898903"
:
{
"type"
:
"file"
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
"Custom field (file)"
,
"listLabel"
:
"Custom field (file)"
,
"formLabel"
:
"Custom field (file)"
,
"filterLabel"
:
"Custom field (file)"
,
"settings"
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
"upperName"
:
"UF_CRM_44_1721812898903"
}
,
"ufCrm44_1721812915476"
:
{
"type"
:
"money"
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
"Custom field (money)"
,
"listLabel"
:
"Custom field (money)"
,
"formLabel"
:
"Custom field (money)"
,
"filterLabel"
:
"Custom field (money)"
,
"settings"
:
{
"DEFAULT_VALUE"
:
""
}
,
"upperName"
:
"UF_CRM_44_1721812915476"
}
,
"ufCrm44_1721812935209"
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
"Custom field (Yes/No)"
,
"listLabel"
:
"Custom field (Yes/No)"
,
"formLabel"
:
"Custom field (Yes/No)"
,
"filterLabel"
:
"Custom field (Yes/No)"
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
{
"en"
:
"Custom field (Yes/No)"
,
"ru"
:
"Custom field (Yes/No)"
,
"th"
:
"Custom field (Yes/No)"
,
"la"
:
"Custom field (Yes/No)"
,
"tc"
:
"Custom field (Yes/No)"
,
"sc"
:
"Custom field (Yes/No)"
,
"br"
:
"Custom field (Yes/No)"
,
"ar"
:
"Custom field (Yes/No)"
,
"fr"
:
"Custom field (Yes/No)"
,
"vn"
:
"Custom field (Yes/No)"
,
"pl"
:
"Custom field (Yes/No)"
,
"tr"
:
"Custom field (Yes/No)"
,
"ja"
:
"Custom field (Yes/No)"
,
"it"
:
"Custom field (Yes/No)"
,
"ms"
:
"Custom field (Yes/No)"
,
"id"
:
"Custom field (Yes/No)"
}
}
,
"upperName"
:
"UF_CRM_44_1721812935209"
}
,
"ufCrm44_1721812948498"
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
true
,
"title"
:
"Custom field (number)"
,
"listLabel"
:
"Custom field (number)"
,
"formLabel"
:
"Custom field (number)"
,
"filterLabel"
:
"Custom field (number)"
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
,
"upperName"
:
"UF_CRM_44_1721812948498"
}
}
cURL (Webhook)
cURL (OAuth)
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
'{
"entityTypeId": 1302,
"data": [{
"ufCrm44_1721812760630": "String for custom field of type String",
"ufCrm44_1721812814433": 81,
"ufCrm44_1721812853419": "'
"
$(date '+%Y-%m-%d')
"
'",
"ufCrm44_1721812885588": [
"example.com",
"second-example.com"
],
"ufCrm44_1721812898903": [
"green_pixel.png",
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
],
"ufCrm44_1721812915476": "300|USD",
"ufCrm44_1721812935209": "Y",
"ufCrm44_1721812948498": 9999.9
},{
"ufCrm44_1721812760630": "String for custom field of type String",
"ufCrm44_1721812814433": 45,
"ufCrm44_1721812853419": "'
"
$(date '+%Y-%m-%d')
"
'",
"ufCrm44_1721812885588": [
"example.com",
"second-example.com"
],
"ufCrm44_1721812898903": [
"green_pixel2.png",
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
],
"ufCrm44_1721812915476": "600|USD",
"ufCrm44_1721812935209": "N",
"ufCrm44_1721812948498": 9999.9
}]
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.item.batchImport
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"entityTypeId": 1302,
"data": [{
"ufCrm44_1721812760630": "String for custom field of type String",
"ufCrm44_1721812814433": 81,
"ufCrm44_1721812853419": "'
"
$(date '+%Y-%m-%d')
"
'",
"ufCrm44_1721812885588": [
"example.com",
"second-example.com"
],
"ufCrm44_1721812898903": [
"green_pixel.png",
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
],
"ufCrm44_1721812915476": "300|USD",
"ufCrm44_1721812935209": "Y",
"ufCrm44_1721812948498": 9999.9
},{
"ufCrm44_1721812760630": "String for custom field of type String",
"ufCrm44_1721812814433": 45,
"ufCrm44_1721812853419": "'
"
$(date '+%Y-%m-%d')
"
'",
"ufCrm44_1721812885588": [
"example.com",
"second-example.com"
],
"ufCrm44_1721812898903": [
"green_pixel2.png",
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
],
"ufCrm44_1721812915476": "600|USD",
"ufCrm44_1721812935209": "N",
"ufCrm44_1721812948498": 9999.9
}],
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/crm.item.batchImport
const
greenPixelInBase64 =
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
;
BX24
.
callMethod
(
'crm.item.batchImport'
,
{
entityTypeId
:
1302
,
data
: [
{
ufCrm44_1721812760630
:
"String for custom field of type String"
,
ufCrm44_1721812814433
:
81
,
ufCrm44_1721812853419
: (
new
Date
()).
toISOString
().
slice
(
0
,
10
),
ufCrm44_1721812885588
: [
"example.com"
,
"second-example.com"
,
],
ufCrm44_1721812898903
: [
"green_pixel.png"
,
greenPixelInBase64,
],
ufCrm44_1721812915476
:
"300|USD"
,
ufCrm44_1721812935209
:
"Y"
,
ufCrm44_1721812948498
:
9999.9
,
},
{
ufCrm44_1721812760630
:
"String for custom field of type String"
,
ufCrm44_1721812814433
:
45
,
ufCrm44_1721812853419
: (
new
Date
()).
toISOString
().
slice
(
0
,
10
),
ufCrm44_1721812885588
: [
"example.com"
,
"second-example.com"
,
],
ufCrm44_1721812898903
: [
"green_pixel2.png"
,
greenPixelInBase64,
],
ufCrm44_1721812915476
:
"600|USD"
,
ufCrm44_1721812935209
:
"N"
,
ufCrm44_1721812948498
:
9999.9
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
'crm.item.batchImport'
,
[
'entityTypeId'
=>
1302
,
'data'
=> [
[
'ufCrm44_1721812760630'
=>
"String for custom field of type String"
,
'ufCrm44_1721812814433'
=>
81
,
'ufCrm44_1721812853419'
=>
date
(
'Y-m-d'
),
'ufCrm44_1721812885588'
=> [
"example.com"
,
"second-example.com"
,
],
'ufCrm44_1721812898903'
=> [
"green_pixel.png"
,
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
,
],
'ufCrm44_1721812915476'
=>
"300|USD"
,
'ufCrm44_1721812935209'
=>
"Y"
,
'ufCrm44_1721812948498'
=>
9999.9
,
],
[
'ufCrm44_1721812760630'
=>
"String for custom field of type String"
,
'ufCrm44_1721812814433'
=>
45
,
'ufCrm44_1721812853419'
=>
date
(
'Y-m-d'
),
'ufCrm44_1721812885588'
=> [
"example.com"
,
"second-example.com"
,
],
'ufCrm44_1721812898903'
=> [
"green_pixel2.png"
,
"iVBORw0KGgoAAAANSUhEUgAAAIAAAAAMCAYAAACqTLVoAAAALklEQVR42u3SAQEAAAQDsEsuOj3YMqwy6fBWCSCAAAIgAAIgAAIgAAIgAAJw3QLOrRH1U/gU4gAAAABJRU5ErkJggg=="
,
],
'ufCrm44_1721812915476'
=>
"600|USD"
,
'ufCrm44_1721812935209'
=>
"N"
,
'ufCrm44_1721812948498'
=>
9999.9
,
],
],
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
The method will return an array
items
, containing objects where each object in this array will contain the identifier of the created item in case of success, or an error message object.
HTTP status:
200
{
"result"
:
{
"items"
:
[
{
"item"
:
{
"id"
:
15
}
}
,
{
"error"
:
"CRM_FIELD_ERROR_REQUIRED"
,
"error_description"
:
"The field \"Title\" is required"
}
]
}
,
"time"
:
{
"start"
:
1723414961.913589
,
"finish"
:
1723414964.652124
,
"duration"
:
2.738534927368164
,
"processing"
:
2.376383066177368
,
"date_start"
:
"2024-08-11T22:22:41+00:00"
,
"date_finish"
:
"2024-08-11T22:22:44+00:00"
,
"operating"
:
2.3762991428375244
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Root element of the response.
Contains a single key
item
items
array
An array containing
item
objects or errors
item
object
Information about the created item.
Contains a single key
id
id
int
Identifier of the created item
time
time
Information about the execution time of the request
By default, custom field names are passed and returned in camelCase, e.g.,
ufCrm2_1639669411830
.
When the parameter
useOriginalUfNames
is passed with the value
Y
, custom fields will be returned with their original names, e.g.,
UF_CRM_2_1639669411830
.
Error Handling
Error Handling
HTTP status:
401
,
400
,
403
{
"error"
:
"NOT_FOUND"
,
"error_description"
:
"Smart process not found"
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
Status
Code
Description
Value
400
NOT_FOUND
Smart process not found
Occurs when an invalid
entityTypeId
is passed
400
ACCESS_DENIED
Access denied
The user does not have permission to add items of type
entityTypeId
400
CRM_FIELD_ERROR_VALUE_NOT_VALID
Invalid value for field "
field
"
An incorrect value for the
field
was passed.
For system fields of type
createdTime
, if the request is not from an administrator
400
100
Expected iterable value for multiple field, but got
type
instead
One of the multiple fields received a value of type
type
, while an iterable type was expected. This can also occur with an incorrect request (invalid JSON or request headers)
400
CREATE_DYNAMIC_ITEM_RESTRICTED
You cannot create a new item due to your plan restrictions
Plan restrictions do not allow creating SPA items
400
MAX_IMPORT_BATCH_SIZE_EXCEEDED
You cannot import more than 20 items
Occurs when more than 20 items are passed during import
401
INVALID_CREDENTIALS
Invalid authorization data for the request
Incorrect
user ID
and/or code in the request path
403
allowed_only_intranet_user
Action allowed only for intranet users
The user is not an intranet user
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
How to Use Examples in Documentation
Continue Learning
Continue Learning
Data Import into CRM
Import a single record crm.item.import
Copied
Was the article helpful?
Yes
No
Previous
Import a single record
Next
Overview of Methods

---

## Widgets Embedded in the Interface of Custom CRM Object Types

**Source:** https://apidocs.bitrix24.com/api-reference/crm/universal/widgets

Widgets Embedded in the Interface of Custom CRM Object Types | Bitrix24 REST API and Marketplace Applications
Widgets Embedded in the Interface of Custom CRM Object Types
Widgets Embedded in the Interface of Custom CRM Object Types
Widgets allow you to integrate custom functionality directly into the Bitrix24 interface. We have previously described this mechanism in the section
Widget Integration Mechanism
.
Unlike standard embedding locations for widgets (such as in deals), for custom CRM object types, it is important to note that these locations become available only after specific custom object types are added to Bitrix24.
The identifiers of these types are used in the symbolic codes of the widget embedding locations. Suppose a custom type "Vendors" has been added to Bitrix24, and the identifier for this custom object type is
131
. In this case, the following locations will be available for embedding widgets:
Tab in the detail form of the entity with the code
CRM_SMART_131_DETAIL_TAB
timeline
button in the entity card with the code
CRM_SMART_131_DETAIL_ACTIVITY
CRM Widgets
CRM Widgets
Context Menu Item in the CRM_XXX_LIST_MENU, CRM_DYNAMIC_XXX_LIST_MENU
Dropdown Menu Item Above the CRM Entity List CRM_XXX_LIST_TOOLBAR, CRM_DYNAMIC_XXX_LIST_TOOLBAR
Tab in the detail form of the CRM entity CRM_XXX_DETAIL_TAB, CRM_DYNAMIC_XXX_DETAIL_TAB
Button above the timeline of the CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY card
Dropdown Menu Item of the Top Button in the CRM_XXX_DETAIL_TOOLBAR, CRM_DYNAMIC_XXX_DETAIL_TOOLBAR
Context Menu Item for the Deal in the CRM Element Card CRM_XXX_ACTIVITY_TIMELINE_MENU, CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU
Dropdown Menu Item for the Document Generator CRM_XXX_DOCUMENTGENERATOR_BUTTON
Dropdown Menu Item of the Top Button in the CRM Robot Designer CRM_XXX_ROBOT_DESIGNER_TOOLBAR
Menu Item in CRM Sales Funnels Toolbar
CRM Analytics Menu Item CRM_ANALYTICS_MENU
Dropdown Menu Item of the Top Button in CRM Analytics CRM_ANALYTICS_TOOLBAR
Copied
Was the article helpful?
Yes
No
Previous
Set Common Detail Form for All Users
Next
Overview of methods

---

