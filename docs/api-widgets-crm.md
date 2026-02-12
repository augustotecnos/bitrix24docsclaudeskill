---
description: 'Widgets: CRM-specific placement types and embedding'
methods:
- crm.activity.get
- crm.company.get
- crm.contact.get
- crm.deal.get
- crm.item.get
- crm.lead.get
- crm.quote.get
- placement.bind
- placement.call
pages: 12
title: 'Widgets: CRM-specific placement types and embedding'
---
# Widgets: CRM-specific placement types and embedding
> Widgets: CRM-specific placement types and embedding
> **12 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Context Menu Item in the CRM_XXX_LIST_MENU, CRM_DYNAMIC_XXX_LIST_MENU](#context-menu-item-in-the-crmxxxlistmenu-crmdynamic)
- [Dropdown Menu Item Above the CRM Entity List CRM_XXX_LIST_TOOLBAR, CRM_DYNAMIC_XXX_LIST_TOOLBAR](#dropdown-menu-item-above-the-crm-entity-list-crmxx)
- [Tab in the detail form of the CRM entity CRM_XXX_DETAIL_TAB, CRM_DYNAMIC_XXX_DETAIL_TAB](#tab-in-the-detail-form-of-the-crm-entity-crmxxxdet)
- [Button above the timeline of the CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY card](#button-above-the-timeline-of-the-crmxxxdetailactiv)
- [Additional Integration Features CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY](#additional-integration-features-crmxxxdetailactivi)
- [Dropdown Menu Item of the Top Button in the CRM_XXX_DETAIL_TOOLBAR, CRM_DYNAMIC_XXX_DETAIL_TOOLBAR](#dropdown-menu-item-of-the-top-button-in-the-crmxxx)
- [Context Menu Item for the Deal in the CRM Element Card CRM_XXX_ACTIVITY_TIMELINE_MENU, CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU](#context-menu-item-for-the-deal-in-the-crm-element-)
- [Dropdown Menu Item for the Document Generator CRM_XXX_DOCUMENTGENERATOR_BUTTON](#dropdown-menu-item-for-the-document-generator-crmx)
- [Dropdown Menu Item of the Top Button in the CRM Robot Designer CRM_XXX_ROBOT_DESIGNER_TOOLBAR](#dropdown-menu-item-of-the-top-button-in-the-crm-ro)
- [Menu Item in CRM Sales Funnels Toolbar](#menu-item-in-crm-sales-funnels-toolbar)
- [CRM Analytics Menu Item CRM_ANALYTICS_MENU](#crm-analytics-menu-item-crmanalyticsmenu)
- [Dropdown Menu Item of the Top Button in CRM Analytics CRM_ANALYTICS_TOOLBAR](#dropdown-menu-item-of-the-top-button-in-crm-analyt)

---

## Context Menu Item in the CRM_XXX_LIST_MENU, CRM_DYNAMIC_XXX_LIST_MENU

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/index

Context Menu Item in the CRM_XXX_LIST_MENU, CRM_DYNAMIC_XXX_LIST_MENU | Bitrix24 REST API and Marketplace Applications
Context Menu Item in the CRM_XXX_LIST_MENU, CRM_DYNAMIC_XXX_LIST_MENU
Context Menu Item in the CRM_XXX_LIST_MENU, CRM_DYNAMIC_XXX_LIST_MENU
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Exploring
Scope:
crm
You can add your item to the context menu of CRM objects:
leads
,
contacts
,
companies
,
deals
,
old invoices
,
estimates
,
new invoices
,
custom entity types
.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
CRM_LEAD_LIST_MENU
Context menu item for
lead
CRM_CONTACT_LIST_MENU
Context menu item for
contact
CRM_COMPANY_LIST_MENU
Context menu item for
company
CRM_DEAL_LIST_MENU
Context menu item for
deal
CRM_INVOICE_LIST_MENU
Context menu item for
old invoice
CRM_SMART_INVOICE_LIST_MENU
Context menu item for
new invoice
CRM_QUOTE_LIST_MENU
Context menu item for
estimate
CRM_ACTIVITY_LIST_MENU
Context menu item for
activity
CRM_DYNAMIC_XXX_LIST_MENU
Context menu item for custom CRM entity type. Instead of XXX, specify the numeric identifier of the specific
custom entity type
. For example,
CRM_DYNAMIC_183_LIST_MENU
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
CRM_LEAD_LIST_MENU
CRM_DEAL_LIST_MENU
CRM_CONTACT_LIST_MENU
CRM_COMPANY_LIST_MENU
CRM_QUOTE_LIST_MENU
CRM_INVOICE_LIST_MENU
CRM_SMART_INVOICE_LIST_MENU
CRM_ACTIVITY_LIST_MENU
CRM_DYNAMIC_XXX_LIST_MENU
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
37430843
b6a2ce62aea9be09c34d9e6d
[AUTH_ID] =>
39e69
f6600631fcd00005a4b00000001f0f10738741fe7296291110a2e9788a33216cf
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
2965
c76600631fcd00005a4b00000001f0f107cdf3226bebc47f89d1b0f15608e44b14
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_LEAD_LIST_MENU
[PLACEMENT_OPTIONS] => {
"ID"
:
"6591"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => a50589d05446337105e25d637db82f43
[AUTH_ID] =>
69e69
f6600631fcd00005a4b00000001f0f107b9e6d35725003c1524f001562c374275
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
5965
c76600631fcd00005a4b00000001f0f107fb7f5a0542d97a9f3a31c73bbfde48e2
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DEAL_LIST_MENU
[PLACEMENT_OPTIONS] => {
"ID"
:
"3473"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => fcd06d800f545d3b6937cdf58cf17ac2
[AUTH_ID] =>
68e99
f6600631fcd00005a4b00000001f0f107343b8243b5a1ad4f168fc8a8d05c182f
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
5868
c76600631fcd00005a4b00000001f0f107b05367c5e576376b33d68414e1b04f18
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_CONTACT_LIST_MENU
[PLACEMENT_OPTIONS] => {
"ID"
:
"13037"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => b61394bd23467de46689899d065e8a0f
[AUTH_ID] =>
9
ce99f6600631fcd00005a4b00000001f0f1073d433234d6fbee7d770aac0b3ba5e23f
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
8
c68c76600631fcd00005a4b00000001f0f107704816219d9d7a765a4038ae79f9a3db
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_COMPANY_LIST_MENU
[PLACEMENT_OPTIONS] => {
"ID"
:
"2946"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => c1228e789d5052287ceb321fe7b3377a
[AUTH_ID] => d3e99f6600631fcd00005a4b00000001f0f1079f90c8cd4e3f2726ab8ea7a40888c844
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => c368c76600631fcd00005a4b00000001f0f107d077746104d8e477278da715f3ea28cf
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_QUOTE_LIST_MENU
[PLACEMENT_OPTIONS] => {
"ID"
:
"5"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => a2734d8a3ee69cc513b26555bc43f44c
[AUTH_ID] => fce99f6600631fcd00005a4b00000001f0f10757595d9831ca4f9591c8b5190a12d385
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => ec68c76600631fcd00005a4b00000001f0f107e37ac66ed69aaa16cbc75c7a650e61ef
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_INVOICE_LIST_MENU
[PLACEMENT_OPTIONS] => {
"ID"
:
"12"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => adada92053b22a4de3895402a01693cf
[AUTH_ID] =>
69
c7ca670076a4b8006f518000000001201c0720c9c9d78077b5f2c5530f64b061c8a1
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
5946
f2670076a4b8006f518000000001201c07709da4b12d3c7e82e120a20e547b638f
[member_id] => e8857f161a1a8288f312b6cc6ad67995
[status] => L
[PLACEMENT] => CRM_SMART_INVOICE_LIST_MENU
[PLACEMENT_OPTIONS] => {
"ID"
:
"32"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => a29cf633b74509437b3873a57d138f10
[AUTH_ID] =>
30
ea9f6600631fcd00005a4b00000001f0f107450fd57122ecc7d9e58f894b3fb2c57f
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
2069
c76600631fcd00005a4b00000001f0f107bd1492748f20b4a006e2a35f9f7c0b6d
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_ACTIVITY_LIST_MENU
[PLACEMENT_OPTIONS] => {
"ID"
:
"1465"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => ef961a45216cf6944d118ebd2a44c119
[AUTH_ID] =>
5
cea9f6600631fcd00005a4b00000001f0f107d2ceb3f7eaaaa5cee8960f2572ab96e4
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
4
c69c76600631fcd00005a4b00000001f0f107e7da55ee918fcdeef4bfa02243184591
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DYNAMIC_183_LIST_MENU
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
The value of
PLACEMENT_OPTIONS
is a JSON string containing an array of one or more keys.
Required parameters are marked with *
Parameter
Description
ID
*
string
Identifier of the CRM object for which the widget was opened.
Can be used to retrieve additional information using the corresponding methods:
any object type
crm.item.get
specifying entityTypeId = '1' for leads, '2' for deals, and
etc.
lead
crm.lead.get
deal
crm.deal.get
contact
crm.contact.get
company
crm.company.get
estimate
crm.quote.get
activity
crm.activity.get
In the case of embedding the widget in a custom type object, the type identifier can be obtained from the value of the
PLACEMENT
parameter. In the example above —
183
Continue Exploring
Continue Exploring
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Widgets in the main menu
Next
Dropdown menu item above the list of entities

---

## Dropdown Menu Item Above the CRM Entity List CRM_XXX_LIST_TOOLBAR, CRM_DYNAMIC_XXX_LIST_TOOLBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/list-toolbar

Dropdown Menu Item Above the CRM Entity List CRM_XXX_LIST_TOOLBAR, CRM_DYNAMIC_XXX_LIST_TOOLBAR | Bitrix24 REST API and Marketplace Applications
Dropdown Menu Item Above the CRM Entity List CRM_XXX_LIST_TOOLBAR, CRM_DYNAMIC_XXX_LIST_TOOLBAR
Dropdown Menu Item Above the CRM Entity List CRM_XXX_LIST_TOOLBAR, CRM_DYNAMIC_XXX_LIST_TOOLBAR
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Learning
Scope:
crm
You can add your dropdown menu item above the list of CRM entity objects:
leads
,
contacts
,
companies
,
deals
,
old invoices
,
estimates
,
new invoices
,
custom entity types
.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
CRM_LEAD_LIST_TOOLBAR
Dropdown menu item above the list of
leads
CRM_CONTACT_LIST_TOOLBAR
Dropdown menu item above the list of
contacts
CRM_COMPANY_LIST_TOOLBAR
Dropdown menu item above the list of
companies
CRM_DEAL_LIST_TOOLBAR
Dropdown menu item above the list of
deals
CRM_INVOICE_LIST_TOOLBAR
Dropdown menu item above the list of
old invoices
CRM_SMART_INVOICE_LIST_TOOLBAR
Dropdown menu item above the list of
new invoices
CRM_QUOTE_LIST_TOOLBAR
Dropdown menu item above the list of
estimates
CRM_DYNAMIC_XXX_LIST_TOOLBAR
Dropdown menu item above the list of custom CRM entity type items. Instead of XXX, you need to specify the numeric identifier of the specific
custom entity type
. For example,
CRM_DYNAMIC_183_LIST_TOOLBAR
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
CRM_LEAD_LIST_TOOLBAR
CRM_DEAL_LIST_TOOLBAR
CRM_CONTACT_LIST_TOOLBAR
CRM_COMPANY_LIST_TOOLBAR
CRM_INVOICE_LIST_TOOLBAR
CRM_SMART_INVOICE_LIST_TOOLBAR
CRM_QUOTE_LIST_TOOLBAR
CRM_DYNAMIC_XXX_LIST_TOOLBAR
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => com
[APP_SID] =>
17621e81
b6c5e43e706be4f943719513
[AUTH_ID] => b2f19f6600631fcd00005a4b00000001f0f1071894b660abb19a2fa0362714239a2aaa
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => a270c76600631fcd00005a4b00000001f0f107a47747d2035445dbcaa0886ec97678df
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_LEAD_LIST_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => com
[APP_SID] =>
55
fb79c4a1bb3645c8bf3b5f0cfca12f
[AUTH_ID] =>
31
f29f6600631fcd00005a4b00000001f0f10781afcd4e67da98de2c0c3ba491e6d6f5
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
2171
c76600631fcd00005a4b00000001f0f10731ca47c52d032bf3568e3f94c3d9750a
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DEAL_LIST_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => com
[APP_SID] =>
3
aec6e81c200862ebe7ed02c5a0551d9
[AUTH_ID] =>
4
af29f6600631fcd00005a4b00000001f0f107657b02e0d0eaaaabbe09ea6c8628110d
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
3
a71c76600631fcd00005a4b00000001f0f107ec7126f6c7499958546207d42d820184
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_CONTACT_LIST_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => com
[APP_SID] =>
179765226
ec81db398cc98e4a5e9015e
[AUTH_ID] =>
5
ff29f6600631fcd00005a4b00000001f0f10706443c53e3994101a662e9b245ee398e
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
4
f71c76600631fcd00005a4b00000001f0f10787f7352bf08be012b32c362e6c808f72
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_COMPANY_LIST_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => com
[APP_SID] =>
611
bd605715c4de60c7efe1fc82ce0be
[AUTH_ID] =>
79
f29f6600631fcd00005a4b00000001f0f107e0bf261552367a5d567964f8862976b1
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
6971
c76600631fcd00005a4b00000001f0f107f5b4499d2f41d14ec3142fb9b189b409
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_INVOICE_LIST_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
1
dc4a02fd9c7c094bb78cac8689d23cb
[AUTH_ID] =>
6986
d4ca670076a4b8006f518000000001201c07456529898882f844c5d744f564bcfafb
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
7653
f2670076a4b8006f518000000001201c0710663db8587fccc71874c46996bf6f49
[member_id] => e8857f161a1a8288f312b6cc6ad67995
[status] => L
[PLACEMENT] => CRM_SMART_INVOICE_LIST_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => com
[APP_SID] =>
5389
d2aee1d75061a59be00996972f78
[AUTH_ID] =>
8
ef29f6600631fcd00005a4b00000001f0f107f56f228b134e9f88dd8088ce08d9de0e
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
7e71
c76600631fcd00005a4b00000001f0f107515f3cc004a6876f039fab870a2cbdc2
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_QUOTE_LIST_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => com
[APP_SID] =>
30
b1cd2ce933551b37c441f8bafc5545
[AUTH_ID] => a9f29f6600631fcd00005a4b00000001f0f107f69952670946852790cb3ec5bd1ab2e9
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
9971
c76600631fcd00005a4b00000001f0f1075c07a22a5dc9d29f124040e460ac04b9
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DYNAMIC_183_LIST_TOOLBAR
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
In the current widget, the
PLACEMENT_OPTIONS
parameter is not passed.
Continue Learning
Continue Learning
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Context menu item in the list of entities
Next
Tab in the detail form of the entity

---

## Tab in the detail form of the CRM entity CRM_XXX_DETAIL_TAB, CRM_DYNAMIC_XXX_DETAIL_TAB

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/detail-tab

Tab in the detail form of the CRM entity CRM_XXX_DETAIL_TAB, CRM_DYNAMIC_XXX_DETAIL_TAB | Bitrix24 REST API and Marketplace Applications
Tab in the detail form of the CRM entity CRM_XXX_DETAIL_TAB, CRM_DYNAMIC_XXX_DETAIL_TAB
Tab in the detail form of the CRM entity CRM_XXX_DETAIL_TAB, CRM_DYNAMIC_XXX_DETAIL_TAB
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
crm
You can add your own tabs to the detail form of CRM objects:
leads
,
contacts
,
companies
,
deals
,
estimates
,
new invoices
,
custom object types
.
The specific placement code for the widget is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Placement Code
Location
CRM_LEAD_DETAIL_TAB
Tab in the
lead
detail form
CRM_DEAL_DETAIL_TAB
Tab in the
deal
detail form
CRM_CONTACT_DETAIL_TAB
Tab in the
contact
detail form
CRM_COMPANY_DETAIL_TAB
Tab in the
company
detail form
CRM_QUOTE_DETAIL_TAB
Tab in the
estimate
detail form
CRM_SMART_INVOICE_DETAIL_TAB
Tab in the
invoice
detail form
CRM_DYNAMIC_XXX_DETAIL_TAB
Tab in the detail form of a custom object type in CRM. Instead of XXX, specify the numeric identifier of the specific
custom object type
. For example,
CRM_DYNAMIC_183_DETAIL_TAB
What the handler receives
What the handler receives
Data is transmitted as a POST request
CRM_LEAD_DETAIL_TAB
CRM_DEAL_DETAIL_TAB
CRM_CONTACT_DETAIL_TAB
CRM_COMPANY_DETAIL_TAB
CRM_QUOTE_DETAIL_TAB
CRM_SMART_INVOICE_DETAIL_TAB
CRM_DYNAMIC_XXX_DETAIL_TAB
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
32
dc7a69a3dac11ea9c95dfc6bf5dd8a
[AUTH_ID] =>
1
bf49f6600631fcd00005a4b00000001f0f107e9a9ddb6de2bd5f7856ac587b492adb4
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
0
b73c76600631fcd00005a4b00000001f0f1079fd883d9c43bf4abf545709c61eb8f69
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_LEAD_DETAIL_TAB
[PLACEMENT_OPTIONS] => {
"ID"
:
"6591"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => d8286e173e919aa1695254997a6e3123
[AUTH_ID] =>
3
cf49f6600631fcd00005a4b00000001f0f107d9825065d14b0d269c63cdaa0bb1967d
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
2
c73c76600631fcd00005a4b00000001f0f1076f22983f060e8e14120e47cbc2c227a0
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DEAL_DETAIL_TAB
[PLACEMENT_OPTIONS] => {
"ID"
:
"3473"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => d17a24f20960a2971eda0e69754e62a2
[AUTH_ID] =>
57
f49f6600631fcd00005a4b00000001f0f1077ef2d8b6c37097b8985bb7fb4948d1e8
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
4773
c76600631fcd00005a4b00000001f0f10711f2f134f53a44072e44b61677961fac
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_CONTACT_DETAIL_TAB
[PLACEMENT_OPTIONS] => {
"ID"
:
"13037"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
1
ff08edeb6a06f8f35a28fd745039801
[AUTH_ID] =>
74
f49f6600631fcd00005a4b00000001f0f1070281f446cf788ea6bd54f8420750aaea
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
6473
c76600631fcd00005a4b00000001f0f107b5ee25f08705b5f616a23e2130eb7fad
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_COMPANY_DETAIL_TAB
[PLACEMENT_OPTIONS] => {
"ID"
:
"2946"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
5571169e21118
b274f4fa57b8fd4e2b3
[AUTH_ID] => aef49f6600631fcd00005a4b00000001f0f1079f066b85d07bc74dc9f4372d83152d70
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
9e73
c76600631fcd00005a4b00000001f0f107541600cc2176b7d270db8ab3f1eecfcf
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_QUOTE_DETAIL_TAB
[PLACEMENT_OPTIONS] => {
"ID"
:
"5"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => fff172819907af99a29b4830304aabe7
[AUTH_ID] => ccbfca670076a4b8006f518000000001201c07b80ac830a875756c6c0c9073bec005c5
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => bc3ef2670076a4b8006f518000000001201c07efcbf35af9b89bb15ea3ab8e7223fe49
[member_id] => e8857f161a1a8288f312b6cc6ad67995
[status] => L
[PLACEMENT] => CRM_SMART_INVOICE_DETAIL_TAB
[PLACEMENT_OPTIONS] => {
"ID"
:
"32"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
5
d7bde16d7895ef326320f00c4bfbd8d
[AUTH_ID] => def49f6600631fcd00005a4b00000001f0f10700d7b3563b156732e94917116f0a81a1
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => ce73c76600631fcd00005a4b00000001f0f1072e9cc05d2796e9b91abaa262fc98bdf9
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DYNAMIC_183_DETAIL_TAB
[PLACEMENT_OPTIONS] => {
"ID"
:
"3"
}
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
The value of
PLACEMENT_OPTIONS
is a JSON string containing an array of one or more keys.
Required parameters are marked with *
Parameter
Description
ID
*
string
Identifier of the CRM object for which the widget was opened.
It can be used to retrieve additional information using the corresponding methods:
any object type
crm.item.get
specifying entityTypeId = '1' for leads, '2' for deals, and
etc.
lead
crm.lead.get
deal
crm.deal.get
contact
crm.contact.get
company
crm.company.get
estimate
crm.quote.get
In the case of embedding the widget in a custom object, the type identifier can be obtained from the value of the
PLACEMENT
parameter. In the example above —
183
Typical use-cases and scenarios
Embed Widget in CRM Card
Continue exploring
Continue exploring
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Dropdown menu item above the list of entities
Next
Button above the timeline of the entity

---

## Button above the timeline of the CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY card

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/detail-activity

Button above the timeline of the CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY card | Bitrix24 REST API and Marketplace Applications
Button above the timeline of the CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY card
Button above the timeline of the CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY card
Where the widget is integrated
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
crm
You can add your item to the timeline menu of CRM objects:
leads
,
contacts
,
companies
,
deals
,
estimates
,
new invoices
,
custom object types
.
The specific placement code for the widget is specified in the
PLACEMENT
parameter of the
placement.bind
method.
Extended capabilities of the button above the timeline are described in the article
Additional capabilities of CRM_XXX_DETAIL_ACTIVITY integration
The integration will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is integrated
Where the widget is integrated
Widget code
Location
CRM_LEAD_DETAIL_ACTIVITY
Timeline menu item for
lead
CRM_CONTACT_DETAIL_ACTIVITY
Timeline menu item for
contact
CRM_COMPANY_DETAIL_ACTIVITY
Timeline menu item for
company
CRM_DEAL_DETAIL_ACTIVITY
Timeline menu item for
deal
CRM_QUOTE_DETAIL_ACTIVITY
Timeline menu item for
estimate
CRM_SMART_INVOICE_DETAIL_ACTIVITY
Timeline menu item for
invoices
CRM_DYNAMIC_XXX_DETAIL_ACTIVITY
Timeline menu item for custom CRM object type. Instead of XXX, specify the numeric identifier of the specific
custom object type
. For example,
CRM_DYNAMIC_183_DETAIL_ACTIVITY
What the handler receives
What the handler receives
Data is transmitted as a POST request
CRM_LEAD_DETAIL_ACTIVITY
CRM_DEAL_DETAIL_ACTIVITY
CRM_CONTACT_DETAIL_ACTIVITY
CRM_COMPANY_DETAIL_ACTIVITY
CRM_QUOTE_DETAIL_ACTIVITY
CRM_SMART_INVOICE_DETAIL_ACTIVITY
CRM_DYNAMIC_XXX_DETAIL_ACTIVITY
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
231
dec2797809e63f2183cd9e5c1db79
[AUTH_ID] =>
29
d1a06600631fcd00005a4b00000001f0f1071497cc09c28ec609a43bb0c802d2ad41
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
1950
c86600631fcd00005a4b00000001f0f107804dc35e52c3002c7e7e155337b89e25
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_LEAD_DETAIL_ACTIVITY
[PLACEMENT_OPTIONS] => {
"ID"
:
"6591"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => fb219fe14b3bb927487324b3bf561e3a
[AUTH_ID] =>
4
ad1a06600631fcd00005a4b00000001f0f107e9193b10f6ec5579451a015c78a66829
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
3
a50c86600631fcd00005a4b00000001f0f107d9898b9feec5e1fd2e9cf59d40121087
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DEAL_DETAIL_ACTIVITY
[PLACEMENT_OPTIONS] => {
"ID"
:
"3473"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => a3e8af64160b5eaa51e16d4cc14f23dc
[AUTH_ID] =>
65
d1a06600631fcd00005a4b00000001f0f107635565dfe5bc6e1924790e68da8091f7
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
5550
c86600631fcd00005a4b00000001f0f10715d6275f1e55e90b58fa5444cc00efdf
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_CONTACT_DETAIL_ACTIVITY
[PLACEMENT_OPTIONS] => {
"ID"
:
"13037"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => c718482c9df48a3115d039967d5183a6
[AUTH_ID] =>
8
dd1a06600631fcd00005a4b00000001f0f10753abde956bcff8eea8801f6ae598becc
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
7
d50c86600631fcd00005a4b00000001f0f1079035d2a1022c0def3c60824ec692788b
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_COMPANY_DETAIL_ACTIVITY
[PLACEMENT_OPTIONS] => {
"ID"
:
"2946"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
7e776
f9d59d8346b452bd9b60a8f3925
[AUTH_ID] => b4d1a06600631fcd00005a4b00000001f0f107d6fc31ffbd4740c5a0a5393c8744ac8a
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => a450c86600631fcd00005a4b00000001f0f10755a4090ea60da33ae27abd087bded527
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_QUOTE_DETAIL_ACTIVITY
[PLACEMENT_OPTIONS] => {
"ID"
:
"5"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => adada92053b22a4de3895402a01693cf
[AUTH_ID] =>
69
c7ca670076a4b8006f518000000001201c0720c9c9d78077b5f2c5530f64b061c8a1
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
5946
f2670076a4b8006f518000000001201c07709da4b12d3c7e82e120a20e547b638f
[member_id] => e8857f161a1a8288f312b6cc6ad67995
[status] => L
[PLACEMENT] => CRM_SMART_INVOICE_DETAIL_ACTIVITY
[PLACEMENT_OPTIONS] => {
"ID"
:
"32"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => e1f8a9f4be2f07b8645216f7b3104a20
[AUTH_ID] => e1d1a06600631fcd00005a4b00000001f0f1077ebff8b4fdddb2a57ccdbc1edd9ce1cf
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => d150c86600631fcd00005a4b00000001f0f1070a03cba852bafb9c58de5ea9fe9a0daa
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DYNAMIC_183_DETAIL_ACTIVITY
[PLACEMENT_OPTIONS] => {
"ID"
:
"3"
}
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
The value of
PLACEMENT_OPTIONS
is a JSON string containing an array of one or more keys.
Required parameters are marked with *
Parameter
Description
ID
*
string
Identifier of the CRM object for which the widget was opened.
It can be used to retrieve additional information using the corresponding methods:
any object type
crm.item.get
specifying entityTypeId = '1' for leads, '2' for deals, and
etc.
lead
crm.lead.get
deal
crm.deal.get
contact
crm.contact.get
company
crm.company.get
estimate
crm.quote.get
In the case of integrating the widget into a custom object, the type identifier can be obtained from the value of the
PLACEMENT
parameter. In the example above —
183
Continue exploring
Continue exploring
Additional Integration Features CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Tab in the detail form of the entity
Next
Extended capabilities of the button above the timeline

---

## Additional Integration Features CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/detail-activity-area

Additional Integration Features CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY | Bitrix24 REST API and Marketplace Applications
Additional Integration Features CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY
Additional Integration Features CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY
OPTIONS Parameter
Registration Example
Working with the Integration Interface
Interface Appearance LayoutDto
ContentBlockDto
ButtonDto
Examples of LayoutDto
Continue Learning
Scope:
crm
Who can work with the integration: a user with access permission to modify the entity
With additional parameters, you can set the Bitrix24 interface for your menu item in the timeline.
To add the integration, use the method
placement.bind
. The basic integration capabilities are described in the article
Button above the entity detail timeline
.
Download an example application using the integration.
OPTIONS Parameter
OPTIONS Parameter
Name
type
Description
useBuiltInInterface
boolean
Use the standard Bitrix24 interface. Default is
N
. If
Y
, the interface is built according to the described structure
LayoutDto
. The process of working with the interface is described
below
newUserNotificationTitle
string
Notification title for new users
newUserNotificationText
string
Notification text for new users. Clicking "More" will open a slider with the context
newUserNotification=Y
and a width of
800px
Registration Example
Registration Example
BX24
.
callMethod
(
'placement.bind'
,
{
'PLACEMENT'
:
'CRM_DEAL_DETAIL_ACTIVITY'
,
'HANDLER'
:
'https://your-handler-uri.com'
,
'TITLE'
:
'My Integration'
,
'OPTIONS'
: {
'useBuiltInInterface'
:
'Y'
,
'newUserNotificationTitle'
:
'Meet the new application'
,
'newUserNotificationText'
:
'E-invoice will help manage invoices'
}
}
);
Working with the Integration Interface
Working with the Integration Interface
Interaction occurs through the method
BX24.placement.call
. The application workflow when using the standard Bitrix24 interface
useBuiltInInterface = Y
:
Loading the iframe.
The application is loaded in a hidden iframe. The
placementOptions
include:
entityTypeId
entityId
useBuiltInInterface: Y
Rendering the interface.
Once the application is loaded, it should call
setLayout
to render the initial state of the integration location.
BX24
.
placement
.
call
(
'setLayout'
,
LayoutDto
, callback);
Responding to actions.
If the application displays interactive elements in the interface, such as links, it can register a handler
bindLayoutEventCallback
to handle interactions with the elements.
BX24
.
placement
.
call
(
'bindLayoutEventCallback'
,
null
, callback);
Managing element states.
The appearance and visibility of specific interface elements can be changed using
setLayoutItemState
.
BX24
.
placement
.
call
(
'setLayoutItemState'
, {
id
:
'...'
,
visible
:
true
/
false
,
properties
: {...} }, callback);
Managing buttons.
The appearance of the buttons at the bottom of the interface can be changed using
setPrimaryButtonState
and
setSecondaryButtonState
.
BX24
.
placement
.
call
(
'setPrimaryButtonState'
, {...}, callback);
BX24
.
placement
.
call
(
'setSecondaryButtonState'
, {...}, callback);
Completing the process.
When the user's interaction with the integration is finished or if the user clicks "cancel,"
finish
should be called. The timeline will switch to the default tab.
BX24
.
placement
.
call
(
'finish'
);
Locking the interface.
For long operations, such as saving, the interface can be locked by calling
lock
. To unlock, call
unlock
.
BX24
.
placement
.
call
(
'lock'
);
// lock
BX24
.
placement
.
call
(
'unlock'
);
// unlock
Tracking changes to the entity.
To track changes to entity fields, for example, to redraw the interface based on the field value, you can register a handler
bindEntityUpdateCallback
. The callback will be called immediately after the fields are saved in the editor.
BX24
.
placement
.
call
(
'bindEntityUpdateCallback'
,
null
, callback);
Interface Appearance LayoutDto
Interface Appearance LayoutDto
Name
type
Description
blocks
ContentBlockDto[]
Associative array of objects describing content blocks. The keys of the array are the block identifiers. Minimum 1 element
primaryButton
ButtonDto
Primary button. Usually completes data processing, saves it
secondaryButton
ButtonDto
Secondary button. Usually cancels the data processing
Pressing active buttons triggers callbacks:
primaryButton
— callback
BX24.placement.call('bindPrimaryButtonClickCallback', null, callback)
,
secondaryButton
— callback
BX24.placement.call('bindSecondaryButtonClickCallback', null, callback)
.
ContentBlockDto
ContentBlockDto
Content blocks of the main area can be combined and flexibly assembled into various interfaces.
General structure of a block:
{
"type"
:
"string"
,
"visible"
:
true
,
"properties"
:
{
}
}
type
— block type, string,
visible
— controls the visibility of the block, boolean field. Changing visibility allows for dynamic interfaces. Default =
true
.
properties
— set of properties for a specific block.
Types of Content Blocks
Types of Content Blocks
Type
Name
text
Text
link
Link
withTitle
Block with Title
lineOfBlocks
Multiple content blocks in one line
dropdownMenu
Dropdown Menu
input
Text Input Field
textarea
Multiline Text Input Field
select
Dropdown Input Field
list
Unordered List
section
Section
Text
Text
Block for displaying formatted text.
Required parameters are marked with *
Name
type
Description
value
*
string
Text
multiline
boolean
Handle line breaks. If
true
,
\n
characters will be replaced with
<br>
.
Default is
false
bold
boolean
Bold text. Default is
false
size
string
Text size. Available values:
xs
,
sm
,
md
— default,
lg
,
xl
color
string
Text color. Available values:
base_50
,
base_60
,
base_70
,
base_90
,
primary
,
warning
,
danger
,
success
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Hello!\nWe are starting."
,
"multiline"
:
true
,
"bold"
:
true
,
"size"
:
"lg"
,
"color"
:
"base_90"
}
}
Link
Link
Required parameters are marked with *
Name
type
Description
text
*
string
Link text, HTML tags are not supported
action
*
ActionDto
Action upon clicking the link
size
string
Text size. Available values:
xs
,
sm
,
md
— default,
lg
,
xl
bold
boolean
Bold text. Default is
false
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Open Deal"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
,
"bold"
:
true
}
}
Block with Title
Block with Title
The block displays a title and value. Another content block can be used as the value.
Required parameters are marked with *
Name
type
Description
title
*
string
Title text
inline
boolean
Show title and value in one line. Default is
false
titleWidth
string
Title width, applied if
inline=true
. Available values:
sm
,
md
— default,
lg
block
*
ContentBlockDto
Content block that serves as the value. Blocks of types
text
,
link
,
lineOfBlocks
are supported
Example with a content block of type text:
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Title"
,
"block"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Some value"
}
}
}
}
Example with a content block of type link:
{
"type"
:
"withTitle"
,
"properties"
:
{
"title"
:
"Title 2"
,
"block"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Open Deal"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
}
}
,
"inline"
:
true
}
}
Multiple Content Blocks in One Line
Multiple Content Blocks in One Line
The block displays multiple content blocks of type text or link in one line. This allows displaying text with different formatting and links in a single line.
Required parameters are marked with *
Name
type
Description
blocks
*
ContentBlockDto[]
Associative array of content blocks. Blocks of types
text
,
link
are supported
{
"type"
:
"lineOfBlocks"
,
"properties"
:
{
"blocks"
:
{
"text"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Some text"
}
}
,
"link"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"link"
,
"action"
:
{
"type"
:
"redirect"
,
"uri"
:
"/crm/deal/details/123/"
}
}
}
,
"boldText"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"bold text"
,
"bold"
:
true
}
}
}
}
}
Dropdown Menu
Dropdown Menu
Required parameters are marked with *
Name
type
Description
selectedValue
string
Current selected value. If not filled, the first value from the list will be used
values
*
object
Object where property names are the code of the value option
vendor
, and property values are the values that the user will see
vendor
{
"type"
:
"dropdownMenu"
,
"properties"
:
{
"selectedValue"
:
"client"
,
"values"
:
{
""
:
"- not selected -"
,
"vendor"
:
"vendor"
,
"client"
:
"client"
}
}
}
To track value changes, register the callback:
BX24.placement.call('bindValueChangeCallback', null, Callback)
to receive changes in any of the blocks
BX24.placement.call('bindValueChangeCallback', 'block id', Callback)
to receive value changes only for that block.
When the value changes, the callback will receive the
id
of the dropdown block and its current value:
{id: "clientMenu", value: "client"}
.
Text Input Field
Text Input Field
Required parameters are marked with *
Name
type
Description
title
string
Field title
value
string
Field text
placeholder
string
Placeholder. Will be shown if the field is not filled
disabled
boolean
If
true
is passed, the field will be locked for editing. Default is
false
errorText
string
Error message. If a non-empty
errorText
is passed, the current value of the field did not pass validation. The user will see the error
{
"type"
:
"input"
,
"properties"
:
{
"value"
:
"aaa@mail.domain"
,
"placeholder"
:
"Enter email"
,
"title"
:
"Email"
,
"errorText"
:
"Invalid value"
}
}
To track value changes, register the callback:
BX24.placement.call('bindValueChangeCallback', null, Callback)
to receive changes in any of the blocks
BX24.placement.call('bindValueChangeCallback', 'block id', Callback)
to receive value changes only for that block.
When the value changes, the callback will receive the
id
of the text input field and its current value:
{id: "email", value: "aaa@mail.domain"}
.
Multiline Text Input Field
Multiline Text Input Field
Required parameters are marked with *
Name
type
Description
title
string
Field title
value
string
Field text
placeholder
string
Placeholder. Will be shown if the field is not filled
disabled
boolean
If
true
is passed, the field will be locked for editing. Default is
false
errorText
string
Error message. If a non-empty
errorText
is passed, the current value of the field did not pass validation. The user will see the error
{
"type"
:
"textarea"
,
"properties"
:
{
"value"
:
"Go through the gate\nTurn left"
,
"title"
:
"Additional Information"
}
}
To track value changes, register the callback:
BX24.placement.call('bindValueChangeCallback', null, Callback)
to receive changes in any of the blocks
BX24.placement.call('bindValueChangeCallback', 'block id', Callback)
to receive value changes only for that block.
When the value changes, the callback will receive the
id
of the text input field and its current value:
{id: "description", value: "Go through the gate\nTurn left"}
.
Dropdown Input Field
Dropdown Input Field
Required parameters are marked with *
Name
type
Description
title
string
Field title
selectedValue
string
Current selected value. If not filled, the first value from the list will be used
values
*
object
Object where property names are the code of the value option
nyc
, and property values are the values that the user will see
New York
disabled
boolean
If
true
is passed, the field will be locked for editing. Default is
false
errorText
string
Error message. If a non-empty
errorText
is passed, the current value of the field did not pass validation. The user will see the error
{
"type"
:
"select"
,
"properties"
:
{
"selectedValue"
:
"la"
,
"values"
:
{
"nyc"
:
"New York"
,
"la"
:
"Los Angeles"
,
"chi"
:
"Chicago"
}
,
"title"
:
"City"
}
}
To track value changes, register the callback:
BX24.placement.call('bindValueChangeCallback', null, Callback)
to receive changes in any of the blocks
BX24.placement.call('bindValueChangeCallback', 'block id', Callback)
to receive value changes only for that block.
When the value changes, the callback will receive the
id
of the field and its current value:
{id: "city", value: "nyc"}
.
Unordered List
Unordered List
Required parameters are marked with *
Name
type
Description
blocks
*
ContentBlockDto[]
Associative array of content blocks. Blocks of types
text
,
link
,
lineOfBlocks
are supported. Minimum 1 element
{
"type"
:
"list"
,
"properties"
:
{
"blocks"
:
{
"li1"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Importing CRM elements without details"
,
"color"
:
"base_70"
}
}
,
"li2"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Getting Started with CRM"
,
"action"
:
{
"type"
:
"layoutEvent"
,
"value"
:
"link2ItemClicked!"
}
}
}
,
"li3"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"How to convert a lead"
,
"bold"
:
true
,
"color"
:
"base_90"
}
}
}
}
}
Section
Section
The block displays a grouped set of blocks. An option with an image is possible.
Required parameters are marked with *
Name
type
Description
blocks
*
ContentBlockDto[]
Associative array of content blocks. Any types of blocks are supported. Minimum 1 element, maximum 20
imageSrc
string
Full path to the image
imageSize
string
Image size. Available values:
lg
— default,
md
,
sm
type
string
Appearance. Available values:
default
— default,
primary
,
warning
,
danger
,
success
,
withBorder
Example with multiple blocks and an image:
{
"type"
:
"section"
,
"properties"
:
{
"type"
:
"withBorder"
,
"imageSrc"
:
"https://helpdesk.bitrix24.com/examples/section.png"
,
"blocks"
:
{
"header"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
" Send the client a link to the meeting"
,
"size"
:
"xl"
,
"color"
:
"base_90"
}
}
,
"notes"
:
{
"type"
:
"list"
,
"properties"
:
{
"blocks"
:
{
"li1"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"The client will choose a convenient slot"
,
"color"
:
"base_70"
}
}
,
"li2"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"The meeting will appear in your activities"
,
"color"
:
"base_70"
}
}
}
}
}
,
"howto"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"How does it work?"
,
"action"
:
{
"type"
:
"openRestApp"
,
"value"
:
"howto"
}
}
}
}
}
}
Example with a single block without an image:
{
"type"
:
"section"
,
"properties"
:
{
"type"
:
"danger"
,
"blocks"
:
{
"errorMessage"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"An error occurred. Please try again."
,
"color"
:
"danger"
}
}
}
}
}
ButtonDto
ButtonDto
Button at the bottom of the interface.
Name
type
Description
title
*
string
Button text
state
string
State. Available values:
normal
— default,
disabled
Actions with Button ActionDto
Actions with Button ActionDto
An action defines the response to a click on a specific element. Available types of actions:
redirect
,
JS event
,
open application slider
.
Redirect
Redirect
Redirect can occur in two ways:
slider, if it is a relative link to standard Bitrix24 objects that support working in a slider,
regular redirect in other cases.
Required parameters are marked with *
Name
type
Description
type
*
const
Action type. Must have the value
redirect
value
*
string
URI link. For example:
https://example.com
or
/crm/deal/details/1/
for Bitrix24 objects
{
"type"
:
"redirect"
,
"value"
:
"/crm/deal/details/1/"
}
JS Event
JS Event
Required parameters are marked with *
Name
type
Description
type
*
const
Action type. Must have the value
layoutEvent
value
*
string
Event identifier. For example:
doSomething
or
start_processing
{
"type"
:
"layoutEvent"
,
"value"
:
"clicked"
}
Calling the action triggers the handler registered via
BX24.placement.call('bindLayoutEventCallback', null, Callback)
or
BX24.placement.call('bindLayoutEventCallback', 'block id', Callback)
.
The handler will receive the
value
of the action and the
id
of the block that triggered the action:
{id: "myLink", value: "clicked"}
.
Opening Application Slider
Opening Application Slider
Calling the action will open the slider of the application that registered the integration. The context will be passed to the slider:
entityTypeId
is the identifier of the object type to which the deal is linked,
entityId
is the identifier of the element.
Required parameters are marked with *
Name
type
Description
type
*
const
Action type. Must have the value
openRestApp
value
array
Array of arbitrary format, the data from which will be passed to the application slider
sliderParams
ActionSliderParamsDto
Parameters for opening the slider
ActionSliderParamsDto
ActionSliderParamsDto
Name
type
Description
width
int
Slider width, px. Cannot be used simultaneously with
leftBoundary
leftBoundary
int
Slider full width of the browser window with a left margin, px. Cannot be used simultaneously with
width
title
string
Text for the browser window title when opening the slider
{
"type"
:
"openRestApp"
,
"value"
:
{
"myId"
:
123
,
"someImportant"
:
"qwerty"
}
,
"sliderParams"
:
{
"title"
:
"This is the slider application title"
,
"width"
:
700
}
}
Examples of LayoutDto
Examples of LayoutDto
{
"blocks"
:
{
"section1"
:
{
"type"
:
"section"
,
"properties"
:
{
"type"
:
"withBorder"
,
"imageSrc"
:
"https://helpdesk.bitrix24.com/examples/section.png"
,
"blocks"
:
{
"header"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
" Send the client a link to the meeting"
,
"size"
:
"xl"
,
"color"
:
"base_90"
}
}
,
"notes"
:
{
"type"
:
"list"
,
"properties"
:
{
"blocks"
:
{
"li1"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"The client will choose a convenient slot"
,
"color"
:
"base_70"
}
}
,
"li2"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"The meeting will appear in your activities"
,
"color"
:
"base_70"
}
}
}
}
}
,
"howto"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"How does it work?"
,
"action"
:
{
"type"
:
"openRestApp"
,
"value"
:
"howto"
}
}
}
}
}
}
,
"section2"
:
{
"type"
:
"section"
,
"properties"
:
{
"type"
:
"primary"
,
"blocks"
:
{
"sectionText"
:
{
"type"
:
"lineOfBlocks"
,
"properties"
:
{
"blocks"
:
{
"block1"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"If you haven't tried the sales generator yet, now is the time to test this tool in action"
,
"color"
:
"base_70"
}
}
,
"block2"
:
{
"type"
:
"link"
,
"properties"
:
{
"text"
:
"Learn more"
,
"action"
:
{
"type"
:
"redirect"
,
"value"
:
"/crm/"
}
}
}
}
}
}
}
}
}
}
,
"primaryButton"
:
{
"title"
:
"Enable"
}
,
"secondaryButton"
:
{
"title"
:
"Cancel"
}
}
{
"blocks"
:
{
"errorMessage"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"Use all the capabilities of mobile SMS marketing\nSending SMS is easy to set up and use in Bitrix24 CRM\nSend messages directly from the deal, lead, client, invoice, or estimate card."
,
"size"
:
"sm"
,
"color"
:
"base_70"
,
"multiline"
:
true
}
}
,
"section1"
:
{
"type"
:
"section"
,
"properties"
:
{
"type"
:
"danger"
,
"blocks"
:
{
"errorMessage"
:
{
"type"
:
"text"
,
"properties"
:
{
"value"
:
"An error occurred. Please try again"
,
"color"
:
"danger"
}
}
}
}
}
}
,
"primaryButton"
:
{
"title"
:
"Enable"
,
"state"
:
"disabled"
}
,
"secondaryButton"
:
{
"title"
:
"Cancel"
,
"state"
:
"disabled"
}
}
{
"blocks"
:
{
"name"
:
{
"type"
:
"input"
,
"properties"
:
{
"value"
:
"John"
,
"placeholder"
:
"Enter name"
,
"title"
:
"Name"
}
}
,
"lastname"
:
{
"type"
:
"input"
,
"properties"
:
{
"value"
:
"Doe"
,
"placeholder"
:
""
,
"title"
:
"Last Name"
}
}
,
"secondname"
:
{
"type"
:
"input"
,
"properties"
:
{
"value"
:
""
,
"placeholder"
:
"Enter middle name"
,
"title"
:
"Middle Name"
}
}
}
,
"primaryButton"
:
{
"title"
:
"Save"
}
,
"secondaryButton"
:
{
"title"
:
"Cancel"
}
}
Continue Learning
Continue Learning
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Button above the timeline of the CRM_XXX_DETAIL_ACTIVITY, CRM_DYNAMIC_XXX_DETAIL_ACTIVITY card
Copied
Was the article helpful?
Yes
No
Previous
Button above the timeline of the entity
Next
Dropdown menu item of the top button in the entity

---

## Dropdown Menu Item of the Top Button in the CRM_XXX_DETAIL_TOOLBAR, CRM_DYNAMIC_XXX_DETAIL_TOOLBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/detail-toolbar

Dropdown Menu Item of the Top Button in the CRM_XXX_DETAIL_TOOLBAR, CRM_DYNAMIC_XXX_DETAIL_TOOLBAR | Bitrix24 REST API and Marketplace Applications
Dropdown Menu Item of the Top Button in the CRM_XXX_DETAIL_TOOLBAR, CRM_DYNAMIC_XXX_DETAIL_TOOLBAR
Dropdown Menu Item of the Top Button in the CRM_XXX_DETAIL_TOOLBAR, CRM_DYNAMIC_XXX_DETAIL_TOOLBAR
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Learning
Scope:
crm
You can add your dropdown menu item to the top button of CRM object cards:
leads
,
contacts
,
companies
,
deals
,
estimates
,
new invoices
,
custom object types
.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
CRM_LEAD_DETAIL_TOOLBAR
Dropdown menu item of the top button in the
lead
card
CRM_DEAL_DETAIL_TOOLBAR
Dropdown menu item of the top button in the
deal
card
CRM_CONTACT_DETAIL_TOOLBAR
Dropdown menu item of the top button in the
contact
card
CRM_COMPANY_DETAIL_TOOLBAR
Dropdown menu item of the top button in the
company
card
CRM_QUOTE_DETAIL_TOOLBAR
Dropdown menu item of the top button in the
estimate
card
CRM_SMART_INVOICE_DETAIL_TOOLBAR
Dropdown menu item of the top button in the
invoices
card
CRM_DYNAMIC_XXX_DETAIL_TOOLBAR
Dropdown menu item of the top button in the custom CRM object type card. Instead of XXX, specify the numeric identifier of the specific
custom object type
. For example,
CRM_DYNAMIC_183_DETAIL_ACTIVITY
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
CRM_LEAD_DETAIL_TOOLBAR
CRM_DEAL_DETAIL_TOOLBAR
CRM_CONTACT_DETAIL_TOOLBAR
CRM_COMPANY_DETAIL_TOOLBAR
CRM_QUOTE_DETAIL_TOOLBAR
CRM_SMART_INVOICE_DETAIL_TOOLBAR
CRM_DYNAMIC_XXX_DETAIL_TOOLBAR
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
0
d43bf11edd7e3c050ea8b0577eb6a87
[AUTH_ID] =>
18
d3a06600631fcd00005a4b00000001f0f1077b7ce52f79713d82c4bc9960bcf4b598
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
0852
c86600631fcd00005a4b00000001f0f107ce505dcd9306e0eb55ad77df1d2b2f16
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_LEAD_DETAIL_TOOLBAR
[PLACEMENT_OPTIONS] => {
"ID"
:
"6591"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
88
fe421c3ce39985adb9d220cc965e61
[AUTH_ID] =>
31
d3a06600631fcd00005a4b00000001f0f10791c1fc87943e62dc8a28210b56b2af87
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
2152
c86600631fcd00005a4b00000001f0f10780aada857e86212d3a73281c74525ccd
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DEAL_DETAIL_TOOLBAR
[PLACEMENT_OPTIONS] => {
"ID"
:
"3473"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
8
bc3acce3a150e11f48469e4a37384af
[AUTH_ID] =>
44
d3a06600631fcd00005a4b00000001f0f10784af91cb9aeebddf2b1822776d4e7a9e
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
3452
c86600631fcd00005a4b00000001f0f1078f707dfdc8c4b9830929c565294f37b0
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_CONTACT_DETAIL_TOOLBAR
[PLACEMENT_OPTIONS] => {
"ID"
:
"13037"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
75
ca32f216adb32ca5a16c928d9a6fd2
[AUTH_ID] =>
5
bd3a06600631fcd00005a4b00000001f0f107b39291622bfbbc6a0c75eeadb4ef65ea
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
4
b52c86600631fcd00005a4b00000001f0f107ac1cfa783b59df28b087eead8d49b869
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_COMPANY_DETAIL_TOOLBAR
[PLACEMENT_OPTIONS] => {
"ID"
:
"2946"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
7
c10e9dd04fc0ee9a2ca4981b708f322
[AUTH_ID] =>
85
d3a06600631fcd00005a4b00000001f0f107f1285d38d8f287a126f7fd9d42ab87fb
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
7552
c86600631fcd00005a4b00000001f0f1072f206ef3499d9fb87f5d9a575a78186a
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_QUOTE_DETAIL_TOOLBAR
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"5"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
0913971
fc9a85afea6263cc6dcff04bd
[AUTH_ID] =>
9
fc7ca670076a4b8006f518000000001201c07e51994c33447f80190049359e6d29a0c
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
8
f46f2670076a4b8006f518000000001201c078f877b9e542e35eeeca4c284d2fd976a
[member_id] => e8857f161a1a8288f312b6cc6ad67995
[status] => L
[PLACEMENT] => CRM_SMART_INVOICE_DETAIL_TOOLBAR
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"32"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
220448997
c6d7f606bd25c1c1896456e
[AUTH_ID] =>
9
ed3a06600631fcd00005a4b00000001f0f10797d8322191958e46f791643a1f7cb06f
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
8e52
c86600631fcd00005a4b00000001f0f10734c4bc5b1f7ad2eca54b546ef12a2bf9
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DYNAMIC_183_DETAIL_TOOLBAR
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"3"
}
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
The value of
PLACEMENT_OPTIONS
is a JSON string containing an array of one or more keys.
Required parameters are marked with *
Parameter
Description
ID
* or
ENTITY_ID
*
string
Identifier of the CRM object for which the widget was opened.
It can be used to retrieve additional information using the corresponding methods:
any object type
crm.item.get
specifying entityTypeId = '1' for leads, '2' for deals, and
etc.
lead
crm.lead.get
deal
crm.deal.get
contact
crm.contact.get
company
crm.company.get
estimate
crm.quote.get
In the case of embedding the widget in a custom object, the type identifier can be obtained from the value of the
PLACEMENT
parameter. In the example above —
183
Continue Learning
Continue Learning
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Extended capabilities of the button above the timeline
Next
Context menu item of the activity in the entity

---

## Context Menu Item for the Deal in the CRM Element Card CRM_XXX_ACTIVITY_TIMELINE_MENU, CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/activity-timeline-menu

Context Menu Item for the Deal in the CRM Element Card CRM_XXX_ACTIVITY_TIMELINE_MENU, CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU | Bitrix24 REST API and Marketplace Applications
Context Menu Item for the Deal in the CRM Element Card CRM_XXX_ACTIVITY_TIMELINE_MENU, CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU
Context Menu Item for the Deal in the CRM Element Card CRM_XXX_ACTIVITY_TIMELINE_MENU, CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU
Where the Widget is Embedded
What the Handler Receives
Continue Exploring
Scope:
crm
You can add your context menu item for the deal in the CRM object cards:
leads
,
deals
,
estimates
,
new invoices
,
custom object types
.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
CRM_LEAD_ACTIVITY_TIMELINE_MENU
Context menu item for the deal in the
lead
CRM_DEAL_ACTIVITY_TIMELINE_MENU
Context menu item for the deal in the
deal
CRM_QUOTE_ACTIVITY_TIMELINE_MENU
Context menu item for the deal in the
estimate
CRM_SMART_INVOICE_ACTIVITY_TIMELINE_MENU
Context menu item for the deal in the
new invoices
CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU
Context menu item for the deal in custom CRM object types. Instead of XXX, specify the numeric identifier of the specific
custom object type
. For example,
CRM_DYNAMIC_183_LIST_MENU
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
CRM_LEAD_ACTIVITY_TIMELINE_MENU
CRM_DEAL_ACTIVITY_TIMELINE_MENU
CRM_QUOTE_ACTIVITY_TIMELINE_MENU
CRM_SMART_INVOICE_ACTIVITY_TIMELINE_MENU
CRM_DYNAMIC_XXX_ACTIVITY_TIMELINE_MENU
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => e6a18a6abe41ba3bd944897d8dc5186d
[AUTH_ID] =>
45
d4a06600631fcd00005a4b00000001f0f10767246d86a580fae119d2a2601665eb33
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
3553
c86600631fcd00005a4b00000001f0f1074bdbcddd7232d3413e2b9ff1ee91dc96
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_LEAD_ACTIVITY_TIMELINE_MENU
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"6591"
,
"TYPE_ID"
:
"1"
,
"TYPE_CATEGORY_ID"
:
"6"
,
"ASSOCIATED_ENTITY_ID"
:
"1523"
,
"ASSOCIATED_ENTITY_TYPE_ID"
:
"6"
,
"TIMELINE_ITEM_ID"
:
"29937"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
71
cc8c707a630542d5e2cf7435bf88c4
[AUTH_ID] =>
87
d4a06600631fcd00005a4b00000001f0f10758d4aabbf27967a9af747de646c5447c
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
7753
c86600631fcd00005a4b00000001f0f1078ec2dd6e94d5dc8f1aebf6524a86ee78
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DEAL_ACTIVITY_TIMELINE_MENU
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"3463"
,
"ASSOCIATED_ENTITY_ID"
:
"1517"
,
"ASSOCIATED_ENTITY_TYPE_ID"
:
"6"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => a63d2f88ffd62d6a300aaea7bf5ebf32
[AUTH_ID] =>
757
ba26600631fcd00005a4b00000001f0f107b07473a33f9378bf912d602ecb056119
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
65
fac96600631fcd00005a4b00000001f0f10726b77ceb5a0aaa50e143b1086fa03324
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_QUOTE_ACTIVITY_TIMELINE_MENU
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"5"
,
"ASSOCIATED_ENTITY_ID"
:
"1529"
,
"ASSOCIATED_ENTITY_TYPE_ID"
:
"6"
}
}
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => a2032d292bcc91a22022db330433a933
[AUTH_ID] => ee2ad0670076a4b8006f518000000001201c07383646b2116914be86aecd467ade5a3e
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => dea9f7670076a4b8006f518000000001201c07e183b89e2613ce88ba7c56f8f80f19d9
[member_id] => e8857f161a1a8288f312b6cc6ad67995
[status] => L
[PLACEMENT] => CRM_SMART_INVOICE_ACTIVITY_TIMELINE_MENU
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"32"
,
"ASSOCIATED_ENTITY_ID"
:
"238"
,
"ASSOCIATED_ENTITY_TYPE_ID"
:
"6"
}
}
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => d659900f7e966c5d135d349b7b7f3c0d
[AUTH_ID] =>
4
a7ba26600631fcd00005a4b00000001f0f1071e1f009645e93bf550bc02ac4f8fdcf6
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
3
afac96600631fcd00005a4b00000001f0f107adfab4bb11ae71eaf061319f2b4b2f87
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DYNAMIC_183_ACTIVITY_TIMELINE_MENU
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"3"
,
"ASSOCIATED_ENTITY_ID"
:
"1527"
,
"ASSOCIATED_ENTITY_TYPE_ID"
:
"6"
}
}
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
The value of
PLACEMENT_OPTIONS
is a JSON string containing an array of one or more keys.
Required parameters are marked with *
Parameter
Description
ENTITY_ID
*
string
Identifier of the CRM object for which the widget was opened.
Can be used to retrieve additional information using the corresponding methods:
any object type
crm.item.get
specifying entityTypeId = '1' for leads, '2' for deals, and
etc.
lead
crm.lead.get
deal
crm.deal.get
estimate
crm.quote.get
In the case of embedding the widget in a custom type object, the type identifier can be obtained from the value of the
PLACEMENT
parameter. In the example above, it is
183
ASSOCIATED_ENTITY_ID
*
string
Identifier of the CRM deal for which the widget was opened.
Can be used to retrieve additional information using the method
crm.activity.get
ASSOCIATED_ENTITY_TYPE_ID
*
string
Identifier of the deal entity type (Activity)
TYPE_ID
*
string
Identifier of the event type
TYPE_CATEGORY_ID
*
string
Identifier of the timeline record type
TIMELINE_ITEM_ID
*
string
Identifier of the timeline record
Continue Exploring
Continue Exploring
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Dropdown menu item of the top button in the entity
Next
Dropdown menu item of the document generator

---

## Dropdown Menu Item for the Document Generator CRM_XXX_DOCUMENTGENERATOR_BUTTON

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/document-generator-button

Dropdown Menu Item for the Document Generator CRM_XXX_DOCUMENTGENERATOR_BUTTON | Bitrix24 REST API and Marketplace Applications
Dropdown Menu Item for the Document Generator CRM_XXX_DOCUMENTGENERATOR_BUTTON
Dropdown Menu Item for the Document Generator CRM_XXX_DOCUMENTGENERATOR_BUTTON
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Learning
Scope:
intranet
You can add your item to the dropdown menu of the document generator for CRM entities:
leads
,
contacts
,
companies
,
deals
,
estimates
,
new invoices
,
custom entity types
.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
CRM_LEAD_DOCUMENTGENERATOR_BUTTON
Item in the dropdown menu of the document generator for
leads
CRM_CONTACT_DOCUMENTGENERATOR_BUTTON
Item in the dropdown menu of the document generator for
contacts
CRM_COMPANY_DOCUMENTGENERATOR_BUTTON
Item in the dropdown menu of the document generator for
companies
CRM_DEAL_DOCUMENTGENERATOR_BUTTON
Item in the dropdown menu of the document generator for
deals
CRM_SMART_INVOICE_DOCUMENTGENERATOR_BUTTON
Item in the dropdown menu of the document generator for
invoices
CRM_QUOTE_DOCUMENTGENERATOR_BUTTON
Item in the dropdown menu of the document generator for
estimates
CRM_DYNAMIC_XXX_DOCUMENTGENERATOR_BUTTON
Item in the dropdown menu of the document generator for custom CRM entity types. Instead of XXX, specify the numeric identifier of the specific
custom entity type
. For example,
CRM_DYNAMIC_183_DOCUMENTGENERATOR_BUTTON
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
CRM_LEAD_DOCUMENTGENERATOR_BUTTON
CRM_DEAL_DOCUMENTGENERATOR_BUTTON
CRM_CONTACT_DOCUMENTGENERATOR_BUTTON
CRM_COMPANY_DOCUMENTGENERATOR_BUTTON
CRM_QUOTE_DOCUMENTGENERATOR_BUTTON
CRM_SMART_INVOICE_DOCUMENTGENERATOR_BUTTON
CRM_DYNAMIC_XXX_DOCUMENTGENERATOR_BUTTON
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
459
ca665c9cab4ddfe9ea5ae2a0840f1
[AUTH_ID] => d54bba6600631fcd00005a4b00000001f0f10778a1773b649abec1feea11861a78c85a
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => c5cae16600631fcd00005a4b00000001f0f1070bb92bc9d139bcccf13fd5061e168c97
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_LEAD_DOCUMENTGENERATOR_BUTTON
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"6591"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
23
ab3058338edf7c4c30a52e4d0b3f94
[AUTH_ID] =>
024
cba6600631fcd00005a4b00000001f0f10776117251d4c2d883c3b981273ddc1d2f
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => f2cae16600631fcd00005a4b00000001f0f1071ccf5fc07f1f6e09595a46e2689ad63b
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DEAL_DOCUMENTGENERATOR_BUTTON
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"3473"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
8610
c737a7b6d9e8707e897310c92a5c
[AUTH_ID] =>
234
cba6600631fcd00005a4b00000001f0f107e5d9a6b11c75b358354b7909a3cbb1d5
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
13
cbe16600631fcd00005a4b00000001f0f1072808b892db51d0797e9f6ef1f47ac479
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_CONTACT_DOCUMENTGENERATOR_BUTTON
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"13037"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
6
c69387b1893adfbce7b0e9dd09a4334
[AUTH_ID] =>
474
cba6600631fcd00005a4b00000001f0f1075e5c6675d9cc38d0226e8d64a137f0d4
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
37
cbe16600631fcd00005a4b00000001f0f107ad057bdb52baf3c9f25ebd88c351e5cb
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_COMPANY_DOCUMENTGENERATOR_BUTTON
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"2946"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
92520
ef005add4cddf34ce7d56417cd6
[AUTH_ID] =>
734
cba6600631fcd00005a4b00000001f0f10783d784554c5d20e60a70194e7fae0928
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
63
cbe16600631fcd00005a4b00000001f0f107f7e3fca578b3e3b68e5be0cf70b35ccc
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_QUOTE_DOCUMENTGENERATOR_BUTTON
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"5"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => adada92053b22a4de3895402a01693cf
[AUTH_ID] =>
69
c7ca670076a4b8006f518000000001201c0720c9c9d78077b5f2c5530f64b061c8a1
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
5946
f2670076a4b8006f518000000001201c07709da4b12d3c7e82e120a20e547b638f
[member_id] => e8857f161a1a8288f312b6cc6ad67995
[status] => L
[PLACEMENT] => CRM_SMART_INVOICE_DOCUMENTGENERATOR_BUTTON
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"32"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => e704d5033456989068deea36a324b888
[AUTH_ID] =>
904
cba6600631fcd00005a4b00000001f0f1072f641be14b9ac7606506e5e3ed850130
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
80
cbe16600631fcd00005a4b00000001f0f107151fd45dc66ee22283e42cdf941e8436
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DYNAMIC_183_DOCUMENTGENERATOR_BUTTON
[PLACEMENT_OPTIONS] => {
"ENTITY_ID"
:
"3"
}
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
The value of
PLACEMENT_OPTIONS
is a JSON string containing an array of one or more keys.
Required parameters are marked with *
Parameter
Description
ENTITY_ID
*
string
Identifier of the CRM entity for which the widget was opened.
It can be used to retrieve additional information using the corresponding methods:
any entity type
crm.item.get
specifying entityTypeId = '1' for leads, '2' for deals, and
etc.
lead
crm.lead.get
deal
crm.deal.get
contact
crm.contact.get
company
crm.company.get
estimate
crm.quote.get
In the case of embedding the widget in a custom entity type, the type identifier can be obtained from the value of the
PLACEMENT
parameter. In the example above —
183
Continue Learning
Continue Learning
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Context menu item of the activity in the entity
Next
Dropdown menu item of the top button in the Automation rule designer

---

## Dropdown Menu Item of the Top Button in the CRM Robot Designer CRM_XXX_ROBOT_DESIGNER_TOOLBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/robot-designer-toolbar

Dropdown Menu Item of the Top Button in the CRM Robot Designer CRM_XXX_ROBOT_DESIGNER_TOOLBAR | Bitrix24 REST API and Marketplace Applications
Dropdown Menu Item of the Top Button in the CRM Robot Designer CRM_XXX_ROBOT_DESIGNER_TOOLBAR
Dropdown Menu Item of the Top Button in the CRM Robot Designer CRM_XXX_ROBOT_DESIGNER_TOOLBAR
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Learning
Scope:
intranet
You can add your dropdown menu item to the top button of the robot designer in CRM entities:
leads
,
deals
,
new invoices
,
custom entity types
.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
CRM_LEAD_ROBOT_DESIGNER_TOOLBAR
Dropdown menu item of the top button in the
lead
CRM_DEAL_ROBOT_DESIGNER_TOOLBAR
Dropdown menu item of the top button in the
deal
CRM_SMART_INVOICE_ROBOT_DESIGNER_TOOLBAR
Dropdown menu item of the top button in the
new invoices
CRM_DYNAMIC_XXX_ROBOT_DESIGNER_TOOLBAR
Dropdown menu item of the top button in custom CRM entity types. Replace XXX with the numeric identifier of the specific
custom entity type
. For example,
CRM_DYNAMIC_183_LIST_MENU
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
CRM_LEAD_ROBOT_DESIGNER_TOOLBAR
CRM_DEAL_ROBOT_DESIGNER_TOOLBAR
CRM_SMART_INVOICE_ROBOT_DESIGNER_TOOLBAR
CRM_DYNAMIC_XXX_ROBOT_DESIGNER_TOOLBAR
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
2
ce63de88c4a9f5843e148d6f7b7a6ed
[AUTH_ID] => d54fba6600631fcd00005a4b00000001f0f1073f6f5fc879c485f124cc572c68a6ee17
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => c5cee16600631fcd00005a4b00000001f0f107833fc0c197d37b9b13905b691787bbdb
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_LEAD_ROBOT_DESIGNER_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => aa01af1bd7f74d944ab61bdc8ed4f011
[AUTH_ID] => ec4fba6600631fcd00005a4b00000001f0f107219e88649824f5ded51f56111616561c
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => dccee16600631fcd00005a4b00000001f0f107021a4718dc94fa53f048dac305baff48
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_DEAL_ROBOT_DESIGNER_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
551
f45b6c2344572c396f678b19b9fd2
[AUTH_ID] =>
9
c44d0670076a4b8006f518000000001201c07653252db32225bf0a643c676de22ba44
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
8
cc3f7670076a4b8006f518000000001201c07f2d093e0a9e3af54d1c1bd9f51b39b95
[member_id] => e8857f161a1a8288f312b6cc6ad67995
[status] => L
[PLACEMENT] => CRM_SMART_INVOICE_ROBOT_DESIGNER_TOOLBAR
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => c1ec1ec90542fe796fe8868c4da3c482
[AUTH_ID] =>
9745
d0670076a4b8006f518000000001201c070f6ab1c3c782c839d8c502019162ff5a
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
87
c4f7670076a4b8006f518000000001201c078c7f1717892822ebf3ef37611b566015
[member_id] => e8857f161a1a8288f312b6cc6ad67995
[status] => L
[PLACEMENT] => CRM_DYNAMIC_183_ROBOT_DESIGNER_TOOLBAR
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
In the current widget, the
PLACEMENT_OPTIONS
parameter is not passed.
Continue Learning
Continue Learning
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Dropdown menu item of the document generator
Next
Dropdown menu item in the Sales Funnels

---

## Menu Item in CRM Sales Funnels Toolbar

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/funnels-toolbar

Menu Item in CRM Sales Funnels Toolbar | Bitrix24 REST API and Marketplace Applications
Menu Item in CRM Sales Funnels Toolbar
Menu Item in CRM Sales Funnels Toolbar
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Your Exploration
Scope:
intranet
You can add your item to the sales funnels toolbar.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
CRM_FUNNELS_TOOLBAR
Item in the sales funnels toolbar
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
4
c8dff86744e675bbb861d69003fbbe9
[AUTH_ID] =>
574
fba6600631fcd00005a4b00000001f0f107066649fd06e706777e462385fca29ac6
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
47
cee16600631fcd00005a4b00000001f0f107f2599a4c4602cfa840b6f9765e5f30c7
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_FUNNELS_TOOLBAR
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
In the current widget, the
PLACEMENT_OPTIONS
parameter is not passed.
Continue Your Exploration
Continue Your Exploration
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Dropdown menu item of the top button in the Automation rule designer
Next
Item in the left menu of CRM analytics

---

## CRM Analytics Menu Item CRM_ANALYTICS_MENU

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/analytics-menu

CRM Analytics Menu Item CRM_ANALYTICS_MENU | Bitrix24 REST API and Marketplace Applications
CRM Analytics Menu Item CRM_ANALYTICS_MENU
CRM Analytics Menu Item CRM_ANALYTICS_MENU
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue your exploration
Scope:
crm
You can add your item to the list of applications in CRM Analytics.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget Code
Location
CRM_ANALYTICS_MENU
Item in the CRM Analytics application list
What the handler receives
What the handler receives
Data is sent as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
1
d421409a6c74c6f917ecd29e5ec3a86
[AUTH_ID] =>
7
b4eba6600631fcd00005a4b00000001f0f10785092f421ae959432ff27233c97c2226
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
6
bcde16600631fcd00005a4b00000001f0f107338065a0ff687e880e437a8ec7ec6919
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_ANALYTICS_MENU
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
In the current widget, the
PLACEMENT_OPTIONS
parameter is not passed.
Continue your exploration
Continue your exploration
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Dropdown menu item in the Sales Funnels
Next
Dropdown menu item of the top button in CRM analytics

---

## Dropdown Menu Item of the Top Button in CRM Analytics CRM_ANALYTICS_TOOLBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/crm/analytics-toolbar

Dropdown Menu Item of the Top Button in CRM Analytics CRM_ANALYTICS_TOOLBAR | Bitrix24 REST API and Marketplace Applications
Dropdown Menu Item of the Top Button in CRM Analytics CRM_ANALYTICS_TOOLBAR
Dropdown Menu Item of the Top Button in CRM Analytics CRM_ANALYTICS_TOOLBAR
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Your Exploration
Scope:
intranet
You can add your own dropdown menu item to the top button in CRM Analytics.
The specific placement code for the widget is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
CRM_ANALYTICS_TOOLBAR
Dropdown menu item of the top button in CRM Analytics
What the Handler Receives
What the Handler Receives
Data is sent as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => d3d342f98a82fc313fbfb1e9fe172163
[AUTH_ID] =>
1
f4fba6600631fcd00005a4b00000001f0f10702ea003068e6f5e38d8290cfcdfe300c
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
0
fcee16600631fcd00005a4b00000001f0f1070dfad25ad4247da6dcb566292a0da3f3
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CRM_ANALYTICS_TOOLBAR
)
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The Bitrix24 address where the widget handler was invoked
PROTOCOL
*
string
Secure or non-secure HTTP protocol:
0
- HTTP
1
- HTTPS
LANG
*
string
The user interface language of Bitrix24 that invoked the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who invoked the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who invoked the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was invoked.
status
string
Type of application that registered the handler for this widget. Accepts values:
L
-
local
application
F
-
free mass-market
application
PLACEMENT
*
string
Code for the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was invoked in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. For example, this could be an array containing the numeric identifier of the CRM entity in the detail form where the widget handler was invoked, etc. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific widget embedding location and object the widget handler was invoked.
Copied
PLACEMENT_OPTIONS
PLACEMENT_OPTIONS
In the current widget, the
PLACEMENT_OPTIONS
parameter is not passed.
Continue Your Exploration
Continue Your Exploration
Install Widget Handler placement.bind
Interaction with UI from Widgets
Interaction with CRM Card
Interactive Applications
Open a Slider with Your Interface
Open Standard Bitrix24 Pages from Application Widgets
Copied
Was the article helpful?
Yes
No
Previous
Item in the left menu of CRM analytics
Next
Context Menu Item in the List

---

