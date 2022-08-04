<!-- loio5567dccb287b4dd9aa755a76cf25ae41 -->

| loio |
| -----|
| 5567dccb287b4dd9aa755a76cf25ae41 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/5567dccb287b4dd9aa755a76cf25ae41) | [demo kit latest release](https://sdk.openui5.org/topic/5567dccb287b4dd9aa755a76cf25ae41)</div>

## What's New in OpenUI5 1.105

With this release OpenUI5 is upgraded from version 1.104 to 1.105.

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

