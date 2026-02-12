---
description: 'Document Generator API: Templates, generation, fields'
methods:
- crm.documentgenerator.
pages: 8
title: 'Document Generator API: Templates, generation, fields'
---
# Document Generator API: Templates, generation, fields
> Document Generator API: Templates, generation, fields
> **8 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [About the Document Generator](#about-the-document-generator)
- [Create a New Document Based on a Template documentgenerator.document.add](#create-a-new-document-based-on-a-template-document)
- [Update Existing Document documentgenerator.document.update](#update-existing-document-documentgeneratordocument)
- [Get Document by ID documentgenerator.document.get](#get-document-by-id-documentgeneratordocumentget)
- [Get the list of documents documentgenerator.document.list](#get-the-list-of-documents-documentgeneratordocumen)
- [Delete Document documentgenerator.document.delete](#delete-document-documentgeneratordocumentdelete)
- [Enable/Disable Public Link for Document documentgenerator.document.enablepublicurl](#enabledisable-public-link-for-document-documentgen)
- [Get a List of Document Fields documentgenerator.document.getfields](#get-a-list-of-document-fields-documentgeneratordoc)

---

## About the Document Generator

**Source:** https://apidocs.bitrix24.com/api-reference/document-generator/index

About the Document Generator | Bitrix24 REST API and Marketplace Applications
About the Document Generator
About the Document Generator
Differences in Method Parameters Across Scopes
Templates
Numbering
List of Regions
Summary
Overview of Methods and Events
Documents
Numbering
Regions
Roles
Templates
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Quick navigation:
all methods
Currently, there are
two scopes
for working with the document generator:
Methods
crm.documentgenerator.*
. The results of these methods are displayed in the CRM interface;
Methods
documentgenerator.*
. The results of these methods are only available at the REST level.
Data from one scope cannot be accessed from another:
You cannot create a CRM document with a template for REST;
You cannot use CRM data when working with methods
documentgenerator.*
.
The following
field types
and their
modifiers
are supported:
IMAGE - images;
STAMP - seals and signatures;
DATE - dates;
NAME - names.
The field types
Money
and
Address
are implemented within the
crm
module, so they cannot be used in the REST of this module. If you need to display such data, you will have to pass it in a pre-formed format.
It is possible to use arrays for insertion into tables and repeating blocks.
Differences in Method Parameters Across Scopes
Differences in Method Parameters Across Scopes
“Internally,” the methods are identical. In fact, the methods
crm.documentgenerator.*
call the methods
documentgenerator.*
after preprocessing the parameters. However, there are several differences:
For the input of methods
crm.documentgenerator.*
, you need to pass the
ID
of the CRM entity type instead of provider names (parameter
entityTypeId
);
For the input of methods
crm.documentgenerator.*
, you need to pass the parameter
entityId
instead of the
value
parameter - the
ID
of the CRM entity.
Templates
Templates
All templates and documents created by this API are tied to the REST module. You cannot access templates and documents from other modules through the
documentgenerator
scope. Therefore, the
moduleId
in the template data will always be
rest
. Even if you specify another module in
add
or
update
, it will not be changed.
Only two providers are available for REST:
Bitrix\DocumentGenerator\DataProvider\Rest
- must always be specified as the provider for the template
Bitrix\DocumentGenerator\DataProvider\HashDataProvider
- used for passing data into tables / repeating blocks
The binding of the template to the user is not considered by the REST methods. However, it can be utilized on the application side.
Numbering
Numbering
For working with numberers, there are methods
documentgenerator.numerator.*
, described
here
. It should be noted that through this scope, you can access all numberers for documents, including those that work in CRM. However, you can only update/delete the numberer that was created through REST.
List of Regions
List of Regions
Each template is tied to a specific country. The list of countries is fixed and currently consists of:
us - United States
by - Belarus
kz - Kazakhstan
ua - Ukraine
br - Brazil
mx - Mexico
de - Germany
uk - United Kingdom
pl - Poland
Starting from version documentgenerator 18.6.1, it became possible to add your own regions. A
separate section
was created for managing them.
Summary
Summary
What can be done?
Create documents based on templates in .docx file format;
Insert lists with an arbitrary number of items into the template via tables or repeating blocks;
Insert images into the template, including from lists;
Insert fields in HTML format with partial preservation of formatting;
Create documents, send them, and track views without user involvement (via Automation rules).
What cannot be done?
Insert multiple values for the file type field;
Insert tables and images from HTML;
Insert vector images;
Formatting transfer is not fully executed.
Overview of Methods and Events
Overview of Methods and Events
Documents
Documents
Method
Description
documentgenerator.document.add
Creates a new document based on a template
documentgenerator.document.delete
Deletes a document
documentgenerator.document.enablepublicurl
Enables/disables a public link to the document
documentgenerator.document.getfields
Retrieves a list of document fields
documentgenerator.document.get
Retrieves a document by its identifier
documentgenerator.document.list
Retrieves a list of documents
documentgenerator.document.update
Modifies an existing document
Numbering
Numbering
Method
Description
documentgenerator.numerator.add
Adds a numberer
documentgenerator.numerator.delete
Deletes a numberer
documentgenerator.numerator.get
Retrieves a numberer by its identifier
documentgenerator.numerator.list
Retrieves a list of numberers
documentgenerator.numerator.update
Modifies a numberer
Regions
Regions
Method
Description
documentgenerator.region.get
Returns information about a region by its identifier
documentgenerator.region.list
Returns a list of regions, both default and custom
documentgenerator.region.delete
Deletes a region
documentgenerator.region.add
Adds a new region
documentgenerator.region.update
Updates an existing country
Roles
Roles
Method
Description
documentgenerator.role.get
Provides information about a role and its access permissions
documentgenerator.role.list
Returns a list of roles without their access permissions
documentgenerator.role.delete
Deletes a role
documentgenerator.role.add
Adds a new role
documentgenerator.role.update
Updates roles
documentgenerator.role.fillaccesses
Sets a set of roles and their bindings
Templates
Templates
Method
Description
documentgenerator.template.add
Uploads a new document template
documentgenerator.template.update
Updates an existing document template
documentgenerator.template.get
Returns a document template by its identifier
documentgenerator.template.list
Returns a list of document templates by filter
documentgenerator.template.delete
Deletes a document template
documentgenerator.template.getfields
Returns a list of document template fields
Copied
Was the article helpful?
Yes
No
Previous
Enable Debug Mode
Next
Generating a simple document

---

## Create a New Document Based on a Template documentgenerator.document.add

**Source:** https://apidocs.bitrix24.com/api-reference/document-generator/document-generator-document-add

Create a New Document Based on a Template documentgenerator.document.add | Bitrix24 REST API and Marketplace Applications
Create a New Document Based on a Template documentgenerator.document.add
Create a New Document Based on a Template documentgenerator.document.add
Examples
Response on Success
Why is there no link to the PDF in the result of document.add
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
documentgenerator
Who can execute the method: any user
The method
documentgenerator.document.add
creates a new document based on a template.
Parameter
Description
templateId
Template ID.
value
External identifier. The value parameter is needed only for the application interface, as an identifier for the external source. This is a string parameter, and you can pass a complete external code into it. For example,
"PARTNER_APP_10_BILL_133”
.
values
A set of field values for the document. In a simple case, this is a one-dimensional array where the key is the field name and the value is the string to be inserted into the document.
stampsEnabled
1 (enable), 0 (disable) stamps and signatures.
fields
Description of the document fields. This parameter is an array where the key is the field name and the value is the description. Codes for simple field types:
TYPE — field type;
FORMAT — format;
PROVIDER — provider;
TITLE — title;
IMAGE — image;
STAMP — stamp/signature;
DATE — date/time;
NAME — name;
PHONE — phone number.
Examples
Examples
You can view
examples of document generation
here.
Response on Success
Response on Success
In case of successful execution, the result will return a structure similar to the method
documentgenerator.document.get()
for the new document.
Why is there no link to the PDF in the result of document.add
Why is there no link to the PDF in the result of document.add
The conversion to
pdf
is an asynchronous operation. At the time the document generation is completed, the pdf file is not yet available.
If a pdf is urgently needed for the document, the only option right now is to make a repeated request to
documentgenerator.document.get
after 20-30 seconds to retrieve the link to the pdf. If it does not appear there, try again.
Copied
Was the article helpful?
Yes
No
Previous
Generating a document with complex tables
Next
Modify an Existing Document

---

## Update Existing Document documentgenerator.document.update

**Source:** https://apidocs.bitrix24.com/api-reference/document-generator/document-generator-document-update

Update Existing Document documentgenerator.document.update | Bitrix24 REST API and Marketplace Applications
Update Existing Document documentgenerator.document.update
Update Existing Document documentgenerator.document.update
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
documentgenerator
Who can execute the method: any user
The method
documentgenerator.document.update
updates an existing document with new values. Please note that updating a document on a remote template is not possible. It works similarly to
documentgenerator.document.add()
.
Parameter
Description
id
Document identifier.
values
Array of new field values for the document.
stampsEnabled
1 (enable), 0 (disable) stamps and signatures.
fields
Field settings.
Copied
Was the article helpful?
Yes
No
Previous
Create a New Document
Next
Retrieve a Document by ID

---

## Get Document by ID documentgenerator.document.get

**Source:** https://apidocs.bitrix24.com/api-reference/document-generator/document-generator-document-get

Get Document by ID documentgenerator.document.get | Bitrix24 REST API and Marketplace Applications
Get Document by ID documentgenerator.document.get
Get Document by ID documentgenerator.document.get
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
documentgenerator
Who can execute the method: any user
The method
documentgenerator.document.get
returns information about a document by its ID.
Parameter
Description
id
Document ID.
Successful Response
Successful Response
200 OK
"document"
:
{
"id"
:
1929
,
// document id
"title"
:
"Rest Template 1"
,
// title
"number"
:
"1"
,
// number
"createTime"
:
"2018-06-05T16:04:40+02:00"
,
// creation date
"updateTime"
:
"2018-06-05T16:04:40+02:00"
,
// modification date
"createdBy"
:
"1"
,
// user id of the document creator
"updatedBy"
:
"1"
,
// user id of the document updater
"stampsEnabled"
:
true
,
// whether stamps and signatures are included
"downloadUrl"
:
""
,
// link for the user to download the docx file
"downloadUrlMachine"
:
""
,
// link for the application to download the docx file
"imageUrl"
:
""
,
// link for the user to download the image
"imageUrlMachine"
:
""
,
// link for the application to download the image
"pdfUrl"
:
""
,
// link for the user to download the pdf
"pdfUrlMachine"
:
""
,
// link for the application to download the pdf
"publicUrl"
:
""
,
// public link (if available)
"isTransformationError"
:
false
,
// whether there was a conversion error
"templateId"
:
"202"
,
// template id
"provider"
:
"Bitrix\\DocumentGenerator\\DataProvider\\Rest"
,
// provider code
"value"
:
"1"
,
// external identifier
"values"
:
{
// field values
"SomeDate"
:
"2018-02-21T16:33:00+03:00"
}
}
Copied
Was the article helpful?
Yes
No
Previous
Modify an Existing Document
Next
Get a List of Documents

---

## Get the list of documents documentgenerator.document.list

**Source:** https://apidocs.bitrix24.com/api-reference/document-generator/document-generator-document-list

Get the list of documents documentgenerator.document.list | Bitrix24 REST API and Marketplace Applications
Get the list of documents documentgenerator.document.list
Get the list of documents documentgenerator.document.list
Example of a filter
Response in case of success
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
documentgenerator
Who can execute the method: any user
The method
documentgenerator.document.list
returns a list of documents based on the filter.
Parameter
Description
select
Array of fields to output.
order
Array to specify the output order
{"id": "desc"}
.
filter
Array for filtering.
start
The ordinal number of the list item from which to return the next items when calling the current method. Details in the article
Features of List Methods
Example of a filter
Example of a filter
"filter"
:
{
"value"
:
5
}
As a result, a list of documents will be generated for the external identifier = 5.
Response in case of success
Response in case of success
200 OK
"documents"
:
[
{
"id"
:
1929
,
// document id
"title"
:
"Rest Template 1"
,
// title
"number"
:
"1"
,
// number
"createTime"
:
"2018-06-05T16:04:40+02:00"
,
// creation date
"updateTime"
:
"2018-06-05T16:04:40+02:00"
,
// modification date
"stampsEnabled"
:
true
,
// whether stamps and signatures are inserted
"downloadUrl"
:
""
,
// link for the user to download the docx file
"downloadUrlMachine"
:
""
,
// link for the application to download the docx file
"imageUrl"
:
""
,
// link for the user to download the image
"imageUrlMachine"
:
""
,
// link for the application to download the image
"pdfUrl"
:
""
,
// link for the user to download the pdf
"pdfUrlMachine"
:
""
,
// link for the application to download the pdf
"publicUrl"
:
""
,
// public link (if available)
"isTransformationError"
:
false
,
// whether there was a conversion error
"templateId"
:
"202"
,
// template id
"provider"
:
"Bitrix\\DocumentGenerator\\DataProvider\\Rest"
,
// provider code
"value"
:
"1"
,
// external identifier
"values"
:
{
// field values
"SomeDate"
:
"2018-02-21T16:33:00+03:00"
}
}
]
Copied
Was the article helpful?
Yes
No
Previous
Retrieve a Document by ID
Next
Delete a Document

---

## Delete Document documentgenerator.document.delete

**Source:** https://apidocs.bitrix24.com/api-reference/document-generator/document-generator-document-delete

Delete Document documentgenerator.document.delete | Bitrix24 REST API and Marketplace Applications
Delete Document documentgenerator.document.delete
Delete Document documentgenerator.document.delete
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
documentgenerator
Who can execute the method: any user
The method
documentgenerator.document.delete
removes a document.
Parameter
Description
id
Document identifier.
Success Response
Success Response
The response is empty.
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Documents
Next
Enable/Disable Public Link for Document

---

## Enable/Disable Public Link for Document documentgenerator.document.enablepublicurl

**Source:** https://apidocs.bitrix24.com/api-reference/document-generator/document-generator-document-enable-public-url

Enable/Disable Public Link for Document documentgenerator.document.enablepublicurl | Bitrix24 REST API and Marketplace Applications
Enable/Disable Public Link for Document documentgenerator.document.enablepublicurl
Enable/Disable Public Link for Document documentgenerator.document.enablepublicurl
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
documentgenerator
Who can execute the method: any user
The method
documentgenerator.document.enablepublicurl
enables/disables the public link for the document.
Parameter
Description
id
Document identifier.
status
1 (enable), 0 (disable) the public link for the document.
Success Response
Success Response
200 OK
"publicUrl"
:
""
// public link
Copied
Was the article helpful?
Yes
No
Previous
Delete a Document
Next
Get a List of Document Fields

---

## Get a List of Document Fields documentgenerator.document.getfields

**Source:** https://apidocs.bitrix24.com/api-reference/document-generator/document-generator-document-get-fields

Get a List of Document Fields documentgenerator.document.getfields | Bitrix24 REST API and Marketplace Applications
Get a List of Document Fields documentgenerator.document.getfields
Get a List of Document Fields documentgenerator.document.getfields
We are still updating this page
Some data may be missing here — we will add it soon.
Scope:
documentgenerator
Who can execute the method: any user
The method
documentgenerator.document.getfields
returns a list of document fields along with their descriptions. The returned values are exactly the same as those from the method
documentgenerator.template.getfields()
.
Copied
Was the article helpful?
Yes
No
Previous
Enable/Disable Public Link for Document
Next
Overview of Methods

---

