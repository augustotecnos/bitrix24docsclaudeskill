---
description: 'CRM Miscellaneous: Data types, field descriptions, settings'
methods:
- crm.activity.fields
- crm.address.fields
- crm.automatedsolution.
- crm.category.get
- crm.company.fields
- crm.company.get
- crm.company.list
- crm.contact.add
- crm.contact.company.items.get
- crm.contact.fields
- crm.contact.get
- crm.contact.list
- crm.contact.update
- crm.contact.userfield.add
- crm.deal.add
- crm.deal.contact.items.delete
- crm.deal.contact.items.get
- crm.deal.contact.items.set
- crm.deal.fields
- crm.deal.get
- crm.deal.list
- crm.deal.update
- crm.enum.activitydirection
- crm.enum.activitynotifytype
- crm.enum.activitypriority
- crm.enum.addresstype
- crm.enum.contenttype
- crm.enum.ownertype
- crm.item.get
- crm.item.productrow.list
pages: 4
title: 'CRM Miscellaneous: Data types, field descriptions, settings'
---
# CRM Miscellaneous: Data types, field descriptions, settings
> CRM Miscellaneous: Data types, field descriptions, settings
> **4 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Overview of CRM](#overview-of-crm)
- [Data Types and Object Structure in the REST API CRM](#data-types-and-object-structure-in-the-rest-api-cr)
- [Fields of Main CRM Objects](#fields-of-main-crm-objects)
- [Typical use-cases and scenarios for REST API in CRM and tutorials](#typical-use-cases-and-scenarios-for-rest-api-in-cr)

---

## Overview of CRM

**Source:** https://apidocs.bitrix24.com/api-reference/crm/index

Overview of CRM | Bitrix24 REST API and Marketplace Applications
Overview of CRM
Overview of CRM
We are still updating this page
Some data may be missing here — we will complete it soon.
CRM
is one of the most functional tools in Bitrix. To effectively use the REST API, it is highly recommended to study the product's functionality and the main user scenarios. Understanding the relationships between CRM objects will simplify the search and use of the REST API tools needed to implement the required functionality.
The current section of the documentation includes the main sections:
Universal methods
Deals
Leads
Contacts
Companies
Timeline and activities
Searching and processing duplicates in CRM
Reference books
Currencies
Document generator
Digital workplaces
Automation and triggers
Auxiliary objects
Deprecated methods
The "Universal methods" section includes a large number of methods that can be used for different CRM objects — deals, leads, contacts, etc.
It is recommended to use universal methods instead of separate methods for deals or leads, for example. Only if universal methods do not allow solving a task that can only be addressed by specialized methods for specific types of objects should one refer to the specialized sections.
Smart processes
in the documentation are described as "
user-defined object types
" since they essentially allow the creation of objects that function alongside deals, leads, and other "standard" objects.
It is not recommended to use the methods described in the "Deprecated" section. They continue to function, but their functionality no longer accounts for emerging updates.
Was the article helpful?
Yes
No
Previous
Conditions in Prompts
Next
Data Types and Structure of Objects in the CRM REST API

---

## Data Types and Object Structure in the REST API CRM

**Source:** https://apidocs.bitrix24.com/api-reference/crm/data-types

Data Types and Object Structure in the REST API CRM | Bitrix24 REST API and Marketplace Applications
Data Types
Data Types and Object Structure in the REST API CRM
Data Types
Object Structure
crm_multifield
crm_item_product_row
crm_currency
crm_currency_localization
crm_orderentity
type
type.relations
type.linkedUserFields
Language Identifiers for Bitrix24
Objects Used in Responses
Description of a Single Field crm_rest_field_description
Description of User Field Type Address
CRM Object Type
Basic data types are listed in a separate
article
.
In this article, we will discuss the data types and object structure specific to CRM.
Data Types
Data Types
Type
Descriptions and Values
crm_status
String identifier of a CRM directory element (for example,
NEW
). Possible values for a specific directory can be obtained using the
crm.status.list
method with a filter by
ENTITY_ID
.
crm_lead
Integer identifier of a CRM lead. Information about the lead can be obtained using the
crm.lead.get
method.
crm_deal
Integer identifier of a CRM deal. Information about the deal can be obtained using the
crm.deal.get
method.
crm_contact
Integer identifier of a CRM contact. Information about the contact can be obtained using the
crm.contact.get
method.
crm_company
Integer identifier of a CRM company. Information about the company can be obtained using the
crm.company.get
method.
crm_quote
Integer identifier of a CRM estimate. Information about the estimate can be obtained using the
crm.quote.get
method.
crm_category
Integer identifier of a CRM funnel (direction). Information about the funnel (direction) can be obtained using the
crm.category.get
method.
crm_entity
Integer identifier of an element of some CRM object. Fields of this type explicitly contain information about which CRM object they belong to. For example, fields like
parentId{entityTypeId}
contain the identifier of the CRM entity type within their name. Information about the element can be obtained using the
crm.item.get
method by passing
entityTypeId
from the field name and
id
from its value.
lang_map
Object format:
{
lang_1: value_1,
lang_2: value_2,
..
lang_n: value_n,
}
where
lang_n
-
Language identifier
value_n
- Value for language
lang_n
crm_item_product_row
Integer identifier of the product item of the CRM object. Product item identifiers can be obtained using the
crm.item.productrow.list
method.
crm_multifield
Object describing a "multifield". Multifields are used to store phone numbers, email addresses, and other contact information. In leads, contacts, and companies, fields of this type are
PHONE
,
EMAIL
,
WEB
, and
IM
.
crm_currency
Object describing currency.
crm_currency_localization
Object describing currency localization.
crm_orderentity
Object describing the connection between CRM and online store orders.
type
Object describing a custom type of CRM object (SPA).
type.relations
Object containing relationships to other CRM entities.
relation
Object describing a linked CRM element.
type.linkedUserFields
Object describing a set of fields in which the SPA should be displayed.
Object Structure
Object Structure
crm_multifield
crm_multifield
Value
type
Description
ID
integer
Identifier of the multifield value.
TYPE_ID
string
Type of the multifield. Can take values
PHONE
,
EMAIL
,
WEB
,
IM
,
LINK
.
VALUE
string
String value of the multifield.
VALUE_TYPE
string
Type of the multifield value.
Can take values
WORK
,
MOBILE
,
FAX
,
HOME
,
PAGER
,
MAILING
,
OTHER
for phone,
WORK
,
HOME
,
MAILING
,
OTHER
for email,
WORK
,
HOME
,
FACEBOOK
,
LIVEJOURNAL
,
TWITTER
,
OTHER
for website,
FACEBOOK
,
TELEGRAM
,
SKYPE
,
VIBER
,
INSTAGRAM
,
BITRIX24
,
OPENLINE
,
IMOL
,
ICQ
,
MSN
,
JABBER
,
OTHER
for messenger.
crm_item_product_row
crm_item_product_row
Value
type
Description
id
integer
Identifier of the product item.
ownerId
integer
Identifier of the CRM object.
ownerType
string
Identifier of the
CRM object type
.
productId
catalog_product.id
Identifier of the product from the catalog.
productName
string
Name of the product in the product item.
price
double
Price per unit of the product item, including discounts and taxes.
priceAccount
double
Price per unit of the product item, including discounts and taxes, converted to the reporting currency.
priceExclusive
double
Price per unit of the product item, including discounts but excluding taxes.
priceNetto
double
Price per unit of the product item, excluding discounts and taxes.
priceBrutto
double
Price per unit of the product item, including taxes but excluding discounts.
quantity
double
Quantity of the product.
discountTypeId
integer
Type of discount.
Possible values:
1
— absolute value
2
— percentage value.
discountRate
double
Discount value in percentage.
discountSum
double
Absolute discount value.
taxRate
double
Tax rate in percentage.
taxIncluded
string
Indicator of whether the tax is included in the price.
Possible values:
Y
– tax included
N
– tax not included.
customized
string
Deprecated.
measureCode
catalog_measure.code
Unit of measure code.
measureName
string
Text representation of the unit of measure (e.g., pcs, kg, m, l, etc.).
sort
integer
Sorting.
xmlId
string
External identifier of the product item.
type
integer
Type of product.
Possible values:
1
- Simple product
2
- Bundle
3
- Product with trade offers
4
- Trade offer
5
- Trade offer that has no product (not specified or deleted)
6
- Specific type, means invalid product with trade offers
7
— Service.
storeId
integer
Identifier of the inventory.
crm_currency
crm_currency
Value
type
Description
AMOUNT
double
Exchange rate relative to the base currency.
For the base currency, it is always equal to
1
. Precision — 4 decimal places.
AMOUNT_CNT
integer
Nominal value.
For the base currency, it is always equal to
1
.
BASE
string
Indicator of whether the currency is base (
Y
/
N
).
CURRENCY
string
Currency identifier. Corresponds to ISO 4217 standard.
DATE_UPDATE
datetime
Date of last modification.
SORT
integer
Sorting.
LID
string
Language code for which the
localization parameters
are returned.
DECIMALS
integer
Number of decimal places in the fractional part (localization parameter).
DEC_POINT
string
Decimal point for output (localization parameter).
FORMAT_STRING
string
Format template (localization parameter).
FULL_NAME
string
Name of the currency (localization parameter).
THOUSANDS_SEP
string
Thousands separator (localization parameter).
LANG
object
Currency localizations.
Object with a list of available localizations in the format
{"lang_1": "value_1", ... "lang_N": "value_N"}
, where
lang_N
— language identifier, and
value
— object of type
crm_currency_localization
.
Language identifier is a string of two Latin letters. Possible values can be found in the
table of language identifiers
.
crm_currency_localization
crm_currency_localization
Value
type
Description
DECIMALS
integer
Number of decimal places in the fractional part.
Default value —
2
.
DEC_POINT
string
Decimal point for output.
Default value —
.
(dot symbol).
FORMAT_STRING
string
Format template. Must contain the symbol # — instead, the price value will be substituted.
Default value —
#
.
Examples of templates for the amount 1000:
$ #
— $ 1000
# rub.
— 1000 rub.
€ #
— € 1000.
FULL_NAME
string
Name of the currency.
Default value —
crm_currency.CURRENCY
.
HIDE_ZERO
string
Indicator of whether to hide insignificant zeros (
Y
/
N
).
Default value —
N
.
THOUSANDS_SEP
string
Thousands separator.
Default value —
(space).
THOUSANDS_VARIANT
string
Code for the thousands separator.
Default value —
S
.
When creating or modifying localization, if a value is specified for the
THOUSANDS_VARIANT
field, the value in
THOUSANDS_SEP
will be ignored and replaced according to the list:
N
— empty, no thousands separator. Example: 12345678
C
— comma. Example: 12,345,678
D
— dot. Example: 12.345.678
S
— space. Example: 12 345 678
B
— non-breaking space. Example: 12 345 678
This differs from the previous option in that when line breaks occur, the result is not split into parts.
If a thousands separator is not needed, the
THOUSANDS_VARIANT
field must be explicitly passed with the value
N
. An empty string in the
THOUSANDS_SEP
field is not allowed.
crm_orderentity
crm_orderentity
Value
type
Description
OWNER_ID
integer
Identifier of the CRM object.
OWNER_TYPE_ID
integer
Identifier of the
CRM object type
.
ORDER_ID
sale_order.id
Identifier of the order.
type
type
Value
type
Description
id
integer
Identifier of the SPA.
title
string
Title of the SPA.
code
string
Symbolic code.
createdBy
integer
Identifier of the user who created this SPA.
entityTypeId
integer
Identifier of the entity type.
isCategoriesEnabled
boolean
Are custom funnels and sales tunnels enabled?
isStagesEnabled
boolean
Is the use of custom stages and Kanban enabled?
isBeginCloseDatesEnabled
boolean
Are the
Start Date
and
End Date
fields enabled?
isClientEnabled
boolean
Is the
Client
field enabled?
isUseInUserfieldEnabled
boolean
Is the use of the SPA in the user field enabled?
isLinkWithProductsEnabled
boolean
Is the linking of catalog products enabled?
isMycompanyEnabled
boolean
Is the
Your Company Details
field enabled?
isDocumentsEnabled
boolean
Is document printing enabled?
isSourceEnabled
boolean
Are the
Source
and
Additional Information about Source
fields enabled?
isObserversEnabled
boolean
Is the
Observers
field enabled?
isRecyclebinEnabled
boolean
Is the use of the recycle bin enabled?
isAutomationEnabled
boolean
Are automation rules and triggers enabled?
isBizProcEnabled
boolean
Is the use of the business process designer enabled?
isSetOpenPermissions
boolean
Should new funnels be available to everyone?
isPaymentsEnabled
boolean
System field indicating whether payment capability is enabled.
isCountersEnabled
boolean
System field indicating whether counters are enabled.
createdTime
datetime
System field indicating the creation time of the SPA.
updatedTime
datetime
System field indicating the time of modification of this SPA.
updatedBy
integer
Identifier of the user who modified this SPA.
relations
object
Object containing relationships to other CRM entities.
linkedUserFields
object
Set of fields in which this SPA should be displayed.
customSections
array
List of all digital workplaces.
This parameter is deprecated. To work with digital workplaces, use the methods
crm.automatedsolution.*
.
customSectionId
integer
Identifier of the digital workplace.
This parameter is deprecated. To work with digital workplaces, use the methods
crm.automatedsolution.*
.
type.relations
type.relations
Value
type
Description
parent
relation[]
CRM elements that will be linked to this SPA.
child
relation[]
CRM elements to which this SPA will be linked.
relation
relation
Value
type
Description
entityTypeId
integer
Identifier of the
system
or
user-defined type
of CRM entity.
isChildrenListEnabled
boolean
Should the linked element be added to the card?
isPredefined
boolean
Is this relationship predefined (system)?
type.linkedUserFields
type.linkedUserFields
Value
type
Description
CALENDAR_EVENT|UF_CRM_CAL_EVENT
boolean
Calendar event.
TASKS_TASK|UF_CRM_TASK
boolean
Tasks.
TASKS_TASK_TEMPLATE|UF_CRM_TASK
boolean
Task templates.
Language Identifiers for Bitrix24
Language Identifiers for Bitrix24
Language Identifier
Language
ar
Arabic
br
Portuguese (Brazil)
de
German
en
English
fr
French
hi
Hindi
id
Indonesian
it
Italian
ja
Japanese
la
Spanish
ms
Malay
pl
Polish
ru
Russian
sc
Chinese
tc
Chinese (Taiwan)
th
Thai
tr
Turkish
ua
Ukrainian
vn
Vietnamese
Objects Used in Responses
Objects Used in Responses
Description of a Single Field crm_rest_field_description
Description of a Single Field crm_rest_field_description
Name
type
Description
type
string
Type of the field.
isRequired
boolean
Is the field required?
isReadOnly
boolean
Is the field read-only?
isImmutable
boolean
Indicator of whether the field value can only be filled once when creating a new element.
isMultiple
boolean
Indicator of whether the field is multiple. If true, values in the field are passed as an array.
isDynamic
boolean
Is the field user-defined?
title
string
Name of the field.
upperName
string
Name of the field in uppercase.
Description of User Field Type Address
Description of User Field Type Address
The user field of type "Address" stores data in a single line. The table provides a description of the components of this line.
A detailed description of the components of the address can be found in the article
About Addresses
.
Name
type
Description
Example
ADDRESS_1
string
Street, house number
Small Znamenka Lane 7/10 b2
ADDRESS_2
string
Apartment, office, room, floor
5
POSTAL_CODE
string
Postal code
119019
CITY
string
Settlement
New York
REGION
string
District
Arbat District
PROVINCE
string
Region
New York
COUNTRY
string
Country
United States
LATITUDE
string
Latitude coordinates
55.748289
LONGITUDE
string
Longitude coordinates
37.60504
LOC_ADDR_ID
string
Location address identifier
10
CRM Object Type
CRM Object Type
Object Type
Numeric Identifier of Type
entityTypeId
Symbolic Code of Type
entityTypeName
Short Symbolic Code of Type
entityTypeAbbr
Type of User Field Object
userFieldEntityId
Lead
1
LEAD
L
CRM_LEAD
Deal
2
DEAL
D
CRM_DEAL
Contact
3
CONTACT
C
CRM_CONTACT
Company
4
COMPANY
CO
CRM_COMPANY
Invoice (old)
5
INVOICE
I
CRM_INVOICE
Invoice (new)
31
SMART_INVOICE
SI
CRM_SMART_INVOICE
Estimate
7
QUOTE
Q
CRM_QUOTE
Requisite
8
REQUISITE
RQ
CRM_REQUISITE
Order
14
ORDER
O
ORDER
SPA
128
DYNAMIC_128
T80
CRM_1
The table describes the SPA with type identifier 128 and identifier 1.
The identifiers of SPA types are in the range from 128 to 191 (inclusive), or have a value greater than 1030 (inclusive) and are even.
The identifiers of SPA types that have been deleted to the recycle bin are in the range from 192 to 255 (inclusive), or have a value greater than 1030 and are odd.
To determine the prefix of the SPA, it is necessary to:
convert the identifier from decimal to hexadecimal. In the case of an identifier equal to 128, we get the value 80.
take the obtained value in lowercase and prepend the Latin letter T to the obtained value. Thus, we get the prefix — T80.
Copied
Was the article helpful?
Yes
No
Previous
CRM Objects and Methods
Next
Fields of Main CRM Objects

---

## Fields of Main CRM Objects

**Source:** https://apidocs.bitrix24.com/api-reference/crm/main-entities-fields

Fields of Main CRM Objects | Bitrix24 REST API and Marketplace Applications
Fields of Main CRM Objects
Fields of Main CRM Objects
Attention!
A more complete list of fields can be found on the pages of methods that return the description of object fields. Such methods are named
crm.object_name.fields
.
Deals
Leads
Companies
Contacts
Requisites
Activities
The field description is returned by the method
crm.deal.fields
Name
type
Description
Read
Write
ID
integer
Deal identifier
Yes
No
TITLE
string
Title
Yes
Yes
TYPE_ID
crm_status
Type of deal. Used only for linking to external sources.
Yes
Yes
CATEGORY_ID
crm_category
Identifier of the direction. Immutable. If this field is not provided when creating a deal, the deal will be created in the general direction.
Yes
Yes
STAGE_ID
crm_status
Identifier of the stage. Possible values:
NEW
— new deal
PREPARATION
— preparing documents
PREPAYMENT_INVOICE
— sending invoice
EXECUTING
— in progress
FINAL_INVOICE
— final invoice
WON
— won
>LOSE
— lost, no analysis required
APOLOGY
— lost, analysis required
Yes
Yes
STAGE_SEMANTIC_ID
string
Name. Read-only. In a sense, summarizes the values of the deal identifier
STAGE_ID
:
P
— for stages with identifiers
NEW
,
PREPARATION
,
PREPAYMENT_INVOICE
,
EXECUTING
, and
FINAL_INVOICE
S
— for the stage with identifier
WON
F
— for stages with identifiers
>LOSE
and
APOLOGY
Yes
No
IS_NEW
char
Flag for a new deal (deals in the first stage)
Yes
No
IS_RECURRING
char
Flag for a recurring deal template. If set to
Y
, it is a template, not a deal
Yes
Yes
IS_RETURN_CUSTOMER
char
Indicator of a repeat lead
Yes
Yes
IS_REPEATED_APPROACH
char
Repeated approach
Yes
Yes
PROBABILITY
integer
Probability
Yes
Yes
CURRENCY_ID
crm_currency
Identifier of the deal currency
Yes
Yes
OPPORTUNITY
double
Amount
Yes
Yes
IS_MANUAL_OPPORTUNITY
char
Indicator of manual opportunity calculation
Yes
Yes
TAX_VALUE
double
Tax rate
Yes
Yes
COMPANY_ID
crm_company
Identifier of the linked company
Yes
Yes
CONTACT_ID
crm_contact
Identifier of the linked contact. Deprecated. Kept for compatibility
Yes
Yes
CONTACT_IDS
crm_contact
Identifier of the linked contact. Multiple.
When using
crm.deal.update
and
crm.deal.add
, an array of contacts can be submitted.
In the methods
crm.deal.list
and
crm.deal.get
, this field does not exist, and
crm.deal.contact.items.get
should be used to get the list of contacts.
To clear the field, use
crm.deal.contact.items.delete
, to replace the value use
crm.deal.contact.items.set
Yes
Yes
QUOTE_ID
crm_quote
Identifier of the quote. Read-only. Deprecated. Use the method
crm.quote.list
with a filter by deal
Yes
No
BEGINDATE
date
Start date
Yes
Yes
CLOSEDATE
date
End date
Yes
Yes
OPENED
char
Available to everyone
Yes
Yes
CLOSED
char
Whether the deal is closed
Yes
Yes
COMMENTS
string
Comments
Yes
Yes
ASSIGNED_BY_ID
user
Linked to user by ID
Yes
Yes
CREATED_BY_ID
user
Created by user
Yes
No
MODIFY_BY_ID
user
Identifier of the author of the last change
Yes
No
MOVED_BY_ID
user
Identifier of the author who moved the item to the current stage
Yes
No
DATE_CREATE
datetime
Creation date
Yes
No
DATE_MODIFY
datetime
Modification date
Yes
No
MOVED_TIME
datetime
Date of moving the item to the current stage
Yes
No
SOURCE_ID
string
Identifier of the source. Defines the source of the deal (callback, advertisement, e-mail, etc.).
A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=SOURCE
Yes
Yes
SOURCE_DESCRIPTION
string
Additional information about the source. Text field
Yes
Yes
ADDITIONAL_INFO
string
Additional information
Yes
Yes
LEAD_ID
crm_lead
Identifier of the linked lead
Yes
No
LOCATION_ID
location
Client's location. Service field, not recommended for use
Yes
Yes
ORIGINATOR_ID
string
Identifier of the data source. Used only for linking to external sources
Yes
Yes
ORIGIN_ID
string
Identifier of the item in the data source. Used only for linking to external sources
Yes
Yes
UTM_SOURCE
string
Advertising system (Google-Adwords, etc.)
Yes
Yes
UTM_MEDIUM
string
Type of traffic: CPC (ads), CPM (banners)
Yes
Yes
UTM_CAMPAIGN
string
Designation of the advertising campaign
Yes
Yes
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
Yes
Yes
UTM_TERM
string
Search condition of the campaign. For example, keywords for contextual advertising
Yes
Yes
PARENT_ID_xxx
crm_entity
Relationship fields.
If there are SPAs related to contacts on the account, then for each such SPA there is a field that stores the relationship between this SPA and the contact. The field itself stores the identifier of the item of that SPA.
For example, the field
PARENT_ID_153
— relationship with the SPA
entityTypeId=153
, stores the identifier of the item of this SPA related to the current contact
Yes
Yes
LAST_ACTIVITY_BY
string
Identifier of the user responsible for the last activity in this lead (for example, who created a new deal in the lead)
Yes
Yes
LAST_ACTIVITY_TIME
datetime
Time of the last activity
Yes
Yes
UF_CRM_xxx
User-defined fields
Yes
Yes
The field description is returned by the method
crm.lead.fields
Name
type
Description
Read
Write
ID
integer
Integer identifier of the lead
Yes
No
TITLE
string
Title of the lead
Yes
Yes
HONORIFIC
crm_status
Form of address. Status from the directory.
A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=HONORIFIC
Yes
Yes
NAME
string
Contact's first name
Yes
Yes
SECOND_NAME
string
Contact's middle name
Yes
Yes
LAST_NAME
string
Contact's last name
Yes
Yes
BIRTHDATE
date
Date of birth
Yes
Yes
COMPANY_TITLE
string
Title of the company linked to the lead
Yes
Yes
SOURCE_ID
crm_status
Identifier of the source. Status from the directory.
A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=SOURCE
Yes
Yes
SOURCE_DESCRIPTION
string
Description of the source
Yes
Yes
STATUS_ID
crm_status
Identifier of the lead stage. Status from the directory.
A list of possible identifiers can be obtained using the method
crm.status.list
with the filter
filter[ENTITY_ID]=STATUS
Yes
Yes
STATUS_DESCRIPTION
string
Additional information about the stage
Yes
Yes
STATUS_SEMANTIC_ID
string
Status. Possible values:
F
(failed) — processed unsuccessfully
S
(success) — processed successfully
P
(processing) — lead in processing
Yes
No
POST
string
Position
Yes
Yes
ADDRESS
string
Contact's address
Yes
Yes
ADDRESS_2
string
Second line of the address. In some countries, it is customary to split the address into 2 parts
Yes
Yes
ADDRESS_CITY
string
City
Yes
Yes
ADDRESS_POSTAL_CODE
string
Postal code
Yes
Yes
ADDRESS_REGION
string
Region
Yes
Yes
ADDRESS_PROVINCE
string
Province
Yes
Yes
ADDRESS_COUNTRY
string
Country
Yes
Yes
ADDRESS_COUNTRY_CODE
string
Country code
Yes
Yes
ADDRESS_LOC_ADDR_ID
integer
Identifier of the address from the location module
Yes
Yes
CURRENCY_ID
crm_currency
Identifier of the currency
Yes
Yes
OPPORTUNITY
double
Estimated amount
Yes
Yes
IS_MANUAL_OPPORTUNITY
char
Indicator of manual calculation of the amount. Allowed values
Y
or
N
Yes
Yes
OPENED
char
Available to everyone. Allowed values
Y
or
N
Yes
Yes
COMMENTS
string
Comments
Yes
Yes
HAS_PHONE
char
Indicator of the phone field being filled. Allowed values
Y
or
N
Yes
No
HAS_EMAIL
char
Indicator of the e-mail field being filled. Allowed values
Y
or
N
Yes
No
HAS_IMOL
char
Indicator of the presence of a linked open line. Allowed values
Y
or
N
Yes
No
ASSIGNED_BY_ID
user
Identifier of the user responsible for the lead
Yes
Yes
CREATED_BY_ID
user
Identifier of the user who created the lead
Yes
No
MODIFY_BY_ID
user
Identifier of the author of the last change
Yes
No
MOVED_BY_ID
user
Identifier of the author who moved the item to the current stage
Yes
No
DATE_CREATE
datetime
Creation date
Yes
No
DATE_MODIFY
datetime
Modification date
Yes
No
MOVED_TIME
datetime
Date of moving the item to the current stage
Yes
No
COMPANY_ID
crm_company
Linking the lead to a company (Field Client->Company)
Yes
Yes
CONTACT_ID
crm_contact
Linking the lead to a contact. Deprecated field, currently not used. Kept for backward compatibility
Yes
Yes
CONTACT_IDS
crm_contact
Identifier of the linked contact. Multiple.
When using
crm.lead.update
and
crm.lead.add
, an array of contacts can be submitted
Yes
Yes
IS_RETURN_CUSTOMER
char
Indicator of a repeat lead. Allowed values
Y
or
N
Yes
No
DATE_CLOSED
datetime
Closing date
Yes
No
ORIGINATOR_ID
string
Identifier of the data source. Used only for linking to external sources
Yes
Yes
ORIGIN_ID
string
Identifier of the item in the data source. Used only for linking to external sources
Yes
Yes
UTM_SOURCE
string
Advertising system (Google-Adwords, etc.)
Yes
Yes
UTM_MEDIUM
string
Type of traffic: CPC (ads), CPM (banners)
Yes
Yes
UTM_CAMPAIGN
string
Designation of the advertising campaign
Yes
Yes
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
Yes
Yes
UTM_TERM
string
Search condition of the campaign. For example, keywords for contextual advertising
Yes
Yes
LAST_ACTIVITY_TIME
datetime
Time of the last activity
Yes
No
LAST_ACTIVITY_BY
string
Identifier of the user responsible for the last activity in this lead (for example, who created a new deal in the lead)
Yes
No
PHONE
crm_multifield
Contact's phone. Multiple
Yes
Yes
EMAIL
crm_multifield
E-mail address. Multiple
Yes
Yes
WEB
crm_multifield
URLs of the lead. Multiple
Yes
Yes
IM
crm_multifield
Messengers. Multiple
Yes
Yes
LINK
crm_multifield
Links. Multiple. Service
Yes
Yes
UF_CRM_xxx
User-defined fields
Yes
Yes
The field description is returned by the method
crm.company.fields
Name
type
Description
Read
Write
ID
integer
Identifier of the company
Yes
No
TITLE
string
Name. Required
Yes
Yes
COMPANY_TYPE
crm_status
Type of company
Yes
Yes
LOGO
file
Logo
Yes
Yes
ADDRESS
string
Address of the company
Yes
Yes
ADDRESS_2
string
Second line of the address. In some countries, it is customary to split the address into 2 parts
Yes
Yes
ADDRESS_CITY
string
City
Yes
Yes
ADDRESS_POSTAL_CODE
string
Postal code
Yes
Yes
ADDRESS_REGION
string
Region
Yes
Yes
ADDRESS_PROVINCE
string
Province
Yes
Yes
ADDRESS_COUNTRY
string
Country
Yes
Yes
ADDRESS_COUNTRY_CODE
string
Country code
Yes
Yes
ADDRESS_LOC_ADDR_ID
integer
Identifier of the location address
Yes
Yes
ADDRESS_LEGAL
string
Legal address
Yes
Yes
REG_ADDRESS
string
Legal address of the company. Deprecated, used for compatibility
Yes
Yes
REG_ADDRESS_2
string
Second line of the legal address. In some countries, it is customary to split the address into 2 parts.
Deprecated, used for compatibility
Yes
Yes
REG_ADDRESS_CITY
string
City of the legal address. Deprecated, used for compatibility
Yes
Yes
REG_ADDRESS_POSTAL_CODE
string
Postal code of the legal address. Deprecated, used for compatibility
Yes
Yes
REG_ADDRESS_REGION
string
Region of the legal address. Deprecated, used for compatibility
Yes
Yes
REG_ADDRESS_PROVINCE
string
Province of the legal address. Deprecated, used for compatibility
Yes
Yes
REG_ADDRESS_COUNTRY
string
Country of the legal address. Deprecated, used for compatibility
Yes
Yes
REG_ADDRESS_COUNTRY_CODE
string
Country code of the legal address. Deprecated, used for compatibility
Yes
Yes
REG_ADDRESS_LOC_ADDR_ID
integer
Legal address identifier of the location address. Deprecated, used for compatibility
Yes
Yes
BANKING_DETAILS
string
Banking details
Yes
Yes
INDUSTRY
crm_status
Industry
Yes
Yes
EMPLOYEES
crm_status
Number of employees
Yes
Yes
CURRENCY_ID
crm_currency
Currency
Yes
Yes
REVENUE
double
Annual revenue
Yes
Yes
OPENED
char
Available to everyone
Yes
Yes
COMMENTS
string
Comments
Yes
Yes
HAS_PHONE
char
Check for the phone field being filled
Yes
No
HAS_EMAIL
char
Check for the e-mail field being filled
Yes
No
HAS_IMOL
char
Is there an open line
Yes
No
IS_MY_COMPANY
char
My company
Yes
Yes
ASSIGNED_BY_ID
user
Linked to user by ID
Yes
Yes
CREATED_BY_ID
user
Who created the company
Yes
No
MODIFY_BY_ID
user
Identifier of the author of the last change
Yes
No
DATE_CREATE
datetime
Creation date
Yes
No
DATE_MODIFY
datetime
Modification date
Yes
No
CONTACT_ID
string
Contact. Used only for linking to external sources.
Yes
Yes
LEAD_ID
crm_lead
Identifier of the lead associated with the company
Yes
No
ORIGINATOR_ID
string
Identifier of the data source. Used only for linking to external sources
Yes
Yes
ORIGIN_ID
string
Identifier of the item in the data source. Used only for linking to external sources
Yes
Yes
ORIGIN_VERSION
string
Original version. Used to protect data from accidental overwriting by an external system.
If the data was imported and not changed in the external system, such data can be edited in CRM without fear that the next export will overwrite the data
Yes
Yes
UTM_SOURCE
string
Advertising system (Google-Adwords, etc.)
Yes
Yes
UTM_MEDIUM
string
Type of traffic: CPC (ads), CPM (banners)
Yes
Yes
UTM_CAMPAIGN
string
Designation of the advertising campaign
Yes
Yes
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
Yes
Yes
UTM_TERM
string
Search condition of the campaign. For example, keywords for contextual advertising
Yes
Yes
PARENT_ID_xxx
crm_entity
Relationship fields.
If there are SPAs related to contacts on the account, for each such SPA there is a field that stores the relationship between this SPA and the contact. The field itself stores the identifier of the item of that SPA.
For example, the field
PARENT_ID_153
— relationship with the SPA
entityTypeId=153
, stores the identifier of the item of this SPA related to the current contact
Yes
Yes
LAST_ACTIVITY_TIME
datetime
Time of the last activity.
Yes
No
LAST_ACTIVITY_BY
string
Identifier of the user responsible for the last activity in this lead (for example, who created a new deal in the lead)
Yes
No
PHONE
crm_multifield
Phone of the company. Multiple
Yes
Yes
EMAIL
crm_multifield
E-mail address. Multiple
Yes
Yes
WEB
crm_multifield
URLs of the company. Multiple
Yes
Yes
IM
crm_multifield
Messengers. Multiple
Yes
Yes
LINK
crm_multifield
Links. Multiple. Service
Yes
Yes
UF_CRM_xxx
User-defined fields
Yes
Yes
The field description is returned by the method
crm.contact.fields
Name
type
Description
Read
Write
ID
integer
Identifier of the contact
Yes
No
HONORIFIC
crm_status
Addressing.
Values from the directory can be obtained using the method
crm.status.list
with the filter by
ENTITY_ID=HONORIFIC
Yes
Yes
NAME
string
First name
Yes
Yes
SECOND_NAME
string
Middle name
Yes
Yes
LAST_NAME
string
Last name
Yes
Yes
PHOTO
file
Photo
Yes
Yes
BIRTHDATE
date
Date of birth
Yes
Yes
TYPE_ID
crm_status
Type of contact.
Values from the directory can be obtained using the method
crm.status.list
with the filter by
ENTITY_ID=CONTACT_TYPE
Yes
Yes
SOURCE_ID
crm_status
Source.
Values from the directory can be obtained using the method
crm.status.list
with the filter by
ENTITY_ID=SOURCE
Yes
Yes
SOURCE_DESCRIPTION
string
Additional information about the source
Yes
Yes
POST
string
Position
Yes
Yes
Deprecated fields
Address fields in the contact are deprecated and are only used in compatibility mode. To work with the address, use
requisites
.
ADDRESS
string
Address (deprecated)
Yes
Yes
ADDRESS_2
string
Second line of the address (deprecated)
Yes
Yes
ADDRESS_CITY
string
City (deprecated)
Yes
Yes
ADDRESS_POSTAL_CODE
string
Postal code (deprecated)
Yes
Yes
ADDRESS_REGION
string
Region (deprecated)
Yes
Yes
ADDRESS_PROVINCE
string
Province (deprecated)
Yes
Yes
ADDRESS_COUNTRY
string
Country (deprecated)
Yes
Yes
ADDRESS_COUNTRY_CODE
string
Country code (deprecated)
Yes
Yes
ADDRESS_LOC_ADDR_ID
location
Identifier of the location address (deprecated)
Yes
Yes
COMMENTS
string
Comment. Supports bb-codes
Yes
Yes
OPENED
char
Available to everyone. Can take values
Y
or
N
. Considered in the work of access permissions for roles with the access level "All open"
Yes
Yes
EXPORT
char
Participates in the export of contacts. Can take values
Y
or
N
Yes
Yes
HAS_PHONE
char
Phone is set. Can take values
Y
or
N
Yes
No
HAS_EMAIL
char
E-mail is set. Can take values
Y
or
N
Yes
No
HAS_IMOL
char
Open line is set. Can take values
Y
or
N
Yes
No
ASSIGNED_BY_ID
user
Responsible
Yes
Yes
CREATED_BY_ID
user
Who created
Yes
No
MODIFY_BY_ID
user
Who modified
Yes
No
DATE_CREATE
datetime
Creation date
Yes
No
DATE_MODIFY
datetime
Modification date
Yes
No
COMPANY_ID
crm_company
Main company of the contact
Yes
Yes
COMPANY_IDS
crm_company
Linking the contact to companies. Multiple.
In the methods
crm.contact.update
and
crm.contact.add
, it is used to submit an array of companies.
In the methods
crm.contact.list
and
crm.contact.get
, this field does not exist, and
crm.contact.company.items.get
should be used to get the list of companies
Yes
Yes
LEAD_ID
crm_lead
Identifier of the lead associated with the contact
Yes
No
Fields for linking to external data sources
If the contact was created by an external system, then:
the field
ORIGINATOR_ID
stores the string identifier of that system
the field
ORIGIN_ID
stores the string identifier of the contact in that external system
the field
ORIGIN_VERSION
stores the version of the contact data in that external system
ORIGINATOR_ID
string
Identifier of the external system that is the source of data about this contact
Yes
Yes
ORIGIN_ID
string
Identifier of the contact in the external system
Yes
Yes
ORIGIN_VERSION
string
Version of the contact data in the external system. Used to protect data from accidental overwriting by an external system.
If the data was imported and not changed in the external system, such data can be edited in CRM without fear that the next export will overwrite the data.
Yes
Yes
FACE_ID
integer
Link to faces from the
faceid
module
Yes
No
UTM_SOURCE
string
Advertising system (Google-Adwords, etc.)
Yes
Yes
UTM_MEDIUM
string
Type of traffic: CPC (ads), CPM (banners)
Yes
Yes
UTM_CAMPAIGN
string
Designation of the advertising campaign
Yes
Yes
UTM_CONTENT
string
Content of the campaign. For example, for contextual ads
Yes
Yes
UTM_TERM
string
Search condition of the campaign. For example, keywords for contextual advertising
Yes
Yes
PARENT_ID_...
Relationship fields.
If there are SPAs related to contacts on the account, for each such SPA there is a field that stores the relationship between this SPA and the contact. The field itself stores the identifier of the item of that SPA.
For example, the field
PARENT_ID_153
— relationship with the SPA
entityTypeId=153
, stores the identifier of the item of this SPA related to the current contact
Yes
Yes
LAST_ACTIVITY_TIME
datetime
Date of the last activity in the timeline
Yes
No
LAST_ACTIVITY_BY
user
Author of the last activity in the timeline
Yes
No
PHONE
crm_multifield
Phones. Multiple
Yes
Yes
EMAIL
crm_multifield
E-mail. Multiple
Yes
Yes
WEB
crm_multifield
Websites. Multiple
Yes
Yes
IM
crm_multifield
Messengers. Multiple
Yes
Yes
LINK
crm_multifield
Links. Multiple. Service
Yes
Yes
UF_CRM_xxx
User-defined fields. For example,
UF_CRM_25534736
.
Depending on the portal settings, contacts may have a set of user-defined fields of specific types. A user-defined field can be added to a contact using the method
crm.contact.userfield.add
General Requisites
General Requisites
The field description is returned by the method
crm.requisite.fields
Name
type
Description
Read
Write
ID
integer
Identifier of the requisite.
Can be obtained using the method
crm.requisite.list
.
Created automatically and unique within the portal
Yes
No
ENTITY_TYPE_ID
integer
Identifier of the parent entity type. Currently, this can only be:
3
— contact
4
— company
Identifiers of all CRM entity types are returned by the method
crm.enum.ownertype
Yes
Yes
ENTITY_ID
integer
Identifier of the parent entity (contact or company).
The identifier can be obtained using the method
crm.company.list
for a company and the method
crm.contact.list
for a contact
Yes
Yes
PRESET_ID
integer
Identifier of the requisites template.
Template identifiers can be obtained using the method
crm.requisite.preset.list
Yes
Yes
DATE_CREATE
datetime
Creation date
Yes
No
DATE_MODIFY
datetime
Modification date
Yes
No
CREATED_BY_ID
user
Identifier of the user who created the requisite
Yes
No
MODIFY_BY_ID
user
Identifier of the user who modified the requisite
Yes
No
NAME
string
Name of the requisite
Yes
Yes
CODE
string
Symbolic code of the requisite
Yes
Yes
XML_ID
string
External key, used for exchange operations.
Identifier of the object in the external information database.
The purpose of the field may change by the end developer
Yes
Yes
ORIGINATOR_ID
string
Identifier of the external information database.
The purpose of the field may change by the end developer
Yes
Yes
ACTIVE
char
Activity indicator.
Values
Y
or
N
are used.
Currently, the field does not actually affect anything
Yes
Yes
ADDRESS_ONLY
char
Indicator of the state when the requisite is used only for storing the address.
Values
Y
or
N
are used. When set to
Y
, the requisites are not displayed in the entity card, but the address is displayed
Yes
Yes
SORT
integer
Sorting. Order in the list of entity requisites when there are multiple
Yes
Yes
RQ_NAME
string
Full name
Yes
Yes
RQ_FIRST_NAME
string
First name
Yes
Yes
RQ_LAST_NAME
string
Last name
Yes
Yes
RQ_SECOND_NAME
string
Middle name
Yes
Yes
RQ_COMPANY_ID
string
Identifier of the organization
Yes
Yes
RQ_COMPANY_NAME
string
Short name of the organization
Yes
Yes
RQ_COMPANY_FULL_NAME
string
Full name of the organization
Yes
Yes
RQ_COMPANY_REG_DATE
string
Date of state registration
Yes
Yes
RQ_DIRECTOR
string
General director
Yes
Yes
RQ_ACCOUNTANT
string
Chief accountant
Yes
Yes
RQ_CEO_NAME
string
Full name of the first leader
Yes
Yes
RQ_CEO_WORK_POS
string
Position of the first leader
Yes
Yes
RQ_CONTACT
string
Contact person
Yes
Yes
RQ_EMAIL
string
E-Mail
Yes
Yes
RQ_PHONE
string
Phone
Yes
Yes
RQ_FAX
string
Fax
Yes
Yes
RQ_IDENT_TYPE
crm_status
Method of identification
Yes
Yes
RQ_IDENT_DOC
string
Type of document
Yes
Yes
RQ_IDENT_DOC_SER
string
Series
Yes
Yes
RQ_IDENT_DOC_NUM
string
Number
Yes
Yes
RQ_IDENT_DOC_PERS_NUM
string
Personal number
Yes
Yes
RQ_IDENT_DOC_DATE
string
Date of issue
Yes
Yes
RQ_IDENT_DOC_ISSUED_BY
string
Issued by
Yes
Yes
RQ_IDENT_DOC_DEP_CODE
string
Department code
Yes
Yes
RQ_INN
string
Taxpayer identification number
Yes
Yes
RQ_KPP
string
Tax registration reason code
Yes
Yes
RQ_USRLE
string
Commercial register number (for country DE)
Yes
Yes
RQ_IFNS
string
Tax authority
Yes
Yes
RQ_OGRN
string
Primary state registration number
Yes
Yes
RQ_OGRNIP
string
Primary state registration number for individual entrepreneurs
Yes
Yes
RQ_OKPO
string
National classification of enterprises and organizations
Yes
Yes
RQ_OKTMO
string
Municipal classification of territories
Yes
Yes
RQ_OKVED
string
All-Russian classifier of economic activities
Yes
Yes
RQ_EDRPOU
string
Unified State Register of Enterprises and Organizations
Yes
Yes
RQ_DRFO
string
Taxpayer registration number
Yes
Yes
RQ_KBE
string
Classification of economic activities
Yes
Yes
RQ_IIN
string
Individual identification number
Yes
Yes
RQ_BIN
string
Business identification number
Yes
Yes
RQ_ST_CERT_SER
string
Series of the state registration certificate
Yes
Yes
RQ_ST_CERT_NUM
string
Number of the state registration certificate
Yes
Yes
RQ_ST_CERT_DATE
string
Date of the state registration certificate
Yes
Yes
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
RQ_VAT_ID
string
VAT ID (identification number of the VAT payer)
Yes
Yes
RQ_VAT_CERT_SER
string
Series of the VAT certificate
Yes
Yes
RQ_VAT_CERT_NUM
string
Number of the VAT certificate
Yes
Yes
RQ_VAT_CERT_DATE
string
Date of the VAT certificate
Yes
Yes
RQ_RESIDENCE_COUNTRY
string
Country of residence
Yes
Yes
RQ_BASE_DOC
string
Basis for action
Yes
Yes
RQ_REGON
string
REGON (for country PL)
Yes
Yes
RQ_KRS
string
KRS (for country PL)
Yes
Yes
RQ_PESEL
string
PESEL (for country PL)
Yes
Yes
RQ_LEGAL_FORM
string
Legal form (for country FR)
Yes
Yes
RQ_SIRET
string
SIRET number (for country FR)
Yes
Yes
RQ_SIREN
string
SIREN number (for country FR)
Yes
Yes
RQ_CAPITAL
string
Share capital (for country FR)
Yes
Yes
RQ_RCS
string
RCS (for country FR)
Yes
Yes
RQ_CNPJ
string
CNPJ (for country BR)
Yes
Yes
RQ_STATE_REG
string
State registration (IE) (for country BR)
Yes
Yes
RQ_MNPL_REG
string
Municipal registration (IM) (for country BR)
Yes
Yes
RQ_CPF
string
CPF (for country BR)
Yes
Yes
UF_CRM_...
User-defined fields. For example,
UF_CRM_1694526604
.
Requisites may have a set of user-defined fields with types:
string
,
boolean
,
double
,
datetime
.
A user-defined field can be added to requisites using the method
crm.requisite.userfield.add
Yes
Yes
Bank Details
Bank Details
The field description is returned by the method
crm.requisite.bankdetail.fields
Name
type
Description
Read
Write
ID
integer
Identifier of the bank detail. Created automatically and unique within the portal
Yes
No
ENTITY_TYPE_ID
integer
Identifier of the parent object type. Can only be
Requisite
(value
8
).
Identifiers of object types are returned by the method
crm.enum.ownertype
Yes
No
ENTITY_ID
integer
Identifier of the parent object
Yes
Yes
COUNTRY_ID
integer
Identifier of the country corresponding to the set of bank detail fields (see method
crm.requisite.preset.countries
for available values).
The country code of the bank detail matches the country code in the linked requisites template, the identifier of which is specified in the field
ENTITY_ID
Yes
Yes
DATE_CREATE
datetime
Creation date
Yes
No
DATE_MODIFY
datetime
Modification date
Yes
No
CREATED_BY_ID
user
Identifier of the user who created the requisite
Yes
No
MODIFY_BY_ID
user
Identifier of the user who modified the requisite
Yes
No
NAME
*
string
Name of the bank detail
Yes
Yes
CODE
string
Symbolic code of the requisite
Yes
Yes
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information database.
The purpose of the field may change by the end developer. Each application ensures the uniqueness of values in this field.
It is recommended to use a unique prefix to avoid collisions with other applications
Yes
Yes
ACTIVE
char
Activity indicator. Values
Y
or
N
are used.
Currently, the field does not actually affect anything
Yes
Yes
SORT
integer
Sorting
Yes
Yes
RQ_BANK_NAME
string
Name of the bank
Yes
Yes
RQ_BANK_ADDR
string
Address of the bank
Yes
Yes
RQ_BANK_CODE
string
Bank code (for country BR)
Yes
Yes
RQ_BANK_ROUTE_NUM
string
Bank Routing Number
Yes
Yes
RQ_BIK
string
BIK
Yes
Yes
RQ_CODEB
string
Bank Code (for country FR)
Yes
Yes
RQ_CODEG
string
Branch Code (for country FR)
Yes
Yes
RQ_RIB
string
RIB Key (for country FR)
Yes
Yes
RQ_MFO
string
MFO
Yes
Yes
RQ_ACC_NAME
string
Bank Account Holder Name
Yes
Yes
RQ_ACC_NUM
string
Bank Account Number
Yes
Yes
RQ_ACC_TYPE
string
Account Type (for country BR)
Yes
Yes
RQ_AGENCY_NAME
string
Agency (for country BR)
Yes
Yes
RQ_IIK
string
IIK
Yes
Yes
RQ_ACC_CURRENCY
string
Currency of the account
Yes
Yes
RQ_COR_ACC_NUM
string
Correspondent account
Yes
Yes
RQ_IBAN
string
IBAN
Yes
Yes
RQ_SWIFT
string
SWIFT
Yes
Yes
RQ_BIC
string
BIC
Yes
Yes
COMMENTS
string
Comment
Yes
Yes
ORIGINATOR_ID
string
Identifier of the external information database. The purpose of the field may change by the end developer
Yes
Yes
Templates of Requisites
Templates of Requisites
The field description is returned by the method
crm.requisite.preset.fields
Name
Description
Read
Write
ID
integer
Identifier of the requisite. Created automatically and unique within the portal
Yes
No
ENTITY_TYPE_ID
integer
Identifier of the parent object type.
Identifiers of CRM object types are returned by the method
crm.enum.ownertype
Yes
Yes
COUNTRY_ID
integer
Identifier of the country corresponding to the set of fields of the requisites template (for available values see method
crm.requisite.preset.countries
)
Yes
Yes
DATE_CREATE
datetime
Creation date
Yes
No
DATE_MODIFY
datetime
Modification date. Contains an empty string if the template has not been changed since creation
Yes
No
CREATED_BY_ID
user
Identifier of the user who created the requisite
Yes
No
MODIFY_BY_ID
user
Identifier of the user who modified the requisite
Yes
No
NAME
string
Name of the requisite
Yes
Yes
XML_ID
string
External key. Used for exchange operations. Identifier of the object in the external information database.
The purpose of the field may change by the end developer.
Each application ensures the uniqueness of values in this field. It is recommended to use a unique prefix to avoid collisions with other applications.
Values of the form
#CRM_REQUISITE_PRESET_DEF_...
are reserved in CRM for identifying templates that are used by default. These identifiers should not be used for your purposes, as this may lead to a violation of logic
Yes
Yes
ACTIVE
char
Activity indicator. Values
Y
or
N
are used. Determines the availability of the template in the selection list when adding requisites
Yes
Yes
SORT
integer
Sorting
Yes
Yes
Fields of Requisites Templates
Fields of Requisites Templates
The field description is returned by the method
crm.requisite.preset.field.fields
Name
type
Description
Read
Write
ID
integer
Identifier of the field. Created automatically and unique within the template
Yes
No
FIELD_NAME
string
Name of the field
Yes
Yes
FIELD_TITLE
string
Alternative name of the field for the requisite.
The alternative name is displayed in various forms for filling requisites. Depending on the specific form, the alternative name may or may not be used
Yes
Yes
SORT
integer
Sorting. Order in the list of template fields
Yes
Yes
IN_SHORT_LIST
char
Show in the short list. Deprecated field, currently not used. Kept for backward compatibility. Can take values
Y
or
N
Yes
Yes
Addresses of Requisites
Addresses of Requisites
The field description is returned by the method
crm.address.fields
Name
Description
Read
Write
TYPE_ID
integer
Identifier of the address type. Element of the enumeration "Address Type".
Elements of the enumeration "Address Type" can be obtained using the method
crm.enum.addresstype
Yes
Yes
ENTITY_TYPE_ID
integer
Identifier of the parent object type.
Identifiers of object types can be obtained using the method
crm.enum.ownertype
.
Addresses can only be linked to Requisites (and requisites to companies or contacts) or Leads. For backward compatibility, the ability to link Addresses to Contacts or Companies has been left. However, this link is only possible on some old portals where the old address handling mode was specifically enabled by technical support.
Yes
Yes
ENTITY_ID
string
Identifier of the parent object
Yes
Yes
ADDRESS_1
string
Street, house, building
Yes
Yes
ADDRESS_2
string
Apartment / office
Yes
Yes
CITY
string
City
Yes
Yes
POSTAL_CODE
string
Postal code
Yes
Yes
REGION
string
Region
Yes
Yes
PROVINCE
string
Province
Yes
Yes
COUNTRY
string
Country
Yes
Yes
COUNTRY_CODE
string
Country code
Yes
Yes
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
module address is specified when creating an address, a copy of the
location
address is created and linked to the created CRM address. If in this case no values are specified for the string address fields, they will be filled from the location address.
If at least one string field was specified, then only the specified fields will be saved in the CRM address, and their values will overwrite the corresponding values in the location address object. The same behavior will occur when updating the address
Yes
Yes
ANCHOR_TYPE_ID
integer
Identifier of the type of the main parent object.
This field is for service use. The value is automatically filled when adding an address.
Identifiers of object types can be obtained using the method
crm.enum.ownertype
.
This field contains the identifier of the type of the parent requisite object (company or contact) if the address is linked to the requisite. If the address is linked to a lead, then this value will be the identifier of the lead
Yes
No
ANCHOR_ID
integer
This field is for service use. The value is automatically filled when adding an address.
This field contains the identifier of the parent requisite object (company or contact) if the address is linked to the requisite. If the address is linked to a lead, then this value will be the identifier of the lead
Yes
No
The field description is returned by the method
crm.activity.fields
Name
Description
Read
Write
ID
integer
Identifier of the activity
Yes
No
OWNER_ID
integer
Identifier of the owner, immutable
Yes
Yes
OWNER_TYPE_ID
crm.enum.ownertype
Type of owner, immutable
Yes
Yes
TYPE_ID
crm_enum_activitytype
Type, immutable
Yes
Yes
PROVIDER_ID
string
Identifier of the provider
Yes
Yes
PROVIDER_TYPE_ID
string
Identifier of the provider type
Yes
Yes
PROVIDER_GROUP_ID
string
Type of connector
Yes
Yes
ASSOCIATED_ENTITY_ID
integer
Identifier of the entity associated with the activity
Yes
No
SUBJECT
string
Subject, title of the activity
Yes
Yes
START_TIME
datetime
Start time of execution
Yes
Yes
END_TIME
datetime
End time
Yes
Yes
DEADLINE
datetime
Deadline. The field is not set directly; the value is taken from
START_TIME
for calls and meetings and from
END_TIME
for tasks
Yes
Yes
COMPLETED
char
Completed
Yes
Yes
STATUS
crm_enum_activitystatus
Status
Yes
Yes
RESPONSIBLE_ID
user
Responsible
Yes
Yes
PRIORITY
crm.enum.activitypriority
Importance
Yes
Yes
NOTIFY_TYPE
crm.enum.activitynotifytype
Type of notifications
Yes
Yes
NOTIFY_VALUE
integer
Notification parameter
Yes
Yes
DESCRIPTION
string
Description
Yes
Yes
DESCRIPTION_TYPE
crm.enum.contenttype
Type of description
Yes
Yes
DIRECTION
crm.enum.activitydirection
Direction of the activity: incoming/outgoing. Relevant for calls and emails, not used for meetings
Yes
Yes
LOCATION
string
Location
Yes
Yes
CREATED
datetime
Creation date
Yes
No
AUTHOR_ID
user
Creator of the activity
Yes
Yes
LAST_UPDATED
datetime
Date of the last update
Yes
No
EDITOR_ID
user
Who modified
Yes
No
SETTINGS
object
Settings
Yes
Yes
ORIGIN_ID
string
Identifier of the item in the data source. Used only for linking to external sources
Yes
Yes
ORIGINATOR_ID
string
Identifier of the data source. Used only for linking to external sources
Yes
Yes
RESULT_STATUS
integer
Unused field, remains for compatibility
Yes
Yes
RESULT_STREAM
integer
Report statistics
Yes
Yes
RESULT_SOURCE_ID
string
Unused field, remains for compatibility
Yes
Yes
PROVIDER_PARAMS
object
Provider parameters
Yes
Yes
PROVIDER_DATA
string
Provider data
Yes
Yes
RESULT_MARK
integer
Unused field, remains for compatibility
Yes
Yes
RESULT_VALUE
double
Unused field, remains for compatibility
Yes
Yes
RESULT_SUM
double
Unused field, remains for compatibility
Yes
Yes
RESULT_CURRENCY_ID
string
Unused field, remains for compatibility
Yes
Yes
AUTOCOMPLETE_RULE
integer
Autocomplete
Yes
Yes
BINDINGS
crm_activity_binding
Bindings
Yes
No
COMMUNICATIONS
crm_activity_communication
Communication channel. Multiple, required
Yes
Yes
FILES
diskfile
Added files. Multiple
Yes
Yes
WEBDAV_ELEMENTS
diskfile
Added files. Multiple. Deprecated, kept for compatibility
Yes
Yes
IS_INCOMING_CHANNEL
char
Is the activity incoming, that is, created as a result of an incoming client request in the communication channel
Yes
No
Copied
Was the article helpful?
Yes
No
Previous
Data Types and Structure of Objects in the CRM REST API
Next
Typical Use-Cases and Tutorials

---

## Typical use-cases and scenarios for REST API in CRM and tutorials

**Source:** https://apidocs.bitrix24.com/api-reference/crm/tutorials

Typical use-cases and scenarios for REST API in CRM and tutorials | Bitrix24 REST API and Marketplace Applications
How to create leads, deals, and other CRM objects
Typical use-cases and scenarios for REST API in CRM and tutorials
How to create leads, deals, and other CRM objects
How to replace an outdated phone number for an existing client; how to update product information and other examples
How to find clients by phone; how to get all activities of a client and other examples of working with lists of entities
How to use Bitrix24 tools for Sales Intelligence
How to add your tab to the deal card; how to add your buttons to the lead card and other examples of CRM widgets
How can you quickly link a form on your website to the CRM? How can you automatically create deals with product items? How can you pass information for Sales Intelligence to Bitrix when creating a lead from your source?
In this section, you will find ready-made examples for solving typical tasks related to CRM.
How to create leads, deals, and other CRM objects
How to create leads, deals, and other CRM objects
Add Lead via Web Form
Add a lead with files via a web form
Add an activity to a new lead or deal depending on the CRM mode
How to Send an Email to a Client on Behalf of an Employee
Add Repeat Lead
Add Contact via Web Form
Add a contact with details via a web form
Add a Company via Web Form
Add a Company with Details via Web Form
Add a deal and company with requisites
Add Calendar Event for Client Interaction
How to Add a Template and Create a Document Based on It
How to Create a Custom Field in a SPA
How to Set Up Rounding for a Custom Field of Type "Number"
How to replace an outdated phone number for an existing client; how to update product information and other examples
How to replace an outdated phone number for an existing client; how to update product information and other examples
How to Change or Delete Phone Numbers and Emails
How to Create Your Lead Editing Form
How to Create Your Contact Editing Form
How to Create Your Company Editing Form
How to Create Your Deal Edit Form
How to find clients by phone; how to get all activities of a client and other examples of working with lists of entities
How to find clients by phone; how to get all activities of a client and other examples of working with lists of entities
How to Find Duplicates in CRM by Phone and Email
How to Get a List of Activities from Deals
How to Get a List of Stages with Semantics for CRM Objects
How to Get the Sales Funnel of a Given Direction with the Semantics of Each Deal Stage
How to use Bitrix24 tools for Sales Intelligence
How to use Bitrix24 tools for Sales Intelligence
How to Transfer Information to Sales Intelligence
How to Use Sales Intelligence When Creating a Lead
How to Use Sales Intelligence When Creating a Deal and Contact
How to add your tab to the deal card; how to add your buttons to the lead card and other examples of CRM widgets
How to add your tab to the deal card; how to add your buttons to the lead card and other examples of CRM widgets
Embed a widget in a lead as a custom property
Embed Widget in CRM Card
Was the article helpful?
Yes
No
Previous
Fields of Main CRM Objects
Next
Determine the Current CRM Operating Mode

---

