<!-- loioebd6f34797d846d1978e02b428d619c7 -->

| loio |
| -----|
| ebd6f34797d846d1978e02b428d619c7 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/ebd6f34797d846d1978e02b428d619c7) | [demo kit latest release](https://sdk.openui5.org/topic/ebd6f34797d846d1978e02b428d619c7)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.116

With this release OpenUI5 is upgraded from version 1.115 to 1.116.

> ### Note:  
> Content marked as <span style="color:#666666;"><span class="SAP-icons"></span></span>** [Preview](https://help.sap.com/docs/whats-new-disclaimer)** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/docs/whats-new-disclaimer).

** **


<table>
<tr>
<th valign="top">

Version



</th>
<th valign="top">

Type



</th>
<th valign="top">

Category



</th>
<th valign="top">

Title



</th>
<th valign="top">

Description



</th>
<th valign="top">

Action



</th>
<th valign="top">

Available as of



</th>
</tr>
<tr>
<td valign="top">

 1.118 



</td>
<td valign="top">

 Deprecated 



</td>
<td valign="top">

 Announcement 



</td>
<td valign="top">

 **`sap.ui.table` Controls: Discontinued Use of `sap.ui.commons` Library** 



</td>
<td valign="top">

**`sap.ui.table` Controls: Discontinued Use of `sap.ui.commons` Library**

We will discontinue the use of the deprecated `sap.ui.commons` library as of OpenUI5 version 1.118. If you use shortcuts for defining titles, footers, column headers, and cell templates in your `sap.ui.table` controls based on the related controls in the `sap.ui.commons` library, these will no longer work. Instead, the `sap.ui.table` controls will always depend on the related controls in the `sap.m` library after version 1.118.

**Recommended Action**: Check which libraries are used in your application. If you use `sap.ui.table` controls and their shortcuts in combination with the `sap.ui.commons` library, make sure to switch to the `sap.m` library.

For more information about how to prepare for this change, see [Change to the SAPUI5 sap.ui.table library](https://blogs.sap.com/2023/05/25/change-to-the-sapui5-sap.ui.table-library/).

<sub><span style="color:#666666;"><span class="SAP-icons"></span></span>** [Preview](https://help.sap.com/docs/whats-new-disclaimer)**•Deprecated•Announcement•Recommended•1.118</sub>



</td>
<td valign="top">

 Recommended 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
<tr>
<td valign="top">

 Upcoming 



</td>
<td valign="top">

 UI Changed 



</td>
<td valign="top">

 Announcement 



</td>
<td valign="top">

 **Improved Keyboard Handling and Screen Reader Support of `sap.m.Table`** 



</td>
<td valign="top">

**Improved Keyboard Handling and Screen Reader Support of `sap.m.Table`**

> ### Note:  
> The following information concerns important upcoming changes for end users. These changes may require end users to adjust and/or test cases to be adapted, but they won't stop or disrupt software or processes.

To improve accessibility, we will completely rework the screen reader and keyboard support of the `sap.m.Table` control in 1.117/1.118. The row-based navigation stays the same, but cell-based navigation will also be possible, similar to the grid table. We will also improve other accessibility features of the table, for example, the *Delete* and *Edit* buttons for row actions will become accessible via keyboard. These features will not only be changed for the responsive table, but partly also for `sap.m.List`. Also, the ARIA role will be adapted.

**Recommended Action**: Test cases might have to be adapted. Stay tuned .

.

<sub><span style="color:#666666;"><span class="SAP-icons"></span></span>** [Preview](https://help.sap.com/docs/whats-new-disclaimer)**•UI Changed•Announcement•Recommended•Upcoming</sub>



</td>
<td valign="top">

 Recommended 



</td>
<td valign="top">

9999-01-01



</td>
</tr>
<tr>
<td valign="top">

 1.116 



</td>
<td valign="top">

 Deprecated 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Deprecations** 



</td>
<td valign="top">

**Deprecations**

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.116</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-07-13



</td>
</tr>
<tr>
<td valign="top">

 1.116 



</td>
<td valign="top">

 New 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **TypeScript: Supported productively** 



</td>
<td valign="top">

**TypeScript: Supported productively**

TypeScript can now be used productively.

 For more information, see [TypeScript in OpenUI5](TypeScript_in_OpenUI5_a7ee961.md). 

<sub>New•Feature•Info Only•OpenUI5</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-07-13



</td>
</tr>
<tr>
<td valign="top">

 1.116 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Modern ECMAScript Support in OpenUI5** 



</td>
<td valign="top">

**Modern ECMAScript Support in OpenUI5**

We have enabled UI5 framework libraries to use modern ECMAScript syntax in their code and define Specification Version 3.0 in their UI5 Tooling configuration.

**Action:** If you use UI5 Tooling in your projects, upgrade to UI5 Tooling 3.0 and make sure that your project's development infrastructure fully supports this change.

For more information, see [Upgrade Your Tools for Modern ECMAScript in UI5](https://blogs.sap.com/2023/05/24/upgrade-your-tools-for-modern-ecmascript-in-ui5/).

<sub>Changed•Feature•Required•1.116</sub>



</td>
<td valign="top">

 Required 



</td>
<td valign="top">

2023-07-13



</td>
</tr>
</table>

