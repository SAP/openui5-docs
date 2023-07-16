<!-- loio89a18bd5d8574cbd8dd0a2da7023f597 -->

| loio |
| -----|
| 89a18bd5d8574cbd8dd0a2da7023f597 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/89a18bd5d8574cbd8dd0a2da7023f597) | [demo kit latest release](https://sdk.openui5.org/topic/89a18bd5d8574cbd8dd0a2da7023f597)</div>

## What's New in OpenUI5 1.69

With this release OpenUI5 is upgraded from version 1.68 to 1.69.

** **


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

 1.69 



</td>
<td valign="top">

 New 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **New Themes for SAP Fiori 3 User Experience** 



</td>
<td valign="top">

**New Themes for SAP Fiori 3 User Experience**

The High Contrast White \(HCW\) and High Contrast Black \(HCB\) themes \(`sap_fiori_3_hcw`/`sap_fiori_3_hcb`\) are now delivered with all SAP Fiori-related libraries. They offer a better visual experience for people with visual impairments.

<sub>New•Feature•Info Only•1.69</sub>



</td>
<td valign="top">

Info Only



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



</td>
<td valign="top">

 New 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Require Modules in XML Views and Fragments** 



</td>
<td valign="top">

**Require Modules in XML Views and Fragments**

Modules can now be required in XML views and fragments and assigned to aliases which can be used as variables in properties, event handlers, and bindings. Such a declarative approach can help to avoid global variables and allows to reuse certain helper classes without a detour via Controller code.

The new `require` attribute with namespace URI `sap.ui.core` can be used to define the module aliases and paths. This attribute can be used at every element of an XML view or fragment. You can specify a list of required modules as Unified Resource Names, similar to `sap.ui.require` and assign aliases to them using a JSON-like syntax.

For details and examples, see [Require Modules in XML View and Fragment](Require_Modules_in_XML_View_and_Fragment_b11d853.md).

<sub>New•Feature•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



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

-   The original of a bound message is available in the message model as `technicalDetails.originalMessage`. This can be used to transport additional information.

-   When calling `sap.ui.model.odata.v4.Context.requestSideEffects`, you can now specify a group ID. You can use this to read side-effects that load slowly in a separate request. Note that you have to ensure in the application that no pending changes for the affected properties exist.

-   You can now use the Partner attribute of navigation properties to automatically shorten paths by removing Partner :n and :1 navigation properties that are adjacent in the path. This allows to access already available data in parent bindings.

-   The `caseSensitive` flag is now supported for `sap.ui.model.Filter`. Note that if case-insensitive filtering is requested, the OData function `tolower` is used for all operands.

-   To asynchronously access data in controller code through bindings, you can now use the `sap.ui.model.odata.v4.ODataContextBinding.requestObject` and `sap.ui.model.odata.v4.ODataPropertyBinding.requestValue` functions.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and Fiori elements applications. Double check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



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

-   You can now set background color for the `Avatar` control through the new `backgroundColor` property. There are 10 predefined colors and an option to set a random one.

-   You can now set a border to be displayed for the `Avatar` by setting the new `showBorder` boolean property to `true`.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.Avatar) and the [Sample](https://sdk.openui5.org/entity/sap.f.Avatar/sample/sap.f.sample.Avatar).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.Breadcrumbs`** 



</td>
<td valign="top">

**`sap.m.Breadcrumbs`**

You can now choose different separator styles to be displayed between the `Breadcrumbs` elements. You can set them through the new `separatorStyle` property.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Breadcrumbs) and the [Sample](https://sdk.openui5.org/entity/sap.m.Breadcrumbs/sample/sap.m.sample.Breadcrumbs).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.ListBase` / `sap.m.ListItemBase`** 



</td>
<td valign="top">

**`sap.m.ListBase` / `sap.m.ListItemBase`**

These controls now support a range selection with key combinations if the `MultiSelect` mode is set. For more information, see the *API Reference* for [`sap.m.ListBase`](https://sdk.openui5.org/api/sap.m.ListBase) and [`sap.m.ListItemBase`](https://sdk.openui5.org/api/sap.m.ListItemBase).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.NavContainer`** 



</td>
<td valign="top">

**`sap.m.NavContainer`**

We have improved the fade and slide animations when navigating forward and backward in `sap.m.NavContainer`.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.NavContainer/sample/sap.m.sample.NavContainer).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.QuickViewPage`** 



</td>
<td valign="top">

**`sap.m.QuickViewPage`**

We have introduced a new `fallbackIcon` property. It allows you to define an icon that will be displayed in case of loading errors of the `icon`. The `fallbackIcon` should be part of the SAP icon font. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.QuickViewPage) and the [Sample](https://sdk.openui5.org/entity/sap.m.QuickView/sample/sap.m.sample.QuickViewFallbackIcon).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.SearchField`** 



</td>
<td valign="top">

**`sap.m.SearchField`**

We have made some changes in the suggestions dialog for the `SearchField` control on mobile devices. The `Cancel` button is now moved to the top, next to the search field, and the button in the footer is changed from `Cancel` to `OK`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SearchField) and the [Sample](https://sdk.openui5.org/entity/sap.m.SearchField/sample/sap.m.sample.SearchFieldSuggestions).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



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

The items in the select list now have a maximum width. If the text of the items is longer than the maximum width, it either truncates or wraps on multiple lines depending on the new `wrapItemsText` property.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Select) and the [Samples](https://sdk.openui5.org/entity/sap.m.Select).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



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

A new *Month* view is now available for the control. It displays a calendar month that always starts from the first week of the month. To set it up, use the new `sap.m.SinglePlanningCalendarMonthView` class in the `views` aggregation of the `SinglePlanningCalendar` control.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.ui.table.plugins.MultiSelectionPlugin`** 



</td>
<td valign="top">

**`sap.ui.table.plugins.MultiSelectionPlugin`**

The plugin for the `sap.ui.table.AnalyticalTable`, the `sap.ui.table.Table`, and the `sap.ui.table.TreeTable` tables now offers various selection modes for applications \(new `selectionMode` property\), for example, the selection of single or multiple rows. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.plugins.MultiSelectionPlugin) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.MultiSelectionPlugin).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
<tr>
<td valign="top">

 1.69 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.ui.unified.Calendar`** 



</td>
<td valign="top">

**`sap.ui.unified.Calendar`**

We have implemented year range in the `Calendar` control to help the user navigate quickly to a year that is outside the visible range. When the year button is selected, there's an additional year range button that enables the interaction.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.unified.Calendar).

<sub>Changed•Control•Info Only•1.69</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-08-15



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

