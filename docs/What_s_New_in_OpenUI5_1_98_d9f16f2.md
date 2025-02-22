<!-- loiod9f16f2262a947ef9cd5b58f11c54b6e -->

| loio |
| -----|
| d9f16f2262a947ef9cd5b58f11c54b6e |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/d9f16f2262a947ef9cd5b58f11c54b6e) | [demo kit latest release](https://sdk.openui5.org/topic/d9f16f2262a947ef9cd5b58f11c54b6e)</div>

## What's New in OpenUI5 1.98

With this release OpenUI5 is upgraded from version 1.97 to 1.98.

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

1.98 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V2 Model** 

</td>
<td valign="top">

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   The `sap.ui.model.odata.v2.ODataListBinding#create` method, which allows to create transient entries in a list binding similar to its counterpart in the OData V4 model. For more information, see [Creating Entities](OData_V2_Model_6c47b2b.md#loio4c4cd99af9b14e08bb72470cc7cabff4).

-   You can now create inactive contexts using `sap.ui.model.odata.v2.ODataListBinding#create`. There is no POST request for an inactive context. The context will become active as soon as any of its properties is changed. Once this happens, the `createActivate` event is raised, enabling the application to create a new inactive context.

    Inactive contexts do not influence `sap.ui.model.odata.v2.ODataListBinding#getCount`. They are neither pending changes nor are they reset by `sap.ui.model.odata.v2.ODataModel#resetChanges`. For more information, see [Creating Entities](OData_V2_Model_6c47b2b.md#loio4c4cd99af9b14e08bb72470cc7cabff4).

-   The `getAllCurrentContexts` method for list bindings returns all current contexts without raising a request.For more information, see [`sap.ui.model.ListBinding#getAllCurrentContexts`](https://sdk.openui5.org/api/sap.ui.model.ListBinding%23methods/getAllCurrentContexts).


<sub>Changed•Feature•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

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

-   You can now replace a row context of a list with a sibling entity of the same collection. The sibling entity must be available as a :1 navigation property and is accessed with an operation binding. For more information, see [Draft Handling with the OData V4 Model](Draft_Handling_with_the_OData_V4_Model_40986e6.md).

-   An application can now create inactive contexts in a list binding using the `bInactive` parameter of `sap.ui.model.odata.v4.ODataListBinding#create`, provided the update group of the binding is an `Auto` group. There is no POST request for an inactive context. The context will become active as soon as any of its properties is changed. Once this happens, the `createActivate` event is raised, enabling the application to create a new inactive context.

    Inactive contexts do not influence `sap.ui.model.odata.v4.ODataListBinding#getCount`. They are neither pending changes nor are they reset by `sap.ui.model.odata.v4.ODataListBinding#resetChanges` or `sap.ui.model.odata.v4.ODataModel#resetChanges`. For more information, see [Creating an Entity in a Collection](Creating_an_Entity_in_a_Collection_c9723f8.md).

-   The `sap.ui.model.odata.v4.ODataListBinding#getAllCurrentContexts` method returns all current contexts without raising a request.

-   The experimental `sap.ui.model.odata.v4.ODataContextBinding#moveEntityTo` method introduced with OpenUI5 1.95 is deprecated.


<sub>Changed•Feature•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.DateTimePicker`, `sap.m.TimePicker`** 

</td>
<td valign="top">

**`sap.m.DateTimePicker`, `sap.m.TimePicker`**

We have introduced a shortcut button that focuses the current time. The button is shown if the new `showCurrentTimeButton` property is set to true. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TimePicker) and the [Sample](https://sdk.openui5.org/entity/sap.m.TimePicker/sample/sap.m.sample.TimePicker).

<sub>Changed•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.DynamicDateRange` \(Experimental\)** 

</td>
<td valign="top">

**`sap.m.DynamicDateRange` \(Experimental\)**

-   When the user types something in the input field of the control, the displayed suggestion items now appear in groups if the `enableGroupHeaders` property is set to `true`.

-   We have added new standard options to the control that represent the first or the last day of the current week, month, quarter, or year.

-   The `StandardDynamicDateRangeKeys` is now an enumeration with keys matching the values. The default value of the `DynamicDateRange` control’s `options` property is now a full array of the keys \(before it was an empty array\).


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DynamicDateRange) and the [Samples](https://sdk.openui5.org/entity/sap.m.DynamicDateRange).

<sub>Changed•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.IconTabBar`** 

</td>
<td valign="top">

**`sap.m.IconTabBar`**

There is a change in the way how the control computes and displays the number of tabs that are in the overflow buttons at both sides of the tabs area, when the property overflow mode is set to `StartAndEnd`. Now, only the top-level tabs are counted and not the nested sub-tabs. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IconTabBar) and the [Sample](https://sdk.openui5.org/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarStartAndEndOverflow).

<sub>Changed•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Label`** 

</td>
<td valign="top">

**`sap.m.Label`**

We have introduced a new `showColon` property. If set to `true`, a colon \(:\) character is added to the label. This feature is useful in cases when the Label is used independently. In contrast, when the Label is in a Form or in a Simple Form, the colon \(:\) character is displayed automatically regardless of the value of the `showColon` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Label).

<sub>Changed•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.List`** 

</td>
<td valign="top">

**`sap.m.List`**

You can now display an avatar in your list instead of an image or icon. We have integrated the `sap.m.Avatar` control as an aggregation of `StandardListItem`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.StandardListItem%23aggregations) and the [Sample](https://sdk.openui5.org/entity/sap.m.StandardListItem/sample/sap.m.sample.StandardListItemAvatar).

<sub>Changed•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.p13n*`** 

</td>
<td valign="top">

**`sap.m.p13n*`**

We have made personalization within a table or list more reusable. Different panels with reusable content for the various types of personalization are now available for freestyle use in your application.

The following panels are available \(as experimental APIs\):

-   `sap.m.p13n.SelectionPanel`

    Defines a number of properties that allow you to select and deselect fields as columns in your table, for example, and to change their order.

-   `sap.m.p13n.SortPanel`

    Defines a number of properties that allow you to sort your items based on various criteria, for example, in ascending or descending order.

-   `sap.m.p13n.GroupPanel`

    Defines a number of properties that allow you to group your data.


The panels are aggregated to `sap.m.p13n.Popup` \(experimental\), which serves as a container for all the panels.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.p13n) and the [Sample](https://sdk.openui5.org/entity/sap.m.p13n.Popup/sample/sap.m.sample.p13n.Popup).

<sub>Changed•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`** 

</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`**

With the new `firstDayOfWeek` property, you can now set the first day of a week displayed in the Week and Month views of the control. If there is no valid value set, the default from the user locale is used. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarSnappingHeader).

<sub>Changed•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.upload.UploadSet`** 

</td>
<td valign="top">

**`sap.m.upload.UploadSet`**

For the `uploadCompleted` event, an additional JSON response object is now passed. Along with it, some of its parameters are also passed such as response, `responseXML`, `readyState`, status, and headers. It helps you to understand if the upload is complete.

<sub>Changed•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

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

-   We have introduced a new filter type – Search \(experimental\). To define it, you only have to set the filter's `type` property to `Search`, and then specify the optional initial value of the filter and the placeholder of the field. For more information, see the [Search Filter](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/filters/search) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/searchFilter) in the Card Explorer.

-   Integration cards now support \(experimentally\) CSRF tokens as a method to prevent CSRF attacks. For more information, see the [CSRF Tokens](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/csrfTokens) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/data/csrf) in the Card Explorer.

-   The submit action of the Adaptive card supports binding syntax. This allows card developers to map the values entered by the end user to the payload structure expected by the back-end service. For more information, see the [Action Handlers](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/actionHandlers) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/adaptive-action-submit-custom-payload) in the Card Explorer.

-   We have added support for more HTTP request methods. Together with GET and POST, Integration cards now also support PUT, PATCH, DELETE, OPTIONS, and HEAD methods. For more information, see the [Data Handling](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/data) section in the Card Explorer.

-   Object cards are \(experimentally\) enhanced with new item types and a new attribute. The new item types are `NumericData`, which shows some KPIs, and `Status`. The new attribute is `maxLines` - it represents the maximum number of lines the text can take. For more information, see the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) section, the [To Do Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/todoCard) sample, and [Additional Object Details](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/additionalObjectDetails) sample in the Card Explorer.

-   We have updated the `sap.ui.integration.widgets.Card` of type Adaptive with the new 1.01 version of UI5 Web Components. For more information, see the [Adaptive Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) section in the Card Explorer.
-   We have updated the `sap.ui.integration.widgets.Card` of type Adaptive to support the newest templating and markdown features available for Microsoft Adaptive Cards, by getting the latest versions of `adaptivecards-templating`, `adaptive-expressions`, and `markdown-it`. Due to changes in the templating syntax, developers should adapt their applications when they switch to version 1.98. For more information, see the [Adaptive Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) section and the [Templating](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/templating) and [Markdown](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/markdown) Samples in the Card Explorer. 

<sub>Changed•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.IllustratedMessage` / `sap.m.IllustratedMessage`** 

</td>
<td valign="top">

**`sap.f.IllustratedMessage` / `sap.m.IllustratedMessage`**

The `sap.f.IllustratedMessage` and its related classes are now moved to the `sap.m` library. The `sap.f` classes and their documentation are kept for compatibility reasons and are marked as deprecated. All of them extend their `sap.m` version.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.IllustratedMessage).

<sub>Deprecated•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
<tr>
<td valign="top">

1.98 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.P13n*`** 

</td>
<td valign="top">

**`sap.m.P13n*`**

The following entities have been deprecated and replaced with the new personalization panels:

-   `sap.m.P13nDialog`

-   `sap.m.P13nColumnsPanel`

-   `sap.m.P13nSortPanel`

-   `sap.m.P13nGroupPanel`


<sub>Deprecated•Control•Info Only•1.98</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2022-01-27

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.132](What_s_New_in_OpenUI5_1_132_bd2e61f.md "With this release OpenUI5 is upgraded from version 1.131 to 1.132.")

[What's New in OpenUI5 1.131](What_s_New_in_OpenUI5_1_131_7d24d94.md "With this release OpenUI5 is upgraded from version 1.130 to 1.131.")

[What's New in OpenUI5 1.130](What_s_New_in_OpenUI5_1_130_85609d4.md "With this release OpenUI5 is upgraded from version 1.129 to 1.130.")

[What's New in OpenUI5 1.129](What_s_New_in_OpenUI5_1_129_d22b8af.md "With this release OpenUI5 is upgraded from version 1.128 to 1.129.")

[What's New in OpenUI5 1.128](What_s_New_in_OpenUI5_1_128_1f76220.md "With this release OpenUI5 is upgraded from version 1.127 to 1.128.")

[What's New in OpenUI5 1.127](What_s_New_in_OpenUI5_1_127_e5e1317.md "With this release OpenUI5 is upgraded from version 1.126 to 1.127.")

[What's New in OpenUI5 1.126](What_s_New_in_OpenUI5_1_126_1d98116.md "With this release OpenUI5 is upgraded from version 1.125 to 1.126.")

[What's New in OpenUI5 1.125](What_s_New_in_OpenUI5_1_125_9d87044.md "With this release OpenUI5 is upgraded from version 1.124 to 1.125.")

[What's New in OpenUI5 1.124](What_s_New_in_OpenUI5_1_124_7f77c3f.md "With this release OpenUI5 is upgraded from version 1.123 to 1.124.")

[What's New in OpenUI5 1.123](What_s_New_in_OpenUI5_1_123_9d00ac7.md "With this release OpenUI5 is upgraded from version 1.122 to 1.123.")

[What's New in OpenUI5 1.122](What_s_New_in_OpenUI5_1_122_5d078da.md "With this release OpenUI5 is upgraded from version 1.121 to 1.122.")

[What's New in OpenUI5 1.121](What_s_New_in_OpenUI5_1_121_91a4a2f.md "With this release OpenUI5 is upgraded from version 1.120 to 1.121.")

[What's New in OpenUI5 1.120](What_s_New_in_OpenUI5_1_120_2359b63.md "With this release OpenUI5 is upgraded from version 1.119 to 1.120.")

[What's New in OpenUI5 1.119](What_s_New_in_OpenUI5_1_119_0b1903a.md "With this release OpenUI5 is upgraded from version 1.118 to 1.119.")

[What's New in OpenUI5 1.118](What_s_New_in_OpenUI5_1_118_3eecbde.md "With this release OpenUI5 is upgraded from version 1.117 to 1.118.")

[What's New in OpenUI5 1.117](What_s_New_in_OpenUI5_1_117_029d3b4.md "With this release OpenUI5 is upgraded from version 1.116 to 1.117.")

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

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_b506da7.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

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

