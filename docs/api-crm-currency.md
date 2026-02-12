---
description: 'CRM Currency: Exchange rates, localizations, base currency'
methods:
- crm.automatedsolution.delete
- crm.currency.add
- crm.currency.base.get
- crm.currency.base.set
- crm.currency.delete
- crm.currency.fields
- crm.currency.get
- crm.currency.list
- crm.currency.localizations.
- crm.currency.localizations.delete
- crm.currency.localizations.fields
- crm.currency.localizations.get
- crm.currency.localizations.set
- crm.currency.update
- event.bind
pages: 18
title: 'CRM Currency: Exchange rates, localizations, base currency'
---
# CRM Currency: Exchange rates, localizations, base currency
> CRM Currency: Exchange rates, localizations, base currency
> **18 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Currencies in CRM: Overview of Methods](#currencies-in-crm-overview-of-methods)
- [Add Currency crm.currency.add](#add-currency-crmcurrencyadd)
- [Update Currency crm.currency.update](#update-currency-crmcurrencyupdate)
- [Get Currency by ID crm.currency.get](#get-currency-by-id-crmcurrencyget)
- [Get the list of currencies crm.currency.list](#get-the-list-of-currencies-crmcurrencylist)
- [Delete Currency crm.currency.delete](#delete-currency-crmcurrencydelete)
- [Get Currency Fields crm.currency.fields](#get-currency-fields-crmcurrencyfields)
- [Get the Symbolic Identifier of the Base Currency crm.currency.base.get](#get-the-symbolic-identifier-of-the-base-currency-c)
- [Set Currency as Base crm.currency.base.set](#set-currency-as-base-crmcurrencybaseset)
- [Currency Localization in CRM: Overview of Methods](#currency-localization-in-crm-overview-of-methods)
- [Get Currency Localizations crm.currency.localizations.get](#get-currency-localizations-crmcurrencylocalization)
- [Set Localizations for Currency crm.currency.localizations.set](#set-localizations-for-currency-crmcurrencylocaliza)
- [Delete currency localizations crm.currency.localizations.delete](#delete-currency-localizations-crmcurrencylocalizat)
- [Get Currency Localization Fields crm.currency.localizations.fields](#get-currency-localization-fields-crmcurrencylocali)
- [Overview of Events When Working with Currencies](#overview-of-events-when-working-with-currencies)
- [Event when adding currency onCrmCurrencyAdd](#event-when-adding-currency-oncrmcurrencyadd)
- [Event onCrmCurrencyUpdate](#event-oncrmcurrencyupdate)
- [Event onCrmCurrencyDelete](#event-oncrmcurrencydelete)

---

## Currencies in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/index

Currencies in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Currencies in CRM: Overview of Methods
Currencies in CRM: Overview of Methods
Currency Relation to CRM Objects
Base Currency
Currency Exchange Rate
Currency Localization
Overview of Methods
Currency in CRM helps to work with clients from different countries. For example, the primary currency in which the company conducts transactions is rubles. The manager adds products priced in rubles to the deal, while the client pays in their preferred currency—tenge. The manager simply needs to change the currency of the deal in the detail form—Bitrix will automatically calculate the cost of the products in tenge based on the exchange rate set in the settings.
Quick navigation:
all methods and events
User documentation:
currencies in Bitrix24
Currency Relation to CRM Objects
Currency Relation to CRM Objects
Products.
The price of a product item can be specified through
price methods
. All price type fields are composite—the amount and currency are changed separately. To specify or change the currency, use the
currency
parameter and pass the currency identifier in the format
RUB
.
Standard field "Amount and Currency."
This field shows the total amount of products and the currency in
deals
,
leads
,
invoices
,
estimates
, and
SPAs
. The
Amount and Currency
field is composite, with the amount and currency changing separately. To specify or change the currency, use the
CURRENCY_ID
parameter and pass the currency identifier in the format
RUB
.
Custom field of type "Money."
To specify or change the currency value, pass the amount and currency code in the format
100|RUB
.
Base Currency
Base Currency
The base currency is the currency in which the company conducts transactions.
If you create or modify a CRM entity without passing the currency code, the base currency is set automatically.
If you change the currency in the field, the amount will be recalculated based on the base currency exchange rate.
To find out the base currency, use the method
crm.currency.base.get
. To change the base currency, use the method
crm.currency.base.set
.
Currency Exchange Rate
Currency Exchange Rate
The exchange rate of any currency in Bitrix is calculated in relation to the base currency.
When you change the base currency, the exchange rate ratios are not recalculated automatically.
To change the exchange rate of a currency to the base, use the currency update method—
crm.currency.update
. Set the ratio in the
AMOUNT
parameter.
Currency Localization
Currency Localization
Currency localization refers to the rules for writing numbers and placing the currency symbol in different languages.
To change or remove currency localization settings, use the group of methods
crm.currency.localizations.*
.
Overview of Methods
Overview of Methods
Scope:
crm
Who can execute the method: depends on the method
Methods
Events
Method
Description
crm.currency.add
Creates a new currency
crm.currency.update
Updates an existing currency
crm.currency.get
Returns currency by symbolic identifier
crm.currency.list
Returns a list of currencies
crm.currency.delete
Deletes a currency
crm.currency.fields
Returns the description of currency fields
crm.currency.base.get
Gets the symbolic identifier of the base currency
crm.currency.base.set
Changes the base currency
Event
Triggered
onCrmCurrencyAdd
When a currency is created
onCrmCurrencyUpdate
When a currency is updated
onCrmCurrencyDelete
When a currency is deleted
Copied
Was the article helpful?
Yes
No
Previous
Get directory fields
Next
Add Currency

---

## Add Currency crm.currency.add

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/crm-currency-add

Add Currency crm.currency.add | Bitrix24 REST API and Marketplace Applications
Method Parameters
Add Currency crm.currency.add
Method Parameters
Parameter fields
Parameter LANG
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to modify CRM settings
This method adds a new currency.
For the languages used on the account, localization parameters must be specified. If not provided,
default parameters
will be used. Localization parameters for a specific language can be set using the
crm.currency.localizations.set
method.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
fields
*
object
Field values (detailed description provided
below
) for adding a new currency in the form of a structure:
fields
: {
CURRENCY
:
'value'
,
BASE
:
'value'
,
AMOUNT_CNT
:
'value'
,
AMOUNT
:
'value'
SORT
:
'value'
LANG
:
'value'
}
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
CURRENCY
*
string
Currency identifier.
Corresponds to the ISO 4217 standard
BASE
string
Indicates whether the currency is base.
Possible values:
Y
— yes
N
— no
Default value is
N
.
Warning
It is not recommended to change the base currency via REST. Otherwise, it will be necessary to change the rates of all currencies.
AMOUNT_CNT
*
int
Denomination. Typically,
1
or a multiple of
10
is used as the denomination.
AMOUNT
*
double
Exchange rate relative to the base currency.
SORT
int
Position in the currency list.
Default value is
100
.
LANG
object
Currency localization parameters.
An object in the format
{"lang_1": "value_1", ... "lang_N": "value_N"}
, where
lang_N
is the language identifier, and
value
is an object of type
crm_currency_localization
.
If not all languages are specified,
default localization parameters
will be used for the remaining ones.
Parameter LANG
Parameter LANG
Name
type
Description
DECIMALS
*
int
Number of decimal places in the fractional part.
DEC_POINT
string
Decimal point for output.
FORMAT_STRING
string
Format template.
FULL_NAME
string
Name of the currency in the language for which localization is added.
HIDE_ZERO
string
Indicates whether to hide insignificant zeros.
THOUSANDS_SEP
string
Thousands separator.
THOUSANDS_VARIANT
string
Code for the thousands separator.
Allowed values are described in the
reference
.
Code Examples
Code Examples
Creating the yuan with localization parameters (Russian and English languages)
The base currency is the ruble. The exchange rate for the yuan is 12.2251 rubles for 1 yuan.
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"CURRENCY":"CNY","BASE":"N","AMOUNT":12.2251,"AMOUNT_CNT":1,"SORT":9000,"LANG":{"ru":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"# CNY","FULL_NAME":"yuan","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"S"},"en":{"DECIMALS":2,"DEC_POINT":",","FORMAT_STRING":"# CNY","FULL_NAME":"yuan","HIDE_ZERO":"Y","THOUSANDS_SEP":"."}}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"CURRENCY":"CNY","BASE":"N","AMOUNT":12.2251,"AMOUNT_CNT":1,"SORT":9000,"LANG":{"ru":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"# CNY","FULL_NAME":"yuan","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"S"},"en":{"DECIMALS":2,"DEC_POINT":",","FORMAT_STRING":"# CNY","FULL_NAME":"yuan","HIDE_ZERO":"Y","THOUSANDS_SEP":"."}}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.add
BX24
.
callMethod
(
"crm.currency.add"
,
{
fields
: {
CURRENCY
:
'CNY'
,
BASE
:
'N'
,
AMOUNT
:
12.2251
,
AMOUNT_CNT
:
1
,
SORT
:
9000
,
LANG
: {
ru
: {
DECIMALS
:
2
,
DEC_POINT
:
'.'
,
FORMAT_STRING
:
'# CNY'
,
FULL_NAME
:
'yuan'
,
HIDE_ZERO
:
'Y'
,
THOUSANDS_VARIANT
:
'S'
,
},
en
: {
DECIMALS
:
2
,
DEC_POINT
:
','
,
FORMAT_STRING
:
'# CNY'
,
FULL_NAME
:
'yuan'
,
HIDE_ZERO
:
'Y'
,
THOUSANDS_SEP
:
'.'
,
},
},
}
},
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.add'
,
[
'fields'
=> [
'CURRENCY'
=>
'CNY'
,
'BASE'
=>
'N'
,
'AMOUNT'
=>
12.2251
,
'AMOUNT_CNT'
=>
1
,
'SORT'
=>
9000
,
'LANG'
=> [
'ru'
=> [
'DECIMALS'
=>
2
,
'DEC_POINT'
=>
'.'
,
'FORMAT_STRING'
=>
'# CNY'
,
'FULL_NAME'
=>
'yuan'
,
'HIDE_ZERO'
=>
'Y'
,
'THOUSANDS_VARIANT'
=>
'S'
,
],
'en'
=> [
'DECIMALS'
=>
2
,
'DEC_POINT'
=>
','
,
'FORMAT_STRING'
=>
'# CNY'
,
'FULL_NAME'
=>
'yuan'
,
'HIDE_ZERO'
=>
'Y'
,
'THOUSANDS_SEP'
=>
'.'
,
],
],
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
Creating the Indonesian rupiah
Assuming the base currency is the ruble. The currency has a very low exchange rate — 1 rupiah is equivalent to 0.00548 rubles. In this case, we increase the denomination (AMOUNT_CNT) to set the rate with the required precision.
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"CURRENCY":"IDR","AMOUNT":54.8738,"AMOUNT_CNT":10000,"SORT":8000,"LANG":{"ru":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"Rp#","FULL_NAME":"rupiah","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"C"},"en":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"# CNY","FULL_NAME":"rupee","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"C"}}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.add
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"fields":{"CURRENCY":"IDR","AMOUNT":54.8738,"AMOUNT_CNT":10000,"SORT":8000,"LANG":{"ru":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"Rp#","FULL_NAME":"rupiah","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"C"},"en":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"# CNY","FULL_NAME":"rupee","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"C"}}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.add
BX24
.
callMethod
(
"crm.currency.add"
,
{
fields
: {
CURRENCY
:
'IDR'
,
AMOUNT
:
54.8738
,
AMOUNT_CNT
:
10000
,
SORT
:
8000
,
LANG
: {
ru
: {
DECIMALS
:
2
,
DEC_POINT
:
'.'
,
FORMAT_STRING
:
'Rp#'
,
FULL_NAME
:
'rupiah'
,
HIDE_ZERO
:
'Y'
,
THOUSANDS_VARIANT
:
'C'
},
en
: {
DECIMALS
:
2
,
DEC_POINT
:
'.'
,
FORMAT_STRING
:
'# CNY'
,
FULL_NAME
:
'rupee'
,
HIDE_ZERO
:
'Y'
,
THOUSANDS_VARIANT
:
'C'
}
}
}
},
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.add'
,
[
'fields'
=> [
'CURRENCY'
=>
'IDR'
,
'AMOUNT'
=>
54.8738
,
'AMOUNT_CNT'
=>
10000
,
'SORT'
=>
8000
,
'LANG'
=> [
'ru'
=> [
'DECIMALS'
=>
2
,
'DEC_POINT'
=>
'.'
,
'FORMAT_STRING'
=>
'Rp#'
,
'FULL_NAME'
=>
'rupiah'
,
'HIDE_ZERO'
=>
'Y'
,
'THOUSANDS_VARIANT'
=>
'C'
,
],
'en'
=> [
'DECIMALS'
=>
2
,
'DEC_POINT'
=>
'.'
,
'FORMAT_STRING'
=>
'# CNY'
,
'FULL_NAME'
=>
'rupee'
,
'HIDE_ZERO'
=>
'Y'
,
'THOUSANDS_VARIANT'
=>
'C'
,
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
"CNY"
,
"time"
:
{
"start"
:
1717684463.467685
,
"finish"
:
1717684465.282238
,
"duration"
:
1.8145530223846436
,
"processing"
:
0.12580394744873047
,
"date_start"
:
"2024-06-06T16:34:23+02:00"
,
"date_finish"
:
"2024-06-06T16:34:25+02:00"
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
crm_currency.CURRENCY
Identifier of the created currency.
time
time
Information about the request execution time.
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
""
,
"error_description"
:
"Access denied."
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
Empty string
Access denied.
Insufficient access rights.
Empty string
The "Currency" module is not found! Please install the "Currency" module.
ERROR_CORE
Undefined array key "#FIELD#"
Required field #FIELD# is not specified (the missing field code will be substituted instead of #FIELD#)
ERROR_CORE
Other errors in the data for creating the currency.
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
Update Currency crm.currency.update
Get Currency by ID crm.currency.get
Get the list of currencies crm.currency.list
Delete Currency crm.currency.delete
Get Currency Fields crm.currency.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Update Currency

---

## Update Currency crm.currency.update

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/crm-currency-update

Update Currency crm.currency.update | Bitrix24 REST API and Marketplace Applications
Parameters
Update Currency crm.currency.update
Parameters
Parameter fields
Parameter LANG
Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to modify CRM settings
This method updates an existing currency.
Parameters
Parameters
Name
type
Description
ID
string
Currency identifier.
Corresponds to the ISO 4217 standard.
The identifier can be obtained using the
crm.currency.list
method.
fields
object
Field values (detailed description provided
below
) for updating the currency in the following structure:
fields
: {
SORT
:
'value'
AMOUNT_CNT
:
'value'
,
AMOUNT
:
'value'
BASE
:
'value'
,
LANG
: {
lang_1
: {
DECIMALS
:
'value'
,
DEC_POINT
:
'value'
,
...
},
...
lang_N
: {
...
}
}
}
Parameter fields
Parameter fields
Required parameters are marked with *
Name
type
Description
SORT
integer
Position in the currency list.
Default value is
100
AMOUNT_CNT
*
integer
Denomination. Typically,
1
or a multiple of
10
is used as the denomination.
AMOUNT
*
double
Exchange rate relative to the base currency.
BASE
string
Indicates whether the currency is a base currency.
Possible values:
Y
— yes
N
— no
Default value is
N
.
Warning
It is not recommended to change the base currency via REST. Otherwise, you will need to change the rates of all currencies.
LANG
object
Currency localization parameters.
An object in the format
{"lang_1": "value_1", ... "lang_N": "value_N"}
, where
lang_N
is the language identifier, and
value
is an object of type
crm_currency_localization
.
If not all languages are specified, the remaining ones will use
default localization parameters
.
Parameter LANG
Parameter LANG
Name
type
Description
DECIMALS
*
int
Number of decimal places in the fractional part.
DEC_POINT
string
Decimal point for output.
FORMAT_STRING
string
Format template.
FULL_NAME
string
Name of the currency in the language for which localization is added.
HIDE_ZERO
string
Indicates whether to hide insignificant zeros.
THOUSANDS_SEP
string
Thousands separator.
THOUSANDS_VARIANT
string
Code for the thousands separator.
Refer to the
crm_currency_localization
documentation for acceptable values.
Examples
Examples
Changing the exchange rate of the yuan relative to the base currency.
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":"CNY","fields":{"AMOUNT":15.3449}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":"CNY","fields":{"AMOUNT":15.3449},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.update
BX24
.
callMethod
(
"crm.currency.update"
,
{
ID
:
'CNY'
,
fields
: {
AMOUNT
:
15.3449
,
}
},
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.update'
,
[
'ID'
=>
'CNY'
,
'fields'
=> [
'AMOUNT'
=>
15.3449
,
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
Changing the localizations of the currency (using the example of the US dollar)
After executing this example, the localizations for the currency USD will be changed (or added) only for English and German languages. Localizations for other languages, if they existed, will not be changed.
This example is similar to the operation of the
crm.currency.localizations.set
method.
How to Use Examples in Documentation
cURL (Webhook)
cURL (OAuth)
JS
PHP
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":"USD","fields":{"LANG":{"en":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"$#","FULL_NAME":"US Dollar","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"S"},"de":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"# $","FULL_NAME":"US-Dollar","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"C"}}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.update
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"ID":"USD","fields":{"LANG":{"en":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"$#","FULL_NAME":"US Dollar","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"S"},"de":{"DECIMALS":2,"DEC_POINT":".","FORMAT_STRING":"# $","FULL_NAME":"US-Dollar","HIDE_ZERO":"Y","THOUSANDS_VARIANT":"C"}}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.update
BX24
.
callMethod
(
"crm.currency.update"
,
{
ID
:
'USD'
,
fields
: {
LANG
: {
en
: {
DECIMALS
:
2
,
DEC_POINT
:
'.'
,
FORMAT_STRING
:
'$#'
,
FULL_NAME
:
'US Dollar'
,
HIDE_ZERO
:
'Y'
,
THOUSANDS_VARIANT
:
'S'
},
de
: {
DECIMALS
:
2
,
DEC_POINT
:
'.'
,
FORMAT_STRING
:
'# $'
,
FULL_NAME
:
'US-Dollar'
,
HIDE_ZERO
:
'Y'
,
THOUSANDS_VARIANT
:
'C'
}
}
}
}
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.update'
,
[
'ID'
=>
'USD'
,
'fields'
=> [
'LANG'
=> [
'en'
=> [
'DECIMALS'
=>
2
,
'DEC_POINT'
=>
'.'
,
'FORMAT_STRING'
=>
'$#'
,
'FULL_NAME'
=>
'US Dollar'
,
'HIDE_ZERO'
=>
'Y'
,
'THOUSANDS_VARIANT'
=>
'S'
,
],
'de'
=> [
'DECIMALS'
=>
2
,
'DEC_POINT'
=>
'.'
,
'FORMAT_STRING'
=>
'# $'
,
'FULL_NAME'
=>
'US-Dollar'
,
'HIDE_ZERO'
=>
'Y'
,
'THOUSANDS_VARIANT'
=>
'C'
,
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
1717764521.938284
,
"finish"
:
1717764522.516576
,
"duration"
:
0.5782921314239502
,
"processing"
:
0.07656002044677734
,
"date_start"
:
"2024-06-07T14:48:41+02:00"
,
"date_finish"
:
"2024-06-07T14:48:42+02:00"
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
Result of the currency update.
time
time
Information about the request execution time.
Error Handling
Error Handling
HTTP status:
400
{
"error"
:
""
,
"error_description"
:
"Access denied."
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
Empty string
Access denied.
Insufficient access rights.
Empty string
The "Currency" module is not found! Please install the "Currency" module.
ERROR_CODE
Other errors in the data for changing the currency.
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
Add Currency crm.currency.add
Get Currency by ID crm.currency.get
Get the list of currencies crm.currency.list
Delete Currency crm.currency.delete
Get Currency Fields crm.currency.fields
Copied
Was the article helpful?
Yes
No
Previous
Add Currency
Next
Get Currency by ID

---

## Get Currency by ID crm.currency.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/crm-currency-get

Get Currency by ID crm.currency.get | Bitrix24 REST API and Marketplace Applications
Get Currency by ID crm.currency.get
Get Currency by ID crm.currency.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to CRM settings
This method retrieves currency data by its symbolic identifier
id
according to ISO 4217.
Note
Localization parameters (settings dependent on language) will be returned for the current account language.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
crm_currency.CURRENCY
Symbolic identifier of the currency.
Corresponds to the ISO 4217 standard.
Can be obtained using the
crm.currency.list
method
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
'{"id":"USD"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"USD","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.get
try
{
const
response =
await
$b24.
callMethod
(
"crm.currency.get"
,
{
id
:
"USD"
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
'crm.currency.get'
,
[
'id'
=>
'USD'
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
'Error calling crm.currency.get: '
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
"crm.currency.get"
,
{
id
:
"USD"
},
)
.
then
(
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
log
(result.
data
());
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.get'
,
[
'id'
=>
'USD'
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
"CURRENCY"
:
"USD"
,
"AMOUNT_CNT"
:
"1"
,
"AMOUNT"
:
"1.0000"
,
"SORT"
:
"100"
,
"BASE"
:
"Y"
,
"FULL_NAME"
:
"United States Dollar"
,
"LID"
:
"de"
,
"FORMAT_STRING"
:
"# $"
,
"DEC_POINT"
:
"."
,
"THOUSANDS_SEP"
:
"&nbsp;"
,
"DECIMALS"
:
"2"
,
"DATE_UPDATE"
:
"2024-01-29T12:28:40+02:00"
,
"LANG"
:
{
"en"
:
{
"FORMAT_STRING"
:
"$#"
,
"FULL_NAME"
:
"United States Dollar"
,
"DEC_POINT"
:
"."
,
"THOUSANDS_SEP"
:
null
,
"DECIMALS"
:
"2"
,
"THOUSANDS_VARIANT"
:
"C"
,
"HIDE_ZERO"
:
"Y"
}
,
"de"
:
{
"FORMAT_STRING"
:
"# $"
,
"FULL_NAME"
:
"United States Dollar"
,
"DEC_POINT"
:
"."
,
"THOUSANDS_SEP"
:
"&nbsp;"
,
"DECIMALS"
:
"2"
,
"THOUSANDS_VARIANT"
:
"B"
,
"HIDE_ZERO"
:
"Y"
}
}
}
,
"time"
:
{
"start"
:
1718357792.091095
,
"finish"
:
1718357792.889212
,
"duration"
:
0.79811692237854
,
"processing"
:
0.10800814628601074
,
"date_start"
:
"2024-06-14T11:36:32+02:00"
,
"date_finish"
:
"2024-06-14T11:36:32+02:00"
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
crm_currency
Object with currency data
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
""
,
"error_description"
:
"Not found"
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
Empty string
Access denied.
Insufficient access permissions
Empty string
Not found
Currency with the specified code not found
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
Add Currency crm.currency.add
Update Currency crm.currency.update
Get the list of currencies crm.currency.list
Delete Currency crm.currency.delete
Get Currency Fields crm.currency.fields
Copied
Was the article helpful?
Yes
No
Previous
Update Currency
Next
Get List of Currencies

---

## Get the list of currencies crm.currency.list

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/crm-currency-list

Get the list of currencies crm.currency.list | Bitrix24 REST API and Marketplace Applications
Get the list of currencies crm.currency.list
Get the list of currencies crm.currency.list
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to CRM settings
This method retrieves the list of currencies created on the account.
Note
Localization parameters (settings dependent on language) will be returned for the current language of the account.
Method Parameters
Method Parameters
Name
type
Description
order
object
An object for sorting records in the format
{"field_1": "order_1", ... "field_N": "order_N"}
, where
field_N
is the identifier of the
crm_currency
.
Possible values for
order_N
:
asc
— in ascending order
desc
— in descending order
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
'{"order":{"sort":"asc","currency":"asc"}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.list
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"order":{"sort":"asc","currency":"asc"},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.list
// callListMethod is recommended when you need to retrieve the entire set of list data and the volume of records is relatively small (up to about 1000 items). The method loads all data at once, which can lead to high memory load when working with large volumes.
try
{
const
response =
await
$b24.
callListMethod
(
'crm.currency.list'
,
{
order
: {
sort
:
'asc'
,
currency
:
'asc'
,
},
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
, entity);
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
// fetchListMethod is preferable when working with large datasets. The method implements iterative fetching using a generator, allowing data to be processed in parts and efficiently using memory.
try
{
const
generator = $b24.
fetchListMethod
(
'crm.currency.list'
, {
order
: {
sort
:
'asc'
,
currency
:
'asc'
,
},
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
, entity);
}
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
// callMethod provides manual control over the pagination process through the start parameter. Suitable for scenarios where precise control over request batches is required. However, it may be less efficient compared to fetchListMethod when dealing with large volumes of data.
try
{
const
response =
await
$b24.
callMethod
(
'crm.currency.list'
, {
order
: {
sort
:
'asc'
,
currency
:
'asc'
,
},
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
, entity);
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
try
{
$response
=
$b24Service
->core
->
call
(
'crm.currency.list'
,
[
'order'
=> [
'sort'
=>
'asc'
,
'currency'
=>
'asc'
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
"crm.currency.list"
,
{
order
: {
sort
:
'asc'
,
currency
:
'asc'
,
},
},
)
.
then
(
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
log
(result.
data
);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.list'
,
[
'order'
=> [
'sort'
=>
'asc'
,
'currency'
=>
'asc'
,
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
"CURRENCY"
:
"USD"
,
"AMOUNT_CNT"
:
"1"
,
"AMOUNT"
:
"1.0000"
,
"SORT"
:
"100"
,
"BASE"
:
"Y"
,
"FULL_NAME"
:
"United States Dollar"
,
"LID"
:
"de"
,
"FORMAT_STRING"
:
"# $"
,
"DEC_POINT"
:
"."
,
"THOUSANDS_SEP"
:
"&nbsp;"
,
"DECIMALS"
:
"2"
,
"DATE_UPDATE"
:
"2024-01-29T12:28:40+02:00"
}
,
{
"CURRENCY"
:
"USD"
,
"AMOUNT_CNT"
:
"1"
,
"AMOUNT"
:
"68.7900"
,
"SORT"
:
"200"
,
"BASE"
:
"N"
,
"FULL_NAME"
:
"United States Dollar"
,
"LID"
:
"de"
,
"FORMAT_STRING"
:
"$#"
,
"DEC_POINT"
:
"."
,
"THOUSANDS_SEP"
:
null
,
"DECIMALS"
:
"2"
,
"DATE_UPDATE"
:
"2023-03-21T15:19:50+02:00"
}
,
{
"CURRENCY"
:
"EUR"
,
"AMOUNT_CNT"
:
"1"
,
"AMOUNT"
:
"78.3200"
,
"SORT"
:
"300"
,
"BASE"
:
"N"
,
"FULL_NAME"
:
"Euro"
,
"LID"
:
"de"
,
"FORMAT_STRING"
:
"# €"
,
"DEC_POINT"
:
"."
,
"THOUSANDS_SEP"
:
"&nbsp;"
,
"DECIMALS"
:
"2"
,
"DATE_UPDATE"
:
"2023-03-21T15:19:50+02:00"
}
,
{
"CURRENCY"
:
"CAD"
,
"AMOUNT_CNT"
:
"1"
,
"AMOUNT"
:
"32.2000"
,
"SORT"
:
"500"
,
"BASE"
:
"N"
,
"FULL_NAME"
:
"Canadian Dollar"
,
"LID"
:
"de"
,
"FORMAT_STRING"
:
"# CAD"
,
"DEC_POINT"
:
"."
,
"THOUSANDS_SEP"
:
"&nbsp;"
,
"DECIMALS"
:
"2"
,
"DATE_UPDATE"
:
"2023-03-21T15:19:50+02:00"
}
]
,
"total"
:
0
,
"time"
:
{
"start"
:
1716986687.629166
,
"finish"
:
1716986688.481436
,
"duration"
:
0.8522701263427734
,
"processing"
:
0.014969825744628906
,
"date_start"
:
"2024-05-29T14:44:47+02:00"
,
"date_finish"
:
"2024-05-29T14:44:48+02:00"
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
crm_currency[]
An array of objects with information about the selected currencies
total
integer
Currently always has a value of
0
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
""
,
"error_description"
:
"Access denied."
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
Empty string
Access denied.
Insufficient access permissions
Empty string
Failed to get list. General error.
Currency module not installed
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
Add Currency crm.currency.add
Update Currency crm.currency.update
Get Currency by ID crm.currency.get
Delete Currency crm.currency.delete
Get Currency Fields crm.currency.fields
Copied
Was the article helpful?
Yes
No
Previous
Get Currency by ID
Next
Delete Currency

---

## Delete Currency crm.currency.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/crm-currency-delete

Delete Currency crm.currency.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete Currency crm.currency.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to modify CRM settings
This method deletes a currency.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
string
Currency identifier.
Corresponds to the ISO 4217 standard.
The identifier can be obtained using the
crm.currency.list
method
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
'{"id":"IDR"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"IDR","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.currency.delete"
,
{
id
:
'IDR'
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
'crm.currency.delete'
,
[
'id'
=>
'IDR'
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
'Error deleting currency: '
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
"crm.currency.delete"
,
{
id
:
'IDR'
},
)
.
then
(
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
log
(result.
data
());
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.delete'
,
[
'id'
=>
'IDR'
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
1718094270.751676
,
"finish"
:
1718094271.335892
,
"duration"
:
0.5842158794403076
,
"processing"
:
0.1017751693725586
,
"date_start"
:
"2024-06-11T10:24:30+02:00"
,
"date_finish"
:
"2024-06-11T10:24:31+02:00"
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
Result of the currency deletion
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
""
,
"error_description"
:
"Access denied."
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
Empty string
Access denied.
Insufficient access permissions
Empty string
Currency module not found! Please install the currency module.
Empty string
Empty string
Currency identifier must consist of 3 characters
Empty string
Cannot delete the base currency.
Empty string
Cannot delete the report currency.
ERROR_CODE
Other errors in the currency modification data
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
Add Currency crm.currency.add
Update Currency crm.currency.update
Get Currency by ID crm.currency.get
Get the list of currencies crm.currency.list
Get Currency Fields crm.currency.fields
Copied
Was the article helpful?
Yes
No
Previous
Get List of Currencies
Next
Get Currency Fields

---

## Get Currency Fields crm.currency.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/crm-currency-fields

Get Currency Fields crm.currency.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Currency Fields crm.currency.fields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to CRM settings
This method retrieves the description of currency fields. Each field is described as a field settings structure
crm_rest_field_description
.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.fields
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
https://**put_your_bitrix24_address**/rest/crm.currency.fields?auth=**put_access_token_here**
try
{
const
response =
await
$b24.
callMethod
(
'crm.currency.fields'
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
'crm.currency.fields'
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
'Error fetching currency fields: '
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
"crm.currency.fields"
,
{},
)
.
then
(
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
log
(result.
data
());
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.fields'
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
"CURRENCY"
:
{
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
,
"isDynamic"
:
false
,
"title"
:
"Currency"
}
,
"AMOUNT_CNT"
:
{
"type"
:
"int"
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
,
"isDynamic"
:
false
,
"title"
:
"Nominal"
}
,
"AMOUNT"
:
{
"type"
:
"double"
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
,
"isDynamic"
:
false
,
"title"
:
"Exchange Rate"
}
,
"BASE"
:
{
"type"
:
"char"
,
"isRequired"
:
false
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
,
"isDynamic"
:
false
,
"title"
:
"Base Currency"
}
,
"SORT"
:
{
"type"
:
"int"
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
,
"isDynamic"
:
false
,
"title"
:
"Sorting"
}
,
"DATE_UPDATE"
:
{
"type"
:
"datetime"
,
"isRequired"
:
false
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
,
"isDynamic"
:
false
,
"title"
:
"Date Updated"
}
,
"LID"
:
{
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
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Site"
}
,
"FORMAT_STRING"
:
{
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
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Format String for Currency Output"
}
,
"FULL_NAME"
:
{
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
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Name"
}
,
"DEC_POINT"
:
{
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
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Decimal Point for Output"
}
,
"THOUSANDS_SEP"
:
{
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
true
,
"isImmutable"
:
false
,
"isMultiple"
:
false
,
"isDynamic"
:
false
,
"title"
:
"Thousands Separator for Output"
}
,
"DECIMALS"
:
{
"type"
:
"int"
,
"isRequired"
:
false
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
,
"isDynamic"
:
false
,
"title"
:
"Number of Decimal Places"
}
,
"LANG"
:
{
"type"
:
"currency_localization"
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
true
,
"isDynamic"
:
false
,
"title"
:
"Language Binding"
}
}
,
"time"
:
{
"start"
:
1716974732.518201
,
"finish"
:
1716974733.260832
,
"duration"
:
0.7426309585571289
,
"processing"
:
0.018947124481201172
,
"date_start"
:
"2024-05-29T11:25:32+02:00"
,
"date_finish"
:
"2024-05-29T11:25:33+02:00"
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
An object with a list of available fields in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field_N
is the identifier of the crm_currency object field, and
value
is an object of type
crm_rest_field_description
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
""
,
"error_description"
:
"Access denied."
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
Empty string
Access denied.
Insufficient access rights
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
Add Currency crm.currency.add
Update Currency crm.currency.update
Get Currency by ID crm.currency.get
Get the list of currencies crm.currency.list
Delete Currency crm.currency.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete Currency
Next
Get Symbolic Identifier of Base Currency

---

## Get the Symbolic Identifier of the Base Currency crm.currency.base.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/crm-currency-base-get

Get the Symbolic Identifier of the Base Currency crm.currency.base.get | Bitrix24 REST API and Marketplace Applications
Code Examples
Get the Symbolic Identifier of the Base Currency crm.currency.base.get
Code Examples
Response Handling
Returned Data
Error Handling
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user
This method retrieves the symbolic identifier of the base currency.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.base.get
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
https://**put_your_bitrix24_address**/rest/crm.currency.base.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.currency.base.get'
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
'crm.currency.base.get'
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
'Error getting base currency: '
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
"crm.currency.base.get"
,
{},
)
.
then
(
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
log
(result.
data
());
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.base.get'
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
"RUB"
,
"time"
:
{
"start"
:
1718095046.076052
,
"finish"
:
1718095046.889631
,
"duration"
:
0.8135790824890137
,
"processing"
:
0.06328010559082031
,
"date_start"
:
"2024-06-11T10:37:26+02:00"
,
"date_finish"
:
"2024-06-11T10:37:26+02:00"
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
crm_currency.CURRENCY
Identifier of the base currency
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
" ERROR_UNEXPECTED_ANSWER "
,
"error_description"
:
"Server returned an unexpected response."
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
Set Currency as Base crm.currency.base.set
Copied
Was the article helpful?
Yes
No
Previous
Get Currency Fields
Next
Set Currency as Base

---

## Set Currency as Base crm.currency.base.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/crm-currency-base-set

Set Currency as Base crm.currency.base.set | Bitrix24 REST API and Marketplace Applications
Set Currency as Base crm.currency.base.set
Set Currency as Base crm.currency.base.set
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to modify CRM settings
This method changes the base currency.
Warning
After changing the base currency, it is necessary to update the exchange rates of other currencies relative to the base!
Method Parameters
Method Parameters
Name
type
Description
id
string
Identifier of the currency that will become the base.
Corresponds to the ISO 4217 standard.
The identifier can be obtained using the
crm.currency.list
method
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
'{"id":"USD"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.base.set
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"USD","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.base.set
try
{
const
response =
await
$b24.
callMethod
(
"crm.currency.base.set"
,
{
id
:
'USD'
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
'crm.currency.base.set'
,
[
'id'
=>
'USD'
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
'Error setting base currency: '
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
"crm.currency.base.set"
,
{
id
:
'USD'
},
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.base.set'
,
[
'id'
=>
'USD'
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
1718122855.747287
,
"finish"
:
1718122856.436222
,
"duration"
:
0.6889350414276123
,
"processing"
:
0.014606952667236328
,
"date_start"
:
"2024-06-11T18:20:55+02:00"
,
"date_finish"
:
"2024-06-11T18:20:56+02:00"
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
Returns the value:
true
— if successful
false
— if the operation could not be completed, but there is no error, or the situation is not considered erroneous. Possible reason: currency module is missing
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
""
,
"error_description"
:
"Access denied."
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
Empty string
Access denied.
Insufficient access permissions
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
Get the Symbolic Identifier of the Base Currency crm.currency.base.get
Copied
Was the article helpful?
Yes
No
Previous
Get Symbolic Identifier of Base Currency
Next
Overview of Methods

---

## Currency Localization in CRM: Overview of Methods

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/localizations/index

Currency Localization in CRM: Overview of Methods | Bitrix24 REST API and Marketplace Applications
Using Localization
Currency Localization in CRM: Overview of Methods
Using Localization
Overview of Methods and Events
Currency localization refers to the rules for writing numbers and placing currency symbols in different languages.
Quick navigation:
all methods and events
User documentation:
currencies in Bitrix24
,
localization structure
Using Localization
Using Localization
Bitrix24.
The display of currency depends on the interface language of Bitrix in the employee's account. In the Russian interface, the amount is displayed in the format
12 345,67 ₽
, while in English it appears as
₽ 12,345.67
.
Bitrix24.Sites.
In the site settings, you can choose the language for standard phrases in the builder blocks. The site language affects the price display format in the store blocks.
User Documentation
How to switch the interface language in Bitrix24
Site and page settings
Overview of Methods and Events
Overview of Methods and Events
Scope:
crm
Who can execute the method: depends on the method
Method
Description
crm.currency.localizations.get
Retrieves existing currency localizations
crm.currency.localizations.set
Updates localizations for a currency or adds them if the localization for the specified language does not exist
crm.currency.localizations.delete
Deletes currency localizations for specified languages
crm.currency.localizations.fields
Retrieves available fields for currency localization, i.e., settings that depend on the language
Copied
Was the article helpful?
Yes
No
Previous
Set Currency as Base
Next
Get Currency Localizations

---

## Get Currency Localizations crm.currency.localizations.get

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/localizations/crm-currency-localizations-get

Get Currency Localizations crm.currency.localizations.get | Bitrix24 REST API and Marketplace Applications
Method Parameters
Get Currency Localizations crm.currency.localizations.get
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to CRM settings
This method retrieves existing currency localizations.
Method Parameters
Method Parameters
Name
type
Description
id
string
Currency identifier.
Corresponds to the ISO 4217 standard.
The identifier can be obtained using the
crm.currency.list
method
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
'{"id":"USD"}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.localizations.get
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"USD","auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.localizations.get
try
{
const
response =
await
$b24.
callMethod
(
'crm.currency.localizations.get'
,
{
id
:
'USD'
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
'crm.currency.localizations.get'
,
[
'id'
=>
'USD'
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
'Error getting currency localizations: '
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
"crm.currency.localizations.get"
,
{
id
:
"USD"
},
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.localizations.get'
,
[
'id'
=>
'USD'
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
"en"
:
{
"FORMAT_STRING"
:
"$#"
,
"FULL_NAME"
:
"United States Dollar"
,
"DEC_POINT"
:
"."
,
"THOUSANDS_SEP"
:
null
,
"DECIMALS"
:
"2"
,
"THOUSANDS_VARIANT"
:
"C"
,
"HIDE_ZERO"
:
"Y"
}
,
"de"
:
{
"FORMAT_STRING"
:
"# $"
,
"FULL_NAME"
:
"US-Dollar"
,
"DEC_POINT"
:
"."
,
"THOUSANDS_SEP"
:
"&nbsp;"
,
"DECIMALS"
:
"2"
,
"THOUSANDS_VARIANT"
:
"B"
,
"HIDE_ZERO"
:
"Y"
}
}
,
"time"
:
{
"start"
:
1718114356.076467
,
"finish"
:
1718114356.682042
,
"duration"
:
0.6055748462677002
,
"processing"
:
0.03888106346130371
,
"date_start"
:
"2024-06-11T15:59:16+02:00"
,
"date_finish"
:
"2024-06-11T15:59:16+02:00"
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
An object in the format
{"lang_1": "value_1", ... "lang_N": "value_N"}
, where
lang_N
is the language identifier, and
value
is an object of type
crm_currency_localization
.
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
""
,
"error_description"
:
"The parameter id is invalid or not defined."
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
Empty string
Access denied.
Insufficient access permissions
Empty string
The parameter id is invalid or not defined.
Empty currency identifier
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
Set Localizations for Currency crm.currency.localizations.set
Delete currency localizations crm.currency.localizations.delete
Get Currency Localization Fields crm.currency.localizations.fields
Copied
Was the article helpful?
Yes
No
Previous
Overview of Methods
Next
Set Localizations for Currency

---

## Set Localizations for Currency crm.currency.localizations.set

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/localizations/crm-currency-localizations-set

Set Localizations for Currency crm.currency.localizations.set | Bitrix24 REST API and Marketplace Applications
Method Parameters
Set Localizations for Currency crm.currency.localizations.set
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to modify CRM settings
This method updates localizations for a currency or adds them if the localization for the specified language does not exist.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
/
type
Description
id
*
string
Currency identifier.
Corresponds to the ISO 4217 standard.
The identifier can be obtained using the
crm.currency.list
method
localizations
*
object
Currency localization parameters.
An object in the format
{"lang_1": "value_1", ... "lang_N": "value_N"}
, where
lang_N
is the language identifier for which to add/change the localization, and
value
is an object of type
crm_currency_localization
.
Existing localizations that are not passed to the method will not be changed.
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
'{"id":"CLF","localizations":{"en":{"FULL_NAME":"Unidad de Fomento","FORMAT_STRING":"CLF#VALUE#","DEC_POINT":".","THOUSANDS_VARIANT":"C","DECIMALS":4},"de":{"FULL_NAME":"Einheit der Entwicklung","FORMAT_STRING":"#VALUE# CLF","DEC_POINT":".","THOUSANDS_VARIANT":"B","DECIMALS":4}}}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.localizations.set
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":"CLF","localizations":{"en":{"FULL_NAME":"Unidad de Fomento","FORMAT_STRING":"CLF#VALUE#","DEC_POINT":".","THOUSANDS_VARIANT":"C","DECIMALS":4},"de":{"FULL_NAME":"Einheit der Entwicklung","FORMAT_STRING":"#VALUE# CLF","DEC_POINT":".","THOUSANDS_VARIANT":"B","DECIMALS":4}},"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.currency.localizations.set
try
{
const
response =
await
$b24.
callMethod
(
"crm.currency.localizations.set"
,
{
id
:
'CLF'
,
localizations
: {
en
: {
FULL_NAME
:
'Unidad de Fomento'
,
FORMAT_STRING
:
'CLF#VALUE#'
,
DEC_POINT
:
'.'
,
THOUSANDS_VARIANT
:
'C'
,
DECIMALS
:
4
,
},
de
: {
FULL_NAME
:
'Einheit der Entwicklung'
,
FORMAT_STRING
:
'#VALUE# CLF'
,
DEC_POINT
:
'.'
,
THOUSANDS_VARIANT
:
'B'
,
DECIMALS
:
4
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
'crm.currency.localizations.set'
,
[
'id'
=>
'CLF'
,
'localizations'
=> [
'en'
=> [
'FULL_NAME'
=>
'Unidad de Fomento'
,
'FORMAT_STRING'
=>
'CLF#VALUE#'
,
'DEC_POINT'
=>
'.'
,
'THOUSANDS_VARIANT'
=>
'C'
,
'DECIMALS'
=>
4
,
],
'de'
=> [
'FULL_NAME'
=>
'Einheit der Entwicklung'
,
'FORMAT_STRING'
=>
'#VALUE# CLF'
,
'DEC_POINT'
=>
'.'
,
'THOUSANDS_VARIANT'
=>
'B'
,
'DECIMALS'
=>
4
,
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
'Error setting currency localizations: '
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
"crm.currency.localizations.set"
,
{
id
:
'CLF'
,
localizations
: {
en
: {
FULL_NAME
:
'Unidad de Fomento'
,
FORMAT_STRING
:
'CLF#VALUE#'
,
DEC_POINT
:
'.'
,
THOUSANDS_VARIANT
:
'C'
,
DECIMALS
:
4
,
},
de
: {
FULL_NAME
:
'Einheit der Entwicklung'
,
FORMAT_STRING
:
'#VALUE# CLF'
,
DEC_POINT
:
'.'
,
THOUSANDS_VARIANT
:
'B'
,
DECIMALS
:
4
,
}
}
},
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.localizations.set'
,
[
'id'
=>
'CLF'
,
'localizations'
=> [
'en'
=> [
'FULL_NAME'
=>
'Unidad de Fomento'
,
'FORMAT_STRING'
=>
'CLF#VALUE#'
,
'DEC_POINT'
=>
'.'
,
'THOUSANDS_VARIANT'
=>
'C'
,
'DECIMALS'
=>
4
,
],
'de'
=> [
'FULL_NAME'
=>
'Einheit der Entwicklung'
,
'FORMAT_STRING'
=>
'#VALUE# CLF'
,
'DEC_POINT'
=>
'.'
,
'THOUSANDS_VARIANT'
=>
'B'
,
'DECIMALS'
=>
4
,
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
1718122481.837301
,
"finish"
:
1718122483.141736
,
"duration"
:
1.3044350147247314
,
"processing"
:
0.08866286277770996
,
"date_start"
:
"2024-06-11T18:14:41+02:00"
,
"date_finish"
:
"2024-06-11T18:14:43+02:00"
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
Returns:
true
— on success
false
– if the operation could not be completed, but there is no error, or the situation is not considered erroneous. Possible scenarios:
currency module is missing
an empty object with localizations was passed
no localization was added/changed
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
""
,
"error_description"
:
"The parameter id is invalid or not defined."
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
Empty string
Access denied.
Insufficient access permissions
Empty string
The parameter id is invalid or not defined.
Empty currency identifier
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
Get Currency Localizations crm.currency.localizations.get
Delete currency localizations crm.currency.localizations.delete
Get Currency Localization Fields crm.currency.localizations.fields
Copied
Was the article helpful?
Yes
No
Previous
Get Currency Localizations
Next
Delete Currency Localizations

---

## Delete currency localizations crm.currency.localizations.delete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/localizations/crm-currency-localizations-delete

Delete currency localizations crm.currency.localizations.delete | Bitrix24 REST API and Marketplace Applications
Method Parameters
Delete currency localizations crm.currency.localizations.delete
Method Parameters
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to modify CRM settings
This method deletes currency localizations for the specified languages.
Method Parameters
Method Parameters
Required parameters are marked with *
Name
type
Description
id
*
string
Currency identifier.
Corresponds to the ISO 4217 standard.
The identifier can be obtained using the
crm.currency.list
method.
lids
*
array
Array of language identifiers for which localizations need to be deleted
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
'{"id":5}'
\
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.automatedsolution.delete
curl -X POST \
-H
"Content-Type: application/json"
\
-H
"Accept: application/json"
\
-d
'{"id":5,"auth":"**put_access_token_here**"}'
\
https://**put_your_bitrix24_address**/rest/crm.automatedsolution.delete
try
{
const
response =
await
$b24.
callMethod
(
"crm.currency.localizations.delete"
,
{
id
:
'CLF'
,
lids
: [
'en'
,
'de'
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
'crm.currency.localizations.delete'
,
[
'id'
=>
'CLF'
,
'lids'
=> [
'en'
,
'de'
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
'Error deleting currency localizations: '
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
"crm.currency.localizations.delete"
,
{
id
:
'CLF'
,
lids
: [
'en'
,
'de'
]
},
)
.
then
(
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
log
(result);
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.automatedsolution.delete'
,
[
'id'
=>
5
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
1718117124.923431
,
"finish"
:
1718117125.511803
,
"duration"
:
0.588371992111206
,
"processing"
:
0.043914079666137695
,
"date_start"
:
"2024-06-11T16:45:24+02:00"
,
"date_finish"
:
"2024-06-11T16:45:25+02:00"
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
Returns:
true
— on success
false
— if the operation could not be completed, but there is no error, or the situation is not considered erroneous. Possible reasons:
currency module is missing
an empty array was passed in the
lids
parameter
no localization was deleted
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
""
,
"error_description"
:
"The parameter id is invalid or not defined."
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
Empty string
Access denied.
Insufficient access rights
Empty string
The parameter id is invalid or not defined
Empty currency identifier
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
Get Currency Localizations crm.currency.localizations.get
Set Localizations for Currency crm.currency.localizations.set
Get Currency Localization Fields crm.currency.localizations.fields
Copied
Was the article helpful?
Yes
No
Previous
Set Localizations for Currency
Next
Get Currency Localization Fields

---

## Get Currency Localization Fields crm.currency.localizations.fields

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/localizations/crm-currency-localizations-fields

Get Currency Localization Fields crm.currency.localizations.fields | Bitrix24 REST API and Marketplace Applications
Code Examples
Get Currency Localization Fields crm.currency.localizations.fields
Code Examples
Response Handling
Returned Data
Error Handling
Possible Error Codes
Statuses and System Error Codes
Continue Learning
Scope:
crm
Who can execute the method: any user with access to CRM settings
This method retrieves the available currency localization fields, which are settings dependent on the language.
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
https://**put_your_bitrix24_address**/rest/**put_your_user_id_here**/**put_your_webhook_here**/crm.currency.localizations.fields
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
https://**put_your_bitrix24_address**/rest/crm.currency.localizations.fields?auth=**put_access_token_here**
try
{
const
response =
await
$b24.
callMethod
(
"crm.currency.localizations.fields"
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
'crm.currency.localizations.fields'
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
"crm.currency.localizations.fields"
,
{},
)
.
then
(
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
log
(result.
data
());
}
},
function
(
error
)
{
console
.
info
(error);
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
'crm.currency.localizations.fields'
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
"FULL_NAME"
:
{
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
,
"isDynamic"
:
false
,
"title"
:
"Name"
}
,
"FORMAT_STRING"
:
{
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
,
"isDynamic"
:
false
,
"title"
:
"Format string for currency output"
}
,
"DEC_POINT"
:
{
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
,
"isDynamic"
:
false
,
"title"
:
"Decimal point for output"
}
,
"THOUSANDS_VARIANT"
:
{
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
,
"isDynamic"
:
false
,
"title"
:
"Thousands separator for output"
}
,
"THOUSANDS_SEP"
:
{
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
,
"isDynamic"
:
false
,
"title"
:
"Custom thousands separator for output"
}
,
"DECIMALS"
:
{
"type"
:
"int"
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
,
"isDynamic"
:
false
,
"title"
:
"Number of decimal places"
}
,
"HIDE_ZERO"
:
{
"type"
:
"char"
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
,
"isDynamic"
:
false
,
"title"
:
"Do not show insignificant zeros"
}
}
,
"time"
:
{
"start"
:
1717659438.587025
,
"finish"
:
1717659439.584851
,
"duration"
:
0.997826099395752
,
"processing"
:
0.05603790283203125
,
"date_start"
:
"2024-06-06T09:37:18+02:00"
,
"date_finish"
:
"2024-06-06T09:37:19+02:00"
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
An object containing a list of available fields in the format
{"field_1": "value_1", ... "field_N": "value_N"}
, where
field_N
is the identifier of the
crm_currency_localization
object, and
value
is an object of type
crm_rest_field_description
.
time
time
Information about the execution time of the request
Error Handling
Error Handling
HTTP Status:
400
{
"error"
:
""
,
"error_description"
:
"Access denied."
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
Empty string
Access denied.
Insufficient access rights
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
Get Currency Localizations crm.currency.localizations.get
Set Localizations for Currency crm.currency.localizations.set
Delete currency localizations crm.currency.localizations.delete
Copied
Was the article helpful?
Yes
No
Previous
Delete Currency Localizations
Next
Overview of events

---

## Overview of Events When Working with Currencies

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/events/index

Overview of Events When Working with Currencies | Bitrix24 REST API and Marketplace Applications
How to Receive Events
Overview of Events When Working with Currencies
How to Receive Events
Server Availability for Sending and Receiving Events
Overview of Events
Events allow applications to respond to changes in almost real-time: receiving notifications about the creation, updating, or deletion of currencies in CRM.
Detailed information on working with events is described in the article
Concept and Benefits of Event Processing
.
Quick navigation:
all events
How to Receive Events
How to Receive Events
You can subscribe to currency events through:
outgoing webhook
application
and the method
event.bind
An example of a handler for the event is described in the article
How to Test Your Handler for Processing Bitrix24 Events
.
Server Availability for Sending and Receiving Events
Server Availability for Sending and Receiving Events
The event handler server must be accessible from the outside. To configure the accessibility of the event handler server and application, refer to the article
Required network access
.
For cloud Bitrix24, no additional configuration is required. For on-premise Bitrix24, configure accessibility on the server or hosting according to the article
Required network access
.
Overview of Events
Overview of Events
Scope:
crm
Who can subscribe: any user
Event
Triggered
onCrmCurrencyAdd
When a currency is added manually or via the method
crm.currency.add
onCrmCurrencyUpdate
When a currency is changed manually or via the method
crm.currency.update
onCrmCurrencyDelete
When a currency is deleted manually or via the method
crm.currency.delete
Copied
Was the article helpful?
Yes
No
Previous
Get Currency Localization Fields
Next
When adding currency

---

## Event when adding currency onCrmCurrencyAdd

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/events/on-crm-currency-add

Event when adding currency onCrmCurrencyAdd | Bitrix24 REST API and Marketplace Applications
Event when adding currency onCrmCurrencyAdd
Event when adding currency onCrmCurrencyAdd
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMCURRENCYADD
will trigger when a new currency is added.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMCURRENCYADD"
,
"event_handler_id"
:
"691"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"CHE"
}
}
,
"ts"
:
"1742303858"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"L"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic code of the event.
In this case —
ONCRMCURRENCYADD
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the added currency.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the added currency.
The structure is described
below
ts
timestamp
Date and time of the event sent from the
event queue
auth
object
Object containing authorization parameters and data about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
string
Identifier of the added currency
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
domain
*
string
Address of Bitrix24 where the event occurred
server_endpoint
*
string
Address of the Bitrix24 authorization server needed to refresh OAuth 2.0 tokens
status
*
string
Status of the application that subscribed to this event:
L
—
local
application
F
—
free mass-market
application
client_endpoint
*
string
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event onCrmCurrencyUpdate
Event onCrmCurrencyDelete
Copied
Was the article helpful?
Yes
No
Previous
Overview of events
Next
When updating currency

---

## Event onCrmCurrencyUpdate

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/events/on-crm-currency-update

Event onCrmCurrencyUpdate | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmCurrencyUpdate
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMCURRENCYUPDATE
will trigger when the currency is updated.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted in the form of a POST request
{
"event"
:
"ONCRMCURRENCYUPDATE"
,
"event_handler_id"
:
"693"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"CHE"
}
}
,
"ts"
:
"1742303870"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"L"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic code of the event.
In this case —
ONCRMCURRENCYUPDATE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the updated currency.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the updated currency.
The structure is described
below
ts
timestamp
Date and time of the event sent from the
event queue
auth
object
Object containing authorization parameters and data about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
string
Identifier of the updated currency
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
domain
*
string
Address of Bitrix24 where the event occurred
server_endpoint
*
string
Address of the Bitrix24 authorization server needed to refresh OAuth 2.0 tokens
status
*
string
Status of the application that subscribed to this event:
L
—
local
application
F
—
free mass-market
application
client_endpoint
*
string
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event when adding currency onCrmCurrencyAdd
Event onCrmCurrencyDelete
Copied
Was the article helpful?
Yes
No
Previous
When adding currency
Next
When deleting currency

---

## Event onCrmCurrencyDelete

**Source:** https://apidocs.bitrix24.com/api-reference/crm/currency/events/on-crm-currency-delete

Event onCrmCurrencyDelete | Bitrix24 REST API and Marketplace Applications
What the handler receives
Event onCrmCurrencyDelete
What the handler receives
Parameter FIELDS
Parameter auth
Continue exploring
Scope:
crm
Who can subscribe: any user
The event
ONCRMCURRENCYDELETE
will trigger when a currency is deleted.
Events will not be sent to the application until the installation is complete.
Check the application installation
What the handler receives
What the handler receives
Data is transmitted as a POST request
{
"event"
:
"ONCRMCURRENCYDELETE"
,
"event_handler_id"
:
"695"
,
"data"
:
{
"FIELDS"
:
{
"ID"
:
"CHE"
}
}
,
"ts"
:
"1742303876"
,
"auth"
:
{
"access_token"
:
"s6p6eclrvim6da22ft9ch94ekreb52lv"
,
"expires_in"
:
"3600"
,
"scope"
:
"crm"
,
"domain"
:
"some-domain.bitrix24.com"
,
"server_endpoint"
:
"https://oauth.bitrix.info/rest/"
,
"status"
:
"L"
,
"client_endpoint"
:
"https://some-domain.bitrix24.com/rest/"
,
"member_id"
:
"a223c6b3710f85df22e9377d6c4f7553"
,
"refresh_token"
:
"4s386p3q0tr8dy89xvmt96234v3dljg8"
,
"application_token"
:
"51856fefc120afa4b628cc82d3935cce"
}
}
Parameter
type
Description
event
string
Symbolic code of the event.
In this case —
ONCRMCURRENCYDELETE
event_handler_id
integer
Identifier of the event handler
data
object
Object containing information about the deleted currency.
Contains a single key
FIELDS
data.FIELDS
object
Object containing information about the fields of the deleted currency.
The structure is described
below
ts
timestamp
Date and time the event was sent from the
event queue
auth
object
Object containing authorization parameters and information about the account where the event occurred.
The structure is described
below
Parameter FIELDS
Parameter FIELDS
Parameter
type
Description
ID
string
Identifier of the deleted currency
Parameter auth
Parameter auth
Required parameters are marked with *
Name
type
Description
access_token
string
Authorization token
OAuth 2.0
expires_in
integer
Time in seconds until the token expires
scope
*
string
Scope
under which the event occurred
domain
*
string
Address of Bitrix24 where the event occurred
server_endpoint
*
string
Address of the Bitrix24 authorization server needed to refresh OAuth 2.0 tokens
status
*
string
Status of the application that subscribed to this event:
L
—
local
application
F
—
free mass-market
application
client_endpoint
*
string
Common path for REST API method calls for Bitrix24 where the event occurred
member_id
*
string
Identifier of Bitrix24 where the event occurred
refresh_token
string
Token for extending authorization
OAuth 2.0
application_token
*
string
Token for secure event handling
Authorization tokens are not always passed to the event handler. If the hit that initiated the event could not be linked to a specific Bitrix24 user, the tokens are not passed. Always check the contents of the auth key in the code.
It is recommended to store tokens obtained earlier during the application installation. Use them when working with the application interface in the form of embeds, widgets, and so on.
Copied
Continue exploring
Continue exploring
Event Handler
Register a new event handler event.bind
Event when adding currency onCrmCurrencyAdd
Event onCrmCurrencyUpdate
Copied
Was the article helpful?
Yes
No
Previous
When updating currency
Next
Document Generator

---

