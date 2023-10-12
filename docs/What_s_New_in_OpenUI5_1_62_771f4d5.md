<!-- loio771f4d5cb01c4b6da7232ef8a841683d -->

| loio |
| -----|
| 771f4d5cb01c4b6da7232ef8a841683d |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/771f4d5cb01c4b6da7232ef8a841683d) | [demo kit latest release](https://sdk.openui5.org/topic/771f4d5cb01c4b6da7232ef8a841683d)</div>

## What's New in OpenUI5 1.62

With this release OpenUI5 is upgraded from version 1.61 to 1.62.

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

1.62 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.GenericTag`** 



</td>
<td valign="top">

**`sap.m.GenericTag`**

The new `sap.m.GenericTag` control displays complimentary information related to the current page, such as key performance indicators \(KPI\) and situations.

![](images/loio7fe88c577d264962b6bec8427efc968d_HiRes.png)

It consists of four different parts:

-   A required status indicator with semantic colors \(A\)

-   An optional icon that is displayed in the same color as the status indicator \(B\)

-   A required text that is truncated automatically \(C\)

-   An optional content area that can display either a control of type `sap.m.ObjectNumber` or a warning icon \(D\)


![](images/loiofb7c92bd4aca46a2abb579058c481ded_HiRes.png)

The control can move to the overflow area of `sap.m.OverflowToolbar`.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.GenericTag) and the [Samples](https://sdk.openui5.org/entity/sap.m.GenericTag).

<sub>New•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`** 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

A card is a user experience design pattern that displays the most concise pieces of information in a limited-space container. It helps users structure their work in an intuitive and dynamic way.

  
  
**Analytical card**

![](images/loio3ff4cbace0714a71924a628d8c81d480_LowRes.png "Analytical card")

Using cards, you can group information, link additional details, and present a summary. You can also get direct insights without leaving the current screen and choose further navigation options. Each card is designed in a different style and contains various content formats.

-   The List card is used to display multiple list items of all kinds.

-   The Analytical card is used for data visualization with various chart types.


Cards can be used by referencing the `sap.ui.integration` library.

`sap.ui.integration.widgets.Card` is a self-contained user interface element, connected to a manifest and used as a widget.

For more information, see [Cards](Cards_5b46b03.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.Card), and the [Samples](https://sdk.openui5.org/entity/sap.ui.integration.widgets.Card).

<sub>New•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Routing in Nested Components** 



</td>
<td valign="top">

**Routing in Nested Components**

OpenUI5 routing now supports navigation to components in addition to the already existing routing to views. You configure the routing in the component’s manifest. Moreover, the target component can also come with its own routing, which integrates via enhanced configuration in the manifest.

For details, see [Enabling Routing in Nested Components](Enabling_Routing_in_Nested_Components_fb19f50.md).

<sub>Changed•Feature•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



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

-   Bound actions on collections can now be executed using the header context of the `sap.ui.model.odata.v4.ODataListBinding`. If the returned entity is part of the same entity set, the promise of `sap.ui.model.odata.v4.ODataContextBinding#execute` can be resolved with a return value context.

-   `sap.ui.model.odata.v4.Context#requestSideEffects` was introduced in OpenUI5 1.61 and now resolves side effects in :n navigations reloading only affected properties.

-   The `##` syntax for branching into the `MetaModel` as described in `sap.ui.model.odata.v4.ODataModel#bindProperty` is now also available in property bindings.

-   Non-primitive values are supported in property bindings with binding mode `OneTime` and target type `"any"`.

-   The following methods can now be executed while a binding is suspended:

    -   `filter`, `sort`, `changeParameters`, `setAggregation`, and `updateAnalyticalInfo` of `sap.ui.model.odata.v4.ODataListBinding`

    -   `changeParameters` of `sap.ui.model.odata.v4.ODataContextBinding`

    -   `refresh` method of all bindings


    When the binding is resumed, a request reflecting all the changes by these methods is triggered.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



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

The control can now display several items at once. This functionality is implemented through a new `customLayout` aggregation of type `sap.m.CarouselLayout`. The `sap.m.CarouselLayout` defines how many items are displayed in the visible area of the `sap.m.Carousel` control and has a `visiblePagesCount` property, which determines the count of items to be displayed.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Carousel) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.CarouselWithMorePages/preview).

<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Column`** 



</td>
<td valign="top">

**`sap.m.Column`**

The `sortIndicator` property now shows a sort icon when a column is sorted. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Column) for the `sortIndicator` property.

<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.ComboBox`** 



</td>
<td valign="top">

**`sap.m.ComboBox`**

In order for the `ComboBox` to be aligned with the rest of the input controls and the already available features, we updated the used list structure of the control from `sap.m.SelectList` to `sap.m.List`, and respectively updated the protected API `getList`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ComboBox).

<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.ListBase`** 



</td>
<td valign="top">

**`sap.m.ListBase`**

You can now use more values for the `highlight` property. These values are provided by the `sap.ui.core.MessageType` and `sap.ui.core.IndicationColor` enumerations. To define a custom semantic for the highlight color, you can use the new `highlightText` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ListItemBase/controlProperties) for the `highlight` property.

<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.OverflowToolbar`** 



</td>
<td valign="top">

**`sap.m.OverflowToolbar`**

-   We extended the `sap.m.sample.OverflowToolbarSimple` sample to demonstrate the behavior of grouped controls. It contains two pairs of grouped controls: `Label` with `Input` and `Label` with `Select`.For more information, see the [Sample](https://sdk.openui5.org/sample/sap.m.sample.OverflowToolbarSimple/preview).

-   The `sap.m.OverflowToolbar` now allows `sap.m.GenericTag` to move into the overflow area.For more information, see the [Sample](https://sdk.openui5.org/sample/sap.m.sample.OverflowToolbarSimple/preview).


<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



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

-   You can now select or deselect single appointments either by clicking or tapping on the appointment or by using the keyboard arrow keys to navigate to the appointment and then select or deselect it by pressing the space bar or the [Enter\] key. You can enter multi-selection mode using key combinations \(for example, [Ctrl + click\] for Microsoft Windows Operating Systems or [Cmd + click\] for Mac Operating Systems\).

-   The `sap.m.SinglePlanningCalendar` now has a new `stickyMode` property which allows users to select which toolbars will be fixed while scrolling.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Samples](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.StandardListItem`** 



</td>
<td valign="top">

**`sap.m.StandardListItem`**

The new `information` value in the `sap.ui.core.ValueState` enumeration is now supported by the `infoState` property of `StandardListItem`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.StandardListItem/methods/getInfoState).

<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.tnt.SideNavigation`** 



</td>
<td valign="top">

**`sap.tnt.SideNavigation`**

We have implemented a `selectedKey` property of `sap.tnt.SideNavigation`, with which you can easily set the selected item, when the control is bound to a model. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.tnt.SideNavigation) and the [Sample](https://sdk.openui5.org/sample/sap.tnt.sample.ToolPage/preview).

<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.ui.core.support.RuleEngineOpaExtension`** 



</td>
<td valign="top">

**`sap.ui.core.support.RuleEngineOpaExtension`**

The rule engine OPA extension, which allows Support Assistant checks, has been enhanced with a new assertion. The new `getReportAsFileInFormat` assertion allows storing past history in `window._$files` in a preferred format. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.support.RuleEngineOpaExtension) and the [Sample](https://sdk.openui5.org/sample/sap.ui.core.sample.OpaWithSupportAssistant/preview).

<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable / sap.ui.table.Table / sap.ui.table.TreeTable`** 



</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable / sap.ui.table.Table / sap.ui.table.TreeTable`**

You can now use more values for the `highlight` property. These values are provided by the `sap.ui.core.MessageType` and `sap.ui.core.IndicationColor` enumerations. To define a custom semantic for the highlight color, you can use the new `highlightText` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.RowSettings) for the `highlight` property.

<sub>Changed•Control•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
<tr>
<td valign="top">

1.62 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Demo Kit Improvements** 



</td>
<td valign="top">

**Demo Kit Improvements**

**Demo Kit Landing Page**

-   We added a block on the welcome page about the *UI5 Evolution* project. It contains a short description with a link to the interactive documentation page about the project. For more information, see [Best Practices for App Developers](Best_Practices_for_App_Developers_28fcd55.md).

-   We added a live code editor to the Demo Kit welcome page that showcases a simple app. You can edit the code directly and see your changes immediately in the *Result* area.

    ![](images/loiofbae7e8570c641a1837ac4d919832d30_HiRes.png)


**Settings Dialog in Samples Section**

You can now switch the *Content Density* of the Demo Kit samples to *Condensed*.

<sub>Changed•Feature•Info Only•1.62</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2019-01-31



</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_a93a6a3.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_f073d69.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_f94bf93.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_a6b1472.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_c9896e9.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_0f5acfd.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_0e30822.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_e8d9da7.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

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

