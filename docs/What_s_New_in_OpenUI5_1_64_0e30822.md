<!-- loio0e30822c3b644a73836abba65736fc5e -->

| loio |
| -----|
| 0e30822c3b644a73836abba65736fc5e |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/0e30822c3b644a73836abba65736fc5e) | [demo kit latest release](https://sdk.openui5.org/topic/0e30822c3b644a73836abba65736fc5e)</div>

## What's New in OpenUI5 1.64

With this release OpenUI5 is upgraded from version 1.63 to 1.64.

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

1.64 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.Card`** 

</td>
<td valign="top">

**`sap.f.Card`**

The new `sap.f.Card` control complies with the visual design of the Integration Card \(`sap.ui.integration.widgets.Card`\). In contrast to the Integration Card, `sap.f.Card` provides more freedom in choosing the structure and the controls you can include, so that you can compose the card content area according to your needs. It enables you to decide and compose the card content area according to your needs.

The `sap.f.Card` consists of three elements: a container with background color and rounded corners, a header, and content areas.

![](images/loiob1ff765e1db44ae38f583bc228e14432_HiRes.png)

For more information, see [Cards](Cards_5b46b03.md), the [API Reference](https://sdk.openui5.org/api/sap.f.Card) and the [Sample](https://sdk.openui5.org/entity/sap.f.Card/sample/sap.f.sample.Card).

<sub>New•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

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

With the new version of the OpenUI5 OData V4 model, the number of decimal places of entered numbers is checked against the unit or the currency customizing when using the `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency` types that were introduced with SAPUI5 1.63.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.DynamicPage`** 

</td>
<td valign="top">

**`sap.f.DynamicPage`**

We have redesigned the content area of the `DynamicPageTitle` control so that the width of the `expandedContent` and `snappedContent` aggregations no longer depends on the width of the `heading` aggregation. Both `expandedContent` and `snappedContent` aggregations can now take the whole width of the `DynamicPageTitle` and are displayed below the heading and content areas.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.f.DynamicPage/sample/sap.f.sample.DynamicPageFreeStyle).

<sub>Changed•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.ShellBar` \(Experimental\)** 

</td>
<td valign="top">

**`sap.f.ShellBar` \(Experimental\)**

We have implemented an additional element that visualizes the number of notifications for the app \(`notificationsNumber` property\). It is displayed at the top right corner of the notifications button. When the resize breakpoint is hit and the notifications button enters the overflow area of the `OverflowToolbar`, the element is displayed at the top right corner of both the `OverflowToolbarButton` and the overflow area notification button.

![](images/loio4ae1e3f40d754916a91d159216dd295f_HiRes.png)

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.ShellBar) and the [Sample](https://sdk.openui5.org/entity/sap.f.ShellBar/sample/sap.f.sample.ShellBar).

<sub>Changed•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

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

We have introduced grouping in the suggestions list of `sap.m.ComboBox`. This feature allows you to group items by certain characteristics, and to display a header. New group can be created in two ways:

-   If data binding is used, grouping is defined on the sorter in data binding.
-   Alternatively, you can add a group header programmatically as an instance of `sap.ui.core.SeparatorItem` with a text property by adding it to the items aggregation of the `sap.m.ComboBox` control. This transforms the `sap.ui.core.SeparatorItem` internally to `sap.m.GroupHeaderListItem`, and uses the text value as the header of the group.

In case a `sap.ui.core.SeparatorItem` without a defined text property is inserted in the aggregation items, the ComboBox will display only a horizontal separator without any text.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ComboBox) and the [Sample](https://sdk.openui5.org/entity/sap.m.ComboBox/sample/sap.m.sample.ComboBoxGrouping). 

<sub>Changed•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.DatePicker`** 

</td>
<td valign="top">

**`sap.m.DatePicker`**

With the new `isValidValue` function, you can receive information on the validity of the latest value provided in `sap.m.DatePicker`, not only on change but at any time, so that you can act upon an incorrectly entered date.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DatePicker) and the [Sample](https://sdk.openui5.org/entity/sap.m.DatePicker/sample/sap.m.sample.DatePicker).

<sub>Changed•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Input / sap.m.ComboBoxBase` \(Experimental\)** 

</td>
<td valign="top">

**`sap.m.Input / sap.m.ComboBoxBase` \(Experimental\)**

We have introduced a new experimental method `showItems(fnFilter)`. It enables you to open a popup with suggestion items for the `sap.m.Input`, `sap.m.ComboBox`, and `sap.m.MultiComboBox` controls, and to filter the available items based on custom criteria.For more information, see the API Reference \([`sap.m.Input`](https://sdk.openui5.org/api/sap.m.Input/methods/showItems), [`sap.m.ComboBoxBase`](https://sdk.openui5.org/api/sap.m.ComboBoxBase/methods/showItems)\).

<sub>Changed•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Input / sap.m.MultiInput`** 

</td>
<td valign="top">

**`sap.m.Input / sap.m.MultiInput`**

We have introduced grouping for the suggestions of `sap.m.Input` and `sap.m.MultiInput`. This feature allows you to easily group items visually by separating the different groups via a distinguishable group header item. The functionality is available for inputs that use list suggestions and table suggestions.For more information, see the samples \( [`sap.m.Input`](https://sdk.openui5.org/entity/sap.m.Input/sample/sap.m.sample.InputGrouping), [`sap.m.MultiInput`](https://sdk.openui5.org/entity/sap.m.MultiInput/sample/sap.m.sample.MultiInputGrouping)\).

<sub>Changed•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

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

-   We have introduced a new all-day logic that checks whether an appointment starts at 00:00 and ends at 00:00 on any day in the future.

-   We have introduced a cozy form factor, which provides larger interactive user interface elements. This facilitates your work with the control on mobile devices.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

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

-   We have introduced a new `Object` card type, which displays the basic details for an object, such as a person or a sales order.For more information, see [Cards](Cards_5b46b03.md) and the [Sample](https://sdk.openui5.org/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.ObjectCard).

-   We have introduced a new `Timeline` card type, which displays time-related content.For more information, see [Cards](Cards_5b46b03.md) and the [Sample](https://sdk.openui5.org/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.TimelineCard).


<sub>Changed•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.uxap.ObjectPageLayout`** 

</td>
<td valign="top">

**`sap.uxap.ObjectPageLayout`**

We have implemented the option to provide a simple, single-line title that takes up less space on smaller phone screens when the dynamic header of the `ObjectPageLayout` control is collapsed \(snapped\). You can enable it via the `snappedTitleOnMobile` aggregation.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageDynamicHeaderTitle) and the [Sample](https://sdk.openui5.org/entity/sap.uxap.ObjectPageLayout/sample/sap.uxap.sample.ObjectPageDynamicHeader).

<sub>Changed•Control•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
<tr>
<td valign="top">

1.64 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit API Reference** 

</td>
<td valign="top">

**Demo Kit API Reference**

-   The API Reference documentation for non-class entities now displays the `@see` and `@example` tags of their JSDocs.For a preview of an `@see` tag, see the [`sap.ui.core.LabelEnablement`](https://sdk.openui5.org/api/sap.ui.core.LabelEnablement) namespace. For a preview of an `@example` tag, see the [`sap/base/util/merge`](https://sdk.openui5.org/api/module%3Asap%2Fbase%2Futil%2Fmerge) function.

-   Based on your feedback, we have improved the API Reference documentation to include the borrowed *Properties*, *Aggregations*, and *Associations* in the respective sections. All the inherited entries are marked with a *Borrowed from:* label in the *Description* column with a link to the corresponding class.

    ![](images/loiod7f2a71df7944a0cb574de845248690e_HiRes.png)


<sub>Changed•Feature•Info Only•1.64</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-03-28

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_a93a6a3.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_f073d69.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_f94bf93.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_a6b1472.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_c9896e9.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_0f5acfd.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

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

