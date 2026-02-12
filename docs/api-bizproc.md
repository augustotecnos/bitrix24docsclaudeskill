---
description: 'Business Process API: Workflow automation, actions, robots'
methods:
- bizproc.activity.add
- bizproc.activity.delete
- bizproc.activity.list
- bizproc.activity.log
- bizproc.activity.update
- bizproc.event.send
- bizproc.robot.add
- bizproc.robot.delete
- bizproc.robot.list
- bizproc.robot.update
- bizproc.task.complete
- bizproc.task.delegate
- bizproc.task.list
- bizproc.workflow.instance.list
- bizproc.workflow.instances
- bizproc.workflow.kill
- bizproc.workflow.start
- bizproc.workflow.template.add
- bizproc.workflow.template.delete
- bizproc.workflow.template.list
- bizproc.workflow.template.update
- bizproc.workflow.terminate
- user.get
pages: 26
title: 'Business Process API: Workflow automation, actions, robots'
---
# Business Process API: Workflow automation, actions, robots
> Business Process API: Workflow automation, actions, robots
> **26 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Workflows and Automation Rules](#workflows-and-automation-rules)
- [Start a business process bizproc.workflow.start](#start-a-business-process-bizprocworkflowstart)
- [Get a list of running workflows bizproc.workflow.instances](#get-a-list-of-running-workflows-bizprocworkflowins)
- [Stop Active Workflow bizproc.workflow.terminate](#stop-active-workflow-bizprocworkflowterminate)
- [Delete Running Process bizproc.workflow.kill](#delete-running-process-bizprocworkflowkill)
- [Business Process Templates: Overview of Methods](#business-process-templates-overview-of-methods)
- [Add Business Process Template bizproc.workflow.template.add](#add-business-process-template-bizprocworkflowtempl)
- [Update Business Process Template bizproc.workflow.template.update](#update-business-process-template-bizprocworkflowte)
- [Get the list of templates bizproc.workflow.template.list](#get-the-list-of-templates-bizprocworkflowtemplatel)
- [Delete Business Process Template bizproc.workflow.template.delete](#delete-business-process-template-bizprocworkflowte)
- [Workflow Tasks: Overview of Methods](#workflow-tasks-overview-of-methods)
- [Get the list of workflow tasks bizproc.task.list](#get-the-list-of-workflow-tasks-bizproctasklist)
- [Complete a business process task bizproc.task.complete](#complete-a-business-process-task-bizproctaskcomple)
- [Delegate a workflow task bizproc.task.delegate](#delegate-a-workflow-task-bizproctaskdelegate)
- [Application Actions: Overview of Methods](#application-actions-overview-of-methods)
- [Add a New Action bizproc.activity.add](#add-a-new-action-bizprocactivityadd)
- [Update Action bizproc.activity.update](#update-action-bizprocactivityupdate)
- [Get the list of actions for the bizproc.activity.list application](#get-the-list-of-actions-for-the-bizprocactivitylis)
- [Delete Action bizproc.activity.delete](#delete-action-bizprocactivitydelete)
- [Write information to the business process log bizproc.activity.log](#write-information-to-the-business-process-log-bizp)
- [Application Automation Rules](#application-automation-rules)
- [Register a New Robot bizproc.robot.add](#register-a-new-robot-bizprocrobotadd)
- [Update Robot Fields bizproc.robot.update](#update-robot-fields-bizprocrobotupdate)
- [Get a list of registered application robots bizproc.robot.list](#get-a-list-of-registered-application-robots-bizpro)
- [Delete Registered Robot bizproc.robot.delete](#delete-registered-robot-bizprocrobotdelete)
- [Return parameters to the action or Automation rule bizproc.event.send](#return-parameters-to-the-action-or-automation-rule)

---

## Workflows and Automation Rules

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/index

Workflows and Automation Rules | Bitrix24 REST API and Marketplace Applications
Workflows and Automation Rules
Workflows and Automation Rules
Popular Scenarios Using REST API
Features of Workflow Functionality
Workflow Template
Workflows
Workflow Tasks
Workflow Actions
Automation Rules
Recommended Learning Sequence
Overview of Methods
Workflow Templates
Workflow Tasks
Application Automation Rules
Application Actions
Quick navigation:
all methods and events
Workflows in Bitrix24 are a low-code tool that allows you to automate everyday tasks without needing deep programming knowledge. Users can easily configure various operations using ready-to-use actions.
You will find these automated processes and can launch them directly from sections such as
Feed
,
CRM
,
Drive
,
SPAs
, and
Universal Lists
.
Workflows can be automatically triggered by specific events (for example, when a new deal is added to CRM) or initiated by the user (like the vacation approval process through the Feed).
In addition to workflows, Bitrix24 offers
automation rules
— an even simpler way to automate tasks, especially convenient for regular users. Automation rules are actively used in CRM and task management.
Popular Scenarios Using REST API
Popular Scenarios Using REST API
With the appropriate methods, you can:
Add ready-made industry
workflow templates
accepted in specific business sectors or types of companies
Propose your scenarios for automatic
workflow launches
(for example, generating an explanatory note in case of a serious project deadline violation, etc.)
Offer workflow launches in your
widgets
if standard interfaces do not provide such an option for the user
You can expand the capabilities of user automation in Bitrix24 by adding your own
workflow actions
and
automation rules
that can:
Send documents to external systems
Create or modify orders in an external online store
Transfer data from external systems to Bitrix24
Launch ready-made external processes (for example, connecting a special external chatbot to a conversation with a client when the deal moves to the delivery approval stage)
Transfer payment data to external Sales Intelligence
Execute a completed business scenario (for example, generating a complex invoice or collecting data from all deals of a single client and returning the total for further use)
Recommendations
Add automation rules instead of workflow actions, as each registered automation rule can also be used as a workflow action. Additionally, your automation rules will be available in
Smart Scenarios
If you want to send changes to an external system when deal or lead statuses change, it’s better to
register an automation rule
that the user will place at the desired stage, instead of intercepting the event on
deal change
or
lead
. This will save you from having to create an interface for matching lead and deal stages with statuses or events of the external system and significantly simplify development.
Features of Workflow Functionality
Features of Workflow Functionality
It is important to understand the terminology and relationships between the objects that implement workflow functionality.
Workflow Template
Workflow Template
This is essentially a logical scheme, an algorithm that implements the required business logic using individual actions and operations available in the workflow designer.
A
template
is always tied to a specific
base object
, the data of which it will operate on. For example, a template may be linked to CRM deals. In this case, the base object will be a specific deal for which the workflow will be launched.
The binding to the base object also defines the context for launching the workflow: for instance, you cannot launch a workflow for a lead based on a template designed for a deal.
Objects can include leads, contacts, companies, invoices, and estimates in CRM, elements of user-defined object types (SPAs), files in Bitrix24 Drive, and others.
A workflow template can have input parameters that the user (or your code) must fill in when launching the workflow based on the selected template.
In addition to input parameters, internal variables can also be used. The template developer must add them in the template settings.
It is important to understand that when we talk about input parameters and variables, we are referring to "descriptions." However, actual values for parameters and variables only arise when a real workflow is launched.
Workflows
Workflows
A workflow is, in fact, a "live" instance created from a template at the moment of
launch
for a specific base object. Clearly, multiple workflows can be launched simultaneously for different base objects.
When a workflow is launched, a copy of the workflow template is created, which remains unchanged until the workflow is completed. If the user makes changes to the template during the execution of the workflow, it will not affect the logic of the already launched workflow.
The values of input parameters and internal variables also have specific values for each individual workflow and change only for it.
Workflow Tasks
Workflow Tasks
During execution, a workflow can use special actions — tasks for workflow participants, when the logic of the workflow requires obtaining additional information from the user, such as approving a document, uploading a file, and so on.
Such actions generate
workflow tasks
. Users who receive tasks see the corresponding information in Bitrix24 and also receive notifications. The
current tasks
for a user can also be retrieved using the corresponding REST API method for automatic processing.
Workflow Actions
Workflow Actions
Actions
of a workflow are the "blocks" from which the workflow template is built. Typically, they represent isolated atomic operations like "Create Task," "Generate Invoice," "Change Document Field Value," and so on.
Workflow actions can have input parameters that the user can specify in the workflow designer during the development of the desired template.
Additionally, actions can return resulting data "back" to the workflow. This data can be used by the workflow designer as input parameters for subsequent actions.
Using the REST API, you can
add your own actions
to workflows in Bitrix24.
Automation Rules
Automation Rules
Automation rules
are objects similar to workflow actions, with the main difference being that they are primarily used not in the workflow designer but in special interfaces of CRM and tasks.
Automation rules can also have input parameters, the values of which will be set by the user configuring the rules in lead funnels, deals, or smart scenarios. They can also return values for use as input parameters for subsequent automation rules.
Using the REST API, you can
add your own automation rules
to Bitrix24. We recommend adding automation rules instead of workflow actions, as automation rules can be used within the workflow designer, meaning you will add your functionality to both the automation rules settings and the workflow designer at once.
Recommended Learning Sequence
Recommended Learning Sequence
Add
your automation rule
to Bitrix24
Learn how to
start a ready-made workflow
or
stop
an already launched one
Discover how to
add your template
Learn how to get a list of current
workflow tasks
, automatically
complete
them for the user, and
delegate
to another user
Overview of Methods
Overview of Methods
Method
Description
bizproc.workflow.start
Starts a new workflow
bizproc.workflow.instances
Returns a list of launched workflows
bizproc.workflow.kill
Deletes a launched workflow along with all process data
bizproc.workflow.terminate
Interrupts the execution of a workflow
Workflow Templates
Workflow Templates
Method
Description
bizproc.workflow.template.add
Adds a new workflow template
bizproc.workflow.template.update
Updates an existing workflow template
bizproc.workflow.template.delete
Deletes a workflow template
bizproc.workflow.template.list
Returns a list of workflow templates
Workflow Tasks
Workflow Tasks
Method
Description
bizproc.task.list
Retrieves a list of workflow tasks
bizproc.task.complete
Completes a workflow task
bizproc.task.delegate
Delegates a workflow task
Application Automation Rules
Application Automation Rules
Method
Description
bizproc.robot.add
Registers a new automation rule
bizproc.robot.update
Updates fields of an already added automation rule
bizproc.robot.list
Returns a list of automation rules registered by the application
bizproc.robot.delete
Deletes a registered automation rule
bizproc.event.send
Returns output parameters for the action specified in the action description
Application Actions
Application Actions
Method
Description
bizproc.activity.add
Adds a new action for use in workflows
bizproc.activity.update
Updates fields of an already added action
bizproc.activity.list
Returns a list of actions installed by the application
bizproc.activity.log
Records information in the workflow log
bizproc.activity.delete
Deletes an action installed by the application
Was the article helpful?
Yes
No
Previous
Get Stage Movement History
Next
Start Workflow

---

## Start a business process bizproc.workflow.start

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-workflow-start

Start a business process bizproc.workflow.start | Bitrix24 REST API and Marketplace Applications
Method Parameters
Start a business process bizproc.workflow.start
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
The method
bizproc.workflow.start
initiates a new business process.
You can only start a business process using REST on paid plans, demo licenses, and NFR licenses.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
TEMPLATE_ID
*
integer
Identifier of the business process template
DOCUMENT_ID
*
array
Identifier of the document to start the business process in the format [
module
,
object
,
ID_element
].
Examples of entries for different document types:
Lead —
['crm', 'CCrmDocumentLead', 'LEAD_777']
Company —
['crm', 'CCrmDocumentCompany', 'COMPANY_777']
Contact —
['crm', 'CCrmDocumentContact', 'CONTACT_777']
Deal —
['crm', 'CCrmDocumentDeal', 'DEAL_777']
Drive file —
['disk', 'Bitrix\\Disk\\BizProcDocument', '777']
News feed process document —
['lists', 'BizprocDocument', '777']
Lists document —
['lists', 'Bitrix\\Lists\\BizprocDocumentLists', '777']
Smart process element —
['crm', 'Bitrix\\Crm\\Integration\\BizProc\\Document\\Dynamic', 'DYNAMIC_147_1']
, where
147
is the
ID
of the smart process, and
1
is the
ID
of the smart process element
Invoice —
['crm', 'Bitrix\\Crm\\Integration\\BizProc\\Document\\SmartInvoice', 'SMART_INVOICE_3']
PARAMETERS
object
Values of the business process template parameters.
Used if the template has parameters.
To pass a value to a parameter of type "User binding," use the format
user_ID
. For example:
PARAMETERS: {
'resp_employee'
: user_14
// Employee ID — 14
}
Code Examples
Code Examples
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
'{"TEMPLATE_ID":1,"DOCUMENT_ID":["crm","CCrmDocumentLead","LEAD_1"],"PARAMETERS":{"Parameter1":"user_1"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/bizproc.workflow.start
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"TEMPLATE_ID":1,"DOCUMENT_ID":["crm","CCrmDocumentLead","LEAD_1"],"PARAMETERS":{"Parameter1":"user_1"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.workflow.start
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.workflow.start'
,
{
TEMPLATE_ID
:
1
,
DOCUMENT_ID
: [
'crm'
,
'CCrmDocumentLead'
,
'LEAD_1'
],
PARAMETERS
: {
'Parameter1'
:
'user_1'
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
(
'response'
, result.
answer
);
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
'bizproc.workflow.start'
,
[
'TEMPLATE_ID'
=>
1
,
'DOCUMENT_ID'
=> [
'crm'
,
'CCrmDocumentLead'
,
'LEAD_1'
],
'PARAMETERS'
=> [
'Parameter1'
=>
'user_1'
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
'Error starting workflow: '
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
'bizproc.workflow.start'
,
{
TEMPLATE_ID
:
1
,
DOCUMENT_ID
: [
'crm'
,
'CCrmDocumentLead'
,
'LEAD_1'
],
PARAMETERS
: {
'Parameter1'
:
'user_1'
},
},
function
(
result
) {
console
.
log
(
'response'
, result.
answer
);
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
'bizproc.workflow.start'
,
[
'TEMPLATE_ID'
=>
1
,
'DOCUMENT_ID'
=> [
'crm'
,
'CCrmDocumentLead'
,
'LEAD_1'
],
'PARAMETERS'
=> [
'Parameter1'
=>
'user_1'
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
"66e81a641752f8.56521481"
,
"time"
:
{
"start"
:
1726476060.581428
,
"finish"
:
1726476060.813776
,
"duration"
:
0.23234796524047852
,
"processing"
:
0.002630949020385742
,
"date_start"
:
"2024-09-16T08:41:00+00:00"
,
"date_finish"
:
"2024-09-16T08:41:00+00:00"
,
"operating_reset_at"
:
1726476660
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
string
Root element of the response.
Returns the identifier of the started business process
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
"ERROR_WRONG_WORKFLOW_ID"
,
"error_description"
:
"Empty TEMPLATE_ID"
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
ERROR_WRONG_WORKFLOW_ID
Empty TEMPLATE_ID
An empty input parameter
TEMPLATE_ID
was provided
400
ERROR_WRONG_WORKFLOW_ID
Template not found
The business process template was not found for the provided
TEMPLATE_ID
400
Empty value
Wrong DOCUMENT_ID!
An incorrect
DOCUMENT_ID
was provided
400
Empty value
Incorrect document type!
Unable to determine the document type from the provided
DOCUMENT_ID
400
Empty value
Template type and DOCUMENT_ID mismatch!
The document type in the template does not match the type determined from
DOCUMENT_ID
.
Attempting to start the template on the wrong entity for which it was created
403
ACCESS_DENIED
Access denied!
The method was not executed by an administrator
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
Workflows and Automation Rules
Get a list of running workflows bizproc.workflow.instances
Stop Active Workflow bizproc.workflow.terminate
Delete Running Process bizproc.workflow.kill
Copied
Was the article helpful?
Yes
No
Previous
Overview
Next
Get List of Workflows

---

## Get a list of running workflows bizproc.workflow.instances

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-workflow-instances

Get a list of running workflows bizproc.workflow.instances | Bitrix24 REST API and Marketplace Applications
Get a list of running workflows bizproc.workflow.instances
Get a list of running workflows bizproc.workflow.instances
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method retrieves a list of running workflows.
bizproc.workflow.instance.list
There is an old method
bizproc.workflow.instance.list
— an alias for the method
bizproc.workflow.instances
. It accepts the same parameters and returns the same results.
Support for
bizproc.workflow.instance.list
is not guaranteed in the future, so we recommend using
bizproc.workflow.instances
.
Method Parameters
Method Parameters
Name
type
Description
SELECT
array
An array containing the list of fields to select.
You can specify only the fields that are necessary.
Available fields:
ID
— identifier of the workflow
MODIFIED
— date of the last modification
OWNED_UNTIL
— time the workflow is locked. The process is considered stuck if the difference between the lock time and the current time is more than 5 minutes
MODULE_ID
— module identifier by document
ENTITY
— entity identifier by document
DOCUMENT_ID
— document identifier
STARTED
— date the workflow was started
STARTED_BY
— who started the workflow
TEMPLATE_ID
— identifier of the workflow template
Default value:
['ID', 'MODIFIED', 'OWNED_UNTIL']
FILTER
object
An object for filtering the list of running workflows in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
The list of filterable fields is the same as for the
SELECT
parameter.
You can specify the type of filtering before the name of the filtered field:
!
— not equal
<
— less than
<=
— less than or equal to
>
— greater than
>=
— greater than or equal to
ORDER
object
An object for sorting the list of running workflows in the format
{"field_1": "value_1", ... "field_N": "value_N"}
.
The list of fields for sorting is the same as for the
SELECT
parameter.
The sorting direction can take the following values:
asc
— ascending
desc
— descending
Default value:
{'MODIFIED': 'desc'}
start
integer
This parameter is used for managing pagination.
The page size of results is always static — 50 records.
To select the second page of results, you need to pass the value
50
. To select the third page of results — the value
100
, and so on.
The formula for calculating the value of the
start
parameter:
start = (N - 1) * 50
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
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"select":["ID","MODIFIED","OWNED_UNTIL","MODULE_ID","ENTITY","DOCUMENT_ID","STARTED","STARTED_BY","TEMPLATE_ID"],"order":{"STARTED":"DESC"},"filter":{">STARTED_BY":0}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/bizproc.workflow.instances
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"select":["ID","MODIFIED","OWNED_UNTIL","MODULE_ID","ENTITY","DOCUMENT_ID","STARTED","STARTED_BY","TEMPLATE_ID"],"order":{"STARTED":"DESC"},"filter":{">STARTED_BY":0},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.workflow.instances
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.workflow.instances'
,
{
select
: [
'ID'
,
'MODIFIED'
,
'OWNED_UNTIL'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'STARTED'
,
'STARTED_BY'
,
'TEMPLATE_ID'
],
order
: {
STARTED
:
'DESC'
},
filter
: {
'>STARTED_BY'
:
0
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
alert
(
"Error: "
+ error);
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
'bizproc.workflow.instances'
,
[
'select'
=> [
'ID'
,
'MODIFIED'
,
'OWNED_UNTIL'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'STARTED'
,
'STARTED_BY'
,
'TEMPLATE_ID'
],
'order'
=> [
'STARTED'
=>
'DESC'
],
'filter'
=> [
'>STARTED_BY'
=>
0
]
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
'Error fetching workflow instances: '
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
'bizproc.workflow.instances'
,
{
select
: [
'ID'
,
'MODIFIED'
,
'OWNED_UNTIL'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'STARTED'
,
'STARTED_BY'
,
'TEMPLATE_ID'
],
order
: {
STARTED
:
'DESC'
},
filter
: {
'>STARTED_BY'
:
0
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
alert
(
"Error: "
+ result.
error
());
else
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
'bizproc.workflow.instances'
,
[
'select'
=> [
'ID'
,
'MODIFIED'
,
'OWNED_UNTIL'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'STARTED'
,
'STARTED_BY'
,
'TEMPLATE_ID'
],
'order'
=> [
'STARTED'
=>
'DESC'
],
'filter'
=> [
'>STARTED_BY'
=>
0
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
"DOCUMENT_ID"
:
"LEAD_1"
,
"ENTITY"
:
"CCrmDocumentLead"
,
"ID"
:
"66e412fdc9bd44.36306599"
,
"STARTED"
:
"2024-09-13T10:25:01+00:00"
,
"MODULE_ID"
:
"crm"
,
"OWNED_UNTIL"
:
null
,
"TEMPLATE_ID"
:
"1"
,
"STARTED_BY"
:
"0"
}
,
{
"DOCUMENT_ID"
:
"DEAL_1633"
,
"ENTITY"
:
"CCrmDocumentDeal"
,
"ID"
:
"658c4d3d6a2906.51542462"
,
"STARTED"
:
"2023-12-27T19:13:49+02:00"
,
"MODULE_ID"
:
"crm"
,
"OWNED_UNTIL"
:
null
,
"TEMPLATE_ID"
:
"212"
,
"STARTED_BY"
:
"57"
}
]
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
1726476060.581428
,
"finish"
:
1726476060.813776
,
"duration"
:
0.23234796524047852
,
"processing"
:
0.002630949020385742
,
"date_start"
:
"2024-09-16T08:41:00+00:00"
,
"date_finish"
:
"2024-09-16T08:41:00+00:00"
,
"operating_reset_at"
:
1726476660
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
The root element of the response.
Contains an array of objects with information about running workflows
total
integer
The total number of records found
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
403
{
"error"
:
"ACCESS_DENIED"
,
"error_description"
:
"Access denied!"
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
ACCESS_DENIED
Access denied!
Method was executed by a non-administrator
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
Workflows and Automation Rules
Start a business process bizproc.workflow.start
Stop Active Workflow bizproc.workflow.terminate
Delete Running Process bizproc.workflow.kill
How to Complete Business Processes of a Terminated Employee
How to Mass Finish Workflows with Date Filter
Copied
Was the article helpful?
Yes
No
Previous
Start Workflow
Next
Stop Workflow

---

## Stop Active Workflow bizproc.workflow.terminate

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-workflow-terminate

Stop Active Workflow bizproc.workflow.terminate | Bitrix24 REST API and Marketplace Applications
Method Parameters
Stop Active Workflow bizproc.workflow.terminate
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method stops the specified workflow. All data related to the workflow will be preserved.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ID
*
string
Identifier of the workflow to be stopped.
The identifier can be obtained using the
bizproc.workflow.instances
method.
STATUS
string
Set the status text.
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
'{"ID":"65e5a449e8f135.21284909","STATUS":"Terminated by rest app."}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/bizproc.workflow.terminate
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":"65e5a449e8f135.21284909","STATUS":"Terminated by rest app.","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.workflow.terminate
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.workflow.terminate'
,
{
ID
:
'65e5a449e8f135.21284909'
,
STATUS
:
'Terminated by rest app.'
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
(
'response'
, result.
answer
);
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
(
'Error:'
, error);
}
try
{
$workflowId
=
'your_workflow_id'
;
// Replace with actual workflow ID
$message
=
'Workflow terminated'
;
// Replace with actual message
$result
=
$serviceBuilder
->
getBizProcScope
()
->
workflow
()
->
terminate
(
$workflowId
,
$message
);
if
(
$result
->
isSuccess
()) {
print
(
$result
->
getCoreResponse
()->
getResponseData
()->
getResult
()[
0
]);
}
else
{
print
(
'Termination failed.'
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
'Error: '
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
'bizproc.workflow.terminate'
,
{
ID
:
'65e5a449e8f135.21284909'
,
STATUS
:
'Terminated by rest app.'
,
},
function
(
result
) {
console
.
log
(
'response'
, result.
answer
);
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
'bizproc.workflow.terminate'
,
[
'ID'
=>
'65e5a449e8f135.21284909'
,
'STATUS'
=>
'Terminated by rest app.'
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
1726476060.581428
,
"finish"
:
1726476060.813776
,
"duration"
:
0.23234796524047852
,
"processing"
:
0.002630949020385742
,
"date_start"
:
"2024-09-16T08:41:00+00:00"
,
"date_finish"
:
"2024-09-16T08:41:00+00:00"
,
"operating_reset_at"
:
1726476660
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
Root element of the response.
Contains
true
in case of success.
time
time
Information about the request execution time.
Error Handling
Error Handling
HTTP status:
400
,
403
{
"error"
:
"ACCESS_DENIED"
,
"error_description"
:
"Access denied!"
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
ACCESS_DENIED
Access denied!
Method was not executed by an administrator.
400
ERROR_WRONG_WORKFLOW_ID
Empty workflow instance ID
An empty value was passed to the
ID
parameter.
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
Workflows and Automation Rules
Start a business process bizproc.workflow.start
Get a list of running workflows bizproc.workflow.instances
Delete Running Process bizproc.workflow.kill
How to Complete Business Processes of a Terminated Employee
How to Mass Finish Workflows with Date Filter
Copied
Was the article helpful?
Yes
No
Previous
Get List of Workflows
Next
Delete Active Process

---

## Delete Running Process bizproc.workflow.kill

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-workflow-kill

Delete Running Process bizproc.workflow.kill | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Running Process bizproc.workflow.kill
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method deletes the running workflow along with all process data.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ID
*
integer
Identifier of the workflow
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
'{"ID":"65e5a449e8f135.21284909"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/bizproc.workflow.kill
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":"65e5a449e8f135.21284909","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.workflow.kill
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.workflow.kill'
,
{
ID
:
'65e5a449e8f135.21284909'
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
(
'response'
, result.
answer
);
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
(
'Error:'
, error);
}
try
{
$workflowId
=
'your_workflow_id'
;
// Replace with your actual workflow ID
$result
=
$serviceBuilder
->
getBizProcScope
()
->
workflow
()
->
kill
(
$workflowId
);
if
(
$result
->
isSuccess
()) {
print_r
(
$result
->
getCoreResponse
()->
getResponseData
()->
getResult
());
}
else
{
print
(
'Failed to kill workflow: '
.
json_encode
(
$result
->
getCoreResponse
()->
getResponseData
()->
getResult
()));
}
}
catch
(
Throwable
$e
) {
print
(
'Error occurred: '
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
'bizproc.workflow.kill'
,
{
ID
:
'65e5a449e8f135.21284909'
,
},
function
(
result
) {
console
.
log
(
'response'
, result.
answer
);
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
'bizproc.workflow.kill'
,
[
'ID'
=>
'65e5a449e8f135.21284909'
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
1726476060.581428
,
"finish"
:
1726476060.813776
,
"duration"
:
0.23234796524047852
,
"processing"
:
0.002630949020385742
,
"date_start"
:
"2024-09-16T08:41:00+00:00"
,
"date_finish"
:
"2024-09-16T08:41:00+00:00"
,
"operating_reset_at"
:
1726476660
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
Root element of the response.
Contains
true
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
"ACCESS_DENIED"
,
"error_description"
:
"Access denied!"
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
ACCESS_DENIED
Access denied!
Method was not executed by an administrator
400
ERROR_WRONG_WORKFLOW_ID
Empty workflow instance ID
Empty value was passed to the
ID
parameter
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
Workflows and Automation Rules
Start a business process bizproc.workflow.start
Get a list of running workflows bizproc.workflow.instances
Stop Active Workflow bizproc.workflow.terminate
How to Complete Business Processes of a Terminated Employee
How to Mass Finish Workflows with Date Filter
Copied
Was the article helpful?
Yes
No
Previous
Stop Workflow
Next
Overview of Methods

---

## Business Process Templates: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/template/index

Business Process Templates: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Add a Business Process Template
Business Process Templates: Overview of Methods
Add a Business Process Template
Application Context
Template Connection to Document
Possible Values
Get List of Templates
Overview of Methods
A business process template is a logical scheme. It implements business logic through actions and operations in the business process designer.
Quick navigation:
all methods and events
User documentation:
How to create a sequential business process template
How to configure template parameters
Add a Business Process Template
Add a Business Process Template
The method
bizproc.workflow.template.add
adds a template to Bitrix24 from a file with the
.bpt
extension. To obtain the file, configure the business process template and export it.
The resulting file can be used as a template in the desired Bitrix24.
User documentation
Business Process Designer
Exporting and Importing Business Process Templates
Application Context
Application Context
The system ties the new template to an
application
. Templates created by the method
bizproc.workflow.template.add
can only be updated or deleted in the context of the application they were created with.
Template Connection to Document
Template Connection to Document
Each template is linked to a base object whose data it manages. For example, a template may be linked to CRM deals. In this case, the base object will be a specific deal for which the business process is initiated.
The connection to the base object defines the launch context: you cannot start a process for a lead using a template for a deal.
The template is linked to the document through the
DOCUMENT_TYPE
parameter, which is an array of three elements:
module identifier
object type
document type
For example,
['crm', 'CCrmDocumentLead', 'LEAD']
.
The values in the array are interrelated. If the first element is
'crm'
, the others must correspond to CRM. It is important to ensure the correctness of the values.
Possible Values
Possible Values
Module Identifier.
Indicates the scope of the business process template.
crm
— CRM
lists
— Universal lists
disk
— Bitrix24 Disk
Object Identifier.
The object within the specified module. For example, in CRM, the object can be a lead or a deal.
CRM
CCrmDocumentLead
— leads
CCrmDocumentContact
— contacts
CCrmDocumentCompany
— companies
CCrmDocumentDeal
— deals
Bitrix\Crm\Integration\BizProc\Document\Quote
— estimates
Bitrix\Crm\Integration\BizProc\Document\SmartInvoice
— invoices
Bitrix\Crm\Integration\BizProc\Document\Dynamic
— SPAs
Lists
BizprocDocument
— processes in the news feed
Bitrix\Lists\BizprocDocumentLists
— lists in groups
Disk
Bitrix\Disk\BizProcDocument
Document Type.
Binding to a specific document of the specified object.
CRM
LEAD
— leads
CONTACT
— contacts
COMPANY
— companies
DEAL
— deals
QUOTE
— estimates
SMART_INVOICE
— invoices
DYNAMIC_XXX
— SPAs, where XXX is the SPA identifier
Universal Lists
iblock_XXX
— information block, where XXX is the information block identifier
Disk
STORAGE_XXX
— disk storage, where XXX is the storage identifier
Get List of Templates
Get List of Templates
To obtain a list of all templates in the account, use the method
bizproc.workflow.template.list
. To get a list of application templates, specify the
FILTER
parameter with the
SYSTEM_CODE
field and the symbolic code of the application, for example,
"SYSTEM_CODE": "rest_app_5"
.
Overview of Methods
Overview of Methods
Scope:
bizproc
Who can execute the method: depending on the method
Method
Description
bizproc.workflow.template.add
Add a business process template from a file
bizproc.workflow.template.update
Update a template
bizproc.workflow.template.list
Get a list of templates
bizproc.workflow.template.delete
Delete a template
Copied
Was the article helpful?
Yes
No
Previous
Delete Active Process
Next
Add Template

---

## Add Business Process Template bizproc.workflow.template.add

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/template/bizproc-workflow-template-add

Add Business Process Template bizproc.workflow.template.add | Bitrix24 REST API and Marketplace Applications
Add Business Process Template bizproc.workflow.template.add
Add Business Process Template bizproc.workflow.template.add
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method adds a business process template from a file.
The business process template must be pre-configured. Export the completed template
to a file
with the
.bpt
extension. The resulting file can be added as a template to the desired Bitrix24.
The method works only in the context of an
application
. The system binds the new template to the application.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
DOCUMENT_TYPE
*
array
Document type. Consists of three string-type elements. They define to which type of objects the new business process template should be attached.
Possible value options:
CRM Module
['crm', 'CCrmDocumentLead', 'LEAD']
— leads
['crm', 'CCrmDocumentContact', 'CONTACT']
— contacts
['crm', 'CCrmDocumentCompany', 'COMPANY']
— companies
['crm', 'CCrmDocumentDeal', 'DEAL']
— deals
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Quote', 'QUOTE']
— estimates
['crm', 'Bitrix\Crm\Integration\BizProc\Document\SmartInvoice', 'SMART_INVOICE']
— invoices
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Dynamic', 'DYNAMIC_XXX']
— SPAs, where XXX is the SPA identifier
Lists Module
['lists', 'BizprocDocument', 'iblock_XXX']
— processes in the news feed, where XXX is the information block identifier
['lists', 'Bitrix\Lists\BizprocDocumentLists', 'iblock_XXX']
— lists in groups, where XXX is the information block identifier
Drive Module
['disk', 'Bitrix\Disk\BizProcDocument', 'STORAGE_XXX']
, where XXX is the storage identifier
NAME
*
string
Template name
DESCRIPTION
string
Template description
TEMPLATE_DATA
*
file
Content of the business process template file in
.bpt
format.
More about file transfer methods can be found in the article
How to Upload Files
AUTO_EXECUTE
integer
Auto-execution settings for the template. Can have the value:
0
— no auto-execution
1
— execute on creation
2
— execute on modification
3
— execute on creation and modification
Default is
0
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"DOCUMENT_TYPE":["lists","BizprocDocument","iblock_164"],"NAME":"App template","DESCRIPTION":"Template was generated by rest application.","AUTO_EXECUTE":3,"TEMPLATE_DATA":["bp-379.bpt","eNrlWNtO41YUfe9XRH5vlTiJhxj1IYkdYTU3Jeb2ZBkwg1UHU9t0BiFLhKk6rTq9aNSHqupF7RcwU1JSIOEXjv+oex/biZ04YWagIKYvcE7Ots9ea9+t8hx/aPOPeGZFbLWlRp1Z1Hl20eYXeEYWa81qURaZRZXP8Ic6n4ZFHsVzcHiwpzEgx3I809Y+29d2HV01Vk3r023DfFLcdPTPdecAJUC4rnaoML5U6+wZqkO3BZ6hgrDdwn2GZ9bp/zTPNC1zT7McXbPxehZvzcPTumPQRzkQIb+TodclF6RHTsmQvCYn3jGsL7wXZOB9Q/5JkVekT87IgPS87ofkyjsC+S9x43VH12hWR7dt3dzFaxbwGtBCwE2aP3TpToztWrFdO7aTY7vl2G41tlsLd65LaSnv6MaWpe3O5xovNDfrmlPTbFt9rM2gmYV1MZ9Oc2llocCxBYUrsByr5Atsnn073qlzZOA8uFDWnjpUMov8vwRGe+TS+z4FRhiSc3Likw/rHp86/Lh9YDtah6+bT6rmpmq4H0SeAMP1YPOa/j2JS4PgnyB27j3zvgajwutPqW2jYgIo7/qqjLSrmFZHpfqBdvQsPzpbtjWrYpmdCMHgRTyj7js7psUsurE3obRszpGN+mIW6CZ/AOgheQUK94CAPukhQnC3jyjQY9IPdRW3dMe0ymanAyEz0nXaC3znQPegZim2ijVRhhgduxGYcaXYkoqlqhj/tdyot+ViXY46JygsNMrLNbEuKxVJrAr0kE2jgVmekajLFwKHCx0pU8CTlPctDbJLhIZmCNwtdEsApftQUNOKbjiapW4gNxt8xo96BB3+lPZ/akHS0C10wNFPtX3D0ffGUkg5+mn0sZJqa9MXQ/4CRuHRp8xindoSo1GqicBDramsJYHLodl+9B0rRRMFBejbDz10PmrQZQt80NEDqt4EeubWoE/cnoi/1hAkMLWglNaT8GM2IT8jwgn0E0BhuQ/hcA8gIzcnAhSgOCnllhjUqCkDsxEDYzQCSEgk74V5QR0f+CzrYugG1o1Cv6Ft03diW8w6pWqj/ImSnJYwciEtgdcOvC8gyR6BFU+gsvcB54CWn7/IEKt/UJVulq8SrJq59XwFjxbLsrSS6MhZECc/QD2EMgIVc4Btj3fsvbjOh2G5YZrG/URuePO070JYlppKc7lUldpLYqKFWQzd36Ble0at2Acr0gYvyYFnQ0zfG8RMaE6l0mrUkhDmC9HqM4DFc2yfcHMyaWnSf9jZqjBiQ24kccHlo1wMqbEHlA8/Vb9/jICi7UZLTnQM7Kx/AqCntAXu+n3kEWLGAQY4OL8e/c1T3O23ZIgReljaVGcnqxW8l/wKdj7zoxwb6P8gQUcYggttx9J3HwfM2abl4OybCUDZmuPA6Xj6xN69vdRYVYqCoFQarVpscsoFh6IgyROn7gRrqBsmCP8XxRnnE58eP0MK2rYK2q+oxr4WmWgm6I6hmE5DEFfNlrgiiatKUyrLy63E8pLnqMed0fkFhjHy92iGASe8wAC8onPbaTBDd8HvhlCAjpIqzrZuaPeTjsObEytOyIMsrskzpwF/6oT88i7AnXA2vnPg4c3TwB/FgSvyetMPwPSkD2Qp/D65StGPKJQFzMZvyQM6pGZom6E+jT1HN3fHUTTB05jx4D07TscIlkt06d45oZMQRpTiJa4f64IoF6XqvKDKLbxRUD3AYMqM4M+KpSw3M5YeYAxxMbyzQyiXvz6E/uehk8NvU0LyjIMJ6Bf6AeKSjnF9aAB7QBd0O/gpF3vCU2ZODb/jRmd+5YXTtVp1xvjKItSX9LP0VzQlUHgX3nfe8wcC0HX/BTDK1SA="],"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.workflow.template.add
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.workflow.template.add'
,
{
DOCUMENT_TYPE
: [
'lists'
,
'BizprocDocument'
,
'iblock_164'
],
NAME
:
'App template'
,
DESCRIPTION
:
'Template was generated by rest application.'
,
AUTO_EXECUTE
:
3
,
TEMPLATE_DATA
: [
"bp-379.bpt"
,
"eNrlWNtO41YUfe9XRH5vlTiJhxj1IYkdYTU3Jeb2ZBkwg1UHU9t0BiFLhKk6rTq9aNSHqupF7RcwU1JSIOEXjv+oex/biZ04YWagIKYvcE7Ots9ea9+t8hx/aPOPeGZFbLWlRp1Z1Hl20eYXeEYWa81qURaZRZXP8Ic6n4ZFHsVzcHiwpzEgx3I809Y+29d2HV01Vk3r023DfFLcdPTPdecAJUC4rnaoML5U6+wZqkO3BZ6hgrDdwn2GZ9bp/zTPNC1zT7McXbPxehZvzcPTumPQRzkQIb+TodclF6RHTsmQvCYn3jGsL7wXZOB9Q/5JkVekT87IgPS87ofkyjsC+S9x43VH12hWR7dt3dzFaxbwGtBCwE2aP3TpToztWrFdO7aTY7vl2G41tlsLd65LaSnv6MaWpe3O5xovNDfrmlPTbFt9rM2gmYV1MZ9Oc2llocCxBYUrsByr5Atsnn073qlzZOA8uFDWnjpUMov8vwRGe+TS+z4FRhiSc3Likw/rHp86/Lh9YDtah6+bT6rmpmq4H0SeAMP1YPOa/j2JS4PgnyB27j3zvgajwutPqW2jYgIo7/qqjLSrmFZHpfqBdvQsPzpbtjWrYpmdCMHgRTyj7js7psUsurE3obRszpGN+mIW6CZ/AOgheQUK94CAPukhQnC3jyjQY9IPdRW3dMe0ymanAyEz0nXaC3znQPegZim2ijVRhhgduxGYcaXYkoqlqhj/tdyot+ViXY46JygsNMrLNbEuKxVJrAr0kE2jgVmekajLFwKHCx0pU8CTlPctDbJLhIZmCNwtdEsApftQUNOKbjiapW4gNxt8xo96BB3+lPZ/akHS0C10wNFPtX3D0ffGUkg5+mn0sZJqa9MXQ/4CRuHRp8xindoSo1GqicBDramsJYHLodl+9B0rRRMFBejbDz10PmrQZQt80NEDqt4EeubWoE/cnoi/1hAkMLWglNaT8GM2IT8jwgn0E0BhuQ/hcA8gIzcnAhSgOCnllhjUqCkDsxEDYzQCSEgk74V5QR0f+CzrYugG1o1Cv6Ft03diW8w6pWqj/ImSnJYwciEtgdcOvC8gyR6BFU+gsvcB54CWn7/IEKt/UJVulq8SrJq59XwFjxbLsrSS6MhZECc/QD2EMgIVc4Btj3fsvbjOh2G5YZrG/URuePO070JYlppKc7lUldpLYqKFWQzd36Ble0at2Acr0gYvyYFnQ0zfG8RMaE6l0mrUkhDmC9HqM4DFc2yfcHMyaWnSf9jZqjBiQ24kccHlo1wMqbEHlA8/Vb9/jICi7UZLTnQM7Kx/AqCntAXu+n3kEWLGAQY4OL8e/c1T3O23ZIgReljaVGcnqxW8l/wKdj7zoxwb6P8gQUcYggttx9J3HwfM2abl4OybCUDZmuPA6Xj6xN69vdRYVYqCoFQarVpscsoFh6IgyROn7gRrqBsmCP8XxRnnE58eP0MK2rYK2q+oxr4WmWgm6I6hmE5DEFfNlrgiiatKUyrLy63E8pLnqMed0fkFhjHy92iGASe8wAC8onPbaTBDd8HvhlCAjpIqzrZuaPeTjsObEytOyIMsrskzpwF/6oT88i7AnXA2vnPg4c3TwB/FgSvyetMPwPSkD2Qp/D65StGPKJQFzMZvyQM6pGZom6E+jT1HN3fHUTTB05jx4D07TscIlkt06d45oZMQRpTiJa4f64IoF6XqvKDKLbxRUD3AYMqM4M+KpSw3M5YeYAxxMbyzQyiXvz6E/uehk8NvU0LyjIMJ6Bf6AeKSjnF9aAB7QBd0O/gpF3vCU2ZODb/jRmd+5YXTtVp1xvjKItSX9LP0VzQlUHgX3nfe8wcC0HX/BTDK1SA="
]
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
alert
(
"Error: "
+ error);
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
'bizproc.workflow.template.add'
,
[
'DOCUMENT_TYPE'
=> [
'lists'
,
'BizprocDocument'
,
'iblock_164'
],
'NAME'
=>
'App template'
,
'DESCRIPTION'
=>
'Template was generated by rest application.'
,
'AUTO_EXECUTE'
=>
3
,
'TEMPLATE_DATA'
=> [
"bp-379.bpt"
,
"eNrlWNtO41YUfe9XRH5vlTiJhxj1IYkdYTU3Jeb2ZBkwg1UHU9t0BiFLhKk6rTq9aNSHqupF7RcwU1JSIOEXjv+oex/biZ04YWagIKYvcE7Ots9ea9+t8hx/aPOPeGZFbLWlRp1Z1Hl20eYXeEYWa81qURaZRZXP8Ic6n4ZFHsVzcHiwpzEgx3I809Y+29d2HV01Vk3r023DfFLcdPTPdecAJUC4rnaoML5U6+wZqkO3BZ6hgrDdwn2GZ9bp/zTPNC1zT7McXbPxehZvzcPTumPQRzkQIb+TodclF6RHTsmQvCYn3jGsL7wXZOB9Q/5JkVekT87IgPS87ofkyjsC+S9x43VH12hWR7dt3dzFaxbwGtBCwE2aP3TpToztWrFdO7aTY7vl2G41tlsLd65LaSnv6MaWpe3O5xovNDfrmlPTbFt9rM2gmYV1MZ9Oc2llocCxBYUrsByr5Atsnn073qlzZOA8uFDWnjpUMov8vwRGe+TS+z4FRhiSc3Likw/rHp86/Lh9YDtah6+bT6rmpmq4H0SeAMP1YPOa/j2JS4PgnyB27j3zvgajwutPqW2jYgIo7/qqjLSrmFZHpfqBdvQsPzpbtjWrYpmdCMHgRTyj7js7psUsurE3obRszpGN+mIW6CZ/AOgheQUK94CAPukhQnC3jyjQY9IPdRW3dMe0ymanAyEz0nXaC3znQPegZim2ijVRhhgduxGYcaXYkoqlqhj/tdyot+ViXY46JygsNMrLNbEuKxVJrAr0kE2jgVmekajLFwKHCx0pU8CTlPctDbJLhIZmCNwtdEsApftQUNOKbjiapW4gNxt8xo96BB3+lPZ/akHS0C10wNFPtX3D0ffGUkg5+mn0sZJqa9MXQ/4CRuHRp8xindoSo1GqicBDramsJYHLodl+9B0rRRMFBejbDz10PmrQZQt80NEDqt4EeubWoE/cnoi/1hAkMLWglNaT8GM2IT8jwgn0E0BhuQ/hcA8gIzcnAhSgOCnllhjUqCkDsxEDYzQCSEgk74V5QR0f+CzrYugG1o1Cv6Ft03diW8w6pWqj/ImSnJYwciEtgdcOvC8gyR6BFU+gsvcB54CWn7/IEKt/UJVulq8SrJq59XwFjxbLsrSS6MhZECc/QD2EMgIVc4Btj3fsvbjOh2G5YZrG/URuePO070JYlppKc7lUldpLYqKFWQzd36Ble0at2Acr0gYvyYFnQ0zfG8RMaE6l0mrUkhDmC9HqM4DFc2yfcHMyaWnSf9jZqjBiQ24kccHlo1wMqbEHlA8/Vb9/jICi7UZLTnQM7Kx/AqCntAXu+n3kEWLGAQY4OL8e/c1T3O23ZIgReljaVGcnqxW8l/wKdj7zoxwb6P8gQUcYggttx9J3HwfM2abl4OybCUDZmuPA6Xj6xN69vdRYVYqCoFQarVpscsoFh6IgyROn7gRrqBsmCP8XxRnnE58eP0MK2rYK2q+oxr4WmWgm6I6hmE5DEFfNlrgiiatKUyrLy63E8pLnqMed0fkFhjHy92iGASe8wAC8onPbaTBDd8HvhlCAjpIqzrZuaPeTjsObEytOyIMsrskzpwF/6oT88i7AnXA2vnPg4c3TwB/FgSvyetMPwPSkD2Qp/D65StGPKJQFzMZvyQM6pGZom6E+jT1HN3fHUTTB05jx4D07TscIlkt06d45oZMQRpTiJa4f64IoF6XqvKDKLbxRUD3AYMqM4M+KpSw3M5YeYAxxMbyzQyiXvz6E/uehk8NvU0LyjIMJ6Bf6AeKSjnF9aAB7QBd0O/gpF3vCU2ZODb/jRmd+5YXTtVp1xvjKItSX9LP0VzQlUHgX3nfe8wcC0HX/BTDK1SA="
]
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
'Error adding workflow template: '
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
'bizproc.workflow.template.add'
,
{
DOCUMENT_TYPE
: [
'lists'
,
'BizprocDocument'
,
'iblock_164'
],
NAME
:
'App template'
,
DESCRIPTION
:
'Template was generated by rest application.'
,
AUTO_EXECUTE
:
3
,
TEMPLATE_DATA
: [
"bp-379.bpt"
,
"eNrlWNtO41YUfe9XRH5vlTiJhxj1IYkdYTU3Jeb2ZBkwg1UHU9t0BiFLhKk6rTq9aNSHqupF7RcwU1JSIOEXjv+oex/biZ04YWagIKYvcE7Ots9ea9+t8hx/aPOPeGZFbLWlRp1Z1Hl20eYXeEYWa81qURaZRZXP8Ic6n4ZFHsVzcHiwpzEgx3I809Y+29d2HV01Vk3r023DfFLcdPTPdecAJUC4rnaoML5U6+wZqkO3BZ6hgrDdwn2GZ9bp/zTPNC1zT7McXbPxehZvzcPTumPQRzkQIb+TodclF6RHTsmQvCYn3jGsL7wXZOB9Q/5JkVekT87IgPS87ofkyjsC+S9x43VH12hWR7dt3dzFaxbwGtBCwE2aP3TpToztWrFdO7aTY7vl2G41tlsLd65LaSnv6MaWpe3O5xovNDfrmlPTbFt9rM2gmYV1MZ9Oc2llocCxBYUrsByr5Atsnn073qlzZOA8uFDWnjpUMov8vwRGe+TS+z4FRhiSc3Likw/rHp86/Lh9YDtah6+bT6rmpmq4H0SeAMP1YPOa/j2JS4PgnyB27j3zvgajwutPqW2jYgIo7/qqjLSrmFZHpfqBdvQsPzpbtjWrYpmdCMHgRTyj7js7psUsurE3obRszpGN+mIW6CZ/AOgheQUK94CAPukhQnC3jyjQY9IPdRW3dMe0ymanAyEz0nXaC3znQPegZim2ijVRhhgduxGYcaXYkoqlqhj/tdyot+ViXY46JygsNMrLNbEuKxVJrAr0kE2jgVmekajLFwKHCx0pU8CTlPctDbJLhIZmCNwtdEsApftQUNOKbjiapW4gNxt8xo96BB3+lPZ/akHS0C10wNFPtX3D0ffGUkg5+mn0sZJqa9MXQ/4CRuHRp8xindoSo1GqicBDramsJYHLodl+9B0rRRMFBejbDz10PmrQZQt80NEDqt4EeubWoE/cnoi/1hAkMLWglNaT8GM2IT8jwgn0E0BhuQ/hcA8gIzcnAhSgOCnllhjUqCkDsxEDYzQCSEgk74V5QR0f+CzrYugG1o1Cv6Ft03diW8w6pWqj/ImSnJYwciEtgdcOvC8gyR6BFU+gsvcB54CWn7/IEKt/UJVulq8SrJq59XwFjxbLsrSS6MhZECc/QD2EMgIVc4Btj3fsvbjOh2G5YZrG/URuePO070JYlppKc7lUldpLYqKFWQzd36Ble0at2Acr0gYvyYFnQ0zfG8RMaE6l0mrUkhDmC9HqM4DFc2yfcHMyaWnSf9jZqjBiQ24kccHlo1wMqbEHlA8/Vb9/jICi7UZLTnQM7Kx/AqCntAXu+n3kEWLGAQY4OL8e/c1T3O23ZIgReljaVGcnqxW8l/wKdj7zoxwb6P8gQUcYggttx9J3HwfM2abl4OybCUDZmuPA6Xj6xN69vdRYVYqCoFQarVpscsoFh6IgyROn7gRrqBsmCP8XxRnnE58eP0MK2rYK2q+oxr4WmWgm6I6hmE5DEFfNlrgiiatKUyrLy63E8pLnqMed0fkFhjHy92iGASe8wAC8onPbaTBDd8HvhlCAjpIqzrZuaPeTjsObEytOyIMsrskzpwF/6oT88i7AnXA2vnPg4c3TwB/FgSvyetMPwPSkD2Qp/D65StGPKJQFzMZvyQM6pGZom6E+jT1HN3fHUTTB05jx4D07TscIlkt06d45oZMQRpTiJa4f64IoF6XqvKDKLbxRUD3AYMqM4M+KpSw3M5YeYAxxMbyzQyiXvz6E/uehk8NvU0LyjIMJ6Bf6AeKSjnF9aAB7QBd0O/gpF3vCU2ZODb/jRmd+5YXTtVp1xvjKItSX9LP0VzQlUHgX3nfe8wcC0HX/BTDK1SA="
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
alert
(
"Error: "
+ result.
error
());
else
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
'bizproc.workflow.template.add'
,
[
'DOCUMENT_TYPE'
=> [
'lists'
,
'BizprocDocument'
,
'iblock_164'
],
'NAME'
=>
'App template'
,
'DESCRIPTION'
=>
'Template was generated by rest application.'
,
'AUTO_EXECUTE'
=>
3
,
'TEMPLATE_DATA'
=> [
"bp-379.bpt"
,
"eNrlWNtO41YUfe9XRH5vlTiJhxj1IYkdYTU3Jeb2ZBkwg1UHU9t0BiFLhKk6rTq9aNSHqupF7RcwU1JSIOEXjv+oex/biZ04YWagIKYvcE7Ots9ea9+t8hx/aPOPeGZFbLWlRp1Z1Hl20eYXeEYWa81qURaZRZXP8Ic6n4ZFHsVzcHiwpzEgx3I809Y+29d2HV01Vk3r023DfFLcdPTPdecAJUC4rnaoML5U6+wZqkO3BZ6hgrDdwn2GZ9bp/zTPNC1zT7McXbPxehZvzcPTumPQRzkQIb+TodclF6RHTsmQvCYn3jGsL7wXZOB9Q/5JkVekT87IgPS87ofkyjsC+S9x43VH12hWR7dt3dzFaxbwGtBCwE2aP3TpToztWrFdO7aTY7vl2G41tlsLd65LaSnv6MaWpe3O5xovNDfrmlPTbFt9rM2gmYV1MZ9Oc2llocCxBYUrsByr5Atsnn073qlzZOA8uFDWnjpUMov8vwRGe+TS+z4FRhiSc3Likw/rHp86/Lh9YDtah6+bT6rmpmq4H0SeAMP1YPOa/j2JS4PgnyB27j3zvgajwutPqW2jYgIo7/qqjLSrmFZHpfqBdvQsPzpbtjWrYpmdCMHgRTyj7js7psUsurE3obRszpGN+mIW6CZ/AOgheQUK94CAPukhQnC3jyjQY9IPdRW3dMe0ymanAyEz0nXaC3znQPegZim2ijVRhhgduxGYcaXYkoqlqhj/tdyot+ViXY46JygsNMrLNbEuKxVJrAr0kE2jgVmekajLFwKHCx0pU8CTlPctDbJLhIZmCNwtdEsApftQUNOKbjiapW4gNxt8xo96BB3+lPZ/akHS0C10wNFPtX3D0ffGUkg5+mn0sZJqa9MXQ/4CRuHRp8xindoSo1GqicBDramsJYHLodl+9B0rRRMFBejbDz10PmrQZQt80NEDqt4EeubWoE/cnoi/1hAkMLWglNaT8GM2IT8jwgn0E0BhuQ/hcA8gIzcnAhSgOCnllhjUqCkDsxEDYzQCSEgk74V5QR0f+CzrYugG1o1Cv6Ft03diW8w6pWqj/ImSnJYwciEtgdcOvC8gyR6BFU+gsvcB54CWn7/IEKt/UJVulq8SrJq59XwFjxbLsrSS6MhZECc/QD2EMgIVc4Btj3fsvbjOh2G5YZrG/URuePO070JYlppKc7lUldpLYqKFWQzd36Ble0at2Acr0gYvyYFnQ0zfG8RMaE6l0mrUkhDmC9HqM4DFc2yfcHMyaWnSf9jZqjBiQ24kccHlo1wMqbEHlA8/Vb9/jICi7UZLTnQM7Kx/AqCntAXu+n3kEWLGAQY4OL8e/c1T3O23ZIgReljaVGcnqxW8l/wKdj7zoxwb6P8gQUcYggttx9J3HwfM2abl4OybCUDZmuPA6Xj6xN69vdRYVYqCoFQarVpscsoFh6IgyROn7gRrqBsmCP8XxRnnE58eP0MK2rYK2q+oxr4WmWgm6I6hmE5DEFfNlrgiiatKUyrLy63E8pLnqMed0fkFhjHy92iGASe8wAC8onPbaTBDd8HvhlCAjpIqzrZuaPeTjsObEytOyIMsrskzpwF/6oT88i7AnXA2vnPg4c3TwB/FgSvyetMPwPSkD2Qp/D65StGPKJQFzMZvyQM6pGZom6E+jT1HN3fHUTTB05jx4D07TscIlkt06d45oZMQRpTiJa4f64IoF6XqvKDKLbxRUD3AYMqM4M+KpSw3M5YeYAxxMbyzQyiXvz6E/uehk8NvU0LyjIMJ6Bf6AeKSjnF9aAB7QBd0O/gpF3vCU2ZODb/jRmd+5YXTtVp1xvjKItSX9LP0VzQlUHgX3nfe8wcC0HX/BTDK1SA="
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
525
,
"time"
:
{
"start"
:
1737529740.157058
,
"finish"
:
1737529740.4302571
,
"duration"
:
0.27319908142089844
,
"processing"
:
0.25160598754882812
,
"date_start"
:
"2025-01-22T10:09:00+01:00"
,
"date_finish"
:
"2025-01-22T10:09:00+01:00"
,
"operating_reset_at"
:
1737530340
,
"operating"
:
0.25158905982971191
}
}
Returned Data
Returned Data
Name
type
Description
result
object
Identifier of the added business process template
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
"ERROR_TEMPLATE_VALIDATION_FAILURE"
,
"error_description"
:
"Incorrect field DOCUMENT_TYPE!"
,
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
Error Message
Description
ACCESS_DENIED
Application context required
Access token not from the application
ACCESS_DENIED
Access denied!
Method was not executed by an administrator
ERROR_TEMPLATE_VALIDATION_FAILURE
Incorrect field DOCUMENT_TYPE!
Incorrect document type specified
ERROR_TEMPLATE_VALIDATION_FAILURE
Empty template name!
Template name not specified
ERROR_TEMPLATE_VALIDATION_FAILURE
Incorrect field AUTO_EXECUTE!
Incorrect auto-execution code specified
ERROR_TEMPLATE_VALIDATION_FAILURE
Incorrect field TEMPLATE_DATA!
Incorrect template data specified
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
Business Process Templates: Overview of Methods
Update Business Process Template bizproc.workflow.template.update
Get the list of templates bizproc.workflow.template.list
Delete Business Process Template bizproc.workflow.template.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Template

---

## Update Business Process Template bizproc.workflow.template.update

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/template/bizproc-workflow-template-update

Update Business Process Template bizproc.workflow.template.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Business Process Template bizproc.workflow.template.update
Method Parameters
FIELDS Parameter
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method updates a business process template.
It allows you to update templates that were created using the
bizproc.workflow.template.add
method. These templates are tied to the application and can only be updated in the context of the same
application
that created them.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ID
*
string
Identifier of the template to be updated
FIELDS
*
object
Object with
fields
of the business process template.
You can update the fields:
NAME
,
DESCRIPTION
,
TEMPLATE_DATA
,
AUTO_EXECUTE
. Attempting to update
other fields
of the template will not result in errors, but those fields will not be updated
FIELDS Parameter
FIELDS Parameter
Name
type
Description
NAME
string
Name of the template
DESCRIPTION
string
Description of the template
TEMPLATE_DATA
file
Content of the file with the business process template in
.bpt
format.
More details on how to transfer files can be found in the article
How to Update and Delete Files
AUTO_EXECUTE
integer
Auto-execution settings for the template. Can have the following values:
0
— no auto-execution
1
— execute on creation
2
— execute on modification
3
— execute on creation and modification
Default is
0
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"ID":525,"FIELDS":{"NAME":"Display Time","DESCRIPTION":"Template shows a message with local and server time","AUTO_EXECUTE":0},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.workflow.template.update
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.workflow.template.update'
,
{
ID
:
525
,
FIELDS
: {
NAME
:
'Display Time'
,
DESCRIPTION
:
'Template shows a message with local and server time'
,
AUTO_EXECUTE
:
0
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
alert
(
"Error: "
+ error);
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
'bizproc.workflow.template.update'
,
[
'ID'
=>
525
,
'FIELDS'
=> [
'NAME'
=>
'Display Time'
,
'DESCRIPTION'
=>
'Template shows a message with local and server time'
,
'AUTO_EXECUTE'
=>
0
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
'Error updating workflow template: '
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
'bizproc.workflow.template.update'
,
{
ID
:
525
,
FIELDS
: {
NAME
:
'Display Time'
,
DESCRIPTION
:
'Template shows a message with local and server time'
,
AUTO_EXECUTE
:
0
,
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
alert
(
"Error: "
+ result.
error
());
else
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
'bizproc.workflow.template.update'
,
[
'ID'
=>
525
,
'FIELDS'
=> [
'NAME'
=>
'Display Time'
,
'DESCRIPTION'
=>
'Template shows a message with local and server time'
,
'AUTO_EXECUTE'
=>
0
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
525
,
"time"
:
{
"start"
:
1737534421.172673
,
"finish"
:
1737534421.209758
,
"duration"
:
0.037085056304931641
,
"processing"
:
0.010869026184082031
,
"date_start"
:
"2025-01-22T11:27:01+01:00"
,
"date_finish"
:
"2025-01-22T11:27:01+01:00"
,
"operating_reset_at"
:
1737535021
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
Identifier of the updated business process template
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
"ERROR_TEMPLATE_NOT_OWNER"
,
"error_description"
:
"You can update ONLY templates created by current application"
,
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
Error Message
Description
ACCESS_DENIED
Application context required
Access token not from the application
ACCESS_DENIED
Access denied!
Method was not executed by an administrator
ERROR_TEMPLATE_VALIDATION_FAILURE
No fields to update.
No fields specified for update
ERROR_TEMPLATE_NOT_FOUND
Workflow template not found.
Template with the specified
ID
not found
ERROR_TEMPLATE_NOT_OWNER
You can update ONLY templates created by current application
This template cannot be edited through this application
ERROR_TEMPLATE_VALIDATION_FAILURE
Empty template name!
Empty template name specified
ERROR_TEMPLATE_VALIDATION_FAILURE
Incorrect field AUTO_EXECUTE!
Invalid auto-execution code specified
ERROR_TEMPLATE_VALIDATION_FAILURE
Incorrect field TEMPLATE_DATA!
Invalid template data specified
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
Business Process Templates: Overview of Methods
Add Business Process Template bizproc.workflow.template.add
Get the list of templates bizproc.workflow.template.list
Delete Business Process Template bizproc.workflow.template.delete
Copied
Was the article helpful?
Yes
No
Previous
Add Template
Next
Get List of Templates

---

## Get the list of templates bizproc.workflow.template.list

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/template/bizproc-workflow-template-list

Get the list of templates bizproc.workflow.template.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of templates bizproc.workflow.template.list
Method Parameters
Template Fields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method retrieves a list of business process templates.
Method Parameters
Method Parameters
Name
type
Description
SELECT
array
The array contains a list of
fields
to select.
You can specify only the fields that are necessary.
Default value —
['ID']
FILTER
object
An object for filtering the list of business process templates in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field_N
—
field
of the template for filtering
value_N
— field value
You can specify the type of filtering before the name of the filtered field:
!
— not equal
<
— less than
<=
— less than or equal to
>
— greater than
>=
— greater than or equal to
ORDER
object
An object for sorting the list of launched business processes in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field_N
—
field
of the template for sorting
value_N
— sorting direction
Sorting direction can take the values:
asc
— ascending
desc
— descending
You can specify multiple fields for sorting, for example,
{NAME: 'ASC', ID: 'DESC'}
.
Default value —
{ID: 'ASC'}
start
integer
This parameter is used for managing pagination.
The page size of results is always static — 50 records.
To select the second page of results, you need to pass the value
50
. To select the third page of results — the value
100
, and so on.
The formula for calculating the
start
parameter value:
start = (N - 1) * 50
, where
N
— the number of the desired page
Template Fields
Template Fields
Name
type
Description
ID
integer
Identifier of the business process template
MODULE_ID
string
Identifier of the module by document. Possible values:
crm
— CRM
lists
— universal lists
disk
— drive
ENTITY
string
Identifier of the object by document. Possible values:
CRM
CCrmDocumentLead
— leads
CCrmDocumentContact
— contacts
CCrmDocumentCompany
— companies
CCrmDocumentDeal
— deals
Bitrix\Crm\Integration\BizProc\Document\Quote
— estimates
Bitrix\Crm\Integration\BizProc\Document\SmartInvoice
— invoices
Bitrix\Crm\Integration\BizProc\Document\Dynamic
— SPAs
Lists
BizprocDocument
— processes in the news feed
Bitrix\Lists\BizprocDocumentLists
— lists in groups
Drive
Bitrix\Disk\BizProcDocument
DOCUMENT_TYPE
integer
Document type. Possible values:
crm:
LEAD
— leads
CONTACT
— contacts
COMPANY
— companies
DEAL
— deals
QUOTE
— estimates
SMART_INVOICE
— invoices
DYNAMIC_XXX
— SPAs, where XXX — identifier of the SPA
lists:
iblock_XXX
— information block, where XXX — identifier of the information block
drive:
STORAGE_XXX
— drive storage, where XXX — identifier of the storage
AUTO_EXECUTE
integer
Auto-execute flag. Can take values:
0
— no auto-execute
1
— execute on creation
2
— execute on modification
3
— execute on creation and modification
NAME
string
Template name
TEMPLATE
array
Array with the description of the template's action structure
PARAMETERS
array
Template parameters
VARIABLES
array
Template variables
CONSTANTS
array
Template constants
MODIFIED
datetime
Date of last modification
IS_MODIFIED
boolean
Whether the template has been modified. Possible values:
Y
— yes, it has been modified
N
— no
This option is needed for
typical templates
of business processes
USER_ID
integer
Identifier of the user who created or modified the template
SYSTEM_CODE
string
System code of the template.
Needed for identifying typical business process templates or templates created by the application
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
'{"select":["ID","NAME","USER_ID","SYSTEM_CODE"],"filter":{"MODULE_ID":"lists","AUTO_EXECUTE":0},"order":{"ID":"DESC"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/bizproc.workflow.template.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"select":["ID","NAME","USER_ID","SYSTEM_CODE"],"filter":{"MODULE_ID":"lists","AUTO_EXECUTE":0},"order":{"ID":"DESC"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.workflow.template.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). This method loads all data at once, which can lead to high memory load when working with large volumes.
const
parameters = {
select
: [
'ID'
,
'NAME'
,
'USER_ID'
,
'SYSTEM_CODE'
],
filter
: {
MODULE_ID
:
'lists'
,
AUTO_EXECUTE
:
0
},
order
: {
ID
:
'DESC'
}
};
try
{
const
response =
await
$b24.
callListMethod
(
'bizproc.workflow.template.list'
, parameters);
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
// fetchListMethod is preferred when working with large datasets. This method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'bizproc.workflow.template.list'
, parameters,
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.workflow.template.list'
, parameters,
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
$result
=
$serviceBuilder
->
getBizProcScope
()
->
template
()
->
list
(
[
'ID'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_TYPE'
,
'AUTO_EXECUTE'
,
'NAME'
,
'TEMPLATE'
,
'PARAMETERS'
,
'VARIABLES'
,
'CONSTANTS'
,
'MODIFIED'
,
'IS_MODIFIED'
,
'USER_ID'
,
'SYSTEM_CODE'
],
[]
);
foreach
(
$result
->
getTemplates
()
as
$template
) {
print
(
"ID: "
.
$template
->ID .
"\n"
);
print
(
"MODULE_ID: "
.
$template
->MODULE_ID .
"\n"
);
print
(
"ENTITY: "
.
$template
->ENTITY .
"\n"
);
print
(
"DOCUMENT_TYPE: "
.
json_encode
(
$template
->DOCUMENT_TYPE) .
"\n"
);
print
(
"AUTO_EXECUTE: "
. (
$template
->AUTO_EXECUTE ?
$template
->AUTO_EXECUTE->value :
'null'
) .
"\n"
);
print
(
"NAME: "
.
$template
->NAME .
"\n"
);
print
(
"TEMPLATE: "
.
json_encode
(
$template
->TEMPLATE) .
"\n"
);
print
(
"PARAMETERS: "
.
json_encode
(
$template
->PARAMETERS) .
"\n"
);
print
(
"VARIABLES: "
.
json_encode
(
$template
->VARIABLES) .
"\n"
);
print
(
"CONSTANTS: "
.
json_encode
(
$template
->CONSTANTS) .
"\n"
);
print
(
"MODIFIED: "
. (
$template
->MODIFIED ?
$template
->MODIFIED->
format
(DATE_ATOM) :
'null'
) .
"\n"
);
print
(
"IS_MODIFIED: "
. (
$template
->IS_MODIFIED ?
'true'
:
'false'
) .
"\n"
);
print
(
"USER_ID: "
.
$template
->USER_ID .
"\n"
);
print
(
"SYSTEM_CODE: "
.
$template
->SYSTEM_CODE .
"\n"
);
print
(
"\n"
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
"Error: "
.
$e
->
getMessage
() .
"\n"
);
}
BX24
.
callMethod
(
'bizproc.workflow.template.list'
,
{
select
: [
'ID'
,
'NAME'
,
'USER_ID'
,
'SYSTEM_CODE'
],
filter
: {
MODULE_ID
:
'lists'
,
AUTO_EXECUTE
:
0
},
order
: {
ID
:
'DESC'
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
alert
(
"Error: "
+ result.
error
());
else
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
'bizproc.workflow.template.list'
,
[
'select'
=> [
'ID'
,
'NAME'
,
'USER_ID'
,
'SYSTEM_CODE'
],
'filter'
=> [
'MODULE_ID'
=>
'lists'
,
'AUTO_EXECUTE'
=>
0
],
'order'
=> [
'ID'
=>
'DESC'
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
"525"
,
"NAME"
:
"Display Time"
,
"USER_ID"
:
"503"
,
"SYSTEM_CODE"
:
"rest_app_5"
}
,
{
"ID"
:
"379"
,
...
}
...
]
,
"total"
:
34
,
"time"
:
{
"start"
:
1737535822.539526
,
"finish"
:
1737535822.564579
,
"duration"
:
0.025053024291992188
,
"processing"
:
0.0019738674163818359
,
"date_start"
:
"2025-01-22T11:50:22+02:00"
,
"date_finish"
:
"2025-01-22T11:50:22+02:00"
,
"operating_reset_at"
:
1737536422
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
The root element of the response.
Contains an array of objects with information about business process templates.
Each object contains
fields
of the template specified in the
SELECT
parameter
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
"Access denied!"
,
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
Error Message
Description
ACCESS_DENIED
Access denied!
The method was not executed by an administrator
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
Business Process Templates: Overview of Methods
Add Business Process Template bizproc.workflow.template.add
Update Business Process Template bizproc.workflow.template.update
Delete Business Process Template bizproc.workflow.template.delete
Copied
Was the article helpful?
Yes
No
Previous
Update Template
Next
Delete Template

---

## Delete Business Process Template bizproc.workflow.template.delete

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/template/bizproc-workflow-template-delete

Delete Business Process Template bizproc.workflow.template.delete | Bitrix24 REST API and Marketplace Applications
Delete Business Process Template bizproc.workflow.template.delete
Delete Business Process Template bizproc.workflow.template.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method deletes a business process template.
It allows you to remove templates that were created using the method
bizproc.workflow.template.add
. These templates are tied to the application and can only be deleted in the context of the same
application
in which they were created.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
ID
*
integer
Identifier of the business process template
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"ID":525,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.workflow.template.delete
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.workflow.template.delete'
,
{
ID
:
525
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
alert
(
"Error: "
+ result.
error
());
else
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
(
'Error:'
, error);
}
try
{
$templateId
=
123
;
// Replace with the actual template ID you want to delete
$result
=
$serviceBuilder
->
getBizProcScope
()
->
template
()
->
delete
(
$templateId
);
if
(
$result
->
isSuccess
()) {
print
(
"Template with ID
{$templateId}
deleted successfully.\n"
);
}
else
{
print
(
"Failed to delete template with ID
{$templateId}
.\n"
);
}
}
catch
(\
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
() .
"\n"
);
}
BX24
.
callMethod
(
'bizproc.workflow.template.delete'
,
{
ID
:
525
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
alert
(
"Error: "
+ result.
error
());
else
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
'bizproc.workflow.template.delete'
,
[
'ID'
=>
525
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
null
,
"time"
:
{
"start"
:
1737536737.1245451
,
"finish"
:
1737536737.3437879
,
"duration"
:
0.21924281120300293
,
"processing"
:
0.18391799926757812
,
"date_start"
:
"2025-01-22T12:05:37+02:00"
,
"date_finish"
:
"2025-01-22T12:05:37+02:00"
,
"operating_reset_at"
:
1737537337
,
"operating"
:
0.18389892578125
}
}
Returned Data
Returned Data
Name
type
Description
result
null
Returns
null
if the template is successfully deleted
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
"ERROR_TEMPLATE_NOT_FOUND"
,
"error_description"
:
"Workflow template not found."
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
Error Message
Description
ACCESS_DENIED
Application context required
Access token not from the application
ACCESS_DENIED
Access denied!
Method was not executed by an administrator
ERROR_TEMPLATE_NOT_FOUND
Workflow template not found.
Template with the specified
ID
not found
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
Business Process Templates: Overview of Methods
Add Business Process Template bizproc.workflow.template.add
Update Business Process Template bizproc.workflow.template.update
Get the list of templates bizproc.workflow.template.list
Copied
Was the article helpful?
Yes
No
Previous
Get List of Templates
Next
Overview of Methods

---

## Workflow Tasks: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-task/index

Workflow Tasks: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Workflow Tasks: Overview of Methods
Workflow Tasks: Overview of Methods
Complete Task
Delegate Task
Overview of Methods
Workflows can create tasks for participants to gather additional information from them. For example, a task can be used to approve a document in accounting, authorize a vacation with a manager, or request a contract from a lawyer. Users can see their tasks in Bitrix24 and receive notifications.
There are four types of tasks:
Document approval
Document acknowledgment
Request for additional information
Request for additional information with rejection
Quick navigation:
all methods and events
User documentation:
Workflow Tasks
Complete Task
Complete Task
You can complete a workflow task by its identifier using the
bizproc.task.complete
method. To obtain the task identifier
TASK_ID
, use the
bizproc.task.list
method. You can only complete your own tasks.
Tasks that request additional information contain fields that the user must fill out. To complete such a task, pass the field values in the
FIELDS
object in the format
{"field_1": "value_1", ... , "field_N": "value_N"}
field_N
— symbolic identifier of the task field
value_N
— field value
You can find out which fields need to be filled out from the response of the
bizproc.task.list
method. The object
"PARAMETERS": "Fields"
contains descriptions of all task fields.
Delegate Task
Delegate Task
A task can be delegated to another employee using the
bizproc.task.delegate
method. To do this, specify the task identifier
TASK_IDS
and the user identifiers:
current assignee
FROM_USER_ID
new assignee
TO_USER_ID
You can obtain the task identifier using the
bizproc.task.list
method, and the user identifier using the
user.get
method.
Overview of Methods
Overview of Methods
Scope:
bizproc
Who can execute the method: any user
Method
Description
bizproc.task.list
Retrieves a list of workflow tasks
bizproc.task.complete
Completes a workflow task
bizproc.task.delegate
Delegates a workflow task
Copied
Was the article helpful?
Yes
No
Previous
Delete Template
Next
Get Task List

---

## Get the list of workflow tasks bizproc.task.list

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-task/bizproc-task-list

Get the list of workflow tasks bizproc.task.list | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get the list of workflow tasks bizproc.task.list
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: any user
The method retrieves a list of workflow tasks.
An account administrator can request all tasks or tasks of any user. A regular user can request their own tasks or those of their subordinate.
To request their own tasks, the
USER_ID
filter does not need to be specified.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
SELECT
array
The array contains a list of
fields
to be selected.
Only the necessary fields can be specified.
By default, it returns the fields
ENTITY
,
DOCUMENT_ID
,
ID
,
WORKFLOW_ID
,
DOCUMENT_NAME
,
NAME
,
DOCUMENT_URL
FILTER
object
An object for filtering the list of tasks in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field_N
—
field
of the task for filtering
value_N
— field value
If
USER_ID
is present in the filter, user subordination is checked:
a manager can request the list of tasks of their subordinates
an administrator can request tasks of any users without restrictions
If the method is called by a non-administrator and the
USER_ID
filter is not specified, it defaults to selecting tasks of the current user
ORDER
object
An object for sorting the list of tasks in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field_N
—
field
of the task for sorting
value_N
— sorting direction
The sorting direction can take the following values:
asc
— ascending
desc
— descending
Multiple fields can be specified for sorting, for example,
{NAME: 'ASC', ID: 'DESC'}
START
integer
The parameter is used for managing pagination.
The page size of results is always static — 50 records.
To select the second page of results, the value
50
must be passed. To select the third page of results — the value
100
, and so on.
The formula for calculating the
start
parameter value:
start = (N - 1) * 50
, where
N
— the desired page number
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
'{"select":["ID","WORKFLOW_ID","DOCUMENT_NAME","DESCRIPTION","NAME","MODIFIED","WORKFLOW_STARTED","WORKFLOW_STARTED_BY","OVERDUE_DATE","WORKFLOW_TEMPLATE_ID","WORKFLOW_TEMPLATE_NAME","WORKFLOW_STATE","STATUS","USER_ID","USER_STATUS","MODULE_ID","ENTITY","DOCUMENT_ID","ACTIVITY","ACTIVITY_NAME","DOCUMENT_URL","PARAMETERS"],"order":{"ID":"DESC"},"filter":{"USER_ID":1,"STATUS":0,"ACTIVITY":"RequestInformationOptionalActivity"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/bizproc.task.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"select":["ID","WORKFLOW_ID","DOCUMENT_NAME","DESCRIPTION","NAME","MODIFIED","WORKFLOW_STARTED","WORKFLOW_STARTED_BY","OVERDUE_DATE","WORKFLOW_TEMPLATE_ID","WORKFLOW_TEMPLATE_NAME","WORKFLOW_STATE","STATUS","USER_ID","USER_STATUS","MODULE_ID","ENTITY","DOCUMENT_ID","ACTIVITY","ACTIVITY_NAME","DOCUMENT_URL","PARAMETERS"],"order":{"ID":"DESC"},"filter":{"USER_ID":1,"STATUS":0,"ACTIVITY":"RequestInformationOptionalActivity"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.task.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
const
parameters = {
select
: [
'ID'
,
'WORKFLOW_ID'
,
'DOCUMENT_NAME'
,
'DESCRIPTION'
,
'NAME'
,
'MODIFIED'
,
'WORKFLOW_STARTED'
,
'WORKFLOW_STARTED_BY'
,
'OVERDUE_DATE'
,
'WORKFLOW_TEMPLATE_ID'
,
'WORKFLOW_TEMPLATE_NAME'
,
'WORKFLOW_STATE'
,
'STATUS'
,
'USER_ID'
,
'USER_STATUS'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'ACTIVITY'
,
'ACTIVITY_NAME'
,
'DOCUMENT_URL'
,
'PARAMETERS'
],
order
: {
ID
:
'DESC'
},
filter
: {
'USER_ID'
:
1
,
'STATUS'
:
0
,
'ACTIVITY'
:
'RequestInformationOptionalActivity'
}
};
try
{
const
response =
await
$b24.
callListMethod
(
'bizproc.task.list'
, parameters);
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
const
parameters = {
select
: [
'ID'
,
'WORKFLOW_ID'
,
'DOCUMENT_NAME'
,
'DESCRIPTION'
,
'NAME'
,
'MODIFIED'
,
'WORKFLOW_STARTED'
,
'WORKFLOW_STARTED_BY'
,
'OVERDUE_DATE'
,
'WORKFLOW_TEMPLATE_ID'
,
'WORKFLOW_TEMPLATE_NAME'
,
'WORKFLOW_STATE'
,
'STATUS'
,
'USER_ID'
,
'USER_STATUS'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'ACTIVITY'
,
'ACTIVITY_NAME'
,
'DOCUMENT_URL'
,
'PARAMETERS'
],
order
: {
ID
:
'DESC'
},
filter
: {
'USER_ID'
:
1
,
'STATUS'
:
0
,
'ACTIVITY'
:
'RequestInformationOptionalActivity'
}
};
try
{
const
generator = $b24.
fetchListMethod
(
'bizproc.task.list'
, parameters,
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
const
parameters = {
select
: [
'ID'
,
'WORKFLOW_ID'
,
'DOCUMENT_NAME'
,
'DESCRIPTION'
,
'NAME'
,
'MODIFIED'
,
'WORKFLOW_STARTED'
,
'WORKFLOW_STARTED_BY'
,
'OVERDUE_DATE'
,
'WORKFLOW_TEMPLATE_ID'
,
'WORKFLOW_TEMPLATE_NAME'
,
'WORKFLOW_STATE'
,
'STATUS'
,
'USER_ID'
,
'USER_STATUS'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'ACTIVITY'
,
'ACTIVITY_NAME'
,
'DOCUMENT_URL'
,
'PARAMETERS'
],
order
: {
ID
:
'DESC'
},
filter
: {
'USER_ID'
:
1
,
'STATUS'
:
0
,
'ACTIVITY'
:
'RequestInformationOptionalActivity'
}
};
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.task.list'
, parameters,
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
'bizproc.task.list'
,
[
'select'
=> [
'ID'
,
'WORKFLOW_ID'
,
'DOCUMENT_NAME'
,
'DESCRIPTION'
,
'NAME'
,
'MODIFIED'
,
'WORKFLOW_STARTED'
,
'WORKFLOW_STARTED_BY'
,
'OVERDUE_DATE'
,
'WORKFLOW_TEMPLATE_ID'
,
'WORKFLOW_TEMPLATE_NAME'
,
'WORKFLOW_STATE'
,
'STATUS'
,
'USER_ID'
,
'USER_STATUS'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'ACTIVITY'
,
'ACTIVITY_NAME'
,
'DOCUMENT_URL'
,
'PARAMETERS'
],
'order'
=> [
'ID'
=>
'DESC'
],
'filter'
=> [
'USER_ID'
=>
1
,
'STATUS'
=>
0
,
'ACTIVITY'
=>
'RequestInformationOptionalActivity'
]
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
'Error: '
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
'bizproc.task.list'
,
{
select
: [
'ID'
,
'WORKFLOW_ID'
,
'DOCUMENT_NAME'
,
'DESCRIPTION'
,
'NAME'
,
'MODIFIED'
,
'WORKFLOW_STARTED'
,
'WORKFLOW_STARTED_BY'
,
'OVERDUE_DATE'
,
'WORKFLOW_TEMPLATE_ID'
,
'WORKFLOW_TEMPLATE_NAME'
,
'WORKFLOW_STATE'
,
'STATUS'
,
'USER_ID'
,
'USER_STATUS'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'ACTIVITY'
,
'ACTIVITY_NAME'
,
'DOCUMENT_URL'
,
'PARAMETERS'
],
order
: {
ID
:
'DESC'
},
filter
: {
'USER_ID'
:
1
,
'STATUS'
:
0
,
'ACTIVITY'
:
'RequestInformationOptionalActivity'
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
alert
(
"Error: "
+ result.
error
());
else
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
'bizproc.task.list'
,
[
'select'
=> [
'ID'
,
'WORKFLOW_ID'
,
'DOCUMENT_NAME'
,
'DESCRIPTION'
,
'NAME'
,
'MODIFIED'
,
'WORKFLOW_STARTED'
,
'WORKFLOW_STARTED_BY'
,
'OVERDUE_DATE'
,
'WORKFLOW_TEMPLATE_ID'
,
'WORKFLOW_TEMPLATE_NAME'
,
'WORKFLOW_STATE'
,
'STATUS'
,
'USER_ID'
,
'USER_STATUS'
,
'MODULE_ID'
,
'ENTITY'
,
'DOCUMENT_ID'
,
'ACTIVITY'
,
'ACTIVITY_NAME'
,
'DOCUMENT_URL'
,
'PARAMETERS'
],
'order'
=> [
'ID'
=>
'DESC'
],
'filter'
=> [
'USER_ID'
=>
1
,
'STATUS'
=>
0
,
'ACTIVITY'
=>
'RequestInformationOptionalActivity'
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
"ENTITY"
:
"BizprocDocument"
,
"DOCUMENT_ID"
:
"2249"
,
"ID"
:
"1477"
,
"WORKFLOW_ID"
:
"67a2ffdb2c57a3.35276854"
,
"DOCUMENT_NAME"
:
"Partner Conference"
,
"DESCRIPTION"
:
""
,
"NAME"
:
"Add contractor information"
,
"MODIFIED"
:
"2025-02-05T09:06:19+02:00"
,
"WORKFLOW_STARTED"
:
"2025-02-05T09:06:19+02:00"
,
"WORKFLOW_STARTED_BY"
:
"1"
,
"OVERDUE_DATE"
:
null
,
"WORKFLOW_TEMPLATE_ID"
:
"565"
,
"WORKFLOW_TEMPLATE_NAME"
:
"Event Organization"
,
"WORKFLOW_STATE"
:
"Waiting for additional information"
,
"STATUS"
:
"0"
,
"USER_ID"
:
"1"
,
"USER_STATUS"
:
"0"
,
"MODULE_ID"
:
"lists"
,
"ACTIVITY"
:
"RequestInformationActivity"
,
"ACTIVITY_NAME"
:
"A3651_68033_56029_16413"
,
"PARAMETERS"
:
{
"CommentLabel"
:
"Comment"
,
"CommentRequired"
:
"Y"
,
"ShowComment"
:
"Y"
,
"StatusOkLabel"
:
"Save result"
,
"Fields"
:
[
{
"Id"
:
"contractor"
,
"Type"
:
"E:ECrm"
,
"Name"
:
"Contractor"
,
"Description"
:
"Who performs the work"
,
"Multiple"
:
false
,
"Required"
:
true
,
"Options"
:
{
"LEAD"
:
"N"
,
"CONTACT"
:
"Y"
,
"COMPANY"
:
"Y"
,
"DEAL"
:
"N"
,
"SMART_INVOICE"
:
"N"
,
"DYNAMIC_136"
:
"N"
,
"DYNAMIC_1038"
:
"N"
}
,
"Settings"
:
null
,
"Default"
:
[
"C_607"
]
}
,
{
"Id"
:
"phone_number"
,
"Type"
:
"string"
,
"Name"
:
"Phone number"
,
"Description"
:
""
,
"Multiple"
:
false
,
"Required"
:
true
,
"Options"
:
null
,
"Settings"
:
null
,
"Default"
:
""
}
]
}
,
"DOCUMENT_URL"
:
"/bizproc/processes/?livefeed=y&list_id=171&element_id=2249"
}
,
{
"ENTITY"
:
"BizprocDocument"
,
"DOCUMENT_ID"
:
"2237"
,
"ID"
:
"1471"
,
...
}
]
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
1738735796.4730229
,
"finish"
:
1738735796.510215
,
"duration"
:
0.037192106246948242
,
"processing"
:
0.0080459117889404297
,
"date_start"
:
"2025-02-05T09:09:56+02:00"
,
"date_finish"
:
"2025-02-05T09:09:56+02:00"
,
"operating_reset_at"
:
1738736396
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
The root element of the response.
Contains an array of objects with information about workflow tasks.
Each object contains
fields
of the task specified in the
SELECT
parameter
total
integer
The total number of records found
time
time
Information about the query execution time
Task Fields
Task Fields
Name
type
Description
ID
integer
Task identifier
WORKFLOW_ID
integer
Workflow identifier
DOCUMENT_NAME
string
Document name
DESCRIPTION
string
Task description
NAME
string
Task name
MODIFIED
datetime
Modification date
WORKFLOW_STARTED
datatime
Workflow start date
WORKFLOW_STARTED_BY
user
Who started the workflow
OVERDUE_DATE
datetime
Deadline
WORKFLOW_TEMPLATE_ID
integer
Workflow template identifier
WORKFLOW_TEMPLATE_NAME
string
Workflow template name
WORKFLOW_STATE
string
Workflow status
STATUS
integer
Task status. Possible values:
0
— in progress
1
— approved
2
— rejected
3
— completed
4
— overdue
USER_ID
user
User identifier
USER_STATUS
integer
User response. Possible values:
0
— awaiting response
1
— approved
2
— rejected
3
— completed
MODULE_ID
string
Module identifier by document
ENTITY
string
Symbolic identifier of the object by document
DOCUMENT_ID
integer
Document identifier
ACTIVITY
string
Task type identifier. Possible values:
ApproveActivity
— document approval
ReviewActivity
— document review
RequestInformationActivity
— request for additional information
RequestInformationOptionalActivity
— request for additional information (with rejection)
ACTIVITY_NAME
string
Action identifier in the template
PARAMETERS
object
An object describing the
task parameters
DOCUMENT_URL
object
Link to the document
PARAMETERS Object
PARAMETERS Object
Name
type
Description
CommentLabel
string
Name of the Comment field
CommentRequired
string
Comment requirement. Allowed values:
N
— no
Y
— yes
YA
— yes, upon approval
YR
— yes, upon rejection
ShowComment
boolean
Show comment. Allowed values:
N
— no
Y
— yes
StatusOkLabel
string
Text of the Acknowledged button
StatusYesLabel
string
Text of the Approve button
StatusNoLabel
string
Text of the Reject button
Fields
array
An array of objects. Each object contains a description of the
field in the task
Fields Object
Fields Object
Name
type
Description
Id
string
Symbolic identifier of the task parameter
Type
string
Parameter type. Basic values:
bool
— yes or no
date
— date
datetime
— date and time
double
— number
int
— integer
select
— list
string
— string
text
— text
user
— user
Other types depend on the document with which the workflow operates
Name
string
|
object
Name of the parameter
Description
string
|
object
Description of the parameter
Multiple
boolean
Parameter multiplicity. Possible values:
true
— yes
false
— no
Required
boolean
Parameter requirement. Possible values:
true
— yes
false
— no
Options
object
Field settings.
Values depend on the parameter type. Examples:
for the List type
select
, these are the options of the list
"Options"
:
{
"1"
:
"First option"
,
"2"
:
"Second option"
,
"3"
:
"Third option"
,
}
,
for the CRM Binding type
'E:ECrm'
, these are the available object types
"Options"
:
{
"LEAD"
:
"N"
,
"CONTACT"
:
"Y"
,
"COMPANY"
:
"Y"
,
"DEAL"
:
"N"
,
"SMART_INVOICE"
:
"N"
,
"DYNAMIC_136"
:
"N"
,
"DYNAMIC_1038"
:
"N"
}
,
Settings
object
Additional field settings
Default
any
Default parameter value
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
"Access denied!"
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
Error Message
Description
ACCESS_DENIED
Access denied!
The method was not initiated by an administrator or you cannot view the tasks of the specified employee
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
Workflow Tasks: Overview of Methods
Complete a business process task bizproc.task.complete
Delegate a workflow task bizproc.task.delegate
How to Complete Business Processes of a Terminated Employee
How to Mass Finish Workflows with Date Filter
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Complete Workflow Task

---

## Complete a business process task bizproc.task.complete

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-task/bizproc-task-complete

Complete a business process task bizproc.task.complete | Bitrix24 REST API and Marketplace Applications
Complete a business process task bizproc.task.complete
Complete a business process task bizproc.task.complete
Method parameters
Code example
Response handling
Returned data
Error handling
Possible error codes
Statuses and System Error Codes
Continue learning
Scope:
bizproc
Who can execute the method: any user
This method completes a business process task:
Document approval
Document acknowledgment
Request for additional information
Request for additional information with rejection
You can only complete your own task.
User documentation
Actions: Tasks
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
TASK_ID
*
integer
Task identifier.
You can obtain the identifier using the
bizproc.task.list
method.
STATUS
*
integer
|
string
Target status of the task. Possible values:
1
or
yes
— yes, approved
2
or
no
— no, rejected
3
or
ok
— ok, acknowledged
4
or
cancel
— cancellation
The set of acceptable values changes depending on the type of task:
Document approval —
1
or
2
Document acknowledgment —
3
Request for additional information —
3
Request for additional information with rejection —
3
or
4
COMMENT
string
User comment.
The requirement for this parameter depends on the task settings.
FIELDS
object
An object describing fields for completing tasks with a request for additional information in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field_N
— symbolic identifier of the task field
value_N
— value of the field
You can obtain field descriptions in the task using the
bizproc.task.list
method in the object
"PARAMETERS": "Fields"
of the response. The structure of the field object description:
"PARAMETERS"
:
{
...
"Fields"
:
[
{
"Id"
:
"field_id"
,
"Type"
:
"type"
,
"Name"
:
"name"
,
"Description"
:
"description"
,
"Multiple"
:
false
,
"Required"
:
true
,
"Options"
:
null
,
"Settings"
:
null
,
"Default"
:
"default_value"
}
Id
— symbolic identifier of the task field.
The
Default
contains default values that can be passed for task completion. These values are converted to an external representation:
for dates — in the rest ATOM ISO-8601 format
for files — as a link to the file
Values are passed in this format to the
bizproc.task.complete
method. They are then converted to an internal representation:
dates from the rest format are converted to internal format
files are saved and attached to the business process
To pass a value in a File type field, specify:
for File type — base64 or an array with the name and base64
for File type (Drive) — file identifier from Drive
More about working with files can be found in the article
How to Upload Files
Code example
Code example
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
'{"TASK_ID":1501,"STATUS":1,"COMMENT":"Added","Fields":{"contractor":"C_607","phone_number":"+19991234567"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/bizproc.task.complete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"TASK_ID":1501,"STATUS":1,"COMMENT":"Added","Fields":{"contractor":"C_607","phone_number":"+19991234567"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.task.complete
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.task.complete'
,
{
'TASK_ID'
:
1501
,
'STATUS'
:
1
,
'COMMENT'
:
'Added'
,
"Fields"
: {
'contractor'
:
'C_607'
,
'phone_number'
:
'+19991234567'
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
alert
(
"Error: "
+ error);
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
'bizproc.task.complete'
,
[
'TASK_ID'
=>
1501
,
'STATUS'
=>
1
,
'COMMENT'
=>
'Added'
,
'Fields'
=> [
'contractor'
=>
'C_607'
,
'phone_number'
=>
'+19991234567'
]
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
'Error completing task: '
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
'bizproc.task.complete'
,
{
'TASK_ID'
:
1501
,
'STATUS'
:
1
,
'COMMENT'
:
'Added'
,
"Fields"
: {
'contractor'
:
'C_607'
,
'phone_number'
:
'+19991234567'
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
alert
(
"Error: "
+ result.
error
());
else
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
'bizproc.task.complete'
,
[
'TASK_ID'
=>
1501
,
'STATUS'
=>
1
,
'COMMENT'
=>
'Added'
,
'Fields'
=> [
'contractor'
=>
'C_607'
,
'phone_number'
=>
'+19991234567'
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
Response handling
Response handling
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
1738746693.9218969
,
"finish"
:
1738746694.1367991
,
"duration"
:
0.21490216255187988
,
"processing"
:
0.19237995147705078
,
"date_start"
:
"2025-02-05T12:11:33+01:00"
,
"date_finish"
:
"2025-02-05T12:11:34+01:00"
,
"operating_reset_at"
:
1738747293
,
"operating"
:
0.19236207008361816
}
}
Returned data
Returned data
Name
type
Description
result
boolean
Returns
true
if the task was completed successfully.
time
time
Information about the request execution time.
Error handling
Error handling
HTTP status:
400
{
"error"
:
"ERROR_TASK_VALIDATION"
,
"error_description"
:
"incorrect STATUS"
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
Possible error codes
Possible error codes
Code
Error message
Description
ERROR_TASK_VALIDATION
empty TASK_ID
ID
of the task is not specified.
ERROR_TASK_VALIDATION
incorrect STATUS
An incorrect task status is specified.
ERROR_TASK_NOT_FOUND
Task not found
No task found with the specified
ID
.
ERROR_TASK_COMPLETED
Task already completed
The task has already been completed.
ERROR_TASK_TYPE
Incorrect task type
Incorrect task type. This task cannot be completed via REST.
ERROR_TASK_EXECUTION
error text from the task
An error occurred during the execution of the task.
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
Continue learning
Continue learning
Workflow Tasks: Overview of Methods
Get the list of workflow tasks bizproc.task.list
Delegate a workflow task bizproc.task.delegate
Copied
Was the article helpful?
Yes
No
Previous
Get Task List
Next
Delegate Workflow Task

---

## Delegate a workflow task bizproc.task.delegate

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-task/bizproc-task-delegate

Delegate a workflow task bizproc.task.delegate | Bitrix24 REST API and Marketplace Applications
Delegate a workflow task bizproc.task.delegate
Delegate a workflow task bizproc.task.delegate
Method parameters
Code examples
Response handling
Returned data
Error handling
Possible error codes
Statuses and System Error Codes
Continue exploring
Scope:
bizproc
Who can execute the method: any user responsible for the workflow task
This method delegates a workflow task. You can only delegate your own task.
User documentation
Actions: Tasks
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
TASK_IDS
*
array
List of task identifiers.
You can obtain identifiers using the
bizproc.task.list
method.
FROM_USER_ID
*
integer
Identifier of the user from whom the tasks will be delegated.
You can obtain the user identifier using the
user.get
method.
TO_USER_ID
*
integer
Identifier of the user to whom the tasks will be delegated.
You can obtain the user identifier using the
user.get
method.
Who you can delegate to depends on the task settings: only subordinates, all employees, or no one.
Code examples
Code examples
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
'{"TASK_IDS":[1128,1129,1130],"FROM_USER_ID":15,"TO_USER_ID":37}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/bizproc.task.delegate
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"TASK_IDS":[1128,1129,1130],"FROM_USER_ID":15,"TO_USER_ID":37,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.task.delegate
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.task.delegate'
,
{
TASK_IDS
: [
1128
,
1129
,
1130
],
FROM_USER_ID
:
15
,
TO_USER_ID
:
37
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
(
'Delegated tasks:'
, result);
processResult
(result);
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
'bizproc.task.delegate'
,
[
'TASK_IDS'
=> [
1128
,
1129
,
1130
],
'FROM_USER_ID'
=>
15
,
'TO_USER_ID'
=>
37
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
'Error delegating task: '
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
'bizproc.task.delegate'
,
{
'TASK_IDS'
: [
1128
,
1129
,
1130
],
'FROM_USER_ID'
:
15
,
'TO_USER_ID'
:
37
,
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
alert
(
"Error: "
+ result.
error
());
else
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
'bizproc.task.delegate'
,
[
'TASK_IDS'
=> [
1128
,
1129
,
1130
],
'FROM_USER_ID'
=>
15
,
'TO_USER_ID'
=>
37
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
Response handling
Response handling
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
1748526089.625516
,
"finish"
:
1748526089.656787
,
"duration"
:
0.03127098083496094
,
"processing"
:
0.008746147155761719
,
"date_start"
:
"2025-05-29T16:41:29+02:00"
,
"date_finish"
:
"2025-05-29T16:41:29+02:00"
,
"operating_reset_at"
:
1748526689
,
"operating"
:
0
}
}
Returned data
Returned data
Name
type
Description
result
boolean
Returns
true
if the task was successfully delegated.
time
time
Information about the request execution time.
Error handling
Error handling
HTTP status:
400
{
"error"
:
"ERROR_INVALID_USER_ID"
,
"error_description"
:
"Invalid FROM_USER_ID"
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
Possible error codes
Possible error codes
Code
Error message
Description
ERROR_TASK_VALIDATION
Invalid TASK_IDS
Invalid task identifiers or the
TASK_IDS
parameter was not provided.
ERROR_INVALID_USER_ID
Invalid FROM_USER_ID
Invalid or missing user identifier from whom the delegation is made.
ERROR_INVALID_USER_ID
Invalid TO_USER_ID
Invalid or missing user identifier to whom the delegation is made.
ERROR_DELEGATION_NOT_ALLOWED
User is not responsible for the task
The user specified in the
FROM_USER_ID
parameter is not responsible for the task.
ERROR_DELEGATION_NOT_ALLOWED
Task delegation is only available for intranet users
The user specified in the
TO_USER_ID
parameter is not an intranet user.
ERROR_DELEGATION_NOT_ALLOWED
List of errors separated by
;
The method can accept multiple tasks. If errors occur in multiple tasks, they will be returned as a list separated by
;
.
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
Continue exploring
Continue exploring
Workflow Tasks: Overview of Methods
Get the list of workflow tasks bizproc.task.list
Complete a business process task bizproc.task.complete
Copied
Was the article helpful?
Yes
No
Previous
Complete Workflow Task
Next
Overview of Methods

---

## Application Actions: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-activity/index

Application Actions: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Application Actions: Overview of Methods
Application Actions: Overview of Methods
Method
Description
bizproc.activity.add
Adds a new action for use in workflows
bizproc.activity.update
Updates an action
bizproc.activity.list
Retrieves a list of actions installed by the application
bizproc.activity.delete
Deletes an action installed by the application
bizproc.activity.log
Records information in the workflow log
Was the article helpful?
Yes
No
Previous
Delegate Workflow Task
Next
Add New Action

---

## Add a New Action bizproc.activity.add

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-activity/bizproc-activity-add

Add a New Action bizproc.activity.add | Bitrix24 REST API and Marketplace Applications
Add a New Action bizproc.activity.add
Add a New Action bizproc.activity.add
Method Parameters
PROPERTY Object
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
Adds a new action for use in workflows.
The method works only in the context of the
application
.
Each document generates its own set of field types. For example, in CRM, there is a field of type Address
UF:address
. To use this field type in your actions, specify the CRM document type in
DOCUMENT_TYPE
and describe the field properties in
PROPERTIES
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
CODE
*
string
Internal identifier of the action. It must be unique within the application.
Allowed characters are
a-z
,
A-Z
,
0-9
, dot, hyphen, and underscore
_
HANDLER
*
string
URL to which the action will send data via the Bitrix24 queue server.
The link must have the same domain where the application is installed
AUTH_USER_ID
integer
Identifier of the user whose token will be passed to the application
USE_SUBSCRIPTION
boolean
Should the action wait for a response from the application? Possible values:
Y
— yes
N
— no
NAME
*
string
|
object
Name of the action.
It can be a string or an associative array of localized strings like:
'NAME'
: {
'de'
:
'Aktionsname'
,
'en'
:
'action name'
,
...
},
DESCRIPTION
string
|
object
Description of the action.
It can be a string or an associative array of localized strings like:
'DESCRIPTION'
: {
'de'
:
'Aktionsbeschreibung'
,
'en'
:
'action description'
,
...
},
PROPERTIES
object
An object with action parameters. Contains objects, each describing a
parameter of the action
.
The system name of the parameter must start with a letter and can contain characters
a-z
,
A-Z
,
0-9
, and underscore
_
RETURN_PROPERTIES
object
An object with additional results of the action. Contains objects, each describing a
parameter of the action
.
This parameter controls whether the action can wait for a response from the application and work with the data that will
come in the response
.
The system name of the parameter must start with a letter and can contain characters
a-z
,
A-Z
,
0-9
, and underscore
_
DOCUMENT_TYPE
array
Document type that will determine the data types for the
PROPERTIES
and
RETURN_PROPERTIES
parameters. Consists of three string-type elements:
module identifier
object identifier
document type
Possible value options:
CRM Module
['crm', 'CCrmDocumentLead', 'LEAD']
— leads
['crm', 'CCrmDocumentContact', 'CONTACT']
— contacts
['crm', 'CCrmDocumentCompany', 'COMPANY']
— companies
['crm', 'CCrmDocumentDeal', 'DEAL']
— deals
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Quote', 'QUOTE']
— estimates
['crm', 'Bitrix\Crm\Integration\BizProc\Document\SmartInvoice', 'SMART_INVOICE']
— invoices
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Dynamic', 'DYNAMIC_XXX']
— SPAs, where XXX is the identifier of the SPA
Lists Module
['lists', 'BizprocDocument', 'iblock_XXX']
— processes in the news feed, where XXX is the identifier of the information block
['lists', 'Bitrix\Lists\BizprocDocumentLists', 'iblock_XXX']
— lists in groups, where XXX is the identifier of the information block
Drive Module
['disk', 'Bitrix\Disk\BizProcDocument', 'STORAGE_XXX']
, where XXX is the storage identifier
FILTER
object
An object with rules to limit the action by document type and edition.
It can contain keys:
INCLUDE
— an array of rules where the action will be displayed
EXCLUDE
— an array of rules where the action will be hidden
Each rule in the array can be a string or an array of document types in full or partial form.
To limit the action by Bitrix24 edition, specify:
b24
— for cloud
box
— for on-premise
Examples:
Exclude the action for on-premise Bitrix24
FILTER
: {
EXCLUDE
: [
'box'
]
}
Display the action only for the Lists module
FILTER
: {
INCLUDE
: [
[
'lists'
]
]
}
Display the action only for the Lists module and deals from CRM
FILTER
: {
INCLUDE
: [
[
'lists'
],
[
'crm'
,
'CCrmDocumentDeal'
]
]
}
USE_PLACEMENT
boolean
Allows opening additional settings for the action in the application slider. Possible values:
Y
— yes
N
— no
PLACEMENT_HANDLER
*
string
URL of the placement handler on the application side. Required if
USE_PLACEMENT = 'Y'
PROPERTY Object
PROPERTY Object
Name
type
Description
Name
string
|
object
Name of the parameter
Description
string
|
object
Description of the parameter
Type
string
Type of the parameter. Basic values:
bool
— yes or no
date
— date
datetime
— date and time
double
— number
int
— integer
select
— list
string
— string
text
— text
user
— user
Options
array
Array of values for the parameter of type list
'TYPE': select'
like:
[
'value1'
:
'title1'
,
'value2'
:
'title2'
,
'value3'
:
'title3'
,
'value4'
:
'title4'
]
Required
boolean
Whether the parameter is required. Possible values:
Y
— yes
N
— no
Multiple
boolean
Whether the parameter can have multiple values. Possible values:
Y
— yes
N
— no
Default
any
Default value of the parameter
Example Objects
Example Objects
// example for select type
'docType'
: {
'Name'
: {
'de'
:
'Dokumenttyp'
,
'en'
:
'Document type'
},
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'PDF'
,
'Type'
:
'select'
,
'Options'
: {
'pdf'
:
'PDF'
,
'docx'
:
'DOCX'
}
}
// example for bool type
'saveDoc'
: {
'Name'
: {
'de'
:
'Dokument speichern'
,
'en'
:
'Save document'
},
'Description'
: {
'de'
:
'Ordnungsnummer zuweisen'
,
'en'
:
'Assign a sequential number'
},
'Type'
:
'bool'
,
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'Y'
}
// example for string type
'Parameters'
: {
'Name'
: {
'de'
:
'Vorlagenparameter'
,
'en'
:
'Template\'s parameters'
},
'Description'
: {
'de'
:
'ParamID={=ParamValue}'
,
'en'
:
'ParamID={=ParamValue}'
},
'Type'
:
'string'
,
'Required'
:
'N'
,
'Multiple'
:
'Y'
}
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"CODE":"md5_action","HANDLER":"https://your_domain/ping.php","AUTH_USER_ID":1,"USE_SUBSCRIPTION":"Y","NAME":{"de":"MD5 Generator","en":"MD5 generator"},"DESCRIPTION":{"de":"Die Aktion gibt den MD5-Hash des Eingabeparameters zurück","en":"Activity returns MD5 hash of input parameter"},"PROPERTIES":{"inputString":{"Name":{"de":"Eingabestring","en":"Input string"},"Description":{"de":"Geben Sie den String ein, den Sie hashen möchten","en":"Input string for hashing"},"Type":"string","Required":"Y","Multiple":"N","Default":"{=Document:NAME}"}},"RETURN_PROPERTIES":{"outputString":{"Name":{"de":"MD5","en":"MD5"},"Type":"string","Multiple":"N","Default":null}},"DOCUMENT_TYPE":["lists","BizprocDocument","iblock_164"],"FILTER":{"INCLUDE":[["lists"]]},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.activity.add
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.activity.add'
,
{
'CODE'
:
'md5_action'
,
'HANDLER'
:
'https://your_domain/ping.php'
,
'AUTH_USER_ID'
:
1
,
'USE_SUBSCRIPTION'
:
'Y'
,
'NAME'
: {
'de'
:
'MD5 Generator'
,
'en'
:
'MD5 generator'
},
'DESCRIPTION'
: {
'de'
:
'Die Aktion gibt den MD5-Hash des Eingabeparameters zurück'
,
'en'
:
'Activity returns MD5 hash of input parameter'
},
'PROPERTIES'
: {
'inputString'
: {
'Name'
: {
'de'
:
'Eingabestring'
,
'en'
:
'Input string'
},
'Description'
: {
'de'
:
'Geben Sie den String ein, den Sie hashen möchten'
,
'en'
:
'Input string for hashing'
},
'Type'
:
'string'
,
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'{=Document:NAME}'
}
},
'RETURN_PROPERTIES'
: {
'outputString'
: {
'Name'
: {
'de'
:
'MD5'
,
'en'
:
'MD5'
},
'Type'
:
'string'
,
'Multiple'
:
'N'
,
'Default'
:
null
}
},
'DOCUMENT_TYPE'
: [
'lists'
,
'BizprocDocument'
,
'iblock_164'
],
'FILTER'
: {
INCLUDE
: [
[
'lists'
]
]
}
}
);
const
result = response.
getData
().
result
;
alert
(
"Success: "
+ result);
}
catch
( error )
{
alert
(
"Error: "
+ error);
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
'bizproc.activity.add'
,
[
'CODE'
=>
'md5_action'
,
'HANDLER'
=>
'https://your_domain/ping.php'
,
'AUTH_USER_ID'
=>
1
,
'USE_SUBSCRIPTION'
=>
'Y'
,
'NAME'
=> [
'de'
=>
'MD5 Generator'
,
'en'
=>
'MD5 generator'
],
'DESCRIPTION'
=> [
'de'
=>
'Die Aktion gibt den MD5-Hash des Eingabeparameters zurück'
,
'en'
=>
'Activity returns MD5 hash of input parameter'
],
'PROPERTIES'
=> [
'inputString'
=> [
'Name'
=> [
'de'
=>
'Eingabestring'
,
'en'
=>
'Input string'
],
'Description'
=> [
'de'
=>
'Geben Sie den String ein, den Sie hashen möchten'
,
'en'
=>
'Input string for hashing'
],
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
'{=Document:NAME}'
]
],
'RETURN_PROPERTIES'
=> [
'outputString'
=> [
'Name'
=> [
'de'
=>
'MD5'
,
'en'
=>
'MD5'
],
'Type'
=>
'string'
,
'Multiple'
=>
'N'
,
'Default'
=>
null
]
],
'DOCUMENT_TYPE'
=> [
'lists'
,
'BizprocDocument'
,
'iblock_164'
],
'FILTER'
=> [
'INCLUDE'
=> [
[
'lists'
]
]
]
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
'Error: '
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
'bizproc.activity.add'
,
{
'CODE'
:
'md5_action'
,
'HANDLER'
:
'https://your_domain/ping.php'
,
'AUTH_USER_ID'
:
1
,
'USE_SUBSCRIPTION'
:
'Y'
,
'NAME'
: {
'de'
:
'MD5 Generator'
,
'en'
:
'MD5 generator'
},
'DESCRIPTION'
: {
'de'
:
'Die Aktion gibt den MD5-Hash des Eingabeparameters zurück'
,
'en'
:
'Activity returns MD5 hash of input parameter'
},
'PROPERTIES'
: {
'inputString'
: {
'Name'
: {
'de'
:
'Eingabestring'
,
'en'
:
'Input string'
},
'Description'
: {
'de'
:
'Geben Sie den String ein, den Sie hashen möchten'
,
'en'
:
'Input string for hashing'
},
'Type'
:
'string'
,
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'{=Document:NAME}'
}
},
'RETURN_PROPERTIES'
: {
'outputString'
: {
'Name'
: {
'de'
:
'MD5'
,
'en'
:
'MD5'
},
'Type'
:
'string'
,
'Multiple'
:
'N'
,
'Default'
:
null
}
},
'DOCUMENT_TYPE'
: [
'lists'
,
'BizprocDocument'
,
'iblock_164'
],
'FILTER'
: {
INCLUDE
: [
[
'lists'
]
]
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
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Success: "
+ result.
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
'bizproc.activity.add'
,
[
'CODE'
=>
'md5_action'
,
'HANDLER'
=>
'https://your_domain/ping.php'
,
'AUTH_USER_ID'
=>
1
,
'USE_SUBSCRIPTION'
=>
'Y'
,
'NAME'
=> [
'de'
=>
'MD5 Generator'
,
'en'
=>
'MD5 generator'
],
'DESCRIPTION'
=> [
'de'
=>
'Die Aktion gibt den MD5-Hash des Eingabeparameters zurück'
,
'en'
=>
'Activity returns MD5 hash of input parameter'
],
'PROPERTIES'
=> [
'inputString'
=> [
'Name'
=> [
'de'
=>
'Eingabestring'
,
'en'
=>
'Input string'
],
'Description'
=> [
'de'
=>
'Geben Sie den String ein, den Sie hashen möchten'
,
'en'
=>
'Input string for hashing'
],
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
'{=Document:NAME}'
]
],
'RETURN_PROPERTIES'
=> [
'outputString'
=> [
'Name'
=> [
'de'
=>
'MD5'
,
'en'
=>
'MD5'
],
'Type'
=>
'string'
,
'Multiple'
=>
'N'
,
'Default'
=>
null
]
],
'DOCUMENT_TYPE'
=> [
'lists'
,
'BizprocDocument'
,
'iblock_164'
],
'FILTER'
=> [
'INCLUDE'
=> [
[
'lists'
]
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
1738148752.692647
,
"finish"
:
1738148752.749058
,
"duration"
:
0.056411027908325195
,
"processing"
:
0.018677949905395508
,
"date_start"
:
"2025-01-29T14:05:52+01:00"
,
"date_finish"
:
"2025-01-29T14:05:52+01:00"
,
"operating_reset_at"
:
1738149352
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
Returns
true
if the action was successfully added
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
"ERROR_ACTIVITY_VALIDATION_FAILURE"
,
"error_description"
:
"Empty activity code!"
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
Error Message
Description
ACCESS_DENIED
Application context required
Application context is required
ACCESS_DENIED
Access denied!
Method was not executed by an administrator
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty data!
Required fields are missing
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty activity code!
Action code is not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity code!
Invalid action code
ERROR_UNSUPPORTED_PROTOCOL
Unsupported handler protocol
Invalid handler protocol http, https
ERROR_WRONG_HANDLER_URL
Wrong handler URL
Invalid handler URL
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty activity NAME!
Action name is not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong properties array!
Incorrectly filled
PROPERTIES
or
RETURN_PROPERTIES
parameters
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong property key !
Invalid property identifier
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty property NAME !
Property name is not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity FILTER!
Invalid filter
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity DOCUMENT_TYPE!
Invalid
DOCUMENT_TYPE
ERROR_ACTIVITY_ALREADY_INSTALLED
Activity or Robot already installed!
An action with this code is already installed
ERROR_ACTIVITY_ADD_FAILURE
Activity or Robot already added!
The action has already been added
ERROR_ACTIVITY_ADD_FAILURE
Activity save error!
Failed to save the action, system error
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
Application Actions: Overview of Methods
Update Action bizproc.activity.update
Get the list of actions for the bizproc.activity.list application
Delete Action bizproc.activity.delete
Write information to the business process log bizproc.activity.log
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Action

---

## Update Action bizproc.activity.update

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-activity/bizproc-activity-update

Update Action bizproc.activity.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Action bizproc.activity.update
Method Parameters
Parameter FIELDS
Object PROPERTY
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method updates a business process action added by the application.
It works only in the context of the
application
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
CODE
*
string
Internal identifier of the action
FIELDS
*
object
Object with
fields
of the business process action
Parameter FIELDS
Parameter FIELDS
Name
type
Description
HANDLER
*
string
URL to which the action will send data via the Bitrix24 queue server.
The link must have the same domain where the application is installed
AUTH_USER_ID
integer
Identifier of the user whose token will be passed to the application
USE_SUBSCRIPTION
boolean
Should the action wait for a response from the application. Possible values:
Y
— yes
N
— no
NAME
*
string
|
object
Name of the action.
Can be a string or an associative array of localized strings like:
'NAME'
: {
'de'
:
'Aktionsname'
,
'en'
:
'action name'
,
...
},
DESCRIPTION
string
|
object
Description of the action.
Can be a string or an associative array of localized strings like:
'DESCRIPTION'
: {
'de'
:
'Aktionsbeschreibung'
,
'en'
:
'action description'
,
...
},
PROPERTIES
object
Object with action parameters. Contains objects, each describing a
parameter of the action
.
The system name of the parameter must start with a letter and can contain characters
a-z
,
A-Z
,
0-9
, and underscore
_
RETURN_PROPERTIES
object
Object with additional results of the action. Contains objects, each describing a
parameter of the action
.
This parameter controls whether the action can wait for a response from the application and work with the data that will
come in the response
.
The system name of the parameter must start with a letter and can contain characters
a-z
,
A-Z
,
0-9
, and underscore
_
DOCUMENT_TYPE
array
Document type that will determine the data types for the
PROPERTIES
and
RETURN_PROPERTIES
parameters. Consists of three string-type elements:
module identifier
object identifier
document type
Possible value options:
CRM Module
['crm', 'CCrmDocumentLead', 'LEAD']
— leads
['crm', 'CCrmDocumentContact', 'CONTACT']
— contacts
['crm', 'CCrmDocumentCompany', 'COMPANY']
— companies
['crm', 'CCrmDocumentDeal', 'DEAL']
— deals
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Quote', 'QUOTE']
— estimates
['crm', 'Bitrix\Crm\Integration\BizProc\Document\SmartInvoice', 'SMART_INVOICE']
— invoices
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Dynamic', 'DYNAMIC_XXX']
— SPAs, where XXX is the identifier of the SPA
Lists Module
['lists', 'BizprocDocument', 'iblock_XXX']
— processes in the news feed, where XXX is the identifier of the information block
['lists', 'Bitrix\Lists\BizprocDocumentLists', 'iblock_XXX']
— lists in groups, where XXX is the identifier of the information block
Drive Module
['disk', 'Bitrix\Disk\BizProcDocument', 'STORAGE_XXX']
, where XXX is the storage identifier
FILTER
object
Object with rules to limit the action by document type and edition.
May contain keys:
INCLUDE
— array of rules where the action will be displayed
EXCLUDE
— array of rules where the action will be hidden
Each rule in the array can be a string or an array of document types in full or partial form.
To limit the action by Bitrix24 edition, specify:
b24
— for cloud
box
— for on-premise
Examples:
Exclude action for on-premise Bitrix24
FILTER
: {
EXCLUDE
: [
'box'
]
}
Display action only for the Lists module
FILTER
: {
INCLUDE
: [
[
'lists'
]
]
}
Display action only for the Lists module and deals from CRM
FILTER
: {
INCLUDE
: [
[
'lists'
],
[
'crm'
,
'CCrmDocumentDeal'
]
]
}
USE_PLACEMENT
boolean
Allows opening additional settings of the action in the application slider. Possible values:
Y
— yes
N
— no
PLACEMENT_HANDLER
*
string
URL of the placement handler on the application side. Required if
USE_PLACEMENT = 'Y'
Object PROPERTY
Object PROPERTY
Name
type
Description
Name
string
|
object
Name of the parameter
Description
string
|
object
Description of the parameter
Type
string
Type of the parameter. Basic values:
bool
— yes or no
date
— date
datetime
— date and time
double
— number
int
— integer
select
— list
string
— string
text
— text
user
— user
Options
array
Array of values for the parameter of type list
'TYPE': select'
like:
[
'value1'
:
'title1'
,
'value2'
:
'title2'
,
'value3'
:
'title3'
,
'value4'
:
'title4'
]
Required
boolean
Requirement of the parameter. Possible values:
Y
— yes
N
— no
Multiple
boolean
Multiplicity of the parameter. Possible values:
Y
— yes
N
— no
Default
any
Default value of the parameter
Example Objects
Example Objects
// example for select type
'docType'
: {
'Name'
: {
'de'
:
'Dokumenttyp'
,
'en'
:
'Document type'
},
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'PDF'
,
'Type'
:
'select'
,
'Options'
: {
'pdf'
:
'PDF'
,
'docx'
:
'DOCX'
}
}
// example for bool type
'saveDoc'
: {
'Name'
: {
'de'
:
'Dokument speichern'
,
'en'
:
'Save document'
},
'Description'
: {
'de'
:
'Einen fortlaufenden Nummer zuweisen'
,
'en'
:
'Assign a sequential number'
},
'Type'
:
'bool'
,
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'Y'
}
// example for string type
'Parameters'
: {
'Name'
: {
'de'
:
'Vorlagenparameter'
,
'en'
:
'Template\'s parameters'
},
'Description'
: {
'de'
:
'ParamID={=ParamValue}'
,
'en'
:
'ParamID={=ParamValue}'
},
'Type'
:
'string'
,
'Required'
:
'N'
,
'Multiple'
:
'Y'
}
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"CODE":"action_test_code","FIELDS":{"AUTH_USER_ID":1,"USE_SUBSCRIPTION":"N","FILTER":{"INCLUDE":[["lists"],["crm","CCrmDocumentDeal"]]}}, "auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.activity.update
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.activity.update'
,
{
'CODE'
:
'action_test_code'
,
'FIELDS'
: {
'AUTH_USER_ID'
:
1
,
'USE_SUBSCRIPTION'
:
'N'
,
'FILTER'
: {
'INCLUDE'
: [
[
'lists'
],
[
'crm'
,
'CCrmDocumentDeal'
]
]
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
alert
(
"Success: "
+ result);
}
catch
( error )
{
alert
(
"Error: "
+ error);
}
try
{
$result
=
$serviceBuilder
->
getBizProcScope
()
->
activity
()
->
update
(
'activity_code'
,
'https://example.com/handler'
,
1
,
[
'en'
=>
'Activity Name'
,
'de'
=>
'Aktivitätsname'
],
[
'en'
=>
'Activity Description'
,
'de'
=>
'Aktivitätsbeschreibung'
],
true
,
[
'param1'
=>
'value1'
],
false
,
[
'returnParam1'
=>
'value1'
],
null
,
null
);
if
(
$result
->
isSuccess
()) {
print
(
$result
->
getCoreResponse
()->
getResponseData
()->
getResult
()[
0
]);
}
else
{
print
(
'Update failed.'
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
'Error: '
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
'bizproc.activity.update'
,
{
'CODE'
:
'action_test_code'
,
'FIELDS'
: {
'AUTH_USER_ID'
:
1
,
'USE_SUBSCRIPTION'
:
'N'
,
'FILTER'
: {
'INCLUDE'
: [
[
'lists'
],
[
'crm'
,
'CCrmDocumentDeal'
]
]
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
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Success: "
+ result.
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
'bizproc.activity.update'
,
[
'CODE'
=>
'action_test_code'
,
'FIELDS'
=> [
'AUTH_USER_ID'
=>
1
,
'USE_SUBSCRIPTION'
=>
'N'
,
'FILTER'
=> [
'INCLUDE'
=> [
[
'lists'
],
[
'crm'
,
'CCrmDocumentDeal'
]
]
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
1738149954.2918739
,
"finish"
:
1738149954.4590819
,
"duration"
:
0.16720795631408691
,
"processing"
:
0.017282962799072266
,
"date_start"
:
"2025-01-29T14:25:54+01:00"
,
"date_finish"
:
"2025-01-29T14:25:54+01:00"
,
"operating_reset_at"
:
1738150554
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
Returns
true
if the action was successfully updated
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
"ERROR_ACTIVITY_VALIDATION_FAILURE"
,
"error_description"
:
"Wrong properties array!"
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
Error Message
Description
ACCESS_DENIED
Application context required
Application context is required
ACCESS_DENIED
Access denied!
Method executed by a non-administrator
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty activity code!
Action code not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity code!
Invalid action code
ERROR_ACTIVITY_NOT_FOUND
Activity or Robot not found!
Action or robot not found
ERROR_UNSUPPORTED_PROTOCOL
Unsupported handler protocol
Invalid handler protocol http, https
ERROR_WRONG_HANDLER_URL
Wrong handler URL
Invalid handler URL
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong properties array!
Incorrectly filled parameters
PROPERTIES
or
RETURN_PROPERTIES
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong property key !
Invalid property identifier
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty property NAME !
Property name not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity FILTER!
Invalid filter
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity DOCUMENT_TYPE!
Invalid
DOCUMENT_TYPE
ERROR_ACTIVITY_VALIDATION_FAILURE
No fields to update
No fields to update
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
Application Actions: Overview of Methods
Add a New Action bizproc.activity.add
Get the list of actions for the bizproc.activity.list application
Delete Action bizproc.activity.delete
Write information to the business process log bizproc.activity.log
Copied
Was the article helpful?
Yes
No
Previous
Add New Action
Next
Get List of Application Actions

---

## Get the list of actions for the bizproc.activity.list application

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-activity/bizproc-activity-list

Get the list of actions for the bizproc.activity.list application | Bitrix24 REST API and Marketplace Applications
Get the list of actions for the bizproc.activity.list application
Get the list of actions for the bizproc.activity.list application
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method retrieves the list of actions defined by the application.
It only works in the context of the
application
.
No parameters are required.
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.activity.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'bizproc.activity.list'
,
{},
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in chunks and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'bizproc.activity.list'
, {},
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.activity.list'
, {},
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
'bizproc.activity.list'
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
'Success: '
.
implode
(
', '
,
$result
->
data
());
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
'Error calling bizproc.activity.list: '
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
'bizproc.activity.list'
,
{},
function
(
result
) {
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
"Success: "
+ result.
data
().
join
(
', '
));
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
'bizproc.activity.list'
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
[
"md5_action"
,
"doc_action"
]
,
"time"
:
{
"start"
:
1738151724.710429
,
"finish"
:
1738151724.7319269
,
"duration"
:
0.021497964859008789
,
"processing"
:
0.0011229515075683594
,
"date_start"
:
"2025-01-29T14:55:24+01:00"
,
"date_finish"
:
"2025-01-29T14:55:24+01:00"
,
"operating_reset_at"
:
1738152324
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
array
List of action identifiers for the application
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
"ACCESS_DENIED"
,
"error_description"
:
"Access denied!"
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
Error Message
Description
ACCESS_DENIED
Application context required
Application context is required
ACCESS_DENIED
Access denied!
The method was not executed by an administrator
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
Application Actions: Overview of Methods
Add a New Action bizproc.activity.add
Update Action bizproc.activity.update
Delete Action bizproc.activity.delete
Write information to the business process log bizproc.activity.log
Copied
Was the article helpful?
Yes
No
Previous
Update Action
Next
Delete Action

---

## Delete Action bizproc.activity.delete

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-activity/bizproc-activity-delete

Delete Action bizproc.activity.delete | Bitrix24 REST API and Marketplace Applications
Delete Action bizproc.activity.delete
Delete Action bizproc.activity.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method deletes an action for workflows that was added by the application.
It only works in the context of the
application
.
When the application is deleted or updated, the associated actions are removed from the list of actions in the workflow designer. If the action is used in a workflow, it is blocked and can only be removed from the scheme. Upon reinstalling the application, the action becomes available again.
Method Parameters
Method Parameters
Name
type
Description
CODE
*
string
Symbolic identifier of the application action
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"code":"md5_action","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.activity.delete
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.activity.delete'
,
{
code
:
'md5_action'
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
alert
(
'Error: '
+ result.
error
());
else
alert
(
"Success: "
+ result);
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
'bizproc.activity.delete'
,
[
'code'
=>
'md5_action'
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
'Success: '
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
'Error deleting activity: '
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
'bizproc.activity.delete'
,
{
code
:
'md5_action'
},
function
(
result
) {
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
"Success: "
+ result.
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
'bizproc.activity.delete'
,
[
'code'
=>
'md5_action'
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
1738150149.8462
,
"finish"
:
1738150149.8894911
,
"duration"
:
0.043291091918945312
,
"processing"
:
0.0053689479827880859
,
"date_start"
:
"2025-01-29T14:29:09+01:00"
,
"date_finish"
:
"2025-01-29T14:29:09+01:00"
,
"operating_reset_at"
:
1738150749
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
Returns
true
if the action was successfully deleted
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
"ERROR_ACTIVITY_NOT_FOUND"
,
"error_description"
:
"Activity or Automation rule not found!"
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
Error Message
Description
ACCESS_DENIED
Application context required
Application context is required
ACCESS_DENIED
Access denied!
Method was not executed by an administrator
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty activity code!
Activity code is not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity code!
Invalid activity code
ERROR_ACTIVITY_NOT_FOUND
Activity or Automation rule not found!
Activity or Automation rule not found
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
Application Actions: Overview of Methods
Add a New Action bizproc.activity.add
Update Action bizproc.activity.update
Get the list of actions for the bizproc.activity.list application
Write information to the business process log bizproc.activity.log
Copied
Was the article helpful?
Yes
No
Previous
Get List of Application Actions
Next
Log Information

---

## Write information to the business process log bizproc.activity.log

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-activity/bizproc-activity-log

Write information to the business process log bizproc.activity.log | Bitrix24 REST API and Marketplace Applications
Write information to the business process log bizproc.activity.log
Write information to the business process log bizproc.activity.log
Method parameters
Code examples
Error handling
Possible error codes
Statuses and System Error Codes
Continue exploring
Scope:
bizproc
Who can execute the method: administrator
The method logs information into the business process log. Event logging must be enabled in the business process template.
User documentation
Business process debugging log: how to enable log storage
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
EVENT_TOKEN
*
string
A unique key required to send an event to the business process.
The token is sent to the application action handler when the business process reaches the execution of this action.
Logging is possible if the application action is subscribed with
'USE_SUBSCRIPTION': 'Y'
during the execution of the business process.
LOG_MESSAGE
*
string
Message to log
Code examples
Code examples
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
'{"event_token":"55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90","log_message":"Please wait for answer!"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/bizproc.activity.log
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"event_token":"55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90","log_message":"Please wait for answer!","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.activity.log
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.activity.log'
,
{
event_token
:
'55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90'
,
log_message
:
'Please wait for answer!'
}
);
const
result = response.
getData
().
result
;
alert
(
"Success: "
+ result);
}
catch
( error )
{
alert
(
"Error: "
+ error);
}
try
{
$eventToken
=
'your_event_token'
;
// Replace with actual event token
$message
=
'Your log message'
;
// Replace with actual message
$result
=
$serviceBuilder
->
getBizProcScope
()
->
activity
()
->
log
(
$eventToken
,
$message
);
if
(
$result
->
isSuccess
()) {
print
(
$result
->
getCoreResponse
()->
getResponseData
()->
getResult
()[
0
]);
}
else
{
print
(
'Log entry failed.'
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
'Error: '
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
'bizproc.activity.log'
,
{
event_token
:
'55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90'
,
log_message
:
'Please wait for answer!'
},
function
(
result
) {
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
"Success: "
+ result.
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
'bizproc.activity.log'
,
[
'event_token'
=>
'55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90'
,
'log_message'
=>
'Please wait for answer!'
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
Error handling
Error handling
HTTP status:
400
{
"error"
:
"ERROR_EMPTY_LOG_MESSAGE"
,
"error_description"
:
"Empty log message!"
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
Possible error codes
Possible error codes
Code
Error message
Description
ERROR_EMPTY_LOG_MESSAGE
Empty log message!
log entry text is not specified
The method may also return errors from the business process.
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
Continue exploring
Continue exploring
Application Actions: Overview of Methods
Add a New Action bizproc.activity.add
Update Action bizproc.activity.update
Get the list of actions for the bizproc.activity.list application
Delete Action bizproc.activity.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete Action
Next
Overview of Methods

---

## Application Automation Rules

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-robot/index

Application Automation Rules | Bitrix24 REST API and Marketplace Applications
Application Automation Rules
Application Automation Rules
Method
Description
bizproc.robot.add
Registers a new Automation Rule
bizproc.robot.update
Updates the fields of an Automation Rule
bizproc.robot.list
Retrieves a list of Automation Rules registered by the application
bizproc.robot.delete
Deletes a registered Automation Rule
bizproc.event.send
Returns the output parameters of the action specified in the action description
Was the article helpful?
Yes
No
Previous
Log Information
Next
Register a New Automation Rule

---

## Register a New Robot bizproc.robot.add

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-robot/bizproc-robot-add

Register a New Robot bizproc.robot.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Register a New Robot bizproc.robot.add
Method Parameters
PROPERTY Object
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method registers a new robot.
It only works in the context of the
application
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
CODE
*
string
Internal identifier of the robot. It must be unique within the application.
Allowed characters are
a-z
,
A-Z
,
0-9
, dot, hyphen, and underscore
_
HANDLER
*
string
URL to which the robot will send data via the Bitrix24 queue server.
The link must have the same domain as the one where the application is installed
AUTH_USER_ID
integer
Identifier of the user whose token will be passed to the application
USE_SUBSCRIPTION
boolean
Should the robot wait for a response from the application? Possible values:
Y
— yes
N
— no
NAME
*
string
|
object
Name of the robot.
It can be a string or an associative array of localized strings like:
'NAME'
: {
'de'
:
'Robotername'
,
'en'
:
'robot name'
,
...
},
DESCRIPTION
string
|
object
Description of the robot.
It can be a string or an associative array of localized strings like:
'DESCRIPTION'
: {
'de'
:
'Beschreibung des Roboters'
,
'en'
:
'robot description'
,
...
},
PROPERTIES
object
An object with robot parameters. Contains objects, each describing a
robot parameter
.
The system name of the parameter must start with a letter and can contain characters
a-z
,
A-Z
,
0-9
, and underscore
_
RETURN_PROPERTIES
object
An object with additional results from the robot. Contains objects, each describing a
robot parameter
.
This parameter controls the robot's ability to wait for a response from the application and work with the data that will
come in the response
.
The system name of the parameter must start with a letter and can contain characters
a-z
,
A-Z
,
0-9
, and underscore
_
DOCUMENT_TYPE
array
Document type that will determine the data types for the
PROPERTIES
and
RETURN_PROPERTIES
parameters. Consists of three string-type elements:
module identifier
object identifier
document type
Possible value options:
CRM Module
['crm', 'CCrmDocumentLead', 'LEAD']
— leads
['crm', 'CCrmDocumentDeal', 'DEAL']
— deals
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Quote', 'QUOTE']
— estimates
['crm', 'Bitrix\Crm\Integration\BizProc\Document\SmartInvoice', 'SMART_INVOICE']
— invoices
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Dynamic', 'DYNAMIC_XXX']
— SPAs, where XXX is the identifier of the SPA
FILTER
object
An object with rules to restrict the robot by document type and edition.
It can contain keys:
INCLUDE
— an array of rules where the robot will be displayed
EXCLUDE
— an array of rules where the robot will be hidden
Each rule in the array can be a string or an array of document types in full or partial form.
To restrict robots by Bitrix24 edition, specify:
b24
— for cloud
box
— for on-premise
Examples:
Exclude the robot for on-premise Bitrix24
'FILTER'
: {
EXCLUDE
: [
'box'
]
}
Display the robot only for deals and leads in CRM
'FILTER'
: {
INCLUDE
: [
[
'crm'
,
'CCrmDocumentDeal'
],
[
'crm'
,
'CCrmDocumentLead'
]
]
}
USE_PLACEMENT
boolean
Allows opening additional robot settings in the application slider. Possible values:
Y
— yes
N
— no
PLACEMENT_HANDLER
*
string
URL of the placement handler on the application side. Required if
USE_PLACEMENT = 'Y'
PROPERTY Object
PROPERTY Object
Name
type
Description
Name
string
|
object
Name of the parameter
Description
string
|
object
Description of the parameter
Type
string
Parameter type. Basic values:
bool
— yes or no
date
— date
datetime
— date and time
double
— number
int
— integer
select
— list
string
— string
text
— text
user
— user
Options
array
An array of parameter values of type list
'TYPE': select'
like:
[
'value1'
:
'title1'
,
'value2'
:
'title2'
,
'value3'
:
'title3'
,
'value4'
:
'title4'
]
Required
boolean
Parameter requirement. Possible values:
Y
— yes
N
— no
Multiple
boolean
Parameter multiplicity. Possible values:
Y
— yes
N
— no
Default
any
Default parameter value
Example Objects
Example Objects
// example for select type
'docType'
: {
'Name'
: {
'de'
:
'Dokumenttyp'
,
'en'
:
'Document type'
},
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'PDF'
,
'Type'
:
'select'
,
'Options'
: {
'pdf'
:
'PDF'
,
'docx'
:
'DOCX'
}
}
// example for bool type
'saveDoc'
: {
'Name'
: {
'de'
:
'Dokument speichern'
,
'en'
:
'Save document'
},
'Description'
: {
'de'
:
'Einen fortlaufenden Nummer zuweisen'
,
'en'
:
'Assign a sequential number'
},
'Type'
:
'bool'
,
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'Y'
}
// example for string type
'Parameters'
: {
'Name'
: {
'de'
:
'Vorlagenparameter'
,
'en'
:
'Template\'s parameters'
},
'Description'
: {
'de'
:
'ParamID={=ParamValue}'
,
'en'
:
'ParamID={=ParamValue}'
},
'Type'
:
'string'
,
'Required'
:
'N'
,
'Multiple'
:
'Y'
}
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"CODE":"test_robot","HANDLER":"https://your_domain/robot.php","AUTH_USER_ID":1,"USE_SUBSCRIPTION":"Y","NAME":"Send Message","PROPERTIES":{"datetime":{"Name":"At what time","Type":"datetime"},"text":{"Name":"Text","Type":"text"},"user":{"Name":"To whom","Type":"user","Default":"Author;"}},"FILTER":{"INCLUDE":[["crm","CCrmDocumentDeal"],["crm","CCrmDocumentLead"]]},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.robot.add
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.robot.add'
,
{
'CODE'
:
'test_robot'
,
'HANDLER'
:
'https://your_domain/robot.php'
,
'AUTH_USER_ID'
:
1
,
'USE_SUBSCRIPTION'
:
'Y'
,
'NAME'
:
'Send Message'
,
'PROPERTIES'
: {
'datetime'
: {
'Name'
:
'At what time'
,
'Type'
:
'datetime'
},
'text'
: {
'Name'
:
'Text'
,
'Type'
:
'text'
},
'user'
: {
'Name'
:
'To whom'
,
'Type'
:
'user'
,
'Default'
:
'Author;'
}
},
'FILTER'
: {
INCLUDE
: [
[
'crm'
,
'CCrmDocumentDeal'
],
[
'crm'
,
'CCrmDocumentLead'
]
]
}
}
);
const
result = response.
getData
().
result
;
alert
(
"Successfully: "
+ result);
}
catch
( error )
{
alert
(
"Error: "
+ error);
}
try
{
$result
=
$serviceBuilder
->
getBizProcScope
()
->
robot
()
->
add
(
'robot_code'
, //
string
$code
'https://example.com/handler'
, //
string
$handlerUrl
1
, //
int
$b24AuthUserId
[
'en'
=>
'Robot Name'
], //
array
$localizedRobotName
true
, //
bool
$isUseSubscription
[], //
array
$properties
false
, //
bool
$isUsePlacement
[] //
array
$returnProperties
);
if
(
$result
->
isSuccess
()) {
print_r
(
$result
->
getCoreResponse
()->
getResponseData
()->
getResult
());
}
else
{
print
(
"Failed to add robot."
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
"Error: "
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
'bizproc.robot.add'
,
{
'CODE'
:
'test_robot'
,
'HANDLER'
:
'https://your_domain/robot.php'
,
'AUTH_USER_ID'
:
1
,
'USE_SUBSCRIPTION'
:
'Y'
,
'NAME'
:
'Send Message'
,
'PROPERTIES'
: {
'datetime'
: {
'Name'
:
'At what time'
,
'Type'
:
'datetime'
},
'text'
: {
'Name'
:
'Text'
,
'Type'
:
'text'
},
'user'
: {
'Name'
:
'To whom'
,
'Type'
:
'user'
,
'Default'
:
'Author;'
}
},
'FILTER'
: {
INCLUDE
: [
[
'crm'
,
'CCrmDocumentDeal'
],
[
'crm'
,
'CCrmDocumentLead'
]
]
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
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Successfully: "
+ result.
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
'bizproc.robot.add'
,
[
'CODE'
=>
'test_robot'
,
'HANDLER'
=>
'https://your_domain/robot.php'
,
'AUTH_USER_ID'
=>
1
,
'USE_SUBSCRIPTION'
=>
'Y'
,
'NAME'
=>
'Send Message'
,
'PROPERTIES'
=> [
'datetime'
=> [
'Name'
=>
'At what time'
,
'Type'
=>
'datetime'
],
'text'
=> [
'Name'
=>
'Text'
,
'Type'
=>
'text'
],
'user'
=> [
'Name'
=>
'To whom'
,
'Type'
=>
'user'
,
'Default'
=>
'Author;'
]
},
'FILTER'
=> [
'INCLUDE'
=> [
[
'crm'
,
'CCrmDocumentDeal'
],
[
'crm'
,
'CCrmDocumentLead'
]
]
}
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
1738148752.692647
,
"finish"
:
1738148752.749058
,
"duration"
:
0.056411027908325195
,
"processing"
:
0.018677949905395508
,
"date_start"
:
"2025-01-29T14:05:52+02:00"
,
"date_finish"
:
"2025-01-29T14:05:52+02:00"
,
"operating_reset_at"
:
1738149352
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
Returns
true
if the robot was successfully added
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
"ERROR_ACTIVITY_VALIDATION_FAILURE"
,
"error_description"
:
"Empty activity code!"
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
Error Message
Description
ACCESS_DENIED
Application context required
Application context is required
ACCESS_DENIED
Access denied!
The method was executed by a non-administrator
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty data!
Required fields with information are not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty activity code!
Robot code is not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity code!
Invalid robot code
ERROR_UNSUPPORTED_PROTOCOL
Unsupported handler protocol
Invalid handler protocol http, https
ERROR_WRONG_HANDLER_URL
Wrong handler URL
Invalid handler URL
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty activity NAME!
Robot name is not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong properties array!
Incorrectly filled parameters
PROPERTIES
or
RETURN_PROPERTIES
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong property key !
Invalid property identifier
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty property NAME !
Property name is not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity FILTER!
Invalid filter
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity DOCUMENT_TYPE!
Invalid
DOCUMENT_TYPE
ERROR_ACTIVITY_ALREADY_INSTALLED
Activity or Robot already installed!
A robot with this code is already installed
ERROR_ACTIVITY_ADD_FAILURE
Activity or Robot already added!
The robot has already been added
ERROR_ACTIVITY_ADD_FAILURE
Activity save error!
Failed to save the robot, system error
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
Application Automation Rules
Update Robot Fields bizproc.robot.update
Get a list of registered application robots bizproc.robot.list
Delete Registered Robot bizproc.robot.delete
Return parameters to the action or Automation rule bizproc.event.send
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Automation Rule Fields

---

## Update Robot Fields bizproc.robot.update

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-robot/bizproc-robot-update

Update Robot Fields bizproc.robot.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update Robot Fields bizproc.robot.update
Method Parameters
FIELDS Parameter
PROPERTY Object
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method updates the fields of a robot registered by the application.
It only works in the context of the
application
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
CODE
*
string
Internal identifier of the robot
FIELDS
*
object
Object with the
fields
of the robot
FIELDS Parameter
FIELDS Parameter
Name
type
Description
HANDLER
*
string
URL to which the robot will send data via the Bitrix24 queue server.
The link must have the same domain as the one where the application is installed
AUTH_USER_ID
integer
Identifier of the user whose token will be passed to the application
USE_SUBSCRIPTION
boolean
Should the robot wait for a response from the application? Possible values:
Y
— yes
N
— no
NAME
*
string
|
object
Name of the robot.
Can be a string or an associative array of localized strings like:
'NAME'
: {
'de'
:
'Robotname'
,
'en'
:
'robot name'
,
...
},
DESCRIPTION
string
|
object
Description of the robot.
Can be a string or an associative array of localized strings like:
'DESCRIPTION'
: {
'de'
:
'Beschreibung des Roboters'
,
'en'
:
'robot description'
,
...
},
PROPERTIES
object
Object with robot parameters. Contains objects, each describing a
robot parameter
.
The system name of the parameter must start with a letter and can contain characters
a-z
,
A-Z
,
0-9
, and underscore
_
RETURN_PROPERTIES
object
Object with additional results from the robot. Contains objects, each describing a
robot parameter
.
This parameter controls the robot's ability to wait for a response from the application and work with the data that
comes in the response
.
The system name of the parameter must start with a letter and can contain characters
a-z
,
A-Z
,
0-9
, and underscore
_
DOCUMENT_TYPE
array
Document type that will determine the data types for the
PROPERTIES
and
RETURN_PROPERTIES
parameters. Consists of three string-type elements:
module identifier
object identifier
document type
Possible value options:
CRM Module
['crm', 'CCrmDocumentLead', 'LEAD']
— leads
['crm', 'CCrmDocumentDeal', 'DEAL']
— deals
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Quote', 'QUOTE']
— estimates
['crm', 'Bitrix\Crm\Integration\BizProc\Document\SmartInvoice', 'SMART_INVOICE']
— invoices
['crm', 'Bitrix\Crm\Integration\BizProc\Document\Dynamic', 'DYNAMIC_XXX']
— SPAs, where XXX is the identifier of the SPA
FILTER
object
Object with rules to restrict the robot by document type and edition.
May contain keys:
INCLUDE
— array of rules where the robot will be displayed
EXCLUDE
— array of rules where the robot will be hidden
Each rule in the array can be a string or an array of document types in full or partial form.
To restrict the robot by Bitrix24 edition, specify:
b24
— for cloud
box
— for on-premise
Examples:
Exclude the robot for on-premise Bitrix24
'FILTER'
: {
EXCLUDE
: [
'box'
]
}
Display the robot only for deals and leads in CRM
'FILTER'
: {
INCLUDE
: [
[
'crm'
,
'CCrmDocumentDeal'
],
[
'crm'
,
'CCrmDocumentLead'
]
]
}
USE_PLACEMENT
boolean
Allows opening additional robot settings in the application slider. Possible values:
Y
— yes
N
— no
PLACEMENT_HANDLER
*
string
URL of the placement handler on the application side. Required if
USE_PLACEMENT = 'Y'
PROPERTY Object
PROPERTY Object
Name
type
Description
Name
string
|
object
Name of the parameter
Description
string
|
object
Description of the parameter
Type
string
Type of the parameter. Basic values:
bool
— yes or no
date
— date
datetime
— date and time
double
— number
int
— integer
select
— list
string
— string
text
— text
user
— user
Options
array
Array of parameter values of type list
'TYPE': select'
like:
[
'value1'
:
'title1'
,
'value2'
:
'title2'
,
'value3'
:
'title3'
,
'value4'
:
'title4'
]
Required
boolean
Parameter requirement. Possible values:
Y
— yes
N
— no
Multiple
boolean
Parameter multiplicity. Possible values:
Y
— yes
N
— no
Default
any
Default value of the parameter
Example Objects
Example Objects
// example for select type
'docType'
: {
'Name'
: {
'de'
:
'Dokumenttyp'
,
'en'
:
'Document type'
},
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'PDF'
,
'Type'
:
'select'
,
'Options'
: {
'pdf'
:
'PDF'
,
'docx'
:
'DOCX'
}
}
// example for bool type
'saveDoc'
: {
'Name'
: {
'de'
:
'Dokument speichern'
,
'en'
:
'Save document'
},
'Description'
: {
'de'
:
'Einen fortlaufenden Nummer zuweisen'
,
'en'
:
'Assign a sequential number'
},
'Type'
:
'bool'
,
'Required'
:
'Y'
,
'Multiple'
:
'N'
,
'Default'
:
'Y'
}
// example for string type
'Parameters'
: {
'Name'
: {
'de'
:
'Vorlagenparameter'
,
'en'
:
'Template\'s parameters'
},
'Description'
: {
'de'
:
'ParamID={=ParamValue}'
,
'en'
:
'ParamID={=ParamValue}'
},
'Type'
:
'string'
,
'Required'
:
'N'
,
'Multiple'
:
'Y'
}
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"CODE":"test_robot","FIELDS":{"NAME":"Send message to author","USE_SUBSCRIPTION":"N","FILTER":{"INCLUDE":[["crm","CCrmDocumentDeal"]]}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.robot.update
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.robot.update'
,
{
'CODE'
:
'test_robot'
,
'FIELDS'
: {
'NAME'
:
'Send message to author'
,
'USE_SUBSCRIPTION'
:
'N'
,
'FILTER'
: {
INCLUDE
: [
[
'crm'
,
'CCrmDocumentDeal'
]
]
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
alert
(
"Success: "
+ result);
}
catch
( error )
{
alert
(
"Error: "
+ error);
}
try
{
$result
=
$serviceBuilder
->
getBizProcScope
()
->
robot
()
->
update
(
'robot_code'
,
'https://example.com/handler'
,
1
,
[
'en'
=>
'Localized Name'
],
true
,
[
'property1'
=>
'value1'
],
false
,
[
'returnProperty1'
]
);
// Process the result
if
(
$result
->
isSuccess
()) {
print_r
(
$result
->
getCoreResponse
()->
getResponseData
()->
getResult
());
}
else
{
print
(
"Update failed."
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
'bizproc.robot.update'
,
{
'CODE'
:
'test_robot'
,
'FIELDS'
: {
'NAME'
:
'Send message to author'
,
'USE_SUBSCRIPTION'
:
'N'
,
'FILTER'
: {
INCLUDE
: [
[
'crm'
,
'CCrmDocumentDeal'
]
]
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
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Success: "
+ result.
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
'bizproc.robot.update'
,
[
'CODE'
=>
'test_robot'
,
'FIELDS'
=> [
'NAME'
=>
'Send message to author'
,
'USE_SUBSCRIPTION'
=>
'N'
,
'FILTER'
=> [
'INCLUDE'
=> [
[
'crm'
,
'CCrmDocumentDeal'
]
]
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
1738149954.2918739
,
"finish"
:
1738149954.4590819
,
"duration"
:
0.16720795631408691
,
"processing"
:
0.017282962799072266
,
"date_start"
:
"2025-01-29T14:25:54+01:00"
,
"date_finish"
:
"2025-01-29T14:25:54+01:00"
,
"operating_reset_at"
:
1738150554
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
Returns
true
if the robot was successfully updated
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
"ERROR_ACTIVITY_VALIDATION_FAILURE"
,
"error_description"
:
"Wrong properties array!"
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
Error Message
Description
ACCESS_DENIED
Application context required
Application context is required
ACCESS_DENIED
Access denied!
Method executed by a non-administrator
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty activity code!
Robot code not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity code!
Invalid robot code
ERROR_ACTIVITY_NOT_FOUND
Activity or Robot not found!
Robot not found
ERROR_UNSUPPORTED_PROTOCOL
Unsupported handler protocol
Invalid handler protocol http, https
ERROR_WRONG_HANDLER_URL
Wrong handler URL
Invalid handler URL
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong properties array!
Incorrectly filled parameters
PROPERTIES
or
RETURN_PROPERTIES
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong property key !
Invalid property identifier
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty property NAME !
Property name not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity FILTER!
Invalid filter
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity DOCUMENT_TYPE!
Invalid
DOCUMENT_TYPE
ERROR_ACTIVITY_VALIDATION_FAILURE
No fields to update
No fields to update
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
Application Automation Rules
Register a New Robot bizproc.robot.add
Get a list of registered application robots bizproc.robot.list
Delete Registered Robot bizproc.robot.delete
Return parameters to the action or Automation rule bizproc.event.send
Copied
Was the article helpful?
Yes
No
Previous
Register a New Automation Rule
Next
Get a List of Automation Rules

---

## Get a list of registered application robots bizproc.robot.list

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-robot/bizproc-robot-list

Get a list of registered application robots bizproc.robot.list | Bitrix24 REST API and Marketplace Applications
Code Examples
Get a list of registered application robots bizproc.robot.list
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
The method returns a list of robots registered by the application.
It works only in the context of the
application
.
No parameters.
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.robot.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'bizproc.robot.list'
,
{},
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
'bizproc.robot.list'
, {},
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.robot.list'
, {},
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
$result
=
$serviceBuilder
->
getBizProcScope
()
->
robot
()
->
list
();
foreach
(
$result
->
getRobots
()
as
$robot
) {
print
(
$robot
->code);
print
(
$robot
->name);
print
(
$robot
->handlerUrl);
print
(
$robot
->authUserId);
print
(
$robot
->isUseSubscription ?
'Yes'
:
'No'
);
print
(
$robot
->isUsePlacement ?
'Yes'
:
'No'
);
if
(
$robot
->createdDate
instanceof
DateTime) {
print
(
$robot
->createdDate->
format
(
DateTime
::
ATOM
));
}
}
}
catch
(
Throwable
$e
) {
// Handle the exception
print
(
'Error: '
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
'bizproc.robot.list'
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
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Success: "
+ result.
data
().
join
(
', '
));
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
'bizproc.robot.list'
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
[
"test_robot"
,
"sms_robot"
]
,
"time"
:
{
"start"
:
1738151724.710429
,
"finish"
:
1738151724.7319269
,
"duration"
:
0.021497964859008789
,
"processing"
:
0.0011229515075683594
,
"date_start"
:
"2025-01-29T14:55:24+01:00"
,
"date_finish"
:
"2025-01-29T14:55:24+01:00"
,
"operating_reset_at"
:
1738152324
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
array
List of application robot identifiers
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
"ACCESS_DENIED"
,
"error_description"
:
"Access denied!"
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
Error Message
Description
ACCESS_DENIED
Application context required
Application context is required
ACCESS_DENIED
Access denied!
The method was not executed by an administrator
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
Application Automation Rules
Register a New Robot bizproc.robot.add
Update Robot Fields bizproc.robot.update
Delete Registered Robot bizproc.robot.delete
Return parameters to the action or Automation rule bizproc.event.send
Copied
Was the article helpful?
Yes
No
Previous
Update Automation Rule Fields
Next
Delete an Automation Rule

---

## Delete Registered Robot bizproc.robot.delete

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-robot/bizproc-robot-delete

Delete Registered Robot bizproc.robot.delete | Bitrix24 REST API and Marketplace Applications
Delete Registered Robot bizproc.robot.delete
Delete Registered Robot bizproc.robot.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: administrator
This method removes a robot registered by the application.
It only works in the context of the
application
.
When the application is deleted or updated, the associated robots are removed from the list of robots. If the robot is in use, it is blocked and can only be removed from the workflow. Upon reinstalling the application, the robot becomes available again.
Method Parameters
Method Parameters
Name
type
Description
CODE
*
string
Symbolic identifier of the application robot
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"CODE":"test_robot","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.robot.delete
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.robot.delete'
,
{
'CODE'
:
'test_robot'
}
);
const
result = response.
getData
().
result
;
alert
(
"Success: "
+ result);
}
catch
( error )
{
alert
(
'Error: '
+ error);
}
try
{
$robotCode
=
'your_robot_code_here'
;
// Replace with the actual robot code
$result
=
$serviceBuilder
->
getBizProcScope
()
->
robot
()
->
delete
(
$robotCode
);
if
(
$result
->
isSuccess
()) {
print
(
"Robot deleted successfully."
);
}
else
{
print
(
"Failed to delete robot."
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
"Error: "
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
'bizproc.robot.delete'
,
{
'CODE'
:
'test_robot'
},
function
(
result
) {
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
"Success: "
+ result.
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
'bizproc.robot.delete'
,
[
'CODE'
=>
'test_robot'
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
1738150149.8462
,
"finish"
:
1738150149.8894911
,
"duration"
:
0.043291091918945312
,
"processing"
:
0.0053689479827880859
,
"date_start"
:
"2025-01-29T14:29:09+01:00"
,
"date_finish"
:
"2025-01-29T14:29:09+01:00"
,
"operating_reset_at"
:
1738150749
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
Returns
true
if the robot was successfully deleted
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
"ERROR_ACTIVITY_NOT_FOUND"
,
"error_description"
:
"Activity or Robot not found!"
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
Error Message
Description
ACCESS_DENIED
Application context required
Application context is required
ACCESS_DENIED
Access denied!
Method executed by non-administrator
ERROR_ACTIVITY_VALIDATION_FAILURE
Empty activity code!
Robot code not specified
ERROR_ACTIVITY_VALIDATION_FAILURE
Wrong activity code!
Invalid robot code
ERROR_ACTIVITY_NOT_FOUND
Activity or Robot not found!
Robot not found
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
Application Automation Rules
Register a New Robot bizproc.robot.add
Update Robot Fields bizproc.robot.update
Get a list of registered application robots bizproc.robot.list
Return parameters to the action or Automation rule bizproc.event.send
Copied
Was the article helpful?
Yes
No
Previous
Get a List of Automation Rules
Next
Return Parameters to a Workflow Action or Automation Rule

---

## Return parameters to the action or Automation rule bizproc.event.send

**Source:** https://apidocs.bitrix24.com/api-reference/bizproc/bizproc-robot/bizproc-event-send

Return parameters to the action or Automation rule bizproc.event.send | Bitrix24 REST API and Marketplace Applications
Method Parameters
Return parameters to the action or Automation rule bizproc.event.send
Method Parameters
Code Examples
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
bizproc
Who can execute the method: any user
The method returns the output parameters of the action specified in the action description.
Method Parameters
Method Parameters
Name
type
Description
EVENT_TOKEN
A special token that is sent to the application handler when the action or Automation rule is executed. The value of this token is received by the handler of the Automation rule or business process action in the array of input data passed.
An event can be sent if the application action is subscribed with
'USE_SUBSCRIPTION': 'Y'
to the execution of the business process or Automation rules
RETURN_VALUES
An array of returned values from the action or Automation rule. It specifies the values of properties that were registered as additional results
RETURN_PROPERTIES
by the methods:
bizproc.robot.add
,
bizproc.robot.update
bizproc.activity.add
,
bizproc.activity.update
LOG_MESSAGE
Text for the business process log.
By default, it has the value "Received response from the application."
Logging of events must be
enabled in the template
of the business process
Code Examples
Code Examples
How to Use Examples in Documentation
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
'{"event_token":"55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90","return_values":{"outputString":"846c55d14f552180874a628d2615e285"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/bizproc.event.send
try
{
const
response =
await
$b24.
callMethod
(
'bizproc.event.send'
,
{
event_token
:
'55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90'
,
return_values
: {
outputString
:
'846c55d14f552180874a628d2615e285'
}
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
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Success: "
+ result);
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
'bizproc.event.send'
,
[
'event_token'
=>
'55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90'
,
'return_values'
=> [
'outputString'
=>
'846c55d14f552180874a628d2615e285'
]
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
'Success: '
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
'Error sending bizproc event: '
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
'bizproc.event.send'
,
{
event_token
:
'55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90'
,
return_values
: {
outputString
:
'846c55d14f552180874a628d2615e285'
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
alert
(
"Error: "
+ result.
error
());
else
alert
(
"Success: "
+ result.
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
'bizproc.event.send'
,
[
'event_token'
=>
'55c1dc1c3f0d75.78875596|A51601_82584_96831_81132|hsyUws1j4XiwqPqN45eH66CcQtEvpUIP.47dd5d888e8e549d2c984713e12a4268e6e87d0208ca1f093ba1075e77f92e90'
,
'return_values'
=> [
'outputString'
=>
'846c55d14f552180874a628d2615e285'
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
Error Handling
Error Handling
Possible Error Codes
Possible Error Codes
The method may return an error code and text from the business process or Automation rule.
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
Application Automation Rules
Copied
Was the article helpful?
Yes
No
Previous
Delete an Automation Rule
Next
Vibe and Widgets

---

