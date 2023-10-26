<!-- loio0b1903a1fcf04cb588985d7f01b0796e -->

| loio |
| -----|
| 0b1903a1fcf04cb588985d7f01b0796e |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/0b1903a1fcf04cb588985d7f01b0796e) | [demo kit latest release](https://sdk.openui5.org/topic/0b1903a1fcf04cb588985d7f01b0796e)</div>

## What's New in OpenUI5 1.119

With this release OpenUI5 is upgraded from version 1.118 to 1.119.

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

1.119 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.p13n.Popup`** 

</td>
<td valign="top">

**sap.m.p13n.Popup**

To select all columns in the personalization dialog, the user can now use the *Select All* option. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.p13n.SelectionPanel%23methods/setMultiSelectMode). 

<sub>Changed•Control•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable, sap.ui.table.Table, sap.ui.table.TreeTable`** 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable, sap.ui.table.Table, sap.ui.table.TreeTable` **

-   You can now use `sap.m.plugins.CellSelector` \(experimental\) for cell selection in a table. It can also be used for the `sap.ui.mdc.Table` control \(experimental\). For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.CellSelector). 

-   We have made the different row mode elements of the tables available. They replace the various properties \(now deprecated\) that used to define, for example, whether a fixed number of rows is displayed in a table, or whether the user can change the number of displayed rows. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.rowmodes) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.RowModes).


<sub>Changed•Feature•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.m.plugins.CopyProvider`** 

</td>
<td valign="top">

**`sap.m.plugins.CopyProvider`**

Users can now copy a cell block they have selected. To provide the required settings, we have introduced the `sap.m.plugins.CopyPreference` enumeration that allows users to either only copy selected cells or both rows and cells that they have selected. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.CopyPreference).

<sub>Changed•Feature•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

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

-   `visibleRowCountMode`

-   `visibleRowCount`

-   `fixedRowCount`

-   `fixedBottomRowCount`

-   `rowHeight`

-   `minAutoRowCount`


<sub>Deprecated•Feature•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.Table` \(experimental\)** 

</td>
<td valign="top">

**`sap.ui.mdc.Table` \(experimental\)**

Drag and drop has been enabled for the rows of the \(experimental\) `sap.ui.mdc.Table` control. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.table.DragDropConfig).

<sub>Changed•Control•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`valueHelpOnly` functionality** 

</td>
<td valign="top">

**`valueHelpOnly` functionality**

We have deprecated the `valueHelpOnly` functionality in the `sap.m.Input` control and its usage is discouraged. The reason is linked to the proper accessibility state of the control, therefore we advise against its further use.

<sub>Deprecated•Control•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 Data Types** 

</td>
<td valign="top">

**OpenUI5 Data Types**

The `getPlaceholderText` method is no longer experimental and can be used productively. It was introduced with OpenUI5 1.114 and is used with the following data types:

-   `sap.ui.model.odata.type.ODataType` and any OData types inheriting from it
-   `sap.ui.model.odata.type.DateTimeWithTimezone`
-   `sap.ui.model.type.Date`
-   `sap.ui.model.type.DateInterval`

<sub>Changed•Feature•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 Client Models** 

</td>
<td valign="top">

**OpenUI5 Client Models**

Client models like `sap.ui.model.json.JSONModel` now support the `ignoreMessages` binding parameter for property bindings.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.ClientModel%23methods/bindProperty).

<sub>Changed•Feature•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

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

For the `tokenHandling` parameter of the `v2.ODataModel`, we now support the additional `skipServerCache` string value. If you provide this value, the security token is not cached with the server as a key. This prevents failing `$batch` requests when accessing services running on different back-end systems behind a reverse proxy. Use this option only if the system landscape is known.

<sub>Changed•Feature•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

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

-   **Experimental:** You can now move nodes in recursive hierarchies. This experimental feature must not be used in productive applications yet.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/move).

-   **Experimental:** The `sap.ui.model.odata.v4.ODataContextBinding#execute` method can now also return a so-called return value context if the path of the binding parameter contains a navigation property. This experimental feature must not be used in productive applications yet.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding%23methods/execute).


<sub>Changed•Feature•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MenuButton`** 

</td>
<td valign="top">

**`sap.m.MenuButton`**

The `beforeMenuOpen` event, which was previously fired in split button mode only, now also fires in regular mode. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MenuButton).

<sub>Changed•Control•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

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

We have introduced a new `rowHeaderPress` event that is fired when the row header is pressed with a mouse click or when reached by the keyboard. This new event replaces the deprecated `rowHeaderClick` event, which was fired on mouse click only. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar).

<sub>Changed•Control•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
<tr>
<td valign="top">

1.119 

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

-   We have updated the Adaptive type `sap.ui.integration.widgets.Card` to support the newest markdown features available for Microsoft Adaptive Cards. Тhe markdown third-party packages are now updated to version 12.3.2. For more information, see the [Adaptive Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesOther/adaptive) Learn section and [Markdown](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/markdown) Samples in the Card Explorer.
-   Client-side pagination now provides access to the paginator model. Before, access was available only for server-side pagination. Card developers can now leverage the power of `skip`, `size`, and `pageIndex` model values to create more informative cards using data binding. For more information, see the [Pagination](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/pagination) Learn section and [Samples](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/pagination) in the Card Explorer.
-   The \(experimental\) `ShowCard` action is used to show another card with more details or additional actions. We have introduced two new \(experimental\) properties to control the card:
    -   `closeButton` - shows or hides a *Close* button in the header of the card. For more information, see the [Default Header](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/default) and [Numeric Header](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/numeric) Learn sections in the Card Explorer.
    -   `resizable` - controls whether the card can be resized. For more information, see the [Show Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/actions/showCard) Learn section in the Card Explorer.


<sub>Changed•Control•Info Only•1.119</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-10-05

</td>
</tr>
</table>

