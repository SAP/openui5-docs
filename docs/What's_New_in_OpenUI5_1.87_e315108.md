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


<table>
<tr>
<td>

**End of Support for Microsoft Internet Explorer 11 after OpenUI5 1.87**

OpenUI5 1.87 is the last version to support Microsoft Internet Explorer 11. For more information, see [OpenUI5 Support Status for Microsoft Internet Explorer 11](Browser_and_Platform_Support_74b59ef.md#loio74b59efa0eef48988d3b716bd0ecc933__MS_IE).



</td>
</tr>
</table>

***

<a name="loioe315108a469f4a729030299a3bc84b77__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td>

**`sap.m.ExpandableText`**

You can use the control to display long texts, for example, inside a table, list, or form. Only the first characters from the text field and a `More` link are shown initially, which allows the full text to be displayed. There are two options for displaying the full text, which are defined by the `overflowMode` property - in place \(default\) or as a popover. The `maxCharacters` property specifies the maximum number of characters from the beginning of the text field, that are shown initially. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ExpandableText) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.ExpandableText).



</td>
</tr>
</table>

***

<a name="loioe315108a469f4a729030299a3bc84b77__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   A new `additionally` property within the `group` map of the `$$aggregation` list binding parameter. This allows you to define properties that are fetched together with a group level, such as a text for a key. For more information, see [`sap.ui.model.odata.v4.ODataListBinding#setAggregation`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/setAggregation) and [Extension for Data Aggregation](Extension_for_Data_Aggregation_7d91431.md).

-   Support of the `sap.ui.model.odata.v4.Context#requestSideEffects` method in combination with kept-alive contexts. A list binding context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.

-   Evaluation of the `Org.OData.Core.V1.ContentID` instance annotation in messages of error responses to change sets, so that the message can be assigned to the correct request and the message target can be calculated correctly. For more information, see [Server Messages in the OData V4 Model](Server_Messages_in_the_OData_V4_Model_fbe1cb5.md).


For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.



</td>
</tr>
</table>

***

<a name="loioe315108a469f4a729030299a3bc84b77__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

**`sap.f.Card`**

We no longer apply default `min-height` in the control, which allows smaller cards to be rendered properly. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.Card).



</td>
</tr>
<tr>
<td>

**`sap.f.GridList`**

We have improved the keyboard handling capabilities of the control. Now, similar to `sap.f.GridContainer`, the navigation with [Arrow\] keys follows the cells of the underlying \(virtual\) grid. This behavior provides stable navigation paths if there are items of different sizes. When any of the borders are reached, the `borderReached` event is fired. To navigate to another `GridList`, you have two options:

-   Navigate using the [Tab\] key.

-   Configure navigation with the [Arrow\] keys. This is achieved by using the `focusItemByDirection` method and requires additional logic from the application side to determine the navigation direction in the actual app layout.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridList) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.f.GridList). 



</td>
</tr>
<tr>
<td>

**`sap.m.BadgeCustomData`**

We have added a new `animation` property that enables you to choose the animation type to be performed by the badge element.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.BadgeCustomData).



</td>
</tr>
<tr>
<td>

`**sap.m.Dialog**`

You can now drag and resize the dialog using the keyboard. To enable this behavior, you have to set the `draggable` and/or `resizable` properties to `true`. While the keyboard focus is located on the title bar, the dialog can then be moved with the [Arrow\] keys and resized with  [Shift\] + [Arrow\]  keys. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Dialog/sample/sap.m.sample.Dialog).



</td>
</tr>
<tr>
<td>

**`sap.m.Image`**

With the new `lazyLoading` property, you can now ensure that off-screen images are loaded early enough so that they finish loading once the user scrolls near them.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Image).



</td>
</tr>
<tr>
<td>

**`sap.m.PlanningCalendar`**

As an application developer you can now use the following new functions:

-   `GetEndDate` returns the end date that is visible in current state of the control.

-   `GetVisibleIntervalsCount` returns the number of intervals \(for example, hours, days, weeks\) that are currently visible.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar/methods). 



</td>
</tr>
<tr>
<td>

**`sap.m.Text`**

The new `emptyIndicatorMode` property allows developers to display an empty text as a language dependent “-” symbol. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Text).



</td>
</tr>
<tr>
<td>

**`sap.m.Title`**

You can now place a link as a title. To enable this functionality, we have introduced the `content` aggregation, which accepts controls \(`sap.m.Link`\) that implement the [`sap.ui.core.ITitleContent`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.ITitleContent) interface. To place a link as a title you have to add the [`sap.m.Link`](https://openui5.hana.ondemand.com/#/api/sap.m.Link) control to the `content` aggregation. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Title).



</td>
</tr>
<tr>
<td>

**`sap.ui.integration.widgets.Card`**

-   Integration cards now allow you to use arrays as values in the manifest parameters. One example scenario is to use an array parameter in expression binding inside the visible property and to display only the elements that have values. For more information, see the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/arrayParameters) in the Card Explorer.

-   Two new experimental actions are now available in the Calendar card that you can use to set dynamic data fetching to be dependent of the selected date/month:

    -   `DateChange` – triggered when a date is selected.

    -   `MonthChange` – triggered when the currently displayed month is changed from the pickers or from the arrow buttons.

    Both `DateChange` and `MonthChange` actions are triggered when the `Today` button is pressed. For more information, see the [Samples](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/calendar/extension) and the [Calendar Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) section in the Card Explorer.

-   The `Extension` feature is no longer in experimental state. For more information, see the [Samples](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension) and the [Card Extension](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/extension) section in the Card Explorer.



</td>
</tr>
<tr>
<td>

**`sap.ui.layout.cssgrid.ResponsiveColumnLayout`**

We have enhanced the layout with higher density of responsive breakpoints, providing flexibility and allowing developers to configure the grid settings and display the content in the best possible way. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.cssgrid.ResponsiveColumnLayout).



</td>
</tr>
</table>

***

<a name="loioe315108a469f4a729030299a3bc84b77__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td>

**Demo Kit HTML Title**

We’ve improved the HTML title tag of the Demo Kit app to contain more information about the page that is currently loaded. Now, if you have multiple tabs with different Demo Kit content loaded on them, you can see the specific page names directly from the browser tab.



</td>
</tr>
</table>

**Parent topicColonSymbol** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.94](What's_New_in_OpenUI5_1.94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What's_New_in_OpenUI5_1.93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What's_New_in_OpenUI5_1.92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What's_New_in_OpenUI5_1.91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What's_New_in_OpenUI5_1.90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What's_New_in_OpenUI5_1.89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What's_New_in_OpenUI5_1.88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

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

[What's New in OpenUI5 1.69](What's_New_in_OpenUI5_1.69_41203fd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

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

