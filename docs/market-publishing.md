---
description: 'Marketplace: Publishing and preparing applications'
methods: []
pages: 16
title: 'Marketplace: Publishing and preparing applications'
---
# Marketplace: Publishing and preparing applications
> Marketplace: Publishing and preparing applications
> **16 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Overview of Mass-Market Applications](#overview-of-mass-market-applications)
- [Bitrix24 Market Partner Status](#bitrix24-market-partner-status)
- [How to Develop an Application](#how-to-develop-an-application)
- [Bitrix24 Market Sandbox Access Conditions for Solution Development](#bitrix24-market-sandbox-access-conditions-for-solu)
- [How to Add a Solution in the Developer's Area](#how-to-add-a-solution-in-the-developers-area)
- [Procedure for Publishing Solutions in Bitrix24 Market](#procedure-for-publishing-solutions-in-bitrix24-mar)
- [FAQ - Frequently Asked Questions about Publishing Solutions in Bitrix24 Market](#faq---frequently-asked-questions-about-publishing-)
- [Requirements for Formatting and Content of Solutions in Bitrix24 Market](#requirements-for-formatting-and-content-of-solutio)
- [Integrate Your Telephony or Contact Center with Bitrix24](#integrate-your-telephony-or-contact-center-with-bi)
- [Ready-Made Websites in Bitrix24](#ready-made-websites-in-bitrix24)
- [Smart Scripts for Bitrix24](#smart-scripts-for-bitrix24)
- [Create Your Reports for the BI Builder in Bitrix24](#create-your-reports-for-the-bi-builder-in-bitrix24)
- [CRM Solution Presets](#crm-solution-presets)
- [Guidelines for Successful and Quick Moderation](#guidelines-for-successful-and-quick-moderation)
- [Sales terms](#sales-terms)
- [Document Flow for Publication](#document-flow-for-publication)

---

## Overview of Mass-Market Applications

**Source:** https://apidocs.bitrix24.com/market/index

Overview of Mass-Market Applications | Bitrix24 REST API and Marketplace Applications
Overview of Mass-Market Applications
Overview of Mass-Market Applications
The key difference between a mass-market solution and a custom local integration is that a mass-market application can be used across multiple Bitrix24 accounts simultaneously. Therefore, in such an application, it is no longer possible to use simple
incoming or outgoing webhooks
, which we discussed earlier.
For mass-market solutions, it is important to understand how the
OAuth 2.0
authorization protocol works.
To host your solutions in the Bitrix24 Marketplace, you will need to become a
technology partner
of Bitrix24 or already be a participant in the 1C-Bitrix partner program to gain access to the Developer's area.
In the Developer's area, you will be able to publish solutions such as:
data migrators to Bitrix24 from other systems
integrations with telephony services
integrations with payment systems
integrations with SMS providers
as well as business applications to extend the functionality of Bitrix24
Continue Your Learning
Continue Your Learning
Overview of Mass-Market Applications in our video course on REST API
Bitrix24 Market Partner Status
How to Add a Solution in the Developer's Area
Sales terms
Promotion in the Bitrix24 Market
Was the article helpful?
Yes
No
Previous
Adding Your Own Methods
Next
Technological Partnership

---

## Bitrix24 Market Partner Status

**Source:** https://apidocs.bitrix24.com/market/technology-partnership

Bitrix24 Market Partner Status | Bitrix24 REST API and Marketplace Applications
General Information
Bitrix24 Market Partner Status
General Information
Rules for obtaining partner status for publishing products in Bitrix24 Market
Continue Learning
General Information
General Information
Bitrix24 partner status is needed to publish and list products at the
Bitrix24 Market
.
Minimal status – “Partner”. If you are already a member of the Bitrix24 affiliate program, you can immediately proceed to authorization in the partner account.
Currently, the terms of the program for publishing affiliate products at the Bitrix24 Market are governed by additional documents that you will need to sign by filling out
account details
after receiving affiliate status.
Bitrix24 Market modules are managed in the
vendor’s account
.
Rules for obtaining partner status for publishing products in Bitrix24 Market
Rules for obtaining partner status for publishing products in Bitrix24 Market
A.
Register as a developer by filling out the following
form
fields:
First name and Last name
– these fields are needed to create a user account that will be linked to your affiliate account;
E-mail
– the value will be used as a login in partner account (in the future you will be able to connect additional users), as well as for mailing automatic notifications (about the moderation status of your decisions, publications, etc.);
Phone
– necessary for quick communication with you in case your e-mail for some reason is unavailable;
Partner Code
is a character identification code that will be used for further generation of codes for your modules and solutions (for example, Bitrix24Assistant solution published as an affiliate solution with the code bitrix.assistant, where bitrix –
partner code
, assistant – specific module code). After adding at least one module for Bitrix24 Market, this prefix cannot bechanged, so choose it carefully;
Company name, website
– please fill in these fields to tell moderators about yourself who are reviewing your technology partnership application;
Company description
– in this field it is advisable to tell what solutions you plan topublish after receiving the Partner status.
B.
You will receive access to the partner account immediately after filling out the form.
C.
The application is reviewed within 3-4 business days and in some cases may be rejected.
D.
After filling out the form, a
partner account
becomes available to you, within which you will be able to work with the necessary documents, as well as manage your products for Bitrix24 Market.
Continue Learning
Continue Learning
About Technological Partnership in our video course on REST API
How to Develop an Application
Was the article helpful?
Yes
No
Previous
Overview of mass-market applications
Next
How to Develop an Application

---

## How to Develop an Application

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/index

How to Develop an Application | Bitrix24 REST API and Marketplace Applications
How to Develop an Application
How to Develop an Application
Developing an application for publication in Bitrix24 Market consists of several key steps:
Create a record
of the future application in the Developer's area. This step is necessary to obtain the client_id/client_secret for further work with the
OAuth 2.0 protocol
. In fact, at this point, the application itself may not even exist on your side. You do not need to provide application descriptions at this stage, as your solution is clearly not ready for publication yet.
Develop the application code using the current documentation on the required
REST API methods
, specifics of working with authorization tokens, etc. Use your Bitrix24 for testing or request access to a "sandbox" for development and debugging from moderators via the Developer's area chat.
Enter descriptions, images, user agreement data with the end user, and other information about the application in the application card in the Developer's area. Sign the
necessary aggrements
and submit the solution for moderation.
Was the article helpful?
Yes
No
Previous
Technological Partnership
Next
Sandbox Access

---

## Bitrix24 Market Sandbox Access Conditions for Solution Development

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/access-to-sandbox

Bitrix24 Market Sandbox Access Conditions for Solution Development | Bitrix24 REST API and Marketplace Applications
1. Definition and scope
Bitrix24 Market Sandbox Access Conditions for Solution Development
1. Definition and scope
2. Sandbox Access Conditions
Sandbox Access Procedure
1. Definition and scope
1. Definition and scope
Bitrix24 Sandbox
provides a full scope of Bitrix24 features and functionality, including the REST API, offering developers comprehensive toolkit for creating applications listed at the Bitrix24 Market. These applications include, but are not limited to, solutions that facilitate the integration of Bitrix24 with third-party services as well as solutions for testing and updating developed applications and for demonstrating features of already developed software to potential customers.
2. Sandbox Access Conditions
2. Sandbox Access Conditions
App developers can request access to the Bitrix24 sandbox under certain conditions:
Access for a period of 3 months to a single Bitrix24 account (instance) can be provided for development and testing of a first application.
Access for a period of 6 months to a single Bitrix24 account (instance) can be provided for testing of published developer applications, providing technical support and demonstrating developer applications to potential customers. The access period, based on Partner’s request can be extended to the next 6 months if this developer already has published applications listed at Bitrix24 Market catalog.
Access for a period of 6 months to a single account (instance) can be provided for testing, additional development updates, technical support and demonstration to potential customers of each individual CRM solution presets, created by the developer. The access period, based on Partner’s request can be extended to the next 6 months if this CRM solution presets will remain published at Bitrix24 Market catalog.
Access to Bitrix24 sandbox is not provided and not extended for Bitrix24 NFR instances, issued within Bitrix24 Partner program.
The sandbox access is terminated if applications are no longer published at the Market and regular complaints submitted against developers, resulting in a termination of previously signed agreements between the parties.
Sandbox Access Procedure
Sandbox Access Procedure
Requests are submitted using a technical support ticket system or via vendor’s chat and are reviewed and approved by responsible Market and integration managers according to conditions specified above during a period of 1-2 working days.
To gain access to Bitrix24 sandbox you need to specify account’s (instance) address for validating the access and describe your objectives for using the sandbox.
Was the article helpful?
Yes
No
Previous
How to Develop an Application
Next
How to Add an Application

---

## How to Add a Solution in the Developer's Area

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/how-to-add-app

How to Add a Solution in the Developer's Area | Bitrix24 REST API and Marketplace Applications
Adding an Application
How to Add a Solution in the Developer's Area
Adding an Application
Testing Functionality
Signing agreements
Publishing the Solution
Adding an Application
Adding an Application
Select the publication region for the solution and fill in the technical specifications: application type, system sections it interacts with, provide links to the solution, or upload an archive containing it.
You can also specify catalog categories, sales terms, and fill in descriptions.
You may postpone filling out the application card until the submission stage for moderation for publication in Bitrix24 Market.
Testing Functionality
Testing Functionality
In the solution card, click the "Test" button. Here you will find
authorization keys
(
client_id
and
secret_id
) and can specify the address of the Bitrix24 account for testing. A new tab will open with your account displaying the solution card in the Market and a "Install" button.
You must independently test the main user scenarios, including installation, uninstallation, and reinstallation of the solution.
Signing agreements
Signing agreements
Before submitting the finished and tested solution for moderation, you will need to enter into agreements with the Bitrix24 company.
To do this, go to the main page and navigate to the
"Sales Settings"
section, select the publication region, sales terms, and add the legal entity (developer information).
For free placement, it is sufficient to agree to the Marketplace Policy of the general terms of use for the partner catalog of solutions.
In the upper right corner, by clicking the "Instructions" button, you can find explanations for filling out this section and requirements for legal entities.
Publishing the Solution
Publishing the Solution
Check the compliance of your solution with the
publication regulations
and
formatting requirements
. We highly recommend verifying the application against our
checklist
.
If everything is in order, go to your applications list and click the "Submit For Moderation" button. If the button is not available, it means the card is not fully completed.
In case of any errors in filling out the information in the solution card, you will receive automatic explanations when submitting for moderation. If necessary, contact the moderator via chat.
Moderation takes 1-3 business days. In case of discrepancies, the moderator will return the solution for revision with comments, which you can find in the chat in the upper right corner of the account. After making corrections, resubmit the solution for moderation.
Upon successful moderation, you will receive a notification in the chat with the moderator. The solution will immediately become available in the catalog, but indexing for search occurs once a day.
Copied
Was the article helpful?
Yes
No
Previous
Sandbox Access
Next
Publication Process for Solutions in the Marketplace

---

## Procedure for Publishing Solutions in Bitrix24 Market

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/publication-requirements

Procedure for Publishing Solutions in Bitrix24 Market | Bitrix24 REST API and Marketplace Applications
1. General Information
Procedure for Publishing Solutions in Bitrix24 Market
1. General Information
2. Adding a Solution
3. Independent Testing of the Solution
4. Moderation
5. Publication
6. Modifying Published Solutions, Updates
7. Procedure for Providing Technical Support to Users
Continue Learning
1. General Information
1. General Information
A
. Solutions that expand the capabilities of existing Bitrix24 tools are accepted for publication in Bitrix24 Market, such as:
Integrations of Bitrix24 with various external systems (telephony, SMS providers, payment systems, e-mail newsletters, etc.);
Industry-specific solutions based on Bitrix24;
Templates for Sites24;
Smart scenarios;
Additional reporting systems, document management tools, tools for automating specific user scenarios, chatbots for Bitrix24, etc.;
Actions for the standard business process builder, automation rules, and CRM triggers;
Connectors for Open Channels to messengers and social networks;
Reports for the BI constructor.
B
. Published solutions can be free or paid:
Free solutions
can be applications that provide users with full functionality all at once, without time limitations. The available functionality of the application should not change during operation, nor should it be turned on or off based on additional conditions or payments. Such solutions may include:
Solutions for migrating user data from third-party products and platforms to Bitrix24.
Integrations with free or paid external systems;
Others;
Developers of solutions may also offer users to pay for additional functionality, removal of built-in limits, etc.** Payments from clients for additional functionality can be accepted independently. Prices and all conditions related to payment must be clearly and thoroughly stated in the solution description so that users can review them in advance.
C
. The publication of a solution in the Market occurs in stages:
You add the solution yourself;
You fill out the solution card and version of the solution yourself;
You conduct installation testing of the solution on your Bitrix24;
You independently check the functionality;
You submit the solution for review by the moderator by clicking the
"Submit For Moderation"
button in the list of solutions;
The moderator approves the solution/version or sends it back for revision, changing the solution to the appropriate status;
2. Adding a Solution
2. Adding a Solution
A solution can be added in the
Developer's area
.
Familiarize yourself with the technical
documentation on REST API
and the
video course
.
When developing and publishing your solution, adhere to the
“Requirements for the Design and Content of Solutions in Bitrix24 Market”
, which you agree to when submitting for moderation.
3. Independent Testing of the Solution
3. Independent Testing of the Solution
A
. You must ensure that your solution installs successfully in Bitrix24. To do this, you should conduct testing from the card of the published version of the solution by clicking the "Test" button and specifying the necessary Bitrix24 to which you have access:
Conduct installation testing on a "clean" Bitrix24 where your solution has never been installed before;
After verification, delete the solution and ensure that any saved user or authorization data from the current Bitrix24 has been removed from internal databases (if your solution is a server application);
Reinstall the solution on the same Bitrix24 to ensure the installation script works in situations where users will attempt to install your solution multiple times;
B
. You must ensure the functionality of your solution works:
Conduct functionality testing on a "clean" Bitrix24 where your solution has never been installed before;
If the functionality of the solution depends on the rights of a specific user, check user scenarios separately as a Bitrix24 administrator and separately as a regular user;
Delete and reinstall the solution on the same Bitrix24 to ensure its functionality in situations where users will attempt to install your solution multiple times;
Do not test your solution before submission on the same Bitrix24 where it was originally developed.
4. Moderation
4. Moderation
Adding a solution to the developer's list does not mean it automatically enters the moderation queue. You must click the
"Submit For Moderation"
button for the solution you wish to publish.
Moderators return the solution for revision if they find at least one error or non-compliance with the
“Requirements for the Design and Content of Solutions in Bitrix24 Market”
. If the solution does not pass moderation, you will need to resubmit it after correcting the issues. The solution will go to the end of the moderation queue.
The moderator will report any found errors in the chat available in the Developer's area.
Moderation timelines are not regulated and depend on the current workload of the moderators.
A successfully moderated solution may be removed from the catalog due to subsequently discovered issues.
A solution may be denied publication in the Bitrix24 Market catalog without explanation by the moderators.
If the solution implements integration with an external system/service, you must provide test access to the system/service in advance, which will allow testing the integration's functionality. Access is provided in the chat with the moderator after submitting the solution for moderation or in a special "Test Data" field in the solution description (this data will not be published). It is necessary that within the integration setup, the moderator can configure the connection between the system/service and their test Bitrix24 (or several in turn). In other words, if the integration only works with one specific Bitrix24 prepared by the solution developer, this will not be sufficient grounds for passing moderation.
Moderation is not a full testing process for the technical and user quality of your solutions, and moderators are not obligated to provide exhaustive information about the technical conditions under which errors occur. All solutions are tested in the standard cloud Bitrix24 on the highest tariff. In cases where additional software installation is required, the moderator has the right to refuse publication of the solution.
5. Publication
5. Publication
After moderation, you will receive a notification of the review result in the moderator's chat;
After successful moderation of the first version of the new application, the solution will be automatically published in the catalog.
Upon successful moderation of subsequent versions, you can independently manage the state of the
"Available in the catalog"
checkbox in the solution card.
6. Modifying Published Solutions, Updates
6. Modifying Published Solutions, Updates
You can independently change the solution description, installation and setup description, technical support description and contact information, logo, and screenshots;
You can upload updates to the solution by going to the
"Version History"
tab in the solution card and clicking the
"Add New Version"
button.
Changes in descriptions, as well as new versions, must be submitted for moderation to become available to end users.
7. Procedure for Providing Technical Support to Users
7. Procedure for Providing Technical Support to Users
A
. The developer is obliged to make efforts to resolve technical issues related to the interaction of their solutions with Bitrix24, without shifting this task onto end users:
If, as a result of investigating the end user's problem, you believe it is not caused by an error in your code, but rather that the Bitrix24 REST API is not functioning or is not working as it did before, you must contact
1C-Bitrix support
and provide logs of specific HTTP requests (with all used parameters) demonstrating the problem.
Bitrix24 does not consult end users on the scenarios and functionality of your solutions and is not responsible for their functionality.
Bitrix24 is responsible for the functioning of the REST API within the framework described in the relevant documentation.
The resolution of technical issues related to the operation of the REST API should always be handled directly between you and 1C-Bitrix technical support without involving end users.
B
. Bitrix24 reserves the right to remove from publication solutions whose developers do not adhere to the above approach.
Continue Learning
Continue Learning
Requirements for Formatting and Content of Solutions in Bitrix24 Market
Was the article helpful?
Yes
No
Previous
How to Add an Application
Next
FAQ

---

## FAQ - Frequently Asked Questions about Publishing Solutions in Bitrix24 Market

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/faq

FAQ - Frequently Asked Questions about Publishing Solutions in Bitrix24 Market | Bitrix24 REST API and Marketplace Applications
FAQ - Frequently Asked Questions about Publishing Solutions in Bitrix24 Market
FAQ - Frequently Asked Questions about Publishing Solutions in Bitrix24 Market
How applications are published and what options and features are available in the developer’s account.
WHAT IS A PUBLICATION REGION?
Your application will be published for the Global region (which includes Bitrix24 accounts in different domain zones such as .com, .de, and so on). It is mandatory to provide an English description, while descriptions in other languages are optional. Only free apps are available for publication. Monetization is available via in-app purchases only. You need to fill in the app data and and accept the agreement in the price policy section.
WHAT SOLUTIONS CAN BE PUBLISHED IN BITRIX24 MARKET?
In
this document
, you can read information about what decisions are made for publication in the Market, find detailed information about possible options for the pricing policy of your solution, etc.
WHEN ADDING THE APPLICATION, AN ERROR OCCURS SAYING "INCORRECT URL"
We send a head request to the specified URL and expect a response of 200, 301, or 302. If we receive any other response, we write "The specified URL is not accessible." You can check this by visiting
reqbin.com
.
WHERE TO FIND CLIENT_ID AND CLIENT_SECRET FOR THE APPLICATION?
These keys can be found after adding the application to the Vendor’s account, opening the solution details page, and clicking on "Test."
WHY MY ALREADY PUBLISHED SOLUTION HAS THE STATUS “PREPARE FOR PUBLISHING”?
Any changes in the application details form (updated descriptions, price policy and etc.), implemented after successful moderation automatically lead to an updated app status. Users won’t yet see the newly updated information in the Bitrix24 Marketplace - they will still view and install the previous version of the moderated solution. Developer can introduce changes in the app and decide to publish them by submitting these changes to be moderated by Bitrix24.
HOW TO ASK A QUESTION TO A BITRIX24 MODERATOR?
Developer can communicate with Bitrix24 moderator via chat assigned to a specific publication region. Chat icons are available in the slider menu on the right-side menu inside the developer’s account.
WHY I CANNOT MAKE CHANGES IN THE APP’S DETAILS AFTER SUBMITTING THE APP TO MODERATORS?
After you have submitted the changes to be verified by moderators, your app details form becomes accessible for viewing only. It’s possible, that at this moment your app is being checked by Bitrix24 team and any app updates will make this check pointless. In case when you have found some minor issues in your app after submitting it, and you want to quickly solve them, please send a message to the moderator’s chat asking to cancel the moderation. After you have fixed all the issues, you can submit your app to be moderated once again.
HOW QUICKLY MY APP IS GOING TO BE MODERATED?
Usually we review the submitted applications during 2-3 business days. However, everything depends on an ongoing queue, because the number of in-progress moderations can be significant and may take some time.
WHAT'S PERMITTED AND WHAT'S NOT?
Ensure in advance that you are aware about the
details checked by moderator
when inspecting your solutions. The more attention you will invest into studying this document, the faster and easier you will pass the moderation successfully.
CHANGES TO THE APPLICATION CODE
After passing moderation, changing the application code is not possible.
NFR LICENSES
To obtain an NFR license, you must have at least one published solution. If you already have published solutions, then to obtain an NFR license for a specific industry solution, please specify that as well. The NFR license is valid for 6 months and can be renewed upon expiration.
DELETING APPLICATIONS
We delete applications only if they have never been moderated and published. To delete unpublished solutions, you can contact the moderator and send the code of the application to be deleted. Moderated solutions can be removed from the catalog by unchecking the Publish box in the app details.
Was the article helpful?
Yes
No
Previous
Publication Process for Solutions in the Marketplace
Next
General Requirements for Solutions

---

## Requirements for Formatting and Content of Solutions in Bitrix24 Market

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/common-requirements

Requirements for Formatting and Content of Solutions in Bitrix24 Market | Bitrix24 REST API and Marketplace Applications
1. Formatting Requirements
Requirements for Formatting and Content of Solutions in Bitrix24 Market
1. Formatting Requirements
A. Publication Region
B. Solution Card
C. Solution Version Card
D. The solution will not be published in the Bitrix24 Market catalog if
2. Content and Functionality Requirements
Continue Learning
1. Formatting Requirements
1. Formatting Requirements
A. Publication Region
A. Publication Region
When creating a new application, select the region where your solution will be available in the future.
You can also choose an existing solution that was previously published in another region when adding a solution to a specific region, provided that the pricing policy of your solution is available for both publication regions.
B. Solution Card
B. Solution Card
The title must be concise and clear for Bitrix24 users.
The "Category Selection" list must contain a list of sections from the Bitrix24 Market catalog where your solution will be displayed:
No more than 5 categories;
The category
"Miscellaneous"
is used only if you cannot find a suitable category for the main functionality of your solution;
To be included in the
"Integrations - Telephony"
category, the solution must meet
additional requirements
;
To be included in the
"Vertical Solutions - Solution presets"
category, the solution must meet
additional requirements
;
To be included in the
"Automation - Workflows"
category, your solution must create
its activities for Workflows
;
To be included in the
"Automation - Automation Rules"
or
"Automation - Triggers"
category, your solution must create
its automation rules
or
CRM triggers
;
To be included in the
"Automation - Chat bots"
category, your solution must
create chatbots
for the Bitrix24 messenger or Open Channels.
In the
"Automation - Workflow"
,
"Automation - Automation Rules"
, and
"Automation - Triggers"
categories, the publication of separate applications from the same developer is not allowed if each of these applications adds only a minor number of workflow activities, automation rules, and triggers. We recommend consolidating such functionality within a single application in the form of a "collection" of activities and automation rules.
In the Tags section for collections, select up to 5 tags from the list that correspond to the theme of your solution.
These tags are not keywords for search but are intended for user navigation within collections and categories. Therefore, you should choose tags that help group your solution with other solutions that address similar user needs.
If you feel that you lack the right tags, please contact the moderators in the chat.
Application Description Block:
Application Description Block:
In the
Application Description
block, depending on the publication region, descriptions are required in the mandatory language for that region. Descriptions in other available languages are optional.
The
Short Description
of the application should contain 1-2 sentences describing the main purpose of your solution.
It is not recommended to duplicate the application title in the short description. Avoid introductory words; formulate the description so that it complements the title. Remember that the short description will be displayed in application lists and should help you attract the user's interest to open your solution card.
The
Full Description
of the solution should contain a list of tasks that your product solves and the capabilities it provides to Bitrix24 users.
You must indicate in the description the features of the solution that limit or affect its user properties, in particular:
Requirements for a specific Bitrix24 tariff plan;
The need for additional software for the solution to work;
The need to connect/pay for external systems and services, as well as additional functionality of the application (see point 4 below);
Specific requirements for user qualifications for installation and operation with the solution;
Specific requirements for user rights (rights to administer the account, or CRM administration, etc.);
The need to install additional partner solutions;
Functional limitations of the solution related to its technical features (for example, "Supports no more than 1000 deals," "Processes only the last 200 tasks," etc.).
If your solution requires or offers an
optional opportunity to purchase additional functionality of the solution
, payment for external paid services and integrations, etc., then the Description of the solution must explicitly indicate the possibility or necessity of such additional payment, including a clear indication of pricing options.
When mentioning the trade names of the Bitrix24 company, please use the correct names, for the market – Bitrix24 Market.
Use the
Keywords
field to list search words that will help users find your solution in the application catalog.
Requirements for filling:
Keywords must correspond to the actual functionality of the solution; arbitrary sets of words cannot be used;
No more than 2000 characters;
No search spam (including mentioning "Bitrix24" and similar brands related to your integration);
Keywords and phrases must be separated by commas.
The text in the
"Installation Process Description"
field should include a list of actions necessary for using the solution:
If the solution contains settings, indicate where to find them and describe specific options;
If the solution includes integration with an external system/service, specify how the integration is configured within the application and on the external service side; the description should be written for a user who is not familiar with the system/service – links to general user documentation are not sufficient.
The
"Support and Feedback Information"
field must contain all available channels for official communication with clients: e-mail, phone, link to feedback form or helpdesk, social media groups. Be sure to specify the technical support operating schedule – working days and hours, response time to incoming requests. If the solution is published in English, this field should not contain links to Russian-language resources (website, helpdesk, etc.).
Icon
- file in JPEG and PNG format (without a transparent background), square, size no less than 250x250 pixels and no more than 650x650 pixels. Low-quality images with blurriness, noticeable pixelation, and those using third-party trademarks, including trademarks and logos owned by 1C-Bitrix, are not allowed.
Screenshots:
Must contain examples of your solution's interface demonstrating demo data relevant to the solution in the context of Bitrix24.
Demo data must be as realistic as possible and demonstrate to the end user the process of setting up and using the application. Screenshots with empty fields, test users, empty reports, etc., are not accepted.
If the solution has its interface within Bitrix24, the application must be open in the slider on the screenshots. Screenshots highlighting details of the internal interface (e.g., enlarged images of options, etc.) are allowed as a supplement to full-screen screenshots.
The size of screenshots must not exceed 1280 by 720 pixels.
Supported formats are JPEG and PNG.
You must provide a link to your own user license agreement in the
"Use my license agreement"
field, as well as a link to your own privacy policy in the
"Use my privacy policy"
field, drafted in accordance with the current legislation of the publication region. The license agreement defining the rights of the user to use your application must contain the name of the solution and the licensor. For your convenience, we have provided links to examples of such documents nearby.
Important:
the link must lead not to a download but to view the corresponding documents in the browser. Supported document formats: html, pdf, txt.
Optionally, you can provide links for
"Contact the Developer"
and
"Request a Demo."
These should be links to a page about your product with any contact form (messenger, online chat, etc.).
Pricing Policy Block
Pricing Policy Block
"The application will be distributed for free"
- users will be able to install the solution for free and without time limitations.
"Users must pay for the external service"
- an additional option for free solutions when payment for an external service is required for the application to work.
"Contains additional paid functionality"
- an additional option for subscription applications that must be included if your solution offers users additional functionality for an additional payment.
Be sure to familiarize yourself with the
document flow rules
for each type of sales terms you use.
C. Solution Version Card
C. Solution Version Card
In the
"The application will work with system sections"
field, include only those rights that are truly necessary for the functionality of the current version of the solution. It is prohibited to include sections that will only be needed in future versions or updates.
The system section
"Users"
in the basic and full version is granted only if their absence would make the main functionality of the solution impossible; in other cases, only the minimum scope is allowed. You can familiarize yourself with the differences in the
documentation
.
Select the technological type of your solution:
Use REST API
– if your solution works on the Bitrix24 REST API;
Solution preset
– if you are publishing an industry-specific CRM obtained through the built-in CRM settings export mechanism. Please note that there is
additional regulation
for this type of solution;
Add Smart Scripts
– if you are publishing a solution with smart scripts obtained through the built-in settings export mechanism in Bitrix24. Please note that there is
additional regulation
for this type of solution;
Website Templates
– if you are publishing a template for Website Templates. Please note that there is
additional regulation
for this type of solution;
Reports for BI Constructor
– if you are publishing a configured report template. Please note that there is
additional regulation
for this type of solution;
In "Use REST API" mode
Enable the
"Add custom page and menu item"
option only if your solution needs a link to appear in the left menu of Bitrix24 accounts. This option is usually not used for solutions that do not imply a user interface within Bitrix24 accounts, particularly for chatbots.
Enable the
"Embed to BitrixMobile"
option only if your application adds its page and item to the main menu, and the layout of this page is fully responsive.
Enable the
"Add widgets"
option only if your application adds widgets to available embedding locations. More about embedding can be found in the
REST API guide
.
Enable the
"Can be installed by user without administrative rights"
option if the logic of your application does not require administrator privileges for the corresponding REST API calls and will work fully with the tokens of a regular Bitrix24 user.
The
"Application URL"
field must contain the URL of the server-type application, or you must upload an archive with a static HTML/JS application using the corresponding button below.
The
"Application installer URL"
field must contain the URL that will be called when the user installs the solution on their Bitrix24. Details about installation can be found
here
.
What's New in the Application
– must contain a list of differences of the current version from previous ones. If the solution description was made in several languages, then the version changes need to be in all these languages.
For the first version of the application, this field does not need to be filled; the information will be automatically taken from the application description.
D. The solution will not be published in the Bitrix24 Market catalog if
D. The solution will not be published in the Bitrix24 Market catalog if
The solution card contains:
Offensive, obscene information in the card fields: calls to violence, pornography, racism, and other materials prohibited by government legislation;
Information that violates Federal laws in the solution description.
Unfilled fields "Solution Installation," "Solution Description," "Support," icon, and screenshots;
Information that does not correspond to the fields (contacts in the description, solution description in support, discounts in the installation description, etc.), or meaningless information;
Offers to purchase the solution, partner services, and/or Bitrix24 products directly from the partner;
Descriptions of promotions, special offers, and discounts on partner solutions and/or Bitrix24 products when purchased directly from the partner;
Obvious grammatical errors in the description fields;
Texts in descriptions or screenshots that do not correspond to the selected description language.
ii. The version card will contain:
Offensive, obscene information in the version fields: calls to violence, pornography, racism, and other materials prohibited by Russian legislation;
Unfilled "What's New in the Application" field, or text that does not correspond to the selected description language;
Information that does not correspond to the fields (title in the description, discounts in the version description, etc.), or meaningless information;
Offers to purchase the solution, partner services, and/or 1C-Bitrix products directly from the partner;
Descriptions of promotions, special offers, and discounts on partner solutions and/or Bitrix24 products when purchased directly from the partner;
Excessive rights to Bitrix24 modules without obvious connection to the functionality of the solution;
Obvious grammatical errors in the title and description;
2. Content and Functionality Requirements
2. Content and Functionality Requirements
The solution must expand the user functionality of Bitrix24, using the built-in tools of the platform or integrating Bitrix24 with external systems.
Integration implies automatic data exchange between Bitrix24 and an external system. A simple call to the interface of an external system from the Bitrix24 interface within an iframe is not considered integration – such solutions may be published in exceptional cases at the discretion of Bitrix24.
The solution is not allowed to request the user's login and password for authorization in Bitrix24. For explicit authorization, the OAuth 2.0 protocol must be used, the implementation of which is described in the corresponding
section
.
A modern and aesthetically appealing design, close to the Bitrix24 interface, is expected. Applications with a simple HTML-based interface will not be published.
All demo data of the solution must not be real. Real phone numbers, email addresses, links to social networks, etc., are not allowed.
If the solution implements the collection of personal data from clients:
This must not violate the provisions of the law regulations;
For organizing advertising mailings, separate consent from the users of the application must be obtained. Consent is also optional, and refusal cannot be a reason for partial or complete disabling of the application's functionality.
Additional requirements for chatbot functionality:
If the solution implements a chatbot, after inviting the chatbot to the chat, the chatbot must display a short reference about its functionality as a greeting, as well as a list of available commands or provide the user with a clear opportunity to obtain extended information about its commands;
The chatbot must have its own avatar.
The server part of the solution must use a valid SSL certificate, at least a Domain Validation (DV) Certificate.
The solution must work correctly in the on-premise Bitrix24.
The application must not overload the server with excessive requests to the REST API:
Always pre-validate requests on the application side and do not allow requests with inherently incorrect data;
Control and handle errors in API interactions and do not resend incorrectly formed requests;
If possible, cache data on the application side and do not make repeated requests whose results cannot change during the user's session with the application;
If multiple requests need to be made in succession, use the
batch request mechanism
whenever possible.
Solutions making requests to the Bitrix24 REST API from the server must keep logs of API requests and responses for at least the last 3 days.
The solution will not be published in the Bitrix24 Market catalog if:
Upon installation, the solution generates an empty page within the frame or a page with content without automatic redirection to the solution interface after installation is complete;
The security scanner detects issues during the solution check;
Offensive, obscene information is present in the interface or demo data: calls to violence, pornography, racism, and other materials prohibited by government legislation;
The functionality of the solution does not correspond to what is stated in the title and description;
The solution is a clone of other solutions from the same developer in terms of graphic design and/or demo content;
The functionality of the solution reveals:
Texts with incorrect encoding;
PHP Warnings, Fatal Errors, Syntax Errors, and/or Parse Errors, and similar messages from another server platform on which the solution is implemented;
Database errors;
Incorrect layout of the user interface, vertical or horizontal scroll bars (at a resolution of at least 1280 px) in the frame;
JavaScript errors;
Links to non-existent or empty pages;
Links to non-existent images, style files, etc.;
Descriptions of promotions, special offers, and discounts on partner modules and/or Bitrix24 products when purchased directly from the partner;
Obvious grammatical errors in the user interface;
The interface of the solution is made in simple HTML;
Real demo data is used when installing the solution. Links, phone numbers, etc.;
Continue Learning
Continue Learning
How to Develop an Application
Ready-Made Websites in Bitrix24
Smart Scripts for Bitrix24
Create Your Reports for the BI Builder in Bitrix24
Integrate Your Telephony or Contact Center with Bitrix24
CRM Solution Presets
Was the article helpful?
Yes
No
Previous
FAQ
Next
Requirements for Telephony

---

## Integrate Your Telephony or Contact Center with Bitrix24

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/requirements-telephony

Integrate Your Telephony or Contact Center with Bitrix24 | Bitrix24 REST API and Marketplace Applications
Required Scenarios
Integrate Your Telephony or Contact Center with Bitrix24
Required Scenarios
Recommended Scenarios
Application Review by Moderators
Continue Learning
The REST API for telephony makes it easy to incorporate your PBX or contact center into business scenarios for Bitrix24 users.
Required Scenarios
Required Scenarios
To be featured on the
Bitrix24 Market
, your integration must support several mandatory user scenarios:
Incoming/outgoing calls must be registered in Bitrix24 using the
telephony.externalcall.register
method. Bitrix24 will automatically create the necessary objects in the CRM: lead, contact, deal, etc. You do not need to add this data; Bitrix24 will handle it automatically upon call registration.
When registering an incoming call, you need to pass the incoming line number to the
telephony.externalcall.register
method to support Sales Intelligence in Bitrix24.
After a successful call, you need to send the call recording to Bitrix24 using the
telephony.externalCall.attachRecord
method.
You need to support the click2call scenario by adding an outgoing call event handler
OnExternalCallStart
.
You need to support the callback request scenario from Bitrix24 CRM forms by adding an outgoing call event handler
OnExternalCallBackStart
.
Telephony solutions that support all mandatory user scenarios will be highlighted in the Bitrix24 Marketplace catalog with the "Recommended" label.
Recommended Scenarios
Recommended Scenarios
In addition to the mandatory telephony integration scenarios, Bitrix24 users expect additional features from quality solutions:
Call forwarding to the responsible manager. For incoming calls, the integration can find the client in Bitrix24 by phone number using the
telephony.externalCall.searchCrmEntities
method. This method will return information about the found client as well as the employee responsible for the client, allowing you to route the call to that employee.
Managing the display of the standard call card during call forwarding. If, after registering a call in Bitrix24, your PBX's queue processing rules (dial plan) require transferring the voice traffic to another employee, you can show the call card to that employee by calling the
telephony.externalcall.show
method. At the same time, you should hide the call card from other employees by calling the
telephony.externalcall.hide
method.
Application Review by Moderators
Application Review by Moderators
Before publishing your integration, our moderators will review the previously described telephony operation scenarios. Additionally, they will check the compliance of the integration card descriptions:
The descriptions and data in the card must meet the
application publication requirements for Bitrix24 Marketplace
.
The card must contain a pricing grid for the services provided or a link to the pricing page.
The card must include a detailed description of the integration's functionality and setup instructions.
To expedite the review process after submitting the application for moderation, it is recommended to provide the moderator with access to the PBX's account in the chat, along with an associated external number and several internal numbers.
Continue Learning
Continue Learning
Requirements for Formatting and Content of Solutions in Bitrix24 Market
Was the article helpful?
Yes
No
Previous
General Requirements for Solutions
Next
Requirements for Ready-Made Websites

---

## Ready-Made Websites in Bitrix24

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/requirements-sites

Ready-Made Websites in Bitrix24 | Bitrix24 REST API and Marketplace Applications
What is a Website Template
Ready-Made Websites in Bitrix24
What is a Website Template
How to Create and Publish a Template in the Market
Technical Recommendations
Content Recommendations
Continue Learning
What is a Website Template
What is a Website Template
Ready-made website templates in Bitrix24
are a separate type of solution in the Bitrix24 Market that does not require programming and does not use the Bitrix24 REST API. When such a solution is installed, clients receive a website that is fully ready for use.
How to Create and Publish a Template in the Market
How to Create and Publish a Template in the Market
You assemble a template on your account from available or third-party blocks from Market applications, create attractive demo content relevant to the template's theme, click the "Export" button, and your Bitrix24 magically compiles and exports an archive with your ready-made website template, which you just need to upload in the partner's account and publish. Everything is done super quickly, and you don't even need to dive into the code.
1. CHOOSE A THEME
Decide on the theme of the future website template. Choose one that you have enough expertise and experience in implementing.
2. DESIGN THE LOGIC
Determine what content and elements should be on the website to achieve the client's goals. Develop a sales scenario that will guide potential buyers to a successful deal or desired action.
3. FILL WITH CONTENT
Create or prepare content for the website, including text, images, and other materials.
4. TRAIN THE DESIGNER
So that they can easily work with the available tools and create a beautiful and appealing design for the website, considering the chosen theme and logic.
5. GET THE RESULT
After completing the work on the design and content, your template is ready for publication in the Market; it just needs to be exported from the account and uploaded to the Developer's area.
Technical Recommendations
Technical Recommendations
Bitrix24 Product Manager Olga Chepyuk and website team developer Andrey Bochkov have compiled a list of technical recommendations to consider when creating templates:
It is best to assemble templates on the latest version of Bitrix24, which is usually cloud-based;
The smaller the template archive size, the better; for this, it is advisable to compress images to a size of no more than 300kb, which is the optimal image size without quality loss;
Archive: no more than 10mb (exceptions may be made in special cases).
Name the template archive strictly in English without spaces to minimize issues during moderation and uploading the template to the showcase;
Use only "website design," NOT "page design," so that if users want to make slight adjustments to the website, they will be less confused;
A super block for use is encouraged;
Try to create the maximum number of blocks for all screen resolutions, reducing the number of "duplicate blocks" depending on the screen resolution (it is better to have 1 block for desktop, tablet, and phone than 3 blocks for each of these screens).
Content Recommendations
Content Recommendations
We also provide recommendations for working with images and texts, as it is primarily the visuals and content that attract clients to the template.
Choose a name for your template that is as concise as possible and reflects the template's theme.
The template preview and the preview image of the rich link look better without text, and it's a great option if they reflect the template's theme;
Check the texts for typos, and try to align them so they look as appealing as possible;
It is better to use a single font rather than 100 different ones in one template;
Use modern fonts unless you aim to create a vintage or anti-trendy website;
The predominant color for accents in the template should be the one you assigned in the "color palette" within the "website design";
It is better to use photos from the unsplash library or other libraries that use a free-to-use license to avoid issues with copyright holders;
In photographs, it is better to avoid the appearance of third-party brand logos, as well as watermarks and other distracting elements;
It is better to upload photos directly into the template rather than inserting images via direct links, so that if the photo is deleted from the resource, it does not disappear from the template, which is more reliable;
You can use AI to generate images (but the images will only be truly high-quality if you know how to compose prompts);
If you use emojis, check the import on any test account to see if they load correctly.
All materials included in the template must not violate the rights of third parties. That is, you must either be the copyright holder, or the license for the materials used must allow distribution.
Continue Learning
Continue Learning
Requirements for Formatting and Content of Solutions in Bitrix24 Market
Was the article helpful?
Yes
No
Previous
Requirements for Telephony
Next
Requirements for Smart Scenarios

---

## Smart Scripts for Bitrix24

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/requirements-smart-scripts

Smart Scripts for Bitrix24 | Bitrix24 REST API and Marketplace Applications
What are Smart scripts
Smart Scripts for Bitrix24
What are Smart scripts
Advantages of Using Smart scripts in Bitrix24
How to Set Up and Publish Smart scripts in Bitrix24
Description Requirements
Continue Learning
Creating such solutions is straightforward. The result is that the client doesn't waste time on routine tasks – smart scripts work for them!
What are Smart scripts
What are Smart scripts
Smart scripts
are a convenient automation tool that, using CRM Automation rules, allows you to create and configure various interaction scripts with contacts and companies, as well as operations outside the Sales Funnel. And the best part is that no programming is required!
Advantages of Using Smart scripts in Bitrix24
Advantages of Using Smart scripts in Bitrix24
AUTOMATION OF OPERATIONS
Smart scripts enable the automation of routine tasks and operations, freeing up time for more important matters.
IMPROVING CUSTOMER INTERACTION
You can create personalized communication scripts with clients, simply enhancing service quality and increasing the average transaction value.
NO PROGRAMMING REQUIRED
Smart scripts in Bitrix24 allow you to create complex scripts without the need for programming. Just set up the automation logic using the available CRM Automation rules.
How to Set Up and Publish Smart scripts in Bitrix24
How to Set Up and Publish Smart scripts in Bitrix24
Go to the contacts list page and find the "Extensions" button. In the dropdown menu, select "Smart scripts."
Create a new script by specifying its name and a brief description. Go to the "Automation rules" tab and configure the script logic using the available CRM Automation rules.
Go to the script settings and specify the parameters that users can change when launching the script. For example, the message text for the mailing.
Save the script and try to launch it by selecting several contacts and choosing the smart script from the menu. You can edit the message text or continue the script's operation.
The completed smart script can be easily exported and used on any Bitrix24 account. It can be published in Bitrix24 Market as a ready-made solution.
Description Requirements
Description Requirements
The title of each smart script should be brief and concise.
In the Full description of the solution, you must list the smart scripts that your solution offers, describe the results of each, and indicate which entities these smart scripts are designed for (leads, deals, etc.).
Outline use cases if Smart scripts have a general nature (for deals, leads, etc.) rather than a specific one (for industry-specific CRM, for accountants, etc.).
In the installation process description, indicate where to go after installing the application and which parameters to fill in to launch each smart script.
Screenshots of the application should display the menu with added smart scripts, the process of launching a script with an example of filling in the necessary parameters, as well as the results of the smart script's operation.
For solutions with smart scripts, the categories "Automation – Smart Scripts" and "Ready-made Solutions – Smart Scripts" are provided.
Continue Learning
Continue Learning
Requirements for Formatting and Content of Solutions in Bitrix24 Market
Was the article helpful?
Yes
No
Previous
Requirements for Ready-Made Websites
Next
Requirements for BI Constructor Reports

---

## Create Your Reports for the BI Builder in Bitrix24

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/requirements-superset

Create Your Reports for the BI Builder in Bitrix24 | Bitrix24 REST API and Marketplace Applications
What Are Report Templates
Create Your Reports for the BI Builder in Bitrix24
What Are Report Templates
What’s Included in a Report Template
What Are the Requirements for Reports
How to Create and Publish a Report in the Marketplace
Continue Learning
This is a great opportunity not only to monetize your knowledge and experience but also to help other businesses improve their analytics. Your template can become a valuable tool for other entrepreneurs looking to enhance their business performance.
What Are Report Templates
What Are Report Templates
BI Builder
is a new tool in Bitrix24 that helps businesses make informed decisions based on data. Users will be able to aggregate various metrics important to their business sector, perform calculations, visually compare data, and more.
Report template
is a specific type of solution in the Bitrix24 Marketplace that does not require programming and does not use the Bitrix24 REST API. When such a solution is installed, clients receive an analytical dashboard ready to use with their data.
What’s Included in a Report Template
What’s Included in a Report Template
Datasets
These are pre-installed datasets from Bitrix24 available for building reports. Currently, they include information about leads, deals, phone calls, etc. The user documentation describes the complete list of datasets. The BI Builder also allows the creation of custom virtual datasets based on SQL queries to the pre-installed datasets.
Dashboards
These are visual panels where you should display key metrics and charts. Dashboards enable clients to quickly assess the state of their business and identify trends and anomalies.
Metrics
These are aggregating numerical indicators that help measure business performance. For example, this could include revenue, average check, conversion to sale, and other metrics.
Calculable Fields
These are computed values created based on existing data in the BI system. They allow for complex mathematical operations, data aggregation, applying logical conditions, and transforming information to derive new indicators and metrics.
Filters
They allow you to select specific segments of data for analysis. For example, you can filter data by a specific region or time period.
Table Charts
Don’t forget about the option to present data in table format, helping users see details about important business metrics.
What Are the Requirements for Reports
What Are the Requirements for Reports
In addition to the
main regulations with requirements for solution formatting
, there are several specific requirements for publishing report templates:
DATASET NAMES, METRIC CODES, AND CALCULABLE FIELD CODES
. In the names of virtual datasets, in the metric codes, and in the codes of calculable fields, use the partner prefix followed by a dot. For example:
virtual dataset
-
mycode.revenue_dynamic
,
metric
-
mycode.avg_bill
;
NAMES AND DESCRIPTIONS OF METRICS AND FIELDS
. Metrics and calculable fields must have a clear name and description, and the "Approved by" field must be filled with the partner's name (the same as in the application card);
DASHBOARD NAMES
. The name of the dashboard must include a postfix with the partner code in square brackets. Example "Dynamics of Key Sales Indicators [
mycode
]";
ADDING METRICS AND FIELDS
. Metrics and calculable fields should be added not on the chart but in the data source for further use in any charts;
USING FILTERS IN CHARTS
. Filters by date range must be applied in charts to limit the volume of loaded data. The recommended period is the current year.
SETTING A LIMIT IN THE CHART
. In the chart settings, it is necessary to specify a row limit. The recommended value is 1000.
USING SERVER-SIDE PAGINATION
. In the table chart, it is recommended to enable server-side pagination for faster performance.
EXPLICIT FILTER IN THE DASHBOARD
. An explicit date range filter that affects the used charts must also be added to the dashboard.
LIMITING THE RANGE FOR THE FILTER IN THE FORM OF A DROPDOWN LIST
. When forming the dashboard filter as a dropdown list, the filter settings should apply a selection based on a limited date range to restrict the volume of loaded data. The recommended period is the current year.
How to Create and Publish a Report in the Marketplace
How to Create and Publish a Report in the Marketplace
To create such a solution, it is sufficient to set up a dashboard with reports in Bitrix24 using standard user tools while considering the aforementioned requirements, and then export these settings using a special built-in tool in the form of an archive. Next, you need to add the application in the Developer's area and attach the obtained archive in the version card of the added application. Then fill out the solution card and submit it for moderation.
Continue Learning
Continue Learning
Requirements for Formatting and Content of Solutions in Bitrix24 Market
Copied
Was the article helpful?
Yes
No
Previous
Requirements for Smart Scenarios
Next
Requirements for Industry-Specific CRMs

---

## CRM Solution Presets

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/requirements-vertical-crm

CRM Solution Presets | Bitrix24 REST API and Marketplace Applications
What is Considered a CRM preset
CRM Solution Presets
What is Considered a CRM preset
How to Think Productively When Creating CRM Presets
What CRM Settings Can Be Used in a CRM preset
Requirements for Publishing CRM Presets
What the Moderator Will Pay Attention To
Continue Your Study
What requirements are placed on CRM presets, how publication occurs, and what to pay attention to during development.
What is Considered a CRM preset
What is Considered a CRM preset
This is a special type of solution in the Bitrix24 Market catalog, which represents a pre-configured CRM for a specific type of business: configured deal directions, a tailored lead funnel, customized CRM cards, specific business automation using CRM automation rules and workflows, etc.
To create such a solution, it is sufficient to configure the CRM in Bitrix24 using standard user tools and then export these settings using a special built-in tool in the form of an archive. Next, you need to add the application in the Developer's area and attach the obtained archive in the version card of the added application.
How to Think Productively When Creating CRM Presets
How to Think Productively When Creating CRM Presets
Discover what is important for clients, how to approach the design of an industry CRM correctly, and how to stand out in the Bitrix24 Market showcase.
What CRM Settings Can Be Used in a CRM preset
What CRM Settings Can Be Used in a CRM preset
CRM directories;
Stages of the lead funnel;
Deal directions and stages of directions;
Custom fields for leads, contacts, companies, and deals (except for fields with the type "link to information block");
CRM cards for leads, contacts, companies, and deals. For deals, cards linked to specific directions are saved;
Settings for automation rules and triggers in CRM;
Workflows related to CRM;
Installed REST applications (published in Bitrix24 Market);
Requirements for Publishing CRM Presets
Requirements for Publishing CRM Presets
The target audience for a CRM presets consists of new Bitrix24 users who are not deeply familiar with the product's configuration features. A ready-made, pre-configured CRM will help them start working effectively with Bitrix24. Therefore, the main requirements for CRM presets relate to descriptions and reference information. These descriptions will help potential clients understand whether your CRM preset will be useful to them, so they must be as clear and detailed as possible.
Thus, to successfully pass moderation, your CRM preset (in addition to
meeting standard requirements for solutions
) must have:
A brief description indicating the business sector for which the CRM preset is made and mentioning 1-2 of the most important distinguishing scenarios (for example, "Repeat sales and automatic control over salespeople's work");
A full description detailing the business sector, distinctive industry scenarios, what specific tasks your CRM preset solves and how (what deal directions are added and why, what fields are present, what scenarios are automated, etc.); what functionality is available at specific Bitrix24 tariff plans;
A screenshot of lead stages (if you are using leads) with clear names that directly relate to the type of business for which you created the industry CRM;
Screenshots of configured automation rules and workflows in CRM;
A screenshot of the slider with the sales funnel (if you are using more than one deal direction);
Screenshots of deal stages in each direction with clear names that directly relate to the type of business for which you created the CRM preset;
Screenshots of the types of CRM cards with standard and custom fields (for each deal direction, if they differ);
Screenshots of tasks assigned to employees in the timeline of the CRM card (if your solution automatically generates tasks for employees) with clear titles related to the type of business for which you created the CRM preset;
A list of third-party applications used in the CRM preset;
A list of available functionality of the CRM preset depending on the Bitrix24 tariff plan.
Additionally, it is recommended to:
Create a training video explaining how to properly use the configured scenarios of the CRM preset. This will help users understand whether to install your solution and will also reduce the load on your technical support. It is advisable to provide a link to the video directly in the description of the CRM preset;
Prepare a textual instruction and FAQ for your solution in advance, and provide a link to these materials in the "Full description" and "Support and feedback information" fields.
What the Moderator Will Pay Attention To
What the Moderator Will Pay Attention To
The moderator does not test the quality of your solutions or check the functionality of workflows and CRM automation rules, but we receive user complaints, and if the non-functionality of the stated scenarios is confirmed, we may remove problematic solutions from publication.
In the usual course, the following will be checked:
Compliance with
publication requirements
;
Quality of screenshots (text on them must be easily readable; optimization that clearly degrades image quality is unacceptable);
Correctness of descriptions, presence of typos;
Compliance of basic CRM settings with descriptions (deal directions and stages, lead funnel stages, CRM card fields, etc.)
Continue Your Study
Continue Your Study
Requirements for Formatting and Content of Solutions in Bitrix24 Market
Was the article helpful?
Yes
No
Previous
Requirements for BI Constructor Reports
Next
Checklist Before Moderation

---

## Guidelines for Successful and Quick Moderation

**Source:** https://apidocs.bitrix24.com/market/preparing-to-publish/checklist

Guidelines for Successful and Quick Moderation | Bitrix24 REST API and Marketplace Applications
Guidelines for Successful and Quick Moderation
Guidelines for Successful and Quick Moderation
We offer you a minimal checklist for self-verification before submitting solutions for moderation:
Come up with an appropriate app name
. "Test App #1" will not pass moderation.
Provide a clear and understandable description
of what your app does, how to set it up, and how to contact your tech support. Naturally, this should comply with all spelling and punctuation norms.
Check the videos and images in the description
to ensure they open correctly, with no broken images or videos hidden by privacy settings.
Create a good icon
- square, up to 650*650 px with a high-quality image, free of pixelation, blurriness, etc.
Attach informative screenshots
. There must be high-quality full-screen screenshots of your solution's interface in the context of Bitrix24.
Provide links to your license agreement and personal data processing policy for your software
. The license agreement must genuinely refer to your application. The name must exactly match what you specified in point 1. Pay close attention to this if you are using one template for multiple solutions or if you plan to change the app's name.
Select only the necessary scopes
. Remember, scopes are not issued "for future use"!
Indicate the widget embedding locations of your application
. Don’t hesitate to specify in the description, or better yet, in the chat with the moderator, the embedding locations of the application if you are using the scope "Application Embedding". Ideally, directly in the version card of the application, select the widget embedding locations that are actually used by your solution.
Meet the requirements for integrations with external services:
In the description, provide a link to the website of the integrated service;
Be sure to include a link to the service's pricing in the description and check the box "User needs to pay for the external service" in the pricing policy of the solution;
Send the account details of the service from which your integration can be verified. This can be done either in the solution card in the "Test Data" field or in the chat with the moderator.
Thoroughly test the functionality of your solution
. If something doesn’t work, we will return the solution for revision, and the moderation process will be delayed.
Continue Your Study
Continue Your Study
Requirements for Formatting and Content of Solutions in Bitrix24 Market
Was the article helpful?
Yes
No
Previous
Requirements for Industry-Specific CRMs
Next
Sales terms

---

## Sales terms

**Source:** https://apidocs.bitrix24.com/market/sales-terms

Sales terms | Bitrix24 REST API and Marketplace Applications
Free Solutions with In-App Purchases
Sales terms
At the moment, Bitrix24 Market supports two types of application placements: free solutions and free solutions with in-app purchases.
Free Solutions with In-App Purchases
Free Solutions with In-App Purchases
Completely free solutions do not require payment during the installation and use of the solution. However, developers of solutions have the option to independently charge for certain functionalities of their solutions.
This means that you can monetize your applications in several ways:
Offer users a free limited trial of your solution, after which users will need to make a payment to continue using your application.
Provide users with a free basic version of your solution and offer extended paid features.
Offer users free limited functionality of your solution and provide paid increased limits, quotas, etc.
In the case of accepting payments, it is necessary to specify the option "Users have to pay for external service" in the application card.
You can independently accept payments from clients for additional functionality of your application. Currently, Bitrix24 does not charge a fee for such payments.
Was the article helpful?
Yes
No
Previous
Checklist Before Moderation
Next
Agreements

---

## Document Flow for Publication

**Source:** https://apidocs.bitrix24.com/market/agreements

Document Flow for Publication | Bitrix24 REST API and Marketplace Applications
How to Sign Documents
Document Flow for Publication
How to Sign Documents
Types of sales terms
Types of Agreements
Creating a legal entity
To publish solutions, agreements must be signed with the Bitrix24 company. Depending on whether the solution will be free for the end user, paid under a subscription model, or sold separately, different agreements will need to be signed.
How to Sign Documents
How to Sign Documents
A brief mini-guide on the process of signing the necessary agreements for publication.
1. GO TO SALES SETTINGS
In the
"Sales Settings"
section, you need to select the publication region.
2. CHOOSE THE SALES TERMS
Depending on the type of sales terms available for the choosen region, different agreements will need to be signed; the types of sales terms are described in more detail below.
3. ADD A LEGAL ENTITY
You need to fill in the details of the legal entity with whom we will sign the necessary agreements. Below, we have outlined the requirements for legal entities.
4. REVIEW THE AGREEMENTS
After creating the legal entity, the necessary agreements will be generated for you, and you can review their terms.
Types of sales terms
Types of sales terms
Choose one or several types of sales terms for solutions:
FREE
You will be able to publish solutions in the
Bitrix24 Market
, which will be available to end users at no cost at the time of installation. Available for all publication regions.
Types of Agreements
Types of Agreements
Each type of sales terms corresponds to its own agreement for signing.
Marketplace Policy
For free solutions and free solutions with the built-in purchases, it is sufficient to read the Marketplace Policy and agree to the terms. Available for all publication regions and types of legal entities.
Creating a legal entity
Creating a legal entity
It is important to correctly choose the organizational form of the legal entity, knowing which types of publication you will be using. There can only be one active legal entity on behalf of which you will sign all necessary agreements.
Was the article helpful?
Yes
No
Previous
Sales terms
Next
Marketing Tools

---

