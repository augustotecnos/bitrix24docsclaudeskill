---
description: Miscellaneous API endpoints
methods:
- user.get
pages: 2
title: Miscellaneous API endpoints
---
# Miscellaneous API endpoints
> Miscellaneous API endpoints
> **2 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Bitrix24 Tools Available for Developers](#bitrix24-tools-available-for-developers)
- [Data Types and Parameter Formats in REST API](#data-types-and-parameter-formats-in-rest-api)

---

## Bitrix24 Tools Available for Developers

**Source:** https://apidocs.bitrix24.com/api-reference/index

Bitrix24 Tools Available for Developers | Bitrix24 REST API and Marketplace Applications
Bitrix24 Tools Available for Developers
Bitrix24 Tools Available for Developers
Bitrix24 is a comprehensive suite of interconnected business tools. The deep integration among them and a unified REST API allow for the creation of highly flexible automation scenarios.
The main tools available through the REST API can be divided into the following key sections:
REST
API
Information
Management
Communications
Company
Management
Execution
Discipline
Sales
Disk24
Application
Storage
Smart
Processes
Universal
Lists
Telephony
Chats
Chatbots
SMS/Messages
Notifications
News
Open
Lines
Employees
Work
Time
Management
Company
Structure
Mail
Services
Projects
Scrum
Calendar
Tasks
CRM
Inventory
Management
Payments
Deliveries
Cash
Registers
Online
Stores
Sites/Landing
Pages
Document
Generator
By understanding the needs required to implement the necessary scenario, you will be able to find descriptions of the methods for these tools in the documentation.
It is important to utilize the existing functionality of Bitrix24, eliminating the need to write everything from scratch. It is essential to seek new interaction scenarios between the existing tools that are part of Bitrix24. Such scenarios open up vast opportunities and can be relatively simple to implement technically.
Bitrix24 Tool
Bitrix24 Tool
Bitrix24 is a comprehensive product that combines many different tools integrated with each other. This integration allows developers to offer users complete business scenarios using multiple tools.
The API reference contains descriptions of the available methods, events, and widgets for the corresponding Bitrix24 tools.
General Methods and Events
BIconnector: Overview of Methods
Overview of CRM
AI in Bitrix24
News Feed
Online Store
Users
Workflows
Tasks
Document Generator
Calendar: Overview of Methods
Payment Systems
Company Structure: Overview of Methods
User Agreements: Overview of Methods
Workgroups and Projects
Open Channels
Online Booking
Chatbots
Chats
Sites and Stores
Message Providers, SMS Providers
Universal Lists
Work Time Accounting
Data Storage
Trade Catalog
Telephony
Drive
Mail Services
Was the article helpful?
Yes
No
Previous
CRM widget
Next
Data Types and Parameter Formats

---

## Data Types and Parameter Formats in REST API

**Source:** https://apidocs.bitrix24.com/api-reference/data-types

Data Types and Parameter Formats in REST API | Bitrix24 REST API and Marketplace Applications
Basic Data Types
Data Types and Parameter Formats in REST API
Basic Data Types
Links to Objects and Directories
Time Object
We are still updating this page
Some data may be missing — we will complete it soon.
Basic Data Types
Basic Data Types
Type
Descriptions and Values
integer
Whole number. For example, 10116
boolean
Boolean value. Most often takes values 'Y' or 'N'. In some outdated methods, it may take values 0 or 1. Read the method descriptions carefully!
double
Floating-point number. For example, 100.15
date
Date in the format 'YYYY-MM-DD'. For example, '2023-12-28', which means December 28, 2023.
datetime
Date and time in the format 'YYYY-MM-DDThh:mm:ss±hh:mm'. For example, '2023-12-28T14:05:48', which means 14 hours, 5 minutes, and 48 seconds on December 28, 2023.
string
Single-line string value. For example, 'Supply Agreement'
text
Multi-line string value, applicable in some special fields of objects.
file
Attached file. Can take a numeric value with a unique file identifier in the system or a value in the form of an array describing a series of file parameters. Read about working with files in the corresponding section.
array
A set of simple type elements. For example, an array of integers [1, 5, 67] or strings ['deal', 'lead', 'quote']
object
Structure of arbitrary nesting level containing elements of different data types. For example,
{
data
:
{
foo
:
"bar"
,
bar
:
"foo"
,
items
:
[
1
,
100
,
200
]
}
}
any
Various data types can serve as parameter values.
Features of Dates and Times
When working with fields of types
date
and
datetime
, note that each user in Bitrix24 can have their own time zone specified in the settings. The Bitrix24 user interface displays dates and times, adapting them to the specific user; however, at the API level, all dates and times are stored according to the server parameters. Read more details in the corresponding material.
Links to Objects and Directories
Links to Objects and Directories
Fields of Bitrix24 objects can contain values that refer to other objects or to values from directories. Technically, such values are most often stored and indicated as integer identifiers of specific objects or directory elements. However, for convenience and to emphasize such relationships, we will use special types in the documentation, such as
crm_company
or
crm_status
. Below are examples of such types with links to methods for obtaining possible values.
Type
Descriptions and Values
user
Integer identifier of a Bitrix24 user. For example, 1. User identifiers can be obtained using the
user.get
method.
Data directories of various Bitrix24 tools:
CRM
Online Store
Product Catalog
Time Object
Time Object
The
time
object is present in the responses to all REST requests and contains information about the execution time of the request.
Name
type
Description
start
[
double
]
Timestamp of the moment the request was initialized.
finish
[
double
]
Timestamp of the moment the request execution was completed.
duration
[
double
]
How long in milliseconds the request took, i.e., the difference between
finish
and
start
.
date_start
[
string
]
String representation of the date and time of the moment the request was initialized.
date_finish
[
double
]
String representation of the date and time of the moment the request execution was completed.
operating_reset_at
[
timestamp
]
Timestamp of the moment when the limit on REST API resources will be reset.
Read more details in the article
operation limit
.
operating
[
double
]
In how many milliseconds the limit on REST API resources will be reset.
Read more details in the article
operation limit
.
Copied
Was the article helpful?
Yes
No
Previous
Tools and Scenarios
Next
Method permissions

---

