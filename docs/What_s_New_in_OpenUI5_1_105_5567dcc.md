<!-- loio5567dccb287b4dd9aa755a76cf25ae41 -->

| loio |
| -----|
| 5567dccb287b4dd9aa755a76cf25ae41 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/5567dccb287b4dd9aa755a76cf25ae41) | [demo kit latest release](https://sdk.openui5.org/topic/5567dccb287b4dd9aa755a76cf25ae41)</div>

## What's New in OpenUI5 1.105

With this release OpenUI5 is upgraded from version 1.104 to 1.105.

***

<a name="loio5567dccb287b4dd9aa755a76cf25ae41__section_st2_dgs_h5b"/>

### Preview and Announcements

The following information concerns important upcoming changes. UI changes may have an impact on the user experience and may require test cases to be adapted.


<table>
<tr>
<th valign="top">

Type



</th>
<th valign="top">

Description



</th>
<th valign="top">

Available as of OpenUI5 Version



</th>
</tr>
<tr>
<td valign="top">

Announcement



</td>
<td valign="top">

**Reminder: Outdated OpenUI5 Versions to Be Removed from the CDN**

For security reasons, OpenUI5 versions that are no longer maintained will be removed from the UI5 content delivery network \(CDN\) one year after their end of maintenance. If a version is still in maintenance, patches of that version that are older than one year will also be removed. We have noted that a number of customers are still using such outdated versions or patches. If this affects you, please note that once these versions or patches are removed, your applications will break. Please update to a more recent version or patch. For more information, see: [Removing Outdated UI5 Versions from UI5 CDN](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/) as well as the UI5 notifications in the Demo Kit.



</td>
<td valign="top">

n/a



</td>
</tr>
<tr>
<td valign="top">

UI Change



</td>
<td valign="top">

**Stricter Validation of Decimal and Grouping Separators**

If a user added grouping separators when entering a number, the parsing logic ignored them. This could result in an unwanted number if the user confused grouping separators and decimal separators. Since OpenUI5 1.99, the grouping separators are checked against the current locale to largely prevent that the user confuses these types of separators.



</td>
<td valign="top">

1.99



</td>
</tr>
</table>

***

<a name="loio5567dccb287b4dd9aa755a76cf25ae41__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

We have started to work on supporting recursive hierarchies and deferred deletion. Both features are work in progress. As of now, they are flagged as experimental and must not be used for productive applications. For more information, see [Recursive Hierarchy](Extension_for_Data_Aggregation_7d91431.md#loio7d914317c0b64c23824bf932cc8a4ae1__section_RCH) and [Deleting an Entity](Deleting_an_Entity_2613ebc.md).



</td>
</tr>
</table>

***

<a name="loio5567dccb287b4dd9aa755a76cf25ae41__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.Dialog`**

We have enabled a new keyboard shortcut for `sap.m.Dialog` with a footer button of type *Accept* or *Emphasized*. Buttons can be triggered by pressing  [Ctrl\] + [Enter\]  for Windows and  [Ctrl\] + [Enter\] / [Cmd\] + [Enter\]  for Mac OS. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Dialog/sample/sap.m.sample.Dialog). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.IllustratedMessage`**

We have enabled vertical responsiveness for the control. The `sap.m.IllustratedMessage` is adjusted automatically, depending also on the available height. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IllustratedMessage). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.List`**

-   To improve accessibility, we have replaced the existing ARIA roles. The following new default roles are available:

    -   `role=list` for lists

    -   `role=listitem` for list items


-   We have also improved the accessibility for the group headers of grouped lists by, for example, adding the ARIA role `role=group`.




</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

We have introduced the `tooltip` property, which is used to provide more information to the user about what will happen after they click the link and the action is executed. It can be used by `ObjectGroupItems` of type `Default` with actions – for example, link, email, or phone. For more information, see the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/object) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object) in the Card Explorer.



</td>
</tr>
</table>

***

<a name="loio5567dccb287b4dd9aa755a76cf25ae41__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated). 



</td>
</tr>
</table>

