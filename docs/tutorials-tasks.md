---
description: 'Tutorials: Tasks management'
methods:
- crm.enum.ownertype
- crm.item.list
pages: 5
title: 'Tutorials: Tasks management'
---
# Tutorials: Tasks management
> Tutorials: Tasks management
> **5 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Typical use-cases and scenarios for REST API in Tasks and tutorials](#typical-use-cases-and-scenarios-for-rest-api-in-ta)
- [How to Create a Task with an Attached File](#how-to-create-a-task-with-an-attached-file)
- [How to Upload a File to a Task](#how-to-upload-a-file-to-a-task)
- [How to Create a Comment in a Task and Attach a File](#how-to-create-a-comment-in-a-task-and-attach-a-fil)
- [How to Attach a Task to a SPA](#how-to-attach-a-task-to-a-spa)

---

## Typical use-cases and scenarios for REST API in Tasks and tutorials

**Source:** https://apidocs.bitrix24.com/tutorials/tasks/index

Typical use-cases and scenarios for REST API in Tasks and tutorials | Bitrix24 REST API and Marketplace Applications
Typical use-cases and scenarios for REST API in Tasks and tutorials
Typical use-cases and scenarios for REST API in Tasks and tutorials
In this section, you will find examples for addressing typical situations related to tasks:
How to Create a Task with an Attached File
How to Upload a File to a Task
How to Create a Comment in a Task and Attach a File
How to Attach a Task to a SPA
Was the article helpful?
Yes
No
Previous
User scenarios and example
Next
How to create a task with an attached file

---

## How to Create a Task with an Attached File

**Source:** https://apidocs.bitrix24.com/tutorials/tasks/how-to-create-task-with-file

How to Create a Task with an Attached File | Bitrix24 REST API and Marketplace Applications
How to Create a Task with an Attached File
How to Create a Task with an Attached File
1. Uploading a File to the Bitrix24 Drive
2. Creating a Task with a File
Code Example
Continue Learning
Scope:
disk
,
tasks
Who can execute the method: users with access to the drive and tasks sections
In Bitrix24, there are two types of file fields:
File.
This field is not linked to the drive; files are uploaded directly through the
Base64 format string
.
File (drive).
This field is linked to the drive, and it stores the ID of the drive object. The Base64 format is not processed in this field, so the file must first be uploaded to the Bitrix24 drive.
To create a task with a file, we will sequentially execute two methods:
disk.folder.uploadfile
— this method uploads a file to the disk.
tasks.task.add
— this method creates a task.
1. Uploading a File to the Bitrix24 Drive
1. Uploading a File to the Bitrix24 Drive
To upload a file to the drive, we use the method
disk.folder.uploadfile
with the following parameters:
id
— we will specify the value
1739
— the identifier of the drive folder where we are uploading the file.
data
— we will specify the file name
NAME
, under which the file will be saved on the Bitrix24 drive.
fileContent
— we pass the file in the format ['file_name.extension', 'file as a Base64 encoded string'].
Uploading the file to the drive is a necessary step, as the
UF_TASK_WEBDAV_FILES
field in tasks only accepts the IDs of drive files.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"disk.folder.uploadfile"
,
{
id
:
1739
,
data
: {
NAME
:
"ava555.jpg"
},
fileContent
: [
'avatar.jpg'
,
'/9j/4AAQSkZJRgABAQEASABIAAD/2wBDAAQDAwQDAwQEAwQ///+dAYq6YFKoAv/AFnAa6ArKv8AAtFJVppxCEAulxQ2DWgfMR//2Q=='
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
'disk.folder.uploadfile'
,
[
'id'
=>
1739
,
'data'
=> [
'NAME'
=>
'ava555.jpg'
],
'fileContent'
=> [
'avatar.jpg'
,
'/9j/4AAQSkZJRgABAQEASABIAAD/2wBDAAQDAwQDAwQEAwQ///+dAYq6YFKoAv/AFnAa6ArKv8AAtFJVppxCEAulxQ2DWgfMR//2Q=='
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
As a result of uploading the file to the drive, we received two different file ID values:
FILE_ID
:
28073
— the internal file ID value.
ID
:
6687
— the drive object ID, this value is used in methods for working with fields of the type "file (drive)".
If the
FILE_ID
value is passed in the request to change the "file (drive)" field, the file will either not be attached to the task because there is no drive object with such an ID, or the wrong file will be attached.
{
"result"
:
{
"ID"
:
6687
,
"NAME"
:
"ava555.jpg"
,
"CODE"
:
null
,
"STORAGE_ID"
:
"1"
,
"TYPE"
:
"file"
,
"PARENT_ID"
:
"1739"
,
"DELETED_TYPE"
:
0
,
"GLOBAL_CONTENT_VERSION"
:
1
,
"FILE_ID"
:
28073
,
"SIZE"
:
"405559"
,
"CREATE_TIME"
:
"2024-11-01T17:00:55+02:00"
,
"UPDATE_TIME"
:
"2024-11-01T17:00:55+02:00"
,
"DELETE_TIME"
:
null
,
"CREATED_BY"
:
"1"
,
"UPDATED_BY"
:
"1"
,
"DELETED_BY"
:
null
,
"DOWNLOAD_URL"
:
"https://your-domain.bitrix24.com/rest/download.json?sessid=9dd90ed5a58ccc41af81f5f0043739db&token=disk%7CaWQ9NjY4NyZfPTJ5ZXdvN2Fsb09SMGw1b0FHTkRMSGR5MFJkN1pLTjNS%7CImRvd25sb2FkfGRpc2t8YVdROU5qWTROeVpmUFRKNVpYZHZOMkZzYjA5U01HdzFiMEZIVGtSTVNHUjVNRkprTjFwTFRqTlN8OWRkOTBlZDVhNThjY2M0MWFmODFmNWYwMDQzNzM5ZGIi.Lup1vDbibL6twiCPfCMFnLSoDLleNX0cfMHGv5PFaJw%3D"
,
"DETAIL_URL"
:
"https://your-domain.bitrix24.com/company/personal/user/1/disk/file/Created files/New folder for testing the process/ava555.jpg"
}
}
2. Creating a Task with a File
2. Creating a Task with a File
To create a task, we use the method
tasks.task.add
with the following parameters:
UF_TASK_WEBDAV_FILES
— we will specify the value
n6687
. This is the file ID from the result of the previous method, to which we add the prefix
n
for uploading the file to the field.
TITLE
— the task title, a required field. Without a title, the task will not be created.
CREATED_BY
— the ID of the task creator, this field cannot be empty. If it is not filled, the creator will automatically be the one who sends the request.
RESPONSIBLE_ID
— the ID of the task assignee, a required field. Without an assignee, the task will not be created.
JS
PHP
BX24
.
callMethod
(
'tasks.task.add'
,
{
fields
: {
TITLE
:
'task for test'
,
RESPONSIBLE_ID
:
1
,
UF_TASK_WEBDAV_FILES
: [
"n6687"
]
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
'tasks.task.add'
,
[
'fields'
=> [
'TITLE'
=>
'task for test'
,
'RESPONSIBLE_ID'
=>
1
,
'UF_TASK_WEBDAV_FILES'
=> [
'n6687'
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
We created a task with ID
3711
.
{
"result"
:
{
"task"
:
{
"id"
:
"3711"
,
"parentId"
:
null
,
"title"
:
"task for test"
,
"description"
:
""
,
"mark"
:
null
,
"priority"
:
"1"
,
"multitask"
:
"N"
,
"notViewed"
:
"N"
,
"replicate"
:
"N"
,
"stageId"
:
"0"
,
"createdBy"
:
"1"
,
"createdDate"
:
"2024-11-02T10:06:08+02:00"
,
"responsibleId"
:
"1"
,
"changedBy"
:
"1"
,
"changedDate"
:
"2024-11-02T10:06:08+02:00"
,
"statusChangedBy"
:
null
,
"closedBy"
:
null
,
"closedDate"
:
null
,
"activityDate"
:
"2024-11-02T10:06:08+02:00"
,
"dateStart"
:
null
,
"deadline"
:
null
,
"startDatePlan"
:
null
,
"endDatePlan"
:
null
,
"guid"
:
"{c2794da9-c7fe-404d-a709-ddab4578717a}"
,
"xmlId"
:
null
,
"commentsCount"
:
null
,
"serviceCommentsCount"
:
null
,
"allowChangeDeadline"
:
"N"
,
"allowTimeTracking"
:
"N"
,
"taskControl"
:
"N"
,
"addInReport"
:
"N"
,
"forkedByTemplateId"
:
null
,
"timeEstimate"
:
"0"
,
"timeSpentInLogs"
:
null
,
"matchWorkTime"
:
"N"
,
"forumTopicId"
:
null
,
"forumId"
:
null
,
"siteId"
:
"s1"
,
"subordinate"
:
"Y"
,
"exchangeModified"
:
null
,
"exchangeId"
:
null
,
"outlookVersion"
:
"1"
,
"viewedDate"
:
null
,
"sorting"
:
null
,
"durationFact"
:
null
,
"isMuted"
:
"N"
,
"isPinned"
:
"N"
,
"isPinnedInGroup"
:
"N"
,
"flowId"
:
null
,
"descriptionInBbcode"
:
"Y"
,
"status"
:
"2"
,
"statusChangedDate"
:
"2024-11-02T10:06:08+02:00"
,
"durationPlan"
:
null
,
"durationType"
:
"days"
,
"favorite"
:
"N"
,
"groupId"
:
"0"
,
"auditors"
:
[
]
,
"accomplices"
:
[
]
,
"checklist"
:
[
]
,
"group"
:
[
]
,
"creator"
:
{
"id"
:
"1"
,
"name"
:
"Viola"
,
"link"
:
"/company/personal/user/1/"
,
"icon"
:
"https://your-domain.bitrix24.com/b13743910/resize_cache/2267/c0120a8d7c10d63c83e32398d1ec4d9e/main/c7b/c7bd44b1babaa5448125dd97d038ce1b/d5fb56b94dc2c3cd8c006a2c595a4895.jpg"
,
"workPosition"
:
""
}
,
"responsible"
:
{
"id"
:
"1"
,
"name"
:
"Viola"
,
"link"
:
"/company/personal/user/1/"
,
"icon"
:
"https://your-domain.bitrix24.com/b13743910/resize_cache/2267/c0120a8d7c10d63c83e32398d1ec4d9e/main/c7b/c7bd44b1babaa5448125dd97d038ce1b/d5fb56b94dc2c3cd8c006a2c595a4895.jpg"
,
"workPosition"
:
""
}
,
"accomplicesData"
:
[
]
,
"auditorsData"
:
[
]
,
"newCommentsCount"
:
0
,
"action"
:
{
"accept"
:
false
,
"decline"
:
false
,
"complete"
:
true
,
"approve"
:
false
,
"disapprove"
:
false
,
"start"
:
true
,
"pause"
:
false
,
"delegate"
:
true
,
"remove"
:
true
,
"edit"
:
true
,
"defer"
:
true
,
"renew"
:
false
,
"create"
:
true
,
"changeDeadline"
:
true
,
"checklistAddItems"
:
true
,
"addFavorite"
:
true
,
"deleteFavorite"
:
false
,
"rate"
:
true
,
"edit.originator"
:
false
,
"checklist.reorder"
:
true
,
"elapsedtime.add"
:
true
,
"dayplan.timer.toggle"
:
false
,
"edit.plan"
:
true
,
"checklist.add"
:
true
,
"favorite.add"
:
true
,
"favorite.delete"
:
false
}
,
"checkListTree"
:
{
"nodeId"
:
0
,
"fields"
:
{
"id"
:
null
,
"copiedId"
:
null
,
"entityId"
:
null
,
"userId"
:
1
,
"createdBy"
:
null
,
"parentId"
:
null
,
"title"
:
""
,
"sortIndex"
:
null
,
"displaySortIndex"
:
""
,
"isComplete"
:
false
,
"isImportant"
:
false
,
"completedCount"
:
0
,
"members"
:
[
]
,
"attachments"
:
[
]
}
,
"action"
:
[
]
,
"descendants"
:
[
]
}
,
"checkListCanAdd"
:
true
}
}
}
In the received result, there is no information about the task files. To check if the file was successfully attached to the task, we will execute the method
tasks.task.get
with the
UF_TASK_WEBDAV_FILES
field in
SELECT
.
As a result of
tasks.task.get
, we will obtain the ID of the record linking the drive file to the task — this is the ID of the connection that links the task and the drive file. To get information about the file by the connection ID, we use the method
disk.attachedObject.get
.
Code Example
Code Example
JS
PHP
// Function to upload a file
function
uploadFileToDisk
(
) {
// ID of the folder where you want to upload the file
var
folderId =
'your_folder_ID'
;
// File name and its content in Base64 format
var
fileName =
'your_file_name'
;
var
fileContentBase64 =
'your_file_content_Base64'
;
// Call the disk.folder.uploadfile method
BX24
.
callMethod
(
'disk.folder.uploadfile'
,
{
id
: folderId,
data
: {
NAME
: fileName
},
fileContent
: [
fileName,
fileContentBase64
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
(
'Error uploading file:'
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
'File uploaded successfully!'
, result.
data
());
var
fileId = result.
data
().
ID
;
// Use the ID from the result
createTaskWithFile
(fileId);
}
}
);
}
// Function to create a task with an attached file
function
createTaskWithFile
(
fileId
) {
// Task parameters
var
taskTitle =
'your_task_title'
;
var
taskDescription =
'your_task_description'
;
var
responsibleId =
'your_responsible_ID'
;
// Call the tasks.task.add method
BX24
.
callMethod
(
'tasks.task.add'
,
{
fields
: {
TITLE
: taskTitle,
DESCRIPTION
: taskDescription,
RESPONSIBLE_ID
: responsibleId,
UF_TASK_WEBDAV_FILES
: [
'n'
+ fileId]
// Add prefix 'n' to the file ID
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
'Error creating task:'
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
'Task created successfully!'
, result.
data
());
}
}
);
}
// Call the function to upload the file and create the task
uploadFileToDisk
();
require_once
(
'crest.php'
);
// Function to upload a file
function
uploadFileToDisk
(
)
{
// ID of the folder where you want to upload the file
$folderId
=
'your_folder_ID'
;
// Name of the file you want to upload
$fileName
=
'your_file_name'
;
// Path to the file on your file system
$filePath
=
'/path/to/your/file'
;
// Read the file content and encode it in Base64
$fileContentBase64
=
base64_encode
(
file_get_contents
(
$filePath
));
// Call the disk.folder.uploadfile method
$result
=
CRest
::
call
(
'disk.folder.uploadfile'
,
[
'id'
=>
$folderId
,
'data'
=> [
'NAME'
=>
$fileName
],
'fileContent'
=> [
$fileName
,
$fileContentBase64
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
'Error uploading file: '
.
$result
[
'error'
];
}
else
{
echo
'File uploaded successfully!'
;
$fileId
=
$result
[
'result'
][
'ID'
];
// Use the ID from the result
createTaskWithFile
(
$fileId
);
}
}
// Function to create a task with an attached file
function
createTaskWithFile
(
$fileId
)
{
// Task parameters
$taskTitle
=
'your_task_title'
;
$taskDescription
=
'your_task_description'
;
$responsibleId
=
'your_responsible_ID'
;
// Call the tasks.task.add method
$result
=
CRest
::
call
(
'tasks.task.add'
,
[
'fields'
=> [
'TITLE'
=>
$taskTitle
,
'DESCRIPTION'
=>
$taskDescription
,
'RESPONSIBLE_ID'
=>
$responsibleId
,
'UF_TASK_WEBDAV_FILES'
=> [
'n'
.
$fileId
] // Add prefix
'n'
to the file ID
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
'Error creating task: '
.
$result
[
'error'
];
}
else
{
echo
'Task created successfully!'
;
}
}
// Call the function to upload the file and create the task
uploadFileToDisk
();
Continue Learning
Continue Learning
How to Upload a File to a Task
Copied
Was the article helpful?
Yes
No
Previous
Typical use-cases for REST API in Tasks and tutorials
Next
How to upload a file to a task

---

## How to Upload a File to a Task

**Source:** https://apidocs.bitrix24.com/tutorials/tasks/how-to-upload-file-to-task

How to Upload a File to a Task | Bitrix24 REST API and Marketplace Applications
How to Upload a File to a Task
How to Upload a File to a Task
1. Uploading a File to the Bitrix24 Drive
2. Attaching the File to the Task
Code Example
Continue Learning
Scope:
disk
,
tasks
Who can execute the method: users with access to the drive and tasks sections
In Bitrix24, there are two types of file fields:
File.
This field is not linked to the drive; files are uploaded directly through the
Base64 format string
.
File (drive).
This field is linked to the drive, and it stores the ID of the drive object. The Base64 format is not processed in this field, so the file must first be uploaded to the Bitrix24 drive.
To attach a file to a task, perform the following two methods in sequence:
disk.folder.uploadfile
— this method uploads the file to the disk.
tasks.task.files.attach
— this method attaches the drive file to the task.
1. Uploading a File to the Bitrix24 Drive
1. Uploading a File to the Bitrix24 Drive
To upload a file to the drive, we use the
disk.folder.uploadfile
method with the following parameters:
id
— specify the value
1739
— the identifier of the drive folder where the file will be uploaded.
data
— specify the file name
NAME
, which will be the name the file is saved as on the Bitrix24 drive.
fileContent
— pass the file in the format ['file_name.extension', 'file as a Base64 encoded string'].
Uploading the file to the drive is a necessary step, as the
UF_TASK_WEBDAV_FILES
field in tasks only accepts drive file IDs.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"disk.folder.uploadfile"
,
{
id
:
1739
,
data
: {
NAME
:
"ava555.jpg"
},
fileContent
: [
'avatar.jpg'
,
'/9j/4AAQSkZJRgABAQEASABIAAD/2wBDAAQDAwQDAwQEAwQ///+dAYq6YFKoAv/AFnAa6ArKv8AAtFJVppxCEAulxQ2DWgfMR//2Q=='
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
'disk.folder.uploadfile'
,
[
'id'
=>
1739
,
'data'
=> [
'NAME'
=>
'ava555.jpg'
],
'fileContent'
=> [
'avatar.jpg'
,
'/9j/4AAQSkZJRgABAQEASABIAAD/2wBDAAQDAwQDAwQEAwQ///+dAYq6YFKoAv/AFnAa6ArKv8AAtFJVppxCEAulxQ2DWgfMR//2Q=='
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
As a result of uploading the file to the drive, we received two different file ID values:
FILE_ID
:
28073
— the internal file ID value.
ID
:
6687
— the drive object ID, which we will use in methods for working with "file (drive)" type fields.
If the request to change the "file (drive)" field passes the
FILE_ID
value, the file will either not be attached to the task because there is no drive object with that ID, or the wrong file will be attached.
{
"result"
:
{
"ID"
:
6687
,
"NAME"
:
"ava555.jpg"
,
"CODE"
:
null
,
"STORAGE_ID"
:
"1"
,
"TYPE"
:
"file"
,
"PARENT_ID"
:
"1739"
,
"DELETED_TYPE"
:
0
,
"GLOBAL_CONTENT_VERSION"
:
1
,
"FILE_ID"
:
28073
,
"SIZE"
:
"405559"
,
"CREATE_TIME"
:
"2024-11-01T17:00:55+02:00"
,
"UPDATE_TIME"
:
"2024-11-01T17:00:55+02:00"
,
"DELETE_TIME"
:
null
,
"CREATED_BY"
:
"1"
,
"UPDATED_BY"
:
"1"
,
"DELETED_BY"
:
null
,
"DOWNLOAD_URL"
:
"https://your-domain.bitrix24.com/rest/download.json?sessid=9dd90ed5a58ccc41af81f5f0043739db&token=disk%7CaWQ9NjY4NyZfPTJ5ZXdvN2Fsb09SMGw1b0FHTkRMSGR5MFJkN1pLTjNS%7CImRvd25sb2FkfGRpc2t8YVdROU5qWTROeVpmUFRKNVpYZHZOMkZzYjA5U01HdzFiMEZIVGtSTVNHUjVNRkprTjFwTFRqTlN8OWRkOTBlZDVhNThjY2M0MWFmODFmNWYwMDQzNzM5ZGIi.Lup1vDbibL6twiCPfCMFnLSoDLleNX0cfMHGv5PFaJw%3D"
,
"DETAIL_URL"
:
"https://your-domain.bitrix24.com/company/personal/user/1/disk/file/Created files/New folder for testing process/ava555.jpg"
}
}
2. Attaching the File to the Task
2. Attaching the File to the Task
To attach the file to the task, we use the
tasks.task.files.attach
method with the following parameters:
taskId
— the ID of the task. To obtain the ID value, use the
tasks.task.list
method.
fileId
— specify the file ID from the result of the previous method
6687
.
JS
PHP
BX24
.
callMethod
(
'tasks.task.files.attach'
,
{
taskId
:
3709
,
fileId
:
6687
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
'tasks.task.files.attach'
,
[
'taskId'
=>
3709
,
'fileId'
=>
6687
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
We uploaded the file to the task and received the ID of the link between the drive file and the task
423
in response. To verify the attachment of the file to the task by the link ID, we use the
disk.attachedObject.get
method.
{
"result"
:
{
"attachmentId"
:
423
}
,
"time"
:
{
"start"
:
1730795703.5871601
,
"finish"
:
1730795703.8165951
,
"duration"
:
0.22943496704101562
,
"processing"
:
0.18604612350463867
,
"date_start"
:
"2024-11-05T11:35:03+02:00"
,
"date_finish"
:
"2024-11-05T11:35:03+02:00"
,
"operating_reset_at"
:
1730796303
,
"operating"
:
0.18602108955383301
}
}
Code Example
Code Example
JS
PHP
// Function to upload a file
function
uploadFileToDisk
(
) {
// ID of the folder where you want to upload the file
var
folderId =
'your_folder_ID'
;
// File name and its content in Base64 format
var
fileName =
'your_file_name'
;
var
fileContentBase64 =
'your_file_content_Base64'
;
// ID of the task to which the file needs to be attached
var
taskId =
'your_task_ID'
;
// Call the disk.folder.uploadfile method
BX24
.
callMethod
(
'disk.folder.uploadfile'
,
{
id
: folderId,
data
: {
NAME
: fileName
},
fileContent
: [
fileName,
fileContentBase64
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
(
'Error uploading file:'
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
'File uploaded successfully!'
, result.
data
());
var
fileId = result.
data
().
ID
;
// Use ID from the result
attachFileToTask
(taskId, fileId);
}
}
);
}
// Function to attach a file to an existing task
function
attachFileToTask
(
taskId, fileId
) {
// Call the tasks.task.files.attach method
BX24
.
callMethod
(
'tasks.task.files.attach'
,
{
taskId
: taskId,
fileIds
: [fileId]
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
'Error attaching file to task:'
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
'File successfully attached to the task!'
, result.
data
());
}
}
);
}
// Call the function to upload the file and attach it to the task
uploadFileToDisk
();
require_once
(
'crest.php'
);
// Function to upload a file
function
uploadFileToDisk
(
)
{
// ID of the folder where you want to upload the file
$folderId
=
'your_folder_ID'
;
// Name of the file you want to upload
$fileName
=
'your_file_name'
;
// Path to the file on your file system
$filePath
=
'/path/to/your/file'
;
// Read the file content and encode it in Base64
$fileContentBase64
=
base64_encode
(
file_get_contents
(
$filePath
));
// ID of the task to which the file needs to be attached
$taskId
=
'your_task_ID'
;
// Call the disk.folder.uploadfile method
$result
=
CRest
::
call
(
'disk.folder.uploadfile'
,
[
'id'
=>
$folderId
,
'data'
=> [
'NAME'
=>
$fileName
],
'fileContent'
=> [
$fileName
,
$fileContentBase64
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
'Error uploading file: '
.
$result
[
'error'
];
}
else
{
echo
'File uploaded successfully!'
;
$fileId
=
$result
[
'result'
][
'ID'
];
// Use ID from the result
attachFileToTask
(
$taskId
,
$fileId
);
}
}
// Function to attach a file to an existing task
function
attachFileToTask
(
$taskId
,
$fileId
)
{
// Call the tasks.task.files.attach method
$result
=
CRest
::
call
(
'tasks.task.files.attach'
,
[
'taskId'
=>
$taskId
,
'fileIds'
=> [
$fileId
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
'Error attaching file to task: '
.
$result
[
'error'
];
}
else
{
echo
'File successfully attached to the task!'
;
}
}
// Call the function to upload the file and attach it to the task
uploadFileToDisk
();
Continue Learning
Continue Learning
How to Create a Task with an Attached File
Copied
Was the article helpful?
Yes
No
Previous
How to create a task with an attached file
Next
How to create a comment in a task and attach a file to it

---

## How to Create a Comment in a Task and Attach a File

**Source:** https://apidocs.bitrix24.com/tutorials/tasks/how-to-create-comment-with-file

How to Create a Comment in a Task and Attach a File | Bitrix24 REST API and Marketplace Applications
How to Create a Comment in a Task and Attach a File
How to Create a Comment in a Task and Attach a File
1. Uploading a File to the Bitrix24 Drive
2. Creating a Comment and Attaching a File
Code Example
Scope:
drive
,
tasks
Who can execute the method: users with access to the drive and tasks sections
In Bitrix24, there are two types of file fields:
File.
This field is not linked to the drive; files are uploaded directly through the
Base64 format string
.
File (drive).
This field is linked to the drive, and it stores the ID of the drive object. The Base64 format is not processed in this field, so the file must first be uploaded to the Bitrix24 drive.
To create a comment in a task and attach a file, we will sequentially execute two methods:
disk.folder.uploadfile
— this method uploads a file to the drive.
task.commentitem.add
— this method creates a comment.
1. Uploading a File to the Bitrix24 Drive
1. Uploading a File to the Bitrix24 Drive
To upload a file to the drive, we use the
disk.folder.uploadfile
method with the following parameters:
id
— we specify the value
1739
— the identifier of the drive folder where we are uploading the file.
data
— we specify the file name
NAME
, under which the file will be saved on the Bitrix24 drive.
fileContent
— we pass the file in the format ['file_name.extension', 'file as a Base64 encoded string'].
Uploading the file to the drive is a necessary step, as the
UF_FORUM_MESSAGE_DOC
field in comments only accepts the IDs of drive files.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"disk.folder.uploadfile"
,
{
id
:
1739
,
data
: {
NAME
:
"file.pdf"
},
fileContent
: [
'file555.pdf'
,
'/9j/4AAQSkZJRgABAQEASABIAAD/2wBDAAQDAwQDAwQEAwQ///+dAYq6YFKoAv/AFnAa6ArKv8AAtFJVppxCEAulxQ2DWgfMR//2Q=='
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
'disk.folder.uploadfile'
,
[
'id'
=>
1739
,
'data'
=> [
'NAME'
=>
'file.pdf'
],
'fileContent'
=> [
'file555.pdf'
,
'/9j/4AAQSkZJRgABAQEASABIAAD/2wBDAAQDAwQDAwQEAwQ///+dAYq6YFKoAv/AFnAa6ArKv8AAtFJVppxCEAulxQ2DWgfMR//2Q=='
]
]
);
As a result of uploading the file to the drive, we received two different file ID values:
FILE_ID
:
28073
— the internal file ID value.
ID
:
6687
— the drive object ID; this value is used in methods for working with fields of the "file (drive)" type.
If the request to change the "file (drive)" field passes the
FILE_ID
value, the file will either not be attached to the task because there is no drive object with that ID, or the wrong file will be attached.
{
"result"
:
{
"ID"
:
6687
,
"NAME"
:
"file.pdf"
,
"CODE"
:
null
,
"STORAGE_ID"
:
"1"
,
"TYPE"
:
"file"
,
"PARENT_ID"
:
"1739"
,
"DELETED_TYPE"
:
0
,
"GLOBAL_CONTENT_VERSION"
:
1
,
"FILE_ID"
:
28073
,
"SIZE"
:
"405559"
,
"CREATE_TIME"
:
"2024-11-01T17:00:55+02:00"
,
"UPDATE_TIME"
:
"2024-11-01T17:00:55+02:00"
,
"DELETE_TIME"
:
null
,
"CREATED_BY"
:
"1"
,
"UPDATED_BY"
:
"1"
,
"DELETED_BY"
:
null
,
"DOWNLOAD_URL"
:
"https://your-domain.bitrix24.com/rest/download.json?sessid=9dd90ed5a58ccc41af81f5f0043739db&token=disk%7CaWQ9NjY4NyZfPTJ5ZXdvN2Fsb09SMGw1b0FHTkRMSGR5MFJkN1pLTjNS%7CImRvd25sb2FkfGRpc2t8YVdROU5qWTROeVpmUFRKNVpYZHZOMkZzYjA5U01HdzFiMEZIVGtSTVNHUjVNRkprTjFwTFRqTlN8OWRkOTBlZDVhNThjY2M0MWFmODFmNWYwMDQzNzM5ZGIi.Lup1vDbibL6twiCPfCMFnLSoDLleNX0cfMHGv5PFaJw%3D"
,
"DETAIL_URL"
:
"https://your-domain.bitrix24.com/company/personal/user/1/disk/file/Created files/New folder for testing the process/file.pdf"
}
}
2. Creating a Comment and Attaching a File
2. Creating a Comment and Attaching a File
To create a comment in a task, we use the
task.commentitem.add
method with the following parameters:
TASKID
— the ID of the task, a required field. Without the task ID, the comment will not be created. To obtain the task ID, we use the
tasks.task.list
method.
AUTHOR_ID
— the ID of the comment author. This parameter can be omitted, in which case the author will automatically be the employee from whose account the request is made.
POST_MESSAGE
— the text of the comment.
UF_FORUM_MESSAGE_DOC
— we specify the value
n6687
. This is the drive file ID from the result of the previous method, to which we add the prefix
n
for uploading the file to the field.
JS
PHP
BX24
.
callMethod
(
'task.commentitem.add'
,
{
TASKID
:
3711
,
FIELDS
: {
POST_MESSAGE
:
'comment for test'
,
AUTHOR_ID
:
29
,
UF_FORUM_MESSAGE_DOC
: [
"n6687"
]
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
'task.commentitem.add'
,
[
'TASKID'
=>
3711
,
'FIELDS'
=> [
'POST_MESSAGE'
=>
'comment for test'
,
'AUTHOR_ID'
=>
29
,
'UF_FORUM_MESSAGE_DOC'
=> [
'n6687'
]
]
]
);
We created a comment with ID
9393
.
{
"result"
:
9393
}
In the received result, there is no information about the file attached to the comment. To check if the file was successfully attached, we will execute the
task.commentitem.get
method.
Code Example
Code Example
JS
PHP
// Function to upload a file
function
uploadFileToDisk
(
) {
// ID of the folder to which the file needs to be uploaded
var
folderId =
'folder_ID'
;
// File name and its content in Base64 format
var
fileName =
'file_name'
;
var
fileContentBase64 =
'file_content_Base64'
;
// Calling the disk.folder.uploadfile method
BX24
.
callMethod
(
'disk.folder.uploadfile'
,
{
id
: folderId,
data
: {
NAME
: fileName
},
fileContent
: [
fileName,
fileContentBase64
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
(
'Error uploading file:'
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
'File successfully uploaded!'
, result.
data
());
var
fileId = result.
data
().
ID
;
// Using ID from the result
createCommentWithFile
(fileId);
}
}
);
}
// Function to create a comment with a file
function
createCommentWithFile
(
fileId
) {
// Comment parameters
var
taskID =
'task_ID'
;
var
commentMessage =
'comment_text'
;
var
authorId =
'comment_author_ID'
;
// Calling the task.commentitem.add method
BX24
.
callMethod
(
'task.commentitem.add'
,
{
TASKID
: taskID,
FIELDS
: {
POST_MESSAGE
: commentMessage,
AUTHOR_ID
: authorId,
UF_FORUM_MESSAGE_DOC
: [
'n'
+ fileId]
// Adding prefix 'n' to the file ID
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
'Comment successfully created!'
, result.
data
());
}
}
);
}
// Calling the function to upload a file and create a comment
uploadFileToDisk
();
require_once
(
'crest.php'
);
// Function to upload a file
function
uploadFileToDisk
(
)
{
// ID of the folder to which the file needs to be uploaded
$folderId
=
'folder_ID'
;
// Name of the file you want to upload
$fileName
=
'file_name'
;
// Path to the file on your file system
$filePath
=
'/path/to/your/file'
;
// Reading the file content and encoding it in Base64
$fileContentBase64
=
base64_encode
(
file_get_contents
(
$filePath
));
// Calling the disk.folder.uploadfile method
$result
=
CRest
::
call
(
'disk.folder.uploadfile'
,
[
'id'
=>
$folderId
,
'data'
=> [
'NAME'
=>
$fileName
],
'fileContent'
=> [
$fileName
,
$fileContentBase64
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
'Error uploading file: '
.
$result
[
'error'
];
}
else
{
echo
'File successfully uploaded!'
;
$fileId
=
$result
[
'result'
][
'ID'
];
// Using ID from the result
createCommentWithFile
(
$fileId
);
}
}
// Function to create a comment with a file
function
createCommentWithFile
(
$fileId
)
{
// Comment parameters
$taskID
=
'task_ID'
;
$commentMessage
=
'comment_text'
;
$authorId
=
'comment_author_ID'
;
// Calling the task.commentitem.add method
$result
=
CRest
::
call
(
'task.commentitem.add'
,
[
'TASKID'
=>
$taskID
,
'FIELDS'
=> [
'POST_MESSAGE'
=>
$commentMessage
,
'AUTHOR_ID'
=>
$authorId
,
'UF_FORUM_MESSAGE_DOC'
=> [
'n'
.
$fileId
] // Adding prefix
'n'
to the file ID
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
'Comment successfully created!'
;
}
}
// Calling the function to upload a file and create a comment
uploadFileToDisk
();
Copied
Was the article helpful?
Yes
No
Previous
How to upload a file to a task
Next
How to attach a task to an SPA

---

## How to Attach a Task to a SPA

**Source:** https://apidocs.bitrix24.com/tutorials/tasks/how-to-connect-task-to-spa

How to Attach a Task to a SPA | Bitrix24 REST API and Marketplace Applications
How to Attach a Task to a SPA
How to Attach a Task to a SPA
1. Retrieving SPA Identifiers
2. Retrieving the SPA Element ID
3. Creating a Task Linked to the SPA Element
Verifying the Created Task
Code Example
Scope:
crm, tasks
Who can execute the method: users with access to the CRM and tasks sections
The key parameter for attaching a task to a CRM entity is the
object type identifier
. The identifier indicates which type of object the link will be added to: a deal, a lead, or a specific SPA.
To create a task and attach it to a SPA, we will sequentially execute three methods:
crm.enum.ownertype
— retrieve the
entityTypeId
and
SYMBOL_CODE_SHORT
of the SPA.
crm.item.list
— retrieve the SPA element using the
entityTypeId
parameter.
tasks.task.add
— create a task and link it to the SPA element using
SYMBOL_CODE_SHORT
.
1. Retrieving SPA Identifiers
1. Retrieving SPA Identifiers
To obtain the SPA identifier, we use the method
crm.enum.ownertype
. The method is called without parameters and returns an enumeration of all CRM object types.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"crm.enum.ownertype"
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
'crm.enum.ownertype'
,
[]
);
The method returns four different identifiers:
"ID"
:
130
,
// entityTypeId — obtained to find the CRM entity by filter
"NAME"
:
"All Inclusive"
,
// name
"SYMBOL_CODE"
:
"DYNAMIC_130"
,
// symbolic code
"SYMBOL_CODE_SHORT"
:
"T82"
// short symbolic code — obtained to link the CRM entity to the task
ID
is obtained to find the CRM entity by filter.
SYMBOL_CODE_SHORT
is obtained to link the CRM entity to the task.
{
"result"
:
[
{
"ID"
:
1
,
"NAME"
:
"Lead"
,
"SYMBOL_CODE"
:
"LEAD"
,
"SYMBOL_CODE_SHORT"
:
"L"
}
,
{
"ID"
:
2
,
"NAME"
:
"Deal"
,
"SYMBOL_CODE"
:
"DEAL"
,
"SYMBOL_CODE_SHORT"
:
"D"
}
,
{
"ID"
:
3
,
"NAME"
:
"Contact"
,
"SYMBOL_CODE"
:
"CONTACT"
,
"SYMBOL_CODE_SHORT"
:
"C"
}
,
{
"ID"
:
4
,
"NAME"
:
"Company"
,
"SYMBOL_CODE"
:
"COMPANY"
,
"SYMBOL_CODE_SHORT"
:
"CO"
}
,
{
"ID"
:
5
,
"NAME"
:
"Invoice (old version)"
,
"SYMBOL_CODE"
:
"INVOICE"
,
"SYMBOL_CODE_SHORT"
:
"I"
}
,
{
"ID"
:
31
,
"NAME"
:
"Invoice"
,
"SYMBOL_CODE"
:
"SMART_INVOICE"
,
"SYMBOL_CODE_SHORT"
:
"SI"
}
,
{
"ID"
:
7
,
"NAME"
:
"Estimate"
,
"SYMBOL_CODE"
:
"QUOTE"
,
"SYMBOL_CODE_SHORT"
:
"Q"
}
,
{
"ID"
:
8
,
"NAME"
:
"Requisites"
,
"SYMBOL_CODE"
:
"REQUISITE"
,
"SYMBOL_CODE_SHORT"
:
"RQ"
}
,
{
"ID"
:
36
,
"NAME"
:
"Document"
,
"SYMBOL_CODE"
:
"SMART_DOCUMENT"
,
"SYMBOL_CODE_SHORT"
:
"DO"
}
,
{
"ID"
:
39
,
"NAME"
:
"Company Document"
,
"SYMBOL_CODE"
:
"SMART_B2E_DOC"
,
"SYMBOL_CODE_SHORT"
:
"SBD"
}
,
{
"ID"
:
177
,
"NAME"
:
"Equipment Purchase"
,
"SYMBOL_CODE"
:
"DYNAMIC_177"
,
"SYMBOL_CODE_SHORT"
:
"Tb1"
}
,
{
"ID"
:
156
,
"NAME"
:
"Purchase"
,
"SYMBOL_CODE"
:
"DYNAMIC_156"
,
"SYMBOL_CODE_SHORT"
:
"T9c"
}
]
}
As a result, we obtained a list of all CRM object types in Bitrix24 with their identifiers. For the next requests, we will use
ID
:
177
and
SYMBOL_CODE_SHORT
:
Tb1
for the SPA "Equipment Purchase".
2. Retrieving the SPA Element ID
2. Retrieving the SPA Element ID
To obtain the SPA element ID, we use the method
crm.item.list
with the following parameters:
entityTypeId
—
177
, the value is equal to the
ID
from the previous method's result.
filter[title]
— specify the name of the element to search for.
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
177
,
// ID from the result of crm.enum.ownertype
select
: [
"id"
,
// selected fields
"title"
],
filter
: {
"title"
:
"Washing Machine"
,
// name of the element
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
177
, // ID
from
the result of crm.
enum
.ownertype
'select'
=> [
'id'
, // selected fields
'title'
],
'filter'
=> [
'title'
=>
'Washing Machine'
, // name of the element
]
]
);
As a result, we obtained the SPA element ID — a parameter necessary for the next request.
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
29
,
"title"
:
"Washing Machine"
}
]
}
,
"total"
:
1
}
3. Creating a Task Linked to the SPA Element
3. Creating a Task Linked to the SPA Element
To create a task, we use the method
tasks.task.add
with the following parameters:
UF_CRM_TASK
— specify the value
Tb1_29
. This is the short symbolic code type
SYMBOL_CODE_SHORT
:
Tb1
from the results of
crm.enum.ownertype
and the SPA element
id
:
29
from the results of
crm.item.list
.
TITLE
— the task title, a required field. Without a title, the task will not be created.
CREATED_BY
— the ID of the task creator, this field cannot be empty. If not filled, the creator will automatically be the one sending the request.
RESPONSIBLE_ID
— the ID of the task performer, a required field. Without a performer, the task will not be created.
JS
PHP
BX24
.
callMethod
(
'tasks.task.add'
,
{
fields
: {
TITLE
:
'task for test'
,
// task title
RESPONSIBLE_ID
:
1
,
// performer
UF_CRM_TASK
: [
// array of CRM elements
"Tb1_29"
]
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
'tasks.task.add'
,
[
'fields'
=> [
'TITLE'
=>
'task for test'
, // task title
'RESPONSIBLE_ID'
=>
1
, // performer
'UF_CRM_TASK'
=> [ //
array
of CRM elements
'Tb1_29'
]
]
]
);
As a result, we created a task with ID
3731
.
{
"result"
:
{
"task"
:
{
"id"
:
"3731"
,
"parentId"
:
null
,
"title"
:
"task for test"
,
"description"
:
""
,
"mark"
:
null
,
"priority"
:
"1"
,
"multitask"
:
"N"
,
"notViewed"
:
"N"
,
"replicate"
:
"N"
,
"stageId"
:
"0"
,
"createdBy"
:
"1"
,
"createdDate"
:
"2025-01-20T14:30:58+02:00"
,
"responsibleId"
:
"1"
,
"changedBy"
:
"1"
,
"changedDate"
:
"2025-01-20T14:30:58+02:00"
,
"statusChangedBy"
:
null
,
"closedBy"
:
null
,
"closedDate"
:
null
,
"activityDate"
:
"2025-01-20T14:30:58+02:00"
,
"dateStart"
:
null
,
"deadline"
:
null
,
"startDatePlan"
:
null
,
"endDatePlan"
:
null
,
"guid"
:
"{34429425-80c6-4927-83bd-220e67bcc202}"
,
"xmlId"
:
null
,
"commentsCount"
:
null
,
"serviceCommentsCount"
:
null
,
"allowChangeDeadline"
:
"N"
,
"allowTimeTracking"
:
"N"
,
"taskControl"
:
"N"
,
"addInReport"
:
"N"
,
"forkedByTemplateId"
:
null
,
"timeEstimate"
:
"0"
,
"timeSpentInLogs"
:
null
,
"matchWorkTime"
:
"N"
,
"forumTopicId"
:
null
,
"forumId"
:
null
,
"siteId"
:
"s1"
,
"subordinate"
:
"Y"
,
"exchangeModified"
:
null
,
"exchangeId"
:
null
,
"outlookVersion"
:
"1"
,
"viewedDate"
:
null
,
"sorting"
:
null
,
"durationFact"
:
null
,
"isMuted"
:
"N"
,
"isPinned"
:
"N"
,
"isPinnedInGroup"
:
"N"
,
"flowId"
:
null
,
"descriptionInBbcode"
:
"Y"
,
"status"
:
"2"
,
"statusChangedDate"
:
"2025-01-20T14:30:58+02:00"
,
"durationPlan"
:
null
,
"durationType"
:
"days"
,
"favorite"
:
"N"
,
"groupId"
:
"0"
,
"auditors"
:
[
]
,
"accomplices"
:
[
]
,
"checklist"
:
[
]
,
"group"
:
[
]
,
"creator"
:
{
"id"
:
"1"
,
"name"
:
"Viola"
,
"link"
:
"/company/personal/user/1/"
,
"icon"
:
"https://your-domain.bitrix24.com/b13743910/resize_cache/2267/c0120a8d7c10d63c83e32398d1ec4d9e/main/c7b/c7bd44b1babaa5448125dd97d038ce1b/d5fb56b94dc2c3cd8c006a2c595a4895.jpg"
,
"workPosition"
:
""
}
,
"responsible"
:
{
"id"
:
"1"
,
"name"
:
"Viola"
,
"link"
:
"/company/personal/user/1/"
,
"icon"
:
"https://your-domain.bitrix24.com/b13743910/resize_cache/2267/c0120a8d7c10d63c83e32398d1ec4d9e/main/c7b/c7bd44b1babaa5448125dd97d038ce1b/d5fb56b94dc2c3cd8c006a2c595a4895.jpg"
,
"workPosition"
:
""
}
,
"accomplicesData"
:
[
]
,
"auditorsData"
:
[
]
,
"newCommentsCount"
:
0
,
"action"
:
{
"accept"
:
false
,
"decline"
:
false
,
"complete"
:
true
,
"approve"
:
false
,
"disapprove"
:
false
,
"start"
:
true
,
"pause"
:
false
,
"delegate"
:
true
,
"remove"
:
true
,
"edit"
:
true
,
"defer"
:
true
,
"renew"
:
false
,
"create"
:
true
,
"changeDeadline"
:
true
,
"checklistAddItems"
:
true
,
"addFavorite"
:
true
,
"deleteFavorite"
:
false
,
"rate"
:
true
,
"take"
:
false
,
"edit.originator"
:
false
,
"checklist.reorder"
:
true
,
"elapsedtime.add"
:
true
,
"dayplan.timer.toggle"
:
false
,
"edit.plan"
:
true
,
"checklist.add"
:
true
,
"favorite.add"
:
true
,
"favorite.delete"
:
false
}
,
"checkListTree"
:
{
"nodeId"
:
0
,
"fields"
:
{
"id"
:
null
,
"copiedId"
:
null
,
"entityId"
:
null
,
"userId"
:
1
,
"createdBy"
:
null
,
"parentId"
:
null
,
"title"
:
""
,
"sortIndex"
:
null
,
"displaySortIndex"
:
""
,
"isComplete"
:
false
,
"isImportant"
:
false
,
"completedCount"
:
0
,
"members"
:
[
]
,
"attachments"
:
[
]
}
,
"action"
:
[
]
,
"descendants"
:
[
]
}
,
"checkListCanAdd"
:
true
}
}
}
Verifying the Created Task
Verifying the Created Task
The obtained result does not contain information about the linked CRM elements. To check if the SPA element has been successfully attached to the task, we will execute the method
tasks.task.get
with the following parameters:
taskId
—
3731
, the ID of the created task from the result of the previous method.
select
—
UF_CRM_TASK
, the field "Link to CRM elements". The method
tasks.task.get
will not return the link field without
UF_CRM_TASK
in
select
.
JS
PHP
BX24
.
callMethod
(
'tasks.task.get'
,
{
taskId
:
3731
,
// task ID
select
: [
'ID'
,
'UF_CRM_TASK'
]
// selected fields
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
'tasks.task.get'
,
[
'taskId'
=>
3731
, // task ID
'select'
=> [
'ID'
,
'UF_CRM_TASK'
] // selected fields
]
);
As a result, we obtained the value of the
ufCrmTask
field:
Tb1_29
. The SPA element has been successfully attached.
{
"result"
:
{
"task"
:
{
"id"
:
"3731"
,
"ufCrmTask"
:
[
"Tb1_29"
]
,
"ufTaskWebdavFiles"
:
false
,
"ufMailMessage"
:
null
,
"ufAuto615763798639"
:
null
,
"ufAuto885808697713"
:
null
,
"ufAuto168639979930"
:
null
,
"ufAuto441714695872"
:
null
,
"ufAuto179124361273"
:
null
,
"favorite"
:
"N"
,
"group"
:
[
]
,
"action"
:
{
"accept"
:
false
,
"decline"
:
false
,
"complete"
:
true
,
"approve"
:
false
,
"disapprove"
:
false
,
"start"
:
true
,
"pause"
:
false
,
"delegate"
:
true
,
"remove"
:
true
,
"edit"
:
true
,
"defer"
:
true
,
"renew"
:
false
,
"create"
:
true
,
"changeDeadline"
:
true
,
"checklistAddItems"
:
true
,
"addFavorite"
:
true
,
"deleteFavorite"
:
false
,
"rate"
:
true
,
"take"
:
false
,
"edit.originator"
:
false
,
"checklist.reorder"
:
true
,
"elapsedtime.add"
:
true
,
"dayplan.timer.toggle"
:
false
,
"edit.plan"
:
true
,
"checklist.add"
:
true
,
"favorite.add"
:
true
,
"favorite.delete"
:
false
}
}
}
}
Code Example
Code Example
JS
PHP
// Variables for user input
var
smartProcessName =
'smart_process_name'
;
// Name of the SPA
var
itemName =
'item_name'
;
// Name of the SPA element
var
responsibleId =
'RESPONSIBLE_ID'
;
// ID of the person responsible for the task
var
taskTitle =
'task_title'
;
// Title of the task
// Function to create a task linked to the SPA element
function
createTaskWithSmartProcess
(
) {
// Retrieving entity type and SPA identifiers
BX24
.
callMethod
(
'crm.enum.ownertype'
,
{},
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
'Error retrieving entity types:'
, result.
error
());
return
;
}
// Finding the required SPA
var
smartProcess = result.
data
().
find
(
function
(
process
) {
return
process.
NAME
=== smartProcessName;
});
if
(!smartProcess) {
console
.
error
(
'SPA not found'
);
return
;
}
var
symbolCodeShort = smartProcess.
SYMBOL_CODE_SHORT
;
// Searching for the SPA element using a title filter
BX24
.
callMethod
(
'crm.item.list'
,
{
entityTypeId
: smartProcess.
ID
,
select
: [
"id"
,
"title"
],
filter
: {
"title"
: itemName }
},
function
(
itemResult
) {
if
(itemResult.
error
()) {
console
.
error
(
'Error retrieving SPA elements:'
, itemResult.
error
());
return
;
}
if
(itemResult.
data
().
items
.
length
===
0
) {
console
.
error
(
'SPA element not found'
);
return
;
}
var
itemId = itemResult.
data
().
items
[
0
].
id
;
// Creating the task
BX24
.
callMethod
(
'tasks.task.add'
,
{
fields
: {
TITLE
: taskTitle,
// Using the entered task title
RESPONSIBLE_ID
: responsibleId,
// Adding the responsible ID
UF_CRM_TASK
: [symbolCodeShort +
'_'
+ itemId]
}
},
function
(
taskResult
) {
if
(taskResult.
error
()) {
console
.
error
(
'Error creating task:'
, taskResult.
error
());
}
else
{
console
.
log
(
'Task successfully created!'
, taskResult.
data
());
}
}
);
}
);
}
);
}
// Calling the function to create the task
createTaskWithSmartProcess
();
require_once
(
'crest.php'
);
// Variables for user input
$smartProcessName
=
'smart_process_name'
;
// Name of the SPA
$itemName
=
'item_name'
;
// Name of the SPA element
$responsibleId
=
'RESPONSIBLE_ID'
;
// ID of the person responsible for the task
$taskTitle
=
'task_title'
;
// Title of the task
// Function to create a task linked to the SPA element
function
createTaskWithSmartProcess
(
$smartProcessName
,
$itemName
,
$responsibleId
,
$taskTitle
)
{
// Retrieving entity type and SPA identifiers
$result
=
CRest
::
call
(
'crm.enum.ownertype'
, []);
if
(
isset
(
$result
[
'error'
])) {
echo
'Error retrieving entity types: '
.
$result
[
'error_description'
];
return
;
}
// Finding the required SPA
$smartProcess
=
null
;
foreach
(
$result
[
'result'
]
as
$process
) {
if
(
$process
[
'NAME'
] ===
$smartProcessName
) {
$smartProcess
=
$process
;
break
;
}
}
if
(!
$smartProcess
) {
echo
'SPA not found'
;
return
;
}
$symbolCodeShort
=
$smartProcess
[
'SYMBOL_CODE_SHORT'
];
// Searching for the SPA element using a title filter
$itemResult
=
CRest
::
call
(
'crm.item.list'
, [
'entityTypeId'
=>
$smartProcess
[
'ID'
],
'select'
=> [
'id'
,
'title'
],
'filter'
=> [
'title'
=>
$itemName
]
]);
if
(
isset
(
$itemResult
[
'error'
])) {
echo
'Error retrieving SPA elements: '
.
$itemResult
[
'error_description'
];
return
;
}
if
(
count
(
$itemResult
[
'result'
][
'items'
]) ===
0
) {
echo
'SPA element not found'
;
return
;
}
$itemId
=
$itemResult
[
'result'
][
'items'
][
0
][
'id'
];
// Creating the task
$taskResult
=
CRest
::
call
(
'tasks.task.add'
, [
'fields'
=> [
'TITLE'
=>
$taskTitle
, // Using the entered task title
'RESPONSIBLE_ID'
=>
$responsibleId
, // Adding the responsible ID
'UF_CRM_TASK'
=> [
$symbolCodeShort
.
'_'
.
$itemId
]
]
]);
if
(
isset
(
$taskResult
[
'error'
])) {
echo
'Error creating task: '
.
$taskResult
[
'error_description'
];
}
else
{
echo
'Task successfully created!'
;
print_r
(
$taskResult
[
'result'
]);
}
}
// Calling the function to create the task
createTaskWithSmartProcess
(
$smartProcessName
,
$itemName
,
$responsibleId
,
$taskTitle
);
Copied
Was the article helpful?
Yes
No
Previous
How to create a comment in a task and attach a file to it
Next
Tutorials and use-cases for REST in the Open Channels module

---

