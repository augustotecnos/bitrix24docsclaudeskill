---
description: 'CRM Deals: Recurring deals and user-defined fields'
methods:
- crm.category.
- crm.deal.contact.
- crm.deal.get
- crm.deal.list
- crm.deal.recurring.add
- crm.deal.recurring.delete
- crm.deal.recurring.expose
- crm.deal.recurring.fields
- crm.deal.recurring.get
- crm.deal.recurring.list
- crm.deal.recurring.update
- crm.deal.update
- crm.deal.userfield.add
- crm.deal.userfield.delete
- crm.deal.userfield.get
- crm.deal.userfield.list
- crm.deal.userfield.update
- crm.item.productrow.
- crm.status.entity.types
- crm.userfield.fields
- crm.userfield.settings.fields
- crm.userfield.types
- event.bind
pages: 24
title: 'CRM Deals: Recurring deals and user-defined fields'
---
# CRM Deals: Recurring deals and user-defined fields
> CRM Deals: Recurring deals and user-defined fields
> **24 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Recurring Deals: Overview of Methods](#recurring-deals-overview-of-methods)
- [Create a New Recurring Deal crm.deal.recurring.add](#create-a-new-recurring-deal-crmdealrecurringadd)
- [Get the list of fields for the recurring deal template crm.deal.recurring.fields](#get-the-list-of-fields-for-the-recurring-deal-temp)
- [Create a New Deal from the Template crm.deal.recurring.expose](#create-a-new-deal-from-the-template-crmdealrecurri)
- [Update existing settings for the recurring deal template crm.deal.recurring.update](#update-existing-settings-for-the-recurring-deal-te)
- [Get the fields of the recurring deal template settings by Id crm.deal.recurring.get](#get-the-fields-of-the-recurring-deal-template-sett)
- [Get a list of recurring deal template settings crm.deal.recurring.list](#get-a-list-of-recurring-deal-template-settings-crm)
- [Delete existing settings for the recurring deal template crm.deal.recurring.delete](#delete-existing-settings-for-the-recurring-deal-te)
- [Overview of Events When Working with Recurring Deals](#overview-of-events-when-working-with-recurring-dea)
- [Event when creating a recurring deal template onCrmDealRecurringAdd](#event-when-creating-a-recurring-deal-template-oncr)
- [Event on Regular Deal Template Change onCrmDealRecurringUpdate](#event-on-regular-deal-template-change-oncrmdealrec)
- [Event on Deleting a Recurring Deal Template onCrmDealRecurringDelete](#event-on-deleting-a-recurring-deal-template-oncrmd)
- [Event when creating a new deal from a recurring deal template onCrmDealRecurringExpose](#event-when-creating-a-new-deal-from-a-recurring-de)
- [Custom Fields for Deals: Overview of Methods](#custom-fields-for-deals-overview-of-methods)
- [Create a Custom Field for Deals crm.deal.userfield.add](#create-a-custom-field-for-deals-crmdealuserfieldad)
- [Update Existing Custom Field for Deals crm.deal.userfield.update](#update-existing-custom-field-for-deals-crmdealuser)
- [Get Custom Deal Field by ID crm.deal.userfield.get](#get-custom-deal-field-by-id-crmdealuserfieldget)
- [Get a list of custom fields for deals crm.deal.userfield.list](#get-a-list-of-custom-fields-for-deals-crmdealuserf)
- [Delete Custom Field crm.deal.userfield.delete](#delete-custom-field-crmdealuserfielddelete)
- [Overview of Events When Working with Custom Deal Fields](#overview-of-events-when-working-with-custom-deal-f)
- [Event when adding a custom field onCrmDealUserFieldAdd](#event-when-adding-a-custom-field-oncrmdealuserfiel)
- [Event on user field change onCrmDealUserFieldUpdate](#event-on-user-field-change-oncrmdealuserfieldupdat)
- [Event onCrmDealUserFieldDelete](#event-oncrmdealuserfielddelete)
- [Event on changing the set of values for a custom list-type field onCrmDealUserFieldSetEnumValues](#event-on-changing-the-set-of-values-for-a-custom-l)

---

## Recurring Deals: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/index

Recurring Deals: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Recurring Deals: Overview of Methods
Recurring Deals: Overview of Methods
Connection of Recurring Deals with Other CRM Objects
Overview of Methods and Events
Recurring deals are deals that are created based on a template. You can set the period and the number of repetitions for recurring deals. They will be automatically created in the selected Sales Funnel.
Quick navigation:
all methods and events
User documentation:
Recurring deals
Connection of Recurring Deals with Other CRM Objects
Connection of Recurring Deals with Other CRM Objects
Deals.
To create a new template, use the method
crm.deal.recurring.add
. Pass the ID of an existing deal in the
DEAL_ID
parameter of the method. The field values of this deal will be saved in the template.
To view the deal based on which the template was created, execute the method
crm.deal.recurring.list
. As a result, you will receive the value
BASED_ID
. Pass the obtained value to the
id
parameter of the method
crm.deal.get
. If the template was created in the recurring deals section of Bitrix24, the
BASED_ID
parameter will be empty.
Funnels.
You can create and manage sales funnels for deals through the group of methods
crm.category.*
where
entityTypeId
of the deal =
2
. To create a recurring deal in the desired funnel, pass the funnel ID in the
CATEGORY_ID
parameter.
Products.
If the deal template includes product items, a new recurring deal will be created with them. To modify the product items in the template, use the methods from the group
crm.item.productrow.*
. Pass the
DEAL_ID
value from the result of the method
crm.deal.recurring.list
as the
ownerId
of the deal.
Clients.
If a company and contacts are selected in the deal template, a new recurring deal will be created with them. To change the company in the template, use the method
crm.deal.update
, and to change the contacts — the methods from the group
crm.deal.contact.*
. Pass the
DEAL_ID
value from the result of the method
crm.deal.recurring.list
as the
id
of the deal.
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can execute the method: depending on the method
Methods
Events
Method
Description
crm.deal.recurring.add
Creates a new recurring deal template
crm.deal.recurring.fields
Returns a list of fields for the recurring deal template
crm.deal.recurring.expose
Creates a new deal based on the template
crm.deal.recurring.update
Modifies the settings of the recurring deal template
crm.deal.recurring.get
Returns the settings of the recurring deal template by Id
crm.deal.recurring.list
Returns a list of recurring deal templates
crm.deal.recurring.delete
Deletes a recurring deal template
Event
Triggered
onCrmDealRecurringAdd
When a new recurring deal is created
onCrmDealRecurringUpdate
When a recurring deal is modified
onCrmDealRecurringDelete
When a recurring deal is deleted
onCrmDealRecurringExpose
When a new deal is created from a recurring deal
Copied
Was the article helpful?
Yes
No
Previous
When Changing the Sales Funnel
Next
Create a New Recurring Deal

---

## Create a New Recurring Deal crm.deal.recurring.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/crm-deal-recurring-add

Create a New Recurring Deal crm.deal.recurring.add | Bitrix24 REST API and Marketplace Applications
Create a New Recurring Deal crm.deal.recurring.add
Create a New Recurring Deal crm.deal.recurring.add
Example
Statuses and System Error Codes
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.recurring.add
adds a new setting for a recurring deal.
Parameter
Description
fields
A set of fields – an array of the form
array ("field"=>"value"[, ...])
, containing the values of the deal fields. The required field is
DEAL_ID
[ID of the deal for which the parameter
IS_RECURRING=Y
is set].
Note
To find out the required format of the fields, execute the method
crm.deal.recurring.fields
and check the format of the received values for these fields.
Example
Example
How to Use Examples in Documentation
JS
PHP
BX24.js
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
const
nextYear =
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
nextYear.
setFullYear
(current.
getFullYear
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
'+03:00'
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
"crm.deal.recurring.add"
,
{
fields
:
{
"DEAL_ID"
:
"45"
,
"CATEGORY_ID"
:
"1"
,
"IS_LIMIT"
:
"D"
,
"LIMIT_DATE"
:
date2str
(nextYear),
"START_DATE"
:
date2str
(nextMonth),
"PARAMS"
: {
"MODE"
:
"multiple"
,
"MULTIPLE_TYPE"
:
"month"
,
"MULTIPLE_INTERVAL"
:
1
,
"OFFSET_BEGINDATE_TYPE"
:
"day"
,
"OFFSET_BEGINDATE_VALUE"
:
1
,
"OFFSET_CLOSEDATE_TYPE"
:
"month"
,
"OFFSET_CLOSEDATE_VALUE"
:
2
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
console
.
info
(
"Recurring deal settings added. Record ID - "
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
$nextYear
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
$nextYear
->
setDate
(
$current
->
format
(
'Y'
) +
1
,
$current
->
format
(
'm'
),
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
'crm.deal.recurring.add'
,
[
'fields'
=> [
'DEAL_ID'
=>
'45'
,
'CATEGORY_ID'
=>
'1'
,
'IS_LIMIT'
=>
'D'
,
'LIMIT_DATE'
=>
date2str
(
$nextYear
),
'START_DATE'
=>
date2str
(
$nextMonth
),
'PARAMS'
=> [
'MODE'
=>
'multiple'
,
'MULTIPLE_TYPE'
=>
'month'
,
'MULTIPLE_INTERVAL'
=>
1
,
'OFFSET_BEGINDATE_TYPE'
=>
'day'
,
'OFFSET_BEGINDATE_VALUE'
=>
1
,
'OFFSET_CLOSEDATE_TYPE'
=>
'month'
,
'OFFSET_CLOSEDATE_VALUE'
=>
2
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
'Success: Recurring deal settings added. Record ID - '
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
'Error adding recurring deal settings: '
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
var
nextYear =
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
nextYear.
setYear
(current.
getFullYear
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
'+03:00'
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
"crm.deal.recurring.add"
,
{
fields
:
{
"DEAL_ID"
:
"45"
,
"CATEGORY_ID"
:
"1"
,
"IS_LIMIT"
:
"D"
,
"LIMIT_DATE"
:
date2str
(nextYear),
"START_DATE"
:
date2str
(nextMonth),
"PARAMS"
: {
"MODE"
:
"multiple"
,
"MULTIPLE_TYPE"
:
"month"
,
"MULTIPLE_INTERVAL"
:
1
,
"OFFSET_BEGINDATE_TYPE"
:
"day"
,
"OFFSET_BEGINDATE_VALUE"
:
1
,
"OFFSET_CLOSEDATE_TYPE"
:
"month"
,
"OFFSET_CLOSEDATE_VALUE"
:
2
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
"Recurring deal settings added. Record ID - "
+ result.
data
());
}
);
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
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Get the List of Recurring Deal Template Fields

---

## Get the list of fields for the recurring deal template crm.deal.recurring.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/crm-deal-recurring-fields

Get the list of fields for the recurring deal template crm.deal.recurring.fields | Bitrix24 REST API and Marketplace Applications
Get the list of fields for the recurring deal template crm.deal.recurring.fields
Get the list of fields for the recurring deal template crm.deal.recurring.fields
Example
Returned fields
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.recurring.fields
returns a list of fields for configuring the recurring deal template along with descriptions.
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
'crm.deal.recurring.fields'
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
'crm.deal.recurring.fields'
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
'Error fetching recurring deal fields: '
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
"crm.deal.recurring.fields"
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
How to Use Examples in Documentation
Returned fields
Returned fields
Field
Description
ID
integer
Identifier of the record in the settings table for the recurring deal. Read-only.
DEAL_ID
integer
ID of the deal template. Immutable.
BASED_ID
integer
ID of the deal on which the template was based. Immutable.
ACTIVE
char
Active flag. Values: Y/N.
NEXT_EXECUTION
date
Date of the next creation of a new deal from the template. Calculated by the system based on the specified parameters. If the value is empty, new deals are not created. Read-only.
LAST_EXECUTION
date
Date of the last creation of a new deal from the template. Read-only.
COUNTER_REPEAT
integer
Number of deals created from the template. Read-only.
START_DATE
date
Start date for calculating the date of the next creation of a new deal. If the value is empty, it is calculated from the current date.
CATEGORY_ID
char
Category that will be assigned to the deal created from the template.
IS_LIMIT
char
Are there restrictions on creating new deals? Values: N - no restrictions, D - date restriction set, T - limit on the number of new deals set.
LIMIT_REPEAT
integer
Maximum number of deals that can be created from this template. Considered if
IS_LIMIT
is T.
LIMIT_DATE
date
Date until which deals can be created from this template. Considered if
IS_LIMIT
is D.
PARAMS
Set of parameters for calculation -
recurring_params
:
MODE
- repetition mode:
single - single (one deal will be created from the template, offset is calculated to the value of START_DATE);
multiple - multiple
MULTIPLE_TYPE
- type of repetition in multiple mode [MODE is multiple]:
day - day
week - week
month - month
year - year
MULTIPLE_INTERVAL
- offset value [MODE is multiple]
SINGLE_BEFORE_START_DATE_TYPE
- type of offset before the start date [MODE is single]:
day - day
week - week
month - month
year - year
SINGLE_BEFORE_START_DATE_VALUE
- offset value before the start date, if not set - no offset [MODE is single]
OFFSET_BEGINDATE_TYPE
- type of offset for calculating the "deal start date" field, calculation is made from the moment of creating a new deal from the template:
day - day
week - week
month - month
year - year
OFFSET_BEGINDATE_VALUE
- offset value for calculating the "deal start date" field, calculation is made from the moment of creating a new deal from the template
OFFSET_CLOSEDATE_TYPE
- offset value for calculating the "deal completion date" field, calculation is made from the moment of creating a new deal from the template:
day - day
week - week
month - month
year - year
OFFSET_CLOSEDATE_VALUE
- offset value for calculating the "deal completion date" field, calculation is made from the moment of creating a new deal from the template
Related methods and topics
Create a New Recurring Deal crm.deal.recurring.add
Copied
Was the article helpful?
Yes
No
Previous
Create a New Recurring Deal
Next
Create a New Deal from a Template

---

## Create a New Deal from the Template crm.deal.recurring.expose

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/crm-deal-recurring-expose

Create a New Deal from the Template crm.deal.recurring.expose | Bitrix24 REST API and Marketplace Applications
Create a New Deal from the Template crm.deal.recurring.expose
Create a New Deal from the Template crm.deal.recurring.expose
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.recurring.expose
creates a new deal from the template.
Parameter
Description
id
*
Identifier of the recurring deal template setting.
Required parameters are marked with *
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
"crm.deal.recurring.expose"
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
'crm.deal.recurring.expose'
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
'Error exposing recurring deal: '
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
"crm.deal.recurring.expose"
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
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get the List of Recurring Deal Template Fields
Next
Modify an Existing Setting for a Recurring Deal Template

---

## Update existing settings for the recurring deal template crm.deal.recurring.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/crm-deal-recurring-update

Update existing settings for the recurring deal template crm.deal.recurring.update | Bitrix24 REST API and Marketplace Applications
Update existing settings for the recurring deal template crm.deal.recurring.update
Update existing settings for the recurring deal template crm.deal.recurring.update
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.recurring.update
updates the existing settings for the recurring deal template.
Parameter
Description
id
Identifier of the recurring deal template settings.
fields
Set of fields – an array of the form
array("field_to_update"=>"value"[, ...])
, where "field_to_update" can take values returned by the method
crm.deal.recurring.fields
.
Note
To find out the required format of the fields, execute the method
crm.deal.recurring.fields
and check the format of the returned values for those fields.
Example
Example
JS
PHP
BX24.js
try
{
const
current =
new
Date
();
const
nextYear =
new
Date
();
nextYear.
setYear
(current.
getFullYear
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
"crm.deal.recurring.update"
,
{
id
: id,
fields
:
{
"CATEGORY_ID"
:
"2"
,
"START_DATE"
:
date2str
(nextYear),
"PARAMS"
: {
"MODE"
:
"single"
,
"SINGLE_BEFORE_START_DATE_TYPE"
:
"day"
,
"SINGLE_BEFORE_START_DATE_VALUE"
:
5
,
"OFFSET_BEGINDATE_TYPE"
:
"day"
,
"OFFSET_BEGINDATE_VALUE"
:
1
,
"OFFSET_CLOSEDATE_TYPE"
:
"month"
,
"OFFSET_CLOSEDATE_VALUE"
:
2
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
(error);
}
try
{
$current
=
new
DateTime
();
$nextYear
=
new
DateTime
();
$nextYear
->
setDate
(
$current
->
format
(
'Y'
) +
1
);
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
'crm.deal.recurring.update'
,
[
'id'
=>
$id
,
'fields'
=> [
'CATEGORY_ID'
=>
'2'
,
'START_DATE'
=>
$date2str
(
$nextYear
),
'PARAMS'
=> [
'MODE'
=>
'single'
,
'SINGLE_BEFORE_START_DATE_TYPE'
=>
'day'
,
'SINGLE_BEFORE_START_DATE_VALUE'
=>
5
,
'OFFSET_BEGINDATE_TYPE'
=>
'day'
,
'OFFSET_BEGINDATE_VALUE'
=>
1
,
'OFFSET_CLOSEDATE_TYPE'
=>
'month'
,
'OFFSET_CLOSEDATE_VALUE'
=>
2
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
'Error updating recurring deal: '
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
nextYear =
new
Date
();
nextYear.
setYear
(current.
getFullYear
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
"crm.deal.recurring.update"
,
{
id
: id,
fields
:
{
"CATEGORY_ID"
:
"2"
,
"START_DATE"
:
date2str
(nextYear),
"PARAMS"
: {
"MODE"
:
"single"
,
"SINGLE_BEFORE_START_DATE_TYPE"
:
"day"
,
"SINGLE_BEFORE_START_DATE_VALUE"
:
5
,
"OFFSET_BEGINDATE_TYPE"
:
"day"
,
"OFFSET_BEGINDATE_VALUE"
:
1
,
"OFFSET_CLOSEDATE_TYPE"
:
"month"
,
"OFFSET_CLOSEDATE_VALUE"
:
2
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
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Create a New Deal from a Template
Next
Get the Template Settings Fields for a Recurring Deal by Id

---

## Get the fields of the recurring deal template settings by Id crm.deal.recurring.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/crm-deal-recurring-get

Get the fields of the recurring deal template settings by Id crm.deal.recurring.get | Bitrix24 REST API and Marketplace Applications
Get the fields of the recurring deal template settings by Id crm.deal.recurring.get
Get the fields of the recurring deal template settings by Id crm.deal.recurring.get
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.recurring.get
returns the fields of the recurring deal template settings by identifier.
Parameter
Description
id
*
Identifier of the recurring deal template settings.
Required parameters are marked with *
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
"crm.deal.recurring.get"
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
'crm.deal.recurring.get'
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
'Error calling crm.deal.recurring.get: '
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
"crm.deal.recurring.get"
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
Modify an Existing Setting for a Recurring Deal Template
Next
Get the List of Recurring Deal Template Settings

---

## Get a list of recurring deal template settings crm.deal.recurring.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/crm-deal-recurring-list

Get a list of recurring deal template settings crm.deal.recurring.list | Bitrix24 REST API and Marketplace Applications
Get a list of recurring deal template settings crm.deal.recurring.list
Get a list of recurring deal template settings crm.deal.recurring.list
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.recurring.list
returns a list of recurring deal template settings based on the filter.
When querying, use the mask "*" to select all fields (excluding custom and multiple fields).
See the description of
list methods
.
Example
Example
JS
PHP
BX24.js
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.deal.recurring.list'
,
{
order
: {
"DEAL_ID"
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
"DEAL_ID "
,
"NEXT_EXECUTION"
,
"LAST_EXECUTION"
,
"CATEGORY_ID"
,
"IS_LIMIT"
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
'crm.deal.recurring.list'
, {
order
: {
"DEAL_ID"
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
"DEAL_ID "
,
"NEXT_EXECUTION"
,
"LAST_EXECUTION"
,
"CATEGORY_ID"
,
"IS_LIMIT"
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
'crm.deal.recurring.list'
, {
order
: {
"DEAL_ID"
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
"DEAL_ID "
,
"NEXT_EXECUTION"
,
"LAST_EXECUTION"
,
"CATEGORY_ID"
,
"IS_LIMIT"
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
'crm.deal.recurring.list'
,
[
'order'
=> [
'DEAL_ID'
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
'DEAL_ID'
,
'NEXT_EXECUTION'
,
'LAST_EXECUTION'
,
'CATEGORY_ID'
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
'Error fetching recurring deals: '
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
"crm.deal.recurring.list"
,
{
order
: {
"DEAL_ID"
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
"DEAL_ID "
,
"NEXT_EXECUTION"
,
"LAST_EXECUTION"
,
"CATEGORY_ID"
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
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get the Template Settings Fields for a Recurring Deal by Id
Next
Delete an Existing Setting for a Recurring Deal Template

---

## Delete existing settings for the recurring deal template crm.deal.recurring.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/crm-deal-recurring-delete

Delete existing settings for the recurring deal template crm.deal.recurring.delete | Bitrix24 REST API and Marketplace Applications
Delete existing settings for the recurring deal template crm.deal.recurring.delete
Delete existing settings for the recurring deal template crm.deal.recurring.delete
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm
Who can execute the method: any user
The method
crm.deal.recurring.delete
removes the existing settings for the recurring deal template.
Parameter
Description
id
*
Identifier of the recurring deal template settings.
Required parameters are marked with *
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
"crm.deal.recurring.delete"
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
'crm.deal.recurring.delete'
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
'Error deleting recurring deal: '
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
"crm.deal.recurring.delete"
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
Get the List of Recurring Deal Template Settings
Next
Overview of Events

---

## Overview of Events When Working with Recurring Deals

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/events/index

Overview of Events When Working with Recurring Deals | Bitrix24 REST API and Marketplace Applications
Overview of Events When Working with Recurring Deals
Overview of Events When Working with Recurring Deals
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, update, or deletion of recurring deals, as well as when new deals are automatically created based on recurring deal templates.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to recurring deal events through:
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
onCrmDealRecurringAdd
When a new recurring deal is created manually or via the method
crm.deal.recurring.add
onCrmDealRecurringUpdate
When a recurring deal is modified manually or via the method
crm.deal.recurring.update
onCrmDealRecurringDelete
When a recurring deal is deleted manually or via the method
crm.deal.recurring.delete
onCrmDealRecurringExpose
When a new deal is automatically created based on a recurring deal template or via the method
crm.deal.recurring.expose
Copied
Was the article helpful?
Yes
No
Previous
Delete an Existing Setting for a Recurring Deal Template
Next
When Creating a New Recurring Deal

---

## Event when creating a recurring deal template onCrmDealRecurringAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/events/on-crm-deal-recurring-add

Event when creating a recurring deal template onCrmDealRecurringAdd | Bitrix24 REST API and Marketplace Applications
Event when creating a recurring deal template onCrmDealRecurringAdd
Event when creating a recurring deal template onCrmDealRecurringAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMDEALRECURRINGADD
will trigger when a new template for a recurring deal is created.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMDEALRECURRINGADD"
,
"event_handler_id"
:
"677"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"11"
,
"RECURRING_DEAL_ID"
:
"6797"
}
}
,
"ts"
:
"1741091781"
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
ONCRMDEALRECURRINGADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created template.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created template.
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
Identifier of the record in the recurring deals settings table
RECURRING_DEAL_ID
integer
Identifier of the recurring deal template
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
Event on Deleting a Recurring Deal Template onCrmDealRecurringDelete
Event when creating a new deal from a recurring deal template onCrmDealRecurringExpose
Event on Regular Deal Template Change onCrmDealRecurringUpdate
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Modifying a Recurring Deal

---

## Event on Regular Deal Template Change onCrmDealRecurringUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/events/on-crm-deal-recurring-update

Event on Regular Deal Template Change onCrmDealRecurringUpdate | Bitrix24 REST API and Marketplace Applications
Event on Regular Deal Template Change onCrmDealRecurringUpdate
Event on Regular Deal Template Change onCrmDealRecurringUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMDEALRECURRINGUPDATE
will trigger when the template of a recurring deal is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMDEALRECURRINGUPDATE"
,
"event_handler_id"
:
"679"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"9"
,
"RECURRING_DEAL_ID"
:
"6791"
}
}
,
"ts"
:
"1741092489"
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
ONCRMDEALRECURRINGUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the modified template.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the modified template.
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
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
integer
Identifier of the record in the settings table for recurring deals
RECURRING_DEAL_ID
integer
Identifier of the recurring deal template
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
Event on Deleting a Recurring Deal Template onCrmDealRecurringDelete
Event when creating a new deal from a recurring deal template onCrmDealRecurringExpose
Event when creating a recurring deal template onCrmDealRecurringAdd
Copied
Was the article helpful?
Yes
No
Previous
When Creating a New Recurring Deal
Next
When Deleting a Recurring Deal

---

## Event on Deleting a Recurring Deal Template onCrmDealRecurringDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/events/on-crm-deal-recurring-delete

Event on Deleting a Recurring Deal Template onCrmDealRecurringDelete | Bitrix24 REST API and Marketplace Applications
Event on Deleting a Recurring Deal Template onCrmDealRecurringDelete
Event on Deleting a Recurring Deal Template onCrmDealRecurringDelete
What the Handler Receives
Parameter FIELDS
Parameter auth
Continue Exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMDEALRECURRINGDELETE
will trigger when a recurring deal template is deleted.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMDEALRECURRINGDELETE"
,
"event_handler_id"
:
"681"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"11"
}
}
,
"ts"
:
"1741092153"
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
ONCRMDEALRECURRINGDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted template.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted template.
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
Identifier of the deleted record in the recurring deals settings table
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
Event when creating a recurring deal template onCrmDealRecurringAdd
Event when creating a new deal from a recurring deal template onCrmDealRecurringExpose
Event on Regular Deal Template Change onCrmDealRecurringUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Modifying a Recurring Deal
Next
When Creating a New Deal from a Recurring Deal

---

## Event when creating a new deal from a recurring deal template onCrmDealRecurringExpose

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/recurring-deals/events/on-crm-deal-recurring-expose

Event when creating a new deal from a recurring deal template onCrmDealRecurringExpose | Bitrix24 REST API and Marketplace Applications
Event when creating a new deal from a recurring deal template onCrmDealRecurringExpose
Event when creating a new deal from a recurring deal template onCrmDealRecurringExpose
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMDEALRECURRINGEXPOSE
will trigger when a new deal is created from a recurring deal template.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMDEALRECURRINGEXPOSE"
,
"event_handler_id"
:
"683"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"9"
,
"RECURRING_DEAL_ID"
:
"6791"
,
"DEAL_ID"
:
"6799"
}
}
,
"ts"
:
"1741092489"
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
ONCRMDEALRECURRINGEXPOSE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created deal.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created deal and the template from which the deal was created.
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
Identifier of the record in the settings table for recurring deals
RECURRING_DEAL_ID
integer
Identifier of the recurring deal template
DEAL_ID
integer
Identifier of the deal created from the template
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
Event on Deleting a Recurring Deal Template onCrmDealRecurringDelete
Event when creating a recurring deal template onCrmDealRecurringAdd
Event on Regular Deal Template Change onCrmDealRecurringUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Recurring Deal
Next
Overview of Methods

---

## Custom Fields for Deals: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/index

Custom Fields for Deals: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Custom Fields for Deals: Overview of Methods
Custom Fields for Deals: Overview of Methods
Types of Custom Fields
Settings for Custom Fields
Errors When Working with Custom Fields
Common Causes of Server Errors
Overview of Methods
Custom fields store information about a deal in various data formats: string, number, link, address, and others.
Quick navigation:
all methods
User Documentation:
Custom Fields in CRM
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
Settings for Custom Fields
Settings for Custom Fields
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
In the cloud Bitrix24, submit a request to
technical support
to get details about the error.
In the on-premise Bitrix24, request the server error log from the server administrator or hosting administrator. Then, contact
technical support
and attach the log for analysis.
Common Causes of Server Errors
Common Causes of Server Errors
You can create 1016 custom fields for deals — this is a limitation of the database architecture. If there are already 1016 fields for deals in Bitrix24, attempting to create a new field will result in the method
crm.deal.userfield.add
returning an error
INTERNAL_SERVER_ERROR
.
You can check the number of custom fields for deals using the method
crm.deal.userfield.list
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
a custom field for deals depends on the number of deals. When a field is created, it is added to all deal detail forms. When a field is deleted, it is removed from all detail forms. The fewer deals in your Bitrix24, the faster fields are created and deleted.
To check the number of deals in Bitrix24, use the method
crm.deal.list
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can perform the methods: depending on the method
Methods
Events
Method
Description
crm.deal.userfield.add
Creates a new custom field for deals
crm.deal.userfield.update
Modifies an existing custom field for deals
crm.deal.userfield.get
Retrieves a custom field for deals by Id
crm.deal.userfield.list
Gets a list of custom fields for deals
crm.deal.userfield.delete
Deletes a custom field for deals
Event
Triggered
onCrmDealUserFieldAdd
When a custom field is added
onCrmDealUserFieldUpdate
When a custom field is modified
onCrmDealUserFieldDelete
When a custom field is deleted
onCrmDealUserFieldSetEnumValues
When the set of values for a list-type custom field is changed
Copied
Was the article helpful?
Yes
No
Previous
When Creating a New Deal from a Recurring Deal
Next
Add Custom Field

---

## Create a Custom Field for Deals crm.deal.userfield.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/crm-deal-userfield-add

Create a Custom Field for Deals crm.deal.userfield.add | Bitrix24 REST API and Marketplace Applications
Create a Custom Field for Deals crm.deal.userfield.add
Create a Custom Field for Deals crm.deal.userfield.add
Method Parameters
Parameter fields
Parameter SETTINGS
Parameter LIST
Code Examples
Example of Creating a Custom Field of Type String
Example of Creating a Custom Field of Type List
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: CRM administrator
The method
crm.deal.userfield.add
creates a new custom field for deals.
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
The system limit for the field code is 20 characters. The custom field name always has the prefix
UF_CRM_
, meaning the actual name length is 13 characters.
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
Error message
HELP_MESSAGE
string
|
lang_map
Help
MULTIPLE
boolean
Is the field multiple? Possible values:
Y
— yes
N
— no
Fields of type
boolean
cannot be multiple.
By default,
N
MANDATORY
boolean
Is the field mandatory? Possible values:
Y
— yes
N
— no
By default,
N
SHOW_FILTER
boolean
Should the field be shown in the filter? Possible values:
Y
— yes
N
— no
By default,
N
SETTINGS
object
Additional field parameters. Each
USER_TYPE_ID
field type has its own set of available settings, described
below
LIST
uf_enum_element[]
List of possible values for the custom field of type
enumeration
, described
below
By default,
[]
SORT
integer
Sort index. Must be greater than zero.
By default,
100
SHOW_IN_LIST
boolean
Should the custom field be shown in the list.
This parameter has no effect within
crm
.
Possible values:
Y
— yes
N
— no
By default,
N
EDIT_IN_LIST
boolean
Allow user editing? Possible values:
Y
— yes
N
— no
By default,
Y
. The value
N
is not supported by all field types within
crm
IS_SEARCHABLE
boolean
Are the field values searchable?
This parameter has no effect within
crm
.
Possible values:
Y
— yes
N
— no
By default,
N
Parameter SETTINGS
Parameter SETTINGS
Each type of custom fields has its own set of additional settings. This method only supports those described below.
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
By default,
''
ROWS
integer
Number of rows in the input field. Must be greater than 0.
By default,
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
By default,
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
By default,
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
By default,
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
— use current time/date
FIXED
— use time/date from
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
By default,
LIST
LIST_HEIGHT
List height. Must be greater than 0.
Available only when
DISPLAY = LIST
or
DISPLAY = UI
.
By default,
1
Name
type
Description
IBLOCK_TYPE_ID
string
Identifier of the information block type.
By default,
''
IBLOCK_ID
string
Identifier of the information block.
By default,
0
DEFAULT_VALUE
string
Default value.
By default,
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
By default,
LIST
LIST_HEIGHT
integer
List height. Must be greater than 0.
By default,
1
ACTIVE_FILTER
boolean
Show elements with the active flag enabled. Possible values:
Y
— yes
N
— no
By default,
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
By default,
''
If none of the following options are provided, the link to leads will be enabled by default
LEAD = Y
.
Name
type
Description
LEAD
boolean
Is the link to
Leads
enabled? Possible values:
Y
— yes
N
— no
By default,
N
CONTACT
boolean
Is the link to
Contacts
enabled? Possible values:
Y
— yes
N
— no
By default,
N
COMPANY
boolean
Is the link to
Companies
enabled? Possible values:
Y
— yes
N
— no
By default,
N
DEAL
boolean
Is the link to
Deals
enabled? Possible values:
Y
— yes
N
— no
By default,
N
Parameter LIST
Parameter LIST
Name
type
Description
VALUE
string
Value of the list item.
List items with an empty or missing
VALUE
will be ignored
SORT
integer
Sort index. Must be greater than or equal to 0.
By default,
0
DEF
boolean
Is the list item the default value? Possible values:
Y
— yes
N
— no
For a multiple field, multiple
DEF = Y
are allowed. For a non-multiple field, the first provided list item with
DEF = Y
will be considered default.
By default,
N
XML_ID
string
External code of the value. Must be unique within the list items of the custom field
Code Examples
Code Examples
How to Use Examples in Documentation
Example of Creating a Custom Field of Type String
Example of Creating a Custom Field of Type String
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
'{"fields":{"LABEL":"Field '
Hello, World!
'","USER_TYPE_ID":"string","FIELD_NAME":"HELLO_WORLD","MULTIPLE":"Y","MANDATORY":"Y","SHOW_FILTER":"Y","SETTINGS":{"DEFAULT_VALUE":"Hello, World! Default value","ROWS":3},"SORT":1000,"EDIT_IN_LIST":"Y","LIST_FILTER_LABEL":"Hello, World! Filter","LIST_COLUMN_LABEL":{"en":"Hello, World! Column","de":"Hallo, Welt! Spalte"},"EDIT_FORM_LABEL":{"en":"Hello, World! Edit","de":"Hallo, Welt! Bearbeiten"},"ERROR_MESSAGE":{"en":"Hello, World! Error","de":"Hallo, Welt! Fehler"},"HELP_MESSAGE":{"en":"Hello, World! Help","de":"Hallo, Welt! Hilfe"}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.userfield.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"LABEL":"Field '
Hello, World!
'","USER_TYPE_ID":"string","FIELD_NAME":"HELLO_WORLD","MULTIPLE":"Y","MANDATORY":"Y","SHOW_FILTER":"Y","SETTINGS":{"DEFAULT_VALUE":"Hello, World! Default value","ROWS":3},"SORT":1000,"EDIT_IN_LIST":"Y","LIST_FILTER_LABEL":"Hello, World! Filter","LIST_COLUMN_LABEL":{"en":"Hello, World! Column","de":"Hallo, Welt! Spalte"},"EDIT_FORM_LABEL":{"en":"Hello, World! Edit","de":"Hallo, Welt! Bearbeiten"},"ERROR_MESSAGE":{"en":"Hello, World! Error","de":"Hallo, Welt! Fehler"},"HELP_MESSAGE":{"en":"Hello, World! Help","de":"Hallo, Welt! Hilfe"}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.deal.userfield.add
BX24
.
callMethod
(
'crm.deal.userfield.add'
,
{
fields
: {
LABEL
:
"Field 'Hello, World!'"
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
'crm.deal.userfield.add'
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
'Test Field'
,
'USER_TYPE_ID'
=>
'string'
,
'XML_ID'
=>
'test_field_1'
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
'Test Field Label'
,
'LIST_COLUMN_LABEL'
=>
'Test Field List Label'
,
'LIST_FILTER_LABEL'
=>
'Test Field Filter Label'
,
'ERROR_MESSAGE'
=>
'Error occurred'
,
'HELP_MESSAGE'
=>
'Help message for Test Field'
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
dealUserfield
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
Example of Creating a Custom Field of Type List
Example of Creating a Custom Field of Type List
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.userfield.add
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
https://**put_your_bitrix24_address**/rest/crm.deal.userfield.add
BX
.
rest
.
callMethod
(
'crm.deal.userfield.add'
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
'crm.deal.userfield.add'
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
HTTP Status:
200
{
"result"
:
6997
,
"time"
:
{
"start"
:
1753789240.8146
,
"finish"
:
1753789241.058695
,
"duration"
:
0.2440950870513916
,
"processing"
:
0.19217395782470703
,
"date_start"
:
"2025-07-29T14:40:40+02:00"
,
"date_finish"
:
"2025-07-29T14:40:41+02:00"
,
"operating_reset_at"
:
1753789840
,
"operating"
:
0.19216084480285645
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
HTTP Status:
400
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
Code
Description
Value
400
The 'FIELD_NAME' field is not found
Either an empty
FIELD_NAME
was provided, or it was not provided at all
400
Field name is too long (more than 50 characters).
The provided
FIELD_NAME
contains more than 50 characters
400
Field name contains invalid characters. Valid characters are: A-Z, 0-9, and _.
The provided
FIELD_NAME
contains invalid characters
400
The 'USER_TYPE_ID' field is not found
Either an empty
USER_TYPE_ID
was provided, or it was not provided at all
400
Invalid user type specified
The provided
USER_TYPE_ID
does not exist
400
List item with XML_ID='XML_ID' already exists
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
Update Existing Custom Field for Deals crm.deal.userfield.update
Get Custom Deal Field by ID crm.deal.userfield.get
Get a list of custom fields for deals crm.deal.userfield.list
Delete Custom Field crm.deal.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Existing Deal Custom Field

---

## Update Existing Custom Field for Deals crm.deal.userfield.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/crm-deal-userfield-update

Update Existing Custom Field for Deals crm.deal.userfield.update | Bitrix24 REST API and Marketplace Applications
Update Existing Custom Field for Deals crm.deal.userfield.update
Update Existing Custom Field for Deals crm.deal.userfield.update
Method Parameters
Parameter fields
Parameter SETTINGS
Parameter LIST
Code Examples
Example of Updating a String Type Custom Field
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: CRM administrator
The method
crm.deal.userfield.update
updates an existing custom field for deals.
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
crm.deal.userfield.add
and
crm.deal.userfield.list
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
Required parameters are marked with *
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
Additional field parameters. Each field type
USER_TYPE_ID
has its own set of available settings, which are described
below
.
The field only overwrites the passed values
LIST
uf_enum_element[]
List of possible values for the custom field of type
enumeration
, description
below
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
Value
N
is not supported by all field types within
crm
IS_SEARCHABLE
boolean
Are the field values searchable?
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
For languages without an explicitly specified value,
''
will be recorded.
The field completely overwrites the previous value
LIST_COLUMN_LABEL
string
|
lang_map
Header in the list.
When passing a string, it is set for each language.
For languages without an explicitly specified value,
''
will be recorded.
The field completely overwrites the previous value
EDIT_FORM_LABEL
string
|
lang_map
Label in the edit form.
When passing a string, it is set for each language.
For languages without an explicitly specified value,
''
will be recorded.
The field completely overwrites the previous value
ERROR_MESSAGE
string
|
lang_map
Error message
HELP_MESSAGE
string
|
lang_map
Help
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
Default value
ROWS
integer
Number of rows in the input field. Must be greater than 0
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
Number precision. Must be greater than or equal to 0
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
Height of the list. Must be greater than 0.
Available only when
DISPLAY = LIST
or
DISPLAY = UI
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
Height of the list. Must be greater than 0
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
to find possible values
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
Parameter LIST
Parameter LIST
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
Sort index. Must be greater than or equal to 0
DEF
boolean
Is the list element the default value? Possible values:
Y
— yes
N
— no
For a multiple field, several
DEF = Y
are allowed. For a non-multiple field, the first passed list element with
DEF = Y
will be considered default
XML_ID
string
External code of the value. Must be unique within the elements of the custom field list
Code Examples
Code Examples
How to Use Examples in Documentation
Example of Updating a String Type Custom Field
Example of Updating a String Type Custom Field
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
'{"id":536,"fields":{"MANDATORY":"N","SHOW_FILTER":"N","SETTINGS":{"DEFAULT_VALUE":"Hello, World! Default value (changed)","ROWS":10},"SORT":2000,"EDIT_IN_LIST":"N","LIST_FILTER_LABEL":"Hello, World! Filter (changed)","LIST_COLUMN_LABEL":{"en":"Hello, World! Column (changed)","de":"Hallo, Welt! Spalte (geändert)"},"EDIT_FORM_LABEL":{"en":"Hello, World! Edit (changed)","de":"Hallo, Welt! Bearbeiten (geändert)"},"ERROR_MESSAGE":{"en":"Hello, World! Error (changed)","de":"Hallo, Welt! Fehler (geändert)"},"HELP_MESSAGE":{"en":"Hello, World! Help (changed)","de":"Hallo, Welt! Hilfe (geändert)"}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.userfield.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":536,"fields":{"MANDATORY":"N","SHOW_FILTER":"N","SETTINGS":{"DEFAULT_VALUE":"Hello, World! Default value (changed)","ROWS":10},"SORT":2000,"EDIT_IN_LIST":"N","LIST_FILTER_LABEL":"Hello, World! Filter (changed)","LIST_COLUMN_LABEL":{"en":"Hello, World! Column (changed)","de":"Hallo, Welt! Spalte (geändert)"},"EDIT_FORM_LABEL":{"en":"Hello, World! Edit (changed)","de":"Hallo, Welt! Bearbeiten (geändert)"},"ERROR_MESSAGE":{"en":"Hello, World! Error (changed)","de":"Hallo, Welt! Fehler (geändert)"},"HELP_MESSAGE":{"en":"Hello, World! Help (changed)","de":"Hallo, Welt! Hilfe (geändert)"}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.deal.userfield.update
BX24
.
callMethod
(
'crm.deal.userfield.update'
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
'crm.deal.userfield.update'
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
1753790234.592207
,
"finish"
:
1753790234.762644
,
"duration"
:
0.17043709754943848
,
"processing"
:
0.11566615104675293
,
"date_start"
:
"2025-07-29T14:57:14+02:00"
,
"date_finish"
:
"2025-07-29T14:57:14+02:00"
,
"operating_reset_at"
:
1753790834
,
"operating"
:
0.11564803123474121
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
400
Parameter 'fields' must be array
The passed
fields
is not an object
400
ID is not defined or invalid
The passed
id
is less than zero or not passed at all
403
Access denied
Occurs when:
the user does not have administrative rights
the user tries to change a custom field not linked to deals
ERROR_NOT_FOUND
The entity with ID 'id' is not found
The custom field with the passed
id
does not exist
ERROR_CORE
List element with value XML_ID='XML_ID' already exists
The passed
XML_ID
for the list element must be unique within the elements of the custom field
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
Create a Custom Field for Deals crm.deal.userfield.add
Get Custom Deal Field by ID crm.deal.userfield.get
Get a list of custom fields for deals crm.deal.userfield.list
Delete Custom Field crm.deal.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Custom Field
Next
Get Deal Custom Field by Id

---

## Get Custom Deal Field by ID crm.deal.userfield.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/crm-deal-userfield-get

Get Custom Deal Field by ID crm.deal.userfield.get | Bitrix24 REST API and Marketplace Applications
Get Custom Deal Field by ID crm.deal.userfield.get
Get Custom Deal Field by ID crm.deal.userfield.get
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
Who can execute the method: CRM administrator
The method
crm.deal.userfield.get
returns a custom deal field by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the custom field associated with the deal.
The identifier can be obtained using the methods
crm.deal.userfield.add
or
crm.deal.userfield.list
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
'{"id":399}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.deal.userfield.get
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
https://**put_your_bitrix24_address**/rest/crm.deal.userfield.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.userfield.get'
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
'crm.deal.userfield.get'
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
'Error getting deal user field: '
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
'crm.deal.userfield.get'
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
'crm.deal.userfield.get'
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
"6997"
,
"ENTITY_ID"
:
"CRM_DEAL"
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
"2000"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"N"
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
"N"
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
"ROWS"
:
10
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
"Hello, World! Default value (changed)"
}
,
"EDIT_FORM_LABEL"
:
{
"ar"
:
""
,
"br"
:
""
,
"de"
:
"Hallo, Welt! Bearbeiten (geändert)"
,
"en"
:
"Hello, World! Edit (changed)"
,
"fr"
:
""
,
"hi"
:
""
,
"id"
:
""
,
"in"
:
""
,
"it"
:
""
,
"ja"
:
""
,
"kz"
:
""
,
"la"
:
""
,
"ms"
:
""
,
"pl"
:
""
,
"ru"
:
""
,
"sc"
:
""
,
"tc"
:
""
,
"th"
:
""
,
"tr"
:
""
,
"ua"
:
""
,
"vn"
:
""
}
,
"LIST_COLUMN_LABEL"
:
{
"ar"
:
""
,
"br"
:
""
,
"de"
:
"Hallo, Welt! Spalte (geändert)"
,
"en"
:
"Hello, World! Column (changed)"
,
"fr"
:
""
,
"hi"
:
""
,
"id"
:
""
,
"in"
:
""
,
"it"
:
""
,
"ja"
:
""
,
"kz"
:
""
,
"la"
:
""
,
"ms"
:
""
,
"pl"
:
""
,
"ru"
:
""
,
"sc"
:
""
,
"tc"
:
""
,
"th"
:
""
,
"tr"
:
""
,
"ua"
:
""
,
"vn"
:
""
}
,
"LIST_FILTER_LABEL"
:
{
"ar"
:
""
,
"br"
:
""
,
"de"
:
"Hallo, Welt! Filter (geändert)"
,
"en"
:
"Hello, World! Filter (changed)"
,
"fr"
:
""
,
"hi"
:
""
,
"id"
:
""
,
"in"
:
""
,
"it"
:
""
,
"ja"
:
""
,
"kz"
:
""
,
"la"
:
""
,
"ms"
:
""
,
"pl"
:
""
,
"ru"
:
""
,
"sc"
:
""
,
"tc"
:
""
,
"th"
:
""
,
"tr"
:
""
,
"ua"
:
""
,
"vn"
:
""
}
,
"ERROR_MESSAGE"
:
{
"ar"
:
""
,
"br"
:
""
,
"de"
:
"Hallo, Welt! Fehler (geändert)"
,
"en"
:
"Hello, World! Error (changed)"
,
"fr"
:
""
,
"hi"
:
""
,
"id"
:
""
,
"in"
:
""
,
"it"
:
""
,
"ja"
:
""
,
"kz"
:
""
,
"la"
:
""
,
"ms"
:
""
,
"pl"
:
""
,
"ru"
:
""
,
"sc"
:
""
,
"tc"
:
""
,
"th"
:
""
,
"tr"
:
""
,
"ua"
:
""
,
"vn"
:
""
}
,
"HELP_MESSAGE"
:
{
"ar"
:
""
,
"br"
:
""
,
"de"
:
"Hallo, Welt! Hilfe (geändert)"
,
"en"
:
"Hello, World! Help (changed)"
,
"fr"
:
""
,
"hi"
:
""
,
"id"
:
""
,
"in"
:
""
,
"it"
:
""
,
"ja"
:
""
,
"kz"
:
""
,
"la"
:
""
,
"ms"
:
""
,
"pl"
:
""
,
"ru"
:
""
,
"sc"
:
""
,
"tc"
:
""
,
"th"
:
""
,
"tr"
:
""
,
"ua"
:
""
,
"vn"
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
1753790529.430936
,
"finish"
:
1753790529.487882
,
"duration"
:
0.05694580078125
,
"processing"
:
0.0039789676666259766
,
"date_start"
:
"2025-07-29T15:02:09+02:00"
,
"date_finish"
:
"2025-07-29T15:02:09+02:00"
,
"operating_reset_at"
:
1753791129
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
The root element of the response, contains information about the custom field. The final list of fields depends on the field type, detailed descriptions of the fields can be found in the method
crm.deal.userfield.add
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
403
Access denied
Occurs when:
the user does not have administrative rights
the user attempts to access a custom field not linked to deals
400
ID is not defined or invalid
The provided
id
is less than or equal to zero, or not provided at all
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
Create a Custom Field for Deals crm.deal.userfield.add
Update Existing Custom Field for Deals crm.deal.userfield.update
Get a list of custom fields for deals crm.deal.userfield.list
Delete Custom Field crm.deal.userfield.delete
Copied
Was the article helpful?
Yes
No
Previous
Update Existing Deal Custom Field
Next
Get List of Deal Custom Fields

---

## Get a list of custom fields for deals crm.deal.userfield.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/crm-deal-userfield-list

Get a list of custom fields for deals crm.deal.userfield.list | Bitrix24 REST API and Marketplace Applications
Get a list of custom fields for deals crm.deal.userfield.list
Get a list of custom fields for deals crm.deal.userfield.list
Method Parameters
Available fields for filtering
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: CRM administrator
The method
crm.deal.userfield.list
returns a list of custom fields for deals based on the filter.
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
field_n
— the name of the field by which the selection of custom fields will be filtered
value_n
— the filter value
All conditions for individual fields are combined using
AND
. See the
list of available fields for filtering
below.
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
"SORT": "ASC",
"ID": "ASC"
}
Available fields for filtering
Available fields for filtering
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
Whether the custom field is multiple.
Possible values:
Y
— yes
N
— no
MANDATORY
boolean
Whether the custom field is mandatory. Possible values:
Y
— yes
N
— no
SHOW_FILTER
char
Whether to show in the list filter. Possible values:
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
Whether to show in the list. Possible values:
Y
— yes
N
— no
EDIT_IN_LIST
boolean
Whether to allow user editing. Possible values:
Y
— yes
N
— no
IS_SEARCHABLE
boolean
Whether the field values are searchable. Possible values:
Y
— yes
N
— no
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
are multiple,
are mandatory,
have custom field labels in German. Thanks to the filter by the
LANG
parameter, we will additionally receive field names in the response.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.deal.userfield.list
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
https://**put_your_bitrix24_address**/rest/crm.deal.userfield.list
// callListMethod is recommended when you need to retrieve
// the entire set of list data and the volume of records is relatively small
// (up to about 1000 items). The method loads all data at once, which
// can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.deal.userfield.list'
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
progress: number
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
, entity) }
}
catch
(
error
: any) {
console
.
error
(
'Request failed'
, error)
}
// fetchListMethod is preferred when working with large datasets.
// The method implements iterative selection using a generator, which
// allows processing data in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.deal.userfield.list'
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
, entity) }
}
}
catch
(
error
: any) {
console
.
error
(
'Request failed'
, error)
}
// callMethod provides manual control over the pagination
// of data retrieval through the start parameter. Suitable for scenarios where
// precise control over request batches is required. However, with large
// volumes of data, it may be less efficient compared to
// fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.userfield.list'
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
, entity) }
}
catch
(
error
: any) {
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
'crm.deal.userfield.list'
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
'Error fetching deal user fields: '
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
'crm.deal.userfield.list'
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
'crm.deal.userfield.list'
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
"N"
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
"5815"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1713790573"
,
"USER_TYPE_ID"
:
"crm_status"
,
"XML_ID"
:
null
,
"SORT"
:
"100"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"N"
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
"ENTITY_TYPE"
:
"INDUSTRY"
}
,
"EDIT_FORM_LABEL"
:
"Directory"
,
"LIST_COLUMN_LABEL"
:
"Directory"
,
"LIST_FILTER_LABEL"
:
"Directory"
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
"6799"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1724077760"
,
"USER_TYPE_ID"
:
"enumeration"
,
"XML_ID"
:
null
,
"SORT"
:
"150"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"N"
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
"EDIT_FORM_LABEL"
:
"Radio"
,
"LIST_COLUMN_LABEL"
:
"Radio"
,
"LIST_FILTER_LABEL"
:
"Radio"
,
"ERROR_MESSAGE"
:
null
,
"HELP_MESSAGE"
:
null
,
"LIST"
:
[
{
"ID"
:
"3157"
,
"SORT"
:
"10"
,
"VALUE"
:
"Children's Radio"
,
"DEF"
:
"N"
,
"XML_ID"
:
"79b4c576f96e65eb40f390e45c0dc802"
}
,
{
"ID"
:
"3159"
,
"SORT"
:
"20"
,
"VALUE"
:
"Shanson Radio"
,
"DEF"
:
"N"
,
"XML_ID"
:
"d3ffd89a825f218f5efd79dffd38fbbf"
}
,
{
"ID"
:
"3161"
,
"SORT"
:
"30"
,
"VALUE"
:
"Love Radio"
,
"DEF"
:
"N"
,
"XML_ID"
:
"dff769fa19d7d7ce8d0677341d221161"
}
,
{
"ID"
:
"3163"
,
"SORT"
:
"40"
,
"VALUE"
:
"Monte Carlo Radio"
,
"DEF"
:
"N"
,
"XML_ID"
:
"1f22e5c818ce336a42bd0ec94eb69b9e"
}
,
{
"ID"
:
"3181"
,
"SORT"
:
"130"
,
"VALUE"
:
"DFM Yuriev-Polsky"
,
"DEF"
:
"N"
,
"XML_ID"
:
"fc1c5e6b4a9fd20b4749240b8dbac41a"
}
]
}
,
{
"ID"
:
"6791"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1722578010"
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
"150"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"N"
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
"Estimate (files)"
,
"LIST_COLUMN_LABEL"
:
"Estimate (files)"
,
"LIST_FILTER_LABEL"
:
"Estimate (files)"
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
"5567"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1709565075"
,
"USER_TYPE_ID"
:
"resourcebooking"
,
"XML_ID"
:
null
,
"SORT"
:
"1"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"N"
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
"USE_USERS"
:
"N"
,
"USE_RESOURCES"
:
"Y"
,
"RESOURCES"
:
{
"resource"
:
{
"XML_ID"
:
"resource"
,
"NAME"
:
"resource"
,
"SECTIONS"
:
[
{
"ID"
:
"7"
,
"CAL_TYPE"
:
"resource"
,
"NAME"
:
"Museum Hall"
}
,
{
"ID"
:
"49"
,
"CAL_TYPE"
:
"resource"
,
"NAME"
:
"resource 1"
}
,
{
"ID"
:
"51"
,
"CAL_TYPE"
:
"resource"
,
"NAME"
:
"resource 2"
}
,
{
"ID"
:
"53"
,
"CAL_TYPE"
:
"resource"
,
"NAME"
:
"1"
}
,
{
"ID"
:
"57"
,
"CAL_TYPE"
:
"resource"
,
"NAME"
:
"Resource"
}
,
{
"ID"
:
"59"
,
"CAL_TYPE"
:
"resource"
,
"NAME"
:
"Resource 2"
}
]
}
}
,
"SELECTED_RESOURCES"
:
[
{
"type"
:
"resource"
,
"id"
:
"7"
,
"title"
:
"Museum Hall"
}
]
,
"SELECTED_USERS"
:
[
]
,
"FULL_DAY"
:
"N"
,
"ALLOW_OVERBOOKING"
:
"Y"
,
"USE_SERVICES"
:
"N"
,
"SERVICE_LIST"
:
[
{
"name"
:
""
,
"duration"
:
"60"
}
]
,
"RESOURCE_LIMIT"
:
-1
,
"TIMEZONE"
:
"Europe/Berlin"
,
"USE_USER_TIMEZONE"
:
"N"
}
,
"EDIT_FORM_LABEL"
:
"MEETING ROOM BOOKING"
,
"LIST_COLUMN_LABEL"
:
"MEETING ROOM BOOKING"
,
"LIST_FILTER_LABEL"
:
"MEETING ROOM BOOKING"
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
"6997"
,
"ENTITY_ID"
:
"CRM_DEAL"
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
"2000"
,
"MULTIPLE"
:
"Y"
,
"MANDATORY"
:
"N"
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
"N"
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
"ROWS"
:
10
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
"Hello, world! Default value (modified)"
}
,
"EDIT_FORM_LABEL"
:
"Hello, world! Edit (modified)"
,
"LIST_COLUMN_LABEL"
:
"Hello, world! Column (modified)"
,
"LIST_FILTER_LABEL"
:
"Hello, world! Filter (modified)"
,
"ERROR_MESSAGE"
:
"Hello, world! Error (modified)"
,
"HELP_MESSAGE"
:
"Hello, world! Help (modified)"
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
1753793143.219832
,
"finish"
:
1753793143.529472
,
"duration"
:
0.30964016914367676
,
"processing"
:
0.06361007690429688
,
"date_start"
:
"2025-07-29T15:45:43+02:00"
,
"date_finish"
:
"2025-07-29T15:45:43+02:00"
,
"operating_reset_at"
:
1753793743
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
The root element of the response, contains a list of custom fields.
The structure of an individual custom field depends on its type. The fields
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
, or are not returned at all.
total
integer
The number of found custom fields
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
400
Parameter 'order' must be array
The provided
order
is not an object
400
Parameter 'filter' must be array
The provided
filter
is not an object
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
Create a Custom Field for Deals crm.deal.userfield.add
Update Existing Custom Field for Deals crm.deal.userfield.update
Get Custom Deal Field by ID crm.deal.userfield.get
Delete Custom Field crm.deal.userfield.delete
How to Set Up Rounding for a Custom Field of Type "Number"
How to Save the Payment Date in the Deal Field
Copied
Was the article helpful?
Yes
No
Previous
Get Deal Custom Field by Id
Next
Delete Deal Custom Field

---

## Delete Custom Field crm.deal.userfield.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/crm-deal-userfield-delete

Delete Custom Field crm.deal.userfield.delete | Bitrix24 REST API and Marketplace Applications
Delete Custom Field crm.deal.userfield.delete
Delete Custom Field crm.deal.userfield.delete
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
Who can execute the method: CRM administrator
The method
crm.deal.userfield.delete
removes a custom field from deals.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the custom field associated with the deal.
The identifier can be obtained using the methods
crm.deal.userfield.add
or
crm.deal.userfield.list
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
'{"id":432}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webbhook_here**/crm.deal.userfield.delete
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
https://**put_your_bitrix24_address**/rest/crm.deal.userfield.delete
try
{
const
response =
await
$b24.
callMethod
(
'crm.deal.userfield.delete'
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
dealUserfield
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
"Userfield deleted successfully."
);
}
else
{
print
(
"Failed to delete userfield."
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
'crm.deal.userfield.delete'
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
'crm.deal.userfield.delete'
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
400
ID is not defined or invalid
The provided
id
is either less than or equal to zero, or not provided at all
403
Access denied
Occurs when:
the user does not have administrative rights
the user attempts to delete a custom field not associated with deals
ERROR_NOT_FOUND
The entity with ID 'id' is not found
The custom field with the provided
id
does not exist
400
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
Create a Custom Field for Deals crm.deal.userfield.add
Get Custom Deal Field by ID crm.deal.userfield.get
Get a list of custom fields for deals crm.deal.userfield.list
Update Existing Custom Field for Deals crm.deal.userfield.update
Copied
Was the article helpful?
Yes
No
Previous
Get List of Deal Custom Fields
Next
Overview of Events

---

## Overview of Events When Working with Custom Deal Fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/events/index

Overview of Events When Working with Custom Deal Fields | Bitrix24 REST API and Marketplace Applications
Overview of Events When Working with Custom Deal Fields
Overview of Events When Working with Custom Deal Fields
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in near real-time: receiving notifications about the creation, update, or deletion of custom deal fields.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to events for custom deal fields through:
outgoing webhook
application
and the method
event.bind
An example of a handler code for the event is described in the article
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
Triggered By
onCrmDealUserFieldAdd
When a custom field is added manually or via the method
crm.deal.userfield.add
onCrmDealUserFieldUpdate
When a custom field is changed manually or via the method
crm.deal.userfield.update
onCrmDealUserFieldDelete
When a custom field is deleted manually or via the method
crm.deal.userfield.delete
onCrmDealUserFieldSetEnumValues
When the set of values for a list-type custom field is changed manually or via the method
crm.deal.userfield.update
Copied
Was the article helpful?
Yes
No
Previous
Delete Deal Custom Field
Next
When Adding a Custom Field

---

## Event when adding a custom field onCrmDealUserFieldAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/events/on-crm-deal-user-field-add

Event when adding a custom field onCrmDealUserFieldAdd | Bitrix24 REST API and Marketplace Applications
Event when adding a custom field onCrmDealUserFieldAdd
Event when adding a custom field onCrmDealUserFieldAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
onCrmDealUserFieldAdd
will trigger when a custom field is added.
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMDEALUSERFIELDADD"
,
"event_handler_id"
:
"657"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6947"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1736930561"
}
}
,
"ts"
:
"1736930561"
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
ONCRMDEALUSERFIELDADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created field.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created field.
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
Identifier of the custom field
ENTITY_ID
string
Symbolic identifier of the object for which the field was created. In this case —
CRM_DEAL
FIELD_NAME
string
Name of the created custom field
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
Event onCrmDealUserFieldDelete
Event on changing the set of values for a custom list-type field onCrmDealUserFieldSetEnumValues
Event on user field change onCrmDealUserFieldUpdate
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Updating a Custom Field

---

## Event on user field change onCrmDealUserFieldUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/events/on-crm-deal-user-field-update

Event on user field change onCrmDealUserFieldUpdate | Bitrix24 REST API and Marketplace Applications
Event on user field change onCrmDealUserFieldUpdate
Event on user field change onCrmDealUserFieldUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
onCrmDealUserFieldUpdate
will trigger when a user field is changed.
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMDEALUSERFIELDUPDATE"
,
"event_handler_id"
:
"661"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6947"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1736930561"
}
}
,
"ts"
:
"1736944167"
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
ONCRMDEALUSERFIELDUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated field.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the updated fields.
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
Identifier of the user field
ENTITY_ID
string
Symbolic identifier of the object for which the field was updated. In this case —
CRM_DEAL
FIELD_NAME
string
Name of the updated user field
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
Event when adding a custom field onCrmDealUserFieldAdd
Event onCrmDealUserFieldDelete
Event on changing the set of values for a custom list-type field onCrmDealUserFieldSetEnumValues
Copied
Was the article helpful?
Yes
No
Previous
When Adding a Custom Field
Next
When Deleting a Custom Field

---

## Event onCrmDealUserFieldDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/events/on-crm-deal-user-field-delete

Event onCrmDealUserFieldDelete | Bitrix24 REST API and Marketplace Applications
Event onCrmDealUserFieldDelete
Event onCrmDealUserFieldDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
onCrmDealUserFieldDelete
will trigger when a custom field is deleted.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMDEALUSERFIELDDELETE"
,
"event_handler_id"
:
"663"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"5227"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1592601331"
}
}
,
"ts"
:
"1736943852"
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
ONCRMDEALUSERFIELDDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted field.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the deleted field.
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
Identifier of the custom field
ENTITY_ID
string
Symbolic identifier of the object for which the field was deleted. In this case —
CRM_DEAL
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
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event when adding a custom field onCrmDealUserFieldAdd
Event on changing the set of values for a custom list-type field onCrmDealUserFieldSetEnumValues
Event on user field change onCrmDealUserFieldUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Updating a Custom Field
Next
When Changing the Set of Values for a List-Type Custom Field

---

## Event on changing the set of values for a custom list-type field onCrmDealUserFieldSetEnumValues

**Source:** https://apidocs.bitrix24.com/api-reference/crm/deals/user-defined-fields/events/on-crm-deal-user-field-set-enum-values

Event on changing the set of values for a custom list-type field onCrmDealUserFieldSetEnumValues | Bitrix24 REST API and Marketplace Applications
Event on changing the set of values for a custom list-type field onCrmDealUserFieldSetEnumValues
Event on changing the set of values for a custom list-type field onCrmDealUserFieldSetEnumValues
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
onCrmDealUserFieldSetEnumValues
will trigger when the set of values for a custom list-type field is changed.
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMDEALUSERFIELDSETENUMVALUES"
,
"event_handler_id"
:
"665"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"6947"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1736930561"
}
}
,
"ts"
:
"1736944167"
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
ONCRMDEALUSERFIELDSETENUMVALUES
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated list-type field.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the updated list-type field.
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
Identifier of the custom list-type field
ENTITY_ID
string
Symbolic identifier of the object for which the list-type field was updated. In this case —
CRM_DEAL
FIELD_NAME
string
Name of the updated custom list-type field
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
Event when adding a custom field onCrmDealUserFieldAdd
Event onCrmDealUserFieldDelete
Event on user field change onCrmDealUserFieldUpdate
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Custom Field
Next
Overview of methods

---

