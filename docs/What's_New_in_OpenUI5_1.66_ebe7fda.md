<!-- loioebe7fda555aa466782090053d6f54f21 -->

| loio |
| -----|
| ebe7fda555aa466782090053d6f54f21 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ebe7fda555aa466782090053d6f54f21) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ebe7fda555aa466782090053d6f54f21)</div>

## What's New in OpenUI5 1.66

With this release OpenUI5 is upgraded from version 1.65 to 1.66.

***

<a name="loioebe7fda555aa466782090053d6f54f21__section_qwl_pb5_zcb"/>

### Improved Features

|**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   New events `createSent` and `createCompleted` on `v4.ODataListBinding`: These events are sent when a POST request for creating an entity is sent to the backend, and when it is completed. Note that the created promise of the new context is only resolved when the POST was successful.

-   `bAtEnd` parameter for the `v4.ODataListBinding.create` method: If this parameter is set, the new entity is added at the end of the list. Note that you must determine the length of the list using `$count`.

-   Format option `emptyString` defaults to 0 for `odata.type.Currency` and `odata.type.Unit`.

-   `v4.Context.requestSideEffects` can also be called on a context of a list binding representing a single entity and the header context of a list binding. For the latter, side effects are loaded for the whole binding.

-   Processing the ETag from the response header.


> Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).

|
|**Support for New Era in the Japanese Calendar**

Starting May 1, 2019, OpenUI5 supports a new era in the Japanese calendar, due to the imperial transition.

|

***

<a name="loioebe7fda555aa466782090053d6f54f21__section_rqn_wd5_zcb"/>

### Improved Controls

|**`sap.f.GridContainer` \(Experimental\)**

We have introduced three new properties:

-   `containerQuery` allows you to derive the layout breakpoints either based on the container surrounding the `sap.f.GridContainer` or the device screen size.

-   `allowDenseFill` is an experimental property that allows you to try out a denser arrangement of the grid items. Smaller items will take up all the available space, ignoring their order.

-    `inlineBlockLayout` is an experimental property. It allows you to arrange the items in rows with the height equal to the highest item in the row.


For more information, see [sap.f.GridContainer](sap.f.GridContainer_cca5ee5.md) and the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer). 

|
|**`sap.m.ComboBox`, `sap.m.MultiComboBox`**

The options list used in these controls is now instantiated lazily. The list is created primarily based on user interaction. As a result of the change, the initialization time of the controls has decreased significantly. For more information, see the samples \([`sap.m.ComboBox`](https://openui5.hana.ondemand.com/#/entity/sap.m.ComboBox), [`sap.m.MultiComboBox`](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiComboBox)\). 

|
|**`sap.m.DateRangeSelection`**

You can now change the date range value using keyboard combinations without opening the calendar. When the cursor is on the start date \(before the delimiter\), we change the start date and when it is on the end date \(after the delimiter\), we change the end date.

-   *PgUp*/*PgDn* - increments/decrements the date

-   * Shift PgUp */* Shift PgDn * - increments/decrements the month

-   * Ctrl Shift PgUp */* Ctrl Shift PgDn * - increments/decrements the year


For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.DateRangeSelection/sample/sap.m.sample.DateRangeSelection).

|
|**`sap.m.Input`**

We have adjusted the value state text for the `sap.m.Input` control. The value state text is now shown in the suggestion popover container when the `sap.m.Input` control has suggestions.

 For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Input) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Input). 

|
|**`sap.m.ObjectStatus`**

You can now switch the background and text colors using the new `inverted` property.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ObjectStatus).

|
|**`sap.m.Select`**

To be better aligned with the other input controls, we have implemented a new `editable` property for the `sap.m.Select` control. If `editable` is set to `false`, the interaction with the control is disabled but remains focusable, and its background color and borders are changed to indicate that it's read-only.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Select) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Select/sample/sap.m.sample.Select).

|
|**`sap.m.SinglePlanningCalendar`**

-   You can now include custom views to display different numbers of columns in the grid area of the control, for example, you can show only the first 10 days of each month. To create custom views, extend the `sap.m.SinglePlanningCalendarView` basic view class.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithCustomViews).

-   We have implemented a new `specialDates` aggregation, that allows you to define special dates for the control. They are visualized as a color bar in the header below the respective dates. In addition, you can add the assigned special dates to the associated `sap.m.PlanningCalendarLegend`.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithLegend).

-   The control can now display longer titles and texts of appointments on multiple lines depending on the length of the appointment.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithCustomViews).

-   We added an arrow indicator to improve the visual design of appointments which are not marked as *All-day* but do continue outside of the visible area.


|

***

<a name="loioebe7fda555aa466782090053d6f54f21__section_z2h_fh5_zcb"/>

### Documentation

|**OData V2 Messaging Documentation**

The OData V2 Messaging documentation has been enhanced and improved. See [Error, Warning, and Info Messages](Error,_Warning,_and_Info_Messages_62b1481.md).

|

