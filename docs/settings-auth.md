---
description: OAuth authentication, app installation/uninstallation, tokens
methods:
- app.573ad8a0346747.09223434
- app.info
- event.bind
- placement.bind
pages: 16
title: OAuth authentication, app installation/uninstallation, tokens
---
# OAuth authentication, app installation/uninstallation, tokens
> OAuth authentication, app installation/uninstallation, tokens
> **16 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Complete OAuth 2.0 Authorization Protocol](#complete-oauth-20-authorization-protocol)
- [Simplified Method for Obtaining OAuth 2.0 Tokens](#simplified-method-for-obtaining-oauth-20-tokens)
- [Automatic Renewal of OAuth 2.0 Tokens](#automatic-renewal-of-oauth-20-tokens)
- [Error Codes](#error-codes)
- [Installation Options for Applications in Bitrix24](#installation-options-for-applications-in-bitrix24)
- [Overview of Installing Local Applications](#overview-of-installing-local-applications)
- [Installation Wizard for Local Application](#installation-wizard-for-local-application)
- [Installation Callback](#installation-callback)
- [Overview of Installing Mass-Market Applications](#overview-of-installing-mass-market-applications)
- [Installation Wizard for Mass-Market Application](#installation-wizard-for-mass-market-application)
- [Installation Callback](#installation-callback)
- [Completing Application Installation](#completing-application-installation)
- [Installation of Industry-Specific CRMs](#installation-of-industry-specific-crms)
- [Installation of Solutions with "Smart Scenarios"](#installation-of-solutions-with-smart-scenarios)
- [Installing Website Templates](#installing-website-templates)
- [Deleting Applications](#deleting-applications)

---

## Complete OAuth 2.0 Authorization Protocol

**Source:** https://apidocs.bitrix24.com/settings/oauth/index

Complete OAuth 2.0 Authorization Protocol | Bitrix24 REST API and Marketplace Applications
Complete OAuth 2.0 Authorization Protocol
Complete OAuth 2.0 Authorization Protocol
How the Protocol Works
General Workflow with OAuth
Full OAuth Authorization in Bitrix24
User Authorization in Bitrix24
Application Authorization
OAuth
is an open authorization protocol that allows a third party to gain limited access to a user's protected resources without needing to share their login and password.
In Bitrix24, the OAuth protocol is used for
local
and
mass-market
applications and is not used in the case of
local webhooks
.
To determine whether you need to implement user authorization using the full protocol in your application, you can refer to the following statements:
I have my own web service (my external application, my separate software, etc.)
The user is already authorized in my service.
I want the user to now authorize in their Bitrix24, and my service to obtain authorization tokens for that Bitrix24 so that my service can work with the REST API of that Bitrix24.
I do not want the user to work with my service "inside" Bitrix24; REST will be used for data exchange, but all scenarios will remain on the side of my service.
If you answered "yes" to all the questions listed, you indeed need to implement the connection using the full OAuth protocol. If your answer is "no" at least once, you should consider the
simplified scenario
for using OAuth.
How the Protocol Works
How the Protocol Works
The protocol is widely used by a vast number of services around the world, as it allows an application to access the API on behalf of a specific user of a specific account.
For the OAuth server, authorization indicates that the user has granted access to the application. The application provides its secret. The account brings everything together and issues the application the appropriate type of access.
The protocol consists of several steps:
The user provides your application with their Bitrix24 address.
The application sends the user to their Bitrix24 to authorize, adding its
client_id
to the request.
In the case of successful authorization in their Bitrix24, the user will be automatically redirected to the application's URL with an additional parameter - the authorization code
code
. Note that this is not yet the authorization token that will be used for working with REST. This is a code needed to obtain the authorization token.
The application, having received the
code
for the specific Bitrix24, directly contacts the authorization server, sending
code
,
client_id
, and
client_secret
.
In response, the authorization server returns the first pair of tokens:
access_token
— the parameter required for working with the REST API
refresh_token
— the token needed later to extend the
access_token
Warning
The lifetime of the authorization code
code
is only 30 seconds, meaning it must be used immediately after receipt.
General Workflow with OAuth
General Workflow with OAuth
A mass-market application or a local one is added and installed in its separate Bitrix24.
Keys are requested from the remote server.
The server redirects the browser to the URL registered by the application.
The response is processed.
All requests to the REST API are signed with the obtained key.
Full OAuth Authorization in Bitrix24
Full OAuth Authorization in Bitrix24
The specific Bitrix24 acts as the data server and holder of user authorization. The authorization server, available at https://oauth.bitrix.info/, serves as the holder of application authorization.
The complete OAuth authorization scenario goes through several steps.
User Authorization in Bitrix24
User Authorization in Bitrix24
The application requests the user’s Bitrix24 address and redirects them to a specially formed URL, for example:
https://portal.bitrix24.com/oauth/authorize/?
client_id=app.573ad8a0346747.09223434
&state=JJHgsdgfkdaslg7lbadsfg
URL parameters:
Required parameters are marked with *
client_id
— the application code obtained:
in the partner area when registering the application and valid for any Bitrix24
in a specific Bitrix24 in the case of a local application (will only be valid for this Bitrix24)
state
— an additional parameter that allows the application to pass arbitrary additional data between authorization steps
At this link, the user will see an authorization form. After authorization (or if there is an authorized session), if the application with the provided
client_id
is installed on the portal, the portal will return the user to the application's
redirect_uri
. If the application is not installed on the portal, the user will see an appropriate error message.
The result of successful user authorization should be the return of the user to the registered application address with additional parameters:
https://www.applicationhost.com/application/?
code=avmocpghblyi01m3h42bljvqtyd19sw1
&state=JJHgsdgfkdaslg7lbadsfg
&domain=portal.bitrix24.com
&member_id=a223c6b3710f85df22e9377d6c4f7553
&scope=crm%2Centity%2Cim%2Ctask
&server_domain=oauth.bitrix.info
Parameters:
code
— the first authorization code, see
below
state
— the value passed in the first request
domain
— the portal domain where authorization is taking place
member_id
— the unique identifier of the portal where authorization is taking place
scope
— a comma-separated list of access permissions to the REST API that the portal grants to the application
server_domain
— the domain of the authorization server
Warning
In the partner area, you can register an application that will not have a "redirect_uri" (authorization data is obtained via redirect_uri). This scenario is possible for mass-market solutions that do not have a permanent address. In this case, it is assumed that the user manually provides the first authorization code to the application. The simplified first authorization code will be displayed to the user directly on the page, and the application should provide the user with a field to enter the code value.
Application Authorization
Application Authorization
Warning
The previous implementation of the protocol assumed that the
client_secret
of the application was given directly to Bitrix24. Due to the expansion of the REST API mechanism to on-premise installations of Bitrix24, such an action becomes unsafe. All operations involving the secret code of the application must be conducted exclusively with the authorization server
oauth.bitrix.info
. For the same reason, this authorization server should be the only trusted source of information about the application's payment status on the portal.
Having obtained the first authorization code
code
in one way or another, the application must proceed to the second step of OAuth authorization and make a hidden request of the following form:
https://oauth.bitrix.info/oauth/token/?
grant_type=authorization_code
&client_id=app.573ad8a0346747.09223434
&client_secret=LJSl0lNB76B5YY6u0YVQ3AW0DrVADcRTwVr4y99PXU1BWQybWK
&code=avmocpghblyi01m3h42bljvqtyd19sw1
Parameters:
Required parameters are marked with *
grant_type
— a parameter indicating the type of authorization data to be validated. It should have the value
authorization_code
client_id
— the application code obtained in the partner area when registering the application or on the portal in the case of a local application
client_secret
— the secret key of the application, obtained in the partner area when registering the application or on the portal in the case of a local application
code
— the value of the code parameter passed to the application at the end of the previous step
Warning
The lifetime of the first authorization code
code
is only 30 seconds, and it must be used immediately after receipt.
In response to such a request, the application will receive a
json
with the following content:
GET /oauth/token/
HTTP/
1.1
200
OK
Content-Type
:
application/json
{
"access_token"
:
"s1morf609228iwyjjpvfv6wsvuja4p8u"
,
"client_endpoint"
:
"https://portal.bitrix24.com/rest/"
,
"domain"
:
"oauth.bitrix.info"
,
"expires_in"
:
3600
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4f9k4jpmg13usmybzuqknt2v9fh0q6rl"
,
"scope"
:
"app"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"T"
}
Significant parameters:
access_token
— the main authorization token required for accessing the REST API
refresh_token
— an additional authorization token used to extend the saved authorization
client_endpoint
— the address of the portal's REST interface
server_endpoint
— the address of the server's REST interface
status
— the status of the application on the portal
At this stage, the application may also receive an authorization error. For example, if the trial or paid period has expired.
{
"error"
:
"PAYMENT_REQUIRED"
,
"error_description"
:
"Payment required"
}
Copied
Was the article helpful?
Yes
No
Previous
Features of REST Calls When Changing the Bitrix24 Address
Next
Simplified Version

---

## Simplified Method for Obtaining OAuth 2.0 Tokens

**Source:** https://apidocs.bitrix24.com/settings/oauth/simple-way

Simplified Method for Obtaining OAuth 2.0 Tokens | Bitrix24 REST API and Marketplace Applications
Simplified Method for Obtaining OAuth 2.0 Tokens
Simplified Method for Obtaining OAuth 2.0 Tokens
The simplest scenario for accessing the REST API is when the application operates within the Bitrix24 interface. In this case, all necessary authorization data is provided to the application upon opening, and there is also the option to use the
js library
for making API calls.
The application receives the following array of POST data:
array
(
'DOMAIN'
=>
'account.bitrix24.com'
,
'PROTOCOL'
=>
'1'
,
'LANG'
=>
'en'
,
'APP_SID'
=>
'dd8cec11e347088fe87c44870a9f1dba'
,
'AUTH_ID'
=>
'ahodg4h37n89vo17gbkgq0x1l825nnb5'
,
'AUTH_EXPIRES'
=>
'3600'
,
'REFRESH_ID'
=>
'2lg086mxijlpvwh0h7r4nl19udm4try5'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'status'
=>
'P'
)
Parameter
Description
DOMAIN
Account domain
PROTOCOL
Access protocol:
0
— http
1
— https
LANG
Current language in which the user is viewing the account
APP_SID
Service parameter for linking the js library with the application environment
AUTH_ID
Main authorization token required for accessing the REST API
AUTH_EXPIRES
Lifetime of the authorization token
REFRESH_ID
Additional authorization token used to extend the saved authorization
member_id
Unique identifier of the account, independent of the domain name
status
Status of the application on the account. The value of this field is purely informational; to obtain a trusted value, use the method
oauth.bitrix.info/rest/app.info
Using the value of the
AUTH_ID
parameter, you can immediately make requests to the API.
As mentioned above, applications in the interface can make API requests on the client side, that is, the user's browser, by connecting the js library and using the methods
BX24.callMethod
and
BX24.callBatch
. In this case, the authorization process will occur automatically.
Thus, a simple scenario for obtaining user authorization tokens upon application installation becomes available. As you know (this was demonstrated in the
relevant example
), public mass-market solutions have the option to specify a separate installation script, which will be shown to the user installing your solution in a frame once — at the time of installation. In this frame, Bitrix24 transmits the same data in the POST request as in the usual case. Therefore, you can design the installation script to save tokens (most importantly, the
refresh_token
as well) on your application's side to later implement the scenario for automatic token renewal.
Application Installation Event
Application Installation Event
Warning
This method is not reliable, as event handlers may trigger with a delay. It is recommended to use it in conjunction with one of the previously described methods if you need authorization tokens immediately after your application is installed without delay.
For applications that do not have a page in the Bitrix24 interface (the
Uses only API
parameter in the application editing form in the partner account or on the account), the following method of authorization is available. In the editing form of the version (or in the editing form of the local application on the account), you can specify the value for the
Callback link for the installation event
parameter. If you specify a link to a handler on the application side in this field, then upon application installation, the handler will receive a POST request with the following data (
application/x-www-form-urlencoded
):
array
(
'event'
=>
'ONAPPINSTALL'
,
'data'
=>
array
(
'VERSION'
=>
'1'
,
'LANGUAGE_ID'
=>
'en'
,
),
'ts'
=>
'1466439714'
,
'auth'
=>
array
(
'access_token'
=>
's6p6eclrvim6da22ft9ch94ekreb52lv'
,
'expires_in'
=>
'3600'
,
'scope'
=>
'entity,im'
,
'domain'
=>
'account.bitrix24.com'
,
'server_endpoint'
=>
'https://oauth.bitrix.info/rest/'
,
'status'
=>
'F'
,
'client_endpoint'
=>
'https://account.bitrix24.com/rest/'
,
'member_id'
=>
'a223c6b3710f85df22e9377d6c4f7553'
,
'refresh_token'
=>
'4s386p3q0tr8dy89xvmt96234v3dljg8'
,
'application_token'
=>
'51856fefc120afa4b628cc82d3935cce'
,
),
)
The request fields contain information about the event (
event
), event data (
data
), and authorization data for accessing the REST API (
auth
) on behalf of the user who installed the application.
Significant parameters:
access_token
— main authorization token required for accessing the REST API
refresh_token
— additional authorization token used to extend the saved authorization
client_endpoint
— address of the account's REST interface
server_endpoint
— address of the server's REST interface
status
— status of the application on the account
For more detailed information on working with events in Bitrix24, you can refer to the
Events
section.
Note
Typically, the authorization data passed to event handlers does not contain data for renewing authorization (
refresh_token
). Some important events, such as the application installation event
ONAPPINSTALL
, are exceptions.
Copied
Was the article helpful?
Yes
No
Previous
Full Protocol
Next
Automatic Token Renewal

---

## Automatic Renewal of OAuth 2.0 Tokens

**Source:** https://apidocs.bitrix24.com/settings/oauth/auto-renewal

Automatic Renewal of OAuth 2.0 Tokens | Bitrix24 REST API and Marketplace Applications
Automatic Renewal of OAuth 2.0 Tokens
Automatic Renewal of OAuth 2.0 Tokens
When to Update Stored Tokens?
Recommended Logic for Working with Tokens
By storing the authorization
refresh_token
value on your side, the application can later use it to access the REST API without user involvement. The lifespan of the
refresh_token
is 180 days.
At any time before the
refresh_token
expires, the application can make the following request:
https://oauth.bitrix.info/oauth/token/?
grant_type=refresh_token
&client_id=app.573ad8a0346747.09223434
&client_secret=LJSl0lNB76B5YY6u0YVQ3AW0DrVADcRTwVr4y99PXU1BWQybWK
&refresh_token=nfhxkzk3gvrg375wl7u7xex9awz6o3k8
Parameters:
Required parameters are marked with *
grant_type
* — parameter indicating the type of authorization data to be validated. Must be set to
refresh_token
;
client_id
* — application code obtained in the partner's account upon application registration, or on the account for local applications;
client_secret
* — secret key of the application, obtained in the partner's account upon application registration or on the account for local applications;
refresh_token
* — value of the stored authorization renewal token.
In response, the application will receive a
json
of the following format:
GET /oauth/token/
HTTP/
1.1
200
OK
Content-Type
:
application/json
{
"access_token"
:
"ydtj8pho532wydb5ixk78ol7uqlb7sch"
,
"client_endpoint"
:
"https://account.bitrix24.com/rest/"
,
"domain"
:
"oauth.bitrix.info"
,
"expires_in"
:
3600
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"3s6lr4kr3cv2od4v853gvrchb875bwxb"
,
"scope"
:
"app"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"T"
}
Significant data in the response:
access_token
— the main authorization token required for accessing the REST API (lifespan — 1 hour)
refresh_token
— new value of the additional authorization token used to extend the stored authorization
client_endpoint
— address of the portal's REST interface
server_endpoint
— address of the server's REST interface
status
— status of the application on the account
At this stage, the application may encounter an authorization error. For example, if the trial or paid period has expired, or if the application has been removed from the account.
{
"error"
:
"PAYMENT_REQUIRED"
,
"error_description"
:
"Payment required"
}
When to Update Stored Tokens?
When to Update Stored Tokens?
If your application's scenario requires constant background data exchange with Bitrix24 without user involvement, you need to consider storing refresh tokens and the mechanism for their use.
As mentioned earlier, the
refresh_token
remains valid for 180 days. This means that if your application does not access Bitrix24 frequently "on its own" to implement application functionality, you only need to contact the authorization server once every 180 days to refresh the stored tokens.
We have encountered cases where application developers "just in case" called the authorization server to refresh the token before every REST request. This is an incorrect scenario that creates unnecessary load. The same applies to scenarios with automatic "token refresh" every hour or every day — this is excessive.
Moreover, by creating unnecessary load on the authorization server, you risk having your application blocked by automation at some point.
Recommended Logic for Working with Tokens
Recommended Logic for Working with Tokens
Store the obtained pairs of
access_token
and
refresh_token
on your side;
Use the stored
access_token
to make requests;
If a specific
access_token
has become invalid, you will receive the corresponding error in response. At this point, you should:
Make a request to the authorization server to obtain a new pair of tokens using the stored
refresh_token
;
Save the new pair of tokens on your side;
Repeat the request to the REST method with the same parameters as before, but with the new
access_token
.
Copied
Was the article helpful?
Yes
No
Previous
Simplified Version
Next
Error Codes

---

## Error Codes

**Source:** https://apidocs.bitrix24.com/settings/oauth/error-codes

Error Codes | Bitrix24 REST API and Marketplace Applications
Error Codes
Error Codes
Code
Description
invalid_request
An incorrectly formatted authorization request was provided
invalid_client
Invalid client data was provided. The application may not be installed in Bitrix24
insufficient_scope
or
invalid_scope
Access permissions requested exceed those specified in the application card
invalid_grant
Invalid authorization tokens were provided when obtaining
access_token
. This occurs during renewal or initial acquisition
Copied
Was the article helpful?
Yes
No
Previous
Automatic Token Renewal
Next
Installation Options

---

## Installation Options for Applications in Bitrix24

**Source:** https://apidocs.bitrix24.com/settings/app-installation/index

Installation Options for Applications in Bitrix24 | Bitrix24 REST API and Marketplace Applications
Installation Options for Applications in Bitrix24
Installation Options for Applications in Bitrix24
When planning user scenarios to be implemented in the application, it's important to understand how the installation process works for a specific Bitrix24 account.
First of all, it's necessary to distinguish between the installation of
local applications
and
mass-market solutions
. Therefore, if you initially plan to develop a mass-market solution, it's advisable to start development with the application added to the Developer's area instead of a "test local" application. Otherwise, after debugging the installation process for a local application, you may find that the installation script needs to be changed for the mass-market solution.
A separate installation scenario is implemented for so-called "configuration" solutions:
industry CRMs
, packages with "
smart scenarios
",
website
templates, BI constructor templates, and other types of solutions that are not REST applications but can be published in the Bitrix24 Marketplace.
Was the article helpful?
Yes
No
Previous
Error Codes
Next
Overview

---

## Overview of Installing Local Applications

**Source:** https://apidocs.bitrix24.com/settings/app-installation/local-apps/index

Overview of Installing Local Applications | Bitrix24 REST API and Marketplace Applications
Overview of Installing Local Applications
Overview of Installing Local Applications
Each local application can only operate on the Bitrix24 where it was added.
In fact, the action of "adding" or "creating" a local application is already equivalent to the installation procedure. For mass-market solutions, these actions differ - first, you need to add the solution in the Developer's area, and only then can it be installed on a specific Bitrix24. For local applications, adding and installing are the same action.
To add a local application, you need to go to the Developer resources section, select the "Other" section, and in the opened slider, choose the scenario "Local application."
There are three options for the installation process that will be triggered when saving a local application:
Adding without an installation scenario;
Adding with an installation wizard;
Adding with a callback installation.
Most often, the first option is chosen for local applications simply because a special installation process in the form of a wizard or callback is more useful for mass-market solutions, which require special onboarding for new users or a one-time interface with pre-configuration of user options, or a callback for saving user tokens at the time of installation on another Bitrix24.
A local application is added and created by the portal administrator only once. Most of the time, developing a setup wizard for your own application is excessive labor. Nevertheless, such scenarios are also possible.
Adding Without an Installation Scenario
Adding Without an Installation Scenario
To ensure that the installation procedure is absent and the application works immediately, it is sufficient to fill in the "Path to your handler" field, specifying the main URL of the application, which will later be used to embed the application's interface into Bitrix24 in the left menu.
Similarly, in the case of a static application, which is an archive with html/js files, you only need to have an index.html file in that archive.
In both cases, after saving the local application, it will already be available to users without any installation procedure.
If your application does not have a user interface, you need to enable the "Uses only API" option. And then, despite the fact that you still do not need an "installation," you will still need REST API tokens for further use. In this case, you cannot do without a
callback handler
, which will receive a call from Bitrix24 immediately after the local application is added.
Was the article helpful?
Yes
No
Previous
Installation Options
Next
Installation Wizard

---

## Installation Wizard for Local Application

**Source:** https://apidocs.bitrix24.com/settings/app-installation/local-apps/installation-master

Installation Wizard for Local Application | Bitrix24 REST API and Marketplace Applications
Installation Wizard for Local Application
Installation Wizard for Local Application
When a local application is added to Bitrix24 for the first time and the user, who is by definition the same Bitrix24 administrator that added the local application, accesses it, Bitrix24 initially displays the URL specified in the "Path for initial installation" field within the application slider.
The user interface implemented at this URL serves as the application's "installation wizard" with any necessary business logic. This could be a configuration form for the application, an informational interface, etc.
Additionally, this URL can be used to initialize and create the required objects in Bitrix24. For example, you can:
set up
event handlers
;
register
widgets
in the necessary embedding locations;
add a
payment system provider
;
register an
SMS messaging provider
;
etc.
In other words, the "installation wizard" URL can be used to perform one-time operations related to adding the application to the account, as after a successful addition, the URL specified in the "Path for initial installation" field will no longer be called.
However, your application must explicitly "notify" Bitrix24 that the installation has been successfully completed. To do this, you need to call the JS method
BX24.installFinish()
. Until this method is called, Bitrix24 considers the application not installed (not configured by the user), and each time the user navigates to the application, it will display the URL specified in the "Path for initial installation" field in the slider.
Features of Installing a Static Local Application
Features of Installing a Static Local Application
Since when uploading a static application, you are uploading an archive of the entire solution rather than specifying paths to your own server, Bitrix24 uses the install.html file from the solution archive as the URL for the "installation wizard." Otherwise, the logic remains the same—you can use JS functions in this file to perform the necessary requests, and to notify about the successful completion of the "wizard," you need to call the method
BX24.installFinish()
.
If install.html is not present in the root of the archive, Bitrix24 assumes that the "installation wizard" procedure is unnecessary and immediately accesses index.html from the same archive.
Was the article helpful?
Yes
No
Previous
Overview
Next
Installation Callback

---

## Installation Callback

**Source:** https://apidocs.bitrix24.com/settings/app-installation/local-apps/installation-callback

Installation Callback | Bitrix24 REST API and Marketplace Applications
Installation Callback
Installation Callback
When a local application is added with the option "Uses only API," it means that it does not have a basic interface in the left menu. Such an application can still register widgets in various embedding locations, but automatically, the item in the left menu will not be added by itself.
This is a useful scenario for applications that do not require a separate user interface, settings, etc., and whose entire business logic is implemented, for example, in the form of automation event handlers.
However, despite the lack of a user interface, such applications still need to obtain authorization tokens. This is where the callback handler comes into play, and the path to it should be specified in the "Path for initial installation" field.
Then, immediately after adding the local application, Bitrix24 will automatically call this URL and send a POST request with OAuth 2.0 authorization data, including the access token and refresh token.
It is expected that the application should store these tokens on its side to update the access token as needed in the future.
In the case of the installation callback handler, the application
must not
call the JS method
BX24.installFinish()
as is required for local applications with the
installation wizard
.
Moreover, even if an attempt is made to do so, it will not work, as this JS method belongs to a library that operates only within the frames of the application's interface in the browser, while the application's callback handler is invoked from the Bitrix24 backend. No browser is involved in this process.
Was the article helpful?
Yes
No
Previous
Installation Wizard
Next
Overview

---

## Overview of Installing Mass-Market Applications

**Source:** https://apidocs.bitrix24.com/settings/app-installation/mass-market-apps/index

Overview of Installing Mass-Market Applications | Bitrix24 REST API and Marketplace Applications
Overview of Installing Mass-Market Applications
Overview of Installing Mass-Market Applications
Published mass-market solutions are installed by users on their Bitrix24 from the Bitrix24 Marketplace.
Additionally, during the development phase, you can install the application from the Developer's area on any Bitrix24 to which you have administrative access.
The typical scenario for creating mass-market solutions involves the developer first "creating" the application in the Developer's area, then writing code and testing it by installing the developed application on an accessible Bitrix24. Only after ensuring its full readiness does the developer submit the solution for moderation. More details on this process can be found in the
relevant section
.
When developing an application, you need to understand what the installation procedure will be and whether it is necessary at all.
In fact, "installing an application" on a specific Bitrix24 is not about uploading a solution or downloading it (except for website templates and other "configuration solutions" that work without REST API), but rather about "registering" the application on the Bitrix24 where the installation is taking place. This registration is solely needed for the authorization server to start issuing OAuth tokens for users of that specific Bitrix24.
Accordingly, depending on the onboarding scenario for users into your application, you should choose the installation scenario.
There are 3 options for the installation process that will be used during the application installation:
Addition without an installation scenario;
Addition with an installation wizard
;
Addition with an installation callback
.
Most often, the second option is chosen for mass-market applications simply because "installing" the application often requires performing some "one-time" procedures, such as registering widget embedding locations, registering event handlers, etc.
Addition Without an Installation Scenario
Addition Without an Installation Scenario
To ensure that the installation procedure is absent and the application works immediately, it is sufficient to fill in the "Application Link" field in the version card, specifying the main URL of the application, which will later be used for embedding the application's interface into Bitrix24's left menu.
Similarly, in the case of a static application, which is an archive with HTML/JS files, you only need to have an index.html file in that archive.
In both cases, after the application is installed, it will already be available to users without any "special" installation procedure.
If your application does not have a user interface, you need to disable the option "Add your page and item to the main menu." Even though you still do not need an "installation" as such, you will still need REST API tokens for further use. In this case, you cannot do without a
callback handler
, which will receive a call from Bitrix24 immediately after the application is installed.
Was the article helpful?
Yes
No
Previous
Installation Callback
Next
Installation Wizard

---

## Installation Wizard for Mass-Market Application

**Source:** https://apidocs.bitrix24.com/settings/app-installation/mass-market-apps/installation-master

Installation Wizard for Mass-Market Application | Bitrix24 REST API and Marketplace Applications
Installation Wizard for Mass-Market Application
Installation Wizard for Mass-Market Application
When an application is installed for the first time on Bitrix24, Bitrix24 opens the application slider and initially displays the URL specified in the "Installation Application Link" field within a frame.
The user interface implemented at this URL serves as the "installation wizard" for the application, complete with any necessary business logic. This could be a configuration form for the application, an informational interface, etc.
Additionally, this URL can be used to initialize and create the required objects in Bitrix24. For example, you can:
set up
event handlers
;
register
widgets
in the necessary embedding locations;
add a
payment system provider
;
register an
SMS messaging provider
;
and so on.
In other words, the "installation wizard" URL can be used to perform one-time operations related to the installation of the application on the account, as after a successful addition, the URL specified in the "Installation Application Link" field will no longer be called. Instead, the user will see the interface from the "Application Link" URL.
However, your application must explicitly "notify" Bitrix24 that the installation has been successfully completed. To do this, you need to call the JS method
BX24.installFinish()
. Until this method is called, Bitrix24 considers that the application is not installed (not configured by the user), and each time the user navigates to the application, it will display the URL specified in the "Installation Application Link" field in the slider.
Features of Installing a Static Application
Features of Installing a Static Application
Since when uploading a static application, you are uploading an archive of the entire solution rather than specifying paths to your own server, Bitrix24 uses the install.html file from the solution archive as the URL for the "installation wizard." Otherwise, the logic remains the same—you can use JS functions in this file to perform the necessary requests, and to notify of the successful completion of the "wizard," you need to call the method
BX24.installFinish()
.
If install.html is not present in the root of the archive, Bitrix24 assumes that the "installation wizard" procedure is unnecessary and immediately refers to index.html from the same archive.
Was the article helpful?
Yes
No
Previous
Overview
Next
Installation Callback

---

## Installation Callback

**Source:** https://apidocs.bitrix24.com/settings/app-installation/mass-market-apps/installation-callback

Installation Callback | Bitrix24 REST API and Marketplace Applications
Installation Callback
Installation Callback
When the option "Add your page and item to the main menu" is not specified in the application card, it means that there is no basic interface in the left menu. Such an application can still register widgets in various embedding locations, but automatically, by itself, an item in the left menu will not be added.
This is a useful scenario for applications that do not require a separate user interface, settings, etc., and whose entire business logic is implemented, for example, in the form of automation rules for event handlers.
However, despite the lack of a user interface, such applications still need to obtain authorization tokens. This is where the callback handler comes in, and the path to it should be specified in the "Event installation handler URL" field.
Then, immediately after adding the local application, Bitrix24 will automatically call this URL and send a POST request with OAuth 2.0 authorization data, including the access token and refresh token.
It is expected that the application should save these tokens on its side to update the access token as needed in the future.
In the case of the installation callback handler, the application
must not
call the JS method
BX24.installFinish()
as is required for local applications with the
installation wizard
.
However, even if you try to do this, it will not work, since this JS method belongs to a library that operates only within the frames of the application's interface in the browser, while the application's callback handler is invoked from the Bitrix24 backend. No browser is involved in this process.
Was the article helpful?
Yes
No
Previous
Installation Wizard
Next
Completing Application Installation

---

## Completing Application Installation

**Source:** https://apidocs.bitrix24.com/settings/app-installation/installation-finish

Completing Application Installation | Bitrix24 REST API and Marketplace Applications
Application without Interface
Completing Application Installation
Application without Interface
Application with Interface
What Doesn't Work Until Installation is Complete
How to Check Installation Status
How and When to Call installFinish
Checklist for Verifying Application Installation
The main distinction in installing applications in Bitrix24 is the presence or absence of a user interface (UI). This determines whether user confirmation is needed for the installation.
Application without Interface
Application without Interface
An application without an interface operates in the background and does not require user actions.
For on-premise applications, enable the "Script only (no user interface) " option.
For mass-market applications, disable the "Add custom page and menu item. Menu item title has to be specified in the application description!" option.
How it works.
The application installation is processed automatically. A POST request with OAuth 2.0 authorization data:
access_token
and
refresh_token
will be sent to the application URL.
For on-premise applications — to the URL from the "Initial installation path  " field.
For mass-market applications — to the "Installation event handler URL."
Developer's role.
Process the incoming callback: verify the data, save the tokens, and prepare the application for operation. The application is immediately considered installed in Bitrix24.
Application with Interface
Application with Interface
The operation of an application with an interface depends on the actions performed by the user.
For on-premise applications, disable the "Script only (no user interface) " option.
For mass-market applications, enable the "Add custom page and menu item. Menu item title has to be specified in the application description!" option.
How the installation works.
Upon first opening, the administrator will see the application setup page.
For on-premise applications — the page from the "Initial installation path" field.
For mass-market applications — the "Application installer URL".
At this stage, the application is considered not installed. Automatic installation is not possible, as user actions are required in the setup wizard for the application to function.
How to complete the installation.
After the user has completed the setup, use the
installFinish
method to finalize the installation. The method is called only from the frontend, from the application setup page.
What Doesn't Work Until Installation is Complete
What Doesn't Work Until Installation is Complete
Until the application sends a signal indicating the completion of installation via
installFinish
, the application will be considered not configured. Functionality will be blocked.
Widgets will not appear in the interface, even if
placement.bind
was successful.
Events will not be sent to the handler, even after a successful
event.bind
.
The application interface will not load:
regular users will see the message
“The application is not fully installed yet. Please contact your Bitrix24 administrator to complete the installation.”
the administrator will see the page from the "Initial installation path" field for on-premise applications or the "Application installer URL" for mass-market applications.
How to Check Installation Status
How to Check Installation Status
Use the
app.info
method to check the installation of the application.
JS
BX24.js
try
{
const
response =
await
$b24.
callMethod
(
'app.info'
, {});
console
.
log
(response.
getData
().
result
.
INSTALLED
);
// true or false
}
catch
(error) {
console
.
error
(error);
}
BX24
.
callMethod
(
"app.info"
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
console
.
error
(result.
error
());
else
console
.
log
(result.
data
().
INSTALLED
);
// true or false
}
);
If the response is:
"INSTALLED": false
— installation is not complete. Call
installFinish
.
"INSTALLED": true
— installation was successful.
How and When to Call installFinish
How and When to Call installFinish
Call the method on the application setup page:
for on-premise applications in the file from the "Initial installation path" field,
for mass-market applications — the "Installation application URL."
Call the method after you have completed the necessary settings: registered widgets, subscribed to events, saved the configuration.
JS
BX24.js
installFinish()
<
script
setup
lang
=
"ts"
>
import
{ onMounted }
from
'vue'
import
{ initializeB24Frame }
from
'@bitrix24/b24jssdk'
const
$b24 =
await
initializeB24Frame
();
onMounted
(
async
() => {
try
{
// 1. Register the widget
await
$b24.
callMethod
(
'placement.bind'
, {
PLACEMENT
:
'CRM_DEAL_DETAIL_TAB'
,
HANDLER
:
'https://example.com/deal-tab'
,
TITLE
:
'Application Data'
});
// 2. Subscribe to the event
await
$b24.
callMethod
(
'event.bind'
, {
event
:
'ONCRMDEALADD'
,
handler
:
'https://example.com/event-handler'
});
// 3. Complete the installation
await
$b24.
installFinish
();
}
catch
(error) {
console
.
error
(
'Installation error:'
, error);
}
});
</
script
>
BX24.installFinish()
BX24
.
init
(
function
(
) {
// 1. Register the widget in the deal card
BX24
.
callMethod
(
'placement.bind'
, {
PLACEMENT
:
'CRM_DEAL_DETAIL_TAB'
,
HANDLER
:
'https://example.com/deal-tab'
,
TITLE
:
'Application Data'
});
// 2. Subscribe to the deal creation event
BX24
.
callMethod
(
'event.bind'
, {
event
:
'ONCRMDEALADD'
,
handler
:
'https://example.com/event-handler'
});
// 3. Complete the installation
BX24
.
installFinish
();
});
Checklist for Verifying Application Installation
Checklist for Verifying Application Installation
Application type and necessity of calling
installFinish
.
Without an interface, only API — calling
installFinish
is not required. Installation completes automatically.
With an interface and setup wizard — calling
installFinish
is mandatory.
Verification of calling
installFinish
.
The method is called after successfully executing other methods in the installation file.
The method is called only once.
Verification of functionality after installation.
Installation status
INSTALLED: true
.
Widgets are displayed in the interface and load the handler interfaces.
Events are received by the handler.
The application interface opens for employees without administrator rights.
Copied
Was the article helpful?
Yes
No
Previous
Installation Callback
Next
Industry CRM Installation

---

## Installation of Industry-Specific CRMs

**Source:** https://apidocs.bitrix24.com/settings/app-installation/vertical-crm-installation

Installation of Industry-Specific CRMs | Bitrix24 REST API and Marketplace Applications
Installation of Industry-Specific CRMs
Installation of Industry-Specific CRMs
An industry-specific CRM is a configuration solution based on CRM settings in the form of a set of deal types, lead stages, custom fields for all CRM entities, settings for Automation rules, workflows, etc., which can be saved as a single archive using the user functionality for exporting industry settings.
This archive can be uploaded in the Developer's area in the application cards and published as an industry solution in the Bitrix24 Marketplace.
The installation of such an application is carried out by Bitrix24 and occurs in several stages:
Automatic downloading of the archive from the Developer's area to the Bitrix24 where the installation takes place;
Unpacking the archive;
Applying the settings from the archive files to the current Bitrix24.
Using REST Applications in the Functionality of Industry-Specific CRMs
Using REST Applications in the Functionality of Industry-Specific CRMs
When configuring the CRM before exporting the settings, the solution developer can install and use applications from the Bitrix24 Marketplace to implement the required functionality.
For example, you can utilize non-standard Automation rules that were added from the Marketplace solution. Alternatively, you can install solutions that format customer phone numbers in the CRM, etc. The convenience lies in the fact that you can focus specifically on the business logic of the CRM itself without delving into the complex development of individual Automation rules or specific integrations. At the same time, by using functionality from other Marketplace solutions, you can offer users of your industry-specific CRMs very flexible and highly functional solutions.
The list of used applications is saved in the industry-specific CRM file during export. Upon import, the applications from this list will be automatically installed on the same Bitrix24 where the industry-specific CRM is being installed.
If among these applications there are solutions available to the client only within the "Bitrix24 Marketplace" subscription, then when publishing your industry-specific CRM, you will also need to place it in the Bitrix24 Marketplace catalog under subscription terms.
Was the article helpful?
Yes
No
Previous
Completing Application Installation
Next
Installing Smart Scenarios

---

## Installation of Solutions with "Smart Scenarios"

**Source:** https://apidocs.bitrix24.com/settings/app-installation/smart-scripts-installation

Installation of Solutions with "Smart Scenarios" | Bitrix24 REST API and Marketplace Applications
Installation of Solutions with "Smart Scenarios"
Installation of Solutions with "Smart Scenarios"
"Smart scenarios" are a configuration solution based on CRM Automation rules, embedded in deals, leads, companies, and contacts outside of the Sales Funnel. "Smart scenarios" can be saved as a single archive using the custom export functionality of industry settings.
This archive can be uploaded in the Developer's area in the application detail form and published as a ready-made solution in the Bitrix24 Marketplace.
The installation of such an application is carried out by Bitrix24 and occurs in several stages:
Automatic downloading of the archive from the Developer's area to the Bitrix24 where the installation takes place;
Unpacking the archive;
Adding "smart scenarios" to the necessary embedding locations from the archive files to the current Bitrix24.
Using REST Applications in the Functionality of "Smart Scenarios"
Using REST Applications in the Functionality of "Smart Scenarios"
When configuring "smart scenarios" before exporting settings, the solution developer can install and use applications from the Bitrix24 Marketplace to implement the required functionality.
For example, you can utilize non-standard Automation rules that were added from the Marketplace solution. The convenience is that you can focus specifically on the business logic of the scenarios themselves without delving into the complex development of individual Automation rules. At the same time, by using Automation rules from Marketplace solutions, you can offer users of your "smart scenarios" very flexible and highly functional solutions.
The list of used applications is saved in the file with "smart scenarios" during export. Upon import, the applications from this list will be automatically installed on the same Bitrix24 where the application with "smart scenarios" is being installed.
If any of these applications include solutions available to the client only within the "Bitrix24 Marketplace" subscription, then when publishing your "smart scenarios," you will also need to place them in the Bitrix24 Marketplace catalog under the subscription terms.
Was the article helpful?
Yes
No
Previous
Industry CRM Installation
Next
Installing Site Templates

---

## Installing Website Templates

**Source:** https://apidocs.bitrix24.com/settings/app-installation/site-templates-installation

Installing Website Templates | Bitrix24 REST API and Marketplace Applications
Using REST Applications in the Functionality of Ready-Made Websites
Installing Website Templates
A "website template" or "ready-made website" is a configuration solution in the form of a single-page or multi-page website, saved as a single archive using the user functionality for exporting the website.
This archive can be uploaded in the Developer's area in the application's detail form and published as a ready-made solution in the Bitrix24 Marketplace.
The installation of such an application is carried out by Bitrix24 and occurs in several stages:
Automatic downloading of the archive from the Developer's area to the Bitrix24 where the installation takes place;
Unpacking the archive;
Registration in the repository of custom layout blocks if non-standard blocks are used;
Creating website pages from the archive.
Using REST Applications in the Functionality of Ready-Made Websites
Using REST Applications in the Functionality of Ready-Made Websites
When creating a website before export, the solution developer can install and use applications from the Bitrix24 Marketplace that add non-standard layout blocks.
The list of applications whose blocks are used in the exported website is saved in a file with the "website template" during export. Upon import, applications from this list will be automatically installed on the same Bitrix24 where the ready-made website is being installed. The convenience is that you can focus specifically on the business logic of your websites without delving into the complex development of unique design solutions in the blocks.
If some of these applications include solutions available to the client only within the "Bitrix24 Marketplace" subscription, then when publishing your ready-made website, you will also need to place it in the Bitrix24 Marketplace catalog under the subscription terms.
Was the article helpful?
Yes
No
Previous
Installing Smart Scenarios
Next
Uninstalling Applications

---

## Deleting Applications

**Source:** https://apidocs.bitrix24.com/settings/app-uninstallation

Deleting Applications | Bitrix24 REST API and Marketplace Applications
Local Applications
Deleting Applications
Local Applications
Mass-Market Applications
Local Applications
Local Applications
The characteristic of local applications is that they are primarily intended for internal automation. In other words, the developer of a local application is often not an external party, but rather an employee or department of the company using its Bitrix24.
Therefore, deleting a local application is usually not an operation that requires automation in the application's code.
However, you have the option to add an event handler
OnAppUninstall
in the local application. If such a handler exists, Bitrix24 will call this handler upon the application's deletion.
When a local application is deleted from Bitrix24, the following are automatically removed:
Event handlers registered by the application
event handlers
;
Handlers registered by the application
widgets
, including custom field types;
Application
storage
created by the application;
Application
settings
created by the application;
Open line
connectors
registered by the application;
Payment
systems
registered by the application;
It is not possible to cancel the deletion of a local application. Adding a local application, even with the same URLs, will effectively create a new application with a new pair of client_id/client_secret for
OAuth authorization
.
Mass-Market Applications
Mass-Market Applications
In contrast to local applications, it is very important for mass-market solutions to be aware of the fact that an application has been deleted from a specific Bitrix24. Especially if the application has implemented mechanisms for updating authorization tokens or business logic that requires periodic access to Bitrix24.
If the application is deleted from a specific Bitrix24, the saved tokens will no longer be valid, and attempts to access such a Bitrix24 will only create unnecessary load on the application's servers.
To receive information about the deletion, the application must add an event handler
OnAppUninstall
. If such a handler exists, Bitrix24 will call this handler upon the application's deletion.
When an application is deleted from Bitrix24, the following are automatically removed:
Event handlers registered by the application
event handlers
;
Handlers registered by the application
widgets
, including custom field types;
Open line
connectors
registered by the application;
Payment
systems
registered by the application;
Before deleting the application, Bitrix24 requests confirmation and offers the option "Delete application settings and data." If this option is not enabled, despite the deletion of the application, the following will remain in Bitrix24:
Application
storage
created by the application;
Application
settings
created by the application;
It is not possible to cancel the deletion of the application. However, it is possible to reinstall the application on the same Bitrix24. In this case, the application will regain access to the undeleted storages and settings.
Was the article helpful?
Yes
No
Previous
Installing Site Templates
Next
Interactive Applications

---

