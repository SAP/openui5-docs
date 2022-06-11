<!-- loio1975e304ab924fb3b799240fdd9fe59b -->

| loio |
| -----|
| 1975e304ab924fb3b799240fdd9fe59b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/1975e304ab924fb3b799240fdd9fe59b) | [demo kit latest release](https://sdk.openui5.org/topic/1975e304ab924fb3b799240fdd9fe59b)</div>

## What's New in OpenUI5 1.64

With this release OpenUI5 is upgraded from version 1.63 to 1.64.

***

<a name="loio1975e304ab924fb3b799240fdd9fe59b__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td valign="top">

**`sap.f.Card`**

The new `sap.f.Card` control complies with the visual design of the Integration Card \(`sap.ui.integration.widgets.Card`\). In contrast to the Integration Card, `sap.f.Card` provides more freedom in choosing the structure and the controls you can include, so that you can compose the card content area according to your needs. It enables you to decide and compose the card content area according to your needs.

The `sap.f.Card` consists of three elements: a container with background color and rounded corners, a header, and content areas.

 ![](images/loiob1ff765e1db44ae38f583bc228e14432_HiRes.png) 

For more information, see [Cards](Cards_5b46b03.md), the [API Reference](https://sdk.openui5.org/api/sap.f.Card) and the [Sample](https://sdk.openui5.org/entity/sap.f.Card/sample/sap.f.sample.Card).



</td>
</tr>
</table>

***

<a name="loio1975e304ab924fb3b799240fdd9fe59b__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

With the new version of the OpenUI5 OData V4 model, the number of decimal places of entered numbers is checked against the unit or the currency customizing when using the `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency` types that were introduced with SAPUI5 1.63.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).



</td>
</tr>
</table>

***

<a name="loio1975e304ab924fb3b799240fdd9fe59b__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.f.DynamicPage`**

We have redesigned the content area of the `DynamicPageTitle` control so that the width of the `expandedContent` and `snappedContent` aggregations no longer depends on the width of the `heading` aggregation. Both `expandedContent` and `snappedContent` aggregations can now take the whole width of the `DynamicPageTitle` and are displayed below the heading and content areas.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.f.DynamicPage/sample/sap.f.sample.DynamicPageFreeStyle).



</td>
</tr>
<tr>
<td valign="top">

**`sap.f.ShellBar` \(Experimental\)**

We have implemented an additional element that visualizes the number of notifications for the app \(`notificationsNumber` property\). It is displayed at the top right corner of the notifications button. When the resize breakpoint is hit and the notifications button enters the overflow area of the `OverflowToolbar`, the element is displayed at the top right corner of both the `OverflowToolbarButton` and the overflow area notification button.

 ![](images/loio4ae1e3f40d754916a91d159216dd295f_HiRes.png) 

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.ShellBar) and the [Sample](https://sdk.openui5.org/entity/sap.f.ShellBar/sample/sap.f.sample.ShellBar).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.ComboBox`**

We have introduced grouping in the suggestions list of `sap.m.ComboBox`. This feature allows you to group items by certain characteristics, and to display a header. New group can be created in two ways:

-   If data binding is used, grouping is defined on the sorter in data binding.
-   Alternatively, you can add a group header programmatically as an instance of `sap.ui.core.SeparatorItem` with a text property by adding it to the items aggregation of the `sap.m.ComboBox` control. This transforms the `sap.ui.core.SeparatorItem` internally to `sap.m.GroupHeaderListItem`, and uses the text value as the header of the group.

In case a `sap.ui.core.SeparatorItem` without a defined text property is inserted in the aggregation items, the ComboBox will display only a horizontal separator without any text. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ComboBox) and the [Sample](https://sdk.openui5.org/entity/sap.m.ComboBox/sample/sap.m.sample.ComboBoxGrouping).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.DatePicker`**

With the new `isValidValue` function, you can receive information on the validity of the latest value provided in `sap.m.DatePicker`, not only on change but at any time, so that you can act upon an incorrectly entered date.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DatePicker) and the [Sample](https://sdk.openui5.org/entity/sap.m.DatePicker/sample/sap.m.sample.DatePicker).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Input`**, **`sap.m.ComboBoxBase`** **\(Experimental\)**

We have introduced a new experimental method `showItems(fnFilter)`. It enables you to open a popup with suggestion items for the `sap.m.Input`, `sap.m.ComboBox`, and `sap.m.MultiComboBox` controls, and to filter the available items based on custom criteria. For more information, see the API Reference \([`sap.m.Input`](https://sdk.openui5.org/api/sap.m.Input/methods/showItems), [`sap.m.ComboBoxBase`](https://sdk.openui5.org/api/sap.m.ComboBoxBase/methods/showItems)\).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Input`**, **`sap.m.MultiInput`**

We have introduced grouping for the suggestions of `sap.m.Input` and `sap.m.MultiInput`. This feature allows you to easily group items visually by separating the different groups via a distinguishable group header item. The functionality is available for inputs that use list suggestions and table suggestions. For more information, see the samples \( [`sap.m.Input`](https://sdk.openui5.org/entity/sap.m.Input/sample/sap.m.sample.InputGrouping), [`sap.m.MultiInput`](https://sdk.openui5.org/entity/sap.m.MultiInput/sample/sap.m.sample.MultiInputGrouping)\).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.SinglePlanningCalendar`**

-   We have introduced a new all-day logic that checks whether an appointment starts at 00:00 and ends at 00:00 on any day in the future.

-   We have introduced a cozy form factor, which provides larger interactive user interface elements. This facilitates your work with the control on mobile devices.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have introduced a new `Object` card type, which displays the basic details for an object, such as a person or a sales order.For more information, see [Cards](Cards_5b46b03.md) and the [Sample](https://sdk.openui5.org/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.ObjectCard).

-   We have introduced a new `Timeline` card type, which displays time-related content.For more information, see [Cards](Cards_5b46b03.md) and the [Sample](https://sdk.openui5.org/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.TimelineCard).




</td>
</tr>
<tr>
<td valign="top">

**`sap.uxap.ObjectPageLayout`**

We have implemented the option to provide a simple, single-line title that takes up less space on smaller phone screens when the dynamic header of the `ObjectPageLayout` control is collapsed \(snapped\). You can enable it via the `snappedTitleOnMobile` aggregation.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageDynamicHeaderTitle) and the [Sample](https://sdk.openui5.org/entity/sap.uxap.ObjectPageLayout/sample/sap.uxap.sample.ObjectPageDynamicHeader).



</td>
</tr>
</table>

***

<a name="loio1975e304ab924fb3b799240fdd9fe59b__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td valign="top">

**API Reference**

-   The API Reference documentation for non-class entities now displays the `@see` and `@example` tags of their JSDocs.For a preview of an `@see` tag, see the [`sap.ui.core.LabelEnablement`](https://sdk.openui5.org/api/sap.ui.core.LabelEnablement) namespace. For a preview of an `@example` tag, see the [`sap/base/util/merge`](https://sdk.openui5.org/api/module%3Asap%2Fbase%2Futil%2Fmerge) function.

-   Based on your feedback, we have improved the API Reference documentation to include the borrowed *Properties*, *Aggregations*, and *Associations* in the respective sections. All the inherited entries are marked with a *Borrowed from:* label in the *Description* column with a link to the corresponding class.

     ![](images/loiod7f2a71df7944a0cb574de845248690e_HiRes.png) 




</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_5a18410.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_5deb78f.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_5e35c25.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_7aacb4e.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_f21858f.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_b39a11b.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_1b09465.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_067e2fb.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_eeb5bd9.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_ccf76b7.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_f081cf0.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f71563c.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_d176be3.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_2ec6b6b.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_b9b0a3f.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_21fc6cb.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_7b82664.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_25e5326.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_609fd01.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_4e89fee.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_41203fd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_5531aef.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_0968958.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_ebe7fda.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_9d2b189.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_77e1dcc.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_27eea38.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_de4d50b.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_2a70354.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_b28edde.md "With this release, OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_53b4b5e.md "With this release, OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

