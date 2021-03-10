<!-- loio27eea38eeb7b40d19d0dfe3ddf513175 -->

| loio |
| -----|
| 27eea38eeb7b40d19d0dfe3ddf513175 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/27eea38eeb7b40d19d0dfe3ddf513175) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/27eea38eeb7b40d19d0dfe3ddf513175)</div>

## What's New in OpenUI5 1.62

With this release OpenUI5 is upgraded from version 1.61 to 1.62.

***

<a name="loio27eea38eeb7b40d19d0dfe3ddf513175__section_bkm_s15_zcb"/>

### New Controls

| **`sap.m.GenericTag`**

 The new `sap.m.GenericTag` control displays complimentary information related to the current page, such as key performance indicators \(KPI\) and situations.

  ![](loio7fe88c577d264962b6bec8427efc968d_HiRes.png) 

 It consists of four different parts:

 -   A required status indicator with semantic colors \(A\)

-   An optional icon that is displayed in the same color as the status indicator \(B\)

-   A required text that is truncated automatically \(C\)

-   An optional content area that can display either a control of type `sap.m.ObjectNumber` or a warning icon \(D\)


  ![](loiofb7c92bd4aca46a2abb579058c481ded_HiRes.png) 

 The control can move to the overflow area of `sap.m.OverflowToolbar`.

 For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.GenericTag) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.GenericTag).

 |
|**`sap.ui.integration.widgets.Card`**

A card is a user experience design pattern that displays the most concise pieces of information in a limited-space container. It helps users structure their work in an intuitive and dynamic way.

  
  
<a name="loio27eea38eeb7b40d19d0dfe3ddf513175__fig_pfj_mhs_5fb"/>Analytical card ![](loio3ff4cbace0714a71924a628d8c81d480_LowRes.png "Analytical card") 

Using cards, you can group information, link additional details, and present a summary. You can also get direct insights without leaving the current screen and choose further navigation options. Each card is designed in a different style and contains various content formats.

-   The List card is used to display multiple list items of all kinds.

-   The Analytical card is used for data visualization with various chart types.


Cards can be used by referencing the `sap.ui.integration` library.`sap.ui.integration.widgets.Card` is a self-contained user interface element, connected to a manifest and used as a widget.

For more information, see [Cards](Cards_5b46b03.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.integration.widgets.Card), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.integration.widgets.Card).

|

***

<a name="loio27eea38eeb7b40d19d0dfe3ddf513175__section_qwl_pb5_zcb"/>

### Improved Features

| **Routing in Nested Components**

 OpenUI5 routing now supports navigation to components in addition to the already existing routing to views. You configure the routing in the component’s manifest. Moreover, the target component can also come with its own routing, which integrates via enhanced configuration in the manifest.

 For details, see [Enabling Routing in Nested Components](Enabling_Routing_in_Nested_Components_fb19f50.md).

 |
| **OpenUI5 OData V4 Model**

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


 > Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).

 |

***

<a name="loio27eea38eeb7b40d19d0dfe3ddf513175__section_rqn_wd5_zcb"/>

### Improved Controls

| **`sap.m.Carousel`**

 The control can now display several items at once. This functionality is implemented through a new `customLayout` aggregation of type `sap.m.CarouselLayout`. The `sap.m.CarouselLayout` defines how many items are displayed in the visible area of the `sap.m.Carousel` control and has a `visiblePagesCount` property, which determines the count of items to be displayed.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Carousel) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.CarouselWithMorePages/preview).

 |
| `**`sap.m.Column`**`

 The `sortIndicator` property now shows a sort icon when a column is sorted. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Column) for the `sortIndicator` property.

 |
| **`sap.m.ComboBox`**

 In order for the `ComboBox` to be aligned with the rest of the input controls and the already available features, we updated the used list structure of the control from `sap.m.SelectList` to `sap.m.List`, and respectively updated the protected API `getList`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ComboBox).

 |
| `**sap.m.ListBase**`

 You can now use more values for the `highlight` property. These values are provided by the `sap.ui.core.MessageType` and `sap.ui.core.IndicationColor` enumerations. To define a custom semantic for the highlight color, you can use the new `highlightText` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ListItemBase/controlProperties) for the `highlight` property.

 |
| **`sap.m.OverflowToolbar`**

 -   We extended the `sap.m.sample.OverflowToolbarSimple` sample to demonstrate the behavior of grouped controls. It contains two pairs of grouped controls: `Label` with `Input` and `Label` with `Select`.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.OverflowToolbarSimple/preview).

-   The `sap.m.OverflowToolbar` now allows `sap.m.GenericTag` to move into the overflow area.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.OverflowToolbarSimple/preview).


 |
| **`sap.m.SinglePlanningCalendar`**

 -   You can now select or deselect single appointments either by clicking or tapping on the appointment or by using the keyboard arrow keys to navigate to the appointment and then select or deselect it by pressing the space bar or the *Enter* key. You can enter multi-selection mode using key combinations \(for example, *Ctrl + click* for Microsoft Windows Operating Systems or *Cmd + click* for Mac Operating Systems\).

-   The `sap.m.SinglePlanningCalendar` now has a new `stickyMode` property which allows users to select which toolbars will be fixed while scrolling.


 For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar).

 |
| `**sap.m.StandardListItem**`

 The new `information` value in the `sap.ui.core.ValueState` enumeration is now supported by the `infoState` property of `StandardListItem`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.StandardListItem/methods/getInfoState).

 |
| **`sap.tnt.SideNavigation`**

 We have implemented a `selectedKey` property of `sap.tnt.SideNavigation`, with which you can easily set the selected item, when the control is bound to a model. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.tnt.SideNavigation) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.tnt.sample.ToolPage/preview).

 |
| **`sap.ui.core.support.RuleEngineOpaExtension`**

 The rule engine OPA extension, which allows Support Assistant checks, has been enhanced with a new assertion. The new `getReportAsFileInFormat` assertion allows storing past history in `window._$files` in a preferred format. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.support.RuleEngineOpaExtension) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.core.sample.OpaWithSupportAssistant/preview).

 |
| **`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`**

 You can now use more values for the `highlight` property. These values are provided by the `sap.ui.core.MessageType` and `sap.ui.core.IndicationColor` enumerations. To define a custom semantic for the highlight color, you can use the new `highlightText` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.RowSettings) for the `highlight` property.

 |

***

<a name="loio27eea38eeb7b40d19d0dfe3ddf513175__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

| **Demo Kit Landing Page**

 -   We added a block on the welcome page about the *UI5 Evolution* project. It contains a short description with a link to the interactive documentation page about the project. For more information, see [Best Practices for App Developers](Best_Practices_for_App_Developers_28fcd55.md).

-   We added a live code editor to the Demo Kit welcome page that showcases a simple app. You can edit the code directly and see your changes immediately in the *Result* area.

![](loiofbae7e8570c641a1837ac4d919832d30_HiRes.png)


 |
| **Settings Dialog in Samples Section**

 You can now switch the *Content Density* of the Demo Kit samples to *Condensed*.

 |

