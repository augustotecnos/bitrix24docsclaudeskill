---
description: 'AI API: AI engine integration, models, providers'
methods:
- user.fields
pages: 9
title: 'AI API: AI engine integration, models, providers'
---
# AI API: AI engine integration, models, providers
> AI API: AI engine integration, models, providers
> **9 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [AI in Bitrix24](#ai-in-bitrix24)
- [Register the service ai.engine.register](#register-the-service-aiengineregister)
- [Get the list of services ai.engine.list](#get-the-list-of-services-aienginelist)
- [Delete service ai.engine.unregister](#delete-service-aiengineunregister)
- [About Prompts for CoPilot](#about-prompts-for-copilot)
- [Add Prompt ai.prompt.register](#add-prompt-aipromptregister)
- [Unregister AI Prompt ai.prompt.unregister](#unregister-ai-prompt-aipromptunregister)
- [Markers in Prompts](#markers-in-prompts)
- [Conditions in Prompts](#conditions-in-prompts)

---

## AI in Bitrix24

**Source:** https://apidocs.bitrix24.com/api-reference/ai/index

AI in Bitrix24 | Bitrix24 REST API and Marketplace Applications
AI in Bitrix24
AI in Bitrix24
We are still updating this page
Some data may be missing here — we will complete it soon.
Scope
:
ai_admin
|
Who can execute the method
:
administrator
REST methods available when working with the ai module. These methods provide capabilities for working with custom AI services, including their registration, viewing the list, and deletion, as well as enabling and disabling request logging for debugging.
Method
Description
ai.engine.register
Method for adding a custom service.
ai.engine.list
Method for retrieving the list of engines.
ai.engine.unregister
Method for removing an engine.
Copied
Was the article helpful?
Yes
No
Previous
Get dataset fields
Next
Register Service

---

## Register the service ai.engine.register

**Source:** https://apidocs.bitrix24.com/api-reference/ai/ai-engine-register

Register the service ai.engine.register | Bitrix24 REST API and Marketplace Applications
Register the service ai.engine.register
Register the service ai.engine.register
Type of AI
Examples
Endpoint
Important points:
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
ai_admin
Who can execute the method: administrator
REST method for adding a custom service. The method registers an
engine
and updates it upon subsequent calls. This is not quite an embedding location, as the partner's
endpoint
must follow strict formats.
Parameter
Description
Version
name
unknown
A meaningful and concise name that will appear in the user interface.
code
unknown
Unique engine code
category
unknown
Can be either text (text generation), image (image generation), or audio (text recognition).
completions_url
unknown
endpoint for processing the user request.
settings
unknown
Type of AI (see description below). Optional.
23.800
The method will return the ID of the added
engine
upon success.
Type of AI
Type of AI
Array of parameters:
Parameter
Description
Version
code_alias
unknown
Type of AI. Available values: ChatGPT (Open AI)
model_context_type
unknown
Type of context counting. Available values: token - tokens, symbol - symbols. Default is token.
model_context_limit
unknown
Volume of context (default is 16K). Before sending your user request, the context limit is checked according to the counting type.
Examples
Examples
JS
PHP
BX24.js
try
{
const
response =
await
$b24.
callMethod
(
'ai.engine.register'
,
{
name
:
'Smith GPT'
,
code
:
'smith_gpt'
,
category
:
'text'
,
completions_url
:
'https://antonds.com/ai/aul/completions/'
,
settings
: {
code_alias
:
'ChatGPT'
,
model_context_type
:
'token'
,
model_context_limit
:
16
*
1024
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
'ai.engine.register'
,
[
'name'
=>
'Smith GPT'
,
'code'
=>
'smith_gpt'
,
'category'
=>
'text'
,
'completions_url'
=>
'https://antonds.com/ai/aul/completions/'
,
'settings'
=> [
'code_alias'
=>
'ChatGPT'
,
'model_context_type'
=>
'token'
,
'model_context_limit'
=>
16
*
1024
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
echo
'Success: '
.
print_r
(
$result
,
true
);
// Your required data processing logic
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
'Error registering AI engine: '
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
'ai.engine.register'
,
{
name
:
'Smith GPT'
,
code
:
'smith_gpt'
,
category
:
'text'
,
completions_url
:
'https://antonds.com/ai/aul/completions/'
,
settings
: {
code_alias
:
'ChatGPT'
,
model_context_type
:
'token'
,
model_context_limit
:
16
*
1024
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
{
console
.
error
(result.
error
());
}
else
{
console
.
info
(result.
data
());
}
}
);
Endpoint
Endpoint
Attention!
In the script, everything is in a single code flow, this is for example purposes. In
production
mode, it is necessary to separate the lines of code into a different section.
Template
for creating a custom endpoint can be used for customizing your own service.
Important points:
Important points:
The script must accept the request, process it quickly, and add it to its internal queue.
A service with the type "image" must send asynchronous requests.
It should be able to return various response statuses (as shown in the example):
200 — normal link transition;
202 — if you accepted the request and added it to the queue;
503 — if the service is unavailable.
A response is expected within a certain time, after which the callback becomes invalid.
Attention!
In addition to the response code, in case of successful generation, the handler must return
json_encode(['result' => 'OK'])
.
When working with the provider category
audio
, in the
prompt
key, you receive an array that includes the following elements:
file
: Link to the file. It is important to note that the file may have no extension.
fields
: An auxiliary internal array that contains:
type
: Content-type of the file, which is especially important if the file has no extension (e.g., "audio/ogg").
prompt
: An auxiliary prompt for the audio file, which may contain key information to assist in recognizing the file, such as your company name.
The provider also receives additional fields:
Fields
Description
Version
auth
Authorization data,
23.600.0
payload_raw
Raw value of the prompt (when using Copilot, there will be a character code of the used prompt)
23.600.0
payload_provider
Character code of the provider pre-prompt (when using Copilot, there will be prompt).
23.600.0
payload_prompt_text
If
payload_provider = prompt
, it will contain the raw instruction of the pre-prompt. This is the unprocessed pre-prompt for independent analysis. More details in the documentation on
prompts
.
23.800.0
payload_markers
Array of additional markers from the user (
original_message
,
user_message
,
language
), used when forming the prompt. More details in the documentation on
prompts
.
23.800.0
payload_role
Role (instruction) used when forming the prompt. In GPT-like systems, you should send this role as a system in the message array.
23.800.0
context
Array of preceding messages in chronological order. For example, a list of comments on a post. The first in such a context list is the author's message (the post itself). Important: The volume of context sent to your provider depends on the volume specified by you and the counting type (more details in the provider documentation). By default, the counting method is "tokens", volume 16K. You should send context to the neural network only if the parameter collect_context is set to true (1). In other cases, it is sent as additional information at your discretion.
23.800.0
max_tokens
Maximum number of lexemes. This parameter controls the length of the output. Optional.
temperature
*
Temperature. This parameter controls the randomness of the output (low values make the output more focused and deterministic). Required.
* - Required parameters
Example
Suppose you receive (in addition to other information) three data arrays.
prompt - contains the current request, this is just text;
payload_role - some text containing instructions;
context - an array (presumably also not empty).
In this case, the resulting array we obtain is:
[
[
"role"
:
"system"
,
"content"
:
"$payload_role"
]
,
[
// the entire context array, or part of it if you want to save the request
// but remember that it goes in chronological order (the most recent messages are at the bottom)
]
,
[
"role"
:
"user"
,
"content"
:
"$prompt"
// this is the current request, and it is NOT included in the context
]
]
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
AI in Bitrix24
Next
Get List of Services

---

## Get the list of services ai.engine.list

**Source:** https://apidocs.bitrix24.com/api-reference/ai/ai-engine-list

Get the list of services ai.engine.list | Bitrix24 REST API and Marketplace Applications
Get the list of services ai.engine.list
Get the list of services ai.engine.list
We are still updating this page
Some data may be missing here — we will fill it in shortly.
Scope:
ai_admin
Who can execute the method: administrator
The method without parameters returns a list of registered
engine
for the current partner. The method is called without parameters.
Examples
Examples
JS
PHP
BX24.js
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'ai.engine.list'
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
// fetchListMethod is preferred when working with large datasets. The method implements iterative selection using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'ai.engine.list'
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
// callMethod provides manual control over the process of paginated data retrieval through the start parameter. It is suitable for scenarios where precise control over request batches is required. However, with large volumes of data, it may be less efficient compared to fetchListMethod.
try
{
const
response =
await
$b24.
callMethod
(
'ai.engine.list'
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
'ai.engine.list'
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
echo
'Success: '
.
print_r
(
$result
,
true
);
// Your required data processing logic
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
'Error calling AI engine list: '
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
'ai.engine.list'
,
{
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
{
console
.
error
(result.
error
());
}
else
{
console
.
info
(result.
data
());
}
}
);
How to Use Examples in Documentation
Copied
Was the article helpful?
Yes
No
Previous
Register Service
Next
Unregister Service

---

## Delete service ai.engine.unregister

**Source:** https://apidocs.bitrix24.com/api-reference/ai/ai-engine-unregister

Delete service ai.engine.unregister | Bitrix24 REST API and Marketplace Applications
Delete service ai.engine.unregister
Delete service ai.engine.unregister
Examples
Response in case of success
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
ai_admin
Who can execute the method: administrator
Method to delete
engine
.
Parameters
Description
code
unknown
Engine code
Examples
Examples
JS
PHP
BX24.js
try
{
const
response =
await
$b24.
callMethod
(
'ai.engine.unregister'
,
{
code
:
'smith_gpt'
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
'ai.engine.unregister'
,
[
'code'
=>
'smith_gpt'
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
// Your required data processing logic
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
'Error unregistering AI engine: '
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
'ai.engine.unregister'
,
{
code
:
'smith_gpt'
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
{
console
.
error
(result.
error
());
}
else
{
console
.
info
(result.
data
());
}
}
);
How to Use Examples in Documentation
Response in case of success
Response in case of success
On success, returns
true
.
Copied
Was the article helpful?
Yes
No
Previous
Get List of Services
Next
About Prompts for CoPilot

---

## About Prompts for CoPilot

**Source:** https://apidocs.bitrix24.com/api-reference/ai/prompts/index

About Prompts for CoPilot | Bitrix24 REST API and Marketplace Applications
About Prompts for CoPilot
About Prompts for CoPilot
We are still updating this page
Some data may be missing here — we will complete it soon.
Even though neural networks are quite intelligent creations, it's important to know how to communicate with them effectively. The average user cannot (and essentially should not) know how to do this. This is where so-called pre-prompts come into play.
Pre-prompts
are texts that supplement the user’s request.
Proper emphasis in such a pre-prompt guides the neural network on what exactly it needs to do, even if the user has not articulated their thoughts very clearly. A more practical example is when a user simply presses the "translate" button, and we need to create a pre-prompt for accurate translation behind the scenes.
In this section of the documentation, we will explain what pre-prompts are, how to write them, and how to register them via REST.
Method
Description
ai.prompt.register
Adds a prompt
ai.prompt.unregister
Removes a prompt
Was the article helpful?
Yes
No
Previous
Unregister Service
Next
Add Prompt

---

## Add Prompt ai.prompt.register

**Source:** https://apidocs.bitrix24.com/api-reference/ai/prompts/ai-prompt-register

Add Prompt ai.prompt.register | Bitrix24 REST API and Marketplace Applications
Add Prompt ai.prompt.register
Add Prompt ai.prompt.register
Category
Examples
Success response
Error response
Typical use-cases and scenarios
We are still updating this page
Some data may be missing — we will fill it in shortly.
Scope:
ai_admin
Who can execute the method: administrator
The method
ai.prompt.register
adds a prompt.
Parameter
Description
category
unknown
The category of the embedding location. CoPilot can be located in various parts of the product. The list of categories is provided
below
code
unknown
A unique code for the prompt. The code must use the prefix
rest_
. This code is set once during registration and cannot be changed afterward.
The pre-prompt can only be updated through its
deletion
icon
unknown
Icon code. You can find a suitable icon in the file
copilot_icons.pdf
prompt
unknown
The text of the prompt. This is what will be sent to the neural network (the user will not see it). The pre-prompt text can use special formatting:
markers
and
conditions
translate
unknown
An array of translations for the item in different languages. Ideally, support at least two languages: English (en) and the portal's language. Support for other languages is at your discretion
parent_code
unknown
The code of the parent section. The code must use the prefix
rest_
sort
unknown
Sorting, specified optionally. Responsible for sorting items among themselves
section
unknown
The category in the prompt menu for visual separation. It can have the following values:
create — "Create from text" category
edit — "Edit text" category
If nothing is specified, the prompt will be placed above these categories
Category
Category
Embedding location category
Where it will appear in CoPilot
livefeed
News feed post
livefeed_comments
Comment on one of the news feed posts
tasks
Task description
tasks_comments
Comment on one of the tasks
chat
Message in one-on-one or group chats
mail
Emails from the personal inbox
mail_crm
Emails with CRM clients in the deal, contact, or company cards
landing
Texts in the Bitrix24 site builder
Examples
Examples
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
// example for cURL (Webhook)
// example for cURL (OAuth)
try
{
const
response =
await
$b24.
callMethod
(
'ai.prompt.register'
,
{
category
: [
"livefeed"
,
"livefeed_comments"
],
code
:
'rest_joke'
,
icon
:
'smile'
,
prompt
:
'Tell a joke'
,
translate
: {
"en"
:
"A joke"
,
"de"
:
"Ein Witz"
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
'ai.prompt.register'
,
[
'category'
=> [
"livefeed"
,
"livefeed_comments"
],
'code'
=>
'rest_joke'
,
'icon'
=>
'smile'
,
'prompt'
=>
'Tell a joke'
,
'translate'
=> [
"en"
=>
"A joke"
,
"de"
=>
"Ein Witz"
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
'Error registering AI prompt: '
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
'ai.prompt.register'
,
{
category
: [
"livefeed"
,
"livefeed_comments"
],
code
:
'rest_joke'
,
icon
:
'smile'
,
prompt
:
'Tell a joke'
,
translate
: {
"en"
:
"A joke"
,
"de"
:
"Ein Witz"
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
{
console
.
error
(result.
error
());
}
else
{
console
.
info
(result.
data
());
}
}
);
// example for php
How to Use Examples in Documentation
Success response
Success response
Error response
Error response
Typical use-cases and scenarios
Typical use-cases and scenarios
Add a New Prompt "Joke"
Copied
Was the article helpful?
Yes
No
Previous
About Prompts for CoPilot
Next
Remove Prompt

---

## Unregister AI Prompt ai.prompt.unregister

**Source:** https://apidocs.bitrix24.com/api-reference/ai/prompts/ai-prompt-unregister

Unregister AI Prompt ai.prompt.unregister | Bitrix24 REST API and Marketplace Applications
Unregister AI Prompt ai.prompt.unregister
Unregister AI Prompt ai.prompt.unregister
Examples
Success Response
Error Response
Typical use-cases and scenarios
We are still updating this page
Some data may be missing — we will complete it shortly.
Scope:
ai_admin
Who can execute the method: administrator
The method
ai.prompt.unregister
removes a prompt.
Parameter
Description
code
*
unknown
Unique prompt code. Always has the prefix
rest_
. This code is set once during registration and cannot be changed afterwards
Required parameters are marked with *
Examples
Examples
cURL (Webhook)
cURL (OAuth)
JS
PHP
BX24.js
PHP CRest
// example for cURL (Webhook)
// example for cURL (OAuth)
try
{
const
response =
await
$b24.
callMethod
(
'ai.prompt.unregister'
,
{
code
:
'rest_joke_wolf'
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
'ai.prompt.unregister'
,
[
'code'
=>
'rest_joke_wolf'
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
// Your data processing logic
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
'Error unregistering AI prompt: '
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
'ai.prompt.unregister'
,
{
code
:
'rest_joke_wolf'
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
{
console
.
error
(result.
error
());
}
else
{
console
.
info
(result.
data
());
}
}
);
// example for PHP
How to Use Examples in Documentation
Success Response
Success Response
Error Response
Error Response
Typical use-cases and scenarios
Typical use-cases and scenarios
Add a New Prompt "Joke"
Copied
Was the article helpful?
Yes
No
Previous
Add Prompt
Next
Markers in Prompts

---

## Markers in Prompts

**Source:** https://apidocs.bitrix24.com/api-reference/ai/prompts/markers

Markers in Prompts | Bitrix24 REST API and Marketplace Applications
Basic Markers
Markers in Prompts
Basic Markers
Additional Markers
Author Markers
Markers of the Current Result
We are still updating this page
Some data may be missing — we will fill it in shortly.
Below is the instruction on the markers that our AI module understands and can correctly interpret for the neural network.
Basic Markers
Basic Markers
{original_message}
— the original message for the pre-prompt. In the text editor architecture, this is all the text typed or the manually selected part of the typed text.
Example of a pre-prompt:
Continue the text: {original_message}
As a result, the text will be continued based on the text typed above or the manually selected part of the text.
{user_input}
— what the user has directly entered.
Example of a pre-prompt:
Write a story about {user_message}
These markers can also be used together:
Write a story about {user_message} continuing the text: {original_message}.
{role}{/role}
— a paired marker that indicates the neural network's role. Inside, the text is set in free form, giving the neural network some instructions. For example, "speak like a robot." On one hand, it seems that the same can be written simply in the pre-prompt. On the other hand, instructions are still instructions, and neural networks take them more seriously.
Features of using the role marker:
Other markers can be used inside the instruction
Only the first instruction is used; the others are simply cut out
The marker is added after
if-conditions
, meaning one
{role}
block can be used for
if
and another for
else
Additional Markers
Additional Markers
{author_message}
— the text of the original post or task description.
Example:
Highlight the main points based on the text: {author_message}
{context_messages}
— the context "how much will fit." For example, the original post + all recent comments, or chat correspondence over a certain period. Or task description + comments on it.
Example:
Formulate the task result based on its description and comments: {context_messages}
These are all the basic markers that can be expanded by developers, but it's better not to rely on that (unless a mutually beneficial agreement is in place).
{language}
— the language of the account (not the user!). For example, German, English, Spanish — these values will replace the marker.
Example of a pre-prompt:
Translate the text into {language}. Text: {original_message}
Author Markers
Author Markers
When we work with contextual messages, each message from the context has an author, their position, and other characteristics. Since the author is a user, we can use the user's string fields. A list of such fields can be obtained using the
user.fields
method.
When writing a marker, one rule must be followed. Everything should be in lowercase:
{author.lower_case_field}
.
Let's look at an example. We will use the NAME and WORK_POSITION fields of the author in the pre-prompt:
Praise the author.
The post you need to praise: {original_message}
Author's name: {author.name}
Author's position: {author.work_position}
Markers of the Current Result
Markers of the Current Result
During the operation of CoPilot, a mini-dialog occurs. You ask a question (or work with text), and you receive a result that you can continue to work with.
A set of results is formed, which you can refer to in the markers. Currently, the stack size is three messages.
This set has several features:
It is filled from the bottom up, meaning the most recent result is at the bottom.
The most recent result is the one that was visible at the moment of sending the new request (not the one that will be received at the moment of the request).
Numbering starts from zero.
Example:
{current_result_0} — the result that was visible at the moment of sending the request (using the prompt)
{current_result_1} — the previous such result
{current_result_2} — the result before the previous one
If any markers are still empty, they are cut out from the text.
Copied
Was the article helpful?
Yes
No
Previous
Remove Prompt
Next
Conditions in Prompts

---

## Conditions in Prompts

**Source:** https://apidocs.bitrix24.com/api-reference/ai/prompts/conditions

Conditions in Prompts | Bitrix24 REST API and Marketplace Applications
Conditions
Conditions in Prompts
Conditions
System Fields
Checking for Null
Negation
Working with Basic Markers
Working with Result Markers
Functions Inside If-Conditions
Setter Functions
Branching
We are still updating this page
Some data may be missing here — we will fill it in shortly.
In the pre-prompt, similar to programming, you can use
if
conditions and
switch
branching.
Conditions
Conditions
Let's start with an example:
@
if
(engine.
code
=
ChatGPT
)
Speak
on behalf
of
the
Automation
rule.
@
else
Speak
on behalf
of
a person.
@endif
As a result, depending on the selected provider on the account, the final pre-prompt will differ.
What can you write in the
@if ()
condition? Let's take a look below. Case sensitivity and extra spaces do not matter.
System Fields
System Fields
engine.code
— provider code (ChatGPT,
ThirdParty
)
engine.category
— can take values text or image. However, currently, CoPilot pre-prompts only work for text.
context.module
— the module that calls CoPilot. For example, you can modify the pre-prompt differently if the request is for the CRM module.
An example of a condition based on a system field was at the beginning of the page. Here’s another one:
@
if
(engine.
code
=
ChatGPT
)
Don
't forget that you are ChatGPT.
@endif
Checking for Null
Checking for Null
@
if
(author.
name
=
null
)
speak on behalf
of
an anonymous user.
@endif
Negation
Negation
@
if
(engine.
code
!=
ChatGPT
)
{context_messages}
@endif
Working with Basic Markers
Working with Basic Markers
These are
basic markers
, as well as pre-installed markers by the developer. However, since they contain user content, it makes sense to use them only for checking for null.
@
if
(marker.
original_message
!=
null
)
praise
for
{original_message}
@
else
praise
for
{user_message}
@endif
On the other hand, through marker checking, you can rely on some system pre-installed marker that is always set by the developer under certain conditions.
@
if
(marker.
role
= vip)
write very importantly.
@endif
Working with Result Markers
Working with Result Markers
You can find information about result markers on the documentation page about
markers
.
How to use them in conditions? Logically, you can only use them for null checks. For example:
@
if
(current_result0 !=
null
)
This
is not the user
's first clarification, please be more careful!
@endif
An important clarification — you should only check the availability of the marker for your logic. A statement like this:
@
if
(current_result0 !=
null
)
{current_result0}
@endif
is meaningless, as if the marker is absent, it will automatically be removed from the text.
Functions Inside If-Conditions
Functions Inside If-Conditions
You can use functions inside the if-expression condition. Currently, only the length definition
length()
is supported. You can pass any marker into this function, including user-defined ones.
@
if
(
length
(marker.
user_message
) <
10
)
The
final response should be very concise.
@
else
Write
like
Tolstoy
.
@endif
{user_message}
Setter Functions
Setter Functions
Inside prompts, you can set temperature and tokens. Moreover, they can be different depending on
conditions
.
@setTemperature()
@setTokens()
Let's enhance the example from the previous section about functions using setters:
@
if
(
length
(marker.
user_message
) <
10
)
The
final response should be very concise.
@
setTemperature
(
0.12
)
@
setTokens
(
200
)
@
else
Write
like
Tolstoy
.
@
setTemperature
(
1
)
@
setTokens
(
1200
)
@endif
Branching
Branching
This is the well-known
switch
in programming. It comes in handy when you have different prompt blocks, but each of them is executed strictly in a certain order. A good example is when you have different prompt texts for different providers. Let's consider this example.
@
switch
(engine.
code
)
@
case
(
ChatGPT
)
**instructions
for
GPT
**
@
case
(anotherGPT)
**instructions
for
anotherGPT**
@
default
**instructions
for
other providers**
@endswitch
What can you insert into
switch
? Everything that you can in
if
.
The branching condition has the highest priority, meaning that if-expressions can be included within case blocks. There can be multiple branching blocks, although this may reduce readability.
Example of combined use of switch and if:
@
switch
(engine.
code
)
@
case
(
ChatGPT
)
you are a pig
@
if
(author.
personalgender
= m) pink @
else
blue @endif
@
case
(anotherGPT)
you are a bear
@
default
you are a wolf
@endswitch
@
switch
(engine.
code
)
@
case
(
ChatGPT
)
from
Pluto
@
case
(anotherGPT)
from
Jupiter
@
default
@
if
(author.
personalgender
= m)
from
Mars
@
else
from
Venus
@endif
@endswitch
ThirdParty — "third party". That is, this can be the code of a third-party provider developed by a partner.
These can be both if-conditions and switch branching.
Copied
Was the article helpful?
Yes
No
Previous
Markers in Prompts
Next
CRM Objects and Methods

---

