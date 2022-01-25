<!-- loioe9c83569a4a54f04a349c4152358f4ff -->

| loio |
| -----|
| e9c83569a4a54f04a349c4152358f4ff |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e9c83569a4a54f04a349c4152358f4ff) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e9c83569a4a54f04a349c4152358f4ff)</div>

## What's New in OpenUI5 1.93

With this release OpenUI5 is upgraded from version 1.92 to 1.93.

***

<a name="loioe9c83569a4a54f04a349c4152358f4ff__section_s1b_bfh_3rb"/>

### New Features


<table>
<tr>
<td valign="top">

**New Theme Available for SAP Fiori User Experience \(Experimental\)**

We have introduced a new theme with 1.93.3, the preview version of the *Horizon* visual theme for SAP Fiori \(theme ID: `sap_horizon`\), as an addition to the existing themes. To preview the new theme, see [https://openui5.hana.ondemand.com/?sap-ui-theme=sap\_horizon\#/controls](https://openui5.hana.ondemand.com/?sap-ui-theme=sap_horizon#/controls).

> ### Note:  
> The theme has the status 'experimental' and thus is subject to change. It must not be used as a basis for custom themes as long as the status is 'experimental'.



</td>
</tr>
</table>

***

<a name="loioe9c83569a4a54f04a349c4152358f4ff__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 Data Types**

The new version of OpenUI5 introduces a new `skipDecimalsValidation` constraint for the `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency` data types. It allows you to switch off validation on the number of decimals.



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   An OData V2-specific context, `sap.ui.model.odata.v2.Context`. Methods of the OData V2 model now return this context instead of the basis context, `sap.ui.model.Context`.

-   The new `sap.ui.model.ListBinding#getCount` method, which returns the count of entries in a list.




</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   A `search` property in the `$$aggregation` binding parameter that allows you to specify a search that is executed before the aggregation. Note that this requires the service to support the `search` transformation in `$apply`. For more information, see [Search Before Data Aggregation](Extension_for_Data_Aggregation_7d91431.md#loio7d914317c0b64c23824bf932cc8a4ae1__section_SBDA).

-   A `retryAfter` property in the technical details of a message originating from a response with a `Retry-After` header. For more information, see [Accessing the HTTP Status Code](Server_Messages_in_the_OData_V4_Model_fbe1cb5.md#loiofbe1cb5613cf4a40a841750bf813238e__section_httpStatus).




</td>
</tr>
</table>

***

<a name="loioe9c83569a4a54f04a349c4152358f4ff__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.f.DynamicPage`**

With the new `headerPinned` property and `headerContentPinnedStateChange` event, you can now control the pinned state of the `DynamicPageHeader` programmatically.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPage).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.IconTabBar`**

-   We have updated the design of the overflow tab according to the latest SAP Fiori guidelines.

    ![](loio90cdc6e0465245ea88856a64eb2f3bfa_LowRes.png)

    Additionally, when using the `StartAndEnd` tab overflow mode, both overflow tabs will display the number of tabs that they hold.

    ![](loiod507f84c6a874e65b56ccce1cc540b99_LowRes.png)

    For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarStartAndEndOverflow).

-   When the control is used in `Inline` header mode, icons can be added in front of the tab-filter titles. This allows, for example, the `sap.m.IconTabBar` control to be used as a horizontal navigation in the `sap.tnt.ToolHeader`. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarInlineIcons).




</td>
</tr>
<tr>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`**

We have provided a new toggle option in multi-selection mode for these controls: If the new `multiSelectMode` property has the `Default` value, the table renders the *Select All* checkbox in the column header as before. If the value of the property is `ClearAll`, the *Select All* checkbox and the related feature are no longer available. The list or table then provides an option to deselect all selected items at once. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase%23methods/getMultiSelectMode) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Table/sample/sap.m.sample.TableMultiSelectMode).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.MultiComboBox`**

We have the range selection functionality in `sap.m.MultiComboBox`. Two new parameters have been introduced to the `selectionChange` event: `changedItems` and `selectAll`. Users can now select a group of items by holding the [Shift\] key and selecting the checkboxes of the first and the last items from the desired group. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiComboBox/sample/sap.m.sample.MultiComboBox).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.PlanningCalendar`**

-   Application developers can now define relative timeframes that are different from the absolute values in the calendar. A relative view displays periods that are relative to a given custom start date. Common use-case scenarios include Week X, Day X \(since the start of a project\), etc. This feature is in experimental state. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendarView) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarRelativeViews). 

-   We have introduced \(in experimental state\) a way to place custom content inside the `CalendarAppointment` control for non-SAP Fiori \(custom\) applications with a freestyle nature. When the `customContent` aggregation is used, the `title`, `text`, `description`, and `icon` properties of the appointment are ignored. The application developer must ensure that all of the accessibility requirements are met, and that the height of the content conforms with the height provided by the appointment. We do not recommend using interactive controls as content, as they may trigger unwanted selection of the appointment with unpredictable results. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.unified.CalendarAppointment).




</td>
</tr>
<tr>
<td valign="top">

**`sap.m.SelectDialog`, `sap.m.TableSelectDialog`**

The `updateStarted`, `updateFinished`, and `selectionChange` events from an inner list or a table are now exposed to the `sap.m.SelectDialog` and `sap.m.TableSelectDialog` controls. Application developers can use these events to achieve lazy loading with JSON model. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SelectDialog/sample/sap.m.sample.SelectDialogLazyLoading).



</td>
</tr>
<tr>
<td valign="top">

**`sap.tnt.ToolPage`**

We have added a new `subHeader` aggregation to the control. You can use it to create a horizontal navigation bar in the tool page layout. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.tnt.ToolPage/sample/sap.tnt.sample.ToolPageNavigation).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have introduced a Configuration Editor tool that supports the card integration process on the customer side. Roles that can use the Configuration Editor include local administrators, page/content administrators, and translators. For more information, see the [Configuration Editor](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/designtime/overview) section and a [Card Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list) in the Card Explorer.

-   We have added \(in experimental state\) a new feature, and now Integration cards can have a footer with actionable buttons. Additionally, the List type card is enhanced and now list items support the same actionable buttons, including the option to remove the item. This behavior is achieved using the new `actionsStrip` \(experimental\) property that describes all buttons and their behavior. For more information, see the [Footer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/footer), and [List Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/list) sections, and the [Footer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/footer) and [List Card Quick Actions](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/quickActions) samples in the Card Explorer.




</td>
</tr>
<tr>
<td valign="top">

**`sap.uxap.ObjectPageLayout`**

With the new `headerContentPinned` property and `pinnedStateChange` event, you can now control the pinned state of the `DynamicPageHeader` programmatically.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.uxap.ObjectPageLayout).



</td>
</tr>
</table>

***

<a name="loioe9c83569a4a54f04a349c4152358f4ff__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated). 



</td>
</tr>
</table>

***

<a name="loioe9c83569a4a54f04a349c4152358f4ff__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td valign="top">

**Change Version Dialog**

We have improved the *Change Version* dialog to help you find the desired version faster. We grouped the patch numbers according to minor version, and we added a search field.

![](loio859079fb6af543689477c5e4713c2973_HiRes.png)



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.95](What's_New_in_OpenUI5_1.95_1b09465.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What's_New_in_OpenUI5_1.94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.92](What's_New_in_OpenUI5_1.92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What's_New_in_OpenUI5_1.91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What's_New_in_OpenUI5_1.90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What's_New_in_OpenUI5_1.89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What's_New_in_OpenUI5_1.88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What's_New_in_OpenUI5_1.87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

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

