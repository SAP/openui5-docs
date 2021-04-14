<!-- loio05ce1dc72c74475bada39234f6721f21 -->

| loio |
| -----|
| 05ce1dc72c74475bada39234f6721f21 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/05ce1dc72c74475bada39234f6721f21) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/05ce1dc72c74475bada39234f6721f21)</div>

## What's New in OpenUI5 1.44

With this release, OpenUI5 is upgraded from version 1.42 to 1.44.

***

### Improved Features

***

#### Navigation and Routing

In the routing configuration, you can now define a `homeRoute` for the generic home page of the app. This is always the first history entry when a user navigates to a view of the app via deep link navigation. For more information, see [Routing Configuration](Routing_Configuration_9023130.md).

***

#### Formatting and Parsing of Week Info for All Calendar Types

The calculation of calendar weeks is now based on minimal days in first week coming from Unicode Common Locale Data Repository \(CLDR\) data.

***

#### OpenUI5 OData V4 Model

The new version of the OpenUI5 OData V4 model introduces the following features:

-   Creating entities

-   Initial version of the V4 AnnotationHelper \(`sap.ui.model.odata.v4.AnnotationHelper`\)

-   Computed annotations in XML Templating with OData V4

-   Forwarding the `$apply` binding parameter


> Caution:  
> **Incompatibility Due to Bug Fix**
> 
> The following bug has been reported: If you call the [sap.ui.model.odata.v4.Context\#getObject\(\)](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/getObject) or the [sap.ui.model.odata.v4.Context\#requestObject\(\)](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/requestObject) methods without a parameter, the expected and documented behavior is that the same result is returned as if the parameter `sPath=""` had been specified. Due to the bug, however, the return value wraps the expected output which can then only be accessed via `.value[0]`, for example `oContext.getObject().value[0]`.
> 
> **If you have used this workaround, your application will break starting with OpenUI5 version 1.44.6.**
> 
> **Solution**: If your application needs to run with both, the fixed and unfixed versions of OpenUI5, specify the `sPath=""` parameter, for example `oContext.getObject("")`. If your application runs on OpenUI5 1.44.7 or higher, you do **not** need to specify the `sPath` parameter. In both cases, you **must not** use the workaround with `.value[0]` any longer.

> Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies controls such as `TreeTable` and `AnalyticalTable` which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

***

#### OData V2 Model

For OData V2 models, the V2 annotation `‘sap:visible=”false”’` is now also converted to V4 annotation `‘"com.sap.vocabularies.UI.v1.Hidden" : { "Bool" : "true" }’`. The old V4 annotation `‘"com.sap.vocabularies.Common.v1.FieldControl": { "EnumMember" : "com.sap.vocabularies.Common.v1.FieldControlType/Hidden" }’` has been deprecated. For more information, see [Meta Model for OData V2](OData_V2_Model_6c47b2b.md#loio341823349ed04df1813197f2a0d71db2) and the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.ODataMetaModel). 

***

#### One Page Acceptance Tests \(OPA5\)

You can now check for empty aggregations in your OPA test with the `AggregationEmpty` matcher. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.test.matchers.AggregationEmpty).

***

### Improved Controls

-   `sap.f.DynamicPage`: Using the new property `toggleHeaderOnTitleClick`, you can now disable the feature to expand and collapse the `DynamicPageHeader` with a title click . The default value for this property is set to `true` so that any existing apps using the `DynamicPage` control are not affected. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPage) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.DynamicPageListReport/preview).

-   `sap.m.Dialog`: We have enabled custom handling for the *Close* button. App developers can check for unsaved changes and prevent the dialog from being closed. This is done with the new property `escapeHandler` of type function. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Dialog/methods/getEscapeHandler) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.Dialog/preview).

-   `sap.m.GenericTile`: With the new `LineMode`, you can switch the visualization of the Generic Tile on a web page or on the SAP Fiori launchpad from the rectangular format to an in-line format. This reduces the space that is used. You perform the switch by changing the value of the `mode` property, but keeping all other settings as already set. After the switch, the control's ID and contents stay the same; only the header and subheader are rendered. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.GenericTileMode) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.GenericTileLineMode/preview).

-   `sap.m.HeaderContainer`: The `HeaderContainer` control has been moved from the `sap.suite.ui.commons` library to the `sap.m` library, to improve control consumption. The visual design of the control has been updated to SAP Fiori 2.0 and to the Belize theme. In addition, the API has been reworked to get a clear naming of properties, aggregations, events, and API descriptions. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.HeaderContainer) and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.HeaderContainer).

-   `sap.m.IconTabBar`:

    -   We have implemented drag and drop of tabs on desktop devices. Clicking and holding a tab lets you change its position in on the tab bar. The functionality is enabled with the `enableTabReordering` property.

    -   We have added a new property, `headerBackgroundDesign`, to change the header background and thus align with the new visual design. Possible values are `Solid`, `Transparent`, and `Translucent`.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.IconTabBar/methods/getEnableTabReordering) and the samples [Tabs Drag and Drop](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.IconTabBarDragDrop/preview) and [Background Design](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.IconTabBarBackgroundDesign/preview). 

-   `sap.m.List` and `sap.m.Table`: You can now highlight items, for example to indicate an error. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ListItemBase).

-   `sap.m.NotificationListItem` and `sap.m.NotificationListGroup`: We have implemented several new features:

    -   New aggregation \(`processingMessage`\) to provide a `sap.m.MessageStrip` notification within a `NotificationListItem`

         ![](loio2b1c9e05fad34795bb189c9c28975b1d_LowRes.png) 

    -   Notification list items are highlighted on mouse-over as with list items.

    -   We have added an event to trigger when the `NotificationListGroup` is expanded or collapsed. The event is called `onCollapse`.

    For more information, see the samples [Notification List Item](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.NotificationListItem/preview) and [Notification List Group with Max Number of Notifications Reached](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.MaxNumberOfNotificationsReached/preview). 

-   `sap.m.PlanningCalendar`: A new `week` view is now available for the `PlanningCalendar` control. It displays a full calendar week that alway starts from the first day of the week \(locale-dependent\) for the corresponding calendar types \(Gregorian, Islamic, Japanese\). For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.PlanningCalendar/preview).

-   `sap.m.Slider` and `sap.m.RangeSlider`: We have implemented responsive tickmarks for the slider controls. The tickmarks are enabled with the `enableTickmarks` property. The number of visible tickmarks depends on the step size and the slider minimum and maximum values. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Slider/methods/getEnableTickmarks) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.Slider/preview).

     ![](loiobf5c44ab603347caa69c729da549cd0f_LowRes.png) 

-   `sap.m.UploadCollection`: The sorting and filtering feature has been enhanced. You can now also display the *Filtered by* information in the info toolbar in the `UploadCollection` control. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.UploadCollection) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.UploadCollectionSortingFiltering/preview).

-   `sap.ui.table.*`:

    -   The sizing behavior of columns is now more predictable, especially when the user manually resizes columns. Columns now have a fixed minimum width.

    -   Keyboard handling has been optimized for navigation as well as editing scenarios.

    -   The default row height when using controls from the `sap.ui.commons` library is now the same as the general default. For more information, see [Content Densities](Content_Densities_e54f729.md).


***

### Documentation Changes

The **Testing** tutorial has been enhanced with two additional steps: [Testing](Testing_291c912.md)

The **Demo Kit** now has the following new features:

-   Several improvements are now available in the *Samples*:

    -   The Belize Deep theme can now be switched from the *Settings* menu.

    -   You can now copy the code from the code section of each control sample on a Combi device and paste it outside the *Samples*.

    -   *Deprecated Since* information is now available in the API descriptions so that it is easier to identify the version when deprecation took place.

    -   Downloaded samples that contain external \(utility\) resources can now be easily imported with less additional effort, for example, into SAP Web IDE 

-   The search feature in the *Icon Explorer* has been improved to find icons not only by name but also by metadata keywords.


