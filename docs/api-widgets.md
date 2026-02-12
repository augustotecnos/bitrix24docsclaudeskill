---
description: 'Widgets: Core methods, tasks, user fields, IM, telephony, calendar'
methods:
- app.info
- crm.company.get
- crm.contact.get
- crm.deal.get
- crm.item.get
- crm.lead.get
- crm.quote.get
- event.get
- placement.bind
- placement.get
- placement.list
- placement.unbind
- user.get
- userfieldconfig.add
pages: 47
title: 'Widgets: Core methods, tasks, user fields, IM, telephony, calendar'
---
# Widgets: Core methods, tasks, user fields, IM, telephony, calendar
> Widgets: Core methods, tasks, user fields, IM, telephony, calendar
> **47 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Widget Integration Mechanism](#widget-integration-mechanism)
- [Bitrix24 UI Kit: Building Interfaces That Speak the Same Language as the Platform](#bitrix24-ui-kit-building-interfaces-that-speak-the)
- [Principles of the Bitrix24 UI Kit Design](#principles-of-the-bitrix24-ui-kit-design)
- [Components and Templates](#components-and-templates)
- [Integration of UI Kit with REST API and Business Logic](#integration-of-ui-kit-with-rest-api-and-business-l)
- [Quick Start](#quick-start)
- [Typical use-cases and scenarios for embedding widgets](#typical-use-cases-and-scenarios-for-embedding-widg)
- [Widget Embedding Locations](#widget-embedding-locations)
- [Widgets in the LEFT_MENU Main Menu](#widgets-in-the-leftmenu-main-menu)
- [Context Menu Item of TASK_LIST_CONTEXT_MENU](#context-menu-item-of-tasklistcontextmenu)
- [Tab in the task card TASK_VIEW_TAB](#tab-in-the-task-card-taskviewtab)
- [Right Sidebar of the TASK_VIEW_SIDEBAR Card](#right-sidebar-of-the-taskviewsidebar-card)
- [Link in the top section of the task card TASK_VIEW_TOP_PANEL](#link-in-the-top-section-of-the-task-card-taskviewt)
- [Item of the main dropdown menu TASK_USER_LIST_TOOLBAR, TASK_GROUP_LIST_TOOLBAR](#item-of-the-main-dropdown-menu-taskuserlisttoolbar)
- [Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR](#main-dropdown-menu-item-near-the-automation-rule-s)
- [Main Dropdown Menu Item of the Project SONET_GROUP_DETAIL_TAB](#main-dropdown-menu-item-of-the-project-sonetgroupd)
- [Dropdown Menu Item Above the Task List TASK_GROUP_LIST_TOOLBAR](#dropdown-menu-item-above-the-task-list-taskgroupli)
- [Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR](#main-dropdown-menu-item-near-the-automation-rule-s)
- [Widgets in the user profile](#widgets-in-the-user-profile)
- [Context Menu Item in USER_PROFILE_MENU](#context-menu-item-in-userprofilemenu)
- [Context Menu Item for the Top Profile Button USER_PROFILE_TOOLBAR](#context-menu-item-for-the-top-profile-button-userp)
- [Widget in the CALENDAR_GRIDVIEW](#widget-in-the-calendargridview)
- [Call Card Tab CALL_CARD](#call-card-tab-callcard)
- [Menu Item in Call Analytics TELEPHONY_ANALYTICS_MENU](#menu-item-in-call-analytics-telephonyanalyticsmenu)
- [WebRTC](#webrtc)
- [Icon of the Left Menu IM_NAVIGATION](#icon-of-the-left-menu-imnavigation)
- [Widget Above the IM_TEXTAREA Message](#widget-above-the-imtextarea-message)
- [Widget for the IM_SIDEBAR](#widget-for-the-imsidebar)
- [IM_CONTEXT_MENU Message Context Menu Item](#imcontextmenu-message-context-menu-item)
- [Collection of Emojis IM_SMILES_SELECTOR](#collection-of-emojis-imsmilesselector)
- [Widget in the CONTACT_CENTER](#widget-in-the-contactcenter)
- [Universal Widgets](#universal-widgets)
- [Widget as a Link with Slider REST_APP_URI](#widget-as-a-link-with-slider-restappuri)
- [Invisible Widget on Every Page PAGE_BACKGROUND_WORKER](#invisible-widget-on-every-page-pagebackgroundworke)
- [Embedding in the Bitrix24 Mobile Application](#embedding-in-the-bitrix24-mobile-application)
- [Install Widget Handler placement.bind](#install-widget-handler-placementbind)
- [Get a list of registered widget placement handlers placement.get](#get-a-list-of-registered-widget-placement-handlers)
- [Retrieving a List of Available Placement Options for the Application](#retrieving-a-list-of-available-placement-options-f)
- [Removing a Registered Placement Handler](#removing-a-registered-placement-handler)
- [Open Standard Bitrix24 Pages from Application Widgets](#open-standard-bitrix24-pages-from-application-widg)
- [Open a Slider with Your Interface](#open-a-slider-with-your-interface)
- [Bitrix24 REST API and Marketplace Applications](#bitrix24-rest-api-and-marketplace-applications)
- [Overview of Methods](#overview-of-methods)
- [Register a new user field type userfieldtype.add](#register-a-new-user-field-type-userfieldtypeadd)
- [Change settings for user field type userfieldtype.update](#change-settings-for-user-field-type-userfieldtypeu)
- [Get a list of registered user field types userfieldtype.list](#get-a-list-of-registered-user-field-types-userfiel)
- [Delete Registered User Field Type userfieldtype.delete](#delete-registered-user-field-type-userfieldtypedel)

---

## Widget Integration Mechanism

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/index

Widget Integration Mechanism | Bitrix24 REST API and Marketplace Applications
Basic Widget in the Left Menu
Widget Integration Mechanism
Basic Widget in the Left Menu
How Other Integrations Work
Special Widgets - Custom Field Types in CRM Cards
Opening Standard and Custom Sliders from Widget Interfaces
Interacting with the Bitrix24 UI from Widgets
Benefits of Using Widgets
The REST API allows you to add your functionality to Bitrix24 in the form of widgets in various places of the user interface - in the main menu of the account, in the item list menus, in CRM and task cards, etc.
Basic Widget in the Left Menu
Basic Widget in the Left Menu
This is the simplest integration, which is done not even through the REST API, but through the settings of a local or mass-market application.
In the case of a
local application
, specify the name of the menu item:
Clicking on this item will open a slider with the application in the form of a frame, into which the URL you specified as the main one in the local application settings will be inserted.
In the case of
mass-market solutions
hosted in the Developer's area, you need to do two things:
In the version card, specify the option "Add your page and item to the main menu"
In the description in the required language, specify the value in the "Application name in the menu" field
How Other Integrations Work
How Other Integrations Work
Unlike the integration of the left menu slider with the main URL of the application,
all other widgets
are integrated differently - using the
placement.bind
method.
Special Widgets - Custom Field Types in CRM Cards
Special Widgets - Custom Field Types in CRM Cards
You can create your own interfaces for displaying and editing fields in CRM cards (in leads, deals, etc.). This can be an interface with geo-maps, sets of informers, or industry data. In fact, Bitrix24 will be responsible for saving field values, while the interface for displaying these values is fully implemented by the applications.
To use this scenario, you need to register
custom field types
. These are not the fields themselves, but the types. Later, either the user through standard CRM interfaces or your application using REST methods can add fields of these types and use your editing interface for such fields.
Opening Standard and Custom Sliders from Widget Interfaces
Opening Standard and Custom Sliders from Widget Interfaces
Often, from the widget interfaces, it is necessary to
open standard pages
of Bitrix24. This could be, for example, a slider with a contact card or a slider with the required task.
In addition to standard sliders, solution developers have the opportunity to display
their custom interfaces in a slider
. For example, this could be your card for viewing a document, a slider with application settings, a slider with a report, etc. You will be able to customize the appearance of such a slider.
Interacting with the Bitrix24 UI from Widgets
Interacting with the Bitrix24 UI from Widgets
For some scenarios, it is necessary for developers to access certain Bitrix24 capabilities directly from the frontend of their widgets.
First of all, this is, of course, the ability to make direct calls to REST methods. Secondly, there are special methods implemented only for specific types of widgets. In particular,
in the
call card
in the
WebRTC scenario
in the
CRM card
Benefits of Using Widgets
Benefits of Using Widgets
We highly recommend using widget integrations in the user interface to implement convenient user scenarios. This provides developers with a number of advantages:
Users will receive your functionality exactly where it needs to be used. For example, if your application provides users with additional information about deals, it is most convenient for users to receive this information when they are already in the relevant deal.
User scenarios with widgets are easier to program. Returning to the previous example: if your application provides additional information about a specific deal, integrating it into the deal card will save you from having to create your own interface with a list of deals in your application. After all, the user already has a great opportunity to find the necessary deal in the CRM interface. You just need to focus on your unique functionality.
If you have developed a mass-market application with widgets, the Market showcase will offer your solution to clients in the widget integration places you used. You will receive more targeted and quality traffic, which means better conversion to installations of your applications.
It is also recommended to use the
openPath
method to show users standard Bitrix24 objects, and the
openApplication
method to simplify user scenarios within your application. Users are accustomed to the pattern where additional information or details about something are displayed in a slider over the previous interface.
You should use
openApplication
:
To show the settings form of your application instead of popup windows inside the application frame
To show various detail forms of your application's objects (viewing an external document, detailed information about an order, etc.)
For forms of adding and editing (for example, for forms to fill out a request, adding a real estate object, etc.)
This approach will save you from a number of problems:
Due to security-related restrictions in browsers, implementing single-page applications in an iframe is quite labor-intensive. Opening separate sliders using the
openApplication
call mitigates this complexity, as Bitrix24 itself transmits the necessary authorization tokens and "context" in the form of your custom parameters to the slider.
Any iframe has a limited size visible to the user. It is impossible to show any popup window inside an iframe that is larger than the iframe itself. Moreover, such an attempt causes scrollbars to appear at the edges of the iframe. This is inconvenient and unattractive. Calling a slider over the interface completely resolves these issues.
In summary, we strongly recommend exploring the use of openPath and openApplication for creating simple, convenient, and functional solutions for Bitrix24.
Copied
Was the article helpful?
Yes
No
Previous
Confirmation methods
Next
UI Kit - interface, unified with the platform

---

## Bitrix24 UI Kit: Building Interfaces That Speak the Same Language as the Platform

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-kit/index

Bitrix24 UI Kit: Building Interfaces That Speak the Same Language as the Platform | Bitrix24 REST API and Marketplace Applications
Bitrix24 UI Kit: Building Interfaces That Speak the Same Language as the Platform
Bitrix24 UI Kit: Building Interfaces That Speak the Same Language as the Platform
What Will Using the UI Kit Give You?
Who Is This For?
Creating an interface is not just about choosing buttons and colors. It's about whether the user feels that your application is
part of Bitrix24
, rather than something foreign squeezed into an iframe.
Bitrix24 UI Kit
is a library of components and design patterns created to:
make your interfaces look and feel
natural
within the Bitrix24 ecosystem,
allow you to focus on business logic instead of reinventing the wheel with CSS,
and ensure that applications—from internal CRM tools to public solutions in the marketplace—remain consistent, predictable, and user-friendly.
If you are developing an application for Bitrix24, you
don’t need
to worry about pixels, margins, and shadows. That’s already been taken care of for you. Instead, you work with ready-made components that are similar to those used by the platform itself.
What Will Using the UI Kit Give You?
What Will Using the UI Kit Give You?
Quick Start.
Connect the UI Kit and immediately gain access to buttons, modal windows, forms, tabs, lists, and dozens of other components.
Consistency.
Your application will "speak" to the user in the same visual language as the entire Bitrix24.
Recognition.
Applications developed using the UI Kit pass moderation faster and are valued higher by users.
Reliability.
UI Kit components are constantly used and tested—this means fewer bugs, fewer CSS hacks, and more confidence in the outcome.
Who Is This For?
Who Is This For?
Developers creating internal corporate applications on Bitrix24.
Teams working on solutions for the Marketplace.
Bitrix24 Partners adapting interfaces to meet client needs.
Anyone who wants to write less UI code and achieve more results.
Was the article helpful?
Yes
No
Previous
Widget embedding mechanism
Next
Design principles

---

## Principles of the Bitrix24 UI Kit Design

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-kit/design

Principles of the Bitrix24 UI Kit Design | Bitrix24 REST API and Marketplace Applications
1. Consistency
Principles of the Bitrix24 UI Kit Design
1. Consistency
2. Adaptability and Scalability
3. Inclusivity and Accessibility
4. Simplicity
5. Component-Based
6. Brand Identity
The Bitrix24 UI Kit is built on the idea of
interface affinity
: any application using the UI Kit should look and feel like a continuation of the Bitrix24 platform, rather than an external service embedded via iframe.
Key principles underlying the library:
1. Consistency
1. Consistency
Interface patterns should be recognizable and predictable for Bitrix24 users. This means:
uniform margins, sizes, and grids,
repeated interaction logic,
unified colors and typography.
Users should feel "at home," regardless of which section of the platform they are in.
2. Adaptability and Scalability
2. Adaptability and Scalability
Components function correctly on different screens—from laptops to embedded panels in mobile applications.
Components use fluid sizes.
Adaptability is set declaratively through Tailwind utility classes, without manual media queries.
There is an option to define adaptive behavior directly in the template.
3. Inclusivity and Accessibility
3. Inclusivity and Accessibility
All components are developed with basic accessibility requirements in mind:
proper HTML semantics,
support for keyboard navigation,
clear focus and aria attributes,
compatibility with dark mode.
4. Simplicity
4. Simplicity
The simpler the interface, the less cognitive load on the user, and the easier it is for the developer to assemble a ready screen:
minimal unnecessary information,
logical hierarchy,
reasonable defaults and "out-of-the-box" behavior.
5. Component-Based
5. Component-Based
Everything in the UI Kit is built as a set of independent Vue components that can be used individually or assembled into templates.
Clear isolation.
Extensibility through props/slots.
Combinability based on the Lego principle.
6. Brand Identity
6. Brand Identity
The UI Kit adheres to the visual language of Bitrix24—colors, icons, button shapes, notification logic, and more align with the style of the main platform.
This is not just a library; it is an extension of the Bitrix24 interface in your applications.
Was the article helpful?
Yes
No
Previous
UI Kit - interface, unified with the platform
Next
Components

---

## Components and Templates

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-kit/components

Components and Templates | Bitrix24 REST API and Marketplace Applications
Categories of Components
Components and Templates
Categories of Components
Component Approach
Default Behavior
The Bitrix24 UI Kit is a library of
design-consistent components
that can be combined, extended, and adapted for specific tasks. The main goal is to accelerate development and ensure uniformity of interfaces across all applications integrated into Bitrix24.
Categories of Components
Categories of Components
UI Kit components are grouped into meaningful categories:
Actions
— buttons, dropdowns, modals, sliders
Notifications
— alerts, toasts, tooltips, progress bars
Information Display
— avatars, badges, icons, calendars, tables
Data Input
— inputs, selectors, checkboxes, radio buttons
Navigation
— menus, tabs, links
For a complete list of available components, see the
detailed documentation
.
Component Approach
Component Approach
All components:
are built on the principle of
composition
— easily combine with each other,
work with theming
— external styling can be adjusted for light/dark themes,
are
responsive
— look good on different resolutions,
are
extensible
— through
slots
and
props
.
You can assemble interfaces from ready-made parts without the need to manually describe visual styles.
Default Behavior
Default Behavior
The UI Kit implements behavior that Bitrix24 users are accustomed to:
margins, alignment, grids — as in the main platform,
logic for opening/closing modals, dropdowns, and popups — identical to platform behavior,
keyboard interaction and focus management — according to accessibility standards.
This eliminates the need to "guess" how a component should behave — everything is already aligned with Bitrix24's UX patterns.
Copied
Was the article helpful?
Yes
No
Previous
Design principles
Next
Integration with REST API and business logic

---

## Integration of UI Kit with REST API and Business Logic

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-kit/app-logic

Integration of UI Kit with REST API and Business Logic | Bitrix24 REST API and Marketplace Applications
How It Used to Be
Integration of UI Kit with REST API and Business Logic
How It Used to Be
What Has Changed
What Remains the Same
Where Is the Logic Now?
What If I Don’t Know Vue?
Transitioning to the new UI Kit may raise questions for developers, especially if you have previously created applications for Bitrix24 using PHP or utilized
BX24.js
in static HTML pages. In this section, we will explain how the approach to building interfaces has changed, what remains the same, and how the connection between the visual part of the UI Kit and the Bitrix24 REST API now works.
How It Used to Be
How It Used to Be
If you have already written applications for Bitrix24, you are familiar with the scheme:
the interface is created using PHP, HTML, and Bootstrap,
a generated markup is displayed within an iframe,
data is loaded using
BX24.callMethod()
from
BX24.js
,
REST requests were made directly from the browser or through PHP "before" the page was rendered.
This approach worked and continues to work, but it has its limitations:
the interface cannot be reused,
it is difficult to implement states: loading, errors, interactions,
CSS often had to be written manually for each screen,
everything is "in your hands": you draw a table — you also update it.
What Has Changed
What Has Changed
Vue
has introduced a
reactive approach
: now you do not manage the DOM directly. Instead, you describe
what should be visible on the screen
, and Vue takes care of monitoring the state of the data and updating the interface when it changes.
A simple example:
<
script
setup
>
import
{ ref }
from
'vue'
;
const
count =
ref
(
0
);
</
script
>
<
template
>
<
button
@
click
=
"count++"
>
Clicked {{ count }} times
</
button
>
</
template
>
The value of
count
is a reactive variable. With each click, the value updates, and the interface automatically re-renders. You do not need to manually change the HTML — Vue does it for you.
With the UI Kit, you get ready-made Vue components that implement all the visual logic for you:
buttons, forms, tables, layouts, modal windows,
components are responsive and match the Bitrix24 style,
you work not with HTML and styles, but with declarative components,
the REST API is now called within the Vue application using fetch() or axios.
However, the REST API remains the same. Methods, parameters, authorization — everything works just like in BX24.js or PHP.
What Remains the Same
What Remains the Same
All REST API methods work exactly the same.
You can call the API from the frontend or from your backend server.
Authorization: OAuth 2.0, webhook — everything remains.
The application still runs inside an iframe.
Where Is the Logic Now?
Where Is the Logic Now?
Here’s how the roles are now divided:
Responsibility
Used to be PHP + BX24.js
Now Vue + UI Kit
Layout
PHP template
UI Kit Vue components
REST request
BX24.callMethod()
axios, fetch, useAsyncData
Result handling
JS manually
Vue reactive variables
Table and other interface elements
HTML + Bootstrap
Bitrix24 UI Kit components
What If I Don’t Know Vue?
What If I Don’t Know Vue?
That’s okay. You don’t need to know all of Vue to start working:
UI Kit components encapsulate behavior,
project structure with Vite or Nuxt is simple,
it’s enough to understand how to pass data and handle events.
You can start by copying examples and gradually figure it out. Additionally, you can use only design tokens and icons if you prefer to stick with HTML + Tailwind CSS for now. However, you won’t gain all the benefits of the UI Kit.
Copied
Was the article helpful?
Yes
No
Previous
Components
Next
Quick start

---

## Quick Start

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/ui-kit/quick-start

Quick Start | Bitrix24 REST API and Marketplace Applications
Level 1: Full Integration via Vue
Quick Start
Level 1: Full Integration via Vue
Why Nuxt?
Why Vite?
Level 2: Design Tokens Only
Why Tailwind CSS?
Icons
Starting a Project with Nuxt
Starting a Project with Vite
The Bitrix24 UI Kit is not just a component library. It is a
multi-layered system
that allows you to adapt the visual style of Bitrix24 depending on
how deeply you want to integrate
and what stack you are using.
You can use the UI Kit as:
A full-fledged
Vue component library
, which we recommend.
A source of
design tokens
on Tailwind CSS and additionally an
icon library
compatible with any frontend stack.
Level 1: Full Integration via Vue
Level 1: Full Integration via Vue
If you are using
Vue 3
— you get the most: ready-made components fully styled in the Bitrix24 style, with support for themes, responsiveness, customization, and UX logic tested on millions of users.
You can choose one of two options to start your project:
Nuxt 3
— ideal for SSR, multi-page applications, and quick integration with the Bitrix24 infrastructure.
Vite
— simplicity, speed, and ease for SPA and microservices architecture.
We support both options. Choose the one that fits your needs.
Why Nuxt?
Why Nuxt?
Great for applications with navigation, localization, and modular structure.
SSR/SSG out of the box — performance is well-handled.
Support for middleware, layouts, and composables.
Why Vite?
Why Vite?
Lightning-fast start and dev server.
Simple configuration.
Perfect for embedded widgets, single-page applications, and microfrontend projects.
Level 2: Design Tokens Only
Level 2: Design Tokens Only
If you are not using Vue but still want your interface to look
like native Bitrix24
— use our
design tokens
system implemented as a
Tailwind CSS
plugin.
Design tokens include:
Bitrix24 color palette, including light and dark themes,
typography,
spacing, sizes, borders,
ready-to-use utilities for Bitrix24 UI patterns.
Why Tailwind CSS?
Why Tailwind CSS?
Tailwind CSS provides a powerful and flexible way to
describe the interface through classes
, without the need to write CSS manually.
Easy integration into any stack: React, Vue, Svelte, even jQuery.
Ability for rapid prototyping and scaling of components.
Used by thousands of teams.
Note
Our plugin is a shortcut to creating interfaces in the Bitrix24 style, even if you are not using our UI Kit on Vue.
Icons
Icons
Do you only need icons in the Bitrix24 brand style? Connect
@bitrix24/icons
— and use SVG icons in any framework. All icons are optimized and available through CSS classes or as Vue/React components.
Starting a Project with Nuxt
Starting a Project with Nuxt
The easiest and most correct way to start a project using Nuxt 3 is to use a "template" that includes all necessary dependencies and settings. Detailed descriptions and examples can be found in the
documentation
.
Starting a Project with Vite
Starting a Project with Vite
Similarly to the "template" for Nuxt, you can use the option for Vite. It also includes all necessary dependencies and settings. Detailed descriptions and examples can be found in the
documentation
.
Copied
Was the article helpful?
Yes
No
Previous
Integration with REST API and business logic
Next
Typical use-cases

---

## Typical use-cases and scenarios for embedding widgets

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/tutorials

Typical use-cases and scenarios for embedding widgets | Bitrix24 REST API and Marketplace Applications
Left Menu
Typical use-cases and scenarios for embedding widgets
Left Menu
Widgets in CRM
Widgets in Automation rules
Left Menu
Left Menu
Application with its own page in the left menu
Widgets in CRM
Widgets in CRM
Embed a widget in a lead as a custom property
Embed a widget in a CRM detail form
Widgets in Automation rules
Widgets in Automation rules
How to Embed Your UI in Robot Parameters
Was the article helpful?
Yes
No
Previous
Quick start
Next
Places for widget embedding

---

## Widget Embedding Locations

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/placements

Widget Embedding Locations | Bitrix24 REST API and Marketplace Applications
Widget Embedding Locations
Widget Embedding Locations
Almost every tool in Bitrix24 has locations for embedding widgets.
Each application can register an unlimited number of widgets, even of the same type, as long as the embedding location allows it. For example, one application can add multiple tabs to a deal's detail form. Or several items to the dropdown context menu in the task list, and so on.
CRM
Custom Field Types in CRM
Tasks
Workgroups/Projects
User Profile
Calendar
Telephony
Messenger
Contact Center
Universal Widgets
Was the article helpful?
Yes
No
Previous
Typical use-cases
Next
Widgets in the main menu

---

## Widgets in the LEFT_MENU Main Menu

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/left-menu

Widgets in the LEFT_MENU Main Menu | Bitrix24 REST API and Marketplace Applications
Widgets in the LEFT_MENU Main Menu
Widgets in the LEFT_MENU Main Menu
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue your study
Scope:
basic
You can add your item to the main menu of the account.
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
LEFT_MENU
Item in the main menu of the account
What the handler receives
What the handler receives
Data is transmitted as a POST request
Array
(
[handler] =>
1
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => fea0d7bc24669fcb8807e88ee394c7ca
[AUTH_ID] =>
63
d39f6600631fcd00005a4b00000001f0f1071905299b72b307a6c223d43877697546
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
5352
c76600631fcd00005a4b00000001f0f107d262f083bb53a16948269371e327d1d9
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => LEFT_MENU
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
Typical use-cases and scenarios
Application with its own page in the left menu
Continue your study
Continue your study
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
Places for widget embedding
Next
Context menu item in the list of entities

---

## Context Menu Item of TASK_LIST_CONTEXT_MENU

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/task/index

Context Menu Item of TASK_LIST_CONTEXT_MENU | Bitrix24 REST API and Marketplace Applications
Context Menu Item of TASK_LIST_CONTEXT_MENU
Context Menu Item of TASK_LIST_CONTEXT_MENU
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
task
You can add your own context menu item to the list.
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
TASK_LIST_CONTEXT_MENU
Context menu item of the list
What the handler receives
What the handler receives
Data is sent as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => d7092a1d8c53d8be01cbb43a856e21ac
[AUTH_ID] => cb50ba6600631fcd00005a4b00000001f0f107523405e8ed8e45f3a87951e6313d42ac
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => bbcfe16600631fcd00005a4b00000001f0f1078b3cbb2ae3909b492b397f73c3966d59
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TASK_LIST_CONTEXT_MENU
[PLACEMENT_OPTIONS] => {
"ID"
:
"286"
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
The identifier of the task for which the widget was opened.
It can be used to retrieve additional information using the
tasks.task.get
method.
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
Dropdown menu item of the top button in CRM analytics
Next
Tab in the Task Detail Form

---

## Tab in the task card TASK_VIEW_TAB

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/task/view-tab

Tab in the task card TASK_VIEW_TAB | Bitrix24 REST API and Marketplace Applications
Tab in the task card TASK_VIEW_TAB
Tab in the task card TASK_VIEW_TAB
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
task
You can add your item in the right panel of the old task detail form.
Starting from version
tasks 25.700.0
, a
new task card
has been released. The location of the
TASK_VIEW_TAB
item is no longer present in the new card. All widgets within the card are displayed in a single Applications block.
Previously registered
TASK_VIEW_TAB
items continue to function and are displayed in the Applications block.
The specific placement code for the widget is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget code
Location
TASK_VIEW_TAB
Tab in the task card
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
0063
a02ba25315469678f946ece50010
[AUTH_ID] =>
9
c52ba6600705a0700005a4b00000001f0f107e81691773d119eb941ad045e362fcb2a
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
8
cd1e16600705a0700005a4b00000001f0f1070aef2cbe270a6f27bcaf791e454e1047
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TASK_VIEW_TAB
[PLACEMENT_OPTIONS] => {
"taskId"
:
"286"
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
taskId
*
string
The identifier of the task for which the widget was opened.
It can be used to retrieve additional information using the
tasks.task.get
method.
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
Context Menu Item in the List
Next
Right Panel of the Task Detail Form

---

## Right Sidebar of the TASK_VIEW_SIDEBAR Card

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/task/view-sidebar

Right Sidebar of the TASK_VIEW_SIDEBAR Card | Bitrix24 REST API and Marketplace Applications
Right Sidebar of the TASK_VIEW_SIDEBAR Card
Right Sidebar of the TASK_VIEW_SIDEBAR Card
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Exploring
Scope:
task
You can add your item in the right panel of the old task detail form.
Starting from version
tasks 25.700.0
, a
new task card
has been released. The location of the
TASK_VIEW_SIDEBAR
item is no longer present in the new card. All widgets within the card are displayed in a single Applications block.
Previously registered
TASK_VIEW_SIDEBAR
items continue to function and are displayed in the Applications block.
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
TASK_VIEW_SIDEBAR
Item in the right sidebar of the task card
What the Handler Receives
What the Handler Receives
Data is sent as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
84986
ed8551be43c882fc720b8e406e3
[AUTH_ID] =>
9e52
ba6600705a0700005a4b00000001f0f1076fce1ae9b9c15bf669f414769c1eb700
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
8
ed1e16600705a0700005a4b00000001f0f10706b7d2b53d9a0e08c50eb4b620b50d9a
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TASK_VIEW_SIDEBAR
[PLACEMENT_OPTIONS] => {
"taskId"
:
"286"
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
taskId
*
string
The identifier of the task for which the widget was opened.
It can be used to retrieve additional information using the
tasks.task.get
method.
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
Tab in the Task Detail Form
Next
Link at the Top of the Task Detail Form

---

## Link in the top section of the task card TASK_VIEW_TOP_PANEL

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/task/view-top-panel

Link in the top section of the task card TASK_VIEW_TOP_PANEL | Bitrix24 REST API and Marketplace Applications
Link in the top section of the task card TASK_VIEW_TOP_PANEL
Link in the top section of the task card TASK_VIEW_TOP_PANEL
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
task
You can add your item in the right panel of the old task detail form.
Starting from version
tasks 25.700.0
, a
new task card
has been released. The location of the
TASK_VIEW_TOP_PANEL
item is no longer present in the new card. All widgets within the card are displayed in a single Applications block.
Previously registered
TASK_VIEW_TOP_PANEL
items continue to function and are displayed in the Applications block.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget code
Location
TASK_VIEW_TOP_PANEL
Item in the top section of the task card
What the handler receives
What the handler receives
Data is sent as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => dac3aa71afd1a1fd8bef05a282dd0b20
[AUTH_ID] =>
3153
ba6600705a0700005a4b00000001f0f107fd2c2625abb62bad95fe9b37a0d1fbb6
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
21
d2e16600705a0700005a4b00000001f0f10707ca46d62b79fcd8d19a8c614e621226
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TASK_VIEW_TOP_PANEL
[PLACEMENT_OPTIONS] => {
"TASK_ID"
:
"286"
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
TASK_ID
*
string
The identifier of the task for which the widget was opened.
It can be used to retrieve additional information using the
tasks.task.get
method.
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
Right Panel of the Task Detail Form
Next
Main Dropdown Menu Item

---

## Item of the main dropdown menu TASK_USER_LIST_TOOLBAR, TASK_GROUP_LIST_TOOLBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/task/list-toolbar

Item of the main dropdown menu TASK_USER_LIST_TOOLBAR, TASK_GROUP_LIST_TOOLBAR | Bitrix24 REST API and Marketplace Applications
Item of the main dropdown menu TASK_USER_LIST_TOOLBAR, TASK_GROUP_LIST_TOOLBAR
Item of the main dropdown menu TASK_USER_LIST_TOOLBAR, TASK_GROUP_LIST_TOOLBAR
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
intranet
You can add your item to the main dropdown menu in user and group tasks.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget code
Location
TASK_USER_LIST_TOOLBAR
Item in the main dropdown menu in user tasks
TASK_GROUP_LIST_TOOLBAR
Item in the main dropdown menu in group tasks
What the handler receives
What the handler receives
Data is transmitted as a POST request
TASK_USER_LIST_TOOLBAR
TASK_GROUP_LIST_TOOLBAR
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
4617
fa96af5d1f523fc2e2b72bd54f11
[AUTH_ID] =>
5253
ba6600705a0700005a4b00000001f0f1076fef51e6d3d3c1616a9fd92a714ca452
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
42
d2e16600705a0700005a4b00000001f0f107cf69d8060249da353587f8ec862be702
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TASK_USER_LIST_TOOLBAR
[PLACEMENT_OPTIONS] => {
"USER_ID"
:
"1"
}
)
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
9
f3b397a4bc09ad1ee9b7a5db991a603
[AUTH_ID] => cc53ba6600705a0700005a4b00000001f0f107e316cd1ed3be4be6856b7077e180656c
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => bcd2e16600705a0700005a4b00000001f0f1075b826a128425efbda11902d7f5d78062
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TASK_GROUP_LIST_TOOLBAR
[PLACEMENT_OPTIONS] => {
"GROUP_ID"
:
"10"
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
USER_ID
*
string
The identifier of the user whose task list the widget was opened over.
Can be used to retrieve additional information using the
user.get
method.
GROUP_ID
*
string
The identifier of the workgroup/project whose task list the widget was opened over.
Can be used to retrieve additional information using the
sonet.group.get
method.
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
Link at the Top of the Task Detail Form
Next
Main Dropdown Menu Item near Automation Rules Settings

---

## Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/task/robot-designer-toolbar

Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR | Bitrix24 REST API and Marketplace Applications
Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR
Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
intranet
You can add your own main dropdown menu item near the Automation rule settings in tasks.
The code for the specific widget placement is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget code
Location
TASK_ROBOT_DESIGNER_TOOLBAR
Main dropdown menu item near the Automation rule settings
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
4617
fa96af5d1f523fc2e2b72bd54f11
[AUTH_ID] =>
5253
ba6600705a0700005a4b00000001f0f1076fef51e6d3d3c1616a9fd92a714ca452
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
42
d2e16600705a0700005a4b00000001f0f107cf69d8060249da353587f8ec862be702
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TASK_USER_LIST_TOOLBAR
[PLACEMENT_OPTIONS] => {
"USER_ID"
:
"1"
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
USER_ID
*
string
The user ID in whose Automation rule settings the widget was opened.
Can be used to retrieve additional information using the
user.get
method.
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
Main Dropdown Menu Item
Next
Main Dropdown Menu Item of the Project

---

## Main Dropdown Menu Item of the Project SONET_GROUP_DETAIL_TAB

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/workgroups/index

Main Dropdown Menu Item of the Project SONET_GROUP_DETAIL_TAB | Bitrix24 REST API and Marketplace Applications
Main Dropdown Menu Item of the Project SONET_GROUP_DETAIL_TAB
Main Dropdown Menu Item of the Project SONET_GROUP_DETAIL_TAB
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Exploring
Scope:
workgroups
You can add your own item to the main dropdown menu of the project.
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
SONET_GROUP_DETAIL_TAB
Main Dropdown Menu Item of the Project
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
3
c900e588b941b81eef07608e4253159
[AUTH_ID] =>
1
a55ba6600705a0700005a4b00000001f0f107db29f044c6ff24e984d378967134de83
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
0
ad4e16600705a0700005a4b00000001f0f10731fce9fa3219163d545a088b217cc2d4
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => SONET_GROUP_DETAIL_TAB
[PLACEMENT_OPTIONS] => {
"GROUP_ID"
:
"10"
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
GROUP_ID
*
string
Identifier of the workgroup/project in which the widget was opened.
It can be used to retrieve additional information using the
sonet.group.get
method.
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
Main Dropdown Menu Item near Automation Rules Settings
Next
Dropdown Menu Item Above the Task List

---

## Dropdown Menu Item Above the Task List TASK_GROUP_LIST_TOOLBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/workgroups/toolbar

Dropdown Menu Item Above the Task List TASK_GROUP_LIST_TOOLBAR | Bitrix24 REST API and Marketplace Applications
Dropdown Menu Item Above the Task List TASK_GROUP_LIST_TOOLBAR
Dropdown Menu Item Above the Task List TASK_GROUP_LIST_TOOLBAR
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue Exploring
Scope:
intranet
You can add your dropdown menu item above the project task list.
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
TASK_GROUP_LIST_TOOLBAR
Dropdown menu item above the task list
What the handler receives
What the handler receives
Data is transmitted as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
25e596577
c2a1ddf98c7863421330527
[AUTH_ID] =>
5
d56ba6600705a0700005a4b00000001f0f107d21c0babb82529a32836e165141a2010
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
4
dd5e16600705a0700005a4b00000001f0f107a934a327935855b75f8c3686204e3bd5
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TASK_ROBOT_DESIGNER_TOOLBAR
[PLACEMENT_OPTIONS] => {
"GROUP_ID"
:
"10"
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
GROUP_ID
*
string
Identifier of the workgroup/project in which the widget was opened.
It can be used to retrieve additional information using the
sonet.group.get
method.
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
Main Dropdown Menu Item of the Project
Next
Main Dropdown Menu Item Next to Automation Rules Settings

---

## Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/workgroups/robot-designer-toolbar

Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR | Bitrix24 REST API and Marketplace Applications
Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR
Main dropdown menu item near the Automation rule settings TASK_ROBOT_DESIGNER_TOOLBAR
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
intranet
You can add your main dropdown menu item near the Automation rule settings in workgroups.
The code for the specific widget placement is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget code
Location
TASK_ROBOT_DESIGNER_TOOLBAR
Main dropdown menu item near the Automation rule settings
What the handler receives
What the handler receives
Data is transmitted as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] =>
25e596577
c2a1ddf98c7863421330527
[AUTH_ID] =>
5
d56ba6600705a0700005a4b00000001f0f107d21c0babb82529a32836e165141a2010
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
4
dd5e16600705a0700005a4b00000001f0f107a934a327935855b75f8c3686204e3bd5
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TASK_ROBOT_DESIGNER_TOOLBAR
[PLACEMENT_OPTIONS] => {
"GROUP_ID"
:
"10"
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
GROUP_ID
*
string
Identifier of the workgroup/project in which the widget was opened.
Can be used to obtain additional information using the
sonet.group.get
method.
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
Dropdown Menu Item Above the Task List
Next
Widgets in User Profile

---

## Widgets in the user profile

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/user-profile/index

Widgets in the user profile | Bitrix24 REST API and Marketplace Applications
Widgets in the user profile
Widgets in the user profile
Context Menu Item in USER_PROFILE_MENU
Context Menu Item for the Top Profile Button USER_PROFILE_TOOLBAR
Was the article helpful?
Yes
No
Previous
Main Dropdown Menu Item Next to Automation Rules Settings
Next
Context Menu Item in Profile

---

## Context Menu Item in USER_PROFILE_MENU

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/user-profile/profile-menu

Context Menu Item in USER_PROFILE_MENU | Bitrix24 REST API and Marketplace Applications
Context Menu Item in USER_PROFILE_MENU
Context Menu Item in USER_PROFILE_MENU
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue your exploration
Scope:
user
You can add your item to the context menu in the profile.
The specific widget placement code is specified in the
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
USER_PROFILE_MENU
Context menu item in the profile
What the handler receives
What the handler receives
Data is transmitted as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => bbdb976c9f5d067b1d48d102ab17b995
[AUTH_ID] => ae70bb6600705a0700005a4b00000001f0f107ab19f75f907d2320df1129aa61f63efc
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
9
eefe26600705a0700005a4b00000001f0f1078586205803785eca5262f6ff48e025ee
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => USER_PROFILE_MENU
[PLACEMENT_OPTIONS] => {
"USER_ID"
:
"1"
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
USER_ID
*
string
The identifier of the user whose profile the widget was opened in.
This can be used to retrieve additional information using the
user.get
method.
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
Widgets in User Profile
Next
Context Menu Item in Profile Top Button

---

## Context Menu Item for the Top Profile Button USER_PROFILE_TOOLBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/user-profile/profile-toolbar

Context Menu Item for the Top Profile Button USER_PROFILE_TOOLBAR | Bitrix24 REST API and Marketplace Applications
Context Menu Item for the Top Profile Button USER_PROFILE_TOOLBAR
Context Menu Item for the Top Profile Button USER_PROFILE_TOOLBAR
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Exploring
Scope:
user
You can add your item to the context menu of the top profile button.
The code for the specific widget placement is specified in the
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
USER_PROFILE_TOOLBAR
Context menu item of the top profile button
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
8
cd7740e289bf14997dd7e5e20cf6d13
[AUTH_ID] => dc70bb6600705a0700005a4b00000001f0f1079c18b7c3d0497a2cf769e3c4d1150a9b
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => ccefe26600705a0700005a4b00000001f0f107961459d1f9ac07ba82616c72079ede7b
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => USER_PROFILE_TOOLBAR
[PLACEMENT_OPTIONS] => {
"USER_ID"
:
"1"
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
USER_ID
*
string
The identifier of the user whose profile the widget was opened in.
It can be used to retrieve additional information using the
user.get
method.
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
Context Menu Item in Profile
Next
Widget in calendar

---

## Widget in the CALENDAR_GRIDVIEW

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/calendar

Widget in the CALENDAR_GRIDVIEW | Bitrix24 REST API and Marketplace Applications
Widget in the CALENDAR_GRIDVIEW
Widget in the CALENDAR_GRIDVIEW
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
calendar
You can add your item to the list of calendar view types.
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget code
Location
CALENDAR_GRIDVIEW
Item in the list of calendar view types
What the handler receives
What the handler receives
Data is sent as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => b4f4b92b5178b5a5276e181ca09d25a7
[AUTH_ID] => be56ba6600705a0700005a4b00000001f0f107e5806d5fe9a98e02021a72e57645f86a
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => aed5e16600705a0700005a4b00000001f0f107a80816604b24a8719792ac2a21d629b5
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CALENDAR_GRIDVIEW
[PLACEMENT_OPTIONS] => {
"viewRangeFrom"
:
"2024-08-12"
,
"viewRangeTo"
:
"2024-08-18"
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
viewRangeFrom
*
date
The start of the date range currently displayed in the calendar.
Can be used to retrieve a list of events to display in the widget using the
calendar.event.get
method.
viewRangeTo
*
date
The end of the date range currently displayed in the calendar.
Can be used to retrieve a list of events to display in the widget using the
calendar.event.get
method.
Continue exploring
Continue exploring
How to Embed an Application in the CALENDAR_GRIDVIEW
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
Context Menu Item in Profile Top Button
Next
Tab in the Call Detail

---

## Call Card Tab CALL_CARD

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/telephony/index

Call Card Tab CALL_CARD | Bitrix24 REST API and Marketplace Applications
Call Card Tab CALL_CARD
Call Card Tab CALL_CARD
Where the widget is embedded
What the handler receives
PLACEMENT_OPTIONS
Continue exploring
Scope:
telephony
You can add your item in the call card tab.
The specific widget placement code is specified in the
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
CALL_CARD
Item in the call card tab
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
588
b8a98e848778a4ffb38fbcf70f2b9
[AUTH_ID] =>
4172
bb6600705a0700005a4b00000001f0f107c42ca5bd5f61030c5d9c3e4d60d11b5a
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
31
f1e26600705a0700005a4b00000001f0f107b1918506d8a2ed9ecf76e8fdac962471
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => CALL_CARD
[PLACEMENT_OPTIONS] => {
"CALL_ID"
:
"externalCall.c3ee67f1a63f6e6117c230ab59cc49ea.1723556778"
,
"PHONE_NUMBER"
:
"555555"
,
"LINE_NUMBER"
:
""
,
"LINE_NAME"
:
""
,
"CRM_ENTITY_TYPE"
:
""
,
"CRM_ENTITY_ID"
:
"0"
,
"CRM_ACTIVITY_ID"
:
"undefined"
,
"CALL_DIRECTION"
:
"incoming"
,
"CALL_STATE"
:
"connected"
,
"CALL_LIST_MODE"
:
"false"
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
CALL_ID
*
string
The identifier of the call during which the widget was opened.
PHONE_NUMBER
*
string
The phone number of the client with whom the conversation is taking place.
LINE_NUMBER
string
The company phone number used to talk to the client.
LINE_NAME
string
The name of the company phone line used to talk to the client.
Lines are added by applications for integrating telephony using the
telephony.externalLine.add
method and are used for user convenience in Sales Intelligence.
CRM_ENTITY_TYPE
integer
Type of the CRM entity
to which the current call is linked.
Knowing the type and identifier of the CRM entity (specified in the
CRM_ENTITY_ID
parameter), you can retrieve information about the entity.
CRM_ENTITY_ID
string
The identifier of the CRM entity to which the current call is linked.
Knowing the type (specified in the
CRM_ENTITY_TYPE
parameter) and the identifier of the CRM entity (specified in the
CRM_ENTITY_ID
parameter), you can retrieve information about the entity using the corresponding methods:
any object type
crm.item.get
with entityTypeId = '1' for leads, '2' for deals, and
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
CRM_ACTIVITY_ID
string
The identifier of the
CRM activity
associated with the current call.
Can be used to obtain additional information using the
user.get
method.
CALL_DIRECTION
*
string
Defines the type of call. Can take the following values:
'incoming', incoming call;
'outcoming', outgoing call
CALL_STATE
string
Defines the state of the call. Can take the following values:
'connected', active call;
Other possible values will be published later.
CALL_LIST_MODE
string
Indicates whether the call is part of a
call campaign
or not.
Can take the following values:
False
, the call is not part of a call campaign;
True
, the call is made as part of a call campaign
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
Widget in calendar
Next
Menu Item in Call Analytics

---

## Menu Item in Call Analytics TELEPHONY_ANALYTICS_MENU

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/telephony/analytics-menu

Menu Item in Call Analytics TELEPHONY_ANALYTICS_MENU | Bitrix24 REST API and Marketplace Applications
Menu Item in Call Analytics TELEPHONY_ANALYTICS_MENU
Menu Item in Call Analytics TELEPHONY_ANALYTICS_MENU
Where the Widget is Embedded
What the Handler Receives
PLACEMENT_OPTIONS
Continue Your Exploration
Scope:
telephony
You can add your own menu item in call analytics.
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
TELEPHONY_ANALYTICS_MENU
Menu item in call analytics
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
Array
(
[DOMAIN] => xxx.bitrix24.com
[PROTOCOL] =>
1
[LANG] => en
[APP_SID] => b308bae53869a142613f8852c1bd3992
[AUTH_ID] =>
4
f77bb6600705a0700005a4b00000001f0f107cbd329fa1d8ea5455dc22653d12e7d54
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
3
ff6e26600705a0700005a4b00000001f0f10746f1299672a11fa3729c3ba98ebd86d2
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => TELEPHONY_ANALYTICS_MENU
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
Tab in the Call Detail
Next
WebRTC

---

## WebRTC

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/telephony/webrtc

WebRTC | Bitrix24 REST API and Marketplace Applications
WebRTC
WebRTC
Bitrix24 allows you to embed an external WebRTC client into the web version of the product. To do this, you need to follow several steps:
Upload your WebRTC client to a
special location
for embedding widgets
PAGE_BACKGROUND_WORKER
;
In case of an incoming call, register it using the standard telephony integration method
Register a call in Bitrix24 telephony.externalcall.register
, which will also display the standard call detail form to the user;
Manage the state and buttons of the call detail form using
special js methods
available for the widget handler
PAGE_BACKGROUND_WORKER
;
After the call ends, notify Bitrix24 about it using the method
Finish Call and Record It in Telephony Statistics telephony.externalcall.finish
.
Other functionalities, such as uploading call recordings to Bitrix24, can also be implemented using the corresponding
telephony integration methods
without referring to the WebRTC client.
Copied
Was the article helpful?
Yes
No
Previous
Menu Item in Call Analytics
Next
Left Menu Icon

---

## Icon of the Left Menu IM_NAVIGATION

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/im/index

Icon of the Left Menu IM_NAVIGATION | Bitrix24 REST API and Marketplace Applications
Icon of the Left Menu IM_NAVIGATION
Icon of the Left Menu IM_NAVIGATION
Where the Widget is Embedded
What the Handler Receives
Continue Exploring
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
im
You can add your item to the left navigation menu. Essentially, this is an application within the chat environment without embedding directly into the chat.
The code for the specific widget embedding location is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The embedding will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
IM_NAVIGATION
Item in the left navigation menu
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
'DOMAIN'
:
'xxx.bitrix24.com'
'PROTOCOL'
:
1
'LANG'
:
'en'
'APP_SID'
:
'99c80eff6378726287350416ee5fef0'
'AUTH_ID'
:
'6061e72600631fcd00005a4b00000001f0f1076700000000f69dd5fc643d9ce2fdbc1'
'AUTH_EXPIRES'
:
3600
'REFRESH_ID'
:
'50e00aa340631fcd00005a4b00000001f0f1071111116580a5b83c2de639ef28c12'
'member_id'
:
'da45a03b265ed12127f8a258d793cc5d'
'status'
:
'L'
'PLACEMENT'
:
'CRM_DEAL_DETAIL_TAB'
'PLACEMENT_OPTIONS'
:
'{"ID":"3443"}'
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The address of Bitrix24 where the widget handler was called
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
The user interface language of Bitrix24 that called the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who called the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who called the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was called.
status
string
Type of the application that registered the handler for this widget. Accepts values:
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
parameter will help determine from which specific widget embedding location your handler was called in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string defining the context of the widget execution. In this case, it is an array containing the numeric identifier of the CRM element in the detail form where the widget handler was called. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific CRM object the widget handler was called
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
WebRTC
Next
Widget Above Message

---

## Widget Above the IM_TEXTAREA Message

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/im/textarea

Widget Above the IM_TEXTAREA Message | Bitrix24 REST API and Marketplace Applications
Widget Above the IM_TEXTAREA Message
Widget Above the IM_TEXTAREA Message
Where the Widget is Embedded
What the Handler Receives
Continue Exploring
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
im
You can add your item to the panel above the input field (content generation while composing a message).
The specific widget embedding code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The embedding will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Embedded
Where the Widget is Embedded
Widget Code
Location
IM_TEXTAREA
Item in the panel above the input field
What the Handler Receives
What the Handler Receives
Data is transmitted as a POST request
'DOMAIN'
:
'xxx.bitrix24.com'
'PROTOCOL'
:
1
'LANG'
:
'en'
'APP_SID'
:
'99c80eff6378726287350416ee5fef0'
'AUTH_ID'
:
'6061e72600631fcd00005a4b00000001f0f1076700000000f69dd5fc643d9ce2fdbc1'
'AUTH_EXPIRES'
:
3600
'REFRESH_ID'
:
'50e00aa340631fcd00005a4b00000001f0f1071111116580a5b83c2de639ef28c12'
'member_id'
:
'da45a03b265ed12127f8a258d793cc5d'
'status'
:
'L'
'PLACEMENT'
:
'CRM_DEAL_DETAIL_TAB'
'PLACEMENT_OPTIONS'
:
'{"ID":"3443"}'
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The address of Bitrix24 where the widget handler was called
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
The user interface language of Bitrix24 that called the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who called the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who called the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was called.
status
string
Type of the application that registered the handler for this widget. Accepts values:
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
Code of the widget embedding location. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget embedding location your handler was called in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string defining the context of the widget execution. In this case, it is an array containing the numeric identifier of the CRM element in the detail form where the widget handler was called. The
PLACEMENT_OPTIONS
parameter, along with the
PLACEMENT
parameter, allows you to accurately determine for which specific CRM object the widget handler was called
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
Left Menu Icon
Next
Sidebar Widget

---

## Widget for the IM_SIDEBAR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/im/sidebar

Widget for the IM_SIDEBAR | Bitrix24 REST API and Marketplace Applications
Widget for the IM_SIDEBAR
Widget for the IM_SIDEBAR
Where the widget is embedded
What the handler receives
Continue studying
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
im
You can add your item to the sidebar. You can create applications that add additional scenarios for chat. For example, a separate Drive for chat or a knowledge base.
The specific placement code for the widget is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget code
Location
IM_SIDEBAR
Item in the sidebar
What the handler receives
What the handler receives
Data is transmitted as a POST request
'DOMAIN'
:
'xxx.bitrix24.com'
'PROTOCOL'
:
1
'LANG'
:
'en'
'APP_SID'
:
'99c80eff6378726287350416ee5fef0'
'AUTH_ID'
:
'6061e72600631fcd00005a4b00000001f0f1076700000000f69dd5fc643d9ce2fdbc1'
'AUTH_EXPIRES'
:
3600
'REFRESH_ID'
:
'50e00aa340631fcd00005a4b00000001f0f1071111116580a5b83c2de639ef28c12'
'member_id'
:
'da45a03b265ed12127f8a258d793cc5d'
'status'
:
'L'
'PLACEMENT'
:
'CRM_DEAL_DETAIL_TAB'
'PLACEMENT_OPTIONS'
:
'{"ID":"3443"}'
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The address of Bitrix24 where the widget handler was called
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
The user interface language of Bitrix24 that called the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who called the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who called the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was called.
status
string
Type of the application that registered the handler for this widget. Accepts values:
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
Code of the widget placement. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget placement your handler was called in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. In this case, it is an array containing the numeric identifier of the CRM element in the card where the widget handler was called. The
PLACEMENT_OPTIONS
parameter along with the
PLACEMENT
parameter allows you to accurately determine for which specific CRM object the widget handler was called
Continue studying
Continue studying
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
Widget Above Message
Next
Context Menu Item for Message

---

## IM_CONTEXT_MENU Message Context Menu Item

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/im/context-menu

IM_CONTEXT_MENU Message Context Menu Item | Bitrix24 REST API and Marketplace Applications
IM_CONTEXT_MENU Message Context Menu Item
IM_CONTEXT_MENU Message Context Menu Item
Where the widget is integrated
What the handler receives
Continue exploring
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
im
You can add your item to the message context menu. Integration into the "Create content based on" item (similar to the actions "Create task" or "Create meeting" based on the message).
The code for the specific widget integration point is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The integration will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is integrated
Where the widget is integrated
Widget code
Location
IM_CONTEXT_MENU
Message context menu item
What the handler receives
What the handler receives
Data is transmitted as a POST request
'DOMAIN'
:
'xxx.bitrix24.com'
'PROTOCOL'
:
1
'LANG'
:
'en'
'APP_SID'
:
'99c80eff6378726287350416ee5fef0'
'AUTH_ID'
:
'6061e72600631fcd00005a4b00000001f0f1076700000000f69dd5fc643d9ce2fdbc1'
'AUTH_EXPIRES'
:
3600
'REFRESH_ID'
:
'50e00aa340631fcd00005a4b00000001f0f1071111116580a5b83c2de639ef28c12'
'member_id'
:
'da45a03b265ed12127f8a258d793cc5d'
'status'
:
'L'
'PLACEMENT'
:
'CRM_DEAL_DETAIL_TAB'
'PLACEMENT_OPTIONS'
:
'{"ID":"3443"}'
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The address of Bitrix24 where the widget handler was called
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
The user interface language of Bitrix24 that called the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who called the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who called the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was called.
status
string
Type of the application that registered the handler for this widget. Accepts values:
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
Code of the widget integration point. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget integration point your handler was called in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string defining the context of the widget execution. In this case, it is an array containing the numeric identifier of the CRM element in the card where the widget handler was called. The
PLACEMENT_OPTIONS
parameter along with the
PLACEMENT
parameter allows you to accurately determine for which specific CRM object the widget handler was called
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
Sidebar Widget
Next
Emoji Collection

---

## Collection of Emojis IM_SMILES_SELECTOR

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/im/smile-selector

Collection of Emojis IM_SMILES_SELECTOR | Bitrix24 REST API and Marketplace Applications
Collection of Emojis IM_SMILES_SELECTOR
Collection of Emojis IM_SMILES_SELECTOR
Where the widget is embedded
What the handler receives
Continue exploring
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
im
You can extend the capabilities of emojis and giphy (there may be your own sources of images or emojis).
The specific widget placement code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget code
Location
IM_SMILES_SELECTOR
Extends the capabilities of emojis and giphy
What the handler receives
What the handler receives
Data is transmitted as a POST request
'DOMAIN'
:
'xxx.bitrix24.com'
'PROTOCOL'
:
1
'LANG'
:
'en'
'APP_SID'
:
'99c80eff6378726287350416ee5fef0'
'AUTH_ID'
:
'6061e72600631fcd00005a4b00000001f0f1076700000000f69dd5fc643d9ce2fdbc1'
'AUTH_EXPIRES'
:
3600
'REFRESH_ID'
:
'50e00aa340631fcd00005a4b00000001f0f1071111116580a5b83c2de639ef28c12'
'member_id'
:
'da45a03b265ed12127f8a258d793cc5d'
'status'
:
'L'
'PLACEMENT'
:
'CRM_DEAL_DETAIL_TAB'
'PLACEMENT_OPTIONS'
:
'{"ID":"3443"}'
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The address of Bitrix24 where the widget handler was called
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
The language of the Bitrix24 user interface that called the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who called the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who called the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was called.
status
string
Type of the application that registered the handler for this widget. Accepts values:
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
Code of the widget placement. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget placement your handler was called in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string defining the context of the widget execution. In this case, it is an array containing the numeric identifier of the CRM element in the card where the widget handler was called. The
PLACEMENT_OPTIONS
parameter along with the
PLACEMENT
parameter allows you to accurately determine for which specific CRM object the widget handler was called
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
Context Menu Item for Message
Next
Widget in contact center

---

## Widget in the CONTACT_CENTER

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/contact-center

Widget in the CONTACT_CENTER | Bitrix24 REST API and Marketplace Applications
Widget in the CONTACT_CENTER
Widget in the CONTACT_CENTER
Where the widget is embedded
What the handler receives
Continue exploring
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
contact_center
You can add your item ("square") to the Contact Center list.
The specific placement code for the widget is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The widget will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the widget is embedded
Where the widget is embedded
Widget code
Location
CONTACT_CENTER
Item ("square") in the Contact Center list
What the handler receives
What the handler receives
Data is transmitted as a POST request
'DOMAIN'
:
'xxx.bitrix24.com'
'PROTOCOL'
:
1
'LANG'
:
'en'
'APP_SID'
:
'99c80eff6378726287350416ee5fef0'
'AUTH_ID'
:
'6061e72600631fcd00005a4b00000001f0f1076700000000f69dd5fc643d9ce2fdbc1'
'AUTH_EXPIRES'
:
3600
'REFRESH_ID'
:
'50e00aa340631fcd00005a4b00000001f0f1071111116580a5b83c2de639ef28c12'
'member_id'
:
'da45a03b265ed12127f8a258d793cc5d'
'status'
:
'L'
'PLACEMENT'
:
'CRM_DEAL_DETAIL_TAB'
'PLACEMENT_OPTIONS'
:
'{"ID":"3443"}'
Required parameters are marked with *
Parameter
type
Description
DOMAIN
*
string
The address of Bitrix24 where the widget handler was called
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
The user interface language of Bitrix24 that called the widget. You can localize the interface language in your widget based on this value
APP_SID
string
String identifier of the application that registered the widget handler
AUTH_ID
string
Authorization token
OAuth 2
issued for the user who called the widget. Can be used for REST API calls on behalf of this user
AUTH_EXPIRES
integer
Time in seconds after which the authorization token will become invalid
REFRESH_ID
string
Refresh token
OAuth 2
issued for the user who called the widget. Can be used to refresh the authorization token on behalf of this user
member_id
*
string
Unique string identifier of Bitrix24 where the widget handler was called.
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
Code of the widget placement. You can use the same handler URL for all your widgets. The value that Bitrix24 will report in the
PLACEMENT
parameter will help determine from which specific widget placement your handler was called in each case
PLACEMENT_OPTIONS
string
Additional data in the form of a JSON string that defines the context of the widget execution. In this case, it is an array containing the numeric identifier of the CRM element in the detail form where the widget handler was called. The
PLACEMENT_OPTIONS
parameter along with the
PLACEMENT
parameter allows you to accurately determine for which specific CRM object the widget handler was called
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
Emoji Collection
Next
Universal Widgets

---

## Universal Widgets

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/universal/index

Universal Widgets | Bitrix24 REST API and Marketplace Applications
Universal Widgets
Universal Widgets
Widget as a Link with Slider REST_APP_URI
Invisible Widget on Every Page PAGE_BACKGROUND_WORKER
Was the article helpful?
Yes
No
Previous
Widget in contact center
Next
Link Widget with Slider

---

## Widget as a Link with Slider REST_APP_URI

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/universal/app-url

Widget as a Link with Slider REST_APP_URI | Bitrix24 REST API and Marketplace Applications
Widget as a Link with Slider REST_APP_URI
Widget as a Link with Slider REST_APP_URI
Where the Widget is Integrated
What the Handler Receives
PLACEMENT_OPTIONS
Continue Learning
Scope:
placement
This integration does not have a separate, pre-defined button in the interface that allows the user to open it independently. The application can simply send a link of a special format to any Bitrix24 tool that supports adding content with links:
Messages and comments in the news feed;
Messages in internal group and individual chats (will not work in open channel dialogs);
Task descriptions and comments;
Calendar meeting descriptions;
Etc.
To use this integration, the link must be in the format
/marketplace/view/#APP_CODE#/
, where
#APP_CODE#
:
The symbolic code of your mass-market application from the Developer's area, which is set in the application card;
The client_id of the local application (for example,
local.66ba434d853c87.18550109
), which can be copied from the application settings in the Developer resources section.
The integration can accept any number of arbitrary parameters in the GET key
params
, for example:
/marketplace/view/#APP_CODE#/?params[test]=y
. In this case,
PLACEMENT_OPTIONS
will be as follows:
[PLACEMENT_OPTIONS] => {
"test"
:
"y"
}
The widget code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The integration will not be displayed in the interface until the application installation is complete.
Check the application installation
Where the Widget is Integrated
Where the Widget is Integrated
Widget Code
Location
REST_APP_URI
The specific integration location is not indicated at the stage of adding the widget handler, as the widget will open when clicking on any links of the special format described above
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
195
ec4ee87932d8f9bbbd6a2f0a83553
[AUTH_ID] => f27bbb6600705a0700005a4b00000001f0f107398c3f17f5fc48d5ce194d5c65de7cfb
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] => e2fae26600705a0700005a4b00000001f0f1075f986dbd8dff24c36c2ad9bb0816a665
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => REST_APP_URI
[PLACEMENT_OPTIONS] => {
"test"
:
"y"
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
is a JSON string containing an array of one or more keys that were specified in the
params
parameter of the specific link, as described above.
This means that by setting in your links and processing the received GET parameter
params
in the widget handler, you can implement any necessary business logic.
Typical use-cases and scenarios
View external documents via link
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
Universal Widgets
Next
Invisible Widget on Every Page

---

## Invisible Widget on Every Page PAGE_BACKGROUND_WORKER

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/universal/background-worker

Invisible Widget on Every Page PAGE_BACKGROUND_WORKER | Bitrix24 REST API and Marketplace Applications
Invisible Widget on Every Page PAGE_BACKGROUND_WORKER
Invisible Widget on Every Page PAGE_BACKGROUND_WORKER
Features of Widget Handler Registration
What the Handler Receives
PLACEMENT_OPTIONS
Continue Learning
Scope:
placement
You can add an "invisible" widget that will be displayed on all pages of Bitrix24. This widget allows you to implement a scenario with an external
WebRTC client
in telephony integrations, but it is not the only possible use case.
For example, using the
interactive interaction
mechanism between backend and frontend applications, you can send a "signal" to the
PAGE_BACKGROUND_WORKER
widget, and upon receiving the "signal," open the application slider using the
openApplication
method.
The widget embedding code is specified in the
PLACEMENT
parameter of the
placement.bind
method.
The embedding will not be displayed in the interface until the application installation is complete.
Check the application installation
Features of Widget Handler Registration
Features of Widget Handler Registration
Unlike other types of widgets, for
PAGE_BACKGROUND_WORKER
, the application can register only one handler.
Since this widget loads on all pages, a handler that takes longer than 3-5 seconds to load may cause delays in rendering the Bitrix24 user interface. If this occurs more than 10 times within a day on the same Bitrix24, the handler will be automatically disabled.
Bitrix24 will inform the application about the handler's disablement. To do this, in the
placement.bind
method, you need to specify the URL in the
OPTIONS[errorHandlerUrl]
parameter. Bitrix24 will call this URL in case the
PAGE_BACKGROUND_WORKER
widget handler is disabled.
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
'{"PLACEMENT":"PAGE_BACKGROUND_WORKER","HANDLER":"http://myapp.com/handler/?type=1","OPTIONS":{"errorHandlerUrl":"http://myapp.com/error/"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/placement.bind
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"PLACEMENT":"PAGE_BACKGROUND_WORKER","HANDLER":"http://myapp.com/handler/?type=1","OPTIONS":{"errorHandlerUrl":"http://myapp.com/error/"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/placement.bind
try
{
const
response =
await
$b24.
callMethod
(
"placement.bind"
,
{
PLACEMENT
:
"PAGE_BACKGROUND_WORKER"
,
HANDLER
:
"http://myapp.com/handler/?type=1"
,
OPTIONS
: {
errorHandlerUrl
:
"http://myapp.com/error/"
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
console
.
error
(result.
error
());
else
console
.
info
(result);
}
catch
(error)
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
'placement.bind'
,
[
'PLACEMENT'
=>
'PAGE_BACKGROUND_WORKER'
,
'HANDLER'
=>
'http://myapp.com/handler/?type=1'
,
'OPTIONS'
=> [
'errorHandlerUrl'
=>
'http://myapp.com/error/'
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
'Error binding placement: '
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
"placement.bind"
,
{
PLACEMENT
:
"PAGE_BACKGROUND_WORKER"
,
HANDLER
:
"http://myapp.com/handler/?type=1"
,
OPTIONS
: {
errorHandlerUrl
:
"http://myapp.com/error/"
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
console
.
error
(result.
error
());
else
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
'placement.bind'
,
[
'PLACEMENT'
=>
'PAGE_BACKGROUND_WORKER'
,
'HANDLER'
=>
'http://myapp.com/handler/?type=1'
,
'OPTIONS'
=> [
'errorHandlerUrl'
=>
'http://myapp.com/error/'
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
What the Handler Receives
What the Handler Receives
Data is sent as a POST request
Array
(
[handler] =>
1
[DOMAIN] => restapi.bitrix24.com
[PROTOCOL] =>
1
[LANG] => de
[APP_SID] =>
588
b8a98e848778a4ffb38fbcf70f2b9
[AUTH_ID] =>
4172
bb6600705a0700005a4b00000001f0f107c42ca5bd5f61030c5d9c3e4d60d11b5a
[AUTH_EXPIRES] =>
3600
[REFRESH_ID] =>
31
f1e26600705a0700005a4b00000001f0f107b1918506d8a2ed9ecf76e8fdac962471
[member_id] => da45a03b265edd8787f8a258d793cc5d
[status] => L
[PLACEMENT] => PAGE_BACKGROUND_WORKER
[PLACEMENT_OPTIONS] => {
"ID"
:
"PAGE_BACKGROUND_WORKER"
,
"URI"
:
"\/company\/personal\/user\/1\/blog\/"
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
Always equals
PAGE_BACKGROUND_WORKER
and is used for internal purposes
URI
*
string
URL-encoded address of the current page where the widget was opened.
Typical use-cases and scenarios
WebRTC Integration Scenario
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
Link Widget with Slider
Next
Embedding in the Bitrix24 mobile application

---

## Embedding in the Bitrix24 Mobile Application

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/mobile-app

Embedding in the Bitrix24 Mobile Application | Bitrix24 REST API and Marketplace Applications
Embedding in the Bitrix24 Mobile Application
Embedding in the Bitrix24 Mobile Application
mobile
Scope
:
mobile
|
Execution rights
:
any user
Copied
Was the article helpful?
Yes
No
Previous
Invisible Widget on Every Page
Next
Register a widget

---

## Install Widget Handler placement.bind

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/placement-bind

Install Widget Handler placement.bind | Bitrix24 REST API and Marketplace Applications
Install Widget Handler placement.bind
Install Widget Handler placement.bind
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Widget Handler
Continue Learning
Scope:
placement
,
depending on the placement location
Who can execute the method: administrator
This method adds a handler for the widget placement.
It can be called at any time during the application's operation; however, it is often more convenient to register your widgets during the
application installation
.
It is important to note that until the application installation is complete, the widgets you register will not be available to regular users in the Bitrix24 interface - they can only be seen by users with administrative rights.
Check the application installation
.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
PLACEMENT
*
string
Identifier of the required widget placement location
HANDLER
*
string
URL of the widget placement handler
TITLE
string
Name of the widget in the interface. Depending on the specific placement location, this may be the name of a tab in a form, the name of a menu item, etc.
DESCRIPTION
string
Description of the widget in the interface. Not used in practice
GROUP_NAME
string
Allows grouping UI elements for multiple handlers of the same type of widget into a group. For example, several dropdown menu items in the
top button of the CRM card
. Supported only by certain types of widgets
LANG_ALL
object
Array of parameters
TITLE
,
DESCRIPTION
, and
GROUP_NAME
for specified languages. Users who have selected one of these languages in the Bitrix24 interface will see localized versions of
TITLE
,
DESCRIPTION
, and
GROUP_NAME
:
"LANG_ALL"
:
{
"en"
:
{
"TITLE"
:
"title"
,
"DESCRIPTION"
:
"description"
,
"GROUP_NAME"
:
"group"
}
,
"de"
:
{
"TITLE"
:
"Überschrift"
,
"DESCRIPTION"
:
"Beschreibung"
,
"GROUP_NAME"
:
"Gruppe"
}
}
OPTIONS
object
Additional display parameters for the widget. Specific values depend on the widget placement location. Currently used in widgets for messengers, in the widget
PAGE_BACKGROUND_WORKER
, and in the widget
CRM_XXX_DETAIL_ACTIVITY
USER_ID
integer
Identifier of the Bitrix24 user for whom the registered widget will be available. Possible values can be obtained using the
user.get
method.
Currently, this parameter is only supported by the widget
PAGE_BACKGROUND_WORKER
.
If you attempt to register a placement in other widgets, you will receive the error
ERROR_PLACEMENT_USER_MODE: User mode is not available
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
'{"PLACEMENT":"PLACEMENT_CODE","HANDLER":"http://myapp.com/handler/?type=1","OPTIONS":{"errorHandlerUrl":"http://myapp.com/error/"},"TITLE":"title","DESCRIPTION":"description","GROUP_NAME":"group","LANG_ALL":{"en":{"TITLE":"title","DESCRIPTION":"description","GROUP_NAME":"group"},"de":{"TITLE":"Überschrift","DESCRIPTION":"Beschreibung","GROUP_NAME":"Gruppe"}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/placement.bind
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"PLACEMENT":"PLACEMENT_CODE","HANDLER":"http://myapp.com/handler/?type=1","OPTIONS":{"errorHandlerUrl":"http://myapp.com/error/"},"TITLE":"title","DESCRIPTION":"description","GROUP_NAME":"group","LANG_ALL":{"en":{"TITLE":"title","DESCRIPTION":"description","GROUP_NAME":"group"},"de":{"TITLE":"Überschrift","DESCRIPTION":"Beschreibung","GROUP_NAME":"Gruppe"}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/placement.bind
try
{
const
response =
await
$b24.
callMethod
(
"placement.bind"
,
{
"PLACEMENT"
:
"PLACEMENT_CODE"
,
"HANDLER"
:
"http://myapp.com/handler/?type=1"
,
"OPTIONS"
: {
"errorHandlerUrl"
:
"http://myapp.com/error/"
},
"TITLE"
:
"title"
,
"DESCRIPTION"
:
"description"
,
"GROUP_NAME"
:
"group"
,
"LANG_ALL"
: {
"en"
: {
"TITLE"
:
"title"
,
"DESCRIPTION"
:
"description"
,
"GROUP_NAME"
:
"group"
,
},
"de"
: {
"TITLE"
:
"Überschrift"
,
"DESCRIPTION"
:
"Beschreibung"
,
"GROUP_NAME"
:
"Gruppe"
,
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
info
(result);
}
catch
(error)
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
'placement.bind'
,
[
'PLACEMENT'
=>
'PLACEMENT_CODE'
,
'HANDLER'
=>
'http://myapp.com/handler/?type=1'
,
'OPTIONS'
=> [
'errorHandlerUrl'
=>
'http://myapp.com/error/'
],
'TITLE'
=>
'title'
,
'DESCRIPTION'
=>
'description'
,
'GROUP_NAME'
=>
'group'
,
'LANG_ALL'
=> [
'en'
=> [
'TITLE'
=>
'title'
,
'DESCRIPTION'
=>
'description'
,
'GROUP_NAME'
=>
'group'
,
],
'de'
=> [
'TITLE'
=>
'Überschrift'
,
'DESCRIPTION'
=>
'Beschreibung'
,
'GROUP_NAME'
=>
'Gruppe'
,
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
'Error binding placement: '
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
"placement.bind"
,
{
"PLACEMENT"
:
"PLACEMENT_CODE"
,
"HANDLER"
:
"http://myapp.com/handler/?type=1"
,
"OPTIONS"
: {
"errorHandlerUrl"
:
"http://myapp.com/error/"
},
"TITLE"
:
"title"
,
"DESCRIPTION"
:
"description"
,
"GROUP_NAME"
:
"group"
,
"LANG_ALL"
: {
"en"
: {
"TITLE"
:
"title"
,
"DESCRIPTION"
:
"description"
,
"GROUP_NAME"
:
"group"
,
},
"de"
: {
"TITLE"
:
"Überschrift"
,
"DESCRIPTION"
:
"Beschreibung"
,
"GROUP_NAME"
:
"Gruppe"
,
}
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
console
.
error
(result.
error
());
else
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
'placement.bind'
,
[
'PLACEMENT'
=>
'PLACEMENT_CODE'
,
'HANDLER'
=>
'http://myapp.com/handler/?type=1'
,
'OPTIONS'
=> [
'errorHandlerUrl'
=>
'http://myapp.com/error/'
],
'TITLE'
=>
'title'
,
'DESCRIPTION'
=>
'description'
,
'GROUP_NAME'
=>
'group'
,
'LANG_ALL'
=> [
'en'
=> [
'TITLE'
=>
'title'
,
'DESCRIPTION'
=>
'description'
,
'GROUP_NAME'
=>
'group'
],
'de'
=> [
'TITLE'
=>
'Überschrift'
,
'DESCRIPTION'
=>
'Beschreibung'
,
'GROUP_NAME'
=>
'Gruppe'
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
Typical use-cases and scenarios
Embed Widget in CRM Card
Embed a widget in a lead as a custom property
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
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Returns the result of adding the widget handler. Possible values:
True
, the handler was successfully registered;
False
, the handler was not registered
time
time
Information about the request execution time
Error Handling
Error Handling
HTTP status:
400
,
403
,
200
{
"error"
:
"ERROR_ARGUMENT"
,
"error_description"
:
"Argument 'PLACEMENT' is null or empty"
,
"argument"
:
"PLACEMENT"
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
Status
ERROR_PLACEMENT_MAX_COUNT
Attempted to re-register the handler for the
PAGE_BACKGROUND_WORKER
widget
200
ERROR_ARGUMENT
Required field value is not specified. The code of the required field is returned in
argument
200
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
Widget Handler
Widget Handler
Thus, a successful call to the
placement.bind
method allowed you to register the widget handler. It is important that the HANDLER_URL parameter you specified points to a real and accessible URL.
Important
It is required that the handler URL is
definitely
accessible from the external network. Links to localhost, local domains, and similar ways of accessing a local web server are not acceptable. Check the availability of the URL you specified using special services that monitor website availability!
When accessing your handler, Bitrix24 will send a POST message containing information about the widget context, such as the deal identifier if the widget is embedded in the deal card in CRM, etc.
Examples of such data can be found in the descriptions of
specific widget placement locations
.
Continue Learning
Continue Learning
Widget Embedding Locations
Retrieving a List of Available Placement Options for the Application
Removing a Registered Placement Handler
Interaction with UI from Widgets
Copied
Was the article helpful?
Yes
No
Previous
Embedding in the Bitrix24 mobile application
Next
Get a list of registered widgets

---

## Get a list of registered widget placement handlers placement.get

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/placement-get

Get a list of registered widget placement handlers placement.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get a list of registered widget placement handlers placement.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
placement
,
depending on the placement
Who can execute the method: administrator
This method retrieves a list of registered widget placement handlers.
Method Parameters
Method Parameters
The method has no parameters.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/placement.get
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
https://**put_your_bitrix24_address**/rest/placement.get
try
{
const
response =
await
$b24.
callMethod
(
"placement.get"
,
{}
);
const
result = response.
getData
().
result
;
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
'placement.get'
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
error_log
(
$result
->
error
());
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
'Error getting placements: '
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
"placement.get"
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
console
.
error
(result.
error
());
else
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
'placement.get'
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
{
"placement"
:
"CRM_DEAL_LIST_TOOLBAR"
,
"userId"
:
0
,
"handler"
:
"https://myapp.com/?handler=1"
,
"options"
:
[
]
,
"title"
:
"Add invoice"
,
"description"
:
""
,
"langAll"
:
{
"de"
:
{
"TITLE"
:
"Add invoice"
,
"DESCRIPTION"
:
""
,
"GROUP_NAME"
:
"Documents"
}
}
}
,
{
"placement"
:
"CRM_DEAL_LIST_TOOLBAR"
,
"userId"
:
0
,
"handler"
:
"https://myapp.com/?handler=1"
,
"options"
:
[
]
,
"title"
:
"Import invoice"
,
"description"
:
""
,
"langAll"
:
{
"de"
:
{
"TITLE"
:
"Import invoice"
,
"DESCRIPTION"
:
""
,
"GROUP_NAME"
:
"Documents"
}
}
}
,
{
"placement"
:
"IM_CONTEXT_MENU"
,
"userId"
:
0
,
"handler"
:
"https://myapp.com/?handler=2"
,
"options"
:
{
"extranet"
:
"N"
,
"context"
:
"ALL"
,
"role"
:
"USER"
}
,
"title"
:
"My App 1"
,
"description"
:
""
,
"langAll"
:
{
"de"
:
{
"TITLE"
:
"My App 1"
,
"DESCRIPTION"
:
""
,
"GROUP_NAME"
:
""
}
}
}
,
{
"placement"
:
"PAGE_BACKGROUND_WORKER"
,
"userId"
:
1
,
"handler"
:
"https://myapp.com/?handler=3"
,
"options"
:
{
"errorHandlerUrl"
:
"https://myapp.com/?handler=3"
}
,
"title"
:
"My App 2"
,
"description"
:
""
,
"langAll"
:
{
"de"
:
{
"TITLE"
:
"My App 2"
,
"DESCRIPTION"
:
""
,
"GROUP_NAME"
:
""
}
}
}
]
,
"time"
:
{
"start"
:
1712132792.910734
,
"finish"
:
1712132793.530359
,
"duration"
:
0.6196250915527344
,
"processing"
:
0.032338857650756836
,
"date_start"
:
"2024-04-03T10:26:32+02:00"
,
"date_finish"
:
"2024-04-03T10:26:33+02:00"
,
"operating_reset_at"
:
1705765533
,
"operating"
:
3.3076241016387939
}
}
Returned Data
Returned Data
Name
type
Description
result
boolean
Returns a list of registered widget handlers. The structure of each element corresponds to the parameters of the
handler registration method
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP status:
400
,
403
,
200
{
"error"
:
"INVALID_REQUEST"
,
"error_description"
:
"Https required"
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
Widget Embedding Locations
Retrieving a List of Available Placement Options for the Application
Install Widget Handler placement.bind
Removing a Registered Placement Handler
Interaction with UI from Widgets
Copied
Was the article helpful?
Yes
No
Previous
Register a widget
Next
Get a list of widgets

---

## Retrieving a List of Available Placement Options for the Application

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/placement-list

Retrieving a List of Available Placement Options for the Application | Bitrix24 REST API and Marketplace Applications
Retrieving a List of Available Placement Options for the Application
Retrieving a List of Available Placement Options for the Application
Parameters
Example
We are still updating this page
Some data may be missing — we will complete it shortly.
placement.list
Scope
:
depending on the placement
|
Who can execute the method
:
for everyone
This method retrieves a list of available placement options for the application.
Parameters
Parameters
Parameter
Description
Available Since
SCOPE
Restricts the list to one of the application's access permissions
Example
Example
GET
https://sometestaccount.bitrix24.com/rest/placement.list?auth=7e623a5a0000cd710000cd5b00000001000000a8b1dbe022e2de93198634e9526b00f7
HTTP/1.1
HTTP/1.1 200 OK
{
"result": [
"CRM_LEAD_LIST_MENU",
"CRM_DEAL_LIST_MENU",
"CRM_INVOICE_LIST_MENU",
"CRM_QUOTE_LIST_MENU",
"CRM_CONTACT_LIST_MENU",
"CRM_COMPANY_LIST_MENU",
"CRM_ACTIVITY_LIST_MENU",
"CRM_LEAD_DETAIL_TAB",
"CRM_DEAL_DETAIL_TAB",
"CRM_CONTACT_DETAIL_TAB",
"CRM_COMPANY_DETAIL_TAB",
"CRM_LEAD_DETAIL_ACTIVITY",
"CRM_DEAL_DETAIL_ACTIVITY",
"CRM_CONTACT_DETAIL_ACTIVITY",
"CRM_COMPANY_DETAIL_ACTIVITY"
]
}
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get a list of registered widgets
Next
Unregister a widget

---

## Removing a Registered Placement Handler

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/placement-unbind

Removing a Registered Placement Handler | Bitrix24 REST API and Marketplace Applications
Removing a Registered Placement Handler
Removing a Registered Placement Handler
Parameters
Example
We are still updating this page
Some data may be missing here — we will complete it shortly.
placement.unbind
Scope
:
depending on the placement
|
Who can execute the method
:
administrator
This method removes the registered handler for a placement and returns the number of removed handlers.
Parameters
Parameters
Parameter
Description
Available since
PLACEMENT
*
Identifier of the placement.
HANDLER
URL of the placement handler. If the handler URL is not specified, all handlers registered by the application for the specified placement will be removed.
* - Required parameter.
Example
Example
GET
https://sometestaccount.com/rest/placement.unbind?auth=7e623a5a0000cd710000cd5b00000001000000a8b1dbe022e2de93198634e9526b00f7&placement=CRM_LEAD_DETAIL_TAB&handler=https%3A%2F%2Fwww.myapplicationhost.com%2Fplacement%2F
HTTP/1.1
HTTP/1.1 200 OK
{
"result": {
"count": 1
}
}
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Get a list of widgets
Next
Call standard sliders

---

## Open Standard Bitrix24 Pages from Application Widgets

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/open-path

Open Standard Bitrix24 Pages from Application Widgets | Bitrix24 REST API and Marketplace Applications
Open Standard Bitrix24 Pages from Application Widgets
Open Standard Bitrix24 Pages from Application Widgets
To avoid creating your own interfaces for displaying information about CRM entities, tasks, etc., and to show users the standard and familiar Bitrix24 pages, you can use the method
openPath
.
This significantly simplifies development and speeds up the application creation process. In your application, you can display lists of deals, tasks, contacts, companies, etc., based on your required business logic. By clicking on a list item, you can open the standard entity page in Bitrix24 using the
openPath
method.
We strongly recommend using this method in your application interfaces, as it enhances the user experience, making your solutions closely resemble the standard Bitrix24 interfaces.
Keep in mind that the
openPath
method does not provide the ability to retrieve data from the standard Bitrix24 pages. It merely opens them in a slider and allows you to track the moment the slider closes, so you can refresh the data in your interface. However, in conjunction with
event handling
and the
interactive interaction
mechanism between the back-end and front-end parts of the application, you can implement data updates in your interface after the standard sliders close.
Example:
Example:
<script src=
"//api.bitrix24.com/api/v1/"
></script>
<
script
>
BX24
.
init
(
function
(
)
{
BX24
.
openPath
(
'/crm/deal/details/5/'
,
function
(
result
)
{
// callback function, called when the slider closes
console
.
log
(result);
}
);
}
);
</
script
>
Copied
Was the article helpful?
Yes
No
Previous
Unregister a widget
Next
Open custom slider

---

## Open a Slider with Your Interface

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/open-application

Open a Slider with Your Interface | Bitrix24 REST API and Marketplace Applications
Open a Slider with Your Interface
Open a Slider with Your Interface
Example
Advantages of Using a Slider
Often, there is a need in your applications to open a popup for user interaction. This could be a popup window where you want to display:
application option settings,
some dialog with the user,
detailed information about a document, product, etc.
This is easy to achieve, but it's important to remember that the application interface is displayed within a frame. This means that any content you show is limited by the size of the frame. A large popup window will cause a scrollbar to appear on the frame, which is not always convenient and definitely not visually appealing.
To solve this problem, you are encouraged to use a slider. A slider is a popup window that opens over the frame and allows you to display any content without being constrained by the original frame size of the application. The Bitrix24 interface itself is built around the use of sliders, and you can use them in your applications.
Example
Example
<script>
BX24
.
openApplication
(
{
'action'
:
'display_setting'
// your custom data passed to the application for display in the slider
},
function
(
)
{
// this handler will be triggered when the slider is closed
alert
(
'Application closed!'
)
}
);
</script>
You decide which parameters you want to pass to your application in order to generate the necessary content/interface for the slider on the application side. In the example above, we pass the parameter
action
with the value
display_setting
to the application. Upon receiving a POST request from Bitrix24 and processing this parameter, the application can create an interface with some user settings instead of showing the default application interface.
The request will come to the same URL that you specified in your application settings in the
Path to your handler
field for a
local application
, or in the
Application link
field for a
mass-market
application.
In other words, your code that responds to this URL should act as a controller or manager, generating different HTML based on the parameters received in the request.
Advantages of Using a Slider
Advantages of Using a Slider
Visually Appealing
. Sliders in Bitrix24 are the standard way to display content, and users are accustomed to them.
Convenient
. Sliders allow you to show content of any size, without being limited by the application frame size, unlike popup windows.
Simple
. Understanding what interface to return in the slider is straightforward; it can be implemented with a simple condition in your code.
Flexible
. You decide what content to display in the slider and can change it based on the parameters passed in the request.
Copied
Was the article helpful?
Yes
No
Previous
Call standard sliders
Next
Close custom slider

---

## Bitrix24 REST API and Marketplace Applications

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/close-application

Bitrix24 REST API and Marketplace Applications
We are still updating this page
Some data may be missing here — we will complete it soon.
Was the article helpful?
Yes
No
Previous
Open custom slider
Next
Interaction with UI from Widgets

---

## Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/user-field/index

Overview of Methods | Bitrix24 REST API and Marketplace Applications
Overview of Methods
Overview of Methods
Scope:
depending on the placement
Who can execute the method: any user
Applications that have access to the
placement
scope can register their own types of custom fields.
Currently, cloud accounts support the use of such fields in both the new and old detail forms of
CRM
entities. Applications can create custom fields of standard types as well as those registered by the application itself. Account administrators can create fields of any registered types, including field types registered by applications. When registering a type, the application specifies the handler address that will open in a frame at the location of the field output, and further operations are virtually indistinguishable from those of a standard widget.
Method
Description
userfieldtype.add
Register a new type of custom fields
userfieldtype.list
Retrieve a list of types of custom fields registered by the application
userfieldtype.update
Modify the settings of a type of custom fields registered by the application
userfieldtype.delete
Remove a type of custom fields registered by the application
Additional Information
Additional Information
Example of embedding in the tutorial
Embed a widget in a lead as a custom property
You have registered a new type of custom fields. If, when trying to create a field with the new type,
userfieldtype.list
returns your new custom field type and you still encounter an error:
Error! 400: ERROR_CORE: Invalid custom type specified. (400)
, it means that the
application
is not fully installed. Call the method
app.info
and ensure that the result returns
INSTALLED = true
. If the application has an interface, to complete the installation, you need to execute the following js code on the application page:
BX24
.
init
(
function
(
){
BX24
.
installFinish
();
});
Local applications refer to applications that are described and added directly to a specific
Bitrix24
.
Copied
Was the article helpful?
Yes
No
Previous
When pressing the "notify admin" button
Next
Register a New Custom Field Type

---

## Register a new user field type userfieldtype.add

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/user-field/userfieldtype-add

Register a new user field type userfieldtype.add | Bitrix24 REST API and Marketplace Applications
Register a new user field type userfieldtype.add
Register a new user field type userfieldtype.add
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
depending on the embedding location
Who can execute the method: any user
The
userfieldtype.add
method registers a new type of custom fields. After registering the type, create a custom field using the
userfieldconfig.add
method.
When opening a card with a custom type field, an array
PLACEMENT_OPTIONS
containing data about the field and entity is passed to the application handler.
{
"MODE"
:
"view"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_TEST_TYPE_1"
,
"ENTITY_VALUE_ID"
:
"7303"
,
"VALUE"
:
null
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"XML_ID"
:
null
,
"ENTITY_DATA"
:
{
"entityTypeId"
:
2
,
"entityId"
:
"7303"
,
"module"
:
"crm"
}
}
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
Restrictions
USER_TYPE_ID
*
string
String code for the type
a-z0-9
must be unique
HANDLER
*
URL
Address of the user type handler
in the same domain as the main application address
must be unique
TITLE
string
Text name of the type. Will be displayed in the administrative interface for user field settings
DESCRIPTION
string
Text description of the type. Will be displayed in the administrative interface for user field settings
OPTIONS
array
Additional settings. Currently, one key is available:
height
— specifies the height of the user field in pixels. Any positive value will apply.
Default is
0
. If
0
is specified, the standard height for displaying this embedding will be used
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
"USER_TYPE_ID": "test_type",
"HANDLER": "https://www.myapplication.com/handler/",
"TITLE": "Updated test type",
"DESCRIPTION": "Test userfield type for documentation with updated description",
"OPTIONS": {
"height": 60
}
}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/userfieldtype.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{
"USER_TYPE_ID": "test_type",
"HANDLER": "https://www.myapplication.com/handler/",
"TITLE": "Updated test type",
"DESCRIPTION": "Test userfield type for documentation with updated description",
"OPTIONS": {
"height": 60
},
"auth": "**put_access_token_here**"
}'
\
https://**put_your_bitrix24_address**/rest/userfieldtype.add
try
{
const
response =
await
$b24.
callMethod
(
'userfieldtype.add'
,
{
USER_TYPE_ID
:
'test_type'
,
HANDLER
:
'https://www.myapplication.com/handler/'
,
TITLE
:
'Updated test type'
,
DESCRIPTION
:
'Test userfield type for documentation with updated description'
,
OPTIONS
: {
height
:
60
,
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
(result);
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
'userfieldtype.add'
,
[
'USER_TYPE_ID'
=>
'test_type'
,
'HANDLER'
=>
'https://www.myapplication.com/handler/'
,
'TITLE'
=>
'Updated test type'
,
'DESCRIPTION'
=>
'Test userfield type for documentation with updated description'
,
'OPTIONS'
=> [
'height'
=>
60
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
error_log
(
$result
->
error
());
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
'Error adding user field type: '
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
'userfieldtype.add'
,
{
USER_TYPE_ID
:
'test_type'
,
HANDLER
:
'https://www.myapplication.com/handler/'
,
TITLE
:
'Updated test type'
,
DESCRIPTION
:
'Test userfield type for documentation with updated description'
,
OPTIONS
: {
height
:
60
,
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
'userfieldtype.add'
,
[
'USER_TYPE_ID'
=>
'test_type'
,
'HANDLER'
=>
'https://www.myapplication.com/handler/'
,
'TITLE'
=>
'Updated test type'
,
'DESCRIPTION'
=>
'Test userfield type for documentation with updated description'
,
'OPTIONS'
=> [
'height'
=>
60
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
1724421710.397825
,
"finish"
:
1724421711.040353
,
"duration"
:
0.6425280570983887
,
"processing"
:
5.888938903808594e-5
,
"date_start"
:
"2024-08-23T16:01:50+02:00"
,
"date_finish"
:
"2024-08-23T16:01:51+02:00"
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
Result of registering the new user field type
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
"ERROR_CORE"
,
"error_description"
:
"Unable to set placement handler: Handler already binded"
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
ERROR_CORE
Unable to set placement handler: Handler already binded
HANDLER
is already occupied by another user field type of this application or
USER_TYPE_ID
is already used by another application
ERROR_ARGUMENT
Argument 'USER_TYPE_ID' is null or empty
USER_TYPE_ID
is not specified
ERROR_ARGUMENT
Argument 'HANDLER' is null or empty
HANDLER
is not specified
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
Change settings for user field type userfieldtype.update
Get a list of registered user field types userfieldtype.list
Delete Registered User Field Type userfieldtype.delete
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Modify Custom Field Type Settings

---

## Change settings for user field type userfieldtype.update

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/user-field/userfieldtype-update

Change settings for user field type userfieldtype.update | Bitrix24 REST API and Marketplace Applications
Method parameters
Change settings for user field type userfieldtype.update
Method parameters
Code examples
Response handling
Returned data
Error handling
Possible error codes
Statuses and System Error Codes
Continue learning
Scope:
depending on the embedding location
Who can execute the method: any user
The method
userfieldtype.update
modifies the settings of a user field type registered by the application. It returns
true
or an error with a description of the reason.
Method parameters
Method parameters
Required parameters are marked with *
Name
type
Description
Restrictions
USER_TYPE_ID
*
string
String code of the type
a-z0-9
must be unique
HANDLER
*
URL
Address of the user type handler
in the same domain as the main application address
must be unique
TITLE
*
string
Text name of the type. Will be displayed in the administrative interface for user field settings
DESCRIPTION
string
Text description of the type. Will be displayed in the administrative interface for user field settings
OPTIONS
array
Additional settings. Currently, one key is available:
height
— specifies the height of the user field in pixels. Any positive value will apply.
Default is
0
. If
0
is specified, the standard height for displaying this embedding will be used
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"USER_TYPE_ID": "test_type",
"HANDLER": "https://www.myapplication.com/handler/",
"TITLE": "Updated test type",
"DESCRIPTION": "Test userfield type for documentation with updated description",
"OPTIONS": {
"height": 60
}
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/userfieldtype.update
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"USER_TYPE_ID": "test_type",
"HANDLER": "https://www.myapplication.com/handler/",
"TITLE": "Updated test type",
"DESCRIPTION": "Test userfield type for documentation with updated description",
"OPTIONS": {
"height": 60
},
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/userfieldtype.update
try
{
const
response =
await
$b24.
callMethod
(
'userfieldtype.update'
,
{
USER_TYPE_ID
:
'test_type'
,
HANDLER
:
'https://www.myapplication.com/handler/'
,
TITLE
:
'Updated test type'
,
DESCRIPTION
:
'Test userfield type for documentation with updated description'
,
OPTIONS
: {
height
:
60
,
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
(result);
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
$result
=
$serviceBuilder
->
getPlacementScope
()
->
userFieldType
()
->
update
(
'custom_user_type'
,  // userTypeId
'https://example.com/handler'
,  // handlerUrl
'Custom User Type'
,  // title
'Description of custom user type'
// description
);
if
(
$result
->
isSuccess
()) {
print
(
"Update successful."
);
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
'userfieldtype.update'
,
{
USER_TYPE_ID
:
'test_type'
,
HANDLER
:
'https://www.myapplication.com/handler/'
,
TITLE
:
'Updated test type'
,
DESCRIPTION
:
'Test userfield type for documentation with updated description'
,
OPTIONS
: {
height
:
60
,
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
'userfieldtype.update'
,
[
'USER_TYPE_ID'
=>
'test_type'
,
'HANDLER'
=>
'https://www.myapplication.com/handler/'
,
'TITLE'
=>
'Updated test type'
,
'DESCRIPTION'
=>
'Test userfield type for documentation with updated description'
,
'OPTIONS'
=> [
'height'
=>
60
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
1724421710.397825
,
"finish"
:
1724421711.040353
,
"duration"
:
0.6425280570983887
,
"processing"
:
5.888938903808594e-5
,
"date_start"
:
"2024-08-23T16:01:50+02:00"
,
"date_finish"
:
"2024-08-23T16:01:51+02:00"
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
Result of changing the user field type
time
time
Information about the execution time of the request
Error handling
Error handling
HTTP status:
400
{
"error"
:
"ERROR_NOT_FOUND"
,
"error_description"
:
"User Field Type not found"
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
ERROR_CORE
Unable to set placement handler: Handler already binded
HANDLER
is already occupied by another user field type of this application or
USER_TYPE_ID
is already used by another application
ERROR_ARGUMENT
Argument 'USER_TYPE_ID' is null or empty
USER_TYPE_ID
is not specified
ERROR_NOT_FOUND
User Field Type not found
User field with the specified
USER_TYPE_ID
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
Continue learning
Continue learning
Register a new user field type userfieldtype.add
Get a list of registered user field types userfieldtype.list
Delete Registered User Field Type userfieldtype.delete
Copied
Was the article helpful?
Yes
No
Previous
Register a New Custom Field Type
Next
Retrieve a List of Registered Custom Field Types

---

## Get a list of registered user field types userfieldtype.list

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/user-field/userfieldtype-list

Get a list of registered user field types userfieldtype.list | Bitrix24 REST API and Marketplace Applications
Code Examples
Get a list of registered user field types userfieldtype.list
Code Examples
Response Handling
Returned Data
Continue Learning
Scope:
depending on the embedding location
Who can execute the method: any user
The method retrieves a list of user field types registered by the application. It returns a list of field types with pagination.
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/userfieldtype.list
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{}' \
https://**put_your_bitrix24_address**/rest/userfieldtype.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'userfieldtype.list'
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
'userfieldtype.list'
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
'userfieldtype.list'
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
$userFieldTypesResult
=
$serviceBuilder
->
getPlacementScope
()->
userFieldType
()->
list
();
$userFieldTypes
=
$userFieldTypesResult
->
getUserFieldTypes
();
foreach
(
$userFieldTypes
as
$userFieldType
) {
print
(
"Description: "
.
$userFieldType
->DESCRIPTION .
"\n"
);
print
(
"Handler: "
.
$userFieldType
->HANDLER .
"\n"
);
print
(
"Title: "
.
$userFieldType
->TITLE .
"\n"
);
print
(
"User Type ID: "
.
$userFieldType
->USER_TYPE_ID .
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
());
}
BX24
.
callMethod
(
'userfieldtype.list'
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
'userfieldtype.list'
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
{
"USER_TYPE_ID"
:
"my_custom_type_2"
,
"HANDLER"
:
"http:\/\/test.com\/test2.php"
,
"TITLE"
:
"test title 2"
,
"DESCRIPTION"
:
"test desc 2"
}
,
{
"USER_TYPE_ID"
:
"my_custom_type_1"
,
"HANDLER"
:
"http:\/\/test.com\/test1.php"
,
"TITLE"
:
"test title 1"
,
"DESCRIPTION"
:
"test desc 1"
}
,
{
"USER_TYPE_ID"
:
"test_user_type"
,
"HANDLER"
:
"http:\/\/test.com\/test.php"
,
"TITLE"
:
"test title"
,
"DESCRIPTION"
:
"test desc"
}
]
,
"total"
:
3
,
"time"
:
{
"start"
:
1724423274.842117
,
"finish"
:
1724423275.558021
,
"duration"
:
0.7159039974212646
,
"processing"
:
0.0018908977508544922
,
"date_start"
:
"2024-08-23T16:27:54+02:00"
,
"date_finish"
:
"2024-08-23T16:27:55+02:00"
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
Root element of the response
total
integer
Number of processed records
time
time
Information about the execution time of the request
Continue Learning
Continue Learning
Register a new user field type userfieldtype.add
Change settings for user field type userfieldtype.update
Delete Registered User Field Type userfieldtype.delete
Copied
Was the article helpful?
Yes
No
Previous
Modify Custom Field Type Settings
Next
Delete a Registered Custom Field Type

---

## Delete Registered User Field Type userfieldtype.delete

**Source:** https://apidocs.bitrix24.com/api-reference/widgets/user-field/userfieldtype-delete

Delete Registered User Field Type userfieldtype.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Registered User Field Type userfieldtype.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
depending on the integration point
Who can execute the method: any user
The method
userfieldtype.delete
removes a user field type registered by the application. It returns
true
or an error with a description of the reason.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
Restrictions
USER_TYPE_ID
*
string
String code of the type
a-z0-9
must be unique
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
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"USER_TYPE_ID": "test"
}' \
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/userfieldtype.delete
curl -X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{
"USER_TYPE_ID": "test",
"auth": "**put_access_token_here**"
}' \
https://**put_your_bitrix24_address**/rest/userfieldtype.delete
try
{
const
response =
await
$b24.
callMethod
(
'userfieldtype.delete'
,
{
USER_TYPE_ID
:
'test'
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
console
.
error
(error);
}
try
{
$userTypeId
=
'example_user_type_id'
;
// Replace with the actual user type ID
$result
=
$serviceBuilder
->
getPlacementScope
()
->
userFieldType
()
->
delete
(
$userTypeId
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
"Error occurred while deleting user field type."
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
"Exception: "
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
'userfieldtype.delete'
,
{
USER_TYPE_ID
:
'test'
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
'userfieldtype.delete'
,
[
'USER_TYPE_ID'
=>
'test'
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
1724421710.397825
,
"finish"
:
1724421711.040353
,
"duration"
:
0.6425280570983887
,
"processing"
:
5.888938903808594e-5
,
"date_start"
:
"2024-08-23T16:01:50+02:00"
,
"date_finish"
:
"2024-08-23T16:01:51+02:00"
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
Result of deleting the user field type
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
"ERROR_NOT_FOUND"
,
"error_description"
:
"User Field Type not found"
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
ERROR_ARGUMENT
Argument 'USER_TYPE_ID' is null or empty
USER_TYPE_ID
is not specified
ERROR_NOT_FOUND
User Field Type not found
User field with the specified
USER_TYPE_ID
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
Register a new user field type userfieldtype.add
Change settings for user field type userfieldtype.update
Get a list of registered user field types userfieldtype.list
Copied
Was the article helpful?
Yes
No
Previous
Retrieve a List of Registered Custom Field Types
Next
Overview of REST 3.0

---

