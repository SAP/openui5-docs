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

    > ### Note:  
    > Use only the Y text types specified in the table below. More Y text types exist but must not be used.

-   `NOTR` is used for strings that are not relevant for translation


<a name="loio831039835e7c4da3a8a0b49567573afe__table_wht_wmp_np"/>X Text Types

|Text type

|Related S2X type

|Description

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>-----------</th>
			<th>------------------</th>
			<th>-------------</th>
		</tr>
	</thead>
	<tbody>

			<td>accessibility
			</td>
			<td>Accessibility
			</td>
		</tr>
		<tr>
			<td>`XALT`
			</td>
			<td>alternativetext
			</td>
			<td>Alternative text
			</td>
		</tr>
		<tr>
			<td>`XBCB`
			</td>
			<td>breadcrumbstep
			</td>
			<td>Breadcrumb step
			</td>
		</tr>
		<tr>
			<td>`XBLI`
			</td>
			<td>listitem
			</td>
			<td>Bullet list item text
			</td>
		</tr>
		<tr>
			<td>`XBUT`
			</td>
			<td>button
			</td>
			<td>Button text
			</td>
		</tr>
		<tr>
			<td>`XCAP`
			</td>
			<td>caption
			</td>
			<td>Caption
			</td>
		</tr>
		<tr>
			<td>`XCEL`
			</td>
			<td>cell
			</td>
			<td>Cell
			</td>
		</tr>
		<tr>
			<td>`XCKL`
			</td>
			<td>checkbox
			</td>
			<td>Checkbox
			</td>
		</tr>
		<tr>
			<td>`XCOL`
			</td>
			<td>tableColumnHeading
			</td>
			<td>Column header
			</td>
		</tr>
		<tr>
			<td>`XCRD`
			</td>
			<td>tabStrip
			</td>
			<td>Tabstrip
			</td>
		</tr>
		<tr>
			<td>`XDAT`
			</td>
			<td>datanavigationtext
			</td>
			<td>Data navigation text
			</td>
		</tr>
		<tr>
			<td>`XFLD`
			</td>
			<td>label
			</td>
			<td>Label
			</td>
		</tr>
		<tr>
			<td>`XFRM`
			</td>
			<td>frame
			</td>
			<td>Frame
			</td>
		</tr>
		<tr>
			<td>`XGLS`
			</td>
			<td>term
			</td>
			<td>Term
			</td>
		</tr>
		<tr>
			<td>`XGRP`
			</td>
			<td>grouptitle
			</td>
			<td>Group title
			</td>
		</tr>
		<tr>
			<td>`XHED`
			</td>
			<td>heading
			</td>
			<td>Heading
			</td>
		</tr>
		<tr>
			<td>`XLGD`
			</td>
			<td>legendtext
			</td>
			<td>Legend text
			</td>
		</tr>
		<tr>
			<td>`XLNK`
			</td>
			<td>hyperlink
			</td>
			<td>Hyperlink text
			</td>
		</tr>
		<tr>
			<td>`XLOG`
			</td>
			<td>logentry
			</td>
			<td>Log entry
			</td>
		</tr>
		<tr>
			<td>`XLST`
			</td>
			<td>listbox
			</td>
			<td>List box item
			</td>
		</tr>
		<tr>
			<td>`XMEN`
			</td>
			<td>menu
			</td>
			<td>Menu header
			</td>
		</tr>
		<tr>
			<td>`XMIT`
			</td>
			<td>menuitem
			</td>
			<td>Menu item
			</td>
		</tr>
		<tr>
			<td>`XMSG`
			</td>
			<td>messagetext
			</td>
			<td>Message text
			</td>
		</tr>
		<tr>
			<td>`XRBL`
			</td>
			<td>radio
			</td>
			<td>Radio button
			</td>
		</tr>
		<tr>
			<td>`XRMP`
			</td>
			<td>roadMapStep
			</td>
			<td>Roadmap step
			</td>
		</tr>
		<tr>
			<td>`XROW`
			</td>
			<td>tableRowHeading
			</td>
			<td>Table row heading
			</td>
		</tr>
		<tr>
			<td>`XSEL`
			</td>
			<td>selectiontext
			</td>
			<td>Selection text
			</td>
		</tr>
		<tr>
			<td>`XTBS`
			</td>
			<td>tab
			</td>
			<td>Tab strip text
			</td>
		</tr>
		<tr>
			<td>`XTIT`
			</td>
			<td>tableTitle
			</td>
			<td>Table title
			</td>
		</tr>
		<tr>
			<td>`XTND`
			</td>
			<td>treeNode
			</td>
			<td>Tree node text
			</td>
		</tr>
		<tr>
			<td>`XTOL`
			</td>
			<td>quickInfo
			</td>
			<td>Quick info text
			</td>
		</tr>
		<tr>
			<td>`XTXT`
			</td>
			<td>generaltext
			</td>
			<td>General text
			</td>
		</tr>
	</tbody>
</table>

<a name="loio831039835e7c4da3a8a0b49567573afe__table_fmz_fnp_np"/>Y Text Types

|Text type

|Related S2X type

|Description

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>-----------</th>
			<th>------------------</th>
			<th>-------------</th>
		</tr>
	</thead>
	<tbody>

			<td>accessibilitylong
			</td>
			<td>Accessibility \(long\)
			</td>
		</tr>
		<tr>
			<td>`YBLI`
			</td>
			<td>list
			</td>
			<td>Bullet list item text
			</td>
		</tr>
		<tr>
			<td>`YDEF`
			</td>
			<td>definition
			</td>
			<td>Definition
			</td>
		</tr>
		<tr>
			<td>`YDES`
			</td>
			<td>description
			</td>
			<td>Description
			</td>
		</tr>
		<tr>
			<td>`YEXP`
			</td>
			<td>explanation
			</td>
			<td>Explanation
			</td>
		</tr>
		<tr>
			<td>`YFAA`
			</td>
			<td>faqa
			</td>
			<td>FAQ answer
			</td>
		</tr>
		<tr>
			<td>`YFAQ`
			</td>
			<td>faq
			</td>
			<td>FAQ
			</td>
		</tr>
		<tr>
			<td>`YGLS`
			</td>
			<td>glossarydefinition
			</td>
			<td>Glossary definition
			</td>
		</tr>
		<tr>
			<td>`YINF`
			</td>
			<td>informationtextlong
			</td>
			<td>Information
			</td>
		</tr>
		<tr>
			<td>`YINS`
			</td>
			<td>instruction
			</td>
			<td>Instruction
			</td>
		</tr>
		<tr>
			<td>`YLOG`
			</td>
			<td>logEntrylong
			</td>
			<td>Log entry
			</td>
		</tr>
		<tr>
			<td>`YMSE`
			</td>
			<td>errorMessage
			</td>
			<td>Error message
			</td>
		</tr>
		<tr>
			<td>`YMSG`
			</td>
			<td>messagetextlong
			</td>
			<td>Message text \(long\)
			</td>
		</tr>
		<tr>
			<td>`YMSI`
			</td>
			<td>informationMessage
			</td>
			<td>Information message long
			</td>
		</tr>
		<tr>
			<td>`YMSW`
			</td>
			<td>warningMessage
			</td>
			<td>Warning message
			</td>
		</tr>
		<tr>
			<td>`YTEC`
			</td>
			<td>technicaltextlong
			</td>
			<td>Technical text
			</td>
		</tr>
		<tr>
			<td>`YTIC`
			</td>
			<td>ticker
			</td>
			<td>Ticker / Marquee
			</td>
		</tr>
		<tr>
			<td>`YTXT`
			</td>
			<td>generaltextlong
			</td>
			<td>General text long
			</td>
		</tr>
	</tbody>
</table>

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

