---
description: Local integrations setup and configuration
methods:
- crm.contact.get
pages: 9
title: Local integrations setup and configuration
---
# Local integrations setup and configuration
> Local integrations setup and configuration
> **9 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Overview of Tools for Local Integrations](#overview-of-tools-for-local-integrations)
- [Typical use-cases and scenarios](#typical-use-cases-and-scenarios)
- [Incoming and Outgoing Webhooks](#incoming-and-outgoing-webhooks)
- [Local Applications](#local-applications)
- [Static Local Application](#static-local-application)
- [Server-side Local Application with User Interface](#server-side-local-application-with-user-interface)
- [Server-side Local Application without User Interface](#server-side-local-application-without-user-interfa)
- [Developer Resources in Bitrix24](#developer-resources-in-bitrix24)
- [How to Fix the "Site Does Not Allow Connection" Error When Opening the Application](#how-to-fix-the-site-does-not-allow-connection-erro)

---

## Overview of Tools for Local Integrations

**Source:** https://apidocs.bitrix24.com/local-integrations/index

Overview of Tools for Local Integrations | Bitrix24 REST API and Marketplace Applications
Continue Your Exploration
Overview of Tools for Local Integrations
Tools for "local integrations" help solve specific automation tasks on a given Bitrix24 account.
What tasks are you most likely to encounter?
Importing data into the CRM or another tool.
Integrations with internal accounting or inventory management systems.
Simple automation related to bulk processing of customer data.
Embedding a couple of your buttons in the right places within Bitrix24.
To tackle these tasks, it's best to use the REST API along with the convenient tools found in the
Developer resources
section of Bitrix24, where you will find ready-made examples for typical tasks using
incoming and outgoing webhooks
, as well as
local applications
.
Continue Your Exploration
Continue Your Exploration
Inbound and outbound webhooks in the REST API video course
Incoming and Outgoing Webhooks
Local Applications
How to Fix the "Site Does Not Allow Connection" Error When Opening the Application
Was the article helpful?
Yes
No
Previous
How to create an open channels connector for chat on the site
Next
Typical Use-Cases and Scenarios

---

## Typical use-cases and scenarios

**Source:** https://apidocs.bitrix24.com/local-integrations/use-cases

Typical use-cases and scenarios | Bitrix24 REST API and Marketplace Applications
Typical use-cases and scenarios
Typical use-cases and scenarios
Use local development tools to solve typical tasks:
How to collect contacts from a form on the website and transfer them to CRM?
How to embed an application in a CRM detail form?
How to import data into CRM?
How to automatically assign tasks to employees?
How to create your own chatbot?
Was the article helpful?
Yes
No
Previous
Overview
Next
Incoming and Outgoing Webhooks

---

## Incoming and Outgoing Webhooks

**Source:** https://apidocs.bitrix24.com/local-integrations/local-webhooks

Incoming and Outgoing Webhooks | Bitrix24 REST API and Marketplace Applications
Incoming Webhook
Incoming and Outgoing Webhooks
Incoming Webhook
Outgoing Webhook
Continue Learning
We are still updating this page
Some data may be missing — we will complete it shortly.
A local webhook is a simplified way to access the methods and events of the Bitrix24 REST API, specifically designed for use within a single account.
Local webhooks are divided into incoming and outgoing.
Incoming Webhook
Incoming Webhook
Through the user interface of the Developer resources section, you can obtain and record an authorization key — an incoming webhook.
This key can then be used to call REST methods, and it does not have an expiration date (unlike OAuth 2.0 authorization tokens).
This makes webhooks an exceptionally simple and convenient mechanism for working with REST, but it is important to understand that this simplicity has its drawbacks:
User participation is required to create a webhook (you cannot generate webhooks automatically).
Since the webhook does not expire, any "leak" of the webhook URL can lead to unauthorized access to your Bitrix24 within the permissions of that specific webhook. Therefore, this mechanism is suitable for "internal" integrations but not for mass-market use cases.
A number of REST methods are not available for use through webhooks, as their logic requires an "application context," and there is no application in Bitrix24 terms for webhooks (in particular, methods for embedding applications in the Bitrix24 interface, telephony events, some chatbot events, etc.).
Despite these limitations, for the vast majority of integration tasks within a specific project, webhooks are an ideal option for working with the REST API.
Typical use-cases and scenarios
Typical use-cases and scenarios for REST API in CRM and tutorials
Add a New Prompt "Joke"
You can create an incoming webhook from the
Developer resources
section (
Applications > Developer resources, "Ready-made scenarios" tab > Other > Incoming webhook
).
In the opened form:
change the name of the webhook
in the request generator, select the REST API method (you can read the method description and download a ready-made code example with the necessary parameters for making requests)
test the webhook by clicking the
Execute
button
specify access permissions, allowing requests only from certain Bitrix24 tools
The request generator will provide a sample URL that should be used when sending data from an external system to Bitrix24.
The URL consists of:
doc-test-b24.bitrix24.com
— the address of your Bitrix24
/rest
— indicating that the work is being done through REST with webhooks
/1
— the identifier of the user who created the webhook
/173glortu42lvpju
— the secret code
Attention!
This code is confidential information. It must be kept secret.
/crm.contact.get
— the called REST API method. In this case, it is the method that returns a contact by its identifier.
.json
— an optional parameter ("transport"). When creating new webhooks, it can be omitted (by default,
.json
will be used). In the ready-made solutions constructor,
.json
is explicitly included.
?ID=42
— parameters required for the specific method. In this case, it is the identifier. Parameters are specified after the question mark and separated by the
&
symbol.
Outgoing Webhook
Outgoing Webhook
For some scenarios, it would be convenient for our automation to trigger automatically when a user changes some data in Bitrix24. For this, there is a tool in local integrations called "Outgoing webhook."
Typical use-cases and scenarios
Typical use-cases and scenarios for REST API in CRM and tutorials
Add a New Prompt "Joke"
Attention!
An active license is required for the outgoing webhook to work in the on-premise version of Bitrix24; it will not work on demo accounts.
You can create an outgoing webhook from the
Developer resources
section (
Applications > Developer resources, "Ready-made scenarios" tab > Other > Outgoing webhook
).
In the opened form:
Change the name of the webhook.
Specify
the URL of your handler
— the page on an external resource where the webhook will send requests.
Choose the event that will trigger the webhook.
When creating an outgoing webhook, a token will be generated as a string of random characters. This code will allow you to verify within the handler that the handler was indeed called by your Bitrix24.
Place the following code on the handler page:
Example handler code for the event
ONCRMDEALUPDATE
<?php
print_r
(
$_REQUEST
);
writeToLog
(
$_REQUEST
,
'incoming'
);
/**
* Write data to log file.
*
*
@param
mixed $data
*
@param
string $title
*
*
@return
bool
*/
function
writeToLog
(
$data
,
$title
=
''
)
{
$log
=
"\n------------------------\n"
;
$log
.=
date
(
"Y.m.d G:i:s"
) .
"\n"
;
$log
.= (
strlen
(
$title
) >
0
?
$title
:
'DEBUG'
) .
"\n"
;
$log
.=
print_r
(
$data
,
1
);
$log
.=
"\n------------------------\n"
;
file_put_contents
(
getcwd
() .
'/hook.log'
,
$log
, FILE_APPEND);
return
true
;
}
To test, open any deal for editing and save the changes; the log will display a history similar to this:
2017.01.17 12:58:29
incoming
Array
(
[event] => ONCRMDEALUPDATE
[data] => Array
(
[FIELDS] => Array
(
[ID] => 662
)
)
[ts] => xxx
[auth] => Array
(
[domain] => xxx.bitrix24.com
[client_endpoint] => https://xxx.bitrix24.com/rest/
[server_endpoint] => https://oauth.bitrix.info/rest/
[member_id] => xxx
[application_token] => xxx
)
)
To ensure the outgoing webhook works, make sure that the necessary
network access
is open on your server.
Continue Learning
Continue Learning
Local Applications
Copied
Was the article helpful?
Yes
No
Previous
Typical Use-Cases and Scenarios
Next
Local Applications

---

## Local Applications

**Source:** https://apidocs.bitrix24.com/local-integrations/local-apps

Local Applications | Bitrix24 REST API and Marketplace Applications
Local Applications
Local Applications
Local applications are those that are described and added directly to a specific Bitrix24. This is the essence of the term "local."
The account administrator decides what permissions to grant such an application and how it will be named in the interface.
There are two types of such applications:
"Static" applications based on HTML/JS. In fact, using these technologies, you can implement single-page applications by accessing the B24 REST API with the JS SDK. They are represented in the interface as a separate page (with a link from the left menu). Static applications cannot receive Bitrix24 events.
"Server" applications with a back-end in any suitable programming languages (PHP, Python, and others). They can access the REST API using the OAuth 2.0 protocol and can also receive events from Bitrix24 in their handlers. They are presented in the interface as a separate page, as well as in the form of embedded popup dialogs in the available embedding objects of Bitrix24. There is an option where the application does not manifest itself in the interface but uses REST.
Continue Learning
Continue Learning
Static Local Application
Server-side Local Application with User Interface
Server-side Local Application without User Interface
Was the article helpful?
Yes
No
Previous
Incoming and Outgoing Webhooks
Next
Static Application

---

## Static Local Application

**Source:** https://apidocs.bitrix24.com/local-integrations/static-local-app

Static Local Application | Bitrix24 REST API and Marketplace Applications
Static Local Application
Static Local Application
We are still updating this page
Some data may be missing — we will complete it soon.
Attention!
The static local application and its deployment described below are intended for cloud Bitrix24 accounts.
This type can be used in on-premise accounts if:
the application is uploaded to any folder in the file structure of the on-premise account
the handler specifies the path to this folder
The archive with the example contains one file and represents a ready-made application that accesses the REST API and displays the full name of the current user.
Download archive
You can install the local application either from the
Developer resources
section (
Applications > Developer resources, tab "Ready-made scenarios" > Other > Local application
), or by following this path: Applications (1) — Developer resources (2) — Other (3) — Local application (4):
In the opened form, fill in the basic fields, upload the archive, and specify the necessary permissions (for our example, user management permissions are required):
After saving, the new application will be displayed in the integrations list (
Applications > Developer resources > Integrations
) in your Bitrix24.
Find
Full Name
in the left menu or in the
More
menu in the Applications section and launch it. The launched application will display the full name of the current user, retrieving it via the REST API through the JS library. Since the static local application operates within the Bitrix24 interface, the JS SDK automatically obtains and uses the authorization of the current user who opened the application, and acts solely within the permissions of that user.
Continue Exploring
Continue Exploring
Server-side Local Application with User Interface
Server-side Local Application without User Interface
Was the article helpful?
Yes
No
Previous
Local Applications
Next
Server-Side Application with UI

---

## Server-side Local Application with User Interface

**Source:** https://apidocs.bitrix24.com/local-integrations/serverside-local-app-with-ui

Server-side Local Application with User Interface | Bitrix24 REST API and Marketplace Applications
Server-side Local Application with User Interface
Server-side Local Application with User Interface
The application utilizes a simplified version of OAuth 2.0 and is displayed as an additional page that shows the full name of the current user. The archive of the example consists of the
CRest SDK
, a
modification of the CRest SDK
for the simplified use of OAuth 2.0, and a PHP file index.php containing the example code. You need to place the files from the example archive on your web server before installing it in Bitrix24.
Attention!
This example operates based on the
CRest SDK
. Before using the example, you must open the file
checkserver.php
in your browser and verify the correctness of your server settings.
Learn more
.
Download the archive
You can install the on-premise application either from the
Developer resources
section (
Applications > Developer resources, tab "Ready-made scenarios" > Other > On-premise application
), or by following this path: Applications (1) — Developer resources (2) — Other (3) — On-premise application (4):
In the opened form, fill in the basic fields and specify the necessary access permissions for the application (for our example, user management permissions are required), indicating the
Path to your handler
(this means that your application must already be physically accessible via URL over HTTPS before you add it to your Bitrix24).
After saving, the new application will be displayed in the list of integrations (
Applications > Developer resources > Integrations
) in your Bitrix24.
Find the application
Full Name
in the left menu or in the
More
menu under Applications and launch it.
The launched application will output debug information about the authorization data of the current user, as well as the full name of the current user, retrieving it via the REST API using this authorization data.
Since this application operates within the Bitrix24 interface and uses the authorization of the current user who opened the application, it acts solely within the access permissions of that user.
Continue Learning
Continue Learning
Static Local Application
Server-side Local Application without User Interface
Was the article helpful?
Yes
No
Previous
Static Application
Next
Server-Side Application without UI

---

## Server-side Local Application without User Interface

**Source:** https://apidocs.bitrix24.com/local-integrations/serverside-local-app-with-no-ui

Server-side Local Application without User Interface | Bitrix24 REST API and Marketplace Applications
Installation
Server-side Local Application without User Interface
Installation
Usage
Continue Exploring
Installation
Installation
The example consists of the
CRest SDK
and a PHP file with an example that you need to place on your web server before adding the application to your Bitrix24. The application can obtain user authorization from Bitrix24 and, while being outside of Bitrix24, access the REST API to retrieve the full name of the user who installed it.
Attention!
This example is based on the
CRest SDK
. Before using the example, you need to open the
checkserver.php
file in your browser and verify the correctness of your server settings.
Learn more
.
Download archive
You can install the local application either from the
Developer resources
section (
Applications > Developer resources, tab "Ready-made scenarios" > Other > Local application
), or by following this path: Applications (1) — Developer resources (2) — Other (3) — Local application (4):
In the opened form, fill in the basic fields and specify the necessary access permissions for the application (for our example, permissions to manage users are required), indicating the
Path to your handler
(this means that your application must already be physically accessible via URL using HTTPS before you start adding it to your Bitrix24).
You need to enable the option
Application uses only API
— this indicates to Bitrix24 that your application will not display a user interface within Bitrix24. In this case, as you will see, the fields where the menu item name for calling the application from Bitrix24 is usually specified will be hidden. Applications that have the "Application uses only API" option enabled either provide a user interface at some URL of their own or do not provide a user interface at all.
Also, note that we filled in the
Path for initial installation
field by specifying
install.php
from the example archive. This URL is called only once when saving the local application form. This URL serves as the handler for the event
ONAPPINSTALL
, where we save the tokens of the user who installed the application.
After saving, you will remain in the addition form, but Bitrix24 will immediately show you the authorization keys for the OAuth 2.0 protocol, which you will need inside the application code:
Since the application without an interface operates outside of Bitrix24, it must implement the full OAuth 2.0 authorization protocol. Open the
settings.php
file from the example and fill in the constants with the application code
C_REST_CLIENT_ID
and the secret key
C_REST_CLIENT_SECRET
, obtained when saving the form.
Upload the modified example to your server.
In Bitrix24, you can go to the
Integrations
list (
Applications > Developer resources > Integrations
) and check for the appearance of the new application in the list of local applications in your Bitrix24:
Usage
Usage
Attention!
This example is based on the
CRest SDK
. Before using the example, you need to open the
checkserver.php
file in your browser and verify the correctness of your server settings.
Learn more
.
Open the
index.php
file from the example in your browser via your URL.
The launched application will output the full name of the user who installed the application, retrieving it via the REST API using the authorization data saved during the application's creation, while also automatically renewing tokens (if it turns out that they are invalid during the request).
Continue Exploring
Continue Exploring
Static Local Application
Server-side Local Application with User Interface
Copied
Was the article helpful?
Yes
No
Previous
Server-Side Application with UI
Next
Overview of the Developer's Area

---

## Developer Resources in Bitrix24

**Source:** https://apidocs.bitrix24.com/local-integrations/developers-area

Developer Resources in Bitrix24 | Bitrix24 REST API and Marketplace Applications
Ready-made Scenarios
Developer Resources in Bitrix24
Ready-made Scenarios
List of Ready-made Scenarios
Integrations
More About the Secret Code in the URL
Statistics
Continue Learning
In the
Developer Resources
section (
Applications > Developer Resources
), you'll find convenient tools to simplify the integration and enhancement of your Bitrix24:
The following tools are available:
Ready-made scenarios
Integrations
Statistics
Let's take a closer look at each of these tools.
Ready-made Scenarios
Ready-made Scenarios
This tab features ready-made scenarios for integration and enhancement, complete with code examples and pre-set parameters based on webhooks and local applications.
In the settings of each scenario, there is a REST request generator (1) that allows you to select the necessary parameter values for further use in external systems:
In the request generator, you can choose the REST API method, read the method description, download a ready-made code example (which already includes the necessary parameters for executing requests), and add your own parameters. You can also execute the request itself and get the result, checking the webhook's functionality.
The access permission settings (2) allow you to restrict request execution to specific Bitrix24 tools.
After saving, the created applications and webhooks will be displayed in the
Integrations
tab.
List of Ready-made Scenarios
List of Ready-made Scenarios
Ready-made scenarios are categorized as follows:
Import/Export Data
(copy client data, employee lists, tasks from any external source, or transfer data accumulated in Bitrix24 to an external system):
Import counterparties
Export counterparties
Other (implement your own scenarios for adding widgets to Bitrix24)
Integrate with External Systems
(automate lead collection from a website form, synchronize changes in client contact details with inventory or accounting systems):
Synchronize counterparties
Add leads
Automate Sales
(automatically move leads and deals through the Sales Funnel and verify data accuracy in CRM):
Move lead through the Sales Funnel
Move deal through the Sales Funnel
Automate Management
(automatically assign tasks to employees, inform management about emerging issues, and publish reports in the live feed):
Assign a task
Send a notification
Publish a report in the live feed
Monitor tasks
Embed Widget
(customize the Bitrix24 interface: display your information directly in the client card, sales scripts in the call card):
Display your data in the CRM card
Add your action to the CRM card
Add sales script to the call card
Generate invoice based on task labor costs
Add Chatbot
(create chatbots that will send notifications and reports to employees directly in the messenger):
Inform employees in chat
Forward messages from chat to the bot
Other
(create an incoming webhook, outgoing webhook, or local application):
Local application
Outgoing webhook
Incoming webhook
Integrations
Integrations
All created integrations (webhooks and applications) in the Bitrix24 account are displayed in a single list on the page:
This list shows the following information about integrations:
Creator
Name
Access permissions
Events
Widgets
You can customize the displayed fields by clicking the gear icon in the upper left corner of the list.
From this list, you can also edit the integration settings (or delete it).
Important!
The secret codes of
other people's
webhooks are not accessible even to the administrator. If an administrator edits someone else's webhook, the secret code will be reset, and the administrator will become the owner of that webhook.
More About the Secret Code in the URL
More About the Secret Code in the URL
The URL consists of:
doc-test-b24.bitrix24.com
— your Bitrix24 address
/rest
— indicating that the work is being done through REST with webhooks
/1
— the identifier of the user who created the webhook
/173glortu42lvpju
— the secret code
/crm.contact.get
— the invoked REST API method. In this case, the method that returns a contact by identifier
.json
— an optional parameter ("transport"). When creating new webhooks, it can be omitted (by default,
.json
will be used). In the ready-made solutions constructor,
.json
is explicitly included
?ID=42
— parameters required for the specific method. In this case, the identifier. Parameters are specified after the question mark and separated by the
&
symbol
Statistics
Statistics
This section displays the total number of daily REST requests for your Bitrix24, along with detailed statistics for each webhook, external integration, or application:
Continue Learning
Continue Learning
Evaluate the REST load in Bitrix24
Copied
Was the article helpful?
Yes
No
Previous
Server-Side Application without UI
Next
How to Fix the "Site Does Not Allow Connection" Error When Opening the Application

---

## How to Fix the "Site Does Not Allow Connection" Error When Opening the Application

**Source:** https://apidocs.bitrix24.com/local-integrations/site-does-not-allow-connection

How to Fix the "Site Does Not Allow Connection" Error When Opening the Application | Bitrix24 REST API and Marketplace Applications
Cause of the Error
How to Fix the "Site Does Not Allow Connection" Error When Opening the Application
Cause of the Error
How to Fix the Error
Configuring Frame Protection in On-Premise Bitrix24
Default Setting
Configuration Conflict
In server applications, an error may occur when loading pages:
The site "application_site_address" does not allow connection.
Cause of the Error
Cause of the Error
The error occurs when the application server prohibits loading pages in a frame. Details of the error can be found in the browser console.
Refused to display 'https://application_site_address/'; in a frame because it set 'X-Frame-Options' to 'sameorigin'.
This error means that the application server has a restriction on opening site pages in a frame from other sites. The restriction is controlled by the
X-Frame-Options
header. This header tells the browser whether pages from the site can be loaded through
<frame>/<iframe>
.
The default setting for most servers for the
X-Frame-Options
header is
sameorigin
. This value allows loading the site only if the frame and the application page are on the same domain.
The
X-Frame-Options
header for a single site can be specified on multiple servers: the main application server and intermediate proxy servers. If there are different
X-Frame-Options
headers, the error message will contain details of the conflicting headers:
Refused to display 'https://application_site_address/'; in a frame because it set multiple 'X-Frame-Options' headers with conflicting values ('ALLOW-FROM https://your-domain.bitrix24.com/, SAMEORIGIN'). Falling back to 'deny'.
How to Fix the Error
How to Fix the Error
To allow loading the site in a frame on a specific Bitrix domain, change the
X-Frame-Options
header settings. Make changes to the nginx configuration on the server with the application files and on intermediate proxy servers if they are used.
If you do not have access to the nginx configuration files or your settings differ, the server administrator or hosting administrator can provide guidance on header settings and grant access.
If you do not have access to the nginx configuration files or your settings differ, the server administrator or hosting administrator can provide guidance on header settings and grant access.
Find the configuration files that contain the
X-Frame-Options
header. Use the following command to search:
grep -iRl "X-Frame-Options" /etc/nginx
In the found file, change the header. Replace the restriction
SAMEORIGIN
with permission for the Bitrix24 domain:
add_header X-Frame-Options "ALLOW-FROM https://your-domain.bitrix24.com/";
If multiple files with the
X-Frame-Options
header are found, ensure that the settings in them do not conflict.
Check the nginx configuration with the command
nginx -t
.
If the response is "test is successful," you can reload the configuration. If there are errors in the response, first make corrections in the files mentioned in the error text.
Restart nginx with the command
nginx -s reload
. Changes will not take effect without a restart.
Configuring Frame Protection in On-Premise Bitrix24
Configuring Frame Protection in On-Premise Bitrix24
If the application server is an on-premise Bitrix24 on a BitrixVM virtual machine, frame protection can be configured in two places:
in the nginx server configuration
on the site — "Frame Protection" (Settings > Proactive Protection > Frame Protection)
Default Setting
Default Setting
The pre-installed setting for BitrixVM is the header
add_header X-Frame-Options SAMEORIGIN;
in the file /etc/nginx/bx/conf/general-add_header.conf.
When frame protection is enabled on the site, the same header
add_header X-Frame-Options SAMEORIGIN;
is added to the nginx configuration file /etc/nginx/bx/conf/general-add_header.conf.
Configuration Conflict
Configuration Conflict
With the default settings, BitrixVM may encounter a situation where the nginx configuration overrides the frame protection setting on the site:
the header will be active even if frame protection is disabled on the site
when frame protection is enabled, the header will be duplicated
One solution to the conflict is to use only one tool. It is recommended to use the "Frame Protection" tool on the site to avoid changing the server configuration files:
In BitrixVM, comment out the header in the file /etc/nginx/bx/conf/general-add_header.conf:
#add_header X-Frame-Options SAMEORIGIN;
Enable frame protection on the "Frame Protection" page (Settings > Proactive Protection > Frame Protection) and set the necessary exceptions for the protection action.
Copied
Was the article helpful?
Yes
No
Previous
Overview of the Developer's Area
Next
Overview of Tools

---

