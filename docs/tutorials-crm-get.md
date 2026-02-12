---
description: 'Tutorials: How to get/list CRM data (search, filters, stages)'
methods:
- crm.activity.list
- crm.address.list
- crm.category.list
- crm.company.list
- crm.contact.list
- crm.dealcategory.default.get
- crm.dealcategory.list
- crm.duplicate.findbycomm
- crm.enum.ownertype
- crm.item.fields
- crm.item.list
- crm.lead.list
- crm.requisite.list
- crm.status.list
- user.LAST_NAME
- user.NAME
- user.current
- user.get
pages: 8
title: 'Tutorials: How to get/list CRM data (search, filters, stages)'
---
# Tutorials: How to get/list CRM data (search, filters, stages)
> Tutorials: How to get/list CRM data (search, filters, stages)
> **8 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Retrieving Lists](#retrieving-lists)
- [How to Find Duplicates in CRM by Phone and Email](#how-to-find-duplicates-in-crm-by-phone-and-email)
- [How to Get a List of Activities from Deals](#how-to-get-a-list-of-activities-from-deals)
- [How to Get a List of Stages with Semantics for CRM Objects](#how-to-get-a-list-of-stages-with-semantics-for-crm)
- [How to Get the Sales Funnel of a Given Direction with the Semantics of Each Deal Stage](#how-to-get-the-sales-funnel-of-a-given-direction-w)
- [How to Get a Client's Address from CRM](#how-to-get-a-clients-address-from-crm)
- [How to Get a List of Vendors](#how-to-get-a-list-of-vendors)
- [How to Filter Items by Stage Name](#how-to-filter-items-by-stage-name)

---

## Retrieving Lists

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-get-lists/index

Retrieving Lists | Bitrix24 REST API and Marketplace Applications
Retrieving Lists
Retrieving Lists
How to Find Duplicates in CRM by Phone and Email
How to Get a List of Activities from Deals
How to Get a List of Stages with Semantics for CRM Objects
How to Get the Sales Funnel of a Given Direction with the Semantics of Each Deal Stage
How to Get a Client's Address from CRM
How to Get a List of Vendors
How to Filter Items by Stage Name
Was the article helpful?
Yes
No
Previous
How to Enter the Payment Date in the Deal Field
Next
How to Find Duplicates in CRM by Phone and Email

---

## How to Find Duplicates in CRM by Phone and Email

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-get-lists/search-by-phone-and-email

How to Find Duplicates in CRM by Phone and Email | Bitrix24 REST API and Marketplace Applications
How to Find Duplicates in CRM by Phone and Email
How to Find Duplicates in CRM by Phone and Email
Prepare the Data
1. Find Duplicate Objects
2. Retrieve Leads
3. Retrieve Contacts
4. Retrieve Companies
Display Results in a Table
Code Example
Scope:
crm
Who can execute the methods: users with read access to CRM entities
You can automate the search for duplicates by phone and email address using a script. It will find leads, contacts, and companies with matching data, retrieve information about them, and display it in a table:
object ID,
object type: lead, contact, or company,
title or first and last name,
phone,
email address.
To find duplicates, we will sequentially execute the following methods:
crm.duplicate.findbycomm
— find duplicates by phone and email,
crm.lead.list
— retrieve leads,
crm.contact.list
— retrieve contacts,
crm.company.list
— retrieve companies.
Prepare the Data
Prepare the Data
We will pass the phone number and email to the script using dialog boxes in the browser. The values will be stored in the variables
phone
and
email
.
If the data is entered correctly and duplicates are found, they will be displayed in the table. Otherwise, the table will be empty.
We will create arrays:
entityIDs
— IDs of found leads, contacts, companies,
$resultEntity
— detailed data about the found objects.
How to Use Examples in Documentation
JS
PHP
let
phone =
prompt
(
"Enter phone number:"
);
let
email =
prompt
(
"Enter email:"
);
let
entityIDs = {
'LEAD'
: [],
'CONTACT'
: [],
'COMPANY'
: []
};
let
resultEntity = {
'lead'
: [],
'contact'
: [],
'company'
: []
};
require_once
(
'crest.php'
);
$phone
=
readline
(
"Enter phone number: "
);
$email
=
readline
(
"Enter email: "
);
$entityIDs
= [
'LEAD'
=> [],
'CONTACT'
=> [],
'COMPANY'
=> []
];
$resultEntity
= [
'lead'
=> [],
'contact'
=> [],
'company'
=> []
];
1. Find Duplicate Objects
1. Find Duplicate Objects
To find duplicate objects by phone and email, we will call the method
crm.duplicate.findbycomm
twice. We will pass two parameters to it.
type
— type of communication,
PHONE
or
EMAIL
.
values
— array of phone numbers or email addresses. We will specify the variables
phone
and
email
.
The IDs of the found duplicates will be combined in the
entityIDs
array.
JS
PHP
if
(phone) {
BX24
.
callMethod
(
"crm.duplicate.findbycomm"
,
{
type
:
"PHONE"
,
values
: [phone]
},
function
(
phoneResult
) {
if
(phoneResult.
error
()) {
console
.
error
(
"Error finding duplicates by phone:"
, phoneResult.
error
());
}
else
{
if
(
Array
.
isArray
(phoneResult.
data
().
LEAD
)) {
entityIDs.
LEAD
= entityIDs.
LEAD
.
concat
(phoneResult.
data
().
LEAD
);
}
if
(
Array
.
isArray
(phoneResult.
data
().
CONTACT
)) {
entityIDs.
CONTACT
= entityIDs.
CONTACT
.
concat
(phoneResult.
data
().
CONTACT
);
}
if
(
Array
.
isArray
(phoneResult.
data
().
COMPANY
)) {
entityIDs.
COMPANY
= entityIDs.
COMPANY
.
concat
(phoneResult.
data
().
COMPANY
);
}
}
}
);
}
if
(email) {
BX24
.
callMethod
(
"crm.duplicate.findbycomm"
,
{
type
:
"EMAIL"
,
values
: [email]
},
function
(
emailResult
) {
if
(emailResult.
error
()) {
console
.
error
(
"Error finding duplicates by email:"
, emailResult.
error
());
}
else
{
if
(
Array
.
isArray
(emailResult.
data
().
LEAD
)) {
entityIDs.
LEAD
= entityIDs.
LEAD
.
concat
(emailResult.
data
().
LEAD
);
}
if
(
Array
.
isArray
(emailResult.
data
().
CONTACT
)) {
entityIDs.
CONTACT
= entityIDs.
CONTACT
.
concat
(emailResult.
data
().
CONTACT
);
}
if
(
Array
.
isArray
(emailResult.
data
().
COMPANY
)) {
entityIDs.
COMPANY
= entityIDs.
COMPANY
.
concat
(emailResult.
data
().
COMPANY
);
}
}
}
);
}
if
(
$phone
)
{
$result
=
CRest
::
call
(
'crm.duplicate.findbycomm'
, [
'type'
=>
'PHONE'
,
'values'
=> [
$phone
]
]);
if
(
is_array
(
$result
[
'result'
][
'LEAD'
]))
{
$entityIDs
[
'LEAD'
] =
array_merge
(
$entityIDs
[
'LEAD'
],
$result
[
'result'
][
'LEAD'
]);
}
if
(
is_array
(
$result
[
'result'
][
'CONTACT'
]))
{
$entityIDs
[
'CONTACT'
] =
array_merge
(
$entityIDs
[
'CONTACT'
],
$result
[
'result'
][
'CONTACT'
]);
}
if
(
is_array
(
$result
[
'result'
][
'COMPANY'
]))
{
$entityIDs
[
'COMPANY'
] =
array_merge
(
$entityIDs
[
'COMPANY'
],
$result
[
'result'
][
'COMPANY'
]);
}
}
if
(
$email
)
{
$result
=
CRest
::
call
(
'crm.duplicate.findbycomm'
, [
'type'
=>
'EMAIL'
,
'values'
=> [
$email
]
]);
if
(
is_array
(
$result
[
'result'
][
'LEAD'
]))
{
$entityIDs
[
'LEAD'
] =
array_merge
(
$entityIDs
[
'LEAD'
],
$result
[
'result'
][
'LEAD'
]);
}
if
(
is_array
(
$result
[
'result'
][
'CONTACT'
]))
{
$entityIDs
[
'CONTACT'
] =
array_merge
(
$entityIDs
[
'CONTACT'
],
$result
[
'result'
][
'CONTACT'
]);
}
if
(
is_array
(
$result
[
'result'
][
'COMPANY'
]))
{
$entityIDs
[
'COMPANY'
] =
array_merge
(
$entityIDs
[
'COMPANY'
],
$result
[
'result'
][
'COMPANY'
]);
}
}
The method
crm.duplicate.findbycomm
will return lists of IDs of leads, contacts, and companies where the specified phone or email address is found.
2. Retrieve Leads
2. Retrieve Leads
If the list of lead IDs is not empty, we will retrieve their data using the method
crm.lead.list
.
Apply a filter by ID.
Select fields:
ID
,
NAME
,
LAST_NAME
,
PHONE
,
EMAIL
,
TITLE
.
Save the result in the
resultEntity
array.
JS
PHP
if
(entityIDs.
LEAD
.
length
>
0
) {
BX24
.
callMethod
(
'crm.lead.list'
, {
'filter'
: {
'ID'
: entityIDs.
LEAD
},
'select'
: [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'PHONE'
,
'EMAIL'
,
'TITLE'
]
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
if
(result.
data
().
length
>
0
) {
resultEntity.
lead
= result.
data
();
}
}
});
}
if
(!
empty
(
$entityIDs
[
'LEAD'
]))
{
$result
=
CRest
::
call
(
'crm.lead.list'
,
[
'filter'
=> [
'ID'
=>
$entityIDs
[
'LEAD'
]
],
'select'
=>     [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'PHONE'
,
'EMAIL'
,
'TITLE'
]
]
);
if
(!
empty
(
$result
[
'result'
]))
{
$resultEntity
[
'lead'
] =
$result
[
'result'
];
}
}
The method
crm.lead.list
will return a list of leads based on the filter.
{
"result"
:
[
{
"ID"
:
"1183"
,
"NAME"
:
null
,
"LAST_NAME"
:
null
,
"TITLE"
:
"Filling out the CRM form \"Contact Information Form for Open Channels\""
,
"PHONE"
:
[
{
"ID"
:
"1957"
,
"VALUE_TYPE"
:
"OTHER"
,
"VALUE"
:
"+13216464646"
,
"TYPE_ID"
:
"PHONE"
}
]
}
]
}
3. Retrieve Contacts
3. Retrieve Contacts
If the list of contact IDs is not empty, we will retrieve their data using the method
crm.contact.list
.
Apply a filter by ID.
Select fields:
ID
,
NAME
,
LAST_NAME
,
PHONE
,
EMAIL
.
Save the result in the
resultEntity
array.
JS
PHP
if
(entityIDs.
CONTACT
.
length
>
0
) {
BX24
.
callMethod
(
'crm.contact.list'
, {
'filter'
: {
'ID'
: entityIDs.
CONTACT
},
'select'
: [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'PHONE'
,
'EMAIL'
]
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
if
(result.
data
().
length
>
0
) {
resultEntity.
contact
= result.
data
();
}
}
});
}
if
(!
empty
(
$entityIDs
[
'CONTACT'
]))
{
$result
=
CRest
::
call
(
'crm.contact.list'
,
[
'filter'
=> [
'ID'
=>
$entityIDs
[
'CONTACT'
]
],
'select'
=>     [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'PHONE'
,
'EMAIL'
]
]
);
if
(!
empty
(
$result
[
'result'
]))
{
$resultEntity
[
'contact'
] =
$result
[
'result'
];
}
}
The method
crm.contact.list
will return a list of contacts based on the filter.
{
"result"
:
[
{
"ID"
:
"23"
,
"NAME"
:
"Alexander"
,
"LAST_NAME"
:
"Alekseev"
,
"EMAIL"
:
[
{
"ID"
:
"854"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"alekseev@example.com"
,
"TYPE_ID"
:
"EMAIL"
}
]
}
]
}
4. Retrieve Companies
4. Retrieve Companies
If the list of company IDs is not empty, we will retrieve their data using the method
crm.company.list
.
Apply a filter by ID.
Select fields:
ID
,
PHONE
,
EMAIL
,
TITLE
.
Save the result in the
resultEntity
array.
JS
PHP
if
(entityIDs.
COMPANY
.
length
>
0
) {
BX24
.
callMethod
(
'crm.company.list'
, {
'filter'
: {
'ID'
: entityIDs.
COMPANY
},
'select'
: [
'ID'
,
'PHONE'
,
'EMAIL'
,
'TITLE'
]
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
if
(result.
data
().
length
>
0
) {
resultEntity.
company
= result.
data
();
}
}
});
}
if
(!
empty
(
$entityIDs
[
'COMPANY'
]))
{
$result
=
CRest
::
call
(
'crm.company.list'
,
[
'filter'
=> [
'ID'
=>
$entityIDs
[
'COMPANY'
]
],
'select'
=>     [
'ID'
,
'PHONE'
,
'EMAIL'
,
'TITLE'
]
]
);
if
(!
empty
(
$result
[
'result'
]))
{
$resultEntity
[
'company'
] =
$result
[
'result'
];
}
}
The method
crm.company.list
will return a list of companies based on the filter.
{
"result":[{
"ID":"587",
"TITLE":"Daisy",
"PHONE":[{
"ID":"1899",
"VALUE_TYPE":"WORK",
"VALUE":"5345654",
"TYPE_ID":"PHONE"
}],
"EMAIL":[{
"ID":"1901",
"VALUE_TYPE":"WORK",
"VALUE":"company@example.com",
"TYPE_ID":"EMAIL"}]
}]
}
Display Results in a Table
Display Results in a Table
We will display the found records in the columns
Identifier
,
Object Type
,
Title/First and Last Name
,
Phone
,
Email
.
JS
PHP
let
table = [];
table.
push
([
"Identifier"
,
"Object Type"
,
"Title/First and Last Name"
,
"Phone"
,
"Email"
]);
for
(
let
entity
in
resultEntity) {
resultEntity[entity].
forEach
(
function
(
item
) {
let
phones =
''
;
if
(item.
PHONE
) {
phones = item.
PHONE
.
map
(
phone
=>
phone.
VALUE
).
join
(
', '
);
}
let
emails =
''
;
if
(item.
EMAIL
) {
emails = item.
EMAIL
.
map
(
email
=>
email.
VALUE
).
join
(
', '
);
}
let
title = item.
TITLE
? item.
TITLE
+ (item.
NAME
|| item.
LAST_NAME
?
': '
:
''
) :
''
;
if
(item.
NAME
|| item.
LAST_NAME
) {
title += [item.
NAME
, item.
LAST_NAME
].
join
(
' '
);
}
table.
push
([
item.
ID
,
entity,
title,
phones ||
'—'
,
emails ||
'—'
]);
});
}
console
.
table
(table);
$table
= [];
$table
[] = [
"Identifier"
,
"Object Type"
,
"Title/First and Last Name"
,
"Phone"
,
"Email"
];
foreach
(
$resultEntity
as
$entityType
=>
$entities
) {
foreach
(
$entities
as
$item
) {
$phones
=
''
;
if
(!
empty
(
$item
[
'PHONE'
])) {
$phones
=
implode
(
', '
,
array_column
(
$item
[
'PHONE'
],
'VALUE'
));
}
$emails
=
''
;
if
(!
empty
(
$item
[
'EMAIL'
])) {
$emails
=
implode
(
', '
,
array_column
(
$item
[
'EMAIL'
],
'VALUE'
));
}
$title
= !
empty
(
$item
[
'TITLE'
]) ?
$item
[
'TITLE'
] :
''
;
if
(!
empty
(
$item
[
'NAME'
]) || !
empty
(
$item
[
'LAST_NAME'
])) {
$namePart
=
trim
(
$item
[
'NAME'
] .
' '
.
$item
[
'LAST_NAME'
]);
if
(
$title
) {
$title
.=
': '
.
$namePart
;
}
else
{
$title
=
$namePart
;
}
}
$table
[] = [
$item
[
'ID'
],
$entityType
,
$title
?:
'—'
,
$phones
?:
'—'
,
$emails
?:
'—'
];
}
}
foreach
(
$table
as
$row
) {
echo
implode
(
"\t"
,
$row
) .
"\n"
;
}
Code Example
Code Example
JS
PHP
// Requesting phone and email from the user
let
phone =
prompt
(
"Enter phone number:"
);
let
email =
prompt
(
"Enter email:"
);
// Initializing variables
let
entityIDs = {
'LEAD'
: [],
'CONTACT'
: [],
'COMPANY'
: []
};
let
resultEntity = {
'lead'
: [],
'contact'
: [],
'company'
: []
};
// Searching for duplicates by phone
if
(phone) {
BX24
.
callMethod
(
"crm.duplicate.findbycomm"
,
{
type
:
"PHONE"
,
values
: [phone]
},
function
(
phoneResult
) {
if
(phoneResult.
error
()) {
console
.
error
(
"Error finding duplicates by phone:"
, phoneResult.
error
());
}
else
{
if
(
Array
.
isArray
(phoneResult.
data
().
LEAD
)) {
entityIDs.
LEAD
= entityIDs.
LEAD
.
concat
(phoneResult.
data
().
LEAD
);
}
if
(
Array
.
isArray
(phoneResult.
data
().
CONTACT
)) {
entityIDs.
CONTACT
= entityIDs.
CONTACT
.
concat
(phoneResult.
data
().
CONTACT
);
}
if
(
Array
.
isArray
(phoneResult.
data
().
COMPANY
)) {
entityIDs.
COMPANY
= entityIDs.
COMPANY
.
concat
(phoneResult.
data
().
COMPANY
);
}
}
}
);
}
// Searching for duplicates by email
if
(email) {
BX24
.
callMethod
(
"crm.duplicate.findbycomm"
,
{
type
:
"EMAIL"
,
values
: [email]
},
function
(
emailResult
) {
if
(emailResult.
error
()) {
console
.
error
(
"Error finding duplicates by email:"
, emailResult.
error
());
}
else
{
if
(
Array
.
isArray
(emailResult.
data
().
LEAD
)) {
entityIDs.
LEAD
= entityIDs.
LEAD
.
concat
(emailResult.
data
().
LEAD
);
}
if
(
Array
.
isArray
(emailResult.
data
().
CONTACT
)) {
entityIDs.
CONTACT
= entityIDs.
CONTACT
.
concat
(emailResult.
data
().
CONTACT
);
}
if
(
Array
.
isArray
(emailResult.
data
().
COMPANY
)) {
entityIDs.
COMPANY
= entityIDs.
COMPANY
.
concat
(emailResult.
data
().
COMPANY
);
}
}
}
);
}
setTimeout
(
function
(
) {
// Processing leads
if
(entityIDs.
LEAD
.
length
>
0
) {
BX24
.
callMethod
(
'crm.lead.list'
, {
'filter'
: {
'ID'
: entityIDs.
LEAD
},
'select'
: [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'PHONE'
,
'EMAIL'
,
'TITLE'
]
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
if
(result.
data
().
length
>
0
) {
resultEntity.
lead
= result.
data
();
}
}
});
}
// Processing contacts
if
(entityIDs.
CONTACT
.
length
>
0
) {
BX24
.
callMethod
(
'crm.contact.list'
, {
'filter'
: {
'ID'
: entityIDs.
CONTACT
},
'select'
: [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'PHONE'
,
'EMAIL'
]
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
if
(result.
data
().
length
>
0
) {
resultEntity.
contact
= result.
data
();
}
}
});
}
// Processing companies
if
(entityIDs.
COMPANY
.
length
>
0
) {
BX24
.
callMethod
(
'crm.company.list'
, {
'filter'
: {
'ID'
: entityIDs.
COMPANY
},
'select'
: [
'ID'
,
'PHONE'
,
'EMAIL'
,
'TITLE'
]
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
if
(result.
data
().
length
>
0
) {
resultEntity.
company
= result.
data
();
}
}
});
}
setTimeout
(
function
(
) {
let
table = [];
// Table header
table.
push
([
"Identifier"
,
"Object Type"
,
"Title/First and Last Name"
,
"Phone"
,
"Email"
]);
// Data rows
for
(
let
entity
in
resultEntity) {
resultEntity[entity].
forEach
(
function
(
item
) {
let
phones =
''
;
if
(item.
PHONE
) {
phones = item.
PHONE
.
map
(
phone
=>
phone.
VALUE
).
join
(
', '
);
}
let
emails =
''
;
if
(item.
EMAIL
) {
emails = item.
EMAIL
.
map
(
email
=>
email.
VALUE
).
join
(
', '
);
}
let
title = item.
TITLE
? item.
TITLE
+ (item.
NAME
|| item.
LAST_NAME
?
': '
:
''
) :
''
;
if
(item.
NAME
|| item.
LAST_NAME
) {
title += [item.
NAME
, item.
LAST_NAME
].
join
(
' '
);
}
table.
push
([
item.
ID
,
entity,
title,
phones ||
'—'
,
emails ||
'—'
]);
});
}
// Output the table to the console
console
.
table
(table);
},
1000
);
// Delay for all requests to complete
},
1000
);
<?php
require_once
(
'crest.php'
);
// Requesting phone and email from the user
$phone
=
readline
(
"Enter phone number: "
);
$email
=
readline
(
"Enter email: "
);
// Initializing variables
$entityIDs
= [
'LEAD'
=> [],
'CONTACT'
=> [],
'COMPANY'
=> []
];
$resultEntity
= [
'lead'
=> [],
'contact'
=> [],
'company'
=> []
];
// Searching for duplicates by phone
if
(
$phone
)
{
$result
=
CRest
::
call
(
'crm.duplicate.findbycomm'
, [
'type'
=>
'PHONE'
,
'values'
=> [
$phone
]
]);
if
(
is_array
(
$result
[
'result'
][
'LEAD'
]))
{
$entityIDs
[
'LEAD'
] =
array_merge
(
$entityIDs
[
'LEAD'
],
$result
[
'result'
][
'LEAD'
]);
}
if
(
is_array
(
$result
[
'result'
][
'CONTACT'
]))
{
$entityIDs
[
'CONTACT'
] =
array_merge
(
$entityIDs
[
'CONTACT'
],
$result
[
'result'
][
'CONTACT'
]);
}
if
(
is_array
(
$result
[
'result'
][
'COMPANY'
]))
{
$entityIDs
[
'COMPANY'
] =
array_merge
(
$entityIDs
[
'COMPANY'
],
$result
[
'result'
][
'COMPANY'
]);
}
}
// Searching for duplicates by email
if
(
$email
)
{
$result
=
CRest
::
call
(
'crm.duplicate.findbycomm'
, [
'type'
=>
'EMAIL'
,
'values'
=> [
$email
]
]);
if
(
is_array
(
$result
[
'result'
][
'LEAD'
]))
{
$entityIDs
[
'LEAD'
] =
array_merge
(
$entityIDs
[
'LEAD'
],
$result
[
'result'
][
'LEAD'
]);
}
if
(
is_array
(
$result
[
'result'
][
'CONTACT'
]))
{
$entityIDs
[
'CONTACT'
] =
array_merge
(
$entityIDs
[
'CONTACT'
],
$result
[
'result'
][
'CONTACT'
]);
}
if
(
is_array
(
$result
[
'result'
][
'COMPANY'
]))
{
$entityIDs
[
'COMPANY'
] =
array_merge
(
$entityIDs
[
'COMPANY'
],
$result
[
'result'
][
'COMPANY'
]);
}
}
// Processing leads
if
(!
empty
(
$entityIDs
[
'LEAD'
]))
{
$result
=
CRest
::
call
(
'crm.lead.list'
,
[
'filter'
=> [
'ID'
=>
$entityIDs
[
'LEAD'
]
],
'select'
=>     [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'PHONE'
,
'EMAIL'
,
'TITLE'
]
]
);
if
(!
empty
(
$result
[
'result'
]))
{
$resultEntity
[
'lead'
] =
$result
[
'result'
];
}
}
// Processing contacts
if
(!
empty
(
$entityIDs
[
'CONTACT'
]))
{
$result
=
CRest
::
call
(
'crm.contact.list'
,
[
'filter'
=> [
'ID'
=>
$entityIDs
[
'CONTACT'
]
],
'select'
=>     [
'ID'
,
'NAME'
,
'LAST_NAME'
,
'PHONE'
,
'EMAIL'
]
]
);
if
(!
empty
(
$result
[
'result'
]))
{
$resultEntity
[
'contact'
] =
$result
[
'result'
];
}
}
// Processing companies
if
(!
empty
(
$entityIDs
[
'COMPANY'
]))
{
$result
=
CRest
::
call
(
'crm.company.list'
,
[
'filter'
=> [
'ID'
=>
$entityIDs
[
'COMPANY'
]
],
'select'
=>     [
'ID'
,
'PHONE'
,
'EMAIL'
,
'TITLE'
]
]
);
if
(!
empty
(
$result
[
'result'
]))
{
$resultEntity
[
'company'
] =
$result
[
'result'
];
}
}
// Forming the table
$table
= [];
// Table header
$table
[] = [
"Identifier"
,
"Object Type"
,
"Title/First and Last Name"
,
"Phone"
,
"Email"
];
// Data rows
foreach
(
$resultEntity
as
$entityType
=>
$entities
) {
foreach
(
$entities
as
$item
) {
$phones
=
''
;
if
(!
empty
(
$item
[
'PHONE'
])) {
$phones
=
implode
(
', '
,
array_column
(
$item
[
'PHONE'
],
'VALUE'
));
}
$emails
=
''
;
if
(!
empty
(
$item
[
'EMAIL'
])) {
$emails
=
implode
(
', '
,
array_column
(
$item
[
'EMAIL'
],
'VALUE'
));
}
$title
= !
empty
(
$item
[
'TITLE'
]) ?
$item
[
'TITLE'
] :
''
;
if
(!
empty
(
$item
[
'NAME'
]) || !
empty
(
$item
[
'LAST_NAME'
])) {
$namePart
=
trim
(
$item
[
'NAME'
] .
' '
.
$item
[
'LAST_NAME'
]);
if
(
$title
) {
$title
.=
': '
.
$namePart
;
}
else
{
$title
=
$namePart
;
}
}
$table
[] = [
$item
[
'ID'
],
$entityType
,
$title
?:
'—'
,
$phones
?:
'—'
,
$emails
?:
'—'
];
}
}
// Output the table to the console with tabulation
foreach
(
$table
as
$row
) {
echo
implode
(
"\t"
,
$row
) .
"\n"
;
}
?>
Copied
Was the article helpful?
Yes
No
Previous
How to Get Lists
Next
How to Get a List of Activities from Deals

---

## How to Get a List of Activities from Deals

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-get-lists/get-activity-list-by-deals

How to Get a List of Activities from Deals | Bitrix24 REST API and Marketplace Applications
How to Get a List of Activities from Deals
How to Get a List of Activities from Deals
1. Get the ID of the Current User
2. Get the List of Deal IDs for the Employee
3. Get the List of Activities for the Found Deals
4. Get User Data by RESPONSIBLE_ID
Code Example
Scope:
crm, user_brief
Who can execute the method: a user with read access to deals in CRM
The list of activities allows tracking current tasks and calls related to deals, deadlines for activities, and responsible individuals. To create a table of activities, we will sequentially execute the following methods:
user.current
— find the
ID
of the current user,
crm.item.list
— retrieve the
ID
of all deals for which the employee is responsible,
crm.activity.list
— generate a list of activities for the deals,
user.get
— obtain information about the individuals responsible for the activities.
1. Get the ID of the Current User
1. Get the ID of the Current User
To obtain the identifier of the current user, we use the method
user.current
.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'user.current'
,
{}
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
'user.current'
,
[]
);
As a result, we will receive the user identifier
"ID": "29"
.
{
"result"
:
{
"ID"
:
"29"
,
"ACTIVE"
:
true
,
"NAME"
:
"John"
,
"LAST_NAME"
:
"Doe"
,
...
}
}
2. Get the List of Deal IDs for the Employee
2. Get the List of Deal IDs for the Employee
To retrieve the identifiers of the deals assigned to the employee, we will call the method
crm.item.list
. We will pass the following parameters:
entityTypeId
— the identifier of the CRM object type. You can obtain the identifiers using the method
crm.enum.ownertype
. We will specify the value —
2
, which corresponds to a deal.
select
— an array of fields to select. We will specify
select: ['id','title']
to get the identifiers and titles of the deals.
filter
— selection filter. To select deals by the
ID
of the responsible employee, we will specify the user identifier obtained in the previous request
assignedById: 29
.
To make the request faster and return only relevant data, add a filter by stages
stageId
. For example, you can select deals at the
In Progress
stage.
How to Filter Items by Stage Name
JS
PHP
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
],
filter
: {
assignedById
:
29
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
],
'filter'
=> [
'assignedById'
=>
29
]
]
);
As a result, we will receive an array
items
with deal identifiers like
"id": 5111
.
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
5111
,
"title"
:
"Deal #1"
}
,
{
"id"
:
5199
,
"title"
:
"Deal #2"
}
,
{
"id"
:
5257
,
"title"
:
"Deal #3"
}
]
}
,
"total"
:
3
}
3. Get the List of Activities for the Found Deals
3. Get the List of Activities for the Found Deals
To obtain the list of activities, we will use the method
crm.activity.list
.
To select activities from multiple deals, we will use the binding key to CRM elements
BINDINGS
in the
filter
. We will pass an array of objects. Each object contains:
OWNER_TYPE_ID
— the identifier of the CRM object type. You can obtain the identifiers using the method
crm.enum.ownertype
. We will specify the value —
2
, which corresponds to a deal.
OWNER_ID
— the identifier of the deal from the result of the previous request.
We will also filter only active activities
COMPLETED: 'N'
.
We will output the following fields in the
select
:
ID
— the identifier of the activity,
OWNER_ID
— the identifier of the deal,
SUBJECT
— the description of the activity,
DEADLINE
— the date and time of the deadline,
RESPONSIBLE_ID
— the identifier of the user responsible for the activity.
JS
PHP
BX24
.
callMethod
(
'crm.activity.list'
,
{
filter
: {
BINDINGS
: [
{
OWNER_TYPE_ID
:
2
,
OWNER_ID
:
5111
},
{
OWNER_TYPE_ID
:
2
,
OWNER_ID
:
5199
},
{
OWNER_TYPE_ID
:
2
,
OWNER_ID
:
5257
}
],
COMPLETED
:
'N'
},
select
: [
'ID'
,
'OWNER_ID'
,
'SUBJECT'
,
'DEADLINE'
,
'RESPONSIBLE_ID'
]
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
'crm.activity.list'
,
[
'filter'
=> [
'BINDINGS'
=> [
[
'OWNER_TYPE_ID'
=>
2
,
'OWNER_ID'
=>
5111
],
[
'OWNER_TYPE_ID'
=>
2
,
'OWNER_ID'
=>
5199
],
[
'OWNER_TYPE_ID'
=>
2
,
'OWNER_ID'
=>
5257
]
],
'COMPLETED'
=>
'N'
],
'select'
=> [
'ID'
,
'OWNER_ID'
,
'SUBJECT'
,
'DEADLINE'
,
'RESPONSIBLE_ID'
]
]
);
As a result, we will receive a list of activities with descriptions for each activity.
{
"result"
:
[
{
"ID"
:
"10120"
,
"OWNER_ID"
:
"5111"
,
"SUBJECT"
:
"Call the client"
,
"DEADLINE"
:
"2025-08-21T16:00:00+02:00"
,
"RESPONSIBLE_ID"
:
"29"
}
,
{
"ID"
:
"10131"
,
"OWNER_ID"
:
"5199"
,
"SUBJECT"
:
"Check the contract"
,
"DEADLINE"
:
"2025-08-29T16:00:00+02:00"
,
"RESPONSIBLE_ID"
:
"47"
}
,
...
]
,
"total"
:
5
}
4. Get User Data by RESPONSIBLE_ID
4. Get User Data by RESPONSIBLE_ID
The individual responsible for the activity in the deal can be any user, not just the one responsible for the deal. To display the name and surname of the individual responsible for the activity in the table, we will use the method
user.get
.
In the
filter
, we will pass the identifiers of the responsible individuals
ID: [29, 47, ...]
.
JS
PHP
BX24
.
callMethod
(
'user.get'
,
{
filter
: {
ID
: [
29
,
47
, ...]
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
'user.get'
,
[
'filter'
=> [
'ID'
=> [
29
,
47
, ...]
]
]
);
As a result, we will receive information about the users.
{
"result"
:
[
{
"ID"
:
"29"
,
"XML_ID"
:
"23699770"
,
"ACTIVE"
:
true
,
"NAME"
:
"John"
,
"LAST_NAME"
:
"Doe"
}
,
{
"ID"
:
"47"
,
"XML_ID"
:
"63726962"
,
"ACTIVE"
:
true
,
"NAME"
:
"Peter"
,
"LAST_NAME"
:
"Smith"
}
,
...
]
,
"total"
:
3
,
}
Code Example
Code Example
JS
PHP
// Function to build an array of bindings to deals
// CRM object type OWNER_TYPE_ID — 2, which means deal
function
buildBindingsFromDealIds
(
dealIds
) {
return
dealIds.
map
(
(
id
) =>
({
OWNER_TYPE_ID
:
2
,
OWNER_ID
: id }));
}
// Function to fetch all items using pagination
// Needed for list methods, as one request can get a maximum of 50 records
function
fetchAllItems
(
method, params, callback
) {
let
allResults = [];
function
processResult
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
`Error fetching data from
${method}
:`
, result.
error
().
ex
);
callback
(result.
error
(),
null
);
return
;
}
const
data = result.
data
();
// Process results based on the method
if
(method ===
'crm.item.list'
) {
allResults = allResults.
concat
(data.
items
|| []);
}
else
if
(method ===
'crm.activity.list'
) {
allResults = allResults.
concat
(data || []);
}
else
{
if
(
Array
.
isArray
(data)) {
allResults = allResults.
concat
(data);
}
else
if
(data &&
Array
.
isArray
(data.
result
)) {
allResults = allResults.
concat
(data.
result
);
}
}
// Check if there are more data
if
(result.
more
&& result.
more
()) {
// Use result.next() to get the next page
result.
next
(processResult);
}
else
{
// If there are no more pages, finish
callback
(
null
, allResults);
}
}
// First request
BX24
.
callMethod
(method, params, processResult);
}
// Step 1: Get information about the current user
BX24
.
callMethod
(
'user.current'
, {},
function
(
userResult
) {
if
(userResult.
error
()) {
console
.
error
(
'Error fetching user:'
, userResult.
error
().
ex
);
return
;
}
const
current = userResult.
data
();
const
userId =
Number
(current.
ID
);
console
.
log
(
'Current user ID:'
, userId);
// Step 2: Get the list of all deals
fetchAllItems
(
'crm.item.list'
, {
entityTypeId
:
2
,
select
: [
'id'
,
'title'
],
filter
: {
assignedById
: userId }
},
function
(
error, allItems
) {
if
(error) {
console
.
error
(
'Error fetching all deals:'
, error.
ex
);
return
;
}
const
dealIds = allItems.
map
(
it
=>
it.
id
);
const
dealMap = allItems.
reduce
(
(
map, deal
) =>
{
map[deal.
id
] = deal.
title
;
return
map;
}, {});
console
.
log
(
'Deals:'
, dealMap);
if
(dealIds.
length
===
0
) {
alert
(
'The employee has no deals'
);
return
;
}
// Build bindings to search for activities by deals
const
bindings =
buildBindingsFromDealIds
(dealIds);
// Step 3: Get all activities linked to these deals
fetchAllItems
(
'crm.activity.list'
, {
filter
: {
BINDINGS
: bindings,
COMPLETED
:
'N'
},
select
: [
'ID'
,
'OWNER_ID'
,
'SUBJECT'
,
'DEADLINE'
,
'RESPONSIBLE_ID'
]
},
function
(
error, allActivities
) {
if
(error) {
console
.
error
(
'Error fetching all activities:'
, error.
ex
);
return
;
}
const
userIds = [...
new
Set
(allActivities.
map
(
a
=>
a.
RESPONSIBLE_ID
))];
if
(userIds.
length
===
0
) {
console
.
log
(
'No incomplete activities for the deals.'
);
console
.
table
([]);
return
;
}
// Step 4: Get user data
BX24
.
callMethod
(
'user.get'
, {
filter
: {
ID
: userIds }
},
function
(
userResult
) {
if
(userResult.
error
()) {
console
.
error
(
'Error fetching users:'
, userResult.
error
().
ex
);
const
tableFallback = allActivities.
map
(
a
=>
({
activityId
: a.
ID
,
dealTitle
: dealMap[a.
OWNER_ID
] ||
`Deal #
${a.OWNER_ID}
`
,
subject
: a.
SUBJECT
,
deadline
: a.
DEADLINE
,
responsibleId
: a.
RESPONSIBLE_ID
,
responsibleName
:
`User
${a.RESPONSIBLE_ID}
(not found)`
}));
console
.
table
(tableFallback);
return
;
}
const
users = userResult.
data
();
const
userMap = users.
reduce
(
(
map, user
) =>
{
map[user.
ID
] =
`
${user.NAME ||
''
}
${user.LAST_NAME ||
''
}
`
.
trim
() || user.
LOGIN
;
return
map;
}, {});
const
table = allActivities.
map
(
a
=>
({
activityId
: a.
ID
,
dealTitle
: dealMap[a.
OWNER_ID
] ||
`Deal #
${a.OWNER_ID}
`
,
subject
: a.
SUBJECT
,
deadline
: a.
DEADLINE
,
responsibleId
: a.
RESPONSIBLE_ID
,
responsibleName
: userMap[a.
RESPONSIBLE_ID
] ||
`User
${a.RESPONSIBLE_ID}
`
}));
console
.
table
(table);
});
});
});
});
<?php
require_once
(
'crest.php'
);
// Function to build an array of bindings to deals
// OWNER_TYPE_ID: 2 — CRM object type — deal
function
buildBindingsFromDealIds
(
$dealIds
)
{
$bindings
= [];
foreach
(
$dealIds
as
$id
) {
$bindings
[] = [
'OWNER_TYPE_ID'
=>
2
,
'OWNER_ID'
=> (
int
)
$id
,
];
}
return
$bindings
;
}
// Function to fetch all items using pagination
// Needed for list methods, as one request can get a maximum of 50 records
function
fetchAllItems
(
$method
,
$params
)
{
$allResults
= [];
$start
=
0
;
$batchSize
=
50
;
do
{
$params
[
'start'
] =
$start
;
$result
=
CRest
::
call
(
$method
,
$params
);
if
(!
empty
(
$result
[
'error'
])) {
return
[
'error'
=>
$result
[
'error'
],
'error_description'
=>
$result
[
'error_description'
]];
}
$data
=
$result
[
'result'
] ?? [];
// Process results based on the method
if
(
$method
===
'crm.item.list'
) {
if
(!
empty
(
$data
[
'items'
]) &&
is_array
(
$data
[
'items'
])) {
$allResults
=
array_merge
(
$allResults
,
$data
[
'items'
]);
}
}
elseif
(
$method
===
'crm.activity.list'
) {
if
(
is_array
(
$data
)) {
$allResults
=
array_merge
(
$allResults
,
$data
);
}
}
else
{
if
(
is_array
(
$data
)) {
$allResults
=
array_merge
(
$allResults
,
$data
);
}
}
// Check if there are more data
if
(
count
(
$data
) >=
$batchSize
) {
$start
+=
$batchSize
;
}
else
{
break
;
}
}
while
(
true
);
return
[
'result'
=>
$allResults
];
}
// Step 1: Get information about the current user
$userResult
=
CRest
::
call
(
'user.current'
, []);
if
(!
empty
(
$userResult
[
'error'
])) {
echo
'Error fetching user: '
.
$userResult
[
'error_description'
] .
"\n"
;
exit
;
}
$current
=
$userResult
[
'result'
] ??
null
;
if
(!
$current
||
empty
(
$current
[
'ID'
])) {
echo
"Failed to get the current user\n"
;
exit
;
}
$userId
= (
int
)
$current
[
'ID'
];
echo
"Current user ID:
$userId
\n"
;
// Step 2: Get the list of all deals
$itemsResult
=
fetchAllItems
(
'crm.item.list'
, [
'entityTypeId'
=>
2
,
'select'
=> [
'id'
,
'title'
],
'filter'
=> [
'assignedById'
=>
$userId
]
]);
if
(
isset
(
$itemsResult
[
'error'
])) {
echo
'Error fetching all deals: '
.
$itemsResult
[
'error_description'
] .
"\n"
;
exit
;
}
$allItems
=
$itemsResult
[
'result'
];
$dealMap
= [];
$dealIds
= [];
foreach
(
$allItems
as
$item
) {
$id
= (
int
)
$item
[
'id'
];
$dealIds
[] =
$id
;
$dealMap
[
$id
] =
$item
[
'title'
];
}
echo
"Deals found: "
.
count
(
$dealIds
) .
"\n"
;
if
(
empty
(
$dealIds
)) {
echo
"The employee has no deals\n"
;
exit
;
}
// Build bindings to search for activities by deals
$bindings
=
buildBindingsFromDealIds
(
$dealIds
);
// Step 3: Get all activities linked to these deals
$activitiesResult
=
fetchAllItems
(
'crm.activity.list'
, [
'filter'
=> [
'BINDINGS'
=>
$bindings
,
'COMPLETED'
=>
'N'
,
],
'select'
=> [
'ID'
,
'OWNER_ID'
,
'SUBJECT'
,
'DEADLINE'
,
'RESPONSIBLE_ID'
]
]);
if
(
isset
(
$activitiesResult
[
'error'
])) {
echo
'Error fetching all activities: '
.
$activitiesResult
[
'error_description'
] .
"\n"
;
exit
;
}
$allActivities
=
$activitiesResult
[
'result'
];
if
(
empty
(
$allActivities
)) {
echo
"No incomplete activities for the deals.\n"
;
echo
implode
(
"\t"
, [
'Activity ID'
,
'Deal'
,
'Subject'
,
'Deadline'
,
'Responsible'
]) .
"\n"
;
exit
;
}
// Collect unique IDs of responsible individuals
$responsibleIds
=
array_unique
(
array_column
(
$allActivities
,
'RESPONSIBLE_ID'
));
$userMap
= [];
if
(!
empty
(
$responsibleIds
)) {
// Step 4: Get user data
$usersResult
=
fetchAllItems
(
'user.get'
, [
'filter'
=> [
'ID'
=>
array_values
(
$responsibleIds
)]
]);
if
(
isset
(
$usersResult
[
'error'
])) {
echo
'Error fetching users: '
.
$usersResult
[
'error_description'
] .
"\n"
;
$userMap
= [];
}
else
{
foreach
(
$usersResult
[
'result'
]
as
$user
) {
$fullName
=
trim
((
$user
[
'NAME'
] ??
''
) .
' '
. (
$user
[
'LAST_NAME'
] ??
''
));
$userMap
[
$user
[
'ID'
]] =
$fullName
?: (
$user
[
'LOGIN'
] ??
"User
{$user['ID']}
"
);
}
}
}
// Build and output the table
$header
= [
'Activity ID'
,
'Deal'
,
'Subject'
,
'Deadline'
,
'Responsible'
];
echo
implode
(
"\t"
,
$header
) .
"\n"
;
foreach
(
$allActivities
as
$a
) {
$activityId
=
$a
[
'ID'
] ??
''
;
$ownerId
= (
int
)(
$a
[
'OWNER_ID'
] ??
0
);
$dealTitle
=
$dealMap
[
$ownerId
] ??
"Deal #
{$ownerId}
"
;
$subject
=
$a
[
'SUBJECT'
] ??
''
;
$deadline
=
$a
[
'DEADLINE'
] ??
''
;
$responsibleId
=
$a
[
'RESPONSIBLE_ID'
] ??
''
;
$responsibleName
=
$userMap
[
$responsibleId
] ??
"User
{$responsibleId}
(not found)"
;
echo
implode
(
"\t"
, [
$activityId
,
$dealTitle
,
$subject
,
$deadline
,
$responsibleName
]) .
"\n"
;
}
Copied
Was the article helpful?
Yes
No
Previous
How to Find Duplicates in CRM by Phone and Email
Next
How to Get a List of Stages with Semantics for CRM Entities

---

## How to Get a List of Stages with Semantics for CRM Objects

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-get-lists/how-to-get-stages-with-semantics

How to Get a List of Stages with Semantics for CRM Objects | Bitrix24 REST API and Marketplace Applications
How to Get a List of Stages with Semantics for CRM Objects
How to Get a List of Stages with Semantics for CRM Objects
Get a List of Stages with Semantics
Code Example
Scope:
crm, user_brief
Who can execute the method: any user with access to CRM
The semantics of a stage reflects the current state of a CRM entity: in progress, successfully completed, or unsuccessful. The system uses the semantics value in automation and reporting.
To create a table of stages for a CRM object with semantics, we use the method
crm.status.list
.
Get a List of Stages with Semantics
Get a List of Stages with Semantics
The method
crm.status.list
returns a description of stages by the
ENTITY_ID
stage code for the CRM object.
Deals
—
DEAL_STAGE
for the main direction of deals and
DEAL_STAGE_xx
for additional ones, where xx is the direction identifier.
Leads
—
STATUS
.
Invoices
—
SMART_INVOICE_STAGE_xx
, where
xx
is the invoice direction identifier value.
Estimates
—
QUOTE_STATUS
.
Documents
—
SMART_DOCUMENT_STAGE_xx
, where
xx
is the
ID
of the document direction.
SPAs
—
DYNAMIC_xx_STAGE_xx
, where the first
xx
is the
ID
of the SPA, and the second
xx
is the direction
ID
.
We will get a description of stages with semantics for leads. To do this, we specify in the filter
filter
the field
ENTITY_ID
with the value
STATUS
.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"crm.status.list"
,
{
order
: {
SORT
:
"ASC"
},
// sorting in ascending order by the SORT field value
filter
: {
ENTITY_ID
:
"STATUS"
},
// getting stages for leads
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
'crm.status.list'
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
'ENTITY_ID'
=>
'STATUS'
]
]
);
As a result, we will get an array of objects, where each object is a description of a stage.
{
"result"
:
[
{
"ID"
:
"1"
,
"ENTITY_ID"
:
"STATUS"
,
"STATUS_ID"
:
"NEW"
,
"NAME"
:
"Not Processed"
,
"NAME_INIT"
:
"Not Processed"
,
"SORT"
:
"10"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#00FFFF"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#00FFFF"
}
}
,
{
"ID"
:
"3"
,
"ENTITY_ID"
:
"STATUS"
,
"STATUS_ID"
:
"ASSIGNED"
,
"NAME"
:
"Responsible Assigned"
,
"NAME_INIT"
:
""
,
"SORT"
:
"20"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#FFF100"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#FFF100"
}
}
,
...
,
{
"ID"
:
"15"
,
"ENTITY_ID"
:
"STATUS"
,
"STATUS_ID"
:
"CONVERTED"
,
"NAME"
:
"Converted"
,
"NAME_INIT"
:
"Converted"
,
"SORT"
:
"50"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#37B44A"
,
"SEMANTICS"
:
"S"
,
"EXTRA"
:
{
"SEMANTICS"
:
"success"
,
"COLOR"
:
"#37B44A"
}
}
,
{
"ID"
:
"17"
,
"ENTITY_ID"
:
"STATUS"
,
"STATUS_ID"
:
"JUNK"
,
"NAME"
:
"Poor Quality Lead"
,
"NAME_INIT"
:
"Poor Quality Lead"
,
"SORT"
:
"60"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
null
,
"COLOR"
:
"#F54819"
,
"SEMANTICS"
:
"F"
,
"EXTRA"
:
{
"SEMANTICS"
:
"failure"
,
"COLOR"
:
"#F54819"
}
}
]
,
"total"
:
6
}
The
EXTRA.SEMANTICS
object contains the semantics of the stages. Possible values:
process
— the CRM entity is in progress,
success
— work with the CRM entity has been successfully completed,
failure
— work with the CRM entity has been unsuccessfully completed.
Code Example
Code Example
The code outputs tables with the list of stages for leads and estimates.
JS
PHP
/**
* Loads all statuses for the given ENTITY_ID
*
@param
{
string
} entityId — entity code, e.g., 'STATUS' or 'QUOTE_STATUS'
*
@returns
{
Promise<Array>
} — array of all statuses
*/
function
loadStatuses
(
entityId
) {
return
new
Promise
(
(
resolve, reject
) =>
{
BX24
.
callMethod
(
'crm.status.list'
, {
filter
: {
ENTITY_ID
: entityId },
select
: [
'STATUS_ID'
,
'NAME'
,
'EXTRA'
],
order
: {
SORT
:
'ASC'
}
},
(
result
) =>
{
if
(result.
error
()) {
reject
(result.
error
());
return
;
}
resolve
(result.
data
());
});
});
}
/**
* Groups statuses by semantics
*/
function
groupStatusesBySemantics
(
statuses
) {
const
groups = {
success
: [],
process
: [],
failure
: [] };
statuses.
forEach
(
item
=>
{
const
semantics = item.
EXTRA
?.
SEMANTICS
||
''
;
const
name = item.
NAME
|| item.
STATUS_ID
;
if
(semantics ===
'success'
) {
groups.
success
.
push
(name);
}
else
if
(semantics ===
'failure'
) {
groups.
failure
.
push
(name);
}
else
{
groups.
process
.
push
(name);
}
});
return
groups;
}
/**
* Formats groups for console.table
*/
function
formatForConsoleTable
(
groups
) {
const
{ success, process, failure } = groups;
const
maxLen =
Math
.
max
(success.
length
, process.
length
, failure.
length
);
const
pad
= (
arr, len
) => [...arr, ...
Array
(len - arr.
length
).
fill
(
''
)];
return
Array
(maxLen).
fill
().
map
(
(
_, i
) =>
({
'✅ Success'
:
pad
(success, maxLen)[i],
'⚠️ In Progress'
:
pad
(process, maxLen)[i],
'❌ Failure'
:
pad
(failure, maxLen)[i]
}));
}
// Requesting statuses
Promise
.
all
([
loadStatuses
(
'STATUS'
).
then
(
data
=>
({
type
:
'Leads'
, data })),
loadStatuses
(
'QUOTE_STATUS'
).
then
(
data
=>
({
type
:
'Estimates'
, data }))
]).
then
(
results
=>
{
results.
forEach
(
(
{ type, data }
) =>
{
console
.
group
(
`📊
${type}
`
);
const
groups =
groupStatusesBySemantics
(data);
console
.
table
(
formatForConsoleTable
(groups));
console
.
groupEnd
();
});
}).
catch
(
err
=>
{
console
.
error
(
'Loading error:'
, err);
});
<?php
require_once
'crest.php'
;
/**
* Gets all statuses for the given ENTITY_ID
*
@param
string $entityId
*
@return
array
*/
function
loadStatuses
(
$entityId
)
{
$result
=
CRest
::
call
(
'crm.status.list'
, [
'filter'
=> [
'ENTITY_ID'
=>
$entityId
],
'select'
=> [
'STATUS_ID'
,
'NAME'
,
'EXTRA'
],
'order'
=> [
'SORT'
=>
'ASC'
]
]);
if
(!
empty
(
$result
[
'error'
])) {
throw
new
Exception
(
"Error loading statuses
$entityId
: "
.
$result
[
'error_description'
]);
}
return
$result
[
'result'
];
}
/**
* Groups statuses by semantics
*/
function
groupStatusesBySemantics
(
$statuses
)
{
$groups
= [
'success'
=> [],
'process'
=> [],
'failure'
=> []];
foreach
(
$statuses
as
$item
) {
$semantics
=
$item
[
'EXTRA'
][
'SEMANTICS'
] ??
''
;
$name
=
$item
[
'NAME'
] ??
$item
[
'STATUS_ID'
];
if
(
$semantics
===
'success'
) {
$groups
[
'success'
][] =
$name
;
}
elseif
(
$semantics
===
'failure'
) {
$groups
[
'failure'
][] =
$name
;
}
else
{
$groups
[
'process'
][] =
$name
;
}
}
return
$groups
;
}
/**
* Formats table rows
*/
function
buildTableRows
(
$groups
)
{
$success
=
$groups
[
'success'
];
$process
=
$groups
[
'process'
];
$failure
=
$groups
[
'failure'
];
$max
=
max
(
count
(
$success
),
count
(
$process
),
count
(
$failure
));
$success
=
array_pad
(
$success
,
$max
,
''
);
$process
=
array_pad
(
$process
,
$max
,
''
);
$failure
=
array_pad
(
$failure
,
$max
,
''
);
$rows
= [];
for
(
$i
=
0
;
$i
<
$max
;
$i
++) {
$rows
[] = [
htmlspecialchars
(
$success
[
$i
]),
htmlspecialchars
(
$process
[
$i
]),
htmlspecialchars
(
$failure
[
$i
])
];
}
return
$rows
;
}
$entities
= [
[
'title'
=>
'Lead Statuses'
,
'entityId'
=>
'STATUS'
],
[
'title'
=>
'Estimate Statuses'
,
'entityId'
=>
'QUOTE_STATUS'
]
];
foreach
(
$entities
as
$entity
) {
try
{
$statuses
=
loadStatuses
(
$entity
[
'entityId'
]);
if
(
empty
(
$statuses
)) {
echo
"<p>No statuses for "
.
htmlspecialchars
(
$entity
[
'title'
]) .
"</p>\n"
;
continue
;
}
$groups
=
groupStatusesBySemantics
(
$statuses
);
$rows
=
buildTableRows
(
$groups
);
echo
"<h2>"
.
htmlspecialchars
(
$entity
[
'title'
]) .
"</h2>\n"
;
echo
"<table border=\"1\" style=\"border-collapse: collapse; width: 100%;\">\n"
;
echo
"<thead><tr>
<th style=\"padding: 8px; background: #d4edda;\">✅ Success</th>
<th style=\"padding: 8px; background: #fff3cd;\">⚠️ In Progress</th>
<th style=\"padding: 8px; background: #f8d7da;\">❌ Failure</th>
</tr></thead>\n<tbody>"
;
foreach
(
$rows
as
$row
) {
echo
"<tr>
<td style=\"padding: 6px;\">
{$row[0]}
</td>
<td style=\"padding: 6px;\">
{$row[1]}
</td>
<td style=\"padding: 6px;\">
{$row[2]}
</td>
</tr>\n"
;
}
echo
"</tbody></table><br>\n"
;
}
catch
(
Exception
$e
) {
echo
"<p style=\"color: red;\">Error: "
.
htmlspecialchars
(
$e
->
getMessage
()) .
"</p>\n"
;
}
}
Copied
Was the article helpful?
Yes
No
Previous
How to Get a List of Activities from Deals
Next
How to Get a Sales Funnel for a Given Direction

---

## How to Get the Sales Funnel of a Given Direction with the Semantics of Each Deal Stage

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-get-lists/how-to-get-deal-funnels

How to Get the Sales Funnel of a Given Direction with the Semantics of Each Deal Stage | Bitrix24 REST API and Marketplace Applications
How to Get the Sales Funnel of a Given Direction with the Semantics of Each Deal Stage
How to Get the Sales Funnel of a Given Direction with the Semantics of Each Deal Stage
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
This example outputs all existing deal directions along with the semantics for each stage.
JS
PHP
var
arCategory = [];
BX24
.
callMethod
(
'crm.dealcategory.list'
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
arCategory = result.
data
().
reduce
(
function
(
acc, item
) {
acc[item.
ID
] = item.
NAME
;
return
acc;
}, {});
BX24
.
callMethod
(
'crm.dealcategory.default.get'
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
arCategory[result.
data
().
ID
] = result.
data
().
NAME
;
Object
.
keys
(arCategory).
forEach
(
function
(
id
) {
var
entity_id = id >
0
?
'DEAL_STAGE_'
+ id :
'DEAL_STAGE'
;
BX24
.
callMethod
(
'crm.status.list'
, {
filter
: {
ENTITY_ID
: entity_id } },
function
(
resultDeal
) {
if
(resultDeal.
error
()) {
console
.
error
(resultDeal.
error
());
}
else
{
var
table =
document
.
createElement
(
'table'
);
var
caption =
document
.
createElement
(
'caption'
);
caption.
textContent
= arCategory[id];
table.
appendChild
(caption);
var
thead =
document
.
createElement
(
'thead'
);
var
trHead =
document
.
createElement
(
'tr'
);
[
'STATUS ID'
,
'NAME'
,
'SEMANTICS'
].
forEach
(
function
(
text
) {
var
th =
document
.
createElement
(
'th'
);
th.
textContent
= text;
trHead.
appendChild
(th);
});
thead.
appendChild
(trHead);
table.
appendChild
(thead);
var
tbody =
document
.
createElement
(
'tbody'
);
resultDeal.
data
().
forEach
(
function
(
item
) {
var
tr =
document
.
createElement
(
'tr'
);
if
(item.
EXTRA
&& item.
EXTRA
.
COLOR
) {
tr.
style
.
color
= item.
EXTRA
.
COLOR
;
}
[
'STATUS_ID'
,
'NAME'
,
'EXTRA.SEMANTICS'
].
forEach
(
function
(
key
) {
var
td =
document
.
createElement
(
'td'
);
td.
textContent
= key.
split
(
'.'
).
reduce
(
function
(
acc, k
) {
return
acc && acc[k];
}, item);
tr.
appendChild
(td);
});
tbody.
appendChild
(tr);
});
table.
appendChild
(tbody);
document
.
body
.
appendChild
(table);
}
});
});
}
});
}
});
Note
To use the examples in PHP, set up the
CRest
class and include the
crest.php
file in the files where this class is used.
Learn more
$arCategory
= [];
$result
=
CRest
::
call
(
'crm.dealcategory.list'
);
if
(!
empty
(
$result
[
'result'
]))
{
$arCategory
=
array_column
(
$result
[
'result'
],
'NAME'
,
'ID'
);
}
$result
=
CRest
::
call
(
'crm.dealcategory.default.get'
);
//get name default deal category
if
(!
empty
(
$result
[
'result'
]))
{
$arCategory
[
$result
[
'result'
][
'ID'
]] =
$result
[
'result'
][
'NAME'
];
}
foreach
(
$arCategory
as
$id
=>
$name
):
if
(
$id
>
0
)
{
$entity_id
=
'DEAL_STAGE_'
.
$id
;
}
else
{
$entity_id
=
'DEAL_STAGE'
;
}
$resultDeal
=
CRest
::
call
(
'crm.status.list'
, [
'filter'
=> [
'ENTITY_ID'
=>
$entity_id
]]);
if
(!
empty
(
$resultDeal
[
'result'
])):
?>
<table>
<caption>
<?=
$name
?>
</caption>
<thead>
<tr>
<th>STATUS ID</th>
<th>NAME</th>
<th>SEMANTICS</th>
</tr>
</thead>
<tbody>
<?
foreach
(
$resultDeal
[
'result'
]
as
$item
):
?>
<tr
<?=
(!
empty
(
$item
[
'EXTRA'
][
'COLOR'
]) ?
' style="color:'
.
$item
[
'EXTRA'
][
'COLOR'
] .
'"'
:
''
);
?>
>
<td>
<?=
$item
[
'STATUS_ID'
]
?>
</td>
<td>
<?=
$item
[
'NAME'
]
?>
</td>
<td>
<?=
$item
[
'EXTRA'
][
'SEMANTICS'
]
?>
</td>
<tr>
<?
endforeach
;
?>
</tbody>
</table>
<?
endif
;
?>
<?
endforeach
;
?>
Copied
Was the article helpful?
Yes
No
Previous
How to Get a List of Stages with Semantics for CRM Entities
Next
How to Get a Client's Address from CRM

---

## How to Get a Client's Address from CRM

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-get-lists/how-to-get-address

How to Get a Client's Address from CRM | Bitrix24 REST API and Marketplace Applications
How to Get a Client's Address from CRM
How to Get a Client's Address from CRM
1. Retrieving Requisites Associated with a Contact
2. Retrieving the Address
Code Example
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
A client's address can be stored in Bitrix:
in a user-defined field of type "address" for any CRM entity. To retrieve the address from the field, call the get or list method for the desired entity type.
in the
requisites
of contacts, companies, and leads. Within a single field
Address
, multiple addresses can be stored with their types specified. A single client may have several requisites recorded.
To obtain a client's address from the requisites, sequentially execute two methods:
crm.requisite.list
crm.address.list
1. Retrieving Requisites Associated with a Contact
1. Retrieving Requisites Associated with a Contact
Obtaining the requisite ID is a necessary step, as the address does not have a direct link to the contact or company. The address is linked to the requisite object.
To retrieve the requisites, we use the crm.requisite.list method with the following filter:
in
ENTITY_TYPE_ID
, specify the value
3
— the identifier for
contact type
. For company type, use the identifier
4
.
in
ENTITY_ID
— the contact ID, in this example
2429
. You can obtain the ID using the
crm.contact.list
method with a filter based on any known contact field. To get the company ID, use
crm.company.list
. If you need to obtain the contact or company ID by phone number or email, refer to the tutorial
“Finding Duplicates by Phone Number”
.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"crm.requisite.list"
,
{
filter
: {
"ENTITY_TYPE_ID"
:
"3"
,
"ENTITY_ID"
:
"2429"
,
},
select
: [
"ID"
,
"ENTITY_TYPE_ID"
,
"ENTITY_ID"
,
],
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
'crm.requisite.list'
,
[
'filter'
=> [
'ENTITY_TYPE_ID'
=>
'3'
,
'ENTITY_ID'
=>
'2429'
,
],
'select'
=> [
'ID'
,
'ENTITY_TYPE_ID'
,
'ENTITY_ID'
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
We obtained the requisite ID
361
— a parameter necessary for the next request.
Array
(
[
result
]
=> Array
(
[
0
]
=> Array
(
[
ID
]
=>
361
[
ENTITY_TYPE_ID
]
=>
3
[
ENTITY_ID
]
=>
2429
)
)
[
total
]
=>
1
)
2. Retrieving the Address
2. Retrieving the Address
To obtain the address, we use the crm.address.list method with the following filter:
in
ENTITY_TYPE_ID
, specify the value
8
— the identifier for
requisite type
in
ENTITY_ID
— the requisite ID obtained from the previous request, in this example
361
in
TYPE_ID
— the
address type
, if you need to retrieve a specific one. For example, the delivery address type is
11
, and the legal address type is
6
.
JS
PHP
BX24
.
callMethod
(
"crm.address.list"
,
{
filter
: {
"ENTITY_TYPE_ID"
:
8
,
"ENTITY_ID"
:
361
,
"TYPE_ID"
:
11
,
},
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
'crm.address.list'
,
[
'filter'
=> [
'ENTITY_TYPE_ID'
=>
8
,
'ENTITY_ID'
=>
361
,
'TYPE_ID'
=>
11
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
We received the delivery address data for the contact.
Array
(
[
result
]
=> Array
(
[
0
]
=> Array
(
[
TYPE_ID
]
=>
11
[
ENTITY_TYPE_ID
]
=>
8
[
ENTITY_ID
]
=>
361
[
ADDRESS_1
]
=>
45
th Lane
,
10
c1
[
ADDRESS_2
]
=>
[
CITY
]
=> New York
[
POSTAL_CODE
]
=>
10001
[
REGION
]
=> Manhattan
[
PROVINCE
]
=> New York
[
COUNTRY
]
=> USA
[
COUNTRY_CODE
]
=>
[
LOC_ADDR_ID
]
=>
571
[
ANCHOR_TYPE_ID
]
=>
3
[
ANCHOR_ID
]
=>
2429
)
)
[
total
]
=>
1
)
Code Example
Code Example
JS
PHP
var
contactId =
"your_contact_ID_here"
;
// Replace with the actual contact ID
// Method to retrieve the requisite ID
BX24
.
callMethod
(
"crm.requisite.list"
,
{
filter
: {
"ENTITY_TYPE_ID"
:
3
,
"ENTITY_ID"
: contactId
},
select
: [
"ID"
]
},
function
(
requisiteResult
) {
if
(requisiteResult.
error
()) {
console
.
error
(requisiteResult.
error
());
}
else
{
var
requisites = requisiteResult.
data
();
if
(requisites.
length
>
0
) {
var
requisiteId = requisites[
0
].
ID
;
console
.
log
(
"Requisite ID:"
, requisiteId);
// Method to retrieve the address
BX24
.
callMethod
(
"crm.address.list"
,
{
filter
: {
"ENTITY_TYPE_ID"
:
8
,
"ENTITY_ID"
: requisiteId,
"TYPE_ID"
:
11
}
},
function
(
addressResult
) {
if
(addressResult.
error
()) {
console
.
error
(addressResult.
error
());
}
else
{
var
addresses = addressResult.
data
();
if
(addresses.
length
>
0
) {
// Create a table to display the addresses
var
table = [];
addresses.
forEach
(
function
(
address
) {
table.
push
({
"Address"
: address.
ADDRESS_1
||
"Not specified"
,
"City"
: address.
CITY
||
"Not specified"
,
"Postal Code"
: address.
POSTAL_CODE
||
"Not specified"
,
"Country"
: address.
COUNTRY
||
"Not specified"
});
});
console
.
table
(table);
}
else
{
console
.
log
(
"Delivery address not found."
);
}
}
}
);
}
else
{
console
.
log
(
"Requisite not found."
);
}
}
}
);
require_once
(
'crest.php'
);
$contactId
=
'your_contact_ID_here'
;
// Replace with the actual contact ID
// Method to retrieve the requisite ID
$requisiteResult
=
CRest
::
call
(
'crm.requisite.list'
,
[
'filter'
=> [
'ENTITY_TYPE_ID'
=>
3
,
'ENTITY_ID'
=>
$contactId
],
'select'
=> [
'ID'
]
]
);
if
(
isset
(
$requisiteResult
[
'error'
])) {
echo
'Error: '
.
$requisiteResult
[
'error_description'
];
}
else
{
$requisites
=
$requisiteResult
[
'result'
];
if
(
count
(
$requisites
) >
0
) {
$requisiteId
=
$requisites
[
0
][
'ID'
];
echo
'Requisite ID: '
.
$requisiteId
. PHP_EOL;
// Method to retrieve the address
$addressResult
=
CRest
::
call
(
'crm.address.list'
,
[
'filter'
=> [
'ENTITY_TYPE_ID'
=>
8
,
'ENTITY_ID'
=>
$requisiteId
,
'TYPE_ID'
=>
11
]
]
);
if
(
isset
(
$addressResult
[
'error'
])) {
echo
'Error: '
.
$addressResult
[
'error_description'
];
}
else
{
$addresses
=
$addressResult
[
'result'
];
if
(
count
(
$addresses
) >
0
) {
// Create a table to display the addresses
echo
'<table border="1">'
;
echo
'<tr><th>Address</th><th>City</th><th>Postal Code</th><th>Country</th></tr>'
;
foreach
(
$addresses
as
$address
) {
echo
'<tr>'
;
echo
'<td>'
. (
$address
[
'ADDRESS_1'
] ??
'Not specified'
) .
'</td>'
;
echo
'<td>'
. (
$address
[
'CITY'
] ??
'Not specified'
) .
'</td>'
;
echo
'<td>'
. (
$address
[
'POSTAL_CODE'
] ??
'Not specified'
) .
'</td>'
;
echo
'<td>'
. (
$address
[
'COUNTRY'
] ??
'Not specified'
) .
'</td>'
;
echo
'</tr>'
;
}
echo
'</table>'
;
}
else
{
echo
'Delivery address not found.'
;
}
}
}
else
{
echo
'Requisite not found.'
;
}
}
Copied
Was the article helpful?
Yes
No
Previous
How to Get a Sales Funnel for a Given Direction
Next
How to Get a List of Vendors

---

## How to Get a List of Vendors

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-get-lists/how-to-get-contractors

How to Get a List of Vendors | Bitrix24 REST API and Marketplace Applications
How to Get a List of Vendors
How to Get a List of Vendors
1. Get the Vendor Category ID
2. Get the List of Vendors
Code Example
Scope:
crm
Who can execute the method: users with permission to view contacts or companies in CRM
Vendors are contacts and companies in CRM that have a system category designation:
CATALOG_CONTRACTOR_CONTACT
— for contacts,
CATALOG_CONTRACTOR_COMPANY
— for companies.
To obtain a list of vendors, we will sequentially execute two methods:
crm.category.list
— to get the category ID for the contact or company.
crm.item.list
— to retrieve the list of vendors based on a filter.
1. Get the Vendor Category ID
1. Get the Vendor Category ID
We will use the method
crm.category.list
with the following parameters:
entityTypeId
— the ID of the
CRM object type
. Use
3
for contacts. For companies, use
4
.
filter[code]
— filter by category code. Use
CATALOG_CONTRACTOR_CONTACT
for contacts. For companies, use
CATALOG_CONTRACTOR_COMPANY
.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'crm.category.list'
,
{
entityTypeId
:
3
,
filter
: {
code
:
'CATALOG_CONTRACTOR_CONTACT'
}
},
function
(
result
) {
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
$result
=
CRest
::
call
(
'crm.category.list'
,
[
'entityTypeId'
=>
3
,
'filter'
=> [
'code'
=>
'CATALOG_CONTRACTOR_CONTACT'
]
]
);
As a result, we will obtain the category ID. In the example,
id
:
15
. The ID may vary across different Bitrix24 instances.
{
"result"
:
{
"categories"
:
[
{
"id"
:
15
,
"name"
:
"Vendor Contacts"
,
"entityTypeId"
:
3
,
"isSystem"
:
"Y"
,
"code"
:
"CATALOG_CONTRACTOR_CONTACT"
}
]
}
}
2. Get the List of Vendors
2. Get the List of Vendors
We will filter the items using the method
crm.item.list
with the following parameters:
entityTypeId
— the ID of the
CRM object type
. Use
3
for contacts. For companies, use
4
.
select
— list of fields to output. All available fields can be obtained using the method
crm.item.fields
.
filter[categoryId]
- the ID of the system category from step 1. In the example,
15
.
JS
PHP
BX24
.
callMethod
(
'crm.item.list'
,
{
entityTypeId
:
3
,
select
: [
'id'
,
'name'
,
'lastName'
,
'categoryId'
],
filter
: {
categoryId
:
15
}
},
function
(
result
) {
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
3
,
'select'
=> [
'id'
,
'name'
,
'lastName'
,
'categoryId'
],
'filter'
=> [
'categoryId'
=>
15
]
]
);
As a result, we will obtain a list of contacts that are vendors.
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
2185
,
"name"
:
"He"
,
"lastName"
:
null
,
"categoryId"
:
15
}
,
{
"id"
:
2443
,
"name"
:
"John"
,
"lastName"
:
"Doe"
,
"categoryId"
:
15
}
]
}
,
"total"
:
2
}
The vendor IDs, in the example
id
:
2185
and
id
:
2443
, should be used in the inventory method
catalog.documentcontractor.add
.
Code Example
Code Example
JS
PHP
var
entityTypeId =
3
;
// 3 - contact; for company use 4
var
categoryCode =
'CATALOG_CONTRACTOR_CONTACT'
;
// for company use CATALOG_CONTRACTOR_COMPANY
BX24
.
callMethod
(
'crm.category.list'
,
{
entityTypeId
: entityTypeId,
filter
: {
code
: categoryCode }
},
function
(
resultCategory
) {
if
(resultCategory.
error
()) {
console
.
error
(resultCategory.
error
() +
': '
+ resultCategory.
error_description
());
return
;
}
var
categories = resultCategory.
data
().
categories
|| [];
if
(!categories.
length
) {
console
.
error
(
'Vendor category not found'
);
return
;
}
var
categoryId = categories[
0
].
id
;
BX24
.
callMethod
(
'crm.item.list'
,
{
entityTypeId
: entityTypeId,
select
: [
'id'
,
'name'
,
'lastName'
,
'categoryId'
],
filter
: {
categoryId
: categoryId },
order
: {
ID
:
'DESC'
}
},
function
(
resultItems
) {
if
(resultItems.
error
()) {
console
.
error
(resultItems.
error
() +
': '
+ resultItems.
error_description
());
}
else
{
console
.
log
(resultItems.
data
());
}
}
);
}
);
require_once
(
'crest.php'
);
$entityTypeId
=
3
;
// 3 - contact; for company use 4
$categoryCode
=
'CATALOG_CONTRACTOR_CONTACT'
;
// for company use CATALOG_CONTRACTOR_COMPANY
$resultCategory
=
CRest
::
call
(
'crm.category.list'
,
[
'entityTypeId'
=>
$entityTypeId
,
'filter'
=> [
'code'
=>
$categoryCode
]
]
);
if
(!
empty
(
$resultCategory
[
'error_description'
])) {
echo
$resultCategory
[
'error_description'
];
return
;
}
$categories
=
$resultCategory
[
'result'
][
'categories'
] ?? [];
if
(
empty
(
$categories
)) {
echo
'Vendor category not found'
;
return
;
}
$categoryId
=
$categories
[
0
][
'id'
];
$resultItems
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
$entityTypeId
,
'select'
=> [
'id'
,
'name'
,
'lastName'
,
'categoryId'
],
'filter'
=> [
'categoryId'
=>
$categoryId
],
'order'
=> [
'ID'
=>
'DESC'
]
]
);
if
(!
empty
(
$resultItems
[
'error_description'
])) {
echo
$resultItems
[
'error_description'
];
}
else
{
print_r
(
$resultItems
[
'result'
]);
}
Copied
Was the article helpful?
Yes
No
Previous
How to Get a Client's Address from CRM
Next
How to Filter Elements by Stage Name

---

## How to Filter Items by Stage Name

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-get-lists/how-to-get-elements-by-stage-filter

How to Filter Items by Stage Name | Bitrix24 REST API and Marketplace Applications
How to Filter Items by Stage Name
How to Filter Items by Stage Name
1. Retrieve the Funnel Identifier
2. Retrieve the Stage Identifier
3. Retrieve the List of Items at the Stage
Retrieve the Responsible Person's Data
Code Example
Scope:
crm, user_brief
Who can execute the method: a user with read access to CRM entities
The stage name is not stored in the "Stage" field of the CRM entity. The "Stage" field contains an identifier. You can match the name and identifier of the stage using methods for working with
dictionaries
— system fields of the "list" type. To search for items by stage name, we will sequentially execute three methods:
crm.category.list
— retrieve the funnel identifier
crm.status.list
— retrieve the stage identifier in the funnel
crm.item.list
— retrieve the list of items at the stage
1. Retrieve the Funnel Identifier
1. Retrieve the Funnel Identifier
We will use the method
crm.category.list
with the parameters:
entityTypeId
— specify
2
for deals. This is the identifier of the
object type
. To find out the identifier of the SPA, execute the method
crm.enum.ownertype
without parameters.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"crm.category.list"
,
{
entityTypeId
:
2
,
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
'crm.category.list'
,
[
'entityTypeId'
=>
2
]
);
As a result, we received the deal funnels. We will identify the required funnel by its name in the
name
field. The funnel identifier will be taken from the
id
field.
{
"result"
:
{
"categories"
:
[
{
"id"
:
9
,
"name"
:
"Funnel with Original Name"
,
"sort"
:
200
,
"entityTypeId"
:
2
,
"isDefault"
:
"N"
,
"originId"
:
""
,
"originatorId"
:
""
}
,
{
"id"
:
10
,
"name"
:
"Lead Route"
,
"sort"
:
200
,
"entityTypeId"
:
2
,
"isDefault"
:
"N"
,
"originId"
:
""
,
"originatorId"
:
""
}
,
{
"id"
:
11
,
"name"
:
"Path to Success"
,
"sort"
:
200
,
"entityTypeId"
:
2
,
"isDefault"
:
"N"
,
"originId"
:
""
,
"originatorId"
:
""
}
,
{
"id"
:
0
,
"name"
:
"General"
,
"sort"
:
300
,
"entityTypeId"
:
2
,
"isDefault"
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
}
2. Retrieve the Stage Identifier
2. Retrieve the Stage Identifier
We will use the method
crm.status.list
with the filter:
ENTITY_ID
— specify
DEAL_STAGE_10
, where
10
is the funnel identifier obtained in step 1.
To obtain the stages of the SPA, use a formula like
DYNAMIC_185_STAGE_11
, where
185
is the
ID
of the SPA, and
11
is the
ID
of the funnel.
If the
ID
of the funnel is
0
, make the request for stages without adding
_ID
.
JS
PHP
BX24
.
callMethod
(
"crm.status.list"
,
{
filter
: {
"ENTITY_ID"
:
"DEAL_STAGE_10"
}
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
'crm.status.list'
,
[
'filter'
=> [
'ENTITY_ID'
=>
'DEAL_STAGE_10'
]
]
);
As a result, we received a list of stages. We will identify the required stage by its name in the
NAME
field. The stage identifier will be taken from the
STATUS_ID
field.
{
"result"
:
[
{
"ID"
:
"331"
,
"ENTITY_ID"
:
"DEAL_STAGE_10"
,
"STATUS_ID"
:
"C10:NEW"
,
"NAME"
:
"New"
,
"NAME_INIT"
:
"New"
,
"SORT"
:
"10"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
"5"
,
"COLOR"
:
"#39A8EF"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#39A8EF"
}
}
,
{
"ID"
:
"333"
,
"ENTITY_ID"
:
"DEAL_STAGE_10"
,
"STATUS_ID"
:
"C10:PREPARATION"
,
"NAME"
:
"Document Preparation"
,
"NAME_INIT"
:
""
,
"SORT"
:
"20"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
"5"
,
"COLOR"
:
"#2FC6F6"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#2FC6F6"
}
}
,
{
"ID"
:
"335"
,
"ENTITY_ID"
:
"DEAL_STAGE_10"
,
"STATUS_ID"
:
"C10:PREPAYMENT_INVOICE"
,
"NAME"
:
"Approval"
,
"NAME_INIT"
:
""
,
"SORT"
:
"30"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
"5"
,
"COLOR"
:
"#55d0e0"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#55d0e0"
}
}
,
{
"ID"
:
"337"
,
"ENTITY_ID"
:
"DEAL_STAGE_10"
,
"STATUS_ID"
:
"C10:EXECUTING"
,
"NAME"
:
"In Progress"
,
"NAME_INIT"
:
""
,
"SORT"
:
"40"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
"5"
,
"COLOR"
:
"#47E4C2"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#47E4C2"
}
}
,
{
"ID"
:
"339"
,
"ENTITY_ID"
:
"DEAL_STAGE_10"
,
"STATUS_ID"
:
"C10:FINAL_INVOICE"
,
"NAME"
:
"Final Invoice"
,
"NAME_INIT"
:
""
,
"SORT"
:
"50"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
"5"
,
"COLOR"
:
"#FFA900"
,
"SEMANTICS"
:
null
,
"EXTRA"
:
{
"SEMANTICS"
:
"process"
,
"COLOR"
:
"#FFA900"
}
}
,
{
"ID"
:
"341"
,
"ENTITY_ID"
:
"DEAL_STAGE_10"
,
"STATUS_ID"
:
"C10:WON"
,
"NAME"
:
"Deal Won"
,
"NAME_INIT"
:
"Deal Won"
,
"SORT"
:
"60"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
"5"
,
"COLOR"
:
"#7BD500"
,
"SEMANTICS"
:
"S"
,
"EXTRA"
:
{
"SEMANTICS"
:
"success"
,
"COLOR"
:
"#7BD500"
}
}
,
{
"ID"
:
"343"
,
"ENTITY_ID"
:
"DEAL_STAGE_10"
,
"STATUS_ID"
:
"C10:LOSE"
,
"NAME"
:
"Deal Lost"
,
"NAME_INIT"
:
"Deal Lost"
,
"SORT"
:
"70"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
"5"
,
"COLOR"
:
"#FF5752"
,
"SEMANTICS"
:
"F"
,
"EXTRA"
:
{
"SEMANTICS"
:
"failure"
,
"COLOR"
:
"#FF5752"
}
}
,
{
"ID"
:
"345"
,
"ENTITY_ID"
:
"DEAL_STAGE_10"
,
"STATUS_ID"
:
"C10:APOLOGY"
,
"NAME"
:
"Analysis of Failure Reason"
,
"NAME_INIT"
:
""
,
"SORT"
:
"80"
,
"SYSTEM"
:
"N"
,
"CATEGORY_ID"
:
"5"
,
"COLOR"
:
"#FF5752"
,
"SEMANTICS"
:
"F"
,
"EXTRA"
:
{
"SEMANTICS"
:
"apology"
,
"COLOR"
:
"#FF5752"
}
}
]
,
"total"
:
8
,
}
3. Retrieve the List of Items at the Stage
3. Retrieve the List of Items at the Stage
We will use the method
crm.item.list
with the parameters:
entityTypeId
— specify
2
for deals. This is the identifier of the
object type
. To find out the identifier of the SPA, execute the method
crm.enum.ownertype
without parameters.
filter[stageId]
— specify
C10:PREPAYMENT_INVOICE
. This is the stage identifier obtained in step 2.
select[]
— specify the fields of the items that we want to retrieve. Without the
select
parameter, all fields, including custom ones, will be returned.
JS
PHP
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
"id"
,
"title"
,
"assignedById"
,
"opportunity"
,
],
filter
: {
"stageId"
: [
"C10:PREPAYMENT_INVOICE"
],
},
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
2
,
'select'
=> [
"id"
,
"title"
,
"assignedById"
,
"opportunity"
,
],
'filter'
=> [
"stageId"
=> [
"C10:PREPAYMENT_INVOICE"
],
],
]
);
As a result, we received a list of items at the requested stage.
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
5111
,
"assignedById"
:
1
,
"title"
:
"Purchase of Stoves"
,
"opportunity"
:
500
}
,
{
"id"
:
5199
,
"assignedById"
:
29
,
"title"
:
"Purchase of Heaters"
,
"opportunity"
:
250
}
,
{
"id"
:
5257
,
"assignedById"
:
29
,
"title"
:
"Purchase of Bread Makers"
,
"opportunity"
:
200
}
,
{
"id"
:
5273
,
"assignedById"
:
29
,
"title"
:
"Purchase of Machines"
,
"opportunity"
:
0
}
,
{
"id"
:
5317
,
"assignedById"
:
29
,
"title"
:
"Purchase of Blenders"
,
"opportunity"
:
100
}
]
}
,
"total"
:
5
,
}
Retrieve the Responsible Person's Data
Retrieve the Responsible Person's Data
In the received result, the
ID
of the employee responsible for the item is specified. To display the first name and last name of the employee, we will use the method
user.get
with the filter:
ID
— specify the value from the
assignedById
parameter obtained in step 3.
JS
PHP
BX24
.
callMethod
(
"user.get"
,
{
"ID"
:
29
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
'user.get'
,
[
'ID'
=>
29
]
);
As a result, we will receive data about the employee, including the fields
NAME
and
LAST_NAME
.
{
"result"
:
[
{
"ID"
:
"29"
,
"ACTIVE"
:
true
,
"NAME"
:
"Vadim"
,
"LAST_NAME"
:
"Valeev"
,
"SECOND_NAME"
:
""
,
"EMAIL"
:
"v.r.valeev@bitrix.com"
,
"LAST_LOGIN"
:
"2025-05-15T13:06:54+00:00"
,
"DATE_REGISTER"
:
"2024-07-15T00:00:00+00:00"
,
"TIME_ZONE"
:
""
,
"IS_ONLINE"
:
"Y"
,
"TIMESTAMP_X"
:
{
}
,
"LAST_ACTIVITY_DATE"
:
{
}
,
"PERSONAL_GENDER"
:
""
,
"PERSONAL_WWW"
:
""
,
"PERSONAL_BIRTHDAY"
:
"2000-07-14T00:00:00+00:00"
,
"PERSONAL_MOBILE"
:
""
,
"PERSONAL_CITY"
:
""
,
"WORK_PHONE"
:
""
,
"WORK_POSITION"
:
""
,
"UF_EMPLOYMENT_DATE"
:
""
,
"UF_DEPARTMENT"
:
[
1
]
,
"USER_TYPE"
:
"employee"
}
,
]
,
}
Code Example
Code Example
JS
PHP
// Step 1: Request the funnel name from the user
let
funnelName =
prompt
(
"Enter the name of the deal funnel:"
);
// Step 2: Retrieve the list of funnels
BX24
.
callMethod
(
"crm.category.list"
,
{
entityTypeId
:
2
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
().
ex
);
return
;
}
let
categories = result.
data
().
categories
;
let
selectedFunnel = categories.
find
(
cat
=>
cat.
name
=== funnelName);
if
(!selectedFunnel) {
alert
(
"Funnel not found."
);
return
;
}
let
funnelId = selectedFunnel.
id
;
// Step 3: Request the stage name from the user
let
stageName =
prompt
(
"Enter the name of the stage:"
);
// Step 4: Retrieve the list of stages for the selected funnel
let
entityID = funnelId ===
0
?
"DEAL_STAGE"
:
`DEAL_STAGE_
${funnelId}
`
;
BX24
.
callMethod
(
"crm.status.list"
,
{
filter
: {
"ENTITY_ID"
: entityID }
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
().
ex
);
return
;
}
let
stages = result.
data
();
let
selectedStage = stages.
find
(
stage
=>
stage.
NAME
=== stageName);
if
(!selectedStage) {
alert
(
"Stage not found."
);
return
;
}
let
stageId = selectedStage.
STATUS_ID
;
// Step 5: Retrieve the list of deals at the selected stage
BX24
.
callMethod
(
"crm.item.list"
,
{
entityTypeId
:
2
,
select
: [
"id"
,
"title"
,
"assignedById"
,
"opportunity"
],
filter
: {
"stageId"
: stageId,
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
().
ex
);
return
;
}
let
deals = result.
data
().
items
;
let
uniqueResponsibleIds = [...
new
Set
(deals.
map
(
deal
=>
deal.
assignedById
))];
let
userMap = {};
// Step 6: Retrieve user information
uniqueResponsibleIds.
forEach
(
userId
=>
{
BX24
.
callMethod
(
"user.get"
,
{
"ID"
: userId
},
function
(
userResult
) {
if
(userResult.
error
()) {
console
.
error
(userResult.
error
().
ex
);
return
;
}
let
user = userResult.
data
()[
0
];
userMap[userId] = {
name
: user.
NAME
,
lastName
: user.
LAST_NAME
};
}
);
});
// Step 7: Output results to the console in a text table format
setTimeout
(
() =>
{
let
table = [];
// Header
table.
push
([
"Deal ID"
,
"Title"
,
"Responsible First Name"
,
"Responsible Last Name"
,
"Expected Revenue"
]);
// Data rows
deals.
forEach
(
deal
=>
{
let
responsible = userMap[deal.
assignedById
] || {
name
:
"Unknown"
,
lastName
:
"Unknown"
};
table.
push
([
deal.
id
,
deal.
title
,
responsible.
name
,
responsible.
lastName
,
deal.
opportunity
||
0
]);
});
// Output the table to the console
console
.
table
(table);
},
1000
);
// Delay for all requests to complete
}
);
}
);
}
);
require_once
(
'crest.php'
);
// Step 1: Request the funnel name from the user
$funnelName
=
readline
(
"Enter the name of the deal funnel: "
);
// Step 2: Retrieve the list of funnels
$result
=
CRest
::
call
(
'crm.category.list'
,
[
'entityTypeId'
=>
2
]
);
if
(!
empty
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
exit
;
}
$categories
=
$result
[
'result'
][
'categories'
];
$selectedFunnel
=
null
;
foreach
(
$categories
as
$category
) {
if
(
$category
[
'NAME'
] ===
$funnelName
) {
$selectedFunnel
=
$category
;
break
;
}
}
if
(!
$selectedFunnel
) {
echo
"Funnel not found.\n"
;
exit
;
}
$funnelId
=
$selectedFunnel
[
'ID'
];
// Step 3: Request the stage name from the user
$stageName
=
readline
(
"Enter the name of the stage: "
);
// Step 4: Retrieve the list of stages for the selected funnel
$entityID
=
$funnelId
===
0
?
"DEAL_STAGE"
:
"DEAL_STAGE_
{$funnelId}
"
;
$result
=
CRest
::
call
(
'crm.status.list'
,
[
'filter'
=> [
'ENTITY_ID'
=>
$entityID
]
]
);
if
(!
empty
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
exit
;
}
$stages
=
$result
[
'result'
];
$selectedStage
=
null
;
foreach
(
$stages
as
$stage
) {
if
(
$stage
[
'NAME'
] ===
$stageName
) {
$selectedStage
=
$stage
;
break
;
}
}
if
(!
$selectedStage
) {
echo
"Stage not found.\n"
;
exit
;
}
$stageId
=
$selectedStage
[
'STATUS_ID'
];
// Step 5: Retrieve the list of deals at the selected stage
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
"id"
,
"title"
,
"assignedById"
,
"opportunity"
],
'filter'
=> [
"stageId"
=>
$stageId
]
]
);
if
(!
empty
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
exit
;
}
$deals
=
$result
[
'result'
][
'items'
];
$uniqueResponsibleIds
=
array_unique
(
array_column
(
$deals
,
'assignedById'
));
$userMap
= [];
// Step 6: Retrieve user information
foreach
(
$uniqueResponsibleIds
as
$userId
) {
$result
=
CRest
::
call
(
'user.get'
,
[
'ID'
=>
$userId
]
);
if
(!
empty
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
continue
;
}
$user
=
$result
[
'result'
][
0
];
$userMap
[
$userId
] = [
'name'
=>
$user
[
'NAME'
],
'lastName'
=>
$user
[
'LAST_NAME'
]
];
}
// Step 7: Output results in a text table format
$table
= [];
// Header
$table
[] = [
"Deal ID"
,
"Title"
,
"Responsible First Name"
,
"Responsible Last Name"
,
"Expected Revenue"
];
// Data rows
foreach
(
$deals
as
$deal
) {
$responsible
=
$userMap
[
$deal
[
'assignedById'
]] ?? [
'name'
=>
'Unknown'
,
'lastName'
=>
'Unknown'
];
$table
[] = [
$deal
[
'id'
],
$deal
[
'title'
],
$responsible
[
'name'
],
$responsible
[
'lastName'
],
$deal
[
'opportunity'
] ??
0
];
}
// Output the table
foreach
(
$table
as
$row
) {
echo
implode
(
"\t"
,
$row
) .
"\n"
;
}
Copied
Was the article helpful?
Yes
No
Previous
How to Get a List of Vendors
Next
Sales Intelligence

---

