<!-- loio7aacb4e107c44c90b5b0dd97fcb1f333 -->

| loio |
| -----|
| 7aacb4e107c44c90b5b0dd97fcb1f333 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/7aacb4e107c44c90b5b0dd97fcb1f333) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/7aacb4e107c44c90b5b0dd97fcb1f333)</div>

## What's New in OpenUI5 1.98

With this release OpenUI5 is upgraded from version 1.97 to 1.98.

***

<a name="loio7aacb4e107c44c90b5b0dd97fcb1f333__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   The `sap.ui.model.odata.v2.ODataListBinding#create` method, which allows to create transient entries in a list binding similar to its counterpart in the OData V4 model. For more information, see [Creating Entities](OData_V2_Model_6c47b2b.md#loio4c4cd99af9b14e08bb72470cc7cabff4).

-   You can now create inactive contexts using `sap.ui.model.odata.v2.ODataListBinding#create`. There is no POST request for an inactive context. The context will become active as soon as any of its properties is changed. Once this happens, the `createActivate` event is raised, enabling the application to create a new inactive context.

    Inactive contexts do not influence `sap.ui.model.odata.v2.ODataListBinding#getCount`. They are neither pending changes nor are they reset by `sap.ui.model.odata.v2.ODataModel#resetChanges`. For more information, see [Creating Entities](OData_V2_Model_6c47b2b.md#loio4c4cd99af9b14e08bb72470cc7cabff4).

-   The `getAllCurrentContexts` method for list bindings returns all current contexts without raising a request.For more information, see [`sap.ui.model.ListBinding#getAllCurrentContexts`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.ListBinding%23methods/getAllCurrentContexts).




</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   You can now replace a row context of a list with a sibling entity of the same collection. The sibling entity must be available as a :1 navigation property and is accessed with an operation binding. For more information, see [Draft Handling with the OData V4 Model](Draft_Handling_with_the_OData_V4_Model_40986e6.md).

-   An application can now create inactive contexts in a list binding using the `bInactive` parameter of `sap.ui.model.odata.v4.ODataListBinding#create`, provided the update group of the binding is an `Auto` group. There is no POST request for an inactive context. The context will become active as soon as any of its properties is changed. Once this happens, the `createActivate` event is raised, enabling the application to create a new inactive context.

    Inactive contexts do not influence `sap.ui.model.odata.v4.ODataListBinding#getCount`. They are neither pending changes nor are they reset by `sap.ui.model.odata.v4.ODataListBinding#resetChanges` or `sap.ui.model.odata.v4.ODataModel#resetChanges`. For more information, see [Creating an Entity](Creating_an_Entity_c9723f8.md).

-   The `sap.ui.model.odata.v4.ODataListBinding#getAllCurrentContexts` method returns all current contexts without raising a request.

-   The experimental `sap.ui.model.odata.v4.ODataContextBinding#moveEntityTo` method introduced with OpenUI5 1.95 is deprecated.




</td>
</tr>
</table>

***

<a name="loio7aacb4e107c44c90b5b0dd97fcb1f333__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.DateTimePicker` and `sap.m.TimePicker`**

We have introduced a shortcut button that focuses the current time. The button is shown if the new `showCurrentTimeButton` property is set to true. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.TimePicker) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.TimePicker/sample/sap.m.sample.TimePicker).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.DynamicDateRange` \(Experimental\)**

-   When the user types something in the input field of the control, the displayed suggestion items now appear in groups if the `enableGroupHeaders` property is set to `true`.

-   We have added new standard options to the control that represent the first or the last day of the current week, month, quarter, or year.

-   The `StandardDynamicDateRangeKeys` is now an enumeration with keys matching the values. The default value of the `DynamicDateRange` control’s `options` property is now a full array of the keys \(before it was an empty array\).


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.DynamicDateRange) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.DynamicDateRange).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.IconTabBar`**

There is a change in the way how the control computes and displays the number of tabs that are in the overflow buttons at both sides of the tabs area, when the property overflow mode is set to `StartAndEnd`. Now, only the top-level tabs are counted and not the nested sub-tabs. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.IconTabBar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarStartAndEndOverflow).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Label`**

We have introduced a new `showColon` property. If set to `true`, a colon \(:\) character is added to the label. This feature is useful in cases when the Label is used independently. In contrast, when the Label is in a Form or in a Simple Form, the colon \(:\) character is displayed automatically regardless of the value of the `showColon` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Label).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.List`**

You can now display an avatar in your list instead of an image or icon. We have integrated the `sap.m.Avatar` control as an aggregation of `StandardListItem`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.StandardListItem%23aggregations) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.StandardListItem/sample/sap.m.sample.StandardListItemAvatar).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.p13n*`**

We have made personalization within a table or list more reusable. Different panels with reusable content for the various types of personalization are now available for freestyle use in your application.

The following panels are available:

-   `sap.m.p13n.SelectionPanel`

    Defines a number of properties that allow you to select and deselect fields as columns in your table, for example, and to change their order.

-   `sap.m.p13n.SortPanel`

    Defines a number of properties that allow you to sort your items based on various criteria, for example, in ascending or descending order.

-   `sap.m.p13n.GroupPanel`

    Defines a number of properties that allow you to group your data.


The panels are aggregated to `sap.m.p13n.Popup`, which serves as a container for all the panels.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.p13n) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.p13n.Popup/sample/sap.m.sample.p13n.Popup).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.SinglePlanningCalendar`**

With the new `firstDayOfWeek` property, you can now set the first day of a week displayed in the Week and Month views of the control. If there is no valid value set, the default from the user locale is used. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarSnappingHeader).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.upload.UploadSet`**

For the `uploadCompleted` event, an additional JSON response object is now passed. Along with it, some of its parameters are also passed such as response, `responseXML`, `readyState`, status, and headers. It helps you to understand if the upload is complete.



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have introduced a new filter type – Search \(experimental\). To define it, you only have to set the filter's `type` property to `Search`, and then specify the optional initial value of the filter and the placeholder of the field. For more information, see the [Search Filter](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/filters/search) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/searchFilter) in the Card Explorer.

-   Integration cards now support \(experimentally\) CSRF tokens as a method to prevent CSRF attacks. For more information, see the [CSRF Tokens](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/csrfTokens) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/data/csrf) in the Card Explorer.

-   The submit action of the Adaptive card supports binding syntax. This allows card developers to map the values entered by the end user to the payload structure expected by the back-end service. For more information, see the [Action Handlers](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/actionHandlers) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/adaptive-action-submit-custom-payload) in the Card Explorer.

-   We have added support for more HTTP request methods. Together with GET and POST, Integration cards now also support PUT, PATCH, DELETE, OPTIONS, and HEAD methods. For more information, see the [Data Handling](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/data) section in the Card Explorer.

-   Object cards are \(experimentally\) enhanced with new item types and a new attribute. The new item types are `NumericData`, which shows some KPIs, and `Status`. The new attribute is `maxLines` - it represents the maximum number of lines the text can take. For more information, see the [Object Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) section, the [To Do Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/todoCard) sample, and [Additional Object Details](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/additionalObjectDetails) sample in the Card Explorer.




</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have updated the `sap.ui.integration.widgets.Card` of type Adaptive with the new 1.01 version of UI5 Web Components. For more information, see the [Adaptive Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) section in the Card Explorer.
-   We have updated the `sap.ui.integration.widgets.Card` of type Adaptive to support the newest templating and markdown features available for Microsoft Adaptive Cards, by getting the latest versions of `adaptivecards-templating`, `adaptive-expressions`, and `markdown-it`. Due to changes in the templating syntax, developers should adapt their applications when they switch to version 1.98. For more information, see the [Adaptive Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) section and the [Templating](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/templating) and [Markdown](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/markdown) Samples in the Card Explorer. 



</td>
</tr>
</table>

***

<a name="loio7aacb4e107c44c90b5b0dd97fcb1f333__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

**`sap.f.IllustratedMessage` / `sap.m.IllustratedMessage`**

The `sap.f.IllustratedMessage` and its related classes are now moved to the `sap.m` library. The `sap.f` classes and their documentation are kept for compatibility reasons and are marked as deprecated. All of them extend their `sap.m` version.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.IllustratedMessage).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.P13n*`**

The following entities have been deprecated and replaced with the new personalization panels:

-   `sap.m.P13nDialog`

-   `sap.m.P13nColumnsPanel`

-   `sap.m.P13nSortPanel`

-   `sap.m.P13nGroupPanel`


 For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated).



</td>
</tr>
</table>

