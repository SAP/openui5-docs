<!-- loiof21858fa6a07451c9cb86e0c023a7092 -->

| loio |
| -----|
| f21858fa6a07451c9cb86e0c023a7092 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f21858fa6a07451c9cb86e0c023a7092) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f21858fa6a07451c9cb86e0c023a7092)</div>

## What's New in OpenUI5 1.97

With this release OpenUI5 is upgraded from version 1.96 to 1.97.

***

<a name="loiof21858fa6a07451c9cb86e0c023a7092__section_vvy_452_rrb"/>

### Preview and Announcements

The following information concerns important upcoming changes. UI changes may have an impact on the user experience and may require test cases to be adapted.


<table>
<tr>
<th valign="top">

Type



</th>
<th valign="top">

Description



</th>
<th valign="top">

Available as of OpenUI5 Version



</th>
</tr>
<tr>
<td valign="top">

Announcement



</td>
<td valign="top">

**Reminder: Outdated Versions to Be Removed from the CDN**

For security reasons, versions that are no longer maintained will be removed from the UI5 content delivery network \(CDN\) one year after their end of maintenance. If a version is still in maintenance, patches of that version that are older than one year will also be removed. We have noted that a number of customers are still using such outdated versions or patches. If this affects you, please note that once these versions or patches are removed, your applications will break. Please update to a more recent version or patch. For more information, see: [Removing Outdated UI5 Versions from UI5 CDN](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/).



</td>
<td valign="top">

n/a



</td>
</tr>
</table>

> ### Note:  
> Content marked as **Preview** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/viewer/wnp_disclaimer).

***

<a name="loiof21858fa6a07451c9cb86e0c023a7092__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   If the parent context of an operation binding is a row context of a list binding, and the result of the operation fulfills the criteria for a return value context, you can now replace that row context with the result of the operation. For more information, see the `sap.ui.model.odata.v4.ODataContextBinding#execute` method, and in particular the `bReplaceWithRVC` parameter.

-   We have introduced the `sap.ui.model.odata.v4.Context#replaceWith` method. You can use it to replace a row context of a list binding by a kept-alive context that is not part of the collection. Such a context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.

-   You can now apply the `sort`, `filter`, `changeParameters`, and `suspend` methods to an `sap.ui.model.odata.v4.ODataListBinding` despite changes in kept-alive contexts or bindings relative to kept-alive contexts of the list. Accordingly, `sap.ui.model.odata.v4.ODataListBinding#hasPendingChanges` has been extended with a `bIgnoreKeptAlive` parameter.

-   The `sap.ui.model.odata.v4.ODataListBinding#filter` and `sap.ui.model.odata.v4.ODataListBinding#sort` methods do not reset the binding if the filters or sorters are unchanged.




</td>
</tr>
</table>

***

<a name="loiof21858fa6a07451c9cb86e0c023a7092__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.Avatar`**

With the new `decorative` property, you can now set the `Avatar` control to be used only for decorative purposes and to be ignored by accessibility tools.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.MessagePage).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.ComboBox`, `sap.m.MultiComboBox`**

We have introduced the `showClearIcon` property. If set to `true`, when there is text input it shows an additional icon that allows users to clear their input. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ComboBox/sample/sap.m.sample.ComboBoxClearIcon) for `sap.m.ComboBox` and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiComboBox/sample/sap.m.sample.MultiComboBoxClearIcon) for `sap.m.MultiComboBox`.



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.DatePicker`, `sap.m.DateRangeSelection`, `sap.m.DateTimePicker`, and `sap.m.TimePicker`**

These controls can now be opened by another control. To enable this feature, we have introduced a new `hideInput` property that hides the input field of the corresponding control. In this case, the only way to open the picker popover is by calling the `openBy` method. This new feature minimizes the visual footprint of the controls, which is useful when more controls are placed together. For more information, see the [DatePicker](https://openui5.hana.ondemand.com/#/entity/sap.m.DatePicker/sample/sap.m.sample.DatePickerHidden), [DateRangeSelection](https://openui5.hana.ondemand.com/#/entity/sap.m.DateRangeSelection/sample/sap.m.sample.DateRangeSelectionHidden), [DateTimePicker](https://openui5.hana.ondemand.com/#/entity/sap.m.DateTimePicker/sample/sap.m.sample.DateTimePickerHidden), and [TimePicker](https://openui5.hana.ondemand.com/#/entity/sap.m.TimePicker/sample/sap.m.sample.TimePickerHidden) samples.



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.DateTimePicker`**

The control now implements the new dial-based design for the time picker.For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.DateTimePicker).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.DynamicDateRange` \(Experimental\)**

We have added a new standard option named `DATETOYEAR` - a period from today to the end of the year. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.DynamicDateRange).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.MessagePage`**

With the new `titleLevel` property, we have enabled app developers to set a custom aria-level of the `MessagePage` title.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.MessagePage).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.PlanningCalendar`**

We have introduced a new `multipleAppointmentsSelection` property that allows mobile users to select multiple appointments. If set to `true`, every mouse click or tap on an appointment will lead to selection. The selection of multiple appointments using the [CTRL\] key is possible regardless of the value of this property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarOneLine).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

Timeline cards now support actions defined on an item level. These actions can be handled by the application in the same way as actions of the List card items.For more information, see the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/timeline) in the Card Explorer.



</td>
</tr>
</table>

***

<a name="loiof21858fa6a07451c9cb86e0c023a7092__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated). 



</td>
</tr>
</table>

***

<a name="loiof21858fa6a07451c9cb86e0c023a7092__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td valign="top">

**Demo Kit News Section with Notifications**

We implemented a *News* section with notifications where you can get highlights on important news about OpenUI5. When we upload new information, you’ll see a notification bell with a counter in the main toolbar.

![](loiofe57420a441440c3bad48ca4a02eaf0f_HiRes.png)



</td>
</tr>
</table>

