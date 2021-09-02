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

***

<a name="loio2d6ffddd26dd41ba91a5cf1b38f6b0f6__section_g3r_bf5_zcb"/>

### SAP Fiori Elements


<table>
<tr>
<td>

The following changes and new features are available for SAP Fiori elements for OData V4:

-   The search field is now also available in the table toolbar on the object page. If the table is searchable \(that is, if an entity set is used for which `sap:searchable` is `true`\), the search field is displayed by default. For more information, see [Tables](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/c0f6592a592e47f9bb6d09900de47412.html "Both the list report and the object page support several table types.") :arrow_upper_right:.

-   When using multi-selection in tables, the *Select All* checkbox has been disabled by default in responsive tables in the list report, and on the object page in tab bar mode. End users can undo the selection using the *Clear All* checkbox. For more information, see [Enabling Multiple Selection in Tables](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/116b5d82e8c545e2a56e1b51b8b0a9bd.html "This feature enables you to configure whether end users can select a single row or multiple rows in a table while triggering table toolbar actions that require context.") :arrow_upper_right:.

-   Application developers can now display a field as a `TextArea` in edit mode or as an `ExpandableText` in display mode. For more information, see [Different Representations of a Field](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/c18ada4bc56e427a9a2df2d1898f28a5.html "Applications can control how the field is represented by using annotations or metadata.") :arrow_upper_right:.

-   App developers can now use fractional digits on visual filters. For more information, see [Visual Filters](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/1714720cae984ad8b9d9111937e7cd38.html "An intuitive way of choosing filter values from an associated measure value.") :arrow_upper_right:.

-   SAP Fiori elements for OData V4 now supports upload and delete functionalities for `Edm.stream` properties. For more information, see [Different Representations of a Field](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/c18ada4bc56e427a9a2df2d1898f28a5.html "Applications can control how the field is represented by using annotations or metadata.") :arrow_upper_right:.

-   SAP Fiori elements for OData V4 now supports the equal split mode for side content. For more information, see [Adding Dynamic Side Content to Object Page Sections](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/8e01a463d3984bfa8b23c2270d40e38c.html "Sometimes it might be necessary to add additional information that is not available with annotations to object page sections or subsections.") :arrow_upper_right:.

-   Application developers can now add actions for each form on the object page. For more information, see [Adding Custom Actions Using Extension Points](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/7619517a92414e27b71f02094bd08d06.html "You can use extension points to add custom actions to the list report and the object page.") :arrow_upper_right: and [Adding Action Buttons to Forms in Sections](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/e64efdad5bdf4264b54052bd7ab2229a.html "You can add action buttons to the forms contained in sections. These forms are indicated by com.sap.vocabularies.UI.v1.FieldGroup. A form action button is then displayed in the toolbar of the object page section that contains the form.") :arrow_upper_right:.




</td>
</tr>
</table>

