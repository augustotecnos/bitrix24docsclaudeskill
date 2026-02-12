---
description: 'Tutorials: Business process automation'
methods:
- bizproc.activity.add
- bizproc.robot.add
- bizproc.robot.delete
- bizproc.robot.list
- bizproc.task.list
- bizproc.workflow.instances
- bizproc.workflow.kill
- bizproc.workflow.terminate
- crm.deal.get
- crm.deal.productrows.get
- crm.invoice.add
- crm.lead.get
- crm.lead.productrows.get
- crm.persontype.list
- placement.call
- user.get
pages: 6
title: 'Tutorials: Business process automation'
---
# Tutorials: Business process automation
> Tutorials: Business process automation
> **6 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Typical use-cases and scenarios for REST API in workflows and Automation rules](#typical-use-cases-and-scenarios-for-rest-api-in-wo)
- [How to Add an Action to Create an Invoice Based on a Lead or Deal](#how-to-add-an-action-to-create-an-invoice-based-on)
- [How to Embed Your UI in Robot Parameters](#how-to-embed-your-ui-in-robot-parameters)
- [How to Embed Your UI in Robot Parameters](#how-to-embed-your-ui-in-robot-parameters)
- [How to Complete Business Processes of a Terminated Employee](#how-to-complete-business-processes-of-a-terminated)
- [How to Mass Finish Workflows with Date Filter](#how-to-mass-finish-workflows-with-date-filter)

---

## Typical use-cases and scenarios for REST API in workflows and Automation rules

**Source:** https://apidocs.bitrix24.com/tutorials/bizproc/index

Typical use-cases and scenarios for REST API in workflows and Automation rules | Bitrix24 REST API and Marketplace Applications
Typical use-cases and scenarios for REST API in workflows and Automation rules
Typical use-cases and scenarios for REST API in workflows and Automation rules
In this section, you will find examples for solving typical tasks related to workflows and CRM Automation rules:
How to Add an Action to Create an Invoice Based on a Lead or Deal
How to Embed Your UI in Robot Parameters
How to Complete Business Processes of a Terminated Employee
How to Mass Finish Workflows with Date Filter
Was the article helpful?
Yes
No
Previous
Set up a delivery service for CRM
Next
How to add an action to create an invoice based on

---

## How to Add an Action to Create an Invoice Based on a Lead or Deal

**Source:** https://apidocs.bitrix24.com/tutorials/bizproc/activity

How to Add an Action to Create an Invoice Based on a Lead or Deal | Bitrix24 REST API and Marketplace Applications
How to Add an Action to Create an Invoice Based on a Lead or Deal
How to Add an Action to Create an Invoice Based on a Lead or Deal
Action Registration File
Action Handler
This example is universal for workflow actions and Automation rules. The only difference is the method:
bizproc.activity.add
— create a workflow action
bizproc.robot.add
— create an Automation rule
In the example code, the method
bizproc.activity.add
is used. If you want to create an Automation rule, replace the method with
bizproc.robot.add
.
To use the example, configure the
CRest
class and include the
crest.php
file in the files where this class is used. More details in the article
How to Use Examples in Documentation
.
Action Registration File
Action Registration File
How to Use Examples in Documentation
Replace the path
$handlerUrl
with your path to the action handler.
JS
PHP
BX24
.
callMethod
(
"bizproc.activity.add"
,
{
"CODE"
:
"activityAccount"
,
"HANDLER"
:
"https://yourdomain.com/handler.php"
,
"AUTH_USER_ID"
:
1
,
"NAME"
:
"ActivityAccount"
,
"DESCRIPTION"
:
"description"
,
"PROPERTIES"
: {
"account_title"
: {
"Name"
:
"Format account title"
,
"Description"
:
""
,
"Type"
:
"string"
,
"Required"
:
"Y"
,
"Multiple"
:
"N"
,
"Default"
:
"Account title"
},
"my_company_id"
: {
"Name"
:
"My Company id"
,
"Description"
:
""
,
"Type"
:
"int"
,
"Required"
:
"Y"
,
"Multiple"
:
"N"
,
"Default"
:
"1"
},
"pay_system_id"
: {
"Name"
:
"Pay system id"
,
"Description"
:
""
,
"Type"
:
"int"
,
"Required"
:
"Y"
,
"Multiple"
:
"N"
,
"Default"
:
"1"
}
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
<?php
$handlerUrl
=
'https://yourdomain.com/handler.php'
;
$result
=
CRest
::
call
(
'bizproc.activity.add'
,
[
'CODE'
=>
'activityAccount'
,
'HANDLER'
=>
$handlerUrl
,
'AUTH_USER_ID'
=>
1
,
'NAME'
=>
'ActivityAccount'
,
'DESCRIPTION'
=>
'description'
,
'PROPERTIES'
=> [
'account_title'
=> [
'Name'
=>
'Format account title'
,
'Description'
=>
''
,
'Type'
=>
'string'
,
'Required'
=>
'Y'
,
'Multiple'
=>
'N'
,
'Default'
=>
'Account title'
,
],
'my_company_id'
=> [
'Name'
=>
'My Company id'
,
'Description'
=>
''
,
'Type'
=>
'int'
,
'Required'
=>
'Y'
,
'Multiple'
=>
'N'
,
'Default'
=>
'1'
,
],
'pay_system_id'
=> [
'Name'
=>
'Pay system id'
,
'Description'
=>
''
,
'Type'
=>
'int'
,
'Required'
=>
'Y'
,
'Multiple'
=>
'N'
,
'Default'
=>
'1'
,
],
]
]
);
?>
Action Handler
Action Handler
How to Use Examples in Documentation
<?php
$my_company_id
=
intval
(
$_REQUEST
[
'properties'
][
'my_company_id'
]);
$pay_system_id
=
intval
(
$_REQUEST
[
'properties'
][
'pay_system_id'
]);
//some in CRest::call('sale.paysystem.list')
$account_title
=
htmlspecialchars
(
$_REQUEST
[
'properties'
][
'account_title'
]);
$arDocument
=
$_REQUEST
[
'document_id'
];
$iDealID
=
0
;
$iLeadID
=
0
;
if
(
is_array
(
$arDocument
))
{
foreach
(
$arDocument
as
$param
)
{
//search id
if
(
strpos
(
$param
,
'DEAL_'
) !==
false
)
{
$iDealID
=
intval
(
substr
(
$param
,
strlen
(
'DEAL_'
)));
break
;
}
elseif
(
strpos
(
$param
,
'LEAD_'
) !==
false
)
{
$iLeadID
=
intval
(
substr
(
$param
,
strlen
(
'LEAD_'
)));
break
;
}
}
}
if
(
$iDealID
>
0
)
{
$result
=
CRest
::
call
(
'crm.deal.get'
,
[
'id'
=>
$iDealID
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
$arData
=
$result
[
'result'
];
$resultProduct
=
CRest
::
call
(
'crm.deal.productrows.get'
,
[
'id'
=>
$iDealID
]
);
}
}
elseif
(
$iLeadID
>
0
)
{
$result
=
CRest
::
call
(
'crm.lead.get'
,
[
'id'
=>
$iLeadID
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
$arData
=
$result
[
'result'
];
$resultProduct
=
CRest
::
call
(
'crm.lead.productrows.get'
,
[
'id'
=>
$iLeadID
]
);
}
}
if
(!
empty
(
$arData
[
'COMPANY_ID'
]) || !
empty
(
$arData
[
'CONTACT_ID'
]))
{
if
(
empty
(
$resultProduct
[
'result'
]))
{
//if the deal or lead has no products
$resultProduct
[
'result'
][] = [
'ID'
=>
0
,
'PRODUCT_ID'
=>
0
,
'PRODUCT_NAME'
=>
$account_title
,
'QUANTITY'
=>
1
,
'PRICE'
=> (
$arData
[
'OPPORTUNITY'
])?:
0
,
];
}
$arProduct
= [];
foreach
(
$resultProduct
[
'result'
]
as
$product
)
{
$arProduct
[] = [
'ID'
=>
$product
[
'ID'
],
'PRODUCT_ID'
=>
$product
[
'PRODUCT_ID'
],
'PRODUCT_NAME'
=>
$product
[
'PRODUCT_NAME'
],
'QUANTITY'
=>
$product
[
'QUANTITY'
],
'PRICE'
=>
$product
[
'PRICE'
]
];
}
$resultInvoice
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
$account_title
,
'UF_COMPANY_ID'
=>
$arData
[
'COMPANY_ID'
],
'UF_CONTACT_ID'
=>
$arData
[
'CONTACT_ID'
],
'UF_DEAL_ID'
=>
$arData
[
'ID'
],
'UF_MYCOMPANY_ID'
=>
$my_company_id
,
'PERSON_TYPE_ID'
=> (
$arData
[
'COMPANY_ID'
] >
0
) ?
1
:
2
,
//1 is company, 2 is contact in CRest::call('crm.persontype.list')
'PAY_SYSTEM_ID'
=>
$pay_system_id
,
"STATUS_ID"
=>
"N"
,
'DATE_INSERT'
=>
date
(DATE_ATOM),
'DATE_BILL'
=>
date
(DATE_ATOM),
'DATE_PAY_BEFORE'
=>
date
(DATE_ATOM,
time
() +
3600
*
24
*
20
),
//20 day pay
'PRODUCT_ROWS'
=>
$arProduct
,
]
]
);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
Typical use-cases for REST API in workflows and Automation rules
Next
How to embed your UI in the Automation rule parameters

---

## How to Embed Your UI in Robot Parameters

**Source:** https://apidocs.bitrix24.com/tutorials/bizproc/setting-robot

How to Embed Your UI in Robot Parameters | Bitrix24 REST API and Marketplace Applications
Implementation Using an Application Example
How to Embed Your UI in Robot Parameters
Implementation Using an Application Example
Full Application Code
In
Bitrix24
, you can configure a robot and workflow action using the application interface. This is implemented through the standard
widget embedding mechanism
. It is available in the on-premise version starting from
20.0.600
of the
Business Processes
module.
Implementation Using an Application Example
Implementation Using an Application Example
Let's consider the implementation using a specific application example; the complete code for the application is presented
below
.
In this example, the application adds a robot that has 2 parameters of type
string
.
How to Use Examples in Documentation
JS
PHP
var
params = {
'CODE'
:
'robot'
,
'HANDLER'
:
'http://handler.com'
,
'AUTH_USER_ID'
:
1
,
'NAME'
:
'Example of Robot Embedding'
,
'USE_PLACEMENT'
:
'Y'
,
'PLACEMENT_HANDLER'
:
'http://handler.com'
,
'PROPERTIES'
: {
'string'
: {
'Name'
:
'Parameter 1'
,
'Type'
:
'string'
},
'stringm'
: {
'Name'
:
'Parameter 2'
,
'Type'
:
'string'
,
'Multiple'
:
'Y'
,
'Default'
: [
'value 1'
,
'value 2'
]
},
}
};
BX24
.
callMethod
(
'bizproc.robot.add'
,
params,
function
(
result
)
{
if
(result.
error
())
alert
(
"Error: "
+ result.
error
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
'bizproc.robot.add'
,
[
'CODE'
=>
'robot'
,
'HANDLER'
=>
'http://handler.com'
,
'AUTH_USER_ID'
=>
1
,
'NAME'
=>
'Example of Robot Embedding'
,
'USE_PLACEMENT'
=>
'Y'
,
'PLACEMENT_HANDLER'
=>
'http://handler.com'
,
'PROPERTIES'
=> [
'string'
=> [
'Name'
=>
'Parameter 1'
,
'Type'
=>
'string'
],
'stringm'
=> [
'Name'
=>
'Parameter 2'
,
'Type'
=>
'string'
,
'Multiple'
=>
'Y'
,
'Default'
=> [
'value 1'
,
'value 2'
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
To allow parameters to be configured through the application, when adding the robot, you need to pass the parameters
USE_PLACEMENT=Y
and the handler
PLACEMENT_HANDLER
.
Next, you need to write the embedding handler, which will render the parameters and save their values. For this, you need to pass the following data in
PLACEMENT_OPTIONS
:
code
— the code of your robot upon registration
activity_name
— the identifier of the action in the workflow template
properties
— a list of properties and their descriptions
current_values
— the current values of the properties
document_type
— the type of document for which the configuration is being made
document_fields
— a list of document fields
template
— a list of available template fields. In the on-premise version of
Bitrix24
, it is available starting from version
24.200.0
For the
template
parameter, the following elements are available:
parameters
— a list of template parameters
variables
— a list of template variables
constants
— a list of template constants
global_variables
— a list of global variables
global_constants
— a list of global constants
return_activities
— a list of actions or robots that generate additional results
The structure of properties in these lists is unified:
{
Id: string, identifier (code) of the property
Type: string, identifier of the property type
Name: string, title
Description: string, description
Multiple: boolean, whether it is a multiple property
Required: boolean, whether it is a required property
Options: mixed, depends on the property type
Settings: list of settings, depends on the property type
Default: mixed, default value for the property
}
The
return_activities
list consists of a list of actions that return results and their properties. It has the structure:
{
Id: string, identifier of the action in the template
Type: string, type of action
Title: string, title of the action in the template
Return: list, available properties
}
The data arrives in the application in the following format:
$array
= [
'code'
=>
'robot'
,
'activity_name'
=>
'A72788_31169_37133_27365'
,
'properties'
=> [
'string'
=> [
'NAME'
=>
'Parameter 1'
,
'TYPE'
=>
'string'
],
'stringm'
=> [
'NAME'
=>
'Parameter 2'
,
'TYPE'
=>
'string'
,
'MULTIPLE'
=>
'Y'
,
'DEFAULT'
=> [
'value 1'
,
'value 2'
]
]
],
'current_values'
=> [
'string'
=>
1
,
'stringm'
=> [
2
]
],
'document_type'
=> [
'crm'
,
'CCrmDocumentDeal'
,
'DEAL'
],
'document_fields'
=> [
'ID'
=> [
'Name'
=>
'ID'
,
'Type'
=>
'int'
,
'Filterable'
=>
1
,
'Editable'
=>
false
,
'Required'
=>
false
,
'BaseType'
=>
'int'
],
'TITLE'
=> [
'Name'
=>
'Title'
,
'Type'
=>
'string'
,
'Filterable'
=>
1
,
'Editable'
=>
1
,
'Required'
=>
1
,
'BaseType'
=>
'string'
],
// ...
],
'template'
=> [
'parameters'
=> [],
'variables'
=> [
[
'Id'
=>
'Approver'
,
'Type'
=>
'user'
,
'Name'
=>
'Approver'
,
'Description'
=>
''
,
'Multiple'
=>
1
,
'Required'
=>
false
,
'Options'
=>
''
,
'Settings'
=>
''
,
'Default'
=>
''
]
],
'constants'
=> [
[
'Id'
=>
'Manager'
,
'Type'
=>
'user'
,
'Name'
=>
'Who Approves'
,
'Description'
=>
'director or deputy'
,
'Multiple'
=>
1
,
'Required'
=>
1
,
'Options'
=>
''
,
'Settings'
=>
''
,
'Default'
=> [
'user_4'
]
]
],
'global_variables'
=> [
[
'Id'
=>
'Variable1666332520655'
,
'Type'
=>
'user'
,
'Name'
=>
'test u'
,
'Description'
=>
''
,
'Multiple'
=>
1
,
'Required'
=>
false
,
'Options'
=>
''
,
'Settings'
=>
''
,
'Default'
=> [
'user_1'
]
]
],
'global_constants'
=> [
[
'Id'
=>
'Constant1666332578194'
,
'Type'
=>
'user'
,
'Name'
=>
'test u 1'
,
'Description'
=>
''
,
'Multiple'
=>
false
,
'Required'
=>
false
,
'Options'
=>
''
,
'Settings'
=>
''
,
'Default'
=>
'user_1'
]
],
'return_activities'
=> [
[
'Id'
=>
'A71026_84473_24610_19894'
,
'Type'
=>
'LogActivity'
,
'Title'
=>
'Log to Report'
,
'Return'
=> [
[
'Id'
=>
'Report'
,
'Name'
=>
'Report'
,
'Type'
=>
'string'
]
]
],
[
'Id'
=>
'A58853_60082_34258_61777'
,
'Type'
=>
'ApproveActivity'
,
'Title'
=>
'Approval'
,
'Return'
=> [
[
'Id'
=>
'TaskId'
,
'Name'
=>
'ID'
,
'Type'
=>
'int'
],
[
'Id'
=>
'Comments'
,
'Name'
=>
'Comments'
,
'Type'
=>
'string'
],
[
'Id'
=>
'VotedCount'
,
'Name'
=>
'Number of Votes'
,
'Type'
=>
'int'
],
[
'Id'
=>
'TotalCount'
,
'Name'
=>
'Total Votes Required'
,
'Type'
=>
'int'
],
[
'Id'
=>
'VotedPercent'
,
'Name'
=>
'Voting Percentage'
,
'Type'
=>
'int'
],
[
'Id'
=>
'ApprovedPercent'
,
'Name'
=>
'Approval Percentage'
,
'Type'
=>
'int'
],
[
'Id'
=>
'NotApprovedPercent'
,
'Name'
=>
'Rejection Percentage'
,
'Type'
=>
'int'
],
[
'Id'
=>
'ApprovedCount'
,
'Name'
=>
'Number Approved'
,
'Type'
=>
'int'
],
[
'Id'
=>
'NotApprovedCount'
,
'Name'
=>
'Number Rejected'
,
'Type'
=>
'int'
],
[
'Id'
=>
'LastApprover'
,
'Name'
=>
'Last Voter'
,
'Type'
=>
'user'
],
[
'Id'
=>
'LastApproverComment'
,
'Name'
=>
'Last Voter Comment'
,
'Type'
=>
'string'
],
[
'Id'
=>
'UserApprovers'
,
'Name'
=>
'Approved by Users'
,
'Type'
=>
'user'
],
[
'Id'
=>
'Approvers'
,
'Name'
=>
'Approved by Users (text)'
,
'Type'
=>
'string'
],
[
'Id'
=>
'UserRejecters'
,
'Name'
=>
'Rejected by Users'
,
'Type'
=>
'user'
],
[
'Id'
=>
'Rejecters'
,
'Name'
=>
'Rejected by Users (text)'
,
'Type'
=>
'string'
],
[
'Id'
=>
'IsTimeout'
,
'Name'
=>
'Automatic Rejection'
,
'Type'
=>
'int'
]
]
]
]
]
];
Next, you need to create the layout and learn how to save parameters directly in the Robot. For this, you can use the
setPropertyValue
function, which is available through
BX24.placement.call
.
BX24
.
placement
.
call
(
'setPropertyValue'
,
{
string
:
'test string'
}
)
As parameters, the
ID
of the property and values are passed. You can pass multiple property values.
BX24
.
placement
.
call
(
'setPropertyValue'
,
{
string
:
'test string'
,
stringm
: [
'test2'
,
'test3'
]
}
)
Then the user saves the robot as usual.
The white area is the embedding, the application frame.
Full Application Code
Full Application Code
How to Use Examples in Documentation
<?php
header
(
'Content-Type: text/html; charset=UTF-8'
);
$protocol
=
$_SERVER
[
'SERVER_PORT'
] ==
'443'
?
'https'
:
'http'
;
$host
=
explode
(
':'
,
$_SERVER
[
'HTTP_HOST'
]);
$host
=
$host
[
0
];
define
(
'BP_APP_HANDLER'
,
$protocol
.
'://'
.
$host
.
explode
(
'?'
,
$_SERVER
[
'REQUEST_URI'
])[
0
]);
?>
<!DOCTYPE html>
<html lang=
"en"
>
<head>
<meta charset=
"UTF-8"
>
<title></title>
</head>
<body>
<link rel=
"stylesheet"
href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
integrity=
"sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T"
crossorigin=
"anonymous"
>
<script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"
integrity=
"sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM"
crossorigin=
"anonymous"
></script>
<script src=
"//api.bitrix24.com/api/v1/"
></script>
<?
if
(!
isset
(
$_POST
[
'PLACEMENT'
]) ||
$_POST
[
'PLACEMENT'
] ===
'DEFAULT'
):
?>
<h1>Robot Embedding</h1>
<div
class
="
container
-
fluid
">
<
div
class
="
container
-
fluid
">
<
h2
>
Robot
</
h2
>
<
button
onclick
="
installRobot
();"
class
="
btn
btn
-
primary
">
Install
</
button
> –
<
button
onclick
="
uninstallRobot
();"
class
="
btn
btn
-
danger
">
Remove
</
button
>
</
div
>
<
hr
/>
<
div
class
="
container
-
fluid
">
<
button
onclick
="
getList
();"
class
="
btn
btn
-
light
">
Get
List
of
Installed
Robots
</
button
>
</
div
>
</
div
>
<
script
type
="
text
/
javascript
">
document
.
body
.
style
.
display
= '
none
';
BX24
.
init
(
function
()
{
document.body.style.display =
''
;
});
function
installRobot
(
)
{
var
params = {
'CODE'
:
'robot'
,
'HANDLER'
:
'<?=BP_APP_HANDLER?>'
,
'AUTH_USER_ID'
:
1
,
'NAME'
:
'Example of Robot Embedding'
,
'USE_PLACEMENT'
:
'Y'
,
'PLACEMENT_HANDLER'
:
'<?=BP_APP_HANDLER?>'
,
'PROPERTIES'
: {
'string'
: {
'Name'
:
'Parameter 1'
,
'Type'
:
'string'
},
'stringm'
: {
'Name'
:
'Parameter 2'
,
'Type'
:
'string'
,
'Multiple'
:
'Y'
,
'Default'
: [
'value 1'
,
'value 2'
]
},
}
};
BX24.
callMethod
(
'bizproc.robot.add'
,
params,
function(result)
{
if
(result.
error
())
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Successfully"
);
}
);
}
function
uninstallRobot
(
)
{
BX24.
callMethod
(
'bizproc.robot.delete'
,
{
'CODE'
:
'robot'
},
function(result)
{
if
(result.
error
())
alert
(
'Error: '
+ result.
error
());
else
alert
(
"Successfully"
);
}
);
}
function
getList
(
)
{
BX24.
callMethod
(
'bizproc.robot.list'
,
{},
function(result)
{
if
(result.
error
())
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Codes of Installed Robots: "
+ result.
data
().
join
(
', '
));
}
);
}
</script>
<?php
else
:
?>
<form name=
"props"
class
="
container
-
fluid
">
<?
php
$
options
=
json_decode
($
_POST
['
PLACEMENT_OPTIONS
'],
true
);
foreach
($
options
['
properties
']
as
$
id
=> $
property
)
{
$multiple
=
isset
(
$property
[
'MULTIPLE'
]) &&
$property
[
'MULTIPLE'
] ===
'Y'
;
$val
= (
array
)
$options
[
'current_values'
][
$id
];
if
(!
$val
)
{
$val
[] =
''
;
}
if
(
$multiple
)
{
$val
[] =
''
;
}
$name
=
$multiple
?
$id
.
'[]'
:
$id
;
?>
<div
class
="
form
-
group
">
<
label
><?=
htmlspecialchars
($
property
['
NAME
'])?>:</
label
>
<?
foreach
($
val
as
$
v
):?>
<
p
><
input
name
="<?=$
name
?>"
value
="<?=
htmlspecialchars
((
string
)$
v
)?>"
class
="
form
-
control
"
onchange
="
setPropertyValue
('<?=$
id
?>',
this
.
name
, <?=(
int
)$
multiple
?>)"></
p
>
<?
endforeach
;?>
</
div
>
<?
php
}
?>
<
script
>
function
setPropertyValue
(
name
,
inputName
,
multiple
)
{
var
form =
new
FormData
(document.forms.props);
var
value = multiple? form.
getAll
(inputName) : form.
get
(inputName);
var
params = {};
params[name] = value;
BX24.placement.
call
(
'setPropertyValue'
,
params
)
}
</script>
</form>
<?php
endif
;
?>
</body>
</html>
Copied
Was the article helpful?
Yes
No
Previous
How to add an action to create an invoice based on
Next
How to terminate workflows of a terminated employee

---

## How to Embed Your UI in Robot Parameters

**Source:** https://apidocs.bitrix24.com/tutorials/bizproc/setting-robot

How to Embed Your UI in Robot Parameters | Bitrix24 REST API and Marketplace Applications
Implementation Using an Application Example
How to Embed Your UI in Robot Parameters
Implementation Using an Application Example
Full Application Code
In
Bitrix24
, you can configure a robot and workflow action using the application interface. This is implemented through the standard
widget embedding mechanism
. It is available in the on-premise version starting from
20.0.600
of the
Business Processes
module.
Implementation Using an Application Example
Implementation Using an Application Example
Let's consider the implementation using a specific application example; the complete code for the application is presented
below
.
In this example, the application adds a robot that has 2 parameters of type
string
.
How to Use Examples in Documentation
JS
PHP
var
params = {
'CODE'
:
'robot'
,
'HANDLER'
:
'http://handler.com'
,
'AUTH_USER_ID'
:
1
,
'NAME'
:
'Example of Robot Embedding'
,
'USE_PLACEMENT'
:
'Y'
,
'PLACEMENT_HANDLER'
:
'http://handler.com'
,
'PROPERTIES'
: {
'string'
: {
'Name'
:
'Parameter 1'
,
'Type'
:
'string'
},
'stringm'
: {
'Name'
:
'Parameter 2'
,
'Type'
:
'string'
,
'Multiple'
:
'Y'
,
'Default'
: [
'value 1'
,
'value 2'
]
},
}
};
BX24
.
callMethod
(
'bizproc.robot.add'
,
params,
function
(
result
)
{
if
(result.
error
())
alert
(
"Error: "
+ result.
error
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
'bizproc.robot.add'
,
[
'CODE'
=>
'robot'
,
'HANDLER'
=>
'http://handler.com'
,
'AUTH_USER_ID'
=>
1
,
'NAME'
=>
'Example of Robot Embedding'
,
'USE_PLACEMENT'
=>
'Y'
,
'PLACEMENT_HANDLER'
=>
'http://handler.com'
,
'PROPERTIES'
=> [
'string'
=> [
'Name'
=>
'Parameter 1'
,
'Type'
=>
'string'
],
'stringm'
=> [
'Name'
=>
'Parameter 2'
,
'Type'
=>
'string'
,
'Multiple'
=>
'Y'
,
'Default'
=> [
'value 1'
,
'value 2'
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
To allow parameters to be configured through the application, when adding the robot, you need to pass the parameters
USE_PLACEMENT=Y
and the handler
PLACEMENT_HANDLER
.
Next, you need to write the embedding handler, which will render the parameters and save their values. For this, you need to pass the following data in
PLACEMENT_OPTIONS
:
code
— the code of your robot upon registration
activity_name
— the identifier of the action in the workflow template
properties
— a list of properties and their descriptions
current_values
— the current values of the properties
document_type
— the type of document for which the configuration is being made
document_fields
— a list of document fields
template
— a list of available template fields. In the on-premise version of
Bitrix24
, it is available starting from version
24.200.0
For the
template
parameter, the following elements are available:
parameters
— a list of template parameters
variables
— a list of template variables
constants
— a list of template constants
global_variables
— a list of global variables
global_constants
— a list of global constants
return_activities
— a list of actions or robots that generate additional results
The structure of properties in these lists is unified:
{
Id: string, identifier (code) of the property
Type: string, identifier of the property type
Name: string, title
Description: string, description
Multiple: boolean, whether it is a multiple property
Required: boolean, whether it is a required property
Options: mixed, depends on the property type
Settings: list of settings, depends on the property type
Default: mixed, default value for the property
}
The
return_activities
list consists of a list of actions that return results and their properties. It has the structure:
{
Id: string, identifier of the action in the template
Type: string, type of action
Title: string, title of the action in the template
Return: list, available properties
}
The data arrives in the application in the following format:
$array
= [
'code'
=>
'robot'
,
'activity_name'
=>
'A72788_31169_37133_27365'
,
'properties'
=> [
'string'
=> [
'NAME'
=>
'Parameter 1'
,
'TYPE'
=>
'string'
],
'stringm'
=> [
'NAME'
=>
'Parameter 2'
,
'TYPE'
=>
'string'
,
'MULTIPLE'
=>
'Y'
,
'DEFAULT'
=> [
'value 1'
,
'value 2'
]
]
],
'current_values'
=> [
'string'
=>
1
,
'stringm'
=> [
2
]
],
'document_type'
=> [
'crm'
,
'CCrmDocumentDeal'
,
'DEAL'
],
'document_fields'
=> [
'ID'
=> [
'Name'
=>
'ID'
,
'Type'
=>
'int'
,
'Filterable'
=>
1
,
'Editable'
=>
false
,
'Required'
=>
false
,
'BaseType'
=>
'int'
],
'TITLE'
=> [
'Name'
=>
'Title'
,
'Type'
=>
'string'
,
'Filterable'
=>
1
,
'Editable'
=>
1
,
'Required'
=>
1
,
'BaseType'
=>
'string'
],
// ...
],
'template'
=> [
'parameters'
=> [],
'variables'
=> [
[
'Id'
=>
'Approver'
,
'Type'
=>
'user'
,
'Name'
=>
'Approver'
,
'Description'
=>
''
,
'Multiple'
=>
1
,
'Required'
=>
false
,
'Options'
=>
''
,
'Settings'
=>
''
,
'Default'
=>
''
]
],
'constants'
=> [
[
'Id'
=>
'Manager'
,
'Type'
=>
'user'
,
'Name'
=>
'Who Approves'
,
'Description'
=>
'director or deputy'
,
'Multiple'
=>
1
,
'Required'
=>
1
,
'Options'
=>
''
,
'Settings'
=>
''
,
'Default'
=> [
'user_4'
]
]
],
'global_variables'
=> [
[
'Id'
=>
'Variable1666332520655'
,
'Type'
=>
'user'
,
'Name'
=>
'test u'
,
'Description'
=>
''
,
'Multiple'
=>
1
,
'Required'
=>
false
,
'Options'
=>
''
,
'Settings'
=>
''
,
'Default'
=> [
'user_1'
]
]
],
'global_constants'
=> [
[
'Id'
=>
'Constant1666332578194'
,
'Type'
=>
'user'
,
'Name'
=>
'test u 1'
,
'Description'
=>
''
,
'Multiple'
=>
false
,
'Required'
=>
false
,
'Options'
=>
''
,
'Settings'
=>
''
,
'Default'
=>
'user_1'
]
],
'return_activities'
=> [
[
'Id'
=>
'A71026_84473_24610_19894'
,
'Type'
=>
'LogActivity'
,
'Title'
=>
'Log to Report'
,
'Return'
=> [
[
'Id'
=>
'Report'
,
'Name'
=>
'Report'
,
'Type'
=>
'string'
]
]
],
[
'Id'
=>
'A58853_60082_34258_61777'
,
'Type'
=>
'ApproveActivity'
,
'Title'
=>
'Approval'
,
'Return'
=> [
[
'Id'
=>
'TaskId'
,
'Name'
=>
'ID'
,
'Type'
=>
'int'
],
[
'Id'
=>
'Comments'
,
'Name'
=>
'Comments'
,
'Type'
=>
'string'
],
[
'Id'
=>
'VotedCount'
,
'Name'
=>
'Number of Votes'
,
'Type'
=>
'int'
],
[
'Id'
=>
'TotalCount'
,
'Name'
=>
'Total Votes Required'
,
'Type'
=>
'int'
],
[
'Id'
=>
'VotedPercent'
,
'Name'
=>
'Voting Percentage'
,
'Type'
=>
'int'
],
[
'Id'
=>
'ApprovedPercent'
,
'Name'
=>
'Approval Percentage'
,
'Type'
=>
'int'
],
[
'Id'
=>
'NotApprovedPercent'
,
'Name'
=>
'Rejection Percentage'
,
'Type'
=>
'int'
],
[
'Id'
=>
'ApprovedCount'
,
'Name'
=>
'Number Approved'
,
'Type'
=>
'int'
],
[
'Id'
=>
'NotApprovedCount'
,
'Name'
=>
'Number Rejected'
,
'Type'
=>
'int'
],
[
'Id'
=>
'LastApprover'
,
'Name'
=>
'Last Voter'
,
'Type'
=>
'user'
],
[
'Id'
=>
'LastApproverComment'
,
'Name'
=>
'Last Voter Comment'
,
'Type'
=>
'string'
],
[
'Id'
=>
'UserApprovers'
,
'Name'
=>
'Approved by Users'
,
'Type'
=>
'user'
],
[
'Id'
=>
'Approvers'
,
'Name'
=>
'Approved by Users (text)'
,
'Type'
=>
'string'
],
[
'Id'
=>
'UserRejecters'
,
'Name'
=>
'Rejected by Users'
,
'Type'
=>
'user'
],
[
'Id'
=>
'Rejecters'
,
'Name'
=>
'Rejected by Users (text)'
,
'Type'
=>
'string'
],
[
'Id'
=>
'IsTimeout'
,
'Name'
=>
'Automatic Rejection'
,
'Type'
=>
'int'
]
]
]
]
]
];
Next, you need to create the layout and learn how to save parameters directly in the Robot. For this, you can use the
setPropertyValue
function, which is available through
BX24.placement.call
.
BX24
.
placement
.
call
(
'setPropertyValue'
,
{
string
:
'test string'
}
)
As parameters, the
ID
of the property and values are passed. You can pass multiple property values.
BX24
.
placement
.
call
(
'setPropertyValue'
,
{
string
:
'test string'
,
stringm
: [
'test2'
,
'test3'
]
}
)
Then the user saves the robot as usual.
The white area is the embedding, the application frame.
Full Application Code
Full Application Code
How to Use Examples in Documentation
<?php
header
(
'Content-Type: text/html; charset=UTF-8'
);
$protocol
=
$_SERVER
[
'SERVER_PORT'
] ==
'443'
?
'https'
:
'http'
;
$host
=
explode
(
':'
,
$_SERVER
[
'HTTP_HOST'
]);
$host
=
$host
[
0
];
define
(
'BP_APP_HANDLER'
,
$protocol
.
'://'
.
$host
.
explode
(
'?'
,
$_SERVER
[
'REQUEST_URI'
])[
0
]);
?>
<!DOCTYPE html>
<html lang=
"en"
>
<head>
<meta charset=
"UTF-8"
>
<title></title>
</head>
<body>
<link rel=
"stylesheet"
href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
integrity=
"sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T"
crossorigin=
"anonymous"
>
<script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"
integrity=
"sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM"
crossorigin=
"anonymous"
></script>
<script src=
"//api.bitrix24.com/api/v1/"
></script>
<?
if
(!
isset
(
$_POST
[
'PLACEMENT'
]) ||
$_POST
[
'PLACEMENT'
] ===
'DEFAULT'
):
?>
<h1>Robot Embedding</h1>
<div
class
="
container
-
fluid
">
<
div
class
="
container
-
fluid
">
<
h2
>
Robot
</
h2
>
<
button
onclick
="
installRobot
();"
class
="
btn
btn
-
primary
">
Install
</
button
> –
<
button
onclick
="
uninstallRobot
();"
class
="
btn
btn
-
danger
">
Remove
</
button
>
</
div
>
<
hr
/>
<
div
class
="
container
-
fluid
">
<
button
onclick
="
getList
();"
class
="
btn
btn
-
light
">
Get
List
of
Installed
Robots
</
button
>
</
div
>
</
div
>
<
script
type
="
text
/
javascript
">
document
.
body
.
style
.
display
= '
none
';
BX24
.
init
(
function
()
{
document.body.style.display =
''
;
});
function
installRobot
(
)
{
var
params = {
'CODE'
:
'robot'
,
'HANDLER'
:
'<?=BP_APP_HANDLER?>'
,
'AUTH_USER_ID'
:
1
,
'NAME'
:
'Example of Robot Embedding'
,
'USE_PLACEMENT'
:
'Y'
,
'PLACEMENT_HANDLER'
:
'<?=BP_APP_HANDLER?>'
,
'PROPERTIES'
: {
'string'
: {
'Name'
:
'Parameter 1'
,
'Type'
:
'string'
},
'stringm'
: {
'Name'
:
'Parameter 2'
,
'Type'
:
'string'
,
'Multiple'
:
'Y'
,
'Default'
: [
'value 1'
,
'value 2'
]
},
}
};
BX24.
callMethod
(
'bizproc.robot.add'
,
params,
function(result)
{
if
(result.
error
())
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Successfully"
);
}
);
}
function
uninstallRobot
(
)
{
BX24.
callMethod
(
'bizproc.robot.delete'
,
{
'CODE'
:
'robot'
},
function(result)
{
if
(result.
error
())
alert
(
'Error: '
+ result.
error
());
else
alert
(
"Successfully"
);
}
);
}
function
getList
(
)
{
BX24.
callMethod
(
'bizproc.robot.list'
,
{},
function(result)
{
if
(result.
error
())
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Codes of Installed Robots: "
+ result.
data
().
join
(
', '
));
}
);
}
</script>
<?php
else
:
?>
<form name=
"props"
class
="
container
-
fluid
">
<?
php
$
options
=
json_decode
($
_POST
['
PLACEMENT_OPTIONS
'],
true
);
foreach
($
options
['
properties
']
as
$
id
=> $
property
)
{
$multiple
=
isset
(
$property
[
'MULTIPLE'
]) &&
$property
[
'MULTIPLE'
] ===
'Y'
;
$val
= (
array
)
$options
[
'current_values'
][
$id
];
if
(!
$val
)
{
$val
[] =
''
;
}
if
(
$multiple
)
{
$val
[] =
''
;
}
$name
=
$multiple
?
$id
.
'[]'
:
$id
;
?>
<div
class
="
form
-
group
">
<
label
><?=
htmlspecialchars
($
property
['
NAME
'])?>:</
label
>
<?
foreach
($
val
as
$
v
):?>
<
p
><
input
name
="<?=$
name
?>"
value
="<?=
htmlspecialchars
((
string
)$
v
)?>"
class
="
form
-
control
"
onchange
="
setPropertyValue
('<?=$
id
?>',
this
.
name
, <?=(
int
)$
multiple
?>)"></
p
>
<?
endforeach
;?>
</
div
>
<?
php
}
?>
<
script
>
function
setPropertyValue
(
name
,
inputName
,
multiple
)
{
var
form =
new
FormData
(document.forms.props);
var
value = multiple? form.
getAll
(inputName) : form.
get
(inputName);
var
params = {};
params[name] = value;
BX24.placement.
call
(
'setPropertyValue'
,
params
)
}
</script>
</form>
<?php
endif
;
?>
</body>
</html>
Copied
Was the article helpful?
Yes
No
Previous
How to add an action to create an invoice based on
Next
How to terminate workflows of a terminated employee

---

## How to Complete Business Processes of a Terminated Employee

**Source:** https://apidocs.bitrix24.com/tutorials/bizproc/how-to-kill-workflows

How to Complete Business Processes of a Terminated Employee | Bitrix24 REST API and Marketplace Applications
How to Complete Business Processes of a Terminated Employee
How to Complete Business Processes of a Terminated Employee
1. Retrieve the ID of the Terminated Employee
2. Retrieve the List of Tasks for the Processes that the Terminated Employee Was Responsible For
3. Complete the Business Processes
Code Example
Scope:
user_brief, user_basic, user, bizproc
Who can execute methods: administrator
When an employee is terminated in Bitrix24, there may be unfinished business processes for which they were responsible.
To complete the active business processes of the terminated employee, we will sequentially execute three methods:
user.get
— retrieve the
ID
of the terminated employee
bizproc.task.list
— get the list of tasks for the processes that the terminated employee was responsible for
bizproc.workflow.kill
— complete the business processes with data deletion. If you need to preserve the fact that the business process was initiated, use the method
bizproc.workflow.terminate
. Both methods are called in the same way.
1. Retrieve the ID of the Terminated Employee
1. Retrieve the ID of the Terminated Employee
We will use the method
user.get
with the following filter:
NAME
— specify the employee's first name
LAST_NAME
— specify the employee's last name
ACTIVE
— this parameter controls the search for active or terminated employees. If this parameter is not passed, the search will include all employees regardless of their status. We will specify
0
to search only among terminated employees.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"user.get"
,
{
filter
: {
"NAME"
:
"employee's name"
,
"LAST_NAME"
:
"employee's last name"
,
"ACTIVE"
:
0
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
'user.get'
,
[
'filter'
=> [
'NAME'
=>
"employee's name"
,
'LAST_NAME'
=>
"employee's last name"
,
'ACTIVE'
=>
0
]
]
);
As a result, we will obtain the
ID
of the terminated employee.
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
"28936832"
,
"ACTIVE"
:
false
,
"NAME"
:
"employee's name"
,
"LAST_NAME"
:
"employee's last name"
,
"SECOND_NAME"
:
""
,
"TITLE"
:
""
,
"EMAIL"
:
"employee_email@gmail.com"
,
"LAST_LOGIN"
:
"2025-03-27T13:49:36+02:00"
,
"DATE_REGISTER"
:
"2020-04-23T03:00:00+02:00"
,
"TIME_ZONE"
:
"Europe/Berlin"
,
"IS_ONLINE"
:
"N"
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
"PERSONAL_PROFESSION"
:
""
,
"PERSONAL_WWW"
:
""
,
"PERSONAL_BIRTHDAY"
:
""
,
"PERSONAL_PHOTO"
:
"https://cdn-com.bitrix24.com/b13743910/main/3f2/3f212fjf8c3627cfe51633f959de/avatar.png"
,
"PERSONAL_ICQ"
:
""
,
"PERSONAL_PHONE"
:
""
,
"PERSONAL_FAX"
:
""
,
"PERSONAL_MOBILE"
:
""
,
"PERSONAL_PAGER"
:
""
,
"PERSONAL_STREET"
:
""
,
"PERSONAL_CITY"
:
""
,
"PERSONAL_STATE"
:
""
,
"PERSONAL_ZIP"
:
""
,
"PERSONAL_COUNTRY"
:
"0"
,
"PERSONAL_MAILBOX"
:
""
,
"PERSONAL_NOTES"
:
""
,
"WORK_PHONE"
:
""
,
"WORK_COMPANY"
:
""
,
"WORK_POSITION"
:
"Manager"
,
"WORK_DEPARTMENT"
:
""
,
"WORK_WWW"
:
""
,
"WORK_FAX"
:
""
,
"WORK_PAGER"
:
""
,
"WORK_STREET"
:
""
,
"WORK_MAILBOX"
:
""
,
"WORK_CITY"
:
""
,
"WORK_STATE"
:
""
,
"WORK_ZIP"
:
""
,
"WORK_COUNTRY"
:
"0"
,
"WORK_PROFILE"
:
""
,
"WORK_NOTES"
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
7
,
1
]
,
"UF_PHONE_INNER"
:
"555"
,
"UF_USR_1619099890455"
:
"12132132123"
,
"USER_TYPE"
:
"employee"
}
]
,
"total"
:
1
,
}
2. Retrieve the List of Tasks for the Processes that the Terminated Employee Was Responsible For
2. Retrieve the List of Tasks for the Processes that the Terminated Employee Was Responsible For
We will use the method
bizproc.task.list
with the following filter:
USER_ID
— the identifier of the employee, we will pass the ID obtained in
step 1
STATUS
— this parameter indicates the status of the tasks, we will specify
0
to filter only incomplete tasks.
JS
PHP
BX24
.
callMethod
(
'bizproc.task.list'
,
{
filter
: {
'USER_ID'
:
29
,
'STATUS'
:
0
,
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
'bizproc.task.list'
,
[
'filter'
=> [
'USER_ID'
=>
29
,
'STATUS'
=>
0
]
]
);
As a result, we will obtain a list of incomplete tasks. Each task has a
WORKFLOW_ID
parameter — this is the
ID
of the business process that we will complete in the next step.
{
"result"
:
[
{
"ENTITY"
:
"CCrmDocumentContact"
,
"DOCUMENT_ID"
:
"CONTACT_2437"
,
"ID"
:
"879"
,
"WORKFLOW_ID"
:
"67e3db8e581121.72266518"
,
"DOCUMENT_NAME"
:
"widget contact"
,
"NAME"
:
"Address"
,
"DOCUMENT_URL"
:
"/crm/contact/details/2437/"
}
,
{
"ENTITY"
:
"CCrmDocumentContact"
,
"DOCUMENT_ID"
:
"CONTACT_2435"
,
"ID"
:
"877"
,
"WORKFLOW_ID"
:
"67c5b492d0b426.74280093"
,
"DOCUMENT_NAME"
:
"Contact #2435"
,
"NAME"
:
"Address"
,
"DOCUMENT_URL"
:
"/crm/contact/details/2435/"
}
,
{
"ENTITY"
:
"CCrmDocumentContact"
,
"DOCUMENT_ID"
:
"CONTACT_2433"
,
"ID"
:
"875"
,
"WORKFLOW_ID"
:
"67c598a987d387.85575151"
,
"DOCUMENT_NAME"
:
"Contact #2433"
,
"NAME"
:
"Address"
,
"DOCUMENT_URL"
:
"/crm/contact/details/2433/"
}
,
{
"ENTITY"
:
"CCrmDocumentContact"
,
"DOCUMENT_ID"
:
"CONTACT_2429"
,
"ID"
:
"871"
,
"WORKFLOW_ID"
:
"67091df4b13dd2.83077613"
,
"DOCUMENT_NAME"
:
"Petrov Vasily"
,
"NAME"
:
"Address"
,
"DOCUMENT_URL"
:
"/crm/contact/details/2429/"
}
,
{
"ENTITY"
:
"CCrmDocumentContact"
,
"DOCUMENT_ID"
:
"CONTACT_2427"
,
"ID"
:
"859"
,
"WORKFLOW_ID"
:
"66e2d5d5c64f82.28057011"
,
"DOCUMENT_NAME"
:
"Ivanovich"
,
"NAME"
:
"Address"
,
"DOCUMENT_URL"
:
"/crm/contact/details/2427/"
}
,
{
"ENTITY"
:
"CCrmDocumentContact"
,
"DOCUMENT_ID"
:
"CONTACT_2425"
,
"ID"
:
"857"
,
"WORKFLOW_ID"
:
"66e0242399d303.52288141"
,
"DOCUMENT_NAME"
:
"Petrovna"
,
"NAME"
:
"Address"
,
"DOCUMENT_URL"
:
"/crm/contact/details/2425/"
}
,
{
"ENTITY"
:
"CCrmDocumentContact"
,
"DOCUMENT_ID"
:
"CONTACT_2423"
,
"ID"
:
"855"
,
"WORKFLOW_ID"
:
"66d870dfbb9542.91956540"
,
"DOCUMENT_NAME"
:
"Smirnov"
,
"NAME"
:
"Address"
,
"DOCUMENT_URL"
:
"/crm/contact/details/2423/"
}
,
{
"ENTITY"
:
"CCrmDocumentContact"
,
"DOCUMENT_ID"
:
"CONTACT_2421"
,
"ID"
:
"853"
,
"WORKFLOW_ID"
:
"66d7fb6f86c0c2.49741539"
,
"DOCUMENT_NAME"
:
"Kalashnikov"
,
"NAME"
:
"Address"
,
"DOCUMENT_URL"
:
"/crm/contact/details/2421/"
}
,
{
"ENTITY"
:
"CCrmDocumentContact"
,
"DOCUMENT_ID"
:
"CONTACT_2419"
,
"ID"
:
"851"
,
"WORKFLOW_ID"
:
"66d073d9c9fc08.23457428"
,
"DOCUMENT_NAME"
:
"Unnamed"
,
"NAME"
:
"Address"
,
"DOCUMENT_URL"
:
"/crm/contact/details/2419/"
}
]
,
"total"
:
9
,
}
3. Complete the Business Processes
3. Complete the Business Processes
We will use the method
bizproc.workflow.kill
with the following parameter:
ID
— the identifier of the process, we will pass the
WORKFLOW_ID
obtained in
step 2
JS
PHP
BX24
.
callMethod
(
'bizproc.workflow.kill'
,
{
ID
:
'67e3db8e581121.72266518'
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
'bizproc.workflow.kill'
,
[
'ID'
=>
'67e3db8e581121.72266518'
]
);
As a result, we will receive
true
, indicating that the process deletion was successful. If you receive an
error
, review the possible error descriptions in the documentation for the method
bizproc.workflow.kill
.
{
"result"
:
true
,
}
Code Example
Code Example
In the example, all found processes are deleted in a loop. If you need to delete a large volume of data, you may encounter limits on request execution. To optimize the code for your workload, use the recommendations in the
Performance
section.
JS
PHP
// Function to get employee ID by first name and last name
function
getUserId
(
firstName, lastName, callback
) {
BX24
.
callMethod
(
"user.get"
,
{
"NAME"
: firstName,
"LAST_NAME"
: lastName,
"ACTIVE"
:
0
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
// Assuming only one user is found
const
userId = result.
data
()[
0
].
ID
;
callback
(userId);
}
}
);
}
// Function to get the list of incomplete tasks for the employee
function
getUserTasks
(
userId, callback
) {
BX24
.
callMethod
(
'bizproc.task.list'
,
{
filter
: {
'USER_ID'
: userId,
'STATUS'
:
0
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
// Extract WORKFLOW_ID from each task
const
workflowIds = result.
data
().
map
(
task
=>
task.
WORKFLOW_ID
);
callback
(workflowIds);
}
}
);
}
// Function to complete business processes by the list of WORKFLOW_ID
function
killWorkflows
(
workflowIds
) {
workflowIds.
forEach
(
workflowId
=>
{
BX24
.
callMethod
(
'bizproc.workflow.kill'
,
{
ID
: workflowId,
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
(
`Workflow
${workflowId}
completed successfully.`
);
}
}
);
});
}
// Main function that combines all steps
function
processEmployeeTasks
(
firstName, lastName
) {
getUserId
(firstName, lastName,
function
(
userId
) {
getUserTasks
(userId,
function
(
workflowIds
) {
killWorkflows
(workflowIds);
});
});
}
// Prompt user for first name and last name
const
firstName =
prompt
(
"Enter the employee's first name:"
);
const
lastName =
prompt
(
"Enter the employee's last name:"
);
// Start the process
processEmployeeTasks
(firstName, lastName);
require_once
(
'crest.php'
);
// Function to get employee ID by first name and last name
function
getUserId
(
$firstName
,
$lastName
)
{
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
'NAME'
=>
$firstName
,
'LAST_NAME'
=>
$lastName
,
'ACTIVE'
=>
0
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
];
return
null
;
}
// Assuming only one user is found
return
$result
[
'result'
][
0
][
'ID'
] ??
null
;
}
// Function to get the list of incomplete tasks for the employee
function
getUserTasks
(
$userId
)
{
$result
=
CRest
::
call
(
'bizproc.task.list'
,
[
'filter'
=> [
'USER_ID'
=>
$userId
,
'STATUS'
=>
0
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
];
return
[];
}
// Extract WORKFLOW_ID from each task
return
array_map
(function(
$task
) {
return
$task
[
'WORKFLOW_ID'
];
},
$result
[
'result'
]);
}
// Function to complete business processes by the list of WORKFLOW_ID
function
killWorkflows
(
$workflowIds
)
{
foreach
(
$workflowIds
as
$workflowId
) {
$result
=
CRest
::
call
(
'bizproc.workflow.kill'
,
[
'ID'
=>
$workflowId
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
];
}
else
{
echo
"Workflow
$workflowId
completed successfully.\n"
;
}
}
}
// Main function that combines all steps
function
processEmployeeTasks
(
$firstName
,
$lastName
)
{
$userId
=
getUserId
(
$firstName
,
$lastName
);
if
(
$userId
) {
$workflowIds
=
getUserTasks
(
$userId
);
killWorkflows
(
$workflowIds
);
}
}
// Prompt user for first name and last name
$firstName
=
readline
(
"Enter the employee's first name: "
);
$lastName
=
readline
(
"Enter the employee's last name: "
);
// Start the process
processEmployeeTasks
(
$firstName
,
$lastName
);
Copied
Was the article helpful?
Yes
No
Previous
How to embed your UI in the Automation rule parameters
Next
How to bulk terminate workflows with a date filter

---

## How to Mass Finish Workflows with Date Filter

**Source:** https://apidocs.bitrix24.com/tutorials/bizproc/how-to-filter-and-kill-workflows

How to Mass Finish Workflows with Date Filter | Bitrix24 REST API and Marketplace Applications
How to Mass Finish Workflows with Date Filter
How to Mass Finish Workflows with Date Filter
1. Get the List of Processes
2. Finish the Workflows
Code Example
Scope:
bizproc
Who can execute methods: administrator
During the use of Bitrix24, there may be accumulated stuck workflows or processes that remain in the "In Progress" status for too long and become irrelevant.
To mass finish old workflows, we will sequentially execute two methods:
bizproc.workflow.instances
— we will get a filtered list of processes
bizproc.workflow.kill
— we will finish the workflows with data deletion. If you need to keep the fact of the workflow's launch, use the method
bizproc.workflow.terminate
. Both methods are called in the same way.
1. Get the List of Processes
1. Get the List of Processes
We will use the method
bizproc.workflow.instances
with a filter:
<STARTED
— we will specify the start date with the prefix
<
, only those processes that were started before this date will be selected.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'bizproc.workflow.instances'
,
{
filter
: {
'<STARTED'
:
'2025-01-01T00:00:00Z'
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
'bizproc.workflow.instances'
,
[
'filter'
=> [
'<STARTED'
=>
'2025-01-01T00:00:00Z'
]
]
);
As a result, we will get the
ID
of all active workflows that were started before the specified date.
{
"result"
:
[
{
"ID"
:
"660e559f34af10.95144732"
,
"MODIFIED"
:
"2024-12-04T10:04:24+03:00"
,
"OWNED_UNTIL"
:
null
}
,
{
"ID"
:
"6639c7b59e9eb5.40607056"
,
"MODIFIED"
:
"2024-12-04T09:52:40+03:00"
,
"OWNED_UNTIL"
:
null
}
,
{
"ID"
:
"66ea9200131729.26195442"
,
"MODIFIED"
:
"2024-09-18T11:42:28+03:00"
,
"OWNED_UNTIL"
:
null
}
,
{
"ID"
:
"65ef0868368978.47049110"
,
"MODIFIED"
:
"2024-03-11T16:34:32+03:00"
,
"OWNED_UNTIL"
:
null
}
]
,
"total"
:
4
,
}
2. Finish the Workflows
2. Finish the Workflows
We will use the method
bizproc.workflow.kill
with the parameter:
ID
— the identifier of the process, we pass the
ID
obtained in
step 1
.
JS
PHP
BX24
.
callMethod
(
'bizproc.workflow.kill'
,
{
ID
:
'660e559f34af10.95144732'
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
'bizproc.workflow.kill'
,
[
'ID'
=>
'660e559f34af10.95144732'
]
);
As a result, we will receive
true
, indicating that the process was successfully deleted. If you received an
error
, check the possible error descriptions in the documentation for the method
bizproc.workflow.kill
.
{
"result"
:
true
,
}
Code Example
Code Example
In the example, all found processes are deleted in a loop. When deleting a large volume of data, there may be limitations on request execution. To optimize the code for your workload, use the recommendations in the
Performance
section.
JS
PHP
// Function to convert date from dd.mm.yyyy format to ISO format
function
convertDateToISO
(
dateString
) {
const
[day, month, year] = dateString.
split
(
'.'
);
return
`
${year}
-
${month}
-
${day}
T00:00:00Z`
;
}
// Request date from user
const
userDateInput =
prompt
(
"Enter date in dd.mm.yyyy format:"
);
const
isoDate =
convertDateToISO
(userDateInput);
// Call the bizproc.workflow.instances method with date filter
BX24
.
callMethod
(
'bizproc.workflow.instances'
,
{
filter
: {
'<STARTED'
: isoDate
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
const
instances = result.
data
();
instances.
forEach
(
instance
=>
{
const
instanceId = instance.
ID
;
// Call the bizproc.workflow.kill method for each ID
BX24
.
callMethod
(
'bizproc.workflow.kill'
,
{
ID
: instanceId
},
function
(
killResult
) {
if
(killResult.
error
()) {
console
.
error
(
`Error deleting process
${instanceId}
:`
, killResult.
error
());
}
else
{
console
.
log
(
`Process
${instanceId}
successfully deleted.`
);
}
}
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
}
);
require_once
(
'crest.php'
);
// Function to convert date from dd.mm.yyyy format to ISO format
function
convertDateToISO
(
$dateString
)
{
list
(
$day
,
$month
,
$year
) =
explode
(
'.'
,
$dateString
);
return
"
{$year}
-
{$month}
-
{$day}
T00:00:00Z"
;
}
// Request date from user
$userDateInput
=
readline
(
"Enter date in dd.mm.yyyy format: "
);
$isoDate
=
convertDateToISO
(
$userDateInput
);
// Call the bizproc.workflow.instances method with date filter
$result
=
CRest
::
call
(
'bizproc.workflow.instances'
,
[
'filter'
=> [
'<STARTED'
=>
$isoDate
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
];
}
else
{
$instances
=
$result
[
'result'
];
foreach
(
$instances
as
$instance
) {
$instanceId
=
$instance
[
'ID'
];
// Call the bizproc.workflow.kill method for each ID
$killResult
=
CRest
::
call
(
'bizproc.workflow.kill'
,
[
'ID'
=>
$instanceId
]
);
if
(!
empty
(
$killResult
[
'error'
])) {
echo
"Error deleting process
{$instanceId}
: "
.
$killResult
[
'error_description'
] .
"\n"
;
}
else
{
echo
"Process
{$instanceId}
successfully deleted.\n"
;
}
}
// Check for additional data
while
(!
empty
(
$result
[
'next'
])) {
$result
=
CRest
::
call
(
'bizproc.workflow.instances'
,
[
'filter'
=> [
'<STARTED'
=>
$isoDate
],
'start'
=>
$result
[
'next'
]
]
);
$instances
=
$result
[
'result'
];
foreach
(
$instances
as
$instance
) {
$instanceId
=
$instance
[
'ID'
];
// Call the bizproc.workflow.kill method for each ID
$killResult
=
CRest
::
call
(
'bizproc.workflow.kill'
,
[
'ID'
=>
$instanceId
]
);
if
(!
empty
(
$killResult
[
'error'
])) {
echo
"Error deleting process
{$instanceId}
: "
.
$killResult
[
'error_description'
] .
"\n"
;
}
else
{
echo
"Process
{$instanceId}
successfully deleted.\n"
;
}
}
}
}
Copied
Was the article helpful?
Yes
No
Previous
How to terminate workflows of a terminated employee
Next
Tutorials and use-cases of REST in the AI module

---

