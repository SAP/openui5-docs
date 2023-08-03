<!-- loio029d3b4a39c84384be6398c444f7e06a -->

| loio |
| -----|
| 029d3b4a39c84384be6398c444f7e06a |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/029d3b4a39c84384be6398c444f7e06a) | [demo kit latest release](https://sdk.openui5.org/topic/029d3b4a39c84384be6398c444f7e06a)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.117

With this release OpenUI5 is upgraded from version 1.116 to 1.117.

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

To improve accessibility, we will completely rework the screen reader and keyboard support of the `sap.m.Table` control in 1.118. The row-based navigation stays the same, but cell-based navigation will also be possible, similar to the grid table. We will also improve other accessibility features of the table, for example, the *Delete* and *Edit* buttons for row actions will become accessible via keyboard. These features will not only be changed for the responsive table, but partly also for `sap.m.List`. Also, the ARIA role will be adapted.

**Recommended Action**: Test cases might have to be adapted. Stay tuned .

.

<sub><span style="color:#666666;"><span class="SAP-icons"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)**•UI Changed•Announcement•Recommended•Upcoming</sub>



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

1.117 



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

-   `sap.ui.table.ColumnMenu` and `sap.ui.table.AnalyticalColumnMenu`

-   `menu` aggregation of `Column`

-   `columnMenuOpen` event of `Column`
-   `columnVisibilityMenuSorter` property of `AnalyticalTable`

-   `showColumnVisibilityMenu` property of `Table`

-   `columnVisibility` event of `Table`

Instead of the deprecated `ColumnMenu`, you can use the `sap.m.table.columnmenu.Menu` control.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.table.columnmenu.Menu) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.Menus).

<sub>Deprecated•Feature•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`** 



</td>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`**

To define the semantic level of a header, we have introduced the `headerLevel` property.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ListBase%23methods/getHeaderLevel).

<sub>Changed•Control•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



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

Refreshing table data via binding might be required if it has been changed in the back end. For example, a user might have selected *Go* in the filter bar without actually changing any filter settings. To evaluate whether the binding needs to be refreshed, even if `bindingInfo` has not changed, the `TableDelegate` uses the new `updateBinding` parameter `mSettings.forceRefresh`.

For more information, see the [API Reference](https://sdk.openui5.org/api/module:sap/ui/mdc/TableDelegate%23methods/sap/ui/mdc/TableDelegate.updateBinding).

<sub>Changed•Control•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

****Sample for `sap.ui.mdc` library**** 



</td>
<td valign="top">

****Sample for `sap.ui.mdc` library****

You can now test the table and filter bar features of the \(experimental\) `sap.ui.mdc` library in a sample. To find the sample for this library in the Demo Kit, go to *Samples* and select MDC Overview. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.mdc/sample/sap.ui.mdc.demokit.sample.TableFilterBarJson).

<sub>New•Feature•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.ui.layout.form.SimpleForm`** 



</td>
<td valign="top">

**`sap.ui.layout.form.SimpleForm`**

`ResponsiveGridLayout` is now the default layout for `SimpleForm` controls \(instead of `ResponsiveLayout`, which has already been deprecated\).

<sub>Changed•Control•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



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

Since OpenUI5 1.116, the framework leverages features of modern ECMAScript up to and including [ECMAScript 2022 Language Specification](https://262.ecma-international.org/13.0/). There are certain restrictions you have to consider when using modern ECMAScript with your UI5 project.

For more information, see [ECMAScript Support](ECMAScript_Support_0cb44d7.md). Please also make sure to [upgrade your tools for modern ECMAScript in UI5](https://blogs.sap.com/2023/05/24/upgrade-your-tools-for-modern-ecmascript-in-ui5/).

<sub>Changed•Feature•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Theme-Dependent Custom Icon Fonts** 



</td>
<td valign="top">

**Theme-Dependent Custom Icon Fonts**

You can now configure variants of a custom icon font for different UI5 themes; previously, a custom icon font was applied to all themes. With an enhanced version of the metadata JSON file associated with an icon font, you can provide theme-dependent path configuration. For instance, this allows you to easily differentiate between custom icons for modern themes, such as SAP Horizon, and custom icons for older themes.

For more information and an example, see [Icon and Icon Pool](Icon_and_Icon_Pool_21ea0ea.md).

<sub>Changed•Feature•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



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

-   We now provide `withCredentials` as an experimental model parameter.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel).

-   **Experimental:** You can now create a nested single entity behind a single-valued navigation property in the transient entity.

    For more information, see *Nested Single Entity* in [Deep Create](Creating_an_Entity_c9723f8.md#loioc9723f8265f644af91c0ed941e114d46__section_DCR).

-   Support for read-only hierarchies is now available.

    For more information, see [Recursive Hierarchy](Extension_for_Data_Aggregation_7d91431.md#loio7d914317c0b64c23824bf932cc8a4ae1__section_RCH).


<sub>Changed•Feature•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



</td>
<td valign="top">

New 



</td>
<td valign="top">

User Documentation 



</td>
<td valign="top">

**TypeScript Tutorial** 



</td>
<td valign="top">

**TypeScript Tutorial**

You are familiar with OpenUI5 app development, but do you want to learn how to do it in TypeScript? Now there is a video that guides you through the official UI5 TypeScript Tutorial, adds hints about how to avoid pitfalls, and provides some background information. To find it, see [UI5 TypeScript Tutorial video](https://youtu.be/CRKNIiXZN6U).

<sub>New•User Documentation•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Menu` and `sap.ui.unified.Menu`** 



</td>
<td valign="top">

**`sap.m.Menu` and `sap.ui.unified.Menu`**

We have introduced a new `isOpen` method that indicates whether the menu is currently open. The `bOpen` flag in `sap.ui.unified.Menu`, which was used for similar purposes, will be phased out. If you use this flag in your applications, we recommend that you replace it with the new method. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Menu/methods/isOpen).

<sub>Changed•Control•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



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

Users can now select a whole week from the Month view if they click on the week number. A second click removes the selection. This feature is enabled when the `dateSelectionMode` property is set to `MultiSelect`. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarDateSelection).

<sub>Changed•Control•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.SelectDialog` and `sap.m.TableSelectDialog`** 



</td>
<td valign="top">

**`sap.m.SelectDialog` and `sap.m.TableSelectDialog`**

To improve the accessibility of these controls, we have introduced a new `initialFocus` property. It defines whether the initial focus will be received by the `SearchField` or by the `Content` list. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SelectDialogBase) and the [Sample](https://sdk.openui5.org/entity/sap.m.TableSelectDialog/sample/sap.m.sample.TableSelectDialogGrowing).

<sub>Changed•Control•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**OPA Framework** 



</td>
<td valign="top">

**OPA Framework**

We have enhanced the OPA framework to now perform comprehensive checks for component parents, ensuring controls nested within multiple layers are correctly treated when evaluating busy states.

<sub>Changed•Feature•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
<tr>
<td valign="top">

1.117 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Panel`** 



</td>
<td valign="top">

**`sap.m.Panel`**

We have introduced the `stickyHeader` property. When set to `true`, the header of the panel will be visible while scrolling content. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Panel/sample/sap.m.sample.PanelSticky). 

<sub>Changed•Control•Info Only•1.117</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2023-08-10



</td>
</tr>
</table>

