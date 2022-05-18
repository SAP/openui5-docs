<!-- loio831039835e7c4da3a8a0b49567573afe -->

| loio |
| -----|
| 831039835e7c4da3a8a0b49567573afe |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/831039835e7c4da3a8a0b49567573afe) | [demo kit latest release](https://sdk.openui5.org/topic/831039835e7c4da3a8a0b49567573afe)</div>

## Annotations in Translation Files

All strings for translation have to be annotated to provide more context for translation. An annotation consists of an "X/Y" text type classification, an optional length restriction, and a freetext explanation how the string is used on the UI.

The following comment types exist:

```ini

#<SAP-Text-Type>
#<SAP-Text-Type>:<Note for translator>
#<SAP-Text-Type>,<Length-Restriction>
#<SAP-Text-Type>,<Length-Restriction>:<Note for translator>
```

***

### Text Classification

The following text type classifications exist:

-   X texts are used for all texts with less than 120 characters \(short texts\)

-   Y texts are used for texts with more than 120 characters

    > ### Note:  
    > Use only the Y text types specified in the table below. More Y text types exist but must not be used.

-   `NOTR` is used for strings that are not relevant for translation


<a name="loio831039835e7c4da3a8a0b49567573afe__table_wht_wmp_np"/>X Text Types


<table>
<tr>
<th valign="top">

Text type



</th>
<th valign="top">

Related S2X type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`XACT`



</td>
<td valign="top">

accessibility



</td>
<td valign="top">

Accessibility



</td>
</tr>
<tr>
<td valign="top">

`XALT`



</td>
<td valign="top">

alternativetext



</td>
<td valign="top">

Alternative text



</td>
</tr>
<tr>
<td valign="top">

`XBCB`



</td>
<td valign="top">

breadcrumbstep



</td>
<td valign="top">

Breadcrumb step



</td>
</tr>
<tr>
<td valign="top">

`XBLI`



</td>
<td valign="top">

listitem



</td>
<td valign="top">

Bullet list item text



</td>
</tr>
<tr>
<td valign="top">

`XBUT`



</td>
<td valign="top">

button



</td>
<td valign="top">

Button text



</td>
</tr>
<tr>
<td valign="top">

`XCAP`



</td>
<td valign="top">

caption



</td>
<td valign="top">

Caption



</td>
</tr>
<tr>
<td valign="top">

`XCEL`



</td>
<td valign="top">

cell



</td>
<td valign="top">

Cell



</td>
</tr>
<tr>
<td valign="top">

`XCKL`



</td>
<td valign="top">

checkbox



</td>
<td valign="top">

Checkbox



</td>
</tr>
<tr>
<td valign="top">

`XCOL`



</td>
<td valign="top">

tableColumnHeading



</td>
<td valign="top">

Column header



</td>
</tr>
<tr>
<td valign="top">

`XCRD`



</td>
<td valign="top">

tabStrip



</td>
<td valign="top">

Tabstrip



</td>
</tr>
<tr>
<td valign="top">

`XDAT`



</td>
<td valign="top">

datanavigationtext



</td>
<td valign="top">

Data navigation text



</td>
</tr>
<tr>
<td valign="top">

`XFLD`



</td>
<td valign="top">

label



</td>
<td valign="top">

Label



</td>
</tr>
<tr>
<td valign="top">

`XFRM`



</td>
<td valign="top">

frame



</td>
<td valign="top">

Frame



</td>
</tr>
<tr>
<td valign="top">

`XGLS`



</td>
<td valign="top">

term



</td>
<td valign="top">

Term



</td>
</tr>
<tr>
<td valign="top">

`XGRP`



</td>
<td valign="top">

grouptitle



</td>
<td valign="top">

Group title



</td>
</tr>
<tr>
<td valign="top">

`XHED`



</td>
<td valign="top">

heading



</td>
<td valign="top">

Heading



</td>
</tr>
<tr>
<td valign="top">

`XLGD`



</td>
<td valign="top">

legendtext



</td>
<td valign="top">

Legend text



</td>
</tr>
<tr>
<td valign="top">

`XLNK`



</td>
<td valign="top">

hyperlink



</td>
<td valign="top">

Hyperlink text



</td>
</tr>
<tr>
<td valign="top">

`XLOG`



</td>
<td valign="top">

logentry



</td>
<td valign="top">

Log entry



</td>
</tr>
<tr>
<td valign="top">

`XLST`



</td>
<td valign="top">

listbox



</td>
<td valign="top">

List box item



</td>
</tr>
<tr>
<td valign="top">

`XMEN`



</td>
<td valign="top">

menu



</td>
<td valign="top">

Menu header



</td>
</tr>
<tr>
<td valign="top">

`XMIT`



</td>
<td valign="top">

menuitem



</td>
<td valign="top">

Menu item



</td>
</tr>
<tr>
<td valign="top">

`XMSG`



</td>
<td valign="top">

messagetext



</td>
<td valign="top">

Message text



</td>
</tr>
<tr>
<td valign="top">

`XRBL`



</td>
<td valign="top">

radio



</td>
<td valign="top">

Radio button



</td>
</tr>
<tr>
<td valign="top">

`XRMP`



</td>
<td valign="top">

roadMapStep



</td>
<td valign="top">

Roadmap step



</td>
</tr>
<tr>
<td valign="top">

`XROW`



</td>
<td valign="top">

tableRowHeading



</td>
<td valign="top">

Table row heading



</td>
</tr>
<tr>
<td valign="top">

`XSEL`



</td>
<td valign="top">

selectiontext



</td>
<td valign="top">

Selection text



</td>
</tr>
<tr>
<td valign="top">

`XTBS`



</td>
<td valign="top">

tab



</td>
<td valign="top">

Tab strip text



</td>
</tr>
<tr>
<td valign="top">

`XTIT`



</td>
<td valign="top">

tableTitle



</td>
<td valign="top">

Table title



</td>
</tr>
<tr>
<td valign="top">

`XTND`



</td>
<td valign="top">

treeNode



</td>
<td valign="top">

Tree node text



</td>
</tr>
<tr>
<td valign="top">

`XTOL`



</td>
<td valign="top">

quickInfo



</td>
<td valign="top">

Quick info text



</td>
</tr>
<tr>
<td valign="top">

`XTXT`



</td>
<td valign="top">

generaltext



</td>
<td valign="top">

General text



</td>
</tr>
</table>

<a name="loio831039835e7c4da3a8a0b49567573afe__table_fmz_fnp_np"/>Y Text Types


<table>
<tr>
<th valign="top">

Text type



</th>
<th valign="top">

Related S2X type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`YACT`



</td>
<td valign="top">

accessibilitylong



</td>
<td valign="top">

Accessibility \(long\)



</td>
</tr>
<tr>
<td valign="top">

`YBLI`



</td>
<td valign="top">

list



</td>
<td valign="top">

Bullet list item text



</td>
</tr>
<tr>
<td valign="top">

`YDEF`



</td>
<td valign="top">

definition



</td>
<td valign="top">

Definition



</td>
</tr>
<tr>
<td valign="top">

`YDES`



</td>
<td valign="top">

description



</td>
<td valign="top">

Description



</td>
</tr>
<tr>
<td valign="top">

`YEXP`



</td>
<td valign="top">

explanation



</td>
<td valign="top">

Explanation



</td>
</tr>
<tr>
<td valign="top">

`YFAA`



</td>
<td valign="top">

faqa



</td>
<td valign="top">

FAQ answer



</td>
</tr>
<tr>
<td valign="top">

`YFAQ`



</td>
<td valign="top">

faq



</td>
<td valign="top">

FAQ



</td>
</tr>
<tr>
<td valign="top">

`YGLS`



</td>
<td valign="top">

glossarydefinition



</td>
<td valign="top">

Glossary definition



</td>
</tr>
<tr>
<td valign="top">

`YINF`



</td>
<td valign="top">

informationtextlong



</td>
<td valign="top">

Information



</td>
</tr>
<tr>
<td valign="top">

`YINS`



</td>
<td valign="top">

instruction



</td>
<td valign="top">

Instruction



</td>
</tr>
<tr>
<td valign="top">

`YLOG`



</td>
<td valign="top">

logEntrylong



</td>
<td valign="top">

Log entry



</td>
</tr>
<tr>
<td valign="top">

`YMSE`



</td>
<td valign="top">

errorMessage



</td>
<td valign="top">

Error message



</td>
</tr>
<tr>
<td valign="top">

`YMSG`



</td>
<td valign="top">

messagetextlong



</td>
<td valign="top">

Message text \(long\)



</td>
</tr>
<tr>
<td valign="top">

`YMSI`



</td>
<td valign="top">

informationMessage



</td>
<td valign="top">

Information message long



</td>
</tr>
<tr>
<td valign="top">

`YMSW`



</td>
<td valign="top">

warningMessage



</td>
<td valign="top">

Warning message



</td>
</tr>
<tr>
<td valign="top">

`YTEC`



</td>
<td valign="top">

technicaltextlong



</td>
<td valign="top">

Technical text



</td>
</tr>
<tr>
<td valign="top">

`YTIC`



</td>
<td valign="top">

ticker



</td>
<td valign="top">

Ticker / Marquee



</td>
</tr>
<tr>
<td valign="top">

`YTXT`



</td>
<td valign="top">

generaltextlong



</td>
<td valign="top">

General text long



</td>
</tr>
</table>

***

### Properties File

```ini

#XMSG: a random text used for demonstration purposes, the meaning is not related to any other content in the UI
HelloWorld=Hello world!

#XBUT,10
OK=OK

#XBUT,15
Cancel=Cancel

#XMSG: The user has just triggered an action which cannot be executed
Unauthorized=User {0} is not authorized to execute command {1}

#XMSG
Multiline=Line 1\nLine 2

#XFLD: The money you get back at shop's checkout-counter
Change=Change
```

