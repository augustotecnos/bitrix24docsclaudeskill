---
description: 'Tutorials: How to add CRM objects (leads, contacts, companies, deals)'
methods:
- crm.activity.
- crm.activity.add
- crm.activity.todo.add
- crm.address.add
- crm.address.fields
- crm.category.add
- crm.category.list
- crm.company.add
- crm.contact.add
- crm.contact.get
- crm.deal.add
- crm.deal.list
- crm.deal.userfield.list
- crm.documentgenerator.document.add
- crm.documentgenerator.document.download
- crm.documentgenerator.document.download.json
- crm.documentgenerator.numerator.add
- crm.documentgenerator.template.add
- crm.documentgenerator.template.download
- crm.documentgenerator.template.download.json
- crm.duplicate.findbycomm
- crm.enum.activitydirection
- crm.enum.activitytype
- crm.enum.addresstype
- crm.enum.contenttype
- crm.enum.ownertype
- crm.item.
- crm.item.add
- crm.item.list
- crm.lead.add
pages: 18
title: 'Tutorials: How to add CRM objects (leads, contacts, companies, deals)'
---
# Tutorials: How to add CRM objects (leads, contacts, companies, deals)
> Tutorials: How to add CRM objects (leads, contacts, companies, deals)
> **18 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [How to Add Leads and Other Entities](#how-to-add-leads-and-other-entities)
- [Add Lead via Web Form](#add-lead-via-web-form)
- [Add a lead with files via a web form](#add-a-lead-with-files-via-a-web-form)
- [Add an activity to a new lead or deal depending on the CRM mode](#add-an-activity-to-a-new-lead-or-deal-depending-on)
- [Add Repeat Lead](#add-repeat-lead)
- [Add Contact via Web Form](#add-contact-via-web-form)
- [Add a contact with details via a web form](#add-a-contact-with-details-via-a-web-form)
- [Add a Company via Web Form](#add-a-company-via-web-form)
- [Add a Company with Details via Web Form](#add-a-company-with-details-via-web-form)
- [How to Create a Vendor in CRM](#how-to-create-a-vendor-in-crm)
- [Add a deal and company with requisites](#add-a-deal-and-company-with-requisites)
- [Add Calendar Event for Client Interaction](#add-calendar-event-for-client-interaction)
- [How to Add a Template and Create a Document Based on It](#how-to-add-a-template-and-create-a-document-based-)
- [How to Send an Email to a Client on Behalf of an Employee](#how-to-send-an-email-to-a-client-on-behalf-of-an-e)
- [How to Add a Comment to the Timeline of a Smart Process](#how-to-add-a-comment-to-the-timeline-of-a-smart-pr)
- [How to Create a Custom Field in a SPA](#how-to-create-a-custom-field-in-a-spa)
- [How to Set Up Rounding for a Custom Field of Type "Number"](#how-to-set-up-rounding-for-a-custom-field-of-type-)
- [How to Create a New Sales Funnel with Stages in a Smart Process](#how-to-create-a-new-sales-funnel-with-stages-in-a-)

---

## How to Add Leads and Other Entities

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/index

How to Add Leads and Other Entities | Bitrix24 REST API and Marketplace Applications
How to Add Leads and Other Entities
How to Add Leads and Other Entities
Add Lead via Web Form
Add a lead with files via a web form
Add an activity to a new lead or deal depending on the CRM mode
Add Repeat Lead
Add Contact via Web Form
Add a contact with details via a web form
Add a Company via Web Form
Add a Company with Details via Web Form
How to Create a Vendor in CRM
Add a deal and company with requisites
Add Calendar Event for Client Interaction
How to Add a Comment to the Timeline of a Smart Process
How to Create a Custom Field in a SPA
How to Set Up Rounding for a Custom Field of Type "Number"
How to Create a New Sales Funnel with Stages in a Smart Process
Was the article helpful?
Yes
No
Previous
How to do... in CRM?
Next
Add Lead

---

## Add Lead via Web Form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-lead

Add Lead via Web Form | Bitrix24 REST API and Marketplace Applications
Add Lead via Web Form
Add Lead via Web Form
1. Creating the Web Form
2. Creating the Form Handler
Scope:
crm
Who can execute the method: users with the permission to create leads in CRM
You can place a form on your site to collect potential client data. When a client fills out the form, their information will be sent to CRM, and you will be able to process the request.
Setting up the form consists of two steps.
Place the form on an HTML page. It will send data to the handler.
Create a file to process the data. The handler will accept and prepare the data, and then create a lead using the method
crm.lead.add
.
1. Creating the Web Form
1. Creating the Web Form
In Bitrix24, you can automatically create a contact and company from a lead. To make the form suitable for various cases, we will make it universal. For the contact, you need to specify the first name and last name, and for the company — the name. We will create a web form on the site page with five fields:
NAME
— first name, required,
LAST_NAME
— last name,
COMPANY_TITLE
— company name,
EMAIL
— e-mail,
PHONE
— phone.
When submitted, the form sends data to the handler
form.php
.
<
form
id
=
"form_to_crm"
method
=
"POST"
action
=
"form.php"
>
<!-- First Name (required field) -->
<
input
type
=
"text"
name
=
"NAME"
placeholder
=
"First Name"
required
>
<!-- Last Name -->
<
input
type
=
"text"
name
=
"LAST_NAME"
placeholder
=
"Last Name"
>
<!-- Company Name -->
<
input
type
=
"text"
name
=
"COMPANY_TITLE"
placeholder
=
"Company Name"
>
<!-- Email -->
<
input
type
=
"text"
name
=
"EMAIL"
placeholder
=
"E-mail"
>
<!-- Phone -->
<
input
type
=
"text"
name
=
"PHONE"
placeholder
=
"Phone"
>
<!-- Submit Button -->
<
input
type
=
"submit"
value
=
"Submit"
>
</
form
>
<!-- Include jQuery for AJAX request -->
<
script
src
=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
>
</
script
>
<
script
>
$(
document
).
ready
(
function
(
) {
$(
'#form_to_crm'
).
on
(
'submit'
,
function
(
el
) {
el.
preventDefault
();
// Prevent default form submission
var
formData = $(
this
).
serialize
();
// Collect form data
// Send data to the server
$.
ajax
({
'method'
:
'POST'
,
'dataType'
:
'json'
,
'url'
:
'form.php'
,
// Handler file
'data'
: formData,
success
:
function
(
data
) {
alert
(data.
message
);
// Show result
}
});
});
});
</
script
>
2. Creating the Form Handler
2. Creating the Form Handler
To process the values from the form fields and add a lead to CRM, we will create the handler
form.php
.
To add a lead, we will use the method
crm.lead.add
. In the
fields
object, we will pass the fields:
TITLE
— lead title, which can be composed of the first name and last name,
NAME
— lead's first name,
LAST_NAME
— lead's last name,
COMPANY_TITLE
— company name,
PHONE
— phone number,
EMAIL
— e-mail.
The values for the fields are obtained from the form. The system stores the phone and email as an array of objects
crm_multifield
, so they need to be formatted as an array.
If a value exists, we add it as the first element
VALUE
in the array, and the second value specifies the type
VALUE_TYPE
, for example:
WORK
— for phone,
HOME
— for email.
If no values exist, we pass an empty array.
Check which required fields are set for leads in your Bitrix24. All required fields must be passed to the method
crm.lead.add
.
<?php
require_once
(
'crest.php'
);
// Get and sanitize data from the form
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sCompanyTitle
=
htmlspecialchars
(
$_POST
[
"COMPANY_TITLE"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$sEmail
=
htmlspecialchars
(
$_POST
[
"EMAIL"
]);
// Format phone and email for Bitrix24 in crm_multifield format
$arPhone
= (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
)) :
array
();
$arEmail
= (!
empty
(
$sEmail
)) ?
array
(
array
(
'VALUE'
=>
$sEmail
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
();
// Create lead title from first name and last name
$sTitle
=
'From website: '
.
trim
(
$sName
.
' '
.
$sLastName
);
// If there is a company name — add it with a dash after the first name and last name
if
(!
empty
(
$sCompanyTitle
)) {
$sTitle
.=
' — '
.
$sCompanyTitle
;
}
// Send data to Bitrix24
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
=> [
'TITLE'
=>
$sTitle
, // Lead title
'NAME'
=>
$sName
, // First Name
'LAST_NAME'
=>
$sLastName
, // Last Name
'COMPANY_TITLE'
=>
$sCompanyTitle
, // Company Name
'PHONE'
=>
$arPhone
, // Phone
'EMAIL'
=>
$arEmail
, // Email
]
]
);
// Check the result and output the message
if
(!
empty
(
$result
[
'result'
])){
echo
json_encode
([
'message'
=>
'Lead added'
]);
}
elseif
(!
empty
(
$result
[
'error_description'
])){
echo
json_encode
([
'message'
=>
'Lead not added: '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
'Lead not added'
]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
How to Add Leads and Other Entities
Next
Add Lead with Files

---

## Add a lead with files via a web form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-lead-with-files

Add a lead with files via a web form | Bitrix24 REST API and Marketplace Applications
Add a lead with files via a web form
Add a lead with files via a web form
1. Creating the web form
2. Creating the form handler
Preparing data from the form
Creating the lead
Full example of the handler code
Scope:
crm
Who can execute the method: users with the permission to create leads in CRM
You can place a form on the site to collect data from potential clients. When a client fills out the form and attaches files, their data will be sent to CRM, and you will be able to process the request.
Setting up the form consists of two steps.
Place the form on an HTML page. It will send the data to the handler.
Create a file to process the data. The handler will accept and prepare the data, and then create a lead using the method
crm.lead.add
.
1. Creating the web form
1. Creating the web form
In Bitrix24, you can automatically create a contact and a company from a lead. To make the form suitable for various cases, we will make it universal. For the contact, you need to specify the first name and last name, and for the company — the name. We will create a web form on the site page with the following fields:
NAME
— first name, required,
LAST_NAME
— last name,
COMPANY_TITLE
— company name,
EMAIL
— e-mail,
PHONE
— phone.
To allow the client to upload files, we will add the following fields to the form:
FILE
— for one file,
FILES
— for adding multiple files.
When submitted, the form sends data to the handler
form.php
.
<
form
id
=
"form_to_crm"
method
=
"POST"
action
=
"form.php"
enctype
=
"multipart/form-data"
>
<!-- First Name (required field) -->
<
input
type
=
"text"
name
=
"NAME"
placeholder
=
"First Name"
required
>
<!-- Last Name -->
<
input
type
=
"text"
name
=
"LAST_NAME"
placeholder
=
"Last Name"
>
<!-- Company Name -->
<
input
type
=
"text"
name
=
"COMPANY_TITLE"
placeholder
=
"Company Name"
>
<!-- Email -->
<
input
type
=
"text"
name
=
"EMAIL"
placeholder
=
"Email"
>
<!-- Phone -->
<
input
type
=
"text"
name
=
"PHONE"
placeholder
=
"Phone"
>
<!-- Field for one file -->
<
input
type
=
"file"
name
=
"FILE"
>
<!-- Field for multiple files -->
<
input
type
=
"file"
name
=
"FILES"
multiple
>
<!-- Submit button -->
<
input
type
=
"submit"
value
=
"Submit"
>
</
form
>
<!-- Include jQuery for AJAX request -->
<
script
src
=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
>
</
script
>
<
script
>
$(
document
).
ready
(
function
(
) {
$(
'#form_to_crm'
).
on
(
'submit'
,
function
(
el
) {
el.
preventDefault
();
var
formData =
new
FormData
(
this
);
// Collect form data with files
$.
ajax
({
method
:
'POST'
,
url
:
'form.php'
,
data
: formData,
processData
:
false
,
contentType
:
false
,
dataType
:
'json'
,
success
:
function
(
data
) {
alert
(data.
message
);
},
error
:
function
(
) {
alert
(
'Error while submitting the form'
);
}
});
});
});
</
script
>
2. Creating the form handler
2. Creating the form handler
To process the values from the form fields and add a lead to CRM, we will create the handler
form.php
.
Preparing data from the form
Preparing data from the form
To use the data from the form in the lead creation method, we need to prepare it.
Cleaning from HTML tags
Cleaning from HTML tags
We will retrieve and clean the data from the form of HTML tags.
// Retrieve and clean data from the form
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sCompanyTitle
=
htmlspecialchars
(
$_POST
[
"COMPANY_TITLE"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$sEmail
=
htmlspecialchars
(
$_POST
[
"EMAIL"
]);
Preparing files
Preparing files
We will prepare the files for upload to Bitrix24. For each file, we need to pass an array:
with the file name,
a string with the file encoded in Base64.
To encode the file, we will use the function
base64_encode
.
Documentation
How to work with files
// Create variables for arrays with files
$arFiles
= [];
$arSingleFile
= [];
// Process the FILES field with multiple files
if
(!
empty
(
$_FILES
[
'FILES'
][
'tmp_name'
])) {
foreach
(
$_FILES
[
'FILES'
][
'tmp_name'
]
as
$key
=>
$tmpName
) {
if
(!
empty
(
$tmpName
)) {
$arFiles
[] = [
'fileData'
=> [
$_FILES
[
'FILES'
][
'name'
][
$key
],
// file name
base64_encode
(
file_get_contents
(
$tmpName
))
// file content encoded in base64
]
];
}
}
}
// Process the FILE field with one file
if
(!
empty
(
$_FILES
[
'FILE'
][
'tmp_name'
])) {
$arSingleFile
= [
'fileData'
=> [
$_FILES
[
'FILE'
][
'name'
],
// file name
base64_encode
(
file_get_contents
(
$_FILES
[
'FILE'
][
'tmp_name'
]))
// file content encoded in base64
]
];
}
Formatting phone and email
Formatting phone and email
The phone and email are stored in the system as an array of objects
crm_multifield
, so they need to be formatted as an array.
If the value exists, we add it as the first element
VALUE
in the array, and the second value is the type
VALUE_TYPE
, for example:
WORK
— for phone,
HOME
— for email.
If the value does not exist, we pass an empty array.
// Format phone and email for Bitrix24 in crm_multifield format
$arPhone
= (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
)) :
array
();
$arEmail
= (!
empty
(
$sEmail
)) ?
array
(
array
(
'VALUE'
=>
$sEmail
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
();
Forming the lead title
Forming the lead title
We will form the lead title from the first name and last name. For companies, we will add the company name to the title.
// Form the lead title from the first name and last name
$sTitle
=
'From the site: '
.
trim
(
$sName
.
' '
.
$sLastName
);
// If there is a company name — add it with a dash after the first name and last name
if
(!
empty
(
$sCompanyTitle
)) {
$sTitle
.=
' — '
.
$sCompanyTitle
;
}
Creating the lead
Creating the lead
To create a lead, we will use the method
crm.lead.add
. In the
fields
object, we will pass the fields:
TITLE
— lead title,
NAME
— lead first name,
LAST_NAME
— lead last name,
COMPANY_TITLE
— company name,
PHONE
— phone number,
EMAIL
— e-mail,
UF_CRM_LEAD_FILES
— custom field for adding multiple files,
UF_CRM_LEAD_FILE
— custom field for a file.
Custom fields
UF_CRM_*
need to be created in Bitrix24 before creating the lead. Add them on the account manually or using the method
crm.lead.userfield.add
. In the example, replace
UF_CRM_LEAD_FILES
and
UF_CRM_LEAD_FILE
with your field names.
Check which required fields are set for leads in your Bitrix24. All required fields must be passed to the method
crm.lead.add
.
CRest
::
call
(
'crm.lead.add'
,
[
'fields'
=> [
'TITLE'
=>
$sTitle
, // Lead title
'NAME'
=>
$sName
, // First Name
'LAST_NAME'
=>
$sLastName
, // Last Name
'COMPANY_TITLE'
=>
$sCompanyTitle
, // Company Name
'PHONE'
=>
$arPhone
, // Phone
'EMAIL'
=>
$arEmail
, // Email
'UF_CRM_LEAD_FILES'
=>
$arFiles
, // Field
for
adding multiple files
'UF_CRM_LEAD_FILE'
=>
$arSingleFile
// Field
for
a file
]
]
);
As a result, we will get the identifier of the new lead
5
.
{
"result"
:
5
}
Full example of the handler code
Full example of the handler code
<?php
require_once
(
'crest.php'
);
// Retrieve and clean data from the form
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sCompanyTitle
=
htmlspecialchars
(
$_POST
[
"COMPANY_TITLE"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$sEmail
=
htmlspecialchars
(
$_POST
[
"EMAIL"
]);
// Create variables for arrays with files
$arFiles
= [];
$arSingleFile
= [];
// Process the FILES field with multiple files
if
(!
empty
(
$_FILES
[
'FILES'
][
'tmp_name'
])) {
foreach
(
$_FILES
[
'FILES'
][
'tmp_name'
]
as
$key
=>
$tmpName
) {
if
(!
empty
(
$tmpName
)) {
$arFiles
[] = [
'fileData'
=> [
$_FILES
[
'FILES'
][
'name'
][
$key
],
base64_encode
(
file_get_contents
(
$tmpName
))
]
];
}
}
}
// Process the FILE field with one file
if
(!
empty
(
$_FILES
[
'FILE'
][
'tmp_name'
])) {
$arSingleFile
= [
'fileData'
=> [
$_FILES
[
'FILE'
][
'name'
],
base64_encode
(
file_get_contents
(
$_FILES
[
'FILE'
][
'tmp_name'
]))
]
];
}
// Format phone and email for Bitrix24 in crm_multifield format
$arPhone
= (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
)) :
array
();
$arEmail
= (!
empty
(
$sEmail
)) ?
array
(
array
(
'VALUE'
=>
$sEmail
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
();
// Form the lead title from the first name and last name
$sTitle
=
'From the site: '
.
trim
(
$sName
.
' '
.
$sLastName
);
// If there is a company name — add it with a dash after the first name and last name
if
(!
empty
(
$sCompanyTitle
)) {
$sTitle
.=
' — '
.
$sCompanyTitle
;
}
// Send data to Bitrix24
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
=> [
'TITLE'
=>
$sTitle
, // Lead title
'NAME'
=>
$sName
, // First Name
'LAST_NAME'
=>
$sLastName
, // Last Name
'COMPANY_TITLE'
=>
$sCompanyTitle
, // Company Name
'PHONE'
=>
$arPhone
, // Phone
'EMAIL'
=>
$arEmail
, // Email
'UF_CRM_LEAD_FILES'
=>
$arFiles
, // Field
for
adding multiple files
'UF_CRM_LEAD_FILE'
=>
$arSingleFile
// Field
for
a file
]
]
);
// Check the result and output a message
if
(!
empty
(
$result
[
'result'
])){
echo
json_encode
([
'message'
=>
'Lead added successfully'
]);
}
elseif
(!
empty
(
$result
[
'error_description'
])){
echo
json_encode
([
'message'
=>
'Lead not added: '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
'Lead not added'
]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
Add Lead
Next
Add Activity to New Lead or Deal Depending on CRM Mode

---

## Add an activity to a new lead or deal depending on the CRM mode

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-objects-with-crm-mode

Add an activity to a new lead or deal depending on the CRM mode | Bitrix24 REST API and Marketplace Applications
Add an activity to a new lead or deal depending on the CRM mode
Add an activity to a new lead or deal depending on the CRM mode
CRM Modes
1. Creating a web form
2. Creating the form handler
Preparing data from the form
Creating a lead and retrieving lead data
Determining the CRM mode and creating an activity
Full example of the handler code
Scope:
crm
Who can execute the method:
creating a lead — users with the right to create a lead,
adding an activity to a lead or deal — users with the right to modify a lead or deal in CRM
You can place a form on the site to collect potential client data. When a client fills out the form, their data will be sent to the CRM. You will be able to process the request and call the client.
Setting up the form consists of two steps.
Place the form on an HTML page. It will send data to the handler.
Create a file to process the data. The handler will:
accept and prepare the data,
create a lead using the
crm.lead.add
method,
check the CRM mode,
add an activity with a reminder to call either the deal or the lead.
CRM Modes
CRM Modes
In Bitrix24, there are two CRM operation modes.
Simple mode — operates without leads. The system automatically converts a new lead into a deal.
Classic mode — separates potential and existing clients. The lead remains in the system after creation.
In the handler, we will determine which mode the CRM is operating in — simple or classic — and based on that, we will link the call reminder to either the deal or the lead.
User documentation
How to choose the CRM operation mode
1. Creating a web form
1. Creating a web form
In Bitrix24, you can automatically create a contact and company from a lead. To make the form suitable for different cases, we will make it universal. For a contact, you need to specify the first name and last name, and for a company — the name. We will create a web form on the site page with five fields:
NAME
— client's first name, required field,
LAST_NAME
— last name,
COMPANY_TITLE
— company name,
PHONE
— phone,
EMAIL
— email.
When submitted, the form sends data to the handler
form.php
.
<
form
id
=
"form_to_crm"
method
=
"POST"
action
=
"form.php"
>
<!-- First Name (required field) -->
<
input
type
=
"text"
name
=
"NAME"
placeholder
=
"First Name"
required
>
<!-- Last Name -->
<
input
type
=
"text"
name
=
"LAST_NAME"
placeholder
=
"Last Name"
>
<!-- Company Name -->
<
input
type
=
"text"
name
=
"COMPANY_TITLE"
placeholder
=
"Company Name"
>
<!-- Email -->
<
input
type
=
"text"
name
=
"EMAIL"
placeholder
=
"Email"
>
<!-- Phone -->
<
input
type
=
"text"
name
=
"PHONE"
placeholder
=
"Phone"
>
<!-- Submit button -->
<
input
type
=
"submit"
value
=
"Submit"
>
</
form
>
<!-- Include jQuery for AJAX request -->
<
script
src
=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
>
</
script
>
<
script
>
$(
document
).
ready
(
function
(
) {
$(
'#form_to_crm'
).
on
(
'submit'
,
function
(
el
) {
el.
preventDefault
();
// Prevent default form submission
var
formData = $(
this
).
serialize
();
// Collect form data
// Send data to the server
$.
ajax
({
'method'
:
'POST'
,
'dataType'
:
'json'
,
'url'
:
'form.php'
,
// Handler file
'data'
: formData,
success
:
function
(
data
) {
alert
(data.
message
);
// Show result
}
});
});
});
</
script
>
2. Creating the form handler
2. Creating the form handler
We will create a file
form.php
, which will:
accept data from the form,
create a lead,
determine the CRM mode,
add an activity with a reminder to call either the lead or the deal.
Preparing data from the form
Preparing data from the form
We will retrieve and sanitize the data from the form.
// Retrieve and sanitize data from the form
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sCompanyTitle
=
htmlspecialchars
(
$_POST
[
"COMPANY_TITLE"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$sEmail
=
htmlspecialchars
(
$_POST
[
"EMAIL"
]);
The system stores the phone and email as an array of objects
crm_multifield
, so they need to be formatted as an array.
If a value exists, we add it as the first element
VALUE
in the array, and the second value indicates the type
VALUE_TYPE
, for example:
WORK
— for phone,
HOME
— for email.
If there is no value, we pass an empty array.
// Format phone and email for Bitrix24 in crm_multifield format
$arPhone
= (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
)) :
array
();
$arEmail
= (!
empty
(
$sEmail
)) ?
array
(
array
(
'VALUE'
=>
$sEmail
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
();
We will form the lead title from the first name and last name. For companies, we will add the company name to the title.
// Form the lead title from the first name and last name
$sTitle
=
'From the site: '
.
trim
(
$sName
.
' '
.
$sLastName
);
// If there is a company name — add it with a dash after the first name and last name
if
(!
empty
(
$sCompanyTitle
)) {
$sTitle
.=
' — '
.
$sCompanyTitle
;
}
Creating a lead and retrieving lead data
Creating a lead and retrieving lead data
We will use the batch method
CRest::callBatch()
to sequentially execute two methods in one request: creating a lead and retrieving lead data. We will collect the methods in the array
$arData[]
.
To add a lead, we will use the
crm.lead.add
method. In the
fields
object, we will pass the fields:
TITLE
— lead title,
NAME
— lead first name,
LAST_NAME
— lead last name,
COMPANY_TITLE
— company name,
PHONE
— phone number,
EMAIL
— email.
Check which required fields are set for leads in your Bitrix24. All required fields must be passed to the
crm.lead.add
method.
'add_lead'
=> [
'method'
=>
'crm.lead.add'
,
'params'
=> [
'fields'
=> [
'TITLE'
=>
$sTitle
,
// Lead title
'NAME'
=>
$sName
,
// First Name
'LAST_NAME'
=>
$sLastName
,
// Last Name
'COMPANY_TITLE'
=>
$sCompanyTitle
,
// Company Name
'PHONE'
=>
$arPhone
,
// Phone
'EMAIL'
=>
$arEmail
,
// Email
]
]
],
To retrieve lead data, we will use the
crm.lead.get
method. In the
ID
parameter, we will pass the identifier of the created lead
$result[add_lead]
from the result of the
crm.lead.add
method.
'get_lead'
=> [
'method'
=>
'crm.lead.get'
,
'params'
=> [
'id'
=>
$result
[add_lead]
// ID from the result of the crm.lead.add method
]
]
We will pass the array of requests
$arData
to the
CRest::callBatch
method. The result of the method execution will be stored in the variable
$result
.
$result
=
CRest
::
callBatch
(
$arData
);
As a result, we will obtain the identifier of the new lead
add_lead
and lead data
get_lead
.
{
"result"
:
{
"result"
:
{
"add_lead"
:
22
,
// result of the crm.lead.add method execution
"get_lead"
:
{
// result of the crm.lead.get method execution
"ID"
:
"22"
,
"TITLE"
:
"John Doe"
,
"HONORIFIC"
:
null
,
"NAME"
:
"John"
,
"SECOND_NAME"
:
null
,
"LAST_NAME"
:
"Doe"
,
"COMPANY_TITLE"
:
null
,
...
,
"STATUS_ID"
:
"CONVERTED"
,
...
}
}
,
"result_error"
:
[
]
,
...
}
Determining the CRM mode and creating an activity
Determining the CRM mode and creating an activity
If the system successfully created the lead, we will save the following in variables:
$leadId
— lead identifier,
$leadStatus
— lead status
STATUS_ID
.
if
(
empty
(
$result
[
'result'
][
'result_error'
][
'add_lead'
]) && !
empty
(
$result
[
'result'
][
'result'
][
'get_lead'
])) {
$leadId
=
$result
[
'result'
][
'result'
][
'add_lead'
];
$leadStatus
=
$result
[
'result'
][
'result'
][
'get_lead'
][
'STATUS_ID'
];
...
}
Simple mode
Simple mode
In simple mode, when a lead with a filled first name is created, the system automatically converts it into a deal. The lead field
STATUS_ID
takes the value
CONVERTED
.
We check the value of the variable
$leadStatus
. If the value is equal to
'CONVERTED'
— the CRM is operating in simple mode and the lead has already been converted into a deal.
In classic mode, a new lead can also be automatically converted into a deal using automation tools.
You can accurately determine the CRM operation mode using the special method
crm.settings.mode.get
.
To obtain the deal identifier, we will use the
crm.deal.list
method. We will specify the
select
field as
ID
, and in the filter
filter
, we will pass the field
LEAD_ID
with the lead identifier from the variable
$leadId
.
if
(
$leadStatus
==
'CONVERTED'
) {
// Simple mode: searching for the deal created from the lead
$resultDeal
=
CRest
::
call
(
'crm.deal.list'
, [
'select'
=> [
'ID'
],
'filter'
=> [
'LEAD_ID'
=>
$leadId
]
]);
As a result, we will obtain the deal identifier.
"result"
:
[
{
"ID"
:
"1811"
}
]
,
To add an activity to the deal, we will use the
crm.activity.todo.add
method. We will pass the fields:
ownerTypeId
— identifier of the CRM object type. You can obtain identifiers using the
crm.enum.ownertype
method. We will specify the value —
2
, which means deal,
ownerId
— identifier of the CRM entity. We will specify the deal identifier obtained in the previous request,
deadline
— deadline for the activity,
title
— activity title,
description
— activity description.
if
(!
empty
(
$resultDeal
[
'result'
][
0
][
'ID'
])) {
$dealId
=
$resultDeal
[
'result'
][
0
][
'ID'
];
// Linking the activity to the deal
CRest
::
call
(
'crm.activity.todo.add'
,
[
'ownerTypeId'
=>
2
, //
object
type — deal
'ownerId'
=>
$dealId
, // deal identifier
'deadline'
=>
date
(
"Y-m-d H:i:s"
,
time
() +
3600
), // current time +
1
hour
'title'
=>
'Call the client'
,
'description'
=>
'Filled out the request on the site'
,
]
);
}
Classic mode
Classic mode
In classic mode, the system does not convert the lead, so we link the activity to the created lead.
To add an activity to the lead, we will use the
crm.activity.todo.add
method. We will pass the fields:
ownerTypeId
— identifier of the CRM object type. You can obtain identifiers using the
crm.enum.ownertype
method. We will specify the value —
1
, which means lead,
ownerId
— identifier of the CRM entity. We will specify the identifier of the new lead,
deadline
— deadline for the activity,
title
— activity title,
description
— activity description.
// Classic mode: linking the activity to the lead
CRest
::
call
(
'crm.activity.todo.add'
,
[
'ownerTypeId'
=>
1
, //
object
type — lead
'ownerId'
=>
$leadId
, // lead identifier
'deadline'
=>
date
(
"Y-m-d H:i:s"
,
time
() +
3600
), // current time +
1
hour
'title'
=>
'Call the client'
,
'description'
=>
'Filled out the request on the site'
,
]
);
Full example of the handler code
Full example of the handler code
How to Use Examples in Documentation
<?php
// Retrieve and sanitize data from the form
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sCompanyTitle
=
htmlspecialchars
(
$_POST
[
"COMPANY_TITLE"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$sEmail
=
htmlspecialchars
(
$_POST
[
"EMAIL"
]);
// Format phone and email for Bitrix24 in crm_multifield format
$arPhone
= (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
)) :
array
();
$arEmail
= (!
empty
(
$sEmail
)) ?
array
(
array
(
'VALUE'
=>
$sEmail
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
();
// Form the lead title from the first name and last name
$sTitle
=
'From the site: '
.
trim
(
$sName
.
' '
.
$sLastName
);
// If there is a company name — add it with a dash after the first name and last name
if
(!
empty
(
$sCompanyTitle
)) {
$sTitle
.=
' — '
.
$sCompanyTitle
;
}
$arData
= [
'add_lead'
=> [
'method'
=>
'crm.lead.add'
,
'params'
=> [
'fields'
=> [
'TITLE'
=>
$sTitle
,
// Lead title
'NAME'
=>
$sName
,
// First Name
'LAST_NAME'
=>
$sLastName
,
// Last Name
'COMPANY_TITLE'
=>
$sCompanyTitle
,
// Company Name
'PHONE'
=>
$arPhone
,
// Phone
'EMAIL'
=>
$arEmail
,
// Email
]
]
],
'get_lead'
=> [
'method'
=>
'crm.lead.get'
,
'params'
=> [
'id'
=>
'$result[add_lead]'
// ID from the result of the crm.lead.add method
]
]
];
$result
=
CRest
::
callBatch
(
$arData
);
if
(
empty
(
$result
[
'result'
][
'result_error'
][
'add_lead'
]) && !
empty
(
$result
[
'result'
][
'result'
][
'get_lead'
])) {
$leadId
=
$result
[
'result'
][
'result'
][
'add_lead'
];
// save the lead identifier in a variable
$leadStatus
=
$result
[
'result'
][
'result'
][
'get_lead'
][
'STATUS_ID'
];
// save the lead status in a variable
if
(
$leadStatus
==
'CONVERTED'
) {
// Simple mode: searching for the deal created from the lead
$resultDeal
=
CRest
::
call
(
'crm.deal.list'
, [
'select'
=> [
'ID'
],
'filter'
=> [
'LEAD_ID'
=>
$leadId
]
]);
if
(!
empty
(
$resultDeal
[
'result'
][
0
][
'ID'
])) {
$dealId
=
$resultDeal
[
'result'
][
0
][
'ID'
];
CRest
::
call
(
// Adding an activity to the deal
'crm.activity.todo.add'
,
[
'ownerTypeId'
=>
2
, //
object
type — deal
'ownerId'
=>
$dealId
, // deal identifier
'deadline'
=>
date
(
"Y-m-d H:i:s"
,
time
() +
3600
), // current time +
1
hour
'title'
=>
'Call the client'
,
'description'
=>
'Filled out the request on the site'
,
]
);
}
}
else
{
CRest
::
call
(
// Classic
mode
: adding an activity to the
new
lead
'crm.activity.todo.add'
,
[
'ownerTypeId'
=>
1
, //
object
type — lead
'ownerId'
=>
$leadId
, // lead identifier
'deadline'
=>
date
(
"Y-m-d H:i:s"
,
time
() +
3600
), // current time +
1
hour
'title'
=>
'Call the client'
,
'description'
=>
'Filled out the request on the site'
,
]
);
}
echo
json_encode
([
'message'
=>
'Activity added to the lead or deal'
]);
}
else
{
$errors
= [];
if
(!
empty
(
$result
[
'result'
][
'result_error'
][
'add_lead'
])) {
$errors
[] =
'Error adding lead: '
.
$result
[
'result'
][
'result_error'
][
'add_lead'
][
'error_description'
];
}
if
(!
empty
(
$result
[
'result'
][
'result_error'
][
'get_lead'
])) {
$errors
[] =
'Error getting lead: '
.
$result
[
'result'
][
'result_error'
][
'get_lead'
][
'error_description'
];
}
echo
json_encode
([
'message'
=> !
empty
(
$errors
) ?
implode
(
'; '
,
$errors
) :
'Unknown error'
]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
Add Lead with Files
Next
Add Repeat Lead

---

## Add Repeat Lead

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-repeat-lead

Add Repeat Lead | Bitrix24 REST API and Marketplace Applications
Add Repeat Lead
Add Repeat Lead
1. Create Web Form
2. Create Form Handler
Get Data from the Form
Search for Duplicate Leads
Process Duplicates
Add New Lead
Complete Example of the Handler Code
Continue Learning
Scope:
crm
Who can execute the method: users with read access permission for leads, contacts, companies, and permission to create leads.
When a client fills out a form on the site, their data is sent to the handler. The script searches the CRM for matches by phone or email among leads, contacts, and companies. If matches are found, the lead is marked as a repeat and linked to the existing record. This approach helps avoid duplicates and increases the efficiency of managers.
The repeat lead mode must be enabled in Bitrix24. Read more in the article
Repeat Leads and Deals
.
The setup consists of two stages:
Prepare the fields and place the form on the page.
Create a handler file that sequentially calls the methods
crm.duplicate.findbycomm
,
crm.lead.list
,
crm.lead.add
.
1. Create Web Form
1. Create Web Form
Create an HTML form with the fields:
NAME
— client's first name, required field,
LAST_NAME
— last name,
PHONE
— phone number,
EMAIL
— email address.
The form sends data using the
POST
method to the file
form.php
.
<
script
src
=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
>
</
script
>
<
script
>
$(
document
).
ready
(
function
(
) {
$(
'#form_to_crm'
).
on
(
'submit'
,
function
(
el
) {
// event submit form
el.
preventDefault
();
// the default action of the event will not be triggered
var
formData = $(
this
).
serialize
();
$.
ajax
({
'method'
:
'POST'
,
'dataType'
:
'json'
,
'url'
:
'form.php'
,
// file for saving filled forms
'data'
: formData,
success
:
function
(
data
) {
// success callback
alert
(data.
message
);
}
});
});
});
</
script
>
<
form
id
=
"form_to_crm"
>
<
input
type
=
"text"
name
=
"NAME"
placeholder
=
"Name"
required
>
<
input
type
=
"text"
name
=
"LAST_NAME"
placeholder
=
"Last name"
>
<
input
type
=
"text"
name
=
"PHONE"
placeholder
=
"Phone"
>
<
input
type
=
"text"
name
=
"EMAIL"
placeholder
=
"E-mail"
>
<
input
type
=
"submit"
value
=
"Submit"
>
</
form
>
2. Create Form Handler
2. Create Form Handler
Create the file
form.php
. The handler will process the data, check for duplicates, and create a lead.
Get Data from the Form
Get Data from the Form
Retrieve and safely process data from the fields
NAME
,
LAST_NAME
,
PHONE
,
EMAIL
to avoid XSS attacks.
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$sEmail
=
htmlspecialchars
(
$_POST
[
"EMAIL"
]);
Form an array
$arFields
with the new lead's data.
$arFields
= [
'TITLE'
=>
'From the site: '
.
implode
(
' '
, [
$sName
,
$sLastName
]),
'NAME'
=> (!
empty
(
$sName
)) ?
$sName
:
'Empty name'
,
'LAST_NAME'
=>
$sLastName
,
'PHONE'
=> (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
(),
'EMAIL'
=> (!
empty
(
$sEmail
)) ?
array
(
array
(
'VALUE'
=>
$sEmail
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
()
];
The lead's title is formed as
From the site: FirstName LastName
.
The system stores phone numbers and email addresses as arrays of objects
crm_multifield
, so we form the arrays
PHONE
and
EMAIL
using the values
$sPhone
and
$sEmail
.
In the
VALUE
fields, we write
$sPhone
and
$sEmail
.
In the
VALUE_TYPE
fields, we pass
types
, for example,
HOME
.
If there are no values in the variables
$sPhone
and
$sEmail
, we specify empty arrays.
Search for Duplicate Leads
Search for Duplicate Leads
To find duplicate leads by phone and email, we use the method
crm.duplicate.findbycomm
twice. We need to pass the following data:
entity_type
— object type. We pass
LEAD
— lead.
type
— communication type. For the first call, we specify
PHONE
, and for the second —
EMAIL
.
PHONE
— array with the phone
$arPhone
obtained from the form.
Search by phone,
"type" => "PHONE"
.
if
(!
empty
(
$sPhone
)){
$arResultDuplicate
=
CRest
::
call
(
'crm.duplicate.findbycomm'
, [
"entity_type"
=>
"LEAD"
,
"type"
=>
"PHONE"
,
"values"
=>
array
(
$sPhone
)
]);
if
(!
empty
(
$arResultDuplicate
[
'result'
][
'LEAD'
])){
$arLeadDuplicate
=
array_merge
(
$arLeadDuplicate
,
$arResultDuplicate
[
'result'
][
'LEAD'
]);
}
}
Search for duplicates by email,
"type" => "EMAIL"
.
if
(!
empty
(
$sEmail
)){
$arResultDuplicate
=
CRest
::
call
(
'crm.duplicate.findbycomm'
, [
"entity_type"
=>
"LEAD"
,
"type"
=>
"EMAIL"
,
"values"
=>
array
(
$sEmail
)
]);
if
(!
empty
(
$arResultDuplicate
[
'result'
][
'LEAD'
])){
$arLeadDuplicate
=
array_merge
(
$arLeadDuplicate
,
$arResultDuplicate
[
'result'
][
'LEAD'
]);
}
}
The identifiers of found duplicates are combined in the array
$arLeadDuplicate
.
Process Duplicates
Process Duplicates
If duplicates are found, we call the method
crm.lead.list
.
Apply a filter by ID and status
CONVERTED
.
Select fields:
ID
,
COMPANY_ID
,
CONTACT_ID
.
Save the result in the array
$arDuplicateLead
.
Fill the fields
COMPANY_ID
and
CONTACT_ID
in the array
$arFields
with values from
$arDuplicateLead
.
if
(!
empty
(
$arLeadDuplicate
)){
$arDuplicateLead
=
CRest
::
call
(
'crm.lead.list'
, [
"filter"
=> [
'=ID'
=>
$arLeadDuplicate
,
'STATUS_ID'
=>
'CONVERTED'
],
"select"
=> [
'ID'
,
'COMPANY_ID'
,
'CONTACT_ID'
]
]);
if
(!
empty
(
$arDuplicateLead
[
'result'
])){
$sCompany
=
reset
(
array_diff
(
array_column
(
$arDuplicateLead
[
'result'
],
'COMPANY_ID'
,
'ID'
), [
''
]));
$sContact
=
reset
(
array_diff
(
array_column
(
$arDuplicateLead
[
'result'
],
'CONTACT_ID'
,
'ID'
), [
''
]));
if
(
$sCompany
>
0
)
$arFields
[
'COMPANY_ID'
] =
$sCompany
;
if
(
$sContact
>
0
)
$arFields
[
'CONTACT_ID'
] =
$sContact
;
}
}
Add New Lead
Add New Lead
To add a lead, we use the method
crm.lead.add
. We pass the array
$arFields
.
Check which required fields are set for leads in your Bitrix24. All required fields must be passed to the method
crm.lead.add
.
$result
=
CRest
::
call
(
'crm.lead.add'
, [
'fields'
=>
$arFields
]);
If the lead is created successfully, the method will return its identifier. If you receive an
error
, review the possible error descriptions in the documentation for the method
crm.lead.add
.
{
"result"
:
3289
}
Complete Example of the Handler Code
Complete Example of the Handler Code
<?php
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$sEmail
=
htmlspecialchars
(
$_POST
[
"EMAIL"
]);
$arFields
= [
'TITLE'
=>
'From the site: '
.
implode
(
' '
, [
$sName
,
$sLastName
]),
'LAST_NAME'
=>
$sLastName
,
'PHONE'
=> (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
(),
'EMAIL'
=> (!
empty
(
$sEmail
)) ?
array
(
array
(
'VALUE'
=>
$sEmail
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
()
];
$arLeadDuplicate
= [];
if
(!
empty
(
$sPhone
)){
// search for duplicates by phone
$arResultDuplicate
=
CRest
::
call
(
'crm.duplicate.findbycomm'
, [
"entity_type"
=>
"LEAD"
,
"type"
=>
"PHONE"
,
"values"
=>
array
(
$sPhone
)
]);
if
(!
empty
(
$arResultDuplicate
[
'result'
][
'LEAD'
])){
$arLeadDuplicate
=
array_merge
(
$arLeadDuplicate
,
$arResultDuplicate
[
'result'
][
'LEAD'
]);
}
}
if
(!
empty
(
$sEmail
)) {
// search for duplicates by email
$arResultDuplicate
=
CRest
::
call
(
'crm.duplicate.findbycomm'
, [
"entity_type"
=>
"LEAD"
,
"type"
=>
"EMAIL"
,
"values"
=> [
$sEmail
]
]);
if
(!
empty
(
$arResultDuplicate
[
'result'
][
'LEAD'
])) {
$arLeadDuplicate
=
array_merge
(
$arLeadDuplicate
,
$arResultDuplicate
[
'result'
][
'LEAD'
]);
}
}
if
(!
empty
(
$arLeadDuplicate
)){
// get duplicate lead with selection of related contact and company fields
$arDuplicateLead
=
CRest
::
call
(
'crm.lead.list'
, [
"filter"
=> [
'=ID'
=>
$arLeadDuplicate
,
'STATUS_ID'
=>
'CONVERTED'
,
],
'select'
=> [
'ID'
,
'COMPANY_ID'
,
'CONTACT_ID'
]
]);
if
(!
empty
(
$arDuplicateLead
[
'result'
])){
$sCompany
=
reset
(
array_diff
(
array_column
(
$arDuplicateLead
[
'result'
],
'COMPANY_ID'
,
'ID'
), [
''
]));
$sContact
=
reset
(
array_diff
(
array_column
(
$arDuplicateLead
[
'result'
],
'CONTACT_ID'
,
'ID'
), [
''
]));
if
(
$sCompany
>
0
)
$arFields
[
'COMPANY_ID'
] =
$sCompany
;
if
(
$sContact
>
0
)
$arFields
[
'CONTACT_ID'
] =
$sContact
;
}
}
$result
=
CRest
::
call
(
'crm.lead.add'
, // create duplicate lead
[
'fields'
=>
$arFields
]
);
if
(!
empty
(
$result
[
'result'
])){
echo
json_encode
([
'message'
=>
'Lead added'
]);
}
elseif
(!
empty
(
$result
[
'error_description'
])){
echo
json_encode
([
'message'
=>
'Lead not added: '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
'Lead not added'
]);
}
?>
Continue Learning
Continue Learning
Get leads, contacts, and companies with matching data crm.duplicate.findbycomm
Get the list of leads crm.lead.list
Create a New Lead crm.lead.add
Copied
Was the article helpful?
Yes
No
Previous
Add Activity to New Lead or Deal Depending on CRM Mode
Next
Add Contact

---

## Add Contact via Web Form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-contact

Add Contact via Web Form | Bitrix24 REST API and Marketplace Applications
Add Contact via Web Form
Add Contact via Web Form
1. Creating the Web Form
2. Creating the Form Handler
Scope:
crm
Who can execute the method: users with permission to create contacts in CRM
You can place a form on the site to collect client data. When a client fills out the form, their data will be sent to CRM, and you will be able to process the request.
Setting up the form consists of two steps.
Place the form on an HTML page. It will send the data to the handler.
Create a file to process the data. The handler will accept and prepare the data, and then create a contact using the method
crm.contact.add
.
1. Creating the Web Form
1. Creating the Web Form
Let's create a web form on the site page with four fields:
NAME
— contact's first name, required,
LAST_NAME
— last name,
EMAIL
— email address,
PHONE
— phone number.
When submitted, the form sends data to the handler
form.php
.
<
form
id
=
"form_to_crm"
method
=
"POST"
action
=
"form.php"
>
<!-- First name, required field -->
<
input
type
=
"text"
name
=
"NAME"
placeholder
=
"First Name"
required
>
<!-- Last name -->
<
input
type
=
"text"
name
=
"LAST_NAME"
placeholder
=
"Last Name"
>
<!-- Email -->
<
input
type
=
"text"
name
=
"EMAIL"
placeholder
=
"Email"
>
<!-- Phone -->
<
input
type
=
"text"
name
=
"PHONE"
placeholder
=
"Phone"
>
<!-- Submit button -->
<
input
type
=
"submit"
value
=
"Submit"
>
</
form
>
<!-- Include jQuery for AJAX request -->
<
script
src
=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
>
</
script
>
<
script
>
$(
document
).
ready
(
function
(
) {
$(
'#form_to_crm'
).
on
(
'submit'
,
function
(
el
) {
el.
preventDefault
();
// Prevent default form submission
var
formData = $(
this
).
serialize
();
// Gather form data
// Send data to the server
$.
ajax
({
'method'
:
'POST'
,
'dataType'
:
'json'
,
'url'
:
'form.php'
,
// Handler file
'data'
: formData,
success
:
function
(
data
) {
alert
(data.
message
);
// Show result
}
});
});
});
</
script
>
2. Creating the Form Handler
2. Creating the Form Handler
To process the values from the form fields and add a contact to CRM, we will create the handler
form.php
.
To add a contact, we will use the method
crm.contact.add
. In the
fields
object, we will pass the fields:
NAME
— contact's first name,
LAST_NAME
— last name,
PHONE
— phone number,
EMAIL
— email address.
The values of the fields are obtained from the form. The system stores phone and email as an array of objects
crm_multifield
, so they need to be formatted as an array.
If a value exists, we add it as the first element
VALUE
in the array, and the second value specifies the type
VALUE_TYPE
, for example:
WORK
— for phone,
HOME
— for email.
If there is no value, we pass an empty array.
Check which required fields are set for contacts in your Bitrix24. All required fields must be passed to the method
crm.contact.add
.
<?php
require_once
(
'crest.php'
);
// Get and sanitize data from the form
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$sEmail
=
htmlspecialchars
(
$_POST
[
"EMAIL"
]);
// Format phone and email for Bitrix24 in crm_multifield format
$arPhone
= (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
)) :
array
();
$arEmail
= (!
empty
(
$sEmail
)) ?
array
(
array
(
'VALUE'
=>
$sEmail
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
();
// Send data to Bitrix24
$result
=
CRest
::
call
(
'crm.contact.add'
,
[
'fields'
=> [
'NAME'
=>
$sName
, // First Name
'LAST_NAME'
=>
$sLastName
, // Last Name
'PHONE'
=>
$arPhone
, // Phone
'EMAIL'
=>
$arEmail
, // Email
]
]
);
// Check the result and output the message
if
(!
empty
(
$result
[
'result'
])){
echo
json_encode
([
'message'
=>
'Contact added'
]);
}
elseif
(!
empty
(
$result
[
'error_description'
])){
echo
json_encode
([
'message'
=>
'Contact not added: '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
'Contact not added'
]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
Add Repeat Lead
Next
Add Contact with Details

---

## Add a contact with details via a web form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-contact-with-requisite

Add a contact with details via a web form | Bitrix24 REST API and Marketplace Applications
Add a contact with details via a web form
Add a contact with details via a web form
1. Creating the web form
Full example of the page code with the form
2. Creating the form handler
Preparing the data
Adding the contact
Adding details to the contact
Adding an address for the detail
Full example of the handler code
Scope:
crm
Who can execute the method: users with permission to create contacts in CRM
You can place a form on the site to collect client data and details. When a client fills out the form, their data will be sent to CRM, and you will be able to process the request.
Setting up the form consists of two steps.
We will place the form on a PHP page. In the page code, we will retrieve the list of detail templates and address fields for the form. The form data will be sent to the handler.
We will create a file to process the data. The handler will accept and prepare the data, and then create a contact with the details.
1. Creating the web form
1. Creating the web form
To generate the form fields, we will use data from Bitrix24. To get information about the detail settings, we will sequentially execute two methods:
crm.address.fields
— we retrieve the list of address fields. The result is saved in
arAddressFields
.
$arAddressFields
=
CRest
::
call
(
'crm.address.fields'
, []);
crm.requisite.preset.list
— we request the list of detail templates. Using the
select
parameter, we choose the
ID
and
NAME
fields for each template. The result is saved in
arRequisiteType
.
$arRequisiteType
=
CRest
::
call
(
'crm.requisite.preset.list'
, [
'select'
=> [
"ID"
,
"NAME"
]
]
);
We will add a web form to the site page with the following fields:
REQ_TYPE
— a dropdown list with the type of details from the
arRequisiteType
array, required,
NAME
— contact's first name, required,
LAST_NAME
— last name,
PHONE
— phone number,
${addressFieldsInputs}
— address fields, which are created dynamically from the
arAddressFields
array.
The form sends data using the
POST
method to the
form.php
file.
Full example of the page code with the form
Full example of the page code with the form
How to Use Examples in Documentation
<?php
// Retrieve the list of address fields and detail templates
$arAddressFields
=
CRest
::
call
(
'crm.address.fields'
, []);
$arRequisiteType
=
CRest
::
call
(
'crm.requisite.preset.list'
, [
'select'
=> [
"ID"
,
"NAME"
]
]);
if
(!
empty
(
$arRequisiteType
[
'result'
])):
$arRequisiteType
=
array_column
(
$arRequisiteType
[
'result'
],
'NAME'
,
'ID'
);
// Remove system and unused address fields
$excludeFields
= [
'TYPE_ID'
,
'ENTITY_TYPE_ID'
,
'ENTITY_ID'
,
'COUNTRY_CODE'
,
'ANCHOR_TYPE_ID'
,
'ANCHOR_ID'
];
foreach
(
$excludeFields
as
$field
) {
unset
(
$arAddressFields
[
'result'
][
$field
]);
}
?>
<form id=
"form_to_crm"
>
<select name=
"REQ_TYPE"
required>
<option value=
""
disabled selected>Select the type of details</option>
<?php
foreach
(
$arRequisiteType
as
$id
=>
$name
):
?>
<option value=
"<?=
$id
?>"
>
<?=
$name
?>
</option>
<?php
endforeach
;
?>
</select>
<input type=
"text"
name=
"NAME"
placeholder=
"First Name"
required>
<input type=
"text"
name=
"LAST_NAME"
placeholder=
"Last Name"
>
<input type=
"text"
name=
"PHONE"
placeholder=
"Phone"
>
<?php
foreach
(
$arAddressFields
[
'result'
]
as
$key
=>
$arField
):
?>
<input type=
"text"
name=
"ADDRESS[<?=
$key
?>]"
placeholder=
"<?=
$arField
['title']?>"
<?=
$arField
[
'isRequired'
] ?
'required'
:
''
?>
>
<?php
endforeach
;
?>
<input type=
"submit"
value=
"Submit"
>
</form>
<?php
else
:
?>
<p>No available types of details.</p>
<?php
endif
;
?>
<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
></script>
<script>
$(document).
ready
(function() {
$(
'#form_to_crm'
).
on
(
'submit'
, function(el) {
el.
preventDefault
();
$.
ajax
({
method
:
'POST'
,
dataType
:
'json'
,
url
:
'form.php'
,
data
: $(this).
serialize
(),
success:
function
(
data
)
{
alert
(data.message);
}
});
});
});
</script>
2. Creating the form handler
2. Creating the form handler
To process the values from the form fields and add a contact to CRM, we will create a handler
form.php
.
Preparing the data
Preparing the data
We retrieve and clean the data from the form:
REQ_TYPE
is converted to a number,
NAME
,
LAST_NAME
,
PHONE
are cleaned of HTML tags.
$iRequisitePresetID
=
intVal
(
$_POST
[
"REQ_TYPE"
]);
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
We prepare the address fields and collect them into the
$arAddress
array.
The values of the fields from the form are cleaned of HTML tags.
We add the address type
TYPE_ID
. The address types can be obtained using the method
crm.enum.addresstype
. We will specify the value —
1
, which means the actual address.
We add the identifier of the
object type
ENTITY_TYPE_ID
. The identifiers can be obtained using the method
crm.enum.ownertype
. We will specify the value —
8
, which means detail.
$arAddress
= [];
foreach
(
$_POST
[
"ADDRESS"
]
as
$key
=>
$val
) {
$arAddress
[
$key
] =
htmlspecialchars
(
$val
);
}
$arAddress
[
'TYPE_ID'
] =
1
;
$arAddress
[
'ENTITY_TYPE_ID'
] =
8
;
The system stores the phone as an array of objects
crm_multifield
, so it needs to be formatted as an array.
We add the phone as the first element
VALUE
in the array, and the second value specifies the type
VALUE_TYPE
, for example,
WORK
.
For an empty value, we pass an empty array.
$arPhone
= !
empty
(
$sPhone
) ? [[
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
]] : [];
Adding the contact
Adding the contact
To create a contact, we will execute the method
crm.contact.add
. In the
fields
object, we pass the fields:
NAME
— contact's first name,
LAST_NAME
— last name,
PHONE
— phone.
Check which required fields are set for contacts in your Bitrix24. All required fields must be passed to the method
crm.contact.add
.
CRest
::
call
(
'crm.contact.add'
, [
'fields'
=> [
'NAME'
=>
$sName
,
'LAST_NAME'
=>
$sLastName
,
'PHONE'
=>
$arPhone
]
]
);
As a result, we will receive the identifier of the new contact, for example,
23
.
{
"result"
:
23
}
Adding details to the contact
Adding details to the contact
To add details to the contact, we will execute the method
crm.requisite.add
. In the
fields
object, we pass the fields:
ENTITY_TYPE_ID
— identifier of the
object type
. The identifiers can be obtained using the method
crm.enum.ownertype
. In the example, we will specify the value
3
, which means contact,
ENTITY_ID
— identifier of the contact received in the previous request,
PRESET_ID
— identifier of the detail template received from the form,
ACTIVE
— activity of the detail
Y
,
NAME
— name of the detail, for example, we will combine the first name and last name of the contact.
CRest
::
call
(
'crm.requisite.add'
,
[
'fields'
=> [
'ENTITY_TYPE_ID'
=>
3
,
'ENTITY_ID'
=>
$contactId
,
'PRESET_ID'
=>
$iRequisitePresetID
,
'ACTIVE'
=>
'Y'
,
'NAME'
=>
implode
(
' '
, [
$sName
,
$sLastName
]),
]
]
);
As a result, we will receive the identifier of the details.
{
"result"
:
34
}
Adding an address for the detail
Adding an address for the detail
We will add an address for the detail using the method
crm.address.add
, if the detail was created successfully. In
$arAddress
, we add
ENTITY_ID
with the
ID
of the detail from the response of the previous request. In the
fields
object, we pass the array
$arAddress
with the address fields.
if
(!
empty
(
$resultRequisite
[
'result'
])) {
$arAddress
[
'ENTITY_ID'
] =
$resultRequisite
[
'result'
];
CRest
::
call
(
'crm.address.add'
,
[
'fields'
=>
$arAddress
]
);
}
Full example of the handler code
Full example of the handler code
<?php
require_once
(
'crest.php'
);
// Retrieve and clean the form data
$iRequisitePresetID
=
intVal
(
$_POST
[
"REQ_TYPE"
]);
$sName
=
htmlspecialchars
(
$_POST
[
"NAME"
]);
$sLastName
=
htmlspecialchars
(
$_POST
[
"LAST_NAME"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
// Prepare the address
$arAddress
= [];
foreach
(
$_POST
[
"ADDRESS"
]
as
$key
=>
$val
) {
$arAddress
[
$key
] =
htmlspecialchars
(
$val
);
}
$arAddress
[
'TYPE_ID'
] =
1
;
// Actual address
$arAddress
[
'ENTITY_TYPE_ID'
] =
8
;
// Object type — detail
// Format the phone for Bitrix24
$arPhone
= !
empty
(
$sPhone
) ? [[
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
]] : [];
// Create the contact
$result
=
CRest
::
call
(
'crm.contact.add'
, [
'fields'
=> [
'NAME'
=>
$sName
,
'LAST_NAME'
=>
$sLastName
,
'PHONE'
=>
$arPhone
]
]);
// Get the identifier of the new contact
if
(!
empty
(
$result
[
'result'
])) {
$contactId
=
$result
[
'result'
];
// Add details for the new contact
$resultRequisite
=
CRest
::
call
(
'crm.requisite.add'
, [
'fields'
=> [
'ENTITY_TYPE_ID'
=>
3
, // Object type — contact
'ENTITY_ID'
=>
$contactId
,
'PRESET_ID'
=>
$iRequisitePresetID
,
'ACTIVE'
=>
'Y'
,
'NAME'
=>
implode
(
' '
, [
$sName
,
$sLastName
]),
]
]);
// Add address if details were created successfully
if
(!
empty
(
$resultRequisite
[
'result'
])) {
$arAddress
[
'ENTITY_ID'
] =
$resultRequisite
[
'result'
];
CRest
::
call
(
'crm.address.add'
, [
'fields'
=>
$arAddress
]);
}
echo
json_encode
([
'message'
=>
'Contact successfully added'
]);
}
else
{
$error
= !
empty
(
$result
[
'error_description'
]) ?
$result
[
'error_description'
] :
'Unknown error'
;
echo
json_encode
([
'message'
=>
'Error: '
.
$error
]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
Add Contact
Next
Add Company

---

## Add a Company via Web Form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-company

Add a Company via Web Form | Bitrix24 REST API and Marketplace Applications
Add a Company via Web Form
Add a Company via Web Form
1. Creating the Web Form
2. Creating the Form Handler
Scope:
crm
Who can execute the method: users with permission to create companies in CRM
You can place a form on the site to collect client data. When a client fills out the form, their data will be sent to CRM, and you will be able to process the request.
Setting up the form consists of two steps.
Place the form on an HTML page. It will send data to the handler.
Create a file to process the data. The handler will accept and prepare the data, and then create a company using the method
crm.company.add
.
1. Creating the Web Form
1. Creating the Web Form
Let's create a web form on the website page with three fields:
TITLE
— company name, required,
EMAIL
— email address,
PHONE
— phone number.
When submitted, the form sends data to the handler
form.php
.
<
form
id
=
"form_to_crm"
method
=
"POST"
action
=
"form.php"
>
<!-- Company name (required field) -->
<
input
type
=
"text"
name
=
"TITLE"
placeholder
=
"Company name"
required
>
<!-- Email address -->
<
input
type
=
"text"
name
=
"EMAIL"
placeholder
=
"Email"
>
<!-- Phone number -->
<
input
type
=
"text"
name
=
"PHONE"
placeholder
=
"Phone"
>
<!-- Submit button -->
<
input
type
=
"submit"
value
=
"Submit"
>
</
form
>
<!-- Include jQuery for AJAX request -->
<
script
src
=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
>
</
script
>
<
script
>
$(
document
).
ready
(
function
(
) {
// Submit the form without reloading the page
$(
'#form_to_crm'
).
on
(
'submit'
,
function
(
el
) {
el.
preventDefault
();
// Cancel the default submission
// Get form data
var
formData = $(
this
).
serialize
();
// Send data to the server
$.
ajax
({
'method'
:
'POST'
,
'dataType'
:
'json'
,
'url'
:
'form.php'
,
// Handler file
'data'
: formData,
success
:
function
(
data
) {
alert
(data.
message
);
// Show the result
}
});
});
});
</
script
>
2. Creating the Form Handler
2. Creating the Form Handler
To process the values from the form fields and add a company to CRM, we will create the handler
form.php
.
To add a company, we will use the method
crm.company.add
. In the
fields
object, we pass the fields:
TITLE
— company name,
COMPANY_TYPE
— type of company. We specify
CUSTOMER
, as only clients of the company fill out the form,
PHONE
— phone number,
EMAIL
— email address.
The values for
TITLE
,
PHONE
, and
EMAIL
are obtained from the form. The system stores phone and email as an array of objects
crm_multifield
, so they need to be formatted as an array.
If a value exists, we add it as the first element
VALUE
in the array, and the second value specifies the type
VALUE_TYPE
, for example:
WORK
— for phone,
HOME
— for email.
If no value exists, we pass an empty array.
Check which required fields are set for companies in your Bitrix24. All required fields must be passed to the method
crm.company.add
.
<?
// Get data from the form
$sTitle
=
htmlspecialchars
(
$_POST
[
"TITLE"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$sEmail
=
htmlspecialchars
(
$_POST
[
"EMAIL"
]);
// Format phone and email for Bitrix24 in crm_multifield format
$arPhone
= (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
)) :
array
();
$arEmail
= (!
empty
(
$sEmail
)) ?
array
(
array
(
'VALUE'
=>
$sEmail
,
'VALUE_TYPE'
=>
'HOME'
)) :
array
();
// Send data to Bitrix24
$result
=
CRest
::
call
(
'crm.company.add'
,
[
'fields'
=>[
"TITLE"
=>
$sTitle
, // Company name
"COMPANY_TYPE"
=>
'CUSTOMER'
, // Company type — client
"PHONE"
=>
$arPhone
, // Phone
"EMAIL"
=>
$arEmail
, // Email
]
]
);
// Return the result
if
(!
empty
(
$result
[
'result'
])){
echo
json_encode
([
'message'
=>
'Company added'
]);
}
elseif
(!
empty
(
$result
[
'error_description'
])){
echo
json_encode
([
'message'
=>
'Company not added: '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
'Company not added'
]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
Add Contact with Details
Next
Add Company with Details

---

## Add a Company with Details via Web Form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-company-with-requisite

Add a Company with Details via Web Form | Bitrix24 REST API and Marketplace Applications
Add a Company with Details via Web Form
Add a Company with Details via Web Form
1. Creating the Web Form
Full Example of the Page Code with the Form
2. Creating the Form Handler
Preparing the Data
Adding the Company
Adding Details to the Company
Adding an Address for the Detail
Full Example of the Handler Code
Scope:
crm
Who can execute the method: users with permission to create companies in CRM
You can place a form on the site to collect client data and details. When a client fills out the form, their data will be sent to CRM, and you will be able to process the request.
Setting up the form consists of two steps.
We will place the form on a PHP page. In the page code, we will retrieve the list of detail templates and address fields for the form. The form data will be sent to the handler.
We will create a file to process the data. The handler will accept and prepare the data, and then create a company with the details.
1 Creating the Web Form
1. Creating the Web Form
To generate the form fields, we will use data from Bitrix24. To get information about the detail settings, we will sequentially execute two methods:
crm.address.fields
— we get the list of address fields. The result is saved in
arAddressFields
.
$arAddressFields
=
CRest
::
call
(
'crm.address.fields'
, []);
crm.requisite.preset.list
— we request the list of detail templates. Using the
select
parameter, we choose the
ID
and
NAME
fields for each template. The result is saved in
arRequisiteType
.
$arRequisiteType
=
CRest
::
call
(
'crm.requisite.preset.list'
, [
'select'
=> [
"ID"
,
"NAME"
]
]
);
We will add a web form to the site page with the following fields:
REQ_TYPE
— a dropdown list with the type of details from the
arRequisiteType
array,
TITLE
— the name of the company, required,
INN
— Tax Identification Number,
PHONE
— phone number,
${addressFieldsInputs}
— address fields that are dynamically created from the
arAddressFields
array.
The form sends data using the
POST
method to the
form.php
file.
Full Example of the Page Code with the Form
Full Example of the Page Code with the Form
How to Use Examples in Documentation
<?php
// Get the list of address fields and detail templates
$arAddressFields
=
CRest
::
call
(
'crm.address.fields'
, []);
$arRequisiteType
=
CRest
::
call
(
'crm.requisite.preset.list'
, [
'select'
=> [
"ID"
,
"NAME"
]
]);
if
(!
empty
(
$arRequisiteType
[
'result'
])):
$arRequisiteType
=
array_column
(
$arRequisiteType
[
'result'
],
'NAME'
,
'ID'
);
// Remove system and unused address fields
$excludeFields
= [
'TYPE_ID'
,
'ENTITY_TYPE_ID'
,
'ENTITY_ID'
,
'COUNTRY_CODE'
,
'ANCHOR_TYPE_ID'
,
'ANCHOR_ID'
];
foreach
(
$excludeFields
as
$field
) {
unset
(
$arAddressFields
[
'result'
][
$field
]);
}
?>
<form id=
"form_to_crm"
>
<select name=
"REQ_TYPE"
required>
<option value=
""
disabled selected>Select the type of details</option>
<?php
foreach
(
$arRequisiteType
as
$id
=>
$name
):
?>
<option value=
"<?=
$id
?>"
>
<?=
$name
?>
</option>
<?php
endforeach
;
?>
</select>
<input type=
"text"
name=
"TITLE"
placeholder=
"Organization Name"
required>
<input type=
"text"
name=
"INN"
placeholder=
"Tax Identification Number"
>
<input type=
"text"
name=
"PHONE"
placeholder=
"Phone Number"
>
<?php
foreach
(
$arAddressFields
[
'result'
]
as
$key
=>
$arField
):
?>
<input type=
"text"
name=
"ADDRESS[<?=
$key
?>]"
placeholder=
"<?=
$arField
['title']?>"
<?=
$arField
[
'isRequired'
] ?
'required'
:
''
?>
>
<?php
endforeach
;
?>
<input type=
"submit"
value=
"Submit"
>
</form>
<?php
else
:
?>
<p>No available types of details.</p>
<?php
endif
;
?>
<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
></script>
<script>
$(document).
ready
(function() {
$(
'#form_to_crm'
).
on
(
'submit'
, function(el) {
el.
preventDefault
();
$.
ajax
({
method
:
'POST'
,
dataType
:
'json'
,
url
:
'form.php'
,
data
: $(this).
serialize
(),
success:
function
(
data
)
{
alert
(data.message);
}
});
});
});
</script>
2 Creating the Form Handler
2. Creating the Form Handler
To process the values from the form fields and add a company to CRM, we will create the handler
form.php
.
Preparing the Data
Preparing the Data
We will retrieve and sanitize the data from the form:
REQ_TYPE
is converted to an integer,
TITLE
,
INN
,
PHONE
are sanitized from HTML tags.
$iRequisitePresetID
=
intVal
(
$_POST
[
"REQ_TYPE"
]);
$sTitle
=
htmlspecialchars
(
$_POST
[
"TITLE"
]);
$sINN
=
htmlspecialchars
(
$_POST
[
"INN"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
We prepare the address fields and collect them into the
$arAddress
array.
The values of the fields from the form are sanitized from HTML tags.
We add the address type
TYPE_ID
. The address types can be obtained using the method
crm.enum.addresstype
. We will specify the value —
1
, which means the actual address.
We add the identifier of the
object type
ENTITY_TYPE_ID
. The identifiers can be obtained using the method
crm.enum.ownertype
. We will specify the value —
8
, which means detail.
$arAddress
= [];
foreach
(
$_POST
[
"ADDRESS"
]
as
$key
=>
$val
) {
$arAddress
[
$key
] =
htmlspecialchars
(
$val
);
}
$arAddress
[
'TYPE_ID'
] =
1
;
$arAddress
[
'ENTITY_TYPE_ID'
] =
8
;
The system stores the phone as an array of objects
crm_multifield
, so it needs to be formatted as an array.
We add the phone as the first element
VALUE
in the array, and the second value specifies the type
VALUE_TYPE
, for example,
WORK
.
For an empty value, we pass an empty array.
$arPhone
= !
empty
(
$sPhone
) ? [[
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
]] : [];
Adding the Company
Adding the Company
To create a company, we will execute the method
crm.company.add
. In the
fields
object, we pass the fields:
TITLE
— the name of the company.
COMPANY_TYPE
— the type of company. The types of companies can be found using the method
crm.status.list
by filtering the
filter
field by
ENTITY_ID
with the value
COMPANY_TYPE
. In the example, we will specify the value
CUSTOMER
, as only clients of the company fill out the form.
PHONE
— phone number.
Check which required fields are set for companies in your Bitrix24. All required fields must be passed to the method
crm.company.add
.
CRest
::
call
(
'crm.company.add'
, [
'fields'
=> [
'TITLE'
=>
$sTitle
,
'COMPANY_TYPE'
=>
'CUSTOMER'
, // Company type — client
'PHONE'
=>
$arPhone
]
]
);
As a result, we will receive the identifier of the new company
5
.
{
"result"
:
5
}
Adding Details to the Company
Adding Details to the Company
To add details to the company, we will execute the method
crm.requisite.add
. In the
fields
object, we pass the fields:
ENTITY_TYPE_ID
— the identifier of the
object type
. The identifiers can be obtained using the method
crm.enum.ownertype
. In the example, we will specify the value
4
, which means company,
ENTITY_ID
— the identifier of the company obtained in the previous request,
PRESET_ID
— the identifier of the detail template obtained from the form,
ACTIVE
— the activity of the detail
Y
,
NAME
— the name of the detail,
RQ_INN
— the Tax Identification Number of the company.
CRest
::
call
(
'crm.requisite.add'
,
[
'fields'
=> [
'ENTITY_TYPE_ID'
=>
4
,
'ENTITY_ID'
=>
$companyId
,
'PRESET_ID'
=>
$iRequisitePresetID
,
'ACTIVE'
=>
'Y'
,
'NAME'
=>
$sTitle
,
'RQ_INN'
=>
$sINN
]
]
);
As a result, we will receive the identifier of the details.
{
"result"
:
27
}
Adding an Address for the Detail
Adding an Address for the Detail
We will add an address for the detail using the method
crm.address.add
if the detail was created successfully. In
$arAddress
, we add
ENTITY_ID
with the
ID
of the detail from the response of the previous request. In the
fields
object, we pass the
$arAddress
array with the address fields.
if
(!
empty
(
$resultRequisite
[
'result'
])) {
$arAddress
[
'ENTITY_ID'
] =
$resultRequisite
[
'result'
];
CRest
::
call
(
'crm.address.add'
,
[
'fields'
=>
$arAddress
]
);
}
Full Example of the Handler Code
Full Example of the Handler Code
<?php
require_once
(
'crest.php'
);
// Get and sanitize form data
$iRequisitePresetID
=
intVal
(
$_POST
[
"REQ_TYPE"
]);
$sTitle
=
htmlspecialchars
(
$_POST
[
"TITLE"
]);
$sINN
=
htmlspecialchars
(
$_POST
[
"INN"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
// Prepare address
$arAddress
= [];
foreach
(
$_POST
[
"ADDRESS"
]
as
$key
=>
$val
) {
$arAddress
[
$key
] =
htmlspecialchars
(
$val
);
}
$arAddress
[
'TYPE_ID'
] =
1
;
// Value 1 — actual address
$arAddress
[
'ENTITY_TYPE_ID'
] =
8
;
// Object type identifier — 8, which means detail
// Format phone for Bitrix24 in crm_multifield format
$arPhone
= !
empty
(
$sPhone
) ? [[
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
]] : [];
// Create company
$result
=
CRest
::
call
(
'crm.company.add'
, [
'fields'
=> [
'TITLE'
=>
$sTitle
,
'COMPANY_TYPE'
=>
'CUSTOMER'
, // Type — client
'PHONE'
=>
$arPhone
]
]);
// Get the identifier of the new company from the response of crm.company.add
if
(!
empty
(
$result
[
'result'
])) {
$companyId
=
$result
[
'result'
];
// Add details for the new company
$resultRequisite
=
CRest
::
call
(
'crm.requisite.add'
, [
'fields'
=> [
'ENTITY_TYPE_ID'
=>
4
, // Object type identifier —
4
, which means company
'ENTITY_ID'
=>
$companyId
,
'PRESET_ID'
=>
$iRequisitePresetID
,
'ACTIVE'
=>
'Y'
,
'NAME'
=>
$sTitle
,
'RQ_INN'
=>
$sINN
]
]);
// Add address if details were created successfully
if
(!
empty
(
$resultRequisite
[
'result'
])) {
$arAddress
[
'ENTITY_ID'
] =
$resultRequisite
[
'result'
];
CRest
::
call
(
'crm.address.add'
, [
'fields'
=>
$arAddress
]);
}
echo
json_encode
([
'message'
=>
'Company successfully added'
]);
}
else
{
$error
= !
empty
(
$result
[
'error_description'
]) ?
$result
[
'error_description'
] :
'Unknown error'
;
echo
json_encode
([
'message'
=>
'Error: '
.
$error
]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
Add Company
Next
Create a Vendor in CRM

---

## How to Create a Vendor in CRM

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-contractor

How to Create a Vendor in CRM | Bitrix24 REST API and Marketplace Applications
How to Create a Vendor in CRM
How to Create a Vendor in CRM
1. Retrieve the Vendor Category ID
2. Create the Vendor
Code Example
Scope:
crm
Who can execute the method: users with permission to create contacts or companies in CRM
Vendors are CRM contacts and companies with a system category designation:
CATALOG_CONTRACTOR_CONTACT
— for contacts,
CATALOG_CONTRACTOR_COMPANY
— for companies.
To create a vendor, we will sequentially execute two methods:
crm.category.list
— retrieve the category ID for the contact or company.
crm.item.add
— create a contact or company as a vendor.
1. Retrieve the Vendor Category ID
1. Retrieve the Vendor Category ID
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
. The ID may vary in different Bitrix24 instances.
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
2. Create the Vendor
2. Create the Vendor
We will use the method
crm.item.add
with the following parameters:
entityTypeId
— the ID of the
CRM object type
. Use
3
for contacts. For companies, use
4
.
fields[categoryId]
— the ID of the system category from step 1. In the example,
15
.
fields[name]
— first name.
fields[lastName]
— last name. For companies, instead of first and last names, you can provide the
fields[title]
field — the name.
fields[fm]
— an array of multi-fields
crm_multifield
for phone and email.
fields[comments]
— comments.
The system stores phone and email as an array of multi-fields
fm
. Each element of the array contains:
typeId
— the type of multi-field,
PHONE
or
EMAIL
,
valueType
— the type of value, for example,
WORK
or
MOBILE
,
value
— the field value.
JS
PHP
BX24
.
callMethod
(
'crm.item.add'
,
{
entityTypeId
:
3
,
fields
: {
name
:
'John'
,
lastName
:
'Doe'
,
categoryId
:
15
,
// id from step 1
fm
: [
{
typeId
:
'PHONE'
,
valueType
:
'WORK'
,
value
:
'+1 900 000 00 00'
},
{
typeId
:
'PHONE'
,
valueType
:
'MOBILE'
,
value
:
'+1 495 111 22 33'
},
{
typeId
:
'EMAIL'
,
valueType
:
'WORK'
,
value
:
'supplier@example.com'
}
],
comments
:
'Electronics vendor'
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
() +
': '
+ result.
error_description
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
'crm.item.add'
,
[
'entityTypeId'
=>
3
,
'fields'
=> [
'name'
=>
'John'
,
'lastName'
=>
'Doe'
,
'categoryId'
=>
15
, // id
from
step
1
'fm'
=> [
[
'typeId'
=>
'PHONE'
,
'valueType'
=>
'WORK'
,
'value'
=>
'+1 900 000 00 00'
],
[
'typeId'
=>
'PHONE'
,
'valueType'
=>
'MOBILE'
,
'value'
=>
'+1 495 111 22 33'
],
[
'typeId'
=>
'EMAIL'
,
'valueType'
=>
'WORK'
,
'value'
=>
'supplier@example.com'
]
],
'comments'
=>
'Electronics vendor'
]
]
);
As a result, the method will return an
item
object with the data of the created vendor.
{
"result"
:
{
"item"
:
{
"id"
:
2449
,
"createdTime"
:
"2025-12-29T13:18:40+01:00"
,
"updatedTime"
:
"2025-12-29T13:18:40+01:00"
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
null
,
"name"
:
"John"
,
"lastName"
:
"Doe"
,
"secondName"
:
null
,
"shortName"
:
null
,
"photo"
:
null
,
"post"
:
null
,
"address"
:
null
,
"comments"
:
"Electronics vendor"
,
"leadId"
:
null
,
"export"
:
"Y"
,
"webformId"
:
null
,
"originatorId"
:
null
,
"originId"
:
null
,
"originVersion"
:
null
,
"birthdate"
:
null
,
"honorific"
:
null
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
"searchContent"
:
null
,
"categoryId"
:
15
,
"lastActivityBy"
:
1
,
"lastActivityTime"
:
"2025-12-29T13:18:40+01:00"
,
"login"
:
null
,
"emailHome"
:
null
,
"emailWork"
:
null
,
"emailMailing"
:
null
,
"phoneMobile"
:
null
,
"phoneWork"
:
null
,
"phoneMailing"
:
null
,
"imol"
:
null
,
"email"
:
null
,
"phone"
:
null
,
"lastCommunicationTime"
:
null
,
"lastCommunicationCallTime"
:
null
,
"lastCommunicationEmailTime"
:
null
,
"lastCommunicationImolTime"
:
null
,
"lastCommunicationWebformTime"
:
null
,
"observers"
:
[
]
,
"companyIds"
:
[
]
,
"entityTypeId"
:
3
,
"fm"
:
[
{
"id"
:
8297
,
"valueType"
:
"WORK"
,
"value"
:
"+1 900 000 00 00"
,
"typeId"
:
"PHONE"
}
,
{
"id"
:
8299
,
"valueType"
:
"MOBILE"
,
"value"
:
"+1 495 111 22 33"
,
"typeId"
:
"PHONE"
}
,
{
"id"
:
8301
,
"valueType"
:
"WORK"
,
"value"
:
"supplier@example.com"
,
"typeId"
:
"EMAIL"
}
]
}
}
,
"time"
:
{
"start"
:
1767003520
,
"finish"
:
1767003520.776535
,
"duration"
:
0.7765350341796875
,
"processing"
:
0
,
"date_start"
:
"2025-12-29T13:18:40+01:00"
,
"date_finish"
:
"2025-12-29T13:18:40+01:00"
,
"operating_reset_at"
:
1767004120
,
"operating"
:
0.4402291774749756
}
}
The vendor ID, in the example
id
:
2449
, should be used in the inventory accounting method
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
var
categoryId =
null
;
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
categoryId = categories[
0
].
id
;
BX24
.
callMethod
(
'crm.item.add'
,
{
entityTypeId
: entityTypeId,
fields
: {
name
:
'John'
,
lastName
:
'Doe'
,
categoryId
: categoryId,
fm
: [
{
typeId
:
'PHONE'
,
valueType
:
'WORK'
,
value
:
'+1 900 000 00 00'
},
{
typeId
:
'PHONE'
,
valueType
:
'MOBILE'
,
value
:
'+1 495 111 22 33'
},
{
typeId
:
'EMAIL'
,
valueType
:
'WORK'
,
value
:
'supplier@example.com'
}
],
comments
:
'Electronics vendor'
}
},
function
(
resultItem
) {
if
(resultItem.
error
()) {
console
.
error
(resultItem.
error
() +
': '
+ resultItem.
error_description
());
}
else
{
console
.
log
(resultItem.
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
$resultItem
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
$entityTypeId
,
'fields'
=> [
'name'
=>
'John'
,
'lastName'
=>
'Doe'
,
'categoryId'
=>
$categoryId
,
'fm'
=> [
[
'typeId'
=>
'PHONE'
,
'valueType'
=>
'WORK'
,
'value'
=>
'+1 900 000 00 00'
],
[
'typeId'
=>
'PHONE'
,
'valueType'
=>
'MOBILE'
,
'value'
=>
'+1 495 111 22 33'
],
[
'typeId'
=>
'EMAIL'
,
'valueType'
=>
'WORK'
,
'value'
=>
'supplier@example.com'
]
],
'comments'
=>
'Electronics vendor'
]
]
);
if
(!
empty
(
$resultItem
[
'error_description'
])) {
echo
$resultItem
[
'error_description'
];
}
else
{
print_r
(
$resultItem
[
'result'
]);
}
Copied
Was the article helpful?
Yes
No
Previous
Add Company with Details
Next
Add Deal and Company with Details

---

## Add a deal and company with requisites

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-deal-with-choice-of-requisite

Add a deal and company with requisites | Bitrix24 REST API and Marketplace Applications
Add a deal and company with requisites
Add a deal and company with requisites
1. Create the web form
Full example of the code
2. Create the form handler
Retrieve the data
Prepare the data
Add the company
Add requisites
Add address to requisites
Add a deal
Full example of the handler code
Continue learning
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
Using a web form, you can automatically add new deals and companies with requisites in Bitrix24. When a client fills out the form, the data is sent to a handler. The handler script creates objects in the CRM via the API.
The setup consists of two stages.
Prepare the fields and place the web form on the page.
Create a handler file that sequentially calls the methods
crm.company.add
,
crm.requisite.add
,
crm.address.add
, and
crm.deal.add
.
1 Create the web form
1. Create the web form
To generate the fields, we use two methods:
crm.address.fields
— retrieves the list of address fields. The result is saved in the array
$arAddressFields
.
crm.requisite.preset.list
— retrieves the list of requisites templates by the fields
ID
and
NAME
. The result is saved in the array
$arRequisiteType
.
How to Use Examples in Documentation
$arAddressFields
=
CRest
::
call
(
'crm.address.fields'
,[]);
$arRequisiteType
=
CRest
::
call
(
'crm.requisite.preset.list'
,
[
'select'
=>[
"ID"
,
"NAME"
]
]
);
From the array
$arAddressFields
, we remove unnecessary address fields so that they do not appear in the form.
unset
(
$arAddressFields
[
'result'
][
'TYPE_ID'
]);
unset
(
$arAddressFields
[
'result'
][
'ENTITY_TYPE_ID'
]);
unset
(
$arAddressFields
[
'result'
][
'ENTITY_ID'
]);
unset
(
$arAddressFields
[
'result'
][
'COUNTRY_CODE'
]);
unset
(
$arAddressFields
[
'result'
][
'ANCHOR_TYPE_ID'
]);
unset
(
$arAddressFields
[
'result'
][
'ANCHOR_ID'
]);
We create an HTML form with the fields:
REQ_TYPE
— a dropdown list with requisites templates from the array
$arRequisiteType
. This is a required field.
TITLE
— the name of the company. This is a required field.
INN
— the company's INN.
PHONE
— the phone number.
ADDRESS
— address fields are created dynamically from
$arAddressFields
. If a field is required, the
required
attribute is added.
The form collects data into a string and sends it via
POST
to the file
form.php
.
<
form
id
=
"form_to_crm"
>
<
select
name
=
"REQ_TYPE"
required
>
<
option
value
=
""
disabled
selected
>
Select
</
option
>
<?php foreach($arRequisiteType as $id=>$name):?>
<
option
value
=
"<?=$id?>"
>
<?=$name?>
</
option
>
<?php endforeach;?>
</
select
>
<
input
type
=
"text"
name
=
"TITLE"
placeholder
=
"Org name"
required
>
<
input
type
=
"text"
name
=
"INN"
placeholder
=
"INN"
>
<
input
type
=
"text"
name
=
"PHONE"
placeholder
=
"Phone"
>
<?php if(is_array($arAddressFields['result'])):?>
<?php foreach($arAddressFields['result'] as $key=>$arField):?>
<
input
type
=
"text"
name
=
"ADDRESS[<?=$key?>]"
placeholder
=
"<?=$arField['title']?>"
<?=
($arField[
'
isRequired
'])?'
required
'
:
'';?>
>
<?php endforeach;?>
<?php endif;?>
<
input
type
=
"submit"
value
=
"Submit"
>
</
form
>
Full example of the code
Full example of the code
<?php
require_once
(
'crest.php'
);
$arAddressFields
=
CRest
::
call
(
'crm.address.fields'
,[]);
$arRequisiteType
=
CRest
::
call
(
'crm.requisite.preset.list'
,
[
'select'
=>[
"ID"
,
"NAME"
]
]
);
if
(!
empty
(
$arRequisiteType
[
'result'
])):
$arRequisiteType
=
array_column
(
$arRequisiteType
[
'result'
],
'NAME'
,
'ID'
);
//unset system address fields
unset
(
$arAddressFields
[
'result'
][
'TYPE_ID'
]);
unset
(
$arAddressFields
[
'result'
][
'ENTITY_TYPE_ID'
]);
unset
(
$arAddressFields
[
'result'
][
'ENTITY_ID'
]);
//unset uninteresting address fields
unset
(
$arAddressFields
[
'result'
][
'COUNTRY_CODE'
]);
unset
(
$arAddressFields
[
'result'
][
'ANCHOR_TYPE_ID'
]);
unset
(
$arAddressFields
[
'result'
][
'ANCHOR_ID'
]);
?>
<form id=
"form_to_crm"
>
<select name=
"REQ_TYPE"
required>
<option value=
""
disabled selected>Select</option>
<?php
foreach
(
$arRequisiteType
as
$id
=>
$name
):
?>
<option value=
"<?=
$id
?>"
>
<?=
$name
?>
</option>
<?php
endforeach
;
?>
</select>
<input type=
"text"
name=
"TITLE"
placeholder=
"Org name"
required>
<input type=
"text"
name=
"INN"
placeholder=
"INN"
>
<input type=
"text"
name=
"PHONE"
placeholder=
"Phone"
>
<?php
if
(
is_array
(
$arAddressFields
[
'result'
])):
?>
<?php
foreach
(
$arAddressFields
[
'result'
]
as
$key
=>
$arField
):
?>
<input type=
"text"
name=
"ADDRESS[<?=
$key
?>]"
placeholder=
"<?=
$arField
['title']?>"
<?=
(
$arField
[
'isRequired'
])?
'required'
:
''
;
?>
>
<?php
endforeach
;
?>
<?php
endif
;
?>
<input type=
"submit"
value=
"Submit"
>
</form>
<?php
else
:
?>
No requisite types.
<?php
endif
;
?>
<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
></script>
<script>
$(document).
ready
(function() {
$(
'#form_to_crm'
).
on
(
'submit'
, function(el) {
//event submit form
el.
preventDefault
();
//the default action of the event will not be triggered
var
formData = $(this).
serialize
();
$.
ajax
({
'method'
:
'POST'
,
'dataType'
:
'json'
,
'url'
:
'form.php'
, // file
for
saving filled forms
'data'
: formData,
success
: function(data){
//success callback
alert
(data.message);
}
});
});
});
</script>
2 Create the form handler
2. Create the form handler
Create the file
form.php
, which will process the data and save it in the CRM.
Retrieve the data
Retrieve the data
Retrieve and process the data from the form.
$iRequisitePresetID
=
intval
(
$_POST
[
"REQ_TYPE"
]);
$sTitle
=
htmlspecialchars
(
$_POST
[
"TITLE"
]);
$sINN
=
htmlspecialchars
(
$_POST
[
"INN"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$arAddress
= [];
foreach
(
$_POST
[
"ADDRESS"
]
as
$key
=>
$val
) {
$arAddress
[
$key
] =
htmlspecialchars
(
$val
);
}
$iRequisitePresetID
— convert the requisites template identifier
REQ_TYPE
to an integer.
$sTitle
,
$sINN
,
$sPhone
— safely process the data from
TITLE
,
INN
,
PHONE
to avoid XSS attacks.
$arAddress
— store the data from the array with address fields
ADDRESS
.
Prepare the data
Prepare the data
Add two required system fields to the
$arAddress
array.
TYPE_ID
— the type of address. We will specify
1
— the actual address. The list of address types can be obtained using the method
crm.enum.addresstype
.
ENTITY_TYPE_ID
—
the identifier of the CRM object type
. We pass
8
— requisites. The complete list of object types can be obtained using the method
crm.enum.ownertype
.
$arAddress
[
'TYPE_ID'
] =
1
;
$arAddress
[
'ENTITY_TYPE_ID'
] =
8
;
The system stores the phone as an array of objects
crm_multifield
, so the value of
$sPhone
needs to be formatted as an array:
in the first element
VALUE
, we write
$sPhone
,
in the second element
VALUE_TYPE
, we pass, for example,
WORK
.
If the variable
$sPhone
has no value, we specify an empty array.
$arPhone
= (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
)) :
array
();
Add the company
Add the company
To add a company, we use the method
crm.company.add
. We need to pass the following data:
TITLE
— the name of the company. We pass
$sTitle
, which we obtained from the form.
COMPANY_TYPE
— the type of company. We will specify
CUSTOMER
— client. The list of types can be obtained using the method
crm.status.list
with the filter
'filter'=>['ENTITY_ID'=>’COMPANY_TYPE']
.
PHONE
— an array with the phone
$arPhone
, which we obtained from the form.
Check which required fields are set for companies in your Bitrix24. All required fields must be passed to the method
crm.company.add
.
$result
=
CRest
::
call
(
'crm.company.add'
,
[
'fields'
=>[
'TITLE'
=>
$sTitle
,
'COMPANY_TYPE'
=>
'CUSTOMER'
,
'PHONE'
=>
$arPhone
,
]
]
);
If the company is successfully created, the method will return its identifier in
$result
. If you receive an
error
, review the possible error descriptions in the documentation for the method
crm.company.add
.
Add requisites
Add requisites
To add requisites, we use the method
crm.requisite.add
. We need to pass the following data:
ENTITY_TYPE_ID
—
the identifier of the CRM object type
. We pass
4
— company. The complete list of object types can be obtained using the method
crm.enum.ownertype
.
ENTITY_ID
— the identifier of the company. We pass
$result
, which we obtained when creating the company.
PRESET_ID
— the identifier of the requisites template. We specify
$iRequisitePresetID
, which we obtained from the form.
NAME
— the name of the requisite. We pass
$sTitle
, which we obtained from the form.
RQ_INN
— the company's INN. We pass
$sINN
, which we obtained from the form.
ACTIVE
— the active flag, we will specify
Y
.
$resultRequisite
=
CRest
::
call
(
'crm.requisite.add'
,
[
'fields'
=>[
'ENTITY_TYPE_ID'
=>
4
,
'ENTITY_ID'
=>
$result
[
'result'
],
'PRESET_ID'
=>
$iRequisitePresetID
,
'ACTIVE'
=>
'Y'
,
'NAME'
=>
$sTitle
,
'RQ_INN'
=>
$sINN
,
]
]
);
If the requisites are successfully added, the method will return the record identifier in
$resultRequisite
. If you receive an
error
, review the possible error descriptions in the documentation for the method
crm.requisite.add
.
Add address to requisites
Add address to requisites
Add the field
ENTITY_ID
to the
$arAddress
array — the identifier of the requisite. We pass
$resultRequisite
, which we obtained when creating the requisite.
$arAddress
[
'ENTITY_ID'
] =
$resultRequisite
[
'result'
];
Use the method
crm.address.add
. We need to pass the array
$arAddress
.
$resultAddress
=
CRest
::
call
(
'crm.address.add'
,
[
'fields'
=>
$arAddress
]
);
The method returns one of the values in the variable
$resultAddress
:
true
— the address has been added,
false
— the address has not been added.
Add a deal
Add a deal
We create the array
$arDealFields
with the data for the deal.
TITLE
— the name of the deal. We will specify the name of the company
$sTitle
, which was obtained from the form,
COMPANY_ID
— the identifier of the company associated with the deal. We pass
$result
, which we obtained when creating the company,
REQUISITE_ID
— the identifier of the requisite. If the requisite is created, we pass
$resultRequisite
.
$arDealFields
= [
'TITLE'
=>
$sTitle
,
'COMPANY_ID'
=>
$result
[
'result'
]
];
if
(!
empty
(
$resultRequisite
[
'result'
])){
$arDealFields
[
'REQUISITE_ID'
] =
$resultRequisite
[
'result'
];
}
To add a deal, we use the method
crm.deal.add
. We pass the array
$arDealFields
.
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
If the deal is successfully created, the method will return its identifier. If you receive an
error
, review the possible error descriptions in the documentation for the method
crm.deal.add
.
{
"result"
:
1789
,
}
Full example of the handler code
Full example of the handler code
<?php
require_once
(
'crest.php'
);
$iRequisitePresetID
=
intVal
(
$_POST
[
"REQ_TYPE"
]);
$sTitle
=
htmlspecialchars
(
$_POST
[
"TITLE"
]);
$sINN
=
htmlspecialchars
(
$_POST
[
"INN"
]);
$sPhone
=
htmlspecialchars
(
$_POST
[
"PHONE"
]);
$arAddress
= [];
foreach
(
$_POST
[
"ADDRESS"
]
as
$key
=>
$val
){
$arAddress
[
$key
] =
htmlspecialchars
(
$val
);
}
$arAddress
[
'TYPE_ID'
] =
1
;
//1 is actual address in CRest::call('crm.enum.addresstype');
$arAddress
[
'ENTITY_TYPE_ID'
] =
8
;
//8 - is requisite in CRest::call('crm.enum.ownertype');
$arPhone
= (!
empty
(
$sPhone
)) ?
array
(
array
(
'VALUE'
=>
$sPhone
,
'VALUE_TYPE'
=>
'WORK'
)) :
array
();
$result
=
CRest
::
call
(
'crm.company.add'
,
[
'fields'
=>[
'TITLE'
=>
$sTitle
,
'COMPANY_TYPE'
=>
'CUSTOMER'
,//is Client in
CRest
::
call
(
'crm.status.list'
,[
'filter'
=>[
'ENTITY_ID'
=>
'COMPANY_TYPE'
]])
'PHONE'
=>
$arPhone
,
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
])){
$resultRequisite
=
CRest
::
call
(
'crm.requisite.add'
,
[
'fields'
=>[
'ENTITY_TYPE_ID'
=>
4
,//
4
- is company in
CRest
::
call
(
'crm.enum.ownertype'
);
'ENTITY_ID'
=>
$result
[
'result'
],//company id
'PRESET_ID'
=>
$iRequisitePresetID
,
'ACTIVE'
=>
'Y'
,
'NAME'
=>
$sTitle
,
'RQ_INN'
=>
$sINN
,
]
]
);
$arDealFields
= [
'TITLE'
=>
$sTitle
,
'COMPANY_ID'
=>
$result
[
'result'
]
];
if
(!
empty
(
$resultRequisite
[
'result'
])){
$arDealFields
[
'REQUISITE_ID'
] =
$resultRequisite
[
'result'
];
//add requisite to deal is analogue "crm.requisite.link.list"
$arAddress
[
'ENTITY_ID'
] =
$resultRequisite
[
'result'
];
//id requisite
$resultAddress
=
CRest
::
call
(
'crm.address.add'
,
[
'fields'
=>
$arAddress
]
);
}
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
echo
json_encode
([
'message'
=>
'add'
]);
}
elseif
(!
empty
(
$result
[
'error_description'
])){
echo
json_encode
([
'message'
=>
'not added: '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
'not added'
]);
}
?>
Continue learning
Continue learning
Create a New Company crm.company.add
Add Requisite crm.requisite.add
Add Address crm.address.add
Create a new deal crm.deal.add
Get Description of Address Fields crm.address.fields
Get a list of requisites templates by filter crm.requisite.preset.list
Get Address Types crm.enum.addresstype
Get CRM Object Types crm.enum.ownertype
Copied
Was the article helpful?
Yes
No
Previous
Create a Vendor in CRM
Next
Add Calendar Event for Client Work

---

## Add Calendar Event for Client Interaction

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-activity-to-contact

Add Calendar Event for Client Interaction | Bitrix24 REST API and Marketplace Applications
Add Calendar Event for Client Interaction
Add Calendar Event for Client Interaction
1. Retrieve Client Data
2. Create Calendar Event
Code Example
Scope:
crm
Who can execute the method: users with permission to modify a CRM entity
Calendar events can be added automatically to remind employees about meetings or calls with clients. An event linked to the client's contact will appear in the calendar of the responsible employee. A task for the event will be added to the contact's detail form.
To add an event to the calendar, we will sequentially execute two methods:
crm.contact.get
— retrieve client data
crm.activity.add
— create a calendar event
1 Retrieve Client Data
1. Retrieve Client Data
We will use the method
crm.contact.get
with the client identifier. For example, we are interested in the contact with the identifier
1
.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'crm.contact.get'
,
{
'id'
:
1
},
);
require_once
(
'crest.php'
);
$resultContact
=
CRest
::
call
(
'crm.contact.get'
,
[
'id'
=>
1
]
);
As a result, we will receive client data, including phone
PHONE
and the identifier of the responsible employee
ASSIGNED_BY_ID
.
{
"result"
:
{
"ID"
:
"1"
,
"POST"
:
"CEO"
,
"COMMENTS"
:
null
,
"NAME"
:
"Alex"
,
"SECOND_NAME"
:
"Kirillovich"
,
"LAST_NAME"
:
"Vronsky"
,
"PHOTO"
:
null
,
"LEAD_ID"
:
null
,
"TYPE_ID"
:
"SHARE"
,
"SOURCE_ID"
:
"SELF"
,
"SOURCE_DESCRIPTION"
:
null
,
"COMPANY_ID"
:
"52"
,
"BIRTHDATE"
:
""
,
"EXPORT"
:
"Y"
,
"HAS_PHONE"
:
"Y"
,
"HAS_EMAIL"
:
"Y"
,
"HAS_IMOL"
:
"N"
,
"DATE_CREATE"
:
"2023-08-18T12:43:42+02:00"
,
"DATE_MODIFY"
:
"2023-10-17T15:59:13+02:00"
,
"ASSIGNED_BY_ID"
:
"61"
,
"CREATED_BY_ID"
:
"57"
,
"MODIFY_BY_ID"
:
"47"
,
"OPENED"
:
"N"
,
"ORIGINATOR_ID"
:
null
,
"ORIGIN_ID"
:
null
,
"ORIGIN_VERSION"
:
null
,
"FACE_ID"
:
null
,
"LAST_ACTIVITY_TIME"
:
"2025-03-15T10:38:21+01:00"
,
"ADDRESS"
:
null
,
"ADDRESS_2"
:
null
,
"ADDRESS_CITY"
:
null
,
"ADDRESS_POSTAL_CODE"
:
null
,
"ADDRESS_REGION"
:
null
,
"ADDRESS_PROVINCE"
:
null
,
"ADDRESS_COUNTRY"
:
null
,
"ADDRESS_LOC_ADDR_ID"
:
null
,
"UTM_SOURCE"
:
null
,
"UTM_MEDIUM"
:
null
,
"UTM_CAMPAIGN"
:
null
,
"UTM_CONTENT"
:
null
,
"UTM_TERM"
:
null
,
"LAST_ACTIVITY_BY"
:
"1"
,
"PHONE"
:
[
{
"ID"
:
"1326"
,
"VALUE_TYPE"
:
"MOBILE"
,
"VALUE"
:
"88001001020"
,
"TYPE_ID"
:
"PHONE"
}
,
]
,
"EMAIL"
:
[
{
"ID"
:
"1328"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"vronsky@example.com"
,
"TYPE_ID"
:
"EMAIL"
}
,
]
}
,
"time"
:
{
"start"
:
1747737934.888428
,
"finish"
:
1747737934.945823
,
"duration"
:
0.057394981384277344
,
"processing"
:
0.029510021209716797
,
"date_start"
:
"2025-05-20T13:45:34+02:00"
,
"date_finish"
:
"2025-05-20T13:45:34+02:00"
}
}
2 Create Calendar Event
2. Create Calendar Event
To create an event, we will use the method
crm.activity.add
. We need to pass the client data and arbitrary parameters for the new event.
SUBJECT
— event title. We will specify
calendar title
.
DESCRIPTION
— description. For example,
calendar body
.
DESCRIPTION_TYPE
— format of the description text. Possible values:
1
— plain text,
2
— HTML markup,
3
— BB-code. We will set the value to
3
.
OWNER_ID
— contact identifier. We will pass the client identifier —
1
.
OWNER_TYPE_ID
—
CRM object type identifier
. We will pass
3
— contact. A complete list of object types can be obtained using the method
crm.enum.ownertype
.
TYPE_ID
— event type. We will specify
1
— meeting. The list of event types can be obtained using the method
crm.enum.activitytype
.
COMMUNICATIONS
— client's contact details:
VALUE
— phone number, we will take the
VALUE
from the
PHONE
array obtained in the first step,
ENTITY_ID
— client identifier, we will pass
1
,
ENTITY_TYPE_ID
—
object type identifier
, we will pass
3
— contact.
START_TIME
and
END_TIME
— start and end date and time in
ISO 8601
format, we will specify, for example, a duration of one hour,
RESPONSIBLE_ID
— identifier of the responsible person, we will pass
ASSIGNED_BY_ID
, which was obtained in the first step.
JS
PHP
BX24
.
callMethod
(
'crm.activity.add'
,
{
'fields'
: {
"SUBJECT"
:
"calendar title"
,
"DESCRIPTION"
:
"calendar body"
,
"DESCRIPTION_TYPE"
:
3
,
"OWNER_ID"
:
1
,
"OWNER_TYPE_ID"
:
3
,
"TYPE_ID"
:
1
,
"COMMUNICATIONS"
: [
{
'VALUE'
:
"88001001020"
,
'ENTITY_ID'
:
1
,
'ENTITY_TYPE_ID'
:
3
}
],
"START_TIME"
:
"2025-05-20T14:00:00"
,
"END_TIME"
:
"2025-05-20T15:00:00"
,
"RESPONSIBLE_ID"
:
61
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
'crm.activity.add'
,
[
'fields'
=> [
"SUBJECT"
=>
"calendar title"
,
"DESCRIPTION"
=>
"calendar body"
,
"DESCRIPTION_TYPE"
=>
3
,
"OWNER_ID"
=>
1
,
"OWNER_TYPE_ID"
=>
3
,
"TYPE_ID"
=>
1
,
"COMMUNICATIONS"
=> [
[
'VALUE'
=>
"88001001020"
,
'ENTITY_ID'
=>
1
,
'ENTITY_TYPE_ID'
=>
3
]
],
"START_TIME"
=>
"2025-05-20T14:00:00"
,
"END_TIME"
=>
"2025-05-20T15:00:00"
,
"RESPONSIBLE_ID"
=>
61
,
]
]
);
If the event is created successfully, the method will return its identifier. If you receive an
error
, review the possible error descriptions in the documentation for the method
crm.activity.add
.
{
"result"
:
6915
,
}
Code Example
Code Example
The example creates a task "Meeting" in the CRM contact detail form and an event lasting one hour in the employee's calendar.
JS
PHP
var
contactID =
1
;
BX24
.
callMethod
(
'crm.contact.get'
,
{
'id'
: contactID
},
function
(
resultContact
) {
if
(resultContact.
error
()) {
console
.
error
(resultContact.
error
() +
': '
+ resultContact.
error_description
());
}
else
{
var
resultActivity = [];
if
(resultContact.
data
().
ASSIGNED_BY_ID
&& resultContact.
data
().
PHONE
) {
var
contactPhone = resultContact.
data
().
PHONE
[
0
];
var
staffID = resultContact.
data
().
ASSIGNED_BY_ID
;
BX24
.
callMethod
(
'crm.activity.add'
,
{
'fields'
: {
"SUBJECT"
:
"calendar title"
,
"DESCRIPTION"
:
"calendar body"
,
"DESCRIPTION_TYPE"
:
3
,
// text, html, bbCode type id in: BX24.callMethod('crm.enum.contenttype');
"OWNER_ID"
: contactID,
"OWNER_TYPE_ID"
:
3
,
// BX24.callMethod('crm.enum.ownertype');
"TYPE_ID"
:
1
,
// BX24.callMethod('crm.enum.activitytype');
"COMMUNICATIONS"
: [
{
'VALUE'
: contactPhone.
VALUE
,
'ENTITY_ID'
: contactID,
'ENTITY_TYPE_ID'
:
3
// BX24.callMethod('crm.enum.ownertype');
}
],
"START_TIME"
:
new
Date
().
toISOString
(),
"END_TIME"
:
new
Date
(
new
Date
().
getTime
() +
3600
*
1000
).
toISOString
(),
"RESPONSIBLE_ID"
: staffID,
}
},
function
(
resultActivity
) {
if
(resultActivity.
error
()) {
console
.
error
(resultActivity.
error
() +
': '
+ resultActivity.
error_description
());
console
.
log
(
JSON
.
stringify
({
'message'
:
'Activity not added: '
+ resultActivity.
error_description
() }));
}
else
{
console
.
log
(
JSON
.
stringify
({
'message'
:
'Activity added'
}));
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
JSON
.
stringify
({
'message'
:
'Activity not added'
}));
}
}
}
);
$contactID
=
1
;
$resultContact
=
CRest
::
call
(
'crm.contact.get'
,
[
'id'
=>
$contactID
]
);
$resultActivity
= [];
if
(!
empty
(
$resultContact
[
'result'
][
'ASSIGNED_BY_ID'
]) && !
empty
(
$resultContact
[
'result'
][
'PHONE'
]))
{
$contactPhone
=
reset
(
$resultContact
[
'result'
][
'PHONE'
]);
$staffID
=
$resultContact
[
'result'
][
'ASSIGNED_BY_ID'
];
$resultActivity
=
CRest
::
call
(
'crm.activity.add'
,
[
'fields'
=> [
"SUBJECT"
=>
"calendar title"
,
"DESCRIPTION"
=>
"calendar body"
,
"DESCRIPTION_TYPE"
=>
3
,//text,html,bbCode type id
in
:
CRest
::
call
(
'crm.enum.contenttype'
);
"OWNER_ID"
=>
$contactID
,
"OWNER_TYPE_ID"
=>
3
, //
CRest
::
call
(
'crm.enum.ownertype'
);
"TYPE_ID"
=>
1
, //
CRest
::
call
(
'crm.enum.activitytype'
);
"COMMUNICATIONS"
=> [
[
'VALUE'
=>
$contactPhone
[
'VALUE'
],
'ENTITY_ID'
=>
$contactID
,
'ENTITY_TYPE_ID'
=>
3
//
CRest
::
call
(
'crm.enum.ownertype'
);
]
],
"START_TIME"
=>
date
(
"Y-m-d H:i:s"
,
time
()),
"END_TIME"
=>
date
(
"Y-m-d H:i:s"
,
time
() +
3600
),
"RESPONSIBLE_ID"
=>
$staffID
,
]
]
);
}
if
(!
empty
(
$resultActivity
[
'result'
]))
{
echo
json_encode
([
'message'
=>
'Activity added'
]);
}
elseif
(!
empty
(
$resultActivity
[
'error_description'
]))
{
echo
json_encode
([
'message'
=>
'Activity not added: '
.
$resultActivity
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
'Activity not added'
]);
}
Copied
Was the article helpful?
Yes
No
Previous
Add Deal and Company with Details
Next
Add Template and Create Document Based on It

---

## How to Add a Template and Create a Document Based on It

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-generate-documents

How to Add a Template and Create a Document Based on It | Bitrix24 REST API and Marketplace Applications
How to Add a Template and Create a Document Based on It
How to Add a Template and Create a Document Based on It
Prepare Variables
1. Create a Document Number Generator
2. Upload the Document Template
3. Generate the Document
Code Example
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
You can automate document handling in CRM using a script. It will perform the complete cycle of document generation: create a number generator, upload a template in
.docx
format, and generate a document for a specific deal.
To create a document, we will sequentially execute the following methods:
crm.documentgenerator.numerator.add
— we will create a document number generator,
crm.documentgenerator.template.add
— we will upload the document template,
crm.documentgenerator.document.add
— we will generate the document.
Prepare Variables
Prepare Variables
Let's define the main variables that we will use during the document generation process.
filePath
— path to the template file. We will specify
template.docx
.
iDealID
— deal identifier. We will create a document for the deal with the identifier
1
.
sDocName
— name of the document being created. We will specify
Product Demonstration Implementation
.
How to Use Examples in Documentation
JS
PHP
let
filePath =
'template.docx'
;
let
iDealID =
1
;
let
sDocName =
'Product Demonstration Implementation'
;
$filePath
=
__DIR__
.
'/template.docx'
;
$iDealID
=
1
;
$sDocName
=
'Product Demonstration Implementation'
;
1 Create a Document Number Generator
1. Create a Document Number Generator
We will create a number generator for documents using
crm.documentgenerator.numerator.add
. We will pass two parameters to the method.
name
— name of the number generator. We will specify
Rest Numerator
.
template
— the template from which the document number will be generated. We will specify
{NUMBER}
— this is a variable that will be replaced with the sequential number. Other variables can be used, for example,
{DAY}
— current day,
{CLIENT_ID}
— client identifier,
{RANDOM}
— random number.
JS
PHP
BX24
.
callMethod
(
'crm.documentgenerator.numerator.add'
,
{
'fields'
: {
'name'
:
'Rest Numerator'
,
'template'
:
'{NUMBER}'
}
},
function
(
resNum
) {
if
(resNum.
error
()) {
console
.
error
(resNum.
error
());
alert
(
'Number generator not added: '
+ resNum.
error_description
());
return
;
}
}
);
$resNum
=
CRest
::
call
(
'crm.documentgenerator.numerator.add'
,
[
'fields'
=> [
'name'
=>
'Rest Numerator'
,
'template'
=>
'{NUMBER}'
,
]
]
);
The method
crm.documentgenerator.numerator.add
will return an object
resNum
with information about the created number generator.
"numerator"
:
{
"name"
:
"Rest Numerator"
,
"template"
:
"{NUMBER}"
,
"id"
:
43
,
"code"
:
null
,
"settings"
:
{
"Bitrix_Main_Numerator_Generator_SequentNumberGenerator"
:
{
"start"
:
1
,
"step"
:
1
,
"length"
:
0
,
"padString"
:
"0"
,
"periodicBy"
:
null
,
"timezone"
:
null
,
"isDirectNumeration"
:
false
}
}
}
2 Upload the Document Template
2. Upload the Document Template
If the number generator is created, we will add the document template using the method
crm.documentgenerator.template.add
.
The content of the template file needs to be converted to
Base64
.
In
crm.documentgenerator.template.add
, we need to pass the following data:
name
— name of the template. We will specify the variable
sDocName
.
numeratorId
— identifier of the number generator. We will pass it from the object
resNum
, which was obtained in the first step.
region
— region of the template. This affects localization, such as currency and date. We will specify
de
— Germany.
users
— array of access permissions. Defines which user groups can see and use the template. We will specify
UA
— all authorized users.
entityTypeId
—
identifier of the CRM object type
. We will specify
2
— deal. A complete list of object types can be obtained using the method
crm.enum.ownertype
.
file
— content of the file
filePath
, which has been converted to Base64.
JS
PHP
function
fileToBase64
(
filePath
) {
return
new
Promise
(
(
resolve, reject
) =>
{
fetch
(filePath)
.
then
(
response
=>
response.
blob
())
.
then
(
blob
=>
{
let
reader =
new
FileReader
();
reader.
onloadend
=
() =>
resolve
(reader.
result
.
split
(
','
)[
1
]);
reader.
onerror
= reject;
reader.
readAsDataURL
(blob);
});
});
}
let
fileContent =
await
fileToBase64
(filePath);
BX24
.
callMethod
(
'crm.documentgenerator.template.add'
,
{
'fields'
: {
'name'
: sDocName,
'numeratorId'
: resNum.
data
().
numerator
.
id
,
'region'
:
'de'
,
'users'
: [
'UA'
],
'entityTypeId'
: [
'2'
],
'file'
: fileContent
}
},
function
(
resTemplate
) {
if
(resTemplate.
error
()) {
console
.
error
(resTemplate.
error
());
alert
(
'Template not added: '
+ resTemplate.
error_description
());
return
;
}
}
);
$resTemplate
=
CRest
::
call
(
'crm.documentgenerator.template.add'
,
[
'fields'
=> [
'name'
=>
$sDocName
,
'numeratorId'
=>
$resNum
[
'result'
][
'numerator'
][
'id'
],
'region'
=>
'de'
,
'users'
=> [
'UA'
// User All
],
'entityTypeId'
=> [
'2'
],
'file'
=>
base64_encode
(
file_get_contents
(
$filePath
))
]
]
);
The method
crm.documentgenerator.template.add
will return an object
resTemplate
with information about the template.
template
:
{
"id"
:
"39"
,
"name"
:
"Product Demonstration Implementation"
,
"region"
:
"de"
,
"active"
:
"Y"
,
"code"
:
null
,
"createTime"
:
"2025-07-09T16:12:13+02:00"
,
"download"
:
"https://some-domain.bitrix24.com/bitrix/services/main/ajax.php?action=crm.documentgenerator.template.download&SITE_ID=s1&id=39"
,
"downloadMachine"
:
"https://some-domain.bitrix24.com/rest/crm.documentgenerator.template.download.json?sessid=c4ad892d7583ead4fd38666a0af85cb7&token=crm%7CYWN0aW9uPWNybS5kb2N1bWVudGdlbmVyYXRvci50ZW1wbGF0ZS5kb3dubG9hZCZTSVRFX0lEPXMxJmlkPTM5Jl89azNRNlFuVVRvUGl5VzNLaExTVDJCR3g1WjdyQ0tSSFA%3D%7CImNybS5kb2N1bWVudGdlbmVyYXRvci50ZW1wbGF0ZS5kb3dubG9hZHxjcm18WVdOMGFXOXVQV055YlM1a2IyTjFiV1Z1ZEdkbGJtVnlZWFJ2Y2k1MFpXMXdiR0YwWlM1a2IzZHViRzloWkNaVFNWUkZYMGxFUFhNeEptbGtQVE01Smw4OWF6TlJObEZ1VlZSdlVHbDVWek5MYUV4VFZESkNSM2cxV2pkeVEwdFNTRkE9fGM0YWQ4OTJkNzU4M2VhZDRmZDM4NjY2YTBhZjg1Y2I3Ig%3D%3D.GMgjAbCT099xlo8CJN9n5mP2s7MBbqfU%2BbEM%2FAzpoYE%3D"
,
"entityTypeId"
:
[
"0"
:
"2"
]
,
"length"
:
1
,
"numeratorId"
:
"43"
,
"users"
:
[
"0"
:
"UA"
]
,
"sort"
:
500
}
3 Generate the Document
3. Generate the Document
If the template is successfully uploaded, we will create a document for the deal using the method
crm.documentgenerator.document.add
. We will specify three parameters in the method.
templateId
— identifier of the template. We will pass it from the object
resTemplate
, which was obtained in the second step.
entityTypeId
—
identifier of the CRM object type
. We will specify
2
— deal. A complete list of object types can be obtained using the method
crm.enum.ownertype
.
entityId
— identifier of the deal. We will specify the variable
iDealID
.
JS
PHP
BX24
.
callMethod
(
'crm.documentgenerator.document.add'
,
{
'templateId'
: resTemplate.
data
().
template
.
id
,
'entityTypeId'
:
'2'
,
'entityId'
: iDealID
},
function
(
resDoc
) {
if
(resDoc.
error
()) {
console
.
error
(resDoc.
error
());
alert
(
'Document not created: '
+ resDoc.
error_description
());
}
else
{
alert
(
'Document created'
);
}
}
);
$resDoc
=
CRest
::
call
(
'crm.documentgenerator.document.add'
,
[
'templateId'
=>
$resTemplate
[
'result'
][
'template'
][
'id'
],
'entityTypeId'
=>
'2'
,
'entityId'
=>
$iDealID
,
]
);
The document will be generated, and the method
crm.documentgenerator.document.add
will return its parameters.
"document"
:
{
"products"
:
{
"currencyId"
:
"EUR"
,
"totalSum"
:
1500
,
"totalRows"
:
1
}
,
"downloadUrl"
:
"https://some-domain.bitrix24.com/bitrix/services/main/ajax.php?action=crm.documentgenerator.document.download&SITE_ID=s1&id=29"
,
"publicUrl"
:
null
,
"title"
:
"Product Demonstration Implementation 1"
,
"number"
:
"1"
,
"id"
:
29
,
"createTime"
:
"2025-07-09T16:29:27+02:00"
,
"createdBy"
:
27
,
"updateTime"
:
"2025-07-09T16:29:27+02:00"
,
"templateId"
:
"39"
,
"emailDiskFile"
:
4917
,
"entityId"
:
"1"
,
"entityTypeId"
:
"2"
,
"downloadUrlMachine"
:
"https://some-domain.bitrix24.com/rest/crm.documentgenerator.document.download.json?sessid=c4ad892d7583ead4fd38666a0af85cb7&token=crm%7CYWN0aW9uPWNybS5kb2N1bWVudGdlbmVyYXRvci5kb2N1bWVudC5kb3dubG9hZCZTSVRFX0lEPXMxJmlkPTI5Jl89YlQ2SU9XeGVnR2s3NnZ5M0hGVlRxTDVaRlJtdFgyNTE%3D%7CImNybS5kb2N1bWVudGdlbmVyYXRvci5kb2N1bWVudC5kb3dubG9hZHxjcm18WVdOMGFXOXVQV055YlM1a2IyTjFiV1Z1ZEdkbGJtVnlZWFJ2Y2k1a2IyTjFiV1Z1ZEM1a2IzZHViRzloWkNaVFNWUkZYMGxFUFhNeEptbGtQVEk1Smw4OVlsUTJTVTlYZUdWblIyczNOblo1TTBoR1ZsUnhURFZhUmxKdGRGZ3lOVEU9fGM0YWQ4OTJkNzU4M2VhZDRmZDM4NjY2YTBhZjg1Y2I3Ig%3D%3D.H575mM4Mf%2Fj4PVH2Ngzb1kmkQhdScsAL75ZJkbYkALk%3D"
}
Code Example
Code Example
JS
PHP
document
.
addEventListener
(
'DOMContentLoaded'
,
function
(
) {
let
filePath =
'template.docx'
;
// path to the local template file
let
iDealID =
1
;
// deal identifier
let
sDocName =
'Product Demonstration Implementation'
;
function
fileToBase64
(
filePath
) {
return
new
Promise
(
(
resolve, reject
) =>
{
fetch
(filePath)
.
then
(
response
=>
response.
blob
())
.
then
(
blob
=>
{
let
reader =
new
FileReader
();
reader.
onloadend
=
() =>
resolve
(reader.
result
.
split
(
','
)[
1
]);
reader.
onerror
= reject;
reader.
readAsDataURL
(blob);
});
});
}
async
function
createDocument
(
) {
try
{
let
fileContent =
await
fileToBase64
(filePath);
BX24
.
callMethod
(
'crm.documentgenerator.numerator.add'
,
{
'fields'
: {
'name'
:
'Rest Numerator'
,
'template'
:
'{NUMBER}'
}
},
function
(
resNum
) {
if
(resNum.
error
()) {
console
.
error
(resNum.
error
());
alert
(
'Number generator not added: '
+ resNum.
error_description
());
return
;
}
if
(resNum.
data
().
numerator
.
id
) {
BX24
.
callMethod
(
'crm.documentgenerator.template.add'
,
{
'fields'
: {
'name'
: sDocName,
'numeratorId'
: resNum.
data
().
numerator
.
id
,
'region'
:
'de'
,
'users'
: [
'UA'
],
'entityTypeId'
: [
'2'
],
'file'
: fileContent
}
},
function
(
resTemplate
) {
if
(resTemplate.
error
()) {
console
.
error
(resTemplate.
error
());
alert
(
'Template not added: '
+ resTemplate.
error_description
());
return
;
}
if
(resTemplate.
data
().
template
.
id
) {
BX24
.
callMethod
(
'crm.documentgenerator.document.add'
,
{
'templateId'
: resTemplate.
data
().
template
.
id
,
'entityTypeId'
:
'2'
,
'entityId'
: iDealID
},
function
(
resDoc
) {
if
(resDoc.
error
()) {
console
.
error
(resDoc.
error
());
alert
(
'Document not created: '
+ resDoc.
error_description
());
}
else
{
alert
(
'Document created'
);
}
}
);
}
}
);
}
}
);
}
catch
(error) {
console
.
error
(error);
alert
(
'Error: '
+ error.
message
);
}
}
createDocument
();
});
$filePath
=
__DIR__
.
'/template.docx'
;
// path to the local template file
$iDealID
=
1
;
// deal identifier
$sDocName
=
'Product Demonstration Implementation'
;
$resNum
=
CRest
::
call
(
'crm.documentgenerator.numerator.add'
,
[
'fields'
=> [
'name'
=>
'Rest Numerator'
,
'template'
=>
'{NUMBER}'
,
]
]
);
if
(!
empty
(
$resNum
[
'result'
][
'numerator'
][
'id'
])) {
$resTemplate
=
CRest
::
call
(
'crm.documentgenerator.template.add'
,
[
'fields'
=> [
'name'
=>
$sDocName
,
'numeratorId'
=>
$resNum
[
'result'
][
'numerator'
][
'id'
], // crm.documentgenerator.numerator.add
'region'
=>
'de'
, // eu,de,ua,by,ru
'users'
=> [
'UA'
// User All
],
'entityTypeId'
=> [
'2'
], //
2
— deal in
CRest
::
call
(
'crm.enum.ownertype'
);
'file'
=>
base64_encode
(
file_get_contents
(
$filePath
))
]
]
);
if
(!
empty
(
$resTemplate
[
'result'
][
'template'
][
'id'
])) {
$resDoc
=
CRest
::
call
(
'crm.documentgenerator.document.add'
,
[
'templateId'
=>
$resTemplate
[
'result'
][
'template'
][
'id'
],
'entityTypeId'
=>
'2'
, //
2
— deal in
CRest
::
call
(
'crm.enum.ownertype'
);
'entityId'
=>
$iDealID
,
]
);
}
}
if
(!
empty
(
$resDoc
[
'result'
])) {
echo
json_encode
([
'message'
=>
'Document created'
]);
}
elseif
(!
empty
(
$resDoc
[
'error_description'
])) {
echo
json_encode
([
'message'
=>
'Document not created: '
.
$resDoc
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
'Document not created'
]);
}
Copied
Was the article helpful?
Yes
No
Previous
Add Calendar Event for Client Work
Next
Send E-mail to Client on Behalf of Employee

---

## How to Send an Email to a Client on Behalf of an Employee

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-send-email

How to Send an Email to a Client on Behalf of an Employee | Bitrix24 REST API and Marketplace Applications
How to Send an Email to a Client on Behalf of an Employee
How to Send an Email to a Client on Behalf of an Employee
1. Retrieve Client Data
2. Retrieve Employee Data
3. Create an Activity of Type "Email"
Complete Code Example
Scope:
crm
Who can perform the method: users with permission to modify a CRM entity
An email can be sent automatically through the CRM. The "From" field will display the name and email address of the employee. An event for the outgoing email will be added to the contact's card.
To send the email, we will sequentially execute three methods:
crm.contact.get
— retrieve the client's data
user.get
— retrieve the employee's data
crm.activity.add
— create an activity of type "Email"
1 Retrieve Client Data
1. Retrieve Client Data
We will use the method
crm.contact.get
with the client's identifier. The identifier value can be stored in the variable
contactID
. For example, we will retrieve the contact data with the identifier
1
.
How to Use Examples in Documentation
JS
PHP
let
contactID =
1
;
BX24
.
callMethod
(
'crm.contact.get'
,
{
'id'
: contactID },
function
(
result
) {
if
(result.
error
()) {
reject
(result.
error
());
}
else
{
resolve
(result.
data
());
}
}
);
$contactID
=
1
;
$resultContact
=
CRest
::
call
(
'crm.contact.get'
,
[
'id'
=>
$contactID
]
);
As a result, we will obtain the client's data, including the email address
EMAIL
and the identifier of the responsible employee
ASSIGNED_BY_ID
.
{
"result"
:
{
"ID"
:
"1"
,
"NAME"
:
"Alex"
,
"SECOND_NAME"
:
"Kirillovich"
,
"LAST_NAME"
:
"Vronsky"
,
"ASSIGNED_BY_ID"
:
"61"
,
"EMAIL"
:
[
{
"ID"
:
"1328"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"vronsky@example.com"
,
"TYPE_ID"
:
"EMAIL"
}
]
}
}
2 Retrieve Employee Data
2. Retrieve Employee Data
To get the data of the responsible employee, we will use the method
user.get
with a filter by the employee's identifier. The identifier should take the value from the
ASSIGNED_BY_ID
field of the
resultContact
object.
JS
PHP
BX24
.
callMethod
(
'user.get'
,
{
'filter'
: {
'ID'
: resultContact.
ASSIGNED_BY_ID
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
reject
(result.
error
());
}
else
{
resolve
(result.
data
());
}
}
);
{
$resultUser
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
=>
$resultContact
[
'result'
][
'ASSIGNED_BY_ID'
]
]
]
);
}
We will obtain the employee's data, including the email address
EMAIL
.
{
"result"
:
[
{
"ID"
:
"61"
,
"ACTIVE"
:
true
,
"NAME"
:
"Ivan"
,
"LAST_NAME"
:
"Petrov"
,
"EMAIL"
:
"ivanpetrov@example.com"
}
]
}
3 Create an Activity of Type "Email"
3. Create an Activity of Type "Email"
We will prepare the variables:
contactEmail
— the first element from the
resultContact
contact,
staff
— the first element from the
resultUser
object.
JS
PHP
let
contactEmail = resultContact.
EMAIL
[
0
];
let
staff = resultUser[
0
];
$contactEmail
=
reset
(
$resultContact
[
'result'
][
'EMAIL'
]);
$staff
=
reset
(
$resultUser
[
'result'
]);
To add the event and send the email, we will use the method
crm.activity.add
. We need to pass the client's data, the employee's data, and the activity parameters.
SUBJECT
— the email subject. We will specify
subject email now
.
DESCRIPTION
— the email body. For example,
body email now
.
DESCRIPTION_TYPE
— the text type. Possible values:
1
— plain text,
2
— HTML markup,
3
— BB-code. We will set the value to
3
.
COMPLETED
— a flag indicating whether the event is completed. We will specify
Y
.
DIRECTION
— the direction of the activity. We will pass
2
— outgoing email. A complete list of activity directions can be obtained using the method
crm.enum.activitydirection
.
OWNER_ID
— the contact identifier. We will pass the variable
contactID
.
OWNER_TYPE_ID
—
the identifier of the CRM object type
. We will pass
3
— contact. A complete list of object types can be obtained using the method
crm.enum.ownertype
.
TYPE_ID
— the activity type. We will specify
4
— email. The list of activity types can be obtained using the method
crm.enum.activitytype
.
COMMUNICATIONS
— the client's contact details:
VALUE
— the email address, taking the
VALUE
from the
contactEmail
array,
ENTITY_ID
— the client identifier, passing
contactID
,
ENTITY_TYPE_ID
—
the identifier of the object type
, passing
3
— contact.
START_TIME
and
END_TIME
— the start and end date and time of the activity. We will specify a duration of 1 hour.
RESPONSIBLE_ID
— the identifier of the responsible person, passing
staff.ID
.
SETTINGS
— additional settings:
MESSAGE_FROM
— the email sender, passing the name
staff.NAME
, last name
staff.LAST_NAME
, and email address
staff.EMAIL
of the employee.
JS
PHP
BX24
.
callMethod
(
'crm.activity.add'
,
{
'fields'
: {
"SUBJECT"
:
"subject email now"
,
"DESCRIPTION"
:
"body email now"
,
"DESCRIPTION_TYPE"
:
3
,
"COMPLETED"
:
"Y"
,
"DIRECTION"
:
2
,
"OWNER_ID"
: contactID,
"OWNER_TYPE_ID"
:
3
,
"TYPE_ID"
:
4
,
"COMMUNICATIONS"
: [
{
'VALUE'
: contactEmail.
VALUE
,
'ENTITY_ID'
: contactID,
'ENTITY_TYPE_ID'
:
3
}
],
"START_TIME"
:
new
Date
().
toISOString
(),
"END_TIME"
:
new
Date
(
Date
.
now
() +
3600
*
1000
).
toISOString
(),
"RESPONSIBLE_ID"
: staff.
ID
,
'SETTINGS'
: {
'MESSAGE_FROM'
:
`
${staff.NAME}
${staff.LAST_NAME}
<
${staff.EMAIL}
>`
}
}
}
);
$resultActivity
=
CRest
::
call
(
'crm.activity.add'
,
[
'fields'
=> [
"SUBJECT"
=>
"subject email now"
,
"DESCRIPTION"
=>
"body email now"
,
"DESCRIPTION_TYPE"
=>
3
,//text,html,bbCode type id
in
:
CRest
::
call
(
'crm.enum.contenttype'
);
"COMPLETED"
=>
"Y"
,//send now
"DIRECTION"
=>
2
,//
CRest
::
call
(
'crm.enum.activitydirection'
);
"OWNER_ID"
=>
$contactID
,
"OWNER_TYPE_ID"
=>
3
, //
CRest
::
call
(
'crm.enum.ownertype'
);
"TYPE_ID"
=>
4
, //
CRest
::
call
(
'crm.enum.activitytype'
);
"COMMUNICATIONS"
=> [
[
'VALUE'
=>
$contactEmail
[
'VALUE'
],
'ENTITY_ID'
=>
$contactID
,
'ENTITY_TYPE_ID'
=>
3
//
CRest
::
call
(
'crm.enum.ownertype'
);
]
],
"START_TIME"
=>
date
(
"Y-m-d H:i:s"
,
time
()),
"END_TIME"
=>
date
(
"Y-m-d H:i:s"
,
time
() +
3600
),
"RESPONSIBLE_ID"
=>
$staff
[
'ID'
],
'SETTINGS'
=> [
'MESSAGE_FROM'
=>
implode
(
' '
,
[
$staff
[
'NAME'
],
$staff
[
'LAST_NAME'
],
'<'
.
$staff
[
'EMAIL'
] .
'>'
]
),
],
]
]
);
If the event is successfully created, the method will return its identifier. If you receive an
error
, refer to the documentation for the method
crm.activity.add
for possible error descriptions.
{
"result"
:
3165
,
}
Complete Code Example
Complete Code Example
The code in the example combines all steps: retrieves the client and employee data, adds the "Email" activity, and sends the email to the client.
JS
PHP
document
.
addEventListener
(
'DOMContentLoaded'
,
function
(
) {
async
function
createEmailActivityForContact
(
) {
try
{
let
contactID =
1
;
let
resultContact =
await
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
'crm.contact.get'
,
{
'id'
: contactID },
function
(
result
) {
if
(result.
error
()) {
reject
(result.
error
());
}
else
{
resolve
(result.
data
());
}
}
);
});
if
(resultContact && resultContact.
ASSIGNED_BY_ID
&& resultContact.
EMAIL
) {
let
resultUser =
await
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
'user.get'
,
{
'filter'
: {
'ID'
: resultContact.
ASSIGNED_BY_ID
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
reject
(result.
error
());
}
else
{
resolve
(result.
data
());
}
}
);
});
if
(resultUser.
length
>
0
) {
let
contactEmail = resultContact.
EMAIL
[
0
];
let
staff = resultUser[
0
];
if
(contactEmail.
VALUE
&& staff.
EMAIL
) {
let
resultActivity =
await
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
'crm.activity.add'
,
{
'fields'
: {
"SUBJECT"
:
"subject email now"
,
"DESCRIPTION"
:
"body email now"
,
"DESCRIPTION_TYPE"
:
3
,
"COMPLETED"
:
"Y"
,
"DIRECTION"
:
2
,
"OWNER_ID"
: contactID,
"OWNER_TYPE_ID"
:
3
,
"TYPE_ID"
:
4
,
"COMMUNICATIONS"
: [
{
'VALUE'
: contactEmail.
VALUE
,
'ENTITY_ID'
: contactID,
'ENTITY_TYPE_ID'
:
3
}
],
"START_TIME"
:
new
Date
().
toISOString
(),
"END_TIME"
:
new
Date
(
Date
.
now
() +
3600
*
1000
).
toISOString
(),
"RESPONSIBLE_ID"
: staff.
ID
,
'SETTINGS'
: {
'MESSAGE_FROM'
:
`
${staff.NAME}
${staff.LAST_NAME}
<
${staff.EMAIL}
>`
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
()) {
reject
(result.
error
());
}
else
{
resolve
(result.
data
());
}
}
);
});
if
(resultActivity) {
console
.
log
(
JSON
.
stringify
({
'message'
:
'Activity added'
}));
}
else
{
console
.
log
(
JSON
.
stringify
({
'message'
:
'Activity not added'
}));
}
}
}
}
}
catch
(error) {
console
.
error
(error);
console
.
log
(
JSON
.
stringify
({
'message'
:
'Activity not added: '
+ error.
message
}));
}
}
createEmailActivityForContact
();
});
<?php
$contactID
=
1
;
$resultContact
=
CRest
::
call
(
'crm.contact.get'
,
[
'id'
=>
$contactID
]
);
$resultActivity
= [];
if
(!
empty
(
$resultContact
[
'result'
][
'ASSIGNED_BY_ID'
]) && !
empty
(
$resultContact
[
'result'
][
'EMAIL'
]))
{
$resultUser
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
=>
$resultContact
[
'result'
][
'ASSIGNED_BY_ID'
]
]
]
);
if
(
$resultUser
[
'result'
])
{
$contactEmail
=
reset
(
$resultContact
[
'result'
][
'EMAIL'
]);
$staff
=
reset
(
$resultUser
[
'result'
]);
if
(!
empty
(
$contactEmail
[
'VALUE'
]) && !
empty
(
$staff
[
'EMAIL'
]))
{
$resultActivity
=
CRest
::
call
(
'crm.activity.add'
,
[
'fields'
=> [
"SUBJECT"
=>
"subject email now"
,
"DESCRIPTION"
=>
"body email now"
,
"DESCRIPTION_TYPE"
=>
3
,//text,html,bbCode type id
in
:
CRest
::
call
(
'crm.enum.contenttype'
);
"COMPLETED"
=>
"Y"
,//send now
"DIRECTION"
=>
2
,//
CRest
::
call
(
'crm.enum.activitydirection'
);
"OWNER_ID"
=>
$contactID
,
"OWNER_TYPE_ID"
=>
3
, //
CRest
::
call
(
'crm.enum.ownertype'
);
"TYPE_ID"
=>
4
, //
CRest
::
call
(
'crm.enum.activitytype'
);
"COMMUNICATIONS"
=> [
[
'VALUE'
=>
$contactEmail
[
'VALUE'
],
'ENTITY_ID'
=>
$contactID
,
'ENTITY_TYPE_ID'
=>
3
//
CRest
::
call
(
'crm.enum.ownertype'
);
]
],
"START_TIME"
=>
date
(
"Y-m-d H:i:s"
,
time
()),
"END_TIME"
=>
date
(
"Y-m-d H:i:s"
,
time
() +
3600
),
"RESPONSIBLE_ID"
=>
$staff
[
'ID'
],
'SETTINGS'
=> [
'MESSAGE_FROM'
=>
implode
(
' '
,
[
$staff
[
'NAME'
],
$staff
[
'LAST_NAME'
],
'<'
.
$staff
[
'EMAIL'
] .
'>'
]
),
],
]
]
);
}
}
}
if
(!
empty
(
$resultActivity
[
'result'
]))
{
echo
json_encode
([
'message'
=>
'Activity added'
]);
}
elseif
(!
empty
(
$resultActivity
[
'error_description'
]))
{
echo
json_encode
([
'message'
=>
'Activity not added: '
.
$resultActivity
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
'Activity not added'
]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
Add Template and Create Document Based on It
Next
Add Comment to Smart Process Timeline

---

## How to Add a Comment to the Timeline of a Smart Process

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-comment-to-spa

How to Add a Comment to the Timeline of a Smart Process | Bitrix24 REST API and Marketplace Applications
How to Add a Comment to the Timeline of a Smart Process
How to Add a Comment to the Timeline of a Smart Process
1. Retrieve the Smart Process Type Identifier
2. Add a Comment to the Smart Process Entity
Code Example
Scope:
crm
Who can execute the method: users with permission to modify the CRM entity
The key parameter for adding a comment to a CRM entity is the
object type identifier
. This identifier indicates which type of object the comment will be added to: a deal, a lead, or a specific smart process. The identifier is used in the parameters
OWNER_TYPE
,
OWNER_TYPE_ID
,
ENTITY_TYPE
, and
ENTITY_TYPE_ID
of the method groups
crm.item.*
,
crm.timeline.*
,
crm.activity.*
.
There are two types of object identifiers in CRM:
Predefined
— these are identifiers for
leads
,
deals
,
companies
,
contacts
,
invoices
, and
estimates
. The identifiers for predefined objects can be found in the
documentation
.
Dynamic
— these are identifiers for smart processes. The smart process identifier is generated at the time of creation and does not depend on the name of the smart process.
You can obtain the identifier of a smart process using two methods:
crm.enum.ownertype
— a method without parameters that returns an enumeration of CRM object types, both predefined and dynamic.
crm.type.list
— a method with a filter that returns only dynamic CRM objects.
To create a comment in a smart process entity, we will sequentially execute two methods:
crm.type.list
— retrieve the smart process by filter.
crm.timeline.comment.add
— create the comment.
1. Retrieve the Smart Process Type Identifier
1. Retrieve the Smart Process Type Identifier
To obtain the type identifier, we use the method
crm.type.list
with a filter:
title
—   specify the name of the smart process.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'crm.type.list'
,
{
filter
: {
"title"
:
"Equipment Purchase"
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
'crm.type.list'
,
[
'filter'
=> [
'title'
=>
'Equipment Purchase'
]
]
);
As a result, we obtain two ID values:
id
:
7
— the ordinal number of the smart process in Bitrix.
entityTypeId
:
177
— the identifier of the smart process type. This parameter is necessary for the next request.
{
"result"
:
{
"types"
:
[
{
"id"
:
7
,
"title"
:
"Equipment Purchase"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
177
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"Y"
,
"isStagesEnabled"
:
"Y"
,
"isBeginCloseDatesEnabled"
:
"Y"
,
"isClientEnabled"
:
"Y"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"Y"
,
"isMycompanyEnabled"
:
"Y"
,
"isDocumentsEnabled"
:
"Y"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"Y"
,
"isRecyclebinEnabled"
:
"Y"
,
"isAutomationEnabled"
:
"Y"
,
"isBizProcEnabled"
:
"Y"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2021-11-26T10:52:17+03:00"
,
"updatedTime"
:
"2024-11-12T15:32:39+03:00"
,
"updatedBy"
:
1
}
]
}
}
2. Add a Comment to the Smart Process Entity
2. Add a Comment to the Smart Process Entity
To add a comment, we use the method
crm.timeline.comment.add
with the following parameters:
ENTITY_ID
—   ID of the entity. To obtain the ID value, use the method
crm.item.list
, where
entityTypeId
filter equals the
entityTypeId
value from
crm.type.list
.
ENTITY_TYPE
— specify
DYNAMIC_177
. The value consists of the
entityTypeId
from the result of the previous method and the prefix for dynamic objects
DYNAMIC_
.
COMMENT
— the text value of the comment.
JS
PHP
BX24
.
callMethod
(
"crm.timeline.comment.add"
,
{
fields
:
{
"ENTITY_ID"
:
19
,
"ENTITY_TYPE"
:
"DYNAMIC_177"
,
"COMMENT"
:
"Confirm the purchase via e-mail!"
,
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
'crm.timeline.comment.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
19
,
'ENTITY_TYPE'
=>
'DYNAMIC_177'
,
'COMMENT'
=>
'Confirm the purchase via e-mail!'
,
]
]
);
We added a comment to the timeline of the smart process entity and received the timeline record ID
55771
in response. This record ID can be used in the methods for
updating
and
deleting
the comment.
{
"result"
:
55771
}
Code Example
Code Example
JS
PHP
// Function to find the smart process identifier
function
findSPA
(
) {
// Name of the smart process to obtain entityTypeId
var
SPAtitle
=
'your_smart_process_name'
;
// Call the crm.type.list method to get entityTypeId
BX24
.
callMethod
(
'crm.type.list'
,
{
filter
: {
title
:
SPAtitle
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
(
'Error finding smart process:'
, result.
error
());
}
else
{
var
types = result.
data
().
types
;
if
(
Array
.
isArray
(types) && types.
length
>
0
) {
var
SPAId
= types[
0
].
entityTypeId
;
// Assuming the desired object is the first in the array
console
.
log
(
'Smart process found'
,
SPAId
);
createComment
(
SPAId
);
}
else
{
console
.
error
(
'Smart process not found or data is empty'
);
}
}
}
);
}
// Function to create a comment in the smart process entity
function
createComment
(
SPAId
) {
// ID of the entity to which the comment will be added
var
elementId =
'your_element_ID'
;
// Text of the comment
var
commentText =
'your_comment'
;
// Call the crm.timeline.comment.add method to add the comment
BX24
.
callMethod
(
"crm.timeline.comment.add"
,
{
fields
: {
ENTITY_ID
: elementId,
ENTITY_TYPE
:
'DYNAMIC_'
+
SPAId
,
COMMENT
: commentText
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
(
'Error creating comment:'
, result.
error
());
}
else
{
console
.
log
(
'Comment added'
, result.
data
());
}
}
);
}
// Call the function to find the smart process and add a comment
findSPA
();
require_once
(
'crest.php'
);
// Function to find the smart process identifier
function
findSPA
(
)
{
// Name of the smart process to obtain entityTypeId
$SPAtitle
=
'your_smart_process_name'
;
// Call the crm.type.list method to get entityTypeId
$result
=
CRest
::
call
(
'crm.type.list'
,
[
'filter'
=> [
'title'
=>
$SPAtitle
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
'Error finding smart process: '
.
$result
[
'error'
];
}
else
{
$types
=
$result
[
'result'
][
'types'
];
if
(
is_array
(
$types
) &&
count
(
$types
) >
0
) {
$SPAId
=
$types
[
0
][
'entityTypeId'
];
// Assuming the desired object is the first in the array
echo
'Smart process found: '
.
$SPAId
;
createComment
(
$SPAId
);
}
else
{
echo
'Smart process not found or data is empty'
;
}
}
}
// Function to create a comment in the smart process entity
function
createComment
(
$SPAId
)
{
// ID of the entity to which the comment will be added
$elementId
=
'your_element_ID'
;
// Text of the comment
$commentText
=
'your_comment'
;
// Call the crm.timeline.comment.add method to add the comment
$result
=
CRest
::
call
(
'crm.timeline.comment.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
$elementId
,
'ENTITY_TYPE'
=>
'DYNAMIC_'
.
$SPAId
,
'COMMENT'
=>
$commentText
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
'Error creating comment: '
.
$result
[
'error'
];
}
else
{
echo
'Comment added'
;
}
}
// Call the function to find the smart process and add a comment
findSPA
();
Copied
Was the article helpful?
Yes
No
Previous
Send E-mail to Client on Behalf of Employee
Next
Create Custom Field in Smart Process

---

## How to Create a Custom Field in a SPA

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-user-field-to-spa

How to Create a Custom Field in a SPA | Bitrix24 REST API and Marketplace Applications
How to Create a Custom Field in a SPA
How to Create a Custom Field in a SPA
1. Retrieve the SPA Identifier
2. Create a Custom Field in the SPA
Code Example
Scope:
crm, userfieldconfig
Who can execute the method: users with permission to modify the SPA
Custom fields enhance the functionality of the CRM to meet your business needs:
You can create fields to store information in various formats: string, money, number, address, file, and others.
You can configure field characteristics: names for different languages, multiple field flag, rounding settings for numeric fields, and more.
To create a custom field in a SPA, we will sequentially execute two methods:
crm.type.list
— retrieve the SPA ID.
userfieldconfig.add
— create a custom field in the SPA.
1. Retrieve the SPA Identifier
1. Retrieve the SPA Identifier
To obtain the SPA ID, we use the method
crm.type.list
with the filter:
title
— specify the name of the SPA.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'crm.type.list'
,
{
filter
: {
// array of fields for filtering
"title"
:
"Equipment Purchase"
// name of the SPA
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
'crm.type.list'
,
[
'filter'
=> [
'title'
=>
'Equipment Purchase'
// name of the SPA
]
]
);
As a result, we will receive the id — this is the ordinal number of the SPA in Bitrix24. In the example,
id
:
7
.
{
"result"
:
{
"types"
:
[
{
"id"
:
7
,
"title"
:
"Equipment Purchase"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
177
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"Y"
,
"isStagesEnabled"
:
"Y"
,
"isBeginCloseDatesEnabled"
:
"Y"
,
"isClientEnabled"
:
"Y"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"Y"
,
"isMycompanyEnabled"
:
"Y"
,
"isDocumentsEnabled"
:
"Y"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"Y"
,
"isRecyclebinEnabled"
:
"Y"
,
"isAutomationEnabled"
:
"Y"
,
"isBizProcEnabled"
:
"Y"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2021-11-26T10:52:17+03:00"
,
"updatedTime"
:
"2024-11-12T15:32:39+03:00"
,
"updatedBy"
:
1
}
]
}
}
2. Create a Custom Field in the SPA
2. Create a Custom Field in the SPA
To create a custom field, we use the method
userfieldconfig.add
with the following parameters:
moduleId
— the identifier of the module in which the method will create the field, a required parameter. The module for SPAs is
crm
.
field[entityId]
— the identifier of the object in the format
CRM_ + {ID}
, where ID is the ordinal number of the SPA in Bitrix24 from the result of
crm.type.list
, a required parameter. In the example, we will specify
CRM_7
.
field[fieldName]
— the field code in the format
UF_ + {object identifier} + _ + {arbitrary string in UPPERCASE}
. The length limit for the code is 50 characters, a required parameter. In the example, we will specify
UF_CRM_7_NEW_REST_LIST
.
field[userTypeId]
— the identifier of the
field type
, a required parameter. In the example, we will specify
enumeration
to create a list-type field, and we will pass the list values in a separate
enum
array.
field[multiple]
— the multiple field flag, an optional parameter. The multiplicity flag cannot be changed after the field is created.
field[editFormLabel]
— an array of names for displaying the field in Bitrix24 in different languages. An optional parameter; if no name is provided, the field code will be displayed in Bitrix24.
JS
PHP
BX24
.
callMethod
(
'userfieldconfig.add'
,
{
moduleId
:
'crm'
,
// Module identifier
field
: {
entityId
:
'CRM_7'
,
// Object identifier
fieldName
:
'UF_CRM_7_NEW_REST_LIST'
,
// Field code
userTypeId
:
'enumeration'
,
// Field type identifier
multiple
:
'Y'
,
// Multiple field flag
editFormLabel
: {
'de'
:
'Merkmal Liste'
,
// Field name in German
'en'
:
'List of characteristics'
// Field name in English
},
enum
: [
// List field values
{
value
:
'Characteristic 1'
,
// Option value
def
:
'N'
,
// Default value flag
sort
:
100
,
// Sort index
},
{
value
:
'Characteristic 2'
,
def
:
'Y'
,
// This option will be the default value
sort
:
200
,
}
]
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
'userfieldconfig.add'
,
[
'moduleId'
=>
'crm'
, // Module identifier
'field'
=> [
'entityId'
=>
'CRM_7'
, // Object identifier
'fieldName'
=>
'UF_CRM_7_NEW_REST_LIST'
, // Field code
'userTypeId'
=>
'enumeration'
, // Field type identifier
'multiple'
=>
'Y'
, // Multiple field flag
'editFormLabel'
=> [
'de'
=>
'Merkmal Liste'
, // Field name in German
'en'
=>
'List of characteristics'
// Field name in English
],
'enum'
=> [ // List field values
[
'value'
=>
'Characteristic 1'
, // Option value
'def'
=>
'N'
, // Default value flag
'sort'
=>
100
, // Sort index
],
[
'value'
=>
'Characteristic 2'
,
'def'
=>
'Y'
, // This option will be the
default
value
'sort'
=>
200
,
]
]
]
]
);
As a result, we will receive the data of the created field.
{
"result"
:
{
"field"
:
{
"id"
:
"6953"
,
"entityId"
:
"CRM_7"
,
"fieldName"
:
"UF_CRM_7_NEW_REST_LIST"
,
"userTypeId"
:
"enumeration"
,
"xmlId"
:
null
,
"sort"
:
"100"
,
"multiple"
:
"Y"
,
"mandatory"
:
"N"
,
"showFilter"
:
"N"
,
"showInList"
:
"Y"
,
"editInList"
:
"Y"
,
"isSearchable"
:
"N"
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
"languageId"
:
{
"en"
:
"en"
,
"de"
:
"de"
}
,
"editFormLabel"
:
{
"en"
:
"List of characteristics"
,
"de"
:
"Merkmal Liste"
}
,
"listColumnLabel"
:
{
"en"
:
null
,
"de"
:
null
}
,
"listFilterLabel"
:
{
"en"
:
null
,
"de"
:
null
}
,
"errorMessage"
:
{
"en"
:
null
,
"de"
:
null
}
,
"helpMessage"
:
{
"en"
:
null
,
"de"
:
null
}
,
"enum"
:
[
{
"id"
:
"3363"
,
"userFieldId"
:
"6953"
,
"value"
:
"Characteristic 1"
,
"def"
:
"N"
,
"sort"
:
"100"
,
"xmlId"
:
"56dff18efcfe25f3bae0117a6b372567"
}
,
{
"id"
:
"3365"
,
"userFieldId"
:
"6953"
,
"value"
:
"Characteristic 2"
,
"def"
:
"Y"
,
"sort"
:
"200"
,
"xmlId"
:
"42e3ebcf5506a65283bf3bf510d8f05a"
}
]
}
}
,
}
Code Example
Code Example
JS
PHP
// Function to retrieve the SPA and create a custom field
function
getCrmTypeAndAddUserField
(
) {
// Variable for user input of the SPA name
var
processTitle =
prompt
(
"Enter the name of the SPA to search:"
,
"Your_Process_Name"
);
// Call the crm.type.list method to retrieve the SPA
BX24
.
callMethod
(
'crm.type.list'
,
{
filter
: {
"title"
: processTitle
// Use the name entered by the user
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
(
'Error retrieving the SPA:'
, result.
error
());
}
else
{
console
.
log
(
'SPA successfully retrieved:'
, result.
data
());
var
spaId = result.
data
().
types
[
0
].
id
;
// Use the id from the result
addUserField
(spaId);
}
}
);
}
// Function to create a custom field
function
addUserField
(
spaId
) {
// Call the userfieldconfig.add method to create a custom field
BX24
.
callMethod
(
'userfieldconfig.add'
,
{
moduleId
:
'crm'
,
field
: {
entityId
:
'CRM_'
+ spaId,
// Use the id from the previous result
fieldName
:
'UF_CRM_'
+ spaId +
'_NEW_REST_LIST'
,
// Use the id
userTypeId
:
'enumeration'
,
multiple
:
'Y'
,
editFormLabel
: {
'de'
:
'Merkmal Liste'
,
'en'
:
'List of characteristics'
},
enum
: [
{
value
:
'Characteristic 1'
,
def
:
'N'
,
sort
:
100
},
{
value
:
'Characteristic 2'
,
def
:
'Y'
,
sort
:
200
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
()) {
console
.
error
(
'Error creating custom field:'
, result.
error
());
}
else
{
console
.
log
(
'Custom field successfully created:'
, result.
data
());
}
}
);
}
// Call the function to retrieve SPA data and create a custom field
getCrmTypeAndAddUserField
();
require_once
(
'crest.php'
);
// Function to retrieve the SPA and create a custom field
function
getCrmTypeAndAddUserField
(
$processTitle
)
{
// Call the crm.type.list method to retrieve the SPA
$result
=
CRest
::
call
(
'crm.type.list'
, [
'filter'
=> [
'title'
=>
$processTitle
// Use the name entered by the user
]
]);
if
(
isset
(
$result
[
'error'
])) {
echo
'Error retrieving the SPA: '
.
$result
[
'error_description'
];
}
else
{
echo
'SPA successfully retrieved: '
;
print_r
(
$result
[
'result'
]);
if
(!
empty
(
$result
[
'result'
][
'types'
])) {
$spaId
=
$result
[
'result'
][
'types'
][
0
][
'id'
];
// Use the id from the result
addUserField
(
$spaId
);
}
else
{
echo
'SPA not found.'
;
}
}
}
// Function to create a custom field
function
addUserField
(
$spaId
)
{
// Call the userfieldconfig.add method to create a custom field
$result
=
CRest
::
call
(
'userfieldconfig.add'
, [
'moduleId'
=>
'crm'
,
'field'
=> [
'entityId'
=>
'CRM_'
.
$spaId
, // Use the id
from
the previous result
'fieldName'
=>
'UF_CRM_'
.
$spaId
.
'_NEW_REST_LIST'
, // Use the id
'userTypeId'
=>
'enumeration'
,
'multiple'
=>
'Y'
,
'editFormLabel'
=> [
'de'
=>
'Merkmal Liste'
,
'en'
=>
'List of characteristics'
],
'enum'
=> [
[
'value'
=>
'Characteristic 1'
,
'def'
=>
'N'
,
'sort'
=>
100
],
[
'value'
=>
'Characteristic 2'
,
'def'
=>
'Y'
,
'sort'
=>
200
]
]
]
]);
if
(
isset
(
$result
[
'error'
])) {
echo
'Error creating custom field: '
.
$result
[
'error_description'
];
}
else
{
echo
'Custom field successfully created: '
;
print_r
(
$result
[
'result'
]);
}
}
// Call the function to retrieve SPA data and create a custom field
$processTitle
=
readline
(
"Enter the name of the SPA to search: "
);
getCrmTypeAndAddUserField
(
$processTitle
);
Copied
Was the article helpful?
Yes
No
Previous
Add Comment to Smart Process Timeline
Next
Set Up Rounding for Custom Field of Type "Number"

---

## How to Set Up Rounding for a Custom Field of Type "Number"

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-precision-to-user-field

How to Set Up Rounding for a Custom Field of Type "Number" | Bitrix24 REST API and Marketplace Applications
How to Set Up Rounding for a Custom Field of Type "Number"
How to Set Up Rounding for a Custom Field of Type "Number"
Creating a Numeric Field with Rounding Setting
Modifying the Setting of an Existing Numeric Field
1. Getting the Field ID
2. Modifying the Rounding Setting for the Field Value
Code Example
Custom fields have standard settings: name, required status, and multiple values.
Additionally, there are specialized settings depending on the field type:
values for the list
rounding precision for numbers
currency for monetary fields
To obtain specialized settings for the "Number" type —
double
, we use the method
crm.userfield.settings.fields
:
JS
PHP
BX24
.
callMethod
(
"crm.userfield.settings.fields"
,
{
type
:
"double"
// type of the custom field
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
'crm.userfield.settings.fields'
,
[
'type'
=>
'double'
// Type of the custom field
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
'Error: '
.
$result
[
'error_description'
];
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
As a result, we will receive two settings: default value and precision.
{
"result"
:
{
"DEFAULT_VALUE"
:
{
"type"
:
"double"
,
"title"
:
"Default Value"
}
,
"PRECISION"
:
{
"type"
:
"int"
,
"title"
:
"Precision"
}
}
}
Creating a Numeric Field with Rounding Setting
Creating a Numeric Field with Rounding Setting
We will create a field of type number with a precision setting of three decimal places. If a value with four or more decimal places is entered in the field, it will automatically round to three decimal places.
To create a custom field, we use the method
userfieldconfig.add
with the following parameters:
moduleId
— the identifier of the module in which the method will create the field, a required parameter. In the example, we create a field for deals, the module is
crm
.
field[entityId]
— the identifier of the object in the format
CRM_ + {ID}
, a required parameter. The list of identifiers for objects can be found in the article —
Entity ID Identifiers
. In the example, we will specify
CRM_DEAL
.
field[fieldName]
— the field code in the format
UF_ + {object identifier} + _ + {arbitrary string in UPPERCASE}
. The length limit for the code is 50 characters, a required parameter. In the example, we will specify
UF_CRM_DEAL_NEW_DOUBLE_FIELD
.
field[userTypeId]
— the identifier of the
field type
, a required parameter. In the example, we will specify
double
to create a number type field.
field[editFormLabel]
— an array of names for displaying the field in Bitrix24 in different languages. An optional parameter; if no name is provided, the field code will be displayed in Bitrix24.
field[settings]
— an array of additional settings for the field depending on its type. An optional parameter; if not provided, default settings will be used. In the example, we will specify the
PRECISION
setting — precision. We will pass an integer equal to the number of decimal places.
JS
PHP
BX24
.
callMethod
(
'userfieldconfig.add'
,
{
moduleId
:
'crm'
,
// Module identifier
field
: {
entityId
:
'CRM_DEAL'
,
// Object identifier
fieldName
:
'UF_CRM_DEAL_NEW_DOUBLE_FIELD'
,
// Field code
userTypeId
:
'double'
,
// Field type identifier
editFormLabel
: {
'en'
:
'Number with Rounding'
,
// Field name in English
'en'
:
'PRECISION double'
// Field name in English
},
settings
: {
// Additional field settings
PRECISION
:
3
,
// Number of decimal places
},
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
'userfieldconfig.add'
,
[
'moduleId'
=>
'crm'
, // Module identifier
'field'
=> [
'entityId'
=>
'CRM_DEAL'
, // Object identifier
'fieldName'
=>
'UF_CRM_DEAL_NEW_DOUBLE_FIELD'
, // Field code
'userTypeId'
=>
'double'
, // Field type identifier
'editFormLabel'
=> [
'en'
=>
'Number with Rounding'
, // Field name in English
'en'
=>
'PRECISION double'
// Field name in English
],
'settings'
=> [ // Additional field settings
'PRECISION'
=>
3
// Number of decimal places
]
]
]
);
As a result, we will receive the data of the created field.
{
"result"
:
{
"field"
:
{
"id"
:
"6961"
,
"entityId"
:
"CRM_DEAL"
,
"fieldName"
:
"UF_CRM_DEAL_NEW_DOUBLE_FIELD"
,
"userTypeId"
:
"double"
,
"xmlId"
:
null
,
"sort"
:
"100"
,
"multiple"
:
"N"
,
"mandatory"
:
"N"
,
"showFilter"
:
"N"
,
"showInList"
:
"Y"
,
"editInList"
:
"Y"
,
"isSearchable"
:
"N"
,
"settings"
:
{
"PRECISION"
:
3
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
"languageId"
:
{
"en"
:
"en"
}
,
"editFormLabel"
:
{
"en"
:
"PRECISION double"
,
"en"
:
"Number with Rounding"
}
,
"listColumnLabel"
:
{
"en"
:
null
}
,
"listFilterLabel"
:
{
"en"
:
null
}
,
"errorMessage"
:
{
"en"
:
null
}
,
"helpMessage"
:
{
"en"
:
null
}
}
}
,
}
Modifying the Setting of an Existing Numeric Field
Modifying the Setting of an Existing Numeric Field
To change the rounding setting of an existing field, we use the method
userfieldconfig.update
by specifying the field ID. The field ID can be obtained in two ways: when creating the field using the method
userfieldconfig.add
or through the method to retrieve the list of custom fields of the object. In the example, the field is for deals, so we will use the method
crm.deal.userfield.list
.
1. Getting the Field ID
1. Getting the Field ID
To get the field ID, we use the method
crm.deal.userfield.list
with the following parameters:
filter[LANG]
— a filter by language used to display field names in the desired language. Without this filter, names will not be displayed.
filter[USER_TYPE_ID]
— a filter by field type used to retrieve only fields of type "Number" in the result.
JS
PHP
BX24
.
callMethod
(
"crm.deal.userfield.list"
,
{
filter
: {
LANG
:
'en'
,
// Language filter for displaying field name
USER_TYPE_ID
:
'double'
// Field type filter
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
'crm.deal.userfield.list'
,
[
'filter'
=> [
'LANG'
=>
'en'
, // Language filter
for
displaying field name
'USER_TYPE_ID'
=>
'double'
// Field type filter
]
]
);
As a result, we will receive all numeric fields of deals with names.
{
"result"
:
[
{
"ID"
:
"6963"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1740471712"
,
"USER_TYPE_ID"
:
"double"
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
"N"
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
"EDIT_FORM_LABEL"
:
"Advance"
,
"LIST_COLUMN_LABEL"
:
"Advance"
,
"LIST_FILTER_LABEL"
:
"Advance"
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
"6807"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1723464314"
,
"USER_TYPE_ID"
:
"double"
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
"N"
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
"EDIT_FORM_LABEL"
:
"Refund Amount"
,
"LIST_COLUMN_LABEL"
:
"Refund Amount"
,
"LIST_FILTER_LABEL"
:
"Refund Amount"
,
"ERROR_MESSAGE"
:
null
,
"HELP_MESSAGE"
:
null
}
]
,
"total"
:
2
,
}
2. Modifying the Rounding Setting for the Field Value
2. Modifying the Rounding Setting for the Field Value
To change the setting of an existing field, we use the method
userfieldconfig.update
with the following parameters:
moduleId
— the identifier of the module in which the method will modify the field, a required parameter. In the example, we modify the field for deals, the module is
crm
.
id
— the identifier of the custom field, a required parameter. In the example, we will pass the field ID obtained from the method
crm.deal.userfield.list
.
field[settings]
— an array of additional settings for the field depending on its type. In the example, we will specify the
PRECISION
setting — precision. We will pass an integer equal to the number of decimal places.
JS
PHP
BX24
.
callMethod
(
'userfieldconfig.update'
,
{
moduleId
:
'crm'
,
// Module identifier
id
:
6807
,
// ID of the custom field
field
: {
settings
: {
// Additional field settings
PRECISION
:
3
,
// Number of decimal places
},
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
'userfieldconfig.update'
,
[
'moduleId'
=>
'crm'
, // Module identifier
'id'
=>
6807
, // ID of the custom field
'field'
=> [
'settings'
=> [ // Additional field settings
'PRECISION'
=>
3
// Number of decimal places
]
]
]
);
As a result, we will receive the data of the modified field.
{
"result"
:
{
"field"
:
{
"id"
:
"6807"
,
"entityId"
:
"CRM_DEAL"
,
"fieldName"
:
"UF_CRM_1723464314"
,
"userTypeId"
:
"double"
,
"xmlId"
:
null
,
"sort"
:
"150"
,
"multiple"
:
"N"
,
"mandatory"
:
"N"
,
"showFilter"
:
"E"
,
"showInList"
:
"Y"
,
"editInList"
:
"Y"
,
"isSearchable"
:
"N"
,
"settings"
:
{
"PRECISION"
:
3
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
"languageId"
:
{
"en"
:
"en"
}
,
"editFormLabel"
:
{
"en"
:
"Refund Amount"
}
,
"listColumnLabel"
:
{
"en"
:
"Refund Amount"
}
,
"listFilterLabel"
:
{
"en"
:
"Refund Amount"
}
,
"errorMessage"
:
{
"en"
:
null
}
,
"helpMessage"
:
{
"en"
:
null
}
}
}
,
}
Code Example
Code Example
JS
PHP
// Function to find and update a custom field
function
updateUserField
(
) {
// Prompt the user for the field name
var
fieldName =
prompt
(
"Enter the field name:"
);
// First method: Get a list of all custom fields of type 'double'
BX24
.
callMethod
(
"crm.deal.userfield.list"
,
{
filter
: {
LANG
:
'en'
,
// Language filter for displaying field name
USER_TYPE_ID
:
'double'
// Field type filter
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
// Iterate through the retrieved fields to find the one by name
var
fields = result.
data
();
var
fieldId =
null
;
for
(
var
i =
0
; i < fields.
length
; i++) {
if
(fields[i].
EDIT_FORM_LABEL
=== fieldName) {
fieldId = fields[i].
ID
;
break
;
}
}
if
(fieldId) {
// Second method: Update the settings of the found field
BX24
.
callMethod
(
'userfieldconfig.update'
,
{
moduleId
:
'crm'
,
// Module identifier
id
: fieldId,
// ID of the found custom field
field
: {
settings
: {
PRECISION
:
3
// Number of decimal places
}
}
},
function
(
updateResult
) {
if
(updateResult.
error
()) {
console
.
error
(updateResult.
error
());
}
else
{
console
.
log
(
"Field settings successfully updated."
);
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
"Field with the specified name not found."
);
}
}
}
);
}
// Run the function
updateUserField
();
require_once
(
'crest.php'
);
// Function to find and update a custom field
function
updateUserField
(
$fieldName
)
{
// First method: Get a list of all custom fields of type 'double'
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
'LANG'
=>
'en'
, // Language filter
for
displaying field name
'USER_TYPE_ID'
=>
'double'
// Field type filter
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
'Error: '
.
$result
[
'error_description'
];
}
else
{
// Iterate through the retrieved fields to find the one by name
$fields
=
$result
[
'result'
];
$fieldId
=
null
;
foreach
(
$fields
as
$field
) {
if
(
$field
[
'EDIT_FORM_LABEL'
] ===
$fieldName
) {
$fieldId
=
$field
[
'ID'
];
break
;
}
}
if
(
$fieldId
) {
// Second method: Update the settings of the found field
$updateResult
=
CRest
::
call
(
'userfieldconfig.update'
,
[
'moduleId'
=>
'crm'
, // Module identifier
'id'
=>
$fieldId
, // ID of the found custom field
'field'
=> [
'settings'
=> [
'PRECISION'
=>
3
// Number of decimal places
]
]
]
);
if
(
isset
(
$updateResult
[
'error'
])) {
echo
'Error: '
.
$updateResult
[
'error_description'
];
}
else
{
echo
'Field settings successfully updated.'
;
}
}
else
{
echo
'Field with the specified name not found.'
;
}
}
}
// Prompt the user for the field name
$fieldName
=
readline
(
"Enter the field name: "
);
// Run the function
updateUserField
(
$fieldName
);
Copied
Was the article helpful?
Yes
No
Previous
Create Custom Field in Smart Process
Next
How to Create a New Sales Funnel with Stages in Smart Process

---

## How to Create a New Sales Funnel with Stages in a Smart Process

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-add-crm-objects/how-to-add-category-to-spa

How to Create a New Sales Funnel with Stages in a Smart Process | Bitrix24 REST API and Marketplace Applications
How to Create a New Sales Funnel with Stages in a Smart Process
How to Create a New Sales Funnel with Stages in a Smart Process
1. Retrieve the Smart Process Identifier
2. Create a New Funnel
3. Retrieve the Stages of the Created Funnel
4. Modify the Pre-installed Stage
5. Add a New Stage to the Funnel
Code Example
Scope:
crm
Who can execute methods: users with administrative access to the CRM section
Sales funnels allow you to divide work in CRM into different stages. For example, a sale can consist of three funnels: sales, delivery, and post-sale service. Access permissions and the view of the CRM entity card can be configured for each funnel.
To create a new funnel in a smart process, we will sequentially execute the following methods:
crm.type.list
— retrieve the numeric identifier of the smart process type.
crm.category.add
— create a new funnel.
crm.status.list
— retrieve the pre-installed stages of the new funnel.
crm.status.update
— modify the pre-installed stage.
crm.status.add
— add a new stage.
1. Retrieve the Smart Process Identifier
1. Retrieve the Smart Process Identifier
Use the method
crm.type.list
with a filter by the smart process
title
.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'crm.type.list'
,
{
filter
: {
title
:
'Equipment Purchase'
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
return
;
}
var
types = result.
data
().
types
;
if
(types.
length
>
0
) {
var
entityTypeId = types[
0
].
entityTypeId
;
console
.
log
(
'entityTypeId:'
, entityTypeId);
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
'crm.type.list'
,
[
'filter'
=> [
'title'
=>
'Equipment Purchase'
] ]
);
$entityTypeId
=
$result
[
'result'
][
'types'
][
0
][
'entityTypeId'
];
As a result, we will obtain and save the
entityTypeId
of the required smart process.
{
"result"
:
{
"types"
:
[
{
"id"
:
7
,
"title"
:
"Equipment Purchase"
,
"code"
:
""
,
"createdBy"
:
1
,
"entityTypeId"
:
177
,
"customSectionId"
:
null
,
"isCategoriesEnabled"
:
"Y"
,
"isStagesEnabled"
:
"Y"
,
"isBeginCloseDatesEnabled"
:
"Y"
,
"isClientEnabled"
:
"Y"
,
"isUseInUserfieldEnabled"
:
"Y"
,
"isLinkWithProductsEnabled"
:
"Y"
,
"isMycompanyEnabled"
:
"Y"
,
"isDocumentsEnabled"
:
"Y"
,
"isSourceEnabled"
:
"Y"
,
"isObserversEnabled"
:
"Y"
,
"isRecyclebinEnabled"
:
"Y"
,
"isAutomationEnabled"
:
"Y"
,
"isBizProcEnabled"
:
"Y"
,
"isSetOpenPermissions"
:
"Y"
,
"isPaymentsEnabled"
:
"N"
,
"isCountersEnabled"
:
"N"
,
"createdTime"
:
"2021-11-26T10:52:17+03:00"
,
"updatedTime"
:
"2024-11-12T15:32:39+03:00"
,
"updatedBy"
:
1
,
"isInitialized"
:
"Y"
}
]
}
,
"total"
:
1
,
"time"
:
{
"start"
:
1751955574.022139
,
"finish"
:
1751955574.065841
,
"duration"
:
0.043701887130737305
,
"processing"
:
0.00709080696105957
,
"date_start"
:
"2025-07-08T09:19:34+03:00"
,
"date_finish"
:
"2025-07-08T09:19:34+03:00"
,
"operating_reset_at"
:
1751956174
,
"operating"
:
0
}
}
2. Create a New Funnel
2. Create a New Funnel
Use the method
crm.category.add
with the following parameters:
entityTypeId
— the numeric identifier of the type from the method
crm.type.list
,
fields[name]
— the name of the funnel,
fields[sort]
— the sorting of the funnel. Sorting affects the position of the funnel in the list.
JS
PHP
BX24
.
callMethod
(
'crm.category.add'
,
{
entityTypeId
: entityTypeId,
fields
: {
name
:
'New Funnel'
,
sort
:
100
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
return
;
}
var
categoryId = result.
data
().
category
.
id
;
console
.
log
(
'categoryId:'
, categoryId);
}
);
$result
=
CRest
::
call
(
'crm.category.add'
,
[
'entityTypeId'
=>
$entityTypeId
,
'fields'
=> [
'name'
=>
'New Funnel'
,
'sort'
=>
100
,
]
]
);
$categoryId
=
$result
[
'result'
][
'category'
][
'id'
];
As a result, we will obtain and save the
id
of the created funnel.
{
"result"
:
{
"category"
:
{
"id"
:
39
,
"name"
:
"New Funnel"
,
"sort"
:
100
,
"entityTypeId"
:
177
,
"isDefault"
:
"N"
}
}
,
"time"
:
{
"start"
:
1751955674.679973
,
"finish"
:
1751955674.87359
,
"duration"
:
0.1936171054840088
,
"processing"
:
0.1517810821533203
,
"date_start"
:
"2025-07-08T09:21:14+03:00"
,
"date_finish"
:
"2025-07-08T09:21:14+03:00"
,
"operating_reset_at"
:
1751956274
,
"operating"
:
0.15175914764404297
}
}
3. Retrieve the Stages of the Created Funnel
3. Retrieve the Stages of the Created Funnel
Use the method
crm.status.list
with the filter:
ENTITY_ID
— the identifier of the CRM directory. For smart process stages, the identifier has the format
DYNAMIC_{entityTypeId}_STAGE_{categoryId}
:
{entityTypeId}
— the numeric identifier of the smart process type from the method
crm.type.list
,
{categoryId}
— the identifier of the funnel from the method
crm.category.add
.
JS
PHP
var
entityId =
`DYNAMIC_
${entityTypeId}
_STAGE_
${categoryId}
`
;
BX24
.
callMethod
(
'crm.status.list'
,
{
filter
: {
ENTITY_ID
: entityId }
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
return
;
}
var
stages = result.
data
();
console
.
log
(
'Stages:'
, stages);
}
);
$entityId
=
"DYNAMIC_
{$entityTypeId}
_STAGE_
{$categoryId}
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
$entityId
] ]
);
$stages
=
$result
[
'result'
];
As a result, we will obtain the pre-installed stages of the funnel. By default, each new funnel has five stages:
three stages "In Progress"
SEMANTICS: ""
,
one stage "Success"
SEMANTICS: "S"
,
one stage "Failure"
SEMANTIC": "F"
.
Each funnel must have at least one stage from each group. There can only be one successful stage in the funnel.
{
"result"
:
[
{
"ID"
:
"737"
,
"ENTITY_ID"
:
"DYNAMIC_177_STAGE_39"
,
"STATUS_ID"
:
"DT177_39:NEW"
,
"NAME"
:
"Start"
,
"NAME_INIT"
:
"Start"
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
"39"
,
"COLOR"
:
"#22B9FF"
,
"SEMANTICS"
:
null
}
,
{
"ID"
:
"739"
,
"ENTITY_ID"
:
"DYNAMIC_177_STAGE_39"
,
"STATUS_ID"
:
"DT177_39:PREPARATION"
,
"NAME"
:
"Preparation"
,
"NAME_INIT"
:
"Preparation"
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
"39"
,
"COLOR"
:
"#88B9FF"
,
"SEMANTICS"
:
null
}
,
{
"ID"
:
"741"
,
"ENTITY_ID"
:
"DYNAMIC_177_STAGE_39"
,
"STATUS_ID"
:
"DT177_39:CLIENT"
,
"NAME"
:
"Approval"
,
"NAME_INIT"
:
"Approval"
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
"39"
,
"COLOR"
:
"#10e5fc"
,
"SEMANTICS"
:
null
}
,
{
"ID"
:
"743"
,
"ENTITY_ID"
:
"DYNAMIC_177_STAGE_39"
,
"STATUS_ID"
:
"DT177_39:SUCCESS"
,
"NAME"
:
"Success"
,
"NAME_INIT"
:
"Success"
,
"SORT"
:
"40"
,
"SYSTEM"
:
"Y"
,
"CATEGORY_ID"
:
"39"
,
"COLOR"
:
"#00ff00"
,
"SEMANTICS"
:
"S"
}
,
{
"ID"
:
"745"
,
"ENTITY_ID"
:
"DYNAMIC_177_STAGE_39"
,
"STATUS_ID"
:
"DT177_39:FAIL"
,
"NAME"
:
"Failure"
,
"NAME_INIT"
:
"Failure"
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
"39"
,
"COLOR"
:
"#ff0000"
,
"SEMANTICS"
:
"F"
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
1751956021.475235
,
"finish"
:
1751956021.514927
,
"duration"
:
0.039691925048828125
,
"processing"
:
0.0024650096893310547
,
"date_start"
:
"2025-07-08T09:27:01+03:00"
,
"date_finish"
:
"2025-07-08T09:27:01+03:00"
,
"operating_reset_at"
:
1751956621
,
"operating"
:
0
}
}
4. Modify the Pre-installed Stage
4. Modify the Pre-installed Stage
Use the method
crm.status.update
with the parameters:
id
— the identifier of the stage from the method
crm.status.list
,
fields[name]
— the new name of the stage.
JS
PHP
BX24
.
callMethod
(
'crm.status.update'
,
{
id
: stageId,
fields
: {
NAME
:
'New Name'
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
return
;
}
console
.
log
(
'Stage updated'
);
}
);
$result
=
CRest
::
call
(
'crm.status.update'
,
[
'id'
=>
$stageId
,
'fields'
=> [
'NAME'
=>
'New Name'
,
]
]
);
As a result, we will receive
true
, indicating that the stage has been successfully modified. If you receive an
error
as a result, review the possible error descriptions in the documentation for the method
crm.status.update
.
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
1751956427.737649
,
"finish"
:
1751956427.799632
,
"duration"
:
0.06198310852050781
,
"processing"
:
0.022645950317382812
,
"date_start"
:
"2025-07-08T09:33:47+03:00"
,
"date_finish"
:
"2025-07-08T09:33:47+03:00"
,
"operating_reset_at"
:
1751957027
,
"operating"
:
0
}
}
5. Add a New Stage to the Funnel
5. Add a New Stage to the Funnel
Use the method
crm.status.add
with the
fields
parameters:
ENTITY_ID
— the identifier of the CRM directory. For smart process stages, the identifier has the format
DYNAMIC_{entityTypeId}_STAGE_{categoryId}
:
{entityTypeId}
— the numeric identifier of the smart process type from the method
crm.type.list
,
{categoryId}
— the identifier of the funnel from the method
crm.category.add
.
STATUS_ID
— the identifier of the stage. For smart process stages, the field must have the prefix
DT{entityTypeId}_{categoryId}
:
{entityTypeId}
— the numeric identifier of the smart process type from the method
crm.type.list
,
{categoryId}
— the identifier of the funnel from the method
crm.category.add
.
NAME
— the name of the stage,
SORT
— the sorting of the stage. Sorting affects the display order of the stage in the kanban. The sorting of "In Progress" stages should be the lowest, "Failure" stages the highest. The "Success" stage should have an intermediate sorting value between the sorting values of "In Progress" and "Failure" stages.
SEMANTICS
— the parameter indicating the stage's group membership. We will specify
F
to create a new stage in the "Failure" group.
JS
PHP
BX24
.
callMethod
(
'crm.status.add'
,
{
fields
: {
ENTITY_ID
: entityId,
STATUS_ID
:
`DT
${entityTypeId}
_
${categoryId}
:MY_STAGE`
,
NAME
:
'My Stage'
,
SORT
:
60
,
SEMANTICS
:
"F"
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
return
;
}
console
.
log
(
'New stage ID:'
, result.
data
());
}
);
$result
=
CRest
::
call
(
'crm.status.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
$entityId
,
'STATUS_ID'
=>
'DT'
.
$entityTypeId
.
'_'
.
$categoryId
.
':MY_STAGE'
,
'NAME'
=>
'My Stage'
,
'SORT'
=>
60
,
'SEMANTICS'
=>
'F'
,
]
]
);
$newStageId
=
$result
[
'result'
];
As a result, we will obtain the ID of the created stage.
{
"result"
:
747
,
"time"
:
{
"start"
:
1751957029.04664
,
"finish"
:
1751957029.107654
,
"duration"
:
0.06101417541503906
,
"processing"
:
0.02231001853942871
,
"date_start"
:
"2025-07-08T09:43:49+03:00"
,
"date_finish"
:
"2025-07-08T09:43:49+03:00"
,
"operating_reset_at"
:
1751957629
,
"operating"
:
0
}
}
Code Example
Code Example
In this example, we create a new funnel in a smart process, change the name of the first pre-installed stage, and add another stage to the "Failure" group. Finally, we call the method
crm.status.list
again and display a table with the groups of stages.
JS
PHP
// 1. Retrieve entityTypeId by the smart process title
BX24
.
callMethod
(
'crm.type.list'
, {
filter
: {
title
:
'Equipment Purchase'
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
return
;
var
entityTypeId = result.
data
().
types
[
0
].
entityTypeId
;
// 2. Create a new funnel
BX24
.
callMethod
(
'crm.category.add'
, {
entityTypeId
: entityTypeId,
fields
: {
name
:
'New Funnel'
,
sort
:
100
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
return
;
var
categoryId = result.
data
().
category
.
id
;
var
entityId =
`DYNAMIC_
${entityTypeId}
_STAGE_
${categoryId}
`
;
// 3. Retrieve the list of stages
BX24
.
callMethod
(
'crm.status.list'
, {
filter
: {
ENTITY_ID
: entityId
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
return
;
var
stages = result.
data
();
// 4. Modify the first stage
var
firstStageId = stages[
0
].
ID
;
BX24
.
callMethod
(
'crm.status.update'
, {
id
: firstStageId,
fields
: {
NAME
:
'First Stage'
}
},
function
(
) {
// 5. Add a new stage
BX24
.
callMethod
(
'crm.status.add'
, {
fields
: {
ENTITY_ID
: entityId,
STATUS_ID
:
`DT
${entityTypeId}
_
${categoryId}
:MY_STAGE`
,
NAME
:
'My Stage'
,
SORT
:
60
,
SEMANTICS
:
"F"
}
},
function
(
) {
// 6. Retrieve and display the final table of stages
BX24
.
callMethod
(
'crm.status.list'
, {
filter
: {
ENTITY_ID
: entityId
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
return
;
printStagesTable
(result.
data
());
});
});
});
});
});
});
function
printStagesTable
(
stages
) {
const
columns = {
'In Progress'
: [],
'Success'
: [],
'Failure'
: []
};
stages.
forEach
(
stage
=>
{
const
semantics = (stage.
EXTRA
&& stage.
EXTRA
.
SEMANTICS
) || stage.
SEMANTICS
;
if
(semantics ===
'S'
) {
columns[
'Success'
].
push
(stage.
NAME
);
}
else
if
(semantics ===
'F'
) {
columns[
'Failure'
].
push
(stage.
NAME
);
}
else
{
columns[
'In Progress'
].
push
(stage.
NAME
);
}
});
// Determine the maximum number of rows
const
maxRows =
Math
.
max
(
columns[
'In Progress'
].
length
,
columns[
'Success'
].
length
,
columns[
'Failure'
].
length
);
// Create an array of objects for console.table
const
tableData = [];
for
(
let
i =
0
; i < maxRows; i++) {
tableData.
push
({
'In Progress'
: columns[
'In Progress'
][i] ||
''
,
'Success'
: columns[
'Success'
][i] ||
''
,
'Failure'
: columns[
'Failure'
][i] ||
''
});
}
console
.
table
(tableData);
}
<?php
require_once
(
'crest.php'
);
// 1. Retrieve entityTypeId by the smart process title
$result
=
CRest
::
call
(
'crm.type.list'
,
[
'filter'
=> [
'title'
=>
'Equipment Purchase'
]
]
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
exit
;
}
$entityTypeId
=
$result
[
'result'
][
'types'
][
0
][
'entityTypeId'
];
// 2. Create a new funnel
$result
=
CRest
::
call
(
'crm.category.add'
,
[
'entityTypeId'
=>
$entityTypeId
,
'fields'
=> [
'name'
=>
'New Funnel'
,
'sort'
=>
100
]
]
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
exit
;
}
$categoryId
=
$result
[
'result'
][
'category'
][
'id'
];
$entityId
=
'DYNAMIC_'
.
$entityTypeId
.
'_STAGE_'
.
$categoryId
;
// 3. Retrieve the list of stages
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
$entityId
]
]
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
exit
;
}
$stages
=
$result
[
'result'
];
// 4. Modify the first stage
if
(!
empty
(
$stages
)) {
$firstStageId
=
$stages
[
0
][
'ID'
];
$result
=
CRest
::
call
(
'crm.status.update'
,
[
'id'
=>
$firstStageId
,
'fields'
=> [
'NAME'
=>
'First Stage'
]
]
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
exit
;
}
}
// 5. Add a new stage
$result
=
CRest
::
call
(
'crm.status.add'
,
[
'fields'
=> [
'ENTITY_ID'
=>
$entityId
,
'STATUS_ID'
=>
'DT'
.
$entityTypeId
.
'_'
.
$categoryId
.
':MY_STAGE'
,
'NAME'
=>
'My Stage'
,
'SORT'
=>
60
,
'SEMANTICS'
=>
'F'
,
]
]
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
exit
;
}
// 6. Retrieve and display the final table of stages
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
$entityId
]
]
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
exit
;
}
$stages
=
$result
[
'result'
];
// Form the stages table
$columns
= [
'In Progress'
=> [],
'Success'
=> [],
'Failure'
=> []
];
foreach
(
$stages
as
$stage
) {
$semantics
= (
$stage
[
'EXTRA'
] &&
$stage
[
'EXTRA'
][
'SEMANTICS'
]) ?
$stage
[
'EXTRA'
][
'SEMANTICS'
] :
$stage
[
'SEMANTICS'
];
if
(
$semantics
===
'S'
) {
$columns
[
'Success'
][] =
$stage
[
'NAME'
];
}
elseif
(
$semantics
===
'F'
) {
$columns
[
'Failure'
][] =
$stage
[
'NAME'
];
}
else
{
$columns
[
'In Progress'
][] =
$stage
[
'NAME'
];
}
}
// Determine the maximum number of rows
$maxRows
=
max
(
count
(
$columns
[
'In Progress'
]),
count
(
$columns
[
'Success'
]),
count
(
$columns
[
'Failure'
])
);
// Create an array of objects for output
$tableData
= [];
for
(
$i
=
0
;
$i
<
$maxRows
;
$i
++) {
$tableData
[] = [
'In Progress'
=>
$columns
[
'In Progress'
][
$i
] ??
''
,
'Success'
=>
$columns
[
'Success'
][
$i
] ??
''
,
'Failure'
=>
$columns
[
'Failure'
][
$i
] ??
''
];
}
// Output the table
echo
"Stages Table:\n"
;
foreach
(
$tableData
as
$row
) {
echo
"In Progress: "
.
$row
[
'In Progress'
] .
" | Success: "
.
$row
[
'Success'
] .
" | Failure: "
.
$row
[
'Failure'
] .
"\n"
;
}
Copied
Was the article helpful?
Yes
No
Previous
Set Up Rounding for Custom Field of Type "Number"
Next
Edit Data

---

