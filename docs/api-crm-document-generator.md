---
description: 'CRM Document Generator: Templates, documents, fields'
methods:
- crm.documentgenerator
- crm.documentgenerator.document.add
- crm.documentgenerator.document.delete
- crm.documentgenerator.document.enablepublicurl
- crm.documentgenerator.document.get
- crm.documentgenerator.document.getfields
- crm.documentgenerator.document.list
- crm.documentgenerator.document.update
- crm.documentgenerator.document.upload
- crm.documentgenerator.numerator.add
- crm.documentgenerator.numerator.delete
- crm.documentgenerator.numerator.get
- crm.documentgenerator.numerator.list
- crm.documentgenerator.numerator.update
- crm.documentgenerator.template.add
- crm.documentgenerator.template.delete
- crm.documentgenerator.template.get
- crm.documentgenerator.template.getfields
- crm.documentgenerator.template.list
- crm.documentgenerator.template.update
- event.bind
pages: 27
title: 'CRM Document Generator: Templates, documents, fields'
---
# CRM Document Generator: Templates, documents, fields
> CRM Document Generator: Templates, documents, fields
> **27 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Document Generator](#document-generator)
- [Documents](#documents)
- [Get Document Fields crm.documentgenerator.document.getfields](#get-document-fields-crmdocumentgeneratordocumentge)
- [Create a new document crm.documentgenerator.document.add](#create-a-new-document-crmdocumentgeneratordocument)
- [Update Document crm.documentgenerator.document.update](#update-document-crmdocumentgeneratordocumentupdate)
- [Get Document Information by Id crm.documentgenerator.document.get](#get-document-information-by-id-crmdocumentgenerato)
- [Get the list of documents crm.documentgenerator.document.list](#get-the-list-of-documents-crmdocumentgeneratordocu)
- [Enable and Disable Public Link for Document crm.documentgenerator.document.enablepublicurl](#enable-and-disable-public-link-for-document-crmdoc)
- [Upload the generated document and attach it to the specified entity crm.documentgenerator.document.upload](#upload-the-generated-document-and-attach-it-to-the)
- [Delete Document crm.documentgenerator.document.delete](#delete-document-crmdocumentgeneratordocumentdelete)
- [Overview of Events When Working with Documents](#overview-of-events-when-working-with-documents)
- [Event when creating a document onCrmDocumentGeneratorDocumentAdd](#event-when-creating-a-document-oncrmdocumentgenera)
- [Event on Document Update <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-6yq53af2">onCrmDocumentGeneratorDocumentUpdate</code>](#event-on-document-update-code-classyfm-clipboard-i)
- [Event on Document Deletion <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-izdewnfc">onCrmDocumentGeneratorDocumentDelete</code>](#event-on-document-deletion-code-classyfm-clipboard)
- [Document Templates](#document-templates)
- [Get Document Template Fields crm.documentgenerator.template.getfields](#get-document-template-fields-crmdocumentgeneratort)
- [Add a New Template crm.documentgenerator.template.add](#add-a-new-template-crmdocumentgeneratortemplateadd)
- [Update Existing Document Template crm.documentgenerator.template.update](#update-existing-document-template-crmdocumentgener)
- [Get Document Template Information by Id crm.documentgenerator.template.get](#get-document-template-information-by-id-crmdocumen)
- [Get a list of document templates crm.documentgenerator.template.list](#get-a-list-of-document-templates-crmdocumentgenera)
- [Delete Document Template crm.documentgenerator.template.delete](#delete-document-template-crmdocumentgeneratortempl)
- [Numberers](#numberers)
- [Add a new numerator crm.documentgenerator.numerator.add](#add-a-new-numerator-crmdocumentgeneratornumeratora)
- [Update Existing Numbering crm.documentgenerator.numerator.update](#update-existing-numbering-crmdocumentgeneratornume)
- [Get Information About the Numerator by Id crm.documentgenerator.numerator.get](#get-information-about-the-numerator-by-id-crmdocum)
- [Get the list of numerators crm.documentgenerator.numerator.list](#get-the-list-of-numerators-crmdocumentgeneratornum)
- [Delete crm.documentgenerator.numerator.delete](#delete-crmdocumentgeneratornumeratordelete)

---

## Document Generator

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/index

Document Generator | Bitrix24 REST API and Marketplace Applications
Document Generator
Document Generator
Features of Passed Values
Providers
Filtering by Deal Directions
List of Regions
Overview of Methods
Documents
Numerator
Document Templates
We are still updating this page
Some data may be missing — we will complete it soon.
Permissions
Scope
:
crm.documentgenerator
|
Who can execute the method
:
any user
Quick navigation:
all methods
The CRM REST methods for documents are implemented through AJAX controllers. The controllers and their actions are implemented in the
Document Generator
module, while the CRM module only provides the wrapper for them. This wrapper transforms the input and output parameters according to the new REST standard, taking into account the specifics of the CRM module.
When working with document methods through the CRM scope, you can only work with templates/documents linked to the CRM module.
Features of Passed Values
Features of Passed Values
Providers
Providers
The
Document Generator
module uses the full class name as the data provider identifier. Since the CRM module uses named/numeric identifiers to identify entities, a similar syntax was used in REST for documents. If the input parameter is called
entityTypeId
, it accepts the numeric index of CRM entities. Currently, the following identifiers are available:
1 - lead
2 - deal
3 - contact
4 - company
5 - invoice
7 - estimate
14 - order
31 - new invoices
It is also possible to use SPAs: their
entityTypeId
is also supported in the Document Generator.
Filtering by Deal Directions
Filtering by Deal Directions
REST methods do not consider the template binding to providers. That is, if a request is sent to generate a document based on a template with a provider to which this template is not linked, there will be no error. It follows that the binding of the template to a specific deal direction is not taken into account. If you want to specify a deal as a provider, only the numeric identifier (2) is indicated.
List of Regions
List of Regions
Each template is linked to a specific country. The list of countries is fixed and currently consists of:
de - Germany
by - Belarus
kz - Kazakhstan
ua - Ukraine
br - Brazil
mx - Mexico
uk - United Kingdom
pl - Poland
Region management is carried out in the
documentgenerator
section.
Overview of Methods
Overview of Methods
Documents
Documents
Method
Description
crm.documentgenerator.document.getfields
Document fields.
crm.documentgenerator.document.add
Create a new document.
crm.documentgenerator.document.update
Modify a document.
crm.documentgenerator.document.get
Retrieve information about a document by Id.
crm.documentgenerator.document.list
Get a list of documents.
crm.documentgenerator.document.enablepublicurl
Enable and disable public link to the document.
crm.documentgenerator.document.upload
Upload the generated document and attach it to the specified entity.
crm.documentgenerator.document.delete
Delete a document.
Numerator
Numerator
Method
Description
crm.documentgenerator.numerator.add
Add a new numerator.
crm.documentgenerator.numerator.update
Modify an existing numerator.
crm.documentgenerator.numerator.get
Retrieve information about a numerator by Id.
crm.documentgenerator.numerator.list
Get a list of numerators.
crm.documentgenerator.numerator.delete
Delete a numerator.
Document Templates
Document Templates
Method
Description
crm.documentgenerator.template.getfields
Document template fields.
crm.documentgenerator.template.add
Add a new template.
crm.documentgenerator.template.update
Modify an existing document template.
crm.documentgenerator.template.get
Retrieve information about a document template by Id.
crm.documentgenerator.template.list
Get a list of document templates.
crm.documentgenerator.template.delete
Delete a document template.
Copied
Was the article helpful?
Yes
No
Previous
When deleting currency
Next
Overview of methods

---

## Documents

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/index

Documents | Bitrix24 REST API and Marketplace Applications
Documents
Documents
We are still updating this page
Some data may be missing here — we will complete it shortly.
Permissions
Scope
:
crm.documentgenerator
|
Who can execute the method
:
any user
Method
Description
crm.documentgenerator.document.getfields
Document fields.
crm.documentgenerator.document.add
Creating a new document.
crm.documentgenerator.document.update
Modifying a document.
crm.documentgenerator.document.get
Retrieving information about a document by Id.
crm.documentgenerator.document.list
Getting a list of documents.
crm.documentgenerator.document.enablepublicurl
Enabling and disabling a public link to the document.
crm.documentgenerator.document.upload
Uploading the generated document and attaching it to the specified entity.
crm.documentgenerator.document.delete
Deleting a document.
Copied
Was the article helpful?
Yes
No
Previous
Document Generator
Next
Get document fields

---

## Get Document Fields crm.documentgenerator.document.getfields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/crm-document-generator-document-get-fields

Get Document Fields crm.documentgenerator.document.getfields | Bitrix24 REST API and Marketplace Applications
Successful Response
Get Document Fields crm.documentgenerator.document.getfields
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.document.getfields
returns a list of document fields along with their descriptions.
Successful Response
Successful Response
The return values are exactly the same as those of the method
crm.documentgenerator.template.getfields()
.
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Create a new document

---

## Create a new document crm.documentgenerator.document.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/crm-document-generator-document-add

Create a new document crm.documentgenerator.document.add | Bitrix24 REST API and Marketplace Applications
Create a new document crm.documentgenerator.document.add
Create a new document crm.documentgenerator.document.add
Response in case of success
Why there is no link to pdf in the result of crm.documentgenerator.document.add
See also
Continue your study
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.document.add
creates a new document based on a template and data from the corresponding entity. In
values
, you can pass an array of additional field values.
Parameter
Description
templateId
Template ID.
entityTypeId
CRM entity type ID.
entityId
Entity ID.
values
Additional field values.
stampsEnabled
1 (enable), 0 (disable) stamps and signatures.
Response in case of success
Response in case of success
In case of successful execution, the response will be a structure similar to the method
crm.documentgenerator.document.get()
for the new document.
Why there is no link to pdf in the result of crm.documentgenerator.document.add
Why there is no link to
pdf
in the result of
crm.documentgenerator.document.add
Conversion to
pdf
is an asynchronous operation. At the time the document generation is completed, the
pdf
file is not yet available. The minimum conversion time is 8 seconds.
If a
pdf
is urgently needed for the document, the only option right now is to make a repeated request to
crm.documentgenerator.document.get
after 20-30 seconds to retrieve the link to the
pdf
. If it hasn't appeared, try again.
See also
See also
Document generation examples
Presentation on the document generator
Document templates
Continue your study
Continue your study
How to Add a Template and Create a Document Based on It
Copied
Was the article helpful?
Yes
No
Previous
Get document fields
Next
Update document

---

## Update Document crm.documentgenerator.document.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/crm-document-generator-document-update

Update Document crm.documentgenerator.document.update | Bitrix24 REST API and Marketplace Applications
Update Document crm.documentgenerator.document.update
Update Document crm.documentgenerator.document.update
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.document.update
updates an existing document with new values. It is important to remember that updating a document based on a remote template is not possible. The method works similarly to
crm.documentgenerator.document.add()
.
Parameter
Description
id
Document identifier.
values
Array of new field values for the document.
stampsEnabled
1 (enable), 0 (disable) stamps and signatures.
Copied
Was the article helpful?
Yes
No
Previous
Create a new document
Next
Get document information by Id

---

## Get Document Information by Id crm.documentgenerator.document.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/crm-document-generator-document-get

Get Document Information by Id crm.documentgenerator.document.get | Bitrix24 REST API and Marketplace Applications
Get Document Information by Id crm.documentgenerator.document.get
Get Document Information by Id crm.documentgenerator.document.get
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.document.get
returns information about a document by its identifier.
Parameter
Description
id
*
Document ID.
Required parameters are marked with *
Why there is no link to pdf in the result of crm.documentgenerator.document.add
Why there is no link to
pdf
in the result of
crm.documentgenerator.document.add
Conversion to
pdf
is an asynchronous operation. At the time the document generation is completed, the
pdf
file is not yet available. The minimum conversion time is 8 seconds.
If a
pdf
is urgently needed for the document, the only option right now is to make a repeated request to
crm.documentgenerator.document.get
after 20-30 seconds to retrieve the link to the
pdf
. If it hasn't appeared, try again.
Response in case of success
Response in case of success
"document"
:
{
"id"
:
1
,
"title"
:
"Invoice (USA) 1"
,
"number"
:
"1"
,
"createTime"
:
"2018-06-05T16:04:40+02:00"
,
"updateTime"
:
"2018-06-05T16:04:40+02:00"
,
"createdBy"
:
"1"
,
"updatedBy"
:
"1"
,
"stampsEnabled"
:
true
,
"downloadUrl"
:
""
,
"downloadUrlMachine"
:
""
,
"imageUrl"
:
""
,
"imageUrlMachine"
:
""
,
"pdfUrl"
:
""
,
"pdfUrlMachine"
:
""
,
"publicUrl"
:
""
,
"isTransformationError"
:
false
,
"templateId"
:
"1"
,
"entityTypeId"
:
1
,
"entityId"
:
"1"
,
"values"
:
{
}
}
Copied
Was the article helpful?
Yes
No
Previous
Update document
Next
Get list of documents

---

## Get the list of documents crm.documentgenerator.document.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/crm-document-generator-document-list

Get the list of documents crm.documentgenerator.document.list | Bitrix24 REST API and Marketplace Applications
Get the list of documents crm.documentgenerator.document.list
Get the list of documents crm.documentgenerator.document.list
Example of a filter
Response in case of success
We are still updating this page
Some data may be missing — we will complete it soon.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.document.list
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
Offset for pagination.
Example of a filter
Example of a filter
"filter"
:
{
"entityTypeId"
:
2
,
"entityId"
:
5
}
As a result, a list of documents will be generated for the deal with ID=5.
Response in case of success
Response in case of success
"documents"
:
[
{
"id"
:
"1523"
,
"title"
:
"Act (USA) 1"
,
"number"
:
"1"
,
"templateId"
:
"115"
,
"entityTypeId"
:
"2"
,
"fileId"
:
"4315"
,
"imageId"
:
"4316"
,
"pdfId"
:
"4317"
,
"createTime"
:
"2018-06-05T16:04:40+02:00"
,
"updateTime"
:
"2018-06-05T16:04:40+02:00"
,
"values"
:
{
}
,
"entityId"
:
"5"
,
"downloadUrl"
:
""
,
"downloadUrlMachine"
:
""
,
"imageUrl"
:
""
,
"imageUrlMachine"
:
""
,
"pdfUrl"
:
""
,
"pdfUrlMachine"
:
""
}
]
Copied
Was the article helpful?
Yes
No
Previous
Get document information by Id
Next
Enable and disable public link to document

---

## Enable and Disable Public Link for Document crm.documentgenerator.document.enablepublicurl

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/crm-document-generator-document-enable-public-url

Enable and Disable Public Link for Document crm.documentgenerator.document.enablepublicurl | Bitrix24 REST API and Marketplace Applications
Enable and Disable Public Link for Document crm.documentgenerator.document.enablepublicurl
Enable and Disable Public Link for Document crm.documentgenerator.document.enablepublicurl
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.document.enablepublicurl
enables/disables the public link for the document.
Parameter
Description
id
Document identifier.
status
1 (enable), 0 (disable) the public link for the document.
Copied
Was the article helpful?
Yes
No
Previous
Get list of documents
Next
Upload generated document and attach it to specified entity

---

## Upload the generated document and attach it to the specified entity crm.documentgenerator.document.upload

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/crm-document-generator-document-upload

Upload the generated document and attach it to the specified entity crm.documentgenerator.document.upload | Bitrix24 REST API and Marketplace Applications
Upload the generated document and attach it to the specified entity crm.documentgenerator.document.upload
Upload the generated document and attach it to the specified entity crm.documentgenerator.document.upload
We are still updating this page
Some data may be missing — we will complete it soon
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.document.upload
uploads a generated document and attaches it to the specified entity. During the upload process, a hidden template is created, linked to the current REST application (one template per application). An empty file is attached to this template (since a template cannot exist without a file).
Parameter
Description
fileContent
Content of the docx file in
base64
.
region
Country.
entityTypeId
ID of the CRM entity type.
entityId
ID of the CRM entity.
title
Document title.
number
Document number.
pdfContent
Content of the pdf file in
base64
, optional.
imageContent
Content of the image in
base64
, optional.
Response in case of success
Response in case of success
The method returns values similar to
crm.documentgenerator.document.add
.
Copied
Was the article helpful?
Yes
No
Previous
Enable and disable public link to document
Next
Delete document

---

## Delete Document crm.documentgenerator.document.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/crm-document-generator-document-delete

Delete Document crm.documentgenerator.document.delete | Bitrix24 REST API and Marketplace Applications
Delete Document crm.documentgenerator.document.delete
Delete Document crm.documentgenerator.document.delete
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.document.delete
removes a document.
Parameter
Description
id
*
Document identifier.
Required parameters are marked with *
Response on Success
Response on Success
The response is empty.
Copied
Was the article helpful?
Yes
No
Previous
Upload generated document and attach it to specified entity
Next
Overview of Events

---

## Overview of Events When Working with Documents

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/events/index

Overview of Events When Working with Documents | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Documents
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, updating, or deletion of documents.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to document events through:
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
documentgenerator, crm
Who can subscribe: any user
Event
Triggered By
onCrmDocumentGeneratorDocumentAdd
When a document is generated manually or by the method
crm.documentgenerator.document.add
onCrmDocumentGeneratorDocumentUpdate
When a document is modified or by the method
crm.documentgenerator.document.update
onCrmDocumentGeneratorDocumentDelete
When a document is deleted or by the method
crm.documentgenerator.document.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete document
Next
When Generating a Document

---

## Event when creating a document onCrmDocumentGeneratorDocumentAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/events/on-crm-document-generator-document-add

Event when creating a document onCrmDocumentGeneratorDocumentAdd | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event when creating a document onCrmDocumentGeneratorDocumentAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
documentgenerator, crm
Who can subscribe: any user
The event
ONCRMDOCUMENTGENERATORDOCUMENTADD
will trigger when a new document is created.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMDOCUMENTGENERATORDOCUMENTADD"
,
"event_handler_id"
:
"821"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"1869"
,
"ENTITY_TYPE_ID"
:
"1"
,
"ENTITY_ID"
:
"1000993"
}
}
,
"ts"
:
"1749042094"
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
"crm, documentgenerator"
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
ONCRMDOCUMENTGENERATORDOCUMENTADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the created document.
Contains the key
FIELDS
data.FIELDS
object
Object containing information about the fields of the created document.
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
Identifier of the created document
ENTITY_TYPE_ID
integer
Identifier of the
object type
to which the document belongs, for example
1
— lead
ENTITY_ID
integer
Identifier of the entity to which the document is linked
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
Event on Document Update `onCrmDocumentGeneratorDocumentUpdate`
Event on Document Deletion `onCrmDocumentGeneratorDocumentDelete`
Copied
Was the article helpful?
Yes
No
Previous
Overview of Events
Next
When Modifying a Document

---

## Event on Document Update <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-6yq53af2">onCrmDocumentGeneratorDocumentUpdate</code>

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/events/on-crm-document-generator-document-update

Event on Document Update <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-6yq53af2">onCrmDocumentGeneratorDocumentUpdate</code> | Bitrix24 REST API and Marketplace Applications
Event on Document Update <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-6yq53af2">onCrmDocumentGeneratorDocumentUpdate</code>
Event on Document Update
onCrmDocumentGeneratorDocumentUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
documentgenerator, crm
Who can subscribe: any user
The event
ONCRMDOCUMENTGENERATORDOCUMENTUPDATE
will trigger when an existing document is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is sent as a POST request
{
"event"
:
"ONCRMDOCUMENTGENERATORDOCUMENTUPDATE"
,
"event_handler_id"
:
"823"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"1869"
,
"ENTITY_TYPE_ID"
:
"1"
,
"ENTITY_ID"
:
"1000993"
}
}
,
"ts"
:
"1749042219"
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
"crm, documentgenerator"
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
Symbolic event code.
In this case —
ONCRMDOCUMENTGENERATORDOCUMENTUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated document.
Contains the key
FIELDS
data.FIELDS
object
Object containing information about the fields of the updated document.
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
Identifier of the updated document
ENTITY_TYPE_ID
integer
Identifier of the
object type
to which the document belongs, for example
1
— lead
ENTITY_ID
integer
Identifier of the entity to which the document is linked
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
Event when creating a document onCrmDocumentGeneratorDocumentAdd
Event on Document Deletion `onCrmDocumentGeneratorDocumentDelete`
Copied
Was the article helpful?
Yes
No
Previous
When Generating a Document
Next
When Deleting a Document

---

## Event on Document Deletion <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-izdewnfc">onCrmDocumentGeneratorDocumentDelete</code>

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/documents/events/on-crm-document-generator-document-delete

Event on Document Deletion <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-izdewnfc">onCrmDocumentGeneratorDocumentDelete</code> | Bitrix24 REST API and Marketplace Applications
Event on Document Deletion <code class="yfm-clipboard-inline-code" role="button" aria-label="Code block" aria-description="To copy the text inside the block, click on the block" tabindex='0' id="inline-code-id-izdewnfc">onCrmDocumentGeneratorDocumentDelete</code>
Event on Document Deletion
onCrmDocumentGeneratorDocumentDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
documentgenerator, crm
Who can subscribe: any user
The event
ONCRMDOCUMENTGENERATORDOCUMENTDELETE
will trigger upon the deletion of a document.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMDOCUMENTGENERATORDOCUMENTDELETE"
,
"event_handler_id"
:
"825"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"1869"
,
"ENTITY_TYPE_ID"
:
"1"
,
"ENTITY_ID"
:
"1000993"
}
}
,
"ts"
:
"1749042237"
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
"crm, documentgenerator"
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
ONCRMDOCUMENTGENERATORDOCUMENTDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted document.
Contains the key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted document.
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
Identifier of the deleted document
ENTITY_TYPE_ID
integer
Identifier of the
object type
to which the document belonged, for example
1
— lead
ENTITY_ID
integer
Identifier of the entity to which the document was attached
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
Event when creating a document onCrmDocumentGeneratorDocumentAdd
Event on Document Update `onCrmDocumentGeneratorDocumentUpdate`
Copied
Was the article helpful?
Yes
No
Previous
When Modifying a Document
Next
Overview of Methods

---

## Document Templates

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/templates/index

Document Templates | Bitrix24 REST API and Marketplace Applications
Document Templates
Document Templates
We are still updating this page
Some data may be missing here — we will complete it shortly.
Permissions
Scope
:
crm.documentgenerator
|
Who can execute the method
:
any user
Method
Description
crm.documentgenerator.template.getfields
Document template fields.
crm.documentgenerator.template.add
Adding a new template.
crm.documentgenerator.template.update
Modifying an existing document template.
crm.documentgenerator.template.get
Retrieving information about a document template by Id.
crm.documentgenerator.template.list
Getting a list of document templates.
crm.documentgenerator.template.delete
Deleting a document template.
Copied
Was the article helpful?
Yes
No
Previous
When Deleting a Document
Next
Retrieve Document Template Fields

---

## Get Document Template Fields crm.documentgenerator.template.getfields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/templates/crm-document-generator-template-get-fields

Get Document Template Fields crm.documentgenerator.template.getfields | Bitrix24 REST API and Marketplace Applications
Get Document Template Fields crm.documentgenerator.template.getfields
Get Document Template Fields crm.documentgenerator.template.getfields
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.template.getfields
returns a list of template fields along with their descriptions.
Parameter
Description
id
Template ID.
entityTypeId
CRM entity type ID.
entityId
ID of the entity being used.
values
Array of additional values.
Response on Success
Response on Success
"templateFields"
:
{
"DocumentNumber"
:
{
"title"
:
"Number"
,
"value"
:
"22"
,
"group"
:
[
"Document"
]
,
"default"
:
"22"
}
,
"MyCompanyUfLogo"
:
{
"title"
:
"Logo"
,
"value"
:
""
,
"type"
:
"IMAGE"
,
"group"
:
[
"Document"
,
"My Company"
]
,
"default"
:
""
}
,
"MY_COMPANY"
:
{
"title"
:
"My Company"
,
"value"
:
[
{
"value"
:
"6"
,
"title"
:
"1C-Bitrix"
,
"selected"
:
"1"
}
,
{
"value"
:
"11"
,
"title"
:
"Kopytov LLC"
,
"selected"
:
" "
}
]
,
"group"
:
[
"Document"
,
"My Company"
]
}
}
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Add New Template

---

## Add a New Template crm.documentgenerator.template.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/templates/crm-document-generator-template-add

Add a New Template crm.documentgenerator.template.add | Bitrix24 REST API and Marketplace Applications
Add a New Template crm.documentgenerator.template.add
Add a New Template crm.documentgenerator.template.add
Parameter fields
Continue Exploring
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.template.add
adds a new template. It returns the same data as calling
crm.documentgenerator.template.get()
on the new template.
Parameter
Description
fields
Array of template fields.
Parameter fields
Parameter fields
Parameter
Description
name
*
Template name.
file
*
File content encoded in
base64
. Alternatively, the file content can be sent in
multipart/form-data
. In this case, it should not be encoded in
base64
.
numeratorId
*
Identifier of the numerator.
region
*
Country.
entityTypeId
*
Array of identifiers of linked entities. The deal code must be passed here, considering filtering by directions.
users
Array of access permissions.
active
Y/N active flag.
withStamps
Y/N to apply stamps and signatures.
sort
Sort index.
Required parameters are marked with *
Continue Exploring
Continue Exploring
How to Add a Template and Create a Document Based on It
Copied
Was the article helpful?
Yes
No
Previous
Retrieve Document Template Fields
Next
Modify Existing Document Template

---

## Update Existing Document Template crm.documentgenerator.template.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/templates/crm-document-generator-template-update

Update Existing Document Template crm.documentgenerator.template.update | Bitrix24 REST API and Marketplace Applications
Update Existing Document Template crm.documentgenerator.template.update
Update Existing Document Template crm.documentgenerator.template.update
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.template.update
updates an existing template. It returns the same data as when calling
crm.documentgenerator.template.get()
.
Parameter
Description
id
Template identifier.
fields
Array of fields. Similar to the method
crm.documentgenerator.template.add
, but here all fields are optional.
Copied
Was the article helpful?
Yes
No
Previous
Add New Template
Next
Get Document Template Information by Id

---

## Get Document Template Information by Id crm.documentgenerator.template.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/templates/crm-document-generator-template-get

Get Document Template Information by Id crm.documentgenerator.template.get | Bitrix24 REST API and Marketplace Applications
Get Document Template Information by Id crm.documentgenerator.template.get
Get Document Template Information by Id crm.documentgenerator.template.get
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.template.get
returns information about a template by its identifier.
Parameter
Description
id
*
Template ID.
Required parameters are marked with *
Successful Response
Successful Response
"template"
:
{
"id"
:
1
,
// template id
"name"
:
"Invoice (USA)"
,
// name
"region"
:
"com"
,
// country
"code"
:
"INVOICE_US"
,
// code
"download"
:
''
,
// download link for the user
"downloadMachine"
:
''
,
// download link for the application
"active"
:
"Y"
,
// active status
"moduleId"
:
"crm"
,
// module id
"numeratorId"
:
1
,
// numerator id
"withStamps"
:
"Y"
,
// apply stamps by default
"isDeleted"
:
"N"
,
// deleted or not
"entityTypeId"
:
[
// linked entities
"0"
:
"4"
,
"1"
:
"3"
,
"2"
:
"2_category_0"
,
"3"
:
"2_category_1"
,
"4"
:
"5"
,
"5"
:
"1"
,
"6"
:
"14"
,
"7"
:
"7"
]
,
"users"
:
[
// linked users
"0"
:
"UA"
]
,
"sort"
:
500
// sort index
}
Copied
Was the article helpful?
Yes
No
Previous
Modify Existing Document Template
Next
Retrieve List of Document Templates

---

## Get a list of document templates crm.documentgenerator.template.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/templates/crm-document-generator-template-list

Get a list of document templates crm.documentgenerator.template.list | Bitrix24 REST API and Marketplace Applications
Get a list of document templates crm.documentgenerator.template.list
Get a list of document templates crm.documentgenerator.template.list
Filter Examples
Response on Success
We are still updating this page
Some data may be missing — we will complete it soon.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.template.list
returns a list of templates based on the filter.
Parameter
Description
select
Array of fields to output. By default, it outputs all template fields except for
users
and
entityTypeId
. To include them, you need to add them additionally. For example,
['*', 'entityTypeId', 'users']
.
order
Array to specify the output order
{"id": "desc"}
.
filter
Array for filtering.
start
offset
for pagination.
Filter Examples
Filter Examples
filter
:
{
"code"
:
"%_US"
,
"numeratorId"
:
"2"
,
"region"
:
"by"
,
"active"
:
"Y"
}
You can pass the entity ID in the filter using the key
entityTypeId
. You should pass the deal code considering the filtering by directions. However, if you need to return templates linked to any deal direction, you can pass it in the filter.
filter
:
{
"entityTypeId"
:
"2%"
}
The method will return a list of templates with their fields.
Response on Success
Response on Success
templates
:
{
115
:
{
"id"
:
"115"
,
"active"
:
"Y"
,
"name"
:
"Act (USA)"
,
"code"
:
"ACT_US"
,
"region"
:
"com"
,
"sort"
:
"100"
,
"createTime"
:
"2018-06-05T13:07:12+02:00"
,
"updateTime"
:
"2018-09-06T14:26:24+02:00"
,
"moduleId"
:
"crm"
,
"numeratorId"
:
"29"
,
"withStamps"
:
"N"
,
"isDeleted"
:
"N"
,
"entityTypeId"
:
[
"0"
:
"4"
,
"1"
:
"3"
,
"2"
:
"2_category_0"
,
"3"
:
"2_category_1"
,
"4"
:
"5"
,
"5"
:
"1"
,
"6"
:
"14"
,
"7"
:
"7"
]
,
"users"
:
[
"0"
:
"UA"
]
}
}
Copied
Was the article helpful?
Yes
No
Previous
Get Document Template Information by Id
Next
Delete Document Template

---

## Delete Document Template crm.documentgenerator.template.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/templates/crm-document-generator-template-delete

Delete Document Template crm.documentgenerator.template.delete | Bitrix24 REST API and Marketplace Applications
Delete Document Template crm.documentgenerator.template.delete
Delete Document Template crm.documentgenerator.template.delete
Parameters
Response on Success
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.template.delete
deletes a template.
Parameters
Parameters
Parameter
Description
id
*
template identifier.
Required parameters are marked with *
Response on Success
Response on Success
The response is empty.
Copied
Was the article helpful?
Yes
No
Previous
Retrieve List of Document Templates
Next
Overview of methods

---

## Numberers

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/numerator/index

Numberers | Bitrix24 REST API and Marketplace Applications
Numberers
Numberers
We are still updating this page
Some data may be missing here — we will complete it soon.
Permissions
Scope
:
crm.documentgenerator
|
Who can execute the method
:
any user
Method
Description
crm.documentgenerator.numerator.add
Adding a new numberer.
crm.documentgenerator.numerator.update
Modifying an existing numberer.
crm.documentgenerator.numerator.get
Retrieving information about a numberer by Id.
crm.documentgenerator.numerator.list
Getting a list of numberers.
crm.documentgenerator.numerator.delete
Deleting a numberer.
Copied
Was the article helpful?
Yes
No
Previous
Delete Document Template
Next
Add a new numberer

---

## Add a new numerator crm.documentgenerator.numerator.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/numerator/crm-document-generator-numerator-add

Add a new numerator crm.documentgenerator.numerator.add | Bitrix24 REST API and Marketplace Applications
Add a new numerator crm.documentgenerator.numerator.add
Add a new numerator crm.documentgenerator.numerator.add
Response in case of success
Continue exploring
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.numerator.add
adds a new numerator.
Parameter
Description
name
Name.
template
Template.
settings
Generator settings.
Response in case of success
Response in case of success
Returns a result identical to
crm.documentgenerator.numerator.get()
.
Continue exploring
Continue exploring
How to Add a Template and Create a Document Based on It
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Modify an existing numberer

---

## Update Existing Numbering crm.documentgenerator.numerator.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/numerator/crm-document-generator-numerator-update

Update Existing Numbering crm.documentgenerator.numerator.update | Bitrix24 REST API and Marketplace Applications
Update Existing Numbering crm.documentgenerator.numerator.update
Update Existing Numbering crm.documentgenerator.numerator.update
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.numerator.update
updates an existing numbering with new values.
Only those numberings that were created through
crm.documentgenerator.numerator.add()
can be updated.
Parameter
Description
id
ID of the numbering.
fields
An array similar to
crm.documentgenerator.numerator.add()
, but all fields are optional.
Response in case of success
Response in case of success
Returns a result identical to
crm.documentgenerator.numerator.get()
.
Copied
Was the article helpful?
Yes
No
Previous
Add a new numberer
Next
Get information about a numberer by Id

---

## Get Information About the Numerator by Id crm.documentgenerator.numerator.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/numerator/crm-document-generator-numerator-get

Get Information About the Numerator by Id crm.documentgenerator.numerator.get | Bitrix24 REST API and Marketplace Applications
Get Information About the Numerator by Id crm.documentgenerator.numerator.get
Get Information About the Numerator by Id crm.documentgenerator.numerator.get
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.numerator.get
returns information about the numerator by its identifier.
Parameter
Description
id
*
ID of the numerator.
Required parameters are marked with *
Successful Response
Successful Response
"numerator"
:
{
"id"
:
"202"
,
// template id
"name"
:
"Rest Template"
,
// name
"template"
:
"{NUMBER}"
,
// template
"settings"
:
{
// generator settings
"Bitrix_Main_Numerator_Generator_SequentNumberGenerator"
:
{
"start"
:
20
,
"step"
:
5
,
"periodicBy"
:
''
,
"timezone"
:
''
,
"isDirectNumeration"
:
''
}
}
,
}
Copied
Was the article helpful?
Yes
No
Previous
Modify an existing numberer
Next
Get a list of numberers

---

## Get the list of numerators crm.documentgenerator.numerator.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/numerator/crm-document-generator-numerator-list

Get the list of numerators crm.documentgenerator.numerator.list | Bitrix24 REST API and Marketplace Applications
Get the list of numerators crm.documentgenerator.numerator.list
Get the list of numerators crm.documentgenerator.numerator.list
We are still updating this page
Some data may be missing — we will complete it soon
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.numerator.list
returns a list of numerators.
Parameter
Description
start
offset
for pagination.
Response on success
Response on success
"numerators"
:
[
{
"id"
:
"202"
,
// template id
"name"
:
"Rest Template"
,
// name
"template"
:
"{NUMBER}"
,
// template
"settings"
:
{
// generator settings
"Bitrix_Main_Numerator_Generator_SequentNumberGenerator"
:
{
"start"
:
20
,
"step"
:
5
,
"periodicBy"
:
''
,
"timezone"
:
''
,
"isDirectNumeration"
:
''
}
}
}
]
Copied
Was the article helpful?
Yes
No
Previous
Get information about a numberer by Id
Next
Delete a numberer

---

## Delete crm.documentgenerator.numerator.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/document-generator/numerator/crm-document-generator-numerator-delete

Delete crm.documentgenerator.numerator.delete | Bitrix24 REST API and Marketplace Applications
Delete crm.documentgenerator.numerator.delete
Delete crm.documentgenerator.numerator.delete
We are still updating this page
Some data may be missing here — we will complete it shortly.
Scope:
crm.documentgenerator
Who can execute the method: any user
The method
crm.documentgenerator.numerator.delete
removes a numerator.
You can only delete numerators that were created using
crm.documentgenerator.numerator.add()
.
Parameter
Description
id
*
ID of the numerator.
Required parameters are marked with *
Response on success
Response on success
The response is empty.
Copied
Was the article helpful?
Yes
No
Previous
Get a list of numberers
Next
Digital Workspaces

---

