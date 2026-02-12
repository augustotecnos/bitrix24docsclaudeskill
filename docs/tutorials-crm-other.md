---
description: 'Tutorials: Other CRM operations'
methods:
- crm.company.add
- crm.contact.add
- crm.deal.add
- crm.lead.add
- crm.lead.list
- crm.lead.userfield.add
- crm.quote.add
- crm.tracking.trace.add
- event.preventDefault
- event.target
pages: 8
title: 'Tutorials: Other CRM operations'
---
# Tutorials: Other CRM operations
> Tutorials: Other CRM operations
> **8 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Typical use-cases and scenarios for REST API in CRM and tutorials](#typical-use-cases-and-scenarios-for-rest-api-in-cr)
- [Sales Intelligence](#sales-intelligence)
- [How to Use Sales Intelligence When Creating a Lead](#how-to-use-sales-intelligence-when-creating-a-lead)
- [How to Use Sales Intelligence When Creating a Deal and Contact](#how-to-use-sales-intelligence-when-creating-a-deal)
- [How to Transfer Information to Sales Intelligence](#how-to-transfer-information-to-sales-intelligence)
- [How to Embed Widgets](#how-to-embed-widgets)
- [Embed a widget in a lead as a custom property](#embed-a-widget-in-a-lead-as-a-custom-property)
- [Embed Widget in CRM Card](#embed-widget-in-crm-card)

---

## Typical use-cases and scenarios for REST API in CRM and tutorials

**Source:** https://apidocs.bitrix24.com/tutorials/crm/index

Typical use-cases and scenarios for REST API in CRM and tutorials | Bitrix24 REST API and Marketplace Applications
How to create leads, deals, and other CRM objects
Typical use-cases and scenarios for REST API in CRM and tutorials
How to create leads, deals, and other CRM objects
How to replace an outdated phone number for an existing client, how to update product information, and other examples
How to find clients by phone, how to get all activities of a client, and other examples of working with lists of entities
How to use Bitrix24's Sales Intelligence tools
How to add your tab to the deal detail form, how to add your buttons to the lead detail form, and other examples of CRM widgets
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
How to Add a Comment to the Timeline of a Smart Process
How to Set Up Rounding for a Custom Field of Type "Number"
How to Create a Custom Field in a SPA
How to replace an outdated phone number for an existing client, how to update product information, and other examples
How to replace an outdated phone number for an existing client, how to update product information, and other examples
How to Change or Delete Phone Numbers and Emails
How to Create Your Lead Editing Form
How to Create Your Contact Editing Form
How to Create Your Company Editing Form
How to Create Your Deal Edit Form
How to find clients by phone, how to get all activities of a client, and other examples of working with lists of entities
How to find clients by phone, how to get all activities of a client, and other examples of working with lists of entities
How to Find Duplicates in CRM by Phone and Email
How to Get a List of Activities from Deals
How to Get a List of Stages with Semantics for CRM Objects
How to Get the Sales Funnel of a Given Direction with the Semantics of Each Deal Stage
How to Get a Client's Address from CRM
How to use Bitrix24's Sales Intelligence tools
How to use Bitrix24's Sales Intelligence tools
How to Transfer Information to Sales Intelligence
How to Use Sales Intelligence When Creating a Lead
How to Use Sales Intelligence When Creating a Deal and Contact
How to add your tab to the deal detail form, how to add your buttons to the lead detail form, and other examples of CRM widgets
How to add your tab to the deal detail form, how to add your buttons to the lead detail form, and other examples of CRM widgets
Embed a widget in a lead as a custom property
Was the article helpful?
Yes
No
Previous
Ready-to-use REST API scenarios
Next
How to Add Leads and Other Entities

---

## Sales Intelligence

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-use-analitycs/index

Sales Intelligence | Bitrix24 REST API and Marketplace Applications
Sales Intelligence
Sales Intelligence
How to Use Sales Intelligence When Creating a Lead
How to Use Sales Intelligence When Creating a Deal and Contact
How to Transfer Information to Sales Intelligence
Was the article helpful?
Yes
No
Previous
How to Filter Elements by Stage Name
Next
How to Use Sales Intelligence When Creating a Lead

---

## How to Use Sales Intelligence When Creating a Lead

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-use-analitycs/use-analitics-for-add-lead

How to Use Sales Intelligence When Creating a Lead | Bitrix24 REST API and Marketplace Applications
How to Use Sales Intelligence When Creating a Lead
How to Use Sales Intelligence When Creating a Lead
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
An example of using Sales Intelligence when creating a lead. First, create a PHP page with a feedback form: First Name, Last Name, Phone. Place the example code on the page.
What happens during the execution of the code?
The standard JS code from Bitrix24's Sales Intelligence is connected.
After filling out the form, in addition to the form fields, a hidden field transmits the code for Sales Intelligence
b24Tracker.guest.getTrace()
.
Then, the method
crm.lead.add
is called, where the code from
getTrace
is added to the
TRACE
field.
The Sales Intelligence script is installed on your site before the closing
</body>
tag on all pages of the site, including the page with the form.
JS
PHP
<!
DOCTYPE
html>
<html lang="en">
<head>
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" crossorigin="anonymous">
</head>
<body class="container">
<h1>Feedback</h1>
<div class="col-12">
<p id="message"></p>
</div>
<form id="feedbackForm">
<input type="hidden" id="FORM_TRACE" name="TRACE">
<div class="row">
<div class="col-4 mt-3">
<label>First Name*</label>
</div>
<div class="col-6 mt-3">
<input type="text" name="NAME" required>
</div>
</div>
<div class="row">
<div class="col-4 mt-3">
<label>Last Name*</label>
</div>
<div class="col-6 mt-3">
<input type="text" name="LAST_NAME" required>
</div>
</div>
<div class="row">
<div class="col-4 mt-3">
<label>Phone*</label>
</div>
<div class="col-6 mt-3">
<input type="text" name="PHONE" required>
</div>
</div>
<div class="row">
<div class="col-sm-10">
<input type="submit" name="SAVE" class="btn btn-primary" value="Send">
</div>
</div>
</form>
<script>
window.onload = function(e){
var traceInput = document.getElementById('FORM_TRACE');
if(traceInput)
{
traceInput.value = b24Tracker.guest.getTrace();
}
}
document.getElementById('feedbackForm').addEventListener('submit', function(event) {
event.preventDefault();
var formData = new FormData(event.target);
var fields = {
TRACE: formData.get('TRACE'),
NAME: formData.get('NAME'),
LAST_NAME: formData.get('LAST_NAME'),
PHONE: [{ value: formData.get('PHONE') }]
};
BX24.callMethod(
'crm.lead.add',
{ fields: fields },
function(result) {
var messageElement = document.getElementById('message');
if(result.error()) {
messageElement.textContent = 'Feedback has not been saved: ' + result.error_description();
} else {
messageElement.textContent = 'Feedback saved';
}
}
);
});
</script>
</body>
</html>
Note
To use the examples in PHP, configure the
CRest
class and include the
crest.php
file in the files where this class is used.
More details
<!DOCTYPE html>
<html lang=
"en"
>
<head>
<link rel=
"stylesheet"
href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
crossorigin=
"anonymous"
>
</head>
<body
class
="
container
">
<
h1
>
Feedback
</
h1
>
<?
php
include
("
crest
.
php
");
$
message
= '';
if
(!
empty
($
_POST
['
SAVE
']))
{
$fields
= [
'TRACE'
=>
$_POST
[
'TRACE'
],
'NAME'
=>
$_POST
[
'NAME'
],
'LAST_NAME'
=>
$_POST
[
'LAST_NAME'
],
'PHONE'
=> [ [
'value'
=>
$_POST
[
'PHONE'
] ] ],
];
$result
=
CRest
::
call
(
'crm.lead.add'
,
[
'fields'
=>
$fields
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
$message
=
'Feedback saved'
;
}
elseif
(!
empty
(
$result
[
'error_description'
]))
{
$message
=
'Feedback has not been saved: '
.
$result
[
'error_description'
];
}
else
{
$message
=
'Feedback has not been saved'
;
}
}
?>
<div
class
="
col
-12">
<
p
><?=$
message
?></
p
>
</
div
>
<
form
method
="
post
"
action
="">
<
input
type
="
hidden
"
id
="
FORM_TRACE
"
name
="
TRACE
">
<
div
class
="
row
">
<
div
class
="
col
-4
mt
-3">
<
label
>
First
Name
*</
label
>
</
div
>
<
div
class
="
col
-6
mt
-3">
<
input
type
="
text
"
name
="
NAME
"
required
>
</
div
>
</
div
>
<
div
class
="
row
">
<
div
class
="
col
-4
mt
-3">
<
label
>
Last
Name
*</
label
>
</
div
>
<
div
class
="
col
-6
mt
-3">
<
input
type
="
text
"
name
="
LAST_NAME
"
required
>
</
div
>
</
div
>
<
div
class
="
row
">
<
div
class
="
col
-4
mt
-3">
<
label
>
Phone
*</
label
>
</
div
>
<
div
class
="
col
-6
mt
-3">
<
input
type
="
text
"
name
="
PHONE
"
required
>
</
div
>
</
div
>
<
div
class
="
row
">
<
div
class
="
col
-
sm
-10">
<
input
type
="
submit
"
name
="
SAVE
"
class
="
btn
btn
-
primary
"
value
="
Send
">
</
div
>
</
div
>
</
form
>
<
script
>
window
.
onload
=
function
(
e
)
{
var
traceInput = document.
getElementById
(
'FORM_TRACE'
);
if
(traceInput)
{
traceInput.value = b24Tracker.guest.
getTrace
();
}
}
</script>
</body>
</html>
Copied
Was the article helpful?
Yes
No
Previous
Sales Intelligence
Next
How to Use Sales Intelligence When Creating a Deal and Contact

---

## How to Use Sales Intelligence When Creating a Deal and Contact

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-use-analitycs/use-analitics-for-add-contact

How to Use Sales Intelligence When Creating a Deal and Contact | Bitrix24 REST API and Marketplace Applications
How to Use Sales Intelligence When Creating a Deal and Contact
How to Use Sales Intelligence When Creating a Deal and Contact
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
An example of using Sales Intelligence when creating a deal and contact. First, create a PHP page with a feedback web form: Full Name, Phone. Place the example code on the page.
What happens during the execution of the code?
The standard JS code from Bitrix24 Sales Intelligence is connected.
After filling out the form, in addition to the form fields, the code for Sales Intelligence
b24Tracker.guest.getTrace()
is passed in a hidden field.
A deal and a related contact are then created.
Finally, an analytics "trace" is registered for these objects, passing their types and identifiers in the following format:
/rest/crm.tracking.trace.add?ENTITIES[0][TYPE]=CONTACT&ENTITIES[0][ID]=3215&ENTITIES[1][TYPE]=LEAD&ENTITIES[1][ID]=1&TRACE=…
The Sales Intelligence script is installed on your site before the closing
</body>
tag on all pages of the site, including the page with the form.
JS
PHP
<!
DOCTYPE
html>
<html lang="en">
<head>
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" crossorigin="anonymous">
</head>
<body class="container">
<h1>Feedback</h1>
<div class="col-12">
<p id="message"></p>
</div>
<form id="feedbackForm">
<input type="hidden" id="FORM_TRACE" name="TRACE">
<div class="row">
<div class="col-4 mt-3">
<label>Name*</label>
</div>
<div class="col-6 mt-3">
<input type="text" name="NAME" required>
</div>
</div>
<div class="row">
<div class="col-4 mt-3">
<label>Last name*</label>
</div>
<div class="col-6 mt-3">
<input type="text" name="LAST_NAME" required>
</div>
</div>
<div class="row">
<div class="col-4 mt-3">
<label>Phone*</label>
</div>
<div class="col-6 mt-3">
<input type="text" name="PHONE" required>
</div>
</div>
<div class="row">
<div class="col-sm-10">
<input type="submit" class="btn btn-primary" value="Send">
</div>
</div>
</form>
<script>
document.getElementById('feedbackForm').addEventListener('submit', function(event) {
event.preventDefault();
var formData = new FormData(event.target);
var fields = {
NAME: formData.get('NAME'),
LAST_NAME: formData.get('LAST_NAME'),
PHONE: [{ value: formData.get('PHONE') }]
};
BX24.callMethod(
'crm.contact.add',
{ fields: fields },
function(resultContact) {
if (resultContact.error()) {
document.getElementById('message').innerText = 'Feedback has not been saved: ' + resultContact.error_description();
} else {
var arDealFields = {
TITLE: 'Feedback page: ' + formData.get('NAME') + ' ' + formData.get('LAST_NAME'),
CONTACT_ID: resultContact.data()
};
BX24.callMethod(
'crm.deal.add',
{ fields: arDealFields },
function(resultDeal) {
if (resultDeal.error()) {
document.getElementById('message').innerText = 'Feedback has not been saved: ' + resultDeal.error_description();
} else {
if (formData.get('TRACE')) {
BX24.callMethod(
'crm.tracking.trace.add',
{
ENTITIES: [
{ TYPE: 'CONTACT', ID: resultContact.data() },
{ TYPE: 'DEAL', ID: resultDeal.data() }
],
TRACE: formData.get('TRACE')
},
function(resultTrace) {
if (resultTrace.error()) {
document.getElementById('message').innerText = 'Feedback has not been saved: ' + resultTrace.error_description();
} else {
document.getElementById('message').innerText = 'Feedback saved';
}
}
);
} else {
document.getElementById('message').innerText = 'Feedback saved';
}
}
}
);
}
}
);
});
window.onload = function(e) {
var traceDom = document.getElementById('FORM_TRACE');
if (traceDom) {
var trace = b24Tracker.guest.getTrace();
traceDom.value = trace;
}
}
</script>
</body>
</html>
Note
To use the examples in PHP, configure the
CRest
class and include the
crest.php
file in the files where this class is used.
More details
<!DOCTYPE html>
<html lang=
"en"
>
<head>
<link rel=
"stylesheet"
href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
crossorigin=
"anonymous"
>
</head>
<body
class
="
container
">
<
h1
>
Feedback
</
h1
>
<?
php
include
("
crest
.
php
");
$
message
= '';
if
(!
empty
($
_POST
['
SAVE
']))
{
$fields
= [
'NAME'
=>
$_POST
[
'NAME'
],
'LAST_NAME'
=>
$_POST
[
'LAST_NAME'
],
'PHONE'
=> [ [
'value'
=>
$_POST
[
'PHONE'
] ] ],
];
$resultContact
=
CRest
::
call
(
'crm.contact.add'
,
[
'fields'
=>
$fields
]
);
if
(!
empty
(
$resultContact
[
'result'
]))
{
$arDealFields
= [
'TITLE'
=>
'Feedback page: '
.
$_POST
[
'NAME'
].
' '
.
$_POST
[
'LAST_NAME'
],
'CONTACT_ID'
=>
$resultContact
[
'result'
]
];
$resultDeal
=
CRest
::
call
(
'crm.deal.add'
,
[
'fields'
=>
$arDealFields
]
);
if
(!
empty
(
$resultDeal
[
'result'
]))
{
if
(!
empty
(
$_POST
[
'TRACE'
]))
{
$resultTrace
=
CRest
::
call
(
'crm.tracking.trace.add'
,
[
'ENTITIES'
=> [
[
'TYPE'
=>
'CONTACT'
,//COMPANY, CONTACT, DEAL, LEAD, QUOTE
'ID'
=>
$resultContact
[
'result'
]
],
[
'TYPE'
=>
'DEAL'
,//COMPANY, CONTACT, DEAL, LEAD, QUOTE
'ID'
=>
$resultDeal
[
'result'
]
]
],
'TRACE'
=>
$_POST
[
'TRACE'
]
]
);
}
$message
=
'Feedback saved'
;
}
elseif
(!
empty
(
$resultDeal
[
'error_description'
]))
{
$message
=
'Feedback has not been saved: '
.
$resultDeal
[
'error_description'
];
}
else
{
$message
=
'Feedback has not been saved'
;
}
}
elseif
(!
empty
(
$resultContact
[
'error_description'
]))
{
$message
=
'Feedback has not been saved: '
.
$resultContact
[
'error_description'
];
}
else
{
$message
=
'Feedback has not been saved'
;
}
}
?>
<div
class
="
col
-12">
<
p
><?=$
message
?></
p
>
</
div
>
<
form
method
="
post
"
action
="">
<
input
type
="
hidden
"
id
="
FORM_TRACE
"
name
="
TRACE
">
<
div
class
="
row
">
<
div
class
="
col
-4
mt
-3">
<
label
>
Name
*</
label
>
</
div
>
<
div
class
="
col
-6
mt
-3">
<
input
type
="
text
"
name
="
NAME
"
required
>
</
div
>
</
div
>
<
div
class
="
row
">
<
div
class
="
col
-4
mt
-3">
<
label
>
Last
name
*</
label
>
</
div
>
<
div
class
="
col
-6
mt
-3">
<
input
type
="
text
"
name
="
LAST_NAME
"
required
>
</
div
>
</
div
>
<
div
class
="
row
">
<
div
class
="
col
-4
mt
-3">
<
label
>
Phone
*</
label
>
</
div
>
<
div
class
="
col
-6
mt
-3">
<
input
type
="
text
"
name
="
PHONE
"
required
>
</
div
>
</
div
>
<
div
class
="
row
">
<
div
class
="
col
-
sm
-10">
<
input
type
="
submit
"
name
="
SAVE
"
class
="
btn
btn
-
primary
"
value
="
Send
">
</
div
>
</
div
>
</
form
>
<
script
>
window
.
onload
=
function
(
e
)
{
var
traceDom = document.
getElementById
(
'FORM_TRACE'
);
if
(traceDom)
{
var
trace = b24Tracker.guest.
getTrace
();
traceDom.value = trace;
}
}
</script>
</body>
</html>
Copied
Was the article helpful?
Yes
No
Previous
How to Use Sales Intelligence When Creating a Lead
Next
How to Transfer Information to Sales Intelligence

---

## How to Transfer Information to Sales Intelligence

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-use-analitycs/info-to-analitics

How to Transfer Information to Sales Intelligence | Bitrix24 REST API and Marketplace Applications
How to Transfer Information to Sales Intelligence
How to Transfer Information to Sales Intelligence
The Easiest Way
Complete Data
Creating a Trace and Obtaining Its ID
One Trace for Related Entities
Continue Learning
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
crm
Who can execute the method: users with administrative access permission to the CRM section.
When creating CRM entities, there are three ways to transfer information for Sales Intelligence.
The Easiest Way
The Easiest Way
Transfer the
UTM_SOURCE
field in the created entity's fields.
In this case, when the entity is created, if a configured source in Sales Intelligence with the same
UTM_SOURCE
is found, this source will be assigned to the entity, the corresponding icon will be displayed, and the entity will participate in the Sales Intelligence report.
Complete Data
Complete Data
Transfer the
TRACE
field in the created entity's fields.
In this case, all data will be taken into account — device, all channels, including the website, and visited pages.
This method works for the following methods:
crm.lead.add
,
crm.deal.add
,
crm.contact.add
,
crm.company.add
,
crm.quote.add
.
{
"fields"
:
{
"NAME"
:
"test"
,
"LAST_NAME"
:
""
,
"TRACE"
:
...
}
,
}
The value of the
TRACE
field must be either the identifier of the saved Sales Intelligence record or a JSON string with an array of a specific format, which can be obtained by simply using the JS code of the Sales Intelligence widget in Bitrix24:
b24Tracker.
guest
.
getTrace
()
The value of the
TRACE
field can be a number — the
ID
of the trace obtained by the method
crm.tracking.trace.add
.
Creating a Trace and Obtaining Its ID
Creating a Trace and Obtaining Its ID
The method creates a trace:
crm.tracking.trace.add
?ENTITIES[0][TYPE]=CONTACT&ENTITIES[0][ID]=3215&ENTITIES[1][TYPE]=LEAD&ENTITIES[1][ID]=1&TRACE=
The
TRACE
field is required, and the value is a string obtained by the method
b24Tracker.guest.getTrace
. See the example above.
The
ENTITIES
field is optional; it can list the entities that are linked to this trace:
ENTITIES
: [
{
TYPE
:
'CONTACT'
,
ID
:
1
},
{
TYPE
:
'LEAD'
,
ID
:
101
}
]
One Trace for Related Entities
One Trace for Related Entities
If a package of related entities (deal + contact + company) is created, a single trace can be created for them. If the contact and company already exist, and only the deal is being created, a trace can be created and linked to the existing entities.
Continue Learning
Continue Learning
Using Sales Intelligence When Creating a Lead
Using Sales Intelligence When Creating a Deal and Contact
Copied
Was the article helpful?
Yes
No
Previous
How to Use Sales Intelligence When Creating a Deal and Contact
Next
How to Embed Widgets in CRM

---

## How to Embed Widgets

**Source:** https://apidocs.bitrix24.com/tutorials/crm/crm-widgets/index

How to Embed Widgets | Bitrix24 REST API and Marketplace Applications
How to Embed Widgets
How to Embed Widgets
Embed a widget in a lead as a custom property
Embed Widget in CRM Card
Was the article helpful?
Yes
No
Previous
How to Transfer Information to Sales Intelligence
Next
Embed a Widget in a Lead as a Custom Property

---

## Embed a widget in a lead as a custom property

**Source:** https://apidocs.bitrix24.com/tutorials/crm/crm-widgets/widget-as-field-in-lead-page

Embed a widget in a lead as a custom property | Bitrix24 REST API and Marketplace Applications
Embed a widget in a lead as a custom property
Embed a widget in a lead as a custom property
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
Example of adding a custom property to a lead's detail form. The example works as follows: after the first interaction with the property in the lead editing form, the handler from the application will always be loaded, even in view mode. The handler makes a request to an external API to obtain the region and operator of the given phone number in the US.
The property installation code is called once. The variable
handlerUrl
is the path to the property handler file.
JS
PHP
var
handlerUrl =
'https://yourdomain.yyy/handler.php'
;
var
type =
'phone_data'
;
var
propCode =
'PHONE_DATA'
;
// max length with prefix UF_CRM_ 20 char
BX24
.
callMethod
(
'userfieldtype.add'
,
{
'USER_TYPE_ID'
: type,
'HANDLER'
: handlerUrl,
'TITLE'
:
'custom type title'
,
'DESCRIPTION'
:
'custom description '
+ type
},
function
(
resultAddPropType
) {
if
(resultAddPropType.
error
()) {
console
.
error
(resultAddPropType.
error
() +
': '
+ resultAddPropType.
error_description
());
}
else
{
console
.
log
(
'property type '
+ type +
' has been added successfully'
);
BX24
.
callMethod
(
'crm.lead.userfield.add'
,
{
'fields'
: {
'USER_TYPE_ID'
: type,
'FIELD_NAME'
: propCode,
'XML_ID'
: propCode,
'MANDATORY'
:
'N'
,
'SHOW_IN_LIST'
:
'Y'
,
'EDIT_IN_LIST'
:
'Y'
,
'EDIT_FORM_LABEL'
:
'My string'
,
'LIST_COLUMN_LABEL'
:
'My string description'
,
'SETTINGS'
: {}
}
},
function
(
resultAddProp
) {
if
(resultAddProp.
error
()) {
console
.
error
(resultAddProp.
error
() +
': '
+ resultAddProp.
error_description
());
}
else
{
console
.
log
(
'property '
+ propCode +
' has been added successfully'
);
}
}
);
}
}
);
Note
To use the PHP examples, configure the
CRest
class and include the
crest.php
file in the files where this class is used.
Learn more
<?php
$handlerUrl
=
'https://yourdomain.yyy/handler.php'
;
$type
=
'phone_data'
;
$propCode
=
'PHONE_DATA'
;
// max length with prefix UF_CRM_ 20 char
$resultAddPropType
=
CRest
::
call
(
'userfieldtype.add'
,
[
'USER_TYPE_ID'
=>
$type
,
'HANDLER'
=>
$handlerUrl
,
'TITLE'
=>
'custom type title'
,
'DESCRIPTION'
=>
'custom description '
.
$type
]
);
if
(
$resultAddPropType
[
'result'
] ==
true
) {
echo
'property type '
.
$type
.
' has been added successfully <br>'
;
$resultAddProp
=
CRest
::
call
(
'crm.lead.userfield.add'
,
[
'fields'
=> [
'USER_TYPE_ID'
=>
$type
,
'FIELD_NAME'
=>
$propCode
,
'XML_ID'
=>
$propCode
,
'MANDATORY'
=>
'N'
,
'SHOW_IN_LIST'
=>
'Y'
,
'EDIT_IN_LIST'
=>
'Y'
,
'EDIT_FORM_LABEL'
=>
'My string'
,
'LIST_COLUMN_LABEL'
=>
'My string description'
,
'SETTINGS'
=> []
]
]
);
if
(
$resultAddProp
[
'error'
]) {
echo
$resultAddProp
[
'error'
] .
': '
.
$resultAddProp
[
'error_description'
];
}
else
{
echo
'property '
.
$propCode
.
' has been added successfully <br>'
;
}
}
elseif
(
$resultAddPropType
[
'error'
]) {
echo
$resultAddPropType
[
'error'
] .
': '
.
$resultAddPropType
[
'error_description'
];
}
?>
The handler file that you specified in the
handlerUrl
variable in the code above:
JS
PHP
var
placementOptions =
BX24
.
getPlacementOptions
();
if
(
BX24
.
getPlacement
() ===
'USERFIELD_TYPE'
) {
var
value = placementOptions.
VALUE
;
if
(placementOptions.
ENTITY_ID
===
'CRM_LEAD'
&& placementOptions.
ENTITY_VALUE_ID
>
0
) {
BX24
.
callMethod
(
'crm.lead.list'
,
{
'filter'
: {
'ID'
:
parseInt
(placementOptions.
ENTITY_VALUE_ID
) },
'select'
: [
'ID'
,
'PHONE'
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
() +
': '
+ result.
error_description
());
}
else
{
if
(result.
data
()[
0
] && result.
data
()[
0
].
PHONE
[
0
] && result.
data
()[
0
].
PHONE
[
0
].
VALUE
) {
value = result.
data
()[
0
].
PHONE
[
0
].
VALUE
.
trim
();
fetch
(
'http://api.bitroid.info/phone/?q='
+ value)
.
then
(
response
=>
response.
json
())
.
then
(
valueData
=>
{
if
(!valueData.
error
) {
value = [valueData.
org
, valueData.
region
].
join
(
', '
);
}
else
{
value =
'error: '
+ valueData.
error
;
}
updateValue
(value);
})
.
catch
(
() =>
{
value =
'no data in base'
+ value;
updateValue
(value);
});
}
else
{
value =
'no data'
;
updateValue
(value);
}
}
}
);
}
else
{
updateValue
(value);
}
}
function
updateValue
(
value
) {
document
.
body
.
style
.
backgroundColor
= placementOptions.
MODE
===
'edit'
?
'#fff'
:
'#f9fafb'
;
if
(placementOptions.
MODE
===
'edit'
) {
document
.
body
.
innerHTML
=
'<input type="text" style="width: 90%;" value="'
+ value +
'" onkeyup="setValue(this.value)">'
;
setValue
(value);
}
else
{
document
.
body
.
innerHTML
= value;
}
}
function
setValue
(
value
) {
BX24
.
placement
.
call
(
'setValue'
, value);
}
Note
To use the PHP examples, configure the
CRest
class and include the
crest.php
file in the files where this class is used.
Learn more
<?php
$placementOptions
=
isset
(
$_REQUEST
[
'PLACEMENT_OPTIONS'
]) ?
json_decode
(
$_REQUEST
[
'PLACEMENT_OPTIONS'
],
true
) :
array
();
if
(
$_REQUEST
[
'PLACEMENT'
] ==
'USERFIELD_TYPE'
):
$value
=
htmlspecialchars
(
$placementOptions
[
'VALUE'
]);
if
(
$placementOptions
[
'ENTITY_ID'
] ==
'CRM_LEAD'
&&
$placementOptions
[
'ENTITY_VALUE_ID'
] >
0
) {
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
intval
(
$placementOptions
[
'ENTITY_VALUE_ID'
])],
'select'
=> [
'ID'
,
'PHONE'
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
][
0
][
'PHONE'
][
0
][
'VALUE'
])) {
$value
=
trim
(
$result
[
'result'
][
0
][
'PHONE'
][
0
][
'VALUE'
]);
$data
=
file_get_contents
(
'http://api.bitroid.info/phone/?q='
.
$value
);
if
(
$data
) {
$valueData
=
json_decode
(
$data
,
true
);
if
(!
$valueData
[
'error'
]) {
$value
=
implode
(
', '
, [
$valueData
[
'org'
],
$valueData
[
'region'
]]);
}
else
{
$value
=
'error: '
.
$valueData
[
'error'
];
}
}
else
{
$value
=
'no data in base'
.
$value
;
}
}
else
{
$value
=
'no data'
;
}
}
?>
<!DOCTYPE html>
<html>
<head>
<script src=
"//api.bitrix24.com/api/v1/dev/"
></script>
</head>
<body style=
"margin: 0; padding: 0; background-color: <?=
$placementOptions
['MODE'] === 'edit' ? '#fff' : '#f9fafb' ?>;"
>
<?php
if
(
$placementOptions
[
'MODE'
] ===
'edit'
):
?>
<input type=
"text"
style=
"width: 90%;"
value=
'<?= $value ?>'
onkeyup=
"setValue(this.value)"
>
<script>
function
setValue
(
value
)
{
BX24.placement.
call
(
'setValue'
, value);
}
BX24.placement.
call
(
'setValue'
,
'<?= $value ?>'
);
</script>
<?php
else
:
?>
<?=
$value
?>
<?php
endif
;
?>
</body>
</html>
<?php
endif
;
?>
Copied
Was the article helpful?
Yes
No
Previous
How to Embed Widgets in CRM
Next
Embed a Widget in a CRM Detail Form

---

## Embed Widget in CRM Card

**Source:** https://apidocs.bitrix24.com/tutorials/crm/crm-widgets/widget-as-detail-tab

Embed Widget in CRM Card | Bitrix24 REST API and Marketplace Applications
Embed Widget in CRM Card
Embed Widget in CRM Card
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
The example archives and additional materials are available in the lesson
Adding widget to CRM entity form
of the Bitrix24 REST API video course.
Copied
Was the article helpful?
Yes
No
Previous
Embed a Widget in a Lead as a Custom Property
Next
Typical use-cases for REST API in online sales

---

