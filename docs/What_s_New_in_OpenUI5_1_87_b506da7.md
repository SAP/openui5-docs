<!-- loiob506da7781ca487195bc7177a8dea9d2 -->

| loio |
| -----|
| b506da7781ca487195bc7177a8dea9d2 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/b506da7781ca487195bc7177a8dea9d2) | [demo kit latest release](https://sdk.openui5.org/topic/b506da7781ca487195bc7177a8dea9d2)</div>

## What's New in OpenUI5 1.87

With this release OpenUI5 is upgraded from version 1.86 to 1.87.

***

****


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

1.87 



</td>
<td valign="top">

Deprecated 



</td>
<td valign="top">

Announcement 



</td>
<td valign="top">

**End of Support for Microsoft Internet Explorer 11 after OpenUI5 1.87** 



</td>
<td valign="top">

**End of Support for Microsoft Internet Explorer 11 after OpenUI5 1.87**

OpenUI5 1.87 is the last version to support Microsoft Internet Explorer 11. For more information, see [OpenUI5 Support Status for Microsoft Internet Explorer 11](Browser_and_Platform_Support_74b59ef.md#loio74b59efa0eef48988d3b716bd0ecc933__MS_IE).

<sub>Deprecated•Announcement•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.ExpandableText`** 



</td>
<td valign="top">

**`sap.m.ExpandableText`**

You can use the control to display long texts, for example, inside a table, list, or form. Only the first characters from the text field and a `More` link are shown initially, which allows the full text to be displayed. There are two options for displaying the full text, which are defined by the `overflowMode` property - in place \(default\) or as a popover. The `maxCharacters` property specifies the maximum number of characters from the beginning of the text field, that are shown initially. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ExpandableText) and the [Samples](https://sdk.openui5.org/entity/sap.m.ExpandableText).

<sub>New•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



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

-   A new `additionally` property within the `group` map of the `$$aggregation` list binding parameter. This allows you to define properties that are fetched together with a group level, such as a text for a key. For more information, see [`sap.ui.model.odata.v4.ODataListBinding#setAggregation`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding/methods/setAggregation) and [Extension for Data Aggregation](Extension_for_Data_Aggregation_7d91431.md).

-   Support of the `sap.ui.model.odata.v4.Context#requestSideEffects` method in combination with kept-alive contexts. A list binding context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.

-   Evaluation of the `Org.OData.Core.V1.ContentID` instance annotation in messages of error responses to change sets, so that the message can be assigned to the correct request and the message target can be calculated correctly. For more information, see [Server Messages in the OData V4 Model](Server_Messages_in_the_OData_V4_Model_fbe1cb5.md).


For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.f.Card`** 



</td>
<td valign="top">

**`sap.f.Card`**

We no longer apply default `min-height` in the control, which allows smaller cards to be rendered properly. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.Card).

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.f.GridList`** 



</td>
<td valign="top">

**`sap.f.GridList`**

We have improved the keyboard handling capabilities of the control. Now, similar to `sap.f.GridContainer`, the navigation with [Arrow\] keys follows the cells of the underlying \(virtual\) grid. This behavior provides stable navigation paths if there are items of different sizes. When any of the borders are reached, the `borderReached` event is fired. To navigate to another `GridList`, you have two options:

-   Navigate using the [Tab\] key.

-   Configure navigation with the [Arrow\] keys. This is achieved by using the `focusItemByDirection` method and requires additional logic from the application side to determine the navigation direction in the actual app layout.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.GridList) and the [Samples](https://sdk.openui5.org/entity/sap.f.GridList).

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.BadgeCustomData`** 



</td>
<td valign="top">

**`sap.m.BadgeCustomData`**

We have added a new `animation` property that enables you to choose the animation type to be performed by the badge element.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.BadgeCustomData).

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Dialog`** 



</td>
<td valign="top">

**`sap.m.Dialog`**

You can now drag and resize the dialog using the keyboard. To enable this behavior, you have to set the `draggable` and/or `resizable` properties to `true`. While the keyboard focus is located on the title bar, the dialog can then be moved with the [Arrow\] keys and resized with [Shift\] + [Arrow\]  keys. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Dialog/sample/sap.m.sample.Dialog).

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Image`** 



</td>
<td valign="top">

**`sap.m.Image`**

With the new `lazyLoading` property, you can now ensure that off-screen images are loaded early enough so that they finish loading once the user scrolls near them.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Image).

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.PlanningCalendar`** 



</td>
<td valign="top">

**`sap.m.PlanningCalendar`**

As an application developer you can now use the following new functions:

-   `GetEndDate` returns the end date that is visible in current state of the control.

-   `GetVisibleIntervalsCount` returns the number of intervals \(for example, hours, days, weeks\) that are currently visible.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar/methods).

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Text`** 



</td>
<td valign="top">

**`sap.m.Text`**

The new `emptyIndicatorMode` property allows developers to display an empty text as a language dependent “-” symbol. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Text).

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Title`** 



</td>
<td valign="top">

**`sap.m.Title`**

You can now place a link as a title. To enable this functionality, we have introduced the `content` aggregation, which accepts controls \(`sap.m.Link`\) that implement the [`sap.ui.core.ITitleContent`](https://sdk.openui5.org/api/sap.ui.core.ITitleContent) interface. To place a link as a title you have to add the [`sap.m.Link`](https://sdk.openui5.org/api/sap.m.Link) control to the `content` aggregation. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Title).

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`** 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   Integration cards now allow you to use arrays as values in the manifest parameters. One example scenario is to use an array parameter in expression binding inside the visible property and to display only the elements that have values. For more information, see the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/arrayParameters) in the Card Explorer.

-   Two new experimental actions are now available in the Calendar card that you can use to set dynamic data fetching to be dependent of the selected date/month:

    -   `DateChange` – triggered when a date is selected.

    -   `MonthChange` – triggered when the currently displayed month is changed from the pickers or from the arrow buttons.


    Both `DateChange` and `MonthChange` actions are triggered when the `Today` button is pressed. For more information, see the [Samples](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/calendar/extension) and the [Calendar Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) section in the Card Explorer.

-   The `Extension` feature is no longer in experimental state. For more information, see the [Samples](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension) and the [Card Extension](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/extension) section in the Card Explorer.

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.ui.layout.cssgrid.ResponsiveColumnLayout`** 



</td>
<td valign="top">

**`sap.ui.layout.cssgrid.ResponsiveColumnLayout`**

We have enhanced the layout with higher density of responsive breakpoints, providing flexibility and allowing developers to configure the grid settings and display the content in the best possible way. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.cssgrid.ResponsiveColumnLayout).

<sub>Changed•Control•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
<tr>
<td valign="top">

1.87 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Demo Kit HTML Title** 



</td>
<td valign="top">

**Demo Kit HTML Title**

We’ve improved the HTML title tag of the Demo Kit app to contain more information about the page that is currently loaded. Now, if you have multiple tabs with different Demo Kit content loaded on them, you can see the specific page names directly from the browser tab.

<sub>Changed•Feature•Info Only•1.87</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-02-25



</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.116](What_s_New_in_OpenUI5_1_116_ebd6f34.md "With this release OpenUI5 is upgraded from version 1.115 to 1.116.")

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

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

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

