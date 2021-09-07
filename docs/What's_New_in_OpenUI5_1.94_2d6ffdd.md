<!-- loio2d6ffddd26dd41ba91a5cf1b38f6b0f6 -->

| loio |
| -----|
| 2d6ffddd26dd41ba91a5cf1b38f6b0f6 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/2d6ffddd26dd41ba91a5cf1b38f6b0f6) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/2d6ffddd26dd41ba91a5cf1b38f6b0f6)</div>

## What's New in OpenUI5 1.94

With this release OpenUI5 is upgraded from version 1.93 to 1.94.

***

<a name="loio2d6ffddd26dd41ba91a5cf1b38f6b0f6__section_yvs_ksr_2qb"/>

### Preview and Announcements

The following information concerns important upcoming changes. UI changes may have an impact on the user experience and may require test cases to be adapted.


<table>
<tr>
<th>

Type



</th>
<th>

Description



</th>
<th>

Available as of OpenUI5 Version



</th>
</tr>
<tr>
<td>

Announcement



</td>
<td>

**Reminder: Outdated Versions to Be Removed from the CDN**

For security reasons, versions that are no longer maintained will be removed from the UI5 content delivery network \(CDN\) one year after their end of maintenance. If a version is still in maintenance, patches of that version that are older than one year will also be removed. We have noted that a number of customers are still using such outdated versions or patches. If this affects you, please note that once these versions or patches are removed, your applications will break. Please update to a more recent version or patch. For more information, see: [Removing Outdated UI5 Versions from UI5 CDN](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/).



</td>
<td>

n/a



</td>
</tr>
</table>

***

<a name="loio2d6ffddd26dd41ba91a5cf1b38f6b0f6__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**OpenUI5 OData V2 Model**

We now provide the `sap.ui.model.odata.v2.Context#isTransient` method, which returns information about whether an entity created on the client is not yet saved in the back-end system.



</td>
</tr>
<tr>
<td>

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   Bound transition messages can now also be received in the `sap-messages` header. This can be useful if the payload, and hence any messages within the payload, is not available, for example in a success response of an action or function without corresponding return type. In this case, the server can send a bound transition message in the `sap-messages` header that the OData V4 model can forward to the message model.

-   XML templating can now process the `@com.sap.vocabularies.UI.v1.DoNotCheckScaleOfMeasureQuantity` annotation. This annotation prevents the validation of the number of decimals.

-   A new `@$ui5.node.groupLevelCount` instance annotation for data aggregation scenarios. It represents the number of direct children of a group node. For more information, see [Extension for Data Aggregation](Extension_for_Data_Aggregation_7d91431.md).




</td>
</tr>
<tr>
<td>

**Whitespaces Visualization**

We have created a new sample pattern that showcases how whitespaces can be enabled on the application level, for freestyle applications. For more information, see [Whitespaces Concept](Whitespaces_Concept_37deb0b.md) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.WhitespacePattern). 



</td>
</tr>
</table>

***

<a name="loio2d6ffddd26dd41ba91a5cf1b38f6b0f6__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

**`sap.m.IconTabBar`**

We have updated the colors of value-state status icons. Now, they have better color-contrast ratios for improved accessibility. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBar).



</td>
</tr>
<tr>
<td>

**`sap.m.Input`, `sap.m.MultiInput`**

We have introduced the `showClearIcon` property. If set to true, when there is text input it shows an additional icon that allows users to clear their input. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Input). 



</td>
</tr>
<tr>
<td>

**`sap.m.List`**

You can now adapt the default wrapping behavior for titles and descriptions in lists and define the number of characters after which wrapping is done by using the new `wrapCharLimit` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.StandardListItem%23methods/getWrapCharLimit) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.StandardListItem/sample/sap.m.sample.StandardListItemWrapping).



</td>
</tr>
<tr>
<td>

**`sap.m.MenuButton`**

We have introduced a new `beforeMenuOpen` event, fired when the arrow button of the `sap.m.MenuButton` in split mode is pressed, and before the dropdown menu opens. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.MenuButton) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.MenuButton/sample/sap.m.sample.MenuButton).



</td>
</tr>
<tr>
<td>

**`sap.m.PlanningCalendar`**

The new `firstDayOfWeek` property enables developers to set the first day of week that is displayed in the week-based views of the `PlanningCalendar` - `Week` view, and `OneMonth` view \(on small devices\). Valid values are 0 to 6 starting on Sunday. If there is no valid value set, the default from the user locale is used. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarWithLegend).



</td>
</tr>
<tr>
<td>

 **`sap.ui.integration.widgets.Card`**

We have updated the Microsoft Adaptive Cards SDK from version 1.2.3 to version 2.9.0, which will give us the possibility to adopt and consume the latest features and functionalities in future releases.



</td>
</tr>
</table>

***

<a name="loio2d6ffddd26dd41ba91a5cf1b38f6b0f6__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td>

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated). 



</td>
</tr>
</table>

