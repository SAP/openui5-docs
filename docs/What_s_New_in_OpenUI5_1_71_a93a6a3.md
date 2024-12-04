<!-- loioa93a6a33b56447de8e158122ea2f57b8 -->

| loio |
| -----|
| a93a6a33b56447de8e158122ea2f57b8 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/a93a6a33b56447de8e158122ea2f57b8) | [demo kit latest release](https://sdk.openui5.org/topic/a93a6a33b56447de8e158122ea2f57b8)</div>

## What's New in OpenUI5 1.71

With this release OpenUI5 is upgraded from version 1.70 to 1.71.

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

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Card Explorer** 

</td>
<td valign="top">

**Card Explorer**

-   An entire new *Integrate* section has been added to the Card Explorer with more information about card consumption in the host environment - in apps, dashboards, or on any HTML page. This section gives you more information on how to use integration cards in apps and about the integration card API.
-   The Card Explorer now preserves the page last visited and thus offers an improved usability and better navigation.

For more information, see [Card Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/index.html).

<sub>Changed•Feature•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Announcement 

</td>
<td valign="top">

**Pre-Announcement: Deprecation of the SAPUI5 Tools for Eclipse** 

</td>
<td valign="top">

**Pre-Announcement: Deprecation of the SAPUI5 Tools for Eclipse**

Version 1.71 is the last SAPUI5 version for which we will update the [SAPUI5 Tools for Eclipse](https://tools.hana.ondemand.com/#sapui5).

> ### Caution:  
> After the release of SAPUI5 1.71, the SAPUI5 Tools for Eclipse will no longer be maintained.

We recommend that you use SAP Web IDE as the development environment for SAPUI5. For more information, see [App Development Using SAP Web IDE](App_Development_Using_SAP_Web_IDE_13ced94.md).

<sub>Changed•Announcement•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

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

-   Custom HTTP headers can be set statically in the manifest or dynamically using `sap.ui.model.odata.v4.ODataModel.changeHttpHeaders`.

-   Annotations for individual overloads of bound actions in the OData 4.01 format are understood as well.

-   `sap.ui.model.odata.v4.Context.requestSideEffects` can now also be called on a context belonging to a context binding that does not request data on its own. The call of `requestSideEffects` is propagated upwards in the binding hierarchy until a context binding or list binding that sends its own data requests is found. During the propagation, list bindings that do not send own data requests must not be passed.

-   Metadata parsing now uses a last-one-wins strategy for duplicated names consistently, also if operations are part of the duplicates.

-   With the model setting `autoExpandSelect:true`, property bindings that become active after their parent context or list binding has sent the first data request will be able to store their data so it can be reused by a later property binding with the same relative path and the same binding context.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and SAP Fiori elements applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Support Assistant** 

</td>
<td valign="top">

**Support Assistant**

The file extension assertion `getReportAsFileInFormat` for OPA tests; which enables Support Assistant checks`RuleEngineOpaExtension`, has changed. Now, the value of the `fileName` parameter should have the extension `.support-assistant.json`, or it will automatically be changed to `.support-assistant.json`. This new feature will improve file recognition in automated test scenarios. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.support.RuleEngineOpaAssertions/methods/sap.ui.core.support.RuleEngineOpaAssertions.getReportAsFileInFormat).

<sub>Changed•Feature•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.dnd.GridDropInfo`** 

</td>
<td valign="top">

**`sap.f.dnd.GridDropInfo`**

We have introduced a new `dropIndicatorSize` property. It allows the app developer to specify the size of the drop indicator for items which are not part of the grid, for example, if a flat list item is dragged over an `sap.f.GridContainer`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.dnd.GridDropInfo) and the [Sample](https://sdk.openui5.org/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainerDragAndDropFromList).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.DynamicPage`, `sap.uxap.ObjectPageLayout`** 

</td>
<td valign="top">

**`sap.f.DynamicPage`, `sap.uxap.ObjectPageLayout`**

We introduced visual improvements based on the latest SAP Fiori Design Guidelines. We adapted the headers of the controls to improve the visual hierarchy and achieve consistency between pages and floorplans.

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`** 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`**

We introduced a visual improvement of the column separator to enhance its visibility. It is applied to the SAP Quartz Light theme and both SAP Belize themes \(along with the high-contrast themes\), and there are no differences between the cozy mode and the compact mode.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.f.FlexibleColumnLayout/sample/sap.f.sample.FlexibleColumnLayoutWithTwoColumnStart).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.GridContainer`** 

</td>
<td valign="top">

**`sap.f.GridContainer`**

This control is no longer experimental, but some properties, methods, and aggregations are still in experimental state.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.GridContainer). 

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Dialog`, `sap.m.IconTabBar`, and `sap.m.Input`** 

</td>
<td valign="top">

**`sap.m.Dialog`, `sap.m.IconTabBar`, and `sap.m.Input`**

Visual improvements based on the latest SAP Fiori Design Guidelines were implemented for the SAP Quartz Light theme.

-   `sap.m.Dialog` - button stretching on mobile phones has been removed.
-   `sap.m.Input` - `Success` semantic state border is now 1 px for both the SAP Quartz Light and SAP Belize themes.
-   `sap.m.IconTabBar` - top, right, and left shadows are hidden. The bottom shadow is visible over the content, and the bottom border has been removed.

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Label`** 

</td>
<td valign="top">

**`sap.m.Label`**

Visual changes have been introduced. If the `required` property is set to `true`, the asterisk is now smaller and darker. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Label/sample/sap.m.sample.Label).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Link`** 

</td>
<td valign="top">

**`sap.m.Link`**

A new key user adaptation/SAPUI5 flexibility feature now enables the `target` property to be changed in the UI Adaptation mode if the `href` property is set. For more information, see the [Samples](https://sdk.openui5.org/entity/sap.m.Link).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

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

We have changed the look of the `sap.m.PlanningCalendar`. The header part is now aligned with the one of `sap.m.SinglePlanningCalendar` to have a similar experience when interacting with the two controls. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarModifyAppointments).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.SelectDialog`** 

</td>
<td valign="top">

**`sap.m.SelectDialog`**

We have updated the behavior of the `sap.m.SelectDialog` when the single selection mode has the `rememberSelections` property set to `true`. Now the user can close the `SelectDialog` by pressing the already selected item from a single selection dialog. This means that the users no longer need to press *Cancel*, if they have opened the `SelectDialog` for a second time to check what was previously selected. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SelectDialog) and the [Sample](https://sdk.openui5.org/entity/sap.m.SelectDialog). 

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

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

A new `viewChange` event has been introduced, which is fired when the user changes the view of the control. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.TableSelectDialog`** 

</td>
<td valign="top">

**`sap.m.TableSelectDialog`**

The new `resizable` and `draggable` properties have been introduced which affect the desktop mode. They allow the `TableSelectDialog` to be dragged and resized. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TableSelectDialog) and the [Sample](https://sdk.openui5.org/entity/sap.m.TableSelectDialog/sample/sap.m.sample.TableSelectDialog).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

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

We have improved the user experience of the search. When there are no items matching the search criteria, the *Select All* checkbox is disabled. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ViewSettingsDialog).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

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

-   Static resource handling improvements have been introduced. Relative URLs for static resources \(i18n files, icons, and images\) inside the manifest can now be resolved based on the provided path in the `baseURL` property. This property helps to resolve the card bundle resource locations, in cases when the card manifest is provided as an object.

-   We have introduced a new `withCredentials` boolean property for the `sap.ui.integration.widgets.Card`’s manifest. It is part of the `request` property. It indicates whether cross-site requests should be made using credentials or not.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.Card).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
<tr>
<td valign="top">

1.71 

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

The new `enableNotification` property of `MultiSelectionPlugin` can be used to display a message when the limit of rows that has been selected at the same time is reached.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.plugins.MultiSelectionPlugin) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.MultiSelectionPlugin).

<sub>Changed•Control•Info Only•1.71</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-10-10

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.130](What_s_New_in_OpenUI5_1_130_85609d4.md "With this release OpenUI5 is upgraded from version 1.129 to 1.130.")

[What's New in OpenUI5 1.129](What_s_New_in_OpenUI5_1_129_d22b8af.md "With this release OpenUI5 is upgraded from version 1.128 to 1.129.")

[What's New in OpenUI5 1.128](What_s_New_in_OpenUI5_1_128_1f76220.md "With this release OpenUI5 is upgraded from version 1.127 to 1.128.")

[What's New in OpenUI5 1.127](What_s_New_in_OpenUI5_1_127_e5e1317.md "With this release OpenUI5 is upgraded from version 1.126 to 1.127.")

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

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_521cad9.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

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

