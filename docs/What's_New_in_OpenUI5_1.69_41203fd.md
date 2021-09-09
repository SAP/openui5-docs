<!-- loio41203fd3272b479d8c665357e3b21a43 -->

| loio |
| -----|
| 41203fd3272b479d8c665357e3b21a43 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/41203fd3272b479d8c665357e3b21a43) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/41203fd3272b479d8c665357e3b21a43)</div>

## What's New in OpenUI5 1.69

With this release OpenUI5 is upgraded from version 1.68 to 1.69.

***

<a name="loio41203fd3272b479d8c665357e3b21a43__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td>

**New Themes for SAP Fiori 3 User Experience**

The High Contrast White \(HCW\) and High Contrast Black \(HCB\) themes \(`sap_fiori_3_hcw`/`sap_fiori_3_hcb`\) are now delivered with all SAP Fiori-related libraries. They offer a better visual experience for people with visual impairments.



</td>
</tr>
<tr>
<td>

**Require Modules in XML Views and Fragments**

Modules can now be required in XML views and fragments and assigned to aliases which can be used as variables in properties, event handlers, and bindings. Such a declarative approach can help to avoid global variables and allows to reuse certain helper classes without a detour via Controller code.

The new `require` attribute with namespace URI `sap.ui.core` can be used to define the module aliases and paths. This attribute can be used at every element of an XML view or fragment. You can specify a list of required modules as Unified Resource Names, similar to `sap.ui.require` and assign aliases to them using a JSON-like syntax.

For details and examples, see [Require Modules in XML View and Fragment](Require_Modules_in_XML_View_and_Fragment_b11d853.md).



</td>
</tr>
</table>

***

<a name="loio41203fd3272b479d8c665357e3b21a43__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The original of a bound message is available in the message model as `technicalDetails.originalMessage`. This can be used to transport additional information.

-   When calling `sap.ui.model.odata.v4.Context.requestSideEffects`, you can now specify a group ID. You can use this to read side-effects that load slowly in a separate request. Note that you have to ensure in the application that no pending changes for the affected properties exist.

-   You can now use the Partner attribute of navigation properties to automatically shorten paths by removing Partner :n and :1 navigation properties that are adjacent in the path. This allows to access already available data in parent bindings.

-   The `caseSensitive` flag is now supported for `sap.ui.model.Filter`. Note that if case-insensitive filtering is requested, the OData function `tolower` is used for all operands.

-   To asynchronously access data in controller code through bindings, you can now use the `sap.ui.model.odata.v4.ODataContextBinding.requestObject` and `sap.ui.model.odata.v4.ODataPropertyBinding.requestValue` functions.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and Fiori elements applications. Double check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).



</td>
</tr>
</table>

***

<a name="loio41203fd3272b479d8c665357e3b21a43__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

**`sap.f.Avatar`**

-   You can now set background color for the `Avatar` control through the new `backgroundColor` property. There are 10 predefined colors and an option to set a random one.

-   You can now set a border to be displayed for the `Avatar` by setting the new `showBorder` boolean property to `true`.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.Avatar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.Avatar/sample/sap.f.sample.Avatar).



</td>
</tr>
<tr>
<td>

**`sap.m.Breadcrumbs`**

You can now choose different separator styles to be displayed between the `Breadcrumbs` elements. You can set them through the new `separatorStyle` property.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Breadcrumbs) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Breadcrumbs/sample/sap.m.sample.Breadcrumbs).



</td>
</tr>
<tr>
<td>

**`sap.m.ListBase`, `sap.m.ListItemBase`**

These controls now support a range selection with key combinations if the `MultiSelect` mode is set. For more information, see the *API Reference* for [`sap.m.ListBase`](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase) and [`sap.m.ListItemBase`](https://openui5.hana.ondemand.com/#/api/sap.m.ListItemBase).



</td>
</tr>
<tr>
<td>

**`sap.m.NavContainer`**

We have improved the fade and slide animations when navigating forward and backward in `sap.m.NavContainer`.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.NavContainer/sample/sap.m.sample.NavContainer).



</td>
</tr>
<tr>
<td>

**`sap.m.QuickViewPage`**

We have introduced a new `fallbackIcon` property. It allows you to define an icon that will be displayed in case of loading errors of the `icon`. The `fallbackIcon` should be part of the SAP icon font. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.QuickViewPage) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.QuickView/sample/sap.m.sample.QuickViewFallbackIcon).



</td>
</tr>
<tr>
<td>

**`sap.m.SearchField`**

We have made some changes in the suggestions dialog for the `SearchField` control on mobile devices. The `Cancel` button is now moved to the top, next to the search field, and the button in the footer is changed from `Cancel` to `OK`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SearchField) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SearchField/sample/sap.m.sample.SearchFieldSuggestions).



</td>
</tr>
<tr>
<td>

**`sap.m.Select`**

The items in the select list now have a maximum width. If the text of the items is longer than the maximum width, it either truncates or wraps on multiple lines depending on the new `wrapItemsText` property.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Select) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Select).



</td>
</tr>
<tr>
<td>

**`sap.m.SinglePlanningCalendar`**

A new *Month* view is now available for the control. It displays a calendar month that always starts from the first week of the month. To set it up, use the new `sap.m.SinglePlanningCalendarMonthView` class in the `views` aggregation of the `SinglePlanningCalendar` control.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar).



</td>
</tr>
<tr>
<td>

**`sap.ui.table.plugins.MultiSelectionPlugin`**

The plugin for the `sap.ui.table.AnalyticalTable`, the `sap.ui.table.Table`, and the `sap.ui.table.TreeTable` tables now offers various selection modes for applications \(new `selectionMode` property\), for example, the selection of single or multiple rows. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.plugins.MultiSelectionPlugin) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.table.Table/sample/sap.ui.table.sample.MultiSelectionPlugin).



</td>
</tr>
<tr>
<td>

**`sap.ui.unified.Calendar`**

We have implemented year range in the `Calendar` control to help the user navigate quickly to a year that is outside the visible range. When the year button is selected, there's an additional year range button that enables the interaction.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.unified.Calendar).



</td>
</tr>
</table>

**Parent topicColonSymbol** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.93](What's_New_in_OpenUI5_1.93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What's_New_in_OpenUI5_1.92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What's_New_in_OpenUI5_1.91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What's_New_in_OpenUI5_1.90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What's_New_in_OpenUI5_1.89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What's_New_in_OpenUI5_1.88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What's_New_in_OpenUI5_1.87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What's_New_in_OpenUI5_1.86_067e2fb.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What's_New_in_OpenUI5_1.85_eeb5bd9.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What's_New_in_OpenUI5_1.84_ccf76b7.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What's_New_in_OpenUI5_1.82_f081cf0.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What's_New_in_OpenUI5_1.81_f71563c.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What's_New_in_OpenUI5_1.80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What's_New_in_OpenUI5_1.79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What's_New_in_OpenUI5_1.78_d176be3.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What's_New_in_OpenUI5_1.77_2ec6b6b.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What's_New_in_OpenUI5_1.76_b9b0a3f.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What's_New_in_OpenUI5_1.75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What's_New_in_OpenUI5_1.74_21fc6cb.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What's_New_in_OpenUI5_1.73_7b82664.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What's_New_in_OpenUI5_1.72_25e5326.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What's_New_in_OpenUI5_1.71_609fd01.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What's_New_in_OpenUI5_1.70_4e89fee.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.68](What's_New_in_OpenUI5_1.68_5531aef.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What's_New_in_OpenUI5_1.67_0968958.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What's_New_in_OpenUI5_1.66_ebe7fda.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What's_New_in_OpenUI5_1.65_9d2b189.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What's_New_in_OpenUI5_1.64_1975e30.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What's_New_in_OpenUI5_1.63_77e1dcc.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What's_New_in_OpenUI5_1.62_27eea38.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What's_New_in_OpenUI5_1.61_de4d50b.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What's_New_in_OpenUI5_1.60_2a70354.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What's_New_in_OpenUI5_1.58_b28edde.md "With this release, OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What's_New_in_OpenUI5_1.56_53b4b5e.md "With this release, OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What's_New_in_OpenUI5_1.54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What's_New_in_OpenUI5_1.52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What's_New_in_OpenUI5_1.50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What's_New_in_OpenUI5_1.48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What's_New_in_OpenUI5_1.46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What's_New_in_OpenUI5_1.44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What's_New_in_OpenUI5_1.42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What's_New_in_OpenUI5_1.40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What's_New_in_OpenUI5_1.38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

