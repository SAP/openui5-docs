<!-- loio3eecbdea5f644f0898079d7e24da9d18 -->

| loio |
| -----|
| 3eecbdea5f644f0898079d7e24da9d18 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/3eecbdea5f644f0898079d7e24da9d18) | [demo kit latest release](https://sdk.openui5.org/topic/3eecbdea5f644f0898079d7e24da9d18)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.118

With this release OpenUI5 is upgraded from version 1.117 to 1.118.

> ### Note:  
> Content marked as <span style="color:#666666;"><span class="SAP-icons"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/docs/whats-new-disclaimer).

****


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

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.DynamicDateRange`** 



</td>
<td valign="top">

**`sap.m.DynamicDateRange`**

With the new `addGroup` method, you can now easily create custom groups and custom-group headers for those groups. In addition, with the new `setGroupHeader` method, you can change the group header of a custom group. For more information, see the [DynamicDateRange API Reference](https://sdk.openui5.org/api/sap.m.DynamicDateRange/methods/addGroup), and the [DynamicDateRangeGroups enumeration](https://sdk.openui5.org/api/sap.m.DynamicDateRangeGroups).

<sub>Changed•Control•Info Only•1.118</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
<tr>
<td valign="top">

1.118 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`** 



</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`**

The control now displays the row-header images using size S avatars with a circle shape. The UX guidance is to use circle shapes for people \(default for the control\), and squares for other business images. You can easily change the shape using the new `iconShape` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar).

<sub>Changed•Control•Info Only•1.118</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
<tr>
<td valign="top">

1.118 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

User Documentation 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`** 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

We have added documentation and a sample that demonstrate how you can bundle all the necessary files needed for a Component card using the UI5 Tooling. With this card type, card developers can expose a whole UI5 Component as content for the card. For more information, see the [Component Preload](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/bundle/componentPreload) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/componentPreload) in the Card Explorer.

<sub>Changed•User Documentation•Info Only•1.118</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
<tr>
<td valign="top">

1.118 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**OpenUI5 OData V4 Model** 



</td>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   **Experimental:** You can now create and delete nodes in recursive hierarchies. Note that these experimental features must not be used in productive applications yet.

    For more information, see the API Reference for [`ODataListBinding#create`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding%23methods/create) and [`Context#delete`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/delete).

-   We now support the provision of a nested single entity in a transient entity.

    For more information, see *Nested Single Entity* in [Deep Create](Creating_an_Entity_c9723f8.md#loioc9723f8265f644af91c0ed941e114d46__section_DCR).


<sub>Changed•Feature•Info Only•1.118</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
<tr>
<td valign="top">

1.118 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.MessageToast`** 



</td>
<td valign="top">

**`sap.m.MessageToast`**

When a message toast opens, users can now move focus to the message using the following combination: [Ctrl/Command\] + [Shift\] + [M\] .

This allows them to keep the message on the screen for as long as they need.

<sub>Changed•Control•Info Only•1.118</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
<tr>
<td valign="top">

1.118 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.ui.mdc.Table`** 



</td>
<td valign="top">

**`sap.ui.mdc.Table` \(experimental\)**

You can now use the context menu also for this control. The `contextMenu` aggregation and related `beforeOpenContextMenu` event have been added to the table.

<sub>Changed•Control•Info Only•1.118</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
<tr>
<td valign="top">

1.118 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Sample for `sap.ui.mdc` library** 



</td>
<td valign="top">

**Sample for `sap.ui.mdc` library \(experimental\)**

You can now test the field and value help features of the \(experimental\) `sap.ui.mdc` library in a sample. To find the sample for this library in the Demo Kit, go to *Samples* and select MDC Overview. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.mdc/sample/sap.ui.mdc.demokit.sample.FieldValueHelpJson).

<sub>New•Feature•Info Only•1.118</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
<tr>
<td valign="top">

1.118 



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

We have deprecated the following entities for `sap.ui.table*`:

-   `grouped` property of `Column`

-   `enableGrouping` property

-   `groupBy` association

-   `group` event


We have introduced the `group` event in `AnalyticalTable` and the `grouped` property in `AnalyticalColumn`.

<sub>Deprecated•Feature•Info Only•1.118</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
<tr>
<td valign="top">

1.118 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Table`** 



</td>
<td valign="top">

**`sap.m.Table`, `sap.m.List`, `sap.m.Tree`**

To improve accessibility, we have completely reworked the screen reader support and keyboard handling of the `sap.m.Table` control. The row-based navigation stays the same, but cell-based navigation is now also possible, similar to the grid table. We have also improved other accessibility features of the table, for example, the *Delete* and *Edit* buttons for row actions have become accessible via keyboard. These features have not only been changed for the responsive table, but partly also for `sap.m.List`. Also, the ARIA role has been adapted. .

<sub>Changed•Control•Info Only•1.118</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-09-07



</td>
</tr>
</table>

