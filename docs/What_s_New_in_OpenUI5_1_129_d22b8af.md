<!-- loiod22b8af563784d8cbcff8afd3955734e -->

| loio |
| -----|
| d22b8af563784d8cbcff8afd3955734e |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/d22b8af563784d8cbcff8afd3955734e) | [demo kit latest release](https://sdk.openui5.org/topic/d22b8af563784d8cbcff8afd3955734e)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.129

With this release OpenUI5 is upgraded from version 1.128 to 1.129.

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

1.129 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Harmonized Context Menu in Key User Adaptation** 

</td>
<td valign="top">

**Harmonized Context Menu in Key User Adaptation**

The context menu is now consistent when you select elements. It no longer depends on how you select an element, such as using the left or right mouse button. The familiar right-click context menu now also appears when you left-click an element.

<sub>Changed•Feature•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**What's New Dialog in Key User Adaptation** 

</td>
<td valign="top">

**What's New Dialog in Key User Adaptation**

The *What's New* dialog keeps you informed about the latest updates, features, and improvements in key user adaptation.

After an upgrade, the dialog automatically shows the new features introduced with the new version. If you're interested in features from previous versions, you can find an overview in the <span class="SAP-icons-V5"></span> \(More Actions\) menu in the toolbar.

<sub>New•Feature•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

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

-   We have added the experimental `$$separate` binding parameter to `ODataListBinding`, which allows you to load properties with a longer loading time in a separate request. At the moment, only navigation properties can be specified in `$$separate`. Note that this parameter must not be used in productive applications yet.

-   We now support filtering by aggregated properties. For more information, see [Filtering](Data_Aggregation_and_Recursive_Hierarchy_7d91431.md#loio7d914317c0b64c23824bf932cc8a4ae1__section_DAF).


<sub>Changed•Feature•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V2 Model** 

</td>
<td valign="top">

**OpenUI5 OData V2 Model**

We now provide the `sap.ui.model.odata.ODataMetaModel#getFunctionImportParameterContext` method, which provides the parameter context for `sap.ui.model.odata.ODataMetaModel#getODataValueLists`. This enables the lazy loading of value list metadata of function import parameters.

For more information, see the API Reference for [`ODataMetaModel#getFunctionImportParameterContext`](https://sdk.openui5.org/api/sap.ui.model.odata.ODataMetaModel%23methods/getFunctionImportParameterContext) and [`ODataMetaModel#getODataValueLists`](https://sdk.openui5.org/api/sap.ui.model.odata.ODataMetaModel%23methods/getODataValueLists).

<sub>Changed•Feature•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MessageStrip`** 

</td>
<td valign="top">

**`sap.m.MessageStrip`**

The control can now display multiple links within its text using the `controls` aggregation.

<sub>Changed•Control•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Select`** 

</td>
<td valign="top">

**`sap.m.Select`**

We have enhanced `sap.m.Select` so that now navigating with the arrow keys in a selection in the control can be reverted using the [Esc\] key, even when the selection list is closed.

<sub>Changed•Control•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

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

<sub>Deprecated•Feature•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

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

We have added the `scrollThreshold` property. It only affects the inner table if it is of type `TableType.Table`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.table.GridTableType%23methods/getScrollThreshold).

<sub>Changed•Control•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.List`, `sap.m.Table`, `sap.m.Tree`** 

</td>
<td valign="top">

**`sap.m.List`, `sap.m.Table`, `sap.m.Tree`**

Group headers for the relevant items in these controls are now sticky, so they remain in a fixed position at the top of the page during vertical scrolling.

<sub>Changed•Control•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`** 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`**

-   We have adapted and tidied up the structure of the context menu of group headers \(for example, we have added submenus\). In addition, the mobile menu button for group headers has been removed.

-   We have tidied up the interactive row count mode and the related entities: We have aligned the visual design of the resizer with the `sap.ui.layout.Splitter` control and improved the interaction, for example, the auto-resize and some missing keyboard shortcuts. We have also added the `maxRowCount` property with a default value. To improve accessibility, we have also added ARIA roles and attributes. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.rowmodes.Interactive%23overview) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.RowModes).
-   We have added the `scrollThreshold` property to the controls. It resembles the existing `threshold` property , but it is only used for scrolling. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.Table%23methods/setScrollThreshold).

<sub>Changed•Control•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

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

A busy indicator is now shown while the rows are still loading. This prevents a misleading `noData` message from being displayed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar).

<sub>Changed•Control•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ResponsivePopover`** 

</td>
<td valign="top">

**`sap.m.ResponsivePopover`**

We have added a new `footer` aggregation to the control. This aggregation allows for the action buttons to be moved into an overflow menu on smaller screens when there isn't enough space. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.ResponsivePopover/sample/sap.m.sample.ResponsivePopover).

<sub>Changed•Control•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

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

We have added a new `selectedIndex` property to the `ComboBox` \(experimental\) filter. The property can provide an initial selected index of the combo box. As a developer, use this property if the keys of the items are not known up front. For more information, see the [Combo Box Filter](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/filters/comboBox) section and [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/comboBoxFilter/dynamicFilterSelectedIndex) in the Card Explorer.

<sub>Changed•Control•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
<tr>
<td valign="top">

1.129 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.unified.Menu`** 

</td>
<td valign="top">

**`sap.ui.unified.Menu`**

We have added a new `closed` event, which is fired when a menu is closed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.Menu).

<sub>Changed•Control•Info Only•1.129</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-03

</td>
</tr>
</table>

