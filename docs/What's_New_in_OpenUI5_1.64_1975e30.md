<!-- loio1975e304ab924fb3b799240fdd9fe59b -->

| loio |
| -----|
| 1975e304ab924fb3b799240fdd9fe59b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/1975e304ab924fb3b799240fdd9fe59b) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/1975e304ab924fb3b799240fdd9fe59b)</div>

## What's New in OpenUI5 1.64

With this release OpenUI5 is upgraded from version 1.63 to 1.64.

***

<a name="loio1975e304ab924fb3b799240fdd9fe59b__section_bkm_s15_zcb"/>

### New Controls

|**`sap.f.Card`**

The new `sap.f.Card` control complies with the visual design of the Integration Card \(`sap.ui.integration.widgets.Card`\). In contrast to the Integration Card, `sap.f.Card` provides more freedom in choosing the structure and the controls you can include, so that you can compose the card content area according to your needs. It enables you to decide and compose the card content area according to your needs.

The `sap.f.Card` consists of three elements: a container with background color and rounded corners, a header, and content areas.

 ![](loiob1ff765e1db44ae38f583bc228e14432_HiRes.png) 

For more information, see [Cards](Cards_5b46b03.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.Card) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.Card/sample/sap.f.sample.Card).

|

***

<a name="loio1975e304ab924fb3b799240fdd9fe59b__section_qwl_pb5_zcb"/>

### Improved Features

|**OpenUI5 OData V4 Model**

With the new version of the OpenUI5 OData V4 model, the number of decimal places of entered numbers is checked against the unit or the currency customizing when using the `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency` types that were introduced with SAPUI5 1.63.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).

|

***

<a name="loio1975e304ab924fb3b799240fdd9fe59b__section_rqn_wd5_zcb"/>

### Improved Controls

|**`sap.f.DynamicPage`**

We have redesigned the content area of the `DynamicPageTitle` control so that the width of the `expandedContent` and `snappedContent` aggregations no longer depends on the width of the `heading` aggregation. Both `expandedContent` and `snappedContent` aggregations can now take the whole width of the `DynamicPageTitle` and are displayed below the heading and content areas.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.DynamicPage/sample/sap.f.sample.DynamicPageFreeStyle).

|
|**`sap.f.ShellBar` \(Experimental\)**

We have implemented an additional element that visualizes the number of notifications for the app \(`notificationsNumber` property\). It is displayed at the top right corner of the notifications button. When the resize breakpoint is hit and the notifications button enters the overflow area of the `OverflowToolbar`, the element is displayed at the top right corner of both the `OverflowToolbarButton` and the overflow area notification button.

 ![](loio4ae1e3f40d754916a91d159216dd295f_HiRes.png) 

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.ShellBar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.ShellBar/sample/sap.f.sample.ShellBar).

|
|**`sap.m.ComboBox`**

We have introduced grouping in the suggestions list of `sap.m.ComboBox`. This feature allows you to group items by certain characteristics, and to display a header. New group can be created in two ways:

-   If data binding is used, grouping is defined on the sorter in data binding.
-   Alternatively, you can add a group header programmatically as an instance of `sap.ui.core.SeparatorItem` with a text property by adding it to the items aggregation of the `sap.m.ComboBox` control. This transforms the `sap.ui.core.SeparatorItem` internally to `sap.m.GroupHeaderListItem`, and uses the text value as the header of the group.

In case a `sap.ui.core.SeparatorItem` without a defined text property is inserted in the aggregation items, the ComboBox will display only a horizontal separator without any text. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ComboBox) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ComboBox/sample/sap.m.sample.ComboBoxGrouping).

|
|**`sap.m.DatePicker`**

With the new `isValidValue` function, you can receive information on the validity of the latest value provided in `sap.m.DatePicker`, not only on change but at any time, so that you can act upon an incorrectly entered date.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.DatePicker) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.DatePicker/sample/sap.m.sample.DatePicker).

|
|**`sap.m.Input`**, **`sap.m.ComboBoxBase`** **\(Experimental\)**

We have introduced a new experimental method `showItems(fnFilter)`. It enables you to open a popup with suggestion items for the `sap.m.Input`, `sap.m.ComboBox`, and `sap.m.MultiComboBox` controls, and to filter the available items based on custom criteria. For more information, see the API Reference \([`sap.m.Input`](https://openui5.hana.ondemand.com/#/api/sap.m.Input/methods/showItems), [`sap.m.ComboBoxBase`](https://openui5.hana.ondemand.com/#/api/sap.m.ComboBoxBase/methods/showItems)\).

|
|**`sap.m.Input`**, **`sap.m.MultiInput`**

We have introduced grouping for the suggestions of `sap.m.Input` and `sap.m.MultiInput`. This feature allows you to easily group items visually by separating the different groups via a distinguishable group header item. The functionality is available for inputs that use list suggestions and table suggestions. For more information, see the samples \( [`sap.m.Input`](https://openui5.hana.ondemand.com/#/entity/sap.m.Input/sample/sap.m.sample.InputGrouping), [`sap.m.MultiInput`](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiInput/sample/sap.m.sample.MultiInputGrouping)\).

|
|**`sap.m.SinglePlanningCalendar`**

-   We have introduced a new all-day logic that checks whether an appointment starts at 00:00 and ends at 00:00 on any day in the future.

-   We have introduced a cozy form factor, which provides larger interactive user interface elements. This facilitates your work with the control on mobile devices.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar).

|
|**`sap.ui.integration.widgets.Card`**

-   We have introduced a new `Object` card type, which displays the basic details for an object, such as a person or a sales order.For more information, see [Cards](Cards_5b46b03.md) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.ObjectCard).

-   We have introduced a new `Timeline` card type, which displays time-related content.For more information, see [Cards](Cards_5b46b03.md) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.TimelineCard).


|
|**`sap.uxap.ObjectPageLayout`**

We have implemented the option to provide a simple, single-line title that takes up less space on smaller phone screens when the dynamic header of the `ObjectPageLayout` control is collapsed \(snapped\). You can enable it via the `snappedTitleOnMobile` aggregation.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.uxap.ObjectPageDynamicHeaderTitle) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.uxap.ObjectPageLayout/sample/sap.uxap.sample.ObjectPageDynamicHeader).

|

***

<a name="loio1975e304ab924fb3b799240fdd9fe59b__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

|**API Reference**

-   The API Reference documentation for non-class entities now displays the `@see` and `@example` tags of their JSDocs.For a preview of an `@see` tag, see the [`sap.ui.core.LabelEnablement`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.LabelEnablement) namespace. For a preview of an `@example` tag, see the [`sap/base/util/merge`](https://openui5.hana.ondemand.com/#/api/module%3Asap%2Fbase%2Futil%2Fmerge) function.

-   Based on your feedback, we have improved the API Reference documentation to include the borrowed *Properties*, *Aggregations*, and *Associations* in the respective sections. All the inherited entries are marked with a *Borrowed from:* label in the *Description* column with a link to the corresponding class.

 ![](loiod7f2a71df7944a0cb574de845248690e_HiRes.png) 


|

