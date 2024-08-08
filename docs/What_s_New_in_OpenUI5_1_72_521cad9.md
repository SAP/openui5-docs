<!-- loio521cad948308479486ba50b3532b9f74 -->

| loio |
| -----|
| 521cad948308479486ba50b3532b9f74 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/521cad948308479486ba50b3532b9f74) | [demo kit latest release](https://sdk.openui5.org/topic/521cad948308479486ba50b3532b9f74)</div>

## What's New in OpenUI5 1.72

With this release OpenUI5 is upgraded from version 1.71 to 1.72.

***

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

1.72 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**New Theme Available \(Experimental\)** 

</td>
<td valign="top">

**New Theme Available \(Experimental\)**

A new theme *SAP Quartz Dark* \(theme ID: `sap_fiori_3_dark`\) has been introduced. The theme is provided as an additional theme in OpenUI5.

> ### Note:  
> This theme will have the status 'experimental' until testing is complete.

<sub>New•Feature•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

****Responsive Paddings Enablement**** 

</td>
<td valign="top">

****Responsive Paddings Enablement****

We have introduced the `sap.ui.core.util.ResponsivePaddingsEnablement` utility for applying responsive paddings over separate parts of the controls, when using the SAP Quartz themes. The breakpoints and layout paddings can now be determined by the container's width, and not by the screen size. We have introduced responsive paddings to the `sap.m.Page`,`sap.m.Popover`, and `sap.m.Wizard` controls.

For more information, see [Enabling Responsive Paddings According to the Control Width](Enabling_Responsive_Paddings_According_to_the_Control_Width_3b718b5.md).

<sub>New•Feature•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.ProductSwitch` \(Experimental\)** 

</td>
<td valign="top">

**`sap.f.ProductSwitch` \(Experimental\)**

The new layout control is a single-level navigation menu that offers access to the entry pages of products. Its items can be configured with an image/icon, title, subtitle, and navigation target.

![](images/loio0a4532ffdad544a783a2670901a43e85_HiRes.png)

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.ProductSwitch) and the [Samples](https://sdk.openui5.org/entity/sap.f.ProductSwitch).

<sub>New•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Navigation in Nested Components** 

</td>
<td valign="top">

**Navigation in Nested Components**

The navigation in nested components has been enhanced with additional information that can now be passed in optional parameters of the `navTo` method of `sap.ui.core.routing.Router`. This additional information enables the routers in nested components to show the targets which are configured to one specific route.

For more information, see [`sap.ui.core.routing.Router.navTo`](https://sdk.openui5.org/api/sap.ui.core.routing.Router/methods/navTo) in the API Reference and [Navigate with Nested Components](Navigate_with_Nested_Components_8e9d6e4.md).

<sub>Changed•Feature•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

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

-   Server-driven paging is now supported unless the server-driven paging takes place in a collection requested with `$expand`.

-   The `resetChanges` method on bindings returns a promise which is resolved without a defined result as soon as all changes in the binding itself and all dependent bindings are canceled.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and SAP Fiori elements applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Title Alignment Changes for SAP Quartz Themes** 

</td>
<td valign="top">

**Title Alignment Changes for SAP Quartz Themes**

A new title alignment has been introduced for the SAP Quartz themes. The title of the affected control is aligned to the start position \(left or right depending on the text directionality\).

Affected Controls:

-   `sap.m.BusyDialog`
-   `sap.m.Dialog`
-   `sap.m.MessageBox`
-   `sap.m.Page`
-   `sap.m.Popover`
-   `sap.m.ResponsivePopover`
-   `sap.m.SelectDialog`
-   `sap.m.TableSelectDialog`
-   `sap.m.ViewSettingsDialog`

<sub>Changed•Feature•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.Avatar`** 

</td>
<td valign="top">

**`sap.f.Avatar`**

We have added more options in the `sap.f.AvatarColor` enum for the background color of the `sap.f.Avatar`: `Transparent`, `TileIcon`, and `Placeholder`. To set them, use the `backgroundColor` property.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.f.Avatar/sample/sap.f.sample.Avatar).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayoutSemanticHelper`** 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayoutSemanticHelper`**

Some methods in the helper class rely on the internal `sap.f.FlexibleColumnLayout` reference to be rendered. To facilitate their use, we have implemented two new public methods: `whenDOMReady` and `isDOMReady`. Additionally, two more abstract methods were implemented that internally wrap `isDOMReady` and `whenDOMReady`, which provide means for other similar methods to be combined, if necessary.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.FlexibleColumnLayoutSemanticHelper).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ActionSheet`** 

</td>
<td valign="top">

**`sap.m.ActionSheet`**

We have extended the `afterClose` event, to provide context information that indicates the trigger of closing the control - whether it closes with a selection, or it is dismissed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ActionSheet).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ComboBox`, `sap.m.MultiComboBox`, `sap.m.Input`, `sap.m.MultiInput`** 

</td>
<td valign="top">

**`sap.m.ComboBox`, `sap.m.MultiComboBox`, `sap.m.Input`, `sap.m.MultiInput`**

We have improved the controls to display the text set in the `valueStateText` property on multiple lines. This ensures that the value state text is displayed even when it is longer than the width of the control's container. For more information, see the [`sap.m.ComboBox` Sample](https://sdk.openui5.org/entity/sap.m.ComboBox/sample/sap.m.sample.ComboBoxValueState).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.DateRangeSelection`** 

</td>
<td valign="top">

**`sap.m.DateRangeSelection`**

We have introduced an optional footer with *OK* and *Cancel* buttons, to provide an alternative way for users to confirm the date range selection. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DateRangeSelection).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

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

-   A new parameter for the direction of the `swipe` event is now available for both left-to-right \(LTR\) and right-to-left \(RTL\) scenarios. This parameter can be used in an app for approvals, for example, where a manager wants to accept or reject leave requests using the swipe function on a mobile device or touch screen. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SwipeDirection) for `SwipeDirection`, the [API Reference](https://sdk.openui5.org/api/sap.m.ListBase/events/swipe) for `swipe`, and the [Sample](https://sdk.openui5.org/entity/sap.m.List/sample/sap.m.sample.ListSwipe).

-   A new `navigated` property is now available: After a user has displayed the details of an item, a navigation indicator at the end of the corresponding row indicates that the user has already viewed the details. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ListItemBase), the [Sample](https://sdk.openui5.org/entity/sap.m.StandardListItem) for lists, and the [Sample](https://sdk.openui5.org/entity/sap.m.Table) for tables.


<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

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

The `appointmentSelect` event was also provided for the appointments in the Month view, fired when an appointment is selected. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

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

**`sap.m.Table`**

If applications configure a responsive table that contains only one column in such a way that all columns are moved to the pop-in or hidden on smaller screens, this setting is now ignored to ensure that there is at least one column visible in the tabular layout. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ViewSettingsDialog`** 

</td>
<td valign="top">

**`sap.m.ViewSettingsDialog`**

The *Reset* button is now fully available for all the tabs in this control.

-   For built-in tabs \(Sort, Group, and Filter\), the initial state of the Sort and Group settings is stored upon first opening. If changed, this state can be restored later using the *Reset* button and Filter tab selection is removed. If no changes have been made, the *Reset* button remains inactive.
-   For custom tabs \(or custom and built-in tabs together\), developers can use the `Reset` event. The *Reset* button is in an active state, no matter if changes are made or not.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ViewSettingsDialog).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

<code><b>sap.m.Wizard</b></code> 

</td>
<td valign="top">

<code><b>sap.m.Wizard</b></code>

We have added a new `backgroundDesign` property. It can change the background color of the content and accepts values from `sap.m.PageBackgroundDesign`. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Wizard/sample/sap.m.sample.WizardCurrentStep).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

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

-   The predefined parameter `LOCALE` is now available, and developers can use it in data-request URL queries.
-   New `manifestReady` event has been introduced in an experimental state. It is fired after the manifest is loaded.
-   The `Refresh` method is now available in experimental state when consuming `sap.ui.integration.widgets.Card` as custom HTML element.

For more information, see [Card Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/index.html).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

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

-   You can now select rows using key combinations \(select one row: [SHIFT\] + [SPACE\] , select multiple rows: [SHIFT\] + [UP\]  and [SHIFT\] + [DOWN\] \). For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.Selection).

-   A new `navigated` property is now available for rows with row actions: After a user has displayed the details of an item, a navigation indicator at the end of the corresponding row indicates that the user has already viewed the details. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.RowSettings) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.RowAction).


<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.unified.FileUploader`** 

</td>
<td valign="top">

**`sap.ui.unified.FileUploader`**

The new `fileEmpty` event was introduced, fired when uploading an empty file. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.sap.ui.unified.FileUploader).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
<tr>
<td valign="top">

1.72 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.uxap.BlockBase`** 

</td>
<td valign="top">

**`sap.uxap.BlockBase`**

You can now subscribe to the new `viewInit` event that is fired when the asynchronously created internal view is available.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.BlockBase).

<sub>Changed•Control•Info Only•1.72</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-11-21

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.126](What_s_New_in_OpenUI5_1_126_1d98116.md "With this release OpenUI5 is upgraded from version 1.125 to 1.126.")

[What's New in OpenUI5 1.125](What_s_New_in_OpenUI5_1_125_9d87044.md "With this release OpenUI5 is upgraded from version 1.124 to 1.125.")

[What's New in OpenUI5 1.124](What_s_New_in_OpenUI5_1_124_7f77c3f.md "With this release OpenUI5 is upgraded from version 1.123 to 1.124.")

[What's New in OpenUI5 1.123](What_s_New_in_OpenUI5_1_123_9d00ac7.md "With this release OpenUI5 is upgraded from version 1.122 to 1.123.")

[What's New in OpenUI5 1.122](What_s_New_in_OpenUI5_1_122_5d078da.md "With this release OpenUI5 is upgraded from version 1.121 to 1.122.")

[What's New in OpenUI5 1.121](What_s_New_in_OpenUI5_1_121_91a4a2f.md "With this release OpenUI5 is upgraded from version 1.120 to 1.121.")

[What's New in OpenUI5 1.120](What_s_New_in_OpenUI5_1_120_2359b63.md "With this release OpenUI5 is upgraded from version 1.119 to 1.120.")

[What's New in OpenUI5 1.119](What_s_New_in_OpenUI5_1_119_0b1903a.md "With this release OpenUI5 is upgraded from version 1.118 to 1.119.")

[What's New in OpenUI5 1.118](What_s_New_in_OpenUI5_1_118_3eecbde.md "With this release OpenUI5 is upgraded from version 1.117 to 1.118.")

[What's New in OpenUI5 1.117](What_s_New_in_OpenUI5_1_117_029d3b4.md "With this release OpenUI5 is upgraded from version 1.116 to 1.117.")

[What's New in OpenUI5 1.116](What_s_New_in_OpenUI5_1_116_ebd6f34.md "With this release OpenUI5 is upgraded from version 1.115 to 1.116.")

[What's New in OpenUI5 1.115](What_s_New_in_OpenUI5_1_115_409fde8.md "With this release OpenUI5 is upgraded from version 1.114 to 1.115.")

[What's New in OpenUI5 1.114](What_s_New_in_OpenUI5_1_114_890fce1.md "With this release OpenUI5 is upgraded from version 1.113 to 1.114.")

[What's New in OpenUI5 1.113](What_s_New_in_OpenUI5_1_113_a9553fe.md "With this release OpenUI5 is upgraded from version 1.112 to 1.113.")

[What's New in OpenUI5 1.112](What_s_New_in_OpenUI5_1_112_34afc69.md "With this release OpenUI5 is upgraded from version 1.111 to 1.112.")

[What's New in OpenUI5 1.111](What_s_New_in_OpenUI5_1_111_7a67837.md "With this release OpenUI5 is upgraded from version 1.110 to 1.111.")

[What's New in OpenUI5 1.110](What_s_New_in_OpenUI5_1_110_71a855c.md "With this release OpenUI5 is upgraded from version 1.109 to 1.110.")

[What's New in OpenUI5 1.109](What_s_New_in_OpenUI5_1_109_3264bd2.md "With this release OpenUI5 is upgraded from version 1.108 to 1.109.")

[What's New in OpenUI5 1.108](What_s_New_in_OpenUI5_1_108_66e33f0.md "With this release OpenUI5 is upgraded from version 1.107 to 1.108.")

[What's New in OpenUI5 1.107](What_s_New_in_OpenUI5_1_107_d4ff916.md "With this release OpenUI5 is upgraded from version 1.106 to 1.107.")

[What's New in OpenUI5 1.106](What_s_New_in_OpenUI5_1_106_5b497b0.md "With this release OpenUI5 is upgraded from version 1.105 to 1.106.")

[What's New in OpenUI5 1.105](What_s_New_in_OpenUI5_1_105_4d6c00e.md "With this release OpenUI5 is upgraded from version 1.104 to 1.105.")

[What's New in OpenUI5 1.104](What_s_New_in_OpenUI5_1_104_69e567c.md "With this release OpenUI5 is upgraded from version 1.103 to 1.104.")

[What's New in OpenUI5 1.103](What_s_New_in_OpenUI5_1_103_0e98c76.md "With this release OpenUI5 is upgraded from version 1.102 to 1.103.")

[What's New in OpenUI5 1.102](What_s_New_in_OpenUI5_1_102_f038c99.md "With this release OpenUI5 is upgraded from version 1.101 to 1.102.")

[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_7733b00.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_27dec1d.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_4f35848.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_d9f16f2.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_fa0e282.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_7a9269f.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_a1aea67.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_c40f1e6.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_f273340.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1ef345d.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_0a2bd79.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_91c10c2.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_e56cddc.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_e15a206.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_b506da7.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_4c1c959.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_1d18eb5.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_dc76640.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_3a8dd13.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f5e2a21.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_8cee506.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_99c4cdc.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_c46b439.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_aad03b5.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_5cbb62d.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_c22208a.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_231dd13.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_a93a6a3.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_f073d69.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_f94bf93.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_a6b1472.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_c9896e9.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_0f5acfd.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_0e30822.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_e8d9da7.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_771f4d5.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_d991552.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_5a0e1f7.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_7c927aa.md "With this release OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_108b7fd.md "With this release OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_c838330.md "With this release OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_849e1b6.md "With this release OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

