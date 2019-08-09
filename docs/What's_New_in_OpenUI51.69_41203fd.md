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

| **New Themes for SAP Fiori 3 User Experience** The High Contrast White \(HCW\) and High Contrast Black \(HCB\) themes \(`sap_fiori_3_hcw`/`sap_fiori_3_hcb`\) are now delivered with all SAP Fiori-related libraries. They offer a better visual experience for people with visual impairments.|
| **Require Modules in XML Views and Fragments** Modules can now be required in XML views and fragments and assigned to aliases which can be used as variables in properties, event handlers, and bindings. Such a declarative approach can help to avoid global variables and allows to reuse certain helper classes without a detour via Controller code. The new `require` attribute with namespace URI `sap.ui.core` can be used to define the module aliases and paths. This attribute can be used at every element of an XML view or fragment. You can specify a list of required modules as Unified Resource Names, similar to `sap.ui.require` and assign aliases to them using a JSON-like syntax. For details and examples, see [Require Modules in XML View and Fragment](Require_Modules_in_XML_View_and_Fragment_b11d853.md).|

***

<a name="loio41203fd3272b479d8c665357e3b21a43__section_qwl_pb5_zcb"/>

### Improved Features

| **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features: -   The original of a bound message is available in the message model as `technicalDetails.originalMessage`. This can be used to transport additional information.

-   When calling `sap.ui.model.odata.v4.Context.requestSideEffects`, you can now specify a group ID. You can use this to read side-effects that load slowly in a separate request. Note that you have to ensure in the application that no pending changes for the affected properties exist.

-   You can now use the Partner attribute of navigation properties to automatically shorten paths by removing Partner :n and :1 navigation properties that are adjacent in the path. This allows to access already available data in parent bindings.

-   The `caseSensitive` flag is now supported for `sap.ui.model.Filter`. Note that if case-insensitive filtering is requested, the OData function `tolower` is used for all operands.

-   To asynchronously access data in controller code through bindings, you can now use the `sap.ui.model.odata.v4.ODataContextBinding.requestObject` and `sap.ui.model.odata.v4.ODataPropertyBinding.requestValue` functions.


 > Note:
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and Fiori elements applications. Double check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).
> 
> 

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).|

***

<a name="loio41203fd3272b479d8c665357e3b21a43__section_rqn_wd5_zcb"/>

### Improved Controls

| **`sap.f.Avatar`** -   You can now set background color for the `Avatar` control through the new `backgroundColor` property. There are 10 predefined colors and an option to set a random one.

-   You can now set a border to be displayed for the `Avatar` by setting the new `showBorder` boolean property to `true`.


 For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.Avatar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.Avatar/sample/sap.f.sample.Avatar).|
| **`sap.m.Breadcrumbs`** You can now choose different separator styles to be displayed between the `Breadcrumbs` elements. You can set them through the new `separatorStyle` property.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Breadcrumbs) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Breadcrumbs/sample/sap.m.sample.Breadcrumbs). |
| **`sap.m.ListBase`, `sap.m.ListItemBase`** These controls now support a range selection with key combinations if the `MultiSelect` mode is set. For more information, see the *API Reference* for [`sap.m.ListBase`](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase) and [`sap.m.ListItemBase`](https://openui5.hana.ondemand.com/#/api/sap.m.ListItemBase). |
| **`sap.m.NavContainer`** We have improved the fade and slide animations when navigating forward and backward in `sap.m.NavContainer`.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.NavContainer/sample/sap.m.sample.NavContainer). |
|**`sap.m.QuickViewPage`**We have introduced a new `fallbackIcon` property. It allows you to define an icon that will be displayed in case of loading errors of the `icon`. The `fallbackIcon` should be part of the SAP icon font. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.QuickViewPage) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.QuickView/sample/sap.m.sample.QuickViewFallbackIcon).|
|**`sap.m.SearchField`**We have made some changes in the suggestions dialog for the `SearchField` control on mobile devices. The `Cancel` button is now moved to the top, next to the search field, and the button in the footer is changed from `Cancel` to `OK`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SearchField) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SearchField/sample/sap.m.sample.SearchFieldSuggestions).|
| **`sap.m.Select`** The items in the select list now have a maximum width. If the text of the items is longer than the maximum width, it either truncates or wraps on multiple lines depending on the new `wrapItemsText` property.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Select) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Select). |
| **`sap.m.SinglePlanningCalendar`** A new *Month* view is now available for the control. It displays a calendar month that always starts from the first week of the month. To set it up, use the new `sap.m.SinglePlanningCalendarMonthView` class in the `views` aggregation of the `SinglePlanningCalendar` control.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar). |
| **`sap.ui.table.plugins.MultiSelectionPlugin`** The plugin for the `sap.ui.table.AnalyticalTable`, the `sap.ui.table.Table`, and the `sap.ui.table.TreeTable` tables now offers various selection modes for applications \(new `selectionMode` property\), for example, the selection of single or multiple rows. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.plugins.MultiSelectionPlugin) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.table.Table/sample/sap.ui.table.sample.MultiSelectionPlugin). |
| **`sap.ui.unified.Calendar`** We have implemented year range in the `Calendar` control to help the user navigate quickly to a year that is outside the visible range. When the year button is selected, there's an additional year range button that enables the interaction.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.unified.Calendar). |

