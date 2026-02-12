---
description: 'Tutorials: How to edit CRM objects (forms, cards, activities)'
methods:
- crm.activity.binding.add
- crm.activity.binding.delete
- crm.activity.binding.move
- crm.activity.list
- crm.company.add
- crm.company.contact.items.get
- crm.company.fields
- crm.company.get
- crm.company.list
- crm.company.update
- crm.contact.add
- crm.contact.company.items.get
- crm.contact.fields
- crm.contact.get
- crm.contact.list
- crm.contact.update
- crm.currency.list
- crm.deal.add
- crm.deal.contact.items.get
- crm.deal.fields
- crm.deal.get
- crm.deal.update
- crm.deal.userfield.list
- crm.dealcategory.list
- crm.enum.ownertype
- crm.item.payment.list
- crm.lead.add
- crm.lead.fields
- crm.lead.get
- crm.lead.update
pages: 9
title: 'Tutorials: How to edit CRM objects (forms, cards, activities)'
---
# Tutorials: How to edit CRM objects (forms, cards, activities)
> Tutorials: How to edit CRM objects (forms, cards, activities)
> **9 pages** | Source: apidocs.bitrix24.com

## Table of Contents
- [Editing Data](#editing-data)
- [How to Create Your Lead Editing Form](#how-to-create-your-lead-editing-form)
- [How to Create Your Contact Editing Form](#how-to-create-your-contact-editing-form)
- [How to Create Your Company Editing Form](#how-to-create-your-company-editing-form)
- [How to Create Your Deal Edit Form](#how-to-create-your-deal-edit-form)
- [How to Change or Delete Phone Numbers and Emails](#how-to-change-or-delete-phone-numbers-and-emails)
- [How to Transfer an Activity Between Entities of the Same Type](#how-to-transfer-an-activity-between-entities-of-th)
- [How to Transfer an Activity from One Object Type to Another](#how-to-transfer-an-activity-from-one-object-type-t)
- [How to Save the Payment Date in the Deal Field](#how-to-save-the-payment-date-in-the-deal-field)

---

## Editing Data

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-edit-crm-objects/index

Editing Data | Bitrix24 REST API and Marketplace Applications
Editing Data
Editing Data
How to Create Your Lead Editing Form
How to Create Your Contact Editing Form
How to Create Your Company Editing Form
How to Create Your Deal Edit Form
How to Change or Delete Phone Numbers and Emails
How to Transfer an Activity Between Entities of the Same Type
How to Transfer an Activity from One Object Type to Another
How to Save the Payment Date in the Deal Field
Was the article helpful?
Yes
No
Previous
How to Create a New Sales Funnel with Stages in Smart Process
Next
How to Create Your Lead Edit Form

---

## How to Create Your Lead Editing Form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-edit-crm-objects/how-to-generate-edit-form-for-lead

How to Create Your Lead Editing Form | Bitrix24 REST API and Marketplace Applications
How to Create Your Lead Editing Form
How to Create Your Lead Editing Form
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
Example of automatically generating a lead editing form with all fields created in Bitrix24 on the application page.
Some field types are not implemented in this example; a message
field not support
will be displayed in place of fields with unsupported types.
Note
To use the examples in PHP, configure the
CRest
class and include the
crest.php
file in the files where this class is used.
Learn more
Generated form code:
<?php
$ID
=
intVal
(
$_REQUEST
[
'ID'
]);
class
CPrintForm
{
/**
*
@var
$arParams array params input keys: 'NAME', 'ID', 'TYPE', 'REQUIRED', 'CHECKED', 'DISABLE', 'MULTIPLE', 'VALUE'
*
@return
string html select
*/
public
static
function
input
(
$arParams
)
{
$count
=
0
;
$i
=
0
;
$sResult
=
''
;
if
(
$arParams
[
'MULTIPLE'
] &&
$arParams
[
'TYPE'
] !=
'file'
)
{
$count
=
2
;
}
$value
=
$arParams
[
'VALUE'
];
while
(
$i
<=
$count
)
{
if
(
$count
>
0
)
{
$value
=
$arParams
[
'VALUE'
][
$i
];
}
$sResult
.=
'<input class="form-control'
. ((
$arParams
[
'TYPE'
] ==
'file'
) ?
'-file'
:
''
) .
'"'
;
if
(!
empty
(
$arParams
[
'ID'
]))
{
$sResult
.=
' id="'
.
$arParams
[
'ID'
] .
'"'
;
}
if
(!
empty
(
$arParams
[
'NAME'
]))
{
$sResult
.=
' name="'
.
$arParams
[
'NAME'
] .
''
. ((
$arParams
[
'MULTIPLE'
]) ?
'[]'
:
''
) .
'"'
;
}
if
(!
empty
(
$arParams
[
'TYPE'
]))
{
$sResult
.=
' type="'
.
$arParams
[
'TYPE'
] .
'"'
;
}
if
(!
empty
(
$arParams
[
'REQUIRED'
]))
{
$sResult
.=
' required'
;
}
if
(!
empty
(
$arParams
[
'DISABLE'
]))
{
$sResult
.=
' disabled'
;
}
if
(!
empty
(
$arParams
[
'CHECKED'
]))
{
$sResult
.=
' checked'
;
}
if
(!
empty
(
$arParams
[
'MULTIPLE'
]))
//sometimes work, not for standard type="text"
{
$sResult
.=
' multiple'
;
}
if
(!
empty
(
$arParams
[
'VALUE'
]))
{
$sResult
.=
' value="'
.
$value
.
'"'
;
}
$sResult
.=
'>'
;
$i
++;
}
return
$sResult
;
}
/**
*
@var
$arParams array settings of select params keys: 'NAME', 'ID', 'REQUIRED', 'DISABLE','MULTIPLE', 'VALUE'
*
@var
$arList array of select options where key is value option and value is title
*
@return
string html select
*/
public
static
function
select
(
$arParams
,
$arList
)
{
$sResult
=
''
;
if
(!
empty
(
$arList
) &&
is_array
(
$arList
))
{
$sResult
.=
'<select class="form-control"'
. ((
$arParams
[
'NAME'
]) ?
' name="'
.
$arParams
[
'NAME'
] .
''
. ((
$arParams
[
'MULTIPLE'
]) ?
'[]'
:
''
) .
'"'
:
''
)
. ((
$arParams
[
'ID'
]) ?
' id="'
.
$arParams
[
'ID'
] .
'"'
:
''
)
. ((
$arParams
[
'REQUIRED'
]) ?
' required'
:
''
)
. ((
$arParams
[
'DISABLE'
]) ?
' disabled'
:
''
)
. ((
$arParams
[
'MULTIPLE'
]) ?
' multiple'
:
''
)
.
'>'
;
$value
= [];
if
(
is_array
(
$arParams
[
'VALUE'
]))
{
$value
=
$arParams
[
'VALUE'
];
}
else
{
$value
[] = (
$arParams
[
'VALUE'
]) ?
$arParams
[
'VALUE'
] :
''
;
}
foreach
(
$arList
as
$key
=>
$title
)
{
$sResult
.=
'<option value="'
.
$key
.
'" '
.
((
in_array
(
$key
,
$value
)) ?
' selected'
:
''
)
.
'>'
.
$title
.
'</option>'
;
}
$sResult
.=
'</select>'
;
}
return
$sResult
;
}
}
$arData
= [
//Get all fields and standard enum fields
'FIELDS'
=> [
'method'
=>
'crm.lead.fields'
,
'params'
=> []
],
'FIELD_VALUES_SOURCE_ID'
=> [
'method'
=>
'crm.status.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][SOURCE_ID][statusType]'
]]
],
'FIELD_VALUES_STATUS_ID'
=> [
'method'
=>
'crm.status.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][STATUS_ID][statusType]'
]]
],
'FIELD_VALUES_CURRENCY'
=> [
'method'
=>
'crm.currency.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][STATUS_ID][statusType]'
]]
],
'OWNER_TYPE'
=> [
'method'
=>
'crm.enum.ownertype'
,
'params'
=> []
],
];
if
(
$ID
>
0
)
//get item and standard enum field values if is update form
{
$arData
[
'ITEM'
] = [
'method'
=>
'crm.lead.get'
,
'params'
=> [
'id'
=>
$ID
]
];
$arData
[
'VALUE_COMPANY_ID'
] = [
'method'
=>
'crm.company.get'
,
'params'
=> [
'id'
=>
'$result[ITEM][COMPANY_ID]'
]
];
$arData
[
'VALUE_CONTACT_ID'
] = [
'method'
=>
'crm.contact.get'
,
'params'
=> [
'id'
=>
'$result[ITEM][CONTACT_ID]'
]
];
}
$arResult
=
CRest
::
callBatch
(
$arData
,
0
);
$arResult
=
$arResult
[
'result'
][
'result'
];
$sResult
=
''
;
$sResultCustom
=
''
;
if
(
is_array
(
$arResult
[
'FIELDS'
])):
foreach
(
$arResult
[
'FIELDS'
]
as
$key
=>
$arField
)
{
$value
=
''
;
$return
=
''
;
if
(!
empty
(
$arResult
[
'ITEM'
][
$key
]))
{
$value
=
$arResult
[
'ITEM'
][
$key
];
}
$arList
= (
isset
(
$arResult
[
'FIELD_VALUES_'
.
$key
])) ?
$arResult
[
'FIELD_VALUES_'
.
$key
] : [];
switch
(
$arField
[
'type'
])
{
case
'crm_status'
:
if
(
empty
(
$arList
))
{
$arFieldsStatus
= \CRest ::
get
(
'crm.status.list'
, [
'filter'
=> [
'ENTITY_ID'
=>
$arField
[
'statusType'
]]]);
if
(!
empty
(
$arFieldsStatus
[
'result'
]))
$arList
=
$arFieldsStatus
[
'result'
];
}
$arList
=
array_column
(
$arList
,
'NAME'
,
'STATUS_ID'
);
$return
= CPrintForm ::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'crm_currency'
:
$arList
=
array_column
(
$arResult
[
'FIELD_VALUES_CURRENCY'
],
'FULL_NAME'
,
'CURRENCY'
);
$return
= CPrintForm ::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'enumeration'
:
if
(!
empty
(
$arField
[
'items'
]))
$arList
=
array_column
(
$arField
[
'items'
],
'VALUE'
,
'ID'
);
$return
= CPrintForm ::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'crm_multifield'
:
//its simple example: need multifield, check data type and more...
if
(!
empty
(
$value
) &&
is_array
(
$value
))
$value
=
reset
(
$value
)[
'VALUE'
];
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
false
,
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]);
break
;
case
'crm_company'
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]);
if
(!
empty
(
$arResult
[
'VALUE_COMPANY_ID'
]) &&
$value
==
$arResult
[
'VALUE_COMPANY_ID'
][
'ID'
])
{
$return
.=
'('
.
$arResult
[
'VALUE_COMPANY_ID'
][
'TITLE'
] .
')'
;
}
break
;
case
'crm_contact'
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]);
if
(!
empty
(
$arResult
[
'VALUE_CONTACT_ID'
]) &&
$value
==
$arResult
[
'VALUE_CONTACT_ID'
][
'ID'
])
{
$return
.=
'('
.
implode
(
' '
, [
$arResult
[
'VALUE_CONTACT_ID'
][
'NAME'
],
$arResult
[
'VALUE_CONTACT_ID'
][
'LAST_NAME'
]]) .
')'
;
}
break
;
case
'file'
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'file'
,
]);
if
(
$arField
[
'isMultiple'
])
{
if
(
is_array
(
$value
))
{
foreach
(
$value
as
$k
=>
$val
)
{
if
(!
empty
(
$val
[
'downloadUrl'
]))
{
$return
.=
'<br/><a href="'
.
$val
[
'downloadUrl'
] .
'">old file '
.
$k
.
'</a>'
;
}
}
}
}
else
{
if
(!
empty
(
$value
[
'downloadUrl'
]))
{
$return
.=
'<br/><a href="'
.
$value
[
'downloadUrl'
] .
'">old file</a>'
;
}
}
break
;
case
'date'
:
if
(!
empty
(
$value
))
{
$value
=
date
(
'Y-m-d'
,
strtotime
(
$value
));
}
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'date'
,
]);
break
;
case
'datetime'
:
if
(!
empty
(
$value
))
{
$value
=
date
(
'Y-m-d\TH:i:s'
,
strtotime
(
$value
));
}
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'datetime-local'
,
]);
break
;
case
'char'
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
'Y'
,
'CHECKED'
=> (
$value
==
'Y'
) ?
true
:
false
,
'TYPE'
=>
'checkbox'
,
]);
break
;
case
'boolean'
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
'1'
,
'CHECKED'
=> (
$value
==
'Y'
) ?
true
:
false
,
'TYPE'
=>
'checkbox'
,
]);
break
;
case
'double'
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'number'
]);
break
;
case
'url'
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]);
break
;
case
'integer'
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'number'
,
]);
break
;
case
'user'
:
$arUser
= [];
if
(!
empty
(
$value
))
{
$arUser
= CRest ::
get
(
'user.get'
, [
'filter'
=> [
'ID'
=>
$value
]]);
}
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'number'
]);
if
(!
empty
(
$arUser
[
'result'
]))
{
$return
.=
'('
;
$i
=
0
;
foreach
(
$arUser
[
'result'
]
as
$val
)
{
$i
++;
if
(
$i
>
1
)
{
$return
.=
', '
;
}
$return
.=
implode
(
' '
, [
$val
[
'NAME'
],
$val
[
'LAST_NAME'
]]);
}
$return
.=
')'
;
}
break
;
case
'money'
:
list
(
$money
,
$currency
) =
explode
(
'|'
,
$value
);
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$money
,
'TYPE'
=>
'number'
,
]);
$arList
=
array_column
(
$arResult
[
'FIELD_VALUES_CURRENCY'
],
'FULL_NAME'
,
'CURRENCY'
);
$return
.= CPrintForm ::
select
(
[
'NAME'
=>
$key
.
'_CURRENCY'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$currency
],
$arList
);
break
;
case
'address'
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]);
break
;
case
'resourcebooking'
:
//some code booking
$return
=
'field not support'
;
break
;
default
:
$return
= CPrintForm ::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]);
break
;
}
if
(
strpos
(
$key
,
'UF_'
) ===
0
)
{
$sResultCustom
.=
'<div class="col-4 mt-3">'
. ((
$arField
[
'formLabel'
]) ?
$arField
[
'formLabel'
] :
$arField
[
'title'
]) .
': '
.
'</div>'
;
$sResultCustom
.=
'<div class="col-6 mt-3">'
.
$return
.
'</div>'
;
}
else
{
$sResult
.=
'<div class="col-4 mt-3">'
. ((
$arField
[
'formLabel'
]) ?
$arField
[
'formLabel'
] :
$arField
[
'title'
]) .
': '
.
'</div>'
;
$sResult
.=
'<div class="col-6 mt-3">'
.
$return
.
'</div>'
;
}
}
?>
<link rel=
"stylesheet"
href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
crossorigin=
"anonymous"
>
<script src=
"https://code.jquery.com/jquery-3.3.1.slim.min.js"
crossorigin=
"anonymous"
></script>
<script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"
crossorigin=
"anonymous"
></script>
<script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"
crossorigin=
"anonymous"
></script>
<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
></script>
<script>
$(document).
ready
(function()
{
$(
'#auto_form'
).
on
(
'submit'
, function(el) {
//event submit form
el.
preventDefault
();
//the default action of the event will not be triggered
var
formData =
new
FormData
(this);
var
xhr =
new
XMLHttpRequest
();
xhr.
open
(
"POST"
,
'auto_form.php'
);
xhr.onreadystatechange =
function
(
)
{
if
(this.readyState ===
4
) {
if
(this.status >=
200
&& this.status <
400
) {
// Success!
var
resp = this.responseText;
try
{
var
json = JSON.
parse
(resp);
if
(typeof json.message !==
'undefined'
) {
alert
(json.message);
}
}
catch
(e) {
return
false
;
}
}
else
{
alert
(
'error'
);
}
}
};
xhr.
send
(formData);
});
});
</script>
<div
class
="
container
">
<
form
id
="
auto_form
"
action
=""
enctype
="
multipart
/
form
-
data
"
method
="
post
">
<?
if
(!
empty
($
arResult
[ '
ITEM
' ][ '
ID
' ]))://
for
update
entity
?>
<
input
type
="
hidden
"
name
="
form
[
ID
]"
value
="<?= $
arResult
[ '
ITEM
' ][ '
ID
' ] ?>">
<?
endif
; ?>
<
h2
>
Standard
fields
</
h2
>
<
div
class
="
row
">
<?= $
sResult
?>
</
div
>
<
h2
>
Custom
fields
</
h2
>
<
div
class
="
row
">
<?= $
sResultCustom
?>
</
div
>
<
div
class
="
row
">
<
div
class
="
col
-
sm
-10
mt
-5">
<
input
type
="
submit
"
class
="
btn
btn
-
primary
"
value
="
Submit
">
</
div
>
</
div
>
</
form
>
</
div
>
<?
endif
; ?>
Code for the
auto_form.php
file that saves the form:
<?php
$arForm
= [];
foreach
(
$_POST
[
'form'
]
as
$key
=>
$item
)
{
if
(
is_array
(
$item
))
{
$arForm
[
$key
] = [];
foreach
(
$item
as
$k
=>
$val
)
{
$arForm
[
$key
][
$k
] =
htmlspecialchars
(
$val
);
}
}
else
{
$arForm
[
$key
] =
htmlspecialchars
(
$item
);
}
}
//make array multiple files for add to custom field
if
(!
empty
(
$_FILES
[
'form'
][
'tmp_name'
]) &&
is_array
(
$_FILES
[
'form'
][
'tmp_name'
]))
{
foreach
(
$_FILES
[
'form'
][
'tmp_name'
]
as
$key
=>
$files
)
{
if
(
is_array
(
$files
))
{
foreach
(
$files
as
$k
=>
$file
)
{
$arForm
[
$key
][
$k
] = [
"fileData"
=> [
$_FILES
[
'form'
][
'name'
][
$key
][
$k
],
base64_encode
(
file_get_contents
(
$file
))
]
];
}
}
else
{
$arForm
[
$key
] = [
"fileData"
=> [
$_FILES
[
'form'
][
'name'
][
$key
],
base64_encode
(
file_get_contents
(
$files
))
]
];
}
}
}
$arResult
=
CRest
::
get
(
'crm.lead.fields'
, []);
if
(!
empty
(
$arResult
[
'result'
]))
{
foreach
(
$arResult
[
'result'
]
as
$key
=>
$prop
)
{
if
(!
isset
(
$arForm
[
$key
]))
{
if
(!
$prop
[
'isReadOnly'
] &&
$prop
[
'type'
] !=
'file'
)
{
if
(
$prop
[
'type'
] ==
'enumeration'
&&
$prop
[
'isMultiple'
])
{
//if type multiple enumeration to clean selected value need send: [false]
$arForm
[
$key
] = [
false
];
}
elseif
(
$prop
[
'isMultiple'
])
{
$arForm
[
$key
] = [];
}
else
{
$arForm
[
$key
] =
''
;
}
}
continue
;
}
//here may be any check field example by type
if
(
$prop
[
'type'
] ==
'crm_multifield'
)
{
if
(
isset
(
$arForm
[
$key
]))
{
$arForm
[
$key
] = [[
'VALUE'
=>
$arForm
[
$key
]]];
}
}
elseif
(
$prop
[
'type'
] ==
'money'
)
{
$arForm
[
$key
] =
implode
(
'|'
, [
$arForm
[
$key
],
$arForm
[
$key
.
'_CURRENCY'
]]);
unset
(
$arForm
[
$key
.
'_CURRENCY'
]);
}
}
}
$arForm
[
'ID'
] =
intVal
(
$arForm
[
'ID'
]);
if
(
$arForm
[
'ID'
] >
0
)
{
$method
=
'crm.lead.update'
;
$arParams
= [
'id'
=>
$arForm
[
'ID'
],
'fields'
=>
$arForm
];
$arMess
= [
'success'
=>
'Lead updated'
,
'error'
=>
'Lead not updated'
,
];
}
else
{
$method
=
'crm.lead.add'
;
$arParams
= [
'fields'
=>
$arForm
];
$arMess
= [
'success'
=>
'Lead added'
,
'error'
=>
'Lead not added'
,
];
}
$result
=
CRest
::
get
(
$method
,
$arParams
);
if
(!
empty
(
$result
[
'result'
]))
{
echo
json_encode
([
'message'
=>
$arMess
[
'success'
] . ((
$method
==
'crm.lead.add'
) ?
' ID:'
.
$result
[
'result'
] :
''
)]);
}
elseif
(!
empty
(
$result
[
'error_description'
]))
{
echo
json_encode
([
'message'
=>
$arMess
[
'error'
] .
': '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
$arMess
[
'error'
]]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
Edit Data
Next
How to Create Your Contact Edit Card

---

## How to Create Your Contact Editing Form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-edit-crm-objects/how-to-make-contact-edit-card

How to Create Your Contact Editing Form | Bitrix24 REST API and Marketplace Applications
How to Create Your Contact Editing Form
How to Create Your Contact Editing Form
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
Example of automatically generating a contact editing form with all fields created in Bitrix24 on the application page.
Some field types are not implemented in this example; a message
field not support
will be displayed in place of unsupported field types.
Note
To use the examples in PHP, configure the
CRest
class and include the
crest.php
file in the files where this class is used.
Learn more
Generated form code:
<?
$ID
=
intVal
(
$_REQUEST
[
'ID'
]);
class
CPrintForm
{
/**
*
@return
string html select
*
@var
$arParams array params input keys: 'NAME', 'ID', 'TYPE', 'REQUIRED', 'CHECKED', 'DISABLE', 'MULTIPLE', 'VALUE'
*/
public
static
function
input
(
$arParams
)
{
$count
=
0
;
$i
=
0
;
$sResult
=
''
;
if
(
$arParams
[
'MULTIPLE'
] &&
$arParams
[
'TYPE'
] !=
'file'
)
{
$count
=
2
;
}
$value
=
$arParams
[
'VALUE'
];
while
(
$i
<=
$count
)
{
if
(
$count
>
0
)
{
$value
=
$arParams
[
'VALUE'
][
$i
];
}
$sResult
.=
'<input class="form-control'
. ((
$arParams
[
'TYPE'
] ==
'file'
) ?
'-file'
:
''
) .
'"'
;
if
(!
empty
(
$arParams
[
'ID'
]))
{
$sResult
.=
' id="'
.
$arParams
[
'ID'
] .
'"'
;
}
if
(!
empty
(
$arParams
[
'NAME'
]))
{
$sResult
.=
' name="'
.
$arParams
[
'NAME'
] .
''
. ((
$arParams
[
'MULTIPLE'
]) ?
'[]'
:
''
) .
'"'
;
}
if
(!
empty
(
$arParams
[
'TYPE'
]))
{
$sResult
.=
' type="'
.
$arParams
[
'TYPE'
] .
'"'
;
}
if
(!
empty
(
$arParams
[
'REQUIRED'
]))
{
$sResult
.=
' required'
;
}
if
(!
empty
(
$arParams
[
'DISABLE'
]))
{
$sResult
.=
' disabled'
;
}
if
(!
empty
(
$arParams
[
'CHECKED'
]))
{
$sResult
.=
' checked'
;
}
if
(!
empty
(
$arParams
[
'MULTIPLE'
]))
{
//sometimes work, not for standard type="text"
$sResult
.=
' multiple'
;
}
if
(!
empty
(
$arParams
[
'VALUE'
]))
{
$sResult
.=
' value="'
.
$value
.
'"'
;
}
$sResult
.=
'>'
;
$i
++;
}
return
$sResult
;
}
/**
*
@return
string html select
*
@var
$arList array of select options where key is value option and value is title
*
@var
$arParams array settings of select params keys: 'NAME', 'ID', 'REQUIRED', 'DISABLE','MULTIPLE', 'VALUE'
*/
public
static
function
select
(
$arParams
,
$arList
)
{
$sResult
=
''
;
if
(!
empty
(
$arList
) &&
is_array
(
$arList
))
{
$sResult
.=
'<select class="form-control"'
.
((
$arParams
[
'NAME'
]) ?
' name="'
.
$arParams
[
'NAME'
] .
''
.
((
$arParams
[
'MULTIPLE'
]) ?
'[]'
:
''
) .
'"'
:
''
) .
((
$arParams
[
'ID'
]) ?
' id="'
.
$arParams
[
'ID'
] .
'"'
:
''
) .
((
$arParams
[
'REQUIRED'
]) ?
' required'
:
''
) .
((
$arParams
[
'DISABLE'
]) ?
' disabled'
:
''
) .
((
$arParams
[
'MULTIPLE'
]) ?
' multiple'
:
''
) .
'>'
;
$value
= [];
if
(
is_array
(
$arParams
[
'VALUE'
]))
{
$value
=
$arParams
[
'VALUE'
];
}
else
{
$value
[] = (
$arParams
[
'VALUE'
]) ?
$arParams
[
'VALUE'
] :
''
;
}
foreach
(
$arList
as
$key
=>
$title
)
{
$sResult
.=
'<option value="'
.
$key
.
'" '
.
((
in_array
(
$key
,
$value
)) ?
' selected'
:
''
) .
'>'
.
$title
.
'</option>'
;
}
$sResult
.=
'</select>'
;
}
return
$sResult
;
}
}
$arData
= [
//Get all fields and standard enum fields
'FIELDS'
=> [
'method'
=>
'crm.contact.fields'
,
'params'
=> []
],
'FIELD_VALUES_SOURCE_ID'
=> [
'method'
=>
'crm.status.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][SOURCE_ID][statusType]'
]]
],
'FIELD_VALUES_STATUS_ID'
=> [
'method'
=>
'crm.status.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][STATUS_ID][statusType]'
]]
],
'FIELD_VALUES_CURRENCY'
=> [
'method'
=>
'crm.currency.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][STATUS_ID][statusType]'
]]
],
'OWNER_TYPE'
=> [
'method'
=>
'crm.enum.ownertype'
,
'params'
=> []
],
];
if
(
$ID
>
0
)
{
//get item and standard enum field values if is update form
$arData
[
'ITEM'
] = [
'method'
=>
'crm.contact.get'
,
'params'
=> [
'id'
=>
$ID
]
];
$arData
[
'VALUE_LEAD_ID'
] = [
'method'
=>
'crm.lead.get'
,
'params'
=> [
'id'
=>
'$result[ITEM][LEAD_ID]'
]
];
}
$arResult
=
CRest
::
callBatch
(
$arData
,
0
);
$arResult
=
$arResult
[
'result'
][
'result'
];
$sResult
=
''
;
$sResultCustom
=
''
;
if
(
is_array
(
$arResult
[
'FIELDS'
])):
if
(
isset
(
$arResult
[
'FIELDS'
][
'COMPANY_ID'
]))
//deprecated use crm.contact.company.items.get
{
unset
(
$arResult
[
'FIELDS'
][
'COMPANY_ID'
]);
}
if
(
isset
(
$arResult
[
'FIELDS'
][
'COMPANY_IDS'
]))
//use crm.contact.company.items.get
{
unset
(
$arResult
[
'FIELDS'
][
'COMPANY_IDS'
]);
}
foreach
(
$arResult
[
'FIELDS'
]
as
$key
=&gt;
$arField
)
{
$value
=
''
;
$return
=
''
;
if
(!
empty
(
$arResult
[
'ITEM'
][
$key
]))
{
$value
=
$arResult
[
'ITEM'
][
$key
];
}
$arList
= (
isset
(
$arResult
[
'FIELD_VALUES_'
.
$key
])) ?
$arResult
[
'FIELD_VALUES_'
.
$key
] : [];
switch
(
$arField
[
'type'
])
{
case
'crm_status'
:
if
(
empty
(
$arList
))
{
$arFieldsStatus
=
\CRest
::
get
(
'crm.status.list'
,
[
'filter'
=&gt; [
'ENTITY_ID'
=&gt;
$arField
[
'statusType'
]]]
);
if
(!
empty
(
$arFieldsStatus
[
'result'
]))
{
$arList
=
$arFieldsStatus
[
'result'
];
}
}
$arList
=
array_column
(
$arList
,
'NAME'
,
'STATUS_ID'
);
$return
=
CPrintForm
::
select
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
],
$arList
);
break
;
case
'crm_currency'
:
$arList
=
array_column
(
$arResult
[
'FIELD_VALUES_CURRENCY'
],
'FULL_NAME'
,
'CURRENCY'
);
$return
=
CPrintForm
::
select
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
],
$arList
);
break
;
case
'enumeration'
:
if
(!
empty
(
$arField
[
'items'
]))
{
$arList
=
array_column
(
$arField
[
'items'
],
'VALUE'
,
'ID'
);
}
$return
=
CPrintForm
::
select
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
],
$arList
);
break
;
case
'crm_multifield'
:
//its simple example: need multifield, check data type and more...
if
(!
empty
(
$value
) &amp;&amp;
is_array
(
$value
))
{
$value
=
reset
(
$value
)[
'VALUE'
];
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
false
,
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'text'
,
]
);
break
;
case
'crm_lead'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'text'
,
]
);
if
(!
empty
(
$arResult
[
'VALUE_LEAD_ID'
]) &amp;&amp;
$value
==
$arResult
[
'VALUE_LEAD_ID'
][
'ID'
])
{
$return
.=
'('
.
$arResult
[
'VALUE_LEAD_ID'
][
'TITLE'
] .
')'
;
}
break
;
case
'file'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'file'
,
]
);
if
(
$arField
[
'isMultiple'
])
{
if
(
is_array
(
$value
))
{
foreach
(
$value
as
$k
=&gt;
$val
)
{
if
(!
empty
(
$val
[
'downloadUrl'
]))
{
$return
.=
'&lt;br/&gt;&lt;a href="'
.
$val
[
'downloadUrl'
] .
'"&gt;old file '
.
$k
.
'&lt;/a&gt;'
;
}
}
}
}
else
{
if
(!
empty
(
$value
[
'downloadUrl'
]))
{
$return
.=
'&lt;br/&gt;&lt;a href="'
.
$value
[
'downloadUrl'
] .
'"&gt;old file&lt;/a&gt;'
;
}
}
break
;
case
'date'
:
if
(!
empty
(
$value
))
{
$value
=
date
(
'Y-m-d'
,
strtotime
(
$value
));
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'date'
,
]
);
break
;
case
'datetime'
:
if
(!
empty
(
$value
))
{
$value
=
date
(
'Y-m-d\TH:i:s'
,
strtotime
(
$value
));
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'datetime-local'
,
]
);
break
;
case
'char'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
'Y'
,
'CHECKED'
=&gt; (
$value
==
'Y'
) ?
true
:
false
,
'TYPE'
=&gt;
'checkbox'
,
]
);
break
;
case
'boolean'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
'1'
,
'CHECKED'
=&gt; (
$value
==
'Y'
) ?
true
:
false
,
'TYPE'
=&gt;
'checkbox'
,
]
);
break
;
case
'double'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'number'
]
);
break
;
case
'user'
:
$arUser
= [];
if
(!
empty
(
$value
))
{
$arUser
=
CRest
::
get
(
'user.get'
, [
'filter'
=&gt; [
'ID'
=&gt;
$value
]]);
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'number'
]
);
if
(!
empty
(
$arUser
[
'result'
]))
{
$return
.=
'('
;
$i
=
0
;
foreach
(
$arUser
[
'result'
]
as
$val
)
{
$i
++;
if
(
$i
&gt;
1
)
{
$return
.=
', '
;
}
$return
.=
implode
(
' '
, [
$val
[
'NAME'
],
$val
[
'LAST_NAME'
]]);
}
$return
.=
')'
;
}
break
;
case
'url'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'text'
,
]
);
break
;
case
'integer'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'number'
,
]
);
break
;
case
'money'
:
list
(
$money
,
$currency
) =
explode
(
'|'
,
$value
);
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$money
,
'TYPE'
=&gt;
'number'
,
]
);
$arList
=
array_column
(
$arResult
[
'FIELD_VALUES_CURRENCY'
],
'FULL_NAME'
,
'CURRENCY'
);
$return
.=
CPrintForm
::
select
(
[
'NAME'
=&gt;
$key
.
'_CURRENCY'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$currency
],
$arList
);
break
;
case
'address'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'text'
,
]
);
break
;
case
'resourcebooking'
:
//some code booking
$return
=
'field not support'
;
break
;
default
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=&gt;
'form['
.
$key
.
']'
,
'REQUIRED'
=&gt;
$arField
[
'isRequired'
],
'DISABLE'
=&gt;
$arField
[
'isReadOnly'
],
'MULTIPLE'
=&gt;
$arField
[
'isMultiple'
],
'VALUE'
=&gt;
$value
,
'TYPE'
=&gt;
'text'
,
]
);
break
;
}
if
(
strpos
(
$key
,
'UF_'
) ===
0
)
{
$sResultCustom
.=
'&lt;div class="col-4 mt-3"&gt;'
.
((
$arField
[
'formLabel'
]) ?
$arField
[
'formLabel'
] :
$arField
[
'title'
]) .
': '
.
'&lt;/div&gt;'
;
$sResultCustom
.=
'&lt;div class="col-6 mt-3"&gt;'
.
$return
.
'&lt;/div&gt;'
;
}
else
{
$sResult
.=
'&lt;div class="col-4 mt-3"&gt;'
.
((
$arField
[
'formLabel'
]) ?
$arField
[
'formLabel'
] :
$arField
[
'title'
]) .
': '
.
'&lt;/div&gt;'
;
$sResult
.=
'&lt;div class="col-6 mt-3"&gt;'
.
$return
.
'&lt;/div&gt;'
;
}
}
?&gt;
&lt;link rel=
"stylesheet"
href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
crossorigin=
"anonymous"
&gt;
&lt;script src=
"https://code.jquery.com/jquery-3.3.1.slim.min.js"
crossorigin=
"anonymous"
&gt;&lt;/script&gt;
&lt;script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"
crossorigin=
"anonymous"
&gt;&lt;/script&gt;
&lt;script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"
crossorigin=
"anonymous"
&gt;&lt;/script&gt;
&lt;script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
&gt;&lt;/script&gt;
&lt;script&gt;
$(document).
ready
(function () {
$(
'#auto_form'
).
on
(
'submit'
, function (el) {
//event submit form
el.
preventDefault
();
//the default action of the event will not be triggered
var
formData =
new
FormData
(this);
var
xhr =
new
XMLHttpRequest
();
xhr.
open
(
"POST"
,
'auto_form.php'
);
xhr.onreadystatechange =
function
(
)
{
if
(this.readyState ===
4
)
{
if
(this.status &gt;=
200
&amp;&amp; this.status &lt;
400
)
{
// Success!
var
resp = this.responseText;
try
{
var
json = JSON.
parse
(resp);
if
(typeof json.message !==
'undefined'
)
{
alert
(json.message);
}
}
catch
(e)
{
return
false
;
}
}
else
{
alert
(
'error'
);
}
}
};
xhr.
send
(formData);
});
});
&lt;/script&gt;
&lt;div
class
="
container
"&
gt
;
&
lt
;
form
id
="
auto_form
"
action
=""
enctype
="
multipart
/
form
-
data
"
method
="
post
"&
gt
;
&
lt
;?
if
(!
empty
($
arResult
['
ITEM
']['
ID
']))://
for
update
entity
?&
gt
;
&
lt
;
input
type
="
hidden
"
name
="
form
[
ID
]"
value
="&
lt
;?=$
arResult
[ '
ITEM
' ][ '
ID
' ]	?&
gt
;"&
gt
;
&
lt
;?
endif
;?&
gt
;
&
lt
;
h2
&
gt
;
Standard
fields
&
lt
;/
h2
&
gt
;
&
lt
;
div
class
="
row
"&
gt
;
&
lt
;?=$
sResult
?&
gt
;
&
lt
;/
div
&
gt
;
&
lt
;
h2
&
gt
;
Custom
fields
&
lt
;/
h2
&
gt
;
&
lt
;
div
class
="
row
"&
gt
;
&
lt
;?=$
sResultCustom
?&
gt
;
&
lt
;/
div
&
gt
;
&
lt
;
div
class
="
row
"&
gt
;
&
lt
;
div
class
="
col
-
sm
-10
mt
-5"&
gt
;
&
lt
;
input
type
="
submit
"
class
="
btn
btn
-
primary
"
value
="
Submit
"&
gt
;
&
lt
;/
div
&
gt
;
&
lt
;/
div
&
gt
;
&
lt
;/
form
&
gt
;
&
lt
;/
div
&
gt
;
&
lt
;?
endif
;?&
gt
;
</
pre
>
File
auto_form.php
:
<?
$arForm
= [];
foreach
(
$_POST
[
'form'
]
as
$key
=>
$item
)
{
if
(
is_array
(
$item
))
{
$arForm
[
$key
] = [];
foreach
(
$item
as
$k
=>
$val
)
{
$arForm
[
$key
][
$k
] =
htmlspecialchars
(
$val
);
}
}
else
{
$arForm
[
$key
] =
htmlspecialchars
(
$item
);
}
}
//make array multiple files for add to custom field
if
(!
empty
(
$_FILES
[
'form'
][
'tmp_name'
]) &&
is_array
(
$_FILES
[
'form'
][
'tmp_name'
]))
{
foreach
(
$_FILES
[
'form'
][
'tmp_name'
]
as
$key
=>
$files
)
{
if
(
is_array
(
$files
))
{
foreach
(
$files
as
$k
=>
$file
)
{
$arForm
[
$key
][
$k
] = [
"fileData"
=> [
$_FILES
[
'form'
][
'name'
][
$key
][
$k
],
base64_encode
(
file_get_contents
(
$file
))
]
];
}
}
else
{
$arForm
[
$key
] = [
"fileData"
=> [
$_FILES
[
'form'
][
'name'
][
$key
],
base64_encode
(
file_get_contents
(
$files
))
]
];
}
}
}
$arResult
=
CRest
::
get
(
'crm.contact.fields'
, []);
if
(!
empty
(
$arResult
[
'result'
]))
{
foreach
(
$arResult
[
'result'
]
as
$key
=>
$prop
)
{
if
(!
isset
(
$arForm
[
$key
]))
{
if
(!
$prop
[
'isReadOnly'
] &&
$prop
[
'type'
] !=
'file'
)
{
if
(
$prop
[
'type'
] ==
'enumeration'
&&
$prop
[
'isMultiple'
])
{
//if type multiple enumeration to clean selected value need send: [false]
$arForm
[
$key
] = [
false
];
}
elseif
(
$prop
[
'isMultiple'
])
{
$arForm
[
$key
] = [];
}
else
{
$arForm
[
$key
] =
''
;
}
}
continue
;
}
//here may be any check field example by type
if
(
$prop
[
'type'
] ==
'crm_multifield'
)
{
if
(
isset
(
$arForm
[
$key
]))
{
$arForm
[
$key
] = [[
'VALUE'
=>
$arForm
[
$key
]]];
}
}
elseif
(
$prop
[
'type'
] ==
'money'
)
{
$arForm
[
$key
] =
implode
(
'|'
, [
$arForm
[
$key
],
$arForm
[
$key
.
'_CURRENCY'
]]);
unset
(
$arForm
[
$key
.
'_CURRENCY'
]);
}
}
}
$arForm
[
'ID'
] =
intVal
(
$arForm
[
'ID'
]);
if
(
$arForm
[
'ID'
] >
0
)
{
$method
=
'crm.contact.update'
;
$arParams
= [
'id'
=>
$arForm
[
'ID'
],
'fields'
=>
$arForm
];
$arMess
= [
'success'
=>
'Contact updated'
,
'error'
=>
'Contact not updated'
,
];
}
else
{
$method
=
'crm.contact.add'
;
$arParams
= [
'fields'
=>
$arForm
];
$arMess
= [
'success'
=>
'Contact added'
,
'error'
=>
'Contact not added'
,
];
}
$result
=
CRest
::
get
(
$method
,
$arParams
);
if
(!
empty
(
$result
[
'result'
]))
{
echo
json_encode
(
[
'message'
=>
$arMess
[
'success'
] . ((
$method
==
'crm.contact.add'
) ?
' ID:'
.
$result
[
'result'
] :
''
)]
);
}
elseif
(!
empty
(
$result
[
'error_description'
]))
{
echo
json_encode
([
'message'
=>
$arMess
[
'error'
] .
': '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
$arMess
[
'error'
]]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
How to Create Your Lead Edit Form
Next
How to Create Your Company Edit Card

---

## How to Create Your Company Editing Form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-edit-crm-objects/how-to-generate-edit-form-for-company

How to Create Your Company Editing Form | Bitrix24 REST API and Marketplace Applications
How to Create Your Company Editing Form
How to Create Your Company Editing Form
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
Example of automatically generating a company editing form with all fields created in Bitrix24 on your application's page.
Some field types are not implemented in the example; a message
field not support
will be displayed in place of unsupported field types.
Note
To use the examples in PHP, configure the
CRest
class and include the
crest.php
file in the files where this class is used.
Learn more
Generated form code:
<?php
$ID
=
intVal
(
$_REQUEST
[
'ID'
]);
class
CPrintForm
{
/**
*
@return
string html select
*
@var
$arParams array params input keys: 'NAME', 'ID', 'TYPE', 'REQUIRED', 'CHECKED', 'DISABLE', 'MULTIPLE', 'VALUE'
*/
public
static
function
input
(
$arParams
)
{
$count
=
0
;
$i
=
0
;
$sResult
=
''
;
if
(
$arParams
[
'MULTIPLE'
] &&
$arParams
[
'TYPE'
] !=
'file'
)
{
$count
=
2
;
}
$value
=
$arParams
[
'VALUE'
];
while
(
$i
<=
$count
)
{
if
(
$count
>
0
)
{
$value
=
$arParams
[
'VALUE'
][
$i
];
}
$sResult
.=
'<input class="form-control'
. ((
$arParams
[
'TYPE'
] ==
'file'
) ?
'-file'
:
''
) .
'"'
;
if
(!
empty
(
$arParams
[
'ID'
]))
{
$sResult
.=
' id="'
.
$arParams
[
'ID'
] .
'"'
;
}
if
(!
empty
(
$arParams
[
'NAME'
]))
{
$sResult
.=
' name="'
.
$arParams
[
'NAME'
] .
''
. ((
$arParams
[
'MULTIPLE'
]) ?
'[]'
:
''
) .
'"'
;
}
if
(!
empty
(
$arParams
[
'TYPE'
]))
{
$sResult
.=
' type="'
.
$arParams
[
'TYPE'
] .
'"'
;
}
if
(!
empty
(
$arParams
[
'REQUIRED'
]))
{
$sResult
.=
' required'
;
}
if
(!
empty
(
$arParams
[
'DISABLE'
]))
{
$sResult
.=
' disabled'
;
}
if
(!
empty
(
$arParams
[
'CHECKED'
]))
{
$sResult
.=
' checked'
;
}
if
(!
empty
(
$arParams
[
'MULTIPLE'
]))
{
//sometimes work, not for standard type="text"
$sResult
.=
' multiple'
;
}
if
(!
empty
(
$arParams
[
'VALUE'
]))
{
$sResult
.=
' value="'
.
$value
.
'"'
;
}
$sResult
.=
'>'
;
$i
++;
}
return
$sResult
;
}
/**
*
@return
string html select
*
@var
$arList array of select options where key is value option and value is title
*
@var
$arParams array settings of select params keys: 'NAME', 'ID', 'REQUIRED', 'DISABLE','MULTIPLE', 'VALUE'
*/
public
static
function
select
(
$arParams
,
$arList
)
{
$sResult
=
''
;
if
(!
empty
(
$arList
) &&
is_array
(
$arList
))
{
$sResult
.=
'<select class="form-control"'
.
((
$arParams
[
'NAME'
]) ?
' name="'
.
$arParams
[
'NAME'
] .
''
.
((
$arParams
[
'MULTIPLE'
]) ?
'[]'
:
''
) .
'"'
:
''
) .
((
$arParams
[
'ID'
]) ?
' id="'
.
$arParams
[
'ID'
] .
'"'
:
''
) .
((
$arParams
[
'REQUIRED'
]) ?
' required'
:
''
) .
((
$arParams
[
'DISABLE'
]) ?
' disabled'
:
''
) .
((
$arParams
[
'MULTIPLE'
]) ?
' multiple'
:
''
) .
'>'
;
$value
= [];
if
(
is_array
(
$arParams
[
'VALUE'
]))
{
$value
=
$arParams
[
'VALUE'
];
}
else
{
$value
[] = (
$arParams
[
'VALUE'
]) ?
$arParams
[
'VALUE'
] :
''
;
}
foreach
(
$arList
as
$key
=>
$title
)
{
$sResult
.=
'<option value="'
.
$key
.
'" '
.
((
in_array
(
$key
,
$value
)) ?
' selected'
:
''
) .
'>'
.
$title
.
'</option>'
;
}
$sResult
.=
'</select>'
;
}
return
$sResult
;
}
}
$arData
= [
//Get all fields and standard enum fields
'FIELDS'
=> [
'method'
=>
'crm.company.fields'
,
'params'
=> []
],
'FIELD_VALUES_SOURCE_ID'
=> [
'method'
=>
'crm.status.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][SOURCE_ID][statusType]'
]]
],
'FIELD_VALUES_STATUS_ID'
=> [
'method'
=>
'crm.status.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][STATUS_ID][statusType]'
]]
],
'FIELD_VALUES_CURRENCY'
=> [
'method'
=>
'crm.currency.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][STATUS_ID][statusType]'
]]
],
'OWNER_TYPE'
=> [
'method'
=>
'crm.enum.ownertype'
,
'params'
=> []
],
];
if
(
$ID
>
0
)
{
//get item and standard enum field values if is update form
$arData
[
'ITEM'
] = [
'method'
=>
'crm.company.get'
,
'params'
=> [
'id'
=>
$ID
]
];
$arData
[
'VALUE_CONTACT_ID'
] = [
'method'
=>
'crm.company.contact.items.get'
,
'params'
=> [
'id'
=>
$ID
]
];
$arData
[
'VALUE_LEAD_ID'
] = [
'method'
=>
'crm.lead.get'
,
'params'
=> [
'id'
=>
'$result[ITEM][LEAD_ID]'
]
];
}
$arResult
=
CRest
::
callBatch
(
$arData
,
0
);
$arResult
=
$arResult
[
'result'
][
'result'
];
$sResult
=
''
;
$sResultCustom
=
''
;
if
(
is_array
(
$arResult
[
'FIELDS'
])):
foreach
(
$arResult
[
'FIELDS'
]
as
$key
=>
$arField
)
{
$value
=
''
;
$return
=
''
;
if
(!
empty
(
$arResult
[
'ITEM'
][
$key
]))
{
$value
=
$arResult
[
'ITEM'
][
$key
];
}
$arList
= (
isset
(
$arResult
[
'FIELD_VALUES_'
.
$key
])) ?
$arResult
[
'FIELD_VALUES_'
.
$key
] : [];
switch
(
$arField
[
'type'
])
{
case
'crm_status'
:
if
(
empty
(
$arList
))
{
$arFieldsStatus
=
\CRest
::
get
(
'crm.status.list'
,
[
'filter'
=> [
'ENTITY_ID'
=>
$arField
[
'statusType'
]]]
);
if
(!
empty
(
$arFieldsStatus
[
'result'
]))
{
$arList
=
$arFieldsStatus
[
'result'
];
}
}
$arList
=
array_column
(
$arList
,
'NAME'
,
'STATUS_ID'
);
$return
=
CPrintForm
::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'crm_currency'
:
$arList
=
array_column
(
$arResult
[
'FIELD_VALUES_CURRENCY'
],
'FULL_NAME'
,
'CURRENCY'
);
$return
=
CPrintForm
::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'enumeration'
:
if
(!
empty
(
$arField
[
'items'
]))
{
$arList
=
array_column
(
$arField
[
'items'
],
'VALUE'
,
'ID'
);
}
$return
=
CPrintForm
::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'crm_multifield'
:
//its simple example: need multifield, check data type and more...
if
(!
empty
(
$value
) &&
is_array
(
$value
))
{
$value
=
reset
(
$value
)[
'VALUE'
];
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
false
,
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
break
;
case
'crm_lead'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
if
(!
empty
(
$arResult
[
'VALUE_LEAD_ID'
]) &&
$value
==
$arResult
[
'VALUE_LEAD_ID'
][
'ID'
])
{
$return
.=
'('
.
$arResult
[
'VALUE_LEAD_ID'
][
'TITLE'
] .
')'
;
}
break
;
case
'crm_contact'
:
$arContact
= [];
if
(!
empty
(
$arResult
[
'VALUE_'
.
$key
]))
{
$arContact
=
$arResult
[
'VALUE_'
.
$key
];
}
elseif
(!
empty
(
$value
))
{
$arContact
=
CRest
::
get
(
'crm.contact.list'
, [
'filter'
=> [
'ID'
=>
$value
]]);
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
if
(!
empty
(
$arContact
[
'result'
]))
{
$return
.=
'('
;
$i
=
0
;
foreach
(
$arContact
[
'result'
]
as
$val
)
{
$i
++;
if
(
$i
>
1
)
{
$return
.=
', '
;
}
$return
.=
implode
(
' '
, [
$val
[
'NAME'
],
$val
[
'LAST_NAME'
]]);
}
$return
.=
')'
;
}
break
;
case
'file'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'file'
,
]
);
if
(
$arField
[
'isMultiple'
])
{
if
(
is_array
(
$value
))
{
foreach
(
$value
as
$k
=>
$val
)
{
if
(!
empty
(
$val
[
'downloadUrl'
]))
{
$return
.=
'<br/><a href="'
.
$val
[
'downloadUrl'
] .
'">old file '
.
$k
.
'</a>'
;
}
}
}
}
else
{
if
(!
empty
(
$value
[
'downloadUrl'
]))
{
$return
.=
'<br/><a href="'
.
$value
[
'downloadUrl'
] .
'">old file</a>'
;
}
}
break
;
case
'date'
:
if
(!
empty
(
$value
))
{
$value
=
date
(
'Y-m-d'
,
strtotime
(
$value
));
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'date'
,
]
);
break
;
case
'datetime'
:
if
(!
empty
(
$value
))
{
$value
=
date
(
'Y-m-d\TH:i:s'
,
strtotime
(
$value
));
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'datetime-local'
,
]
);
break
;
case
'char'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
'Y'
,
'CHECKED'
=> (
$value
==
'Y'
) ?
true
:
false
,
'TYPE'
=>
'checkbox'
,
]
);
break
;
case
'boolean'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
'1'
,
'CHECKED'
=> (
$value
==
'Y'
) ?
true
:
false
,
'TYPE'
=>
'checkbox'
,
]
);
break
;
case
'double'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'number'
]
);
break
;
case
'user'
:
$arUser
= [];
if
(!
empty
(
$value
))
{
$arUser
=
CRest
::
get
(
'user.get'
, [
'filter'
=> [
'ID'
=>
$value
]]);
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'number'
]
);
if
(!
empty
(
$arUser
[
'result'
]))
{
$return
.=
'('
;
$i
=
0
;
foreach
(
$arUser
[
'result'
]
as
$val
)
{
$i
++;
if
(
$i
>
1
)
{
$return
.=
', '
;
}
$return
.=
implode
(
' '
, [
$val
[
'NAME'
],
$val
[
'LAST_NAME'
]]);
}
$return
.=
')'
;
}
break
;
case
'url'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
break
;
case
'integer'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'number'
,
]
);
break
;
case
'money'
:
list
(
$money
,
$currency
) =
explode
(
'|'
,
$value
);
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$money
,
'TYPE'
=>
'number'
,
]
);
$arList
=
array_column
(
$arResult
[
'FIELD_VALUES_CURRENCY'
],
'FULL_NAME'
,
'CURRENCY'
);
$return
.=
CPrintForm
::
select
(
[
'NAME'
=>
$key
.
'_CURRENCY'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$currency
],
$arList
);
break
;
case
'address'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
break
;
case
'resourcebooking'
:
//some code booking
$return
=
'field not support'
;
break
;
default
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
break
;
}
if
(
strpos
(
$key
,
'UF_'
) ===
0
)
{
$sResultCustom
.=
'<div class="col-4 mt-3">'
.
((
$arField
[
'formLabel'
]) ?
$arField
[
'formLabel'
] :
$arField
[
'title'
]) .
': '
.
'</div>'
;
$sResultCustom
.=
'<div class="col-6 mt-3">'
.
$return
.
'</div>'
;
}
else
{
$sResult
.=
'<div class="col-4 mt-3">'
.
((
$arField
[
'formLabel'
]) ?
$arField
[
'formLabel'
] :
$arField
[
'title'
]) .
': '
.
'</div>'
;
$sResult
.=
'<div class="col-6 mt-3">'
.
$return
.
'</div>'
;
}
}
?>
<link rel=
"stylesheet"
href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
crossorigin=
"anonymous"
>
<script src=
"https://code.jquery.com/jquery-3.3.1.slim.min.js"
crossorigin=
"anonymous"
></script>
<script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"
crossorigin=
"anonymous"
></script>
<script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"
crossorigin=
"anonymous"
></script>
<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
></script>
<script>
$(document).
ready
(function () {
$(
'#auto_form'
).
on
(
'submit'
, function (el) {
//event submit form
el.
preventDefault
();
//the default action of the event will not be triggered
var
formData =
new
FormData
(this);
var
xhr =
new
XMLHttpRequest
();
xhr.
open
(
"POST"
,
'auto_form.php'
);
xhr.onreadystatechange =
function
(
)
{
if
(this.readyState ===
4
)
{
if
(this.status >=
200
&& this.status <
400
)
{
// Success!
var
resp = this.responseText;
try
{
var
json = JSON.
parse
(resp);
if
(typeof json.message !==
'undefined'
)
{
alert
(json.message);
}
}
catch
(e)
{
return
false
;
}
}
else
{
alert
(
'error'
);
}
}
};
xhr.
send
(formData);
});
});
</script>
<div
class
="
container
">
<
form
id
="
auto_form
"
action
=""
enctype
="
multipart
/
form
-
data
"
method
="
post
">
<?
php
if
(!
empty
($
arResult
['
ITEM
']['
ID
']))://
for
update
entity
?>
<
input
type
="
hidden
"
name
="
form
[
ID
]"
value
="<?=$
arResult
[ '
ITEM
' ][ '
ID
' ]?>">
<?
php
endif
;?>
<
h2
>
Standard
fields
</
h2
>
<
div
class
="
row
">
<?=$
sResult
?>
</
div
>
<
h2
>
Custom
fields
</
h2
>
<
div
class
="
row
">
<?=$
sResultCustom
?>
</
div
>
<
div
class
="
row
">
<
div
class
="
col
-
sm
-10
mt
-5">
<
input
type
="
submit
"
class
="
btn
btn
-
primary
"
value
="
Submit
">
</
div
>
</
div
>
</
form
>
</
div
>
<?
php
endif
;?>
auto_form.php
file:
<?php
$arForm
= [];
foreach
(
$_POST
[
'form'
]
as
$key
=>
$item
) {
if
(
is_array
(
$item
)) {
$arForm
[
$key
] = [];
foreach
(
$item
as
$k
=>
$val
) {
$arForm
[
$key
][
$k
] =
htmlspecialchars
(
$val
);
}
}
else
{
$arForm
[
$key
] =
htmlspecialchars
(
$item
);
}
}
//make array multiple files for add to custom field
if
(!
empty
(
$_FILES
[
'form'
][
'tmp_name'
]) &&
is_array
(
$_FILES
[
'form'
][
'tmp_name'
])) {
foreach
(
$_FILES
[
'form'
][
'tmp_name'
]
as
$key
=>
$files
) {
if
(
is_array
(
$files
)) {
foreach
(
$files
as
$k
=>
$file
) {
$arForm
[
$key
][
$k
] = [
"fileData"
=> [
$_FILES
[
'form'
][
'name'
][
$key
][
$k
],
base64_encode
(
file_get_contents
(
$file
))
]
];
}
}
else
{
$arForm
[
$key
] = [
"fileData"
=> [
$_FILES
[
'form'
][
'name'
][
$key
],
base64_encode
(
file_get_contents
(
$files
))
]
];
}
}
}
$arResult
=
CRest
::
get
(
'crm.company.fields'
, []);
if
(!
empty
(
$arResult
[
'result'
])) {
foreach
(
$arResult
[
'result'
]
as
$key
=>
$prop
) {
if
(!
isset
(
$arForm
[
$key
])) {
if
(!
$prop
[
'isReadOnly'
] &&
$prop
[
'type'
] !=
'file'
) {
if
(
$prop
[
'type'
] ==
'enumeration'
&&
$prop
[
'isMultiple'
]) {
//if type multiple enumeration to clean selected value need send: [false]
$arForm
[
$key
] = [
false
];
}
elseif
(
$prop
[
'isMultiple'
]) {
$arForm
[
$key
] = [];
}
else
{
$arForm
[
$key
] =
''
;
}
}
continue
;
}
//here may be any check field example by type
if
(
$prop
[
'type'
] ==
'crm_multifield'
) {
if
(
isset
(
$arForm
[
$key
])) {
$arForm
[
$key
] = [[
'VALUE'
=>
$arForm
[
$key
]]];
}
}
elseif
(
$prop
[
'type'
] ==
'money'
) {
$arForm
[
$key
] =
implode
(
'|'
, [
$arForm
[
$key
],
$arForm
[
$key
.
'_CURRENCY'
]]);
unset
(
$arForm
[
$key
.
'_CURRENCY'
]);
}
}
}
$arForm
[
'ID'
] =
intVal
(
$arForm
[
'ID'
]);
if
(
$arForm
[
'ID'
] >
0
) {
$method
=
'crm.company.update'
;
$arParams
= [
'id'
=>
$arForm
[
'ID'
],
'fields'
=>
$arForm
];
$arMess
= [
'success'
=>
'Company updated'
,
'error'
=>
'Company not updated'
,
];
}
else
{
$method
=
'crm.company.add'
;
$arParams
= [
'fields'
=>
$arForm
];
$arMess
= [
'success'
=>
'Company added'
,
'error'
=>
'Company not added'
,
];
}
$result
=
CRest
::
get
(
$method
,
$arParams
);
if
(!
empty
(
$result
[
'result'
])) {
echo
json_encode
(
[
'message'
=>
$arMess
[
'success'
] . ((
$method
==
'crm.company.add'
) ?
' ID:'
.
$result
[
'result'
] :
''
)]
);
}
elseif
(!
empty
(
$result
[
'error_description'
])) {
echo
json_encode
([
'message'
=>
$arMess
[
'error'
] .
': '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
$arMess
[
'error'
]]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
How to Create Your Contact Edit Card
Next
How to Create Your Deal Edit Card

---

## How to Create Your Deal Edit Form

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-edit-crm-objects/how-to-generate-edit-form-for-deal

How to Create Your Deal Edit Form | Bitrix24 REST API and Marketplace Applications
How to Create Your Deal Edit Form
How to Create Your Deal Edit Form
Scope:
crm
Who can execute the method: users with administrative access to the CRM section
Example of automatically generating a deal edit form with all fields created in Bitrix24 on the application page.
Some field types are not implemented in the example; a message
field not support
will be displayed in place of unsupported field types.
Note
To use the examples in PHP, configure the
CRest
class and include the
crest.php
file in the files where this class is used.
Learn more
Generated form code:
<?php
$ID
=
intVal
(
$_REQUEST
[
'ID'
]);
class
CPrintForm
{
/**
*
@return
string html select
*
@var
$arParams array params input keys: 'NAME', 'ID', 'TYPE', 'REQUIRED', 'CHECKED', 'DISABLE', 'MULTIPLE', 'VALUE'
*/
public
static
function
input
(
$arParams
)
{
$count
=
0
;
$i
=
0
;
$sResult
=
''
;
if
(
$arParams
[
'MULTIPLE'
] &&
$arParams
[
'TYPE'
] !=
'file'
)
{
$count
=
2
;
}
$value
=
$arParams
[
'VALUE'
];
while
(
$i
<=
$count
)
{
if
(
$count
>
0
)
{
$value
=
$arParams
[
'VALUE'
][
$i
];
}
$sResult
.=
'<input class="form-control'
. ((
$arParams
[
'TYPE'
] ==
'file'
) ?
'-file'
:
''
) .
'"'
;
if
(!
empty
(
$arParams
[
'ID'
]))
{
$sResult
.=
' id="'
.
$arParams
[
'ID'
] .
'"'
;
}
if
(!
empty
(
$arParams
[
'NAME'
]))
{
$sResult
.=
' name="'
.
$arParams
[
'NAME'
] .
''
.
((
$arParams
[
'MULTIPLE'
]) ?
'[]'
:
''
) .
'"'
;
}
if
(!
empty
(
$arParams
[
'TYPE'
]))
{
$sResult
.=
' type="'
.
$arParams
[
'TYPE'
] .
'"'
;
}
if
(!
empty
(
$arParams
[
'REQUIRED'
]))
{
$sResult
.=
' required'
;
}
if
(!
empty
(
$arParams
[
'DISABLE'
]))
{
$sResult
.=
' disabled'
;
}
if
(!
empty
(
$arParams
[
'CHECKED'
]))
{
$sResult
.=
' checked'
;
}
if
(!
empty
(
$arParams
[
'MULTIPLE'
]))
{
//sometimes work, not for standard type="text"
$sResult
.=
' multiple'
;
}
if
(!
empty
(
$arParams
[
'VALUE'
]))
{
$sResult
.=
' value="'
.
$value
.
'"'
;
}
$sResult
.=
'>'
;
$i
++;
}
return
$sResult
;
}
/**
*
@return
string html select
*
@var
$arList array of select options where key is value option and value is title
*
@var
$arParams array settings of select params keys: 'NAME', 'ID', 'REQUIRED', 'DISABLE','MULTIPLE', 'VALUE'
*/
public
static
function
select
(
$arParams
,
$arList
)
{
$sResult
=
''
;
if
(!
empty
(
$arList
) &&
is_array
(
$arList
))
{
$sResult
.=
'<select class="form-control"'
.
((
$arParams
[
'NAME'
]) ?
' name="'
.
$arParams
[
'NAME'
] .
''
.
((
$arParams
[
'MULTIPLE'
]) ?
'[]'
:
''
) .
'"'
:
''
) .
((
$arParams
[
'ID'
]) ?
' id="'
.
$arParams
[
'ID'
] .
'"'
:
''
) .
((
$arParams
[
'REQUIRED'
]) ?
' required'
:
''
) .
((
$arParams
[
'DISABLE'
]) ?
' disabled'
:
''
) .
((
$arParams
[
'MULTIPLE'
]) ?
' multiple'
:
''
) .
'>'
;
$value
= [];
if
(
is_array
(
$arParams
[
'VALUE'
]))
{
$value
=
$arParams
[
'VALUE'
];
}
else
{
$value
[] = (
$arParams
[
'VALUE'
]) ?
$arParams
[
'VALUE'
] :
''
;
}
foreach
(
$arList
as
$key
=>
$title
)
{
$sResult
.=
'<option value="'
.
$key
.
'" '
.
((
in_array
(
$key
,
$value
)) ?
' selected'
:
''
) .
'>'
.
$title
.
'</option>'
;
}
$sResult
.=
'</select>'
;
}
return
$sResult
;
}
}
$arData
= [
//Get all fields and standard enum fields
'FIELDS'
=> [
'method'
=>
'crm.deal.fields'
,
'params'
=> []
],
'FIELD_VALUES_SOURCE_ID'
=> [
'method'
=>
'crm.status.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][SOURCE_ID][statusType]'
]]
],
'FIELD_VALUES_STATUS_ID'
=> [
'method'
=>
'crm.status.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][STATUS_ID][statusType]'
]]
],
'FIELD_VALUES_CURRENCY'
=> [
'method'
=>
'crm.currency.list'
,
//only 50 first values
'params'
=> [
'filter'
=> [
'ENTITY_ID'
=>
'$result[FIELDS][STATUS_ID][statusType]'
]]
],
'OWNER_TYPE'
=> [
'method'
=>
'crm.enum.ownertype'
,
'params'
=> []
],
];
if
(
$ID
>
0
)
{
//get item and standard enum field values if is update form
$arData
[
'ITEM'
] = [
'method'
=>
'crm.deal.get'
,
'params'
=> [
'id'
=>
$ID
]
];
$arData
[
'VALUE_CATEGORY_ID'
] = [
//only 50 first unlocked values
'method'
=>
'crm.dealcategory.list'
,
'params'
=> [
'filter'
=> [
'IS_LOCKED'
=>
'N'
]]
];
$arData
[
'VALUE_LEAD_ID'
] = [
'method'
=>
'crm.lead.get'
,
'params'
=> [
'id'
=>
'$result[ITEM][LEAD_ID]'
]
];
//QUOTE_ID is deprecated use crm.quote.list:
$arData
[
'VALUE_QUOTE_ID'
] = [
'method'
=>
'crm.quote.list'
,
'params'
=> [
'filter'
=> [
'DEAL_ID'
=>
$ID
]]
];
}
$arResult
=
CRest
::
callBatch
(
$arData
,
0
);
$arResult
=
$arResult
[
'result'
][
'result'
];
$sResult
=
''
;
$sResultCustom
=
''
;
if
(
is_array
(
$arResult
[
'FIELDS'
])):
if
(
isset
(
$arResult
[
'FIELDS'
][
'CONTACT_ID'
]))
//deprecated use crm.deal.contact.items.get
{
unset
(
$arResult
[
'FIELDS'
][
'CONTACT_ID'
]);
}
if
(
isset
(
$arResult
[
'FIELDS'
][
'CONTACT_IDS'
]))
// use crm.deal.contact.items.get
{
unset
(
$arResult
[
'FIELDS'
][
'CONTACT_IDS'
]);
}
foreach
(
$arResult
[
'FIELDS'
]
as
$key
=>
$arField
)
{
$value
=
''
;
$return
=
''
;
if
(!
empty
(
$arResult
[
'ITEM'
][
$key
]))
{
$value
=
$arResult
[
'ITEM'
][
$key
];
}
$arList
= (
isset
(
$arResult
[
'FIELD_VALUES_'
.
$key
])) ?
$arResult
[
'FIELD_VALUES_'
.
$key
] : [];
switch
(
$arField
[
'type'
])
{
case
'crm_category'
:
if
(!
empty
(
$arResult
[
'VALUE_'
.
$key
]))
{
$arList
=
array_column
(
$arResult
[
'VALUE_'
.
$key
],
'NAME'
,
'ID'
);
}
$return
=
CPrintForm
::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'crm_quote'
:
//only for QUOTE_ID read only type
if
(!
empty
(
$arResult
[
'VALUE_QUOTE_ID'
]))
{
$return
.=
implode
(
', '
,
array_column
(
$arResult
[
'VALUE_QUOTE_ID'
],
'TITLE'
));
}
break
;
case
'location'
:
$return
.=
'field not support location'
;
break
;
case
'crm_status'
:
if
(
empty
(
$arList
))
{
$arFieldsStatus
=
\CRest
::
get
(
'crm.status.list'
,
[
'filter'
=> [
'ENTITY_ID'
=>
$arField
[
'statusType'
]]]
);
if
(!
empty
(
$arFieldsStatus
[
'result'
]))
{
$arList
=
$arFieldsStatus
[
'result'
];
}
}
$arList
=
array_column
(
$arList
,
'NAME'
,
'STATUS_ID'
);
$return
=
CPrintForm
::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'crm_currency'
:
$arList
=
array_column
(
$arResult
[
'FIELD_VALUES_CURRENCY'
],
'FULL_NAME'
,
'CURRENCY'
);
$return
=
CPrintForm
::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'enumeration'
:
if
(!
empty
(
$arField
[
'items'
]))
{
$arList
=
array_column
(
$arField
[
'items'
],
'VALUE'
,
'ID'
);
}
$return
=
CPrintForm
::
select
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
],
$arList
);
break
;
case
'crm_multifield'
:
//its simple example: need multifield, check data type and more...
if
(!
empty
(
$value
) &&
is_array
(
$value
))
{
$value
=
reset
(
$value
)[
'VALUE'
];
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
false
,
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
break
;
case
'crm_lead'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
if
(!
empty
(
$arResult
[
'VALUE_LEAD_ID'
]) &&
$value
==
$arResult
[
'VALUE_LEAD_ID'
][
'ID'
])
{
$return
.=
'('
.
$arResult
[
'VALUE_LEAD_ID'
][
'TITLE'
] .
')'
;
}
break
;
case
'crm_company'
:
$arCompany
= [];
if
(!
empty
(
$arResult
[
'VALUE_'
.
$key
]))
{
$arCompany
=
$arResult
[
'VALUE_'
.
$key
];
}
elseif
(!
empty
(
$value
))
{
$arCompany
=
CRest
::
get
(
'crm.company.list'
, [
'filter'
=> [
'ID'
=>
$value
]]);
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
if
(!
empty
(
$arCompany
[
'result'
]))
{
$return
.=
'('
;
$i
=
0
;
foreach
(
$arCompany
[
'result'
]
as
$val
)
{
$i
++;
if
(
$i
>
1
)
{
$return
.=
', '
;
}
$return
.=
$val
[
'TITLE'
];
}
$return
.=
')'
;
}
break
;
case
'crm_contact'
:
$arContact
= [];
if
(!
empty
(
$arResult
[
'VALUE_'
.
$key
]))
{
$arContact
=
$arResult
[
'VALUE_'
.
$key
];
}
elseif
(!
empty
(
$value
))
{
$arContact
=
CRest
::
get
(
'crm.contact.list'
, [
'filter'
=> [
'ID'
=>
$value
]]);
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
if
(!
empty
(
$arContact
[
'result'
]))
{
$return
.=
'('
;
$i
=
0
;
foreach
(
$arContact
[
'result'
]
as
$val
)
{
$i
++;
if
(
$i
>
1
)
{
$return
.=
', '
;
}
$return
.=
implode
(
' '
, [
$val
[
'NAME'
],
$val
[
'LAST_NAME'
]]);
}
$return
.=
')'
;
}
break
;
case
'file'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'file'
,
]
);
if
(
$arField
[
'isMultiple'
])
{
if
(
is_array
(
$value
))
{
foreach
(
$value
as
$k
=>
$val
)
{
if
(!
empty
(
$val
[
'downloadUrl'
]))
{
$return
.=
'<br/><a href="'
.
$val
[
'downloadUrl'
] .
'">old file '
.
$k
.
'</a>'
;
}
}
}
}
else
{
if
(!
empty
(
$value
[
'downloadUrl'
]))
{
$return
.=
'<br/><a href="'
.
$value
[
'downloadUrl'
] .
'">old file</a>'
;
}
}
break
;
case
'date'
:
if
(!
empty
(
$value
))
{
$value
=
date
(
'Y-m-d'
,
strtotime
(
$value
));
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'date'
,
]
);
break
;
case
'datetime'
:
if
(!
empty
(
$value
))
{
$value
=
date
(
'Y-m-d\TH:i:s'
,
strtotime
(
$value
));
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'datetime-local'
,
]
);
break
;
case
'char'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
'Y'
,
'CHECKED'
=> (
$value
==
'Y'
) ?
true
:
false
,
'TYPE'
=>
'checkbox'
,
]
);
break
;
case
'boolean'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
'1'
,
'CHECKED'
=> (
$value
==
'Y'
) ?
true
:
false
,
'TYPE'
=>
'checkbox'
,
]
);
break
;
case
'double'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'number'
]
);
break
;
case
'user'
:
$arUser
= [];
if
(!
empty
(
$value
))
{
$arUser
=
CRest
::
get
(
'user.get'
, [
'filter'
=> [
'ID'
=>
$value
]]);
}
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'number'
]
);
if
(!
empty
(
$arUser
[
'result'
]))
{
$return
.=
'('
;
$i
=
0
;
foreach
(
$arUser
[
'result'
]
as
$val
)
{
$i
++;
if
(
$i
>
1
)
{
$return
.=
', '
;
}
$return
.=
implode
(
' '
, [
$val
[
'NAME'
],
$val
[
'LAST_NAME'
]]);
}
$return
.=
')'
;
}
break
;
case
'url'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
break
;
case
'integer'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'number'
,
]
);
break
;
case
'money'
:
list
(
$money
,
$currency
) =
explode
(
'|'
,
$value
);
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$money
,
'TYPE'
=>
'number'
,
]
);
$arList
=
array_column
(
$arResult
[
'FIELD_VALUES_CURRENCY'
],
'FULL_NAME'
,
'CURRENCY'
);
$return
.=
CPrintForm
::
select
(
[
'NAME'
=>
$key
.
'_CURRENCY'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$currency
],
$arList
);
break
;
case
'address'
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
break
;
case
'resourcebooking'
:
//some code booking
$return
=
'field not support'
;
break
;
default
:
$return
=
CPrintForm
::
input
(
[
'NAME'
=>
'form['
.
$key
.
']'
,
'REQUIRED'
=>
$arField
[
'isRequired'
],
'DISABLE'
=>
$arField
[
'isReadOnly'
],
'MULTIPLE'
=>
$arField
[
'isMultiple'
],
'VALUE'
=>
$value
,
'TYPE'
=>
'text'
,
]
);
break
;
}
if
(
strpos
(
$key
,
'UF_'
) ===
0
)
{
$sResultCustom
.=
'<div class="col-4 mt-3">'
.
((
$arField
[
'formLabel'
]) ?
$arField
[
'formLabel'
] :
$arField
[
'title'
]) .
': '
.
'</div>'
;
$sResultCustom
.=
'<div class="col-6 mt-3">'
.
$return
.
'</div>'
;
}
else
{
$sResult
.=
'<div class="col-4 mt-3">'
.
((
$arField
[
'formLabel'
]) ?
$arField
[
'formLabel'
] :
$arField
[
'title'
]) .
': '
.
'</div>'
;
$sResult
.=
'<div class="col-6 mt-3">'
.
$return
.
'</div>'
;
}
?>
<link rel=
"stylesheet"
href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
crossorigin=
"anonymous"
>
<script src=
"https://code.jquery.com/jquery-3.3.1.slim.min.js"
crossorigin=
"anonymous"
></script>
<script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"
crossorigin=
"anonymous"
></script>
<script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"
crossorigin=
"anonymous"
></script>
<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"
></script>
<script>
$(document).
ready
(function () {
$(
'#auto_form'
).
on
(
'submit'
, function (el) {
//event submit form
el.
preventDefault
();
//the default action of the event will not be triggered
var
formData =
new
FormData
(this);
var
xhr =
new
XMLHttpRequest
();
xhr.
open
(
"POST"
,
'auto_form.php'
);
xhr.onreadystatechange =
function
(
)
{
if
(this.readyState ===
4
)
{
if
(this.status >=
200
&& this.status <
400
)
{
// Success!
var
resp = this.responseText;
try
{
var
json = JSON.
parse
(resp);
if
(typeof json.message !==
'undefined'
)
{
alert
(json.message);
}
}
catch
(e)
{
return
false
;
}
}
else
{
alert
(
'error'
);
}
}
};
xhr.
send
(formData);
});
});
</script>
<div
class
="
container
">
<
form
id
="
auto_form
"
action
=""
enctype
="
multipart
/
form
-
data
"
method
="
post
">
<?
php
if
(!
empty
($
arResult
['
ITEM
']['
ID
']))://
for
update
entity
?>
<
input
type
="
hidden
"
name
="
form
[
ID
]"
value
="<?=$
arResult
['
ITEM
']['
ID
']?>">
<?
php
endif
;?>
<
h2
>
Standard
fields
</
h2
>
<
div
class
="
row
">
<?=$
sResult
?>
</
div
>
<
h2
>
Custom
fields
</
h2
>
<
div
class
="
row
">
<?=$
sResultCustom
?>
</
div
>
<
div
class
="
row
">
<
div
class
="
col
-
sm
-10
mt
-5">
<
input
type
="
submit
"
class
="
btn
btn
-
primary
"
value
="
Submit
">
</
div
>
</
div
>
</
form
>
</
div
>
<?
php
endif
;?>
File
auto_form.php
:
<?php
$arForm
= [];
foreach
(
$_POST
[
'form'
]
as
$key
=>
$item
) {
if
(
is_array
(
$item
)) {
$arForm
[
$key
] = [];
foreach
(
$item
as
$k
=>
$val
) {
$arForm
[
$key
][
$k
] =
htmlspecialchars
(
$val
);
}
}
else
{
$arForm
[
$key
] =
htmlspecialchars
(
$item
);
}
}
//make array multiple files for add to custom field
if
(!
empty
(
$_FILES
[
'form'
][
'tmp_name'
]) &&
is_array
(
$_FILES
[
'form'
][
'tmp_name'
])) {
foreach
(
$_FILES
[
'form'
][
'tmp_name'
]
as
$key
=>
$files
) {
if
(
is_array
(
$files
)) {
foreach
(
$files
as
$k
=>
$file
) {
$arForm
[
$key
][
$k
] = [
"fileData"
=> [
$_FILES
[
'form'
][
'name'
][
$key
][
$k
],
base64_encode
(
file_get_contents
(
$file
))
]
];
}
}
else
{
$arForm
[
$key
] = [
"fileData"
=> [
$_FILES
[
'form'
][
'name'
][
$key
],
base64_encode
(
file_get_contents
(
$files
))
]
];
}
}
}
$arResult
=
CRest
::
get
(
'crm.deal.fields'
, []);
if
(!
empty
(
$arResult
[
'result'
])) {
foreach
(
$arResult
[
'result'
]
as
$key
=>
$prop
) {
if
(!
isset
(
$arForm
[
$key
])) {
if
(!
$prop
[
'isReadOnly'
] &&
$prop
[
'type'
] !=
'file'
) {
if
(
$prop
[
'type'
] ==
'enumeration'
&&
$prop
[
'isMultiple'
]) {
//if type multiple enumeration to clean selected value need send: [false]
$arForm
[
$key
] = [
false
];
}
elseif
(
$prop
[
'isMultiple'
]) {
$arForm
[
$key
] = [];
}
else
{
$arForm
[
$key
] =
''
;
}
}
continue
;
}
//here may be any check field example by type
if
(
$prop
[
'type'
] ==
'crm_multifield'
) {
if
(
isset
(
$arForm
[
$key
])) {
$arForm
[
$key
] = [[
'VALUE'
=>
$arForm
[
$key
]]];
}
}
elseif
(
$prop
[
'type'
] ==
'money'
) {
$arForm
[
$key
] =
implode
(
'|'
, [
$arForm
[
$key
],
$arForm
[
$key
.
'_CURRENCY'
]]);
unset
(
$arForm
[
$key
.
'_CURRENCY'
]);
}
}
}
$arForm
[
'ID'
] =
intVal
(
$arForm
[
'ID'
]);
if
(
$arForm
[
'ID'
] >
0
) {
$method
=
'crm.deal.update'
;
$arParams
= [
'id'
=>
$arForm
[
'ID'
],
'fields'
=>
$arForm
];
$arMess
= [
'success'
=>
'Deal updated'
,
'error'
=>
'Deal not updated'
,
];
}
else
{
$method
=
'crm.deal.add'
;
$arParams
= [
'fields'
=>
$arForm
];
$arMess
= [
'success'
=>
'Deal added'
,
'error'
=>
'Deal not added'
,
];
}
$result
=
CRest
::
get
(
$method
,
$arParams
);
if
(!
empty
(
$result
[
'result'
])) {
echo
json_encode
(
[
'message'
=>
$arMess
[
'success'
] . ((
$method
==
'crm.deal.add'
) ?
' ID:'
.
$result
[
'result'
] :
''
)]
);
}
elseif
(!
empty
(
$result
[
'error_description'
])) {
echo
json_encode
([
'message'
=>
$arMess
[
'error'
] .
': '
.
$result
[
'error_description'
]]);
}
else
{
echo
json_encode
([
'message'
=>
$arMess
[
'error'
]]);
}
?>
Copied
Was the article helpful?
Yes
No
Previous
How to Create Your Company Edit Card
Next
How to Change or Remove Phone Numbers and Email

---

## How to Change or Delete Phone Numbers and Emails

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-edit-crm-objects/how-to-change-email-or-phone

How to Change or Delete Phone Numbers and Emails | Bitrix24 REST API and Marketplace Applications
How to Change or Delete Phone Numbers and Emails
How to Change or Delete Phone Numbers and Emails
Fields crm_multifield
Example with Email
1. Adding a Contact with Two Emails
2. Retrieving the Contact for Editing
3. Updating the Email List
Full Code Example
Example with Phone Numbers
1. Adding a Contact with Two Phone Numbers
2. Retrieving the Contact for Editing
3. Updating the Phone List
Full Code Example
Scope:
crm
Who can execute the method: users with permission to create and modify contacts in CRM
Contact data in CRM can contain multiple phone numbers and email addresses. Sometimes it is necessary to update existing values or remove unnecessary ones.
Let's create a contact with multiple emails and phone numbers, and then modify this information. To do this, we will sequentially execute three methods:
crm.contact.add
— create a contact in CRM,
crm.contact.get
— retrieve information about the created contact,
crm.contact.update
— update the email and phone data.
Fields crm_multifield
Fields crm_multifield
The system stores phone numbers and emails as an array of objects
crm_multifield
. Each object has the following fields:
{
ID
:
123
,
// Identifier of the existing record. Needed for updating
TYPE_ID
:
"PHONE"
,
// Type of the multifield
VALUE
:
"test@test.com"
,
// Value
VALUE_TYPE
:
"WORK"
// Type of the value
}
To delete a value from a multifield, pass the identifier
ID
and an empty value
VALUE
. Alternatively, specify the parameter
DELETE: 'Y'
instead of
VALUE
.
To update a value in a multifield, pass the identifier and the new value.
Example with Email
Example with Email
1. Adding a Contact with Two Emails
1. Adding a Contact with Two Emails
To create a contact in CRM, we will execute the method
crm.contact.add
. In the
fields
object, we will pass the fields:
NAME
— the name of the contact,
EMAIL
— an array of email addresses from
arNewEmail
.
Check which required fields are set for contacts in your Bitrix24. All required fields must be passed to the method
crm.contact.add
.
// preparing addresses in crm_multifield format
let
arNewEmail = [
{
VALUE
:
'work_email@nomail.com'
,
VALUE_TYPE
:
'WORK'
},
{
VALUE
:
'home_email@nomail.com'
,
VALUE_TYPE
:
'HOME'
}
];
// creating a new contact
BX24
.
callMethod
(
"crm.contact.add"
,
{
fields
: {
NAME
:
'New Contact'
,
EMAIL
: arNewEmail
}
}
);
As a result, we will receive the identifier of the new contact, for example,
25
.
{
"result"
:
25
}
2. Retrieving the Contact for Editing
2. Retrieving the Contact for Editing
To get information about the created contact, we use the method
crm.contact.get
with the identifier
ID
from the result of the previous request.
let
contactId = newContact.
data
().
result
;
// saving the ID of the created contact in a variable
// retrieving information about the contact by ID
BX24
.
callMethod
(
"crm.contact.get"
,
{
ID
: contactId
}
);
As a result, we will receive a description of all fields of the new contact.
{
"result"
:
{
"ID"
:
"25"
,
"NAME"
:
"New Contact"
,
...
,
// other fields
"EMAIL"
:
[
{
"ID"
:
"1967"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"work_email@nomail.com"
,
"TYPE_ID"
:
"EMAIL"
}
,
{
"ID"
:
"1969"
,
"VALUE_TYPE"
:
"HOME"
,
"VALUE"
:
"home_email@nomail.com"
,
"TYPE_ID"
:
"EMAIL"
}
]
}
}
3. Updating the Email List
3. Updating the Email List
To change the email list, we will execute the method
crm.contact.update
.
ID
— the identifier of the contact,
FIELDS
— an array of fields to be changed. We will pass the
EMAIL
field in the array and the new address values: for the first address, we will specify a new email, and for the second —
DELETE: 'Y'
to remove it.
// preparing an array with new email information
let
arUpdateEmail = [
{
ID
: contactData.
EMAIL
[
0
].
ID
,
VALUE
:
'new_work_email@example.com'
},
// changing value for the first email
{
ID
: contactData.
EMAIL
[
1
].
ID
,
'DELETE'
:
'Y'
}
// removing the second value
];
// updating the contact
BX24
.
callMethod
(
"crm.contact.update"
,
{
ID
: contactId,
FIELDS
: {
EMAIL
: arUpdateEmail
}
}
);
Upon successful update, the method will return
true
.
{
"result"
:
true
,
}
Full Code Example
Full Code Example
How to Use Examples in Documentation
JS
PHP
let
arNewEmail = [
{
'VALUE'
:
'work_email@nomail.com'
,
'VALUE_TYPE'
:
'WORK'
},
{
'VALUE'
:
'home_email@nomail.com'
,
'VALUE_TYPE'
:
'HOME'
}
];
// Step 1: Create a contact
BX24
.
callMethod
(
"crm.contact.add"
,
{
fields
: {
'NAME'
:
'New Contact'
,
'EMAIL'
: arNewEmail
}
},
function
(
newContact
) {
if
(newContact.
error
()) {
console
.
error
(
'Error creating contact: '
+ newContact.
error_description
());
}
else
{
let
contactId = newContact.
data
().
result
;
// Step 2: Retrieve contact data
BX24
.
callMethod
(
"crm.contact.get"
,
{
ID
: contactId
},
function
(
newContactData
) {
// Check for email presence
if
(newContactData.
data
().
result
.
EMAIL
?.
length
>=
2
) {
let
contactData = newContactData.
data
().
result
;
// Step 3: Prepare email update
let
arUpdateEmail = [
{
'ID'
: contactData.
EMAIL
[
0
].
ID
,
'VALUE'
:
'new_work_email@example.com'
},
{
'ID'
: contactData.
EMAIL
[
1
].
ID
,
'DELETE'
:
'Y'
}
];
// Updating contact
BX24
.
callMethod
(
"crm.contact.update"
,
{
ID
: contactId,
FIELDS
: {
'EMAIL'
: arUpdateEmail
}
},
function
(
resultContactChange
) {
if
(resultContactChange.
error
()) {
console
.
error
(
'Error updating contact:'
, resultContactChange.
error
());
}
else
{
console
.
log
(
'Contact successfully updated'
);
}
}
);
}
else
{
console
.
warn
(
'Not enough emails found for update.'
);
}
}
);
}
}
);
<?php
require_once
(
'crest.php'
);
// Preparing an array of emails in multifield format
$newEmail
= [
[
'VALUE'
=>
'work_email@nomail.com'
,
'VALUE_TYPE'
=>
'WORK'
],
[
'VALUE'
=>
'home_email@nomail.com'
,
'VALUE_TYPE'
=>
'HOME'
]
];
// Creating a contact
$newContact
=
CRest
::
call
(
'crm.contact.add'
, [
'fields'
=> [
'NAME'
=>
'New Contact'
,
'EMAIL'
=>
$newEmail
]
]);
if
(!
empty
(
$newContact
[
'result'
])) {
$contactId
=
$newContact
[
'result'
];
// Step 2: Retrieve contact data
$contactData
=
CRest
::
call
(
'crm.contact.get'
, [
'ID'
=>
$contactId
]);
if
(!
empty
(
$contactData
[
'result'
][
'EMAIL'
][
0
]) && !
empty
(
$contactData
[
'result'
][
'EMAIL'
][
1
])) {
// Step 3: Prepare email update
$updateEmail
= [
[
'ID'
=>
$contactData
[
'result'
][
'EMAIL'
][
0
][
'ID'
],
'VALUE'
=>
'new_work_email@example.com'
],
[
'ID'
=>
$contactData
[
'result'
][
'EMAIL'
][
1
][
'ID'
],
'DELETE'
=>
'Y'
]
// Removing second email
];
// Updating contact
$changeResult
=
CRest
::
call
(
'crm.contact.update'
, [
'ID'
=>
$contactId
,
'FIELDS'
=> [
'EMAIL'
=>
$updateEmail
]
]);
if
(!
empty
(
$changeResult
[
'error'
])) {
echo
'Error updating contact: '
.
$changeResult
[
'error_description'
];
}
else
{
echo
'Contact successfully updated.'
;
}
}
else
{
echo
'No emails found for update.'
;
}
}
else
{
echo
'Error creating contact: '
.
$newContact
[
'error_description'
];
}
?>
Example with Phone Numbers
Example with Phone Numbers
Similarly, you can update the list of phone numbers for the contact
PHONE
.
1. Adding a Contact with Two Phone Numbers
1. Adding a Contact with Two Phone Numbers
To create a contact in CRM, we will execute the method
crm.contact.add
. In the
fields
object, we will pass the fields:
NAME
— the name of the contact,
PHONE
— an array of phone numbers from
arNewPhone
.
Check which required fields are set for contacts in your Bitrix24. All required fields must be passed to the method
crm.contact.add
.
// preparing phones in crm_multifield format
let
arNewPhone = [
{
VALUE
:
'89991234567'
,
VALUE_TYPE
:
'WORK'
},
{
VALUE
:
'89997654321'
,
VALUE_TYPE
:
'HOME'
}
];
// creating a new contact
BX24
.
callMethod
(
"crm.contact.add"
,
{
fields
: {
NAME
:
'New Contact'
,
PHONE
: arNewPhone
}
}
);
As a result, we will receive the identifier of the new contact, for example,
25
.
{
"result"
:
25
}
2. Retrieving the Contact for Editing
2. Retrieving the Contact for Editing
To get information about the created contact, we use the method
crm.contact.get
with the identifier
ID
obtained from the previous request.
let
contactId = newContact.
data
().
result
;
// saving the ID of the created contact in a variable
// retrieving information about the contact by ID
BX24
.
callMethod
(
"crm.contact.get"
,
{
ID
: contactId
}
);
As a result, we will receive a description of all fields of the new contact.
{
"result"
:
{
"ID"
:
"25"
,
"NAME"
:
"New Contact"
,
...
,
// other fields
"PHONE"
:
[
{
"ID"
:
"1971"
,
"VALUE_TYPE"
:
"WORK"
,
"VALUE"
:
"89991234567"
,
"TYPE_ID"
:
"PHONE"
}
,
{
"ID"
:
"1973"
,
"VALUE_TYPE"
:
"HOME"
,
"VALUE"
:
"89997654321"
,
"TYPE_ID"
:
"PHONE"
}
]
}
}
3. Updating the Phone List
3. Updating the Phone List
To change the phone list, we will execute the method
crm.contact.update
.
ID
— the identifier of the contact,
FIELDS
— an array of fields to be changed. We will pass the
PHONE
field in the array and the new phone values: for the first phone, we will specify a new value, and for the second — an empty value to remove it.
// preparing an array with new phone information
let
arUpdatePhone = [
{
ID
: contactData.
PHONE
[
0
].
ID
,
VALUE
:
'81119876541'
},
{
ID
: contactData.
PHONE
[
1
].
ID
,
VALUE
:
''
}
];
// updating the contact
BX24
.
callMethod
(
"crm.contact.update"
,
{
ID
: contactId,
FIELDS
: {
PHONE
: arUpdatePhone
}
}
);
Upon successful update, the method will return
true
.
{
"result"
:
true
,
}
Full Code Example
Full Code Example
How to Use Examples in Documentation
JS
PHP
let
arNewPhone = [
{
VALUE
:
'89991234567'
,
VALUE_TYPE
:
'WORK'
},
{
VALUE
:
'89997654321'
,
VALUE_TYPE
:
'HOME'
}
];
// Step 1: Create a contact
BX24
.
callMethod
(
"crm.contact.add"
,
{
fields
: {
NAME
:
'New Contact'
,
PHONE
: arNewPhone
}
},
function
(
newContact
) {
if
(newContact.
error
()) {
console
.
error
(
'Error creating contact: '
+ newContact.
error_description
());
}
else
{
let
contactId = newContact.
data
().
result
;
// Step 2: Retrieve contact data
BX24
.
callMethod
(
"crm.contact.get"
,
{
ID
: contactId
},
function
(
contactData
) {
// Check for phone presence
if
(contactData.
data
().
result
.
PHONE
?.
length
>=
2
) {
let
phoneData = contactData.
data
().
result
;
// Step 3: Prepare phone update
let
arUpdatePhone = [
{
ID
: phoneData.
PHONE
[
0
].
ID
,
VALUE
:
'81119876541'
},
{
ID
: phoneData.
PHONE
[
1
].
ID
,
VALUE
:
''
}
];
// Updating contact
BX24
.
callMethod
(
"crm.contact.update"
,
{
ID
: contactId,
FIELDS
: {
PHONE
: arUpdatePhone
}
},
function
(
resultContactChange
) {
if
(resultContactChange.
error
()) {
console
.
error
(
'Error updating contact:'
, resultContactChange.
error
());
}
else
{
console
.
log
(
'Contact successfully updated'
);
}
}
);
}
else
{
console
.
warn
(
'Not enough phones found for update.'
);
}
}
);
}
}
);
<?php
require_once
(
'crest.php'
);
// Preparing an array of phones in multifield format
$newPhone
= [
[
'VALUE'
=>
'89991234567'
,
'VALUE_TYPE'
=>
'WORK'
],
[
'VALUE'
=>
'89997654321'
,
'VALUE_TYPE'
=>
'HOME'
]
];
// Creating a contact
$newContact
=
CRest
::
call
(
'crm.contact.add'
, [
'fields'
=> [
'NAME'
=>
'New Contact'
,
'PHONE'
=>
$newPhone
]
]);
if
(!
empty
(
$newContact
[
'result'
])) {
$contactId
=
$newContact
[
'result'
];
// Step 2: Retrieve contact data
$contactData
=
CRest
::
call
(
'crm.contact.get'
, [
'ID'
=>
$contactId
]);
if
(!
empty
(
$contactData
[
'result'
][
'PHONE'
][
0
]) && !
empty
(
$contactData
[
'result'
][
'PHONE'
][
1
])) {
// Step 3: Prepare phone update
$updatePhone
= [
[
'ID'
=>
$contactData
[
'result'
][
'PHONE'
][
0
][
'ID'
],
'VALUE'
=>
'81119876541'
],
[
'ID'
=>
$contactData
[
'result'
][
'PHONE'
][
1
][
'ID'
],
'VALUE'
=>
''
]
// Removing second phone
];
// Updating contact
$changeResult
=
CRest
::
call
(
'crm.contact.update'
, [
'ID'
=>
$contactId
,
'FIELDS'
=> [
'PHONE'
=>
$updatePhone
]
]);
if
(!
empty
(
$changeResult
[
'error'
])) {
echo
'Error updating contact: '
.
$changeResult
[
'error_description'
];
}
else
{
echo
'Contact successfully updated.'
;
}
}
else
{
echo
'No phones found for update.'
;
}
}
else
{
echo
'Error creating contact: '
.
$newContact
[
'error_description'
];
}
?>
Copied
Was the article helpful?
Yes
No
Previous
How to Create Your Deal Edit Card
Next
How to Move an Activity Between Entities of the Same Type

---

## How to Transfer an Activity Between Entities of the Same Type

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-edit-crm-objects/how-to-move-activity

How to Transfer an Activity Between Entities of the Same Type | Bitrix24 REST API and Marketplace Applications
How to Transfer an Activity Between Entities of the Same Type
How to Transfer an Activity Between Entities of the Same Type
1. Retrieve the Activity ID
2. Create a New Entity
3. Transfer the Activity Between Entities
Code Example
Scope:
crm
Who can execute the method: users with permission to modify CRM entities
Activities related to CRM entities are stored in the timeline of the entity's detail form. Transferring an activity from one entity to another may be necessary when multiple emails or calls related to different leads are captured in a single lead. In this case, the original lead can be split into several new ones, and the activities can be transferred for accurate data tracking.
To transfer an activity, we will sequentially execute three methods:
crm.activity.list
— retrieve the activity ID
crm.lead.add
— create an entity to which we will transfer the activity, in this example, a lead
crm.activity.binding.move
— perform the activity transfer
1. Retrieve the Activity ID
1. Retrieve the Activity ID
We will use the method
crm.activity.list
with the following filters:
OWNER_TYPE_ID
—
object type
, specify
1
for leads
OWNER_ID
— ID of the entity from which we will transfer the activity
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"crm.activity.list"
,
{
filter
:
{
"OWNER_TYPE_ID"
:
1
,
"OWNER_ID"
:
1000977
},
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
'crm.activity.list'
,
[
'filter'
=> [
'OWNER_TYPE_ID'
=>
1
,
'OWNER_ID'
=>
1000977
]
]
);
As a result, we will receive all activities associated with the specified entity.
{
"result"
:
[
{
"ID"
:
"7685"
,
"OWNER_ID"
:
"1000977"
,
"OWNER_TYPE_ID"
:
"1"
,
"TYPE_ID"
:
"4"
,
"PROVIDER_ID"
:
"CRM_EMAIL"
,
"PROVIDER_TYPE_ID"
:
"EMAIL"
,
"PROVIDER_GROUP_ID"
:
null
,
"ASSOCIATED_ENTITY_ID"
:
"0"
,
"SUBJECT"
:
"for leads"
,
"CREATED"
:
"2025-03-10T10:57:41+02:00"
,
"LAST_UPDATED"
:
"2025-03-10T10:57:41+02:00"
,
"START_TIME"
:
"2025-03-10T10:57:34+02:00"
,
"END_TIME"
:
"2025-03-10T20:00:00+02:00"
,
"DEADLINE"
:
"9999-12-31T00:00:00+02:00"
,
"COMPLETED"
:
"N"
,
"STATUS"
:
"1"
,
"RESPONSIBLE_ID"
:
"29"
,
"PRIORITY"
:
"2"
,
"NOTIFY_TYPE"
:
"0"
,
"NOTIFY_VALUE"
:
"0"
,
"DESCRIPTION"
:
"<div>first email</div>\r\n"
,
"DESCRIPTION_TYPE"
:
"3"
,
"DIRECTION"
:
"1"
,
"LOCATION"
:
""
,
"SETTINGS"
:
{
"EMAIL_META"
:
{
"__email"
:
"some_email@gmail.com"
,
"from"
:
"Some client <some_client@gmail.com>"
,
"replyTo"
:
""
,
"to"
:
"\"some_email@gmail.com\" <some_email@gmail.com>"
,
"cc"
:
""
,
"bcc"
:
""
}
,
"SANITIZE_ON_VIEW"
:
1
}
,
"ORIGINATOR_ID"
:
null
,
"ORIGIN_ID"
:
null
,
"AUTHOR_ID"
:
"1"
,
"EDITOR_ID"
:
"29"
,
"PROVIDER_PARAMS"
:
[
]
,
"PROVIDER_DATA"
:
null
,
"RESULT_MARK"
:
"0"
,
"RESULT_VALUE"
:
null
,
"RESULT_SUM"
:
null
,
"RESULT_CURRENCY_ID"
:
null
,
"RESULT_STATUS"
:
"0"
,
"RESULT_STREAM"
:
"0"
,
"RESULT_SOURCE_ID"
:
null
,
"AUTOCOMPLETE_RULE"
:
"0"
}
,
{
"ID"
:
"7687"
,
"OWNER_ID"
:
"1000977"
,
"OWNER_TYPE_ID"
:
"1"
,
"TYPE_ID"
:
"4"
,
"PROVIDER_ID"
:
"CRM_EMAIL"
,
"PROVIDER_TYPE_ID"
:
"EMAIL"
,
"PROVIDER_GROUP_ID"
:
null
,
"ASSOCIATED_ENTITY_ID"
:
"0"
,
"SUBJECT"
:
"for leads"
,
"CREATED"
:
"2025-03-10T10:58:13+02:00"
,
"LAST_UPDATED"
:
"2025-03-10T10:58:13+02:00"
,
"START_TIME"
:
"2025-03-10T10:58:08+02:00"
,
"END_TIME"
:
"2025-03-10T20:00:00+02:00"
,
"DEADLINE"
:
"9999-12-31T00:00:00+02:00"
,
"COMPLETED"
:
"N"
,
"STATUS"
:
"1"
,
"RESPONSIBLE_ID"
:
"29"
,
"PRIORITY"
:
"2"
,
"NOTIFY_TYPE"
:
"0"
,
"NOTIFY_VALUE"
:
"0"
,
"DESCRIPTION"
:
"<div>second email</div>\r\n"
,
"DESCRIPTION_TYPE"
:
"3"
,
"DIRECTION"
:
"1"
,
"LOCATION"
:
""
,
"SETTINGS"
:
{
"EMAIL_META"
:
{
"__email"
:
"some_email@gmail.com"
,
"from"
:
"Some client <some_client@gmail.com>"
,
"replyTo"
:
""
,
"to"
:
"\"some_email@gmail.com\" <some_email@gmail.com>"
,
"cc"
:
""
,
"bcc"
:
""
}
,
"SANITIZE_ON_VIEW"
:
1
}
,
"ORIGINATOR_ID"
:
null
,
"ORIGIN_ID"
:
null
,
"AUTHOR_ID"
:
"1"
,
"EDITOR_ID"
:
"29"
,
"PROVIDER_PARAMS"
:
[
]
,
"PROVIDER_DATA"
:
null
,
"RESULT_MARK"
:
"0"
,
"RESULT_VALUE"
:
null
,
"RESULT_SUM"
:
null
,
"RESULT_CURRENCY_ID"
:
null
,
"RESULT_STATUS"
:
"0"
,
"RESULT_STREAM"
:
"0"
,
"RESULT_SOURCE_ID"
:
null
,
"AUTOCOMPLETE_RULE"
:
"0"
}
]
,
"total"
:
2
}
We will select the desired activity from the list received and save its
ID
:
7687
. In the
code example
, the selection of the activity is implemented by searching for a phrase from the
DESCRIPTION
field.
2. Create a New Entity
2. Create a New Entity
To create a new lead to which we will transfer the email activity, we will execute the method
crm.lead.add
with the following parameters:
fields[TITLE]
— title of the lead
fields[ASSIGNED_BY_ID]
— identifier of the person responsible for the new lead
params[REGISTER_SONET_EVENT]
— parameter for registering notifications, specify
Y
so that system notifications are triggered for the new lead upon creation
All required fields for leads in your Bitrix24 must be specified in the method; otherwise, the lead will not be created. You can check which fields are required using the method
crm.lead.fields
, which is called without parameters.
JS
PHP
BX24
.
callMethod
(
"crm.lead.add"
,
{
fields
:
{
TITLE
:
"Second lead"
,
ASSIGNED_BY_ID
:
1
,
},
params
: {
REGISTER_SONET_EVENT
:
"Y"
,
}
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
'crm.lead.add'
,
[
'fields'
=> [
'TITLE'
=>
'Second lead'
,
'ASSIGNED_BY_ID'
=>
1
,
],
'params'
=> [
'REGISTER_SONET_EVENT'
=>
'Y'
,
]
]
);
As a result, we will receive the ID of the created lead.
{
"result"
:
1000979
}
3. Transfer the Activity Between Entities
3. Transfer the Activity Between Entities
To transfer the activity, we will use the method
crm.activity.binding.move
with the following parameters:
activityId
— ID of the activity, obtained in
step 1
using the method
crm.activity.list
sourceEntityTypeId
— ID of the
object type
from which we are transferring the activity
sourceEntityId
— ID of the entity from which we are transferring the activity
targetEntityTypeId
— ID of the
object type
to which we are transferring the activity
targetEntityId
— ID of the entity to which we are transferring the activity, obtained in
step 2
using the method
crm.lead.add
sourceEntityTypeId
and
targetEntityTypeId
must have the same object type value.
JS
PHP
BX24
.
callMethod
(
'crm.activity.binding.move'
,
{
activityId
:
7687
,
sourceEntityTypeId
:
1
,
sourceEntityId
:
1000977
,
targetEntityTypeId
:
1
,
targetEntityId
:
1000979
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
'crm.activity.binding.move'
,
[
'activityId'
=>
7687
,
'sourceEntityTypeId'
=>
1
,
'sourceEntityId'
=>
1000977
,
'targetEntityTypeId'
=>
1
,
'targetEntityId'
=>
1000979
]
);
As a result, we will receive
true
, indicating that the activity transfer was successful. If you receive an
error
in the result, review the possible error descriptions in the documentation for the method
crm.activity.binding.move
.
{
"result"
:
true
}
Code Example
Code Example
JS
PHP
// Function to execute all steps
function
transferActivity
(
) {
// Prompt user for the ID of the first lead
const
firstLeadId =
prompt
(
"Enter the ID of the first lead:"
);
// Prompt user for the search phrase for the description field
const
searchPhrase =
prompt
(
"Enter the phrase to search in the email body:"
);
// Step 1: Retrieve the list of activities for the specified lead
BX24
.
callMethod
(
"crm.activity.list"
,
{
filter
: {
"OWNER_TYPE_ID"
:
1
,
"OWNER_ID"
: firstLeadId
},
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
(result.
error
());
return
;
}
const
activities = result.
data
();
const
targetActivity = activities.
find
(
activity
=>
activity.
DESCRIPTION
.
includes
(searchPhrase));
if
(!targetActivity) {
console
.
log
(
`Activity with description containing '
${searchPhrase}
' not found.`
);
return
;
}
const
activityId = targetActivity.
ID
;
// Step 2: Create a new lead
BX24
.
callMethod
(
"crm.lead.add"
,
{
fields
: {
TITLE
:
"Second lead"
,
ASSIGNED_BY_ID
:
1
,
},
params
: {
REGISTER_SONET_EVENT
:
"Y"
,
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
(result.
error
());
return
;
}
const
newLeadId = result.
data
();
// Step 3: Transfer the activity
BX24
.
callMethod
(
'crm.activity.binding.move'
,
{
activityId
: activityId,
sourceEntityTypeId
:
1
,
sourceEntityId
: firstLeadId,
targetEntityTypeId
:
1
,
targetEntityId
: newLeadId
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
(result.
error
());
}
else
{
console
.
log
(
"Activity successfully transferred."
);
}
}
);
}
);
}
);
}
// Execute the function
transferActivity
();
require_once
(
'crest.php'
);
// Function to execute all steps
function
transferActivity
(
$firstLeadId
,
$searchPhrase
)
{
// Step 1: Retrieve the list of activities for the specified lead
$result
=
CRest
::
call
(
'crm.activity.list'
,
[
'filter'
=> [
'OWNER_TYPE_ID'
=>
1
,
'OWNER_ID'
=>
$firstLeadId
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
'Error: '
.
$result
[
'error_description'
];
return
;
}
$activities
=
$result
[
'result'
];
$targetActivity
=
null
;
foreach
(
$activities
as
$activity
) {
if
(
strpos
(
$activity
[
'DESCRIPTION'
],
$searchPhrase
) !==
false
) {
$targetActivity
=
$activity
;
break
;
}
}
if
(!
$targetActivity
) {
echo
"Activity with description containing '
{$searchPhrase}
' not found."
;
return
;
}
$activityId
=
$targetActivity
[
'ID'
];
// Step 2: Create a new lead
$leadResult
=
CRest
::
call
(
'crm.lead.add'
,
[
'fields'
=> [
'TITLE'
=>
'Second lead'
,
'ASSIGNED_BY_ID'
=>
1
,
],
'params'
=> [
'REGISTER_SONET_EVENT'
=>
'Y'
,
]
]
);
if
(
isset
(
$leadResult
[
'error'
])) {
echo
'Error: '
.
$leadResult
[
'error_description'
];
return
;
}
$newLeadId
=
$leadResult
[
'result'
];
// Step 3: Transfer the activity
$moveResult
=
CRest
::
call
(
'crm.activity.binding.move'
,
[
'activityId'
=>
$activityId
,
'sourceEntityTypeId'
=>
1
,
'sourceEntityId'
=>
$firstLeadId
,
'targetEntityTypeId'
=>
1
,
'targetEntityId'
=>
$newLeadId
]
);
if
(
isset
(
$moveResult
[
'error'
])) {
echo
'Error: '
.
$moveResult
[
'error_description'
];
}
else
{
echo
'Activity successfully transferred.'
;
}
}
// Prompt user for the ID of the first lead and the search phrase
$firstLeadId
=
readline
(
"Enter the ID of the first lead: "
);
$searchPhrase
=
readline
(
"Enter the phrase to search in the email body: "
);
// Execute the function
transferActivity
(
$firstLeadId
,
$searchPhrase
);
Copied
Was the article helpful?
Yes
No
Previous
How to Change or Remove Phone Numbers and Email
Next
How to Move an Activity from One Object Type to Another

---

## How to Transfer an Activity from One Object Type to Another

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-edit-crm-objects/how-to-move-activity-between-objects

How to Transfer an Activity from One Object Type to Another | Bitrix24 REST API and Marketplace Applications
How to Transfer an Activity from One Object Type to Another
How to Transfer an Activity from One Object Type to Another
1. Retrieve the Activity ID
2. Retrieve the Company ID
3. Add the Binding of the Activity to the Company
4. Remove the Binding of the Activity from the Lead
Code Example
Scope:
crm
Who can execute the method: users with permission to modify CRM entities
Activities related to CRM entities are stored in the timeline of the entity's card. Transferring activities may be necessary between different types of entities:
lead
,
deal
,
contact
,
company
,
invoice
,
SPA
. For example, if a client has two email addresses but only one is saved in your Bitrix24 company card, when the client sends an email from the second, unknown address, the email will create a new lead instead of attaching to the existing company card. To keep client information in one place, you can transfer the activity from the lead to the company card.
To transfer the activity, we will sequentially execute four methods:
crm.activity.list
— retrieve the activity ID
crm.company.list
— retrieve the company ID for transferring the activity
crm.activity.binding.add
— add the binding of the activity to the company
crm.activity.binding.delete
— remove the binding of the activity from the lead
1. Retrieve the Activity ID
1. Retrieve the Activity ID
Use the method
crm.activity.list
with the filter:
OWNER_TYPE_ID
—
object type
, specify
1
for lead
OWNER_ID
— ID of the entity from which we will transfer the activity
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
"crm.activity.list"
,
{
filter
:
{
"OWNER_TYPE_ID"
:
1
,
"OWNER_ID"
:
1000977
},
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
'crm.activity.list'
,
[
'filter'
=> [
'OWNER_TYPE_ID'
=>
1
,
'OWNER_ID'
=>
1000977
]
]
);
As a result, we will receive all activities related to the specified entity.
{
"result"
:
[
{
"ID"
:
"7685"
,
"OWNER_ID"
:
"1000977"
,
"OWNER_TYPE_ID"
:
"1"
,
"TYPE_ID"
:
"4"
,
"PROVIDER_ID"
:
"CRM_EMAIL"
,
"PROVIDER_TYPE_ID"
:
"EMAIL"
,
"PROVIDER_GROUP_ID"
:
null
,
"ASSOCIATED_ENTITY_ID"
:
"0"
,
"SUBJECT"
:
"for leads"
,
"CREATED"
:
"2025-03-10T10:57:41+03:00"
,
"LAST_UPDATED"
:
"2025-03-10T10:57:41+03:00"
,
"START_TIME"
:
"2025-03-10T10:57:34+03:00"
,
"END_TIME"
:
"2025-03-10T20:00:00+03:00"
,
"DEADLINE"
:
"9999-12-31T00:00:00+03:00"
,
"COMPLETED"
:
"N"
,
"STATUS"
:
"1"
,
"RESPONSIBLE_ID"
:
"29"
,
"PRIORITY"
:
"2"
,
"NOTIFY_TYPE"
:
"0"
,
"NOTIFY_VALUE"
:
"0"
,
"DESCRIPTION"
:
"<div>first email</div>\r\n"
,
"DESCRIPTION_TYPE"
:
"3"
,
"DIRECTION"
:
"1"
,
"LOCATION"
:
""
,
"SETTINGS"
:
{
"EMAIL_META"
:
{
"__email"
:
"some_email@gmail.com"
,
"from"
:
"Some client <some_client@gmail.com>"
,
"replyTo"
:
""
,
"to"
:
"\"some_email@gmail.com\" <some_email@gmail.com>"
,
"cc"
:
""
,
"bcc"
:
""
}
,
"SANITIZE_ON_VIEW"
:
1
}
,
"ORIGINATOR_ID"
:
null
,
"ORIGIN_ID"
:
null
,
"AUTHOR_ID"
:
"1"
,
"EDITOR_ID"
:
"29"
,
"PROVIDER_PARAMS"
:
[
]
,
"PROVIDER_DATA"
:
null
,
"RESULT_MARK"
:
"0"
,
"RESULT_VALUE"
:
null
,
"RESULT_SUM"
:
null
,
"RESULT_CURRENCY_ID"
:
null
,
"RESULT_STATUS"
:
"0"
,
"RESULT_STREAM"
:
"0"
,
"RESULT_SOURCE_ID"
:
null
,
"AUTOCOMPLETE_RULE"
:
"0"
}
]
,
"total"
:
1
}
2. Retrieve the Company ID
2. Retrieve the Company ID
Use the method
crm.company.list
with the filter:
TITLE
— company name
To limit the returned fields, add the
select
parameter and specify only the
ID
and
TITLE
fields.
JS
PHP
BX24
.
callMethod
(
"crm.company.list"
,
{
filter
: {
"TITLE"
:
"Company_Name"
},
select
: [
"ID"
,
"TITLE"
]
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
'crm.company.list'
,
[
'filter'
=> [
'TITLE'
=>
'Company_Name'
],
'select'
=> [
'ID'
,
'TITLE'
]
]
);
As a result, we will receive the company ID —
ID
:
173
.
{
"result"
:
[
{
"ID"
:
"173"
,
"TITLE"
:
"Company_Name"
}
]
,
"total"
:
1
}
3. Add the Binding of the Activity to the Company
3. Add the Binding of the Activity to the Company
To bind the activity and the company, use the method
crm.activity.binding.add
with the parameters:
activityId
— ID of the activity, obtained in
step 1
using the method
crm.activity.list
entityTypeId
— ID of the
object type
, specify
4
for company
entityId
— ID of the company, obtained in
step 2
using the method
crm.company.list
JS
PHP
BX24
.
callMethod
(
'crm.activity.binding.add'
,
{
activityId
:
7685
,
entityTypeId
:
4
,
entityId
:
173
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
'crm.activity.binding.add'
,
[
'activityId'
=>
7685
,
'entityTypeId'
=>
4
,
'entityId'
=>
173
]
);
As a result, we will receive
true
, indicating that the binding for the activity was successfully created. If you receive an
error
in the result, review the possible error descriptions in the documentation for the method
crm.activity.binding.add
.
{
"result"
:
true
}
4. Remove the Binding of the Activity from the Lead
4. Remove the Binding of the Activity from the Lead
Use the method
crm.activity.binding.delete
with the parameters:
activityId
— ID of the activity, obtained in
step 1
using the method
crm.activity.list
entityTypeId
— ID of the
object type
, specify
1
for lead
entityId
— ID of the lead from which we are removing the activity
JS
PHP
BX24
.
callMethod
(
'crm.activity.binding.delete'
,
{
activityId
:
7685
,
entityTypeId
:
1
,
entityId
:
1000977
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
'crm.activity.binding.delete'
,
[
'activityId'
=>
7685
,
'entityTypeId'
=>
1
,
'entityId'
=>
1000977
]
);
As a result, we will receive
true
, indicating that the binding of the activity from the lead was successfully removed. If you receive an
error
in the result, review the possible error descriptions in the documentation for the method
crm.activity.binding.delete
.
{
"result"
:
true
}
Code Example
Code Example
JS
PHP
// Function to execute all steps
function
transferActivityToCompany
(
) {
// Prompt user for lead ID
const
leadId =
prompt
(
"Enter lead ID:"
);
// Prompt user for company name
const
companyName =
prompt
(
"Enter company name:"
);
// Step 1: Retrieve the list of activities for the specified lead
BX24
.
callMethod
(
"crm.activity.list"
,
{
filter
: {
"OWNER_TYPE_ID"
:
1
,
"OWNER_ID"
: leadId
},
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
(result.
error
());
return
;
}
const
activities = result.
data
();
if
(activities.
length
===
0
) {
console
.
log
(
"No activities found for the specified lead."
);
return
;
}
const
activityId = activities[
0
].
ID
;
// Step 2: Search for the company by name
BX24
.
callMethod
(
"crm.company.list"
,
{
filter
: {
"TITLE"
: companyName },
select
: [
"ID"
,
"TITLE"
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
(result.
error
());
return
;
}
const
companies = result.
data
();
if
(companies.
length
===
0
) {
console
.
log
(
"No company found with the specified name."
);
return
;
}
const
companyId = companies[
0
].
ID
;
// Step 3: Create a binding for the found activity and company
BX24
.
callMethod
(
'crm.activity.binding.add'
,
{
activityId
: activityId,
entityTypeId
:
4
,
entityId
: companyId
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
(result.
error
());
return
;
}
console
.
log
(
"Activity successfully bound to the company."
);
// Step 4: Remove the binding of the activity from the lead
BX24
.
callMethod
(
'crm.activity.binding.delete'
,
{
activityId
: activityId,
entityTypeId
:
1
,
entityId
: leadId
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
(result.
error
());
}
else
{
console
.
log
(
"Activity successfully unbound from the lead."
);
}
}
);
}
);
}
);
}
);
}
// Execute the function
transferActivityToCompany
();
require_once
(
'crest.php'
);
// Function to execute all steps
function
transferActivityToCompany
(
$leadId
,
$companyName
)
{
// Step 1: Retrieve the list of activities for the specified lead
$activityResult
=
CRest
::
call
(
'crm.activity.list'
,
[
'filter'
=> [
'OWNER_TYPE_ID'
=>
1
,
'OWNER_ID'
=>
$leadId
]
]
);
if
(
isset
(
$activityResult
[
'error'
])) {
echo
'Error: '
.
$activityResult
[
'error_description'
];
return
;
}
$activities
=
$activityResult
[
'result'
];
if
(
empty
(
$activities
)) {
echo
"No activities found for the specified lead."
;
return
;
}
$activityId
=
$activities
[
0
][
'ID'
];
// Step 2: Search for the company by name
$companyResult
=
CRest
::
call
(
'crm.company.list'
,
[
'filter'
=> [
'TITLE'
=>
$companyName
],
'select'
=> [
'ID'
,
'TITLE'
]
]
);
if
(
isset
(
$companyResult
[
'error'
])) {
echo
'Error: '
.
$companyResult
[
'error_description'
];
return
;
}
$companies
=
$companyResult
[
'result'
];
if
(
empty
(
$companies
)) {
echo
"No company found with the specified name."
;
return
;
}
$companyId
=
$companies
[
0
][
'ID'
];
// Step 3: Create a binding for the found activity and company
$bindingAddResult
=
CRest
::
call
(
'crm.activity.binding.add'
,
[
'activityId'
=>
$activityId
,
'entityTypeId'
=>
4
,
'entityId'
=>
$companyId
]
);
if
(
isset
(
$bindingAddResult
[
'error'
])) {
echo
'Error: '
.
$bindingAddResult
[
'error_description'
];
return
;
}
echo
"Activity successfully bound to the company."
;
// Step 4: Remove the binding of the activity from the lead
$bindingDeleteResult
=
CRest
::
call
(
'crm.activity.binding.delete'
,
[
'activityId'
=>
$activityId
,
'entityTypeId'
=>
1
,
'entityId'
=>
$leadId
]
);
if
(
isset
(
$bindingDeleteResult
[
'error'
])) {
echo
'Error: '
.
$bindingDeleteResult
[
'error_description'
];
}
else
{
echo
"Activity successfully unbound from the lead."
;
}
}
// Prompt user for lead ID and company name
$leadId
=
readline
(
"Enter lead ID: "
);
$companyName
=
readline
(
"Enter company name: "
);
// Execute the function
transferActivityToCompany
(
$leadId
,
$companyName
);
Copied
Was the article helpful?
Yes
No
Previous
How to Move an Activity Between Entities of the Same Type
Next
How to Enter the Payment Date in the Deal Field

---

## How to Save the Payment Date in the Deal Field

**Source:** https://apidocs.bitrix24.com/tutorials/crm/how-to-edit-crm-objects/how-to-set-paid-date-to-deal

How to Save the Payment Date in the Deal Field | Bitrix24 REST API and Marketplace Applications
How to Save the Payment Date in the Deal Field
How to Save the Payment Date in the Deal Field
1. Getting the Field Identifier
2. Getting the Payment Date
3. Saving the Date in the Deal Field
Checking the Value of the Deal Field
Code Example
Scope:
crm
Who can execute the method: users with permission to modify CRM entity
In Bitrix24, the payment date is stored in payment documents. Sometimes, the payment date may be needed in the deal field:
for integrations with external systems,
BI Builder reports,
automations through Automation rules and workflows.
To transfer the payment date information to the deal, we will sequentially execute three methods:
crm.deal.userfield.list
— we will get the identifier of the deal field where we will save the information about the date
crm.item.payment.list
— we will get the payment information
crm.deal.update
— we will save the payment date in the deal field
1. Getting the Field Identifier
1. Getting the Field Identifier
To get the identifier of the deal field, we use the method
crm.deal.userfield.list
with the parameters:
filter[LANG]
— we use this language filter to display field names in the desired language. Without this filter, the names will not be displayed.
filter[USER_TYPE_ID]
— we use this field type filter to get only fields of type "Date" in the result.
How to Use Examples in Documentation
JS
PHP
BX24
.
callMethod
(
'crm.deal.userfield.list'
,
{
filter
: {
LANG
:
'de'
,
USER_TYPE_ID
:
'date'
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
'crm.deal.userfield.list'
,
[
'filter'
=> [
'LANG'
=>
'de'
,
'USER_TYPE_ID'
=>
'date'
]
}
);
As a result, we will get information about all deal fields of type "Date". We will identify the appropriate field by its name in the
EDIT_FORM_LABEL
parameter. The field identifier will be taken from the
FIELD_NAME
field.
{
"result"
:
[
{
"ID"
:
"6787"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1723209318"
,
"USER_TYPE_ID"
:
"date"
,
"XML_ID"
:
null
,
"SORT"
:
"150"
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"E"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_IN_LIST"
:
"Y"
,
"IS_SEARCHABLE"
:
"N"
,
"SETTINGS"
:
{
"DEFAULT_VALUE"
:
{
"TYPE"
:
"NONE"
,
"VALUE"
:
""
}
}
,
"EDIT_FORM_LABEL"
:
"Payment Date"
,
"LIST_COLUMN_LABEL"
:
"Payment Date"
,
"LIST_FILTER_LABEL"
:
"Payment Date"
,
"ERROR_MESSAGE"
:
null
,
"HELP_MESSAGE"
:
null
}
,
{
"ID"
:
"6795"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1723206732"
,
"USER_TYPE_ID"
:
"date"
,
"XML_ID"
:
null
,
"SORT"
:
"150"
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"E"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_IN_LIST"
:
"Y"
,
"IS_SEARCHABLE"
:
"N"
,
"SETTINGS"
:
{
"DEFAULT_VALUE"
:
{
"TYPE"
:
"NONE"
,
"VALUE"
:
""
}
}
,
"EDIT_FORM_LABEL"
:
"End of Campaign"
,
"LIST_COLUMN_LABEL"
:
"End of Campaign"
,
"LIST_FILTER_LABEL"
:
"End of Campaign"
,
"ERROR_MESSAGE"
:
null
,
"HELP_MESSAGE"
:
null
}
,
{
"ID"
:
"6805"
,
"ENTITY_ID"
:
"CRM_DEAL"
,
"FIELD_NAME"
:
"UF_CRM_1723206709"
,
"USER_TYPE_ID"
:
"date"
,
"XML_ID"
:
null
,
"SORT"
:
"150"
,
"MULTIPLE"
:
"N"
,
"MANDATORY"
:
"N"
,
"SHOW_FILTER"
:
"E"
,
"SHOW_IN_LIST"
:
"Y"
,
"EDIT_IN_LIST"
:
"Y"
,
"IS_SEARCHABLE"
:
"N"
,
"SETTINGS"
:
{
"DEFAULT_VALUE"
:
{
"TYPE"
:
"NONE"
,
"VALUE"
:
""
}
}
,
"EDIT_FORM_LABEL"
:
"Start of Campaign"
,
"LIST_COLUMN_LABEL"
:
"Start of Campaign"
,
"LIST_FILTER_LABEL"
:
"Start of Campaign"
,
"ERROR_MESSAGE"
:
null
,
"HELP_MESSAGE"
:
null
}
]
,
"total"
:
3
,
}
2. Getting the Payment Date
2. Getting the Payment Date
We use the method
crm.item.payment.list
with the parameters:
entityId
—
ID
of the deal for which we are getting the payment date
entityTypeId
—
object type
, we will specify
2
for the deal
JS
PHP
BX24
.
callMethod
(
'crm.item.payment.list'
, {
entityId
:
6917
,
entityTypeId
:
2
,
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
'crm.item.payment.list'
,
[
'entityId'
=>
6917
,
'entityTypeId'
=>
2
]
);
As a result, we will get a list of payments with fields for the deal. We will take the payment date from the
datePaid
field.
{
"result"
:
[
{
"id"
:
503
,
"accountNumber"
:
"831/1"
,
"paid"
:
"Y"
,
"datePaid"
:
"2025-04-29T13:03:20+02:00"
,
"empPaidId"
:
1
,
"paySystemId"
:
19
,
"sum"
:
15
,
"currency"
:
"EUR"
,
"paySystemName"
:
"YooKassa"
}
]
,
}
3. Saving the Date in the Deal Field
3. Saving the Date in the Deal Field
To modify the deal field and record the payment date in it, we use the method
crm.deal.update
with the parameters:
id
—
ID
of the deal, required parameter
fields[UF_CRM_1723209318]
— we will specify the value from the
datePaid
field obtained in
step 2
. We will pass the
FIELD_NAME
of the field obtained in
step 1
as the field identifier.
JS
PHP
BX24
.
callMethod
(
'crm.deal.update'
,
{
id
:
6917
,
fields
: {
UF_CRM_1723209318
:
"2025-04-29T13:03:20+02:00"
,
},
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
'crm.deal.update'
,
[
'id'
=>
6917
,
'fields'
=> [
'UF_CRM_1723209318'
=>
'2025-04-29T13:03:20+02:00'
]
]
);
As a result, we will receive
true
, indicating that the deal has been successfully updated. If you received an
error
in the result, refer to the documentation for the method
crm.deal.update
to understand possible errors.
{
"result"
:
true
,
}
Checking the Value of the Deal Field
Checking the Value of the Deal Field
The received result does not contain information about the deal fields. To check if the payment date field has been successfully updated, we will execute the method
crm.deal.get
with the parameters:
id
—
ID
of the deal, required parameter
JS
PHP
BX24
.
callMethod
(
'crm.deal.get'
,
{
id
:
6917
,
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
'crm.deal.get'
,
[
'id'
=>
6917
]
);
As a result, we will get the values of all deal fields, including custom fields. The value of the "Payment Date" field
UF_CRM_1723209318
:
2025-04-29T03:00:00+02:00
has been successfully set.
{
"result"
:
{
"ID"
:
"6917"
,
"TITLE"
:
"Deal #6531"
,
"TYPE_ID"
:
"SALE"
,
"STAGE_ID"
:
"C9:NEW"
,
"PROBABILITY"
:
"0"
,
"CURRENCY_ID"
:
"EUR"
,
"OPPORTUNITY"
:
"30.00"
,
"IS_MANUAL_OPPORTUNITY"
:
"N"
,
"TAX_VALUE"
:
"0.00"
,
"LEAD_ID"
:
null
,
"COMPANY_ID"
:
"0"
,
"CONTACT_ID"
:
"275"
,
"QUOTE_ID"
:
null
,
"BEGINDATE"
:
"2024-08-20T03:00:00+02:00"
,
"CLOSEDATE"
:
"2024-08-27T03:00:00+02:00"
,
"ASSIGNED_BY_ID"
:
"1"
,
"CREATED_BY_ID"
:
"1"
,
"MODIFY_BY_ID"
:
"1"
,
"DATE_CREATE"
:
"2025-04-29T00:03:19+02:00"
,
"DATE_MODIFY"
:
"2025-05-05T10:17:08+02:00"
,
"OPENED"
:
"Y"
,
"CLOSED"
:
"N"
,
"COMMENTS"
:
""
,
"ADDITIONAL_INFO"
:
null
,
"LOCATION_ID"
:
null
,
"CATEGORY_ID"
:
"9"
,
"STAGE_SEMANTIC_ID"
:
"P"
,
"IS_NEW"
:
"Y"
,
"IS_RECURRING"
:
"N"
,
"IS_RETURN_CUSTOMER"
:
"Y"
,
"IS_REPEATED_APPROACH"
:
"N"
,
"SOURCE_ID"
:
""
,
"SOURCE_DESCRIPTION"
:
""
,
"ORIGINATOR_ID"
:
null
,
"ORIGIN_ID"
:
null
,
"MOVED_BY_ID"
:
"0"
,
"MOVED_TIME"
:
"2025-04-29T00:03:19+02:00"
,
"LAST_ACTIVITY_TIME"
:
"2025-04-29T13:03:21+02:00"
,
"UTM_SOURCE"
:
null
,
"UTM_MEDIUM"
:
null
,
"UTM_CAMPAIGN"
:
null
,
"UTM_CONTENT"
:
null
,
"UTM_TERM"
:
null
,
"PARENT_ID_156"
:
null
,
"PARENT_ID_177"
:
null
,
"LAST_COMMUNICATION_TIME"
:
null
,
"LAST_ACTIVITY_BY"
:
"1"
,
"UF_CRM_66976FE3B2425"
:
[
]
,
"UF_CRM_1723206732"
:
""
,
"UF_CRM_1723206709"
:
""
,
"UF_CRM_1740471712"
:
""
,
"UF_CRM_1723209318"
:
"2025-04-29T03:00:00+02:00"
,
"UF_CRM_1722577765"
:
""
,
"UF_CRM_1723188121"
:
""
}
,
}
Code Example
Code Example
JS
PHP
// Step 1: Get FIELD_NAME for the field with EDIT_FORM_LABEL "Payment Date"
BX24
.
callMethod
(
'crm.deal.userfield.list'
,
{
filter
: {
LANG
:
'de'
,
USER_TYPE_ID
:
'date'
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
(result.
error
());
}
else
{
const
fields = result.
data
();
const
dateField = fields.
find
(
field
=>
field.
EDIT_FORM_LABEL
===
"Payment Date"
);
if
(dateField) {
const
fieldName = dateField.
FIELD_NAME
;
console
.
log
(
"FIELD_NAME for 'Payment Date':"
, fieldName);
// Step 2: Request deal ID from the user and get the payment date
const
dealId =
prompt
(
"Enter the deal ID:"
);
BX24
.
callMethod
(
'crm.item.payment.list'
,
{
entityId
: dealId,
entityTypeId
:
2
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
(result.
error
());
}
else
{
const
payments = result.
data
();
if
(payments.
length
>
0
) {
const
datePaid = payments[
0
].
datePaid
;
console
.
log
(
"Payment Date:"
, datePaid);
// Step 3: Update the deal
BX24
.
callMethod
(
'crm.deal.update'
,
{
id
: dealId,
fields
: {
[fieldName]: datePaid
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
(result.
error
());
}
else
{
console
.
log
(
"Deal successfully updated"
);
}
}
);
}
}
}
);
}
}
}
);
require_once
(
'crest.php'
);
// Step 1: Get FIELD_NAME for the field with EDIT_FORM_LABEL "Payment Date"
$result
=
CRest
::
call
(
'crm.deal.userfield.list'
,
[
'filter'
=> [
'LANG'
=>
'de'
,
'USER_TYPE_ID'
=>
'date'
]
]
);
if
(!
empty
(
$result
[
'error'
])) {
echo
"Error: "
.
$result
[
'error_description'
];
}
else
{
$fields
=
$result
[
'result'
];
$dateField
=
null
;
foreach
(
$fields
as
$field
) {
if
(
$field
[
'EDIT_FORM_LABEL'
] ===
"Payment Date"
) {
$dateField
=
$field
;
break
;
}
}
if
(
$dateField
) {
$fieldName
=
$dateField
[
'FIELD_NAME'
];
echo
"FIELD_NAME for 'Payment Date': "
.
$fieldName
.
"\n"
;
// Step 2: Request deal ID from the user and get the payment date
$dealId
=
readline
(
"Enter the deal ID: "
);
$paymentResult
=
CRest
::
call
(
'crm.item.payment.list'
,
[
'entityId'
=>
$dealId
,
'entityTypeId'
=>
2
]
);
if
(!
empty
(
$paymentResult
[
'error'
])) {
echo
"Error: "
.
$paymentResult
[
'error_description'
];
}
else
{
$payments
=
$paymentResult
[
'result'
];
if
(
count
(
$payments
) >
0
) {
$datePaid
=
$payments
[
0
][
'datePaid'
];
echo
"Payment Date: "
.
$datePaid
.
"\n"
;
// Step 3: Update the deal
$updateResult
=
CRest
::
call
(
'crm.deal.update'
,
[
'id'
=>
$dealId
,
'fields'
=> [
$fieldName
=>
$datePaid
]
]
);
if
(!
empty
(
$updateResult
[
'error'
])) {
echo
"Error: "
.
$updateResult
[
'error_description'
];
}
else
{
echo
"Deal successfully updated\n"
;
}
}
}
}
}
Copied
Was the article helpful?
Yes
No
Previous
How to Move an Activity from One Object Type to Another
Next
How to Get Lists

---

