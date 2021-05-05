<!-- loioa8449849c81249bb8abd98b4b9342a4a -->

| loio |
| -----|
| a8449849c81249bb8abd98b4b9342a4a |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a8449849c81249bb8abd98b4b9342a4a) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a8449849c81249bb8abd98b4b9342a4a)</div>

## What's New in OpenUI5 1.50

With this release, OpenUI5 is upgraded from version 1.48 to 1.50.

***

<a name="loioa8449849c81249bb8abd98b4b9342a4a__section_qfc_g5h_fbb"/>

### New Demo Kit \(already available as of version 1.48.5\)

The Demo Kit app has a new modern design that is intuitive and can be used on both desktop and mobile devices.

The global search has been improved and the results are now displayed in categories. They also include results from the *Samples* section, which was not possible with the old Demo Kit since the *Explored* app was a decoupled app.

|-   Landing page with getting started information

-   *Documentation* with detailed information

-    *API Reference* with JavaScript documentation about the framework and the UI controls, including details for the corresponding properties, aggregations, associations, events, and methods

-   *Samples*, showcasing almost all controls with ability to download the sample code

-   *Demo Apps*, showcasing real-life scenarios that can easily be downloaded


| SAPUI5 Highlights   

|

***

<a name="loioa8449849c81249bb8abd98b4b9342a4a__section_ewk_q4b_31b"/>

### New Features

-   The Unicode Common Locale Data Repository \(CLDR\) has been updated to version 31.

-   The correct plural category for a given number is now handled by the locale-specific plural rules offered by CLDR. Different languages use different plural forms, some languages have only singular and plural, others require additional forms, for example, dual \(two\), paucal \(few\), or many.

-   -   `sap.ui.model.type.DateInterval` - a date interval \(without time\)

-   `sap.ui.model.type.DateTimeInterval` - a date interval with the exact point of time

-   `sap.ui.model.type.TimeInterval` - a time interval \(without date\)

    For more information, see [sap.ui.model.type.DateTimeInterval](sap.ui.model.type.DateTimeInterval_94658aa.md) and the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.type). 

-   The configuration option `animationMode` replaces `animation`, which is now deprecated. The new option supports several states \(`full`, `basic`, `minimal`, `none`\), which allow controls to extend support for animations in a more granular way instead of a binary `on`/`off` state. For more information, see [Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md), [76b7d5065cf64304a1d2841046043c34.md](), and the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Configuration.AnimationMode). 


***

### New Controls

-   `sap.m.PlanningCalendarLegend`: Enables two types of items to be displayed in the `sap.m.PlanningCalendar` as a legend - types of days \(for example, special dates and holidays\) and appointments. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendarLegend).

     ![](loioe8f3d352f8044779a3d90e37c0e9798e_LowRes.png) 


***

### Improved Features

***

#### OpenUI5 OData V4 Model

The new version of the OpenUI5 OData V4 model introduces an adapter that allows you to use an OData V2 service together with the OData V4 model in read scenarios. The adapter offers the following features:

-   Metadata is converted, including some V2 annotations.

-   Data in the response is converted.

-   Literals in the request URI are converted, except for `Edm.DateTime`, `Edm.DateTimeOffset`, `Edm.Time`, and `Edm.Binary`.

-   `$select`, `$expand`, and `$orderby` are handled. Cases that are not supported by OData V2, like `$orderby` in `$expand`, lead to an error.

-   All unsupported query options lead to an error.


> ### Caution:  
> **Incompatibility Due to a Bug Fix**
> 
> The following bug has been reported: If you call the [sap.ui.model.odata.v4.Context\#getObject\(\)](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/getObject) or the [sap.ui.model.odata.v4.Context\#requestObject\(\)](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/requestObject) methods without a parameter, the expected and documented behavior is that the same result is returned as if the parameter `sPath=""` had been specified. However, due to the bug, the return value wraps the expected output that can then only be accessed via `.value[0]`, for example `oContext.getObject().value[0]`.
> 
> **If you have used this workaround, your application will break starting with OpenUI5 version 1.44.6.**
> 
> **Solution**: If your application needs to run with both the fixed and unfixed versions of OpenUI5, specify the `sPath=""` parameter, for the `sPath` parameter. In both cases, you **must not** use the workaround with `.value[0]` any longer.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

***

#### Support Assistant: OPA Test Sample Added

With the roll-out of Support Assistant in version 1.48, we introduced the possibility to use the tool in OPA tests to check if there are issues in the different states of an application. This is possible by enabling the available OPA extension.

As of this version, there is now a sample of the OPA integration in the Demo Kit. It demonstrates how you can extend existing OPA tests by making calls to the assertions in the Support Assistant extension. These assertions may have different severity, execution scope and subset of rules which are taken into consideration. The sample also shows how to execute rule checks and how to get reports.

As of this version, there is now a sample of the OPA integration in the Demo Kit. For more information, see [Integrating the Rules in OPA Tests](Integrating_the_Rules_in_OPA_Tests_cfabbd4.md) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.core.sample.OpaWithSupportAssistant/preview).

***

### Improved Controls

-   `sap.f.DynamicPage` has the following new features:

    -   You can now define the priority of the `DynamicPageTitle` areas with the use of the new `primaryArea` property. The primary area shrinks at a slower rate, remaining visible as long as possible.

    -   With the new content aggregation of the `DynamicPageTitle`, you can add content in the middle area of the title. This content is displayed both in the expanded and collapsed states of the `DynamicPageHeader`.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPageTitle).

-   `sap.f.semantic.SemanticPage`: To align with the latest SAP Fiori design guidelines, the following changes were implemented:

    -   The position of the draft indicator is changed to be the first one before the finalizing actions in the footer toolbar of the page.

    -   A new *Edit* button was added as the main action and the order of the actions changed to *Edit*, *Delete*, *Copy*, and *Add*.

    For more information, see [Semantic Page \(sap.f\)](Semantic_Page_(sap.f)_47dc868.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.semantic), and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.SemanticPage/preview).

-   `sap.m.Label` has the following new properties:

    -   `wrapping`: Determines whether text within a label is wrapped. The default value is `false`. If set to `false`, the label text only uses one line and any exceeding text is truncated and replaced with an ellipsis. When you use the `Label` within a `sap.m.Form` the label text is automatically displayed as wrapped.

         ![](loioa18049e61af44b0d9f766dc0d743ea0b_LowRes.png) 

    -    `displayOnly`: Determines whether the label is in `displayOnly` mode. Controls in this mode are non-interactive, non-focusable, cannot be edited, and do not form part of the tab chain. The `displayOnly` property is used in `Form` controls when they are in preview mode.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Label) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Label).

-   `sap.m.MessageStrip` now supports a limited set of formatting tags for the text. The available tags are `<a>`, `<em>`, `<strong>`, and `<u>`. To enable the additional formatting tags, you have to set the `enableFormattedText` property to `true`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.MessageStrip) and the [Samples](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.MessageStripWithEnableFormattedText/preview).

-   `sap.m.Panel` has a new parameter for the `expand` event that identifies whether the user or the application is expanding or collapsing the `Panel` control. The parameter is called `triggeredByInteraction` and is `true` when the panel is expanded as a result of a user action. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Panel) and the [Samples](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.PanelExpanded/preview).

-   `sap.m.PlanningCalendar`:
    -   You can now directly navigate to a date with fewer clicks.

    -   With the use of the new `builtInViews` property the app developer can now define which of the built-in views are displayed. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.PlanningCalendarViews/preview).

    -   To save space, the days are now displayed on the same line as the dates. If you want to display the day names on a separate line, set the `showDayNamesLine` property to `true`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.PlanningCalendarSingle/preview).

-   `sap.m.ProgressIndicator`: You can now set the control in a display-only state using the new `displayOnly` property. When set to `true`, the control has different visualization and is not active, not editable, and cannot be focused. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ProgressIndicator) and the [Samples](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.ProgressIndicator/preview).

-   `sap.m.RatingIndicator`: A new state can be set using the `displayOnly` property. It enables visually distinguishable rendering of the `RatingIndicator` \(gray color\), denoting it as non-interactive in forms. All controls in this mode are also non-focusable and not part of the tab chain. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.RatingIndicator) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.RatingIndicator/preview).

     ![](loioe38d0425a1d44102a6834a9efe0d95be_LowRes.png) 

-   `sap.m.semantic.SemanticPage`. You can now set the background color of the page using the new `backgroundDesign` property. For more information, see [Semantic Page \(sap.m\)](Semantic_Page_(sap.m)_4a97a07.md) and the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.semantic.SemanticPage).

-   `sap.m.UploadCollection`: `UploadCollectionItem` has been extended to display folders in the `UploadCollection` control. When you click the file name or item thumbnail, you can perform custom actions by adding an event handler to the `press` event. With the `deletePress` event, you can control the deletion of an item. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.UploadCollectionItem) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.UploadCollectionFolderHierarchy/preview).

-   `sap.m.Tree`: The `toggleOpenState` event has been added. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Tree) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TreeJSONLazyLoading/preview).

-   `sap.ui.unified.Calendar`: The days of the previous/next month are no longer visible whenever the `sap.ui.unified.Calendar` displays multiple months. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.unified.Calendar) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.unified.sample.CalendarMultipleMonth/preview).

-   `sap.ui.layout.form.Form` and `sap.ui.layout.form.SimpleForm`: The samples, including the descriptions, have been simplified and are now more consistent. For more information, see the [Form](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.form.Form) and the [SimpleForm](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.form.SimpleForm) samples.


