<!-- loio9d2b1897722a4e99b60580fb09aa35e0 -->

| loio |
| -----|
| 9d2b1897722a4e99b60580fb09aa35e0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9d2b1897722a4e99b60580fb09aa35e0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9d2b1897722a4e99b60580fb09aa35e0)</div>

## What's New in OpenUI5 1.65

With this release OpenUI5 is upgraded from version 1.64 to 1.65.

***

<a name="loio9d2b1897722a4e99b60580fb09aa35e0__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td>

**New Theme Available**

A new theme with *SAP Quartz Light* as the default appearance \(theme ID `sap_fiori_3`\) has been introduced. The theme is provided as an additional theme in OpenUI5.

For more information, see [Supported Combinations of Themes and Libraries](Supported_Combinations_of_Themes_and_Libraries_38ff8c2.md).



</td>
</tr>
</table>

***

<a name="loio9d2b1897722a4e99b60580fb09aa35e0__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td>

**`sap.f.GridContainer (Experimental)`**

The new `GridContainer` control allows you to align tiles, cards, and other controls in configuration, such as an overview page. It relies on a regular grid mesh constructed of rows with the same height and columns with the same width. Each item can be configured to span a different number of rows and columns inside that mesh. `GridContainer` automatically calculates how many rows an item needs, based on the height of the item.

 ![](loio2916482f87df4b91afabd81d6070fc78_HiRes.png) 

For more information, see [sap.f.GridContainer](sap.f.GridContainer_cca5ee5.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer), and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainer).



</td>
</tr>
</table>

***

<a name="loio9d2b1897722a4e99b60580fb09aa35e0__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   You can now create more than one transient entity in a list binding without refreshing the list binding, see `sap.ui.model.odata.v4.ODataListBinding` in the API Reference.

-   It is now ensured that created and persisted records are shown only once in the list, and that `$count` reflects the number of records shown in the table. Duplicates are avoided by filtering out created and persisted records using system query option `$filter`.

-   You can use `@$ui5.context.isTransient` in expression bindings to find out whether context is transient, see `sap.ui.model.odata.v4.Context.isTransient` in the API Reference.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).



</td>
</tr>
<tr>
<td>

**Test Automation**

The setup for Karma-based test automation has been improved significantly: The corresponding plugin has been completely reworked and renamed to `karma-ui5`.

For more information, see [Installing Karma for Automated Testing](Test_Automation_ae44824.md#loioa182676ed3714bd5b4f011eb29076f6c) and [karma-ui5 on Github](https://help.sap.com/viewer/disclaimer-for-links?q=https%3A%2F%2Fgithub.com%2FSAP%2Fkarma-openui5).



</td>
</tr>
</table>

***

<a name="loio9d2b1897722a4e99b60580fb09aa35e0__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

**`sap.f.Avatar`**

With the new `fallbackIcon` property, you can define a fallback icon to be displayed if the image `src` is incorrect and no `initials` are set. If `fallbackIcon` is not set, a default fallback icon is displayed depending on the value of the `displayShape` property.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.Avatar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.Avatar/sample/sap.f.sample.Avatar).



</td>
</tr>
<tr>
<td>

**`sap.f.DynamicPage`**

-   We have implemented a new sticky subheader in the `DynamicPage` control. It is positioned below the `DynamicPageHeader` and is always visible \(sticks to the `DynamicPageTitle` when the header is collapsed\). You can implement the subheader with the new `stickySubheader` association, which accepts controls that implement the `sap.f.IDynamicPageStickyContent` interface.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPage) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.DynamicPage/sample/sap.f.sample.DynamicPageWithStickySubheader).

-   We have improved the visual design of the content set in the `snappedContent` and `expandedContent` aggregations of `sap.f.DynamicPageTitle`. The width of the content set in these aggregations and the `heading` aggregation are no longer dependent.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.DynamicPage/sample/sap.f.sample.DynamicPageFreeStyle).




</td>
</tr>
<tr>
<td>

**`sap.f.ShellBar`**

The control is no longer experimental. To comply with the latest UX guidelines, its child controls have a predefined semantic order and are displayed in their cozy content density mode with dark visual design.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.ShellBar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.ShellBar/sample/sap.f.sample.ShellBar).



</td>
</tr>
<tr>
<td>

**`sap.m.Select`**

We have improved the `sap.m.Select` control to display the text set in the `valueStateText` property on multiple lines when the dropdown list is opened. The implementation ensures that the value state text is displayed even though it is longer than the width of the `sap.m.Select` container.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Select) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Select/sample/sap.m.sample.SelectValueState).



</td>
</tr>
<tr>
<td>

**`sap.m.SinglePlanningCalendar`**

-   You can now change the start and end date of appointments by selecting and dragging their top or bottom end and dropping it on the desired time interval. Use the new `enableAppointmentsResize` property to enable the feature.

-   You can now create appointments by clicking and dragging. Select a start \(or end\) time interval in an empty cell, start dragging up \(or down\) over the time intervals to determine the desired time interval. Use the new `enableAppointmentsCreate` property to enable the feature.

-   We have improved the visual design of appointments that are shorter than 30 minutes. The color bar at the left border of appointments now has variable height to represent the time interval accurately. For appointments that are 30 minutes or longer, it fills 100% of the height.

-   You can now focus on individual cells in the `SinglePlanningCalendar` and navigate between them using the keyboard. When pressing the [Space\] or [Enter\] key on a focused cell, the new `cellPress` event is fired, which can be used for creating an appointment.

-   We have improved the visual design of the control by adding a shadow effect below the sticky header so that it is easier for the user to recognize the line between the fixed header and the scrollable content.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar).



</td>
</tr>
<tr>
<td>

**`sap.m.ToolbarSeparator`**

We have enabled the control to move to the overflow area of `sap.m.OverflowToolbar` where it changes its layout from vertical to horizontal. If the control happens to be the first or the last item of the overflow area, it is not displayed.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.OverflowToolbar/sample/sap.m.sample.OverflowToolbarSimple).



</td>
</tr>
<tr>
<td>

**`sap.ui.core.hyphenation.Hyphenation`**

We have changed the `leftmin` and `rightmin` properties for all languages, with the default value of 3 characters. `leftmin` defines the minimum of characters to remain on the previous line, and `rightmin` defines the minimum of characters to move to the new line.For more information, see [Hyphenation for Text Controls](Hyphenation_for_Text_Controls_6322164.md) and the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.hyphenation.Hyphenation). 



</td>
</tr>
<tr>
<td>

**`sap.ui.integration.widgets.Card`**

-   We have introduced a new `Table` card type, that displays a set of items in a table format. Table cards use the responsive UI5 control `sap.m.Table`.

-   We have introduced a new experimental card type - `Component` card. It is used to display multiple controls. The `Component` card is used as a custom approach for use cases that do not fit in other card types and structures. The content area of the unstructured content card can be moved to the top.

    > ### Note:  
    > In contrast to the other integration card types, the structure and behavior of the `Component` card are custom-definable and follow the established OpenUI5 Component model. For more information, see [Components](Components_958ead5.md).


For more information, see [Cards](Cards_5b46b03.md), the [API Reference](https://openui5.hana.ondemand.com//#/api/sap.ui.integration.widgets.Card), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.integration.widgets.Card).



</td>
</tr>
<tr>
<td>

**`sap.uxap.ObjectPageHeader`**

-   We have improved the visual appearance of the image placed in `ObjectPageHeader` to be identical with the styling of the `sap.f.Avatar` control.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.uxap.ObjectPageLayout/sample/sap.uxap.sample.ObjectPageDynamicHeader).

-   When the user presses an action from the overflow area, a dialog should open and the action sheet should close. To notify the app developer that the action is in the overflow area, we now pass an additional `bInOverflow` parameter along with the `press` event of the control set in the `actions` aggregation of the `sap.uxap.ObjectPageHeader`.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.uxap.ObjectPageHeader).



</td>
</tr>
</table>

***

<a name="loio9d2b1897722a4e99b60580fb09aa35e0__section_z2h_fh5_zcb"/>

### Documentation and Training


<table>
<tr>
<td>

**New openSAP Course: Evolved Web Apps with SAPUI5**

We have launched a new openSAP course on how to develop professional web apps with UI5. Key highlights:

-   Evolved best practices and recommendations for app developers
-   New UI5 innovations \(drag and drop, OData V4, XML composites\)
-   Developer productivity tools and features in SAP Web IDE
-   Optimizing apps with the UI5 Tooling
-   Configuring apps for SAP Fiori elements and SAP Fiori launchpad
-   Adapting apps with SAPUI5 flexibility

The key concepts shown in this course apply to both, SAPUI5 and OpenUI5. The course is aimed at intermediate to advanced developers but is also suitable for ambitious UI5 beginners. Participation is free of charge.

For more information and to enroll, see [https://open.sap.com/courses/ui52](https://open.sap.com/courses/ui52).

 ![](loio56cac78b078f4cf3ada1fc92a9430182_LowRes.png) 



</td>
</tr>
</table>

***

<a name="loio9d2b1897722a4e99b60580fb09aa35e0__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td>

**Demo Kit Search**

We have improved the global search capabilities in the Demo Kit app by migrating to a client-side search based on Elasticlunr.js.

 ![](loio36a8538c55c3402b9c7adef4df7cba2c_HiRes.png) 



</td>
</tr>
</table>

