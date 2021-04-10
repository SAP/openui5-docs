<!-- loioe315108a469f4a729030299a3bc84b77 -->

| loio |
| -----|
| e315108a469f4a729030299a3bc84b77 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e315108a469f4a729030299a3bc84b77) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e315108a469f4a729030299a3bc84b77)</div>

## What's New in OpenUI5 1.87

With this release OpenUI5 is upgraded from version 1.86 to 1.87.

***

<a name="loioe315108a469f4a729030299a3bc84b77__section_yxw_pxt_zcb"/>

### New Features

|**End of Support for Microsoft Internet Explorer 11 after OpenUI5 1.87**

OpenUI5 1.87 is the last version to support Microsoft Internet Explorer 11. For more information, see [OpenUI5 Support Status for Microsoft Internet Explorer 11](Browser_and_Platform_Support_74b59ef.md#loio74b59efa0eef48988d3b716bd0ecc933__MS_IE).

|

***

<a name="loioe315108a469f4a729030299a3bc84b77__section_bkm_s15_zcb"/>

### New Controls

|**`sap.m.ExpandableText`**

You can use the control to display long texts, for example, inside a table, list, or form. Only the first characters from the text field and a `More` link are shown initially, which allows the full text to be displayed. There are two options for displaying the full text, which are defined by the `overflowMode` property - in place \(default\) or as a popover. The `maxCharacters` property specifies the maximum number of characters from the beginning of the text field, that are shown initially. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ExpandableText) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.ExpandableText).

|

***

<a name="loioe315108a469f4a729030299a3bc84b77__section_qwl_pb5_zcb"/>

### Improved Features

|**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   A new `additionally` property within the `group` map of the `$$aggregation` list binding parameter. This allows you to define properties that are fetched together with a group level, such as a text for a key. For more information, see [`sap.ui.model.odata.v4.ODataListBinding#setAggregation`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/setAggregation) and [Extension for Data Aggregation](Extension_for_Data_Aggregation_7d91431.md).

-   Support of the `sap.ui.model.odata.v4.Context#requestSideEffects` method in combination with kept-alive contexts. A list binding context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.

-   Evaluation of the `Org.OData.Core.V1.ContentID` instance annotation in messages of error responses to change sets, so that the message can be assigned to the correct request and the message target can be calculated correctly. For more information, see [Server Messages in the OData V4 Model](Server_Messages_in_the_OData_V4_Model_fbe1cb5.md).


For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

|

***

<a name="loioe315108a469f4a729030299a3bc84b77__section_rqn_wd5_zcb"/>

### Improved Controls

|**`sap.f.Card`**

We no longer apply default `min-height` in the control, which allows smaller cards to be rendered properly. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.Card).

|
|**`sap.f.GridList`**

We have improved the keyboard handling capabilities of the control. Now, similar to `sap.f.GridContainer`, the navigation with [Arrow\] keys follows the cells of the underlying \(virtual\) grid. This behavior provides stable navigation paths if there are items of different sizes. When any of the borders are reached, the `borderReached` event is fired. To navigate to another `GridList`, you have two options:

-   Navigate using the [Tab\] key.

-   Configure navigation with the [Arrow\] keys. This is achieved by using the `focusItemByDirection` method and requires additional logic from the application side to determine the navigation direction in the actual app layout.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridList) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.f.GridList).

|
|**`sap.m.BadgeCustomData`**

We have added a new `animation` property that enables you to choose the animation type to be performed by the badge element.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.BadgeCustomData).

|
|`**sap.m.Dialog**`

You can now drag and resize the dialog using the keyboard. To enable this behavior, you have to set the `draggable` and/or `resizable` properties to `true`. While the keyboard focus is located on the title bar, the dialog can then be moved with the [Arrow\] keys and resized with  [Shift\] + [Arrow\]  keys. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Dialog/sample/sap.m.sample.Dialog).

|
|**`sap.m.Image`**

With the new `lazyLoading` property, you can now ensure that off-screen images are loaded early enough so that they finish loading once the user scrolls near them.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Image).

|
|**`sap.m.PlanningCalendar`**

As an application developer you can now use the following new functions:

-   `GetEndDate` returns the end date that is visible in current state of the control.

-   `GetVisibleIntervalsCount` returns the number of intervals \(for example, hours, days, weeks\) that are currently visible.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar/methods).

|
|**`sap.m.Text`**

The new `emptyIndicatorMode` property allows developers to display an empty text as a language dependent “-” symbol. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Text).

|
|**`sap.m.Title`**

You can now place a link as a title. To enable this functionality, we have introduced the `content` aggregation, which accepts controls \(`sap.m.Link`\) that implement the [`sap.ui.core.ITitleContent`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.ITitleContent) interface. To place a link as a title you have to add the [`sap.m.Link`](https://openui5.hana.ondemand.com/#/api/sap.m.Link) control to the `content` aggregation. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Title).

|
|**`sap.ui.integration.widgets.Card`**

-   Integration cards now allow you to use arrays as values in the manifest parameters. One example scenario is to use an array parameter in expression binding inside the visible property and to display only the elements that have values. For more information, see the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/arrayParameters) in the Card Explorer.

-   Two new experimental actions are now available in the Calendar card that you can use to set dynamic data fetching to be dependent of the selected date/month:

-   `DateChange` – triggered when a date is selected.

-   `MonthChange` – triggered when the currently displayed month is changed from the pickers or from the arrow buttons.

Both `DateChange` and `MonthChange` actions are triggered when the `Today` button is pressed. For more information, see the [Samples](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/calendar/extension) and the [Calendar Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) section in the Card Explorer.

-   The `Extension` feature is no longer in experimental state. For more information, see the [Samples](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension) and the [Card Extension](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/extension) section in the Card Explorer.

|
|**`sap.ui.layout.cssgrid.ResponsiveColumnLayout`**

We have enhanced the layout with higher density of responsive breakpoints, providing flexibility and allowing developers to configure the grid settings and display the content in the best possible way. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.cssgrid.ResponsiveColumnLayout).

|

***

<a name="loioe315108a469f4a729030299a3bc84b77__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

|**Demo Kit HTML Title**

We’ve improved the HTML title tag of the Demo Kit app to contain more information about the page that is currently loaded. Now, if you have multiple tabs with different Demo Kit content loaded on them, you can see the specific page names directly from the browser tab.

|

