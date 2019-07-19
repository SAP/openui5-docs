<!-- loio831039835e7c4da3a8a0b49567573afe -->

| loio |
| -----|
| 831039835e7c4da3a8a0b49567573afe |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/831039835e7c4da3a8a0b49567573afe) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/831039835e7c4da3a8a0b49567573afe)</div>

## Annotations in Translation Files

All strings for translation have to be annotated to provide more context for translation. An annotation consists of an "X/Y" text type classification, an optional length restriction, and a freetext explanation how the string is used on the UI.

The following comment types exist:

``` prefs

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

    > Note:
    > Use only the Y text types specified in the table below. More Y text types exist but must not be used.
    > 
    > 

-   `NOTR` is used for strings that are not relevant for translation


X Text Types<a name="loio831039835e7c4da3a8a0b49567573afe__table_wht_wmp_np"/>

|Text type|Related S2X type|Description|
|---------|----------------|-----------|
|`XACT`|accessibility|Accessibility|
|`XALT`|alternativetext|Alternative text|
|`XBCB`|breadcrumbstep|Breadcrumb step|
|`XBLI`|listitem|Bullet list item text|
|`XBUT`|button|Button text|
|`XCAP`|caption|Caption|
|`XCEL`|cell|Cell|
|`XCKL`|checkbox|Checkbox|
|`XCOL`|tableColumnHeading|Column header|
|`XCRD`|tabStrip|Tabstrip|
|`XDAT`|datanavigationtext|Data navigation text|
|`XFLD`|label|Label|
|`XFRM`|frame|Frame|
|`XGLS`|term|Term|
|`XGRP`|grouptitle|Group title|
|`XHED`|heading|Heading|
|`XLGD`|legendtext|Legend text|
|`XLNK`|hyperlink|Hyperlink text|
|`XLOG`|logentry|Log entry|
|`XLST`|listbox|List box item|
|`XMEN`|menu|Menu header|
|`XMIT`|menuitem|Menu item|
|`XMSG`|messagetext|Message text|
|`XRBL`|radio|Radio button|
|`XRMP`|roadMapStep|Roadmap step|
|`XROW`|tableRowHeading|Table row heading|
|`XSEL`|selectiontext|Selection text|
|`XTBS`|tab|Tab strip text|
|`XTIT`|tableTitle|Table title|
|`XTND`|treeNode|Tree node text|
|`XTOL`|quickInfo|Quick info text|
|`XTXT`|generaltext|General text|

Y Text Types<a name="loio831039835e7c4da3a8a0b49567573afe__table_fmz_fnp_np"/>

|Text type|Related S2X type|Description|
|---------|----------------|-----------|
|`YACT`|accessibilitylong|Accessibility \(long\)|
|`YBLI`|list|Bullet list item text|
|`YDEF`|definition|Definition|
|`YDES`|description|Description|
|`YEXP`|explanation|Explanation|
|`YFAA`|faqa|FAQ answer|
|`YFAQ`|faq|FAQ|
|`YGLS`|glossarydefinition|Glossary definition|
|`YINF`|informationtextlong|Information|
|`YINS`|instruction|Instruction|
|`YLOG`|logEntrylong|Log entry|
|`YMSE`|errorMessage|Error message|
|`YMSG`|messagetextlong|Message text \(long\)|
|`YMSI`|informationMessage|Information message long|
|`YMSW`|warningMessage|Warning message|
|`YTEC`|technicaltextlong|Technical text|
|`YTIC`|ticker|Ticker / Marquee|
|`YTXT`|generaltextlong|General text long|

***

### Properties File

``` prefs

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

