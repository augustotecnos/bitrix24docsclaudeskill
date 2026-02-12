---
description: 'BI Connector API: Datasets, metrics, analytics integration'
methods:
- app.domain
pages: 23
title: 'BI Connector API: Datasets, metrics, analytics integration'
---
# BI Connector API: Datasets, metrics, analytics integration
> BI Connector API: Datasets, metrics, analytics integration
> **23 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [BIconnector: Overview of Methods](#biconnector-overview-of-methods)
- [Connector: Overview of Methods](#connector-overview-of-methods)
- [Create Connector biconnector.connector.add](#create-connector-biconnectorconnectoradd)
- [Update the biconnector.connector.update](#update-the-biconnectorconnectorupdate)
- [Get Connector by ID biconnector.connector.get](#get-connector-by-id-biconnectorconnectorget)
- [Get the list of connectors biconnector.connector.list](#get-the-list-of-connectors-biconnectorconnectorlis)
- [Delete Connector biconnector.connector.delete](#delete-connector-biconnectorconnectordelete)
- [Get Connector Fields biconnector.connector.fields](#get-connector-fields-biconnectorconnectorfields)
- [Sources: Overview of Methods](#sources-overview-of-methods)
- [Create Source biconnector.source.add](#create-source-biconnectorsourceadd)
- [Change source biconnector.source.update](#change-source-biconnectorsourceupdate)
- [Get Source by ID biconnector.source.get](#get-source-by-id-biconnectorsourceget)
- [Get the list of sources biconnector.source.list](#get-the-list-of-sources-biconnectorsourcelist)
- [Delete source biconnector.source.delete](#delete-source-biconnectorsourcedelete)
- [Get Source Fields of biconnector.source.fields](#get-source-fields-of-biconnectorsourcefields)
- [Datasets: Overview of Methods](#datasets-overview-of-methods)
- [Create Dataset biconnector.dataset.add](#create-dataset-biconnectordatasetadd)
- [Update Dataset biconnector.dataset.update](#update-dataset-biconnectordatasetupdate)
- [Update Dataset Fields biconnector.dataset.fields.update](#update-dataset-fields-biconnectordatasetfieldsupda)
- [Get dataset by id biconnector.dataset.get](#get-dataset-by-id-biconnectordatasetget)
- [Get the list of datasets biconnector.dataset.list](#get-the-list-of-datasets-biconnectordatasetlist)
- [Delete dataset biconnector.dataset.delete](#delete-dataset-biconnectordatasetdelete)
- [Get Fields of the Dataset biconnector.dataset.fields](#get-fields-of-the-dataset-biconnectordatasetfields)

---

## BIconnector: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/index

BIconnector: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Connector
BIconnector: Overview of Methods
Connector
Sources
Datasets
Methods only work in the context of the
application
Scope:
biconnector
Who can execute the methods: a user with access to the "Analyst Workspace" section
Connector
Connector
Method
Description
biconnector.connector.add
Adds a new connector
biconnector.connector.update
Updates an existing connector
biconnector.connector.get
Returns information about the connector
biconnector.connector.list
Returns a list of available connectors
biconnector.connector.delete
Deletes a connector
biconnector.connector.fields
Returns the description of the connector fields
Sources
Sources
Method
Description
biconnector.source.add
Adds a new source
biconnector.source.update
Updates an existing source
biconnector.source.get
Returns information about the source
biconnector.source.list
Returns a list of available sources
biconnector.source.delete
Deletes a source
biconnector.source.fields
Returns the description of the source fields
Datasets
Datasets
Method
Description
biconnector.dataset.add
Adds a new dataset
biconnector.dataset.update
Updates an existing dataset
biconnector.dataset.fields.update
Updates the fields of the dataset
biconnector.dataset.get
Returns information about the dataset
biconnector.dataset.list
Returns a list of available datasets
biconnector.dataset.delete
Deletes a dataset
biconnector.dataset.fields
Returns the description of the dataset fields
Copied
Was the article helpful?
Yes
No
Previous
When Adding a User
Next
Overview of methods

---

## Connector: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/connector/index

Connector: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Connector: Overview of Methods
Connector: Overview of Methods
Connector's Relationship with Sources and Datasets
Description of Connector Fields
Settings Field
Connector Endpoints
Field Parameters
Overview of Methods
Continue Learning
The connector is a tool for integrating Bitrix24 with external data systems. It is responsible for connecting to third-party APIs and databases, importing data for analytics and reporting.
Each connector contains settings for working with a specific source:
endpoints — URLs for sending HTTP requests,
authorization parameters.
Quick navigation:
all methods
Methods work only in the context of the
application
Connector's Relationship with Sources and Datasets
Connector's Relationship with Sources and Datasets
The connector is the top level in the data hierarchy within the BIconnector module:
Connector
establishes a connection with an external data source.
Source
defines which specific data is available from the connected service.
Dataset
forms the final set of data that can be used in reports and analytics.
Description of Connector Fields
Description of Connector Fields
Name
type
Description
Read
Write
id
integer
Unique identifier of the connector
✅
❌
title
string
Name of the connector
✅
✅
logo
string
URL of the logo or base64 string
✅
✅
description
string
Description of the connector
✅
✅
sort
integer
Sorting order
✅
✅
urlCheck
string
URL for connection check
✅
✅
urlData
string
URL for data retrieval
✅
✅
urlTableList
string
URL for table list
✅
✅
urlTableDescription
string
URL for table description
✅
✅
settings
array
Connector settings
✅
✅
dateCreate
datetime
Date of connector creation
✅
❌
Settings Field
Settings Field
The
settings
field contains an array of parameters necessary for configuring data sources. Each parameter is an object with the following structure:
code
— parameter code, used as the identifier for the parameter, this is how parameters are passed to the external source.
name
— parameter name, which will be displayed in the interface, in the "Analyst's workspace" section.
type
— parameter type, currently only
STRING
is supported.
{
"code": "code_value",
"name": "name_value",
"type": "type_value"
}
Connector Endpoints
Connector Endpoints
urlCheck
urlCheck
The
urlCheck
endpoint performs two key functions:
Checks the availability of the connection to the external source.
Authenticates the user.
The endpoint is called:
when creating a new connection,
when editing an existing connection,
when creating a dataset.
A POST request is sent to the endpoint with the following parameters:
setting_code_n
— code of the connector's settings parameter.
settings_value_n
— value of this parameter related to the specific source.
{
"connection": {
"setting_code_1": "settings_value_1",
...,
"setting_code_n": "settings_value_n"
}
}
Depending on availability, the endpoint returns information about the status of the source. Requirements for the response format from the endpoint to the request from Bitrix24: the response must not be empty, HTTP status:
200
. The response format is flexible.
A request to the endpoint for connection verification can be sent from the interface, in the "Analyst's workspace" section.
urlTableList
urlTableList
The
urlTableList
endpoint returns a list of available tables in
JSON
format. The endpoint will return tables that match the search query. The endpoint is called when creating a dataset through the interface.
A POST request is sent to the endpoint with the following parameters:
searchString
— value of the search string, searches tables by
externalCode
.
setting_code_n
— code of the connector's settings parameter.
settings_value_n
— value of this parameter related to the specific source.
{
"searchString": "search_value",
"connection": {
"setting_code_1": "settings_value_1",
...,
"setting_code_n": "settings_value_n"
}
}
The response returns an array of objects corresponding to the request, with the structure:
code
— name of the dataset that will be used in Bitrix24.
title
— name of the dataset in the external source. The search is performed based on this field.
{
'code' => 'dataset_name',
'title' => 'externalName'
}
urlTableDescription
urlTableDescription
The
urlTableDescription
endpoint returns a list of fields for a specific table in
JSON
format. The endpoint is called when creating a dataset through the interface.
A POST request is sent to the endpoint with the following parameters:
table
—
externalCode
of the dataset for which the description is requested.
setting_code_n
— code of the connector's settings parameter.
settings_value_n
— value of this parameter related to the specific source.
{
"name": "entityName",
"connection": {
"setting_code_1": "settings_value_1",
...,
"setting_code_n": "settings_value_n"
}
}
The response returns an array of fields with the structure:
code
— code of the dataset field.
name
— name of the dataset field.
type
— field type, supported values:
int
,
string
,
double
,
date
,
datetime
.
{
'code' => "code_value",
'name' => "title_value",
'type' => "type_value"
}
urlData
urlData
The
urlData
endpoint returns data from a specific table in
JSON
format.
The endpoint is called:
when creating a dataset through the interface,
when synchronizing dataset fields through the interface,
when executing requests to retrieve data for the BI Builder.
A POST request is sent to the endpoint with the following parameters:
select
— selection of dataset fields.
filter
— filter by dataset fields.
limit
— limit of dataset selection.
table
—
externalCode
of the dataset for which data is requested.
setting_code_n
— code of the connector's settings parameter.
settings_value_n
— value of this parameter related to the specific source.
{
"select": **array**,
"filter": **object**,
"limit": **int**,
"table": "entityName",
"connection": {
"setting_code_1": "settings_value_1",
...,
"setting_code_n": "settings_value_n"
}
}
The response returns an array of fields with the structure:
FIELD_N
— field code.
VALUE_ROW_M_N
— values of field
N
in row
M
.
[
["FIELD_1","FIELD_2",...,"FIELD_N"],
[VALUE_ROW_1_1,VALUE_ROW_1_2,...,VALUE_ROW_1_N,],
[VALUE_ROW_2_1,VALUE_ROW_2_2,...,VALUE_ROW_2_N,]
...
,[VALUE_ROW_M_1,VALUE_ROW_M_2,...,VALUE_ROW_M_N,]
]
Field Parameters
Field Parameters
Name
type
Description
title
string
Field name
type
string
Field type
isRequired
boolean
Required field
isReadOnly
boolean
Field is read-only
isImmutable
boolean
Field value can only be set once and only when creating a new element. After that, the field value cannot be changed
isMultiple
boolean
Multiple field. If true, values in the field are passed as an array
Overview of Methods
Overview of Methods
Scope:
biconnector
Who can execute methods: user with access to the "Analyst's workspace" section
Method
Description
biconnector.connector.add
Adds a new connector
biconnector.connector.update
Updates an existing connector
biconnector.connector.get
Returns information about the connector
biconnector.connector.list
Returns a list of available connectors
biconnector.connector.delete
Deletes a connector
biconnector.connector.fields
Returns the description of the connector fields
Continue Learning
Continue Learning
Example of creating a connector based on B24PHPSDK
Meetup about creating a connector
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Create connector

---

## Create Connector biconnector.connector.add

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/connector/biconnector-connector-add

Create Connector biconnector.connector.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Create Connector biconnector.connector.add
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
biconnector
Who can execute the method: user with access to the "Analyst's workspace" section
The method
biconnector.connector.add
creates a new connector that allows integrating external data sources into Bitrix24.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
An object containing data to create a new connector. The object format:
{
"field_1": "value_1",
"field_2": "value_2",
...,
"field_n": "value_n"
}
field_n
— field name
value_n
— field value
Detailed description below
Parameter fields
Parameter fields
Name
type
Description
title
*
string
Connector name
logo
*
string
Connector logo. Can be provided as a link to an image or a base64 formatted string, for example
data:image/svg+xml;base64,PHN2ZyB3...
description
string
Connector description
urlCheck
*
string
Connector endpoint for availability check,
(detailed description)
urlTableList
*
string
Connector endpoint for retrieving the list of tables,
(detailed description)
urlTableDescription
*
string
Connector endpoint for retrieving the description of a specific table,
(detailed description)
urlData
*
string
Connector endpoint for retrieving data from the selected table,
(detailed description)
settings
*
array
List of connection parameters,
(detailed description)
sort
int
Connector sorting parameter. Default value is
100
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
'{
"fields": {
"title": "SUPER REST CONNECTOR",
"logo": "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyMiAyMiIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxjaXJjbGUgY3g9IjExIiBjeT0iMTEiIHI9IjEwIiBmaWxsPSIjRkYzQjNCIiAvPgoJPHRleHQgeD0iMTEiIHk9IjEzIiBmb250LWZhbWlseT0iQXJpYWwsIHNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iNiIgZmlsbD0iI0ZGRkZGRiIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZm9udC13ZWlnaHQ9ImJvbGQiPlJFU1Q8L3RleHQ+Cjwvc3ZnPg==",
"description": "Connector with token",
"urlCheck": "http://example.com/api/check",
"urlTableList": "http://example.com/api/table_list",
"urlTableDescription": "http://example.com/api/table_description",
"urlData": "http://example.com/api/data",
"settings": [
{
"name": "Login",
"type": "STRING",
"code": "login"
},
{
"name": "Password",
"type": "STRING",
"code": "password"
}
],
"sort": 100
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.connector.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"fields": {
"title": "SUPER REST CONNECTOR",
"logo": "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyMiAyMiIgZmlsbD0ibm9uZSIgeG1zbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxjaXJjbGUgY3g9IjExIiBjeT0iMTEiIHI9IjEwIiBmaWxsPSIjRkYzQjNCIiAvPgoJPHRleHQgeD0iMTEiIHk9IjEzIiBmb250LWZhbWlseT0iQXJpYWwsIHNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iNiIgZmlsbD0iI0ZGRkZGRiIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZm9udC13ZWlnaHQ9ImJvbGQiPlJFU1Q8L3RleHQ+Cjwvc3ZnPg==",
"description": "Connector with token",
"urlCheck": "http://example.com/api/check",
"urlTableList": "http://example.com/api/table_list",
"urlTableDescription": "http://example.com/api/table_description",
"urlData": "http://example.com/api/data",
"settings": [
{
"name": "Login",
"type": "STRING",
"code": "login"
},
{
"name": "Password",
"type": "STRING",
"code": "password"
}
],
"sort": 100
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.connector.add
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.connector.add'
,
{
fields
: {
"title"
:
"SUPER REST CONNECTOR"
,
"logo"
:
"data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyMiAyMiIgZmlsbD0ibm9uZSIgeG1zbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxjaXJjbGUgY3g9IjExIiBjeT0iMTEiIHI9IjEwIiBmaWxsPSIjRkYzQjNCIiAvPgoJPHRleHQgeD0iMTEiIHk9IjEzIiBmb250LWZhbWlseT0iQXJpYWwsIHNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iNiIgZmlsbD0iI0ZGRkZGRiIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZm9udC13ZWlnaHQ9ImJvbGQiPlJFU1Q8L3RleHQ+Cjwvc3ZnPg=="
,
"description"
:
"Connector with token"
,
"urlCheck"
:
"http://example.com/api/check"
,
"urlTableList"
:
"http://example.com/api/table_list"
,
"urlTableDescription"
:
"http://example.com/api/table_description"
,
"urlData"
:
"http://example.com/api/data"
,
"settings"
: [
{
"name"
:
"Login"
,
"type"
:
"STRING"
,
"code"
:
"login"
},
{
"name"
:
"Password"
,
"type"
:
"STRING"
,
"code"
:
"password"
}
],
"sort"
:
100
},
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
(result.
data
());
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
'biconnector.connector.add'
,
[
'fields'
=> [
"title"
=>
"SUPER REST CONNECTOR"
,
"logo"
=>
"data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyMiAyMiIgZmlsbD0ibm9uZSIgeG1zbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxjaXJjbGUgY3g9IjExIiBjeT0iMTEiIHI9IjEwIiBmaWxsPSIjRkYzQjNCIiAvPgoJPHRleHQgeD0iMTEiIHk9IjEzIiBmb250LWZhbWlseT0iQXJpYWwsIHNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iNiIgZmlsbD0iI0ZGRkZGRiIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZm9udC13ZWlnaHQ9ImJvbGQiPlJFU1Q8L3RleHQ+Cjwvc3ZnPg=="
,
"description"
=>
"Connector with token"
,
"urlCheck"
=>
"http://example.com/api/check"
,
"urlTableList"
=>
"http://example.com/api/table_list"
,
"urlTableDescription"
=>
"http://example.com/api/table_description"
,
"urlData"
=>
"http://example.com/api/data"
,
"settings"
=> [
[
"name"
=>
"Login"
,
"type"
=>
"STRING"
,
"code"
=>
"login"
],
[
"name"
=>
"Password"
,
"type"
=>
"STRING"
,
"code"
=>
"password"
]
],
"sort"
=>
100
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
'Error adding connector: '
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
'biconnector.connector.add'
,
{
fields
: {
"title"
:
"SUPER REST CONNECTOR"
,
"logo"
:
"data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyMiAyMiIgZmlsbD0ibm9uZSIgeG1zbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxjaXJjbGUgY3g9IjExIiBjeT0iMTEiIHI9IjEwIiBmaWxsPSIjRkYzQjNCIiAvPgoJPHRleHQgeD0iMTEiIHk9IjEzIiBmb250LWZhbWlseT0iQXJpYWwsIHNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iNiIgZmlsbD0iI0ZGRkZGRiIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZm9udC13ZWlnaHQ9ImJvbGQiPlJFU1Q8L3RleHQ+Cjwvc3ZnPg=="
,
"description"
:
"Connector with token"
,
"urlCheck"
:
"http://example.com/api/check"
,
"urlTableList"
:
"http://example.com/api/table_list"
,
"urlTableDescription"
:
"http://example.com/api/table_description"
,
"urlData"
:
"http://example.com/api/data"
,
"settings"
: [
{
"name"
:
"Login"
,
"type"
:
"STRING"
,
"code"
:
"login"
},
{
"name"
:
"Password"
,
"type"
:
"STRING"
,
"code"
:
"password"
}
],
"sort"
:
100
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
'biconnector.connector.add'
,
[
'fields'
=> [
'title'
=>
'SUPER REST CONNECTOR'
,
'logo'
=>
'data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyMiAyMiIgZmlsbD0ibm9uZSIgeG1zbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxjaXJjbGUgY3g9IjExIiBjeT0iMTEiIHI9IjEwIiBmaWxsPSIjRkYzQjNCIiAvPgoJPHRleHQgeD0iMTEiIHk9IjEzIiBmb250LWZhbWlseT0iQXJpYWwsIHNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iNiIgZmlsbD0iI0ZGRkZGRiIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZm9udC13ZWlnaHQ9ImJvbGQiPlJFU1Q8L3RleHQ+Cjwvc3ZnPg=='
,
'description'
=>
'Connector with token'
,
'urlCheck'
=>
'http://example.com/api/check'
,
'urlTableList'
=>
'http://example.com/api/table_list'
,
'urlTableDescription'
=>
'http://example.com/api/table_description'
,
'urlData'
=>
'http://example.com/api/data'
,
'settings'
=> [
[
'name'
=>
'Login'
,
'type'
=>
'STRING'
,
'code'
=>
'login'
],
[
'name'
=>
'Password'
,
'type'
=>
'STRING'
,
'code'
=>
'password'
]
],
'sort'
=>
100
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
{
"id"
:
4
}
,
"time"
:
{
"start"
:
1725013197.635808
,
"finish"
:
1725013198.580873
,
"duration"
:
0.9450650215148926
,
"processing"
:
0.6822988986968994
,
"date_start"
:
"2024-08-30T12:19:57+02:00"
,
"date_finish"
:
"2024-08-30T12:19:58+02:00"
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
integer
Root element of the response, contains the identifier of the created connector
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
"VALIDATION_FIELDS_NOT_PROVIDED"
,
"error_description"
:
"Fields not provided."
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
VALIDATION_FIELDS_NOT_PROVIDED
Fields not provided
Fields were not passed in the request
VALIDATION_UNKNOWN_PARAMETERS
Unknown parameters: #LIST_OF_PARAMS#
Unknown parameters detected: list
VALIDATION_REQUIRED_FIELD_MISSING
Field "#TITLE#" is required.
Required field #TITLE# was not provided
VALIDATION_READ_ONLY_FIELD
Field "#TITLE#" is read only.
Field #TITLE# is read-only and cannot be modified
VALIDATION_IMMUTABLE_FIELD
Field "#TITLE#" is immutable.
Field #TITLE# is immutable
VALIDATION_INVALID_FIELD_TYPE
Field "#TITLE#" must be of type #TYPE#.
Field #TITLE# must be of type #TYPE#
VALIDATION_SETTINGS_MISSING_REQUIRED_FIELDS
Settings must include "type", "name" and "code" fields.
Settings must include
type
,
name
, and
code
fields
VALIDATION_SETTINGS_NAME_TOO_LONG
Parameter "name" must be less than 512 characters.
The value of the parameter
name
must not exceed 512 characters
VALIDATION_SETTINGS_CODE_TOO_LONG
Parameter "code" must be less than 512 characters.
The value of the parameter
code
must not exceed 512 characters
VALIDATION_SETTINGS_INVALID_TYPE
Parameter "type" is not correct.
Invalid value for parameter
type
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
Update the biconnector.connector.update
Get Connector by ID biconnector.connector.get
Get the list of connectors biconnector.connector.list
Delete Connector biconnector.connector.delete
Get Connector Fields biconnector.connector.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Update connector

---

## Update the biconnector.connector.update

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/connector/biconnector-connector-update

Update the biconnector.connector.update | Bitrix24 REST API and Marketplace Applications
Method Parameters
Update the biconnector.connector.update
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
biconnector
Who can execute the method: user with access to the "Analyst's workspace" section
The method
biconnector.connector.update
updates an existing connector.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Connector identifier, can be obtained using the methods
biconnector.connector.list
and
biconnector.connector.add
fields
*
object
An object containing the updated data. The object format:
{
"field_1": "value_1",
"field_2": "value_2",
...,
"field_n": "value_n"
}
field_n
— field name
value_n
— field value
Detailed description below
Parameter fields
Parameter fields
Name
type
Description
title
string
New connector name
logo
string
New connector logo. Can be passed as a link to an image or a base64 formatted string, for example
data:image/svg+xml;base64,PHN2ZyB3...
description
string
New connector description
urlCheck
string
New endpoint for checking the connector's availability,
(detailed description)
urlTableList
string
New endpoint for obtaining the list of tables,
(detailed description)
urlTableDescription
string
New endpoint for obtaining the description of a specific table,
(detailed description)
urlData
string
New endpoint for obtaining data from the selected table,
(detailed description)
settings
array
New list of connection parameters,
(detailed description)
sort
int
New sorting parameter for the connector
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
'{
"id": 4,
"fields": {
"title": "UPDATED REST CONNECTOR",
"logo": "data:image/svg+xml;base64,NEWLOGODATA",
"description": "Updated description",
"urlCheck": "http://example.com/api/new_check",
"urlTableList": "http://example.com/api/new_table_list",
"urlTableDescription": "http://example.com/api/new_table_description",
"urlData": "http://example.com/api/new_data",
"settings": [
{
"name": "Employee Identifier",
"type": "STRING",
"code": "id"
},
{
"name": "Password",
"type": "STRING",
"code": "password"
}
],
"sort": 200
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.connector.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"id": 4,
"fields": {
"title": "UPDATED REST CONNECTOR",
"logo": "data:image/svg+xml;base64,NEWLOGODATA",
"description": "Updated description",
"urlCheck": "http://example.com/api/new_check",
"urlTableList": "http://example.com/api/new_table_list",
"urlTableDescription": "http://example.com/api/new_table_description",
"urlData": "http://example.com/api/new_data",
"settings": [
{
"name": "Employee Identifier",
"type": "STRING",
"code": "id"
},
{
"name": "Password",
"type": "STRING",
"code": "password"
}
],
"sort": 200
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.connector.update
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.connector.update'
,
{
id
:
4
,
fields
: {
"title"
:
"UPDATED REST CONNECTOR"
,
"logo"
:
"data:image/svg+xml;base64,NEWLOGODATA"
,
"description"
:
"Updated description"
,
"urlCheck"
:
"http://example.com/api/new_check"
,
"urlTableList"
:
"http://example.com/api/new_table_list"
,
"urlTableDescription"
:
"http://example.com/api/new_table_description"
,
"urlData"
:
"http://example.com/api/new_data"
,
"settings"
: [
{
"name"
:
"Employee Identifier"
,
"type"
:
"STRING"
,
"code"
:
"id"
},
{
"name"
:
"Password"
,
"type"
:
"STRING"
,
"code"
:
"password"
}
],
"sort"
:
200
}
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
'biconnector.connector.update'
,
[
'id'
=>
4
,
'fields'
=> [
"title"
=>
"UPDATED REST CONNECTOR"
,
"logo"
=>
"data:image/svg+xml;base64,NEWLOGODATA"
,
"description"
=>
"Updated description"
,
"urlCheck"
=>
"http://example.com/api/new_check"
,
"urlTableList"
=>
"http://example.com/api/new_table_list"
,
"urlTableDescription"
=>
"http://example.com/api/new_table_description"
,
"urlData"
=>
"http://example.com/api/new_data"
,
"settings"
=> [
[
"name"
=>
"Employee Identifier"
,
"type"
=>
"STRING"
,
"code"
=>
"id"
],
[
"name"
=>
"Password"
,
"type"
=>
"STRING"
,
"code"
=>
"password"
]
],
"sort"
=>
200
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
'Error updating connector: '
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
'biconnector.connector.update'
,
{
id
:
4
,
fields
: {
"title"
:
"UPDATED REST CONNECTOR"
,
"logo"
:
"data:image/svg+xml;base64,NEWLOGODATA"
,
"description"
:
"Updated description"
,
"urlCheck"
:
"http://example.com/api/new_check"
,
"urlTableList"
:
"http://example.com/api/new_table_list"
,
"urlTableDescription"
:
"http://example.com/api/new_table_description"
,
"urlData"
:
"http://example.com/api/new_data"
,
"settings"
: [
{
"name"
:
"Employee Identifier"
,
"type"
:
"STRING"
,
"code"
:
"id"
},
{
"name"
:
"Password"
,
"type"
:
"STRING"
,
"code"
:
"password"
}
],
"sort"
:
200
}
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
'biconnector.connector.update'
,
[
'id'
=>
4
,
'fields'
=> [
'title'
=>
'UPDATED REST CONNECTOR'
,
'logo'
=>
'data:image/svg+xml;base64,NEWLOGODATA'
,
'description'
=>
'Updated description'
,
'urlCheck'
=>
'http://example.com/api/new_check'
,
'urlTableList'
=>
'http://example.com/api/new_table_list'
,
'urlTableDescription'
=>
'http://example.com/api/new_table_description'
,
'urlData'
=>
'http://example.com/api/new_data'
,
'settings'
=> [
[
'name'
=>
'Employee Identifier'
,
'type'
=>
'STRING'
,
'code'
=>
'id'
],
[
'name'
=>
'Password'
,
'type'
=>
'STRING'
,
'code'
=>
'password'
]
],
'sort'
=>
200
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
1725365418.056843
,
"finish"
:
1725365419.671506
,
"duration"
:
1.6146628856658936
,
"processing"
:
1.3475170135498047
,
"date_start"
:
"2024-09-03T14:10:18+02:00"
,
"date_finish"
:
"2024-09-03T14:10:19+02:00"
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
200
{
"error"
:
"VALIDATION_FIELDS_NOT_PROVIDED"
,
"error_description"
:
"Fields not provided."
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
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not specified
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
VALIDATION_FIELDS_NOT_PROVIDED
Fields not provided.
Fields were not passed in the request
VALIDATION_UNKNOWN_PARAMETERS
Unknown parameters: #LIST_OF_PARAMS#
Unknown parameters detected: list
VALIDATION_READ_ONLY_FIELD
Field "#TITLE#" is read only.
Field #TITLE# is read-only and cannot be modified
VALIDATION_IMMUTABLE_FIELD
Field "#TITLE#" is immutable.
Field #TITLE# is immutable
VALIDATION_INVALID_FIELD_TYPE
Field "#TITLE#" must be of type #TYPE#.
Field #TITLE# must be of type #TYPE#
CONNECTOR_NOT_FOUND
Connector was not found.
Connector not found
VALIDATION_SETTINGS_MISSING_REQUIRED_FIELDS
Settings must include "type", "name" and "code" fields.
Settings must include the fields
type
,
name
, and
code
VALIDATION_SETTINGS_INVALID_TYPE
Parameter "type" is not correct.
Invalid value for parameter
type
VALIDATION_SETTINGS_NAME_TOO_LONG
Parameter "name" must be less than 512 characters.
The value of parameter
name
must not exceed 512 characters
VALIDATION_SETTINGS_CODE_TOO_LONG
Parameter "code" must be less than 512 characters.
The value of parameter
code
must not exceed 512 characters
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
Create Connector biconnector.connector.add
Get Connector by ID biconnector.connector.get
Get the list of connectors biconnector.connector.list
Delete Connector biconnector.connector.delete
Get Connector Fields biconnector.connector.fields
Copied
Was the article helpful?
Yes
No
Previous
Create connector
Next
Get connector information

---

## Get Connector by ID biconnector.connector.get

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/connector/biconnector-connector-get

Get Connector by ID biconnector.connector.get | Bitrix24 REST API and Marketplace Applications
Get Connector by ID biconnector.connector.get
Get Connector by ID biconnector.connector.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: user with access to the "Analyst Workspace" section
The method
biconnector.connector.get
returns information about the connector by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
The identifier of the connector, which can be obtained using the methods
biconnector.connector.list
and
biconnector.connector.add
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
'{
"id": 4
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.connector.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"id": 4,
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.connector.get
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.connector.get'
,
{
id
:
4
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
() ?
console
.
error
(result.
error
()) :
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
'biconnector.connector.get'
,
[
'id'
=>
4
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
'Info: '
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
'Error calling biconnector.connector.get: '
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
'biconnector.connector.get'
,
{
id
:
4
,
},
(
result
) =>
{
result.
error
() ?
console
.
error
(result.
error
()) :
console
.
info
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
'biconnector.connector.get'
,
[
'id'
=>
4
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
5
,
"title"
:
"SUPER REST CONNECTOR"
,
"dateCreate"
:
"2025-03-24 07:25:59"
,
"logo"
:
"https://masterpiecer-images.s3.amazonaws.com/5fd531dca6427c7:upscaled"
,
"description"
:
"Connector with token"
,
"sort"
:
100
,
"urlCheck"
:
"http://app.domain/check"
,
"settings"
:
[
{
"name"
:
"Login"
,
"code"
:
"login"
,
"type"
:
"STRING"
}
,
{
"name"
:
"Password"
,
"code"
:
"password"
,
"type"
:
"STRING"
}
]
,
"urlData"
:
"http://app.domain/data"
,
"urlTableList"
:
"http://app.domain/table_list"
,
"urlTableDescription"
:
"http://app.domain/table_description"
}
}
,
"time"
:
{
"start"
:
1725365418.056843
,
"finish"
:
1725365419.671506
,
"duration"
:
1.6146628856658936
,
"processing"
:
1.3475170135498047
,
"date_start"
:
"2024-09-03T14:10:18+02:00"
,
"date_finish"
:
"2024-09-03T14:10:19+02:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
item
The root element of the response. Contains information about the connector fields. Field descriptions can be found in the article
Connector: Overview of Methods
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP Status:
200
{
"error"
:
"VALIDATION_ID_NOT_PROVIDED"
,
"error_description"
:
"ID is missing."
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
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not provided
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
CONNECTOR_NOT_FOUND
Connector was not found.
Connector not found
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
Update the biconnector.connector.update
Create Connector biconnector.connector.add
Get the list of connectors biconnector.connector.list
Delete Connector biconnector.connector.delete
Get Connector Fields biconnector.connector.fields
Copied
Was the article helpful?
Yes
No
Previous
Update connector
Next
Get list of connectors

---

## Get the list of connectors biconnector.connector.list

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/connector/biconnector-connector-list

Get the list of connectors biconnector.connector.list | Bitrix24 REST API and Marketplace Applications
Get the list of connectors biconnector.connector.list
Get the list of connectors biconnector.connector.list
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: user with access to the "Analyst's workspace" section
The method
biconnector.connector.list
returns a list of connectors based on a filter. It is an implementation of the list method for connectors.
Method Parameters
Method Parameters
Name
type
Description
select
string[]
List of fields that must be filled in the connectors in the selection. By default, all fields are taken
filter
object
Filter for selecting connectors. Example format:
{
"field_1"
:
"value_1"
,
"field_2"
:
"value_2"
}
You can add a prefix to the keys
field_n
to specify the filter operation.
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
— IN, an array is passed as a value
!@
— NOT IN, an array is passed as a value
%
— LIKE, substring search. The
%
symbol in the filter value does not need to be passed. The search looks for a substring in any position of the string
=%
— LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
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
=
— equal, exact match (used by default)
!=
— not equal
!
— not equal
The list of available fields for filtering can be found using the method
biconnector.connector.fields
order
object
Sorting parameters. Example format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
field_n
— the name of the field by which the selection of connectors will be sorted
value_n
— a
string
type value, equal to:
ASC
— ascending sort
DESC
— descending sort
page
integer
Controls pagination. The page size of results is 50 records. To navigate through results, pass the page number
Code Examples
Code Examples
How to Use Examples in Documentation
Get the list of connectors where:
the name starts with
MyConnector
the description is not empty
Display only the necessary fields:
identifier
id
name
title
endpoint for checking the availability of the source
urlCheck
creation date
dateCreate
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
'{
"SELECT": [
"id",
"title",
"urlCheck",
"dateCreate"
],
"FILTER": {
"%=title": "MyConnector%",
"!description": ""
},
"ORDER": {
"dateCreate": "DESC"
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.connector.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"SELECT": [
"id",
"title",
"urlCheck",
"dateCreate"
],
"FILTER": {
"%=title": "MyConnector%",
"!description": ""
},
"ORDER": {
"dateCreate": "DESC"
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.connector.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'biconnector.connector.list'
,
{
select
: [
"id"
,
"title"
,
"urlCheck"
,
"dateCreate"
],
filter
: {
'%=title'
:
"MyConnector%"
,
'!description'
:
''
},
order
: {
dateCreate
:
"DESC"
}
},
(
progress
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
());
}
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'biconnector.connector.list'
, {
select
: [
"id"
,
"title"
,
"urlCheck"
,
"dateCreate"
],
filter
: {
'%=title'
:
"MyConnector%"
,
'!description'
:
''
},
order
: {
dateCreate
:
"DESC"
}
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
'biconnector.connector.list'
, {
select
: [
"id"
,
"title"
,
"urlCheck"
,
"dateCreate"
],
filter
: {
'%=title'
:
"MyConnector%"
,
'!description'
:
''
},
order
: {
dateCreate
:
"DESC"
}
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
$response
=
$b24Service
->core
->
call
(
'biconnector.connector.list'
,
[
'select'
=> [
"id"
,
"title"
,
"urlCheck"
,
"dateCreate"
],
'filter'
=> [
'%=title'
=>
"MyConnector%"
,
'!description'
=>
''
],
'order'
=> [
'dateCreate'
=>
"DESC"
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
'Error calling biconnector.connector.list: '
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
'biconnector.connector.list'
,
{
select
: [
"id"
,
"title"
,
"urlCheck"
,
"dateCreate"
],
filter
: {
'%=title'
:
"MyConnector%"
,
'!description'
:
''
},
order
: {
dateCreate
:
"DESC"
}
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
'biconnector.connector.list'
,
[
'select'
=> [
"id"
,
"title"
,
"urlCheck"
,
"dateCreate"
],
'filter'
=> [
'%=title'
=>
"MyConnector%"
,
'!description'
=>
''
],
'order'
=> [
'dateCreate'
=>
"DESC"
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
"id"
:
"11"
,
"title"
:
"MyConnector_2"
,
"urlCheck"
:
"https://new_example.com/check"
,
"dateCreate"
:
"2025-03-24 07:25:59"
}
,
{
"id"
:
"9"
,
"title"
:
"MyConnector"
,
"urlCheck"
:
"https://example.com/check"
,
"dateCreate"
:
"2025-03-21 12:22:32"
}
]
,
"time"
:
{
"start"
:
1742804947.923552
,
"finish"
:
1742804947.995446
,
"duration"
:
0.07189393043518066
,
"processing"
:
0.0017020702362060547
,
"date_start"
:
"2025-03-24T08:29:07+00:00"
,
"date_finish"
:
"2025-03-24T08:29:07+00:00"
}
}
Returned Data
Returned Data
result
object
The root element of the response. Contains an array of objects with information about the fields of connectors.
It should be noted that the structure of fields may change due to the
select
parameter
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
"VALIDATION_SELECT_TYPE"
,
"error_description"
:
"Parameter \"select\" must be array."
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
VALIDATION_SELECT_TYPE
Parameter "select" must be array.
The
select
parameter is not an object
VALIDATION_FILTER_TYPE
Parameter "filter" must be array.
The
filter
parameter is not an object
VALIDATION_ORDER_TYPE
Parameter "order" must be array.
The
order
parameter is not an object
VALIDATION_FIELD_NOT_ALLOWED_IN_SELECT
Field "#TITLE#" is not allowed in the "select".
These fields are not allowed in the selection
VALIDATION_FIELD_NOT_ALLOWED_IN_FILTER
Field "#TITLE#" is not allowed in the "filter".
These fields are not allowed in the filter
VALIDATION_FIELD_NOT_ALLOWED_IN_ORDER
Field "#TITLE#" is not allowed in the "order".
These fields are not allowed for sorting
VALIDATION_INVALID_FILTER_LOGIC
Field "logic" must be either "AND" or "OR".
The
logic
field can only have the value "AND" or "OR"
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
Update the biconnector.connector.update
Get Connector by ID biconnector.connector.get
Create Connector biconnector.connector.add
Delete Connector biconnector.connector.delete
Get Connector Fields biconnector.connector.fields
Copied
Was the article helpful?
Yes
No
Previous
Get connector information
Next
Delete connector

---

## Delete Connector biconnector.connector.delete

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/connector/biconnector-connector-delete

Delete Connector biconnector.connector.delete | Bitrix24 REST API and Marketplace Applications
Delete Connector biconnector.connector.delete
Delete Connector biconnector.connector.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: user with access to the "Analyst Workspace" section
The method
biconnector.connector.delete
removes an existing connector.
A connector can be deleted if it has no sources.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the connector, can be obtained using the methods
biconnector.connector.list
and
biconnector.connector.add
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
'{
"id": 4
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.connector.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"id": 4,
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.connector.delete
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.connector.delete'
,
{
id
:
4
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
() ?
console
.
error
(result.
error
()) :
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
'biconnector.connector.delete'
,
[
'id'
=>
4
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
'Info: '
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
'Error deleting connector: '
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
'biconnector.connector.delete'
,
{
id
:
4
,
},
(
result
) =>
{
result.
error
() ?
console
.
error
(result.
error
()) :
console
.
info
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
'biconnector.connector.delete'
,
[
'id'
=>
4
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
1725365418.056843
,
"finish"
:
1725365419.671506
,
"duration"
:
1.6146628856658936
,
"processing"
:
1.3475170135498047
,
"date_start"
:
"2024-09-03T14:10:18+02:00"
,
"date_finish"
:
"2024-09-03T14:10:19+02:00"
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
200
{
"error"
:
"VALIDATION_ID_NOT_PROVIDED"
,
"error_description"
:
"ID is missing."
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
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not specified
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
CONNECTOR_NOT_FOUND
Connector was not found.
Connector not found
CONNECTOR_DELETE_RESTRICTED
Connector cannot be removed. Remove the connections related to the connector first.
Cannot delete connector while related connections exist
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
Update the biconnector.connector.update
Get Connector by ID biconnector.connector.get
Get the list of connectors biconnector.connector.list
Create Connector biconnector.connector.add
Get Connector Fields biconnector.connector.fields
Copied
Was the article helpful?
Yes
No
Previous
Get list of connectors
Next
Get connector fields

---

## Get Connector Fields biconnector.connector.fields

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/connector/biconnector-connector-fields

Get Connector Fields biconnector.connector.fields | Bitrix24 REST API and Marketplace Applications
Get Connector Fields biconnector.connector.fields
Get Connector Fields biconnector.connector.fields
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: any user
The method
biconnector.connector.fields
returns a description of the connector fields. A table with the description of standard fields can be found in the article
Connector: Overview of Methods
.
Method Parameters
Method Parameters
No parameters.
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
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.connector.fields
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
https://**put_your_bitrix24_address**/rest/biconnector.connector.fields
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.connector.fields'
,
{}
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
'biconnector.connector.fields'
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
'Error calling biconnector.connector.fields: '
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
'biconnector.connector.fields'
,
{},
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
'biconnector.connector.fields'
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
HTTP Status:
200
{
"result"
:
{
"fields"
:
[
{
"title"
:
"id"
,
"type"
:
"integer"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"title"
,
"type"
:
"string"
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
}
,
{
"title"
:
"logo"
,
"type"
:
"string"
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
}
,
{
"title"
:
"description"
,
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
}
,
{
"title"
:
"sort"
,
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
}
,
{
"title"
:
"urlCheck"
,
"type"
:
"string"
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
}
,
{
"title"
:
"urlData"
,
"type"
:
"string"
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
}
,
{
"title"
:
"urlTableList"
,
"type"
:
"string"
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
}
,
{
"title"
:
"urlTableDescription"
,
"type"
:
"string"
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
}
,
{
"title"
:
"settings"
,
"type"
:
"array"
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
true
}
,
{
"title"
:
"dateCreate"
,
"type"
:
"datetime"
,
"isRequired"
:
true
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
}
]
}
,
"time"
:
{
"start"
:
1740671757.058651
,
"finish"
:
1740671757.179896
,
"duration"
:
0.12124514579772949
,
"processing"
:
5.507469177246094e-5
,
"date_start"
:
"2025-02-27T15:55:57+00:00"
,
"date_finish"
:
"2025-02-27T15:55:57+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
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
— connector field
value_n
—
field information
time
time
Information about the request execution time
Error Handling
Error Handling
The method does not return errors.
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
Update the biconnector.connector.update
Get Connector by ID biconnector.connector.get
Get the list of connectors biconnector.connector.list
Delete Connector biconnector.connector.delete
Create Connector biconnector.connector.add
Copied
Was the article helpful?
Yes
No
Previous
Delete connector
Next
Overview of methods

---

## Sources: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/source/index

Sources: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Sources: Overview of Methods
Sources: Overview of Methods
Connection of the Source with the Connector and Datasets
Description of Source Fields
Field settings
Overview of Methods
A source is a separate connection to an external system in the BIconnector module. The source defines which specific data from the external system will be available for use in reports and analytics in Bitrix24.
Quick navigation:
all methods
Methods only work in the context of the
application
Connection of the Source with the Connector and Datasets
Connection of the Source with the Connector and Datasets
The source is registered through the connector. In the hierarchy of the BIconnector module, sources occupy an intermediate level:
Connector
establishes a connection with the external data source.
Source
defines the access parameters for the data.
Dataset
forms the final set of data that can be used in reports and analytics.
Description of Source Fields
Description of Source Fields
Name
type
Description
Read
Write
id
integer
Unique identifier of the source
✅
❌
title
string
Name of the source
✅
✅
type
string
Type of the source, value is always
rest
✅
❌
code
string
Code of the source, system field
✅
❌
description
string
Description of the source
✅
✅
active
boolean
Status of the source's activity
✅
✅
dateCreate
datetime
Creation date of the source
✅
❌
dateUpdate
datetime
Update date of the source
✅
❌
createdById
integer
Identifier of the user who created the source
✅
❌
updatedById
integer
Identifier of the user who updated the source
✅
❌
connectorId
integer
Identifier of the connector to which the source is linked
✅
✅
settings
array
List of authorization parameters
✅
✅
Field settings
Field settings
The
settings
field contains a list of parameters for authorization through the connector. The parameters are passed in the format of an object, where the key is the parameter identifier —
code
. The values of
code
can be obtained using the methods
biconnector.connector.list
or
biconnector.connector.get
.
Overview of Methods
Overview of Methods
Scope:
biconnector
Who can execute the methods: a user with access to the "Analyst Workspace" section
Method
Description
biconnector.source.add
Adds a new source
biconnector.source.update
Updates an existing source
biconnector.source.get
Returns information about the source
biconnector.source.list
Returns a list of available sources
biconnector.source.delete
Deletes a source
biconnector.source.fields
Returns the description of the source fields
Copied
Was the article helpful?
Yes
No
Previous
Get connector fields
Next
Create source

---

## Create Source biconnector.source.add

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/source/biconnector-source-add

Create Source biconnector.source.add | Bitrix24 REST API and Marketplace Applications
Create Source biconnector.source.add
Create Source biconnector.source.add
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
biconnector
Who can execute the method: user with access to the "Analyst's Workspace" section
The method
biconnector.source.add
creates a new data source associated with the connector.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
An object containing data to create a new source. The object format is:
{
"field_1": "value_1",
"field_2": "value_2",
...,
"field_n": "value_n"
}
field_n
— field name
value_n
— field value
Detailed description below
Parameter fields
Parameter fields
Name
type
Description
title
*
string
Source name
description
string
Source description
active
boolean
Source activity.
Default is
true
connectorId
*
integer
Connector identifier, can be obtained using the methods
biconnector.connector.list
or
biconnector.connector.add
settings
*
object
A list of parameters for authorization, passed as an object where the key is the
code
of the parameter.
Parameters can be obtained using the methods
biconnector.connector.list
or
biconnector.connector.get
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
'{"fields":{"title":"CRM Source","description":"CRM data source","connectorId":123,"settings":{"login":"admin","password":"qwerty"}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.source.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"title":"CRM Source","description":"CRM data source","connectorId":123,"settings":{"login":"admin","password":"qwerty"}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/biconnector.source.add
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.source.add'
,
{
fields
: {
"title"
:
"CRM Source"
,
"description"
:
"CRM data source"
,
"connectorId"
:
123
,
"settings"
: {
"login"
:
"admin"
,
"password"
:
"qwerty"
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
result.
error
() ?
console
.
error
(result.
error
()) :
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
'biconnector.source.add'
,
[
'fields'
=> [
"title"
=>
"CRM Source"
,
"description"
=>
"CRM data source"
,
"connectorId"
=>
123
,
"settings"
=> [
"login"
=>
"admin"
,
"password"
=>
"qwerty"
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
if
(
$response
->
getError
()) {
error_log
(
$response
->
getError
());
echo
'Error: '
.
$response
->
getError
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
,
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
'Error adding source: '
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
'biconnector.source.add'
,
{
fields
: {
"title"
:
"CRM Source"
,
"description"
:
"CRM data source"
,
"connectorId"
:
123
,
"settings"
: {
"login"
:
"admin"
,
"password"
:
"qwerty"
}
}
},
(
result
) =>
{
result.
error
() ?
console
.
error
(result.
error
()) :
console
.
info
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
'biconnector.source.add'
,
[
'fields'
=> [
'title'
=>
'CRM Source'
,
'description'
=>
'CRM data source'
,
'connectorId'
=>
123
,
'settings'
=> [
'login'
=>
'admin'
,
'password'
=>
'qwerty'
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
{
"id"
:
7
}
,
"time"
:
{
"start"
:
1725013197.635808
,
"finish"
:
1725013198.580873
,
"duration"
:
0.9450650215148926
,
"processing"
:
0.6822988986968994
,
"date_start"
:
"2024-08-30T12:19:57+02:00"
,
"date_finish"
:
"2024-08-30T12:19:58+02:00"
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
integer
Root element of the response, contains the identifier of the created source
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
"VALIDATION_FIELDS_NOT_PROVIDED"
,
"error_description"
:
"Fields not provided."
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
VALIDATION_FIELDS_NOT_PROVIDED
Fields not provided.
Fields were not passed in the request
VALIDATION_UNKNOWN_PARAMETERS
Unknown parameters: #LIST_OF_PARAMS#
Unknown parameters detected: list
VALIDATION_REQUIRED_FIELD_MISSING
Field "#TITLE#" is required.
Required field #TITLE# was not provided
VALIDATION_READ_ONLY_FIELD
Field "#TITLE#" is read only.
Field #TITLE# is read-only and cannot be modified
VALIDATION_IMMUTABLE_FIELD
Field "#TITLE#" is immutable.
Field #TITLE# is immutable
VALIDATION_INVALID_FIELD_TYPE
Field "#TITLE#" must be of type #TYPE#.
Field #TITLE# must be of type #TYPE#
CONNECTOR_NOT_FOUND
Connector was not found.
Connector not found
SOURCE_CREATE_CONNECTION_ERROR
Cannot create connection.
Error creating connection
SOURCE_UPDATE_CONNECTION_ERROR
Cannot update connection.
Error updating connection
BX_ERROR
Cannot delete source. Delete all related datasets first.
Cannot delete source while related datasets exist
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
Change source biconnector.source.update
Get Source by ID biconnector.source.get
Get the list of sources biconnector.source.list
Delete source biconnector.source.delete
Get Source Fields of biconnector.source.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Update source

---

## Change source biconnector.source.update

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/source/biconnector-source-update

Change source biconnector.source.update | Bitrix24 REST API and Marketplace Applications
Change source biconnector.source.update
Change source biconnector.source.update
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
biconnector
Who can execute the method: user with access to the "Analyst's workspace" section
The method
biconnector.source.update
updates an existing source.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the source, can be obtained using the methods
biconnector.source.list
and
biconnector.source.add
fields
*
object
Object containing the updated data.
Object format:
{
"field_1": "value_1",
"field_2": "value_2",
...,
"field_n": "value_n"
}
field_n
— field name
value_n
— field value
Detailed description below
Parameter fields
Parameter fields
Name
type
Description
title
string
New name of the source
description
string
New description of the source
active
boolean
Activity status of the source
settings
object
List of parameters for authorization, passed as an object where the key is the
code
of the parameter.
Parameters can be obtained using the methods
biconnector.connector.list
or
biconnector.connector.get
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
'{
"id": 4,
"fields": {
"title": "New source name",
"description": "Updated source description",
"active": false,
"settings": {
"login": "new_admin",
"password": "new_password"
}
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.source.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"id": 4,
"fields": {
"title": "New source name",
"description": "Updated source description",
"active": false,
"settings": {
"login": "new_admin",
"password": "new_password"
}
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.source.update
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.source.update'
,
{
id
:
4
,
fields
: {
"title"
:
"New source name"
,
"description"
:
"Updated source description"
,
"active"
:
false
,
"settings"
: {
"login"
:
"new_admin"
,
"password"
:
"new_password"
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
'biconnector.source.update'
,
[
'id'
=>
4
,
'fields'
=> [
"title"
=>
"New source name"
,
"description"
=>
"Updated source description"
,
"active"
=>
false
,
"settings"
=> [
"login"
=>
"new_admin"
,
"password"
=>
"new_password"
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
'Error updating source: '
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
'biconnector.source.update'
,
{
id
:
4
,
fields
: {
"title"
:
"New source name"
,
"description"
:
"Updated source description"
,
"active"
:
false
,
"settings"
: {
"login"
:
"new_admin"
,
"password"
:
"new_password"
}
}
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
'biconnector.source.update'
,
[
'id'
=>
4
,
'fields'
=> [
'title'
=>
'New source name'
,
'description'
=>
'Updated source description'
,
'active'
=>
false
,
'settings'
=> [
'login'
=>
'new_admin'
,
'password'
=>
'new_password'
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
1725365418.056843
,
"finish"
:
1725365419.671506
,
"duration"
:
1.6146628856658936
,
"processing"
:
1.3475170135498047
,
"date_start"
:
"2024-09-03T14:10:18+02:00"
,
"date_finish"
:
"2024-09-03T14:10:19+02:00"
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
on success
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
"VALIDATION_FIELDS_NOT_PROVIDED"
,
"error_description"
:
"Fields not provided."
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
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not specified
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
VALIDATION_FIELDS_NOT_PROVIDED
Fields not provided.
Fields not passed in the request
VALIDATION_UNKNOWN_PARAMETERS
Unknown parameters: #LIST_OF_PARAMS#
Unknown parameters detected: list
VALIDATION_REQUIRED_FIELD_MISSING
Field "#TITLE#" is required.
Required field #TITLE# not provided
VALIDATION_READ_ONLY_FIELD
Field "#TITLE#" is read only.
Field #TITLE# is read-only and cannot be modified
VALIDATION_IMMUTABLE_FIELD
Field "#TITLE#" is immutable.
Field #TITLE# is immutable
VALIDATION_INVALID_FIELD_TYPE
Field "#TITLE#" must be of type #TYPE#.
Field #TITLE# must be of type #TYPE#
SOURCE_NOT_FOUND
Source was not found.
Source not found
SOURCE_CREATE_CONNECTION_ERROR
Cannot create connection.
Error creating connection
SOURCE_UPDATE_CONNECTION_ERROR
Cannot update connection.
Error updating connection
BX_ERROR
Cannot delete source. Delete all related datasets first.
Cannot delete source while related datasets exist
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
Create Source biconnector.source.add
Get Source by ID biconnector.source.get
Get the list of sources biconnector.source.list
Delete source biconnector.source.delete
Get Source Fields of biconnector.source.fields
Copied
Was the article helpful?
Yes
No
Previous
Create source
Next
Get source by id

---

## Get Source by ID biconnector.source.get

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/source/biconnector-source-get

Get Source by ID biconnector.source.get | Bitrix24 REST API and Marketplace Applications
Get Source by ID biconnector.source.get
Get Source by ID biconnector.source.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: user with access to the "Analyst Workspace" section
The method
biconnector.source.get
returns information about the source by its identifier.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the source, which can be obtained using the methods
biconnector.source.list
and
biconnector.source.add
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
'{"id":6}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.source.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":6,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/biconnector.source.get
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.source.get'
,
{
id
:
6
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
() ?
console
.
error
(result.
error
()) :
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
'biconnector.source.get'
,
[
'id'
=>
6
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
'Error getting source: '
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
'biconnector.source.get'
,
{
id
:
6
,
},
(
result
) =>
{
result.
error
() ?
console
.
error
(result.
error
()) :
console
.
info
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
'biconnector.source.get'
,
[
'id'
=>
6
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
"connection"
:
{
"id"
:
6
,
"type"
:
"rest"
,
"code"
:
"rest_1"
,
"title"
:
"Rest source SQL"
,
"description"
:
"Connection for working with mySql"
,
"active"
:
true
,
"dateCreate"
:
"2025-03-20 14:50:06"
,
"dateUpdate"
:
"2025-03-20 14:50:06"
,
"createdById"
:
1
,
"updatedById"
:
1
}
,
"connectorId"
:
1
,
"settings"
:
[
{
"code"
:
"token"
,
"name"
:
"Token"
,
"type"
:
"STRING"
,
"value"
:
"beliberda"
,
"id"
:
8
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
1742929480.368097
,
"finish"
:
1742929480.449558
,
"duration"
:
0.08146095275878906
,
"processing"
:
0.006555080413818359
,
"date_start"
:
"2025-03-25T19:04:40+00:00"
,
"date_finish"
:
"2025-03-25T19:04:40+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
item
Root element of the response. Contains information about the source fields. Field descriptions can be found in the article
Sources: Overview of Methods
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP Status:
200
{
"error"
:
"VALIDATION_ID_NOT_PROVIDED"
,
"error_description"
:
"ID is missing."
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
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not provided
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
SOURCE_NOT_FOUND
Source was not found.
Source not found
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
Change source biconnector.source.update
Create Source biconnector.source.add
Get the list of sources biconnector.source.list
Delete source biconnector.source.delete
Get Source Fields of biconnector.source.fields
Copied
Was the article helpful?
Yes
No
Previous
Update source
Next
Get list of sources

---

## Get the list of sources biconnector.source.list

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/source/biconnector-source-list

Get the list of sources biconnector.source.list | Bitrix24 REST API and Marketplace Applications
Get the list of sources biconnector.source.list
Get the list of sources biconnector.source.list
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: a user with access to the "Analyst Workspace" section
The method
biconnector.source.list
returns a list of sources based on a filter. It is an implementation of the list method for sources.
Method Parameters
Method Parameters
Name
type
Description
select
string[]
List of fields that must be filled in the sources in the selection. By default, all fields are taken
filter
object
Filter for selecting sources. Example format:
{
"field_1"
:
"value_1"
,
"field_2"
:
"value_2"
}
You can add a prefix to the keys
field_n
to clarify the filter's operation.
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
symbol in the filter value does not need to be passed. The search looks for a substring in any position of the string
=%
— LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
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
=
— equal, exact match (used by default)
!=
— not equal
!
— not equal
The list of available fields for filtering can be found using the method
biconnector.source.fields
.
The filter does not support the
settings
field; it will be ignored
order
object
Sorting parameters. Example format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
field_n
— the name of the field by which the sources will be sorted
value_n
— a
string
type value, equal to:
ASC
— ascending sort
DESC
— descending sort
page
integer
Controls pagination. The page size of results is 50 records. To navigate through results, pass the page number
Code Examples
Code Examples
How to Use Examples in Documentation
Get the list of sources where:
the name starts with
Sql
the description is not empty
the connector ID is equal to
2
or
4
Display only the necessary fields:
ID
id
Title
title
Active
active
Creation date
dateCreate
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
'{"select":["id","title","active","dateCreate"],"filter":{"%=title":"Sql%","!description":"","@connectorId":[2,4]},"order":{"dateCreate":"DESC"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.source.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"select":["id","title","active","dateCreate"],"filter":{"%=title":"Sql%","!description":"","@connectorId":[2,4]},"order":{"dateCreate":"DESC"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/biconnector.source.list
// callListMethod is recommended when you need to get the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
const
selectFields = [
"id"
,
"title"
,
"active"
,
"dateCreate"
];
try
{
const
response =
await
$b24.
callListMethod
(
'biconnector.source.list'
,
{
select
: selectFields,
filter
: {
'%=title'
:
"Sql%"
,
'!description'
:
""
,
"@connectorId"
: [
2
,
4
]
},
order
: {
dateCreate
:
"DESC"
}
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
const
selectFields = [
"id"
,
"title"
,
"active"
,
"dateCreate"
];
try
{
const
generator = $b24.
fetchListMethod
(
'biconnector.source.list'
, {
select
: selectFields,
filter
: {
'%=title'
:
"Sql%"
,
'!description'
:
""
,
"@connectorId"
: [
2
,
4
]
},
order
: {
dateCreate
:
"DESC"
}
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
const
selectFields = [
"id"
,
"title"
,
"active"
,
"dateCreate"
];
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.source.list'
, {
select
: selectFields,
filter
: {
'%=title'
:
"Sql%"
,
'!description'
:
""
,
"@connectorId"
: [
2
,
4
]
},
order
: {
dateCreate
:
"DESC"
}
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
$response
=
$b24Service
->core
->
call
(
'biconnector.source.list'
,
[
'select'
=> [
"id"
,
"title"
,
"active"
,
"dateCreate"
],
'filter'
=> [
'%=title'
=>
"Sql%"
,
'!description'
=>
""
,
"@connectorId"
=> [
2
,
4
]
],
'order'
=> [
'dateCreate'
=>
"DESC"
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
'Error fetching source list: '
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
'biconnector.source.list'
,
{
select
: [
"id"
,
"title"
,
"active"
,
"dateCreate"
],
filter
: {
'%=title'
:
"Sql%"
,
'!description'
:
""
,
"@connectorId"
: [
2
,
4
]
},
order
: {
dateCreate
:
"DESC"
}
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
'biconnector.source.list'
,
[
'select'
=> [
"id"
,
"title"
,
"active"
,
"dateCreate"
],
'filter'
=> [
'%=title'
=>
"Sql%"
,
'!description'
=>
""
,
'@connectorId'
=> [
2
,
4
]
],
'order'
=> [
'dateCreate'
=>
"DESC"
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
"id"
:
"11"
,
"title"
:
"Sql_host"
,
"active"
:
true
,
"dateCreate"
:
"2025-03-24 07:25:59"
}
,
{
"id"
:
"10"
,
"title"
:
"Sql_partner"
,
"active"
:
false
,
"dateCreate"
:
"2025-03-21 12:22:32"
}
]
,
"time"
:
{
"start"
:
1742804947.923552
,
"finish"
:
1742804947.995446
,
"duration"
:
0.07189393043518066
,
"processing"
:
0.0017020702362060547
,
"date_start"
:
"2025-03-24T08:29:07+00:00"
,
"date_finish"
:
"2025-03-24T08:29:07+00:00"
}
}
Returned Data
Returned Data
result
object
The root element of the response. Contains an array of objects with information about the fields of the sources.
It should be noted that the structure of the fields may change due to the
select
parameter
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
"VALIDATION_SELECT_TYPE"
,
"error_description"
:
"Parameter \"select\" must be array."
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
VALIDATION_SELECT_TYPE
Parameter "select" must be array.
The
select
parameter is not an object
VALIDATION_FILTER_TYPE
Parameter "filter" must be array.
The
filter
parameter is not an object
VALIDATION_ORDER_TYPE
Parameter "order" must be array.
The
order
parameter is not an object
VALIDATION_FIELD_NOT_ALLOWED_IN_SELECT
Field "#TITLE#" is not allowed in the "select".
These fields are not allowed in the selection
VALIDATION_FIELD_NOT_ALLOWED_IN_FILTER
Field "#TITLE#" is not allowed in the "filter".
These fields are not allowed in the filter
VALIDATION_FIELD_NOT_ALLOWED_IN_ORDER
Field "#TITLE#" is not allowed in the "order".
These fields are not allowed for sorting
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
Change source biconnector.source.update
Get Source by ID biconnector.source.get
Create Source biconnector.source.add
Delete source biconnector.source.delete
Get Source Fields of biconnector.source.fields
Copied
Was the article helpful?
Yes
No
Previous
Get source by id
Next
Delete source

---

## Delete source biconnector.source.delete

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/source/biconnector-source-delete

Delete source biconnector.source.delete | Bitrix24 REST API and Marketplace Applications
Delete source biconnector.source.delete
Delete source biconnector.source.delete
Method parameters
Code examples
Response handling
Returned data
Error handling
Possible error codes
Statuses and System Error Codes
Continue exploring
Scope:
biconnector
Who can execute the method: user with access to the "Analyst's workspace" section
The method
biconnector.source.delete
removes an existing connection.
A connection can be deleted if it has no datasets.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the connection, can be obtained using the methods
biconnector.source.list
or
biconnector.source.add
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
'{"id":4}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.source.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":4,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/biconnector.source.delete
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.source.delete'
,
{
id
:
4
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
() ?
console
.
error
(result.
error
()) :
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
'biconnector.source.delete'
,
[
'id'
=>
4
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
'Info: '
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
'Error deleting source: '
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
'biconnector.source.delete'
,
{
id
:
4
,
},
(
result
) =>
{
result.
error
() ?
console
.
error
(result.
error
()) :
console
.
info
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
'biconnector.source.delete'
,
[
'id'
=>
4
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
1725365418.056843
,
"finish"
:
1725365419.671506
,
"duration"
:
1.6146628856658936
,
"processing"
:
1.3475170135498047
,
"date_start"
:
"2024-09-03T14:10:18+02:00"
,
"date_finish"
:
"2024-09-03T14:10:19+02:00"
}
}
Returned data
Returned data
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
Information about the execution time of the request
Error handling
Error handling
HTTP status:
200
{
"error"
:
"VALIDATION_ID_NOT_PROVIDED"
,
"error_description"
:
"ID is missing."
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
Description
Value
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not specified
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
SOURCE_NOT_FOUND
Source was not found.
Source not found
BX_ERROR
Cannot delete source. Delete all related datasets first.
Cannot delete source while related datasets exist
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
Change source biconnector.source.update
Get Source by ID biconnector.source.get
Get the list of sources biconnector.source.list
Create Source biconnector.source.add
Get Source Fields of biconnector.source.fields
Copied
Was the article helpful?
Yes
No
Previous
Get list of sources
Next
Get source fields

---

## Get Source Fields of biconnector.source.fields

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/source/biconnector-source-fields

Get Source Fields of biconnector.source.fields | Bitrix24 REST API and Marketplace Applications
Get Source Fields of biconnector.source.fields
Get Source Fields of biconnector.source.fields
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: any user
The method
biconnector.source.fields
returns a description of the source fields. A table with the description of standard fields can be found in the article
Sources: Overview of Methods
.
Method Parameters
Method Parameters
No parameters.
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
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.source.fields
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
https://**put_your_bitrix24_address**/rest/biconnector.source.fields
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.source.fields'
,
{}
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
'biconnector.source.fields'
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
'Error fetching source fields: '
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
'biconnector.source.fields'
,
{},
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
'biconnector.source.fields'
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
{
"fields"
:
[
{
"title"
:
"id"
,
"type"
:
"integer"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"title"
,
"type"
:
"string"
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
}
,
{
"title"
:
"type"
,
"type"
:
"string"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"code"
,
"type"
:
"string"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"description"
,
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
}
,
{
"title"
:
"active"
,
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
}
,
{
"title"
:
"dateCreate"
,
"type"
:
"datetime"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"dateUpdate"
,
"type"
:
"datetime"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"createdById"
,
"type"
:
"integer"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"updatedById"
,
"type"
:
"integer"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"connectorId"
,
"type"
:
"integer"
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
true
,
"isMultiple"
:
false
}
,
{
"title"
:
"settings"
,
"type"
:
"array"
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
true
}
]
}
,
"time"
:
{
"start"
:
1742896156.448294
,
"finish"
:
1742896156.503291
,
"duration"
:
0.05499696731567383
,
"processing"
:
0.0004570484161376953
,
"date_start"
:
"2025-03-25T09:49:16+00:00"
,
"date_finish"
:
"2025-03-25T09:49:16+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
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
— source field
value_n
—
field information
time
time
Information about the request execution time
Error Handling
Error Handling
The method does not return errors.
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
Change source biconnector.source.update
Get Source by ID biconnector.source.get
Get the list of sources biconnector.source.list
Delete source biconnector.source.delete
Create Source biconnector.source.add
Copied
Was the article helpful?
Yes
No
Previous
Delete source
Next
Overview of methods

---

## Datasets: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/dataset/index

Datasets: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Connection of Dataset with Connector and Sources
Datasets: Overview of Methods
Connection of Dataset with Connector and Sources
Description of Dataset Fields
Description of the Fields Field
Overview of Methods
A dataset is an object of the BIconnector module. Datasets are used to display and process information in Bitrix24 obtained from sources.
Quick navigation:
all methods
Methods work only in the context of the
application
Connection of Dataset with Connector and Sources
Connection of Dataset with Connector and Sources
A dataset is the final level in the hierarchy of data handling in the BIconnector module:
Connector
establishes a connection with an external data source.
Source
defines which specific data is available from the connected service.
Dataset
forms the final set of data that can be used in reports and analytics.
Description of Dataset Fields
Description of Dataset Fields
Name
type
Description
Read
Write
id
integer
Unique identifier of the dataset
✅
❌
type
string
Type of the dataset, the value is always
rest
✅
❌
name
string
Name of the dataset
✅
✅
description
string
Description of the dataset
✅
✅
externalCode
string
External code of the dataset
✅
✅
externalName
string
External name of the dataset
✅
✅
dateCreate
datetime
Creation date of the dataset
✅
❌
dateUpdate
datetime
Update date of the dataset
✅
❌
createdById
integer
Identifier of the user who created the dataset
✅
❌
updatedById
integer
Identifier of the user who updated the dataset
✅
❌
externalId
integer
External identifier of the dataset
✅
❌
fields
array
List of
fields
included in the dataset
✅
✅
Description of the Fields Field
Description of the Fields Field
Name
type
Description
Read
Write
id
integer
Identifier of the field
✅
❌
datasetId
integer
Identifier of the dataset to which the field belongs
✅
✅
type
string
Data type. Available types:
int
— integer
string
— string
double
— decimal number, separator is a dot
date
— date, format
Y-m-d
datetime
— date with time, format
Y-m-d H:i:s
✅
✅
name
string
Name of the field. The name must start with a letter and can only use uppercase Latin letters
A-Z
, digits, and the
_
sign. The maximum length of the name is 32 characters
✅
✅
externalCode
string
External code of the field
✅
✅
visible
boolean
Field visibility flag
✅
✅
Overview of Methods
Overview of Methods
Scope:
biconnector
Who can perform methods: a user with access to the "Analyst's Workspace" section
Method
Description
biconnector.dataset.add
Adds a new dataset
biconnector.dataset.update
Updates an existing dataset
biconnector.dataset.fields.update
Updates the fields of the dataset
biconnector.dataset.get
Returns information about the dataset
biconnector.dataset.list
Returns a list of available datasets
biconnector.dataset.delete
Deletes a dataset
biconnector.dataset.fields
Returns the description of the dataset fields
Copied
Was the article helpful?
Yes
No
Previous
Get source fields
Next
Create dataset

---

## Create Dataset biconnector.dataset.add

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/dataset/biconnector-dataset-add

Create Dataset biconnector.dataset.add | Bitrix24 REST API and Marketplace Applications
Create Dataset biconnector.dataset.add
Create Dataset biconnector.dataset.add
Method Parameters
Parameter fields
Code Examples
Response Handling
Returned Data
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: a user with access to the "Analyst's Workspace" section
The method
biconnector.dataset.add
creates a new dataset associated with a data source.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
An object containing data to create a new dataset. The object format is:
{
"field_1": "value_1",
"field_2": "value_2",
...,
"field_n": "value_n"
}
field_n
— field name
value_n
— field value
Detailed description below
Parameter fields
Parameter fields
Name
type
Description
name
*
string
The name of the dataset. The name must start with a letter and can only use lowercase Latin letters
a-z
, numbers, and the underscore
_
. The maximum length of the name is 230 characters.
externalName
*
string
The name of the dataset in the external source, in the application.
externalCode
*
string
A unique code for the dataset in the external source, used when retrieving data.
sourceId
*
integer
The identifier of the source, which can be obtained using the methods
biconnector.source.list
or
biconnector.source.add
.
description
string
Description of the dataset.
fields
*
array
A list of dataset fields,
(Detailed description)
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
'{
"fields": {
"sourceId": 3,
"name": "rest_dataset",
"externalName": "externalName",
"externalCode": "externalCode",
"description": "Dataset description",
"fields": [
{ "type": "int", "name": "ID", "externalCode": "ID" },
{ "type": "string", "name": "NAME", "externalCode": "NAME" },
{ "type": "string", "name": "SURNAME", "externalCode": "SURNAME" },
{ "type": "double", "name": "SCORE", "externalCode": "SCORE" },
{ "type": "date", "name": "DATE", "externalCode": "DATE" },
{ "type": "datetime", "name": "TIME", "externalCode": "TIME" }
]
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.dataset.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"fields": {
"sourceId": 3,
"name": "rest_dataset",
"externalName": "externalName",
"externalCode": "externalCode",
"description": "Dataset description",
"fields": [
{ "type": "int", "name": "ID", "externalCode": "ID" },
{ "type": "string", "name": "NAME", "externalCode": "NAME" },
{ "type": "string", "name": "SURNAME", "externalCode": "SURNAME" },
{ "type": "double", "name": "SCORE", "externalCode": "SCORE" },
{ "type": "date", "name": "DATE", "externalCode": "DATE" },
{ "type": "datetime", "name": "TIME", "externalCode": "TIME" }
]
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.dataset.add
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.dataset.add'
,
{
fields
: {
"sourceId"
:
3
,
"name"
:
"rest_dataset"
,
"externalName"
:
"externalName"
,
"externalCode"
:
"externalCode"
,
"description"
:
"Dataset description"
,
"fields"
: [
{
"type"
:
"int"
,
"name"
:
"ID"
,
"externalCode"
:
"ID"
},
{
"type"
:
"string"
,
"name"
:
"NAME"
,
"externalCode"
:
"NAME"
},
{
"type"
:
"string"
,
"name"
:
"SURNAME"
,
"externalCode"
:
"SURNAME"
},
{
"type"
:
"double"
,
"name"
:
"SCORE"
,
"externalCode"
:
"SCORE"
},
{
"type"
:
"date"
,
"name"
:
"DATE"
,
"externalCode"
:
"DATE"
},
{
"type"
:
"datetime"
,
"name"
:
"TIME"
,
"externalCode"
:
"TIME"
}
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
'biconnector.dataset.add'
,
[
'fields'
=> [
'sourceId'
=>
3
,
'name'
=>
'rest_dataset'
,
'externalName'
=>
'externalName'
,
'externalCode'
=>
'externalCode'
,
'description'
=>
'Dataset description'
,
'fields'
=> [
[
'type'
=>
'int'
,
'name'
=>
'ID'
,
'externalCode'
=>
'ID'
],
[
'type'
=>
'string'
,
'name'
=>
'NAME'
,
'externalCode'
=>
'NAME'
],
[
'type'
=>
'string'
,
'name'
=>
'SURNAME'
,
'externalCode'
=>
'SURNAME'
],
[
'type'
=>
'double'
,
'name'
=>
'SCORE'
,
'externalCode'
=>
'SCORE'
],
[
'type'
=>
'date'
,
'name'
=>
'DATE'
,
'externalCode'
=>
'DATE'
],
[
'type'
=>
'datetime'
,
'name'
=>
'TIME'
,
'externalCode'
=>
'TIME'
],
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
'Error adding dataset: '
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
'biconnector.dataset.add'
,
{
fields
: {
"sourceId"
:
3
,
"name"
:
"rest_dataset"
,
"externalName"
:
"externalName"
,
"externalCode"
:
"externalCode"
,
"description"
:
"Dataset description"
,
"fields"
: [
{
"type"
:
"int"
,
"name"
:
"ID"
,
"externalCode"
:
"ID"
},
{
"type"
:
"string"
,
"name"
:
"NAME"
,
"externalCode"
:
"NAME"
},
{
"type"
:
"string"
,
"name"
:
"SURNAME"
,
"externalCode"
:
"SURNAME"
},
{
"type"
:
"double"
,
"name"
:
"SCORE"
,
"externalCode"
:
"SCORE"
},
{
"type"
:
"date"
,
"name"
:
"DATE"
,
"externalCode"
:
"DATE"
},
{
"type"
:
"datetime"
,
"name"
:
"TIME"
,
"externalCode"
:
"TIME"
}
]
}
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
'biconnector.dataset.add'
,
[
'fields'
=> [
'sourceId'
=>
3
,
'name'
=>
'rest_dataset'
,
'externalName'
=>
'externalName'
,
'externalCode'
=>
'externalCode'
,
'description'
=>
'Dataset description'
,
'fields'
=> [
[
'type'
=>
'int'
,
'name'
=>
'ID'
,
'externalCode'
=>
'ID'
],
[
'type'
=>
'string'
,
'name'
=>
'NAME'
,
'externalCode'
=>
'NAME'
],
[
'type'
=>
'string'
,
'name'
=>
'SURNAME'
,
'externalCode'
=>
'SURNAME'
],
[
'type'
=>
'double'
,
'name'
=>
'SCORE'
,
'externalCode'
=>
'SCORE'
],
[
'type'
=>
'date'
,
'name'
=>
'DATE'
,
'externalCode'
=>
'DATE'
],
[
'type'
=>
'datetime'
,
'name'
=>
'TIME'
,
'externalCode'
=>
'TIME'
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
{
"id"
:
10
}
,
"time"
:
{
"start"
:
1725013197.635808
,
"finish"
:
1725013198.580873
,
"duration"
:
0.9450650215148926
,
"processing"
:
0.6822988986968994
,
"date_start"
:
"2024-08-30T12:19:57+02:00"
,
"date_finish"
:
"2024-08-30T12:19:58+02:00"
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
integer
The root element of the response, contains the identifier of the created dataset.
time
time
Information about the request execution time.
HTTP status:
200
{
"error"
:
"VALIDATION_FIELDS_NOT_PROVIDED"
,
"error_description"
:
"Fields not provided."
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
VALIDATION_FIELDS_NOT_PROVIDED
Fields not provided.
Fields were not passed in the request.
VALIDATION_UNKNOWN_PARAMETERS
Unknown parameters: #LIST_OF_PARAMS#
Unknown parameters detected: list.
VALIDATION_REQUIRED_FIELD_MISSING
Field "#TITLE#" is required.
Required field #TITLE# was not provided.
VALIDATION_READ_ONLY_FIELD
Field "#TITLE#" is read only.
Field #TITLE# is read-only and cannot be modified.
VALIDATION_IMMUTABLE_FIELD
Field "#TITLE#" is immutable.
Field #TITLE# is immutable.
VALIDATION_INVALID_FIELD_TYPE
Field "#TITLE#" must be of type #TYPE#.
Field #TITLE# must be of type #TYPE#.
SOURCE_NOT_FOUND
Source was not found.
Source not found.
DATASET_ALREADY_EXIST
Dataset with this name already exists.
A dataset with this name already exists.
VALIDATION_DATASET_NAME_INVALID
Dataset name has to start with a lowercase Latin character. Possible entry includes lowercase Latin characters (a-z), numbers (0-9) and underscores.
Incorrect dataset name format. The name must start with a letter and can only use lowercase Latin letters
(a-z)
, numbers, and the underscore
_
.
VALIDATION_DATASET_NAME_TOO_LONG
Dataset name must not exceed 230 characters.
Dataset name must not exceed 230 characters.
VALIDATION_DUPLICATE_FIELD_CODE
Duplicate values found in the "code" parameter: #LIST_CODES#
Duplicates found in the
externalCode
parameter of dataset fields.
VALIDATION_DUPLICATE_FIELD_NAME
Duplicate values found in the "name" parameter: #LIST_NAMES#
Duplicates found in the
name
parameter of dataset fields.
VALIDATION_FIELD_MISSING_REQUIRED_PARAMETERS
Field must include the required parameters: "name", "externalCode" and "type".
Field must include the parameters
name
,
externalCode
, and
type
.
VALIDATION_FIELD_NAME_INVALID_FORMAT
Field "name" has to start with an uppercase Latin character. Possible entry includes uppercase Latin characters (A-Z), numbers (0-9) and underscores.
Incorrect field name format. The name must start with a letter and can only use uppercase Latin letters
(A-Z)
, numbers, and the underscore
_
.
VALIDATION_FIELD_NAME_TOO_LONG
Field "name" must not exceed 32 characters.
Field name must not exceed 32 characters.
VALIDATION_FIELD_INVALID_TYPE
Invalid field type.
Invalid field type.
-
Error adding dataset
Error adding dataset.
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
Get Fields of the Dataset biconnector.dataset.fields
Update Dataset biconnector.dataset.update
Update Dataset Fields biconnector.dataset.fields.update
Get dataset by id biconnector.dataset.get
Get the list of datasets biconnector.dataset.list
Delete dataset biconnector.dataset.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of methods
Next
Update dataset

---

## Update Dataset biconnector.dataset.update

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/dataset/biconnector-dataset-update

Update Dataset biconnector.dataset.update | Bitrix24 REST API and Marketplace Applications
Update Dataset biconnector.dataset.update
Update Dataset biconnector.dataset.update
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
biconnector
Who can execute the method: a user with access to the "Analyst Workspace" section
The method
biconnector.dataset.update
updates an existing dataset.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the dataset, can be obtained using the methods
biconnector.dataset.list
and
biconnector.dataset.add
fields
*
object
An object containing the updated data.
Object format:
{
"field_1": "value_1",
"field_2": "value_2",
...,
"field_n": "value_n"
}
field_n
— field name
value_n
— field value
Detailed description below
Parameter fields
Parameter fields
Name
type
Description
description
string
Description of the dataset
To change the fields of the dataset, use the method
biconnector.dataset.fields.update
.
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
'{
"id": 10,
"fields": {
"description": "New description"
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.dataset.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"id": 10,
"fields": {
"description": "New description"
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.dataset.update
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.dataset.update'
,
{
id
:
10
,
fields
: {
"description"
:
"New description"
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
'biconnector.dataset.update'
,
[
'id'
=>
10
,
'fields'
=> [
"description"
=>
"New description"
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
'Error updating dataset: '
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
'biconnector.dataset.update'
,
{
id
:
10
,
fields
: {
"description"
:
"New description"
,
}
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
'biconnector.dataset.update'
,
[
'id'
=>
10
,
'fields'
=> [
'description'
=>
'New description'
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
1725365418.056843
,
"finish"
:
1725365419.671506
,
"duration"
:
1.6146628856658936
,
"processing"
:
1.3475170135498047
,
"date_start"
:
"2024-09-03T14:10:18+02:00"
,
"date_finish"
:
"2024-09-03T14:10:19+02:00"
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
200
{
"error"
:
"VALIDATION_FIELDS_NOT_PROVIDED"
,
"error_description"
:
"Fields not provided."
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
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not specified
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
VALIDATION_FIELDS_NOT_PROVIDED
Fields not provided.
Fields were not passed in the request
VALIDATION_UNKNOWN_PARAMETERS
Unknown parameters: #LIST_OF_PARAMS#
Unknown parameters detected: #LIST_OF_PARAMS#.
VALIDATION_REQUIRED_FIELD_MISSING
Field "#TITLE#" is required.
Required field #TITLE# was not provided
VALIDATION_READ_ONLY_FIELD
Field "#TITLE#" is read only.
Field #TITLE# is read-only and cannot be modified
VALIDATION_IMMUTABLE_FIELD
Field "#TITLE#" is immutable.
Field #TITLE# is immutable
VALIDATION_INVALID_FIELD_TYPE
Field "#TITLE#" must be of type #TYPE#.
Field #TITLE# must be of type #TYPE#
DATASET_NOT_FOUND
Dataset was not found.
Dataset not found
INVALID_METHOD
Use the method "biconnector.dataset.fields.update" to update the dataset fields.
To update fields, use the method
biconnector.dataset.fields.update
-
Error updating dataset.
Error updating dataset
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
Create Dataset biconnector.dataset.add
Get Fields of the Dataset biconnector.dataset.fields
Update Dataset Fields biconnector.dataset.fields.update
Get dataset by id biconnector.dataset.get
Get the list of datasets biconnector.dataset.list
Delete dataset biconnector.dataset.delete
Copied
Was the article helpful?
Yes
No
Previous
Create dataset
Next
Modify dataset fields

---

## Update Dataset Fields biconnector.dataset.fields.update

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/dataset/biconnector-dataset-fields-update

Update Dataset Fields biconnector.dataset.fields.update | Bitrix24 REST API and Marketplace Applications
Update Dataset Fields biconnector.dataset.fields.update
Update Dataset Fields biconnector.dataset.fields.update
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: user with access to the "Analyst's workspace" section
The method
biconnector.dataset.fields.update
updates the fields of an existing dataset.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the dataset, can be obtained using the methods
biconnector.dataset.list
or
biconnector.dataset.add
add
object
Object containing an array of fields to be added with the following structure:
{
"type" : "int",
"name": "NAME",
"externalCode":"NAME"
},
type
— field type
name
— field name
externalCode
— external code of the field
update
object
Object containing an array of fields to be updated with the following structure:
{
"id": 12,
"visible": false
},
id
— Identifier of the field, can be obtained using the method
biconnector.dataset.get
visible
— visibility of the field
delete
int[]
Object containing an array of field identifiers for deletion. Field identifiers can be obtained using the method
biconnector.dataset.get
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
'{
"id": 10,
"add": [
{
"type": "int",
"name": "NAME",
"externalCode": "NAME"
},
{
"type": "int",
"name": "ID",
"externalCode": "ID"
}
],
"update": [
{
"id": 12,
"visible": false
},
{
"id": 13,
"visible": true
}
],
"delete": [
14,
15
]
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.dataset.fields.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"id": 10,
"add": [
{
"type": "int",
"name": "NAME",
"externalCode": "NAME"
},
{
"type": "int",
"name": "ID",
"externalCode": "ID"
}
],
"update": [
{
"id": 12,
"visible": false
},
{
"id": 13,
"visible": true
}
],
"delete": [
14,
15
],
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.dataset.fields.update
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.dataset.fields.update'
,
{
id
:
10
,
add
: [
{
type
:
"int"
,
name
:
"NAME"
,
externalCode
:
"NAME"
},
{
type
:
"int"
,
name
:
"ID"
,
externalCode
:
"ID"
}
],
update
: [
{
"id"
:
12
,
"visible"
:
false
},
{
"id"
:
13
,
"visible"
:
true
}
],
delete
: [
14
,
15
]
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
'biconnector.dataset.fields.update'
,
[
'id'
=>
10
,
'add'
=> [
[
'type'
=>
"int"
,
'name'
=>
"NAME"
,
'externalCode'
=>
"NAME"
],
[
'type'
=>
"int"
,
'name'
=>
"ID"
,
'externalCode'
=>
"ID"
]
],
'update'
=> [
[
'id'
=>
12
,
'visible'
=>
false
],
[
'id'
=>
13
,
'visible'
=>
true
]
],
'delete'
=> [
14
,
15
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
'Error updating dataset fields: '
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
'biconnector.dataset.fields.update'
,
{
id
:
10
,
add
: [
{
type
:
"int"
,
name
:
"NAME"
,
externalCode
:
"NAME"
},
{
type
:
"int"
,
name
:
"ID"
,
externalCode
:
"ID"
}
],
update
: [
{
"id"
:
12
,
"visible"
:
false
},
{
"id"
:
13
,
"visible"
:
true
}
],
delete
: [
14
,
15
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
'biconnector.dataset.fields.update'
,
[
'id'
=>
10
,
'add'
=> [
[
'type'
=>
'int'
,
'name'
=>
'NAME'
,
'externalCode'
=>
'NAME'
],
[
'type'
=>
'int'
,
'name'
=>
'ID'
,
'externalCode'
=>
'ID'
]
],
'update'
=> [
[
'id'
=>
12
,
'visible'
=>
false
],
[
'id'
=>
13
,
'visible'
=>
true
]
],
'delete'
=> [
14
,
15
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
1725365418.056843
,
"finish"
:
1725365419.671506
,
"duration"
:
1.6146628856658936
,
"processing"
:
1.3475170135498047
,
"date_start"
:
"2024-09-03T14:10:18+02:00"
,
"date_finish"
:
"2024-09-03T14:10:19+02:00"
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
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
"VALIDATION_ID_NOT_PROVIDED"
,
"error_description"
:
"ID is missing."
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
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not specified
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
DATASET_NOT_FOUND
Dataset was not found.
Dataset not found
DATASET_UPDATE_ERROR
Error updating dataset.
Error updating dataset
VALIDATION_DUPLICATE_FIELD_CODE
Duplicate values found in the "code" parameter: #LIST_CODES#
Duplicates found in the
externalCode
parameter of dataset fields
VALIDATION_DUPLICATE_FIELD_NAME
Duplicate values found in the "name" parameter: #LIST_NAMES#
Duplicates found in the
name
parameter of dataset fields
VALIDATION_FIELD_NAME_INVALID_FORMAT
Field "name" has to start with an uppercase Latin character. Possible entry includes uppercase Latin characters (A-Z), numbers (0-9) and underscores.
Incorrect field name format. The name must start with a letter, only uppercase Latin letters
(A-Z)
, numbers, and
_
are allowed
VALIDATION_FIELD_NAME_TOO_LONG
Field "name" must not exceed 32 characters.
Field name must not exceed 32 characters
VALIDATION_FIELD_INVALID_TYPE
Invalid field type.
Incorrect field type
VALIDATION_DUPLICATE_EXIST_CODE
The following "externalCode" values already exist in the current fields: #LIST_CODES#
Fields with this
externalCode
parameter already exist
VALIDATION_DUPLICATE_EXIST_NAME
The following "name" values already exist in the current fields: #LIST_NAMES#
Fields with this
name
parameter already exist
VALIDATION_FIELD_ADD_MISSING_REQUIRED_FIELDS
Field to be added must include the required parameters: "name", "externalCode" and "type".
Field to be added must include
name
,
externalCode
, and
type
parameters
VALIDATION_FIELD_UPDATE_MISSING_REQUIRED_FIELDS
Field to be updated must include the required parameters: "id" and "visible".
Field to be updated must include
id
and
visible
parameters
VALIDATION_FIELD_DELETE_INVALID_ID
ID to be deleted must be a positive integer.
Invalid
id
format for deletion
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
Create Dataset biconnector.dataset.add
Update Dataset biconnector.dataset.update
Get Fields of the Dataset biconnector.dataset.fields
Get dataset by id biconnector.dataset.get
Get the list of datasets biconnector.dataset.list
Delete dataset biconnector.dataset.delete
Copied
Was the article helpful?
Yes
No
Previous
Update dataset
Next
Get dataset by id

---

## Get dataset by id biconnector.dataset.get

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/dataset/biconnector-dataset-get

Get dataset by id biconnector.dataset.get | Bitrix24 REST API and Marketplace Applications
Get dataset by id biconnector.dataset.get
Get dataset by id biconnector.dataset.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: user with access to the "Analyst's workspace" section
The method
biconnector.dataset.get
returns information about a dataset by its identifier.
Method Parameters
Method Parameters
Name
type
Description
id
*
integer
Identifier of the dataset, which can be obtained using the methods
biconnector.dataset.list
and
biconnector.dataset.add
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
'{"id":2}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.dataset.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":2,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/biconnector.dataset.get
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.dataset.get'
,
{
id
:
2
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
'biconnector.dataset.get'
,
[
'id'
=>
2
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
'Error getting dataset: '
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
'biconnector.dataset.get'
,
{
id
:
2
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
'biconnector.dataset.get'
,
[
'id'
=>
2
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
"item"
:
{
"id"
:
2
,
"type"
:
"rest"
,
"name"
:
"rest_dataset11111"
,
"description"
:
"new__2_"
,
"externalCode"
:
"extrnalCode"
,
"externalName"
:
"extranalName"
,
"dateCreate"
:
"2025-03-26 15:28:06"
,
"dateUpdate"
:
"2025-03-27 07:47:43"
,
"createdById"
:
1
,
"updatedById"
:
1
,
"externalId"
:
275
,
"fields"
:
[
{
"id"
:
224
,
"datasetId"
:
2
,
"type"
:
"int"
,
"name"
:
"ID"
,
"externalCode"
:
"ID"
,
"visible"
:
true
}
,
{
"id"
:
225
,
"datasetId"
:
2
,
"type"
:
"string"
,
"name"
:
"NAME"
,
"externalCode"
:
"NAME"
,
"visible"
:
true
}
,
{
"id"
:
226
,
"datasetId"
:
2
,
"type"
:
"string"
,
"name"
:
"SURNAME"
,
"externalCode"
:
"SURNAME"
,
"visible"
:
true
}
,
{
"id"
:
227
,
"datasetId"
:
2
,
"type"
:
"double"
,
"name"
:
"SCORE"
,
"externalCode"
:
"SCORE"
,
"visible"
:
true
}
,
{
"id"
:
228
,
"datasetId"
:
2
,
"type"
:
"date"
,
"name"
:
"DATA"
,
"externalCode"
:
"DATA"
,
"visible"
:
true
}
,
{
"id"
:
229
,
"datasetId"
:
2
,
"type"
:
"datetime"
,
"name"
:
"TIME"
,
"externalCode"
:
"TIME"
,
"visible"
:
true
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
1743061675.963969
,
"finish"
:
1743061676.064591
,
"duration"
:
0.10062193870544434
,
"processing"
:
0.011152029037475586
,
"date_start"
:
"2025-03-27T07:47:55+00:00"
,
"date_finish"
:
"2025-03-27T07:47:56+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
item
Root element of the response. Contains information about the dataset fields. Field descriptions can be found in the article
Datasets: Overview of Methods
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
"VALIDATION_ID_NOT_PROVIDED"
,
"error_description"
:
"ID is missing."
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
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not provided
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
DATASET_NOT_FOUND
Dataset was not found.
Dataset not found
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
Create Dataset biconnector.dataset.add
Update Dataset biconnector.dataset.update
Update Dataset Fields biconnector.dataset.fields.update
Get Fields of the Dataset biconnector.dataset.fields
Get the list of datasets biconnector.dataset.list
Delete dataset biconnector.dataset.delete
Copied
Was the article helpful?
Yes
No
Previous
Modify dataset fields
Next
Get list of datasets

---

## Get the list of datasets biconnector.dataset.list

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/dataset/biconnector-dataset-list

Get the list of datasets biconnector.dataset.list | Bitrix24 REST API and Marketplace Applications
Get the list of datasets biconnector.dataset.list
Get the list of datasets biconnector.dataset.list
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: a user with access to the "Analyst Workspace" section
The method
biconnector.dataset.list
returns a list of datasets based on a filter. It is an implementation of the listing method for datasets.
Method Parameters
Method Parameters
Name
type
Description
select
string[]
A list of fields that must be populated in the datasets in the selection. By default, all fields are taken.
The
fields
parameter is not supported and will be ignored.
filter
object
Filter for selecting datasets. Example format:
{
"field_1"
:
"value_1"
,
"field_2"
:
"value_2"
}
You can add a prefix to the keys
field_n
to specify the filter operation.
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
symbol in the filter value does not need to be passed. The search looks for a substring in any position of the string.
=%
— LIKE, substring search. The
%
symbol needs to be passed in the value. Examples:
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
=
— equals, exact match (used by default)
!=
— not equal
!
— not equal
The list of available fields for filtering can be found using the method
biconnector.dataset.fields
.
The filter does not support the
fields
parameter and it will be ignored.
order
object
Sorting parameters. Example format:
{
field_1: value_1,
field_2: value_2,
...,
field_n: value_n,
}
where:
field_n
— the name of the field by which the dataset selection will be sorted
value_n
— a
string
value equal to:
ASC
— ascending sort
DESC
— descending sort
page
integer
Controls pagination. The page size of results is 50 records. To navigate through the results, pass the page number.
Code Examples
Code Examples
How to Use Examples in Documentation
Get the list of sources where:
the name starts with
Sales
the description is not empty
the source ID equals
2
or
4
For clarity, select only the necessary fields:
ID
id
Name
name
Description
description
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
'{
"select": ["id", "name", "description"],
"filter": {
"%=name": "Sales%",
"!description": "",
"@sourceId": [2, 4]
},
"order": {
"dateCreate": "DESC"
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.dataset.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"select": ["id", "name", "description"],
"filter": {
"%=name": "Sales%",
"!description": "",
"@sourceId": [2, 4]
},
"order": {
"dateCreate": "DESC"
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/biconnector.dataset.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'biconnector.dataset.list'
,
{
select
: [
"id"
,
"name"
,
"description"
],
filter
: {
'%=name'
:
"Sales%"
,
'!description'
:
""
,
"@sourceId"
: [
2
,
4
]
},
order
: {
dateCreate
:
"DESC"
}
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'biconnector.dataset.list'
, {
select
: [
"id"
,
"name"
,
"description"
],
filter
: {
'%=name'
:
"Sales%"
,
'!description'
:
""
,
"@sourceId"
: [
2
,
4
]
},
order
: {
dateCreate
:
"DESC"
}
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
// callMethod provides manual control over the pagination process through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.dataset.list'
, {
select
: [
"id"
,
"name"
,
"description"
],
filter
: {
'%=name'
:
"Sales%"
,
'!description'
:
""
,
"@sourceId"
: [
2
,
4
]
},
order
: {
dateCreate
:
"DESC"
}
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
$response
=
$b24Service
->core
->
call
(
'biconnector.dataset.list'
,
[
'select'
=> [
"id"
,
"name"
,
"description"
],
'filter'
=> [
'%=name'
=>
"Sales%"
,
'!description'
=>
""
,
"@sourceId"
=> [
2
,
4
]
],
'order'
=> [
'dateCreate'
=>
"DESC"
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
$response
->
getError
()) {
error_log
(
$response
->
getError
());
echo
'Error: '
.
$response
->
getError
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
,
true
);
// Your data processing logic
processData
(
$result
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
'Error calling biconnector.dataset.list: '
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
'biconnector.dataset.list'
,
{
select
: [
"id"
,
"name"
,
"description"
],
filter
: {
'%=name'
:
"Sales%"
,
'!description'
:
""
,
"@sourceId"
: [
2
,
4
]
},
order
: {
dateCreate
:
"DESC"
}
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
'biconnector.dataset.list'
,
[
'select'
=> [
"id"
,
"name"
,
"description"
],
'filter'
=> [
'%=name'
=>
"Sales%"
,
'!description'
=>
""
,
'@sourceId'
=> [
2
,
4
]],
'order'
=> [
'dateCreate'
=>
"DESC"
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
"id"
:
"9"
,
"name"
:
"sales_data_main"
,
"description"
:
"Monthly sales report"
}
,
{
"id"
:
"6"
,
"name"
:
"sales_data_first_branch"
,
"description"
:
"Monthly sales report for first branch"
}
,
{
"id"
:
"5"
,
"name"
:
"sales_data_second_branch"
,
"description"
:
"Monthly sales report for second branch"
}
]
,
"time"
:
{
"start"
:
1743061675.963969
,
"finish"
:
1743061676.064591
,
"duration"
:
0.10062193870544434
,
"processing"
:
0.011152029037475586
,
"date_start"
:
"2025-03-27T07:47:55+00:00"
,
"date_finish"
:
"2025-03-27T07:47:56+00:00"
}
}
Returned Data
Returned Data
result
object
The root element of the response. Contains an array of objects with information about the fields of the datasets.
It should be noted that the structure of the fields may change due to the
select
parameter.
time
time
Information about the execution time of the request.
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
"VALIDATION_SELECT_TYPE"
,
"error_description"
:
"Parameter \"select\" must be array."
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
VALIDATION_SELECT_TYPE
Parameter "select" must be array.
The
select
parameter is not an object.
VALIDATION_FILTER_TYPE
Parameter "filter" must be array.
The
filter
parameter is not an object.
VALIDATION_ORDER_TYPE
Parameter "order" must be array.
The
order
parameter is not an object.
VALIDATION_FIELD_NOT_ALLOWED_IN_SELECT
Field "#TITLE#" is not allowed in the "select".
These fields are not allowed in the selection.
VALIDATION_FIELD_NOT_ALLOWED_IN_FILTER
Field "#TITLE#" is not allowed in the "filter".
These fields are not allowed in the filter.
VALIDATION_FIELD_NOT_ALLOWED_IN_ORDER
Field "#TITLE#" is not allowed in the "order".
These fields are not allowed for sorting.
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
Create Dataset biconnector.dataset.add
Update Dataset biconnector.dataset.update
Update Dataset Fields biconnector.dataset.fields.update
Get dataset by id biconnector.dataset.get
Get Fields of the Dataset biconnector.dataset.fields
Delete dataset biconnector.dataset.delete
Copied
Was the article helpful?
Yes
No
Previous
Get dataset by id
Next
Delete dataset

---

## Delete dataset biconnector.dataset.delete

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/dataset/biconnector-dataset-delete

Delete dataset biconnector.dataset.delete | Bitrix24 REST API and Marketplace Applications
Delete dataset biconnector.dataset.delete
Delete dataset biconnector.dataset.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: a user with access to the "Analyst Workspace" section
The method
biconnector.dataset.delete
removes an existing dataset.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
integer
Identifier of the dataset, can be obtained using the methods
biconnector.dataset.list
or
biconnector.dataset.add
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
'{"id":4}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.dataset.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":4,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/biconnector.dataset.delete
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.dataset.delete'
,
{
id
:
4
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
'biconnector.dataset.delete'
,
[
'id'
=>
4
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
'Info: '
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
'Error deleting dataset: '
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
'biconnector.dataset.delete'
,
{
id
:
4
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
'biconnector.dataset.delete'
,
[
'id'
=>
4
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
1725365418.056843
,
"finish"
:
1725365419.671506
,
"duration"
:
1.6146628856658936
,
"processing"
:
1.3475170135498047
,
"date_start"
:
"2024-09-03T14:10:18+02:00"
,
"date_finish"
:
"2024-09-03T14:10:19+02:00"
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
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
200
{
"error"
:
"VALIDATION_ID_NOT_PROVIDED"
,
"error_description"
:
"ID is missing."
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
VALIDATION_ID_NOT_PROVIDED
ID is missing.
Identifier is not specified
VALIDATION_INVALID_ID_FORMAT
ID has to be a positive integer.
Invalid ID format
DATASET_NOT_FOUND
Dataset was not found.
Dataset not found
-
Error deleting dataset
Error deleting dataset
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
Create Dataset biconnector.dataset.add
Update Dataset biconnector.dataset.update
Update Dataset Fields biconnector.dataset.fields.update
Get dataset by id biconnector.dataset.get
Get the list of datasets biconnector.dataset.list
Get Fields of the Dataset biconnector.dataset.fields
Copied
Was the article helpful?
Yes
No
Previous
Get list of datasets
Next
Get dataset fields

---

## Get Fields of the Dataset biconnector.dataset.fields

**Source:** https://apidocs.bitrix24.com/api-reference/biconnector/dataset/biconnector-dataset-fields

Get Fields of the Dataset biconnector.dataset.fields | Bitrix24 REST API and Marketplace Applications
Get Fields of the Dataset biconnector.dataset.fields
Get Fields of the Dataset biconnector.dataset.fields
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
biconnector
Who can execute the method: a user with access to the "Analyst Workspace" section
The method
biconnector.dataset.fields
returns a description of the dataset fields. A table with descriptions of standard fields can be found in the article
Datasets: Overview of Methods
.
Method Parameters
Method Parameters
No parameters.
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
'{}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/biconnector.dataset.fields
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
https://**put_your_bitrix24_address**/rest/biconnector.dataset.fields
try
{
const
response =
await
$b24.
callMethod
(
'biconnector.dataset.fields'
,
{}
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
'biconnector.dataset.fields'
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
'Error calling biconnector.dataset.fields: '
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
'biconnector.dataset.fields'
,
{},
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
'biconnector.dataset.fields'
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
HTTP Status:
200
{
"result"
:
{
"fields"
:
[
{
"title"
:
"id"
,
"type"
:
"integer"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"sourceId"
,
"type"
:
"integer"
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
true
,
"isMultiple"
:
false
}
,
{
"title"
:
"name"
,
"type"
:
"string"
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
true
,
"isMultiple"
:
false
}
,
{
"title"
:
"type"
,
"type"
:
"string"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"description"
,
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
}
,
{
"title"
:
"externalName"
,
"type"
:
"string"
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
true
,
"isMultiple"
:
false
}
,
{
"title"
:
"externalCode"
,
"type"
:
"string"
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
true
,
"isMultiple"
:
false
}
,
{
"title"
:
"externalId"
,
"type"
:
"integer"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"dateCreate"
,
"type"
:
"datetime"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"dateUpdate"
,
"type"
:
"datetime"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"createdById"
,
"type"
:
"integer"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"updatedById"
,
"type"
:
"integer"
,
"isRequired"
:
true
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
}
,
{
"title"
:
"fields"
,
"type"
:
"array"
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
true
}
]
}
,
"time"
:
{
"start"
:
1740757652.264398
,
"finish"
:
1740757652.343882
,
"duration"
:
0.0794839859008789
,
"processing"
:
2.002716064453125e-5
,
"date_start"
:
"2025-02-28T15:47:32+00:00"
,
"date_finish"
:
"2025-02-28T15:47:32+00:00"
}
}
Returned Data
Returned Data
Name
type
Description
result
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
— dataset field
value_n
—
field information
time
time
Information about the request execution time
Error Handling
Error Handling
The method does not return errors.
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
Create Dataset biconnector.dataset.add
Update Dataset biconnector.dataset.update
Update Dataset Fields biconnector.dataset.fields.update
Get dataset by id biconnector.dataset.get
Get the list of datasets biconnector.dataset.list
Delete dataset biconnector.dataset.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete dataset
Next
AI in Bitrix24

---

