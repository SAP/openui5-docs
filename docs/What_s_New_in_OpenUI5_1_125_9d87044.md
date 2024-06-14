<!-- loio9d87044050f44763a2aeabff0a7a6bb2 -->

| loio |
| -----|
| 9d87044050f44763a2aeabff0a7a6bb2 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/9d87044050f44763a2aeabff0a7a6bb2) | [demo kit latest release](https://sdk.openui5.org/topic/9d87044050f44763a2aeabff0a7a6bb2)</div>

## What's New in OpenUI5 1.125

With this release OpenUI5 is upgraded from version 1.124 to 1.125.

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

1.125 

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

**`sap.ui.mdc.Table`**

In the table in the `View Settings` dialog \(`P13n`\), you can now use the `Select All` option to select all columns at once to make them visible. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.mdc.Table/sample/sap.ui.mdc.demokit.sample.TableJson).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.filterbar.vh.FilterBar`, `sap.ui.mdc.filterbar.vh.CollectiveSearchSelect`** 

</td>
<td valign="top">

**`sap.ui.mdc.filterbar.vh.FilterBar`, `sap.ui.mdc.filterbar.vh.CollectiveSearchSelect`**

To make it easier to find value-help-related entities, we have moved these controls to the `sap.ui.mdc.valuehelp` namespace.

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable` ** 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable` **

To enable automatic resizing of columns, we have introduced the `autoResizeColumn` function. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.Column%23methods/getAutoResizable).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.m.p13n.Engine` ** 

</td>
<td valign="top">

**`sap.m.p13n.Engine`**

We have added a tutorial that allows you to build and try out your own artifacts based on the controls in the <code><code>P13n</code></code> class. For more information, see the [P13nify Everything - Personalization for Any Control](https://github.com/SAP-samples/ui5-p13n-tutorial).



<sub>Changed•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.ui.mdc` library** 

</td>
<td valign="top">

**`sap.ui.mdc` library**

We have added a tutorial that allows you to build and try out your own artifacts based on the controls in the `sap.ui.mdc` library. For more information, see the [OpenUI5 MDC Tutorial](https://github.com/SAP-samples/ui5-mdc-json-tutorial).

<sub>Changed•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

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

**`sap.ui.mdc.Table`, `sap.ui.mdc.table.DragDropConfig`**

-   We have enhanced the `DropInfo` configuration: You can now use `preventDefault` for the `dragover` event. This way, you can disable dropping on a specific location, for example, between two table rows. To help consumers find out whether to prevent the default of the `dragenter` event when dragging over the edge of two DOM nodes, we have also added the `dropPosition` parameter to the event. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.dnd.DropInfo%23events/dragOver) for the `dragOver` event and the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.table.DragDropConfig%23events/Summary) for `DragDropConfig`. 

-   We have introduced the `browserEvent` parameter for all drag-and-drop-related events in `DragDropConfig` allowing consumers to access the `DataTransfer` object. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.table.DragDropConfig).


<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 Resource Model** 

</td>
<td valign="top">

**OpenUI5 Resource Model**

We have deprecated the `async` parameter of the `sap.ui.model.resource.ResourceModel` API. A warning is now logged if the `async` parameter is not set to `true`.

<sub>Deprecated•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

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

The maintenance of recursive hierarchies is no longer experimental; you can now use it in productive applications. For more information, see [Recursive Hierarchy](Data_Aggregation_and_Recursive_Hierarchy_7d91431.md#loio7d914317c0b64c23824bf932cc8a4ae1__section_RCH).

<sub>Changed•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Icon Explorer** 

</td>
<td valign="top">

**Icon Explorer**

We have added the following new icons to the SAP Fiori Tools icon font:

-   business-application-studio
-   clone-from-git
-   business-accelerator

Find the icon that fits your needs using the [Icon Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/iconExplorer/webapp/index.html) tool. 

<sub>Changed•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Carousel`** 

</td>
<td valign="top">

**`sap.m.Carousel`**

You can now display the carousel’s page indicator over the content. To enable this behavior, we have created a new `sap.m.CarouselPageIndicatorPlacementType` enumeration, that replaces the old `sap.m.PlacementType`. The new enumeration has two additional values that you can use for this purpose - `OverContentTop` and `OverContentBottom`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Carousel) and the [Sample](https://sdk.openui5.org/entity/sap.m.Carousel/sample/sap.m.sample.CarouselWithDisplayOptions).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`** 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`**

Using the new `noData` aggregation, you can now set the control to display an illustrated message when there is no data available. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

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

-   To enhance the accessibility of the control, we have enabled screen readers to announce information about the number of appointments hidden in the *More* button, along with the corresponding date of these appointments.
-   We have added a new `sourceLink` property to the `moreLinkPress` event. The new property enables developers to identify the exact *More* button that has been pressed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`** 

</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   You can now set the card to display a custom image loaded from the extension, rather than the default illustrated message. For more information, see the [Custom Image Message](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/customImage) sample in the Card Explorer.
-   The rendered card now has a `data-help-id` attribute set on its root element. This `data-help-id` is useful when you want to connect the card with a help system for the end user, for example SAP Companion. For more information, see the [Help ID](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/helpId) section in the Card Explorer.

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
</table>

